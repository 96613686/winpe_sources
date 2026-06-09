# SvcXportDelete

- ea: `0x140055720`
- end: `0x140055970`
- name: `SvcXportDelete`
- size: `592`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140011cb8`
- `0x140025760`

## callees

- `0x14000d1b0`
- `0x140043440`
- `0x140054c20`
- `0x140055720`

## import_xrefs

- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x1400558a2`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x1400558a2`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140055948`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140055948`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400557b7`
- `ntoskrnl!RtlInitUnicodeString` at `0x140055802`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400557b7`
- `ntoskrnl!RtlInitUnicodeString` at `0x140055802`

## pseudocode

```c
__int64 __fastcall SvcXportDelete(__int64 a1, __int64 a2, unsigned __int64 a3, unsigned int a4)
{
  int v6; // ebx
  __int64 v7; // rax
  const wchar_t *v8; // rcx
  __int64 v9; // rdi
  unsigned __int64 v10; // rsi
  __int64 v11; // rax
  unsigned __int64 v12; // rcx
  __int64 v13; // rax
  CHAR *v14; // rcx
  __int64 v15; // rax
  char v16; // di
  USHORT Length; // r9
  USHORT v18; // ax
  struct _UNICODE_STRING *p_DestinationString; // rdx
  struct _UNICODE_STRING *p_UnicodeString; // rcx
  struct _UNICODE_STRING *v21; // r8
  struct _UNICODE_STRING *v22; // rdx
  struct _UNICODE_STRING *v23; // rcx
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF
  struct _STRING SourceString; // [rsp+40h] [rbp-28h] BYREF
  struct _UNICODE_STRING v28; // [rsp+50h] [rbp-18h] BYREF

  DestinationString = 0;
  SourceString = 0;
  v28 = 0;
  UnicodeString = 0;
  if ( a4 < 0x138 )
    goto LABEL_2;
  v7 = *(_QWORD *)(a3 + 8);
  if ( v7 )
  {
    v8 = (const wchar_t *)(v7 + a3);
    *(_QWORD *)(a3 + 8) = v7 + a3;
    if ( v7 + a3 )
    {
      if ( (unsigned __int64)v8 <= a3 )
        goto LABEL_7;
      v9 = a4;
      if ( (unsigned __int64)v8 >= a4 + a3 )
        goto LABEL_7;
      goto LABEL_10;
    }
  }
  else
  {
    v8 = 0;
  }
  v9 = a4;
LABEL_10:
  v10 = v9 + a3;
  if ( RtlStringCbLengthW(v8, v9 + a3 - (_QWORD)v8, 0) < 0 )
    goto LABEL_2;
  RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(a3 + 8));
  v11 = *(_QWORD *)(a3 + 40);
  if ( !v11 )
    goto LABEL_17;
  v12 = v11 + a3;
  *(_QWORD *)(a3 + 40) = v11 + a3;
  if ( v11 + a3 && (v12 <= a3 || v12 >= v10) )
  {
LABEL_7:
    v6 = -1073741819;
    goto LABEL_53;
  }
  if ( RtlStringCbLengthW((STRSAFE_PCNZWCH)(v11 + a3), v9 - v11, 0) < 0 )
  {
LABEL_2:
    v6 = -1073741811;
LABEL_53:
    *(_DWORD *)(a2 + 68) = 2140;
    return (unsigned int)v6;
  }
  RtlInitUnicodeString(&v28, *(PCWSTR *)(a3 + 40));
LABEL_17:
  v13 = *(_QWORD *)(a3 + 16);
  if ( v13 )
  {
    v14 = (CHAR *)(v13 + a3);
    *(_QWORD *)(a3 + 16) = v13 + a3;
    if ( v13 + a3 && ((unsigned __int64)v14 <= a3 || (unsigned __int64)v14 >= v10) )
      goto LABEL_7;
    v15 = *(unsigned int *)(a3 + 24);
    if ( (unsigned int)v15 > 0xFFFF || (unsigned __int64)&v14[v15] > v10 )
      goto LABEL_7;
  }
  else
  {
    v14 = 0;
  }
  v16 = 0;
  if ( !*(_DWORD *)(a3 + 24) || !v14 )
    goto LABEL_32;
  if ( (*(_DWORD *)(a3 + 48) & 0x20) == 0 )
  {
    v18 = *(_WORD *)(a3 + 24);
    SourceString.Buffer = v14;
    SourceString.Length = v18;
    SourceString.MaximumLength = v18;
    v6 = RtlAnsiStringToUnicodeString(&UnicodeString, &SourceString, 1u);
    if ( v6 < 0 )
      goto LABEL_53;
    v16 = 1;
LABEL_32:
    Length = UnicodeString.Length;
    goto LABEL_33;
  }
  Length = *(_WORD *)(a3 + 24);
  UnicodeString.Buffer = (PWSTR)v14;
  UnicodeString.Length = Length;
  UnicodeString.MaximumLength = Length;
  if ( (Length & 1) != 0 )
    goto LABEL_2;
