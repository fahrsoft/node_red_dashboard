# node_red_dashboard
An extensive Node Red dashboard configuration for a sailboat dashboard. This is made to allow an OpenPlotter installation on a Raspberry Pi 4 controlling things and a Raspberry Pi 3 used for display in the cockpit. The code is loaded on the Pi4 while the Pi3 displays via the web URL.

This set of flows includes the excellent work of the Beagle-Sailsteer-Cockpit from Ariavander Hoek https://github.com/ArievanderHoek/Beagle-Sailsteer-Cockpit, but with some fixes to remove error messages and modification to fit a 7" 1024x600dpi touchscreen. 

It interfaces with my Peet Bros. Anemometer (https://github.com/fahrsoft/peetbros_anemometer_nanoiot_mqtt) transmitting over WiFi with MQTT to provide wind information. It shows a lot of barometric information and sky information derived from SignalK plugins like Derived Data and Barometer Trend; position information from the GPS; anchoring information and alarms from the Anchor Alarm plugin, and CPU temperature from two Raspberry Pis on my network. 

It also includes an alert system to display notifications from SignalK if they are tagged for display and audio alerts. The alert can be snoozed by tapping on the alert row on the table of alerts, in which case it will not sound an alarm again (if that alert is dismissed and raised again by the system, the sound will happen again). Sounds will repeat every 20 seconds until the alert is snoozed or corrected. The sound will be spoken on computers that can provide text to speech, but an alarm sound will also be raised from the OpenPlotter host Pi as well via its built-in sound output, either the headphone jack or HDMI port. 

Finally it automatically requests a GRIB file by sending a formatted email then retrieving that email to save to a file for OpenCPN, etc. to consume for weather information.

Requirements:
@signalk/node-red-embedded
node-red-contrib-play-sound
node-red-contrib-simpletime
node-red-contrib-speakerpi
node-red-contrib-string
node-red-contrib-ui-svg
node-red-dashboard
node-red-email
node-red-rbe
node-red-tail
node-red-ui-table
