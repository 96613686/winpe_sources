# ATL::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::`vector deleting destructor'(uint)

- ea: `0x180002c20`
- end: `0x180002c76`
- name: `??_E?$CComObject@V?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@UEAAPEAXI@Z`
- size: `86`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180001194`
- `0x180002730`
- `0x180002c20`
- `0x180015010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::`vector deleting destructor'(
        _DWORD *Block,
        char a2)
{
  Block[12] = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::~CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180002c20  mov     [rsp+arg_0], rbx
0x180002c25  push    rdi
0x180002c26  sub     rsp, 20h
0x180002c2a  mov     dword ptr [rcx+30h], 0C0000001h
0x180002c31  lea     rax, ??_7?$CComObject@V?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@6B@; const ATL::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::`vftable'
0x180002c38  mov     [rcx], rax
0x180002c3b  mov     rdi, rcx
0x180002c3e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002c45  mov     ebx, edx
0x180002c47  mov     rax, [rcx]
0x180002c4a  mov     rax, [rax+10h]
0x180002c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c53  mov     rcx, rdi
0x180002c56  call    ??1?$CComEnumImpl@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@@ATL@@UEAA@XZ; ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::~CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>(void)
0x180002c5b  test    bl, 1
0x180002c5e  jz      short loc_180002C68
0x180002c60  mov     rcx, rdi; Block
0x180002c63  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002c68  mov     rbx, [rsp+28h+arg_0]
0x180002c6d  mov     rax, rdi
0x180002c70  add     rsp, 20h
0x180002c74  pop     rdi
0x180002c75  retn
```
