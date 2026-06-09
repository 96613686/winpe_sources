# _RNvNtCsdwtLm5uWta6_10gdi_region3ffi22ScanLookAsideList_Free

- ea: `0x14000fda0`
- end: `0x14000fda5`
- name: `_RNvNtCsdwtLm5uWta6_10gdi_region3ffi22ScanLookAsideList_Free`
- size: `5`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140004cc0`
- `0x140004e40`
- `0x14000acb0`
- `0x140014dd0`
- `0x1400153c0`
- `0x140015ac0`
- `0x140018ab0`
- `0x1400193b0`

## callees

- `0x140017754`

## pseudocode

```c
// attributes: thunk
void __fastcall RNvNtCsdwtLm5uWta6_10gdi_region3ffi22ScanLookAsideList_Free(void *a1)
{
  cxxbridge1_ScanLookAsideList_Free(a1);
}

```

## disassembly

```asm
0x14000fda0  jmp     cxxbridge1$ScanLookAsideList_Free
```
