==============================================================================
Webpack
==============================================================================

Prerequisits
------------

Install Webpack globally::

  $ sudo npm install webpack -g

Install Webpack development server globally::

  $ sudo npm install webpack-dev-server -g

Create initial npm configuration::

  $ npm init

Install css style loader locally::

  $ npm install css-loader style-loader


Create Basic Example
--------------------

webpack.config.js::

    module.exports = {
        entry: "./entry.js",
        output: {
            path: __dirname,
            filename: "bundle.js"
        },
        module: {
            loaders: [
                { test: /\.css$/, loader: "style!css" }
            ]
        }
    };

index.html::

    <html>
        <head>
            <meta charset="utf-8">
        </head>
        <body>
            <script type="text/javascript" src="bundle.js" charset="utf-8"></script>
        </body>
    </html>


content.js::

    module.exports = "It works from content.js.";

style.css::

    body {
        background: yellow;
    }

entry.js::
    require("./style.css");
    document.write(require("./content.js"));


Development Server
------------------

Start the Webpack development server::

  $ webpack-dev-server --progress --colors

Open the site in the browser::

  http://localhost:8080/webpack-dev-server/bundle


Source / Further Reading
------------------------

  https://webpack.github.io/docs/tutorials/getting-started/
