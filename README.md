## Basic Ruby on Rails CRUD App for Product with React.js API
This is a Rails App for displaying products with the following attributes: title, short description, description, initial price and final price.

The homepage is the collection page of the products. Each product is displayed by a card with its title and short description, which is link to the diplay page of each product. In case the user is logged in and has admin privileges, he has the options to edit or delete a product on its card and to create a new product. 

In the display page of each product, its title, short description and description are displayed and when a button is clicked its initial and final prices are displayed. In case of admin user, he has the options to edit or delete the product on its display page.

## Information about the App
* Ruby version 3.0.0
* Rails version 6.1.4.1
* Node version 14.17.6
* Yarn version 1.22.11
* React version 17.0.2
* SQLite for database
* HTML5, SCSS and Bootstrap 5 for front end
* Devise was used for user authentication and CanCanCan for user authorization
* Friendly_id is used for generating the slugs of the products
* React.js with Webpacker was used as API for fetching the product prices and display them on product display page after a button is clicked.

## Steps to run the App

1. Clone this git repository to your wanted folder and move to the directory of the project
```
$ git clone https://github.com/elinachar/products_demo.git
$ cd products_demo
```

2. Install all depedencies for the app
```
$ bundle install
$ yarn install OR npm install
```

3. Prepare the database
```
$ bundle exec rails db:prepare
```

4. Start the Rails app
```
$ bundle exec rails s
```

5. Visit the app in your browser at http://localhost:3000/
At that point there is no product and it should display that there are no products, yet. 

6. Create a new account either by cliking on top-right of the navigation bar Login and then clicking Sign up or by visiting http://localhost:3000/sign-up

7. Connect to database and give your user the admin attribute.
In a new CLI window move to the directory of the app:
```
$ bundle exec rails c
> u = User.find_by_email("your-email-address") OR u = User.first (if it is the only user in the db)
> u.admin = true
> u.save
> exit
```

8. Now that your are logged in and you are admin user you can create products.
- Visit the home page (http://localhost:3000/) of the app and click "Create New Product" 

- In the 'New Product' page (http://localhost:3000/products/new) fill in the attributes of the product and click the button "Create Product". Keep in mind that both the initial and final prices should be only numbers (floats) without any currency symbol. The currency is Euro and the ??? sybmol is added by default when displaying the prices of the product.

- Once the product has successfully created you are redirected to the display page of the product.

- In the display page of the product the title, the sort description and description of the product are shown. Above them there is a button "Show Product Prices", which when it clicked it displays the intial price and the final price of the project.

- As admin user you can edit or delete the project in its display page. You can also go back to see the collection of the products by clicking "Back to Products" button or by clicking the "Products Demo" app title at the top left of the navigation bar.


