# MprInfoBlockAdd

- ea: `0x180075c80`
- end: `0x180075ee4`
- name: `MprInfoBlockAdd`
- size: `612`
- prototype: `DWORD __stdcall(LPVOID lpHeader, DWORD dwInfoType, DWORD dwItemSize, DWORD dwItemCount, LPBYTE lpItemData, LPVOID *lplpNewHeader)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180063be4`
- `0x180063de4`
- `0x180064270`

## callees

- `0x180075c5c`
- `0x180075c80`
- `0x180076010`
- `0x180077552`
- `0x18007755e`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180075db3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180075db3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180075da5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180075da5`

## pseudocode

```c

```
