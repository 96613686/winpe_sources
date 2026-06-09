# SetupChange(_PRINTHANDLE *,ulong,ushort *,ulong *,ulong,ulong,_PRINTER_NOTIFY_OPTIONS *,_PRINTER_NOTIFY_INIT * *,void *,IRemoteNotifyChannel *)

- ea: `0x14006d8e8`
- end: `0x14006da9f`
- name: `?SetupChange@@YAHPEAU_PRINTHANDLE@@KPEAGPEAKKKPEAU_PRINTER_NOTIFY_OPTIONS@@PEAPEAU_PRINTER_NOTIFY_INIT@@PEAXPEAUIRemoteNotifyChannel@@@Z`
- size: `439`
- prototype: `__int64 __fastcall(struct _PRINTHANDLE *, unsigned int, unsigned __int16 *, unsigned int *, unsigned int, unsigned int, struct _PRINTER_NOTIFY_OPTIONS *, struct _PRINTER_NOTIFY_INIT **, void *, struct IRemoteNotifyChannel *)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x14006cc88`
- `0x14006dd70`

## callees

- `0x140004790`
- `0x140011f7c`
- `0x140015290`
- `0x140015378`
- `0x14006ca98`
- `0x14006d350`
- `0x14006d8e8`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006d9cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006d9cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14006da28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14006da28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006da43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006da43`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006da83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006da83`

## string_xrefs

- `0x14006d91c`: `Already watching printer handle.`

## pseudocode

```c

```
