```mermaid
---
title: "shoseki"
---
erDiagram
  booksBd ||--|| books
  books ||--o{ reviews :""
  booksBd{
    int id PK "auto_increment"
    varchar(30) isbn
  }
	books{
		int id PK "auto_increment"
		int isbn "ISBN。9桁か11桁の数字"
		varchar(30) title "書籍名"
		varchar(30) publisher "出版社"
		varchar(30) author "作者名"
		int price "価格"
		}
	reviews{
		int id PK "auto_increment"
		int book_id FK "外部キー。booksテーブルの主キー。"
		varchar(30) user_name "社員名"
		varchar(200) comment "レビュー"
		int score "0～で評価"
	}
```