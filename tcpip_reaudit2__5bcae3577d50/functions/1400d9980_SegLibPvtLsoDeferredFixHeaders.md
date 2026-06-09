# SegLibPvtLsoDeferredFixHeaders

- ea: `0x1400d9980`
- end: `0x1400da9ed`
- name: `SegLibPvtLsoDeferredFixHeaders`
- size: `4205`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400d8ce4`

## callees

- `0x1400d9980`
- `0x1400daa00`
- `0x1401bf700`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401cda0c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401cdadd`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401cdbac`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401cdc7c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401cdd4c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401cde1f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401cdef2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401cdfc7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401ce09c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401ce179`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401cda0c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401cdadd`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401cdbac`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401cdc7c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401cdd4c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401cde1f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401cdef2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401cdfc7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401ce09c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401ce179`

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
  __int64 v18; // rcx
  int v19; // eax
  char v20; // r12
  __int64 v21; // rcx
  __int64 v22; // rcx
  unsigned int v23; // eax
  __int64 v24; // r10
  _DWORD *v25; // rdx
  unsigned int v26; // r15d
  __int64 v27; // r8
  int v28; // eax
  bool v29; // cf
  __int64 v30; // r12
  char v31; // r15
  __int64 v32; // rcx
  __int64 v33; // rcx
  unsigned int v34; // eax
  _DWORD *v35; // rdx
  unsigned int v36; // r12d
  __int64 v37; // r8
  int v38; // eax
  __int64 v39; // r11
  __int64 v40; // rcx
  __int64 v41; // rcx
  unsigned int v42; // eax
  _QWORD *v43; // r8
  unsigned int v44; // r15d
  __int64 v45; // rcx
  unsigned int v46; // eax
  __int64 result; // rax
  unsigned __int32 *v48; // r11
  unsigned __int32 v49; // r15d
  __int64 v50; // rcx
  __int64 v51; // rcx
  unsigned int v52; // eax
  _QWORD *v53; // r8
  unsigned int v54; // r12d
  _QWORD **v55; // r10
  __int64 v56; // rcx
  unsigned int v57; // eax
  unsigned int v58; // r11d
  _WORD *v59; // r12
  __int64 v60; // rcx
  __int64 v61; // rcx
  unsigned int v62; // eax
  _DWORD *v63; // r8
  unsigned int v64; // r15d
  __int64 v65; // rcx
  __int64 v66; // rdx
  unsigned int v67; // eax
  __int64 v68; // rbp
  unsigned __int16 v69; // ax
  _WORD *v70; // r12
  __int64 v71; // rdx
  unsigned int v72; // r15d
  __int64 v73; // rcx
  __int64 *v74; // r14
  __int64 v75; // rcx
  unsigned int v76; // eax
  _DWORD *v77; // r8
  unsigned int v78; // ebp
  __int64 v79; // rcx
  int v80; // eax
  __int64 *v81; // r14
  __int16 v82; // r12
  unsigned __int16 v83; // r12
  unsigned __int16 *v84; // r15
  __int64 v85; // rcx
  unsigned int v86; // eax
  _DWORD *v87; // r8
  unsigned int v88; // ebp
  __int64 v89; // rcx
  __int64 v90; // rdx
  int v91; // eax
  int v92; // edx
  _WORD *v93; // r12
  __int64 v94; // rdx
  unsigned int v95; // ebp
  __int64 v96; // rcx
  unsigned int v97; // eax
  _DWORD *v98; // r8
  unsigned int v99; // r15d
  __int64 v100; // rcx
  __int64 v101; // rdx
  unsigned int v102; // eax
  _WORD *v103; // r15
  __int16 v104; // r12
  __int64 v105; // rcx
  __int64 *v106; // r14
  __int64 v107; // rcx
  unsigned int v108; // eax
  _DWORD *v109; // r8
  unsigned int v110; // ebp
  __int64 v111; // rcx
  __int64 v112; // rdx
  unsigned int v113; // eax
  char v114; // al
  char v115; // al
  char v116; // al
  char v117; // al
  char v118; // al
  char v119; // al
  __int64 v120; // rcx
  char v121; // al
  __int64 v122; // rcx
  char v123; // al
  __int64 v124; // r8
  __int64 v125; // rax
  __int64 v126; // r9
  __int64 v127; // rax
  __int64 v128; // r8
  __int64 v129; // r8
  __int64 v130; // rax
  __int64 v131; // r9
  __int64 v132; // rax
  __int64 v133; // r8
  __int64 v134; // r8
  __int64 v135; // rax
  __int64 v136; // rcx
  __int64 v137; // r9
  __int64 v138; // rax
  __int64 v139; // rdx
  __int64 v140; // r8
  __int64 v141; // rax
  __int64 v142; // rcx
  __int64 v143; // r9
  __int64 v144; // rax
  __int64 v145; // rdx
  __int64 v146; // r8
  __int64 v147; // rax
  __int64 v148; // rcx
  __int64 v149; // r9
  __int64 v150; // rax
  __int64 v151; // rdx
  __int64 v152; // r8
  __int64 v153; // rax
  __int64 v154; // r9
  __int64 v155; // rax
  __int64 v156; // rdx
  __int64 v157; // r8
  __int64 v158; // rax
  __int64 v159; // r9
  __int64 v160; // rax
  __int64 v161; // rdx
  __int64 v162; // r8
  __int64 v163; // rax
  __int64 v164; // r9
  __int64 v165; // rax
  __int64 v166; // rdx
  __int64 v167; // r8
  __int64 v168; // rax
  __int64 v169; // r9
  __int64 v170; // rax
  __int64 v171; // rdx
  __int64 v172; // r8
  __int64 v173; // rax
  __int64 v174; // r9
  __int64 v175; // rax
  __int64 v176; // rdx
  _DWORD *v177; // rax
  int v178; // ecx
  __int64 v179; // r8
  __int64 v180; // rcx
  __int64 v181; // rax
  __int64 v182; // r8
  __int64 v183; // r9
  volatile signed __int32 *v184; // rcx
  __int64 v185; // r8
  __int64 v186; // r9
  __int64 v187; // rcx
  __int64 v188; // r8
  _DWORD *v189; // rax
  int v190; // ecx
  __int64 v191; // r8
  __int64 v192; // rcx
  __int64 v193; // rax
  __int64 v194; // r8
  __int64 v195; // r9
  volatile signed __int32 *v196; // rcx
  __int64 v197; // r8
  __int64 v198; // r9
  __int64 v199; // rcx
  __int64 v200; // r8
  _DWORD *v201; // rax
  int v202; // ecx
  __int64 v203; // rdx
  __int64 v204; // rcx
  __int64 v205; // rax
  __int64 v206; // rdx
  __int64 v207; // r9
  volatile signed __int32 *v208; // rcx
  __int64 v209; // rdx
  __int64 v210; // r9
  __int64 v211; // rcx
  __int64 v212; // rdx
  _DWORD *v213; // rax
  int v214; // ecx
  __int64 v215; // rdx
  __int64 v216; // rcx
  __int64 v217; // rax
  __int64 v218; // rdx
  __int64 v219; // r9
  volatile signed __int32 *v220; // rcx
  __int64 v221; // rdx
  __int64 v222; // r9
  __int64 v223; // rcx
  __int64 v224; // rdx
  _DWORD *v225; // rax
  int v226; // ecx
  __int64 v227; // rdx
  __int64 v228; // rcx
  __int64 v229; // rax
  __int64 v230; // rdx
  __int64 v231; // r9
  volatile signed __int32 *v232; // rcx
  __int64 v233; // rdx
  __int64 v234; // r9
  __int64 v235; // rcx
  __int64 v236; // rdx
  _DWORD *v237; // rax
  __int64 v238; // rdx
  __int64 v239; // rcx
  __int64 v240; // rax
  __int64 v241; // rdx
  __int64 v242; // r9
  volatile signed __int32 *v243; // rcx
  __int64 v244; // rdx
  __int64 v245; // r9
  __int64 v246; // rcx
  __int64 v247; // rdx
  _DWORD *v248; // rax
  int v249; // ecx
  __int64 v250; // rdx
  __int64 v251; // rcx
  __int64 v252; // rax
  __int64 v253; // rdx
  __int64 v254; // r9
  volatile signed __int32 *v255; // rcx
  __int64 v256; // rdx
  __int64 v257; // r9
  __int64 v258; // rcx
  __int64 v259; // rdx
  _DWORD *v260; // rax
  int v261; // ecx
  __int64 v262; // rdx
  __int64 v263; // rcx
  __int64 v264; // rax
  __int64 v265; // rdx
  __int64 v266; // r9
  volatile signed __int32 *v267; // rcx
  __int64 v268; // rdx
  __int64 v269; // rcx
  __int64 v270; // rdx
  _DWORD *v271; // rax
  int v272; // ecx
  __int64 v273; // rdx
  __int64 v274; // rcx
  __int64 v275; // rax
  __int64 v276; // rdx
  __int64 v277; // r9
  volatile signed __int32 *v278; // rcx
  __int64 v279; // rdx
  __int64 v280; // r9
  __int64 v281; // rcx
  __int64 v282; // rdx
  _DWORD *v283; // rax
  int v284; // ecx
  __int64 v285; // rdx
  __int64 v286; // rcx
  __int64 v287; // rax
  __int64 v288; // rdx
  __int64 v289; // r9
  volatile signed __int32 *v290; // rcx
  __int64 v291; // rdx
  __int64 v292; // rcx
  __int64 v293; // rdx
  unsigned __int16 v294; // [rsp+20h] [rbp-68h]
  _QWORD **v295; // [rsp+28h] [rbp-60h]
  unsigned __int32 *v296; // [rsp+30h] [rbp-58h]
  __int16 v297; // [rsp+90h] [rbp+8h]
  __int64 v298; // [rsp+98h] [rbp+10h]
  unsigned int v301; // [rsp+B0h] [rbp+28h]

  v298 = a2;
  v6 = *(_WORD *)(a2 + 24);
  v7 = (__int64 *)(a1 + 80);
  v294 = -13108;
  v9 = 0;
  v10 = a4;
  if ( a5 == *(_DWORD *)(a2 + 8) )
  {
    v20 = *(_BYTE *)(a2 + 27) & 2;
    v297 = v6 + *(_WORD *)(a2 + 4) - a6;
    if ( !a1 )
      goto LABEL_126;
    v21 = *v7;
    if ( *(_BYTE *)(*v7 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
    {
      v124 = *(unsigned int *)(a1 + 12);
      v125 = 0;
      *(_BYTE *)(a1 + 4) = 1;
      if ( (_DWORD)v124 != -1 )
      {
        a2 = *(_QWORD *)(v21 + 24);
        if ( a2 )
          v125 = a2 + 20 * v124;
      }
      _InterlockedAdd16((volatile signed __int16 *)(v125 + 16), 1u);
    }
    v7 = (__int64 *)(a1 + 80);
    v22 = *(_QWORD *)(a1 + 80);
    v23 = *(_DWORD *)(v22 + 4);
    if ( v23 )
    {
      v24 = a1 + 32;
      v25 = *(_DWORD **)(a1 + 32);
      v295 = (_QWORD **)(a1 + 32);
      v26 = v25[2];
      if ( v26 >= v25[3] )
      {
        v26 = 0;
        if ( *(_DWORD *)(a1 + 16) < v23
          && (v177 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v22 + 64)), (v25 = v177) != 0) )
        {
          *(_QWORD *)v177 = 0;
          v24 = a1 + 32;
          v177[2] = 0;
          v178 = *(_DWORD *)(*v7 + 8);
          *((_QWORD *)v177 + 2) = v177 + 6;
          v177[3] = v178;
          **(_QWORD **)(a1 + 32) = v177;
          v179 = *v7;
          ++*(_DWORD *)(a1 + 16);
          *(_QWORD *)(a1 + 32) = v177;
          if ( *(_BYTE *)(v179 + 1) == 1 )
          {
            v180 = *(unsigned int *)(a1 + 12);
            v181 = 0;
            if ( (_DWORD)v180 != -1 )
            {
              v182 = *(_QWORD *)(v179 + 24);
              if ( v182 )
                v181 = v182 + 20 * v180;
            }
            _InterlockedAdd16((volatile signed __int16 *)(v181 + 12), 1u);
            v183 = *(unsigned int *)(a1 + 12);
            v184 = 0;
            if ( (_DWORD)v183 != -1 )
            {
              v185 = *(_QWORD *)(*v7 + 24);
              if ( v185 )
                v184 = (volatile signed __int32 *)(v185 + 20 * v183);
            }
            _InterlockedAdd(v184, 1u);
          }
        }
        else
        {
          LOBYTE(v25) = 1;
          BLFlushBatchOpContextEx(a1, v25, 0);
          v25 = (_DWORD *)(a1 + 56);
          v24 = a1 + 32;
        }
      }
      v17 = (_DWORD *)(a1 + 20);
      ++*(_DWORD *)(a1 + 20);
      ++v25[2];
      if ( *(_BYTE *)(*v7 + 1) == 1 )
      {
        v126 = *(unsigned int *)(a1 + 12);
        v127 = 0;
        if ( (_DWORD)v126 != -1 )
        {
          v128 = *(_QWORD *)(*v7 + 24);
          if ( v128 )
            v127 = v128 + 20 * v126;
        }
        _InterlockedAdd16((volatile signed __int16 *)(v127 + 14), 1u);
        v186 = *(unsigned int *)(a1 + 12);
        v187 = 0;
        if ( (_DWORD)v186 != -1 )
        {
          v188 = *(_QWORD *)(*v7 + 24);
          if ( v188 )
            v187 = v188 + 20 * v186;
        }
        _InterlockedAdd((volatile signed __int32 *)(v187 + 4), 1u);
      }
      a2 = *((_QWORD *)v25 + 2);
      v27 = 3LL * v26;
      v28 = *(_DWORD *)(a2 + 24LL * v26 + 16);
      v29 = v20 != 0;
      v30 = a4;
      *(_QWORD *)(a2 + 8 * v27) = a4;
      *(_DWORD *)(a2 + 8 * v27 + 8) = 104;
      *(_DWORD *)(a2 + 8 * v27 + 16) = v28 & 0xFFFFFFF0 | (5 - v29);
      goto LABEL_16;
    }
    if ( *(_DWORD *)(a1 + 20) )
    {
      LOBYTE(a2) = 1;
      BLFlushBatchOpContextEx(a1, a2, 0);
    }
    if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (*(_BYTE *)(a1 + 8) & 6) == 6 )
    {
      (*(void (__fastcall **)(__int64))(*v7 + 32))(v22);
      v121 = *(_BYTE *)(v10 + 13);
      if ( v20 )
        v118 = v121 | 1;
      else
        v118 = v121 & 0xFE;
      *(_BYTE *)(v10 + 13) = v118;
      (*(void (__fastcall **)(__int64))(*v7 + 40))(v120);
    }
    else
    {
LABEL_126:
      v114 = *(_BYTE *)(v10 + 13);
      if ( v20 )
        v115 = v114 | 1;
      else
        v115 = v114 & 0xFE;
      *(_BYTE *)(v10 + 13) = v115;
    }
    v30 = a4;
    v24 = a1 + 32;
    v295 = (_QWORD **)(a1 + 32);
    v17 = (_DWORD *)(a1 + 20);
LABEL_16:
    v31 = *(_BYTE *)(v298 + 27) & 4;
    if ( !a1 )
      goto LABEL_132;
    v32 = *v7;
    if ( *(_BYTE *)(*v7 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
    {
      v129 = *(unsigned int *)(a1 + 12);
      v130 = 0;
      *(_BYTE *)(a1 + 4) = 1;
      if ( (_DWORD)v129 != -1 )
      {
        a2 = *(_QWORD *)(v32 + 24);
        if ( a2 )
          v130 = a2 + 20 * v129;
      }
      _InterlockedAdd16((volatile signed __int16 *)(v130 + 16), 1u);
    }
    v33 = *v7;
    v34 = *(_DWORD *)(*v7 + 4);
    if ( v34 )
    {
      v35 = *(_DWORD **)v24;
      v36 = *(_DWORD *)(*(_QWORD *)v24 + 8LL);
      if ( v36 >= *(_DWORD *)(*(_QWORD *)v24 + 12LL) )
      {
        v36 = 0;
        if ( *(_DWORD *)(a1 + 16) < v34
          && (v189 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v33 + 64)), (v35 = v189) != 0) )
        {
          *(_QWORD *)v189 = 0;
          v189[2] = 0;
          v190 = *(_DWORD *)(*v7 + 8);
          *((_QWORD *)v189 + 2) = v189 + 6;
          v189[3] = v190;
          **(_QWORD **)(a1 + 32) = v189;
          v191 = *v7;
          ++*(_DWORD *)(a1 + 16);
          *(_QWORD *)(a1 + 32) = v189;
          if ( *(_BYTE *)(v191 + 1) == 1 )
          {
            v192 = *(unsigned int *)(a1 + 12);
            v193 = 0;
            if ( (_DWORD)v192 != -1 )
            {
              v194 = *(_QWORD *)(v191 + 24);
              if ( v194 )
                v193 = v194 + 20 * v192;
            }
            _InterlockedAdd16((volatile signed __int16 *)(v193 + 12), 1u);
            v195 = *(unsigned int *)(a1 + 12);
            v196 = 0;
            if ( (_DWORD)v195 != -1 )
            {
              v197 = *(_QWORD *)(*v7 + 24);
              if ( v197 )
                v196 = (volatile signed __int32 *)(v197 + 20 * v195);
            }
            _InterlockedAdd(v196, 1u);
          }
        }
        else
        {
          LOBYTE(v35) = 1;
          BLFlushBatchOpContextEx(a1, v35, 0);
          v35 = (_DWORD *)(a1 + 56);
        }
      }
      ++*v17;
      ++v35[2];
      if ( *(_BYTE *)(*v7 + 1) == 1 )
      {
        v131 = *(unsigned int *)(a1 + 12);
        v132 = 0;
        if ( (_DWORD)v131 != -1 )
        {
          v133 = *(_QWORD *)(*v7 + 24);
          if ( v133 )
            v132 = v133 + 20 * v131;
        }
        _InterlockedAdd16((volatile signed __int16 *)(v132 + 14), 1u);
        v198 = *(unsigned int *)(a1 + 12);
        v199 = 0;
        if ( (_DWORD)v198 != -1 )
        {
          v200 = *(_QWORD *)(*v7 + 24);
          if ( v200 )
            v199 = v200 + 20 * v198;
        }
        _InterlockedAdd((volatile signed __int32 *)(v199 + 4), 1u);
      }
      a2 = *((_QWORD *)v35 + 2);
      v37 = 3LL * v36;
      v38 = *(_DWORD *)(a2 + 24LL * v36 + 16);
      v39 = a4;
      *(_QWORD *)(a2 + 8 * v37) = a4;
      *(_DWORD *)(a2 + 8 * v37 + 8) = 107;
      *(_DWORD *)(a2 + 8 * v37 + 16) = v38 & 0xFFFFFFF0 | (5 - (v31 != 0));
      goto LABEL_22;
    }
    if ( *v17 )
    {
      LOBYTE(a2) = 1;
      BLFlushBatchOpContextEx(a1, a2, 0);
    }
    if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (*(_BYTE *)(a1 + 8) & 6) == 6 )
    {
      (*(void (__fastcall **)(__int64))(*v7 + 32))(v33);
      v123 = *(_BYTE *)(v30 + 13);
      if ( v31 )
        v119 = v123 | 8;
      else
        v119 = v123 & 0xF7;
      *(_BYTE *)(v30 + 13) = v119;
      (*(void (__fastcall **)(__int64))(*v7 + 40))(v122);
    }
    else
    {
LABEL_132:
      v116 = *(_BYTE *)(v30 + 13);
      if ( v31 )
        v117 = v116 | 8;
      else
        v117 = v116 & 0xF7;
      *(_BYTE *)(v30 + 13) = v117;
    }
    v39 = a4;
LABEL_22:
    v14 = (_QWORD **)(a1 + 32);
    goto LABEL_34;
  }
  v297 = *(_WORD *)a2 + v6;
  if ( !a1 )
    goto LABEL_27;
  v11 = *v7;
  if ( *(_BYTE *)(*v7 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
  {
    v134 = *(unsigned int *)(a1 + 12);
    v135 = 0;
    *(_BYTE *)(a1 + 4) = 1;
    if ( (_DWORD)v134 != -1 )
    {
      a2 = *(_QWORD *)(v11 + 24);
      if ( a2 )
        v135 = a2 + 20 * v134;
    }
    _InterlockedAdd16((volatile signed __int16 *)(v135 + 16), 1u);
  }
  v7 = (__int64 *)(a1 + 80);
  v12 = *(_QWORD *)(a1 + 80);
  v13 = *(_DWORD *)(v12 + 4);
  if ( v13 )
  {
    v14 = (_QWORD **)(a1 + 32);
    v15 = *(_DWORD **)(a1 + 32);
    v295 = (_QWORD **)(a1 + 32);
    v16 = v15[2];
    if ( v16 >= v15[3] )
    {
      v16 = 0;
      if ( *(_DWORD *)(a1 + 16) < v13
        && (v201 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v12 + 64)), (v15 = v201) != 0) )
      {
        *(_QWORD *)v201 = 0;
        v201[2] = 0;
        v202 = *(_DWORD *)(*v7 + 8);
        *((_QWORD *)v201 + 2) = v201 + 6;
        v201[3] = v202;
        **v14 = v201;
        v203 = *v7;
        ++*(_DWORD *)(a1 + 16);
        *v14 = v201;
        if ( *(_BYTE *)(v203 + 1) == 1 )
        {
          v204 = *(unsigned int *)(a1 + 12);
          v205 = 0;
          if ( (_DWORD)v204 != -1 )
          {
            v206 = *(_QWORD *)(v203 + 24);
            if ( v206 )
              v205 = v206 + 20 * v204;
          }
          _InterlockedAdd16((volatile signed __int16 *)(v205 + 12), 1u);
          v207 = *(unsigned int *)(a1 + 12);
          v208 = 0;
          if ( (_DWORD)v207 != -1 )
          {
            v209 = *(_QWORD *)(*v7 + 24);
            if ( v209 )
              v208 = (volatile signed __int32 *)(v209 + 20 * v207);
          }
          _InterlockedAdd(v208, 1u);
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
      v137 = *(unsigned int *)(a1 + 12);
      v138 = 0;
      if ( (_DWORD)v137 != -1 )
      {
        v139 = *(_QWORD *)(*v7 + 24);
        if ( v139 )
          v138 = v139 + 20 * v137;
      }
      _InterlockedAdd16((volatile signed __int16 *)(v138 + 14), 1u);
      v210 = *(unsigned int *)(a1 + 12);
      v211 = 0;
      if ( (_DWORD)v210 != -1 )
      {
        v212 = *(_QWORD *)(*v7 + 24);
        if ( v212 )
          v211 = v212 + 20 * v210;
      }
      _InterlockedAdd((volatile signed __int32 *)(v211 + 4), 1u);
    }
    v18 = *((_QWORD *)v15 + 2);
    a2 = 3LL * v16;
    v19 = *(_DWORD *)(v18 + 24LL * v16 + 16);
    v10 = a4;
    *(_QWORD *)(v18 + 8 * a2) = a4;
    *(_DWORD *)(v18 + 8 * a2 + 16) = v19 & 0xFFFFFFF0 | 5;
    *(_DWORD *)(v18 + 8 * a2 + 8) = 104;
    goto LABEL_29;
  }
  if ( *(_DWORD *)(a1 + 20) )
  {
    LOBYTE(a2) = 1;
    BLFlushBatchOpContextEx(a1, a2, 0);
  }
  if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (*(_BYTE *)(a1 + 8) & 6) == 6 )
  {
    (*(void (__fastcall **)(__int64))(*v7 + 32))(v12);
    *(_BYTE *)(v10 + 13) &= ~1u;
    (*(void (__fastcall **)(__int64))(*v7 + 40))(v136);
  }
  else
  {
LABEL_27:
    *(_BYTE *)(v10 + 13) &= ~1u;
  }
  v14 = (_QWORD **)(a1 + 32);
  v295 = (_QWORD **)(a1 + 32);
  v17 = (_DWORD *)(a1 + 20);
  if ( !a1 )
    goto LABEL_96;
LABEL_29:
  v40 = *v7;
  if ( *(_BYTE *)(*v7 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
  {
    v140 = *(unsigned int *)(a1 + 12);
    v141 = 0;
    *(_BYTE *)(a1 + 4) = 1;
    if ( (_DWORD)v140 != -1 )
    {
      a2 = *(_QWORD *)(v40 + 24);
      if ( a2 )
        v141 = a2 + 20 * v140;
    }
    _InterlockedAdd16((volatile signed __int16 *)(v141 + 16), 1u);
  }
  v41 = *v7;
  v42 = *(_DWORD *)(*v7 + 4);
  if ( !v42 )
  {
    if ( *v17 )
    {
      LOBYTE(a2) = 1;
      BLFlushBatchOpContextEx(a1, a2, 0);
    }
    if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (*(_BYTE *)(a1 + 8) & 6) == 6 )
    {
      (*(void (__fastcall **)(__int64))(*v7 + 32))(v41);
      *(_BYTE *)(v10 + 13) &= ~8u;
      (*(void (__fastcall **)(__int64))(*v7 + 40))(v142);
      goto LABEL_97;
    }
LABEL_96:
    *(_BYTE *)(v10 + 13) &= ~8u;
LABEL_97:
    v39 = a4;
    v295 = v14;
    goto LABEL_34;
  }
  v43 = *v14;
  v44 = *((_DWORD *)*v14 + 2);
  if ( v44 >= *((_DWORD *)*v14 + 3) )
  {
    v44 = 0;
    if ( *(_DWORD *)(a1 + 16) < v42
      && (v213 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v41 + 64)), (v43 = v213) != 0) )
    {
      *(_QWORD *)v213 = 0;
      v213[2] = 0;
      v214 = *(_DWORD *)(*v7 + 8);
      *((_QWORD *)v213 + 2) = v213 + 6;
      v213[3] = v214;
      **v14 = v213;
      v215 = *v7;
      ++*(_DWORD *)(a1 + 16);
      *v14 = v213;
      if ( *(_BYTE *)(v215 + 1) == 1 )
      {
        v216 = *(unsigned int *)(a1 + 12);
        v217 = 0;
        if ( (_DWORD)v216 != -1 )
        {
          v218 = *(_QWORD *)(v215 + 24);
          if ( v218 )
            v217 = v218 + 20 * v216;
        }
        _InterlockedAdd16((volatile signed __int16 *)(v217 + 12), 1u);
        v219 = *(unsigned int *)(a1 + 12);
        v220 = 0;
        if ( (_DWORD)v219 != -1 )
        {
          v221 = *(_QWORD *)(*v7 + 24);
          if ( v221 )
            v220 = (volatile signed __int32 *)(v221 + 20 * v219);
        }
        _InterlockedAdd(v220, 1u);
      }
    }
    else
    {
      LOBYTE(a2) = 1;
      BLFlushBatchOpContextEx(a1, a2, 0);
      v43 = (_QWORD *)(a1 + 56);
    }
  }
  ++*v17;
  ++*((_DWORD *)v43 + 2);
  if ( *(_BYTE *)(*v7 + 1) == 1 )
  {
    v143 = *(unsigned int *)(a1 + 12);
    v144 = 0;
    if ( (_DWORD)v143 != -1 )
    {
      v145 = *(_QWORD *)(*v7 + 24);
      if ( v145 )
        v144 = v145 + 20 * v143;
    }
    _InterlockedAdd16((volatile signed __int16 *)(v144 + 14), 1u);
    v222 = *(unsigned int *)(a1 + 12);
    v223 = 0;
    if ( (_DWORD)v222 != -1 )
    {
      v224 = *(_QWORD *)(*v7 + 24);
      if ( v224 )
        v223 = v224 + 20 * v222;
    }
    _InterlockedAdd((volatile signed __int32 *)(v223 + 4), 1u);
  }
  v45 = v43[2];
  a2 = 3LL * v44;
  v39 = a4;
  v46 = *(_DWORD *)(v45 + 24LL * v44 + 16) & 0xFFFFFFF0 | 5;
  *(_QWORD *)(v45 + 8 * a2) = a4;
  *(_DWORD *)(v45 + 8 * a2 + 16) = v46;
  *(_DWORD *)(v45 + 8 * a2 + 8) = 107;
LABEL_34:
  result = v298;
  v48 = (unsigned __int32 *)(v39 + 4);
  v296 = v48;
  v49 = _byteswap_ulong(*(_DWORD *)(v298 + 12) + a6);
  if ( !a1 )
    goto LABEL_120;
  v50 = *v7;
  if ( *(_BYTE *)(*v7 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
  {
    v146 = *(unsigned int *)(a1 + 12);
    v147 = 0;
    *(_BYTE *)(a1 + 4) = 1;
    if ( (_DWORD)v146 != -1 )
    {
      a2 = *(_QWORD *)(v50 + 24);
      if ( a2 )
        v147 = a2 + 20 * v146;
    }
    _InterlockedAdd16((volatile signed __int16 *)(v147 + 16), 1u);
  }
  v51 = *v7;
  v52 = *(_DWORD *)(*v7 + 4);
  if ( !v52 )
  {
    if ( *v17 )
    {
      LOBYTE(a2) = 1;
      BLFlushBatchOpContextEx(a1, a2, 0);
      v48 = v296;
    }
    if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (result = *(_DWORD *)(a1 + 8) & 6, (*(_BYTE *)(a1 + 8) & 6) == 6) )
    {
      (*(void (__fastcall **)(__int64))(*v7 + 32))(v51);
      *(_DWORD *)(a4 + 4) = v49;
      result = (*(__int64 (__fastcall **)(__int64))(*v7 + 40))(v148);
      goto LABEL_121;
    }
LABEL_120:
    *v48 = v49;
LABEL_121:
    v55 = v295;
    goto LABEL_41;
  }
  v53 = *v14;
  v54 = *((_DWORD *)*v14 + 2);
  if ( v54 >= *((_DWORD *)v53 + 3) )
  {
    v54 = 0;
    if ( *(_DWORD *)(a1 + 16) < v52
      && (v225 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v51 + 64)), (v53 = v225) != 0) )
    {
      v55 = v295;
      *(_QWORD *)v225 = 0;
      v225[2] = 0;
      v226 = *(_DWORD *)(*v7 + 8);
      *((_QWORD *)v225 + 2) = v225 + 6;
      v225[3] = v226;
      **v295 = v225;
      v227 = *v7;
      ++*(_DWORD *)(a1 + 16);
      *v295 = v225;
      if ( *(_BYTE *)(v227 + 1) == 1 )
      {
        v228 = *(unsigned int *)(a1 + 12);
        v229 = 0;
        if ( (_DWORD)v228 != -1 )
        {
          v230 = *(_QWORD *)(v227 + 24);
          if ( v230 )
            v229 = v230 + 20 * v228;
        }
        _InterlockedAdd16((volatile signed __int16 *)(v229 + 12), 1u);
        v231 = *(unsigned int *)(a1 + 12);
        v232 = 0;
        if ( (_DWORD)v231 != -1 )
        {
          v233 = *(_QWORD *)(*v7 + 24);
          if ( v233 )
            v232 = (volatile signed __int32 *)(v233 + 20 * v231);
        }
        _InterlockedAdd(v232, 1u);
      }
    }
    else
    {
      LOBYTE(a2) = 1;
      BLFlushBatchOpContextEx(a1, a2, 0);
      v55 = v295;
      v53 = (_QWORD *)(a1 + 56);
    }
    v48 = v296;
  }
  else
  {
    v55 = v295;
  }
  ++*v17;
  ++*((_DWORD *)v53 + 2);
  if ( *(_BYTE *)(*v7 + 1) == 1 )
  {
    v149 = *(unsigned int *)(a1 + 12);
    v150 = 0;
    if ( (_DWORD)v149 != -1 )
    {
      v151 = *(_QWORD *)(*v7 + 24);
      if ( v151 )
        v150 = v151 + 20 * v149;
    }
    _InterlockedAdd16((volatile signed __int16 *)(v150 + 14), 1u);
    v234 = *(unsigned int *)(a1 + 12);
    v235 = 0;
    if ( (_DWORD)v234 != -1 )
    {
      v236 = *(_QWORD *)(*v7 + 24);
      if ( v236 )
        v235 = v236 + 20 * v234;
    }
    _InterlockedAdd((volatile signed __int32 *)(v235 + 4), 1u);
  }
  v56 = v53[2];
  a2 = 3LL * v54;
  v57 = *(_DWORD *)(v56 + 24LL * v54 + 16) & 0xFFFFFFF3;
  *(_QWORD *)(v56 + 8 * a2) = v48;
  result = v57 | 3;
  *(_DWORD *)(v56 + 8 * a2 + 8) = v49;
  *(_DWORD *)(v56 + 8 * a2 + 16) = result;
LABEL_41:
  if ( (*(_BYTE *)(v298 + 27) & 1) == 0 )
  {
    HIWORD(v58) = HIWORD(a5);
    result = 0x7FFF;
    LOWORD(v58) = __ROR2__((*(_WORD *)(v298 + 16) + a5) & 0x7FFF, 8);
    v59 = a3 + 2;
    v301 = v58;
    v294 = v58;
    if ( !a1 )
      goto LABEL_91;
    v60 = *v7;
    if ( *(_BYTE *)(*v7 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
    {
      v152 = *(unsigned int *)(a1 + 12);
      v153 = 0;
      *(_BYTE *)(a1 + 4) = 1;
      if ( (_DWORD)v152 != -1 )
      {
        a2 = *(_QWORD *)(v60 + 24);
        if ( a2 )
          v153 = a2 + 20 * v152;
      }
      _InterlockedAdd16((volatile signed __int16 *)(v153 + 16), 1u);
    }
    v61 = *v7;
    v62 = *(_DWORD *)(*v7 + 4);
    if ( v62 )
    {
      v63 = *v55;
      v64 = *((_DWORD *)*v55 + 2);
      if ( v64 >= *((_DWORD *)*v55 + 3) )
      {
        v64 = 0;
        if ( *(_DWORD *)(a1 + 16) < v62
          && (v237 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v61 + 64)), (v63 = v237) != 0) )
        {
          *(_QWORD *)v237 = 0;
          v237[2] = 0;
          v237[3] = *(_DWORD *)(*v7 + 8);
          *((_QWORD *)v237 + 2) = v237 + 6;
          **v295 = v237;
          v238 = *v7;
          ++*(_DWORD *)(a1 + 16);
          *v295 = v237;
          if ( *(_BYTE *)(v238 + 1) == 1 )
          {
            v239 = *(unsigned int *)(a1 + 12);
            v240 = 0;
            if ( (_DWORD)v239 != -1 )
            {
              v241 = *(_QWORD *)(v238 + 24);
              if ( v241 )
                v240 = v241 + 20 * v239;
            }
            _InterlockedAdd16((volatile signed __int16 *)(v240 + 12), 1u);
            v242 = *(unsigned int *)(a1 + 12);
            v243 = 0;
            if ( (_DWORD)v242 != -1 )
            {
              v244 = *(_QWORD *)(*v7 + 24);
              if ( v244 )
                v243 = (volatile signed __int32 *)(v244 + 20 * v242);
            }
            _InterlockedAdd(v243, 1u);
          }
        }
        else
        {
          LOBYTE(a2) = 1;
          BLFlushBatchOpContextEx(a1, a2, 0);
          v63 = (_DWORD *)(a1 + 56);
        }
        LOWORD(v58) = v301;
      }
      ++*v17;
      ++v63[2];
      if ( *(_BYTE *)(*v7 + 1) == 1 )
      {
        v154 = *(unsigned int *)(a1 + 12);
        v155 = 0;
        if ( (_DWORD)v154 != -1 )
        {
          v156 = *(_QWORD *)(*v7 + 24);
          if ( v156 )
            v155 = v156 + 20 * v154;
        }
        _InterlockedAdd16((volatile signed __int16 *)(v155 + 14), 1u);
        v245 = *(unsigned int *)(a1 + 12);
        v246 = 0;
        if ( (_DWORD)v245 != -1 )
        {
          v247 = *(_QWORD *)(*v7 + 24);
          if ( v247 )
            v246 = v247 + 20 * v245;
        }
        _InterlockedAdd((volatile signed __int32 *)(v246 + 4), 1u);
      }
      v65 = *((_QWORD *)v63 + 2);
      v66 = 3LL * v64;
      v67 = *(_DWORD *)(v65 + 24LL * v64 + 16) & 0xFFFFFFF2;
      *(_QWORD *)(v65 + 8 * v66) = v59;
      result = v67 | 2;
      *(_WORD *)(v65 + 8 * v66 + 8) = v58;
      *(_DWORD *)(v65 + 8 * v66 + 16) = result;
      goto LABEL_48;
    }
    if ( *v17 )
    {
      LOBYTE(a2) = 1;
      BLFlushBatchOpContextEx(a1, a2, 0);
      LOWORD(v58) = v301;
    }
    if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (result = *(_DWORD *)(a1 + 8) & 6, (*(_BYTE *)(a1 + 8) & 6) == 6) )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 32LL))(v61);
      *v59 = v301;
      result = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)(a1 + 80) + 40LL))(v301);
    }
    else
    {
LABEL_91:
      *v59 = v58;
    }
  }
LABEL_48:
  v68 = v298;
  if ( (*(_BYTE *)(v298 + 27) & 0x10) != 0 )
    return result;
  v69 = __ROR2__(v297 - *(_WORD *)(v298 + 22), 8);
  v70 = (_WORD *)(a4 + 16);
  v71 = *(unsigned __int16 *)(v298 + 20) + (unsigned int)v69;
  v72 = (unsigned __int16)(*(_WORD *)(v298 + 20) + v69) + WORD1(v71);
  if ( !a1 )
    goto LABEL_108;
  v73 = *(_QWORD *)(a1 + 80);
  if ( *(_BYTE *)(v73 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
  {
    v157 = *(unsigned int *)(a1 + 12);
    v158 = 0;
    *(_BYTE *)(a1 + 4) = 1;
    if ( (_DWORD)v157 != -1 )
    {
      v71 = *(_QWORD *)(v73 + 24);
      if ( v71 )
        v158 = v71 + 20 * v157;
    }
    _InterlockedAdd16((volatile signed __int16 *)(v158 + 16), 1u);
  }
  v74 = (__int64 *)(a1 + 80);
  v75 = *(_QWORD *)(a1 + 80);
  v76 = *(_DWORD *)(v75 + 4);
  if ( v76 )
  {
    v77 = *(_DWORD **)(a1 + 32);
    v78 = v77[2];
    if ( v78 >= v77[3] )
    {
      v78 = 0;
      if ( *(_DWORD *)(a1 + 16) < v76
        && (v248 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v75 + 64)), (v77 = v248) != 0) )
      {
        *(_QWORD *)v248 = 0;
        v248[2] = 0;
        v249 = *(_DWORD *)(*v74 + 8);
        *((_QWORD *)v248 + 2) = v248 + 6;
        v248[3] = v249;
        **(_QWORD **)(a1 + 32) = v248;
        v250 = *v74;
        ++*(_DWORD *)(a1 + 16);
        *(_QWORD *)(a1 + 32) = v248;
        if ( *(_BYTE *)(v250 + 1) == 1 )
        {
          v251 = *(unsigned int *)(a1 + 12);
          v252 = 0;
          if ( (_DWORD)v251 != -1 )
          {
            v253 = *(_QWORD *)(v250 + 24);
            if ( v253 )
              v252 = v253 + 20 * v251;
          }
          _InterlockedAdd16((volatile signed __int16 *)(v252 + 12), 1u);
          v254 = *(unsigned int *)(a1 + 12);
          v255 = 0;
          if ( (_DWORD)v254 != -1 )
          {
            v256 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
            if ( v256 )
              v255 = (volatile signed __int32 *)(v256 + 20 * v254);
          }
          _InterlockedAdd(v255, 1u);
          v74 = (__int64 *)(a1 + 80);
        }
      }
      else
      {
        LOBYTE(v71) = 1;
        BLFlushBatchOpContextEx(a1, v71, 0);
        v77 = (_DWORD *)(a1 + 56);
      }
    }
    ++*(_DWORD *)(a1 + 20);
    ++v77[2];
    if ( *(_BYTE *)(*v74 + 1) == 1 )
    {
      v159 = *(unsigned int *)(a1 + 12);
      v160 = 0;
      if ( (_DWORD)v159 != -1 )
      {
        v161 = *(_QWORD *)(*v74 + 24);
        if ( v161 )
          v160 = v161 + 20 * v159;
      }
      _InterlockedAdd16((volatile signed __int16 *)(v160 + 14), 1u);
      v257 = *(unsigned int *)(a1 + 12);
      v258 = 0;
      if ( (_DWORD)v257 != -1 )
      {
        v259 = *(_QWORD *)(*v74 + 24);
        if ( v259 )
          v258 = v259 + 20 * v257;
      }
      _InterlockedAdd((volatile signed __int32 *)(v258 + 4), 1u);
    }
    v79 = *((_QWORD *)v77 + 2);
    v71 = 3LL * v78;
    v80 = *(_DWORD *)(v79 + 24LL * v78 + 16);
    v68 = v298;
    *(_QWORD *)(v79 + 8 * v71) = v70;
    *(_DWORD *)(v79 + 8 * v71 + 16) = v80 & 0xFFFFFFF0 | 2;
    *(_WORD *)(v79 + 8 * v71 + 8) = v72;
    goto LABEL_55;
  }
  if ( *(_DWORD *)(a1 + 20) )
  {
    LOBYTE(v71) = 1;
    BLFlushBatchOpContextEx(a1, v71, 0);
  }
  if ( (*(_BYTE *)(a1 + 8) & 5) != 5 && (*(_BYTE *)(a1 + 8) & 6) != 6 )
  {
LABEL_108:
    *v70 = v72;
LABEL_55:
    v81 = (__int64 *)(a1 + 80);
    goto LABEL_56;
  }
  v81 = (__int64 *)(a1 + 80);
  (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
  *v70 = v72;
  (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
LABEL_56:
  result = *(unsigned __int8 *)(v68 + 26);
  v82 = v297 - result;
  if ( (*(_BYTE *)(v68 + 27) & 1) == 0 )
  {
    v83 = __ROR2__(v82, 8);
    v84 = a3 + 1;
    if ( a1 )
    {
      v85 = *v81;
      if ( *(_BYTE *)(*v81 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
      {
        v167 = *(unsigned int *)(a1 + 12);
        v168 = 0;
        *(_BYTE *)(a1 + 4) = 1;
        if ( (_DWORD)v167 != -1 )
        {
          v71 = *(_QWORD *)(v85 + 24);
          if ( v71 )
            v168 = v71 + 20 * v167;
        }
        _InterlockedAdd16((volatile signed __int16 *)(v168 + 16), 1u);
        v81 = (__int64 *)(a1 + 80);
      }
      v86 = *(_DWORD *)(*v81 + 4);
      if ( v86 )
      {
        v87 = *(_DWORD **)(a1 + 32);
        v88 = v87[2];
        if ( v88 >= v87[3] )
        {
          v88 = 0;
          if ( *(_DWORD *)(a1 + 16) < v86
            && (v271 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*v81 + 64)), (v87 = v271) != 0) )
          {
            *(_QWORD *)v271 = 0;
            v271[2] = 0;
            v272 = *(_DWORD *)(*v81 + 8);
            *((_QWORD *)v271 + 2) = v271 + 6;
            v271[3] = v272;
            **(_QWORD **)(a1 + 32) = v271;
            v273 = *v81;
            ++*(_DWORD *)(a1 + 16);
            *(_QWORD *)(a1 + 32) = v271;
            if ( *(_BYTE *)(v273 + 1) == 1 )
            {
              v274 = *(unsigned int *)(a1 + 12);
              v275 = 0;
              if ( (_DWORD)v274 != -1 )
              {
                v276 = *(_QWORD *)(v273 + 24);
                if ( v276 )
                  v275 = v276 + 20 * v274;
              }
              _InterlockedAdd16((volatile signed __int16 *)(v275 + 12), 1u);
              v277 = *(unsigned int *)(a1 + 12);
              v278 = 0;
              if ( (_DWORD)v277 != -1 )
              {
                v279 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
                if ( v279 )
                  v278 = (volatile signed __int32 *)(v279 + 20 * v277);
              }
              _InterlockedAdd(v278, 1u);
              v81 = (__int64 *)(a1 + 80);
            }
          }
          else
          {
            LOBYTE(v71) = 1;
            BLFlushBatchOpContextEx(a1, v71, 0);
            v87 = (_DWORD *)(a1 + 56);
          }
        }
        ++*(_DWORD *)(a1 + 20);
        ++v87[2];
        if ( *(_BYTE *)(*v81 + 1) == 1 )
        {
          v169 = *(unsigned int *)(a1 + 12);
          v170 = 0;
          if ( (_DWORD)v169 != -1 )
          {
            v171 = *(_QWORD *)(*v81 + 24);
            if ( v171 )
              v170 = v171 + 20 * v169;
          }
          _InterlockedAdd16((volatile signed __int16 *)(v170 + 14), 1u);
          v280 = *(unsigned int *)(a1 + 12);
          v281 = 0;
          if ( (_DWORD)v280 != -1 )
          {
            v282 = *(_QWORD *)(*v81 + 24);
            if ( v282 )
              v281 = v282 + 20 * v280;
          }
          _InterlockedAdd((volatile signed __int32 *)(v281 + 4), 1u);
          v81 = (__int64 *)(a1 + 80);
        }
        v89 = *((_QWORD *)v87 + 2);
        v90 = 3LL * v88;
        v91 = *(_DWORD *)(v89 + 24LL * v88 + 16);
        v68 = v298;
        *(_QWORD *)(v89 + 8 * v90) = v84;
        *(_DWORD *)(v89 + 8 * v90 + 16) = v91 & 0xFFFFFFF0 | 2;
        *(_WORD *)(v89 + 8 * v90 + 8) = v83;
LABEL_63:
        v92 = v83 + *(unsigned __int16 *)(v68 + 18);
        result = v294;
        v93 = a3 + 5;
        v94 = (unsigned int)v294 + v92;
        v95 = ~((unsigned int)(v94 + __ROR4__(v94, 16)) >> 16);
        if ( !a1 )
          goto LABEL_113;
        v96 = *v81;
        if ( *(_BYTE *)(*v81 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
        {
          v172 = *(unsigned int *)(a1 + 12);
          v173 = 0;
          *(_BYTE *)(a1 + 4) = 1;
          if ( (_DWORD)v172 != -1 )
          {
            v94 = *(_QWORD *)(v96 + 24);
            if ( v94 )
              v173 = v94 + 20 * v172;
          }
          _InterlockedAdd16((volatile signed __int16 *)(v173 + 16), 1u);
          v81 = (__int64 *)(a1 + 80);
        }
        v97 = *(_DWORD *)(*v81 + 4);
        if ( v97 )
        {
          v98 = *(_DWORD **)(a1 + 32);
          v99 = v98[2];
          if ( v99 >= v98[3] )
          {
            v99 = 0;
            if ( *(_DWORD *)(a1 + 16) < v97
              && (v283 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*v81 + 64)), (v98 = v283) != 0) )
            {
              *(_QWORD *)v283 = 0;
              v283[2] = 0;
              v284 = *(_DWORD *)(*v81 + 8);
              *((_QWORD *)v283 + 2) = v283 + 6;
              v283[3] = v284;
              **(_QWORD **)(a1 + 32) = v283;
              v285 = *v81;
              ++*(_DWORD *)(a1 + 16);
              *(_QWORD *)(a1 + 32) = v283;
              if ( *(_BYTE *)(v285 + 1) == 1 )
              {
                v286 = *(unsigned int *)(a1 + 12);
                v287 = 0;
                if ( (_DWORD)v286 != -1 )
                {
                  v288 = *(_QWORD *)(v285 + 24);
                  if ( v288 )
                    v287 = v288 + 20 * v286;
                }
                _InterlockedAdd16((volatile signed __int16 *)(v287 + 12), 1u);
                v289 = *(unsigned int *)(a1 + 12);
                v290 = 0;
                if ( (_DWORD)v289 != -1 )
                {
                  v291 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
                  if ( v291 )
                    v290 = (volatile signed __int32 *)(v291 + 20 * v289);
                }
                _InterlockedAdd(v290, 1u);
                v81 = (__int64 *)(a1 + 80);
              }
            }
            else
            {
              LOBYTE(v94) = 1;
              BLFlushBatchOpContextEx(a1, v94, 0);
              v98 = (_DWORD *)(a1 + 56);
            }
          }
          ++*(_DWORD *)(a1 + 20);
          ++v98[2];
          if ( *(_BYTE *)(*v81 + 1) == 1 )
          {
            v174 = *(unsigned int *)(a1 + 12);
            v175 = 0;
            if ( (_DWORD)v174 != -1 )
            {
              v176 = *(_QWORD *)(*v81 + 24);
              if ( v176 )
                v175 = v176 + 20 * v174;
            }
            _InterlockedAdd16((volatile signed __int16 *)(v175 + 14), 1u);
            v292 = *(unsigned int *)(a1 + 12);
            if ( (_DWORD)v292 != -1 )
            {
              v293 = *(_QWORD *)(*v81 + 24);
              if ( v293 )
                v9 = v293 + 20 * v292;
            }
            _InterlockedAdd((volatile signed __int32 *)(v9 + 4), 1u);
          }
          v100 = *((_QWORD *)v98 + 2);
          v101 = 3LL * v99;
          v102 = *(_DWORD *)(v100 + 24LL * v99 + 16) & 0xFFFFFFF2;
          *(_QWORD *)(v100 + 8 * v101) = v93;
          result = v102 | 2;
          *(_WORD *)(v100 + 8 * v101 + 8) = v95;
          *(_DWORD *)(v100 + 8 * v101 + 16) = result;
          return result;
        }
        if ( *(_DWORD *)(a1 + 20) )
        {
          LOBYTE(v94) = 1;
          BLFlushBatchOpContextEx(a1, v94, 0);
        }
        if ( (*(_BYTE *)(a1 + 8) & 5) != 5 )
        {
          result = *(_DWORD *)(a1 + 8) & 6;
          if ( (*(_BYTE *)(a1 + 8) & 6) != 6 )
          {
LABEL_113:
            *v93 = v95;
            return result;
          }
        }
        (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
        *v93 = v95;
        return (*(__int64 (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
      }
      if ( *(_DWORD *)(a1 + 20) )
      {
        LOBYTE(v71) = 1;
        BLFlushBatchOpContextEx(a1, v71, 0);
      }
      if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (v81 = (__int64 *)(a1 + 80), (*(_BYTE *)(a1 + 8) & 6) == 6) )
      {
        (*(void (**)(void))(*v81 + 32))();
        *v84 = v83;
        (*(void (**)(void))(*v81 + 40))();
        goto LABEL_63;
      }
    }
    *v84 = v83;
    goto LABEL_63;
  }
  v103 = a3 + 2;
  v104 = __ROR2__(v82 - 40, 8);
  if ( !a1 )
  {
LABEL_143:
    *v103 = v104;
    return result;
  }
  v105 = *(_QWORD *)(a1 + 80);
  if ( *(_BYTE *)(v105 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
  {
    v162 = *(unsigned int *)(a1 + 12);
    v163 = 0;
    *(_BYTE *)(a1 + 4) = 1;
    if ( (_DWORD)v162 != -1 )
    {
      v71 = *(_QWORD *)(v105 + 24);
      if ( v71 )
        v163 = v71 + 20 * v162;
    }
    _InterlockedAdd16((volatile signed __int16 *)(v163 + 16), 1u);
  }
  v106 = (__int64 *)(a1 + 80);
  v107 = *(_QWORD *)(a1 + 80);
  v108 = *(_DWORD *)(v107 + 4);
  if ( !v108 )
  {
    if ( *(_DWORD *)(a1 + 20) )
    {
      LOBYTE(v71) = 1;
      BLFlushBatchOpContextEx(a1, v71, 0);
    }
    if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (result = *(_DWORD *)(a1 + 8) & 6, (*(_BYTE *)(a1 + 8) & 6) == 6) )
    {
      (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
      *v103 = v104;
      return (*(__int64 (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
    }
    goto LABEL_143;
  }
  v109 = *(_DWORD **)(a1 + 32);
  v110 = v109[2];
  if ( v110 >= v109[3] )
  {
    v110 = 0;
    if ( *(_DWORD *)(a1 + 16) < v108
      && (v260 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v107 + 64)), (v109 = v260) != 0) )
    {
      *(_QWORD *)v260 = 0;
      v260[2] = 0;
      v261 = *(_DWORD *)(*v106 + 8);
      *((_QWORD *)v260 + 2) = v260 + 6;
      v260[3] = v261;
      **(_QWORD **)(a1 + 32) = v260;
      v262 = *v106;
      ++*(_DWORD *)(a1 + 16);
      *(_QWORD *)(a1 + 32) = v260;
      if ( *(_BYTE *)(v262 + 1) == 1 )
      {
        v263 = *(unsigned int *)(a1 + 12);
        v264 = 0;
        if ( (_DWORD)v263 != -1 )
        {
          v265 = *(_QWORD *)(v262 + 24);
          if ( v265 )
            v264 = v265 + 20 * v263;
        }
        _InterlockedAdd16((volatile signed __int16 *)(v264 + 12), 1u);
        v266 = *(unsigned int *)(a1 + 12);
        v267 = 0;
        if ( (_DWORD)v266 != -1 )
        {
          v268 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
          if ( v268 )
            v267 = (volatile signed __int32 *)(v268 + 20 * v266);
        }
        _InterlockedAdd(v267, 1u);
        v106 = (__int64 *)(a1 + 80);
      }
    }
    else
    {
      LOBYTE(v71) = 1;
      BLFlushBatchOpContextEx(a1, v71, 0);
      v109 = (_DWORD *)(a1 + 56);
    }
  }
  ++*(_DWORD *)(a1 + 20);
  ++v109[2];
  if ( *(_BYTE *)(*v106 + 1) == 1 )
  {
    v164 = *(unsigned int *)(a1 + 12);
    v165 = 0;
    if ( (_DWORD)v164 != -1 )
    {
      v166 = *(_QWORD *)(*v106 + 24);
      if ( v166 )
        v165 = v166 + 20 * v164;
    }
    _InterlockedAdd16((volatile signed __int16 *)(v165 + 14), 1u);
    v269 = *(unsigned int *)(a1 + 12);
    if ( (_DWORD)v269 != -1 )
    {
      v270 = *(_QWORD *)(*v106 + 24);
      if ( v270 )
        v9 = v270 + 20 * v269;
    }
    _InterlockedAdd((volatile signed __int32 *)(v9 + 4), 1u);
  }
  v111 = *((_QWORD *)v109 + 2);
  v112 = 3LL * v110;
  v113 = *(_DWORD *)(v111 + 24LL * v110 + 16) & 0xFFFFFFF2;
  *(_QWORD *)(v111 + 8 * v112) = v103;
  result = v113 | 2;
  *(_WORD *)(v111 + 8 * v112 + 8) = v104;
  *(_DWORD *)(v111 + 8 * v112 + 16) = result;
  return result;
}

```

