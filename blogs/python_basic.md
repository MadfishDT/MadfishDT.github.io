## Python Basic

* Python Grammer

    - ref: https://docs.python.org/3/tutorial/

**Installation**
1. [Python Download](https://www.python.org/downloads/)
    * Latest version 3.8.0
    * Be care version, because some python context can not compatible lower version.
        - for example, most platform user 2.7.x version python scrips. some partof 2.7.x version python script not work in 3.x.x version

2. Mac or Lunux
    - Most Mac or Linux  have python
     
    ```
    >> python
    Python 2.7.10 (default, Feb  7 2017, 00:08:15) 
    ```

3. online python terminal
    - https://www.python.org/


**Basic Grammer**

1. number

```python
>>python
>>>1+2
3
>>>1000-10
9990
>>>12345678 * 3
37037034
>>> 5000 / 3
1666
```

2. variable
```python
>>python
>>>money = 100
>>>pay = 10
>>>money - pay
90
>>> a = 'pig'
>>> b = 'dad'
>>> a + b
pigdad
```
- string slice
    - [0:2] index 0 to 2 string slice
    - [startIndex:count]
    - [startIndex:] : start to end
    - [:count] : start to count
    
    ```
    >>python
    a = "abcedfg"
    >>> a[0:2]
    ab
    ```

2. list

```python
    >>python
    >>>family = ['mother', 'father', 'gentleman', 'sexy lady']
    >>>len(familly)
    4
    >>>family[0]
    mother
```

- list slice
    - [0:2] index 0 to 2 list slice
    - [startIndex:count]
    - [startIndex:] : start to end
    - [:count] : start to count

    ```
    >>python
    a = [1, 2, 3, 4, 5]
    >>> a[0:2]
    [1, 2]
    ```
3. Tuple

- () scope object
- Tuple look like List
- Tuple value can not be removed and modified

```python
>>python
>>>t1 = (1, 2, 'a', 'b')
```