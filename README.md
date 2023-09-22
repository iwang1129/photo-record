# アプリケーション名
 photo-record
# アプリケーション概要
  旅行の記録だけでなく、子どもや植物などの成長記録もまとめられるアプリ
# URL

# テスト用アカウント

# 利用方法
# アプリケーションを作成した背景
  私はよく旅行に行き、その際に多くの写真を撮影しますが、これらの写真を整理することや後で見返すことが難しいと感じていた。
  この課題を解決するために、自分の旅行や日常の大切な瞬間を簡単に整理し、思い出を永遠に残せるアプリを開発することにした。
  また、旅行だけでなく、植物や子どもなどの成長記録も効果的に残せるアプリを作成することで、、幅広いニーズに対応できると考えた。
  

# 洗い出した要件
# https://docs.google.com/spreadsheets/d/13S0EnM5Z5TSJ4NKORHzOBlCPNMLfN2OXuiSBmPqyP5g/edit#gid=982722306

# テーブル設計

## users テーブル

| Column             | Type   | Options                  |
| ------------------ | ------ | -------------------------|
| email              | string | null: false, unique true |
| nickname           | string | null: false              |
| encrypted_password | string | null: false              |

### Association
- has_many :rooms
- has_many :messages

## rooms テーブル

| Column | Type   | Options     |
| ------ | ------ | ----------- |
| name   | string | null: false |

### Association
- belong_to :user
- has_many :messages

## messages テーブル

| Column  | Type       | Options                        |
| ------- | ---------- | ------------------------------ |
| content | text       |                                |
| user    | references | null: false, foreign_key: true |
| room    | references | null: false, foreign_key: true |

### Association

- belongs_to :room
- belongs_to :user

# 開発環境
  フロントエンド
  バックエンド
  インフラ
  テスト
  テキストエディタ
  タスク管理

