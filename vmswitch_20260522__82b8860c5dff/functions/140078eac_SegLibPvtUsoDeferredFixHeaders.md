# SegLibPvtUsoDeferredFixHeaders

- ea: `0x140078eac`
- end: `0x140079b9f`
- name: `SegLibPvtUsoDeferredFixHeaders`
- size: `3315`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140001594`
- `0x1401b9e8c`

## callees

- `0x140006620`
- `0x140052030`
- `0x140078eac`
- `0x1401bbe10`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140078fcf`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007924e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007944b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140079663`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140079860`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140079a66`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140078fcf`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007924e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007944b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140079663`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140079860`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140079a66`

## pseudocode

```c
NTSTATUS __fastcall SegLibPvtUsoDeferredFixHeaders(
        __int64 a1,
        __int64 a2,
        unsigned __int16 *a3,
        __int64 a4,
        int a5,
        __int16 a6)
{
  __int16 v6; // r12
  __int64 v7; // rax
  int v8; // r15d
  __int64 v10; // rbp
  unsigned __int16 *v12; // r14
  unsigned __int16 v13; // si
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 *v16; // rdi
  __int64 v17; // rcx
  unsigned int v18; // eax
  _DWORD *v19; // r8
  unsigned int v20; // ebp
  _DWORD *v21; // rax
  int v22; // ecx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r9
  volatile signed __int32 *v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r9
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // r9
  __int64 v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // rdx
  int v38; // eax
  USHORT v39; // r9
  NTSTATUS result; // eax
  __int64 v41; // rdx
  int v42; // ecx
  __int16 v43; // r9
  unsigned __int8 v44; // r10
  unsigned int v45; // esi
  unsigned int v46; // r11d
  USHORT v47; // r15
  unsigned __int16 v48; // ax
  __int16 v49; // r12
  _WORD *v50; // r14
  __int64 v51; // rcx
  __int64 v52; // r8
  __int64 v53; // rax
  __int64 v54; // rdi
  __int64 v55; // rcx
  unsigned int v56; // eax
  _DWORD *v57; // r8
  unsigned int v58; // ebp
  _DWORD *v59; // rax
  int v60; // ecx
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // rax
  __int64 v64; // rdx
  __int64 v65; // r9
  volatile signed __int32 *v66; // rcx
  __int64 v67; // rdx
  __int64 v68; // r9
  __int64 v69; // rax
  __int64 v70; // rdx
  __int64 v71; // r9
  __int64 v72; // rcx
  __int64 v73; // rdx
  __int64 v74; // rcx
  int v75; // eax
  _WORD *v76; // r14
  __int16 v77; // r15
  __int64 v78; // rcx
  __int64 v79; // r8
  __int64 v80; // rax
  unsigned int v81; // eax
  _DWORD *v82; // r8
  unsigned int v83; // esi
  _DWORD *v84; // rax
  int v85; // ecx
  __int64 v86; // rdx
  __int64 v87; // rcx
  __int64 v88; // rax
  __int64 v89; // rdx
  __int64 v90; // r9
  volatile signed __int32 *v91; // rcx
  __int64 v92; // rdx
  __int64 v93; // r9
  __int64 v94; // rax
  __int64 v95; // rdx
  __int64 v96; // r9
  __int64 v97; // rcx
  __int64 v98; // rdx
  __int64 v99; // rcx
  unsigned int v100; // eax
  __int16 v101; // r12
  __int16 v102; // r12
  _WORD *v103; // r14
  __int64 v104; // rcx
  __int64 v105; // r8
  __int64 v106; // rax
  unsigned int v107; // eax
  __int64 v108; // rax
  _DWORD *v109; // r8
  unsigned int v110; // esi
  _DWORD *v111; // rax
  int v112; // ecx
  __int64 v113; // rdx
  __int64 v114; // rcx
  __int64 v115; // rax
  __int64 v116; // rdx
  __int64 v117; // r9
  volatile signed __int32 *v118; // rcx
  __int64 v119; // rdx
  __int64 v120; // r9
  __int64 v121; // rax
  __int64 v122; // rdx
  __int64 v123; // r9
  __int64 v124; // rcx
  __int64 v125; // rdx
  __int64 v126; // rcx
  __int64 v127; // rdx
  unsigned int v128; // eax
  unsigned __int16 v129; // r12
  unsigned __int16 *v130; // r14
  __int64 v131; // rcx
  __int64 v132; // r8
  __int64 v133; // rax
  unsigned int v134; // eax
  _DWORD *v135; // r8
  unsigned int v136; // esi
  _DWORD *v137; // rax
  int v138; // ecx
  __int64 v139; // rdx
  __int64 v140; // rcx
  __int64 v141; // rax
  __int64 v142; // rdx
  __int64 v143; // r9
  volatile signed __int32 *v144; // rcx
  __int64 v145; // rdx
  __int64 v146; // r9
  __int64 v147; // rax
  __int64 v148; // rdx
  __int64 v149; // r9
  __int64 v150; // rcx
  __int64 v151; // rdx
  __int64 v152; // rcx
  __int64 v153; // rdx
  unsigned int v154; // eax
  _WORD *v155; // r14
  __int64 v156; // rdx
  unsigned int v157; // esi
  __int64 v158; // rcx
  __int64 v159; // r8
  __int64 v160; // rax
  unsigned int v161; // eax
  _DWORD *v162; // r8
  unsigned int v163; // ebp
  _DWORD *v164; // rax
  int v165; // ecx
  __int64 v166; // rdx
  __int64 v167; // rcx
  __int64 v168; // rax
  __int64 v169; // rdx
  __int64 v170; // r9
  volatile signed __int32 *v171; // rcx
  __int64 v172; // rdx
  __int64 v173; // r9
  __int64 v174; // rax
  __int64 v175; // rdx
  __int64 v176; // r9
  __int64 v177; // rcx
  __int64 v178; // rdx
  __int64 v179; // rcx
  __int64 v180; // rdx
  unsigned int v181; // eax
  NTSTATUS v182; // [rsp+20h] [rbp-48h]
  unsigned __int16 v183; // [rsp+24h] [rbp-44h]
  __int64 v184; // [rsp+78h] [rbp+10h]
  USHORT pusResult; // [rsp+88h] [rbp+20h] BYREF

  v184 = a2;
  v6 = *(_WORD *)(a2 + 18);
  v7 = 0;
  v8 = a5;
  v10 = a2;
  pusResult = 0;
  v182 = 0;
  v183 = -13108;
  if ( (*(_BYTE *)(a2 + 23) & 1) != 0 )
    goto LABEL_39;
  v12 = a3 + 2;
  v13 = __ROR2__(*(_WORD *)(a2 + 20) + a5, 8);
  v183 = v13;
  if ( !a1 )
  {
LABEL_38:
    *v12 = v13;
    goto LABEL_39;
  }
  v14 = *(_QWORD *)(a1 + 80);
  if ( *(_BYTE *)(v14 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
  {
    v15 = *(unsigned int *)(a1 + 12);
    *(_BYTE *)(a1 + 4) = 1;
    if ( (_DWORD)v15 != -1 )
    {
      a2 = *(_QWORD *)(v14 + 24);
      if ( a2 )
        v7 = a2 + 20 * v15;
    }
    _InterlockedAdd16((volatile signed __int16 *)(v7 + 16), 1u);
  }
  v16 = (__int64 *)(a1 + 80);
  v17 = *(_QWORD *)(a1 + 80);
  v18 = *(_DWORD *)(v17 + 4);
  if ( !v18 )
  {
    if ( *(_DWORD *)(a1 + 20) )
    {
      LOBYTE(a2) = 1;
      BLFlushBatchOpContextEx(a1, a2, 0);
    }
    if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (*(_BYTE *)(a1 + 8) & 6) == 6 )
    {
      (*(void (**)(void))(*v16 + 32))();
      *v12 = v13;
      (*(void (**)(void))(*v16 + 40))();
      goto LABEL_39;
    }
    goto LABEL_38;
  }
  v19 = *(_DWORD **)(a1 + 32);
  v20 = v19[2];
  if ( v20 >= v19[3] )
  {
    v20 = 0;
    if ( *(_DWORD *)(a1 + 16) < v18 )
    {
      v21 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v17 + 64));
      v19 = v21;
      if ( v21 )
      {
        *(_QWORD *)v21 = 0;
        v21[2] = 0;
        v22 = *(_DWORD *)(*v16 + 8);
        *((_QWORD *)v21 + 2) = v21 + 6;
        v21[3] = v22;
        **(_QWORD **)(a1 + 32) = v21;
        v23 = *v16;
        ++*(_DWORD *)(a1 + 16);
        *(_QWORD *)(a1 + 32) = v21;
        if ( *(_BYTE *)(v23 + 1) == 1 )
        {
          v24 = *(unsigned int *)(a1 + 12);
          v25 = 0;
          if ( (_DWORD)v24 != -1 )
          {
            v26 = *(_QWORD *)(v23 + 24);
            if ( v26 )
              v25 = v26 + 20 * v24;
          }
          _InterlockedAdd16((volatile signed __int16 *)(v25 + 12), 1u);
          v27 = *(unsigned int *)(a1 + 12);
          v28 = 0;
          if ( (_DWORD)v27 != -1 )
          {
            v29 = *(_QWORD *)(*v16 + 24);
            if ( v29 )
              v28 = (volatile signed __int32 *)(v29 + 20 * v27);
          }
          _InterlockedAdd(v28, 1u);
        }
        goto LABEL_29;
      }
      LOBYTE(a2) = 1;
    }
    else
    {
      LOBYTE(a2) = 1;
    }
    BLFlushBatchOpContextEx(a1, a2, 0);
    v19 = (_DWORD *)(a1 + 56);
  }
