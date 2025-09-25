[Commands --> Standard --> Utilities](#commandsutilities)

[Commands --> Standard --> Unix --> TMOS](#commandstmos)

[Commands --> Groups](#commandsgroups)

[Graphs --> Groups](#graphgroups)

[Security Overview --> General Tab](#securitygeneral)

[Security Overview --> Performance Tab](#securityperf)


## <a name=commandsutilities></a> Commands --> Standard --> Utilities

Click the word Utilities to expand the selections.
- **Virtual Server Traffic** - This is an abbreviated list of stats that TMOS logs for the Virtual servers.  Every column header is clickable, which will sort the rows based on the values.
    - Sorting by Client Side Bits in, can show the most and least requested Virtual Servers since last boot or statistics being cleared.
    - Sorting by CPU Usage can show Virtuals that have a higher impact on the performance of the platform.
    - Clicking the Back to Qkview will use that browser window to return you to the Status overview page.  This could cause an excess of open tabs.

## <a name=commandstmos></a> Commands --> Standard --> Unix --> TMOS

Click the words, Unix and TMOS to expand the selections.
There are many sources here which have valuable data, but I mainly use these. 
- **tmctl -a (blade)** - This is a collection of various tmstats tables which contain a lot of detailed data not commonly displayed in the GUI. The modules provisioned and objects configured will determine the number of tables the device actively populates. *Devices with a larger configuration object count could have issues loading this page.*
    - **monitor_instance_stat**
    - **monitor_stat**
    - **pool_member_stat**
    - **pool_Stat**
    - **profile_clientssl_stat**
    - **profile_http_stat**
    - **rule_stat**
    - **tmm.clock_advance**
    - **virtual_server_cpu_stat**
    - **virtual_server_stat**
    - 


## <a name=commandsgroups></a> Commands --> Group

As you work to investigate issues on your devices, you can group relevant commands together and name the groups as you see like.  This gives you a shortcut to the data you seek in your qkview and can return all of the commands on a single page for your review.

## <a name=graphgroups></a> Graphs --> Groups

some content 4

## <a name=securitygeneral></a> Security Overview --> General Tab

some content 5 

## <a name=securityperf></a> Security Overview --> Performance Tab

some content 6
