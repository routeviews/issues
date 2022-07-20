

TODO: make a 'new collector' form in github and provide a link here.
TODO: We should be more standard, so that we can literally just auto-deploy new collectors given the IP Address and credentials...
TODO: consider moving all 'new collector' docs here, and pointing to a hyperlink here.

# Hosting a Route Views Collector

Thank you for your interest in setting up a new Route Views collector!
Collectors hosted by the community are one of the core assets of this project that keep it running.

There are operational overheads when we establish and begin maintaining any new collector.
So, we do weigh all the factors before accepting (or denying) a request to establish a new collector.

> At this time, we do not accept hosting multihop collectors.
> We use standard Ubuntu VMs provided by the University of Oregon for our multihop collectors.

## Request Form

> We are using GitHub to intake and triage issues.

Please fill out the ["New Collector Request" issue form](https://github.com/routeviews/issues/issues/new?assignees=&labels=collector%28s%29&template=new-collector.yml&title=New+Collector) if you wish to host a new collector for Route Views.

## Evaluating an Internet Exchange (IX)

There are several things to consider when evaluating whether or not an exchange will be a good fit for a Route Views collector today:

- [ ] Does the exchange (IX) has a peeringdb entry?
  We've built our automation scripts on top of peeringdb, so not having a peeringdb entry means that all peering requests for that exchange will have to be manually configured.
- [ ] Does the exchange have some peers we are interested in?
  * The Middle East/Northern Africa, Central Asia, and Easter Asia are all largely underrepresented regions in terms of RouteViews coverage. A collector in one of these regions even on a smaller exchange (< 12 peers), is still a good value proposition. 
  * In Contrast, A 5th Collector in Brazil, on a peering fabric that has significant overlap with peers on other exchanges we're at, does not.

## System Requirements

To set up a collector, Route Views will need a VM and some connections. 
In terms of the VM itself, we require the following minimum resources:

* 4 virtual CPUs
* 32 GB memory
* 200 GB storage 
* Two network interfaces:
  1. The interface that points to the exchange for peering, and 
  2. An interface for transit/management. 
     * Both an IPv6 and IPv4 address are required on the transit interface.

Additionally, we look to you to do the work of plumbing a VLAN from the IX to the new collector -- so that we can establish our collector at the IX.

> Route Views is attempting to standardize on the Ubuntu Operating System.
> So, if there will be an OS pre-installed, we prefer Ubuntu Server LTS.
