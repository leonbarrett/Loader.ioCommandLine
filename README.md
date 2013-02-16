What
===

This is a simple tool to run and view load test using the Loader.io service.

You'll need an API key from Loader.io first

How
===

To run a load test starting with 0 connections, up to 10 connections over a 30 section period against http://thisisleon.co.uk try this:

`$ loaderio -m test:create -u http://thisisleon.co.uk -l 0-10-30 --name Demo`

Installation
=======

Ensure you have PHP installed as CLI. Run `php -v` to check

Download the file and make it executable

`chmod a+x loaderio`

Either place it in your path, or add to your path.

`echo 'export PATH=YOURPATHHERE:$PATH' >> ~/.profile`

When using the tool for the 1st time you will be prompted to add in your Loader.io api key.

You can also add a loader_cli.config to your home directory containing:

`[account_settings]
api_key = API_KEY

Type `loaderio --help` for help.

Methods
=====

`$loaderio -m test:create -u URL -l LOAD -name NAME` - will start a load test against the specified URL. Load test settings in the form [from]-[to]-[time_in_sec] (ex: 0-200-60 from 0 connections to 200 connections during 60 seconds)

`$loaderio -m test:list` - return a list of tests

`$loaderio -m test:view -t TEST_ID` - view results for a test

`$loaderio -m app:list` - return a list of apps

`$loaderio -m app:create -h HOST_NAME` - create an app with the specified host name

`$loaderio -m app:verify -h HOST_NAME -v {url|dns}` - verify an app

`$loaderio -m app:view -h HOST_NAME` - view an app


Parameters
==========

These are global parameters that will work across the methods:

* -m or --method 		= the method name. This is required to actually do anything. See above for a list of available methods
* -h or --host 			= hostname/app ID to test
* -v or --verify 		= method for verification (url or dns)
* -u or --url			= url to test
* -l or --load			= load test settings in the form [from]-[to]-[time_in_sec] (ex: 0-200-60 from 0 connections to 200 connections during 60 seconds)
* -n or --name			= test name
* -t or --test			= test ID


Thanks
=====

Thanks to https://github.com/pete-otaqui/ClipClop for the library to parse the command line options