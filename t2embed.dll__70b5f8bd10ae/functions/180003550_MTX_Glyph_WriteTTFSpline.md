# MTX_Glyph_WriteTTFSpline

- ea: `0x180003550`
- end: `0x180004019`
- name: `MTX_Glyph_WriteTTFSpline`
- size: `2761`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004320`

## callees

- `0x1800034b4`
- `0x180003550`
- `0x180006400`
- `0x18000ddd4`
- `0x18002b010`

## import_xrefs

- `msvcrt!longjmp` at `0x180003595`
- `msvcrt!longjmp` at `0x180003697`
- `msvcrt!longjmp` at `0x1800036a7`
- `msvcrt!longjmp` at `0x1800036d6`
- `msvcrt!longjmp` at `0x18000375c`
- `msvcrt!longjmp` at `0x180003780`
- `msvcrt!longjmp` at `0x18000394b`
- `msvcrt!longjmp` at `0x180003a2e`
- `msvcrt!longjmp` at `0x180003a49`
- `msvcrt!longjmp` at `0x180003b15`
- `msvcrt!longjmp` at `0x180003c59`
- `msvcrt!longjmp` at `0x180003c88`
- `msvcrt!longjmp` at `0x180003c9f`
- `msvcrt!longjmp` at `0x180003cb6`
- `msvcrt!longjmp` at `0x180003ccd`
- `msvcrt!longjmp` at `0x180003d4b`
- `msvcrt!longjmp` at `0x180003595`
- `msvcrt!longjmp` at `0x180003697`
- `msvcrt!longjmp` at `0x1800036a7`
- `msvcrt!longjmp` at `0x1800036d6`
- `msvcrt!longjmp` at `0x18000375c`
- `msvcrt!longjmp` at `0x180003780`
- `msvcrt!longjmp` at `0x18000394b`
- `msvcrt!longjmp` at `0x180003a2e`
- `msvcrt!longjmp` at `0x180003a49`
- `msvcrt!longjmp` at `0x180003b15`
- `msvcrt!longjmp` at `0x180003c59`
- `msvcrt!longjmp` at `0x180003c88`
- `msvcrt!longjmp` at `0x180003c9f`
- `msvcrt!longjmp` at `0x180003cb6`
- `msvcrt!longjmp` at `0x180003ccd`
- `msvcrt!longjmp` at `0x180003d4b`

## pseudocode

```c
__int64 __fastcall MTX_Glyph_WriteTTFSpline(__int16 *a1, _QWORD *a2, int a3, unsigned int *a4)
{
  __int64 v5; // r12
  unsigned int v8; // ecx
  unsigned int v9; // edx
  __int16 v10; // dx
  _BYTE *v11; // r14
  __int16 v12; // cx
  __int16 v13; // cx
  __int16 v14; // cx
  __int16 v15; // cx
  _JBTYPE *v16; // rcx
  __int64 v17; // rsi
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // r9
  unsigned __int16 v20; // r13
  __int64 v21; // r9
  __int16 v22; // r8
  _BYTE *i; // rdi
  __int64 v24; // rcx
  __int16 v25; // dx
  _BYTE *v26; // rdi
  unsigned __int64 v27; // r9
  __int16 v28; // cx
  __int64 v29; // r9
  _BYTE *v30; // r8
  __int64 v32; // r9
  __int16 v33; // r11
  __int64 v34; // r12
  _BYTE *m; // rdi
  __int64 v36; // rax
  __int64 v37; // r8
  char v38; // r10
  __int64 v39; // rdx
  char v40; // al
  __int64 *v41; // r14
  __int64 v42; // rbp
  int v43; // ebx
  __int64 v44; // r15
  __int64 v45; // rax
  __int64 v46; // rdx
  __int16 v47; // ax
  __int16 v48; // r11
  __int16 v49; // bp
  __int64 v50; // rax
  char v51; // dl
  __int16 v52; // r9
  __int64 v53; // rax
  __int16 v54; // r9
  __int64 v55; // r15
  _BYTE *v56; // rdi
  unsigned __int64 v57; // rcx
  unsigned int v58; // edx
  unsigned int v59; // eax
  unsigned int v60; // ecx
  __int16 v61; // r9
  __int64 v62; // r15
  __int64 v63; // r14
  _BYTE *v64; // rdi
  __int16 v65; // cx
  __int16 v66; // dx
  unsigned __int8 v67; // r10
  char v68; // cl
  _BYTE *v69; // rdi
  unsigned __int64 v70; // rcx
  __int16 v71; // cx
  unsigned __int16 v72; // dx
  __int64 v73; // r14
  _BYTE *k; // rdi
  __int64 v75; // rcx
  __int16 v76; // r9
  __int16 v77; // r11
  __int64 v78; // r15
  __int16 v79; // ax
  __int64 v80; // r14
  _BYTE *v81; // rdi
  __int64 v82; // rax
  char v83; // r10
  char v84; // dl
  char v85; // al
  _BYTE *v86; // rdi
  unsigned __int64 v87; // rcx
  __int64 v88; // r10
  __int16 v89; // r8
  __int64 v90; // r9
  _BYTE *j; // rdi
  __int64 v92; // rcx
  __int16 v93; // dx
  _BYTE *v94; // rdi
  unsigned __int64 v95; // rcx
  unsigned int v96; // edx
  unsigned int v97; // eax
  unsigned int v98; // ecx
  unsigned int v99; // edx
  unsigned int v100; // eax
  unsigned int v101; // ecx
  unsigned int v102; // edx
  unsigned int v103; // eax
  unsigned int v104; // ecx
  unsigned int v105; // eax
  unsigned int v106; // ecx
  __int64 v107; // r8
  __int64 v108; // r8
  __int64 v109; // r8
  __int64 v110; // r8
  __int64 v111; // r8
  __int64 v112; // r8
  __int64 v113; // [rsp+80h] [rbp+8h]

  v5 = a3;
  if ( !a1[6] )
    return 0;
  if ( a3 < 0
    || (v8 = *a4, (*a4 & 0x80000000) != 0)
    || a3 + 10 < (unsigned int)a3
    || (v9 = a3 + 14, a3 + 14 < (unsigned int)(a3 + 10)) )
  {
    longjmp((_JBTYPE *)(*((_QWORD *)a1 + 17) + 48LL), 3321);
  }
  if ( v9 > v8 )
  {
    v107 = v9 + (v8 >> 1) + 2;
    if ( (unsigned int)v107 >= v9 && (unsigned int)v107 <= 0x7FFFFFFF )
    {
      *a4 = v107;
    }
    else
    {
      *a4 = 0x7FFFFFFF;
      v107 = 0x7FFFFFFF;
    }
    *a2 = MTX_mem_realloc(*((_QWORD *)a1 + 17), *a2, v107);
  }
  if ( a1[33] > 0 )
  {
    v10 = a1[34];
    if ( v10 >= 0 )
      longjmp((_JBTYPE *)(*((_QWORD *)a1 + 17) + 48LL), 3362);
  }
  else
  {
    v10 = a1[6];
  }
  v11 = (_BYTE *)(v5 + *a2);
  *v11 = HIBYTE(v10);
  v11[1] = v10;
  v12 = a1[1];
  v11[3] = v12;
  v11[2] = HIBYTE(v12);
  v13 = a1[3];
  v11[5] = v13;
  v11[4] = HIBYTE(v13);
  v14 = *a1;
  v11[7] = *a1;
  v11[6] = HIBYTE(v14);
  v15 = a1[2];
  v11[9] = v15;
  v11[8] = HIBYTE(v15);
  if ( a1[33] > 0 )
  {
    v19 = (unsigned int)(2 * a1[33]) + 10LL;
    if ( v19 < 0xA || v19 > 0x7FFFFFFF )
      longjmp((_JBTYPE *)(*((_QWORD *)a1 + 17) + 48LL), 3321);
    AllocateGlyphSpace((_DWORD)a1, (_DWORD)a2, v5, v19, (__int64)a4);
    v20 = 0;
    v21 = v5 + *a2;
    v22 = 0;
    for ( i = (_BYTE *)(v21 + 10); v22 < a1[33]; i += 2 )
    {
      v24 = v22++;
      v25 = *(_WORD *)(*((_QWORD *)a1 + 7) + 2 * v24);
      i[1] = v25;
      *i = HIBYTE(v25);
    }
    v26 = &i[-v21];
    v27 = (unsigned __int64)&v26[(unsigned __int16)a1[35] + 2];
    if ( v27 < (unsigned __int64)v26 || v27 > 0x7FFFFFFF )
      longjmp((_JBTYPE *)(*((_QWORD *)a1 + 17) + 48LL), 3321);
    AllocateGlyphSpace((_DWORD)a1, (_DWORD)a2, v5, v27, (__int64)a4);
    v28 = a1[35];
    v29 = v5 + *a2;
    v30 = &v26[v29];
    if ( v28 )
    {
      v30[1] = v28;
      *v30 = HIBYTE(v28);
      v30 += 2;
      if ( a1[35] )
      {
        do
        {
          v46 = v20++;
          *v30++ = *(_BYTE *)(v46 + *((_QWORD *)a1 + 9));
        }
        while ( v20 < (unsigned __int16)a1[35] );
      }
    }
    return (unsigned int)((_DWORD)v30 - v29);
  }
  else
  {
    v16 = (_JBTYPE *)*((_QWORD *)a1 + 17);
    if ( a1[7] < 0 )
      longjmp(v16 + 3, 3362);
    v17 = MTX_mem_malloc(v16, (unsigned int)a1[7]);
    v18 = 2 * a1[6] + 10LL;
    if ( v18 > 0x7FFFFFFF || v18 < 0xA )
      longjmp((_JBTYPE *)(*((_QWORD *)a1 + 17) + 48LL), 3321);
    v96 = *a4;
    if ( (*a4 & 0x80000000) != 0
      || (v97 = v18 + v5, (int)v18 + (int)v5 < (unsigned int)v5)
      || (v98 = v97 + 4, v97 + 4 < v97) )
    {
      longjmp((_JBTYPE *)(*((_QWORD *)a1 + 17) + 48LL), 3321);
    }
    if ( v98 > v96 )
    {
      v108 = v98 + (v96 >> 1) + 2;
      if ( (unsigned int)v108 >= v98 && (unsigned int)v108 <= 0x7FFFFFFF )
      {
        *a4 = v108;
      }
      else
      {
        *a4 = 0x7FFFFFFF;
        v108 = 0x7FFFFFFF;
      }
      *a2 = MTX_mem_realloc(*((_QWORD *)a1 + 17), *a2, v108);
    }
    v88 = *a2;
    v89 = 0;
    v90 = *a2 + v5;
    for ( j = (_BYTE *)(v90 + 10); v89 < a1[6]; j += 2 )
    {
      v92 = v89++;
      v93 = *(_WORD *)(*((_QWORD *)a1 + 3) + 2 * v92);
      j[1] = v93;
      *j = HIBYTE(v93);
    }
    v94 = &j[-v90];
    v95 = (unsigned __int64)&v94[(unsigned __int16)a1[35] + 2];
    if ( v95 > 0x7FFFFFFF || v95 < (unsigned __int64)v94 )
      longjmp((_JBTYPE *)(*((_QWORD *)a1 + 17) + 48LL), 3321);
    v99 = *a4;
    if ( (*a4 & 0x80000000) != 0
      || (v100 = v95 + v5, (int)v95 + (int)v5 < (unsigned int)v5)
      || (v101 = v100 + 4, v100 + 4 < v100) )
    {
      longjmp((_JBTYPE *)(*((_QWORD *)a1 + 17) + 48LL), 3321);
    }
    if ( v101 > v99 )
    {
      v109 = v101 + (v99 >> 1) + 2;
      if ( (unsigned int)v109 >= v101 && (unsigned int)v109 <= 0x7FFFFFFF )
      {
        *a4 = v109;
      }
      else
      {
        *a4 = 0x7FFFFFFF;
        v109 = 0x7FFFFFFF;
      }
      *a2 = MTX_mem_realloc(*((_QWORD *)a1 + 17), v88, v109);
    }
    v71 = a1[35];
    v72 = 0;
    v55 = *a2;
    v73 = *a2 + v5;
    v113 = *a2;
    v94[v73] = HIBYTE(v71);
    v94[v73 + 1] = v71;
    for ( k = &v94[v73 + 2]; v72 < (unsigned __int16)a1[35]; ++k )
    {
      v75 = v72++;
      *k = *(_BYTE *)(v75 + *((_QWORD *)a1 + 9));
    }
    v47 = a1[7];
    v37 = 0;
    v48 = 0;
    v49 = 0;
    if ( v47 > 0 )
    {
      do
      {
        v50 = *((_QWORD *)a1 + 4);
        v51 = *(_BYTE *)((__int16)v37 + *((_QWORD *)a1 + 6)) & 1;
        v52 = *(_WORD *)(v50 + 2LL * (__int16)v37) - v49;
        v49 = *(_WORD *)(v50 + 2LL * (__int16)v37);
        if ( !v52 || (unsigned __int16)(v52 + 255) <= 0x1FEu && (v51 |= 2u, v52 > 0) )
          v51 |= 0x10u;
        v53 = *((_QWORD *)a1 + 5);
        v54 = *(_WORD *)(v53 + 2LL * (__int16)v37) - v48;
        v48 = *(_WORD *)(v53 + 2LL * (__int16)v37);
        if ( !v54 || (unsigned __int16)(v54 + 255) <= 0x1FEu && (v51 |= 4u, v54 > 0) )
          v51 |= 0x20u;
        *(_BYTE *)((__int16)v37 + v17) = v51;
        LOWORD(v37) = v37 + 1;
        v47 = a1[7];
      }
      while ( (__int16)v37 < v47 );
      v55 = v113;
    }
    v56 = &k[-v73];
    v57 = (unsigned __int64)&v56[v47];
    if ( v57 < (unsigned __int64)v56 || v57 > 0x7FFFFFFF )
      longjmp((_JBTYPE *)(*((_QWORD *)a1 + 17) + 48LL), 3321);
    v58 = *a4;
    if ( (*a4 & 0x80000000) != 0 || (v59 = v57 + a3, (int)v57 + a3 < (unsigned int)a3) || (v60 = v59 + 4, v59 + 4 < v59) )
      longjmp((_JBTYPE *)(*((_QWORD *)a1 + 17) + 48LL), 3321);
    if ( v60 > v58 )
    {
      v110 = v60 + (v58 >> 1) + 2;
      if ( (unsigned int)v110 >= v60 && (unsigned int)v110 <= 0x7FFFFFFF )
      {
        *a4 = v110;
      }
      else
      {
        *a4 = 0x7FFFFFFF;
        v110 = 0x7FFFFFFF;
      }
      *a2 = MTX_mem_realloc(*((_QWORD *)a1 + 17), v55, v110);
    }
    v61 = a1[7];
    v62 = *a2;
    v63 = *a2 + a3;
    v64 = &v56[v63];
    if ( v61 > 0 )
    {
      v65 = 0;
      do
      {
        v66 = v65 + 1;
        v67 = 0;
        v37 = (unsigned __int16)(v65 + 1);
        if ( (__int16)(v65 + 1) < v61 )
        {
          do
          {
            if ( *(_BYTE *)(v65 + v17) != *(_BYTE *)((__int16)v37 + v17) )
              break;
            if ( v67 == 0xFF )
              break;
            ++v67;
            LOWORD(v37) = v37 + 1;
          }
          while ( (__int16)v37 < v61 );
        }
        v68 = *(_BYTE *)(v65 + v17);
        if ( v67 > 1u )
        {
          *v64 = v68 | 8;
          v65 = v37;
          v64[1] = v67;
          v64 += 2;
        }
        else
        {
          *v64++ = v68;
          v65 = v66;
        }
        v61 = a1[7];
      }
      while ( v65 < v61 );
    }
    v69 = &v64[-v63];
    v70 = (unsigned __int64)&v69[2 * v61];
    if ( v70 > 0x7FFFFFFF || v70 < (unsigned __int64)v69 )
      longjmp((_JBTYPE *)(*((_QWORD *)a1 + 17) + 48LL), 3321);
    v102 = *a4;
    if ( (*a4 & 0x80000000) != 0
      || (v103 = v70 + a3, (int)v70 + a3 < (unsigned int)a3)
      || (v104 = v103 + 4, v103 + 4 < v103) )
    {
      longjmp((_JBTYPE *)(*((_QWORD *)a1 + 17) + 48LL), 3321);
    }
    if ( v104 > v102 )
    {
      v111 = v104 + (v102 >> 1) + 2;
      if ( (unsigned int)v111 >= v104 && (unsigned int)v111 <= 0x7FFFFFFF )
      {
        *a4 = v111;
      }
      else
      {
        *a4 = 0x7FFFFFFF;
        v111 = 0x7FFFFFFF;
      }
      *a2 = MTX_mem_realloc(*((_QWORD *)a1 + 17), v62, v111);
    }
    v76 = 0;
    v77 = 0;
    v78 = *a2;
    v79 = a1[7];
    v80 = *a2 + a3;
    v81 = &v69[v80];
    if ( v79 > 0 )
    {
      do
      {
        v82 = *((_QWORD *)a1 + 4);
        v37 = *(unsigned __int16 *)(v82 + 2LL * v76);
        LOWORD(v37) = v37 - v77;
        v77 = *(_WORD *)(v82 + 2LL * v76);
        LOBYTE(v82) = *(_BYTE *)(v17 + v76);
        v83 = v37;
        v84 = v82 & 0x10;
        if ( (v82 & 2) != 0 )
        {
          LOBYTE(v37) = -(char)v37;
          v85 = v37;
          if ( v84 )
            v85 = v83;
          *v81++ = v85;
        }
        else if ( !v84 )
        {
          v81[1] = v37;
          *v81 = BYTE1(v37);
          v81 += 2;
        }
        v79 = a1[7];
        ++v76;
      }
      while ( v76 < v79 );
    }
    v86 = &v81[-v80];
    v87 = (unsigned __int64)&v86[2 * v79];
    if ( v87 > 0x7FFFFFFF || v87 < (unsigned __int64)v86 )
      longjmp((_JBTYPE *)(*((_QWORD *)a1 + 17) + 48LL), 3321);
    v39 = *a4;
    if ( (int)v39 < 0 || (v105 = v87 + a3, (int)v87 + a3 < (unsigned int)a3) || (v106 = v105 + 4, v105 + 4 < v105) )
      longjmp((_JBTYPE *)(*((_QWORD *)a1 + 17) + 48LL), 3321);
    if ( v106 > (unsigned int)v39 )
    {
      v112 = v106 + ((unsigned int)v39 >> 1) + 2;
      if ( (unsigned int)v112 >= v106 && (unsigned int)v112 <= 0x7FFFFFFF )
      {
        *a4 = v112;
      }
      else
      {
        *a4 = 0x7FFFFFFF;
        v112 = 0x7FFFFFFF;
      }
      *a2 = MTX_mem_realloc(*((_QWORD *)a1 + 17), v78, v112);
    }
    v32 = 0;
    v33 = 0;
    v34 = *a2 + a3;
    for ( m = &v86[v34]; (__int16)v32 < a1[7]; LOWORD(v32) = v32 + 1 )
    {
      v36 = *((_QWORD *)a1 + 5);
      v37 = *(unsigned __int16 *)(v36 + 2LL * (__int16)v32);
      LOWORD(v37) = v37 - v33;
      v33 = *(_WORD *)(v36 + 2LL * (__int16)v32);
      LOBYTE(v36) = *(_BYTE *)(v17 + (__int16)v32);
      v39 = (unsigned __int8)v36;
      v38 = v37;
      LOBYTE(v39) = v36 & 0x20;
      if ( (v36 & 4) != 0 )
      {
        LOBYTE(v37) = -(char)v37;
        v40 = v37;
        if ( (_BYTE)v39 )
          v40 = v38;
        *m++ = v40;
      }
      else if ( !(_BYTE)v39 )
      {
        m[1] = v37;
        *m = BYTE1(v37);
        m += 2;
      }
    }
    if ( v17 )
    {
      v41 = (__int64 *)*((_QWORD *)a1 + 17);
      v42 = *v41;
      v43 = *((_DWORD *)v41 + 3);
      do
      {
        if ( --v43 < 0 )
          longjmp((_JBTYPE *)v41 + 3, 3358);
        v44 = v42 + 16LL * v43;
      }
      while ( *(_QWORD *)v44 != v17 );
      ((void (__fastcall *)(__int64, __int64, __int64, __int64))v41[5])(v17, v39, v37, v32);
      v45 = *((int *)v41 + 3);
      if ( (int)v45 + ~v43 > 0 )
      {
        *(_QWORD *)v44 = *(_QWORD *)(v42 + 16 * v45 - 16);
        *(_DWORD *)(v44 + 8) = *(_DWORD *)(v42 + 16LL * *((int *)v41 + 3) - 8);
        *(_QWORD *)(v42 + 16LL * *((int *)v41 + 3) - 16) = 0;
        *(_DWORD *)(v42 + 16LL * *((int *)v41 + 3) - 8) = 0;
      }
      else
      {
        *(_QWORD *)v44 = 0;
        *(_DWORD *)(v44 + 8) = 0;
      }
      --*((_DWORD *)v41 + 3);
    }
    return (unsigned int)((_DWORD)m - v34);
  }
}

