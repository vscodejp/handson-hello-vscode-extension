# 補完機能の実装

## ブランチ切り替え

補完機能の実装CodeTourを使うためには，ブランチを切り替える必要があります．

```sh
git checkout -b completion
```

## サーバー設定

```ts
connection.onInitialize((params): InitializeResult => {
    ...
    return {
        capabilities: {
            ...
            // Tell the client that the server supports code completion
            completionProvider: {
                resolveProvider: true
            }
        }
    };
});
```

## 補完機能の実装



## 使ってみよう

## テストしよう

## 発展課題

* 好きな言語の補完機能を実装してみよう．(package.jsonでの対応言語設定を忘れないように)
* 補完機能を実装したら，テストしてみよう．
