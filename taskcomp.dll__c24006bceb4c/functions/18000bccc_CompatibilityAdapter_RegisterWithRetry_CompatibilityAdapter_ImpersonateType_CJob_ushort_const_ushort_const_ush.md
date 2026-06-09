# CompatibilityAdapter::RegisterWithRetry(CompatibilityAdapter::ImpersonateType,CJob *,ushort const *,ushort const *,ushort const *,int)

- ea: `0x18000bccc`
- end: `0x18000bd76`
- name: `?RegisterWithRetry@CompatibilityAdapter@@QEAAJW4ImpersonateType@1@PEAVCJob@@PEBG22H@Z`
- size: `170`
- prototype: `__int64 __fastcall(__int64, int, __int64, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010750`
- `0x180015280`

## callees

- `0x18000ac28`
- `0x18000bccc`

## import_xrefs

- `msvcrt!rand` at `0x18000bd27`
- `msvcrt!rand` at `0x18000bd27`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000bd56`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000bd56`

## pseudocode

```c

```
