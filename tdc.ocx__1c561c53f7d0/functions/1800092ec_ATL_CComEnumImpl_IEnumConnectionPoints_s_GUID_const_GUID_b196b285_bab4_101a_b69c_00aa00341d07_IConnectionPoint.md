# ATL::CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>::Skip(ulong)

- ea: `0x1800092ec`
- end: `0x180009322`
- name: `?Skip@?$CComEnumImpl@UIEnumConnectionPoints@@$1?_GUID_b196b285_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@@ATL@@UEAAJK@Z`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800092d0`

## callees

- `0x1800092ec`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>::Skip(
        __int64 a1,
        __int64 a2)
{
  int v2; // r8d
  __int64 result; // rax
  __int64 v5; // rcx
  __int64 v6; // rax

  v2 = a2;
  if ( !(_DWORD)a2 )
    return 2147942487LL;
  v5 = *(_QWORD *)(a1 + 32);
  v6 = (*(_QWORD *)(a1 + 24) - v5) >> 3;
  if ( (unsigned int)a2 > (unsigned int)v6 )
    a2 = (unsigned int)v6;
  result = v2 != (_DWORD)a2;
  *(_QWORD *)(a1 + 32) = v5 + 8 * a2;
  return result;
}

```

## disassembly

```asm
0x1800092ec  mov     r8d, edx
0x1800092ef  mov     r9, rcx
0x1800092f2  test    edx, edx
0x1800092f4  jnz     short loc_1800092FC
0x1800092f6  mov     eax, 80070057h
0x1800092fb  retn
0x1800092fc  mov     rcx, [rcx+20h]
0x180009300  mov     rax, [r9+18h]
0x180009304  sub     rax, rcx
0x180009307  sar     rax, 3
0x18000930b  cmp     r8d, eax
0x18000930e  cmova   edx, eax
0x180009311  xor     eax, eax
0x180009313  cmp     r8d, edx
0x180009316  setnz   al
0x180009319  lea     rcx, [rcx+rdx*8]
0x18000931d  mov     [r9+20h], rcx
0x180009321  retn
```
