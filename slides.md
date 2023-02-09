---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: "../assets/images/rive_screenshot.png"
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
transition: slide-left
# use UnoCSS
css: unocss
---

# 簡単！ツール一つで<br>アニメーションが作れる<br>RIVEをさわってみた

HMS Engineering Lightning Talks<br>2/9

<!--
  - 挨拶
  - りぶ？らいぶ？
  - このツール一つでアニメーションが作れる


  - どんなアニメーションが作れるか
-->

---
class: px-20
---

<h1 class="smaller_head">イラスト系のサイトでたまに見られるこういう表現...</h1>

<div grid="~ cols-2 gap-2" m="-t-2">

<a class="text-xl font-bold text-indigo-800" href="https://cookpad.careers/" target="_blank">https://cookpad.careers/</a>

<a class="text-xl font-bold text-indigo-800" href="https://www.prismpartner.co.jp/" target="_blank">https://www.prismpartner.co.jp/</a>

<img border="rounded" src="/assets/images/cookpad_screenshot.png">

<img border="rounded" src="/assets/images/prism_screenshot.png">

</div>

<p class="text-xl font-bold text-indigo-800 slidev-vclick-target slidev-vclick-hidden" v-click>
  これら2つは<strong>Lottie</strong>というツールを使って作られている
</p>

<style>
  .smaller_head {
    font-size: 2rem !important;
  }

  .slidev-vclick-target {
    transition: opacity 500ms ease;
  }

  .slidev-vclick-hidden {
    opacity: 0;
    pointer-events: none;
  }
</style>

---

# Lottieとは

<a href="https://airbnb.design/lottie/" target="_blank">https://airbnb.design/lottie/</a>

<ul>
  <li class="text-xl font-bold text-indigo-800" v-click>Airbnbが運営するアニメーションライブラリ</li>
  <li class="text-xl font-bold text-indigo-800" v-click>After Effect(Adobe製の動画・アニメーション作成ツール)で作ったアニメーションを扱う</li>
  <li class="text-xl font-bold text-indigo-800" v-click>After Effectで作ったアニメーションを<br>ZXP installer,Bodymovinを使って書き出したJSONファイルを元にサイトやアプリに埋め込む</li>
  <li class="text-xl font-bold text-indigo-800" v-click>Web / iOS / Android / React Native / Windowsに対応</li>
</ul>

<br>
<br>

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

ul {
  margin-top: 3rem;
}

li {
  margin-bottom: 2rem;
}
</style>

<!--
  - LottieとはAirbnbが運営しているアニメーションライブラリ
  - Adobe製のAfterEffectという動画・アニメーション作成ツールで作ったアニメーションを扱う
  - ZXPinstallerというツール上で、Bodymovinというアドオンをインストールしてそれを使ってAfterEffectのアニメーションをJSONファイルに書き出す。それをlottieを使ってサイトやアプリに埋め込む。
  - Web,iOS,Android,ReactNative,Windowsアプリなど幅広く対応
-->


---

# Lottieの不便なところ

<p></p>

<ul>
  <li class="text-xl font-bold text-indigo-800" v-click>たくさんのツールを使う必要がある...</li>
  <li class="text-xl font-bold text-indigo-800" v-click>AfterEffectで作ったアニメーションがそのまま動く保証がない...</li>
  <li class="text-xl font-bold text-indigo-800" v-click>インタラクティブな動きをAfterEffect上で作ることができない...</li>
</ul>

<p class="text-4xl font-bold text-orange-400" v-click>ここで今回紹介するRIVEの出番です</p>

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

ul {
  margin: 3rem auto;
}

li {
  margin-bottom: 2rem;
}
</style>

<!--
- Lottieを使うにはAfterEffectでアニメーションを作成し、ZXP installer,Bodymovinを使ってJSONを出力することが必須になる
  - AfterEffectで作ったアニメーションをBodymovin等のサードパーティ製のツールを通す必要があるので、作ったアニメーションがそのまま確実に動くという保証がない
  - LottieLabというAEを使わなくても作れるようにするツールが作られているがまだ開発中とのこと https://lottielab.com/
  - AfterEffectは動画でしかないので、Lottieのコード上であればホバーとかスクロールに合わせた簡単なインタラクティブな動きを作ることはできるが、AE上でそのテスト等をすることができない
-->

---

# RIVEのここがすごい

<a href="https://rive.app/" target="_blank">https://rive.app/</a>

<ul>
  <li class="text-xl font-bold text-indigo-800" v-click>ブラウザで動くモーショングラフィックツール</li>
  <li class="text-xl font-bold text-indigo-800" v-click>MacOSアプリが最近リリース（Windowsは開発中）</li>
  <li class="text-xl font-bold text-indigo-800" v-click>デザインの作成からアニメーションの作成、ファイルの書き出しまで、RIVEのみで完結することができる</li>
  <li class="text-xl font-bold text-indigo-800" v-click>インタラクティブな動きをRIVE上で作成することができる</li>
</ul>

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

ul {
  margin-top: 3rem;
}

li {
  margin-bottom: 2rem;
}
</style>

<!--
  - RIVEはブラウザ上で作ることができる
  - MacOSアプリが最近リリースされた
  - Lottieでは沢山のツール群を使っていたが、RIVEではデザインの作成から、アニメーションの作成、ファイルの書き出しまでこれ一つで行うことができる
  - (そのため、Lottieで懸念であった作ったアニメーションの動作が保証されていないという問題はクリアになる)
  - デザイン上のボタンやRIVE上で設定したトリガーを通じてインタラクティブな動きを設定可能、かなり複雑な動作もさせることができる
  - 実際にRIVEアプリをさわっていく
