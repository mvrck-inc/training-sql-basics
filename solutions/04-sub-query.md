## この課題で身につく能力

副問合せを活用できる

## 課題

以下の課題の結果をこのファイルに貼り付けて、Pull Requestを送る形で提出してください

1. 「スッキリわかるSQL入門 第2版」p.230 問題7-2の実行結果を貼り付けて下さい

解答)

料金テーブル(prices)とレンタルテーブル(rental_cars)をCREATEするSQL(DDL)はこちらです。
PlayGroundであるDB Fiddleは外部キー(`FOREIGN KEY`)に対応していないので、ローカルでは知らせているMySQLでテーブルを作成すると良いでしょう。

```sql
CREATE TABLE prices (
  `car_code` CHAR(3) NOT NULL,     -- 車種コード
  `car_name` VARCHAR(20) NOT NULL, -- 車種名
  `price`    INT NOT NULL,         -- 値段
  PRIMARY KEY(`car_code`)          -- プライマリーキー
) CHARACTER SET utf8mb4;           -- MySQL 5.7だと、utf8mb4でないと日本語を正しく扱ってくれません

CREATE TABLE rental_cars (
  `rental_id`   CHAR(4) NOT NULL, -- レンタルID
  `car_code`    CHAR(3) NOT NULL, -- 車種コード
  `duration`    INT NOT NULL,     -- レンタル期間
  FOREIGN KEY fk_car_code (`car_code`) references prices(`car_code`)
);
```

データを挿入するSQL(DML)はこちら。

```sql
INSERT INTO prices (car_code, car_name, price) VALUES ('S01', '軽自動車',     5250);
INSERT INTO prices (car_code, car_name, price) VALUES ('S02', 'ハッチバック', 5775);
INSERT INTO prices (car_code, car_name, price) VALUES ('S03', 'セダン',       8400);
INSERT INTO prices (car_code, car_name, price) VALUES ('E01', 'エコカー',     8400);
INSERT INTO prices (car_code, car_name, price) VALUES ('E02', 'エコカーS',    8715);

INSERT INTO rental_cars (rental_id, car_code, duration) VALUES ('1001', 'S02', 1);
INSERT INTO rental_cars (rental_id, car_code, duration) VALUES ('1002', 'S01', 3);
INSERT INTO rental_cars (rental_id, car_code, duration) VALUES ('1201', 'E01', 2);
INSERT INTO rental_cars (rental_id, car_code, duration) VALUES ('1202', 'S02', 5);
INSERT INTO rental_cars (rental_id, car_code, duration) VALUES ('1510', 'E01', 1);
```

答えのSQLクエリは書籍に載っているので省略します。提出の際は必ず自分で実行した結果を貼り付けてください。

---

2. 「スッキリわかるSQL入門 第2版」p.231 問題7-3のSQL文および実行結果を貼り付けて下さい

解答)
個体識別テーブル(cows)と頭数集計テーブル(stats)をCREATEするSQL(DDL)はこちらです。
PlayGroundであるDB Fiddleは外部キー(`FOREIGN KEY`)に対応していないので、ローカルでは知らせているMySQLでテーブルを作成すると良いでしょう。

```sql
CREATE TABLE cows (
  `id`            CHAR(4) NOT NULL,     -- 個体識別番号
  `birth_date`    DATE NOT NULL,        -- 出生日
  `gender`        CHAR(1) NOT NULL,     -- 雌雄コード、genderでいいのか？w
  `mother_id`     CHAR(4) NOT NULL,     -- 母牛番号
  `category_code` CHAR(2) NOT NULL,     -- 品種コード
  `prefecture`    VARCHAR(10) NOT NULL, -- 飼育県
  PRIMARY KEY(`id`)                     -- プライマリーキー
) CHARACTER SET utf8mb4;                -- MySQL 5.7だと、utf8mb4でないと日本語を正しく扱ってくれません

CREATE TABLE cow_stats (
  `prefecture` VARCHAR(10) NOT NULL, -- 飼育県
  `count`      INT NOT NULL,         -- 頭数
) CHARACTER SET utf8mb4;             -- MySQL 5.7だと、utf8mb4でないと日本語を正しく扱ってくれません
```

データを挿入するSQL(DML)はこちら。

```sql
INSERT INTO cows (id, birth_date, gender, mother_id, category_code, prefecture) VALUES ('A101', '2019-01-01', '1', 'A001', '01', '北海道');
INSERT INTO cows (id, birth_date, gender, mother_id, category_code, prefecture) VALUES ('A201', '2019-01-02', '2', 'A001', '02', '北海道');
INSERT INTO cows (id, birth_date, gender, mother_id, category_code, prefecture) VALUES ('A301', '2019-01-03', '1', 'B003', '03', '北海道');
INSERT INTO cows (id, birth_date, gender, mother_id, category_code, prefecture) VALUES ('B111', '2019-01-04', '2', 'B008', '01', '北海道');
INSERT INTO cows (id, birth_date, gender, mother_id, category_code, prefecture) VALUES ('C101', '2019-01-05', '1', 'C009', '02', '鹿児島');
INSERT INTO cows (id, birth_date, gender, mother_id, category_code, prefecture) VALUES ('C121', '2019-01-06', '2', 'C008', '02', '鹿児島');
INSERT INTO cows (id, birth_date, gender, mother_id, category_code, prefecture) VALUES ('C111', '2019-01-07', '1', 'C007', '02', '鹿児島');
INSERT INTO cows (id, birth_date, gender, mother_id, category_code, prefecture) VALUES ('D101', '2019-01-08', '1', 'D001', '02', '宮崎');
INSERT INTO cows (id, birth_date, gender, mother_id, category_code, prefecture) VALUES ('D121', '2019-01-09', '2', 'D002', '02', '宮崎');
INSERT INTO cows (id, birth_date, gender, mother_id, category_code, prefecture) VALUES ('D131', '2019-01-11', '1', 'D004', '02', '宮城');
INSERT INTO cows (id, birth_date, gender, mother_id, category_code, prefecture) VALUES ('F101', '2019-01-12', '2', 'F001', '01', '宮城');
INSERT INTO cows (id, birth_date, gender, mother_id, category_code, prefecture) VALUES ('G101', '2019-01-13', '2', 'G001', '02', '秋田');

INSERT INTO cow_stats (prefecture, count) VALUES ('北海道', 512000);
INSERT INTO cow_stats (prefecture, count) VALUES ('鹿児島', 343000);
INSERT INTO cow_stats (prefecture, count) VALUES ('宮崎',   250000);
INSERT INTO cow_stats (prefecture, count) VALUES ('宮城',    83000);
INSERT INTO cow_stats (prefecture, count) VALUES ('秋田',    19000);
```

答えのSQLクエリは書籍に載っているので省略します。提出の際は必ず自分で実行した結果を貼り付けてください。
