# ParseUncPath

- ea: `0x1800401d0`
- end: `0x180040374`
- name: `ParseUncPath`
- size: `420`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18003f704`
- `0x18003f958`

## callees

- `0x180010508`
- `0x1800401d0`
- `0x1800607d4`
- `0x180060cd6`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180040332`
- `KERNEL32!HeapFree` at `0x180040332`
- `KERNEL32!GetProcessHeap` at `0x18004031e`
- `KERNEL32!GetProcessHeap` at `0x18004031e`
- `ntdll!RtlAllocateHeap` at `0x1800402ca`
- `ntdll!RtlAllocateHeap` at `0x1800402ca`

## pseudocode

```c

```
