# Nomenclature
__topic__: topic as in mqtt <p>
__module__: module in a physical sense, so each module gets its own esp with sensors <p>
__#__: wildcard in mqtt <p>

# Data Storage
Data will be published and then retained in the Broker until we get a new message. Also saving to Database for future uses <p>
Publish config? (retained messages) <p>
Publish config to redis? <p>
Does MQTT saves datetime of last received value or do we need a client keeping track of that? Is it even impotant? <p>



# Workers
__module__: module id <p>

## Sensor Worker
Spawns new thread that handles a number of sensors <p>
__time__ <p>

### Sensor
__topic__ <p>
__type__ <p>
__pin__ <p>
~~hardwire in firmware or~~ do some kind of functional programming <p>
__topic__ as: <p>
{module}/{type}/{pin} -msg: # <p>
~~{module}/{type}  msg: {pin}~~ <p>
maybe generate __topic__ automatically. <p>
do we need a name or do we just use the topic? <p>


## Relay Worker
Spawns a new thead that handles a certain amount of relays <p>

### Relay
__topic__ <p>
__type__ <p>
__pin__ <p>

__topic__ as: <p>
{module}/{type}/{pin} -msg: on/off <p>
  
## Trigger
Triggers if sth happens e.g. if pressure meats a certain threshold <p>

Is it smart to do pressure as functional programming over the internetz since it need to work in realtime and if we have a lag shit is hitting the fan.(jk pump has overpressure turnoff)(auto turn off on dc?) <p>

## Action
Activated by a Trigger, e.g. Pressure Trigger turning of the pump <p>


combine trigger and action or do it as two things <p>





  
# FAQs
  
~~own thread for every sensor or for every worker only?~~ <p>
own worker for each module so module == worker YES<p>
use own thread for sensor worker, relay worker, etc. YES <p>
~~make module a superclass of worker, so we can create as many workers per module as we want and make worker == thread~~ <p>
in a config based system can we archive hotswap or do we need to restart every time we make a change?<p>
is restarting bad anyways? <p>
Do we utiliese DACs? YES for Light <p> 
Can we duplicate Modules with the same config since several modules will have same sensor/actuators? <p>
