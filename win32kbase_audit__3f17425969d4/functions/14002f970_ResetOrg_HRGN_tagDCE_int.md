# ResetOrg(HRGN__ *,tagDCE *,int)

- ea: `0x14002f970`
- end: `0x1400309c4`
- name: `?ResetOrg@@YAXPEAUHRGN__@@PEAUtagDCE@@H@Z`
- size: `4180`
- prototype: `void __fastcall(HRGN, unsigned __int64, KAFFINITY ProcessorHistory, __int64)`
- caller_count: `2`
- callee_count: `36`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140038210`
- `0x140040c10`

## callees

- `0x1400260d0`
- `0x140026cc8`
- `0x14002a1d0`
- `0x14002cca4`
- `0x14002de30`
- `0x14002f850`
- `0x14002f8b0`
- `0x14002f970`
- `0x140031190`
- `0x140031520`
- `0x1400317e0`
- `0x140031c20`
- `0x140031c90`
- `0x140031fa0`
- `0x140032300`
- `0x1400323a0`
- `0x1400324c0`
- `0x14003405c`
- `0x140035008`
- `0x14003d28c`
- `0x140040b64`
- `0x1400771b8`
- `0x140077494`
- `0x1400782b0`
- `0x140078fb0`
- `0x140079250`
- `0x140079330`
- `0x1400798ac`
- `0x140079cd0`
- `0x140079f00`
- `0x14007a030`
- `0x14007a5a0`
- `0x140156e9c`
- `0x140192b70`
- `0x1402388e0`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14002ff37`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14002ff37`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002fc91`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002fe75`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400300d0`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002fc91`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002fe75`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400300d0`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002fa3e`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002fa6f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002fab4`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002fae1`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002fa3e`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002fa6f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002fab4`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002fae1`
- `WIN32K!W32GetSessionState` at `0x14002fc66`
- `WIN32K!W32GetSessionState` at `0x14002fde5`
- `WIN32K!W32GetSessionState` at `0x14002fe45`
- `WIN32K!W32GetSessionState` at `0x14002ff43`
- `WIN32K!W32GetSessionState` at `0x140030036`
- `WIN32K!W32GetSessionState` at `0x14003019f`
- `WIN32K!W32GetSessionState` at `0x14003025e`
- `WIN32K!W32GetSessionState` at `0x14003030d`
- `WIN32K!W32GetSessionState` at `0x1400305a1`
- `WIN32K!W32GetSessionState` at `0x14002fc66`
- `WIN32K!W32GetSessionState` at `0x14002fde5`
- `WIN32K!W32GetSessionState` at `0x14002fe45`
- `WIN32K!W32GetSessionState` at `0x14002ff43`
- `WIN32K!W32GetSessionState` at `0x140030036`
- `WIN32K!W32GetSessionState` at `0x14003019f`
- `WIN32K!W32GetSessionState` at `0x14003025e`
- `WIN32K!W32GetSessionState` at `0x14003030d`
- `WIN32K!W32GetSessionState` at `0x1400305a1`
- `WIN32K!W32GetUserSessionState` at `0x14002fce4`
- `WIN32K!W32GetUserSessionState` at `0x14002fce4`

## pseudocode

```c
void __fastcall ResetOrg(HRGN a1, unsigned __int64 a2, KAFFINITY ProcessorHistory, __int64 a4)
{
  __int64 v4; // rax
  unsigned __int64 v6; // r14
  __int64 v7; // rcx
  int v8; // eax
  int *v9; // rbx
  __m128i v10; // xmm6
  LONG v11; // r13d
  LONG v12; // r12d
  struct tagMONITOR *v13; // rcx
  int (*v14)(void); // rax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64); // rax
  __int64 v17; // rdi
  int (*v18)(void); // rax
  __int64 (__fastcall *v19)(__int64); // rax
  __int64 v20; // rax
  int v21; // r9d
  int v22; // esi
  int v23; // edi
  __int64 v24; // rax
  int v25; // esi
  int v26; // edi
  int v27; // r13d
  volatile signed __int16 *v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rdi
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rcx
  _QWORD *v37; // rax
  unsigned __int64 *v38; // rcx
  __int64 v39; // rax
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // rax
  __int64 v45; // rcx
  __int64 SessionState; // rax
  __int64 v47; // rax
  __int64 v48; // rcx
  __int64 v49; // rdi
  __int64 *v50; // rax
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // rcx
  _QWORD *v54; // rax
  struct Gre::Base::SESSION_GLOBALS *v55; // r12
  HSEMAPHORE v56; // rdi
  DC *v57; // rcx
  struct _ENTRY *v58; // rax
  __int64 v59; // rdx
  __int64 v60; // rcx
  __int64 v61; // r8
  __int64 v62; // r9
  _QWORD *v63; // r14
  __int64 v64; // rcx
  __int64 v65; // r8
  __int64 v66; // rbx
  __int64 v67; // r13
  unsigned int v68; // ebx
  __int64 v69; // rdx
  __int64 v70; // rcx
  __int64 v71; // r8
  __int64 v72; // r9
  __int64 v73; // rbx
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rcx
  DC *v77; // rbx
  __int64 v78; // r15
  unsigned int *v79; // r14
  _QWORD *v80; // rax
  unsigned __int64 v81; // rdx
  __int64 v82; // r8
  __int64 v83; // rax
  unsigned __int64 v84; // rcx
  __int64 v85; // rcx
  _QWORD *v86; // rax
  __int64 v87; // r9
  __int64 v88; // r11
  __int64 v89; // rax
  int v90; // eax
  int v91; // r10d
  bool v92; // zf
  __int64 v93; // rax
  __int64 v94; // r14
  __int64 v95; // r8
  __int64 v96; // r9
  DC *v97; // rbx
  DC *v98; // rcx
  struct _ENTRY *v99; // rax
  __int64 v100; // rdx
  __int64 v101; // r8
  __int64 v102; // r9
  DC *v103; // rbx
  __int64 v104; // rdx
  __int64 v105; // rcx
  __int64 v106; // r8
  __int64 v107; // r9
  struct _GRETHREAD *v108; // rax
  __int64 v109; // rax
  _QWORD **v110; // rcx
  __int64 *v111; // rdx
  __int64 v112; // rax
  __int64 v113; // rax
  __int64 v114; // rcx
  __int64 v115; // rax
  __int64 v116; // rdx
  __int64 v117; // r12
  __int64 v118; // r10
  unsigned int (__fastcall **v119)(const struct REGION_CORE *); // rdi
  const struct REGION_CORE *v120; // rsi
  int v121; // ebx
  _DWORD *v122; // rcx
  LONG v123; // r14d
  LONG v124; // ebx
  __int64 *v125; // r11
  __int64 v126; // r11
  bool v127; // cc
  __int64 v128; // rax
  int v129; // eax
  bool v130; // cc
  __m128i v131; // xmm0
  __m128i v132; // xmm0
  __int64 v133; // rdx
  __int64 v134; // r8
  __int64 v135; // r9
  _DWORD *i; // rdx
  __int64 v137; // rcx
  __int64 v138; // rbx
  __int64 v139; // r10
  __int64 v140; // rdx
  unsigned __int64 v141; // [rsp+30h] [rbp-D0h] BYREF
  __m128i v142; // [rsp+38h] [rbp-C8h]
  __int64 v143; // [rsp+48h] [rbp-B8h] BYREF
  DC *v144; // [rsp+50h] [rbp-B0h] BYREF
  int v145; // [rsp+58h] [rbp-A8h]
  struct Gre::Base::SESSION_GLOBALS *v146; // [rsp+60h] [rbp-A0h]
  __int64 v147; // [rsp+68h] [rbp-98h]
  __int128 v148; // [rsp+70h] [rbp-90h] BYREF
  __int128 v149; // [rsp+80h] [rbp-80h]
  __int128 v150; // [rsp+90h] [rbp-70h] BYREF
  __int128 v151; // [rsp+A0h] [rbp-60h]
  __int64 v152; // [rsp+B0h] [rbp-50h]
  __int64 v153; // [rsp+C0h] [rbp-40h] BYREF
  int v154; // [rsp+C8h] [rbp-38h]
  __int64 v155; // [rsp+D0h] [rbp-30h]
  __int64 v156; // [rsp+D8h] [rbp-28h]
  __int128 v157; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v158; // [rsp+F0h] [rbp-10h]
  volatile signed __int16 *v159; // [rsp+100h] [rbp+0h] BYREF
  __int64 v160; // [rsp+108h] [rbp+8h] BYREF
  struct tagMONITOR *v161; // [rsp+110h] [rbp+10h]
  int v162; // [rsp+130h] [rbp+30h]
  __int64 v163; // [rsp+138h] [rbp+38h] BYREF
  __int64 v164; // [rsp+140h] [rbp+40h] BYREF
  _QWORD **v165; // [rsp+148h] [rbp+48h]
  int v166; // [rsp+168h] [rbp+68h]
  __int64 v167; // [rsp+170h] [rbp+70h] BYREF
  __int64 v168; // [rsp+178h] [rbp+78h] BYREF
  struct tagMONITOR *v169; // [rsp+180h] [rbp+80h]
  int v170; // [rsp+1A0h] [rbp+A0h]
  struct _RECTL v171; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v172; // [rsp+1B8h] [rbp+B8h]

  v4 = *(_QWORD *)(a2 + 80);
  LODWORD(v143) = ProcessorHistory;
  v6 = a2;
  v171 = 0;
  v7 = *(_QWORD *)(v4 + 40);
  if ( (*(_WORD *)(v7 + 42) & 0x2FFF) == 0x29D )
  {
    v9 = (int *)(a2 + 48);
    v38 = *(unsigned __int64 **)(W32GetUserSessionState(v7, a2) + 56744);
    v8 = *(_DWORD *)(v6 + 48);
    a2 = *v38;
    v11 = *(_DWORD *)(*v38 + 32) - *(_DWORD *)(*v38 + 24);
    v12 = *(_DWORD *)(*v38 + 36) - *(_DWORD *)(*v38 + 28);
    v171.bottom = v12;
    v171.right = v11;
    v10 = (__m128i)v171;
  }
  else
  {
    v8 = *(_DWORD *)(a2 + 48);
    v9 = (int *)(a2 + 48);
    if ( (v8 & 1) != 0 )
    {
      v10 = *(__m128i *)(v7 + 88);
      v11 = *(_DWORD *)(v7 + 96);
    }
    else
    {
      v10 = *(__m128i *)(v7 + 104);
      v11 = *(_DWORD *)(v7 + 112);
    }
    v12 = _mm_cvtsi128_si32(_mm_srli_si128(v10, 12));
    v171 = (struct _RECTL)v10;
  }
  v13 = *(struct tagMONITOR **)(v6 + 72);
  if ( !v13 || (v8 & 0x4000) != 0 )
  {
    v142.m128i_i32[0] = v10.m128i_i32[0];
    LODWORD(v141) = _mm_cvtsi128_si32(_mm_srli_si128(v10, 4));
  }
  else
  {
    v142 = *(__m128i *)(*((_QWORD *)v13 + 5) + 28LL);
    v132 = _mm_srli_si128(v142, 4);
    ProcessorHistory = (unsigned int)(v171.left - v142.m128i_i32[0]);
    v11 -= v142.m128i_i32[0];
    v142.m128i_i32[0] = ProcessorHistory;
    a2 = (unsigned int)-_mm_cvtsi128_si32(v132);
    v171.left = ProcessorHistory;
    v171.right = v11;
    v12 += a2;
    LODWORD(v141) = a2 + v171.top;
    v171.bottom = v12;
    v171.top += a2;
    if ( a1 )
      SetMonitorRegion(v13, a1, a1);
    v10 = (__m128i)v171;
  }
  if ( (*v9 & 0x4000000) != 0 )
    goto LABEL_29;
  v13 = *(struct tagMONITOR **)(W32GetWin32kBaseApiSetTable(v13) + 48);
  v14 = (int (*)(void))*((_QWORD *)v13 + 275);
  if ( !v14 || v14() < 0 )
    goto LABEL_39;
  v15 = *(_QWORD *)(v6 + 80);
  a2 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v13) + 48);
  v16 = *(__int64 (__fastcall **)(__int64))(a2 + 2208);
  v17 = v16 ? v16(v15) : 0LL;
  if ( !v17 )
    goto LABEL_39;
  if ( (*(_DWORD *)(*(_QWORD *)(v17 + 40) + 24LL) & 0x20000000) == 0
    || (v13 = *(struct tagMONITOR **)(W32GetWin32kBaseApiSetTable(v13) + 48),
        (v18 = (int (*)(void))*((_QWORD *)v13 + 277)) == 0)
    || v18() < 0
    || (v13 = *(struct tagMONITOR **)(W32GetWin32kBaseApiSetTable(v13) + 48),
        (v19 = (__int64 (__fastcall *)(__int64))*((_QWORD *)v13 + 278)) == 0)
    || !v19(v17) )
  {
LABEL_29:
    if ( a1 )
    {
      RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)&v167, a1, 0, 0);
      v30 = v167;
      if ( v167 )
      {
        v171 = 0;
        RGNOBJ::vSet((RGNOBJ *)&v167, &v171);
        v30 = v167;
      }
      if ( !v170 )
      {
        RGNOBJ::UpdateUserRgn((RGNOBJ *)&v167);
        v30 = v167;
      }
      if ( v30 )
        _InterlockedDecrement16((volatile signed __int16 *)(v30 + 12));
      v31 = v168;
      if ( *(__int64 **)(v168 + 8) != &v168 || (v13 = v169, a2 = (unsigned __int64)&v168, *(__int64 **)v169 != &v168) )
