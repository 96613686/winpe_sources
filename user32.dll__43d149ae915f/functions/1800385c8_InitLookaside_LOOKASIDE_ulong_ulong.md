# InitLookaside(_LOOKASIDE *,ulong,ulong)

- ea: `0x1800385c8`
- end: `0x1800386af`
- name: `?InitLookaside@@YAJPEAU_LOOKASIDE@@KK@Z`
- size: `231`
- prototype: `__int64 __fastcall(struct _LOOKASIDE *, unsigned int, unsigned int)`
- caller_count: `7`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180009510`
- `0x180011800`
- `0x180033990`
- `0x180037bd0`
- `0x180039fc0`
- `0x180051d40`
- `0x180057fa0`

## callees

- `0x1800385c8`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180038612`
- `ntdll!RtlEnterCriticalSection` at `0x180038612`
- `ntdll!RtlLeaveCriticalSection` at `0x18003867c`
- `ntdll!RtlLeaveCriticalSection` at `0x180038695`
- `ntdll!RtlLeaveCriticalSection` at `0x18003867c`
- `ntdll!RtlLeaveCriticalSection` at `0x180038695`
- `ntdll!RtlFreeHeap` at `0x1800386a7`
- `ntdll!RtlFreeHeap` at `0x1800386a7`
- `ntdll!RtlAllocateHeap` at `0x1800385ed`
- `ntdll!RtlAllocateHeap` at `0x1800385ed`

## pseudocode

```c

```
