# GrepSelectBitmap(XDCOBJ &,HBITMAP__ *,GSBOptions)

- ea: `0x140027d70`
- end: `0x14002921d`
- name: `?GrepSelectBitmap@@YA?AVGSBResult@@AEAVXDCOBJ@@PEAUHBITMAP__@@W4GSBOptions@@@Z`
- size: `5293`
- prototype: `__int64 __fastcall(__int64, __int64 *, _DWORD *, char)`
- caller_count: `3`
- callee_count: `44`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14001bf50`
- `0x140023910`
- `0x14002bed0`

## callees

- `0x140011e60`
- `0x14001e034`
- `0x140022cd4`
- `0x140022d38`
- `0x140026c40`
- `0x140026cc8`
- `0x140027d70`
- `0x140029d90`
- `0x140029e80`
- `0x140029f0c`
- `0x14002a0b0`
- `0x14002a138`
- `0x14002a1d0`
- `0x1400309d0`
- `0x140030e10`
- `0x140031520`
- `0x140031750`
- `0x140031784`
- `0x1400317c0`
- `0x1400317e0`
- `0x140031da0`
- `0x140031ea0`
- `0x140031fa0`
- `0x140032300`
- `0x1400323a0`
- `0x1400324c0`
- `0x140033390`
- `0x1400371c0`
- `0x14003b6a0`
- `0x14003db08`
- `0x14003dee0`
- `0x140079330`
- `0x140107ca8`
- `0x14010e68c`
- `0x140111520`
- `0x140119784`
- `0x14011c20c`
- `0x14012e228`
- `0x140166a0c`
- `0x14016a47c`
- `0x140192b70`
- `0x1401afe80`
- `0x1402388e0`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400285fa`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400285fa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140028014`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140028394`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400285c6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400288e9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140028daf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140028ed5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140028014`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140028394`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400285c6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400288e9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140028daf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140028ed5`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14002860f`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14002860f`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x1400289cf`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x1400289cf`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140029082`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140029082`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140029073`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140029073`
- `ntoskrnl!KeIsAttachedProcess` at `0x1400289b8`
- `ntoskrnl!KeIsAttachedProcess` at `0x1400289b8`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x140027ee6`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x1400287ba`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x140027ee6`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x1400287ba`
- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x140028af4`
- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x1400290ba`
- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x140028af4`
- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x1400290ba`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140027dbc`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140028721`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140027dbc`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140028721`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400283e0`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140028405`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400283e0`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140028405`
- `WIN32K!W32GetSessionState` at `0x140027e35`
- `WIN32K!W32GetSessionState` at `0x140027ea2`
- `WIN32K!W32GetSessionState` at `0x140028066`
- `WIN32K!W32GetSessionState` at `0x14002814d`
- `WIN32K!W32GetSessionState` at `0x140028196`
- `WIN32K!W32GetSessionState` at `0x140028248`
- `WIN32K!W32GetSessionState` at `0x1400282c5`
- `WIN32K!W32GetSessionState` at `0x1400282f1`
- `WIN32K!W32GetSessionState` at `0x14002848a`
- `WIN32K!W32GetSessionState` at `0x140028523`
- `WIN32K!W32GetSessionState` at `0x1400285d8`
- `WIN32K!W32GetSessionState` at `0x140028937`
- `WIN32K!W32GetSessionState` at `0x140028971`
- `WIN32K!W32GetSessionState` at `0x140028a0a`
- `WIN32K!W32GetSessionState` at `0x140028bf5`
- `WIN32K!W32GetSessionState` at `0x140028ca8`
- `WIN32K!W32GetSessionState` at `0x1400290da`
- `WIN32K!W32GetSessionState` at `0x140027e35`
- `WIN32K!W32GetSessionState` at `0x140027ea2`
- `WIN32K!W32GetSessionState` at `0x140028066`
- `WIN32K!W32GetSessionState` at `0x14002814d`
- `WIN32K!W32GetSessionState` at `0x140028196`
- `WIN32K!W32GetSessionState` at `0x140028248`
- `WIN32K!W32GetSessionState` at `0x1400282c5`
- `WIN32K!W32GetSessionState` at `0x1400282f1`
- `WIN32K!W32GetSessionState` at `0x14002848a`
- `WIN32K!W32GetSessionState` at `0x140028523`
- `WIN32K!W32GetSessionState` at `0x1400285d8`
- `WIN32K!W32GetSessionState` at `0x140028937`
- `WIN32K!W32GetSessionState` at `0x140028971`
- `WIN32K!W32GetSessionState` at `0x140028a0a`
- `WIN32K!W32GetSessionState` at `0x140028bf5`
- `WIN32K!W32GetSessionState` at `0x140028ca8`
- `WIN32K!W32GetSessionState` at `0x1400290da`

## pseudocode

```c
__int64 __fastcall GrepSelectBitmap(__int64 a1, __int64 *a2, _DWORD *a3, char a4)
{
  unsigned int v4; // esi
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int128 *v13; // rdx
  _QWORD *v14; // rax
  __int64 v15; // rcx
  struct _GRETHREAD *v16; // rax
  __int64 v17; // rdx
  unsigned __int64 i; // rcx
  __int64 v19; // r8
  unsigned __int64 v20; // r9
  struct _GRETHREAD *v21; // rbx
  char v22; // r13
  SURFACE *v23; // r14
  __int64 v24; // rbx
  unsigned int v25; // edi
  __int64 *CurrentThreadWin32ThreadAndEnterCriticalRegion; // rsi
  __int64 v27; // rbx
  int v28; // r15d
  HSEMAPHORE v29; // rax
  HSEMAPHORE v30; // rsi
  unsigned int v31; // r14d
  __int64 v32; // rdi
  __int64 v33; // rax
  __int64 v34; // rcx
  __int64 *v35; // rdi
  __int64 v36; // rbx
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // r8
  __int64 v41; // r9
  int v42; // edx
  __int64 *v43; // rcx
  __int64 v44; // r8
  __int64 v45; // rbx
  __int64 v46; // rcx
  __int64 v47; // r9
  __int64 *v48; // rdi
  int v49; // ebx
  SURFACE *v50; // rsi
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // rdi
  __int64 v54; // rdi
  __int64 v55; // r15
  int v56; // r14d
  __int64 *v57; // rcx
  __int64 v58; // r8
  __int64 v59; // r9
  unsigned int v60; // r14d
  __int64 v61; // rax
  __int64 v62; // rdx
  DC *v63; // r10
  __int64 v64; // r14
  __int64 v65; // rax
  __int64 v66; // rcx
  _DWORD *v67; // rdi
  __int64 v68; // rax
  __int64 v69; // rdx
  __int64 v70; // r8
  __int64 v71; // r9
  DC **v72; // r15
  __int64 v73; // rcx
  int v74; // eax
  __int64 v75; // rcx
  __int64 v76; // rdx
  __int64 v77; // rcx
  __int64 v78; // r8
  __int64 v79; // r9
  __int64 v80; // rax
  __int64 v81; // rbx
  __int64 v82; // rdx
  unsigned int *v83; // r15
  __int64 v84; // r8
  __int64 v85; // rdx
  __int64 *v86; // rdi
  __int64 v87; // rbx
  __int64 v88; // rax
  int (*v89)(void); // rax
  __int64 v90; // r9
  __int64 v91; // rcx
  void (__fastcall *v92)(DC **, SURFACE *, __int64); // rax
  int v93; // eax
  _BOOL8 v94; // r8
  int v95; // eax
  int v96; // ecx
  unsigned int v97; // eax
  DC *v98; // rdx
  __int64 v99; // rcx
  __int64 v100; // r8
  __int64 v101; // r9
  int v102; // edx
  __int64 v103; // rdx
  __int64 v104; // rcx
  __int64 v105; // rax
  __int64 v106; // rax
  SURFACE *v107; // rbx
  __int64 v108; // rdi
  __int64 v109; // rdx
  unsigned int *v110; // rsi
  __int64 v111; // r8
  __int64 v112; // rdx
  __int64 *v113; // rdi
  __int64 v114; // rbx
  __int64 v115; // rax
  __int64 v116; // rdx
  __int64 v117; // rcx
  __int64 v118; // r8
  __int64 v119; // r9
  __int64 v120; // rax
  DC *v121; // r15
  __int64 v122; // rdi
  _DWORD *v123; // r14
  __int64 v124; // rsi
  int v125; // eax
  int v126; // r9d
  int v127; // r10d
  int v128; // edx
  int v129; // r8d
  _DWORD *v130; // rcx
  struct _GRETHREAD *v131; // rax
  unsigned int v132; // edi
  __int64 *v133; // rax
  __int64 v134; // rcx
  __int64 v135; // rdx
  unsigned int v136; // esi
  int v137; // eax
  __int64 v138; // rdi
  unsigned int v139; // esi
  __int64 *v140; // r14
  __int64 v141; // rdi
  int v142; // r15d
  __int64 v143; // rax
  unsigned int *v144; // r14
  unsigned int v145; // esi
  __int64 *v146; // rsi
  __int64 v147; // rax
  __int64 *v148; // rcx
  __int64 v149; // rsi
  __int64 v150; // rdi
  __int64 v151; // rax
  __int64 *v152; // rdi
  int v153; // eax
  __int64 v154; // rcx
  __int64 v155; // r8
  __int64 v156; // r9
  __int64 v157; // rdx
  __int64 v158; // rax
  __int64 v159; // rax
  __int64 v160; // rdx
  __int64 v161; // rax
  int v162; // ecx
  int v163; // r8d
  HSEMAPHORE v164; // r14
  struct _KTHREAD *CurrentThread; // rsi
  __int64 v166; // rdi
  __int64 *ThreadWin32Thread; // rax
  __int64 v168; // rax
  __int64 v169; // rdi
  __int64 v170; // rdx
  __int64 v171; // rcx
  __int64 v172; // r8
  __int64 v173; // r9
  bool v174; // zf
  __int64 v175; // rax
  char v177; // al
  int v178; // eax
  __int64 v179; // rax
  __int64 v180; // rax
  __int64 v181; // rcx
  __int64 v182; // rax
  __int64 v183; // r10
  __int64 v184; // r11
  unsigned int v185; // edx
  unsigned int v186; // eax
  DC *v187; // r10
  __int64 v188; // rax
  __int64 v189; // rcx
  __int64 v190; // rcx
  __int64 v191; // r10
  __int64 v192; // r11
  unsigned int v193; // edx
  unsigned int v194; // eax
  int v195; // eax
  ThreadRestrictNewHandlesRegion *v196; // rcx
  ThreadRestrictNewHandlesRegion *v197; // rcx
  int CurrentWin32kSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  __int64 SessionState; // rax
  __int64 v202; // [rsp+38h] [rbp-C8h] BYREF
  SURFACE *v203; // [rsp+40h] [rbp-C0h]
  HSEMAPHORE v204; // [rsp+48h] [rbp-B8h]
  unsigned int v205[2]; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD *v206; // [rsp+58h] [rbp-A8h] BYREF
  HSEMAPHORE v207; // [rsp+60h] [rbp-A0h] BYREF
  int v208; // [rsp+68h] [rbp-98h]
  __int16 v209; // [rsp+6Ch] [rbp-94h]
  __int64 v210; // [rsp+70h] [rbp-90h]
  __int64 *v211; // [rsp+78h] [rbp-88h]
  __int128 v212; // [rsp+80h] [rbp-80h] BYREF
  __int128 v213; // [rsp+90h] [rbp-70h]
  __int64 v214; // [rsp+A0h] [rbp-60h]
  __int128 v215; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v216; // [rsp+B8h] [rbp-48h]
  SURFACE *v217; // [rsp+C8h] [rbp-38h]
  __int64 *v218; // [rsp+D0h] [rbp-30h]
  __int64 v219; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v220; // [rsp+E0h] [rbp-20h]
  __int64 v221; // [rsp+E8h] [rbp-18h]
  _BYTE v222[12]; // [rsp+F0h] [rbp-10h] BYREF
  __int16 v223; // [rsp+FCh] [rbp-4h]
  __int64 *v224; // [rsp+100h] [rbp+0h]

  v215 = 0;
  v4 = (unsigned int)a3;
  v206 = a3;
  v216 = 0;
  v218 = a2;
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(a1);
  if ( CurrentThreadWin32Thread )
    v10 = *CurrentThreadWin32Thread;
  else
    v10 = 0;
  v11 = v10 + 8;
  v12 = -v10;
  v13 = (__int128 *)(v11 & -(__int64)(v12 != 0));
  *(_QWORD *)&v216 = &v215;
  *((_QWORD *)&v216 + 1) = UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
  if ( v13 )
  {
    v14 = (_QWORD *)v13 + 11;
    v15 = *((_QWORD *)v13 + 11);
    if ( *(__int128 **)(v15 + 8) != (__int128 *)((char *)v13 + 88) )
      goto LABEL_5;
    *(_QWORD *)&v215 = *((_QWORD *)v13 + 11);
    v13 = &v215;
    *((_QWORD *)&v215 + 1) = v14;
    *(_QWORD *)(v15 + 8) = &v215;
    v12 = (__int64)&v215;
    *v14 = &v215;
  }
  else
  {
    *((_QWORD *)&v215 + 1) = &v215;
    *(_QWORD *)&v215 = &v215;
  }
  v211 = (__int64 *)a2[2];
  v217 = 0;
  v204 = (HSEMAPHORE)(**(_QWORD **)(W32GetSessionState(v12, v13, v8, v9) + 88) + 624LL);
  EngAcquireSemaphoreShared(v204);
  v16 = GreGetCurrentThreadCrossSessionCheck();
  v21 = v16;
  v22 = 1;
  if ( v16 )
  {
    v19 = *(_QWORD *)v16;
    if ( (*(_QWORD *)v16 & 0xFFFFFFDFFFFFFFFEuLL) != 0 && (*(_QWORD *)v16 & 2) == 0 )
    {
      LODWORD(v17) = 38;
      for ( i = 0; i < 0x40; ++i )
      {
        v20 = 0xFFFFFFDFFFFFFFFFuLL;
        v195 = i;
        if ( ((1LL << i) & 0xFFFFFFDFFFFFFFFFuLL & v19) == 0 )
          v195 = v17;
        v17 = (unsigned int)v195;
      }
      if ( v195 > 1 && v195 != 38 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(i, (unsigned int)v195);
    }
    LOBYTE(i) = *((_BYTE *)v21 + 9);
    *((_BYTE *)v21 + 9) = i + 1;
    if ( !(_BYTE)i )
      *(_QWORD *)v21 |= 2uLL;
  }
  v203 = 0;
  v209 = 0;
  v23 = 0;
  v220 = *(_QWORD *)(W32GetSessionState(i, v17, v19, v20) + 88);
  v24 = 0;
  v210 = v220;
  v25 = (unsigned __int16)v4 | (v4 >> 8) & 0xFF0000;
  v202 = 0;
  CurrentThreadWin32ThreadAndEnterCriticalRegion = (__int64 *)PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion(&v202);
  if ( !(unsigned int)IsThreadCrossSessionAttached() && CurrentThreadWin32ThreadAndEnterCriticalRegion )
    v24 = *CurrentThreadWin32ThreadAndEnterCriticalRegion;
  v27 = (v24 + 8) & -(__int64)(v24 != 0);
  if ( v27 )
    v221 = *(_QWORD *)(v27 + 64);
  else
    v221 = 0;
  v28 = 1;
  v208 = 1;
  v29 = (HSEMAPHORE)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v220 + 8) + 40LL))(
                      *(_QWORD *)(v220 + 8),
                      v25);
  v207 = v29;
  v30 = v29;
  if ( v29 )
  {
    _m_prefetchw(v29 + 2);
    v31 = (_DWORD)v29[2] & 0xFFFFFFFE;
    if ( v31 != (v202 & 0xFFFFFFFC) && v31 && (!v221 || v31 != (unsigned int)UMPDGetThreadClientPID(v27)) )
    {
      HANDLELOCK::vUnlock((HANDLELOCK *)&v207);
      v28 = v208;
      v30 = v207;
      goto LABEL_19;
    }
    if ( (*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v220 + 8) + 96LL))(
                       *(_QWORD *)(v220 + 8),
                       *(_DWORD *)v30)
                   + 14)
        & 0x20) == 0 )
    {
LABEL_19:
      v23 = v203;
      goto LABEL_20;
    }
    v23 = 0;
    if ( !v27
      || (v196 = *(ThreadRestrictNewHandlesRegion **)(v27 + 328)) == 0
      || !*((_BYTE *)v196 + 80)
      || !ThreadRestrictNewHandlesRegion::InRegion(v196, v25) )
    {
      LOBYTE(v209) = 1;
      HANDLELOCK::vUnlock((HANDLELOCK *)&v207);
      v28 = v208;
      v30 = v207;
    }
  }
  else
  {
    v28 = 0;
    KeLeaveCriticalRegion();
  }