LABEL_44:
        __fastfail(3u);
      *(_QWORD *)v169 = v168;
      *(_QWORD *)(v31 + 8) = v13;
    }
LABEL_39:
    v27 = v141;
    goto LABEL_40;
  }
  v20 = *(_QWORD *)(v17 + 40);
  v21 = v142.m128i_i32[0];
  v22 = *(_DWORD *)(v20 + 88);
  v23 = *(_DWORD *)(v20 + 92);
  v24 = *(_QWORD *)(v6 + 72);
  if ( v24 && *v9 < 0 )
  {
    v21 = v22 + v142.m128i_i32[0];
    v11 += v22;
    v12 += v23;
    a2 = (unsigned int)(v23 + v141);
    v13 = (struct tagMONITOR *)(unsigned int)(v22 + v142.m128i_i32[0]);
    v142 = *(__m128i *)(*(_QWORD *)(v24 + 40) + 28LL);
    v129 = v142.m128i_i32[0];
    v130 = v21 <= v142.m128i_i32[0];
    v131 = _mm_srli_si128(v142, 8);
    if ( v21 <= v142.m128i_i32[0] )
      v21 = v142.m128i_i32[0];
    ProcessorHistory = (unsigned int)_mm_cvtsi128_si32(v131);
    if ( !v130 )
      v129 = (int)v13;
    if ( v11 < (int)ProcessorHistory )
      ProcessorHistory = (unsigned int)v11;
    else
      v11 = ProcessorHistory;
    if ( v129 >= (int)ProcessorHistory )
      goto LABEL_177;
    if ( (int)a2 <= v142.m128i_i32[1] )
      a2 = v142.m128i_u32[1];
    LODWORD(v141) = a2;
    if ( v12 >= v142.m128i_i32[3] )
      v12 = v142.m128i_i32[3];
    if ( (int)a2 >= v12 )
    {
LABEL_177:
      v12 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
      LODWORD(v141) = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 4));
      v171 = 0;
      v11 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
      v21 = _mm_cvtsi128_si32((__m128i)0LL);
    }
  }
  v25 = -v22;
  v26 = -v23;
  a4 = (unsigned int)(v25 + v21);
  v171.right = v25 + v11;
  v27 = v26 + v141;
  v142.m128i_i32[0] = a4;
  v171.left = a4;
  v171.bottom = v26 + v12;
  v171.top = v26 + v141;
  if ( !a1 )
    goto LABEL_28;
  RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)&v159, a1, 0, 0);
  v28 = v159;
  v141 = 0;
  if ( v159 )
  {
    v141 = __PAIR64__(v26, v25);
    if ( WPP_MAIN_CB.Dpc.ProcessorHistory )
    {
      v119 = *(unsigned int (__fastcall ***)(const struct REGION_CORE *))WPP_MAIN_CB.Dpc.ProcessorHistory;
      v120 = (const struct REGION_CORE *)(v159 + 12);
      v121 = (*(__int64 (__fastcall **)(_DWORD *, unsigned __int64 *))(*(_QWORD *)WPP_MAIN_CB.Dpc.ProcessorHistory + 96LL))(
               (_DWORD *)v159 + 6,
               &v141);
      RgnCaptureLiveMemoryDumpOnZeroSizedScan(v119, v120);
      if ( v121 )
      {
        ProcessorHistory = WPP_MAIN_CB.Dpc.ProcessorHistory;
        if ( WPP_MAIN_CB.Dpc.ProcessorHistory )
        {
          v122 = v159 + 12;
          if ( !v159 )
            v122 = 0;
          (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)WPP_MAIN_CB.Dpc.ProcessorHistory + 32LL))(v122);
          v28 = v159;
          goto LABEL_21;
        }
      }
    }
    else
    {
      if ( *((_DWORD *)v159 + 12) == 1 )
        goto LABEL_21;
      v115 = *((int *)v159 + 13);
      v116 = *((int *)v159 + 15);
      if ( (int)v115 >= (int)v116 )
        goto LABEL_21;
      v117 = *((int *)v159 + 14);
      v118 = *((int *)v159 + 16);
      if ( (int)v117 >= (int)v118 )
        goto LABEL_21;
      a4 = v25 + v115;
      if ( (unsigned __int64)(a4 + 0x80000000LL) <= 0xFFFFFFFF )
      {
        v138 = v26 + v118;
        if ( (unsigned __int64)(v138 + 0x80000000LL) <= 0xFFFFFFFF )
        {
          v139 = v25 + v116;
          if ( (unsigned __int64)(v139 + 0x80000000LL) <= 0xFFFFFFFF )
          {
            v140 = v26 + v117;
            if ( (unsigned __int64)(v140 + 0x80000000LL) <= 0xFFFFFFFF
              && (((a4 & 0xF8000000) + 0x8000000) & 0xF7FFFFFF) == 0
              && (((v138 & 0xF8000000) + 0x8000000) & 0xF7FFFFFF) == 0
              && (((v139 & 0xF8000000) + 0x8000000) & 0xF7FFFFFF) == 0
              && (((v140 & 0xF8000000) + 0x8000000) & 0xF7FFFFFF) == 0 )
            {
              *((_DWORD *)v159 + 13) = a4;
              *((_DWORD *)v28 + 14) = v140;
              *((_DWORD *)v28 + 15) = v139;
              *((_DWORD *)v28 + 16) = v138;
              ProcessorHistory = *((unsigned int *)v159 + 12);
              for ( i = (_DWORD *)*((_QWORD *)v159 + 3);
                    (_DWORD)ProcessorHistory;
                    i = (_DWORD *)((char *)i + (unsigned int)(4 * *i + 16)) )
              {
                i[1] += v26;
                ProcessorHistory = (unsigned int)(ProcessorHistory - 1);
                i[2] += v26;
                LODWORD(v137) = *i;
                if ( *i )
                {
                  do
                  {
                    v137 = (unsigned int)(v137 - 1);
                    i[v137 + 3] += v25;
                  }
                  while ( (_DWORD)v137 );
                }
              }
              *(_DWORD *)((char *)i - (unsigned int)(4 * *(i - 1) + 16) + 8) = 0x7FFFFFFF;
              *(_DWORD *)(*((_QWORD *)v159 + 3) + 4LL) = 0x80000000;
              v28 = v159;
              goto LABEL_21;
            }
          }
        }
      }
      EngSetLastError(0x216u);
    }
    v28 = v159;
  }
