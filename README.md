# Rainpaper
Live wallpapers for windows from a webpage.

How to use:
1. Get GeckoFX from Nuget (using the package manager after opening the project)
2. Compile
3. Move wallpaper.htm to the .exe directory
4. ???
5. Profit

I started out making a cool webpage (wallpaper.htm) and wanted to turn it into a wallpaper. Unfortunately there are no good options for displaying a webpage as a wallpaper in windows. I found a couple of outdated tools that might have worked on Windows XP but they certianly didnt work on Windows 10.
Rainpaper is my lil' hacky program that lets me use my sick animations as a sick wallpaper.

There are two main tasks Rainpaper does:
1. Displaying a webpage on a windows form
2. Drawing the form behind the desktop icons

The first stage is fairly easy. I use GeckoFX (the Firefox engine) since the .net built-in webpage control did not work with Canvas elements
Stage two is quite a bit more complicated. It involves finding the window that is used to smoothly transition between web pages (Progman -> WorkerW). 
The following user32.dll functions are used: FindWindow, FindWindowEx, EnumWindows, EnumWindowsProc, SendMessageTimeout, GetDCEx, ReleaseDC, SetParent.
Once you find the correct window it's as simple as calling SetParent and my windows will be drawn behind the desktop icons!