# CallerIdentity::CheckCallerCapability(ushort const *,bool *)

- ea: `0x180047868`
- end: `0x180047b02`
- name: `?CheckCallerCapability@CallerIdentity@@YAJPEBGPEA_N@Z`
- size: `666`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, const unsigned __int16 *, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003e38c`
- `0x180227fac`

## callees

- `0x18000b7e8`
- `0x18003c5e4`
- `0x1800456b0`
- `0x180047224`
- `0x180047868`
- `0x1800e9448`
- `0x180179748`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180047931`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180047931`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180047a88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180047a88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047aad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047ae0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047aeb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047af6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047aad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047ae0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047aeb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047af6`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18004795e`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18004795e`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800478b4`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800478b4`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18004799f`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18004799f`

## pseudocode

```c

```
