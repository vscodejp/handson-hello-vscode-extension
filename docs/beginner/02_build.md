# Hello Worldを起動しよう

`F5`で拡張機能をビルドしてください。
すると、新しくVS Codeのウィンドウが開きます。

次に新しいくウィンドウ上でコマンドパレットを呼び出します。
コマンドパレットは`F1`から呼び出せます。
以下のようにコマンドパレットから`Hello World`を実行します。

![コマンドパレットにHello Worldを入力](../..//images/beginner_command_palette.png)

以下のようにウィンドウの右下にHello Worldが表示されれば成功です。

![Hello Worldコマンドの実行結果](../../images/beginner_helloworld.png)

出力の詳細は生成された`src/extension.ts`ファイルに書かれています。
出力内容を変えるには`window.showInformationMessage('Hello World from Hello VSCode!');`の部分を編集しましょう。

```ts
(注:src/extension.ts)
// VS Code拡張機能APIパッケージを'vscode'として利用
import { ExtensionContext, commands, window } from 'vscode';

// 拡張機能が起動したときに実行するメソッド
export function activate(
    context: ExtensionContext) {

    // デバッグ用コンソールに起動したことを知らせる
    // エラー時はconsole.errorを利用する
    console.log('"hello-vscode" is now active!');

    // package.jsonで定義したコマンドを実行
    let disposable = commands.registerCommand('hello-vscode.helloWorld', () => {
        // コマンド呼び出し時の実行内容

        // 右下にウィンドウにメッセージを出力
        window.showInformationMessage('Hello World from Hello VSCode!');
    });

    context.subscriptions.push(disposable);
}

// 拡張機能が無効になったときに呼び出す
export function deactivate() {}
```

　このコードでは、`ExtensionContext`（拡張機能専用のユーティリティ）、`commands`（helloworldなどのコマンドの管理）、`window`（エディタやターミナルなどのウィンドウの管理）という3つのVS Code APIを利用しています。
VS Code APIの詳細は、[ドキュメント](https://code.visualstudio.com/api/references/vscode-api)を参照してください。
