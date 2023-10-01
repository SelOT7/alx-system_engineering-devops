# Distributed Web Infrastructure
## Description
This is a a three server web infrastructure that hosts the website www.foobar.com.

## About This Infrastructure
*  Now there are two servers. Each server has it's own web server, application server, codebase, and Database. It will be helpful incase there is alot of traffic, failure in the other server.
  It also has a HA proxy loadbalancer. This will distribute traffic among the two servers.
*  It can be either, Weighted round robin, where each server is weighed and the server that weighs more gets frequent requests or Weighted least connection, where each server is weighed and request is sent to the one with least conections.
*  It uses Active-Active, if at anytime a server fails, request isn't sent to it until it passes health check, which the pther one carries on the function. It can also use Active-passive, if at anytime the active server fails, in a heart beat the passive will take over till the other one recovers.
*  Primary replica is a primary source server(node), that is allowed to host read/write availability database. Secondary replica is the server which maintains the full backup copy of primary server, it hosts read-only availability database. When they are in a synchronized or Asynchronized mode, during a failover the secondary replica assumes the primary role with or without guarantee of data protection then when the primary replica is available it then takes on the role of secondary replica.
*  
