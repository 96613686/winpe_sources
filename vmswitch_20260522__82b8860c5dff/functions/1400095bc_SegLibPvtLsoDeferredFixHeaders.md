# SegLibPvtLsoDeferredFixHeaders

- ea: `0x1400095bc`
- end: `0x14000acc4`
- name: `SegLibPvtLsoDeferredFixHeaders`
- size: `5896`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140002da4`
- `0x1400082b8`
- `0x140092f04`

## callees

- `0x140006620`
- `0x1400095bc`
- `0x1401bbe10`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000a22f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000a2d7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000a407`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000a4ab`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000a5f5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000a708`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000a7b1`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000a8c9`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000a96e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000aae0`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000a22f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000a2d7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000a407`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000a4ab`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000a5f5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000a708`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000a7b1`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000a8c9`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000a96e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000aae0`

## pseudocode

```c
__int64 __fastcall SegLibPvtLsoDeferredFixHeaders(
        __int64 a1,
        __int64 a2,
        unsigned __int16 *a3,
        __int64 a4,
        int a5,
        int a6)
{
  __int16 v6; // ax
  __int64 *v7; // r14
  __int64 v9; // rdi
  __int64 v10; // r15
  __int64 v11; // rcx
  __int64 v12; // rcx
  unsigned int v13; // eax
  _QWORD **v14; // r12
  _DWORD *v15; // r8
  unsigned int v16; // r15d
  _DWORD *v17; // rbp
  __int64 v18; // r9
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r9
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rcx
  int v25; // eax
  char v26; // r12
  __int64 v27; // rcx
  __int64 v28; // rcx
  unsigned int v29; // eax
  __int64 v30; // r10
  _DWORD *v31; // rdx
  unsigned int v32; // r15d
  __int64 v33; // r9
  __int64 v34; // rax
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // r8
  int v40; // eax
  bool v41; // cf
  __int64 v42; // r12
  char v43; // r15
  __int64 v44; // rcx
  unsigned int v45; // eax
  _DWORD *v46; // rdx
  unsigned int v47; // r12d
  __int64 v48; // r9
  __int64 v49; // rax
  __int64 v50; // r8
  __int64 v51; // r9
  __int64 v52; // rcx
  __int64 v53; // r8
  __int64 v54; // r8
  int v55; // eax
  __int64 v56; // r11
  __int64 v57; // rcx
  unsigned int v58; // eax
  _QWORD *v59; // r8
  unsigned int v60; // r15d
  __int64 v61; // r9
  __int64 v62; // rax
  __int64 v63; // rdx
  __int64 v64; // r9
  __int64 v65; // rcx
  __int64 v66; // rdx
  __int64 v67; // rcx
  unsigned int v68; // eax
  __int64 result; // rax
  unsigned __int32 *v70; // r11
  unsigned __int32 v71; // r15d
  __int64 v72; // rcx
  unsigned int v73; // eax
  _QWORD *v74; // r8
  unsigned int v75; // r12d
  _QWORD **v76; // r10
  __int64 v77; // r9
  __int64 v78; // rax
  __int64 v79; // rdx
  __int64 v80; // r9
  __int64 v81; // rcx
  __int64 v82; // rdx
  __int64 v83; // rcx
  unsigned int v84; // eax
  unsigned __int16 v85; // r11
  unsigned __int16 *v86; // r12
  __int64 v87; // rcx
  unsigned int v88; // eax
  _DWORD *v89; // r8
  unsigned int v90; // r15d
  __int64 v91; // r9
  __int64 v92; // rax
  __int64 v93; // rdx
  __int64 v94; // r9
  __int64 v95; // rcx
  __int64 v96; // rdx
  __int64 v97; // rcx
  __int64 v98; // rdx
  unsigned int v99; // eax
  __int64 v100; // rbp
  unsigned __int16 v101; // ax
  _WORD *v102; // r12
  __int64 v103; // rdx
  unsigned int v104; // r15d
  __int64 v105; // rcx
  __int64 *v106; // r14
  __int64 v107; // rcx
  unsigned int v108; // eax
  _DWORD *v109; // r8
  unsigned int v110; // ebp
  __int64 v111; // r9
  __int64 v112; // rax
  __int64 v113; // rdx
  __int64 v114; // r9
  __int64 v115; // rcx
  __int64 v116; // rdx
  __int64 v117; // rcx
  int v118; // eax
  __int64 *v119; // r14
  __int16 v120; // r12
  unsigned __int16 v121; // r12
  unsigned __int16 *v122; // r15
  __int64 v123; // rcx
  unsigned int v124; // eax
  _DWORD *v125; // r8
  unsigned int v126; // ebp
  __int64 v127; // r9
  __int64 v128; // rax
  __int64 v129; // rdx
  __int64 v130; // r9
  __int64 v131; // rcx
  __int64 v132; // rdx
  __int64 v133; // rcx
  __int64 v134; // rdx
  int v135; // eax
  int v136; // edx
  _WORD *v137; // r12
  __int64 v138; // rdx
  unsigned int v139; // ebp
  __int64 v140; // rcx
  unsigned int v141; // eax
  _DWORD *v142; // r8
  unsigned int v143; // r15d
  __int64 v144; // r9
  __int64 v145; // rax
  __int64 v146; // rdx
  __int64 v147; // rcx
  __int64 v148; // rdx
  __int64 v149; // rcx
  __int64 v150; // rdx
  unsigned int v151; // eax
  __int64 v152; // r8
  __int64 v153; // rax
  __int64 v154; // r8
  __int64 v155; // rax
  _WORD *v156; // r15
  __int16 v157; // r12
  __int64 v158; // rcx
  __int64 *v159; // r14
  __int64 v160; // rcx
  unsigned int v161; // eax
  _DWORD *v162; // r8
  unsigned int v163; // ebp
  __int64 v164; // r9
  __int64 v165; // rax
  __int64 v166; // rdx
  __int64 v167; // rcx
  __int64 v168; // rdx
  __int64 v169; // rcx
  __int64 v170; // rdx
  unsigned int v171; // eax
  char v172; // al
  char v173; // al
  char v174; // al
  char v175; // al
  __int64 v176; // r8
  __int64 v177; // rax
  __int64 v178; // r8
  __int64 v179; // rax
  __int64 v180; // r8
  __int64 v181; // rax
  __int64 v182; // r8
  __int64 v183; // rax
  _DWORD *v184; // rax
  int v185; // ecx
  __int64 v186; // rdx
  __int64 v187; // rcx
  __int64 v188; // rax
  __int64 v189; // rdx
  __int64 v190; // r9
  volatile signed __int32 *v191; // rcx
  __int64 v192; // rdx
  _DWORD *v193; // rax
  __int64 v194; // rdx
  __int64 v195; // rcx
  __int64 v196; // rax
  __int64 v197; // rdx
  __int64 v198; // r9
  volatile signed __int32 *v199; // rcx
  __int64 v200; // rdx
  char v201; // al
  char v202; // al
  char v203; // al
  char v204; // al
  _DWORD *v205; // rax
  int v206; // ecx
  __int64 v207; // rdx
  __int64 v208; // rcx
  __int64 v209; // rax
  __int64 v210; // rdx
  __int64 v211; // r9
  volatile signed __int32 *v212; // rcx
  __int64 v213; // rdx
  _DWORD *v214; // rax
  int v215; // ecx
  __int64 v216; // rdx
  __int64 v217; // rcx
  __int64 v218; // rax
  __int64 v219; // rdx
  __int64 v220; // r9
  volatile signed __int32 *v221; // rcx
  __int64 v222; // rdx
  __int64 v223; // r8
  __int64 v224; // rax
  __int64 v225; // r8
  __int64 v226; // rax
  __int64 v227; // r8
  __int64 v228; // rax
  _DWORD *v229; // rax
  int v230; // ecx
  __int64 v231; // rdx
  __int64 v232; // rcx
  __int64 v233; // rax
  __int64 v234; // rdx
  __int64 v235; // r9
  volatile signed __int32 *v236; // rcx
  __int64 v237; // rdx
  _DWORD *v238; // rax
  int v239; // ecx
  __int64 v240; // rdx
  __int64 v241; // rcx
  __int64 v242; // rax
  __int64 v243; // rdx
  __int64 v244; // r9
  volatile signed __int32 *v245; // rcx
  __int64 v246; // rdx
  _DWORD *v247; // rax
  int v248; // ecx
  __int64 v249; // rdx
  __int64 v250; // rcx
  __int64 v251; // rax
  __int64 v252; // rdx
  __int64 v253; // r9
  volatile signed __int32 *v254; // rcx
  __int64 v255; // rdx
  _DWORD *v256; // rax
  int v257; // ecx
  __int64 v258; // r8
  __int64 v259; // rcx
  __int64 v260; // rax
  __int64 v261; // r8
  __int64 v262; // r9
  volatile signed __int32 *v263; // rcx
  __int64 v264; // r8
  _DWORD *v265; // rax
  int v266; // ecx
  __int64 v267; // r8
  __int64 v268; // rcx
  __int64 v269; // rax
  __int64 v270; // r8
  __int64 v271; // r9
  volatile signed __int32 *v272; // rcx
  __int64 v273; // r8
  __int64 v274; // r8
  __int64 v275; // rax
  _DWORD *v276; // rax
  int v277; // ecx
  __int64 v278; // rdx
  __int64 v279; // rcx
  __int64 v280; // rax
  __int64 v281; // rdx
  __int64 v282; // r9
  volatile signed __int32 *v283; // rcx
  __int64 v284; // rdx
  unsigned __int16 v285; // [rsp+20h] [rbp-68h]
  _QWORD **v286; // [rsp+28h] [rbp-60h]
  unsigned __int32 *v287; // [rsp+30h] [rbp-58h]
  __int16 v288; // [rsp+90h] [rbp+8h]
  __int64 v289; // [rsp+98h] [rbp+10h]
  unsigned __int16 v292; // [rsp+B0h] [rbp+28h]

  v289 = a2;
  v6 = *(_WORD *)(a2 + 24);
  v7 = (__int64 *)(a1 + 80);
  v285 = -13108;
  v9 = 0;
  v10 = a4;
  if ( a5 == *(_DWORD *)(a2 + 8) )
  {
    v26 = *(_BYTE *)(a2 + 27) & 2;
    v288 = v6 + *(_WORD *)(a2 + 4) - a6;
    if ( !a1 )
      goto LABEL_168;
    v27 = *v7;
    if ( *(_BYTE *)(*v7 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
    {
      v180 = *(unsigned int *)(a1 + 12);
      v181 = 0;
      *(_BYTE *)(a1 + 4) = 1;
      if ( (_DWORD)v180 != -1 )
      {
        a2 = *(_QWORD *)(v27 + 24);
        if ( a2 )
          v181 = a2 + 20 * v180;
      }
      _InterlockedAdd16((volatile signed __int16 *)(v181 + 16), 1u);
    }
    v7 = (__int64 *)(a1 + 80);
    v28 = *(_QWORD *)(a1 + 80);
    v29 = *(_DWORD *)(v28 + 4);
    if ( v29 )
    {
      v30 = a1 + 32;
      v31 = *(_DWORD **)(a1 + 32);
      v286 = (_QWORD **)(a1 + 32);
      v32 = v31[2];
      if ( v32 >= v31[3] )
      {
        v32 = 0;
        if ( *(_DWORD *)(a1 + 16) < v29
          && (v256 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v28 + 64)), (v31 = v256) != 0) )
        {
          *(_QWORD *)v256 = 0;
          v30 = a1 + 32;
          v256[2] = 0;
          v257 = *(_DWORD *)(*v7 + 8);
          *((_QWORD *)v256 + 2) = v256 + 6;
          v256[3] = v257;
          **(_QWORD **)(a1 + 32) = v256;
          v258 = *v7;
          ++*(_DWORD *)(a1 + 16);
          *(_QWORD *)(a1 + 32) = v256;
          if ( *(_BYTE *)(v258 + 1) == 1 )
          {
            v259 = *(unsigned int *)(a1 + 12);
            v260 = 0;
            if ( (_DWORD)v259 != -1 )
            {
              v261 = *(_QWORD *)(v258 + 24);
              if ( v261 )
                v260 = v261 + 20 * v259;
            }
            _InterlockedAdd16((volatile signed __int16 *)(v260 + 12), 1u);
            v262 = *(unsigned int *)(a1 + 12);
            v263 = 0;
            if ( (_DWORD)v262 != -1 )
            {
              v264 = *(_QWORD *)(*v7 + 24);
              if ( v264 )
                v263 = (volatile signed __int32 *)(v264 + 20 * v262);
            }
            _InterlockedAdd(v263, 1u);
          }
        }
        else
        {
          LOBYTE(v31) = 1;
          BLFlushBatchOpContextEx(a1, v31, 0);
          v31 = (_DWORD *)(a1 + 56);
          v30 = a1 + 32;
        }
      }
      v17 = (_DWORD *)(a1 + 20);
      ++*(_DWORD *)(a1 + 20);
      ++v31[2];
      if ( *(_BYTE *)(*v7 + 1) == 1 )
      {
        v33 = *(unsigned int *)(a1 + 12);
        v34 = 0;
        if ( (_DWORD)v33 != -1 )
        {
          v35 = *(_QWORD *)(*v7 + 24);
          if ( v35 )
            v34 = v35 + 20 * v33;
        }
        _InterlockedAdd16((volatile signed __int16 *)(v34 + 14), 1u);
        v36 = *(unsigned int *)(a1 + 12);
        v37 = 0;
        if ( (_DWORD)v36 != -1 )
        {
          v38 = *(_QWORD *)(*v7 + 24);
          if ( v38 )
            v37 = v38 + 20 * v36;
        }
        _InterlockedAdd((volatile signed __int32 *)(v37 + 4), 1u);
      }
      a2 = *((_QWORD *)v31 + 2);
      v39 = 3LL * v32;
      v40 = *(_DWORD *)(a2 + 24LL * v32 + 16);
      v41 = v26 != 0;
      v42 = a4;
      *(_QWORD *)(a2 + 8 * v39) = a4;
      *(_DWORD *)(a2 + 8 * v39 + 8) = 104;
      *(_DWORD *)(a2 + 8 * v39 + 16) = v40 & 0xFFFFFFF0 | (5 - v41);
      goto LABEL_28;
    }
    if ( *(_DWORD *)(a1 + 20) )
    {
      LOBYTE(a2) = 1;
      BLFlushBatchOpContextEx(a1, a2, 0);
    }
    if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (*(_BYTE *)(a1 + 8) & 6) == 6 )
    {
      (*(void (**)(void))(*v7 + 32))();
      v201 = *(_BYTE *)(v10 + 13);
      if ( v26 )
        v202 = v201 | 1;
      else
        v202 = v201 & 0xFE;
      *(_BYTE *)(v10 + 13) = v202;
      (*(void (**)(void))(*v7 + 40))();
    }
    else
    {
LABEL_168:
      v172 = *(_BYTE *)(v10 + 13);
      if ( v26 )
        v173 = v172 | 1;
      else
        v173 = v172 & 0xFE;
      *(_BYTE *)(v10 + 13) = v173;
    }
    v42 = a4;
    v30 = a1 + 32;
    v286 = (_QWORD **)(a1 + 32);
    v17 = (_DWORD *)(a1 + 20);
LABEL_28:
    v43 = *(_BYTE *)(v289 + 27) & 4;
    if ( !a1 )
      goto LABEL_175;
    v44 = *v7;
    if ( *(_BYTE *)(*v7 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
    {
      v182 = *(unsigned int *)(a1 + 12);
      v183 = 0;
      *(_BYTE *)(a1 + 4) = 1;
      if ( (_DWORD)v182 != -1 )
      {
        a2 = *(_QWORD *)(v44 + 24);
        if ( a2 )
          v183 = a2 + 20 * v182;
      }
      _InterlockedAdd16((volatile signed __int16 *)(v183 + 16), 1u);
    }
    v45 = *(_DWORD *)(*v7 + 4);
    if ( v45 )
    {
      v46 = *(_DWORD **)v30;
      v47 = *(_DWORD *)(*(_QWORD *)v30 + 8LL);
      if ( v47 >= *(_DWORD *)(*(_QWORD *)v30 + 12LL) )
      {
        v47 = 0;
        if ( *(_DWORD *)(a1 + 16) < v45
          && (v265 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*v7 + 64)), (v46 = v265) != 0) )
        {
          *(_QWORD *)v265 = 0;
          v265[2] = 0;
          v266 = *(_DWORD *)(*v7 + 8);
          *((_QWORD *)v265 + 2) = v265 + 6;
          v265[3] = v266;
          **(_QWORD **)(a1 + 32) = v265;
          v267 = *v7;
          ++*(_DWORD *)(a1 + 16);
          *(_QWORD *)(a1 + 32) = v265;
          if ( *(_BYTE *)(v267 + 1) == 1 )
          {
            v268 = *(unsigned int *)(a1 + 12);
            v269 = 0;
            if ( (_DWORD)v268 != -1 )
            {
              v270 = *(_QWORD *)(v267 + 24);
              if ( v270 )
                v269 = v270 + 20 * v268;
            }
            _InterlockedAdd16((volatile signed __int16 *)(v269 + 12), 1u);
            v271 = *(unsigned int *)(a1 + 12);
            v272 = 0;
            if ( (_DWORD)v271 != -1 )
            {
              v273 = *(_QWORD *)(*v7 + 24);
              if ( v273 )
                v272 = (volatile signed __int32 *)(v273 + 20 * v271);
            }
            _InterlockedAdd(v272, 1u);
          }
        }
        else
        {
          LOBYTE(v46) = 1;
          BLFlushBatchOpContextEx(a1, v46, 0);
          v46 = (_DWORD *)(a1 + 56);
        }
      }
      ++*v17;
      ++v46[2];
      if ( *(_BYTE *)(*v7 + 1) == 1 )
      {
        v48 = *(unsigned int *)(a1 + 12);
        v49 = 0;
        if ( (_DWORD)v48 != -1 )
        {
          v50 = *(_QWORD *)(*v7 + 24);
          if ( v50 )
            v49 = v50 + 20 * v48;
        }
        _InterlockedAdd16((volatile signed __int16 *)(v49 + 14), 1u);
        v51 = *(unsigned int *)(a1 + 12);
        v52 = 0;
        if ( (_DWORD)v51 != -1 )
        {
          v53 = *(_QWORD *)(*v7 + 24);
          if ( v53 )
            v52 = v53 + 20 * v51;
        }
        _InterlockedAdd((volatile signed __int32 *)(v52 + 4), 1u);
      }
      a2 = *((_QWORD *)v46 + 2);
      v54 = 3LL * v47;
      v55 = *(_DWORD *)(a2 + 24LL * v47 + 16);
      v56 = a4;
      *(_QWORD *)(a2 + 8 * v54) = a4;
      *(_DWORD *)(a2 + 8 * v54 + 8) = 107;
      *(_DWORD *)(a2 + 8 * v54 + 16) = v55 & 0xFFFFFFF0 | (5 - (v43 != 0));
      goto LABEL_41;
    }
    if ( *v17 )
    {
      LOBYTE(a2) = 1;
      BLFlushBatchOpContextEx(a1, a2, 0);
    }
    if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (*(_BYTE *)(a1 + 8) & 6) == 6 )
    {
      (*(void (**)(void))(*v7 + 32))();
      v203 = *(_BYTE *)(v42 + 13);
      if ( v43 )
        v204 = v203 | 8;
      else
        v204 = v203 & 0xF7;
      *(_BYTE *)(v42 + 13) = v204;
      (*(void (**)(void))(*v7 + 40))();
    }
    else
    {
LABEL_175:
      v174 = *(_BYTE *)(v42 + 13);
      if ( v43 )
        v175 = v174 | 8;
      else
        v175 = v174 & 0xF7;
      *(_BYTE *)(v42 + 13) = v175;
    }
    v56 = a4;
