# CMachineName::SetComputerNameHelper(_COMPUTER_NAME_FORMAT,ushort * *)

- ea: `0x1800f07e8`
- end: `0x1800f0954`
- name: `?SetComputerNameHelper@CMachineName@@AEAAXW4_COMPUTER_NAME_FORMAT@@PEAPEAG@Z`
- size: `364`
- prototype: `void(CMachineName *__hidden this, enum _COMPUTER_NAME_FORMAT, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800f095c`
- `0x1800f09ac`

## callees

- `0x180034540`
- `0x1800a1e98`
- `0x1800f07e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f08af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0912`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f08af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0912`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f08ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f08ed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f0864`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f0864`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800f0817`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800f0880`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800f0817`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800f0880`

## string_xrefs

- `0x1800f08d0`: `onecore\com\combase\rpcss\olescm\mach.cxx`
- `0x1800f0933`: `onecore\com\combase\rpcss\olescm\mach.cxx`
- `0x1800f08c2`: `CMachineName::SetComputerNameHelper`
- `0x1800f0925`: `CMachineName::SetComputerNameHelper`

## pseudocode

```c

```
