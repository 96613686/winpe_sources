# GrepSelectBitmap(XDCOBJ &,HBITMAP__ *,GSBOptions)

- ea: `0x140027d70`
- end: `0x14002921d`
- name: `?GrepSelectBitmap@@YA?AVGSBResult@@AEAVXDCOBJ@@PEAUHBITMAP__@@W4GSBOptions@@@Z`
- size: `5293`
- prototype: ``
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
__int64 __fastcall GrepSelectBitmap(__int64 a1, __int64 *a2, _DWORD *a3, __int64 a4)
{
  unsigned int v4; // esi
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  struct _GRETHREAD *v11; // rax
  struct _GRETHREAD *v12; // rbx
  char v13; // r13
  __int64 v14; // r8
  char v15; // cl
  SURFACE *v16; // r14
  __int64 v17; // rbx
  unsigned int v18; // edi
  __int64 *CurrentThreadWin32ThreadAndEnterCriticalRegion; // rsi
  __int64 v20; // rbx
  int v21; // r15d
  HSEMAPHORE v22; // rax
  HSEMAPHORE v23; // rsi
  unsigned int v24; // r14d
  __int64 v25; // rdi
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 *v28; // rdi
  __int64 v29; // rbx
  __int64 v30; // rax
  int v31; // edx
  __int64 *v32; // rcx
  int v33; // r8d
  __int64 v34; // rbx
  __int64 *v35; // rdi
  int v36; // ebx
  SURFACE *v37; // rsi
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // rdi
  __int64 v41; // rdi
  __int64 v42; // r15
  int v43; // r14d
  __int64 *v44; // rcx
  unsigned int v45; // r14d
  __int64 SessionState; // rax
  DC *v47; // r10
  __int64 v48; // r14
  __int64 v49; // rax
  __int64 v50; // rcx
  _DWORD *v51; // rdi
  __int64 v52; // rax
  DC **v53; // r15
  __int64 v54; // rcx
  int v55; // eax
  __int64 v56; // rcx
  __int64 v57; // rdx
  __int64 v58; // rcx
  __int64 v59; // rax
  __int64 v60; // rbx
  __int64 v61; // rdx
  unsigned int *v62; // r15
  __int64 v63; // r8
  __int64 v64; // rdx
  __int64 *v65; // rdi
  __int64 v66; // rbx
  __int64 v67; // rax
  int (*v68)(void); // rax
  __int64 v69; // rdx
  __int64 v70; // rcx
  void (__fastcall *v71)(DC **, SURFACE *, __int64); // rax
  int v72; // eax
  BOOL v73; // r8d
  int v74; // eax
  int v75; // ecx
  unsigned int v76; // eax
  __int64 v77; // rcx
  int v78; // edx
  int v79; // edx
  __int64 v80; // rcx
  __int64 v81; // rax
  __int64 v82; // rax
  SURFACE *v83; // rbx
  __int64 v84; // rdi
  __int64 v85; // rdx
  unsigned int *v86; // rsi
  __int64 v87; // r8
  __int64 v88; // rdx
  __int64 *v89; // rdi
  __int64 v90; // rbx
  __int64 v91; // rax
  __int64 v92; // rcx
  __int64 v93; // rax
  DC *v94; // r15
  __int64 v95; // rdi
  _DWORD *v96; // r14
  __int64 v97; // rsi
  int v98; // eax
  int v99; // r9d
  int v100; // r10d
  int v101; // edx
  int v102; // r8d
  _DWORD *v103; // rcx
  struct _GRETHREAD *v104; // rax
  __int64 v105; // rdx
  __int64 v106; // r8
  __int64 v107; // r9
  unsigned int v108; // edi
  __int64 *v109; // rax
  __int64 v110; // rcx
  __int64 v111; // rdx
  unsigned int v112; // esi
  int v113; // eax
  __int64 v114; // rdi
  unsigned int v115; // esi
  __int64 *v116; // r14
  __int64 v117; // rdi
  int v118; // r15d
  __int64 v119; // rax
  unsigned int *v120; // r14
  unsigned int v121; // esi
  __int64 v122; // rsi
  __int64 v123; // rax
  __int64 v124; // rcx
  __int64 *v125; // rsi
  __int64 v126; // rdi
  __int64 v127; // rax
  __int64 v128; // rdi
  int v129; // eax
  __int64 v130; // rcx
  __int64 v131; // rdx
  __int64 v132; // rax
  __int64 v133; // rax
  int v134; // edx
  __int64 v135; // rax
  __int64 v136; // rdx
  __int64 v137; // rcx
  int v138; // r8d
  HSEMAPHORE v139; // r14
  struct _KTHREAD *CurrentThread; // rsi
  __int64 v141; // rdi
  __int64 *ThreadWin32Thread; // rax
  __int64 v143; // rax
  __int64 v144; // rdi
  __int64 v145; // rcx
  bool v146; // zf
  __int64 v147; // rax
  char v149; // al
  int v150; // eax
  __int64 v151; // rax
  __int64 v152; // rax
  __int64 v153; // rcx
  __int64 v154; // rax
  __int64 v155; // r10
  __int64 v156; // r11
  unsigned int v157; // edx
  int v158; // eax
  unsigned int v159; // edx
  char v160; // r8
  DC *v161; // r10
  __int64 v162; // rax
  __int64 v163; // rcx
  __int64 v164; // rcx
  __int64 v165; // r10
  __int64 v166; // r11
  unsigned int v167; // edx
  int v168; // eax
  unsigned int v169; // edx
  int v170; // edx
  unsigned __int64 i; // rcx
  int v172; // eax
  ThreadRestrictNewHandlesRegion *v173; // rcx
  ThreadRestrictNewHandlesRegion *v174; // rcx
  int CurrentWin32kSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  __int64 v177; // rax
  char v178; // [rsp+30h] [rbp-D0h]
  __int64 v179; // [rsp+38h] [rbp-C8h] BYREF
  SURFACE *v180; // [rsp+40h] [rbp-C0h]
  HSEMAPHORE v181; // [rsp+48h] [rbp-B8h]
  unsigned int v182[2]; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD *v183; // [rsp+58h] [rbp-A8h] BYREF
  HSEMAPHORE v184; // [rsp+60h] [rbp-A0h] BYREF
  int v185; // [rsp+68h] [rbp-98h]
  __int16 v186; // [rsp+6Ch] [rbp-94h]
  __int64 v187; // [rsp+70h] [rbp-90h]
  __int64 v188; // [rsp+78h] [rbp-88h]
  __int128 v189; // [rsp+80h] [rbp-80h] BYREF
  __int128 v190; // [rsp+90h] [rbp-70h]
  __int64 v191; // [rsp+A0h] [rbp-60h]
  __int128 v192; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v193; // [rsp+B8h] [rbp-48h]
  SURFACE *v194; // [rsp+C8h] [rbp-38h]
  __int64 *v195; // [rsp+D0h] [rbp-30h]
  __int64 v196; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v197; // [rsp+E0h] [rbp-20h]
  __int64 v198; // [rsp+E8h] [rbp-18h]
  _BYTE v199[12]; // [rsp+F0h] [rbp-10h] BYREF
  __int16 v200; // [rsp+FCh] [rbp-4h]
  __int64 v201; // [rsp+100h] [rbp+0h]

  v178 = a4;
  v192 = 0;
  v4 = (unsigned int)a3;
  v183 = a3;
  v193 = 0;
  v195 = a2;
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(a1, a2, a3, a4);
  if ( CurrentThreadWin32Thread )
    v8 = *CurrentThreadWin32Thread;
  else
    v8 = 0;
  v9 = (v8 + 8) & -(__int64)(v8 != 0);
  *(_QWORD *)&v193 = &v192;
  *((_QWORD *)&v193 + 1) = UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
  if ( v9 )
  {
    v10 = *(_QWORD *)(((v8 + 8) & -(__int64)(v8 != 0)) + 0x58);
    if ( *(_QWORD *)(v10 + 8) != v9 + 88 )
      goto LABEL_5;
    *(_QWORD *)&v192 = *(_QWORD *)(v9 + 88);
    *((_QWORD *)&v192 + 1) = v9 + 88;
    *(_QWORD *)(v10 + 8) = &v192;
    *(_QWORD *)(v9 + 88) = &v192;
  }
  else
  {
    *((_QWORD *)&v192 + 1) = &v192;
    *(_QWORD *)&v192 = &v192;
  }
  v188 = a2[2];
  v194 = 0;
  v181 = (HSEMAPHORE)(**(_QWORD **)(((__int64 (*)(void))W32GetSessionState)() + 88) + 624LL);
  EngAcquireSemaphoreShared(v181);
  v11 = GreGetCurrentThreadCrossSessionCheck();
  v12 = v11;
  v13 = 1;
  if ( v11 )
  {
    v14 = *(_QWORD *)v11;
    if ( (*(_QWORD *)v11 & 0xFFFFFFDFFFFFFFFEuLL) != 0 && (*(_QWORD *)v11 & 2) == 0 )
    {
      v170 = 38;
      for ( i = 0; i < 0x40; ++i )
      {
        v172 = i;
        if ( ((1LL << i) & 0xFFFFFFDFFFFFFFFFuLL & v14) == 0 )
          v172 = v170;
        v170 = v172;
      }
      if ( v172 > 1 && v172 != 38 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(i, (unsigned int)v172, v14, 0xFFFFFFDFFFFFFFFFuLL);
    }
    v15 = *((_BYTE *)v12 + 9);
    *((_BYTE *)v12 + 9) = v15 + 1;
    if ( !v15 )
      *(_QWORD *)v12 |= 2uLL;
  }
  v180 = 0;
  v186 = 0;
  v16 = 0;
  v197 = *(_QWORD *)(((__int64 (*)(void))W32GetSessionState)() + 88);
  v17 = 0;
  v187 = v197;
  v18 = (unsigned __int16)v4 | (v4 >> 8) & 0xFF0000;
  v179 = 0;
  CurrentThreadWin32ThreadAndEnterCriticalRegion = (__int64 *)PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion(&v179);
  if ( !(unsigned int)IsThreadCrossSessionAttached() && CurrentThreadWin32ThreadAndEnterCriticalRegion )
    v17 = *CurrentThreadWin32ThreadAndEnterCriticalRegion;
  v20 = (v17 + 8) & -(__int64)(v17 != 0);
  if ( v20 )
    v198 = *(_QWORD *)(v20 + 64);
  else
    v198 = 0;
  v21 = 1;
  v185 = 1;
  v22 = (HSEMAPHORE)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v197 + 8) + 40LL))(
                      *(_QWORD *)(v197 + 8),
                      v18);
  v184 = v22;
  v23 = v22;
  if ( v22 )
  {
    _m_prefetchw(v22 + 2);
    v24 = (_DWORD)v22[2] & 0xFFFFFFFE;
    if ( v24 != (v179 & 0xFFFFFFFC) && v24 && (!v198 || v24 != (unsigned int)UMPDGetThreadClientPID(v20)) )
    {
      HANDLELOCK::vUnlock((HANDLELOCK *)&v184);
      v21 = v185;
      v23 = v184;
      goto LABEL_19;
    }
    if ( (*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v197 + 8) + 96LL))(
                       *(_QWORD *)(v197 + 8),
                       *(_DWORD *)v23)
                   + 14)
        & 0x20) == 0 )
    {
LABEL_19:
      v16 = v180;
      goto LABEL_20;
    }
    v16 = 0;
    if ( !v20
      || (v173 = *(ThreadRestrictNewHandlesRegion **)(v20 + 328)) == 0
      || !*((_BYTE *)v173 + 80)
      || !ThreadRestrictNewHandlesRegion::InRegion(v173, v18) )
    {
      LOBYTE(v186) = 1;
      HANDLELOCK::vUnlock((HANDLELOCK *)&v184);
      v21 = v185;
      v23 = v184;
    }
  }
  else
  {
    v21 = 0;
    KeLeaveCriticalRegion();
  }
