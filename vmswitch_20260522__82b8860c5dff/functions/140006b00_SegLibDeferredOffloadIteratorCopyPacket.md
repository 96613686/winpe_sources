# SegLibDeferredOffloadIteratorCopyPacket

- ea: `0x140006b00`
- end: `0x1400082af`
- name: `SegLibDeferredOffloadIteratorCopyPacket`
- size: `6063`
- prototype: `__int64 __fastcall(int)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x140033a48`
- `0x1400637dc`
- `0x140085e80`

## callees

- `0x140003fcc`
- `0x140004b70`
- `0x140006620`
- `0x140006b00`
- `0x1400082b8`
- `0x1401bbcb0`
- `0x1401bbe10`
- `0x1401bbfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400073bb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140007475`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140007643`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140007933`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140007a34`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140007bca`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400073bb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140007475`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140007643`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140007933`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140007a34`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140007bca`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140007617`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400077e3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140007812`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140007a0c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140007b88`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140007d83`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140007617`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400077e3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140007812`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140007a0c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140007b88`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140007d83`

## pseudocode

```c
__int64 __fastcall SegLibDeferredOffloadIteratorCopyPacket(__int64 a1, __int64 a2, __int64 a3, char *a4)
{
  char *v4; // r10
  __int64 v5; // rdi
  __int64 v7; // r13
  unsigned int v8; // ebp
  struct _MDL *v9; // r14
  unsigned int i; // r15d
  unsigned int ByteCount; // eax
  char *MappedSystemVa; // rax
  unsigned int v13; // ecx
  char *v14; // r9
  unsigned int v15; // r12d
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 *v19; // r15
  unsigned int v20; // eax
  _DWORD *v21; // rdx
  unsigned int v22; // r11d
  __int64 v23; // r10
  __int64 v24; // rax
  __int64 v25; // r10
  __int64 v26; // rcx
  __int64 v27; // r15
  __int64 v28; // rcx
  __int64 v29; // rax
  char *v30; // r10
  int v31; // eax
  __int64 v32; // r14
  struct _MDL *v33; // rsi
  unsigned int j; // ebp
  unsigned int v35; // eax
  char *v36; // rax
  unsigned int v37; // r14d
  unsigned int v38; // ecx
  char *v39; // r12
  char *k; // r9
  unsigned int v41; // ebp
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rcx
  unsigned int v45; // eax
  _DWORD *v46; // rdx
  unsigned int v47; // r10d
  __int64 v48; // rcx
  __int64 v49; // r9
  __int64 v50; // rax
  __int64 v51; // r9
  __int64 v52; // rcx
  __int64 v53; // r15
  __int64 v54; // rcx
  __int64 v55; // rax
  struct _MDL *v56; // rsi
  unsigned int m; // ebp
  unsigned int v58; // eax
  unsigned int v59; // r15d
  char *v60; // rax
  unsigned int v61; // ecx
  unsigned int v62; // ecx
  char *v63; // r10
  __int64 v64; // rdx
  char *v65; // rbp
  __int64 v66; // r9
  size_t v67; // r14
  __int64 v68; // rax
  __int64 v69; // r8
  __int64 v70; // rcx
  __int64 v71; // rcx
  unsigned int v72; // eax
  __int64 v73; // rdx
  __int64 v74; // rcx
  __int64 v75; // r11
  __int64 v76; // rax
  __int64 v77; // r9
  __int64 v78; // rcx
  __int64 v79; // r9
  __int64 v80; // rcx
  __int64 v81; // rax
  char v82; // r12
  bool v83; // zf
  __int64 v84; // rax
  unsigned __int16 v85; // si
  __int64 v86; // rcx
  unsigned int v87; // eax
  _DWORD *v88; // rdx
  unsigned int v89; // ebp
  __int64 v90; // rcx
  __int64 v91; // r10
  __int64 v92; // rax
  __int64 v93; // r9
  __int64 v94; // r9
  __int64 v95; // rcx
  __int64 v96; // r8
  __int64 v97; // rdx
  int v98; // eax
  unsigned int v99; // eax
  int v100; // edx
  __int64 v102; // rax
  unsigned int v103; // edi
  unsigned __int64 v104; // r14
  unsigned int v105; // esi
  __int64 v106; // rdx
  __int16 *v107; // r15
  __int64 v108; // rax
  __int64 v109; // rcx
  __int64 *v110; // rdi
  unsigned int v111; // eax
  _DWORD *v112; // r8
  unsigned int v113; // ebp
  __int64 v114; // r10
  __int64 v115; // rax
  __int64 v116; // r9
  __int64 v117; // rcx
  __int64 v118; // r9
  __int64 v119; // rcx
  __int64 v120; // rax
  _DWORD *v121; // rax
  int v122; // ecx
  __int64 v123; // r9
  __int64 v124; // rcx
  __int64 v125; // rax
  __int64 v126; // r9
  __int64 v127; // rcx
  __int64 v128; // r9
  volatile signed __int32 *v129; // r14
  _DWORD *v130; // rax
  int v131; // ecx
  __int64 v132; // rdx
  __int64 v133; // rcx
  __int64 v134; // rax
  __int64 v135; // rdx
  __int64 v136; // rcx
  __int64 v137; // rdx
  __int64 v138; // rax
  __int64 v139; // rcx
  unsigned int v140; // eax
  unsigned int v141; // r12d
  __int64 v142; // rcx
  __int64 v143; // r11
  __int64 v144; // rdx
  __int64 v145; // rax
  __int64 v146; // r9
  __int64 v147; // rcx
  __int64 v148; // r9
  __int64 v149; // rax
  __int64 v150; // rdx
  int v151; // ecx
  unsigned int v152; // ecx
  _DWORD *v153; // rax
  int v154; // ecx
  __int64 v155; // r9
  __int64 v156; // rcx
  __int64 v157; // rax
  __int64 v158; // r9
  __int64 v159; // r10
  volatile signed __int32 *v160; // rcx
  __int64 v161; // r9
  bool v162; // bp
  __int16 *v163; // rcx
  __int16 v164; // ax
  char *v165; // rax
  unsigned __int16 v166; // si
  _DWORD *v167; // rax
  int v168; // ecx
  __int64 v169; // rcx
  __int64 v170; // rax
  __int64 v171; // r9
  volatile signed __int32 *v172; // rcx
  _DWORD *v173; // rax
  int v174; // ecx
  __int64 v175; // r9
  __int64 v176; // rcx
  __int64 v177; // rax
  __int64 v178; // r9
  __int64 v179; // r10
  volatile signed __int32 *v180; // rcx
  __int64 v181; // r9
  bool v182; // al
  __int16 *v183; // r8
  volatile signed __int32 *v184; // r14
  _DWORD *v185; // rax
  int v186; // ecx
  __int64 v187; // rdx
  __int64 v188; // rcx
  __int64 v189; // rax
  __int64 v190; // rdx
  __int64 v191; // rcx
  __int64 v192; // rdx
  bool v193; // r12
  __int16 *v194; // rdx
  unsigned __int16 v195; // ax
  __int16 v196; // ax
  unsigned __int16 v197; // ax
  __int16 v198; // ax
  __int16 v199; // ax
  unsigned __int16 v200; // di
  __int16 *v201; // r8
  __int16 v202; // cx
  __int16 v203; // cx
  __int16 v204; // cx
  __int16 v205; // cx
  __int16 *v206; // rdx
  __int16 v207; // cx
  __int16 v208; // cx
  __int16 v209; // dx
  __int16 v210; // dx
  __int16 *v211; // rdx
  __int16 v212; // cx
  __int16 v213; // cx
  __int16 v214; // cx
  __int64 v215; // r8
  __int64 v216; // rcx
  __int64 v217; // r8
  __int64 v218; // rcx
  __int64 v219; // r10
  __int64 v220; // rcx
  __int64 v221; // r9
  __int16 v222; // cx
  unsigned int v223; // [rsp+30h] [rbp-68h]
  int v224; // [rsp+34h] [rbp-64h]
  unsigned int v225; // [rsp+38h] [rbp-60h]
  unsigned int v226; // [rsp+38h] [rbp-60h]
  unsigned int v227; // [rsp+40h] [rbp-58h]
  char *Src; // [rsp+48h] [rbp-50h]
  char *Srca; // [rsp+48h] [rbp-50h]
  __int16 *Srcb; // [rsp+48h] [rbp-50h]
  char *v231; // [rsp+50h] [rbp-48h]
  __int16 *n; // [rsp+50h] [rbp-48h]
  __int64 v233; // [rsp+58h] [rbp-40h]
  char v234; // [rsp+A8h] [rbp+10h]

  v4 = a4;
  v5 = a2;
  if ( *(_BYTE *)(a2 + 109) || *(_BYTE *)(a2 + 113) )
    return SegLibOffloadIteratorDeferredCopyFragment();
  v7 = *(_QWORD *)(a2 + 32);
  if ( !*(_BYTE *)(a2 + 115) )
    goto LABEL_4;
  v31 = *(_DWORD *)a2;
  if ( (*(_DWORD *)a2 & 4) == 0 )
  {
    if ( (v31 & 8) == 0 )
    {
LABEL_4:
      v8 = *(_DWORD *)(v7 + 24);
      if ( v8 )
      {
        v9 = *(struct _MDL **)(v7 + 8);
        for ( i = *(_DWORD *)(v7 + 16); v9; i -= ByteCount )
        {
          ByteCount = v9->ByteCount;
          if ( ByteCount > i )
            break;
          v9 = v9->Next;
        }
        v227 = 0;
        if ( (v9->MdlFlags & 5) != 0 )
        {
          MappedSystemVa = (char *)v9->MappedSystemVa;
        }
        else
        {
          MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v9, 0, MmCached, 0, 0, 0x40000000u);
          v4 = a4;
        }
        if ( MappedSystemVa )
        {
          v13 = v9->ByteCount - i;
          v14 = &MappedSystemVa[i];
          v231 = v14;
          while ( 1 )
          {
            Src = v4;
            v15 = v8;
            if ( v13 <= v8 )
              v15 = v13;
            if ( !a1 )
              break;
            v16 = *(_QWORD *)(a1 + 80);
            if ( *(_BYTE *)(v16 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
            {
              a3 = *(unsigned int *)(a1 + 12);
              v17 = 0;
              *(_BYTE *)(a1 + 4) = 1;
              if ( (_DWORD)a3 != -1 )
              {
                a2 = *(_QWORD *)(v16 + 24);
                if ( a2 )
                  v17 = a2 + 20 * a3;
              }
              _InterlockedIncrement16((volatile signed __int16 *)(v17 + 16));
            }
            v18 = *(_QWORD *)(a1 + 80);
            v19 = (__int64 *)(a1 + 80);
            v20 = *(_DWORD *)(v18 + 4);
            if ( v20 )
            {
              v21 = *(_DWORD **)(a1 + 32);
              v22 = v21[2];
              if ( v22 >= v21[3] )
              {
                if ( *(_DWORD *)(a1 + 16) < v20
                  && (v167 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v18 + 64)), (v21 = v167) != 0) )
                {
                  *(_QWORD *)v167 = 0;
                  v167[2] = 0;
                  v168 = *(_DWORD *)(*v19 + 8);
                  *((_QWORD *)v167 + 2) = v167 + 6;
                  v167[3] = v168;
                  **(_QWORD **)(a1 + 32) = v167;
                  a3 = *v19;
                  ++*(_DWORD *)(a1 + 16);
                  *(_QWORD *)(a1 + 32) = v167;
                  if ( *(_BYTE *)(a3 + 1) == 1 )
                  {
                    v169 = *(unsigned int *)(a1 + 12);
                    v170 = 0;
                    if ( (_DWORD)v169 != -1 )
                    {
                      a3 = *(_QWORD *)(a3 + 24);
                      if ( a3 )
                        v170 = a3 + 20 * v169;
                    }
                    _InterlockedIncrement16((volatile signed __int16 *)(v170 + 12));
                    v171 = *(unsigned int *)(a1 + 12);
                    v172 = 0;
                    if ( (_DWORD)v171 != -1 )
                    {
                      a3 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
                      if ( a3 )
                        v172 = (volatile signed __int32 *)(a3 + 20 * v171);
                    }
                    _InterlockedIncrement(v172);
                    v19 = (__int64 *)(a1 + 80);
                  }
                  v4 = Src;
                  v22 = 0;
                  v14 = v231;
                }
                else
                {
                  LOBYTE(v21) = 1;
                  BLFlushBatchOpContextEx(a1, v21, 0);
                  v4 = Src;
                  v21 = (_DWORD *)(a1 + 56);
                  v14 = v231;
                  v22 = 0;
                }
              }
              ++*(_DWORD *)(a1 + 20);
              ++v21[2];
              if ( *(_BYTE *)(*v19 + 1) == 1 )
              {
                v23 = *(unsigned int *)(a1 + 12);
                v24 = 0;
                if ( (_DWORD)v23 != -1 )
                {
                  a3 = *(_QWORD *)(*v19 + 24);
                  if ( a3 )
                    v24 = a3 + 20 * v23;
                }
                _InterlockedIncrement16((volatile signed __int16 *)(v24 + 14));
                v25 = *(unsigned int *)(a1 + 12);
                v26 = 0;
                if ( (_DWORD)v25 != -1 )
                {
                  a3 = *(_QWORD *)(*v19 + 24);
                  if ( a3 )
                    v26 = a3 + 20 * v25;
                }
                _InterlockedIncrement((volatile signed __int32 *)(v26 + 4));
                v4 = Src;
              }
              v27 = v15;
              v28 = 3LL * v22;
              v29 = *((_QWORD *)v21 + 2);
              *(_QWORD *)(v29 + 8 * v28) = v4;
              *(_QWORD *)(v29 + 8 * v28 + 8) = v14;
              a2 = v29 + 24LL * v22;
              *(_DWORD *)(a2 + 16) = (16 * v15) | 1;
            }
            else
            {
              if ( *(_DWORD *)(a1 + 20) )
              {
                LOBYTE(a2) = 1;
                BLFlushBatchOpContextEx(a1, a2, 0);
                v14 = v231;
                v19 = (__int64 *)(a1 + 80);
                v4 = Src;
              }
              if ( (*(_BYTE *)(a1 + 8) & 5) != 5 && (*(_BYTE *)(a1 + 8) & 6) != 6 )
                break;
              (*(void (**)(void))(*v19 + 32))();
              memmove(Src, v231, v15);
              (*(void (**)(void))(*v19 + 40))();
              v27 = v15;
            }
LABEL_31:
            v8 -= v15;
            if ( !v8 )
              goto LABEL_32;
            v9 = v9->Next;
            if ( (v9->MdlFlags & 5) != 0 )
              v14 = (char *)v9->MappedSystemVa;
            else
              v14 = (char *)MmMapLockedPagesSpecifyCache(v9, 0, MmCached, 0, 0, 0x40000000u);
            v231 = v14;
            if ( !v14 )
              goto LABEL_154;
            v13 = v9->ByteCount;
            v4 = &Src[v27];
          }
          v27 = v15;
          memmove(v4, v14, v15);
          goto LABEL_31;
        }
LABEL_154:
        LOBYTE(a3) = 1;
        BLFlushBatchOpContextEx(a1, 0, a3);
        return (unsigned int)-1073741670;
      }
LABEL_239:
      v227 = 0;
      goto LABEL_32;
    }
    LOWORD(a2) = *(_WORD *)(a2 + 118);
    if ( !(_WORD)a2 )
      LOWORD(a2) = HIWORD(v31) & 0x3FF;
    v32 = (unsigned __int16)a2;
    v233 = (unsigned __int16)a2;
    if ( *(unsigned int *)(v7 + 24) < (unsigned __int64)(unsigned __int16)a2 + 8 )
      return (unsigned int)-1073741789;
    a2 = (unsigned __int16)a2;
    v225 = a2;
    if ( (_WORD)a2 )
    {
      v33 = *(struct _MDL **)(v7 + 8);
      for ( j = *(_DWORD *)(v7 + 16); v33; j -= v35 )
      {
        v35 = v33->ByteCount;
        if ( v35 > j )
          break;
        v33 = v33->Next;
      }
      v227 = 0;
      if ( (v33->MdlFlags & 5) != 0 )
      {
        v36 = (char *)v33->MappedSystemVa;
      }
      else
      {
        v36 = (char *)MmMapLockedPagesSpecifyCache(v33, 0, MmCached, 0, 0, 0x40000000u);
        a2 = v225;
        v4 = a4;
      }
      if ( !v36 )
        goto LABEL_154;
      v37 = a2;
      v38 = v33->ByteCount - j;
      v39 = &v36[j];
      for ( k = v4; ; k = &Srca[v53] )
      {
        Srca = k;
        v41 = v37;
        if ( v38 <= v37 )
          v41 = v38;
        if ( !a1 )
        {
LABEL_127:
          v53 = v41;
          memmove(k, v39, v41);
          goto LABEL_65;
        }
        v42 = *(_QWORD *)(a1 + 80);
        if ( *(_BYTE *)(v42 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
        {
          a3 = *(unsigned int *)(a1 + 12);
          v43 = 0;
          *(_BYTE *)(a1 + 4) = 1;
          if ( (_DWORD)a3 != -1 )
          {
            a2 = *(_QWORD *)(v42 + 24);
            if ( a2 )
              v43 = a2 + 20 * a3;
          }
          _InterlockedIncrement16((volatile signed __int16 *)(v43 + 16));
        }
        v44 = *(_QWORD *)(a1 + 80);
        v45 = *(_DWORD *)(v44 + 4);
        if ( v45 )
          break;
        if ( *(_DWORD *)(a1 + 20) )
        {
          LOBYTE(a2) = 1;
          BLFlushBatchOpContextEx(a1, a2, 0);
          k = Srca;
        }
        if ( (*(_BYTE *)(a1 + 8) & 5) != 5 && (*(_BYTE *)(a1 + 8) & 6) != 6 )
          goto LABEL_127;
        (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
        memmove(Srca, v39, v41);
        (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
        v53 = v41;
LABEL_65:
        v37 -= v41;
        if ( !v37 )
        {
          LODWORD(a2) = v225;
          a3 = 0;
          v32 = v233;
          goto LABEL_67;
        }
        v33 = v33->Next;
        if ( (v33->MdlFlags & 5) != 0 )
          v39 = (char *)v33->MappedSystemVa;
        else
          v39 = (char *)MmMapLockedPagesSpecifyCache(v33, 0, MmCached, 0, 0, 0x40000000u);
        if ( !v39 )
          goto LABEL_154;
        v38 = v33->ByteCount;
      }
      v46 = *(_DWORD **)(a1 + 32);
      v47 = v46[2];
      if ( v47 < v46[3] )
      {
LABEL_56:
        ++*(_DWORD *)(a1 + 20);
        ++v46[2];
        v48 = *(_QWORD *)(a1 + 80);
        if ( *(_BYTE *)(v48 + 1) == 1 )
        {
          v49 = *(unsigned int *)(a1 + 12);
          v50 = 0;
          if ( (_DWORD)v49 != -1 )
          {
            a3 = *(_QWORD *)(v48 + 24);
            if ( a3 )
              v50 = a3 + 20 * v49;
          }
          _InterlockedIncrement16((volatile signed __int16 *)(v50 + 14));
          v51 = *(unsigned int *)(a1 + 12);
          v52 = 0;
          if ( (_DWORD)v51 != -1 )
          {
            a3 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
            if ( a3 )
              v52 = a3 + 20 * v51;
          }
          _InterlockedIncrement((volatile signed __int32 *)(v52 + 4));
          k = Srca;
        }
        v53 = v41;
        v54 = 3LL * v47;
        v55 = *((_QWORD *)v46 + 2);
        *(_QWORD *)(v55 + 8 * v54) = k;
        *(_QWORD *)(v55 + 8 * v54 + 8) = v39;
        a2 = v55 + 24LL * v47;
        *(_DWORD *)(a2 + 16) = (16 * v41) | 1;
        goto LABEL_65;
      }
      v46 = 0;
      if ( *(_DWORD *)(a1 + 16) < v45
        && (v121 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v44 + 64)), (v46 = v121) != 0) )
      {
        a3 = 0;
        *(_QWORD *)v121 = 0;
        v121[2] = 0;
        v122 = *(_DWORD *)(*(_QWORD *)(a1 + 80) + 8LL);
        *((_QWORD *)v121 + 2) = v121 + 6;
        v121[3] = v122;
        **(_QWORD **)(a1 + 32) = v121;
        v123 = *(_QWORD *)(a1 + 80);
        ++*(_DWORD *)(a1 + 16);
        *(_QWORD *)(a1 + 32) = v121;
        if ( *(_BYTE *)(v123 + 1) != 1 )
        {
          v47 = 0;
          goto LABEL_174;
        }
        v124 = *(unsigned int *)(a1 + 12);
        v125 = 0;
        if ( (_DWORD)v124 != -1 )
        {
          v126 = *(_QWORD *)(v123 + 24);
          if ( v126 )
            v125 = v126 + 20 * v124;
        }
        _InterlockedIncrement16((volatile signed __int16 *)(v125 + 12));
        v127 = *(unsigned int *)(a1 + 12);
        if ( (_DWORD)v127 != -1 )
        {
          v128 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
          if ( v128 )
            a3 = v128 + 20 * v127;
        }
        _InterlockedIncrement((volatile signed __int32 *)a3);
      }
      else
      {
        LOBYTE(v46) = 1;
        BLFlushBatchOpContextEx(a1, v46, 0);
        v46 = (_DWORD *)(a1 + 56);
      }
      v47 = 0;
LABEL_174:
      k = Srca;
      goto LABEL_56;
    }
    a3 = 0;
    v227 = 0;
LABEL_67:
    v56 = *(struct _MDL **)(v7 + 8);
    for ( m = a2 + *(_DWORD *)(v7 + 16); v56; m -= v58 )
    {
      v58 = v56->ByteCount;
      if ( v58 > m )
        break;
      v56 = v56->Next;
    }
    v59 = *(_DWORD *)(v7 + 24) - a2;
    if ( !v59 )
      goto LABEL_32;
    if ( v56 )
    {
      v234 = *(_BYTE *)(v5 + 116);
      if ( (v56->MdlFlags & 5) != 0 )
        v60 = (char *)v56->MappedSystemVa;
      else
        v60 = (char *)MmMapLockedPagesSpecifyCache(v56, 0, MmCached, 0, 0, 0x40000000u);
      if ( v60 )
      {
        v61 = v56->ByteCount;
        if ( v61 > m )
        {
          v62 = v61 - m;
          v63 = &v60[m];
          v64 = v59;
          Srcb = (__int16 *)v63;
          v65 = &a4[v32];
          v226 = v59;
          v66 = (__int64)&a4[v32 + 6];
          for ( n = (__int16 *)v66; ; v66 = (__int64)n )
          {
            v67 = (unsigned int)v64;
            if ( v62 <= (unsigned int)v64 )
              v67 = v62;
            v223 = v67;
            if ( v65 )
              break;
            v138 = *(_QWORD *)(a1 + 80);
            if ( *(_BYTE *)(v138 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
            {
              v215 = *(unsigned int *)(a1 + 12);
              v216 = 0;
              *(_BYTE *)(a1 + 4) = 1;
              if ( (_DWORD)v215 != -1 )
              {
                v64 = *(_QWORD *)(v138 + 24);
                if ( v64 )
                  v216 = v64 + 20 * v215;
              }
              _InterlockedIncrement16((volatile signed __int16 *)(v216 + 16));
            }
            v139 = *(_QWORD *)(a1 + 80);
            v140 = *(_DWORD *)(v139 + 4);
            if ( v140 )
            {
              a3 = *(_QWORD *)(a1 + 32);
              v141 = *(_DWORD *)(a3 + 8);
              if ( v141 >= *(_DWORD *)(a3 + 12) )
              {
                v184 = 0;
                v141 = 0;
                if ( *(_DWORD *)(a1 + 16) < v140
                  && (v185 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v139 + 64)),
                      (a3 = (__int64)v185) != 0) )
                {
                  *(_QWORD *)v185 = 0;
                  v185[2] = 0;
                  v186 = *(_DWORD *)(*(_QWORD *)(a1 + 80) + 8LL);
                  *((_QWORD *)v185 + 2) = v185 + 6;
                  v185[3] = v186;
                  **(_QWORD **)(a1 + 32) = v185;
                  v187 = *(_QWORD *)(a1 + 80);
                  ++*(_DWORD *)(a1 + 16);
                  *(_QWORD *)(a1 + 32) = v185;
                  if ( *(_BYTE *)(v187 + 1) == 1 )
                  {
                    v188 = *(unsigned int *)(a1 + 12);
                    v189 = 0;
                    if ( (_DWORD)v188 != -1 )
                    {
                      v190 = *(_QWORD *)(v187 + 24);
                      if ( v190 )
                        v189 = v190 + 20 * v188;
                    }
                    _InterlockedIncrement16((volatile signed __int16 *)(v189 + 12));
                    v191 = *(unsigned int *)(a1 + 12);
                    if ( (_DWORD)v191 != -1 )
                    {
                      v192 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
                      if ( v192 )
                        v184 = (volatile signed __int32 *)(v192 + 20 * v191);
                    }
                    _InterlockedIncrement(v184);
                  }
                  LODWORD(v67) = v223;
                  v63 = (char *)Srcb;
                }
                else
                {
                  LOBYTE(v64) = 1;
                  BLFlushBatchOpContextEx(a1, v64, 0);
                  v63 = (char *)Srcb;
                  a3 = a1 + 56;
                  LODWORD(v67) = v223;
                }
              }
              ++*(_DWORD *)(a1 + 20);
              ++*(_DWORD *)(a3 + 8);
              v142 = *(_QWORD *)(a1 + 80);
              if ( *(_BYTE *)(v142 + 1) == 1 )
              {
                v143 = *(unsigned int *)(a1 + 12);
                v144 = 0;
                v145 = 0;
                if ( (_DWORD)v143 != -1 )
                {
                  v146 = *(_QWORD *)(v142 + 24);
                  if ( v146 )
                    v145 = v146 + 20 * v143;
                }
                _InterlockedIncrement16((volatile signed __int16 *)(v145 + 14));
                v147 = *(unsigned int *)(a1 + 12);
                if ( (_DWORD)v147 != -1 )
                {
                  v148 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
                  if ( v148 )
                    v144 = v148 + 20 * v147;
                }
                _InterlockedIncrement((volatile signed __int32 *)(v144 + 4));
              }
              v149 = v141;
              v82 = v234;
              v150 = *(_QWORD *)(a3 + 16) + 24 * v149;
              v151 = *(_DWORD *)(v150 + 16);
              if ( v234 )
                v152 = v151 & 0xFFFFFFF0 | 7;
              else
                v152 = v151 & 0xFFFFFFF0 | 6;
              *(_DWORD *)(v150 + 16) = v152;
              *(_QWORD *)v150 = n;
              *(_QWORD *)(v150 + 8) = v63;
              *(_DWORD *)(v150 + 16) = v152 & 0xF | (16 * v67);
            }
            else
            {
              if ( *(_DWORD *)(a1 + 20) )
              {
                LOBYTE(v64) = 1;
                BLFlushBatchOpContextEx(a1, v64, 0);
                v66 = (__int64)n;
              }
              v193 = (*(_BYTE *)(a1 + 8) & 5) == 5 || (*(_DWORD *)(a1 + 8) & 6) == 6;
              v194 = *(__int16 **)(a1 + 48);
              if ( v194 && v194 != (__int16 *)v66 )
              {
                if ( v193 )
                {
                  (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
                  v201 = *(__int16 **)(a1 + 48);
                  v202 = *v201;
                  if ( (*(_DWORD *)(a1 + 44) & 1) != 0 )
                    v202 = __ROR2__(v202, 8);
                  v203 = ~v202;
                  if ( *(_BYTE *)(a1 + 40) && !v203 )
                    v203 = -1;
                  *v201 = v203;
                  *(_QWORD *)(a1 + 48) = 0;
                  *(_DWORD *)(a1 + 44) = 0;
                  (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
                }
                else
                {
                  v204 = *v194;
                  if ( (*(_DWORD *)(a1 + 44) & 1) != 0 )
                    v204 = __ROR2__(v204, 8);
                  v205 = ~v204;
                  if ( *(_BYTE *)(a1 + 40) && !v205 )
                    v205 = -1;
                  *v194 = v205;
                  *(_DWORD *)(a1 + 44) = 0;
                }
              }
              *(_QWORD *)(a1 + 48) = n;
              *(_BYTE *)(a1 + 40) = v234 != 0;
              if ( v193 )
              {
                (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
                if ( n >= Srcb && n < (__int16 *)((char *)Srcb + (unsigned int)v67) )
                  v197 = 0;
                else
                  v197 = *n;
                v198 = tcpxsum(v197, Srcb, (unsigned int)v67);
                *n = v198;
                if ( (v67 & 1) != 0 )
                {
                  *n = __ROR2__(v198, 8);
                  ++*(_DWORD *)(a1 + 44);
                }
                (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
                v82 = v234;
              }
              else
              {
                if ( n < Srcb || n >= (__int16 *)((char *)Srcb + (unsigned int)v67) )
                  v195 = *n;
                else
                  v195 = 0;
                v196 = tcpxsum(v195, Srcb, (unsigned int)v67);
                *n = v196;
                if ( (v67 & 1) != 0 )
                {
                  *n = __ROR2__(v196, 8);
                  ++*(_DWORD *)(a1 + 44);
                }
                v82 = v234;
              }
            }
LABEL_98:
            v83 = v226 == (_DWORD)v67;
            v64 = v226 - (unsigned int)v67;
            v226 -= v67;
            if ( v83 )
            {
              if ( v65 )
              {
                v84 = *(_QWORD *)(a1 + 80);
                v85 = 0;
                if ( *(_BYTE *)(v84 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
                {
                  v217 = *(unsigned int *)(a1 + 12);
                  v218 = 0;
                  *(_BYTE *)(a1 + 4) = 1;
                  if ( (_DWORD)v217 != -1 )
                  {
                    v64 = *(_QWORD *)(v84 + 24);
                    if ( v64 )
                      v218 = v64 + 20 * v217;
                  }
                  _InterlockedIncrement16((volatile signed __int16 *)(v218 + 16));
                }
                v86 = *(_QWORD *)(a1 + 80);
                v87 = *(_DWORD *)(v86 + 4);
                if ( v87 )
                {
                  v88 = *(_DWORD **)(a1 + 32);
                  v89 = v88[2];
                  if ( v89 >= v88[3] )
                  {
                    v89 = 0;
                    if ( *(_DWORD *)(a1 + 16) < v87
                      && (v153 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v86 + 64)), (v88 = v153) != 0) )
                    {
                      *(_QWORD *)v153 = 0;
                      v153[2] = 0;
                      v154 = *(_DWORD *)(*(_QWORD *)(a1 + 80) + 8LL);
                      *((_QWORD *)v153 + 2) = v153 + 6;
                      v153[3] = v154;
                      **(_QWORD **)(a1 + 32) = v153;
                      v155 = *(_QWORD *)(a1 + 80);
                      ++*(_DWORD *)(a1 + 16);
                      *(_QWORD *)(a1 + 32) = v153;
                      if ( *(_BYTE *)(v155 + 1) == 1 )
                      {
                        v156 = *(unsigned int *)(a1 + 12);
                        v157 = 0;
                        if ( (_DWORD)v156 != -1 )
                        {
                          v158 = *(_QWORD *)(v155 + 24);
                          if ( v158 )
                            v157 = v158 + 20 * v156;
                        }
                        _InterlockedIncrement16((volatile signed __int16 *)(v157 + 12));
                        v159 = *(unsigned int *)(a1 + 12);
                        v160 = 0;
                        if ( (_DWORD)v159 != -1 )
                        {
                          v161 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
                          if ( v161 )
                            v160 = (volatile signed __int32 *)(v161 + 20 * v159);
                        }
                        _InterlockedIncrement(v160);
                      }
                    }
                    else
                    {
                      LOBYTE(v88) = 1;
                      BLFlushBatchOpContextEx(a1, v88, 0);
                      v88 = (_DWORD *)(a1 + 56);
                    }
                  }
                  ++*(_DWORD *)(a1 + 20);
                  ++v88[2];
                  v90 = *(_QWORD *)(a1 + 80);
                  if ( *(_BYTE *)(v90 + 1) == 1 )
                  {
                    v91 = *(unsigned int *)(a1 + 12);
                    v92 = 0;
                    if ( (_DWORD)v91 != -1 )
                    {
                      v93 = *(_QWORD *)(v90 + 24);
                      if ( v93 )
                        v92 = v93 + 20 * v91;
                    }
                    _InterlockedIncrement16((volatile signed __int16 *)(v92 + 14));
                    v94 = *(unsigned int *)(a1 + 12);
                    v95 = 0;
                    if ( (_DWORD)v94 != -1 )
                    {
                      v96 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
                      if ( v96 )
                        v95 = v96 + 20 * v94;
                    }
                    _InterlockedIncrement((volatile signed __int32 *)(v95 + 4));
                  }
                  v97 = *((_QWORD *)v88 + 2) + 24LL * v89;
                  v98 = *(_DWORD *)(v97 + 16);
                  if ( v82 )
                    v99 = v98 & 0xFFFFFFF0 | 7;
                  else
                    v99 = v98 & 0xFFFFFFF0 | 6;
                  v30 = a4;
                  *(_DWORD *)(v97 + 16) = v99;
                  *(_QWORD *)(v97 + 8) = &a4[v233];
                  *(_DWORD *)(v97 + 16) = v99 & 0xF | (16 * v59);
                  a3 = (__int64)&a4[v233 + 6];
                  *(_QWORD *)v97 = a3;
                  goto LABEL_119;
                }
                if ( *(_DWORD *)(a1 + 20) )
                {
                  LOBYTE(v64) = 1;
                  BLFlushBatchOpContextEx(a1, v64, 0);
                }
                v162 = (*(_BYTE *)(a1 + 8) & 5) == 5 || (*(_DWORD *)(a1 + 8) & 6) == 6;
                v163 = *(__int16 **)(a1 + 48);
                if ( v163 && v163 != n )
                {
                  if ( v162 )
                  {
                    (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
                    v206 = *(__int16 **)(a1 + 48);
                    v207 = *v206;
                    if ( (*(_DWORD *)(a1 + 44) & 1) != 0 )
                      v207 = __ROR2__(v207, 8);
                    v208 = ~v207;
                    if ( *(_BYTE *)(a1 + 40) && !v208 )
                      v208 = -1;
                    *v206 = v208;
                    *(_QWORD *)(a1 + 48) = 0;
                    *(_DWORD *)(a1 + 44) = 0;
                    (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
                  }
                  else
                  {
                    v209 = *v163;
                    if ( (*(_DWORD *)(a1 + 44) & 1) != 0 )
                      v209 = __ROR2__(v209, 8);
                    v210 = ~v209;
                    if ( *(_BYTE *)(a1 + 40) && !v210 )
                      v210 = -1;
                    *v163 = v210;
                    *(_DWORD *)(a1 + 44) = 0;
                  }
                }
                *(_BYTE *)(a1 + 40) = v82 != 0;
                *(_QWORD *)(a1 + 48) = n;
                if ( !v162 )
                {
                  if ( n < (__int16 *)&a4[v233] || n >= (__int16 *)&a4[v233 + v59] )
                    v85 = *n;
                  v164 = tcpxsum(v85, &a4[v233], v59);
                  *n = v164;
                  if ( (v59 & 1) != 0 )
                  {
                    v30 = a4;
                    *n = __ROR2__(v164, 8);
                    ++*(_DWORD *)(a1 + 44);
                    goto LABEL_119;
                  }
                  goto LABEL_32;
                }
                (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
                if ( n < (__int16 *)&a4[v233] || n >= (__int16 *)&a4[v233 + v59] )
                  v85 = *n;
                v199 = tcpxsum(v85, &a4[v233], v59);
                *n = v199;
                if ( (v59 & 1) != 0 )
                {
                  *n = __ROR2__(v199, 8);
                  ++*(_DWORD *)(a1 + 44);
                }
                (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
                v30 = a4;
LABEL_119:
                if ( !*(_BYTE *)(v5 + 115) || (*(_DWORD *)v5 & 0x10) == 0 )
                  return v227;
                v102 = *(unsigned __int8 *)(v5 + 108);
                v103 = *(_DWORD *)(v7 + 24) - v102;
                if ( v103 >= 0x14 )
                {
                  LOBYTE(a3) = 1;
                  v104 = (unsigned __int64)&v30[v102];
                  BLFlushBatchOpContextEx(a1, 0, a3);
                  v105 = 4 * (*(_BYTE *)v104 & 0xF);
                  if ( v105 <= v103 )
                  {
                    v106 = 0;
                    v107 = (__int16 *)(v104 + 10);
                    *(_WORD *)(v104 + 10) = 0;
                    v108 = *(_QWORD *)(a1 + 80);
                    if ( *(_BYTE *)(v108 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
                    {
                      v219 = *(unsigned int *)(a1 + 12);
                      v220 = 0;
                      *(_BYTE *)(a1 + 4) = 1;
                      if ( (_DWORD)v219 != -1 )
                      {
                        v221 = *(_QWORD *)(v108 + 24);
                        if ( v221 )
                          v220 = v221 + 20 * v219;
                      }
                      _InterlockedIncrement16((volatile signed __int16 *)(v220 + 16));
                    }
                    v109 = *(_QWORD *)(a1 + 80);
                    v110 = (__int64 *)(a1 + 80);
                    v111 = *(_DWORD *)(v109 + 4);
                    if ( v111 )
                    {
                      v112 = *(_DWORD **)(a1 + 32);
                      v113 = v112[2];
                      if ( v113 >= v112[3] )
                      {
                        v113 = 0;
                        if ( *(_DWORD *)(a1 + 16) < v111
                          && (v173 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v109 + 64)),
                              (v112 = v173) != 0) )
                        {
                          v106 = 0;
                          *(_QWORD *)v173 = 0;
                          v173[2] = 0;
                          v174 = *(_DWORD *)(*v110 + 8);
                          *((_QWORD *)v173 + 2) = v173 + 6;
                          v173[3] = v174;
                          **(_QWORD **)(a1 + 32) = v173;
                          v175 = *v110;
                          ++*(_DWORD *)(a1 + 16);
                          *(_QWORD *)(a1 + 32) = v173;
                          if ( *(_BYTE *)(v175 + 1) == 1 )
                          {
                            v176 = *(unsigned int *)(a1 + 12);
                            v177 = 0;
                            if ( (_DWORD)v176 != -1 )
                            {
                              v178 = *(_QWORD *)(v175 + 24);
                              if ( v178 )
                                v177 = v178 + 20 * v176;
                            }
                            _InterlockedIncrement16((volatile signed __int16 *)(v177 + 12));
                            v179 = *(unsigned int *)(a1 + 12);
                            v180 = 0;
                            if ( (_DWORD)v179 != -1 )
                            {
                              v181 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
                              if ( v181 )
                                v180 = (volatile signed __int32 *)(v181 + 20 * v179);
                            }
                            _InterlockedIncrement(v180);
                            v110 = (__int64 *)(a1 + 80);
                          }
                        }
                        else
                        {
                          LOBYTE(v106) = 1;
                          BLFlushBatchOpContextEx(a1, v106, 0);
                          v106 = 0;
                          v112 = (_DWORD *)(a1 + 56);
                        }
                      }
                      ++*(_DWORD *)(a1 + 20);
                      ++v112[2];
                      if ( *(_BYTE *)(*v110 + 1) == 1 )
                      {
                        v114 = *(unsigned int *)(a1 + 12);
                        v115 = 0;
                        if ( (_DWORD)v114 != -1 )
                        {
                          v116 = *(_QWORD *)(*v110 + 24);
                          if ( v116 )
                            v115 = v116 + 20 * v114;
                        }
                        _InterlockedIncrement16((volatile signed __int16 *)(v115 + 14));
                        v117 = *(unsigned int *)(a1 + 12);
                        if ( (_DWORD)v117 != -1 )
                        {
                          v118 = *(_QWORD *)(*v110 + 24);
                          if ( v118 )
                            v106 = v118 + 20 * v117;
                        }
                        _InterlockedIncrement((volatile signed __int32 *)(v106 + 4));
                      }
                      v119 = 3LL * v113;
                      v120 = *((_QWORD *)v112 + 2);
                      *(_QWORD *)(v120 + 8 * v119 + 8) = v104;
                      *(_QWORD *)(v120 + 8 * v119) = v107;
                      *(_DWORD *)(v120 + 8 * v119 + 16) = (16 * v105) | 6;
                      return v227;
                    }
                    if ( *(_DWORD *)(a1 + 20) )
                    {
                      LOBYTE(v106) = 1;
                      BLFlushBatchOpContextEx(a1, v106, 0);
                      LOWORD(v106) = 0;
                    }
                    v182 = (*(_BYTE *)(a1 + 8) & 5) == 5 || (*(_DWORD *)(a1 + 8) & 6) == 6;
                    v183 = *(__int16 **)(a1 + 48);
                    if ( !v183 || v183 == v107 )
                    {
                      *(_BYTE *)(a1 + 40) = 0;
                      *(_QWORD *)(a1 + 48) = v107;
                      if ( v182 )
                      {
                        v200 = 0;
LABEL_324:
                        (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
                        if ( (unsigned __int64)v107 < v104 || (unsigned __int64)v107 >= v104 + v105 )
                          v200 = *v107;
                        *v107 = tcpxsum(v200, v104, v105);
                        (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
                        return v227;
                      }
                    }
                    else
                    {
                      if ( v182 )
                      {
                        (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
                        v211 = *(__int16 **)(a1 + 48);
                        v212 = *v211;
                        if ( (*(_DWORD *)(a1 + 44) & 1) != 0 )
                          v212 = __ROR2__(v212, 8);
                        v222 = ~v212;
                        if ( *(_BYTE *)(a1 + 40) && !v222 )
                          v222 = -1;
                        v200 = 0;
                        *v211 = v222;
                        *(_QWORD *)(a1 + 48) = 0;
                        *(_DWORD *)(a1 + 44) = 0;
                        (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
                        *(_BYTE *)(a1 + 40) = 0;
                        *(_QWORD *)(a1 + 48) = v107;
                        goto LABEL_324;
                      }
                      v213 = *v183;
                      if ( (*(_DWORD *)(a1 + 44) & 1) != 0 )
                        v213 = __ROR2__(v213, 8);
                      v214 = ~v213;
                      if ( *(_BYTE *)(a1 + 40) && !v214 )
                        v214 = -1;
                      *v183 = v214;
                      *(_QWORD *)(a1 + 48) = 0;
                      *(_DWORD *)(a1 + 44) = 0;
                      *(_BYTE *)(a1 + 40) = 0;
                      *(_QWORD *)(a1 + 48) = v107;
                    }
                    if ( (unsigned __int64)v107 < v104 || (unsigned __int64)v107 >= v104 + v105 )
                      LOWORD(v106) = *v107;
                    *v107 = tcpxsum((unsigned __int16)v106, v104, v105);
                    return v227;
                  }
                }
                return (unsigned int)-2147483643;
              }
LABEL_32:
              v30 = a4;
              goto LABEL_119;
            }
            v56 = v56->Next;
            if ( !v56 )
              goto LABEL_148;
            if ( (v56->MdlFlags & 5) != 0 )
            {
              v63 = (char *)v56->MappedSystemVa;
              Srcb = (__int16 *)v63;
            }
            else
            {
              v165 = (char *)MmMapLockedPagesSpecifyCache(v56, 0, MmCached, 0, 0, 0x40000000u);
              v64 = v226;
              v63 = v165;
              Srcb = (__int16 *)v165;
            }
            if ( !v63 )
              goto LABEL_148;
            v62 = v56->ByteCount;
          }
          if ( !a1 )
            goto LABEL_132;
          v68 = *(_QWORD *)(a1 + 80);
          if ( *(_BYTE *)(v68 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
          {
            v69 = *(unsigned int *)(a1 + 12);
            v70 = 0;
            *(_BYTE *)(a1 + 4) = 1;
            if ( (_DWORD)v69 != -1 )
            {
              v64 = *(_QWORD *)(v68 + 24);
              if ( v64 )
                v70 = v64 + 20 * v69;
            }
            _InterlockedIncrement16((volatile signed __int16 *)(v70 + 16));
          }
          v71 = *(_QWORD *)(a1 + 80);
          v72 = *(_DWORD *)(v71 + 4);
          if ( v72 )
          {
            a3 = *(_QWORD *)(a1 + 32);
            v73 = *(unsigned int *)(a3 + 8);
            v224 = v73;
            if ( (unsigned int)v73 >= *(_DWORD *)(a3 + 12) )
            {
              v129 = 0;
              v224 = 0;
              if ( *(_DWORD *)(a1 + 16) < v72
                && (v130 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v71 + 64)),
                    (a3 = (__int64)v130) != 0) )
              {
                *(_QWORD *)v130 = 0;
                v130[2] = 0;
                v131 = *(_DWORD *)(*(_QWORD *)(a1 + 80) + 8LL);
                *((_QWORD *)v130 + 2) = v130 + 6;
                v130[3] = v131;
                **(_QWORD **)(a1 + 32) = v130;
                v132 = *(_QWORD *)(a1 + 80);
                ++*(_DWORD *)(a1 + 16);
                *(_QWORD *)(a1 + 32) = v130;
                if ( *(_BYTE *)(v132 + 1) == 1 )
                {
                  v133 = *(unsigned int *)(a1 + 12);
                  v134 = 0;
                  if ( (_DWORD)v133 != -1 )
                  {
                    v135 = *(_QWORD *)(v132 + 24);
                    if ( v135 )
                      v134 = v135 + 20 * v133;
                  }
                  _InterlockedIncrement16((volatile signed __int16 *)(v134 + 12));
                  v136 = *(unsigned int *)(a1 + 12);
                  if ( (_DWORD)v136 != -1 )
                  {
                    v137 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
                    if ( v137 )
                      v129 = (volatile signed __int32 *)(v137 + 20 * v136);
                  }
                  _InterlockedIncrement(v129);
                }
                LODWORD(v73) = 0;
                v67 = v223;
                v63 = (char *)Srcb;
              }
              else
              {
                LOBYTE(v73) = 1;
                BLFlushBatchOpContextEx(a1, v73, 0);
                LODWORD(v73) = 0;
                a3 = a1 + 56;
                v63 = (char *)Srcb;
                v67 = v223;
              }
            }
            ++*(_DWORD *)(a1 + 20);
            ++*(_DWORD *)(a3 + 8);
            v74 = *(_QWORD *)(a1 + 80);
            if ( *(_BYTE *)(v74 + 1) == 1 )
            {
              v75 = *(unsigned int *)(a1 + 12);
              v73 = 0;
              v76 = 0;
              if ( (_DWORD)v75 != -1 )
              {
                v77 = *(_QWORD *)(v74 + 24);
                if ( v77 )
                  v76 = v77 + 20 * v75;
              }
              _InterlockedIncrement16((volatile signed __int16 *)(v76 + 14));
              v78 = *(unsigned int *)(a1 + 12);
              if ( (_DWORD)v78 != -1 )
              {
                v79 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
                if ( v79 )
                  v73 = v79 + 20 * v78;
              }
              _InterlockedIncrement((volatile signed __int32 *)(v73 + 4));
              LODWORD(v73) = v224;
            }
            v80 = 3LL * (unsigned int)v73;
            v81 = *(_QWORD *)(a3 + 16);
            *(_QWORD *)(v81 + 8 * v80) = v65;
            *(_QWORD *)(v81 + 8 * v80 + 8) = v63;
            *(_DWORD *)(v81 + 24LL * (unsigned int)v73 + 16) = (16 * v67) | 1;
            goto LABEL_97;
          }
          if ( *(_DWORD *)(a1 + 20) )
          {
            LOBYTE(v64) = 1;
            BLFlushBatchOpContextEx(a1, v64, 0);
            v63 = (char *)Srcb;
          }
          if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (*(_BYTE *)(a1 + 8) & 6) == 6 )
          {
            (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
            memmove(v65, Srcb, v67);
            (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
          }
          else
          {
LABEL_132:
            memmove(v65, v63, v67);
          }
LABEL_97:
          v82 = v234;
          v65 += v67;
          LODWORD(v67) = v223;
          goto LABEL_98;
        }
      }
LABEL_148:
      v227 = -1073741670;
    }
    else
    {
      v227 = -1073741811;
    }
    LOBYTE(a3) = 1;
    BLFlushBatchOpContextEx(a1, 0, a3);
    return v227;
  }
  v166 = *(_WORD *)(a2 + 118);
  if ( !v166 )
    v166 = HIWORD(v31) & 0x3FF;
  if ( *(unsigned int *)(v7 + 24) < (unsigned __int64)v166 + 20 )
    return (unsigned int)-1071448043;
  v100 = SegLibPvtDeferredCopyMdlChainData(a1, *(_QWORD *)(v7 + 8), *(unsigned int *)(v7 + 16), v166, a4);
  if ( v100 >= 0 )
  {
    v100 = SegLibPvtDeferredChecksumTransport(a1, v7, v166, 0, (__int64)&a4[v166 + 16], &a4[v166]);
    if ( v100 >= 0 )
      goto LABEL_239;
  }
  return (unsigned int)v100;
}

```

## disassembly

```asm
0x140006b00  mov     rax, rsp
0x140006b03  mov     [rax+20h], r9
0x140006b07  push    rbx
0x140006b08  push    rdi
0x140006b09  sub     rsp, 88h
0x140006b10  cmp     byte ptr [rdx+6Dh], 0
0x140006b14  mov     r10, r9
0x140006b17  mov     rdi, rdx
0x140006b1a  mov     rbx, rcx
0x140006b1d  jnz     loc_1400072F8
0x140006b23  cmp     byte ptr [rdx+71h], 0
0x140006b27  jnz     loc_1400072F8
0x140006b2d  cmp     byte ptr [rdx+73h], 0
0x140006b31  mov     [rax-28h], r13
0x140006b35  mov     r13, [rdx+20h]
0x140006b39  mov     [rax+8], rbp
0x140006b3d  mov     [rax-18h], rsi
0x140006b41  mov     [rax-20h], r12
0x140006b45  mov     [rax-30h], r14
0x140006b49  mov     [rax-38h], r15
0x140006b4d  jnz     loc_140006CB6
0x140006b53  mov     ebp, [r13+18h]
0x140006b57  test    ebp, ebp
0x140006b59  jz      loc_140007904
0x140006b5f  mov     r14, [r13+8]
0x140006b63  mov     r15d, [r13+10h]
0x140006b67  test    r14, r14
0x140006b6a  jz      short loc_140006B79
0x140006b6c  mov     eax, [r14+28h]
0x140006b70  cmp     eax, r15d
0x140006b73  jbe     loc_140007912
0x140006b79  xor     esi, esi
0x140006b7b  test    byte ptr [r14+0Ah], 5
0x140006b80  mov     [rsp+98h+var_58], rsi
0x140006b85  jz      loc_1400079F2
0x140006b8b  mov     rax, [r14+18h]
0x140006b8f  test    rax, rax
0x140006b92  jz      loc_14000731C
0x140006b98  mov     ecx, [r14+28h]
0x140006b9c  sub     ecx, r15d
0x140006b9f  mov     r9d, r15d
0x140006ba2  add     r9, rax
0x140006ba5  mov     [rsp+98h+var_48], r9
0x140006baa  cmp     ecx, ebp
0x140006bac  mov     [rsp+98h+Src], r10
0x140006bb1  mov     r12d, ebp
0x140006bb4  cmovbe  r12d, ecx
0x140006bb8  test    rbx, rbx
0x140006bbb  jz      loc_14000738F
0x140006bc1  mov     rax, [rbx+50h]
0x140006bc5  cmp     byte ptr [rax+1], 1
0x140006bc9  jnz     short loc_140006BF8
0x140006bcb  cmp     [rbx+4], sil
0x140006bcf  jnz     short loc_140006BF8
0x140006bd1  mov     r8d, [rbx+0Ch]
0x140006bd5  mov     rcx, rsi
0x140006bd8  mov     byte ptr [rbx+4], 1
0x140006bdc  cmp     r8d, 0FFFFFFFFh
0x140006be0  jz      short loc_140006BF3
0x140006be2  mov     rdx, [rax+18h]
0x140006be6  test    rdx, rdx
0x140006be9  jz      short loc_140006BF3
0x140006beb  lea     rcx, [r8+r8*4]
0x140006bef  lea     rcx, [rdx+rcx*4]
0x140006bf3  lock inc word ptr [rcx+10h]
0x140006bf8  mov     rcx, [rbx+50h]
0x140006bfc  lea     r15, [rbx+50h]
0x140006c00  mov     eax, [rcx+4]
0x140006c03  test    eax, eax
0x140006c05  jz      loc_140007353
0x140006c0b  mov     rdx, [rbx+20h]
0x140006c0f  mov     r11d, [rdx+8]
0x140006c13  cmp     r11d, [rdx+0Ch]
0x140006c17  jnb     loc_140007926
0x140006c1d  inc     dword ptr [rbx+14h]
0x140006c20  inc     dword ptr [rdx+8]
0x140006c23  mov     rcx, [r15]
0x140006c26  cmp     byte ptr [rcx+1], 1
0x140006c2a  jnz     short loc_140006C79
0x140006c2c  mov     r10d, [rbx+0Ch]
0x140006c30  mov     rax, rsi
0x140006c33  cmp     r10d, 0FFFFFFFFh
0x140006c37  jz      short loc_140006C4A
0x140006c39  mov     r8, [rcx+18h]
0x140006c3d  test    r8, r8
0x140006c40  jz      short loc_140006C4A
0x140006c42  lea     rcx, [r10+r10*4]
0x140006c46  lea     rax, [r8+rcx*4]
0x140006c4a  lock inc word ptr [rax+0Eh]
0x140006c4f  mov     r10d, [rbx+0Ch]
0x140006c53  mov     rcx, rsi
0x140006c56  cmp     r10d, 0FFFFFFFFh
0x140006c5a  jz      short loc_140006C70
0x140006c5c  mov     rax, [r15]
0x140006c5f  mov     r8, [rax+18h]
0x140006c63  test    r8, r8
0x140006c66  jz      short loc_140006C70
0x140006c68  lea     rcx, [r10+r10*4]
0x140006c6c  lea     rcx, [r8+rcx*4]
0x140006c70  lock inc dword ptr [rcx+4]
0x140006c74  mov     r10, [rsp+98h+Src]
0x140006c79  mov     eax, r11d
0x140006c7c  mov     r15d, r12d
0x140006c7f  lea     rcx, [rax+rax*2]
0x140006c83  mov     rax, [rdx+10h]
0x140006c87  mov     [rax+rcx*8], r10
0x140006c8b  mov     [rax+rcx*8+8], r9
0x140006c90  lea     rdx, [rax+rcx*8]
0x140006c94  mov     eax, r12d
0x140006c97  shl     eax, 4
0x140006c9a  or      eax, 1
0x140006c9d  mov     [rdx+10h], eax
0x140006ca0  sub     ebp, r12d
0x140006ca3  jnz     loc_140007850
0x140006ca9  mov     r10, [rsp+98h+arg_18]
0x140006cb1  jmp     loc_140007114
0x140006cb6  mov     eax, [rdx]
0x140006cb8  test    al, 4
0x140006cba  jnz     loc_140007881
0x140006cc0  test    al, 8
0x140006cc2  jz      loc_140006B53
0x140006cc8  movzx   edx, word ptr [rdx+76h]
0x140006ccc  mov     ecx, 3FFh
0x140006cd1  shr     eax, 10h
0x140006cd4  and     ax, cx
0x140006cd7  test    dx, dx
0x140006cda  cmovz   dx, ax
0x140006cde  mov     eax, [r13+18h]
0x140006ce2  movzx   r14d, dx
0x140006ce6  mov     [rsp+98h+var_40], r14
0x140006ceb  lea     rcx, [r14+8]
0x140006cef  cmp     rax, rcx
0x140006cf2  jb      loc_14000810E
0x140006cf8  movzx   edx, dx
0x140006cfb  mov     [rsp+98h+var_60], edx
0x140006cff  test    edx, edx
0x140006d01  jz      loc_140007346
0x140006d07  mov     rsi, [r13+8]
0x140006d0b  mov     ebp, [r13+10h]
0x140006d0f  test    rsi, rsi
0x140006d12  jz      short loc_140006D1F
0x140006d14  mov     eax, [rsi+28h]
0x140006d17  cmp     eax, ebp
0x140006d19  jbe     loc_140007333
0x140006d1f  xor     r15d, r15d
0x140006d22  test    byte ptr [rsi+0Ah], 5
0x140006d26  mov     [rsp+98h+var_58], r15
0x140006d2b  jz      loc_1400075FC
0x140006d31  mov     rax, [rsi+18h]
0x140006d35  test    rax, rax
0x140006d38  jz      loc_14000731C
0x140006d3e  mov     ecx, [rsi+28h]
0x140006d41  mov     r14d, edx
0x140006d44  sub     ecx, ebp
0x140006d46  mov     r12d, ebp
0x140006d49  add     r12, rax
0x140006d4c  mov     r9, r10
0x140006d4f  cmp     ecx, r14d
0x140006d52  mov     [rsp+98h+Src], r9
0x140006d57  mov     ebp, r14d
0x140006d5a  cmovbe  ebp, ecx
0x140006d5d  test    rbx, rbx
0x140006d60  jz      loc_140007189
0x140006d66  mov     rcx, [rbx+50h]
0x140006d6a  cmp     byte ptr [rcx+1], 1
0x140006d6e  jnz     short loc_140006D9D
0x140006d70  cmp     byte ptr [rbx+4], 0
0x140006d74  jnz     short loc_140006D9D
0x140006d76  mov     r8d, [rbx+0Ch]
0x140006d7a  mov     rax, r15
0x140006d7d  mov     byte ptr [rbx+4], 1
0x140006d81  cmp     r8d, 0FFFFFFFFh
0x140006d85  jz      short loc_140006D98
0x140006d87  mov     rdx, [rcx+18h]
0x140006d8b  test    rdx, rdx
0x140006d8e  jz      short loc_140006D98
0x140006d90  lea     rcx, [r8+r8*4]
0x140006d94  lea     rax, [rdx+rcx*4]
0x140006d98  lock inc word ptr [rax+10h]
0x140006d9d  mov     rcx, [rbx+50h]
0x140006da1  mov     eax, [rcx+4]
0x140006da4  test    eax, eax
0x140006da6  jz      loc_140007155
0x140006dac  mov     rdx, [rbx+20h]
0x140006db0  mov     r10d, [rdx+8]
0x140006db4  cmp     r10d, [rdx+0Ch]
0x140006db8  jnb     loc_1400073A5
0x140006dbe  inc     dword ptr [rbx+14h]
0x140006dc1  inc     dword ptr [rdx+8]
0x140006dc4  mov     rcx, [rbx+50h]
0x140006dc8  cmp     byte ptr [rcx+1], 1
0x140006dcc  jnz     short loc_140006E1F
0x140006dce  mov     r9d, [rbx+0Ch]
0x140006dd2  xor     r11d, r11d
0x140006dd5  mov     eax, r11d
0x140006dd8  cmp     r9d, 0FFFFFFFFh
0x140006ddc  jz      short loc_140006DEF
0x140006dde  mov     r8, [rcx+18h]
0x140006de2  test    r8, r8
0x140006de5  jz      short loc_140006DEF
0x140006de7  lea     rcx, [r9+r9*4]
0x140006deb  lea     rax, [r8+rcx*4]
0x140006def  lock inc word ptr [rax+0Eh]
0x140006df4  mov     r9d, [rbx+0Ch]
0x140006df8  mov     rcx, r11
0x140006dfb  cmp     r9d, 0FFFFFFFFh
0x140006dff  jz      short loc_140006E16
0x140006e01  mov     rax, [rbx+50h]
0x140006e05  mov     r8, [rax+18h]
0x140006e09  test    r8, r8
0x140006e0c  jz      short loc_140006E16
0x140006e0e  lea     rcx, [r9+r9*4]
0x140006e12  lea     rcx, [r8+rcx*4]
0x140006e16  lock inc dword ptr [rcx+4]
0x140006e1a  mov     r9, [rsp+98h+Src]
0x140006e1f  mov     eax, r10d
0x140006e22  mov     r15d, ebp
0x140006e25  lea     rcx, [rax+rax*2]
0x140006e29  mov     rax, [rdx+10h]
0x140006e2d  mov     [rax+rcx*8], r9
0x140006e31  mov     [rax+rcx*8+8], r12
0x140006e36  lea     rdx, [rax+rcx*8]
0x140006e3a  mov     eax, ebp
0x140006e3c  shl     eax, 4
0x140006e3f  or      eax, 1
0x140006e42  mov     [rdx+10h], eax
0x140006e45  sub     r14d, ebp
0x140006e48  jnz     loc_140007302
0x140006e4e  mov     edx, [rsp+98h+var_60]
0x140006e52  xor     r8d, r8d
0x140006e55  mov     r14, [rsp+98h+var_40]
0x140006e5a  mov     ebp, [r13+10h]
0x140006e5e  mov     rsi, [r13+8]
0x140006e62  add     ebp, edx
0x140006e64  test    rsi, rsi
0x140006e67  jz      short loc_140006E74
0x140006e69  mov     eax, [rsi+28h]
0x140006e6c  cmp     eax, ebp
0x140006e6e  jbe     loc_140007514
0x140006e74  mov     r15d, [r13+18h]
0x140006e78  sub     r15d, edx
0x140006e7b  jz      loc_140006CA9
0x140006e81  test    rsi, rsi
0x140006e84  jz      loc_140008165
0x140006e8a  test    byte ptr [rsi+0Ah], 5
0x140006e8e  movzx   r12d, byte ptr [rdi+74h]
0x140006e93  mov     byte ptr [rsp+98h+arg_8], r12b
0x140006e9b  jz      loc_1400077C8
0x140006ea1  mov     rax, [rsi+18h]
0x140006ea5  test    rax, rax
0x140006ea8  jz      loc_1400072DC
0x140006eae  mov     ecx, [rsi+28h]
0x140006eb1  cmp     ecx, ebp
0x140006eb3  jbe     loc_1400072DC
0x140006eb9  mov     r8, [rsp+98h+arg_18]
0x140006ec1  sub     ecx, ebp
0x140006ec3  add     r8, r14
0x140006ec6  mov     r10d, ebp
0x140006ec9  add     r10, rax
0x140006ecc  mov     edx, r15d
0x140006ecf  mov     [rsp+98h+Src], r10
0x140006ed4  mov     rbp, r8
0x140006ed7  mov     [rsp+98h+var_60], edx
0x140006edb  lea     r9, [r8+6]
0x140006edf  mov     [rsp+98h+var_48], r9
0x140006ee4  cmp     ecx, edx
0x140006ee6  mov     r14d, edx
0x140006ee9  cmovbe  r14d, ecx
0x140006eed  mov     [rsp+98h+var_68], r14d
0x140006ef2  test    rbp, rbp
0x140006ef5  jz      loc_140007527
0x140006efb  test    rbx, rbx
0x140006efe  jz      loc_1400071D3
0x140006f04  mov     rax, [rbx+50h]
0x140006f08  cmp     byte ptr [rax+1], 1
0x140006f0c  jnz     short loc_140006F3A
0x140006f0e  cmp     byte ptr [rbx+4], 0
0x140006f12  jnz     short loc_140006F3A
0x140006f14  mov     r8d, [rbx+0Ch]
0x140006f18  xor     ecx, ecx
0x140006f1a  mov     byte ptr [rbx+4], 1
0x140006f1e  cmp     r8d, 0FFFFFFFFh
0x140006f22  jz      short loc_140006F35
0x140006f24  mov     rdx, [rax+18h]
0x140006f28  test    rdx, rdx
0x140006f2b  jz      short loc_140006F35
0x140006f2d  lea     rcx, [r8+r8*4]
0x140006f31  lea     rcx, [rdx+rcx*4]
0x140006f35  lock inc word ptr [rcx+10h]
0x140006f3a  mov     rcx, [rbx+50h]
0x140006f3e  mov     eax, [rcx+4]
0x140006f41  test    eax, eax
0x140006f43  jz      loc_14000719F
0x140006f49  mov     r8, [rbx+20h]
0x140006f4d  mov     edx, [r8+8]
0x140006f51  mov     [rsp+98h+var_64], edx
0x140006f55  cmp     edx, [r8+0Ch]
0x140006f59  jnb     loc_140007460
0x140006f5f  inc     dword ptr [rbx+14h]
0x140006f62  inc     dword ptr [r8+8]
  ... truncated ...
```
