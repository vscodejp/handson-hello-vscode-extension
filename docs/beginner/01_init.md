# Hello Worldを作成しよう

　Yaomanの`yo`コマンドで、VS Codeの拡張機能のプロジェクトを作成します。
以下のように`yo code`を実行してください。
今回は、TypeScriptを使った`hello-vscode`プロジェクトを作成しています。

```sh
$ yo code
**拡張機能のタイプ**
? What type of extension do you want to create?
New Extension (TypeScript)
**拡張機能の名前**
? What's the name of your extension?
Hello VSCode
**拡張機能のID（全小文字）**
? What's the identifier of your extension?
hello-vscode
**拡張機能の説明**
? What's the description of your extension?
（空欄のまま）
**gitリポジトリを作成するか**
? Initialize a git repository?
Yes
**webpackを利用して作成するか？**
? Bundle the source code with webpack?
No
**パッケージマネージャーはnpm？ それともyarn？**
? Which package manager to use?
npm
```

　作成されたHello VSCodeプロジェクトのディレクトリ構成は以下のとおりです。

```md
.
├── .vscode             // 拡張機能開発に使うVS Codeファイル
│   ├── extensions.json // 開発で利用する拡張機能。標準ではESLint
│   ├── launch.json     // 拡張機能のデバッグ用コマンドを扱うファイル
│   ├── setting.json    // プロジェクトの設定
│   └── tasks.json      // ビルドおよびコンパイル用
│── node_modules        // 依存パッケージ格納フォルダ
│── out                 // コンパイルで生成したファイル格納フォルダ
├── src
│   ├── extension.ts    // 拡張機能のソースコード
│   └─test
│      ├── suite
│      │    ├── extension.test.ts // ユニットテストコード
│      │    └── index.ts          // ユニットテスト実行用コード
│      └── runTest.ts             // テストコードのメインファイル
├── .eslintrc.json    // ESLintの設定ファイル
├── .gitignore        // Gitで管理しないファイルを定義する
├── .vscodeignore     // 拡張機能のパッケージ時に除外するファイルの定義
├── CHANGELOG.md      // ユーザーに向けた拡張機能の更新情報
├── package-lock.json // node_modulesを再現するための依存関係リスト
├── package.json      // 依存関係、バージョン、仕様の管理
├── README.md         // 拡張機能の説明書
├── tsconfig.json     // TypeScriptのコンパイル設定
└── vsc-extension-quickstart.md // 拡張機能開発のHOWTOドキュメント
```

特に重要なファイルは、`src/extension.ts`と`test/suite/extension.test.ts`、`package.json`です。
`src/extension.ts`と`test/suite/extension.test.ts`は以降で紹介します。`./package.json`は多くの要素で構成されているため、[詳細はドキュメント](https://code.visualstudio.com/api/references/extension-manifest)を参照してください。
