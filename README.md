## users テーブル

| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| name     | string | NOT NULL    |
| email    | string | NOT NULL    |
| password | string | NOT NULL    |
| profile  | text   | NOT NULL    |
|occupation| text   | NOT NUlL    |
| position | text   | NOT NULL    |

##Association
has_many :prototypes
has_many :comments


## prototypes テーブル

| Column | Type   | Options     |
| ------ | ------ | ----------- |
| title  | string | NOT NULL    |
| catch_copy |text| NOT NULL    |
|concept | text | NOT NULL      |
| image  |ActiveStorageで実装|
| user   | references |

##Association
belong_to :user
has_many :comments

## comments テーブル

| Column   | Type   | Options     |
|----------|--------|-------------|
| text     | text   | NOT NULL    |
| user     | references |
| prototype| references |

##Association
belong_to :prototype
belong_to :user
