# Codepath-Week-9-Assignment
Using Honeypot and Google Cloud VMs to practice network attacks

For this assignment I used Google Cloud services to host 4 seperate honeypot VMs running Ubuntu 14.04
- Admin VM (general admin VM to oversee network)
- [Dionaea VM](https://github.com/DinoTools/dionaea)
- [Snort VM](https://github.com/threatstream/mhn/wiki/Snort-Sensor)
- [p0f VM](https://github.com/threatstream/mhn/wiki/p0f-Sensor)

# Issues encountered:
Installing the correct Ubuntu version and getting all of the honeypot VMs to work correctly was tricky, but in the end all 4 VMs were up and running and communicating.

# Summary of Data
* There were a total of 528 attacks over all 3 honeypots (Dionaea, snort, and p0f) The VMs were active for about 3 hours in the late evening and were left on to collect data. 
* For dionaea there were 285 attacks, p0f: 167 attacks, and snort had 76 attacks. For me, the top port attacked was 80 ( HTTP port, with 134 attacks), followed by port 23 (Telnet port, 89 attacks), and then port 5060 (SIP, 42 attacks), and port 22 (SSH, 18 attacks), another attacked port was 445 the Active Microsoft Directory with 48 attacks.
* Two our of the top 5 hacker attack IP adresses were located in Spain, with 106 attacks, another address from France attacked a total of 48 times.
* For Snort, the most detected signature was "ET DROP Dshield Block Listed Source group 1" with 21 attacks, the second most detected signature was "ET CINS Active Threat Intelligence Poor Reputation IP TCP group 4" which got attacked only 6 times.

When going further into snort you find that the ET DROP signature signafies that the IP is coming from a potential security threat, while the other signature indicates that the IP already has a bad reputation with the ET CINS system.

The attached .json file has the exported data from the honeypot projects.


