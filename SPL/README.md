# Splunk Processing Language (SPL)

## Search Command

### Search For Specific Error Messages

You can search for specific words in the search bar.
For example:
```index=botsv3 ("error" OR "failed" OR "failure")```

### Filter Events by Source IP Address

You can search for specific IP addresses either in the source field or not.
For example:
```index=botsv3 src_ip="172.16.0.178"```

### Search For Login Failures In a Specific Time Range

You can search for events witin a certain time frame.
For example:
```index=botsv3 EventCode=4625 earliest=-15y latest=-5y```

### Filter by Event Type and Status Code

Typically event types are part of a data administrative tool. If you're going to put things into data models, they're going to come with an event type.
For example:
```index=botsv3 eventtype="cpu" cpu="all"```

### Combine Search with Wildcards For Flexible Filtering

You can use wildcards for search flexibility.
For example:
```index=botsv3 user="*admin*"```
