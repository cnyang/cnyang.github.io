---
layout: post
title: "Flot Example"
categories:
  - Note
tags: 
  - Flot
---
## Flot data example

```php
$data = [];
for ($i = 0; $i < 5; $i += 1) {
    $data[] = [$i, $i * 3];
}
$data2 = [];
for ($i = 0; $i < 5; $i += 1) {
    $data2[] = [$i, $i * 4];
}
$retValue = json_encode(array("label" => $type, "data" => $data, "label2" => $period, "data2" => $data2));
return $retValue;
```

```javascript
function onDataReceived(series) {
        var dataset = {
          label: series.label,
          data: series.data
        };

        var dataset2 = {
          label: series.label2,
          data: series.data2
        };

        $.plot("#chart", [dataset, dataset2]);
      }

```
