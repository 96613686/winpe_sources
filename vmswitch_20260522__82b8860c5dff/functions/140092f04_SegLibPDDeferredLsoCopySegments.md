# SegLibPDDeferredLsoCopySegments

- ea: `0x140092f04`
- end: `0x140093c10`
- name: `SegLibPDDeferredLsoCopySegments`
- size: `3340`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140092168`
- `0x140097d50`

## callees

- `0x140002ae8`
- `0x140006620`
- `0x1400095bc`
- `0x140060064`
- `0x140092f04`
- `0x1401bab6c`
- `0x1401bbb52`
- `0x1401bbc40`
- `0x1401bbcb0`
- `0x1401bbe10`
- `0x1401bbfc0`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140093068`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14009327c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14009352d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140093775`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140093aaa`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140093068`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14009327c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14009352d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140093775`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140093aaa`

## pseudocode

```c
_QWORD *__fastcall SegLibPDDeferredLsoCopySegments(__int64 a1, char *a2, __int64 a3, int a4, __int64 a5)
{
  char *v5; // r13
  __int64 v9; // rdx
  __int64 v10; // r14
  void *v11; // r10
  size_t v12; // r15
  __int64 v13; // rdi
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 v17; // rcx
  unsigned int v18; // eax
  _QWORD *result; // rax
  _DWORD *v20; // rdx
  unsigned int v21; // r13d
  _DWORD *v22; // rax
  int v23; // ecx
  __int64 v24; // r8
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // r8
  __int64 v28; // r9
  volatile signed __int32 *v29; // rcx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rax
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // rcx
  __int64 v38; // rdx
  char *v39; // r13
  void *v40; // r10
  size_t v41; // r15
  __int64 v42; // rcx
  __int64 v43; // r8
  __int64 v44; // rax
  unsigned int v45; // eax
  _DWORD *v46; // rdx
  unsigned int v47; // r12d
  _DWORD *v48; // rax
  int v49; // ecx
  __int64 v50; // r8
  __int64 v51; // rcx
  __int64 v52; // rax
  __int64 v53; // r8
  __int64 v54; // r9
  volatile signed __int32 *v55; // rcx
  __int64 v56; // r8
  __int64 v57; // r9
  __int64 v58; // rax
  __int64 v59; // r8
  __int64 v60; // rcx
  __int64 v61; // r8
  __int64 v62; // rcx
  bool v63; // zf
  __int64 v64; // rdi
  __int64 v65; // r15
  __int64 v66; // rax
  __int64 v67; // r8
  unsigned __int64 v68; // rcx
  __int64 v69; // rax
  void *v70; // rsp
  __int64 v71; // rdx
  __int64 v72; // r8
  size_t v73; // r12
  void *v74; // r9
  __int64 v75; // rax
  unsigned int v76; // eax
  void *v77; // r8
  _QWORD *v78; // rdx
  unsigned int v79; // r14d
  _DWORD *v80; // rax
  int v81; // ecx
  __int64 v82; // rax
  __int64 v83; // r8
  volatile signed __int32 *v84; // rcx
  __int64 v85; // r8
  __int64 v86; // rax
  __int64 v87; // r8
  __int64 v88; // rcx
  __int64 v89; // r8
  __int64 v90; // rcx
  __int64 v91; // rax
  __int64 v92; // r14
  char *v93; // r12
  void *v94; // r10
  size_t v95; // r14
  __int64 v96; // rcx
  __int64 v97; // r8
  __int64 v98; // rax
  __int64 v99; // rcx
  unsigned int v100; // eax
  _DWORD *v101; // rdx
  int v102; // r12d
  unsigned int v103; // r14d
  _DWORD *v104; // rax
  int v105; // ecx
  __int64 v106; // r8
  __int64 v107; // rcx
  __int64 v108; // rax
  __int64 v109; // r8
  __int64 v110; // r9
  volatile signed __int32 *v111; // rcx
  __int64 v112; // r8
  __int64 v113; // r9
  __int64 v114; // rax
  __int64 v115; // r8
  __int64 v116; // r9
  __int64 v117; // rcx
  __int64 v118; // r8
  __int64 v119; // rcx
  __int64 v120; // rax
  __int64 v121; // rdx
  char *v122; // r14
  __int64 v123; // rax
  unsigned int v124; // r12d
  char *v125; // r11
  __int64 v126; // rcx
  __int64 v127; // rax
  unsigned int v128; // eax
  char v129; // r13
  __int16 *v130; // rdx
  __int16 *v131; // rdx
  __int16 v132; // cx
  __int16 v133; // cx
  __int16 v134; // cx
  __int16 v135; // cx
  __int16 v136; // ax
  __int16 v137; // ax
  _DWORD *v138; // rdx
  unsigned int v139; // r10d
  _DWORD *v140; // rax
  int v141; // ecx
  __int64 v142; // r8
  __int64 v143; // rcx
  __int64 v144; // rax
  __int64 v145; // r8
  __int64 v146; // r9
  volatile signed __int32 *v147; // rcx
  __int64 v148; // r8
  __int64 v149; // r9
  __int64 v150; // rax
  __int64 v151; // r8
  __int64 v152; // rcx
  __int64 v153; // r8
  __int64 v154; // rcx
  __int64 v155; // rax
  int v156; // ecx
  void *v157; // [rsp+30h] [rbp+0h] BYREF
  void *v158; // [rsp+38h] [rbp+8h]
  char *v159; // [rsp+40h] [rbp+10h]
  void *Src; // [rsp+48h] [rbp+18h]
  int v161; // [rsp+50h] [rbp+20h]
  __int64 v162; // [rsp+58h] [rbp+28h]
  char *v163; // [rsp+60h] [rbp+30h]
  __int64 v164; // [rsp+68h] [rbp+38h]
  unsigned __int16 *v165; // [rsp+70h] [rbp+40h]
  _QWORD v166[12]; // [rsp+80h] [rbp+50h] BYREF

  v5 = a2;
  v158 = a2;
  v164 = a3;
  LODWORD(Src) = a4;
  v162 = a5;
  memset(v166, 0, sizeof(v166));
  if ( *(_DWORD *)(a3 + 84) >= 0x1000u )
  {
    v161 = *(_DWORD *)a5 * a4;
    v165 = (unsigned __int16 *)&v5[*(unsigned __int8 *)(a5 + 26)];
    v63 = (*(_BYTE *)(a5 + 27) & 8) == 0;
    v163 = &v5[*(unsigned __int16 *)(a5 + 22)];
    if ( v63 )
    {
      v64 = 0;
      v65 = a1 + 80;
      v66 = *(_QWORD *)(a1 + 80);
      v67 = 4;
      if ( v66 && *(_BYTE *)(v66 + 48) )
        v67 = *(unsigned int *)(v66 + 16);
      v68 = 24LL * (unsigned int)v67;
      v69 = v68 + 15;
      if ( v68 + 15 < v68 )
        v69 = 0xFFFFFFFFFFFFFF0LL;
      v70 = alloca(v69 & 0xFFFFFFFFFFFFFFF0uLL);
      BLInitializeBatchOpContextFromContextEx(a1, &v157, v67, v166);
      v72 = v166[10];
      v73 = *(unsigned __int16 *)(a5 + 24);
      v159 = (char *)(a5 + 24);
      v74 = (void *)(*(_QWORD *)(v164 + 32) + *(unsigned __int16 *)(v164 + 58));
      v157 = v74;
      if ( *(_BYTE *)(v166[10] + 1LL) == 1 && !BYTE4(v166[0]) )
      {
        v75 = 0;
        BYTE4(v166[0]) = 1;
        if ( HIDWORD(v166[1]) != -1 )
        {
          v71 = *(_QWORD *)(v166[10] + 24LL);
          if ( v71 )
            v75 = v71 + 20LL * HIDWORD(v166[1]);
        }
        _InterlockedAdd16((volatile signed __int16 *)(v75 + 16), 1u);
        v72 = v166[10];
      }
      v76 = *(_DWORD *)(v72 + 4);
      if ( v76 )
      {
        v78 = (_QWORD *)v166[4];
        v79 = *(_DWORD *)(v166[4] + 8LL);
        if ( v79 >= *(_DWORD *)(v166[4] + 12LL) )
        {
          v79 = 0;
          if ( LODWORD(v166[2]) < v76
            && (v80 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v72 + 64)), (v78 = v80) != 0) )
          {
            *(_QWORD *)v80 = 0;
            v80[2] = 0;
            v81 = *(_DWORD *)(v166[10] + 8LL);
            *((_QWORD *)v80 + 2) = v80 + 6;
            v80[3] = v81;
            *(_QWORD *)v166[4] = v80;
            ++LODWORD(v166[2]);
            v166[4] = v80;
            if ( *(_BYTE *)(v166[10] + 1LL) == 1 )
            {
              v82 = 0;
              if ( HIDWORD(v166[1]) != -1 )
              {
                v83 = *(_QWORD *)(v166[10] + 24LL);
                if ( v83 )
                  v82 = v83 + 20LL * HIDWORD(v166[1]);
              }
              _InterlockedAdd16((volatile signed __int16 *)(v82 + 12), 1u);
              v84 = 0;
              if ( HIDWORD(v166[1]) != -1 )
              {
                v85 = *(_QWORD *)(v166[10] + 24LL);
                if ( v85 )
                  v84 = (volatile signed __int32 *)(v85 + 20LL * HIDWORD(v166[1]));
              }
              _InterlockedAdd(v84, 1u);
            }
          }
          else
          {
            LOBYTE(v78) = 1;
            BLFlushBatchOpContextEx(v166, v78, 0);
            v78 = &v166[7];
          }
          v74 = v157;
        }
        ++HIDWORD(v166[2]);
        ++*((_DWORD *)v78 + 2);
        if ( *(_BYTE *)(v166[10] + 1LL) == 1 )
        {
          v86 = 0;
          if ( HIDWORD(v166[1]) != -1 )
          {
            v87 = *(_QWORD *)(v166[10] + 24LL);
            if ( v87 )
              v86 = v87 + 20LL * HIDWORD(v166[1]);
          }
          _InterlockedAdd16((volatile signed __int16 *)(v86 + 14), 1u);
          v88 = 0;
          if ( HIDWORD(v166[1]) != -1 )
          {
            v89 = *(_QWORD *)(v166[10] + 24LL);
            if ( v89 )
              v88 = v89 + 20LL * HIDWORD(v166[1]);
          }
          _InterlockedAdd((volatile signed __int32 *)(v88 + 4), 1u);
        }
        v90 = 3LL * v79;
        v91 = v78[2];
        v77 = v158;
        *(_QWORD *)(v91 + 8 * v90) = v158;
        *(_DWORD *)(v91 + 8 * v90 + 16) = (16 * v73) | 1;
        *(_QWORD *)(v91 + 8 * v90 + 8) = v74;
      }
      else
      {
        if ( HIDWORD(v166[2]) )
        {
          LOBYTE(v71) = 1;
          BLFlushBatchOpContextEx(v166, v71, 0);
          v72 = v166[10];
          v74 = v157;
        }
        if ( (v166[1] & 5) == 5 || (v166[1] & 6) == 6 )
        {
          (*(void (**)(void))(v72 + 32))();
          memmove(v158, v157, v73);
          (*(void (**)(void))(v166[10] + 40LL))();
        }
        else
        {
          memmove(v158, v74, v73);
        }
      }
      LOBYTE(v77) = 1;
      BLFlushBatchOpContextEx(v166, 0, v77);
      v92 = v162;
      SegLibPvtParseHeaders(v162, v165, v163);
      v93 = v159;
      goto LABEL_155;
    }
    v93 = (char *)(a5 + 24);
    v94 = (void *)(*(_QWORD *)(a3 + 32) + *(unsigned __int16 *)(a3 + 58));
    v95 = *(unsigned __int16 *)(a5 + 24);
    v64 = 0;
    v159 = (char *)(a5 + 24);
    v157 = v94;
    if ( a1 )
    {
      v96 = *(_QWORD *)(a1 + 80);
      if ( *(_BYTE *)(v96 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
      {
        v97 = *(unsigned int *)(a1 + 12);
        v98 = 0;
        *(_BYTE *)(a1 + 4) = 1;
        if ( (_DWORD)v97 != -1 )
        {
          v9 = *(_QWORD *)(v96 + 24);
          if ( v9 )
            v98 = v9 + 20 * v97;
        }
        _InterlockedAdd16((volatile signed __int16 *)(v98 + 16), 1u);
      }
      v65 = a1 + 80;
      v99 = *(_QWORD *)(a1 + 80);
      v100 = *(_DWORD *)(v99 + 4);
      if ( v100 )
      {
        v101 = *(_DWORD **)(a1 + 32);
        v102 = v95;
        v103 = v101[2];
        if ( v103 >= v101[3] )
        {
          v103 = 0;
          if ( *(_DWORD *)(a1 + 16) < v100
            && (v104 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v99 + 64)), (v101 = v104) != 0) )
          {
            *(_QWORD *)v104 = 0;
            v104[2] = 0;
            v105 = *(_DWORD *)(*(_QWORD *)v65 + 8LL);
            *((_QWORD *)v104 + 2) = v104 + 6;
            v104[3] = v105;
            **(_QWORD **)(a1 + 32) = v104;
            v106 = *(_QWORD *)v65;
            ++*(_DWORD *)(a1 + 16);
            *(_QWORD *)(a1 + 32) = v104;
            if ( *(_BYTE *)(v106 + 1) == 1 )
            {
              v107 = *(unsigned int *)(a1 + 12);
              v108 = 0;
              if ( (_DWORD)v107 != -1 )
              {
                v109 = *(_QWORD *)(v106 + 24);
                if ( v109 )
                  v108 = v109 + 20 * v107;
              }
              _InterlockedAdd16((volatile signed __int16 *)(v108 + 12), 1u);
              v110 = *(unsigned int *)(a1 + 12);
              v111 = 0;
              if ( (_DWORD)v110 != -1 )
              {
                v112 = *(_QWORD *)(*(_QWORD *)v65 + 24LL);
                if ( v112 )
                  v111 = (volatile signed __int32 *)(v112 + 20 * v110);
              }
              _InterlockedAdd(v111, 1u);
            }
          }
          else
          {
            LOBYTE(v101) = 1;
            BLFlushBatchOpContextEx(a1, v101, 0);
            v101 = (_DWORD *)(a1 + 56);
          }
          v94 = v157;
        }
        ++*(_DWORD *)(a1 + 20);
        ++v101[2];
        if ( *(_BYTE *)(*(_QWORD *)v65 + 1LL) == 1 )
        {
          v113 = *(unsigned int *)(a1 + 12);
          v114 = 0;
          if ( (_DWORD)v113 != -1 )
          {
            v115 = *(_QWORD *)(*(_QWORD *)v65 + 24LL);
            if ( v115 )
              v114 = v115 + 20 * v113;
          }
          _InterlockedAdd16((volatile signed __int16 *)(v114 + 14), 1u);
          v116 = *(unsigned int *)(a1 + 12);
          v117 = 0;
          if ( (_DWORD)v116 != -1 )
          {
            v118 = *(_QWORD *)(*(_QWORD *)v65 + 24LL);
            if ( v118 )
              v117 = v118 + 20 * v116;
          }
          _InterlockedAdd((volatile signed __int32 *)(v117 + 4), 1u);
        }
        v119 = 3LL * v103;
        v120 = *((_QWORD *)v101 + 2);
        *(_QWORD *)(v120 + 8 * v119) = v158;
        *(_DWORD *)(v120 + 8 * v119 + 16) = (16 * v102) | 1;
        v93 = v159;
        *(_QWORD *)(v120 + 8 * v119 + 8) = v94;
        goto LABEL_154;
      }
      if ( *(_DWORD *)(a1 + 20) )
      {
        LOBYTE(v9) = 1;
        BLFlushBatchOpContextEx(a1, v9, 0);
        v94 = v157;
      }
      if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (*(_BYTE *)(a1 + 8) & 6) == 6 )
      {
        (*(void (**)(void))(*(_QWORD *)v65 + 32LL))();
        memmove(v158, v157, v95);
        (*(void (**)(void))(*(_QWORD *)v65 + 40LL))();
LABEL_154:
        v92 = v162;
LABEL_155:
        SegLibPvtLsoDeferredFixHeaders(a1, v92, v165, (__int64)v163, (int)Src, v161);
        v121 = *(_QWORD *)v65;
        v122 = v163 + 16;
        v123 = *(unsigned __int16 *)(v162 + 22);
        v124 = *(unsigned __int16 *)v93 - (_DWORD)v123;
        v125 = (char *)v158 + v123;
        v159 = (char *)v158 + v123;
        if ( *(_BYTE *)(v121 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
        {
          v126 = *(unsigned int *)(a1 + 12);
          v127 = 0;
          *(_BYTE *)(a1 + 4) = 1;
          if ( (_DWORD)v126 != -1 )
          {
            v121 = *(_QWORD *)(v121 + 24);
            if ( v121 )
              v127 = v121 + 20 * v126;
          }
          _InterlockedAdd16((volatile signed __int16 *)(v127 + 16), 1u);
        }
        v128 = *(_DWORD *)(*(_QWORD *)v65 + 4LL);
        if ( v128 )
        {
          v138 = *(_DWORD **)(a1 + 32);
          v139 = v138[2];
          if ( v139 >= v138[3] )
          {
            if ( *(_DWORD *)(a1 + 16) < v128
              && (v140 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)v65 + 64LL)),
                  (v138 = v140) != 0) )
            {
              *(_QWORD *)v140 = 0;
              v140[2] = 0;
              v141 = *(_DWORD *)(*(_QWORD *)v65 + 8LL);
              *((_QWORD *)v140 + 2) = v140 + 6;
              v140[3] = v141;
              **(_QWORD **)(a1 + 32) = v140;
              v142 = *(_QWORD *)v65;
              ++*(_DWORD *)(a1 + 16);
              *(_QWORD *)(a1 + 32) = v140;
              if ( *(_BYTE *)(v142 + 1) == 1 )
              {
                v143 = *(unsigned int *)(a1 + 12);
                v144 = 0;
                if ( (_DWORD)v143 != -1 )
                {
                  v145 = *(_QWORD *)(v142 + 24);
                  if ( v145 )
                    v144 = v145 + 20 * v143;
                }
                _InterlockedAdd16((volatile signed __int16 *)(v144 + 12), 1u);
                v146 = *(unsigned int *)(a1 + 12);
                v147 = 0;
                if ( (_DWORD)v146 != -1 )
                {
                  v148 = *(_QWORD *)(*(_QWORD *)v65 + 24LL);
                  if ( v148 )
                    v147 = (volatile signed __int32 *)(v148 + 20 * v146);
                }
                _InterlockedAdd(v147, 1u);
              }
            }
            else
            {
              LOBYTE(v138) = 1;
              BLFlushBatchOpContextEx(a1, v138, 0);
              v138 = (_DWORD *)(a1 + 56);
            }
            v125 = v159;
            v139 = 0;
          }
          ++*(_DWORD *)(a1 + 20);
          ++v138[2];
          if ( *(_BYTE *)(*(_QWORD *)v65 + 1LL) == 1 )
          {
            v149 = *(unsigned int *)(a1 + 12);
            v150 = 0;
            if ( (_DWORD)v149 != -1 )
            {
              v151 = *(_QWORD *)(*(_QWORD *)v65 + 24LL);
              if ( v151 )
                v150 = v151 + 20 * v149;
            }
            _InterlockedAdd16((volatile signed __int16 *)(v150 + 14), 1u);
            v152 = *(unsigned int *)(a1 + 12);
            if ( (_DWORD)v152 != -1 )
            {
              v153 = *(_QWORD *)(*(_QWORD *)v65 + 24LL);
              if ( v153 )
                v64 = v153 + 20 * v152;
            }
            _InterlockedAdd((volatile signed __int32 *)(v64 + 4), 1u);
          }
          v154 = 3LL * v139;
          v155 = *((_QWORD *)v138 + 2);
          *(_QWORD *)(v155 + 8 * v154 + 8) = v125;
          *(_DWORD *)(v155 + 8 * v154 + 16) = (16 * v124) | 6;
          *(_QWORD *)(v155 + 8 * v154) = v122;
        }
        else
        {
          if ( *(_DWORD *)(a1 + 20) )
          {
            LOBYTE(v121) = 1;
            BLFlushBatchOpContextEx(a1, v121, 0);
          }
          if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (v129 = 0, (*(_DWORD *)(a1 + 8) & 6) == 6) )
            v129 = 1;
          v130 = *(__int16 **)(a1 + 48);
          if ( v130 && v130 != (__int16 *)v122 )
          {
            if ( v129 )
            {
              (*(void (**)(void))(*(_QWORD *)v65 + 32LL))();
              v131 = *(__int16 **)(a1 + 48);
              v132 = *v131;
              if ( (*(_DWORD *)(a1 + 44) & 1) != 0 )
                v132 = __ROR2__(v132, 8);
              v133 = ~v132;
              if ( *(_BYTE *)(a1 + 40) && !v133 )
                v133 = -1;
              *v131 = v133;
              *(_QWORD *)(a1 + 48) = 0;
              *(_DWORD *)(a1 + 44) = 0;
              (*(void (**)(void))(*(_QWORD *)v65 + 40LL))();
            }
            else
            {
              v134 = *v130;
              if ( (*(_DWORD *)(a1 + 44) & 1) != 0 )
                v134 = __ROR2__(v134, 8);
              v135 = ~v134;
              if ( *(_BYTE *)(a1 + 40) && !v135 )
                v135 = -1;
              *v130 = v135;
              *(_DWORD *)(a1 + 44) = 0;
            }
          }
          *(_BYTE *)(a1 + 40) = 0;
          *(_QWORD *)(a1 + 48) = v122;
          if ( v129 )
          {
            (*(void (**)(void))(*(_QWORD *)v65 + 32LL))();
            if ( v122 < v159 || v122 >= &v159[v124] )
              LOWORD(v64) = *(_WORD *)v122;
            v136 = tcpxsum((unsigned __int16)v64, v159, v124);
            *(_WORD *)v122 = v136;
            if ( (v124 & 1) != 0 )
            {
              *(_WORD *)v122 = __ROR2__(v136, 8);
              ++*(_DWORD *)(a1 + 44);
            }
            (*(void (**)(void))(*(_QWORD *)v65 + 40LL))();
          }
          else
          {
            if ( v122 < v159 || v122 >= &v159[v124] )
              LOWORD(v64) = *(_WORD *)v122;
            v137 = tcpxsum((unsigned __int16)v64, v159, v124);
            *(_WORD *)v122 = v137;
            if ( (v124 & 1) != 0 )
            {
              *(_WORD *)v122 = __ROR2__(v137, 8);
              ++*(_DWORD *)(a1 + 44);
            }
          }
        }
        if ( (_DWORD)Src == *(_DWORD *)(v162 + 8) )
          v156 = *(_DWORD *)(v162 + 4) - v161;
        else
          v156 = *(_DWORD *)v162;
        return (_QWORD *)SegLibPDDeferredTcpChecksumAndCopyBuffer(
                           a1,
                           (char *)v158 + *(unsigned __int16 *)(v162 + 24),
                           v164,
                           v161 + (unsigned int)*(unsigned __int16 *)(v162 + 24),
                           v156,
                           v163 + 16);
      }
    }
    else
    {
      v65 = 80;
    }
    memmove(v158, v94, v95);
    goto LABEL_154;
  }
  v10 = a1 + 80;
  v11 = (void *)(*(_QWORD *)(a3 + 32) + *(unsigned __int16 *)(a3 + 58));
  v12 = *(unsigned int *)(a3 + 60);
  v13 = 0;
  Src = v11;
  if ( !a1 )
    goto LABEL_37;
  v14 = *(_QWORD *)v10;
  if ( *(_BYTE *)(*(_QWORD *)v10 + 1LL) == 1 && !*(_BYTE *)(a1 + 4) )
  {
    v15 = *(unsigned int *)(a1 + 12);
    v16 = 0;
    *(_BYTE *)(a1 + 4) = 1;
    if ( (_DWORD)v15 != -1 )
    {
      v9 = *(_QWORD *)(v14 + 24);
      if ( v9 )
        v16 = v9 + 20 * v15;
    }
    _InterlockedAdd16((volatile signed __int16 *)(v16 + 16), 1u);
  }
  v10 = a1 + 80;
  v17 = *(_QWORD *)(a1 + 80);
  v18 = *(_DWORD *)(v17 + 4);
  if ( v18 )
  {
    v20 = *(_DWORD **)(a1 + 32);
    v21 = v20[2];
    if ( v21 >= v20[3] )
    {
      v21 = 0;
      if ( *(_DWORD *)(a1 + 16) < v18
        && (v22 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v17 + 64)), (v20 = v22) != 0) )
      {
        *(_QWORD *)v22 = 0;
        v22[2] = 0;
        v23 = *(_DWORD *)(*(_QWORD *)v10 + 8LL);
        *((_QWORD *)v22 + 2) = v22 + 6;
        v22[3] = v23;
        **(_QWORD **)(a1 + 32) = v22;
        v24 = *(_QWORD *)v10;
        ++*(_DWORD *)(a1 + 16);
        *(_QWORD *)(a1 + 32) = v22;
        if ( *(_BYTE *)(v24 + 1) == 1 )
        {
          v25 = *(unsigned int *)(a1 + 12);
          v26 = 0;
          if ( (_DWORD)v25 != -1 )
          {
            v27 = *(_QWORD *)(v24 + 24);
            if ( v27 )
              v26 = v27 + 20 * v25;
          }
          _InterlockedAdd16((volatile signed __int16 *)(v26 + 12), 1u);
          v28 = *(unsigned int *)(a1 + 12);
          v29 = 0;
          if ( (_DWORD)v28 != -1 )
          {
            v30 = *(_QWORD *)(*(_QWORD *)v10 + 24LL);
            if ( v30 )
              v29 = (volatile signed __int32 *)(v30 + 20 * v28);
          }
          _InterlockedAdd(v29, 1u);
        }
      }
      else
      {
        LOBYTE(v20) = 1;
        BLFlushBatchOpContextEx(a1, v20, 0);
        v20 = (_DWORD *)(a1 + 56);
      }
      v11 = Src;
    }
    ++*(_DWORD *)(a1 + 20);
    ++v20[2];
    if ( *(_BYTE *)(*(_QWORD *)v10 + 1LL) == 1 )
    {
      v31 = *(unsigned int *)(a1 + 12);
      v32 = 0;
      if ( (_DWORD)v31 != -1 )
      {
        v33 = *(_QWORD *)(*(_QWORD *)v10 + 24LL);
        if ( v33 )
          v32 = v33 + 20 * v31;
      }
      _InterlockedAdd16((volatile signed __int16 *)(v32 + 14), 1u);
      v34 = *(unsigned int *)(a1 + 12);
      v35 = 0;
      if ( (_DWORD)v34 != -1 )
      {
        v36 = *(_QWORD *)(*(_QWORD *)v10 + 24LL);
        if ( v36 )
          v35 = v36 + 20 * v34;
      }
      _InterlockedAdd((volatile signed __int32 *)(v35 + 4), 1u);
    }
    v37 = 3LL * v21;
    result = (_QWORD *)*((_QWORD *)v20 + 2);
    v5 = (char *)v158;
    result[v37] = v158;
    LODWORD(result[v37 + 2]) = (16 * v12) | 1;
    result[v37 + 1] = v11;
    goto LABEL_38;
  }
  if ( *(_DWORD *)(a1 + 20) )
  {
    LOBYTE(v9) = 1;
    BLFlushBatchOpContextEx(a1, v9, 0);
    v11 = Src;
  }
  if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (*(_BYTE *)(a1 + 8) & 6) == 6 )
  {
    (*(void (**)(void))(*(_QWORD *)v10 + 32LL))();
    memmove(v5, Src, v12);
    result = (_QWORD *)(*(__int64 (**)(void))(*(_QWORD *)v10 + 40LL))();
  }
  else
  {
LABEL_37:
    result = memmove(v5, v11, v12);
  }