LABEL_29:
  ++*(_DWORD *)(a1 + 20);
  ++v19[2];
  if ( *(_BYTE *)(*v16 + 1) == 1 )
  {
    v30 = *(unsigned int *)(a1 + 12);
    v31 = 0;
    if ( (_DWORD)v30 != -1 )
    {
      v32 = *(_QWORD *)(*v16 + 24);
      if ( v32 )
        v31 = v32 + 20 * v30;
    }
    _InterlockedAdd16((volatile signed __int16 *)(v31 + 14), 1u);
    v33 = *(unsigned int *)(a1 + 12);
    v34 = 0;
    if ( (_DWORD)v33 != -1 )
    {
      v35 = *(_QWORD *)(*v16 + 24);
      if ( v35 )
        v34 = v35 + 20 * v33;
    }
    _InterlockedAdd((volatile signed __int32 *)(v34 + 4), 1u);
  }
  v36 = *((_QWORD *)v19 + 2);
  v37 = 3LL * v20;
  v38 = *(_DWORD *)(v36 + 24LL * v20 + 16);
  v10 = v184;
  *(_QWORD *)(v36 + 8 * v37) = v12;
  *(_DWORD *)(v36 + 8 * v37 + 16) = v38 & 0xFFFFFFF0 | 2;
  *(_WORD *)(v36 + 8 * v37 + 8) = v13;