LABEL_20:
  if ( v21 )
  {
    v25 = v187;
    if ( *((_BYTE *)v23 + 14) == 5 && *((_WORD *)v23 + 6) == WORD1(v183) )
    {
      v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v187 + 8) + 96LL))(
              *(_QWORD *)(v187 + 8),
              *(_DWORD *)v23);
      v27 = v197;
      v16 = (SURFACE *)v26;
      ++*(_DWORD *)(v26 + 8);
      TrackObjectReferenceIncrement(v27, 3, *(_QWORD *)(v26 + 712));
    }
    v28 = *(__int64 **)(v25 + 8);
    v29 = *v28;
    v30 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v28 + 96))(v28, *(_DWORD *)v23);
    (*(void (__fastcall **)(__int64 *, __int64))(v29 + 48))(v28, v30);
    KeLeaveCriticalRegion();
  }
  v194 = v16;
  if ( v16 )
  {
    LOBYTE(v185) = (v178 & 2) != 0;
    v184 = (HSEMAPHORE)(*(_QWORD *)v188 + 1144LL);
    if ( (v178 & 2) != 0 )
      EngAcquireSemaphoreShared(v184);
    else
      GreAcquireSemaphoreInternal(v184);
    GrepAcquireLockValidate<2>();
    v32 = *(__int64 **)(((__int64 (*)(void))W32GetSessionState)() + 88);
    v34 = *v32;
    if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
      McTemplateK0pqz_EtwWriteTransfer((_DWORD)v32, v31, v33, v34 + 1512, 0, (__int64)L"Hmgr");
    GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(v32, v34 + 1512);
    v35 = v195;
    v36 = 1;
    v37 = v194;
    v182[0] = 1;
    v38 = *v195;
    *(_QWORD *)v199 = *(_QWORD *)(*v195 + 48);
    if ( *(_QWORD *)v38 )
    {
      v39 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v195[2] + 8) + 8LL))(*(_QWORD *)(v195[2] + 8));
    }
    else
    {
      v39 = v38 + 2152;
      *(_OWORD *)(v38 + 2152) = 0;
      *(_QWORD *)(v38 + 2168) = 0;
      *(_DWORD *)(v38 + 2160) = -2147483630;
      *(_QWORD *)(v38 + 2168) = 0;
    }
    v40 = *v35;
    if ( *(_DWORD *)(v40 + 32) != 1 )
    {
      *(_BYTE *)(a1 + 8) = 6;
      goto LABEL_245;
    }
    if ( *((_DWORD *)v37 + 50) && !(unsigned int)SURFACE::bStockSurface(v37) && *((_QWORD *)v37 + 24) != *(_QWORD *)v40 )
    {
      *(_BYTE *)(a1 + 8) = 7;
LABEL_245:
      *(_QWORD *)a1 = 0;
      v177 = ((__int64 (*)(void))W32GetSessionState)();
      GreReleaseSemaphoreExclusive<20,>(*(_QWORD *)(v177 + 88));
      SEMOBJEXORSHARED<2>::~SEMOBJEXORSHARED<2>(&v184);
      goto LABEL_150;
    }
    v41 = *(_QWORD *)(v40 + 48);
    if ( (*((_WORD *)v37 + 50) || *((_QWORD *)v37 + 3)) && *((_QWORD *)v37 + 6) != v41 )
    {
LABEL_223:
      *(_BYTE *)(a1 + 8) = v13;
      goto LABEL_245;
    }
    v42 = *((_QWORD *)v37 + 20);
    if ( !v42 )
    {
      if ( *((_DWORD *)v37 + 24) != *(_DWORD *)(v41 + 2092) )
      {
        v13 = 2;
        goto LABEL_223;
      }
      if ( (*(_DWORD *)(v41 + 2156) & 0x100) != 0 )
        v42 = 0;
      else
        v42 = *(_QWORD *)(v41 + 1792);
    }
    v43 = *(_DWORD *)(v39 + 8);
    v196 = *((_QWORD *)v37 + 6);
    v44 = *(__int64 **)(W32GetSessionState(0) + 88);
    if ( v37 != (SURFACE *)v44[547] && v41 && *((_QWORD *)v37 + 5) )
    {
      v44 = (__int64 *)(*(_DWORD *)(v41 + 40) & 1);
      if ( (*(_DWORD *)(v41 + 40) & 1) != 0 && (*((_DWORD *)v37 + 36) & 0x40000) != 0 )
      {
        *(_DWORD *)v199 = 33279186;
        *(_QWORD *)&v199[4] = 1;
        RtlLogUnexpectedCodepath(v199, 0);
        v149 = 3;
        goto LABEL_161;
      }
      if ( v196 && (_DWORD)v44 != (*(_DWORD *)(v196 + 40) & 1) )
      {
        *(_DWORD *)v199 = 33279186;
        *(_QWORD *)&v199[4] = 2;
        RtlLogUnexpectedCodepath(v199, 0);
        v149 = 4;
LABEL_161:
        *(_QWORD *)a1 = 0;
        *(_BYTE *)(a1 + 8) = v149;
        MLOCKOBJ::~MLOCKOBJ((MLOCKOBJ *)v182);
        SEMOBJEXORSHARED<2>::~SEMOBJEXORSHARED<2>(&v184);
        GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal, v181);
        SURFREF::~SURFREF((SURFREF *)&v192);
        return a1;
      }
    }
    v45 = v43 & 0xFFFFFFFE;
    if ( v45 && (*((_DWORD *)v37 + 36) & 0x800) != 0 )
    {
      *(_BYTE *)(a1 + 8) = 9;
      goto LABEL_173;
    }
    if ( (v178 & 4) == 0 && !v45 )
    {
      *(_BYTE *)(a1 + 8) = 10;
      goto LABEL_173;
    }
    SessionState = W32GetSessionState(v44);
    v44 = v195;
    v47 = (DC *)*v195;
    v48 = *(_QWORD *)(*v195 + 496);
    if ( v48 )
    {
      if ( v195[3] )
        v48 = v195[3];
    }
    else
    {
      v48 = *(_QWORD *)(*(_QWORD *)(SessionState + 88) + 4376LL);
    }
    if ( (!_bittest((const signed __int32 *)(v48 + 144), 0x1Au)
       || !_bittest((const signed __int32 *)v37 + 36, 0x1Au)
       || (*(_DWORD *)(v48 + 148) & 0x200) != 0)
      && (v178 & 1) == 0 )
    {
      *(_BYTE *)(a1 + 8) = 11;
LABEL_173:
      *(_QWORD *)a1 = 0;
      v151 = W32GetSessionState(v44);
      GreReleaseSemaphoreExclusive<20,>(*(_QWORD *)(v151 + 88));
      SEMOBJEXORSHARED<2>::~SEMOBJEXORSHARED<2>(&v184);
      GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal, v181);
      v146 = v194 == 0;
      goto LABEL_145;
    }
    v49 = *((_QWORD *)v47 + 122);
    v180 = 0;
    LODWORD(v197) = *(_DWORD *)(v49 + 108);
    v50 = v197 & 7;
    LODWORD(v198) = v197 & 7;
    if ( (v197 & 7) != 0 )
    {
      *(_DWORD *)(v49 + 108) = 0;
      v153 = *((_QWORD *)v47 + 122);
      *(_QWORD *)v182 = *(_QWORD *)(v153 + 316);
      v154 = *(_QWORD *)(v153 + 324);
      v182[0] = -v182[0];
      HIDWORD(v179) = HIDWORD(v154);
      LODWORD(v179) = -(int)v154;
      *(_QWORD *)(v153 + 316) = *(_QWORD *)v182;
      *(_QWORD *)(*((_QWORD *)v47 + 122) + 324LL) = v179;
      DC::MirrorWindowOrg(v47);
      v156 = *(_QWORD *)(v155 + 976);
      if ( (*(_BYTE *)(v156 + 272) & 6) != 6 )
      {
        *(_DWORD *)(v156 + 272) ^= 2u;
        v156 = *(_QWORD *)(v155 + 976);
      }
      v157 = *(_DWORD *)(v155 + 248);
      v50 = v157;
      v158 = v157 | 4;
      v159 = v157 & 0xFFFFFFFB;
      if ( (v50 & 4) == 0 )
        v159 = v158;
      *(_DWORD *)(v155 + 248) = v159;
      *(_DWORD *)(v156 + 340) |= 0x4090u;
    }
    if ( *((_QWORD *)v37 + 20) != v42 )
    {
      *((_DWORD *)v37 + 36) |= 0x8000000u;
      *((_QWORD *)v37 + 20) = v42;
      if ( v42 )
      {
        v152 = W32GetSessionState(v50);
        HmgIncrementShareReferenceCount(*(_QWORD *)(v152 + 88), v42);
      }
    }
    if ( (*(_DWORD *)(v48 + 144) & 0x1000000) != 0 )
      v180 = *(SURFACE **)v48;
    v51 = *(_DWORD **)(v48 + 32);
    v179 = (__int64)v51;
    if ( v183 == v51 )
      goto LABEL_133;
    v52 = W32GetSessionState(v50);
    v53 = (DC **)v195;
    v54 = *v195;
    if ( v37 == *(SURFACE **)(*(_QWORD *)(v52 + 88) + 4376LL) )
    {
      v55 = *(_DWORD *)(v54 + 520);
      *(_QWORD *)(v54 + 496) = 0;
      if ( (v55 & 1) != 0 )
      {
        *(_DWORD *)(v54 + 36) |= 0x10u;
        *(_QWORD *)(v54 + 524) = 0;
        *(_DWORD *)(v54 + 520) = v55 & 0xFFFFFFF8 | 4;
        *(_QWORD *)(v54 + 532) = 0;
        DC::vUpdateCachedDPIScaleValue((DC *)v54);
      }
    }
    else
    {
      *(_QWORD *)(v54 + 496) = v37;
      if ( (*((_DWORD *)v37 + 37) & 0x800) != 0 )
      {
        DC::vSetDpiScaling(v54, *(_QWORD *)((char *)v37 + 692));
      }
      else
      {
        v150 = *(_DWORD *)(v54 + 520);
        if ( (v150 & 1) != 0 )
        {
          *(_DWORD *)(v54 + 36) |= 0x10u;
          *(_QWORD *)(v54 + 524) = 0;
          *(_QWORD *)(v54 + 532) = 0;
          *(_DWORD *)(v54 + 520) = v150 & 0xFFFFFFF8 | 4;
          DC::vUpdateCachedDPIScaleValue((DC *)v54);
        }
      }
      if ( (*(_DWORD *)v37 & 0x800000) != 0 && _bittest16((const signed __int16 *)v37 + 51, 9u)
        || !*((_WORD *)v37 + 50) && *((_DWORD *)v37 + 62) )
      {
        *((_DWORD *)*v53 + 9) |= 0x10000u;
      }
      else
      {
        *((_DWORD *)*v53 + 9) &= ~0x10000u;
      }
    }
    *((_QWORD *)*v53 + 64) = *((_QWORD *)v37 + 7);
    v56 = *((_QWORD *)*v53 + 122);
    *(_DWORD *)(v56 + 152) |= 0xFu;
    v58 = *(_QWORD *)(W32GetSessionState(v56) + 88);
    if ( v48 == *(_QWORD *)(v58 + 4376) )
    {
LABEL_71:
      v68 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v58, v57) + 24) + 608LL);
      if ( v68 )
      {
        if ( v68() >= 0 )
        {
          v71 = *(void (__fastcall **)(DC **, SURFACE *, __int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v70, v69) + 24)
                                                                 + 616LL);
          if ( v71 )
            v71(v53, v37, 1);
        }
      }
      v72 = *((_DWORD *)v37 + 36);
      v73 = (v72 & 0x4000) != 0 || (v72 & 0x800010) != 0 && (*(_DWORD *)(*(_QWORD *)v199 + 40LL) & 1) != 0;
      v74 = *((_DWORD *)*v53 + 9);
      v75 = v74 | 0x200;
      v76 = v74 & 0xFFFFFDFF;
      if ( !v73 )
        v75 = v76;
      *((_DWORD *)*v53 + 9) = v75;
      v77 = *((unsigned int *)*v53 + 9);
      if ( (v77 & 0x200) != 0 && (*((_DWORD *)v37 + 36) & 0x200) != 0 )
        LODWORD(v77) = v77 | 0x8000;
      else
        LODWORD(v77) = v77 & 0xFFFF7FFF;
      *((_DWORD *)*v53 + 9) = v77;
      if ( v37 != *(SURFACE **)(*(_QWORD *)(W32GetSessionState(v77) + 88) + 4376LL) )
      {
        SURFACE::vInc_cRef(v37);
        if ( (*(_DWORD *)v37 & 0x800000) == 0 || (*((_WORD *)v37 + 51) & 0x200) == 0 )
        {
          *((_QWORD *)v37 + 24) = *(_QWORD *)*v53;
          *((_QWORD *)v37 + 6) = *((_QWORD *)*v53 + 6);
        }
      }
      if ( *((_WORD *)v37 + 50) || (v78 = 1, !*((_QWORD *)v37 + 28)) )
        v78 = 0;
      **((_DWORD **)*v53 + 122) = v78 | **((_DWORD **)*v53 + 122) & 0xFFFFFFFE;
      if ( *((_WORD *)v37 + 50) || (v79 = 1, !*((_QWORD *)v37 + 28)) )
        v79 = 0;
      v80 = *((_QWORD *)*v53 + 122);
      if ( v79 )
        v81 = *((_QWORD *)v37 + 29);
      else
        v81 = 0;
      *(_QWORD *)(v80 + 24) = v81;
      v82 = W32GetSessionState(v80);
      v83 = v194;
      *(_QWORD *)&v189 = 0;
      v84 = *(_QWORD *)(v82 + 88);
      v85 = (unsigned __int16)*(_DWORD *)v194 | (*(_DWORD *)v194 >> 8) & 0xFF0000u;
      DWORD2(v189) = 0;
      WORD6(v189) = 0;
      *(_QWORD *)&v190 = v84;
      HANDLELOCK::vLockHandle(&v189, v85, 1);
      if ( !DWORD2(v189) )
      {
        HmgPentryFromPobj(v84, v83);
        goto LABEL_100;
      }
      v86 = (unsigned int *)v189;
      switch ( *(_BYTE *)(v189 + 14) )
      {
        case 4:
          v87 = *((_QWORD *)v83 + 14);
          v88 = 2;
          break;
        case 5:
          v87 = *((_QWORD *)v83 + 89);
          v88 = 3;
          break;
        case 0x10:
          v87 = *((_QWORD *)v83 + 17);
          v88 = 0;
          break;
        default:
          goto LABEL_99;
      }
      TrackObjectReferenceDecrement(v84, v88, v87);
