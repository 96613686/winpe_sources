# WdcDiskMonitor::SetFileName(_WDC_FILE_INFO *,ushort const *)

- ea: `0x1800085f0`
- end: `0x1800088aa`
- name: `?SetFileName@WdcDiskMonitor@@AEAAJPEAU_WDC_FILE_INFO@@PEBG@Z`
- size: `698`
- prototype: `__int64 __fastcall(WdcDiskMonitor *__hidden this, struct _WDC_FILE_INFO *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800081e0`
- `0x18000a4d0`

## callees

- `0x180006a80`
- `0x1800085f0`
- `0x1800088b0`
- `0x18000b854`
- `0x180069ab4`
- `0x180069b40`
- `0x180084e04`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180008615`
- `KERNEL32!GetProcessHeap` at `0x1800086b4`
- `KERNEL32!GetProcessHeap` at `0x180008615`
- `KERNEL32!GetProcessHeap` at `0x1800086b4`
- `KERNEL32!HeapAlloc` at `0x180008626`
- `KERNEL32!HeapAlloc` at `0x180008626`
- `KERNEL32!HeapFree` at `0x1800086c2`
- `KERNEL32!HeapFree` at `0x1800086c2`
- `OLEAUT32!__imp_SysAllocString` at `0x180008675`
- `OLEAUT32!__imp_SysAllocString` at `0x18000875e`
- `OLEAUT32!__imp_SysAllocString` at `0x1800087a4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800087c9`
- `OLEAUT32!__imp_SysAllocString` at `0x180008675`
- `OLEAUT32!__imp_SysAllocString` at `0x18000875e`
- `OLEAUT32!__imp_SysAllocString` at `0x1800087a4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800087c9`
- `OLEAUT32!__imp_SysFreeString` at `0x180008838`
- `OLEAUT32!__imp_SysFreeString` at `0x18000887e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000888c`
- `OLEAUT32!__imp_SysFreeString` at `0x180008838`
- `OLEAUT32!__imp_SysFreeString` at `0x18000887e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000888c`

## string_xrefs

- `0x1800086e9`: `WdcDiskMonitor::SetFileName`
- `0x180008727`: `WdcDiskMonitor::SetFileName`

## pseudocode

```c

```
