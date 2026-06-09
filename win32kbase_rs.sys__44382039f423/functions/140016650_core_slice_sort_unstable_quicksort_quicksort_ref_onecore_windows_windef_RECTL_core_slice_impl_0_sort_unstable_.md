# core::slice::sort::unstable::quicksort::quicksort_ref$_onecore_windows::windef::_RECTL__core::slice::impl$0::sort_unstable_by_key::closure_env$0_ref$_onecore_windows::windef::_RECTL__i32_rgncore::impl$1::subtract_complex::closure_env$0___

- ea: `0x140016650`
- end: `0x14001738b`
- name: `core::slice::sort::unstable::quicksort::quicksort_ref$_onecore_windows::windef::_RECTL__core::slice::impl$0::sort_unstable_by_key::closure_env$0_ref$_onecore_windows::windef::_RECTL__i32_rgncore::impl$1::subtract_complex::closure_env$0___`
- size: `3387`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400162d0`
- `0x140016650`

## callees

- `0x140016450`
- `0x140016590`
- `0x140016650`
- `0x140017a10`
- `0x140017b00`
- `0x1400187c0`

## pseudocode

```c
unsigned __int64 __fastcall core::slice::sort::unstable::quicksort::quicksort_ref__onecore_windows::windef::_RECTL__core::slice::impl_0::sort_unstable_by_key::closure_env_0_ref__onecore_windows::windef::_RECTL__i32_rgncore::impl_1::subtract_complex::closure_env_0___(
        _QWORD *a1,
        unsigned __int64 a2,
        _QWORD *a3,
        unsigned int a4)
{
  unsigned __int64 v4; // r12
  unsigned __int64 v6; // rbp
  unsigned __int64 v7; // rdx
  _QWORD *v8; // r15
  _QWORD *v9; // r8
  __int64 v10; // rax
  int v11; // ecx
  __int64 v12; // rdx
  __int64 v13; // r12
  __int64 v14; // r15
  __int64 v15; // rdx
  __int64 v16; // r13
  __int64 v17; // r9
  __int64 v18; // rbx
  __int64 v19; // r10
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rsi
  __int64 v23; // r14
  __int64 v24; // rax
  __int64 v25; // rbp
  __int64 v26; // r15
  __int64 v27; // r11
  __int64 v28; // r13
  __int64 v29; // r9
  bool v30; // cc
  __int64 v31; // rdx
  __int64 v32; // rbx
  __int64 v33; // rdi
  __int64 v34; // rax
  __int64 v35; // r10
  __int64 v36; // rdx
  __int64 v37; // rsi
  __int64 v38; // r11
  __int64 v39; // r9
  __int64 v40; // r12
  __int64 v41; // rcx
  __int64 v42; // rbp
  __int64 v43; // r9
  __int64 v44; // r14
  __int64 v45; // rsi
  __int64 v46; // r13
  __int64 v47; // rdi
  __int64 v48; // rax
  __int64 v49; // rcx
  __int64 v50; // r9
  __int64 v51; // rcx
  __int64 v52; // rdx
  __int64 v53; // r11
  __int64 v54; // r11
  __int64 v55; // rsi
  __int64 v56; // rdi
  __int64 v57; // r9
  __int64 v58; // rax
  __int64 v59; // rcx
  __int64 v60; // r11
  __int64 v61; // r11
  __int64 v62; // r9
  __int64 v63; // rax
  __int64 v64; // rcx
  __int64 v65; // rax
  int v66; // r9d
  __int64 v67; // rdx
  __int64 v68; // rcx
  __int64 v69; // rsi
  __int64 v70; // r9
  __int64 v71; // r14
  __int64 v72; // r10
  __int64 v73; // r11
  __int64 v74; // rax
  __int64 v75; // rdi
  __int64 v76; // rbx
  __int64 v77; // rdx
  __int64 v78; // r12
  __int64 v79; // rsi
  __int64 v80; // r14
  __int64 v81; // r13
  __int64 v82; // r15
  __int64 v83; // r9
  __int64 v84; // rbx
  __int64 v85; // rcx
  __int64 v86; // rax
  __int64 v87; // r11
  __int64 v88; // r10
  __int64 v89; // rsi
  __int64 v90; // rsi
  __int64 v91; // r9
  __int64 v92; // r11
  __int64 v93; // rcx
  __int64 v94; // rax
  __int64 v95; // rax
  bool v96; // zf
  char *v97; // rax
  __int64 v98; // rcx
  char *v99; // rdx
  _QWORD *v100; // r10
  __int64 v101; // rsi
  __int64 v102; // r9
  int v103; // r11d
  __int64 v104; // r10
  char *v107; // rax
  _QWORD *v108; // r8
  int v109; // ecx
  int v110; // edx
  bool v111; // r9
  int v112; // r10d
  char v113; // cl
  __int64 v114; // rax
  __int64 v115; // rcx
  __int64 v116; // rdx
  _QWORD *v117; // rax
  __int64 v118; // rcx
  unsigned __int64 v119; // r10
  _QWORD *v120; // r9
  int v121; // edx
  __int64 v122; // r8
  __int64 v123; // r11
  _BOOL8 v124; // rsi
  __int64 v125; // rsi
  __int64 v126; // r11
  _BOOL8 v127; // r8
  _QWORD *v128; // r10
  _QWORD *v129; // r11
  _QWORD *v130; // rax
  __int64 v131; // rcx
  unsigned __int64 v132; // r10
  _QWORD *v133; // rdx
  int v134; // r8d
  __int64 v135; // r9
  __int64 v136; // r11
  _BOOL8 v137; // rsi
  __int64 v138; // rsi
  __int64 v139; // r11
  _BOOL8 v140; // r9
  _QWORD *v141; // r10
  _QWORD *v142; // r11
  _QWORD *v143; // rsi
  __int64 v144; // rdx
  __int64 v145; // rdi
  _BOOL8 v146; // r9
  _BOOL8 v147; // rdx
  unsigned __int64 v148; // rdx
  _QWORD *v149; // rsi
  __int64 v150; // rax
  _QWORD *v151; // rdi
  _QWORD *v152; // rsi
  __int64 v153; // r9
  __int64 v154; // rdi
  _BOOL8 v155; // r8
  _BOOL8 v156; // r9
  unsigned __int64 v157; // r9
  __int64 v158; // rax
  unsigned __int64 result; // rax
  unsigned __int64 v160; // r11
  _QWORD *v161; // r8
  _QWORD *v162; // rdx
  __int64 v163; // r10
  _QWORD *v164; // r9
  __int64 v165; // rcx
  int v166; // esi
  __int64 v167; // rdi
  __int64 v168; // rbx
  bool v169; // sf
  bool v170; // of
  __int64 v171; // rax
  int v172; // esi
  int v173; // r14d
  BOOL v174; // ebx
  _QWORD *v175; // rdx
  _QWORD *v176; // r8
  bool v177; // al
  _QWORD *v178; // r11
  _BYTE v179[40]; // [rsp+0h] [rbp-1A8h] BYREF
  unsigned __int64 v180; // [rsp+28h] [rbp-180h]
  unsigned __int64 v181; // [rsp+30h] [rbp-178h]
  _QWORD *v182; // [rsp+38h] [rbp-170h]
  void *v183; // [rsp+40h] [rbp-168h]
  unsigned __int64 v184; // [rsp+48h] [rbp-160h]
  __int64 v185; // [rsp+50h] [rbp-158h]
  unsigned __int64 v186; // [rsp+58h] [rbp-150h]
  _QWORD Src[32]; // [rsp+60h] [rbp-148h] BYREF
  __int64 v188; // [rsp+160h] [rbp-48h]

  v4 = a2;
  if ( a2 >= 0x21 )
  {
    while ( 1 )
    {
      if ( !a4 )
      {
        if ( _security_cookie == ((unsigned __int64)v179 ^ v188) )
          return RINvNtNtNtNtCs9MWeMO1rkJG_4core5slice4sort8unstable8heapsort8heapsortRNtNtCscTDbrdTM4KX_15onecore_windows6windef6__RECTLNCINvMB8_SB15_20sort_unstable_by_keylNCNvMs_CsdcpJtfrLhSH_7rgncoreNtB2C_10RegionCore16subtract_complex0E0EB2C_(
                   a1,
                   v4);
LABEL_255:
        JUMPOUT(0x14001738ALL);
      }
      v107 = (char *)&a1[4 * (v4 >> 3)];
      v108 = &a1[7 * (v4 >> 3)];
      if ( v4 >= 0x40 )
      {
        --a4;
        v114 = core::slice::sort::shared::pivot::median3_rec_ref__onecore_windows::windef::_RECTL__core::slice::impl_0::sort_unstable_by_key::closure_env_0_ref__onecore_windows::windef::_RECTL__i32_rgncore::impl_1::subtract_complex::closure_env_0___(
                 a1,
                 &a1[4 * (v4 >> 3)],
                 v108)
             - (_QWORD)a1;
        if ( !a3 )
          goto LABEL_223;
      }
      else
      {
        v109 = *(_DWORD *)(*a1 + 4LL);
        v110 = *(_DWORD *)(*(_QWORD *)v107 + 4LL);
        v111 = v109 < v110;
        v112 = *(_DWORD *)(*v108 + 4LL);
        v113 = (v109 < v110) ^ (v109 < v112);
        if ( v111 != v110 < v112 )
          v107 = (char *)&a1[7 * (v4 >> 3)];
        if ( v113 )
          v107 = (char *)a1;
        --a4;
        v114 = v107 - (char *)a1;
        if ( !a3 )
        {
LABEL_223:
          v116 = *a1;
          v115 = *(_QWORD *)((char *)a1 + v114);
LABEL_224:
          *a1 = v115;
          *(_QWORD *)((char *)a1 + v114) = v116;
          v130 = a1 + 1;
          v131 = a1[1];
          v132 = (unsigned __int64)&a1[v4 - 1];
          v133 = a1 + 2;
          v134 = *(_DWORD *)(*a1 + 4LL);
          if ( (unsigned __int64)(a1 + 2) >= v132 )
          {
            v141 = a1 + 1;
            v135 = 0;
            v142 = &a1[v4];
            if ( v133 != v142 )
              goto LABEL_230;
          }
          else
          {
            v135 = 0;
            do
            {
              v136 = *v133;
              v137 = *(_DWORD *)(*v133 + 4LL) < v134;
              *(v133 - 1) = v130[v135];
              v130[v135] = v136;
              v138 = v135 + v137;
              v139 = v133[1];
              v140 = *(_DWORD *)(v139 + 4) < v134;
              *v133 = v130[v138];
              v130[v138] = v139;
              v135 = v138 + v140;
              v133 += 2;
            }
            while ( (unsigned __int64)v133 < v132 );
            v141 = v133 - 1;
            v142 = &a1[v4];
            if ( v133 == v142 )
              goto LABEL_231;
            do
            {
LABEL_230:
              v143 = v141;
              v141 = v133;
              v144 = v135;
              v145 = *v141;
              v146 = *(_DWORD *)(*v141 + 4LL) < v134;
              *v143 = v130[v144];
              v130[v144] = v145;
              v135 = v144 + v146;
              v133 = v141 + 1;
            }
            while ( v141 + 1 != v142 );
          }
LABEL_231:
          v147 = *(_DWORD *)(v131 + 4) < v134;
          *v141 = v130[v135];
          v130[v135] = v131;
          v148 = v135 + v147;
          if ( v148 >= v4 )
            goto LABEL_254;
          v149 = &a1[v148];
          v150 = *a1;
          *a1 = *v149;
          *v149 = v150;
          v151 = &a1[v148 + 1];
          v4 += ~v148;
          core::slice::sort::unstable::quicksort::quicksort_ref__onecore_windows::windef::_RECTL__core::slice::impl_0::sort_unstable_by_key::closure_env_0_ref__onecore_windows::windef::_RECTL__i32_rgncore::impl_1::subtract_complex::closure_env_0___(
            a1,
            v148,
            a3,
            a4);
          a3 = v149;
          a1 = v151;
          goto LABEL_208;
        }
      }
      v115 = *(_QWORD *)((char *)a1 + v114);
      v116 = *a1;
      if ( *(_DWORD *)(*a3 + 4LL) < *(_DWORD *)(v115 + 4) )
        goto LABEL_224;
      *a1 = v115;
      *(_QWORD *)((char *)a1 + v114) = v116;
      v117 = a1 + 1;
      v118 = a1[1];
      v119 = (unsigned __int64)&a1[v4 - 1];
      v120 = a1 + 2;
      v121 = *(_DWORD *)(*a1 + 4LL);
      if ( (unsigned __int64)(a1 + 2) < v119 )
        break;
      v128 = a1 + 1;
      v122 = 0;
      v129 = &a1[v4];
      if ( v120 != v129 )
        goto LABEL_234;
LABEL_235:
      v156 = v121 >= *(_DWORD *)(v118 + 4);
      *v128 = v117[v122];
      v117[v122] = v118;
      v157 = v122 + v156;
      if ( v157 >= v4 )
LABEL_254:
        BUG();
      v158 = *a1;
      *a1 = a1[v157];
      a1[v157] = v158;
      v4 -= v157 + 1;
      a1 += v157 + 1;
      a3 = 0;
LABEL_208:
      if ( v4 < 0x21 )
        goto LABEL_2;
    }
    v122 = 0;
    do
    {
      v123 = *v120;
      v124 = v121 >= *(_DWORD *)(*v120 + 4LL);
      *(v120 - 1) = v117[v122];
      v117[v122] = v123;
      v125 = v122 + v124;
      v126 = v120[1];
      v127 = v121 >= *(_DWORD *)(v126 + 4);
      *v120 = v117[v125];
      v117[v125] = v126;
      v122 = v125 + v127;
      v120 += 2;
    }
    while ( (unsigned __int64)v120 < v119 );
    v128 = v120 - 1;
    v129 = &a1[v4];
    if ( v120 == v129 )
      goto LABEL_235;
    do
    {
LABEL_234:
      v152 = v128;
      v128 = v120;
      v153 = v122;
      v154 = *v128;
      v155 = v121 >= *(_DWORD *)(*v128 + 4LL);
      *v152 = v117[v153];
      v117[v153] = v154;
      v122 = v153 + v155;
      v120 = v128 + 1;
    }
    while ( v128 + 1 != v129 );
    goto LABEL_235;
  }
LABEL_2:
  if ( v4 < 2 )
    goto LABEL_248;
  v6 = v4 >> 1;
  v7 = v4 >> 1;
  if ( v4 < 0x12 )
    v7 = v4;
  v8 = &a1[v6];
  v186 = v4 - v6;
  v9 = a1;
  v184 = v4;
  v183 = a1;
  v182 = v8;
  v181 = v4 >> 1;
  do
  {
    if ( v7 <= 0xC )
    {
      v64 = 1;
      if ( v7 > 8 )
      {
        v65 = v9[3];
        v66 = *(_DWORD *)(v65 + 4);
        v180 = v7;
        v67 = *v9;
        v68 = v9[1];
        v69 = v65;
        if ( v66 < *(_DWORD *)(*v9 + 4LL) )
        {
          v69 = *v9;
          v67 = v65;
        }
        v70 = v9[7];
        if ( *(_DWORD *)(v70 + 4) < *(_DWORD *)(v68 + 4) )
        {
          v70 = v9[1];
          v68 = v9[7];
        }
        v71 = v9[2];
        v72 = v9[5];
        if ( *(_DWORD *)(v72 + 4) < *(_DWORD *)(v71 + 4) )
        {
          v72 = v9[2];
          v71 = v9[5];
        }
        v73 = v9[4];
        v74 = v9[8];
        if ( *(_DWORD *)(v74 + 4) < *(_DWORD *)(v73 + 4) )
        {
          v74 = v9[4];
          v73 = v9[8];
        }
        v75 = v70;
        if ( *(_DWORD *)(v70 + 4) >= *(_DWORD *)(v67 + 4) )
          v70 = v67;
        else
          v75 = v67;
        v76 = v73;
        if ( *(_DWORD *)(v73 + 4) >= *(_DWORD *)(v71 + 4) )
          v73 = v71;
        else
          v76 = v71;
        v77 = v74;
        if ( *(_DWORD *)(v74 + 4) >= *(_DWORD *)(v69 + 4) )
          v74 = v69;
        else
          v77 = v69;
        v6 = v181;
        v78 = v9[6];
        if ( *(_DWORD *)(v78 + 4) < *(_DWORD *)(v72 + 4) )
        {
          v78 = v72;
          v72 = v9[6];
        }
        v79 = v73;
        if ( *(_DWORD *)(v73 + 4) >= *(_DWORD *)(v70 + 4) )
          v73 = v70;
        else
          v79 = v70;
        v80 = v74;
        if ( *(_DWORD *)(v74 + 4) >= *(_DWORD *)(v68 + 4) )
          v74 = v68;
        else
          v80 = v68;
        v81 = v72;
        if ( *(_DWORD *)(v72 + 4) >= *(_DWORD *)(v76 + 4) )
          v72 = v76;
        else
          v81 = v76;
        v82 = v77;
        if ( *(_DWORD *)(v77 + 4) >= *(_DWORD *)(v75 + 4) )
          v77 = v75;
        else
          v82 = v75;
        v83 = v72;
        if ( *(_DWORD *)(v72 + 4) >= *(_DWORD *)(v74 + 4) )
          v72 = v74;
        else
          v83 = v74;
        v84 = v78;
        if ( *(_DWORD *)(v78 + 4) < *(_DWORD *)(v80 + 4) )
        {
          v84 = v80;
          v80 = v78;
        }
        v4 = v184;
        v85 = v77;
        if ( *(_DWORD *)(v77 + 4) >= *(_DWORD *)(v81 + 4) )
          v77 = v81;
        else
          v85 = v81;
        a1 = v183;
        v86 = v72;
        if ( *(_DWORD *)(v72 + 4) >= *(_DWORD *)(v73 + 4) )
          v72 = v73;
        else
          v86 = v73;
        *v9 = v72;
        v87 = v83;
        if ( *(_DWORD *)(v83 + 4) >= *(_DWORD *)(v79 + 4) )
          v83 = v79;
        else
          v87 = v79;
        v88 = v77;
        if ( *(_DWORD *)(v77 + 4) >= *(_DWORD *)(v80 + 4) )
          v77 = v80;
        else
          v88 = v80;
        v89 = v82;
        if ( *(_DWORD *)(v82 + 4) < *(_DWORD *)(v84 + 4) )
        {
          v89 = v84;
          v84 = v82;
        }
        v8 = v182;
        v9[8] = v89;
        v90 = v77;
        if ( *(_DWORD *)(v77 + 4) >= *(_DWORD *)(v83 + 4) )
          v77 = v83;
        else
          v90 = v83;
        v91 = v88;
        if ( *(_DWORD *)(v88 + 4) >= *(_DWORD *)(v87 + 4) )
          v88 = v87;
        else
          v91 = v87;
        v92 = v85;
        if ( *(_DWORD *)(v85 + 4) < *(_DWORD *)(v84 + 4) )
        {
          v92 = v84;
          v84 = v85;
        }
        v9[7] = v92;
        v93 = v77;
        if ( *(_DWORD *)(v77 + 4) >= *(_DWORD *)(v86 + 4) )
          v77 = v86;
        else
          v93 = v86;
        v9[1] = v77;
        v7 = v180;
        v9[2] = v93;
        v94 = v88;
        if ( *(_DWORD *)(v88 + 4) >= *(_DWORD *)(v90 + 4) )
          v88 = v90;
        else
          v94 = v90;
        v9[3] = v88;
        v9[4] = v94;
        v95 = v84;
        if ( *(_DWORD *)(v84 + 4) >= *(_DWORD *)(v91 + 4) )
          v84 = v91;
        else
          v95 = v91;
        v9[5] = v84;
        v9[6] = v95;
        v64 = 9;
      }
    }
    else
    {
      v10 = v9[12];
      v11 = *(_DWORD *)(v10 + 4);
      v180 = v7;
      v12 = *v9;
      v13 = v10;
      if ( v11 < *(_DWORD *)(*v9 + 4LL) )
      {
        v13 = *v9;
        v12 = v10;
      }
      v14 = v9[1];
      *v9 = v12;
      v9[12] = v13;
      v15 = v9[10];
      if ( *(_DWORD *)(v15 + 4) < *(_DWORD *)(v14 + 4) )
      {
        v15 = v14;
        v14 = v9[10];
      }
      v9[1] = v14;
      v9[10] = v15;
      v16 = v9[2];
      v17 = v9[9];
      if ( *(_DWORD *)(v17 + 4) < *(_DWORD *)(v16 + 4) )
      {
        v17 = v9[2];
        v16 = v9[9];
      }
      v9[2] = v16;
      v9[9] = v17;
      v18 = v9[3];
      v19 = v9[7];
      if ( *(_DWORD *)(v19 + 4) < *(_DWORD *)(v18 + 4) )
      {
        v19 = v9[3];
        v18 = v9[7];
      }
      v9[3] = v18;
      v9[7] = v19;
      v20 = v9[5];
      v21 = v9[11];
      if ( *(_DWORD *)(v21 + 4) < *(_DWORD *)(v20 + 4) )
      {
        v21 = v9[5];
        v20 = v9[11];
      }
      v9[5] = v20;
      v9[11] = v21;
      v22 = v9[6];
      v23 = v9[8];
      if ( *(_DWORD *)(v23 + 4) < *(_DWORD *)(v22 + 4) )
      {
        v23 = v9[6];
        v22 = v9[8];
      }
      v9[6] = v22;
      v9[8] = v23;
      v24 = v22;
      if ( *(_DWORD *)(v22 + 4) >= *(_DWORD *)(v14 + 4) )
        v22 = v14;
      else
        v24 = v14;
      v9[1] = v22;
      v9[6] = v24;
      v25 = v18;
      if ( *(_DWORD *)(v18 + 4) >= *(_DWORD *)(v16 + 4) )
        v18 = v16;
      else
        v25 = v16;
      v9[2] = v18;
      v9[3] = v25;
      v26 = v21;
      if ( *(_DWORD *)(v21 + 4) >= *(_DWORD *)(v9[4] + 4LL) )
        v21 = v9[4];
      else
        v26 = v9[4];
      v9[4] = v21;
      v9[11] = v26;
      v27 = v17;
      if ( *(_DWORD *)(v17 + 4) < *(_DWORD *)(v19 + 4) )
      {
        v27 = v19;
        v19 = v17;
      }
      v9[7] = v19;
      v9[9] = v27;
      v28 = v15;
      if ( *(_DWORD *)(v15 + 4) < *(_DWORD *)(v23 + 4) )
      {
        v28 = v23;
        v23 = v15;
      }
      v9[8] = v23;
      v9[10] = v28;
      v29 = v21;
      if ( *(_DWORD *)(v21 + 4) >= *(_DWORD *)(*v9 + 4LL) )
        v21 = *v9;
      else
        v29 = *v9;
      *v9 = v21;
      v9[4] = v29;
      v30 = *(_DWORD *)(v18 + 4) < *(_DWORD *)(v22 + 4);
      v31 = v18;
      if ( *(_DWORD *)(v18 + 4) < *(_DWORD *)(v22 + 4) )
        v31 = v22;
      v185 = v31;
      if ( !v30 )
        v18 = v22;
      v9[1] = v18;
      v9[2] = v31;
      v32 = v24;
      if ( *(_DWORD *)(v24 + 4) < *(_DWORD *)(v25 + 4) )
      {
        v32 = v25;
        v25 = v24;
      }
      v9[3] = v25;
      v9[6] = v32;
      v33 = v23;
      if ( *(_DWORD *)(v23 + 4) >= *(_DWORD *)(v19 + 4) )
        v23 = v19;
      else
        v33 = v19;
      v9[7] = v23;
      v9[8] = v33;
      v34 = v28;
      if ( *(_DWORD *)(v28 + 4) >= *(_DWORD *)(v27 + 4) )
        v28 = v27;
      else
        v34 = v27;
      v9[9] = v28;
      v9[10] = v34;
      v35 = v13;
      if ( *(_DWORD *)(v13 + 4) < *(_DWORD *)(v26 + 4) )
      {
        v35 = v26;
        v26 = v13;
      }
      v9[11] = v26;
      v9[12] = v35;
      v36 = v32;
      if ( *(_DWORD *)(v32 + 4) >= *(_DWORD *)(v29 + 4) )
        v32 = v29;
      else
        v36 = v29;
      v9[4] = v32;
      v9[6] = v36;
      v37 = v28;
      if ( *(_DWORD *)(v28 + 4) >= *(_DWORD *)(v9[5] + 4LL) )
        v28 = v9[5];
      else
        v37 = v9[5];
      v9[5] = v28;
      v9[9] = v37;
      v38 = v26;
      if ( *(_DWORD *)(v26 + 4) >= *(_DWORD *)(v33 + 4) )
        v26 = v33;
      else
        v38 = v33;
      v9[8] = v26;
      v9[11] = v38;
      v39 = v35;
      if ( *(_DWORD *)(v35 + 4) >= *(_DWORD *)(v34 + 4) )
        v35 = v34;
      else
        v39 = v34;
      v9[10] = v35;
      v9[12] = v39;
      v40 = v28;
      if ( *(_DWORD *)(v28 + 4) >= *(_DWORD *)(v21 + 4) )
        v28 = v21;
      else
        v40 = v21;
      *v9 = v28;
      v9[5] = v40;
      v41 = v26;
      if ( *(_DWORD *)(v26 + 4) >= *(_DWORD *)(v25 + 4) )
        v26 = v25;
      else
        v41 = v25;
      v9[3] = v26;
      v9[8] = v41;
      v42 = v23;
      if ( *(_DWORD *)(v23 + 4) < *(_DWORD *)(v32 + 4) )
      {
        v42 = v32;
        v32 = v23;
      }
      v9[4] = v32;
      v9[7] = v42;
      v43 = v38;
      if ( *(_DWORD *)(v38 + 4) >= *(_DWORD *)(v36 + 4) )
        v38 = v36;
      else
        v43 = v36;
      v9[6] = v38;
      v9[11] = v43;
      v44 = v35;
      if ( *(_DWORD *)(v35 + 4) >= *(_DWORD *)(v37 + 4) )
        v35 = v37;
      else
        v44 = v37;
      v9[9] = v35;
      v9[10] = v44;
      v45 = v9[1];
      if ( *(_DWORD *)(v45 + 4) < *(_DWORD *)(v28 + 4) )
      {
        v45 = v28;
        v28 = v9[1];
      }
      *v9 = v28;
      v9[1] = v45;
      v46 = v40;
      if ( *(_DWORD *)(v40 + 4) >= *(_DWORD *)(v185 + 4) )
        v40 = v185;
      else
        v46 = v185;
      v9[2] = v40;
      v9[5] = v46;
      v47 = v35;
      if ( *(_DWORD *)(v35 + 4) >= *(_DWORD *)(v38 + 4) )
        v35 = v38;
      else
        v47 = v38;
      v9[6] = v35;
      v9[9] = v47;
      v48 = v41;
      if ( *(_DWORD *)(v41 + 4) < *(_DWORD *)(v42 + 4) )
      {
        v48 = v42;
        v42 = v41;
      }
      v9[7] = v42;
      v9[8] = v48;
      v49 = v43;
      if ( *(_DWORD *)(v43 + 4) < *(_DWORD *)(v44 + 4) )
      {
        v49 = v44;
        v44 = v43;
      }
      v9[10] = v44;
      v9[11] = v49;
      v50 = v26;
      if ( *(_DWORD *)(v26 + 4) < *(_DWORD *)(v45 + 4) )
      {
        v50 = v45;
        v45 = v26;
      }
      v8 = v182;
      v9[1] = v45;
      v9[3] = v50;
      v51 = v32;
      if ( *(_DWORD *)(v32 + 4) < *(_DWORD *)(v40 + 4) )
      {
        v51 = v40;
        v40 = v32;
      }
      v9[2] = v40;
      v9[4] = v51;
      v52 = v35;
      if ( *(_DWORD *)(v35 + 4) >= *(_DWORD *)(v46 + 4) )
        v35 = v46;
      else
        v52 = v46;
      a1 = v183;
      v9[5] = v35;
      v9[6] = v52;
      v53 = v44;
      if ( *(_DWORD *)(v44 + 4) >= *(_DWORD *)(v47 + 4) )
        v44 = v47;
      else
        v53 = v47;
      v9[9] = v44;
      v9[10] = v53;
      v54 = v40;
      if ( *(_DWORD *)(v40 + 4) >= *(_DWORD *)(v45 + 4) )
        v40 = v45;
      else
        v54 = v45;
      v9[1] = v40;
      v4 = v184;
      v9[2] = v54;
      v55 = v51;
      if ( *(_DWORD *)(v51 + 4) >= *(_DWORD *)(v50 + 4) )
        v51 = v50;
      else
        v55 = v50;
      v9[3] = v51;
      v9[4] = v55;
      v56 = v42;
      if ( *(_DWORD *)(v42 + 4) < *(_DWORD *)(v35 + 4) )
      {
        v56 = v35;
        v35 = v42;
      }
      v6 = v181;
      v9[5] = v35;
      v9[7] = v56;
      v57 = v48;
      if ( *(_DWORD *)(v48 + 4) < *(_DWORD *)(v52 + 4) )
      {
        v57 = v52;
        v52 = v48;
      }
      v9[6] = v52;
      v9[8] = v57;
      v58 = v51;
      if ( *(_DWORD *)(v51 + 4) >= *(_DWORD *)(v54 + 4) )
        v51 = v54;
      else
        v58 = v54;
      v9[2] = v51;
      v9[3] = v58;
      v59 = v35;
      if ( *(_DWORD *)(v35 + 4) >= *(_DWORD *)(v55 + 4) )
        v35 = v55;
      else
        v59 = v55;
      v9[4] = v35;
      v9[5] = v59;
      v60 = v56;
      if ( *(_DWORD *)(v56 + 4) < *(_DWORD *)(v52 + 4) )
      {
        v60 = v52;
        v52 = v56;
      }
      v9[6] = v52;
      v9[7] = v60;
      v61 = v44;
      if ( *(_DWORD *)(v44 + 4) < *(_DWORD *)(v57 + 4) )
      {
        v61 = v57;
        v57 = v44;
      }
      v9[8] = v57;
      v9[9] = v61;
      v62 = v35;
      if ( *(_DWORD *)(v35 + 4) >= *(_DWORD *)(v58 + 4) )
        v35 = v58;
      else
        v62 = v58;
      v9[3] = v35;
      v9[4] = v62;
      v63 = v52;
      if ( *(_DWORD *)(v52 + 4) >= *(_DWORD *)(v59 + 4) )
        v52 = v59;
      else
        v63 = v59;
      v9[5] = v52;
      v7 = v180;
      v9[6] = v63;
      v64 = 13;
    }
    if ( v64 - 1 >= v7 )
      goto LABEL_254;
    if ( v64 != v7 )
    {
      v97 = (char *)&v9[v7];
      v98 = (unsigned int)(8 * v64);
      v99 = (char *)v9 + (unsigned int)v98;
      do
      {
        v101 = *((_QWORD *)v99 - 1);
        v102 = *(_QWORD *)v99;
        v103 = *(_DWORD *)(*(_QWORD *)v99 + 4LL);
        if ( v103 < *(_DWORD *)(v101 + 4) )
        {
          v104 = v98;
          do
          {
            *(_QWORD *)((char *)v9 + v104) = v101;
            if ( v104 == 8 )
            {
              v100 = v9;
              goto LABEL_200;
            }
            v101 = *(_QWORD *)((char *)v9 + v104 - 16);
            v104 -= 8;
          }
          while ( v103 < *(_DWORD *)(v101 + 4) );
          v100 = (_QWORD *)((char *)v9 + v104);
LABEL_200:
          *v100 = v102;
        }
        v99 += 8;
        v98 += 8;
      }
      while ( v99 != v97 );
    }
    if ( v4 < 0x12 )
      goto LABEL_248;
    v7 = v186;
    v96 = v9 == a1;
    v9 = v8;
  }
  while ( v96 );
  v160 = v4 - 1;
  v161 = &a1[v4 - 1];
  v162 = v8 - 1;
  v163 = 0;
  v164 = a1;
  do
  {
    v165 = *v164;
    v166 = *(_DWORD *)(*v8 + 4LL);
    v167 = 0;
    v168 = 0;
    v170 = __OFSUB__(v166, *(_DWORD *)(*v164 + 4LL));
    v169 = v166 - *(_DWORD *)(*v164 + 4LL) < 0;
    if ( v166 < *(_DWORD *)(*v164 + 4LL) )
      v165 = *v8;
    Src[v163++] = v165;
    LOBYTE(v167) = v169 == v170;
    LOBYTE(v168) = v169 ^ v170;
    v8 += v168;
    v171 = *v161;
    v172 = *(_DWORD *)(*v161 + 4LL);
    v173 = 0;
    v164 += v167;
    v174 = v172 < *(_DWORD *)(*v162 + 4LL);
    if ( v172 < *(_DWORD *)(*v162 + 4LL) )
      v171 = *v162;
    LOBYTE(v173) = v172 >= *(_DWORD *)(*v162 + 4LL);
    Src[v160] = v171;
    v161 = (_QWORD *)((char *)v161 - (unsigned int)(8 * v173));
    v162 = (_QWORD *)((char *)v162 - (unsigned int)(8 * v174));
    --v160;
  }
  while ( v6 != v163 );
  v175 = v162 + 1;
  v176 = v161 + 1;
  if ( (v4 & 1) != 0 )
  {
    v178 = v8;
    if ( v164 < v175 )
      v178 = v164;
    Src[v163] = *v178;
    v177 = &v8[v164 >= v175] != v176;
    if ( &v164[v164 < v175] != v175 )
LABEL_253:
      RNvNtNtNtNtCs9MWeMO1rkJG_4core5slice4sort6shared9smallsort22panic_on_ord_violation();
  }
  else
  {
    v177 = v8 != v176;
    if ( v164 != v175 )
      goto LABEL_253;
  }
  if ( v177 )
    goto LABEL_253;
  memmove(a1, Src, 8 * v4);
LABEL_248:
  result = (unsigned __int64)v179 ^ v188;
  if ( _security_cookie != ((unsigned __int64)v179 ^ v188) )
    goto LABEL_255;
  return result;
}

