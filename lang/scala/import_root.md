ScalaのimportはJavaと違ってscalaファイルと同じ階層のフォルダをトップレベルとして扱える。

```
+ src
  + main
    + scala
	  + foo
	    + Foo.scala
		+ bar
		  + Bar.scala
```

たとえばこのようなフォルダ構成で`Foo.scala`が`Bar.scala`をimportするときに

```
import foo.bar.Bar
```

ではなく、

```
import bar.Bar
```

でimportできる。
ここでパッケージが`bar`で始まる外部ライブラリをimportしたくても同じプロジェクトのパッケージが優先されるので参照することができない。
そのような場合はトップレベルを表す`_root_`と組み合わせて

```
import _root_.bar._
```

とすることでimportすることができる。

