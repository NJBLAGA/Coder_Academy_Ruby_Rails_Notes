# Notes

## ***Term 2 Week 1***

-------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------

### **Thursday Class 14/01/21**

1. Tech Stack
1. Stack Share
1. MVC Architecture
1. Code along: Ordering drinks at the bar app applying MVC Architecture

[MVC ARTICLES]
[https://www.freecodecamp.org/news/model-view-controller-mvc-explained-through-ordering-drinks-at-the-bar-efcba6255053/a] [https://www.guru99.com/mvc-tutorial.html]

## Composition Example

```Ruby
class Movement
    def move
        puts "can move"
    end
end

class Automobile

end

#Composition creating an instance of another class within current class.
class Car < Automobile
    def initialize
        @movement = Movement.new
        @movement.move
    end
end


@car1 = Car.new 
```

### ***Rails Docs:***

[https://guides.rubyonrails.org/] ====> ***READ THROUGH THE DOCS AS WE GO THROUGH THE CONTENT IN CLASS***

[https://edstem.org/courses/4965/lessons/5832/slides/42171] ====> ***Controllers***

-------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------

## **Friday 15/01/21**

1. Rails intro (What and Why Rails)
1. Create Rails app
1. Walk through folder and file structure
1. Rails credentials and master key
1. Start a server
1. Rails routes - brief overview of http protocol and Rest Api
1. Create a get route in rails app to get a list of books
1. Controller
1. View(render)
1. Erb

### ***Helpful Links for rails credentials***

[https://www.codewithjason.com/understanding-rails-secrets-credentials/]

### ***Master Key Password:***

[https://stackoverflow.com/questions/61961858/vscode-doesnt-wait-on-command-editor-code-wait-bin-rails-credentialsedit]

In Terminal:

```ruby
EDITOR="code --wait" bin/rails credentials:edit
```

Type in master-key ruby file:

- password: xxxxxx

Save and close file.

In Terminal:

```ruby
Rails.application.credentials.config
```

To display PW:

```ruby
Rails.application.credentials.config[:password]
```

Change port

```ruby
Rails s -p 3001
```

### ***Postman:***

[https://www.postman.com/downloads/]

OR

In Terminal:

``` t
sudo snap install postman
```

### ***External Sources:***

[https://www.khanacademy.org/math]

-------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------

## ***Term 2 Week 2***

-------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------

## **ERD**

1. An entity is represented by a rectangle.

1. A weak entity is represented by a rectangle with a double outline.

1. Actions are represented by diamonds.

1. Attributes are represented by ovals.

## **Generating a Model**

```ruby
rails g model User name:string age:integer
```

## **Create**

```ruby
user = User.create(name: 'Eddie', age:31)

user =User.new
user.name = 'Eddie'
user.save
```

## **Read**

```ruby
user = User.all

user = User.first
second = User.find(2)
eddie = User.find_by(name: 'Eddie')
```

## **Update**

```ruby
user = User.find_by(name: 'Eddie')
user.name = 'Ed'
user.save

user = User.find_by(name: 'Eddie')
user.update(name: 'Ed')
```

## **Delete**

```ruby
user =User.find_by(name: 'Eddie')
user.destroy

User.destroy_by(name: 'Eddie')
User.destroy_all
```

## Active Record Associations Docs

[https://edstem.org/courses/4965/lessons/5835/slides/42177]

Has One Relationship:

```ruby
belongs_to
has_one
```

Has Many Relationship:

```ruby
belongs_to
has_many
```

Has Many Through:

```ruby
appointments
through:
```

Polymorphic:

```ruby
polymorphic
'able' suffix
```

## Active Record Migrations Docs

[https://edstem.org/courses/4965/lessons/5835/slides/42176]

```ruby
rails db:migrate
rails db:rollback
```

Adding single:

```ruby
rails generate migration AddPriceToBooks price:integer
rails db:migrate
```

Adding multiple:

```ruby
rails generate migration AddDetailsToBooks rating:integer description:text
rails db:migrate
```

Adding reference to another table:

```ruby
rails generate migration AddAuthorRefToBooks author:references
# Author set as a foreign key
rails db:migrate
```

Removing col:

```ruby
rails generate migration RemoveRatingFRomBooks rating:integer
rails db:migrate
```

Run own migration (Change Methods) ====> @ DOCS

## Model Methods Docs

Validations:

```ruby
validates :title, presence: true
# Cannot save book unless it has title attribute set.

validates :description, length: { minimum: 10, too_short: "%{count} is the minimum number of characters!" }
# Cannot save book if description was to short with error message.

validates :description, length: { in: 10..100 }
# Cannot save book if description is not within range.

validates :price, numericality: { greater_than_or_equal_to: 0 }
# Fails to save if the price has to be greater than or equal to 0.
```

Scopes:

```ruby
scope :bargin, -> { where(price: 0..500) }
```

-------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------

## **Thursday Class 21/01/21**

### **Content**

1. Routes
1. Controllers
1. Rspec

### **RSPEC:**

**Rspec Docs** =====> [http://rspec.info/documentation/]

**Rspec Core Docs** =====> [https://rspec.info/documentation/3.9/rspec-core/]

**Expectations** =====> [https://rubydoc.info/gems/rspec-expectations]

**Rspec - Rails Docs** =====> [https://rspec.info/documentation/4.0/rspec-rails/]
**Hashes - Rails Cheat Sheet** =====> [https://www.shortcutfoo.com/app/dojos/ruby-hashes/cheatsheet?fbclid=IwAR10e0kIF-6tEuSjgoer5vfppyusu5PX_ZTteqImISGMt0f5tserptCMm6U]

## ***spell_app*** ===> Week_2 Folder

### **App Install:**

``` ruby
# In terminal type the following:
rails new spell_app -T -d=postgresql
rails db:create
# In the gem file type the following:
gem 'rspec-rails'
# In terminal type the following:
bundle install
rails generate rspec:install
rails g controller Pages
# Open fold up in VS Code
code spell_app
```

-------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------

## **Friday Class 22/01/21**

Practice Quiz - Code: cs-is-fun

### **Agenda**

1. Rails View
1. Forms HTML Way
1. Navbar
1. Partials
1. Rails MOdel
1. Database Rails Migration
1. Forms Rails way (form_way)

Helpful Links:

[https://www.youtube.com/watch?v=t_ispmWmdjY&ab_channel=freeCodeCamp.orge]
[https://www.rubyguides.com/2019/06/rails-params/]
[https://guides.rubyonrails.org/active_record_basics.html]
[https://edgeguides.rubyonrails.org/active_record_migrations.html]
[https://guides.rubyonrails.org/form_helpers.html]
[https://www.youtube.com/watch?v=fmyvWz5TUWg&t=2s&ab_channel=freeCodeCamp.org]

-------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------

## ***Term 2 Week 3***

### **Rails Deployment**

- Heroku

- Digital Ocean

- Amazon EC2

### **Heroku**

Heroku Docs ======> [https://devcenter.heroku.com/articles/getting-started-with-ruby]

### **Forms**

#### **Action View Form Helpers**

[https://edstem.org/courses/4965/lessons/6021/slides/43401]

#### **Form_with Docs**

[https://edstem.org/courses/4965/lessons/6021/slides/43402]

-------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------

## **Thursday Class 28/01/21**

**Action View Helper ====>** [https://apidock.com/rails/ActionView/Helpers/UrlHelper/button_to]

-------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------

## **Friday Class 29/01/21**

**spell_app ====>** [https://github.com/CoderAcademy-ALL/spell_app]
**Renaming Apps from CLI ====>**[https://devcenter.heroku.com/articles/renaming-apps]

-------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------

## ***Term 2 Week 4***

### **Scaffolding**

```ruby
    rails g scaffold Posts title:string content:text
```

### **Authentication Intro**

Enable  gem 'bcrypt', '~> 3.1.7'

```ruby
rails g scaffold User email:uniq password:digest
```

```ruby
rails g controller sessions new create destroy
```

### **Related content:**

#### **Session vs Token Based Authentication** [https://medium.com/@sherryhsu/session-vs-token-based-authentication-11a6c5ac45e4]

#### **2 Sessions** [https://guides.rubyonrails.org/security.html#sessions]

#### **Your Node.js authentication tutorial is (probably) wrong** [https://medium.com/hackernoon/your-node-js-authentication-tutorial-is-wrong-f1a3bf831a46]

#### **Cookies - Web Development - YOUTUBE** [https://www.youtube.com/watch?v=xdH9zsW1CK0&feature=youtu.be&ab_channel=Udacity]

### **Devise:**

#### **Devise Github/Documentation:** [https://github.com/heartcombo/devise]

-------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------

## **Thursday Class 4/02/21**

Agenda:
        Complex Associations
        One to One
        One to Many (review)
        Mini challenge
        Many to Many (Join Table)
        Mini Challenge
        has_many_through ( based on how we go with time)
        Mini Challenge:

Take away msg:

Associations are super useful in Rails, but its not easy to get your head around it the first go. So do jump into the Rails console and play with it.

**Pretty print:**

```ruby
pp Author
```

**Mini Challenge 1:**

Create a user table and a tweet table. Decide what association must be set between the tables.

1. From the rails console - create 2 users
1. Create 2 tweets for each user
1. Show the tweet made by the first user
1. Delete the second user and ensure the second users tweets are also deleted.

**Many to many association rule:**

1. Must follow alphabetical odder

1. First table must be pluralized

-------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------

## **Friday Class 5/02/21**

**Agenda:**

Agenda:
        Complex Associations
        has_many :through
        mini challenge
        Polymorphic association
        mini challenge
        self join
        mini challenge
        Advance Challenge: build the front end for student, teacher, subject example (has_many :through association)

[https://guides.rubyonrails.org/association_basics.html]

**Helpful Git comment tips / tricks** [https://dev.to/sublimegeek/what-tense-do-you-use-in-git-commit-messages--4hic]

**Postgresql Tutorial:** [https://www.postgresqltutorial.com/postgresql-inner-join/]

-------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------

## ***Term 2 Week 5***

-------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------

## **Payment**

**Setting up Stripe:**

**Stripe: ====>** [www.stripe.com]

1. Sign Up
1. Create business name
1. Developers -> API Keys

```ruby
bundle install stripe

# Followed by:

rails credentials:edit
# Opens credential file:
# Type the following:

stripe:
  secret_key: ###########
  public_key: ###########
```

1. Config / initializer
1. Create a stripe.rb file
1. Add the following line:

```Ruby
Stripe.api_key = Rails.application.credentials.dig(:stripe, :secret_key)
```

-------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------

## **Thursday Class 10/02/21**

See Notes

Heroku Docs - [https://devcenter.heroku.com/]

-------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------

## **Friday Class 11/02/21**
