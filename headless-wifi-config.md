# Headless WIFI setup and ssh activation

## WIFI configuration
To headlessly configure WiFi on your Pi, you can create the file ```/boot/wpa_supplicant.conf``` (in the boot partition not /boot of raspbian) that contains the following lines:

For Raspbian Stretch and later:

``` java
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
country=«your_ISO-3166-1_two-letter_country_code»

network={
    ssid="your_SSID"
    psk="your_PSK"
    key_mgmt=WPA-PSK
}
```

For Raspbian Jessie:
``` java
network={
    ssid="your_SSID"
    psk="your_PSK"
    key_mgmt=WPA-PSK
}
```

where :
- your_ISO-3166-1_two-letter_country_code = FR for france or CA for canada you can get your country's ISO two lettre code from [here](https://www.iso.org/obp/ui/#search).
- your_SSID = your WiFi's name
- your_PSK = your WiFi's password

## SSH activation
last step is SSH activation because it's desactivated by default in raspbian. And to do so, you only need to create /boot/ssh.
