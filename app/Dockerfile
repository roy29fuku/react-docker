# https://hub.docker.com/_/node からイメージを取得
# node:<version>-alpine:<version>とすることでalpineベースの軽量イメージを取得できる
FROM node:16.13.0-alpine3.12

# 作業スペースに移動（ymlで定義したホストのappをマウントした場所）
WORKDIR /usr/src/app

# Ubuntuで発生するpermission deniedの回避
RUN mkdir -p ./node_modules
RUN chown node:node ./node_modules

# ライブラリをインストール
COPY ./package.json .
COPY ./package-lock.json .
RUN npm install


# アプリケーションを起動
CMD ["npm", "start"]
