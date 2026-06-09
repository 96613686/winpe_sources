# _RNvMs_NtCsdcpJtfrLhSH_7rgncore5mergeNtB6_10RegionCore5merge

- ea: `0x14000e9d0`
- end: `0x14000f38c`
- name: `_RNvMs_NtCsdcpJtfrLhSH_7rgncore5mergeNtB6_10RegionCore5merge`
- size: `2492`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140004a90`
- `0x140004e40`
- `0x14000ca10`

## callees

- `0x14000b710`
- `0x14000e9d0`
- `0x14000fdc0`
- `0x1400120f0`
- `0x140012770`
- `0x140012f10`
- `0x140017a10`
- `0x140018450`
- `0x140018470`
- `0x1400184d7`
- `0x140018630`
- `0x140018650`
- `0x140018690`
- `0x1400193b0`

## pseudocode

```c
__int64 __fastcall RNvMs_NtCsdcpJtfrLhSH_7rgncore5mergeNtB6_10RegionCore5merge(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int8 a4)
{
  unsigned __int64 v4; // rbx
  __int64 v5; // r14
  __int64 v6; // rax
  unsigned __int64 v8; // r15
  __int64 v9; // r12
  __int64 v10; // rax
  char valid; // al
  __int64 v12; // rcx
  __int64 v13; // rdx
  unsigned __int64 v14; // rax
  unsigned int v15; // r13d
  unsigned __int64 v16; // rdi
  __int64 v17; // rcx
  uintptr_t v18; // rdi
  uintptr_t v19; // r13
  int v20; // r8d
  int v21; // ebp
  __int64 v22; // rdx
  uintptr_t v23; // rcx
  __int64 v24; // r8
  unsigned __int64 v25; // rdx
  uintptr_t v26; // rax
  __int64 v27; // r9
  unsigned __int64 v28; // rdx
  unsigned __int64 v29; // r15
  int *v30; // rsi
  int *v31; // rbp
  int *v32; // rbx
  int *v33; // r12
  unsigned __int8 v34; // r14
  unsigned __int8 v35; // r13
  _QWORD *v36; // rdi
  int *v37; // rax
  char *v38; // rcx
  bool v39; // zf
  __int64 v40; // rdx
  unsigned __int64 v41; // rdx
  int v42; // ecx
  __int64 v43; // r15
  unsigned __int64 v44; // rdx
  unsigned __int64 v45; // rax
  int *v46; // rdx
  unsigned __int64 v47; // r9
  const void *v48; // r8
  unsigned __int64 v49; // rax
  unsigned __int64 v50; // rbx
  int v51; // ebp
  __int64 v52; // rax
  uintptr_t v53; // rbx
  unsigned __int64 v54; // r8
  __int64 v55; // r9
  uintptr_t v56; // rcx
  int v57; // eax
  int v58; // eax
  __int64 v59; // rax
  unsigned __int64 v60; // rdx
  int v61; // eax
  int v62; // eax
  unsigned __int64 v63; // rax
  unsigned __int64 v65; // rcx
  __int64 v66; // [rsp+0h] [rbp-128h] BYREF
  unsigned __int8 v67; // [rsp+3Fh] [rbp-E9h]
  __int64 v68; // [rsp+40h] [rbp-E8h]
  __int64 v69; // [rsp+48h] [rbp-E0h]
  __int64 v70; // [rsp+50h] [rbp-D8h]
  __int64 v71; // [rsp+58h] [rbp-D0h]
  int *v72; // [rsp+60h] [rbp-C8h]
  int *v73; // [rsp+68h] [rbp-C0h]
  int v74; // [rsp+70h] [rbp-B8h]
  unsigned int v75; // [rsp+74h] [rbp-B4h]
  uintptr_t v76; // [rsp+78h] [rbp-B0h]
  __int64 v77; // [rsp+80h] [rbp-A8h]
  unsigned __int64 v78; // [rsp+88h] [rbp-A0h]
  unsigned __int64 v79; // [rsp+90h] [rbp-98h]
  __int64 v80; // [rsp+98h] [rbp-90h]
  unsigned __int64 v81; // [rsp+A0h] [rbp-88h]
  __int64 v82; // [rsp+A8h] [rbp-80h]
  uintptr_t v83; // [rsp+B0h] [rbp-78h]
  uintptr_t v84; // [rsp+B8h] [rbp-70h]
  char v85; // [rsp+C7h] [rbp-61h] BYREF
  _QWORD *v86; // [rsp+C8h] [rbp-60h] BYREF
  unsigned __int64 v87; // [rsp+D0h] [rbp-58h]
  unsigned __int64 v88; // [rsp+D8h] [rbp-50h]
  __int64 v89; // [rsp+E0h] [rbp-48h]

  v67 = a4;
  v4 = *(_QWORD *)(a2 + 16);
  if ( !v4 )
    goto LABEL_133;
  v5 = *(_QWORD *)(a2 + 8);
  v6 = *(int *)(v5 + 4 * v4 - 4);
  if ( v6 < 0 )
    goto LABEL_121;
  if ( v4 < v6 + 4
    || (v69 = a3,
        v68 = a2,
        !RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143(
           a2,
           v4 - v6 - 4))
    || (v8 = *(_QWORD *)(v69 + 16)) == 0 )
  {
LABEL_133:
    RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed(&anon_22b06d26984f22b1c5b0f9b994440758_15_llvm_8899961222222301143);
  }
  v9 = *(_QWORD *)(v69 + 8);
  v10 = *(int *)(v9 + 4 * v8 - 4);
  if ( v10 < 0 )
LABEL_121:
    RNvNtCs9MWeMO1rkJG_4core6result13unwrap_failed(
      (unsigned int)anon_22b06d26984f22b1c5b0f9b994440758_6_llvm_8899961222222301143,
      43,
      (unsigned int)&v85,
      (unsigned int)anon_22b06d26984f22b1c5b0f9b994440758_5_llvm_8899961222222301143,
      (__int64)&anon_22b06d26984f22b1c5b0f9b994440758_10_llvm_8899961222222301143);
  if ( v8 < v10 + 4 )
    goto LABEL_133;
  valid = RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143(
            v69,
            v8 - v10 - 4);
  v12 = v68;
  if ( !valid )
    goto LABEL_133;
  v13 = *(_QWORD *)a1;
  if ( *(_QWORD *)a1 <= 0x1Bu )
  {
    v14 = *(_QWORD *)(a1 + 16);
    if ( 28 - v14 > v13 - v14 )
    {
      v15 = 14;
      if ( v14 > 0x1C )
        goto LABEL_114;
      v16 = 28;
      if ( (unsigned __int64)(2 * v13) >= 0x1D )
        v16 = 2 * v13;
      RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
        (__int64 *)&v86,
        v13,
        *(const void **)(a1 + 8),
        v16,
        4u,
        4u);
      if ( (_DWORD)v86 == 1 )
        goto LABEL_114;
      *(_QWORD *)(a1 + 8) = v87;
      *(_QWORD *)a1 = v16;
      v12 = v68;
    }
  }
  *(_QWORD *)(a1 + 16) = 0;
  *(_OWORD *)(a1 + 24) = _xmm;
  *(_DWORD *)(a1 + 40) = 0x80000000;
  if ( !RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143(
          v12,
          0)
    || !RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143(
          v69,
          0) )
  {
    RNvNtCs9MWeMO1rkJG_4core9panicking5panic(
      &anon_22b06d26984f22b1c5b0f9b994440758_17_llvm_8899961222222301143,
      52,
      &anon_22b06d26984f22b1c5b0f9b994440758_18_llvm_8899961222222301143);
  }
  v17 = 1;
  v18 = 0;
  v19 = 0;
  v70 = a1;
  v76 = v4;
  v82 = v5;
  v81 = v8;
  v80 = v9;
  while ( 1 )
  {
    if ( v19 + 1 >= v8 )
      RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
        v19 + 1,
        v8,
        &anon_22b06d26984f22b1c5b0f9b994440758_11_llvm_8899961222222301143);
    v20 = *(_DWORD *)(v5 + 4 * v17);
    if ( *(_DWORD *)(v9 + 4 * v19 + 4) > v20 )
      v20 = *(_DWORD *)(v9 + 4 * v19 + 4);
    if ( v18 + 2 >= v4 )
      RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
        v18 + 2,
        v4,
        &anon_22b06d26984f22b1c5b0f9b994440758_19_llvm_8899961222222301143);
    if ( v19 + 2 >= v8 )
      RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
        v19 + 2,
        v8,
        &anon_22b06d26984f22b1c5b0f9b994440758_19_llvm_8899961222222301143);
    v21 = *(_DWORD *)(v5 + 4 * v18 + 8);
    if ( *(_DWORD *)(v9 + 4 * v19 + 8) < v21 )
      v21 = *(_DWORD *)(v9 + 4 * v19 + 8);
    if ( v18 >= v4 )
