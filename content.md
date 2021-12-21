# [勉強会] 実践形式でwebサービスを立ち上げてみよう
## サーバーを新規作成しよう
```
https://dashboard.codeanywhere.com/containers  
New Container → ruby
```

## CUIでターミナルを操作してみよう
CUIとは、文字入力によってコンピューターを扱う操作方式のこと。対義語はGUIで、こちらは画面に表示されている要素をマウスやキーボードなどで操作することでコンピューターを扱う。

```
whoami
pwd
ls -l
touch test.txt
ls -l

cat test.txt
echo "hello" >> test.txt
cat test.txt
```

## Railsの新しいプロジェクトを追加しよう
Ruby on Railsは、簡単なコマンドを叩くだけで新しいプロジェクトのひな型が作成される。

```
ruby -v
rails -v

rails new demo_app
cd demo_app

bundle update
bundle install

rails s

config.hosts << "port-3000-xxxxxxxxx.preview.codeanywhere.com"
```

## ユーザーのデータを扱えるようにしてみよう
```
rails generate scaffold User name:string age:integer

bundle exec rake db:migrate

rails s

https://port-3000-xxxxx.preview.codeanywhere.com/users
```

## アプリケーションのプログラムを書き換えて、仕様変更をしてみよう

### アルファベット順にユーザーを並べ替える
```
order(name: :asc)
```

### パラメーターとして受け渡した文字列で検索できるようにする
```
where("name LIKE '%#{params[:name]}%'")
注) 本当は危険な書き方です。
```

### 最大表示件数を５件にする
```
limit(5)
```
