# SegLibOffloadIteratorDeferredCopyNetBuffer

- ea: `0x140004ee0`
- end: `0x140006618`
- name: `SegLibOffloadIteratorDeferredCopyNetBuffer`
- size: `5944`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1401b9998`

## callees

- `0x140003fcc`
- `0x140004b70`
- `0x140004ee0`
- `0x140006620`
- `0x1401bbcb0`
- `0x1401bbe10`
- `0x1401bbfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140005770`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000581d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400059df`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140005c0b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140005d0b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140005f1f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140005770`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000581d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400059df`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140005c0b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140005d0b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140005f1f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400059bb`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140005b79`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140005ba5`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140005cea`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140005ee5`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400060e1`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400059bb`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140005b79`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140005ba5`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140005cea`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140005ee5`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400060e1`

## pseudocode

```c
__int64 __fastcall SegLibOffloadIteratorDeferredCopyNetBuffer(__int64 a1, int *a2, __int64 a3, char *a4)
{
  char *v4; // r14
  unsigned int *v5; // rbp
  int *v6; // r15
  unsigned int v8; // r14d
  struct _MDL *v9; // rdi
  unsigned int i; // esi
  unsigned int ByteCount; // eax
  unsigned int v12; // r12d
  char *MappedSystemVa; // rax
  char *v14; // r10
  unsigned int v15; // ecx
  char *v16; // r9
  unsigned int v17; // r13d
  __int64 v18; // rax
  int *v19; // rcx
  __int64 v20; // rcx
  __int64 *v21; // rsi
  unsigned int v22; // eax
  _DWORD *v23; // rdx
  unsigned int v24; // r11d
  __int64 v25; // r10
  __int64 v26; // rax
  __int64 v27; // r10
  __int64 v28; // rcx
  __int64 v29; // rsi
  __int64 v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rdx
  unsigned int v34; // r13d
  struct _MDL *v35; // rdi
  unsigned int j; // esi
  unsigned int v37; // eax
  char *v38; // rax
  unsigned int v39; // ebp
  unsigned int v40; // ecx
  char *v41; // r12
  char *v42; // r10
  unsigned int v43; // esi
  __int64 v44; // rcx
  __int64 v45; // r9
  __int64 v46; // rax
  __int64 v47; // rcx
  unsigned int v48; // eax
  _DWORD *v49; // rdx
  unsigned int v50; // r10d
  __int64 v51; // rcx
  __int64 v52; // r9
  __int64 v53; // rax
  __int64 v54; // r9
  __int64 v55; // rcx
  __int64 v56; // r14
  __int64 v57; // rax
  struct _MDL *v58; // rdi
  unsigned int k; // esi
  unsigned int v60; // eax
  unsigned int v61; // r14d
  char *v62; // rax
  unsigned int v63; // ecx
  unsigned int v64; // ecx
  __int64 v65; // rdx
  __int64 v66; // r9
  char *v67; // rsi
  char *v68; // r9
  __int64 v69; // r11
  size_t v70; // r14
  __int64 v71; // rax
  __int64 v72; // rcx
  __int64 v73; // rcx
  unsigned int v74; // eax
  _DWORD *v75; // rdx
  unsigned int v76; // r11d
  __int64 v77; // rcx
  __int64 v78; // r10
  __int64 v79; // rax
  __int64 v80; // r10
  __int64 v81; // rcx
  __int64 v82; // rcx
  __int64 v83; // rax
  char v84; // r13
  bool v85; // zf
  __int64 v86; // rax
  __int64 v87; // rcx
  unsigned int v88; // eax
  _DWORD *v89; // rdx
  unsigned int v90; // edi
  __int64 v91; // rcx
  __int64 v92; // r9
  __int64 v93; // rax
  __int64 v94; // r8
  __int64 v95; // r9
  __int64 v96; // rcx
  __int64 v97; // r8
  __int64 v98; // rdx
  int v99; // eax
  unsigned int v100; // eax
  __int64 v101; // rax
  unsigned int v102; // esi
  unsigned __int64 v103; // r14
  __int64 v104; // rdx
  unsigned int v105; // edi
  __int16 *v106; // r15
  __int64 v107; // rax
  __int64 v108; // rcx
  __int64 *v109; // rsi
  unsigned int v110; // eax
  _DWORD *v111; // rdx
  unsigned int v112; // ebp
  __int64 v113; // r9
  __int64 v114; // rax
  __int64 v115; // r8
  __int64 v116; // r9
  __int64 v117; // rcx
  __int64 v118; // r8
  __int64 v119; // rcx
  __int64 v120; // rax
  _DWORD *v121; // rax
  int v122; // ecx
  __int64 v123; // rcx
  __int64 v124; // rax
  __int64 v125; // r9
  volatile signed __int32 *v126; // rcx
  _DWORD *v127; // rax
  int v128; // ecx
  __int64 v129; // rcx
  __int64 v130; // rax
  __int64 v131; // r9
  volatile signed __int32 *v132; // rcx
  __int64 v133; // rax
  __int64 v134; // rcx
  unsigned int v135; // eax
  _DWORD *v136; // rdx
  unsigned int v137; // r13d
  __int64 v138; // rcx
  __int64 v139; // r10
  __int64 v140; // rax
  __int64 v141; // r10
  __int64 v142; // rcx
  __int64 v143; // rax
  __int64 v144; // rdx
  int v145; // ecx
  unsigned int v146; // ecx
  _DWORD *v147; // rax
  int v148; // ecx
  __int64 v149; // r8
  __int64 v150; // rcx
  __int64 v151; // rax
  __int64 v152; // r8
  __int64 v153; // r9
  volatile signed __int32 *v154; // rcx
  __int64 v155; // r8
  bool v156; // di
  __int16 *v157; // rcx
  unsigned int v158; // r14d
  unsigned __int16 v159; // ax
  __int16 v160; // ax
  char *v161; // rax
  _DWORD *v162; // rax
  int v163; // ecx
  __int64 v164; // rcx
  __int64 v165; // rax
  __int64 v166; // r9
  volatile signed __int32 *v167; // rcx
  _DWORD *v168; // rax
  int v169; // ecx
  __int64 v170; // r8
  __int64 v171; // rcx
  __int64 v172; // rax
  __int64 v173; // r8
  __int64 v174; // r9
  volatile signed __int32 *v175; // rcx
  __int64 v176; // r8
  unsigned __int16 v177; // di
  bool v178; // al
  __int16 *v179; // rdx
  unsigned __int16 v180; // ax
  _DWORD *v181; // rax
  int v182; // ecx
  __int64 v183; // rcx
  __int64 v184; // rax
  __int64 v185; // r9
  volatile signed __int32 *v186; // rcx
  bool v187; // r13
  __int16 *v188; // rdx
  unsigned __int16 v189; // ax
  __int16 v190; // ax
  unsigned __int16 v191; // ax
  __int16 v192; // ax
  unsigned int v193; // r14d
  unsigned __int16 v194; // ax
  __int16 v195; // ax
  unsigned __int16 v196; // ax
  __int16 *v197; // r8
  __int16 v198; // cx
  __int16 v199; // cx
  __int16 v200; // cx
  __int16 v201; // cx
  __int16 *v202; // rdx
  __int16 v203; // cx
  __int16 v204; // cx
  __int16 v205; // dx
  __int16 v206; // dx
  __int16 *v207; // rdx
  __int16 v208; // cx
  __int16 v209; // cx
  __int16 v210; // cx
  __int64 v211; // rcx
  __int64 v212; // r8
  __int64 v213; // rcx
  __int64 v214; // r9
  __int64 v215; // rcx
  __int64 v216; // r8
  __int16 v217; // cx
  unsigned int v219; // [rsp+34h] [rbp-64h]
  __int16 *Src; // [rsp+40h] [rbp-58h]
  unsigned int *v221; // [rsp+48h] [rbp-50h]
  char *v222; // [rsp+48h] [rbp-50h]
  __int16 *v223; // [rsp+48h] [rbp-50h]
  __int64 v224; // [rsp+50h] [rbp-48h]
  char *v225; // [rsp+A8h] [rbp+10h]
  char *v226; // [rsp+A8h] [rbp+10h]
  unsigned int v227; // [rsp+A8h] [rbp+10h]
  char v228; // [rsp+B0h] [rbp+18h]

  v4 = a4;
  v5 = (unsigned int *)*((_QWORD *)a2 + 4);
  v6 = a2;
  v221 = v5;
  if ( !*((_BYTE *)a2 + 115) )
  {
LABEL_2:
    v8 = v5[6];
    if ( !v8 )
    {
      v12 = 0;
      goto LABEL_120;
    }
    v9 = (struct _MDL *)*((_QWORD *)v5 + 1);
    for ( i = v5[4]; v9; i -= ByteCount )
    {
      ByteCount = v9->ByteCount;
      if ( ByteCount > i )
        break;
      v9 = v9->Next;
    }
    v12 = 0;
    if ( (v9->MdlFlags & 5) != 0 )
      MappedSystemVa = (char *)v9->MappedSystemVa;
    else
      MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v9, 0, MmCached, 0, 0, 0x40000000u);
    if ( MappedSystemVa )
    {
      v14 = a4;
      v15 = v9->ByteCount - i;
      v16 = &MappedSystemVa[i];
      v222 = v16;
      while ( 1 )
      {
        v225 = v14;
        v17 = v8;
        if ( v15 <= v8 )
          v17 = v15;
        if ( !a1 )
          break;
        v18 = *(_QWORD *)(a1 + 80);
        if ( *(_BYTE *)(v18 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
        {
          a3 = *(unsigned int *)(a1 + 12);
          v19 = 0;
          *(_BYTE *)(a1 + 4) = 1;
          if ( (_DWORD)a3 != -1 )
          {
            a2 = *(int **)(v18 + 24);
            if ( a2 )
              v19 = &a2[5 * a3];
          }
          _InterlockedIncrement16((volatile signed __int16 *)v19 + 8);
        }
        v20 = *(_QWORD *)(a1 + 80);
        v21 = (__int64 *)(a1 + 80);
        v22 = *(_DWORD *)(v20 + 4);
        if ( v22 )
        {
          v23 = *(_DWORD **)(a1 + 32);
          v24 = v23[2];
          if ( v24 >= v23[3] )
          {
            if ( *(_DWORD *)(a1 + 16) < v22
              && (v162 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v20 + 64)), (v23 = v162) != 0) )
            {
              *(_QWORD *)v162 = 0;
              v162[2] = 0;
              v163 = *(_DWORD *)(*v21 + 8);
              *((_QWORD *)v162 + 2) = v162 + 6;
              v162[3] = v163;
              **(_QWORD **)(a1 + 32) = v162;
              a3 = *v21;
              ++*(_DWORD *)(a1 + 16);
              *(_QWORD *)(a1 + 32) = v162;
              if ( *(_BYTE *)(a3 + 1) == 1 )
              {
                v164 = *(unsigned int *)(a1 + 12);
                v165 = 0;
                if ( (_DWORD)v164 != -1 )
                {
                  a3 = *(_QWORD *)(a3 + 24);
                  if ( a3 )
                    v165 = a3 + 20 * v164;
                }
                _InterlockedIncrement16((volatile signed __int16 *)(v165 + 12));
                v166 = *(unsigned int *)(a1 + 12);
                v167 = 0;
                if ( (_DWORD)v166 != -1 )
                {
                  a3 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
                  if ( a3 )
                    v167 = (volatile signed __int32 *)(a3 + 20 * v166);
                }
                _InterlockedIncrement(v167);
                v21 = (__int64 *)(a1 + 80);
              }
              v14 = v225;
              v24 = 0;
              v16 = v222;
            }
            else
            {
              LOBYTE(v23) = 1;
              BLFlushBatchOpContextEx(a1, v23, 0);
              v14 = v225;
              v23 = (_DWORD *)(a1 + 56);
              v16 = v222;
              v24 = 0;
            }
          }
          ++*(_DWORD *)(a1 + 20);
          ++v23[2];
          if ( *(_BYTE *)(*v21 + 1) == 1 )
          {
            v25 = *(unsigned int *)(a1 + 12);
            v26 = 0;
            if ( (_DWORD)v25 != -1 )
            {
              a3 = *(_QWORD *)(*v21 + 24);
              if ( a3 )
                v26 = a3 + 20 * v25;
            }
            _InterlockedIncrement16((volatile signed __int16 *)(v26 + 14));
            v27 = *(unsigned int *)(a1 + 12);
            v28 = 0;
            if ( (_DWORD)v27 != -1 )
            {
              a3 = *(_QWORD *)(*v21 + 24);
              if ( a3 )
                v28 = a3 + 20 * v27;
            }
            _InterlockedIncrement((volatile signed __int32 *)(v28 + 4));
            v14 = v225;
          }
          v29 = v17;
          v30 = 3LL * v24;
          v31 = *((_QWORD *)v23 + 2);
          *(_QWORD *)(v31 + 8 * v30) = v14;
          *(_QWORD *)(v31 + 8 * v30 + 8) = v16;
          a2 = (int *)(v31 + 24LL * v24);
          a2[4] = (16 * v17) | 1;
        }
        else
        {
          if ( *(_DWORD *)(a1 + 20) )
          {
            LOBYTE(a2) = 1;
            BLFlushBatchOpContextEx(a1, a2, 0);
            v16 = v222;
            v21 = (__int64 *)(a1 + 80);
            v14 = v225;
          }
          if ( (*(_BYTE *)(a1 + 8) & 5) != 5 && (*(_BYTE *)(a1 + 8) & 6) != 6 )
            break;
          (*(void (**)(void))(*v21 + 32))();
          memmove(v225, v222, v17);
          (*(void (**)(void))(*v21 + 40))();
          v29 = v17;
        }
LABEL_29:
        v8 -= v17;
        if ( !v8 )
          goto LABEL_120;
        v9 = v9->Next;
        if ( (v9->MdlFlags & 5) != 0 )
          v16 = (char *)v9->MappedSystemVa;
        else
          v16 = (char *)MmMapLockedPagesSpecifyCache(v9, 0, MmCached, 0, 0, 0x40000000u);
        v222 = v16;
        if ( !v16 )
          goto LABEL_154;
        v15 = v9->ByteCount;
        v14 = &v225[v29];
      }
      v29 = v17;
      memmove(v14, v16, v17);
      goto LABEL_29;
    }
LABEL_154:
    LOBYTE(a3) = 1;
    BLFlushBatchOpContextEx(a1, 0, a3);
    return (unsigned int)-1073741670;
  }
  v32 = *a2;
  if ( (*a2 & 4) == 0 )
  {
    if ( (v32 & 8) == 0 )
      goto LABEL_2;
    v33 = *((unsigned __int16 *)a2 + 59);
    if ( !(_WORD)v33 )
      LOWORD(v33) = HIWORD(v32) & 0x3FF;
    v224 = (unsigned __int16)v33;
    if ( v5[6] < (unsigned __int64)(unsigned __int16)v33 + 8 )
      return (unsigned int)-1073741789;
    v34 = (unsigned __int16)v33;
    if ( (_WORD)v33 )
    {
      v35 = (struct _MDL *)*((_QWORD *)v5 + 1);
      for ( j = v5[4]; v35; j -= v37 )
      {
        v37 = v35->ByteCount;
        if ( v37 > j )
          break;
        v35 = v35->Next;
      }
      a3 = 0;
      if ( (v35->MdlFlags & 5) != 0 )
      {
        v38 = (char *)v35->MappedSystemVa;
      }
      else
      {
        v38 = (char *)MmMapLockedPagesSpecifyCache(v35, 0, MmCached, 0, 0, 0x40000000u);
        a3 = 0;
      }
      if ( !v38 )
        goto LABEL_154;
      v39 = v34;
      v40 = v35->ByteCount - j;
      v41 = &v38[j];
      v42 = v4;
      while ( 1 )
      {
        v226 = v42;
        v43 = v39;
        if ( v40 <= v39 )
          v43 = v40;
        if ( !a1 )
          break;
        v44 = *(_QWORD *)(a1 + 80);
        if ( *(_BYTE *)(v44 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
        {
          v45 = *(unsigned int *)(a1 + 12);
          v46 = 0;
          *(_BYTE *)(a1 + 4) = 1;
          if ( (_DWORD)v45 != -1 )
          {
            v33 = *(_QWORD *)(v44 + 24);
            if ( v33 )
              v46 = v33 + 20 * v45;
          }
          _InterlockedIncrement16((volatile signed __int16 *)(v46 + 16));
        }
        v47 = *(_QWORD *)(a1 + 80);
        v48 = *(_DWORD *)(v47 + 4);
        if ( v48 )
        {
          v49 = *(_DWORD **)(a1 + 32);
          v50 = v49[2];
          if ( v50 >= v49[3] )
          {
            if ( *(_DWORD *)(a1 + 16) < v48
              && (v121 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v47 + 64)), (v49 = v121) != 0) )
            {
              *(_QWORD *)v121 = 0;
              v121[2] = 0;
              v122 = *(_DWORD *)(*(_QWORD *)(a1 + 80) + 8LL);
              *((_QWORD *)v121 + 2) = v121 + 6;
              v121[3] = v122;
              **(_QWORD **)(a1 + 32) = v121;
              a3 = *(_QWORD *)(a1 + 80);
              ++*(_DWORD *)(a1 + 16);
              *(_QWORD *)(a1 + 32) = v121;
              if ( *(_BYTE *)(a3 + 1) == 1 )
              {
                v123 = *(unsigned int *)(a1 + 12);
                v124 = 0;
                if ( (_DWORD)v123 != -1 )
                {
                  a3 = *(_QWORD *)(a3 + 24);
                  if ( a3 )
                    v124 = a3 + 20 * v123;
                }
                _InterlockedIncrement16((volatile signed __int16 *)(v124 + 12));
                v125 = *(unsigned int *)(a1 + 12);
                v126 = 0;
                if ( (_DWORD)v125 != -1 )
                {
                  a3 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
                  if ( a3 )
                    v126 = (volatile signed __int32 *)(a3 + 20 * v125);
                }
                _InterlockedIncrement(v126);
              }
            }
            else
            {
              LOBYTE(v49) = 1;
              BLFlushBatchOpContextEx(a1, v49, 0);
              v49 = (_DWORD *)(a1 + 56);
            }
            v50 = 0;
          }
          ++*(_DWORD *)(a1 + 20);
          ++v49[2];
          v51 = *(_QWORD *)(a1 + 80);
          if ( *(_BYTE *)(v51 + 1) == 1 )
          {
            v52 = *(unsigned int *)(a1 + 12);
            v53 = 0;
            if ( (_DWORD)v52 != -1 )
            {
              a3 = *(_QWORD *)(v51 + 24);
              if ( a3 )
                v53 = a3 + 20 * v52;
            }
            _InterlockedIncrement16((volatile signed __int16 *)(v53 + 14));
            v54 = *(unsigned int *)(a1 + 12);
            v55 = 0;
            if ( (_DWORD)v54 != -1 )
            {
              a3 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
              if ( a3 )
                v55 = a3 + 20 * v54;
            }
            _InterlockedIncrement((volatile signed __int32 *)(v55 + 4));
          }
          v56 = v43;
          v57 = *((_QWORD *)v49 + 2);
          *(_QWORD *)(v57 + 24LL * v50 + 8) = v41;
          v33 = v57 + 24LL * v50;
          *(_QWORD *)v33 = v226;
          *(_DWORD *)(v33 + 16) = (16 * v43) | 1;
        }
        else
        {
          if ( *(_DWORD *)(a1 + 20) )
          {
            LOBYTE(v33) = 1;
            BLFlushBatchOpContextEx(a1, v33, 0);
            v42 = v226;
          }
          if ( (*(_BYTE *)(a1 + 8) & 5) != 5 && (*(_BYTE *)(a1 + 8) & 6) != 6 )
            break;
          (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)(a1 + 80) + 32LL))(v47, v33, a3);
          memmove(v226, v41, v43);
          (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
          v56 = v43;
        }
LABEL_66:
        v39 -= v43;
        if ( !v39 )
        {
          v5 = v221;
          goto LABEL_68;
        }
        v35 = v35->Next;
        if ( (v35->MdlFlags & 5) != 0 )
          v41 = (char *)v35->MappedSystemVa;
        else
          v41 = (char *)MmMapLockedPagesSpecifyCache(v35, 0, MmCached, 0, 0, 0x40000000u);
        if ( !v41 )
          goto LABEL_154;
        v40 = v35->ByteCount;
        v42 = &v226[v56];
        a3 = 0;
      }
      v56 = v43;
      memmove(v42, v41, v43);
      goto LABEL_66;
    }
LABEL_68:
    v12 = 0;
    v58 = (struct _MDL *)*((_QWORD *)v5 + 1);
    for ( k = v34 + v5[4]; v58; k -= v60 )
    {
      v60 = v58->ByteCount;
      if ( v60 > k )
        break;
      v58 = v58->Next;
    }
    v61 = v5[6] - v34;
    v227 = v61;
    if ( !v61 )
      goto LABEL_120;
    if ( v58 )
    {
      v228 = *((_BYTE *)v6 + 116);
      if ( (v58->MdlFlags & 5) != 0 )
        v62 = (char *)v58->MappedSystemVa;
      else
        v62 = (char *)MmMapLockedPagesSpecifyCache(v58, 0, MmCached, 0, 0, 0x40000000u);
      if ( v62 )
      {
        v63 = v58->ByteCount;
        if ( v63 > k )
        {
          v64 = v63 - k;
          a3 = (__int64)&a4[v224];
          v65 = v61;
          v66 = k;
          v67 = &a4[v224];
          v68 = &v62[v66];
          v219 = v61;
          Src = (__int16 *)v68;
          v69 = (__int64)&a4[v224 + 6];
          v223 = (__int16 *)v69;
          while ( 1 )
          {
            v70 = (unsigned int)v65;
            if ( v64 <= (unsigned int)v65 )
              v70 = v64;
            if ( v67 )
              break;
            v133 = *(_QWORD *)(a1 + 80);
            if ( *(_BYTE *)(v133 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
            {
              a3 = *(unsigned int *)(a1 + 12);
              v211 = 0;
              *(_BYTE *)(a1 + 4) = 1;
              if ( (_DWORD)a3 != -1 )
              {
                v65 = *(_QWORD *)(v133 + 24);
                if ( v65 )
                  v211 = v65 + 20 * a3;
              }
              _InterlockedIncrement16((volatile signed __int16 *)(v211 + 16));
            }
            v134 = *(_QWORD *)(a1 + 80);
            v135 = *(_DWORD *)(v134 + 4);
            if ( v135 )
            {
              v136 = *(_DWORD **)(a1 + 32);
              v137 = v136[2];
              if ( v137 >= v136[3] )
              {
                v137 = 0;
                if ( *(_DWORD *)(a1 + 16) < v135
                  && (v181 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v134 + 64)), (v136 = v181) != 0) )
                {
                  *(_QWORD *)v181 = 0;
                  v181[2] = 0;
                  v182 = *(_DWORD *)(*(_QWORD *)(a1 + 80) + 8LL);
                  *((_QWORD *)v181 + 2) = v181 + 6;
                  v181[3] = v182;
                  **(_QWORD **)(a1 + 32) = v181;
                  a3 = *(_QWORD *)(a1 + 80);
                  ++*(_DWORD *)(a1 + 16);
                  *(_QWORD *)(a1 + 32) = v181;
                  if ( *(_BYTE *)(a3 + 1) == 1 )
                  {
                    v183 = *(unsigned int *)(a1 + 12);
                    v184 = 0;
                    if ( (_DWORD)v183 != -1 )
                    {
                      a3 = *(_QWORD *)(a3 + 24);
                      if ( a3 )
                        v184 = a3 + 20 * v183;
                    }
                    _InterlockedIncrement16((volatile signed __int16 *)(v184 + 12));
                    v185 = *(unsigned int *)(a1 + 12);
                    v186 = 0;
                    if ( (_DWORD)v185 != -1 )
                    {
                      a3 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
                      if ( a3 )
                        v186 = (volatile signed __int32 *)(a3 + 20 * v185);
                    }
                    _InterlockedIncrement(v186);
                  }
                  v69 = (__int64)&a4[v224 + 6];
                  v68 = (char *)Src;
                }
                else
                {
                  LOBYTE(v136) = 1;
                  BLFlushBatchOpContextEx(a1, v136, 0);
                  v69 = (__int64)&a4[v224 + 6];
                  v136 = (_DWORD *)(a1 + 56);
                  v68 = (char *)Src;
                }
              }
              ++*(_DWORD *)(a1 + 20);
              ++v136[2];
              v138 = *(_QWORD *)(a1 + 80);
              if ( *(_BYTE *)(v138 + 1) == 1 )
              {
                v139 = *(unsigned int *)(a1 + 12);
                v140 = 0;
                if ( (_DWORD)v139 != -1 )
                {
                  a3 = *(_QWORD *)(v138 + 24);
                  if ( a3 )
                    v140 = a3 + 20 * v139;
                }
                _InterlockedIncrement16((volatile signed __int16 *)(v140 + 14));
                v141 = *(unsigned int *)(a1 + 12);
                v142 = 0;
                if ( (_DWORD)v141 != -1 )
                {
                  a3 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
                  if ( a3 )
                    v142 = a3 + 20 * v141;
                }
                _InterlockedIncrement((volatile signed __int32 *)(v142 + 4));
              }
              v143 = v137;
              v84 = v228;
              v144 = *((_QWORD *)v136 + 2) + 24 * v143;
              v145 = *(_DWORD *)(v144 + 16);
              if ( v228 )
                v146 = v145 & 0xFFFFFFF0 | 7;
              else
                v146 = v145 & 0xFFFFFFF0 | 6;
              *(_DWORD *)(v144 + 16) = v146;
              *(_QWORD *)(v144 + 8) = v68;
              *(_DWORD *)(v144 + 16) = v146 & 0xF | (16 * v70);
              *(_QWORD *)v144 = v69;
            }
            else
            {
              if ( *(_DWORD *)(a1 + 20) )
              {
                LOBYTE(v65) = 1;
                BLFlushBatchOpContextEx(a1, v65, 0);
                v69 = (__int64)&a4[v224 + 6];
              }
              v187 = (*(_BYTE *)(a1 + 8) & 5) == 5 || (*(_DWORD *)(a1 + 8) & 6) == 6;
              v188 = *(__int16 **)(a1 + 48);
              if ( v188 && v188 != (__int16 *)v69 )
              {
                if ( v187 )
                {
                  (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
                  v197 = *(__int16 **)(a1 + 48);
                  v198 = *v197;
                  if ( (*(_DWORD *)(a1 + 44) & 1) != 0 )
                    v198 = __ROR2__(v198, 8);
                  v199 = ~v198;
                  if ( *(_BYTE *)(a1 + 40) && !v199 )
                    v199 = -1;
                  *v197 = v199;
                  *(_QWORD *)(a1 + 48) = 0;
                  *(_DWORD *)(a1 + 44) = 0;
                  (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
                }
                else
                {
                  v200 = *v188;
                  if ( (*(_DWORD *)(a1 + 44) & 1) != 0 )
                    v200 = __ROR2__(v200, 8);
                  v201 = ~v200;
                  if ( *(_BYTE *)(a1 + 40) && !v201 )
                    v201 = -1;
                  *v188 = v201;
                  *(_DWORD *)(a1 + 44) = 0;
                }
              }
              *(_QWORD *)(a1 + 48) = v223;
              *(_BYTE *)(a1 + 40) = v228 != 0;
              if ( v187 )
              {
                (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
                if ( v223 < Src || (v191 = 0, v223 >= (__int16 *)((char *)Src + (unsigned int)v70)) )
                  v191 = *v223;
                v192 = tcpxsum(v191, Src, (unsigned int)v70);
                *v223 = v192;
                if ( (v70 & 1) != 0 )
                {
                  *v223 = __ROR2__(v192, 8);
                  ++*(_DWORD *)(a1 + 44);
                }
                (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
                v84 = v228;
              }
              else
              {
                if ( v223 < Src || v223 >= (__int16 *)((char *)Src + (unsigned int)v70) )
                  v189 = *v223;
                else
                  v189 = 0;
                v190 = tcpxsum(v189, Src, (unsigned int)v70);
                *v223 = v190;
                if ( (v70 & 1) != 0 )
                {
                  *v223 = __ROR2__(v190, 8);
                  ++*(_DWORD *)(a1 + 44);
                }
                v84 = v228;
              }
            }
LABEL_99:
            v85 = v219 == (_DWORD)v70;
            v65 = v219 - (unsigned int)v70;
            v219 -= v70;
            if ( v85 )
            {
              if ( !v67 )
                goto LABEL_120;
              v86 = *(_QWORD *)(a1 + 80);
              if ( *(_BYTE *)(v86 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
              {
                v212 = *(unsigned int *)(a1 + 12);
                v213 = 0;
                *(_BYTE *)(a1 + 4) = 1;
                if ( (_DWORD)v212 != -1 )
                {
                  v65 = *(_QWORD *)(v86 + 24);
                  if ( v65 )
                    v213 = v65 + 20 * v212;
                }
                _InterlockedIncrement16((volatile signed __int16 *)(v213 + 16));
              }
              v87 = *(_QWORD *)(a1 + 80);
              v88 = *(_DWORD *)(v87 + 4);
              if ( v88 )
              {
                v89 = *(_DWORD **)(a1 + 32);
                v90 = v89[2];
                if ( v90 >= v89[3] )
                {
                  v90 = 0;
                  if ( *(_DWORD *)(a1 + 16) < v88
                    && (v147 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v87 + 64)), (v89 = v147) != 0) )
                  {
                    *(_QWORD *)v147 = 0;
                    v147[2] = 0;
                    v148 = *(_DWORD *)(*(_QWORD *)(a1 + 80) + 8LL);
                    *((_QWORD *)v147 + 2) = v147 + 6;
                    v147[3] = v148;
                    **(_QWORD **)(a1 + 32) = v147;
                    v149 = *(_QWORD *)(a1 + 80);
                    ++*(_DWORD *)(a1 + 16);
                    *(_QWORD *)(a1 + 32) = v147;
                    if ( *(_BYTE *)(v149 + 1) == 1 )
                    {
                      v150 = *(unsigned int *)(a1 + 12);
                      v151 = 0;
                      if ( (_DWORD)v150 != -1 )
                      {
                        v152 = *(_QWORD *)(v149 + 24);
                        if ( v152 )
                          v151 = v152 + 20 * v150;
                      }
                      _InterlockedIncrement16((volatile signed __int16 *)(v151 + 12));
                      v153 = *(unsigned int *)(a1 + 12);
                      v154 = 0;
                      if ( (_DWORD)v153 != -1 )
                      {
                        v155 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
                        if ( v155 )
                          v154 = (volatile signed __int32 *)(v155 + 20 * v153);
                      }
                      _InterlockedIncrement(v154);
                    }
                  }
                  else
                  {
                    LOBYTE(v89) = 1;
                    BLFlushBatchOpContextEx(a1, v89, 0);
                    v89 = (_DWORD *)(a1 + 56);
                  }
                }
                ++*(_DWORD *)(a1 + 20);
                ++v89[2];
                v91 = *(_QWORD *)(a1 + 80);
                if ( *(_BYTE *)(v91 + 1) == 1 )
                {
                  v92 = *(unsigned int *)(a1 + 12);
                  v93 = 0;
                  if ( (_DWORD)v92 != -1 )
                  {
                    v94 = *(_QWORD *)(v91 + 24);
                    if ( v94 )
                      v93 = v94 + 20 * v92;
                  }
                  _InterlockedIncrement16((volatile signed __int16 *)(v93 + 14));
                  v95 = *(unsigned int *)(a1 + 12);
                  v96 = 0;
                  if ( (_DWORD)v95 != -1 )
                  {
                    v97 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
                    if ( v97 )
                      v96 = v97 + 20 * v95;
                  }
                  _InterlockedIncrement((volatile signed __int32 *)(v96 + 4));
                }
                v98 = *((_QWORD *)v89 + 2) + 24LL * v90;
                v99 = *(_DWORD *)(v98 + 16);
                if ( v84 )
                  v100 = v99 & 0xFFFFFFF0 | 7;
                else
                  v100 = v99 & 0xFFFFFFF0 | 6;
                *(_DWORD *)(v98 + 16) = v100;
                a3 = (__int64)&a4[v224 + 6];
                *(_QWORD *)(v98 + 8) = &a4[v224];
                *(_QWORD *)v98 = a3;
                *(_DWORD *)(v98 + 16) = v100 & 0xF | (16 * v227);
                goto LABEL_120;
              }
              if ( *(_DWORD *)(a1 + 20) )
              {
                LOBYTE(v65) = 1;
                BLFlushBatchOpContextEx(a1, v65, 0);
              }
              v156 = (*(_BYTE *)(a1 + 8) & 5) == 5 || (*(_DWORD *)(a1 + 8) & 6) == 6;
              v157 = *(__int16 **)(a1 + 48);
              if ( v157 && v157 != v223 )
              {
                if ( v156 )
                {
                  (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
                  v202 = *(__int16 **)(a1 + 48);
                  v203 = *v202;
                  if ( (*(_DWORD *)(a1 + 44) & 1) != 0 )
                    v203 = __ROR2__(v203, 8);
                  v204 = ~v203;
                  if ( *(_BYTE *)(a1 + 40) && !v204 )
                    v204 = -1;
                  *v202 = v204;
                  *(_QWORD *)(a1 + 48) = 0;
                  *(_DWORD *)(a1 + 44) = 0;
                  (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
                }
                else
                {
                  v205 = *v157;
                  if ( (*(_DWORD *)(a1 + 44) & 1) != 0 )
                    v205 = __ROR2__(v205, 8);
                  v206 = ~v205;
                  if ( *(_BYTE *)(a1 + 40) && !v206 )
                    v206 = -1;
                  *v157 = v206;
                  *(_DWORD *)(a1 + 44) = 0;
                }
              }
              *(_BYTE *)(a1 + 40) = v84 != 0;
              *(_QWORD *)(a1 + 48) = v223;
              if ( !v156 )
              {
                if ( v223 < (__int16 *)&a4[v224] )
                {
                  v158 = v227;
                }
                else
                {
                  v158 = v227;
                  if ( v223 < (__int16 *)&a4[v224 + v227] )
                  {
                    v159 = 0;
LABEL_221:
                    v160 = tcpxsum(v159, &a4[v224], v158);
                    *v223 = v160;
                    if ( (v158 & 1) != 0 )
                    {
                      *v223 = __ROR2__(v160, 8);
                      ++*(_DWORD *)(a1 + 44);
                    }
LABEL_120:
                    v4 = a4;
LABEL_121:
                    if ( !*((_BYTE *)v6 + 115) || (*v6 & 0x10) == 0 )
                      return v12;
                    v101 = *((unsigned __int8 *)v6 + 108);
                    v102 = v5[6] - v101;
                    if ( v102 < 0x14 )
                      return (unsigned int)-2147483643;
                    LOBYTE(a3) = 1;
                    v103 = (unsigned __int64)&v4[v101];
                    BLFlushBatchOpContextEx(a1, 0, a3);
                    v105 = 4 * (*(_BYTE *)v103 & 0xF);
                    if ( v105 > v102 )
                      return (unsigned int)-2147483643;
                    *(_WORD *)(v103 + 10) = 0;
                    v106 = (__int16 *)(v103 + 10);
                    v107 = *(_QWORD *)(a1 + 80);
                    if ( *(_BYTE *)(v107 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
                    {
                      v214 = *(unsigned int *)(a1 + 12);
                      v215 = 0;
                      *(_BYTE *)(a1 + 4) = 1;
                      if ( (_DWORD)v214 != -1 )
                      {
                        v216 = *(_QWORD *)(v107 + 24);
                        if ( v216 )
                          v215 = v216 + 20 * v214;
                      }
                      _InterlockedIncrement16((volatile signed __int16 *)(v215 + 16));
                    }
                    v108 = *(_QWORD *)(a1 + 80);
                    v109 = (__int64 *)(a1 + 80);
                    v110 = *(_DWORD *)(v108 + 4);
                    if ( v110 )
                    {
                      v111 = *(_DWORD **)(a1 + 32);
                      v112 = v111[2];
                      if ( v112 >= v111[3] )
                      {
                        v112 = 0;
                        if ( *(_DWORD *)(a1 + 16) < v110
                          && (v168 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v108 + 64)),
                              (v111 = v168) != 0) )
                        {
                          *(_QWORD *)v168 = 0;
                          v168[2] = 0;
                          v169 = *(_DWORD *)(*v109 + 8);
                          *((_QWORD *)v168 + 2) = v168 + 6;
                          v168[3] = v169;
                          **(_QWORD **)(a1 + 32) = v168;
                          v170 = *v109;
                          ++*(_DWORD *)(a1 + 16);
                          *(_QWORD *)(a1 + 32) = v168;
                          if ( *(_BYTE *)(v170 + 1) == 1 )
                          {
                            v171 = *(unsigned int *)(a1 + 12);
                            v172 = 0;
                            if ( (_DWORD)v171 != -1 )
                            {
                              v173 = *(_QWORD *)(v170 + 24);
                              if ( v173 )
                                v172 = v173 + 20 * v171;
                            }
                            _InterlockedIncrement16((volatile signed __int16 *)(v172 + 12));
                            v174 = *(unsigned int *)(a1 + 12);
                            v175 = 0;
                            if ( (_DWORD)v174 != -1 )
                            {
                              v176 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
                              if ( v176 )
                                v175 = (volatile signed __int32 *)(v176 + 20 * v174);
                            }
                            _InterlockedIncrement(v175);
                            v109 = (__int64 *)(a1 + 80);
                          }
                        }
                        else
                        {
                          LOBYTE(v111) = 1;
                          BLFlushBatchOpContextEx(a1, v111, 0);
                          v111 = (_DWORD *)(a1 + 56);
                        }
                      }
                      ++*(_DWORD *)(a1 + 20);
                      ++v111[2];
                      if ( *(_BYTE *)(*v109 + 1) == 1 )
                      {
                        v113 = *(unsigned int *)(a1 + 12);
                        v114 = 0;
                        if ( (_DWORD)v113 != -1 )
                        {
                          v115 = *(_QWORD *)(*v109 + 24);
                          if ( v115 )
                            v114 = v115 + 20 * v113;
                        }
                        _InterlockedIncrement16((volatile signed __int16 *)(v114 + 14));
                        v116 = *(unsigned int *)(a1 + 12);
                        v117 = 0;
                        if ( (_DWORD)v116 != -1 )
                        {
                          v118 = *(_QWORD *)(*v109 + 24);
                          if ( v118 )
                            v117 = v118 + 20 * v116;
                        }
                        _InterlockedIncrement((volatile signed __int32 *)(v117 + 4));
                      }
                      v119 = 3LL * v112;
                      v120 = *((_QWORD *)v111 + 2);
                      *(_QWORD *)(v120 + 8 * v119 + 8) = v103;
                      *(_QWORD *)(v120 + 8 * v119) = v106;
                      *(_DWORD *)(v120 + 8 * v119 + 16) = (16 * v105) | 6;
                      return v12;
                    }
                    if ( *(_DWORD *)(a1 + 20) )
                    {
                      LOBYTE(v104) = 1;
                      BLFlushBatchOpContextEx(a1, v104, 0);
                    }
                    v178 = (*(_BYTE *)(a1 + 8) & 5) == 5 || (*(_DWORD *)(a1 + 8) & 6) == 6;
                    v179 = *(__int16 **)(a1 + 48);
                    if ( !v179 || v179 == v106 )
                    {
                      *(_BYTE *)(a1 + 40) = 0;
                      *(_QWORD *)(a1 + 48) = v106;
                      if ( v178 )
                      {
LABEL_322:
                        (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
                        if ( (unsigned __int64)v106 < v103 || (v196 = 0, (unsigned __int64)v106 >= v103 + v105) )
                          v196 = *v106;
                        *v106 = tcpxsum(v196, v103, v105);
                        (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
                        return v12;
                      }
                    }
                    else
                    {
                      if ( v178 )
                      {
                        (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
                        v207 = *(__int16 **)(a1 + 48);
                        v208 = *v207;
                        if ( (*(_DWORD *)(a1 + 44) & 1) != 0 )
                          v208 = __ROR2__(v208, 8);
                        v217 = ~v208;
                        if ( *(_BYTE *)(a1 + 40) && !v217 )
                          v217 = -1;
                        *v207 = v217;
                        *(_QWORD *)(a1 + 48) = 0;
                        *(_DWORD *)(a1 + 44) = 0;
                        (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
                        *(_BYTE *)(a1 + 40) = 0;
                        *(_QWORD *)(a1 + 48) = v106;
                        goto LABEL_322;
                      }
                      v209 = *v179;
                      if ( (*(_DWORD *)(a1 + 44) & 1) != 0 )
                        v209 = __ROR2__(v209, 8);
                      v210 = ~v209;
                      if ( *(_BYTE *)(a1 + 40) && !v210 )
                        v210 = -1;
                      *v179 = v210;
                      *(_QWORD *)(a1 + 48) = 0;
                      *(_DWORD *)(a1 + 44) = 0;
                      *(_BYTE *)(a1 + 40) = 0;
                      *(_QWORD *)(a1 + 48) = v106;
                    }
                    if ( (unsigned __int64)v106 < v103 || (unsigned __int64)v106 >= v103 + v105 )
                      v180 = *v106;
                    else
                      v180 = 0;
                    *v106 = tcpxsum(v180, v103, v105);
                    return v12;
                  }
                }
                v159 = *v223;
                goto LABEL_221;
              }
              (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
              if ( v223 < (__int16 *)&a4[v224] )
              {
                v193 = v227;
              }
              else
              {
                v193 = v227;
                if ( v223 < (__int16 *)&a4[v224 + v227] )
                {
                  v194 = 0;
LABEL_316:
                  v195 = tcpxsum(v194, &a4[v224], v193);
                  *v223 = v195;
                  if ( (v193 & 1) != 0 )
                  {
                    *v223 = __ROR2__(v195, 8);
                    ++*(_DWORD *)(a1 + 44);
                  }
                  (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
                  goto LABEL_120;
                }
              }
              v194 = *v223;
              goto LABEL_316;
            }
            v58 = v58->Next;
            if ( !v58 )
              goto LABEL_149;
            if ( (v58->MdlFlags & 5) != 0 )
            {
              v68 = (char *)v58->MappedSystemVa;
              Src = (__int16 *)v68;
            }
            else
            {
              v161 = (char *)MmMapLockedPagesSpecifyCache(v58, 0, MmCached, 0, 0, 0x40000000u);
              v65 = v219;
              v68 = v161;
              Src = (__int16 *)v161;
            }
            if ( !v68 )
              goto LABEL_149;
            v64 = v58->ByteCount;
            v69 = (__int64)&a4[v224 + 6];
          }
          if ( !a1 )
            goto LABEL_133;
          v71 = *(_QWORD *)(a1 + 80);
          if ( *(_BYTE *)(v71 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
          {
            a3 = *(unsigned int *)(a1 + 12);
            v72 = 0;
            *(_BYTE *)(a1 + 4) = 1;
            if ( (_DWORD)a3 != -1 )
            {
              v65 = *(_QWORD *)(v71 + 24);
              if ( v65 )
                v72 = v65 + 20 * a3;
            }
            _InterlockedIncrement16((volatile signed __int16 *)(v72 + 16));
          }
          v73 = *(_QWORD *)(a1 + 80);
          v74 = *(_DWORD *)(v73 + 4);
          if ( v74 )
          {
            v75 = *(_DWORD **)(a1 + 32);
            v76 = v75[2];
            if ( v76 >= v75[3] )
            {
              if ( *(_DWORD *)(a1 + 16) < v74
                && (v127 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v73 + 64)), (v75 = v127) != 0) )
              {
                *(_QWORD *)v127 = 0;
                v127[2] = 0;
                v128 = *(_DWORD *)(*(_QWORD *)(a1 + 80) + 8LL);
                *((_QWORD *)v127 + 2) = v127 + 6;
                v127[3] = v128;
                **(_QWORD **)(a1 + 32) = v127;
                a3 = *(_QWORD *)(a1 + 80);
                ++*(_DWORD *)(a1 + 16);
                *(_QWORD *)(a1 + 32) = v127;
                if ( *(_BYTE *)(a3 + 1) == 1 )
                {
                  v129 = *(unsigned int *)(a1 + 12);
                  v130 = 0;
                  if ( (_DWORD)v129 != -1 )
                  {
                    a3 = *(_QWORD *)(a3 + 24);
                    if ( a3 )
                      v130 = a3 + 20 * v129;
                  }
                  _InterlockedIncrement16((volatile signed __int16 *)(v130 + 12));
                  v131 = *(unsigned int *)(a1 + 12);
                  v132 = 0;
                  if ( (_DWORD)v131 != -1 )
                  {
                    a3 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
                    if ( a3 )
                      v132 = (volatile signed __int32 *)(a3 + 20 * v131);
                  }
                  _InterlockedIncrement(v132);
                }
                v68 = (char *)Src;
                v76 = 0;
              }
              else
              {
                LOBYTE(v75) = 1;
                BLFlushBatchOpContextEx(a1, v75, 0);
                v68 = (char *)Src;
                v75 = (_DWORD *)(a1 + 56);
                v76 = 0;
              }
            }
            ++*(_DWORD *)(a1 + 20);
            ++v75[2];
            v77 = *(_QWORD *)(a1 + 80);
            if ( *(_BYTE *)(v77 + 1) == 1 )
            {
              v78 = *(unsigned int *)(a1 + 12);
              v79 = 0;
              if ( (_DWORD)v78 != -1 )
              {
                a3 = *(_QWORD *)(v77 + 24);
                if ( a3 )
                  v79 = a3 + 20 * v78;
              }
              _InterlockedIncrement16((volatile signed __int16 *)(v79 + 14));
              v80 = *(unsigned int *)(a1 + 12);
              v81 = 0;
              if ( (_DWORD)v80 != -1 )
              {
                a3 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
                if ( a3 )
                  v81 = a3 + 20 * v80;
              }
              _InterlockedIncrement((volatile signed __int32 *)(v81 + 4));
            }
            v82 = 3LL * v76;
            v83 = *((_QWORD *)v75 + 2);
            *(_QWORD *)(v83 + 8 * v82) = v67;
            *(_QWORD *)(v83 + 8 * v82 + 8) = v68;
            *(_DWORD *)(v83 + 24LL * v76 + 16) = (16 * v70) | 1;
            goto LABEL_98;
          }
          if ( *(_DWORD *)(a1 + 20) )
          {
            LOBYTE(v65) = 1;
            BLFlushBatchOpContextEx(a1, v65, 0);
            v68 = (char *)Src;
          }
          if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (*(_BYTE *)(a1 + 8) & 6) == 6 )
          {
            (*(void (__fastcall **)(__int64, __int64, __int64, char *))(*(_QWORD *)(a1 + 80) + 32LL))(v73, v65, a3, v68);
            memmove(v67, Src, v70);
            (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
          }
          else
          {
LABEL_133:
            memmove(v67, v68, v70);
          }
LABEL_98:
          v84 = v228;
          v67 += v70;
          goto LABEL_99;
        }
      }
LABEL_149:
      v12 = -1073741670;
    }
    else
    {
      v12 = -1073741811;
    }
    LOBYTE(a3) = 1;
    BLFlushBatchOpContextEx(a1, 0, a3);
    return v12;
  }
  v177 = *((_WORD *)a2 + 59);
  if ( !v177 )
    v177 = HIWORD(v32) & 0x3FF;
  if ( v5[6] < (unsigned __int64)v177 + 20 )
  {
    return (unsigned int)-1071448043;
  }
  else
  {
    v12 = SegLibPvtDeferredCopyMdlChainData(a1, *((_QWORD *)v5 + 1), v5[4], v177, a4);
    if ( (v12 & 0x80000000) == 0 )
    {
      v12 = SegLibPvtDeferredChecksumTransport(a1, (int)v5, v177, 0, (__int64)&v4[v177 + 16], &v4[v177]);
      if ( (v12 & 0x80000000) == 0 )
      {
        v12 = 0;
        goto LABEL_121;
      }
    }
  }
  return v12;
}

```

