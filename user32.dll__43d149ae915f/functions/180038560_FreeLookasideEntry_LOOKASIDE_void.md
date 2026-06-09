# FreeLookasideEntry(_LOOKASIDE *,void *)

- ea: `0x180038560`
- end: `0x1800385bf`
- name: `?FreeLookasideEntry@@YAXPEAU_LOOKASIDE@@PEAX@Z`
- size: `95`
- prototype: `void(struct _LOOKASIDE *, void *)`
- caller_count: `8`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180008ab0`
- `0x180011800`
- `0x1800320d4`
- `0x180037bd0`
- `0x180038734`
- `0x180051d40`
- `0x18006fad4`
- `0x180079a1c`

## callees

- `0x180038560`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180038582`
- `ntdll!RtlEnterCriticalSection` at `0x180038582`
- `ntdll!RtlLeaveCriticalSection` at `0x18003859a`
- `ntdll!RtlLeaveCriticalSection` at `0x18003859a`
- `ntdll!RtlFreeHeap` at `0x1800385b7`
- `ntdll!RtlFreeHeap` at `0x1800385b7`

## pseudocode

```c

```