LABEL_33:
  if ( DestinationString.Buffer )
  {
    if ( *(_DWORD *)(a2 + 64) >= 2u )
    {
      p_DestinationString = &DestinationString;
      p_UnicodeString = &UnicodeString;
      if ( !DestinationString.Length )
        p_DestinationString = 0;
      if ( !Length )
        p_UnicodeString = 0;
      SrvNetSetEndpointFlag(p_UnicodeString, p_DestinationString, 0);
      Length = UnicodeString.Length;
    }
    v21 = &DestinationString;
    v22 = &v28;
    if ( !DestinationString.Length )
      v21 = 0;
    v23 = &UnicodeString;
    if ( !v28.Length )
      v22 = 0;
    if ( !Length )
      v23 = 0;
    v6 = SrvNetDeleteServedName(&v23->Length, &v22->Length, v21);
    if ( v6 == -1073741772 )
    {
      *(_DWORD *)(a2 + 68) = 2310;
      v6 = 0;
    }
    else
    {
      *(_DWORD *)(a2 + 68) = 0;
    }
  }
  else
  {
    v6 = -1073741811;
  }
  if ( v16 )
    RtlFreeUnicodeString(&UnicodeString);
  if ( v6 < 0 )
    goto LABEL_53;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140055720  push    rbp
