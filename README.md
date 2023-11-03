# E46 M3 Cluster
This repo contains a Vector CANoe configuration for a BMW M46 M3 instument cluster with SMG coding.

Following messages are implemented:
|CAN ID|Message name|Content|
|:---|:---|:---|
|0x316|DME1|i.e. RPM|
|0x329|DME2|i.e. cruise control light, engine (water) temperature, ...|
|0x545|DME4|i.e. overheat light, oil warning, eml light, check engine light, oil temperature, rpm warn field, ...|
|0x610|VIN|VIN request, RTR flag is set|
|0x153|ASC1|i.e. vehicle speed|
|0x1F0|ASC2|wheel speed|
|0x1F3|ASC1|..|
|0x43F|SMG2|i.e. gear info, display, drivelogic, ...|

SMG2 (CAN ID 0x43F) is implemented in CAPL, the checksum calculation is included, so gear info is displayed.
VIN Request (CAN ID 0x610) is also implemented in CAPL, because of RTR-fields. This message will be answered by instrument cluster with correct VIN.