# WimPathDupeIfNecessary

- ea: `0x1800110a0`
- end: `0x18001123b`
- name: `WimPathDupeIfNecessary`
- size: `411`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180010efc`
- `0x180011244`

## callees

- `0x180010508`
- `0x1800110a0`
- `0x18003f074`

## import_xrefs

- `msvcrt!wcsncmp` at `0x1800110ee`
- `msvcrt!wcsncmp` at `0x1800110ee`
- `KERNEL32!SetLastError` at `0x1800110cb`
- `KERNEL32!SetLastError` at `0x1800110cb`
- `ntdll!RtlFreeHeap` at `0x1800111fb`
- `ntdll!RtlFreeHeap` at `0x1800111fb`
- `ntdll!RtlAllocateHeap` at `0x18001115c`
- `ntdll!RtlAllocateHeap` at `0x18001115c`

## pseudocode

```c

```
