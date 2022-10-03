# Change Home/End Key to behave like Window

- make a new directory ```mkdir -p ~/Library/KeyBindings```
- make a new file for keyboard dictionary ```vim ~/Library/KeyBindings/DefaultKeyBinding.dict```
- add followning text:
```
{
"\UF729"  = moveToBeginningOfLine:; // home
"\UF72B"  = moveToEndOfLine:; // end
"$\UF729" = moveToBeginningOfLineAndModifySelection:; // shift-home
"$\UF72B" = moveToEndOfLineAndModifySelection:; // shift-end
"^\UF729" = moveToBeginningOfDocument:; // ctrl-home
"^\UF72B" = moveToEndOfDocument:; // ctrl-end
"^$\UF729" = moveToBeginningOfDocumentAndModifySelection:; // ctrl-shift-home
"^$\UF72B" = moveToEndOfDocumentAndModifySelection:; // ctrl-shift-end
}
```
- Restart Finder ```killall Finder```


https://damieng.com/blog/2015/04/24/make-home-end-keys-behave-like-windows-on-mac-os-x/

# Screenshot
- ```Press Command + Shift + 4``` to take screenshot

To setup save folder
- Press Command + Shift + 5
- Click on Options
- Now either pick a folder that is listed, or choose Other Location.

https://www.macworld.com/article/673251/how-to-change-where-screenshots-are-saved-on-a-mac.html

# F5 to refresh Chrome
https://www.maciverse.com/make-f5-refresh-the-browser-on-a-mac.html

# Switch the Control and Command Keys
https://www.macinstruct.com/tutorials/how-to-switch-the-control-and-command-keys/

# Show Hidden files in Finder
- open terminal
- execute ```defaults write com.apple.Finder AppleShowAllFiles true```
- restart finder ```killall finder```

https://nordlocker.com/blog/how-to-show-hidden-files-mac/#:~:text=The%20first%20and%20easiest%20method,as%20translucent%20in%20the%20folder.

# Create Shortcut to Open IntelliJ Folder
- Open Automator from App Launcher
- Choose ```Quick Action```  
  - Workflow receives current: ```folders``` in ```Finder.app```
  - Search and Select ```Run Shell Script```
  - paste this script ```open -a "IntelliJ IDEA.app" "$*"``` and change Pass Input to ```as argument```
  - Save

https://www.youtube.com/watch?v=V59RwTqhxzE&t=97s

To delete
- Open Finder, go to ~/Library/Services
- delete a file

https://www.youtube.com/watch?v=kaVHwhau1M4