LABEL_99:
      --*((_DWORD *)v83 + 2);
      v89 = *(__int64 **)(v190 + 8);
      v90 = *v89;
      v91 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v89 + 96))(v89, *v86);
      (*(void (__fastcall **)(__int64 *, __int64))(v90 + 48))(v89, v91);
      KeLeaveCriticalRegion();
LABEL_100:
      v194 = 0;
      v93 = W32GetSessionState(v92);
      GreReleaseSemaphoreExclusive<20,>(*(_QWORD *)(v93 + 88));
      v36 = 0;
      DC::bSetDefaultRegion(*v53);
      v94 = *v53;
      KeEnterCriticalRegion();
      ExAcquirePushLockSharedEx((char *)v94 + 1112, 0);
      GrepAcquireLockValidate<37>();
      GrepAcquireLockValidate<38>();
      v95 = *v195;
      v96 = *(_DWORD **)(*v195 + 1136);
      if ( *(_QWORD *)*v195 )
      {
        v97 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v188 + 8) + 8LL))(*(_QWORD *)(v188 + 8), *v195);
      }
      else
      {
        v97 = v95 + 2152;
        *(_OWORD *)(v95 + 2152) = 0;
        *(_QWORD *)(v95 + 2168) = 0;
        *(_DWORD *)(v95 + 2160) = -2147483630;
        *(_QWORD *)(v95 + 2168) = 0;
      }
      if ( (*(_BYTE *)(v97 + 15) & 4) != 0 )
      {
        if ( !v96
          || (v183 = v96,
              *(_DWORD *)(*(_QWORD *)(v95 + 976) + 116LL) = RGNOBJ::iComplexity((RGNOBJ *)&v183),
              (unsigned int)RGNOBJ::iComplexity((RGNOBJ *)&v183) == 1) )
        {
          *(_OWORD *)(*(_QWORD *)(v95 + 976) + 120LL) = xmmword_140251EB8;
        }
        else
        {
          v98 = *(_DWORD *)(v95 + 1036);
          v99 = *(_DWORD *)(v95 + 1032);
          v100 = v96[14] - v98;
          v101 = v96[16] - v98;
          v102 = v96[15] - v99;
          v103 = *(_DWORD **)(v95 + 976);
          v103[30] = v96[13] - v99;
          v103[31] = v100;
          v103[32] = v102;
          v103[33] = v101;
        }
        *(_BYTE *)(v97 + 15) &= ~4u;
      }
      v104 = GreGetCurrentThreadCrossSessionCheck();
      if ( v104 )
        *(_QWORD *)v104 &= ~0x4000000000uLL;
      GrePushLock::ReleaseLock((DC *)((char *)v94 + 1112));
      v108 = (unsigned int)v180;
      if ( v180 )
      {
        v189 = 0;
        v190 = 0;
        v109 = (__int64 *)PsGetCurrentThreadWin32Thread(v50, v105, v106, v107);
        if ( v109 )
          v110 = *v109;
        else
          v110 = 0;
        *(_QWORD *)&v190 = &v189;
        *((_QWORD *)&v190 + 1) = UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
        if ( ((v110 + 8) & -(__int64)(v110 != 0)) != 0 )
        {
          v111 = *(_QWORD *)(((v110 + 8) & -(__int64)(v110 != 0)) + 0x58);
          if ( *(_QWORD *)(v111 + 8) != ((v110 + 8) & -(__int64)(v110 != 0)) + 88 )
LABEL_5:
            __fastfail(3u);
          *(_QWORD *)&v189 = *(_QWORD *)(((v110 + 8) & -(__int64)(v110 != 0)) + 0x58);
          *((_QWORD *)&v189 + 1) = ((v110 + 8) & -(__int64)(v110 != 0)) + 88;
          *(_QWORD *)(v111 + 8) = &v189;
          *(_QWORD *)(((v110 + 8) & -(__int64)(v110 != 0)) + 0x58) = &v189;
        }
        else
        {
          *((_QWORD *)&v189 + 1) = &v189;
          *(_QWORD *)&v189 = &v189;
        }
        v112 = v108;
        v201 = v188;
        v113 = (unsigned __int16)v108;
        v114 = 0;
        v196 = 0;
        v115 = v113 | (v112 >> 8) & 0xFF0000;
        v200 = 0;
        v182[0] = v115;
        v183 = 0;
        v116 = (__int64 *)PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion(&v183);
        if ( !(unsigned int)IsThreadCrossSessionAttached() && v116 )
          v114 = *v116;
        v117 = (v114 + 8) & -(__int64)(v114 != 0);
        if ( v117 )
          v179 = *(_QWORD *)(v117 + 64);
        else
          v179 = 0;
        v118 = 1;
        *(_DWORD *)&v199[8] = 1;
        v119 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v188 + 8) + 40LL))(*(_QWORD *)(v188 + 8), v115);
        *(_QWORD *)v199 = v119;
        v120 = (unsigned int *)v119;
        if ( v119 )
        {
          _m_prefetchw((const void *)(v119 + 8));
          v121 = *(_DWORD *)(v119 + 8) & 0xFFFFFFFE;
          if ( v121 == ((unsigned int)v183 & 0xFFFFFFFC)
            || !v121
            || v179 && v121 == (unsigned int)UMPDGetThreadClientPID(v117) )
          {
            if ( (*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v188 + 8) + 96LL))(
                               *(_QWORD *)(v188 + 8),
                               *v120)
                           + 14)
                & 0x20) == 0 )
              goto LABEL_123;
            if ( v117 )
            {
              v174 = *(ThreadRestrictNewHandlesRegion **)(v117 + 328);
              if ( v174 )
              {
                if ( *((_BYTE *)v174 + 80) && ThreadRestrictNewHandlesRegion::InRegion(v174, v182[0]) )
                  goto LABEL_123;
              }
            }
            LOBYTE(v200) = 1;
          }
          HANDLELOCK::vUnlock((HANDLELOCK *)v199);
          v120 = *(unsigned int **)v199;
          v118 = *(_DWORD *)&v199[8];
        }
        else
        {
          v118 = 0;
          KeLeaveCriticalRegion();
        }
