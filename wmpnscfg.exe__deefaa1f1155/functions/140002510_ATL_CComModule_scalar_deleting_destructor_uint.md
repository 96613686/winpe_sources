# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x140002510`
- end: `0x14000254e`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `62`
- prototype: `void *__fastcall(ATL::CComModule *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400011b0`
- `0x140002510`
- `0x140004c18`

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
0x140002510  mov     [rsp+arg_0], rbx
0x140002515  push    rdi
0x140002516  sub     rsp, 20h
0x14000251a  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x140002521  mov     ebx, edx
0x140002523  mov     [rcx], rax
0x140002526  mov     rdi, rcx
0x140002529  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x14000252e  test    bl, 1
0x140002531  jz      short loc_140002540
0x140002533  mov     edx, 50h ; 'P'
0x140002538  mov     rcx, rdi; Block
0x14000253b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140002540  mov     rbx, [rsp+28h+arg_0]
0x140002545  mov     rax, rdi
0x140002548  add     rsp, 20h
0x14000254c  pop     rdi
0x14000254d  retn
```
