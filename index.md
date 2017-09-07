# SmartPx Integration Document 

## Integration Step 
### Step 1
Insert the script bellow into the `<head>` element of client’s website
```html
<script src="http://smartpx.io/sdk/smartpx.min.js?v=1.0"></script>
<script type="text/javascript">
	Smartpx.init({
		transaction_id: '123456789',
		custom_fields: {}
	});
</script>
```
## Add source
custom_fields : {"source": "source_id"}

## Source ID:
1: Facebook

2: Google

3: Admicro

4: Massoffer

5: Ants

6: Adflex

# Import transaction data api
Each day imports event data from the day before
## Import clicks
Path: /eway/clicks
* Method: Post
* Parameter:
  - file: contains event data
  - date: date of events in file
* Sample:
```
curl -X POST \
  http://185.12.178.57:19501/eway/clicks \
  -H 'cache-control: no-cache' \
  -H 'content-type: multipart/form-data; boundary=----WebKitFormBoundary7MA4YWxkTrZu0gW' \
  -F file=@test.csv \
  -F date=2017-09-07
```
* Format file:
  - One event per row
  - Format of each row is json: {"click_id":"123213213"}
* Sample response: 
```json
{"has_error":false}
```

## Import conversations
Path: /eway/conversions
* Method: Post
* Sample response: 
```json
{"has_error":false}
```
## Update conversations
Path: /eway/conversions
* Method: PUT
* Sample response: 
```json
{"has_error":false}
```
