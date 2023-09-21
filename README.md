# fluffy-memory

First Bus API Reverse Engineer Attempt using Burp Suite and Version 5.5.0 of the [iOS App](https://apps.apple.com/gb/app/first-bus/id566586379)

## Variables

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
