# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x180002d50`
- end: `0x180002d8a`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `58`
- prototype: `void *__fastcall(ATL::CComModule *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002d50`
- `0x180005418`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002d76`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002d76`

## pseudocode

```c
ATL::CComModule *__fastcall ATL::CComModule::`scalar deleting destructor'(ATL::CComModule *this, unsigned int a2)
{
  char v2; // bl

  v2 = a2;
  *(_QWORD *)this = &ATL::CComModule::`vftable';
  ATL::CAtlModule::Term(this, a2);
  if ( (v2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002d50  mov     [rsp+arg_0], rbx
0x180002d55  push    rdi
0x180002d56  sub     rsp, 20h
0x180002d5a  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x180002d61  mov     ebx, edx
0x180002d63  mov     [rcx], rax
0x180002d66  mov     rdi, rcx
0x180002d69  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x180002d6e  test    bl, 1
0x180002d71  jz      short loc_180002D7C
0x180002d73  mov     rcx, rdi
0x180002d76  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002d7c  mov     rbx, [rsp+28h+arg_0]
0x180002d81  mov     rax, rdi
0x180002d84  add     rsp, 20h
0x180002d88  pop     rdi
0x180002d89  retn
```
