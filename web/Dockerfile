FROM node:14.7.0

# (1) プロキシ設定
ENV http_proxy 'http://gwproxy.daikin.co.jp:3128'
ENV https_proxy 'http://gwproxy.daikin.co.jp:3128'
ENV no_proxy '127.0.0.1,localhost'

# (2) パッケージアップデート
RUN apt-get update

# (3) NUXTソースファイルコピー
WORKDIR /webapp
COPY webapp /webapp

# (4) ライブラリを取得しビルド
RUN npm install
RUN npm run build

ENV HOST 0.0.0.0

CMD ["npm", "run", "start"]

EXPOSE 3000
