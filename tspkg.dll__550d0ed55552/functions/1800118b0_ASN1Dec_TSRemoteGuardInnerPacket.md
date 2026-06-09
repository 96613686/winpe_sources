# ASN1Dec_TSRemoteGuardInnerPacket

- ea: `0x1800118b0`
- end: `0x180011adc`
- name: `ASN1Dec_TSRemoteGuardInnerPacket`
- size: `556`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800118b0`

## import_xrefs

- `MSASN1!ASN1BERDecU32Val` at `0x180011955`
- `MSASN1!ASN1BERDecU32Val` at `0x180011955`
- `MSASN1!ASN1BERDecOctetString2` at `0x1800119a9`
- `MSASN1!ASN1BERDecOctetString2` at `0x1800119fd`
- `MSASN1!ASN1BERDecOctetString2` at `0x1800119a9`
- `MSASN1!ASN1BERDecOctetString2` at `0x1800119fd`
- `MSASN1!ASN1BERDecSkip` at `0x180011aa4`
- `MSASN1!ASN1BERDecSkip` at `0x180011aa4`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18001196f`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800119c3`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180011a17`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180011a78`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180011acb`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18001196f`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800119c3`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180011a17`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180011a78`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180011acb`
- `MSASN1!ASN1BERDecNotEndOfContents` at `0x180011a96`
- `MSASN1!ASN1BERDecNotEndOfContents` at `0x180011a96`
- `MSASN1!ASN1BERDecPeekTag` at `0x18001191b`
- `MSASN1!ASN1BERDecPeekTag` at `0x180011a2d`
- `MSASN1!ASN1BERDecPeekTag` at `0x18001191b`
- `MSASN1!ASN1BERDecPeekTag` at `0x180011a2d`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180011901`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18001193a`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18001198e`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800119e2`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180011a50`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180011901`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18001193a`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18001198e`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800119e2`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180011a50`
- `MSASN1!ASN1BERDecOpenType2` at `0x180011a62`
- `MSASN1!ASN1BERDecOpenType2` at `0x180011a62`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_TSRemoteGuardInnerPacket(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v9; // [rsp+20h] [rbp-20h] BYREF
  __int64 v10; // [rsp+28h] [rbp-18h] BYREF
  __int64 v11; // [rsp+30h] [rbp-10h] BYREF
  int v12; // [rsp+58h] [rbp+18h] BYREF
  __int64 v13; // [rsp+68h] [rbp+28h] BYREF

  v13 = 0;
  v11 = 0;
  v12 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  v9 = 0;
  v10 = 0;
  if ( !(unsigned int)ASN1BERDecExplicitTag(a1, a2, &v13, &v11) )
    return 0;
  v5 = v13;
  *(_BYTE *)a3 = 0;
  ASN1BERDecPeekTag(v5, &v12);
  if ( v12 == 0x80000000 )
  {
    v6 = v13;
    *(_BYTE *)a3 |= 0x80u;
    if ( !(unsigned int)ASN1BERDecExplicitTag(v6, 0x80000000LL, &v9, &v10)
      || !(unsigned int)ASN1BERDecU32Val(v9, 10, a3 + 4)
      || !(unsigned int)ASN1BERDecEndOfContents(v13, v9, v10) )
    {
      return 0;
    }
  }
  if ( !(unsigned int)ASN1BERDecExplicitTag(v13, 2147483649LL, &v9, &v10) )
    return 0;
  if ( !(unsigned int)ASN1BERDecOctetString2(v9, 4, a3 + 8) )
    return 0;
  if ( !(unsigned int)ASN1BERDecEndOfContents(v13, v9, v10) )
    return 0;
  if ( !(unsigned int)ASN1BERDecExplicitTag(v13, 2147483650LL, &v9, &v10) )
    return 0;
  if ( !(unsigned int)ASN1BERDecOctetString2(v9, 4, a3 + 24) )
    return 0;
  if ( !(unsigned int)ASN1BERDecEndOfContents(v13, v9, v10) )
    return 0;
  if ( (unsigned int)ASN1BERDecPeekTag(v13, &v12) )
  {
    if ( v12 == -2147483645 )
    {
      v7 = v13;
      *(_BYTE *)a3 |= 0x40u;
      if ( !(unsigned int)ASN1BERDecExplicitTag(v7, 2147483651LL, &v9, &v10)
        || !(unsigned int)ASN1BERDecOpenType2(v9, a3 + 40)
        || !(unsigned int)ASN1BERDecEndOfContents(v13, v9, v10) )
      {
        return 0;
      }
    }
  }
  if ( *(char *)a3 >= 0 )
    *(_DWORD *)(a3 + 4) = 0;
  while ( (unsigned int)ASN1BERDecNotEndOfContents(v13, v11) )
  {
    if ( !(unsigned int)ASN1BERDecSkip(v13) )
      return 0;
  }
  return (unsigned int)ASN1BERDecEndOfContents(a1, v13, v11) != 0;
}

```

