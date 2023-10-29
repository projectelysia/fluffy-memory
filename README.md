# First Bus

First Bus API Reverse Engineer Attempt using Burp Suite and Version 5.5.0 of the [iOS App](https://apps.apple.com/gb/app/first-bus/id566586379)

## HTTP API

First has a regular HTTP API which can be used to get static details like stop details, route details, departure details and streaming details.

### Variables

| Name                    | Description                                                                | Example                   |
| ----------------------- | -------------------------------------------------------------------------- | ------------------------- |
| `ATCO_ID`               | An ATCO ID for a bus / train stop                                          | `490010928W`              |
| `Routing_DepartureTime` | Set by the pre-process script to the current time URL encoded              | `2023-09-21T21%3A47%3A00` |
| `HOME_LAT`              | The latitude of your home location                                         | `51.5074`                 |
| `HOME_LON`              | The longitude of your home location                                        | `-0.1278`                 |
| `ORIGIN`                | The lattitude and longitude of where routing should start from URL encoded | `51.5074%2C-0.1278`       |
| `DESTINATION`           | The lattitude and longitude of where routing should end URL encoded        | `51.5074%2C-0.1278`       |
| `PROVIDER_CODE`         | The codename of the company running the service                            | `tfl`                     |
| `ROUTE_NUMBER`          | The number of the route you want to get the route details for              | `N9`                      |

## WS API

First also has a WebSocket streaming API to allow you to subscribe to bus travel events like location, capacity and extended bus details as they happen.

The WS API requires an `Authorization` header with a bearer token. The token changes every so often but it can be obtained by sending a `GET` request to the `Get WS Auth` endpoint in the HTTP API.

### Body

The operator code is the codename of the company running the service. For example, `tfl` for Transport for London.

```json
{
	"id": "22eeac17-edbb-4760-ae57-11182efd8a20",
	"jsonrpc": "2.0",
	"method": "configuration",
	"params": {
		"filters": [
			{
				"direction": "inbound",
				"operator": "TFL",
				"service": "1"
			}
		],
		"max_lat": 0,
		"max_lon": 0,
		"min_lat": 0,
		"min_lon": 0,
		"limit": 50
	}
}
```
