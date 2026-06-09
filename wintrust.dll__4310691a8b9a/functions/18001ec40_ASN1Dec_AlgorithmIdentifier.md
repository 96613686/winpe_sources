# ASN1Dec_AlgorithmIdentifier

- ea: `0x18001ec40`
- end: `0x18001ecf2`
- name: `ASN1Dec_AlgorithmIdentifier`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800306c0`

## callees

- `0x18001ec40`

## import_xrefs

- `MSASN1!ASN1BERDecOpenType2` at `0x18001ecbd`
- `MSASN1!ASN1BERDecOpenType2` at `0x18001ecbd`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18001ec79`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18001ec79`
- `MSASN1!ASN1BERDecPeekTag` at `0x18001eca7`
- `MSASN1!ASN1BERDecPeekTag` at `0x18001eca7`
- `MSASN1!ASN1BERDecObjectIdentifier2` at `0x18001ec93`
- `MSASN1!ASN1BERDecObjectIdentifier2` at `0x18001ec93`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18001ecd4`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18001ecd4`

## pseudocode

```c
_BOOL8 __fastcall ASN1Dec_AlgorithmIdentifier(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 v5; // rcx
  __int64 v6; // rcx
  _QWORD v8[3]; // [rsp+20h] [rbp-18h] BYREF
  int v9; // [rsp+48h] [rbp+10h] BYREF
  __int64 v10; // [rsp+58h] [rbp+20h] BYREF

  v10 = 0;
  v8[0] = 0;
  v9 = 0;
  if ( (unsigned int)ASN1BERDecExplicitTag(a1, 16, &v10, v8)
    && (v5 = v10, *a3 = 0, (unsigned int)ASN1BERDecObjectIdentifier2(v5, 6, a3 + 4))
    && (!(unsigned int)ASN1BERDecPeekTag(v10, &v9)
     || (v6 = v10, *a3 |= 0x80u, (unsigned int)ASN1BERDecOpenType2(v6, a3 + 72))) )
  {
    return (unsigned int)ASN1BERDecEndOfContents(a1, v10, v8[0]) != 0;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x18001ec40  mov     rax, rsp
0x18001ec43  mov     [rax+8], rbx
0x18001ec47  mov     [rax+10h], edx
0x18001ec4a  push    rdi
0x18001ec4b  sub     rsp, 30h
0x18001ec4f  mov     rbx, r8
0x18001ec52  mov     qword ptr [rax+20h], 0
0x18001ec5a  lea     r8, [rax+20h]
0x18001ec5e  mov     qword ptr [rax-18h], 0
0x18001ec66  lea     r9, [rax-18h]
0x18001ec6a  mov     dword ptr [rax+10h], 0
0x18001ec71  mov     edx, 10h
0x18001ec76  mov     rdi, rcx
0x18001ec79  call    cs:__imp_ASN1BERDecExplicitTag
0x18001ec7f  test    eax, eax
0x18001ec81  jz      short loc_18001ECEE
0x18001ec83  mov     rcx, [rsp+38h+arg_18]
0x18001ec88  lea     r8, [rbx+4]
0x18001ec8c  xor     eax, eax
0x18001ec8e  mov     [rbx], al
0x18001ec90  lea     edx, [rax+6]
0x18001ec93  call    cs:__imp_ASN1BERDecObjectIdentifier2
0x18001ec99  test    eax, eax
0x18001ec9b  jz      short loc_18001ECEE
0x18001ec9d  mov     rcx, [rsp+38h+arg_18]
0x18001eca2  lea     rdx, [rsp+38h+arg_8]
0x18001eca7  call    cs:__imp_ASN1BERDecPeekTag
0x18001ecad  test    eax, eax
0x18001ecaf  jz      short loc_18001ECC7
0x18001ecb1  mov     rcx, [rsp+38h+arg_18]
0x18001ecb6  lea     rdx, [rbx+48h]
0x18001ecba  or      byte ptr [rbx], 80h
0x18001ecbd  call    cs:__imp_ASN1BERDecOpenType2
0x18001ecc3  test    eax, eax
0x18001ecc5  jz      short loc_18001ECEE
0x18001ecc7  mov     r8, [rsp+38h+var_18]
0x18001eccc  mov     rcx, rdi
0x18001eccf  mov     rdx, [rsp+38h+arg_18]
0x18001ecd4  call    cs:__imp_ASN1BERDecEndOfContents
0x18001ecda  xor     ecx, ecx
0x18001ecdc  test    eax, eax
0x18001ecde  setnz   cl
0x18001ece1  mov     eax, ecx
0x18001ece3  mov     rbx, [rsp+38h+arg_0]
0x18001ece8  add     rsp, 30h
0x18001ecec  pop     rdi
0x18001eced  retn
0x18001ecee  xor     eax, eax
0x18001ecf0  jmp     short loc_18001ECE3
```