LABEL_20:
  if ( v28 )
  {
    v32 = v210;
    if ( *((_BYTE *)v30 + 14) == 5 && *((_WORD *)v30 + 6) == WORD1(v206) )
    {
      v33 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v210 + 8) + 96LL))(
              *(_QWORD *)(v210 + 8),
              *(_DWORD *)v30);
      v34 = v220;
      v23 = (SURFACE *)v33;
      ++*(_DWORD *)(v33 + 8);
      TrackObjectReferenceIncrement(v34, 3, *(_QWORD *)(v33 + 712));
    }
    v35 = *(__int64 **)(v32 + 8);
    v36 = *v35;
    v37 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v35 + 96))(v35, *(_DWORD *)v30);
    (*(void (__fastcall **)(__int64 *, __int64))(v36 + 48))(v35, v37);
    KeLeaveCriticalRegion();
  }
  v217 = v23;
  if ( v23 )
  {
    LOBYTE(v208) = (a4 & 2) != 0;
    v207 = (HSEMAPHORE)(*v211 + 1144);
    if ( (a4 & 2) != 0 )
      EngAcquireSemaphoreShared(v207);
    else
      GreAcquireSemaphoreInternal(v207);
    GrepAcquireLockValidate<2>();
    v43 = *(__int64 **)(W32GetSessionState(v39, v38, v40, v41) + 88);
    v45 = *v43;
    if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
      McTemplateK0pqz_EtwWriteTransfer((_DWORD)v43, v42, v44, v45 + 1512, 0, (__int64)L"Hmgr");
    GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(v43, v45 + 1512, v44);
    v48 = v218;
    v49 = 1;
    v50 = v217;
    v205[0] = 1;
    v51 = *v218;
    *(_QWORD *)v222 = *(_QWORD *)(*v218 + 48);
    if ( *(_QWORD *)v51 )
    {
      v52 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v218[2] + 8) + 8LL))(*(_QWORD *)(v218[2] + 8));
    }
    else
    {
      v52 = v51 + 2152;
      *(_OWORD *)(v51 + 2152) = 0;
      *(_QWORD *)(v51 + 2168) = 0;
      *(_DWORD *)(v51 + 2160) = -2147483630;
      *(_QWORD *)(v51 + 2168) = 0;
    }
    v53 = *v48;
    if ( *(_DWORD *)(v53 + 32) != 1 )
    {
      *(_BYTE *)(a1 + 8) = 6;
      goto LABEL_245;
    }
    if ( *((_DWORD *)v50 + 50) && !(unsigned int)SURFACE::bStockSurface(v50) && *((_QWORD *)v50 + 24) != *(_QWORD *)v53 )
    {
      *(_BYTE *)(a1 + 8) = 7;
LABEL_245:
      *(_QWORD *)a1 = 0;
      SessionState = W32GetSessionState(v46, v51, v52, v47);
      GreReleaseSemaphoreExclusive<20,>(*(_QWORD *)(SessionState + 88));
      SEMOBJEXORSHARED<2>::~SEMOBJEXORSHARED<2>(&v207);
      goto LABEL_150;
    }
    v54 = *(_QWORD *)(v53 + 48);
    if ( (*((_WORD *)v50 + 50) || *((_QWORD *)v50 + 3)) && *((_QWORD *)v50 + 6) != v54 )
    {
LABEL_223:
      *(_BYTE *)(a1 + 8) = v22;
      goto LABEL_245;
    }
    v55 = *((_QWORD *)v50 + 20);
    v46 = 0;
    if ( !v55 )
    {
      if ( *((_DWORD *)v50 + 24) != *(_DWORD *)(v54 + 2092) )
      {
        v22 = 2;
        goto LABEL_223;
      }
      if ( (*(_DWORD *)(v54 + 2156) & 0x100) != 0 )
        v55 = 0;
      else
        v55 = *(_QWORD *)(v54 + 1792);
    }
    v56 = *(_DWORD *)(v52 + 8);
    v219 = *((_QWORD *)v50 + 6);
    v57 = *(__int64 **)(W32GetSessionState(0, v51, v52, v47) + 88);
    if ( v50 != (SURFACE *)v57[547] && v54 && *((_QWORD *)v50 + 5) )
    {
      v57 = (__int64 *)(*(_DWORD *)(v54 + 40) & 1);
      if ( (*(_DWORD *)(v54 + 40) & 1) != 0 && (*((_DWORD *)v50 + 36) & 0x40000) != 0 )
      {
        *(_DWORD *)v222 = 33279186;
        *(_QWORD *)&v222[4] = 1;
        RtlLogUnexpectedCodepath(v222, 0);
        v177 = 3;
        goto LABEL_161;
      }
      if ( v219 && (_DWORD)v57 != (*(_DWORD *)(v219 + 40) & 1) )
      {
        *(_DWORD *)v222 = 33279186;
        *(_QWORD *)&v222[4] = 2;
        RtlLogUnexpectedCodepath(v222, 0);
        v177 = 4;
LABEL_161:
        *(_QWORD *)a1 = 0;
        *(_BYTE *)(a1 + 8) = v177;
        MLOCKOBJ::~MLOCKOBJ((MLOCKOBJ *)v205);
        SEMOBJEXORSHARED<2>::~SEMOBJEXORSHARED<2>(&v207);
        GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal, v204);
        SURFREF::~SURFREF((SURFREF *)&v215);
        return a1;
      }
    }
    v60 = v56 & 0xFFFFFFFE;
    if ( v60 && (*((_DWORD *)v50 + 36) & 0x800) != 0 )
    {
      *(_BYTE *)(a1 + 8) = 9;
      goto LABEL_173;
    }
    if ( (a4 & 4) == 0 && !v60 )
    {
      *(_BYTE *)(a1 + 8) = 10;
      goto LABEL_173;
    }
    v61 = W32GetSessionState(v57, 0, v58, v59);
    v57 = v218;
    v62 = 0;
    v63 = (DC *)*v218;
    v64 = *(_QWORD *)(*v218 + 496);
    if ( v64 )
    {
      if ( v218[3] )
        v64 = v218[3];
    }
    else
    {
      v64 = *(_QWORD *)(*(_QWORD *)(v61 + 88) + 4376LL);
    }
    if ( (!_bittest((const signed __int32 *)(v64 + 144), 0x1Au)
       || !_bittest((const signed __int32 *)v50 + 36, 0x1Au)
       || (*(_DWORD *)(v64 + 148) & 0x200) != 0)
      && (a4 & 1) == 0 )
    {
      *(_BYTE *)(a1 + 8) = 11;
LABEL_173:
      *(_QWORD *)a1 = 0;
      v179 = W32GetSessionState(v57, 0, v58, v59);
      GreReleaseSemaphoreExclusive<20,>(*(_QWORD *)(v179 + 88));
      SEMOBJEXORSHARED<2>::~SEMOBJEXORSHARED<2>(&v207);
      GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal, v204);
      v174 = v217 == 0;
      goto LABEL_145;
    }
    v65 = *((_QWORD *)v63 + 122);
    v203 = 0;
    LODWORD(v220) = *(_DWORD *)(v65 + 108);
    v66 = v220 & 7;
    LODWORD(v221) = v220 & 7;
    if ( (v220 & 7) != 0 )
    {
      *(_DWORD *)(v65 + 108) = 0;
      v181 = *((_QWORD *)v63 + 122);
      *(_QWORD *)v205 = *(_QWORD *)(v181 + 316);
      v182 = *(_QWORD *)(v181 + 324);
      v205[0] = -v205[0];
      HIDWORD(v202) = HIDWORD(v182);
      LODWORD(v202) = -(int)v182;
      *(_QWORD *)(v181 + 316) = *(_QWORD *)v205;
      *(_QWORD *)(*((_QWORD *)v63 + 122) + 324LL) = v202;
      DC::MirrorWindowOrg(v63);
      v184 = *(_QWORD *)(v183 + 976);
      if ( (*(_BYTE *)(v184 + 272) & 6) != 6 )
      {
        *(_DWORD *)(v184 + 272) ^= 2u;
        v184 = *(_QWORD *)(v183 + 976);
      }
      v185 = *(_DWORD *)(v183 + 248);
      v66 = v185;
      v186 = v185 | 4;
      v62 = v185 & 0xFFFFFFFB;
      if ( (v66 & 4) == 0 )
        v62 = v186;
      *(_DWORD *)(v183 + 248) = v62;
      *(_DWORD *)(v184 + 340) |= 0x4090u;
    }
    if ( *((_QWORD *)v50 + 20) != v55 )
    {
      *((_DWORD *)v50 + 36) |= 0x8000000u;
      *((_QWORD *)v50 + 20) = v55;
      if ( v55 )
      {
        v180 = W32GetSessionState(v66, v62, v58, v59);
        HmgIncrementShareReferenceCount(*(_QWORD *)(v180 + 88), v55);
      }
    }
    if ( (*(_DWORD *)(v64 + 144) & 0x1000000) != 0 )
      v203 = *(SURFACE **)v64;
    v67 = *(_DWORD **)(v64 + 32);
    v202 = (__int64)v67;
    if ( v206 == v67 )
      goto LABEL_133;
    v68 = W32GetSessionState(v66, v62, v58, v59);
    v72 = (DC **)v218;
    v73 = *v218;
    if ( v50 == *(SURFACE **)(*(_QWORD *)(v68 + 88) + 4376LL) )
    {
      v74 = *(_DWORD *)(v73 + 520);
      *(_QWORD *)(v73 + 496) = 0;
      if ( (v74 & 1) != 0 )
      {
        *(_DWORD *)(v73 + 36) |= 0x10u;
        *(_QWORD *)(v73 + 524) = 0;
        *(_DWORD *)(v73 + 520) = v74 & 0xFFFFFFF8 | 4;
        *(_QWORD *)(v73 + 532) = 0;
        DC::vUpdateCachedDPIScaleValue((DC *)v73);
      }
    }
    else
    {
      *(_QWORD *)(v73 + 496) = v50;
      if ( (*((_DWORD *)v50 + 37) & 0x800) != 0 )
      {
        DC::vSetDpiScaling(v73, *(_QWORD *)((char *)v50 + 692));
      }
      else
      {
        v178 = *(_DWORD *)(v73 + 520);
        if ( (v178 & 1) != 0 )
        {
          *(_DWORD *)(v73 + 36) |= 0x10u;
          *(_QWORD *)(v73 + 524) = 0;
          *(_QWORD *)(v73 + 532) = 0;
          *(_DWORD *)(v73 + 520) = v178 & 0xFFFFFFF8 | 4;
          DC::vUpdateCachedDPIScaleValue((DC *)v73);
        }
      }
      if ( (*(_DWORD *)v50 & 0x800000) != 0 && _bittest16((const signed __int16 *)v50 + 51, 9u)
        || !*((_WORD *)v50 + 50) && *((_DWORD *)v50 + 62) )
      {
        *((_DWORD *)*v72 + 9) |= 0x10000u;
      }
      else
      {
        *((_DWORD *)*v72 + 9) &= ~0x10000u;
      }
    }
    *((_QWORD *)*v72 + 64) = *((_QWORD *)v50 + 7);
    v75 = *((_QWORD *)*v72 + 122);
    *(_DWORD *)(v75 + 152) |= 0xFu;
    v77 = *(_QWORD *)(W32GetSessionState(v75, v69, v70, v71) + 88);
    if ( v64 == *(_QWORD *)(v77 + 4376) )
    {
LABEL_71:
      v89 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v77) + 24) + 608LL);
      if ( v89 )
      {
        if ( v89() >= 0 )
        {
          v92 = *(void (__fastcall **)(DC **, SURFACE *, __int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v91) + 24)
                                                                 + 616LL);
          if ( v92 )
            v92(v72, v50, 1);
        }
      }
      v93 = *((_DWORD *)v50 + 36);
      v94 = (v93 & 0x4000) != 0 || (v93 & 0x800010) != 0 && (*(_DWORD *)(*(_QWORD *)v222 + 40LL) & 1) != 0;
      v95 = *((_DWORD *)*v72 + 9);
      v96 = v95 | 0x200;
      v97 = v95 & 0xFFFFFDFF;
      if ( !v94 )
        v96 = v97;
      *((_DWORD *)*v72 + 9) = v96;
      v98 = *v72;
      v99 = *((unsigned int *)*v72 + 9);
      if ( (v99 & 0x200) != 0 && (*((_DWORD *)v50 + 36) & 0x200) != 0 )
        LODWORD(v99) = v99 | 0x8000;
      else
        LODWORD(v99) = v99 & 0xFFFF7FFF;
      *((_DWORD *)v98 + 9) = v99;
      if ( v50 != *(SURFACE **)(*(_QWORD *)(W32GetSessionState(v99, v98, v94, v90) + 88) + 4376LL) )
      {
        SURFACE::vInc_cRef(v50);
        if ( (*(_DWORD *)v50 & 0x800000) == 0 || (*((_WORD *)v50 + 51) & 0x200) == 0 )
        {
          *((_QWORD *)v50 + 24) = *(_QWORD *)*v72;
          *((_QWORD *)v50 + 6) = *((_QWORD *)*v72 + 6);
        }
      }
      if ( *((_WORD *)v50 + 50) || (v102 = 1, !*((_QWORD *)v50 + 28)) )
        v102 = 0;
      **((_DWORD **)*v72 + 122) = v102 | **((_DWORD **)*v72 + 122) & 0xFFFFFFFE;
      if ( *((_WORD *)v50 + 50) || (v103 = 1, !*((_QWORD *)v50 + 28)) )
        v103 = 0;
      v104 = *((_QWORD *)*v72 + 122);
      if ( (_DWORD)v103 )
        v105 = *((_QWORD *)v50 + 29);
      else
        v105 = 0;
      *(_QWORD *)(v104 + 24) = v105;
      v106 = W32GetSessionState(v104, v103, v100, v101);
      v107 = v217;
      *(_QWORD *)&v212 = 0;
      v108 = *(_QWORD *)(v106 + 88);
      v109 = (unsigned __int16)*(_DWORD *)v217 | (*(_DWORD *)v217 >> 8) & 0xFF0000u;
      DWORD2(v212) = 0;
      WORD6(v212) = 0;
      *(_QWORD *)&v213 = v108;
      HANDLELOCK::vLockHandle(&v212, v109, 1);
      if ( !DWORD2(v212) )
      {
        HmgPentryFromPobj(v108, v107);
        goto LABEL_100;
      }
      v110 = (unsigned int *)v212;
      switch ( *(_BYTE *)(v212 + 14) )
      {
        case 4:
          v111 = *((_QWORD *)v107 + 14);
          v112 = 2;
          break;
        case 5:
          v111 = *((_QWORD *)v107 + 89);
          v112 = 3;
          break;
        case 0x10:
          v111 = *((_QWORD *)v107 + 17);
          v112 = 0;
          break;
        default:
          goto LABEL_99;
      }
      TrackObjectReferenceDecrement(v108, v112, v111);
