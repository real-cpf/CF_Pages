---
sidebar: auto
---
# Ruby On Rails Demo

## new rails project
+ ruby
+ sqlite3
+ gem
+ rails
+ rail new demo
+ bin/rails server
## hello word
+ 修改route配置
  ```ruby
  Rails.application.routes.draw do
    # 配置首页
    root "articles#index"
    # 配置articles路由
    get "/articles", to: "articles#index"
    # 这里指向了 bin/rails generate controller Articles index --skip-routes 生成的页面
  end
  ```

## curd
+ db & orm
  + model `bin/rails generate model Article title:string body:text`
  + migrate `bin/rails db:migrate`
  + CRUD
    + `article = Article.new(title: "Hello Rails", body: "I am on Rails!")` / `article.save`
    + `Article.find(1)`
    + `Article.all`
    + `@article.update(article_params)`
+ resources route
  ```ruby
  resources :articles do
    resources :comments
  end
  ```
