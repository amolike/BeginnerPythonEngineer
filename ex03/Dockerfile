FROM ubuntu:20.04
# nginxのインストール
RUN apt-get update && apt-get install -y \
    nginx \
    tzdata \
 && rm -rf /var/lib/apt/lists/*
# タイムゾーンを設定する環境変数
ENV TZ=Asia/Tokyo
# ポートの設定
EXPOSE 80
# ファイルのコピー
COPY src/index.html /var/www/html/
# nginxの起動
CMD ["nginx","-g","daemon off;"]
