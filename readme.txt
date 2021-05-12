FILE NAME:    iLO5_231.bin
TITLE:        iLO 5 firmware v2.31

LANGUAGE:  English

DIVISIONS:  Systems

PRODUCTS AFFECTED:
  	HPE ProLiant BL460c Gen10 Server 
	HPE ProLiant DL580 Gen10 Server 
	HPE ProLiant DL560 Gen10 Server 
	HPE ProLiant DL385 Gen10 Plus Server 
	HPE ProLiant DL385 Gen10 Server 
	HPE ProLiant DL380 Gen10 Server 
	HPE ProLiant DL360 Gen10 Server 
	HPE ProLiant DL325 Gen10 Plus Server
	HPE ProLiant DL325 Gen10 Server 
	HPE ProLiant DL180 Gen10 Server 
	HPE ProLiant DL160 Gen10 Server 
	HPE ProLiant DL120 Gen10 Server 
	HPE ProLiant DL20 Gen10 Server 
	HPE ProLiant ML350 Gen10 Server 
	HPE ProLiant ML110 Gen10 Server 
	HPE ProLiant ML30 Gen10 Server 
	HPE ProLiant XL450 Gen10 Server 
	HPE ProLiant XL420 Gen10 Server 
	HPE Proliant XL270d Gen10 Server 
	HPE ProLiant XL230k Gen10 Server 
	HPE ProLiant XL190r Gen10 Server 
	HPE ProLiant XL170r Gen10 Server 
	HPE Apollo XL225n Gen10 Plus
	HPE Apollo r2800 Gen10 24 SFF Flexible Configure-to-order Chassis 
	HPE Apollo r2600 Gen10 24 SFF Premium Configure-to-order Chassis 
	HPE Apollo r2200 Gen10 12 LFF Configure-to-order Chassis 
	HPE Apollo 4510 Gen10 System 
	HPE Apollo 4200 Gen10 Server
	HPE ProLiant m750 Server Blade
	HPE Synergy 660 Gen10 Compute Module 
	HPE Synergy SY480 Gen10 Plus 
	HPE Synergy 480 Gen10 Compute Module 
	
THIS VERSION VALIDATED WITH:
  	Microsoft Windows Server 2019 	
	Microsoft Windows Server 2016 	
	Microsoft Windows Server 2012 R2	
	Red Hat Enterprise Linux 8 Server 	
	Red Hat Enterprise Linux 7 Server 	
	SUSE Linux Enterprise Server 15 	
	SUSE Linux Enterprise Server 12 	
	VMware ESXi 7.0
	VMware ESXi 6.7
	VMware ESXi 6.5



PREREQUISITE:  N/A

BUILD DATE:  	 October 13, 2020
EFFECTIVE DATE:  October 19, 2020

DESCRIPTION:   Firmware for the Hewlett Packard Enterprise
               Integrated Lights-Out 5 Management Controller
			   
LAST RECOMMENDED OR CRITICAL VERSION: 2.30 

PREVIOUS VERSION: 2.30

UPGRADE REQUIREMENTS: RECOMMENDED 

UPGRADING FROM A PREVIOUS VERSION OF iLO
 
- Upgrading to iLO 5 version 2.31 is supported on servers with iLO 5 1.48 or later installed. 
- On servers with an earlier version of iLO 5 installed, you must first install iLO 5 1.48, 
  and then install iLO 5 2.31. For example, if a server has iLO 5 1.10 installed, install iLO 5 
  1.48, and then install iLO 5 2.31. 

FIRMWARE DEPENDENCY:

  Hewlett Packard Enterprise recommends the following or greater versions of iLO utilities
  for best performance:
  
  - RESTful Interface Tool (iLOREST) 3.0
  - HPQLOCFG v5.2
  - Lights-Out XML Scripting Sample bundle 5.20.0 or later
  - HPONCFG Windows 5.3.0
  - HPONCFG Linux 5.5.0 or later
  - LOCFG v5.20.0 or later
  - HPLOMIG 5.2.0

  NOTE: Updated utilities and system libraries are required to support the iLO 
  High Security, FIPS, and CNSA security states.

KNOWN ISSUES:

 - To connect to the iLO Service Port with a USB Ethernet adapter, you must use a USB 2.0 device that is based on the AX88772 series chipset from ASIX Electronics Corporation. Hewlett Packard Enterprise recommends the HPE USB to Ethernet Adapter (part number Q7Y55A).
 - The server must be powered off when you update the Server Platform Services (SPS) Firmware or the Innovation Engine (IE) Firmware. After powering off the server, wait 30 seconds before initiating an SPS or IE firmware update.
 - With the release of iLO 5, some features in the iLO web interface are not supported by RIBCL or the CLI. Instead, HPE recommends the use of the iLO RESTful API, particularly for setting the iLO security state and configuring extended user privileges. The iLO RESTful API is the preferred programmatic interface for Gen10 and later systems. The preferred CLI and scripting tool is the RESTful Interface Tool (iLOREST).
 - Starting with iLO 5 1.20, SNMP settings are not backward compatible with older iLO firmware versions. The SNMP settings are discarded when you downgrade the firmware to an earlier version.
 - When you start the iLO web interface, and then you launch the HTML5 IRC, these interfaces are counted as a single iLO session. This behavior is different from the .NET IRC and the Java IRC, which are separate sessions from the iLO web interface. The Idle Connection Timeout specifies how long a session can be inactive before it ends automatically. If you start a virtual media operation (such as an OS installation), and the Idle Connection Timeout is reached, the HTML5 IRC and the iLO web interface close automatically, and the virtual media operation is interrupted. To avoid this issue, you can set the Idle Connection Timeout to a longer value, use a different remote console, or make sure that the session is not idle during the virtual media operation.
 - To support power usage reporting and optimum server thermal fan control on Linux servers with NVIDIA GPU option cards: Blacklist the nouveau video driver, and then load the NVIDIA GPU driver in persistent mode by entering the following command: nvidia-smi -pm 1
