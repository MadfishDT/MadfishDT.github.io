## libdmg build

libdmg-hfsplus is library to make dmg files on linux system
(this is tested in ubuntu)
### libdmg github
- [download source](https://github.com/planetbeing/libdmg-hfsplus)
```shell
    $ git clone https://github.com/  planetbeing/libdmg-hfsplus.git .
    Cloning into '.'...
    remote: Enumerating objects: 5511, done.
    remote: Total 5511 (delta 0), reused 0 (delta 0), pack-reused 5511
    Receiving objects: 100% (5511/5511), 30.58
```

### Install basic build package install 
- install build-essential
    ```
    sudo apt-get install build-essential
    ```

- install 'cmake'
    ```
    sudo apt-get install cmake
    ```
- install 'make'
    ```
    sudo apt-get install make
    ```

### Install library package

- libdmg-hfsplus explain how to build but this explaination included assumption that zlib source is in dmg directory

- to build dmg lib first of all install 'zlib development package'
    ```
    sudo apt-get install -y zlib1g-dev
    ```

- Second install open ssl 
    ```
    sudo apt-get install -y openssl
    ```

### build

- to build DMG libaray in libdmg source, bellow command is official 
    ```
    cd dmg/zlib-1.2.3
    ./configure
    make
    cd ..
    make
    ```
- but this way is not good way, becasue we have to download zlib source and build it
- so I just using zlib package(zlib1g-dev)
    ```
    $ cd dmg
    $ cmake ./CMakeLists.txt 
    $ make
    ```
- it make error, because header files path so it is not right way.
- actually all of header files is in includes folder, so if you want include headers, you should build on root folder
- just run cmake command in source root folder
    ```
    $cmake ./CmakeLists.txt
    ```
- cmake makes build configs and make files
- and make package
    ```
    $make dmg
    $cd dmg
    $make
    ```
- into dmg folder and command 'make', 
- first 'make dmg' make dmg.a library, second go into dmg foler and 'make' create dmg binary.
- if build is success, you can see dmg binary in ./dmg folder
- unfortunatly sombody can see error like
    - 'error: field ‘hmacCTX’ has incomplete type' error
    - this error
    - the reason happen this error is open ssl API. 
    - HMAC_CTX is changed openssl after 1.1.0 version
    - so if you want build with open ssl version after 1.1.0, you should change some code.
    - but we have simple solution. https://github.com/planetbeing/libdmg-hfsplus/blob/openssl-1.1 branch
    - if you meet this error, please use openssl-1.1 branch code