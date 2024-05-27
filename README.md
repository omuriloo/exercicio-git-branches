# Code Navigation

Visual Studio Code has a high productivity code editor which, when combined with programming language services, gives you the power of an IDE and the speed of a text editor. In this topic, we'll first describe VS Code's language intelligence features (suggestions, parameter hints, smart code navigation) and then show the power of the core text editor.

## Quick file navigation

> Tip: You can open any file by its name when you type Ctrl+P (Quick Open).

The Explorer is great for navigating between files when you are exploring a project. However, when you are working on a task, you will find yourself quickly jumping between the same set of files. VS Code provides two powerful commands to navigate in and across files with easy-to-use key bindings.

Hold `Ctrl` and press `Tab` to view a list of all files open in an editor group. To open one of these files, use `Tab` again to pick the file you want to navigate to, then release `Ctrl` to open it. 
![image](https://github.com/omuriloo/exercicio-git-branches/assets/158228238/3db6dda5-91fe-400e-bfa7-de89c8b003c8)

Alternatively, you can use `Alt+Left` and `Alt+Right` to navigate between files and edit locations. If you are jumping around between different lines of the same file, these shortcuts allow you to navigate between those locations easily.

##  Breadcrumbs

The editor has a navigation bar above its contents called [Breadcrumbs](https://en.wikipedia.org/wiki/Breadcrumb_navigation). It shows the current location and allows you to quickly navigate between folders, files, and symbols.
![image](https://github.com/omuriloo/exercicio-git-branches/assets/158228238/b5d69555-d041-406c-a497-1480fd6fedbb)
Breadcrumbs always show the file path and, with the help of language extensions, the symbol path up to the cursor position. The symbols shown are the same as in Outline view and Go to Symbol.

Selecting a breadcrumb in the path displays a dropdown with that level's siblings so you can quickly navigate to other folders and files.
![image](https://github.com/omuriloo/exercicio-git-branches/assets/158228238/9b9a736e-d83c-42cc-907e-ca68912d36a2)
If the current file type has language support for symbols, you will see the current symbol path and a dropdown of other symbols at the same level and below.
![alt text](image.png)

You can turn off breadcrumbs with the View > Show Breadcrumbs toggle or with the `breadcrumbs.enabled` [setting](https://code.visualstudio.com/docs/getstarted/settings).

### Breadcrumb customization

The appearance of breadcrumbs can be customized. If you have very long paths or are only interested in either file paths or symbols paths, you can use the `breadcrumbs.filePath` and `breadcrumbs.symbolPath` settings. Both support `on`, `off`, and `last` and they define if or what part of the path you see. By default, breadcrumbs show file and symbol icons to the left of the breadcrumb but you can remove the icons by setting `breadcrumbs.icons` to false

### Symbol order in Breadcrumbs

You can control how symbols are ordered in the Breadcrumbs dropdown with the `breadcrumbs.symbolSortOrder` settings.

Allowed values are:

* `position` - position in the file (default)
* `name` - alphabetical order
* `type` - symbol type orde

### Breadcrumb keyboard navigation
To interact with breadcrumbs, use the Focus Breadcrumbs command or press `Ctrl+Shift+..` It will select that last element and open a dropdown that allows you to navigate to a sibling file or symbol. Use the `Left` and `Right` keyboard shortcuts to go to elements before or after the current element. When the dropdown appears, start typing - all matching elements will be highlighted and the best match will be selected for quick navigation.

You can also interact with breadcrumbs without the dropdown. Press `Ctrl+Shift+`; to focus the last element, use `Left` and `Right` to navigate, and use Space to reveal the element in the editor.

## Go to Definition
If a language supports it, you can go to the definition of a symbol by pressing `F12`.

If you press `Ctrl` and hover over a symbol, a preview of the declaration will appear:
![image](https://github.com/omuriloo/exercicio-git-branches/assets/158228238/15ffb267-ccae-493b-ae6e-d368fa33844d)

> Tip: You can jump to the definition with `Ctrl+Click` or open the definition to the side with `Ctrl+Alt+Click`.

## Go to Type Definition
Some [languages](https://code.visualstudio.com/docs/languages/overview) also support jumping to the type definition of a symbol by running the Go to Type Definition command from either the editor context menu or the Command Palette. This will take you to the definition of the type of a symbol. The command `editor.action.goToTypeDefinition` is not bound to a keyboard shortcut by default but you can add your own custom [keybinding](https://code.visualstudio.com/docs/getstarted/keybindings).

## Go to Implementation
[languages](https://code.visualstudio.com/docs/languages/overview) can also support jumping to the implementation of a symbol by pressing `Ctrl+F12`. For an interface, this shows all the implementors of that interface and for abstract methods, this shows all concrete implementations of that method.

## Go to Symbol
You can navigate symbols inside a file with `Ctrl+Shift+O`. By typing `:` the symbols will be grouped by category. Press `Up` or `Down` and navigate to the place you want.
![image](https://github.com/omuriloo/exercicio-git-branches/assets/158228238/edf88d04-436d-416c-a13c-05d101db3b30)

## Open symbol by name
Some languages support jumping to a symbol across files with `Ctrl+T`. Type the first letter of a type you want to navigate to, regardless of which file contains it, and press `Enter`.
![image](https://github.com/omuriloo/exercicio-git-branches/assets/158228238/ed510c87-cf31-4629-9b5f-b4fdb2ea9e80)

## Peek
We think there's nothing worse than a big context switch when all you want is to quickly check something. That's why we support peeked editors. When you execute a Go to References search (via `Shift+F12`), or a Peek Definition (via `Alt+F12`), we embed the result inline:
![image](https://github.com/omuriloo/exercicio-git-branches/assets/158228238/cdfcac90-2709-4681-aece-773877c69a7b)

You can navigate between different references in the peeked editor and make quick edits right there. Clicking on the peeked editor filename or double-clicking in the result list will open the reference in the outer editor.

> Tip: Additionally, the peek window is closed if you press `Escape` or double-click in the peek editor region. You can disable this behavior with the `editor.stablePeek` [setting](https://code.visualstudio.com/docs/getstarted/settings).

Bracket matching
Matching brackets will be highlighted as soon as the cursor is near one of them.
![image](https://github.com/omuriloo/exercicio-git-branches/assets/158228238/69f403e4-c074-4da3-9b73-ee76965e9de0)

Tip: You can jump to the matching bracket with `Ctrl+Shift+\`

`"workbench.colorCustomizations": {
    "editorBracketHighlight.foreground1": "#FFD700",
    "editorBracketHighlight.foreground2": "#DA70D6",
    "editorBracketHighlight.foreground3": "#179fff",
},`