LABEL_21:
  if ( !v162 )
  {
    RGNOBJ::UpdateUserRgn((RGNOBJ *)&v159);
    v28 = v159;
  }
  if ( v28 )
    _InterlockedDecrement16(v28 + 6);
  v29 = v160;
  if ( *(__int64 **)(v160 + 8) != &v160 )
    goto LABEL_44;
  v13 = v161;
  a2 = (unsigned __int64)&v160;
  if ( *(__int64 **)v161 != &v160 )
    goto LABEL_44;
  *(_QWORD *)v161 = v160;
  *(_QWORD *)(v29 + 8) = v13;
LABEL_28:
  v10 = (__m128i)v171;
LABEL_40:
  v32 = *(_QWORD *)(v6 + 16);
  v153 = 0;
  v154 = 0;
  v155 = *(_QWORD *)(W32GetSessionState(v13, a2, ProcessorHistory, a4) + 88);
  v156 = 0;
  v153 = 0;
  v154 = 0;
  v157 = 0;
  v158 = 0;
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v155);
  if ( !CurrentThreadWin32Thread || (v34 = *CurrentThreadWin32Thread) == 0 )
  {
    *(_QWORD *)&v158 = &v153;
    *((_QWORD *)&v158 + 1) = UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic;
    goto LABEL_190;
  }
  *(_QWORD *)&v158 = &v153;
  *((_QWORD *)&v158 + 1) = UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic;
  v35 = v34 + 8;
  if ( !v35 )
  {
LABEL_190:
    *((_QWORD *)&v157 + 1) = &v157;
    *(_QWORD *)&v157 = &v157;
    goto LABEL_48;
  }
  v36 = *(_QWORD *)(v35 + 88);
  v37 = (_QWORD *)(v35 + 88);
  if ( *(_QWORD **)(v36 + 8) != v37 )
    goto LABEL_44;
  *(_QWORD *)&v157 = v36;
  *((_QWORD *)&v157 + 1) = v37;
  *(_QWORD *)(v36 + 8) = &v157;
  *v37 = &v157;
