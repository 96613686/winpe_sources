# GetCachedRedirectedEntry(_GUID *,ushort const *,ushort *,ulong,CHashTable<_GUID,ushort> *,_RTL_CRITICAL_SECTION *,int *)

- ea: `0x180107680`
- end: `0x1801079b0`
- name: `?GetCachedRedirectedEntry@@YAJPEAU_GUID@@PEBGPEAGKPEAV?$CHashTable@U_GUID@@G@@PEAU_RTL_CRITICAL_SECTION@@PEAH@Z`
- size: `816`
- prototype: `__int64 __usercall@<rax>(void *Source@<rcx>, unsigned __int8 *@<rdx>, LPOLESTR lpsz@<r8>, CByteHashTable *, LPCRITICAL_SECTION lpCriticalSection, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180100df0`
- `0x180104c00`

## callees

- `0x180100a24`
- `0x180103d88`
- `0x180107648`
- `0x180107680`
- `0x180118198`
- `0x1801285e6`
- `0x180128660`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180107752`
- `msvcrt!memcpy_s` at `0x1801077c5`
- `msvcrt!memcpy_s` at `0x18010782b`
- `msvcrt!memcpy_s` at `0x180107752`
- `msvcrt!memcpy_s` at `0x1801077c5`
- `msvcrt!memcpy_s` at `0x18010782b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010772a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010788d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801078fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180107943`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010772a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010788d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801078fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180107943`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180107708`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010784d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801078df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180107708`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010784d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801078df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180107800`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180107800`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801078cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801078cb`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1801078aa`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180107965`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1801078aa`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180107965`
- `api-ms-win-core-com-l1-1-0!CoGetTreatAsClass` at `0x18010778e`
- `api-ms-win-core-com-l1-1-0!CoGetTreatAsClass` at `0x18010778e`

## pseudocode

```c

```
