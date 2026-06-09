# CProcessEntry::PackageRequest(_EXTENSION_CONTROL_BLOCK *,long,CAsyncPipeOverlapped * *)

- ea: `0x18001e8c8`
- end: `0x18001ec98`
- name: `?PackageRequest@CProcessEntry@@AEAAJPEAU_EXTENSION_CONTROL_BLOCK@@JPEAPEAUCAsyncPipeOverlapped@@@Z`
- size: `976`
- prototype: `__int64 __fastcall(CProcessEntry *this, struct _EXTENSION_CONTROL_BLOCK *, int, struct CAsyncPipeOverlapped **)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18001f150`

## callees

- `0x18000b694`
- `0x1800109b0`
- `0x1800111b0`
- `0x180011390`
- `0x18001d740`
- `0x18001e8c8`
- `0x180020568`
- `0x18004d030`
- `0x1800653ba`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x18001e935`
- `KERNEL32!lstrlenA` at `0x18001e9b6`
- `KERNEL32!lstrlenA` at `0x18001e935`
- `KERNEL32!lstrlenA` at `0x18001e9b6`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001ea8f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001ea8f`

## pseudocode

```c

```
