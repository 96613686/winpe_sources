# _RNvNtCsdwtLm5uWta6_10gdi_region3ffi26ScanLookAsideList_Allocate

- ea: `0x14000fdb0`
- end: `0x14000fdb5`
- name: `_RNvNtCsdwtLm5uWta6_10gdi_region3ffi26ScanLookAsideList_Allocate`
- size: `5`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000bc20`
- `0x14000c3d0`
- `0x140018ab0`
- `0x1400193b0`

## callees

- `0x140017738`

## pseudocode

```c
// attributes: thunk
void *__fastcall RNvNtCsdwtLm5uWta6_10gdi_region3ffi26ScanLookAsideList_Allocate()
{
  return cxxbridge1_ScanLookAsideList_Allocate();
}

```

## disassembly

```asm
0x14000fdb0  jmp     cxxbridge1$ScanLookAsideList_Allocate
```
