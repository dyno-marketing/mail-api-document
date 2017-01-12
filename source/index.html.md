---
title: Dyno Email Marketing API Reference

language_tabs:
- curl
- java
- python
- php

toc_footers:
  - <a href='http://mail.dyno.me/#/account/settings'>Sign Up for a Developer Key</a>
  - Powered by Dyno Email Marketing

includes:
  - errors

search: true
---

# Introduction

Welcome to the Dyno Email Marketing API! You can use our API to access information on various objects in our system.

We have language bindings in Curl, Java, Python, Php ! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.


# Enviroment
Production: api.mail.dyno.me:19000	


# Authentication

To authorize, use this header in your request:

`User-Api-Key:dyno`

Make sure to replace `dyno` with your API key.

You can register a new API key at our [setting module](http://mail.dyno.me/#/account/settings)


# API convention

## Request
Request must set header **User-Api-Key**

PUT & POST request must set header **Content-Type** to **application/json**

Find & Count request must based on flat json to support dynamic filtering, listing
Our api support following type with operations

**String**

* Equal
	
* Like
	
		Like: like
		Like ignore case: like_ignore_case
		Like regex: like_regex
		
* Not Like
	
		Not Like: not_like
		Not Like ignore case: not_like_ignore_case
		Not Like regex: not_like_regex
		
* In: in
	
* Not in: not_in
	
* Sample: 
	
		Equal: {"username":"username"}
		Like: "email":{"like":"thanhdd"}
		In: “id”: {“in”: “123,234”}

**Number**

* Equal: eq
	
* Greater than: gt

* Greater than or equal: gte

* Less than: lt

* Less than or equal: lte

* Sample: {"created":{"gte":1439054168}}

**Select specific fields**

	application_fields: 
	Type: Json array
	Sample: “application_fields” : [“id”, “username”]

**Paging**

	application_limit
	application_offset

**Order**

	application_order_by: <field_name>
	application_order_direction: asc | desc


## Response 

> HTTP Code 200

```json
{
	"has_error": false,
	"error_code": "",
	"data": {
		"user_id":"4d1b9220-5a43-11e6-ae4a-6e8264809144"
	}
}
```

> HTTP Code 500

```json
{
	"has_error": true,
	"error_code": "123”
	"error message": "RESOURCE NOT FOUND"
}
```

# Template
## Get
### HTTP Request
`GET http://api.mail.dyno.me:19000/templates/:id`
### Query Parameters
Parameter | Default | Description
--------- | ------- | -----------
id | | Object id
> The above command returns JSON structured like this:
```json
```

## Create
### HTTP Request
`POST http://api.mail.dyno.me:19000/templates `
> The above command returns JSON structured like this:
```json
```

## Change info
### HTTP Request
`PUT http://api.mail.dyno.me:19000/templates/:id`
### Query Parameters
Parameter | Default | Description
--------- | ------- | -----------
id | | Object id
> The above command returns JSON structured like this:
```json
```

## Delete
### HTTP Request
`DELETE http://api.mail.dyno.me:19000/templates/:id`
### Query Parameters
Parameter | Default | Description
--------- | ------- | -----------
id | | Object id
> The above command returns JSON structured like this:
```json
```

## Find
### HTTP Request
`POST http://api.mail.dyno.me:19000/templates/find`
> The above command returns JSON structured like this:
```json
```

## Count
### HTTP Request
`POST http://api.mail.dyno.me:19000/templates/count`
> The above command returns JSON structured like this:
```json
```


# Lists
## Get
### HTTP Request
`GET http://api.mail.dyno.me:19000/lists/:id`
### Query Parameters
Parameter | Default | Description
--------- | ------- | -----------
id | | Object id
> The above command returns JSON structured like this:
```json
```

## Create
### HTTP Request
`POST http://api.mail.dyno.me:19000/lists`
> The above command returns JSON structured like this:
```json
```

## Change info
### HTTP Request
`PUT http://api.mail.dyno.me:19000/lists/:id`
### Query Parameters
Parameter | Default | Description
--------- | ------- | -----------
id | | Object id
> The above command returns JSON structured like this:
```json
```

## Delete
### HTTP Request
`DELETE http://api.mail.dyno.me:19000/lists/:id`
### Query Parameters
Parameter | Default | Description
--------- | ------- | -----------
id | | Object id
> The above command returns JSON structured like this:
```json
```

## Find
### HTTP Request
`POST http://api.mail.dyno.me:19000/lists/find`
> The above command returns JSON structured like this:
```json
```

## Count
### HTTP Request
`POST http://api.mail.dyno.me:19000/lists/count`
> The above command returns JSON structured like this:
```json
```


# Campaigns
## Get
### HTTP Request
`GET http://api.mail.dyno.me:19000/campaigns/:id`
### Query Parameters
Parameter | Default | Description
--------- | ------- | -----------
id | | Object id
> The above command returns JSON structured like this:
```json
```

## Create
### HTTP Request
`POST http://api.mail.dyno.me:19000/campaigns `
> The above command returns JSON structured like this:
```json
```

## Change info
### HTTP Request
`PUT http://api.mail.dyno.me:19000/campaigns/:id`
### Query Parameters
Parameter | Default | Description
--------- | ------- | -----------
id | | Object id
> The above command returns JSON structured like this:
```json
```

## Delete
### HTTP Request
`DELETE http://api.mail.dyno.me:19000/campaigns/:id`
### Query Parameters
Parameter | Default | Description
--------- | ------- | -----------
id | | Object id
> The above command returns JSON structured like this:
```json
```

## Find
### HTTP Request
`POST http://api.mail.dyno.me:19000/campaigns/find`
> The above command returns JSON structured like this:
```json
```

## Count
### HTTP Request
`POST http://api.mail.dyno.me:19000/campaigns/count`
> The above command returns JSON structured like this:
```json
```
	
# Campaigns process

## Start campaign
### HTTP Request
`POST http://api.mail.dyno.me:19000/campaign_process/init`
### Parameters
Parameter | Default | Description
--------- | ------- | -----------
campaign_id | | campaign id
iso_start_time  | | (yyyy-MM-dd'T'HH:mm:ss): optional
time_zone | | optional 
subject | |  optional
from_name | | optional
from_email | | optional
preview_message | | optional
> The above command returns JSON structured like this:
```json
```

## Update & resume campaign
### HTTP Request
`POST http://api.mail.dyno.me:19000/campaign_process/update_and_resume`
### Parameters
Parameter | Default | Description
--------- | ------- | -----------
campaign_id | | campaign id
subject | |  optional
from_name | | optional
from_email | | optional
preview_message | | optional
> The above command returns JSON structured like this:
```json
```

## Reschedule campaign
### HTTP Request
`POST http://api.mail.dyno.me:19000/campaign_process/reschedule`
### Parameters
Parameter | Default | Description
--------- | ------- | -----------
campaign_id | | campaign id
iso_start_time  | | (yyyy-MM-dd'T'HH:mm:ss): optional
time_zone | | optional 
subject | |  optional
from_name | | optional
from_email | | optional
preview_message | | optional
> The above command returns JSON structured like this:
```json
```

## Cancel schedule
### HTTP Request
`POST http://api.mail.dyno.me:19000/campaign_process/cancel_schedule`
### Parameters
Parameter | Default | Description
--------- | ------- | -----------
id | | Object id
> The above command returns JSON structured like this:
```json
```

## Stop campaign
### HTTP Request
`POST http://api.mail.dyno.me:19000/campaign_process/stop`
### Parameters
Parameter | Default | Description
--------- | ------- | -----------
id | | Object id
> The above command returns JSON structured like this:
```json
```

## Pause campaign
### HTTP Request
`POST http://api.mail.dyno.me:19000/campaign_process/pause`
### Parameters
Parameter | Default | Description
--------- | ------- | -----------
id | | Object id
> The above command returns JSON structured like this:
```json
```

## Resume campaign
### HTTP Request
`POST http://api.mail.dyno.me:19000/campaign_process/resume`
> The above command returns JSON structured like this:
```json
```