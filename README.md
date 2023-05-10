# Attack codes for Rogue devices

All attack codes will be specified with this repository, pure/unchagned code is in subdir `00` and each directory represented by a number is explained in details inside our documentation provided to TP.

Source code of the template commes from https://github.com/lnlp/LMIC-node.

### 00 Default End Node Source code
This folder contains the customized LMIC library for the end node to allow it to connect to our chirpstack infrastructure and send an example uplink data payload.

## Realized attacks

### 01 Jamming attack 
Jamming of the End node network registration process. Or physical jamming of the End device resulting in service degradation and message loss.

### 02 Replay attacks
The attacker manages to capture a message from the End device to the LoRa gateway, prevents the uplink communication between given and device and the gateway and then replays the original message.

### 03 Unathorized gateway movement
The attacker moves a selected LoRa gateway between locations.

### 04 Unathorized database access
Chirpstack uses Reddis database to store sensitive infromation. If the attacker manages to connect to the Reddis databse from a forbidden IP address he can potentialy gain access to sensitive infromation including the secret key stored in the databse.

### 05 MITM attack between application and network server
This attack was no realized as we used Chirpstack which integrates both the application and the network server.

### 06 Transmission restrictions violation
In our example scenariou we set the End node to send an uplink message every 30 seconds. In our example scenario violation of the restrictions consisted of an End device sending uplink data messages more frequently than every 30 seconds. But this attack could have been further modified to break even the regulations set by the EU-868 regulation.

### 07 Service degradation/anomallies in data values
This included anomalies in meassured temperature values, but also service degradation resulting from sending messages less frequently than the set 30 second window for an uplink data message.

### 08 Bit flipping attack
This attack was not realized as the LMIC library which we used for our end devices uses and AES encryption algorithm to encrypt the payload and this particular algorithm is not vulnerable to bit flipping attack.

