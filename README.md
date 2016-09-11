# amitkhare/InkRouter

##InkRouter is an easy to use minimal PHP routing system

```sh
<?php

// autoload via composer
require __DIR__.'/../vendor/autoload.php';

// use namespace
use InkImagine\InkRouter\InkRouter;

// Take an instance of Router Class.
// set Base URI as second perameter : /example
$router = new InkRouter(['db'='DATABASE','var1'=123],"/example");

// URL::GET www.example.com/
$router-add("GET",'/', "Page:home");

// URL::GET www.example.com/product/222
$router-add("GET",'/product/{d}', "Page:product#id");

// URL::POST www.example.com/product
$router-add("POST",'/product', "Page:product_process");

// URL::GET www.example.com/about/something/
$router-add("GET",'/about/{w}', "Page:about#var1",['myname'='amitkhare']);

// URL::GET www.example.com/page/t-shirts/323
$router-add("GET",'/page/(\w+)/(\d+)/', "Page:get#category|id");

// Dispatch Routes.
$router-dispatch();
```