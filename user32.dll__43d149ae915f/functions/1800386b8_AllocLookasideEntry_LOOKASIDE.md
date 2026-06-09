# AllocLookasideEntry(_LOOKASIDE *)

- ea: `0x1800386b8`
- end: `0x18003872d`
- name: `?AllocLookasideEntry@@YAPEAXPEAU_LOOKASIDE@@@Z`
- size: `117`
- prototype: `void *__fastcall(struct _LOOKASIDE *)`
- caller_count: `7`
- callee_count: `2`
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

- `0x1800386b8`
- `0x180096dc5`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x1800386cc`
- `ntdll!RtlEnterCriticalSection` at `0x1800386cc`
- `ntdll!RtlLeaveCriticalSection` at `0x1800386e9`
- `ntdll!RtlLeaveCriticalSection` at `0x1800386e9`
- `ntdll!RtlAllocateHeap` at `0x18003871d`
- `ntdll!RtlAllocateHeap` at `0x18003871d`

## pseudocode

```c

```
