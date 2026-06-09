# cxxbridge1$ScanLookAsideList_Allocate

- ea: `0x140017738`
- end: `0x14001774e`
- name: `cxxbridge1$ScanLookAsideList_Allocate`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x14000fdb0`

## import_xrefs

- `win32kbase!ScanLookAsideList_Allocate` at `0x14001773c`
- `win32kbase!ScanLookAsideList_Allocate` at `0x14001773c`

## pseudocode

```c
void *cxxbridge1_ScanLookAsideList_Allocate()
{
  return ScanLookAsideList_Allocate();
}

```

## disassembly

```asm
0x140017738  sub     rsp, 28h
0x14001773c  call    cs:__imp_?ScanLookAsideList_Allocate@@YAPEAXXZ; ScanLookAsideList_Allocate(void)
0x140017743  nop     dword ptr [rax+rax+00h]
0x140017748  add     rsp, 28h
0x14001774c  retn
```
