# CMachineName::SetComputerNameHelper(_COMPUTER_NAME_FORMAT,ushort * *)

- ea: `0x1800f8438`
- end: `0x1800f85cf`
- name: `?SetComputerNameHelper@CMachineName@@AEAAXW4_COMPUTER_NAME_FORMAT@@PEAPEAG@Z`
- size: `407`
- prototype: `void(CMachineName *__hidden this, enum _COMPUTER_NAME_FORMAT, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800f85d8`
- `0x1800f8630`

## callees

- `0x180034260`
- `0x1800a7388`
- `0x1800f8438`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f847b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f8517`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f8586`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f847b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f8517`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f8586`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f855b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f855b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f84c0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f84c0`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800f8467`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800f84e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800f8467`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800f84e2`

## string_xrefs

- `0x1800f853e`: `onecore\com\combase\rpcss\olescm\mach.cxx`
- `0x1800f85ad`: `onecore\com\combase\rpcss\olescm\mach.cxx`
- `0x1800f8530`: `CMachineName::SetComputerNameHelper`
- `0x1800f859f`: `CMachineName::SetComputerNameHelper`

## pseudocode

```c

```
