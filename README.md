# HexyJS

[![Build Status](https://travis-ci.com/jecsham/hexyjs.svg?branch=master)](https://travis-ci.com/jecsham/hexyjs)

A simple library with some hexadecimal utilities.

## Install
```sh
    $ npm install hexyjs
```
## Basic Usage

 ```js

    const hexyjs = require("hexy");
    
    /* String to Hexadecimal  */

    hexyjs.strToHex("Cave Story");
    // => 436176652053746f7279


    /* Hexadecimal to String */

    hexyjs.hexToStr("436176652053746f7279");
    // => Cave Story

    hexyjs.hexToStr("W36176652053746f727P"); // invalid hex string
    // => false


    /* Validate a Hexadecimal string */

    hexyjs.isHex("436176652053746f7279");
    // => true

    hexyjs.isHex("43 61 76 65 20 53 74 6f 72 79");
    // => true

    hexyjs.isHex("32JGD");  
    // => false

```

## strToHex() Options
You can use this function with options to change the output.

* **grouped:** string output will be grouped (*default: false*)
* **uppercase:** string letters will be transformed to upper case. (*default: false*)

 ```js

    hexyjs.strToHex("Cave Story", { uppercase: true });
    // => 436176652053746F7279

    hexyjs.strToHex("Cave Story", { grouped: true });
    // => 43 61 76 65 20 53 74 6f 72 79

```
## isHex() strict option
Strict option is enabled by default, that means the function will return false if the string length is not divisible by 2. If you disabled it, you can validate characters for example. Check out the following example.

 ```js

    hexyjs.isHex("1"); // strict enabled  
    // => false

    hexyjs.isHex("1", false); // strict disabled  
    // => true

```


