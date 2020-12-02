## Nomenclature
__topic__: topic as in mqtt <p>
__module__: module in a physical sense, so each module gets its own esp with sensors <p>

## Workers

### Sensor Worker

Runs a sensor attached to a esp and gets their reading ever x Seconds to the mqtt broker
__name__ <p>
__topic__ <p>
__time__ <p>
__module__ <p>
__type__ <p>
__pin__ <p>
hardwire in firmware or do some kind of functional programming? <p>
maybe __topic__ as: <p>
{module}/{type}/{pin} msg: read <p>
{module}/{type}  msg: {pin} <p>
maybe generate __topic__ automatically. <p>
own thread for every sensor or for every worker only? <p>
own worker for each module so module == worker <p>
