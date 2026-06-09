# ScSendPreshutdownControl(CServiceRecord *)

- ea: `0x140003a88`
- end: `0x140003c31`
- name: `?ScSendPreshutdownControl@@YAKPEAVCServiceRecord@@@Z`
- size: `425`
- prototype: `unsigned int __fastcall(struct CServiceRecord *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x1400386c4`

## callees

- `0x140003a88`
- `0x140003e54`
- `0x140004c98`
- `0x1400188fc`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140003aba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140003aba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140003aed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140003c10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140003aed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140003c10`
- `ntdll!RtlReleaseResource` at `0x140003afa`
- `ntdll!RtlReleaseResource` at `0x140003c1d`
- `ntdll!RtlReleaseResource` at `0x140003afa`
- `ntdll!RtlReleaseResource` at `0x140003c1d`
- `ntdll!RtlAcquireResourceShared` at `0x140003aaa`
- `ntdll!RtlAcquireResourceShared` at `0x140003aaa`

## pseudocode

```c

```
