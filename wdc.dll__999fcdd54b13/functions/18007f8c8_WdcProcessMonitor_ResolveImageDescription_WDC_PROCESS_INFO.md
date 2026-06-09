# WdcProcessMonitor::ResolveImageDescription(_WDC_PROCESS_INFO *)

- ea: `0x18007f8c8`
- end: `0x18007fb64`
- name: `?ResolveImageDescription@WdcProcessMonitor@@AEAAJPEAU_WDC_PROCESS_INFO@@@Z`
- size: `668`
- prototype: `__int64 __fastcall(WdcProcessMonitor *__hidden this, struct _WDC_PROCESS_INFO *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180025694`

## callees

- `0x1800044ac`
- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x18001c9b4`
- `0x18001cb20`
- `0x18002add4`
- `0x180033058`
- `0x18007f8c8`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18007fb49`
- `KERNEL32!CloseHandle` at `0x18007fb49`
- `KERNEL32!GetLastError` at `0x18007fad4`
- `KERNEL32!GetLastError` at `0x18007fad4`
- `KERNEL32!QueryFullProcessImageNameW` at `0x18007faca`
- `KERNEL32!QueryFullProcessImageNameW` at `0x18007faca`
- `OLEAUT32!__imp_SysAllocString` at `0x18007f9a2`
- `OLEAUT32!__imp_SysAllocString` at `0x18007f9a2`
- `OLEAUT32!__imp_SysFreeString` at `0x18007f992`
- `OLEAUT32!__imp_SysFreeString` at `0x18007f992`

## string_xrefs

- `0x18007fa26`: `%systemroot%\system32\ntoskrnl.exe`

## pseudocode

```c

```
