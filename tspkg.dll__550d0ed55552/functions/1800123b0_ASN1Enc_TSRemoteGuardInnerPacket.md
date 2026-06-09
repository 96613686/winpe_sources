# ASN1Enc_TSRemoteGuardInnerPacket

- ea: `0x1800123b0`
- end: `0x18001253c`
- name: `ASN1Enc_TSRemoteGuardInnerPacket`
- size: `396`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800123b0`

## import_xrefs

- `MSASN1!ASN1DEREncOctetString` at `0x180012477`
- `MSASN1!ASN1DEREncOctetString` at `0x1800124bf`
- `MSASN1!ASN1DEREncOctetString` at `0x180012477`
- `MSASN1!ASN1DEREncOctetString` at `0x1800124bf`
- `MSASN1!ASN1BEREncOpenType` at `0x1800124fc`
- `MSASN1!ASN1BEREncOpenType` at `0x1800124fc`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18001243f`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18001248b`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800124cf`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18001250c`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18001251c`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18001243f`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18001248b`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800124cf`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18001250c`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18001251c`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800123e1`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180012411`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180012459`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800124a5`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800124eb`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800123e1`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180012411`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180012459`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800124a5`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800124eb`
- `MSASN1!ASN1BEREncU32` at `0x18001242b`
- `MSASN1!ASN1BEREncU32` at `0x18001242b`

## pseudocode

```c
_BOOL8 __fastcall ASN1Enc_TSRemoteGuardInnerPacket(__int64 a1, __int64 a2, __int64 a3)
{
  char v5; // si
  unsigned int v7; // [rsp+48h] [rbp+28h] BYREF
  unsigned int v8; // [rsp+58h] [rbp+38h] BYREF

  v8 = 0;
  v7 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  if ( !(unsigned int)ASN1BEREncExplicitTag(a1, a2, &v8) )
    return 0;
  v5 = *(_BYTE *)a3 & 0x7F;
  if ( *(_DWORD *)(a3 + 4) )
    v5 = *(_BYTE *)a3;
  return (v5 >= 0
       || (unsigned int)ASN1BEREncExplicitTag(a1, 0x80000000LL, &v7)
       && (unsigned int)ASN1BEREncU32(a1, 10, *(unsigned int *)(a3 + 4))
       && (unsigned int)ASN1BEREncEndOfContents(a1, v7))
      && (unsigned int)ASN1BEREncExplicitTag(a1, 2147483649LL, &v7)
      && (unsigned int)ASN1DEREncOctetString(a1, 4, *(unsigned int *)(a3 + 8), *(_QWORD *)(a3 + 16))
      && (unsigned int)ASN1BEREncEndOfContents(a1, v7)
      && (unsigned int)ASN1BEREncExplicitTag(a1, 2147483650LL, &v7)
      && (unsigned int)ASN1DEREncOctetString(a1, 4, *(unsigned int *)(a3 + 24), *(_QWORD *)(a3 + 32))
      && (unsigned int)ASN1BEREncEndOfContents(a1, v7)
      && ((v5 & 0x40) == 0
       || (unsigned int)ASN1BEREncExplicitTag(a1, 2147483651LL, &v7)
       && (unsigned int)ASN1BEREncOpenType(a1, a3 + 40)
       && (unsigned int)ASN1BEREncEndOfContents(a1, v7))
      && (unsigned int)ASN1BEREncEndOfContents(a1, v8) != 0;
}