LABEL_38:
  v38 = *(_QWORD *)(v164 + 8);
  if ( !v38 )
    return result;
  v39 = &v5[*(unsigned int *)(v164 + 60)];
  v40 = (void *)(*(_QWORD *)(v38 + 32) + *(unsigned __int16 *)(v38 + 58));
  v41 = *(unsigned int *)(v38 + 60);
  v158 = v40;
  if ( !a1 )
    return memmove(v39, v40, v41);
  v42 = *(_QWORD *)v10;
  if ( *(_BYTE *)(*(_QWORD *)v10 + 1LL) == 1 && !*(_BYTE *)(a1 + 4) )
  {
    v43 = *(unsigned int *)(a1 + 12);
    v44 = 0;
    *(_BYTE *)(a1 + 4) = 1;
    if ( (_DWORD)v43 != -1 )
    {
      v38 = *(_QWORD *)(v42 + 24);
      if ( v38 )
        v44 = v38 + 20 * v43;
    }
    _InterlockedAdd16((volatile signed __int16 *)(v44 + 16), 1u);
  }
  v45 = *(_DWORD *)(*(_QWORD *)v10 + 4LL);
  if ( !v45 )
  {
    if ( *(_DWORD *)(a1 + 20) )
    {
      LOBYTE(v38) = 1;
      BLFlushBatchOpContextEx(a1, v38, 0);
      v40 = v158;
    }
    if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (*(_BYTE *)(a1 + 8) & 6) == 6 )
    {
      (*(void (**)(void))(*(_QWORD *)v10 + 32LL))();
      memmove(v39, v158, v41);
      return (_QWORD *)(*(__int64 (**)(void))(*(_QWORD *)v10 + 40LL))();
    }
    return memmove(v39, v40, v41);
  }
  v46 = *(_DWORD **)(a1 + 32);
  v47 = v46[2];
  if ( v47 >= v46[3] )
  {
    v47 = 0;
    if ( *(_DWORD *)(a1 + 16) < v45
      && (v48 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)v10 + 64LL)), (v46 = v48) != 0) )
    {
      *(_QWORD *)v48 = 0;
      v48[2] = 0;
      v49 = *(_DWORD *)(*(_QWORD *)v10 + 8LL);
      *((_QWORD *)v48 + 2) = v48 + 6;
      v48[3] = v49;
      **(_QWORD **)(a1 + 32) = v48;
      v50 = *(_QWORD *)v10;
      ++*(_DWORD *)(a1 + 16);
      *(_QWORD *)(a1 + 32) = v48;
      if ( *(_BYTE *)(v50 + 1) == 1 )
      {
        v51 = *(unsigned int *)(a1 + 12);
        v52 = 0;
        if ( (_DWORD)v51 != -1 )
        {
          v53 = *(_QWORD *)(v50 + 24);
          if ( v53 )
            v52 = v53 + 20 * v51;
        }
        _InterlockedAdd16((volatile signed __int16 *)(v52 + 12), 1u);
        v54 = *(unsigned int *)(a1 + 12);
        v55 = 0;
        if ( (_DWORD)v54 != -1 )
        {
          v56 = *(_QWORD *)(*(_QWORD *)v10 + 24LL);
          if ( v56 )
            v55 = (volatile signed __int32 *)(v56 + 20 * v54);
        }
        _InterlockedAdd(v55, 1u);
      }
    }
    else
    {
      LOBYTE(v46) = 1;
      BLFlushBatchOpContextEx(a1, v46, 0);
      v46 = (_DWORD *)(a1 + 56);
    }
    v40 = v158;
  }
  ++*(_DWORD *)(a1 + 20);
  ++v46[2];
  if ( *(_BYTE *)(*(_QWORD *)v10 + 1LL) == 1 )
  {
    v57 = *(unsigned int *)(a1 + 12);
    v58 = 0;
    if ( (_DWORD)v57 != -1 )
    {
      v59 = *(_QWORD *)(*(_QWORD *)v10 + 24LL);
      if ( v59 )
        v58 = v59 + 20 * v57;
    }
    _InterlockedAdd16((volatile signed __int16 *)(v58 + 14), 1u);
    v60 = *(unsigned int *)(a1 + 12);
    if ( (_DWORD)v60 != -1 )
    {
      v61 = *(_QWORD *)(*(_QWORD *)v10 + 24LL);
      if ( v61 )
        v13 = v61 + 20 * v60;
    }
    _InterlockedAdd((volatile signed __int32 *)(v13 + 4), 1u);
  }
  v62 = 3LL * v47;
  result = (_QWORD *)*((_QWORD *)v46 + 2);
  result[v62] = v39;
  LODWORD(result[v62 + 2]) = (16 * v41) | 1;
  result[v62 + 1] = v40;
  return result;
}

