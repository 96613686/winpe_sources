# ResetOrg(HRGN__ *,tagDCE *,int)

- ea: `0x140023110`
- end: `0x140024164`
- name: `?ResetOrg@@YAXPEAUHRGN__@@PEAUtagDCE@@H@Z`
- size: `4180`
- prototype: `void __fastcall(HRGN, struct tagDCE *, int)`
- caller_count: `2`
- callee_count: `36`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140066fe0`
- `0x1400697e0`

## callees

- `0x140010070`
- `0x1400195ac`
- `0x140019d88`
- `0x14001d160`
- `0x140020444`
- `0x1400215d0`
- `0x140022ff0`
- `0x140023050`
- `0x140023110`
- `0x140024930`
- `0x140024cc0`
- `0x140024f80`
- `0x1400252f0`
- `0x140025360`
- `0x140025990`
- `0x140025a30`
- `0x140025b50`
- `0x140026270`
- `0x140026f60`
- `0x140027200`
- `0x1400272d4`
- `0x140027f3c`
- `0x140028360`
- `0x140028590`
- `0x140028a70`
- `0x140029748`
- `0x140029778`
- `0x140029a54`
- `0x140040ccc`
- `0x1400487d0`
- `0x140048d40`
- `0x140069734`
- `0x140153b0c`
- `0x140190760`
- `0x140238160`
- `0x140238240`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x1400236d7`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400236d7`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140023431`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140023615`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140023870`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140023431`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140023615`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140023870`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400231de`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002320f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140023254`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140023281`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400231de`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002320f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140023254`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140023281`
- `WIN32K!W32GetSessionState` at `0x140023406`
- `WIN32K!W32GetSessionState` at `0x140023585`
- `WIN32K!W32GetSessionState` at `0x1400235e5`
- `WIN32K!W32GetSessionState` at `0x1400236e3`
- `WIN32K!W32GetSessionState` at `0x1400237d6`
- `WIN32K!W32GetSessionState` at `0x14002393f`
- `WIN32K!W32GetSessionState` at `0x1400239fe`
- `WIN32K!W32GetSessionState` at `0x140023aad`
- `WIN32K!W32GetSessionState` at `0x140023d41`
- `WIN32K!W32GetSessionState` at `0x140023406`
- `WIN32K!W32GetSessionState` at `0x140023585`
- `WIN32K!W32GetSessionState` at `0x1400235e5`
- `WIN32K!W32GetSessionState` at `0x1400236e3`
- `WIN32K!W32GetSessionState` at `0x1400237d6`
- `WIN32K!W32GetSessionState` at `0x14002393f`
- `WIN32K!W32GetSessionState` at `0x1400239fe`
- `WIN32K!W32GetSessionState` at `0x140023aad`
- `WIN32K!W32GetSessionState` at `0x140023d41`
- `WIN32K!W32GetUserSessionState` at `0x140023484`
- `WIN32K!W32GetUserSessionState` at `0x140023484`

## pseudocode

```c
void __fastcall ResetOrg(HRGN a1, struct tagDCE *a2, int a3)
{
  __int64 v3; // rax
  __int64 v6; // rcx
  int v7; // eax
  int *v8; // rbx
  __m128i v9; // xmm6
  LONG v10; // r13d
  LONG v11; // r12d
  struct tagMONITOR *v12; // rcx
  int (*v13)(void); // rax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64); // rax
  __int64 v16; // rdi
  int (*v17)(void); // rax
  __int64 (__fastcall *v18)(__int64); // rax
  __int64 v19; // rax
  int v20; // r9d
  int v21; // esi
  int v22; // edi
  __int64 v23; // rax
  int v24; // esi
  int v25; // edi
  int v26; // r13d
  volatile signed __int16 *v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rdi
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rcx
  _QWORD *v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 v42; // rcx
  __int64 SessionState; // rax
  __int64 v44; // rax
  __int64 v45; // rcx
  __int64 v46; // rdi
  __int64 *v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rcx
  _QWORD *v51; // rax
  struct Gre::Base::SESSION_GLOBALS *v52; // r12
  HSEMAPHORE v53; // rdi
  DC *v54; // rcx
  struct _ENTRY *v55; // rax
  __int64 v56; // rcx
  _QWORD *v57; // r14
  __int64 v58; // rcx
  __int64 v59; // rbx
  __int64 v60; // r13
  __int64 v61; // rdx
  __int64 v62; // r8
  unsigned int v63; // ebx
  __int64 v64; // rcx
  __int64 v65; // rbx
  __int64 v66; // rax
  __int64 v67; // rax
  DC *v68; // rbx
  __int64 v69; // r15
  _DWORD *v70; // r14
  _QWORD *v71; // rax
  __int64 v72; // rax
  unsigned __int64 v73; // rcx
  __int64 v74; // rcx
  _QWORD *v75; // rax
  __int64 v76; // r9
  __int64 v77; // r11
  __int64 v78; // rax
  int v79; // eax
  int v80; // r8d
  LONG v81; // edx
  int v82; // r10d
  bool v83; // zf
  __int64 v84; // rax
  __int64 v85; // r14
  int v86; // r8d
  DC *v87; // rbx
  DC *v88; // rcx
  struct _ENTRY *v89; // rax
  DC *v90; // rbx
  __int64 v91; // rcx
  struct _GRETHREAD *v92; // rax
  __int64 v93; // rax
  _QWORD **v94; // rcx
  __int64 v95; // rax
  __int64 v96; // rax
  __int64 v97; // rcx
  __int64 v98; // rax
  __int64 v99; // rdx
  __int64 v100; // r12
  __int64 v101; // r10
  __int64 v102; // r9
  const struct BaseRustExports *v103; // rdi
  const struct REGION_CORE *v104; // rsi
  int v105; // ebx
  _DWORD *v106; // rcx
  LONG v107; // r14d
  LONG v108; // ebx
  __int64 *v109; // r11
  __int64 v110; // r11
  bool v111; // cc
  __int64 v112; // rax
  __int32 v113; // edx
  __int32 v114; // eax
  bool v115; // cc
  __m128i v116; // xmm0
  int v117; // r8d
  __m128i v118; // xmm0
  int v119; // edx
  HSURF v120; // rdx
  int v121; // r8d
  _DWORD *i; // rdx
  __int64 v123; // rcx
  __int64 v124; // rbx
  __int64 v125; // r10
  __int64 v126; // rdx
  unsigned __int64 v127; // [rsp+30h] [rbp-D0h] BYREF
  __m128i v128; // [rsp+38h] [rbp-C8h]
  __int64 v129; // [rsp+48h] [rbp-B8h] BYREF
  DC *v130; // [rsp+50h] [rbp-B0h] BYREF
  int v131; // [rsp+58h] [rbp-A8h]
  struct Gre::Base::SESSION_GLOBALS *v132; // [rsp+60h] [rbp-A0h]
  __int64 v133; // [rsp+68h] [rbp-98h]
  __int128 v134; // [rsp+70h] [rbp-90h] BYREF
  __int128 v135; // [rsp+80h] [rbp-80h]
  __int128 v136; // [rsp+90h] [rbp-70h] BYREF
  __int128 v137; // [rsp+A0h] [rbp-60h]
  __int64 v138; // [rsp+B0h] [rbp-50h]
  __int64 v139; // [rsp+C0h] [rbp-40h] BYREF
  int v140; // [rsp+C8h] [rbp-38h]
  __int64 v141; // [rsp+D0h] [rbp-30h]
  __int64 v142; // [rsp+D8h] [rbp-28h]
  __int128 v143; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v144; // [rsp+F0h] [rbp-10h]
  volatile signed __int16 *v145; // [rsp+100h] [rbp+0h] BYREF
  __int64 v146; // [rsp+108h] [rbp+8h] BYREF
  struct tagMONITOR *v147; // [rsp+110h] [rbp+10h]
  int v148; // [rsp+130h] [rbp+30h]
  __int64 v149; // [rsp+138h] [rbp+38h] BYREF
  __int64 v150; // [rsp+140h] [rbp+40h] BYREF
  _QWORD **v151; // [rsp+148h] [rbp+48h]
  int v152; // [rsp+168h] [rbp+68h]
  __int64 v153; // [rsp+170h] [rbp+70h] BYREF
  __int64 v154; // [rsp+178h] [rbp+78h] BYREF
  struct tagMONITOR *v155; // [rsp+180h] [rbp+80h]
  int v156; // [rsp+1A0h] [rbp+A0h]
  struct _RECTL v157; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v158; // [rsp+1B8h] [rbp+B8h]

  v3 = *((_QWORD *)a2 + 10);
  LODWORD(v129) = a3;
  v157 = 0;
  v6 = *(_QWORD *)(v3 + 40);
  if ( (*(_WORD *)(v6 + 42) & 0x2FFF) == 0x29D )
  {
    v8 = (int *)((char *)a2 + 48);
    v37 = *(_QWORD *)(W32GetUserSessionState(v6) + 56744);
    v7 = *((_DWORD *)a2 + 12);
    v10 = *(_DWORD *)(*(_QWORD *)v37 + 32LL) - *(_DWORD *)(*(_QWORD *)v37 + 24LL);
    v11 = *(_DWORD *)(*(_QWORD *)v37 + 36LL) - *(_DWORD *)(*(_QWORD *)v37 + 28LL);
    v157.bottom = v11;
    v157.right = v10;
    v9 = (__m128i)v157;
  }
  else
  {
    v7 = *((_DWORD *)a2 + 12);
    v8 = (int *)((char *)a2 + 48);
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
    v157 = (struct _RECTL)v9;
  }
  v12 = (struct tagMONITOR *)*((_QWORD *)a2 + 9);
  if ( !v12 || (v7 & 0x4000) != 0 )
  {
    v128.m128i_i32[0] = v9.m128i_i32[0];
    LODWORD(v127) = _mm_cvtsi128_si32(_mm_srli_si128(v9, 4));
  }
  else
  {
    v128 = *(__m128i *)(*((_QWORD *)v12 + 5) + 28LL);
    v118 = _mm_srli_si128(v128, 4);
    v10 -= v128.m128i_i32[0];
    v128.m128i_i32[0] = v157.left - v128.m128i_i32[0];
    v119 = -_mm_cvtsi128_si32(v118);
    v157.left = v128.m128i_i32[0];
    v157.right = v10;
    v11 += v119;
    LODWORD(v127) = v119 + v157.top;
    v157.bottom = v11;
    v157.top += v119;
    if ( a1 )
      SetMonitorRegion(v12, a1, a1);
    v9 = (__m128i)v157;
  }
  if ( (*v8 & 0x4000000) != 0 )
    goto LABEL_29;
  v12 = *(struct tagMONITOR **)(W32GetWin32kBaseApiSetTable() + 48);
  v13 = (int (*)(void))*((_QWORD *)v12 + 275);
  if ( !v13 || v13() < 0 )
    goto LABEL_39;
  v14 = *((_QWORD *)a2 + 10);
  v15 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 2208LL);
  v16 = v15 ? v15(v14) : 0LL;
  if ( !v16 )
    goto LABEL_39;
  if ( (*(_DWORD *)(*(_QWORD *)(v16 + 40) + 24LL) & 0x20000000) == 0
    || (v12 = *(struct tagMONITOR **)(W32GetWin32kBaseApiSetTable() + 48),
        (v17 = (int (*)(void))*((_QWORD *)v12 + 277)) == 0)
    || v17() < 0
    || (v12 = *(struct tagMONITOR **)(W32GetWin32kBaseApiSetTable() + 48),
        (v18 = (__int64 (__fastcall *)(__int64))*((_QWORD *)v12 + 278)) == 0)
    || !v18(v16) )
  {
LABEL_29:
    if ( a1 )
    {
      RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)&v153, a1, 0, 0);
      v29 = v153;
      if ( v153 )
      {
        v157 = 0;
        RGNOBJ::vSet((RGNOBJ *)&v153, &v157);
        v29 = v153;
      }
      if ( !v156 )
      {
        RGNOBJ::UpdateUserRgn((RGNOBJ *)&v153);
        v29 = v153;
      }
      if ( v29 )
        _InterlockedDecrement16((volatile signed __int16 *)(v29 + 12));
      v30 = v154;
      if ( *(__int64 **)(v154 + 8) != &v154 || (v12 = v155, *(__int64 **)v155 != &v154) )
