# **Rails**

## **Routes**

### **CRUD Operations**

1. GET -> Read
1. POST -> Create
1. PUT / PATCH -> Update
1. DELETE -> Delete

```ruby
get 'orders', to: 'orders#index'

get 'orders/:id", to: 'orders#show'

<!-- Root Route -->

root to: 'controller#action
<!-- GET by default -->

"$%.2f" %
```

- yeild renders all code inside the body.

```ruby
rails new scaffold_Cafe -d postgresql
rails db:create
rails db:migrate
rails g scaffold Order item:string quanity:integer
# default option =====> resources:order
```

## **Controllers**

```ruby
rails g controller projects
# create method in new controller
# Params Method
params[:id]
# Turn into string for Json
# IN PUBLIC ===> json file ===> strings not symbols

# Read class method:
def read_class
JSON.parse(File.read(Rails.public_path.join("projects.json")))
end
# Hook below:
before_action :read_class
# Make instance variable for scope!

# Cross site request forgery(CSRF)
skip_before_action :verify_authenticity_token

# Query String:

localhost:3000/projects?id=3&name=portfolio app&github_status=true


# Create Method:
def create
new_project = {id:params[:id].to_i, 
name:: params[:name], 
github_status:params[:github_status]}

# Write Projects Method:
def write_projects(projects)
File.write(Rails.public_path.join("projects.json"), JSON.generate(projects))
# Hashes ===> Strings

# Redirect_to Method:
#  check routes
rails routes -c projects
redirect_to projects_path

place certain methods under private mods

private key_word
```

## **Views**

```ruby
ERB == Embedded Ruby
# link_to method
link_to (2 attributes)
link_to project[:name], project_path(project[:id])

# Partials:
# Nav
layout file --> application.html.erb
# Entry point for all view files.
# Views -> shared folder -> _nav.html.erb
# IN applications.html.erb -->
# <%= render partial: "shared/nav %>

# Asset Pipeline:

# <%= image_tag asset_path("dog.jpg"), width:400 %>

#Css & SASS
application.css
remove require_tree (loads Css in other files)
leave require_self(loads Css in this file)
# Then create main.scss
In application.css => require_main
# @import
create folder base
and file -> global.scss
in main.scss -> @import "base/global.scss"
```

## **SQL**

```ruby
psql == shell

/l == list all databases
/dt == list tables/databases
/c == connect to database
/d == display table

Script => create table if not exists name (),


Alter Table => Documentation
# add Column
alter table items
add column price decimal not nul,
add column price not null default 0..0;
# Set price with default value if table has items already.
```

## **Models**

<!-- CRUD: -->

![Create](/images/model_create.jpeg)

![Read](/images/model_read.jpeg)

![Update](/images/model_update.jpeg)

![Delete](/images/model_delete.jpeg)

![Has_one](/images/model_has_one.jpeg)

![Has_many](/images/model_has_many.jpeg)

![Has_many_through](/images/model_has_many_through.jpeg)

![polymporphic](/images/model_polymporphic.jpeg)

![migrations](/images/model_migrations.jpeg)

```ruby
# Object-oriented fashion
rails g model Car name:string
# SINGULAR, PASCAL CASE OR SNAKE CASE
rails db:migrate

# ActiveRecord Associations:

# Has_one
rails g model supplier name:string
rails g model account balance:integer supplier:references
rails db:migrate

# ActiveRecord Migrations:

rails db:migrate -> (update database)
rails db:rollback -> (revert database)

# Schema File ----> NEVER EDIT -----> Edit it through migrates.

# Add extra columns:
rails g migration AddPriceToBooks price:integer
rails db:migrate
# Check Schema File

# Multi adds:
rails g migration AddDetailsToBooks rating:integer description:text
rails db:migrate

# Add References to other tables:
rails g migration AddAuthorRefToBooks author:references
rails db:migrate

# Removing Columns:
rails g migration RemoveRatingFromBooks rating:integer
rails db:migrate

# Validations:
validates :title, presence:true
# no_title errors.full_messages --> in rails c
validates :description, length:{minimum:10, too_short: "%{count} is the miniumum number of characters!"}
# Range:
validates :description, length:{ in: 10...100}
validates :price, numericality: {only_integer: true}
validates :price, numericality: {greater_than_or_equal_to: 0}
# Scopes:
scope :bargin, -> { where(price: 0..500)}
```

