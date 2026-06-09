# ASN1Enc_SpcIndirectDataContent

- ea: `0x180031540`
- end: `0x180031663`
- name: `ASN1Enc_SpcIndirectDataContent`
- size: `291`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180030df8`
- `0x180031540`

## import_xrefs

- `MSASN1!ASN1BEREncOpenType` at `0x1800315bd`
- `MSASN1!ASN1BEREncOpenType` at `0x1800315bd`
- `MSASN1!ASN1BEREncOctetString` at `0x18003161e`
- `MSASN1!ASN1BEREncOctetString` at `0x18003161e`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800315d2`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18003162f`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180031640`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800315d2`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18003162f`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180031640`
- `MSASN1!ASN1BEREncObjectIdentifier2` at `0x1800315a3`
- `MSASN1!ASN1BEREncObjectIdentifier2` at `0x1800315a3`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18003156b`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18003158b`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800315ee`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18003156b`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18003158b`
- `MSASN1!ASN1BEREncExplicitTag` at `0x1800315ee`

## pseudocode

```c
_BOOL8 __fastcall ASN1Enc_SpcIndirectDataContent(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rdx
  unsigned int v7; // [rsp+38h] [rbp+10h] BYREF
  unsigned int v8; // [rsp+48h] [rbp+20h] BYREF

  v8 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  if ( (unsigned int)ASN1BEREncExplicitTag(a1, a2, &v8)
    && (v7 = 0, (unsigned int)ASN1BEREncExplicitTag(a1, 16, &v7))
    && (unsigned int)ASN1BEREncObjectIdentifier2(a1, 6, a3 + 4)
    && (*(char *)a3 >= 0 || (unsigned int)ASN1BEREncOpenType(a1, a3 + 72))
    && (unsigned int)ASN1BEREncEndOfContents(a1, v7)
    && (v7 = 0, (unsigned int)ASN1BEREncExplicitTag(a1, 16, &v7))
    && ASN1Enc_AlgorithmIdentifier(a1, v5, (char *)(a3 + 88))
    && (unsigned int)ASN1BEREncOctetString(a1, 4, *(unsigned int *)(a3 + 176), *(_QWORD *)(a3 + 184))
    && (unsigned int)ASN1BEREncEndOfContents(a1, v7) )
  {
    return (unsigned int)ASN1BEREncEndOfContents(a1, v8) != 0;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180031540  mov     rax, rsp
0x180031543  mov     [rax+8], rbx
0x180031547  mov     [rax+18h], rbp
0x18003154b  push    rdi
0x18003154c  sub     rsp, 20h
0x180031550  test    edx, edx
0x180031552  mov     dword ptr [rax+20h], 0
0x180031559  mov     rdi, r8
0x18003155c  mov     ebp, 10h
0x180031561  cmovz   edx, ebp
0x180031564  lea     r8, [rax+20h]
0x180031568  mov     rbx, rcx
0x18003156b  call    cs:__imp_ASN1BEREncExplicitTag
0x180031571  test    eax, eax
0x180031573  jz      loc_180031651
0x180031579  lea     r8, [rsp+28h+arg_8]
0x18003157e  mov     [rsp+28h+arg_8], 0
0x180031586  mov     edx, ebp
0x180031588  mov     rcx, rbx
0x18003158b  call    cs:__imp_ASN1BEREncExplicitTag
0x180031591  test    eax, eax
0x180031593  jz      loc_180031651
0x180031599  lea     r8, [rdi+4]
0x18003159d  mov     rcx, rbx
0x1800315a0  lea     edx, [rbp-0Ah]
0x1800315a3  call    cs:__imp_ASN1BEREncObjectIdentifier2
0x1800315a9  test    eax, eax
0x1800315ab  jz      loc_180031651
0x1800315b1  cmp     byte ptr [rdi], 0
0x1800315b4  jge     short loc_1800315CB
0x1800315b6  lea     rdx, [rdi+48h]
0x1800315ba  mov     rcx, rbx
0x1800315bd  call    cs:__imp_ASN1BEREncOpenType
0x1800315c3  test    eax, eax
0x1800315c5  jz      loc_180031651
0x1800315cb  mov     edx, [rsp+28h+arg_8]
0x1800315cf  mov     rcx, rbx
0x1800315d2  call    cs:__imp_ASN1BEREncEndOfContents
0x1800315d8  test    eax, eax
0x1800315da  jz      short loc_180031651
0x1800315dc  lea     r8, [rsp+28h+arg_8]
0x1800315e1  mov     [rsp+28h+arg_8], 0
0x1800315e9  mov     edx, ebp
0x1800315eb  mov     rcx, rbx
0x1800315ee  call    cs:__imp_ASN1BEREncExplicitTag
0x1800315f4  test    eax, eax
0x1800315f6  jz      short loc_180031651
0x1800315f8  lea     r8, [rdi+58h]
0x1800315fc  mov     rcx, rbx
0x1800315ff  call    ASN1Enc_AlgorithmIdentifier
0x180031604  test    eax, eax
0x180031606  jz      short loc_180031651
0x180031608  mov     r9, [rdi+0B8h]
0x18003160f  mov     edx, 4
0x180031614  mov     r8d, [rdi+0B0h]
0x18003161b  mov     rcx, rbx
0x18003161e  call    cs:__imp_ASN1BEREncOctetString
0x180031624  test    eax, eax
0x180031626  jz      short loc_180031651
0x180031628  mov     edx, [rsp+28h+arg_8]
0x18003162c  mov     rcx, rbx
0x18003162f  call    cs:__imp_ASN1BEREncEndOfContents
0x180031635  test    eax, eax
0x180031637  jz      short loc_180031651
0x180031639  mov     edx, [rsp+28h+arg_18]
0x18003163d  mov     rcx, rbx
0x180031640  call    cs:__imp_ASN1BEREncEndOfContents
0x180031646  xor     ecx, ecx
0x180031648  test    eax, eax
0x18003164a  setnz   cl
0x18003164d  mov     eax, ecx
0x18003164f  jmp     short loc_180031653
0x180031651  xor     eax, eax
0x180031653  mov     rbx, [rsp+28h+arg_0]
0x180031658  mov     rbp, [rsp+28h+arg_10]
0x18003165d  add     rsp, 20h
0x180031661  pop     rdi
0x180031662  retn
```
