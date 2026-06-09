# CConnectionRequestParameters::SetAll(ADDRESS_RESOLUTION_OPTIONS *,ulong,ulong,ushort,ulong,long,int,int,int,int,int,int,void *,char const *,SECURITY_CACHE_LIST_ENTRY *,CServerInfo *,int)

- ea: `0x18004ee70`
- end: `0x18004f05b`
- name: `?SetAll@CConnectionRequestParameters@@QEAAKPEAUADDRESS_RESOLUTION_OPTIONS@@KKGKJHHHHHHPEAXPEBDPEAVSECURITY_CACHE_LIST_ENTRY@@PEAVCServerInfo@@H@Z`
- size: `491`
- prototype: `unsigned int __fastcall(CConnectionRequestParameters *__hidden this, struct ADDRESS_RESOLUTION_OPTIONS *, unsigned int, unsigned int, unsigned __int16, unsigned int, int, int, int, int, int, int, int, void *, const char *Src, struct SECURITY_CACHE_LIST_ENTRY *, struct CServerInfo *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180160f10`
- `0x18017c558`

## callees

- `0x18002a4c4`
- `0x18004edf0`
- `0x18004ee70`
- `0x1800c00ec`
- `0x1800c25b4`
- `0x1800d5e78`
- `0x180154882`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ef63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ef63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ef3e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ef3e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004efcb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004efcb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004eff9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004eff9`
- `CRYPT32!CertFreeCertificateContext` at `0x18004f036`
- `CRYPT32!CertFreeCertificateContext` at `0x18004f036`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18004f01d`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18004f01d`

## pseudocode

```c

```
