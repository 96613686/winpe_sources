# UnistoreImpersonator::Impersonate(void)

- ea: `0x18001f2f0`
- end: `0x18001f3be`
- name: `?Impersonate@UnistoreImpersonator@@QEAAJXZ`
- size: `206`
- prototype: `__int64 __fastcall(UnistoreImpersonator *__hidden this)`
- caller_count: `15`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x18001ef00`
- `0x18001f3d0`
- `0x180080a80`
- `0x180080c70`
- `0x180080ec0`
- `0x180086d90`
- `0x180093ec0`
- `0x1800b6dc0`
- `0x1800b77a0`
- `0x1800b7b10`
- `0x1800b7e80`
- `0x1800c8c70`
- `0x1800e46e0`
- `0x1800eb7f0`
- `0x1800eb9b0`

## callees

- `0x180008f0c`
- `0x18001f2f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f37d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f37d`
- `unistore!StartUnifiedStoreWorkForClient` at `0x18001f397`
- `unistore!StartUnifiedStoreWorkForClient` at `0x18001f397`
- `unistore!RegisterRundownProtectionForProcess` at `0x18001f35c`
- `unistore!RegisterRundownProtectionForProcess` at `0x18001f35c`
- `unistore!IsUnistoreInProc` at `0x18001f2fd`
- `unistore!IsUnistoreInProc` at `0x18001f2fd`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001f31a`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001f31a`

## string_xrefs

- `0x18001f339`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\UnistoreImpersonator.h`

## pseudocode

```c

```
