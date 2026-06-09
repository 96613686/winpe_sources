# SimpleRemoteActivation(void *,CrossContainerServerSet *,tagORPCTHIS *,__MIDL_XmitDefs_0003 *,tagORPCTHAT *,__MIDL_XmitDefs_0011 *,_GUID const *,ushort const *,ulong,ushort *,tagMInterfacePointer *,ulong,ulong,ulong,_GUID const *,ushort,ushort * const,CONTAINERVERSION_FOR_NEGOTIATION const *,_GUID const &,unsigned __int64 *,tagDUALSTRINGARRAY * *,_GUID *,unsigned __int64 *,_GUID *,ulong *,tagCOMVERSION *,CONTAINERVERSION *,tagMInterfacePointer * *,long *)

- ea: `0x180098ff0`
- end: `0x180099c2d`
- name: `?SimpleRemoteActivation@@YAJPEAXPEAVCrossContainerServerSet@@PEAUtagORPCTHIS@@PEAU__MIDL_XmitDefs_0003@@PEAUtagORPCTHAT@@PEAU__MIDL_XmitDefs_0011@@PEBU_GUID@@PEBGKPEAGPEAUtagMInterfacePointer@@KKK6GQEAGPEBUCONTAINERVERSION_FOR_NEGOTIATION@@AEBU6@PEA_KPEAPEAUtagDUALSTRINGARRAY@@PEAU6@PEA_KPEAU6@PEAKPEAUtagCOMVERSION@@PEAUCONTAINERVERSION@@PEAPEAU7@PEAJ@Z`
- size: `3133`
- prototype: `__int64 __fastcall(struct ComWinRTActivationProperties *, struct CrossContainerServerSet *, struct tagORPCTHIS *, struct __MIDL_XmitDefs_0003 *, struct tagORPCTHAT *, struct __MIDL_XmitDefs_0011 *, const struct _GUID *, PCWSTR sourceString, unsigned int, unsigned __int16 *, struct tagMInterfacePointer *Src, unsigned int, unsigned int, unsigned int, struct _GUID *, unsigned __int16, unsigned __int16 *const, const struct CONTAINERVERSION_FOR_NEGOTIATION *, const struct _GUID *, unsigned __int64 *, struct tagDUALSTRINGARRAY **, struct _GUID *, unsigned __int64 *, struct _GUID *, unsigned int *, struct tagCOMVERSION *, struct CONTAINERVERSION *, struct tagMInterfacePointer **, int *)`
- caller_count: `2`
- callee_count: `24`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180095e90`
- `0x180097130`

## callees

- `0x180004c80`
- `0x1800051f0`
- `0x18000834c`
- `0x18000d4c4`
- `0x18001cad8`
- `0x1800222f4`
- `0x18002ba28`
- `0x18002ebac`
- `0x180031950`
- `0x180056d48`
- `0x18005faa8`
- `0x180088d3c`
- `0x1800899b0`
- `0x18008e98c`
- `0x180098884`
- `0x180098ff0`
- `0x180099d34`
- `0x1800b27e0`
- `0x1800b3128`
- `0x1800fe6e8`
- `0x1801038f0`
- `0x180103cd8`
- `0x18010a078`
- `0x18010b010`

## import_xrefs

- `ntdll!RtlIsMultiSessionSku` at `0x1800994f4`
- `ntdll!RtlIsMultiSessionSku` at `0x1800994f4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18009948a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18009948a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800995e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099651`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009978e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099b29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800995e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099651`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009978e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099b29`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180099313`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800996fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009974e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180099313`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800996fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009974e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800994c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800994c0`

## string_xrefs

- `0x180099119`: `onecore\com\combase\rpcss\olescm\remactif.cxx`
- `0x18009937b`: `onecore\com\combase\rpcss\olescm\remactif.cxx`
- `0x18009942f`: `onecore\com\combase\rpcss\olescm\remactif.cxx`
- `0x180099576`: `onecore\com\combase\rpcss\olescm\remactif.cxx`
- `0x1800995be`: `onecore\com\combase\rpcss\olescm\remactif.cxx`
- `0x180099769`: `onecore\com\combase\rpcss\olescm\remactif.cxx`
- `0x18009987b`: `onecore\com\combase\rpcss\olescm\remactif.cxx`
- `0x1800998ed`: `onecore\com\combase\rpcss\olescm\remactif.cxx`
- `0x180099a86`: `onecore\com\combase\rpcss\olescm\remactif.cxx`
- `0x180099b9c`: `onecore\com\combase\rpcss\olescm\remactif.cxx`
- `0x180099bec`: `onecore\com\combase\rpcss\olescm\remactif.cxx`

## pseudocode

```c

```
