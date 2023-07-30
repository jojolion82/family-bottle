users テーブル
カラム名	データ型	制約
id	INTEGER	PRIMARY KEY, AUTO_INCREMENT
name	VARCHAR(255)	NOT NULL
email	VARCHAR(255)	NOT NULL, UNIQUE
password	VARCHAR(255)	NOT NULL
created_at	DATETIME	NOT NULL
updated_at	DATETIME	NOT NULL
family_groups テーブル
カラム名	データ型	制約
id	INTEGER	PRIMARY KEY, AUTO_INCREMENT
name	VARCHAR(255)	NOT NULL
created_at	DATETIME	NOT NULL
updated_at	DATETIME	NOT NULL
family_members テーブル
カラム名	データ型	制約
id	INTEGER	PRIMARY KEY, AUTO_INCREMENT
user_id	INTEGER	NOT NULL, FOREIGN KEY (users.id)
family_group_id	INTEGER	NOT NULL, FOREIGN KEY (family_groups.id)
created_at	DATETIME	NOT NULL
updated_at	DATETIME	NOT NULL
bottles テーブル
カラム名	データ型	制約
id	INTEGER	PRIMARY KEY, AUTO_INCREMENT
content	TEXT	NOT NULL
theme	VARCHAR(255)	
sender_id	INTEGER	NOT NULL, FOREIGN KEY (users.id)
receiver_id	INTEGER	NOT NULL, FOREIGN KEY (users.id)
created_at	DATETIME	NOT NULL
updated_at	DATETIME	NOT NULL
comments テーブル
カラム名	データ型	制約
id	INTEGER	PRIMARY KEY, AUTO_INCREMENT
content	TEXT	NOT NULL
bottle_id	INTEGER	NOT NULL, FOREIGN KEY (bottles.id)
user_id	INTEGER	NOT NULL, FOREIGN KEY (users.id)
created_at	DATETIME	NOT NULL
updated_at	DATETIME	NOT NULL