LABEL_134:
      RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
        v18,
        v4,
        &anon_22b06d26984f22b1c5b0f9b994440758_2_llvm_8899961222222301143);
    if ( v19 >= v8 )
      goto LABEL_135;
    RNvMs5_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE3new(
      (__int64)&v86,
      (unsigned __int64 *)a1,
      v20,
      v21,
      *(int *)(v5 + 4 * v18) + (__int64)*(int *)(v9 + 4 * v19));
    v77 = (unsigned int)v87;
    v71 = (__int64)v86;
    if ( !v86 )
    {
      LODWORD(v63) = v77;
      goto LABEL_112;
    }
    v23 = v18 + 3;
    v24 = *(int *)(v5 + 4 * v18);
    v25 = v24 + v18 + 3;
    if ( __CFADD__(v24, v18 + 3) || v25 > v4 )
      RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail(
        v23,
        v25,
        v4,
        &anon_22b06d26984f22b1c5b0f9b994440758_16_llvm_8899961222222301143);
    v26 = v19 + 3;
    v27 = *(int *)(v9 + 4 * v19);
    v28 = v27 + v19 + 3;
    if ( __CFADD__(v27, v19 + 3) || v28 > v8 )
      RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail(
        v26,
        v28,
        v8,
        &anon_22b06d26984f22b1c5b0f9b994440758_16_llvm_8899961222222301143);
    v74 = v21;
    v83 = v19;
    v84 = v18;
    v75 = HIDWORD(v87);
    v29 = v88;
    v30 = (int *)(v5 + 4 * v23);
    v72 = &v30[v24];
    v31 = (int *)(v9 + 4 * v26);
    v73 = &v31[v27];
    v32 = &v31[(_DWORD)v27 != 0];
    if ( !(_DWORD)v27 )
      v31 = 0;
    v33 = &v30[(_DWORD)v24 != 0];
    if ( !(_DWORD)v24 )
      v30 = 0;
    v34 = 1;
    v35 = v67;
    v36 = (_QWORD *)v71;
    v78 = v88;
    if ( v30 )
      break;
