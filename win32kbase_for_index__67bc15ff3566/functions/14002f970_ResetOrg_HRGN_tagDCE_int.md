# ResetOrg(HRGN__ *,tagDCE *,int)

- ea: `0x14002f970`
- end: `0x1400309c4`
- name: `?ResetOrg@@YAXPEAUHRGN__@@PEAUtagDCE@@H@Z`
- size: `4180`
- prototype: `void __fastcall(HRGN, struct tagDCE *, int)`
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
void __fastcall ResetOrg(HRGN a1, unsigned __int64 a2, __int64 a3)
{
  __int64 v3; // rax
  unsigned __int64 v5; // r14
  __int64 v6; // rcx
  int v7; // eax
  int *v8; // rbx
  __m128i v9; // xmm6
  LONG v10; // r13d
  LONG v11; // r12d
  struct tagMONITOR *v12; // rcx
  int (*v13)(void); // rax
  __int64 v14; // rdx
  __int64 v15; // rdi
  __int64 v16; // rdx
  __int64 (__fastcall *v17)(__int64); // rax
  __int64 v18; // rdi
  int (*v19)(void); // rax
  __int64 v20; // rdx
  __int64 (__fastcall *v21)(__int64); // rax
  __int64 v22; // rax
  int v23; // r9d
  int v24; // esi
  int v25; // edi
  __int64 v26; // rax
  int v27; // esi
  int v28; // edi
  int v29; // r13d
  volatile signed __int16 *v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rdi
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rcx
  _QWORD *v42; // rax
  unsigned __int64 *v43; // rcx
  __int64 v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // rax
  __int64 v48; // rcx
  __int64 SessionState; // rax
  __int64 v50; // rax
  __int64 v51; // rcx
  __int64 v52; // rdi
  __int64 v53; // rdx
  __int64 v54; // r8
  __int64 v55; // r9
  __int64 *v56; // rax
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // rcx
  _QWORD *v60; // rax
  struct Gre::Base::SESSION_GLOBALS *v61; // r12
  HSEMAPHORE v62; // rdi
  DC *v63; // rcx
  struct _ENTRY *v64; // rax
  __int64 v65; // rcx
  _QWORD *v66; // r14
  __int64 v67; // rcx
  __int64 v68; // rbx
  __int64 v69; // r13
  __int64 v70; // rdx
  __int64 v71; // r8
  unsigned int v72; // ebx
  __int64 v73; // rcx
  __int64 v74; // rbx
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // rdx
  __int64 v78; // rcx
  __int64 v79; // r8
  __int64 v80; // r9
  DC *v81; // rbx
  __int64 v82; // r15
  _DWORD *v83; // r14
  _QWORD *v84; // rax
  __int64 v85; // rax
  unsigned __int64 v86; // rcx
  __int64 v87; // rcx
  _QWORD *v88; // rax
  __int64 v89; // r9
  __int64 v90; // r11
  __int64 v91; // rax
  int v92; // eax
  int v93; // r8d
  LONG v94; // edx
  int v95; // r10d
  bool v96; // zf
  __int64 v97; // rax
  __int64 v98; // r14
  int v99; // r8d
  DC *v100; // rbx
  DC *v101; // rcx
  struct _ENTRY *v102; // rax
  DC *v103; // rbx
  __int64 v104; // rcx
  struct _GRETHREAD *v105; // rax
  __int64 v106; // rax
  _QWORD **v107; // rcx
  __int64 v108; // rax
  __int64 v109; // rax
  __int64 v110; // rcx
  __int64 v111; // rax
  __int64 v112; // rdx
  __int64 v113; // r12
  __int64 v114; // r10
  __int64 v115; // r9
  const struct BaseRustExports *v116; // rdi
  const struct REGION_CORE *v117; // rsi
  int v118; // ebx
  _DWORD *v119; // rcx
  LONG v120; // r14d
  LONG v121; // ebx
  __int64 *v122; // r11
  __int64 v123; // r11
  bool v124; // cc
  __int64 v125; // rax
  __int32 v126; // edx
  __int32 v127; // eax
  bool v128; // cc
  __m128i v129; // xmm0
  int v130; // r8d
  __m128i v131; // xmm0
  HSURF v132; // rdx
  int v133; // r8d
  _DWORD *i; // rdx
  __int64 v135; // rcx
  __int64 v136; // rbx
  __int64 v137; // r10
  __int64 v138; // rdx
  unsigned __int64 v139; // [rsp+30h] [rbp-D0h] BYREF
  __m128i v140; // [rsp+38h] [rbp-C8h]
  __int64 v141; // [rsp+48h] [rbp-B8h] BYREF
  DC *v142; // [rsp+50h] [rbp-B0h] BYREF
  int v143; // [rsp+58h] [rbp-A8h]
  struct Gre::Base::SESSION_GLOBALS *v144; // [rsp+60h] [rbp-A0h]
  __int64 v145; // [rsp+68h] [rbp-98h]
  __int128 v146; // [rsp+70h] [rbp-90h] BYREF
  __int128 v147; // [rsp+80h] [rbp-80h]
  __int128 v148; // [rsp+90h] [rbp-70h] BYREF
  __int128 v149; // [rsp+A0h] [rbp-60h]
  __int64 v150; // [rsp+B0h] [rbp-50h]
  __int64 v151; // [rsp+C0h] [rbp-40h] BYREF
  int v152; // [rsp+C8h] [rbp-38h]
  __int64 v153; // [rsp+D0h] [rbp-30h]
  __int64 v154; // [rsp+D8h] [rbp-28h]
  __int128 v155; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v156; // [rsp+F0h] [rbp-10h]
  volatile signed __int16 *v157; // [rsp+100h] [rbp+0h] BYREF
  __int64 v158; // [rsp+108h] [rbp+8h] BYREF
  struct tagMONITOR *v159; // [rsp+110h] [rbp+10h]
  int v160; // [rsp+130h] [rbp+30h]
  __int64 v161; // [rsp+138h] [rbp+38h] BYREF
  __int64 v162; // [rsp+140h] [rbp+40h] BYREF
  _QWORD **v163; // [rsp+148h] [rbp+48h]
  int v164; // [rsp+168h] [rbp+68h]
  __int64 v165; // [rsp+170h] [rbp+70h] BYREF
  __int64 v166; // [rsp+178h] [rbp+78h] BYREF
  struct tagMONITOR *v167; // [rsp+180h] [rbp+80h]
  int v168; // [rsp+1A0h] [rbp+A0h]
  struct _RECTL v169; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v170; // [rsp+1B8h] [rbp+B8h]

  v3 = *(_QWORD *)(a2 + 80);
  LODWORD(v141) = a3;
  v5 = a2;
  v169 = 0;
  v6 = *(_QWORD *)(v3 + 40);
  if ( (*(_WORD *)(v6 + 42) & 0x2FFF) == 0x29D )
  {
    v8 = (int *)(a2 + 48);
    v43 = *(unsigned __int64 **)(W32GetUserSessionState(v6, a2, a3) + 56744);
    v7 = *(_DWORD *)(v5 + 48);
    a2 = *v43;
    v10 = *(_DWORD *)(*v43 + 32) - *(_DWORD *)(*v43 + 24);
    v11 = *(_DWORD *)(*v43 + 36) - *(_DWORD *)(*v43 + 28);
    v169.bottom = v11;
    v169.right = v10;
    v9 = (__m128i)v169;
  }
  else
  {
    v7 = *(_DWORD *)(a2 + 48);
    v8 = (int *)(a2 + 48);
    if ( (v7 & 1) != 0 )
    {
      v9 = *(__m128i *)(v6 + 88);
      v10 = *(_DWORD *)(v6 + 96);
    }
    else
    {
      v9 = *(__m128i *)(v6 + 104);
      v10 = *(_DWORD *)(v6 + 112);
    }
    v11 = _mm_cvtsi128_si32(_mm_srli_si128(v9, 12));
    v169 = (struct _RECTL)v9;
  }
  v12 = *(struct tagMONITOR **)(v5 + 72);
  if ( !v12 || (v7 & 0x4000) != 0 )
  {
    v140.m128i_i32[0] = v9.m128i_i32[0];
    LODWORD(v139) = _mm_cvtsi128_si32(_mm_srli_si128(v9, 4));
  }
  else
  {
    v140 = *(__m128i *)(*((_QWORD *)v12 + 5) + 28LL);
    v131 = _mm_srli_si128(v140, 4);
    v10 -= v140.m128i_i32[0];
    v140.m128i_i32[0] = v169.left - v140.m128i_i32[0];
    a2 = (unsigned int)-_mm_cvtsi128_si32(v131);
    v169.left = v140.m128i_i32[0];
    v169.right = v10;
    v11 += a2;
    LODWORD(v139) = a2 + v169.top;
    v169.bottom = v11;
    v169.top += a2;
    if ( a1 )
      SetMonitorRegion(v12, a1, a1);
    v9 = (__m128i)v169;
  }
  if ( (*v8 & 0x4000000) != 0 )
    goto LABEL_29;
  v12 = *(struct tagMONITOR **)(W32GetWin32kBaseApiSetTable(v12, a2) + 48);
  v13 = (int (*)(void))*((_QWORD *)v12 + 275);
  if ( !v13 || v13() < 0 )
    goto LABEL_39;
  v15 = *(_QWORD *)(v5 + 80);
  v16 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v12, v14) + 48);
  v17 = *(__int64 (__fastcall **)(__int64))(v16 + 2208);
  v18 = v17 ? v17(v15) : 0LL;
  if ( !v18 )
    goto LABEL_39;
  if ( (*(_DWORD *)(*(_QWORD *)(v18 + 40) + 24LL) & 0x20000000) == 0
    || (v12 = *(struct tagMONITOR **)(W32GetWin32kBaseApiSetTable(v12, v16) + 48),
        (v19 = (int (*)(void))*((_QWORD *)v12 + 277)) == 0)
    || v19() < 0
    || (v12 = *(struct tagMONITOR **)(W32GetWin32kBaseApiSetTable(v12, v20) + 48),
        (v21 = (__int64 (__fastcall *)(__int64))*((_QWORD *)v12 + 278)) == 0)
    || !v21(v18) )
  {
LABEL_29:
    if ( a1 )
    {
      RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)&v165, a1, 0, 0);
      v32 = v165;
      if ( v165 )
      {
        v169 = 0;
        RGNOBJ::vSet((RGNOBJ *)&v165, &v169);
        v32 = v165;
      }
      if ( !v168 )
      {
        RGNOBJ::UpdateUserRgn((RGNOBJ *)&v165);
        v32 = v165;
      }
      if ( v32 )
        _InterlockedDecrement16((volatile signed __int16 *)(v32 + 12));
      v33 = v166;
      if ( *(__int64 **)(v166 + 8) != &v166 || (v12 = v167, *(__int64 **)v167 != &v166) )
