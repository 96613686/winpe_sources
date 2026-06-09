# CreateConsole(void)

- ea: `0x1400e4cd4`
- end: `0x1400e4dc3`
- name: `?CreateConsole@@YA?AUConsoleDriverHandles@@XZ`
- size: `239`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400e0b10`

## callees

- `0x140044adc`
- `0x1400e4cd4`
- `0x1400e8a9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400e4d4d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400e4d4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e4d3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e4d3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e4d45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e4d45`

## string_xrefs

- `0x1400e4d97`: `onecore\vm\compute\service\cexec\lib\consoletostream.cpp`
- `0x1400e4db1`: `onecore\vm\compute\service\cexec\lib\consoletostream.cpp`

## pseudocode

```c

```
