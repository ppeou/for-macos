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
