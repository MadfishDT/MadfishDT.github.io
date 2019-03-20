## Electron Implementation BrowerWindow setAspectRatio Function on Windows os

Electron Browser Window setAspectratio is implemented on Windows OS
- [I am trying to merge this feature to current electron master branch](https://github.com/electron/electron/pull/17245)

 1. Problem
    * setAspectratio works on only MacOS

    ```js
    const electron = require('electron');
    const curWindow = electron.remote.getCurrentWindow();
    curWindow.setAspectRatio(4/5);
    ```

    Mac OS Provide API to keep window size ratio, but Window OS do not have like that API

 2. Solution
    * implement keeping width-height ratio function on Window OS
    * using WM_SIZE or WM_SIZING window Event

    ```cpp
    void NativeWindowViews::HandleSizingEvent(WPARAM w_param, LPARAM l_param) {
    double aspect_ratio = GetAspectRatio();
    // aspect_ratio width/height
    if (aspect_ratio == 0) {
        return;
    }
    RECT* window_rect;
    window_rect = reinterpret_cast<RECT*>(l_param);
    int width = window_rect->right - window_rect->left;
    int height = window_rect->bottom - window_rect->top;

    double result_width = 0;
    double result_height = 0;

    switch ((UINT)w_param) {
        case WMSZ_LEFT:
        case WMSZ_RIGHT:
        result_width = width;
        result_height = static_cast<double>(width) / aspect_ratio;
        break;
        case WMSZ_TOP:
        case WMSZ_BOTTOM:
        result_width = static_cast<double>(height) * aspect_ratio;
        result_height = height;
        break;
        case WMSZ_TOPLEFT:
        case WMSZ_TOPRIGHT:
        case WMSZ_BOTTOMLEFT:
        case WMSZ_BOTTOMRIGHT:
        result_width = static_cast<double>(height) * aspect_ratio;
        result_height = height;
        break;
        default:
        break;
    }
    gfx::Size ratio_fit_size(result_width, result_height);
    gfx::Size min_fit_size = GetMinimumSize();
    if (min_fit_size.width() >= result_width ||
        min_fit_size.height() >= result_height) {
        return;
    } else {
        // SetSize(ratio_fit_size, false);
        window_rect->right = window_rect->left + result_width;
        window_rect->bottom = window_rect->top + result_height;
    }
        }
    ```