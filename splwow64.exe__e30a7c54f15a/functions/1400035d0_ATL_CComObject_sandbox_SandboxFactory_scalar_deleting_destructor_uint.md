# ATL::CComObject<sandbox::SandboxFactory>::`scalar deleting destructor'(uint)

- ea: `0x1400035d0`
- end: `0x14000362d`
- name: `??_G?$CComObject@VSandboxFactory@sandbox@@@ATL@@UEAAPEAXI@Z`
- size: `93`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001b90`
- `0x1400035d0`
- `0x140016010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<sandbox::SandboxFactory>::`scalar deleting destructor'(_DWORD *Block, char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<sandbox::SandboxFactory>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  *(_QWORD *)Block = &sandbox::SandboxFactory::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1400035d0  mov     [rsp+arg_0], rbx
0x1400035d5  push    rdi
0x1400035d6  sub     rsp, 20h
0x1400035da  mov     dword ptr [rcx+8], 0C0000001h
0x1400035e1  lea     rax, ??_7?$CComObject@VSandboxFactory@sandbox@@@ATL@@6B@; const ATL::CComObject<sandbox::SandboxFactory>::`vftable'
0x1400035e8  mov     [rcx], rax
0x1400035eb  mov     rdi, rcx
0x1400035ee  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1400035f5  mov     ebx, edx
0x1400035f7  mov     rax, [rcx]
0x1400035fa  mov     rax, [rax+10h]
0x1400035fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003603  lea     rax, ??_7SandboxFactory@sandbox@@6B@; const sandbox::SandboxFactory::`vftable'
0x14000360a  mov     [rdi], rax
0x14000360d  test    bl, 1
0x140003610  jz      short loc_14000361F
0x140003612  mov     edx, 20h ; ' '
0x140003617  mov     rcx, rdi; Block
0x14000361a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000361f  mov     rbx, [rsp+28h+arg_0]
0x140003624  mov     rax, rdi
0x140003627  add     rsp, 20h
0x14000362b  pop     rdi
0x14000362c  retn
```
