<div align="center">

  <h1><code>Rust and WebAssemblyでgame of life</code></h1>
  [Rust 🦀 and WebAssembly 🕸](https://rustwasm.github.io/docs/book/introduction.html)
  Rust&WasmでGameOfLifeを作るチュートリアルより。

  避けるべきこと
  - ティックごとにユニバース全体をWebAssemblyリニアメモリにコピーしたりWebAssemblyリニアメモリからコピーすること。
  ユニバース内のすべてのセルにオブジェクトを割り当てたり、各セルの読み取りと書き込みに境界を越えた呼び出しを貸したりする必要はありません。

  Universから特定の座標にあるセルを見つけるには以下の数式を使用する。
  ```
  index(row, column, universe) = row * widht(universe) + column
  ```
UniverseのセルをJSに公開する方法
`std::fmt::Display`forを実装する。
これを使用してテキストとしてセルを生成できるｌ。
このRustで生成された文字列はwasmリニアメモリからJSのガベージコレクションヒープ内のJS文字列にぴーされ、HＴＭＬｗお設定して表示されます。

 
</div>
