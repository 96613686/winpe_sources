# gdi_rust::region::from_path::fast_fill_region_from_edges

- ea: `0x140011120`
- end: `0x1400120e0`
- name: `gdi_rust::region::from_path::fast_fill_region_from_edges`
- size: `4032`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400101f0`

## callees

- `0x14000abf0`
- `0x14000c1a0`
- `0x14000f3a0`
- `0x14000f6b0`
- `0x140011120`
- `0x140012b60`
- `0x140017a10`
- `0x1400184d7`
- `0x140018780`
- `0x1400187a0`

## pseudocode

```c
__int64 __fastcall gdi_rust::region::from_path::fast_fill_region_from_edges(
        unsigned __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        int a5)
{
  unsigned __int64 v5; // rsi
  unsigned __int64 v7; // rdx
  int v8; // eax
  __int64 v9; // r8
  unsigned __int64 v10; // rbx
  int v11; // r10d
  unsigned __int64 v12; // rcx
  bool v13; // cc
  unsigned __int64 v14; // rbx
  int v15; // r8d
  __int64 v16; // r15
  unsigned __int64 v17; // r10
  int v18; // r11d
  __int64 v19; // r8
  int v20; // r11d
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // r8
  int v23; // r10d
  unsigned __int64 v24; // r8
  int v25; // r11d
  __int64 v26; // rax
  int v27; // eax
  __int64 v28; // rbp
  unsigned int v29; // eax
  int v30; // ecx
  __int64 v31; // r15
  __int64 v32; // r14
  unsigned __int64 v33; // rbp
  unsigned __int64 v34; // r13
  unsigned int v35; // eax
  __int64 v36; // r10
  __int64 v37; // r9
  int v38; // ecx
  unsigned __int64 v39; // r13
  unsigned __int64 v40; // rdx
  unsigned __int64 v41; // r11
  unsigned __int64 v42; // rbp
  unsigned __int64 v43; // r8
  unsigned __int64 v44; // rax
  __int64 v45; // rcx
  int v46; // r13d
  unsigned __int64 v47; // rcx
  __int64 v48; // rbp
  int v49; // r9d
  int v50; // r11d
  int v51; // r10d
  int v52; // eax
  int v53; // ebp
  int v54; // ecx
  int v55; // eax
  int v56; // r11d
  int v57; // ecx
  char v58; // si
  unsigned int v59; // edx
  int v60; // r11d
  int v61; // eax
  bool v62; // bp
  int v63; // r14d
  int v64; // eax
  int v65; // r14d
  bool v66; // sf
  int v67; // eax
  int v68; // r12d
  bool v69; // zf
  int v70; // r9d
  int v71; // ecx
  bool v72; // sf
  int v73; // eax
  unsigned __int64 v74; // r11
  int v75; // edx
  int v76; // r11d
  int v77; // r10d
  int v78; // ecx
  __int64 v79; // rax
  int v80; // r10d
  int v81; // r11d
  int v82; // r9d
  int v83; // ecx
  int v84; // r14d
  int v85; // eax
  int v86; // r11d
  char v87; // cl
  unsigned int v88; // edx
  int v89; // r11d
  int v90; // eax
  bool v91; // bp
  int v92; // r14d
  int v93; // eax
  int v94; // r14d
  bool v95; // sf
  int v96; // eax
  int v97; // r12d
  int v98; // r10d
  int v99; // ecx
  bool v100; // sf
  int v101; // eax
  unsigned __int64 v102; // r11
  int v103; // edx
  int v104; // r11d
  int v105; // r14d
  int v106; // eax
  int v107; // r8d
  int v108; // r14d
  __int64 v109; // rax
  __int64 v110; // r8
  int v111; // ebp
  __int64 v112; // rax
  __int64 v113; // rdx
  __int64 v114; // r8
  __int64 v115; // rax
  __int64 v116; // rdx
  __int64 v117; // rcx
  unsigned __int64 v118; // r9
  unsigned int v119; // ecx
  unsigned int v120; // eax
  __int64 v121; // rax
  __int64 v122; // rdx
  int v123; // eax
  int v124; // esi
  int v125; // ebp
  int v126; // r14d
  int v127; // ecx
  int v128; // ebp
  int v129; // esi
  int v130; // r14d
  int v131; // r15d
  unsigned __int64 v132; // r9
  __int64 v133; // r8
  unsigned __int64 v134; // rdx
  int v135; // ebp
  unsigned __int64 v136; // r13
  int v137; // r14d
  int v138; // r11d
  int v139; // r12d
  __int64 v140; // r10
  int v141; // esi
  int v142; // eax
  int v143; // eax
  unsigned __int64 v144; // rbp
  __int64 v145; // rax
  unsigned __int64 v146; // rdx
  unsigned __int64 v147; // r9
  unsigned __int64 v148; // rdx
  __int64 v149; // r8
  __int64 v150; // rax
  unsigned __int64 v151; // rcx
  __int64 v152; // rax
  __int64 v153; // rdx
  unsigned __int64 v154; // rdx
  unsigned __int64 v155; // r9
  unsigned __int64 v156; // r12
  int v157; // ebx
  __int64 v158; // rax
  __int64 v159; // r8
  unsigned int v160; // eax
  __int64 v161; // rdx
  __int64 v162; // rax
  __int64 v163; // r8
  unsigned int v164; // eax
  __int64 v165; // rax
  __int64 v166; // rdx
  __int64 v168; // [rsp+0h] [rbp-118h] BYREF
  int v169; // [rsp+2Ch] [rbp-ECh]
  int v170; // [rsp+30h] [rbp-E8h]
  int v171; // [rsp+34h] [rbp-E4h]
  int v172; // [rsp+38h] [rbp-E0h]
  int v173; // [rsp+3Ch] [rbp-DCh]
  unsigned __int64 v174; // [rsp+40h] [rbp-D8h]
  int v175; // [rsp+4Ch] [rbp-CCh]
  int v176; // [rsp+50h] [rbp-C8h]
  int v177; // [rsp+54h] [rbp-C4h]
  __int64 v178; // [rsp+58h] [rbp-C0h]
  unsigned __int64 v179; // [rsp+60h] [rbp-B8h]
  unsigned __int64 v180; // [rsp+68h] [rbp-B0h]
  unsigned __int64 v181; // [rsp+70h] [rbp-A8h]
  __int64 v182; // [rsp+78h] [rbp-A0h]
  int v183; // [rsp+80h] [rbp-98h]
  int v184; // [rsp+84h] [rbp-94h]
  __int64 v185; // [rsp+88h] [rbp-90h]
  int v186; // [rsp+94h] [rbp-84h]
  unsigned __int64 v187; // [rsp+98h] [rbp-80h]
  unsigned __int64 v188; // [rsp+A0h] [rbp-78h]
  unsigned __int64 v189; // [rsp+A8h] [rbp-70h]
  unsigned __int64 v190; // [rsp+B0h] [rbp-68h] BYREF
  unsigned __int64 v191; // [rsp+B8h] [rbp-60h] BYREF
  unsigned __int64 v192; // [rsp+C0h] [rbp-58h]
  _DWORD v193[2]; // [rsp+C8h] [rbp-50h] BYREF
  __int64 v194; // [rsp+D0h] [rbp-48h]

  v5 = a3;
  v187 = a3 - 1;
  if ( a3 <= 1 )
    RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(1, a3, &off_14001BBB0);
  v7 = a1;
  v8 = *(_DWORD *)(a2 + 4);
  if ( *(_DWORD *)(a2 + 12) <= v8 )
  {
    v19 = 2;
    do
    {
      if ( v5 == v19 )
      {
        v10 = v187;
        goto LABEL_28;
      }
      v20 = *(_DWORD *)(a2 + 8 * v19 + 4);
      v21 = v19 + 1;
      v13 = v20 <= *(_DWORD *)(a2 + 8 * v19++ - 4);
    }
    while ( v13 );
    v10 = v21 - 2;
    v22 = v21;
    do
    {
      if ( v5 == v22 )
        goto LABEL_28;
      if ( v5 <= v22 )
      {
        if ( v5 > v21 )
          v21 = v5;
        RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(v21, v5, &off_14001BBC8);
      }
      v23 = *(_DWORD *)(a2 + 8 * v22++ + 4);
      v13 = v23 < v20;
      v20 = v23;
    }
    while ( !v13 );
    v24 = v22 - 2;
    v16 = 0;
    while ( 1 )
    {
      if ( v23 < v8 )
        goto LABEL_190;
      if ( v5 - 2 == v24 )
        break;
      v25 = *(_DWORD *)(a2 + 8 * v24++ + 20);
      v13 = v25 <= v23;
      v23 = v25;
      if ( !v13 )
        goto LABEL_190;
    }
LABEL_28:
    if ( v10 >= v5 )
LABEL_40:
      RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(v10, v5, &off_14001BBF8);
    goto LABEL_29;
  }
  v9 = 2;
  v10 = 0;
  do
  {
    if ( v5 == v9 )
      goto LABEL_28;
    v11 = *(_DWORD *)(a2 + 8 * v9 + 4);
    v12 = v9 + 1;
    v13 = v11 < *(_DWORD *)(a2 + 8 * v9++ - 4);
  }
  while ( !v13 );
  v14 = v12;
  do
  {
    if ( v5 == v14 )
    {
      v10 = 0;
      if ( *(_DWORD *)(a2 + 8 * v5 - 4) < v8 )
        v10 = v187;
      if ( v10 >= v5 )
        goto LABEL_40;
LABEL_29:
      v16 = 0x21600000101LL;
      v26 = a5 - (__int64)(int)a4;
      if ( v26 > 2147483632 )
        goto LABEL_190;
      v27 = ((int)v26 + 15) >> 4;
      if ( (unsigned int)(v27 - 107374183) < 0xF3333333 )
        goto LABEL_190;
      v28 = *(int *)(a2 + 8 * v10 + 4);
      v29 = 14 * v27;
      v30 = 28;
      if ( v29 >= 0x1D )
        v30 = v29;
      RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore23clear_scans_and_reserve(&v191, v7, v30);
      if ( (_DWORD)v191 == 1 )
      {
        v31 = HIDWORD(v191);
        v32 = 257;
LABEL_189:
        v16 = v32 | (v31 << 32);
        goto LABEL_190;
      }
      v33 = (unsigned __int64)(v28 + 15) >> 4;
      v34 = v192;
      v190 = v192;
      v35 = RNvMs5_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11append_scan(
              v192,
              0x80000000LL,
              (unsigned int)v33,
              4,
              0);
      v32 = 257;
      if ( v35 )
      {
        v31 = v35;
        goto LABEL_188;
      }
      v36 = 1;
      v37 = -1;
      v170 = 0;
      v38 = 0;
      v171 = 0;
      v173 = 0;
      v172 = 0;
      v175 = 0;
      v169 = 0;
      v180 = v34;
      v39 = 0;
      v40 = v10;
      v185 = v5;
      v41 = v33;
      v42 = 0;
      v177 = 0;
LABEL_42:
      v182 = v36;
      v178 = v37;
      while ( 1 )
      {
        v43 = HIDWORD(v42);
        v179 = v41;
        if ( HIDWORD(v42) )
        {
          v31 = v185;
          v176 = v38;
          v44 = HIDWORD(v39);
          if ( HIDWORD(v39) )
            goto LABEL_45;
        }
        else
        {
          v31 = v185;
          if ( v185 <= 0 )
            goto LABEL_183;
          v31 = v185 + 1;
          v47 = v10;
          while ( 1 )
          {
            if ( v37 < 0 )
            {
              v10 = v47 - 1;
              if ( !v47 )
                v10 = v187;
              if ( v10 >= v5 )
LABEL_201:
                RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(v10, v5, &off_14001BC10);
            }
            else
            {
              v10 = v47 + 1;
              if ( v47 + 1 >= v5 )
                v10 = 0;
              if ( v10 >= v5 )
                goto LABEL_201;
            }
            v48 = *(int *)(a2 + 8 * v10 + 4);
            v43 = (unsigned int)((unsigned __int64)(v48 + 15) >> 4) - (unsigned int)v41;
            if ( (int)(((unsigned __int64)(v48 + 15) >> 4) - v41) > 0 )
              break;
            --v31;
            v47 = v10;
            if ( (unsigned __int64)v31 < 2 )
              goto LABEL_183;
          }
          if ( v47 >= v5 )
LABEL_204:
            RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(v47, v5, &off_14001BC28);
          v49 = *(_DWORD *)(a2 + 8 * v47);
          v50 = *(_DWORD *)(a2 + 8 * v47 + 4);
          v51 = v48 - v50;
          v52 = *(_DWORD *)(a2 + 8 * v10) - v49;
          if ( v52 < 0 )
          {
            v54 = v49 - *(_DWORD *)(a2 + 8 * v10);
            if ( v51 <= v54 )
            {
              if ( (_DWORD)v48 == v50 )
                goto LABEL_211;
              v174 = v40;
              if ( v51 == -1 )
              {
                v40 = (unsigned int)-v52;
                if ( __OFSUB__(-v52, 1) )
                  goto LABEL_210;
              }
              v53 = v52 / v51;
              if ( v54 % v51 <= 0 )
              {
                v171 = v54 % v51;
              }
              else
              {
                --v53;
                v171 = v51 - v54 % v51;
              }
              v40 = v174;
            }
            else
            {
              v171 = v51 + v52;
              v53 = -1;
            }
          }
          else
          {
            v171 = *(_DWORD *)(a2 + 8 * v10) - v49;
            if ( v52 >= v51 )
            {
              if ( (_DWORD)v48 == v50 )
                goto LABEL_208;
              v53 = v171 / v51;
              v171 %= v51;
            }
            else
            {
              v53 = 0;
            }
          }
          v55 = -1;
          v56 = v50 & 0xF;
          if ( v56 )
          {
            if ( v56 == 15 )
              goto LABEL_83;
            v188 = v5;
            v57 = v53;
            v174 = v40;
            v185 = v31;
            v58 = 16 - v56;
            v59 = (16 - v56) & 0xFFFFFFFE;
            do
            {
              v60 = 0;
              v66 = v171 + v55 < 0;
              v61 = v171 + v55;
              v62 = !v66;
              v63 = v51;
              if ( v66 )
                v63 = 0;
              v64 = v61 - v63;
              v65 = 0;
              v66 = v171 + v64 < 0;
              v67 = v171 + v64;
              v68 = v51;
              if ( v66 )
                v68 = 0;
              v55 = v67 - v68;
              LOBYTE(v60) = v62;
              LOBYTE(v65) = !v66;
              v49 += v60 + v57 + v57 + v65;
              v59 -= 2;
            }
            while ( v59 );
            v69 = (v58 & 1) == 0;
            v31 = v185;
            v40 = v174;
            v53 = v57;
            v5 = v188;
            if ( !v69 )
            {
LABEL_83:
              v70 = v53 + v49;
              v71 = 0;
              v72 = v171 + v55 < 0;
              v73 = v171 + v55;
              v74 = v40;
              v75 = 0;
              if ( !v72 )
                v75 = v51;
              LOBYTE(v71) = !v72;
              v55 = v73 - v75;
              v40 = v74;
              v49 = v70 + v71;
            }
          }
          v177 = v53;
          v31 -= 2;
          v42 = (v43 << 32) | (unsigned int)v51;
          v76 = v51 * (v49 | 0xFFFFFFF0);
          v77 = v49 + 15;
          if ( (v49 & 0xF) == 0 )
            v76 = v49 & 0xF;
          v78 = v76;
          if ( (v49 & 0xF) == 0 )
            v77 = v49;
          v170 = v77 >> 4;
          v36 = v182;
          v37 = v178;
          v41 = v179;
          v176 = (v55 + v78) >> 4;
          v44 = HIDWORD(v39);
          if ( HIDWORD(v39) )
          {
LABEL_45:
            v45 = (unsigned int)v39;
            v46 = v44;
            goto LABEL_133;
          }
        }
        if ( v31 <= 0 )
        {
LABEL_183:
          v162 = RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore13last_scan_mut(v180, v40, v43);
          a4 = *(_QWORD *)(v162 + 16);
          if ( v7 >= a4 )
            goto LABEL_203;
          if ( *(_DWORD *)(*(_QWORD *)(v162 + 8) + 4 * v7) )
          {
            v164 = RNvMs5_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11append_scan(
                     v180,
                     v179,
                     0x7FFFFFFF,
                     4,
                     0);
            v31 = v164;
            v32 = 256 - ((v164 == 0) - 1LL);
          }
          else
          {
            v165 = RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore13last_scan_mut(v180, v179, v163);
            v117 = v166 + 2;
            v118 = *(_QWORD *)(v165 + 16);
            if ( v166 + 2 >= v118 )
LABEL_206:
              RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
                v117,
                v118,
                &anon_01189c164b0c425bf67614ee34d1a89c_16_llvm_7541658972310832757);
            *(_DWORD *)(*(_QWORD *)(v165 + 8) + 4 * v166 + 8) = 0x7FFFFFFF;
            v32 = 256;
          }
          goto LABEL_188;
        }
        ++v31;
        v47 = v40;
        while ( 1 )
        {
          if ( v36 < 0 )
          {
            v40 = v47 - 1;
            if ( !v47 )
              v40 = v187;
            if ( v40 >= v5 )
            {
LABEL_200:
              v10 = v40;
              goto LABEL_201;
            }
          }
          else
          {
            v40 = v47 + 1;
            if ( v47 + 1 >= v5 )
              v40 = 0;
            if ( v40 >= v5 )
              goto LABEL_200;
          }
          v79 = *(int *)(a2 + 8 * v40 + 4);
          v46 = ((unsigned __int64)(v79 + 15) >> 4) - v41;
          if ( v46 > 0 )
            break;
          --v31;
          v47 = v40;
          if ( (unsigned __int64)v31 < 2 )
            goto LABEL_183;
        }
        if ( v47 >= v5 )
          goto LABEL_204;
        v80 = *(_DWORD *)(a2 + 8 * v47);
        v81 = *(_DWORD *)(a2 + 8 * v47 + 4);
        v82 = v79 - v81;
        v83 = *(_DWORD *)(a2 + 8 * v40) - v80;
        if ( v83 < 0 )
        {
          v84 = v80 - *(_DWORD *)(a2 + 8 * v40);
          if ( v82 <= v84 )
          {
            v169 = *(_DWORD *)(a2 + 8 * v40) - v80;
            if ( (_DWORD)v79 == v81 )
LABEL_211:
              RNvNtNtCs9MWeMO1rkJG_4core9panicking11panic_const23panic_const_div_by_zero(&off_14001BC58, v40);
            v174 = v40;
            if ( v82 == -1 && __OFSUB__(-v169, 1) )
LABEL_210:
              RNvNtNtCs9MWeMO1rkJG_4core9panicking11panic_const24panic_const_div_overflow(&off_14001BC58, v40);
            if ( v84 % v82 <= 0 )
            {
              v172 = v169 / v82;
              v169 = v84 % v82;
            }
            else
            {
              v172 = v169 / v82 - 1;
              v169 = v82 - v84 % v82;
            }
            v40 = v174;
          }
          else
          {
            v169 = v82 + v83;
            v172 = -1;
          }
        }
        else
        {
          v172 = 0;
          v169 = v83;
          if ( v83 >= v82 )
          {
            if ( (_DWORD)v79 == v81 )
LABEL_208:
              RNvNtNtCs9MWeMO1rkJG_4core9panicking11panic_const23panic_const_div_by_zero(&off_14001BC40, v40);
            v172 = v169 / v82;
            v169 %= v82;
          }
        }
        v85 = -1;
        v86 = v81 & 0xF;
        if ( v86 )
        {
          if ( v86 == 15 )
            goto LABEL_127;
          v181 = v42;
          v174 = v40;
          v185 = v31;
          v87 = 16 - v86;
          v88 = (16 - v86) & 0xFFFFFFFE;
          do
          {
            v89 = 0;
            v66 = v169 + v85 < 0;
            v90 = v169 + v85;
            v91 = !v66;
            v92 = v82;
            if ( v66 )
              v92 = 0;
            v93 = v90 - v92;
            v94 = 0;
            v95 = v169 + v93 < 0;
            v96 = v169 + v93;
            v97 = v82;
            if ( v95 )
              v97 = 0;
            v85 = v96 - v97;
            LOBYTE(v89) = v91;
            LOBYTE(v94) = !v95;
            v80 += v89 + v172 + v172 + v94;
            v88 -= 2;
          }
          while ( v88 );
          v31 = v185;
          v40 = v174;
          LODWORD(v42) = v181;
          if ( (v87 & 1) != 0 )
          {
LABEL_127:
            v98 = v172 + v80;
            v99 = 0;
            v100 = v169 + v85 < 0;
            v101 = v169 + v85;
            v102 = v40;
            v103 = 0;
            if ( !v100 )
              v103 = v82;
            LOBYTE(v99) = !v100;
            v85 = v101 - v103;
            v40 = v102;
            v80 = v98 + v99;
          }
        }
        v31 -= 2;
        v104 = v82 * (v80 | 0xFFFFFFF0);
        v105 = v80 + 15;
        if ( (v80 & 0xF) == 0 )
        {
          v104 = v80 & 0xF;
          v105 = v80;
        }
        v45 = (unsigned int)v82;
        v173 = v105 >> 4;
        v175 = (v85 + v104) >> 4;
        v36 = v182;
        v37 = v178;
        v41 = v179;
LABEL_133:
        v106 = v43;
        if ( v46 < (int)v43 )
          v106 = v46;
        v42 = ((unsigned __int64)(unsigned int)(v43 - v106) << 32) | (unsigned int)v42;
        v183 = v106;
        v39 = v45 | ((unsigned __int64)(unsigned int)(v46 - v106) << 32);
        v107 = v169;
        v185 = v31;
        if ( v169 | v171 | v177 | v172 )
        {
          v188 = v5;
          v181 = v42;
          v38 = v176;
          v123 = v173;
          v124 = v170;
          while ( 1 )
          {
            v169 = v107;
            v174 = v40;
            v182 = v36;
            v179 = v39;
            v178 = v37;
            v189 = v41;
            v173 = v123;
            if ( v123 - v124 <= 0 )
            {
              v136 = v181;
              v135 = v172;
              v137 = v124;
              v138 = v171;
              v139 = v177;
              v140 = v178;
              while ( 1 )
              {
                v134 = v174;
                v133 = v182;
                v132 = v179;
                v131 = v169;
                v184 = v175;
                v170 = v135;
                v141 = v173;
                v174 = v10;
                v182 = v140;
                v169 = v138;
                v175 = v38;
                v135 = v139;
                v142 = v137;
                v137 = v173;
                v173 = v142;
                v143 = v142 - v141;
                if ( !v143 )
                  break;
                v179 = v136;
                v124 = v137;
                v139 = v170;
                v38 = v184;
                v138 = v131;
                v136 = v132;
                v140 = v133;
                v10 = v134;
                if ( v143 > 0 )
                  goto LABEL_167;
              }
              v186 = v131;
              v178 = v179;
              v179 = v133;
              v156 = v134;
              v157 = v135;
              v158 = RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore13last_scan_mut(v180, v134, v133);
              a4 = *(_QWORD *)(v158 + 16);
              if ( v7 >= a4 )
                goto LABEL_203;
              v159 = (unsigned int)(v189 + 1);
              if ( *(_DWORD *)(*(_QWORD *)(v158 + 8) + 4 * v7) )
              {
                v160 = RNvMs5_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11append_scan(
                         v180,
                         (unsigned int)v189,
                         v159,
                         4,
                         0);
                v41 = (unsigned int)(v189 + 1);
                v31 = v160;
                v125 = v173;
                v177 = v157;
                v176 = v175;
                v171 = v169;
                v181 = v136;
                v37 = v182;
                v10 = v174;
                v172 = v170;
                v175 = v184;
                v107 = v186;
                v39 = v178;
                v36 = v179;
                v40 = v156;
                if ( v160 )
                  goto LABEL_193;
                goto LABEL_157;
              }
              v152 = RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore13last_scan_mut(v180, v7, v159);
              v154 = v161 + 2;
              v155 = *(_QWORD *)(v152 + 16);
              if ( v154 >= v155 )
LABEL_209:
                RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
                  v154,
                  v155,
                  &anon_01189c164b0c425bf67614ee34d1a89c_16_llvm_7541658972310832757);
              v125 = v173;
              v177 = v157;
              v176 = v175;
              v171 = v169;
              v181 = v136;
              v37 = v182;
              v10 = v174;
              v173 = v137;
              v172 = v170;
              v175 = v184;
              v107 = v186;
              v39 = v178;
              v36 = v179;
              v174 = v156;
              v41 = (unsigned int)(v189 + 1);
            }
            else
            {
              v170 = v177;
              v184 = v38;
              v131 = v171;
              v132 = v181;
              v133 = v178;
              v134 = v10;
              v135 = v172;
LABEL_167:
              v172 = v135;
              v10 = v134;
              v178 = v133;
              v144 = v132;
              v171 = v131;
              v176 = v184;
              v177 = v170;
              v170 = v124;
              v145 = RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore13last_scan_mut(v180, v134, v133);
              v147 = v146;
              v148 = *(_QWORD *)(v145 + 16);
              if ( v147 >= v148 )
                RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
                  v147,
                  v148,
                  &anon_01189c164b0c425bf67614ee34d1a89c_1_llvm_7541658972310832757);
              v149 = (unsigned int)(v189 + 1);
              v150 = *(_QWORD *)(v145 + 8);
              v69 = *(_DWORD *)(v150 + 4 * v147) == 2;
              v39 = v179;
              v137 = v173;
              v181 = v144;
              if ( !v69 )
                goto LABEL_156;
              v151 = v147 + 3;
              if ( v147 + 3 >= v148 )
                goto LABEL_207;
              if ( *(_DWORD *)(v150 + 4 * v147 + 12) != v170 )
                goto LABEL_156;
              v151 = v147 + 4;
              if ( v147 + 4 >= v148 )
LABEL_207:
                RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
                  v151,
                  v148,
                  &anon_01189c164b0c425bf67614ee34d1a89c_13_llvm_7541658972310832757);
              if ( *(_DWORD *)(v150 + 4 * v147 + 16) != v173 )
              {
LABEL_156:
                v125 = v170;
                v191 = __PAIR64__(v173, v170);
                v120 = RNvMs5_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11append_scan(
                         v180,
                         (unsigned int)v189,
                         v149,
                         &v191,
                         2);
                v41 = (unsigned int)(v189 + 1);
                v36 = v182;
                v40 = v174;
                v37 = v178;
                v107 = v169;
                if ( v120 )
                  goto LABEL_192;
                goto LABEL_157;
              }
              v152 = RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore13last_scan_mut(v180, v148, v149);
              v154 = v153 + 2;
              v155 = *(_QWORD *)(v152 + 16);
              if ( v154 >= v155 )
                goto LABEL_209;
              v36 = v182;
              v37 = v178;
              v107 = v169;
              v41 = (unsigned int)(v189 + 1);
              v125 = v170;
            }
            *(_DWORD *)(*(_QWORD *)(v152 + 8) + 4 * v154) = v41;
            v40 = v174;
            v137 = v173;
LABEL_157:
            v126 = v172 + v137;
            v127 = 0;
            if ( v107 + v175 >= 0 )
              v127 = v39;
            v123 = v126 + (v107 + v175 >= 0);
            v175 = v107 + v175 - v127;
            v128 = v177 + v125;
            v129 = 0;
            v130 = v181;
            if ( v171 + v176 < 0 )
              v130 = 0;
            LOBYTE(v129) = v171 + v176 >= 0;
            v124 = v128 + v129;
            v38 = v171 + v176 - v130;
            if ( !--v183 )
            {
              v170 = v124;
              v173 = v123;
              v169 = v107;
              v42 = v181;
              v5 = v188;
              goto LABEL_42;
            }
          }
        }
        v174 = v40;
        v108 = v173;
        if ( v170 == v173 )
        {
          v109 = RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore13last_scan_mut(v180, v40, (unsigned int)v169);
          a4 = *(_QWORD *)(v109 + 16);
          if ( v7 >= a4 )
            goto LABEL_203;
          if ( *(_DWORD *)(*(_QWORD *)(v109 + 8) + 4 * v7) )
          {
            v31 = (unsigned int)RNvMs5_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11append_scan(
                                  v180,
                                  v179,
                                  (unsigned int)(v179 + v183),
                                  4,
                                  0);
            v173 = v170;
            v41 = (unsigned int)(v179 + v183);
            v36 = v182;
            v40 = v174;
            v37 = v178;
            v38 = v176;
            if ( (_DWORD)v31 )
            {
LABEL_193:
              v32 = 257;
              goto LABEL_188;
            }
          }
          else
          {
            v121 = RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore13last_scan_mut(v180, v179, v110);
            v117 = v122 + 2;
            v118 = *(_QWORD *)(v121 + 16);
            if ( v122 + 2 >= v118 )
              goto LABEL_206;
            v41 = (unsigned int)(v183 + v179);
            *(_DWORD *)(*(_QWORD *)(v121 + 8) + 4 * v122 + 8) = v41;
            v173 = v170;
            v36 = v182;
            v40 = v174;
            v37 = v178;
            v38 = v176;
          }
        }
        else
        {
          v181 = v42;
          v111 = v173;
          if ( v170 < v173 )
            v111 = v170;
          if ( v170 > v173 )
            v108 = v170;
          v112 = RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore13last_scan_mut(v180, v40, (unsigned int)v169);
          v191 = v112;
          v192 = v7;
          a4 = *(_QWORD *)(v112 + 16);
          if ( v7 >= a4 )
            goto LABEL_203;
          if ( *(_DWORD *)(*(_QWORD *)(v112 + 8) + 4 * v7) == 2
            && (unsigned int)RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalRINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E6x_wallCs7vXzV21FY6F_8gdi_rust(
                               &v191,
                               0) == v111
            && (unsigned int)RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalRINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E6x_wallCs7vXzV21FY6F_8gdi_rust(
                               &v191,
                               1) == v108 )
          {
            v115 = RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore13last_scan_mut(v180, v113, v114);
            v117 = v116 + 2;
            v118 = *(_QWORD *)(v115 + 16);
            if ( v116 + 2 >= v118 )
              goto LABEL_206;
            v119 = v179 + v183;
            *(_DWORD *)(*(_QWORD *)(v115 + 8) + 4 * v116 + 8) = v179 + v183;
            v37 = v178;
            v42 = v181;
          }
          else
          {
            v193[0] = v111;
            v193[1] = v108;
            v120 = RNvMs5_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11append_scan(
                     v180,
                     v179,
                     (unsigned int)(v179 + v183),
                     v193,
                     2);
            v119 = v179 + v183;
            v37 = v178;
            v42 = v181;
            if ( v120 )
            {
LABEL_192:
              v31 = v120;
              v32 = 257;
LABEL_188:
              RNvXCsdcpJtfrLhSH_7rgncoreNtB2_11RegionGuardNtNtNtCs9MWeMO1rkJG_4core3ops4drop4Drop4drop(&v190);
              goto LABEL_189;
            }
          }
          v41 = v119;
          v36 = v182;
          v40 = v174;
          v38 = v176;
        }
      }
    }
    if ( v5 <= v14 )
    {
      if ( v5 > v12 )
        v12 = v5;
      RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(v12, v5, &off_14001BBE0);
    }
    v15 = *(_DWORD *)(a2 + 8 * v14++ + 4);
    v13 = v15 <= v11;
    v11 = v15;
  }
  while ( v13 );
  v10 = v14 - 2;
  v16 = 0;
  v17 = v10;
  do
  {
    if ( v15 > v8 )
      break;
    if ( v5 - 2 == v17 )
      goto LABEL_28;
    v18 = *(_DWORD *)(a2 + 8 * v17++ + 20);
    v13 = v18 < v15;
    v15 = v18;
  }
  while ( !v13 );
