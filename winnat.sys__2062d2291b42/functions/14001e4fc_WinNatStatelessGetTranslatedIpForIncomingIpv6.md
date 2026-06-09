# WinNatStatelessGetTranslatedIpForIncomingIpv6

- ea: `0x14001e4fc`
- end: `0x14001e585`
- name: `WinNatStatelessGetTranslatedIpForIncomingIpv6`
- size: `137`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14001dd5c`
- `0x14001e7d8`

## callees

- `0x140004da0`
- `0x14000e390`
- `0x140015640`
- `0x14001aefc`
- `0x14001e4fc`

## pseudocode

```c
__int64 __fastcall WinNatStatelessGetTranslatedIpForIncomingIpv6(__int64 *a1, __int64 a2, const UCHAR *a3, _DWORD *a4)
{
  __int64 v4; // rbp
  __int64 v7; // rbx
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 result; // rax

  v4 = *a1;
  v7 = a2;
  if ( (Feature_CLAT_Preview2_RandomLocalAddress__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_CLAT_Preview2_RandomLocalAddress__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_CLAT_Preview2_RandomLocalAddress__private_IsEnabledDeviceUsageNoInline(
                                     a1,
                                     a2,
                                     a3,
                                     a4);
  if ( !IsEnabledDeviceUsageNoInline || IN6_IS_ADDR_UNSPECIFIED((const IN6_ADDR *)(v7 + 44)) )
  {
    LOBYTE(a2) = *(_BYTE *)(v7 + 24);
    IN6_EXTRACT_V4ADDR_FROM_V4EMBV6(v4 + 24, a2, a4);
  }
  else
  {
    *a4 = *(_DWORD *)v7;
  }
  LOBYTE(a2) = *(_BYTE *)(v7 + 42);
  IN6_EXTRACT_V4ADDR_FROM_V4EMBV6(v4 + 8, a2, a3);
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
0x14001e4fc  push    rbx
0x14001e4fe  push    rbp
0x14001e4ff  push    rsi
0x14001e500  push    rdi
0x14001e501  sub     rsp, 28h
0x14001e505  mov     rbp, [rcx]
0x14001e508  mov     rsi, r9
0x14001e50b  mov     rdi, r8
0x14001e50e  mov     rbx, rdx
0x14001e511  mov     eax, cs:Feature_CLAT_Preview2_RandomLocalAddress__private_featureState
0x14001e517  test    al, 10h
0x14001e519  jz      short loc_14001E520
0x14001e51b  and     eax, 1
0x14001e51e  jmp     short loc_14001E525
0x14001e520  call    Feature_CLAT_Preview2_RandomLocalAddress__private_IsEnabledDeviceUsageNoInline
0x14001e525  test    eax, eax
0x14001e527  jz      short loc_14001E53C
0x14001e529  lea     rcx, [rbx+2Ch]; a
0x14001e52d  call    IN6_IS_ADDR_UNSPECIFIED
0x14001e532  test    al, al
0x14001e534  jnz     short loc_14001E53C
0x14001e536  mov     eax, [rbx]
0x14001e538  mov     [rsi], eax
0x14001e53a  jmp     short loc_14001E54B
0x14001e53c  mov     dl, [rbx+18h]
0x14001e53f  lea     rcx, [rbp+18h]
0x14001e543  mov     r8, rsi
0x14001e546  call    IN6_EXTRACT_V4ADDR_FROM_V4EMBV6
0x14001e54b  mov     dl, [rbx+2Ah]
0x14001e54e  lea     rcx, [rbp+8]
0x14001e552  mov     r8, rdi
0x14001e555  call    IN6_EXTRACT_V4ADDR_FROM_V4EMBV6
0x14001e55a  mov     rcx, rdi; Address
0x14001e55d  call    Ipv4AddressType
0x14001e562  cmp     eax, 1
0x14001e565  jnz     short loc_14001E576
0x14001e567  mov     eax, [rdi]
0x14001e569  cmp     ax, 0FEA9h
0x14001e56d  jz      short loc_14001E576
0x14001e56f  xor     eax, eax
0x14001e571  cmp     byte ptr [rdi], 7Fh
0x14001e574  jnz     short loc_14001E57B
0x14001e576  mov     eax, 0C000021Bh
0x14001e57b  add     rsp, 28h
0x14001e57f  pop     rdi
0x14001e580  pop     rsi
0x14001e581  pop     rbp
0x14001e582  pop     rbx
0x14001e583  retn
```
