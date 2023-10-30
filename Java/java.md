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
1. ソースコード（人間語）の作成
2. コンパイル（翻訳：コンピューターが理解できる文字列へ）
3. 処理の実行
4. デバッグ（ソースコードの修正）

## JDK
- Java Development Kit
- 二つの機能
- コンパイラー（javacコマンド）
- Javaの実行環境（Java仮想マシン、JVM:Java Virtual Machineの略。これをインストールすればOSに依存せずにどんな環境でもJavaのプログラムを動かすことができる）
- 用途により数種類のパッケージがある。通常はJava SE（スタンダードエディション）

## eclipse(Pleiades All in One)
- 統合開発環境

## ソースコード実行の3ステップ
1. カレントディレクトリの変更
2. コンパイル `javac Sample.java` でバイトコードファイルを生成（Sample.class）
3. 実行　`java Sample` のみでOK（拡張子は不要）


## コンソールに出力
- `System.out.println();`

### 基本的なコードの書き方
- classの後のSampleはファイル名と同じにする
- `public static void main(String[] args){}`これはお決まりのおまじないで{}のブロック中に処理を書いていく
~~~
class Sample {

	public static void main(String[] args) {
		System.out.println("Hello World");

	}

}
~~~

## 変数
- 名前付きの箱
- 変数で扱われるデータのことを値

### 型
-　　変数で扱うデータの種類
- intはデータ型で整数の意味
~~~
  int number;
  number = 10;
~~~

- Stringはデータ型で文字列の意味
~~~
  String name;
  name = "Yamada";
~~~

## データ型の変換
- 文字列→整数`Integer.parseInt(int型として扱いたい文字列)`
- 整数→文字列`String.valueOf(String型として扱いたい整数)`

## 配列
- 型名[] 配列名 = new 型名[要素名];
- 短縮した書き方で配列の宣言と同時に複数の要素を初期化する`char[] sample = {'赤','青','白'}`

## 自己代入
~~~
int x = 3;
x = x + 2;
出力結果 5
~~~
### 省略形
- `x = x + 10;` → `x += 10;`
### 値が1の時さらに省略可能
- `x = x + 1;` → `x += 1;` → `x ++;`

## 型変換
### 自動変換
- int型とdouble型の計算結果はdouble型になる
### 強制型変換
#### キャスト
~~~
int number1 = 13;
int number2 = 4;
System.out.println((double)number1 / number2);
~~~
- （double）の右横の変数が強制的にdouble型になることで、number2もそれに合わせてdouble型になり、出力結果が3ではなく3.25になる

## 真偽値
- boolean型
- true,false

## 条件分岐
### if文
- if文の{}に「;」はいらない。また{}内の処理のまとまりをブロックという
~~~
if (条件式)　{
   処理;
}

int x = 10;
if (x == 10) {
   System.out.println("xは10です");
}
~~~

### switch文
~~~
swich (条件の値) {
   case 値1:
　　　　　　　　処理；
　　　　　　　　break;
   case 値2:
　　　　　　　　処理；
　　　　　　　　break;
   case 値3:
　　　　　　　　処理；
　　　　　　　　break;
}
~~~
### default
- if文のelseみたいな役割を持つdefaultがある
~~~
int n = 0;
swich (n) {
   case 1:
　　　　　　　　System.out.println("大吉");
　　　　　　　　break;
   case 2:
　　　　　　　　System.out.println("吉");
　　　　　　　　break;
   case 3:
　　　　　　　　System.out.println("小吉");
　　　　　　　　break;
　　　　　　default:
    System.out.println("大凶");
    break
}
~~~
### while文
- 条件がtrueの間、{}内の処理を繰り返す
~~~
while (条件) {
　　　　繰り返す処理;
}

int i = 1;

while (i <= 5) {
    System.out.println(i);
    i++;
}
~~~
- 繰り返し処理の流れ
1. 変数の初期化
2. 条件
3. 繰り返す処理
4. 変数の更新(無限ループに陥るので必ず、falseになる条件を実装すること。例「i++;」)

### for文
- forの後の()内に、「変数の初期化、条件式、変数の更新」の3つを記述する。それぞれセミコロンで区切るが、最後の変数の更新にはセミコロンはつけないことに注意。
~~~
for (int i = 1; i <= 5; i++;) {
    System.out.println(i);
}
~~~
### break
- 条件をfalseにする以外に、繰り返し処理を終了させる記述
- 下記のようにif文などの条件分岐と組み合わせることで、任意の箇所で繰り返し処理を終了させる(変数iの値が6になった段階でfor分を終了)
~~~
for (int i = 1; i <= 10; i++;) {
    if (i > 5) {
      break;
    }
    System.out.println(i);
}
~~~
### continue
- continueはその周の処理だけをスキップして、次の周を実行する。下記のようにif文などと組み合わせる。
- 変数iが3の倍数の時、その周のループを終了し、次のループを実行する。したがって出力結果は、1,2,4,5,7,8,10
~~~
for (int i = 1; i <= 10; i++;) {
    if (i % 3 == 0) {
      continue;
    }
    System.out.println(i);
}
~~~
## 配列
- `int[] numbers = {1,2,3};`
- `String[] names = {"tanaka","yamada","suzuki"};`
- 配列の要素は、前から順に「0,1,2,・・・」とインデックス番号が振られている
- 配列の各要素は、配列名[インデックス番号]とすることで取得できる
~~~
String[] names = {"tanaka","yamada","suzuki"};
System.out.println("私の名前は" + names[0] + "です");
出力結果
私の名前はtanakaです
~~~
###　配列とfor文
- 下記の例ではiが「0,1,2」の間繰り返し処理される
~~~
String[] names = {"tanaka","yamada","suzuki"};
for (int i = 0; i < 3; i++) {
    System.out.println("私の名前は" + names[i] + "です");
}
~~~
### length
 - lengthを使うと要素を数えてくれるので、それを使い上記の`i < 3`と置き換えて使用できる
~~~
String[] names = {"tanaka","yamada","suzuki"};
for (int i = 0; i < names.lemgth; i++) {
    System.out.println("私の名前は" + names[i] + "です");
}
~~~
### 拡張for文（配列用の特別なfor文）
- 上記までのfor文よりも短縮して書ける
~~~
for (データ型　変数名：配列名) {
    繰り返す処理;
}

String[] names = {"tanaka","yamada","suzuki"};
for (string name:names) {
    System.out.println("私の名前は" + name + "です");
}
~~~

## メソッド
- メソッドは何かしらの処理を割り当てた部品。処理ごとにメソッド切り分けるとわかりやすい。
- メソッドは何度でも使い回すことができる
