# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x1800059d0`
- end: `0x180005a0e`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `62`
- prototype: `void *__fastcall(ATL::CComModule *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001fc0`
- `0x180002594`
- `0x1800059d0`

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
0x1800059d0  mov     [rsp+arg_0], rbx
0x1800059d5  push    rdi
0x1800059d6  sub     rsp, 20h
0x1800059da  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x1800059e1  mov     ebx, edx
0x1800059e3  mov     [rcx], rax
0x1800059e6  mov     rdi, rcx
0x1800059e9  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x1800059ee  test    bl, 1
0x1800059f1  jz      short loc_180005A00
0x1800059f3  mov     edx, 50h ; 'P'; unsigned __int64
0x1800059f8  mov     rcx, rdi; void *
0x1800059fb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005a00  mov     rbx, [rsp+28h+arg_0]
0x180005a05  mov     rax, rdi
0x180005a08  add     rsp, 20h
0x180005a0c  pop     rdi
0x180005a0d  retn
```
