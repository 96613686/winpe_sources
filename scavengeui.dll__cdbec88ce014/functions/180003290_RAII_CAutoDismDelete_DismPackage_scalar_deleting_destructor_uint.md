# RAII::CAutoDismDelete<_DismPackage *>::`scalar deleting destructor'(uint)

- ea: `0x180003290`
- end: `0x1800032dd`
- name: `??_G?$CAutoDismDelete@PEAU_DismPackage@@@RAII@@UEAAPEAXI@Z`
- size: `77`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180003290`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800032c9`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800032c9`
- `DismApi!DismDelete` at `0x1800032b2`
- `DismApi!DismDelete` at `0x1800032b2`

## pseudocode

```c
_QWORD *__fastcall RAII::CAutoDismDelete<_DismPackage *>::`scalar deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &RAII::CAutoDismDelete<_DismPackage *>::`vftable';
  if ( a1[1] )
  {
    DismDelete();
    a1[1] = 0;
  }
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180003290  mov     [rsp+arg_0], rbx
0x180003295  push    rdi
0x180003296  sub     rsp, 20h
0x18000329a  lea     rax, ??_7?$CAutoDismDelete@PEAU_DismPackage@@@RAII@@6B@; const RAII::CAutoDismDelete<_DismPackage *>::`vftable'
0x1800032a1  mov     rbx, rcx
0x1800032a4  mov     [rcx], rax
0x1800032a7  mov     edi, edx
0x1800032a9  mov     rcx, [rcx+8]
0x1800032ad  test    rcx, rcx
0x1800032b0  jz      short loc_1800032C0
0x1800032b2  call    cs:__imp_DismDelete
0x1800032b8  mov     qword ptr [rbx+8], 0
0x1800032c0  test    dil, 1
0x1800032c4  jz      short loc_1800032CF
0x1800032c6  mov     rcx, rbx
0x1800032c9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800032cf  mov     rax, rbx
0x1800032d2  mov     rbx, [rsp+28h+arg_0]
0x1800032d7  add     rsp, 20h
0x1800032db  pop     rdi
0x1800032dc  retn
```
