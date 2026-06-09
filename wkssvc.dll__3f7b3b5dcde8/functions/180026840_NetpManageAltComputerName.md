# NetpManageAltComputerName

- ea: `0x180026840`
- end: `0x180027ac0`
- name: `NetpManageAltComputerName`
- size: `4736`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, unsigned int, __int64, const WCHAR *, unsigned int)`
- caller_count: `6`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180027c90`
- `0x180027d80`
- `0x1800288a0`
- `0x180028990`
- `0x180028ee0`
- `0x180028fd0`

## callees

- `0x180006360`
- `0x180007c80`
- `0x180008950`
- `0x1800089d0`
- `0x18001e420`
- `0x18002016c`
- `0x180026448`
- `0x180026840`
- `0x180027ac8`
- `0x1800296a0`
- `0x180033159`

## import_xrefs

- `ntdll!RtlGetNtProductType` at `0x180026a4e`
- `ntdll!RtlGetNtProductType` at `0x180026a4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c6d`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x18002739e`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x18002739e`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x180027a16`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x180027a16`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180027a06`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180027a06`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreePasswordCredentials` at `0x1800279f7`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreePasswordCredentials` at `0x1800279f7`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsMakePasswordCredentialsW` at `0x180026f06`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsMakePasswordCredentialsW` at `0x180026f06`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsBindWithSpnExW` at `0x180026f4b`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsBindWithSpnExW` at `0x180026f4b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026bd5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027315`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026bd5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027315`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002799c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800279ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800279ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002799c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800279ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800279ba`
- `api-ms-win-core-kernel32-private-l1-1-0!SetLocalPrimaryComputerNameW` at `0x180026e01`
- `api-ms-win-core-kernel32-private-l1-1-0!SetLocalPrimaryComputerNameW` at `0x180027873`
- `api-ms-win-core-kernel32-private-l1-1-0!SetLocalPrimaryComputerNameW` at `0x180026e01`
- `api-ms-win-core-kernel32-private-l1-1-0!SetLocalPrimaryComputerNameW` at `0x180027873`
- `api-ms-win-core-kernel32-private-l1-1-0!RemoveLocalAlternateComputerNameW` at `0x180026dd3`
- `api-ms-win-core-kernel32-private-l1-1-0!RemoveLocalAlternateComputerNameW` at `0x1800277f1`
- `api-ms-win-core-kernel32-private-l1-1-0!RemoveLocalAlternateComputerNameW` at `0x180026dd3`
- `api-ms-win-core-kernel32-private-l1-1-0!RemoveLocalAlternateComputerNameW` at `0x1800277f1`
- `api-ms-win-core-kernel32-private-l1-1-0!EnumerateLocalComputerNamesW` at `0x180026c0e`
- `api-ms-win-core-kernel32-private-l1-1-0!EnumerateLocalComputerNamesW` at `0x180026c0e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DnsHostnameToComputerNameW` at `0x180026c63`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DnsHostnameToComputerNameW` at `0x180026c63`
- `api-ms-win-core-kernel32-legacy-l1-1-0!AddLocalAlternateComputerNameW` at `0x180026d9a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!AddLocalAlternateComputerNameW` at `0x18002782b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!AddLocalAlternateComputerNameW` at `0x180026d9a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!AddLocalAlternateComputerNameW` at `0x18002782b`
- `dsreg!DsrDeviceHostNameUpdate` at `0x180027738`
- `dsreg!DsrDeviceHostNameUpdate` at `0x180027738`
- `dsreg!DsrIsDeviceJoinedEx` at `0x1800276d2`
- `dsreg!DsrIsDeviceJoinedEx` at `0x1800276d2`
- `logoncli!DsGetDcNameWithAccountW` at `0x180026e7c`
- `logoncli!DsGetDcNameWithAccountW` at `0x180026e7c`
- `netutils!NetApiBufferFree` at `0x180027950`
- `netutils!NetApiBufferFree` at `0x18002795f`
- `netutils!NetApiBufferFree` at `0x18002796d`
- `netutils!NetApiBufferFree` at `0x18002797f`
- `netutils!NetApiBufferFree` at `0x18002798e`
- `netutils!NetApiBufferFree` at `0x1800279e8`
- `netutils!NetApiBufferFree` at `0x180027950`
- `netutils!NetApiBufferFree` at `0x18002795f`
- `netutils!NetApiBufferFree` at `0x18002796d`
- `netutils!NetApiBufferFree` at `0x18002797f`
- `netutils!NetApiBufferFree` at `0x18002798e`
- `netutils!NetApiBufferFree` at `0x1800279e8`
- `DSROLE!DsRoleFreeMemory` at `0x180026ac1`
- `DSROLE!DsRoleFreeMemory` at `0x180026ac1`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180026aa1`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180026aa1`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x180026d03`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x180026d03`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x1800279d8`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x1800279d8`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x180026d42`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x180026d42`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1800279c9`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1800279c9`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180026ff3`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180027059`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1800271d3`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18002721d`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180026ff3`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180027059`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1800271d3`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18002721d`
- `WLDAP32!__imp_LdapGetLastError` at `0x180026fa2`
- `WLDAP32!__imp_LdapGetLastError` at `0x180027186`
- `WLDAP32!__imp_LdapGetLastError` at `0x180026fa2`
- `WLDAP32!__imp_LdapGetLastError` at `0x180027186`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180026fd1`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180027031`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180027150`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1800271ac`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180027631`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180026fd1`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180027031`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180027150`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1800271ac`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180027631`
- `WLDAP32!__imp_ldap_unbind_s` at `0x180027a24`
- `WLDAP32!__imp_ldap_unbind_s` at `0x180027a32`
- `WLDAP32!__imp_ldap_unbind_s` at `0x180027a24`
- `WLDAP32!__imp_ldap_unbind_s` at `0x180027a32`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180027110`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180027259`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180027110`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180027259`
- `WLDAP32!__imp_ldap_err2stringW` at `0x180027012`
- `WLDAP32!__imp_ldap_err2stringW` at `0x180027078`
- `WLDAP32!__imp_ldap_err2stringW` at `0x180027131`
- `WLDAP32!__imp_ldap_err2stringW` at `0x1800271ea`
- `WLDAP32!__imp_ldap_err2stringW` at `0x180027238`
- `WLDAP32!__imp_ldap_err2stringW` at `0x180027276`
- `WLDAP32!__imp_ldap_err2stringW` at `0x180027612`
- `WLDAP32!__imp_ldap_err2stringW` at `0x180027012`
- `WLDAP32!__imp_ldap_err2stringW` at `0x180027078`
- `WLDAP32!__imp_ldap_err2stringW` at `0x180027131`
- `WLDAP32!__imp_ldap_err2stringW` at `0x1800271ea`
- `WLDAP32!__imp_ldap_err2stringW` at `0x180027238`
- `WLDAP32!__imp_ldap_err2stringW` at `0x180027276`
- `WLDAP32!__imp_ldap_err2stringW` at `0x180027612`
- `WLDAP32!__imp_ldap_initW` at `0x180026f92`
- `WLDAP32!__imp_ldap_initW` at `0x180027171`
- `WLDAP32!__imp_ldap_initW` at `0x180026f92`
- `WLDAP32!__imp_ldap_initW` at `0x180027171`
- `WLDAP32!__imp_ldap_modify_ext_sW` at `0x1800275f3`
- `WLDAP32!__imp_ldap_modify_ext_sW` at `0x1800275f3`
- `DNSAPI!DnsNameCompare_W` at `0x180026ebc`
- `DNSAPI!DnsNameCompare_W` at `0x180026ebc`
- `DNSAPI!DnsValidateName_W` at `0x180026af9`
- `DNSAPI!DnsValidateName_W` at `0x180026af9`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpAvoidNetlogonSpnSet` at `0x1800274f3`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpAvoidNetlogonSpnSet` at `0x1800278fc`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpAvoidNetlogonSpnSet` at `0x1800274f3`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpAvoidNetlogonSpnSet` at `0x1800278fc`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetSetuppCloseLog` at `0x180027941`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetSetuppCloseLog` at `0x180027941`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetSetuppOpenLog` at `0x1800269c3`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetSetuppOpenLog` at `0x1800269c3`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpCrackNamesStatus2Win32Error` at `0x180027415`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpCrackNamesStatus2Win32Error` at `0x180027415`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x1800269d9`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x1800269f2`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180026a0b`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180026a23`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180026a43`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180026a83`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180026ae1`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180026bf3`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180026c36`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180026c8b`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180026d21`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180026dbc`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180026ee5`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180026f76`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180026fc9`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027029`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027148`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x1800271a4`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027200`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x1800272d5`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x1800273c9`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x1800273fc`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002757e`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027629`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027695`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027714`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027752`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002780f`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027849`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027891`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x1800278ef`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002792d`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027a93`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x1800269d9`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x1800269f2`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180026a0b`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180026a23`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180026a43`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180026a83`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180026ae1`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180026bf3`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180026c36`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180026c8b`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180026d21`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180026dbc`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180026ee5`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180026f76`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180026fc9`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027029`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027148`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x1800271a4`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027200`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x1800272d5`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x1800273c9`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x1800273fc`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002757e`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027629`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027695`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027714`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027752`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002780f`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027849`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027891`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x1800278ef`

## string_xrefs

- `0x1800269d2`: `NetpManageAltComputerName called:\n`
- `0x180026a7c`: `NetpManageAltComputerName: Not supported on wksta: %lu\n`
- `0x180026ada`: `NetpManageAltComputerName: Invalid Flags passed\n`
- `0x180026b1e`: `NetpManageAltComputerName: DnsValidateName failed: 0x%lx\n`
- `0x180027aaf`: `NetpGetComputerObjectDn: Cannot NetpSeparateUserAndDomain 0x%lx\n`
- `0x180026b9a`: `NetpManageAltComputerName: NetpGetComputerName failed: 0x%lx\n`
- `0x180027a8a`: `NetpManageAltComputerName: NetpGetMachineAccountName failed: 0x%lx\n`
- `0x180026bec`: `NetpManageAltComputerName: LocalAlloc for PrimaryName failed\n`
- `0x180026c2c`: `NetpManageAltComputerName: EnumerateLocalComputerNamesW failed with Size 0x%lx: 0x%lx\n`
- `0x180026c84`: `NetpManageAltComputerName: DnsHostnameToComputerNameW failed: 0x%lx\n`
- `0x180026cbe`: `NetpManageAltComputerName: NetpGetMachineAccountName (2) failed: 0x%lx\n`
- `0x180026d18`: `NetpManageAltComputerName: LsaOpenPolicy failed: 0x%lx\n`
- `0x180026d57`: `NetpManageAltComputerName: LsaQueryInformationPolicy failed: 0x%lx\n`
- `0x180026d7e`: `NetpManageAltComputerName: WsImpersonateClient failed: 0x%lx\n`
- `0x180026db3`: `NetpManageAltComputerName: AddLocalAlternateComputerName failed 0x%lx\n`
- `0x180026dec`: `NetpManageAltComputerName: RemoveLocalAlternateComputerName failed 0x%lx\n`
- `0x180026e1a`: `NetpManageAltComputerName: SetLocalPrimaryComputerName failed 0x%lx\n`
- `0x180026e95`: `NetpManageAltComputerName: DsGetDcNameWithAccountW failed 0x%lx\n`
- `0x180026ed4`: `NetpManageAltComputerName: Got different DC '%ws' than local DC '%ws'\n`
- `0x180026f21`: `NetpManageAltComputerName: DsMakePasswordCredentials failed 0x%lx\n`
- `0x180026f69`: `NetpManageAltComputerName: DsBindWithSpnExW failed to '%ws': 0x%lx\n`
- `0x180026fbe`: `NetpManageAltComputerName: ldap_init to %ws failed: %lu\n`
- `0x18002719a`: `NetpManageAltComputerName: ldap_init to %ws failed: %lu\n`
- `0x180027018`: `NetpManageAltComputerName: ldap_set_option LDAP_OPT_REFERRALS failed on %ws: %ld: %ws\n`
- `0x1800271f0`: `NetpManageAltComputerName: ldap_set_option LDAP_OPT_REFERRALS failed on %ws: %ld: %ws\n`
- `0x18002707e`: `NetpManageAltComputerName: ldap_set_option LDAP_OPT_AREC_EXCLUSIVE failed on %ws: %ld: %ws\n`
- `0x18002723e`: `NetpManageAltComputerName: ldap_set_option LDAP_OPT_AREC_EXCLUSIVE failed on %ws: %ld: %ws\n`
- `0x180027141`: `NetpManageAltComputerName: ldap_bind failed on %ws: %ld: %ws\n`
- `0x18002727c`: `NetpManageAltComputerName: ldap_bind failed on %ws: %ld: %ws\n`
- `0x1800272c8`: `NetpManageAltComputerName: NetpSetPrimarySamAccountName failed on %ws: 0x%lx\n`
- `0x1800273b8`: `NetpManageAltComputerName: DsCrackNames failed on '%ws' for %ws: 0x%lx\n`
- `0x1800273ea`: `NetpManageAltComputerName: CrackNames failed for %ws: substatus 0x%lx\n`
- `0x180027445`: `NetpManageAltComputerName: Cracked Name %ws is not unique on %ws: %lu\n`
- `0x180027575`: `NetpManageAltComputerName: NetpQueryService failed 0x%lx\n`
- `0x1800274d6`: `NetpManageAltComputerName: NetpControlServices failed 0x%lx\n`
- `0x180027622`: `NetpManageAltComputerName: ldap_modify_ext_s failed on %ws: %ld: %ws\n`
- `0x180027677`: `NetpManageAltComputerName: NetpForceReplicateComputerObject failed to replicate object %ws from %ws to %ws, error:%ld.  This is not a fatal error.\n`
- `0x1800276de`: `NetpManageAltComputerName: DsrIsDeviceJoinedEx failed: 0x%08x\n`
- `0x18002770d`: `NetpManageAltComputerName: DsrIsDeviceJoinedEx returned %s. DsrInstance = %d\n`
- `0x18002774b`: `NetpManageAltComputerName: DsrDeviceHostNameUpdate returned 0x%08x\n`
- `0x180027808`: `NetpManageAltComputerName: (rollback) RemoveLocalAlternateComputerName failed 0x%lx\n`
- `0x180027842`: `NetpManageAltComputerName: (rollback) AddLocalAlternateComputerName failed 0x%lx\n`
- `0x18002788a`: `NetpManageAltComputerName: (rollback) SetLocalPrimaryComputerName failed 0x%lx\n`
- `0x1800278e2`: `NetpManageAltComputerName: NetpSetPrimarySamAccountName (rollback) failed on %ws: 0x%lx\n`
- `0x180027926`: `NetpManageAltComputerName: (rollback) Failed starting netlogon: 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NetpManageAltComputerName(
        __int64 a1,
        const WCHAR *a2,
        unsigned int a3,
        __int64 a4,
        const WCHAR *a5,
        unsigned int a6)
{
  void *v9; // r12
  WCHAR *v11; // rsi
  LDAP *v12; // r13
  LDAP *v13; // r14
  enum _NT_PRODUCT_TYPE v14; // ecx
  unsigned int ComputerNameEx2; // ebx
  char v16; // di
  char v17; // r15
  WCHAR *v18; // rax
  int v19; // ebx
  LDAP *v20; // rax
  ULONG LastError; // ebx
  ULONG v22; // edi
  LPCWSTR v23; // rbx
  PWCHAR v24; // rax
  ULONG v25; // eax
  LPCWSTR v26; // rbx
  PWCHAR v27; // rax
  __int64 v28; // r14
  __int64 v29; // rax
  __int64 v30; // rax
  LPCWSTR v31; // rbx
  __int64 v32; // rax
  ULONG v33; // edi
  LPCWSTR v34; // rbx
  PWCHAR v35; // rax
  LDAP *v36; // rdi
  ULONG v37; // ebx
  PWCHAR v38; // rax
  PWCHAR v39; // rax
  PWCHAR v40; // rax
  LPCWSTR v41; // rbx
  __int64 v42; // rdi
  WCHAR *v43; // rax
  NTSTATUS v44; // eax
  unsigned int v45; // eax
  PDS_NAME_RESULTW v46; // rdx
  int v47; // r14d
  __int64 v48; // rcx
  ULONG v49; // edi
  LPCWSTR v50; // rbx
  PWCHAR v51; // rax
  int v52; // r9d
  int IsDeviceJoined; // eax
  const wchar_t *v54; // rdx
  int v55; // edi
  unsigned int v56; // edi
  char v57; // r12
  unsigned int v58; // edi
  unsigned int v59; // edi
  unsigned int v60; // edi
  unsigned int v61; // edi
  DWORD BindFlags[2]; // [rsp+20h] [rbp-E0h]
  char v63; // [rsp+40h] [rbp-C0h]
  char v64; // [rsp+42h] [rbp-BEh]
  char v65; // [rsp+43h] [rbp-BDh]
  LPVOID v66; // [rsp+48h] [rbp-B8h] BYREF
  LDAP *v67; // [rsp+50h] [rbp-B0h]
  LPVOID v68; // [rsp+58h] [rbp-A8h] BYREF
  int invalue; // [rsp+60h] [rbp-A0h] BYREF
  int v70; // [rsp+64h] [rbp-9Ch]
  LPCWSTR Password; // [rsp+68h] [rbp-98h]
  enum _NT_PRODUCT_TYPE ProductType; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR Hostname; // [rsp+78h] [rbp-88h]
  PDS_NAME_RESULTW pResult; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v75; // [rsp+88h] [rbp-78h] BYREF
  int v76; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int v77; // [rsp+90h] [rbp-70h] BYREF
  LPCWSTR rpNames; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR username; // [rsp+A0h] [rbp-60h] BYREF
  PVOID DomainInfo; // [rsp+A8h] [rbp-58h] BYREF
  LPCWSTR v81; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE hDS; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v83; // [rsp+C0h] [rbp-40h]
  LPCWSTR User; // [rsp+C8h] [rbp-38h] BYREF
  LPCWSTR Domain; // [rsp+D0h] [rbp-30h] BYREF
  DWORD nSize; // [rsp+D8h] [rbp-28h] BYREF
  PVOID PolicyHandle; // [rsp+E0h] [rbp-20h] BYREF
  RPC_AUTH_IDENTITY_HANDLE pAuthIdentity; // [rsp+E8h] [rbp-18h] BYREF
  PBYTE Buffer; // [rsp+F0h] [rbp-10h] BYREF
  HLOCAL hMem; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v91; // [rsp+100h] [rbp+0h] BYREF
  __int128 *v92; // [rsp+110h] [rbp+10h]
  __int128 v93; // [rsp+118h] [rbp+18h] BYREF
  __int128 *v94; // [rsp+128h] [rbp+28h]
  __int128 v95; // [rsp+130h] [rbp+30h] BYREF
  __int128 *v96; // [rsp+140h] [rbp+40h]
  _QWORD v97[3]; // [rsp+148h] [rbp+48h] BYREF
  char v98; // [rsp+160h] [rbp+60h]
  int v99; // [rsp+161h] [rbp+61h]
  __int16 v100; // [rsp+165h] [rbp+65h]
  char v101; // [rsp+167h] [rbp+67h]
  __int128 v102; // [rsp+168h] [rbp+68h] BYREF
  __int128 v103; // [rsp+178h] [rbp+78h] BYREF
  __int128 v104; // [rsp+188h] [rbp+88h] BYREF
  WCHAR cred[8]; // [rsp+198h] [rbp+98h] BYREF
  __int128 v106; // [rsp+1A8h] [rbp+A8h]
  __int128 v107; // [rsp+1B8h] [rbp+B8h]
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+1C8h] [rbp+C8h] BYREF
  PLDAPControlW ServerControls[2]; // [rsp+1F8h] [rbp+F8h] BYREF
  _DWORD v110[8]; // [rsp+208h] [rbp+108h] BYREF
  LDAPModW *mods; // [rsp+228h] [rbp+128h] BYREF
  __int128 v112; // [rsp+230h] [rbp+130h]
  __int64 v113; // [rsp+240h] [rbp+140h]
  WCHAR ComputerName[16]; // [rsp+248h] [rbp+148h] BYREF

  Password = a5;
  Hostname = a2;
  LODWORD(v92) = 0;
  LODWORD(v94) = 0;
  LODWORD(v96) = 0;
  v113 = 0;
  ProductType = 0;
  v97[0] = L"1.2.840.113556.1.4.1413";
  PolicyHandle = 0;
  v99 = 0;
  v9 = 0;
  v100 = 0;
  v101 = 0;
  ServerControls[0] = (PLDAPControlW)v97;
  memset(v110, 0, 28);
  DomainInfo = 0;
  v75 = 256;
  username = 0;
  v81 = 0;
  User = 0;
  Domain = 0;
  rpNames = 0;
  hMem = 0;
  pAuthIdentity = 0;
  hDS = 0;
  invalue = 0;
  memset(&ObjectAttributes, 0, 44);
  pResult = 0;
  v68 = 0;
  v104 = 0;
  mods = 0;
  v102 = 0;
  Buffer = 0;
  v103 = 0;
  v76 = 0;
  v91 = 0;
  v77 = 1;
  v93 = 0;
  v97[1] = 0;
  v95 = 0;
  v97[2] = 0;
  v112 = 0;
  v98 = 0;
  *(_OWORD *)cred = 0;
  ServerControls[1] = 0;
  v106 = 0;
  v83 = a4;
  v107 = 0;
  v70 = a3;
  v66 = 0;
  if ( _InterlockedExchange(&JoinpCallInProgress, 1) == 1 )
    return 1791;
  v11 = 0;
  v67 = 0;
  v12 = 0;
  v13 = 0;
  if ( IsNetpManageIPCConnectPresent() )
    NetSetuppOpenLog();
  if ( IsNetpManageIPCConnectPresent() )
    NetpLogPrintHelper(L"NetpManageAltComputerName called:\n");
  if ( IsNetpManageIPCConnectPresent() )
    NetpLogPrintHelper(L" AlternateName = %ws\n", a2);
  if ( IsNetpManageIPCConnectPresent() )
    NetpLogPrintHelper(L" DomainAccount = %ws\n", a4);
  if ( IsNetpManageIPCConnectPresent() )
    NetpLogPrintHelper(L" Action = 0x%lx\n", a3);
  if ( IsNetpManageIPCConnectPresent() )
    NetpLogPrintHelper(L" Flags = 0x%lx\n", a6);
  if ( RtlGetNtProductType(&ProductType) )
  {
    v14 = ProductType;
  }
  else
  {
    v14 = NtProductWinNt;
    ProductType = NtProductWinNt;
  }
  if ( (unsigned int)(v14 - 2) > 1 )
  {
    if ( IsNetpManageIPCConnectPresent() )
      NetpLogPrintHelper(L"NetpManageAltComputerName: Not supported on wksta: %lu\n", (unsigned int)ProductType);
    ComputerNameEx2 = 50;
    goto LABEL_250;
  }
  if ( v14 != NtProductLanManNt )
  {
LABEL_25:
    if ( a6 && (a6 & 1) == 0 )
    {
      if ( IsNetpManageIPCConnectPresent() )
        NetpLogPrintHelper(L"NetpManageAltComputerName: Invalid Flags passed\n");
      ComputerNameEx2 = 1004;
      goto LABEL_249;
    }
    ComputerNameEx2 = DnsValidateName_W(a2, DnsNameHostnameFull);
    if ( ComputerNameEx2 && ComputerNameEx2 != 9556 )
    {
      if ( IsNetpManageIPCConnectPresent() )
        NetpLogPrintHelper(L"NetpManageAltComputerName: DnsValidateName failed: 0x%lx\n", ComputerNameEx2);
      goto LABEL_249;
    }
    v16 = 0;
    v64 = 0;
    v17 = 0;
    v63 = 0;
    if ( v83 )
    {
      if ( !IsNetpManageIPCConnectPresent() )
      {
        ComputerNameEx2 = 50;
        goto LABEL_291;
      }
      ComputerNameEx2 = NetpSeparateUserAndDomain(v83, &User, &Domain);
    }
    else if ( Password )
    {
      Password = 0;
    }
    if ( !ComputerNameEx2 )
    {
      ComputerNameEx2 = NetpGetComputerNameEx2(&v66, ComputerNameNetBIOS);
      if ( ComputerNameEx2 )
      {
        if ( IsNetpManageIPCConnectPresent() )
          NetpLogPrintHelper(L"NetpManageAltComputerName: NetpGetComputerName failed: 0x%lx\n", ComputerNameEx2);
        goto LABEL_249;
      }
      if ( IsNetpManageIPCConnectPresent() )
      {
        ComputerNameEx2 = NetpGetMachineAccountName(v66, &username);
        if ( !ComputerNameEx2 )
        {
          v18 = (WCHAR *)LocalAlloc(0x40u, 2LL * v75);
          v11 = v18;
          if ( !v18 )
          {
            if ( IsNetpManageIPCConnectPresent() )
              NetpLogPrintHelper(L"NetpManageAltComputerName: LocalAlloc for PrimaryName failed\n");
            ComputerNameEx2 = 8;
            goto LABEL_249;
          }
          ComputerNameEx2 = EnumerateLocalComputerNamesW(0, 0, v18, &v75);
          if ( ComputerNameEx2 )
          {
            if ( IsNetpManageIPCConnectPresent() )
              NetpLogPrintHelper(
                L"NetpManageAltComputerName: EnumerateLocalComputerNamesW failed with Size 0x%lx: 0x%lx\n",
                v75,
                ComputerNameEx2);
            goto LABEL_249;
          }
          v65 = 0;
          if ( v70 == 3 )
          {
            nSize = 16;
            if ( !DnsHostnameToComputerNameW(Hostname, ComputerName, &nSize) )
            {
              ComputerNameEx2 = GetLastError();
              if ( IsNetpManageIPCConnectPresent() )
                NetpLogPrintHelper(
                  L"NetpManageAltComputerName: DnsHostnameToComputerNameW failed: 0x%lx\n",
                  ComputerNameEx2);
              goto LABEL_198;
            }
            ComputerNameEx2 = NetpGetMachineAccountName(ComputerName, &v81);
            if ( ComputerNameEx2 )
            {
              if ( IsNetpManageIPCConnectPresent() )
                NetpLogPrintHelper(
                  L"NetpManageAltComputerName: NetpGetMachineAccountName (2) failed: 0x%lx\n",
                  ComputerNameEx2);
              goto LABEL_249;
            }
          }
          ObjectAttributes.Length = 48;
          memset(&ObjectAttributes.RootDirectory, 0, 20);
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v19 = LsaLookupOpenLocalPolicy(&ObjectAttributes, 1u, &PolicyHandle);
          if ( v19 < 0 )
          {
            if ( IsNetpManageIPCConnectPresent() )
              NetpLogPrintHelper(L"NetpManageAltComputerName: LsaOpenPolicy failed: 0x%lx\n", (unsigned int)v19);
LABEL_62:
            ComputerNameEx2 = NetpNtStatusToApiStatus(v19);
LABEL_198:
            if ( !ComputerNameEx2 )
            {
              if ( !v65 || v70 != 3 )
                goto LABEL_249;
              IsDeviceJoined = DsrIsDeviceJoinedEx(&v76, 0, &v77);
              if ( IsDeviceJoined < 0 )
              {
                NetpLogPrintHelper(
                  L"NetpManageAltComputerName: DsrIsDeviceJoinedEx failed: 0x%08x\n",
                  (unsigned int)IsDeviceJoined);
                goto LABEL_249;
              }
              if ( IsNetpManageIPCConnectPresent() )
              {
                v54 = L"true";
                if ( !v76 )
                  v54 = L"false";
                NetpLogPrintHelper(
                  L"NetpManageAltComputerName: DsrIsDeviceJoinedEx returned %s. DsrInstance = %d\n",
                  v54,
                  v77);
              }
              if ( !v76 || v77 )
                goto LABEL_249;
              v55 = DsrDeviceHostNameUpdate(Hostname, 7);
              if ( IsNetpManageIPCConnectPresent() )
                NetpLogPrintHelper(
                  L"NetpManageAltComputerName: DsrDeviceHostNameUpdate returned 0x%08x\n",
                  (unsigned int)v55);
              if ( v55 >= 0 )
                goto LABEL_249;
              if ( v55 != -2147024891 && v55 != -2146893808 )
              {
                switch ( v55 )
                {
                  case -2145648510:
                    ComputerNameEx2 = 2730;
                    goto LABEL_235;
                  case -2145648509:
                    ComputerNameEx2 = 2729;
                    goto LABEL_235;
                  case -2145648508:
                    ComputerNameEx2 = 2731;
                    goto LABEL_235;
                }
                if ( v55 != -805306334 )
                {
                  ComputerNameEx2 = 2728;
LABEL_235:
                  v59 = SetLocalPrimaryComputerNameW(v11, 0);
                  if ( v59 && IsNetpManageIPCConnectPresent() )
                    NetpLogPrintHelper(
                      L"NetpManageAltComputerName: (rollback) SetLocalPrimaryComputerName failed 0x%lx\n",
                      v59);
                  goto LABEL_238;
                }
              }
              ComputerNameEx2 = 5;
              goto LABEL_235;
            }
            if ( !v65 )
            {
LABEL_238:
              v57 = v63;
              goto LABEL_239;
            }
            if ( v70 == 1 )
            {
              v56 = RemoveLocalAlternateComputerNameW(Hostname, 0);
              if ( v56 && IsNetpManageIPCConnectPresent() )
                NetpLogPrintHelper(
                  L"NetpManageAltComputerName: (rollback) RemoveLocalAlternateComputerName failed 0x%lx\n",
                  v56);
LABEL_228:
              v57 = v63;
              goto LABEL_239;
            }
            if ( v70 == 2 )
            {
              v58 = AddLocalAlternateComputerNameW(Hostname, 0);
              if ( v58 && IsNetpManageIPCConnectPresent() )
                NetpLogPrintHelper(
                  L"NetpManageAltComputerName: (rollback) AddLocalAlternateComputerName failed 0x%lx\n",
                  v58);
              goto LABEL_228;
            }
            v63 = v16;
            if ( v70 == 3 )
              goto LABEL_235;
            v57 = v16;
LABEL_239:
            if ( v64 )
            {
              v60 = NetpSetPrimarySamAccountName(*(LPCWSTR *)v68, v81, username, (__int64)Password);
              if ( v60 )
              {
                if ( IsNetpManageIPCConnectPresent() )
                  NetpLogPrintHelper(
                    L"NetpManageAltComputerName: NetpSetPrimarySamAccountName (rollback) failed on %ws: 0x%lx\n",
                    *(_QWORD *)v68,
                    v60);
              }
            }
            if ( v57 )
              NetpAvoidNetlogonSpnSet(0);
            if ( v17 )
            {
              v61 = NetpControlServices(2, 1);
              if ( v61 )
              {
                if ( IsNetpManageIPCConnectPresent() )
                  NetpLogPrintHelper(L"NetpManageAltComputerName: (rollback) Failed starting netlogon: 0x%lx\n", v61);
              }
            }
            goto LABEL_249;
          }
          v19 = LsaLookupGetDomainInfo(PolicyHandle, DnsDomainInformation, &DomainInfo);
          if ( v19 < 0 )
          {
            if ( IsNetpManageIPCConnectPresent() )
              NetpLogPrintHelper(
                L"NetpManageAltComputerName: LsaQueryInformationPolicy failed: 0x%lx\n",
                (unsigned int)v19);
            goto LABEL_62;
          }
          ComputerNameEx2 = WsImpersonateClient2(0, 0);
          if ( ComputerNameEx2 )
          {
            if ( IsNetpManageIPCConnectPresent() )
              NetpLogPrintHelper(L"NetpManageAltComputerName: WsImpersonateClient failed: 0x%lx\n", ComputerNameEx2);
            goto LABEL_249;
          }
          switch ( v70 )
          {
            case 1:
              ComputerNameEx2 = AddLocalAlternateComputerNameW(Hostname, 0);
              if ( ComputerNameEx2 )
              {
                if ( IsNetpManageIPCConnectPresent() )
                  NetpLogPrintHelper(
                    L"NetpManageAltComputerName: AddLocalAlternateComputerName failed 0x%lx\n",
                    ComputerNameEx2);
                goto LABEL_197;
              }
              break;
            case 2:
              ComputerNameEx2 = RemoveLocalAlternateComputerNameW(Hostname, 0);
              if ( ComputerNameEx2 )
              {
                if ( IsNetpManageIPCConnectPresent() )
                  NetpLogPrintHelper(
                    L"NetpManageAltComputerName: RemoveLocalAlternateComputerName failed 0x%lx\n",
                    ComputerNameEx2);
                goto LABEL_197;
              }
              break;
            case 3:
              ComputerNameEx2 = SetLocalPrimaryComputerNameW(Hostname, 0);
              if ( ComputerNameEx2 )
              {
                if ( IsNetpManageIPCConnectPresent() )
                  NetpLogPrintHelper(
                    L"NetpManageAltComputerName: SetLocalPrimaryComputerName failed 0x%lx\n",
                    ComputerNameEx2);
                goto LABEL_197;
              }
              break;
          }
          ComputerNameEx2 = 0;
          v65 = 1;
          if ( !*((_QWORD *)DomainInfo + 8) || !*((_WORD *)DomainInfo + 8) )
          {
LABEL_197:
            WsRevertToSelf2(0, 0);
            goto LABEL_198;
          }
          ComputerNameEx2 = DsGetDcNameWithAccountW(
                              0,
                              username,
                              12288,
                              0,
                              0,
                              0,
                              (_BYTE)v9 != 0 ? 1074286592 : 1073745936,
                              &v68);
          if ( ComputerNameEx2 )
          {
            if ( IsNetpManageIPCConnectPresent() )
              NetpLogPrintHelper(L"NetpManageAltComputerName: DsGetDcNameWithAccountW failed 0x%lx\n", ComputerNameEx2);
            goto LABEL_197;
          }
          if ( ProductType == NtProductLanManNt && !(_BYTE)v9 && !DnsNameCompare_W(v11, (PCWSTR)(*(_QWORD *)v68 + 4LL)) )
          {
            if ( IsNetpManageIPCConnectPresent() )
              NetpLogPrintHelper(
                L"NetpManageAltComputerName: Got different DC '%ws' than local DC '%ws'\n",
                *(_QWORD *)v68 + 4LL,
                v11);
            ComputerNameEx2 = 1355;
            goto LABEL_197;
          }
          ComputerNameEx2 = DsMakePasswordCredentialsW(User, Domain, Password, &pAuthIdentity);
          if ( ComputerNameEx2 )
          {
            if ( IsNetpManageIPCConnectPresent() )
              NetpLogPrintHelper(
                L"NetpManageAltComputerName: DsMakePasswordCredentials failed 0x%lx\n",
                ComputerNameEx2);
            goto LABEL_197;
          }
          ComputerNameEx2 = DsBindWithSpnExW(*(LPCWSTR *)v68, 0, pAuthIdentity, 0, 0, &hDS);
          if ( ComputerNameEx2 )
          {
            if ( IsNetpManageIPCConnectPresent() )
              NetpLogPrintHelper(
                L"NetpManageAltComputerName: DsBindWithSpnExW failed to '%ws': 0x%lx\n",
                *(_QWORD *)v68,
                ComputerNameEx2);
            goto LABEL_197;
          }
          v20 = ldap_initW((const PWSTR)(*(_QWORD *)v68 + 4LL), 0x185u);
          v12 = v20;
          if ( !v20 )
          {
            LastError = LdapGetLastError();
            if ( IsNetpManageIPCConnectPresent() )
              NetpLogPrintHelper(
                L"NetpManageAltComputerName: ldap_init to %ws failed: %lu\n",
                *(_QWORD *)v68 + 4LL,
                LastError);
            ComputerNameEx2 = LdapMapErrorToWin32(LastError);
            goto LABEL_197;
          }
          invalue = 0;
          v22 = ldap_set_optionW(v20, 8, &invalue);
          if ( v22 )
          {
            if ( IsNetpManageIPCConnectPresent() )
            {
              v23 = *(LPCWSTR *)v68;
              v24 = ldap_err2stringW(v22);
              NetpLogPrintHelper(
                L"NetpManageAltComputerName: ldap_set_option LDAP_OPT_REFERRALS failed on %ws: %ld: %ws\n",
                v23 + 2,
                v22,
                v24);
            }
LABEL_105:
            v25 = LdapMapErrorToWin32(v22);
LABEL_106:
            ComputerNameEx2 = v25;
            v17 = (char)v13;
            v16 = (char)v13;
            goto LABEL_197;
          }
          invalue = 1;
          v22 = ldap_set_optionW(v12, 152, &invalue);
          if ( v22 )
          {
            if ( IsNetpManageIPCConnectPresent() )
            {
              v26 = *(LPCWSTR *)v68;
              v27 = ldap_err2stringW(v22);
              NetpLogPrintHelper(
                L"NetpManageAltComputerName: ldap_set_option LDAP_OPT_AREC_EXCLUSIVE failed on %ws: %ld: %ws\n",
                v26 + 2,
                v22,
                v27);
            }
            goto LABEL_105;
          }
          v28 = -1;
          if ( User )
          {
            *(_QWORD *)cred = User;
            v29 = -1;
            do
              ++v29;
            while ( User[v29] );
            *(_DWORD *)&cred[4] = v29;
          }
          if ( Domain )
          {
            *(_QWORD *)&v106 = Domain;
            v30 = -1;
            do
              ++v30;
            while ( Domain[v30] );
            DWORD2(v106) = v30;
          }
          v31 = Password;
          if ( Password )
          {
            *(_QWORD *)&v107 = Password;
            v32 = -1;
            do
              ++v32;
            while ( Password[v32] );
            DWORD2(v107) = v32;
          }
          HIDWORD(v107) = 2;
          v33 = ldap_bind_sW(v12, 0, cred, 0x486u);
          if ( v33 )
          {
            if ( IsNetpManageIPCConnectPresent() )
            {
              v34 = *(LPCWSTR *)v68;
              v35 = ldap_err2stringW(v33);
              NetpLogPrintHelper(L"NetpManageAltComputerName: ldap_bind failed on %ws: %ld: %ws\n", v34 + 2, v33, v35);
            }
            v25 = LdapMapErrorToWin32(v33);
            v13 = v67;
            goto LABEL_106;
          }
          if ( (_BYTE)v9 )
          {
            v36 = ldap_initW(v11, 0x185u);
            v67 = v36;
            if ( !v36 )
            {
              v37 = LdapGetLastError();
              if ( IsNetpManageIPCConnectPresent() )
                NetpLogPrintHelper(L"NetpManageAltComputerName: ldap_init to %ws failed: %lu\n", v11, v37);
LABEL_130:
              ComputerNameEx2 = LdapMapErrorToWin32(v37);
              v13 = v36;
LABEL_131:
              v17 = 0;
              v16 = 0;
              goto LABEL_197;
            }
            invalue = 0;
            v37 = ldap_set_optionW(v36, 8, &invalue);
            if ( v37 )
            {
              if ( IsNetpManageIPCConnectPresent() )
              {
                v38 = ldap_err2stringW(v37);
                NetpLogPrintHelper(
                  L"NetpManageAltComputerName: ldap_set_option LDAP_OPT_REFERRALS failed on %ws: %ld: %ws\n",
                  v11,
                  v37,
                  v38);
              }
              goto LABEL_130;
            }
            invalue = 1;
            v37 = ldap_set_optionW(v36, 152, &invalue);
            if ( v37 )
            {
              if ( IsNetpManageIPCConnectPresent() )
              {
                v39 = ldap_err2stringW(v37);
                NetpLogPrintHelper(
                  L"NetpManageAltComputerName: ldap_set_option LDAP_OPT_AREC_EXCLUSIVE failed on %ws: %ld: %ws\n",
                  v11,
                  v37,
                  v39);
              }
              goto LABEL_130;
            }
            v37 = ldap_bind_sW(v36, 0, cred, 0x486u);
            if ( v37 )
            {
              if ( IsNetpManageIPCConnectPresent() )
              {
                v40 = ldap_err2stringW(v37);
                NetpLogPrintHelper(L"NetpManageAltComputerName: ldap_bind failed on %ws: %ld: %ws\n", v11, v37, v40);
              }
              goto LABEL_130;
            }
            v31 = Password;
          }
          if ( v70 == 3 )
          {
            ComputerNameEx2 = NetpSetPrimarySamAccountName(*(LPCWSTR *)v68, username, v81, (__int64)v31);
            if ( ComputerNameEx2 )
            {
              if ( IsNetpManageIPCConnectPresent() )
                NetpLogPrintHelper(
                  L"NetpManageAltComputerName: NetpSetPrimarySamAccountName failed on %ws: 0x%lx\n",
                  *(_QWORD *)v68,
                  ComputerNameEx2);
              goto LABEL_146;
            }
            v41 = v81;
            v64 = 1;
          }
          else
          {
            v41 = username;
          }
          do
            ++v28;
          while ( v41[v28] );
          v42 = v28 + *(unsigned __int16 *)DomainInfo + 2LL;
          v43 = (WCHAR *)LocalAlloc(0x40u, 2 * v42);
          rpNames = v43;
          if ( !v43 )
          {
            ComputerNameEx2 = 8;
LABEL_146:
            v13 = v67;
            goto LABEL_131;
          }
          memcpy_0(v43, *((const void **)DomainInfo + 1), *(unsigned __int16 *)DomainInfo);
          v44 = RtlStringCchPrintfW(rpNames, v42, L"%ws\\%ws", rpNames, v41);
          v16 = 0;
          if ( v44 < 0 )
          {
            v45 = NetpNtStatusToApiStatus(v44);
            goto LABEL_154;
          }
          v17 = 1;
          ComputerNameEx2 = DsCrackNamesW(
                              hDS,
                              DS_NAME_NO_FLAGS,
                              DS_NT4_ACCOUNT_NAME,
                              DS_FQDN_1779_NAME,
                              1u,
                              &rpNames,
                              &pResult);
          if ( ComputerNameEx2 )
          {
            if ( IsNetpManageIPCConnectPresent() )
              NetpLogPrintHelper(
                L"NetpManageAltComputerName: DsCrackNames failed on '%ws' for %ws: 0x%lx\n",
                *(_QWORD *)v68,
                rpNames,
                ComputerNameEx2);
            goto LABEL_155;
          }
          v46 = pResult;
          if ( pResult->rItems->status )
          {
            if ( IsNetpManageIPCConnectPresent() )
              NetpLogPrintHelper(
                L"NetpManageAltComputerName: CrackNames failed for %ws: substatus 0x%lx\n",
                rpNames,
                pResult->rItems->status);
            if ( !IsNetpManageIPCConnectPresent() )
            {
              ComputerNameEx2 = 50;
              goto LABEL_155;
            }
            v45 = NetpCrackNamesStatus2Win32Error(pResult->rItems->status);
LABEL_154:
            ComputerNameEx2 = v45;
LABEL_155:
            v13 = v67;
            v17 = 0;
            goto LABEL_197;
          }
          if ( pResult->cItems > 1 )
          {
            ComputerNameEx2 = 8471;
            if ( IsNetpManageIPCConnectPresent() )
              NetpLogPrintHelper(
                L"NetpManageAltComputerName: Cracked Name %ws is not unique on %ws: %lu\n",
                rpNames,
                *(_QWORD *)v68,
                pResult->cItems);
            goto LABEL_155;
          }
          v47 = v70;
          if ( v70 != 3 )
          {
            v48 = 0;
            v63 = 0;
            v17 = 0;
            goto LABEL_186;
          }
          if ( IsNetpManageIPCConnectPresent() )
          {
            ComputerNameEx2 = NetpQueryService(L"NETLOGON", v110, &hMem);
            if ( !ComputerNameEx2 )
            {
              if ( v110[1] != 1 )
              {
                if ( IsNetpManageIPCConnectPresent() )
                {
                  ComputerNameEx2 = NetpControlServices(1, 1);
                  if ( !ComputerNameEx2 )
                    goto LABEL_179;
                }
                else
                {
                  ComputerNameEx2 = 50;
                }
                if ( IsNetpManageIPCConnectPresent() )
                  NetpLogPrintHelper(L"NetpManageAltComputerName: NetpControlServices failed 0x%lx\n", ComputerNameEx2);
                goto LABEL_155;
              }
              v17 = 0;
LABEL_179:
              if ( IsNetpManageIPCConnectPresent() )
                NetpAvoidNetlogonSpnSet(1);
              v46 = pResult;
              v48 = 2;
              v102 = (unsigned __int64)Hostname;
              *((_QWORD *)&v91 + 1) = L"DnsHostName";
              v92 = &v102;
              mods = (LDAPModW *)&v91;
              v94 = &v103;
              *(_QWORD *)&v112 = &v93;
              LODWORD(v91) = 2;
              v103 = (unsigned __int64)v11;
              *((_QWORD *)&v93 + 1) = L"msDS-AdditionalDnsHostName";
              LODWORD(v93) = 0;
              v63 = 1;
LABEL_186:
              v104 = (unsigned __int64)Hostname;
              *((_QWORD *)&v95 + 1) = L"msDS-AdditionalDnsHostName";
              v96 = &v104;
              LODWORD(v95) = v47 != 1;
              *(&mods + v48) = (LDAPModW *)&v95;
              v49 = ldap_modify_ext_sW(v12, v46->rItems->pName, &mods, ServerControls, 0);
              if ( v49 )
              {
                if ( IsNetpManageIPCConnectPresent() )
                {
                  v50 = *(LPCWSTR *)v68;
                  v51 = ldap_err2stringW(v49);
                  NetpLogPrintHelper(
                    L"NetpManageAltComputerName: ldap_modify_ext_s failed on %ws: %ld: %ws\n",
                    v50 + 2,
                    v49,
                    v51);
                }
                ComputerNameEx2 = LdapMapErrorToWin32(v49);
              }
              else if ( (_BYTE)v9 )
              {
                v52 = v47;
                v13 = v67;
                ComputerNameEx2 = NetpForceReplicateComputerObject(v12, v67, pResult->rItems->pName, v52);
                if ( ComputerNameEx2 )
                {
                  if ( IsNetpManageIPCConnectPresent() )
                  {
                    BindFlags[0] = ComputerNameEx2;
                    NetpLogPrintHelper(
                      L"NetpManageAltComputerName: NetpForceReplicateComputerObject failed to replicate object %ws from %w"
                       "s to %ws, error:%ld.  This is not a fatal error.\n",
                      pResult->rItems->pName,
                      *(_QWORD *)v68,
                      v11,
                      *(_QWORD *)BindFlags);
                  }
                  ComputerNameEx2 = 0;
                }
                goto LABEL_196;
              }
              v13 = v67;
LABEL_196:
              v16 = v63;
              goto LABEL_197;
            }
          }
          else
          {
            ComputerNameEx2 = 50;
          }
          if ( IsNetpManageIPCConnectPresent() )
            NetpLogPrintHelper(L"NetpManageAltComputerName: NetpQueryService failed 0x%lx\n", ComputerNameEx2);
          goto LABEL_155;
        }
      }
      else
      {
        ComputerNameEx2 = 50;
      }
      if ( IsNetpManageIPCConnectPresent() )
        NetpLogPrintHelper(L"NetpManageAltComputerName: NetpGetMachineAccountName failed: 0x%lx\n", ComputerNameEx2);
LABEL_289:
      v57 = 0;
      goto LABEL_239;
    }
LABEL_291:
    if ( IsNetpManageIPCConnectPresent() )
      NetpLogPrintHelper(L"NetpGetComputerObjectDn: Cannot NetpSeparateUserAndDomain 0x%lx\n", ComputerNameEx2);
    goto LABEL_289;
  }
  ComputerNameEx2 = DsRoleGetPrimaryDomainInformation(0, DsRolePrimaryDomainInfoBasic, &Buffer);
  if ( !ComputerNameEx2 )
  {
    LOBYTE(v9) = (*((_DWORD *)Buffer + 1) & 8) != 0;
    DsRoleFreeMemory(Buffer);
    goto LABEL_25;
  }
