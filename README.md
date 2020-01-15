# calm-bp-objects
Create an S3 compliant Object Store via REST calls

- Download Nutanix Calm blueprint (.json) in order to run blueprint in Nutanix Prism Central hosted Calm service.
- On upload to Calm service, note all previous blueprint credentials are invalidated.
- Populate blueprint credentials with your Prism Central user name and password.

## WIP ...DELETE /objectstores/{UUID} ...WIP
## GET /objectstore/list
Print status / list all objectstores. Returns edited response for each objectstore (see below)

## GET /objectstores/{UUID}

Print status of objectstore defined by UUID. Returns edited response :

Objectstore current status
--------------------------
name		smartstore\
UUID		ee937940-b5f6-44ef-6169-21e1986db900\
state		PENDING\
%age completed:	5

## POST /objectstores

# Required input variables

- objectstore_name: smartstore

name of objectstore.

- infra_network: vlan.56

name of infrastructure network, used to obtain network UUID reference.

- client_network: vlan.64

name of client network, used to obtain network UUID reference.

- cluster_name: SAFC

underlying cluster infrastructure on which object store will be deployed, used to obtain cluster UUID reference.

- infra_network_dns: 10.68.59.251

DNS used for infrastructure network.

- infra_network_vip: 10.68.59.252

VIP used to communicate across infrastructure network.

- access_network_ip1: 10.68.64.251
- access_network_ip1: 10.68.64.252
- access_network_ip1: 10.68.64.253
- access_network_ip1: 10.68.64.254

4 IP addresses required for access network (don't have to be consecutive).

- vcpu_count: 10

Total number of vCPUs used by K8s cluster (minimum of 10 or a multiple of 10).

- total_memory_size_mib: 32768

total amount of RAM used by K8s cluster (min of 32GiB, or a multiple of 32GiB for every 10 vCPUs ie 30 vCPUs = 3 x 32 GiB RAM).

- total_capacity_gib: 5120

total capacity of objectstore in GiB.

- domain_name: objects.nutanix.com

required domain name.
