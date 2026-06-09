# InvokeDefaultBrowserSearch(ushort const *)

- ea: `0x180037534`
- end: `0x1800376a4`
- name: `?InvokeDefaultBrowserSearch@@YAJPEBG@Z`
- size: `368`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007b9ac`

## callees

- `0x18000b7d0`
- `0x18000b854`
- `0x180037534`
- `0x18003a3c0`
- `0x18003b0ac`

## import_xrefs

- `SHLWAPI!AssocQueryStringW` at `0x1800375c7`
- `SHLWAPI!AssocQueryStringW` at `0x1800375c7`
- `SHELL32!ShellExecuteExW` at `0x18003762b`
- `SHELL32!ShellExecuteExW` at `0x18003762b`
- `KERNEL32!GetLastError` at `0x180037639`
- `KERNEL32!GetLastError` at `0x180037639`

## string_xrefs

- `0x1800375d7`: `https://www.bing.com/search?q=`

## pseudocode

```c

```
