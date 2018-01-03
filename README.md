# About

This is an API application only. 
The structure of this API is 
* User has many posts
* User has many comments
* Posts has many comments

## Commands 
1. Create new rails API App
> rails new my_blog --api

2. Create scaffold for User, Post and Comments
> rails g scaffold user email:string password:string auth_token:string

> rails g scaffold post title:string body:text user:references

> rails g scaffold comment body:text user:references post:references

3. Migrage the database
> rake db:migrate

4. Seed the dummy data using db/seed.rb file
> rake db:seed

5. Create a serializer
> rails g serializer user

6. 



# Deploying to heroku
1. run command 
> heroku create
2.Edit gem file 
```
group :development, :test do
  gem 'sqlite3'
end

group :production do
  gem 'pg'
end
```
3. run bundle install
> bundle install --without production

4. add commit and push

5. push it on heroku
> git push heroku mater

6. migrate db to heroku 
> heroku run rails db:migrate

7. Open application
> heroku open
