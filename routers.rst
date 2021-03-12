BGP:
	Name: rtr1.transit1
	Purpose: BGP sessions (IPv4, IPv6) for IP transit
	Usage: Provides full BGP4/BGP6 connectivity and tunnels traffic back via Wireguard

	Name: rtr2.transit1
	Purpose: Redundant clone of rtr1.transit1
	Usage: Providers redundancy for rtr1.transit1, same upstreams but different physical box

HYPERVISOR ROUTERS:

	Name: rtr.core1
	Purpose: Core router for KVM machines to flow through
	IP Prefixes (LAN): 10.100.100.0/24, 10.2.3.0/24, 10.99.0.0/24

	Name: rtr.expr1
	Purpose: Experimental router, this is the staging ground before moving to rtr.core1
	IP Prefixes (LAN): 10.200.0.0/24, 10.50.0.0/24

PEERING ROUTERS:

	Name: rtr.peer1
	Purpose: Peering with other BGP-run networks
	IP Prefixes (LAN): N/A

	Name: rtr.ny.peer1
	Purpose: Peering with other BGP-run networks in New York (better connectivity)
	IP Prefixes (LAN): N/A