LABEL_99:
      --*((_DWORD *)v107 + 2);
      v113 = *(__int64 **)(v213 + 8);
      v114 = *v113;
      v115 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v113 + 96))(v113, *v110);
      (*(void (__fastcall **)(__int64 *, __int64))(v114 + 48))(v113, v115);
      KeLeaveCriticalRegion();
LABEL_100:
      v217 = 0;
      v120 = W32GetSessionState(v117, v116, v118, v119);
      GreReleaseSemaphoreExclusive<20,>(*(_QWORD *)(v120 + 88));
      v49 = 0;
      DC::bSetDefaultRegion(*v72);
      v121 = *v72;
      KeEnterCriticalRegion();
      ExAcquirePushLockSharedEx((char *)v121 + 1112, 0);
      GrepAcquireLockValidate<37>();
      GrepAcquireLockValidate<38>();
      v122 = *v218;
      v123 = *(_DWORD **)(*v218 + 1136);
      if ( *(_QWORD *)*v218 )
      {
        v124 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v211[1] + 8LL))(v211[1], *v218);
      }
      else
      {
        v124 = v122 + 2152;
        *(_OWORD *)(v122 + 2152) = 0;
        *(_QWORD *)(v122 + 2168) = 0;
        *(_DWORD *)(v122 + 2160) = -2147483630;
        *(_QWORD *)(v122 + 2168) = 0;
      }
      if ( (*(_BYTE *)(v124 + 15) & 4) != 0 )
      {
        if ( !v123
          || (v206 = v123,
              *(_DWORD *)(*(_QWORD *)(v122 + 976) + 116LL) = RGNOBJ::iComplexity((RGNOBJ *)&v206),
              (unsigned int)RGNOBJ::iComplexity((RGNOBJ *)&v206) == 1) )
        {
          *(_OWORD *)(*(_QWORD *)(v122 + 976) + 120LL) = xmmword_140251EB8;
        }
        else
        {
          v125 = *(_DWORD *)(v122 + 1036);
          v126 = *(_DWORD *)(v122 + 1032);
          v127 = v123[14] - v125;
          v128 = v123[16] - v125;
          v129 = v123[15] - v126;
          v130 = *(_DWORD **)(v122 + 976);
          v130[30] = v123[13] - v126;
          v130[31] = v127;
          v130[32] = v129;
          v130[33] = v128;
        }
        *(_BYTE *)(v124 + 15) &= ~4u;
      }
      v131 = GreGetCurrentThreadCrossSessionCheck();
      if ( v131 )
        *(_QWORD *)v131 &= ~0x4000000000uLL;
      GrePushLock::ReleaseLock((DC *)((char *)v121 + 1112));
      v132 = (unsigned int)v203;
      if ( v203 )
      {
        v212 = 0;
        v213 = 0;
        v133 = (__int64 *)PsGetCurrentThreadWin32Thread(v66);
        if ( v133 )
          v134 = *v133;
        else
          v134 = 0;
        *(_QWORD *)&v213 = &v212;
        *((_QWORD *)&v213 + 1) = UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
        if ( ((v134 + 8) & -(__int64)(v134 != 0)) != 0 )
        {
          v135 = *(_QWORD *)(((v134 + 8) & -(__int64)(v134 != 0)) + 0x58);
          if ( *(_QWORD *)(v135 + 8) != ((v134 + 8) & -(__int64)(v134 != 0)) + 88 )
LABEL_5:
            __fastfail(3u);
          *(_QWORD *)&v212 = *(_QWORD *)(((v134 + 8) & -(__int64)(v134 != 0)) + 0x58);
          *((_QWORD *)&v212 + 1) = ((v134 + 8) & -(__int64)(v134 != 0)) + 88;
          *(_QWORD *)(v135 + 8) = &v212;
          *(_QWORD *)(((v134 + 8) & -(__int64)(v134 != 0)) + 0x58) = &v212;
        }
        else
        {
          *((_QWORD *)&v212 + 1) = &v212;
          *(_QWORD *)&v212 = &v212;
        }
        v136 = v132;
        v224 = v211;
        v137 = (unsigned __int16)v132;
        v138 = 0;
        v219 = 0;
        v139 = v137 | (v136 >> 8) & 0xFF0000;
        v223 = 0;
        v205[0] = v139;
        v206 = 0;
        v140 = (__int64 *)PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion(&v206);
        if ( !(unsigned int)IsThreadCrossSessionAttached() && v140 )
          v138 = *v140;
        v141 = (v138 + 8) & -(__int64)(v138 != 0);
        if ( v141 )
          v202 = *(_QWORD *)(v141 + 64);
        else
          v202 = 0;
        v142 = 1;
        *(_DWORD *)&v222[8] = 1;
        v143 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v211[1] + 40LL))(v211[1], v139);
        *(_QWORD *)v222 = v143;
        v144 = (unsigned int *)v143;
        if ( v143 )
        {
          _m_prefetchw((const void *)(v143 + 8));
          v145 = *(_DWORD *)(v143 + 8) & 0xFFFFFFFE;
          if ( v145 == ((unsigned int)v206 & 0xFFFFFFFC)
            || !v145
            || v202 && v145 == (unsigned int)UMPDGetThreadClientPID(v141) )
          {
            if ( (*(_BYTE *)((*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v211[1] + 96LL))(v211[1], *v144)
                           + 14)
                & 0x20) == 0 )
              goto LABEL_123;
            if ( v141 )
            {
              v197 = *(ThreadRestrictNewHandlesRegion **)(v141 + 328);
              if ( v197 )
              {
                if ( *((_BYTE *)v197 + 80) && ThreadRestrictNewHandlesRegion::InRegion(v197, v205[0]) )
                  goto LABEL_123;
              }
            }
            LOBYTE(v223) = 1;
          }
          HANDLELOCK::vUnlock((HANDLELOCK *)v222);
          v144 = *(unsigned int **)v222;
          v142 = *(_DWORD *)&v222[8];
        }
        else
        {
          v142 = 0;
          KeLeaveCriticalRegion();
        }
