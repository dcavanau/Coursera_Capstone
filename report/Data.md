# Data
The data used to train and evaluate the model is the collision data set from the SDOT Traffic Management Division, Traffic Records Group. The data set is updated weekly from 2004 to the present. The data set is compiled from all collisions provided by the Seattle Police department and recorded by the Traffic Records Group.

The attributes from the data set that may be used to drive the prediction model are:

Attribute | Description | Notes
---------|----------|---------
 LOCATION | Description of the general location of the collision | See 1
 WEATHER | Description of the weather conditions during the time of the collision | See 2
 SPEEDING | Wheather or not speed was a factor in the collision | See 3
 LIGHTCOND| The light conditions during the time of the collision| See 4
 ROADCOND | The condtion of the road during the condition| See 5
 JUNCTIONTYPE | Category of junction at which the collision took place | See 6
 PERSONCOUNT | The number of people involved in the collision| See 7
 VEHCOUNT | The number of vehicles involved in the collision | See 8

1. Initial analysis indicates that there are only two location fields provided. The bulk of the records show an _EXCEPTRSNCODE_ field of _NEI_ with an _EXCEPTRSNDESC_ field of _Not Enfough Information or insufficient Location Information_.

2. This field has enumerated values. The _UNKNOWN_ value represents 298 entries out of 194673. These records could be safely eliminated from the data set.  There is overlap with other fields that contain the _UNKNOWN_ value.

3. This field has enumerated values. The _Y_ value exists in 8 entries out of 194673. The rest of the entries are blank. If there were a greater number of _Y_ entries in the data set, a reasonable assumption would be to set the blank entries to _N_.

4. This field has enumerated values. The _UNKNOWN_ value represents 270 entries out of 194673. These records could be safely eliminated from the data set. There is overlap with other fields that contain the _UNKNOWN_ value.

5. This field has enumerated values. The _UNKNOWN_ value represents 299 entries out of 194673. These records could be safely eliminated from the data set.  There is overlap with other fields that contain the _UNKNOWN_ value.

6. This field has enumerated values. The blank value represents 568 entries out of 194673. These records could be safely eliminated from the data set.  There is overlap with other fields that contain the _UNKNOWN_ value.

7. This field has numeric values from 1 to 5.

8. This field has values from 1 to 4.

Attribute | Description | Notes
----------|-------------|------
SEVERITYCODE | A code that corresponds to the severity of the collision | See note 1

1. This field has values describing property damage (1) or injury (2). The unknown (0), serious injury (2b), and fatality (3) values are not represented in this data set, therefore no predictions can be made other than for property damage (1) or injury (2).
