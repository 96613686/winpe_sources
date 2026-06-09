# GetCachedRedirectedEntry(_GUID *,ushort const *,ushort *,ulong,CHashTable<_GUID,ushort> *,_RTL_CRITICAL_SECTION *,int *)

- ea: `0x1800fc924`
- end: `0x1800fcbf9`
- name: `?GetCachedRedirectedEntry@@YAJPEAU_GUID@@PEBGPEAGKPEAV?$CHashTable@U_GUID@@G@@PEAU_RTL_CRITICAL_SECTION@@PEAH@Z`
- size: `725`
- prototype: `__int64 __usercall@<rax>(void *Source@<rcx>, unsigned __int8 *@<rdx>, LPOLESTR lpsz@<r8>, CByteHashTable *, LPCRITICAL_SECTION lpCriticalSection, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800f6630`
- `0x1800fa100`

## callees

- `0x1800f62a4`
- `0x1800f9354`
- `0x1800fc8ec`
- `0x1800fc924`
- `0x18010c740`
- `0x18011ba26`
- `0x18011baa0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800fc9ea`
- `msvcrt!memcpy_s` at `0x1800fca51`
- `msvcrt!memcpy_s` at `0x1800fcaab`
- `msvcrt!memcpy_s` at `0x1800fc9ea`
- `msvcrt!memcpy_s` at `0x1800fca51`
- `msvcrt!memcpy_s` at `0x1800fcaab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fc9c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fcb01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fcb5a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fcb99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fc9c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fcb01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fcb5a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fcb99`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800fc9ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800fcac7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800fcb41`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800fc9ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800fcac7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800fcb41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fca86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fca86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fcb33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fcb33`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800fcb18`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800fcbb5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800fcb18`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800fcbb5`
- `api-ms-win-core-com-l1-1-0!CoGetTreatAsClass` at `0x1800fca20`
- `api-ms-win-core-com-l1-1-0!CoGetTreatAsClass` at `0x1800fca20`

## pseudocode

```c

```
