![Pretense](/images/cover_banner.jpg)

# User Manual

**Pretense** is my second attempt at a dynamic campaign in DCS. 

This mission came from all the things that Foothold failed to live up to in my mind.

I wanted the focus to be on you, the player, as a mercenary pilot in the middle of this war unfolding around you. Your job is to choose from the available missions and complete them, while earning experience and climbing through the ranks.

In this mission bases need resources to upgrade themselves and deploy defenses. Resources that they will now attempt to share with eachother and push towards the frontline where they are needed.

This time AI groups are truly dynamic, each base deciding what to build and where to send it. No waypoints for any of the AI are predetermined in the mission editor. Everything is decided in the moment.

This time the campaign was built with performance in mind. Activity is concentrated on the frontline, bases farther away will operate in a less active mode, but will still be there as functional parts of the economy.

It took more then a year to make this. Burned myself out trying to balance it. I'm still not sure if it works exactly the way I wish it did.

But here it is. Enjoy.

If, after you get the chance to play it a bit, you consider I deserve it, feel free to buy me a [beer](https://www.buymeacoffee.com/dzsek). 

## 1. The Battlefield

These are some general rules on how the mission functions.

### 1.1 Zones

Zones define points of interest that can be controlled by one of the coalitions.
They provide a staging point for friendly forces, and in some cases they generate resources to be used by the coalition.

They can build structures, deploy defenses, and launch AI missions against the enemy.

A coalition looses control of a zone once all of its structures are destroyed, and can be captured by an AI supply mission, or by players deploying a capture squad at them.

Zones function in a variaty of modes, that are set automatically by the game based on their distance from the frontline, and in some cases, the purpose of the zone.

Modes:
|Mode |Description|
|:---:|:----------|
|Normal|Zone functions at its full capacity using its resources to build structures, deploy/repair defenses, and launch AI missions<br/>Reserved for zones directly on the frontline where the action is happening|
|Supply|Zone functions like normal, except it no longer launches AI missions, except those that transfer resources to other zones<br/>Reserved for zones close to the frontline but not directly neighboring enemy zones<br/>These zones focus on supplying the front, but are still somewhat defensive|
|Export|Zone will sell all defenses and focus on pushing resources towards the front<br/>Reserved for zones far from the frontline where not much action happens<br/>Zones will still attempt to build structures|
|Override|These zones always function as if they were in Normal mode, regardless of where they are located<br/>reserved for zones that hold SAM sites and Airfields|

### 1.2 Resources

Zones use a resource called "supply" to either build structures, deploy defenses, resupply other zones or launch missions against the enemy.

There is a maximum amount of supply that a zone can hold, any further deliveries are lost.

Everything a zone builds consumes supply, but each structure, defensive group, or AI mission has different costs.

Build time depends on the cost of whatever the zone is currently building, but is also occasionally influenced by the game to provide a limited pushback oportunity by either of the coalitions.

Zones that are below a certain treshold of resources will gain a "low supply" trait, which restricts what they can build, but also makes them more likely to get resupplied by other friendly zones. This is marked in by the `(!)` in the zone label.

### 1.3 Production

Production is handled automatically by the zone, and not under control of the players.

What a zone can build depends on a so called "tech tree". 
The root of this tree is a list of structures, each one, when built will unlock new build options for the zone.

There is no hard rules on what each building can do, but there are some general ones:

|Type|Description|
|:---:|:----|
|Tents & Barracks|Usually the first structure built(for free) once a zone is captured.<br/>Allows the zone to deploy infantry and armor to defend itself|
|Fuel storage buildings|Allow the zone to transfer resources to other zones in need|
|Ammo storage buildings|Allow the zone to launch ground based assault missions against enemy zones|
|Command centers|Allow the zone to deploy air defenses and launch aircraft in missions against enemy zones|

Again, these rules are not set in stone and there are some exceptions if you look hard enough.

### 1.4 Zone labels

Zones labels contain the zones name and how many resources they have.
In case the zone is building something it will also display the name of what is being built and its progress towards completing it.

In the case of enemy zones, only the name of the zone will be displayed, unless revealed by player recon missions (see [section 3.5](#35-mission-types)).

### 1.5 AI Mission types

|Mission Type|Description|
|:----------:|:----------|
|Supply| Moves resources between two zones<br/>Captures neutral zones<br/>Supply convoys: slow, move on roads, will only supply connected zones<br/>Supply helicopters: fast, will supply zones up to 2 connections away|
|Patrol|Patrols the area around the frontline and engages enemy aircraft|
|CAS|Engages enemy defenses at zones near the frontline<br/>Two types: Fixed wing and Helicopters|
|BAI|Engages enemy convoys|
|Strike|Bombs enemy structures near the frontline|
|SEAD|Engages air defenses at zones near the frontline|
|AWACS|Orbits the airbase it is deployed at|Anounces frequency on takeoff|
|Tanker|Orbits a base farther back from the frontline in a racetrack pattern|
|Assault|Ground convoy, move on roads, attack connected enemy zones<br/>While inside an enemy zone, will trigger an explosion at a random enemy structure inside the zone<br/>If the zone turns neutral, they will capture it and despawn|
|Cargo planes|Special missions that periodically fly in from the edge of the map and land at airfields to inject new supplies into the economy|

## 2. Logistics
This section covers only player logistics. For AI logistics see the supply AI mission in section 1.4

### 2.1 Supplies

Supplies can be transported by players between zones using transport aircraft.

Players can load as much supply as they want from any friendly zone, as long as the zone has resources to spare, and the players are confortable with flying with the added weight.

To load and unload supply you need to be stationary on the ground, within the limits of a friendly zone, and have at least one cargo door open on your aircraft.

Each unit of supply weighs 1kg.

Managing supplies onboard your aircraft is done using the `Other->Logistics->Load/Unload supplies` options in the radio menu. This is only available to aircraft that are allowed to carry supplies. A list of compatible aircraft is provided in [section 2.4](#24-compatible-aircraft)

Loading supplies removes them from the zone.
Unloading them adds them to the zone.

Dying or abandoning your aircraft with supplies on board will cause the supplies to be lost.

### 2.2 Infantry

Some aircraft are capable of deploying infantry squads with various roles to the battlefield. Every squad has a specific purpose, and once they accomplish their mission, can be extracted back to a friendly zone.

Managing squads onboard your aircraft is done using the `Other->Logistics->Infantry` options in the radio menu. This is only available to aircraft that are allowed to carry infantry. A list of compatible aircraft is provided in [section 2.4](#24-compatible-aircraft)

Loading a squad costs a certain amount of resources from the zone. This is dependant on the type of squad you are trying to load.
The zone will refuse your request if it is low on resources.

Only a single squad can be loaded at one time. Unloading a squad at the same zone its been loaded at will unload the squad and refund the resources to the zone.

Once a squad is deployed, it will take a certain amount of time until they complete their mission, after which they can be extracted to a friendly zone to recover some resources. 

Once they are ready to extract they will deploy blue smoke. If not extracted before a set time limit the squad will be lost.

Loading a squad that is ready to extract is done by landing near them and using the `Other->Logistics->Infantry->Extract squad` option from the radio menu.

Available infrantry squads:

| Squad | Description |
|:-----:|:------------|
|Capture| If deployed at a neutral zone, will capture the zone to their side |
|Sabotage| If deployed to an enemy zone, will trigger an explosion at a random structure within the zone, which in turn destroys a random amount of resources as well in that zone |
|Ambush| Squad armed with rifles and RPGs that can be deployed anywhere on the battlefield. Can be used to intercept enemy convoys.|
|Engineers| If deployed at a friendly zone, they will boost production speed in that while reducing costs for anything built at the zone for a limited time.|
|MANPADS| Squad armed with rifles for self protection and MANPADS, that can be deployed anywhere on the battlefield. Can be used to provide some protection from enemy aircraft or intercept enemy supply helicopters|


Squad stats

| Squad | Weight | Supply cost | Mission duration | Extraction Time limit |
|:-----:|:------:|:-----------:|:----------------:|:---------------------:|
|Capture|700kg|200|1 minute|30 minutes*|
|Sabotage|800kg|500|5 minutes|30 minutes|
|Ambush|900kg|300|20 minutes|30 minutes|
|Engineers|200kg|1000|1 minute|30 minutes*|
|MANPADS|900kg|500|20 minutes|30 minutes|

>*Note that Capture and Engineer squads do not require extraction if they were deployed in accordance with their mission 

### 2.3 CSAR (Combat search and rescue)

Pilots that eject in combat can be rescued by players using transport capable aircraft. The commands relevant to CSAR can be found under the `Other->Logistics->CSAR` option in the radio menu.

This menu holds commands that aid you in finding someone to rescue, as well as the commands you use to extract and unload your targets.

The `Show info` command will show you bearing and distance to the nearest pilot in need of rescue.

The `Smoke marker` command will tell the nearest pilot to deploy a smoke marker nearby, as a visual aid to help find him. A `Flare` command is also available for low visibility conditions.

To be able to extract a pilot you dont necessarily need to land, but you will need to at least hover close to your target. Once you are in position you can extract your target using the `Extract pilot` command.

You can bring your rescues back to any frienly zone and unload them using the `Unload` command to regain some resources for the zone.

Each aircraft has a maximum amount of rescued pilots that it can hold at one time, this limit is specified below in [section 2.4](#24-compatible-aircraft)

### 2.4 Compatible aircraft
By default the following aircraft can participate in logistics
| Aircraft | Can carry supplies | Can carry infantry | CSAR capacity |
|:---:|:---:|:---:|:---:|
|Mi-24P|Yes|Yes|8|
|Mi-8MT|Yes|Yes|24|
|UH-1H|Yes|Yes|12|
|SA342|No|Yes|2|

Although community mods are not available in the mission by default, the following mods are supported if you choose to add them.

| Aircraft | Can carry supplies | Can carry infantry | CSAR capacity |
|:---:|:---:|:---:|:---:|
|Hercules*|Yes|Yes|92|
|UH-60L|Yes|Yes|11|

>*Note that the Hercules cargo drop is not supported at this time, logistics can only be done using the radio menu

## 3. Missions

>Note: A reminder on the commands can be accessed using the `Other->Missions->Help` option in the radio, or by creating a map marker anywhere and settings its text to `help`

These are assignments that can be taken by players and completed for an XP reward.

Missions are generated based on the state of the battlefield. Not all types of missions are available at all times.

### 3.1 The mission board

Currently available missions can be viewed on the `mission board` by accesing `Other->Missions->List Missions` in the radio menu.

Each mission on the list has a short description, and most importantly a `4 digit code` that is unique to that mission. The next section will describe how to use this code to accept a mission.

Missions expire after a few minutes if not taken by anyone, or, if due to changes on the battlefield, they are no longer valid.

Some mission types can have multiple variations with slightly different sets of objectives and difficulties. Pay attention to the wording of the mission description.

### 3.2 Accepting, joining and leaving a mission

Before being able to complete a mission you will need to accept it. This can only be done while landed and stationary at a friendly zone.

To accept a mission, you can dial in its `4 digit code` using the `Other->Missions->Dial Code` option in the radio menu.

If the code was for a valid mission, this mission will now be assigned to you, and it will be removed from the mission board. The mission will now enter the `prepping` phase.

In this phase the mission has not started yet, and is only visible to you using the `Other->Missions->Active Mission` option in the radio.

You will notice that the `4 digit code` has been replaced by a new one.
This new code is only visible to you. If you so wish you can share it with a friend, who can use it to join you on your mission.

To do so, he can dial in the `4 digit code` that you shared with him using the `Other->Missions->Dial Code` option in the radio menu.

Any number of players can join the same mission, and the displayed rewards will be awarded to every player individually, no splitting.

Missions can only be joined by players who are on the ground inside a friendly zone, and as long as all current members are still on the ground and the mission is still in the `prepping` phase.

Leaving a mission in progress can be done by using the `Other->Missions->Leave Mission` option in the radio menu.

All of these options are also available by map marker commands. For instructions on how to use them you can access the `Other->Missions->Help` option in the radio menu, or create a marker anywhere on the map and set its text to `help`.

### 3.3 Starting and completing a mission

Once you have accepted a mission, and all your friends joined, you can start the mission by simply taking off.

Once any member of the mission takes off the mission will change into the `commencing` phase.
The mission can not be joined in this phase. This is a transitory state that lasts until all players have taken off. While still in this phase, the airborne players can still land to turn the mission back into the `prepping` phase, should you wish to add someone else to your mission.

Once every member has taken off the mission turns `active` and the objectives can now be completed.
These vary based on the mission you have accepted and can be checked by accessing your active mission details mentioned in [section 3.2](#32-accepting-joining-and-leaving-a-mission).

Some missions require you to complete all objectives listed, some only require that you complete any one of them. This is specified in the mission description.

Some objectives are not meant to be completed, but will increase the final reward for the mission. In such cases theres always an additional objective that you can complete to finish the mission when you've had enough.

Some missions will provide guiding information for your objectives, be it bearing & distance, accurate coordinates, or just names of zones.

Some objectives can be completed by any of the players (ex. destroy X amount of ground units), some
need to be completed at the same time by all players (ex. fly over a specific zone), and some can be accomplished faster if more players are doing the activity together (ex. helicopter recon).

Once the objectives are completed the missions is considered complete, and rewards are distributed to each player into their temporary accounts. Anything in the temporary account will be lost if the player dies or abandones their aircraft. To claim these rewards permanently, the player must land at a friendly zone.

### 3.4 Failed missions

Missions can also be failed if the objectives are deemed no longer possible to complete. In this case all members will get a message, and will be unassigned from the mission, the rewards lost. This can happen in any phase of the mission up until the mission is completed.

Any member who dies or abandones their aircraft will be unassigned from the mission and no longer able to join it, even after respawning.

### 3.5 Mission Types

| Mission | Description | Available to |
|:-------:|:------------|:------------:|
|CAP| Patrol the specified zone(s) and engage enemies on your way.| Fixed wing|
|TARCAP| Protect the specified players while they accomplish their mission. Mission completion is tied to target missions completion | Fixed wing|
|CAS| Destroy the specified number of ground units. Some variations need the units to be destoyed at a specific location| Any|
|BAI| Destroy the specified convoy before it reaches its destination|Any|
|SEAD| Destroy a radar at the specified zone. This includes any unit with a search or a track radar. (ex. SA-19, SA-15) | Any|
|DEAD| Destroy all air defenses at the specified zone| Any|
|Strike| Destroy either the specified number of structures at a zone, or a specific structure. Specific target missions are made available by completing Recon missions. | Any|
|Deep Strike| Destroy a specific structure, deep behind enemy lines. Mission made available by completing Deep Recon missions | Any|
|Runway Attack| Bomb runway at specified zone with minimum 5 bombs. Going above the required amount will increase the reward. Missiles and cluster bombs can not be used to complete this mission. | Any |
|Recon (Fixed wing)| Fly over the specified zone. If multiple players are part of the same mission, all players need to be at the zone simultaneously for the objective to register. Can reveal targets for Strike missions. Will reveal the zones build and resource status on the map for a limited time. | Fixed wing |
|Deep Recon(Fixed wing)| Fly over the specified zone, deep behind enemy lines. If multiple players are part of the same mission, all players need to be at the zone simultaneously for the objective to register. Can reveal targets for Deep Strike missions. Will reveal the zones build and resource status on the map for a limited time. | Fixed wing |
|Recon (Helicopter)| Fly within range of the specified zone and stay within sight of as many enemy units as you can. Objective completes faster the more enemies from the zone are visible to you. Can reveal targets for Strike missions. Will reveal the zones build and resource status on the map for a limited time. | Any helicopter |
|Supply| Transport specified amount of resources to specified zone | Supply stransport capable aircraft [section 2.4](#24-compatible-aircraft)|
|Escort| Escort specified friendly convoy on their way between zones. Objective is completed by spending the required time near the convoy, or if the convoy reaches its destination. | Any helicopter|
|CSAR| Rescue a specified ejected pilot and bring them back to a friendly zone | Infantry transport capable aircraft [section 2.4](#24-compatible-aircraft)|
|Extraction| Extract a specified infantry group once they are ready with their mission, and bring them to a friendly zone | Infantry transport capable aircraft [section 2.4](#24-compatible-aircraft)|

## 4. Finding information while playing

### 4.1 Kneeboard

Your kneeboard contains a few pages covering the location of each zone, in alphabetical order. These are added to the end of the default kneeboard pages, in reverse order, so that they're easier to find by going backwards from the default kneeboard page.

Should your plane support waypoints, you will also find which waypoint each zone is assigned to by default.

Some planes have a limited amount of waypoints, and they wont have all zones programmed in.

The Ka-50 waypoints are always offset by 1, as waypoint 1 is considered the start position of the aircraft.

### 4.2 Radio Channels

The mission regularly spawns support units that you might need to contact within mission, like AWACS and Tankers.
The frequencies for them can be checked in the `Other->Information->Frequencies` option in the radio menu.

Only units that are currently alive are shown in this menu. It can happen that the unit in question is just spawned and is in the process of taking off and will not immediatly respond on the frequency.

### 4.3 Player information

Your stats can be accessed through the `Other->Information->Player` option in the radio menu.

This currently only contains your name, XP, and rank.

## 5. Player XP and Ranks

You gain XP by completing missions, killing enemies and delivering resources.
After a certain amount of XP you will rank up.

XP and ranks do not have a gameplay purpose at the moment. They are just theres for tracking your contributions to the mission and bragging rights.

## 6. Editing the mission to suit your needs


- You can add any client aircraft you want anywhere on the map. Should you add it inside the borders of a zone, the slot will be blocked according to the state of the zone. No extra effort required on your part to make it work.
- Due to limitations with the DCS scripting API, multiple client aircraft in the same group are not supported. Please limit all slots to single aircraft groups, otherwise the radio menu and some other features will not work correctly.
- You **can not** adjust difficulty by deleting AI aircraft from the mission editor. Doing so will result in script errors.
- Logistics capable aircraft where categorized by what maked logical sense on what they can carry. In case you would like to enable logistics for other aircraft you can do so by adding a doScript action afther the scripts are loaded in the initialization trigger in the mission editor and overriding the values in there like this:

```
PlayerLogistics.allowedTypes['Mi-24P'] = { supplies = true, infantry = true, pilotCapacity = 8 }
PlayerLogistics.allowedTypes['Mi-8MT'] = { supplies = true, infantry = true, pilotCapacity = 24 }
PlayerLogistics.allowedTypes['UH-1H'] = { supplies = true, infantry = true,  pilotCapacity = 12}
PlayerLogistics.allowedTypes['Hercules'] = { supplies = true, infantry = true, pilotCapacity = 92 }
PlayerLogistics.allowedTypes['UH-60L'] = { supplies = true, infantry = true, pilotCapacity = 11 }
PlayerLogistics.allowedTypes['Ka-50'] = { supplies = false, infantry = false, pilotCapacity = 0 }
PlayerLogistics.allowedTypes['Ka-50_3'] = { supplies = false, infantry = false, pilotCapacity = 0  }
PlayerLogistics.allowedTypes['SA342Mistral'] = { supplies = false, infantry = true, pilotCapacity = 2}
PlayerLogistics.allowedTypes['SA342L'] = { supplies = false, infantry = true, pilotCapacity = 2}
PlayerLogistics.allowedTypes['SA342M'] = { supplies = false, infantry = true, pilotCapacity = 2}
PlayerLogistics.allowedTypes['SA342Minigun'] = { supplies = false, infantry = true, pilotCapacity = 2}
PlayerLogistics.allowedTypes['AH-64D_BLK_II'] = { supplies = false, infantry = false, pilotCapacity = 0  }
```
- You only need to add the lines for the aircraft you want to change.

- There is currently no easy way to adjust difficulty. The flow of the mission depends on many factors such as cost of AI groups, default build speeds, the flow of resources to each zone, the decision of each zone on what to build, a BattlefieldManager component that adds some variation to the default build speeds based on battlefield state, a randomized boost factor to build speeds to make either coalition occasionally push harder, and finally the behaviour of the DCS AI. It is unpredictable by nature, and any changes you make might have unexpected side effects. Your best bet is to try adjusting the commented values inside BattlefieldManager, specifically the limits of the math.random for x, the boostIntensity variable, and the multiplier variable.

## 7. Persistence
This mission comes with persistance, which allows the mission to remember its state when you exit the mission and continue from there once you start it up again.

To enable persistance you have to allow the mission environment inside DCS to read and write to and from your file system. To do this you will need to edit `\Scripts\MissionScripting.lua` inside your DCS or DCS server installation folder.

Change the following section:
```
do
    sanitizeModule('os')
    sanitizeModule('io')
    sanitizeModule('lfs')
    _G['require'] = nil
    _G['loadlib'] = nil
    _G['package'] = nil
end
```
To look like this:
```
do
    sanitizeModule('os')
    --sanitizeModule('io')
    --sanitizeModule('lfs')
    _G['require'] = nil
    _G['loadlib'] = nil
    _G['package'] = nil
end
```

**:warning:Be aware that by doing this you are allowing full access to your file system to scripts running within DCS. Only run missions you trust after doing this change.**

To reset progress and start the mission from the beginning you can delete the save file. 

This can be found in `C:\Users\<windows_username>\Saved Games\DCS.openbeta\Missions\Saves\`, and its called `pretense_<version>.json`

> Note: AI groups that are restored from a save file will always be at full numbers and at full loadout, even if part of the group was destroyed previously, or they have expended some of their munitions

## 8. Running the mission on a server

### 8.1 Slotblock

For players to be prevented from spawning at enemy zones, the included `slotblock.lua` file must be placed in your servers `C:\Users\<windows_username>\Saved Games\DCS.openbeta\Scripts\Hooks` folder, and the server restarted, in case it was already running at the time.


### 8.2 Stats file

In addition to the save file the mission also writes to a file called `player_stats.json` in `C:\Users\<windows_username>\Saved Games\DCS.openbeta\Missions\Saves\`

This is a JSON file containing the information about the currently running mission, and is updated once per minute.

Information in the file includes players who have played the mission and their XP, what aircraft players are currently flying, and the name of the zones broken down into 3 lists for red, blue, and neutral coalitions.

You can use the information in this file to export a mission status to a discord server or to a website, or whatever other use you can come up with for it.