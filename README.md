![Latest version](https://img.shields.io/github/v/release/magicsunday/webtrees-fan-chart?sort=semver)
![License](https://img.shields.io/github/license/magicsunday/webtrees-fan-chart)
![PHPStan](https://github.com/magicsunday/webtrees-fan-chart/actions/workflows/phpstan.yml/badge.svg)
![PHPCodeSniffer](https://github.com/magicsunday/webtrees-fan-chart/actions/workflows/phpcs.yml/badge.svg)
![CodeQL](https://github.com/magicsunday/webtrees-fan-chart/actions/workflows/codeql-analysis.yml/badge.svg)


<!-- TOC -->
* [Fan chart](#fan-chart)
  * [Installation](#installation)
    * [Manual installation](#manual-installation)
      * [Configuration](#configuration)
      * [Usage](#usage)
    * [Using Composer](#using-composer)
    * [Using Git](#using-git)
  * [Development](#development)
    * [Run tests](#run-tests)
<!-- TOC -->


# Fan chart
This module provides an SVG ancestor fan chart for the [webtrees](https://www.webtrees.net) genealogy application.

![210 Degree chart with opened contextmenu](assets/fan-chart-210-contextmenu.png)
![210 Degree chart with color gradients and hidden empty segments](assets/fan-chart-210-gradient.png)


## Installation
Requires Webtrees 2.2.

There are several ways to install the module. The method using [composer](#using-composer) is suitable
for experienced users, as a developer you can also use [git](#using-git) to get a copy of the repository. For all other users,
however, manual installation is recommended.

### Manual installation
To manually install the module, perform the following steps:

1. Download the [latest release](https://github.com/magicsunday/webtrees-fan-chart/releases/latest) of the module.
2. Upload the downloaded file to your web server.
3. Unzip the package into your ``modules_v4`` directory.
4. Rename the folder to ``webtrees-fan-chart``

If everything was successful, you should see a subdirectory ``webtrees-fan-chart`` with the unpacked content
in the ``modules_v4`` directory.

Now the module has to be activated within Webtrees.

#### Configuration
Go to the control panel (admin section) of your installation and scroll down to the ``Modules`` section. Click
on ``Charts`` (in subsection Genealogy). Enable the ``Fan chart`` custom module (optionally disable the original
installed fan chart module) and save your settings.

![Control panel - Module administration](assets/control-panel-modules.png)

#### Usage
At the charts' menu, you will find a new link called `Fan chart`. Use the provided configuration options
to adjust the layout of the charts according to your needs.

Right-clicking on an individual opens a tooltip providing more detailed information of the current individual.


### Using Composer
Typically, to install with [composer](https://getcomposer.org/), just run the following command from the command line, 
from the root of your Webtrees installation.

``` 
composer require magicsunday/webtrees-fan-chart --update-no-dev
```

The module will automatically install into the ``modules_v4`` directory of your Webtrees installation.

To remove the module run:
```
composer remove magicsunday/webtrees-fan-chart --update-no-dev
```

Then follow the steps described in [configuration](#configuration) and [usage](#usage).

#### Latest version
If you are using the development version of Webtrees (main branch), you may also need to install the development 
version of the module. For this, please use the following command:
```
composer require magicsunday/webtrees-fan-chart:dev-master --update-no-dev
```


### Using Git
If you are using ``git``, you could also clone the current master branch directly into your ``modules_v4`` directory 
by calling:

```
git clone https://github.com/magicsunday/webtrees-fan-chart.git modules_v4/webtrees-fan-chart
```

Then follow the steps described in [configuration](#configuration) and [usage](#usage).


## Development
To build/update the javascript, run the following commands:

```
nvm install node
npm install --unsafe-perm --save-dev
npm run prepare
```

### Run tests
```
composer update
vendor/bin/phpstan analyse --memory-limit=-1 -c phpstan.neon
vendor/bin/phpcs src/ --standard=PSR12
```
