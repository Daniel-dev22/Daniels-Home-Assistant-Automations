The 2 thermostat `automations` are triggered every 5 minutes, on state change of the thermostat schedules or when the thermostat mode switches from off to either cool or heat.

Then the correct schedule is used based off of what mode the thermostat is using and the variables specific to that thermostat are then passed to the `master script`.

The script pulls in the correct set temperature based off the schedule sensor for the time of day and day of the week if needed and then goes through conditions that will affect the final temperature sent or not sent to the thermostat.

First, is the thermostat running or not running. There is a 2 degrees threshold maintained on all thermostats meaning when it turns on during cool it is `- 2` degrees and off `+ 2` for heat it is the inverse of cool.

Then based off the weather should the thermostat temperature be modified further or any other conditions. Then once the `summer or winter condition temperature` is chosen if that temperature is not equal to the current set temperature of the thermostat it will be sent to the thermostat and if it is equal to the set temperature nothing happens to avoid a useless transmission