LABEL_48:
  v39 = HmgShareLock(v155, v32, 1, 1);
  v153 = v39;
  if ( v39 )
  {
    *(_DWORD *)(v39 + 8LL * (*(_DWORD *)(v39 + 40) & 1) + 1016) = v142.m128i_i32[0];
    *(_DWORD *)(v153 + 8LL * (*(_DWORD *)(v153 + 40) & 1) + 1020) = v27;
    v42 = v153;
    v43 = *(_DWORD *)(v153 + 40) & 1;
    *(_DWORD *)(v153 + 1192) = *(_DWORD *)(v153 + 124) + *(_DWORD *)(v153 + 8 * v43 + 1016);
    *(_DWORD *)(v42 + 1196) = *(_DWORD *)(v42 + 128) + *(_DWORD *)(v42 + 8 * v43 + 1020);
    *(__m128i *)(v153 + 1032) = v10;
    v44 = v153;
    v45 = *(unsigned int *)(v153 + 520);
    if ( (v45 & 1) != 0 && (v45 & 2) == 0 )
    {
      v45 = (unsigned int)v45 | 4;
      *(_DWORD *)(v153 + 36) |= 0x10u;
      *(_DWORD *)(v44 + 520) = v45;
      v44 = v153;
    }
    if ( v44 )
    {
      SessionState = W32GetSessionState(v45, v42, v40, v41);
      HmgDecrementShareReferenceCount(*(_QWORD *)(SessionState + 88), v153);
      v153 = 0;
    }
  }
  v47 = v157;
  if ( *(__int128 **)(v157 + 8) != &v157 )
    goto LABEL_44;
  v48 = *((_QWORD *)&v157 + 1);
  if ( **((__int128 ***)&v157 + 1) != &v157 )
    goto LABEL_44;
  **((_QWORD **)&v157 + 1) = v157;
  *(_QWORD *)(v47 + 8) = v48;
  if ( !(_DWORD)v143 )
    return;
  v49 = *(_QWORD *)(v6 + 16);
  v144 = 0;
  v145 = 0;
  v146 = *(struct Gre::Base::SESSION_GLOBALS **)(W32GetSessionState(v48, &v157, v40, v41) + 88);
  v147 = 0;
  v144 = 0;
  v145 = 0;
  v148 = 0;
  v149 = 0;
  v50 = (__int64 *)PsGetCurrentThreadWin32Thread(v146);
  if ( !v50 || (v51 = *v50) == 0 )
  {
    *((_QWORD *)&v149 + 1) = UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic;
    *(_QWORD *)&v149 = &v144;
    goto LABEL_192;
  }
  *((_QWORD *)&v149 + 1) = UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic;
  *(_QWORD *)&v149 = &v144;
  v52 = v51 + 8;
  if ( !v52 )
  {
LABEL_192:
    *((_QWORD *)&v148 + 1) = &v148;
    *(_QWORD *)&v148 = &v148;
    goto LABEL_60;
  }
  v53 = *(_QWORD *)(v52 + 88);
  v54 = (_QWORD *)(v52 + 88);
  if ( *(_QWORD **)(v53 + 8) != v54 )
    goto LABEL_44;
  *(_QWORD *)&v148 = v53;
  *((_QWORD *)&v148 + 1) = v54;
  *(_QWORD *)(v53 + 8) = &v148;
  *v54 = &v148;
