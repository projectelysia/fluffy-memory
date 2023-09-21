# fluffy-memory

First Bus API Reverse Engineer Attempt using Burp Suite and Version 5.5.0 of the [iOS App](https://apps.apple.com/gb/app/first-bus/id566586379)

## Variables

| Name                    | Description                                                                        |
| ----------------------- | ---------------------------------------------------------------------------------- |
| `ATCO_ID`               | An ATCO ID for a bus / train stop                                                  |
| `Routing_DepartureTime` | Set by the pre-process script to the current time URL encoded                      |
| `HOME_LAT`              | The latitude of your home location                                                 |
| `HOME_LON`              | The longitude of your home location                                                |
| `ORIGIN`                | The lattitude and longitude of where routing should start from URL encoded         |
| `DESTINATION`           | The lattitude and longitude of where routing should end URL encoded                |
| `PROVIDER_CODE`         | The codename of the company running the service; `eg tfl for Transport for London` |
| `ROUTE_NUMBER`          | The number of the route you want to get the route details for                      |
