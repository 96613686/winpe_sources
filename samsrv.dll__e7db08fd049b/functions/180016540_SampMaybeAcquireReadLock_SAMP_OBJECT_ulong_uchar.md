# SampMaybeAcquireReadLock(_SAMP_OBJECT *,ulong,uchar *)

- ea: `0x180016540`
- end: `0x180016797`
- name: `?SampMaybeAcquireReadLock@@YAXPEAU_SAMP_OBJECT@@KPEAE@Z`
- size: `599`
- prototype: `void __fastcall(struct _SAMP_OBJECT *, unsigned int, unsigned __int8 *)`
- caller_count: `13`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180002b40`
- `0x180009030`
- `0x180015c50`
- `0x180015e90`
- `0x180036700`
- `0x18004f050`
- `0x1800559a0`
- `0x180055cc0`
- `0x1800647e0`
- `0x180064b60`
- `0x1800a3130`
- `0x1800a8e60`
- `0x1800ae5f0`

## callees

- `0x180012a28`
- `0x180016540`
- `0x180024dc0`
- `0x1800270b4`
- `0x180027e24`
- `0x1800372ac`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18001659f`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001659f`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001657d`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001657d`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18001658f`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18001658f`
- `ntdll!RtlEnterCriticalSection` at `0x180016628`
- `ntdll!RtlEnterCriticalSection` at `0x180016628`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180016612`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180016635`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180016612`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180016635`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtSetGlobalTransactionType` at `0x18001678c`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtSetGlobalTransactionType` at `0x18001678c`

## pseudocode

```c

```