LABEL_44:
        __fastfail(3u);
      *(_QWORD *)v155 = v154;
      *(_QWORD *)(v30 + 8) = v12;
    }
LABEL_39:
    v26 = v127;
    goto LABEL_40;
  }
  v19 = *(_QWORD *)(v16 + 40);
  v20 = v128.m128i_i32[0];
  v21 = *(_DWORD *)(v19 + 88);
  v22 = *(_DWORD *)(v19 + 92);
  v23 = *((_QWORD *)a2 + 9);
  if ( v23 && *v8 < 0 )
  {
    v20 = v21 + v128.m128i_i32[0];
    v10 += v21;
    v11 += v22;
    v113 = v22 + v127;
    v12 = (struct tagMONITOR *)(unsigned int)(v21 + v128.m128i_i32[0]);
    v128 = *(__m128i *)(*(_QWORD *)(v23 + 40) + 28LL);
    v114 = v128.m128i_i32[0];
    v115 = v20 <= v128.m128i_i32[0];
    v116 = _mm_srli_si128(v128, 8);
    if ( v20 <= v128.m128i_i32[0] )
      v20 = v128.m128i_i32[0];
    v117 = _mm_cvtsi128_si32(v116);
    if ( !v115 )
      v114 = (int)v12;
    if ( v10 < v117 )
      v117 = v10;
    else
      v10 = v117;
    if ( v114 >= v117 )
      goto LABEL_177;
    if ( v113 <= v128.m128i_i32[1] )
      v113 = v128.m128i_i32[1];
    LODWORD(v127) = v113;
    if ( v11 >= v128.m128i_i32[3] )
      v11 = v128.m128i_i32[3];
    if ( v113 >= v11 )
    {
LABEL_177:
      v11 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
      LODWORD(v127) = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 4));
      v157 = 0;
      v10 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
      v20 = _mm_cvtsi128_si32((__m128i)0LL);
    }
  }
  v24 = -v21;
  v25 = -v22;
  v157.right = v24 + v10;
  v26 = v25 + v127;
  v128.m128i_i32[0] = v24 + v20;
  v157.left = v24 + v20;
  v157.bottom = v25 + v11;
  v157.top = v25 + v127;
  if ( !a1 )
    goto LABEL_28;
  RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)&v145, a1, 0, 0);
  v27 = v145;
  v127 = 0;
  if ( v145 )
  {
    v127 = __PAIR64__(v25, v24);
    if ( WPP_MAIN_CB.Dpc.ProcessorHistory )
    {
      v103 = *(const struct BaseRustExports **)WPP_MAIN_CB.Dpc.ProcessorHistory;
      v104 = (const struct REGION_CORE *)(v145 + 12);
      v105 = (*(__int64 (__fastcall **)(_DWORD *, unsigned __int64 *))(*(_QWORD *)WPP_MAIN_CB.Dpc.ProcessorHistory + 96LL))(
               (_DWORD *)v145 + 6,
               &v127);
      RgnCaptureLiveMemoryDumpOnZeroSizedScan(v103, v104);
      if ( v105 && WPP_MAIN_CB.Dpc.ProcessorHistory )
      {
        v106 = v145 + 12;
        if ( !v145 )
          v106 = 0;
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)WPP_MAIN_CB.Dpc.ProcessorHistory + 32LL))(v106);
        v27 = v145;
        goto LABEL_21;
      }
    }
    else
    {
      if ( *((_DWORD *)v145 + 12) == 1 )
        goto LABEL_21;
      v98 = *((int *)v145 + 13);
      v99 = *((int *)v145 + 15);
      if ( (int)v98 >= (int)v99 )
        goto LABEL_21;
      v100 = *((int *)v145 + 14);
      v101 = *((int *)v145 + 16);
      if ( (int)v100 >= (int)v101 )
        goto LABEL_21;
      v102 = v24 + v98;
      if ( (unsigned __int64)(v102 + 0x80000000LL) <= 0xFFFFFFFF )
      {
        v124 = v25 + v101;
        if ( (unsigned __int64)(v124 + 0x80000000LL) <= 0xFFFFFFFF )
        {
          v125 = v24 + v99;
          if ( (unsigned __int64)(v125 + 0x80000000LL) <= 0xFFFFFFFF )
          {
            v126 = v25 + v100;
            if ( (unsigned __int64)(v126 + 0x80000000LL) <= 0xFFFFFFFF
              && (((v102 & 0xF8000000) + 0x8000000) & 0xF7FFFFFF) == 0
              && (((v124 & 0xF8000000) + 0x8000000) & 0xF7FFFFFF) == 0
              && (((v125 & 0xF8000000) + 0x8000000) & 0xF7FFFFFF) == 0
              && (((v126 & 0xF8000000) + 0x8000000) & 0xF7FFFFFF) == 0 )
            {
              *((_DWORD *)v145 + 13) = v102;
              *((_DWORD *)v27 + 14) = v126;
              *((_DWORD *)v27 + 15) = v125;
              *((_DWORD *)v27 + 16) = v124;
              v121 = *((_DWORD *)v145 + 12);
              for ( i = (_DWORD *)*((_QWORD *)v145 + 3); v121; i = (_DWORD *)((char *)i + (unsigned int)(4 * *i + 16)) )
              {
                i[1] += v25;
                --v121;
                i[2] += v25;
                LODWORD(v123) = *i;
                if ( *i )
                {
                  do
                  {
                    v123 = (unsigned int)(v123 - 1);
                    i[v123 + 3] += v24;
                  }
                  while ( (_DWORD)v123 );
                }
              }
              *(_DWORD *)((char *)i - (unsigned int)(4 * *(i - 1) + 16) + 8) = 0x7FFFFFFF;
              *(_DWORD *)(*((_QWORD *)v145 + 3) + 4LL) = 0x80000000;
              v27 = v145;
              goto LABEL_21;
            }
          }
        }
      }
      EngSetLastError(0x216u);
    }
    v27 = v145;
  }
