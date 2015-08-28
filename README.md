# ios-ble

## Challenges:
* Results for `writeValue:forCharacteristic:` and `readValueForCharacteristic` delivered via delegatge methods `peripheral:didWriteValueForCharacteristic:error:` and `peripheral:didUpdateValueForCharacteristic:error:`. The order of delegate methods calls depends on behavior of remote device, as remote hardware decides in what order to execute incoming commands to ensure optimal usage of hardware resources.
* Time of response for a read & write calls depends on hardware implementation. There are no built-in timeouts that may interrupt calls. Also according to [Bluetooth Core Specification v4.0](https://www.bluetooth.org/docman/handlers/downloaddoc.ashx?doc_id=229737) "No Error Response or Write Response shall be sent in response to this command. If the server cannot write this attribute for any reason the command shall be ignored." This requires implementation of custom time-out mechanism.
