# MTX_Glyph_WriteCTFSpline

- ea: `0x1800059a0`
- end: `0x1800063f3`
- name: `MTX_Glyph_WriteCTFSpline`
- size: `2643`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180004320`

## callees

- `0x1800034b4`
- `0x1800059a0`
- `0x180006400`
- `0x180009c80`
- `0x18000b160`
- `0x18000bc10`
- `0x18000bd00`
- `0x18000d5a0`
- `0x18000d900`
- `0x18000ddd4`
- `0x18001a69c`

## import_xrefs

- `msvcrt!longjmp` at `0x1800059ef`
- `msvcrt!longjmp` at `0x180005cdb`
- `msvcrt!longjmp` at `0x180005d4e`
- `msvcrt!longjmp` at `0x180005e3d`
- `msvcrt!longjmp` at `0x180005ecb`
- `msvcrt!longjmp` at `0x180005f39`
- `msvcrt!longjmp` at `0x180005f50`
- `msvcrt!longjmp` at `0x180006091`
- `msvcrt!longjmp` at `0x1800060a1`
- `msvcrt!longjmp` at `0x1800060b1`
- `msvcrt!longjmp` at `0x1800060c8`
- `msvcrt!longjmp` at `0x180006164`
- `msvcrt!longjmp` at `0x18000628a`
- `msvcrt!longjmp` at `0x1800059ef`
- `msvcrt!longjmp` at `0x180005cdb`
- `msvcrt!longjmp` at `0x180005d4e`
- `msvcrt!longjmp` at `0x180005e3d`
- `msvcrt!longjmp` at `0x180005ecb`
- `msvcrt!longjmp` at `0x180005f39`
- `msvcrt!longjmp` at `0x180005f50`
- `msvcrt!longjmp` at `0x180006091`
- `msvcrt!longjmp` at `0x1800060a1`
- `msvcrt!longjmp` at `0x1800060b1`
- `msvcrt!longjmp` at `0x1800060c8`
- `msvcrt!longjmp` at `0x180006164`
- `msvcrt!longjmp` at `0x18000628a`

## pseudocode

```c
__int64 __fastcall MTX_Glyph_WriteCTFSpline(__int16 *a1, _QWORD *a2, int a3, _DWORD *a4)
{
  bool v4; // zf
  _DWORD *v5; // r15
  __int64 v6; // r14
  __int64 *v7; // r13
  __int64 v8; // r12
  unsigned int v10; // ecx
  unsigned int v11; // edx
  __int16 v13; // ax
  __int16 *v14; // rbp
  __int16 v15; // r15
  __int16 v16; // r12
  _BOOL8 v17; // rdx
  unsigned __int16 v18; // r13
  __int64 v19; // rcx
  __int16 *v20; // r14
  unsigned __int16 *v21; // rsi
  int v22; // ebx
  __int16 v23; // r8
  unsigned __int16 v24; // dx
  __int16 v25; // r11
  unsigned __int16 v26; // r10
  unsigned int i; // ecx
  __int64 v28; // r9
  __int16 v29; // ax
  __int16 v30; // ax
  __int16 v31; // bx
  BOOL v32; // ecx
  _QWORD *v33; // rsi
  _BYTE *v34; // rsi
  __int16 v35; // cx
  _BYTE *v36; // rbx
  __int16 v37; // ax
  __int16 v38; // cx
  __int16 v39; // cx
  __int16 v40; // cx
  __int16 v41; // ax
  __int16 v42; // cx
  __int64 v43; // rax
  _BYTE *v44; // rbx
  __int64 v45; // r8
  __int16 *v46; // r12
  unsigned __int64 v47; // rbx
  int v48; // ecx
  unsigned __int64 v49; // r9
  unsigned __int64 v50; // rbx
  unsigned __int64 v51; // r9
  __int16 v52; // cx
  int v53; // r12d
  int v54; // ebx
  unsigned __int16 v55; // dx
  __int64 v56; // r8
  __int16 v57; // cx
  __int16 v58; // r9
  unsigned __int16 v59; // r10
  unsigned __int16 v60; // r10
  _BYTE *v61; // r13
  __int64 v62; // rsi
  __int16 *v63; // rbp
  unsigned __int64 v64; // rcx
  __int64 v65; // r9
  __int16 v66; // r8
  __int64 v67; // rsi
  int v68; // ebp
  __int64 v69; // rdx
  __int64 v70; // rcx
  _BYTE *v71; // r13
  _BYTE *v72; // r9
  __int16 v73; // r15
  unsigned int v74; // edx
  __int16 v75; // r14
  int v76; // ecx
  __int16 v77; // r8
  unsigned int v78; // eax
  _BYTE *v79; // r13
  int v80; // eax
  unsigned int v81; // edx
  unsigned int v82; // eax
  unsigned int v83; // ecx
  _QWORD *v84; // r14
  int v85; // r12d
  int v86; // ebx
  _JBTYPE *v87; // rdx
  __int16 v88; // r10
  __int16 v89; // r11
  __int16 v90; // si
  __int64 v91; // rbp
  __int16 v92; // cx
  _BYTE *v93; // rdx
  __int64 v94; // rbx
  unsigned __int64 v95; // rdx
  __int16 v96; // r8
  __int64 v97; // rsi
  _BYTE *j; // rbx
  __int64 v99; // rcx
  __int16 v100; // dx
  __int64 v101; // r8
  __int64 v102; // r8
  __int64 v103; // rax
  unsigned __int64 v104; // rbx
  __int64 v105; // rcx
  _QWORD *v106; // rbx
  __int64 v107; // rbx
  __int16 v108; // [rsp+30h] [rbp-88h]
  _BYTE *v109; // [rsp+38h] [rbp-80h] BYREF
  __int64 v110; // [rsp+40h] [rbp-78h]
  __int64 v111; // [rsp+48h] [rbp-70h]
  unsigned __int64 v112; // [rsp+50h] [rbp-68h]
  __int64 v113; // [rsp+58h] [rbp-60h]
  __int16 *v114; // [rsp+60h] [rbp-58h]
  INT piResult; // [rsp+C0h] [rbp+8h] BYREF
  _QWORD *v116; // [rsp+C8h] [rbp+10h]
  int v117; // [rsp+D0h] [rbp+18h]
  _DWORD *v118; // [rsp+D8h] [rbp+20h]

  v118 = a4;
  v117 = a3;
  v116 = a2;
  v4 = a1[6] == 0;
  v5 = a4;
  v6 = a3;
  v7 = a2;
  v8 = a3;
  v113 = a3;
  if ( v4 )
  {
    if ( a3 < 0
      || (v10 = *a4, (int)*a4 < 0)
      || a3 + 2 < (unsigned int)a3
      || (v11 = a3 + 6, a3 + 6 < (unsigned int)(a3 + 2)) )
    {
      longjmp((_JBTYPE *)(*((_QWORD *)a1 + 17) + 48LL), 3321);
    }
    if ( v11 > v10 )
    {
      v103 = *v7;
      v101 = v11 + (v10 >> 1) + 2;
      if ( (unsigned int)v101 >= v11 && (unsigned int)v101 <= 0x7FFFFFFF )
      {
        *a4 = v101;
      }
      else
      {
        *a4 = 0x7FFFFFFF;
        v101 = 0x7FFFFFFF;
      }
      *v7 = MTX_mem_realloc(*((_QWORD *)a1 + 17), v103, v101);
    }
    *(_WORD *)(v6 + *v7) = 0;
    return 2;
  }
  if ( a1[33] > 0 )
  {
    VerifyConditionInternal(*((_QWORD *)a1 + 17), (unsigned __int16)a1[34] >> 15);
    AllocateGlyphSpace((_DWORD)a1, (_DWORD)v7, v6, 10, (__int64)v5);
    v38 = a1[34];
    v14 = a1;
    v34 = (_BYTE *)(v6 + *v7);
    *v34 = HIBYTE(v38);
    v36 = v34 + 9;
    v34[1] = v38;
    v39 = a1[1];
    v34[3] = v39;
    v34[2] = HIBYTE(v39);
    v40 = a1[3];
    v34[5] = v40;
    v34[4] = HIBYTE(v40);
    v41 = *a1;
    v34[7] = *a1;
    v34[6] = HIBYTE(v41);
    v42 = a1[2];
    v34[8] = HIBYTE(v42);
  }
  else
  {
    v13 = a1[3];
    v14 = a1;
    v15 = *a1;
    v16 = a1[1];
    v17 = a1[7] > 0;
    v18 = a1[2];
    v19 = *((_QWORD *)a1 + 17);
    LOWORD(piResult) = v13;
    VerifyConditionInternal(v19, v17);
    v20 = (__int16 *)*((_QWORD *)a1 + 4);
    v21 = (unsigned __int16 *)*((_QWORD *)a1 + 5);
    v22 = a1[7];
    v23 = *v20;
    v24 = *v21;
    v25 = *v20;
    v26 = *v21;
    if ( v22 > 1 )
    {
      for ( i = 1; (int)i < v22; ++i )
      {
        v28 = i;
        v29 = v20[v28];
        if ( v29 > v25 )
        {
          v25 = v20[i];
        }
        else if ( v29 < v23 )
        {
          v23 = v20[i];
        }
        v30 = v21[v28];
        if ( v30 > (__int16)v26 )
        {
          v26 = v21[v28];
        }
        else if ( v30 < (__int16)v24 )
        {
          v24 = v21[v28];
        }
      }
    }
    v31 = piResult;
    v6 = v117;
    v32 = v15 != v25 || v18 != v26;
    if ( v16 != v23 )
      v32 = 1;
    if ( (_WORD)piResult != v24 || v32 )
    {
      v33 = v116;
      AllocateGlyphSpace((_DWORD)a1, (_DWORD)v116, v117, 12, (__int64)v118);
      v34 = (_BYTE *)(v6 + *v33);
      *(_WORD *)v34 = -129;
      v35 = a1[6];
      v34[3] = v35;
      v34[2] = HIBYTE(v35);
      v34[4] = HIBYTE(v16);
      v34[5] = v16;
      v8 = v6;
      v34[6] = HIBYTE(v31);
      v34[7] = v31;
      v36 = v34 + 11;
      v34[8] = HIBYTE(v15);
      v34[9] = v15;
      v5 = v118;
      v37 = HIBYTE(v18);
      v34[11] = v18;
      v7 = v116;
      v34[10] = v37;
      goto LABEL_27;
    }
    v7 = v116;
    v5 = v118;
    AllocateGlyphSpace((_DWORD)a1, (_DWORD)v116, v117, 2, (__int64)v118);
    v42 = a1[6];
    v8 = v6;
    v34 = (_BYTE *)(v6 + *v7);
    *v34 = HIBYTE(v42);
    v36 = v34 + 1;
  }
  *v36 = v42;
LABEL_27:
  v43 = a1[33];
  v44 = v36 + 1;
  if ( (__int16)v43 > 0 )
  {
    v50 = v44 - v34;
    v51 = v50 + 2 * v43;
    if ( v51 > 0x7FFFFFFF || v51 < v50 )
      longjmp((_JBTYPE *)(*((_QWORD *)a1 + 17) + 48LL), 3321);
    piResult = v50 + 2 * v43;
    AllocateGlyphSpace((_DWORD)a1, (_DWORD)v7, v6, v51, (__int64)v5);
    v96 = 0;
    v97 = v8 + *v7;
    for ( j = (_BYTE *)(v97 + v50); v96 < a1[33]; j += 2 )
    {
      v99 = v96++;
      v100 = *(_WORD *)(*((_QWORD *)a1 + 7) + 2 * v99);
      j[1] = v100;
      *j = HIBYTE(v100);
    }
    if ( a1[35] )
    {
      j -= v97;
      if ( j + 6 < j || UIntPtrToInt((UINT_PTR)(j + 6), &piResult) < 0 )
        longjmp((_JBTYPE *)(*((_QWORD *)a1 + 17) + 48LL), 3321);
      AllocateGlyphSpace((_DWORD)a1, (_DWORD)v7, v6, piResult, (__int64)v5);
      v97 = v8 + *v7;
      v109 = &j[v97];
      PushInitialCTFStack(a1, &v109);
      WriteRemainingCTFCode(a1, &v109);
      LODWORD(j) = (_DWORD)v109;
    }
    return (unsigned int)((_DWORD)j - v97);
  }
  else
  {
    v45 = (unsigned int)v14[7];
    v46 = v14 + 7;
    v114 = v14 + 7;
    VerifyGlyphBuffersize(a1, 1, v45);
    v47 = v44 - v34;
    v111 = MTX_mem_malloc(*((_QWORD *)a1 + 17), (unsigned int)v14[7]);
    v48 = 3 * a1[6];
    v49 = v47 + v48;
    if ( v49 > 0x7FFFFFFF || v49 < v47 )
      longjmp((_JBTYPE *)(*((_QWORD *)a1 + 17) + 48LL), 3321);
    piResult = v47 + v48;
    AllocateGlyphSpace((_DWORD)a1, (_DWORD)v7, v6, v49, (__int64)v5);
    v90 = 0;
    v91 = (int)v6 + *v7;
    v92 = 0;
    v93 = (_BYTE *)(v47 + v91);
    v109 = (_BYTE *)(v47 + v91);
    if ( a1[6] > 0 )
    {
      do
      {
        v94 = 2LL * v90;
        Write255UShort(&v109, (unsigned __int16)(*(_WORD *)(v94 + *((_QWORD *)a1 + 3)) - v92));
        ++v90;
        v92 = *(_WORD *)(v94 + *((_QWORD *)a1 + 3));
      }
      while ( v90 < a1[6] );
      v93 = v109;
    }
    v95 = (unsigned __int64)&v93[-v91];
    v112 = v95;
    if ( v95 > 0x7FFFFFFF || (v104 = v95 + *v46, v104 < v95) || UIntPtrToInt(v95 + *v46, &piResult) < 0 )
      longjmp((_JBTYPE *)(*((_QWORD *)a1 + 17) + 48LL), 3321);
    AllocateGlyphSpace((_DWORD)a1, (_DWORD)v7, v6, piResult, (__int64)v5);
    v105 = (int)v6;
    v75 = 0;
    v110 = v105 + *v7;
    v79 = (_BYTE *)(v104 + v110);
    v80 = 0;
    v73 = 0;
    while ( 1 )
    {
      v52 = *v46;
      LODWORD(v109) = v80;
      if ( (__int16)v80 >= v52 )
        break;
      LOWORD(piResult) = *(_WORD *)(*((_QWORD *)a1 + 4) + 2LL * (__int16)v80);
      v53 = v73 - (__int16)piResult;
      v108 = *(_WORD *)(*((_QWORD *)a1 + 5) + 2LL * (__int16)v80);
      if ( (__int16)piResult - v73 >= 0 )
        v53 = (__int16)piResult - v73;
      v54 = v75 - v108;
      if ( v54 < 0 )
        v54 = v108 - v75;
      v55 = 0;
      while ( 1 )
      {
        v56 = 12LL * v55;
        v57 = *(_WORD *)((char *)qword_180031CA0 + v56 + 2);
        if ( !v57 || *((_BYTE *)&qword_180031CA0[1] + v56 + 2) == (__int16)piResult < v73 )
        {
          v58 = *(_WORD *)((char *)qword_180031CA0 + v56 + 4);
          if ( !v58 || *((_BYTE *)&qword_180031CA0[1] + v56 + 3) == v108 < v75 )
          {
            v59 = *(_WORD *)((char *)qword_180031CA0 + v56 + 6);
            if ( (unsigned __int16)v53 >= v59 && (unsigned __int16)v53 <= (unsigned __int16)(v59 + (1 << v57) - 1) )
            {
              v60 = *(_WORD *)((char *)&qword_180031CA0[1] + v56);
              if ( (unsigned __int16)v54 >= v60 && (unsigned __int16)v54 <= (unsigned __int16)(v60 + (1 << v58) - 1) )
                break;
            }
          }
        }
        if ( ++v55 >= 0x80u )
          longjmp((_JBTYPE *)(*((_QWORD *)a1 + 17) + 48LL), 3362);
      }
      v61 = &v79[-v110];
      *(_BYTE *)(v111 + (__int16)v80) = v55 | ((*(_BYTE *)(*((_QWORD *)a1 + 6) + (__int16)v80) ^ 1) << 7);
      v62 = 12LL * v55;
      v63 = (__int16 *)((char *)qword_180031CA0 + v62);
      v64 = (unsigned __int64)&v61[*(__int16 *)((char *)qword_180031CA0 + v62) - 1];
      if ( v64 > 0x7FFFFFFF || v64 < (unsigned __int64)v61 )
        longjmp((_JBTYPE *)(*((_QWORD *)a1 + 17) + 48LL), 3321);
      if ( v117 < 0
        || (v81 = *v118, (int)*v118 < 0)
        || (v82 = v64 + v117, (int)v64 + v117 < (unsigned int)v117)
        || (v83 = v82 + 4, v82 + 4 < v82) )
      {
        longjmp((_JBTYPE *)(*((_QWORD *)a1 + 17) + 48LL), 3321);
      }
      if ( v83 > v81 )
      {
        v102 = v83 + (v81 >> 1) + 2;
        if ( (unsigned int)v102 >= v83 && (unsigned int)v102 <= 0x7FFFFFFF )
        {
          *v118 = v102;
        }
        else
        {
          *v118 = 0x7FFFFFFF;
          v102 = 0x7FFFFFFF;
        }
        v84 = v116;
        *v84 = MTX_mem_realloc(*((_QWORD *)a1 + 17), *v116, v102);
      }
      else
      {
        v84 = v116;
      }
      v79 = &v61[v113 + *v84];
      v110 = v113 + *v84;
      v85 = v53 - *(__int16 *)((char *)qword_180031CA0 + v62 + 6);
      if ( v85 < 0 )
        longjmp((_JBTYPE *)(*((_QWORD *)a1 + 17) + 48LL), 3362);
      v86 = v54 - *(__int16 *)((char *)&qword_180031CA0[1] + v62);
      v87 = (_JBTYPE *)*((_QWORD *)a1 + 17);
      if ( v86 < 0 )
        longjmp(v87 + 3, 3362);
      v88 = *(_WORD *)((char *)qword_180031CA0 + v62 + 2);
      if ( v85 >= 1 << v88 )
        longjmp(v87 + 3, 3362);
      v89 = *(_WORD *)((char *)qword_180031CA0 + v62 + 4);
      if ( v86 >= 1 << v89 )
        longjmp(v87 + 3, 3362);
      v73 = piResult;
      v74 = 0;
      v75 = v108;
      if ( v88 > 0 )
        v74 = (v85 & ((1 << v88) - 1)) << (32 - v88);
      if ( v89 > 0 )
        v74 |= (v86 & ((1 << v89) - 1)) << (32 - v89 - v88);
      v76 = 24;
      v77 = 1;
      if ( *v63 > 1 )
      {
        do
        {
          ++v77;
          v78 = v74 >> v76;
          v76 -= 8;
          *v79++ = v78;
        }
        while ( v77 < *v63 );
      }
      HIWORD(v80) = WORD1(v109);
      v46 = v114;
      LOWORD(v80) = (_WORD)v109 + 1;
    }
    v65 = v110;
    v66 = 0;
    v67 = v111;
    if ( v52 > 0 )
    {
      v68 = v112;
      do
      {
        v69 = v66;
        v70 = v68 + v66++;
        *(_BYTE *)(v70 + v65) = *(_BYTE *)(v69 + v67);
      }
      while ( v66 < *v46 );
    }
    v71 = &v79[-v65];
    v72 = v71 + 6;
    if ( (unsigned __int64)(v71 + 6) > 0x7FFFFFFF || v72 < v71 )
      longjmp((_JBTYPE *)(*((_QWORD *)a1 + 17) + 48LL), 3321);
    v106 = v116;
    AllocateGlyphSpace((_DWORD)a1, (_DWORD)v116, v117, (_DWORD)v72, (__int64)v118);
    v107 = v113 + *v106;
    v109 = &v71[v107];
    PushInitialCTFStack(a1, &v109);
    WriteRemainingCTFCode(a1, &v109);
    DiscardPointer(*((_QWORD *)a1 + 17), v67, 1);
    return (unsigned int)((_DWORD)v109 - v107);
  }
}