LABEL_21:
  if ( !v148 )
  {
    RGNOBJ::UpdateUserRgn((RGNOBJ *)&v145);
    v27 = v145;
  }
  if ( v27 )
    _InterlockedDecrement16(v27 + 6);
  v28 = v146;
  if ( *(__int64 **)(v146 + 8) != &v146 )
    goto LABEL_44;
  v12 = v147;
  if ( *(__int64 **)v147 != &v146 )
    goto LABEL_44;
  *(_QWORD *)v147 = v146;
  *(_QWORD *)(v28 + 8) = v12;
LABEL_28:
  v9 = (__m128i)v157;
LABEL_40:
  v31 = *((_QWORD *)a2 + 2);
  v139 = 0;
  v140 = 0;
  v141 = *(_QWORD *)(W32GetSessionState(v12) + 88);
  v142 = 0;
  v139 = 0;
  v140 = 0;
  v143 = 0;
  v144 = 0;
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread();
  if ( !CurrentThreadWin32Thread || (v33 = *CurrentThreadWin32Thread) == 0 )
  {
    *(_QWORD *)&v144 = &v139;
    *((_QWORD *)&v144 + 1) = UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic;
    goto LABEL_190;
  }
  *(_QWORD *)&v144 = &v139;
  *((_QWORD *)&v144 + 1) = UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic;
  v34 = v33 + 8;
  if ( !v34 )
  {
LABEL_190:
    *((_QWORD *)&v143 + 1) = &v143;
    *(_QWORD *)&v143 = &v143;
    goto LABEL_48;
  }
  v35 = *(_QWORD *)(v34 + 88);
  v36 = (_QWORD *)(v34 + 88);
  if ( *(_QWORD **)(v35 + 8) != v36 )
    goto LABEL_44;
  *(_QWORD *)&v143 = v35;
  *((_QWORD *)&v143 + 1) = v36;
  *(_QWORD *)(v35 + 8) = &v143;
  *v36 = &v143;
