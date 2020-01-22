This module is released as shareware.  It is free for Crestron programmers to use in 
their own system or dealers to use in their showrooms.  If the code is used in a
customer's system, where the dealer will profit from it, then I ask for simple payment
of $100 ($105 if paid through Paypal).  This payment licenses the dealer to use it on 
as many customer systems as they want. Anyone who pays for the module will also be 
provided with the full S# source code for the module.  To arrange for payment please
contact jay.m.basen@gmail.com 

This module is designed to simulate circadian lighting in a home.  It tracks the sun
and outputs the color temperature and brightness for smart bulbs to mimic the changes 
the sun goes through during the day.  While the mimimum and maximum color temperatures 
are available as parameters they should not be changed unless there is a clear need to 
do so as 55000K is the color temperature of the sun at mid-day and 2000K is the color 
temperature of the sun at sunset. In the example program the minimum color temperature 
is set to 2200K as this the low color temperature limit of Philips Hue White Ambiance 
bulbs. If you are using Philips Hue Color Ambiance bulbs the minimum color temperature 
can be set to 2000K.  If using bulbs from another manufacturer, these parameters should
be set to match the specifications of those bulbs.

However, the maximum and minimum brightness should be adjusted based on measurements
from a digital light meter that displays the light level in lux.  These are available
inexpensively from Amazon.  The max brightness  should be set such that the lights in 
the home produce at least 20,000 lux; the light level outside, on a sunny day, in the 
shade.  The minimum brightness should be set so the lights in the home produce 
aproximately 400 lux;the light level at sunrise and sunset.  The module will transition
from the max brightness level to the minumum brightness level as the sun travels across
the sky.  It will then maintain the minimum brightness level throughout the evening and 
night. 

The circadian lighting example program includes Philips Hue integration modules from 
Ultamation (https://www.ultamation.com/).  If you want to use the circadian lighting
module with Philips Hue bulbs, the latest version of these modules should 
be downloaded from the Ultamation web site and a license key must also be separately 
purchased from them.

INPUTS
Initialize                    -   Pulse this input to intialize the module 
Circadian_Lighting_Enable     -   Enables calculation of solar azimuth/elevation and
                                  outputting of brightness and color temperature
                                  to lights
Circadian_Lighting_Disable    -   Disables calculations and outputting brightness and
                                  color temperature to lights
Circadian_Lighting_Toggle     -   Toggles Circadian Lighting on/off
Light_*_On_FB                 -   Feedback from lighting driver module as to whether
                                  a light is on.  

OUTPUTS
Circadian_Lighting_Enable_FB  -   High if circadian lighting enabled.  Otherwise Low
Circadian_Lighting_Disabled_FB-   High if circadian lighting disabled.  Otherwise Low
Color_Temperature_*           -   The color temperature that smart lighting should be set to
                                  for proper circadian lighting
Brightness_*                  -   The brightness that smart lighting should be set to for proper
                                  circadian lighting
Hue_*                         -   The hue set for color bulbs when circadian lighting is
                                  enabled
Saturation_*                  -   The saturation set for color bulbs when circadian lighting 
                                  is enabled

PARAMETERS
Latitude                      -   Latitude of the home
Longitude                     -   Longitude of the home
Logger_Level                  -   Defines which types of messages will be logged during 
                                  operation for debugging purposes 0 = None, 3 = Errors, 
                                  7 = Errors + Status, 9 = Errors + Status + Math
Minutes_Between_Calcs         -   The number of minutes the module will wait between 
                                  calculation operations
Max_Color_Temperature         -   Defaults to 5500K.  Shouldn't be changed unless there is a 
                                  specific need
Min_Color_Temperature         -   Defaults to 2000K.  Shouldn't be changed unless there is a 
                                  specific need
Max_Brightness_*              -   The maximum dimming level a light will be set to. Lighting
                                  level in the room should be set with a light meter to match 
                                  daytime shade lighting of 20,000 lux, or more, at the places
                                  in the room that people will occupy.
Min_Brightness_*              -   The minimum dimming level a light will be set to.  Lighting
                                  level in the room should be set with a light meter to match 
                                  sunrise/sunset lighting of 400 lux at the places in the room 
                                  that people will occupy.
