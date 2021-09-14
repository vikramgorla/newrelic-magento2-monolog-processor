# New Relic Magento 2 Monolog Processor
This is an extension of NewRelic PHP Monolog Enricher to add in context logging capabilities for Magento 2.

This only implements Processor Class to add the contextual metadata required for New Relic logs in context to operate.¨

Handler class is not implemented on purpose to prevent additional overhead to transactions and not wait to send logs to New Relic logs API endpoint, you can continue to use any existing log forwarders to send logs to New Relic.

Read more about New Relic logs in context here : 
[New Relic PHP: Configure logs in context](https://docs.newrelic.com/docs/logs/enable-log-management-new-relic/configure-logs-context/configure-logs-context-php/#php-monolog)