LABEL_249:
  v9 = v66;
LABEL_250:
  if ( IsNetpManageIPCConnectPresent() )
    NetSetuppCloseLog();
  if ( User )
    NetApiBufferFree((LPVOID)User);
  if ( Domain )
    NetApiBufferFree((LPVOID)Domain);
  if ( v9 )
    NetApiBufferFree(v9);
  if ( username )
    NetApiBufferFree((LPVOID)username);
  if ( v81 )
    NetApiBufferFree((LPVOID)v81);
  if ( v11 )
    LocalFree(v11);
  if ( rpNames )
    LocalFree((HLOCAL)rpNames);
  if ( hMem )
    LocalFree(hMem);
  if ( DomainInfo )
    LsaLookupFreeMemory(DomainInfo);
  if ( PolicyHandle )
    LsaLookupClose(PolicyHandle);
  if ( v68 )
    NetApiBufferFree(v68);
  if ( pAuthIdentity )
    DsFreePasswordCredentials(pAuthIdentity);
  if ( pResult )
    DsFreeNameResultW(pResult);
  if ( hDS )
    DsUnBindW(&hDS);
  if ( v12 )
    ldap_unbind_s(v12);
  if ( v13 )
    ldap_unbind_s(v13);
  _InterlockedExchange(&JoinpCallInProgress, 0);
  return ComputerNameEx2;
}

