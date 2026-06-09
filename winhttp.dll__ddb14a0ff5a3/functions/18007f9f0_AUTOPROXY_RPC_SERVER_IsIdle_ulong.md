# AUTOPROXY_RPC_SERVER::IsIdle(ulong)

- ea: `0x18007f9f0`
- end: `0x18007facb`
- name: `?IsIdle@AUTOPROXY_RPC_SERVER@@QEAAHK@Z`
- size: `219`
- prototype: `__int64 __fastcall(AUTOPROXY_RPC_SERVER *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18007f970`

## callees

- `0x1800532d8`
- `0x18007f9f0`
- `0x1800db6b0`
- `0x1800dd710`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007fa27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007fa27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fa51`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fa73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fa51`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fa73`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007fa2d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007fa2d`

## pseudocode

```c

```