LABEL_44:
        __fastfail(3u);
      *(_QWORD *)v167 = v166;
      *(_QWORD *)(v33 + 8) = v12;
    }
LABEL_39:
    v29 = v139;
    goto LABEL_40;
  }
  v22 = *(_QWORD *)(v18 + 40);
  v23 = v140.m128i_i32[0];
  v24 = *(_DWORD *)(v22 + 88);
  v25 = *(_DWORD *)(v22 + 92);
  v26 = *(_QWORD *)(v5 + 72);
  if ( v26 && *v8 < 0 )
  {
    v23 = v24 + v140.m128i_i32[0];
    v10 += v24;
    v11 += v25;
    v126 = v25 + v139;
    v12 = (struct tagMONITOR *)(unsigned int)(v24 + v140.m128i_i32[0]);
    v140 = *(__m128i *)(*(_QWORD *)(v26 + 40) + 28LL);
    v127 = v140.m128i_i32[0];
    v128 = v23 <= v140.m128i_i32[0];
    v129 = _mm_srli_si128(v140, 8);
    if ( v23 <= v140.m128i_i32[0] )
      v23 = v140.m128i_i32[0];
    v130 = _mm_cvtsi128_si32(v129);
    if ( !v128 )
      v127 = (int)v12;
    if ( v10 < v130 )
      v130 = v10;
    else
      v10 = v130;
    if ( v127 >= v130 )
      goto LABEL_177;
    if ( v126 <= v140.m128i_i32[1] )
      v126 = v140.m128i_i32[1];
    LODWORD(v139) = v126;
    if ( v11 >= v140.m128i_i32[3] )
      v11 = v140.m128i_i32[3];
    if ( v126 >= v11 )
    {
LABEL_177:
      v11 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
      LODWORD(v139) = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 4));
      v169 = 0;
      v10 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
      v23 = _mm_cvtsi128_si32((__m128i)0LL);
    }
  }
  v27 = -v24;
  v28 = -v25;
  v169.right = v27 + v10;
  v29 = v28 + v139;
  v140.m128i_i32[0] = v27 + v23;
  v169.left = v27 + v23;
  v169.bottom = v28 + v11;
  v169.top = v28 + v139;
  if ( !a1 )
    goto LABEL_28;
  RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)&v157, a1, 0, 0);
  v30 = v157;
  v139 = 0;
  if ( v157 )
  {
    v139 = __PAIR64__(v28, v27);
    if ( WPP_MAIN_CB.Dpc.ProcessorHistory )
    {
      v116 = *(const struct BaseRustExports **)WPP_MAIN_CB.Dpc.ProcessorHistory;
      v117 = (const struct REGION_CORE *)(v157 + 12);
      v118 = (*(__int64 (__fastcall **)(_DWORD *, unsigned __int64 *))(*(_QWORD *)WPP_MAIN_CB.Dpc.ProcessorHistory + 96LL))(
               (_DWORD *)v157 + 6,
               &v139);
      RgnCaptureLiveMemoryDumpOnZeroSizedScan(v116, v117);
      if ( v118 && WPP_MAIN_CB.Dpc.ProcessorHistory )
      {
        v119 = v157 + 12;
        if ( !v157 )
          v119 = 0;
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)WPP_MAIN_CB.Dpc.ProcessorHistory + 32LL))(v119);
        v30 = v157;
        goto LABEL_21;
      }
    }
    else
    {
      if ( *((_DWORD *)v157 + 12) == 1 )
        goto LABEL_21;
      v111 = *((int *)v157 + 13);
      v112 = *((int *)v157 + 15);
      if ( (int)v111 >= (int)v112 )
        goto LABEL_21;
      v113 = *((int *)v157 + 14);
      v114 = *((int *)v157 + 16);
      if ( (int)v113 >= (int)v114 )
        goto LABEL_21;
      v115 = v27 + v111;
      if ( (unsigned __int64)(v115 + 0x80000000LL) <= 0xFFFFFFFF )
      {
        v136 = v28 + v114;
        if ( (unsigned __int64)(v136 + 0x80000000LL) <= 0xFFFFFFFF )
        {
          v137 = v27 + v112;
          if ( (unsigned __int64)(v137 + 0x80000000LL) <= 0xFFFFFFFF )
          {
            v138 = v28 + v113;
            if ( (unsigned __int64)(v138 + 0x80000000LL) <= 0xFFFFFFFF
              && (((v115 & 0xF8000000) + 0x8000000) & 0xF7FFFFFF) == 0
              && (((v136 & 0xF8000000) + 0x8000000) & 0xF7FFFFFF) == 0
              && (((v137 & 0xF8000000) + 0x8000000) & 0xF7FFFFFF) == 0
              && (((v138 & 0xF8000000) + 0x8000000) & 0xF7FFFFFF) == 0 )
            {
              *((_DWORD *)v157 + 13) = v115;
              *((_DWORD *)v30 + 14) = v138;
              *((_DWORD *)v30 + 15) = v137;
              *((_DWORD *)v30 + 16) = v136;
              v133 = *((_DWORD *)v157 + 12);
              for ( i = (_DWORD *)*((_QWORD *)v157 + 3); v133; i = (_DWORD *)((char *)i + (unsigned int)(4 * *i + 16)) )
              {
                i[1] += v28;
                --v133;
                i[2] += v28;
                LODWORD(v135) = *i;
                if ( *i )
                {
                  do
                  {
                    v135 = (unsigned int)(v135 - 1);
                    i[v135 + 3] += v27;
                  }
                  while ( (_DWORD)v135 );
                }
              }
              *(_DWORD *)((char *)i - (unsigned int)(4 * *(i - 1) + 16) + 8) = 0x7FFFFFFF;
              *(_DWORD *)(*((_QWORD *)v157 + 3) + 4LL) = 0x80000000;
              v30 = v157;
              goto LABEL_21;
            }
          }
        }
      }
      EngSetLastError(0x216u);
    }
    v30 = v157;
  }
