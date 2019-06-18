===============
Express & Vue
===============

Express backend & Vue frontend

Run
===

Run docker and visit http://localhost:8080::

    $ docker-compose up

How to build it from scratch?
=============================

1. Create project folder::

    $ mkdir express-vue
    $ cd express-vue

2. Create Express backend app, install dependencies::

    $ express back
    $ cd back
    $ npm install

3. Change default port from ``3000`` to ``8000`` in ``bin/www``.

4. Enable CORS in Express using following middleware::

    app.use(function(req, res, next) {
      res.header("Access-Control-Allow-Origin", "*");
      res.header("Access-Control-Allow-Headers", "Origin, X-Requested-With, Content-Type, Accept");
      next();
    });

5. Install ``vue client``::

    $ npm install -g @vue/cli

6. Create Vue frontend app in project folder, install dependencies::

    $ vue create front

7. Fetch data from Express backend through "http://localhost:8000/<path>" inside .vue files.

8. Create separate ``Dockerfile`` in back and front apps and ``docker-compose.yml`` in project folder.