LABEL_48:
  v38 = HmgShareLock(v141, v31, 1, 1);
  v139 = v38;
  if ( v38 )
  {
    *(_DWORD *)(v38 + 8LL * (*(_DWORD *)(v38 + 40) & 1) + 1016) = v128.m128i_i32[0];
    *(_DWORD *)(v139 + 8LL * (*(_DWORD *)(v139 + 40) & 1) + 1020) = v26;
    v39 = v139;
    v40 = *(_DWORD *)(v139 + 40) & 1;
    *(_DWORD *)(v139 + 1192) = *(_DWORD *)(v139 + 124) + *(_DWORD *)(v139 + 8 * v40 + 1016);
    *(_DWORD *)(v39 + 1196) = *(_DWORD *)(v39 + 128) + *(_DWORD *)(v39 + 8 * v40 + 1020);
    *(__m128i *)(v139 + 1032) = v9;
    v41 = v139;
    v42 = *(unsigned int *)(v139 + 520);
    if ( (v42 & 1) != 0 && (v42 & 2) == 0 )
    {
      v42 = (unsigned int)v42 | 4;
      *(_DWORD *)(v139 + 36) |= 0x10u;
      *(_DWORD *)(v41 + 520) = v42;
      v41 = v139;
    }
    if ( v41 )
    {
      SessionState = W32GetSessionState(v42);
      HmgDecrementShareReferenceCount(*(_QWORD *)(SessionState + 88), v139);
      v139 = 0;
    }
  }
  v44 = v143;
  if ( *(__int128 **)(v143 + 8) != &v143 )
    goto LABEL_44;
  v45 = *((_QWORD *)&v143 + 1);
  if ( **((__int128 ***)&v143 + 1) != &v143 )
    goto LABEL_44;
  **((_QWORD **)&v143 + 1) = v143;
  *(_QWORD *)(v44 + 8) = v45;
  if ( !(_DWORD)v129 )
    return;
  v46 = *((_QWORD *)a2 + 2);
  v130 = 0;
  v131 = 0;
  v132 = *(struct Gre::Base::SESSION_GLOBALS **)(W32GetSessionState(v45) + 88);
  v133 = 0;
  v130 = 0;
  v131 = 0;
  v134 = 0;
  v135 = 0;
  v47 = (__int64 *)PsGetCurrentThreadWin32Thread();
  if ( !v47 || (v48 = *v47) == 0 )
  {
    *((_QWORD *)&v135 + 1) = UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic;
    *(_QWORD *)&v135 = &v130;
    goto LABEL_192;
  }
  *((_QWORD *)&v135 + 1) = UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic;
  *(_QWORD *)&v135 = &v130;
  v49 = v48 + 8;
  if ( !v49 )
  {
LABEL_192:
    *((_QWORD *)&v134 + 1) = &v134;
    *(_QWORD *)&v134 = &v134;
    goto LABEL_60;
  }
  v50 = *(_QWORD *)(v49 + 88);
  v51 = (_QWORD *)(v49 + 88);
  if ( *(_QWORD **)(v50 + 8) != v51 )
    goto LABEL_44;
  *(_QWORD *)&v134 = v50;
  *((_QWORD *)&v134 + 1) = v51;
  *(_QWORD *)(v50 + 8) = &v134;
  *v51 = &v134;
