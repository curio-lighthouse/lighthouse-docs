---
description: Bluetooth connection specifications
---

# Bluetooth Connection

## Raspberry Pi

### Bluetooth Service

The Raspberry Pi broadcasts a service called "`raspberrypi`" on server socket 1 using the UUID of 

```text
1e0ca4ea-299d-4335-93eb-27fcfe7fa848
```

### Connecting to the Raspberry Pi

The Raspberry Pi includes a script called `simple-agent` which configures the Bluetooth to be open, visible, and auto-accept any incoming pairing requests.  `simple-agent` is located at:

```text
/home/pi/Downloads/lighthouse/bluez-test-scripts/examples/simple-agent
```

The `simple-agent` script allows Android devices to automatically connect and disconnect from the Raspberry Pi without the use of a pairing code. 





