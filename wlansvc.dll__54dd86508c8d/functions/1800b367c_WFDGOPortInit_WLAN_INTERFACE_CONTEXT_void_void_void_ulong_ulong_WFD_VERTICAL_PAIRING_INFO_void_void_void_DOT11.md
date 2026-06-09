# WFDGOPortInit(_WLAN_INTERFACE_CONTEXT *,void (*)(void *,void *,ulong,ulong,_WFD_VERTICAL_PAIRING_INFO *),void (*)(void *,void *,_DOT11_WPS_CONFIG_METHOD,ulong,ulong),void (*)(void *,_GUID *,uchar (*)[6],_WFD_DEVICE_DESCRIPTOR *,int,ulong,_DOT11_AUTH_ALGORITHM,int),void (*)(void *,_GUID const &,uchar const (&)[6],_DOT11_AUTH_ALGORITHM,ulong),void (*)(void *,_GUID *,uchar (*)[6],uchar (*)[6],_WFD_GROUP_ID *,_DOT11_WFD_CHANNEL *,ulong,uchar *,int),void *)

- ea: `0x1800b367c`
- end: `0x1800b39f5`
- name: `?WFDGOPortInit@@YAKPEAU_WLAN_INTERFACE_CONTEXT@@P6AXPEAX1KKPEAU_WFD_VERTICAL_PAIRING_INFO@@@ZP6AX11W4_DOT11_WPS_CONFIG_METHOD@@KK@ZP6AX1PEAU_GUID@@PEAY05EPEAU_WFD_DEVICE_DESCRIPTOR@@HKW4_DOT11_AUTH_ALGORITHM@@H@ZP6AX1AEBU4@AEAY05$$CBE9K@ZP6AX1677PEAU_WFD_GROUP_ID@@PEAU_DOT11_WFD_CHANNEL@@KPEAEH@Z1@Z`
- size: `889`
- prototype: `unsigned int __usercall@<eax>(struct _WLAN_INTERFACE_CONTEXT *@<rcx>, void (*)(void *, void *, unsigned int, unsigned int, struct _WFD_VERTICAL_PAIRING_INFO *)@<rdx>, void (__high *)(void *, void *, enum _DOT11_WPS_CONFIG_METHOD, unsigned int, unsigned int)@<r8>, void (*)(void *, struct _GUID *, unsigned __int8 (*)[6], struct _WFD_DEVICE_DESCRIPTOR *, int, unsigned int, enum _DOT11_AUTH_ALGORITHM, int)@<r9>, void (*)(void *, const struct _GUID *, const unsigned __int8 (*)[6], enum _DOT11_AUTH_ALGORITHM, unsigned int), void (*)(void *, struct _GUID *, unsigned __int8 (*)[6], unsigned __int8 (*)[6], struct _WFD_GROUP_ID *, struct _DOT11_WFD_CHANNEL *, unsigned int, unsigned __int8 *, int), void *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x1800cc780`
- `0x180195554`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x18008ba08`
- `0x18008d594`
- `0x18008d690`
- `0x180090ce8`
- `0x1800b367c`
- `0x1800c6774`
- `0x1800cafb4`
- `0x1800dabbc`
- `0x1800dc6bc`
- `0x1800dd6ac`
- `0x18019c3d4`
- `0x18019d900`
- `0x18019e3b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b37ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b39a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b37ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b39a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b36e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b3935`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b3989`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b36e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b3935`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b3989`

## pseudocode

```c

```
