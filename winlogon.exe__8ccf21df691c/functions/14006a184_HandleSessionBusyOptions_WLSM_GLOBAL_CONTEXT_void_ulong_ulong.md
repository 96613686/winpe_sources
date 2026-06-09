# HandleSessionBusyOptions(_WLSM_GLOBAL_CONTEXT *,void *,ulong,ulong)

- ea: `0x14006a184`
- end: `0x14006a5ba`
- name: `?HandleSessionBusyOptions@@YAJPEAU_WLSM_GLOBAL_CONTEXT@@PEAXKK@Z`
- size: `1078`
- prototype: `__int64 __fastcall(struct _WLSM_GLOBAL_CONTEXT *, void *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14006e950`

## callees

- `0x1400057f4`
- `0x1400064b0`
- `0x140006970`
- `0x14000aa04`
- `0x14000d4e0`
- `0x140013050`
- `0x140016850`
- `0x140016a30`
- `0x140037b00`
- `0x14003d7d8`
- `0x140041c34`
- `0x14004ddc8`
- `0x140053720`
- `0x1400544e0`
- `0x140056348`
- `0x14005eebc`
- `0x140067224`
- `0x1400687f4`
- `0x14006a184`
- `0x14008c9d0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14006a2b7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14006a2b7`
- `ext-ms-win-session-winsta-l1-1-0!WinStationReportUIResult` at `0x14006a4ca`
- `ext-ms-win-session-winsta-l1-1-0!WinStationReportUIResult` at `0x14006a4ca`
- `ext-ms-win-session-winsta-l1-1-4!WinStationGetLastWinlogonNotification` at `0x14006a26c`
- `ext-ms-win-session-winsta-l1-1-4!WinStationGetLastWinlogonNotification` at `0x14006a26c`

## string_xrefs

- `0x14006a201`: `lsm.dll`
- `0x14006a333`: `clientcore\ds\security\umstartup\winlogon\core\logon.cxx`
- `0x14006a373`: `clientcore\ds\security\umstartup\winlogon\core\logon.cxx`
- `0x14006a3f6`: `clientcore\ds\security\umstartup\winlogon\core\logon.cxx`
- `0x14006a4a4`: `clientcore\ds\security\umstartup\winlogon\core\logon.cxx`

## pseudocode

```c

```
