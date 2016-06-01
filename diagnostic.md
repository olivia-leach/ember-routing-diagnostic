# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    Tasks performed inside the Ember Application Router:
    * tell the application which URL corresponds to which view

    Tasks performed inside an Ember Route:
    * parse the URL
    * extract meaningful information (e.g. dynamic segments)
    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    ember g route campus/boston
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    {{#link-to 'campus.boston'}}Boston Campus{{/link-to}}
    ```

1.  Explain **at least** two differences between the following two route
    definitions.

    ```js
    this.route('products', function () {
      this.route('product', { path: '/:product_id' }); // <= 👀here
    });

    this.route('product', { path: '/products/:product_id' }); // <= 👀 here
    ```

    ```md
    The first route defines a nested route for product (one item in the products list) since it is defined within the products route. The second route defines a stand-alone route for 'product.' The second method is the correct way to handle this situation if looking at one product creates a different view state than looking at the product list as a whole.
    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    We can access '123' inside the model hook of the product route. '123' would be stored at params.movie_id.
    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
    Since the Route has a model method, we can reference data from that method in the corresponding template by using: model.

    For example:
    <h4>model.name</h4>
    ```
