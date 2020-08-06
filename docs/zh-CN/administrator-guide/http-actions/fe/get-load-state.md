---
{
    "title": "Get Load State",
    "language": "zh-CN"
}
---

<!-- 
Licensed to the Apache Software Foundation (ASF) under one
or more contributor license agreements.  See the NOTICE file
distributed with this work for additional information
regarding copyright ownership.  The ASF licenses this file
to you under the Apache License, Version 2.0 (the
"License"); you may not use this file except in compliance
with the License.  You may obtain a copy of the License at

  http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing,
software distributed under the License is distributed on an
"AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
KIND, either express or implied.  See the License for the
specific language governing permissions and limitations
under the License.
-->

# Get Load State

## Request

`GET /api/<db>/get_load_state`

## Description

返回指定label的导入事务的状态
    
## Path parameters

* <db>

    指定数据库

## Query parameters

* `label`

    指定导入label

## Request body

无

## Response

```
{
	"msg": "success",
	"code": 0,
	"data": "VISIBLE",
	"count": 0
}
```

如label不存在，则返回：

```
{
	"msg": "success",
	"code": 0,
	"data": "UNKNOWN",
	"count": 0
}
```
    
## Examples

1. 回去指定label的导入事务的状态。

    ```
    GET /api/example_db/get_load_state?label=my_label
    
    {
    	"msg": "success",
    	"code": 0,
    	"data": "VISIBLE",
    	"count": 0
    }
    ```