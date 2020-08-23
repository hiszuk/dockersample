FROM mysql:5.7

# (1) プロキシ設定
ENV http_proxy 'http://gwproxy.daikin.co.jp:3128'
ENV https_proxy 'http://gwproxy.daikin.co.jp:3128'
ENV no_proxy '127.0.0.1,localhost'

# (2) パッケージアップデート
RUN apt-get update

# (3) スクリプトと各種設定ファイルのコピー
COPY etc/mysql/mysql.conf.d/mysqld.cnf /etc/mysql/mysql.conf.d/
COPY etc/mysql/conf.d/mysql.cnf /etc/mysql/conf.d/
COPY prepare.sh /usr/local/bin/
COPY init-data.sh /usr/local/bin/
COPY sql /sql

# (4) mysqldの実行
CMD ["mysqld"]
