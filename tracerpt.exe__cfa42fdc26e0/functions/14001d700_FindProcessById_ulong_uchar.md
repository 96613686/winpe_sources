# FindProcessById(ulong,uchar)

- ea: `0x14001d700`
- end: `0x14001d77e`
- name: `?FindProcessById@@YAPEAU_PROCESS_RECORD@@KE@Z`
- size: `126`
- prototype: `struct _PROCESS_RECORD *__fastcall(int, char)`
- caller_count: `12`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400033c0`
- `0x140005834`
- `0x140006588`
- `0x1400069c8`
- `0x1400078ec`
- `0x140008d14`
- `0x140009258`
- `0x14000978c`
- `0x140009d78`
- `0x140009ea8`
- `0x14000a0d4`
- `0x14001cd40`

## callees

- `0x14001d700`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x14001d71b`
- `ntdll!RtlEnterCriticalSection` at `0x14001d71b`
- `ntdll!RtlLeaveCriticalSection` at `0x14001d745`
- `ntdll!RtlLeaveCriticalSection` at `0x14001d764`
- `ntdll!RtlLeaveCriticalSection` at `0x14001d745`
- `ntdll!RtlLeaveCriticalSection` at `0x14001d764`

## pseudocode

```c

```