LABEL_41:
    v14 = (_QWORD **)(a1 + 32);
    goto LABEL_60;
  }
  v288 = *(_WORD *)a2 + v6;
  if ( !a1 )
    goto LABEL_46;
  v11 = *v7;
  if ( *(_BYTE *)(*v7 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
  {
    v152 = *(unsigned int *)(a1 + 12);
    v153 = 0;
    *(_BYTE *)(a1 + 4) = 1;
    if ( (_DWORD)v152 != -1 )
    {
      a2 = *(_QWORD *)(v11 + 24);
      if ( a2 )
        v153 = a2 + 20 * v152;
    }
    _InterlockedAdd16((volatile signed __int16 *)(v153 + 16), 1u);
  }
  v7 = (__int64 *)(a1 + 80);
  v12 = *(_QWORD *)(a1 + 80);
  v13 = *(_DWORD *)(v12 + 4);
  if ( v13 )
  {
    v14 = (_QWORD **)(a1 + 32);
    v15 = *(_DWORD **)(a1 + 32);
    v286 = (_QWORD **)(a1 + 32);
    v16 = v15[2];
    if ( v16 >= v15[3] )
    {
      v16 = 0;
      if ( *(_DWORD *)(a1 + 16) < v13
        && (v205 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v12 + 64)), (v15 = v205) != 0) )
      {
        *(_QWORD *)v205 = 0;
        v205[2] = 0;
        v206 = *(_DWORD *)(*v7 + 8);
        *((_QWORD *)v205 + 2) = v205 + 6;
        v205[3] = v206;
        **v14 = v205;
        v207 = *v7;
        ++*(_DWORD *)(a1 + 16);
        *v14 = v205;
        if ( *(_BYTE *)(v207 + 1) == 1 )
        {
          v208 = *(unsigned int *)(a1 + 12);
          v209 = 0;
          if ( (_DWORD)v208 != -1 )
          {
            v210 = *(_QWORD *)(v207 + 24);
            if ( v210 )
              v209 = v210 + 20 * v208;
          }
          _InterlockedAdd16((volatile signed __int16 *)(v209 + 12), 1u);
          v211 = *(unsigned int *)(a1 + 12);
          v212 = 0;
          if ( (_DWORD)v211 != -1 )
          {
            v213 = *(_QWORD *)(*v7 + 24);
            if ( v213 )
              v212 = (volatile signed __int32 *)(v213 + 20 * v211);
          }
          _InterlockedAdd(v212, 1u);
        }
      }
      else
      {
        LOBYTE(a2) = 1;
        BLFlushBatchOpContextEx(a1, a2, 0);
        v15 = (_DWORD *)(a1 + 56);
      }
    }
    v17 = (_DWORD *)(a1 + 20);
    ++*(_DWORD *)(a1 + 20);
    ++v15[2];
    if ( *(_BYTE *)(*v7 + 1) == 1 )
    {
      v18 = *(unsigned int *)(a1 + 12);
      v19 = 0;
      if ( (_DWORD)v18 != -1 )
      {
        v20 = *(_QWORD *)(*v7 + 24);
        if ( v20 )
          v19 = v20 + 20 * v18;
      }
      _InterlockedAdd16((volatile signed __int16 *)(v19 + 14), 1u);
      v21 = *(unsigned int *)(a1 + 12);
      v22 = 0;
      if ( (_DWORD)v21 != -1 )
      {
        v23 = *(_QWORD *)(*v7 + 24);
        if ( v23 )
          v22 = v23 + 20 * v21;
      }
      _InterlockedAdd((volatile signed __int32 *)(v22 + 4), 1u);
    }
    v24 = *((_QWORD *)v15 + 2);
    a2 = 3LL * v16;
    v25 = *(_DWORD *)(v24 + 24LL * v16 + 16);
    v10 = a4;
    *(_QWORD *)(v24 + 8 * a2) = a4;
    *(_DWORD *)(v24 + 8 * a2 + 16) = v25 & 0xFFFFFFF0 | 5;
    *(_DWORD *)(v24 + 8 * a2 + 8) = 104;
    goto LABEL_48;
  }
  if ( *(_DWORD *)(a1 + 20) )
  {
    LOBYTE(a2) = 1;
    BLFlushBatchOpContextEx(a1, a2, 0);
  }
  if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (*(_BYTE *)(a1 + 8) & 6) == 6 )
  {
    (*(void (**)(void))(*v7 + 32))();
    *(_BYTE *)(v10 + 13) &= ~1u;
    (*(void (**)(void))(*v7 + 40))();
  }
  else
  {
LABEL_46:
    *(_BYTE *)(v10 + 13) &= ~1u;
  }
  v14 = (_QWORD **)(a1 + 32);
  v286 = (_QWORD **)(a1 + 32);
  v17 = (_DWORD *)(a1 + 20);
  if ( !a1 )
    goto LABEL_134;
