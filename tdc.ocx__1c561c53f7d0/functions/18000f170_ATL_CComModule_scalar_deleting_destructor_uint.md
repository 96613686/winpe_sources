# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x18000f170`
- end: `0x18000f1a9`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `57`
- prototype: `void *__fastcall(ATL::CComModule *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001194`
- `0x18000f170`
- `0x180012bac`

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
0x18000f170  mov     [rsp+arg_0], rbx
0x18000f175  push    rdi
0x18000f176  sub     rsp, 20h
0x18000f17a  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x18000f181  mov     ebx, edx
0x18000f183  mov     [rcx], rax
0x18000f186  mov     rdi, rcx
0x18000f189  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x18000f18e  test    bl, 1
0x18000f191  jz      short loc_18000F19B
0x18000f193  mov     rcx, rdi; Block
0x18000f196  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f19b  mov     rbx, [rsp+28h+arg_0]
0x18000f1a0  mov     rax, rdi
0x18000f1a3  add     rsp, 20h
0x18000f1a7  pop     rdi
0x18000f1a8  retn
```