-  On certain HPE Mellanox adapters that support dual port personality (InfiniBand/Ethernet), the port personality gets reset to the default value during an adapter firmware update.

       o        For more information, see the document a00068199en_us on the Hewlett Packard Enterprise Support Center webpage: 
                https://support.hpe.com/hpsc/doc/public/display?docId=emr_na-a00068199en_us.

       o        The document lists iLO 5 1.48 as the minimum version to install before an adapter firmware update. However, iLO 5 1.48
                or later is required before updating to iLO 5 2.10 or later.

FIXES:
- iLO doesn't detect NVMe controllers during power cycle test
- iLO doesn't show FW version information when the server has more than 8 GPUs
- iLO resets after FWPKG/PLDM update and coldboot
- IE and SPS Firmware updates are failing
- Remote Syslog is made to adhere to RFC 5424 for Unstructured data format	
- On VSP performing ‘cat’ or ‘head’ or 'tail' command on a file that contains some embedded NULL characters hangs the VSP OR trims the file after the NULL character
- Inaccurate Memory Sensor status reported in the vSphere web client for HPE ProLiant Gen10 and Gen10 Plus servers running VMware ESXi 6.5/6.7/7.0 (Refer to Customer Advisory: https://support.hpe.com/hpesc/public/docDisplay?docId=emr_na-a00106468en_us)

SECURITY FIXES:
 
  For information about the latest security bulletins and vulnerabilities addressed in this version, 
  see the following website: https://support.hpe.com/hpesc/public/home.

Security best practices:

  For the latest information about security best practices, see the HPE Integrated Lights-Out Security 
  Technology Brief at the following website: http://www.hpe.com/support/ilo-docs.


ENHANCEMENTS:

- Ability to read DIMM serial number using REST api
- Enabled support for below GPUs: 
NVIDIA A100 HGX x4 GPU Air Cooled Baseboard  
NVIDIA A100 HGX x8 GPU Air FIO Baseboard  
AMD Instinct MI100 PCIE Accelerator


SUPPORT:

1.  iLO 5 firmware updates and utilities can be found here:

      https://www.hpe.com/support/iLO5

2. IPv6 network communications
     Supported Networking Features
		IPv6 Over Shared Network Port Connections
                IPv6 Static Address Assignment
                IPv6 SLAAC Address Assignment
                IPv6 Static Route Assignment
                IPv6 Static Default Gateway Entry
                DHCPv6 Stateful Address Assignment
                DHCPv6 Stateless DNS, Domain Name, and NTP Configuration
                Integrated Remote Console
                OA Single Sign-On
                HPE Single Sign-On
                Web Server
                SSH Server
                SNTP Client
                DDNS Client
                RIBCL over IPv6
                SNMP
                AlertMail
                Remote Syslog
                WinDBG Support
                HPQLOCFG/HPLOMIG over an IPv6 connection
                URL-based Virtual Media
                CLI/RIBCL Key Import over IPv6
                Authentication using LDAP and Kerberos over IPv6
                iLO Federation
                IPMI
                Embedded remote support
     Networking Features not supported by IPv6 in this release 
                NETBIOS-WINS
                Key managers
                
3. You might encounter a "data inconsistency error" when you use iLO Federation
   Management. This error occurs when an iLO on your network is not 
   responding correctly. Use the data on the Multi-System map page to 
   troubleshoot data inconsistency errors.

DOCUMENTATION -

1.  iLO 5 documentation is available at https://www.hpe.com/support/ilo-docs.

2.  Check the online help for information about how to use iLO. To access the 
    online help, Click the question mark icon in the upper right corner of 
    any iLO web interface page.

HOW TO USE -

1.  Download the iLO 5 Online Firmware Update Component for your
    operating system.

2.  Install the firmware using one of these options:
i
    a) Run the component on the host to be updated.
       The component will update the iLO 5 firmware and reset the iLO processor.

    b) Extract the firmware from the component. This will place the firmware
       image file, iLO5_yyy.bin (where yyy represents the firmware version), in
       the target directory.  You can use the following methods to install firmware:

       i) Login to iLO, navigate to the Flash Firmware page, and update the
          firmware from there.

       ii) Use the iLO RESTful API or ILOREST. For more information, see the 
           following website: http://www.hpe.com/support/restfulinterface/docs.

       iii) Use the Lights-Out Configuration Utility (HPQLOCFG) and RIBCL/XML
            scripts to update iLO 5 across the network.

       iv) Use the Online Lights-Out Configuration utility (HPONCFG) and
           RIBCL/XML scripts to update iLO 5 from the supported host OS.

3.  iLO automatically resets after a successful update.
    There is no need to manually reset iLO.

Copyright 2002,2020 Hewlett Packard Enterprise Development, LP
