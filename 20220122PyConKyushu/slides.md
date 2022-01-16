---
# try also 'default' to start simple
theme: default
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: "text-center"
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
---

# Welcome to Slidev

Presentation slides for developers

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub"
    class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---

# What is Slidev?

Slidev is a slides maker and presenter designed for developers, consist of the following features

- 📝 **Text-based** - focus on the content with Markdown, and then style them later
- 🎨 **Themable** - theme can be shared and used with npm packages
- 🧑‍💻 **Developer Friendly** - code highlighting, live coding with autocompletion
- 🤹 **Interactive** - embedding Vue components to enhance your expressions
- 🎥 **Recording** - built-in recording and camera view
- 📤 **Portable** - export into PDF, PNGs, or even a hostable SPA
- 🛠 **Hackable** - anything possible on a webpage

<br>
<br>

Read more about [Why Slidev?](https://sli.dev/guide/why)

<!--
You can have `style` tag in markdown to override the style for the current page.
Learn more: https://sli.dev/guide/syntax#embedded-styles
-->

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---

# Navigation

Hover on the bottom-left corner to see the navigation's controls panel, [learn more](https://sli.dev/guide/navigation.html)

### Keyboard Shortcuts

|                                                    |                             |
| -------------------------------------------------- | --------------------------- |
| <kbd>right</kbd> / <kbd>space</kbd>                | next animation or slide     |
| <kbd>left</kbd> / <kbd>shift</kbd><kbd>space</kbd> | previous animation or slide |
| <kbd>up</kbd>                                      | previous slide              |
| <kbd>down</kbd>                                    | next slide                  |

<!-- https://sli.dev/guide/animations.html#click-animations -->

<img
  v-click
  class="absolute -bottom-9 -left-7 w-80 opacity-50"
  src="https://sli.dev/assets/arrow-bottom-left.svg"
/>

<p v-after class="absolute bottom-23 left-45 opacity-30 transform -rotate-10">Here!</p>

---

layout: image-right
image: https://source.unsplash.com/collection/94734566/1920x1080

---

# Code

Use code snippets and get the highlighting directly![^1]

```ts {all|2|1-6|9|all}
interface User {
  id: number;
  firstName: string;
  lastName: string;
  role: string;
}

function updateUser(id: number, update: User) {
  const user = getUser(id);
  const newUser = { ...user, ...update };
  saveUser(id, newUser);
}
```

<arrow v-click="3" x1="400" y1="420" x2="230" y2="330" color="#564" width="3" arrowSize="1" />

[^1]: [Learn More](https://sli.dev/guide/syntax.html#line-highlighting)

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
</style>

---

# Components

<div grid="~ cols-2 gap-4">
<div>

You can use Vue components directly inside your slides.

We have provided a few built-in components like `<Tweet/>` and `<Youtube/>` that you can use directly. And adding your custom components is also super easy.

```html
<Counter :count="10" />
```

<!-- ./components/Counter.vue -->
<Counter :count="10" m="t-4" />

Check out [the guides](https://sli.dev/builtin/components.html) for more.

</div>
<div>

```html
<Tweet id="1390115482657726468" />
```

<Tweet id="1390115482657726468" scale="0.65" />

</div>
</div>

---

## class: px-20

# Themes

Slidev comes with powerful theming support. Themes can provide styles, layouts, components, or even configurations for tools. Switching between themes by just **one edit** in your frontmatter:

<div grid="~ cols-2 gap-2" m="-t-2">

```yaml
---
theme: default
---
```

```yaml
---
theme: seriph
---
```

<img border="rounded" src="https://github.com/slidevjs/themes/blob/main/screenshots/theme-default/01.png?raw=true">

<img border="rounded" src="https://github.com/slidevjs/themes/blob/main/screenshots/theme-seriph/01.png?raw=true">

</div>

Read more about [How to use a theme](https://sli.dev/themes/use.html) and
check out the [Awesome Themes Gallery](https://sli.dev/themes/gallery.html).

---

## preload: false

# Animations

Animations are powered by [@vueuse/motion](https://motion.vueuse.org/).

```html
<div v-motion :initial="{ x: -80 }" :enter="{ x: 0 }">Slidev</div>
```

<div class="w-60 relative mt-6">
  <div class="relative w-40 h-40">
    <img
      v-motion
      :initial="{ x: 800, y: -100, scale: 1.5, rotate: -50 }"
      :enter="final"
      class="absolute top-0 left-0 right-0 bottom-0"
      src="https://sli.dev/logo-square.png"
    />
    <img
      v-motion
      :initial="{ y: 500, x: -100, scale: 2 }"
      :enter="final"
      class="absolute top-0 left-0 right-0 bottom-0"
      src="https://sli.dev/logo-circle.png"
    />
    <img
      v-motion
      :initial="{ x: 600, y: 400, scale: 2, rotate: 100 }"
      :enter="final"
      class="absolute top-0 left-0 right-0 bottom-0"
      src="https://sli.dev/logo-triangle.png"
    />
  </div>

  <div
    class="text-5xl absolute top-14 left-40 text-[#2B90B6] -z-1"
    v-motion
    :initial="{ x: -80, opacity: 0}"
    :enter="{ x: 0, opacity: 1, transition: { delay: 2000, duration: 1000 } }">
    Slidev
  </div>
</div>

<!-- vue script setup scripts can be directly used in markdown, and will only affects current page -->
<script setup lang="ts">
const final = {
  x: 0,
  y: 0,
  rotate: 0,
  scale: 1,
  transition: {
    type: 'spring',
    damping: 10,
    stiffness: 20,
    mass: 2
  }
}
</script>

<div
  v-motion
  :initial="{ x:35, y: 40, opacity: 0}"
  :enter="{ y: 0, opacity: 1, transition: { delay: 3500 } }">

[Learn More](https://sli.dev/guide/animations.html#motion)

</div>


---
layout: center
class: text-center

---

# Learn More

[Documentations](https://sli.dev) · [GitHub](https://github.com/slidevjs/slidev) · [Showcases](https://sli.dev/showcases.html)

---

# 自己紹介

---

# 会社紹介

---

# その他関連組織

---

# Podcast 紹介

---
layout: section

---

# このトークの概要

2017 年に PyCon mini Kumamoto でトークした内容を 2022 年版にアップデートしたものです

https://speakerdeck.com/terapyon/sugushi-merareru-pythonfalsehuan-jing-gou-zhu

---
layout: section

---
# Python バージョン

何を使っていますか？

---

# 寺田のオススメ

|                        |                  |
| ---------------------- | ---------------- |
| 実装                   | CPython          |
| Python バージョン       | 3.9              |
| インストール方法         | 公式インストーラ |
| 仮想環境                | venv             |
| パッケージインストール     | pip              |
| エディタ                | VSCode           |

<style>
td:nth-of-type(1){
  text-align: center;
}
tr:nth-child(odd) td {
    background-color: #f8f8f8;
}
tr:nth-child(even) td {
    background-color: #ffffff;
}
}
</style>

---
layout: section

---

# 実装

---

# Python 実装と選択

<div grid="~ cols-2 gap-4">
<div>

## 実装の種類

- CPython
  - C で実装されている
- PyPy
  - Python で実装
- MicroPython
- Cython

</div>
<div v-click>

## 選択方法

- 特別な理由がなければ
- CPython でいい。
- Python といえば CPython のことを言う

</div>
</div>
---
layout: section

---

# バージョン

---

# バージョン年表

---

# Python バージョンの選択

- 特別な理由がなければ
  - 最新がでてから、半年くらいたったとき
- 選択するときのポイント
  - ライブラリが対応しているか？
  - 動作させる環境は？

---

# バージョンアップのタイミング

- あせって、Python のバージョンを上げなくてもいい
  - 5 年間の保守期間があるので
- 上げるモチベーション
  - 新しい機能を使いたい
  - ライブラリの対応状況が変わる
  - 積極的にやらないことが多い

---

# インストール方法

---

# インストール方法の種類

- 公式インストーラ
  - バニラインストーラ
- 公式版をソースコンパイル
- OS パッケージマネージャー
  - apt / DNF / brew
- Anaconda
  - 様々なパッケージがまとめてインストール

---

# インストール方法の種類

- 特に理由がなければ
  - 公式インストーラ
- Linux 環境なら
  - ソースコンパイル
- パッケージマネジャーを使う場合もある

---

# 公式サイトのスクリーンショット

---

# Anaconda

- 科学技術計算系のパッケージが同梱されている
- インストールは手軽だが、
  - ハマリポイントも多い
- Windows 環境でも、公式版と pip でインストールが可能
  - wheel のおかげ
- 大企業で使う場合は有料化されているので注意

---

# Python のバージョンを複数

- OS 上に複数のマイナーバージョン
  - 公式インストーラでインストール可能
  - マイクロバージョンを混在させることはできない

---

# 仮想環境

---

# 仮想環境とは

- 一つの OS 上に、複数の Python 環境を作れる
- 利用する Python ライブラリを区分できる
- OS 上のグローバルな Python 環境をクリーンに保てる

- Python レイヤーの仮想環境に限定
- OS を仮想化やコンテナ化とは別物

---

# 仮想環境の種類

- venv モジュール
  - Python 標準ライブラリ
- virtualenv
  - 以前の Python では使われていた
  - venv モジュールがある今、使われない
- pyenv
  - Python のマイクロバージョンの切替も可能
- conda コマンド
  - Anaconda で使う

---

# 仮想環境の選択

- venv モジュール

venv モジュールの使い方

<div grid="~ cols-2 gap-4">
<div>

Linux / macOS

```
$ python -m venv venv  # venvというフォルダができる
$ sourse venv/bin/activate  # 仮想環境を有効化
(venv) $   # プロンプトが変化
(venv) $ deactivate. # 仮想環境の無効化
$ rm -r venv  # 仮想環境のフォルダを削除
```

</div>
<div>

Windows

```
> py -m venv venv  # venvというフォルダができる
> venv\Scripts\Activate.ps1 # 仮想環境を有効化
(venv) >   # プロンプトが変化
(venv) > deactivate. # 仮想環境の無効化
$ rmdir venv  # 仮想環境のフォルダを削除
```
</div>
</div>

---

# パッケージのインストール

---

# パッケージのインストールとは

- サードパーティー製パッケージを導入
- PyPI (パイピーアイと読む)
- https://pypi.org

---

# PyPI

スクリーンキャプチャ

---

# pip コマンド

- ***

# wheel とは

---

# エディタ

---

# エディタの種類

---

# エディタの選択

---

# 寺田のオススメ(再掲)

---

# 寺田の環境 macOS

---

# 寺田の環境 Linux

---

# Windows の場合
