# HA-Alexa
Code I used for Alexa and Node-Red

"node-red-contrib-amazon-echo": https://flows.nodered.org/node/node-red-contrib-amazon-echo

Main Video "**Home Assistant: Controlling Devices with Alexa**": https://youtu.be/l1as3tYVy64


- **Basic On/Off Code**
```yaml
if (msg.payload === "on") msg.payload = {"service":"turn_on"}
if (msg.payload === "off") msg.payload = {"service":"turn_off"}
return msg
```

- **Full Code for Lighting**
```
if (msg.payload === "on")
msg.payload =
{
    "service": "turn_on",
    data:
    {"rgb_color": msg.rgb, "brightness": msg.bri}
};
if (msg.payload === "off") msg.payload = {"service":"turn_off"}
return msg
