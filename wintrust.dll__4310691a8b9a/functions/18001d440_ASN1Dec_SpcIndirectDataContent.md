# ASN1Dec_SpcIndirectDataContent

- ea: `0x18001d440`
- end: `0x18001d649`
- name: `ASN1Dec_SpcIndirectDataContent`
- size: `521`
- prototype: `_BOOL8 __fastcall(__int64, __int64, _BYTE *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001d440`

## import_xrefs

- `MSASN1!ASN1BERDecOpenType2` at `0x18001d4fc`
- `MSASN1!ASN1BERDecOpenType2` at `0x18001d5c9`
- `MSASN1!ASN1BERDecOpenType2` at `0x18001d4fc`
- `MSASN1!ASN1BERDecOpenType2` at `0x18001d5c9`
- `MSASN1!ASN1BERDecOctetString2` at `0x18001d5f8`
- `MSASN1!ASN1BERDecOctetString2` at `0x18001d5f8`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18001d47d`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18001d4b4`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18001d545`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18001d57c`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18001d47d`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18001d4b4`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18001d545`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18001d57c`
- `MSASN1!ASN1BERDecPeekTag` at `0x18001d4e7`
- `MSASN1!ASN1BERDecPeekTag` at `0x18001d5b0`
- `MSASN1!ASN1BERDecPeekTag` at `0x18001d4e7`
- `MSASN1!ASN1BERDecPeekTag` at `0x18001d5b0`
- `MSASN1!ASN1BERDecObjectIdentifier2` at `0x18001d4d1`
- `MSASN1!ASN1BERDecObjectIdentifier2` at `0x18001d59a`
- `MSASN1!ASN1BERDecObjectIdentifier2` at `0x18001d4d1`
- `MSASN1!ASN1BERDecObjectIdentifier2` at `0x18001d59a`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18001d515`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18001d5de`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18001d60d`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18001d622`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18001d515`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18001d5de`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18001d60d`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18001d622`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_SpcIndirectDataContent(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rsi
  __int64 v9; // rdi
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v13; // [rsp+20h] [rbp-30h] BYREF
  __int64 v14; // [rsp+28h] [rbp-28h] BYREF
  __int64 v15; // [rsp+30h] [rbp-20h] BYREF
  __int64 v16; // [rsp+38h] [rbp-18h] BYREF
  __int64 v17; // [rsp+40h] [rbp-10h] BYREF
  int v18; // [rsp+88h] [rbp+38h] BYREF
  __int64 v19; // [rsp+98h] [rbp+48h] BYREF

  v14 = 0;
  v17 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  if ( !(unsigned int)ASN1BERDecExplicitTag(a1, a2, &v14, &v17) )
    return 0;
  v5 = v14;
  v19 = 0;
  v13 = 0;
  v18 = 0;
  if ( !(unsigned int)ASN1BERDecExplicitTag(v14, 16, &v19, &v13) )
    return 0;
  v6 = v19;
  *a3 = 0;
  if ( !(unsigned int)ASN1BERDecObjectIdentifier2(v6, 6, a3 + 4) )
    return 0;
  if ( (unsigned int)ASN1BERDecPeekTag(v19, &v18) )
  {
    v7 = v19;
    *a3 |= 0x80u;
    if ( !(unsigned int)ASN1BERDecOpenType2(v7, a3 + 72) )
      return 0;
  }
  if ( !(unsigned int)ASN1BERDecEndOfContents(v5, v19, v13) )
    return 0;
  v8 = v14;
  v13 = 0;
  v16 = 0;
  if ( !(unsigned int)ASN1BERDecExplicitTag(v14, 16, &v13, &v16) )
    return 0;
  v9 = v13;
  v19 = 0;
  v15 = 0;
  v18 = 0;
  if ( !(unsigned int)ASN1BERDecExplicitTag(v13, 16, &v19, &v15) )
    return 0;
  v10 = v19;
  a3[88] = 0;
  if ( !(unsigned int)ASN1BERDecObjectIdentifier2(v10, 6, a3 + 92) )
    return 0;
  if ( (unsigned int)ASN1BERDecPeekTag(v19, &v18) )
  {
    v11 = v19;
    a3[88] |= 0x80u;
    if ( !(unsigned int)ASN1BERDecOpenType2(v11, a3 + 160) )
      return 0;
  }
  return (unsigned int)ASN1BERDecEndOfContents(v9, v19, v15)
      && (unsigned int)ASN1BERDecOctetString2(v13, 4, a3 + 176)
      && (unsigned int)ASN1BERDecEndOfContents(v8, v13, v16)
      && (unsigned int)ASN1BERDecEndOfContents(a1, v14, v17) != 0;
}

