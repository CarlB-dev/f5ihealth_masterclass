As a former app admin in charge of the traffic management devices, I had three use cases, general health of my device including discovery of what was active/inactive, Why is this happening, and the SIGH they scanned my device and they think it is vulnerable to 80 CVEs that I have learn about and defend against.
As a presales resource supporting customers, the first two are still in my main use cases with some variations.

The first two use cases are related to an extent and can prove/disprove certain conditions or give information to other teams(like developer, hypervisor, networking, or security teams).

Let me remove a common misunderstanding, YOU DO NOT NEED A SUPPORT CASE TO USE iHEALTH!

Some of the steps I will cover are also things that DO NOT require iHealth, but as I do not have CLI access to a customer's devices, iHealth is a way for me to see things that may help resolve some challenges.  With that in mind as I drill into the iHealth data I am also trying to build a library of commands for BIG-IP Admins to use locally when iHealth is not an option or simply too slow.  I try to keep this updated here - https://github.com/CarlB-dev/f5_bash_tmsh_collection/tree/main/system_usage 

Before we get started, because tracking CVEs was never a huge concern in my past I always start by having a way to hide the vast majority of them from my main screens of interest.  If you feel the same way, then lets make that happen:
- Log into iHealth using your MyF5 credentials.
- In the grey bar at the top of the screen, to the right side you would find the word *Settings*, click that.
- Scroll down to the *Diagnostics Settings* and uncheck the box next to *Show CVE*.
- Scroll to the bottom and push the *Save* button.

Back to our regular programming.  From here I assume you have qkview uploaded per [https://my.f5.com/manage/s/article/K12878](https://my.f5.com/manage/s/article/K12878)

In your list of *Uploads*, you should see your current qkview, click the Hostname for the qkview you just uploaded.

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
	