## disassembly

```asm
0x140004ee0  mov     [rsp+arg_0], rbx
0x140004ee5  mov     [rsp+arg_18], r9
0x140004eea  mov     [rsp+arg_10], r8d
0x140004eef  push    rbp
0x140004ef0  push    rsi
0x140004ef1  push    rdi
0x140004ef2  push    r12
0x140004ef4  push    r13
0x140004ef6  push    r14
0x140004ef8  push    r15
0x140004efa  sub     rsp, 60h
0x140004efe  cmp     byte ptr [rdx+73h], 0
0x140004f02  mov     r14, r9
0x140004f05  mov     rbp, [rdx+20h]
0x140004f09  mov     r15, rdx
0x140004f0c  mov     [rsp+98h+var_50], rbp
0x140004f11  mov     rbx, rcx
0x140004f14  jnz     loc_1400050A8
0x140004f1a  mov     r14d, [rbp+18h]
0x140004f1e  test    r14d, r14d
0x140004f21  jz      loc_140005BF6
0x140004f27  mov     rdi, [rbp+8]
0x140004f2b  mov     esi, [rbp+10h]
0x140004f2e  test    rdi, rdi
0x140004f31  jz      short loc_140004F3E
0x140004f33  mov     eax, [rdi+28h]
0x140004f36  cmp     eax, esi
0x140004f38  jbe     loc_140005BE3
0x140004f3e  xor     r12d, r12d
0x140004f41  test    byte ptr [rdi+0Ah], 5
0x140004f45  jz      loc_140005CCF
0x140004f4b  mov     rax, [rdi+18h]
0x140004f4f  test    rax, rax
0x140004f52  jz      loc_1400056DA
0x140004f58  mov     ecx, [rdi+28h]
0x140004f5b  mov     r10, [rsp+98h+arg_18]
0x140004f63  sub     ecx, esi
0x140004f65  mov     r9d, esi
0x140004f68  add     r9, rax
0x140004f6b  mov     [rsp+98h+var_50], r9
0x140004f70  cmp     ecx, r14d
0x140004f73  mov     [rsp+98h+arg_8], r10
0x140004f7b  mov     r13d, r14d
0x140004f7e  cmovbe  r13d, ecx
0x140004f82  test    rbx, rbx
0x140004f85  jz      loc_140005745
0x140004f8b  mov     rax, [rbx+50h]
0x140004f8f  cmp     byte ptr [rax+1], 1
0x140004f93  jnz     short loc_140004FC2
0x140004f95  cmp     [rbx+4], r12b
0x140004f99  jnz     short loc_140004FC2
0x140004f9b  mov     r8d, [rbx+0Ch]
0x140004f9f  mov     rcx, r12
0x140004fa2  mov     byte ptr [rbx+4], 1
0x140004fa6  cmp     r8d, 0FFFFFFFFh
0x140004faa  jz      short loc_140004FBD
0x140004fac  mov     rdx, [rax+18h]
0x140004fb0  test    rdx, rdx
0x140004fb3  jz      short loc_140004FBD
0x140004fb5  lea     rcx, [r8+r8*4]
0x140004fb9  lea     rcx, [rdx+rcx*4]
0x140004fbd  lock inc word ptr [rcx+10h]
0x140004fc2  mov     rcx, [rbx+50h]
0x140004fc6  lea     rsi, [rbx+50h]
0x140004fca  mov     eax, [rcx+4]
0x140004fcd  test    eax, eax
0x140004fcf  jz      loc_140005705
0x140004fd5  mov     rdx, [rbx+20h]
0x140004fd9  mov     r11d, [rdx+8]
0x140004fdd  cmp     r11d, [rdx+0Ch]
0x140004fe1  jnb     loc_140005BFE
0x140004fe7  inc     dword ptr [rbx+14h]
0x140004fea  inc     dword ptr [rdx+8]
0x140004fed  mov     rcx, [rsi]
0x140004ff0  cmp     byte ptr [rcx+1], 1
0x140004ff4  jnz     short loc_140005046
0x140004ff6  mov     r10d, [rbx+0Ch]
0x140004ffa  mov     rax, r12
0x140004ffd  cmp     r10d, 0FFFFFFFFh
0x140005001  jz      short loc_140005014
0x140005003  mov     r8, [rcx+18h]
0x140005007  test    r8, r8
0x14000500a  jz      short loc_140005014
0x14000500c  lea     rcx, [r10+r10*4]
0x140005010  lea     rax, [r8+rcx*4]
0x140005014  lock inc word ptr [rax+0Eh]
0x140005019  mov     r10d, [rbx+0Ch]
0x14000501d  mov     rcx, r12
0x140005020  cmp     r10d, 0FFFFFFFFh
0x140005024  jz      short loc_14000503A
0x140005026  mov     rax, [rsi]
0x140005029  mov     r8, [rax+18h]
0x14000502d  test    r8, r8
0x140005030  jz      short loc_14000503A
0x140005032  lea     rcx, [r10+r10*4]
0x140005036  lea     rcx, [r8+rcx*4]
0x14000503a  lock inc dword ptr [rcx+4]
0x14000503e  mov     r10, [rsp+98h+arg_8]
0x140005046  mov     eax, r11d
0x140005049  mov     esi, r13d
0x14000504c  lea     rcx, [rax+rax*2]
0x140005050  mov     rax, [rdx+10h]
0x140005054  mov     [rax+rcx*8], r10
0x140005058  mov     [rax+rcx*8+8], r9
0x14000505d  lea     rdx, [rax+rcx*8]
0x140005061  mov     eax, r13d
0x140005064  shl     eax, 4
0x140005067  or      eax, 1
0x14000506a  mov     [rdx+10h], eax
0x14000506d  sub     r14d, r13d
0x140005070  jz      loc_140005501
0x140005076  mov     rdi, [rdi]
0x140005079  test    byte ptr [rdi+0Ah], 5
0x14000507d  jz      loc_1400060C6
0x140005083  mov     r9, [rdi+18h]
0x140005087  mov     [rsp+98h+var_50], r9
0x14000508c  test    r9, r9
0x14000508f  jz      loc_1400056DA
0x140005095  mov     r10, [rsp+98h+arg_8]
0x14000509d  mov     ecx, [rdi+28h]
0x1400050a0  add     r10, rsi
0x1400050a3  jmp     loc_140004F70
0x1400050a8  mov     eax, [rdx]
0x1400050aa  test    al, 4
0x1400050ac  jnz     loc_140005DA6
0x1400050b2  test    al, 8
0x1400050b4  jz      loc_140004F1A
0x1400050ba  movzx   edx, word ptr [rdx+76h]
0x1400050be  mov     ecx, 3FFh
0x1400050c3  shr     eax, 10h
0x1400050c6  and     ax, cx
0x1400050c9  test    dx, dx
0x1400050cc  cmovz   dx, ax
0x1400050d0  movzx   eax, dx
0x1400050d3  mov     [rsp+98h+var_48], rax
0x1400050d8  lea     rcx, [rax+8]
0x1400050dc  mov     eax, [rbp+18h]
0x1400050df  cmp     rax, rcx
0x1400050e2  jb      loc_140006466
0x1400050e8  movzx   r13d, dx
0x1400050ec  test    r13d, r13d
0x1400050ef  jz      loc_14000523D
0x1400050f5  mov     rdi, [rbp+8]
0x1400050f9  mov     esi, [rbp+10h]
0x1400050fc  test    rdi, rdi
0x1400050ff  jz      short loc_14000510C
0x140005101  mov     eax, [rdi+28h]
0x140005104  cmp     eax, esi
0x140005106  jbe     loc_1400056F2
0x14000510c  xor     r8d, r8d
0x14000510f  test    byte ptr [rdi+0Ah], 5
0x140005113  jz      loc_1400059A0
0x140005119  mov     rax, [rdi+18h]
0x14000511d  test    rax, rax
0x140005120  jz      loc_1400056DA
0x140005126  mov     ecx, [rdi+28h]
0x140005129  mov     ebp, r13d
0x14000512c  sub     ecx, esi
0x14000512e  mov     r12d, esi
0x140005131  add     r12, rax
0x140005134  mov     r10, r14
0x140005137  cmp     ecx, ebp
0x140005139  mov     [rsp+98h+arg_8], r10
0x140005141  mov     esi, ebp
0x140005143  cmovbe  esi, ecx
0x140005146  test    rbx, rbx
0x140005149  jz      loc_140005558
0x14000514f  mov     rcx, [rbx+50h]
0x140005153  cmp     byte ptr [rcx+1], 1
0x140005157  jnz     short loc_140005186
0x140005159  cmp     byte ptr [rbx+4], 0
0x14000515d  jnz     short loc_140005186
0x14000515f  mov     r9d, [rbx+0Ch]
0x140005163  mov     rax, r8
0x140005166  mov     byte ptr [rbx+4], 1
0x14000516a  cmp     r9d, 0FFFFFFFFh
0x14000516e  jz      short loc_140005181
0x140005170  mov     rdx, [rcx+18h]
0x140005174  test    rdx, rdx
0x140005177  jz      short loc_140005181
0x140005179  lea     rcx, [r9+r9*4]
0x14000517d  lea     rax, [rdx+rcx*4]
0x140005181  lock inc word ptr [rax+10h]
0x140005186  mov     rcx, [rbx+50h]
0x14000518a  mov     eax, [rcx+4]
0x14000518d  test    eax, eax
0x14000518f  jz      loc_140005521
0x140005195  mov     rdx, [rbx+20h]
0x140005199  mov     r10d, [rdx+8]
0x14000519d  cmp     r10d, [rdx+0Ch]
0x1400051a1  jnb     loc_14000575B
0x1400051a7  xor     r11d, r11d
0x1400051aa  inc     dword ptr [rbx+14h]
0x1400051ad  inc     dword ptr [rdx+8]
0x1400051b0  mov     rcx, [rbx+50h]
0x1400051b4  cmp     byte ptr [rcx+1], 1
0x1400051b8  jnz     short loc_140005203
0x1400051ba  mov     r9d, [rbx+0Ch]
0x1400051be  mov     rax, r11
0x1400051c1  cmp     r9d, 0FFFFFFFFh
0x1400051c5  jz      short loc_1400051D8
0x1400051c7  mov     r8, [rcx+18h]
0x1400051cb  test    r8, r8
0x1400051ce  jz      short loc_1400051D8
0x1400051d0  lea     rcx, [r9+r9*4]
0x1400051d4  lea     rax, [r8+rcx*4]
0x1400051d8  lock inc word ptr [rax+0Eh]
0x1400051dd  mov     r9d, [rbx+0Ch]
0x1400051e1  mov     rcx, r11
0x1400051e4  cmp     r9d, 0FFFFFFFFh
0x1400051e8  jz      short loc_1400051FF
0x1400051ea  mov     rax, [rbx+50h]
0x1400051ee  mov     r8, [rax+18h]
0x1400051f2  test    r8, r8
0x1400051f5  jz      short loc_1400051FF
0x1400051f7  lea     rcx, [r9+r9*4]
0x1400051fb  lea     rcx, [r8+rcx*4]
0x1400051ff  lock inc dword ptr [rcx+4]
0x140005203  mov     eax, r10d
0x140005206  mov     r14d, esi
0x140005209  lea     rcx, [rax+rax*2]
0x14000520d  mov     rax, [rdx+10h]
0x140005211  mov     [rax+rcx*8+8], r12
0x140005216  lea     rdx, [rax+rcx*8]
0x14000521a  mov     rax, [rsp+98h+arg_8]
0x140005222  mov     [rdx], rax
0x140005225  mov     eax, esi
0x140005227  shl     eax, 4
0x14000522a  or      eax, 1
0x14000522d  mov     [rdx+10h], eax
0x140005230  sub     ebp, esi
0x140005232  jnz     loc_1400056C0
0x140005238  mov     rbp, [rsp+98h+var_50]
0x14000523d  mov     esi, [rbp+10h]
0x140005240  xor     r12d, r12d
0x140005243  mov     rdi, [rbp+8]
0x140005247  add     esi, r13d
0x14000524a  test    rdi, rdi
0x14000524d  jz      short loc_14000525A
0x14000524f  mov     eax, [rdi+28h]
0x140005252  cmp     eax, esi
0x140005254  jbe     loc_1400058BA
0x14000525a  mov     r14d, [rbp+18h]
0x14000525e  sub     r14d, r13d
0x140005261  mov     dword ptr [rsp+98h+arg_8], r14d
0x140005269  jz      loc_140005501
0x14000526f  test    rdi, rdi
0x140005272  jz      loc_1400064BC
0x140005278  test    byte ptr [rdi+0Ah], 5
0x14000527c  movzx   r13d, byte ptr [r15+74h]
0x140005281  mov     byte ptr [rsp+98h+arg_10], r13b
0x140005289  jz      loc_140005B5E
0x14000528f  mov     rax, [rdi+18h]
0x140005293  test    rax, rax
0x140005296  jz      loc_1400056A8
0x14000529c  mov     ecx, [rdi+28h]
0x14000529f  cmp     ecx, esi
0x1400052a1  jbe     loc_1400056A8
0x1400052a7  mov     r8, [rsp+98h+arg_18]
0x1400052af  sub     ecx, esi
0x1400052b1  add     r8, [rsp+98h+var_48]
0x1400052b6  mov     edx, r14d
0x1400052b9  mov     r9d, esi
0x1400052bc  mov     rsi, r8
0x1400052bf  add     r9, rax
0x1400052c2  mov     [rsp+98h+var_64], edx
0x1400052c6  mov     [rsp+98h+Src], r9
0x1400052cb  lea     r11, [r8+6]
0x1400052cf  mov     [rsp+98h+var_50], r11
0x1400052d4  cmp     ecx, edx
0x1400052d6  mov     r14d, edx
0x1400052d9  cmovbe  r14d, ecx
0x1400052dd  mov     [rsp+98h+var_60], r14d
0x1400052e2  test    rsi, rsi
0x1400052e5  jz      loc_1400058CD
0x1400052eb  test    rbx, rbx
0x1400052ee  jz      loc_1400055A2
0x1400052f4  mov     rax, [rbx+50h]
0x1400052f8  cmp     byte ptr [rax+1], 1
0x1400052fc  jnz     short loc_14000532B
0x1400052fe  cmp     byte ptr [rbx+4], 0
0x140005302  jnz     short loc_14000532B
0x140005304  mov     r8d, [rbx+0Ch]
0x140005308  mov     rcx, r12
0x14000530b  mov     byte ptr [rbx+4], 1
0x14000530f  cmp     r8d, 0FFFFFFFFh
0x140005313  jz      short loc_140005326
0x140005315  mov     rdx, [rax+18h]
0x140005319  test    rdx, rdx
0x14000531c  jz      short loc_140005326
0x14000531e  lea     rcx, [r8+r8*4]
0x140005322  lea     rcx, [rdx+rcx*4]
0x140005326  lock inc word ptr [rcx+10h]
0x14000532b  mov     rcx, [rbx+50h]
0x14000532f  mov     eax, [rcx+4]
0x140005332  test    eax, eax
0x140005334  jz      loc_14000556E
0x14000533a  mov     rdx, [rbx+20h]
0x14000533e  mov     r11d, [rdx+8]
0x140005342  cmp     r11d, [rdx+0Ch]
  ... truncated ...
```
