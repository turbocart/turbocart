# turbocart
Open source shopping cart microservice.

_See below for instructions on how to get access to our technology preview._


## What is it?

At it's core turbocart is an API that manages inventory and
processes sales transactions in a really fast manner.

You can self-host turbocart in any type of datacenter... it
supports "serverless" mode and if configured right can be
setup to support a globally distributed, fault-tolerant,
zero-downtime service across multiple clouds.


## Turbocart in your CMS

One key thing is that your sales data no longer resides
*within* your CMS (content management system), separating things out so that your CMS performs better. Most shopping carts that live "within" your CMS make your CMS perormance very bad. Turbocart solves this issue.

The Turbocart API is designed to minimize server communication
so with your old CMS-based solution you may have dozens or
hundreds of HTTP requests to have a user successfully transact. With Turbocart that traffic can be reduced to less
than 10 requests. For landing pages with few items it could
even be done with as little as 3-5 transmissions.

We provide a basic "shopping cart" front-end service that
you can use as an attachment on your website, or you can code
your own and just submit the results to the API.

Our product roadmap includes making plugins for popuar CMS
systems to make it even simpler to manage adding products
to your pages.

Turbocart is also ideal for inclusion on statically-generated websites allowing you to have extremely fast website performance for both content and the shopping cart.


## Migrating from a CMS cart to Turbocart

The Turbocart team has migrated dozens of e-commerce stores across different platforms. We are desiging the system with this in mind.

Our goal is to have pre-built, configurable, migration tools for popular CMS platforms. We want it to be as simple as including a Turbocart plugin in your CMS, running the migration, and then disabling your old commerce system. Yes, we are suggesting that in many cases this could be an "in-place" migration(!).

Plugins we want to build will target migrations for:

 - WordPress / WooCommrece
 - DrupaCommerce
 - Ubercart sites running on Drupal
 - Magento
 - ... and more

If your commerce site is using one of the above platforms please reach out to us if you are concerned about performance of your website. We would love to hear from you.

We want to simplify migrations to the point where CMS developers can focus on *content* again.


## Behind the scenes

We use node.js for the API and Apache Cassandra as the database. The reason for this is the ability to scale (Cassandra scales linearly), but also so that the service is fault-tolerant to network outages.

If your store starts getting very popuar you can simply add more copies of the node.js API service to your production environment, and likewise you can add more physical databases into Cassandra's data Ring, so that you can sale infinitely. 

We recommend you follow Cassandra's suggestions by putting the databases directly on the network but you can also choose to run them in Kubernetes or another container orchestration system.

Generally we like to run the database ring as a different service than the node.js API "web workers" to have the most precision in determining how to scale.

Cassandra itself is a response to Amazon's Dynamo paper and allows you to tune Turbocart performance based on your specific needs for consistency, reliability, and performance (ie, the CAP theorem).

You can run the node.js API endpoints as a "serverless" configuration if you don't mind waiting for those services to start up. For optimal performance we generally prefer to run in a server environment to reduce the chance of users facing a startup delay.


## Relese schedule:

  - Initial release (beta): June 2018
  - Second major release: December 2018

Releases will follow a 6-month release cycle.


## Join the Turbocart Preview program

As we put the finishing touches on version 1 we are inviting store owners and developers to join our technology preview.

For qualifining sites we will help you with migrating existing
data and get your content ready for launch. For others, we will help answer questions. We also welcome code review.

We are also looking for help putting final touches on the documentation site which will help developers and users get started with the service.

Email the Kafei Interactive team to get access to the technology preview: turbocart-preview@kafei.ca.


## Copyright and License

Licence is MIT.

Work is sponsored by Kafei Interactive Inc.

©2018 Ryan Weal, Kafei Interactive Inc.
