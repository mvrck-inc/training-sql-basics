## この課題で身につく能力

PlayGround, REPL, IDEで素早くScalaソースコードを書き実行できる

## 課題

以下の課題の結果をこのファイルに貼り付けて、Pull Requestを送る形で提出してください

---
1. オンラインの[Playground](https://www.db-fiddle.com/)で以下のSQLを実行し、結果を貼り付けて下さい。

```sql
CREATE TABLE first_table (
  `name` VARCHAR(255) NOT NULL,
  `age`INT NOT NULL
);


INSERT INTO first_table (name, age) VALUES ("Richard Imaoka", 18);
```

```sql
SELECT * FROM first_table;
```

解答) 以下のようになります。左側と右側に画面が別れていて、左側にDDL/DML (= CREATE TABLE, INSERT INTO)、右側にクエリ(SELECT)を入れることに注意して下さい。

![image](https://user-images.githubusercontent.com/7414320/76934997-9c045680-6933-11ea-8a3b-d50d787db129.png)


---
2. 自分のローカルPCにMySQL 5.7をインストールして下さい。

解答) 結構面倒ですね。まず、自分のMacBookにhomebrewが入っていなかったら https://brew.sh/ からインストールして下さい。
MacBookを前提に説明するので、Windows機やLinux機を使う場合別途相談して下さい。

`brew install mysql@5.7`でMySQL 5.7がインストールできます。最新バージョンは8.0.xなのですが、Amazon側の制約などもあり、5.7をインストールすることにします。

https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/AuroraMySQL.Updates.html
> All 1.x Aurora MySQL engine versions are wire-compatible with Community MySQL 5.6.10a. All 2.x Aurora MySQL engine versions are wire-compatible with Community MySQL 5.7.12.

brew installではMySQLのコマンドライン・クライアントと、DBサーバーの両方がインストールされるので確認します。

```
> which mysql
/usr/local/opt/mysql@5.7/bin/mysql
> which mysql.server
/usr/local/opt/mysql@5.7/bin/mysql.server
```

`mysql.server start` でMySQLサーバーを開始できます。

コマンドラインからログイン出来ることを確認しましょう。

```
> mysql --host=127.0.0.1 -u root -p
password:
```

↑二行目でパスワードを聞かれていますが、何も設定せず立ち上げたので、そのままEnterを押せばコマンドラインからログインできるはずです。(もしかするとパスワードが`root`になっているかもしれません)

---
3. 自分のローカルPCにMySQL WorkBenchをインストールして下さい。

解答) 
- リンクはこちら https://www.mysql.com/products/workbench/
- MySQL WorkBench以外にもMacbookなら https://www.sequelpro.com/ がおすすめです

好きな方を使いましょう。迷ったらMySQL Workbench。

`Host: 127.0.0.1, Port:3306, user=root, password=` (もしかするとパスワードが`root`になっているかもしれません)

---
4. MySQL WorkBenchから以下のSQLを実行して、結果を貼り付けて下さい。

```sql
CREATE DATABASE maverick_sql_training;

USE maverick_sql_training;

CREATE TABLE first_table (
  `name` VARCHAR(255) NOT NULL,
  `age`INT NOT NULL
);


INSERT INTO first_table (name, age) VALUES ("Richard Imaoka", 18);

SELECT * FROM first_table;
```

解答) SQLは上に載っているので省略します。提出の際は必ず自分で実行した結果を貼り付けてください。課題3.でSequel Proを選んだ人はそちらでもよいです。
