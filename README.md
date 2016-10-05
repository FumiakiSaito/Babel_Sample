## Babel環境をインストール
(開発にのみBabelを使うのでdevとする)

```
npm install --save-dev babel-cli
```

ES2015から変換を行うためのプリセットをインストール

```
npm install --save-dev babel-preset-es2015
```

.babelrcを作成する

```
{
    presets: ["es2015"]
}
```

変換テストする  
test.js  

```
[1,2,3].map(n => n + 1);
```

node_modules/.bin/babel test.js  
(標準出力)

```
"use strict";

[1, 2, 3].map(function (n) {
  return n + 1;
});
```

実際のファイル書き出しは-oオプションを使う

```
node_modules/.bin/babel test.js -o test_compiled.js
```
