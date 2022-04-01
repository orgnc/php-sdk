# Organic PHP SDK
PHP SDK for [Organic Platform](https://organic.ly) API Integration

You need an account with Organic in order to connect to the API. If you are interested enhancing your digital media with
the power of Organic, please [contact Organic sales](https://organic.ly/contact/).

## Authentication
You can retrieve your API key from inside the Organic dashboard, under Documentation > Wordpress Plugin. Note that while
the API key is often used for our plugins, it can also be used directly with the SDK here.

![Organic Dashboard API Key](/docs/api-key.png)

Also, almost all actions within the SDK are performed within the context of an individual website. To get the UUID of
the website you want to work with, go to the Documentation > Code Snippet section of your dashboard. The UUID is a bit
difficult to find at the moment, but you can see it in the config string highlighted here after you have selected the
site:

![Organic Dashboard Site UUID](/docs/site-uuid.png)

## Connecting to the API
Organic publishes a GraphQL API endpoint to communicate with. Basic connection works like this:

```php
use Organic\SDK\SDK;

$apiKey = '__FROM_YOUR_DASHBOARD__';
$siteId = '__UUID_FOR_YOUR_WEBSITE__';

$sdk = new SDK( $siteId, $apiKey );
```

## Fetch Your Site's Ads.txt
If you are using Organic Ads on your website and want to pull your managed ads.txt content, you can pull it using:

```php
$myAdsTxt = $sdk->queryAdsTxt();
```