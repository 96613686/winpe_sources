# ATL::CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>::~CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>(void)

- ea: `0x1800026c4`
- end: `0x180002728`
- name: `??1?$CComEnumImpl@UIEnumConnectionPoints@@$1?_GUID_b196b285_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@@ATL@@UEAA@XZ`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002bc0`

## callees

- `0x1800011a0`
- `0x1800026c4`
- `0x180015010`

## pseudocode

```c
void __fastcall ATL::CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>::~CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>(
        __int64 a1)
{
  _QWORD *i; // rdi
  __int64 v3; // rcx

  if ( (*(_BYTE *)(a1 + 40) & 2) != 0 )
  {
    for ( i = *(_QWORD **)(a1 + 16); i != *(_QWORD **)(a1 + 24); ++i )
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
0x1800026c4  mov     [rsp+arg_0], rbx
0x1800026c9  push    rdi
0x1800026ca  sub     rsp, 20h
0x1800026ce  test    byte ptr [rcx+28h], 2
0x1800026d2  mov     rbx, rcx
0x1800026d5  jz      short loc_180002708
0x1800026d7  mov     rdi, [rcx+10h]
0x1800026db  cmp     rdi, [rcx+18h]
0x1800026df  jz      short loc_1800026FF
0x1800026e1  mov     rcx, [rdi]
0x1800026e4  test    rcx, rcx
0x1800026e7  jz      short loc_1800026F5
0x1800026e9  mov     rax, [rcx]
0x1800026ec  mov     rax, [rax+10h]
0x1800026f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026f5  add     rdi, 8
0x1800026f9  cmp     rdi, [rbx+18h]
0x1800026fd  jnz     short loc_1800026E1
0x1800026ff  mov     rcx, [rbx+10h]; Block
0x180002703  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180002708  mov     rcx, [rbx+8]
0x18000270c  test    rcx, rcx
0x18000270f  jz      short loc_18000271D
0x180002711  mov     rax, [rcx]
0x180002714  mov     rax, [rax+10h]
0x180002718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000271d  mov     rbx, [rsp+28h+arg_0]
0x180002722  add     rsp, 20h
0x180002726  pop     rdi
0x180002727  retn
```
