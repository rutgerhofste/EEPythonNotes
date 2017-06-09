# EEPythonNotes
## Lessons learned switching from Javascript to Python API for Earth Engine

Installation etc. was done using information on the ee website (Jan 2017)
 
1. Dictionaries in python are declared using a colon and keys MUST be in quotes e.g. {“foo” : 42}
 
2. In order to print a variable, you have to make the parameter client side instead of server side. Use `.getInfo()` to get the job done. [link](https://developers.google.com/earth-engine/client_server)
 
3. Arguments in methods are not specified in a dictionary format but in a pythonic way: `geometry = ee.Geometry.Polygon(coords = [[0, 0], [10,  0], [10, 10], [0, 10]])` Instead of var `geometry = ee.Geometry.Polygon({coords: [[0, 0], [10,  0], [10, 10], [0, 10]],geodesic:false});`
 
4. Export tasks can be found under `ee.batch.Export` and should also be started using `.start()`
 
5. You can check progress of tasks using `<TASKNAME>.status()`
 
6. Mapping functions client side works according to Python syntax. You should cast type again after mapping. `newVariable = map(function,sequence)`
 

 
7. When exporting, the region has to be client side in JSON format: `region=geometry.getInfo()['coordinates']`
 
8. You can get a tasks list with the following command
`ee.batch.Task.list()`
 
9. Export task function is client side. 
 
10. Use `True`, `False` and `None` instead of `true`, `false` and `null`
 
11. Use retrying library for exponential backoff [link](https://pypi.python.org/pypi/retrying)
 
The following notes are probably no longer relevant now the datalab option is available: 
Want to run python scripts on a virtual machine in the cloud, use compute engine with the following commands:
 
`sudo apt-get update`

`sudo apt-get install libffi-dev libssl-dev python-dev python-pip`

`sudo pip install cryptography google-api-python-client earthengine-api`
 
After that will have to authenticate and transfer the script (gsutil) 
 
Using command line tool (using subprocess and bored by slowness), use google cloud shell and a bash script. 
 

 
 
 
 
 
 
 
 
 