LABEL_39:
  if ( (*(_BYTE *)(v10 + 23) & 4) != 0 )
    return v182;
  if ( v8 == *(_DWORD *)(v10 + 8) )
    v39 = *(_WORD *)(v10 + 4) - a6;
  else
    v39 = *(_WORD *)v10;
  result = RtlUShortAdd(8u, v39, &pusResult);
  v182 = result;
  if ( result >= 0 )
  {
    v45 = *(unsigned __int16 *)(v10 + 12);
    v46 = v42 - 7;
    v47 = pusResult;
    if ( *(_WORD *)(v10 + 12) )
    {
      v48 = __ROR2__(pusResult, 8);
      v41 = v45 + v48;
      v45 = (unsigned __int16)(v45 + v48) + WORD1(v41);
      if ( !v45 )
        LOWORD(v45) = -1;
    }
    else if ( (v44 & (unsigned __int8)v46) != 0 )
    {
      return -1071448043;
    }
    v49 = v43 + v6;
    v50 = (_WORD *)(a4 + 6);
    if ( !a1 )
    {
      v54 = 80;
      goto LABEL_86;
    }
    v51 = *(_QWORD *)(a1 + 80);
    if ( *(_BYTE *)(v51 + 1) == (_BYTE)v46 && !*(_BYTE *)(a1 + 4) )
    {
      v52 = *(unsigned int *)(a1 + 12);
      v53 = 0;
      *(_BYTE *)(a1 + 4) = v46;
      if ( (_DWORD)v52 != -1 )
      {
        v41 = *(_QWORD *)(v51 + 24);
        if ( v41 )
          v53 = v41 + 20 * v52;
      }
      _InterlockedAdd16((volatile signed __int16 *)(v53 + 16), v46);
    }
    v54 = a1 + 80;
    v55 = *(_QWORD *)(a1 + 80);
    v56 = *(_DWORD *)(v55 + 4);
    if ( !v56 )
    {
      if ( *(_DWORD *)(a1 + 20) )
      {
        LOBYTE(v41) = v46;
        BLFlushBatchOpContextEx(a1, v41, 0);
      }
      if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (*(_BYTE *)(a1 + 8) & 6) == 6 )
      {
        (*(void (**)(void))(*(_QWORD *)v54 + 32LL))();
        *v50 = v45;
        (*(void (**)(void))(*(_QWORD *)v54 + 40LL))();
LABEL_87:
        v46 = 1;
        goto LABEL_88;
      }
LABEL_86:
      *v50 = v45;
      goto LABEL_87;
    }
    v57 = *(_DWORD **)(a1 + 32);
    v58 = v57[2];
    if ( v58 >= v57[3] )
    {
      v58 = 0;
      if ( *(_DWORD *)(a1 + 16) < v56 )
      {
        v59 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v55 + 64));
        v57 = v59;
        if ( v59 )
        {
          *(_QWORD *)v59 = 0;
          v46 = 1;
          v59[2] = 0;
          v60 = *(_DWORD *)(*(_QWORD *)v54 + 8LL);
          *((_QWORD *)v59 + 2) = v59 + 6;
          v59[3] = v60;
          **(_QWORD **)(a1 + 32) = v59;
          v61 = *(_QWORD *)v54;
          ++*(_DWORD *)(a1 + 16);
          *(_QWORD *)(a1 + 32) = v59;
          if ( *(_BYTE *)(v61 + 1) == 1 )
          {
            v62 = *(unsigned int *)(a1 + 12);
            v63 = 0;
            if ( (_DWORD)v62 != -1 )
            {
              v64 = *(_QWORD *)(v61 + 24);
              if ( v64 )
                v63 = v64 + 20 * v62;
            }
            _InterlockedAdd16((volatile signed __int16 *)(v63 + 12), 1u);
            v65 = *(unsigned int *)(a1 + 12);
            v66 = 0;
            if ( (_DWORD)v65 != -1 )
            {
              v67 = *(_QWORD *)(*(_QWORD *)v54 + 24LL);
              if ( v67 )
                v66 = (volatile signed __int32 *)(v67 + 20 * v65);
            }
            _InterlockedAdd(v66, 1u);
          }
          goto LABEL_76;
        }
        LOBYTE(v41) = 1;
      }
      else
      {
        LOBYTE(v41) = v46;
      }
      BLFlushBatchOpContextEx(a1, v41, 0);
      v57 = (_DWORD *)(a1 + 56);
      v46 = 1;
    }
LABEL_76:
    *(_DWORD *)(a1 + 20) += v46;
    v57[2] += v46;
    if ( *(_BYTE *)(*(_QWORD *)v54 + 1LL) == (_BYTE)v46 )
    {
      v68 = *(unsigned int *)(a1 + 12);
      v69 = 0;
      if ( (_DWORD)v68 != -1 )
      {
        v70 = *(_QWORD *)(*(_QWORD *)v54 + 24LL);
        if ( v70 )
          v69 = v70 + 20 * v68;
      }
      _InterlockedAdd16((volatile signed __int16 *)(v69 + 14), v46);
      v71 = *(unsigned int *)(a1 + 12);
      v72 = 0;
      if ( (_DWORD)v71 != -1 )
      {
        v73 = *(_QWORD *)(*(_QWORD *)v54 + 24LL);
        if ( v73 )
          v72 = v73 + 20 * v71;
      }
      _InterlockedAdd((volatile signed __int32 *)(v72 + 4), v46);
    }
    v74 = *((_QWORD *)v57 + 2);
    v41 = 3LL * v58;
    v75 = *(_DWORD *)(v74 + 24LL * v58 + 16);
    v10 = v184;
    *(_QWORD *)(v74 + 8 * v41) = v50;
    *(_DWORD *)(v74 + 8 * v41 + 16) = v75 & 0xFFFFFFF0 | 2;
    *(_WORD *)(v74 + 8 * v41 + 8) = v45;
LABEL_88:
    v76 = (_WORD *)(a4 + 4);
    v77 = __ROR2__(v47, 8);
    if ( !a1 )
    {
LABEL_124:
      *v76 = v77;
      goto LABEL_125;
    }
    v78 = *(_QWORD *)v54;
    if ( *(_BYTE *)(*(_QWORD *)v54 + 1LL) == (_BYTE)v46 && !*(_BYTE *)(a1 + 4) )
    {
      v79 = *(unsigned int *)(a1 + 12);
      v80 = 0;
      *(_BYTE *)(a1 + 4) = v46;
      if ( (_DWORD)v79 != -1 )
      {
        v41 = *(_QWORD *)(v78 + 24);
        if ( v41 )
          v80 = v41 + 20 * v79;
      }
      _InterlockedAdd16((volatile signed __int16 *)(v80 + 16), v46);
    }
    v81 = *(_DWORD *)(*(_QWORD *)v54 + 4LL);
    if ( !v81 )
    {
      if ( *(_DWORD *)(a1 + 20) )
      {
        LOBYTE(v41) = v46;
        BLFlushBatchOpContextEx(a1, v41, 0);
      }
      if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (*(_BYTE *)(a1 + 8) & 6) == 6 )
      {
        (*(void (**)(void))(*(_QWORD *)v54 + 32LL))();
        *v76 = v77;
        (*(void (**)(void))(*(_QWORD *)v54 + 40LL))();
        goto LABEL_125;
      }
      goto LABEL_124;
    }
    v82 = *(_DWORD **)(a1 + 32);
    v83 = v82[2];
    if ( v83 >= v82[3] )
    {
      v83 = 0;
      if ( *(_DWORD *)(a1 + 16) < v81 )
      {
        v84 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)v54 + 64LL));
        v82 = v84;
        if ( v84 )
        {
          *(_QWORD *)v84 = 0;
          v46 = 1;
          v84[2] = 0;
          v85 = *(_DWORD *)(*(_QWORD *)v54 + 8LL);
          *((_QWORD *)v84 + 2) = v84 + 6;
          v84[3] = v85;
          **(_QWORD **)(a1 + 32) = v84;
          v86 = *(_QWORD *)v54;
          ++*(_DWORD *)(a1 + 16);
          *(_QWORD *)(a1 + 32) = v84;
          if ( *(_BYTE *)(v86 + 1) == 1 )
          {
            v87 = *(unsigned int *)(a1 + 12);
            v88 = 0;
            if ( (_DWORD)v87 != -1 )
            {
              v89 = *(_QWORD *)(v86 + 24);
              if ( v89 )
                v88 = v89 + 20 * v87;
            }
            _InterlockedAdd16((volatile signed __int16 *)(v88 + 12), 1u);
            v90 = *(unsigned int *)(a1 + 12);
            v91 = 0;
            if ( (_DWORD)v90 != -1 )
            {
              v92 = *(_QWORD *)(*(_QWORD *)v54 + 24LL);
              if ( v92 )
                v91 = (volatile signed __int32 *)(v92 + 20 * v90);
            }
            _InterlockedAdd(v91, 1u);
          }
          goto LABEL_115;
        }
        LOBYTE(v41) = 1;
      }
      else
      {
        LOBYTE(v41) = v46;
      }
      BLFlushBatchOpContextEx(a1, v41, 0);
      v82 = (_DWORD *)(a1 + 56);
      v46 = 1;
    }
