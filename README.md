# Analytics

## Fork of Original Repo by TestNotice

Port of Laravel 3 bundle [lordcoste/analytics-s2s](https://github.com/lordcoste/analytics-s2s) for Laravel 4

[![Build Status](https://travis-ci.org/thujohn/analytics-l4.png?branch=master)](https://travis-ci.org/thujohn/analytics-l4)

## Configuration

Run `php artisan config:publish thujohn/analytics` and modify the config file with your own informations.

## Usage
Querying the API for visits and pageviews in the last week.

More information about this calling the Google Analytics API can be found here https://developers.google.com/apis-explorer/#s/analytics/v3/analytics.data.ga.get
A list of all Google Analytics metrics can be found here https://developers.google.com/analytics/devguides/reporting/core/dimsmets
```php
$site_id = Analytics::getSiteIdByUrl('http://github.com/'); // return something like 'ga:11111111'

$stats = Analytics::query($site_id, '7daysAgo', 'yesterday', 'ga:visits,ga:pageviews');
```
