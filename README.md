phpnats
=======

**Travis**

* Master: [![Build Status](https://travis-ci.org/repejota/phpnats.png?branch=master)](https://travis-ci.org/repejota/phpnats)
* Develop: [![Build Status](https://travis-ci.org/repejota/phpnats.png?branch=develop)](https://travis-ci.org/repejota/phpnats)

**Coverage**

* Master: [![Coverage Status](https://coveralls.io/repos/repejota/phpnats/badge.svg?branch=master)](https://coveralls.io/r/repejota/phpnats?branch=master)
* Develop: [![Coverage Status](https://coveralls.io/repos/repejota/phpnats/badge.svg?branch=develop)](https://coveralls.io/r/repejota/phpnats?branch=develop)

Introduction
------------

A PHP client for the [NATS messaging system](https://nats.io).

>  Note: phpnats is under heavy development.

Requirements
------------

* php ~5.4
* [nats](https://github.com/derekcollison/nats) or [gnatsd](https://github.com/apcera/gnatsd)


Usage
-----

### Basic Usage

```php
$client = new \Nats\Connection();
$client->connect();

# Simple Publisher
$client->publish("foo", "foo bar");

# Simple Subscriber
$callback = function($payload)
{
    printf("Data: %s\r\n", $payload);
};
$client->subscribe("foo", $callback);

# Wait for 1 message
$client->wait(1);
```

Developer's Information
-----------------------

### Tests

Tests are in the `tests` folder.
To run them, you need `PHPUnit` and execute `make test`.

### Code Quality

We are using [PHP Code Sniffer](http://pear.php.net/package/PHP_CodeSniffer/docs)
to ensure our code follow an high quality standard.

To perform an analysis of the code execute `make cs`.


Creators
--------

**Raül Pérez**

- <https://twitter.com/repejota>
- <https://github.com/repejota>

**Adrià Cidre**

- <https://twitter.com/adriacidre>
- <https://github.com/adriacidre>

**José Gil**

- <https://twitter.com/josgilmo>
- <https://github.com/josgilmo>

**Gorka López de Torre**

- <https://twitter.com/glopezdetorre>
- <https://github.com/glopezdetorre>



License
-------

MIT, see [LICENSE](LICENSE)
