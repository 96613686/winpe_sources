# SetupChange(_PRINTHANDLE *,ulong,ushort *,ulong *,ulong,ulong,_PRINTER_NOTIFY_OPTIONS *,_PRINTER_NOTIFY_INIT * *,void *,IRemoteNotifyChannel *)

- ea: `0x140067258`
- end: `0x1400673f6`
- name: `?SetupChange@@YAHPEAU_PRINTHANDLE@@KPEAGPEAKKKPEAU_PRINTER_NOTIFY_OPTIONS@@PEAPEAU_PRINTER_NOTIFY_INIT@@PEAXPEAUIRemoteNotifyChannel@@@Z`
- size: `414`
- prototype: `__int64 __fastcall(struct _PRINTHANDLE *, unsigned int, unsigned __int16 *, unsigned int *, unsigned int, unsigned int, struct _PRINTER_NOTIFY_OPTIONS *, struct _PRINTER_NOTIFY_INIT **, void *, struct IRemoteNotifyChannel *)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x14006669c`
- `0x140067670`

## callees

- `0x1400041c0`
- `0x140010c2c`
- `0x140013fe8`
- `0x1400140cc`
- `0x1400664e8`
- `0x140066ca8`
- `0x140067258`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006733c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006733c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140067392`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140067392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400673a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400673a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400673e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400673e1`

## string_xrefs

- `0x14006728c`: `Already watching printer handle.`

## pseudocode

```c

```
