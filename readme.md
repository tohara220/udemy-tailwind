## 学ぶこと
- 基礎
- 簡単にウェブサイトを作りたい
- レスポンシブ

## nodeとは？
- サーバー側で動くJS
- インストールするとnode, nmpが使えるようになる。
- npm install -g yarn
    - globalでyarnが使えるようになる

## 環境構築 => npm は node ないと不可。-D は開発環境用 -Gはどのプロジェクトでも使えるようにする。
- npm install -D tailwindcss
- npx tailwindcss init

## ビルドのショートカット作成
- npm init -y
- npm run build # ショートカットされたものを呼び出す
- watch（常に監視）というものが適用されてrebuildされている。
- input.cssがoutput.cssに反映される！

## tailwindの波線を解消する
- "css.lint.unknownAtRules": "ignore",をcode-workspaceに追記する。波線消える。
- tailwind CSS IntelliSenseも入れる。

## TailwindCSSとは？
- CSSフレームワーク。
    - 部品を使ってWebサイトを作れる！
    - 一からCSSを描かなくて良い。
- できること
    - レスポンシブ対応
    - 繰り返し使うスタイルを抽出化
        - dangerの色をよく使う => 他のパーツに対して適用できる。
    - カスタマイズデザイン

- メリット
    - クラス名を考えなくて良い
    - CSSファイルが肥大化しない。作る必要がない。
    - 変更を加えるのが怖くない。（依存部分は限定的）

- よく使われる場面
    - react, viewなど
    - コンポーネント管理ができるため

- プロパティ
    - 文字サイズ変更
        - text-7xl
    - 太さ
        - font-bold
    - padding
        - 内側の余白
        - px, py
    - margin
        - 要素の外側の余白

- レスポンシブにおけるブレークポイント
    - スマホ；~640px sm
    - タブレット: ~768 md
    - 小さいPC: ~1250px lg
    - 大きいPC: 1250px~ xl
- レスポンシブ：ユーティリティを使う。
    - breakpoint

- 幅を狭くしたら文字色を小さくする
- sm:text-red-400 sm以上のサイズなら、テキストをレッドにする。

- 抽出化
    - 新しいクラスをinput.cssで作成する
    - クラス内で@applyとして、そのクラスに紐づけたい属性を並列でかく。

- カスタムデザイン
    - extends: {colors{primary: {100:"#ebf8ff"}}}

- フォントを変える方法
    - Googleフォントで使いたいものをチェックする
    - linkタグをコピーしてhead内に貼り付け
    - CSS rulesをtailwind.config.jsのfontfamily:{}の中に書き込む。

- navバー
    - container: 
    - 中央に配置するにはmx-autoを当てる。
    - いい感じに余白が当たる。
    - containerとmx-autoの組み合わせで実現できる。
    - mx-auto: margin leftとmargin rightがautoになる。

- 横並びにする。
    - flexで小要素を横並びにする。
    - justify-between: 
    - justifyはflexがないと当たらないので注意
    - items-center: 横の線に沿って整列させるナビゲーションバーの文字列の中心を基準に揃える。
- 感覚をあける 
    - space-x-12

- 色を変える
    - hover:text-selected-text transition-all duration-300
    - 300msかけてテキストの色を変える

- ハンバーガーメニューをつける
    - まずは消したい部分を指定する。class="md:hidden"
    - ハンバーガーアイコンを取得する
        - font-awsome
        - https://cdnjs.com/libraries/font-awesome　まずはここからcdnjsを取得する
        - <i class="fa-solid fa-bars"></i>を入れる。
        - リンクを消す。
        - hiddenにして、追加でmd:flexすると、条件で消えるようになる。
        - 中央揃え: items-center
        - div.containerとすると、簡単にクラスが作れる！

- ヒーローセクション
    - flex-wrapは、はみ出たら折り返す

- 文字を左揃えにする
    - md:text-left md以上で左揃えになる
    - 

- -z-10 Z軸で奥側にする。