HYPERVISORS:

	Name: triplet
	Purpose: primary hypervisor and storage, runs personal sites & backups
	Specifications: 2xE5-2650v2, 4x2TB HDD, 64GB DDR3 ECC, 10GE NIC, Debian Buster (libvirt, lxc)
	Backs up to: Encladeaus & BackBlaze B2
	IP Prefixes (WAN): [removed]
	IP Prefixes (LAN): N/A (DMZ)
	Private Direct Connections (PDCs): rtr1&rtr2

	Name: encladeaus
	Purpose: code testing ground, important file backup storage
	Specifications: 2 vCores (Intel Gold Procs), 80 GB + 160GB Storage, 4 GB DDR4, Ubuntu 20.04 (lxc, docker)
	Backs up to: local backup, triplet
	IP Prefixes (WAN): [removed]
	IP Prefixes (LAN): 172.18.34.0/24
	Primary LAN IP: 172.18.34.2
	Private Direct Connections (PDCs): N/A
	Planned PDCs: triplet
	
	Name: cyllene
	Purpose: production, hosts wife & I's personal websites (HA fallover)
	Specifications: 2 vCores (AMD EPYC), 40 GB Storage, 2 GB DDR4, Ubuntu 20.04 (lxc, docker)
	Backs up to: BackBlaze B2, triplet, encladeaus
	IP Prefixes (WAN): [removed]
	IP Prefixes (LAN): 172.18.34.0/24
	Primary LAN IP: 172.18.34.3
	Private Direct Connections (PDCs): N/A
	Planned PDCs: triplet

	Name: awful
	Purpose: long-term graveyard of projects that failed, died or never finished
	Specifications: 1 GB memory, 1 TB storage, 1 vCore (AMD Ryzen)
	Backs up to: nowhere (most projects in private git repos already)
	IP Prefixes (WAN): [removed]
	IP Prefixes (LAN): N/A
	Private Direct Connections (PDCs): N/A
	Planned PDCs: None
