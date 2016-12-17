docker-composeでDBの起動完了を待ってWebアプリを実行したい場合、以下の解説のようにWebアプリ側でDBの生存チェックを行う。
docker-composeのdepends_onは起動順序は制御できるものの、依存するコンテナの起動完了を待つことができないからである。

* [Controlling startup order in Compose](https://docs.docker.com/compose/startup-order/)
