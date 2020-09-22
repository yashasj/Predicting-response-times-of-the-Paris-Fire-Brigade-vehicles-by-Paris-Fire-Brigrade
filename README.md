# Predicting-response-times-of-the-Paris-Fire-Brigade-vehicles-by-Paris-Fire-Brigrade

##The response time is one of the most important factors for emergency services because their ability to save lives and rescue people depends on it.
A non-optimal choice of an emergency vehicle for a rescue request may lengthen the arrival time of the rescuers and impact the future of the victim. This choice is therefore highly critical for emergency services and directly relies on their ability to predict precisely the arrival time of the different units available.

List of Attributes and its description
•	Emergency vehicle selection : Identifying of selection instance of an emergency vehicle for an intervention                                                                                                                           
•	Alert reason category (category):It has various categories from 1 to 9
•	Intervention on public roads(boolean) : whether the intervention is on public road or not 
•	 Floor (int):floor in which intervention happened 
•	 Location of the event(category) :it defines where the event has taken place ex: entrance    hall , boiler room , motorway etc
•	Longitude intervention(float) : approximate longitude of the intervention address
•	Latitude intervention (float) :approximate latitude of the intervention address
•	Emergency vehicle type (category) :type of the emergency vehicle
•	Rescue centre (category) :identification of rescue centre to which it belongs 
•	Date key selection (int) :selection date in YYYYMMDD format
•	Time key selection (int) :selection time in HHMMSS format
•	Status preceding selection: status of the emergency vehicle prior selection 
•	 Departed from its rescue centre (boolean) :whether the vehicle has departed from its rescue centre or not 
•	OSRM estimated distance (float) :distance calculated by the OSRM route service
•	OSRM estimated duration (float) :transit delay calculated by the OSRM route service

Challenge site: https://challengedata.ens.fr/participants/challenges/21/
