# CUserProfile::~CUserProfile(void)

- ea: `0x180034784`
- end: `0x18003480a`
- name: `??1CUserProfile@@QEAA@XZ`
- size: `134`
- prototype: `void __fastcall(LPCWSTR *this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002e180`
- `0x18002f1f0`

## callees

- `0x180034784`
- `0x18006e628`
- `0x18006e6f8`
- `0x1800772c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800347e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800347e9`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800347cc`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800347cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800347a4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800347a4`

## string_xrefs

- `0x1800347b0`: `SeRestorePrivilege`

## pseudocode

```c

```
