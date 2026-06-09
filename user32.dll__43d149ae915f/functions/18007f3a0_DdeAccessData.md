# DdeAccessData

- ea: `0x18007f3a0`
- end: `0x18007f424`
- name: `DdeAccessData`
- size: `132`
- prototype: `LPBYTE __stdcall(HDDEDATA hData, LPDWORD pcbDataSize)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180045fc0`

## callees

- `0x1800482c4`
- `0x18004888c`
- `0x18007f3a0`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x18007f3b9`
- `ntdll!RtlEnterCriticalSection` at `0x18007f3b9`
- `ntdll!RtlLeaveCriticalSection` at `0x18007f411`
- `ntdll!RtlLeaveCriticalSection` at `0x18007f411`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x18007f3f1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x18007f3f1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18007f3ff`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18007f3ff`

## pseudocode

```c

```
