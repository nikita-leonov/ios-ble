# ios-ble

## Challenges:
* Results for `writeValue:forCharacteristic:` and `readValueForCharacteristic` delivered via delegatge methods `peripheral:didWriteValueForCharacteristic:error:` and `peripheral:didUpdateValueForCharacteristic:error:`. The order of delegate methods call is up to behavior of remote device, as remote hardware decided in what order to perform incoming commands.
* Time of response for a read & write calls is up to hardware implementation. There is no built-in timeouts that may interrupt calls. Also according to [Bluetooth Core Specification v4.0](https://www.bluetooth.org/docman/handlers/downloaddoc.ashx?doc_id=229737) "No Error Response or Write Response shall be sent in response to this command. If the server cannot write this attribute for any reason the command shall be ignored." this require implementation of custom time-out mechanism.
