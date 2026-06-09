# Windows::Internal::Feedback::HasPackageQueryCapability(void)

- ea: `0x18003e38c`
- end: `0x18003e645`
- name: `?HasPackageQueryCapability@Feedback@Internal@Windows@@YAJXZ`
- size: `697`
- prototype: `__int64 __fastcall(Windows::Internal::Feedback *__hidden this)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003dc50`
- `0x18003e6f8`
- `0x180227bb0`
- `0x180227d10`

## callees

- `0x18000b7e8`
- `0x18003c5e4`
- `0x18003e38c`
- `0x1800456b0`
- `0x180047224`
- `0x180047868`
- `0x1800e9448`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003e42f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003e42f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003e5d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003e5d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e5f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e624`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e62f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e63a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e5f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e624`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e62f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e63a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003e45c`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003e45c`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18003e3c2`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18003e3c2`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18003e4a1`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18003e4a1`

## string_xrefs

- `0x18003e5a4`: `shell\twinui\feedback\lib\feedbackbroker.cpp`

## pseudocode

```c

```
