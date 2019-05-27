# README


## usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, unique: true|
|name|strings|null: false|
|e-mail|string|null: false, foreign_key: false, unique: true|
|password|string|null: false|

###Assosiation
- has_many :messages, through :groups_messages
- has_many :groups
- has_many :members
- belongs_to :group


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
|group_id|integer|null :false|
|group_name|strings|null :false|
|name|strings|null :false, foreign_key :true|
|user_id|integer|null :false, foreign_key :true|

### Assosiation
- has_many :users
- has_many :messages

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|null :false|
|image|strings|null :true|
|user_id|integer|null :false, foreign_key :true|
|group_id|integer|null :false, foreign_key :true|

### Assosiation
- belongs_to :group
- belongs_to :member