LABEL_21:
  if ( !v160 )
  {
    RGNOBJ::UpdateUserRgn((RGNOBJ *)&v157);
    v30 = v157;
  }
  if ( v30 )
    _InterlockedDecrement16(v30 + 6);
  v31 = v158;
  if ( *(__int64 **)(v158 + 8) != &v158 )
    goto LABEL_44;
  v12 = v159;
  if ( *(__int64 **)v159 != &v158 )
    goto LABEL_44;
  *(_QWORD *)v159 = v158;
  *(_QWORD *)(v31 + 8) = v12;
LABEL_28:
  v9 = (__m128i)v169;
LABEL_40:
  v34 = *(_QWORD *)(v5 + 16);
  v151 = 0;
  v152 = 0;
  v153 = *(_QWORD *)(W32GetSessionState(v12) + 88);
  v154 = 0;
  v151 = 0;
  v152 = 0;
  v155 = 0;
  v156 = 0;
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v153, v35, v36, v37);
  if ( !CurrentThreadWin32Thread || (v39 = *CurrentThreadWin32Thread) == 0 )
  {
    *(_QWORD *)&v156 = &v151;
    *((_QWORD *)&v156 + 1) = UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic;
    goto LABEL_190;
  }
  *(_QWORD *)&v156 = &v151;
  *((_QWORD *)&v156 + 1) = UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic;
  v40 = v39 + 8;
  if ( !v40 )
  {
LABEL_190:
    *((_QWORD *)&v155 + 1) = &v155;
    *(_QWORD *)&v155 = &v155;
    goto LABEL_48;
  }
  v41 = *(_QWORD *)(v40 + 88);
  v42 = (_QWORD *)(v40 + 88);
  if ( *(_QWORD **)(v41 + 8) != v42 )
    goto LABEL_44;
  *(_QWORD *)&v155 = v41;
  *((_QWORD *)&v155 + 1) = v42;
  *(_QWORD *)(v41 + 8) = &v155;
  *v42 = &v155;
