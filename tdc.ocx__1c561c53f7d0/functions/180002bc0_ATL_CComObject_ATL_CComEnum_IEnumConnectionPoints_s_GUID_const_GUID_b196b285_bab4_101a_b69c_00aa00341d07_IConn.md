# ATL::CComObject<ATL::CComEnum<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>>::`scalar deleting destructor'(uint)

- ea: `0x180002bc0`
- end: `0x180002c16`
- name: `??_G?$CComObject@V?$CComEnum@UIEnumConnectionPoints@@$1?_GUID_b196b285_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@UEAAPEAXI@Z`
- size: `86`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180001194`
- `0x1800026c4`
- `0x180002bc0`
- `0x180015010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<ATL::CComEnum<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>>::`scalar deleting destructor'(
        _DWORD *Block,
        char a2)
{
  Block[12] = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<ATL::CComEnum<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  ATL::CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>::~CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180002bc0  mov     [rsp+arg_0], rbx
0x180002bc5  push    rdi
0x180002bc6  sub     rsp, 20h
0x180002bca  mov     dword ptr [rcx+30h], 0C0000001h
0x180002bd1  lea     rax, ??_7?$CComObject@V?$CComEnum@UIEnumConnectionPoints@@$1?_GUID_b196b285_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@6B@; const ATL::CComObject<ATL::CComEnum<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>>::`vftable'
0x180002bd8  mov     [rcx], rax
0x180002bdb  mov     rdi, rcx
0x180002bde  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002be5  mov     ebx, edx
0x180002be7  mov     rax, [rcx]
0x180002bea  mov     rax, [rax+10h]
0x180002bee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bf3  mov     rcx, rdi
0x180002bf6  call    ??1?$CComEnumImpl@UIEnumConnectionPoints@@$1?_GUID_b196b285_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@@ATL@@UEAA@XZ; ATL::CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>::~CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>(void)
0x180002bfb  test    bl, 1
0x180002bfe  jz      short loc_180002C08
0x180002c00  mov     rcx, rdi; Block
0x180002c03  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002c08  mov     rbx, [rsp+28h+arg_0]
0x180002c0d  mov     rax, rdi
0x180002c10  add     rsp, 20h
0x180002c14  pop     rdi
0x180002c15  retn
```
