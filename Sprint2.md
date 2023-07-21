# News section

- Step 1: Create a Database to Work with

- Step 2: Connect to Your Database

- Step 3: Setting up Your Model

- Step 4: Display the News

- Step 5: Routing


# Step 1:

You need to create a database ci4tutorial that can be used for this tutorial, and then configure CodeIgniter to use it.

    CREATE TABLE news (
        id serial Primary key,
        title VARCHAR(128) NOT NULL,
        slug VARCHAR(128) NOT NULL unique,
        body TEXT NOT NULL
    );

Records:

    INSERT INTO news VALUES
        (1,'Elvis sighted','elvis-sighted','Elvis was sighted at the Podunk internet cafe. It looked like he was writing a CodeIgniter app.'),
        (2,'Say it is not so!','say-it-isnt-so','Scientists conclude that some programmers have a sense of humor.'),
        (3,'Caffeination, Yes!','caffeination-yes','World s largest coffee shop open onsite nested coffee shop for staff only.');

# Step 2:

    See app/Config/Database.php

# Step 3 :

> Models are the place where you retrieve, insert, and update information in your database or other data stores.

Open up the app/Models/NewsModel.php 

# Step 4 :

Now that the queries are written, the model should be tied to the views that are going to display the news items to the user.

    Open app/Controllers/News.php.

    Create app/Views/news/index.php 

>We are again using using esc() to help prevent XSS attacks. But this time we also passed “url” as a second    parameter. That’s because attack patterns are different depending on the context in which the output is used:

    <p><a href="/news/<?= esc($news_item['slug'], 'url') ?>">View article</a></p>

Now:

    app/Views/news/view.php



