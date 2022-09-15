### vs code 相关设置 

1. 格式化代码 

 第一步 安装相关插件↓插件列表 
 
  * ESLint 
  * Vetur 
  * Prettier Code formatter 
  
 第二步 配置setting.json 
 
 ``` 
 {
  "workbench.startupEditor": "newUntitledFile",
  "files.autoSave": "off", // 关闭文件自动保存，避免开发时候页面变化
  "editor.tabSize": 2, // tab距离
  "editor.formatOnSave": true, // 在保存时自动格式化
  "editor.minimap.enabled": false, // 关闭右侧快速预览
  "files.eol": "\n", // 设定文件的换行符,\n（linux模式）或\r\n(win模式)
  "editor.detectIndentation": false, // 关闭vscode的缩进检查
  "editor.fontSize": 14, //设置文字大小
  "editor.lineHeight": 0, //设置文字行高
  "editor.lineNumbers": "on", //开启行数提示
  "prettier.singleQuote": true, // 使用单引号
  "prettier.printWidth": 220, // 每行不超过220
  "prettier.jsxBracketSameLine": true,
  "prettier.jsxSingleQuote": true,
  "editor.quickSuggestions": {
    //开启自动显示建议
    "other": true,
    "comments": true,
    "strings": true
  },
  "window.zoomLevel": 0, // 调整窗口的缩放级别
  //根据文件后缀名定义vue文件类型
  "files.associations": {
    "*.vue": "vue"
  },
  // 为各类文件制定Fatmatter插件
  "[vue]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode" // 采用prettier处理格式化
  },
  "[javascript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[json]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[jsonc]": {
    "editor.defaultFormatter": "vscode.json-language-features"
  },
  // ESLint 的相关配置
  "eslint.validate": [
    "javascript",
    "javascriptreact",
    "vue"
  ],
  // "eslint.autoFixOnSave": true,  很多插件提示这么设定，但实际vscode中已经弃用这个设置，改用下面的方式。
  "editor.codeActionsOnSave": {
    // 保存时触发的事件
    "source.fixAll.eslint": true // 自动fix eslint
  },
  "eslint.run": "onSave", // 保存就校验
  // 函数名后增加空格
  "javascript.format.insertSpaceBeforeFunctionParenthesis": true,
  "javascript.format.insertSpaceAfterFunctionKeywordForAnonymousFunctions": true,
  "workbench.iconTheme": "vscode-icons",
  "workbench.colorCustomizations": {
    "editorBracketHighlight.foreground1": "#ffd700",
    "editorBracketPairGuide.activeBackground1": "#ffd7007f",
    "editorBracketHighlight.foreground2": "#da70d6",
    "editorBracketPairGuide.activeBackground2": "#da70d67f",
    "editorBracketHighlight.foreground3": "#87cefa",
    "editorBracketPairGuide.activeBackground3": "#87cefa7f",
    "editorBracketHighlight.foreground4": "#ffd700",
    "editorBracketPairGuide.activeBackground4": "#ffd7007f",
    "editorBracketHighlight.foreground5": "#da70d6",
    "editorBracketPairGuide.activeBackground5": "#da70d67f",
    "editorBracketHighlight.foreground6": "#87cefa",
    "editorBracketPairGuide.activeBackground6": "#87cefa7f",
    "editorBracketHighlight.unexpectedBracket.foreground": "#ff0000",
  },
  "editor.bracketPairColorization.enabled": true,
  "editor.guides.bracketPairs": "active",
  "prettier.semi": false,
  "settingsSync.ignoredSettings": [], // 每行结尾加;
  "prettier.trailingComma": "none" // 对象最后一个元素 不加逗号
}
``` 

