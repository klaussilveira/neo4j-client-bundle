Neo4j Client Bundle
===================

This bundle provides a simple integration of Josh Adell's 
[Neo4jPHP](https://github.com/jadell/neo4jphp) library into Symfony2.
It allows manipulation of data inside the Neo4j graph database
through the REST connectors.

## Installation

To install this bundle, add this to your project's composer.json:

``` json
"require": {
    // ...
    "klaussilveira/neo4j-client-bundle": "dev-master",
}
```

Next, update your vendors by running:

``` bash
$ composer update
```

Now enable the bundle in the kernel:

``` php
<?php
// app/AppKernel.php

public function registerBundles()
{
    $bundles = array(
        // ...
        new Neo4j\Client\ClientBundle\Neo4jClientBundle(),
    );
}
```

And configure the bundle by adding the `neo4j_client` namespace into `config.yml`:

``` yaml
neo4j_client:
    host: 'localhost'
    port: 7474
```

Congratulations! You're ready to use Neo4j Client into Symfony2.

## Basic Usage

The only thing to do is to request the `neo4j.client` service from the 
container to get an instance of `Everyman\Neo4j\Client`.

``` php
<?php

$client = $this->get('neo4j.client');
print_r($client->getServerInfo());

```