LABEL_48:
  v44 = HmgShareLock(v153, v34, 1, 1);
  v151 = v44;
  if ( v44 )
  {
    *(_DWORD *)(v44 + 8LL * (*(_DWORD *)(v44 + 40) & 1) + 1016) = v140.m128i_i32[0];
    *(_DWORD *)(v151 + 8LL * (*(_DWORD *)(v151 + 40) & 1) + 1020) = v29;
    v45 = v151;
    v46 = *(_DWORD *)(v151 + 40) & 1;
    *(_DWORD *)(v151 + 1192) = *(_DWORD *)(v151 + 124) + *(_DWORD *)(v151 + 8 * v46 + 1016);
    *(_DWORD *)(v45 + 1196) = *(_DWORD *)(v45 + 128) + *(_DWORD *)(v45 + 8 * v46 + 1020);
    *(__m128i *)(v151 + 1032) = v9;
    v47 = v151;
    v48 = *(unsigned int *)(v151 + 520);
    if ( (v48 & 1) != 0 && (v48 & 2) == 0 )
    {
      v48 = (unsigned int)v48 | 4;
      *(_DWORD *)(v151 + 36) |= 0x10u;
      *(_DWORD *)(v47 + 520) = v48;
      v47 = v151;
    }
    if ( v47 )
    {
      SessionState = W32GetSessionState(v48);
      HmgDecrementShareReferenceCount(*(_QWORD *)(SessionState + 88), v151);
      v151 = 0;
    }
  }
  v50 = v155;
  if ( *(__int128 **)(v155 + 8) != &v155 )
    goto LABEL_44;
  v51 = *((_QWORD *)&v155 + 1);
  if ( **((__int128 ***)&v155 + 1) != &v155 )
    goto LABEL_44;
  **((_QWORD **)&v155 + 1) = v155;
  *(_QWORD *)(v50 + 8) = v51;
  if ( !(_DWORD)v141 )
    return;
  v52 = *(_QWORD *)(v5 + 16);
  v142 = 0;
  v143 = 0;
  v144 = *(struct Gre::Base::SESSION_GLOBALS **)(W32GetSessionState(v51) + 88);
  v145 = 0;
  v142 = 0;
  v143 = 0;
  v146 = 0;
  v147 = 0;
  v56 = (__int64 *)PsGetCurrentThreadWin32Thread(v144, v53, v54, v55);
  if ( !v56 || (v57 = *v56) == 0 )
  {
    *((_QWORD *)&v147 + 1) = UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic;
    *(_QWORD *)&v147 = &v142;
    goto LABEL_192;
  }
  *((_QWORD *)&v147 + 1) = UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic;
  *(_QWORD *)&v147 = &v142;
  v58 = v57 + 8;
  if ( !v58 )
  {
LABEL_192:
    *((_QWORD *)&v146 + 1) = &v146;
    *(_QWORD *)&v146 = &v146;
    goto LABEL_60;
  }
  v59 = *(_QWORD *)(v58 + 88);
  v60 = (_QWORD *)(v58 + 88);
  if ( *(_QWORD **)(v59 + 8) != v60 )
    goto LABEL_44;
  *(_QWORD *)&v146 = v59;
  *((_QWORD *)&v146 + 1) = v60;
  *(_QWORD *)(v59 + 8) = &v146;
  *v60 = &v146;
