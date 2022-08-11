
*check_arubaoscx_health* is an icinga2 check which queries AurubaOS-CX based
switches for various health parameters.

Depending on the switch type and OS version different things are available
and will be reported.

Monitored Health Parameters:

  * Fan status e.g. arubaWiredFanState, arubaWiredFanName
  * VSX status e.g. arubaWiredVsxDeviceRole, arubaWiredVsxConfigSync, arubaWiredVsxIslOperState
  * PSU status e.g. arubaWiredPSUName, arubaWiredPSUState

Example output:


	AOS_CX_HEALTH OK - Aruba JL479A 8320 TL.10.09.0010 
		FAN status: 10 ok PSU status: 2 ok 
		VSX status: secondary sync enabled inSync


Usage
-----

	check_arubaoscx_health [-CHt] [long options...] <some-arg>
		-H STR --host STR       Aruba CX OS hostname
		-C STR --community STR  SNMP community
		-t INT --timeout INT    Timeout

		--help                  print usage message and exit

Installation
------------

You will need some perl modules. On Debian/Ubuntu based systems:

	apt-get install libnet-snmp-perl liblist-moreutils-perl \
		libmonitoring-plugin-perl libgetopt-long-descriptive-perl 
		
