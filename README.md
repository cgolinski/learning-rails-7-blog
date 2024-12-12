# README

Course: https://gorails.com/series/build-a-blog-with-rails-7

Current module: https://gorails.com/episodes/adding-tailwindcss-to-rails

## Notes

### MVC

Model: db and validations. Ruby classes. E.g. email, validation that not gmail.com

View: HTML, JSON, output sent to user

Controller: handles requests

Routes: e.g. /sign_up url path. Tells which controller to send request to, e.g. Users::Registrations Controller
Helpers:

GET /sign_up --> Users::Registrations Controller --> User model --> Users::Registrations Controller --> form HTML view

POST /sign_up --> Users::Registrations Controller --> User model --> try to save to db --> success/failure back to Users::Registrations Controller

-success-> login user (set a cookie); redirect to /homepage

-failure-> render form HTML errors

### Rails commands

In repo in Terminal: `rails c`

#### Generate new model

`rails generate model BlogPost title:string body:text`

Creates `app/models/blog_post.rb` and `db/migrate/20241211130306_create_blog_posts.rb`

#### Create new blog post

`BlogPost.create(title: "Hello World", body: "This is my very first blog post")`

#### Update existing blog post

`blog_post = BlogPost.find(1)`

`BlogPost.update(title: "Updated title", body: "This is my very first blog post")`

#### Delete blog post

`blog_post.destroy`

#### See Active Record model names converted into other things

`BlogPost.model_name`

provides ways to convert the class name into other things you might need

```
 @collection="blog_posts",
 @element="blog_post",
 @human="Blog post",
 @i18n_key=:blog_post,
 @klass=BlogPost(id: integer, title: string, body: text, created_at: datetime, updated_at: datetime),
 @name="BlogPost",
 @param_key="blog_post",
 @plural="blog_posts",
 @route_key="blog_posts",
 @singular="blog_post",
 @singular_route_key="blog_post",
 @uncountable=false>
```

### TablePlus

#### To open db in TablePlus

1. Open TablePlus
2. Click "+" to add new db
3. Select SQLite
4. Select file: `/db/development.sqlite3`, click "open"
5. Click "connect" (no other fields needed)