LABEL_60:
  v142 = (DC *)HmgShareLock(v144, v52, 1, 1);
  if ( !v142 )
    goto LABEL_110;
  v61 = v144;
  v62 = (HSEMAPHORE)(*(_QWORD *)v144 + 1248LL);
  GreAcquireSemaphoreInternal(v62);
  GrepAcquireLockValidate<11>();
  v63 = v142;
  *((_DWORD *)v142 + 9) |= 0x10u;
  v64 = DC::PentryFromPobj(v63, v61);
  *((_BYTE *)v64 + 15) |= 4u;
  if ( !a1 )
  {
    DC::vReleaseVis(v142, v61);
    DC::bSetDefaultRegion(v142);
    goto LABEL_105;
  }
  PsGetCurrentProcessId();
  v66 = *(_QWORD **)(W32GetSessionState(v65) + 88);
  v141 = *v66 + 1512LL;
  GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(v67, v141);
  HANDLELOCK::HANDLELOCK(&v169, v66, a1, 1);
  if ( v169.right )
  {
    v68 = *(_QWORD *)&v169.left;
    if ( *(_BYTE *)(*(_QWORD *)&v169.left + 14LL) == 4
      && *(_WORD *)(*(_QWORD *)&v169.left + 12LL) == WORD1(a1)
      && ((v69 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v170 + 8) + 96LL))(
                   *(_QWORD *)(v170 + 8),
                   **(unsigned int **)&v169.left),
           GreGetCurrentThread(),
           !*(_WORD *)(v69 + 12))
       || *(struct _KTHREAD **)(v69 + 16) == KeGetCurrentThread()) )
    {
      v72 = *(_DWORD *)(v68 + 8) & 0xFFFFFFFE;
      if ( v72 && (unsigned int)HmgIncProcessHandleCount(0, v70, v71) )
      {
        HmgDecProcessHandleCount(v66, v72);
        HANDLELOCK::Pid((HANDLELOCK *)&v169, 0);
        *(_WORD *)(v69 + 14) &= ~0x10u;
      }
    }
    else
    {
      BYTE1(v169.bottom) = 1;
    }
    HANDLELOCK::vUnlock((HANDLELOCK *)&v169);
  }
  HANDLELOCK::~HANDLELOCK((HANDLELOCK *)&v169);
  SEMOBJ<20>::vUnlock(&v141);
  RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)&v161, a1, 0, 0);
  if ( !v161 )
  {
    v98 = *((_QWORD *)v61 + 533);
    goto LABEL_95;
  }
  v74 = *(_QWORD *)v142;
  v75 = W32GetSessionState(v73);
  v76 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)(v75 + 88) + 8LL) + 16LL))(
          *(_QWORD *)(*(_QWORD *)(v75 + 88) + 8LL),
          (unsigned __int16)v74 | ((unsigned int)v74 >> 8) & 0xFF0000);
  if ( !v76
    || *(_BYTE *)(v76 + 14) != 1
    || (v77 = *(unsigned __int8 *)(v76 + 13),
        v78 = *(unsigned __int8 *)(v76 + 12),
        LOWORD(v77) = v78 | ((_WORD)v77 << 8),
        (_WORD)v77 != WORD1(v74))
    || (*(_DWORD *)(v76 + 8) & 0xFFFFFFFE) != 0x80000012 )
  {
    v81 = v142;
    if ( (*((_DWORD *)v142 + 9) & 0x100000) != 0 )
    {
      v82 = *((_QWORD *)v142 + 6);
      if ( v82 )
      {
        v83 = (_DWORD *)v161;
        if ( v161 )
        {
          v148 = 0;
          v149 = 0;
          v84 = (_QWORD *)PsGetCurrentThreadWin32Thread(v78, v77, v79, v80);
          if ( v84 && *v84 )
          {
            v85 = *v84 + 8LL;
            *(_QWORD *)&v149 = &v148;
            v86 = (unsigned __int64)UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
            *((_QWORD *)&v149 + 1) = UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
            if ( v85 )
            {
              v87 = *(_QWORD *)(v85 + 88);
              v88 = (_QWORD *)(v85 + 88);
              if ( *(_QWORD **)(v87 + 8) != v88 )
                goto LABEL_44;
              *(_QWORD *)&v148 = v87;
              *((_QWORD *)&v148 + 1) = v88;
              *(_QWORD *)(v87 + 8) = &v148;
              v86 = (unsigned __int64)&v148;
              *v88 = &v148;
LABEL_81:
              v89 = 0;
              v96 = (*((_DWORD *)v81 + 9) & 0x40000) == 0;
              v150 = 0;
              if ( v96 )
              {
                v90 = *((_QWORD *)v81 + 62);
                v91 = 0;
              }
              else
              {
                v132 = (HSURF)*((_QWORD *)v81 + 268);
                if ( v132 )
                {
                  SURFREF::vLock((SURFREF *)&v148, v132);
                  v89 = v150;
                  v90 = v150;
                  v91 = v150;
                }
                else
                {
                  v90 = *(_QWORD *)(v82 + 2544);
                  v91 = 0;
                }
              }
              if ( !v90 )
              {
                v96 = v91 == 0;
LABEL_90:
                if ( v96 )
                {
LABEL_92:
                  PopThreadGuardedObject(&v148);
                  goto LABEL_93;
                }
LABEL_91:
                v97 = W32GetSessionState(v86);
                HmgDecrementShareReferenceCount(*(_QWORD *)(v97 + 88), v150);
                goto LABEL_92;
              }
              if ( (*(_DWORD *)(v82 + 40) & 0x20000) != 0 && *(int *)(v90 + 144) < 0
                || (v92 = *((_DWORD *)v81 + 9), (v92 & 0x1000) != 0) && (v92 & 0x4000) == 0
                || (v93 = v83[13], v94 = v83[15], v93 == v94)
                || (v95 = v83[14], v86 = (unsigned int)v83[16], v95 == (_DWORD)v86)
                || v93 == 0x7FFFFFFF && (_DWORD)v86 == 0x80000000 && v95 == 0x7FFFFFFF && v94 == (_DWORD)v86 )
              {
                v96 = v89 == 0;
                goto LABEL_90;
              }
              v120 = v83[13];
              v121 = v95;
              if ( (*(_DWORD *)(v90 + 148) & 0x800) != 0 )
                v122 = (__int64 *)(v90 + 700);
              else
                v122 = (__int64 *)(v90 + 56);
              v123 = *v122;
              if ( v93 >= v94 )
              {
                if ( v93 > v94 )
                {
                  v120 = v94;
                  v94 = v93;
                }
                v124 = v95 <= (int)v86;
              }
              else
              {
                v124 = v95 <= (int)v86;
                if ( v95 < (int)v86 )
                {
                  if ( v93 >= 0 )
                  {
                    if ( (int)v123 >= v94 && v95 >= 0 )
                    {
                      if ( SHIDWORD(v123) >= (int)v86 )
                      {
                        if ( !v89 )
                          goto LABEL_92;
                        goto LABEL_91;
                      }
LABEL_154:
                      v86 = HIDWORD(v123);
LABEL_155:
                      if ( v94 < v120 )
                      {
                        v120 = v94;
                      }
                      else if ( (int)v86 < v121 )
                      {
                        v121 = v86;
                      }
                      v169.left = v120;
                      v169.top = v121;
                      v169.right = v94;
                      v169.bottom = v86;
                      if ( v89 )
                      {
                        v125 = W32GetSessionState(v86);
                        HmgDecrementShareReferenceCount(*(_QWORD *)(v125 + 88), v150);
                      }
                      PopThreadGuardedObject(&v148);
                      RGNOBJ::vSet((RGNOBJ *)&v161, &v169);
                      goto LABEL_93;
                    }
LABEL_149:
                    if ( v121 < 0 )
                      v121 = 0;
                    if ( (int)v123 < v94 )
                      v94 = v123;
                    if ( SHIDWORD(v123) >= (int)v86 )
                      goto LABEL_155;
                    goto LABEL_154;
                  }
LABEL_147:
                  if ( v120 < 0 )
                    v120 = 0;
                  goto LABEL_149;
                }
              }
              if ( !v124 )
              {
                v121 = v86;
                v86 = (unsigned int)v95;
              }
              goto LABEL_147;
            }
          }
          else
          {
            v86 = (unsigned __int64)UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
            *(_QWORD *)&v149 = &v148;
            *((_QWORD *)&v149 + 1) = UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
          }
          *((_QWORD *)&v148 + 1) = &v148;
          *(_QWORD *)&v148 = &v148;
          goto LABEL_81;
        }
      }
    }
  }