LABEL_190:
  if ( _security_cookie != ((unsigned __int64)&v168 ^ v194) )
LABEL_203:
    RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
      v7,
      a4,
      &anon_01189c164b0c425bf67614ee34d1a89c_1_llvm_7541658972310832757);
  return v16;
}

```

## disassembly

```asm
0x140011120  push    r15
0x140011122  push    r14
0x140011124  push    r13
0x140011126  push    r12
0x140011128  push    rsi
0x140011129  push    rdi
0x14001112a  push    rbp
0x14001112b  push    rbx
0x14001112c  sub     rsp, 0D8h
0x140011133  mov     rsi, r8
0x140011136  mov     rax, cs:__security_cookie
0x14001113d  xor     rax, rsp
0x140011140  mov     [rsp+118h+var_48], rax
0x140011148  mov     rax, r8
0x14001114b  sub     rax, 1
0x14001114f  mov     [rsp+118h+var_80], rax
0x140011157  jbe     loc_14001203A
0x14001115d  mov     rdi, rdx
0x140011160  mov     rdx, rcx
0x140011163  mov     eax, [rdi+4]
0x140011166  cmp     [rdi+0Ch], eax
0x140011169  jle     loc_1400111F7
0x14001116f  mov     r8d, 2
0x140011175  xor     ebx, ebx
0x140011177  nop     word ptr [rax+rax+00000000h]
0x140011180  cmp     rsi, r8
0x140011183  jz      loc_14001127B
0x140011189  mov     r10d, [rdi+r8*8+4]
0x14001118e  lea     rcx, [r8+1]
0x140011192  cmp     r10d, [rdi+r8*8-4]
0x140011197  mov     r8, rcx
0x14001119a  jge     short loc_140011180
0x14001119c  mov     rbx, rcx
0x14001119f  nop
0x1400111a0  cmp     rsi, rbx
0x1400111a3  jz      loc_14001134E
0x1400111a9  jbe     loc_140011FF9
0x1400111af  mov     r8d, [rdi+rbx*8+4]
0x1400111b4  inc     rbx
0x1400111b7  cmp     r8d, r10d
0x1400111ba  mov     r10d, r8d
0x1400111bd  jle     short loc_1400111A0
0x1400111bf  lea     rcx, [rsi-2]
0x1400111c3  add     rbx, 0FFFFFFFFFFFFFFFEh
0x1400111c7  xor     r15d, r15d
0x1400111ca  mov     r10, rbx
0x1400111cd  nop     dword ptr [rax]
0x1400111d0  cmp     r8d, eax
0x1400111d3  jg      loc_140011FB8
0x1400111d9  cmp     rcx, r10
0x1400111dc  jz      loc_14001127B
0x1400111e2  mov     r11d, [rdi+r10*8+14h]
0x1400111e7  inc     r10
0x1400111ea  cmp     r11d, r8d
0x1400111ed  mov     r8d, r11d
0x1400111f0  jge     short loc_1400111D0
0x1400111f2  jmp     loc_140011FB8
0x1400111f7  mov     r8d, 2
0x1400111fd  nop     dword ptr [rax]
0x140011200  cmp     rsi, r8
0x140011203  jz      short loc_140011273
0x140011205  mov     r11d, [rdi+r8*8+4]
0x14001120a  lea     rcx, [r8+1]
0x14001120e  cmp     r11d, [rdi+r8*8-4]
0x140011213  mov     r8, rcx
0x140011216  jle     short loc_140011200
0x140011218  lea     rbx, [rcx-2]
0x14001121c  mov     r8, rcx
0x14001121f  nop
0x140011220  cmp     rsi, r8
0x140011223  jz      short loc_14001127B
0x140011225  jbe     loc_14001200F
0x14001122b  mov     r10d, [rdi+r8*8+4]
0x140011230  inc     r8
0x140011233  cmp     r10d, r11d
0x140011236  mov     r11d, r10d
0x140011239  jge     short loc_140011220
0x14001123b  lea     rcx, [rsi-2]
0x14001123f  add     r8, 0FFFFFFFFFFFFFFFEh
0x140011243  xor     r15d, r15d
0x140011246  nop     word ptr [rax+rax+00000000h]
0x140011250  cmp     r10d, eax
0x140011253  jl      loc_140011FB8
0x140011259  cmp     rcx, r8
0x14001125c  jz      short loc_14001127B
0x14001125e  mov     r11d, [rdi+r8*8+14h]
0x140011263  inc     r8
0x140011266  cmp     r11d, r10d
0x140011269  mov     r10d, r11d
0x14001126c  jle     short loc_140011250
0x14001126e  jmp     loc_140011FB8
0x140011273  mov     rbx, [rsp+118h+var_80]
0x14001127b  cmp     rbx, rsi
0x14001127e  jnb     loc_140011366
0x140011284  mov     r15, 21600000101h
0x14001128e  movsxd  rax, [rsp+118h+arg_20]
0x140011296  movsxd  rcx, r9d
0x140011299  sub     rax, rcx
0x14001129c  cmp     rax, 7FFFFFF0h
0x1400112a2  jg      loc_140011FB8
0x1400112a8  add     eax, 0Fh
0x1400112ab  sar     eax, 4
0x1400112ae  lea     ecx, [rax-6666667h]
0x1400112b4  cmp     ecx, 0F3333333h
0x1400112ba  jb      loc_140011FB8
0x1400112c0  movsxd  rbp, dword ptr [rdi+rbx*8+4]
0x1400112c5  lea     ecx, [rax+rax]
0x1400112c8  shl     eax, 4
0x1400112cb  sub     eax, ecx
0x1400112cd  cmp     eax, 1Dh
0x1400112d0  mov     ecx, 1Ch
0x1400112d5  cmovnb  ecx, eax
0x1400112d8  movsxd  r8, ecx
0x1400112db  lea     rcx, [rsp+118h+var_60]
0x1400112e3  call    _RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore23clear_scans_and_reserve
0x1400112e8  cmp     dword ptr [rsp+118h+var_60], 1
0x1400112f0  jnz     short loc_140011305
0x1400112f2  mov     r15d, dword ptr [rsp+118h+var_60+4]
0x1400112fa  mov     r14d, 101h
0x140011300  jmp     loc_140011FB1
0x140011305  add     rbp, 0Fh
0x140011309  shr     rbp, 4
0x14001130d  mov     r13, [rsp+118h+var_58]
0x140011315  mov     [rsp+118h+var_68], r13
0x14001131d  mov     [rsp+118h+var_F8], 0
0x140011326  mov     r9d, 4
0x14001132c  mov     rcx, r13
0x14001132f  mov     edx, 80000000h
0x140011334  mov     r8d, ebp
0x140011337  call    _RNvMs5_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11append_scan
0x14001133c  mov     r14d, 101h
0x140011342  test    eax, eax
0x140011344  jz      short loc_140011378
0x140011346  mov     r15d, eax
0x140011349  jmp     loc_140011FA4
0x14001134e  xor     ebx, ebx
0x140011350  cmp     [rdi+rsi*8-4], eax
0x140011354  cmovl   rbx, [rsp+118h+var_80]
0x14001135d  cmp     rbx, rsi
0x140011360  jb      loc_140011284
0x140011366  lea     r8, off_14001BBF8; "gdi_rust\\src\\region\\from_path.rs"
0x14001136d  mov     rcx, rbx
0x140011370  mov     rdx, rsi
0x140011373  call    _RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check
0x140011378  mov     r10d, 1
0x14001137e  mov     r9, 0FFFFFFFFFFFFFFFFh
0x140011385  xor     r14d, r14d
0x140011388  mov     [rsp+118h+var_E8], 0
0x140011390  xor     ecx, ecx
0x140011392  mov     [rsp+118h+var_E4], 0
0x14001139a  mov     [rsp+118h+var_DC], 0
0x1400113a2  mov     [rsp+118h+var_E0], 0
0x1400113aa  mov     [rsp+118h+var_CC], 0
0x1400113b2  mov     [rsp+118h+var_EC], 0
0x1400113ba  mov     [rsp+118h+var_B0], r13
0x1400113bf  xor     r13d, r13d
0x1400113c2  mov     rdx, rbx
0x1400113c5  mov     [rsp+118h+var_90], rsi
0x1400113cd  mov     r11, rbp
0x1400113d0  xor     ebp, ebp
0x1400113d2  mov     [rsp+118h+var_C4], 0
0x1400113da  mov     [rsp+118h+var_A0], r10
0x1400113df  mov     [rsp+118h+var_C0], r9
0x1400113e4  mov     r8, rbp
0x1400113e7  shr     r8, 20h
0x1400113eb  mov     [rsp+118h+var_B8], r11
0x1400113f0  jz      short loc_140011416
0x1400113f2  mov     r15, [rsp+118h+var_90]
0x1400113fa  mov     [rsp+118h+var_C8], ecx
0x1400113fe  mov     rax, r13
0x140011401  shr     rax, 20h
0x140011405  jz      loc_140011676
0x14001140b  mov     ecx, r13d
0x14001140e  mov     r13d, eax
0x140011411  jmp     loc_1400118D6
0x140011416  mov     r15, [rsp+118h+var_90]
0x14001141e  test    r15, r15
0x140011421  jle     loc_140011F21
0x140011427  inc     r15
0x14001142a  mov     rcx, rbx
0x14001142d  nop     dword ptr [rax]
0x140011430  test    r9, r9
0x140011433  js      short loc_140011450
0x140011435  lea     rbx, [rcx+1]
0x140011439  cmp     rbx, rsi
0x14001143c  cmovnb  rbx, r14
0x140011440  cmp     rbx, rsi
0x140011443  jb      short loc_140011469
0x140011445  jmp     loc_140012028
0x140011450  mov     rbx, rcx
0x140011453  sub     rbx, 1
0x140011457  cmovb   rbx, [rsp+118h+var_80]
0x140011460  cmp     rbx, rsi
0x140011463  jnb     loc_140012028
0x140011469  movsxd  rbp, dword ptr [rdi+rbx*8+4]
0x14001146e  lea     r8, [rbp+0Fh]
0x140011472  shr     r8, 4
0x140011476  sub     r8d, r11d
0x140011479  test    r8d, r8d
0x14001147c  jg      short loc_14001148F
0x14001147e  dec     r15
0x140011481  mov     rcx, rbx
0x140011484  cmp     r15, 2
0x140011488  jnb     short loc_140011430
0x14001148a  jmp     loc_140011F21
0x14001148f  cmp     rcx, rsi
0x140011492  jnb     loc_140012070
0x140011498  mov     r9d, [rdi+rcx*8]
0x14001149c  mov     r11d, [rdi+rcx*8+4]
0x1400114a1  mov     r10d, ebp
0x1400114a4  sub     r10d, r11d
0x1400114a7  mov     eax, [rdi+rbx*8]
0x1400114aa  sub     eax, r9d
0x1400114ad  js      short loc_1400114BC
0x1400114af  mov     [rsp+118h+var_E4], eax
0x1400114b3  cmp     eax, r10d
0x1400114b6  jge     short loc_1400114D3
0x1400114b8  xor     ebp, ebp
0x1400114ba  jmp     short loc_140011536
0x1400114bc  mov     ecx, eax
0x1400114be  neg     ecx
0x1400114c0  cmp     r10d, ecx
0x1400114c3  jle     short loc_1400114F2
0x1400114c5  add     eax, r10d
0x1400114c8  mov     [rsp+118h+var_E4], eax
0x1400114cc  mov     ebp, 0FFFFFFFFh
0x1400114d1  jmp     short loc_140011536
0x1400114d3  cmp     ebp, r11d
0x1400114d6  jz      loc_1400120A9
0x1400114dc  mov     rcx, rdx
0x1400114df  mov     eax, [rsp+118h+var_E4]
0x1400114e3  cdq
0x1400114e4  idiv    r10d
0x1400114e7  mov     ebp, eax
0x1400114e9  mov     [rsp+118h+var_E4], edx
0x1400114ed  mov     rdx, rcx
0x1400114f0  jmp     short loc_140011536
0x1400114f2  cmp     ebp, r11d
0x1400114f5  jz      loc_1400120D3
0x1400114fb  mov     [rsp+118h+var_D8], rdx
0x140011500  cmp     r10d, 0FFFFFFFFh
0x140011504  jnz     short loc_140011510
0x140011506  mov     edx, eax
0x140011508  neg     edx
0x14001150a  jo      loc_1400120C7
0x140011510  cdq
0x140011511  idiv    r10d
0x140011514  mov     ebp, eax
0x140011516  mov     eax, ecx
0x140011518  cdq
0x140011519  idiv    r10d
0x14001151c  test    edx, edx
0x14001151e  jle     short loc_14001152D
0x140011520  dec     ebp
0x140011522  mov     eax, r10d
0x140011525  sub     eax, edx
0x140011527  mov     [rsp+118h+var_E4], eax
0x14001152b  jmp     short loc_140011531
0x14001152d  mov     [rsp+118h+var_E4], edx
0x140011531  mov     rdx, [rsp+118h+var_D8]
0x140011536  mov     eax, 0FFFFFFFFh
0x14001153b  and     r11d, 0Fh
0x14001153f  jz      loc_140011611
0x140011545  cmp     r11d, 0Fh
0x140011549  jz      loc_1400115EE
0x14001154f  mov     [rsp+118h+var_78], rsi
0x140011557  mov     ecx, ebp
0x140011559  mov     [rsp+118h+var_D8], rdx
0x14001155e  mov     [rsp+118h+var_90], r15
0x140011566  mov     edx, 10h
0x14001156b  sub     edx, r11d
0x14001156e  mov     esi, edx
0x140011570  and     edx, 0FFFFFFFEh
0x140011573  jmp     short loc_1400115A0
0x140011580  sub     eax, r12d
0x140011583  add     r9d, ecx
0x140011586  mov     r11b, bpl
0x140011589  add     r9d, ecx
0x14001158c  mov     ebp, r9d
0x14001158f  add     ebp, r11d
0x140011592  mov     r14b, r15b
0x140011595  mov     r9d, r14d
0x140011598  add     r9d, ebp
0x14001159b  add     edx, 0FFFFFFFEh
0x14001159e  jz      short loc_1400115CB
0x1400115a0  xor     r11d, r11d
0x1400115a3  add     eax, [rsp+118h+var_E4]
0x1400115a7  setns   bpl
0x1400115ab  mov     r14d, r10d
0x1400115ae  jns     short loc_1400115B3
0x1400115b0  xor     r14d, r14d
0x1400115b3  sub     eax, r14d
0x1400115b6  xor     r14d, r14d
0x1400115b9  add     eax, [rsp+118h+var_E4]
0x1400115bd  setns   r15b
0x1400115c1  mov     r12d, r10d
0x1400115c4  jns     short loc_140011580
0x1400115c6  xor     r12d, r12d
0x1400115c9  jmp     short loc_140011580
0x1400115cb  test    sil, 1
  ... truncated ...
```
