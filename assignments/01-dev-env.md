## この課題で身につく能力

PlayGround, REPL, IDEで素早くScalaソースコードを書き実行できる

## 課題

以下の課題の結果をこのファイルに貼り付けて、Pull Requestを送る形で提出してください

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

2. 自分のローカルPCにMySQL 5.7をインストールして下さい。

3. 自分のローカルPCにMySQL WorkBenchをインストールして下さい。

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