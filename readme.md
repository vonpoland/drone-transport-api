# This is FAKE drone api.

## Prerequisite

`npm install serverless mocha -g`

## Test

`npm test`

## How to run api offline?

```bash
npm install
sls dynamodb install
serverless offlne start --migrate
```


## Usage

### Create a drone

```bash
curl -X POST -H "Content-Type:application/json" http://localhost:3000/drones --data '{ "name": "Thook", "speed": 1, "location": { "lon": 60.161679 ,"lat": 24.957612}}'
```

### List drones
```bash
curl http://localhost:3000/drones
curl http://localhost:3000/drones?fromLat=10&fromLon=12&toLat=10&toLon=12.5
```

### Get the drone by id
```bash
curl http://localhost:3000/drones/{id}
```

### Create booking
```bash
curl -X POST -H "Content-Type:application/json" http://localhost:3000/drones/bookings --data '{  "droneId": "38e6da70-3036-11e7-bbe6-8b20de079d19", "route": {  "from": { "lon": 60.161679 ,"lat": 24.957612}, "to": { "lon": 60.161679 ,"lat": 24.957612}}}'
```

### Update booking
```bash
curl -X PUT -H "Content-Type:application/json" http://localhost:3000/drones/9bc999d0-3035-11e7-89fa-990ea7966214/bookings --data '{   "route": {  "from": { "lon": 70 ,"lat": 80}, "to": { "lon": 71 ,"lat": 72}}}'
```

### Delete booking
```bash
curl -X DELETE http://localhost:3000/drones/38e6da70-3036-11e7-bbe6-8b20de079d19/bookings
```