LABEL_60:
  v144 = (DC *)HmgShareLock(v146, v49, 1, 1);
  if ( !v144 )
    goto LABEL_110;
  v55 = v146;
  v56 = (HSEMAPHORE)(*(_QWORD *)v146 + 1248LL);
  GreAcquireSemaphoreInternal(v56);
  GrepAcquireLockValidate<11>();
  v57 = v144;
  *((_DWORD *)v144 + 9) |= 0x10u;
  v58 = DC::PentryFromPobj(v57, v55);
  *((_BYTE *)v58 + 15) |= 4u;
  if ( !a1 )
  {
    DC::vReleaseVis(v144, v55);
    DC::bSetDefaultRegion(v144, v133, v134, v135);
    goto LABEL_105;
  }
  PsGetCurrentProcessId();
  v63 = *(_QWORD **)(W32GetSessionState(v60, v59, v61, v62) + 88);
  v143 = *v63 + 1512LL;
  GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(v64, v143, v65);
  HANDLELOCK::HANDLELOCK(&v171, v63, a1, 1);
  if ( v171.right )
  {
    v66 = *(_QWORD *)&v171.left;
    if ( *(_BYTE *)(*(_QWORD *)&v171.left + 14LL) == 4
      && *(_WORD *)(*(_QWORD *)&v171.left + 12LL) == WORD1(a1)
      && ((v67 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v172 + 8) + 96LL))(
                   *(_QWORD *)(v172 + 8),
                   **(unsigned int **)&v171.left),
           GreGetCurrentThread(),
           !*(_WORD *)(v67 + 12))
       || *(struct _KTHREAD **)(v67 + 16) == KeGetCurrentThread()) )
    {
      v68 = *(_DWORD *)(v66 + 8) & 0xFFFFFFFE;
      if ( v68 && (unsigned int)HmgIncProcessHandleCount(0) )
      {
        HmgDecProcessHandleCount(v63, v68);
        HANDLELOCK::Pid((HANDLELOCK *)&v171, 0);
        *(_WORD *)(v67 + 14) &= ~0x10u;
      }
    }
    else
    {
      BYTE1(v171.bottom) = 1;
    }
    HANDLELOCK::vUnlock((HANDLELOCK *)&v171);
  }
  HANDLELOCK::~HANDLELOCK((HANDLELOCK *)&v171);
  SEMOBJ<20>::vUnlock(&v143);
  RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)&v163, a1, 0, 0);
  if ( !v163 )
  {
    v94 = *((_QWORD *)v55 + 533);
    goto LABEL_95;
  }
  v73 = *(_QWORD *)v144;
  v74 = W32GetSessionState(v70, v69, v71, v72);
  v75 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)(v74 + 88) + 8LL) + 16LL))(
          *(_QWORD *)(*(_QWORD *)(v74 + 88) + 8LL),
          (unsigned __int16)v73 | ((unsigned int)v73 >> 8) & 0xFF0000);
  if ( !v75
    || *(_BYTE *)(v75 + 14) != 1
    || (v76 = *(unsigned __int8 *)(v75 + 12), *(_WORD *)(v75 + 12) != WORD1(v73))
    || (*(_DWORD *)(v75 + 8) & 0xFFFFFFFE) != 0x80000012 )
  {
    v77 = v144;
    if ( (*((_DWORD *)v144 + 9) & 0x100000) != 0 )
    {
      v78 = *((_QWORD *)v144 + 6);
      if ( v78 )
      {
        v79 = (unsigned int *)v163;
        if ( v163 )
        {
          v150 = 0;
          v151 = 0;
          v80 = (_QWORD *)PsGetCurrentThreadWin32Thread(v76);
          if ( v80 && *v80 )
          {
            v83 = *v80 + 8LL;
            *(_QWORD *)&v151 = &v150;
            v84 = (unsigned __int64)UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
            *((_QWORD *)&v151 + 1) = UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
            if ( v83 )
            {
              v85 = *(_QWORD *)(v83 + 88);
              v86 = (_QWORD *)(v83 + 88);
              if ( *(_QWORD **)(v85 + 8) != v86 )
                goto LABEL_44;
              *(_QWORD *)&v150 = v85;
              v81 = (unsigned __int64)&v150;
              *((_QWORD *)&v150 + 1) = v86;
              *(_QWORD *)(v85 + 8) = &v150;
              v84 = (unsigned __int64)&v150;
              *v86 = &v150;
LABEL_81:
              v87 = 0;
              v92 = (*((_DWORD *)v77 + 9) & 0x40000) == 0;
              v152 = 0;
              if ( v92 )
              {
                v88 = *((_QWORD *)v77 + 62);
                v89 = 0;
              }
              else
              {
                v81 = *((_QWORD *)v77 + 268);
                if ( v81 )
                {
                  SURFREF::vLock((SURFREF *)&v150, (HSURF)v81);
                  v87 = v152;
                  v88 = v152;
                  v89 = v152;
                }
                else
                {
                  v88 = *(_QWORD *)(v78 + 2544);
                  v89 = 0;
                }
              }
              if ( !v88 )
              {
                v92 = v89 == 0;
LABEL_90:
                if ( v92 )
                {
LABEL_92:
                  PopThreadGuardedObject(&v150);
                  goto LABEL_93;
                }
LABEL_91:
                v93 = W32GetSessionState(v84, v81, v82, v87);
                HmgDecrementShareReferenceCount(*(_QWORD *)(v93 + 88), v152);
                goto LABEL_92;
              }
              if ( (*(_DWORD *)(v78 + 40) & 0x20000) != 0 && *(int *)(v88 + 144) < 0
                || (v90 = *((_DWORD *)v77 + 9), (v90 & 0x1000) != 0) && (v90 & 0x4000) == 0
                || (v82 = v79[13], v81 = v79[15], (_DWORD)v82 == (_DWORD)v81)
                || (v91 = v79[14], v84 = v79[16], v91 == (_DWORD)v84)
                || (_DWORD)v82 == 0x7FFFFFFF
                && (_DWORD)v84 == 0x80000000
                && v91 == 0x7FFFFFFF
                && (_DWORD)v81 == (_DWORD)v84 )
              {
                v92 = v87 == 0;
                goto LABEL_90;
              }
              v123 = v79[13];
              v124 = v91;
              if ( (*(_DWORD *)(v88 + 148) & 0x800) != 0 )
                v125 = (__int64 *)(v88 + 700);
              else
                v125 = (__int64 *)(v88 + 56);
              v126 = *v125;
              if ( (int)v82 >= (int)v81 )
              {
                if ( (int)v82 > (int)v81 )
                {
                  v123 = v81;
                  v81 = (unsigned int)v82;
                }
                v127 = v91 <= (int)v84;
              }
              else
              {
                v127 = v91 <= (int)v84;
                if ( v91 < (int)v84 )
                {
                  if ( (int)v82 >= 0 )
                  {
                    if ( (int)v126 >= (int)v81 && v91 >= 0 )
                    {
                      if ( SHIDWORD(v126) >= (int)v84 )
                      {
                        if ( !v87 )
                          goto LABEL_92;
                        goto LABEL_91;
                      }
LABEL_154:
                      v84 = HIDWORD(v126);
LABEL_155:
                      if ( (int)v81 < v123 )
                      {
                        v123 = v81;
                      }
                      else if ( (int)v84 < v124 )
                      {
                        v124 = v84;
                      }
                      v171.left = v123;
                      v171.top = v124;
                      v171.right = v81;
                      v171.bottom = v84;
                      if ( v87 )
                      {
                        v128 = W32GetSessionState(v84, v81, v82, v87);
                        HmgDecrementShareReferenceCount(*(_QWORD *)(v128 + 88), v152);
                      }
                      PopThreadGuardedObject(&v150);
                      RGNOBJ::vSet((RGNOBJ *)&v163, &v171);
                      goto LABEL_93;
                    }
LABEL_149:
                    if ( v124 < 0 )
                      v124 = 0;
                    if ( (int)v126 < (int)v81 )
                      v81 = (unsigned int)v126;
                    if ( SHIDWORD(v126) >= (int)v84 )
                      goto LABEL_155;
                    goto LABEL_154;
                  }
LABEL_147:
                  if ( v123 < 0 )
                    v123 = 0;
                  goto LABEL_149;
                }
              }
              if ( !v127 )
              {
                v124 = v84;
                v84 = (unsigned int)v91;
              }
              goto LABEL_147;
            }
          }
          else
          {
            v84 = (unsigned __int64)UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
            *(_QWORD *)&v151 = &v150;
            *((_QWORD *)&v151 + 1) = UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
          }
          *((_QWORD *)&v150 + 1) = &v150;
          *(_QWORD *)&v150 = &v150;
          goto LABEL_81;
        }
      }
    }
  }
LABEL_93:
  v94 = v163;
  if ( !(unsigned int)RGNOBJAPI::bDeleteHandle((RGNOBJAPI *)&v163) )
    goto LABEL_98;
  v163 = 0;
