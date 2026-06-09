# PFPathIsUnderTempDir

- ea: `0x1400014a0`
- end: `0x140001551`
- name: `PFPathIsUnderTempDir`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400098a8`

## callees

- `0x1400014a0`
- `0x1400018f4`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140001513`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140001531`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140001513`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140001531`

## pseudocode

```c
char __fastcall PFPathIsUnderTempDir(__int64 a1)
{
  char v1; // bl
  UNICODE_STRING String1; // [rsp+20h] [rbp-40h] BYREF
  UNICODE_STRING v4; // [rsp+30h] [rbp-30h] BYREF
  __int128 v5; // [rsp+40h] [rbp-20h] BYREF
  __int128 v6; // [rsp+50h] [rbp-10h] BYREF

  v5 = 0;
  String1 = 0;
  v4 = 0;
  v6 = 0;
  ParsePathElement(a1, &v5, &String1);
  ParsePathElement(&String1, &v5, &String1);
  ParsePathElement(&String1, &String1, &v4);
  ParsePathElement(&v4, &v4, &v6);
  v1 = 1;
  if ( RtlCompareUnicodeString(&String1, &String2, 1u) || RtlCompareUnicodeString(&v4, &stru_140006010, 1u) )
    return 0;
  return v1;
}

```

## disassembly

```asm
0x1400014a0  mov     [rsp-8+arg_0], rbx
0x1400014a5  push    rbp
0x1400014a6  mov     rbp, rsp
0x1400014a9  sub     rsp, 60h
0x1400014ad  xorps   xmm0, xmm0
0x1400014b0  lea     r8, [rbp+String1]
0x1400014b4  xorps   xmm1, xmm1
0x1400014b7  lea     rdx, [rbp+var_20]
0x1400014bb  movups  [rbp+var_20], xmm0
0x1400014bf  movups  xmmword ptr [rbp+String1.Length], xmm1
0x1400014c3  movups  xmmword ptr [rbp+var_30.Length], xmm0
0x1400014c7  movups  [rbp+var_10], xmm1
0x1400014cb  call    ParsePathElement
0x1400014d0  lea     rdx, [rbp+var_20]
0x1400014d4  lea     rcx, [rbp+String1]
0x1400014d8  lea     r8, [rbp+String1]
0x1400014dc  call    ParsePathElement
0x1400014e1  lea     rdx, [rbp+String1]
0x1400014e5  lea     rcx, [rbp+String1]
0x1400014e9  lea     r8, [rbp+var_30]
0x1400014ed  call    ParsePathElement
0x1400014f2  lea     rdx, [rbp+var_30]
0x1400014f6  lea     rcx, [rbp+var_30]
0x1400014fa  lea     r8, [rbp+var_10]
0x1400014fe  call    ParsePathElement
0x140001503  mov     bl, 1
0x140001505  lea     rdx, String2; String2
0x14000150c  mov     r8b, bl; CaseInSensitive
0x14000150f  lea     rcx, [rbp+String1]; String1
0x140001513  call    cs:__imp_RtlCompareUnicodeString
0x14000151a  nop     dword ptr [rax+rax+00h]
0x14000151f  test    eax, eax
0x140001521  jnz     short loc_140001541
0x140001523  mov     r8b, bl; CaseInSensitive
0x140001526  lea     rdx, stru_140006010; String2
0x14000152d  lea     rcx, [rbp+var_30]; String1
0x140001531  call    cs:__imp_RtlCompareUnicodeString
0x140001538  nop     dword ptr [rax+rax+00h]
0x14000153d  test    eax, eax
0x14000153f  jz      short loc_140001543
0x140001541  xor     bl, bl
0x140001543  mov     al, bl
0x140001545  mov     rbx, [rsp+60h+arg_0]
0x14000154a  add     rsp, 60h
0x14000154e  pop     rbp
0x14000154f  retn
```
