## この課題で身につく能力

JOINで2つのテーブルを内部結合できる(内部/外部の違いと左/右結合の違いは知らなくて良い)

## 課題

以下の課題の結果をこのファイルに貼り付けて、Pull Requestを送る形で提出してください

1. 「スッキリわかるSQL入門 第2版」p.267 問題8-1のテーブル及びデータを自分で準備し、SQLの実行結果を貼り付けて下さい

解答) データの準備はこちら

```sql
CREATE TABLE A (
  A1 INT NOT NULL,
  A2 INT NOT NULL
);

CREATE TABLE B (
  B1 INT NOT NULL,
  B2 INT
);

INSERT INTO A (A1, A2) VALUES (1,3);
INSERT INTO A (A1, A2) VALUES (2,4);

INSERT INTO B (B1, B2) VALUES (1,2);
INSERT INTO B (B1) VALUES (1);
```

SQLと実行結果は書籍に載っているので省略します。提出の際は必ず自分で実行した結果を貼り付けてください。

---
2. 「スッキリわかるSQL入門 第2版」p.267 問題8-2のテーブル及びデータを自分で準備し、SQLの実行結果を貼り付けて下さい

解答) データの準備はこちら

```sql
CREATE TABLE departments (
  A1 INT NOT NULL,
  A2 INT NOT NULL
);

CREATE TABLE bosses (
  B1 INT NOT NULL,
  B2 INT
);

CREATE TABLE employees (
  B1 INT NOT NULL,
  B2 INT
);

CREATE TABLE bosses (
  B1 INT NOT NULL,
  B2 INT
);

CREATE TABLE bosses (
  B1 INT NOT NULL,
  B2 INT
);
INSERT INTO A (A1, A2) VALUES (1,3);
INSERT INTO A (A1, A2) VALUES (2,4);

INSERT INTO B (B1, B2) VALUES (1,2);
INSERT INTO B (B1) VALUES (1);
```

SQLと実行結果は書籍に載っているので省略します。提出の際は必ず自分で実行した結果を貼り付けてください。
