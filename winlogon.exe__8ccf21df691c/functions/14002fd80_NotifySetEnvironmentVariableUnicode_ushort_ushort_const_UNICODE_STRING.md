# NotifySetEnvironmentVariableUnicode(ushort * *,ushort const *,_UNICODE_STRING *)

- ea: `0x14002fd80`
- end: `0x1400302e9`
- name: `?NotifySetEnvironmentVariableUnicode@@YAKPEAPEAGPEBGPEAU_UNICODE_STRING@@@Z`
- size: `1385`
- prototype: `unsigned int __fastcall(unsigned __int16 **, const unsigned __int16 *, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14002f788`
- `0x14002f800`

## callees

- `0x1400198e0`
- `0x14001a200`
- `0x14002fd80`
- `0x140043d88`
- `0x14009cc60`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002ff23`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002ff23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002ffd4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002ffd4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002febf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002ff12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002ffc6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002febf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002ff12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002ffc6`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x14002fecd`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x14002fecd`
- `ntdll!RtlCompareUnicodeString` at `0x140030027`
- `ntdll!RtlCompareUnicodeString` at `0x140030027`

## pseudocode

```c

```
