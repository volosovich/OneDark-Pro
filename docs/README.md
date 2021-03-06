# OneDark Pro 

## About
[OneDark-Pro](https://marketplace.visualstudio.com/items?itemName=zhuangtongfa.Material-theme) is based on Atom's default One Dark theme, and is one of the most downloaded themes for VS Code. This document will show you how to install the theme on VS Code, and how to develop and contribute to this project.

## Install
Using the Extensions menu, search for **'One Dark Pro'**. Don't forget to apply the theme (see below).

![ScreenShot](https://raw.githubusercontent.com/Binaryify/OneDark-Pro/master/static/screenshot3.png)

## Apply
Press `ctrl(⌘) + k`, then press `ctrl(⌘) + t`, you will see a theme selection interface. Choose **'One Dark Pro'**.

![ScreenShot](https://raw.githubusercontent.com/Binaryify/OneDark-Pro/master/static/screenshot4.png)

## Develop 
If you see any inconsistencies or missing colors, the following guide will show you how to make your own changes. You can submit your improvements as a merge request to this theme.

### Find the VS Code extension path

In a terminal, `cd` to your themes folder

- Windows:
`C:\Users\yourUserName\.vscode\extensions\themes`  

- Mac/linux:
`~/.vscode/extensions/themes`

![ScreenShot](https://raw.githubusercontent.com/Binaryify/OneDark-Pro/master/static/screenshot5.png)

Then open 'OneDark-Pro.json' with VS Code: `code OneDark-Pro.json`

![ScreenShot](https://raw.githubusercontent.com/Binaryify/OneDark-Pro/master/static/screenshot6.png)

### Example from 'OneDark-Pro.json'
The following is a code snippet taken from the **'OneDark-Pro.json'** file:

![ScreenShot](https://raw.githubusercontent.com/Binaryify/OneDark-Pro/master/static/screenshot7.png)

### Principle
VS Code will parse code and specify a scope for each piece of syntax. For example, the scope may be a keyword, a constant, or punctuation. **'OneDark-Pro.json'** includes the settings that tell VS Code how to format the text accordingly, using these scopes.

### Common scope list

```
comment
constant
constant.character.escape
constant.language
constant.numeric
declaration.section entity.name.section
declaration.tag
deco.folding
entity.name.function
entity.name.tag
entity.name.type
entity.other.attribute-name
entity.other.inherited-class
invalid
invalid.deprecated.trailing-whitespace
keyword
keyword.control.import
keyword.operator.js
markup.heading
markup.list
markup.quote
meta.embedded
meta.preprocessor
meta.section entity.name.section
meta.tag
storage
storage.type.method
string
string source
string.unquoted
support.class
support.constant
support.function
support.type
support.variable
text source
variable
variable.language
variable.other
variable.parameter
```

### Get code scope
VS Code comes with a built-in tool to easily obtain the scope of a piece of syntax. 

Press `ctrl(⌘) + shift + P`, then type `dev`, and choose **"Developer: Inspect TM Scopes"** option.

This will show you the selected token's scope. There are four sections:

- the in-scope piece of syntax

- language, token type, etc.

- the theme rule and shows the foreground color of the token

- the list of scopes for the token

![ScreenShot](https://raw.githubusercontent.com/Binaryify/OneDark-Pro/master/static/screenshot8.png)
![ScreenShot](https://raw.githubusercontent.com/Binaryify/OneDark-Pro/master/static/screenshot9.png)

### Add/Change code color
Now you know the rules for the theme, you simply need the code scope and the hex color you would like. Now edit the **'OneDark-Pro.json'** file, add/change code snippet like this:

```json
{
      "name": "c++ function",
      "scope": "meta.function.c",
      "settings": {
        "foreground": "#e06c75"
      }
}
```
### Reload
Then press `ctrl(⌘) + shift + P`, type **'reload'** and press `enter`. Once the window has reloaded, you will find the color of the code has changed.

![screenshot](https://raw.githubusercontent.com/Binaryify/OneDark-Pro/master/static/screenshot13.png)

### Commonly used theme colors

- Whiskey : `#D19A66` (constant)
- Fountain Blue : `#56B6C2` (console)
- Chalky : `#E5C07B` (constant)
- Soft Purple : `#C678DD` (url,keyword)
- Malibu : `#61AFEF` (function)
- Pistachio : `#98C379` (string)
- Cadet Blue : `#ABB2BF` (text)
- Froly : `#E06C75` (variable)

![screenshot](https://raw.githubusercontent.com/Binaryify/OneDark-Pro/master/static/screenshot10.png)

## Workbench theming
If you want to play around with new colors, use the setting `workbench.colorCustomizations` to customize the currently selected theme.
For example, you can add this snippet in your "settings.json" file:

```json
"workbench.colorCustomizations":{
  "tab.activeBackground": "#282c34",
  "activityBar.background": "#282c34",
  "editorGroup.background": "#282c34",
  "sideBar.background": "#282c34"
}
```

Please check the official documentation, [Theme Color Reference](https://code.visualstudio.com/docs/getstarted/theme-color-reference), for more helpful information.

## Contribute
Now you know how to develop the theme, you can fork this repository and send a pull request with your version. The request will be reviewed, and if successful, merged into this theme and published on the VS Code market.

To publish your own theme, please refer to the official documentation: [https://code.visualstudio.com/docs/extensions/themes-snippets-colorizers](https://code.visualstudio.com/docs/extensions/themes-snippets-colorizers)  
