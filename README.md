# README


## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, index: true|
|e-mail|string|null: false, foreign_key: false, unique: true|
|password|string|null: false|

###Assosiation
- has_many :messages
- has_many :groups, through :members
- has_many :member


## membersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|


###Association
- belongs_to :group
- belongs_to :user


## groupテーブル

|Column|Type|Options|
|------|----|-------|
|group_name|string|null :false|

### Assosiation
- has_many :users, through :members
- has_many :messages
- has_many :members


## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text||
|image|string||
|user_id|integer|null :false, foreign_key :true|
|group_id|integer|null :false, foreign_key :true|

### Assosiation
- belongs_to :group
- belongs_to :member
