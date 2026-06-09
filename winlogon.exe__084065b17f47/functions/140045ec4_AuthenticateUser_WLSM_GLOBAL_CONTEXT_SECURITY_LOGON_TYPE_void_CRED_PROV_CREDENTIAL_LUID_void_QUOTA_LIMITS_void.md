# AuthenticateUser(_WLSM_GLOBAL_CONTEXT *,_SECURITY_LOGON_TYPE,void *,_CRED_PROV_CREDENTIAL *,_LUID *,void * *,_QUOTA_LIMITS *,void * *,ulong *,long *,long *,int *)

- ea: `0x140045ec4`
- end: `0x14004735f`
- name: `?AuthenticateUser@@YAKPEAU_WLSM_GLOBAL_CONTEXT@@W4_SECURITY_LOGON_TYPE@@PEAXPEAU_CRED_PROV_CREDENTIAL@@PEAU_LUID@@PEAPEAXPEAU_QUOTA_LIMITS@@5PEAKPEAJ8PEAH@Z`
- size: `5275`
- prototype: `unsigned int(struct _WLSM_GLOBAL_CONTEXT *, enum _SECURITY_LOGON_TYPE, void *, struct _CRED_PROV_CREDENTIAL *, struct _LUID *, void **, struct _QUOTA_LIMITS *, void **, unsigned int *, int *, int *, int *)`
- caller_count: `2`
- callee_count: `39`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140044c90`
- `0x14006cf20`

## callees

- `0x140002300`
- `0x140002564`
- `0x1400057f4`
- `0x140013050`
- `0x140015720`
- `0x1400198e0`
- `0x14001a200`
- `0x1400285f0`
- `0x14002ba10`
- `0x1400320e4`
- `0x140032414`
- `0x140032550`
- `0x1400326a8`
- `0x140034700`
- `0x140036d38`
- `0x140037e2c`
- `0x140039458`
- `0x14003a97c`
- `0x14003ba50`
- `0x14003f584`
- `0x140041c34`
- `0x140043d14`
- `0x140044800`
- `0x140045ec4`
- `0x14004ca84`
- `0x14004df08`
- `0x14004ea3c`
- `0x14004eb98`
- `0x14004effc`
- `0x140053720`
- `0x1400544e0`
- `0x1400560f4`
- `0x140056348`
- `0x140066f40`
- `0x140068a9c`
- `0x14006b9d4`
- `0x14006caf0`
- `0x14008efdc`
- `0x14009753c`

## import_xrefs

- `ntdll!NtAllocateLocallyUniqueId` at `0x140046abf`
- `ntdll!NtAllocateLocallyUniqueId` at `0x140046abf`
- `ntdll!RtlGetActiveConsoleId` at `0x14004689e`
- `ntdll!RtlGetActiveConsoleId` at `0x14004689e`
- `ntdll!RtlInitString` at `0x140046b66`
- `ntdll!RtlInitString` at `0x140046b66`
- `ntdll!RtlNtStatusToDosError` at `0x140046ac7`
- `ntdll!RtlNtStatusToDosError` at `0x140047192`
- `ntdll!RtlNtStatusToDosError` at `0x14009f3ac`
- `ntdll!RtlNtStatusToDosError` at `0x140046ac7`
- `ntdll!RtlNtStatusToDosError` at `0x140047192`
- `ntdll!RtlNtStatusToDosError` at `0x14009f3ac`
- `SspiCli!SeciAllocateAndSetCallFlags` at `0x140046da8`
- `SspiCli!SeciAllocateAndSetCallFlags` at `0x140046da8`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x140046d97`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x140046d97`
- `SspiCli!LsaLogonUser` at `0x140046e78`
- `SspiCli!LsaLogonUser` at `0x140046e78`
- `SspiCli!SeciFreeCallContext` at `0x1400471f5`
- `SspiCli!SeciFreeCallContext` at `0x14009f40c`
- `SspiCli!SeciFreeCallContext` at `0x1400471f5`
- `SspiCli!SeciFreeCallContext` at `0x14009f40c`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrLogonUser` at `0x140046c95`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrLogonUser` at `0x140046c95`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x140046937`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x140046937`

## string_xrefs

- `0x140046ccb`: `usermgr.dll`

## pseudocode

```c

```
