# OSDeploymentHelper::CreateAndAcquireSandboxAccessMutex(_GUID const &,void * *,ulong)

- ea: `0x18001981c`
- end: `0x18001999b`
- name: `?CreateAndAcquireSandboxAccessMutex@OSDeploymentHelper@@YAJAEBU_GUID@@PEAPEAXK@Z`
- size: `383`
- prototype: `__int64 __fastcall(GUID *rguid, const struct _GUID *, void **, unsigned int)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180019cc4`
- `0x18001d330`
- `0x18001fe7c`
- `0x180028ea8`

## callees

- `0x180003950`
- `0x18001981c`
- `0x1800199a4`
- `0x18001a8f4`
- `0x180030110`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180019962`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180019962`
- `RPCRT4!UuidToStringW` at `0x1800198b9`
- `RPCRT4!UuidToStringW` at `0x1800198b9`

## pseudocode

```c

```
