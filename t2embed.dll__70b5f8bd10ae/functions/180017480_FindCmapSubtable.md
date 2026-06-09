# FindCmapSubtable

- ea: `0x180017480`
- end: `0x18001768b`
- name: `FindCmapSubtable`
- size: `523`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f298`
- `0x180016f54`
- `0x180017330`
- `0x180027c1c`
- `0x180027d28`

## callees

- `0x1800134b4`
- `0x180015190`
- `0x180017480`

## pseudocode

```c
__int64 __fastcall FindCmapSubtable(__int64 a1, __int16 a2, __int16 a3, _WORD *a4)
{
  unsigned int v7; // r13d
  unsigned int v8; // ebx
  int v9; // edi
  int v10; // r15d
  __int16 i; // r12
  __int16 j; // r12
  _WORD v14[2]; // [rsp+30h] [rbp-10h] BYREF
  int v15; // [rsp+34h] [rbp-Ch] BYREF
  __int64 v16; // [rsp+38h] [rbp-8h] BYREF

  v15 = 0;
  v16 = 0;
  v14[0] = 0;
  v7 = TTTableOffset(a1, "cmap");
  if ( !v7 )
    return 0;
  if ( (unsigned __int16)ReadGeneric((__int64 *)a1, (__int64)&v15, 4u, (unsigned __int8 *)CMAP_HEADER_CONTROL, v7, v14) )
    return 0;
  v8 = v7 + v14[0];
  if ( v8 > *(_DWORD *)(a1 + 8) || SHIWORD(v15) > 1000 )
    return 0;
  v9 = 0;
  v10 = 0;
  if ( a2 == 3 && a3 == -1 )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= SHIWORD(v15) )
        goto LABEL_31;
      if ( (unsigned __int16)ReadGeneric(
                               (__int64 *)a1,
                               (__int64)&v16,
                               8u,
                               (unsigned __int8 *)CMAP_TABLELOC_CONTROL,
                               v8,
                               v14) )
        return 0;
      if ( (_WORD)v16 == 3 )
      {
        if ( WORD1(v16) == 10 )
        {
          *a4 = 10;
LABEL_20:
          v10 = HIDWORD(v16);
          v9 = 1;
          goto LABEL_21;
        }
        if ( WORD1(v16) == 1 )
        {
          if ( !v9 || *a4 != 10 )
          {
            *a4 = 1;
            goto LABEL_20;
          }
        }
        else if ( !WORD1(v16) && !v9 )
        {
          *a4 = 0;
          goto LABEL_20;
        }
      }
LABEL_21:
      v8 += v14[0];
    }
  }
  for ( j = 0; j < SHIWORD(v15); ++j )
  {
    if ( v9 )
      return v10 + v7 < *(_DWORD *)(a1 + 8) ? v10 + v7 : 0;
    if ( (unsigned __int16)ReadGeneric(
                             (__int64 *)a1,
                             (__int64)&v16,
                             8u,
                             (unsigned __int8 *)CMAP_TABLELOC_CONTROL,
                             v8,
                             v14) )
      return 0;
    if ( (_WORD)v16 == a2 && (WORD1(v16) == a3 || a3 == -1) )
    {
      v9 = 1;
      v10 = HIDWORD(v16);
      *a4 = WORD1(v16);
    }
    v8 += v14[0];
  }
LABEL_31:
  if ( !v9 )
    return 0;
  return v10 + v7 < *(_DWORD *)(a1 + 8) ? v10 + v7 : 0;
}

