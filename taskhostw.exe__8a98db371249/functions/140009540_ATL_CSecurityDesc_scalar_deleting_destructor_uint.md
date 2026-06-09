# ATL::CSecurityDesc::`scalar deleting destructor'(uint)

- ea: `0x140009540`
- end: `0x14000957a`
- name: `??_GCSecurityDesc@ATL@@UEAAPEAXI@Z`
- size: `58`
- prototype: `ATL::CSecurityDesc *__fastcall(ATL::CSecurityDesc *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140002ce0`
- `0x140009540`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140009566`
- `msvcrt!??3@YAXPEAX@Z` at `0x140009566`

## pseudocode

```c
ATL::CSecurityDesc *__fastcall ATL::CSecurityDesc::`scalar deleting destructor'(ATL::CSecurityDesc *this, char a2)
{
  *(_QWORD *)this = &ATL::CSecurityDesc::`vftable';
  ATL::CSecurityDesc::Clear(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140009540  mov     [rsp+arg_0], rbx
0x140009545  push    rdi
0x140009546  sub     rsp, 20h
0x14000954a  lea     rax, ??_7CSecurityDesc@ATL@@6B@; const ATL::CSecurityDesc::`vftable'
0x140009551  mov     ebx, edx
0x140009553  mov     [rcx], rax
0x140009556  mov     rdi, rcx
0x140009559  call    ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
0x14000955e  test    bl, 1
0x140009561  jz      short loc_14000956C
0x140009563  mov     rcx, rdi
0x140009566  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000956c  mov     rbx, [rsp+28h+arg_0]
0x140009571  mov     rax, rdi
0x140009574  add     rsp, 20h
0x140009578  pop     rdi
0x140009579  retn
```
