# Desktop Sheep
A remake of the Windows XP Program

I found the original sprites for an old [Windows XP program](https://www.youtube.com/watch?v=GEYyX9HtkPg) [here](https://www.pinterest.de/pin/382172718377526278/) and made my own version.
It works pretty much the same as the original, and should be compatible with Windows 10 & 11 (maybe even 7! But I cant test that).

## Installation ##
Just download this repository. If windows or chrome blocks the execution/download, you have to find a solution yourself (I 

## How did I do it? ##
**(Pretty technical)**
Every single sheep has its own little window. I used a bunch of functions from the User32.dll to create the window, resize it, remove titlebar and hide from the taskbar.
Additionally every window has a transparency key (Set by [SetLayeredWindowAttributes](https://docs.microsoft.com/en-us/windows/win32/api/winuser/nf-winuser-setlayeredwindowattributes)). Rendering a window with native Windows is pretty slow, but barely enough for around 10 sheeps at a time. After some research I learned there are 3 ways to move a window in Windows: [1. SetWindowPos](https://docs.microsoft.com/en-us/windows/win32/api/winuser/nf-winuser-setwindowpos), [2. DeferWindowPos](https://docs.microsoft.com/en-us/windows/win32/api/winuser/nf-winuser-deferwindowpos), [3. MoveWindow](https://docs.microsoft.com/en-us/windows/win32/api/winuser/nf-winuser-movewindow). The last one is the fastes one and lets me move the windows pretty smoothly.

The rest is just a bunch of animating, collision solving and error prevention. I used my [program](https://github.com/Real-Gollum/Window-Visibility-Detector) to sort out hidden windows and let [EnumDesktopWindows](https://docs.microsoft.com/en-us/windows/win32/api/winuser/nf-winuser-enumdesktopwindows) do the rest. It's a huge messy chunk of code, but it works.

Feel free to ask me any questions on how I did a specific thing.
Enjoy!
