# NetpManageAltComputerName

- ea: `0x1800288a8`
- end: `0x180029db3`
- name: `NetpManageAltComputerName`
- size: `5387`
- prototype: ``
- caller_count: `6`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180029fc0`
- `0x18002a0b0`
- `0x18002ac90`
- `0x18002ad80`
- `0x18002b330`
- `0x18002b420`

## callees

- `0x1800067e4`
- `0x1800081b0`
- `0x180009010`
- `0x180009090`
- `0x18001fbd0`
- `0x18002191c`
- `0x180028438`
- `0x1800288a8`
- `0x180029dbc`
- `0x18002bb68`
- `0x180036191`

## import_xrefs

- `ntdll!RtlGetNtProductType` at `0x180028ada`
- `ntdll!RtlGetNtProductType` at `0x180028ada`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028d4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028d4b`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x180029582`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x180029582`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x180029cf0`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x180029cf0`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180029cda`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180029cda`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreePasswordCredentials` at `0x180029cc5`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreePasswordCredentials` at `0x180029cc5`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsMakePasswordCredentialsW` at `0x180029036`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsMakePasswordCredentialsW` at `0x180029036`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsBindWithSpnExW` at `0x180029081`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsBindWithSpnExW` at `0x180029081`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028c91`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800294f3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028c91`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800294f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029c46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029c5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029c70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029c46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029c5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029c70`
- `api-ms-win-core-kernel32-private-l1-1-0!SetLocalPrimaryComputerNameW` at `0x180028f19`
- `api-ms-win-core-kernel32-private-l1-1-0!SetLocalPrimaryComputerNameW` at `0x180029ad5`
- `api-ms-win-core-kernel32-private-l1-1-0!SetLocalPrimaryComputerNameW` at `0x180028f19`
- `api-ms-win-core-kernel32-private-l1-1-0!SetLocalPrimaryComputerNameW` at `0x180029ad5`
- `api-ms-win-core-kernel32-private-l1-1-0!RemoveLocalAlternateComputerNameW` at `0x180028ee5`
- `api-ms-win-core-kernel32-private-l1-1-0!RemoveLocalAlternateComputerNameW` at `0x180029a3b`
- `api-ms-win-core-kernel32-private-l1-1-0!RemoveLocalAlternateComputerNameW` at `0x180028ee5`
- `api-ms-win-core-kernel32-private-l1-1-0!RemoveLocalAlternateComputerNameW` at `0x180029a3b`
- `api-ms-win-core-kernel32-private-l1-1-0!EnumerateLocalComputerNamesW` at `0x180028cd6`
- `api-ms-win-core-kernel32-private-l1-1-0!EnumerateLocalComputerNamesW` at `0x180028cd6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DnsHostnameToComputerNameW` at `0x180028d3b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DnsHostnameToComputerNameW` at `0x180028d3b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!AddLocalAlternateComputerNameW` at `0x180028e9c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!AddLocalAlternateComputerNameW` at `0x180029a81`
- `api-ms-win-core-kernel32-legacy-l1-1-0!AddLocalAlternateComputerNameW` at `0x180028e9c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!AddLocalAlternateComputerNameW` at `0x180029a81`
- `dsreg!DsrDeviceHostNameUpdate` at `0x180029976`
- `dsreg!DsrDeviceHostNameUpdate` at `0x180029976`
- `dsreg!DsrIsDeviceJoinedEx` at `0x180029904`
- `dsreg!DsrIsDeviceJoinedEx` at `0x180029904`
- `logoncli!DsGetDcNameWithAccountW` at `0x180028f9a`
- `logoncli!DsGetDcNameWithAccountW` at `0x180028f9a`
- `netutils!NetApiBufferFree` at `0x180029bdc`
- `netutils!NetApiBufferFree` at `0x180029bf1`
- `netutils!NetApiBufferFree` at `0x180029c05`
- `netutils!NetApiBufferFree` at `0x180029c1d`
- `netutils!NetApiBufferFree` at `0x180029c32`
- `netutils!NetApiBufferFree` at `0x180029cb0`
- `netutils!NetApiBufferFree` at `0x180029bdc`
- `netutils!NetApiBufferFree` at `0x180029bf1`
- `netutils!NetApiBufferFree` at `0x180029c05`
- `netutils!NetApiBufferFree` at `0x180029c1d`
- `netutils!NetApiBufferFree` at `0x180029c32`
- `netutils!NetApiBufferFree` at `0x180029cb0`
- `DSROLE!DsRoleFreeMemory` at `0x180028b5f`
- `DSROLE!DsRoleFreeMemory` at `0x180028b5f`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180028b39`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180028b39`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x180028df3`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x180028df3`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x180029c9a`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x180029c9a`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x180028e3e`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x180028e3e`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x180029c85`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x180029c85`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18002914d`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1800291cb`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180029381`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1800293dd`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18002914d`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1800291cb`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180029381`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1800293dd`
- `WLDAP32!__imp_LdapGetLastError` at `0x1800290ea`
- `WLDAP32!__imp_LdapGetLastError` at `0x180029322`
- `WLDAP32!__imp_LdapGetLastError` at `0x1800290ea`
- `WLDAP32!__imp_LdapGetLastError` at `0x180029322`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180029125`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18002919d`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1800292e0`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180029354`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180029857`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180029125`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18002919d`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1800292e0`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180029354`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180029857`
- `WLDAP32!__imp_ldap_unbind_s` at `0x180029d04`
- `WLDAP32!__imp_ldap_unbind_s` at `0x180029d18`
- `WLDAP32!__imp_ldap_unbind_s` at `0x180029d04`
- `WLDAP32!__imp_ldap_unbind_s` at `0x180029d18`
- `WLDAP32!__imp_ldap_bind_sW` at `0x18002928e`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180029425`
- `WLDAP32!__imp_ldap_bind_sW` at `0x18002928e`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180029425`
- `WLDAP32!__imp_ldap_err2stringW` at `0x180029172`
- `WLDAP32!__imp_ldap_err2stringW` at `0x1800291f0`
- `WLDAP32!__imp_ldap_err2stringW` at `0x1800292b5`
- `WLDAP32!__imp_ldap_err2stringW` at `0x18002939e`
- `WLDAP32!__imp_ldap_err2stringW` at `0x1800293fe`
- `WLDAP32!__imp_ldap_err2stringW` at `0x180029448`
- `WLDAP32!__imp_ldap_err2stringW` at `0x18002982c`
- `WLDAP32!__imp_ldap_err2stringW` at `0x180029172`
- `WLDAP32!__imp_ldap_err2stringW` at `0x1800291f0`
- `WLDAP32!__imp_ldap_err2stringW` at `0x1800292b5`
- `WLDAP32!__imp_ldap_err2stringW` at `0x18002939e`
- `WLDAP32!__imp_ldap_err2stringW` at `0x1800293fe`
- `WLDAP32!__imp_ldap_err2stringW` at `0x180029448`
- `WLDAP32!__imp_ldap_err2stringW` at `0x18002982c`
- `WLDAP32!__imp_ldap_initW` at `0x1800290d4`
- `WLDAP32!__imp_ldap_initW` at `0x180029307`
- `WLDAP32!__imp_ldap_initW` at `0x1800290d4`
- `WLDAP32!__imp_ldap_initW` at `0x180029307`
- `WLDAP32!__imp_ldap_modify_ext_sW` at `0x180029807`
- `WLDAP32!__imp_ldap_modify_ext_sW` at `0x180029807`
- `DNSAPI!DnsNameCompare_W` at `0x180028fe0`
- `DNSAPI!DnsNameCompare_W` at `0x180028fe0`
- `DNSAPI!DnsValidateName_W` at `0x180028ba3`
- `DNSAPI!DnsValidateName_W` at `0x180028ba3`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpAvoidNetlogonSpnSet` at `0x1800296fb`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpAvoidNetlogonSpnSet` at `0x180029b70`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpAvoidNetlogonSpnSet` at `0x1800296fb`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpAvoidNetlogonSpnSet` at `0x180029b70`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetSetuppCloseLog` at `0x180029bc7`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetSetuppCloseLog` at `0x180029bc7`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetSetuppOpenLog` at `0x180028a2b`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetSetuppOpenLog` at `0x180028a2b`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpCrackNamesStatus2Win32Error` at `0x18002960b`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpCrackNamesStatus2Win32Error` at `0x18002960b`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028a47`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028a66`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028a85`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028aa3`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028ac9`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028b15`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028b85`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028cb5`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028d04`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028d6f`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028e17`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028ec8`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002900f`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x1800290b2`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180029117`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002918f`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x1800292d2`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180029346`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x1800293ba`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x1800294ad`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x1800295b3`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x1800295ec`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002978c`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180029849`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x1800298c1`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002994c`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180029996`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180029a5f`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180029aa5`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180029af9`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180029b5d`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180029bad`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180029d80`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028a47`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028a66`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028a85`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028aa3`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028ac9`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028b15`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028b85`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028cb5`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028d04`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028d6f`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028e17`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028ec8`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002900f`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x1800290b2`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180029117`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002918f`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x1800292d2`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180029346`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x1800293ba`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x1800294ad`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x1800295b3`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x1800295ec`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002978c`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180029849`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x1800298c1`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002994c`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180029996`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180029a5f`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180029aa5`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180029af9`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180029b5d`

## string_xrefs

- `0x180028a40`: `NetpManageAltComputerName called:\n`
- `0x180028b0e`: `NetpManageAltComputerName: Not supported on wksta: %lu\n`
- `0x180028b7e`: `NetpManageAltComputerName: Invalid Flags passed\n`
- `0x180028bce`: `NetpManageAltComputerName: DnsValidateName failed: 0x%lx\n`
- `0x180029da2`: `NetpGetComputerObjectDn: Cannot NetpSeparateUserAndDomain 0x%lx\n`
- `0x180028c50`: `NetpManageAltComputerName: NetpGetComputerName failed: 0x%lx\n`
- `0x180029d77`: `NetpManageAltComputerName: NetpGetMachineAccountName failed: 0x%lx\n`
- `0x180028cae`: `NetpManageAltComputerName: LocalAlloc for PrimaryName failed\n`
- `0x180028cfa`: `NetpManageAltComputerName: EnumerateLocalComputerNamesW failed with Size 0x%lx: 0x%lx\n`
- `0x180028d68`: `NetpManageAltComputerName: DnsHostnameToComputerNameW failed: 0x%lx\n`
- `0x180028dae`: `NetpManageAltComputerName: NetpGetMachineAccountName (2) failed: 0x%lx\n`
- `0x180028e0e`: `NetpManageAltComputerName: LsaOpenPolicy failed: 0x%lx\n`
- `0x180028e59`: `NetpManageAltComputerName: LsaQueryInformationPolicy failed: 0x%lx\n`
- `0x180028e80`: `NetpManageAltComputerName: WsImpersonateClient failed: 0x%lx\n`
- `0x180028ebf`: `NetpManageAltComputerName: AddLocalAlternateComputerName failed 0x%lx\n`
- `0x180028f04`: `NetpManageAltComputerName: RemoveLocalAlternateComputerName failed 0x%lx\n`
- `0x180028f38`: `NetpManageAltComputerName: SetLocalPrimaryComputerName failed 0x%lx\n`
- `0x180028fb9`: `NetpManageAltComputerName: DsGetDcNameWithAccountW failed 0x%lx\n`
- `0x180028ffe`: `NetpManageAltComputerName: Got different DC '%ws' than local DC '%ws'\n`
- `0x180029057`: `NetpManageAltComputerName: DsMakePasswordCredentials failed 0x%lx\n`
- `0x1800290a5`: `NetpManageAltComputerName: DsBindWithSpnExW failed to '%ws': 0x%lx\n`
- `0x18002910c`: `NetpManageAltComputerName: ldap_init to %ws failed: %lu\n`
- `0x18002933c`: `NetpManageAltComputerName: ldap_init to %ws failed: %lu\n`
- `0x18002917e`: `NetpManageAltComputerName: ldap_set_option LDAP_OPT_REFERRALS failed on %ws: %ld: %ws\n`
- `0x1800293aa`: `NetpManageAltComputerName: ldap_set_option LDAP_OPT_REFERRALS failed on %ws: %ld: %ws\n`
- `0x1800291fc`: `NetpManageAltComputerName: ldap_set_option LDAP_OPT_AREC_EXCLUSIVE failed on %ws: %ld: %ws\n`
- `0x18002940a`: `NetpManageAltComputerName: ldap_set_option LDAP_OPT_AREC_EXCLUSIVE failed on %ws: %ld: %ws\n`
- `0x1800292cb`: `NetpManageAltComputerName: ldap_bind failed on %ws: %ld: %ws\n`
- `0x180029454`: `NetpManageAltComputerName: ldap_bind failed on %ws: %ld: %ws\n`
- `0x1800294a0`: `NetpManageAltComputerName: NetpSetPrimarySamAccountName failed on %ws: 0x%lx\n`
- `0x1800295a2`: `NetpManageAltComputerName: DsCrackNames failed on '%ws' for %ws: 0x%lx\n`
- `0x1800295da`: `NetpManageAltComputerName: CrackNames failed for %ws: substatus 0x%lx\n`
- `0x180029641`: `NetpManageAltComputerName: Cracked Name %ws is not unique on %ws: %lu\n`
- `0x180029783`: `NetpManageAltComputerName: NetpQueryService failed 0x%lx\n`
- `0x1800296de`: `NetpManageAltComputerName: NetpControlServices failed 0x%lx\n`
- `0x180029842`: `NetpManageAltComputerName: ldap_modify_ext_s failed on %ws: %ld: %ws\n`
- `0x1800298a3`: `NetpManageAltComputerName: NetpForceReplicateComputerObject failed to replicate object %ws from %ws to %ws, error:%ld.  This is not a fatal error.\n`
- `0x180029916`: `NetpManageAltComputerName: DsrIsDeviceJoinedEx failed: 0x%08x\n`
- `0x180029945`: `NetpManageAltComputerName: DsrIsDeviceJoinedEx returned %s. DsrInstance = %d\n`
- `0x18002998f`: `NetpManageAltComputerName: DsrDeviceHostNameUpdate returned 0x%08x\n`
- `0x180029a58`: `NetpManageAltComputerName: (rollback) RemoveLocalAlternateComputerName failed 0x%lx\n`
- `0x180029a9e`: `NetpManageAltComputerName: (rollback) AddLocalAlternateComputerName failed 0x%lx\n`
- `0x180029af2`: `NetpManageAltComputerName: (rollback) SetLocalPrimaryComputerName failed 0x%lx\n`
- `0x180029b50`: `NetpManageAltComputerName: NetpSetPrimarySamAccountName (rollback) failed on %ws: 0x%lx\n`
- `0x180029ba6`: `NetpManageAltComputerName: (rollback) Failed starting netlogon: 0x%lx\n`

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
  __int64 v14; // rcx
  LPCWSTR v15; // rcx
  DWORD ComputerNameEx2; // ebx
  __int64 v17; // rcx
  char v18; // di
  char v19; // r15
  __int64 v20; // rcx
  WCHAR *v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  int v27; // ebx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  LDAP *v34; // rax
  ULONG LastError; // ebx
  __int64 v36; // rcx
  __int64 v37; // rcx
  ULONG v38; // edi
  LPCWSTR v39; // rbx
  PWCHAR v40; // rax
  ULONG v41; // eax
  __int64 v42; // rcx
  LPCWSTR v43; // rbx
  PWCHAR v44; // rax
  __int64 v45; // r14
  __int64 v46; // rax
  __int64 v47; // rax
  LPCWSTR v48; // rbx
  __int64 v49; // rax
  ULONG v50; // edi
  LPCWSTR v51; // rbx
  PWCHAR v52; // rax
  LDAP *v53; // rdi
  ULONG v54; // ebx
  __int64 v55; // rcx
  __int64 v56; // rcx
  PWCHAR v57; // rax
  __int64 v58; // rcx
  PWCHAR v59; // rax
  PWCHAR v60; // rax
  LPCWSTR v61; // rbx
  __int64 v62; // rdi
  WCHAR *v63; // rax
  NTSTATUS v64; // eax
  DWORD v65; // eax
  PDS_NAME_RESULTW v66; // rdx
  unsigned int v67; // r14d
  __int64 v68; // rcx
  ULONG v69; // edi
  LPCWSTR v70; // rbx
  PWCHAR v71; // rax
  int IsDeviceJoined; // eax
  __int64 v73; // rcx
  const wchar_t *v74; // rdx
  int v75; // edi
  __int64 v76; // rcx
  unsigned int v77; // edi
  char v78; // r12
  unsigned int v79; // edi
  unsigned int v80; // edi
  unsigned int v81; // edi
  unsigned int v82; // edi
  DWORD BindFlags[2]; // [rsp+20h] [rbp-E0h]
  char v84; // [rsp+40h] [rbp-C0h]
  char v85; // [rsp+42h] [rbp-BEh]
  char v86; // [rsp+43h] [rbp-BDh]
  void *v87; // [rsp+48h] [rbp-B8h] BYREF
  LDAP *v88; // [rsp+50h] [rbp-B0h]
  LPVOID v89; // [rsp+58h] [rbp-A8h] BYREF
  int invalue; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v91; // [rsp+64h] [rbp-9Ch]
  LPCWSTR Password; // [rsp+68h] [rbp-98h]
  enum _NT_PRODUCT_TYPE ProductType; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR Hostname; // [rsp+78h] [rbp-88h]
  PDS_NAME_RESULTW pResult; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v96; // [rsp+88h] [rbp-78h] BYREF
  int v97; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int v98; // [rsp+90h] [rbp-70h] BYREF
  LPCWSTR rpNames; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR username; // [rsp+A0h] [rbp-60h] BYREF
  PVOID DomainInfo; // [rsp+A8h] [rbp-58h] BYREF
  LPCWSTR v102; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE hDS; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v104; // [rsp+C0h] [rbp-40h]
  LPCWSTR User; // [rsp+C8h] [rbp-38h] BYREF
  LPCWSTR Domain; // [rsp+D0h] [rbp-30h] BYREF
  DWORD nSize; // [rsp+D8h] [rbp-28h] BYREF
  PVOID PolicyHandle; // [rsp+E0h] [rbp-20h] BYREF
  RPC_AUTH_IDENTITY_HANDLE pAuthIdentity; // [rsp+E8h] [rbp-18h] BYREF
  PBYTE Buffer; // [rsp+F0h] [rbp-10h] BYREF
  HLOCAL hMem; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v112; // [rsp+100h] [rbp+0h] BYREF
  __int128 *v113; // [rsp+110h] [rbp+10h]
  __int128 v114; // [rsp+118h] [rbp+18h] BYREF
  __int128 *v115; // [rsp+128h] [rbp+28h]
  __int128 v116; // [rsp+130h] [rbp+30h] BYREF
  __int128 *v117; // [rsp+140h] [rbp+40h]
  _QWORD v118[3]; // [rsp+148h] [rbp+48h] BYREF
  char v119; // [rsp+160h] [rbp+60h]
  int v120; // [rsp+161h] [rbp+61h]
  __int16 v121; // [rsp+165h] [rbp+65h]
  char v122; // [rsp+167h] [rbp+67h]
  __int128 v123; // [rsp+168h] [rbp+68h] BYREF
  __int128 v124; // [rsp+178h] [rbp+78h] BYREF
  __int128 v125; // [rsp+188h] [rbp+88h] BYREF
  WCHAR cred[8]; // [rsp+198h] [rbp+98h] BYREF
  __int128 v127; // [rsp+1A8h] [rbp+A8h]
  __int128 v128; // [rsp+1B8h] [rbp+B8h]
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+1C8h] [rbp+C8h] BYREF
  PLDAPControlW ServerControls[2]; // [rsp+1F8h] [rbp+F8h] BYREF
  _DWORD v131[8]; // [rsp+208h] [rbp+108h] BYREF
  LDAPModW *mods; // [rsp+228h] [rbp+128h] BYREF
  __int128 v133; // [rsp+230h] [rbp+130h]
  __int64 v134; // [rsp+240h] [rbp+140h]
  WCHAR ComputerName[16]; // [rsp+248h] [rbp+148h] BYREF

  Password = a5;
  Hostname = a2;
  LODWORD(v113) = 0;
  LODWORD(v115) = 0;
  LODWORD(v117) = 0;
  v134 = 0;
  ProductType = 0;
  v118[0] = L"1.2.840.113556.1.4.1413";
  PolicyHandle = 0;
  v120 = 0;
  v9 = 0;
  v121 = 0;
  v122 = 0;
  ServerControls[0] = (PLDAPControlW)v118;
  memset(v131, 0, 28);
  DomainInfo = 0;
  v96 = 256;
  username = 0;
  v102 = 0;
  User = 0;
  Domain = 0;
  rpNames = 0;
  hMem = 0;
  pAuthIdentity = 0;
  hDS = 0;
  invalue = 0;
  memset(&ObjectAttributes, 0, 44);
  pResult = 0;
  v89 = 0;
  v125 = 0;
  mods = 0;
  v123 = 0;
  Buffer = 0;
  v124 = 0;
  v97 = 0;
  v112 = 0;
  v98 = 1;
  v114 = 0;
  v118[1] = 0;
  v116 = 0;
  v118[2] = 0;
  v133 = 0;
  v119 = 0;
  *(_OWORD *)cred = 0;
  ServerControls[1] = 0;
  v127 = 0;
  v104 = a4;
  v128 = 0;
  v91 = a3;
  v87 = 0;
  if ( _InterlockedExchange(&JoinpCallInProgress, 1) == 1 )
    return 1791;
  v11 = 0;
  v88 = 0;
  v12 = 0;
  v13 = 0;
  if ( (unsigned __int8)((__int64 (*)(void))IsNetpManageIPCConnectPresent)() )
    NetSetuppOpenLog();
  if ( (unsigned __int8)((__int64 (*)(void))IsNetpManageIPCConnectPresent)() )
    NetpLogPrintHelper(L"NetpManageAltComputerName called:\n");
  if ( (unsigned __int8)((__int64 (*)(void))IsNetpManageIPCConnectPresent)() )
    NetpLogPrintHelper(L" AlternateName = %ws\n", a2);
  if ( (unsigned __int8)((__int64 (*)(void))IsNetpManageIPCConnectPresent)() )
    NetpLogPrintHelper(L" DomainAccount = %ws\n", a4);
  if ( (unsigned __int8)((__int64 (*)(void))IsNetpManageIPCConnectPresent)() )
    NetpLogPrintHelper(L" Action = 0x%lx\n", a3);
  if ( (unsigned __int8)((__int64 (*)(void))IsNetpManageIPCConnectPresent)() )
    NetpLogPrintHelper(L" Flags = 0x%lx\n", a6);
  if ( RtlGetNtProductType(&ProductType) )
  {
    v14 = (unsigned int)ProductType;
  }
  else
  {
    v14 = 1;
    ProductType = NtProductWinNt;
  }
  if ( (unsigned int)(v14 - 2) > 1 )
  {
    if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v14) )
      NetpLogPrintHelper(L"NetpManageAltComputerName: Not supported on wksta: %lu\n", (unsigned int)ProductType);
    ComputerNameEx2 = 50;
    goto LABEL_250;
  }
  if ( (_DWORD)v14 != 2 )
  {
LABEL_25:
    if ( a6 && (a6 & 1) == 0 )
    {
      if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v14) )
        NetpLogPrintHelper(L"NetpManageAltComputerName: Invalid Flags passed\n");
      ComputerNameEx2 = 1004;
      goto LABEL_249;
    }
    ComputerNameEx2 = DnsValidateName_W(a2, DnsNameHostnameFull);
    if ( ComputerNameEx2 && ComputerNameEx2 != 9556 )
    {
      if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v17) )
        NetpLogPrintHelper(L"NetpManageAltComputerName: DnsValidateName failed: 0x%lx\n", ComputerNameEx2);
      goto LABEL_249;
    }
    v18 = 0;
    v85 = 0;
    v19 = 0;
    v84 = 0;
    if ( v104 )
    {
      if ( !(unsigned __int8)((__int64 (*)(void))IsNetpManageIPCConnectPresent)() )
      {
        ComputerNameEx2 = 50;
        goto LABEL_291;
      }
      ComputerNameEx2 = NetpSeparateUserAndDomain(v104, &User, &Domain);
    }
    else if ( Password )
    {
      Password = 0;
    }
    if ( !ComputerNameEx2 )
    {
      ComputerNameEx2 = NetpGetComputerNameEx2(&v87, 0);
      if ( ComputerNameEx2 )
      {
        if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v20) )
          NetpLogPrintHelper(L"NetpManageAltComputerName: NetpGetComputerName failed: 0x%lx\n", ComputerNameEx2);
        goto LABEL_249;
      }
      if ( (unsigned __int8)((__int64 (*)(void))IsNetpManageIPCConnectPresent)() )
      {
        ComputerNameEx2 = NetpGetMachineAccountName(v87, &username);
        if ( !ComputerNameEx2 )
        {
          v21 = (WCHAR *)LocalAlloc(0x40u, 2LL * v96);
          v11 = v21;
          if ( !v21 )
          {
            if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v22) )
              NetpLogPrintHelper(L"NetpManageAltComputerName: LocalAlloc for PrimaryName failed\n");
            ComputerNameEx2 = 8;
            goto LABEL_249;
          }
          ComputerNameEx2 = EnumerateLocalComputerNamesW(0, 0, v21, &v96);
          if ( ComputerNameEx2 )
          {
            if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v23) )
              NetpLogPrintHelper(
                L"NetpManageAltComputerName: EnumerateLocalComputerNamesW failed with Size 0x%lx: 0x%lx\n",
                v96,
                ComputerNameEx2);
            goto LABEL_249;
          }
          v86 = 0;
          if ( v91 == 3 )
          {
            nSize = 16;
            if ( !DnsHostnameToComputerNameW(Hostname, ComputerName, &nSize) )
            {
              ComputerNameEx2 = GetLastError();
              if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v24) )
                NetpLogPrintHelper(
                  L"NetpManageAltComputerName: DnsHostnameToComputerNameW failed: 0x%lx\n",
                  ComputerNameEx2);
              goto LABEL_198;
            }
            ComputerNameEx2 = NetpGetMachineAccountName(ComputerName, &v102);
            if ( ComputerNameEx2 )
            {
              if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v25) )
                NetpLogPrintHelper(
                  L"NetpManageAltComputerName: NetpGetMachineAccountName (2) failed: 0x%lx\n",
                  ComputerNameEx2);
              goto LABEL_249;
            }
          }
          ObjectAttributes.Length = 48;
          memset(&ObjectAttributes.RootDirectory, 0, 20);
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v27 = LsaLookupOpenLocalPolicy(&ObjectAttributes, 1u, &PolicyHandle);
          if ( v27 < 0 )
          {
            if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v26) )
              NetpLogPrintHelper(L"NetpManageAltComputerName: LsaOpenPolicy failed: 0x%lx\n", (unsigned int)v27);
LABEL_62:
            ComputerNameEx2 = NetpNtStatusToApiStatus(v27);
LABEL_198:
            if ( !ComputerNameEx2 )
            {
              if ( !v86 || v91 != 3 )
                goto LABEL_249;
              IsDeviceJoined = DsrIsDeviceJoinedEx(&v97, 0, &v98);
              if ( IsDeviceJoined < 0 )
              {
                NetpLogPrintHelper(
                  L"NetpManageAltComputerName: DsrIsDeviceJoinedEx failed: 0x%08x\n",
                  (unsigned int)IsDeviceJoined);
                goto LABEL_249;
              }
              if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v73) )
              {
                v74 = L"true";
                if ( !v97 )
                  v74 = L"false";
                NetpLogPrintHelper(
                  L"NetpManageAltComputerName: DsrIsDeviceJoinedEx returned %s. DsrInstance = %d\n",
                  v74,
                  v98);
              }
              if ( !v97 || v98 )
                goto LABEL_249;
              v75 = DsrDeviceHostNameUpdate(Hostname, 7);
              if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v76) )
                NetpLogPrintHelper(
                  L"NetpManageAltComputerName: DsrDeviceHostNameUpdate returned 0x%08x\n",
                  (unsigned int)v75);
              if ( v75 >= 0 )
                goto LABEL_249;
              if ( v75 != -2147024891 && v75 != -2146893808 )
              {
                switch ( v75 )
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
                if ( v75 != -805306334 )
                {
                  ComputerNameEx2 = 2728;
LABEL_235:
                  v80 = SetLocalPrimaryComputerNameW(v11, 0);
                  if ( v80 && (unsigned __int8)IsNetpManageIPCConnectPresent(v15) )
                    NetpLogPrintHelper(
                      L"NetpManageAltComputerName: (rollback) SetLocalPrimaryComputerName failed 0x%lx\n",
                      v80);
                  goto LABEL_238;
                }
              }
              ComputerNameEx2 = 5;
              goto LABEL_235;
            }
            v15 = Password;
            if ( !v86 )
            {
LABEL_238:
              v78 = v84;
              goto LABEL_239;
            }
            if ( v91 == 1 )
            {
              v77 = RemoveLocalAlternateComputerNameW(Hostname, 0);
              if ( v77 && (unsigned __int8)IsNetpManageIPCConnectPresent(v15) )
                NetpLogPrintHelper(
                  L"NetpManageAltComputerName: (rollback) RemoveLocalAlternateComputerName failed 0x%lx\n",
                  v77);
LABEL_228:
              v78 = v84;
              goto LABEL_239;
            }
            if ( v91 == 2 )
            {
              v79 = AddLocalAlternateComputerNameW(Hostname, 0);
              if ( v79 && (unsigned __int8)IsNetpManageIPCConnectPresent(v15) )
                NetpLogPrintHelper(
                  L"NetpManageAltComputerName: (rollback) AddLocalAlternateComputerName failed 0x%lx\n",
                  v79);
              goto LABEL_228;
            }
            v84 = v18;
            if ( v91 == 3 )
              goto LABEL_235;
            v78 = v18;
LABEL_239:
            if ( v85 )
            {
              v81 = NetpSetPrimarySamAccountName(*(LPCWSTR *)v89, v102, username, (__int64)Password);
              if ( v81 )
              {
                if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v15) )
                  NetpLogPrintHelper(
                    L"NetpManageAltComputerName: NetpSetPrimarySamAccountName (rollback) failed on %ws: 0x%lx\n",
                    *(_QWORD *)v89,
                    v81);
              }
            }
            if ( v78 )
              NetpAvoidNetlogonSpnSet(0);
            if ( v19 )
            {
              v82 = NetpControlServices(2, 1);
              if ( v82 )
              {
                if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v15) )
                  NetpLogPrintHelper(L"NetpManageAltComputerName: (rollback) Failed starting netlogon: 0x%lx\n", v82);
              }
            }
            goto LABEL_249;
          }
          v27 = LsaLookupGetDomainInfo(PolicyHandle, DnsDomainInformation, &DomainInfo);
          if ( v27 < 0 )
          {
            if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v28) )
              NetpLogPrintHelper(
                L"NetpManageAltComputerName: LsaQueryInformationPolicy failed: 0x%lx\n",
                (unsigned int)v27);
            goto LABEL_62;
          }
          ComputerNameEx2 = WsImpersonateClient2(0, 0);
          if ( ComputerNameEx2 )
          {
            if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v29) )
              NetpLogPrintHelper(L"NetpManageAltComputerName: WsImpersonateClient failed: 0x%lx\n", ComputerNameEx2);
            goto LABEL_249;
          }
          switch ( v91 )
          {
            case 1u:
              ComputerNameEx2 = AddLocalAlternateComputerNameW(Hostname, 0);
              if ( ComputerNameEx2 )
              {
                if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v30) )
                  NetpLogPrintHelper(
                    L"NetpManageAltComputerName: AddLocalAlternateComputerName failed 0x%lx\n",
                    ComputerNameEx2);
                goto LABEL_197;
              }
              break;
            case 2u:
              ComputerNameEx2 = RemoveLocalAlternateComputerNameW(Hostname, 0);
              if ( ComputerNameEx2 )
              {
                if ( (unsigned __int8)((__int64 (*)(void))IsNetpManageIPCConnectPresent)() )
                  NetpLogPrintHelper(
                    L"NetpManageAltComputerName: RemoveLocalAlternateComputerName failed 0x%lx\n",
                    ComputerNameEx2);
                goto LABEL_197;
              }
              break;
            case 3u:
              ComputerNameEx2 = SetLocalPrimaryComputerNameW(Hostname, 0);
              if ( ComputerNameEx2 )
              {
                if ( (unsigned __int8)((__int64 (*)(void))IsNetpManageIPCConnectPresent)() )
                  NetpLogPrintHelper(
                    L"NetpManageAltComputerName: SetLocalPrimaryComputerName failed 0x%lx\n",
                    ComputerNameEx2);
                goto LABEL_197;
              }
              break;
          }
          ComputerNameEx2 = 0;
          v86 = 1;
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
                              &v89);
          if ( ComputerNameEx2 )
          {
            if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v31) )
              NetpLogPrintHelper(L"NetpManageAltComputerName: DsGetDcNameWithAccountW failed 0x%lx\n", ComputerNameEx2);
            goto LABEL_197;
          }
          if ( ProductType == NtProductLanManNt && !(_BYTE)v9 && !DnsNameCompare_W(v11, (PCWSTR)(*(_QWORD *)v89 + 4LL)) )
          {
            if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v32) )
              NetpLogPrintHelper(
                L"NetpManageAltComputerName: Got different DC '%ws' than local DC '%ws'\n",
                *(_QWORD *)v89 + 4LL,
                v11);
            ComputerNameEx2 = 1355;
            goto LABEL_197;
          }
          ComputerNameEx2 = DsMakePasswordCredentialsW(User, Domain, Password, &pAuthIdentity);
          if ( ComputerNameEx2 )
          {
            if ( (unsigned __int8)IsNetpManageIPCConnectPresent(0) )
              NetpLogPrintHelper(
                L"NetpManageAltComputerName: DsMakePasswordCredentials failed 0x%lx\n",
                ComputerNameEx2);
            goto LABEL_197;
          }
          ComputerNameEx2 = DsBindWithSpnExW(*(LPCWSTR *)v89, 0, pAuthIdentity, 0, 0, &hDS);
          if ( ComputerNameEx2 )
          {
            if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v33) )
              NetpLogPrintHelper(
                L"NetpManageAltComputerName: DsBindWithSpnExW failed to '%ws': 0x%lx\n",
                *(_QWORD *)v89,
                ComputerNameEx2);
            goto LABEL_197;
          }
          v34 = ldap_initW((const PWSTR)(*(_QWORD *)v89 + 4LL), 0x185u);
          v12 = v34;
          if ( !v34 )
          {
            LastError = LdapGetLastError();
            if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v36) )
              NetpLogPrintHelper(
                L"NetpManageAltComputerName: ldap_init to %ws failed: %lu\n",
                *(_QWORD *)v89 + 4LL,
                LastError);
            ComputerNameEx2 = LdapMapErrorToWin32(LastError);
            goto LABEL_197;
          }
          invalue = 0;
          v38 = ldap_set_optionW(v34, 8, &invalue);
          if ( v38 )
          {
            if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v37) )
            {
              v39 = *(LPCWSTR *)v89;
              v40 = ldap_err2stringW(v38);
              NetpLogPrintHelper(
                L"NetpManageAltComputerName: ldap_set_option LDAP_OPT_REFERRALS failed on %ws: %ld: %ws\n",
                v39 + 2,
                v38,
                v40);
            }
LABEL_105:
            v41 = LdapMapErrorToWin32(v38);
LABEL_106:
            ComputerNameEx2 = v41;
            v19 = (char)v13;
            v18 = (char)v13;
            goto LABEL_197;
          }
          invalue = 1;
          v38 = ldap_set_optionW(v12, 152, &invalue);
          if ( v38 )
          {
            if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v42) )
            {
              v43 = *(LPCWSTR *)v89;
              v44 = ldap_err2stringW(v38);
              NetpLogPrintHelper(
                L"NetpManageAltComputerName: ldap_set_option LDAP_OPT_AREC_EXCLUSIVE failed on %ws: %ld: %ws\n",
                v43 + 2,
                v38,
                v44);
            }
            goto LABEL_105;
          }
          v45 = -1;
          if ( User )
          {
            *(_QWORD *)cred = User;
            v46 = -1;
            do
              ++v46;
            while ( User[v46] );
            *(_DWORD *)&cred[4] = v46;
          }
          if ( Domain )
          {
            *(_QWORD *)&v127 = Domain;
            v47 = -1;
            do
              ++v47;
            while ( Domain[v47] );
            DWORD2(v127) = v47;
          }
          v48 = Password;
          if ( Password )
          {
            *(_QWORD *)&v128 = Password;
            v49 = -1;
            do
              ++v49;
            while ( Password[v49] );
            DWORD2(v128) = v49;
          }
          HIDWORD(v128) = 2;
          v50 = ldap_bind_sW(v12, 0, cred, 0x486u);
          if ( v50 )
          {
            if ( (unsigned __int8)IsNetpManageIPCConnectPresent(0) )
            {
              v51 = *(LPCWSTR *)v89;
              v52 = ldap_err2stringW(v50);
              NetpLogPrintHelper(L"NetpManageAltComputerName: ldap_bind failed on %ws: %ld: %ws\n", v51 + 2, v50, v52);
            }
            v41 = LdapMapErrorToWin32(v50);
            v13 = v88;
            goto LABEL_106;
          }
          if ( (_BYTE)v9 )
          {
            v53 = ldap_initW(v11, 0x185u);
            v88 = v53;
            if ( !v53 )
            {
              v54 = LdapGetLastError();
              if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v55) )
                NetpLogPrintHelper(L"NetpManageAltComputerName: ldap_init to %ws failed: %lu\n", v11, v54);
LABEL_130:
              ComputerNameEx2 = LdapMapErrorToWin32(v54);
              v13 = v53;
LABEL_131:
              v19 = 0;
              v18 = 0;
              goto LABEL_197;
            }
            invalue = 0;
            v54 = ldap_set_optionW(v53, 8, &invalue);
            if ( v54 )
            {
              if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v56) )
              {
                v57 = ldap_err2stringW(v54);
                NetpLogPrintHelper(
                  L"NetpManageAltComputerName: ldap_set_option LDAP_OPT_REFERRALS failed on %ws: %ld: %ws\n",
                  v11,
                  v54,
                  v57);
              }
              goto LABEL_130;
            }
            invalue = 1;
            v54 = ldap_set_optionW(v53, 152, &invalue);
            if ( v54 )
            {
              if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v58) )
              {
                v59 = ldap_err2stringW(v54);
                NetpLogPrintHelper(
                  L"NetpManageAltComputerName: ldap_set_option LDAP_OPT_AREC_EXCLUSIVE failed on %ws: %ld: %ws\n",
                  v11,
                  v54,
                  v59);
              }
              goto LABEL_130;
            }
            v54 = ldap_bind_sW(v53, 0, cred, 0x486u);
            if ( v54 )
            {
              if ( (unsigned __int8)IsNetpManageIPCConnectPresent(0) )
              {
                v60 = ldap_err2stringW(v54);
                NetpLogPrintHelper(L"NetpManageAltComputerName: ldap_bind failed on %ws: %ld: %ws\n", v11, v54, v60);
              }
              goto LABEL_130;
            }
            v48 = Password;
          }
          if ( v91 == 3 )
          {
            ComputerNameEx2 = NetpSetPrimarySamAccountName(*(LPCWSTR *)v89, username, v102, (__int64)v48);
            if ( ComputerNameEx2 )
            {
              if ( (unsigned __int8)IsNetpManageIPCConnectPresent(0) )
                NetpLogPrintHelper(
                  L"NetpManageAltComputerName: NetpSetPrimarySamAccountName failed on %ws: 0x%lx\n",
                  *(_QWORD *)v89,
                  ComputerNameEx2);
              goto LABEL_146;
            }
            v61 = v102;
            v85 = 1;
          }
          else
          {
            v61 = username;
          }
          do
            ++v45;
          while ( v61[v45] );
          v62 = v45 + *(unsigned __int16 *)DomainInfo + 2LL;
          v63 = (WCHAR *)LocalAlloc(0x40u, 2 * v62);
          rpNames = v63;
          if ( !v63 )
          {
            ComputerNameEx2 = 8;
LABEL_146:
            v13 = v88;
            goto LABEL_131;
          }
          memcpy_0(v63, *((const void **)DomainInfo + 1), *(unsigned __int16 *)DomainInfo);
          v64 = RtlStringCchPrintfW(rpNames, v62, L"%ws\\%ws", rpNames, v61);
          v18 = 0;
          if ( v64 < 0 )
          {
            v65 = NetpNtStatusToApiStatus(v64);
            goto LABEL_154;
          }
          v19 = 1;
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
            if ( (unsigned __int8)((__int64 (*)(void))IsNetpManageIPCConnectPresent)() )
              NetpLogPrintHelper(
                L"NetpManageAltComputerName: DsCrackNames failed on '%ws' for %ws: 0x%lx\n",
                *(_QWORD *)v89,
                rpNames,
                ComputerNameEx2);
            goto LABEL_155;
          }
          v66 = pResult;
          if ( pResult->rItems->status )
          {
            if ( (unsigned __int8)((__int64 (*)(void))IsNetpManageIPCConnectPresent)() )
              NetpLogPrintHelper(
                L"NetpManageAltComputerName: CrackNames failed for %ws: substatus 0x%lx\n",
                rpNames,
                pResult->rItems->status);
            if ( !(unsigned __int8)((__int64 (*)(void))IsNetpManageIPCConnectPresent)() )
            {
              ComputerNameEx2 = 50;
              goto LABEL_155;
            }
            v65 = NetpCrackNamesStatus2Win32Error(pResult->rItems->status);
LABEL_154:
            ComputerNameEx2 = v65;
LABEL_155:
            v13 = v88;
            v19 = 0;
            goto LABEL_197;
          }
          if ( pResult->cItems > 1 )
          {
            ComputerNameEx2 = 8471;
            if ( (unsigned __int8)((__int64 (*)(void))IsNetpManageIPCConnectPresent)() )
              NetpLogPrintHelper(
                L"NetpManageAltComputerName: Cracked Name %ws is not unique on %ws: %lu\n",
                rpNames,
                *(_QWORD *)v89,
                pResult->cItems);
            goto LABEL_155;
          }
          v67 = v91;
          if ( v91 != 3 )
          {
            v68 = 0;
            v84 = 0;
            v19 = 0;
            goto LABEL_186;
          }
          if ( (unsigned __int8)((__int64 (*)(void))IsNetpManageIPCConnectPresent)() )
          {
            ComputerNameEx2 = NetpQueryService(L"NETLOGON", v131, &hMem);
            if ( !ComputerNameEx2 )
            {
              if ( v131[1] != 1 )
              {
                if ( (unsigned __int8)((__int64 (*)(void))IsNetpManageIPCConnectPresent)() )
                {
                  ComputerNameEx2 = NetpControlServices(1, 1);
                  if ( !ComputerNameEx2 )
                    goto LABEL_179;
                }
                else
                {
                  ComputerNameEx2 = 50;
                }
                if ( (unsigned __int8)((__int64 (*)(void))IsNetpManageIPCConnectPresent)() )
                  NetpLogPrintHelper(L"NetpManageAltComputerName: NetpControlServices failed 0x%lx\n", ComputerNameEx2);
                goto LABEL_155;
              }
              v19 = 0;
LABEL_179:
              if ( (unsigned __int8)((__int64 (*)(void))IsNetpManageIPCConnectPresent)() )
                NetpAvoidNetlogonSpnSet(1);
              v66 = pResult;
              v68 = 2;
              v123 = (unsigned __int64)Hostname;
              *((_QWORD *)&v112 + 1) = L"DnsHostName";
              v113 = &v123;
              mods = (LDAPModW *)&v112;
              v115 = &v124;
              *(_QWORD *)&v133 = &v114;
              LODWORD(v112) = 2;
              v124 = (unsigned __int64)v11;
              *((_QWORD *)&v114 + 1) = L"msDS-AdditionalDnsHostName";
              LODWORD(v114) = 0;
              v84 = 1;
LABEL_186:
              v125 = (unsigned __int64)Hostname;
              *((_QWORD *)&v116 + 1) = L"msDS-AdditionalDnsHostName";
              v117 = &v125;
              LODWORD(v116) = v67 != 1;
              *(&mods + v68) = (LDAPModW *)&v116;
              v69 = ldap_modify_ext_sW(v12, v66->rItems->pName, &mods, ServerControls, 0);
              if ( v69 )
              {
                if ( (unsigned __int8)((__int64 (*)(void))IsNetpManageIPCConnectPresent)() )
                {
                  v70 = *(LPCWSTR *)v89;
                  v71 = ldap_err2stringW(v69);
                  NetpLogPrintHelper(
                    L"NetpManageAltComputerName: ldap_modify_ext_s failed on %ws: %ld: %ws\n",
                    v70 + 2,
                    v69,
                    v71);
                }
                ComputerNameEx2 = LdapMapErrorToWin32(v69);
              }
              else if ( (_BYTE)v9 )
              {
                v13 = v88;
                ComputerNameEx2 = NetpForceReplicateComputerObject(v12);
                if ( ComputerNameEx2 )
                {
                  if ( (unsigned __int8)((__int64 (*)(void))IsNetpManageIPCConnectPresent)() )
                  {
                    BindFlags[0] = ComputerNameEx2;
                    NetpLogPrintHelper(
                      L"NetpManageAltComputerName: NetpForceReplicateComputerObject failed to replicate object %ws from %w"
                       "s to %ws, error:%ld.  This is not a fatal error.\n",
                      pResult->rItems->pName,
                      *(_QWORD *)v89,
                      v11,
                      *(_QWORD *)BindFlags);
                  }
                  ComputerNameEx2 = 0;
                }
                goto LABEL_196;
              }
              v13 = v88;
LABEL_196:
              v18 = v84;
              goto LABEL_197;
            }
          }
          else
          {
            ComputerNameEx2 = 50;
          }
          if ( (unsigned __int8)((__int64 (*)(void))IsNetpManageIPCConnectPresent)() )
            NetpLogPrintHelper(L"NetpManageAltComputerName: NetpQueryService failed 0x%lx\n", ComputerNameEx2);
          goto LABEL_155;
        }
      }
      else
      {
        ComputerNameEx2 = 50;
      }
      if ( (unsigned __int8)((__int64 (*)(void))IsNetpManageIPCConnectPresent)() )
        NetpLogPrintHelper(L"NetpManageAltComputerName: NetpGetMachineAccountName failed: 0x%lx\n", ComputerNameEx2);
LABEL_289:
      v78 = 0;
      goto LABEL_239;
    }
LABEL_291:
    if ( (unsigned __int8)((__int64 (*)(void))IsNetpManageIPCConnectPresent)() )
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
  v9 = v87;
LABEL_250:
  if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v15) )
    NetSetuppCloseLog();
  if ( User )
    NetApiBufferFree((LPVOID)User);
  if ( Domain )
    NetApiBufferFree((LPVOID)Domain);
  if ( v9 )
    NetApiBufferFree(v9);
  if ( username )
    NetApiBufferFree((LPVOID)username);
  if ( v102 )
    NetApiBufferFree((LPVOID)v102);
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
  if ( v89 )
    NetApiBufferFree(v89);
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
0x1800288a8  mov     [rsp-8+arg_0], rbx
0x1800288ad  push    rbp
0x1800288ae  push    rsi
0x1800288af  push    rdi
0x1800288b0  push    r12
0x1800288b2  push    r13
0x1800288b4  push    r14
0x1800288b6  push    r15
0x1800288b8  lea     rbp, [rsp-170h]
0x1800288c0  sub     rsp, 270h
0x1800288c7  mov     rax, cs:__security_cookie
0x1800288ce  xor     rax, rsp
0x1800288d1  mov     [rbp+1A0h+var_38], rax
0x1800288d8  mov     rax, [rbp+1A0h+arg_20]
0x1800288df  xor     ecx, ecx
0x1800288e1  xorps   xmm0, xmm0
0x1800288e4  mov     [rsp+2A0h+Password], rax
0x1800288e9  xor     eax, eax
0x1800288eb  mov     [rsp+2A0h+Hostname], rdx
0x1800288f0  mov     dword ptr [rbp+1A0h+var_190], eax
0x1800288f3  mov     r15, rdx
0x1800288f6  mov     dword ptr [rbp+1A0h+var_178], eax
0x1800288f9  lea     edx, [rcx+1]
0x1800288fc  mov     dword ptr [rbp+1A0h+var_160], eax
0x1800288ff  xorps   xmm1, xmm1
0x180028902  mov     [rbp+1A0h+var_60], rax
0x180028909  mov     ebx, r8d
0x18002890c  lea     rax, a12840113556141; "1.2.840.113556.1.4.1413"
0x180028913  mov     [rsp+2A0h+ProductType], ecx
0x180028917  mov     [rbp+1A0h+var_158], rax
0x18002891b  mov     rdi, r9
0x18002891e  xor     eax, eax
0x180028920  mov     [rbp+1A0h+PolicyHandle], rcx
0x180028924  mov     [rbp+1A0h+var_13F], eax
0x180028927  mov     r12d, ecx
0x18002892a  mov     [rbp+1A0h+var_13B], ax
0x18002892e  mov     [rbp+1A0h+var_139], al
0x180028931  lea     rax, [rbp+1A0h+var_158]
0x180028935  mov     [rbp+1A0h+ServerControls], rax
0x18002893c  mov     eax, edx
0x18002893e  movups  xmmword ptr [rbp+1A0h+var_98], xmm0
0x180028945  mov     [rbp+1A0h+DomainInfo], rcx
0x180028949  movups  xmmword ptr [rbp+1A0h+ObjectAttributes.ObjectName], xmm0
0x180028950  mov     [rbp+1A0h+var_218], 100h
0x180028957  mov     [rbp+1A0h+username], rcx
0x18002895b  mov     [rbp+1A0h+var_1F0], rcx
0x18002895f  mov     [rbp+1A0h+User], rcx
0x180028963  mov     [rbp+1A0h+Domain], rcx
0x180028967  mov     [rbp+1A0h+rpNames], rcx
0x18002896b  movups  xmmword ptr [rbp+1A0h+var_98+0Ch], xmm0
0x180028972  mov     [rbp+1A0h+hMem], rcx
0x180028976  mov     [rbp+1A0h+pAuthIdentity], rcx
0x18002897a  mov     [rbp+1A0h+hDS], rcx
0x18002897e  mov     [rsp+2A0h+invalue], ecx
0x180028982  movups  xmmword ptr [rbp+1A0h+ObjectAttributes.Length], xmm0
0x180028989  mov     [rbp+1A0h+pResult], rcx
0x18002898d  movups  xmmword ptr [rbp+1A0h+ObjectAttributes+1Ch], xmm0
0x180028994  mov     [rsp+2A0h+var_248], rcx
0x180028999  movups  [rbp+1A0h+var_118], xmm0
0x1800289a0  mov     [rbp+1A0h+mods], rcx
0x1800289a7  movups  [rbp+1A0h+var_138], xmm1
0x1800289ab  mov     [rbp+1A0h+Buffer], rcx
0x1800289af  movups  [rbp+1A0h+var_128], xmm0
0x1800289b3  mov     [rbp+1A0h+var_214], ecx
0x1800289b6  movups  [rbp+1A0h+var_1A0], xmm0
0x1800289ba  mov     [rbp+1A0h+var_210], edx
0x1800289bd  movups  [rbp+1A0h+var_188], xmm0
0x1800289c1  mov     [rbp+1A0h+var_150], rcx
0x1800289c5  movups  [rbp+1A0h+var_170], xmm0
0x1800289c9  mov     [rbp+1A0h+var_148], rcx
0x1800289cd  movups  [rbp+1A0h+var_70], xmm0
0x1800289d4  mov     [rbp+1A0h+var_140], cl
0x1800289d7  movups  xmmword ptr [rbp+1A0h+cred], xmm0
0x1800289de  mov     [rbp+1A0h+var_A0], rcx
0x1800289e5  movups  [rbp+1A0h+var_F8], xmm0
0x1800289ec  mov     [rbp+1A0h+var_1E0], r9
0x1800289f0  movups  [rbp+1A0h+var_E8], xmm0
0x1800289f7  xchg    eax, cs:JoinpCallInProgress
0x1800289fd  mov     [rsp+2A0h+var_23C], ebx
0x180028a01  mov     [rsp+2A0h+var_258], rcx
0x180028a06  cmp     eax, edx
0x180028a08  jnz     short loc_180028A14
0x180028a0a  mov     eax, 6FFh
0x180028a0f  jmp     loc_180029D2F
0x180028a14  mov     rsi, rcx
0x180028a17  mov     [rsp+2A0h+var_250], rcx
0x180028a1c  mov     r13, rcx
0x180028a1f  mov     r14, rcx
0x180028a22  call    IsNetpManageIPCConnectPresent
0x180028a27  test    al, al
0x180028a29  jz      short loc_180028A37
0x180028a2b  call    cs:__imp_NetSetuppOpenLog
0x180028a32  nop     dword ptr [rax+rax+00h]
0x180028a37  call    IsNetpManageIPCConnectPresent
0x180028a3c  test    al, al
0x180028a3e  jz      short loc_180028A53
0x180028a40  lea     rcx, aNetpmanagealtc_23; "NetpManageAltComputerName called:\n"
0x180028a47  call    cs:__imp_NetpLogPrintHelper
0x180028a4e  nop     dword ptr [rax+rax+00h]
0x180028a53  call    IsNetpManageIPCConnectPresent
0x180028a58  test    al, al
0x180028a5a  jz      short loc_180028A72
0x180028a5c  mov     rdx, r15
0x180028a5f  lea     rcx, aAlternatenameW; " AlternateName = %ws\n"
0x180028a66  call    cs:__imp_NetpLogPrintHelper
0x180028a6d  nop     dword ptr [rax+rax+00h]
0x180028a72  call    IsNetpManageIPCConnectPresent
0x180028a77  test    al, al
0x180028a79  jz      short loc_180028A91
0x180028a7b  mov     rdx, rdi
0x180028a7e  lea     rcx, aDomainaccountW; " DomainAccount = %ws\n"
0x180028a85  call    cs:__imp_NetpLogPrintHelper
0x180028a8c  nop     dword ptr [rax+rax+00h]
0x180028a91  call    IsNetpManageIPCConnectPresent
0x180028a96  test    al, al
0x180028a98  jz      short loc_180028AAF
0x180028a9a  mov     edx, ebx
0x180028a9c  lea     rcx, aAction0xLx; " Action = 0x%lx\n"
0x180028aa3  call    cs:__imp_NetpLogPrintHelper
0x180028aaa  nop     dword ptr [rax+rax+00h]
0x180028aaf  call    IsNetpManageIPCConnectPresent
0x180028ab4  mov     edi, [rbp+1A0h+arg_28]
0x180028aba  xor     ebx, ebx
0x180028abc  test    al, al
0x180028abe  jz      short loc_180028AD5
0x180028ac0  mov     edx, edi
0x180028ac2  lea     rcx, aFlags0xLx; " Flags = 0x%lx\n"
0x180028ac9  call    cs:__imp_NetpLogPrintHelper
0x180028ad0  nop     dword ptr [rax+rax+00h]
0x180028ad5  lea     rcx, [rsp+2A0h+ProductType]; ProductType
0x180028ada  call    cs:__imp_RtlGetNtProductType
0x180028ae1  nop     dword ptr [rax+rax+00h]
0x180028ae6  test    al, al
0x180028ae8  jnz     short loc_180028AF5
0x180028aea  mov     ecx, 1
0x180028aef  mov     [rsp+2A0h+ProductType], ecx
0x180028af3  jmp     short loc_180028AF9
0x180028af5  mov     ecx, [rsp+2A0h+ProductType]
0x180028af9  lea     eax, [rcx-2]
0x180028afc  cmp     eax, 1
0x180028aff  jbe     short loc_180028B2B
0x180028b01  call    IsNetpManageIPCConnectPresent
0x180028b06  test    al, al
0x180028b08  jz      short loc_180028B21
0x180028b0a  mov     edx, [rsp+2A0h+ProductType]
0x180028b0e  lea     rcx, aNetpmanagealtc_5; "NetpManageAltComputerName: Not supporte"...
0x180028b15  call    cs:__imp_NetpLogPrintHelper
0x180028b1c  nop     dword ptr [rax+rax+00h]
0x180028b21  mov     ebx, 32h ; '2'
0x180028b26  jmp     loc_180029BBE
0x180028b2b  cmp     ecx, 2
0x180028b2e  jnz     short loc_180028B6B
0x180028b30  lea     edx, [rcx-1]; InfoLevel
0x180028b33  xor     ecx, ecx; lpServer
0x180028b35  lea     r8, [rbp+1A0h+Buffer]; Buffer
0x180028b39  call    cs:__imp_DsRoleGetPrimaryDomainInformation
0x180028b40  nop     dword ptr [rax+rax+00h]
0x180028b45  mov     ebx, eax
0x180028b47  test    eax, eax
0x180028b49  jnz     loc_180029BB9
0x180028b4f  mov     rcx, [rbp+1A0h+Buffer]; Buffer
0x180028b53  mov     r12d, [rcx+4]
0x180028b57  shr     r12d, 3
0x180028b5b  and     r12b, 1
0x180028b5f  call    cs:__imp_DsRoleFreeMemory
0x180028b66  nop     dword ptr [rax+rax+00h]
0x180028b6b  test    edi, edi
0x180028b6d  jz      short loc_180028B9B
0x180028b6f  test    dil, 1
0x180028b73  jnz     short loc_180028B9B
0x180028b75  call    IsNetpManageIPCConnectPresent
0x180028b7a  test    al, al
0x180028b7c  jz      short loc_180028B91
0x180028b7e  lea     rcx, aNetpmanagealtc_31; "NetpManageAltComputerName: Invalid Flag"...
0x180028b85  call    cs:__imp_NetpLogPrintHelper
0x180028b8c  nop     dword ptr [rax+rax+00h]
0x180028b91  mov     ebx, 3ECh
0x180028b96  jmp     loc_180029BB9
0x180028b9b  mov     edx, 2; Format
0x180028ba0  mov     rcx, r15; pszName
0x180028ba3  call    cs:__imp_DnsValidateName_W
0x180028baa  nop     dword ptr [rax+rax+00h]
0x180028baf  mov     ebx, eax
0x180028bb1  xor     eax, eax
0x180028bb3  test    ebx, ebx
0x180028bb5  jz      short loc_180028BDA
0x180028bb7  cmp     ebx, 2554h
0x180028bbd  jz      short loc_180028BDA
0x180028bbf  call    IsNetpManageIPCConnectPresent
0x180028bc4  test    al, al
0x180028bc6  jz      loc_180029BB9
0x180028bcc  mov     edx, ebx
0x180028bce  lea     rcx, aNetpmanagealtc_0; "NetpManageAltComputerName: DnsValidateN"...
0x180028bd5  jmp     loc_180029BAD
0x180028bda  mov     dil, al
0x180028bdd  mov     [rsp+2A0h+var_25E], al
0x180028be1  mov     r15b, al
0x180028be4  mov     [rsp+2A0h+var_260], al
0x180028be8  mov     [rsp+2A0h+var_25F], al
0x180028bec  cmp     [rbp+1A0h+var_1E0], rax
0x180028bf0  jnz     short loc_180028C00
0x180028bf2  cmp     [rsp+2A0h+Password], rax
0x180028bf7  jz      short loc_180028C27
0x180028bf9  mov     [rsp+2A0h+Password], rax
0x180028bfe  jmp     short loc_180028C27
0x180028c00  call    IsNetpManageIPCConnectPresent
0x180028c05  test    al, al
0x180028c07  jz      loc_180029D94
0x180028c0d  mov     rcx, [rbp+1A0h+var_1E0]
0x180028c11  lea     r8, [rbp+1A0h+Domain]
0x180028c15  lea     rdx, [rbp+1A0h+User]
0x180028c19  call    cs:__imp_NetpSeparateUserAndDomain
0x180028c20  nop     dword ptr [rax+rax+00h]
0x180028c25  mov     ebx, eax
0x180028c27  test    ebx, ebx
0x180028c29  jnz     loc_180029D99
0x180028c2f  xor     edx, edx
0x180028c31  lea     rcx, [rsp+2A0h+var_258]
0x180028c36  call    NetpGetComputerNameEx2
0x180028c3b  mov     ebx, eax
0x180028c3d  test    eax, eax
0x180028c3f  jz      short loc_180028C5C
0x180028c41  call    IsNetpManageIPCConnectPresent
0x180028c46  test    al, al
0x180028c48  jz      loc_180029BB9
0x180028c4e  mov     edx, ebx
0x180028c50  lea     rcx, aNetpmanagealtc_33; "NetpManageAltComputerName: NetpGetCompu"...
0x180028c57  jmp     loc_180029BAD
0x180028c5c  call    IsNetpManageIPCConnectPresent
0x180028c61  test    al, al
0x180028c63  jz      loc_180029D69
0x180028c69  mov     rcx, [rsp+2A0h+var_258]
0x180028c6e  lea     rdx, [rbp+1A0h+username]
0x180028c72  call    cs:__imp_NetpGetMachineAccountName
0x180028c79  nop     dword ptr [rax+rax+00h]
0x180028c7e  mov     ebx, eax
0x180028c80  test    eax, eax
0x180028c82  jnz     loc_180029D6E
0x180028c88  mov     edx, [rbp+1A0h+var_218]
0x180028c8b  lea     ecx, [rax+40h]; uFlags
0x180028c8e  add     rdx, rdx; uBytes
0x180028c91  call    cs:__imp_LocalAlloc
0x180028c98  nop     dword ptr [rax+rax+00h]
0x180028c9d  mov     rsi, rax
0x180028ca0  test    rax, rax
0x180028ca3  jnz     short loc_180028CCB
0x180028ca5  call    IsNetpManageIPCConnectPresent
0x180028caa  test    al, al
0x180028cac  jz      short loc_180028CC1
0x180028cae  lea     rcx, aNetpmanagealtc_38; "NetpManageAltComputerName: LocalAlloc f"...
0x180028cb5  call    cs:__imp_NetpLogPrintHelper
0x180028cbc  nop     dword ptr [rax+rax+00h]
0x180028cc1  mov     ebx, 8
0x180028cc6  jmp     loc_180029BB9
0x180028ccb  lea     r9, [rbp+1A0h+var_218]
0x180028ccf  mov     r8, rsi
0x180028cd2  xor     edx, edx
0x180028cd4  xor     ecx, ecx
0x180028cd6  call    cs:__imp_EnumerateLocalComputerNamesW
0x180028cdd  nop     dword ptr [rax+rax+00h]
0x180028ce2  mov     ebx, eax
0x180028ce4  xor     eax, eax
0x180028ce6  test    ebx, ebx
0x180028ce8  jz      short loc_180028D15
0x180028cea  call    IsNetpManageIPCConnectPresent
0x180028cef  test    al, al
0x180028cf1  jz      loc_180029BB9
0x180028cf7  mov     edx, [rbp+1A0h+var_218]
0x180028cfa  lea     rcx, aNetpmanagealtc_17; "NetpManageAltComputerName: EnumerateLoc"...
0x180028d01  mov     r8d, ebx
0x180028d04  call    cs:__imp_NetpLogPrintHelper
0x180028d0b  nop     dword ptr [rax+rax+00h]
0x180028d10  jmp     loc_180029BB9
0x180028d15  cmp     [rsp+2A0h+var_23C], 3
0x180028d1a  mov     [rsp+2A0h+var_25D], al
0x180028d1e  jnz     loc_180028DBA
0x180028d24  mov     rcx, [rsp+2A0h+Hostname]; Hostname
0x180028d29  lea     r8, [rbp+1A0h+nSize]; nSize
0x180028d2d  lea     rdx, [rbp+1A0h+ComputerName]; ComputerName
0x180028d34  mov     [rbp+1A0h+nSize], 10h
0x180028d3b  call    cs:__imp_DnsHostnameToComputerNameW
0x180028d42  nop     dword ptr [rax+rax+00h]
0x180028d47  test    eax, eax
0x180028d49  jnz     short loc_180028D80
0x180028d4b  call    cs:__imp_GetLastError
0x180028d52  nop     dword ptr [rax+rax+00h]
0x180028d57  mov     ebx, eax
0x180028d59  call    IsNetpManageIPCConnectPresent
0x180028d5e  test    al, al
0x180028d60  jz      loc_1800298DD
0x180028d66  mov     edx, ebx
0x180028d68  lea     rcx, aNetpmanagealtc_25; "NetpManageAltComputerName: DnsHostnameT"...
0x180028d6f  call    cs:__imp_NetpLogPrintHelper
0x180028d76  nop     dword ptr [rax+rax+00h]
0x180028d7b  jmp     loc_1800298DD
0x180028d80  lea     rdx, [rbp+1A0h+var_1F0]
0x180028d84  lea     rcx, [rbp+1A0h+ComputerName]
0x180028d8b  call    cs:__imp_NetpGetMachineAccountName
0x180028d92  nop     dword ptr [rax+rax+00h]
0x180028d97  mov     ebx, eax
  ... truncated ...
```
