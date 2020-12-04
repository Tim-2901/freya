# Nomenclature
__topic__: topic as in mqtt <p>
__module__: module in a physical sense, so each module gets its own esp with sensors <p>
__#__: wildcard in mqtt <p>

# Data Storage
Data will be published and then retained in the Broker until we get a new message. Also saving to Database for future uses <p>
Publish config? (retained messages) <p>
Publish config to redis? <p>
Does MQTT saves datetime of last received value or do we need a client keeping track of that? Is it even impotant? <p>



# Node
__name__: name of the node <p>
__type__: type of the node (e.g. esp32) <p>
__intervall__: Interval at which sensor readings are taken <p>
## Sensor Worker
Spawns new thread that handles a number of sensors <p>
### Sensor
__topic__ optional <p>
__type__ <p>
__pin__ <p>
~~hardwire in firmware or~~ do some kind of functional programming <p>
__topic__ as: <p>
~~{module}/{type}/{pin} -msg: #~~  <p>
{module}/{type}  -msg: {pin}<p>
maybe generate __topic__ automatically. <p>
do we need a name or do we just use the topic? <p>


## Actuator Worker
Spawns a new thread that handles a certain amount of actuators <p>

### Actuator
__topic__ optional <p>
__type__ <p>
__pin__ <p>

__topic__ as: <p>
{module}/{type} -msg: pin, on/off <p>
  
## Trigger Worker
Spawns a new thread that handles a certain amount of triggers <p>
### Trigger
__name__ <p>
__topic__ <p>
__condition__ <p>
__threshold__ <p>
__hysteresis__ <p>
__action__ <p>

## Action Worker
Spawns a new thread that handles a certain amount of actions <p>

### Action
__name__ <p>
__topic__ <p>
__key__ <p>










  
# FAQs
  
~~own thread for every sensor or for every worker only?~~ <p>
own worker for each module so module == worker YES<p>
use own thread for sensor worker, relay worker, etc. YES <p>
~~make module a superclass of worker, so we can create as many workers per module as we want and make worker == thread~~ <p>
in a config based system can we archive hotswap or do we need to restart every time we make a change?<p>
is restarting bad anyways? <p>
Do we utiliese DACs? YES for Light <p> 
Can we duplicate Modules with the same config since several modules will have same sensor/actuators? <p>
Is it smart to do pressure as functional programming over the internetz since it need to work in realtime and if we have a lag shit is hitting the fan.(jk pump has overpressure turnoff)(auto turn off on dc?) <p>
combine trigger and action or do it as two things <p>



# Later

Add support for displays <p>
Add support for buttons, potentiometers... <p>