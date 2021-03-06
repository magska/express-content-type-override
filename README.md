# Express Content-Type Override Middleware

[![NPM Version](https://img.shields.io/npm/v/express-content-type-override.svg)](https://travis-ci.org/rbartoli/express-content-type-override)
[![Travis build status](https://travis-ci.org/rbartoli/express-content-type-override.png?branch=master)](https://npmjs.org/package/express-content-type-override)

An Express middleware to override the `content-type` header of the request.

## Installation

```bash
$ npm install --save express-content-type-override
```

## Usage

```javascript
var express = require('express');
var app = express();
var bodyParser = require('body-parser');
var registrationController = require('./controllers/registrationController');

server.use( '/registration', contentTypeOverride({
    contentType: 'application/x-www-form-urlencoded',
    charset: 'utf-8'
}));
server.use( bodyParser.json() );
server.use( bodyParser.urlencoded({
    extended: true
}));

app.post( '/registration', registrationController.index );

app.listen( 3000 );
```

## Options
**contentType**
Specify the `content-type` mime-type you'd like to use. Defaults to `application/x-www-form-urlencoded`.

**charset**
If you need to specify charset as part of `content-type`. No default, will not be part of `content-type` if not set.

## License
The MIT License (MIT)

Copyright (c) 2015 Riccardo Bartoli

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
