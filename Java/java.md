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
### 配列とfor文
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

~~~
class Main {
  public static void main(String[] args) {
    // sampleメソッドを呼び出してください
    sample();
    
  }
  
  // sampleaメソッドを定義してください
  public static void sample() {
  System.out.println("私の名前はTanaka Tarouです");
  }
  
}

出力結果
私の名前はTanaka Tarouです
~~~

## 引数
- メソッドに与える追加情報のようなものでメソッドを呼び出す時に一緒に引数を渡すと、メソッドの中でその値を利用することができる。
~~~
public static void メソッド名（データ型　変数名） {
    実行する処理;
}

public static void hello（String name） {
    実行する処理;
}
~~~
- 上記のメソッド名の後のかっこは仮引数

~~~
class Main {
  public static void main(String[] args) {
    // 引数に「Yamada Yarou」を渡してください
    printData("Yamada Yarou");
    
    // 引数に「Tanaka Hanako」を渡してください
    printData("Tanaka Hanako");
    
  }

  // 引数を受け取るようにしてください
  public static void printData(String name) {
    // 「私の名前は◯◯です」と出力されるように書き換えてください
    System.out.println("私の名前は" + name +"です");
    
  }
}

出力結果
私の名前はYamada Tarouです
私の名前はTanaka Hanakoです
~~~
### 引数は複数持つことができる
- 「,」カンマで区切る
~~~
public static void メソッド名(データ型 変数名1,データ型 変数名2) {
    実行する処理;
}

例
public static void メソッド名(String item, int price) {
    System.out.println(item + "は" + price + "円です");
}

class main {
    public sstatic void main(String[] args) {
      printPrice("ハンバーガー",1200);
      printPrice("コーラ",300);
    }
　　　　　　　　public static void printPrice(String item, int price) {
      System.out.println(item + "は" + price + "円です");
    }
}

出力結果
ハンバーガーは1200円です
コーラは300円です
~~~
## 戻り値のあるメソッド
- メソッド内でreturnを使うと、returnの値をメソッドの呼び出し元に返すことができる
- 戻り値のデータ型を指定
- 定型だった`public static void`の`void`の部分に指定する
~~~
public static 戻り値のデータ型 メソッド名（引数） {
    return 戻り値;
}

例
public static int add（int a, int b） {
    return a + b;
}

具体例
public static void main(String[] args) {
    int total = add(7,5);
    System.out.println(total);
}
public static int add(int a, int b) {
    return a + b;
}
出力結果
12
~~~
### void
- `void`は戻り値がないという意味
### メソッドのオーバーロード
- 同じメソッド名は使えないが、引数の方や個数が違う場合は同名のメソッドを定義できる。これをオーバーロードと言う。
~~~
class Main {
  public static void main(String[] args) {
    printData(fullName("Tanaka", "Tarou"), 27);
    
    // fullNameメソッドを用いて、printDataの引数を書き換えてください
    printData(fullName("Ayajyou", "Porin", "Nakami"), 24);
  }

  public static void printData(String name, int age) {
    System.out.println("私の名前は" + name + "です");
    System.out.println("年齢は" + age + "歳です");
  }

  public static String fullName(String firstName, String lastName) {
    return firstName + " " + lastName;
  }
  
  // fullNameメソッドを定義してください
  public static String fullName(String firstName, String middleName, String lastName) {
    return firstName + " " + middleName + " " + lastName;
  }
  
}
~~~
##　クラス
- メソッドという小さな部品をまとめる、大きな部品のイメージ
- 他のクラスのメソッドを利用することも可能
- クラス名とファイル名は同名かつ最初は大文字
- 実行用のクラスとロジックをまとめるクラスで役割分担
~~~
クラスの呼び出し例
Main.java
class Main {
  public static void main(String[] args) {
    Person.hello();
 }
}

Person.java
class Person {
  public static void hello() {
    System.out.println("Hello World");
 }
}
~~~
### 外部ライブラリ
- Javaでは他人が作ったクラスを利用することができ、これを外部ライブラリという
- importを用いて使用することができる
- よく使われるライブラリはimportの記述を省ける（例えばMathクラス）
~~~
例：Mathというクラス（ライブラリ）を読み込むには
improt java.lang.Math;

class Main {
  public static void main(String[] args) {
  ・
　　　　・
　　　　・
 }
}
~~~
### Scanner
- コンソールに入力した値を受け取るライブラリ
- `import java.util.Scanner`と記述する
~~~
import java.util.Scanner;
class Main {
  public static void main(String[] args) {
    Scanner scanner = new Scanner(System.in);

    String name = scanner.next();
  }
}

'new Scanner(System.in);'でScannerの初期化
`scanner.next();`で文字列の入力を受け取る

例：
// java.util.Scannerを読み込んでください
import java.util.Scanner;

class Main {
  public static void main (String[] args) {
    Scanner scanner = new Scanner(System.in);
    
    System.out.print("お名前： ");
    
    // 変数nameを定義し、コンソールから文字列を受け取って代入してください
    String name = scanner.next();
    
    // 「こんにちは◯◯さん」と出力してください
    System.out.println(name + "さんこんにちは");
  }
}
~~~
##オブジェクト指向
- 人間が楽にプログラムを組み立てるための工夫
- オブジェクト（もの）を中心にしたという意味
### クラスとインスタンス
- クラスとインスタンスオブジェクト指向で大事
- インスタンスとはオブジェクトの別名
- クラスはインスタンスの設計図なので、インスタンスはクラスという設計図をもとに作られる
- インスタンスは情報と振る舞いを持つ
- 情報をインスタンスフィールド、振る舞いをインスタンスメソッドと呼ぶ
