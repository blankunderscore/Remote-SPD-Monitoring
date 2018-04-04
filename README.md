# Remote-SPD-Monitoring

Remotely monitor dry contacts on surge protectors while utilizing ESP-NOW for future use of DEEP-SLEEP methods.  This process utilizes two ESP32 boards from WeMos.  The LOLIN32 board pushes a 5V HI onto the common (COM) terminal of the remote contacts with one of the digital inputs waiting on the normally open (NO) contact.  Once the SPD reaches end of life and disconnects the digital pin will be set high and therefore can transfer data to the Slave board that one of the SPDs has disconnected.

Four SPDs were utilized for the prototype in order to allow for the push to occur.

# Limitations

- Boards were set in real-time with a delay of 3s in order to provide fast feedback but ESP32 boards can deep-sleep for years
- ESP8266 (ESP-01) can only deep-sleep for up to 1 hour which limits the lifetime significantly
- ESP32 boards can only operate on 2.4 GHz WiFi which limits the use of hotspots to access MQTT and IFTTT servers

# Future commits

I want to bring in a modem which can repeat a cellular phone hotspot at 2.4 GHz since all phone hotspots operate on 5 GHz which would allow for external https access.