LABEL_95:
  v97 = v144;
  v98 = v144;
  *((_DWORD *)v144 + 9) |= 0x10u;
  v99 = DC::PentryFromPobj(v98, v55);
  *((_BYTE *)v99 + 15) |= 4u;
  GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v97 + 1112));
  v143 = *((_QWORD *)v97 + 142);
  *(_QWORD *)&v171.left = v97;
  LOBYTE(v171.right) = 1;
  RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v143, v100, v101, v102);
  *((_QWORD *)v97 + 142) = *((_QWORD *)v55 + 533);
  _reset___lambda_call_V_lambda_1___1__AcquireDcVisRgnExclusive_DC__QEAA_XZ__details_wil__QEAAXXZ(&v171);
  v103 = v144;
  GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v144 + 1112));
  *((_QWORD *)v144 + 142) = v94;
  *(_DWORD *)(v94 + 72) = _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(W32GetSessionState(
                                                                                          v105,
                                                                                          v104,
                                                                                          v106,
                                                                                          v107)
                                                                                      + 88)
                                                                          + 4248LL));
  v108 = GreGetCurrentThreadCrossSessionCheck();
  if ( v108 )
    *(_QWORD *)v108 &= ~0x4000000000uLL;
  GrePushLock::ReleaseLock((DC *)((char *)v103 + 1112));
LABEL_98:
  if ( !v166 )
    RGNOBJ::UpdateUserRgn((RGNOBJ *)&v163);
  if ( v163 )
    _InterlockedDecrement16((volatile signed __int16 *)(v163 + 12));
  v109 = v164;
  if ( *(__int64 **)(v164 + 8) != &v164 )
    goto LABEL_44;
  v110 = v165;
  v111 = &v164;
  if ( *v165 != &v164 )
    goto LABEL_44;
  *v165 = (_QWORD *)v164;
  *(_QWORD *)(v109 + 8) = v110;
LABEL_105:
  if ( v56 )
  {
    if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
      McTemplateK0pz_EtwWriteTransfer(
        (_DWORD)v110,
        (unsigned int)LockRelease,
        v95,
        (_DWORD)v56,
        (__int64)L"VisRgnPublish");
    GrepReleaseLockValidate<11>();
    GreReleaseSemaphoreSharedInternal(v56);
  }
  if ( v144 )
  {
    v112 = W32GetSessionState(v110, v111, v95, v96);
    HmgDecrementShareReferenceCount(*(_QWORD *)(v112 + 88), v144);
    v144 = 0;
  }
LABEL_110:
  v113 = v148;
  if ( *(__int128 **)(v148 + 8) != &v148 )
    goto LABEL_44;
  v114 = *((_QWORD *)&v148 + 1);
  if ( **((__int128 ***)&v148 + 1) != &v148 )
    goto LABEL_44;
  **((_QWORD **)&v148 + 1) = v148;
  *(_QWORD *)(v113 + 8) = v114;
}