```

## disassembly

```asm
0x1800123b0  mov     [rsp-18h+arg_0], rbx
0x1800123b5  push    rbp
0x1800123b6  push    rsi
0x1800123b7  push    rdi
0x1800123b8  mov     rbp, rsp
0x1800123bb  sub     rsp, 20h
0x1800123bf  test    edx, edx
0x1800123c1  mov     [rbp+arg_18], 0
0x1800123c8  mov     eax, 10h
0x1800123cd  mov     [rbp+arg_8], 0
0x1800123d4  mov     rdi, r8
0x1800123d7  cmovz   edx, eax
0x1800123da  lea     r8, [rbp+arg_18]
0x1800123de  mov     rbx, rcx
0x1800123e1  call    cs:__imp_ASN1BEREncExplicitTag
0x1800123e7  test    eax, eax
0x1800123e9  jz      loc_18001252D
0x1800123ef  movzx   ecx, byte ptr [rdi]
0x1800123f2  mov     al, cl
0x1800123f4  and     al, 7Fh
0x1800123f6  cmp     dword ptr [rdi+4], 0
0x1800123fa  movzx   esi, al
0x1800123fd  cmovnz  esi, ecx
0x180012400  test    sil, sil
0x180012403  jns     short loc_18001244D
0x180012405  lea     r8, [rbp+arg_8]
0x180012409  mov     edx, 80000000h
0x18001240e  mov     rcx, rbx
0x180012411  call    cs:__imp_ASN1BEREncExplicitTag
0x180012417  test    eax, eax
0x180012419  jz      loc_18001252D
0x18001241f  mov     r8d, [rdi+4]
0x180012423  mov     edx, 0Ah
0x180012428  mov     rcx, rbx
0x18001242b  call    cs:__imp_ASN1BEREncU32
0x180012431  test    eax, eax
0x180012433  jz      loc_18001252D
0x180012439  mov     edx, [rbp+arg_8]
0x18001243c  mov     rcx, rbx
0x18001243f  call    cs:__imp_ASN1BEREncEndOfContents
0x180012445  test    eax, eax
0x180012447  jz      loc_18001252D
0x18001244d  lea     r8, [rbp+arg_8]
0x180012451  mov     edx, 80000001h
0x180012456  mov     rcx, rbx
0x180012459  call    cs:__imp_ASN1BEREncExplicitTag
0x18001245f  test    eax, eax
0x180012461  jz      loc_18001252D
0x180012467  mov     r9, [rdi+10h]
0x18001246b  mov     edx, 4
0x180012470  mov     r8d, [rdi+8]
0x180012474  mov     rcx, rbx
0x180012477  call    cs:__imp_ASN1DEREncOctetString
0x18001247d  test    eax, eax
0x18001247f  jz      loc_18001252D
0x180012485  mov     edx, [rbp+arg_8]
0x180012488  mov     rcx, rbx
0x18001248b  call    cs:__imp_ASN1BEREncEndOfContents
0x180012491  test    eax, eax
0x180012493  jz      loc_18001252D
0x180012499  lea     r8, [rbp+arg_8]
0x18001249d  mov     edx, 80000002h
0x1800124a2  mov     rcx, rbx
0x1800124a5  call    cs:__imp_ASN1BEREncExplicitTag
0x1800124ab  test    eax, eax
0x1800124ad  jz      short loc_18001252D
0x1800124af  mov     r9, [rdi+20h]
0x1800124b3  mov     edx, 4
0x1800124b8  mov     r8d, [rdi+18h]
0x1800124bc  mov     rcx, rbx
0x1800124bf  call    cs:__imp_ASN1DEREncOctetString
0x1800124c5  test    eax, eax
0x1800124c7  jz      short loc_18001252D
0x1800124c9  mov     edx, [rbp+arg_8]
0x1800124cc  mov     rcx, rbx
0x1800124cf  call    cs:__imp_ASN1BEREncEndOfContents
0x1800124d5  test    eax, eax
0x1800124d7  jz      short loc_18001252D
0x1800124d9  test    sil, 40h
0x1800124dd  jz      short loc_180012516
0x1800124df  lea     r8, [rbp+arg_8]
0x1800124e3  mov     edx, 80000003h
0x1800124e8  mov     rcx, rbx
0x1800124eb  call    cs:__imp_ASN1BEREncExplicitTag
0x1800124f1  test    eax, eax
0x1800124f3  jz      short loc_18001252D
0x1800124f5  lea     rdx, [rdi+28h]
0x1800124f9  mov     rcx, rbx
0x1800124fc  call    cs:__imp_ASN1BEREncOpenType
0x180012502  test    eax, eax
0x180012504  jz      short loc_18001252D
0x180012506  mov     edx, [rbp+arg_8]
0x180012509  mov     rcx, rbx
0x18001250c  call    cs:__imp_ASN1BEREncEndOfContents
0x180012512  test    eax, eax
0x180012514  jz      short loc_18001252D
0x180012516  mov     edx, [rbp+arg_18]
0x180012519  mov     rcx, rbx
0x18001251c  call    cs:__imp_ASN1BEREncEndOfContents
0x180012522  xor     ecx, ecx
0x180012524  test    eax, eax
0x180012526  setnz   cl
0x180012529  mov     eax, ecx
0x18001252b  jmp     short loc_18001252F
0x18001252d  xor     eax, eax
0x18001252f  mov     rbx, [rsp+20h+arg_0]
0x180012534  add     rsp, 20h
0x180012538  pop     rdi
0x180012539  pop     rsi
0x18001253a  pop     rbp
0x18001253b  retn
```
