# ReadCTFSpline

- ea: `0x180004e10`
- end: `0x180005993`
- name: `ReadCTFSpline`
- size: `2947`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180004320`

## callees

- `0x180004e10`
- `0x180006400`
- `0x180006504`
- `0x180006a80`
- `0x180009d40`
- `0x18000a550`
- `0x18000af10`
- `0x18002b010`

## import_xrefs

- `msvcrt!longjmp` at `0x18000505e`
- `msvcrt!longjmp` at `0x180005071`
- `msvcrt!longjmp` at `0x18000544a`
- `msvcrt!longjmp` at `0x1800054fb`
- `msvcrt!longjmp` at `0x18000550b`
- `msvcrt!longjmp` at `0x18000551b`
- `msvcrt!longjmp` at `0x18000552b`
- `msvcrt!longjmp` at `0x18000553e`
- `msvcrt!longjmp` at `0x18000554e`
- `msvcrt!longjmp` at `0x180005561`
- `msvcrt!longjmp` at `0x180005574`
- `msvcrt!longjmp` at `0x180005584`
- `msvcrt!longjmp` at `0x180005594`
- `msvcrt!longjmp` at `0x1800055a4`
- `msvcrt!longjmp` at `0x1800055ef`
- `msvcrt!longjmp` at `0x180005646`
- `msvcrt!longjmp` at `0x1800056f4`
- `msvcrt!longjmp` at `0x180005704`
- `msvcrt!longjmp` at `0x180005714`
- `msvcrt!longjmp` at `0x1800057a8`
- `msvcrt!longjmp` at `0x1800057b8`
- `msvcrt!longjmp` at `0x1800057c8`
- `msvcrt!longjmp` at `0x1800057d8`
- `msvcrt!longjmp` at `0x1800057e8`
- `msvcrt!longjmp` at `0x1800057f8`
- `msvcrt!longjmp` at `0x18000505e`
- `msvcrt!longjmp` at `0x180005071`
- `msvcrt!longjmp` at `0x18000544a`
- `msvcrt!longjmp` at `0x1800054fb`
- `msvcrt!longjmp` at `0x18000550b`
- `msvcrt!longjmp` at `0x18000551b`
- `msvcrt!longjmp` at `0x18000552b`
- `msvcrt!longjmp` at `0x18000553e`
- `msvcrt!longjmp` at `0x18000554e`
- `msvcrt!longjmp` at `0x180005561`
- `msvcrt!longjmp` at `0x180005574`
- `msvcrt!longjmp` at `0x180005584`
- `msvcrt!longjmp` at `0x180005594`
- `msvcrt!longjmp` at `0x1800055a4`
- `msvcrt!longjmp` at `0x1800055ef`
- `msvcrt!longjmp` at `0x180005646`
- `msvcrt!longjmp` at `0x1800056f4`
- `msvcrt!longjmp` at `0x180005704`
- `msvcrt!longjmp` at `0x180005714`
- `msvcrt!longjmp` at `0x1800057a8`
- `msvcrt!longjmp` at `0x1800057b8`
- `msvcrt!longjmp` at `0x1800057c8`
- `msvcrt!longjmp` at `0x1800057d8`
- `msvcrt!longjmp` at `0x1800057e8`
- `msvcrt!longjmp` at `0x1800057f8`

## pseudocode

```c
__int64 __fastcall ReadCTFSpline(__int64 a1, char *a2)
{
  __int64 v3; // rcx
  __int16 v4; // r12
  char *v5; // r13
  _JBTYPE **v6; // r15
  _JBTYPE *v7; // r14
  unsigned __int64 v8; // rbp
  int v9; // edi
  unsigned __int64 v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rcx
  _JBTYPE *v13; // r14
  unsigned __int64 v14; // rbp
  int v15; // edi
  unsigned __int64 v16; // rsi
  __int64 v17; // rax
  __int64 v18; // rcx
  _JBTYPE *v19; // r14
  unsigned __int64 v20; // rbp
  int v21; // edi
  unsigned __int64 v22; // rsi
  __int64 v23; // rax
  __int64 v24; // rcx
  _JBTYPE *v25; // r14
  unsigned __int64 v26; // rbp
  int v27; // edi
  unsigned __int64 v28; // rsi
  __int64 v29; // rax
  __int64 v30; // rcx
  _JBTYPE *v31; // r14
  unsigned __int64 v32; // rbp
  int v33; // edi
  unsigned __int64 v34; // rsi
  __int64 v35; // rax
  char *v36; // rdi
  __int16 v37; // cx
  int v38; // ecx
  __int64 v40; // rdx
  bool v41; // cc
  _JBTYPE *v42; // rcx
  __int64 v43; // rax
  _JBTYPE *v44; // rcx
  int v45; // eax
  __int64 v46; // rdx
  __int64 v47; // rax
  int v48; // edx
  __int64 v49; // r8
  __int16 v50; // r9
  __int16 v51; // bp
  int v52; // esi
  __int64 v53; // rdi
  __int16 v54; // cx
  __int64 v55; // rdx
  bool v56; // sf
  _JBTYPE *v57; // rcx
  __int64 v58; // rax
  int v59; // ecx
  int v60; // r8d
  char v61; // al
  __int64 v62; // rdx
  int v63; // eax
  _JBTYPE *v64; // rcx
  __int64 v65; // rdx
  __int64 v66; // rax
  _JBTYPE *v67; // rcx
  int v68; // eax
  __int64 v69; // rdx
  __int16 v70; // r13
  int i; // esi
  __int64 v72; // r15
  unsigned __int64 v73; // rdx
  __int64 v74; // r14
  _JBTYPE *v75; // rbp
  char v76; // r10
  __int64 v77; // r11
  unsigned __int8 v78; // al
  int v79; // ecx
  unsigned __int8 *v80; // rax
  int v81; // ecx
  unsigned __int8 v82; // r8
  int v83; // eax
  unsigned __int8 *v84; // rcx
  unsigned __int8 v85; // r8
  int v86; // ecx
  unsigned __int8 *v87; // rax
  unsigned __int8 v88; // dl
  __int64 v89; // r8
  unsigned int v90; // r9d
  __int16 v91; // cx
  int v92; // r11d
  int v93; // r9d
  int v94; // edx
  int v95; // ecx
  _JBTYPE *v96; // rcx
  char *v97; // rsi
  __int64 v98; // r8
  __int16 v99; // bp
  __int64 v100; // r10
  _JBTYPE *v101; // rcx
  char *v102; // r14
  char *v103; // rdx
  __int64 v104; // rdx
  __int16 v105; // ax
  __int64 v106; // rdx
  __int64 v107; // rdx
  __int16 v108; // ax
  char *v109; // rdx
  __int16 v110; // cx
  __int16 v111; // ax
  __int64 v112; // rdx
  __int64 v113; // rdx
  int v114; // [rsp+70h] [rbp+8h]
  char *v115; // [rsp+78h] [rbp+10h] BYREF
  _JBTYPE **v116; // [rsp+80h] [rbp+18h]
  char *v117; // [rsp+88h] [rbp+20h]

  v117 = a2;
  v3 = *(_QWORD *)(a1 + 16);
  v4 = 0;
  v5 = a2;
  v6 = (_JBTYPE **)(a1 + 136);
  v116 = (_JBTYPE **)(a1 + 136);
  if ( v3 )
  {
    v7 = *v6;
    v8 = (*v6)->Part[0];
    v9 = HIDWORD((*v6)->Part[1]);
    do
    {
      if ( --v9 < 0 )
        longjmp(v7 + 3, 3358);
      v10 = v8 + 16LL * v9;
    }
    while ( *(_QWORD *)v10 != v3 );
    ((void (*)(void))v7[2].Part[1])();
    v11 = SHIDWORD(v7->Part[1]);
    if ( (int)v11 + ~v9 > 0 )
    {
      *(_QWORD *)v10 = *(_QWORD *)(v8 + 16 * v11 - 16);
      *(_DWORD *)(v10 + 8) = *(_DWORD *)(v8 + 16LL * SHIDWORD(v7->Part[1]) - 8);
      *(_QWORD *)(v8 + 16LL * SHIDWORD(v7->Part[1]) - 16) = 0;
      *(_DWORD *)(v8 + 16LL * SHIDWORD(v7->Part[1]) - 8) = 0;
    }
    else
    {
      *(_QWORD *)v10 = 0;
      *(_DWORD *)(v10 + 8) = 0;
    }
    --HIDWORD(v7->Part[1]);
  }
  else
  {
    v116 = (_JBTYPE **)(a1 + 136);
  }
  v12 = *(_QWORD *)(a1 + 24);
  *(_QWORD *)(a1 + 16) = 0;
  if ( v12 )
  {
    v13 = *v6;
    v14 = (*v6)->Part[0];
    v15 = HIDWORD((*v6)->Part[1]);
    do
    {
      if ( --v15 < 0 )
        longjmp(v13 + 3, 3358);
      v16 = v14 + 16LL * v15;
    }
    while ( *(_QWORD *)v16 != v12 );
    ((void (*)(void))v13[2].Part[1])();
    v17 = SHIDWORD(v13->Part[1]);
    if ( (int)v17 + ~v15 > 0 )
    {
      *(_QWORD *)v16 = *(_QWORD *)(v14 + 16 * v17 - 16);
      *(_DWORD *)(v16 + 8) = *(_DWORD *)(v14 + 16LL * SHIDWORD(v13->Part[1]) - 8);
      *(_QWORD *)(v14 + 16LL * SHIDWORD(v13->Part[1]) - 16) = 0;
      *(_DWORD *)(v14 + 16LL * SHIDWORD(v13->Part[1]) - 8) = 0;
    }
    else
    {
      *(_QWORD *)v16 = 0;
      *(_DWORD *)(v16 + 8) = 0;
    }
    --HIDWORD(v13->Part[1]);
  }
  v18 = *(_QWORD *)(a1 + 48);
  *(_QWORD *)(a1 + 24) = 0;
  if ( v18 )
  {
    v19 = *v6;
    v20 = (*v6)->Part[0];
    v21 = HIDWORD((*v6)->Part[1]);
    do
    {
      if ( --v21 < 0 )
        longjmp(v19 + 3, 3358);
      v22 = v20 + 16LL * v21;
    }
    while ( *(_QWORD *)v22 != v18 );
    ((void (*)(void))v19[2].Part[1])();
    v23 = SHIDWORD(v19->Part[1]);
    if ( (int)v23 + ~v21 > 0 )
    {
      *(_QWORD *)v22 = *(_QWORD *)(v20 + 16 * v23 - 16);
      *(_DWORD *)(v22 + 8) = *(_DWORD *)(v20 + 16LL * SHIDWORD(v19->Part[1]) - 8);
      *(_QWORD *)(v20 + 16LL * SHIDWORD(v19->Part[1]) - 16) = 0;
      *(_DWORD *)(v20 + 16LL * SHIDWORD(v19->Part[1]) - 8) = 0;
    }
    else
    {
      *(_QWORD *)v22 = 0;
      *(_DWORD *)(v22 + 8) = 0;
    }
    --HIDWORD(v19->Part[1]);
  }
  v24 = *(_QWORD *)(a1 + 32);
  *(_QWORD *)(a1 + 48) = 0;
  if ( v24 )
  {
    v25 = *v6;
    v26 = (*v6)->Part[0];
    v27 = HIDWORD((*v6)->Part[1]);
    do
    {
      if ( --v27 < 0 )
        longjmp(v25 + 3, 3358);
      v28 = v26 + 16LL * v27;
    }
    while ( *(_QWORD *)v28 != v24 );
    ((void (*)(void))v25[2].Part[1])();
    v29 = SHIDWORD(v25->Part[1]);
    if ( (int)v29 + ~v27 > 0 )
    {
      *(_QWORD *)v28 = *(_QWORD *)(v26 + 16 * v29 - 16);
      *(_DWORD *)(v28 + 8) = *(_DWORD *)(v26 + 16LL * SHIDWORD(v25->Part[1]) - 8);
      *(_QWORD *)(v26 + 16LL * SHIDWORD(v25->Part[1]) - 16) = 0;
      *(_DWORD *)(v26 + 16LL * SHIDWORD(v25->Part[1]) - 8) = 0;
    }
    else
    {
      *(_QWORD *)v28 = 0;
      *(_DWORD *)(v28 + 8) = 0;
    }
    --HIDWORD(v25->Part[1]);
  }
  v30 = *(_QWORD *)(a1 + 40);
  *(_QWORD *)(a1 + 32) = 0;
  if ( v30 )
  {
    v31 = *v6;
    v32 = (*v6)->Part[0];
    v33 = HIDWORD((*v6)->Part[1]);
    do
    {
      if ( --v33 < 0 )
        longjmp(v31 + 3, 3358);
      v34 = v32 + 16LL * v33;
    }
    while ( *(_QWORD *)v34 != v30 );
    ((void (*)(void))v31[2].Part[1])();
    v35 = SHIDWORD(v31->Part[1]);
    if ( (int)v35 + ~v33 > 0 )
    {
      *(_QWORD *)v34 = *(_QWORD *)(v32 + 16 * v35 - 16);
      *(_DWORD *)(v34 + 8) = *(_DWORD *)(v32 + 16LL * SHIDWORD(v31->Part[1]) - 8);
      *(_QWORD *)(v32 + 16LL * SHIDWORD(v31->Part[1]) - 16) = 0;
      *(_DWORD *)(v32 + 16LL * SHIDWORD(v31->Part[1]) - 8) = 0;
    }
    else
    {
      *(_QWORD *)v34 = 0;
      *(_DWORD *)(v34 + 8) = 0;
    }
    --HIDWORD(v31->Part[1]);
  }
  v36 = v5 + 2;
  *(_QWORD *)(a1 + 40) = 0;
  if ( (unsigned __int64)(v5 + 2) > *(_QWORD *)(a1 + 128) )
    longjmp(*v6 + 3, 3362);
  if ( (unsigned __int64)v5 < *(_QWORD *)(a1 + 120) )
    longjmp(*v6 + 3, 3362);
  v37 = (*v5 << 8) | (unsigned __int8)v5[1];
  v114 = 1;
  *(_WORD *)(a1 + 12) = v37;
  v115 = v5 + 2;
  if ( v37 < 0 )
  {
    CheckReadBoundsGlyph(a1, v5 + 2, 8);
    v109 = v5 + 8;
    *(_WORD *)(a1 + 2) = (v5[2] << 8) | (unsigned __int8)v5[3];
    *(_WORD *)(a1 + 6) = (v5[4] << 8) | (unsigned __int8)v5[5];
    v110 = (unsigned __int8)v5[7];
    v111 = v5[6];
LABEL_140:
    v36 = v109 + 2;
    v115 = v109 + 2;
    *(_WORD *)a1 = (v111 << 8) | v110;
    *(_WORD *)(a1 + 4) = (*v109 << 8) | (unsigned __int8)v109[1];
    goto LABEL_40;
  }
  if ( v37 == 0x7FFF )
  {
    CheckReadBoundsGlyph(a1, v5 + 2, 10);
    v109 = v5 + 10;
    v114 = 0;
    *(_WORD *)(a1 + 12) = (v5[2] << 8) | (unsigned __int8)v5[3];
    *(_WORD *)(a1 + 2) = (v5[4] << 8) | (unsigned __int8)v5[5];
    *(_WORD *)(a1 + 6) = (v5[6] << 8) | (unsigned __int8)v5[7];
    v110 = (unsigned __int8)v5[9];
    v111 = v5[8];
    goto LABEL_140;
  }
LABEL_40:
  v38 = *(__int16 *)(a1 + 12);
  if ( !*(_WORD *)(a1 + 12) )
    return (unsigned int)((_DWORD)v36 - (_DWORD)v5);
  if ( *(__int16 *)(a1 + 12) >= 0 )
  {
    v40 = (unsigned int)(2 * v38);
    v41 = (int)v40 < v38;
    v42 = *v6;
    if ( v41 )
      longjmp(v42 + 3, 3362);
    v43 = MTX_mem_malloc(v42, v40);
    v44 = *v6;
    *(_QWORD *)(a1 + 16) = v43;
    v45 = *(__int16 *)(a1 + 12);
    if ( *(__int16 *)(a1 + 12) < 0 )
      longjmp(v44 + 3, 3362);
    v46 = (unsigned int)(2 * v45);
    if ( (int)v46 < v45 )
      longjmp(v44 + 3, 3362);
    v47 = MTX_mem_malloc(v44, v46);
    LOWORD(v48) = *(_WORD *)(a1 + 12);
    v49 = v47;
    *(_QWORD *)(a1 + 24) = v47;
    v50 = 0;
    v51 = 0;
    v52 = 0;
    if ( (__int16)v48 > 0 )
    {
      while ( 1 )
      {
        v53 = 2LL * v52;
        *(_WORD *)(v53 + *(_QWORD *)(a1 + 16)) = v50;
        ++v52;
        *(_WORD *)(v53 + *(_QWORD *)(a1 + 24)) = v51 + Read255UShort(a1, &v115, v49);
        v48 = *(__int16 *)(a1 + 12);
        v49 = *(_QWORD *)(a1 + 24);
        if ( v52 >= v48 )
          break;
        v51 = *(_WORD *)(v49 + v53);
        v50 = v51 + 1;
      }
      v36 = v115;
    }
    v54 = *(_WORD *)(v49 + 2LL * (__int16)v48 - 2) + 1;
    *(_WORD *)(a1 + 14) = v54;
    if ( v54 <= 0 )
      longjmp(*v6 + 3, 3362);
    v55 = v54;
    if ( (unsigned __int64)&v36[v54] > *(_QWORD *)(a1 + 128) )
      longjmp(*v6 + 3, 3362);
    if ( (unsigned __int64)v36 < *(_QWORD *)(a1 + 120) )
      longjmp(*v6 + 3, 3362);
    v56 = v54 < 0;
    v57 = *v6;
    if ( v56 )
      longjmp(v57 + 3, 3362);
    v58 = MTX_mem_malloc(v57, v55);
    LOWORD(v59) = *(_WORD *)(a1 + 14);
    v60 = 0;
    *(_QWORD *)(a1 + 48) = v58;
    if ( (__int16)v59 > 0 )
    {
      do
      {
        v61 = *v36++;
        v62 = v60++;
        *(_BYTE *)(v62 + *(_QWORD *)(a1 + 48)) = v61;
        v59 = *(__int16 *)(a1 + 14);
      }
      while ( v60 < v59 );
      v115 = v36;
    }
    if ( (v59 & 0x8000u) != 0 )
      longjmp(*v6 + 3, 3362);
    v63 = (__int16)v59;
    v64 = *v6;
    v65 = (unsigned int)(2 * v63);
    if ( (int)v65 < v63 )
      longjmp(v64 + 3, 3362);
    v66 = MTX_mem_malloc(v64, v65);
    v67 = *v6;
    *(_QWORD *)(a1 + 32) = v66;
    v68 = *(__int16 *)(a1 + 14);
    if ( *(__int16 *)(a1 + 14) < 0 )
      longjmp(v67 + 3, 3362);
    v69 = (unsigned int)(2 * v68);
    if ( (int)v69 < v68 )
      longjmp(v67 + 3, 3362);
    *(_QWORD *)(a1 + 40) = MTX_mem_malloc(v67, v69);
    v70 = 0;
    for ( i = 0; i < *(__int16 *)(a1 + 14); *(_WORD *)(*(_QWORD *)(a1 + 40) + 2 * v74) = v4 )
    {
      v72 = *(_QWORD *)(a1 + 48);
      v73 = *(_QWORD *)(a1 + 120);
      v74 = i;
      v75 = *v116;
      v76 = *(_BYTE *)(v72 + i);
      v77 = v76 & 0x7F;
      if ( (unsigned __int64)v36 < v73 || (unsigned __int64)v36 >= *(_QWORD *)(a1 + 128) )
        v78 = 0;
      else
        v78 = *v36;
      v79 = v78;
      v80 = (unsigned __int8 *)(v36 + 1);
      v81 = v79 << 24;
      if ( (unsigned __int64)(v36 + 1) < v73 || (unsigned __int64)v80 >= *(_QWORD *)(a1 + 128) )
        v82 = 0;
      else
        v82 = *v80;
      v83 = v81 | (v82 << 16);
      v84 = (unsigned __int8 *)(v36 + 2);
      if ( (unsigned __int64)(v36 + 2) < v73 || (unsigned __int64)v84 >= *(_QWORD *)(a1 + 128) )
        v85 = 0;
      else
        v85 = *v84;
      v86 = v83 | (v85 << 8);
      v87 = (unsigned __int8 *)(v36 + 3);
      if ( (unsigned __int64)(v36 + 3) < v73 || (unsigned __int64)v87 >= *(_QWORD *)(a1 + 128) )
        v88 = 0;
      else
        v88 = *v87;
      v89 = 12 * v77;
      v90 = v86 | v88;
      v91 = *((_WORD *)qword_180031CA0 + 6 * v77 + 1);
      v36 += *((__int16 *)qword_180031CA0 + 6 * v77) - 1;
      v115 = v36;
      v92 = (v90 >> (32 - v91)) & ((1 << v91) - 1);
      if ( v92 < 0
        || (v93 = ((1 << *(_WORD *)((char *)qword_180031CA0 + v89 + 4)) - 1)
                & (v90 >> (32 - v91 - *(_WORD *)((char *)qword_180031CA0 + v89 + 4))),
            (v94 = v92 + *(__int16 *)((char *)qword_180031CA0 + v89 + 6), v94 < 0)
         || (v95 = v93 + *(__int16 *)((char *)&qword_180031CA0[1] + v89), v95 < 0)) )
      {
        longjmp(v75 + 3, 3362);
      }
      if ( *((_BYTE *)&qword_180031CA0[1] + v89 + 2) )
        v94 = -v94;
      if ( *((_BYTE *)&qword_180031CA0[1] + v89 + 3) )
        v95 = -v95;
      v70 += v94;
      v4 += v95;
      ++i;
      *(_BYTE *)(v72 + v74) = (unsigned __int8)~v76 >> 7;
      *(_WORD *)(*(_QWORD *)(a1 + 32) + 2 * v74) = v70;
    }
    if ( v114 )
      SetBBox(a1);
    LODWORD(v5) = (_DWORD)v117;
    goto LABEL_95;
  }
  *(_WORD *)(a1 + 68) = v38;
  v96 = *v6;
  if ( !*(_QWORD *)(a1 + 56) )
    longjmp(v96 + 3, 3362);
  while ( 1 )
  {
    v97 = v36;
    if ( (unsigned __int64)(v36 + 2) > *(_QWORD *)(a1 + 128) )
      longjmp(v96 + 3, 3362);
    if ( (unsigned __int64)v36 < *(_QWORD *)(a1 + 120)
      || (v98 = *(__int16 *)(a1 + 66), (__int16)v98 >= *(__int16 *)(a1 + 64)) )
    {
      longjmp(v96 + 3, 3362);
    }
    v99 = (*v36 << 8) | (unsigned __int8)v36[1];
    *(_WORD *)(*(_QWORD *)(a1 + 56) + 2 * v98) = v99;
    v100 = *(__int16 *)(a1 + 66);
    v101 = *v6;
    *(_WORD *)(a1 + 66) = v100 + 1;
    if ( (unsigned __int64)(v36 + 4) > *(_QWORD *)(a1 + 128) )
      longjmp(v101 + 3, 3362);
    if ( (unsigned __int64)(v36 + 2) < *(_QWORD *)(a1 + 120) || (__int16)(v100 + 1) >= *(__int16 *)(a1 + 64) )
      longjmp(v101 + 3, 3362);
    v102 = v36 + 6;
    v103 = v36 + 4;
    *(_WORD *)(*(_QWORD *)(a1 + 56) + 2 * v100 + 2) = (unsigned __int8)v36[3] | (unsigned __int16)(v36[2] << 8);
    ++*(_WORD *)(a1 + 66);
    if ( (v99 & 1) != 0 )
    {
      CheckReadBoundsGlyph(a1, v103, 4);
      v106 = (unsigned int)v36[4];
      LOWORD(v106) = (unsigned __int8)v36[5] | (unsigned __int16)(v36[4] << 8);
      WriteComponentData(a1, v106);
      v104 = (unsigned int)*v102;
      v36 += 8;
      v105 = (unsigned __int8)v97[7];
      v102 = v36;
      v115 = v36;
    }
    else
    {
      CheckReadBoundsGlyph(a1, v103, 2);
      v104 = (unsigned int)v36[4];
      v36 += 6;
      v105 = (unsigned __int8)v97[5];
      v115 = v102;
    }
    LOWORD(v104) = v105 | ((_WORD)v104 << 8);
    WriteComponentData(a1, v104);
    if ( (v99 & 8) != 0 )
    {
      CheckReadBoundsGlyph(a1, v36, 2);
      v36 = v102 + 2;
      v107 = (unsigned __int8)v102[1];
      v108 = *v102 << 8;
    }
    else
    {
      if ( (v99 & 0x40) != 0 )
      {
        CheckReadBoundsGlyph(a1, v36, 4);
        WriteComponentData(a1, (unsigned __int16)((*v102 << 8) | (unsigned __int8)v102[1]));
        v107 = (unsigned int)v102[2];
        v36 = v102 + 4;
        v108 = (unsigned __int8)v102[3];
      }
      else
      {
        if ( (v99 & 0x80u) == 0 )
          goto LABEL_122;
        CheckReadBoundsGlyph(a1, v36, 8);
        WriteComponentData(a1, (unsigned __int16)((*v102 << 8) | (unsigned __int8)v102[1]));
        v112 = (unsigned int)v102[2];
        LOWORD(v112) = (unsigned __int8)v102[3] | (unsigned __int16)(v102[2] << 8);
        WriteComponentData(a1, v112);
        v113 = (unsigned int)v102[4];
        LOWORD(v113) = (unsigned __int8)v102[5] | (unsigned __int16)(v102[4] << 8);
        WriteComponentData(a1, v113);
        v107 = (unsigned int)v102[6];
        v36 = v102 + 8;
        v108 = (unsigned __int8)v102[7];
      }
      LOWORD(v107) = (_WORD)v107 << 8;
    }
    LOWORD(v107) = v108 | v107;
    v115 = v36;
    WriteComponentData(a1, v107);
LABEL_122:
    if ( *(_WORD *)(a1 + 66) >= *(_WORD *)(a1 + 64) )
      longjmp(*v6 + 3, 3362);
    if ( (v99 & 0x20) == 0 )
      break;
    v96 = *v6;
  }
  *(_WORD *)(a1 + 70) = 0;
  if ( (v99 & 0x100) != 0 )
  {
LABEL_95:
    ReadAllCTFInstructions(a1, &v115);
    LODWORD(v36) = (_DWORD)v115;
  }
  return (unsigned int)((_DWORD)v36 - (_DWORD)v5);
}

