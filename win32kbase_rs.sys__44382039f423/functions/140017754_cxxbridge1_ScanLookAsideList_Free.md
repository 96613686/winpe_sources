# cxxbridge1$ScanLookAsideList_Free

- ea: `0x140017754`
- end: `0x14001776a`
- name: `cxxbridge1$ScanLookAsideList_Free`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x14000fda0`

## import_xrefs

- `win32kbase!ScanLookAsideList_Free` at `0x140017758`
- `win32kbase!ScanLookAsideList_Free` at `0x140017758`

## pseudocode

```c
void __fastcall cxxbridge1_ScanLookAsideList_Free(void *a1)
{
  ScanLookAsideList_Free(a1);
}

```

## disassembly

```asm
0x140017754  sub     rsp, 28h
0x140017758  call    cs:__imp_?ScanLookAsideList_Free@@YAXPEAX@Z; ScanLookAsideList_Free(void *)
0x14001775f  nop     dword ptr [rax+rax+00h]
0x140017764  add     rsp, 28h
0x140017768  retn
```
