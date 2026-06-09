# CServiceRecord::GetDependentServicesInternal(utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>> &,utl::unordered_set<CServiceRecord *,utl::hash<CServiceRecord *>,utl::equal_to<CServiceRecord *>,utl::allocator<CServiceRecord *>> &,ulong,void * *,int *,int)

- ea: `0x140004e58`
- end: `0x1400050b7`
- name: `?GetDependentServicesInternal@CServiceRecord@@IEAAHAEAV?$list@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@utl@@@utl@@AEAV?$unordered_set@PEAVCServiceRecord@@U?$hash@PEAVCServiceRecord@@@utl@@U?$equal_to@PEAVCServiceRecord@@@3@V?$allocator@PEAVCServiceRecord@@@3@@3@KPEAPEAXPEAHH@Z`
- size: `607`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, PHANDLE TokenHandle, int *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400040f8`
- `0x140004e58`

## callees

- `0x140002890`
- `0x140003fc4`
- `0x14000498c`
- `0x140004e58`
- `0x140005c8c`
- `0x140006498`
- `0x140007130`
- `0x1400188fc`
- `0x14003f9b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140004ee2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140004f20`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140004ee2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140004f20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140004f10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140004f78`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140004fee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140004f10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140004f78`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140004fee`

## pseudocode

```c

```
