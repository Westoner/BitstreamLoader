# BitstreamLoader
Bitstream Loader v1.4
Prerequisites:
To set the voltage and load the bitstream, you must purchase NextJtag V2.

What is Bitstream Loader
Bitstream loader allows you to create and launch, pre-defined mining configurations for coins to mine with FPGAs.

When creating a config, you can follow a few simple steps:
1)	Click Add/Edit Bitstream Config
2)	Chose to Add New, or select and existing config to edit
3)	Browse to the location of the miner program and bitstream, and store the file and path in your config
4)	Browse to the path and location of NextJTag (if used)
a.	Click the Load Bitstream box
b.	Set the desired voltage
c.	Click the Set Voltage box
5)	Set the Miner Params and specify if they are to be loaded at the end, or directly after the miner program (miner file requirement dependent)
6)	Set the number of FPGAs to be used
7)	Set the Launch Delay (adds a delay between running each miner instance (personal preference – I like to let the miner start mining, before launching the next instance)
8)	Set the option to use a pool or a token file
9)	Set the Window Title (this is used to create a unique miner instance window title)
10)	Set the Loop Offset – used for multiple PC instances. If you run 10 FPGAs on PC1 and 10 on PC2, set this to 10 on PC2, so that the rig names and window titles all start from 11. The pool will then show Rig1 to Rig20. 


Setting Voltages and Loading Bitstreams
 	Set the location of NextJTag and (V2 only) set the volatge of your FPGA. Both these settings are ignored if “Load Bitstream” is not checked.

 	Num FPGAs: This value is used in a few ways… 
1) Controls the number of instances to launch, when Use All FPGAs is set.
2) Used as part of the window title of each miner instance launched.
3) Used as a unique identifier for the Rig Name Format, in the pools section.
4) When Use 1 FPGA is set, It’s used as the single instance window title and rig name format, if used.
	
 	Loop Launch Delay: Adds a delay between launching all 

Create a single Master launch file or a Master with separate launch files for each FPGA
 
When checked, “Separate Instances (with loop) allows you to create a launch-file for each FPGA, and one Master file to launch them all. The Master file uses the Miner Launch Delay value, and randomizes it, so that all the loops are not running at identical times. 
 
If we use the above configuration: The Master file would be named “Nexus Variable - Nexus RU.cmd” and each separate miner file would be named “Nexus RU-1.cmd”, “Nexus RU-2.cmd” etc. The Master file would look like this:
 
And the separate files would look like this:
 
The above file launches the miner and waits until it shuts down, at which point it will re-launch it, unless you click the red cross to emergency close, which then will terminate the miner and upon returning to the launch file, you will be asked if you want to terminate the batch job. If the miner restarts, the number of restarts is recorded in the launch file. The launch file starts minimised to prevent cluttering up the screen.
 
Adding Configurations
 
Adding configs is simple! Provide a Config Title and use the Load buttons to locate the various elements.
Location or Params allows you to control where params are added. Some go between the Miner and pool, while others after the pool. If you need both, try adding the params after the Pool Port in the pool config, like this :8433 -u
No. FPGAs is used in loops.
Window Title is for the CMD window title of the miner. A loop runs to create the files, using from 1 to No. FPGAs, which provides the unique Window Title for each miner instance.
Miner Launch Delay sets the time between launching each instance of the miner.
Write all new settings for a new config.
Keep the same title to edit the current config.
Add text to the title, to clone the current config, into a new config. 
 
Adding and Editing Pool Configurations
 
Chose to add a new Pool Configuration, or edit an existing one. Add text to the title of an existing config to clone it. You must have a Bitstream Configuration selected, to add/edit a Pool Config.
The Port is appended directly onto the pool URL, like this mypool.comPool.
So if the miner needs this format: eu.mypool.com:1234 then add :1234 in the Port box
And if the miner needs this format: eu.mypool.com 1234 then add  1234 in the Port box (space before port)
Wallet well here’s a suggestion: Let me know what coin you’re mining, and I’ll let you have my wallet address 😊. If not, then just add your own ☹

Adding and Editing Token File Configurations
 
