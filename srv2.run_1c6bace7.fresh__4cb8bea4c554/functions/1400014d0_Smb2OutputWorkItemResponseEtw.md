# Smb2OutputWorkItemResponseEtw

- ea: `0x1400014d0`
- end: `0x140003098`
- name: `Smb2OutputWorkItemResponseEtw`
- size: `7112`
- prototype: ``
- caller_count: `3`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140006580`
- `0x140006ad0`
- `0x140008c40`

## callees

- `0x1400014d0`
- `0x1400030a0`
- `0x1400033cc`
- `0x140003744`
- `0x140004020`
- `0x14001d218`
- `0x14001d858`
- `0x14001db08`
- `0x14001e03c`
- `0x14001e2d0`
- `0x14001e720`
- `0x14001ea24`
- `0x140026294`
- `0x1400265c0`
- `0x1400268ec`
- `0x140026c00`
- `0x14002700c`
- `0x140038490`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140002dfb`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140002dfb`
- `HAL!KeQueryPerformanceCounter` at `0x140001566`
- `HAL!KeQueryPerformanceCounter` at `0x140002bb5`
- `HAL!KeQueryPerformanceCounter` at `0x140001566`
- `HAL!KeQueryPerformanceCounter` at `0x140002bb5`

## pseudocode

```c
__int64 __fastcall Smb2OutputWorkItemResponseEtw(__int64 a1)
{
  __int64 v1; // rax
  __int64 v3; // rsi
  bool v4; // zf
  __int64 v5; // rdi
  __int64 v6; // rax
  __int64 result; // rax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rax
  _QWORD *v12; // rcx
  __int64 *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rax
  _QWORD *v17; // rcx
  __int64 *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rax
  __int16 v22; // r12
  __int16 v23; // r14
  __int16 v24; // di
  __int16 v25; // r10
  _QWORD *v26; // rcx
  __int64 *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rax
  __int16 v31; // r12
  __int16 v32; // r14
  __int16 v33; // di
  __int16 v34; // r10
  int v35; // ecx
  __int64 *v36; // rdx
  _QWORD *v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rax
  __int16 v41; // r12
  __int16 v42; // r14
  __int16 v43; // di
  __int16 v44; // r10
  __int64 v45; // rcx
  __int64 v46; // rax
  __int64 *v47; // rax
  __int64 v48; // rax
  __int64 *v49; // rax
  __int64 v50; // rdx
  __int64 v51; // rcx
  __int64 v52; // rax
  _QWORD *v53; // rcx
  __int64 v54; // rdx
  __int64 v55; // rdx
  __int64 v56; // rax
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v58; // rax
  _QWORD *v59; // rcx
  __int64 v60; // rdx
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // rcx
  int v64; // r8d
  _QWORD *v65; // rcx
  __int64 v66; // rdx
  _QWORD *v67; // rcx
  __int64 v68; // rdx
  _QWORD *v69; // rcx
  __int64 v70; // rdx
  _QWORD *v71; // rcx
  __int64 v72; // rdx
  _QWORD *v73; // rcx
  __int64 v74; // rdx
  __int64 v75; // rdx
  __int64 v76; // rax
  __int64 v77; // rax
  __int16 v78; // r12
  __int16 v79; // r14
  __int16 v80; // di
  __int16 v81; // r10
  __int16 v82; // r8
  __int64 v83; // r13
  unsigned int *v84; // rdx
  __int64 v85; // rdx
  __int64 v86; // rdx
  __int64 v87; // rax
  __int64 v88; // rdx
  __int64 v89; // rax
  __int16 v90; // r12
  __int16 v91; // r14
  __int16 v92; // di
  __int16 v93; // r10
  __int16 v94; // r8
  __int64 v95; // rdx
  __int64 v96; // rax
  __int16 v97; // r12
  __int16 v98; // r14
  __int16 v99; // di
  __int16 v100; // r10
  __int64 v101; // rdx
  __int64 v102; // rax
  __int16 v103; // r12
  __int16 v104; // r14
  __int16 v105; // di
  __int16 v106; // r10
  __int64 v107; // rdx
  __int64 v108; // rax
  __int16 v109; // r12
  __int16 v110; // r14
  __int16 v111; // di
  __int16 v112; // r10
  __int64 v113; // rdx
  __int64 v114; // rax
  _QWORD *v115; // rcx
  __int64 v116; // rdx
  __int64 v117; // rdx
  __int64 v118; // rax
  __int16 v119; // r12
  __int16 v120; // r14
  __int16 v121; // di
  __int16 v122; // r10
  char v123; // [rsp+60h] [rbp-190h]
  __int16 v124; // [rsp+68h] [rbp-188h]
  __int64 v125; // [rsp+70h] [rbp-180h]
  char v126; // [rsp+78h] [rbp-178h]
  __int64 v127; // [rsp+80h] [rbp-170h]
  char v128; // [rsp+88h] [rbp-168h]
  __int64 v129; // [rsp+90h] [rbp-160h]
  char v130; // [rsp+98h] [rbp-158h]
  __int64 v131; // [rsp+A0h] [rbp-150h]
  char v132; // [rsp+A8h] [rbp-148h]
  __int64 v133; // [rsp+B0h] [rbp-140h]
  __int16 v134; // [rsp+B8h] [rbp-138h]
  __int64 v135; // [rsp+C0h] [rbp-130h]
  __int16 v136; // [rsp+C8h] [rbp-128h]
  __int64 v137; // [rsp+D0h] [rbp-120h]
  __int64 v138; // [rsp+D8h] [rbp-118h]
  __int64 v139; // [rsp+E0h] [rbp-110h]
  __int64 v140; // [rsp+E8h] [rbp-108h]
  __int64 v141; // [rsp+F0h] [rbp-100h]
  __int64 v142; // [rsp+F8h] [rbp-F8h]
  __int64 *v143; // [rsp+170h] [rbp-80h]
  __int64 *v144; // [rsp+170h] [rbp-80h]
  __int64 *v145; // [rsp+170h] [rbp-80h]
  __int64 *v146; // [rsp+170h] [rbp-80h]
  __int64 *v147; // [rsp+170h] [rbp-80h]
  __int64 *v148; // [rsp+170h] [rbp-80h]
  __int64 *v149; // [rsp+170h] [rbp-80h]
  __int64 *v150; // [rsp+170h] [rbp-80h]
  __int64 *v151; // [rsp+170h] [rbp-80h]
  __int64 *v152; // [rsp+170h] [rbp-80h]
  __int64 *v153; // [rsp+170h] [rbp-80h]
  __int64 *v154; // [rsp+170h] [rbp-80h]
  __int64 *v155; // [rsp+170h] [rbp-80h]
  __int64 *v156; // [rsp+170h] [rbp-80h]
  __int64 *v157; // [rsp+170h] [rbp-80h]
  __int64 *v158; // [rsp+170h] [rbp-80h]
  __int64 *v159; // [rsp+178h] [rbp-78h]
  __int64 v160; // [rsp+178h] [rbp-78h]
  __int64 v161; // [rsp+178h] [rbp-78h]
  __int64 *v162; // [rsp+178h] [rbp-78h]
  __int64 *v163; // [rsp+178h] [rbp-78h]
  __int64 *v164; // [rsp+178h] [rbp-78h]
  __int64 v165; // [rsp+178h] [rbp-78h]
  __int64 *v166; // [rsp+178h] [rbp-78h]
  __int64 *v167; // [rsp+178h] [rbp-78h]
  __int64 *v168; // [rsp+178h] [rbp-78h]
  __int64 *v169; // [rsp+178h] [rbp-78h]
  __int64 *v170; // [rsp+178h] [rbp-78h]
  __int64 *v171; // [rsp+178h] [rbp-78h]
  __int64 *v172; // [rsp+178h] [rbp-78h]
  __int64 *v173; // [rsp+180h] [rbp-70h]
  __int64 *v174; // [rsp+180h] [rbp-70h]
  __int64 *v175; // [rsp+180h] [rbp-70h]
  __int64 *v176; // [rsp+180h] [rbp-70h]
  __int64 *v177; // [rsp+180h] [rbp-70h]
  __int64 *v178; // [rsp+180h] [rbp-70h]
  __int64 *v179; // [rsp+180h] [rbp-70h]
  __int64 *v180; // [rsp+180h] [rbp-70h]
  __int64 *v181; // [rsp+180h] [rbp-70h]
  __int64 *v182; // [rsp+180h] [rbp-70h]
  __int64 *v183; // [rsp+180h] [rbp-70h]
  __int64 v184; // [rsp+180h] [rbp-70h]
  __int64 *v185; // [rsp+180h] [rbp-70h]
  __int64 *v186; // [rsp+180h] [rbp-70h]
  __int64 *v187; // [rsp+188h] [rbp-68h]
  __int64 *v188; // [rsp+188h] [rbp-68h]
  __int64 *v189; // [rsp+188h] [rbp-68h]
  char v190; // [rsp+190h] [rbp-60h]
  char v191; // [rsp+194h] [rbp-5Ch]
  int v192; // [rsp+198h] [rbp-58h]
  int v193; // [rsp+198h] [rbp-58h]
  __int64 *v194; // [rsp+198h] [rbp-58h]
  __int64 v195; // [rsp+198h] [rbp-58h]
  int v196; // [rsp+198h] [rbp-58h]
  __int64 v197; // [rsp+1A0h] [rbp-50h]
  __int64 v198; // [rsp+1A8h] [rbp-48h]
  __int64 v199; // [rsp+1B0h] [rbp-40h]
  __int16 v200; // [rsp+1B0h] [rbp-40h]
  _LARGE_INTEGER PerformanceFrequency; // [rsp+1B8h] [rbp-38h] BYREF
  __int64 v202; // [rsp+1C0h] [rbp-30h]
  __int64 v203; // [rsp+1C8h] [rbp-28h]
  __int64 v204; // [rsp+1D0h] [rbp-20h]
  __int64 v205; // [rsp+1D8h] [rbp-18h]
  __int64 v206; // [rsp+1E0h] [rbp-10h]
  __int64 v207; // [rsp+1E8h] [rbp-8h]
  __int128 v208; // [rsp+1F0h] [rbp+0h] BYREF

  v1 = *(_QWORD *)(a1 + 312);
  v205 = -1;
  v202 = -1;
  v3 = a1 + 584;
  v4 = *(_BYTE *)(a1 + 600) == 0;
  v5 = *(_QWORD *)(v1 + 24);
  v203 = v5;
  v204 = a1 + 584;
  v208 = 0;
  if ( !v4 )
  {
    PerformanceCounter = KeQueryPerformanceCounter(0);
    v58 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))SRV2_PERF_UPDATE_PERF_COUNTER)(
            v3,
            0,
            (LARGE_INTEGER)PerformanceCounter.QuadPart);
    *(_BYTE *)(v3 + 128) = 0;
    *(_QWORD *)(v3 + 136) = v58;
  }
  v6 = *(_QWORD *)(a1 + 416);
  if ( v6 )
    v202 = *(_QWORD *)(*(_QWORD *)(v6 + 560) + 176LL);
  PerformanceFrequency.QuadPart = 0;
  KeQueryPerformanceCounter(&PerformanceFrequency);
  result = *(unsigned int *)(v5 + 8);
  v190 = *(_DWORD *)(v5 + 8);
  if ( (int)result < 0 )
  {
    if ( (Microsoft_Windows_SMBServerEnableBits & 2) != 0 )
    {
      v59 = *(_QWORD **)(a1 + 560);
      v150 = &Srv2ZeroGuid;
      v60 = v59[9];
      if ( v60 )
        v188 = (__int64 *)(v60 + 96);
      else
        v188 = &Srv2ZeroGuid;
      v75 = v59[7];
      if ( v75 )
        v194 = (__int64 *)(v75 + 24);
      else
        v194 = &Srv2ZeroGuid;
      v76 = v59[4];
      if ( v76 )
        v150 = (__int64 *)(v76 + 72);
      return McTemplateK0xqqxxhhqqqqxqxqxqxqxqxqxxjjjj_EtwWriteTransfer(
               *(unsigned __int16 *)(a1 + 612),
               (unsigned int)SMB2_EVENT_RESP_ERROR,
               v204,
               *(_QWORD *)(v203 + 40),
               *(_DWORD *)(v203 + 32),
               *(_DWORD *)(v203 + 36),
               *(_QWORD *)(v203 + 24),
               v202,
               *(_WORD *)(v203 + 12),
               *(_WORD *)(v203 + 14),
               *(_DWORD *)(v203 + 16),
               v190,
               **(_BYTE **)(a1 + 64),
               *(_WORD *)(a1 + 602),
               1000000000LL * *(_QWORD *)(a1 + 624) / PerformanceFrequency.QuadPart,
               *(_WORD *)(a1 + 604),
               1000000000LL * *(_QWORD *)(a1 + 632) / PerformanceFrequency.QuadPart,
               *(_WORD *)(a1 + 606),
               1000000000LL * *(_QWORD *)(a1 + 640) / PerformanceFrequency.QuadPart,
               *(_WORD *)(a1 + 608),
               1000000000LL * *(_QWORD *)(a1 + 648) / PerformanceFrequency.QuadPart,
               *(_WORD *)(a1 + 610),
               1000000000LL * *(_QWORD *)(a1 + 656) / PerformanceFrequency.QuadPart,
               *(_WORD *)(a1 + 612),
               1000000000LL * *(_QWORD *)(a1 + 664) / PerformanceFrequency.QuadPart,
               *(_WORD *)(a1 + 616),
               1000000000LL * *(_QWORD *)(a1 + 680) / PerformanceFrequency.QuadPart,
               1000000000LL * *(_QWORD *)(a1 + 688) / PerformanceFrequency.QuadPart,
               *(_QWORD *)(*(_QWORD *)(a1 + 96) + 496LL) + 72LL,
               (__int64)v150,
               (__int64)v194,
               (__int64)v188);
    }
  }
  else
  {
    result = *(unsigned __int16 *)(v5 + 12);
    v191 = *(_WORD *)(v5 + 12);
    if ( (_DWORD)result == 10 )
    {
      if ( (Microsoft_Windows_SMBServerEnableBits & 2) != 0 )
      {
        v26 = *(_QWORD **)(a1 + 560);
        v27 = &Srv2ZeroGuid;
        v146 = &Srv2ZeroGuid;
        v28 = v26[9];
        if ( v28 )
          v176 = (__int64 *)(v28 + 96);
        else
          v176 = &Srv2ZeroGuid;
        v29 = v26[7];
        if ( v29 )
          v27 = (__int64 *)(v29 + 24);
        v162 = v27;
        v30 = v26[4];
        if ( v30 )
          v146 = (__int64 *)(v30 + 72);
        v31 = *(_WORD *)(a1 + 610);
        v32 = *(_WORD *)(a1 + 608);
        v33 = *(_WORD *)(a1 + 606);
        v34 = *(_WORD *)(a1 + 604);
        *(_QWORD *)&v208 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 496LL) + 72LL;
        v142 = (__int64)v176;
        v141 = (__int64)v162;
        v140 = (__int64)v146;
        v139 = v208;
        v138 = 1000000000LL * *(_QWORD *)(a1 + 688) / PerformanceFrequency.QuadPart;
        v137 = 1000000000LL * *(_QWORD *)(a1 + 680) / PerformanceFrequency.QuadPart;
        v136 = *(_WORD *)(a1 + 616);
        v35 = *(unsigned __int16 *)(a1 + 612);
        v135 = 1000000000LL * *(_QWORD *)(a1 + 664) / PerformanceFrequency.QuadPart;
        v134 = *(_WORD *)(a1 + 612);
        v133 = 1000000000LL * *(_QWORD *)(a1 + 656) / PerformanceFrequency.QuadPart;
        v132 = v31;
        v131 = 1000000000LL * *(_QWORD *)(a1 + 648) / PerformanceFrequency.QuadPart;
        v130 = v32;
        v129 = 1000000000LL * *(_QWORD *)(a1 + 640) / PerformanceFrequency.QuadPart;
        v128 = v33;
        v127 = 1000000000LL * *(_QWORD *)(a1 + 632) / PerformanceFrequency.QuadPart;
        v126 = v34;
        v125 = 1000000000LL * *(_QWORD *)(a1 + 624) / PerformanceFrequency.QuadPart;
        v124 = *(_WORD *)(a1 + 602);
        v123 = **(_BYTE **)(a1 + 64);
        v36 = SMB2_EVENT_RESP_LOCK;
        return McTemplateK0xqqxxhhqqqqxqxqxqxqxqxqxxjjjj_EtwWriteTransfer(
                 v35,
                 (_DWORD)v36,
                 v204,
                 *(_QWORD *)(v203 + 40),
                 *(_DWORD *)(v203 + 32),
                 *(_DWORD *)(v203 + 36),
                 *(_QWORD *)(v203 + 24),
                 v202,
                 v191,
                 *(_WORD *)(v203 + 14),
                 *(_DWORD *)(v203 + 16),
                 v190,
                 v123,
                 v124,
                 v125,
                 v126,
                 v127,
                 v128,
                 v129,
                 v130,
                 v131,
                 v132,
                 v133,
                 v134,
                 v135,
                 v136,
                 v137,
                 v138,
                 v139,
                 v140,
                 v141,
                 v142);
      }
    }
    else if ( (_DWORD)result == 8 )
    {
      if ( (Microsoft_Windows_SMBServerEnableBits & 2) != 0 )
      {
        v8 = *(_QWORD **)(a1 + 560);
        v143 = &Srv2ZeroGuid;
        v9 = v8[9];
        if ( v9 )
        {
          v205 = *(_QWORD *)(v9 + 80);
          v173 = (__int64 *)(v9 + 96);
        }
        else
        {
          v173 = &Srv2ZeroGuid;
        }
        v10 = v8[7];
        if ( v10 )
          v159 = (__int64 *)(v10 + 24);
        else
          v159 = &Srv2ZeroGuid;
        v11 = v8[4];
        if ( v11 )
          v143 = (__int64 *)(v11 + 72);
        return McTemplateK0xqqxxhhqqqqxqxqxqxqxqxqxqxxqjjjjx_EtwWriteTransfer(
                 *(unsigned __int16 *)(a1 + 612),
                 **(unsigned __int8 **)(a1 + 64),
                 v204,
                 *(_QWORD *)(v203 + 40),
                 *(_DWORD *)(v203 + 32),
                 *(_DWORD *)(v203 + 36),
                 *(_QWORD *)(v203 + 24),
                 v202,
                 v191,
                 *(_WORD *)(v203 + 14),
                 *(_DWORD *)(v203 + 16),
                 v190,
                 **(_BYTE **)(a1 + 64),
                 *(_WORD *)(a1 + 602),
                 1000000000LL * *(_QWORD *)(a1 + 624) / PerformanceFrequency.QuadPart,
                 *(_WORD *)(a1 + 604),
                 1000000000LL * *(_QWORD *)(a1 + 632) / PerformanceFrequency.QuadPart,
                 *(_WORD *)(a1 + 606),
                 1000000000LL * *(_QWORD *)(a1 + 640) / PerformanceFrequency.QuadPart,
                 *(_WORD *)(a1 + 608),
                 1000000000LL * *(_QWORD *)(a1 + 648) / PerformanceFrequency.QuadPart,
                 *(_WORD *)(a1 + 610),
                 1000000000LL * *(_QWORD *)(a1 + 656) / PerformanceFrequency.QuadPart,
                 *(_WORD *)(a1 + 612),
                 1000000000LL * *(_QWORD *)(a1 + 664) / PerformanceFrequency.QuadPart,
                 *(_WORD *)(a1 + 614),
                 1000000000LL * *(_QWORD *)(a1 + 672) / PerformanceFrequency.QuadPart,
                 *(_WORD *)(a1 + 616),
                 1000000000LL * *(_QWORD *)(a1 + 680) / PerformanceFrequency.QuadPart,
                 1000000000LL * *(_QWORD *)(a1 + 688) / PerformanceFrequency.QuadPart,
                 *(_DWORD *)(v203 + 68),
                 *(_QWORD *)(*(_QWORD *)(a1 + 96) + 496LL) + 72LL,
                 (__int64)v143,
                 (__int64)v159,
                 (__int64)v173,
                 v205);
      }
    }
    else
    {
      switch ( *(_WORD *)(v5 + 12) )
      {
        case 0:
          if ( (Microsoft_Windows_SMBServerEnableBits & 2) != 0 )
            result = McTemplateK0xqqxxhhqqqqxqxqxqxqxqxqxxhhqqqqxj_EtwWriteTransfer(
                       *(_DWORD *)(v203 + 88),
                       **(unsigned __int8 **)(a1 + 64),
                       v204,
                       *(_QWORD *)(v203 + 40),
                       *(_DWORD *)(v203 + 32),
                       *(_DWORD *)(v203 + 36),
                       *(_QWORD *)(v203 + 24),
                       v202,
                       result,
                       *(_WORD *)(v203 + 14),
                       *(_DWORD *)(v203 + 16),
                       v190,
                       **(_BYTE **)(a1 + 64),
                       *(_WORD *)(a1 + 602),
                       1000000000LL * *(_QWORD *)(a1 + 624) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 604),
                       1000000000LL * *(_QWORD *)(a1 + 632) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 606),
                       1000000000LL * *(_QWORD *)(a1 + 640) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 608),
                       1000000000LL * *(_QWORD *)(a1 + 648) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 610),
                       1000000000LL * *(_QWORD *)(a1 + 656) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 612),
                       1000000000LL * *(_QWORD *)(a1 + 664) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 616),
                       1000000000LL * *(_QWORD *)(a1 + 680) / PerformanceFrequency.QuadPart,
                       1000000000LL * *(_QWORD *)(a1 + 688) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(v203 + 66),
                       *(_WORD *)(v203 + 68),
                       *(_DWORD *)(v203 + 88),
                       *(_DWORD *)(v203 + 92),
                       *(_DWORD *)(v203 + 96),
                       *(_DWORD *)(v203 + 100),
                       *(_QWORD *)(v203 + 104),
                       *(_QWORD *)(*(_QWORD *)(a1 + 96) + 496LL) + 72LL);
          break;
        case 1:
          if ( (Microsoft_Windows_SMBServerEnableBits & 2) != 0 )
          {
            v46 = *(_QWORD *)(*(_QWORD *)(a1 + 560) + 32LL);
            if ( v46 )
              v47 = (__int64 *)(v46 + 72);
            else
              v47 = &Srv2ZeroGuid;
            result = McTemplateK0xqqxxhhqqqqxqxqxqxqxqxqxxhjj_EtwWriteTransfer(
                       *(unsigned __int16 *)(a1 + 612),
                       **(unsigned __int8 **)(a1 + 64),
                       v204,
                       *(_QWORD *)(v203 + 40),
                       *(_DWORD *)(v203 + 32),
                       *(_DWORD *)(v203 + 36),
                       *(_QWORD *)(v203 + 24),
                       v202,
                       v191,
                       *(_WORD *)(v203 + 14),
                       *(_DWORD *)(v203 + 16),
                       v190,
                       **(_BYTE **)(a1 + 64),
                       *(_WORD *)(a1 + 602),
                       1000000000LL * *(_QWORD *)(a1 + 624) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 604),
                       1000000000LL * *(_QWORD *)(a1 + 632) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 606),
                       1000000000LL * *(_QWORD *)(a1 + 640) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 608),
                       1000000000LL * *(_QWORD *)(a1 + 648) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 610),
                       1000000000LL * *(_QWORD *)(a1 + 656) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 612),
                       1000000000LL * *(_QWORD *)(a1 + 664) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 616),
                       1000000000LL * *(_QWORD *)(a1 + 680) / PerformanceFrequency.QuadPart,
                       1000000000LL * *(_QWORD *)(a1 + 688) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(v203 + 66),
                       *(_QWORD *)(*(_QWORD *)(a1 + 96) + 496LL) + 72LL,
                       (__int64)v47);
          }
          break;
        case 2:
          if ( (Microsoft_Windows_SMBServerEnableBits & 2) != 0 )
          {
            v48 = *(_QWORD *)(*(_QWORD *)(a1 + 560) + 32LL);
            if ( v48 )
              v49 = (__int64 *)(v48 + 72);
            else
              v49 = &Srv2ZeroGuid;
            result = McTemplateK0xqqxxhhqqqqxqxqxqxqxqxqxxjj_EtwWriteTransfer(
                       *(unsigned __int16 *)(a1 + 612),
                       **(unsigned __int8 **)(a1 + 64),
                       v204,
                       *(_QWORD *)(v203 + 40),
                       *(_DWORD *)(v203 + 32),
                       *(_DWORD *)(v203 + 36),
                       *(_QWORD *)(v203 + 24),
                       v202,
                       v191,
                       *(_WORD *)(v203 + 14),
                       *(_DWORD *)(v203 + 16),
                       v190,
                       **(_BYTE **)(a1 + 64),
                       *(_WORD *)(a1 + 602),
                       1000000000LL * *(_QWORD *)(a1 + 624) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 604),
                       1000000000LL * *(_QWORD *)(a1 + 632) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 606),
                       1000000000LL * *(_QWORD *)(a1 + 640) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 608),
                       1000000000LL * *(_QWORD *)(a1 + 648) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 610),
                       1000000000LL * *(_QWORD *)(a1 + 656) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 612),
                       1000000000LL * *(_QWORD *)(a1 + 664) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 616),
                       1000000000LL * *(_QWORD *)(a1 + 680) / PerformanceFrequency.QuadPart,
                       1000000000LL * *(_QWORD *)(a1 + 688) / PerformanceFrequency.QuadPart,
                       *(_QWORD *)(*(_QWORD *)(a1 + 96) + 496LL) + 72LL,
                       (__int64)v49);
          }
          break;
        case 3:
          if ( (Microsoft_Windows_SMBServerEnableBits & 2) != 0 )
          {
            v61 = *(_QWORD *)(a1 + 560);
            v151 = &Srv2ZeroGuid;
            v62 = *(_QWORD *)(v61 + 56);
            if ( v62 )
              v189 = (__int64 *)(v62 + 24);
            else
              v189 = &Srv2ZeroGuid;
            v77 = *(_QWORD *)(v61 + 32);
            if ( v77 )
              v151 = (__int64 *)(v77 + 72);
            v78 = *(_WORD *)(a1 + 610);
            v79 = *(_WORD *)(a1 + 608);
            v80 = *(_WORD *)(a1 + 606);
            v81 = *(_WORD *)(a1 + 604);
            v184 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 496LL) + 72LL;
            v82 = *(_WORD *)(a1 + 602);
            v165 = 1000000000LL * *(_QWORD *)(a1 + 688) / PerformanceFrequency.QuadPart;
            v195 = 1000000000LL * *(_QWORD *)(a1 + 680) / PerformanceFrequency.QuadPart;
            v200 = *(_WORD *)(a1 + 616);
            v83 = 1000000000LL * *(_QWORD *)(a1 + 664) / PerformanceFrequency.QuadPart;
            LODWORD(v205) = *(unsigned __int16 *)(a1 + 612);
            result = McTemplateK0xqqxxhhqqqqxqxqxqxqxqxqxxuqqqjjj_EtwWriteTransfer(
                       v205,
                       **(unsigned __int8 **)(a1 + 64),
                       v204,
                       *(_QWORD *)(v203 + 40),
                       *(_DWORD *)(v203 + 32),
                       *(_DWORD *)(v203 + 36),
                       *(_QWORD *)(v203 + 24),
                       v202,
                       v191,
                       *(_WORD *)(v203 + 14),
                       *(_DWORD *)(v203 + 16),
                       v190,
                       **(_BYTE **)(a1 + 64),
                       v82,
                       1000000000LL * *(_QWORD *)(a1 + 624) / PerformanceFrequency.QuadPart,
                       v81,
                       1000000000LL * *(_QWORD *)(a1 + 632) / PerformanceFrequency.QuadPart,
                       v80,
                       1000000000LL * *(_QWORD *)(a1 + 640) / PerformanceFrequency.QuadPart,
                       v79,
                       1000000000LL * *(_QWORD *)(a1 + 648) / PerformanceFrequency.QuadPart,
                       v78,
                       1000000000LL * *(_QWORD *)(a1 + 656) / PerformanceFrequency.QuadPart,
                       v205,
                       v83,
                       v200,
                       v195,
                       v165,
                       *(_BYTE *)(v203 + 66),
                       *(_DWORD *)(v203 + 68),
                       *(_DWORD *)(v203 + 72),
                       *(_DWORD *)(v203 + 76),
                       v184,
                       (__int64)v151,
                       (__int64)v189);
          }
          break;
        case 4:
          if ( (Microsoft_Windows_SMBServerEnableBits & 2) != 0 )
          {
            v50 = *(_QWORD *)(a1 + 560);
            v148 = &Srv2ZeroGuid;
            v51 = *(_QWORD *)(v50 + 56);
            if ( v51 )
              v187 = (__int64 *)(v51 + 24);
            else
              v187 = &Srv2ZeroGuid;
            v52 = *(_QWORD *)(v50 + 32);
            if ( v52 )
              v148 = (__int64 *)(v52 + 72);
            result = McTemplateK0xqqxxhhqqqqxqxqxqxqxqxqxxjjj_EtwWriteTransfer(
                       *(unsigned __int16 *)(a1 + 612),
                       **(unsigned __int8 **)(a1 + 64),
                       v204,
                       *(_QWORD *)(v203 + 40),
                       *(_DWORD *)(v203 + 32),
                       *(_DWORD *)(v203 + 36),
                       *(_QWORD *)(v203 + 24),
                       v202,
                       v191,
                       *(_WORD *)(v203 + 14),
                       *(_DWORD *)(v203 + 16),
                       v190,
                       **(_BYTE **)(a1 + 64),
                       *(_WORD *)(a1 + 602),
                       1000000000LL * *(_QWORD *)(a1 + 624) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 604),
                       1000000000LL * *(_QWORD *)(a1 + 632) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 606),
                       1000000000LL * *(_QWORD *)(a1 + 640) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 608),
                       1000000000LL * *(_QWORD *)(a1 + 648) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 610),
                       1000000000LL * *(_QWORD *)(a1 + 656) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 612),
                       1000000000LL * *(_QWORD *)(a1 + 664) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 616),
                       1000000000LL * *(_QWORD *)(a1 + 680) / PerformanceFrequency.QuadPart,
                       1000000000LL * *(_QWORD *)(a1 + 688) / PerformanceFrequency.QuadPart,
                       *(_QWORD *)(*(_QWORD *)(a1 + 96) + 496LL) + 72LL,
                       (__int64)v148,
                       (__int64)v187);
          }
          break;
        case 5:
          v63 = *(_QWORD *)(a1 + 560);
          v208 = 0;
          v64 = 0;
          LODWORD(v205) = 0;
          LODWORD(v207) = 0;
          if ( *(_BYTE *)(v63 + 306) )
          {
            result = *(_QWORD *)(v63 + 104);
            if ( result )
            {
              v208 = *(_OWORD *)(result + 80);
              result = *(unsigned int *)(*(_QWORD *)(v63 + 104) + 120LL);
              LODWORD(v207) = *(_DWORD *)(*(_QWORD *)(v63 + 104) + 120LL);
            }
          }
          if ( *(_DWORD *)(v5 + 148) )
          {
            result = *(_QWORD *)(a1 + 312);
            v84 = (unsigned int *)(*(_QWORD *)(result + 24) + *(unsigned int *)(v5 + 144));
            if ( v84 )
            {
              do
              {
                result = *v84;
                ++v64;
                if ( !(_DWORD)result )
                  break;
                v84 = (unsigned int *)((char *)v84 + result);
              }
              while ( v84 );
              LODWORD(v205) = v64;
            }
          }
          if ( (Microsoft_Windows_SMBServerEnableBits & 2) != 0 )
          {
            v85 = *(_QWORD *)(v63 + 72);
            v157 = &Srv2ZeroGuid;
            if ( v85 )
              v166 = (__int64 *)(v85 + 96);
            else
              v166 = &Srv2ZeroGuid;
            v86 = *(_QWORD *)(v63 + 56);
            if ( v86 )
              v185 = (__int64 *)(v86 + 24);
            else
              v185 = &Srv2ZeroGuid;
            v87 = *(_QWORD *)(v63 + 32);
            if ( v87 )
              v157 = (__int64 *)(v87 + 72);
            result = McTemplateK0xqqxxhhqqqqxqxqxqxqxqxqxxuqxxxxxxqxqjqjjjj_EtwWriteTransfer(
                       *(_DWORD *)(v203 + 120),
                       **(unsigned __int8 **)(a1 + 64),
                       v204,
                       *(_QWORD *)(v203 + 40),
                       *(_DWORD *)(v203 + 32),
                       *(_DWORD *)(v203 + 36),
                       *(_QWORD *)(v203 + 24),
                       v202,
                       v191,
                       *(_WORD *)(v203 + 14),
                       *(_DWORD *)(v203 + 16),
                       v190,
                       **(_BYTE **)(a1 + 64),
                       *(_WORD *)(a1 + 602),
                       1000000000LL * *(_QWORD *)(a1 + 624) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 604),
                       1000000000LL * *(_QWORD *)(a1 + 632) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 606),
                       1000000000LL * *(_QWORD *)(a1 + 640) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 608),
                       1000000000LL * *(_QWORD *)(a1 + 648) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 610),
                       1000000000LL * *(_QWORD *)(a1 + 656) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 612),
                       1000000000LL * *(_QWORD *)(a1 + 664) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 616),
                       1000000000LL * *(_QWORD *)(a1 + 680) / PerformanceFrequency.QuadPart,
                       1000000000LL * *(_QWORD *)(a1 + 688) / PerformanceFrequency.QuadPart,
                       *(_BYTE *)(v203 + 66),
                       *(_DWORD *)(v203 + 68),
                       *(_QWORD *)(v203 + 72),
                       *(_QWORD *)(v203 + 80),
                       *(_QWORD *)(v203 + 88),
                       *(_QWORD *)(v203 + 96),
                       *(_QWORD *)(v203 + 104),
                       *(_QWORD *)(v203 + 112),
                       *(_DWORD *)(v203 + 120),
                       *(_QWORD *)(v203 + 128),
                       v205,
                       (__int64)&v208,
                       v207,
                       *(_QWORD *)(*(_QWORD *)(a1 + 96) + 496LL) + 72LL,
                       (__int64)v157,
                       (__int64)v185,
                       (__int64)v166);
          }
          break;
        case 6:
          if ( (Microsoft_Windows_SMBServerEnableBits & 2) != 0 )
          {
            v53 = *(_QWORD **)(a1 + 560);
            v149 = &Srv2ZeroGuid;
            v54 = v53[9];
            if ( v54 )
              v178 = (__int64 *)(v54 + 96);
            else
              v178 = &Srv2ZeroGuid;
            v55 = v53[7];
            if ( v55 )
              v164 = (__int64 *)(v55 + 24);
            else
              v164 = &Srv2ZeroGuid;
            v56 = v53[4];
            if ( v56 )
              v149 = (__int64 *)(v56 + 72);
            result = McTemplateK0xqqxxhhqqqqxqxqxqxqxqxqxxhxxxxxxqjjjj_EtwWriteTransfer(
                       *(_QWORD *)(v203 + 96),
                       **(unsigned __int8 **)(a1 + 64),
                       v204,
                       *(_QWORD *)(v203 + 40),
                       *(_DWORD *)(v203 + 32),
                       *(_DWORD *)(v203 + 36),
                       *(_QWORD *)(v203 + 24),
                       v202,
                       v191,
                       *(_WORD *)(v203 + 14),
                       *(_DWORD *)(v203 + 16),
                       v190,
                       **(_BYTE **)(a1 + 64),
                       *(_WORD *)(a1 + 602),
                       1000000000LL * *(_QWORD *)(a1 + 624) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 604),
                       1000000000LL * *(_QWORD *)(a1 + 632) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 606),
                       1000000000LL * *(_QWORD *)(a1 + 640) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 608),
                       1000000000LL * *(_QWORD *)(a1 + 648) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 610),
                       1000000000LL * *(_QWORD *)(a1 + 656) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 612),
                       1000000000LL * *(_QWORD *)(a1 + 664) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 616),
                       1000000000LL * *(_QWORD *)(a1 + 680) / PerformanceFrequency.QuadPart,
                       1000000000LL * *(_QWORD *)(a1 + 688) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(v203 + 66),
                       *(_QWORD *)(v203 + 72),
                       *(_QWORD *)(v203 + 80),
                       *(_QWORD *)(v203 + 88),
                       *(_QWORD *)(v203 + 96),
                       *(_QWORD *)(v203 + 104),
                       *(_QWORD *)(v203 + 112),
                       *(_DWORD *)(v203 + 120),
                       *(_QWORD *)(*(_QWORD *)(a1 + 96) + 496LL) + 72LL,
                       (__int64)v149,
                       (__int64)v164,
                       (__int64)v178);
          }
          break;
        case 7:
          if ( (Microsoft_Windows_SMBServerEnableBits & 2) != 0 )
          {
            v65 = *(_QWORD **)(a1 + 560);
            v152 = &Srv2ZeroGuid;
            v66 = v65[9];
            if ( v66 )
              v179 = (__int64 *)(v66 + 96);
            else
              v179 = &Srv2ZeroGuid;
            v88 = v65[7];
            if ( v88 )
              v167 = (__int64 *)(v88 + 24);
            else
              v167 = &Srv2ZeroGuid;
            v89 = v65[4];
            if ( v89 )
              v152 = (__int64 *)(v89 + 72);
            v90 = *(_WORD *)(a1 + 610);
            v91 = *(_WORD *)(a1 + 608);
            v92 = *(_WORD *)(a1 + 606);
            v93 = *(_WORD *)(a1 + 604);
            v198 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 496LL) + 72LL;
            v94 = *(_WORD *)(a1 + 602);
            v197 = 1000000000LL * *(_QWORD *)(a1 + 688) / PerformanceFrequency.QuadPart;
            v206 = 1000000000LL * *(_QWORD *)(a1 + 680) / PerformanceFrequency.QuadPart;
            v142 = (__int64)v179;
            v141 = (__int64)v167;
            v140 = (__int64)v152;
            v139 = v198;
            LOBYTE(v138) = v197;
            LOBYTE(v137) = v206;
            v136 = *(_WORD *)(a1 + 616);
            v35 = *(unsigned __int16 *)(a1 + 612);
            v135 = 1000000000LL * *(_QWORD *)(a1 + 664) / PerformanceFrequency.QuadPart;
            v134 = *(_WORD *)(a1 + 612);
            v133 = 1000000000LL * *(_QWORD *)(a1 + 656) / PerformanceFrequency.QuadPart;
            v132 = v90;
            v131 = 1000000000LL * *(_QWORD *)(a1 + 648) / PerformanceFrequency.QuadPart;
            v130 = v91;
            v129 = 1000000000LL * *(_QWORD *)(a1 + 640) / PerformanceFrequency.QuadPart;
            v128 = v92;
            v127 = 1000000000LL * *(_QWORD *)(a1 + 632) / PerformanceFrequency.QuadPart;
            v126 = v93;
            v125 = 1000000000LL * *(_QWORD *)(a1 + 624) / PerformanceFrequency.QuadPart;
            LOBYTE(v124) = v94;
            v123 = **(_BYTE **)(a1 + 64);
            v36 = SMB2_EVENT_RESP_FLUSH;
            return McTemplateK0xqqxxhhqqqqxqxqxqxqxqxqxxjjjj_EtwWriteTransfer(
                     v35,
                     (_DWORD)v36,
                     v204,
                     *(_QWORD *)(v203 + 40),
                     *(_DWORD *)(v203 + 32),
                     *(_DWORD *)(v203 + 36),
                     *(_QWORD *)(v203 + 24),
                     v202,
                     v191,
                     *(_WORD *)(v203 + 14),
                     *(_DWORD *)(v203 + 16),
                     v190,
                     v123,
                     v124,
                     v125,
                     v126,
                     v127,
                     v128,
                     v129,
                     v130,
                     v131,
                     v132,
                     v133,
                     v134,
                     v135,
                     v136,
                     v137,
                     v138,
                     v139,
                     v140,
                     v141,
                     v142);
          }
          break;
        case 9:
          if ( (Microsoft_Windows_SMBServerEnableBits & 2) != 0 )
          {
            v12 = *(_QWORD **)(a1 + 560);
            v13 = &Srv2ZeroGuid;
            v144 = &Srv2ZeroGuid;
            v14 = v12[9];
            if ( v14 )
            {
              v205 = *(_QWORD *)(v14 + 80);
              v174 = (__int64 *)(v14 + 96);
              v13 = &Srv2ZeroGuid;
            }
            else
            {
              v174 = &Srv2ZeroGuid;
            }
            v15 = v12[7];
            if ( v15 )
              v13 = (__int64 *)(v15 + 24);
            v160 = (__int64)v13;
            v16 = v12[4];
            if ( v16 )
              v144 = (__int64 *)(v16 + 72);
            result = McTemplateK0xqqxxhhqqqqxqxqxqxqxqxqxqxxqqhhjjjjx_EtwWriteTransfer(
                       *(_DWORD *)(v203 + 72),
                       **(unsigned __int8 **)(a1 + 64),
                       v204,
                       *(_QWORD *)(v203 + 40),
                       *(_DWORD *)(v203 + 32),
                       *(_DWORD *)(v203 + 36),
                       *(_QWORD *)(v203 + 24),
                       v202,
                       v191,
                       *(_WORD *)(v203 + 14),
                       *(_DWORD *)(v203 + 16),
                       v190,
                       **(_BYTE **)(a1 + 64),
                       *(_WORD *)(a1 + 602),
                       1000000000LL * *(_QWORD *)(a1 + 624) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 604),
                       1000000000LL * *(_QWORD *)(a1 + 632) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 606),
                       1000000000LL * *(_QWORD *)(a1 + 640) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 608),
                       1000000000LL * *(_QWORD *)(a1 + 648) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 610),
                       1000000000LL * *(_QWORD *)(a1 + 656) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 612),
                       1000000000LL * *(_QWORD *)(a1 + 664) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 614),
                       1000000000LL * *(_QWORD *)(a1 + 672) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 616),
                       1000000000LL * *(_QWORD *)(a1 + 680) / PerformanceFrequency.QuadPart,
                       1000000000LL * *(_QWORD *)(a1 + 688) / PerformanceFrequency.QuadPart,
                       *(_DWORD *)(v203 + 68),
                       *(_DWORD *)(v203 + 72),
                       *(_WORD *)(v203 + 76),
                       *(_WORD *)(v203 + 78),
                       *(_QWORD *)(*(_QWORD *)(a1 + 96) + 496LL) + 72LL,
                       (__int64)v144,
                       v160,
                       (__int64)v174,
                       v205);
          }
          break;
        case 0xB:
          if ( (Microsoft_Windows_SMBServerEnableBits & 2) != 0 )
          {
            v17 = *(_QWORD **)(a1 + 560);
            v18 = &Srv2ZeroGuid;
            v145 = &Srv2ZeroGuid;
            v19 = v17[9];
            if ( v19 )
              v175 = (__int64 *)(v19 + 96);
            else
              v175 = &Srv2ZeroGuid;
            v20 = v17[7];
            if ( v20 )
              v18 = (__int64 *)(v20 + 24);
            v161 = (__int64)v18;
            v21 = v17[4];
            if ( v21 )
              v145 = (__int64 *)(v21 + 72);
            v22 = *(_WORD *)(a1 + 610);
            v23 = *(_WORD *)(a1 + 608);
            v24 = *(_WORD *)(a1 + 606);
            v25 = *(_WORD *)(a1 + 604);
            *(_QWORD *)&v208 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 496LL) + 72LL;
            v192 = *(unsigned __int16 *)(a1 + 612);
            result = McTemplateK0xqqxxhhqqqqxqxqxqxqxqxqxxqqxjjjj_EtwWriteTransfer(
                       v192,
                       **(unsigned __int8 **)(a1 + 64),
                       v204,
                       *(_QWORD *)(v203 + 40),
                       *(_DWORD *)(v203 + 32),
                       *(_DWORD *)(v203 + 36),
                       *(_QWORD *)(v203 + 24),
                       v202,
                       v191,
                       *(_WORD *)(v203 + 14),
                       *(_DWORD *)(v203 + 16),
                       v190,
                       **(_BYTE **)(a1 + 64),
                       *(_WORD *)(a1 + 602),
                       1000000000LL * *(_QWORD *)(a1 + 624) / PerformanceFrequency.QuadPart,
                       v25,
                       1000000000LL * *(_QWORD *)(a1 + 632) / PerformanceFrequency.QuadPart,
                       v24,
                       1000000000LL * *(_QWORD *)(a1 + 640) / PerformanceFrequency.QuadPart,
                       v23,
                       1000000000LL * *(_QWORD *)(a1 + 648) / PerformanceFrequency.QuadPart,
                       v22,
                       1000000000LL * *(_QWORD *)(a1 + 656) / PerformanceFrequency.QuadPart,
                       v192,
                       1000000000LL * *(_QWORD *)(a1 + 664) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 616),
                       1000000000LL * *(_QWORD *)(a1 + 680) / PerformanceFrequency.QuadPart,
                       1000000000LL * *(_QWORD *)(a1 + 688) / PerformanceFrequency.QuadPart,
                       *(_DWORD *)(v203 + 68),
                       *(_DWORD *)(v203 + 104),
                       *(_QWORD *)(v203 + 72),
                       v208,
                       (__int64)v145,
                       v161,
                       (__int64)v175);
          }
          break;
        case 0xD:
          if ( (Microsoft_Windows_SMBServerEnableBits & 2) != 0 )
            result = McTemplateK0xqqxxhhqqqqxqxqxqxqxqxqxxj_EtwWriteTransfer(
                       *(unsigned __int16 *)(a1 + 612),
                       **(unsigned __int8 **)(a1 + 64),
                       v204,
                       *(_QWORD *)(v203 + 40),
                       *(_DWORD *)(v203 + 32),
                       *(_DWORD *)(v203 + 36),
                       *(_QWORD *)(v203 + 24),
                       v202,
                       result,
                       *(_WORD *)(v203 + 14),
                       *(_DWORD *)(v203 + 16),
                       v190,
                       **(_BYTE **)(a1 + 64),
                       *(_WORD *)(a1 + 602),
                       1000000000LL * *(_QWORD *)(a1 + 624) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 604),
                       1000000000LL * *(_QWORD *)(a1 + 632) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 606),
                       1000000000LL * *(_QWORD *)(a1 + 640) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 608),
                       1000000000LL * *(_QWORD *)(a1 + 648) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 610),
                       1000000000LL * *(_QWORD *)(a1 + 656) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 612),
                       1000000000LL * *(_QWORD *)(a1 + 664) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 616),
                       1000000000LL * *(_QWORD *)(a1 + 680) / PerformanceFrequency.QuadPart,
                       1000000000LL * *(_QWORD *)(a1 + 688) / PerformanceFrequency.QuadPart,
                       *(_QWORD *)(*(_QWORD *)(a1 + 96) + 496LL) + 72LL);
          break;
        case 0xE:
          if ( (Microsoft_Windows_SMBServerEnableBits & 2) != 0 )
          {
            v67 = *(_QWORD **)(a1 + 560);
            v153 = &Srv2ZeroGuid;
            v68 = v67[9];
            if ( v68 )
              v180 = (__int64 *)(v68 + 96);
            else
              v180 = &Srv2ZeroGuid;
            v95 = v67[7];
            if ( v95 )
              v168 = (__int64 *)(v95 + 24);
            else
              v168 = &Srv2ZeroGuid;
            v96 = v67[4];
            if ( v96 )
              v153 = (__int64 *)(v96 + 72);
            v97 = *(_WORD *)(a1 + 610);
            v98 = *(_WORD *)(a1 + 608);
            v99 = *(_WORD *)(a1 + 606);
            v100 = *(_WORD *)(a1 + 604);
            *(_QWORD *)&v208 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 496LL) + 72LL;
            v142 = (__int64)v180;
            v141 = (__int64)v168;
            v140 = (__int64)v153;
            v139 = v208;
            v138 = 1000000000LL * *(_QWORD *)(a1 + 688) / PerformanceFrequency.QuadPart;
            v137 = 1000000000LL * *(_QWORD *)(a1 + 680) / PerformanceFrequency.QuadPart;
            v136 = *(_WORD *)(a1 + 616);
            v35 = *(unsigned __int16 *)(a1 + 612);
            v135 = 1000000000LL * *(_QWORD *)(a1 + 664) / PerformanceFrequency.QuadPart;
            v134 = *(_WORD *)(a1 + 612);
            v133 = 1000000000LL * *(_QWORD *)(a1 + 656) / PerformanceFrequency.QuadPart;
            v132 = v97;
            v131 = 1000000000LL * *(_QWORD *)(a1 + 648) / PerformanceFrequency.QuadPart;
            v130 = v98;
            v129 = 1000000000LL * *(_QWORD *)(a1 + 640) / PerformanceFrequency.QuadPart;
            v128 = v99;
            v127 = 1000000000LL * *(_QWORD *)(a1 + 632) / PerformanceFrequency.QuadPart;
            v126 = v100;
            v125 = 1000000000LL * *(_QWORD *)(a1 + 624) / PerformanceFrequency.QuadPart;
            v124 = *(_WORD *)(a1 + 602);
            v123 = **(_BYTE **)(a1 + 64);
            v36 = SMB2_EVENT_RESP_QUERY_DIRECTORY;
            return McTemplateK0xqqxxhhqqqqxqxqxqxqxqxqxxjjjj_EtwWriteTransfer(
                     v35,
                     (_DWORD)v36,
                     v204,
                     *(_QWORD *)(v203 + 40),
                     *(_DWORD *)(v203 + 32),
                     *(_DWORD *)(v203 + 36),
                     *(_QWORD *)(v203 + 24),
                     v202,
                     v191,
                     *(_WORD *)(v203 + 14),
                     *(_DWORD *)(v203 + 16),
                     v190,
                     v123,
                     v124,
                     v125,
                     v126,
                     v127,
                     v128,
                     v129,
                     v130,
                     v131,
                     v132,
                     v133,
                     v134,
                     v135,
                     v136,
                     v137,
                     v138,
                     v139,
                     v140,
                     v141,
                     v142);
          }
          break;
        case 0xF:
          if ( (Microsoft_Windows_SMBServerEnableBits & 2) != 0 )
          {
            v69 = *(_QWORD **)(a1 + 560);
            v154 = &Srv2ZeroGuid;
            v70 = v69[9];
            if ( v70 )
              v181 = (__int64 *)(v70 + 96);
            else
              v181 = &Srv2ZeroGuid;
            v101 = v69[7];
            if ( v101 )
              v169 = (__int64 *)(v101 + 24);
            else
              v169 = &Srv2ZeroGuid;
            v102 = v69[4];
            if ( v102 )
              v154 = (__int64 *)(v102 + 72);
            v103 = *(_WORD *)(a1 + 610);
            v104 = *(_WORD *)(a1 + 608);
            v105 = *(_WORD *)(a1 + 606);
            v106 = *(_WORD *)(a1 + 604);
            *(_QWORD *)&v208 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 496LL) + 72LL;
            v142 = (__int64)v181;
            v141 = (__int64)v169;
            v140 = (__int64)v154;
            v139 = v208;
            v138 = 1000000000LL * *(_QWORD *)(a1 + 688) / PerformanceFrequency.QuadPart;
            v137 = 1000000000LL * *(_QWORD *)(a1 + 680) / PerformanceFrequency.QuadPart;
            v136 = *(_WORD *)(a1 + 616);
            v35 = *(unsigned __int16 *)(a1 + 612);
            v135 = 1000000000LL * *(_QWORD *)(a1 + 664) / PerformanceFrequency.QuadPart;
            v134 = *(_WORD *)(a1 + 612);
            v133 = 1000000000LL * *(_QWORD *)(a1 + 656) / PerformanceFrequency.QuadPart;
            v132 = v103;
            v131 = 1000000000LL * *(_QWORD *)(a1 + 648) / PerformanceFrequency.QuadPart;
            v130 = v104;
            v129 = 1000000000LL * *(_QWORD *)(a1 + 640) / PerformanceFrequency.QuadPart;
            v128 = v105;
            v127 = 1000000000LL * *(_QWORD *)(a1 + 632) / PerformanceFrequency.QuadPart;
            v126 = v106;
            v125 = 1000000000LL * *(_QWORD *)(a1 + 624) / PerformanceFrequency.QuadPart;
            v124 = *(_WORD *)(a1 + 602);
            v123 = **(_BYTE **)(a1 + 64);
            v36 = SMB2_EVENT_RESP_CHANGE_NOTIFY;
            return McTemplateK0xqqxxhhqqqqxqxqxqxqxqxqxxjjjj_EtwWriteTransfer(
                     v35,
                     (_DWORD)v36,
                     v204,
                     *(_QWORD *)(v203 + 40),
                     *(_DWORD *)(v203 + 32),
                     *(_DWORD *)(v203 + 36),
                     *(_QWORD *)(v203 + 24),
                     v202,
                     v191,
                     *(_WORD *)(v203 + 14),
                     *(_DWORD *)(v203 + 16),
                     v190,
                     v123,
                     v124,
                     v125,
                     v126,
                     v127,
                     v128,
                     v129,
                     v130,
                     v131,
                     v132,
                     v133,
                     v134,
                     v135,
                     v136,
                     v137,
                     v138,
                     v139,
                     v140,
                     v141,
                     v142);
          }
          break;
        case 0x10:
          if ( *(_DWORD *)(v5 + 68) )
          {
            v45 = **(_QWORD **)(*(_QWORD *)(a1 + 312) + 80LL);
            if ( (*(_BYTE *)(v45 + 10) & 5) != 0 )
              result = *(_QWORD *)(v45 + 24);
            else
              result = (__int64)MmMapLockedPagesSpecifyCache((PMDL)v45, 0, MmCached, 0, 0, 0x40000010u);
            v199 = result;
          }
          else
          {
            v199 = v5 + *(unsigned __int16 *)(v5 + 66);
          }
          if ( (Microsoft_Windows_SMBServerEnableBits & 2) != 0 )
          {
            v37 = *(_QWORD **)(a1 + 560);
            v147 = &Srv2ZeroGuid;
            v38 = v37[9];
            if ( v38 )
              v177 = (__int64 *)(v38 + 96);
            else
              v177 = &Srv2ZeroGuid;
            v39 = v37[7];
            if ( v39 )
              v163 = (__int64 *)(v39 + 24);
            else
              v163 = &Srv2ZeroGuid;
            v40 = v37[4];
            if ( v40 )
              v147 = (__int64 *)(v40 + 72);
            v41 = *(_WORD *)(a1 + 610);
            v42 = *(_WORD *)(a1 + 608);
            v43 = *(_WORD *)(a1 + 606);
            v44 = *(_WORD *)(a1 + 604);
            *(_QWORD *)&v208 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 496LL) + 72LL;
            v193 = *(unsigned __int16 *)(a1 + 612);
            result = McTemplateK0xqqxxhhqqqqxqxqxqxqxqxqxxqbr25jjjj_EtwWriteTransfer(
                       v193,
                       **(unsigned __int8 **)(a1 + 64),
                       v204,
                       *(_QWORD *)(v203 + 40),
                       *(_DWORD *)(v203 + 32),
                       *(_DWORD *)(v203 + 36),
                       *(_QWORD *)(v203 + 24),
                       v202,
                       *(_WORD *)(v203 + 12),
                       *(_WORD *)(v203 + 14),
                       *(_DWORD *)(v203 + 16),
                       *(_DWORD *)(v203 + 8),
                       **(_BYTE **)(a1 + 64),
                       *(_WORD *)(a1 + 602),
                       1000000000LL * *(_QWORD *)(a1 + 624) / PerformanceFrequency.QuadPart,
                       v44,
                       1000000000LL * *(_QWORD *)(a1 + 632) / PerformanceFrequency.QuadPart,
                       v43,
                       1000000000LL * *(_QWORD *)(a1 + 640) / PerformanceFrequency.QuadPart,
                       v42,
                       1000000000LL * *(_QWORD *)(a1 + 648) / PerformanceFrequency.QuadPart,
                       v41,
                       1000000000LL * *(_QWORD *)(a1 + 656) / PerformanceFrequency.QuadPart,
                       v193,
                       1000000000LL * *(_QWORD *)(a1 + 664) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 616),
                       1000000000LL * *(_QWORD *)(a1 + 680) / PerformanceFrequency.QuadPart,
                       1000000000LL * *(_QWORD *)(a1 + 688) / PerformanceFrequency.QuadPart,
                       *(_DWORD *)(v203 + 68),
                       v199,
                       v208,
                       (__int64)v147,
                       (__int64)v163,
                       (__int64)v177);
          }
          break;
        case 0x11:
          if ( (Microsoft_Windows_SMBServerEnableBits & 2) != 0 )
          {
            v71 = *(_QWORD **)(a1 + 560);
            v155 = &Srv2ZeroGuid;
            v72 = v71[9];
            if ( v72 )
              v182 = (__int64 *)(v72 + 96);
            else
              v182 = &Srv2ZeroGuid;
            v107 = v71[7];
            if ( v107 )
              v170 = (__int64 *)(v107 + 24);
            else
              v170 = &Srv2ZeroGuid;
            v108 = v71[4];
            if ( v108 )
              v155 = (__int64 *)(v108 + 72);
            v109 = *(_WORD *)(a1 + 610);
            v110 = *(_WORD *)(a1 + 608);
            v111 = *(_WORD *)(a1 + 606);
            v112 = *(_WORD *)(a1 + 604);
            *(_QWORD *)&v208 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 496LL) + 72LL;
            v142 = (__int64)v182;
            v141 = (__int64)v170;
            v140 = (__int64)v155;
            v139 = v208;
            v138 = 1000000000LL * *(_QWORD *)(a1 + 688) / PerformanceFrequency.QuadPart;
            v137 = 1000000000LL * *(_QWORD *)(a1 + 680) / PerformanceFrequency.QuadPart;
            v136 = *(_WORD *)(a1 + 616);
            v35 = *(unsigned __int16 *)(a1 + 612);
            v135 = 1000000000LL * *(_QWORD *)(a1 + 664) / PerformanceFrequency.QuadPart;
            v134 = *(_WORD *)(a1 + 612);
            v133 = 1000000000LL * *(_QWORD *)(a1 + 656) / PerformanceFrequency.QuadPart;
            v132 = v109;
            v131 = 1000000000LL * *(_QWORD *)(a1 + 648) / PerformanceFrequency.QuadPart;
            v130 = v110;
            v129 = 1000000000LL * *(_QWORD *)(a1 + 640) / PerformanceFrequency.QuadPart;
            v128 = v111;
            v127 = 1000000000LL * *(_QWORD *)(a1 + 632) / PerformanceFrequency.QuadPart;
            v126 = v112;
            v125 = 1000000000LL * *(_QWORD *)(a1 + 624) / PerformanceFrequency.QuadPart;
            v124 = *(_WORD *)(a1 + 602);
            v123 = **(_BYTE **)(a1 + 64);
            v36 = SMB2_EVENT_RESP_SET_INFO;
            return McTemplateK0xqqxxhhqqqqxqxqxqxqxqxqxxjjjj_EtwWriteTransfer(
                     v35,
                     (_DWORD)v36,
                     v204,
                     *(_QWORD *)(v203 + 40),
                     *(_DWORD *)(v203 + 32),
                     *(_DWORD *)(v203 + 36),
                     *(_QWORD *)(v203 + 24),
                     v202,
                     v191,
                     *(_WORD *)(v203 + 14),
                     *(_DWORD *)(v203 + 16),
                     v190,
                     v123,
                     v124,
                     v125,
                     v126,
                     v127,
                     v128,
                     v129,
                     v130,
                     v131,
                     v132,
                     v133,
                     v134,
                     v135,
                     v136,
                     v137,
                     v138,
                     v139,
                     v140,
                     v141,
                     v142);
          }
          break;
        case 0x12:
          if ( *(_WORD *)(v5 + 64) == 24 )
          {
            if ( (Microsoft_Windows_SMBServerEnableBits & 2) != 0 )
            {
              v73 = *(_QWORD **)(a1 + 560);
              v156 = &Srv2ZeroGuid;
              v74 = v73[9];
              if ( v74 )
                v183 = (__int64 *)(v74 + 96);
              else
                v183 = &Srv2ZeroGuid;
              v113 = v73[7];
              if ( v113 )
                v171 = (__int64 *)(v113 + 24);
              else
                v171 = &Srv2ZeroGuid;
              v114 = v73[4];
              if ( v114 )
                v156 = (__int64 *)(v114 + 72);
              result = McTemplateK0xqqxxhhqqqqxqxqxqxqxqxqxxuxjjjj_EtwWriteTransfer(
                         *(unsigned __int16 *)(a1 + 612),
                         **(unsigned __int8 **)(a1 + 64),
                         v204,
                         *(_QWORD *)(v203 + 40),
                         *(_DWORD *)(v203 + 32),
                         *(_DWORD *)(v203 + 36),
                         *(_QWORD *)(v203 + 24),
                         v202,
                         v191,
                         *(_WORD *)(v203 + 14),
                         *(_DWORD *)(v203 + 16),
                         v190,
                         **(_BYTE **)(a1 + 64),
                         *(_WORD *)(a1 + 602),
                         1000000000LL * *(_QWORD *)(a1 + 624) / PerformanceFrequency.QuadPart,
                         *(_WORD *)(a1 + 604),
                         1000000000LL * *(_QWORD *)(a1 + 632) / PerformanceFrequency.QuadPart,
                         *(_WORD *)(a1 + 606),
                         1000000000LL * *(_QWORD *)(a1 + 640) / PerformanceFrequency.QuadPart,
                         *(_WORD *)(a1 + 608),
                         1000000000LL * *(_QWORD *)(a1 + 648) / PerformanceFrequency.QuadPart,
                         *(_WORD *)(a1 + 610),
                         1000000000LL * *(_QWORD *)(a1 + 656) / PerformanceFrequency.QuadPart,
                         *(_WORD *)(a1 + 612),
                         1000000000LL * *(_QWORD *)(a1 + 664) / PerformanceFrequency.QuadPart,
                         *(_WORD *)(a1 + 616),
                         1000000000LL * *(_QWORD *)(a1 + 680) / PerformanceFrequency.QuadPart,
                         1000000000LL * *(_QWORD *)(a1 + 688) / PerformanceFrequency.QuadPart,
                         *(_BYTE *)(v203 + 66),
                         *(_QWORD *)(v203 + 72),
                         *(_QWORD *)(*(_QWORD *)(a1 + 96) + 496LL) + 72LL,
                         (__int64)v156,
                         (__int64)v171,
                         (__int64)v183);
            }
          }
          else if ( (Microsoft_Windows_SMBServerEnableBits & 2) != 0 )
          {
            v115 = *(_QWORD **)(a1 + 560);
            v158 = &Srv2ZeroGuid;
            v116 = v115[9];
            if ( v116 )
              v186 = (__int64 *)(v116 + 96);
            else
              v186 = &Srv2ZeroGuid;
            v117 = v115[7];
            if ( v117 )
              v172 = (__int64 *)(v117 + 24);
            else
              v172 = &Srv2ZeroGuid;
            v118 = v115[4];
            if ( v118 )
              v158 = (__int64 *)(v118 + 72);
            v119 = *(_WORD *)(a1 + 610);
            v120 = *(_WORD *)(a1 + 608);
            v121 = *(_WORD *)(a1 + 606);
            v122 = *(_WORD *)(a1 + 604);
            *(_QWORD *)&v208 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 496LL) + 72LL;
            v196 = *(unsigned __int16 *)(a1 + 612);
            result = McTemplateK0xqqxxhhqqqqxqxqxqxqxqxqxxqqijjjjj_EtwWriteTransfer(
                       v196,
                       **(unsigned __int8 **)(a1 + 64),
                       v204,
                       *(_QWORD *)(v203 + 40),
                       *(_DWORD *)(v203 + 32),
                       *(_DWORD *)(v203 + 36),
                       *(_QWORD *)(v203 + 24),
                       v202,
                       v191,
                       *(_WORD *)(v203 + 14),
                       *(_DWORD *)(v203 + 16),
                       v190,
                       **(_BYTE **)(a1 + 64),
                       *(_WORD *)(a1 + 602),
                       1000000000LL * *(_QWORD *)(a1 + 624) / PerformanceFrequency.QuadPart,
                       v122,
                       1000000000LL * *(_QWORD *)(a1 + 632) / PerformanceFrequency.QuadPart,
                       v121,
                       1000000000LL * *(_QWORD *)(a1 + 640) / PerformanceFrequency.QuadPart,
                       v120,
                       1000000000LL * *(_QWORD *)(a1 + 648) / PerformanceFrequency.QuadPart,
                       v119,
                       1000000000LL * *(_QWORD *)(a1 + 656) / PerformanceFrequency.QuadPart,
                       v196,
                       1000000000LL * *(_QWORD *)(a1 + 664) / PerformanceFrequency.QuadPart,
                       *(_WORD *)(a1 + 616),
                       1000000000LL * *(_QWORD *)(a1 + 680) / PerformanceFrequency.QuadPart,
                       1000000000LL * *(_QWORD *)(a1 + 688) / PerformanceFrequency.QuadPart,
                       *(_DWORD *)(v203 + 68),
                       *(_DWORD *)(v203 + 88),
                       *(_QWORD *)(v203 + 92),
                       v203 + 72,
                       v208,
                       (__int64)v158,
                       (__int64)v172,
                       (__int64)v186);
          }
          break;
        default:
          return result;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400014d0  push    rbp
