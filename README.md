# ais_json

This is a simple AIS parser that reads a UDP stream from [aisdispatcher](http://www.aishub.net/ais-dispatcher) parses it into JSON and posts the output via http to the aprs.fi endpoint.

requires libais: https://pypi.org/project/libais/

aprs.fi accepts the ais message in the following format:

```json
{
 "protocol": "jsonais",
 "encodetime": "20131231235959",
 "groups": [
  {
   "path": [ { "name": "MYACCOUNT", "url": "http://www.example.com/" } ],
   "msgs": [
    {
     "msgtype": "18",
     "mmsi":123456789,
     "callsign":"C4LL5GN",
     "shipname":"MY BOAT NAME",
     "shiptype":37,
     "status":5,
     "speed":0,
     "lon":0.00000,
     "lat":0.00000,
     "course":0.0,
     "heading":0.0,
     "length":12,
     "width":2,
     "ref_front":6,
     "ref_left":1,
     "draught":1,
     "rxtime":"20131231235959"
    }
   ]
  }
 ]
}
```

## usage:
edit settings.py to include your aprs.fi account name and SeCrEtKeY

Your AIS SeCrEtKeY can be found in https://aprs.fi/account/ under "AIS password"


## install

* git clone https://github.com/hsiboy/ais_json.git
* pip install libais
* pip install termcolor
* $ cd ais_json
* $ ./ais_json.py &