```

## disassembly

```asm
0x180017480  mov     rax, rsp
0x180017483  mov     [rax+8], rbx
0x180017487  mov     [rax+20h], r9
0x18001748b  mov     [rax+18h], r8w
0x180017490  mov     [rax+10h], dx
0x180017494  push    rbp
0x180017495  push    rsi
0x180017496  push    rdi
0x180017497  push    r12
0x180017499  push    r13
0x18001749b  push    r14
0x18001749d  push    r15
0x18001749f  mov     rbp, rsp
0x1800174a2  sub     rsp, 40h
0x1800174a6  movzx   r12d, dx
0x1800174aa  mov     [rbp+var_C], 0
0x1800174b1  xor     eax, eax
0x1800174b3  mov     [rbp+var_8], 0
0x1800174bb  lea     rdx, aCmap; "cmap"
0x1800174c2  mov     [rbp+var_10], ax
0x1800174c6  movzx   esi, r8w
0x1800174ca  mov     r14, rcx
0x1800174cd  call    TTTableOffset
0x1800174d2  mov     r13d, eax
0x1800174d5  test    eax, eax
0x1800174d7  jz      loc_180017671
0x1800174dd  lea     rax, [rbp+var_10]
0x1800174e1  mov     r8d, 4
0x1800174e7  mov     [rsp+40h+var_18], rax
0x1800174ec  lea     r9, CMAP_HEADER_CONTROL
0x1800174f3  lea     rdx, [rbp+var_C]
0x1800174f7  mov     [rsp+40h+var_20], r13d
0x1800174fc  mov     rcx, r14
0x1800174ff  call    ReadGeneric
0x180017504  xor     ecx, ecx
0x180017506  test    ax, ax
0x180017509  jnz     loc_180017671
0x18001750f  movzx   ebx, [rbp+var_10]
0x180017513  add     ebx, r13d
0x180017516  cmp     ebx, [r14+8]
0x18001751a  ja      loc_180017671
0x180017520  mov     eax, 3E8h
0x180017525  cmp     word ptr [rbp+var_C+2], ax
0x180017529  jg      loc_180017671
0x18001752f  mov     edi, ecx
0x180017531  mov     r15d, ecx
0x180017534  mov     eax, 0FFFFh
0x180017539  cmp     r12w, 3
0x18001753e  jnz     loc_1800175E9
0x180017544  cmp     si, ax
0x180017547  jnz     loc_1800175E9
0x18001754d  mov     r12d, ecx
0x180017550  lea     esi, [rcx+1]
0x180017553  cmp     r12w, word ptr [rbp+var_C+2]
0x180017558  jge     loc_18001765F
0x18001755e  lea     rax, [rbp+var_10]
0x180017562  mov     r8d, 8
0x180017568  mov     [rsp+40h+var_18], rax
0x18001756d  lea     r9, CMAP_TABLELOC_CONTROL
0x180017574  lea     rdx, [rbp+var_8]
0x180017578  mov     [rsp+40h+var_20], ebx
0x18001757c  mov     rcx, r14
0x18001757f  call    ReadGeneric
0x180017584  xor     ecx, ecx
0x180017586  test    ax, ax
0x180017589  jnz     loc_180017671
0x18001758f  cmp     word ptr [rbp+var_8], 3
0x180017594  jnz     short loc_1800175DA
0x180017596  movzx   eax, word ptr [rbp+var_8+2]
0x18001759a  lea     edx, [rcx+0Ah]
0x18001759d  cmp     ax, dx
0x1800175a0  jnz     short loc_1800175AB
0x1800175a2  mov     rax, [rbp+arg_18]
0x1800175a6  mov     [rax], dx
0x1800175a9  jmp     short loc_1800175D4
0x1800175ab  cmp     ax, si
0x1800175ae  jnz     short loc_1800175C2
0x1800175b0  mov     rax, [rbp+arg_18]
0x1800175b4  test    edi, edi
0x1800175b6  jz      short loc_1800175BD
0x1800175b8  cmp     [rax], dx
0x1800175bb  jz      short loc_1800175DA
0x1800175bd  mov     [rax], si
0x1800175c0  jmp     short loc_1800175D4
0x1800175c2  test    ax, ax
0x1800175c5  jnz     short loc_1800175DA
0x1800175c7  test    edi, edi
0x1800175c9  jnz     short loc_1800175DA
0x1800175cb  mov     eax, ecx
0x1800175cd  mov     rcx, [rbp+arg_18]
0x1800175d1  mov     [rcx], ax
0x1800175d4  mov     r15d, dword ptr [rbp+var_8+4]
0x1800175d8  mov     edi, esi
0x1800175da  movzx   eax, [rbp+var_10]
0x1800175de  add     r12w, si
0x1800175e2  add     ebx, eax
0x1800175e4  jmp     loc_180017553
0x1800175e9  mov     r12d, ecx
0x1800175ec  mov     esi, 1
0x1800175f1  cmp     r12w, word ptr [rbp+var_C+2]
0x1800175f6  jge     short loc_18001765F
0x1800175f8  test    edi, edi
0x1800175fa  jnz     short loc_180017663
0x1800175fc  lea     rax, [rbp+var_10]
0x180017600  mov     rcx, r14
0x180017603  mov     [rsp+40h+var_18], rax
0x180017608  lea     r8d, [rdi+8]
0x18001760c  lea     r9, CMAP_TABLELOC_CONTROL
0x180017613  mov     [rsp+40h+var_20], ebx
0x180017617  lea     rdx, [rbp+var_8]
0x18001761b  call    ReadGeneric
0x180017620  test    ax, ax
0x180017623  jnz     short loc_180017671
0x180017625  movzx   eax, [rbp+arg_8]
0x180017629  cmp     word ptr [rbp+var_8], ax
0x18001762d  jnz     short loc_180017653
0x18001762f  movzx   eax, word ptr [rbp+var_8+2]
0x180017633  movzx   ecx, [rbp+arg_10]
0x180017637  cmp     ax, cx
0x18001763a  jz      short loc_180017646
0x18001763c  mov     edx, 0FFFFh
0x180017641  cmp     cx, dx
0x180017644  jnz     short loc_180017653
0x180017646  mov     rcx, [rbp+arg_18]
0x18001764a  mov     edi, esi
0x18001764c  mov     r15d, dword ptr [rbp+var_8+4]
0x180017650  mov     [rcx], ax
0x180017653  movzx   eax, [rbp+var_10]
0x180017657  add     r12w, si
0x18001765b  add     ebx, eax
0x18001765d  jmp     short loc_1800175F1
0x18001765f  test    edi, edi
0x180017661  jz      short loc_180017671
0x180017663  lea     ecx, [r15+r13]
0x180017667  cmp     ecx, [r14+8]
0x18001766b  sbb     eax, eax
0x18001766d  and     eax, ecx
0x18001766f  jmp     short loc_180017673
0x180017671  xor     eax, eax
0x180017673  mov     rbx, [rsp+40h+arg_0]
0x18001767b  add     rsp, 40h
0x18001767f  pop     r15
0x180017681  pop     r14
0x180017683  pop     r13
0x180017685  pop     r12
0x180017687  pop     rdi
0x180017688  pop     rsi
0x180017689  pop     rbp
0x18001768a  retn
```
