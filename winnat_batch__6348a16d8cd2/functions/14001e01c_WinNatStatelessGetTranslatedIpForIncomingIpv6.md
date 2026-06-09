# WinNatStatelessGetTranslatedIpForIncomingIpv6

- ea: `0x14001e01c`
- end: `0x14001e084`
- name: `WinNatStatelessGetTranslatedIpForIncomingIpv6`
- size: `104`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001d87c`
- `0x14001e2a0`

## callees

- `0x140004da0`
- `0x14001aa1c`
- `0x14001e01c`

## pseudocode

```c
__int64 __fastcall WinNatStatelessGetTranslatedIpForIncomingIpv6(__int64 *a1, __int64 a2, const UCHAR *a3, __int64 a4)
{
  __int64 v4; // rbx
  __int64 v6; // rdi
  __int64 v7; // rdx
  __int64 result; // rax

  v4 = *a1;
  v6 = a2;
  LOBYTE(a2) = *(_BYTE *)(a2 + 24);
  IN6_EXTRACT_V4ADDR_FROM_V4EMBV6(*a1 + 24, a2, a4);
  LOBYTE(v7) = *(_BYTE *)(v6 + 42);
  IN6_EXTRACT_V4ADDR_FROM_V4EMBV6(v4 + 8, v7, a3);
  if ( Ipv4AddressType(a3) != NlatUnicast )
    return 3221226011LL;
  if ( (unsigned __int16)*(_DWORD *)a3 == 0xFEA9 )
    return 3221226011LL;
  result = 0;
  if ( *a3 == 127 )
    return 3221226011LL;
  return result;
}

```

## disassembly

```asm
0x14001e01c  mov     [rsp+arg_0], rbx
0x14001e021  mov     [rsp+arg_8], rsi
0x14001e026  push    rdi
0x14001e027  sub     rsp, 20h
0x14001e02b  mov     rbx, [rcx]
0x14001e02e  mov     rsi, r8
0x14001e031  mov     rdi, rdx
0x14001e034  mov     r8, r9
0x14001e037  mov     dl, [rdx+18h]
0x14001e03a  lea     rcx, [rbx+18h]
0x14001e03e  call    IN6_EXTRACT_V4ADDR_FROM_V4EMBV6
0x14001e043  mov     dl, [rdi+2Ah]
0x14001e046  lea     rcx, [rbx+8]
0x14001e04a  mov     r8, rsi
0x14001e04d  call    IN6_EXTRACT_V4ADDR_FROM_V4EMBV6
0x14001e052  mov     rcx, rsi; Address
0x14001e055  call    Ipv4AddressType
0x14001e05a  cmp     eax, 1
0x14001e05d  jnz     short loc_14001E06E
0x14001e05f  mov     eax, [rsi]
0x14001e061  cmp     ax, 0FEA9h
0x14001e065  jz      short loc_14001E06E
0x14001e067  xor     eax, eax
0x14001e069  cmp     byte ptr [rsi], 7Fh
0x14001e06c  jnz     short loc_14001E073
0x14001e06e  mov     eax, 0C000021Bh
0x14001e073  mov     rbx, [rsp+28h+arg_0]
0x14001e078  mov     rsi, [rsp+28h+arg_8]
0x14001e07d  add     rsp, 20h
0x14001e081  pop     rdi
0x14001e082  retn
```
