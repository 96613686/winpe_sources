# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x180007230`
- end: `0x180007269`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `57`
- prototype: `ATL::CComModule *__fastcall(ATL::CComModule *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800012d4`
- `0x180007230`
- `0x180009968`

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
0x180007230  mov     [rsp+arg_0], rbx
0x180007235  push    rdi
0x180007236  sub     rsp, 20h
0x18000723a  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x180007241  mov     ebx, edx
0x180007243  mov     [rcx], rax
0x180007246  mov     rdi, rcx
0x180007249  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x18000724e  test    bl, 1
0x180007251  jz      short loc_18000725B
0x180007253  mov     rcx, rdi; Block
0x180007256  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000725b  mov     rbx, [rsp+28h+arg_0]
0x180007260  mov     rax, rdi
0x180007263  add     rsp, 20h
0x180007267  pop     rdi
0x180007268  retn
```
