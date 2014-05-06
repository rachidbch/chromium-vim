#cVimrc

###Mappings
 * Mappings are defined with the following structure: ```map <KEY> <MAPPING_NAME>```
 * Control, meta, and alt can be used also:
```viml
<C-u> "Ctrl + u
<M-u> "Meta + u
<A-u> "Alt  + u
```
 * It is also possible to unmap default bindings with ```unmap <KEY>```
 * To unmap all default keybindings, use ```unmapAll```

###Settings

 * Boolean cVimrc settings are enabled with the command ```'set' + <SETTING_NAME>``` and disabled with<br>
   the command ```'set' + no<SETTING_NAME>``` (for example, ```set regexp``` and ```set noregexp```)
 * Other settings are defined with ```=``` used as a separator (for example, ```set hintcharacters=abc```)

|setting|type|description|default|
|-------|----|------------|----------:|
|searchlimit|integer|set the amount of results displayed in the command bar|20|
|scrollstep|integer|set the amount of pixels scrolled when using the scrollUp and scrollDown commands|75|
|hud|boolean|show the heads-up-display|true|
|regexp|boolean|use regexp in find mode|true|
|ignorecase|boolean|ignore search case in find mode|true|
|ignorediacritics|boolean|convert diacritical characters to their English equivalents|true|
|autofocus|boolean|allows websites to automatically focus an input box when they are first loaded|true|
|insertmappings|boolean|use insert mappings to navigate the cursor in text boxes (see bindings below)|true|
|smoothscroll|boolean|use smooth scrolling|true|
|hintcharacters|string (alphanumeric)|set the default characters to be used in link hint mode|"asdfgqwertzxcvb"|
|barposition|string <br>["top", "bottom"]|set the default position of the command bar|"top"|

###Example configuration
```viml
" Settings
set searchlimit=30
set scrollstep=70
set nosmoothscroll
set nohud
set noautofocus
set barposition=bottom

" Mappings
unmap j
map j scrollUp

map <C-u> rootFrame
map <M-h> previousTab
map <C-d> scrollPageDown
map <C-e> scrollPageUp
```

#Keybindings

