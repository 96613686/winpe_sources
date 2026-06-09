# ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::Init(tagCONNECTDATA *,tagCONNECTDATA *,IUnknown *,ATL::CComEnumFlags)

- ea: `0x180006bb0`
- end: `0x180006c17`
- name: `?Init@?$CComEnumImpl@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@@ATL@@QEAAJPEAUtagCONNECTDATA@@0PEAUIUnknown@@W4CComEnumFlags@2@@Z`
- size: `103`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000415c`
- `0x180005240`

## callees

- `0x180006bb0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::Init(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  __int64 v7; // rcx

  *(_QWORD *)(a1 + 16) = a2;
  *(_QWORD *)(a1 + 24) = a3;
  if ( *(_QWORD *)(a1 + 8) != a4 )
  {
    if ( a4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a4 + 8LL))(a4);
    v7 = *(_QWORD *)(a1 + 8);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *(_QWORD *)(a1 + 8) = a4;
  }
  *(_QWORD *)(a1 + 32) = *(_QWORD *)(a1 + 16);
  *(_DWORD *)(a1 + 40) = a5;
  return 0;
}

```

## disassembly

```asm
0x180006bb0  mov     [rsp+arg_0], rbx
0x180006bb5  push    rdi
0x180006bb6  sub     rsp, 20h
0x180006bba  mov     [rcx+10h], rdx
0x180006bbe  mov     rdi, r9
0x180006bc1  mov     [rcx+18h], r8
0x180006bc5  mov     rbx, rcx
0x180006bc8  cmp     [rcx+8], r9
0x180006bcc  jz      short loc_180006BFB
0x180006bce  test    r9, r9
0x180006bd1  jz      short loc_180006BE2
0x180006bd3  mov     rax, [r9]
0x180006bd6  mov     rcx, r9
0x180006bd9  mov     rax, [rax+8]
0x180006bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006be2  mov     rcx, [rbx+8]
0x180006be6  test    rcx, rcx
0x180006be9  jz      short loc_180006BF7
0x180006beb  mov     rax, [rcx]
0x180006bee  mov     rax, [rax+10h]
0x180006bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bf7  mov     [rbx+8], rdi
0x180006bfb  mov     rax, [rbx+10h]
0x180006bff  mov     [rbx+20h], rax
0x180006c03  mov     eax, [rsp+28h+arg_20]
0x180006c07  mov     [rbx+28h], eax
0x180006c0a  xor     eax, eax
0x180006c0c  mov     rbx, [rsp+28h+arg_0]
0x180006c11  add     rsp, 20h
0x180006c15  pop     rdi
0x180006c16  retn
```
