# CDlpActionLayoutUsb::CopyProgressRoutine(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *)

- ea: `0x18000d100`
- end: `0x18000d235`
- name: `?CopyProgressRoutine@CDlpActionLayoutUsb@@CAKT_LARGE_INTEGER@@000KKPEAX11@Z`
- size: `309`
- prototype: `unsigned int __fastcall(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x18000abc4`
- `0x18000d100`
- `0x180012f5c`
- `0x18001fd60`
- `0x18002b5bc`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d16b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d1c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d16b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d1c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d192`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d1ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d192`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d1ea`

## string_xrefs

- `0x18000d210`: `LayoutUsb: Requesting cancel from copy engine`

## pseudocode

```c

```
