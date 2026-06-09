# LockoutHandleFailedLogon(_LARGE_INTEGER *,int,int)

- ea: `0x140065330`
- end: `0x140065543`
- name: `?LockoutHandleFailedLogon@@YAHPEAT_LARGE_INTEGER@@HH@Z`
- size: `531`
- prototype: `__int64 __fastcall(PLARGE_INTEGER Time, int, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1400647e0`
- `0x140071780`

## callees

- `0x1400060d0`
- `0x1400198e0`
- `0x14001a200`
- `0x14001a520`
- `0x140053720`
- `0x140056348`
- `0x140065330`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400654e4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400654e4`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x140065486`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x140065486`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x140065474`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x140065474`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x1400653c2`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x1400653c2`
- `ntdll!RtlTimeToSecondsSince1980` at `0x1400654a4`
- `ntdll!RtlTimeToSecondsSince1980` at `0x1400654b5`
- `ntdll!RtlTimeToSecondsSince1980` at `0x1400654a4`
- `ntdll!RtlTimeToSecondsSince1980` at `0x1400654b5`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x140065423`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x140065423`

## string_xrefs

- `0x1400653b9`: `TermService`

## pseudocode

```c

```
