* Please follow the template we introduced in NOVEMBER.md file.
* Every parser need to be added under the corresponding feature.

| Module                  | Version       |
| ------------------------|:-------------:|
| ``genie.libs.parser``   |               |

--------------------------------------------------------------------------------
                                New
--------------------------------------------------------------------------------

* JUNOS
    * Added ShowOspfNeighborDetail for:
        * show ospf neighbor {neighbor} detail
    * Added ShowInterfacesDescriptions for:
        * show interfaces descriptions
    * Added ShowPfeRouteSummary for:
        * show pfe route summary
    * Added ShowOspfDatabaseLsaidDetail for:
        * show ospf database lsa-id {ipaddress} detail
    * Added ShowOspfDatabaseNetworkLsaidDetail for:
        * show ospf database network lsa-id {ipaddress} detail
    * Added ShowOspf3DatabaseLinkAdvertisingRouter for:
        * show ospf3 database link advertising-router {ipaddress} detail
    * Added ShowOspf3DatabaseNetworkDetail for:
        * show ospf3 database network detail

* IOSXE
    * Updated ShowMacAddressTable for new commnad:
        * show mac address-table vlan {vlan}

* IOS
    * Updated ShowMacAddressTable for new commnad:
        * show mac address-table vlan {vlan}

--------------------------------------------------------------------------------
                                Fix
--------------------------------------------------------------------------------

* IOSXE
    * Fixed ShowBootvar to support more outputs
    * Removed duplicate ShowBoot parser & fixed existing ShowBoot parser
    * Fixed ShowDmvpn not executing the command properly on device
    * Update ShowIpRoute:
        * Fixed regex for VRF name, now supports the '-' character in name.
    * Updated ShowInterfacesSwitchport:
        * Fixed the order of conditional statements, now the parser can parse the device output correctly
    * Updated ShowAccessLists:
        * Fixed a typo in code.
    * Update ShowVlan:
        * Fixed regex for vlan name, now also supports multiple white spaces.
        * Added regex for toking ring table.
        * Added the following keys: 'token_ring', 'are_hops', 'ste_hops' and 'backup_crf'.

* NXOS
    * Updated ShowIpStaticRouteMulticast:
        * Change key 'address_family' into Optional
    * Updated ShowRunInterface:
        * Add regex to support various sample outputs
    * Updated ShowInterfaceStatus:
        * Fix a regex pattern to support various outputs
    * Updated ShowInterface
        * Added regex to support interfaces down for SFP Not Inserted
        * Added regex to support interfaces down for ErrDisabled
        * Added regex to support interfaces down due to being suspended (LACP)

* IOSXR
    * Updated ShowBgpSessions:
        * Added regex to support various outputs
    * Updated ShowBgpInstanceNeighborsDetail:
        * Updated regex to support various outputs
* LINUX
    * Fixed Ifconfig parser issues.

* JUNOS
    * Updated ShowRoute:
        * Update regex to support various outputs.
    * Updated ShowRouteProtocolExtensive:
        * Update key 'validation-state' as Optional


* IOS 
    * Updated ShowIpArp
        * Added argument 'output' into super().cli()
                
