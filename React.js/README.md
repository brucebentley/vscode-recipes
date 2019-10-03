# Live edit & debug your React apps directly from Visual Studio Code — without leaving the editor

_Supercharge your React debugging workflow with Visual Studio Code and Chrome debugging._

by [Bruce Bentley ( @bruce_bentley )](https://github.com/brucebentley/)

In the most recent release of our [Chrome Debugger for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome), we have landed a bunch of improvements to our sourcemapping-engine, which enables us to support live-editing and debugging out of the box with [`create-react-app`](https://github.com/facebookincubator/create-react-app).

This enables you as a developer to write and debug your React code without leaving the editor, and most importantly it enables you to have a continuous development workflow, where context switching is minimal, as you don’t have to switch between tools.

You can now write code, set a breakpoints, make a changes to the code, and debug your newly modified code — all from your editor 🔥🎉🎈

## How to get started in 6 steps

1. Download the [latest release of Visual Studio Code](http://code.visualstudio.com/Download) and install the [Chrome Debugger](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome)
2. Create your React app using [`create-react-app`](https://github.com/facebookincubator/create-react-app)
3. Use the following config for your `launch.json` file to configure the Visual Studio Code debugger and put it inside `.vscode/` in your root folder.
    ```json
   {
       "version": "0.2.0",
       "configurations": [
           {
               "name": "Chrome",
               "type": "chrome",
               "request": "launch",
               "url": "http://localhost:3000",
               "webRoot": "${workspaceRoot}/src"
           }
       ]
   }
    ```
4. Start your React app by running npm start in your favorite terminal.
5. Start debugging in Visual Studio Code by pressing `F5` or by clicking the green debug icon.

🎈🎉 **Happy debugging!** 🎉🎈

## Details

The Chrome debugger now supports [Webpack’s Hot Module Replacement mechanism](https://webpack.github.io/docs/hot-module-replacement.html), which pushes module changes to the browser by running a local file watcher.

The Chrome debugger is now able to pickup these changes and re-applies the newly generated HMR sourcemap to the loaded source files on the fly. This enables the live editing and debugging experiences, _without adding a need for more file watches or background tools_.
