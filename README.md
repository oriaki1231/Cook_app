
# Name

### Cook app 〜料理を楽しむ全ての人に〜

# Overview

Cook appは誰でも簡単にレシピをシェアできるレシピサイト!  
登録すればいつでもどこでも全てのレシピを閲覧・投稿ができます。  
![83761e05a5366bde1a05ae09aeebd5ad](https://user-images.githubusercontent.com/60604379/77889150-630ba080-72a8-11ea-8833-ba99863f7ab9.gif)

# Production environment

Cook app  
URL : http://13.113.184.38/  

テストアカウント  
email : test@gmail.com  
pass : 123456
 
# Production background
 
- 自分が料理好きということもあり、手軽にレシピを共有できるサイトをゼロから作成してみたかった。  
- 最新の料理を手軽に閲覧できるようなサイトを作りたかった。

# Ingenuity

- プログラミングスクールで学んだカリキュラム外の技術の使用  
 （cssフレームワーク、画像のアップロードが簡単になるgem "refile"の利用）  
- 統一感のあるビューで見やすく、オシャレにまとめた  
- トップ画面に新着レシピの写真を載せることで常に最新の料理を閲覧できるようにした

# Environment & Technology used
 
* ruby 2.5.1  
* Rails 5.2.4.1  
  
- gem 'devise'  
- gem "refile", require: "refile/rails", github: 'manfe/refile'  
- gem "refile-mini_magick"  
- gem "bulma-rails"  
- gem 'pry-rails'  
- gem "refile-s3"  
- gem 'haml-rails'
 
# DEMO

 1.まずは新規登録をしよう  
 2.新規登録後はプロフィールやアイコンを自由にセッティング  
 3.セッティングが終わったらレシピを投稿してみよう  
 4.新着レシピはトップ画面に載るのでチェック
 
- 新規登録
![f67ecf5a0bbe438848d07f50eabdb7d8](https://user-images.githubusercontent.com/60604379/77890034-c4803f00-72a9-11ea-9a2e-7724a3829b84.gif)

- レシピ投稿
![c8c32544e0a6df76657ec3fb7db76c77](https://user-images.githubusercontent.com/60604379/77890369-525c2a00-72aa-11ea-8052-3344c34bf0e2.gif)

# To be implemented
 
- レシピのカテゴリー別登録機能
- レシピ検索機能
- お気に入り機能
- 動画投稿機能
- コメント、レビュー機能

# DB

### usersテーブル
|Column|Type|Options|
|------|----|-------|
| name               | string | null: false |
| email              | string | null: false |
| encrypted_password | string | null: false |
| profile            | text   ||
| profile_image_id   | string ||

### Association
- has_many   :recipes, dependent: :destroy
- attachment :profile_image


### recipesテーブル
|Column|Type|Options|
|------|----|-------|
| title     | string  | null: false|
| body      | text    | null: false|
| image_id  | string  | null: false|
| user_id   | integer | null: false|

### Association
- belongs_to :user
- attachment :image
 