LABEL_115:
    *(_DWORD *)(a1 + 20) += v46;
    v82[2] += v46;
    if ( *(_BYTE *)(*(_QWORD *)v54 + 1LL) == (_BYTE)v46 )
    {
      v93 = *(unsigned int *)(a1 + 12);
      v94 = 0;
      if ( (_DWORD)v93 != -1 )
      {
        v95 = *(_QWORD *)(*(_QWORD *)v54 + 24LL);
        if ( v95 )
          v94 = v95 + 20 * v93;
      }
      _InterlockedAdd16((volatile signed __int16 *)(v94 + 14), v46);
      v96 = *(unsigned int *)(a1 + 12);
      v97 = 0;
      if ( (_DWORD)v96 != -1 )
      {
        v98 = *(_QWORD *)(*(_QWORD *)v54 + 24LL);
        if ( v98 )
          v97 = v98 + 20 * v96;
      }
      _InterlockedAdd((volatile signed __int32 *)(v97 + 4), v46);
    }
    v99 = *((_QWORD *)v82 + 2);
    v41 = 3LL * v83;
    v100 = *(_DWORD *)(v99 + 24LL * v83 + 16) & 0xFFFFFFF2;
    *(_QWORD *)(v99 + 8 * v41) = v76;
    *(_WORD *)(v99 + 8 * v41 + 8) = v77;
    *(_DWORD *)(v99 + 8 * v41 + 16) = v100 | 2;
LABEL_125:
    v101 = v49 - *(unsigned __int8 *)(v10 + 22);
    if ( (*(_BYTE *)(v10 + 23) & 1) != 0 )
    {
      v102 = __ROR2__(v101 - 40, 8);
      v103 = a3 + 2;
      if ( !a1 )
        goto LABEL_163;
      v104 = *(_QWORD *)v54;
      if ( *(_BYTE *)(*(_QWORD *)v54 + 1LL) == 1 && !*(_BYTE *)(a1 + 4) )
      {
        v105 = *(unsigned int *)(a1 + 12);
        v106 = 0;
        *(_BYTE *)(a1 + 4) = 1;
        if ( (_DWORD)v105 != -1 )
        {
          v41 = *(_QWORD *)(v104 + 24);
          if ( v41 )
            v106 = v41 + 20 * v105;
        }
        _InterlockedAdd16((volatile signed __int16 *)(v106 + 16), 1u);
      }
      v107 = *(_DWORD *)(*(_QWORD *)v54 + 4LL);
      if ( !v107 )
      {
        if ( *(_DWORD *)(a1 + 20) )
        {
          LOBYTE(v41) = 1;
          BLFlushBatchOpContextEx(a1, v41, 0);
        }
        if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (*(_BYTE *)(a1 + 8) & 6) == 6 )
        {
          (*(void (**)(void))(*(_QWORD *)v54 + 32LL))();
          *v103 = v102;
          v108 = *(_QWORD *)v54;
LABEL_139:
          (*(void (**)(void))(v108 + 40))();
          return v182;
        }
LABEL_163:
        *v103 = v102;
        return v182;
      }
      v109 = *(_DWORD **)(a1 + 32);
      v110 = v109[2];
      if ( v110 >= v109[3] )
      {
        v110 = 0;
        if ( *(_DWORD *)(a1 + 16) < v107 )
        {
          v111 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)v54 + 64LL));
          v109 = v111;
          if ( v111 )
          {
            *(_QWORD *)v111 = 0;
            v111[2] = 0;
            v112 = *(_DWORD *)(*(_QWORD *)v54 + 8LL);
            *((_QWORD *)v111 + 2) = v111 + 6;
            v111[3] = v112;
            **(_QWORD **)(a1 + 32) = v111;
            v113 = *(_QWORD *)v54;
            ++*(_DWORD *)(a1 + 16);
            *(_QWORD *)(a1 + 32) = v111;
            if ( *(_BYTE *)(v113 + 1) == 1 )
            {
              v114 = *(unsigned int *)(a1 + 12);
              v115 = 0;
              if ( (_DWORD)v114 != -1 )
              {
                v116 = *(_QWORD *)(v113 + 24);
                if ( v116 )
                  v115 = v116 + 20 * v114;
              }
              _InterlockedAdd16((volatile signed __int16 *)(v115 + 12), 1u);
              v117 = *(unsigned int *)(a1 + 12);
              v118 = 0;
              if ( (_DWORD)v117 != -1 )
              {
                v119 = *(_QWORD *)(*(_QWORD *)v54 + 24LL);
                if ( v119 )
                  v118 = (volatile signed __int32 *)(v119 + 20 * v117);
              }
              _InterlockedAdd(v118, 1u);
            }
            goto LABEL_154;
          }
          LOBYTE(v41) = 1;
        }
        else
        {
          LOBYTE(v41) = 1;
        }
        BLFlushBatchOpContextEx(a1, v41, 0);
        v109 = (_DWORD *)(a1 + 56);
      }
