# SmartPx Integration Document 

## Integration Step 
### Step 1
Insert the script bellow into the `<head>` element of client’s website
```html
<script src="https://smartpx.io/sdk/smartpx.min.js?v=1.2"></script>
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

7: Meganet

8: NCT

9: Zalo

10: VNG

11: Criteo

12: Acxiom

13: Viettel Media

14: Bibibook (Mobifone 3G)

# Import transaction data api
Each day imports event data from the day before
## Import clicks
Path: /eway/clicks
* Method: Post
* Parameter:
  - data: json array contains event data
  - date: date of events (format: yyyy-mm-dd)
  - hour: hour of events (format: HH: 9am -> 09)
* Sample:
```
curl -X POST \
  http://185.12.178.57:19501/eway/clicks \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -d '{"date":"2017-09-11", "hour":"09", "data":[{"conversion_id":"12"}]}'
```
* Sample response: 
```json
{"has_error":false}
```
* Notes: time is utc

## Import conversions
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
