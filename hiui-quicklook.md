
Time limited review, what I look for and where:
- Status Overview page
	- Platform(hardware, Vcmp/Tenant, or virtual)
	- Version (does it have a EHF applied)
	- Quick Links section, Do I see the link all, next to the bigip.conf file?  This indicates the use of partitions, which is also a precursor for Route domains in many cases.
	- System
		- Status - does it show Active(meaning that traffic is passing through this device), take note of the time, bigger is not always better.
		- Uptime - If over 180 days then it is likely that the admin has not been tracking the Quarterly Security Notifications. This also impacts the accuracy of the statistics counters we will review later.
		- Physical Memory - for the virtual editions, is this adequate?
		- CPU totals - Min 2, no matter the platform in production.  In VCMP and F5OS Tenant situations this also dictates the RAM assigned.
	- Configuration Totals
		- Overall this should drive the management provisioning setting above a certain level.
		- Monitor instances - click the number to see if layer 7(External/http/https) monitoring is the norm or not.
	- Licensing and Provisioning
		- What is provisioned and is it licensed?  AAM can be provisioned prior to v16 and could prevent upgrades if there are any AAM objects in the config.
	