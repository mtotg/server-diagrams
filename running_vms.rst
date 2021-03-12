VIRTUAL MACHINES RUNNING (PRODUCTION):

	Name: webserver01
	Software: DirectAdmin Personal License
	Purpose: website hosting (personal sites, falls over to cyllene)
	Specification: 4 GB Memory, 150 GB Storage
	Private Direct Connections (PDCs): rtr1&rtr2

	Name: friendsandfamily01
	Software: DirectAdmin Standard License
	Purpose: friends and family websites
	Specification: 8 GB Memory, 250 GB Storage
	Private Direct Connections (PDCs): rtr1&rtr2

	Name: storage01
	Software: s3fs, restic, scp
	Purpose: Backup storage server, all files here automatically encrypted and backed up to BackBlaze B2, some back up to other servers if super important & local backups too
	Specification: 8 GB Memory, 1 TB Storage
	Private Direct Connections (PDCs): None
	VPN-Only Connections: WG-Mesh Network (only authenticated users)
	LAN-Only Connections: VM->VM crosstalk enabled, limited scope

	Name: gitlab
	Software: gitlab
	Purpose: Private gitlab server, projects live here before moving to github or hosted gitlab
	Specification: 8 GB Memory, 250 GB Storage
	Private Direct Connections (PDCs): None
	VPN-Only Connections: WG-Mesh Network (only authenticated users)
	LAN-Only Connections: VM->VM crosstalk enabled, limited scope

	Name: docker1
	Software: docker, k3s
	Purpose: All things docker live here
	Specification: 2 GB Memory, 100 GB Storage
	LAN-Only Connections: HAProxy->VM only for 80/443/8080/8443 ports

VIRTUAL MACHINES RUNNING (DEV/STAGING):

	Name: vps
	Software: N/A
	Purpose: A jumphost, general VPS for myself
	Specification: 4 GB Memory, 20 GB Storage
	Private Direct Connections (PDCs): rtr1&rtr2

VIRTUAL MACHINES RUNNING (ENTERTAINMENT):

	Name: docker2
	Software: Plex, Sonarr, Radarr
	Purpose: Plex Media Server (movies, etc)
	Specification: 4 GB Memory, 1 TB Storage (4 TB mounted via NFS)
	Private Direct Connections (PDCs): rtr1&rtr2 limited scope (tunnelled IP out for Plex)

GRAVEYARD:

	Name: win10
	Software: Firefox, Chrome, Microsoft Edge
	Purpose: Whenever I need a windows VM to test things out
	Specification: 16 GB Memory, 80 GB storage
	Note: Left off 99% of the time, scaled down or up as necessary. Highest possible configuration noted in specification.