LABEL_123:
        if ( v118 )
        {
          v122 = v201;
          if ( *((_BYTE *)v120 + 14) == 5 && *((_WORD *)v120 + 6) == WORD1(v180) )
          {
            v123 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v201 + 8) + 96LL))(
                     *(_QWORD *)(v201 + 8),
                     *v120);
            v124 = v188;
            v196 = v123;
            ++*(_DWORD *)(v123 + 8);
            TrackObjectReferenceIncrement(v124, 3, *(_QWORD *)(v123 + 712));
          }
          v125 = *(__int64 **)(v122 + 8);
          v126 = *v125;
          v127 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v125 + 96))(v125, *v120);
          (*(void (__fastcall **)(__int64 *, __int64))(v126 + 48))(v125, v127);
          KeLeaveCriticalRegion();
        }
        v128 = v188;
        v191 = v196;
        v129 = SURFACE::bDeleteSurface(v196, v188, 0, 0);
        v131 = v191;
        v146 = v129 == 0;
        v132 = *(_QWORD *)(v128 + 3088);
        if ( !v146 )
          v131 = 0;
        v191 = v131;
        v51 = *(_DWORD **)(v132 + 168);
        if ( v131 )
        {
          v133 = W32GetSessionState(v130);
          HmgDecrementShareReferenceCount(*(_QWORD *)(v133 + 88), v191);
        }
        PopThreadGuardedObject(&v189);
        goto LABEL_133;
      }
      v51 = (_DWORD *)v179;