LABEL_67:
    if ( v31 )
    {
      if ( v34 >= 0x10u )
        RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(v34, 16, &off_14001B758);
      v38 = (char *)qword_14001CE70 + v34;
      v46 = &v32[v32 != v73];
      if ( v32 == v73 )
        v32 = 0;
      v37 = v31;
      v31 = v32;
      v32 = v46;
      v30 = 0;
      goto LABEL_40;
    }
    v86 = v36;
    v87 = __PAIR64__(v75, v77);
    v88 = v29;
    v49 = RNvMs4_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE18commit_or_coalesceB7_((__int64)&v86);
    if ( (v49 & 1) != 0 )
    {
      v63 = HIDWORD(v49);
      a1 = v70;
      goto LABEL_112;
    }
    a1 = v70;
    v50 = *(_QWORD *)(v70 + 16);
    v5 = v82;
    v8 = v81;
    v9 = v80;
    v18 = v84;
    v19 = v83;
    v51 = v74;
    if ( !v50 )
      goto LABEL_133;
    v52 = *(int *)(*(_QWORD *)(v70 + 8) + 4 * v50 - 4);
    if ( v52 < 0 )
      goto LABEL_121;
    if ( v50 < v52 + 4 )
      goto LABEL_133;
    v53 = v50 - v52 - 4;
    if ( !RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143(
            v70,
            v53) )
      goto LABEL_133;
    if ( v74 == 0x7FFFFFFF )
    {
      LODWORD(v63) = 0;
      goto LABEL_112;
    }
    v54 = *(_QWORD *)(v70 + 16);
    if ( v53 >= v54 )
      RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
        v53,
        *(_QWORD *)(v70 + 16),
        &anon_22b06d26984f22b1c5b0f9b994440758_2_llvm_8899961222222301143);
    v55 = *(_QWORD *)(v70 + 8);
    if ( *(_DWORD *)(v55 + 4 * v53) )
    {
      v56 = v53 + 3;
      if ( v53 + 3 >= v54 )
        RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
          v56,
          *(_QWORD *)(v70 + 16),
          &anon_22b06d26984f22b1c5b0f9b994440758_14_llvm_8899961222222301143);
      v57 = *(_DWORD *)(v55 + 4 * v56);
      if ( v57 < *(_DWORD *)(v70 + 28) )
        *(_DWORD *)(v70 + 28) = v57;
      if ( v53 + 1 >= v54 )
        RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
          v53 + 1,
          v54,
          &anon_22b06d26984f22b1c5b0f9b994440758_11_llvm_8899961222222301143);
      v58 = *(_DWORD *)(v55 + 4 * v53 + 4);
      if ( v58 < *(_DWORD *)(a1 + 32) )
        *(_DWORD *)(a1 + 32) = v58;
      v59 = *(int *)(v55 + 4 * v53);
      v60 = v59 + v56;
      if ( __CFADD__(v59, v56) || v60 > v54 )
        RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail(
          v56,
          v60,
          v54,
          &anon_22b06d26984f22b1c5b0f9b994440758_16_llvm_8899961222222301143);
      if ( !(_DWORD)v59 )
        RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed(&off_14001B770);
      v61 = *(_DWORD *)(v55 + 4 * v56 + 4 * v59 - 4);
      if ( v61 > *(_DWORD *)(a1 + 36) )
        *(_DWORD *)(a1 + 36) = v61;
      if ( v53 + 2 >= v54 )
        RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
          v53 + 2,
          v54,
          &anon_22b06d26984f22b1c5b0f9b994440758_19_llvm_8899961222222301143);
      v62 = *(_DWORD *)(v55 + 4 * v53 + 8);
      if ( v62 > *(_DWORD *)(a1 + 40) )
        *(_DWORD *)(a1 + 40) = v62;
    }
    if ( v51 != *(_DWORD *)(v5 + 4 * v18 + 8) )
    {
      v4 = v76;
      if ( v51 != *(_DWORD *)(v9 + 4 * v19 + 8) )
        goto LABEL_19;
LABEL_106:
      if ( v19 >= v8 )
LABEL_135:
        RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
          v19,
          v8,
          &anon_22b06d26984f22b1c5b0f9b994440758_2_llvm_8899961222222301143);
      v19 += *(int *)(v9 + 4 * v19) + 4LL;
      if ( !RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143(
              v69,
              v19) )
        RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt(qword_14001CE90, 57, &off_14001B788);
      goto LABEL_19;
    }
    v4 = v76;
    if ( v18 >= v76 )
      goto LABEL_134;
    v18 += *(int *)(v5 + 4 * v18) + 4LL;
    if ( !RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143(
            v68,
            v18) )
      RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt(qword_14001CE90, 57, &off_14001B7A0);
    if ( v51 == *(_DWORD *)(v9 + 4 * v19 + 8) )
      goto LABEL_106;