LABEL_93:
  v98 = v161;
  if ( !(unsigned int)RGNOBJAPI::bDeleteHandle((RGNOBJAPI *)&v161) )
    goto LABEL_98;
  v161 = 0;
LABEL_95:
  v100 = v142;
  v101 = v142;
  *((_DWORD *)v142 + 9) |= 0x10u;
  v102 = DC::PentryFromPobj(v101, v61);
  *((_BYTE *)v102 + 15) |= 4u;
  GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v100 + 1112));
  v141 = *((_QWORD *)v100 + 142);
  *(_QWORD *)&v169.left = v100;
  LOBYTE(v169.right) = 1;
  RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v141);
  *((_QWORD *)v100 + 142) = *((_QWORD *)v61 + 533);
  _reset___lambda_call_V_lambda_1___1__AcquireDcVisRgnExclusive_DC__QEAA_XZ__details_wil__QEAAXXZ(&v169);
  v103 = v142;
  GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v142 + 1112));
  *((_QWORD *)v142 + 142) = v98;
  *(_DWORD *)(v98 + 72) = _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(W32GetSessionState(v104) + 88)
                                                                          + 4248LL));
  v105 = GreGetCurrentThreadCrossSessionCheck();
  if ( v105 )
    *(_QWORD *)v105 &= ~0x4000000000uLL;
  GrePushLock::ReleaseLock((DC *)((char *)v103 + 1112));
