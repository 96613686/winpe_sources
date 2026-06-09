# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x180002fc0`
- end: `0x180002ffa`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `58`
- prototype: `void *__fastcall(ATL::CComModule *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002fc0`
- `0x180005f7c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002fe6`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002fe6`

## pseudocode

```c
ATL::CComModule *__fastcall ATL::CComModule::`scalar deleting destructor'(ATL::CComModule *this, char a2)
{
  *(_QWORD *)this = &ATL::CComModule::`vftable';
  ATL::CAtlModule::Term(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002fc0  mov     [rsp+arg_0], rbx
0x180002fc5  push    rdi
0x180002fc6  sub     rsp, 20h
0x180002fca  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x180002fd1  mov     ebx, edx
0x180002fd3  mov     [rcx], rax
0x180002fd6  mov     rdi, rcx
0x180002fd9  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x180002fde  test    bl, 1
0x180002fe1  jz      short loc_180002FEC
0x180002fe3  mov     rcx, rdi
0x180002fe6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002fec  mov     rbx, [rsp+28h+arg_0]
0x180002ff1  mov     rax, rdi
0x180002ff4  add     rsp, 20h
0x180002ff8  pop     rdi
0x180002ff9  retn
```