LABEL_19:
    v17 = v18 + 1;
    if ( v18 + 1 >= v4 )
      RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
        v17,
        v4,
        &anon_22b06d26984f22b1c5b0f9b994440758_11_llvm_8899961222222301143);
  }
  while ( 1 )
  {
LABEL_42:
    v37 = v30;
    if ( v31 )
    {
      if ( *v30 >= *v31 )
      {
        if ( *v30 <= *v31 )
        {
          if ( v34 >= 0x10u )
            RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(v34, 16, &off_14001B6F8);
          v38 = &byte_14001CE4B[v34];
          v39 = v33 == v72;
          v30 = v33;
          v33 += v33 != v72;
          if ( v39 )
            v30 = 0;
          v39 = v32 == v73;
          v31 = v32;
          v32 += v32 != v73;
          if ( v39 )
            v31 = 0;
        }
        else
        {
          if ( v34 >= 0x10u )
            RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(v34, 16, &off_14001B710);
          v38 = (char *)qword_14001CE70 + v34;
          v40 = 0;
          v37 = v31;
          v31 = 0;
          if ( v32 != v73 )
            v31 = v32;
          LOBYTE(v40) = v32 != v73;
          v32 += v40;
        }
      }
      else
      {
        if ( v34 >= 0x10u )
          RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(v34, 16, &off_14001B728);
        v38 = (char *)qword_14001CE80 + v34;
        v30 = 0;
        if ( v33 != v72 )
          v30 = v33;
        v33 += v33 != v72;
      }
    }
    else
    {
      if ( v34 >= 0x10u )
        RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(v34, 16, &off_14001B740);
      v38 = (char *)qword_14001CE80 + v34;
      v39 = v33 == v72;
      v30 = v33;
      v33 += v33 != v72;
      if ( v39 )
        v30 = 0;
      v31 = 0;
    }
LABEL_40:
    v34 = *v38;
    if ( (v35 & (unsigned __int8)*v38) != 0 )
      break;
    if ( !v30 )
      goto LABEL_67;
  }
  v41 = v36[2];
  if ( v29 >= v41 )
    RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(
      v29,
      v41,
      &anon_22b06d26984f22b1c5b0f9b994440758_37_llvm_8899961222222301143);
  v42 = *v37;
  ++*(_DWORD *)(v36[1] + 4 * v29);
  v43 = v36[2];
  v44 = v43 + 1;
  if ( *v36 != v43 )
  {
    v45 = v36[1];
    goto LABEL_66;
  }
  LODWORD(v71) = v42;
  v47 = 2 * v43;
  if ( v44 > 2 * v43 )
    v47 = v43 + 1;
  if ( v47 < 5 )
    v47 = 4;
  v48 = (const void *)v36[1];
  v79 = v47;
  RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
    (__int64 *)&v86,
    v43,
    v48,
    v47,
    4u,
    4u);
  if ( !(_BYTE)v86 )
  {
    v45 = v87;
    v36[1] = v87;
    *v36 = v79;
    v42 = v71;
    v44 = v43 + 1;
LABEL_66:
    *(_DWORD *)(v45 + 4 * v43) = v42;
    v36[2] = v44;
    v35 ^= 0xFu;
    v29 = v78;
    if ( !v30 )
      goto LABEL_67;
    goto LABEL_42;
  }
  v65 = v78;
  if ( v78 > v36[2] )
    RNvNtCs9MWeMO1rkJG_4core9panicking5panic(
      "assertion failed: index <= scan_data.len()assertion failed: ScanInternal::is_valid_scan(&&*self.scan_data, previou"
      "s_index)TryFromIntErrorseh_unwind\\src\\lib.rs",
      42,
      &anon_22b06d26984f22b1c5b0f9b994440758_44_llvm_8899961222222301143);
  v36[2] = v78;
  LODWORD(v63) = 14;
  a1 = v70;
  if ( !v65 )
  {
    RNvNtCsdwtLm5uWta6_10gdi_region3ffi27RustOnZeroSizedScanCallback();
    LODWORD(v63) = 14;
  }