LABEL_154:
      ++*(_DWORD *)(a1 + 20);
      ++v109[2];
      if ( *(_BYTE *)(*(_QWORD *)v54 + 1LL) == 1 )
      {
        v120 = *(unsigned int *)(a1 + 12);
        v121 = 0;
        if ( (_DWORD)v120 != -1 )
        {
          v122 = *(_QWORD *)(*(_QWORD *)v54 + 24LL);
          if ( v122 )
            v121 = v122 + 20 * v120;
        }
        _InterlockedAdd16((volatile signed __int16 *)(v121 + 14), 1u);
        v123 = *(unsigned int *)(a1 + 12);
        v124 = 0;
        if ( (_DWORD)v123 != -1 )
        {
          v125 = *(_QWORD *)(*(_QWORD *)v54 + 24LL);
          if ( v125 )
            v124 = v125 + 20 * v123;
        }
        _InterlockedAdd((volatile signed __int32 *)(v124 + 4), 1u);
      }
      v126 = *((_QWORD *)v109 + 2);
      v127 = 3LL * v110;
      v128 = *(_DWORD *)(v126 + 24LL * v110 + 16) & 0xFFFFFFF2;
      *(_QWORD *)(v126 + 8 * v127) = v103;
      *(_WORD *)(v126 + 8 * v127 + 8) = v102;
      *(_DWORD *)(v126 + 8 * v127 + 16) = v128 | 2;
      return v182;
    }
    v129 = __ROR2__(v101, 8);
    v130 = a3 + 1;
    if ( !a1 )
    {
LABEL_200:
      *v130 = v129;
      goto LABEL_201;
    }
    v131 = *(_QWORD *)v54;
    if ( *(_BYTE *)(*(_QWORD *)v54 + 1LL) == 1 && !*(_BYTE *)(a1 + 4) )
    {
      v132 = *(unsigned int *)(a1 + 12);
      v133 = 0;
      *(_BYTE *)(a1 + 4) = 1;
      if ( (_DWORD)v132 != -1 )
      {
        v41 = *(_QWORD *)(v131 + 24);
        if ( v41 )
          v133 = v41 + 20 * v132;
      }
      _InterlockedAdd16((volatile signed __int16 *)(v133 + 16), 1u);
    }
    v134 = *(_DWORD *)(*(_QWORD *)v54 + 4LL);
    if ( !v134 )
    {
      if ( *(_DWORD *)(a1 + 20) )
      {
        LOBYTE(v41) = 1;
        BLFlushBatchOpContextEx(a1, v41, 0);
      }
      if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (*(_BYTE *)(a1 + 8) & 6) == 6 )
      {
        (*(void (**)(void))(*(_QWORD *)v54 + 32LL))();
        *v130 = v129;
        (*(void (**)(void))(*(_QWORD *)v54 + 40LL))();
        goto LABEL_201;
      }
      goto LABEL_200;
    }
    v135 = *(_DWORD **)(a1 + 32);
    v136 = v135[2];
    if ( v136 >= v135[3] )
    {
      v136 = 0;
      if ( *(_DWORD *)(a1 + 16) < v134 )
      {
        v137 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)v54 + 64LL));
        v135 = v137;
        if ( v137 )
        {
          *(_QWORD *)v137 = 0;
          v137[2] = 0;
          v138 = *(_DWORD *)(*(_QWORD *)v54 + 8LL);
          *((_QWORD *)v137 + 2) = v137 + 6;
          v137[3] = v138;
          **(_QWORD **)(a1 + 32) = v137;
          v139 = *(_QWORD *)v54;
          ++*(_DWORD *)(a1 + 16);
          *(_QWORD *)(a1 + 32) = v137;
          if ( *(_BYTE *)(v139 + 1) == 1 )
          {
            v140 = *(unsigned int *)(a1 + 12);
            v141 = 0;
            if ( (_DWORD)v140 != -1 )
            {
              v142 = *(_QWORD *)(v139 + 24);
              if ( v142 )
                v141 = v142 + 20 * v140;
            }
            _InterlockedAdd16((volatile signed __int16 *)(v141 + 12), 1u);
            v143 = *(unsigned int *)(a1 + 12);
            v144 = 0;
            if ( (_DWORD)v143 != -1 )
            {
              v145 = *(_QWORD *)(*(_QWORD *)v54 + 24LL);
              if ( v145 )
                v144 = (volatile signed __int32 *)(v145 + 20 * v143);
            }
            _InterlockedAdd(v144, 1u);
          }
          goto LABEL_191;
        }
        LOBYTE(v41) = 1;
      }
      else
      {
        LOBYTE(v41) = 1;
      }
      BLFlushBatchOpContextEx(a1, v41, 0);
      v135 = (_DWORD *)(a1 + 56);
    }
LABEL_191:
    ++*(_DWORD *)(a1 + 20);
    ++v135[2];
    if ( *(_BYTE *)(*(_QWORD *)v54 + 1LL) == 1 )
    {
      v146 = *(unsigned int *)(a1 + 12);
      v147 = 0;
      if ( (_DWORD)v146 != -1 )
      {
        v148 = *(_QWORD *)(*(_QWORD *)v54 + 24LL);
        if ( v148 )
          v147 = v148 + 20 * v146;
      }
      _InterlockedAdd16((volatile signed __int16 *)(v147 + 14), 1u);
      v149 = *(unsigned int *)(a1 + 12);
      v150 = 0;
      if ( (_DWORD)v149 != -1 )
      {
        v151 = *(_QWORD *)(*(_QWORD *)v54 + 24LL);
        if ( v151 )
          v150 = v151 + 20 * v149;
      }
      _InterlockedAdd((volatile signed __int32 *)(v150 + 4), 1u);
    }
    v152 = *((_QWORD *)v135 + 2);
    v153 = 3LL * v136;
    v154 = *(_DWORD *)(v152 + 24LL * v136 + 16) & 0xFFFFFFF2;
    *(_QWORD *)(v152 + 8 * v153) = v130;
    *(_WORD *)(v152 + 8 * v153 + 8) = v129;
    *(_DWORD *)(v152 + 8 * v153 + 16) = v154 | 2;
