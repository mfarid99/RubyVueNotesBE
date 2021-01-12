-Day 11 of 100, today I am create a note App using Ruby on Rails on the backend and Vue on the frontend. To set up the project, I used the following: <rails new noteapp --database=postgresql --api> For a quicker set up, using --api allows the developer to limit the number of features/templates that Rails provides.  In this project, Vue frontend will consume the API and we will use Postgres as the database. 
-Configure the database:
*For the purpose of deploying to Heroku, under database.yml file (under config), I updated the production section to:
  <<: *default
  database: noteapp_production
  url: <%= ENV['DATABASE_URL'] %>
  *To create a superuser, in terminal enter: CREATE USER <username> WITH SUPERUSER PASSWORD '<password>';
  *Enter the username/password under test in .yml and then add the port number. Then add host: localhost. Copy the same info in development 
-Then make sure Gemfile has all the needed libraries. Uncomment cors (managing permission) and bcrypt (encrypting passwords) and add gem 'jwt' (authentication). bundle install
-rails db:create to create database
-Then I configured cors where it is important to change origins to "*" which means anyone can make a request to the server and can request anything. 
-Then I configured the routes. Remember resource command creates all the RESTful routes for the model
-Then, I created the user model using the following command: rails g model User username:string password_digest:string age:integer
-Then create controller 
-To verify that the database was seeded after running rails db:seed, run the rails console and search for the user that we created in seed (p User.find(1))
-After setting up user_controller and application_controller, test the login function in postman
-Now, we built the notes model using scaffold


