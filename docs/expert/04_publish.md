# 公開方法

以下はそれぞれ各リンクを参照ください．

## VS Code 拡張機能の公開

[公式ガイド（英語）](https://code.visualstudio.com/api/working-with-extensions/publishing-extension)
[日本語記事](https://qiita.com/567000/items/c4cf825fb30e3e247285#%E5%85%AC%E9%96%8B%E3%81%99%E3%82%8B)

まとめると以下のコマンドです．

```sh
vsce login
vsce publish
```

### Language Serverの公開

npmパッケージとして公開します．

[公式ガイド（英語）](https://docs.npmjs.com/creating-and-publishing-unscoped-public-packages)
[日本語記事](https://qiita.com/TsutomuNakamura/items/f943e0490d509f128ae2)

まとめると以下のコマンドです．

```sh
cd server
npm login
npm publish
```

## 他エディタでもLSPを利用

以下のコマンドでLanguage Serverのnpmパッケージをインストールすることで他のエディタでも開発したLSPを利用できます．

```sh
npm install -g {公開したLanguage Server}
```

### エディタごとの利用方法リンク

* [neovim/Vim](https://qiita.com/succi0303/items/cd30d0ea40d419d4431c#javascript)
* [Emacs](https://qiita.com/blue0513/items/acc962738c7f4da26656)
* [Sublime Text](https://tukumemo.com/language-server-protocol-sublimetext/)
* [Atom (英語ドキュメント)](https://github.com/atom/atom-languageclient)

## 発展

公式が提供しているLSPの実装例は以下のとおりです．
更に新しい機能を作りたい場合はこれらを参考に発展させていきましょう．

| サンプル | 内容 |
| ------ | --- |
| [LSP Sample](https://github.com/Microsoft/vscode-extension-samples/tree/master/lsp-sample)  | 小文字のアルファベットを見つけると注意する．本記事の内容に加え，設定ファイルへのアクセスなども行う |
| [LSP Multi Root Server Sample](https://github.com/Microsoft/vscode-extension-samples/tree/master/lsp-multi-server-sample)  | [マルチルートワークスペース](https://code.visualstudio.com/docs/editor/multi-root-workspaces)ごとにLSPを立ち上げる，LSP Sampleの拡張版 |
| [LSP Log Streaming Sample](https://github.com/Microsoft/vscode-extension-samples/tree/master/lsp-log-streaming-sample)  |LSP実行時にログを出力する, LSP Sampleの拡張版|
| [LSP UI Example](https://github.com/microsoft/vscode-extension-samples/tree/master/lsp-user-input-sample) |ファイルの１行目に文字の挿入を行うアクションを追加する|


より高度な開発を体験するには[各言語サーバーのOSS](https://microsoft.github.io/language-server-protocol/implementors/servers/)に参加するのが一番だと思います．

## 参考文献

* [Eclipse プラグイン開発](https://www.amazon.co.jp/Eclipseプラグイン開発-エリック-ガンマ/dp/4797324899)
* [Language Server Extension Guide](https://code.visualstudio.com/api/language-extensions/language-server-extension-guide)
* [Language Server Protocol](https://microsoft.github.io/language-server-protocol/)