```

## disassembly

```asm
0x14002f970  push    rbp
0x14002f972  push    rbx
0x14002f973  push    r12
0x14002f975  push    r13
0x14002f977  push    r14
0x14002f979  push    r15
0x14002f97b  lea     rbp, [rsp-0E8h]
0x14002f983  sub     rsp, 1E8h
0x14002f98a  movaps  [rsp+210h+var_40], xmm6
0x14002f992  mov     rax, cs:__security_cookie
0x14002f999  xor     rax, rsp
0x14002f99c  mov     [rbp+110h+var_50], rax
0x14002f9a3  mov     rax, [rdx+50h]
0x14002f9a7  mov     r15, rcx
0x14002f9aa  xorps   xmm0, xmm0
0x14002f9ad  mov     dword ptr [rsp+210h+var_1C8], r8d
0x14002f9b2  mov     r14, rdx
0x14002f9b5  movups  xmmword ptr [rbp+110h+var_68.left], xmm0
0x14002f9bc  mov     rcx, [rax+28h]
0x14002f9c0  movzx   eax, word ptr [rcx+2Ah]
0x14002f9c4  and     eax, 0FFFF2FFFh
0x14002f9c9  cmp     eax, 29Dh
0x14002f9ce  jz      loc_14002FCE4
0x14002f9d4  mov     eax, [rdx+30h]
0x14002f9d7  lea     rbx, [rdx+30h]
0x14002f9db  test    al, 1
0x14002f9dd  jnz     loc_14002FD2A
0x14002f9e3  movups  xmm6, xmmword ptr [rcx+68h]
0x14002f9e7  mov     r13d, [rcx+70h]
0x14002f9eb  movdqa  xmm0, xmm6
0x14002f9ef  psrldq  xmm0, 0Ch
0x14002f9f4  movd    r12d, xmm0
0x14002f9f9  movups  xmmword ptr [rbp+110h+var_68.left], xmm6
0x14002fa00  mov     rcx, [r14+48h]; struct tagMONITOR *
0x14002fa04  test    rcx, rcx
0x14002fa07  jnz     loc_1400306AA
0x14002fa0d  movdqa  xmm0, xmm6
0x14002fa11  movss   dword ptr [rsp+210h+var_1D8], xmm6
0x14002fa17  psrldq  xmm0, 4
0x14002fa1c  movd    dword ptr [rsp+210h+var_1E0], xmm0
0x14002fa22  test    dword ptr [rbx], 4000000h
0x14002fa28  mov     [rsp+210h+arg_10], rsi
0x14002fa30  mov     [rsp+210h+var_30], rdi
0x14002fa38  jnz     loc_14002FBE1
0x14002fa3e  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14002fa45  nop     dword ptr [rax+rax+00h]
0x14002fa4a  mov     rcx, [rax+30h]
0x14002fa4e  mov     rax, [rcx+898h]
0x14002fa55  test    rax, rax
0x14002fa58  jz      loc_14002FC52
0x14002fa5e  call    _guard_dispatch_icall
0x14002fa63  test    eax, eax
0x14002fa65  js      loc_14002FC52
0x14002fa6b  mov     rdi, [r14+50h]
0x14002fa6f  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14002fa76  nop     dword ptr [rax+rax+00h]
0x14002fa7b  mov     rdx, [rax+30h]
0x14002fa7f  mov     rax, [rdx+8A0h]
0x14002fa86  test    rax, rax
0x14002fa89  jz      loc_1400304DF
0x14002fa8f  mov     rcx, rdi
0x14002fa92  call    _guard_dispatch_icall
0x14002fa97  mov     rdi, rax
0x14002fa9a  test    rdi, rdi
0x14002fa9d  jz      loc_14002FC52
0x14002faa3  mov     rax, [rdi+28h]
0x14002faa7  test    dword ptr [rax+18h], 20000000h
0x14002faae  jz      loc_14002FBE1
0x14002fab4  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14002fabb  nop     dword ptr [rax+rax+00h]
0x14002fac0  mov     rcx, [rax+30h]
0x14002fac4  mov     rax, [rcx+8A8h]
0x14002facb  test    rax, rax
0x14002face  jz      loc_14002FBE1
0x14002fad4  call    _guard_dispatch_icall
0x14002fad9  test    eax, eax
0x14002fadb  js      loc_14002FBE1
0x14002fae1  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14002fae8  nop     dword ptr [rax+rax+00h]
0x14002faed  mov     rcx, [rax+30h]
0x14002faf1  mov     rax, [rcx+8B0h]
0x14002faf8  test    rax, rax
0x14002fafb  jz      loc_14002FBE1
0x14002fb01  mov     rcx, rdi
0x14002fb04  call    _guard_dispatch_icall
0x14002fb09  test    rax, rax
0x14002fb0c  jz      loc_14002FBE1
0x14002fb12  mov     rax, [rdi+28h]
0x14002fb16  mov     r9d, dword ptr [rsp+210h+var_1D8]
0x14002fb1b  mov     esi, [rax+58h]
0x14002fb1e  mov     edi, [rax+5Ch]
0x14002fb21  mov     rax, [r14+48h]
0x14002fb25  test    rax, rax
0x14002fb28  jnz     loc_1400305F4
0x14002fb2e  neg     esi
0x14002fb30  neg     edi
0x14002fb32  add     r13d, esi
0x14002fb35  add     r9d, esi
0x14002fb38  mov     [rbp+110h+var_68.right], r13d
0x14002fb3f  add     r12d, edi
0x14002fb42  mov     r13d, dword ptr [rsp+210h+var_1E0]
0x14002fb47  add     r13d, edi
0x14002fb4a  mov     dword ptr [rsp+210h+var_1D8], r9d
0x14002fb4f  mov     [rbp+110h+var_68.left], r9d
0x14002fb56  mov     [rbp+110h+var_68.bottom], r12d
0x14002fb5d  mov     [rbp+110h+var_68.top], r13d
0x14002fb64  test    r15, r15
0x14002fb67  jz      short loc_14002FBD8
0x14002fb69  xor     r9d, r9d; int
0x14002fb6c  lea     rcx, [rbp+110h+var_110]; this
0x14002fb70  xor     r8d, r8d; int
0x14002fb73  mov     rdx, r15; HRGN
0x14002fb76  call    ??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z; RGNOBJAPI::RGNOBJAPI(HRGN__ *,int,int)
0x14002fb7b  mov     rcx, [rbp+110h+var_110]
0x14002fb7f  mov     [rsp+210h+var_1E0], 0
0x14002fb88  test    rcx, rcx
0x14002fb8b  jnz     loc_1400303E7
0x14002fb91  cmp     [rbp+110h+var_E0], 0
0x14002fb95  jnz     short loc_14002FBA4
0x14002fb97  lea     rcx, [rbp+110h+var_110]; this
0x14002fb9b  call    ?UpdateUserRgn@RGNOBJ@@QEAAXXZ; RGNOBJ::UpdateUserRgn(void)
0x14002fba0  mov     rcx, [rbp+110h+var_110]
0x14002fba4  test    rcx, rcx
0x14002fba7  jz      short loc_14002FBAE
0x14002fba9  lock dec word ptr [rcx+0Ch]
0x14002fbae  mov     rax, [rbp+110h+var_108]
0x14002fbb2  lea     rcx, [rbp+110h+var_108]
0x14002fbb6  cmp     [rax+8], rcx
0x14002fbba  jnz     loc_14002FCDD
0x14002fbc0  mov     rcx, [rbp+110h+var_100]
0x14002fbc4  lea     rdx, [rbp+110h+var_108]
0x14002fbc8  cmp     [rcx], rdx
0x14002fbcb  jnz     loc_14002FCDD
0x14002fbd1  mov     [rcx], rax
0x14002fbd4  mov     [rax+8], rcx
0x14002fbd8  movups  xmm6, xmmword ptr [rbp+110h+var_68.left]
0x14002fbdf  jmp     short loc_14002FC57
0x14002fbe1  test    r15, r15
0x14002fbe4  jz      short loc_14002FC52
0x14002fbe6  xor     r9d, r9d; int
0x14002fbe9  lea     rcx, [rbp+110h+var_A0]; this
0x14002fbed  xor     r8d, r8d; int
0x14002fbf0  mov     rdx, r15; HRGN
0x14002fbf3  call    ??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z; RGNOBJAPI::RGNOBJAPI(HRGN__ *,int,int)
0x14002fbf8  mov     rax, [rbp+110h+var_A0]
0x14002fbfc  test    rax, rax
0x14002fbff  jnz     loc_1400304BB
0x14002fc05  cmp     [rbp+110h+var_70], 0
0x14002fc0c  jnz     short loc_14002FC1B
0x14002fc0e  lea     rcx, [rbp+110h+var_A0]; this
0x14002fc12  call    ?UpdateUserRgn@RGNOBJ@@QEAAXXZ; RGNOBJ::UpdateUserRgn(void)
0x14002fc17  mov     rax, [rbp+110h+var_A0]
0x14002fc1b  test    rax, rax
0x14002fc1e  jz      short loc_14002FC25
0x14002fc20  lock dec word ptr [rax+0Ch]
0x14002fc25  mov     rax, [rbp+110h+var_98]
0x14002fc29  lea     rcx, [rbp+110h+var_98]
0x14002fc2d  cmp     [rax+8], rcx
0x14002fc31  jnz     loc_14002FCDD
0x14002fc37  mov     rcx, [rbp+110h+var_90]
0x14002fc3e  lea     rdx, [rbp+110h+var_98]
0x14002fc42  cmp     [rcx], rdx
0x14002fc45  jnz     loc_14002FCDD
0x14002fc4b  mov     [rcx], rax
0x14002fc4e  mov     [rax+8], rcx
0x14002fc52  mov     r13d, dword ptr [rsp+210h+var_1E0]
0x14002fc57  mov     rdi, [r14+10h]
0x14002fc5b  xor     r12d, r12d
0x14002fc5e  mov     [rbp+110h+var_150], r12
0x14002fc62  mov     [rbp+110h+var_148], r12d
0x14002fc66  call    cs:__imp_W32GetSessionState
0x14002fc6d  nop     dword ptr [rax+rax+00h]
0x14002fc72  xorps   xmm0, xmm0
0x14002fc75  mov     rcx, [rax+58h]
0x14002fc79  mov     [rbp+110h+var_140], rcx
0x14002fc7d  mov     [rbp+110h+var_138], r12
0x14002fc81  mov     [rbp+110h+var_150], r12
0x14002fc85  mov     [rbp+110h+var_148], r12d
0x14002fc89  movups  [rbp+110h+var_130], xmm0
0x14002fc8d  movups  [rbp+110h+var_120], xmm0
0x14002fc91  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14002fc98  nop     dword ptr [rax+rax+00h]
0x14002fc9d  test    rax, rax
0x14002fca0  jz      loc_140030774
0x14002fca6  mov     rax, [rax]
0x14002fca9  test    rax, rax
0x14002fcac  jz      loc_140030774
0x14002fcb2  lea     rcx, [rbp+110h+var_150]
0x14002fcb6  mov     qword ptr [rbp+110h+var_120], rcx
0x14002fcba  lea     rbx, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDCOBJA@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic(void *)
0x14002fcc1  mov     qword ptr [rbp+110h+var_120+8], rbx
0x14002fcc5  add     rax, 8
0x14002fcc9  jz      loc_140030787
0x14002fccf  mov     rcx, [rax+58h]
0x14002fcd3  add     rax, 58h ; 'X'
0x14002fcd7  cmp     [rcx+8], rax
0x14002fcdb  jz      short loc_14002FD37
0x14002fcdd  mov     ecx, 3
0x14002fce2  int     29h; Win8: RtlFailFast(ecx)
0x14002fce4  call    cs:__imp_W32GetUserSessionState
0x14002fceb  nop     dword ptr [rax+rax+00h]
0x14002fcf0  lea     rbx, [r14+30h]
0x14002fcf4  mov     rcx, [rax+0DDA8h]
0x14002fcfb  mov     eax, [rbx]
0x14002fcfd  mov     rdx, [rcx]
0x14002fd00  mov     r13d, [rdx+20h]
0x14002fd04  sub     r13d, [rdx+18h]
0x14002fd08  mov     r12d, [rdx+24h]
0x14002fd0c  sub     r12d, [rdx+1Ch]
0x14002fd10  mov     [rbp+110h+var_68.bottom], r12d
0x14002fd17  mov     [rbp+110h+var_68.right], r13d
0x14002fd1e  movups  xmm6, xmmword ptr [rbp+110h+var_68.left]
0x14002fd25  jmp     loc_14002FA00
0x14002fd2a  movups  xmm6, xmmword ptr [rcx+58h]
0x14002fd2e  mov     r13d, [rcx+60h]
0x14002fd32  jmp     loc_14002F9EB
0x14002fd37  mov     qword ptr [rbp+110h+var_130], rcx
0x14002fd3b  lea     rdx, [rbp+110h+var_130]
0x14002fd3f  mov     qword ptr [rbp+110h+var_130+8], rax
0x14002fd43  mov     [rcx+8], rdx
0x14002fd47  lea     rcx, [rbp+110h+var_130]
0x14002fd4b  mov     [rax], rcx
0x14002fd4e  mov     rcx, [rbp+110h+var_140]
0x14002fd52  mov     esi, 1
0x14002fd57  mov     r9d, esi
0x14002fd5a  movzx   r8d, sil
0x14002fd5e  mov     rdx, rdi
0x14002fd61  call    ?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14002fd66  mov     [rbp+110h+var_150], rax
0x14002fd6a  test    rax, rax
0x14002fd6d  jz      loc_14002FE02
0x14002fd73  mov     ecx, [rax+28h]
0x14002fd76  mov     edx, dword ptr [rsp+210h+var_1D8]
0x14002fd7a  and     ecx, esi
0x14002fd7c  mov     [rax+rcx*8+3F8h], edx
0x14002fd83  mov     rcx, [rbp+110h+var_150]
0x14002fd87  mov     eax, [rcx+28h]
0x14002fd8a  and     eax, esi
0x14002fd8c  mov     [rcx+rax*8+3FCh], r13d
0x14002fd94  mov     rdx, [rbp+110h+var_150]
0x14002fd98  mov     eax, [rdx+28h]
0x14002fd9b  and     eax, esi
0x14002fd9d  mov     ecx, eax
0x14002fd9f  mov     eax, [rdx+rax*8+3F8h]
0x14002fda6  add     eax, [rdx+7Ch]
0x14002fda9  mov     [rdx+4A8h], eax
0x14002fdaf  mov     eax, [rdx+rcx*8+3FCh]
0x14002fdb6  add     eax, [rdx+80h]
0x14002fdbc  mov     [rdx+4ACh], eax
0x14002fdc2  mov     rax, [rbp+110h+var_150]
0x14002fdc6  movups  xmmword ptr [rax+408h], xmm6
0x14002fdcd  mov     rax, [rbp+110h+var_150]
0x14002fdd1  mov     ecx, [rax+208h]
0x14002fdd7  test    sil, cl
0x14002fdda  jnz     loc_140030951
0x14002fde0  test    rax, rax
0x14002fde3  jz      short loc_14002FE02
0x14002fde5  call    cs:__imp_W32GetSessionState
0x14002fdec  nop     dword ptr [rax+rax+00h]
0x14002fdf1  mov     rdx, [rbp+110h+var_150]
0x14002fdf5  mov     rcx, [rax+58h]
0x14002fdf9  call    HmgDecrementShareReferenceCount
0x14002fdfe  mov     [rbp+110h+var_150], r12
0x14002fe02  mov     rax, qword ptr [rbp+110h+var_130]
0x14002fe06  lea     rcx, [rbp+110h+var_130]
0x14002fe0a  cmp     [rax+8], rcx
0x14002fe0e  jnz     loc_14002FCDD
0x14002fe14  mov     rcx, qword ptr [rbp+110h+var_130+8]
0x14002fe18  lea     rdx, [rbp+110h+var_130]
0x14002fe1c  cmp     [rcx], rdx
0x14002fe1f  jnz     loc_14002FCDD
0x14002fe25  mov     [rcx], rax
0x14002fe28  mov     [rax+8], rcx
0x14002fe2c  cmp     dword ptr [rsp+210h+var_1C8], r12d
0x14002fe31  jz      loc_14003035E
0x14002fe37  mov     rdi, [r14+10h]
0x14002fe3b  mov     [rsp+210h+var_1C0], r12
0x14002fe40  mov     [rsp+210h+var_1B8], r12d
0x14002fe45  call    cs:__imp_W32GetSessionState
0x14002fe4c  nop     dword ptr [rax+rax+00h]
0x14002fe51  xorps   xmm0, xmm0
0x14002fe54  mov     rcx, [rax+58h]
0x14002fe58  mov     [rsp+210h+var_1B0], rcx
0x14002fe5d  mov     [rsp+210h+var_1A8], r12
0x14002fe62  mov     [rsp+210h+var_1C0], r12
0x14002fe67  mov     [rsp+210h+var_1B8], r12d
0x14002fe6c  movups  [rsp+210h+var_1A0], xmm0
0x14002fe71  movups  [rbp+110h+var_190], xmm0
0x14002fe75  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14002fe7c  nop     dword ptr [rax+rax+00h]
0x14002fe81  test    rax, rax
0x14002fe84  jz      loc_14003079C
0x14002fe8a  mov     rax, [rax]
0x14002fe8d  test    rax, rax
0x14002fe90  jz      loc_14003079C
0x14002fe96  mov     qword ptr [rbp+110h+var_190+8], rbx
0x14002fe9a  lea     rcx, [rsp+210h+var_1C0]
0x14002fe9f  mov     qword ptr [rbp+110h+var_190], rcx
0x14002fea3  add     rax, 8
0x14002fea7  jz      loc_1400307A9
  ... truncated ...
```
