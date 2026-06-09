# _RNvNtNtCs7vXzV21FY6F_8gdi_rust6region9from_path20region_from_path_mut

- ea: `0x1400101f0`
- end: `0x140011118`
- name: `_RNvNtNtCs7vXzV21FY6F_8gdi_rust6region9from_path20region_from_path_mut`
- size: `3880`
- prototype: `__int64 __fastcall(_DWORD *, _OWORD *, char, _DWORD *, char, unsigned int)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140005040`

## callees

- `0x140005210`
- `0x14000b710`
- `0x14000be40`
- `0x14000c1a0`
- `0x14000f3a0`
- `0x14000f4c0`
- `0x14000f720`
- `0x14000f800`
- `0x14000fab0`
- `0x14000fba0`
- `0x14000fdd0`
- `0x14000fe20`
- `0x1400101f0`
- `0x140011120`
- `0x140012b60`
- `0x140012f10`
- `0x14001778c`
- `0x1400177ac`
- `0x14001790a`
- `0x140017a10`
- `0x140017b00`
- `0x140017f00`
- `0x140018450`
- `0x1400184d7`
- `0x140018690`
- `0x1400189a0`
- `0x140018ab0`
- `0x140018cb7`

## pseudocode

```c
__int64 __fastcall RNvNtNtCs7vXzV21FY6F_8gdi_rust6region9from_path20region_from_path_mut(
        _DWORD *a1,
        _OWORD *a2,
        char a3,
        _DWORD *a4,
        char a5,
        unsigned int a6)
{
  __int64 *v7; // rax
  int v8; // r11d
  unsigned int v9; // r12d
  unsigned int v10; // esi
  unsigned __int64 v11; // r13
  __int64 ***v12; // r10
  __int64 **v13; // rbx
  __int64 v14; // rdi
  __int64 v15; // r14
  __int64 *v16; // rbp
  unsigned __int64 v17; // r15
  int v18; // esi
  int v19; // r9d
  int v20; // r8d
  _DWORD *v21; // rsi
  __int64 v22; // rbx
  __int64 v23; // r14
  __int64 v24; // r8
  __int64 v25; // rdx
  char *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  int v29; // r10d
  _OWORD *v30; // rdi
  _DWORD *v31; // rdx
  __int64 v32; // rcx
  _DWORD *v33; // rsi
  unsigned int v34; // eax
  _DWORD *v36; // rsi
  __int64 *v37; // rbx
  __int64 v38; // rdi
  __int64 v39; // rdi
  __int64 v40; // rbp
  void *v41; // r12
  __int64 *v42; // rdi
  void *v43; // rax
  __int64 v44; // r15
  char *v45; // rbx
  void *v46; // rdx
  __int64 v47; // r15
  void *v48; // r12
  int v49; // eax
  __int64 v50; // r14
  unsigned __int64 v51; // rax
  __int64 v52; // rsi
  void *v53; // rcx
  unsigned int *v54; // rbx
  __int64 v55; // rdi
  unsigned int v56; // edi
  __int64 v57; // rax
  __int64 v58; // rcx
  __int64 v59; // rdx
  int v60; // r8d
  int v61; // r8d
  __int64 v62; // r9
  bool v63; // sf
  __int64 v64; // r9
  unsigned __int64 v65; // r15
  unsigned int v66; // ebx
  int v67; // eax
  __int64 v68; // r9
  __int64 v69; // rax
  int v70; // r8d
  __int64 v71; // rcx
  __int128 *v72; // r10
  __int64 v73; // rdx
  __int64 v74; // r9
  __int128 *v75; // r9
  __int128 v76; // xmm0
  __int128 v77; // xmm1
  __int128 v78; // xmm0
  __int128 v79; // xmm1
  __int128 v80; // xmm0
  __int128 v81; // xmm1
  bool v82; // zf
  __int64 v83; // r14
  __int64 v84; // r12
  unsigned __int64 i; // r13
  __int128 v86; // xmm0
  __int128 v87; // xmm1
  __int64 v88; // rbp
  __int64 v89; // rsi
  __int64 v90; // rdx
  __int64 v91; // rax
  __int128 v92; // xmm1
  __int128 v93; // xmm2
  __int64 v94; // r15
  unsigned int v95; // r8d
  __int64 v96; // rbp
  __int64 *v97; // r12
  unsigned __int64 v98; // rbx
  unsigned __int64 v99; // rsi
  unsigned __int64 v100; // rdx
  __int64 v101; // rdi
  unsigned int v102; // eax
  int v103; // eax
  int v104; // eax
  unsigned __int64 v105; // r14
  char *v106; // rdi
  int v107; // ecx
  unsigned int v108; // eax
  __int64 v109; // rax
  __int64 v110; // r14
  unsigned __int64 v111; // rbx
  unsigned __int64 v112; // r15
  __int64 v113; // rdi
  unsigned __int64 v114; // rdx
  int v115; // esi
  __int64 v116; // rax
  __int64 v117; // r13
  __int64 v118; // rax
  __int64 v119; // r14
  unsigned __int64 v120; // rax
  int v121; // eax
  __int64 v122; // rdx
  unsigned __int64 v123; // rsi
  char v124; // [rsp+0h] [rbp-238h] BYREF
  __int64 v125; // [rsp+20h] [rbp-218h]
  char v126; // [rsp+37h] [rbp-201h]
  void *v127; // [rsp+38h] [rbp-200h]
  __int64 v128; // [rsp+40h] [rbp-1F8h]
  void *Src; // [rsp+48h] [rbp-1F0h]
  unsigned int v130; // [rsp+54h] [rbp-1E4h]
  __int64 v131; // [rsp+58h] [rbp-1E0h]
  __int64 v132; // [rsp+60h] [rbp-1D8h]
  __int64 v133; // [rsp+68h] [rbp-1D0h]
  char v134; // [rsp+77h] [rbp-1C1h] BYREF
  __int64 v135; // [rsp+78h] [rbp-1C0h] BYREF
  _OWORD v136[20]; // [rsp+80h] [rbp-1B8h] BYREF
  __int64 v137; // [rsp+1C0h] [rbp-78h] BYREF
  __int128 v138; // [rsp+1C8h] [rbp-70h]
  _BYTE v139[24]; // [rsp+1D8h] [rbp-60h] BYREF
  __int64 v140; // [rsp+1F0h] [rbp-48h]

  if ( (a5 & 1) == 0 )
  {
    v7 = (__int64 *)*((_QWORD *)a2 + 1);
    if ( !v7 )
    {
      LODWORD(v11) = 87;
      goto LABEL_48;
    }
    a6 = 0;
    do
    {
      while ( 1 )
      {
        v8 = *((_DWORD *)v7 + 4);
        v9 = ((v8 & 8) != 0) + a6;
        v10 = *((_DWORD *)v7 + 5);
        if ( (v8 & 0x10) != 0 )
          break;
        a6 = v10 - (v8 & 1) + v9;
        v7 = (__int64 *)*v7;
        if ( !v7 )
          goto LABEL_8;
      }
      a6 = v10 / 3 + v9;
      v7 = (__int64 *)*v7;
    }
    while ( v7 );
  }
LABEL_8:
  LODWORD(v11) = 87;
  if ( a6 < 2 )
    goto LABEL_48;
  if ( a4 && (a4[1] >= *((_DWORD *)a2 + 7) || a4[3] <= *((_DWORD *)a2 + 9)) )
    goto LABEL_37;
  v12 = (__int64 ***)*((_QWORD *)a2 + 1);
  if ( !v12 )
    RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed(&off_14001BB80);
  v13 = *v12;
  v14 = *((unsigned int *)v12 + 5);
  v15 = 4;
  if ( *((_DWORD *)v12 + 5) )
    v15 = (__int64)(v12 + 3);
  if ( !v13 )
  {
    if ( (unsigned int)v14 <= 1 )
    {
      v21 = a1;
      RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore16set_to_null_scan(a1, a2);
      a1 = v21;
      goto LABEL_50;
    }
    Src = a4;
    v126 = a3;
    v19 = *((_DWORD *)a2 + 7);
    v127 = a2;
    LODWORD(v125) = *((_DWORD *)a2 + 9);
    v128 = (__int64)a1;
    LODWORD(a2) = (_DWORD)v12 + 24;
    v20 = v14;
LABEL_34:
    v27 = gdi_rust::region::from_path::fast_fill_region_from_edges((_DWORD)a1, (_DWORD)a2, v20, v19, v125);
    a3 = v126;
    a4 = Src;
    if ( (v27 & 1) != 0 )
    {
      LODWORD(v11) = HIDWORD(v27);
      goto LABEL_48;
    }
    a1 = (_DWORD *)v128;
    a2 = v127;
    if ( (v27 & 0x100) == 0 )
      goto LABEL_37;
LABEL_50:
    v36 = a1;
    RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore20tighten_bounding_box(a1, a2);
    if ( (v36[7] & 0xF8000000) - 1 >= 0xF7FFFFFF
      && (v36[10] & 0xF8000000) - 1 >= 0xF7FFFFFF
      && (v36[9] & 0xF8000000) - 1 >= 0xF7FFFFFF )
    {
      LODWORD(v11) = 87;
      if ( (unsigned int)(v36[8] + 0x8000000) < 0x10000000 )
        LODWORD(v11) = 0;
    }
    goto LABEL_48;
  }
  if ( a6 > 0x28 || ((_DWORD)v12[2] & 2) != 0 )
    goto LABEL_37;
  v127 = a2;
  v128 = (__int64)a1;
  Src = a4;
  v126 = a3;
  v16 = *v13;
  v17 = *((unsigned int *)v13 + 5);
  v18 = *((_DWORD *)v13 + 4);
  memset(v136, 0, sizeof(v136));
  if ( (unsigned int)v14 >= 0x29 )
    RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail(0, v14, 40, &off_14001BB98);
  memmove(v136, (const void *)v15, 8 * v14);
  if ( !(v18 & 1 | (40 - v14 < v17)) )
  {
    v22 = (__int64)(v13 + 3);
    if ( !v17 )
      v22 = 4;
    v23 = v17 + v14;
    memmove((char *)v136 + 8 * v14, (const void *)v22, 8 * v17);
    if ( v16 )
    {
      while ( (v16[2] & 1) == 0 )
      {
        v24 = *((unsigned int *)v16 + 5);
        if ( 40 - (int)v23 < (unsigned int)v24 )
          break;
        v25 = (__int64)(v16 + 3);
        if ( !*((_DWORD *)v16 + 5) )
          v25 = 4;
        v16 = (__int64 *)*v16;
        v26 = (char *)v136 + 8 * v23;
        v23 += v24;
        memmove(v26, (const void *)v25, 8 * v24);
        if ( !v16 )
          goto LABEL_33;
      }
      goto LABEL_20;
    }
LABEL_33:
    v19 = *((_DWORD *)v127 + 7);
    LODWORD(v125) = *((_DWORD *)v127 + 9);
    a2 = v136;
    LODWORD(a1) = v128;
    v20 = v23;
    goto LABEL_34;
  }
LABEL_20:
  a3 = v126;
  a4 = Src;
  a1 = (_DWORD *)v128;
  a2 = v127;
LABEL_37:
  v28 = *((_DWORD *)a2 + 7);
  v29 = *((_DWORD *)a2 + 9);
  if ( v29 < v28 )
    goto LABEL_48;
  if ( a4 )
  {
    if ( a4[1] > v28 )
      v28 = a4[1];
    if ( a4[3] < v29 )
      v29 = a4[3];
  }
  v30 = a2;
  v31 = a1;
  v126 = a3;
  v32 = v29 - (__int64)v28;
  if ( v32 > 238609135 )
  {
    LODWORD(v11) = 534;
    goto LABEL_48;
  }
  v33 = a4;
  v34 = 0;
  if ( v32 > 0 )
    v34 = v32;
  RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore23clear_scans_and_reserve(v136, v31, 8LL * (v34 >> 4) + 108);
  if ( LODWORD(v136[0]) == 1 )
  {
    LODWORD(v11) = DWORD1(v136[0]);
    goto LABEL_48;
  }
  v135 = *((_QWORD *)&v136[0] + 1);
  v37 = (__int64 *)*((_QWORD *)v30 + 1);
  *(_QWORD *)v139 = 0;
  *(_QWORD *)&v139[8] = 8;
  *(_QWORD *)&v139[16] = 0;
  v38 = 3;
  if ( a6 >= 4 )
    v38 = a6;
  v39 = v38 + 1;
  RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm67646547_EE11finish_growCs7vXzV21FY6F_8gdi_rust_llvm_1180095224807683263(
    (unsigned int)v136,
    (unsigned int)v139,
    v39,
    8,
    48);
  if ( LODWORD(v136[0]) == 1 )
  {
    LODWORD(v11) = 14;
    goto LABEL_180;
  }
  v11 = *((_QWORD *)&v136[0] + 1);
  v137 = v39;
  v138 = *((unsigned __int64 *)&v136[0] + 1);
  cxxbridge1_PsGetCurrentThread(v136);
  if ( v37 )
  {
    v40 = *(_QWORD *)&v136[0];
    v41 = 0;
    v127 = 0;
    do
    {
      v42 = (__int64 *)*v37;
      *(_QWORD *)&v136[0] = v40;
      cxxbridge1_PsIsThreadTerminating(v136, v139);
      if ( v139[0] )
      {
        LODWORD(v11) = 31;
        if ( !v137 )
          goto LABEL_180;
LABEL_81:
        v53 = (void *)v138;
        goto LABEL_179;
      }
      v43 = v37 + 3;
      v44 = *((unsigned int *)v37 + 5);
      LODWORD(Src) = *((_DWORD *)v37 + 4);
      if ( ((unsigned __int8)Src & 1) != 0 )
      {
        if ( !v44 )
          RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(0, 0, &off_14001BAA8);
        --v44;
        v45 = (char *)(v37 + 4);
        v127 = v43;
        v46 = v43;
      }
      else
      {
        v45 = (char *)(v37 + 3);
        v46 = v41;
      }
      v47 = 8 * v44;
      while ( v47 )
      {
        if ( !v46 )
          RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed(&off_14001BAC0);
        v48 = v45;
        v45 += 8;
        v49 = gdi_rust::region::from_path::GlobalEdgeTable::add_edge(&v137, v46, v48, v33);
        v47 -= 8;
        v46 = v48;
        if ( v49 )
          goto LABEL_80;
      }
      if ( ((unsigned __int8)Src & 2) != 0 )
      {
        if ( !v46 )
          goto LABEL_201;
        if ( !v127 )
          RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed(&off_14001BAF0);
        v49 = gdi_rust::region::from_path::GlobalEdgeTable::add_edge(&v137, v46, v127, v33);
        if ( v49 )
        {
LABEL_80:
          LODWORD(v11) = v49;
          if ( !v137 )
            goto LABEL_180;
          goto LABEL_81;
        }
        v46 = 0;
      }
      v41 = v46;
      v37 = v42;
    }
    while ( v42 );
    v50 = v137;
    LODWORD(v11) = v138;
    if ( __OFSUB__(-v137, 1) )
      goto LABEL_180;
    v51 = DWORD1(v138);
    v52 = *((_QWORD *)&v138 + 1);
  }
  else
  {
    v51 = HIDWORD(v11);
    v50 = 1;
    v52 = 0;
  }
  v54 = (unsigned int *)((v51 << 32) | (unsigned int)v11);
  cxxbridge1_PsGetCurrentThread(v136);
  v55 = *(_QWORD *)&v136[0];
  RINvCs3PyRTeGQ7Na_12fallible_vec20try_with_capacity_inNtNtNtCs7vXzV21FY6F_8gdi_rust6region9from_path4EdgeINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm67646547_EEBW_(
    v136,
    v52);
  if ( __OFSUB__(-*(_QWORD *)&v136[0], 1) )
  {
    LODWORD(v11) = 14;
    goto LABEL_177;
  }
  v137 = *(_QWORD *)&v136[0];
  v138 = *(_OWORD *)((char *)v136 + 8);
  *(_QWORD *)&v136[0] = v55;
  cxxbridge1_PsIsThreadTerminating(v136, v139);
  if ( v139[0] )
  {
LABEL_86:
    LODWORD(v11) = 31;
    if ( v137 )
      goto LABEL_176;
    goto LABEL_177;
  }
  Src = v54 + 12;
  v127 = v54;
  v131 = v55;
  v56 = 0x80000000;
  v128 = v50;
  while ( 1 )
  {
    if ( !*((_QWORD *)&v138 + 1) )
      goto LABEL_97;
    v57 = v138;
    v58 = 48LL * *((_QWORD *)&v138 + 1);
    v59 = 0;
    do
    {
      v60 = *(_DWORD *)(v57 + v59 + 24) - 1;
      *(_DWORD *)(v57 + v59 + 24) = v60;
      if ( v60 > 0 )
      {
        v61 = *(_DWORD *)(v57 + v59 + 36) + *(_DWORD *)(v57 + v59 + 28);
        *(_DWORD *)(v57 + v59 + 28) = v61;
        v62 = *(_QWORD *)(v57 + v59);
        v63 = *(_QWORD *)(v57 + v59 + 8) + v62 < 0;
        v64 = *(_QWORD *)(v57 + v59 + 8) + v62;
        *(_QWORD *)(v57 + v59) = v64;
        if ( !v63 )
        {
          *(_QWORD *)(v57 + v59) = v64 - *(_QWORD *)(v57 + v59 + 16);
          *(_DWORD *)(v57 + v59 + 28) = *(char *)(v57 + v59 + 40) + v61;
        }
      }
      v59 += 48;
    }
    while ( v58 != v59 );
    RINvMs_NtCsexo9QDNEsji_5alloc3vecINtB5_3VecNtNtNtCs7vXzV21FY6F_8gdi_rust6region9from_path4EdgeINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm67646547_EE10retain_mutNCINvB2_6retainNCNvMs_BH_NtBH_15ActiveEdgeTable7advance0E0EBL_(
      &v137,
      &v134);
    v65 = *((_QWORD *)&v138 + 1);
    if ( *((_QWORD *)&v138 + 1) != 1 )
      break;
LABEL_111:
    if ( !v52 )
    {
      v52 = 0;
      goto LABEL_129;
    }
LABEL_112:
    if ( v54[8] == v56 )
    {
      v83 = 0;
      v84 = 0;
      for ( i = 0; ; ++i )
      {
        if ( i >= v65 || (signed int)v54[7] <= *(_DWORD *)(v138 + v84 + 28) )
        {
          v86 = *(_OWORD *)v54;
          v87 = *((_OWORD *)v54 + 1);
          v136[2] = *((_OWORD *)v54 + 2);
          v136[1] = v87;
          v136[0] = v86;
          v88 = v52 - 1;
          memmove(v54, Src, 48 * (v52 - 1));
          v89 = *((_QWORD *)&v138 + 1);
          if ( v137 == *((_QWORD *)&v138 + 1) )
          {
            v94 = 2LL * *((_QWORD *)&v138 + 1);
            if ( (unsigned __int64)(2LL * *((_QWORD *)&v138 + 1)) < 5 )
              v94 = 4;
            RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm67646547_EE11finish_growCs7vXzV21FY6F_8gdi_rust_llvm_1180095224807683263(
              (unsigned int)v139,
              (unsigned int)&v137,
              v94,
              8,
              48);
            if ( *(_DWORD *)v139 == 1 )
            {
              LODWORD(v11) = 14;
              v54 = (unsigned int *)v127;
              goto LABEL_174;
            }
            v90 = *(_QWORD *)&v139[8];
            *(_QWORD *)&v138 = *(_QWORD *)&v139[8];
            v137 = v94;
            v54 = (unsigned int *)v127;
          }
          else
          {
            v90 = v138;
          }
          memmove((void *)(v90 + v84 + 48), (const void *)(v84 + v90), 48 * (v83 + v89));
          v91 = v138;
          v92 = v136[1];
          v93 = v136[2];
          *(_OWORD *)(v138 + v84) = v136[0];
          *(_OWORD *)(v91 + v84 + 16) = v92;
          *(_OWORD *)(v91 + v84 + 32) = v93;
          v65 = ++*((_QWORD *)&v138 + 1);
          if ( !v88 )
          {
            v52 = 0;
LABEL_127:
            v50 = v128;
            break;
          }
          v52 = v88;
          if ( v54[8] != v56 )
            goto LABEL_127;
        }
        v84 += 48;
        --v83;
      }
    }
LABEL_129:
    v95 = v56;
    v96 = v138;
    RNvMs5_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE3new(
      (unsigned int)v136,
      v135,
      v95,
      ++v56,
      v65);
    v97 = *(__int64 **)&v136[0];
    LODWORD(v11) = DWORD2(v136[0]);
    if ( !*(_QWORD *)&v136[0] )
    {
      v109 = v131;
      goto LABEL_167;
    }
    v130 = v56;
    v132 = v52;
    *(_DWORD *)&v139[20] = DWORD1(v136[1]);
    *(_QWORD *)&v139[12] = *(_QWORD *)((char *)v136 + 12);
    *(_QWORD *)v139 = *(_QWORD *)&v136[0];
    *(_DWORD *)&v139[8] = DWORD2(v136[0]);
    if ( v126 )
    {
      if ( v65 )
      {
        v98 = *(_QWORD *)&v139[16] + 3LL;
        v99 = 0;
        while ( 1 )
        {
          while ( 1 )
          {
            v100 = v97[2];
            if ( v98 > v100 )
              goto LABEL_200;
            v101 = 48 * v99;
            v102 = *(_DWORD *)(v96 + 48 * v99 + 28);
            if ( v100 == v98 || *(_DWORD *)(v97[1] + 4 * v100 - 4) < (signed int)v102 )
            {
              v103 = RNvMs4_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11append_wallCs7vXzV21FY6F_8gdi_rust(
                       v139,
                       v102);
              if ( v103 )
                goto LABEL_172;
            }
            else
            {
              RNvMs4_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE8pop_wallCs7vXzV21FY6F_8gdi_rust(v139);
            }
            v104 = *(char *)(v101 + v96 + 41);
            v105 = v99 + 1;
            v106 = (char *)(v96 + 89 + v101);
            do
            {
              if ( v105 >= v65 )
              {
                v123 = v99 + 1;
                if ( v65 > v123 )
                  v123 = v65;
                RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(v123, v65, &off_14001BB68);
              }
              v107 = *v106;
              ++v105;
              v106 += 48;
              v104 += v107;
            }
            while ( v104 );
            v100 = v97[2];
            if ( v98 > v100 )
LABEL_200:
              RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail(
                v98,
                v100,
                v100,
                &anon_01189c164b0c425bf67614ee34d1a89c_27_llvm_7541658972310832757);
            v108 = *(_DWORD *)(v106 - 61);
            if ( v98 == v100 || *(_DWORD *)(v97[1] + 4 * v100 - 4) < (signed int)v108 )
              break;
            RNvMs4_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE8pop_wallCs7vXzV21FY6F_8gdi_rust(v139);
            v99 = v105;
            if ( v105 >= v65 )
              goto LABEL_165;
          }
          v103 = RNvMs4_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11append_wallCs7vXzV21FY6F_8gdi_rust(
                   v139,
                   v108);
          if ( v103 )
            break;
          v99 = v105;
          if ( v105 >= v65 )
            goto LABEL_165;
        }
LABEL_172:
        LODWORD(v11) = v103;
LABEL_173:
        v54 = (unsigned int *)v127;
        RNvXs6_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EENtNtNtCs9MWeMO1rkJG_4core3ops4drop4Drop4dropCs7vXzV21FY6F_8gdi_rust(v139);
LABEL_174:
        v50 = v128;
LABEL_175:
        if ( v137 )
LABEL_176:
          Win32FreePool_0(v138);
LABEL_177:
        if ( v50 )
        {
          v53 = v54;
          goto LABEL_179;
        }
        goto LABEL_180;
      }
    }
    else if ( v65 )
    {
      v110 = 48 * v65;
      v111 = *(_QWORD *)&v139[16];
      v112 = *(_QWORD *)&v139[16] + 3LL;
      v113 = 0;
      v133 = v110;
      do
      {
        while ( 1 )
        {
          v114 = v97[2];
          if ( v112 > v114 )
            RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail(
              v112,
              v114,
              v97[2],
              &anon_01189c164b0c425bf67614ee34d1a89c_27_llvm_7541658972310832757);
          v115 = *(_DWORD *)(v96 + v113 + 28);
          v116 = v97[1];
          if ( v112 == v114 || *(_DWORD *)(v116 + 4 * v114 - 4) < v115 )
            break;
          RNvMs4_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE8pop_wallCs7vXzV21FY6F_8gdi_rust(v139);
          v113 += 48;
          if ( v110 == v113 )
            goto LABEL_165;
        }
        if ( v111 >= v114 )
          RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
            v111,
            v114,
            &anon_01189c164b0c425bf67614ee34d1a89c_17_llvm_7541658972310832757);
        ++*(_DWORD *)(v116 + 4 * v111);
        v117 = v97[2];
        if ( *v97 == v117 )
        {
          v119 = 2 * v117;
          if ( (unsigned __int64)(2 * v117) < 5 )
            v119 = 4;
          RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCs7vXzV21FY6F_8gdi_rust_llvm_1180095224807683263(
            (unsigned int)v136,
            (_DWORD)v97,
            v119,
            4,
            4);
          if ( LOBYTE(v136[0]) )
          {
            LODWORD(v11) = 14;
            goto LABEL_173;
          }
          v118 = *((_QWORD *)&v136[0] + 1);
          v97[1] = *((_QWORD *)&v136[0] + 1);
          *v97 = v119;
          v110 = v133;
        }
        else
        {
          v118 = v97[1];
        }
        *(_DWORD *)(v118 + 4 * v117) = v115;
        ++v97[2];
        v113 += 48;
      }
      while ( v110 != v113 );
    }
LABEL_165:
    *(_QWORD *)&v136[1] = *(_QWORD *)&v139[16];
    v136[0] = *(_OWORD *)v139;
    v120 = RNvMs4_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE18commit_or_coalesceCs7vXzV21FY6F_8gdi_rust(v136);
    if ( (v120 & 1) != 0 )
    {
      v11 = HIDWORD(v120);
      v50 = v128;
      v54 = (unsigned int *)v127;
      v52 = v132;
      v109 = v131;
      v56 = v130;
LABEL_167:
      if ( (_DWORD)v11 )
        goto LABEL_175;
      goto LABEL_170;
    }
    v50 = v128;
    v54 = (unsigned int *)v127;
    v52 = v132;
    v109 = v131;
    v56 = v130;
LABEL_170:
    *(_QWORD *)&v136[0] = v109;
    cxxbridge1_PsIsThreadTerminating(v136, v139);
    if ( v139[0] )
      goto LABEL_86;
  }
  if ( *((_QWORD *)&v138 + 1) )
  {
    v68 = 1;
    v69 = v138;
    v70 = 0;
    v71 = 0;
    while ( 1 )
    {
      v73 = v68;
      v74 = 48 * v68;
      if ( *(_DWORD *)(v69 + v74 + 28) >= *(_DWORD *)(v69 + 48 * v71 + 28) )
      {
        if ( v71 + 2 == v65 )
        {
          v71 = 0;
          v68 = 1;
          v82 = (v70 & 1) == 0;
          v70 = 0;
          if ( v82 )
            goto LABEL_111;
        }
        else
        {
          LODWORD(v72) = v70;
LABEL_105:
          v68 = v73 + 1;
          v70 = (int)v72;
          v71 = v73;
          if ( v73 + 1 == v65 )
            RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(v65, v65, &off_14001BB50);
        }
      }
      else
      {
        v75 = (__int128 *)(v69 + v74);
        v72 = (__int128 *)(v69 + 48 * v71);
        v76 = *v72;
        v77 = v72[1];
        v136[2] = v72[2];
        v136[1] = v77;
        v136[0] = v76;
        v78 = *v75;
        v79 = v75[1];
        v72[2] = v75[2];
        v72[1] = v79;
        *v72 = v78;
        v80 = v136[0];
        v81 = v136[1];
        v75[2] = v136[2];
        v75[1] = v81;
        *v75 = v80;
        LOBYTE(v72) = 1;
        v70 = 0;
        v68 = 1;
        v82 = v71 + 2 == v65;
        v71 = 0;
        if ( !v82 )
          goto LABEL_105;
      }
    }
  }
LABEL_97:
  if ( v52 )
  {
    v66 = v54[8];
    if ( v66 == v56 )
    {
      v65 = 0;
    }
    else
    {
      v67 = RNvMs5_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11append_scan(
              v135,
              v56,
              v66,
              4,
              0);
      if ( v67 )
      {
        LODWORD(v11) = v67;
LABEL_190:
        v54 = (unsigned int *)v127;
        if ( v137 )
          goto LABEL_176;
        goto LABEL_177;
      }
      v65 = *((_QWORD *)&v138 + 1);
      v56 = v66;
    }
    v54 = (unsigned int *)v127;
    goto LABEL_112;
  }
  v121 = RNvMs5_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11append_scan(
           v135,
           v56,
           0x7FFFFFFF,
           4,
           0);
  if ( v121 )
  {
    LODWORD(v11) = v121;
    goto LABEL_190;
  }
  RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore20tighten_bounding_box(v135, v122);
  LODWORD(v11) = 87;
  if ( (unsigned __int8)rgncore::is_valid_scr_rc(v135 + 28) )
    LODWORD(v11) = 0;
  if ( v137 )
    Win32FreePool_0(v138);
  if ( v50 )
  {
    v53 = v127;
LABEL_179:
    Win32FreePool_0(v53);
  }
LABEL_180:
  RNvXCsdcpJtfrLhSH_7rgncoreNtB2_11RegionGuardNtNtNtCs9MWeMO1rkJG_4core3ops4drop4Drop4drop(&v135);
LABEL_48:
  if ( _security_cookie != ((unsigned __int64)&v124 ^ v140) )
LABEL_201:
    RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed(&off_14001BAD8);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400101f0  push    r15
0x1400101f2  push    r14
0x1400101f4  push    r13
0x1400101f6  push    r12
0x1400101f8  push    rsi
0x1400101f9  push    rdi
0x1400101fa  push    rbp
0x1400101fb  push    rbx
0x1400101fc  sub     rsp, 1F8h
0x140010203  mov     rax, cs:__security_cookie
0x14001020a  xor     rax, rsp
0x14001020d  mov     [rsp+238h+var_48], rax
0x140010215  test    [rsp+238h+arg_20], 1
0x14001021d  jz      short loc_140010229
0x14001021f  mov     r12d, [rsp+238h+arg_28]
0x140010227  jmp     short loc_14001028E
0x140010229  mov     rax, [rdx+8]
0x14001022d  test    rax, rax
0x140010230  jz      loc_140010385
0x140010236  xor     r12d, r12d
0x140010239  mov     r10d, 0AAAAAAABh
0x14001023f  jmp     short loc_140010262
0x140010250  and     r11d, 1
0x140010254  sub     esi, r11d
0x140010257  add     r12d, esi
0x14001025a  mov     rax, [rax]
0x14001025d  test    rax, rax
0x140010260  jz      short loc_14001028E
0x140010262  mov     r11d, [rax+10h]
0x140010266  bt      r11d, 3
0x14001026b  adc     r12d, 0
0x14001026f  mov     esi, [rax+14h]
0x140010272  test    r11b, 10h
0x140010276  jz      short loc_140010250
0x140010278  mov     r11d, esi
0x14001027b  imul    r11, r10
0x14001027f  shr     r11, 21h
0x140010283  add     r12d, r11d
0x140010286  mov     rax, [rax]
0x140010289  test    rax, rax
0x14001028c  jnz     short loc_140010262
0x14001028e  mov     r13d, 57h ; 'W'
0x140010294  cmp     r12d, 2
0x140010298  jb      loc_140010530
0x14001029e  test    r9, r9
0x1400102a1  jz      short loc_1400102BD
0x1400102a3  mov     eax, [r9+4]
0x1400102a7  cmp     eax, [rdx+1Ch]
0x1400102aa  jge     loc_1400104AF
0x1400102b0  mov     eax, [r9+0Ch]
0x1400102b4  cmp     eax, [rdx+24h]
0x1400102b7  jle     loc_1400104AF
0x1400102bd  mov     r10, [rdx+8]
0x1400102c1  test    r10, r10
0x1400102c4  jz      loc_1400110AE
0x1400102ca  mov     rbx, [r10]
0x1400102cd  mov     edi, [r10+14h]
0x1400102d1  lea     rax, [r10+18h]
0x1400102d5  test    rdi, rdi
0x1400102d8  mov     r14d, 4
0x1400102de  cmovnz  r14, rax
0x1400102e2  test    rbx, rbx
0x1400102e5  jz      loc_140010390
0x1400102eb  cmp     r12d, 28h ; '('
0x1400102ef  ja      loc_1400104AF
0x1400102f5  mov     eax, [r10+10h]
0x1400102f9  and     eax, 2
0x1400102fc  jnz     loc_1400104AF
0x140010302  mov     [rsp+238h+var_200], rdx
0x140010307  mov     [rsp+238h+var_1F8], rcx
0x14001030c  mov     [rsp+238h+Src], r9
0x140010311  mov     [rsp+238h+var_201], r8b
0x140010316  mov     rbp, [rbx]
0x140010319  mov     r15d, [rbx+14h]
0x14001031d  mov     esi, [rbx+10h]
0x140010320  lea     rcx, [rsp+238h+var_1B8]; void *
0x140010328  mov     r8d, 140h; Size
0x14001032e  xor     edx, edx; Val
0x140010330  call    memset
0x140010335  cmp     edi, 29h ; ')'
0x140010338  jnb     loc_140010F87
0x14001033e  lea     r8, ds:0[rdi*8]; Size
0x140010346  lea     rcx, [rsp+238h+var_1B8]; void *
0x14001034e  mov     rdx, r14; Src
0x140010351  call    memmove
0x140010356  mov     eax, 28h ; '('
0x14001035b  sub     rax, rdi
0x14001035e  cmp     rax, r15
0x140010361  setb    al
0x140010364  or      al, sil
0x140010367  test    al, 1
0x140010369  jz      short loc_1400103CF
0x14001036b  movzx   r8d, [rsp+238h+var_201]
0x140010371  mov     r9, [rsp+238h+Src]
0x140010376  mov     rcx, [rsp+238h+var_1F8]
0x14001037b  mov     rdx, [rsp+238h+var_200]
0x140010380  jmp     loc_1400104AF
0x140010385  mov     r13d, 57h ; 'W'
0x14001038b  jmp     loc_140010530
0x140010390  cmp     edi, 1
0x140010393  jbe     short loc_1400103BF
0x140010395  mov     [rsp+238h+Src], r9
0x14001039a  mov     [rsp+238h+var_201], r8b
0x14001039f  mov     r9d, [rdx+1Ch]
0x1400103a3  mov     [rsp+238h+var_200], rdx
0x1400103a8  mov     edx, [rdx+24h]
0x1400103ab  mov     dword ptr [rsp+238h+var_218], edx
0x1400103af  mov     [rsp+238h+var_1F8], rcx
0x1400103b4  mov     rdx, rax
0x1400103b7  mov     r8, rdi
0x1400103ba  jmp     loc_14001047A
0x1400103bf  mov     rsi, rcx
0x1400103c2  call    _RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore16set_to_null_scan
0x1400103c7  mov     rcx, rsi
0x1400103ca  jmp     loc_140010562
0x1400103cf  add     rbx, 18h
0x1400103d3  test    r15, r15
0x1400103d6  mov     esi, 4
0x1400103db  cmovz   rbx, rsi
0x1400103df  lea     r14, [r15+rdi]
0x1400103e3  lea     rcx, [rsp+rdi*8+238h+var_238]
0x1400103e7  add     rcx, 80h; void *
0x1400103ee  shl     r15, 3
0x1400103f2  mov     rdx, rbx; Src
0x1400103f5  mov     r8, r15; Size
0x1400103f8  call    memmove
0x1400103fd  test    rbp, rbp
0x140010400  jz      short loc_14001045A
0x140010402  nop     word ptr [rax+rax+00000000h]
0x140010410  test    byte ptr [rbp+10h], 1
0x140010414  jnz     loc_14001036B
0x14001041a  mov     r8d, [rbp+14h]
0x14001041e  mov     eax, 28h ; '('
0x140010423  sub     rax, r14
0x140010426  cmp     eax, r8d
0x140010429  jb      loc_14001036B
0x14001042f  lea     rdx, [rbp+18h]
0x140010433  test    r8, r8
0x140010436  cmovz   rdx, rsi; Src
0x14001043a  mov     rbp, [rbp+0]
0x14001043e  lea     rcx, [rsp+r14*8+238h+var_238]
0x140010442  add     rcx, 80h; void *
0x140010449  add     r14, r8
0x14001044c  shl     r8, 3; Size
0x140010450  call    memmove
0x140010455  test    rbp, rbp
0x140010458  jnz     short loc_140010410
0x14001045a  mov     rax, [rsp+238h+var_200]
0x14001045f  mov     r9d, [rax+1Ch]
0x140010463  mov     eax, [rax+24h]
0x140010466  mov     dword ptr [rsp+238h+var_218], eax
0x14001046a  lea     rdx, [rsp+238h+var_1B8]
0x140010472  mov     rcx, [rsp+238h+var_1F8]
0x140010477  mov     r8, r14
0x14001047a  call    gdi_rust__region__from_path__fast_fill_region_from_edges
0x14001047f  test    al, 1
0x140010481  movzx   r8d, [rsp+238h+var_201]
0x140010487  mov     r9, [rsp+238h+Src]
0x14001048c  jz      short loc_14001049A
0x14001048e  shr     rax, 20h
0x140010492  mov     r13d, eax
0x140010495  jmp     loc_140010530
0x14001049a  test    eax, 100h
0x14001049f  mov     rcx, [rsp+238h+var_1F8]
0x1400104a4  mov     rdx, [rsp+238h+var_200]
0x1400104a9  jnz     loc_140010562
0x1400104af  mov     eax, [rdx+1Ch]
0x1400104b2  mov     r10d, [rdx+24h]
0x1400104b6  cmp     r10d, eax
0x1400104b9  jl      short loc_140010530
0x1400104bb  test    r9, r9
0x1400104be  jz      short loc_1400104D6
0x1400104c0  mov     r11d, [r9+4]
0x1400104c4  cmp     r11d, eax
0x1400104c7  cmovg   eax, r11d
0x1400104cb  mov     r11d, [r9+0Ch]
0x1400104cf  cmp     r11d, r10d
0x1400104d2  cmovl   r10d, r11d
0x1400104d6  mov     rdi, rdx
0x1400104d9  mov     rdx, rcx
0x1400104dc  mov     [rsp+238h+var_201], r8b
0x1400104e1  movsxd  rcx, r10d
0x1400104e4  cdqe
0x1400104e6  sub     rcx, rax
0x1400104e9  cmp     rcx, 0E38E2EFh
0x1400104f0  jg      loc_140010F7C
0x1400104f6  mov     rsi, r9
0x1400104f9  xor     eax, eax
0x1400104fb  test    rcx, rcx
0x1400104fe  cmovg   rax, rcx
0x140010502  shr     eax, 4
0x140010505  lea     r8, ds:6Ch[rax*8]
0x14001050d  lea     rcx, [rsp+238h+var_1B8]
0x140010515  call    _RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore23clear_scans_and_reserve
0x14001051a  cmp     dword ptr [rsp+238h+var_1B8], 1
0x140010522  jnz     loc_1400105B9
0x140010528  mov     r13d, dword ptr [rsp+238h+var_1B8+4]
0x140010530  mov     rax, [rsp+238h+var_48]
0x140010538  xor     rax, rsp
0x14001053b  mov     rcx, cs:__security_cookie
0x140010542  cmp     rcx, rax
0x140010545  jnz     loc_140011086
0x14001054b  mov     eax, r13d
0x14001054e  add     rsp, 1F8h
0x140010555  pop     rbx
0x140010556  pop     rbp
0x140010557  pop     rdi
0x140010558  pop     rsi
0x140010559  pop     r12
0x14001055b  pop     r13
0x14001055d  pop     r14
0x14001055f  pop     r15
0x140010561  retn
0x140010562  mov     rsi, rcx
0x140010565  call    _RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore20tighten_bounding_box
0x14001056a  mov     eax, 0F8000000h
0x14001056f  mov     ecx, [rsi+1Ch]
0x140010572  and     ecx, eax
0x140010574  dec     ecx
0x140010576  cmp     ecx, 0F7FFFFFFh
0x14001057c  jb      short loc_140010530
0x14001057e  and     eax, [rsi+28h]
0x140010581  dec     eax
0x140010583  cmp     eax, 0F7FFFFFFh
0x140010588  jb      short loc_140010530
0x14001058a  mov     eax, 0F8000000h
0x14001058f  and     eax, [rsi+24h]
0x140010592  dec     eax
0x140010594  cmp     eax, 0F7FFFFFFh
0x140010599  jb      short loc_140010530
0x14001059b  mov     eax, 8000000h
0x1400105a0  add     eax, [rsi+20h]
0x1400105a3  xor     ecx, ecx
0x1400105a5  cmp     eax, 10000000h
0x1400105aa  mov     r13d, 57h ; 'W'
0x1400105b0  cmovb   r13d, ecx
0x1400105b4  jmp     loc_140010530
0x1400105b9  mov     rax, qword ptr [rsp+238h+var_1B8+8]
0x1400105c1  mov     [rsp+238h+var_1C0], rax
0x1400105c6  mov     rbx, [rdi+8]
0x1400105ca  mov     qword ptr [rsp+238h+var_60], 0
0x1400105d6  mov     qword ptr [rsp+238h+var_60+8], 8
0x1400105e2  mov     [rsp+238h+var_50], 0
0x1400105ee  cmp     r12d, 4
0x1400105f2  mov     edi, 3
0x1400105f7  cmovnb  edi, r12d
0x1400105fb  inc     rdi
0x1400105fe  mov     [rsp+238h+var_218], 30h ; '0'
0x140010607  lea     rcx, [rsp+238h+var_1B8]
0x14001060f  lea     rdx, [rsp+238h+var_60]
0x140010617  mov     r9d, 8
0x14001061d  mov     r8, rdi
0x140010620  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm67646547_EE11finish_growCs7vXzV21FY6F_8gdi_rust_llvm_1180095224807683263
0x140010625  cmp     dword ptr [rsp+238h+var_1B8], 1
0x14001062d  jnz     short loc_14001063A
0x14001062f  mov     r13d, 0Eh
0x140010635  jmp     loc_140010F56
0x14001063a  mov     r13, qword ptr [rsp+238h+var_1B8+8]
0x140010642  mov     [rsp+238h+var_78], rdi
0x14001064a  mov     qword ptr [rsp+238h+var_70], r13
0x140010652  mov     qword ptr [rsp+238h+var_70+8], 0
0x14001065e  lea     rcx, [rsp+238h+var_1B8]
0x140010666  call    cxxbridge1$PsGetCurrentThread
0x14001066b  test    rbx, rbx
0x14001066e  jz      loc_1400107C3
0x140010674  mov     rbp, qword ptr [rsp+238h+var_1B8]
0x14001067c  xor     r12d, r12d
0x14001067f  lea     rcx, [rsp+238h+var_1B8]
0x140010687  lea     rax, [rsp+238h+var_60]
0x14001068f  lea     r14, [rsp+238h+var_78]
0x140010697  mov     [rsp+238h+var_200], 0
0x1400106a0  mov     rdi, [rbx]
0x1400106a3  mov     qword ptr [rsp+238h+var_1B8], rbp
0x1400106ab  mov     rdx, rax
0x1400106ae  call    cxxbridge1$PsIsThreadTerminating
0x1400106b3  cmp     byte ptr [rsp+238h+var_60], 0
0x1400106bb  jnz     loc_140010F65
0x1400106c1  lea     rax, [rbx+18h]
0x1400106c5  mov     ecx, [rbx+10h]
0x1400106c8  mov     r15d, [rbx+14h]
0x1400106cc  test    cl, 1
0x1400106cf  mov     dword ptr [rsp+238h+Src], ecx
0x1400106d3  jnz     short loc_1400106DD
0x1400106d5  mov     rbx, rax
0x1400106d8  mov     rdx, r12
0x1400106db  jmp     short loc_1400106F5
0x1400106dd  test    r15, r15
0x1400106e0  jz      loc_140011107
0x1400106e6  dec     r15
0x1400106e9  add     rbx, 20h ; ' '
0x1400106ed  mov     [rsp+238h+var_200], rax
0x1400106f2  mov     rdx, rax
0x1400106f5  shl     r15, 3
0x1400106f9  test    r15, r15
0x1400106fc  jz      short loc_140010729
0x1400106fe  test    rdx, rdx
0x140010701  jz      loc_140010F9E
0x140010707  mov     r12, rbx
0x14001070a  add     rbx, 8
0x14001070e  mov     rcx, r14
  ... truncated ...
```