| Movement                |                                                                 | Mapping name           |
| ----------------------- | :-------------------------------------------------------------- | :--------------------- |
| j, s                    | scroll down                                                     | scrollDown             |
| k, w                    | scroll up                                                       | scrollUp               |
| d                       | scroll half-page down                                           | scrollPageDown         |
| u, e                    | scroll half-page up                                             | scrollPageUp           |
| l                       | scroll right                                                    | scrollRight            |
| h                       | scroll left                                                     | scrollLeft             |
| gi                      | go to first input box                                           | goToInput              |
| zz                      | center page to current search match (middle)                    | centerMatchH           |
| zt                      | center page to current search match (top)                       | centerMatchT           |
| zb                      | center page to current search match (bottom)                    | centerMatchB           |
| **Link Hints**          |                                                                 |                        |
| f                       | open link in current tab                                        | createHint             |
| F                       | open link in new tab                                            | createTabbedHint       |
| W                       | open link in new window                                         | createHintWindow       |
| M                       | open multiple links                                             | createMultiHint        |
| Y                       | copy url from link to clipboard                                 | yankUrl                |
| gr                      | reverse image search (google images)                            | reverseImage           |
| ;                       | change the link hint focus                                      |                        |
| **Miscellaneous**       |                                                                 |                        |
| :                       | open command bar                                                | openCommandBar         |
| /                       | open search bar                                                 | openSearchBar          |
| ?                       | open search bar (reverse search)                                | openSearchBarReverse   |
| I                       | search through browser history                                  | :history               |
| i                       | enter insert mode (escape to exit)                              | insertMode             |
| r                       | reload the current tab                                          | reloadTab              |
| gR                      | reload the current tab + local cache                            | reloadTabUncached      |
| yy                      | copy the url of the current page to the clipboard               | yankDocumentUrl        |
| b                       | search through bookmarks                                        | :bookmarks             |
| p                       | open the clipboard selection                                    | openPaste              |
| P                       | open the clipboard selection in a new tab                       | openPasteTab           |
| gj                      | hide the download shelf                                         | hideDownloadsShelf     |
| gf                      | cycle through iframes                                           | nextFrame              |
| gF                      | go to the root frame                                            | rootFrame              |
| **Tab Navigation**      |                                                                 |                        |
| gt, K, R                | navigate to the next tab                                        | nextTab                |
| gT, J, E                | navigate to the previous tab                                    | previousTab            |
| x                       | close the current tab                                           | closeTab               |
| t                       | :tabopen                                                        | :tabopen               |
| T                       | :tabopen &lt;CURRENT URL&gt;                                    |                        |
| H, S                    | go back                                                         | goBack                 |
| L, D                    | go forward                                                      | goForward              |
| B                       | change to another tab                                           | :buffers               |
| &lt;                    | move current tab left                                           | moveTabLeft            |
| &gt;                    | move current tab right                                          | moveTabRight           |
| gp                      | pin/unpin the current tab                                       | pinTab                 |
| go                      | duplicate the current tab                                       | :duplicate&            |
| gO                      | duplicate the current tab (focus)                               | :duplicate             |
| **Find Mode**           |                                                                 |                        |
| n                       | next search result                                              | nextSearchResult       |
| N                       | previous search result                                          | previousSearchResult   |
| v                       | enter visual mode (highlight current search)                    |                        |
| **Visual/Caret Mode**   |                                                                 |                        |
| escape                  | exit visual mode to caret mode/exit caret mode to normal mode   |                        |
| v                       | toggle between visual/caret mode                                |                        |
| h, j, k, l              | move the caret position/extend the visual selection             |                        |
| y                       | copys the current selection                                     |                        |
| n                       | select the next search result                                   |                        |
| N                       | select the previous search result                               |                        |
| p                       | open highlighted text in current tab                            |                        |
| P                       | open highlighted text in new tab                                |                        |
| **Text boxes**          |                                                                 |                        |
| &lt;C-i&gt;             | move cursor to the beginning of the line                        |                        |
| &lt;C-e&gt;             | move cursor to the end of the line                              |                        |
| &lt;C-u&gt;             | delete to the beginning of the line                             |                        |
| &lt;C-o&gt;             | delete to the end of the line                                   |                        |
| &lt;C-y&gt;             | delete back one word                                            |                        |
| &lt;C-p&gt;             | delete forward one word                                         |                        |
| &lt;C-h&gt;             | move cursor back one word                                       |                        |
| &lt;C-l&gt;             | move cursor forward one word                                    |                        |
| &lt;C-f&gt;             | move cursor forward one letter                                  |                        |
| &lt;C-b&gt;             | move cursor back one letter                                     |                        |

#Command Mode

| Command                                     | Description                                                       |
| ------------------------------------------- | ----------------------------------------------------------------- |
| :tabopen (autocomplete)                     | open a new tab with the typed/completed url/google search         |
| :open (autocomplete)                        | open the typed/completed url/google search                        |
| :history (autocomplete)                     | search through browser history                                    |
| :bookmarks (autocomplete)                   | search through bookmarks                                          |
| :bookmarks /&lt;folder&gt; (autocomplete)   | browse bookmarks by folder/open all bookmarks from folder         |
| :set (autocomplete)                         | temporarily change a cVim setting                                 |
| :chrome:// (autocomplete)                   | open a chrome:// url                                              |
| :closetab                                   | close the current tab                                             |
| :duplicate                                  | duplicate the current tab                                         |
| :settings                                   | open the settings page                                            |
| :nohl                                       | clear the highlighted text from the last search                   |
| :buffers (autocomplete)                     | change to a different tab                                         |
| :mksession                                  | create a new session from the current tabs in the active window   |
| :delsession (autocomplete)                  | delete a saved session                                            |
| :session (autocomplete)                     | open the tabs from a saved session in a new window                |

#Tips

 * You can specify whether you activate the tab (:tabopen, :bookmarks, :history, etc) by appending an ampersand (&) to the end of the url
 * Prepend a number to the command to repeat that command N times
 * Use the up/down arrows in command/find mode to navigate through previously executed commands/searches -- you can also use this to search for previously executed commands starting with a certain combination of letters (for example, entering "ta" in the command bar and pressing the up arrow will search command history for all matches beginning with "ta"