LABEL_133:
      v134 = v198;
      if ( (_DWORD)v198 )
      {
        v160 = v197;
        v161 = (DC *)*v195;
        v162 = *(_QWORD *)(*v195 + 976);
        v50 = *(_DWORD *)(v162 + 108) & 7;
        *(_DWORD *)(v162 + 108) = v197;
        if ( (_DWORD)v50 != v134 )
        {
          v163 = *((_QWORD *)v161 + 122);
          v179 = *(_QWORD *)(v163 + 316);
          v180 = *(SURFACE **)(v163 + 324);
          if ( (v160 & 1) != 0 )
            *(_DWORD *)(v163 + 104) = 8;
          v164 = *((_QWORD *)v161 + 122);
          LODWORD(v179) = -(int)v179;
          LODWORD(v180) = -(int)v180;
          *(_QWORD *)(v164 + 316) = v179;
          *(_QWORD *)(*((_QWORD *)v161 + 122) + 324LL) = v180;
          DC::MirrorWindowOrg(v161);
          v166 = *(_QWORD *)(v165 + 976);
          if ( (*(_BYTE *)(v166 + 272) & 6) != 6 )
          {
            *(_DWORD *)(v166 + 272) ^= 2u;
            v166 = *(_QWORD *)(v165 + 976);
          }
          v167 = *(_DWORD *)(v165 + 248);
          v50 = v167;
          v168 = v167 | 4;
          v169 = v167 & 0xFFFFFFFB;
          if ( (v50 & 4) == 0 )
            v169 = v168;
          *(_DWORD *)(v165 + 248) = v169;
          *(_DWORD *)(v166 + 340) |= 0x4090u;
        }
      }
      *(_QWORD *)a1 = v51;
      *(_BYTE *)(a1 + 8) = 0;
      if ( v36 )
      {
        v135 = W32GetSessionState(v50);
        GreReleaseSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(
          *(_QWORD *)(v135 + 88),
          **(_QWORD **)(v135 + 88) + 1512LL);
      }
      SEMOBJEXORSHARED<2>::~SEMOBJEXORSHARED<2>(&v184);
      v139 = v181;
      if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
        McTemplateK0pz_EtwWriteTransfer(
          v137,
          (unsigned int)LockRelease,
          v138,
          (_DWORD)v181,
          (__int64)L"DynamicModeChange");
      CurrentThread = KeGetCurrentThread();
      v141 = 0;
      if ( !(unsigned __int8)KeIsAttachedProcess(v137, v136)
        || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(),
            CurrentThreadProcess = PsGetCurrentThreadProcess(),
            CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
      {
        ThreadWin32Thread = (__int64 *)PsGetThreadWin32Thread(CurrentThread);
        if ( ThreadWin32Thread )
          v141 = *ThreadWin32Thread;
      }
      v143 = v141 + 8;
      v144 = -v141;
      if ( (v143 & -(__int64)(v144 != 0)) != 0 )
      {
        v146 = (*(_BYTE *)((v143 & -(__int64)(v144 != 0)) + 9))-- == 1;
        if ( v146 )
          *(_QWORD *)(v143 & -(__int64)(v144 != 0)) &= ~2uLL;
      }
      GreReleaseSemaphoreSharedInternal(v139);
      goto LABEL_144;
    }
    if ( (*(_DWORD *)(v48 + 144) & 0x10) != 0 && (int)IsvMirrorIncludeNotifySupported() >= 0 )
      vMirrorIncludeNotifyWrap(v53, v48, 0);
    v59 = W32GetSessionState(v58);
    *(_QWORD *)&v189 = 0;
    DWORD2(v189) = 0;
    WORD6(v189) = 0;
    v60 = *(_QWORD *)(v59 + 88);
    v61 = (unsigned __int16)*(_DWORD *)v48 | (*(_DWORD *)v48 >> 8) & 0xFF0000u;
    *(_QWORD *)&v190 = v60;
    HANDLELOCK::vLockHandle(&v189, v61, 1);
    if ( !DWORD2(v189) )
    {
      HmgPentryFromPobj(v60, v48);
LABEL_65:
      v146 = (*(_DWORD *)(v48 + 200))-- == 1;
      if ( v146 )
      {
        *(_QWORD *)(v48 + 192) = 0;
        if ( v180 )
          v180 = *(SURFACE **)v48;
        if ( (*(_DWORD *)(v48 + 144) & 0x8000000) != 0 )
        {
          v196 = *(_QWORD *)(v48 + 160);
          *(_QWORD *)(v48 + 160) = 0;
          XEPALOBJ::vUnrefPalette((XEPALOBJ *)&v196);
        }
        *(_DWORD *)(v48 + 144) &= ~0x8000000u;
      }
      goto LABEL_71;
    }
    v62 = (unsigned int *)v189;
    switch ( *(_BYTE *)(v189 + 14) )
    {
      case 4:
        v63 = *(_QWORD *)(v48 + 112);
        v64 = 2;
        break;
      case 5:
        v63 = *(_QWORD *)(v48 + 712);
        v64 = 3;
        break;
      case 0x10:
        v63 = *(_QWORD *)(v48 + 136);
        v64 = 0;
        break;
      default:
        goto LABEL_64;
    }
    TrackObjectReferenceDecrement(v60, v64, v63);
LABEL_64:
    --*(_DWORD *)(v48 + 8);
    v65 = *(__int64 **)(v190 + 8);
    v66 = *v65;
    v67 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v65 + 96))(v65, *v62);
    (*(void (__fastcall **)(__int64 *, __int64))(v66 + 48))(v65, v67);
    KeLeaveCriticalRegion();
    v53 = (DC **)v195;
    goto LABEL_65;
  }
  *(_QWORD *)a1 = 0;
  *(_BYTE *)(a1 + 8) = 5;
LABEL_150:
  GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal, v181);
LABEL_144:
  v146 = v194 == 0;
LABEL_145:
  if ( !v146 )
  {
    v147 = W32GetSessionState(v145);
    HmgDecrementShareReferenceCount(*(_QWORD *)(v147 + 88), v194);
  }
  PopThreadGuardedObject(&v192);
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
