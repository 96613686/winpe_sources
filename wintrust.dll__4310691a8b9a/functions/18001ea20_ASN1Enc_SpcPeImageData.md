# ASN1Enc_SpcPeImageData

- ea: `0x18001ea20`
- end: `0x18001eb35`
- name: `ASN1Enc_SpcPeImageData`
- size: `277`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001ea20`
- `0x18001eb40`

## import_xrefs

- `MSASN1!ASN1BEREncRemoveZeroBits` at `0x18001eaa7`
- `MSASN1!ASN1BEREncRemoveZeroBits` at `0x18001eaa7`
- `MSASN1!ASN1bitstring_cmp` at `0x18001ea7f`
- `MSASN1!ASN1bitstring_cmp` at `0x18001ea7f`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18001eafe`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18001eb0f`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18001eafe`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18001eb0f`
- `MSASN1!ASN1BEREncBitString` at `0x18001eabe`
- `MSASN1!ASN1BEREncBitString` at `0x18001eabe`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18001ea5d`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18001eadb`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18001ea5d`
- `MSASN1!ASN1BEREncExplicitTag` at `0x18001eadb`

## pseudocode

```c
_BOOL8 __fastcall ASN1Enc_SpcPeImageData(__int64 a1, __int64 a2, __int64 a3)
{
  char v5; // bl
  char v6; // bp
  __int64 v7; // rdx
  _DWORD v9[10]; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v10; // [rsp+58h] [rbp+10h] BYREF
  unsigned int v11; // [rsp+68h] [rbp+20h] BYREF

  v9[0] = 0;
  v10 = 0;
  v11 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  if ( !(unsigned int)ASN1BEREncExplicitTag(a1, a2, v9) )
    return 0;
  v5 = *(_BYTE *)a3;
  v6 = *(_BYTE *)a3 & 0x7F;
  if ( (unsigned int)ASN1bitstring_cmp(a3 + 8, &SpcPeImageData_flags_default, 1) )
    v6 = v5;
  if ( (v6 >= 0
     || (v7 = *(_QWORD *)(a3 + 16),
         v10 = *(_DWORD *)(a3 + 8),
         ASN1BEREncRemoveZeroBits(&v10, v7),
         (unsigned int)ASN1BEREncBitString(a1, 3, v10, *(_QWORD *)(a3 + 16))))
    && ((v6 & 0x40) == 0
     || (unsigned int)ASN1BEREncExplicitTag(a1, 0x80000000LL, &v11)
     && (unsigned int)ASN1Enc_SpcLink(a1, 0, a3 + 24)
     && (unsigned int)ASN1BEREncEndOfContents(a1, v11)) )
  {
    return (unsigned int)ASN1BEREncEndOfContents(a1, v9[0]) != 0;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x18001ea20  mov     rax, rsp
0x18001ea23  mov     [rax+8], rbx
0x18001ea27  mov     [rax+18h], rbp
0x18001ea2b  push    rsi
0x18001ea2c  push    rdi
0x18001ea2d  push    r14
0x18001ea2f  sub     rsp, 30h
0x18001ea33  mov     dword ptr [rax-28h], 0
0x18001ea3a  test    edx, edx
0x18001ea3c  mov     dword ptr [rax+10h], 0
0x18001ea43  mov     rsi, r8
0x18001ea46  mov     dword ptr [rax+20h], 0
0x18001ea4d  lea     r8, [rsp+48h+var_28]
0x18001ea52  mov     eax, 10h
0x18001ea57  mov     rdi, rcx
0x18001ea5a  cmovz   edx, eax
0x18001ea5d  call    cs:__imp_ASN1BEREncExplicitTag
0x18001ea63  test    eax, eax
0x18001ea65  jz      loc_18001EB31
0x18001ea6b  movzx   ebx, byte ptr [rsi]
0x18001ea6e  lea     rdx, SpcPeImageData_flags_default
0x18001ea75  mov     r8d, 1
0x18001ea7b  lea     rcx, [rsi+8]
0x18001ea7f  call    cs:__imp_ASN1bitstring_cmp
0x18001ea85  mov     cl, bl
0x18001ea87  and     cl, 7Fh
0x18001ea8a  test    eax, eax
0x18001ea8c  movzx   ebp, cl
0x18001ea8f  cmovnz  ebp, ebx
0x18001ea92  test    bpl, bpl
0x18001ea95  jns     short loc_18001EAC8
0x18001ea97  mov     eax, [rsi+8]
0x18001ea9a  lea     rcx, [rsp+48h+arg_8]
0x18001ea9f  mov     rdx, [rsi+10h]
0x18001eaa3  mov     [rsp+48h+arg_8], eax
0x18001eaa7  call    cs:__imp_ASN1BEREncRemoveZeroBits
0x18001eaad  mov     r9, [rsi+10h]
0x18001eab1  mov     edx, 3
0x18001eab6  mov     r8d, [rsp+48h+arg_8]
0x18001eabb  mov     rcx, rdi
0x18001eabe  call    cs:__imp_ASN1BEREncBitString
0x18001eac4  test    eax, eax
0x18001eac6  jz      short loc_18001EB31
0x18001eac8  test    bpl, 40h
0x18001eacc  jz      short loc_18001EB08
0x18001eace  lea     r8, [rsp+48h+arg_18]
0x18001ead3  mov     edx, 80000000h
0x18001ead8  mov     rcx, rdi
0x18001eadb  call    cs:__imp_ASN1BEREncExplicitTag
0x18001eae1  test    eax, eax
0x18001eae3  jz      short loc_18001EB31
0x18001eae5  lea     r8, [rsi+18h]
0x18001eae9  xor     edx, edx
0x18001eaeb  mov     rcx, rdi
0x18001eaee  call    ASN1Enc_SpcLink
0x18001eaf3  test    eax, eax
0x18001eaf5  jz      short loc_18001EB31
0x18001eaf7  mov     edx, [rsp+48h+arg_18]
0x18001eafb  mov     rcx, rdi
0x18001eafe  call    cs:__imp_ASN1BEREncEndOfContents
0x18001eb04  test    eax, eax
0x18001eb06  jz      short loc_18001EB31
0x18001eb08  mov     edx, [rsp+48h+var_28]
0x18001eb0c  mov     rcx, rdi
0x18001eb0f  call    cs:__imp_ASN1BEREncEndOfContents
0x18001eb15  xor     ecx, ecx
0x18001eb17  test    eax, eax
0x18001eb19  setnz   cl
0x18001eb1c  mov     eax, ecx
0x18001eb1e  mov     rbx, [rsp+48h+arg_0]
0x18001eb23  mov     rbp, [rsp+48h+arg_10]
0x18001eb28  add     rsp, 30h
0x18001eb2c  pop     r14
0x18001eb2e  pop     rdi
0x18001eb2f  pop     rsi
0x18001eb30  retn
0x18001eb31  xor     eax, eax
0x18001eb33  jmp     short loc_18001EB1E
```
