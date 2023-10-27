# Java
- プログラミング言語の一つ
- 様々なデバイスで動くアプリケーションを作ることができる
- Write Once,Run Anywhere.一度書いたらどこでも動作するを提唱

## プログラミング言語のタイプ
### インタープリター方式
- PHP/Ruby/python/JavaScript...
- 事前のコンパイルが必要なく、書いたらすぐに実行ができるがコンパイル型より処理が遅いデメリットがある

### コンパイラ方式
- C/C++/Java...
- 処理が高速だが、書き直すたびに変換が必要で手間がかかるデメリットがある

## プログラミングの手順
1.ソースコード（人間語）の作成
2.コンパイル（翻訳：コンピューターが理解できる文字列へ）
3.処理の実行
4.デバッグ（ソースコードの修正）

## JDK
- Java Development Kit
- 二つの機能
- コンパイラー（javacコマンド）
- Javaの実行環境（Java仮想マシン、JVM:Java Virtual Machineの略。これをインストールすればOSに依存せずにどんな環境でもJavaのプログラムを動かすことができる）
- 用途により数種類のパッケージがある。通常はJava SE（スタンダードエディション）

## eclipse(Pleiades All in One)
- 統合開発環境

## ソースコード実行の3ステップ
1.カレントディレクトリの変更
2.コンパイル `javac Sample.java` でバイトコードファイルを生成（Sample.class）
3.実行　`java Sample` のみでOK（拡張子は不要）


## コンソールに出力
- `System.out.println();`

## 変数
- intはデータ型で整数の意味
  
  int number;
  number = 10;

- Stringはデータ型で文字列の意味
- String name;
- name = "Yamada";