LABEL_98:
  if ( !v164 )
    RGNOBJ::UpdateUserRgn((RGNOBJ *)&v161);
  if ( v161 )
    _InterlockedDecrement16((volatile signed __int16 *)(v161 + 12));
  v106 = v162;
  if ( *(__int64 **)(v162 + 8) != &v162 )
    goto LABEL_44;
  v107 = v163;
  if ( *v163 != &v162 )
    goto LABEL_44;
  *v163 = (_QWORD *)v162;
  *(_QWORD *)(v106 + 8) = v107;
LABEL_105:
  if ( v62 )
  {
    if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
      McTemplateK0pz_EtwWriteTransfer(
        (_DWORD)v107,
        (unsigned int)LockRelease,
        v99,
        (_DWORD)v62,
        (__int64)L"VisRgnPublish");
    GrepReleaseLockValidate<11>();
    GreReleaseSemaphoreSharedInternal(v62);
  }
  if ( v142 )
  {
    v108 = W32GetSessionState(v107);
    HmgDecrementShareReferenceCount(*(_QWORD *)(v108 + 88), v142);
    v142 = 0;
  }
LABEL_110:
  v109 = v146;
  if ( *(__int128 **)(v146 + 8) != &v146 )
    goto LABEL_44;
  v110 = *((_QWORD *)&v146 + 1);
  if ( **((__int128 ***)&v146 + 1) != &v146 )
    goto LABEL_44;
  **((_QWORD **)&v146 + 1) = v146;
  *(_QWORD *)(v109 + 8) = v110;
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
