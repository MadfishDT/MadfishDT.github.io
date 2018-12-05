## Electron build 'ATS Disable on mac os'

You can off ATS mode

 1. [What is ATS](https://techcrunch.com/2016/06/14/apple-will-require-https-connections-for-ios-apps-by-the-end-of-2016/)
 - Appication Transport Securirty
 - to install Application on OSX and IOS, installer or application have some restrictions
 - Typically, Application download through 'HTTPS' protocol

 2. Needs 
 - if your server or domain do not support 'https' or current step on developing, ATS is useless or blocking stuff

How To off ATS mode in Application

 1. see info.plist
 - info.plist describe Application **Permissions**
 - Edit Permission you can get 'https' ignore 
 
 * original info.plist '/atom/browser/resource/mac/info.plist'
 ```xml
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
    <dict>
    <key>CFBundleDisplayName</key>
    <string>${PRODUCT_NAME}</string>
    <key>CFBundleExecutable</key>
    <string>${PRODUCT_NAME}</string>
    <key>CFBundleIdentifier</key>
    <string>${ATOM_BUNDLE_ID}</string>
    <key>CFBundleInfoDictionaryVersion</key>
    <string>6.0</string>
    <key>CFBundleName</key>
    <string>${PRODUCT_NAME}</string>
    <key>CFBundlePackageType</key>
    <string>APPL</string>
    <key>CFBundleIconFile</key>
    <string>electron.icns</string>
    <key>CFBundleVersion</key>
    <string>1.4.16</string>
    <key>CFBundleShortVersionString</key>
    <string>1.4.16</string>
    <key>LSApplicationCategoryType</key>
    <string>public.app-category.developer-tools</string>
    <key>LSMinimumSystemVersion</key>
    <string>10.9.0</string>
    <key>NSMainNibFile</key>
    <string>MainMenu</string>
    <key>NSPrincipalClass</key>
    <string>AtomApplication</string>
    <key>NSSupportsAutomaticGraphicsSwitching</key>
    <true/>
    <key>NSHighResolutionCapable</key>
    <true/>
    </dict>
    </plist>
 ```

  * apply ATS ignore

  ```xml
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
    <dict>
    <key>CFBundleDisplayName</key>
    <string>${PRODUCT_NAME}</string>
    <key>CFBundleExecutable</key>
    <string>${PRODUCT_NAME}</string>
    <key>CFBundleIdentifier</key>
    <string>${ATOM_BUNDLE_ID}</string>
    <key>CFBundleInfoDictionaryVersion</key>
    <string>6.0</string>
    <key>CFBundleName</key>
    <string>${PRODUCT_NAME}</string>
    <key>CFBundlePackageType</key>
    <string>APPL</string>
    <key>CFBundleIconFile</key>
    <string>electron.icns</string>
    <key>CFBundleVersion</key>
    <string>1.4.16</string>
    <key>CFBundleShortVersionString</key>
    <string>1.4.16</string>
    <key>LSApplicationCategoryType</key>
    <string>public.app-category.developer-tools</string>
    <key>LSMinimumSystemVersion</key>
    <string>10.9.0</string>
    <key>NSMainNibFile</key>
    <string>MainMenu</string>
    <key>NSPrincipalClass</key>
    <string>AtomApplication</string>
    <key>NSSupportsAutomaticGraphicsSwitching</key>
    <true/>
    <key>NSHighResolutionCapable</key>
    <true/>
 +  <key>NSAppTransportSecurity</key>
 +  <dict>
 +     <key>NSAllowsArbitraryLoads</key><true/>
 +  </dict>
  </dict>
  </plist>
  ```