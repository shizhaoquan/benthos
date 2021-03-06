---
title: throttle
type: processor
status: stable
categories: ["Utility"]
---

<!--
     THIS FILE IS AUTOGENERATED!

     To make changes please edit the contents of:
     lib/processor/throttle.go
-->

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';


Throttles the throughput of a pipeline to a maximum of one message batch per
period. This throttle is per processing pipeline, and therefore four threads
each with a throttle would result in four times the rate specified.

```yaml
# Config fields, showing default values
throttle:
  period: 100us
```

The period should be specified as a time duration string. For example, '1s'
would be 1 second, '10ms' would be 10 milliseconds, etc.

## Fields

### `period`

The period to throttle to.


Type: `string`  
Default: `"100us"`  


