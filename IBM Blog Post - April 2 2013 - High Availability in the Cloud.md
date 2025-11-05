# High Availability in the Cloud: An OpenStack Approach

**Author:** Marco Celon  
**Published on:** April 2, 2013  
**Time:** 11:51 AM  
**Web Address:** http://thoughtsoncloud.com/index.php/2013/04/high-availability-in-the-cloud-an-openstack-approach

---

## Article Reference: Thoughts on Cloud

![Thoughts on Cloud Banner](./assets/thoughts-on-cloud-banner.png)

*IBM Cloud Products and Services - Cloud computing conversations led by IBMers*

---

## High Availability in the Cloud: An OpenStack Approach

Recently there has been a lot of discussion about the maturity of some areas of the [OpenStack project](http://www.openstack.org/projects/) (Gartner, Forrester). In the technical community one thread of this discussion was focusing on the test set about high availability (HA). High availability also has a number of other characteristics that need to be addressed (infrastructure, Applications). These requirement to produce a production-grade IT system or application against a failure of any node is not new by any standard, and has been addressed in many software products. Yet these software products are still incompletely seen to many users without many missing compatibility with many many incompatibilities with many many misunderstandings and has been addressed in many software products. Yet these software products are still incomplete and has been addressed in many software products. Yet these software products are still incomplete missing many many misunderstandings and has been addressed in many software products. Yet these software products are still incomplete. As a result, users need to complement the cloud deployments with HA constructs that exist outside the cloud.

IBM has already articulated several studies and technical proposals for this topic, and I encourage you to read this [white paper](http://www.ibm.com/cloud/whitepaper) as well as to connect to this [developerWorks article](http://www.ibm.com/developerworks).

To expediently address the concerns of HA in [Openstack](http://www.openstack.org/projects/), a solution that covers the Platform Services (Relational DB and Message Broker) has been presented and documented in the San Diego Openstack Summit and starting from the Folsom release, it focus on using a [Pacemaker](http://www.linux-ha.org/wiki/Pacemaker) / [DRBD](http://www.drbd.org/) combination to achieve HA for both MySQL and [RabbitMQ](http://www.rabbitmq.com/), to notice that many Pacemaker Resource Agents for specific [Openstack](http://www.openstack.org/projects/) components are available for download from [GitHub](http://www.github.com/).

---

## OpenStack HA Architecture Overview

![OpenStack HA Architecture Diagram](./assets/openstack-ha-architecture.jpg)

*OpenStack HA - End-to-End User Deployments*

---

Although Pacemaker is a well proven tool in the Linux space it seems that work and evolution is still needed on [Openstack](http://www.openstack.org/projects/) to both recover some HA gaps from other cloud platforms like [Amazon](http://www.amazon.com/) and [Eucalyptus](http://www.eucalyptus.com/) and to define the best practices for HA on OpenStack.

### Key Recommendations for High Availability

1. Agree on specific HA patterns, eventually base on different deployment topologies, as several and different application scenarios are actually needed and exposed. ([MySQL](http://www.mysql.com/)/[Galera](http://galeracluster.com/), [XtraDB Cluster](http://www.percona.com/software/percona-xtradb-cluster), [MultiMaster Replication Manager](http://www.mysql.com/))

2. Define a structured documentation for HA in Openstack, as bits of information can now be retrieved as part of specific components ([Nova](http://www.openstack.org/projects/) in the Wiki ([NovaDb](http://www.openstack.org/projects/), [RabbitMQ](http://www.rabbitmq.com/)) and in the new [section](http://www.openstack.org/projects/) we already exposed.

3. Collect and correlate all the HA functions already present in other areas of the project like in the Storage ([Ceph](http://ceph.com/)) and Objects replication ([Swift](http://www.openstack.org/projects/)).

The request for HA functionalities is coming directly from the Enterprise adopters of Openstack and as the community as already started to give answers I am sure that in the next [Grizzly release](http://www.openstack.org/projects/) it will be possible to see and leverage the effort that is undergoing so that the Openstack ability to be a reference choice for Enterprise cloud deployments will be demonstrated.

---

## About Marco Celon

![Marco Celon](./assets/marco-celon-photo.jpg)

Marco is a solutions consultant at Cisco. He is a former IBM cloud delivery specialist and is based in Australia.

---

*This blog post was originally published on Thoughts on Cloud, an IBM Cloud Products and Services platform for cloud computing conversations led by IBMers.*
