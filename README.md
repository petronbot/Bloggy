Petra's Blog
------------

A cool blog for Petra Gulicher

This blog is built with WordPress. The way the project is structured is built upon the very clever
[WordPress-Skeleton][1] project template by Mark Jaquith.


Setting up WordPress
--------------------

Once you've cloned the project from github, you'll need to add a git submodule to point to the WordPress [github mirror][2]. To clone it, you just need to enter:

	git submodule add https://github.com/WordPress/WordPress.git build/public/wp/
    git submodule update

Next, create the file `build/public/local-config.php` (use local-config-sample.php as a template). As part of this you'll need to create a MySQL database, username and password and put those details into 
`build/public/local-config.php`.

Database Name: `petrablog`
Database User: `petrablog`
Database Pass: `petrablog`

Next, you can choose to allow WordPress to initialise your blank database with a fresh WordPress installation, or you can import the project's database dump to initialise your development environment with some actual content.


Upgrading WordPress
-------------------

This is just a matter of checking out a different tag for the submodule in `build/public/wp`. Use:

    cd build/public/wp
    git checkout 4.4-branch
    cd ../../../
    git commit -m "Update Wordpress to version 4.4"

After you've done this, other developers who have a working copy will need to do the following again after they next pull and merge:

    git submodule update

---

[1]: https://github.com/markjaquith/WordPress-Skeleton
[2]: https://github.com/WordPress/WordPress