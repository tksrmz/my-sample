[Monit](https://mmonit.com/monit/)のサンプルコード

## 使い方

```console
# イメージのビルド
$ docker build -t monit-apache-demo .

# コンテナの起動
# ポート`8888`でApache
# ポート`8889`でMonit
$ docker run -d \
  --name monit-test \
  -p 8888:80 \
  -p 8889:2812 \
  monit-apache-demo

# Apacheを終了させると、Monitが再起動する
$ docker exec monit-test pkill apache2
```