LABEL_48:
  v57 = *v7;
  if ( *(_BYTE *)(*v7 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
  {
    v154 = *(unsigned int *)(a1 + 12);
    v155 = 0;
    *(_BYTE *)(a1 + 4) = 1;
    if ( (_DWORD)v154 != -1 )
    {
      a2 = *(_QWORD *)(v57 + 24);
      if ( a2 )
        v155 = a2 + 20 * v154;
    }
    _InterlockedAdd16((volatile signed __int16 *)(v155 + 16), 1u);
  }
  v58 = *(_DWORD *)(*v7 + 4);
  if ( !v58 )
  {
    if ( *v17 )
    {
      LOBYTE(a2) = 1;
      BLFlushBatchOpContextEx(a1, a2, 0);
    }
    if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (*(_BYTE *)(a1 + 8) & 6) == 6 )
    {
      (*(void (**)(void))(*v7 + 32))();
      *(_BYTE *)(v10 + 13) &= ~8u;
      (*(void (**)(void))(*v7 + 40))();
      goto LABEL_135;
    }
LABEL_134:
    *(_BYTE *)(v10 + 13) &= ~8u;
LABEL_135:
    v56 = a4;
    v286 = v14;
    goto LABEL_60;
  }
  v59 = *v14;
  v60 = *((_DWORD *)*v14 + 2);
  if ( v60 >= *((_DWORD *)*v14 + 3) )
  {
    v60 = 0;
    if ( *(_DWORD *)(a1 + 16) < v58
      && (v214 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*v7 + 64)), (v59 = v214) != 0) )
    {
      *(_QWORD *)v214 = 0;
      v214[2] = 0;
      v215 = *(_DWORD *)(*v7 + 8);
      *((_QWORD *)v214 + 2) = v214 + 6;
      v214[3] = v215;
      **v14 = v214;
      v216 = *v7;
      ++*(_DWORD *)(a1 + 16);
      *v14 = v214;
      if ( *(_BYTE *)(v216 + 1) == 1 )
      {
        v217 = *(unsigned int *)(a1 + 12);
        v218 = 0;
        if ( (_DWORD)v217 != -1 )
        {
          v219 = *(_QWORD *)(v216 + 24);
          if ( v219 )
            v218 = v219 + 20 * v217;
        }
        _InterlockedAdd16((volatile signed __int16 *)(v218 + 12), 1u);
        v220 = *(unsigned int *)(a1 + 12);
        v221 = 0;
        if ( (_DWORD)v220 != -1 )
        {
          v222 = *(_QWORD *)(*v7 + 24);
          if ( v222 )
            v221 = (volatile signed __int32 *)(v222 + 20 * v220);
        }
        _InterlockedAdd(v221, 1u);
      }
    }
    else
    {
      LOBYTE(a2) = 1;
      BLFlushBatchOpContextEx(a1, a2, 0);
      v59 = (_QWORD *)(a1 + 56);
    }
  }
  ++*v17;
  ++*((_DWORD *)v59 + 2);
  if ( *(_BYTE *)(*v7 + 1) == 1 )
  {
    v61 = *(unsigned int *)(a1 + 12);
    v62 = 0;
    if ( (_DWORD)v61 != -1 )
    {
      v63 = *(_QWORD *)(*v7 + 24);
      if ( v63 )
        v62 = v63 + 20 * v61;
    }
    _InterlockedAdd16((volatile signed __int16 *)(v62 + 14), 1u);
    v64 = *(unsigned int *)(a1 + 12);
    v65 = 0;
    if ( (_DWORD)v64 != -1 )
    {
      v66 = *(_QWORD *)(*v7 + 24);
      if ( v66 )
        v65 = v66 + 20 * v64;
    }
    _InterlockedAdd((volatile signed __int32 *)(v65 + 4), 1u);
  }
  v67 = v59[2];
  a2 = 3LL * v60;
  v56 = a4;
  v68 = *(_DWORD *)(v67 + 24LL * v60 + 16) & 0xFFFFFFF0 | 5;
  *(_QWORD *)(v67 + 8 * a2) = a4;
  *(_DWORD *)(v67 + 8 * a2 + 16) = v68;
  *(_DWORD *)(v67 + 8 * a2 + 8) = 107;
