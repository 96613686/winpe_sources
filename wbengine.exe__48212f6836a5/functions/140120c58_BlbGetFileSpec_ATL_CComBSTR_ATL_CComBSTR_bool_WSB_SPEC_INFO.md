# BlbGetFileSpec(ATL::CComBSTR &,ATL::CComBSTR &,bool,_WSB_SPEC_INFO &)

- ea: `0x140120c58`
- end: `0x140120e0c`
- name: `?BlbGetFileSpec@@YAJAEAVCComBSTR@ATL@@0_NAEAU_WSB_SPEC_INFO@@@Z`
- size: `436`
- prototype: `int(struct ATL::CComBSTR *, struct ATL::CComBSTR *, bool, struct _WSB_SPEC_INFO *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x14011f5bc`
- `0x14011f9a8`

## callees

- `0x14000bb24`
- `0x14000cbcc`
- `0x140088384`
- `0x1400889f0`
- `0x140088d0c`
- `0x140120c58`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x140120cd1`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x140120d25`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x140120cd1`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x140120d25`
- `KERNEL32!GetLastError` at `0x140120cdd`
- `KERNEL32!GetLastError` at `0x140120d2f`
- `KERNEL32!GetLastError` at `0x140120cdd`
- `KERNEL32!GetLastError` at `0x140120d2f`
- `ole32!CoTaskMemFree` at `0x140120d64`
- `ole32!CoTaskMemFree` at `0x140120db8`
- `ole32!CoTaskMemFree` at `0x140120dc6`
- `ole32!CoTaskMemFree` at `0x140120d64`
- `ole32!CoTaskMemFree` at `0x140120db8`
- `ole32!CoTaskMemFree` at `0x140120dc6`

## pseudocode

```c

```
