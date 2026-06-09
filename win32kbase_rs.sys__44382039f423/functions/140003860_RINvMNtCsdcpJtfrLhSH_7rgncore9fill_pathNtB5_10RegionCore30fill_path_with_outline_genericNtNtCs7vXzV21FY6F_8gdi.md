# _RINvMNtCsdcpJtfrLhSH_7rgncore9fill_pathNtB5_10RegionCore30fill_path_with_outline_genericNtNtCs7vXzV21FY6F_8gdi_rust6region12EPATHOBJSinkEB1s_

- ea: `0x140003860`
- end: `0x140004811`
- name: `_RINvMNtCsdcpJtfrLhSH_7rgncore9fill_pathNtB5_10RegionCore30fill_path_with_outline_genericNtNtCs7vXzV21FY6F_8gdi_rust6region12EPATHOBJSinkEB1s_`
- size: `4017`
- prototype: `__int64 __fastcall(unsigned __int64, __int64 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140004cf0`

## callees

- `0x140003860`
- `0x14000a950`
- `0x14000f5b0`
- `0x14000fc10`
- `0x14001791c`
- `0x14001792e`
- `0x140017a10`
- `0x140017dd0`
- `0x140017f00`
- `0x140018470`
- `0x1400184d7`
- `0x140018630`
- `0x140018c00`

## pseudocode