## disassembly

```asm
0x1400d9980  mov     [rsp+arg_18], r9
0x1400d9985  mov     [rsp+arg_10], r8
0x1400d998a  mov     [rsp+arg_8], rdx
0x1400d998f  push    rbx
0x1400d9990  push    rbp
0x1400d9991  push    rsi
0x1400d9992  push    rdi
0x1400d9993  push    r12
0x1400d9995  push    r13
0x1400d9997  push    r14
0x1400d9999  push    r15
0x1400d999b  sub     rsp, 48h
0x1400d999f  movzx   eax, word ptr [rdx+18h]
0x1400d99a3  lea     r14, [rcx+50h]
0x1400d99a7  mov     rbx, rcx
0x1400d99aa  mov     dword ptr [rsp+88h+var_68], 0CCCCh
0x1400d99b2  mov     ecx, [rsp+88h+arg_20]
0x1400d99b9  or      r13d, 0FFFFFFFFh
0x1400d99bd  xor     edi, edi
0x1400d99bf  mov     r15, r9
0x1400d99c2  mov     esi, 1
0x1400d99c7  cmp     ecx, [rdx+8]
0x1400d99ca  jz      loc_1400D9A84
0x1400d99d0  add     ax, [rdx]
0x1400d99d3  mov     [rsp+88h+arg_0], ax
0x1400d99db  test    rbx, rbx
0x1400d99de  jz      loc_1400D9BF0
0x1400d99e4  mov     rcx, [r14]
0x1400d99e7  cmp     [rcx+1], sil
0x1400d99eb  jz      loc_1400DA512
0x1400d99f1  lea     r14, [rbx+50h]
0x1400d99f5  mov     rcx, [r14]
0x1400d99f8  mov     eax, [rcx+4]
0x1400d99fb  test    eax, eax
0x1400d99fd  jz      loc_1400D9BCB
0x1400d9a03  lea     r12, [rbx+20h]
0x1400d9a07  mov     r8, [r12]
0x1400d9a0b  mov     [rsp+88h+var_60], r12
0x1400d9a10  mov     r15d, [r8+8]
0x1400d9a14  cmp     r15d, [r8+0Ch]
0x1400d9a18  jnb     short loc_1400D9A64
0x1400d9a1a  lea     rbp, [rbx+14h]
0x1400d9a1e  add     [rbp+0], esi
0x1400d9a21  add     [r8+8], esi
0x1400d9a25  mov     rcx, [r14]
0x1400d9a28  cmp     [rcx+1], sil
0x1400d9a2c  jz      loc_1400DA587
0x1400d9a32  mov     rcx, [r8+10h]
0x1400d9a36  mov     eax, r15d
0x1400d9a39  lea     rdx, [rax+rax*2]
0x1400d9a3d  mov     eax, [rcx+rdx*8+10h]
0x1400d9a41  mov     r15, [rsp+88h+arg_18]
0x1400d9a49  and     eax, 0FFFFFFF5h
0x1400d9a4c  or      eax, 5
0x1400d9a4f  mov     [rcx+rdx*8], r15
0x1400d9a53  mov     [rcx+rdx*8+10h], eax
0x1400d9a57  mov     dword ptr [rcx+rdx*8+8], 68h ; 'h'
0x1400d9a5f  jmp     loc_1400D9C13
0x1400d9a64  mov     r15d, edi
0x1400d9a67  cmp     [rbx+10h], eax
0x1400d9a6a  jb      loc_1401CDBA8
0x1400d9a70  xor     r8d, r8d
0x1400d9a73  mov     dl, sil
0x1400d9a76  mov     rcx, rbx
0x1400d9a79  call    BLFlushBatchOpContextEx
0x1400d9a7e  lea     r8, [rbx+38h]
0x1400d9a82  jmp     short loc_1400D9A1A
0x1400d9a84  movzx   ecx, word ptr [rdx+4]
0x1400d9a88  sub     cx, word ptr [rsp+88h+arg_28]
0x1400d9a90  mov     r12b, [rdx+1Bh]
0x1400d9a94  add     cx, ax
0x1400d9a97  and     r12b, 2
0x1400d9a9b  mov     [rsp+88h+arg_0], cx
0x1400d9aa3  test    rbx, rbx
0x1400d9aa6  jz      loc_1400DA2D1
0x1400d9aac  mov     rcx, [r14]
0x1400d9aaf  cmp     [rcx+1], sil
0x1400d9ab3  jz      loc_1400DA428
0x1400d9ab9  lea     r14, [rbx+50h]
0x1400d9abd  mov     rcx, [r14]
0x1400d9ac0  mov     eax, [rcx+4]
0x1400d9ac3  test    eax, eax
0x1400d9ac5  jz      loc_1400DA2AC
0x1400d9acb  lea     r10, [rbx+20h]
0x1400d9acf  mov     rdx, [r10]
0x1400d9ad2  mov     [rsp+88h+var_60], r10
0x1400d9ad7  mov     r15d, [rdx+8]
0x1400d9adb  cmp     r15d, [rdx+0Ch]
0x1400d9adf  jnb     loc_1400DA0B9
0x1400d9ae5  lea     rbp, [rbx+14h]
0x1400d9ae9  add     [rbp+0], esi
0x1400d9aec  add     [rdx+8], esi
0x1400d9aef  mov     rcx, [r14]
0x1400d9af2  cmp     [rcx+1], sil
0x1400d9af6  jz      loc_1400DA473
0x1400d9afc  mov     rdx, [rdx+10h]
0x1400d9b00  mov     eax, r15d
0x1400d9b03  lea     r8, [rax+rax*2]
0x1400d9b07  mov     eax, [rdx+r8*8+10h]
0x1400d9b0c  neg     r12b
0x1400d9b0f  mov     r12, [rsp+88h+arg_18]
0x1400d9b17  sbb     ecx, ecx
0x1400d9b19  mov     [rdx+r8*8], r12
0x1400d9b1d  add     ecx, 5
0x1400d9b20  mov     dword ptr [rdx+r8*8+8], 68h ; 'h'
0x1400d9b29  and     eax, 0FFFFFFF0h
0x1400d9b2c  or      ecx, eax
0x1400d9b2e  mov     [rdx+r8*8+10h], ecx
0x1400d9b33  mov     r15, [rsp+88h+arg_8]
0x1400d9b3b  mov     r15b, [r15+1Bh]
0x1400d9b3f  and     r15b, 4
0x1400d9b43  test    rbx, rbx
0x1400d9b46  jz      loc_1400DA30D
0x1400d9b4c  mov     rcx, [r14]
0x1400d9b4f  cmp     [rcx+1], sil
0x1400d9b53  jz      loc_1400DA49D
0x1400d9b59  mov     rcx, [r14]
0x1400d9b5c  mov     eax, [rcx+4]
0x1400d9b5f  test    eax, eax
0x1400d9b61  jz      loc_1400DA2E8
0x1400d9b67  mov     rdx, [r10]
0x1400d9b6a  mov     r12d, [rdx+8]
0x1400d9b6e  cmp     r12d, [rdx+0Ch]
0x1400d9b72  jnb     loc_1400DA0E0
0x1400d9b78  add     [rbp+0], esi
0x1400d9b7b  add     [rdx+8], esi
0x1400d9b7e  mov     rcx, [r14]
0x1400d9b81  cmp     [rcx+1], sil
0x1400d9b85  jz      loc_1400DA4E8
0x1400d9b8b  mov     rdx, [rdx+10h]
0x1400d9b8f  mov     eax, r12d
0x1400d9b92  lea     r8, [rax+rax*2]
0x1400d9b96  mov     eax, [rdx+r8*8+10h]
0x1400d9b9b  neg     r15b
0x1400d9b9e  mov     r11, [rsp+88h+arg_18]
0x1400d9ba6  sbb     ecx, ecx
0x1400d9ba8  mov     [rdx+r8*8], r11
0x1400d9bac  add     ecx, 5
0x1400d9baf  mov     dword ptr [rdx+r8*8+8], 6Bh ; 'k'
0x1400d9bb8  and     eax, 0FFFFFFF0h
0x1400d9bbb  or      ecx, eax
0x1400d9bbd  mov     [rdx+r8*8+10h], ecx
0x1400d9bc2  lea     r12, [rbx+20h]
0x1400d9bc6  jmp     loc_1400D9C81
0x1400d9bcb  cmp     [rbx+14h], edi
0x1400d9bce  jnz     loc_1400DA54A
0x1400d9bd4  mov     eax, [rbx+8]
0x1400d9bd7  and     eax, 5
0x1400d9bda  cmp     al, 5
0x1400d9bdc  jz      loc_1400DA55D
0x1400d9be2  mov     eax, [rbx+8]
0x1400d9be5  and     eax, 6
0x1400d9be8  cmp     al, 6
0x1400d9bea  jz      loc_1400DA55D
0x1400d9bf0  movzx   eax, byte ptr [r15+0Dh]
0x1400d9bf5  btr     eax, 0
0x1400d9bf9  mov     [r15+0Dh], al
0x1400d9bfd  lea     r12, [rbx+20h]
0x1400d9c01  mov     [rsp+88h+var_60], r12
0x1400d9c06  lea     rbp, [rbx+14h]
0x1400d9c0a  test    rbx, rbx
0x1400d9c0d  jz      loc_1400DA157
0x1400d9c13  mov     rcx, [r14]
0x1400d9c16  cmp     [rcx+1], sil
0x1400d9c1a  jz      loc_1400DA5B1
0x1400d9c20  mov     rcx, [r14]
0x1400d9c23  mov     eax, [rcx+4]
0x1400d9c26  test    eax, eax
0x1400d9c28  jz      loc_1400DA132
0x1400d9c2e  mov     r8, [r12]
0x1400d9c32  mov     r15d, [r8+8]
0x1400d9c36  cmp     r15d, [r8+0Ch]
0x1400d9c3a  jnb     loc_1400DA02F
0x1400d9c40  add     [rbp+0], esi
0x1400d9c43  add     [r8+8], esi
0x1400d9c47  mov     rcx, [r14]
0x1400d9c4a  cmp     [rcx+1], sil
0x1400d9c4e  jz      loc_1400DA626
0x1400d9c54  mov     rcx, [r8+10h]
0x1400d9c58  mov     eax, r15d
0x1400d9c5b  lea     rdx, [rax+rax*2]
0x1400d9c5f  mov     eax, [rcx+rdx*8+10h]
0x1400d9c63  mov     r11, [rsp+88h+arg_18]
0x1400d9c6b  and     eax, 0FFFFFFF5h
0x1400d9c6e  or      eax, 5
0x1400d9c71  mov     [rcx+rdx*8], r11
0x1400d9c75  mov     [rcx+rdx*8+10h], eax
0x1400d9c79  mov     dword ptr [rcx+rdx*8+8], 6Bh ; 'k'
0x1400d9c81  mov     rax, [rsp+88h+arg_8]
0x1400d9c89  add     r11, 4
0x1400d9c8d  mov     r15d, [rsp+88h+arg_28]
0x1400d9c95  mov     [rsp+88h+var_58], r11
0x1400d9c9a  add     r15d, [rax+0Ch]
0x1400d9c9e  bswap   r15d
0x1400d9ca1  test    rbx, rbx
0x1400d9ca4  jz      loc_1400DA29F
0x1400d9caa  mov     rcx, [r14]
0x1400d9cad  cmp     [rcx+1], sil
0x1400d9cb1  jz      loc_1400DA650
0x1400d9cb7  mov     rcx, [r14]
0x1400d9cba  mov     eax, [rcx+4]
0x1400d9cbd  test    eax, eax
0x1400d9cbf  jz      loc_1400DA27A
0x1400d9cc5  mov     r8, [r12]
0x1400d9cc9  mov     r12d, [r8+8]
0x1400d9ccd  cmp     r12d, [r8+0Ch]
0x1400d9cd1  jnb     loc_1400D9FD7
0x1400d9cd7  mov     r10, [rsp+88h+var_60]
0x1400d9cdc  add     [rbp+0], esi
0x1400d9cdf  add     [r8+8], esi
0x1400d9ce3  mov     rcx, [r14]
0x1400d9ce6  cmp     [rcx+1], sil
0x1400d9cea  jz      loc_1400DA6C9
0x1400d9cf0  mov     rcx, [r8+10h]
0x1400d9cf4  mov     eax, r12d
0x1400d9cf7  lea     rdx, [rax+rax*2]
0x1400d9cfb  mov     eax, [rcx+rdx*8+10h]
0x1400d9cff  and     eax, 0FFFFFFF3h
0x1400d9d02  mov     [rcx+rdx*8], r11
0x1400d9d06  or      eax, 3
0x1400d9d09  mov     [rcx+rdx*8+8], r15d
0x1400d9d0e  mov     [rcx+rdx*8+10h], eax
0x1400d9d12  mov     rcx, [rsp+88h+arg_8]
0x1400d9d1a  test    [rcx+1Bh], sil
0x1400d9d1e  jnz     loc_1400D9DC5
0x1400d9d24  mov     r11d, [rsp+88h+arg_20]
0x1400d9d2c  mov     eax, 7FFFh
0x1400d9d31  add     r11w, [rcx+10h]
0x1400d9d36  mov     r12, [rsp+88h+arg_10]
0x1400d9d3e  and     r11w, ax
0x1400d9d42  ror     r11w, 8
0x1400d9d47  add     r12, 4
0x1400d9d4b  mov     [rsp+88h+arg_20], r11d
0x1400d9d53  mov     [rsp+88h+var_68], r11w
0x1400d9d59  test    rbx, rbx
0x1400d9d5c  jz      loc_1400DA128
0x1400d9d62  mov     rcx, [r14]
0x1400d9d65  cmp     [rcx+1], sil
0x1400d9d69  jz      loc_1400DA6F3
0x1400d9d6f  mov     rcx, [r14]
0x1400d9d72  mov     eax, [rcx+4]
0x1400d9d75  test    eax, eax
0x1400d9d77  jz      loc_1400DA103
0x1400d9d7d  mov     r8, [r10]
0x1400d9d80  mov     r15d, [r8+8]
0x1400d9d84  cmp     r15d, [r8+0Ch]
0x1400d9d88  jnb     loc_1400DA004
0x1400d9d8e  add     [rbp+0], esi
0x1400d9d91  add     [r8+8], esi
0x1400d9d95  mov     rcx, [r14]
0x1400d9d98  cmp     [rcx+1], sil
0x1400d9d9c  jz      loc_1400DA771
0x1400d9da2  mov     rcx, [r8+10h]
0x1400d9da6  mov     eax, r15d
0x1400d9da9  lea     rdx, [rax+rax*2]
0x1400d9dad  mov     eax, [rcx+rdx*8+10h]
0x1400d9db1  and     eax, 0FFFFFFF2h
0x1400d9db4  mov     [rcx+rdx*8], r12
0x1400d9db8  or      eax, 2
0x1400d9dbb  mov     [rcx+rdx*8+8], r11w
0x1400d9dc1  mov     [rcx+rdx*8+10h], eax
0x1400d9dc5  mov     rbp, [rsp+88h+arg_8]
0x1400d9dcd  test    byte ptr [rbp+1Bh], 10h
0x1400d9dd1  jz      short loc_1400D9DE5
0x1400d9dd3  add     rsp, 48h
0x1400d9dd7  pop     r15
0x1400d9dd9  pop     r14
0x1400d9ddb  pop     r13
0x1400d9ddd  pop     r12
0x1400d9ddf  pop     rdi
0x1400d9de0  pop     rsi
0x1400d9de1  pop     rbp
0x1400d9de2  pop     rbx
0x1400d9de3  retn
0x1400d9de5  movzx   eax, [rsp+88h+arg_0]
0x1400d9ded  sub     ax, [rbp+16h]
0x1400d9df1  mov     r12, [rsp+88h+arg_18]
0x1400d9df9  ror     ax, 8
0x1400d9dfd  add     r12, 10h
0x1400d9e01  movzx   edx, ax
0x1400d9e04  movzx   eax, word ptr [rbp+14h]
0x1400d9e08  add     edx, eax
0x1400d9e0a  mov     r15d, edx
0x1400d9e0d  movzx   eax, dx
0x1400d9e10  shr     r15d, 10h
0x1400d9e14  add     r15d, eax
0x1400d9e17  test    rbx, rbx
0x1400d9e1a  jz      loc_1400DA21F
0x1400d9e20  mov     rcx, [rbx+50h]
0x1400d9e24  cmp     [rcx+1], sil
0x1400d9e28  jz      loc_1400DA79B
0x1400d9e2e  lea     r14, [rbx+50h]
0x1400d9e32  mov     rcx, [r14]
0x1400d9e35  mov     eax, [rcx+4]
0x1400d9e38  test    eax, eax
0x1400d9e3a  jz      loc_1400DA1FA
0x1400d9e40  mov     r8, [rbx+20h]
0x1400d9e44  mov     ebp, [r8+8]
0x1400d9e48  cmp     ebp, [r8+0Ch]
0x1400d9e4c  jnb     loc_1400DA052
  ... truncated ...
```
