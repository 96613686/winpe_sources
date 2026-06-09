# SimpleRemoteActivation(void *,CrossContainerServerSet *,tagORPCTHIS *,__MIDL_XmitDefs_0003 *,tagORPCTHAT *,__MIDL_XmitDefs_0011 *,_GUID const *,ushort const *,ulong,ushort *,tagMInterfacePointer *,ulong,ulong,ulong,_GUID const *,ushort,ushort * const,CONTAINERVERSION_FOR_NEGOTIATION const *,_GUID const &,unsigned __int64 *,tagDUALSTRINGARRAY * *,_GUID *,unsigned __int64 *,_GUID *,ulong *,tagCOMVERSION *,CONTAINERVERSION *,tagMInterfacePointer * *,long *)

- ea: `0x18009e608`
- end: `0x18009f271`
- name: `?SimpleRemoteActivation@@YAJPEAXPEAVCrossContainerServerSet@@PEAUtagORPCTHIS@@PEAU__MIDL_XmitDefs_0003@@PEAUtagORPCTHAT@@PEAU__MIDL_XmitDefs_0011@@PEBU_GUID@@PEBGKPEAGPEAUtagMInterfacePointer@@KKK6GQEAGPEBUCONTAINERVERSION_FOR_NEGOTIATION@@AEBU6@PEA_KPEAPEAUtagDUALSTRINGARRAY@@PEAU6@PEA_KPEAU6@PEAKPEAUtagCOMVERSION@@PEAUCONTAINERVERSION@@PEAPEAU7@PEAJ@Z`
- size: `3177`
- prototype: `__int64 __fastcall(void *, struct CrossContainerServerSet *, struct tagORPCTHIS *, struct __MIDL_XmitDefs_0003 *, struct tagORPCTHAT *, struct __MIDL_XmitDefs_0011 *, const struct _GUID *, PCWSTR sourceString, unsigned int, unsigned __int16 *, struct tagMInterfacePointer *Src, unsigned int, unsigned int, unsigned int, const struct _GUID *, unsigned __int16, unsigned __int16 *const, const struct CONTAINERVERSION_FOR_NEGOTIATION *, const struct _GUID *, unsigned __int64 *, struct tagDUALSTRINGARRAY **, struct _GUID *, unsigned __int64 *, struct _GUID *, unsigned int *, struct tagCOMVERSION *, struct CONTAINERVERSION *, struct tagMInterfacePointer **, int *)`
- caller_count: `2`
- callee_count: `25`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18009b390`
- `0x18009c6b0`

## callees

- `0x180003210`
- `0x1800055c0`
- `0x180005b40`
- `0x180008d14`
- `0x1800210f8`
- `0x180024418`
- `0x18002750c`
- `0x18002c498`
- `0x180031a78`
- `0x18005bb8c`
- `0x180064b54`
- `0x18008d85c`
- `0x18008e54c`
- `0x180091a10`
- `0x180095c0c`
- `0x18009de74`
- `0x18009e608`
- `0x18009f374`
- `0x1800b7ac0`
- `0x1800b8428`
- `0x180106f00`
- `0x18010c2a0`
- `0x18010c6ac`
- `0x180112d78`
- `0x180114010`

## import_xrefs

- `ntdll!RtlIsMultiSessionSku` at `0x18009eb0d`
- `ntdll!RtlIsMultiSessionSku` at `0x18009eb0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009ebff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009ec76`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009edc5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009f166`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009ebff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009ec76`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009edc5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009f166`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009e92b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009ed27`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009ed7f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009e92b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009ed27`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009ed7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18009ead3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18009ead3`

## string_xrefs

- `0x18009e731`: `onecore\com\combase\rpcss\olescm\remactif.cxx`
- `0x18009e999`: `onecore\com\combase\rpcss\olescm\remactif.cxx`
- `0x18009ea4d`: `onecore\com\combase\rpcss\olescm\remactif.cxx`
- `0x18009eb95`: `onecore\com\combase\rpcss\olescm\remactif.cxx`
- `0x18009ebdd`: `onecore\com\combase\rpcss\olescm\remactif.cxx`
- `0x18009eda0`: `onecore\com\combase\rpcss\olescm\remactif.cxx`
- `0x18009eeb8`: `onecore\com\combase\rpcss\olescm\remactif.cxx`
- `0x18009ef2a`: `onecore\com\combase\rpcss\olescm\remactif.cxx`
- `0x18009f0c3`: `onecore\com\combase\rpcss\olescm\remactif.cxx`
- `0x18009f1df`: `onecore\com\combase\rpcss\olescm\remactif.cxx`
- `0x18009f22f`: `onecore\com\combase\rpcss\olescm\remactif.cxx`

## pseudocode

```c

```
