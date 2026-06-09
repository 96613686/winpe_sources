# ECNcDestroyHandler(tagWND *,tagED *)

- ea: `0x180079a1c`
- end: `0x180079b30`
- name: `?ECNcDestroyHandler@@YAXPEAUtagWND@@PEAUtagED@@@Z`
- size: `276`
- prototype: `void(struct tagWND *, struct tagED *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180033af0`

## callees

- `0x180038560`
- `0x180057fa0`
- `0x180079a1c`

## import_xrefs

- `win32u!NtUserSetWindowFNID` at `0x180079ad4`
- `win32u!NtUserSetWindowFNID` at `0x180079ad4`
- `ntdll!RtlFreeHeap` at `0x180079a65`
- `ntdll!RtlFreeHeap` at `0x180079a80`
- `ntdll!RtlFreeHeap` at `0x180079a9b`
- `ntdll!RtlFreeHeap` at `0x180079a65`
- `ntdll!RtlFreeHeap` at `0x180079a80`
- `ntdll!RtlFreeHeap` at `0x180079a9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079a38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079a38`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180079a4a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180079a4a`
- `GDI32!DeleteObject` at `0x180079ab7`
- `GDI32!DeleteObject` at `0x180079ab7`

## pseudocode

```c

```
