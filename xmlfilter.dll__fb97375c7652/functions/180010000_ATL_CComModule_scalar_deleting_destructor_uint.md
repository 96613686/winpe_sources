# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x180010000`
- end: `0x18001003e`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `62`
- prototype: `ATL::CComModule *__fastcall(ATL::CComModule *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000213c`
- `0x180010000`
- `0x180013170`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x180010000  mov     [rsp+arg_0], rbx
0x180010005  push    rdi
0x180010006  sub     rsp, 20h
0x18001000a  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x180010011  mov     ebx, edx
0x180010013  mov     [rcx], rax
0x180010016  mov     rdi, rcx
0x180010019  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x18001001e  test    bl, 1
0x180010021  jz      short loc_180010030
0x180010023  mov     edx, 50h ; 'P'
0x180010028  mov     rcx, rdi; Block
0x18001002b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010030  mov     rbx, [rsp+28h+arg_0]
0x180010035  mov     rax, rdi
0x180010038  add     rsp, 20h
0x18001003c  pop     rdi
0x18001003d  retn
```
