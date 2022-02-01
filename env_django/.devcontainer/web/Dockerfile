FROM python:3.9-slim
# パッケージインストール
RUN apt-get update && apt-get install -y \
    tzdata \
 && rm -rf /var/lib/apt/lists/*

# モジュールインストール
WORKDIR /tmp/work
COPY requirements.txt ${PWD}
RUN pip install -r requirements.txt

#環境変数の定義
ENV TZ=Asia/Tokyo
ENV USER user1

#一般権限のユーザ追加
RUN useradd -m ${USER} --uid 1000
RUN gpasswd -a ${USER} sudo
RUN echo "${USER}:passwd" | chpasswd

#ユーザ切り替え
USER ${USER}

