# Predicting-response-times-of-the-Paris-Fire-Brigade-vehicles-by-Paris-Fire-Brigrade

The response time is one of the most important factors for emergency services because their ability to save lives and rescue people depends on it.
A non-optimal choice of an emergency vehicle for a rescue request may lengthen the arrival time of the rescuers and impact the future of the victim. This choice is therefore highly critical for emergency services and directly relies on their ability to predict precisely the arrival time of the different units available.
Input parameters (x_train.csv and x_test.csv):
[ID] emergency vehicle selection: identifier of the selection instance of an emergency vehicle for an intervention
Intervention
intervention: identifier of the intervention
Alert reason
alert reason category (category): alert reason category
alert reason (category): alert reason
Address
intervention on public roads (boolean): 1 when it concerns an intervention on public roads, 0 otherwise
floor (int): floor of the intervention
location of the event (category): qualifies the location of the emergency request, for example: entrance hall, boiler room, motorway, etc.
longitude intervention (float): approximate longitude of the intervention address
latitude intervention (float): approximate latitude of the intervention address
Emergency vehicle
emergency vehicle: identifier of the emergency vehicle
emergency vehicle type (category): type of the emergency vehicle
rescue center (category): identifier of the rescue center to which belong the vehicle (parking spot of the emergency vehicle)
selection time (datetime): selection time of the emergency vehicle
date key selection (int): selection date in YYYYMMDD format
time key selection (int): selection time in HHMMSS format
State of the emergency vehicle preceding its selection for an intervention
Operational status of the vehicle preceding its selection
status preceding selection (category): status of the emergency vehicle prior to selection. An emergency vehicle is in various statuses during an intervention:
Selection - selection of the emergency vehicle by the rescue commitment application
Departed - the vehicle starts its route to the location of the emergency request
Presented - the vehicle arrives at the location of the request
Hospital transportation - the vehicle starts its transport of a victim to hospital
Hospital arrival - the vehicle arrives at the hospital
Leaving hospital - the vehicle leaves the hospital
Returned - the vehicle has returned to its parking spot
Leave the premises - because the vehicle can also simply leave the scene of an intervention without having to transport any victim
Not available - for various reasons the vehicle can be in an unavailable position
Not relevant - statutes without interest
delta status preceding selection-selection (int): number of seconds before the vehicle was selected when its previous status was entered
departed from its rescue center (boolean) : 1 when the vehicle departed from its rescue center (emergency vehicle parking spot), 0 otherwise
GPS position of the vehicle before departure
longitude before departure (float): longitude of the position of the vehicle preceding his departure
latitude previous departure (float): latitude of the position of the vehicle preceding his departure
delta position gps previous departure-departure (int): number of seconds before the selection of the vehicle where its GPS position was recorded (when not parked at its emergency center)
GPS tracks
GPS tracks departure-presentation (float pair list): successive GPS positions (*longitude,latitude;longitude,latitude,* etc.) of the vehicle between departure and presentation. This information is for informational purposes to study vehicle behaviors. (The beacons, emitting the GPS positions of vehicles, are currently not always lit)
GPS tracks departure-presentation datetime (datetime list): datetime associated with successive GPS positions between the departure and the presentation of the vehicle.
Estimated route
OSRM estimated route (json object): service route response of an OSRM instance (http://project-osrm.org/docs/v5.15.2/api/#route-service) setup with the Ile-de-France OpenStreetMap data
OSRM estimated distance (float): distance calculated by the OSRM route service
OSRM estimated duration (float): transit delay calculated by the OSRM route service
Output parameters (y_train.csv and y_test.csv):
[ID] emergency vehicle selection: identifier of a selection instance of an emergency vehicle for an intervention
[TO PREDICT] delta selection-departure (int): elapsed time in seconds between the selection and the departure of the emergency vehicle
[TO PREDICT] delta departure-presentation (int): elapsed time in seconds between the departure of the emergency vehicle and its presentation on the intervention scene
[TO PREDICT] delta selection-presentation (int): elapsed time in seconds between the selection of the emergency vehicle and its presentation on the intervention scene (delta selection-departure + delta departure-presentation)
Supplementary files (x_train_additional_file.csv and x_test_additional_file.csv):
[ID] emergency vehicle selection: identifier of a selection instance of an emergency vehicle for an intervention
OSRM estimate from last observed GPS position (json object): service route response from last observed GPS position of an OSRM instance (http://project-osrm.org/docs/v5.15.2/api/#route-service) setup with the Ile-de-France OpenStreetMap data
OSRM estimated distance from last observed GPS position (float): distance (in meters) calculated by the OSRM route service from last observed GPS position
OSRM estimated duration from last observed GPS position (float): transit delay (in seconds) calculated by the OSRM route service from last observed GPS position
time elapsed between selection and last observed GPS position (float): in seconds
updated OSRM estimated duration (float): time elapsed (in seconds) between selection and last observed GPS position + OSRM estimated duration from last observed GPS position