LABEL_123:
        if ( v142 )
        {
          v146 = v224;
          if ( *((_BYTE *)v144 + 14) == 5 && *((_WORD *)v144 + 6) == WORD1(v203) )
          {
            v147 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v224[1] + 96LL))(v224[1], *v144);
            v148 = v211;
            v219 = v147;
            ++*(_DWORD *)(v147 + 8);
            TrackObjectReferenceIncrement(v148, 3, *(_QWORD *)(v147 + 712));
          }
          v149 = v146[1];
          v150 = *(_QWORD *)v149;
          v151 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v149 + 96LL))(v149, *v144);
          (*(void (__fastcall **)(__int64, __int64))(v150 + 48))(v149, v151);
          KeLeaveCriticalRegion();
        }
        v152 = v211;
        v214 = v219;
        v153 = SURFACE::bDeleteSurface(v219, v211, 0, 0);
        v157 = v214;
        v174 = v153 == 0;
        v158 = v152[386];
        if ( !v174 )
          v157 = 0;
        v214 = v157;
        v67 = *(_DWORD **)(v158 + 168);
        if ( v157 )
        {
          v159 = W32GetSessionState(v154, v157, v155, v156);
          HmgDecrementShareReferenceCount(*(_QWORD *)(v159 + 88), v214);
        }
        PopThreadGuardedObject(&v212);
        goto LABEL_133;
      }
      v67 = (_DWORD *)v202;
