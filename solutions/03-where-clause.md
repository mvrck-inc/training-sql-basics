## この課題で身につく能力

=と<、>をつかったWHERE句を書ける

## 課題

以下の課題の結果をこのファイルに貼り付けて、Pull Requestを送る形で提出してください

1. 「スッキリわかるSQL入門 第2版」p.102 問題3-1のSQL文を作成して実行結果を貼り付けて下さい。

最初にテーブルを作成しますが、その際は以下のSQL(DDL)を使います。書籍では列名は日本語ですが、列名に日本語を使うことはあまりないので、英語の列名を使っています。

```sql
CREATE TABLE temparatures (
  `month`           INT NOT NULL, -- 月
  `rainfall`        INT NOT NULL, -- 降水量
  `max_temparature` INT NOT NULL, -- 最高気温
  `min_temparature` INT NOT NULL, -- 最低気温
  `humidity`        INT NOT NULL  -- 湿度
); 
```

天気のデータは以下をINSERT INTOで挿入して下さい。

| month  | raifall  | max_temparature | min_temparature | humidity |
|--------|----------|-----------------|-----------------|----------|
|  4     | 100      |  20             | 3               | 50       |
|  5     | 320      |  20             | 3               | 40       |
|  6     | 400      |  20             | 3               | 90       |
|  7     | 200      |  30             | 3               | 80       |
|  8     | 100      |  35             | 3               | 80       |


解答) 
天気データを挿入するSQL(DML)は以下になります。

```sql
INSERT INTO temparatures (month, rainfall, max_temparature, min_temparature, humidity) VALUES (4, 100, 20, 3, 50);
INSERT INTO temparatures (month, rainfall, max_temparature, min_temparature, humidity) VALUES (5, 320, 20, 3, 40);
INSERT INTO temparatures (month, rainfall, max_temparature, min_temparature, humidity) VALUES (6, 400, 20, 3, 90);
INSERT INTO temparatures (month, rainfall, max_temparature, min_temparature, humidity) VALUES (7, 200, 30, 3, 80);
INSERT INTO temparatures (month, rainfall, max_temparature, min_temparature, humidity) VALUES (8, 100, 35, 3, 80);
```

答えのSQLクエリは書籍に載っているので省略します。提出の際は必ず自分で実行した結果を貼り付けてください。

---
2. 「スッキリわかるSQL入門 第2版」p.103 問題3-2のSQL文を作成して実行結果を貼り付けて下さい。。

解答) 答えのSQLクエリは書籍に載っているので省略します。提出の際は必ず自分で実行した結果を貼り付けてください。

---
3. 「スッキリわかるSQL入門 第2版」p.103 問題3-3のSQL文を作成して実行結果を貼り付けて下さい。。

解答) 答えは書籍に載っているので省略します。提出の際は必ず自分で実行した結果を貼り付けてください。
