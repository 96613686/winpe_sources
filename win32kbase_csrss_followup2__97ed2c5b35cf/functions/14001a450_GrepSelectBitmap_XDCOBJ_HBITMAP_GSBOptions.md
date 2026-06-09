# GrepSelectBitmap(XDCOBJ &,HBITMAP__ *,GSBOptions)

- ea: `0x14001a450`
- end: `0x14001b8fd`
- name: `?GrepSelectBitmap@@YA?AVGSBResult@@AEAVXDCOBJ@@PEAUHBITMAP__@@W4GSBOptions@@@Z`
- size: `5293`
- prototype: ``
- caller_count: `3`
- callee_count: `44`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000f0c0`
- `0x14001f670`
- `0x140045bc0`

## callees

- `0x140010070`
- `0x1400108cc`
- `0x140011c20`
- `0x140019d00`
- `0x140019d88`
- `0x140019e70`
- `0x14001a450`
- `0x14001c470`
- `0x14001c560`
- `0x14001c8b4`
- `0x14001d160`
- `0x140024170`
- `0x1400245b0`
- `0x140024cc0`
- `0x140024ef0`
- `0x140024f24`
- `0x140024f60`
- `0x140024f80`
- `0x140025470`
- `0x140025570`
- `0x140025990`
- `0x140025a30`
- `0x140025b50`
- `0x140025b90`
- `0x140026270`
- `0x14002afa0`
- `0x140031bf4`
- `0x14003e820`
- `0x14003f37c`
- `0x140041ac0`
- `0x140043e04`
- `0x1400f0fb8`
- `0x140100788`
- `0x14010d06c`
- `0x140110520`
- `0x140116914`
- `0x1401195dc`
- `0x14012f8b8`
- `0x1401527c8`
- `0x14016459c`
- `0x140190760`
- `0x1401aee40`
- `0x140238160`
- `0x140238240`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14001acda`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001acda`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001a6f4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001aa74`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001aca6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001afc9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b48f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b5b5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001a6f4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001aa74`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001aca6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001afc9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b48f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b5b5`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14001acef`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14001acef`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x14001b0af`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x14001b0af`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001b762`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001b762`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14001b753`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14001b753`
- `ntoskrnl!KeIsAttachedProcess` at `0x14001b098`
- `ntoskrnl!KeIsAttachedProcess` at `0x14001b098`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x14001a5c6`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x14001ae9a`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x14001a5c6`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x14001ae9a`
- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x14001b1d4`
- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x14001b79a`
- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x14001b1d4`
- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x14001b79a`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001a49c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001ae01`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001a49c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001ae01`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14001aac0`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14001aae5`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14001aac0`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14001aae5`
- `WIN32K!W32GetSessionState` at `0x14001a515`
- `WIN32K!W32GetSessionState` at `0x14001a582`
- `WIN32K!W32GetSessionState` at `0x14001a746`
- `WIN32K!W32GetSessionState` at `0x14001a82d`
- `WIN32K!W32GetSessionState` at `0x14001a876`
- `WIN32K!W32GetSessionState` at `0x14001a928`
- `WIN32K!W32GetSessionState` at `0x14001a9a5`
- `WIN32K!W32GetSessionState` at `0x14001a9d1`
- `WIN32K!W32GetSessionState` at `0x14001ab6a`
- `WIN32K!W32GetSessionState` at `0x14001ac03`
- `WIN32K!W32GetSessionState` at `0x14001acb8`
- `WIN32K!W32GetSessionState` at `0x14001b017`
- `WIN32K!W32GetSessionState` at `0x14001b051`
- `WIN32K!W32GetSessionState` at `0x14001b0ea`
- `WIN32K!W32GetSessionState` at `0x14001b2d5`
- `WIN32K!W32GetSessionState` at `0x14001b388`
- `WIN32K!W32GetSessionState` at `0x14001b7ba`
- `WIN32K!W32GetSessionState` at `0x14001a515`
- `WIN32K!W32GetSessionState` at `0x14001a582`
- `WIN32K!W32GetSessionState` at `0x14001a746`
- `WIN32K!W32GetSessionState` at `0x14001a82d`
- `WIN32K!W32GetSessionState` at `0x14001a876`
- `WIN32K!W32GetSessionState` at `0x14001a928`
- `WIN32K!W32GetSessionState` at `0x14001a9a5`
- `WIN32K!W32GetSessionState` at `0x14001a9d1`
- `WIN32K!W32GetSessionState` at `0x14001ab6a`
- `WIN32K!W32GetSessionState` at `0x14001ac03`
- `WIN32K!W32GetSessionState` at `0x14001acb8`
- `WIN32K!W32GetSessionState` at `0x14001b017`
- `WIN32K!W32GetSessionState` at `0x14001b051`
- `WIN32K!W32GetSessionState` at `0x14001b0ea`
- `WIN32K!W32GetSessionState` at `0x14001b2d5`
- `WIN32K!W32GetSessionState` at `0x14001b388`
- `WIN32K!W32GetSessionState` at `0x14001b7ba`

## pseudocode