LABEL_60:
  result = v289;
  v70 = (unsigned __int32 *)(v56 + 4);
  v287 = v70;
  v71 = _byteswap_ulong(*(_DWORD *)(v289 + 12) + a6);
  if ( !a1 )
    goto LABEL_197;
  v72 = *v7;
  if ( *(_BYTE *)(*v7 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
  {
    v176 = *(unsigned int *)(a1 + 12);
    v177 = 0;
    *(_BYTE *)(a1 + 4) = 1;
    if ( (_DWORD)v176 != -1 )
    {
      a2 = *(_QWORD *)(v72 + 24);
      if ( a2 )
        v177 = a2 + 20 * v176;
    }
    _InterlockedAdd16((volatile signed __int16 *)(v177 + 16), 1u);
  }
  v73 = *(_DWORD *)(*v7 + 4);
  if ( !v73 )
  {
    if ( *v17 )
    {
      LOBYTE(a2) = 1;
      BLFlushBatchOpContextEx(a1, a2, 0);
      v70 = v287;
    }
    if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (result = *(_DWORD *)(a1 + 8) & 6, (*(_BYTE *)(a1 + 8) & 6) == 6) )
    {
      (*(void (**)(void))(*v7 + 32))();
      *(_DWORD *)(a4 + 4) = v71;
      result = (*(__int64 (**)(void))(*v7 + 40))();
      goto LABEL_198;
    }
LABEL_197:
    *v70 = v71;
LABEL_198:
    v76 = v286;
    goto LABEL_74;
  }
  v74 = *v14;
  v75 = *((_DWORD *)*v14 + 2);
  if ( v75 >= *((_DWORD *)v74 + 3) )
  {
    v75 = 0;
    if ( *(_DWORD *)(a1 + 16) < v73
      && (v184 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*v7 + 64)), (v74 = v184) != 0) )
    {
      v76 = v286;
      *(_QWORD *)v184 = 0;
      v184[2] = 0;
      v185 = *(_DWORD *)(*v7 + 8);
      *((_QWORD *)v184 + 2) = v184 + 6;
      v184[3] = v185;
      **v286 = v184;
      v186 = *v7;
      ++*(_DWORD *)(a1 + 16);
      *v286 = v184;
      if ( *(_BYTE *)(v186 + 1) == 1 )
      {
        v187 = *(unsigned int *)(a1 + 12);
        v188 = 0;
        if ( (_DWORD)v187 != -1 )
        {
          v189 = *(_QWORD *)(v186 + 24);
          if ( v189 )
            v188 = v189 + 20 * v187;
        }
        _InterlockedAdd16((volatile signed __int16 *)(v188 + 12), 1u);
        v190 = *(unsigned int *)(a1 + 12);
        v191 = 0;
        if ( (_DWORD)v190 != -1 )
        {
          v192 = *(_QWORD *)(*v7 + 24);
          if ( v192 )
            v191 = (volatile signed __int32 *)(v192 + 20 * v190);
        }
        _InterlockedAdd(v191, 1u);
      }
    }
    else
    {
      LOBYTE(a2) = 1;
      BLFlushBatchOpContextEx(a1, a2, 0);
      v76 = v286;
      v74 = (_QWORD *)(a1 + 56);
    }
    v70 = v287;
  }
  else
  {
    v76 = v286;
  }
  ++*v17;
  ++*((_DWORD *)v74 + 2);
  if ( *(_BYTE *)(*v7 + 1) == 1 )
  {
    v77 = *(unsigned int *)(a1 + 12);
    v78 = 0;
    if ( (_DWORD)v77 != -1 )
    {
      v79 = *(_QWORD *)(*v7 + 24);
      if ( v79 )
        v78 = v79 + 20 * v77;
    }
    _InterlockedAdd16((volatile signed __int16 *)(v78 + 14), 1u);
    v80 = *(unsigned int *)(a1 + 12);
    v81 = 0;
    if ( (_DWORD)v80 != -1 )
    {
      v82 = *(_QWORD *)(*v7 + 24);
      if ( v82 )
        v81 = v82 + 20 * v80;
    }
    _InterlockedAdd((volatile signed __int32 *)(v81 + 4), 1u);
  }
  v83 = v74[2];
  a2 = 3LL * v75;
  v84 = *(_DWORD *)(v83 + 24LL * v75 + 16) & 0xFFFFFFF3;
  *(_QWORD *)(v83 + 8 * a2) = v70;
  result = v84 | 3;
  *(_DWORD *)(v83 + 8 * a2 + 8) = v71;
  *(_DWORD *)(v83 + 8 * a2 + 16) = result;
