# RSMDCのStorybookでマニュアルのデプロイ手順

## 目的

Storybookで作ったRSMDCのマニュアルをデプロイするため手順です。

マニュアルは[https://rsmdc.github.io](https://rsmdc.github.io)で参照出来ます。

## 手順

**A. 順番ステップ**

1. `rsmdc.github.io`というプロジェクトを`clone`します

```cmd
$ git clone https://github.com/rsmdc/rsmdc.github.io.git
```

2. `rsmdc-storybook` というプロジェクトを`clone`します

```cmd
$ cd rsmdc.github.io.git
$ git clone https://github.com/rsmdc/rsmdc.github.io.git
```

3. `rsmdc-storybook` をビルドします

```
$ cd rsmdc-storybook
$ yarn
$ yarn build-storybook
```

4. ビルドしたファイルに反映します。

```cmd
$ cd ..
$ cp -r rsmdc-storybook/storybook-static/* .
```

5. Githubに変更したものを反映します。

```cmd
$ git add .
$ git commit -m 'release '$(date +%F)
$ git push origin master
```

デプロイが終わります。 [https://rsmdc.github.io](https://rsmdc.github.io)に変更したものが確認出来ます。

**B. 短い実行コマンド**

`A.`のコマンドをまとめて、以下のコマンドが早く実行出来ます。

```cmd
$ yarn build
$ yarn deploy
```


