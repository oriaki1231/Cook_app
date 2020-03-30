
# Name

### Cook app 〜料理を楽しむ全ての人に〜

Cook appは誰でも簡単にレシピをシェアできるレシピサイトです

# Overview

ユーザー登録制のレシピ共有サイト
登録すればいつでもどこでも全てのレシピを閲覧できます。
![83761e05a5366bde1a05ae09aeebd5ad](https://user-images.githubusercontent.com/60604379/77889150-630ba080-72a8-11ea-8833-ba99863f7ab9.gif)

 
# DEMO
 
- 新規登録
![f67ecf5a0bbe438848d07f50eabdb7d8](https://user-images.githubusercontent.com/60604379/77890034-c4803f00-72a9-11ea-9a2e-7724a3829b84.gif)

- レシピ投稿
![c8c32544e0a6df76657ec3fb7db76c77](https://user-images.githubusercontent.com/60604379/77890369-525c2a00-72aa-11ea-8052-3344c34bf0e2.gif)

 
# Features
 
"hoge"のセールスポイントや差別化などを説明する
 
# Requirement
 
"hoge"を動かすのに必要なライブラリなどを列挙する
 
* huga 3.5.2
* hogehuga 1.0.2
 
# Installation
 
Requirementで列挙したライブラリなどのインストール方法を説明する
 
```bash
pip install huga_package
```
 
# How to use
 
DEMOの実行方法など、"hoge"の基本的な使い方を説明する
 
```bash
git clone https://github.com/hoge/~
cd examples
python demo.py
```
 
# Note
 
注意点などがあれば書く

# DB

## usersテーブル
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


## recipesテーブル
|Column|Type|Options|
|------|----|-------|
| title     | string  | null: false|
| body      | text    | null: false|
| image_id  | string  | null: false|
| user_id   | integer | null: false|

### Association
- belongs_to :user
- attachment :image
 