LABEL_201:
    v155 = a3 + 5;
    v156 = v183 + v129 + (unsigned int)*(unsigned __int16 *)(v10 + 14);
    v157 = ~((unsigned int)(v156 + __ROR4__(v183 + v129 + *(unsigned __int16 *)(v10 + 14), 16)) >> 16);
    if ( !a1 )
      goto LABEL_235;
    v158 = *(_QWORD *)v54;
    if ( *(_BYTE *)(*(_QWORD *)v54 + 1LL) == 1 && !*(_BYTE *)(a1 + 4) )
    {
      v159 = *(unsigned int *)(a1 + 12);
      v160 = 0;
      *(_BYTE *)(a1 + 4) = 1;
      if ( (_DWORD)v159 != -1 )
      {
        v156 = *(_QWORD *)(v158 + 24);
        if ( v156 )
          v160 = v156 + 20 * v159;
      }
      _InterlockedAdd16((volatile signed __int16 *)(v160 + 16), 1u);
    }
    v161 = *(_DWORD *)(*(_QWORD *)v54 + 4LL);
    if ( v161 )
    {
      v162 = *(_DWORD **)(a1 + 32);
      v163 = v162[2];
      if ( v163 >= v162[3] )
      {
        v163 = 0;
        if ( *(_DWORD *)(a1 + 16) < v161
          && (v164 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)v54 + 64LL)),
              (v162 = v164) != 0) )
        {
          *(_QWORD *)v164 = 0;
          v164[2] = 0;
          v165 = *(_DWORD *)(*(_QWORD *)v54 + 8LL);
          *((_QWORD *)v164 + 2) = v164 + 6;
          v164[3] = v165;
          **(_QWORD **)(a1 + 32) = v164;
          v166 = *(_QWORD *)v54;
          ++*(_DWORD *)(a1 + 16);
          *(_QWORD *)(a1 + 32) = v164;
          if ( *(_BYTE *)(v166 + 1) == 1 )
          {
            v167 = *(unsigned int *)(a1 + 12);
            v168 = 0;
            if ( (_DWORD)v167 != -1 )
            {
              v169 = *(_QWORD *)(v166 + 24);
              if ( v169 )
                v168 = v169 + 20 * v167;
            }
            _InterlockedAdd16((volatile signed __int16 *)(v168 + 12), 1u);
            v170 = *(unsigned int *)(a1 + 12);
            v171 = 0;
            if ( (_DWORD)v170 != -1 )
            {
              v172 = *(_QWORD *)(*(_QWORD *)v54 + 24LL);
              if ( v172 )
                v171 = (volatile signed __int32 *)(v172 + 20 * v170);
            }
            _InterlockedAdd(v171, 1u);
          }
        }
        else
        {
          LOBYTE(v156) = 1;
          BLFlushBatchOpContextEx(a1, v156, 0);
          v162 = (_DWORD *)(a1 + 56);
        }
      }
      ++*(_DWORD *)(a1 + 20);
      ++v162[2];
      if ( *(_BYTE *)(*(_QWORD *)v54 + 1LL) == 1 )
      {
        v173 = *(unsigned int *)(a1 + 12);
        v174 = 0;
        if ( (_DWORD)v173 != -1 )
        {
          v175 = *(_QWORD *)(*(_QWORD *)v54 + 24LL);
          if ( v175 )
            v174 = v175 + 20 * v173;
        }
        _InterlockedAdd16((volatile signed __int16 *)(v174 + 14), 1u);
        v176 = *(unsigned int *)(a1 + 12);
        v177 = 0;
        if ( (_DWORD)v176 != -1 )
        {
          v178 = *(_QWORD *)(*(_QWORD *)v54 + 24LL);
          if ( v178 )
            v177 = v178 + 20 * v176;
        }
        _InterlockedAdd((volatile signed __int32 *)(v177 + 4), 1u);
      }
      v179 = *((_QWORD *)v162 + 2);
      v180 = 3LL * v163;
      v181 = *(_DWORD *)(v179 + 24LL * v163 + 16) & 0xFFFFFFF2;
      *(_QWORD *)(v179 + 8 * v180) = v155;
      *(_WORD *)(v179 + 8 * v180 + 8) = v157;
      *(_DWORD *)(v179 + 8 * v180 + 16) = v181 | 2;
      return v182;
    }
    if ( *(_DWORD *)(a1 + 20) )
    {
      LOBYTE(v156) = 1;
      BLFlushBatchOpContextEx(a1, v156, 0);
    }
    if ( (*(_BYTE *)(a1 + 8) & 5) != 5 && (*(_BYTE *)(a1 + 8) & 6) != 6 )
    {
LABEL_235:
      *v155 = v157;
      return v182;
    }
    (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
    *v155 = v157;
    v108 = *(_QWORD *)(a1 + 80);
    goto LABEL_139;
  }
  return result;
}

