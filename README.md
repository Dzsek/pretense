[![Pretense](/images/cover_banner.jpg)](https://www.digitalcombatsimulator.com/en/files/3331159/)
[![Pretense Syria Cold War](/images/cover_syria_banner.jpg)](https://www.digitalcombatsimulator.com/en/files/3332140/)
[![Pretense Syria](/images/cover_syria_modern_banner.jpg)](https://www.digitalcombatsimulator.com/en/files/3332520/)

# User Manual | [English(EN)](README.md) | [简体中文(CN)](README_CN.md)

**Pretense** is my second attempt at a dynamic campaign in DCS. 

This mission came from all the things that Foothold failed to live up to in my mind.

I wanted the focus to be on you, the player, as a mercenary pilot in the middle of this war unfolding around you. Your job is to choose from the available missions and complete them, while earning experience and climbing through the ranks.

In this mission bases need resources to upgrade themselves and deploy defenses. Resources that they will now attempt to share with eachother and push towards the frontline where they are needed.

This time AI groups are truly dynamic, each base deciding what to build and where to send it. No waypoints for any of the AI are predetermined in the mission editor. Everything is decided in the moment.

This time the campaign was built with performance in mind. Activity is concentrated on the frontline, bases farther away will operate in a less active mode, but will still be there as functional parts of the economy.

It took more then a year to make this. Burned myself out trying to balance it. I'm still not sure if it works exactly the way I wish it did.

But here it is. Enjoy.

If, after you get the chance to play it a bit, you consider I deserve it, feel free to buy me a [beer](https://www.buymeacoffee.com/dzsek). 

## Contents

1. [The Battlefield](#1-the-battlefield)
    1. [Zones](#11-zones)
    2. [Resources](#12-resources)
    3. [Production](#13-production)
    4. [Zone labels](#14-zone-labels)
    5. [AI Mission types](#15-ai-mission-types)
    6. [Player Spawns](#16-player-spawns)
    7. [Capturing a zone](#17-capturing-a-zone)
2. [Logistics](#2-logistics)
    1. [Supplies](#21-supplies)
    2. [Infantry](#22-infantry)
    3. [CSAR](#23-csar-combat-search-and-rescue)
    4. [Compatible aircraft](#24-compatible-aircraft)
    5. [Hercules mod airdrop support](#25-hercules-mod-airdrop-support)
3. [Missions](#3-missions)
    1. [The mission board](#31-the-mission-board)
    2. [Accepting, joining and leaving a mission](#32-accepting-joining-and-leaving-a-mission)
    3. [Starting and completing a mission](#33-starting-and-completing-a-mission)
    4. [Failed missions](#34-failed-missions)
    5. [Mission Types](#35-mission-types)
4. [Finding information while playing](#4-finding-information-while-playing)
    1. [Kneeboard](#41-kneeboard)
    2. [Radio Channels](#42-radio-channels)
    3. [Player information](#43-player-information)
    4. [GCI menu](#44-gci-menu)
5. [Player XP, Ranks, and Command tokens](#5-player-xp-ranks-and-command-tokens)
6. [Editing the mission to suit your needs](#6-editing-the-mission-to-suit-your-needs)
    1. [Config](#61-config)
    2. [Randomized start](#62-randomized-start)
7. [Persistence](#7-persistence)
    1. [Persistence for mission time and weather randomization](#71-persistence-for-mission-time-and-weather-randomization)
8. [Running the mission on a server](#8-running-the-mission-on-a-server)
    1. [Slotblock](#81-slotblock)
    2. [Stats file](#82-stats-file)
9. [Issue reporting](#9-issue-reporting)
    1. [Knows issues with 3rd party scripts](#91-knows-issues-with-3rd-party-scripts)
10. [FAQ](#10-faq)
    1. [Is it compatible with IADS, CTLD, etc. scripts?](#101-is-it-compatible-with-iads-ctld-etc-scripts)
    2. [I've added the hercules mod, but airdropped units just disapear](#102-ive-added-the-hercules-mod-but-airdropped-units-just-disapear)
    3. [I've added CTLD/Hercules script, but deployed units are not saved after the mission is restarted.](#103-ive-added-ctldhercules-script-but-deployed-units-are-not-saved-after-the-mission-is-restarted)
    4. [It's too difficult/too easy](#104-its-too-difficulttoo-easy)
    5. [I've conquered all zones up to the mountains but now gameplay has slowed down significantly, and flight times across the mountains are too long.](#105-ive-conquered-all-zones-up-to-the-mountains-but-now-gameplay-has-slowed-down-significantly-and-flight-times-across-the-mountains-are-too-long)
    6. [Can I play this in singleplayer?](#106-can-i-play-this-in-singleplayer)
    7. [FC3 aircraft are cold start even in the hot start version of the mission](#107-fc3-aircraft-are-cold-start-even-in-the-hot-start-version-of-the-mission)
    8. [Will you do a version for *[insert map]* ?](#108-will-you-do-a-version-for-insert-map)
11. [Changelog](#11-changelog)

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

### 1.6 Player Spawns

Players can spawn in certain zones as long as it is controlled by the blue coalition. These zones are marked on the map with a green outline.

### 1.7 Capturing a zone

In order to capture a zone, it first needs to turn neutral. This happens when all structures are destroyed in the zone.

Once the zone is neutral it can be captured in one of 3 ways:

- An AI supply convoy or helicopter arrives at the zone
- An AI assault group is inside the zone for a long enough (~5-10 minutes)
- A player deploys a capture squad inside the zone and the squad finishes their mission

>Note: Defensive groups do not have to be destroyed for a zone to turn neutral, and they can keep defending the area even after the coalition lost control of the zone.

### 1.8 Carriers

Carriers look similar to regular zones but behave differently in a number of ways:

- The zone follows the carrier as it moves
- Carriers do not build and deploy AI missions autonomously
- Carrier resources are deducted each time a player takes off from the carrier and refunded when a player lands at a carrier
- If the carrier has run out of resources player spawns are restricted
- Carriers dont get resupplied automatically by the AI, but can be resupplied by players by bringing in supplies from a regular zone, or simply landing any aircraft on the carrier, which will award one aircrafts worth of resources

Players can call in various AI support missions from a carrier after they reach the rank of `O-3 Captain`. Calling in support uses the resources of the carrier. If there are insufficient resources available, the support can not be called in.

The following AI support types can be called in from the Carrier:
|Name|Description|Cost|
|:--:|:----------|:--:|
|CAP|Patrols around a selected frontline zone|1000|
|Strike|Bombs structures in the selected frontline zone|2000|
|Tanker|Orbits around selected friendly zone and provides refueling services|3000|
|AWACS|Orbits around selected friendly zone and provides AWACS services|5000|
|Transport Helo|Transport helicopter flies to and lands at the target zone, capturing it if its neutral, and delivering supplies to it|3000|

Players who reach the rank of `O-7 Brigadier general` can move the carrier using the navigation radio menu of the carrier. The carrier can be commanded to either move to one of the waypoints displayed on the map and wait there, or patrol around one of the displayed zones on the map.

## 2. Logistics
This section covers only player logistics. For AI logistics see the supply AI mission in section 1.4

### 2.1 Supplies

Supplies can be transported by players between zones using transport aircraft.

Players can load as much supply as they want from any friendly zone, as long as the zone has resources to spare, and the players are confortable with flying with the added weight.

To load and unload supply you need to be stationary on the ground, within the limits of a friendly zone, and have at least one cargo door open on your aircraft.

Each unit of supply weighs 1kg.

Managing supplies onboard your aircraft is done using the `Other->Logistics->Supplies->Load/Unload` options in the radio menu. This is only available to aircraft that are allowed to carry supplies. A list of compatible aircraft is provided in [section 2.4](#24-compatible-aircraft)

Loading supplies removes them from the zone.
Unloading them adds them to the zone.

Dying or abandoning your aircraft with supplies on board will cause the supplies to be lost.

### 2.2 Infantry

Some aircraft are capable of deploying infantry squads with various roles to the battlefield. Every squad has a specific purpose, and once they accomplish their mission, can be extracted back to a friendly zone.

Managing squads onboard your aircraft is done using the `Other->Logistics->Infantry->Load/Unload` options in the radio menu. This is only available to aircraft that are allowed to carry infantry. A list of compatible aircraft is provided in [section 2.4](#24-compatible-aircraft)

Loading a squad costs a certain amount of resources from the zone. This is dependant on the type of squad you are trying to load.
The zone will refuse your request if it is low on resources.

You can load as many squads as they fit on your aircraft. You can find aircraft capacity below in [section 2.4](#24-compatible-aircraft)

Unloading a squad at the same zone its been loaded at will unload the squad and refund the resources to the zone.

Once a squad is deployed, it will take a certain amount of time until they complete their mission, after which they can be extracted to a friendly zone to recover some resources. 

Once they are ready to extract they will deploy blue smoke. If not extracted before a set time limit the squad will be lost.

Loading a squad that is ready to extract is done by landing near them and using the `Other->Logistics->Infantry->Extract squad` option from the radio menu.

Available infrantry squads:

| Squad | Description |
|:-----:|:------------|
|Capture| If deployed at a neutral zone, will capture the zone to their side |
|Sabotage| If deployed to an enemy zone, will trigger an explosion at the closest structure to them within the zone, which in turn destroys a random amount of resources as well in that zone |
|Ambush| Squad armed with rifles and RPGs that can be deployed anywhere on the battlefield. Can be used to intercept enemy convoys.|
|Engineers| If deployed at a friendly zone, they will boost production speed, while reducing costs for anything built at the zone for a limited time.|
|MANPADS| Squad armed with rifles for self protection and MANPADS, that can be deployed anywhere on the battlefield. Can be used to provide some protection from enemy aircraft or intercept enemy supply helicopters|
|Spy| Spy disguised as an enemy soldier. If deployed to an enemy zone, will reveal its, and its neighbours, resources and production for 30 minutes, and will allow for Strike missions to be generated towards specific buildings in those zones.|
|Rapier SAM| Small defensive SAM system. Can be deployed anywhere on the battlefield.|


Squad stats

| Squad | Weight | Supply cost | Mission duration | Extraction Time limit | Size |
|:-----:|:------:|:-----------:|:----------------:|:---------------------:|:----:|
|Capture|700kg|200|1 minute|30 minutes*|4|
|Sabotage|800kg|500|5 minutes|30 minutes|4|
|Ambush|900kg|300|20 minutes|30 minutes|5|
|Engineers|200kg|1000|1 minute|30 minutes*|2|
|MANPADS|900kg|500|20 minutes|30 minutes|5|
|Spy|100kg|300|10 minutes|30 minutes|1|
|Rapier SAM|1200kg|2000|60 minutes|30 minutes|8|

>Note: Capture and Engineer squads do not require extraction if they were deployed in accordance with their mission 

### 2.3 CSAR (Combat search and rescue)

Pilots that eject in combat can be rescued by players using transport capable aircraft. The commands relevant to CSAR can be found under the `Other->Logistics->CSAR` option in the radio menu.

This menu holds commands that aid you in finding someone to rescue, as well as the commands you use to extract and unload your targets.

The `Show info` command will show you bearing and distance to the nearest pilot in need of rescue.

The `Smoke marker` command will tell the nearest pilot to deploy a smoke marker nearby, as a visual aid to help find him. A `Flare` command is also available for low visibility conditions.

To be able to extract a pilot you dont necessarily need to land, but you will need to at least hover close to your target. Once you are in position you can extract your target using the `Extract pilot` command. This command has a 1 minute grace period in which you can attempt getting within parameters, for the extract to succeed.

You can bring your rescues back to any frienly zone and unload them using the `Unload` command to regain some resources for the zone.

Each aircraft has a capacity of personnel that it can hold at one time, this limit is specified below in [section 2.4](#24-compatible-aircraft)

### 2.4 Compatible aircraft
By default the following aircraft can participate in logistics
| Aircraft | Can carry supplies | Personnel capacity |
|:---:|:---:|:---:|
|Mi-24P|Yes|8|
|Mi-8MT|Yes|24|
|UH-1H|Yes|12|
|SA342|No|2|

Although community mods are not available in the mission by default, the following mods are supported if you choose to add them.

| Aircraft | Can carry supplies | Personnel capacity |
|:---:|:---:|:---:|
|Hercules*|Yes|92|
|UH-60L|Yes|12|

### 2.5 Hercules mod airdrop support

If you add the Hercules mod, supply and infantry squad air drops are enabled by default.

You need to follow a few steps for this to correctly function:
1. Load the `Generic Crate [20000lb]` cargo onto your aircraft, as many as you desire
2a. Load supplies from the `Other->Logistics->Supplies->Load/Unload` option in the radio menu
2b. Load infantrysquads from the `Other->Logistics->Infantry->Load/Unload` option in the radio menu
3. Drop the crate as you would normally over a zone. Make sure it lands on a clear area and not over trees/buildings.

Supplies loaded onto the aircraft are packed inside the crates until they fill the capacity of whatever number of crates you have loaded.

Supplies loaded into crates do not add aditional weight to the aircraft. (The weight is already provided by the crate)

Supply crates that collide with trees, buildings or units during their descent, or crates that land outside of a zone will be lost.

For the weight calculation to work, supplies most be loaded from the logistics menu **after** the crates have been loaded onto the aircraft. Failing to do so will result in incorrect weight being applied until the next time supplies are loaded/unloaded using the logistics menu.

Each crate object will hold a maximum of 9000 units of supplies.

Each crate dropped is loaded with as many supplies as possible up to its maximum, and depending on how much supply is loaded on the aircraft. 

Example:
- 3 crates on board and 15000 supplies loaded
- First crate dropped contains 9000 supplies, aircraft left with 6000 suppies
- Second crate dropped contains 6000 supplies, aircraft left with 0 supplies
- Third crate dropped contains 0 supplies, aircraft still at 0 supplies

Infantry squads can be deployed the same way. Each dropped crate will auto select one of the loaded infantry squads. You can prepare a specific squad manually using the `Other->Logistics->Loadmaster` option in the radio menu. After your prepared squad is dropped, the next one will be auto selected again, unless you prepare a new one.

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
|Deploy Squad| Deploy specified squad to specified zone.|Infantry transport capable aircraft [section 2.4](#24-compatible-aircraft)|

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

This contains your name, XP, CMD tokens, rank, and survival multiplier.

### 4.4 GCI menu

The GCI menu lets you set a warning radius around you, in which you will recieve reports of any detected units.

To activate reports you have to choose a warning radius from the `Other->GCI->Set Warning Radius` option in the radio menu.
You can disable reports using the `Other->GCI->Disable` option.

The selected option will persist through aircraft changes, respawns and mission/server restarts.

> Note: This is not an all-seeing eye of Sauron. You will only recieve reports of aircraft that were detected by search radars, early warning radars, and AWACS on your side.

## 5. Player XP, Ranks, and Command tokens

You gain XP by completing missions, killing enemies and delivering resources.
After a certain amount of XP you will rank up.

Once you reach rank ``E-6`` you will have a chance to earn CMD tokens when you complete a mission. The higher your rank the better your chances.

You can spend CMD tokens using the ``Command & Control`` radio menu. Once you buy an item, it will deduct the displayed number of CMD tokens from your account, and instructions will be displayed on how to use the bought item. In some cases you will be directed to open the radio menu again and select a target for your bought item from a menu of zones on the frontline.

Available CMD items:

|Item|Description|
|:---:|:----|
|Smoke markers|Will mark 5 enemies at the zone with red smoke|
|JTAC|Will spawn a JTAC drone at the chosen zone that will lase enemies for you. Lasts 30 minutes or until the zone runs out of enemies|
|Priority Zone|The selected zone will become a priority for your coalition. All AI missions will first target this zone if possible, and choose an alternative target if the selected one is not viable. You can use this to prioritize attacks on an enemy zone, captures on a neutral zone, and resupplys on a friendly zone. Lasts about 1 hour |
|Hack comms|Has a chance to reveal resources and production information of zones near the frontline(success rate 50%)|
|Bribe officer|Has a chance to reveal resources and production on almost all enemy zones. (success rate 50%)|
|Shell zone|Artillery will shell the enemy in the selected zone|
|Sabotage|Saboteurs will be sent to the selected zone to plant explosives at one of its buildings. (succes rate 90%)|

The amount of XP earned can be increased by staying in the same aircraft for longer periods of time. After 10 minutes of flight time, an XP multiplier will start growing slowly from 1.0x up to 5.0x. The current value of the multiplier can be seen in the player information menu. This survival bonus is applied at the time the XP is earned. 

You can secure your multiplier by landing at a friendly zone and shutting down your engines. While the multiplier is secured, you can freely switch to a different aircraft or exit the game without reseting it to 1.0x. Taking off will remove the secure status. Switching to a different aircraft, or respawning for any reason while not secured will reset the multiplier. 

Secured status can be verified with the `Other->Information->Player` option, where the `[SECURED]` label will be displayed next to the multiplier if secured.

## 6. Editing the mission to suit your needs

- You can add any client aircraft you want anywhere on the map. Should you add it inside the borders of a zone, the slot will be blocked according to the state of the zone. No extra effort required on your part to make it work.
- Due to limitations with the DCS scripting API, multiple client aircraft in the same group are not supported. Please limit all slots to single aircraft groups, otherwise the radio menu and some other features will not work correctly.
- You **can not** adjust difficulty by deleting AI aircraft from the mission editor. Doing so will result in script errors.
- Logistics capable aircraft where categorized by what maked logical sense on what they can carry. In case you would like to enable logistics for other aircraft you can do so by adding a doScript action afther the scripts are loaded in the initialization trigger in the mission editor and overriding the values in there like this:

```lua
PlayerLogistics.allowedTypes['Mi-24P'] = { supplies = true, personCapacity = 8 }
PlayerLogistics.allowedTypes['Mi-8MT'] = { supplies = true, personCapacity = 24 }
PlayerLogistics.allowedTypes['UH-1H'] = { supplies = true, personCapacity = 12}
PlayerLogistics.allowedTypes['Hercules'] = { supplies = true, personCapacity = 92 }
PlayerLogistics.allowedTypes['UH-60L'] = { supplies = true, personCapacity = 12 }
PlayerLogistics.allowedTypes['Ka-50'] = { supplies = false }
PlayerLogistics.allowedTypes['Ka-50_3'] = { supplies = false }
PlayerLogistics.allowedTypes['SA342L'] = { supplies = false, personCapacity = 2}
PlayerLogistics.allowedTypes['SA342M'] = { supplies = false, personCapacity = 2}
PlayerLogistics.allowedTypes['SA342Minigun'] = { supplies = false, personCapacity = 2}
PlayerLogistics.allowedTypes['AH-64D_BLK_II'] = { supplies = false }
```
- You only need to add the lines for the aircraft you want to change.

- There is currently no easy way to adjust difficulty. The flow of the mission depends on many factors such as cost of AI groups, default build speeds, the flow of resources to each zone, the decision of each zone on what to build, a BattlefieldManager component that adds some variation to the default build speeds based on battlefield state, a randomized boost factor to build speeds to make either coalition occasionally push harder, and finally the behaviour of the DCS AI. It is unpredictable by nature, and any changes you make might have unexpected side effects.

## 6.1 Config

You can override some values that have to do with balance by running the following code **before** any other scripts are loaded.
```lua
Config = Config or {}
Config.lossCompensation = 1.1 -- gives advantage to the side with less zones. Set to 0 to disable
Config.randomBoost = 0.0004 -- adds a random factor to build speeds that changes every 30 minutes, set to 0 to disable
Config.buildSpeed = 10 -- structure and defense build speed (smaller number longer build times)
Config.supplyBuildSpeed = 85 -- supply helicopters and convoys build speed (smaller number longer build times)
Config.missionBuildSpeedReduction = 0.12 -- reduction of build speed in case of ai missions (smaller number longer build times)
Config.maxDistFromFront = 129640 -- max distance in meters from front after which zone is forced into low activity state (export mode)
Config.restrictMissionAcceptance = true -- if set to true, missions can only be accepted while landed inside friendly zones

-- specify how many of each mission type can be present at the same time on the mission board
-- note that increasing the number of some of these can result in multiple missions getting generated against the same targets
Config.missions = { 
    ['cap_easy'] = 2,
    ['cap_medium'] = 1,
    ['tarcap'] = 1,
    ['cas_easy'] = 2,
    ['cas_medium'] = 1,
    ['cas_hard'] = 1,
    ['bai'] = 1,
    ['sead'] = 3,
    ['dead'] = 1,
    ['strike_veryeasy'] = 2,
    ['strike_easy'] = 1,
    ['strike_medium'] = 3,
    ['strike_hard'] = 1,
    ['deep_strike'] = 3,
    ['recon_plane'] = 3,
    ['recon_plane_deep'] = 3,
    ['anti_runway'] = 2,
    ['supply_easy'] = 3,
    ['supply_hard'] = 1,
    ['escort'] = 2,
    ['csar'] = 1,
    ['scout_helo'] = 3,
    ['extraction'] = 1,
    ['deploy_squad'] = 3
}

Config.missionBoardSize = 15 -- sets how many missions can be on the mission board simultaneously, increasing this too much will cause the list to be too not fit on the screen anymore, and in extreme cases cause performance issues
```

You can paste this in a do script action that is run **before** the mission scripts. You can leave out the values you do not wish to change.
I recommend only making small changes, only to one value at a time, and playing for a while to see how it feels.

The values listed above are the defaults.

## 6.2 Randomized start

You can randomize the campaign when starting a new save by creating an empty file named `randomize.lua` in the `C:\Users\<windows_username>\Saved Games\DCS.openbeta\Missions\Saves\` folder.

Next time you start the mission without a save file, it will attempt randomizing the state of the zones.

Note that this is in no way guaranteed to be balanced and your experience may vary. It is intended as a bonus feature, so treat it as such.

## 7. Persistence
This mission comes with persistance, which allows the mission to remember its state when you exit the mission and continue from there once you start it up again.

To enable persistance you have to allow the mission environment inside DCS to read and write to and from your file system. To do this you will need to edit `\Scripts\MissionScripting.lua` inside your DCS or DCS server installation folder.

Change the following section:
```lua
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
```lua
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

Player stats, such as XP is stored in a separate file in the same location called `player_stats.json`, and can be reset separately from mission progress as needed.

> Note: AI groups that are restored from a save file will always be at full numbers and at full loadout, even if part of the group was destroyed previously, or they have expended some of their munitions

### 7.1 Persistence for mission time and weather randomization

Additional (experimental) persistence can be enable by installing and configuring the [TimePersistence](https://github.com/Dzsek/TimePersistence) mod.
All settings (time, weather, temperature, wind) are enabled by default. These can be configured by editing the properties of the ``props`` zone int the mission editor near Batumi in the south of Caucasus.

## 8. Running the mission on a server

### 8.1 Slotblock

For players to be prevented from spawning at enemy zones, the included `slotblock.lua` file must be placed in your servers `C:\Users\<windows_username>\Saved Games\DCS.openbeta\Scripts\Hooks` folder, and the server restarted, in case it was already running at the time.


### 8.2 Stats file

In addition to the save file the mission also writes to a file called `player_stats.json` in `C:\Users\<windows_username>\Saved Games\DCS.openbeta\Missions\Saves\`

This is a JSON file containing the information about the currently running mission, and is updated once per minute.

Information in the file includes players who have played the mission and their XP, what aircraft players are currently flying, and the name of the zones broken down into 3 lists for red, blue, and neutral coalitions.

You can use the information in this file to export a mission status to a discord server or to a website, or whatever other use you can come up with for it.


## 9. Issue reporting

If you find any bugs, issues, or you find the campaign does not work according to what is described in this manual, please report them on the Foothold Discord under  [#pretense-bug-reports](https://discord.com/channels/959044877470027848/1031459721313517578) channel. 

Here's a [Discord invite](https://discord.gg/PtPsb9Mpk6) if you are not already a member.

Try to include your dcs.log file and your Pretense save file into your bug report if possible.

Please only report issues with unmodified versions of this campaign. I can't track down issues caused by modifications. Even if you modified a seemingly unrelated part, it can still cause problems in other unforseen ways.

If you encounter issues with modified versions, your best bet is to either retrace your steps, or redownload the original version.

### 9.1 Knows issues with 3rd party scripts

- Splash_Damage_2_0 script: objects destroyed by secondary explosions do not count as destroyed by players, preventing the kills form registering for certain objectives
- CTLD script: objects deployed with ctld scripts are not tracked by the mission and not persisted between restarts
- Hercules airdrop script: objects spawned from the hercules airdrop are not tracked by the mission and not persisted between restarts

## 10. FAQ

### 10.1 Is it compatible with IADS, CTLD, etc. scripts?

Most likely not, but cant hurt to try. The campaign is almost exclusively run from scripts, I can not guarantee its compatible with every other script out there.

### 10.2 I've added the hercules mod, but airdropped units just disapear

You need to add the Hercules airdrop script to the mission. It is not added by default. Only Squads from the Logistics menu built into the mission are supported by default.

### 10.3 I've added CTLD/Hercules script, but deployed units are not saved after the mission is restarted.

Units created by 3rd party scripts are not tracked, saved, or restored. Persistence only works with objects created and maintained by the campaign itself.

### 10.4 It's too difficult/too easy

See the last point in [section 6.](#6-editing-the-mission-to-suit-your-needs)

### 10.5 I've conquered all zones up to the mountains but now gameplay has slowed down significantly, and flight times across the mountains are too long.

Yes, geography tends to have that effect. Best thing you can do at this point is concentrate on gaining a foothold in one of the zones across the mountains to have a staging point for ground forces.

### 10.6 Can I play this in singleplayer?

It is possible to finish the whole campaign in singleplayer, but some areas might prove a bit difficult, depending on what modules you have available to you and your patience and skill.

### 10.7 FC3 aircraft are cold start even in the hot start version of the mission

This is intentional, as FC3 aircraft can not be rearmed with the engines running. The startup is relatively simple and fast anyway.

### 10.8 Will you do a version for *[insert map]* ?

I probably wont.
If I will, I wont tell you about it unless it's close to release.

### 10.9 I've cleared a zone but no AI is coming to capture it

There can be several reasons why a zone does not instantly try to capture neighbouring zones.
 - its supply groups are already deployed on different missions
 - its unable to build supply missions due to the building needed to produce them being destroyed or not built yet
 - it does not have enough resources to finish building the supply mission
 - it is currently working on building something else

Note that the AI will not always make the best and most optimal decission.

### 10.10 Enemy units have spawned in the enemy zone while I was over it and promptly shot me down

Each zone will deploy any defensive or offensive groups as soon as it finishes building them. It does not stop working just because their enemy is close. Try not to hang around too long over enemy zones. 

Alternatively, complete recon missions, drop spies in enemy zones, or use the CMD options available to reveal what the enemy is working on and what their progress is, so you don't get caught off-guard. 

If a zone is currently attempting to repair a damaged defensive group, destroying a unit of said group will reset the zones progress on repairing it.

### 10.11 Why cant I rearm at this zone?

Not every zone is setup as a FARP. Only zones that you can spawn at and zones that have airfields will allow you to rearm and refuel.
Some static objects that serve as structures for the zones do have FARP in the name, but this alone does not mean the zone is setup as a FARP.

## 11. Changelog

### v1.0 - 6 June 2023 

- Initial Release

### v1.0.1 - 9 June 2023

- Added supply helicopters to Lima 
- Changed TACAN of tankers to not interfere with datalink
- Fixed CSAR pilots not registering for logistics functions

### v1.0.2 - 11 June 2023

- Made zone information show up in spectator mode
- Fixed infantry extraction missions not showing up
- Fixed incorrect capacity indication for CSAR
- Added guidance messages to infantry extraction and CSAR missions

### v1.1 - 29 June 2023

- Added notification when a zone changes owner
- Added new deployable infantry type: Spy
- Added CMD token earning chance based on rank
- Added Command & Control menu (Smoke, JTAC, Set priority zone, Hack enemy comms, Bribe enemy officer)
- Added simple version of Strike mission (kill any 1 building)
- Added Deploy Squad mission type
- Added reason to mission failure message
- Added persistence for deployed infantry and ejected pilots
- Added F-15E slots
- Adjusted altitude of route between Lima and Tyrnyauz as supply helicopters were crashing into mountains
- Fixed being able to unload extracted squads at enemy or neutral zones
- Replaced oil pump buildings with old ED model, SA assets were too hard to kill
- Attempted fix for strike mission failing rarely when target is destroyed by player
- Sabotage squad now targets closest structure to deploy point
- Refactored building and defensive group spawning at zones to use script templates instead of ME defined ones
- Reworked defensive group composition of most zones
- Zones now spawn a small defensive squad upon capture, this group can not be repaired
- Mission board will now hide missions that are not compatible with current aircraft
- Assault convoys will now attempt to disperse upon meeting enemies, instead of just stopping in their tracks
- Fixed Mi-8 not being able to load anything while front side door is open

> Note: this patch is not compatible with old saves and will reset mission progress.

### Caucasus v1.1.1 - 29 June 2023

- Fixed crash on completing mission before player has rank

### Caucasus v1.1.2 - 29 June 2023

- Fixed crash starting strike mission with specific building as target

### Caucasus v1.1.3 - 29 June 2023

- Fixed wrong bluefor infantry model being used

### Caucasus v1.1.4 - 2 July 2023

- Added closest zone name to BAI, CSAR, Extract and Escort mission targets to mission short description (replaces MGRS)
- Fixed JTAC clear target and priority menus
- Attempted fix for ejected pilot replacement spawning in 0,0 position
- Slightly Increased distance and altitude limits for hover pickups of ejected pilots (alt 50->70, dist 50->100)
- Added support for persistence of time and date (see [section 7.1](#71-persistence-for-mission-time-and-weather-randomization))
- Added support for randomization of weather on startup (see [section 7.1](#71-persistence-for-mission-time-and-weather-randomization))

### Caucasus v1.1.5 - 2 July 2023

- Fixed CMD points not getting awarded
- Fixed ground convoy disperse not working
- Fixed aircraft not getting sent home properly

### Caucasus v1.1.6 - 3 July 2023

- Removed winds (they were included accidentally)
- Enabled EPLRS for all AWACS

### Caucasus v1.1.7 - 3 July 2023

- Fixed another crash on CMD reward

### Caucasus v1.1.8 - 4 July 2023

- BAI mission now correctly tracks player kills
- Fixed crash on CMD reward when completing helicopter missions that end on the ground

### Caucasus v1.1.9 - 5 July 2023

- Rebalanced CMD chance
- Reduced bribe effectiveness to 50%
- Added marker for zones that have player spawns active
- Extract pilot menu option now enabled a 1 minute timer in which you can get into the correct parameters for the extract to happen

### Caucasus v1.1.10 - 8 July 2023

- Fixed persistence when groups saved within target zone
- Fixed units spawning outside of spawnzones ocasionally

### Caucasus v1.1.11 - 9 July 2023

- Fixed crash on attempting to spawn blue off map supply cargo plane
- Fixed crash when bribe command is used

### Caucasus v1.2 - 11 July 2023

- Added GCI menu
- Fixed crash on inexistent pilot unit during extract grace period
- Fixed resource recovery ratio from landed aircraft

### Caucasus v1.2.1 - 11 July 2023

- Fixed script error when radar somehow detects an inexistent object

### Caucasus v1.3 - 13 July 2023

- Added support for Hercules Supply and Infantry drops
- Unified logistics capacity for squads and extracted pilots
- Now able to load multiple infantry squads as long as capacity allows it
- Added Rapier SAM as a deployable squad

### Caucasus v1.3.1 - 15 July 2023

- Accept/Join at the end of the dial menu is now autodetected as long as the code is correct
- Removed digits 6-9 of dial menu to reduce size of menu. Mission generation adjusted to not use these digits

### Caucasus v1.3.2 - 17 July 2023

- Reduced speed of tankers
- Replaced S-3B tanker with KC-130
- Reaching certain ranks now awards a few CMD points
- GCI now includes target aspect
- GCI limited to top 10 contacts
- GCI now reports altitude in segments of 250m instead of 1000m (if metric is used)
- Increased spread of SAM spawns from 150m to 300m
- AI Helicopters will now attempt to engage ground units they encounter on their route, not just at their destination
- Added option to randomize the state of the zones when starting a new save (see [section 6.2](#62-randomized-start))

### Caucasus V1.3.3 - 22 July 2023

- Fixed groups despawned due to getting blocked not refunding resources
- Deploy Squad mission now only gives instant rewards when deploying Engineers
- Fixed 50% fuel on one of the F-15E slots in Batumi
- Corrected tanker speed

### Syria Cold War V1.0.1 - 22 July 2023

- Fixed groups despawned due to getting blocked not refunding resources
- Deploy Squad mission now only gives instant rewards when deploying Engineers
- Removed fuel tanks from MB-339 AIs on Kiryat to allow it to take off on the short runway.
- Marked Jasim as a spawn point

### Caucasus V1.3.4 - 2 Aug 2023

- Fixed crash when CSAR target despawns or is destroyed mid mission
- Added message for when Hercules cargo drop fails due to the crate crashing into something

### Syria Cold War V1.0.2 - 2 Aug 2023

- Fixed crash when CSAR target despawns or is destroyed mid mission
- Adjusted spawn pos of El Taebah convoys to reduce chance of blockage
- Adjusted client Su-25 at Kiryat to stop it from rolling off the taxiway on spawn
- Added message for when Hercules cargo drop fails due to the crate crashing into something


### Caucasus V1.3.5 - 9 Aug 2023

- Fixed TARCAP target player list not showing
- JTAC now lasts 60 minutes
- Fixed AI patrol missions choosing enemy zones to patrol
- Zones that are more then 70 nm away and more then 4 hops away from the frontline will now go to export operating mode even if they would otherwise be forced to stay active, these will still build aircraft in export mode
- Zones now get instantly built up if they get bumped up to normal operating mode, as far as the resources allow it

### Syria Cold War V1.0.3 - 9 Aug 2023

- Fixed TARCAP target player list not showing
- Fixed AI patrol missions choosing enemy zones to patrol
- Fixed some AI patrols having wrong default task
- Adjusted fuel of helicopters to 50%
- Zones that are more then 70 nm away and more then 4 hops away from the frontline will now go to export operating mode even if they would otherwise be forced to stay active, these will still build aircraft in export mode
- Zones now get instantly built up if they get bumped up to normal operating mode, as far as the resources allow it

### Caucasus V1.3.6 - 20 Sept 2023

- Fixed crash when player C130 dies before cargo crates hit the ground
- Airbases and FARPs now forced to same coalition as zone
- Corrected squad extraction smoke color to Blue as per manual
- Corrected Hercules cargo drop position calculation
- Squads now spawn a bit further from the helicopter
- Fixed crash on trying to restore a zone from culling but zone is neutral

### Syria Cold War V1.0.4 - 20 Sept 2023

- Fixed crash when player C130 dies before cargo crates hit the ground
- Airbases and FARPs now forced to same coalition as zone
- Corrected squad extraction smoke color to Blue as per manual
- Corrected Hercules cargo drop position calculation
- Squads now spawn a bit further from the helicopter
- Fixed crash on trying to restore a zone from culling but zone is neutral

### Syria V1.0.1 - 20 Sept 2023

- Fixed crash when player C130 dies before cargo crates hit the ground
- Airbases and FARPs now forced to same coalition as zone
- Corrected squad extraction smoke color to Blue as per manual
- Corrected Hercules cargo drop position calculation
- Squads now spawn a bit further from the helicopter
- Fixed crash on trying to restore a zone from culling but zone is neutral
- F-14B player spawns now have INS fast align enabled
- Added missing JTAC option

### Caucasus V1.3.7 - 1 Dec 2023

- Fixed issues introduced from scripting API changes (getCategory())
- Updated mist to latest version

### Syria Cold War V1.0.5 - 1 Dec 2023

- Fixed issues introduced from scripting API changes (getCategory())
- Updated mist to latest version

### Syria V1.0.2 - 1 Dec 2023

- Fixed issues introduced from scripting API changes (getCategory())
- Updated mist to latest version

### Caucasus V1.3.8 - 3 Dec 2023

- Fixed issue where ground assault convoys were stopping to engage already destroyed enemies

### Syria Cold War V1.0.6 - 3 Dec 2023

- Fixed issue where ground assault convoys were stopping to engage already destroyed enemies

### Syria V1.0.3 - 3 Dec 2023

- Fixed issue where ground assault convoys were stopping to engage already destroyed enemies

### Caucasus V1.4.0 - 15 Dec 2023

- Added xp multiplier bonus for surviving longer times in the same aircraft
- Ground assault convoys now attempt repositioning if they stopped to engage the enemy but have been waiting for a long time
- Fixed TARCAP mission not failing on some occasions when it should have
- Added manual landing validation option to radio menu (For cases when the game fails to detect a landing)
- Added config option to disable having to be landed and inside friendly zone to accept missions
- Added persistent player configuration radio menu
- Players can now enable a warning from the radio menu, that shows up while they are landed and have no active mission
- Added logic to attempt getting ground convoys unstuck
- GCI settings are now persistent between respawns, aircraft changes and mission/server restarts
- Added EPLRS task to AWACS

### Syria Cold War V1.1.0 - 15 Dec 2023

- Added xp multiplier bonus for surviving longer times in the same aircraft
- Ground assault convoys now attempt repositioning if they stopped to engage the enemy but have been waiting for a long time
- Fixed TARCAP mission not failing on some occasions when it should have
- Added manual landing validation option to radio menu (For cases when the game fails to detect a landing)
- Added config option to disable having to be landed and inside friendly zone to accept missions
- Added persistent player configuration radio menu
- Players can now enable a warning from the radio menu, that shows up while they are landed and have no active mission
- Added logic to attempt getting ground convoys unstuck
- GCI settings are now persistent between respawns, aircraft changes and mission/server restarts
- Replaced BMP-2 with BMP-1 units
- Downgraded some of the AA weapons of the AI

### Syria V1.1.0 - 15 Dec 2023

- Added xp multiplier bonus for surviving longer times in the same aircraft
- Ground assault convoys now attempt repositioning if they stopped to engage the enemy but have been waiting for a long time
- Fixed TARCAP mission not failing on some occasions when it should have
- Added manual landing validation option to radio menu (For cases when the game fails to detect a landing)
- Added config option to disable having to be landed and inside friendly zone to accept missions
- Added persistent player configuration radio menu
- Players can now enable a warning from the radio menu, that shows up while they are landed and have no active mission
- Added logic to attempt getting ground convoys unstuck
- GCI settings are now persistent between respawns, aircraft changes and mission/server restarts
- Added EPLRS task to AWACS

### Caucasus V1.4.1 - 17 Dec 2023

- Fixed crash on AWACS tasking 

### Syria Cold War V1.1.1 - 17 Dec 2023

- Fixed crash on AWACS tasking (not relevant as no AWACS in cold war, main script change only)

### Syria V1.1.1 - 17 Dec 2023

- Fixed crash on AWACS tasking

### Caucasus V1.4.2 - 18 Dec 2023

- Fixed AWACS datalink

### Syria Cold War V1.1.2 - 18 Dec 2023

- Fixed AWACS datalink (not relevant as no AWACS in cold war, main script change only)

### Syria V1.1.2 - 18 Dec 2023

- Fixed AWACS datalink

### Caucasus V1.4.3 - 19 Dec 2023

- Added FCR to Apache spawns
- Save now resets if any of the coalitions does not own a single zone at mission load
- Join code now shows in mission details in air if mission accept restrictions are disabled

### Syria Cold War V1.1.3 - 19 Dec 2023

- Save now resets if any of the coalitions does not own a single zone at mission load
- Join code now shows in mission details in air if mission accept restrictions are disabled

### Syria V1.1.3 - 19 Dec 2023

- Added FCR to Apache spawns
- Save now resets if any of the coalitions does not own a single zone at mission load
- Join code now shows in mission details in air if mission accept restrictions are disabled

### Caucasus V1.4.4 - 20 Dec 2023

- Fixed Config.restrictMissionAcceptance being overriden when set to false according to instructions
- Fixed error when loading supplies into C130 mod without having crates on board
- Fixed error when droping supply crate over invalid terrain
- Fixed mission file serializer format to be similar to EDs (should fix some compatibility issues with 3rd party tools)

### Syria Cold War V1.1.4 - 20 Dec 2023

- Fixed Config.restrictMissionAcceptance being overriden when set to false according to instructions
- Fixed error when loading supplies into C130 mod without having crates on board
- Fixed error when droping supply crate over invalid terrain
- Fixed mission file serializer format to be similar to EDs (should fix some compatibility issues with 3rd party tools)

### Syria V1.1.4 - 20 Dec 2023

- Fixed Config.restrictMissionAcceptance being overriden when set to false according to instructions
- Fixed error when loading supplies into C130 mod without having crates on board
- Fixed error when droping supply crate over invalid terrain
- Fixed mission file serializer format to be similar to EDs (should fix some compatibility issues with 3rd party tools)

### Caucasus V1.4.5 - 21 Dec 2023

- Fixed unit category detection after latest change from ED which could cause script errors

### Syria Cold War V1.1.5 - 21 Dec 2023

- Fixed unit category detection after latest change from ED which could cause script errors

### Syria V1.1.5 - 21 Dec 2023

- Fixed unit category detection after latest change from ED which could cause script errors

### Caucasus V1.4.6 - 27 Dec 2023

- Fixed config menu not appearing for players of low rank
- Fixed error when target of CSAR mission is killed

### Syria Cold War V1.1.6 - 27 Dec 2023

- Fixed config menu not appearing for players of low rank
- Fixed error when target of CSAR mission is killed

### Syria V1.1.6 - 27 Dec 2023

- Fixed config menu not appearing for players of low rank
- Fixed error when target of CSAR mission is killed

### Pretense V1.5 - 29 Dec 2023

>Note: Unified version numbers, changes from now on will refer to all Pretense missions, except if otherwise specified

- Added new CMD options (Sabotage and artillery) (see [section 5](#5-player-xp-ranks-and-command-tokens))
- You can now secure your survival bonus if you shut down your aircraft while landed at a friendly zone (see [section 5](#5-player-xp-ranks-and-command-tokens))

### Pretense V1.5.1 - 5 Jan 2024

- Command & Control menu moved to always be the last option in the radio menu
- Reduced accuracy of Artillery CMD option
- Fixed runway bombing mission progress not registering
- Syria Cold War: removed SA-19 from SA-6 group

### Pretense V1.5.2 - 13 Jan 2024

- Spy squad can now generate Strike mission targets on successful completion of their mission
- Increased size of mission board
- Mission board size and mission availability can now be configured
- Fixed another error during CSAR when pilot is killed
- Rebalanced CMD earnings and costs
- Increased priority zone CMD to 2 hours
- Increased accuracy of Artillery CMD option

### Pretense V1.6 - 21 Jan 2024

> Note: This update will start a new mission save file, resetting your mission progress. The player profiles will remain unaffected.

- Added Carriers

### Pretense V1.6.1 - 22 Jan 2024

- Replaced F-14s of Apex Flight with F/A-18s cause they were misbehaving
- Split Harriers on Invincible into two separate flights
- Limited Zone selection of CAP flights to near frontline to reduce clutter in radio menu
- Tentative fix for error when updating state of AI aircraft
- Fixed issue with activating multiple target menus at once generating wrong menus

### Pretense v1.6.2 - 23 Jan 2024

- Fixed error when assigning SEAD missions
- Fixed issue with Harriers landing immediately after takeoff from carrier

### Pretense v1.6.3 - 31 Jan 2024

- Fixed script error on Hercules cargo drop collision
- Fixed carrier stop command not being applied when reaching a goto waypoint
- Fixed Nova flight on Caucasus not spawning on LHA
- Fixed missing waypoints from kneeboards