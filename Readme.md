<font color=#66ccff>edit by lty4ever</font>
# Property Data Type
* Keyword def can be used as Global Default Value
	+ Vector : ([X],[Y])   0 -> (0,0) 	[dd]% -> Percentage of Screen
	+ Double : Number
	+ Boolean : true(t) / false(f)
	+ String : Text
* Shortened Name can be used eg. glo -> GLOBE.png/ bh -> BLACK_HOLE.png
# Entity’s Property
	## + Vector
1.	loc = Location = 0
2.	vel = Velocity = 0
3.	acc = Acceleration = 0
4.	siz = Size = (100,100)
	## + Double
1.	mas = Mass = 10
2.	elc = Elasticity = 1
3.	trc = Tracing Position Count = 20
4.	mot = Motion(Displacement) Scale = 0.5
	## Boolean
1.	mtg = Mutual Gravity (Common Gravity) = false
    true : calculate through G * m1 * m2 / r^2
    false : Constants Gravity only in reference to the mass of gravity source.
2.	gvig = Ignore Self-Gravity = false
    true : Ignore gravitation release from the entity
    false : attract other entities (exert force toward the source)
3.	spt = Susceptibility = false
    true : Can be affected by other entities’ force
    false : Extremely stable, unaffectable
4.	trcv = Trace Visibility = false
    true : Track the position of the entity and show on the stage
5.	velv = Velocity Visibility = false
    true : Display the velocity’s direction and relative scale on the stage
6.	acv = Acceleration Visibility = false
    true : Display the acceleration’s direction and relative scale on the stage
7.	mkv = Mark Visibility = false
    true : Display the frame (Component Scale) of the entity on the stage
8.	undrg = Undraggable = false
9.	rcvg = Receive Global(Stage’s) Gravity = false
10.	rcvf = Receive Global(Stage’s) Friction = false
	## String
1.	tag = Tag = “ent@[hashCode]”
2.	img = Image = “glo”
# Stage Property
* Get access to stage’s property through tag stg
	## Vector
1.	envg = Environmental Gravity = (0,2.4)
	## Double
1.	fric = Environmental Friction = -0.02
2.	delta = Timer Operating Interval = 30
	## Boolean
1.	bnd = Boundary = false
    true : Place a Boundary Round the Screen
2.	bak = Background = false
    true : Place a half-transparent background
    false : Remove the background.
# Global Property
* Get access to global property through tag def
	## String
3.	path = Default relative path of the Resource Directory = “”
# Mapping of Property Name & value
* Space can not appear in the Mapping Statement
[propertyName](+)=[value],[propertyName](+)=[value],...
# Command
* tag = entityTag / stg(Stage) / def(Global Property or Default Value) / all(All entities)
1.	add [mapping of propertyName&value]
    Add an entity with specific property(s) to stage
2.	[tag].set [mapping of propertyName&value]
    Set the property(s) of specific entity(s)/stage
3.	[entityTag].del
    Delete specific entity(s) from the stage
4.	[tag].get [propertyNameList]
    Print out specific property(s) of entity(s)/stage
5.	preset [px file path]
    execute all the command in the px file
6.	start
    Enable the timer to tick
7.	pause
    disable the timer
8.	end
    exit the simulator

# Directory Structure
1.	./RES
    Resource Directory
2.	./RES/IMG
    Image Directory
3.	./RES/PRS
    Preset Directory

# Examples
1. def.set vel=(10,10)
   Set Global Default Velocity to (10,10)
2. add tag=e1,vel=def,img=bh
   Add an entity with tag of “e1”, image of blackhole and default velocity
3. stg.set bnd=t,delta=20
   Set a Boundary around the Screen and change interval of the timer to 20ms
4. add tag=e2,img=def,loc=(50%,50%)
   Add an entity with tag of “e1”, default image and location at the Center of the Screen
5. preset traceAll.px
   Read command in the preset File traceAll.px (all.set trcv=t)
6. all.set vel+=(10,10),siz+=(10,10)
   Add (10,10) to all the entities’ size and velocity
7. all.del
   Delete all the entities from the stage




