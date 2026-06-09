# ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::~CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>(void)

- ea: `0x180002730`
- end: `0x180002794`
- name: `??1?$CComEnumImpl@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@@ATL@@UEAA@XZ`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002c20`

## callees

- `0x1800011a0`
- `0x180002730`
- `0x180015010`

## pseudocode

```c
void __fastcall ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::~CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>(
        __int64 a1)
{
  _QWORD *i; // rdi
  __int64 v3; // rcx

  if ( (*(_BYTE *)(a1 + 40) & 2) != 0 )
  {
    for ( i = *(_QWORD **)(a1 + 16); i != *(_QWORD **)(a1 + 24); i += 2 )
    {
      if ( *i )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*i + 16LL))(*i);
    }
    operator delete[](*(void **)(a1 + 16));
  }
  v3 = *(_QWORD *)(a1 + 8);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
}

```

## disassembly

```asm
0x180002730  mov     [rsp+arg_0], rbx
0x180002735  push    rdi
0x180002736  sub     rsp, 20h
0x18000273a  test    byte ptr [rcx+28h], 2
0x18000273e  mov     rbx, rcx
0x180002741  jz      short loc_180002774
0x180002743  mov     rdi, [rcx+10h]
0x180002747  cmp     rdi, [rcx+18h]
0x18000274b  jz      short loc_18000276B
0x18000274d  mov     rcx, [rdi]
0x180002750  test    rcx, rcx
0x180002753  jz      short loc_180002761
0x180002755  mov     rax, [rcx]
0x180002758  mov     rax, [rax+10h]
0x18000275c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002761  add     rdi, 10h
0x180002765  cmp     rdi, [rbx+18h]
0x180002769  jnz     short loc_18000274D
0x18000276b  mov     rcx, [rbx+10h]; Block
0x18000276f  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180002774  mov     rcx, [rbx+8]
0x180002778  test    rcx, rcx
0x18000277b  jz      short loc_180002789
0x18000277d  mov     rax, [rcx]
0x180002780  mov     rax, [rax+10h]
0x180002784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002789  mov     rbx, [rsp+28h+arg_0]
0x18000278e  add     rsp, 20h
0x180002792  pop     rdi
0x180002793  retn
```
