# RtlCombineNtPathSegments

- ea: `0x18001b30c`
- end: `0x18001b690`
- name: `RtlCombineNtPathSegments`
- size: `900`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18001a17c`

## callees

- `0x1800054f0`
- `0x180007568`
- `0x1800077f4`
- `0x180009410`
- `0x18001b30c`
- `0x18001b698`
- `0x18001b762`

## string_xrefs

- `0x18001b33d`: `onecore\base\lstring\path.cpp`
- `0x18001b39b`: `onecore\base\lstring\path.cpp`
- `0x18001b59a`: `onecore\base\lstring\path.cpp`
- `0x18001b5d0`: `onecore\base\lstring\path.cpp`
- `0x18001b3b9`: `Not-null check failed: PathOut`
- `0x18001b350`: `RtlCombineNtPathSegments`
- `0x18001b3ae`: `RtlCombineNtPathSegments`
- `0x18001b5b3`: `RtlCombineNtPathSegments`
- `0x18001b5e9`: `RtlCombineNtPathSegments`
- `0x18001b35b`: `(PathSegmentCount == 0) || (PathSegments != 0)`
- `0x18001b5f4`: `BytesLeft >= BytesToCopy`

## pseudocode

```c
__int64 __fastcall RtlCombineNtPathSegments(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // r15
  const char *v5; // rax
  __int64 result; // rax
  unsigned __int64 v7; // rdi
  unsigned __int64 i; // rbx
  unsigned __int64 *v9; // rcx
  unsigned __int64 v10; // rsi
  __int64 v11; // rsi
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rsi
  void *v14; // rbx
  __int128 v15; // xmm6
  unsigned __int64 v16; // r14
  int v17; // ebx
  unsigned __int64 v18; // rax
  _WORD *v19; // rdi
  unsigned __int64 *v20; // rax
  unsigned __int64 v21; // r15
  __int64 v22; // rdx
  int v23; // r13d
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // r15
  void *v26; // rcx
  __int64 v27; // xmm1_8
  char v28; // [rsp+20h] [rbp-60h]
  char v29; // [rsp+21h] [rbp-5Fh]
  unsigned __int64 v30; // [rsp+28h] [rbp-58h] BYREF
  __int128 v31; // [rsp+30h] [rbp-50h] BYREF
  __int64 v32; // [rsp+40h] [rbp-40h]
  const char *v33; // [rsp+48h] [rbp-38h]
  unsigned __int64 v34; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int64 v35; // [rsp+58h] [rbp-28h]
  unsigned __int64 *v36; // [rsp+60h] [rbp-20h]
  __int64 v37; // [rsp+68h] [rbp-18h]

  v37 = a2;
  v4 = a2;
  if ( !a2 )
  {
    v32 = 602;
    *(_QWORD *)&v31 = "onecore\\base\\lstring\\path.cpp";
    *((_QWORD *)&v31 + 1) = "RtlCombineNtPathSegments";
    v5 = "(PathSegmentCount == 0) || (PathSegments != 0)";
LABEL_3:
    v33 = v5;
    RtlReportErrorOrigination(a1, a2, 3221225485LL);
    return 3221225485LL;
  }
  if ( !a3 )
  {
    v32 = 603;
    *(_QWORD *)&v31 = "onecore\\base\\lstring\\path.cpp";
    *((_QWORD *)&v31 + 1) = "RtlCombineNtPathSegments";
    v5 = "Not-null check failed: PathOut";
    goto LABEL_3;
  }
  v7 = 0;
  for ( i = 0; i < 2; ++i )
  {
    while ( 1 )
    {
      v34 = 0;
      v9 = (unsigned __int64 *)(v4 + 24 * i);
      v30 = 0;
      v10 = *v9;
      result = RtlTrimNtPathSegment(v9, &v34, &v30);
      if ( (int)result < 0 )
        return result;
      if ( v34 > v10 || v30 > v10 - v34 )
        goto LABEL_58;
      v11 = v10 - v30 - (v34 & -(__int64)(i != 0));
      if ( !v11 )
        goto LABEL_15;
      v12 = v11 + v7;
      if ( v11 + v7 < v7 )
        return 3221225621LL;
      if ( i )
        break;
      v7 += v11;
      i = 1;
    }
    v7 = v12 + 2;
    if ( v12 + 2 < v12 )
      return 3221225621LL;
LABEL_15:
    ;
  }
  v13 = *(_QWORD *)(a3 + 8);
  v14 = 0;
  v32 = 0;
  v15 = 0;
  v31 = 0;
  if ( v7 <= v13 )
  {
    v16 = *(_QWORD *)(a3 + 16);
    v29 = 0;
LABEL_25:
    v18 = 0;
    v28 = 1;
    v35 = 0;
    v19 = (_WORD *)v16;
    while ( 1 )
    {
      v34 = 0;
      v20 = (unsigned __int64 *)(v4 + 24 * v18);
      v30 = 0;
      v21 = *v20;
      v36 = v20;
      if ( v21 )
      {
        v23 = RtlTrimNtPathSegment(v20, &v34, &v30);
        if ( v23 < 0 )
        {
          if ( v14 )
            anonymous_namespace_::OurRtlFreeStringRoutine(v14);
          return (unsigned int)v23;
        }
        v24 = v34;
        if ( v34 > v21 || v30 > v21 - v34 )
          goto LABEL_58;
        if ( v28 )
        {
          v24 = 0;
        }
        else if ( v34 >= 2 )
        {
          v24 = v34 - 2;
        }
        else if ( v19 == (_WORD *)v16 || *(v19 - 1) != 92 )
        {
          if ( v13 < 2 )
          {
            v32 = 694;
            *(_QWORD *)&v31 = "onecore\\base\\lstring\\path.cpp";
            *((_QWORD *)&v31 + 1) = "RtlCombineNtPathSegments";
            v33 = "BytesLeft >= sizeof(WCHAR)";
            RtlReportErrorOrigination(v34, v22, 3221225507LL);
LABEL_44:
            if ( v14 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v14);
            return 3221225507LL;
          }
          *v19++ = 92;
          v13 -= 2LL;
        }
        v25 = *v36 - v30 - v24;
        if ( v13 < v25 )
        {
          v32 = 708;
          *(_QWORD *)&v31 = "onecore\\base\\lstring\\path.cpp";
          *((_QWORD *)&v31 + 1) = "RtlCombineNtPathSegments";
          v33 = "BytesLeft >= BytesToCopy";
          RtlReportErrorOrigination(v24, v22, 3221225507LL);
          if ( v14 )
            goto LABEL_44;
          return 3221225507LL;
        }
        memcpy_0(v19, (const void *)(v24 + v36[2]), *v36 - v30 - v24);
        v19 = (_WORD *)((char *)v19 + v25);
        v28 = 0;
        v13 -= v25;
      }
      v18 = v35 + 1;
      v35 = v18;
      if ( v18 >= 2 )
      {
        if ( v29 )
        {
          v26 = *(void **)(a3 + 16);
          v27 = v32;
          v32 = 0;
          *(_OWORD *)a3 = v15;
          *(_QWORD *)(a3 + 16) = v27;
          if ( v26 )
            anonymous_namespace_::OurRtlFreeStringRoutine(v26);
          v14 = (void *)v32;
        }
        if ( (unsigned __int64)v19 >= v16 )
        {
          *(_QWORD *)a3 = (char *)v19 - v16;
          if ( v14 )
            anonymous_namespace_::OurRtlFreeStringRoutine(v14);
          return 0;
        }
LABEL_58:
        INTERNAL_ERROR_ACTION(-1073741595);
      }
      v4 = v37;
    }
  }
  v17 = RtlAllocateLUnicodeString(v7, &v31);
  if ( v17 >= 0 )
  {
    v14 = (void *)v32;
    v13 = *((_QWORD *)&v31 + 1);
    v16 = v32;
    v15 = v31;
    v29 = 1;
    goto LABEL_25;
  }
  if ( v32 )
    anonymous_namespace_::OurRtlFreeStringRoutine((void *)v32);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18001b30c  mov     [rsp-38h+arg_0], rbx
0x18001b311  push    rbp
0x18001b312  push    rsi
0x18001b313  push    rdi
0x18001b314  push    r12
0x18001b316  push    r13
0x18001b318  push    r14
0x18001b31a  push    r15
0x18001b31c  mov     rbp, rsp
0x18001b31f  sub     rsp, 80h
0x18001b326  xor     r13d, r13d
0x18001b329  movaps  [rsp+80h+var_10], xmm6
0x18001b32e  mov     [rbp+var_18], rdx
0x18001b332  mov     r12, r8
0x18001b335  mov     r15, rdx
0x18001b338  test    rdx, rdx
0x18001b33b  jnz     short loc_18001B396
0x18001b33d  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18001b344  mov     [rbp+var_40], 25Ah
0x18001b34c  mov     qword ptr [rbp+var_50], rax
0x18001b350  lea     rax, aRtlcombinentpa; "RtlCombineNtPathSegments"
0x18001b357  mov     qword ptr [rbp+var_50+8], rax
0x18001b35b  lea     rax, aPathsegmentcou; "(PathSegmentCount == 0) || (PathSegment"...
0x18001b362  mov     r8d, 0C000000Dh
0x18001b368  mov     [rbp+var_38], rax
0x18001b36c  call    RtlReportErrorOrigination
0x18001b371  mov     eax, 0C000000Dh
0x18001b376  mov     rbx, [rsp+80h+arg_0]
0x18001b37e  movaps  xmm6, [rsp+80h+var_10]
0x18001b383  add     rsp, 80h
0x18001b38a  pop     r15
0x18001b38c  pop     r14
0x18001b38e  pop     r13
0x18001b390  pop     r12
0x18001b392  pop     rdi
0x18001b393  pop     rsi
0x18001b394  pop     rbp
0x18001b395  retn
0x18001b396  test    r12, r12
0x18001b399  jnz     short loc_18001B3C2
0x18001b39b  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18001b3a2  mov     [rbp+var_40], 25Bh
0x18001b3aa  mov     qword ptr [rbp+var_50], rax
0x18001b3ae  lea     rax, aRtlcombinentpa; "RtlCombineNtPathSegments"
0x18001b3b5  mov     qword ptr [rbp+var_50+8], rax
0x18001b3b9  lea     rax, aNotNullCheckFa_0; "Not-null check failed: PathOut"
0x18001b3c0  jmp     short loc_18001B362
0x18001b3c2  mov     rdi, r13
0x18001b3c5  mov     rbx, r13
0x18001b3c8  lea     rax, [rbx+rbx*2]
0x18001b3cc  mov     [rbp+var_30], r13
0x18001b3d0  lea     rcx, [r15+rax*8]
0x18001b3d4  mov     [rbp+var_58], r13
0x18001b3d8  mov     rsi, [rcx]
0x18001b3db  lea     r8, [rbp+var_58]
0x18001b3df  lea     rdx, [rbp+var_30]
0x18001b3e3  call    RtlTrimNtPathSegment
0x18001b3e8  test    eax, eax
0x18001b3ea  js      short loc_18001B376
0x18001b3ec  mov     rdx, [rbp+var_30]
0x18001b3f0  cmp     rdx, rsi
0x18001b3f3  ja      loc_18001B685
0x18001b3f9  mov     rax, rsi
0x18001b3fc  sub     rax, rdx
0x18001b3ff  cmp     [rbp+var_58], rax
0x18001b403  ja      loc_18001B685
0x18001b409  mov     rax, rbx
0x18001b40c  neg     rax
0x18001b40f  sbb     rcx, rcx
0x18001b412  sub     rsi, [rbp+var_58]
0x18001b416  and     rcx, rdx
0x18001b419  sub     rsi, rcx
0x18001b41c  jz      short loc_18001B435
0x18001b41e  lea     rax, [rsi+rdi]
0x18001b422  cmp     rax, rdi
0x18001b425  jb      short loc_18001B46B
0x18001b427  test    rbx, rbx
0x18001b42a  jz      short loc_18001B460
0x18001b42c  lea     rdi, [rax+2]
0x18001b430  cmp     rdi, rax
0x18001b433  jb      short loc_18001B46B
0x18001b435  inc     rbx
0x18001b438  cmp     rbx, 2
0x18001b43c  jb      short loc_18001B3C8
0x18001b43e  mov     rsi, [r12+8]
0x18001b443  xor     ebx, ebx
0x18001b445  mov     [rbp+var_40], rbx
0x18001b449  xorps   xmm6, xmm6
0x18001b44c  movups  [rbp+var_50], xmm6
0x18001b450  cmp     rdi, rsi
0x18001b453  ja      short loc_18001B475
0x18001b455  mov     r14, [r12+10h]
0x18001b45a  mov     [rbp+var_5F], r13b
0x18001b45e  jmp     short loc_18001B4AF
0x18001b460  mov     rdi, rax
0x18001b463  inc     rbx
0x18001b466  jmp     loc_18001B3C8
0x18001b46b  mov     eax, 0C0000095h
0x18001b470  jmp     loc_18001B376
0x18001b475  lea     rdx, [rbp+var_50]
0x18001b479  mov     rcx, rdi
0x18001b47c  call    RtlAllocateLUnicodeString
0x18001b481  mov     ebx, eax
0x18001b483  test    eax, eax
0x18001b485  jns     short loc_18001B49C
0x18001b487  mov     rcx, [rbp+var_40]
0x18001b48b  test    rcx, rcx
0x18001b48e  jz      short loc_18001B495
0x18001b490  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001b495  mov     eax, ebx
0x18001b497  jmp     loc_18001B376
0x18001b49c  mov     rbx, [rbp+var_40]
0x18001b4a0  mov     rsi, qword ptr [rbp+var_50+8]
0x18001b4a4  mov     r14, rbx
0x18001b4a7  movups  xmm6, [rbp+var_50]
0x18001b4ab  mov     [rbp+var_5F], 1
0x18001b4af  mov     rax, r13
0x18001b4b2  mov     [rbp+var_60], 1
0x18001b4b6  mov     [rbp+var_28], rax
0x18001b4ba  mov     rdi, r14
0x18001b4bd  lea     rax, [rax+rax*2]
0x18001b4c1  mov     [rbp+var_30], r13
0x18001b4c5  lea     rax, [r15+rax*8]
0x18001b4c9  mov     [rbp+var_58], r13
0x18001b4cd  mov     r15, [rax]
0x18001b4d0  mov     [rbp+var_20], rax
0x18001b4d4  test    r15, r15
0x18001b4d7  jz      loc_18001B57C
0x18001b4dd  lea     r8, [rbp+var_58]
0x18001b4e1  mov     rcx, rax
0x18001b4e4  lea     rdx, [rbp+var_30]
0x18001b4e8  call    RtlTrimNtPathSegment
0x18001b4ed  mov     r13d, eax
0x18001b4f0  test    eax, eax
0x18001b4f2  js      loc_18001B620
0x18001b4f8  mov     rcx, [rbp+var_30]
0x18001b4fc  cmp     rcx, r15
0x18001b4ff  ja      loc_18001B685
0x18001b505  sub     r15, rcx
0x18001b508  cmp     [rbp+var_58], r15
0x18001b50c  ja      loc_18001B685
0x18001b512  xor     r13d, r13d
0x18001b515  cmp     [rbp+var_60], r13b
0x18001b519  jz      short loc_18001B520
0x18001b51b  mov     ecx, r13d
0x18001b51e  jmp     short loc_18001B54D
0x18001b520  cmp     rcx, 2
0x18001b524  jnb     short loc_18001B549
0x18001b526  mov     eax, 5Ch ; '\'
0x18001b52b  cmp     rdi, r14
0x18001b52e  jz      short loc_18001B536
0x18001b530  cmp     [rdi-2], ax
0x18001b534  jz      short loc_18001B54D
0x18001b536  cmp     rsi, 2
0x18001b53a  jb      short loc_18001B59A
0x18001b53c  mov     [rdi], ax
0x18001b53f  add     rdi, 2
0x18001b543  sub     rsi, 2
0x18001b547  jmp     short loc_18001B54D
0x18001b549  sub     rcx, 2
0x18001b54d  mov     rax, [rbp+var_20]
0x18001b551  mov     r15, [rax]
0x18001b554  sub     r15, [rbp+var_58]
0x18001b558  sub     r15, rcx
0x18001b55b  cmp     rsi, r15
0x18001b55e  jb      short loc_18001B5D0
0x18001b560  mov     rdx, [rax+10h]
0x18001b564  mov     r8, r15; Size
0x18001b567  add     rdx, rcx; Src
0x18001b56a  mov     rcx, rdi; void *
0x18001b56d  call    memcpy_0
0x18001b572  add     rdi, r15
0x18001b575  mov     [rbp+var_60], r13b
0x18001b579  sub     rsi, r15
0x18001b57c  mov     rax, [rbp+var_28]
0x18001b580  inc     rax
0x18001b583  mov     [rbp+var_28], rax
0x18001b587  cmp     rax, 2
0x18001b58b  jnb     loc_18001B635
0x18001b591  mov     r15, [rbp+var_18]
0x18001b595  jmp     loc_18001B4BD
0x18001b59a  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18001b5a1  mov     [rbp+var_40], 2B6h
0x18001b5a9  mov     qword ptr [rbp+var_50], rax
0x18001b5ad  mov     r8d, 0C0000023h
0x18001b5b3  lea     rax, aRtlcombinentpa; "RtlCombineNtPathSegments"
0x18001b5ba  mov     qword ptr [rbp+var_50+8], rax
0x18001b5be  lea     rax, aBytesleftSizeo; "BytesLeft >= sizeof(WCHAR)"
0x18001b5c5  mov     [rbp+var_38], rax
0x18001b5c9  call    RtlReportErrorOrigination
0x18001b5ce  jmp     short loc_18001B609
0x18001b5d0  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18001b5d7  mov     [rbp+var_40], 2C4h
0x18001b5df  mov     qword ptr [rbp+var_50], rax
0x18001b5e3  mov     r8d, 0C0000023h
0x18001b5e9  lea     rax, aRtlcombinentpa; "RtlCombineNtPathSegments"
0x18001b5f0  mov     qword ptr [rbp+var_50+8], rax
0x18001b5f4  lea     rax, aBytesleftBytes; "BytesLeft >= BytesToCopy"
0x18001b5fb  mov     [rbp+var_38], rax
0x18001b5ff  call    RtlReportErrorOrigination
0x18001b604  test    rbx, rbx
0x18001b607  jz      short loc_18001B616
0x18001b609  test    rbx, rbx
0x18001b60c  jz      short loc_18001B616
0x18001b60e  mov     rcx, rbx
0x18001b611  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001b616  mov     eax, 0C0000023h
0x18001b61b  jmp     loc_18001B376
0x18001b620  test    rbx, rbx
0x18001b623  jz      short loc_18001B62D
0x18001b625  mov     rcx, rbx
0x18001b628  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001b62d  mov     eax, r13d
0x18001b630  jmp     loc_18001B376
0x18001b635  cmp     [rbp+var_5F], r13b
0x18001b639  jz      short loc_18001B665
0x18001b63b  mov     rcx, [r12+10h]
0x18001b640  xor     eax, eax
0x18001b642  movsd   xmm1, [rbp+var_40]
0x18001b647  mov     [rbp+var_40], rax
0x18001b64b  movups  xmmword ptr [r12], xmm6
0x18001b650  movsd   qword ptr [r12+10h], xmm1
0x18001b657  test    rcx, rcx
0x18001b65a  jz      short loc_18001B661
0x18001b65c  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001b661  mov     rbx, [rbp+var_40]
0x18001b665  cmp     rdi, r14
0x18001b668  jb      short loc_18001B685
0x18001b66a  sub     rdi, r14
0x18001b66d  mov     [r12], rdi
0x18001b671  test    rbx, rbx
0x18001b674  jz      short loc_18001B67E
0x18001b676  mov     rcx, rbx
0x18001b679  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001b67e  xor     eax, eax
0x18001b680  jmp     loc_18001B376
0x18001b685  mov     ecx, 0C00000E5h; int
0x18001b68a  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