LABEL_60:
  v130 = (DC *)HmgShareLock(v132, v46, 1, 1);
  if ( !v130 )
    goto LABEL_110;
  v52 = v132;
  v53 = (HSEMAPHORE)(*(_QWORD *)v132 + 1248LL);
  GreAcquireSemaphoreInternal(v53);
  GrepAcquireLockValidate<11>();
  v54 = v130;
  *((_DWORD *)v130 + 9) |= 0x10u;
  v55 = DC::PentryFromPobj(v54, v52);
  *((_BYTE *)v55 + 15) |= 4u;
  if ( !a1 )
  {
    DC::vReleaseVis(v130, v52);
    DC::bSetDefaultRegion(v130);
    goto LABEL_105;
  }
  PsGetCurrentProcessId();
  v57 = *(_QWORD **)(W32GetSessionState(v56) + 88);
  v129 = *v57 + 1512LL;
  GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(v58, v129);
  HANDLELOCK::HANDLELOCK(&v157, v57, a1, 1);
  if ( v157.right )
  {
    v59 = *(_QWORD *)&v157.left;
    if ( *(_BYTE *)(*(_QWORD *)&v157.left + 14LL) == 4
      && *(_WORD *)(*(_QWORD *)&v157.left + 12LL) == WORD1(a1)
      && ((v60 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v158 + 8) + 96LL))(
                   *(_QWORD *)(v158 + 8),
                   **(unsigned int **)&v157.left),
           GreGetCurrentThread(),
           !*(_WORD *)(v60 + 12))
       || *(struct _KTHREAD **)(v60 + 16) == KeGetCurrentThread()) )
    {
      v63 = *(_DWORD *)(v59 + 8) & 0xFFFFFFFE;
      if ( v63 && (unsigned int)HmgIncProcessHandleCount(0, v61, v62) )
      {
        HmgDecProcessHandleCount(v57, v63);
        HANDLELOCK::Pid((HANDLELOCK *)&v157, 0);
        *(_WORD *)(v60 + 14) &= ~0x10u;
      }
    }
    else
    {
      BYTE1(v157.bottom) = 1;
    }
    HANDLELOCK::vUnlock((HANDLELOCK *)&v157);
  }
  HANDLELOCK::~HANDLELOCK((HANDLELOCK *)&v157);
  SEMOBJ<20>::vUnlock(&v129);
  RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)&v149, a1, 0, 0);
  if ( !v149 )
  {
    v85 = *((_QWORD *)v52 + 533);
    goto LABEL_95;
  }
  v65 = *(_QWORD *)v130;
  v66 = W32GetSessionState(v64);
  v67 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)(v66 + 88) + 8LL) + 16LL))(
          *(_QWORD *)(*(_QWORD *)(v66 + 88) + 8LL),
          (unsigned __int16)v65 | ((unsigned int)v65 >> 8) & 0xFF0000);
  if ( !v67
    || *(_BYTE *)(v67 + 14) != 1
    || *(_WORD *)(v67 + 12) != WORD1(v65)
    || (*(_DWORD *)(v67 + 8) & 0xFFFFFFFE) != 0x80000012 )
  {
    v68 = v130;
    if ( (*((_DWORD *)v130 + 9) & 0x100000) != 0 )
    {
      v69 = *((_QWORD *)v130 + 6);
      if ( v69 )
      {
        v70 = (_DWORD *)v149;
        if ( v149 )
        {
          v136 = 0;
          v137 = 0;
          v71 = (_QWORD *)PsGetCurrentThreadWin32Thread();
          if ( v71 && *v71 )
          {
            v72 = *v71 + 8LL;
            *(_QWORD *)&v137 = &v136;
            v73 = (unsigned __int64)UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
            *((_QWORD *)&v137 + 1) = UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
            if ( v72 )
            {
              v74 = *(_QWORD *)(v72 + 88);
              v75 = (_QWORD *)(v72 + 88);
              if ( *(_QWORD **)(v74 + 8) != v75 )
                goto LABEL_44;
              *(_QWORD *)&v136 = v74;
              *((_QWORD *)&v136 + 1) = v75;
              *(_QWORD *)(v74 + 8) = &v136;
              v73 = (unsigned __int64)&v136;
              *v75 = &v136;
LABEL_81:
              v76 = 0;
              v83 = (*((_DWORD *)v68 + 9) & 0x40000) == 0;
              v138 = 0;
              if ( v83 )
              {
                v77 = *((_QWORD *)v68 + 62);
                v78 = 0;
              }
              else
              {
                v120 = (HSURF)*((_QWORD *)v68 + 268);
                if ( v120 )
                {
                  SURFREF::vLock((SURFREF *)&v136, v120);
                  v76 = v138;
                  v77 = v138;
                  v78 = v138;
                }
                else
                {
                  v77 = *(_QWORD *)(v69 + 2544);
                  v78 = 0;
                }
              }
              if ( !v77 )
              {
                v83 = v78 == 0;
LABEL_90:
                if ( v83 )
                {
LABEL_92:
                  PopThreadGuardedObject(&v136);
                  goto LABEL_93;
                }
LABEL_91:
                v84 = W32GetSessionState(v73);
                HmgDecrementShareReferenceCount(*(_QWORD *)(v84 + 88), v138);
                goto LABEL_92;
              }
              if ( (*(_DWORD *)(v69 + 40) & 0x20000) != 0 && *(int *)(v77 + 160) < 0
                || (v79 = *((_DWORD *)v68 + 9), (v79 & 0x1000) != 0) && (v79 & 0x4000) == 0
                || (v80 = v70[13], v81 = v70[15], v80 == v81)
                || (v82 = v70[14], v73 = (unsigned int)v70[16], v82 == (_DWORD)v73)
                || v80 == 0x7FFFFFFF && (_DWORD)v73 == 0x80000000 && v82 == 0x7FFFFFFF && v81 == (_DWORD)v73 )
              {
                v83 = v76 == 0;
                goto LABEL_90;
              }
              v107 = v70[13];
              v108 = v82;
              if ( (*(_DWORD *)(v77 + 164) & 0x800) != 0 )
                v109 = (__int64 *)(v77 + 716);
              else
                v109 = (__int64 *)(v77 + 56);
              v110 = *v109;
              if ( v80 >= v81 )
              {
                if ( v80 > v81 )
                {
                  v107 = v81;
                  v81 = v80;
                }
                v111 = v82 <= (int)v73;
              }
              else
              {
                v111 = v82 <= (int)v73;
                if ( v82 < (int)v73 )
                {
                  if ( v80 >= 0 )
                  {
                    if ( (int)v110 >= v81 && v82 >= 0 )
                    {
                      if ( SHIDWORD(v110) >= (int)v73 )
                      {
                        if ( !v76 )
                          goto LABEL_92;
                        goto LABEL_91;
                      }
LABEL_154:
                      v73 = HIDWORD(v110);
LABEL_155:
                      if ( v81 < v107 )
                      {
                        v107 = v81;
                      }
                      else if ( (int)v73 < v108 )
                      {
                        v108 = v73;
                      }
                      v157.left = v107;
                      v157.top = v108;
                      v157.right = v81;
                      v157.bottom = v73;
                      if ( v76 )
                      {
                        v112 = W32GetSessionState(v73);
                        HmgDecrementShareReferenceCount(*(_QWORD *)(v112 + 88), v138);
                      }
                      PopThreadGuardedObject(&v136);
                      RGNOBJ::vSet((RGNOBJ *)&v149, &v157);
                      goto LABEL_93;
                    }
LABEL_149:
                    if ( v108 < 0 )
                      v108 = 0;
                    if ( (int)v110 < v81 )
                      v81 = v110;
                    if ( SHIDWORD(v110) >= (int)v73 )
                      goto LABEL_155;
                    goto LABEL_154;
                  }
LABEL_147:
                  if ( v107 < 0 )
                    v107 = 0;
                  goto LABEL_149;
                }
              }
              if ( !v111 )
              {
                v108 = v73;
                v73 = (unsigned int)v82;
              }
              goto LABEL_147;
            }
          }
          else
          {
            v73 = (unsigned __int64)UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
            *(_QWORD *)&v137 = &v136;
            *((_QWORD *)&v137 + 1) = UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
          }
          *((_QWORD *)&v136 + 1) = &v136;
          *(_QWORD *)&v136 = &v136;
          goto LABEL_81;
        }
      }
    }
  }
LABEL_93:
  v85 = v149;
  if ( !(unsigned int)RGNOBJAPI::bDeleteHandle((RGNOBJAPI *)&v149) )
    goto LABEL_98;
  v149 = 0;