```c
__int64 __fastcall RINvMNtCsdcpJtfrLhSH_7rgncore9fill_pathNtB5_10RegionCore30fill_path_with_outline_genericNtNtCs7vXzV21FY6F_8gdi_rust6region12EPATHOBJSinkEB1s_(
        unsigned __int64 a1,
        __int64 *a2)
{
  unsigned __int64 v2; // r14
  size_t v4; // r12
  __int64 v5; // rbx
  __int64 v6; // r15
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rdx
  __int64 v9; // rax
  unsigned __int64 v10; // rdi
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rsi
  __int64 v14; // rax
  int v15; // ecx
  int v16; // eax
  unsigned __int64 v17; // rdi
  char valid; // al
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // r13
  __int64 v21; // rcx
  __int64 v22; // r15
  __int64 v23; // r11
  unsigned __int64 v24; // rsi
  __int64 v25; // r10
  unsigned __int64 v26; // r12
  __int64 v27; // r10
  unsigned __int64 v28; // r11
  unsigned __int64 v29; // rax
  __int64 v30; // r8
  unsigned __int64 v31; // r9
  unsigned __int64 v32; // rcx
  unsigned __int64 v33; // rcx
  unsigned __int64 v34; // rbp
  unsigned __int64 v35; // r13
  unsigned __int64 v36; // rsi
  unsigned __int64 v37; // rbx
  unsigned __int64 v38; // r9
  unsigned __int64 v39; // rsi
  unsigned int v40; // r9d
  unsigned int v41; // eax
  char v42; // al
  unsigned __int64 v43; // rbp
  __int64 v44; // r8
  unsigned __int64 v45; // r9
  __int64 v46; // rbx
  unsigned __int64 v47; // r10
  unsigned __int64 v48; // rax
  unsigned int v49; // edx
  unsigned int v50; // eax
  unsigned __int64 v51; // rcx
  unsigned __int64 v52; // rdx
  __int64 v53; // rax
  __int64 v54; // rax
  unsigned __int64 v55; // r11
  unsigned __int64 v56; // rcx
  bool v57; // zf
  __int64 v58; // rcx
  unsigned __int64 v59; // r15
  __int64 v60; // r12
  __int64 v61; // r8
  unsigned __int64 v62; // rbx
  __int64 v63; // r10
  unsigned __int64 v64; // r9
  unsigned __int64 v65; // r13
  unsigned __int64 v66; // rdi
  bool v67; // cc
  unsigned __int64 v68; // rbp
  unsigned __int64 v69; // r11
  unsigned __int64 v70; // r11
  unsigned int v71; // edx
  unsigned int v72; // eax
  __int64 v73; // rax
  unsigned __int64 v74; // rsi
  int *v75; // r15
  __int64 v76; // r12
  unsigned __int64 v77; // rbx
  int v78; // eax
  __int64 v79; // rdx
  unsigned __int64 v80; // r8
  __int64 v81; // rbp
  unsigned __int64 v82; // rcx
  unsigned __int64 v83; // r9
  unsigned __int64 v84; // rax
  unsigned __int64 v85; // rbx
  unsigned int v86; // r8d
  unsigned int v87; // eax
  __int64 v88; // r12
  char v89; // al
  bool v90; // cf
  unsigned __int64 v91; // r11
  int v92; // ecx
  __int64 v93; // rax
  __int64 v94; // rax
  int v95; // ecx
  unsigned int v96; // esi
  __int64 v98; // [rsp+0h] [rbp-148h] BYREF
  unsigned __int64 v99; // [rsp+30h] [rbp-118h]
  unsigned __int64 v100; // [rsp+38h] [rbp-110h]
  __int64 v101; // [rsp+40h] [rbp-108h]
  __int64 v102; // [rsp+48h] [rbp-100h]
  __int64 v103; // [rsp+50h] [rbp-F8h]
  unsigned __int64 v104; // [rsp+58h] [rbp-F0h]
  __int64 v105; // [rsp+60h] [rbp-E8h]
  __int64 v106; // [rsp+68h] [rbp-E0h]
  int v107; // [rsp+74h] [rbp-D4h]
  __int64 v108; // [rsp+78h] [rbp-D0h]
  unsigned __int64 v109; // [rsp+80h] [rbp-C8h]
  __int64 v110; // [rsp+88h] [rbp-C0h]
  unsigned __int64 v111; // [rsp+90h] [rbp-B8h]
  unsigned __int64 v112; // [rsp+98h] [rbp-B0h]
  __int64 v113; // [rsp+A0h] [rbp-A8h]
  unsigned __int64 v114; // [rsp+A8h] [rbp-A0h]
  unsigned __int64 v115; // [rsp+B0h] [rbp-98h]
  unsigned __int64 v116; // [rsp+B8h] [rbp-90h]
  unsigned __int64 v117; // [rsp+C0h] [rbp-88h]
  unsigned __int64 v118; // [rsp+C8h] [rbp-80h]
  unsigned __int64 v119; // [rsp+D0h] [rbp-78h]
  unsigned __int64 v120; // [rsp+D8h] [rbp-70h]
  char v121; // [rsp+E7h] [rbp-61h] BYREF
  int v122; // [rsp+E8h] [rbp-60h] BYREF
  int v123; // [rsp+ECh] [rbp-5Ch]
  void *v124; // [rsp+F0h] [rbp-58h]
  __int64 v125; // [rsp+100h] [rbp-48h]

  v4 = *(_QWORD *)(a1 + 16);
  if ( v4 )
  {
    v10 = a1;
    v5 = 8;
    if ( v4 >= 9 )
      v5 = *(_QWORD *)(a1 + 16);
    RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecNtB5_11RawVecInner11finish_growCs7vXzV21FY6F_8gdi_rust_llvm_1180095224807683263(
      &v122,
      0,
      1,
      v5,
      1,
      1);
    if ( v122 == 1 )
    {
      v96 = 14;
      goto LABEL_177;
    }
    v101 = (__int64)v124;
    memset(v124, 0, v4);
  }
  else
  {
    v101 = 1;
    v5 = 0;
  }
  v6 = RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore10first_scan();
  v2 = v7;
  v105 = *a2;
  v108 = a2[1];
  v99 = v4;
  do
  {
    v8 = *(_QWORD *)(v6 + 16);
    if ( v2 >= v8 )
LABEL_200:
      RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
        v2,
        v8,
        &anon_01189c164b0c425bf67614ee34d1a89c_1_llvm_7541658972310832757);
    v9 = *(_QWORD *)(v6 + 8);
    v10 = *(int *)(v9 + 4 * v2);
    if ( !*(_DWORD *)(v9 + 4 * v2) )
      goto LABEL_166;
    v11 = v2 + 3;
    v111 = v2 + 1;
    v120 = v2 + 4;
    v12 = 0;
    do
    {
      v112 = v12;
      v13 = v11 + v12;
      if ( v11 + v12 >= v4 )
        RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(v11 + v12, v4, &off_14001B0D8);
      if ( *(_BYTE *)(v101 + v13) )
        goto LABEL_9;
      v114 = v11;
      v8 = *(_QWORD *)(v6 + 16);
      if ( v2 >= v8 )
        goto LABEL_200;
      v14 = *(_QWORD *)(v6 + 8);
      if ( v112 >= *(int *)(v14 + 4 * v2) )
        goto LABEL_172;
      if ( v13 >= v8 )
        goto LABEL_193;
      if ( v111 >= v8 )
        RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
          v111,
          v8,
          &anon_01189c164b0c425bf67614ee34d1a89c_10_llvm_7541658972310832757);
      v15 = *(_DWORD *)(v14 + 4 * v13);
      v16 = *(_DWORD *)(v14 + 4 * v2 + 4);
      v122 = v15;
      v123 = v16;
      v107 = 31;
      if ( !(unsigned int)EPATHOBJ_bMoveTo_0(v105, v108, &v122) )
        goto LABEL_174;
      v119 = v10;
      v110 = v5;
      v8 = *(_QWORD *)(v6 + 16);
      if ( v2 >= v8 )
        goto LABEL_200;
      v17 = v120 + *(int *)(*(_QWORD *)(v6 + 8) + 4 * v2);
      valid = RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalRINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanCs7vXzV21FY6F_8gdi_rust_llvm_7541658972310832757(
                v6,
                v17);
      v19 = v112;
      v20 = v112 & 1;
      *(_BYTE *)(v101 + v13) = 1;
      v116 = ~v20;
      v117 = v20 + 3;
      v21 = v6;
      v22 = 0;
      if ( valid )
        v22 = v21;
      v115 = v2;
      v109 = v2;
      v113 = v21;
      v23 = v21;
      v24 = v19;
      v104 = v20;
      v25 = 1;
      if ( v22 )
        goto LABEL_20;
      while ( 2 )
      {
        v43 = v99;
LABEL_70:
        v8 = *(_QWORD *)(v21 + 16);
        if ( v2 >= v8 )
          goto LABEL_200;
        v44 = *(_QWORD *)(v21 + 8);
        v45 = *(int *)(v44 + 4 * v2);
        if ( v24 >= v45 )
          goto LABEL_172;
        v46 = v21;
        v33 = v2 + v24 + 3;
        if ( v33 >= v8 )
          goto LABEL_187;
        if ( v2 + 2 >= v8 )
          RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
            v2 + 2,
            v8,
            &anon_01189c164b0c425bf67614ee34d1a89c_15_llvm_7541658972310832757);
        v47 = v24 + v25;
        if ( v47 >= v45 )
          goto LABEL_172;
        v102 = v23;
        v48 = v47 + v2 + 3;
        if ( v48 >= v8 )
          RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
            v47 + v2 + 3,
            v8,
            &anon_01189c164b0c425bf67614ee34d1a89c_13_llvm_7541658972310832757);
        v10 = v47;
        v49 = *(_DWORD *)(v44 + 4 * v2 + 8);
        v50 = *(_DWORD *)(v44 + 4 * v48);
        v122 = *(_DWORD *)(v44 + 4 * v33);
        v123 = v49;
        v124 = (void *)__PAIR64__(v49, v50);
        if ( !(unsigned int)EPATHOBJ_bPolyLineTo_0(v105, v108, &v122, 2) )
          goto LABEL_170;
        if ( !v109 )
          goto LABEL_81;
        v51 = v109 - 1;
        v52 = *(_QWORD *)(v102 + 16);
        if ( v109 - 1 >= v52 )
LABEL_197:
          RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
            v51,
            v52,
            &anon_01189c164b0c425bf67614ee34d1a89c_8_llvm_7541658972310832757);
        v53 = *(int *)(*(_QWORD *)(v102 + 8) + 4 * v109 - 4);
        if ( v53 < 0 )
LABEL_184:
          RNvNtCs9MWeMO1rkJG_4core6result13unwrap_failed(
            (unsigned int)&anon_01189c164b0c425bf67614ee34d1a89c_5_llvm_7541658972310832757,
            43,
            (unsigned int)&v121,
            (unsigned int)anon_01189c164b0c425bf67614ee34d1a89c_4_llvm_7541658972310832757,
            (__int64)&anon_01189c164b0c425bf67614ee34d1a89c_9_llvm_7541658972310832757);
        if ( v109 >= v53 + 4 )
        {
          v24 = v109 - v53 - 4;
          v57 = (unsigned __int8)RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalRINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanCs7vXzV21FY6F_8gdi_rust_llvm_7541658972310832757(
                                   v102,
                                   v24) == 0;
          v54 = 0;
          if ( !v57 )
            v54 = v102;
          v55 = v10;
          v56 = v109 + v10 + 3;
          if ( v56 >= v43 )
            goto LABEL_201;
        }
        else
        {
LABEL_81:
          v54 = 0;
          v55 = v10;
          v56 = v109 + v10 + 3;
          if ( v56 >= v43 )
            goto LABEL_201;
        }
        *(_BYTE *)(v101 + v56) = 1;
        v103 = -1;
        v58 = v46;
        if ( !v54 )
          goto LABEL_140;
        while ( 1 )
        {
          v59 = v24;
          v8 = *(_QWORD *)(v54 + 16);
          if ( v24 >= v8 )
            goto LABEL_192;
          v60 = v54;
          v61 = *(_QWORD *)(v54 + 8);
          v62 = *(int *)(v61 + 4 * v24);
          if ( !*(_DWORD *)(v61 + 4 * v24) )
            goto LABEL_140;
          v29 = *(_QWORD *)(v58 + 16);
          if ( v2 >= v29 )
            goto LABEL_189;
          v63 = *(_QWORD *)(v58 + 8);
          v64 = *(int *)(v63 + 4 * v2);
          if ( v55 >= v64 )
            goto LABEL_172;
          v106 = v58;
          v32 = v55 + v2 + 3;
          if ( v32 >= v29 )
            goto LABEL_190;
          v65 = v116 + v62;
          if ( !__CFADD__(v116, v62) )
            goto LABEL_172;
          v33 = v24 + v65 + 3;
          if ( v33 >= v8 )
            goto LABEL_187;
          v118 = v55 + v2;
          v24 = *(unsigned int *)(v63 + 4 * (v55 + v2) + 12);
          v66 = v59 + 3;
          v67 = *(_DWORD *)(v61 + 4 * v33) < (int)v24;
          v100 = v55;
          if ( v67 )
          {
            v68 = v116 + v62;
            goto LABEL_109;
          }
          if ( (unsigned int)v104 >= (unsigned int)v62 )
            goto LABEL_172;
          v33 = v59 + v117;
          if ( v59 + v117 >= v8 )
            goto LABEL_187;
          if ( *(_DWORD *)(v61 + 4 * v33) >= (int)v24 )
            break;
          v69 = (v62 - 1) >> 1;
          v68 = v104;
          if ( v69 != v104 )
          {
            v68 = v104;
            while ( v69 < v62 )
            {
              v33 = v66 + v69;
              if ( v66 + v69 >= v8 )
                goto LABEL_187;
              if ( *(_DWORD *)(v61 + 4 * v33) >= (int)v24 )
              {
                v65 = v69;
                v69 = (v68 + v69) >> 1;
                if ( v69 == v68 )
                  goto LABEL_109;
              }
              else
              {
                v68 = v69;
                v69 = (v69 + v65) >> 1;
                if ( v69 == v68 )
                  goto LABEL_109;
              }
            }
            goto LABEL_172;
          }
LABEL_109:
          v20 = v104;
          if ( (v68 & 1) != (_DWORD)v104 )
          {
            if ( v68 >= v62 )
              goto LABEL_172;
            v33 = v66 + v68;
            if ( v66 + v68 >= v8 )
              goto LABEL_187;
            if ( v100 - 1 >= v64 )
              goto LABEL_172;
            v38 = v118 + 2;
            if ( v118 + 2 >= v29 )
              goto LABEL_191;
            if ( *(_DWORD *)(v61 + 4 * v33) <= *(_DWORD *)(v63 + 4 * v118 + 8) )
              goto LABEL_139;
LABEL_122:
            if ( v68 >= v62 )
              goto LABEL_172;
            goto LABEL_125;
          }
          v70 = v68 + 1;
          if ( v100 < v64 - 1 )
          {
            if ( v70 >= v62 )
              goto LABEL_172;
            v33 = v59 + v68 + 4;
            if ( v33 >= v8 )
              goto LABEL_187;
            if ( v100 + 1 >= v64 )
              goto LABEL_172;
            ++v68;
            v38 = v118 + 4;
            if ( v118 + 4 >= v29 )
              goto LABEL_191;
            v20 = v104;
            if ( *(_DWORD *)(v61 + 4 * v33) > *(_DWORD *)(v63 + 4 * v118 + 16) )
            {
              v103 = 1;
              goto LABEL_139;
            }
            goto LABEL_122;
          }
          ++v68;
          if ( v70 >= v62 )
            goto LABEL_172;
LABEL_125:
          v10 = v68 + v66;
          if ( v10 >= v8 )
            RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
              v10,
              v8,
              &anon_01189c164b0c425bf67614ee34d1a89c_13_llvm_7541658972310832757);
          v71 = *(_DWORD *)(v61 + 4 * v10);
          if ( (_DWORD)v24 != v71 )
          {
            if ( v2 + 1 >= v29 )
              RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
                v2 + 1,
                v29,
                &anon_01189c164b0c425bf67614ee34d1a89c_10_llvm_7541658972310832757);
            v72 = *(_DWORD *)(v63 + 4 * v2 + 4);
            v122 = v24;
            v123 = v72;
            v124 = (void *)__PAIR64__(v72, v71);
            if ( !(unsigned int)EPATHOBJ_bPolyLineTo_0(v105, v108, &v122, 2) )
              goto LABEL_170;
          }
          if ( !v59 )
            goto LABEL_88;
          v51 = v59 - 1;
          v52 = *(_QWORD *)(v60 + 16);
          if ( v59 - 1 >= v52 )
            goto LABEL_197;
          v73 = *(int *)(*(_QWORD *)(v60 + 8) + 4 * v59 - 4);
          if ( v73 < 0 )
            goto LABEL_184;
          if ( v59 >= v73 + 4 )
          {
            v24 = v59 - v73 - 4;
            v57 = (unsigned __int8)RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalRINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanCs7vXzV21FY6F_8gdi_rust_llvm_7541658972310832757(
                                     v60,
                                     v24) == 0;
            v54 = 0;
            if ( !v57 )
              v54 = v60;
            if ( v10 >= v99 )
LABEL_196:
              RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(v10, v99, &off_14001B0F0);
          }
          else
          {
LABEL_88:
            v54 = 0;
            if ( v10 >= v99 )
              goto LABEL_196;
          }
          *(_BYTE *)(v101 + v10) = 1;
          v2 = v59;
          v58 = v60;
          v55 = v68;
          v102 = v60;
          v109 = v59;
          if ( !v54 )
          {
            v2 = v59;
            v58 = v60;
            v109 = v59;
            v102 = v60;
            v55 = v68;
            goto LABEL_140;
          }
        }
        v20 = v104;
LABEL_139:
        v55 = v100;
        v58 = v106;
LABEL_140:
        v10 = *(_QWORD *)(v113 + 16);
        v74 = *(_QWORD *)(v58 + 16);
        if ( v10 != v74
          || (v75 = *(int **)(v58 + 8),
              v76 = v58,
              v77 = v55,
              v78 = memcmp(*(const void **)(v113 + 8), v75, 4 * v10),
              v58 = v76,
              v55 = v77,
              v78)
          || v115 != v2
          || v112 != v77 - 1 )
        {
          if ( v2 >= v74 )
            RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
              v2,
              v74,
              &anon_01189c164b0c425bf67614ee34d1a89c_1_llvm_7541658972310832757);
          v79 = *(_QWORD *)(v58 + 8);
          v80 = *(int *)(v79 + 4 * v2);
          if ( v55 >= v80 )
            goto LABEL_172;
          v81 = v58;
          v82 = v2 + v55 + 3;
          if ( v82 >= v74 )
            RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
              v82,
              v74,
              &anon_01189c164b0c425bf67614ee34d1a89c_13_llvm_7541658972310832757);
          v59 = v109;
          if ( v2 + 1 >= v74 )
            RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
              v2 + 1,
              v74,
              &anon_01189c164b0c425bf67614ee34d1a89c_10_llvm_7541658972310832757);
          v83 = v55 + v103;
          if ( v55 + v103 >= v80 )
            goto LABEL_172;
          v84 = v83 + v2 + 3;
          if ( v84 >= v74 )
            RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
              v83 + v2 + 3,
              v74,
              &anon_01189c164b0c425bf67614ee34d1a89c_13_llvm_7541658972310832757);
          v85 = v55 + v103;
          v86 = *(_DWORD *)(v79 + 4 * v2 + 4);
          v87 = *(_DWORD *)(v79 + 4 * v84);
          v122 = *(_DWORD *)(v79 + 4 * v82);
          v123 = v86;
          v124 = (void *)__PAIR64__(v86, v87);
          if ( (unsigned int)EPATHOBJ_bPolyLineTo_0(v105, v108, &v122, 2) )
          {
            v88 = v102;
            v8 = *(_QWORD *)(v102 + 16);
            if ( v109 >= v8 )
LABEL_192:
              RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
                v59,
                v8,
                &anon_01189c164b0c425bf67614ee34d1a89c_1_llvm_7541658972310832757);
            v17 = v109 + *(int *)(*(_QWORD *)(v102 + 8) + 4 * v109) + 4;
            v89 = RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalRINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanCs7vXzV21FY6F_8gdi_rust_llvm_7541658972310832757(
                    v102,
                    v17);
            v56 = v109 + v85 + 3;
            if ( v56 < v99 )
            {
              v24 = v85;
              *(_BYTE *)(v101 + v56) = 1;
              v22 = 0;
              if ( v89 )
                v22 = v88;
              v23 = v88;
              v25 = 1;
              v21 = v81;
              if ( !v22 )
                continue;
LABEL_20:
              while ( 2 )
              {
                v102 = v23;
                v26 = v17;
                v8 = *(_QWORD *)(v22 + 16);
                if ( v17 >= v8 )
                  goto LABEL_188;
                v27 = *(_QWORD *)(v22 + 8);
                v28 = *(int *)(v27 + 4 * v17);
                if ( *(_DWORD *)(v27 + 4 * v17) )
                {
                  v29 = *(_QWORD *)(v21 + 16);
                  if ( v2 >= v29 )
LABEL_189:
                    RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
                      v2,
                      v29,
                      &anon_01189c164b0c425bf67614ee34d1a89c_1_llvm_7541658972310832757);
                  v30 = *(_QWORD *)(v21 + 8);
                  v31 = *(int *)(v30 + 4 * v2);
                  if ( v24 >= v31 )
                    goto LABEL_172;
                  v106 = v21;
                  v32 = v24 + v2 + 3;
                  if ( v32 >= v29 )
LABEL_190:
                    RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
                      v32,
                      v29,
                      &anon_01189c164b0c425bf67614ee34d1a89c_13_llvm_7541658972310832757);
                  if ( (unsigned int)v20 >= (unsigned int)v28 )
                    goto LABEL_172;
                  v33 = v17 + v117;
                  if ( v17 + v117 >= v8 )
                    goto LABEL_187;
                  v103 = v24;
                  v100 = v2 + v24;
                  v10 = *(unsigned int *)(v30 + 4 * (v2 + v24) + 12);
                  v34 = v20;
                  if ( *(_DWORD *)(v27 + 4 * v33) > (int)v10 )
                    goto LABEL_38;
                  v34 = v116 + v28;
                  if ( !__CFADD__(v116, v28) )
                    goto LABEL_172;
                  v33 = v26 + v34 + 3;
                  if ( v33 >= v8 )
                    goto LABEL_187;
                  if ( *(_DWORD *)(v27 + 4 * v33) <= (int)v10 )
                  {
                    v43 = v99;
                    v20 = v104;
LABEL_65:
                    v25 = 1;
                  }
                  else
                  {
                    v35 = (v28 - 1) >> 1;
                    v36 = v104;
                    if ( v35 != v104 )
                    {
                      v37 = v26 + 3;
                      while ( v35 < v28 )
                      {
                        v33 = v37 + v35;
                        if ( v37 + v35 >= v8 )
                          goto LABEL_187;
                        if ( *(_DWORD *)(v27 + 4 * v33) <= (int)v10 )
                        {
                          v36 = v35;
                          v35 = (v35 + v34) >> 1;
                          if ( v35 == v36 )
                            goto LABEL_38;
                        }
                        else
                        {
                          v34 = v35;
                          v35 = (v36 + v35) >> 1;
                          if ( v35 == v36 )
                            goto LABEL_38;
                        }
                      }
LABEL_172:
                      RNvNtCs9MWeMO1rkJG_4core9panicking5panic(
                        anon_01189c164b0c425bf67614ee34d1a89c_11_llvm_7541658972310832757,
                        43,
                        &anon_01189c164b0c425bf67614ee34d1a89c_12_llvm_7541658972310832757);
                    }
LABEL_38:
                    v20 = v104;
                    if ( (v34 & 1) == (_DWORD)v104 )
                    {
                      if ( v34 >= v28 )
                        goto LABEL_172;
                      v33 = v26 + v34 + 3;
                      if ( v33 < v8 )
                      {
                        if ( v103 + 1 >= v31 )
                          goto LABEL_172;
                        v38 = v100 + 4;
                        if ( v100 + 4 < v29 )
                        {
                          if ( *(_DWORD *)(v27 + 4 * v33) >= *(_DWORD *)(v30 + 4 * v100 + 16) )
                          {
                            v43 = v99;
                            goto LABEL_65;
                          }
LABEL_51:
                          if ( v34 >= v28 )
                            goto LABEL_172;
LABEL_52:
                          v13 = v26 + v34 + 3;
                          if ( v13 < v8 )
                          {
                            v40 = *(_DWORD *)(v27 + 4 * v13);
                            if ( (_DWORD)v10 == v40 )
                              goto LABEL_57;
                            if ( v2 + 2 >= v29 )
                              RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
                                v2 + 2,
                                v29,
                                &anon_01189c164b0c425bf67614ee34d1a89c_15_llvm_7541658972310832757);
                            v41 = *(_DWORD *)(v30 + 4 * v2 + 8);
                            v122 = v10;
                            v123 = v41;
                            v124 = (void *)__PAIR64__(v41, v40);
                            if ( (unsigned int)EPATHOBJ_bPolyLineTo_0(v105, v108, &v122, 2) )
                            {
                              v8 = *(_QWORD *)(v22 + 16);
LABEL_57:
                              if ( v26 < v8 )
                              {
                                v17 = v26 + *(int *)(*(_QWORD *)(v22 + 8) + 4 * v26) + 4;
                                v42 = RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalRINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanCs7vXzV21FY6F_8gdi_rust_llvm_7541658972310832757(
                                        v22,
                                        v17);
                                if ( v13 >= v99 )
                                  RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
                                    v26 + v34 + 3,
                                    v99,
                                    &off_14001B0F0);
                                *(_BYTE *)(v101 + v13) = 1;
                                v2 = v26;
                                v21 = v22;
                                v24 = v34;
                                v23 = v22;
                                v109 = v26;
                                v25 = 1;
                                if ( v42 )
                                  continue;
                                v2 = v26;
                                v21 = v22;
                                v109 = v26;
                                v23 = v22;
                                v24 = v34;
                                v43 = v99;
                                goto LABEL_70;
                              }
LABEL_188:
                              RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
                                v26,
                                v8,
                                &anon_01189c164b0c425bf67614ee34d1a89c_1_llvm_7541658972310832757);
                            }
LABEL_170:
                            v5 = v110;
                            if ( !v110 )
                            {
LABEL_176:
                              v96 = v107;
                              goto LABEL_177;
                            }
LABEL_175:
                            RNvCskrXTfrW5pjd_7___rustc14___rust_dealloc(v101, v5, 1);
                            goto LABEL_176;
                          }
LABEL_193:
                          RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
                            v13,
                            v8,
                            &anon_01189c164b0c425bf67614ee34d1a89c_13_llvm_7541658972310832757);
                        }
LABEL_191:
                        RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
                          v38,
                          v29,
                          &anon_01189c164b0c425bf67614ee34d1a89c_13_llvm_7541658972310832757);
                      }
LABEL_187:
                      RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
                        v33,
                        v8,
                        &anon_01189c164b0c425bf67614ee34d1a89c_13_llvm_7541658972310832757);
                    }
                    v39 = v34 - 1;
                    if ( !v103 )
                    {
                      --v34;
                      if ( v39 >= v28 )
                        goto LABEL_172;
                      goto LABEL_52;
                    }
                    if ( v39 >= v28 )
                      goto LABEL_172;
                    v33 = v26 + v34 + 2;
                    if ( v33 >= v8 )
                      goto LABEL_187;
                    if ( v103 - 1 >= v31 )
                      goto LABEL_172;
                    v38 = v100 + 2;
                    if ( v100 + 2 >= v29 )
                      goto LABEL_191;
                    --v34;
                    if ( *(_DWORD *)(v27 + 4 * v33) >= *(_DWORD *)(v30 + 4 * v100 + 8) )
                      goto LABEL_51;
                    v25 = -1;
                    v43 = v99;
                  }
                  v24 = v103;
                  v21 = v106;
                }
                else
                {
                  v43 = v99;
                  v25 = 1;
                }
                break;
              }
              v23 = v102;
              goto LABEL_70;
            }
LABEL_201:
            RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(v56, v99, &off_14001B0F0);
          }
          v5 = v110;
LABEL_174:
          if ( !v5 )
            goto LABEL_176;
          goto LABEL_175;
        }
        break;
      }
      v2 = v115;
      if ( v115 >= v10 )
        goto LABEL_210;
      v90 = v77 < v75[v115];
      v5 = v110;
      v4 = v99;
      if ( !v90 )
        goto LABEL_172;
      v91 = v114 + v55;
      if ( v91 >= v10 )
        RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
          v91,
          v10,
          &anon_01189c164b0c425bf67614ee34d1a89c_13_llvm_7541658972310832757);
      if ( v111 >= v10 )
        RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
          v111,
          v10,
          &anon_01189c164b0c425bf67614ee34d1a89c_10_llvm_7541658972310832757);
      v92 = v75[v115 + 1];
      v122 = v75[v91];
      v123 = v92;
      if ( !(unsigned int)EPATHOBJ_bPolyLineTo_0(v105, v108, &v122, 1) )
        goto LABEL_174;
      v93 = *(_QWORD *)(v105 + 8);
      if ( !v93 )
      {
        v107 = 87;
        if ( !v110 )
          goto LABEL_176;
        goto LABEL_175;
      }
      *(_BYTE *)(v93 + 72) |= 1u;
      v94 = *(_QWORD *)(v93 + 40);
      v6 = v113;
      v10 = v119;
      v11 = v114;
      if ( v94 )
      {
        v95 = *(_DWORD *)(v94 + 16);
        if ( (v95 & 8) == 0 )
        {
          *(_DWORD *)(v94 + 16) = v95 | 8;
          ++*(_DWORD *)(v105 + 4);
        }
      }
LABEL_9:
      v12 = v112 + 1;
    }
    while ( v112 + 1 != v10 );
    v8 = *(_QWORD *)(v6 + 16);
LABEL_166:
    if ( v2 >= v8 )
      goto LABEL_200;
    v2 += *(int *)(*(_QWORD *)(v6 + 8) + 4 * v2) + 4LL;
  }
  while ( (unsigned __int8)RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalRINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanCs7vXzV21FY6F_8gdi_rust_llvm_7541658972310832757(
                             v6,
                             v2) );
  v96 = 0;
  if ( v5 )
    RNvCskrXTfrW5pjd_7___rustc14___rust_dealloc(v101, v5, 1);
LABEL_177:
  if ( _security_cookie != ((unsigned __int64)&v98 ^ v125) )
LABEL_210:
    RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
      v2,
      v10,
      &anon_01189c164b0c425bf67614ee34d1a89c_1_llvm_7541658972310832757);
  return v96;
}

```

