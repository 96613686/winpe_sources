# ATL::CComObject<CSrDrvWuHelper>::`vector deleting destructor'(uint)

- ea: `0x1800071d0`
- end: `0x18000721e`
- name: `??_E?$CComObject@VCSrDrvWuHelper@@@ATL@@UEAAPEAXI@Z`
- size: `78`
- prototype: `_DWORD *__fastcall(_DWORD *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800012d4`
- `0x1800071d0`
- `0x180016010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<CSrDrvWuHelper>::`vector deleting destructor'(_DWORD *Block, char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CSrDrvWuHelper>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800071d0  mov     [rsp+arg_0], rbx
0x1800071d5  push    rdi
0x1800071d6  sub     rsp, 20h
0x1800071da  mov     dword ptr [rcx+8], 0C0000001h
0x1800071e1  lea     rax, ??_7?$CComObject@VCSrDrvWuHelper@@@ATL@@6B@; const ATL::CComObject<CSrDrvWuHelper>::`vftable'
0x1800071e8  mov     [rcx], rax
0x1800071eb  mov     rdi, rcx
0x1800071ee  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800071f5  mov     ebx, edx
0x1800071f7  mov     rax, [rcx]
0x1800071fa  mov     rax, [rax+10h]
0x1800071fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007203  test    bl, 1
0x180007206  jz      short loc_180007210
0x180007208  mov     rcx, rdi; Block
0x18000720b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007210  mov     rbx, [rsp+28h+arg_0]
0x180007215  mov     rax, rdi
0x180007218  add     rsp, 20h
0x18000721c  pop     rdi
0x18000721d  retn
```
