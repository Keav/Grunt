# Grunt
Project scaffold for a Grunt based project

## LiveReload

LiveReload is awesome. It allows you to stay focused in your code and each time you save a file, your site is automatically updated in the browser, instantly.

I've seen lots of Grunt guides that detail using Grunt-Connect to spin up a local web server on the fly. I've not checked, but I'm guessing these methods are only good for static html and not for php driven sites, which most of mine are. As well as this, I naturally like to have a separation of concerns -  Sublime Text for coding and linting, Grunt for Building and WAMP/MAMP are my web servers of choice. This allows me to configure my Apache server as I wish, with Virtual Hosts, and of course provides MySQL for my databases.

* Add the LiveReload extension to your browser. The main site is `http://livereload.com/` but you should use your browsers extensions store and find the individual extension there.
* Include something like the following in your `Gruntfile.js`:
```
        watch: {
            options: {
            },
            livereload: {
                files: ['src/**/*.html', 'src/**/*.php', 'src/**/*.css', 'src/**/*.js'],
                options: {livereload: true}
            }
        }
```
1. Fire up your local server
2. Run `grunt watch` in your terminal to start Grunt watching your files for changes
3. Load your site in your browser and then enable the LiveReload extension

NB: if you have not run `grunt watch` then LiveReload will have nothing to connect to and will simply appear to do nothing.

## Deleting the `node_modules` folder on Windows

Due to the ridiculous folder nesting associated with node modules (the nesting is how it defines dependancies) and Windows ridiculous limit on path lengths (the path cannot exceed 256 characters), Windows often has major issues deleting this folder.

RimRaf (https://github.com/isaacs/rimraf) to the rescue!

RimRaf is the UNIX command `rm -rf` (Recursive, Force).

Install it globally:
```
npm install rimraf -g
```

Then run it where you need to delete `node_modules`:
```
rimraf node_modules
```

...and breathe ;)
