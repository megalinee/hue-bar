# hue-bar
hue-bar is a Rofi-based Philips Hue light controller

![alt text](rofi-view.png)

![alt text](polybar-view.png)

### Dependencies
- Rofi
- Python 3.3+
  - rofi_menu
  
You can simply install the python dependencies by typing:
`pip install rofi_menu`

### Setting Up hue.py
To get the proper API keys you must go to the following link and make an account:<br />
https://developers.meethue.com/develop/hue-api-v2/getting-started/

Once you've made an account follow along the steps on the website to get your Hue bridge IP & username.
Paste these values into the matching variables at the top of the hue.py file<br />

Use the following curl command to retrieve username:<br />
`curl --request POST --data '{"devicetype":"linux#huebar", "generateclientkey":true}' https://<Hue IP>/api -k`

Your room name will be the same name as what you set it on your other devices

### Polybar Config
Paste this in your config.ini file, replacing `pathtoscript` with the path to the script.
```
[module/lights]
type = custom/text
content = "󰌵"
click-left = rofi -modi mymenu:/pathtoscript/hue.py -show mymenu -show-icons
```
