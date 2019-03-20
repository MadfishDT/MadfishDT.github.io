## Electron Add new Feature moveTop

[Electron Browser Window moveTop function](https://electronjs.org/docs/api/browser-window)
- this feature is merged in electron master branch few month ago
 1. Problem
    * move Top(z-order) function not implemented in electron

    ```js
    const electron = require('electron');
    const curWindow = electron.remote.getCurrentWindow();
    curWindow.moveTop();
    ```

 2. Solution
    * on Window os, we can use SetWindowPos
    * on Mac os, we can use 

    - **Windows OS**
    ```cpp
        void NativeWindowViews::MoveTop() {
        #if defined(OS_WIN)
        gfx::Point pos = GetPosition();
        gfx::Size size = GetSize();
        ::SetWindowPos(GetAcceleratedWidget(), HWND_TOP, pos.x(), pos.y(),
                        size.width(), size.height(),
                        SWP_NOACTIVATE | SWP_NOMOVE | SWP_NOSIZE | SWP_SHOWWINDOW);
        #elif defined(USE_X11)
            atom::MoveWindowToForeground(GetAcceleratedWidget());
        #endif
        }
    ```

    - **MacOS**
    ```objc
        void NativeWindowMac::MoveTop() {
            [window_ orderWindow:NSWindowAbove relativeTo:0];
        }
    ```