```

## disassembly

```asm
0x1800059a0  mov     [rsp+arg_18], r9
0x1800059a5  mov     [rsp+arg_10], r8d
0x1800059aa  mov     [rsp+arg_8], rdx
0x1800059af  push    rdi
0x1800059b0  push    r12
0x1800059b2  push    r13
0x1800059b4  push    r14
0x1800059b6  push    r15
0x1800059b8  sub     rsp, 90h
0x1800059bf  cmp     word ptr [rcx+0Ch], 0
0x1800059c4  mov     r15, r9
0x1800059c7  movsxd  r14, r8d
0x1800059ca  mov     r13, rdx
0x1800059cd  mov     r12, r14
0x1800059d0  mov     [rsp+0B8h+var_60], r14
0x1800059d5  mov     rdi, rcx
0x1800059d8  jnz     short loc_180005A36
0x1800059da  test    r8d, r8d
0x1800059dd  jns     short loc_1800059F6
0x1800059df  mov     rcx, [rdi+88h]
0x1800059e6  mov     edx, 0CF9h; Value
0x1800059eb  add     rcx, 30h ; '0'; Buf
0x1800059ef  call    cs:__imp_longjmp
0x1800059f6  mov     ecx, [r9]
0x1800059f9  test    ecx, ecx
0x1800059fb  js      short loc_1800059DF
0x1800059fd  lea     eax, [r14+2]
0x180005a01  cmp     eax, r14d
0x180005a04  jb      short loc_1800059DF
0x180005a06  lea     edx, [rax+4]
0x180005a09  cmp     edx, eax
0x180005a0b  jb      short loc_1800059DF
0x180005a0d  cmp     edx, ecx
0x180005a0f  ja      loc_180006256
0x180005a15  mov     rax, [r13+0]
0x180005a19  mov     word ptr [r14+rax], 0
0x180005a20  mov     eax, 2
0x180005a25  add     rsp, 90h
0x180005a2c  pop     r15
0x180005a2e  pop     r14
0x180005a30  pop     r13
0x180005a32  pop     r12
0x180005a34  pop     rdi
0x180005a35  retn
0x180005a36  cmp     word ptr [rcx+42h], 0
0x180005a3b  mov     [rsp+0B8h+var_30], rbx
0x180005a43  mov     [rsp+0B8h+var_38], rbp
0x180005a4b  mov     [rsp+0B8h+var_40], rsi
0x180005a50  jg      loc_180005BD6
0x180005a56  movzx   eax, word ptr [rcx+6]
0x180005a5a  xor     edx, edx
0x180005a5c  cmp     [rcx+0Eh], dx
0x180005a60  mov     rbp, rdi
0x180005a63  movzx   r15d, word ptr [rcx]
0x180005a67  movzx   r12d, word ptr [rcx+2]
0x180005a6c  setnle  dl
0x180005a6f  movzx   r13d, word ptr [rcx+4]
0x180005a74  mov     rcx, [rcx+88h]
0x180005a7b  mov     word ptr [rsp+0B8h+piResult], ax
0x180005a83  call    VerifyConditionInternal
0x180005a88  mov     r14, [rdi+20h]
0x180005a8c  mov     rsi, [rdi+28h]
0x180005a90  movsx   ebx, word ptr [rdi+0Eh]
0x180005a94  movzx   r8d, word ptr [r14]
0x180005a98  movzx   edx, word ptr [rsi]
0x180005a9b  movzx   r11d, r8w
0x180005a9f  movzx   r10d, dx
0x180005aa3  cmp     ebx, 1
0x180005aa6  jle     short loc_180005AEA
0x180005aa8  mov     ecx, 1
0x180005aad  nop     dword ptr [rax]
0x180005ab0  mov     eax, ecx
0x180005ab2  lea     r9, [rax+rax]
0x180005ab6  movzx   eax, word ptr [r14+r9]
0x180005abb  cmp     ax, r11w
0x180005abf  jg      loc_180005BCD
0x180005ac5  cmp     ax, r8w
0x180005ac9  cmovl   r8w, ax
0x180005ace  movzx   eax, word ptr [r9+rsi]
0x180005ad3  cmp     ax, r10w
0x180005ad7  jg      loc_180005BC4
0x180005add  cmp     ax, dx
0x180005ae0  cmovl   dx, ax
0x180005ae4  inc     ecx
0x180005ae6  cmp     ecx, ebx
0x180005ae8  jl      short loc_180005AB0
0x180005aea  movzx   ebx, word ptr [rsp+0B8h+piResult]
0x180005af2  xor     ecx, ecx
0x180005af4  movsxd  r14, [rsp+0B8h+arg_10]
0x180005afc  cmp     r13w, r10w
0x180005b00  setnz   cl
0x180005b03  xor     eax, eax
0x180005b05  cmp     r15w, r11w
0x180005b09  setnz   al
0x180005b0c  or      ecx, eax
0x180005b0e  mov     eax, 1
0x180005b13  cmp     r12w, r8w
0x180005b17  mov     r8d, r14d
0x180005b1a  cmovnz  ecx, eax
0x180005b1d  xor     eax, eax
0x180005b1f  cmp     bx, dx
0x180005b22  setnz   al
0x180005b25  or      ecx, eax
0x180005b27  mov     rcx, rdi
0x180005b2a  jz      loc_180005CE2
0x180005b30  mov     rax, [rsp+0B8h+arg_18]
0x180005b38  mov     r9d, 0Ch
0x180005b3e  mov     rsi, [rsp+0B8h+arg_8]
0x180005b46  mov     rdx, rsi
0x180005b49  mov     [rsp+0B8h+var_98], rax
0x180005b4e  call    AllocateGlyphSpace
0x180005b53  mov     rsi, [rsi]
0x180005b56  add     rsi, r14
0x180005b59  mov     word ptr [rsi], 0FF7Fh
0x180005b5e  movzx   ecx, word ptr [rdi+0Ch]
0x180005b62  mov     [rsi+3], cl
0x180005b65  movzx   eax, cx
0x180005b68  shr     ax, 8
0x180005b6c  mov     [rsi+2], al
0x180005b6f  movzx   eax, r12w
0x180005b73  shr     ax, 8
0x180005b77  mov     [rsi+4], al
0x180005b7a  movzx   eax, bx
0x180005b7d  mov     [rsi+5], r12b
0x180005b81  mov     r12, r14
0x180005b84  shr     ax, 8
0x180005b88  mov     [rsi+6], al
0x180005b8b  movzx   eax, r15w
0x180005b8f  mov     [rsi+7], bl
0x180005b92  lea     rbx, [rsi+0Bh]
0x180005b96  shr     ax, 8
0x180005b9a  mov     [rsi+8], al
0x180005b9d  movzx   eax, r13w
0x180005ba1  mov     [rsi+9], r15b
0x180005ba5  mov     r15, [rsp+0B8h+arg_18]
0x180005bad  shr     ax, 8
0x180005bb1  mov     [rbx], r13b
0x180005bb4  mov     r13, [rsp+0B8h+arg_8]
0x180005bbc  mov     [rsi+0Ah], al
0x180005bbf  jmp     loc_180005C62
0x180005bc4  movzx   r10d, ax
0x180005bc8  jmp     loc_180005AE4
0x180005bcd  movzx   r11d, ax
0x180005bd1  jmp     loc_180005ACE
0x180005bd6  movzx   edx, word ptr [rcx+44h]
0x180005bda  mov     rcx, [rcx+88h]
0x180005be1  shr     edx, 0Fh
0x180005be4  call    VerifyConditionInternal
0x180005be9  mov     r9d, 0Ah
0x180005bef  mov     [rsp+0B8h+var_98], r15
0x180005bf4  mov     r8d, r14d
0x180005bf7  mov     rdx, r13
0x180005bfa  mov     rcx, rdi
0x180005bfd  call    AllocateGlyphSpace
0x180005c02  movzx   ecx, word ptr [rdi+44h]
0x180005c06  mov     rbp, rdi
0x180005c09  mov     rsi, [r13+0]
0x180005c0d  movzx   eax, cx
0x180005c10  add     rsi, r14
0x180005c13  shr     ax, 8
0x180005c17  mov     [rsi], al
0x180005c19  lea     rbx, [rsi+9]
0x180005c1d  mov     [rsi+1], cl
0x180005c20  movzx   ecx, word ptr [rdi+2]
0x180005c24  mov     [rsi+3], cl
0x180005c27  movzx   eax, cx
0x180005c2a  shr     ax, 8
0x180005c2e  mov     [rsi+2], al
0x180005c31  movzx   ecx, word ptr [rdi+6]
0x180005c35  mov     [rsi+5], cl
0x180005c38  movzx   eax, cx
0x180005c3b  shr     ax, 8
0x180005c3f  mov     [rsi+4], al
0x180005c42  movzx   ecx, word ptr [rdi]
0x180005c45  movzx   eax, cx
0x180005c48  mov     [rsi+7], cl
0x180005c4b  shr     ax, 8
0x180005c4f  mov     [rsi+6], al
0x180005c52  movzx   ecx, word ptr [rdi+4]
0x180005c56  movzx   eax, cx
0x180005c59  shr     ax, 8
0x180005c5d  mov     [rsi+8], al
0x180005c60  mov     [rbx], cl
0x180005c62  movsx   rax, word ptr [rdi+42h]
0x180005c67  inc     rbx
0x180005c6a  mov     ecx, 0Eh
0x180005c6f  test    ax, ax
0x180005c72  jg      loc_180005D25
0x180005c78  movsx   r8d, word ptr [rcx+rbp]
0x180005c7d  lea     r12, [rcx+rbp]
0x180005c81  mov     edx, 1
0x180005c86  mov     [rsp+0B8h+var_58], r12
0x180005c8b  mov     rcx, rdi
0x180005c8e  call    VerifyGlyphBuffersize
0x180005c93  movsx   edx, word ptr [r12]
0x180005c98  mov     rcx, [rdi+88h]
0x180005c9f  call    MTX_mem_malloc
0x180005ca4  sub     rbx, rsi
0x180005ca7  mov     [rsp+0B8h+var_70], rax
0x180005cac  movsx   eax, word ptr [rdi+0Ch]
0x180005cb0  lea     ecx, [rax+rax*2]
0x180005cb3  movsxd  r9, ecx
0x180005cb6  add     r9, rbx
0x180005cb9  cmp     r9, 7FFFFFFFh
0x180005cc0  ja      short loc_180005CCB
0x180005cc2  cmp     r9, rbx
0x180005cc5  jnb     loc_1800060CF
0x180005ccb  mov     rcx, [rdi+88h]
0x180005cd2  mov     edx, 0CF9h; Value
0x180005cd7  add     rcx, 30h ; '0'; Buf
0x180005cdb  call    cs:__imp_longjmp
0x180005ce2  mov     r13, [rsp+0B8h+arg_8]
0x180005cea  mov     r9d, 2
0x180005cf0  mov     r15, [rsp+0B8h+arg_18]
0x180005cf8  mov     rdx, r13
0x180005cfb  mov     [rsp+0B8h+var_98], r15
0x180005d00  call    AllocateGlyphSpace
0x180005d05  movzx   ecx, word ptr [rdi+0Ch]
0x180005d09  mov     r12, r14
0x180005d0c  mov     rsi, [r13+0]
0x180005d10  movzx   eax, cx
0x180005d13  add     rsi, r14
0x180005d16  shr     ax, 8
0x180005d1a  mov     [rsi], al
0x180005d1c  lea     rbx, [rsi+1]
0x180005d20  jmp     loc_180005C60
0x180005d25  sub     rbx, rsi
0x180005d28  lea     r9, [rbx+rax*2]
0x180005d2c  cmp     r9, 7FFFFFFFh
0x180005d33  ja      short loc_180005D3E
0x180005d35  cmp     r9, rbx
0x180005d38  jnb     loc_18000616B
0x180005d3e  mov     rcx, [rdi+88h]
0x180005d45  mov     edx, 0CF9h; Value
0x180005d4a  add     rcx, 30h ; '0'; Buf
0x180005d4e  call    cs:__imp_longjmp
0x180005d55  movzx   ecx, word ptr [r12]
0x180005d5a  lea     r10, qword_180031CA0
0x180005d61  mov     dword ptr [rsp+0B8h+var_80], eax
0x180005d65  cmp     ax, cx
0x180005d68  jge     loc_180005ED2
0x180005d6e  movsx   rbp, ax
0x180005d72  mov     rax, [rdi+20h]
0x180005d76  movsx   r12d, r15w
0x180005d7a  movsx   eax, word ptr [rax+rbp*2]
0x180005d7e  mov     ecx, eax
0x180005d80  mov     word ptr [rsp+0B8h+piResult], ax
0x180005d88  mov     r11d, eax
0x180005d8b  mov     rax, [rdi+28h]
0x180005d8f  sub     r11d, r12d
0x180005d92  sub     r12d, ecx
0x180005d95  movsx   eax, word ptr [rax+rbp*2]
0x180005d99  mov     esi, eax
0x180005d9b  mov     [rsp+0B8h+var_88], ax
0x180005da0  movsx   eax, r14w
0x180005da4  sub     esi, eax
0x180005da6  test    r11d, r11d
0x180005da9  mov     ebx, esi
0x180005dab  cmovns  r12d, r11d
0x180005daf  shr     r11d, 1Fh
0x180005db3  neg     ebx
0x180005db5  cmovs   ebx, esi
0x180005db8  shr     esi, 1Fh
0x180005dbb  xor     edx, edx
0x180005dbd  nop     dword ptr [rax]
0x180005dc0  movzx   eax, dx
0x180005dc3  lea     rcx, [rax+rax*2]
0x180005dc7  lea     r8, ds:0[rcx*4]
0x180005dcf  movzx   ecx, word ptr [r8+r10+2]
0x180005dd5  test    cx, cx
0x180005dd8  jz      short loc_180005DE1
0x180005dda  cmp     [r8+r10+0Ah], r11b
0x180005ddf  jnz     short loc_180005E20
0x180005de1  movzx   r9d, word ptr [r8+r10+4]
0x180005de7  test    r9w, r9w
0x180005deb  jz      short loc_180005DF4
0x180005ded  cmp     [r8+r10+0Bh], sil
0x180005df2  jnz     short loc_180005E20
0x180005df4  movzx   r10d, word ptr [r8+r10+6]
0x180005dfa  cmp     r12w, r10w
0x180005dfe  jb      short loc_180005E19
0x180005e00  mov     r14d, 1
0x180005e06  mov     eax, r14d
0x180005e09  shl     ax, cl
0x180005e0c  dec     ax
0x180005e0f  add     ax, r10w
0x180005e13  cmp     r12w, ax
0x180005e17  jbe     short loc_180005E44
0x180005e19  lea     r10, qword_180031CA0
0x180005e20  inc     dx
0x180005e23  mov     eax, 80h
0x180005e28  cmp     dx, ax
0x180005e2b  jb      short loc_180005DC0
0x180005e2d  mov     rcx, [rdi+88h]
0x180005e34  mov     edx, 0D22h; Value
0x180005e39  add     rcx, 30h ; '0'; Buf
0x180005e3d  call    cs:__imp_longjmp
0x180005e44  lea     r15, qword_180031CA0
0x180005e4b  movzx   r10d, word ptr [r8+r15+8]
0x180005e51  cmp     bx, r10w
  ... truncated ...
```
