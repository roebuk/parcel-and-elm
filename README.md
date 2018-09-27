# Getting up and running with Parcel & Elm

As of v1.10.0, Parcel ships with Elm support straight outo of the box. If you've never used Parcel, here's how to get started. 

Initialise a new project and install parcel as a local dependency.

    $ yarn init
    $ yarn add parcel


Create an `index.html` and within here link to a JavaScript file. In our case, the JS file will be
stored in `./src/index.js`. Parcel will magically follow the `src` attribute of your script tag and
use that as an entry point for your app.

Inside this JS file we will import out Elm code which is also stored within the `src` directory.


    import { Elm } from './Main.elm';

    Elm.Main.init({
      node: document.querySelector('.root')
    });


### Developing

Parcel ships with it's own web server that is enabled when we run `parcel index.html`. Because
Parcel is installed locally, we can access the local binary by adding this command into our
`scripts` section of our `package.json` file. Now when we run this script with `$ yarn start` we
are able to access the running app via [http://localhost:1234](http://localhost:1234)

### Productioning

To create a producion build, let's add another script to our `scripts` section of the
`package.json` file. We'll add a `build` script that will run `parcel build index.html`. Parcel
will automatically add the `--optimize` flag to the Elm compiler to keep our assets super small.
Parcel will output our build assets in the `dist` directory.


That's it. Hopefully this helps get you up and running with Elm & Parcel 🚀
