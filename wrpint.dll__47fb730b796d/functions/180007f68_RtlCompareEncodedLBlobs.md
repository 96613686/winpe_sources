# RtlCompareEncodedLBlobs

- ea: `0x180007f68`
- end: `0x180008242`
- name: `RtlCompareEncodedLBlobs`
- size: `730`
- prototype: `__int64 __fastcall(_QWORD *, __int64, _QWORD *, __int64 (__fastcall *)(const char **, __int64, __int64), __int64 (__fastcall *)(_QWORD), int *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007a80`
- `0x180015478`
- `0x180016178`

## callees

- `0x1800054f0`
- `0x180007568`
- `0x180007f68`
- `0x180009460`
- `0x18001c010`

## string_xrefs

- `0x180007fb6`: `RtlCompareEncodedLBlobs`
- `0x180007fe5`: `RtlCompareEncodedLBlobs`
- `0x180008014`: `RtlCompareEncodedLBlobs`
- `0x1800080fb`: `RtlCompareEncodedLBlobs`
- `0x18000813b`: `RtlCompareEncodedLBlobs`
- `0x180008202`: `RtlCompareEncodedLBlobs`
- `0x18000820d`: `Not-null check failed: ComparisonResult`

## pseudocode

```c
__int64 __fastcall RtlCompareEncodedLBlobs(
        _QWORD *a1,
        __int64 a2,
        _QWORD *a3,
        __int64 (__fastcall *a4)(const char **, __int64, __int64),
        __int64 (__fastcall *a5)(_QWORD),
        int *a6)
{
  __int64 (__fastcall *v7)(_QWORD); // r12
  const char *v8; // rax
  __int64 v9; // rbx
  int v10; // ecx
  __int64 v11; // rdi
  __int64 v12; // rsi
  __int64 v13; // r14
  unsigned int *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  unsigned int *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  unsigned int v20; // r12d
  unsigned int v21; // eax
  int v22; // eax
  __int64 v24; // rax
  unsigned int v25; // r12d
  __int64 v26; // rax
  const char *v27; // [rsp+20h] [rbp-50h] BYREF
  const char *v28; // [rsp+28h] [rbp-48h]
  __int64 v29; // [rsp+30h] [rbp-40h]
  const char *v30; // [rsp+38h] [rbp-38h]
  unsigned int v31; // [rsp+40h] [rbp-30h]
  unsigned int v32; // [rsp+44h] [rbp-2Ch]
  __int64 (__fastcall *v33)(_QWORD); // [rsp+48h] [rbp-28h]
  __int64 (__fastcall *v34)(const char **, __int64, __int64); // [rsp+50h] [rbp-20h]
  _BYTE v35[24]; // [rsp+58h] [rbp-18h] BYREF

  v7 = a5;
  v34 = a4;
  v33 = a5;
  if ( !a6 )
  {
    v29 = 2251;
    v27 = "onecore\\base\\lstring\\lblob.cpp";
    v28 = "RtlCompareEncodedLBlobs";
    v8 = "Not-null check failed: ComparisonResult";
    goto LABEL_41;
  }
  *a6 = 0;
  if ( !a1 )
  {
    v29 = 2252;
    v27 = "onecore\\base\\lstring\\lblob.cpp";
    v28 = "RtlCompareEncodedLBlobs";
    v8 = "Not-null check failed: String1";
LABEL_41:
    v30 = v8;
    RtlReportErrorOrigination(a1, a2, 3221225485LL);
    return 3221225485LL;
  }
  if ( !a3 )
  {
    v29 = 2254;
    v27 = "onecore\\base\\lstring\\lblob.cpp";
    v28 = "RtlCompareEncodedLBlobs";
    v8 = "Not-null check failed: String2";
    goto LABEL_41;
  }
  if ( !a4 )
  {
    v29 = 2255;
    v27 = "onecore\\base\\lstring\\lblob.cpp";
    v28 = "RtlCompareEncodedLBlobs";
    v8 = "Not-null check failed: pfn2";
    goto LABEL_41;
  }
  v9 = a1[2];
  v10 = 0;
  v11 = a3[2];
  v12 = v9 + *a1;
  v13 = v11 + *a3;
  if ( v9 == v12 )
  {
LABEL_36:
    if ( v11 != v13 )
      v10 = -1;
    v22 = v10;
LABEL_39:
    *a6 = v22;
    return 0;
  }
  else
  {
    if ( a5 )
    {
      while ( 1 )
      {
        if ( v11 == v13 )
          goto LABEL_16;
        v14 = (unsigned int *)RtlDecodeUtf16LE(v35, v9, v12);
        v16 = *v14;
        v9 = *((_QWORD *)v14 + 1);
        v31 = v16;
        if ( (_DWORD)v16 == -1 )
          break;
        v17 = (unsigned int *)v34(&v27, v11, v13);
        v19 = *v17;
        v11 = *((_QWORD *)v17 + 1);
        v32 = v19;
        if ( (_DWORD)v19 == -1 )
        {
          if ( (int)v11 < 0 )
          {
            v29 = 2276;
            goto LABEL_20;
          }
LABEL_42:
          INTERNAL_ERROR_ACTION(-1073741595);
        }
        v20 = v7(v31);
        v21 = v33(v32);
        if ( v20 < v21 )
          goto LABEL_31;
        if ( v20 != v21 )
          goto LABEL_17;
        v7 = v33;
        v10 = 0;
        if ( v9 == v12 )
          goto LABEL_16;
      }
      if ( (int)v9 >= 0 )
        goto LABEL_42;
      v29 = 2275;
    }
    else
    {
      while ( 1 )
      {
        if ( v11 == v13 )
        {
LABEL_16:
          if ( v9 == v12 )
            goto LABEL_36;
LABEL_17:
          v22 = 1;
          goto LABEL_39;
        }
        v24 = RtlDecodeUtf16LE(&v27, v9, v12);
        v25 = *(_DWORD *)v24;
        v9 = *(_QWORD *)(v24 + 8);
        if ( *(_DWORD *)v24 == -1 )
          break;
        v26 = v34((const char **)v35, v11, v13);
        v11 = *(_QWORD *)(v26 + 8);
        if ( *(_DWORD *)v26 == -1 )
        {
          if ( (int)v11 >= 0 )
            goto LABEL_42;
          v29 = 2293;
LABEL_20:
          v27 = "onecore\\base\\lstring\\lblob.cpp";
          v28 = "RtlCompareEncodedLBlobs";
          v30 = "__rv.UcsCharacter != (0xffffffff)";
          RtlReportErrorOrigination(v19, v18, (unsigned int)v11);
          return (unsigned int)v11;
        }
        if ( v25 < *(_DWORD *)v26 )
        {
LABEL_31:
          v22 = -1;
          goto LABEL_39;
        }
        if ( v25 != *(_DWORD *)v26 )
          goto LABEL_17;
        v10 = 0;
        if ( v9 == v12 )
          goto LABEL_16;
      }
      if ( (int)v9 >= 0 )
        goto LABEL_42;
      v29 = 2292;
    }
    v27 = "onecore\\base\\lstring\\lblob.cpp";
    v28 = "RtlCompareEncodedLBlobs";
    v30 = "__rv.UcsCharacter != (0xffffffff)";
    RtlReportErrorOrigination(v16, v15, (unsigned int)v9);
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x180007f68  push    rbp
0x180007f6a  push    rbx
0x180007f6b  push    rsi
0x180007f6c  push    rdi
0x180007f6d  push    r12
0x180007f6f  push    r13
0x180007f71  push    r14
0x180007f73  mov     rbp, rsp
0x180007f76  sub     rsp, 70h
0x180007f7a  mov     r13, [rbp+arg_28]
0x180007f7e  mov     rax, rcx
0x180007f81  mov     r12, [rbp+arg_20]
0x180007f85  mov     [rbp+var_20], r9
0x180007f89  mov     [rbp+var_28], r12
0x180007f8d  test    r13, r13
0x180007f90  jz      loc_1800081EF
0x180007f96  mov     dword ptr [r13+0], 0
0x180007f9e  test    rax, rax
0x180007fa1  jnz     short loc_180007FCD
0x180007fa3  lea     rax, aOnecoreBaseLst_1; "onecore\\base\\lstring\\lblob.cpp"
0x180007faa  mov     [rbp+var_40], 8CCh
0x180007fb2  mov     [rbp+var_50], rax
0x180007fb6  lea     rax, aRtlcompareenco; "RtlCompareEncodedLBlobs"
0x180007fbd  mov     [rbp+var_48], rax
0x180007fc1  lea     rax, aNotNullCheckFa_1; "Not-null check failed: String1"
0x180007fc8  jmp     loc_180008214
0x180007fcd  test    r8, r8
0x180007fd0  jnz     short loc_180007FFC
0x180007fd2  lea     rax, aOnecoreBaseLst_1; "onecore\\base\\lstring\\lblob.cpp"
0x180007fd9  mov     [rbp+var_40], 8CEh
0x180007fe1  mov     [rbp+var_50], rax
0x180007fe5  lea     rax, aRtlcompareenco; "RtlCompareEncodedLBlobs"
0x180007fec  mov     [rbp+var_48], rax
0x180007ff0  lea     rax, aNotNullCheckFa_15; "Not-null check failed: String2"
0x180007ff7  jmp     loc_180008214
0x180007ffc  test    r9, r9
0x180007fff  jnz     short loc_18000802B
0x180008001  lea     rax, aOnecoreBaseLst_1; "onecore\\base\\lstring\\lblob.cpp"
0x180008008  mov     [rbp+var_40], 8CFh
0x180008010  mov     [rbp+var_50], rax
0x180008014  lea     rax, aRtlcompareenco; "RtlCompareEncodedLBlobs"
0x18000801b  mov     [rbp+var_48], rax
0x18000801f  lea     rax, aNotNullCheckFa_13; "Not-null check failed: pfn2"
0x180008026  jmp     loc_180008214
0x18000802b  mov     rbx, [rax+10h]
0x18000802f  xor     ecx, ecx
0x180008031  mov     rsi, [rax]
0x180008034  mov     rdi, [r8+10h]
0x180008038  add     rsi, rbx
0x18000803b  mov     r14, [r8]
0x18000803e  add     r14, rdi
0x180008041  cmp     rbx, rsi
0x180008044  jz      loc_1800081DC
0x18000804a  test    r12, r12
0x18000804d  jz      loc_18000815D
0x180008053  cmp     rdi, r14
0x180008056  jz      short loc_1800080CA
0x180008058  mov     r8, rsi
0x18000805b  lea     rcx, [rbp+var_18]
0x18000805f  mov     rdx, rbx
0x180008062  call    RtlDecodeUtf16LE
0x180008067  mov     ecx, [rax]
0x180008069  mov     rbx, [rax+8]
0x18000806d  mov     [rbp+var_30], ecx
0x180008070  cmp     ecx, 0FFFFFFFFh
0x180008073  jz      loc_18000811D
0x180008079  mov     rax, [rbp+var_20]
0x18000807d  lea     rcx, [rbp+var_50]
0x180008081  mov     r8, r14
0x180008084  mov     rdx, rdi
0x180008087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000808c  mov     ecx, [rax]
0x18000808e  mov     rdi, [rax+8]
0x180008092  mov     [rbp+var_2C], ecx
0x180008095  cmp     ecx, 0FFFFFFFFh
0x180008098  jz      short loc_1800080DD
0x18000809a  mov     ecx, [rbp+var_30]
0x18000809d  mov     rax, r12
0x1800080a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080a5  mov     ecx, [rbp+var_2C]
0x1800080a8  mov     r12d, eax
0x1800080ab  mov     rax, [rbp+var_28]
0x1800080af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080b4  cmp     r12d, eax
0x1800080b7  jb      loc_1800081B5
0x1800080bd  jnz     short loc_1800080D3
0x1800080bf  mov     r12, [rbp+var_28]
0x1800080c3  xor     ecx, ecx
0x1800080c5  cmp     rbx, rsi
0x1800080c8  jnz     short loc_180008053
0x1800080ca  cmp     rbx, rsi
0x1800080cd  jz      loc_1800081DC
0x1800080d3  mov     eax, 1
0x1800080d8  jmp     loc_1800081E7
0x1800080dd  test    edi, edi
0x1800080df  jns     loc_180008237
0x1800080e5  mov     [rbp+var_40], 8E4h
0x1800080ed  lea     rax, aOnecoreBaseLst_1; "onecore\\base\\lstring\\lblob.cpp"
0x1800080f4  mov     r8d, edi
0x1800080f7  mov     [rbp+var_50], rax
0x1800080fb  lea     rax, aRtlcompareenco; "RtlCompareEncodedLBlobs"
0x180008102  mov     [rbp+var_48], rax
0x180008106  lea     rax, aRvUcscharacter_0; "__rv.UcsCharacter != (0xffffffff)"
0x18000810d  mov     [rbp+var_38], rax
0x180008111  call    RtlReportErrorOrigination
0x180008116  mov     eax, edi
0x180008118  jmp     loc_180008228
0x18000811d  test    ebx, ebx
0x18000811f  jns     loc_180008237
0x180008125  mov     [rbp+var_40], 8E3h
0x18000812d  lea     rax, aOnecoreBaseLst_1; "onecore\\base\\lstring\\lblob.cpp"
0x180008134  mov     r8d, ebx
0x180008137  mov     [rbp+var_50], rax
0x18000813b  lea     rax, aRtlcompareenco; "RtlCompareEncodedLBlobs"
0x180008142  mov     [rbp+var_48], rax
0x180008146  lea     rax, aRvUcscharacter_0; "__rv.UcsCharacter != (0xffffffff)"
0x18000814d  mov     [rbp+var_38], rax
0x180008151  call    RtlReportErrorOrigination
0x180008156  mov     eax, ebx
0x180008158  jmp     loc_180008228
0x18000815d  cmp     rdi, r14
0x180008160  jz      loc_1800080CA
0x180008166  mov     r8, rsi
0x180008169  lea     rcx, [rbp+var_50]
0x18000816d  mov     rdx, rbx
0x180008170  call    RtlDecodeUtf16LE
0x180008175  mov     r12d, [rax]
0x180008178  mov     rbx, [rax+8]
0x18000817c  cmp     r12d, 0FFFFFFFFh
0x180008180  jz      short loc_1800081CB
0x180008182  mov     rax, [rbp+var_20]
0x180008186  lea     rcx, [rbp+var_18]
0x18000818a  mov     r8, r14
0x18000818d  mov     rdx, rdi
0x180008190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008195  cmp     dword ptr [rax], 0FFFFFFFFh
0x180008198  mov     rdi, [rax+8]
0x18000819c  jz      short loc_1800081BA
0x18000819e  cmp     r12d, [rax]
0x1800081a1  jb      short loc_1800081B5
0x1800081a3  jnz     loc_1800080D3
0x1800081a9  xor     ecx, ecx
0x1800081ab  cmp     rbx, rsi
0x1800081ae  jnz     short loc_18000815D
0x1800081b0  jmp     loc_1800080CA
0x1800081b5  or      eax, 0FFFFFFFFh
0x1800081b8  jmp     short loc_1800081E7
0x1800081ba  test    edi, edi
0x1800081bc  jns     short loc_180008237
0x1800081be  mov     [rbp+var_40], 8F5h
0x1800081c6  jmp     loc_1800080ED
0x1800081cb  test    ebx, ebx
0x1800081cd  jns     short loc_180008237
0x1800081cf  mov     [rbp+var_40], 8F4h
0x1800081d7  jmp     loc_18000812D
0x1800081dc  or      eax, 0FFFFFFFFh
0x1800081df  cmp     rdi, r14
0x1800081e2  cmovnz  ecx, eax
0x1800081e5  mov     eax, ecx
0x1800081e7  mov     [r13+0], eax
0x1800081eb  xor     eax, eax
0x1800081ed  jmp     short loc_180008228
0x1800081ef  lea     rax, aOnecoreBaseLst_1; "onecore\\base\\lstring\\lblob.cpp"
0x1800081f6  mov     [rbp+var_40], 8CBh
0x1800081fe  mov     [rbp+var_50], rax
0x180008202  lea     rax, aRtlcompareenco; "RtlCompareEncodedLBlobs"
0x180008209  mov     [rbp+var_48], rax
0x18000820d  lea     rax, aNotNullCheckFa_10; "Not-null check failed: ComparisonResult"
0x180008214  mov     r8d, 0C000000Dh
0x18000821a  mov     [rbp+var_38], rax
0x18000821e  call    RtlReportErrorOrigination
0x180008223  mov     eax, 0C000000Dh
0x180008228  add     rsp, 70h
0x18000822c  pop     r14
0x18000822e  pop     r13
0x180008230  pop     r12
0x180008232  pop     rdi
0x180008233  pop     rsi
0x180008234  pop     rbx
0x180008235  pop     rbp
0x180008236  retn
0x180008237  mov     ecx, 0C00000E5h; int
0x18000823c  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
