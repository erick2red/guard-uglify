## What?
Compresses your javascript files, using uglifyjs and the uglifier gem when you save your source file.

## Use
if you haven't already:

    gem install uglifier

then

    git clone https://github.com/erick2red/guard-uglify.git
    cd guard-uglify
    rake install

in your project's directory root

    guard init
    guard init uglify

which will add this to your Guardfile  

    guard 'uglify',
      :input => "app/assets/javascripts",
      :output => "public/javascripts",
      :uglifier => {
          :mangle => {
            :toplevel => true
          },
          :compress => {
            :drop_console => true,
          }
        }

Adjust the paths, and set the options, `:uglifier` options contains the options passed to Uglifier gem which you can find [here][1].

Note that:

1. every minified file will contain the *.min.js* suffix
2. Files in your source folder with that same suffix won't be minifed.

## License
(The MIT License)

Copyright (c) 2014 Erick Pérez Castellanos

Copyright (c) 2011 Aaron Cruz

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the 'Software'), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

[1]: https://github.com/lautis/uglifier/blob/master/README.md
