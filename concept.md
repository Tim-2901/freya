## Nomenclature
__topic__: topic as in mqtt <p>
__module__: module in a physical sense, so each module gets its own esp with sensors <p>
__#__: wildcard in mqtt

## Workers
__module__: module id <p>

### Sensor Worker
Spawns new thread that handles all sensors of a certain module
__time__ <p>

#### Sensor
__topic__ <p>
__type__ <p>
__pin__ <p>
~~hardwire in firmware or~~ do some kind of functional programming <p>
__topic__ as: <p>
{module}/{type}/{pin} -msg: # <p>
~~{module}/{type}  msg: {pin}~~ <p>
maybe generate __topic__ automatically. <p>
do we need a name or do we just use the topic? <p>


### Relay Worker
Spawns a new thead that handles all relays of a certain module <p>

#### Relay
__topic__ <p>
__type__ <p>
__pin__ <p>

__topic__ as: <p>
{module}/{type}/{pin} -msg: on/off <p>
  
  
  
~~own thread for every sensor or for every worker only?~~ <p>
own worker for each module so module == worker <p>
use own thread for sensor worker, relay worker, etc. <p>
