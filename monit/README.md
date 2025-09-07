[Monit](https://mmonit.com/monit/)のサンプルコード

## 使い方

```shell
# イメージのビルド
docker build -t monit-apache-demo .

# コンテナの起動
# ポート`8888`でApache
# ポート`8889`でMonit
docker run -d \
  --name monit-test \
  -p 8888:80 \
  -p 8889:2812 \
  monit-apache-demo

# Apache再起動のデモ
# 終了前の確認
docker exec monit-test monit status
# Apache終了
docker exec monit-test pkill apache2
# MonitがApacheを再起動したことの確認（Apache終了後90秒くらい待機してから実行）
docker exec monit-test monit status
```
