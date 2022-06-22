## Craft Activity Log

This plugin provides a detailed activity log for incoming web requests.

### Requirements

This plugin requires Craft CMS 4.x or later.

### Installation

1. Include the package:

```
composer require matfish/craft-activity-log
```

2. Install the plugin:

```
php craft plugin/install activity-log
```

### Usage

Once the plugin is installed Craft will start recording all requests, excluding Control Panel AJAX requests (except for Login request).
Data points include:
* URL
* Action (if it is an action request)
* User
* Site
* Query
* Payload 
* IP
* User agent
* Method (GET,POST,PUT or DELETE)
* Is CP (Control Panel) Request?
* Is AJAX request?
* Response Code
* Execution Time
* Timestamp (Created at)

The user can control which request types to record under the Settings page.

Requests can be viewed and filtered under the Activity Log page.
Click the "Columns" button to add or remove columns from the table on the fly. 
Note that most columns have a dedicated filter attached to them (except for date range at the top of the table).
Click the "+" sign on the left-hand side of each row to expand a child row containing the full request data.

### Pruning Data

You can prune (delete) data before that last X days using the following console command:
```bash
php craft activity-log/logs/prune --days=30
```
If omitted the `days` option defaults to 30 days.

### License

You can try Activity Log in a development environment for as long as you like. Once your site goes live, you are
required to purchase a license for the plugin. License is purchasable through
the [Craft Plugin Store](https://plugins.craftcms.com/activity-log).

For more information, see
Craft's [Commercial Plugin Licensing](https://craftcms.com/docs/4.x/plugins.html#commercial-plugin-licensing).