## disassembly

```asm
0x1800118b0  mov     [rsp-8+arg_0], rbx
0x1800118b5  mov     [rsp-8+arg_10], rdi
0x1800118ba  push    rbp
0x1800118bb  mov     rbp, rsp
0x1800118be  sub     rsp, 40h
0x1800118c2  test    edx, edx
0x1800118c4  mov     [rbp+arg_18], 0
0x1800118cc  mov     eax, 10h
0x1800118d1  mov     [rbp+var_10], 0
0x1800118d9  mov     rbx, r8
0x1800118dc  mov     [rbp+arg_8], 0
0x1800118e3  cmovz   edx, eax
0x1800118e6  mov     [rbp+var_20], 0
0x1800118ee  lea     r9, [rbp+var_10]
0x1800118f2  mov     [rbp+var_18], 0
0x1800118fa  lea     r8, [rbp+arg_18]
0x1800118fe  mov     rdi, rcx
0x180011901  call    cs:__imp_ASN1BERDecExplicitTag
0x180011907  test    eax, eax
0x180011909  jz      loc_180011AAE
0x18001190f  mov     rcx, [rbp+arg_18]
0x180011913  lea     rdx, [rbp+arg_8]
0x180011917  xor     eax, eax
0x180011919  mov     [rbx], al
0x18001191b  call    cs:__imp_ASN1BERDecPeekTag
0x180011921  mov     edx, 80000000h
0x180011926  cmp     [rbp+arg_8], edx
0x180011929  jnz     short loc_18001197D
0x18001192b  mov     rcx, [rbp+arg_18]
0x18001192f  lea     r9, [rbp+var_18]
0x180011933  or      byte ptr [rbx], 80h
0x180011936  lea     r8, [rbp+var_20]
0x18001193a  call    cs:__imp_ASN1BERDecExplicitTag
0x180011940  test    eax, eax
0x180011942  jz      loc_180011AAE
0x180011948  mov     rcx, [rbp+var_20]
0x18001194c  lea     r8, [rbx+4]
0x180011950  mov     edx, 0Ah
0x180011955  call    cs:__imp_ASN1BERDecU32Val
0x18001195b  test    eax, eax
0x18001195d  jz      loc_180011AAE
0x180011963  mov     r8, [rbp+var_18]
0x180011967  mov     rdx, [rbp+var_20]
0x18001196b  mov     rcx, [rbp+arg_18]
0x18001196f  call    cs:__imp_ASN1BERDecEndOfContents
0x180011975  test    eax, eax
0x180011977  jz      loc_180011AAE
0x18001197d  mov     rcx, [rbp+arg_18]
0x180011981  lea     r9, [rbp+var_18]
0x180011985  lea     r8, [rbp+var_20]
0x180011989  mov     edx, 80000001h
0x18001198e  call    cs:__imp_ASN1BERDecExplicitTag
0x180011994  test    eax, eax
0x180011996  jz      loc_180011AAE
0x18001199c  mov     rcx, [rbp+var_20]
0x1800119a0  lea     r8, [rbx+8]
0x1800119a4  mov     edx, 4
0x1800119a9  call    cs:__imp_ASN1BERDecOctetString2
0x1800119af  test    eax, eax
0x1800119b1  jz      loc_180011AAE
0x1800119b7  mov     r8, [rbp+var_18]
0x1800119bb  mov     rdx, [rbp+var_20]
0x1800119bf  mov     rcx, [rbp+arg_18]
0x1800119c3  call    cs:__imp_ASN1BERDecEndOfContents
0x1800119c9  test    eax, eax
0x1800119cb  jz      loc_180011AAE
0x1800119d1  mov     rcx, [rbp+arg_18]
0x1800119d5  lea     r9, [rbp+var_18]
0x1800119d9  lea     r8, [rbp+var_20]
0x1800119dd  mov     edx, 80000002h
0x1800119e2  call    cs:__imp_ASN1BERDecExplicitTag
0x1800119e8  test    eax, eax
0x1800119ea  jz      loc_180011AAE
0x1800119f0  mov     rcx, [rbp+var_20]
0x1800119f4  lea     r8, [rbx+18h]
0x1800119f8  mov     edx, 4
0x1800119fd  call    cs:__imp_ASN1BERDecOctetString2
0x180011a03  test    eax, eax
0x180011a05  jz      loc_180011AAE
0x180011a0b  mov     r8, [rbp+var_18]
0x180011a0f  mov     rdx, [rbp+var_20]
0x180011a13  mov     rcx, [rbp+arg_18]
0x180011a17  call    cs:__imp_ASN1BERDecEndOfContents
0x180011a1d  test    eax, eax
0x180011a1f  jz      loc_180011AAE
0x180011a25  mov     rcx, [rbp+arg_18]
0x180011a29  lea     rdx, [rbp+arg_8]
0x180011a2d  call    cs:__imp_ASN1BERDecPeekTag
0x180011a33  test    eax, eax
0x180011a35  jz      short loc_180011A82
0x180011a37  mov     edx, 80000003h
0x180011a3c  cmp     [rbp+arg_8], edx
0x180011a3f  jnz     short loc_180011A82
0x180011a41  mov     rcx, [rbp+arg_18]
0x180011a45  lea     r9, [rbp+var_18]
0x180011a49  or      byte ptr [rbx], 40h
0x180011a4c  lea     r8, [rbp+var_20]
0x180011a50  call    cs:__imp_ASN1BERDecExplicitTag
0x180011a56  test    eax, eax
0x180011a58  jz      short loc_180011AAE
0x180011a5a  mov     rcx, [rbp+var_20]
0x180011a5e  lea     rdx, [rbx+28h]
0x180011a62  call    cs:__imp_ASN1BERDecOpenType2
0x180011a68  test    eax, eax
0x180011a6a  jz      short loc_180011AAE
0x180011a6c  mov     r8, [rbp+var_18]
0x180011a70  mov     rdx, [rbp+var_20]
0x180011a74  mov     rcx, [rbp+arg_18]
0x180011a78  call    cs:__imp_ASN1BERDecEndOfContents
0x180011a7e  test    eax, eax
0x180011a80  jz      short loc_180011AAE
0x180011a82  cmp     byte ptr [rbx], 0
0x180011a85  jl      short loc_180011A8E
0x180011a87  mov     dword ptr [rbx+4], 0
0x180011a8e  mov     rdx, [rbp+var_10]
0x180011a92  mov     rcx, [rbp+arg_18]
0x180011a96  call    cs:__imp_ASN1BERDecNotEndOfContents
0x180011a9c  test    eax, eax
0x180011a9e  jz      short loc_180011AC0
0x180011aa0  mov     rcx, [rbp+arg_18]
0x180011aa4  call    cs:__imp_ASN1BERDecSkip
0x180011aaa  test    eax, eax
0x180011aac  jnz     short loc_180011A8E
0x180011aae  xor     eax, eax
0x180011ab0  mov     rbx, [rsp+40h+arg_0]
0x180011ab5  mov     rdi, [rsp+40h+arg_10]
0x180011aba  add     rsp, 40h
0x180011abe  pop     rbp
0x180011abf  retn
0x180011ac0  mov     r8, [rbp+var_10]
0x180011ac4  mov     rcx, rdi
0x180011ac7  mov     rdx, [rbp+arg_18]
0x180011acb  call    cs:__imp_ASN1BERDecEndOfContents
0x180011ad1  xor     ecx, ecx
0x180011ad3  test    eax, eax
0x180011ad5  setnz   cl
0x180011ad8  mov     eax, ecx
0x180011ada  jmp     short loc_180011AB0
```
