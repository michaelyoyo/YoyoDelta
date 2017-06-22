# YoyoDelta

Initial Commit - 

	This is (hopefully) going to be the home of all the design files needed to 
	build the YoyoDelta printer. I'll detail more of the motivation behind this
	and reasons for the design in the future, probably. As it stands, I'll see
	what I can do in the initial commit.

	At present I'm going into my fourth year of engineering school, and like any
	good engineering student, I've seen a few printers and think I can do better.
	I just so happen to be in a good position to do that right now, so I thought
	I would give it a shot.

	The goal of this machine is to try and avoid the flaws of the dozen-ish models
	of printers I have experience troubleshooting maintaining and running, and
	to incorporate the latest and greatest that that the 3D printing world has to
	offer. 

	I do realize the futility in trying to make something with the newest components
	without having the ability to upgrade, so secondary goal here (and my 
	justification for the time) is the make the printer in such a way that its
	easy to upgrade later.

	The current wishlist of features for this printer is quite exhaustive.
		
		-Medium to Large Build Volume (for a desktop machine)
		
		-High Temperature Actively Heated Chamber (>150C)
			*I'm not sure if I can share this subsystem design online
		-Very High Temperature Hot End (>350C)
		
		-High movement speed (>500mm/s)
		-High acceleration/rigidity (reach top speed during 1/2 axis length move?)
		-Precise Enough to Utilize Small Nozzles (<0.3mm)

		-Controlled over Web Browser
		-Numerous Sensors/Monitoring Systems to detect possible faults

	In the end I would love to add soluble support to this but I just don't
	personally think the filament technology is there yet. Ultimaker's PVA
	is the best I've seen but even other PVA's haven't stood up to that. Let
	alone the mess that was my HIPS experiments. Some day this will improve and
	I'll eat my words, but I've got a long enough list right now without worrying
	about dual extrusion.

	So with that being said I've made some initial design decisions detailed below.

		-Printer Style
			-Delta
				-Low Mass (higher acceleration for given rigidity)
				-Traditionally high speed
				-Easy to enclose chamber (no motors/electronics needed)
				-Larger build volumes are common
				-If I'm going to build a printer, I want it to be cool to watch

		-Linear Motion
			-Openbuilds V Slot Rail
				-Not too expensive
				-Easily Available
				-Can be modified with metal wheels for high temperature
		-Frame
			-Openbuilds V Slot and Routed Aluminium Plate
				-Available in varying widths
				-Easy to Assemble/Adjust
				-Routed Plates can add rigidity

		-Motors
			-400step/rev NEMA17 Motors
				-Minimal inductance for high speed travel
				-Higher intrinsic precision (w/out need for microsteps)
				-Easily supported by 3D Printer Electronics
				-Cheaper than Faster/More Precise Alternatives 

		-Electronics
			-DuetWifi for Control
				-Trinamic Stepper Drivers
				-32 Bit Processor
			-PanelDue, RTD Interface
			-MeanWell 24v 400W Open Frame Supply
				-5Vsb for powering DuetWifi
				-PS_On signal to shutdown motors/heaters
				-Plenty of protection for electronics

		-Heaters
			-Generic Kapton Heated Bed
				-Highest Temperature rating readily available
			-E3D v6 w/ RTD 

		-Extruder
			-E3D Titan
				-High Quality
				-Might spring for a Bondtech later but unsure if filament path
					friction will be an issue for the single hobbed gear and
					pancake stepper