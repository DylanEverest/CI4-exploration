# Create News Items

- Enable CSRF Filter

- Create a Form : View , Controller

- Model Updating

- Routing 


# Step 1 : Enable CSRF Filter

see  app/Config/Filters.php:

    public array $methods = [
        'post' => ['csrf'],
    ];

It configures the CSRF filter to be enabled for all POST requests. You can read more about the CSRF protection in Security library.

In general, if you use $methods filters, you should disable Auto Routing (Legacy) because Auto Routing (Legacy) permits any HTTP method to access a controller. Accessing the controller with a method you don’t expect could bypass the filter.
    
    Since v4.2.0, the auto-routing is disabled by default.

    $routes->setAutoRoute(false);
