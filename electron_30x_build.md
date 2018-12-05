## Electron build '3.0.x branch  make error, on higner than MAC SDK 10.10'

change function call type you can solve this problem

 1. Problem
    * atom_application_delegate.mm 99 line
    * restorationHandler parameter error
    ```objc
    (BOOL)application:(NSApplication*)sender
    continueUserActivity:(NSUserActivity*)userActivity
      restorationHandler:
          (void (^)(NSArray* restorableObjects))restorationHandler
    API_AVAILABLE(macosx(10.10)) {
    std::string activity_type(base::SysNSStringToUTF8(userActivity.activityType));
    ```
 2. Solution
    * restorationHandler parameter error
    ```objc
    (BOOL)application:(NSApplication*)sender
    continueUserActivity:(NSUserActivity*)userActivity
      restorationHandler:
           (void(^)(NSArray<id<NSUserActivityRestoring>> *restorableObjects))restorationHandle
    API_AVAILABLE(macosx(10.10)) {
    std::string activity_type(base::SysNSStringToUTF8(userActivity.activityType));
    ```