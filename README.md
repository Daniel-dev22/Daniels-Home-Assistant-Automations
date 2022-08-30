# Daniels-Home-Assistant-Automations
An Overview of some of the Automations I developed
###
Inside each file is a `template_sensors.yaml` which is broken out of a main file called `templates.yaml` in home assistant where template sensors go.
###
Template sensors are used to feed data to or trigger automations. In some examples such as the thermostat schedule it is both a trigger and a resource to determine the current scheduled temperature. In others it is used to trigger the automation to open or close the shades as well as be checked against during triggers that guard against failure from the automation being interrupted among other potential causes. In essence all automations have built in guards that were tested rigorously to ensure the automation runs successfully.
###
As Home Assistant is based on python and utilizes `.yaml` files everytime an automation is edited the entire `automations.yaml` file must be reloaded which can cause automations that were already processing or about to trigger to not trigger. To counter that I either leverage triggering off of an automation reload in addition to the standard triggers or a time pattern is used to accomplish both acting as a guard against those reload issues or allow for conditions to be checked every `x` minutes.
