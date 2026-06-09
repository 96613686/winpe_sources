# RtlCalculateUtf16StringLengthFromLUtf8String

- ea: `0x180009150`
- end: `0x1800092d4`
- name: `RtlCalculateUtf16StringLengthFromLUtf8String`
- size: `388`
- prototype: `__int64 __fastcall(__int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180015b40`

## callees

- `0x1800054f0`
- `0x180007568`
- `0x180009150`
- `0x1800093c8`
- `0x180009500`

## string_xrefs

- `0x180009229`: `NewTempBytesRequired > TempBytesRequired`

## pseudocode

```c
__int64 __fastcall RtlCalculateUtf16StringLengthFromLUtf8String(__int64 a1, unsigned __int64 *a2)
{
  _QWORD *v3; // r8
  const char *v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rsi
  unsigned __int64 i; // rbx
  __int64 v8; // rax
  __int64 v9; // rdx
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rdx
  const char *v13; // [rsp+20h] [rbp-20h] BYREF
  const char *v14; // [rsp+28h] [rbp-18h]
  __int64 v15; // [rsp+30h] [rbp-10h]
  const char *v16; // [rsp+38h] [rbp-8h]

  if ( !a2 )
  {
    v15 = 1031;
    v13 = "onecore\\base\\lstring\\lutf8_string.cpp";
    v14 = "RtlCalculateUtf16StringLengthFromLUtf8String";
    v4 = "Not-null check failed: BytesRequired";
    goto LABEL_16;
  }
  *a2 = -1;
  if ( !(unsigned __int8)RtlIsLUtf8StringValid(a1, a2, a1) )
  {
    v15 = 1032;
    v13 = "onecore\\base\\lstring\\lutf8_string.cpp";
    v14 = "RtlCalculateUtf16StringLengthFromLUtf8String";
    v4 = "::RtlIsLUtf8StringValid(Source)";
LABEL_16:
    v16 = v4;
    RtlReportErrorOrigination(a1, a2, 3221225485LL);
    return 3221225485LL;
  }
  v5 = *(_QWORD *)(a1 + 16);
  v6 = v5 + *v3;
  for ( i = 0; ; i += v10 + 4 )
  {
    if ( v5 == v6 )
    {
      *a2 = i;
      return 0;
    }
    v8 = RtlDecodeUtf8(&v13, v5, v6);
    v5 = *(_QWORD *)(v8 + 8);
    if ( *(_DWORD *)v8 == -1 )
      break;
    if ( *(_DWORD *)v8 >= 0x110000u )
    {
      v15 = 1045;
      v13 = "onecore\\base\\lstring\\lutf8_string.cpp";
      v14 = "RtlCalculateUtf16StringLengthFromLUtf8String";
      v16 = "rv.UcsCharacter < 0x110000";
      RtlReportErrorOrigination(v5, v9, 3221225825LL);
      return 3221225825LL;
    }
    v10 = -(__int64)(*(_DWORD *)v8 < 0x10000u) & 0xFFFFFFFFFFFFFFFEuLL;
    v11 = i + v10 + 4;
    if ( v11 <= i )
    {
      v15 = 1047;
      v13 = "onecore\\base\\lstring\\lutf8_string.cpp";
      v14 = "RtlCalculateUtf16StringLengthFromLUtf8String";
      v16 = "NewTempBytesRequired > TempBytesRequired";
      RtlReportErrorOrigination(v5, v11, 3221225621LL);
      return 3221225621LL;
    }
  }
  if ( (int)v5 >= 0 )
    INTERNAL_ERROR_ACTION(-1073741595);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180009150  mov     [rsp-18h+arg_10], rbx
0x180009155  push    rbp
0x180009156  push    rsi
0x180009157  push    rdi
0x180009158  mov     rbp, rsp
0x18000915b  sub     rsp, 40h
0x18000915f  mov     rdi, rdx
0x180009162  mov     r8, rcx
0x180009165  test    rdx, rdx
0x180009168  jz      loc_180009283
0x18000916e  mov     qword ptr [rdx], 0FFFFFFFFFFFFFFFFh
0x180009175  call    RtlIsLUtf8StringValid
0x18000917a  test    al, al
0x18000917c  jnz     short loc_1800091A8
0x18000917e  lea     rax, aOnecoreBaseLst_3; "onecore\\base\\lstring\\lutf8_string.cp"...
0x180009185  mov     [rbp+var_10], 408h
0x18000918d  mov     [rbp+var_20], rax
0x180009191  lea     rax, aRtlcalculateut; "RtlCalculateUtf16StringLengthFromLUtf8S"...
0x180009198  mov     [rbp+var_18], rax
0x18000919c  lea     rax, aRtlislutf8stri; "::RtlIsLUtf8StringValid(Source)"
0x1800091a3  jmp     loc_1800092A8
0x1800091a8  mov     rcx, [rcx+10h]
0x1800091ac  mov     rsi, [r8]
0x1800091af  add     rsi, rcx
0x1800091b2  xor     ebx, ebx
0x1800091b4  jmp     short loc_1800091F6
0x1800091b6  mov     rdx, rcx
0x1800091b9  mov     r8, rsi
0x1800091bc  lea     rcx, [rbp+var_20]
0x1800091c0  call    RtlDecodeUtf8
0x1800091c5  cmp     dword ptr [rax], 0FFFFFFFFh
0x1800091c8  mov     rcx, [rax+8]
0x1800091cc  jz      loc_18000927B
0x1800091d2  cmp     dword ptr [rax], 110000h
0x1800091d8  jnb     short loc_180009240
0x1800091da  cmp     dword ptr [rax], 10000h
0x1800091e0  sbb     rax, rax
0x1800091e3  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800091e7  lea     rdx, [rax+4]
0x1800091eb  add     rdx, rbx
0x1800091ee  cmp     rdx, rbx
0x1800091f1  jbe     short loc_180009205
0x1800091f3  mov     rbx, rdx
0x1800091f6  cmp     rcx, rsi
0x1800091f9  jnz     short loc_1800091B6
0x1800091fb  mov     [rdi], rbx
0x1800091fe  xor     eax, eax
0x180009200  jmp     loc_1800092BC
0x180009205  lea     rax, aOnecoreBaseLst_3; "onecore\\base\\lstring\\lutf8_string.cp"...
0x18000920c  mov     [rbp+var_10], 417h
0x180009214  mov     [rbp+var_20], rax
0x180009218  mov     r8d, 0C0000095h
0x18000921e  lea     rax, aRtlcalculateut; "RtlCalculateUtf16StringLengthFromLUtf8S"...
0x180009225  mov     [rbp+var_18], rax
0x180009229  lea     rax, aNewtempbytesre; "NewTempBytesRequired > TempBytesRequire"...
0x180009230  mov     [rbp+var_8], rax
0x180009234  call    RtlReportErrorOrigination
0x180009239  mov     eax, 0C0000095h
0x18000923e  jmp     short loc_1800092BC
0x180009240  lea     rax, aOnecoreBaseLst_3; "onecore\\base\\lstring\\lutf8_string.cp"...
0x180009247  mov     [rbp+var_10], 415h
0x18000924f  mov     [rbp+var_20], rax
0x180009253  mov     r8d, 0C0000161h
0x180009259  lea     rax, aRtlcalculateut; "RtlCalculateUtf16StringLengthFromLUtf8S"...
0x180009260  mov     [rbp+var_18], rax
0x180009264  lea     rax, aRvUcscharacter; "rv.UcsCharacter < 0x110000"
0x18000926b  mov     [rbp+var_8], rax
0x18000926f  call    RtlReportErrorOrigination
0x180009274  mov     eax, 0C0000161h
0x180009279  jmp     short loc_1800092BC
0x18000927b  test    ecx, ecx
0x18000927d  jns     short loc_1800092C9
0x18000927f  mov     eax, ecx
0x180009281  jmp     short loc_1800092BC
0x180009283  lea     rax, aOnecoreBaseLst_3; "onecore\\base\\lstring\\lutf8_string.cp"...
0x18000928a  mov     [rbp+var_10], 407h
0x180009292  mov     [rbp+var_20], rax
0x180009296  lea     rax, aRtlcalculateut; "RtlCalculateUtf16StringLengthFromLUtf8S"...
0x18000929d  mov     [rbp+var_18], rax
0x1800092a1  lea     rax, aNotNullCheckFa_14; "Not-null check failed: BytesRequired"
0x1800092a8  mov     r8d, 0C000000Dh
0x1800092ae  mov     [rbp+var_8], rax
0x1800092b2  call    RtlReportErrorOrigination
0x1800092b7  mov     eax, 0C000000Dh
0x1800092bc  mov     rbx, [rsp+40h+arg_10]
0x1800092c1  add     rsp, 40h
0x1800092c5  pop     rdi
0x1800092c6  pop     rsi
0x1800092c7  pop     rbp
0x1800092c8  retn
0x1800092c9  mov     ecx, 0C00000E5h; int
0x1800092ce  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