```

## disassembly

```asm
0x180004e10  push    rbx
0x180004e12  push    rbp
0x180004e13  push    rsi
0x180004e14  push    rdi
0x180004e15  push    r12
0x180004e17  push    r13
0x180004e19  push    r14
0x180004e1b  push    r15
0x180004e1d  sub     rsp, 28h
0x180004e21  mov     rbx, rcx
0x180004e24  mov     [rsp+68h+arg_18], rdx
0x180004e2c  mov     rcx, [rcx+10h]
0x180004e30  xor     r12d, r12d
0x180004e33  mov     r13, rdx
0x180004e36  lea     r15, [rbx+88h]
0x180004e3d  mov     [rsp+68h+arg_10], r15
0x180004e45  test    rcx, rcx
0x180004e48  jz      loc_180005118
0x180004e4e  mov     r14, [r15]
0x180004e51  mov     rbp, [r14]
0x180004e54  mov     edi, [r14+0Ch]
0x180004e58  dec     edi
0x180004e5a  test    edi, edi
0x180004e5c  js      loc_18000579F
0x180004e62  movsxd  rsi, edi
0x180004e65  shl     rsi, 4
0x180004e69  add     rsi, rbp
0x180004e6c  cmp     [rsi], rcx
0x180004e6f  jnz     short loc_180004E58
0x180004e71  mov     rax, [r14+28h]
0x180004e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e7a  movsxd  rax, dword ptr [r14+0Ch]
0x180004e7e  not     edi
0x180004e80  add     edi, eax
0x180004e82  test    edi, edi
0x180004e84  jg      loc_180005125
0x180004e8a  mov     [rsi], r12
0x180004e8d  mov     [rsi+8], r12d
0x180004e91  dec     dword ptr [r14+0Ch]
0x180004e95  mov     rcx, [rbx+18h]
0x180004e99  mov     [rbx+10h], r12
0x180004e9d  test    rcx, rcx
0x180004ea0  jz      short loc_180004EE9
0x180004ea2  mov     r14, [r15]
0x180004ea5  mov     rbp, [r14]
0x180004ea8  mov     edi, [r14+0Ch]
0x180004eac  dec     edi
0x180004eae  test    edi, edi
0x180004eb0  js      loc_1800057AF
0x180004eb6  movsxd  rsi, edi
0x180004eb9  shl     rsi, 4
0x180004ebd  add     rsi, rbp
0x180004ec0  cmp     [rsi], rcx
0x180004ec3  jnz     short loc_180004EAC
0x180004ec5  mov     rax, [r14+28h]
0x180004ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ece  movsxd  rax, dword ptr [r14+0Ch]
0x180004ed2  not     edi
0x180004ed4  add     edi, eax
0x180004ed6  test    edi, edi
0x180004ed8  jg      loc_18000515B
0x180004ede  mov     [rsi], r12
0x180004ee1  mov     [rsi+8], r12d
0x180004ee5  dec     dword ptr [r14+0Ch]
0x180004ee9  mov     rcx, [rbx+30h]
0x180004eed  mov     [rbx+18h], r12
0x180004ef1  test    rcx, rcx
0x180004ef4  jz      short loc_180004F3D
0x180004ef6  mov     r14, [r15]
0x180004ef9  mov     rbp, [r14]
0x180004efc  mov     edi, [r14+0Ch]
0x180004f00  dec     edi
0x180004f02  test    edi, edi
0x180004f04  js      loc_1800057BF
0x180004f0a  movsxd  rsi, edi
0x180004f0d  shl     rsi, 4
0x180004f11  add     rsi, rbp
0x180004f14  cmp     [rsi], rcx
0x180004f17  jnz     short loc_180004F00
0x180004f19  mov     rax, [r14+28h]
0x180004f1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f22  movsxd  rax, dword ptr [r14+0Ch]
0x180004f26  not     edi
0x180004f28  add     edi, eax
0x180004f2a  test    edi, edi
0x180004f2c  jg      loc_180005191
0x180004f32  mov     [rsi], r12
0x180004f35  mov     [rsi+8], r12d
0x180004f39  dec     dword ptr [r14+0Ch]
0x180004f3d  mov     rcx, [rbx+20h]
0x180004f41  mov     [rbx+30h], r12
0x180004f45  test    rcx, rcx
0x180004f48  jz      short loc_180004F91
0x180004f4a  mov     r14, [r15]
0x180004f4d  mov     rbp, [r14]
0x180004f50  mov     edi, [r14+0Ch]
0x180004f54  dec     edi
0x180004f56  test    edi, edi
0x180004f58  js      loc_1800057CF
0x180004f5e  movsxd  rsi, edi
0x180004f61  shl     rsi, 4
0x180004f65  add     rsi, rbp
0x180004f68  cmp     [rsi], rcx
0x180004f6b  jnz     short loc_180004F54
0x180004f6d  mov     rax, [r14+28h]
0x180004f71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f76  movsxd  rax, dword ptr [r14+0Ch]
0x180004f7a  not     edi
0x180004f7c  add     edi, eax
0x180004f7e  test    edi, edi
0x180004f80  jg      loc_1800051C7
0x180004f86  mov     [rsi], r12
0x180004f89  mov     [rsi+8], r12d
0x180004f8d  dec     dword ptr [r14+0Ch]
0x180004f91  mov     rcx, [rbx+28h]
0x180004f95  mov     [rbx+20h], r12
0x180004f99  test    rcx, rcx
0x180004f9c  jz      short loc_180004FE5
0x180004f9e  mov     r14, [r15]
0x180004fa1  mov     rbp, [r14]
0x180004fa4  mov     edi, [r14+0Ch]
0x180004fa8  dec     edi
0x180004faa  test    edi, edi
0x180004fac  js      loc_1800057DF
0x180004fb2  movsxd  rsi, edi
0x180004fb5  shl     rsi, 4
0x180004fb9  add     rsi, rbp
0x180004fbc  cmp     [rsi], rcx
0x180004fbf  jnz     short loc_180004FA8
0x180004fc1  mov     rax, [r14+28h]
0x180004fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fca  movsxd  rax, dword ptr [r14+0Ch]
0x180004fce  not     edi
0x180004fd0  add     edi, eax
0x180004fd2  test    edi, edi
0x180004fd4  jg      loc_1800051FD
0x180004fda  mov     [rsi], r12
0x180004fdd  mov     [rsi+8], r12d
0x180004fe1  dec     dword ptr [r14+0Ch]
0x180004fe5  lea     rdi, [r13+2]
0x180004fe9  mov     [rbx+28h], r12
0x180004fed  cmp     rdi, [rbx+80h]
0x180004ff4  ja      short loc_180005065
0x180004ff6  cmp     r13, [rbx+78h]
0x180004ffa  jb      short loc_180005052
0x180004ffc  movsx   eax, byte ptr [r13+0]
0x180005001  movzx   ecx, byte ptr [r13+1]
0x180005006  shl     ax, 8
0x18000500a  or      cx, ax
0x18000500d  mov     [rsp+68h+arg_0], 1
0x180005015  mov     [rbx+0Ch], cx
0x180005019  mov     [rsp+68h+arg_8], rdi
0x18000501e  jl      loc_1800057FF
0x180005024  mov     eax, 7FFFh
0x180005029  cmp     cx, ax
0x18000502c  jz      loc_180005889
0x180005032  movsx   ecx, word ptr [rbx+0Ch]
0x180005036  mov     rax, rdi
0x180005039  test    cx, cx
0x18000503c  jnz     short loc_180005078
0x18000503e  sub     eax, r13d
0x180005041  add     rsp, 28h
0x180005045  pop     r15
0x180005047  pop     r14
0x180005049  pop     r13
0x18000504b  pop     r12
0x18000504d  pop     rdi
0x18000504e  pop     rsi
0x18000504f  pop     rbp
0x180005050  pop     rbx
0x180005051  retn
0x180005052  mov     rcx, [r15]
0x180005055  mov     edx, 0D22h; Value
0x18000505a  add     rcx, 30h ; '0'; Buf
0x18000505e  call    cs:__imp_longjmp
0x180005065  mov     rcx, [r15]
0x180005068  mov     edx, 0D22h; Value
0x18000506d  add     rcx, 30h ; '0'; Buf
0x180005071  call    cs:__imp_longjmp
0x180005078  js      loc_1800055AB
0x18000507e  lea     edx, [rcx+rcx]
0x180005081  cmp     edx, ecx
0x180005083  mov     rcx, [r15]
0x180005086  jl      loc_18000559B
0x18000508c  call    MTX_mem_malloc
0x180005091  mov     rcx, [r15]
0x180005094  mov     [rbx+10h], rax
0x180005098  movsx   eax, word ptr [rbx+0Ch]
0x18000509c  test    ax, ax
0x18000509f  js      loc_18000558B
0x1800050a5  lea     edx, [rax+rax]
0x1800050a8  cmp     edx, eax
0x1800050aa  jl      loc_18000557B
0x1800050b0  call    MTX_mem_malloc
0x1800050b5  movzx   edx, word ptr [rbx+0Ch]
0x1800050b9  mov     r8, rax
0x1800050bc  mov     [rbx+18h], rax
0x1800050c0  mov     r9d, r12d
0x1800050c3  mov     ebp, r12d
0x1800050c6  mov     esi, r12d
0x1800050c9  cmp     r12w, dx
0x1800050cd  jge     loc_180005238
0x1800050d3  movsxd  rax, esi
0x1800050d6  lea     rdx, [rsp+68h+arg_8]
0x1800050db  mov     rcx, rbx
0x1800050de  lea     rdi, [rax+rax]
0x1800050e2  mov     rax, [rbx+10h]
0x1800050e6  mov     [rdi+rax], r9w
0x1800050eb  call    Read255UShort
0x1800050f0  mov     rcx, [rbx+18h]
0x1800050f4  add     ax, bp
0x1800050f7  inc     esi
0x1800050f9  mov     [rdi+rcx], ax
0x1800050fd  movsx   edx, word ptr [rbx+0Ch]
0x180005101  mov     r8, [rbx+18h]
0x180005105  cmp     esi, edx
0x180005107  jge     loc_180005233
0x18000510d  movzx   ebp, word ptr [r8+rdi]
0x180005112  lea     r9d, [rbp+1]
0x180005116  jmp     short loc_1800050D3
0x180005118  mov     [rsp+68h+arg_10], r15
0x180005120  jmp     loc_180004E95
0x180005125  add     rax, rax
0x180005128  mov     rax, [rbp+rax*8-10h]
0x18000512d  mov     [rsi], rax
0x180005130  movsxd  rax, dword ptr [r14+0Ch]
0x180005134  add     rax, rax
0x180005137  mov     eax, [rbp+rax*8-8]
0x18000513b  mov     [rsi+8], eax
0x18000513e  movsxd  rax, dword ptr [r14+0Ch]
0x180005142  add     rax, rax
0x180005145  mov     [rbp+rax*8-10h], r12
0x18000514a  movsxd  rax, dword ptr [r14+0Ch]
0x18000514e  add     rax, rax
0x180005151  mov     [rbp+rax*8-8], r12d
0x180005156  jmp     loc_180004E91
0x18000515b  add     rax, rax
0x18000515e  mov     rax, [rbp+rax*8-10h]
0x180005163  mov     [rsi], rax
0x180005166  movsxd  rax, dword ptr [r14+0Ch]
0x18000516a  add     rax, rax
0x18000516d  mov     eax, [rbp+rax*8-8]
0x180005171  mov     [rsi+8], eax
0x180005174  movsxd  rax, dword ptr [r14+0Ch]
0x180005178  add     rax, rax
0x18000517b  mov     [rbp+rax*8-10h], r12
0x180005180  movsxd  rax, dword ptr [r14+0Ch]
0x180005184  add     rax, rax
0x180005187  mov     [rbp+rax*8-8], r12d
0x18000518c  jmp     loc_180004EE5
0x180005191  add     rax, rax
0x180005194  mov     rax, [rbp+rax*8-10h]
0x180005199  mov     [rsi], rax
0x18000519c  movsxd  rax, dword ptr [r14+0Ch]
0x1800051a0  add     rax, rax
0x1800051a3  mov     eax, [rbp+rax*8-8]
0x1800051a7  mov     [rsi+8], eax
0x1800051aa  movsxd  rax, dword ptr [r14+0Ch]
0x1800051ae  add     rax, rax
0x1800051b1  mov     [rbp+rax*8-10h], r12
0x1800051b6  movsxd  rax, dword ptr [r14+0Ch]
0x1800051ba  add     rax, rax
0x1800051bd  mov     [rbp+rax*8-8], r12d
0x1800051c2  jmp     loc_180004F39
0x1800051c7  add     rax, rax
0x1800051ca  mov     rax, [rbp+rax*8-10h]
0x1800051cf  mov     [rsi], rax
0x1800051d2  movsxd  rax, dword ptr [r14+0Ch]
0x1800051d6  add     rax, rax
0x1800051d9  mov     eax, [rbp+rax*8-8]
0x1800051dd  mov     [rsi+8], eax
0x1800051e0  movsxd  rax, dword ptr [r14+0Ch]
0x1800051e4  add     rax, rax
0x1800051e7  mov     [rbp+rax*8-10h], r12
0x1800051ec  movsxd  rax, dword ptr [r14+0Ch]
0x1800051f0  add     rax, rax
0x1800051f3  mov     [rbp+rax*8-8], r12d
0x1800051f8  jmp     loc_180004F8D
0x1800051fd  add     rax, rax
0x180005200  mov     rax, [rbp+rax*8-10h]
0x180005205  mov     [rsi], rax
0x180005208  movsxd  rax, dword ptr [r14+0Ch]
0x18000520c  add     rax, rax
0x18000520f  mov     eax, [rbp+rax*8-8]
0x180005213  mov     [rsi+8], eax
0x180005216  movsxd  rax, dword ptr [r14+0Ch]
0x18000521a  add     rax, rax
0x18000521d  mov     [rbp+rax*8-10h], r12
0x180005222  movsxd  rax, dword ptr [r14+0Ch]
0x180005226  add     rax, rax
0x180005229  mov     [rbp+rax*8-8], r12d
0x18000522e  jmp     loc_180004FE1
0x180005233  mov     rdi, [rsp+68h+arg_8]
0x180005238  movsx   rax, dx
0x18000523c  movzx   ecx, word ptr [r8+rax*2-2]
0x180005242  inc     cx
0x180005245  mov     [rbx+0Eh], cx
0x180005249  test    cx, cx
0x18000524c  jle     loc_1800054EF
0x180005252  movsx   rdx, cx
  ... truncated ...
```
