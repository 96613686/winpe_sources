# CEventNotifier::RegisterEventCB(ushort *,_GUID const *,_GUID const *,ushort const *,ushort *,ushort *,ushort *,_FILETIME &,int)

- ea: `0x180002610`
- end: `0x1800028ec`
- name: `?RegisterEventCB@CEventNotifier@@AEAAJPEAGPEBU_GUID@@1PEBG000AEAU_FILETIME@@H@Z`
- size: `732`
- prototype: `int(CEventNotifier *__hidden this, unsigned __int16 *, const struct _GUID *, const struct _GUID *, const unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, struct _FILETIME *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180001cd4`
- `0x1800315a0`

## callees

- `0x180002610`
- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x180010d78`
- `0x1800287b0`
- `0x18002de18`
- `0x18002def8`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800027df`
- `KERNEL32!LocalFree` at `0x1800027df`
- `KERNEL32!LocalAlloc` at `0x1800026df`
- `KERNEL32!LocalAlloc` at `0x1800026df`
- `KERNEL32!lstrlenW` at `0x18000266e`
- `KERNEL32!lstrlenW` at `0x18000266e`
- `OLEAUT32!__imp_SysAllocString` at `0x180002740`
- `OLEAUT32!__imp_SysAllocString` at `0x180002815`
- `OLEAUT32!__imp_SysAllocString` at `0x180002836`
- `OLEAUT32!__imp_SysAllocString` at `0x180002854`
- `OLEAUT32!__imp_SysAllocString` at `0x180002740`
- `OLEAUT32!__imp_SysAllocString` at `0x180002815`
- `OLEAUT32!__imp_SysAllocString` at `0x180002836`
- `OLEAUT32!__imp_SysAllocString` at `0x180002854`
- `OLEAUT32!__imp_SysFreeString` at `0x1800027a4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800027b2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800027c4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800027d6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800027a4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800027b2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800027c4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800027d6`

## string_xrefs

- `0x180002684`: `CEventNotifier::RegisterEventCB: ptszCommandline is greater than MAX_PATH characters!`
- `0x1800026a6`: `CEventNotifier::RegisterEventCB: ptszCommandline is greater than MAX_PATH characters!`

## pseudocode

```c

```
