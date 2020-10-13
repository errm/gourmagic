# GourMagic Pro

This repository contains code relating to some experiments I am making with
a Kitchen machine the Gourmia - GourMagic Pro GMK9000

This machine is an Android powered food mixer / cooker that seems quite similar
(as far as I can tell) to the popular (and expensive) Thermomix kitchen machines.

## The machine

This machine is currently relatively good value (£60) on Amazon UK

* https://www.amazon.co.uk/gp/product/B07JC8VXQG  (£60)
* https://www.amazon.co.uk/Gourmia-GKM9000-Multi-Cooker-Kitchen-Machine/dp/B08CRW22ZB (£80)

I have tried cooking a number of Thermomix recipes on it without any issues,
and for me it is worth the money just to not stir my porridge by hand every morning.

Since it seems like it will be easy to add my own recipes, and perhaps update
the software on the machine it also seems worthwhile as an engineering project.

* The machine seems to be running (an old) version of android.
* There is a working web-browser.
* It has a USB port, a micro-sd card and can connect to WiFi.

## sdcard

The machine has a micro-sd card, the factory contents of which I have dumped to
the sdcard directory.

An initial investigation of these files follows:

* `mp3` & `mp4` the manual makes some mention of adding music or videos to these
(empty) directories... I am not sure what the point of this would be 🤷 and I
haven't tried to see if it works yet.

* `pdf` this contains a PDF of the paper manual that came with the machine,
you can look at it on the machine, the PDF app seems to be trying to show
banner ads 💩😢

* `Recipes` this is the good stuff... it looks like the makers have dropped
support for this machine, so there is no way to get new recipes onto the machine
from there website or app or whatever. However they are all stored in this directory.

The format seems quite simple, a directory containing a `recipe.xml` and a
small image.

```xml
<?xml version="1.0" encoding="utf-8"?>
<recipe>
  <name>Recipie Name</name>
  <img>filename.jpg</img>
  <totaltime>300</totaltime>
  <ingredients>List of ingredients seperated with linebreaks</ingredients>
  <type>1</type> <!--Not sure what this is yet, but there are different values for different recipies-->
  <videoname>null</videoname>
  <step>
    <!-- These attrubtes controll the operation of the mixer, on steps for manual actions they are all set to 0-->
    <speed>0</speed>
    <temp>0</temp>
    <time>0</time>
    <describe>A description for the step</describe>
  </step>
  <step>
    <speed>3</speed>
    <temp>90</temp>
    <time>180</time>
    <describe>Time temp and speed can be set for cooking</describe>
  </step>
  <step>
    <speed>3</speed>
    <temp>90</temp>
    <time>180</time>
    <reverse>yes</reverse>
    <describe>The blades can be reversed (for stirring)</describe>
  </step>
</recipe>
```

📝 These files are reproduced here for educational purposes owner, As I was 
unable to ascertain any copyright owner I was unable to ask permission to do so.
No infringement of any rights is intended, and if you are unhappy about any or
all of these files being reproduced here please open a github issue or email me
for removal.