LABEL_95:
  v87 = v130;
  v88 = v130;
  *((_DWORD *)v130 + 9) |= 0x10u;
  v89 = DC::PentryFromPobj(v88, v52);
  *((_BYTE *)v89 + 15) |= 4u;
  GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v87 + 1112));
  v129 = *((_QWORD *)v87 + 142);
  *(_QWORD *)&v157.left = v87;
  LOBYTE(v157.right) = 1;
  RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v129);
  *((_QWORD *)v87 + 142) = *((_QWORD *)v52 + 533);
  _reset___lambda_call_V_lambda_1___1__AcquireDcVisRgnExclusive_DC__QEAA_XZ__details_wil__QEAAXXZ(&v157);
  v90 = v130;
  GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v130 + 1112));
  *((_QWORD *)v130 + 142) = v85;
  *(_DWORD *)(v85 + 72) = _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(W32GetSessionState(v91) + 88)
                                                                          + 4248LL));
  v92 = GreGetCurrentThreadCrossSessionCheck();
  if ( v92 )
    *(_QWORD *)v92 &= ~0x4000000000uLL;
  GrePushLock::ReleaseLock((DC *)((char *)v90 + 1112));
LABEL_98:
  if ( !v152 )
    RGNOBJ::UpdateUserRgn((RGNOBJ *)&v149);
  if ( v149 )
    _InterlockedDecrement16((volatile signed __int16 *)(v149 + 12));
  v93 = v150;
  if ( *(__int64 **)(v150 + 8) != &v150 )
    goto LABEL_44;
  v94 = v151;
  if ( *v151 != &v150 )
    goto LABEL_44;
  *v151 = (_QWORD *)v150;
  *(_QWORD *)(v93 + 8) = v94;
LABEL_105:
  if ( v53 )
  {
    if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
      McTemplateK0pz_EtwWriteTransfer(
        (_DWORD)v94,
        (unsigned int)LockRelease,
        v86,
        (_DWORD)v53,
        (__int64)L"VisRgnPublish");
    GrepReleaseLockValidate<11>();
    GreReleaseSemaphoreSharedInternal(v53);
  }
  if ( v130 )
  {
    v95 = W32GetSessionState(v94);
    HmgDecrementShareReferenceCount(*(_QWORD *)(v95 + 88), v130);
    v130 = 0;
  }
LABEL_110:
  v96 = v134;
  if ( *(__int128 **)(v134 + 8) != &v134 )
    goto LABEL_44;
  v97 = *((_QWORD *)&v134 + 1);
  if ( **((__int128 ***)&v134 + 1) != &v134 )
    goto LABEL_44;
  **((_QWORD **)&v134 + 1) = v134;
  *(_QWORD *)(v96 + 8) = v97;
}

