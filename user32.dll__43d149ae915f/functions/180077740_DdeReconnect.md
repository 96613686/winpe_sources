# DdeReconnect

- ea: `0x180077740`
- end: `0x1800778d2`
- name: `DdeReconnect`
- size: `402`
- prototype: `HCONV __stdcall(HCONV hConv)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x1800481f4`
- `0x1800482c4`
- `0x180048320`
- `0x1800483d4`
- `0x18004888c`
- `0x18006639c`
- `0x180076dd0`
- `0x180077740`
- `0x18008fbfc`
- `0x180096e00`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180077780`
- `ntdll!RtlEnterCriticalSection` at `0x180077780`
- `ntdll!RtlLeaveCriticalSection` at `0x1800778a7`
- `ntdll!RtlLeaveCriticalSection` at `0x1800778a7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007783a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007783a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180077891`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180077891`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180077888`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180077888`

## pseudocode

```c

```
