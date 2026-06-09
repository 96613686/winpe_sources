# WxSIDToSIDString(_SID *,CWxString *)

- ea: `0x18004b4e0`
- end: `0x18004b767`
- name: `?WxSIDToSIDString@@YAJPEAU_SID@@PEAVCWxString@@@Z`
- size: `647`
- prototype: `__int64 __fastcall(struct _SID *, struct CWxString *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a210`
- `0x1800a7888`

## callees

- `0x18004b4e0`
- `0x180080fb0`
- `0x180084259`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004b5d8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004b5d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004b640`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004b640`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b707`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b707`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b6a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b6a7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004b514`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004b514`

## pseudocode

```c

```
