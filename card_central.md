# **Card In CLass Rails Application**

## **Day 1**

```ruby
-----------------------------------------
rails new card_central -d postgresql -T
bundle
yarn install --check-files
rails db:create
push to github
place rspec into gemfiles
bundle
rails g rspec:install
bundle exec rspec
gem install rspec
start new branch "listings"
rails g scaffold Listing title:string description:text price:integer sold:boolean
rails db:migrate
heroku login
heroku create name
git push heroku main
merge branch with main
push to github
heroku run rails db:migrate
-----------------------------------------
```

## **Day 2**

```ruby
-----------------------------------------
# root route
root "listing#index"
# root is short for root to:
# Bootstrap:
new branch
gem 'bootstrap', '~> 5.0.0.beta1' ==> gemfile
bundle install
application.css -> application.scss
add @import "bootstrap";
keep both require
gem 'jquery-rails' ==> gemfile
bundle install
# add:
# //= require jquery3
# //= require popper
# //= require bootstrap-sprockets
# ==> application.js
# add <meta name="viewport" content="width=device-width, initial-scale=1"> ==> application.html.erb
# create shared folder in views, _navbar.html.erb
require render 'shared/navbar'

# run Heroku for catch up
# New branch devise
# Devise
# omnivise
gem file ==> gem 'devise'
bundle install
rails generate devise:install
in config/environments/development.rb:
===> config.action_mailer.default_url_options = { host: 'localhost', port: 3000 }
===> application.html.erb
<p class="notice"><%= notice %></p>
<p class="alert"><%= alert %></p>
rails g devise:views
rails g devise User
migration => create_table :users
t.string :name, null: false, default: ""
rails db:migrate
# helper methods
# if user_signed_in?
heroku run rails db:migrate




-----------------------------------------
```