LABEL_133:
      v160 = (unsigned int)v221;
      if ( (_DWORD)v221 )
      {
        v58 = (unsigned int)v220;
        v187 = (DC *)*v218;
        v188 = *(_QWORD *)(*v218 + 976);
        v66 = *(_DWORD *)(v188 + 108) & 7;
        *(_DWORD *)(v188 + 108) = v220;
        if ( (_DWORD)v66 != (_DWORD)v160 )
        {
          v189 = *((_QWORD *)v187 + 122);
          v202 = *(_QWORD *)(v189 + 316);
          v203 = *(SURFACE **)(v189 + 324);
          if ( (v58 & 1) != 0 )
            *(_DWORD *)(v189 + 104) = 8;
          v190 = *((_QWORD *)v187 + 122);
          LODWORD(v202) = -(int)v202;
          LODWORD(v203) = -(int)v203;
          *(_QWORD *)(v190 + 316) = v202;
          *(_QWORD *)(*((_QWORD *)v187 + 122) + 324LL) = v203;
          DC::MirrorWindowOrg(v187);
          v192 = *(_QWORD *)(v191 + 976);
          if ( (*(_BYTE *)(v192 + 272) & 6) != 6 )
          {
            *(_DWORD *)(v192 + 272) ^= 2u;
            v192 = *(_QWORD *)(v191 + 976);
          }
          v193 = *(_DWORD *)(v191 + 248);
          v66 = v193;
          v194 = v193 | 4;
          v160 = v193 & 0xFFFFFFFB;
          if ( (v66 & 4) == 0 )
            v160 = v194;
          *(_DWORD *)(v191 + 248) = v160;
          *(_DWORD *)(v192 + 340) |= 0x4090u;
        }
      }
      *(_QWORD *)a1 = v67;
      *(_BYTE *)(a1 + 8) = 0;
      if ( v49 )
      {
        v161 = W32GetSessionState(v66, v160, v58, v59);
        GreReleaseSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(
          *(_QWORD *)(v161 + 88),
          **(_QWORD **)(v161 + 88) + 1512LL);
      }
      SEMOBJEXORSHARED<2>::~SEMOBJEXORSHARED<2>(&v207);
      v164 = v204;
      if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
        McTemplateK0pz_EtwWriteTransfer(
          v162,
          (unsigned int)LockRelease,
          v163,
          (_DWORD)v204,
          (__int64)L"DynamicModeChange");
      CurrentThread = KeGetCurrentThread();
      v166 = 0;
      if ( !(unsigned __int8)KeIsAttachedProcess()
        || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(),
            CurrentThreadProcess = PsGetCurrentThreadProcess(),
            CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
      {
        ThreadWin32Thread = (__int64 *)PsGetThreadWin32Thread(CurrentThread);
        if ( ThreadWin32Thread )
          v166 = *ThreadWin32Thread;
      }
      v168 = v166 + 8;
      v169 = -v166;
      if ( (v168 & -(__int64)(v169 != 0)) != 0 )
      {
        v174 = (*(_BYTE *)((v168 & -(__int64)(v169 != 0)) + 9))-- == 1;
        if ( v174 )
          *(_QWORD *)(v168 & -(__int64)(v169 != 0)) &= ~2uLL;
      }
      GreReleaseSemaphoreSharedInternal(v164);
      goto LABEL_144;
    }
    if ( (*(_DWORD *)(v64 + 144) & 0x10) != 0 && (int)IsvMirrorIncludeNotifySupported() >= 0 )
      vMirrorIncludeNotifyWrap(v72, v64, 0);
    v80 = W32GetSessionState(v77, v76, v78, v79);
    *(_QWORD *)&v212 = 0;
    DWORD2(v212) = 0;
    WORD6(v212) = 0;
    v81 = *(_QWORD *)(v80 + 88);
    v82 = (unsigned __int16)*(_DWORD *)v64 | (*(_DWORD *)v64 >> 8) & 0xFF0000u;
    *(_QWORD *)&v213 = v81;
    HANDLELOCK::vLockHandle(&v212, v82, 1);
    if ( !DWORD2(v212) )
    {
      HmgPentryFromPobj(v81, v64);
LABEL_65:
      v174 = (*(_DWORD *)(v64 + 200))-- == 1;
      if ( v174 )
      {
        *(_QWORD *)(v64 + 192) = 0;
        if ( v203 )
          v203 = *(SURFACE **)v64;
        if ( (*(_DWORD *)(v64 + 144) & 0x8000000) != 0 )
        {
          v219 = *(_QWORD *)(v64 + 160);
          *(_QWORD *)(v64 + 160) = 0;
          XEPALOBJ::vUnrefPalette((XEPALOBJ *)&v219);
        }
        *(_DWORD *)(v64 + 144) &= ~0x8000000u;
      }
      goto LABEL_71;
    }
    v83 = (unsigned int *)v212;
    switch ( *(_BYTE *)(v212 + 14) )
    {
      case 4:
        v84 = *(_QWORD *)(v64 + 112);
        v85 = 2;
        break;
      case 5:
        v84 = *(_QWORD *)(v64 + 712);
        v85 = 3;
        break;
      case 0x10:
        v84 = *(_QWORD *)(v64 + 136);
        v85 = 0;
        break;
      default:
        goto LABEL_64;
    }
    TrackObjectReferenceDecrement(v81, v85, v84);
