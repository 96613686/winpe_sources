# RequestCredentials(_WLSM_GLOBAL_CONTEXT *,_WLUI_REQUEST_REASON,_WLUI_REQUEST_FLAGS,_CRED_PROV_CREDENTIAL *,_CRED_PROV_CREDENTIAL *,uint *,int *)

- ea: `0x140016284`
- end: `0x14001683e`
- name: `?RequestCredentials@@YAKPEAU_WLSM_GLOBAL_CONTEXT@@W4_WLUI_REQUEST_REASON@@W4_WLUI_REQUEST_FLAGS@@PEAU_CRED_PROV_CREDENTIAL@@3PEAIPEAH@Z`
- size: `1466`
- prototype: `unsigned int __fastcall(__int64, int, int, __int64, struct _CRED_PROV_CREDENTIAL *, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `27`
- tags: `loader_planting`

## callers

- `0x140015ba0`

## callees

- `0x140012040`
- `0x140012f40`
- `0x140016284`
- `0x1400198e0`
- `0x14001a200`
- `0x1400292b4`
- `0x14002ba10`
- `0x140037740`
- `0x140037b00`
- `0x14003ca84`
- `0x14003f88c`
- `0x140041c34`
- `0x14004a58c`
- `0x14004d2c8`
- `0x14004ea3c`
- `0x14004eae4`
- `0x14004f830`
- `0x14004fdfc`
- `0x140053720`
- `0x1400544e0`
- `0x140056348`
- `0x14005697c`
- `0x14008946c`
- `0x1400895ac`
- `0x140089ba0`
- `0x14008cad4`
- `0x14009cc54`

## import_xrefs

- `ntdll!RtlCopyLuid` at `0x1400165fb`
- `ntdll!RtlCopyLuid` at `0x1400165fb`
- `ext-ms-win-session-winsta-l1-1-0!WinStationFreeUserCredentials` at `0x140016363`
- `ext-ms-win-session-winsta-l1-1-0!WinStationFreeUserCredentials` at `0x140016397`
- `ext-ms-win-session-winsta-l1-1-0!WinStationFreeUserCredentials` at `0x140016363`
- `ext-ms-win-session-winsta-l1-1-0!WinStationFreeUserCredentials` at `0x140016397`
- `ext-ms-win-session-winsta-l1-1-0!WinStationGetRestrictedLogonInfo` at `0x1400165a3`
- `ext-ms-win-session-winsta-l1-1-0!WinStationGetRestrictedLogonInfo` at `0x1400165a3`
- `ext-ms-win-session-winsta-l1-1-0!WinStationGetUserCredentials` at `0x14001633e`
- `ext-ms-win-session-winsta-l1-1-0!WinStationGetUserCredentials` at `0x14001633e`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x140016323`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x140016323`
- `ext-ms-win-winlogon-mincreds-l1-1-0!MinCredGetLogonCredentials` at `0x14001644d`
- `ext-ms-win-winlogon-mincreds-l1-1-0!MinCredGetLogonCredentials` at `0x14001644d`

## pseudocode

```c

```
