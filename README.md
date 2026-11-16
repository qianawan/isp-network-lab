# IK2215 ISP Network Configuration (Kathará / FRRouting)

A cleaned portfolio snapshot of the AS104 implementation from a KTH IK2215 group project. It contains the network configuration files and startup scripts for a simulated ISP; it is not a standalone Kathará lab because the course-provided base topology and other AS configurations are intentionally not included.

## Project overview

The lab configures an ISP with four routers, three servers, and two clients. The configuration combines:

- OSPF for internal routing and redundant paths
- eBGP/iBGP and route maps for upstream and neighboring-AS policy
- BIND DNS zones and resolver configuration
- ISC DHCP, a DHCP relay, and client startup scripts
- Apache-hosted service page
- Kathará device/link configuration and Linux startup commands

All addresses are course-lab values for an isolated virtual topology. Do not apply them to a live network.

## My contribution

This was a two-person course project. I implemented the router and service configurations, startup scripts, and configuration troubleshooting; I also reviewed the subnet plan and corrected an address-range issue. My teammate created the topology drawing. The topology drawing and the course's shared starter files are not included here.

## Repository layout

- `configs/` — AS104 router, server, and client configuration directories
- `scripts/` — startup scripts for AS104 devices
- `examples/lab.conf.as104` — AS104 device-to-link fragment to merge into the official course lab file

The web page uses placeholders instead of student names and email addresses. The original bundle also contained the course template for other autonomous systems; those files and course submission documents have been excluded.

## Run in the course environment

1. Obtain the current IK2215 Kathará lab template through the course's authorized channel.
2. Copy the `configs/as104*` directories and `scripts/as104*.startup` files into the template's `project/` directory.
3. Add `examples/lab.conf.as104` to the template's `lab.conf` only if AS104 is the ASN assigned to your lab; keep the rest of the official topology intact.
4. Start the lab in the course VM:

   ```sh
   kathara lstart --noterminals
   ```

5. Use the course's verification procedure to check routing, DNS, DHCP, and web reachability. This repository has not been run as a standalone lab; the original course VM/template is required for end-to-end verification.

## Resume wording (draft)

> Configured an ISP network lab with OSPF and BGP routing policies, BIND DNS, ISC DHCP/DHCP relay, and Linux service startup scripts in Kathará; reviewed and corrected subnet allocation in a two-person project.

## Language note

The supplied `project.tar.gz` contains **no Java source files**. This project supports listing networking and Linux configuration experience; it does not support claiming Java implementation. Add Java to the CV only if you can point to a separate Java codebase and describe your own work in it.

## Coursework and attribution

This repository is a personal portfolio record of my contribution to a group assignment. The official IK2215 starter template, course specification, assessment reports, teammate's topology drawing, and other students' identifiers are not redistributed here. Please follow KTH course rules and do not submit this work as your own.