```c
__int64 __fastcall GrepSelectBitmap(__int64 a1, __int64 *a2, _DWORD *a3, char a4)
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
  __int64 v57; // rcx
  __int64 v58; // rax
  __int64 v59; // rbx
  __int64 v60; // rdx
  unsigned int *v61; // r15
  __int64 v62; // r8
  __int64 v63; // rdx
  __int64 *v64; // rdi
  __int64 v65; // rbx
  __int64 v66; // rax
  int (*v67)(void); // rax
  void (__fastcall *v68)(DC **, SURFACE *, __int64); // rax
  int v69; // eax
  BOOL v70; // r8d
  int v71; // eax
  int v72; // ecx
  unsigned int v73; // eax
  __int64 v74; // rcx
  int v75; // edx
  int v76; // edx
  __int64 v77; // rcx
  __int64 v78; // rax
  __int64 v79; // rax
  SURFACE *v80; // rbx
  __int64 v81; // rdi
  __int64 v82; // rdx
  unsigned int *v83; // rsi
  __int64 v84; // r8
  __int64 v85; // rdx
  __int64 *v86; // rdi
  __int64 v87; // rbx
  __int64 v88; // rax
  __int64 v89; // rcx
  __int64 v90; // rax
  DC *v91; // r15
  __int64 v92; // rdi
  _DWORD *v93; // r14
  __int64 v94; // rsi
  int v95; // eax
  int v96; // r9d
  int v97; // r10d
  int v98; // edx
  int v99; // r8d
  _DWORD *v100; // rcx
  struct _GRETHREAD *v101; // rax
  unsigned int v102; // edi
  __int64 *v103; // rax
  __int64 v104; // rcx
  __int64 v105; // rdx
  unsigned int v106; // esi
  int v107; // eax
  __int64 v108; // rdi
  unsigned int v109; // esi
  __int64 *v110; // r14
  __int64 v111; // rdi
  int v112; // r15d
  __int64 v113; // rax
  unsigned int *v114; // r14
  unsigned int v115; // esi
  __int64 v116; // rsi
  __int64 v117; // rax
  __int64 v118; // rcx
  __int64 *v119; // rsi
  __int64 v120; // rdi
  __int64 v121; // rax
  __int64 v122; // rdi
  int v123; // eax
  __int64 v124; // rcx
  __int64 v125; // rdx
  __int64 v126; // rax
  __int64 v127; // rax
  int v128; // edx
  __int64 v129; // rax
  int v130; // ecx
  int v131; // r8d
  HSEMAPHORE v132; // r14
  struct _KTHREAD *CurrentThread; // rsi
  __int64 v134; // rdi
  __int64 *ThreadWin32Thread; // rax
  __int64 v136; // rax
  __int64 v137; // rdi
  __int64 v138; // rcx
  bool v139; // zf
  __int64 v140; // rax
  char v142; // al
  int v143; // eax
  __int64 v144; // rax
  __int64 v145; // rax
  __int64 v146; // rcx
  __int64 v147; // rax
  __int64 v148; // r10
  __int64 v149; // r11
  unsigned int v150; // edx
  int v151; // eax
  unsigned int v152; // edx
  char v153; // r8
  DC *v154; // r10
  __int64 v155; // rax
  __int64 v156; // rcx
  __int64 v157; // rcx
  __int64 v158; // r10
  __int64 v159; // r11
  unsigned int v160; // edx
  int v161; // eax
  unsigned int v162; // edx
  int v163; // edx
  unsigned __int64 i; // rcx
  int v165; // eax
  ThreadRestrictNewHandlesRegion *v166; // rcx
  ThreadRestrictNewHandlesRegion *v167; // rcx
  int CurrentWin32kSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  __int64 v170; // rax
  __int64 v172; // [rsp+38h] [rbp-C8h] BYREF
  SURFACE *v173; // [rsp+40h] [rbp-C0h]
  HSEMAPHORE v174; // [rsp+48h] [rbp-B8h]
  unsigned int v175[2]; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD *v176; // [rsp+58h] [rbp-A8h] BYREF
  HSEMAPHORE v177; // [rsp+60h] [rbp-A0h] BYREF
  int v178; // [rsp+68h] [rbp-98h]
  __int16 v179; // [rsp+6Ch] [rbp-94h]
  __int64 v180; // [rsp+70h] [rbp-90h]
  __int64 v181; // [rsp+78h] [rbp-88h]
  __int128 v182; // [rsp+80h] [rbp-80h] BYREF
  __int128 v183; // [rsp+90h] [rbp-70h]
  __int64 v184; // [rsp+A0h] [rbp-60h]
  __int128 v185; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v186; // [rsp+B8h] [rbp-48h]
  SURFACE *v187; // [rsp+C8h] [rbp-38h]
  __int64 *v188; // [rsp+D0h] [rbp-30h]
  __int64 v189; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v190; // [rsp+E0h] [rbp-20h]
  __int64 v191; // [rsp+E8h] [rbp-18h]
  _BYTE v192[12]; // [rsp+F0h] [rbp-10h] BYREF
  __int16 v193; // [rsp+FCh] [rbp-4h]
  __int64 v194; // [rsp+100h] [rbp+0h]

  v185 = 0;
  v4 = (unsigned int)a3;
  v176 = a3;
  v186 = 0;
  v188 = a2;
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread();
  if ( CurrentThreadWin32Thread )
    v8 = *CurrentThreadWin32Thread;
  else
    v8 = 0;
  v9 = (v8 + 8) & -(__int64)(v8 != 0);
  *(_QWORD *)&v186 = &v185;
  *((_QWORD *)&v186 + 1) = UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
  if ( v9 )
  {
    v10 = *(_QWORD *)(((v8 + 8) & -(__int64)(v8 != 0)) + 0x58);
    if ( *(_QWORD *)(v10 + 8) != v9 + 88 )
      goto LABEL_5;
    *(_QWORD *)&v185 = *(_QWORD *)(v9 + 88);
    *((_QWORD *)&v185 + 1) = v9 + 88;
    *(_QWORD *)(v10 + 8) = &v185;
    *(_QWORD *)(v9 + 88) = &v185;
  }
  else
  {
    *((_QWORD *)&v185 + 1) = &v185;
    *(_QWORD *)&v185 = &v185;
  }
  v181 = a2[2];
  v187 = 0;
  v174 = (HSEMAPHORE)(**(_QWORD **)(((__int64 (*)(void))W32GetSessionState)() + 88) + 624LL);
  EngAcquireSemaphoreShared(v174);
  v11 = GreGetCurrentThreadCrossSessionCheck();
  v12 = v11;
  v13 = 1;
  if ( v11 )
  {
    v14 = *(_QWORD *)v11;
    if ( (*(_QWORD *)v11 & 0xFFFFFFDFFFFFFFFEuLL) != 0 && (*(_QWORD *)v11 & 2) == 0 )
    {
      v163 = 38;
      for ( i = 0; i < 0x40; ++i )
      {
        v165 = i;
        if ( ((1LL << i) & 0xFFFFFFDFFFFFFFFFuLL & v14) == 0 )
          v165 = v163;
        v163 = v165;
      }
      if ( v165 > 1 && v165 != 38 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(i, (unsigned int)v165);
    }
    v15 = *((_BYTE *)v12 + 9);
    *((_BYTE *)v12 + 9) = v15 + 1;
    if ( !v15 )
      *(_QWORD *)v12 |= 2uLL;
  }
  v173 = 0;
  v179 = 0;
  v16 = 0;
  v190 = *(_QWORD *)(((__int64 (*)(void))W32GetSessionState)() + 88);
  v17 = 0;
  v180 = v190;
  v18 = (unsigned __int16)v4 | (v4 >> 8) & 0xFF0000;
  v172 = 0;
  CurrentThreadWin32ThreadAndEnterCriticalRegion = (__int64 *)PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion(&v172);
  if ( !(unsigned int)IsThreadCrossSessionAttached() && CurrentThreadWin32ThreadAndEnterCriticalRegion )
    v17 = *CurrentThreadWin32ThreadAndEnterCriticalRegion;
  v20 = (v17 + 8) & -(__int64)(v17 != 0);
  if ( v20 )
    v191 = *(_QWORD *)(v20 + 64);
  else
    v191 = 0;
  v21 = 1;
  v178 = 1;
  v22 = (HSEMAPHORE)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v190 + 8) + 40LL))(
                      *(_QWORD *)(v190 + 8),
                      v18);
  v177 = v22;
  v23 = v22;
  if ( v22 )
  {
    _m_prefetchw(v22 + 2);
    v24 = (_DWORD)v22[2] & 0xFFFFFFFE;
    if ( v24 != (v172 & 0xFFFFFFFC) && v24 && (!v191 || v24 != (unsigned int)UMPDGetThreadClientPID(v20)) )
    {
      HANDLELOCK::vUnlock((HANDLELOCK *)&v177);
      v21 = v178;
      v23 = v177;
      goto LABEL_19;
    }
    if ( (*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v190 + 8) + 96LL))(
                       *(_QWORD *)(v190 + 8),
                       *(_DWORD *)v23)
                   + 14)
        & 0x20) == 0 )
    {
LABEL_19:
      v16 = v173;
      goto LABEL_20;
    }
    v16 = 0;
    if ( !v20
      || (v166 = *(ThreadRestrictNewHandlesRegion **)(v20 + 328)) == 0
      || !*((_BYTE *)v166 + 80)
      || !ThreadRestrictNewHandlesRegion::InRegion(v166, v18) )
    {
      LOBYTE(v179) = 1;
      HANDLELOCK::vUnlock((HANDLELOCK *)&v177);
      v21 = v178;
      v23 = v177;
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
    v25 = v180;
    if ( *((_BYTE *)v23 + 14) == 5 && *((_WORD *)v23 + 6) == WORD1(v176) )
    {
      v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v180 + 8) + 96LL))(
              *(_QWORD *)(v180 + 8),
              *(_DWORD *)v23);
      v27 = v190;
      v16 = (SURFACE *)v26;
      ++*(_DWORD *)(v26 + 8);
      TrackObjectReferenceIncrement(v27, 3, *(_QWORD *)(v26 + 728));
    }
    v28 = *(__int64 **)(v25 + 8);
    v29 = *v28;
    v30 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v28 + 96))(v28, *(_DWORD *)v23);
    (*(void (__fastcall **)(__int64 *, __int64))(v29 + 48))(v28, v30);
    KeLeaveCriticalRegion();
  }
  v187 = v16;
  if ( v16 )
  {
    LOBYTE(v178) = (a4 & 2) != 0;
    v177 = (HSEMAPHORE)(*(_QWORD *)v181 + 1144LL);
    if ( (a4 & 2) != 0 )
      EngAcquireSemaphoreShared(v177);
    else
      GreAcquireSemaphoreInternal(v177);
    GrepAcquireLockValidate<2>();
    v32 = *(__int64 **)(((__int64 (*)(void))W32GetSessionState)() + 88);
    v34 = *v32;
    if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
      McTemplateK0pqz_EtwWriteTransfer((_DWORD)v32, v31, v33, v34 + 1512, 0, (__int64)L"Hmgr");
    GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(v32, v34 + 1512);
    v35 = v188;
    v36 = 1;
    v37 = v187;
    v175[0] = 1;
    v38 = *v188;
    *(_QWORD *)v192 = *(_QWORD *)(*v188 + 48);
    if ( *(_QWORD *)v38 )
    {
      v39 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v188[2] + 8) + 8LL))(*(_QWORD *)(v188[2] + 8));
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
    if ( *((_DWORD *)v37 + 54) && !(unsigned int)SURFACE::bStockSurface(v37) && *((_QWORD *)v37 + 26) != *(_QWORD *)v40 )
    {
      *(_BYTE *)(a1 + 8) = 7;
LABEL_245:
      *(_QWORD *)a1 = 0;
      v170 = ((__int64 (*)(void))W32GetSessionState)();
      GreReleaseSemaphoreExclusive<20,>(*(_QWORD *)(v170 + 88));
      SEMOBJEXORSHARED<2>::~SEMOBJEXORSHARED<2>(&v177);
      goto LABEL_150;
    }
    v41 = *(_QWORD *)(v40 + 48);
    if ( (*((_WORD *)v37 + 50) || *((_QWORD *)v37 + 3)) && *((_QWORD *)v37 + 6) != v41 )
    {
LABEL_223:
      *(_BYTE *)(a1 + 8) = v13;
      goto LABEL_245;
    }
    v42 = *((_QWORD *)v37 + 22);
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
    v189 = *((_QWORD *)v37 + 6);
    v44 = *(__int64 **)(W32GetSessionState(0) + 88);
    if ( v37 != (SURFACE *)v44[547] && v41 && *((_QWORD *)v37 + 5) )
    {
      v44 = (__int64 *)(*(_DWORD *)(v41 + 40) & 1);
      if ( (*(_DWORD *)(v41 + 40) & 1) != 0 && (*((_DWORD *)v37 + 40) & 0x40000) != 0 )
      {
        *(_DWORD *)v192 = 33279186;
        *(_QWORD *)&v192[4] = 1;
        RtlLogUnexpectedCodepath(v192, 0);
        v142 = 3;
        goto LABEL_161;
      }
      if ( v189 && (_DWORD)v44 != (*(_DWORD *)(v189 + 40) & 1) )
      {
        *(_DWORD *)v192 = 33279186;
        *(_QWORD *)&v192[4] = 2;
        RtlLogUnexpectedCodepath(v192, 0);
        v142 = 4;
LABEL_161:
        *(_QWORD *)a1 = 0;
        *(_BYTE *)(a1 + 8) = v142;
        MLOCKOBJ::~MLOCKOBJ((MLOCKOBJ *)v175);
        SEMOBJEXORSHARED<2>::~SEMOBJEXORSHARED<2>(&v177);
        GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal, v174);
        SURFREF::~SURFREF((SURFREF *)&v185);
        return a1;
      }
    }
    v45 = v43 & 0xFFFFFFFE;
    if ( v45 && (*((_DWORD *)v37 + 40) & 0x800) != 0 )
    {
      *(_BYTE *)(a1 + 8) = 9;
      goto LABEL_173;
    }
    if ( (a4 & 4) == 0 && !v45 )
    {
      *(_BYTE *)(a1 + 8) = 10;
      goto LABEL_173;
    }
    SessionState = W32GetSessionState(v44);
    v44 = v188;
    v47 = (DC *)*v188;
    v48 = *(_QWORD *)(*v188 + 496);
    if ( v48 )
    {
      if ( v188[3] )
        v48 = v188[3];
    }
    else
    {
      v48 = *(_QWORD *)(*(_QWORD *)(SessionState + 88) + 4376LL);
    }
    if ( (!_bittest((const signed __int32 *)(v48 + 160), 0x1Au)
       || !_bittest((const signed __int32 *)v37 + 40, 0x1Au)
       || (*(_DWORD *)(v48 + 164) & 0x200) != 0)
      && (a4 & 1) == 0 )
    {
      *(_BYTE *)(a1 + 8) = 11;
LABEL_173:
      *(_QWORD *)a1 = 0;
      v144 = W32GetSessionState(v44);
      GreReleaseSemaphoreExclusive<20,>(*(_QWORD *)(v144 + 88));
      SEMOBJEXORSHARED<2>::~SEMOBJEXORSHARED<2>(&v177);
      GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal, v174);
      v139 = v187 == 0;
      goto LABEL_145;
    }
    v49 = *((_QWORD *)v47 + 122);
    v173 = 0;
    LODWORD(v190) = *(_DWORD *)(v49 + 108);
    v50 = v190 & 7;
    LODWORD(v191) = v190 & 7;
    if ( (v190 & 7) != 0 )
    {
      *(_DWORD *)(v49 + 108) = 0;
      v146 = *((_QWORD *)v47 + 122);
      *(_QWORD *)v175 = *(_QWORD *)(v146 + 316);
      v147 = *(_QWORD *)(v146 + 324);
      v175[0] = -v175[0];
      HIDWORD(v172) = HIDWORD(v147);
      LODWORD(v172) = -(int)v147;
      *(_QWORD *)(v146 + 316) = *(_QWORD *)v175;
      *(_QWORD *)(*((_QWORD *)v47 + 122) + 324LL) = v172;
      DC::MirrorWindowOrg(v47);
      v149 = *(_QWORD *)(v148 + 976);
      if ( (*(_BYTE *)(v149 + 272) & 6) != 6 )
      {
        *(_DWORD *)(v149 + 272) ^= 2u;
        v149 = *(_QWORD *)(v148 + 976);
      }
      v150 = *(_DWORD *)(v148 + 248);
      v50 = v150;
      v151 = v150 | 4;
      v152 = v150 & 0xFFFFFFFB;
      if ( (v50 & 4) == 0 )
        v152 = v151;
      *(_DWORD *)(v148 + 248) = v152;
      *(_DWORD *)(v149 + 340) |= 0x4090u;
    }
    if ( *((_QWORD *)v37 + 22) != v42 )
    {
      *((_DWORD *)v37 + 40) |= 0x8000000u;
      *((_QWORD *)v37 + 22) = v42;
      if ( v42 )
      {
        v145 = W32GetSessionState(v50);
        HmgIncrementShareReferenceCount(*(_QWORD *)(v145 + 88), v42);
      }
    }
    if ( (*(_DWORD *)(v48 + 160) & 0x1000000) != 0 )
      v173 = *(SURFACE **)v48;
    v51 = *(_DWORD **)(v48 + 32);
    v172 = (__int64)v51;
    if ( v176 == v51 )
      goto LABEL_133;
    v52 = W32GetSessionState(v50);
    v53 = (DC **)v188;
    v54 = *v188;
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
      if ( (*((_DWORD *)v37 + 41) & 0x800) != 0 )
      {
        DC::vSetDpiScaling(v54, *(_QWORD *)((char *)v37 + 708));
      }
      else
      {
        v143 = *(_DWORD *)(v54 + 520);
        if ( (v143 & 1) != 0 )
        {
          *(_DWORD *)(v54 + 36) |= 0x10u;
          *(_QWORD *)(v54 + 524) = 0;
          *(_QWORD *)(v54 + 532) = 0;
          *(_DWORD *)(v54 + 520) = v143 & 0xFFFFFFF8 | 4;
          DC::vUpdateCachedDPIScaleValue((DC *)v54);
        }
      }
      if ( (*(_DWORD *)v37 & 0x800000) != 0 && _bittest16((const signed __int16 *)v37 + 51, 9u)
        || !*((_WORD *)v37 + 50) && *((_DWORD *)v37 + 66) )
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
    v57 = *(_QWORD *)(W32GetSessionState(v56) + 88);
    if ( v48 == *(_QWORD *)(v57 + 4376) )
    {
LABEL_71:
      v67 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 24) + 608LL);
      if ( v67 )
      {
        if ( v67() >= 0 )
        {
          v68 = *(void (__fastcall **)(DC **, SURFACE *, __int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 24)
                                                                 + 616LL);
          if ( v68 )
            v68(v53, v37, 1);
        }
      }
      v69 = *((_DWORD *)v37 + 40);
      v70 = (v69 & 0x4000) != 0 || (v69 & 0x800010) != 0 && (*(_DWORD *)(*(_QWORD *)v192 + 40LL) & 1) != 0;
      v71 = *((_DWORD *)*v53 + 9);
      v72 = v71 | 0x200;
      v73 = v71 & 0xFFFFFDFF;
      if ( !v70 )
        v72 = v73;
      *((_DWORD *)*v53 + 9) = v72;
      v74 = *((unsigned int *)*v53 + 9);
      if ( (v74 & 0x200) != 0 && (*((_DWORD *)v37 + 40) & 0x200) != 0 )
        LODWORD(v74) = v74 | 0x8000;
      else
        LODWORD(v74) = v74 & 0xFFFF7FFF;
      *((_DWORD *)*v53 + 9) = v74;
      if ( v37 != *(SURFACE **)(*(_QWORD *)(W32GetSessionState(v74) + 88) + 4376LL) )
      {
        SURFACE::vInc_cRef(v37);
        if ( (*(_DWORD *)v37 & 0x800000) == 0 || (*((_WORD *)v37 + 51) & 0x200) == 0 )
        {
          *((_QWORD *)v37 + 26) = *(_QWORD *)*v53;
          *((_QWORD *)v37 + 6) = *((_QWORD *)*v53 + 6);
        }
      }
      if ( *((_WORD *)v37 + 50) || (v75 = 1, !*((_QWORD *)v37 + 30)) )
        v75 = 0;
      **((_DWORD **)*v53 + 122) = v75 | **((_DWORD **)*v53 + 122) & 0xFFFFFFFE;
      if ( *((_WORD *)v37 + 50) || (v76 = 1, !*((_QWORD *)v37 + 30)) )
        v76 = 0;
      v77 = *((_QWORD *)*v53 + 122);
      if ( v76 )
        v78 = *((_QWORD *)v37 + 31);
      else
        v78 = 0;
      *(_QWORD *)(v77 + 24) = v78;
      v79 = W32GetSessionState(v77);
      v80 = v187;
      *(_QWORD *)&v182 = 0;
      v81 = *(_QWORD *)(v79 + 88);
      v82 = (unsigned __int16)*(_DWORD *)v187 | (*(_DWORD *)v187 >> 8) & 0xFF0000u;
      DWORD2(v182) = 0;
      WORD6(v182) = 0;
      *(_QWORD *)&v183 = v81;
      HANDLELOCK::vLockHandle(&v182, v82, 1);
      if ( !DWORD2(v182) )
      {
        HmgPentryFromPobj(v81, v80);
        goto LABEL_100;
      }
      v83 = (unsigned int *)v182;
      switch ( *(_BYTE *)(v182 + 14) )
      {
        case 4:
          v84 = *((_QWORD *)v80 + 14);
          v85 = 2;
          break;
        case 5:
          v84 = *((_QWORD *)v80 + 91);
          v85 = 3;
          break;
        case 0x10:
          v84 = *((_QWORD *)v80 + 17);
          v85 = 0;
          break;
        default:
          goto LABEL_99;
      }
      TrackObjectReferenceDecrement(v81, v85, v84);
LABEL_99:
      --*((_DWORD *)v80 + 2);
      v86 = *(__int64 **)(v183 + 8);
      v87 = *v86;
      v88 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v86 + 96))(v86, *v83);
      (*(void (__fastcall **)(__int64 *, __int64))(v87 + 48))(v86, v88);
      KeLeaveCriticalRegion();
LABEL_100:
      v187 = 0;
      v90 = W32GetSessionState(v89);
      GreReleaseSemaphoreExclusive<20,>(*(_QWORD *)(v90 + 88));
      v36 = 0;
      DC::bSetDefaultRegion(*v53);
      v91 = *v53;
      KeEnterCriticalRegion();
      ExAcquirePushLockSharedEx((char *)v91 + 1112, 0);
      GrepAcquireLockValidate<37>();
      GrepAcquireLockValidate<38>();
      v92 = *v188;
      v93 = *(_DWORD **)(*v188 + 1136);
      if ( *(_QWORD *)*v188 )
      {
        v94 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v181 + 8) + 8LL))(*(_QWORD *)(v181 + 8), *v188);
      }
      else
      {
        v94 = v92 + 2152;
        *(_OWORD *)(v92 + 2152) = 0;
        *(_QWORD *)(v92 + 2168) = 0;
        *(_DWORD *)(v92 + 2160) = -2147483630;
        *(_QWORD *)(v92 + 2168) = 0;
      }
      if ( (*(_BYTE *)(v94 + 15) & 4) != 0 )
      {
        if ( !v93
          || (v176 = v93,
              *(_DWORD *)(*(_QWORD *)(v92 + 976) + 116LL) = RGNOBJ::iComplexity((RGNOBJ *)&v176),
              (unsigned int)RGNOBJ::iComplexity((RGNOBJ *)&v176) == 1) )
        {
          *(_OWORD *)(*(_QWORD *)(v92 + 976) + 120LL) = xmmword_140250EB8;
        }
        else
        {
          v95 = *(_DWORD *)(v92 + 1036);
          v96 = *(_DWORD *)(v92 + 1032);
          v97 = v93[14] - v95;
          v98 = v93[16] - v95;
          v99 = v93[15] - v96;
          v100 = *(_DWORD **)(v92 + 976);
          v100[30] = v93[13] - v96;
          v100[31] = v97;
          v100[32] = v99;
          v100[33] = v98;
        }
        *(_BYTE *)(v94 + 15) &= ~4u;
      }
      v101 = GreGetCurrentThreadCrossSessionCheck();
      if ( v101 )
        *(_QWORD *)v101 &= ~0x4000000000uLL;
      GrePushLock::ReleaseLock((DC *)((char *)v91 + 1112));
      v102 = (unsigned int)v173;
      if ( v173 )
      {
        v182 = 0;
        v183 = 0;
        v103 = (__int64 *)PsGetCurrentThreadWin32Thread();
        if ( v103 )
          v104 = *v103;
        else
          v104 = 0;
        *(_QWORD *)&v183 = &v182;
        *((_QWORD *)&v183 + 1) = UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
        if ( ((v104 + 8) & -(__int64)(v104 != 0)) != 0 )
        {
          v105 = *(_QWORD *)(((v104 + 8) & -(__int64)(v104 != 0)) + 0x58);
          if ( *(_QWORD *)(v105 + 8) != ((v104 + 8) & -(__int64)(v104 != 0)) + 88 )
LABEL_5:
            __fastfail(3u);
          *(_QWORD *)&v182 = *(_QWORD *)(((v104 + 8) & -(__int64)(v104 != 0)) + 0x58);
          *((_QWORD *)&v182 + 1) = ((v104 + 8) & -(__int64)(v104 != 0)) + 88;
          *(_QWORD *)(v105 + 8) = &v182;
          *(_QWORD *)(((v104 + 8) & -(__int64)(v104 != 0)) + 0x58) = &v182;
        }
        else
        {
          *((_QWORD *)&v182 + 1) = &v182;
          *(_QWORD *)&v182 = &v182;
        }
        v106 = v102;
        v194 = v181;
        v107 = (unsigned __int16)v102;
        v108 = 0;
        v189 = 0;
        v109 = v107 | (v106 >> 8) & 0xFF0000;
        v193 = 0;
        v175[0] = v109;
        v176 = 0;
        v110 = (__int64 *)PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion(&v176);
        if ( !(unsigned int)IsThreadCrossSessionAttached() && v110 )
          v108 = *v110;
        v111 = (v108 + 8) & -(__int64)(v108 != 0);
        if ( v111 )
          v172 = *(_QWORD *)(v111 + 64);
        else
          v172 = 0;
        v112 = 1;
        *(_DWORD *)&v192[8] = 1;
        v113 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v181 + 8) + 40LL))(*(_QWORD *)(v181 + 8), v109);
        *(_QWORD *)v192 = v113;
        v114 = (unsigned int *)v113;
        if ( v113 )
        {
          _m_prefetchw((const void *)(v113 + 8));
          v115 = *(_DWORD *)(v113 + 8) & 0xFFFFFFFE;
          if ( v115 == ((unsigned int)v176 & 0xFFFFFFFC)
            || !v115
            || v172 && v115 == (unsigned int)UMPDGetThreadClientPID(v111) )
          {
            if ( (*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v181 + 8) + 96LL))(
                               *(_QWORD *)(v181 + 8),
                               *v114)
                           + 14)
                & 0x20) == 0 )
              goto LABEL_123;
            if ( v111 )
            {
              v167 = *(ThreadRestrictNewHandlesRegion **)(v111 + 328);
              if ( v167 )
              {
                if ( *((_BYTE *)v167 + 80) && ThreadRestrictNewHandlesRegion::InRegion(v167, v175[0]) )
                  goto LABEL_123;
              }
            }
            LOBYTE(v193) = 1;
          }
          HANDLELOCK::vUnlock((HANDLELOCK *)v192);
          v114 = *(unsigned int **)v192;
          v112 = *(_DWORD *)&v192[8];
        }
        else
        {
          v112 = 0;
          KeLeaveCriticalRegion();
        }
LABEL_123:
        if ( v112 )
        {
          v116 = v194;
          if ( *((_BYTE *)v114 + 14) == 5 && *((_WORD *)v114 + 6) == WORD1(v173) )
          {
            v117 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v194 + 8) + 96LL))(
                     *(_QWORD *)(v194 + 8),
                     *v114);
            v118 = v181;
            v189 = v117;
            ++*(_DWORD *)(v117 + 8);
            TrackObjectReferenceIncrement(v118, 3, *(_QWORD *)(v117 + 728));
          }
          v119 = *(__int64 **)(v116 + 8);
          v120 = *v119;
          v121 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v119 + 96))(v119, *v114);
          (*(void (__fastcall **)(__int64 *, __int64))(v120 + 48))(v119, v121);
          KeLeaveCriticalRegion();
        }
        v122 = v181;
        v184 = v189;
        v123 = SURFACE::bDeleteSurface(v189, v181, 0, 0);
        v125 = v184;
        v139 = v123 == 0;
        v126 = *(_QWORD *)(v122 + 3088);
        if ( !v139 )
          v125 = 0;
        v184 = v125;
        v51 = *(_DWORD **)(v126 + 168);
        if ( v125 )
        {
          v127 = W32GetSessionState(v124);
          HmgDecrementShareReferenceCount(*(_QWORD *)(v127 + 88), v184);
        }
        PopThreadGuardedObject(&v182);
        goto LABEL_133;
      }
      v51 = (_DWORD *)v172;
LABEL_133:
      v128 = v191;
      if ( (_DWORD)v191 )
      {
        v153 = v190;
        v154 = (DC *)*v188;
        v155 = *(_QWORD *)(*v188 + 976);
        v50 = *(_DWORD *)(v155 + 108) & 7;
        *(_DWORD *)(v155 + 108) = v190;
        if ( (_DWORD)v50 != v128 )
        {
          v156 = *((_QWORD *)v154 + 122);
          v172 = *(_QWORD *)(v156 + 316);
          v173 = *(SURFACE **)(v156 + 324);
          if ( (v153 & 1) != 0 )
            *(_DWORD *)(v156 + 104) = 8;
          v157 = *((_QWORD *)v154 + 122);
          LODWORD(v172) = -(int)v172;
          LODWORD(v173) = -(int)v173;
          *(_QWORD *)(v157 + 316) = v172;
          *(_QWORD *)(*((_QWORD *)v154 + 122) + 324LL) = v173;
          DC::MirrorWindowOrg(v154);
          v159 = *(_QWORD *)(v158 + 976);
          if ( (*(_BYTE *)(v159 + 272) & 6) != 6 )
          {
            *(_DWORD *)(v159 + 272) ^= 2u;
            v159 = *(_QWORD *)(v158 + 976);
          }
          v160 = *(_DWORD *)(v158 + 248);
          v50 = v160;
          v161 = v160 | 4;
          v162 = v160 & 0xFFFFFFFB;
          if ( (v50 & 4) == 0 )
            v162 = v161;
          *(_DWORD *)(v158 + 248) = v162;
          *(_DWORD *)(v159 + 340) |= 0x4090u;
        }
      }
      *(_QWORD *)a1 = v51;
      *(_BYTE *)(a1 + 8) = 0;
      if ( v36 )
      {
        v129 = W32GetSessionState(v50);
        GreReleaseSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(
          *(_QWORD *)(v129 + 88),
          **(_QWORD **)(v129 + 88) + 1512LL);
      }
      SEMOBJEXORSHARED<2>::~SEMOBJEXORSHARED<2>(&v177);
      v132 = v174;
      if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
        McTemplateK0pz_EtwWriteTransfer(
          v130,
          (unsigned int)LockRelease,
          v131,
          (_DWORD)v174,
          (__int64)L"DynamicModeChange");
      CurrentThread = KeGetCurrentThread();
      v134 = 0;
      if ( !(unsigned __int8)KeIsAttachedProcess()
        || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(),
            CurrentThreadProcess = PsGetCurrentThreadProcess(),
            CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
      {
        ThreadWin32Thread = (__int64 *)PsGetThreadWin32Thread(CurrentThread);
        if ( ThreadWin32Thread )
          v134 = *ThreadWin32Thread;
      }
      v136 = v134 + 8;
      v137 = -v134;
      if ( (v136 & -(__int64)(v137 != 0)) != 0 )
      {
        v139 = (*(_BYTE *)((v136 & -(__int64)(v137 != 0)) + 9))-- == 1;
        if ( v139 )
          *(_QWORD *)(v136 & -(__int64)(v137 != 0)) &= ~2uLL;
      }
      GreReleaseSemaphoreSharedInternal(v132);
      goto LABEL_144;
    }
    if ( (*(_DWORD *)(v48 + 160) & 0x10) != 0 && (int)IsvMirrorIncludeNotifySupported() >= 0 )
      vMirrorIncludeNotifyWrap(v53, v48, 0);
    v58 = W32GetSessionState(v57);
    *(_QWORD *)&v182 = 0;
    DWORD2(v182) = 0;
    WORD6(v182) = 0;
    v59 = *(_QWORD *)(v58 + 88);
    v60 = (unsigned __int16)*(_DWORD *)v48 | (*(_DWORD *)v48 >> 8) & 0xFF0000u;
    *(_QWORD *)&v183 = v59;
    HANDLELOCK::vLockHandle(&v182, v60, 1);
    if ( !DWORD2(v182) )
    {
      HmgPentryFromPobj(v59, v48);
LABEL_65:
      v139 = (*(_DWORD *)(v48 + 216))-- == 1;
      if ( v139 )
      {
        *(_QWORD *)(v48 + 208) = 0;
        if ( v173 )
          v173 = *(SURFACE **)v48;
        if ( (*(_DWORD *)(v48 + 160) & 0x8000000) != 0 )
        {
          v189 = *(_QWORD *)(v48 + 176);
          *(_QWORD *)(v48 + 176) = 0;
          XEPALOBJ::vUnrefPalette((XEPALOBJ *)&v189);
        }
        *(_DWORD *)(v48 + 160) &= ~0x8000000u;
      }
      goto LABEL_71;
    }
    v61 = (unsigned int *)v182;
    switch ( *(_BYTE *)(v182 + 14) )
    {
      case 4:
        v62 = *(_QWORD *)(v48 + 112);
        v63 = 2;
        break;
      case 5:
        v62 = *(_QWORD *)(v48 + 728);
        v63 = 3;
        break;
      case 0x10:
        v62 = *(_QWORD *)(v48 + 136);
        v63 = 0;
        break;
      default:
        goto LABEL_64;
    }
    TrackObjectReferenceDecrement(v59, v63, v62);
LABEL_64:
    --*(_DWORD *)(v48 + 8);
    v64 = *(__int64 **)(v183 + 8);
    v65 = *v64;
    v66 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v64 + 96))(v64, *v61);
    (*(void (__fastcall **)(__int64 *, __int64))(v65 + 48))(v64, v66);
    KeLeaveCriticalRegion();
    v53 = (DC **)v188;
    goto LABEL_65;
  }
  *(_QWORD *)a1 = 0;
  *(_BYTE *)(a1 + 8) = 5;
LABEL_150:
  GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal, v174);
LABEL_144:
  v139 = v187 == 0;
LABEL_145:
  if ( !v139 )
  {
    v140 = W32GetSessionState(v138);
    HmgDecrementShareReferenceCount(*(_QWORD *)(v140 + 88), v187);
  }
  PopThreadGuardedObject(&v185);
  return a1;
}

```

