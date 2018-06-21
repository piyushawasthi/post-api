# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version
```
ruby-2.4.1 [ x86_64 ]
```

* System dependencies
```
Ubuntu 16.04
Mac
Windows + Ruby kit
```
* Configuration
```
1: Unzip testapp
2: Go into testapp
3: Install bundle gem 'gem install bundle'
4: Run 'bundle install'
```

* Database creation
```
$ rake db:create
Created database 'testapp_development'
Created database 'testapp_test'
```

* Database initialization
```
$ rake db:migrate
== 20180620203924 DeviseTokenAuthCreateUsers: migrating =======================
-- create_table(:users)
   -> 0.0784s
-- add_index(:users, :email, {:unique=>true})
   -> 0.0447s
-- add_index(:users, [:uid, :provider], {:unique=>true})
   -> 0.0573s
-- add_index(:users, :reset_password_token, {:unique=>true})
   -> 0.0424s
-- add_index(:users, :confirmation_token, {:unique=>true})
   -> 0.0555s
== 20180620203924 DeviseTokenAuthCreateUsers: migrated (0.2790s) ==============

== 20180620204740 CreatePosts: migrating ======================================
-- create_table(:posts)
   -> 0.0751s
== 20180620204740 CreatePosts: migrated (0.0753s) =============================
```

* How to run the test suite
```
bundle exec rspec spec
```

* API postman output
```
{
  "info": {
    "_postman_id": "8c9c5e62-0141-4e2e-b719-eeac658146d0",
    "name": "DeviseRelated",
    "schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json"
  },
  "item": [
    {
      "name": "http://localhost:3000/auth",
      "request": {
        "auth": {
          "type": "noauth"
        },
        "method": "POST",
        "header": [
          {
            "key": "Content-Type",
            "value": "application/json"
          },
          {
            "key": "",
            "value": "",
            "disabled": true
          }
        ],
        "body": {
          "mode": "raw",
          "raw": "{\r\n    \"email\": \"admin@app.com\",\r\n    \"password\": \"12345678\",\r\n    \"password_confirmation\": \"12345678\"\r\n}"
        },
        "url": {
          "raw": "http://localhost:3000/auth",
          "protocol": "http",
          "host": [
            "localhost"
          ],
          "port": "3000",
          "path": [
            "auth"
          ]
        },
        "description": "Creating a User"
      },
      "response": []
    },
    {
      "name": "http://localhost:3000/posts",
      "request": {
        "method": "POST",
        "header": [
          {
            "key": "Content-Type",
            "value": "application/json"
          },
          {
            "key": "access-token",
            "value": "EKppvfB3WENUu8BHvOAa2w"
          },
          {
            "key": "client",
            "value": "z5zLvleJsIYJvwYtSHKn2w"
          },
          {
            "key": "expiry",
            "value": "1530740039"
          },
          {
            "key": "uid",
            "value": "admin@app.com"
          }
        ],
        "body": {
          "mode": "raw",
          "raw": "{\r\n    \"title\": \"Post One\",\r\n    \"url\": \"postone@app.com\"\r\n}"
        },
        "url": {
          "raw": "http://localhost:3000/posts",
          "protocol": "http",
          "host": [
            "localhost"
          ],
          "port": "3000",
          "path": [
            "posts"
          ]
        },
        "description": "Creating Post"
      },
      "response": []
    },
    {
      "name": "http://localhost:3000/auth/sign_in",
      "request": {
        "method": "POST",
        "header": [
          {
            "key": "Content-Type",
            "value": "application/json"
          }
        ],
        "body": {
          "mode": "raw",
          "raw": "{\r\n    \"email\": \"admin@app.com\",\r\n    \"password\": \"12345678\"\r\n}"
        },
        "url": {
          "raw": "http://localhost:3000/auth/sign_in",
          "protocol": "http",
          "host": [
            "localhost"
          ],
          "port": "3000",
          "path": [
            "auth",
            "sign_in"
          ]
        },
        "description": "Users Sign in"
      },
      "response": []
    },
    {
      "name": "http://localhost:3000/posts",
      "request": {
        "method": "GET",
        "header": [
          {
            "key": "Content-Type",
            "value": "application/json"
          },
          {
            "key": "access-token",
            "value": "Ggj4jklYobK3EluIeOHy6Q"
          },
          {
            "key": "client",
            "value": "l4Ari_GzfHoq_XF-w_sW8A"
          },
          {
            "key": "expiry",
            "value": "1530740911"
          },
          {
            "key": "uid",
            "value": "admin@app.com"
          }
        ],
        "body": {},
        "url": {
          "raw": "http://localhost:3000/posts",
          "protocol": "http",
          "host": [
            "localhost"
          ],
          "port": "3000",
          "path": [
            "posts"
          ]
        },
        "description": "List of all the posts related to that user"
      },
      "response": []
    }
  ]
}
```

* Deployment instructions

* ...