```

## disassembly

```asm
0x180003550  mov     [rsp+arg_18], r9
0x180003555  mov     [rsp+arg_10], r8d
0x18000355a  mov     [rsp+arg_8], rdx
0x18000355f  push    rbx
0x180003560  push    rbp
0x180003561  push    r12
0x180003563  push    r15
0x180003565  sub     rsp, 58h
0x180003569  cmp     word ptr [rcx+0Ch], 0
0x18000356e  mov     r15, r9
0x180003571  movsxd  r12, r8d
0x180003574  mov     rbp, rdx
0x180003577  mov     rbx, rcx
0x18000357a  jz      loc_180003FDF
0x180003580  test    r8d, r8d
0x180003583  jns     short loc_18000359C
0x180003585  mov     rcx, [rbx+88h]
0x18000358c  mov     edx, 0CF9h; Value
0x180003591  add     rcx, 30h ; '0'; Buf
0x180003595  call    cs:__imp_longjmp
0x18000359c  mov     ecx, [r9]
0x18000359f  test    ecx, ecx
0x1800035a1  js      short loc_180003585
0x1800035a3  lea     eax, [r12+0Ah]
0x1800035a8  cmp     eax, r12d
0x1800035ab  jb      short loc_180003585
0x1800035ad  lea     edx, [rax+4]
0x1800035b0  cmp     edx, eax
0x1800035b2  jb      short loc_180003585
0x1800035b4  cmp     edx, ecx
0x1800035b6  ja      loc_180003F55
0x1800035bc  cmp     word ptr [rbx+42h], 0
0x1800035c1  jg      loc_180003763
0x1800035c7  movzx   edx, word ptr [rbx+0Ch]
0x1800035cb  mov     [rsp+78h+var_28], rsi
0x1800035d0  movzx   ecx, dx
0x1800035d3  shr     cx, 8
0x1800035d7  mov     [rsp+78h+var_30], rdi
0x1800035dc  mov     [rsp+78h+var_38], r13
0x1800035e1  mov     [rsp+78h+var_40], r14
0x1800035e6  mov     r14, [rbp+0]
0x1800035ea  add     r14, r12
0x1800035ed  mov     [r14], cl
0x1800035f0  lea     rdi, [r14+0Ah]
0x1800035f4  mov     [r14+1], dl
0x1800035f8  movzx   ecx, word ptr [rbx+2]
0x1800035fc  mov     [r14+3], cl
0x180003600  movzx   eax, cx
0x180003603  shr     ax, 8
0x180003607  mov     [r14+2], al
0x18000360b  movzx   ecx, word ptr [rbx+6]
0x18000360f  mov     [r14+5], cl
0x180003613  movzx   eax, cx
0x180003616  shr     ax, 8
0x18000361a  mov     [r14+4], al
0x18000361e  movzx   ecx, word ptr [rbx]
0x180003621  mov     [r14+7], cl
0x180003625  movzx   eax, cx
0x180003628  shr     ax, 8
0x18000362c  mov     [r14+6], al
0x180003630  movzx   ecx, word ptr [rbx+4]
0x180003634  movzx   eax, cx
0x180003637  mov     [r14+9], cl
0x18000363b  shr     ax, 8
0x18000363f  mov     [r14+8], al
0x180003643  movsx   eax, word ptr [rbx+42h]
0x180003647  test    ax, ax
0x18000364a  jg      short loc_1800036AE
0x18000364c  movsx   eax, word ptr [rbx+0Eh]
0x180003650  mov     rcx, [rbx+88h]
0x180003657  test    ax, ax
0x18000365a  js      short loc_18000369E
0x18000365c  mov     edx, eax
0x18000365e  call    MTX_mem_malloc
0x180003663  mov     rsi, rax
0x180003666  sub     rdi, r14
0x180003669  movsx   eax, word ptr [rbx+0Ch]
0x18000366d  add     eax, eax
0x18000366f  movsxd  rcx, eax
0x180003672  add     rcx, rdi
0x180003675  cmp     rcx, 7FFFFFFFh
0x18000367c  ja      short loc_180003687
0x18000367e  cmp     rcx, rdi
0x180003681  jnb     loc_180003D52
0x180003687  mov     rcx, [rbx+88h]
0x18000368e  mov     edx, 0CF9h; Value
0x180003693  add     rcx, 30h ; '0'; Buf
0x180003697  call    cs:__imp_longjmp
0x18000369e  add     rcx, 30h ; '0'; Buf
0x1800036a2  mov     edx, 0D22h; Value
0x1800036a7  call    cs:__imp_longjmp
0x1800036ae  sub     rdi, r14
0x1800036b1  lea     r9d, [rax+rax]
0x1800036b5  add     r9, rdi
0x1800036b8  cmp     r9, rdi
0x1800036bb  jb      short loc_1800036C6
0x1800036bd  cmp     r9, 7FFFFFFFh
0x1800036c4  jbe     short loc_1800036DD
0x1800036c6  mov     rcx, [rbx+88h]
0x1800036cd  mov     edx, 0CF9h; Value
0x1800036d2  add     rcx, 30h ; '0'; Buf
0x1800036d6  call    cs:__imp_longjmp
0x1800036dd  mov     r8d, r12d
0x1800036e0  mov     [rsp+78h+var_58], r15
0x1800036e5  mov     rdx, rbp
0x1800036e8  mov     rcx, rbx
0x1800036eb  call    AllocateGlyphSpace
0x1800036f0  mov     r9, [rbp+0]
0x1800036f4  xor     r13d, r13d
0x1800036f7  add     r9, r12
0x1800036fa  movzx   r8d, r13w
0x1800036fe  add     rdi, r9
0x180003701  cmp     r13w, [rbx+42h]
0x180003706  jge     short loc_18000372F
0x180003708  mov     rax, [rbx+38h]
0x18000370c  movsx   rcx, r8w
0x180003710  inc     r8w
0x180003714  movzx   edx, word ptr [rax+rcx*2]
0x180003718  mov     [rdi+1], dl
0x18000371b  movzx   eax, dx
0x18000371e  shr     ax, 8
0x180003722  mov     [rdi], al
0x180003724  add     rdi, 2
0x180003728  cmp     r8w, [rbx+42h]
0x18000372d  jl      short loc_180003708
0x18000372f  sub     rdi, r9
0x180003732  movzx   r9d, word ptr [rbx+46h]
0x180003737  add     r9, 2
0x18000373b  add     r9, rdi
0x18000373e  cmp     r9, rdi
0x180003741  jb      short loc_18000374C
0x180003743  cmp     r9, 7FFFFFFFh
0x18000374a  jbe     short loc_180003787
0x18000374c  mov     rcx, [rbx+88h]
0x180003753  mov     edx, 0CF9h; Value
0x180003758  add     rcx, 30h ; '0'; Buf
0x18000375c  call    cs:__imp_longjmp
0x180003763  movzx   edx, word ptr [rbx+44h]
0x180003767  test    dx, dx
0x18000376a  js      loc_1800035CB
0x180003770  mov     rcx, [rbx+88h]
0x180003777  mov     edx, 0D22h; Value
0x18000377c  add     rcx, 30h ; '0'; Buf
0x180003780  call    cs:__imp_longjmp
0x180003787  mov     r8d, r12d
0x18000378a  mov     [rsp+78h+var_58], r15
0x18000378f  mov     rdx, rbp
0x180003792  mov     rcx, rbx
0x180003795  call    AllocateGlyphSpace
0x18000379a  mov     r9, [rbp+0]
0x18000379e  movzx   ecx, word ptr [rbx+46h]
0x1800037a2  add     r9, r12
0x1800037a5  lea     r8, [rdi+r9]
0x1800037a9  test    cx, cx
0x1800037ac  jnz     loc_1800038F4
0x1800037b2  sub     r8d, r9d
0x1800037b5  mov     eax, r8d
0x1800037b8  jmp     loc_180003882
0x1800037bd  cmp     ecx, edx
0x1800037bf  ja      loc_180003FC8
0x1800037c5  mov     rax, [rsp+78h+arg_8]
0x1800037cd  movzx   r9d, r13w
0x1800037d1  movzx   r11d, r13w
0x1800037d5  add     r12, [rax]
0x1800037d8  add     rdi, r12
0x1800037db  cmp     r13w, [rbx+0Eh]
0x1800037e0  jge     short loc_18000382E
0x1800037e2  mov     rax, [rbx+28h]
0x1800037e6  movsx   rdx, r9w
0x1800037ea  movzx   r8d, word ptr [rax+rdx*2]
0x1800037ef  sub     r8w, r11w
0x1800037f3  movzx   r11d, word ptr [rax+rdx*2]
0x1800037f8  movzx   eax, byte ptr [rsi+rdx]
0x1800037fc  movzx   edx, al
0x1800037ff  movzx   r10d, r8w
0x180003803  and     dl, 20h
0x180003806  test    al, 4
0x180003808  jz      loc_1800038A1
0x18000380e  neg     r8b
0x180003811  movzx   ecx, r10b
0x180003815  test    dl, dl
0x180003817  movzx   eax, r8b
0x18000381b  cmovnz  eax, ecx
0x18000381e  mov     [rdi], al
0x180003820  inc     rdi
0x180003823  inc     r9w
0x180003827  cmp     r9w, [rbx+0Eh]
0x18000382c  jl      short loc_1800037E2
0x18000382e  test    rsi, rsi
0x180003831  jz      short loc_18000387D
0x180003833  mov     r14, [rbx+88h]
0x18000383a  mov     rbp, [r14]
0x18000383d  mov     ebx, [r14+0Ch]
0x180003841  dec     ebx
0x180003843  test    ebx, ebx
0x180003845  js      loc_180003942
0x18000384b  movsxd  r15, ebx
0x18000384e  shl     r15, 4
0x180003852  add     r15, rbp
0x180003855  cmp     [r15], rsi
0x180003858  jnz     short loc_180003841
0x18000385a  mov     rax, [r14+28h]
0x18000385e  mov     rcx, rsi
0x180003861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003866  movsxd  rax, dword ptr [r14+0Ch]
0x18000386a  not     ebx
0x18000386c  add     ebx, eax
0x18000386e  test    ebx, ebx
0x180003870  jg      short loc_1800038C0
0x180003872  mov     [r15], r13
0x180003875  mov     [r15+8], r13d
0x180003879  dec     dword ptr [r14+0Ch]
0x18000387d  sub     edi, r12d
0x180003880  mov     eax, edi
0x180003882  mov     r13, [rsp+78h+var_38]
0x180003887  mov     rdi, [rsp+78h+var_30]
0x18000388c  mov     rsi, [rsp+78h+var_28]
0x180003891  mov     r14, [rsp+78h+var_40]
0x180003896  add     rsp, 58h
0x18000389a  pop     r15
0x18000389c  pop     r12
0x18000389e  pop     rbp
0x18000389f  pop     rbx
0x1800038a0  retn
0x1800038a1  test    dl, dl
0x1800038a3  jnz     loc_180003823
0x1800038a9  movzx   eax, r8w
0x1800038ad  mov     [rdi+1], r8b
0x1800038b1  shr     ax, 8
0x1800038b5  mov     [rdi], al
0x1800038b7  add     rdi, 2
0x1800038bb  jmp     loc_180003823
0x1800038c0  add     rax, rax
0x1800038c3  mov     rax, [rbp+rax*8-10h]
0x1800038c8  mov     [r15], rax
0x1800038cb  movsxd  rax, dword ptr [r14+0Ch]
0x1800038cf  add     rax, rax
0x1800038d2  mov     eax, [rbp+rax*8-8]
0x1800038d6  mov     [r15+8], eax
0x1800038da  movsxd  rax, dword ptr [r14+0Ch]
0x1800038de  add     rax, rax
0x1800038e1  mov     [rbp+rax*8-10h], r13
0x1800038e6  movsxd  rax, dword ptr [r14+0Ch]
0x1800038ea  add     rax, rax
0x1800038ed  mov     [rbp+rax*8-8], r13d
0x1800038f2  jmp     short loc_180003879
0x1800038f4  mov     [r8+1], cl
0x1800038f8  movzx   eax, cx
0x1800038fb  shr     ax, 8
0x1800038ff  mov     [r8], al
0x180003902  add     r8, 2
0x180003906  cmp     r13w, [rbx+46h]
0x18000390b  jnb     loc_1800037B2
0x180003911  nop     dword ptr [rax+00h]
0x180003915  nop     word ptr [rax+rax+00000000h]
0x180003920  mov     rcx, [rbx+48h]
0x180003924  movzx   edx, r13w
0x180003928  inc     r13w
0x18000392c  movzx   edx, byte ptr [rdx+rcx]
0x180003930  mov     [r8], dl
0x180003933  inc     r8
0x180003936  cmp     r13w, [rbx+46h]
0x18000393b  jb      short loc_180003920
0x18000393d  jmp     loc_1800037B2
0x180003942  lea     rcx, [r14+30h]; Buf
0x180003946  mov     edx, 0D1Eh; Value
0x18000394b  call    cs:__imp_longjmp
0x180003952  movzx   eax, word ptr [rbx+0Eh]
0x180003956  movzx   r8d, r13w
0x18000395a  movzx   r11d, r13w
0x18000395e  movzx   ebp, r13w
0x180003962  cmp     r13w, ax
0x180003966  jge     loc_1800039FE
0x18000396c  mov     r12d, 0FFh
0x180003972  mov     r15d, 1FEh
0x180003978  nop     dword ptr [rax+rax+00000000h]
0x180003980  mov     rax, [rbx+30h]
0x180003984  movsx   r10, r8w
0x180003988  movzx   edx, byte ptr [r10+rax]
0x18000398d  mov     rax, [rbx+20h]
0x180003991  and     dl, 1
0x180003994  movzx   r9d, word ptr [rax+r10*2]
0x180003999  sub     r9w, bp
0x18000399d  movzx   ebp, word ptr [rax+r10*2]
0x1800039a2  jz      short loc_1800039B7
0x1800039a4  lea     eax, [r12+r9]
0x1800039a8  cmp     ax, r15w
0x1800039ac  ja      short loc_1800039BA
0x1800039ae  or      dl, 2
0x1800039b1  test    r9w, r9w
0x1800039b5  jle     short loc_1800039BA
0x1800039b7  or      dl, 10h
0x1800039ba  mov     rax, [rbx+28h]
0x1800039be  movzx   r9d, word ptr [rax+r10*2]
0x1800039c3  sub     r9w, r11w
0x1800039c7  movzx   r11d, word ptr [rax+r10*2]
0x1800039cc  jz      short loc_1800039E1
0x1800039ce  lea     eax, [r12+r9]
0x1800039d2  cmp     ax, r15w
0x1800039d6  ja      short loc_1800039E4
  ... truncated ...
```
