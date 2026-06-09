# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x140002110`
- end: `0x14000214e`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `62`
- prototype: `ATL::CComModule *__fastcall(ATL::CComModule *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001110`
- `0x140002110`
- `0x140005294`

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
0x140002110  mov     [rsp+arg_0], rbx
0x140002115  push    rdi
0x140002116  sub     rsp, 20h
0x14000211a  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x140002121  mov     ebx, edx
0x140002123  mov     [rcx], rax
0x140002126  mov     rdi, rcx
0x140002129  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x14000212e  test    bl, 1
0x140002131  jz      short loc_140002140
0x140002133  mov     edx, 50h ; 'P'
0x140002138  mov     rcx, rdi; Block
0x14000213b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140002140  mov     rbx, [rsp+28h+arg_0]
0x140002145  mov     rax, rdi
0x140002148  add     rsp, 20h
0x14000214c  pop     rdi
0x14000214d  retn
```