```

## disassembly

```asm
0x180026840  mov     [rsp-8+arg_0], rbx
0x180026845  push    rbp
0x180026846  push    rsi
0x180026847  push    rdi
0x180026848  push    r12
0x18002684a  push    r13
0x18002684c  push    r14
0x18002684e  push    r15
0x180026850  lea     rbp, [rsp-170h]
0x180026858  sub     rsp, 270h
0x18002685f  mov     rax, cs:__security_cookie
0x180026866  xor     rax, rsp
0x180026869  mov     [rbp+1A0h+var_38], rax
0x180026870  mov     rax, [rbp+1A0h+arg_20]
0x180026877  xor     ecx, ecx
0x180026879  xorps   xmm0, xmm0
0x18002687c  mov     [rsp+2A0h+Password], rax
0x180026881  xor     eax, eax
0x180026883  mov     [rsp+2A0h+Hostname], rdx
0x180026888  mov     dword ptr [rbp+1A0h+var_190], eax
0x18002688b  mov     r15, rdx
0x18002688e  mov     dword ptr [rbp+1A0h+var_178], eax
0x180026891  lea     edx, [rcx+1]
0x180026894  mov     dword ptr [rbp+1A0h+var_160], eax
0x180026897  xorps   xmm1, xmm1
0x18002689a  mov     [rbp+1A0h+var_60], rax
0x1800268a1  mov     ebx, r8d
0x1800268a4  lea     rax, a12840113556141; "1.2.840.113556.1.4.1413"
0x1800268ab  mov     [rsp+2A0h+ProductType], ecx
0x1800268af  mov     [rbp+1A0h+var_158], rax
0x1800268b3  mov     rdi, r9
0x1800268b6  xor     eax, eax
0x1800268b8  mov     [rbp+1A0h+PolicyHandle], rcx
0x1800268bc  mov     [rbp+1A0h+var_13F], eax
0x1800268bf  mov     r12d, ecx
0x1800268c2  mov     [rbp+1A0h+var_13B], ax
0x1800268c6  mov     [rbp+1A0h+var_139], al
0x1800268c9  lea     rax, [rbp+1A0h+var_158]
0x1800268cd  mov     [rbp+1A0h+ServerControls], rax
0x1800268d4  mov     eax, edx
0x1800268d6  movups  xmmword ptr [rbp+1A0h+var_98], xmm0
0x1800268dd  mov     [rbp+1A0h+DomainInfo], rcx
0x1800268e1  movups  xmmword ptr [rbp+1A0h+ObjectAttributes.ObjectName], xmm0
0x1800268e8  mov     [rbp+1A0h+var_218], 100h
0x1800268ef  mov     [rbp+1A0h+username], rcx
0x1800268f3  mov     [rbp+1A0h+var_1F0], rcx
0x1800268f7  mov     [rbp+1A0h+User], rcx
0x1800268fb  mov     [rbp+1A0h+Domain], rcx
0x1800268ff  mov     [rbp+1A0h+rpNames], rcx
0x180026903  movups  xmmword ptr [rbp+1A0h+var_98+0Ch], xmm0
0x18002690a  mov     [rbp+1A0h+hMem], rcx
0x18002690e  mov     [rbp+1A0h+pAuthIdentity], rcx
0x180026912  mov     [rbp+1A0h+hDS], rcx
0x180026916  mov     [rsp+2A0h+invalue], ecx
0x18002691a  movups  xmmword ptr [rbp+1A0h+ObjectAttributes.Length], xmm0
0x180026921  mov     [rbp+1A0h+pResult], rcx
0x180026925  movups  xmmword ptr [rbp+1A0h+ObjectAttributes+1Ch], xmm0
0x18002692c  mov     [rsp+2A0h+var_248], rcx
0x180026931  movups  [rbp+1A0h+var_118], xmm0
0x180026938  mov     [rbp+1A0h+mods], rcx
0x18002693f  movups  [rbp+1A0h+var_138], xmm1
0x180026943  mov     [rbp+1A0h+Buffer], rcx
0x180026947  movups  [rbp+1A0h+var_128], xmm0
0x18002694b  mov     [rbp+1A0h+var_214], ecx
0x18002694e  movups  [rbp+1A0h+var_1A0], xmm0
0x180026952  mov     [rbp+1A0h+var_210], edx
0x180026955  movups  [rbp+1A0h+var_188], xmm0
0x180026959  mov     [rbp+1A0h+var_150], rcx
0x18002695d  movups  [rbp+1A0h+var_170], xmm0
0x180026961  mov     [rbp+1A0h+var_148], rcx
0x180026965  movups  [rbp+1A0h+var_70], xmm0
0x18002696c  mov     [rbp+1A0h+var_140], cl
0x18002696f  movups  xmmword ptr [rbp+1A0h+cred], xmm0
0x180026976  mov     [rbp+1A0h+var_A0], rcx
0x18002697d  movups  [rbp+1A0h+var_F8], xmm0
0x180026984  mov     [rbp+1A0h+var_1E0], r9
0x180026988  movups  [rbp+1A0h+var_E8], xmm0
0x18002698f  xchg    eax, cs:JoinpCallInProgress
0x180026995  mov     [rsp+2A0h+var_23C], ebx
0x180026999  mov     [rsp+2A0h+var_258], rcx
0x18002699e  cmp     eax, edx
0x1800269a0  jnz     short loc_1800269AC
0x1800269a2  mov     eax, 6FFh
0x1800269a7  jmp     loc_180027A43
0x1800269ac  mov     rsi, rcx
0x1800269af  mov     [rsp+2A0h+var_250], rcx
0x1800269b4  mov     r13, rcx
0x1800269b7  mov     r14, rcx
0x1800269ba  call    IsNetpManageIPCConnectPresent
0x1800269bf  test    al, al
0x1800269c1  jz      short loc_1800269C9
0x1800269c3  call    cs:__imp_NetSetuppOpenLog
0x1800269c9  call    IsNetpManageIPCConnectPresent
0x1800269ce  test    al, al
0x1800269d0  jz      short loc_1800269DF
0x1800269d2  lea     rcx, aNetpmanagealtc_23; "NetpManageAltComputerName called:\n"
0x1800269d9  call    cs:__imp_NetpLogPrintHelper
0x1800269df  call    IsNetpManageIPCConnectPresent
0x1800269e4  test    al, al
0x1800269e6  jz      short loc_1800269F8
0x1800269e8  mov     rdx, r15
0x1800269eb  lea     rcx, aAlternatenameW; " AlternateName = %ws\n"
0x1800269f2  call    cs:__imp_NetpLogPrintHelper
0x1800269f8  call    IsNetpManageIPCConnectPresent
0x1800269fd  test    al, al
0x1800269ff  jz      short loc_180026A11
0x180026a01  mov     rdx, rdi
0x180026a04  lea     rcx, aDomainaccountW; " DomainAccount = %ws\n"
0x180026a0b  call    cs:__imp_NetpLogPrintHelper
0x180026a11  call    IsNetpManageIPCConnectPresent
0x180026a16  test    al, al
0x180026a18  jz      short loc_180026A29
0x180026a1a  mov     edx, ebx
0x180026a1c  lea     rcx, aAction0xLx; " Action = 0x%lx\n"
0x180026a23  call    cs:__imp_NetpLogPrintHelper
0x180026a29  call    IsNetpManageIPCConnectPresent
0x180026a2e  mov     edi, [rbp+1A0h+arg_28]
0x180026a34  xor     ebx, ebx
0x180026a36  test    al, al
0x180026a38  jz      short loc_180026A49
0x180026a3a  mov     edx, edi
0x180026a3c  lea     rcx, aFlags0xLx; " Flags = 0x%lx\n"
0x180026a43  call    cs:__imp_NetpLogPrintHelper
0x180026a49  lea     rcx, [rsp+2A0h+ProductType]; ProductType
0x180026a4e  call    cs:__imp_RtlGetNtProductType
0x180026a54  test    al, al
0x180026a56  jnz     short loc_180026A63
0x180026a58  mov     ecx, 1
0x180026a5d  mov     [rsp+2A0h+ProductType], ecx
0x180026a61  jmp     short loc_180026A67
0x180026a63  mov     ecx, [rsp+2A0h+ProductType]
0x180026a67  lea     eax, [rcx-2]
0x180026a6a  cmp     eax, 1
0x180026a6d  jbe     short loc_180026A93
0x180026a6f  call    IsNetpManageIPCConnectPresent
0x180026a74  test    al, al
0x180026a76  jz      short loc_180026A89
0x180026a78  mov     edx, [rsp+2A0h+ProductType]
0x180026a7c  lea     rcx, aNetpmanagealtc_5; "NetpManageAltComputerName: Not supporte"...
0x180026a83  call    cs:__imp_NetpLogPrintHelper
0x180026a89  mov     ebx, 32h ; '2'
0x180026a8e  jmp     loc_180027938
0x180026a93  cmp     ecx, 2
0x180026a96  jnz     short loc_180026AC7
0x180026a98  lea     edx, [rcx-1]; InfoLevel
0x180026a9b  xor     ecx, ecx; lpServer
0x180026a9d  lea     r8, [rbp+1A0h+Buffer]; Buffer
0x180026aa1  call    cs:__imp_DsRoleGetPrimaryDomainInformation
0x180026aa7  mov     ebx, eax
0x180026aa9  test    eax, eax
0x180026aab  jnz     loc_180027933
0x180026ab1  mov     rcx, [rbp+1A0h+Buffer]; Buffer
0x180026ab5  mov     r12d, [rcx+4]
0x180026ab9  shr     r12d, 3
0x180026abd  and     r12b, 1
0x180026ac1  call    cs:__imp_DsRoleFreeMemory
0x180026ac7  test    edi, edi
0x180026ac9  jz      short loc_180026AF1
0x180026acb  test    dil, 1
0x180026acf  jnz     short loc_180026AF1
0x180026ad1  call    IsNetpManageIPCConnectPresent
0x180026ad6  test    al, al
0x180026ad8  jz      short loc_180026AE7
0x180026ada  lea     rcx, aNetpmanagealtc_31; "NetpManageAltComputerName: Invalid Flag"...
0x180026ae1  call    cs:__imp_NetpLogPrintHelper
0x180026ae7  mov     ebx, 3ECh
0x180026aec  jmp     loc_180027933
0x180026af1  mov     edx, 2; Format
0x180026af6  mov     rcx, r15; pszName
0x180026af9  call    cs:__imp_DnsValidateName_W
0x180026aff  mov     ebx, eax
0x180026b01  xor     eax, eax
0x180026b03  test    ebx, ebx
0x180026b05  jz      short loc_180026B2A
0x180026b07  cmp     ebx, 2554h
0x180026b0d  jz      short loc_180026B2A
0x180026b0f  call    IsNetpManageIPCConnectPresent
0x180026b14  test    al, al
0x180026b16  jz      loc_180027933
0x180026b1c  mov     edx, ebx
0x180026b1e  lea     rcx, aNetpmanagealtc_0; "NetpManageAltComputerName: DnsValidateN"...
0x180026b25  jmp     loc_18002792D
0x180026b2a  mov     dil, al
0x180026b2d  mov     [rsp+2A0h+var_25E], al
0x180026b31  mov     r15b, al
0x180026b34  mov     [rsp+2A0h+var_260], al
0x180026b38  mov     [rsp+2A0h+var_25F], al
0x180026b3c  cmp     [rbp+1A0h+var_1E0], rax
0x180026b40  jnz     short loc_180026B50
0x180026b42  cmp     [rsp+2A0h+Password], rax
0x180026b47  jz      short loc_180026B71
0x180026b49  mov     [rsp+2A0h+Password], rax
0x180026b4e  jmp     short loc_180026B71
0x180026b50  call    IsNetpManageIPCConnectPresent
0x180026b55  test    al, al
0x180026b57  jz      loc_180027AA1
0x180026b5d  mov     rcx, [rbp+1A0h+var_1E0]
0x180026b61  lea     r8, [rbp+1A0h+Domain]
0x180026b65  lea     rdx, [rbp+1A0h+User]
0x180026b69  call    cs:__imp_NetpSeparateUserAndDomain
0x180026b6f  mov     ebx, eax
0x180026b71  test    ebx, ebx
0x180026b73  jnz     loc_180027AA6
0x180026b79  xor     edx, edx
0x180026b7b  lea     rcx, [rsp+2A0h+var_258]
0x180026b80  call    NetpGetComputerNameEx2
0x180026b85  mov     ebx, eax
0x180026b87  test    eax, eax
0x180026b89  jz      short loc_180026BA6
0x180026b8b  call    IsNetpManageIPCConnectPresent
0x180026b90  test    al, al
0x180026b92  jz      loc_180027933
0x180026b98  mov     edx, ebx
0x180026b9a  lea     rcx, aNetpmanagealtc_33; "NetpManageAltComputerName: NetpGetCompu"...
0x180026ba1  jmp     loc_18002792D
0x180026ba6  call    IsNetpManageIPCConnectPresent
0x180026bab  test    al, al
0x180026bad  jz      loc_180027A7C
0x180026bb3  mov     rcx, [rsp+2A0h+var_258]
0x180026bb8  lea     rdx, [rbp+1A0h+username]
0x180026bbc  call    cs:__imp_NetpGetMachineAccountName
0x180026bc2  mov     ebx, eax
0x180026bc4  test    eax, eax
0x180026bc6  jnz     loc_180027A81
0x180026bcc  mov     edx, [rbp+1A0h+var_218]
0x180026bcf  lea     ecx, [rax+40h]; uFlags
0x180026bd2  add     rdx, rdx; uBytes
0x180026bd5  call    cs:__imp_LocalAlloc
0x180026bdb  mov     rsi, rax
0x180026bde  test    rax, rax
0x180026be1  jnz     short loc_180026C03
0x180026be3  call    IsNetpManageIPCConnectPresent
0x180026be8  test    al, al
0x180026bea  jz      short loc_180026BF9
0x180026bec  lea     rcx, aNetpmanagealtc_38; "NetpManageAltComputerName: LocalAlloc f"...
0x180026bf3  call    cs:__imp_NetpLogPrintHelper
0x180026bf9  mov     ebx, 8
0x180026bfe  jmp     loc_180027933
0x180026c03  lea     r9, [rbp+1A0h+var_218]
0x180026c07  mov     r8, rsi
0x180026c0a  xor     edx, edx
0x180026c0c  xor     ecx, ecx
0x180026c0e  call    cs:__imp_EnumerateLocalComputerNamesW
0x180026c14  mov     ebx, eax
0x180026c16  xor     eax, eax
0x180026c18  test    ebx, ebx
0x180026c1a  jz      short loc_180026C41
0x180026c1c  call    IsNetpManageIPCConnectPresent
0x180026c21  test    al, al
0x180026c23  jz      loc_180027933
0x180026c29  mov     edx, [rbp+1A0h+var_218]
0x180026c2c  lea     rcx, aNetpmanagealtc_17; "NetpManageAltComputerName: EnumerateLoc"...
0x180026c33  mov     r8d, ebx
0x180026c36  call    cs:__imp_NetpLogPrintHelper
0x180026c3c  jmp     loc_180027933
0x180026c41  cmp     [rsp+2A0h+var_23C], 3
0x180026c46  mov     [rsp+2A0h+var_25D], al
0x180026c4a  jnz     short loc_180026CCA
0x180026c4c  mov     rcx, [rsp+2A0h+Hostname]; Hostname
0x180026c51  lea     r8, [rbp+1A0h+nSize]; nSize
0x180026c55  lea     rdx, [rbp+1A0h+ComputerName]; ComputerName
0x180026c5c  mov     [rbp+1A0h+nSize], 10h
0x180026c63  call    cs:__imp_DnsHostnameToComputerNameW
0x180026c69  test    eax, eax
0x180026c6b  jnz     short loc_180026C96
0x180026c6d  call    cs:__imp_GetLastError
0x180026c73  mov     ebx, eax
0x180026c75  call    IsNetpManageIPCConnectPresent
0x180026c7a  test    al, al
0x180026c7c  jz      loc_1800276AB
0x180026c82  mov     edx, ebx
0x180026c84  lea     rcx, aNetpmanagealtc_25; "NetpManageAltComputerName: DnsHostnameT"...
0x180026c8b  call    cs:__imp_NetpLogPrintHelper
0x180026c91  jmp     loc_1800276AB
0x180026c96  lea     rdx, [rbp+1A0h+var_1F0]
0x180026c9a  lea     rcx, [rbp+1A0h+ComputerName]
0x180026ca1  call    cs:__imp_NetpGetMachineAccountName
0x180026ca7  mov     ebx, eax
0x180026ca9  xor     eax, eax
0x180026cab  test    ebx, ebx
0x180026cad  jz      short loc_180026CCA
0x180026caf  call    IsNetpManageIPCConnectPresent
0x180026cb4  test    al, al
0x180026cb6  jz      loc_180027933
0x180026cbc  mov     edx, ebx
0x180026cbe  lea     rcx, aNetpmanagealtc_22; "NetpManageAltComputerName: NetpGetMachi"...
0x180026cc5  jmp     loc_18002792D
0x180026cca  xorps   xmm0, xmm0
0x180026ccd  mov     [rbp+1A0h+ObjectAttributes.Length], 30h ; '0'
0x180026cd7  lea     r8, [rbp+1A0h+PolicyHandle]; PolicyHandle
0x180026cdb  mov     [rbp+1A0h+ObjectAttributes.RootDirectory], rax
0x180026ce2  mov     edx, 1; AccessMask
0x180026ce7  mov     [rbp+1A0h+ObjectAttributes.Attributes], eax
0x180026ced  lea     rcx, [rbp+1A0h+ObjectAttributes]; ObjectAttributes
0x180026cf4  mov     [rbp+1A0h+ObjectAttributes.ObjectName], rax
0x180026cfb  movdqu  xmmword ptr [rbp+1A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180026d03  call    cs:__imp_LsaLookupOpenLocalPolicy
0x180026d09  mov     ebx, eax
0x180026d0b  test    eax, eax
0x180026d0d  jns     short loc_180026D35
  ... truncated ...
```
