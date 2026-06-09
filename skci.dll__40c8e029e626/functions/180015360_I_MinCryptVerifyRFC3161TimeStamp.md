# I_MinCryptVerifyRFC3161TimeStamp

- ea: `0x180015360`
- end: `0x1800154dd`
- name: `I_MinCryptVerifyRFC3161TimeStamp`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180014f60`

## callees

- `0x180014614`
- `0x180015360`
- `0x180015624`
- `0x180033980`
- `0x18004cfb4`
- `0x18004d8cc`
- `0x18004f3e8`

## import_xrefs

- `securekernel!RtlCompareMemory` at `0x18001540b`
- `securekernel!RtlCompareMemory` at `0x18001547f`
- `securekernel!RtlCompareMemory` at `0x18001540b`
- `securekernel!RtlCompareMemory` at `0x18001547f`

## pseudocode

```c
__int64 __fastcall I_MinCryptVerifyRFC3161TimeStamp(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        _DWORD *a5,
        _QWORD *a6,
        unsigned int *a7)
{
  int v7; // edx
  __int64 v8; // rcx
  unsigned int v10; // esi
  int v11; // edi
  __int64 v12; // rbx
  SIZE_T Length[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v15[48]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v16[16]; // [rsp+90h] [rbp-70h] BYREF
  int v17; // [rsp+A0h] [rbp-60h]
  void *v18; // [rsp+A8h] [rbp-58h]
  _BYTE v19[16]; // [rsp+B0h] [rbp-50h] BYREF
  int v20; // [rsp+C0h] [rbp-40h] BYREF
  void *Source2; // [rsp+C8h] [rbp-38h]
  _BYTE v22[64]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE Source1[64]; // [rsp+110h] [rbp+10h] BYREF

  v7 = *(_DWORD *)a1;
  v8 = *(_QWORD *)(a1 + 8);
  LODWORD(Length[0]) = 0;
  if ( (int)MinCrypK_VerifySignedDataKModeEx(v8, v7, 0, 0, (__int64)&qword_1800524F0, a4, &v20, 0, 0) < 0 )
  {
    *a5 |= 0x40000u;
    return (unsigned int)-1073740760;
  }
  if ( v20 != 11
    || RtlCompareMemory(qword_1800522B8, Source2, 0xBu) != 11
    || (int)MinAsn1ParseRfc3161TimeStampToken(v22, v15) < 0 )
  {
    *a5 |= 0x50000u;
    return (unsigned int)-1073740760;
  }
  v10 = MinCryptDecodeHashAlgorithmIdentifier(v16);
  if ( !v10 )
    return (unsigned int)-1073740760;
  v11 = HashpHashMemory(v10, 1, a3 + 272, Source1, Length);
  if ( v11 >= 0 )
  {
    if ( LODWORD(Length[0]) != v17 )
      return (unsigned int)-1073740760;
    v12 = LODWORD(Length[0]);
    if ( RtlCompareMemory(Source1, v18, LODWORD(Length[0])) != v12 )
      return (unsigned int)-1073740760;
    if ( !(unsigned __int8)MinAsn1DecodeGeneralizedTime(v19, a6) )
      *a6 = 0;
    *a7 = v10;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180015360  mov     [rsp-8+arg_8], rbx
0x180015365  push    rbp
0x180015366  push    rsi
0x180015367  push    rdi
0x180015368  push    r14
0x18001536a  push    r15
0x18001536c  lea     rbp, [rsp-60h]
0x180015371  sub     rsp, 160h
0x180015378  mov     rax, cs:__security_cookie
0x18001537f  xor     rax, rsp
0x180015382  mov     [rbp+80h+var_30], rax
0x180015386  mov     edx, [rcx]; int
0x180015388  lea     rax, [rbp+80h+var_C0]
0x18001538c  mov     rcx, [rcx+8]; int
0x180015390  mov     rdi, r8
0x180015393  mov     r14, [rbp+80h+arg_28]
0x18001539a  xor     r8d, r8d; int
0x18001539d  mov     rbx, [rbp+80h+arg_20]
0x1800153a4  mov     r15, [rbp+80h+arg_30]
0x1800153ab  mov     [rsp+180h+var_140], 0; __int64
0x1800153b4  mov     [rsp+180h+var_148], 0; __int64
0x1800153bd  mov     [rsp+180h+var_150], rax; void *
0x1800153c2  lea     rax, qword_1800524F0
0x1800153c9  mov     qword ptr [rsp+180h+var_158], r9; int
0x1800153ce  xor     r9d, r9d; int
0x1800153d1  mov     [rsp+180h+var_160], rax; __int64
0x1800153d6  mov     dword ptr [rsp+180h+Length], 0
0x1800153de  call    MinCrypK_VerifySignedDataKModeEx
0x1800153e3  test    eax, eax
0x1800153e5  jns     short loc_1800153F0
0x1800153e7  bts     dword ptr [rbx], 12h
0x1800153eb  jmp     loc_1800154B2
0x1800153f0  cmp     [rbp+80h+var_C0], 0Bh
0x1800153f4  jnz     loc_1800154AC
0x1800153fa  mov     rdx, [rbp+80h+Source2]; Source2
0x1800153fe  lea     rcx, qword_1800522B8; Source1
0x180015405  mov     r8d, 0Bh; Length
0x18001540b  call    cs:__imp_RtlCompareMemory
0x180015412  nop     dword ptr [rax+rax+00h]
0x180015417  cmp     rax, 0Bh
0x18001541b  jnz     loc_1800154AC
0x180015421  lea     rdx, [rsp+180h+var_120]
0x180015426  lea     rcx, [rbp+80h+var_B0]
0x18001542a  call    MinAsn1ParseRfc3161TimeStampToken
0x18001542f  test    eax, eax
0x180015431  js      short loc_1800154AC
0x180015433  lea     rcx, [rbp+80h+var_F0]
0x180015437  call    MinCryptDecodeHashAlgorithmIdentifier
0x18001543c  mov     esi, eax
0x18001543e  test    eax, eax
0x180015440  jz      short loc_1800154B2
0x180015442  lea     rax, [rsp+180h+Length]
0x180015447  mov     edx, 1
0x18001544c  lea     r8, [rdi+110h]
0x180015453  mov     [rsp+180h+var_160], rax
0x180015458  lea     r9, [rbp+80h+Source1]
0x18001545c  mov     ecx, esi
0x18001545e  call    HashpHashMemory
0x180015463  mov     edi, eax
0x180015465  test    eax, eax
0x180015467  js      short loc_1800154B7
0x180015469  mov     eax, dword ptr [rsp+180h+Length]
0x18001546d  cmp     eax, [rbp+80h+var_E0]
0x180015470  jnz     short loc_1800154B2
0x180015472  mov     rdx, [rbp+80h+var_D8]; Source2
0x180015476  lea     rcx, [rbp+80h+Source1]; Source1
0x18001547a  mov     r8d, eax; Length
0x18001547d  mov     ebx, eax
0x18001547f  call    cs:__imp_RtlCompareMemory
0x180015486  nop     dword ptr [rax+rax+00h]
0x18001548b  cmp     rax, rbx
0x18001548e  jnz     short loc_1800154B2
0x180015490  mov     rdx, r14
0x180015493  lea     rcx, [rbp+80h+var_D0]
0x180015497  call    MinAsn1DecodeGeneralizedTime
0x18001549c  test    al, al
0x18001549e  jnz     short loc_1800154A7
0x1800154a0  mov     qword ptr [r14], 0
0x1800154a7  mov     [r15], esi
0x1800154aa  jmp     short loc_1800154B7
0x1800154ac  or      dword ptr [rbx], 50000h
0x1800154b2  mov     edi, 0C0000428h
0x1800154b7  mov     eax, edi
0x1800154b9  mov     rcx, [rbp+80h+var_30]
0x1800154bd  xor     rcx, rsp; StackCookie
0x1800154c0  call    __security_check_cookie
0x1800154c5  mov     rbx, [rsp+180h+arg_8]
0x1800154cd  add     rsp, 160h
0x1800154d4  pop     r15
0x1800154d6  pop     r14
0x1800154d8  pop     rdi
0x1800154d9  pop     rsi
0x1800154da  pop     rbp
0x1800154db  retn
```