-->

---

# RIVEの使い方

これを作っていく

<Rive src="/assets/rivs/bird.riv" v-click />

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

# デザインの作成

<p></p>

<ul>
  <li class="text-xl font-bold text-indigo-800" v-click>簡単なイラストとかだと十分にかける(かも？)</li>
  <li class="text-xl font-bold text-indigo-800" v-click>モーションライブラリならではの骨？も使える</li>
</ul>

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

ul {
  margin-top: 3rem;
}

li {
  margin-bottom: 2rem;
}
</style>

<!--
  - わからないからデザイナーの方触ってみて感想を教えてください
  - 簡単なイラストくらいだったら余裕で使えるのでは
  - モーションライブラリならではの骨みたいなのも使える（使い方わからん）
-->

---

# アニメーションの作成

<p></p>

<ul>
  <li class="text-xl font-bold text-indigo-800" v-click>かなり直感的</li>
  <li class="text-xl font-bold text-indigo-800" v-click>細かいこともできそうな印象</li>
</ul>


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

ul {
  margin-top: 3rem;
}

li {
  margin-bottom: 2rem;
}
</style>

<!--
  - ここもAE使っているデザイナーの方、感想を教えて欲しい
  - 操作はかなり直感的で使いやすい気がする
  - 結構細かいことできる気が、凝ろうと思えば凝れる感
-->

---

# エクスポート

<p></p>

<ul>
  <li class="text-xl font-bold text-indigo-800" v-click>簡単に出力可能</li>
  <li class="text-xl font-bold text-indigo-800" v-click>

  `.riv`という拡張子を持つファイルを取得することができる

  </li>
  <li class="text-xl font-bold text-indigo-800" v-click>RIVEはWeb / React / iOS / Android / Flutter / C++ (Mac/Linux/Windows) / C# / React NativeとLottieよりも幅広く対応(?)</li>
</ul>


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

ul {
  margin-top: 3rem;
}

li {
  margin-bottom: 2rem;
}
</style>

<!--
  - ボタン一つでファイルの出力が完了
  - `.riv`という拡張子を持つファイルを出力
  - わざわざJsonファイルとかにしない潔さ？
  - Web / React / iOS / Android / Flutter / C++ (Mac/Linux/Windows) / C# / React NativeとLottieよりも幅広く対応
  - ReactとかはWebと一緒だが、公式ライブラリがReact用にでていたりして、使いやすい
-->

---
layout: image-right
image: ../assets/images/simple_rive_screenshot.png
---


# Webで表示してみる

<p></p>

<a class="text-xl font-bold text-indigo-800" href="https://t5a1r1ou.github.io/simple_rive/" target="_blank">https://t5a1r1ou.github.io/simple_rive/</a>

```js

// これだけ！
new rive.Rive({
  src: "./assets/rivs/bird.riv",
  canvas: document.getElementById("canvas"),
  autoplay: true
});


```

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

ul {
  margin-top: 3rem;
}

li {
  margin-bottom: 2rem;
}
</style>

---

# インタラクティブなアニメーションを追加する

<p></p>

<a class="text-xl font-bold text-indigo-800" href="https://t5a1r1ou.github.io/interactive_rive/" target="_blank">https://t5a1r1ou.github.io/interactive_rive/</a>

<RiveInterActive src="/assets/rivs/bird_interactive.riv" v-click />

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

ul {
  margin-top: 3rem;
}

li {
  margin-bottom: 2rem;
}
</style>


---
layout: image-right
image: ../assets/images/janken_screenshot.png
---

# じゃんけんゲームに導入してみた

<p></p>

<a class="text-xl font-bold text-indigo-800" href="https://t5a1r1ou.github.io/janken_rive/" target="_blank">https://t5a1r1ou.github.io/janken_rive/</a>

<ul>
  <li class="text-xl font-bold text-indigo-800" v-click>プログラム上からアニメーションを発火させることができるtriggerを使っている</li>
</ul>


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

ul {
  margin-top: 3rem;
}

li {
  margin-bottom: 2rem;
}
</style>

<!--
  - JS講座で作ったじゃんけんゲームの画像をそれぞれアニメーションに置き換えてみた
  - triggerと呼ばれるプログラム上からアニメーションを発火させることができるものを使っている
  - 実際に作った画面を見てみる
-->

---

# RIVEのここが辛い

<p></p>

<ul>
  <li class="text-xl font-bold text-indigo-800" v-click>ドキュメントが英語</li>
  <li class="text-xl font-bold text-indigo-800" v-click>Lottieに比べて情報が少ない</li>
  <li class="text-xl font-bold text-indigo-800" v-click>無料枠3つ...(無料でつかわせてもらえるだけでありがたい...)</li>
</ul>


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

ul {
  margin-top: 3rem;
}

li {
  margin-bottom: 2rem;
}
</style>

<!--
  - ドキュメントが英語なのはLottieもだけど、、、
  - Lottieに比べて情報が少ないいい
  - 無料枠3つ 無駄にアカウント2つ作りました
-->

---
layout: center
class: text-center
---

# サンプルのご紹介

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
layout: center
class: text-center
---

# ご清聴ありがとうございました

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