LABEL_74:
  if ( (*(_BYTE *)(v289 + 27) & 1) == 0 )
  {
    result = 0x7FFF;
    v85 = __ROR2__((*(_WORD *)(v289 + 16) + a5) & 0x7FFF, 8);
    v86 = a3 + 2;
    v292 = v85;
    v285 = v85;
    if ( !a1 )
      goto LABEL_140;
    v87 = *v7;
    if ( *(_BYTE *)(*v7 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
    {
      v178 = *(unsigned int *)(a1 + 12);
      v179 = 0;
      *(_BYTE *)(a1 + 4) = 1;
      if ( (_DWORD)v178 != -1 )
      {
        a2 = *(_QWORD *)(v87 + 24);
        if ( a2 )
          v179 = a2 + 20 * v178;
      }
      _InterlockedAdd16((volatile signed __int16 *)(v179 + 16), 1u);
    }
    v88 = *(_DWORD *)(*v7 + 4);
    if ( v88 )
    {
      v89 = *v76;
      v90 = *((_DWORD *)*v76 + 2);
      if ( v90 >= *((_DWORD *)*v76 + 3) )
      {
        v90 = 0;
        if ( *(_DWORD *)(a1 + 16) < v88
          && (v193 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*v7 + 64)), (v89 = v193) != 0) )
        {
          *(_QWORD *)v193 = 0;
          v193[2] = 0;
          v193[3] = *(_DWORD *)(*v7 + 8);
          *((_QWORD *)v193 + 2) = v193 + 6;
          **v286 = v193;
          v194 = *v7;
          ++*(_DWORD *)(a1 + 16);
          *v286 = v193;
          if ( *(_BYTE *)(v194 + 1) == 1 )
          {
            v195 = *(unsigned int *)(a1 + 12);
            v196 = 0;
            if ( (_DWORD)v195 != -1 )
            {
              v197 = *(_QWORD *)(v194 + 24);
              if ( v197 )
                v196 = v197 + 20 * v195;
            }
            _InterlockedAdd16((volatile signed __int16 *)(v196 + 12), 1u);
            v198 = *(unsigned int *)(a1 + 12);
            v199 = 0;
            if ( (_DWORD)v198 != -1 )
            {
              v200 = *(_QWORD *)(*v7 + 24);
              if ( v200 )
                v199 = (volatile signed __int32 *)(v200 + 20 * v198);
            }
            _InterlockedAdd(v199, 1u);
          }
        }
        else
        {
          LOBYTE(a2) = 1;
          BLFlushBatchOpContextEx(a1, a2, 0);
          v89 = (_DWORD *)(a1 + 56);
        }
        v85 = v292;
      }
      ++*v17;
      ++v89[2];
      if ( *(_BYTE *)(*v7 + 1) == 1 )
      {
        v91 = *(unsigned int *)(a1 + 12);
        v92 = 0;
        if ( (_DWORD)v91 != -1 )
        {
          v93 = *(_QWORD *)(*v7 + 24);
          if ( v93 )
            v92 = v93 + 20 * v91;
        }
        _InterlockedAdd16((volatile signed __int16 *)(v92 + 14), 1u);
        v94 = *(unsigned int *)(a1 + 12);
        v95 = 0;
        if ( (_DWORD)v94 != -1 )
        {
          v96 = *(_QWORD *)(*v7 + 24);
          if ( v96 )
            v95 = v96 + 20 * v94;
        }
        _InterlockedAdd((volatile signed __int32 *)(v95 + 4), 1u);
      }
      v97 = *((_QWORD *)v89 + 2);
      v98 = 3LL * v90;
      v99 = *(_DWORD *)(v97 + 24LL * v90 + 16) & 0xFFFFFFF2;
      *(_QWORD *)(v97 + 8 * v98) = v86;
      result = v99 | 2;
      *(_WORD *)(v97 + 8 * v98 + 8) = v85;
      *(_DWORD *)(v97 + 8 * v98 + 16) = result;
      goto LABEL_88;
    }
    if ( *v17 )
    {
      LOBYTE(a2) = 1;
      BLFlushBatchOpContextEx(a1, a2, 0);
      v85 = v292;
    }
    if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (result = *(_DWORD *)(a1 + 8) & 6, (*(_BYTE *)(a1 + 8) & 6) == 6) )
    {
      (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
      *v86 = v292;
      result = (*(__int64 (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
    }
    else
    {
LABEL_140:
      *v86 = v85;
    }
  }
LABEL_88:
  v100 = v289;
  if ( (*(_BYTE *)(v289 + 27) & 0x10) != 0 )
    return result;
  v101 = __ROR2__(v288 - *(_WORD *)(v289 + 22), 8);
  v102 = (_WORD *)(a4 + 16);
  v103 = *(unsigned __int16 *)(v289 + 20) + (unsigned int)v101;
  v104 = (unsigned __int16)(*(_WORD *)(v289 + 20) + v101) + WORD1(v103);
  if ( !a1 )
    goto LABEL_182;
  v105 = *(_QWORD *)(a1 + 80);
  if ( *(_BYTE *)(v105 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
  {
    v223 = *(unsigned int *)(a1 + 12);
    v224 = 0;
    *(_BYTE *)(a1 + 4) = 1;
    if ( (_DWORD)v223 != -1 )
    {
      v103 = *(_QWORD *)(v105 + 24);
      if ( v103 )
        v224 = v103 + 20 * v223;
    }
    _InterlockedAdd16((volatile signed __int16 *)(v224 + 16), 1u);
  }
  v106 = (__int64 *)(a1 + 80);
  v107 = *(_QWORD *)(a1 + 80);
  v108 = *(_DWORD *)(v107 + 4);
  if ( v108 )
  {
    v109 = *(_DWORD **)(a1 + 32);
    v110 = v109[2];
    if ( v110 >= v109[3] )
    {
      v110 = 0;
      if ( *(_DWORD *)(a1 + 16) < v108
        && (v229 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v107 + 64)), (v109 = v229) != 0) )
      {
        *(_QWORD *)v229 = 0;
        v229[2] = 0;
        v230 = *(_DWORD *)(*v106 + 8);
        *((_QWORD *)v229 + 2) = v229 + 6;
        v229[3] = v230;
        **(_QWORD **)(a1 + 32) = v229;
        v231 = *v106;
        ++*(_DWORD *)(a1 + 16);
        *(_QWORD *)(a1 + 32) = v229;
        if ( *(_BYTE *)(v231 + 1) == 1 )
        {
          v232 = *(unsigned int *)(a1 + 12);
          v233 = 0;
          if ( (_DWORD)v232 != -1 )
          {
            v234 = *(_QWORD *)(v231 + 24);
            if ( v234 )
              v233 = v234 + 20 * v232;
          }
          _InterlockedAdd16((volatile signed __int16 *)(v233 + 12), 1u);
          v235 = *(unsigned int *)(a1 + 12);
          v236 = 0;
          if ( (_DWORD)v235 != -1 )
          {
            v237 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
            if ( v237 )
              v236 = (volatile signed __int32 *)(v237 + 20 * v235);
          }
          _InterlockedAdd(v236, 1u);
          v106 = (__int64 *)(a1 + 80);
        }
      }
      else
      {
        LOBYTE(v103) = 1;
        BLFlushBatchOpContextEx(a1, v103, 0);
        v109 = (_DWORD *)(a1 + 56);
      }
    }
    ++*(_DWORD *)(a1 + 20);
    ++v109[2];
    if ( *(_BYTE *)(*v106 + 1) == 1 )
    {
      v111 = *(unsigned int *)(a1 + 12);
      v112 = 0;
      if ( (_DWORD)v111 != -1 )
      {
        v113 = *(_QWORD *)(*v106 + 24);
        if ( v113 )
          v112 = v113 + 20 * v111;
      }
      _InterlockedAdd16((volatile signed __int16 *)(v112 + 14), 1u);
      v114 = *(unsigned int *)(a1 + 12);
      v115 = 0;
      if ( (_DWORD)v114 != -1 )
      {
        v116 = *(_QWORD *)(*v106 + 24);
        if ( v116 )
          v115 = v116 + 20 * v114;
      }
      _InterlockedAdd((volatile signed __int32 *)(v115 + 4), 1u);
    }
    v117 = *((_QWORD *)v109 + 2);
    v103 = 3LL * v110;
    v118 = *(_DWORD *)(v117 + 24LL * v110 + 16);
    v100 = v289;
    *(_QWORD *)(v117 + 8 * v103) = v102;
    *(_DWORD *)(v117 + 8 * v103 + 16) = v118 & 0xFFFFFFF0 | 2;
    *(_WORD *)(v117 + 8 * v103 + 8) = v104;
    goto LABEL_102;
  }
  if ( *(_DWORD *)(a1 + 20) )
  {
    LOBYTE(v103) = 1;
    BLFlushBatchOpContextEx(a1, v103, 0);
  }
  if ( (*(_BYTE *)(a1 + 8) & 5) != 5 && (*(_BYTE *)(a1 + 8) & 6) != 6 )
  {
LABEL_182:
    *v102 = v104;
LABEL_102:
    v119 = (__int64 *)(a1 + 80);
    goto LABEL_103;
  }
  v119 = (__int64 *)(a1 + 80);
  (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
  *v102 = v104;
  (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
LABEL_103:
  result = *(unsigned __int8 *)(v100 + 26);
  v120 = v288 - result;
  if ( (*(_BYTE *)(v100 + 27) & 1) == 0 )
  {
    v121 = __ROR2__(v120, 8);
    v122 = a3 + 1;
    if ( a1 )
    {
      v123 = *v119;
      if ( *(_BYTE *)(*v119 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
      {
        v225 = *(unsigned int *)(a1 + 12);
        v226 = 0;
        *(_BYTE *)(a1 + 4) = 1;
        if ( (_DWORD)v225 != -1 )
        {
          v103 = *(_QWORD *)(v123 + 24);
          if ( v103 )
            v226 = v103 + 20 * v225;
        }
        _InterlockedAdd16((volatile signed __int16 *)(v226 + 16), 1u);
        v119 = (__int64 *)(a1 + 80);
      }
      v124 = *(_DWORD *)(*v119 + 4);
      if ( v124 )
      {
        v125 = *(_DWORD **)(a1 + 32);
        v126 = v125[2];
        if ( v126 >= v125[3] )
        {
          v126 = 0;
          if ( *(_DWORD *)(a1 + 16) < v124
            && (v238 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*v119 + 64)), (v125 = v238) != 0) )
          {
            *(_QWORD *)v238 = 0;
            v238[2] = 0;
            v239 = *(_DWORD *)(*v119 + 8);
            *((_QWORD *)v238 + 2) = v238 + 6;
            v238[3] = v239;
            **(_QWORD **)(a1 + 32) = v238;
            v240 = *v119;
            ++*(_DWORD *)(a1 + 16);
            *(_QWORD *)(a1 + 32) = v238;
            if ( *(_BYTE *)(v240 + 1) == 1 )
            {
              v241 = *(unsigned int *)(a1 + 12);
              v242 = 0;
              if ( (_DWORD)v241 != -1 )
              {
                v243 = *(_QWORD *)(v240 + 24);
                if ( v243 )
                  v242 = v243 + 20 * v241;
              }
              _InterlockedAdd16((volatile signed __int16 *)(v242 + 12), 1u);
              v244 = *(unsigned int *)(a1 + 12);
              v245 = 0;
              if ( (_DWORD)v244 != -1 )
              {
                v246 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
                if ( v246 )
                  v245 = (volatile signed __int32 *)(v246 + 20 * v244);
              }
              _InterlockedAdd(v245, 1u);
              v119 = (__int64 *)(a1 + 80);
            }
          }
          else
          {
            LOBYTE(v103) = 1;
            BLFlushBatchOpContextEx(a1, v103, 0);
            v125 = (_DWORD *)(a1 + 56);
          }
        }
        ++*(_DWORD *)(a1 + 20);
        ++v125[2];
        if ( *(_BYTE *)(*v119 + 1) == 1 )
        {
          v127 = *(unsigned int *)(a1 + 12);
          v128 = 0;
          if ( (_DWORD)v127 != -1 )
          {
            v129 = *(_QWORD *)(*v119 + 24);
            if ( v129 )
              v128 = v129 + 20 * v127;
          }
          _InterlockedAdd16((volatile signed __int16 *)(v128 + 14), 1u);
          v130 = *(unsigned int *)(a1 + 12);
          v131 = 0;
          if ( (_DWORD)v130 != -1 )
          {
            v132 = *(_QWORD *)(*v119 + 24);
            if ( v132 )
              v131 = v132 + 20 * v130;
          }
          _InterlockedAdd((volatile signed __int32 *)(v131 + 4), 1u);
          v119 = (__int64 *)(a1 + 80);
        }
        v133 = *((_QWORD *)v125 + 2);
        v134 = 3LL * v126;
        v135 = *(_DWORD *)(v133 + 24LL * v126 + 16);
        v100 = v289;
        *(_QWORD *)(v133 + 8 * v134) = v122;
        *(_DWORD *)(v133 + 8 * v134 + 16) = v135 & 0xFFFFFFF0 | 2;
        *(_WORD *)(v133 + 8 * v134 + 8) = v121;
LABEL_117:
        v136 = v121 + *(unsigned __int16 *)(v100 + 18);
        result = v285;
        v137 = a3 + 5;
        v138 = (unsigned int)v285 + v136;
        v139 = ~((unsigned int)(v138 + __ROR4__(v138, 16)) >> 16);
        if ( !a1 )
          goto LABEL_187;
        v140 = *v119;
        if ( *(_BYTE *)(*v119 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
        {
          v227 = *(unsigned int *)(a1 + 12);
          v228 = 0;
          *(_BYTE *)(a1 + 4) = 1;
          if ( (_DWORD)v227 != -1 )
          {
            v138 = *(_QWORD *)(v140 + 24);
            if ( v138 )
              v228 = v138 + 20 * v227;
          }
          _InterlockedAdd16((volatile signed __int16 *)(v228 + 16), 1u);
          v119 = (__int64 *)(a1 + 80);
        }
        v141 = *(_DWORD *)(*v119 + 4);
        if ( v141 )
        {
          v142 = *(_DWORD **)(a1 + 32);
          v143 = v142[2];
          if ( v143 >= v142[3] )
          {
            v143 = 0;
            if ( *(_DWORD *)(a1 + 16) < v141
              && (v247 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*v119 + 64)), (v142 = v247) != 0) )
            {
              *(_QWORD *)v247 = 0;
              v247[2] = 0;
              v248 = *(_DWORD *)(*v119 + 8);
              *((_QWORD *)v247 + 2) = v247 + 6;
              v247[3] = v248;
              **(_QWORD **)(a1 + 32) = v247;
              v249 = *v119;
              ++*(_DWORD *)(a1 + 16);
              *(_QWORD *)(a1 + 32) = v247;
              if ( *(_BYTE *)(v249 + 1) == 1 )
              {
                v250 = *(unsigned int *)(a1 + 12);
                v251 = 0;
                if ( (_DWORD)v250 != -1 )
                {
                  v252 = *(_QWORD *)(v249 + 24);
                  if ( v252 )
                    v251 = v252 + 20 * v250;
                }
                _InterlockedAdd16((volatile signed __int16 *)(v251 + 12), 1u);
                v253 = *(unsigned int *)(a1 + 12);
                v254 = 0;
                if ( (_DWORD)v253 != -1 )
                {
                  v255 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
                  if ( v255 )
                    v254 = (volatile signed __int32 *)(v255 + 20 * v253);
                }
                _InterlockedAdd(v254, 1u);
                v119 = (__int64 *)(a1 + 80);
              }
            }
            else
            {
              LOBYTE(v138) = 1;
              BLFlushBatchOpContextEx(a1, v138, 0);
              v142 = (_DWORD *)(a1 + 56);
            }
          }
          ++*(_DWORD *)(a1 + 20);
          ++v142[2];
          if ( *(_BYTE *)(*v119 + 1) == 1 )
          {
            v144 = *(unsigned int *)(a1 + 12);
            v145 = 0;
            if ( (_DWORD)v144 != -1 )
            {
              v146 = *(_QWORD *)(*v119 + 24);
              if ( v146 )
                v145 = v146 + 20 * v144;
            }
            _InterlockedAdd16((volatile signed __int16 *)(v145 + 14), 1u);
            v147 = *(unsigned int *)(a1 + 12);
            if ( (_DWORD)v147 != -1 )
            {
              v148 = *(_QWORD *)(*v119 + 24);
              if ( v148 )
                v9 = v148 + 20 * v147;
            }
            _InterlockedAdd((volatile signed __int32 *)(v9 + 4), 1u);
          }
          v149 = *((_QWORD *)v142 + 2);
          v150 = 3LL * v143;
          v151 = *(_DWORD *)(v149 + 24LL * v143 + 16) & 0xFFFFFFF2;
          *(_QWORD *)(v149 + 8 * v150) = v137;
          result = v151 | 2;
          *(_WORD *)(v149 + 8 * v150 + 8) = v139;
          *(_DWORD *)(v149 + 8 * v150 + 16) = result;
          return result;
        }
        if ( *(_DWORD *)(a1 + 20) )
        {
          LOBYTE(v138) = 1;
          BLFlushBatchOpContextEx(a1, v138, 0);
        }
        if ( (*(_BYTE *)(a1 + 8) & 5) != 5 )
        {
          result = *(_DWORD *)(a1 + 8) & 6;
          if ( (*(_BYTE *)(a1 + 8) & 6) != 6 )
          {
LABEL_187:
            *v137 = v139;
            return result;
          }
        }
        (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
        *v137 = v139;
        return (*(__int64 (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
      }
      if ( *(_DWORD *)(a1 + 20) )
      {
        LOBYTE(v103) = 1;
        BLFlushBatchOpContextEx(a1, v103, 0);
      }
      if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (v119 = (__int64 *)(a1 + 80), (*(_BYTE *)(a1 + 8) & 6) == 6) )
      {
        (*(void (**)(void))(*v119 + 32))();
        *v122 = v121;
        (*(void (**)(void))(*v119 + 40))();
        goto LABEL_117;
      }
    }
    *v122 = v121;
    goto LABEL_117;
  }
  v156 = a3 + 2;
  v157 = __ROR2__(v120 - 40, 8);
  if ( !a1 )
  {
LABEL_293:
    *v156 = v157;
    return result;
  }
  v158 = *(_QWORD *)(a1 + 80);
  if ( *(_BYTE *)(v158 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
  {
    v274 = *(unsigned int *)(a1 + 12);
    v275 = 0;
    *(_BYTE *)(a1 + 4) = 1;
    if ( (_DWORD)v274 != -1 )
    {
      v103 = *(_QWORD *)(v158 + 24);
      if ( v103 )
        v275 = v103 + 20 * v274;
    }
    _InterlockedAdd16((volatile signed __int16 *)(v275 + 16), 1u);
  }
  v159 = (__int64 *)(a1 + 80);
  v160 = *(_QWORD *)(a1 + 80);
  v161 = *(_DWORD *)(v160 + 4);
  if ( !v161 )
  {
    if ( *(_DWORD *)(a1 + 20) )
    {
      LOBYTE(v103) = 1;
      BLFlushBatchOpContextEx(a1, v103, 0);
    }
    if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (result = *(_DWORD *)(a1 + 8) & 6, (*(_BYTE *)(a1 + 8) & 6) == 6) )
    {
      (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
      *v156 = v157;
      return (*(__int64 (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
    }
    goto LABEL_293;
  }
  v162 = *(_DWORD **)(a1 + 32);
  v163 = v162[2];
  if ( v163 >= v162[3] )
  {
    v163 = 0;
    if ( *(_DWORD *)(a1 + 16) < v161
      && (v276 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v160 + 64)), (v162 = v276) != 0) )
    {
      *(_QWORD *)v276 = 0;
      v276[2] = 0;
      v277 = *(_DWORD *)(*v159 + 8);
      *((_QWORD *)v276 + 2) = v276 + 6;
      v276[3] = v277;
      **(_QWORD **)(a1 + 32) = v276;
      v278 = *v159;
      ++*(_DWORD *)(a1 + 16);
      *(_QWORD *)(a1 + 32) = v276;
      if ( *(_BYTE *)(v278 + 1) == 1 )
      {
        v279 = *(unsigned int *)(a1 + 12);
        v280 = 0;
        if ( (_DWORD)v279 != -1 )
        {
          v281 = *(_QWORD *)(v278 + 24);
          if ( v281 )
            v280 = v281 + 20 * v279;
        }
        _InterlockedAdd16((volatile signed __int16 *)(v280 + 12), 1u);
        v282 = *(unsigned int *)(a1 + 12);
        v283 = 0;
        if ( (_DWORD)v282 != -1 )
        {
          v284 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
          if ( v284 )
            v283 = (volatile signed __int32 *)(v284 + 20 * v282);
        }
        _InterlockedAdd(v283, 1u);
        v159 = (__int64 *)(a1 + 80);
      }
    }
    else
    {
      LOBYTE(v103) = 1;
      BLFlushBatchOpContextEx(a1, v103, 0);
      v162 = (_DWORD *)(a1 + 56);
    }
  }
  ++*(_DWORD *)(a1 + 20);
  ++v162[2];
  if ( *(_BYTE *)(*v159 + 1) == 1 )
  {
    v164 = *(unsigned int *)(a1 + 12);
    v165 = 0;
    if ( (_DWORD)v164 != -1 )
    {
      v166 = *(_QWORD *)(*v159 + 24);
      if ( v166 )
        v165 = v166 + 20 * v164;
    }
    _InterlockedAdd16((volatile signed __int16 *)(v165 + 14), 1u);
    v167 = *(unsigned int *)(a1 + 12);
    if ( (_DWORD)v167 != -1 )
    {
      v168 = *(_QWORD *)(*v159 + 24);
      if ( v168 )
        v9 = v168 + 20 * v167;
    }
    _InterlockedAdd((volatile signed __int32 *)(v9 + 4), 1u);
  }
  v169 = *((_QWORD *)v162 + 2);
  v170 = 3LL * v163;
  v171 = *(_DWORD *)(v169 + 24LL * v163 + 16) & 0xFFFFFFF2;
  *(_QWORD *)(v169 + 8 * v170) = v156;
  result = v171 | 2;
  *(_WORD *)(v169 + 8 * v170 + 8) = v157;
  *(_DWORD *)(v169 + 8 * v170 + 16) = result;
  return result;
}

```

## disassembly

```asm
0x1400095bc  mov     [rsp+arg_18], r9
0x1400095c1  mov     [rsp+arg_10], r8
0x1400095c6  mov     [rsp+arg_8], rdx
0x1400095cb  push    rbx
0x1400095cc  push    rbp
0x1400095cd  push    rsi
0x1400095ce  push    rdi
0x1400095cf  push    r12
0x1400095d1  push    r13
0x1400095d3  push    r14
0x1400095d5  push    r15
0x1400095d7  sub     rsp, 48h
0x1400095db  movzx   eax, word ptr [rdx+18h]
0x1400095df  lea     r14, [rcx+50h]
0x1400095e3  mov     rbx, rcx
0x1400095e6  mov     dword ptr [rsp+88h+var_68], 0CCCCh
0x1400095ee  mov     ecx, [rsp+88h+arg_20]
0x1400095f5  or      r13d, 0FFFFFFFFh
0x1400095f9  xor     edi, edi
0x1400095fb  mov     r15, r9
0x1400095fe  mov     esi, 1
0x140009603  cmp     ecx, [rdx+8]
0x140009606  jz      loc_1400096E6
0x14000960c  add     ax, [rdx]
0x14000960f  mov     [rsp+88h+arg_0], ax
0x140009617  test    rbx, rbx
0x14000961a  jz      loc_1400098E0
0x140009620  mov     rcx, [r14]
0x140009623  cmp     [rcx+1], sil
0x140009627  jz      loc_140009ED6
0x14000962d  lea     r14, [rbx+50h]
0x140009631  mov     rcx, [r14]
0x140009634  mov     eax, [rcx+4]
0x140009637  test    eax, eax
0x140009639  jz      loc_1400098B1
0x14000963f  lea     r12, [rbx+20h]
0x140009643  mov     r8, [r12]
0x140009647  mov     [rsp+88h+var_60], r12
0x14000964c  mov     r15d, [r8+8]
0x140009650  cmp     r15d, [r8+0Ch]
0x140009654  jnb     loc_14000A3F7
0x14000965a  lea     rbp, [rbx+14h]
0x14000965e  add     [rbp+0], esi
0x140009661  add     [r8+8], esi
0x140009665  mov     rcx, [r14]
0x140009668  cmp     [rcx+1], sil
0x14000966c  jnz     short loc_1400096B4
0x14000966e  mov     r9d, [rbx+0Ch]
0x140009672  mov     rax, rdi
0x140009675  cmp     r9d, r13d
0x140009678  jz      short loc_14000968B
0x14000967a  mov     rdx, [rcx+18h]
0x14000967e  test    rdx, rdx
0x140009681  jz      short loc_14000968B
0x140009683  lea     rcx, [r9+r9*4]
0x140009687  lea     rax, [rdx+rcx*4]
0x14000968b  lock add [rax+0Eh], si
0x140009690  mov     r9d, [rbx+0Ch]
0x140009694  mov     rcx, rdi
0x140009697  cmp     r9d, r13d
0x14000969a  jz      short loc_1400096B0
0x14000969c  mov     rax, [r14]
0x14000969f  mov     rdx, [rax+18h]
0x1400096a3  test    rdx, rdx
0x1400096a6  jz      short loc_1400096B0
0x1400096a8  lea     rcx, [r9+r9*4]
0x1400096ac  lea     rcx, [rdx+rcx*4]
0x1400096b0  lock add [rcx+4], esi
0x1400096b4  mov     rcx, [r8+10h]
0x1400096b8  mov     eax, r15d
0x1400096bb  lea     rdx, [rax+rax*2]
0x1400096bf  mov     eax, [rcx+rdx*8+10h]
0x1400096c3  mov     r15, [rsp+88h+arg_18]
0x1400096cb  and     eax, 0FFFFFFF5h
0x1400096ce  or      eax, 5
0x1400096d1  mov     [rcx+rdx*8], r15
0x1400096d5  mov     [rcx+rdx*8+10h], eax
0x1400096d9  mov     dword ptr [rcx+rdx*8+8], 68h ; 'h'
0x1400096e1  jmp     loc_140009903
0x1400096e6  movzx   ecx, word ptr [rdx+4]
0x1400096ea  sub     cx, word ptr [rsp+88h+arg_28]
0x1400096f2  mov     r12b, [rdx+1Bh]
0x1400096f6  add     cx, ax
0x1400096f9  and     r12b, 2
0x1400096fd  mov     [rsp+88h+arg_0], cx
0x140009705  test    rbx, rbx
0x140009708  jz      loc_14000A031
0x14000970e  mov     rcx, [r14]
0x140009711  cmp     [rcx+1], sil
0x140009715  jz      loc_14000A1B5
0x14000971b  lea     r14, [rbx+50h]
0x14000971f  mov     rcx, [r14]
0x140009722  mov     eax, [rcx+4]
0x140009725  test    eax, eax
0x140009727  jz      loc_14000A002
0x14000972d  lea     r10, [rbx+20h]
0x140009731  mov     rdx, [r10]
0x140009734  mov     [rsp+88h+var_60], r10
0x140009739  mov     r15d, [rdx+8]
0x14000973d  cmp     r15d, [rdx+0Ch]
0x140009741  jnb     loc_14000A8B9
0x140009747  lea     rbp, [rbx+14h]
0x14000974b  add     [rbp+0], esi
0x14000974e  add     [rdx+8], esi
0x140009751  mov     rcx, [r14]
0x140009754  cmp     [rcx+1], sil
0x140009758  jnz     short loc_1400097A0
0x14000975a  mov     r9d, [rbx+0Ch]
0x14000975e  mov     rax, rdi
0x140009761  cmp     r9d, r13d
0x140009764  jz      short loc_140009777
0x140009766  mov     r8, [rcx+18h]
0x14000976a  test    r8, r8
0x14000976d  jz      short loc_140009777
0x14000976f  lea     rcx, [r9+r9*4]
0x140009773  lea     rax, [r8+rcx*4]
0x140009777  lock add [rax+0Eh], si
0x14000977c  mov     r9d, [rbx+0Ch]
0x140009780  mov     rcx, rdi
0x140009783  cmp     r9d, r13d
0x140009786  jz      short loc_14000979C
0x140009788  mov     rax, [r14]
0x14000978b  mov     r8, [rax+18h]
0x14000978f  test    r8, r8
0x140009792  jz      short loc_14000979C
0x140009794  lea     rcx, [r9+r9*4]
0x140009798  lea     rcx, [r8+rcx*4]
0x14000979c  lock add [rcx+4], esi
0x1400097a0  mov     rdx, [rdx+10h]
0x1400097a4  mov     eax, r15d
0x1400097a7  lea     r8, [rax+rax*2]
0x1400097ab  mov     eax, [rdx+r8*8+10h]
0x1400097b0  neg     r12b
0x1400097b3  mov     r12, [rsp+88h+arg_18]
0x1400097bb  sbb     ecx, ecx
0x1400097bd  mov     [rdx+r8*8], r12
0x1400097c1  add     ecx, 5
0x1400097c4  mov     dword ptr [rdx+r8*8+8], 68h ; 'h'
0x1400097cd  and     eax, 0FFFFFFF0h
0x1400097d0  or      ecx, eax
0x1400097d2  mov     [rdx+r8*8+10h], ecx
0x1400097d7  mov     r15, [rsp+88h+arg_8]
0x1400097df  mov     r15b, [r15+1Bh]
0x1400097e3  and     r15b, 4
0x1400097e7  test    rbx, rbx
0x1400097ea  jz      loc_14000A07B
0x1400097f0  mov     rcx, [r14]
0x1400097f3  cmp     [rcx+1], sil
0x1400097f7  jz      loc_14000A1EA
0x1400097fd  mov     rcx, [r14]
0x140009800  mov     eax, [rcx+4]
0x140009803  test    eax, eax
0x140009805  jz      loc_14000A04C
0x14000980b  mov     rdx, [r10]
0x14000980e  mov     r12d, [rdx+8]
0x140009812  cmp     r12d, [rdx+0Ch]
0x140009816  jnb     loc_14000A95E
0x14000981c  add     [rbp+0], esi
0x14000981f  add     [rdx+8], esi
0x140009822  mov     rcx, [r14]
0x140009825  cmp     [rcx+1], sil
0x140009829  jnz     short loc_140009871
0x14000982b  mov     r9d, [rbx+0Ch]
0x14000982f  mov     rax, rdi
0x140009832  cmp     r9d, r13d
0x140009835  jz      short loc_140009848
0x140009837  mov     r8, [rcx+18h]
0x14000983b  test    r8, r8
0x14000983e  jz      short loc_140009848
0x140009840  lea     rcx, [r9+r9*4]
0x140009844  lea     rax, [r8+rcx*4]
0x140009848  lock add [rax+0Eh], si
0x14000984d  mov     r9d, [rbx+0Ch]
0x140009851  mov     rcx, rdi
0x140009854  cmp     r9d, r13d
0x140009857  jz      short loc_14000986D
0x140009859  mov     rax, [r14]
0x14000985c  mov     r8, [rax+18h]
0x140009860  test    r8, r8
0x140009863  jz      short loc_14000986D
0x140009865  lea     rcx, [r9+r9*4]
0x140009869  lea     rcx, [r8+rcx*4]
0x14000986d  lock add [rcx+4], esi
0x140009871  mov     rdx, [rdx+10h]
0x140009875  mov     eax, r12d
0x140009878  lea     r8, [rax+rax*2]
0x14000987c  mov     eax, [rdx+r8*8+10h]
0x140009881  neg     r15b
0x140009884  mov     r11, [rsp+88h+arg_18]
0x14000988c  sbb     ecx, ecx
0x14000988e  mov     [rdx+r8*8], r11
0x140009892  add     ecx, 5
0x140009895  mov     dword ptr [rdx+r8*8+8], 6Bh ; 'k'
0x14000989e  and     eax, 0FFFFFFF0h
0x1400098a1  or      ecx, eax
0x1400098a3  mov     [rdx+r8*8+10h], ecx
0x1400098a8  lea     r12, [rbx+20h]
0x1400098ac  jmp     loc_1400099B3
0x1400098b1  cmp     [rbx+14h], edi
0x1400098b4  jz      short loc_1400098C4
0x1400098b6  xor     r8d, r8d
0x1400098b9  mov     dl, sil
0x1400098bc  mov     rcx, rbx
0x1400098bf  call    BLFlushBatchOpContextEx
0x1400098c4  mov     eax, [rbx+8]
0x1400098c7  and     eax, 5
0x1400098ca  cmp     al, 5
0x1400098cc  jz      loc_14000AB90
0x1400098d2  mov     eax, [rbx+8]
0x1400098d5  and     eax, 6
0x1400098d8  cmp     al, 6
0x1400098da  jz      loc_14000AB90
0x1400098e0  movzx   eax, byte ptr [r15+0Dh]
0x1400098e5  btr     eax, 0
0x1400098e9  mov     [r15+0Dh], al
0x1400098ed  lea     r12, [rbx+20h]
0x1400098f1  mov     [rsp+88h+var_60], r12
0x1400098f6  lea     rbp, [rbx+14h]
0x1400098fa  test    rbx, rbx
0x1400098fd  jz      loc_140009E76
0x140009903  mov     rcx, [r14]
0x140009906  cmp     [rcx+1], sil
0x14000990a  jz      loc_140009F0B
0x140009910  mov     rcx, [r14]
0x140009913  mov     eax, [rcx+4]
0x140009916  test    eax, eax
0x140009918  jz      loc_140009E47
0x14000991e  mov     r8, [r12]
0x140009922  mov     r15d, [r8+8]
0x140009926  cmp     r15d, [r8+0Ch]
0x14000992a  jnb     loc_14000A49B
0x140009930  add     [rbp+0], esi
0x140009933  add     [r8+8], esi
0x140009937  mov     rcx, [r14]
0x14000993a  cmp     [rcx+1], sil
0x14000993e  jnz     short loc_140009986
0x140009940  mov     r9d, [rbx+0Ch]
0x140009944  mov     rax, rdi
0x140009947  cmp     r9d, r13d
0x14000994a  jz      short loc_14000995D
0x14000994c  mov     rdx, [rcx+18h]
0x140009950  test    rdx, rdx
0x140009953  jz      short loc_14000995D
0x140009955  lea     rcx, [r9+r9*4]
0x140009959  lea     rax, [rdx+rcx*4]
0x14000995d  lock add [rax+0Eh], si
0x140009962  mov     r9d, [rbx+0Ch]
0x140009966  mov     rcx, rdi
0x140009969  cmp     r9d, r13d
0x14000996c  jz      short loc_140009982
0x14000996e  mov     rax, [r14]
0x140009971  mov     rdx, [rax+18h]
0x140009975  test    rdx, rdx
0x140009978  jz      short loc_140009982
0x14000997a  lea     rcx, [r9+r9*4]
0x14000997e  lea     rcx, [rdx+rcx*4]
0x140009982  lock add [rcx+4], esi
0x140009986  mov     rcx, [r8+10h]
0x14000998a  mov     eax, r15d
0x14000998d  lea     rdx, [rax+rax*2]
0x140009991  mov     eax, [rcx+rdx*8+10h]
0x140009995  mov     r11, [rsp+88h+arg_18]
0x14000999d  and     eax, 0FFFFFFF5h
0x1400099a0  or      eax, 5
0x1400099a3  mov     [rcx+rdx*8], r11
0x1400099a7  mov     [rcx+rdx*8+10h], eax
0x1400099ab  mov     dword ptr [rcx+rdx*8+8], 6Bh ; 'k'
0x1400099b3  mov     rax, [rsp+88h+arg_8]
0x1400099bb  add     r11, 4
0x1400099bf  mov     r15d, [rsp+88h+arg_28]
0x1400099c7  mov     [rsp+88h+var_58], r11
0x1400099cc  add     r15d, [rax+0Ch]
0x1400099d0  bswap   r15d
0x1400099d3  test    rbx, rbx
0x1400099d6  jz      loc_14000A173
0x1400099dc  mov     rcx, [r14]
0x1400099df  cmp     [rcx+1], sil
0x1400099e3  jz      loc_14000A10A
0x1400099e9  mov     rcx, [r14]
0x1400099ec  mov     eax, [rcx+4]
0x1400099ef  test    eax, eax
0x1400099f1  jz      loc_14000A13F
0x1400099f7  mov     r8, [r12]
0x1400099fb  mov     r12d, [r8+8]
0x1400099ff  cmp     r12d, [r8+0Ch]
0x140009a03  jnb     loc_14000A21F
0x140009a09  mov     r10, [rsp+88h+var_60]
0x140009a0e  add     [rbp+0], esi
0x140009a11  add     [r8+8], esi
0x140009a15  mov     rcx, [r14]
0x140009a18  cmp     [rcx+1], sil
0x140009a1c  jnz     short loc_140009A64
0x140009a1e  mov     r9d, [rbx+0Ch]
0x140009a22  mov     rax, rdi
0x140009a25  cmp     r9d, r13d
0x140009a28  jz      short loc_140009A3B
0x140009a2a  mov     rdx, [rcx+18h]
0x140009a2e  test    rdx, rdx
0x140009a31  jz      short loc_140009A3B
0x140009a33  lea     rcx, [r9+r9*4]
  ... truncated ...
```
