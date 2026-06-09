# ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::Skip(ulong)

- ea: `0x180009328`
- end: `0x18000935a`
- name: `?Skip@?$CComEnumImpl@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@@ATL@@UEAAJK@Z`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800092e0`

## callees

- `0x180009328`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::Skip(
        __int64 a1,
        unsigned int a2)
{
  __int64 v4; // rax
  unsigned int v5; // ecx
  __int64 v6; // rax

  if ( !a2 )
    return 2147942487LL;
  v4 = *(_QWORD *)(a1 + 24) - *(_QWORD *)(a1 + 32);
  v5 = a2;
  v6 = v4 >> 4;
  if ( a2 > (unsigned int)v6 )
    v5 = v6;
  *(_QWORD *)(a1 + 32) += 16LL * v5;
  return a2 != v5;
}

```

## disassembly

```asm
0x180009328  mov     r8, rcx
0x18000932b  test    edx, edx
0x18000932d  jnz     short loc_180009335
0x18000932f  mov     eax, 80070057h
0x180009334  retn
0x180009335  mov     rax, [rcx+18h]
0x180009339  sub     rax, [rcx+20h]
0x18000933d  mov     ecx, edx
0x18000933f  sar     rax, 4
0x180009343  cmp     edx, eax
0x180009345  cmova   ecx, eax
0x180009348  mov     eax, ecx
0x18000934a  shl     rax, 4
0x18000934e  add     [r8+20h], rax
0x180009352  xor     eax, eax
0x180009354  cmp     edx, ecx
0x180009356  setnz   al
0x180009359  retn
```