```

## disassembly

```asm
0x140078eac  mov     r11, rsp
0x140078eaf  mov     [r11+8], rbx
0x140078eb3  mov     [r11+18h], r8
0x140078eb7  mov     [r11+10h], rdx
0x140078ebb  push    rbp
0x140078ebc  push    rsi
0x140078ebd  push    rdi
0x140078ebe  push    r12
0x140078ec0  push    r13
0x140078ec2  push    r14
0x140078ec4  push    r15
0x140078ec6  sub     rsp, 30h
0x140078eca  movzx   r12d, word ptr [rdx+12h]
0x140078ecf  xor     eax, eax
0x140078ed1  mov     r15d, [rsp+68h+arg_20]
0x140078ed9  mov     r13, r9
0x140078edc  mov     rbp, rdx
0x140078edf  mov     [r11+20h], ax
0x140078ee4  mov     rbx, rcx
0x140078ee7  mov     [rsp+68h+var_48], eax
0x140078eeb  lea     r10d, [rax+1]
0x140078eef  mov     dword ptr [rsp+68h+var_44], 0CCCCh
0x140078ef7  test    [rdx+17h], r10b
0x140078efb  jnz     loc_1400790FC
0x140078f01  movzx   esi, r15w
0x140078f05  lea     r14, [r8+4]
0x140078f09  add     si, [rdx+14h]
0x140078f0d  ror     si, 8
0x140078f11  mov     [rsp+68h+var_44], si
0x140078f16  test    rcx, rcx
0x140078f19  jz      loc_1400790F8
0x140078f1f  mov     rcx, [rcx+50h]
0x140078f23  cmp     [rcx+1], r10b
0x140078f27  jnz     short loc_140078F53
0x140078f29  cmp     [rbx+4], al
0x140078f2c  jnz     short loc_140078F53
0x140078f2e  mov     r8d, [rbx+0Ch]
0x140078f32  mov     [rbx+4], r10b
0x140078f36  cmp     r8d, 0FFFFFFFFh
0x140078f3a  jz      short loc_140078F4D
0x140078f3c  mov     rdx, [rcx+18h]
0x140078f40  test    rdx, rdx
0x140078f43  jz      short loc_140078F4D
0x140078f45  lea     rcx, [r8+r8*4]
0x140078f49  lea     rax, [rdx+rcx*4]
0x140078f4d  lock add [rax+10h], r10w
0x140078f53  lea     rdi, [rbx+50h]
0x140078f57  mov     rcx, [rdi]
0x140078f5a  mov     eax, [rcx+4]
0x140078f5d  test    eax, eax
0x140078f5f  jnz     short loc_140078FAD
0x140078f61  cmp     [rbx+14h], eax
0x140078f64  jz      short loc_140078F74
0x140078f66  xor     r8d, r8d
0x140078f69  mov     dl, r10b
0x140078f6c  mov     rcx, rbx
0x140078f6f  call    BLFlushBatchOpContextEx
0x140078f74  mov     eax, [rbx+8]
0x140078f77  and     eax, 5
0x140078f7a  cmp     al, 5
0x140078f7c  jz      short loc_140078F8C
0x140078f7e  mov     eax, [rbx+8]
0x140078f81  and     eax, 6
0x140078f84  cmp     al, 6
0x140078f86  jnz     loc_1400790F8
0x140078f8c  mov     rax, [rdi]
0x140078f8f  mov     rax, [rax+20h]
0x140078f93  call    _guard_dispatch_icall
0x140078f98  mov     [r14], si
0x140078f9c  mov     rax, [rdi]
0x140078f9f  mov     rax, [rax+28h]
0x140078fa3  call    _guard_dispatch_icall
0x140078fa8  jmp     loc_1400790FC
0x140078fad  mov     r8, [rbx+20h]
0x140078fb1  mov     ebp, [r8+8]
0x140078fb5  cmp     ebp, [r8+0Ch]
0x140078fb9  jb      loc_140079077
0x140078fbf  xor     ebp, ebp
0x140078fc1  cmp     [rbx+10h], eax
0x140078fc4  jb      short loc_140078FCB
0x140078fc6  mov     dl, r10b
0x140078fc9  jmp     short loc_140078FE5
0x140078fcb  add     rcx, 40h ; '@'; Lookaside
0x140078fcf  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140078fd6  nop     dword ptr [rax+rax+00h]
0x140078fdb  mov     r8, rax
0x140078fde  test    rax, rax
0x140078fe1  jnz     short loc_140078FFC
0x140078fe3  mov     dl, 1
0x140078fe5  xor     r8d, r8d
0x140078fe8  mov     rcx, rbx
0x140078feb  call    BLFlushBatchOpContextEx
0x140078ff0  lea     r8, [rbx+38h]
0x140078ff4  mov     r10d, 1
0x140078ffa  jmp     short loc_140079077
0x140078ffc  mov     [rax], rbp
0x140078fff  mov     r10d, 1
0x140079005  mov     [rax+8], ebp
0x140079008  mov     rax, [rdi]
0x14007900b  mov     ecx, [rax+8]
0x14007900e  lea     rax, [r8+18h]
0x140079012  mov     [r8+10h], rax
0x140079016  mov     [r8+0Ch], ecx
0x14007901a  mov     rax, [rbx+20h]
0x14007901e  mov     [rax], r8
0x140079021  mov     rdx, [rdi]
0x140079024  add     [rbx+10h], r10d
0x140079028  mov     [rbx+20h], r8
0x14007902c  cmp     [rdx+1], r10b
0x140079030  jnz     short loc_140079077
0x140079032  mov     ecx, [rbx+0Ch]
0x140079035  xor     eax, eax
0x140079037  cmp     ecx, 0FFFFFFFFh
0x14007903a  jz      short loc_14007904D
0x14007903c  mov     rdx, [rdx+18h]
0x140079040  test    rdx, rdx
0x140079043  jz      short loc_14007904D
0x140079045  lea     rcx, [rcx+rcx*4]
0x140079049  lea     rax, [rdx+rcx*4]
0x14007904d  lock add [rax+0Ch], r10w
0x140079053  mov     r9d, [rbx+0Ch]
0x140079057  xor     ecx, ecx
0x140079059  cmp     r9d, 0FFFFFFFFh
0x14007905d  jz      short loc_140079073
0x14007905f  mov     rax, [rdi]
0x140079062  mov     rdx, [rax+18h]
0x140079066  test    rdx, rdx
0x140079069  jz      short loc_140079073
0x14007906b  lea     rcx, [r9+r9*4]
0x14007906f  lea     rcx, [rdx+rcx*4]
0x140079073  lock add [rcx], r10d
0x140079077  add     [rbx+14h], r10d
0x14007907b  add     [r8+8], r10d
0x14007907f  mov     rcx, [rdi]
0x140079082  cmp     [rcx+1], r10b
0x140079086  jnz     short loc_1400790D0
0x140079088  mov     r9d, [rbx+0Ch]
0x14007908c  xor     eax, eax
0x14007908e  cmp     r9d, 0FFFFFFFFh
0x140079092  jz      short loc_1400790A5
0x140079094  mov     rdx, [rcx+18h]
0x140079098  test    rdx, rdx
0x14007909b  jz      short loc_1400790A5
0x14007909d  lea     rcx, [r9+r9*4]
0x1400790a1  lea     rax, [rdx+rcx*4]
0x1400790a5  lock add [rax+0Eh], r10w
0x1400790ab  mov     r9d, [rbx+0Ch]
0x1400790af  xor     ecx, ecx
0x1400790b1  cmp     r9d, 0FFFFFFFFh
0x1400790b5  jz      short loc_1400790CB
0x1400790b7  mov     rax, [rdi]
0x1400790ba  mov     rdx, [rax+18h]
0x1400790be  test    rdx, rdx
0x1400790c1  jz      short loc_1400790CB
0x1400790c3  lea     rcx, [r9+r9*4]
0x1400790c7  lea     rcx, [rdx+rcx*4]
0x1400790cb  lock add [rcx+4], r10d
0x1400790d0  mov     rcx, [r8+10h]
0x1400790d4  mov     eax, ebp
0x1400790d6  lea     rdx, [rax+rax*2]
0x1400790da  mov     eax, [rcx+rdx*8+10h]
0x1400790de  mov     rbp, [rsp+68h+arg_8]
0x1400790e3  and     eax, 0FFFFFFF2h
0x1400790e6  or      eax, 2
0x1400790e9  mov     [rcx+rdx*8], r14
0x1400790ed  mov     [rcx+rdx*8+10h], eax
0x1400790f1  mov     [rcx+rdx*8+8], si
0x1400790f6  jmp     short loc_1400790FC
0x1400790f8  mov     [r14], si
0x1400790fc  mov     r10b, [rbp+17h]
0x140079100  test    r10b, 4
0x140079104  jnz     loc_140079B85
0x14007910a  cmp     r15d, [rbp+8]
0x14007910e  jnz     short loc_140079120
0x140079110  movzx   r9d, word ptr [rbp+4]
0x140079115  sub     r9w, [rsp+68h+arg_28]
0x14007911e  jmp     short loc_140079125
0x140079120  movzx   r9d, word ptr [rbp+0]
0x140079125  mov     ecx, 8; usAugend
0x14007912a  lea     r8, [rsp+68h+pusResult]; pusResult
0x140079132  movzx   edx, r9w; usAddend
0x140079136  call    RtlUShortAdd
0x14007913b  mov     [rsp+68h+var_48], eax
0x14007913f  test    eax, eax
0x140079141  js      loc_140079B89
0x140079147  movzx   esi, word ptr [rbp+0Ch]
0x14007914b  lea     r11d, [rcx-7]
0x14007914f  movzx   r15d, [rsp+68h+pusResult]
0x140079158  test    esi, esi
0x14007915a  jnz     short loc_14007916B
0x14007915c  test    r11b, r10b
0x14007915f  jz      short loc_14007918A
0x140079161  mov     eax, 0C0230015h
0x140079166  jmp     loc_140079B89
0x14007916b  movzx   eax, r15w
0x14007916f  ror     ax, 8
0x140079173  movzx   edx, ax
0x140079176  add     edx, esi
0x140079178  movzx   eax, dx
0x14007917b  mov     esi, edx
0x14007917d  shr     esi, 10h
0x140079180  add     esi, eax
0x140079182  mov     eax, 0FFFFh
0x140079187  cmovz   esi, eax
0x14007918a  add     r12w, r9w
0x14007918e  lea     r14, [r13+6]
0x140079192  test    rbx, rbx
0x140079195  jz      loc_140079377
0x14007919b  mov     rcx, [rbx+50h]
0x14007919f  cmp     [rcx+1], r11b
0x1400791a3  jnz     short loc_1400791D2
0x1400791a5  cmp     byte ptr [rbx+4], 0
0x1400791a9  jnz     short loc_1400791D2
0x1400791ab  mov     r8d, [rbx+0Ch]
0x1400791af  xor     eax, eax
0x1400791b1  mov     [rbx+4], r11b
0x1400791b5  cmp     r8d, 0FFFFFFFFh
0x1400791b9  jz      short loc_1400791CC
0x1400791bb  mov     rdx, [rcx+18h]
0x1400791bf  test    rdx, rdx
0x1400791c2  jz      short loc_1400791CC
0x1400791c4  lea     rcx, [r8+r8*4]
0x1400791c8  lea     rax, [rdx+rcx*4]
0x1400791cc  lock add [rax+10h], r11w
0x1400791d2  lea     rdi, [rbx+50h]
0x1400791d6  mov     rcx, [rdi]
0x1400791d9  mov     eax, [rcx+4]
0x1400791dc  test    eax, eax
0x1400791de  jnz     short loc_14007922C
0x1400791e0  cmp     [rbx+14h], eax
0x1400791e3  jz      short loc_1400791F3
0x1400791e5  xor     r8d, r8d
0x1400791e8  mov     dl, r11b
0x1400791eb  mov     rcx, rbx
0x1400791ee  call    BLFlushBatchOpContextEx
0x1400791f3  mov     eax, [rbx+8]
0x1400791f6  and     eax, 5
0x1400791f9  cmp     al, 5
0x1400791fb  jz      short loc_14007920B
0x1400791fd  mov     eax, [rbx+8]
0x140079200  and     eax, 6
0x140079203  cmp     al, 6
0x140079205  jnz     loc_14007937B
0x14007920b  mov     rax, [rdi]
0x14007920e  mov     rax, [rax+20h]
0x140079212  call    _guard_dispatch_icall
0x140079217  mov     [r14], si
0x14007921b  mov     rax, [rdi]
0x14007921e  mov     rax, [rax+28h]
0x140079222  call    _guard_dispatch_icall
0x140079227  jmp     loc_14007937F
0x14007922c  mov     r8, [rbx+20h]
0x140079230  mov     ebp, [r8+8]
0x140079234  cmp     ebp, [r8+0Ch]
0x140079238  jb      loc_1400792F6
0x14007923e  xor     ebp, ebp
0x140079240  cmp     [rbx+10h], eax
0x140079243  jb      short loc_14007924A
0x140079245  mov     dl, r11b
0x140079248  jmp     short loc_140079264
0x14007924a  add     rcx, 40h ; '@'; Lookaside
0x14007924e  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140079255  nop     dword ptr [rax+rax+00h]
0x14007925a  mov     r8, rax
0x14007925d  test    rax, rax
0x140079260  jnz     short loc_14007927B
0x140079262  mov     dl, 1
0x140079264  xor     r8d, r8d
0x140079267  mov     rcx, rbx
0x14007926a  call    BLFlushBatchOpContextEx
0x14007926f  lea     r8, [rbx+38h]
0x140079273  mov     r11d, 1
0x140079279  jmp     short loc_1400792F6
0x14007927b  mov     [rax], rbp
0x14007927e  mov     r11d, 1
0x140079284  mov     [rax+8], ebp
0x140079287  mov     rax, [rdi]
0x14007928a  mov     ecx, [rax+8]
0x14007928d  lea     rax, [r8+18h]
0x140079291  mov     [r8+10h], rax
0x140079295  mov     [r8+0Ch], ecx
0x140079299  mov     rax, [rbx+20h]
0x14007929d  mov     [rax], r8
0x1400792a0  mov     rdx, [rdi]
0x1400792a3  add     [rbx+10h], r11d
0x1400792a7  mov     [rbx+20h], r8
0x1400792ab  cmp     [rdx+1], r11b
0x1400792af  jnz     short loc_1400792F6
0x1400792b1  mov     ecx, [rbx+0Ch]
0x1400792b4  xor     eax, eax
0x1400792b6  cmp     ecx, 0FFFFFFFFh
0x1400792b9  jz      short loc_1400792CC
0x1400792bb  mov     rdx, [rdx+18h]
0x1400792bf  test    rdx, rdx
0x1400792c2  jz      short loc_1400792CC
0x1400792c4  lea     rcx, [rcx+rcx*4]
0x1400792c8  lea     rax, [rdx+rcx*4]
0x1400792cc  lock add [rax+0Ch], r11w
0x1400792d2  mov     r9d, [rbx+0Ch]
0x1400792d6  xor     ecx, ecx
  ... truncated ...
```
