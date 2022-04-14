# <h1>Ansible Playbook for deploying an L3Out with Static Routing </h1>

This playbook provides an example of deploying an L3Out with static routing.
It uses the following modules: 

      cisco.aci.aci_l3out:
      cisco.aci.aci_l3out_logical_node_profile:
      cisco.aci.aci_l3out_logical_node:
      cisco.aci.aci_l3out_logical_interface_profile:
      cisco.aci.aci_l3out_interface:
      cisco.aci.aci_l3out_extepg:
      cisco.aci.aci_l3out_extepg_to_contract:
      cisco.aci.aci_l3out_extsubnet:
      cisco.aci.aci_l3out_static_routes:
      cisco.aci.aci_l3out_static_routes_nexthop:

This playbook only requires the cisco.aci collection.

It makes a few assumptions:

- This L3Out was created in the common Tenant, but this can be used anywhere.
- Some of the options should be changed to reflect the type of L3Out you want to deploy - external subnet scope, route control, etc.
- This playbook uses an SVI interface, but can be changed to use a direct interface, port channel, etc.
- The contract for the External EPG was previously created.
- That you have created the associated objects such as VRF, Application Profiles, EPGs, and Fabric access policies.
- The associated domain has already been configured under the EPG.

A lot of these assumptions could be taken care of in a playbook, but I wanted this to be specific.

This was tested with Ansible 2.12 base (Built with python 3.9.7) with ACI version 4.2(6h).