0x140055722  push    rbx
0x140055723  push    rsi
0x140055724  push    rdi
0x140055725  push    r14
0x140055727  push    r15
0x140055729  mov     rbp, rsp
0x14005572c  sub     rsp, 68h
0x140055730  xorps   xmm0, xmm0
0x140055733  xorps   xmm1, xmm1
0x140055736  mov     rbx, r8
0x140055739  mov     r14, rdx
0x14005573c  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140055740  movups  xmmword ptr [rbp+SourceString.Length], xmm1
0x140055744  movups  xmmword ptr [rbp+var_18.Length], xmm0
0x140055748  movups  xmmword ptr [rbp+UnicodeString.Length], xmm1
0x14005574c  cmp     r9d, 138h
0x140055753  jnb     short loc_14005575F
0x140055755  mov     ebx, 0C000000Dh
0x14005575a  jmp     loc_140055958
0x14005575f  mov     rax, [r8+8]
0x140055763  xor     r15d, r15d
0x140055766  test    rax, rax
0x140055769  jz      short loc_140055793
0x14005576b  lea     rcx, [rax+r8]
0x14005576f  mov     [r8+8], rcx
0x140055773  test    rcx, rcx
0x140055776  jz      short loc_140055796
0x140055778  cmp     rcx, rbx
0x14005577b  jbe     short loc_140055789
0x14005577d  mov     edi, r9d
0x140055780  lea     rax, [rdi+r8]
0x140055784  cmp     rcx, rax
0x140055787  jb      short loc_140055799
0x140055789  mov     ebx, 0C0000005h
0x14005578e  jmp     loc_140055958
0x140055793  mov     rcx, r15; psz
0x140055796  mov     edi, r9d
0x140055799  lea     rsi, [rdi+r8]
0x14005579d  xor     r8d, r8d; pcbLength
0x1400557a0  mov     rdx, rsi
0x1400557a3  sub     rdx, rcx; cbMax
0x1400557a6  call    RtlStringCbLengthW
0x1400557ab  test    eax, eax
0x1400557ad  js      short loc_140055755
0x1400557af  mov     rdx, [rbx+8]; SourceString
0x1400557b3  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400557b7  call    cs:__imp_RtlInitUnicodeString
0x1400557be  nop     dword ptr [rax+rax+00h]
0x1400557c3  mov     rax, [rbx+28h]
0x1400557c7  test    rax, rax
0x1400557ca  jz      short loc_14005580E
0x1400557cc  lea     rcx, [rax+rbx]; psz
0x1400557d0  mov     [rbx+28h], rcx
0x1400557d4  test    rcx, rcx
0x1400557d7  jz      short loc_1400557E3
0x1400557d9  cmp     rcx, rbx
0x1400557dc  jbe     short loc_140055789
0x1400557de  cmp     rcx, rsi
0x1400557e1  jnb     short loc_140055789
0x1400557e3  sub     rdi, rcx
0x1400557e6  xor     r8d, r8d; pcbLength
0x1400557e9  lea     rdx, [rbx+rdi]; cbMax
0x1400557ed  call    RtlStringCbLengthW
0x1400557f2  test    eax, eax
0x1400557f4  js      loc_140055755
0x1400557fa  mov     rdx, [rbx+28h]; SourceString
0x1400557fe  lea     rcx, [rbp+var_18]; DestinationString
0x140055802  call    cs:__imp_RtlInitUnicodeString
0x140055809  nop     dword ptr [rax+rax+00h]
0x14005580e  mov     rax, [rbx+10h]
0x140055812  test    rax, rax
0x140055815  jz      short loc_140055851
0x140055817  lea     rcx, [rax+rbx]
0x14005581b  mov     [rbx+10h], rcx
0x14005581f  test    rcx, rcx
0x140055822  jz      short loc_140055836
0x140055824  cmp     rcx, rbx
0x140055827  jbe     loc_140055789
0x14005582d  cmp     rcx, rsi
0x140055830  jnb     loc_140055789
0x140055836  mov     eax, [rbx+18h]
0x140055839  cmp     eax, 0FFFFh
0x14005583e  ja      loc_140055789
0x140055844  add     rax, rcx
0x140055847  cmp     rax, rsi
0x14005584a  jbe     short loc_140055854
0x14005584c  jmp     loc_140055789
0x140055851  mov     rcx, r15
0x140055854  mov     dil, r15b
0x140055857  cmp     [rbx+18h], r15d
0x14005585b  jbe     short loc_1400558BB
0x14005585d  test    rcx, rcx
0x140055860  jz      short loc_1400558BB
0x140055862  mov     eax, [rbx+30h]
0x140055865  test    al, 20h
0x140055867  jz      short loc_140055887
0x140055869  movzx   r9d, word ptr [rbx+18h]
0x14005586e  mov     [rbp+UnicodeString.Buffer], rcx
0x140055872  mov     [rbp+UnicodeString.Length], r9w
0x140055877  mov     [rbp+UnicodeString.MaximumLength], r9w
0x14005587c  test    r9b, 1
0x140055880  jz      short loc_1400558C0
0x140055882  jmp     loc_140055755
0x140055887  movzx   eax, word ptr [rbx+18h]
0x14005588b  lea     rdx, [rbp+SourceString]; SourceString
0x14005588f  mov     [rbp+SourceString.Buffer], rcx
0x140055893  mov     r8b, 1; AllocateDestinationString
0x140055896  lea     rcx, [rbp+UnicodeString]; DestinationString
0x14005589a  mov     [rbp+SourceString.Length], ax
0x14005589e  mov     [rbp+SourceString.MaximumLength], ax
0x1400558a2  call    cs:__imp_RtlAnsiStringToUnicodeString
0x1400558a9  nop     dword ptr [rax+rax+00h]
0x1400558ae  mov     ebx, eax
0x1400558b0  test    eax, eax
0x1400558b2  js      loc_140055958
0x1400558b8  mov     dil, 1
0x1400558bb  movzx   r9d, [rbp+UnicodeString.Length]
0x1400558c0  cmp     [rbp+DestinationString.Buffer], r15
0x1400558c4  jnz     short loc_1400558CD
0x1400558c6  mov     ebx, 0C000000Dh
0x1400558cb  jmp     short loc_14005593F
0x1400558cd  cmp     dword ptr [r14+40h], 2
0x1400558d2  jb      short loc_1400558FA
0x1400558d4  cmp     [rbp+DestinationString.Length], r15w
0x1400558d9  lea     rdx, [rbp+DestinationString]
0x1400558dd  lea     rcx, [rbp+UnicodeString]
0x1400558e1  cmovbe  rdx, r15
0x1400558e5  test    r9w, r9w
0x1400558e9  cmovz   rcx, r15
0x1400558ed  xor     r8d, r8d
0x1400558f0  call    SrvNetSetEndpointFlag
0x1400558f5  movzx   r9d, [rbp+UnicodeString.Length]
0x1400558fa  cmp     [rbp+DestinationString.Length], r15w
0x1400558ff  lea     r8, [rbp+DestinationString]
0x140055903  lea     rdx, [rbp+var_18]
0x140055907  cmovbe  r8, r15
0x14005590b  lea     rcx, [rbp+UnicodeString]
0x14005590f  cmp     [rbp+var_18.Length], r15w
0x140055914  cmovbe  rdx, r15
0x140055918  test    r9w, r9w
0x14005591c  cmovz   rcx, r15
0x140055920  call    SrvNetDeleteServedName
0x140055925  mov     ebx, eax
0x140055927  cmp     eax, 0C0000034h
0x14005592c  jnz     short loc_14005593B
0x14005592e  mov     dword ptr [r14+44h], 906h
0x140055936  mov     ebx, r15d
0x140055939  jmp     short loc_14005593F
0x14005593b  mov     [r14+44h], r15d
0x14005593f  test    dil, dil
0x140055942  jz      short loc_140055954
0x140055944  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x140055948  call    cs:__imp_RtlFreeUnicodeString
0x14005594f  nop     dword ptr [rax+rax+00h]
0x140055954  test    ebx, ebx
0x140055956  jns     short loc_140055960
0x140055958  mov     dword ptr [r14+44h], 85Ch
0x140055960  mov     eax, ebx
0x140055962  add     rsp, 68h
0x140055966  pop     r15
0x140055968  pop     r14
0x14005596a  pop     rdi
0x14005596b  pop     rsi
0x14005596c  pop     rbx
0x14005596d  pop     rbp
0x14005596e  retn
```