```

## disassembly

```asm
0x140016650  push    r15
0x140016652  push    r14
0x140016654  push    r13
0x140016656  push    r12
0x140016658  push    rsi
0x140016659  push    rdi
0x14001665a  push    rbp
0x14001665b  push    rbx
0x14001665c  sub     rsp, 168h
0x140016663  mov     r12, rdx
0x140016666  mov     r13, rcx
0x140016669  mov     rax, cs:__security_cookie
0x140016670  xor     rax, rsp
0x140016673  mov     [rsp+1A8h+var_48], rax
0x14001667b  cmp     rdx, 21h ; '!'
0x14001667f  jnb     loc_140016ECE
0x140016685  cmp     r12, 2
0x140016689  jb      loc_140017313
0x14001668f  mov     rbp, r12
0x140016692  shr     rbp, 1
0x140016695  cmp     r12, 12h
0x140016699  mov     rdx, rbp
0x14001669c  cmovb   rdx, r12
0x1400166a0  lea     r15, ds:0[rbp*8]
0x1400166a8  add     r15, r13
0x1400166ab  mov     rax, r12
0x1400166ae  sub     rax, rbp
0x1400166b1  mov     [rsp+1A8h+var_150], rax
0x1400166b6  mov     r8, r13
0x1400166b9  mov     [rsp+1A8h+var_160], r12
0x1400166be  mov     [rsp+1A8h+var_168], r13
0x1400166c3  mov     [rsp+1A8h+var_170], r15
0x1400166c8  mov     [rsp+1A8h+var_178], rbp
0x1400166cd  nop     dword ptr [rax]
0x1400166d0  cmp     rdx, 0Ch
0x1400166d4  jbe     loc_140016BF0
0x1400166da  mov     rax, [r8+60h]
0x1400166de  mov     ecx, [rax+4]
0x1400166e1  mov     [rsp+1A8h+var_180], rdx
0x1400166e6  mov     rdx, [r8]
0x1400166e9  cmp     ecx, [rdx+4]
0x1400166ec  mov     r12, rax
0x1400166ef  cmovl   r12, rdx
0x1400166f3  cmovl   rdx, rax
0x1400166f7  mov     r15, [r8+8]
0x1400166fb  mov     [r8], rdx
0x1400166fe  mov     [r8+60h], r12
0x140016702  mov     rax, [r8+50h]
0x140016706  mov     ecx, [rax+4]
0x140016709  cmp     ecx, [r15+4]
0x14001670d  mov     rdx, rax
0x140016710  cmovl   rdx, r15
0x140016714  cmovl   r15, rax
0x140016718  mov     [r8+8], r15
0x14001671c  mov     [r8+50h], rdx
0x140016720  mov     rax, [r8+48h]
0x140016724  mov     r13, [r8+10h]
0x140016728  mov     ecx, [rax+4]
0x14001672b  cmp     ecx, [r13+4]
0x14001672f  mov     r9, rax
0x140016732  cmovl   r9, r13
0x140016736  cmovl   r13, rax
0x14001673a  mov     [r8+10h], r13
0x14001673e  mov     [r8+48h], r9
0x140016742  mov     rbx, [r8+18h]
0x140016746  mov     rax, [r8+38h]
0x14001674a  mov     ecx, [rax+4]
0x14001674d  cmp     ecx, [rbx+4]
0x140016750  mov     r10, rax
0x140016753  cmovl   r10, rbx
0x140016757  cmovl   rbx, rax
0x14001675b  mov     [r8+18h], rbx
0x14001675f  mov     [r8+38h], r10
0x140016763  mov     rax, [r8+28h]
0x140016767  mov     r11, [r8+58h]
0x14001676b  mov     ecx, [r11+4]
0x14001676f  cmp     ecx, [rax+4]
0x140016772  mov     rcx, r11
0x140016775  cmovl   rcx, rax
0x140016779  cmovl   rax, r11
0x14001677d  mov     [r8+28h], rax
0x140016781  mov     [r8+58h], rcx
0x140016785  mov     rsi, [r8+30h]
0x140016789  mov     rax, [r8+40h]
0x14001678d  mov     r11d, [rax+4]
0x140016791  cmp     r11d, [rsi+4]
0x140016795  mov     r14, rax
0x140016798  cmovl   r14, rsi
0x14001679c  cmovl   rsi, rax
0x1400167a0  mov     [r8+30h], rsi
0x1400167a4  mov     [r8+40h], r14
0x1400167a8  mov     eax, [rsi+4]
0x1400167ab  cmp     eax, [r15+4]
0x1400167af  mov     rax, rsi
0x1400167b2  cmovl   rax, r15
0x1400167b6  cmovge  rsi, r15
0x1400167ba  mov     [r8+8], rsi
0x1400167be  mov     [r8+30h], rax
0x1400167c2  mov     r11d, [rbx+4]
0x1400167c6  cmp     r11d, [r13+4]
0x1400167ca  mov     rbp, rbx
0x1400167cd  cmovl   rbp, r13
0x1400167d1  cmovge  rbx, r13
0x1400167d5  mov     [r8+10h], rbx
0x1400167d9  mov     [r8+18h], rbp
0x1400167dd  mov     r11, [r8+20h]
0x1400167e1  mov     edi, [rcx+4]
0x1400167e4  cmp     edi, [r11+4]
0x1400167e8  mov     r15, rcx
0x1400167eb  cmovl   r15, r11
0x1400167ef  cmovge  rcx, r11
0x1400167f3  mov     [r8+20h], rcx
0x1400167f7  mov     [r8+58h], r15
0x1400167fb  mov     r11d, [r9+4]
0x1400167ff  cmp     r11d, [r10+4]
0x140016803  mov     r11, r9
0x140016806  cmovl   r11, r10
0x14001680a  cmovl   r10, r9
0x14001680e  mov     [r8+38h], r10
0x140016812  mov     [r8+48h], r11
0x140016816  mov     r9d, [rdx+4]
0x14001681a  cmp     r9d, [r14+4]
0x14001681e  mov     r13, rdx
0x140016821  cmovl   r13, r14
0x140016825  cmovl   r14, rdx
0x140016829  mov     [r8+40h], r14
0x14001682d  mov     [r8+50h], r13
0x140016831  mov     rdx, [r8]
0x140016834  mov     r9d, [rcx+4]
0x140016838  cmp     r9d, [rdx+4]
0x14001683c  mov     r9, rcx
0x14001683f  cmovl   r9, rdx
0x140016843  cmovge  rcx, rdx
0x140016847  mov     [r8], rcx
0x14001684a  mov     [r8+20h], r9
0x14001684e  mov     edx, [rbx+4]
0x140016851  cmp     edx, [rsi+4]
0x140016854  mov     rdx, rbx
0x140016857  cmovl   rdx, rsi
0x14001685b  mov     [rsp+1A8h+var_158], rdx
0x140016860  cmovge  rbx, rsi
0x140016864  mov     [r8+8], rbx
0x140016868  mov     [r8+10h], rdx
0x14001686c  mov     edx, [rax+4]
0x14001686f  cmp     edx, [rbp+4]
0x140016872  mov     rbx, rax
0x140016875  cmovl   rbx, rbp
0x140016879  cmovl   rbp, rax
0x14001687d  mov     [r8+18h], rbp
0x140016881  mov     [r8+30h], rbx
0x140016885  mov     eax, [r14+4]
0x140016889  cmp     eax, [r10+4]
0x14001688d  mov     rdi, r14
0x140016890  cmovl   rdi, r10
0x140016894  cmovge  r14, r10
0x140016898  mov     [r8+38h], r14
0x14001689c  mov     [r8+40h], rdi
0x1400168a0  mov     eax, [r13+4]
0x1400168a4  cmp     eax, [r11+4]
0x1400168a8  mov     rax, r13
0x1400168ab  cmovl   rax, r11
0x1400168af  cmovge  r13, r11
0x1400168b3  mov     [r8+48h], r13
0x1400168b7  mov     [r8+50h], rax
0x1400168bb  mov     edx, [r12+4]
0x1400168c0  cmp     edx, [r15+4]
0x1400168c4  mov     r10, r12
0x1400168c7  cmovl   r10, r15
0x1400168cb  cmovl   r15, r12
0x1400168cf  mov     [r8+58h], r15
0x1400168d3  mov     [r8+60h], r10
0x1400168d7  mov     edx, [rbx+4]
0x1400168da  cmp     edx, [r9+4]
0x1400168de  mov     rdx, rbx
0x1400168e1  cmovl   rdx, r9
0x1400168e5  cmovge  rbx, r9
0x1400168e9  mov     [r8+20h], rbx
0x1400168ed  mov     [r8+30h], rdx
0x1400168f1  mov     r9, [r8+28h]
0x1400168f5  mov     r11d, [r13+4]
0x1400168f9  cmp     r11d, [r9+4]
0x1400168fd  mov     rsi, r13
0x140016900  cmovl   rsi, r9
0x140016904  cmovge  r13, r9
0x140016908  mov     [r8+28h], r13
0x14001690c  mov     [r8+48h], rsi
0x140016910  mov     r9d, [r15+4]
0x140016914  cmp     r9d, [rdi+4]
0x140016918  mov     r11, r15
0x14001691b  cmovl   r11, rdi
0x14001691f  cmovge  r15, rdi
0x140016923  mov     [r8+40h], r15
0x140016927  mov     [r8+58h], r11
0x14001692b  mov     r9d, [r10+4]
0x14001692f  cmp     r9d, [rax+4]
0x140016933  mov     r9, r10
0x140016936  cmovl   r9, rax
0x14001693a  cmovge  r10, rax
0x14001693e  mov     [r8+50h], r10
0x140016942  mov     [r8+60h], r9
0x140016946  mov     eax, [r13+4]
0x14001694a  cmp     eax, [rcx+4]
0x14001694d  mov     r12, r13
0x140016950  cmovl   r12, rcx
0x140016954  cmovge  r13, rcx
0x140016958  mov     [r8], r13
0x14001695b  mov     [r8+28h], r12
0x14001695f  mov     eax, [r15+4]
0x140016963  cmp     eax, [rbp+4]
0x140016966  mov     rcx, r15
0x140016969  cmovl   rcx, rbp
0x14001696d  cmovge  r15, rbp
0x140016971  mov     [r8+18h], r15
0x140016975  mov     [r8+40h], rcx
0x140016979  mov     eax, [r14+4]
0x14001697d  cmp     eax, [rbx+4]
0x140016980  mov     rbp, r14
0x140016983  cmovl   rbp, rbx
0x140016987  cmovl   rbx, r14
0x14001698b  mov     [r8+20h], rbx
0x14001698f  mov     [r8+38h], rbp
0x140016993  mov     eax, [r11+4]
0x140016997  cmp     eax, [rdx+4]
0x14001699a  mov     r9, r11
0x14001699d  cmovl   r9, rdx
0x1400169a1  cmovge  r11, rdx
0x1400169a5  mov     [r8+30h], r11
0x1400169a9  mov     [r8+58h], r9
0x1400169ad  mov     eax, [r10+4]
0x1400169b1  cmp     eax, [rsi+4]
0x1400169b4  mov     r14, r10
0x1400169b7  cmovl   r14, rsi
0x1400169bb  cmovge  r10, rsi
0x1400169bf  mov     [r8+48h], r10
0x1400169c3  mov     [r8+50h], r14
0x1400169c7  mov     rax, [r8+8]
0x1400169cb  mov     edx, [rax+4]
0x1400169ce  cmp     edx, [r13+4]
0x1400169d2  mov     rsi, rax
0x1400169d5  cmovl   rsi, r13
0x1400169d9  cmovl   r13, rax
0x1400169dd  mov     [r8], r13
0x1400169e0  mov     [r8+8], rsi
0x1400169e4  mov     eax, [r12+4]
0x1400169e9  mov     rdx, [rsp+1A8h+var_158]
0x1400169ee  cmp     eax, [rdx+4]
0x1400169f1  mov     r13, r12
0x1400169f4  cmovl   r13, rdx
0x1400169f8  cmovge  r12, rdx
0x1400169fc  mov     [r8+10h], r12
0x140016a00  mov     [r8+28h], r13
0x140016a04  mov     eax, [r10+4]
0x140016a08  cmp     eax, [r11+4]
0x140016a0c  mov     rdi, r10
0x140016a0f  cmovl   rdi, r11
0x140016a13  cmovge  r10, r11
0x140016a17  mov     [r8+30h], r10
0x140016a1b  mov     [r8+48h], rdi
0x140016a1f  mov     eax, [rcx+4]
0x140016a22  cmp     eax, [rbp+4]
0x140016a25  mov     rax, rcx
0x140016a28  cmovl   rax, rbp
0x140016a2c  cmovl   rbp, rcx
0x140016a30  mov     [r8+38h], rbp
0x140016a34  mov     [r8+40h], rax
0x140016a38  mov     ecx, [r9+4]
0x140016a3c  cmp     ecx, [r14+4]
0x140016a40  mov     rcx, r9
0x140016a43  cmovl   rcx, r14
0x140016a47  cmovl   r14, r9
0x140016a4b  mov     [r8+50h], r14
0x140016a4f  mov     [r8+58h], rcx
0x140016a53  mov     ecx, [r15+4]
0x140016a57  cmp     ecx, [rsi+4]
0x140016a5a  mov     r9, r15
0x140016a5d  cmovl   r9, rsi
0x140016a61  cmovl   rsi, r15
0x140016a65  mov     r15, [rsp+1A8h+var_170]
0x140016a6a  mov     [r8+8], rsi
0x140016a6e  mov     [r8+18h], r9
0x140016a72  mov     ecx, [rbx+4]
0x140016a75  cmp     ecx, [r12+4]
0x140016a7a  mov     rcx, rbx
0x140016a7d  cmovl   rcx, r12
0x140016a81  cmovl   r12, rbx
0x140016a85  mov     [r8+10h], r12
0x140016a89  mov     [r8+20h], rcx
0x140016a8d  mov     edx, [r10+4]
0x140016a91  cmp     edx, [r13+4]
0x140016a95  mov     rdx, r10
0x140016a98  cmovl   rdx, r13
0x140016a9c  cmovge  r10, r13
0x140016aa0  mov     r13, [rsp+1A8h+var_168]
0x140016aa5  mov     [r8+28h], r10
0x140016aa9  mov     [r8+30h], rdx
0x140016aad  mov     r11d, [r14+4]
0x140016ab1  cmp     r11d, [rdi+4]
0x140016ab5  mov     r11, r14
0x140016ab8  cmovl   r11, rdi
0x140016abc  cmovge  r14, rdi
  ... truncated ...
```