```

## disassembly

```asm
0x140023110  push    rbp
0x140023112  push    rbx
0x140023113  push    r12
0x140023115  push    r13
0x140023117  push    r14
0x140023119  push    r15
0x14002311b  lea     rbp, [rsp-0E8h]
0x140023123  sub     rsp, 1E8h
0x14002312a  movaps  [rsp+210h+var_40], xmm6
0x140023132  mov     rax, cs:__security_cookie
0x140023139  xor     rax, rsp
0x14002313c  mov     [rbp+110h+var_50], rax
0x140023143  mov     rax, [rdx+50h]
0x140023147  mov     r15, rcx
0x14002314a  xorps   xmm0, xmm0
0x14002314d  mov     dword ptr [rsp+210h+var_1C8], r8d
0x140023152  mov     r14, rdx
0x140023155  movups  xmmword ptr [rbp+110h+var_68.left], xmm0
0x14002315c  mov     rcx, [rax+28h]
0x140023160  movzx   eax, word ptr [rcx+2Ah]
0x140023164  and     eax, 0FFFF2FFFh
0x140023169  cmp     eax, 29Dh
0x14002316e  jz      loc_140023484
0x140023174  mov     eax, [rdx+30h]
0x140023177  lea     rbx, [rdx+30h]
0x14002317b  test    al, 1
0x14002317d  jnz     loc_1400234CA
0x140023183  movups  xmm6, xmmword ptr [rcx+68h]
0x140023187  mov     r13d, [rcx+70h]
0x14002318b  movdqa  xmm0, xmm6
0x14002318f  psrldq  xmm0, 0Ch
0x140023194  movd    r12d, xmm0
0x140023199  movups  xmmword ptr [rbp+110h+var_68.left], xmm6
0x1400231a0  mov     rcx, [r14+48h]; struct tagMONITOR *
0x1400231a4  test    rcx, rcx
0x1400231a7  jnz     loc_140023E4A
0x1400231ad  movdqa  xmm0, xmm6
0x1400231b1  movss   dword ptr [rsp+210h+var_1D8], xmm6
0x1400231b7  psrldq  xmm0, 4
0x1400231bc  movd    dword ptr [rsp+210h+var_1E0], xmm0
0x1400231c2  test    dword ptr [rbx], 4000000h
0x1400231c8  mov     [rsp+210h+arg_10], rsi
0x1400231d0  mov     [rsp+210h+var_30], rdi
0x1400231d8  jnz     loc_140023381
0x1400231de  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400231e5  nop     dword ptr [rax+rax+00h]
0x1400231ea  mov     rcx, [rax+30h]
0x1400231ee  mov     rax, [rcx+898h]
0x1400231f5  test    rax, rax
0x1400231f8  jz      loc_1400233F2
0x1400231fe  call    _guard_dispatch_icall
0x140023203  test    eax, eax
0x140023205  js      loc_1400233F2
0x14002320b  mov     rdi, [r14+50h]
0x14002320f  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140023216  nop     dword ptr [rax+rax+00h]
0x14002321b  mov     rdx, [rax+30h]
0x14002321f  mov     rax, [rdx+8A0h]
0x140023226  test    rax, rax
0x140023229  jz      loc_140023C7F
0x14002322f  mov     rcx, rdi
0x140023232  call    _guard_dispatch_icall
0x140023237  mov     rdi, rax
0x14002323a  test    rdi, rdi
0x14002323d  jz      loc_1400233F2
0x140023243  mov     rax, [rdi+28h]
0x140023247  test    dword ptr [rax+18h], 20000000h
0x14002324e  jz      loc_140023381
0x140023254  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14002325b  nop     dword ptr [rax+rax+00h]
0x140023260  mov     rcx, [rax+30h]
0x140023264  mov     rax, [rcx+8A8h]
0x14002326b  test    rax, rax
0x14002326e  jz      loc_140023381
0x140023274  call    _guard_dispatch_icall
0x140023279  test    eax, eax
0x14002327b  js      loc_140023381
0x140023281  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140023288  nop     dword ptr [rax+rax+00h]
0x14002328d  mov     rcx, [rax+30h]
0x140023291  mov     rax, [rcx+8B0h]
0x140023298  test    rax, rax
0x14002329b  jz      loc_140023381
0x1400232a1  mov     rcx, rdi
0x1400232a4  call    _guard_dispatch_icall
0x1400232a9  test    rax, rax
0x1400232ac  jz      loc_140023381
0x1400232b2  mov     rax, [rdi+28h]
0x1400232b6  mov     r9d, dword ptr [rsp+210h+var_1D8]
0x1400232bb  mov     esi, [rax+58h]
0x1400232be  mov     edi, [rax+5Ch]
0x1400232c1  mov     rax, [r14+48h]
0x1400232c5  test    rax, rax
0x1400232c8  jnz     loc_140023D94
0x1400232ce  neg     esi
0x1400232d0  neg     edi
0x1400232d2  add     r13d, esi
0x1400232d5  add     r9d, esi
0x1400232d8  mov     [rbp+110h+var_68.right], r13d
0x1400232df  add     r12d, edi
0x1400232e2  mov     r13d, dword ptr [rsp+210h+var_1E0]
0x1400232e7  add     r13d, edi
0x1400232ea  mov     dword ptr [rsp+210h+var_1D8], r9d
0x1400232ef  mov     [rbp+110h+var_68.left], r9d
0x1400232f6  mov     [rbp+110h+var_68.bottom], r12d
0x1400232fd  mov     [rbp+110h+var_68.top], r13d
0x140023304  test    r15, r15
0x140023307  jz      short loc_140023378
0x140023309  xor     r9d, r9d; int
0x14002330c  lea     rcx, [rbp+110h+var_110]; this
0x140023310  xor     r8d, r8d; int
0x140023313  mov     rdx, r15; HRGN
0x140023316  call    ??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z; RGNOBJAPI::RGNOBJAPI(HRGN__ *,int,int)
0x14002331b  mov     rcx, [rbp+110h+var_110]
0x14002331f  mov     [rsp+210h+var_1E0], 0
0x140023328  test    rcx, rcx
0x14002332b  jnz     loc_140023B87
0x140023331  cmp     [rbp+110h+var_E0], 0
0x140023335  jnz     short loc_140023344
0x140023337  lea     rcx, [rbp+110h+var_110]; this
0x14002333b  call    ?UpdateUserRgn@RGNOBJ@@QEAAXXZ; RGNOBJ::UpdateUserRgn(void)
0x140023340  mov     rcx, [rbp+110h+var_110]
0x140023344  test    rcx, rcx
0x140023347  jz      short loc_14002334E
0x140023349  lock dec word ptr [rcx+0Ch]
0x14002334e  mov     rax, [rbp+110h+var_108]
0x140023352  lea     rcx, [rbp+110h+var_108]
0x140023356  cmp     [rax+8], rcx
0x14002335a  jnz     loc_14002347D
0x140023360  mov     rcx, [rbp+110h+var_100]
0x140023364  lea     rdx, [rbp+110h+var_108]
0x140023368  cmp     [rcx], rdx
0x14002336b  jnz     loc_14002347D
0x140023371  mov     [rcx], rax
0x140023374  mov     [rax+8], rcx
0x140023378  movups  xmm6, xmmword ptr [rbp+110h+var_68.left]
0x14002337f  jmp     short loc_1400233F7
0x140023381  test    r15, r15
0x140023384  jz      short loc_1400233F2
0x140023386  xor     r9d, r9d; int
0x140023389  lea     rcx, [rbp+110h+var_A0]; this
0x14002338d  xor     r8d, r8d; int
0x140023390  mov     rdx, r15; HRGN
0x140023393  call    ??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z; RGNOBJAPI::RGNOBJAPI(HRGN__ *,int,int)
0x140023398  mov     rax, [rbp+110h+var_A0]
0x14002339c  test    rax, rax
0x14002339f  jnz     loc_140023C5B
0x1400233a5  cmp     [rbp+110h+var_70], 0
0x1400233ac  jnz     short loc_1400233BB
0x1400233ae  lea     rcx, [rbp+110h+var_A0]; this
0x1400233b2  call    ?UpdateUserRgn@RGNOBJ@@QEAAXXZ; RGNOBJ::UpdateUserRgn(void)
0x1400233b7  mov     rax, [rbp+110h+var_A0]
0x1400233bb  test    rax, rax
0x1400233be  jz      short loc_1400233C5
0x1400233c0  lock dec word ptr [rax+0Ch]
0x1400233c5  mov     rax, [rbp+110h+var_98]
0x1400233c9  lea     rcx, [rbp+110h+var_98]
0x1400233cd  cmp     [rax+8], rcx
0x1400233d1  jnz     loc_14002347D
0x1400233d7  mov     rcx, [rbp+110h+var_90]
0x1400233de  lea     rdx, [rbp+110h+var_98]
0x1400233e2  cmp     [rcx], rdx
0x1400233e5  jnz     loc_14002347D
0x1400233eb  mov     [rcx], rax
0x1400233ee  mov     [rax+8], rcx
0x1400233f2  mov     r13d, dword ptr [rsp+210h+var_1E0]
0x1400233f7  mov     rdi, [r14+10h]
0x1400233fb  xor     r12d, r12d
0x1400233fe  mov     [rbp+110h+var_150], r12
0x140023402  mov     [rbp+110h+var_148], r12d
0x140023406  call    cs:__imp_W32GetSessionState
0x14002340d  nop     dword ptr [rax+rax+00h]
0x140023412  xorps   xmm0, xmm0
0x140023415  mov     rcx, [rax+58h]
0x140023419  mov     [rbp+110h+var_140], rcx
0x14002341d  mov     [rbp+110h+var_138], r12
0x140023421  mov     [rbp+110h+var_150], r12
0x140023425  mov     [rbp+110h+var_148], r12d
0x140023429  movups  [rbp+110h+var_130], xmm0
0x14002342d  movups  [rbp+110h+var_120], xmm0
0x140023431  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140023438  nop     dword ptr [rax+rax+00h]
0x14002343d  test    rax, rax
0x140023440  jz      loc_140023F14
0x140023446  mov     rax, [rax]
0x140023449  test    rax, rax
0x14002344c  jz      loc_140023F14
0x140023452  lea     rcx, [rbp+110h+var_150]
0x140023456  mov     qword ptr [rbp+110h+var_120], rcx
0x14002345a  lea     rbx, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDCOBJA@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic(void *)
0x140023461  mov     qword ptr [rbp+110h+var_120+8], rbx
0x140023465  add     rax, 8
0x140023469  jz      loc_140023F27
0x14002346f  mov     rcx, [rax+58h]
0x140023473  add     rax, 58h ; 'X'
0x140023477  cmp     [rcx+8], rax
0x14002347b  jz      short loc_1400234D7
0x14002347d  mov     ecx, 3
0x140023482  int     29h; Win8: RtlFailFast(ecx)
0x140023484  call    cs:__imp_W32GetUserSessionState
0x14002348b  nop     dword ptr [rax+rax+00h]
0x140023490  lea     rbx, [r14+30h]
0x140023494  mov     rcx, [rax+0DDA8h]
0x14002349b  mov     eax, [rbx]
0x14002349d  mov     rdx, [rcx]
0x1400234a0  mov     r13d, [rdx+20h]
0x1400234a4  sub     r13d, [rdx+18h]
0x1400234a8  mov     r12d, [rdx+24h]
0x1400234ac  sub     r12d, [rdx+1Ch]
0x1400234b0  mov     [rbp+110h+var_68.bottom], r12d
0x1400234b7  mov     [rbp+110h+var_68.right], r13d
0x1400234be  movups  xmm6, xmmword ptr [rbp+110h+var_68.left]
0x1400234c5  jmp     loc_1400231A0
0x1400234ca  movups  xmm6, xmmword ptr [rcx+58h]
0x1400234ce  mov     r13d, [rcx+60h]
0x1400234d2  jmp     loc_14002318B
0x1400234d7  mov     qword ptr [rbp+110h+var_130], rcx
0x1400234db  lea     rdx, [rbp+110h+var_130]
0x1400234df  mov     qword ptr [rbp+110h+var_130+8], rax
0x1400234e3  mov     [rcx+8], rdx
0x1400234e7  lea     rcx, [rbp+110h+var_130]
0x1400234eb  mov     [rax], rcx
0x1400234ee  mov     rcx, [rbp+110h+var_140]
0x1400234f2  mov     esi, 1
0x1400234f7  mov     r9d, esi
0x1400234fa  movzx   r8d, sil
0x1400234fe  mov     rdx, rdi
0x140023501  call    ?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x140023506  mov     [rbp+110h+var_150], rax
0x14002350a  test    rax, rax
0x14002350d  jz      loc_1400235A2
0x140023513  mov     ecx, [rax+28h]
0x140023516  mov     edx, dword ptr [rsp+210h+var_1D8]
0x14002351a  and     ecx, esi
0x14002351c  mov     [rax+rcx*8+3F8h], edx
0x140023523  mov     rcx, [rbp+110h+var_150]
0x140023527  mov     eax, [rcx+28h]
0x14002352a  and     eax, esi
0x14002352c  mov     [rcx+rax*8+3FCh], r13d
0x140023534  mov     rdx, [rbp+110h+var_150]
0x140023538  mov     eax, [rdx+28h]
0x14002353b  and     eax, esi
0x14002353d  mov     ecx, eax
0x14002353f  mov     eax, [rdx+rax*8+3F8h]
0x140023546  add     eax, [rdx+7Ch]
0x140023549  mov     [rdx+4A8h], eax
0x14002354f  mov     eax, [rdx+rcx*8+3FCh]
0x140023556  add     eax, [rdx+80h]
0x14002355c  mov     [rdx+4ACh], eax
0x140023562  mov     rax, [rbp+110h+var_150]
0x140023566  movups  xmmword ptr [rax+408h], xmm6
0x14002356d  mov     rax, [rbp+110h+var_150]
0x140023571  mov     ecx, [rax+208h]
0x140023577  test    sil, cl
0x14002357a  jnz     loc_1400240F1
0x140023580  test    rax, rax
0x140023583  jz      short loc_1400235A2
0x140023585  call    cs:__imp_W32GetSessionState
0x14002358c  nop     dword ptr [rax+rax+00h]
0x140023591  mov     rdx, [rbp+110h+var_150]
0x140023595  mov     rcx, [rax+58h]
0x140023599  call    HmgDecrementShareReferenceCount
0x14002359e  mov     [rbp+110h+var_150], r12
0x1400235a2  mov     rax, qword ptr [rbp+110h+var_130]
0x1400235a6  lea     rcx, [rbp+110h+var_130]
0x1400235aa  cmp     [rax+8], rcx
0x1400235ae  jnz     loc_14002347D
0x1400235b4  mov     rcx, qword ptr [rbp+110h+var_130+8]
0x1400235b8  lea     rdx, [rbp+110h+var_130]
0x1400235bc  cmp     [rcx], rdx
0x1400235bf  jnz     loc_14002347D
0x1400235c5  mov     [rcx], rax
0x1400235c8  mov     [rax+8], rcx
0x1400235cc  cmp     dword ptr [rsp+210h+var_1C8], r12d
0x1400235d1  jz      loc_140023AFE
0x1400235d7  mov     rdi, [r14+10h]
0x1400235db  mov     [rsp+210h+var_1C0], r12
0x1400235e0  mov     [rsp+210h+var_1B8], r12d
0x1400235e5  call    cs:__imp_W32GetSessionState
0x1400235ec  nop     dword ptr [rax+rax+00h]
0x1400235f1  xorps   xmm0, xmm0
0x1400235f4  mov     rcx, [rax+58h]
0x1400235f8  mov     [rsp+210h+var_1B0], rcx
0x1400235fd  mov     [rsp+210h+var_1A8], r12
0x140023602  mov     [rsp+210h+var_1C0], r12
0x140023607  mov     [rsp+210h+var_1B8], r12d
0x14002360c  movups  [rsp+210h+var_1A0], xmm0
0x140023611  movups  [rbp+110h+var_190], xmm0
0x140023615  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14002361c  nop     dword ptr [rax+rax+00h]
0x140023621  test    rax, rax
0x140023624  jz      loc_140023F3C
0x14002362a  mov     rax, [rax]
0x14002362d  test    rax, rax
0x140023630  jz      loc_140023F3C
0x140023636  mov     qword ptr [rbp+110h+var_190+8], rbx
0x14002363a  lea     rcx, [rsp+210h+var_1C0]
0x14002363f  mov     qword ptr [rbp+110h+var_190], rcx
0x140023643  add     rax, 8
0x140023647  jz      loc_140023F49
  ... truncated ...
```
