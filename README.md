## DB設計

## usersテーブル
|  Column   |  Type    |  Options                |
|  ------   |  ------  |  ---------------------  |
|  name     |  string  |  null: false            |
|  email    |  string  |  null: false            |
|  password |  string  |  null: false            |
|  sex      |  integer |  null: false            |
|  age      |  integer |  null: false            |
|  remark   |  text    |  null: false            |

## Association
- has_many :posts
- has_many :comments



##  postsテーブル
|  Column   |  Type      |  Options                       |
|  -------- |  ------    |  --------------------          |
|  name     |  string    |  null: false                   |
|  title    |  string    |  null: false                   |
|  area     |  integer   |  null: false                   |
|  genre    |  integer   |  null: false                   |
|  date     |  string    |  null: false                   |
|  address  |  string    |  null: false                   | 
|  url      |  string    |  null: false                   |
|  remark   |  text      |  null: false                   |
|  user     |  references| null: false, foreign_key: true |

## Association
- belongs_to :user
- has_many :comments
- has_many :images


## commentsテーブル
|  Column   |  Type    |  Options                |
|  ------   |  ------  |  ---------------------  |
|  user_id  |  string  |  null: false            |
|  post_id  |  string  |  null: false            |
|  text     |  text    |  null: false            |

## Association
- belongs_to :user
- belongs_to :post


## imagesテーブル
|  Column   |  Type        |  Options                        |
|  ------   |  ------      |  -----------------------------  |
|  url      |  string      |  null: false                    |
|  post_id  |  references  |  null: false, foreign_key: true |

## Association
- belongs_to :post

