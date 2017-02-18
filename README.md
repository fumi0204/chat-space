# chat-space

##Requirements

*ruby 2.3.1

*Rails 5.0.0

##Database Design

###Users table

| columm | type | not null | unique | index |
|:-----------|------------:|:------------:|:------------:|:------------:|
| name | string | true | true | true |
| password | string | true | false | false |

Association: has_many :groups, has_many : messages

###Groups table

| columm | type | not null | unique | index |
|:-----------|------------:|:------------:|:------------:|:------------:|
| name | string | true | true | true |

Association: has_many :users , has_many : messages

###Group_user table

| columm | type | not null | unique | index |
|:-----------|------------:|:------------:|:------------:|:------------:|
| group_id | integer | true | false | true |
| user_id | integer | true | false | true |

Association: belongs_to :users , belongs_to : groups

###Messages table

| columm | type | not null | unique | index |
|:-----------|------------:|:------------:|:------------:|:------------:|
| body | text | true | false | false |
| image | string | false | false | false |
| group_id | integer | true | true | true |
| user_id | integer | true | true | true |

Association: belongs_to : users, belongs_to :groups


