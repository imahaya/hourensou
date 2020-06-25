# アプリケーション名
hourensou

## トップページ
[![トップページ](https://i.gyazo.com/40d0e20d923780b41a3c5f6c78196da3.png)](https://gyazo.com/40d0e20d923780b41a3c5f6c78196da3)

# 制作背景(意図)
突然ですが、あなたに質問です。あなたは仕事をする時、1日の数多くあるタスクの中でどれから手をつけて良いのか分からなくなってしまったり、仕事中に連絡したい事があっても、相手がその場に居なかったりした経験はありませんか？ 特に私は、前職でどのタスクから手をつけて良いのか分からなくなってしまうことが多く、1日の始めに今日やるべきタスクを紙にまとめてから仕事をしていました。その日のタスクを洗い出してから仕事に取り掛かる事は、頭の中で整理が出来て良いと思ったのですが、紙にまとめる事で、無くしてしまう事が多く、管理がしにくかったです。私は、このような経験をもとに、ToDoリストの作成や報告、連絡、相談が出来るアプリを作りたいと思ったのがきっかけです。

# 本番環境
## デプロイ先
herokuによるデプロイ
https://morning-headland-97173.herokuapp.com/
##テストアカウント&ID
ニックネーム  test
Eメールアドレス  test@test
パスワード  123456

# アプリケーション概要
このアプリケーションは企業で主に複数人でコミュニケーションを通して仕事をしていくという方々に使って頂きたいと思い作成しました。
出来る事としては、ToDoリストの作成や報告・連絡・相談と言った内容の投稿が出来ます。他のユーザーの投稿も閲覧が出来て、ToDoリストであればお互いにタスクの進捗具合を確認し、仕事の分担をする事も可能です。
他にも自分の投稿した内容は編集・削除が出来、各ユーザーの投稿した内容を一覧表示する事が出来ます。

# 機能一覧
●ユーザー登録、ログイン、ログアウト機能

●ToDoリスト、報告、連絡、相談の投稿機能

●投稿内容の編集、削除機能

## 投稿ページ
[![投稿ページ](https://i.gyazo.com/9c35f652fb7ac26ae652cae253096f77.png)](https://gyazo.com/9c35f652fb7ac26ae652cae253096f77)

## 編集、削除ページ
[![編集、削除ページ](https://i.gyazo.com/683c68193e2cdf44b3567a2bd7d2820a.png)](https://gyazo.com/683c68193e2cdf44b3567a2bd7d2820a)

# 工夫したポイント
投稿する際、タイトルや投稿内容が空だった場合トップページに表示されないようにバリデーションを設定しました。
本人が投稿した内容のみ編集、削除が出来るようにしました。
アプリ名がhourensouなので背景画像にほうれん草を沢山貼り付けました。

# 使用技術(開発環境)
## 開発言語
Rails 5.2.3
## データベース
MySQL2 0.5.3

# 課題、今後実装したい機能
課題としては、開発期間が短い中、DB設計や各ページのビューをどのようにするかなどの事前準備が甘く開発に苦労しました。ですので、これからアプリ開発する時は、事前準備をしっかり整えてから開発に取り掛かろうと思います。
今後実装したい機能は以下の通りです。

●ユーザー新規登録、ログインページのビューがまだ完成出来ていないので見た目を整えたい

●ユーザー登録をする際にアイコンを設定出来るようにする。誰が投稿しているのか出来るだけ一目で分かるようにしたい(現状トップページにある□の部分にアイコンを設置する予定)

●メッセージ送信機能(メッセージだけでなく画像も送信出来るようにしたい)

●自動更新機能

●ajaxを使用した非同期処理

# hourensou DB設計
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false, unique|
|password|string|null: false, unique|
|nickname|string|null: false, unique, index: true|
### Association
- has_many :posts

## postsテーブル
|Column|Type|Options|
|------|----|-------|
|title|string|null: false|
|content|text|null: false|
### Association
- belongs_to :user