LABEL_112:
  v15 = v63;
  if ( !*(_QWORD *)(a1 + 16) )
    RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore16set_to_null_scan(a1, v22);
LABEL_114:
  if ( _security_cookie != ((unsigned __int64)&v66 ^ v89) )
    JUMPOUT(0x14000F38BLL);
  return v15;
}

```

## disassembly

```asm
0x14000e9d0  push    r15
0x14000e9d2  push    r14
0x14000e9d4  push    r13
0x14000e9d6  push    r12
0x14000e9d8  push    rsi
0x14000e9d9  push    rdi
0x14000e9da  push    rbp
0x14000e9db  push    rbx
0x14000e9dc  sub     rsp, 0E8h
0x14000e9e3  mov     [rsp+128h+var_E9], r9b
0x14000e9e8  mov     rax, cs:__security_cookie
0x14000e9ef  xor     rax, rsp
0x14000e9f2  mov     [rsp+128h+var_48], rax
0x14000e9fa  mov     rbx, [rdx+10h]
0x14000e9fe  test    rbx, rbx
0x14000ea01  jz      loc_14000F2BE
0x14000ea07  mov     r9, rdx
0x14000ea0a  mov     r14, [rdx+8]
0x14000ea0e  movsxd  rax, dword ptr [r14+rbx*4-4]
0x14000ea13  test    rax, rax
0x14000ea16  js      loc_14000F1CE
0x14000ea1c  mov     rsi, rcx
0x14000ea1f  lea     rcx, [rax+4]
0x14000ea23  cmp     rbx, rcx
0x14000ea26  jb      loc_14000F2BE
0x14000ea2c  mov     rdx, rbx
0x14000ea2f  sub     rdx, rax
0x14000ea32  add     rdx, 0FFFFFFFFFFFFFFFCh
0x14000ea36  mov     rcx, r9
0x14000ea39  mov     [rsp+128h+var_E0], r8
0x14000ea3e  mov     [rsp+128h+var_E8], r9
0x14000ea43  call    _RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143
0x14000ea48  mov     rcx, [rsp+128h+var_E0]
0x14000ea4d  test    al, al
0x14000ea4f  jz      loc_14000F2BE
0x14000ea55  mov     r15, [rcx+10h]
0x14000ea59  test    r15, r15
0x14000ea5c  jz      loc_14000F2BE
0x14000ea62  mov     r12, [rcx+8]
0x14000ea66  movsxd  rax, dword ptr [r12+r15*4-4]
0x14000ea6b  test    rax, rax
0x14000ea6e  js      loc_14000F1CE
0x14000ea74  lea     rdx, [rax+4]
0x14000ea78  cmp     r15, rdx
0x14000ea7b  jb      loc_14000F2BE
0x14000ea81  mov     rdx, r15
0x14000ea84  sub     rdx, rax
0x14000ea87  add     rdx, 0FFFFFFFFFFFFFFFCh
0x14000ea8b  call    _RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143
0x14000ea90  mov     rcx, [rsp+128h+var_E8]
0x14000ea95  test    al, al
0x14000ea97  jz      loc_14000F2BE
0x14000ea9d  mov     rdx, [rsi]
0x14000eaa0  cmp     rdx, 1Bh
0x14000eaa4  ja      loc_14000EB2B
0x14000eaaa  mov     rax, [rsi+10h]
0x14000eaae  mov     r9d, 1Ch
0x14000eab4  sub     r9, rax
0x14000eab7  mov     r8, rdx
0x14000eaba  sub     r8, rax
0x14000eabd  cmp     r9, r8
0x14000eac0  jbe     short loc_14000EB2B
0x14000eac2  mov     r13d, 0Eh
0x14000eac8  cmp     rax, 1Ch
0x14000eacc  ja      loc_14000F14A
0x14000ead2  lea     rax, [rdx+rdx]
0x14000ead6  cmp     rax, 1Dh
0x14000eada  mov     edi, 1Ch
0x14000eadf  cmovnb  rdi, rax
0x14000eae3  mov     r8, [rsi+8]
0x14000eae7  mov     [rsp+128h+var_100], 4
0x14000eaf0  mov     [rsp+128h+var_108], 4
0x14000eaf9  lea     rcx, [rsp+128h+var_60]
0x14000eb01  mov     r9, rdi
0x14000eb04  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244
0x14000eb09  cmp     dword ptr [rsp+128h+var_60], 1
0x14000eb11  jz      loc_14000F14A
0x14000eb17  mov     rax, [rsp+128h+var_58]
0x14000eb1f  mov     [rsi+8], rax
0x14000eb23  mov     [rsi], rdi
0x14000eb26  mov     rcx, [rsp+128h+var_E8]
0x14000eb2b  mov     qword ptr [rsi+10h], 0
0x14000eb33  movaps  xmm0, cs:__xmm@800000007fffffff7fffffff00000000
0x14000eb3a  movups  xmmword ptr [rsi+18h], xmm0
0x14000eb3e  mov     dword ptr [rsi+28h], 80000000h
0x14000eb45  xor     edx, edx
0x14000eb47  call    _RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143
0x14000eb4c  test    al, al
0x14000eb4e  jz      loc_14000F22A
0x14000eb54  mov     rcx, [rsp+128h+var_E0]
0x14000eb59  xor     edx, edx
0x14000eb5b  call    _RNvMNtCsdcpJtfrLhSH_7rgncore4scanINtB2_12ScanInternalQINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEB1o_E13is_valid_scanB4__llvm_8899961222222301143
0x14000eb60  test    al, al
0x14000eb62  jz      loc_14000F22A
0x14000eb68  mov     ecx, 1
0x14000eb6d  xor     edi, edi
0x14000eb6f  xor     r13d, r13d
0x14000eb72  mov     [rsp+128h+var_D8], rsi
0x14000eb77  mov     [rsp+128h+var_B0], rbx
0x14000eb7c  mov     [rsp+128h+var_80], r14
0x14000eb84  mov     [rsp+128h+var_88], r15
0x14000eb8c  mov     [rsp+128h+var_90], r12
0x14000eb94  jmp     short loc_14000EBAD
0x14000eba0  lea     rcx, [rdi+1]
0x14000eba4  cmp     rcx, rbx
0x14000eba7  jnb     loc_14000F333
0x14000ebad  lea     rax, [r13+1]
0x14000ebb1  cmp     rax, r15
0x14000ebb4  jnb     loc_14000F30C
0x14000ebba  mov     r8d, [r14+rcx*4]
0x14000ebbe  mov     eax, [r12+r13*4+4]
0x14000ebc3  cmp     eax, r8d
0x14000ebc6  cmovg   r8d, eax
0x14000ebca  lea     rcx, [rdi+2]
0x14000ebce  cmp     rcx, rbx
0x14000ebd1  jnb     loc_14000F2EE
0x14000ebd7  lea     rcx, [r13+2]
0x14000ebdb  cmp     rcx, r15
0x14000ebde  jnb     loc_14000F2FD
0x14000ebe4  mov     ebp, [r14+rdi*4+8]
0x14000ebe9  mov     eax, [r12+r13*4+8]
0x14000ebee  cmp     eax, ebp
0x14000ebf0  cmovl   ebp, eax
0x14000ebf3  cmp     rdi, rbx
0x14000ebf6  jnb     loc_14000F2CA
0x14000ebfc  cmp     r13, r15
0x14000ebff  jnb     loc_14000F2DC
0x14000ec05  movsxd  rax, dword ptr [r14+rdi*4]
0x14000ec09  movsxd  rcx, dword ptr [r12+r13*4]
0x14000ec0d  add     rcx, rax
0x14000ec10  mov     [rsp+128h+var_108], rcx
0x14000ec15  lea     rcx, [rsp+128h+var_60]
0x14000ec1d  mov     rdx, rsi
0x14000ec20  mov     r9d, ebp
0x14000ec23  call    _RNvMs5_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE3new
0x14000ec28  mov     rcx, [rsp+128h+var_60]
0x14000ec30  mov     eax, dword ptr [rsp+128h+var_58]
0x14000ec37  mov     [rsp+128h+var_A8], rax
0x14000ec3f  mov     [rsp+128h+var_D0], rcx
0x14000ec44  test    rcx, rcx
0x14000ec47  jz      loc_14000F121
0x14000ec4d  lea     rcx, [rdi+3]
0x14000ec51  movsxd  r8, dword ptr [r14+rdi*4]
0x14000ec55  mov     rdx, rcx
0x14000ec58  add     rdx, r8
0x14000ec5b  jb      loc_14000F1AD
0x14000ec61  cmp     rdx, rbx
0x14000ec64  ja      loc_14000F1AD
0x14000ec6a  lea     rax, [r13+3]
0x14000ec6e  movsxd  r9, dword ptr [r12+r13*4]
0x14000ec72  mov     rdx, rax
0x14000ec75  add     rdx, r9
0x14000ec78  jb      loc_14000F1BC
0x14000ec7e  cmp     rdx, r15
0x14000ec81  ja      loc_14000F1BC
0x14000ec87  mov     [rsp+128h+var_B8], ebp
0x14000ec8b  mov     [rsp+128h+var_78], r13
0x14000ec93  mov     [rsp+128h+var_70], rdi
0x14000ec9b  mov     edx, dword ptr [rsp+128h+var_58+4]
0x14000eca2  mov     [rsp+128h+var_B4], edx
0x14000eca6  mov     r15, [rsp+128h+var_50]
0x14000ecae  lea     rsi, [r14+rcx*4]
0x14000ecb2  lea     rcx, [rsi+r8*4]
0x14000ecb6  mov     [rsp+128h+var_C8], rcx
0x14000ecbb  xor     ecx, ecx
0x14000ecbd  test    r9d, r9d
0x14000ecc0  setnz   cl
0x14000ecc3  lea     rbp, [r12+rax*4]
0x14000ecc7  lea     rax, [rbp+r9*4+0]
0x14000eccc  mov     [rsp+128h+var_C0], rax
0x14000ecd1  lea     rbx, [rbp+rcx*4+0]
0x14000ecd6  mov     eax, 0
0x14000ecdb  cmovz   rbp, rax
0x14000ecdf  xor     eax, eax
0x14000ece1  test    r8d, r8d
0x14000ece4  mov     r8d, 0
0x14000ecea  setnz   al
0x14000eced  lea     r12, [rsi+rax*4]
0x14000ecf1  cmovz   rsi, r8
0x14000ecf5  mov     r14b, 1
0x14000ecf8  movzx   r13d, [rsp+128h+var_E9]
0x14000ecfe  lea     r9, qword_14001CE70
0x14000ed05  lea     r10, qword_14001CE80
0x14000ed0c  lea     r11, byte_14001CE4B
0x14000ed13  mov     rdi, [rsp+128h+var_D0]
0x14000ed18  mov     [rsp+128h+var_A0], r15
0x14000ed20  test    rsi, rsi
0x14000ed23  jnz     short loc_14000ED46
0x14000ed25  jmp     loc_14000EE60
0x14000ed30  movzx   r14d, byte ptr [rcx]
0x14000ed34  test    r14b, r13b
0x14000ed37  jnz     loc_14000EE13
0x14000ed3d  test    rsi, rsi
0x14000ed40  jz      loc_14000EE60
0x14000ed46  mov     rax, rsi
0x14000ed49  movzx   ecx, r14b
0x14000ed4d  test    rbp, rbp
0x14000ed50  jz      short loc_14000ED80
0x14000ed52  mov     edx, [rbp+0]
0x14000ed55  cmp     [rax], edx
0x14000ed57  jge     short loc_14000EDA6
0x14000ed59  cmp     r14b, 10h
0x14000ed5d  jnb     loc_14000F264
0x14000ed63  add     rcx, r10
0x14000ed66  xor     edx, edx
0x14000ed68  cmp     r12, [rsp+128h+var_C8]
0x14000ed6d  setnz   dl
0x14000ed70  mov     esi, 0
0x14000ed75  cmovnz  rsi, r12
0x14000ed79  lea     r12, [r12+rdx*4]
0x14000ed7d  jmp     short loc_14000ED30
0x14000ed80  cmp     r14b, 10h
0x14000ed84  jnb     loc_14000F253
0x14000ed8a  add     rcx, r10
0x14000ed8d  xor     edx, edx
0x14000ed8f  cmp     r12, [rsp+128h+var_C8]
0x14000ed94  setnz   dl
0x14000ed97  mov     rsi, r12
0x14000ed9a  lea     r12, [r12+rdx*4]
0x14000ed9e  cmovz   rsi, r8
0x14000eda2  xor     ebp, ebp
0x14000eda4  jmp     short loc_14000ED30
0x14000eda6  jle     short loc_14000EDD7
0x14000eda8  cmp     r14b, 10h
0x14000edac  jnb     loc_14000F286
0x14000edb2  add     rcx, r9
0x14000edb5  xor     edx, edx
0x14000edb7  cmp     rbx, [rsp+128h+var_C0]
0x14000edbc  mov     rsi, rax
0x14000edbf  mov     rax, rbp
0x14000edc2  mov     ebp, 0
0x14000edc7  cmovnz  rbp, rbx
0x14000edcb  setnz   dl
0x14000edce  lea     rbx, [rbx+rdx*4]
0x14000edd2  jmp     loc_14000ED30
0x14000edd7  cmp     r14b, 10h
0x14000eddb  jnb     loc_14000F275
0x14000ede1  add     rcx, r11
0x14000ede4  xor     edx, edx
0x14000ede6  cmp     r12, [rsp+128h+var_C8]
0x14000edeb  setnz   dl
0x14000edee  mov     rsi, r12
0x14000edf1  lea     r12, [r12+rdx*4]
0x14000edf5  cmovz   rsi, r8
0x14000edf9  xor     edx, edx
0x14000edfb  cmp     rbx, [rsp+128h+var_C0]
0x14000ee00  setnz   dl
0x14000ee03  mov     rbp, rbx
0x14000ee06  lea     rbx, [rbx+rdx*4]
0x14000ee0a  cmovz   rbp, r8
0x14000ee0e  jmp     loc_14000ED30
0x14000ee13  mov     rdx, [rdi+10h]
0x14000ee17  cmp     r15, rdx
0x14000ee1a  jnb     loc_14000F297
0x14000ee20  mov     ecx, [rax]
0x14000ee22  mov     rax, [rdi+8]
0x14000ee26  inc     dword ptr [rax+r15*4]
0x14000ee2a  mov     r15, [rdi+10h]
0x14000ee2e  lea     rdx, [r15+1]
0x14000ee32  cmp     [rdi], r15
0x14000ee35  jz      short loc_14000EE9C
0x14000ee37  mov     rax, [rdi+8]
0x14000ee3b  mov     [rax+r15*4], ecx
0x14000ee3f  mov     [rdi+10h], rdx
0x14000ee43  xor     r13b, 0Fh
0x14000ee47  mov     r15, [rsp+128h+var_A0]
0x14000ee4f  test    rsi, rsi
0x14000ee52  jnz     loc_14000ED46
0x14000ee58  nop     dword ptr [rax+rax+00000000h]
0x14000ee60  test    rbp, rbp
0x14000ee63  jz      loc_14000EF30
0x14000ee69  movzx   ecx, r14b
0x14000ee6d  cmp     r14b, 10h
0x14000ee71  jnb     loc_14000F242
0x14000ee77  add     rcx, r9
0x14000ee7a  xor     eax, eax
0x14000ee7c  cmp     rbx, [rsp+128h+var_C0]
0x14000ee81  setnz   al
0x14000ee84  lea     rdx, [rbx+rax*4]
0x14000ee88  cmovz   rbx, r8
0x14000ee8c  mov     rax, rbp
0x14000ee8f  mov     rbp, rbx
0x14000ee92  mov     rbx, rdx
0x14000ee95  xor     esi, esi
0x14000ee97  jmp     loc_14000ED30
0x14000ee9c  mov     dword ptr [rsp+128h+var_D0], ecx
0x14000eea0  lea     r9, [r15+r15]
0x14000eea4  cmp     rdx, r9
0x14000eea7  cmova   r9, rdx
0x14000eeab  cmp     r9, 5
0x14000eeaf  mov     eax, 4
0x14000eeb4  cmovb   r9, rax
0x14000eeb8  mov     r8, [rdi+8]
0x14000eebc  mov     [rsp+128h+var_100], 4
0x14000eec5  mov     [rsp+128h+var_108], 4
0x14000eece  lea     rcx, [rsp+128h+var_60]
0x14000eed6  mov     rdx, r15
0x14000eed9  mov     [rsp+128h+var_98], r9
0x14000eee1  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244
0x14000eee6  cmp     byte ptr [rsp+128h+var_60], 0
  ... truncated ...
```
