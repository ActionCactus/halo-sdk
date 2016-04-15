Welcome to the Halo SDK
------------------------

This is not the actual Halo project repository. If your looking for the core Halo 
application take a hop over to [here](https://github.com/ff36/halo-core).

This repository is dedicated to the API definition used to generate SDKs for 
Halo in your desired language. Due to the intense nature of maintaining SDKs in 
multiple languages we've opted to use the amazing SDK generators that exist and 
instead maintain the API definitions themselves.


Building a Halo SDK
-------------------------------
#### Download

The easiest way to get the SDK in the language of your choice is to get it from here:
<script type='text/javascript' async src='https://apimatic.io/js/apimatic-widget.js'></script><div id='apimatic-widget' data-apikey='IuEH8uoLMgm15CIH9eU-YGcm1CrjSH1aG7UyDW-uIC4qBa2J7iyEsKOYM0xaHX_q'></div>

If you cant find the a specific language then the next best option is to grab the definition.
You will need to select the API definition file that best suits your needs. We currently 
support blueprints, apimatic and swagger 2.0. Between these you can generate an SDK in 
more than 30 languages which seems pretty awesome.

Which definition you use will primarily depend on the target language for your SDK and 
your own personal preference.

#### Usage

We intend to produce a wiki with detailed guides. However, as a quick start guide you will need to
select an SDK generator. For now lets go with APIMatic. Head over to the [APIMatic](https://apimatic.io/)
website and create a free account if you don't already have one. 

On your account dashboard, click on **Import** and select the **api-matic.json** definition you 
downloaded for here. Once the definition has completed its import click on **Generate** and select 
the language you would like to generate the SDK in. 

Currently they target platforms are;
 - C#
 - Objective C
 - Android
 - Java
 - PHP
 - Python
 - AngularJS
 - Javascript
 - Ruby


#### Need help?

Currently we recomend that you visit your SDK generating service for support. This repo is just 
dedicated to maintaining the definition files and we are unlikely to change that any time soon.


Helping Halo
----------------

#### Found a bug

If you found a repeatable bug, and you are sure that the bug is specifically to do with the API definition, 
then be sure to [search existing issues](https://github.com/ff36/halo-sdk/issues) first.
If the bug relates to Halo or the API itself then please head on over to the [Halo repository](https://github.com/ff36/halo-core) 
and follow the guidlines relating to bug filling. Include steps to consistently reproduce the problem, 
actual vs. expected results, screenshots, and your OS and Halo version number.