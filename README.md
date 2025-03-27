# docker-compose-test

docker compose のチュートリアル
[Quickstart | Docker Docs](https://docs.docker.com/compose/gettingstarted/)
をやってみた。

## ざっくりした使い方

```sh
docker compose up
```

で <http://127.0.0.1:8000> を Web ブラウザで開く。
リロードしてみる。カウントが増える。
CTRL+C で止める。

```sh
docker compose up -d
```

でデーモンモード。

```sh
docker compose down
```

で終了。

### watch

ホットリロードみたいなやつ。
docker と fastapi の dev モードの組み合わせで動いてるらしい。

```sh
docker compose watch
# または
docker compose up --watch
```

で app.py を編集して保存する。リロードする。

## メモ

`docker compose up` は compose.yml と include している.yml の変更しか見ないので、
ソース(この場合`app.py`)を変更したら

```sh
docker compose up --build
```

でイメージを作り直すこと。