```

## disassembly

```asm
0x140092f04  push    rbp
0x140092f06  push    rbx
0x140092f07  push    rsi
0x140092f08  push    rdi
0x140092f09  push    r12
0x140092f0b  push    r13
0x140092f0d  push    r14
0x140092f0f  push    r15
0x140092f11  sub     rsp, 0F8h
0x140092f18  lea     rbp, [rsp+30h]
0x140092f1d  mov     rax, cs:__security_cookie
0x140092f24  xor     rax, rbp
0x140092f27  mov     [rbp+100h+var_50], rax
0x140092f2e  mov     rsi, [rbp+100h+arg_20]
0x140092f35  mov     r13, rdx
0x140092f38  mov     [rbp+100h+var_F8], rdx
0x140092f3c  mov     rdi, r8
0x140092f3f  xor     edx, edx; Val
0x140092f41  mov     [rbp+100h+var_C8], r8
0x140092f45  mov     rbx, rcx
0x140092f48  mov     dword ptr [rbp+100h+Src], r9d
0x140092f4c  lea     rcx, [rbp+100h+var_B0]; void *
0x140092f50  mov     [rbp+100h+var_D8], rsi
0x140092f54  mov     r14d, r9d
0x140092f57  lea     r8d, [rdx+60h]; Size
0x140092f5b  call    memset
0x140092f60  cmp     dword ptr [rdi+54h], 1000h
0x140092f67  jnb     loc_140093391
0x140092f6d  movzx   r10d, word ptr [rdi+3Ah]
0x140092f72  lea     r14, [rbx+50h]
0x140092f76  add     r10, [rdi+20h]
0x140092f7a  or      r12d, 0FFFFFFFFh
0x140092f7e  mov     r15d, [rdi+3Ch]
0x140092f82  mov     esi, 1
0x140092f87  xor     edi, edi
0x140092f89  mov     [rbp+100h+Src], r10
0x140092f8d  test    rbx, rbx
0x140092f90  jz      loc_14009316D
0x140092f96  mov     rcx, [r14]
0x140092f99  cmp     [rcx+1], sil
0x140092f9d  jnz     short loc_140092FCA
0x140092f9f  cmp     [rbx+4], dil
0x140092fa3  jnz     short loc_140092FCA
0x140092fa5  mov     r8d, [rbx+0Ch]
0x140092fa9  mov     eax, edi
0x140092fab  mov     [rbx+4], sil
0x140092faf  cmp     r8d, r12d
0x140092fb2  jz      short loc_140092FC5
0x140092fb4  mov     rdx, [rcx+18h]
0x140092fb8  test    rdx, rdx
0x140092fbb  jz      short loc_140092FC5
0x140092fbd  lea     rcx, [r8+r8*4]
0x140092fc1  lea     rax, [rdx+rcx*4]
0x140092fc5  lock add [rax+10h], si
0x140092fca  lea     r14, [rbx+50h]
0x140092fce  mov     rcx, [r14]
0x140092fd1  mov     eax, [rcx+4]
0x140092fd4  test    eax, eax
0x140092fd6  jnz     short loc_140093033
0x140092fd8  cmp     [rbx+14h], edi
0x140092fdb  jz      short loc_140092FEF
0x140092fdd  xor     r8d, r8d
0x140092fe0  mov     dl, sil
0x140092fe3  mov     rcx, rbx
0x140092fe6  call    BLFlushBatchOpContextEx
0x140092feb  mov     r10, [rbp+100h+Src]
0x140092fef  mov     eax, [rbx+8]
0x140092ff2  and     eax, 5
0x140092ff5  cmp     al, 5
0x140092ff7  jz      short loc_140093007
0x140092ff9  mov     eax, [rbx+8]
0x140092ffc  and     eax, 6
0x140092fff  cmp     al, 6
0x140093001  jnz     loc_14009316D
0x140093007  mov     rax, [r14]
0x14009300a  mov     rax, [rax+20h]
0x14009300e  call    _guard_dispatch_icall
0x140093013  mov     rdx, [rbp+100h+Src]; Src
0x140093017  mov     r8, r15; Size
0x14009301a  mov     rcx, r13; void *
0x14009301d  call    memmove
0x140093022  mov     rax, [r14]
0x140093025  mov     rax, [rax+28h]
0x140093029  call    _guard_dispatch_icall
0x14009302e  jmp     loc_14009317B
0x140093033  mov     rdx, [rbx+20h]
0x140093037  mov     r13d, [rdx+8]
0x14009303b  cmp     r13d, [rdx+0Ch]
0x14009303f  jb      loc_1400930F2
0x140093045  mov     r13d, edi
0x140093048  cmp     [rbx+10h], eax
0x14009304b  jb      short loc_140093064
0x14009304d  xor     r8d, r8d
0x140093050  mov     dl, sil
0x140093053  mov     rcx, rbx
0x140093056  call    BLFlushBatchOpContextEx
0x14009305b  lea     rdx, [rbx+38h]
0x14009305f  jmp     loc_1400930EE
0x140093064  add     rcx, 40h ; '@'; Lookaside
0x140093068  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14009306f  nop     dword ptr [rax+rax+00h]
0x140093074  mov     rdx, rax
0x140093077  test    rax, rax
0x14009307a  jz      short loc_14009304D
0x14009307c  mov     [rax], rdi
0x14009307f  mov     [rax+8], edi
0x140093082  mov     rax, [r14]
0x140093085  mov     ecx, [rax+8]
0x140093088  lea     rax, [rdx+18h]
0x14009308c  mov     [rdx+10h], rax
0x140093090  mov     [rdx+0Ch], ecx
0x140093093  mov     rax, [rbx+20h]
0x140093097  mov     [rax], rdx
0x14009309a  mov     r8, [r14]
0x14009309d  add     [rbx+10h], esi
0x1400930a0  mov     [rbx+20h], rdx
0x1400930a4  cmp     [r8+1], sil
0x1400930a8  jnz     short loc_1400930EE
0x1400930aa  mov     ecx, [rbx+0Ch]
0x1400930ad  mov     rax, rdi
0x1400930b0  cmp     ecx, r12d
0x1400930b3  jz      short loc_1400930C6
0x1400930b5  mov     r8, [r8+18h]
0x1400930b9  test    r8, r8
0x1400930bc  jz      short loc_1400930C6
0x1400930be  lea     rcx, [rcx+rcx*4]
0x1400930c2  lea     rax, [r8+rcx*4]
0x1400930c6  lock add [rax+0Ch], si
0x1400930cb  mov     r9d, [rbx+0Ch]
0x1400930cf  mov     rcx, rdi
0x1400930d2  cmp     r9d, r12d
0x1400930d5  jz      short loc_1400930EB
0x1400930d7  mov     rax, [r14]
0x1400930da  mov     r8, [rax+18h]
0x1400930de  test    r8, r8
0x1400930e1  jz      short loc_1400930EB
0x1400930e3  lea     rcx, [r9+r9*4]
0x1400930e7  lea     rcx, [r8+rcx*4]
0x1400930eb  lock add [rcx], esi
0x1400930ee  mov     r10, [rbp+100h+Src]
0x1400930f2  add     [rbx+14h], esi
0x1400930f5  add     [rdx+8], esi
0x1400930f8  mov     rcx, [r14]
0x1400930fb  cmp     [rcx+1], sil
0x1400930ff  jnz     short loc_140093147
0x140093101  mov     r9d, [rbx+0Ch]
0x140093105  mov     rax, rdi
0x140093108  cmp     r9d, r12d
0x14009310b  jz      short loc_14009311E
0x14009310d  mov     r8, [rcx+18h]
0x140093111  test    r8, r8
0x140093114  jz      short loc_14009311E
0x140093116  lea     rcx, [r9+r9*4]
0x14009311a  lea     rax, [r8+rcx*4]
0x14009311e  lock add [rax+0Eh], si
0x140093123  mov     r9d, [rbx+0Ch]
0x140093127  mov     rcx, rdi
0x14009312a  cmp     r9d, r12d
0x14009312d  jz      short loc_140093143
0x14009312f  mov     rax, [r14]
0x140093132  mov     r8, [rax+18h]
0x140093136  test    r8, r8
0x140093139  jz      short loc_140093143
0x14009313b  lea     rcx, [r9+r9*4]
0x14009313f  lea     rcx, [r8+rcx*4]
0x140093143  lock add [rcx+4], esi
0x140093147  mov     eax, r13d
0x14009314a  lea     rcx, [rax+rax*2]
0x14009314e  mov     rax, [rdx+10h]
0x140093152  mov     r13, [rbp+100h+var_F8]
0x140093156  shl     r15d, 4
0x14009315a  or      r15d, esi
0x14009315d  mov     [rax+rcx*8], r13
0x140093161  mov     [rax+rcx*8+10h], r15d
0x140093166  mov     [rax+rcx*8+8], r10
0x14009316b  jmp     short loc_14009317B
0x14009316d  mov     r8, r15; Size
0x140093170  mov     rdx, r10; Src
0x140093173  mov     rcx, r13; void *
0x140093176  call    memmove
0x14009317b  mov     r8, [rbp+100h+var_C8]
0x14009317f  mov     rdx, [r8+8]
0x140093183  test    rdx, rdx
0x140093186  jz      loc_140093BEC
0x14009318c  mov     eax, [r8+3Ch]
0x140093190  movzx   r10d, word ptr [rdx+3Ah]
0x140093195  add     r13, rax
0x140093198  add     r10, [rdx+20h]
0x14009319c  mov     r15d, [rdx+3Ch]
0x1400931a0  mov     [rbp+100h+var_F8], r10
0x1400931a4  test    rbx, rbx
0x1400931a7  jz      loc_14009337E
0x1400931ad  mov     rcx, [r14]
0x1400931b0  cmp     [rcx+1], sil
0x1400931b4  jnz     short loc_1400931E2
0x1400931b6  cmp     [rbx+4], dil
0x1400931ba  jnz     short loc_1400931E2
0x1400931bc  mov     r8d, [rbx+0Ch]
0x1400931c0  mov     rax, rdi
0x1400931c3  mov     [rbx+4], sil
0x1400931c7  cmp     r8d, r12d
0x1400931ca  jz      short loc_1400931DD
0x1400931cc  mov     rdx, [rcx+18h]
0x1400931d0  test    rdx, rdx
0x1400931d3  jz      short loc_1400931DD
0x1400931d5  lea     rcx, [r8+r8*4]
0x1400931d9  lea     rax, [rdx+rcx*4]
0x1400931dd  lock add [rax+10h], si
0x1400931e2  mov     rcx, [r14]
0x1400931e5  mov     eax, [rcx+4]
0x1400931e8  test    eax, eax
0x1400931ea  jnz     short loc_140093247
0x1400931ec  cmp     [rbx+14h], edi
0x1400931ef  jz      short loc_140093203
0x1400931f1  xor     r8d, r8d
0x1400931f4  mov     dl, sil
0x1400931f7  mov     rcx, rbx
0x1400931fa  call    BLFlushBatchOpContextEx
0x1400931ff  mov     r10, [rbp+100h+var_F8]
0x140093203  mov     eax, [rbx+8]
0x140093206  and     eax, 5
0x140093209  cmp     al, 5
0x14009320b  jz      short loc_14009321B
0x14009320d  mov     eax, [rbx+8]
0x140093210  and     eax, 6
0x140093213  cmp     al, 6
0x140093215  jnz     loc_14009337E
0x14009321b  mov     rax, [r14]
0x14009321e  mov     rax, [rax+20h]
0x140093222  call    _guard_dispatch_icall
0x140093227  mov     rdx, [rbp+100h+var_F8]; Src
0x14009322b  mov     r8, r15; Size
0x14009322e  mov     rcx, r13; void *
0x140093231  call    memmove
0x140093236  mov     rax, [r14]
0x140093239  mov     rax, [rax+28h]
0x14009323d  call    _guard_dispatch_icall
0x140093242  jmp     loc_140093BEC
0x140093247  mov     rdx, [rbx+20h]
0x14009324b  mov     r12d, [rdx+8]
0x14009324f  cmp     r12d, [rdx+0Ch]
0x140093253  jb      loc_140093307
0x140093259  mov     r12d, edi
0x14009325c  cmp     [rbx+10h], eax
0x14009325f  jb      short loc_140093278
0x140093261  xor     r8d, r8d
0x140093264  mov     dl, sil
0x140093267  mov     rcx, rbx
0x14009326a  call    BLFlushBatchOpContextEx
0x14009326f  lea     rdx, [rbx+38h]
0x140093273  jmp     loc_140093303
0x140093278  add     rcx, 40h ; '@'; Lookaside
0x14009327c  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140093283  nop     dword ptr [rax+rax+00h]
0x140093288  mov     rdx, rax
0x14009328b  test    rax, rax
0x14009328e  jz      short loc_140093261
0x140093290  mov     [rax], rdi
0x140093293  mov     [rax+8], edi
0x140093296  mov     rax, [r14]
0x140093299  mov     ecx, [rax+8]
0x14009329c  lea     rax, [rdx+18h]
0x1400932a0  mov     [rdx+10h], rax
0x1400932a4  mov     [rdx+0Ch], ecx
0x1400932a7  mov     rax, [rbx+20h]
0x1400932ab  mov     [rax], rdx
0x1400932ae  mov     r8, [r14]
0x1400932b1  add     [rbx+10h], esi
0x1400932b4  mov     [rbx+20h], rdx
0x1400932b8  cmp     [r8+1], sil
0x1400932bc  jnz     short loc_140093303
0x1400932be  mov     ecx, [rbx+0Ch]
0x1400932c1  mov     rax, rdi
0x1400932c4  cmp     ecx, 0FFFFFFFFh
0x1400932c7  jz      short loc_1400932DA
0x1400932c9  mov     r8, [r8+18h]
0x1400932cd  test    r8, r8
0x1400932d0  jz      short loc_1400932DA
0x1400932d2  lea     rcx, [rcx+rcx*4]
0x1400932d6  lea     rax, [r8+rcx*4]
0x1400932da  lock add [rax+0Ch], si
0x1400932df  mov     r9d, [rbx+0Ch]
0x1400932e3  mov     rcx, rdi
0x1400932e6  cmp     r9d, 0FFFFFFFFh
0x1400932ea  jz      short loc_140093300
0x1400932ec  mov     rax, [r14]
0x1400932ef  mov     r8, [rax+18h]
0x1400932f3  test    r8, r8
0x1400932f6  jz      short loc_140093300
0x1400932f8  lea     rcx, [r9+r9*4]
0x1400932fc  lea     rcx, [r8+rcx*4]
0x140093300  lock add [rcx], esi
0x140093303  mov     r10, [rbp+100h+var_F8]
0x140093307  add     [rbx+14h], esi
0x14009330a  add     [rdx+8], esi
0x14009330d  mov     rcx, [r14]
0x140093310  cmp     [rcx+1], sil
0x140093314  jnz     short loc_140093359
0x140093316  mov     r9d, [rbx+0Ch]
0x14009331a  mov     rax, rdi
  ... truncated ...
```
