# Phoenix Framework
 
## Directory structure

- `config/`
  - `config.exs` is the entry point.
    At the end of this file the environment specific config is loaded
  - `runtime.exs` is executed for all envs.
    It's executed after compilation and before the system starts
- `lib/`
  - `<appname>/`
    - Model in MVC architecture
    - dir for business logic and business domain
    - It typically interacts directly with the database
    - `repo.ex` main interface to the database
  - `<appname>_web/`
    - View and Controller in MVC architecture
    - `endpoint.ex` is the entry point for HTTP requests. 
      From here is sent to `rounter.ex`
    - `router.ex` defines the rules to dispatch requests to **controllers**, which calls a **view module** to render HTML
    - There is a naming convention for controllers, views and template directories

      ```
      lib/<appname>_web/
        controllers/
          example_controller.ex # inside module ExampleController
          example_html.ex # inside module view ExampleHTML
          example_html/ # .heex templates
            index.html.heex
            
      ```

- `assets/`
  - A dir that keeps code for the front-end that needs to be bundled (CSS, JS).
    The generated assets are saved in `priv/static/assets/`
  - The bundle process is configured in `config/config.exs`

## Request life-cycle

1. Endpoint

   - Handles HTTP requests

2. Router (`lib/<appname>_web/router.ex`)

   - Responsible of matching HTTP requests (verb + path) with parts of the application (controller + action)

     ```elixir 
     # inside router.ex

     # verb path, controller, action
     get "/example", ExampleController, :index
     ```
   
   - The router allows to scope functionality.
     For example, authentication
   
3. Controller 

   - Controllers are Elixir modules
   - The controller talks to the business domain (db) and prepares the data for the presentation layer
   - Actions
     -  Actions are Elixir functions defined within a controller
     -  The purpose of actions is to gather the data and perform the tasks needed for rendering
   - Example of a controller with an action `lib/<appname>_web/controllers/example_controller.ex`

     ```elixir
     defmodule Appname.ExampleController do
       use AppnameWeb, :controller

      # action
       def index(conn, _params) do
         render(conn, :index)
       end
     end
     ```

5. View

   - You could use function components or templates
   - Example `lib/<appname>_web/controllers/example_html.ex`
   

## Auth

- Includes
  - Password hashing
  - Forbidding access
  - Account confirmation (not enforced by default)
- If you go to `/dev/mailbox` you can check the confirmation emails that were sent

## Ecto

- Ecto schemas specify how Elixir data types map to and external sources, such as database tables
- You can generate an Ecto schema with the task `phx.gen.schema`. 
  This will generate two files: a schema in `lib/<appname>/` and a migration file

  ```bash
  mix phx.gen.schema User users name:string email:string number_of_pets:integer
  # The first argument is the schema module
  # The second argument is the plural name (used as the table name)
  # The other arguments are fields
  ```

- Ecto Repo is the interface into the storage system, be it a database or an external service like a RESTful API

## CLI

- `mix phx.server`

## Investigate

- Qué son los Contexts?