0x1400014d2  push    rbx
0x1400014d3  push    rsi
0x1400014d4  push    rdi
0x1400014d5  lea     rbp, [rsp-28h]
0x1400014da  sub     rsp, 218h
0x1400014e1  mov     rax, cs:__security_cookie
0x1400014e8  xor     rax, rsp
0x1400014eb  mov     [rbp+40h+var_30], rax
0x1400014ef  mov     rax, [rcx+138h]
0x1400014f6  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1400014fd  mov     [rbp+40h+var_58], rsi
0x140001501  xorps   xmm0, xmm0
0x140001504  mov     [rbp+40h+var_70], rsi
0x140001508  mov     rbx, rcx
0x14000150b  lea     rsi, [rcx+248h]
0x140001512  cmp     byte ptr [rsi+10h], 0
0x140001516  mov     rdi, [rax+18h]
0x14000151a  mov     [rbp+40h+var_68], rdi
0x14000151e  mov     [rbp+40h+var_60], rsi
0x140001522  movups  [rbp+40h+var_40], xmm0
0x140001526  jnz     loc_140002BB3
0x14000152c  mov     rax, [rbx+1A0h]
0x140001533  test    rax, rax
0x140001536  jnz     loc_140002E10
0x14000153c  mov     [rsp+230h+arg_8], r12
0x140001544  lea     rcx, [rbp+40h+PerformanceFrequency]; PerformanceFrequency
0x140001548  mov     [rsp+230h+arg_10], r13
0x140001550  xor     esi, esi
0x140001552  mov     [rsp+230h+arg_18], r14
0x14000155a  mov     [rsp+230h+var_20], r15
0x140001562  mov     qword ptr [rbp+40h+PerformanceFrequency], rsi
0x140001566  call    cs:__imp_KeQueryPerformanceCounter
0x14000156d  nop     dword ptr [rax+rax+00h]
0x140001572  mov     eax, [rdi+8]
0x140001575  mov     [rbp+40h+var_A0], eax
0x140001578  test    eax, eax
0x14000157a  js      loc_140002E27
0x140001580  movzx   eax, word ptr [rdi+0Ch]
0x140001584  mov     [rbp+40h+var_9C], eax
0x140001587  cmp     eax, 0Ah
0x14000158a  jnz     short loc_14000159F
0x14000158c  test    cs:Microsoft_Windows_SMBServerEnableBits, 2
0x140001593  jnz     loc_140001D96
0x140001599  jmp     def_14000185A; jumptable 000000014000185A default case, cases 8,10,12
0x14000159f  cmp     eax, 8
0x1400015a2  jnz     loc_140001840
0x1400015a8  test    cs:Microsoft_Windows_SMBServerEnableBits, 2
0x1400015af  jz      def_14000185A; jumptable 000000014000185A default case, cases 8,10,12
0x1400015b5  mov     rcx, [rbx+230h]
0x1400015bc  lea     rax, Srv2ZeroGuid
0x1400015c3  mov     [rbp+40h+var_C0], rax
0x1400015c7  mov     rdx, [rcx+48h]
0x1400015cb  test    rdx, rdx
0x1400015ce  jnz     loc_140001B15
0x1400015d4  mov     [rbp+40h+var_B0], rax
0x1400015d8  mov     rdx, [rcx+38h]
0x1400015dc  test    rdx, rdx
0x1400015df  jz      loc_140001837
0x1400015e5  add     rdx, 18h
0x1400015e9  mov     [rbp+40h+var_B8], rdx
0x1400015ed  mov     rax, [rcx+20h]
0x1400015f1  test    rax, rax
0x1400015f4  jnz     loc_140003046
0x1400015fa  mov     rcx, qword ptr [rbp+40h+PerformanceFrequency]
0x1400015fe  mov     rax, [rbx+60h]
0x140001602  movzx   r12d, word ptr [rbx+262h]
0x14000160a  movzx   r14d, word ptr [rbx+260h]
0x140001612  movzx   edi, word ptr [rbx+25Eh]
0x140001619  mov     rax, [rax+1F0h]
0x140001620  add     rax, 48h ; 'H'
0x140001624  movzx   r10d, word ptr [rbx+25Ch]
0x14000162c  mov     qword ptr [rbp+40h+var_40], rax
0x140001630  imul    rax, [rbx+2B0h], 3B9ACA00h
0x14000163b  movzx   r8d, word ptr [rbx+25Ah]
0x140001643  cqo
0x140001645  idiv    rcx
0x140001648  mov     [rbp+40h+var_88], rax
0x14000164c  imul    rax, [rbx+2A8h], 3B9ACA00h
0x140001657  cqo
0x140001659  idiv    rcx
0x14000165c  mov     [rbp+40h+var_90], rax
0x140001660  movzx   eax, word ptr [rbx+268h]
0x140001667  mov     dword ptr [rbp+40h+var_A8], eax
0x14000166a  imul    rax, [rbx+2A0h], 3B9ACA00h
0x140001675  cqo
0x140001677  idiv    rcx
0x14000167a  mov     [rbp+40h+var_50], rax
0x14000167e  movzx   eax, word ptr [rbx+266h]
0x140001685  mov     dword ptr [rbp+40h+var_98], eax
0x140001688  imul    rax, [rbx+298h], 3B9ACA00h
0x140001693  cqo
0x140001695  idiv    rcx
0x140001698  mov     r13, rax
0x14000169b  movzx   eax, word ptr [rbx+264h]
0x1400016a2  mov     dword ptr [rbp+40h+var_80], eax
0x1400016a5  imul    rax, [rbx+290h], 3B9ACA00h
0x1400016b0  cqo
0x1400016b2  idiv    rcx
0x1400016b5  mov     r15, rax
0x1400016b8  imul    rax, [rbx+288h], 3B9ACA00h
0x1400016c3  cqo
0x1400016c5  idiv    rcx
0x1400016c8  mov     rsi, rax
0x1400016cb  imul    rax, [rbx+280h], 3B9ACA00h
0x1400016d6  cqo
0x1400016d8  idiv    rcx
0x1400016db  mov     r11, rax
0x1400016de  imul    rax, [rbx+278h], 3B9ACA00h
0x1400016e9  cqo
0x1400016eb  idiv    rcx
0x1400016ee  mov     r9, rax
0x1400016f1  imul    rax, [rbx+270h], 3B9ACA00h
0x1400016fc  cqo
0x1400016fe  idiv    rcx
0x140001701  mov     rcx, [rbx+40h]
0x140001705  mov     rbx, [rbp+40h+var_68]
0x140001709  movzx   edx, byte ptr [rcx]
0x14000170c  mov     rcx, [rbp+40h+var_58]
0x140001710  mov     [rsp+230h+var_118], rcx
0x140001718  mov     rcx, [rbp+40h+var_B0]
0x14000171c  mov     [rsp+230h+var_120], rcx
0x140001724  mov     rcx, [rbp+40h+var_B8]
0x140001728  mov     [rsp+230h+var_128], rcx
0x140001730  mov     rcx, [rbp+40h+var_C0]
0x140001734  mov     [rsp+230h+var_130], rcx
0x14000173c  mov     rcx, qword ptr [rbp+40h+var_40]
0x140001740  mov     [rsp+230h+var_138], rcx
0x140001748  mov     ecx, [rbx+44h]
0x14000174b  mov     dword ptr [rsp+230h+var_140], ecx
0x140001752  mov     rcx, [rbp+40h+var_88]
0x140001756  mov     [rsp+230h+var_148], rcx
0x14000175e  mov     rcx, [rbp+40h+var_90]
0x140001762  mov     [rsp+230h+var_150], rcx
0x14000176a  mov     ecx, dword ptr [rbp+40h+var_A8]
0x14000176d  mov     dword ptr [rsp+230h+var_158], ecx
0x140001774  mov     rcx, [rbp+40h+var_50]
0x140001778  mov     [rsp+230h+var_160], rcx
0x140001780  mov     ecx, dword ptr [rbp+40h+var_98]
0x140001783  mov     dword ptr [rsp+230h+var_168], ecx
0x14000178a  mov     ecx, dword ptr [rbp+40h+var_80]
0x14000178d  mov     [rsp+230h+var_170], r13
0x140001795  mov     dword ptr [rsp+230h+var_178], ecx
0x14000179c  mov     [rsp+230h+var_180], r15
0x1400017a4  mov     dword ptr [rsp+230h+var_188], r12d
0x1400017ac  mov     [rsp+230h+var_190], rsi
0x1400017b4  mov     dword ptr [rsp+230h+var_198], r14d
0x1400017bc  mov     [rsp+230h+var_1A0], r11
0x1400017c4  mov     dword ptr [rsp+230h+var_1A8], edi
0x1400017cb  mov     [rsp+230h+var_1B0], r9
0x1400017d3  mov     r9, [rbx+28h]
0x1400017d7  mov     dword ptr [rsp+230h+var_1B8], r10d
0x1400017dc  mov     [rsp+230h+var_1C0], rax
0x1400017e1  mov     eax, [rbp+40h+var_A0]
0x1400017e4  mov     dword ptr [rsp+230h+var_1C8], r8d
0x1400017e9  mov     r8, [rbp+40h+var_60]
0x1400017ed  mov     dword ptr [rsp+230h+var_1D0], edx
0x1400017f1  mov     [rsp+230h+var_1D8], eax
0x1400017f5  mov     eax, [rbx+10h]
0x1400017f8  mov     [rsp+230h+var_1E0], eax
0x1400017fc  movzx   eax, word ptr [rbx+0Eh]
0x140001800  mov     [rsp+230h+var_1E8], ax
0x140001805  mov     eax, [rbp+40h+var_9C]
0x140001808  mov     [rsp+230h+var_1F0], ax
0x14000180d  mov     rax, [rbp+40h+var_70]
0x140001811  mov     [rsp+230h+var_1F8], rax
0x140001816  mov     rax, [rbx+18h]
0x14000181a  mov     [rsp+230h+var_200], rax
0x14000181f  mov     eax, [rbx+24h]
0x140001822  mov     [rsp+230h+Priority], eax
0x140001826  mov     eax, [rbx+20h]
0x140001829  mov     [rsp+230h+BugCheckOnFailure], eax
0x14000182d  call    McTemplateK0xqqxxhhqqqqxqxqxqxqxqxqxqxxqjjjjx_EtwWriteTransfer
0x140001832  jmp     def_14000185A; jumptable 000000014000185A default case, cases 8,10,12
0x140001837  mov     [rbp+40h+var_B8], rax
0x14000183b  jmp     loc_1400015ED
0x140001840  cmp     eax, 12h; switch 19 cases
0x140001843  ja      def_14000185A; jumptable 000000014000185A default case, cases 8,10,12
0x140001849  lea     rdx, cs:140000000h
0x140001850  mov     ecx, ds:(jpt_14000185A - 140000000h)[rdx+rax*4]
0x140001857  add     rcx, rdx
0x14000185a  jmp     rcx; switch jump
0x140001860  test    cs:Microsoft_Windows_SMBServerEnableBits, 2; jumptable 000000014000185A case 9
0x140001867  jz      def_14000185A; jumptable 000000014000185A default case, cases 8,10,12
0x14000186d  mov     rcx, [rbx+230h]
0x140001874  lea     rax, Srv2ZeroGuid
0x14000187b  mov     [rbp+40h+var_C0], rax
0x14000187f  mov     rdx, [rcx+48h]
0x140001883  test    rdx, rdx
0x140001886  jnz     loc_140001FDE
0x14000188c  mov     [rbp+40h+var_B0], rax
0x140001890  mov     rdx, [rcx+38h]
0x140001894  test    rdx, rdx
0x140001897  jnz     loc_140001FFA
0x14000189d  mov     [rbp+40h+var_B8], rax
0x1400018a1  mov     rax, [rcx+20h]
0x1400018a5  test    rax, rax
0x1400018a8  jnz     loc_140002F34
0x1400018ae  mov     rcx, qword ptr [rbp+40h+PerformanceFrequency]
0x1400018b2  mov     rax, [rbx+60h]
0x1400018b6  movzx   r13d, word ptr [rbx+262h]
0x1400018be  movzx   r15d, word ptr [rbx+260h]
0x1400018c6  movzx   esi, word ptr [rbx+25Eh]
0x1400018cd  mov     rax, [rax+1F0h]
0x1400018d4  add     rax, 48h ; 'H'
0x1400018d8  movzx   r11d, word ptr [rbx+25Ch]
0x1400018e0  mov     [rbp+40h+var_88], rax
0x1400018e4  imul    rax, [rbx+2B0h], 3B9ACA00h
0x1400018ef  movzx   r9d, word ptr [rbx+25Ah]
0x1400018f7  cqo
0x1400018f9  idiv    rcx
0x1400018fc  mov     [rbp+40h+var_90], rax
0x140001900  imul    rax, [rbx+2A8h], 3B9ACA00h
0x14000190b  cqo
0x14000190d  idiv    rcx
0x140001910  mov     [rbp+40h+var_50], rax
0x140001914  movzx   eax, word ptr [rbx+268h]
0x14000191b  mov     dword ptr [rbp+40h+var_A8], eax
0x14000191e  imul    rax, [rbx+2A0h], 3B9ACA00h
0x140001929  cqo
0x14000192b  idiv    rcx
0x14000192e  mov     [rbp+40h+var_48], rax
0x140001932  movzx   eax, word ptr [rbx+266h]
0x140001939  mov     dword ptr [rbp+40h+var_98], eax
0x14000193c  imul    rax, [rbx+298h], 3B9ACA00h
0x140001947  cqo
0x140001949  idiv    rcx
0x14000194c  mov     qword ptr [rbp+40h+var_40], rax
0x140001950  movzx   eax, word ptr [rbx+264h]
0x140001957  mov     dword ptr [rbp+40h+var_80], eax
0x14000195a  imul    rax, [rbx+290h], 3B9ACA00h
0x140001965  cqo
0x140001967  idiv    rcx
0x14000196a  mov     r12, rax
0x14000196d  imul    rax, [rbx+288h], 3B9ACA00h
0x140001978  cqo
0x14000197a  idiv    rcx
0x14000197d  mov     r14, rax
0x140001980  imul    rax, [rbx+280h], 3B9ACA00h
0x14000198b  cqo
0x14000198d  idiv    rcx
0x140001990  mov     rdi, rax
0x140001993  imul    rax, [rbx+278h], 3B9ACA00h
0x14000199e  cqo
0x1400019a0  idiv    rcx
0x1400019a3  mov     r10, rax
0x1400019a6  imul    rax, [rbx+270h], 3B9ACA00h
0x1400019b1  cqo
0x1400019b3  idiv    rcx
0x1400019b6  mov     rcx, [rbx+40h]
0x1400019ba  mov     rbx, [rbp+40h+var_68]
0x1400019be  mov     r8, rax
0x1400019c1  mov     rax, [rbp+40h+var_B0]
0x1400019c5  movzx   edx, byte ptr [rcx]
0x1400019c8  mov     rcx, [rbp+40h+var_58]
0x1400019cc  mov     [rsp+230h+var_100], rcx
0x1400019d4  mov     rcx, [rbp+40h+var_C0]
0x1400019d8  mov     [rsp+230h+var_108], rax
0x1400019e0  mov     rax, [rbp+40h+var_B8]
0x1400019e4  mov     [rsp+230h+var_110], rax
0x1400019ec  mov     rax, [rbp+40h+var_88]
0x1400019f0  mov     [rsp+230h+var_118], rcx
0x1400019f8  movzx   ecx, word ptr [rbx+4Eh]
0x1400019fc  mov     [rsp+230h+var_120], rax
0x140001a04  mov     eax, [rbx+44h]
0x140001a07  mov     word ptr [rsp+230h+var_128], cx
0x140001a0f  movzx   ecx, word ptr [rbx+4Ch]
0x140001a13  mov     word ptr [rsp+230h+var_130], cx
0x140001a1b  mov     ecx, [rbx+48h]
0x140001a1e  mov     dword ptr [rsp+230h+var_138], ecx
0x140001a25  mov     dword ptr [rsp+230h+var_140], eax
0x140001a2c  mov     rax, [rbp+40h+var_90]
0x140001a30  mov     [rsp+230h+var_148], rax
0x140001a38  mov     rax, [rbp+40h+var_50]
0x140001a3c  mov     [rsp+230h+var_150], rax
0x140001a44  mov     eax, dword ptr [rbp+40h+var_A8]
0x140001a47  mov     dword ptr [rsp+230h+var_158], eax
0x140001a4e  mov     rax, [rbp+40h+var_48]
0x140001a52  mov     [rsp+230h+var_160], rax
0x140001a5a  mov     eax, dword ptr [rbp+40h+var_98]
0x140001a5d  mov     dword ptr [rsp+230h+var_168], eax
0x140001a64  mov     rax, qword ptr [rbp+40h+var_40]
0x140001a68  mov     [rsp+230h+var_170], rax
0x140001a70  mov     eax, dword ptr [rbp+40h+var_80]
0x140001a73  mov     dword ptr [rsp+230h+var_178], eax
0x140001a7a  mov     eax, [rbp+40h+var_A0]
0x140001a7d  mov     [rsp+230h+var_180], r12
0x140001a85  mov     dword ptr [rsp+230h+var_188], r13d
0x140001a8d  mov     [rsp+230h+var_190], r14
0x140001a95  mov     dword ptr [rsp+230h+var_198], r15d
0x140001a9d  mov     [rsp+230h+var_1A0], rdi
0x140001aa5  mov     dword ptr [rsp+230h+var_1A8], esi
0x140001aac  mov     [rsp+230h+var_1B0], r10
0x140001ab4  mov     dword ptr [rsp+230h+var_1B8], r11d
0x140001ab9  mov     [rsp+230h+var_1C0], r8
0x140001abe  mov     r8, [rbp+40h+var_60]
0x140001ac2  mov     dword ptr [rsp+230h+var_1C8], r9d
0x140001ac7  mov     r9, [rbx+28h]
0x140001acb  mov     dword ptr [rsp+230h+var_1D0], edx
0x140001acf  mov     [rsp+230h+var_1D8], eax
  ... truncated ...
```
