# ASN1Enc_AlgorithmIdentifier

- ea: `0x180030df8`
- end: `0x180030e78`
- name: `ASN1Enc_AlgorithmIdentifier`
- size: `128`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180031210`
- `0x180031540`

## callees

- `0x180030df8`

## import_xrefs

- `MSASN1!ASN1BEREncOpenType` at `0x180030e49`
- `MSASN1!ASN1BEREncOpenType` at `0x180030e49`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180030e5a`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180030e5a`
- `MSASN1!ASN1BEREncObjectIdentifier2` at `0x180030e33`
- `MSASN1!ASN1BEREncObjectIdentifier2` at `0x180030e33`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180030e1d`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180030e1d`

## pseudocode

```c
_BOOL8 __fastcall ASN1Enc_AlgorithmIdentifier(__int64 a1, __int64 a2, char *a3)
{
  unsigned int v6; // [rsp+38h] [rbp+10h] BYREF

  v6 = 0;
  return (unsigned int)ASN1BEREncExplicitTag(a1, 16, &v6)
      && (unsigned int)ASN1BEREncObjectIdentifier2(a1, 6, a3 + 4)
      && (*a3 >= 0 || (unsigned int)ASN1BEREncOpenType(a1, a3 + 72))
      && (unsigned int)ASN1BEREncEndOfContents(a1, v6) != 0;
}

```

## disassembly

```asm
0x180030df8  mov     rax, rsp
0x180030dfb  mov     [rax+8], rbx
0x180030dff  mov     [rax+10h], edx
0x180030e02  push    rdi
0x180030e03  sub     rsp, 20h
0x180030e07  mov     rbx, r8
0x180030e0a  mov     dword ptr [rax+10h], 0
0x180030e11  lea     r8, [rax+10h]
0x180030e15  mov     edx, 10h
0x180030e1a  mov     rdi, rcx
0x180030e1d  call    cs:__imp_ASN1BEREncExplicitTag
0x180030e23  test    eax, eax
0x180030e25  jz      short loc_180030E6B
0x180030e27  lea     r8, [rbx+4]
0x180030e2b  mov     edx, 6
0x180030e30  mov     rcx, rdi
0x180030e33  call    cs:__imp_ASN1BEREncObjectIdentifier2
0x180030e39  test    eax, eax
0x180030e3b  jz      short loc_180030E6B
0x180030e3d  cmp     byte ptr [rbx], 0
0x180030e40  jge     short loc_180030E53
0x180030e42  lea     rdx, [rbx+48h]
0x180030e46  mov     rcx, rdi
0x180030e49  call    cs:__imp_ASN1BEREncOpenType
0x180030e4f  test    eax, eax
0x180030e51  jz      short loc_180030E6B
0x180030e53  mov     edx, [rsp+28h+arg_8]
0x180030e57  mov     rcx, rdi
0x180030e5a  call    cs:__imp_ASN1BEREncEndOfContents
0x180030e60  xor     ecx, ecx
0x180030e62  test    eax, eax
0x180030e64  setnz   cl
0x180030e67  mov     eax, ecx
0x180030e69  jmp     short loc_180030E6D
0x180030e6b  xor     eax, eax
0x180030e6d  mov     rbx, [rsp+28h+arg_0]
0x180030e72  add     rsp, 20h
0x180030e76  pop     rdi
0x180030e77  retn
```
