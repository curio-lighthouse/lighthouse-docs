---
description: Start up process and scripts on the Raspberry Pi
---

# Raspberry Pi Scripts

{% hint style="info" %}
A bash script \(/home/pi/Downloads/lighthouse/bluetooth-script.sh\) is executed at startup in order to configure bluetooth settings for the Raspberry Pi and start 3 Python scripts \(explained below\).  An entry for the bash script is made in the /etc/rc.local file in order to the script to be executed at startup.
{% endhint %}

{% tabs %}
{% tab title="bluetooth-script.sh" %}
#### Details:

* Entry in /etc/rc.local ensures this script is executed on startup.
* Configures bluetooth to be on and available for pairing.
* Starts simple-agent, lighthouse, and power-button Python scripts.
{% endtab %}

{% tab title="simple-agent" %}
Python script enabling headless bluetooth connections by handling input required for bluetooth connections on the Raspberry Pi.
{% endtab %}

{% tab title="lighthouse" %}
Python script for reading and sending LiDAR data as well as commands sent to and from the phone.
{% endtab %}

{% tab title="power-button" %}
Python script that shuts down or turns on the Raspberry Pi after pressing the button.
{% endtab %}
{% endtabs %}