LABEL_64:
    --*(_DWORD *)(v64 + 8);
    v86 = *(__int64 **)(v213 + 8);
    v87 = *v86;
    v88 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v86 + 96))(v86, *v83);
    (*(void (__fastcall **)(__int64 *, __int64))(v87 + 48))(v86, v88);
    KeLeaveCriticalRegion();
    v72 = (DC **)v218;
    goto LABEL_65;
  }
  *(_QWORD *)a1 = 0;
  *(_BYTE *)(a1 + 8) = 5;
LABEL_150:
  GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal, v204);
LABEL_144:
  v174 = v217 == 0;
LABEL_145:
  if ( !v174 )
  {
    v175 = W32GetSessionState(v171, v170, v172, v173);
    HmgDecrementShareReferenceCount(*(_QWORD *)(v175 + 88), v217);
  }
  PopThreadGuardedObject(&v215);
  return a1;
}

```

## disassembly

```asm
0x140027d70  mov     [rsp-8+arg_18], rbx
0x140027d75  push    rbp
0x140027d76  push    rsi
0x140027d77  push    rdi
0x140027d78  push    r12
0x140027d7a  push    r13
0x140027d7c  push    r14
0x140027d7e  push    r15
0x140027d80  lea     rbp, [rsp-10h]
0x140027d85  sub     rsp, 110h
0x140027d8c  mov     rax, cs:__security_cookie
0x140027d93  xor     rax, rsp
0x140027d96  mov     [rbp+40h+var_38], rax
0x140027d9a  xorps   xmm0, xmm0
0x140027d9d  mov     [rsp+140h+var_110], r9b
0x140027da2  movups  [rbp+40h+var_98], xmm0
0x140027da6  mov     rsi, r8
0x140027da9  mov     [rsp+140h+var_E8], r8
0x140027dae  movups  [rbp+40h+var_88], xmm0
0x140027db2  mov     rbx, rdx
0x140027db5  mov     [rbp+40h+var_70], rdx
0x140027db9  mov     r12, rcx
0x140027dbc  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140027dc3  nop     dword ptr [rax+rax+00h]
0x140027dc8  xor     r15d, r15d
0x140027dcb  test    rax, rax
0x140027dce  jz      loc_14002905C
0x140027dd4  mov     rcx, [rax]
0x140027dd7  lea     rax, [rcx+8]
0x140027ddb  neg     rcx
0x140027dde  sbb     rdx, rdx
0x140027de1  and     rdx, rax
0x140027de4  lea     rax, [rbp+40h+var_98]
0x140027de8  mov     qword ptr [rbp+40h+var_88], rax
0x140027dec  lea     rax, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORSPACEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x140027df3  mov     qword ptr [rbp+40h+var_88+8], rax
0x140027df7  jz      loc_140029111
0x140027dfd  lea     rax, [rdx+58h]
0x140027e01  mov     rcx, [rax]
0x140027e04  cmp     [rcx+8], rax
0x140027e08  jz      short loc_140027E11
0x140027e0a  mov     ecx, 3
0x140027e0f  int     29h; Win8: RtlFailFast(ecx)
0x140027e11  mov     qword ptr [rbp+40h+var_98], rcx
0x140027e15  lea     rdx, [rbp+40h+var_98]
0x140027e19  mov     qword ptr [rbp+40h+var_98+8], rax
0x140027e1d  mov     [rcx+8], rdx
0x140027e21  lea     rcx, [rbp+40h+var_98]
0x140027e25  mov     [rax], rcx
0x140027e28  mov     rax, [rbx+10h]
0x140027e2c  mov     [rsp+140h+var_C8], rax
0x140027e31  mov     [rbp+40h+var_78], r15
0x140027e35  call    cs:__imp_W32GetSessionState
0x140027e3c  nop     dword ptr [rax+rax+00h]
0x140027e41  mov     rcx, [rax+58h]
0x140027e45  mov     rax, [rcx]
0x140027e48  add     rax, 270h
0x140027e4e  mov     rcx, rax; hsem
0x140027e51  mov     [rsp+140h+var_F8], rax
0x140027e56  call    EngAcquireSemaphoreShared
0x140027e5b  call    ?GreGetCurrentThreadCrossSessionCheck@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThreadCrossSessionCheck(void)
0x140027e60  mov     rbx, rax
0x140027e63  mov     r13d, 1
0x140027e69  test    rax, rax
0x140027e6c  jz      short loc_140027EA2
0x140027e6e  mov     r8, [rax]
0x140027e71  mov     rax, 0FFFFFFDFFFFFFFFEh
0x140027e7b  test    rax, r8
0x140027e7e  setnz   cl
0x140027e81  test    r8b, 2
0x140027e85  setz    al
0x140027e88  test    al, cl
0x140027e8a  jnz     loc_140028F15
0x140027e90  mov     cl, [rbx+9]
0x140027e93  lea     eax, [rcx+r13]
0x140027e97  mov     [rbx+9], al
0x140027e9a  test    cl, cl
0x140027e9c  jnz     short loc_140027EA2
0x140027e9e  or      qword ptr [rbx], 2
0x140027ea2  call    cs:__imp_W32GetSessionState
0x140027ea9  nop     dword ptr [rax+rax+00h]
0x140027eae  mov     edi, esi
0x140027eb0  mov     [rsp+140h+var_100], r15
0x140027eb5  shr     edi, 8
0x140027eb8  lea     rcx, [rsp+140h+var_108]
0x140027ebd  and     edi, 0FF0000h
0x140027ec3  mov     [rsp+140h+var_D4], r15w
0x140027ec9  mov     rax, [rax+58h]
0x140027ecd  mov     r14, r15
0x140027ed0  mov     [rbp+40h+var_60], rax
0x140027ed4  mov     rbx, r15
0x140027ed7  mov     [rsp+140h+var_D0], rax
0x140027edc  movzx   eax, si
0x140027edf  or      edi, eax
0x140027ee1  mov     [rsp+140h+var_108], r15
0x140027ee6  call    cs:__imp_PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion
0x140027eed  nop     dword ptr [rax+rax+00h]
0x140027ef2  mov     rsi, rax
0x140027ef5  call    IsThreadCrossSessionAttached
0x140027efa  test    eax, eax
0x140027efc  jnz     short loc_140027F06
0x140027efe  test    rsi, rsi
0x140027f01  jz      short loc_140027F06
0x140027f03  mov     rbx, [rsi]
0x140027f06  lea     rax, [rbx+8]
0x140027f0a  neg     rbx
0x140027f0d  sbb     rbx, rbx
0x140027f10  and     rbx, rax
0x140027f13  jz      loc_1400290FE
0x140027f19  mov     rax, [rbx+40h]
0x140027f1d  mov     [rbp+40h+var_58], rax
0x140027f21  mov     rcx, [rbp+40h+var_60]
0x140027f25  mov     edx, edi
0x140027f27  mov     r15d, r13d
0x140027f2a  mov     [rsp+140h+var_D8], r13d
0x140027f2f  mov     rcx, [rcx+8]
0x140027f33  mov     rax, [rcx]
0x140027f36  mov     rax, [rax+28h]
0x140027f3a  call    _guard_dispatch_icall
0x140027f3f  xor     ecx, ecx
0x140027f41  mov     [rsp+140h+var_E0], rax
0x140027f46  mov     rsi, rax
0x140027f49  test    rax, rax
0x140027f4c  jz      loc_140028DAC
0x140027f52  prefetchw byte ptr [rax+8]
0x140027f56  mov     r14d, [rax+8]
0x140027f5a  mov     eax, dword ptr [rsp+140h+var_108]
0x140027f5e  and     r14d, 0FFFFFFFEh
0x140027f62  and     eax, 0FFFFFFFCh
0x140027f65  cmp     r14d, eax
0x140027f68  jnz     loc_140028C5C
0x140027f6e  mov     rax, [rbp+40h+var_60]
0x140027f72  mov     edx, [rsi]
0x140027f74  mov     rcx, [rax+8]
0x140027f78  mov     rax, [rcx]
0x140027f7b  mov     rax, [rax+60h]
0x140027f7f  call    _guard_dispatch_icall
0x140027f84  test    byte ptr [rax+0Eh], 20h
0x140027f88  jnz     loc_140028FC7
0x140027f8e  mov     r14, [rsp+140h+var_100]
0x140027f93  test    r15d, r15d
0x140027f96  jz      loc_140028020
0x140027f9c  cmp     byte ptr [rsi+0Eh], 5
0x140027fa0  mov     rdi, [rsp+140h+var_D0]
0x140027fa5  jnz     short loc_140027FF0
0x140027fa7  movzx   eax, byte ptr [rsi+0Ch]
0x140027fab  movzx   ecx, byte ptr [rsi+0Dh]
0x140027faf  shl     cx, 8
0x140027fb3  or      cx, ax
0x140027fb6  mov     eax, dword ptr [rsp+140h+var_E8]
0x140027fba  shr     eax, 10h
0x140027fbd  cmp     cx, ax
0x140027fc0  jnz     short loc_140027FF0
0x140027fc2  mov     rcx, [rdi+8]
0x140027fc6  mov     edx, [rsi]
0x140027fc8  mov     rax, [rcx]
0x140027fcb  mov     rax, [rax+60h]
0x140027fcf  call    _guard_dispatch_icall
0x140027fd4  mov     rcx, [rbp+40h+var_60]
0x140027fd8  mov     edx, 3
0x140027fdd  mov     r14, rax
0x140027fe0  add     [rax+8], r13d
0x140027fe4  mov     r8, [rax+2C8h]
0x140027feb  call    ?TrackObjectReferenceIncrement@@YAXAEAUSESSION_GLOBALS@Base@Gre@@W4ReferenceTrackerCountedType@@PEAX@Z; TrackObjectReferenceIncrement(Gre::Base::SESSION_GLOBALS &,ReferenceTrackerCountedType,void *)
0x140027ff0  mov     rdi, [rdi+8]
0x140027ff4  mov     edx, [rsi]
0x140027ff6  mov     rcx, rdi
0x140027ff9  mov     rbx, [rdi]
0x140027ffc  mov     rax, [rbx+60h]
0x140028000  call    _guard_dispatch_icall
0x140028005  mov     rdx, rax
0x140028008  mov     rcx, rdi
0x14002800b  mov     rax, [rbx+30h]
0x14002800f  call    _guard_dispatch_icall
0x140028014  call    cs:__imp_KeLeaveCriticalRegion
0x14002801b  nop     dword ptr [rax+rax+00h]
0x140028020  xor     r15d, r15d
0x140028023  mov     [rbp+40h+var_78], r14
0x140028027  test    r14, r14
0x14002802a  jz      loc_140028A57
0x140028030  test    [rsp+140h+var_110], 2
0x140028035  mov     rax, [rsp+140h+var_C8]
0x14002803a  setnz   byte ptr [rsp+140h+var_D8]
0x14002803f  test    [rsp+140h+var_110], 2
0x140028044  mov     rax, [rax]
0x140028047  lea     rax, [rax+478h]
0x14002804e  mov     [rsp+140h+var_E0], rax
0x140028053  mov     rcx, rax; Resource
0x140028056  jnz     loc_140028B42
0x14002805c  call    ?GreAcquireSemaphoreInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreInternal(HSEMAPHORE__ *)
0x140028061  call    ??$GrepAcquireLockValidate@$01@@YAXXZ; GrepAcquireLockValidate<2>(void)
0x140028066  call    cs:__imp_W32GetSessionState
0x14002806d  nop     dword ptr [rax+rax+00h]
0x140028072  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, r15d
0x140028079  mov     rcx, [rax+58h]
0x14002807d  mov     rbx, [rcx]
0x140028080  jnz     loc_140029159
0x140028086  lea     rdx, [rbx+5E8h]
0x14002808d  call    ??$GreAcquireSemaphoreCommon@$0BE@P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140028092  mov     rdi, [rbp+40h+var_70]
0x140028096  mov     ebx, r13d
0x140028099  mov     rsi, [rbp+40h+var_78]
0x14002809d  mov     [rsp+140h+var_F0], ebx
0x1400280a1  mov     rdx, [rdi]
0x1400280a4  mov     rax, [rdx+30h]
0x1400280a8  mov     [rbp+40h+var_50], rax
0x1400280ac  cmp     [rdx], r15
0x1400280af  jnz     loc_140028A84
0x1400280b5  lea     r8, [rdx+868h]
0x1400280bc  xorps   xmm0, xmm0
0x1400280bf  movups  xmmword ptr [r8], xmm0
0x1400280c3  xor     eax, eax
0x1400280c5  mov     [r8+10h], rax
0x1400280c9  mov     dword ptr [rdx+870h], 80000012h
0x1400280d3  mov     [rdx+878h], r15
0x1400280da  mov     rdi, [rdi]
0x1400280dd  cmp     [rdi+20h], r13d
0x1400280e1  jnz     loc_1400290D0
0x1400280e7  cmp     [rsi+0C8h], r15d
0x1400280ee  jnz     loc_140028F5F
0x1400280f4  mov     rdi, [rdi+30h]
0x1400280f8  cmp     [rsi+64h], r15w
0x1400280fd  jnz     loc_140028FA0
0x140028103  cmp     [rsi+18h], r15
0x140028107  jnz     loc_140028FA0
0x14002810d  mov     r15, [rsi+0A0h]
0x140028114  xor     ecx, ecx
0x140028116  test    r15, r15
0x140028119  jnz     short loc_140028141
0x14002811b  mov     eax, [rdi+82Ch]
0x140028121  cmp     [rsi+60h], eax
0x140028124  jnz     loc_140029188
0x14002812a  test    dword ptr [rdi+86Ch], 100h
0x140028134  jnz     loc_140029151
0x14002813a  mov     r15, [rdi+700h]
0x140028141  mov     rax, [rsi+30h]
0x140028145  mov     r14d, [r8+8]
0x140028149  mov     [rbp+40h+var_68], rax
0x14002814d  call    cs:__imp_W32GetSessionState
0x140028154  nop     dword ptr [rax+rax+00h]
0x140028159  xor     edx, edx
0x14002815b  mov     rcx, [rax+58h]
0x14002815f  cmp     rsi, [rcx+1118h]
0x140028166  jz      short loc_140028171
0x140028168  test    rdi, rdi
0x14002816b  jnz     loc_140028AB0
0x140028171  and     r14d, 0FFFFFFFEh
0x140028175  jz      short loc_140028187
0x140028177  test    dword ptr [rsi+90h], 800h
0x140028181  jnz     loc_14002900E
0x140028187  mov     dil, [rsp+140h+var_110]
0x14002818c  test    dil, 4
0x140028190  jz      loc_140028C3B
0x140028196  call    cs:__imp_W32GetSessionState
0x14002819d  nop     dword ptr [rax+rax+00h]
0x1400281a2  mov     rcx, [rbp+40h+var_70]
0x1400281a6  xor     edx, edx
0x1400281a8  mov     r10, [rcx]
0x1400281ab  mov     r14, [r10+1F0h]
0x1400281b2  test    r14, r14
0x1400281b5  jnz     loc_140028A74
0x1400281bb  mov     rax, [rax+58h]
0x1400281bf  mov     r14, [rax+1118h]
0x1400281c6  bt      dword ptr [r14+90h], 1Ah
0x1400281cf  jnb     loc_140028BE2
0x1400281d5  bt      dword ptr [rsi+90h], 1Ah
0x1400281dd  jnb     loc_140028BE2
0x1400281e3  test    dword ptr [r14+94h], 200h
0x1400281ee  jnz     loc_140028BE2
0x1400281f4  mov     rax, [r10+3D0h]
0x1400281fb  mov     [rsp+140h+var_100], rdx
0x140028200  mov     ecx, [rax+6Ch]
0x140028203  mov     dword ptr [rbp+40h+var_60], ecx
0x140028206  and     ecx, 7
0x140028209  mov     dword ptr [rbp+40h+var_58], ecx
0x14002820c  jnz     loc_140028CDD
0x140028212  cmp     [rsi+0A0h], r15
0x140028219  jnz     loc_140028C90
0x14002821f  test    dword ptr [r14+90h], 1000000h
0x14002822a  jz      short loc_140028234
0x14002822c  mov     rax, [r14]
0x14002822f  mov     [rsp+140h+var_100], rax
0x140028234  mov     rdi, [r14+20h]
0x140028238  mov     [rsp+140h+var_108], rdi
0x14002823d  cmp     [rsp+140h+var_E8], rdi
0x140028242  jz      loc_140028C88
0x140028248  call    cs:__imp_W32GetSessionState
0x14002824f  nop     dword ptr [rax+rax+00h]
0x140028254  mov     r15, [rbp+40h+var_70]
0x140028258  mov     rcx, [rax+58h]
0x14002825c  mov     rax, [rcx+1118h]
0x140028263  mov     rcx, [r15]; this
0x140028266  cmp     rsi, rax
0x140028269  jnz     loc_140028B6C
0x14002826f  mov     eax, [rcx+208h]
0x140028275  xor     edi, edi
0x140028277  mov     [rcx+1F0h], rdi
0x14002827e  test    r13b, al
0x140028281  jz      short loc_1400282A6
0x140028283  or      dword ptr [rcx+24h], 10h
  ... truncated ...
```
