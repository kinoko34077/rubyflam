# japanese-ruby-parser

小説家になろう形式と青空文庫形式のルビ表記を、単体で解析・正規化・変換・再出力することを目的とする共通ライブラリ。

## 現在の状態
Repository Bootstrap直後の初期仕様。実装・完全互換性・リリースは未受入。

## 目標
- 小説家になろう公式のルビ挙動（明示／省略／括弧／抑制／長さ・文字種・無効入力）をテストで検証し、互換性を保証する。
- 青空文庫記法は既存OSS `aozora-wasm` を評価・再利用し、ルビ構造を共通の中間表現へ統合する。
- `japanese-orthography/runtime/transform-shared.js` など既存ルビコードを正本・回帰テストとして移植し、重複実装を残さない。
- 入力の原文範囲・記法・読み・親文字を保全し、HTML等へのレンダリングと再シリアライズを分離する。
- 単体ライブラリ受入後に、各既存リポのルビ処理を利用側アダプターへ段階的に置換する。

## 参照
- 既存正本: https://github.com/kinoko34077/japanese-orthography
- 既存ランタイム: https://github.com/kinoko34077/japanese-orthography/blob/main/runtime/transform-shared.js
- 青空文庫パーサ候補: https://github.com/P4suta/aozora
- 管理: https://github.com/kinoko34077/devflow

## 境界
- 本リポはルビ記法の解析・構造化・描画用データ変換を所有する。漢字の読み自動生成、辞書・語義解決、歴史的表記変換は対象外。
- 本リポの仕様・ライブラリが正式受入されるまで、既存利用リポの既存コードは変更しない。
- 公開リポジトリであることと、ライセンス選択・パッケージ公開・リリースは別の決定。第三者著作権・NOTICEを検証してから配布する。