```

## disassembly

```asm
0x18001d440  mov     [rsp-28h+arg_0], rbx
0x18001d445  push    rbp
0x18001d446  push    rsi
0x18001d447  push    rdi
0x18001d448  push    r12
0x18001d44a  push    r14
0x18001d44c  mov     rbp, rsp
0x18001d44f  sub     rsp, 50h
0x18001d453  test    edx, edx
0x18001d455  mov     [rbp+var_28], 0
0x18001d45d  mov     rbx, r8
0x18001d460  mov     [rbp+var_10], 0
0x18001d468  mov     r12d, 10h
0x18001d46e  lea     r9, [rbp+var_10]
0x18001d472  cmovz   edx, r12d
0x18001d476  lea     r8, [rbp+var_28]
0x18001d47a  mov     r14, rcx
0x18001d47d  call    cs:__imp_ASN1BERDecExplicitTag
0x18001d483  test    eax, eax
0x18001d485  jz      loc_18001D645
0x18001d48b  mov     rdi, [rbp+var_28]
0x18001d48f  lea     r9, [rbp+var_30]
0x18001d493  mov     rcx, rdi
0x18001d496  mov     [rbp+arg_18], 0
0x18001d49e  lea     r8, [rbp+arg_18]
0x18001d4a2  mov     [rbp+var_30], 0
0x18001d4aa  mov     edx, r12d
0x18001d4ad  mov     [rbp+arg_8], 0
0x18001d4b4  call    cs:__imp_ASN1BERDecExplicitTag
0x18001d4ba  test    eax, eax
0x18001d4bc  jz      loc_18001D645
0x18001d4c2  mov     rcx, [rbp+arg_18]
0x18001d4c6  lea     r8, [rbx+4]
0x18001d4ca  xor     eax, eax
0x18001d4cc  mov     [rbx], al
0x18001d4ce  lea     edx, [rax+6]
0x18001d4d1  call    cs:__imp_ASN1BERDecObjectIdentifier2
0x18001d4d7  test    eax, eax
0x18001d4d9  jz      loc_18001D645
0x18001d4df  mov     rcx, [rbp+arg_18]
0x18001d4e3  lea     rdx, [rbp+arg_8]
0x18001d4e7  call    cs:__imp_ASN1BERDecPeekTag
0x18001d4ed  test    eax, eax
0x18001d4ef  jz      short loc_18001D50A
0x18001d4f1  mov     rcx, [rbp+arg_18]
0x18001d4f5  lea     rdx, [rbx+48h]
0x18001d4f9  or      byte ptr [rbx], 80h
0x18001d4fc  call    cs:__imp_ASN1BERDecOpenType2
0x18001d502  test    eax, eax
0x18001d504  jz      loc_18001D645
0x18001d50a  mov     r8, [rbp+var_30]
0x18001d50e  mov     rcx, rdi
0x18001d511  mov     rdx, [rbp+arg_18]
0x18001d515  call    cs:__imp_ASN1BERDecEndOfContents
0x18001d51b  test    eax, eax
0x18001d51d  jz      loc_18001D645
0x18001d523  mov     rsi, [rbp+var_28]
0x18001d527  lea     r9, [rbp+var_18]
0x18001d52b  mov     rcx, rsi
0x18001d52e  mov     [rbp+var_30], 0
0x18001d536  lea     r8, [rbp+var_30]
0x18001d53a  mov     [rbp+var_18], 0
0x18001d542  mov     edx, r12d
0x18001d545  call    cs:__imp_ASN1BERDecExplicitTag
0x18001d54b  test    eax, eax
0x18001d54d  jz      loc_18001D645
0x18001d553  mov     rdi, [rbp+var_30]
0x18001d557  lea     r9, [rbp+var_20]
0x18001d55b  mov     rcx, rdi
0x18001d55e  mov     [rbp+arg_18], 0
0x18001d566  lea     r8, [rbp+arg_18]
0x18001d56a  mov     [rbp+var_20], 0
0x18001d572  mov     edx, r12d
0x18001d575  mov     [rbp+arg_8], 0
0x18001d57c  call    cs:__imp_ASN1BERDecExplicitTag
0x18001d582  test    eax, eax
0x18001d584  jz      loc_18001D645
0x18001d58a  mov     rcx, [rbp+arg_18]
0x18001d58e  lea     r8, [rbx+5Ch]
0x18001d592  xor     eax, eax
0x18001d594  mov     [rbx+58h], al
0x18001d597  lea     edx, [rax+6]
0x18001d59a  call    cs:__imp_ASN1BERDecObjectIdentifier2
0x18001d5a0  test    eax, eax
0x18001d5a2  jz      loc_18001D645
0x18001d5a8  mov     rcx, [rbp+arg_18]
0x18001d5ac  lea     rdx, [rbp+arg_8]
0x18001d5b0  call    cs:__imp_ASN1BERDecPeekTag
0x18001d5b6  test    eax, eax
0x18001d5b8  jz      short loc_18001D5D3
0x18001d5ba  mov     rcx, [rbp+arg_18]
0x18001d5be  lea     rdx, [rbx+0A0h]
0x18001d5c5  or      byte ptr [rbx+58h], 80h
0x18001d5c9  call    cs:__imp_ASN1BERDecOpenType2
0x18001d5cf  test    eax, eax
0x18001d5d1  jz      short loc_18001D645
0x18001d5d3  mov     r8, [rbp+var_20]
0x18001d5d7  mov     rcx, rdi
0x18001d5da  mov     rdx, [rbp+arg_18]
0x18001d5de  call    cs:__imp_ASN1BERDecEndOfContents
0x18001d5e4  test    eax, eax
0x18001d5e6  jz      short loc_18001D645
0x18001d5e8  mov     rcx, [rbp+var_30]
0x18001d5ec  lea     r8, [rbx+0B0h]
0x18001d5f3  mov     edx, 4
0x18001d5f8  call    cs:__imp_ASN1BERDecOctetString2
0x18001d5fe  test    eax, eax
0x18001d600  jz      short loc_18001D645
0x18001d602  mov     r8, [rbp+var_18]
0x18001d606  mov     rcx, rsi
0x18001d609  mov     rdx, [rbp+var_30]
0x18001d60d  call    cs:__imp_ASN1BERDecEndOfContents
0x18001d613  test    eax, eax
0x18001d615  jz      short loc_18001D645
0x18001d617  mov     r8, [rbp+var_10]
0x18001d61b  mov     rcx, r14
0x18001d61e  mov     rdx, [rbp+var_28]
0x18001d622  call    cs:__imp_ASN1BERDecEndOfContents
0x18001d628  xor     ecx, ecx
0x18001d62a  test    eax, eax
0x18001d62c  setnz   cl
0x18001d62f  mov     eax, ecx
0x18001d631  mov     rbx, [rsp+50h+arg_0]
0x18001d639  add     rsp, 50h
0x18001d63d  pop     r14
0x18001d63f  pop     r12
0x18001d641  pop     rdi
0x18001d642  pop     rsi
0x18001d643  pop     rbp
0x18001d644  retn
0x18001d645  xor     eax, eax
0x18001d647  jmp     short loc_18001D631
```
