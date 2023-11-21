# laravel-graphql-todoapp
[Laravel GraphQL](https://lighthouse-php.com/6/getting-started/installation.html#install-graphql-devtools)

- Create a database file:
  ```bash
  touch database/database.sqlite
  ```

- Create a model for your Todo item, e.g., `Todo.php`:

    ```bash
    php artisan make:model Todo -m
    ```

- Define the models structure and relationships in the migration file.

  ```php
  public function up()
  {
      Schema::create('todos', function (Blueprint $table) {
          $table->id();
          $table->string('title');
          $table->boolean('completed')->default(false);
          $table->timestamps();
          $table->softDeletes();
      });
  }
  ```

  ```bash
  php artisan migrate
  ```
- Install Lighthouse (GraphQL library for Laravel):
  
  ```bash
  composer require nuwave/lighthouse
  ```

- Install GraphiQL (Playground)
  ```bash
  composer require mll-lab/laravel-graphiql
  ```

- Create a folder called graphql and a file called schema.graphql in the root folder

- Create a Query using Lighthouse to customize the return value:
  ```bash
  php artisan lighthouse:query Greetings
  ```

- Run api and visit /graphiql