## disassembly

```asm
0x140003860  push    r15
0x140003862  push    r14
0x140003864  push    r13
0x140003866  push    r12
0x140003868  push    rsi
0x140003869  push    rdi
0x14000386a  push    rbp
0x14000386b  push    rbx
0x14000386c  sub     rsp, 108h
0x140003873  mov     rsi, rdx
0x140003876  mov     rax, cs:__security_cookie
0x14000387d  xor     rax, rsp
0x140003880  mov     [rsp+148h+var_48], rax
0x140003888  mov     r12, [rcx+10h]
0x14000388c  test    r12, r12
0x14000388f  jnz     loc_1400045A3
0x140003895  mov     eax, 1
0x14000389a  mov     [rsp+148h+var_108], rax
0x14000389f  xor     ebx, ebx
0x1400038a1  call    _RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore10first_scan
0x1400038a6  mov     r15, rax
0x1400038a9  mov     r14, rdx
0x1400038ac  mov     rax, [rsi]
0x1400038af  mov     [rsp+148h+var_E8], rax
0x1400038b4  mov     rax, [rsi+8]
0x1400038b8  mov     [rsp+148h+var_D0], rax
0x1400038bd  mov     [rsp+148h+var_118], r12
0x1400038c2  mov     rdx, [r15+10h]
0x1400038c6  cmp     r14, rdx
0x1400038c9  jnb     loc_14000471C
0x1400038cf  mov     rax, [r15+8]
0x1400038d3  movsxd  rdi, dword ptr [rax+r14*4]
0x1400038d7  test    rdi, rdi
0x1400038da  jz      loc_1400044E0
0x1400038e0  lea     rdx, [r14+3]
0x1400038e4  lea     rax, [r14+1]
0x1400038e8  mov     [rsp+148h+var_B8], rax
0x1400038f0  lea     rax, [r14+4]
0x1400038f4  mov     [rsp+148h+var_70], rax
0x1400038fc  xor     eax, eax
0x1400038fe  mov     [rsp+148h+var_B0], rax
0x140003906  lea     rsi, [rdx+rax]
0x14000390a  cmp     rsi, r12
0x14000390d  jnb     loc_14000479F
0x140003913  mov     rax, [rsp+148h+var_108]
0x140003918  cmp     byte ptr [rax+rsi], 0
0x14000391c  jz      short loc_140003940
0x14000391e  mov     rax, [rsp+148h+var_B0]
0x140003926  inc     rax
0x140003929  cmp     rax, rdi
0x14000392c  jnz     short loc_1400038FE
0x14000392e  jmp     loc_1400044DC
0x140003940  mov     [rsp+148h+var_A0], rdx
0x140003948  mov     rdx, [r15+10h]
0x14000394c  cmp     r14, rdx
0x14000394f  jnb     loc_14000471C
0x140003955  mov     rax, [r15+8]
0x140003959  movsxd  rcx, dword ptr [rax+r14*4]
0x14000395d  cmp     [rsp+148h+var_B0], rcx
0x140003965  jnb     loc_140004536
0x14000396b  cmp     rsi, rdx
0x14000396e  jnb     loc_1400046AC
0x140003974  cmp     [rsp+148h+var_B8], rdx
0x14000397c  jnb     loc_1400047B1
0x140003982  mov     ecx, [rax+rsi*4]
0x140003985  mov     eax, [rax+r14*4+4]
0x14000398a  mov     [rsp+148h+var_60], ecx
0x140003991  mov     [rsp+148h+var_5C], eax
0x140003998  mov     rcx, [rsp+148h+var_E8]
0x14000399d  mov     rdx, [rsp+148h+var_D0]
0x1400039a2  lea     r8, [rsp+148h+var_60]
0x1400039aa  call    EPATHOBJ_bMoveTo_0
0x1400039af  mov     [rsp+148h+var_D4], 1Fh
0x1400039b7  test    eax, eax
0x1400039b9  jz      loc_140004556
0x1400039bf  mov     [rsp+148h+var_78], rdi
0x1400039c7  mov     [rsp+148h+var_C0], rbx
0x1400039cf  mov     rdx, [r15+10h]
0x1400039d3  cmp     r14, rdx
0x1400039d6  jnb     loc_14000471C
0x1400039dc  mov     rax, [r15+8]
0x1400039e0  movsxd  rdi, dword ptr [rax+r14*4]
0x1400039e4  add     rdi, [rsp+148h+var_70]
0x1400039ec  mov     rcx, r15
0x1400039ef  mov     rdx, rdi
0x1400039f2  call    _RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalRINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanCs7vXzV21FY6F_8gdi_rust_llvm_7541658972310832757
0x1400039f7  mov     rdx, [rsp+148h+var_B0]
0x1400039ff  mov     r13d, edx
0x140003a02  and     r13d, 1
0x140003a06  mov     rcx, [rsp+148h+var_108]
0x140003a0b  mov     byte ptr [rcx+rsi], 1
0x140003a0f  mov     rcx, r13
0x140003a12  not     rcx
0x140003a15  mov     [rsp+148h+var_90], rcx
0x140003a1d  lea     rcx, [r13+3]
0x140003a21  mov     [rsp+148h+var_88], rcx
0x140003a29  test    al, al
0x140003a2b  mov     rcx, r15
0x140003a2e  mov     r15d, 0
0x140003a34  cmovnz  r15, rcx
0x140003a38  mov     rbp, rcx
0x140003a3b  mov     [rsp+148h+var_98], r14
0x140003a43  mov     [rsp+148h+var_C8], r14
0x140003a4b  mov     [rsp+148h+var_A8], rcx
0x140003a53  mov     r11, rcx
0x140003a56  mov     rsi, rdx
0x140003a59  mov     [rsp+148h+var_F0], r13
0x140003a5e  mov     r10d, 1
0x140003a64  mov     rcx, rbp
0x140003a67  test    r15, r15
0x140003a6a  jz      loc_140003D95
0x140003a70  mov     [rsp+148h+var_100], r11
0x140003a75  mov     r12, rdi
0x140003a78  mov     rdx, [r15+10h]
0x140003a7c  cmp     rdi, rdx
0x140003a7f  jnb     loc_14000465B
0x140003a85  mov     r10, [r15+8]
0x140003a89  movsxd  r11, dword ptr [r10+r12*4]
0x140003a8d  test    r11, r11
0x140003a90  jz      loc_140003D37
0x140003a96  mov     rax, [rcx+10h]
0x140003a9a  cmp     r14, rax
0x140003a9d  jnb     loc_14000466A
0x140003aa3  mov     r8, [rcx+8]
0x140003aa7  movsxd  r9, dword ptr [r8+r14*4]
0x140003aab  cmp     rsi, r9
0x140003aae  jnb     loc_140004536
0x140003ab4  mov     [rsp+148h+var_E0], rcx
0x140003ab9  lea     rcx, [rsi+r14]
0x140003abd  add     rcx, 3
0x140003ac1  cmp     rcx, rax
0x140003ac4  jnb     loc_14000467C
0x140003aca  cmp     r13d, r11d
0x140003acd  jnb     loc_140004536
0x140003ad3  mov     rcx, [rsp+148h+var_88]
0x140003adb  add     rcx, r12
0x140003ade  cmp     rcx, rdx
0x140003ae1  jnb     loc_14000464F
0x140003ae7  mov     [rsp+148h+var_F8], rsi
0x140003aec  add     rsi, r14
0x140003aef  mov     [rsp+148h+var_110], rsi
0x140003af4  mov     edi, [r8+rsi*4+0Ch]
0x140003af9  mov     rbp, r13
0x140003afc  cmp     [r10+rcx*4], edi
0x140003b00  jg      loc_140003B90
0x140003b06  mov     rbp, r11
0x140003b09  add     rbp, [rsp+148h+var_90]
0x140003b11  jnb     loc_140004536
0x140003b17  lea     rcx, [r12+rbp]
0x140003b1b  add     rcx, 3
0x140003b1f  cmp     rcx, rdx
0x140003b22  jnb     loc_14000464F
0x140003b28  cmp     [r10+rcx*4], edi
0x140003b2c  jle     loc_140003D5F
0x140003b32  lea     r13, [r11-1]
0x140003b36  shr     r13, 1
0x140003b39  mov     rsi, [rsp+148h+var_F0]
0x140003b3e  cmp     r13, rsi
0x140003b41  jz      short loc_140003B90
0x140003b43  lea     rbx, [r12+3]
0x140003b48  jmp     short loc_140003B5F
0x140003b50  mov     rsi, r13
0x140003b53  lea     r13, [rsi+rbp]
0x140003b57  shr     r13, 1
0x140003b5a  cmp     r13, rsi
0x140003b5d  jz      short loc_140003B90
0x140003b5f  cmp     r13, r11
0x140003b62  jnb     loc_140004536
0x140003b68  lea     rcx, [rbx+r13]
0x140003b6c  cmp     rcx, rdx
0x140003b6f  jnb     loc_14000464F
0x140003b75  cmp     [r10+rcx*4], edi
0x140003b79  jle     short loc_140003B50
0x140003b7b  mov     rbp, r13
0x140003b7e  lea     r13, [rsi+rbp]
0x140003b82  shr     r13, 1
0x140003b85  cmp     r13, rsi
0x140003b88  jnz     short loc_140003B5F
0x140003b8a  nop     word ptr [rax+rax+00h]
0x140003b90  mov     ecx, ebp
0x140003b92  and     ecx, 1
0x140003b95  mov     r13, [rsp+148h+var_F0]
0x140003b9a  cmp     ecx, r13d
0x140003b9d  jnz     short loc_140003BF0
0x140003b9f  cmp     rbp, r11
0x140003ba2  jnb     loc_140004536
0x140003ba8  lea     rcx, [r12+rbp]
0x140003bac  add     rcx, 3
0x140003bb0  cmp     rcx, rdx
0x140003bb3  mov     rbx, [rsp+148h+var_110]
0x140003bb8  jnb     loc_14000464F
0x140003bbe  mov     rsi, [rsp+148h+var_F8]
0x140003bc3  inc     rsi
0x140003bc6  cmp     rsi, r9
0x140003bc9  jnb     loc_140004536
0x140003bcf  lea     r9, [rbx+4]
0x140003bd3  cmp     r9, rax
0x140003bd6  jnb     loc_14000468B
0x140003bdc  mov     ecx, [r10+rcx*4]
0x140003be0  cmp     ecx, [r8+rbx*4+10h]
0x140003be5  jl      short loc_140003C4F
0x140003be7  jmp     loc_140003D6B
0x140003bf0  lea     rsi, [rbp-1]
0x140003bf4  cmp     [rsp+148h+var_F8], 0
0x140003bfa  jz      loc_140003D26
0x140003c00  cmp     rsi, r11
0x140003c03  jnb     loc_140004536
0x140003c09  lea     rcx, [r12+rbp]
0x140003c0d  add     rcx, 2
0x140003c11  cmp     rcx, rdx
0x140003c14  jnb     loc_14000464F
0x140003c1a  mov     rbx, [rsp+148h+var_F8]
0x140003c1f  dec     rbx
0x140003c22  cmp     rbx, r9
0x140003c25  jnb     loc_140004536
0x140003c2b  mov     rbx, [rsp+148h+var_110]
0x140003c30  lea     r9, [rbx+2]
0x140003c34  cmp     r9, rax
0x140003c37  jnb     loc_14000468B
0x140003c3d  mov     ecx, [r10+rcx*4]
0x140003c41  mov     rbp, rsi
0x140003c44  cmp     ecx, [r8+rbx*4+8]
0x140003c49  jl      loc_140003D78
0x140003c4f  cmp     rbp, r11
0x140003c52  jnb     loc_140004536
0x140003c58  lea     rsi, [r12+rbp]
0x140003c5c  add     rsi, 3
0x140003c60  cmp     rsi, rdx
0x140003c63  jnb     loc_1400046AC
0x140003c69  mov     r9d, [r10+rsi*4]
0x140003c6d  cmp     edi, r9d
0x140003c70  jz      short loc_140003CCA
0x140003c72  lea     rcx, [r14+2]
0x140003c76  cmp     rcx, rax
0x140003c79  jnb     loc_1400046FE
0x140003c7f  mov     eax, [r8+r14*4+8]
0x140003c84  mov     [rsp+148h+var_60], edi
0x140003c8b  mov     [rsp+148h+var_5C], eax
0x140003c92  mov     dword ptr [rsp+148h+var_58], r9d
0x140003c9a  mov     dword ptr [rsp+148h+var_58+4], eax
0x140003ca1  mov     rcx, [rsp+148h+var_E8]
0x140003ca6  mov     rdx, [rsp+148h+var_D0]
0x140003cab  lea     r8, [rsp+148h+var_60]
0x140003cb3  mov     r9d, 2
0x140003cb9  call    EPATHOBJ_bPolyLineTo_0
0x140003cbe  test    eax, eax
0x140003cc0  jz      loc_140004527
0x140003cc6  mov     rdx, [r15+10h]
0x140003cca  cmp     r12, rdx
0x140003ccd  jnb     loc_14000465B
0x140003cd3  mov     rax, [r15+8]
0x140003cd7  movsxd  rax, dword ptr [rax+r12*4]
0x140003cdb  lea     rdi, [r12+rax]
0x140003cdf  add     rdi, 4
0x140003ce3  mov     rcx, r15
0x140003ce6  mov     rdx, rdi
0x140003ce9  call    _RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalRINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanCs7vXzV21FY6F_8gdi_rust_llvm_7541658972310832757
0x140003cee  cmp     rsi, [rsp+148h+var_118]
0x140003cf3  jnb     loc_1400046BB
0x140003cf9  mov     rcx, [rsp+148h+var_108]
0x140003cfe  mov     byte ptr [rcx+rsi], 1
0x140003d02  mov     r14, r12
0x140003d05  mov     rcx, r15
0x140003d08  mov     rsi, rbp
0x140003d0b  mov     r11, r15
0x140003d0e  mov     [rsp+148h+var_C8], r12
0x140003d16  test    al, al
0x140003d18  mov     r10d, 1
0x140003d1e  jnz     loc_140003A70
0x140003d24  jmp     short loc_140003D44
0x140003d26  mov     rbp, rsi
0x140003d29  cmp     rbp, r11
0x140003d2c  jb      loc_140003C58
0x140003d32  jmp     loc_140004536
0x140003d37  mov     rbp, [rsp+148h+var_118]
0x140003d3c  mov     r10d, 1
0x140003d42  jmp     short loc_140003D8E
0x140003d44  mov     r14, r12
0x140003d47  mov     rcx, r15
0x140003d4a  mov     [rsp+148h+var_C8], r12
0x140003d52  mov     r11, r15
0x140003d55  mov     rsi, rbp
0x140003d58  mov     rbp, [rsp+148h+var_118]
0x140003d5d  jmp     short loc_140003D9A
0x140003d5f  mov     rbp, [rsp+148h+var_118]
0x140003d64  mov     r13, [rsp+148h+var_F0]
0x140003d69  jmp     short loc_140003D70
0x140003d6b  mov     rbp, [rsp+148h+var_118]
0x140003d70  mov     r10d, 1
0x140003d76  jmp     short loc_140003D84
0x140003d78  mov     r10, 0FFFFFFFFFFFFFFFFh
0x140003d7f  mov     rbp, [rsp+148h+var_118]
0x140003d84  mov     rsi, [rsp+148h+var_F8]
0x140003d89  mov     rcx, [rsp+148h+var_E0]
0x140003d8e  mov     r11, [rsp+148h+var_100]
0x140003d93  jmp     short loc_140003D9A
0x140003d95  mov     rbp, [rsp+148h+var_118]
0x140003d9a  mov     rdx, [rcx+10h]
0x140003d9e  cmp     r14, rdx
0x140003da1  jnb     loc_14000471C
  ... truncated ...
```
