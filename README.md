## VS Code

This is your code editor, where you will be doing most of your work.
VS Code is an open source editor made by Microsoft

Make sure you can run `code --help` from the command line and you get help. If you do not see help, please follow these steps:
- Mac: Select Shell Command: Install 'Code' command in path from the Command Palette. _Command Palette is what pops up when you press `shift + ⌘ + P` while inside VS Code. (`shift + ctrl + P` in Windows)_
- Windows: Make sure you selected `Add to PATH` during the installation. Also, you will have to close and re-open any running command promps.

There a bunch of amazing extensions that will make our lives so much easier.
The best way to download these extensions will be to use the respective shell scripts included in this repo. Just copy the files and paste them into your console.

(`vscode-extensions.sh`):

- [Debugger for Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome): lets us run debug sessions in VS Code from Chrome
- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint): allows us to lint or JavaScript, showing style and syntax errors
- [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode): code formatter
- [Jest](https://marketplace.visualstudio.com/items?itemName=Orta.vscode-jest): automatically runs and monitors your Jest tests
- [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer): Launch a local development server with live reload feature for static & dynamic pages.
- [Popping and Locking Theme](https://marketplace.visualstudio.com/items?itemName=hedinne.popping-and-locking-vscode): the best theme
- [Bracket Pair Colorizer](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer): allows matching brackets to be identified with colours
- [DotENV](https://marketplace.visualstudio.com/items?itemName=mikestead.dotenv): syntax highlighting for `.ENV` files
- [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens): adds a bunch of Git goodies to your editor
- [JavaScript (ES6) code snippets](https://marketplace.visualstudio.com/items?itemName=xabikos.JavaScriptSnippets)
- [ES7 React/Redux/GraphQL/React-Native snippets](https://marketplace.visualstudio.com/items?itemName=dsznajder.es7-react-js-snippets)
- [LintLens](https://marketplace.visualstudio.com/items?itemName=ghmcadams.lintlens): context for your ESLint file
- [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one): All you need for Markdown (keyboard shortcuts, table of contents, auto preview and more)
- [Markdown Preview Enhanced](https://marketplace.visualstudio.com/items?itemName=shd101wyy.markdown-preview-enhanced): provides you with many useful functionalities such as automatic scroll sync, math typesetting, mermaid, PlantUML, pandoc, PDF export, code chunk, presentation writer
- [npm Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.npm-intellisense): autocompletes npm modules in import statements
- [open in browser](https://marketplace.visualstudio.com/items?itemName=techer.open-in-browser): opens current HTML file in browser
- [TODO Highlight](https://marketplace.visualstudio.com/items?itemName=wayou.vscode-todo-highlight): highlights your TODOs
- [Jest Snippets](https://marketplace.visualstudio.com/items?itemName=andys8.jest-snippets): allows snippets for fast jest blocks

### Settings

I have also included my entire VS Code settings file (`vscode-settings.json`). 
You can copy these if you like.

To import settings, simply open up VS Code and in the command palette (Ctrl+Shift+P) search for `Open Settings (JSON)`.
This will open a JSON file of all your settings.
You can copy and paste my settings directly into this file.

## ESLint

A linter checks your code code for sytnax and style erros in real-time.
ESLint is a linter for JavaScript.
Having your ESLint properly configured will make your lives soooooo much easier.

We will setup a global ESLint configuration so that all of your projects can use the same settings.
It is also possible to modify these settings on a per-project basis.

1. Install ESLint dependencies globally
  ```sh
  $ npm install -g eslint@^5.16.0 babel-eslint prettier eslint-config-airbnb eslint-config-airbnb-base eslint-plugin-import eslint-plugin-react eslint-config-prettier eslint-config-react-app eslint-plugin-flowtype@^2.50.3 eslint-plugin-jsx-a11y eslint-plugin-prettier eslint-plugin-promise eslint-plugin-react-hooks @typescript-eslint/parser @typescript-eslint/eslint-plugin typescript 
  ```
2. Set ESLint Node path setting in VS Code so that ESLint knows where to find your dependencies (just drop these settings into your VS Code settings JSON)
   - Mac
    ```json
    "eslint.nodePath": "/usr/local/lib/node_modules/",
    ```
   - Windows
   ```json
   "eslint.nodePath": "C:\Users\<your username>\AppData\Roaming\npm",
   ```  
3. Set a few other VS Code settings to properly autoformat your code (or ensure they exist)
  ```json
  "editor.formatOnSave": true,
  "eslint.autoFixOnSave": false,
  "eslint.alwaysShowStatus": true,
  "[javascript]": {
    "editor.formatOnSave": false
  },
  ```
4. Drop the `.eslintrc` file somewhere low in your file hierarchy on your computer (Like in C:\Users\CBrand). This is the file that will be used to decide which rules to apply. You can also use and modify these settings on a per-project basis. Just include the file in the root of your project directory, then you can customize the settings for each project. **Note:** These settings are by no means perfect. What works for me may not work for you. Use these as a starting point and then customize to your liking.

## Git

Set your user name and email address. This is important because every Git commit uses this information, and it’s immutably baked into the commits you start creating:
```sh
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```

Configure the default text editor that will be used when Git needs you to type in a message. If you want to use VS Code, you can do the following:
```sh
$ git config --global core.editor code
```

## Resources

- [How to Setup VS Code + Prettier + ESLint](https://www.youtube.com/watch?v=YIvjKId9m2c)
- [How to globally set up eslint in vscode](https://medium.com/@davidchristophersally/how-to-set-up-eslint-in-vscode-globally-253f25fbaff9)
- [ESLint Docs](https://eslint.org/docs/rules/)
- [First-Time Git Setup](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)