## disassembly

```asm
0x14001a450  mov     [rsp-8+arg_18], rbx
0x14001a455  push    rbp
0x14001a456  push    rsi
0x14001a457  push    rdi
0x14001a458  push    r12
0x14001a45a  push    r13
0x14001a45c  push    r14
0x14001a45e  push    r15
0x14001a460  lea     rbp, [rsp-10h]
0x14001a465  sub     rsp, 110h
0x14001a46c  mov     rax, cs:__security_cookie
0x14001a473  xor     rax, rsp
0x14001a476  mov     [rbp+40h+var_38], rax
0x14001a47a  xorps   xmm0, xmm0
0x14001a47d  mov     [rsp+140h+var_110], r9b
0x14001a482  movups  [rbp+40h+var_98], xmm0
0x14001a486  mov     rsi, r8
0x14001a489  mov     [rsp+140h+var_E8], r8
0x14001a48e  movups  [rbp+40h+var_88], xmm0
0x14001a492  mov     rbx, rdx
0x14001a495  mov     [rbp+40h+var_70], rdx
0x14001a499  mov     r12, rcx
0x14001a49c  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14001a4a3  nop     dword ptr [rax+rax+00h]
0x14001a4a8  xor     r15d, r15d
0x14001a4ab  test    rax, rax
0x14001a4ae  jz      loc_14001B73C
0x14001a4b4  mov     rcx, [rax]
0x14001a4b7  lea     rax, [rcx+8]
0x14001a4bb  neg     rcx
0x14001a4be  sbb     rdx, rdx
0x14001a4c1  and     rdx, rax
0x14001a4c4  lea     rax, [rbp+40h+var_98]
0x14001a4c8  mov     qword ptr [rbp+40h+var_88], rax
0x14001a4cc  lea     rax, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORSPACEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x14001a4d3  mov     qword ptr [rbp+40h+var_88+8], rax
0x14001a4d7  jz      loc_14001B7F1
0x14001a4dd  lea     rax, [rdx+58h]
0x14001a4e1  mov     rcx, [rax]
0x14001a4e4  cmp     [rcx+8], rax
0x14001a4e8  jz      short loc_14001A4F1
0x14001a4ea  mov     ecx, 3
0x14001a4ef  int     29h; Win8: RtlFailFast(ecx)
0x14001a4f1  mov     qword ptr [rbp+40h+var_98], rcx
0x14001a4f5  lea     rdx, [rbp+40h+var_98]
0x14001a4f9  mov     qword ptr [rbp+40h+var_98+8], rax
0x14001a4fd  mov     [rcx+8], rdx
0x14001a501  lea     rcx, [rbp+40h+var_98]
0x14001a505  mov     [rax], rcx
0x14001a508  mov     rax, [rbx+10h]
0x14001a50c  mov     [rsp+140h+var_C8], rax
0x14001a511  mov     [rbp+40h+var_78], r15
0x14001a515  call    cs:__imp_W32GetSessionState
0x14001a51c  nop     dword ptr [rax+rax+00h]
0x14001a521  mov     rcx, [rax+58h]
0x14001a525  mov     rax, [rcx]
0x14001a528  add     rax, 270h
0x14001a52e  mov     rcx, rax; hsem
0x14001a531  mov     [rsp+140h+var_F8], rax
0x14001a536  call    EngAcquireSemaphoreShared
0x14001a53b  call    ?GreGetCurrentThreadCrossSessionCheck@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThreadCrossSessionCheck(void)
0x14001a540  mov     rbx, rax
0x14001a543  mov     r13d, 1
0x14001a549  test    rax, rax
0x14001a54c  jz      short loc_14001A582
0x14001a54e  mov     r8, [rax]
0x14001a551  mov     rax, 0FFFFFFDFFFFFFFFEh
0x14001a55b  test    rax, r8
0x14001a55e  setnz   cl
0x14001a561  test    r8b, 2
0x14001a565  setz    al
0x14001a568  test    al, cl
0x14001a56a  jnz     loc_14001B5F5
0x14001a570  mov     cl, [rbx+9]
0x14001a573  lea     eax, [rcx+r13]
0x14001a577  mov     [rbx+9], al
0x14001a57a  test    cl, cl
0x14001a57c  jnz     short loc_14001A582
0x14001a57e  or      qword ptr [rbx], 2
0x14001a582  call    cs:__imp_W32GetSessionState
0x14001a589  nop     dword ptr [rax+rax+00h]
0x14001a58e  mov     edi, esi
0x14001a590  mov     [rsp+140h+var_100], r15
0x14001a595  shr     edi, 8
0x14001a598  lea     rcx, [rsp+140h+var_108]
0x14001a59d  and     edi, 0FF0000h
0x14001a5a3  mov     [rsp+140h+var_D4], r15w
0x14001a5a9  mov     rax, [rax+58h]
0x14001a5ad  mov     r14, r15
0x14001a5b0  mov     [rbp+40h+var_60], rax
0x14001a5b4  mov     rbx, r15
0x14001a5b7  mov     [rsp+140h+var_D0], rax
0x14001a5bc  movzx   eax, si
0x14001a5bf  or      edi, eax
0x14001a5c1  mov     [rsp+140h+var_108], r15
0x14001a5c6  call    cs:__imp_PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion
0x14001a5cd  nop     dword ptr [rax+rax+00h]
0x14001a5d2  mov     rsi, rax
0x14001a5d5  call    IsThreadCrossSessionAttached
0x14001a5da  test    eax, eax
0x14001a5dc  jnz     short loc_14001A5E6
0x14001a5de  test    rsi, rsi
0x14001a5e1  jz      short loc_14001A5E6
0x14001a5e3  mov     rbx, [rsi]
0x14001a5e6  lea     rax, [rbx+8]
0x14001a5ea  neg     rbx
0x14001a5ed  sbb     rbx, rbx
0x14001a5f0  and     rbx, rax
0x14001a5f3  jz      loc_14001B7DE
0x14001a5f9  mov     rax, [rbx+40h]
0x14001a5fd  mov     [rbp+40h+var_58], rax
0x14001a601  mov     rcx, [rbp+40h+var_60]
0x14001a605  mov     edx, edi
0x14001a607  mov     r15d, r13d
0x14001a60a  mov     [rsp+140h+var_D8], r13d
0x14001a60f  mov     rcx, [rcx+8]
0x14001a613  mov     rax, [rcx]
0x14001a616  mov     rax, [rax+28h]
0x14001a61a  call    _guard_dispatch_icall
0x14001a61f  xor     ecx, ecx
0x14001a621  mov     [rsp+140h+var_E0], rax
0x14001a626  mov     rsi, rax
0x14001a629  test    rax, rax
0x14001a62c  jz      loc_14001B48C
0x14001a632  prefetchw byte ptr [rax+8]
0x14001a636  mov     r14d, [rax+8]
0x14001a63a  mov     eax, dword ptr [rsp+140h+var_108]
0x14001a63e  and     r14d, 0FFFFFFFEh
0x14001a642  and     eax, 0FFFFFFFCh
0x14001a645  cmp     r14d, eax
0x14001a648  jnz     loc_14001B33C
0x14001a64e  mov     rax, [rbp+40h+var_60]
0x14001a652  mov     edx, [rsi]
0x14001a654  mov     rcx, [rax+8]
0x14001a658  mov     rax, [rcx]
0x14001a65b  mov     rax, [rax+60h]
0x14001a65f  call    _guard_dispatch_icall
0x14001a664  test    byte ptr [rax+0Eh], 20h
0x14001a668  jnz     loc_14001B6A7
0x14001a66e  mov     r14, [rsp+140h+var_100]
0x14001a673  test    r15d, r15d
0x14001a676  jz      loc_14001A700
0x14001a67c  cmp     byte ptr [rsi+0Eh], 5
0x14001a680  mov     rdi, [rsp+140h+var_D0]
0x14001a685  jnz     short loc_14001A6D0
0x14001a687  movzx   eax, byte ptr [rsi+0Ch]
0x14001a68b  movzx   ecx, byte ptr [rsi+0Dh]
0x14001a68f  shl     cx, 8
0x14001a693  or      cx, ax
0x14001a696  mov     eax, dword ptr [rsp+140h+var_E8]
0x14001a69a  shr     eax, 10h
0x14001a69d  cmp     cx, ax
0x14001a6a0  jnz     short loc_14001A6D0
0x14001a6a2  mov     rcx, [rdi+8]
0x14001a6a6  mov     edx, [rsi]
0x14001a6a8  mov     rax, [rcx]
0x14001a6ab  mov     rax, [rax+60h]
0x14001a6af  call    _guard_dispatch_icall
0x14001a6b4  mov     rcx, [rbp+40h+var_60]
0x14001a6b8  mov     edx, 3
0x14001a6bd  mov     r14, rax
0x14001a6c0  add     [rax+8], r13d
0x14001a6c4  mov     r8, [rax+2D8h]
0x14001a6cb  call    ?TrackObjectReferenceIncrement@@YAXAEAUSESSION_GLOBALS@Base@Gre@@W4ReferenceTrackerCountedType@@PEAX@Z; TrackObjectReferenceIncrement(Gre::Base::SESSION_GLOBALS &,ReferenceTrackerCountedType,void *)
0x14001a6d0  mov     rdi, [rdi+8]
0x14001a6d4  mov     edx, [rsi]
0x14001a6d6  mov     rcx, rdi
0x14001a6d9  mov     rbx, [rdi]
0x14001a6dc  mov     rax, [rbx+60h]
0x14001a6e0  call    _guard_dispatch_icall
0x14001a6e5  mov     rdx, rax
0x14001a6e8  mov     rcx, rdi
0x14001a6eb  mov     rax, [rbx+30h]
0x14001a6ef  call    _guard_dispatch_icall
0x14001a6f4  call    cs:__imp_KeLeaveCriticalRegion
0x14001a6fb  nop     dword ptr [rax+rax+00h]
0x14001a700  xor     r15d, r15d
0x14001a703  mov     [rbp+40h+var_78], r14
0x14001a707  test    r14, r14
0x14001a70a  jz      loc_14001B137
0x14001a710  test    [rsp+140h+var_110], 2
0x14001a715  mov     rax, [rsp+140h+var_C8]
0x14001a71a  setnz   byte ptr [rsp+140h+var_D8]
0x14001a71f  test    [rsp+140h+var_110], 2
0x14001a724  mov     rax, [rax]
0x14001a727  lea     rax, [rax+478h]
0x14001a72e  mov     [rsp+140h+var_E0], rax
0x14001a733  mov     rcx, rax; Resource
0x14001a736  jnz     loc_14001B222
0x14001a73c  call    ?GreAcquireSemaphoreInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreInternal(HSEMAPHORE__ *)
0x14001a741  call    ??$GrepAcquireLockValidate@$01@@YAXXZ; GrepAcquireLockValidate<2>(void)
0x14001a746  call    cs:__imp_W32GetSessionState
0x14001a74d  nop     dword ptr [rax+rax+00h]
0x14001a752  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, r15d
0x14001a759  mov     rcx, [rax+58h]
0x14001a75d  mov     rbx, [rcx]
0x14001a760  jnz     loc_14001B839
0x14001a766  lea     rdx, [rbx+5E8h]
0x14001a76d  call    ??$GreAcquireSemaphoreCommon@$0BE@P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x14001a772  mov     rdi, [rbp+40h+var_70]
0x14001a776  mov     ebx, r13d
0x14001a779  mov     rsi, [rbp+40h+var_78]
0x14001a77d  mov     [rsp+140h+var_F0], ebx
0x14001a781  mov     rdx, [rdi]
0x14001a784  mov     rax, [rdx+30h]
0x14001a788  mov     [rbp+40h+var_50], rax
0x14001a78c  cmp     [rdx], r15
0x14001a78f  jnz     loc_14001B164
0x14001a795  lea     r8, [rdx+868h]
0x14001a79c  xorps   xmm0, xmm0
0x14001a79f  movups  xmmword ptr [r8], xmm0
0x14001a7a3  xor     eax, eax
0x14001a7a5  mov     [r8+10h], rax
0x14001a7a9  mov     dword ptr [rdx+870h], 80000012h
0x14001a7b3  mov     [rdx+878h], r15
0x14001a7ba  mov     rdi, [rdi]
0x14001a7bd  cmp     [rdi+20h], r13d
0x14001a7c1  jnz     loc_14001B7B0
0x14001a7c7  cmp     [rsi+0D8h], r15d
0x14001a7ce  jnz     loc_14001B63F
0x14001a7d4  mov     rdi, [rdi+30h]
0x14001a7d8  cmp     [rsi+64h], r15w
0x14001a7dd  jnz     loc_14001B680
0x14001a7e3  cmp     [rsi+18h], r15
0x14001a7e7  jnz     loc_14001B680
0x14001a7ed  mov     r15, [rsi+0B0h]
0x14001a7f4  xor     ecx, ecx
0x14001a7f6  test    r15, r15
0x14001a7f9  jnz     short loc_14001A821
0x14001a7fb  mov     eax, [rdi+82Ch]
0x14001a801  cmp     [rsi+60h], eax
0x14001a804  jnz     loc_14001B868
0x14001a80a  test    dword ptr [rdi+86Ch], 100h
0x14001a814  jnz     loc_14001B831
0x14001a81a  mov     r15, [rdi+700h]
0x14001a821  mov     rax, [rsi+30h]
0x14001a825  mov     r14d, [r8+8]
0x14001a829  mov     [rbp+40h+var_68], rax
0x14001a82d  call    cs:__imp_W32GetSessionState
0x14001a834  nop     dword ptr [rax+rax+00h]
0x14001a839  xor     edx, edx
0x14001a83b  mov     rcx, [rax+58h]
0x14001a83f  cmp     rsi, [rcx+1118h]
0x14001a846  jz      short loc_14001A851
0x14001a848  test    rdi, rdi
0x14001a84b  jnz     loc_14001B190
0x14001a851  and     r14d, 0FFFFFFFEh
0x14001a855  jz      short loc_14001A867
0x14001a857  test    dword ptr [rsi+0A0h], 800h
0x14001a861  jnz     loc_14001B6EE
0x14001a867  mov     dil, [rsp+140h+var_110]
0x14001a86c  test    dil, 4
0x14001a870  jz      loc_14001B31B
0x14001a876  call    cs:__imp_W32GetSessionState
0x14001a87d  nop     dword ptr [rax+rax+00h]
0x14001a882  mov     rcx, [rbp+40h+var_70]
0x14001a886  xor     edx, edx
0x14001a888  mov     r10, [rcx]
0x14001a88b  mov     r14, [r10+1F0h]
0x14001a892  test    r14, r14
0x14001a895  jnz     loc_14001B154
0x14001a89b  mov     rax, [rax+58h]
0x14001a89f  mov     r14, [rax+1118h]
0x14001a8a6  bt      dword ptr [r14+0A0h], 1Ah
0x14001a8af  jnb     loc_14001B2C2
0x14001a8b5  bt      dword ptr [rsi+0A0h], 1Ah
0x14001a8bd  jnb     loc_14001B2C2
0x14001a8c3  test    dword ptr [r14+0A4h], 200h
0x14001a8ce  jnz     loc_14001B2C2
0x14001a8d4  mov     rax, [r10+3D0h]
0x14001a8db  mov     [rsp+140h+var_100], rdx
0x14001a8e0  mov     ecx, [rax+6Ch]
0x14001a8e3  mov     dword ptr [rbp+40h+var_60], ecx
0x14001a8e6  and     ecx, 7
0x14001a8e9  mov     dword ptr [rbp+40h+var_58], ecx
0x14001a8ec  jnz     loc_14001B3BD
0x14001a8f2  cmp     [rsi+0B0h], r15
0x14001a8f9  jnz     loc_14001B370
0x14001a8ff  test    dword ptr [r14+0A0h], 1000000h
0x14001a90a  jz      short loc_14001A914
0x14001a90c  mov     rax, [r14]
0x14001a90f  mov     [rsp+140h+var_100], rax
0x14001a914  mov     rdi, [r14+20h]
0x14001a918  mov     [rsp+140h+var_108], rdi
0x14001a91d  cmp     [rsp+140h+var_E8], rdi
0x14001a922  jz      loc_14001B368
0x14001a928  call    cs:__imp_W32GetSessionState
0x14001a92f  nop     dword ptr [rax+rax+00h]
0x14001a934  mov     r15, [rbp+40h+var_70]
0x14001a938  mov     rcx, [rax+58h]
0x14001a93c  mov     rax, [rcx+1118h]
0x14001a943  mov     rcx, [r15]; this
0x14001a946  cmp     rsi, rax
0x14001a949  jnz     loc_14001B24C
0x14001a94f  mov     eax, [rcx+208h]
0x14001a955  xor     edi, edi
0x14001a957  mov     [rcx+1F0h], rdi
0x14001a95e  test    r13b, al
0x14001a961  jz      short loc_14001A986
0x14001a963  or      dword ptr [rcx+24h], 10h
  ... truncated ...
```
