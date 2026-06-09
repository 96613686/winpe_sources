# ATL::CComObject<CContainer>::`scalar deleting destructor'(uint)

- ea: `0x1400020a0`
- end: `0x140002108`
- name: `??_G?$CComObject@VCContainer@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `char *__fastcall(char *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001110`
- `0x1400020a0`
- `0x140007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400020e1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400020e1`

## pseudocode

```c
char *__fastcall ATL::CComObject<CContainer>::`scalar deleting destructor'(char *Block, char a2)
{
  *((_DWORD *)Block + 2) = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CContainer>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( Block[56] )
  {
    Block[56] = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 16));
  }
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1400020a0  mov     [rsp+arg_0], rbx
0x1400020a5  push    rdi
0x1400020a6  sub     rsp, 20h
0x1400020aa  mov     dword ptr [rcx+8], 0C0000001h
0x1400020b1  lea     rax, ??_7?$CComObject@VCContainer@@@ATL@@6B@; const ATL::CComObject<CContainer>::`vftable'
0x1400020b8  mov     [rcx], rax
0x1400020bb  mov     rbx, rcx
0x1400020be  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1400020c5  mov     edi, edx
0x1400020c7  mov     rax, [rcx]
0x1400020ca  mov     rax, [rax+10h]
0x1400020ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400020d3  lea     rcx, [rbx+10h]; lpCriticalSection
0x1400020d7  cmp     byte ptr [rcx+28h], 0
0x1400020db  jz      short loc_1400020E7
0x1400020dd  mov     byte ptr [rcx+28h], 0
0x1400020e1  call    cs:__imp_DeleteCriticalSection
0x1400020e7  test    dil, 1
0x1400020eb  jz      short loc_1400020FA
0x1400020ed  mov     edx, 40h ; '@'
0x1400020f2  mov     rcx, rbx; Block
0x1400020f5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400020fa  mov     rax, rbx
0x1400020fd  mov     rbx, [rsp+28h+arg_0]
0x140002102  add     rsp, 20h
0x140002106  pop     rdi
0x140002107  retn
```
