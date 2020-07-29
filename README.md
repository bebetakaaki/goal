# README

・アプリ名
　goal

・概要
　アパレル個人販売能力を向上する事が出来ます。

・制作背景(意図)
　自店舗の売り上げを伸ばしたいと思いこの個人アプリを作成しました。売り上げを伸ばすには販売員の販売能力を伸ばす必要があります。販売能力を伸ばすには出勤から退勤までの振り返りが必要だと実感しています。なぜなら、私が毎日接客した中でお客様に響いたワード、商品提案のタイミング、動向、先輩方の接客で自分にも出来る事を毎日ノートにメモをしていました。すると学生なので出勤回数が半分でしたが月間販売ランキングで１００人中４５位になる事が出来ました。新卒で就職した時も同じ様に続けて結果を残せたので、毎日の振り返りが出来るアプリケーションを作成したいと言う背景があり作成しました。
 
・DEMO(gifで動画や写真を貼って、ビューのイメージを掴んでもらいます)
  トップページ
　 https://gyazo.com/6087f895c5775e757565f123f73943b5
  ログイン画面
 　https://gyazo.com/33cc33dd4295416a319f8315d1f5f36d
  
・実装予定の内容
　フォームの入力。
・DB設計
　## new_accountテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|
|password|string|null: false|
|again-password|string|null: false|
### Association
- has_many :group_create
- has_many :chat

## group_createテーブル
|Column|Type|Options|
|------|----|-------|
|group_name|integer|null: false|
|chat_member|integer|null: false, foreign_key: true|
|new_account_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :new_account
- has_many :chat

## chatテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|new_account_id|integer|null: false, foreign_key: true|
|group_create_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :new_account
- belongs_to :group_create
