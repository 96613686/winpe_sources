# CIISModuleFactory::Terminate(void)

- ea: `0x180002540`
- end: `0x180002572`
- name: `?Terminate@CIISModuleFactory@@UEAAXXZ`
- size: `50`
- prototype: `void __fastcall(CIISModuleFactory *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180002540`

## import_xrefs

- `iisutil!PuDeleteDebugPrintsObject` at `0x180002560`
- `iisutil!PuDeleteDebugPrintsObject` at `0x180002560`

## pseudocode

```c
void __fastcall CIISModuleFactory::Terminate(CIISModuleFactory *this)
{
  if ( this )
  {
    *((_QWORD *)this + 1) = &CHttpModule::`vftable';
    operator delete(this);
  }
  g_pDebug = PuDeleteDebugPrintsObject(g_pDebug);
}

```

## disassembly

```asm
0x180002540  sub     rsp, 28h
0x180002544  test    rcx, rcx
0x180002547  jz      short loc_180002559
0x180002549  lea     rax, ??_7CHttpModule@@6B@; const CHttpModule::`vftable'
0x180002550  mov     [rcx+8], rax
0x180002554  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002559  mov     rcx, cs:g_pDebug
0x180002560  call    cs:__imp_PuDeleteDebugPrintsObject
0x180002566  mov     cs:g_pDebug, rax
0x18000256d  add     rsp, 28h
0x180002571  retn
```
