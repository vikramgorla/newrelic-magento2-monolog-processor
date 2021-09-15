# New Relic Magento 2 Monolog Processor
This is an extension of NewRelic PHP Monolog Enricher to add in context logging capabilities for Magento 2.

This only implements Processor Class to add the contextual metadata required for New Relic logs in context to operate.

Handler class is not implemented on purpose to prevent additional overhead to transactions and not wait to send logs to New Relic logs API endpoint, you can continue to use any existing log forwarders to send logs to New Relic.

If you dont have any existing log forwarders and can afford overhead to sychronously push logs to New Relic (or to use handler on non production environments where you can afford latency), use the handler extension available here [vgorla/newrelic-magento2-monolog-handler](https://github.com/vikramgorla/newrelic-magento2-monolog-handler) which will automatically install processor (this extension) if you use composer based on the declared dependacy.

### Installation

Using Composer :

```
$ composer require vgorla/newrelic-magento2-monolog-processor
```

Enable Distributed Tracing :

[Enable Distributed Tracing](https://docs.newrelic.com/docs/distributed-tracing/enable-configure/language-agents-enable-distributed-tracing/#php-config) in your New Relic Configuration file (normally newrelic.ini), enabling infinite tracing is not mandatory for in context logs to work.
```
newrelic.distributed_tracing_enabled = true
newrelic.span_events_enabled = true
```
Read more about New Relic logs in context here : 
[New Relic PHP: Configure logs in context](https://docs.newrelic.com/docs/logs/enable-log-management-new-relic/configure-logs-context/configure-logs-context-php/#php-monolog)