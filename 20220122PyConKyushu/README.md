# Welcome to [Slidev](https://github.com/slidevjs/slidev)!

To start the slide show:

- `npm install`
- `npm run dev`
- visit http://localhost:3030

Edit the [slides.md](./slides.md) to see the changes.

Learn more about Slidev on [documentations](https://sli.dev/).

## 環境構築

```
$ cd slides
$ npm init slidev
```

```
✔ Project name: … 20220122PyConKyushu
✔ Package name: … 20220122pyconkyushu
  Scaffolding project in 20220122PyConKyushu ...
  Done.

✔ Install and start it now? … yes
✔ Choose the agent › npm
```

Export用設定

```
$ npm i -D playwright-chromium
```

## コマンド

起動

```
$ npx slidev
```

PDFエクスポート

```
$ npx slidev export
```

クリックごとのページを作る

```
$ npx slidev export --with-clicks
```

