# xxxSwitchDesktop

- ea: `0x140194824`
- end: `0x140195723`
- name: `xxxSwitchDesktop`
- size: `3839`
- prototype: ``
- caller_count: `6`
- callee_count: `43`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140194224`
- `0x140194464`
- `0x1401945b0`
- `0x14023ec50`
- `0x14026cdd0`
- `0x1402720c0`

## callees

- `0x1400143c0`
- `0x140014460`
- `0x14001cb40`
- `0x140024100`
- `0x140028660`
- `0x1400292ec`
- `0x14002ac60`
- `0x14002d054`
- `0x1400373d0`
- `0x140038bb4`
- `0x14003a978`
- `0x1400b71ac`
- `0x1400bcaa0`
- `0x1400de254`
- `0x1400ec110`
- `0x1400ef954`
- `0x1401488b0`
- `0x140148b90`
- `0x1401600a4`
- `0x140194824`
- `0x140197750`
- `0x14019c780`
- `0x1401df29c`
- `0x1401f2774`
- `0x1401fba84`
- `0x14020e2b0`
- `0x14021fa80`
- `0x140228a44`
- `0x14022c2a0`
- `0x140230058`
- `0x140233dd0`
- `0x140236140`
- `0x14023ea20`
- `0x140240f7c`
- `0x14026e0fc`
- `0x1402714b0`
- `0x140272e14`
- `0x140274490`
- `0x140285ffc`
- `0x1402875a8`
- `0x1402913f0`
- `0x1402afe14`
- `0x1402c57b8`

## import_xrefs

- `ntoskrnl!KePulseEvent` at `0x14019559f`
- `ntoskrnl!KePulseEvent` at `0x14019559f`
- `ntoskrnl!PsIsSystemThread` at `0x140194ad6`
- `ntoskrnl!PsIsSystemThread` at `0x140194ad6`
- `ntoskrnl!PsGetThreadProcessId` at `0x140194b20`
- `ntoskrnl!PsGetThreadProcessId` at `0x1401955f4`
- `ntoskrnl!PsGetThreadProcessId` at `0x140194b20`
- `ntoskrnl!PsGetThreadProcessId` at `0x1401955f4`
- `ntoskrnl!ObQueryNameInfo` at `0x140194909`
- `ntoskrnl!ObQueryNameInfo` at `0x14019491d`
- `ntoskrnl!ObQueryNameInfo` at `0x140194932`
- `ntoskrnl!ObQueryNameInfo` at `0x140194946`
- `ntoskrnl!ObQueryNameInfo` at `0x1401949fc`
- `ntoskrnl!ObQueryNameInfo` at `0x140194a10`
- `ntoskrnl!ObQueryNameInfo` at `0x140194a25`
- `ntoskrnl!ObQueryNameInfo` at `0x140194a39`
- `ntoskrnl!ObQueryNameInfo` at `0x140194909`
- `ntoskrnl!ObQueryNameInfo` at `0x14019491d`
- `ntoskrnl!ObQueryNameInfo` at `0x140194932`
- `ntoskrnl!ObQueryNameInfo` at `0x140194946`
- `ntoskrnl!ObQueryNameInfo` at `0x1401949fc`
- `ntoskrnl!ObQueryNameInfo` at `0x140194a10`
- `ntoskrnl!ObQueryNameInfo` at `0x140194a25`
- `ntoskrnl!ObQueryNameInfo` at `0x140194a39`
- `ntoskrnl!ExDesktopObjectType` at `0x140194c49`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140194c65`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140194c65`
- `win32kbase!LockObjectAssignment` at `0x140194c17`
- `win32kbase!LockObjectAssignment` at `0x1401950c2`
- `win32kbase!LockObjectAssignment` at `0x140194c17`
- `win32kbase!LockObjectAssignment` at `0x1401950c2`
- `win32kbase!?Clear@tagUNIQUE_WINDOW_HANDLE@@QEAAXXZ` at `0x1401954cb`
- `win32kbase!?Clear@tagUNIQUE_WINDOW_HANDLE@@QEAAXXZ` at `0x1401954cb`
- `win32kbase!?Set@tagUNIQUE_WINDOW_HANDLE@@QEAAXPEBUtagWND@@@Z` at `0x140194d3c`
- `win32kbase!?Set@tagUNIQUE_WINDOW_HANDLE@@QEAAXPEBUtagWND@@@Z` at `0x140194d3c`
- `win32kbase!SynchronizeContext` at `0x1401950fe`
- `win32kbase!SynchronizeContext` at `0x1401950fe`
- `win32kbase!CitDesktopSwitch` at `0x14019510f`
- `win32kbase!CitDesktopSwitch` at `0x14019510f`
- `win32kbase!UserReferenceDwmApiPort` at `0x140195243`
- `win32kbase!UserReferenceDwmApiPort` at `0x140195243`
- `win32kbase!GreSuspendDirectDraw` at `0x1401953de`
- `win32kbase!GreSuspendDirectDraw` at `0x1401953de`
- `win32kbase!GreResumeDirectDraw` at `0x140195453`
- `win32kbase!GreResumeDirectDraw` at `0x140195453`
- `win32kbase!?Get@tagUNIQUE_WINDOW_HANDLE@@QEBAPEAUtagWND@@XZ` at `0x140195463`
- `win32kbase!?Get@tagUNIQUE_WINDOW_HANDLE@@QEBAPEAUtagWND@@XZ` at `0x140195463`
- `win32kbase!GreLockDynamicModeChange` at `0x140194e01`
- `win32kbase!GreLockDynamicModeChange` at `0x140194e01`
- `win32kbase!GreUnlockDynamicModeChange` at `0x140194e0d`
- `win32kbase!GreUnlockDynamicModeChange` at `0x140194e0d`
- `win32kbase!AllocQueue` at `0x140195178`
- `win32kbase!AllocQueue` at `0x140195178`
- `win32kbase!?gbIgnoreStressedOutStuff@@3HA` at `0x14019526e`
- `win32kbase!?gbIgnoreStressedOutStuff@@3HA` at `0x140195414`
- `win32kbase!?gbIgnoreStressedOutStuff@@3HA` at `0x1401954f5`
- `win32kbase!_HMPheFromObject` at `0x140194f0d`
- `win32kbase!_HMPheFromObject` at `0x140194f8a`
- `win32kbase!_HMPheFromObject` at `0x14019503c`
- `win32kbase!_HMPheFromObject` at `0x140194f0d`
- `win32kbase!_HMPheFromObject` at `0x140194f8a`
- `win32kbase!_HMPheFromObject` at `0x14019503c`
- `win32kbase!EnterCrit` at `0x140195262`
- `win32kbase!EnterCrit` at `0x140195262`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x14019522d`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x14019522d`
- `win32kbase!HMAssignmentLock` at `0x140194f52`
- `win32kbase!HMAssignmentLock` at `0x140194fd3`
- `win32kbase!HMAssignmentLock` at `0x140195081`
- `win32kbase!HMAssignmentLock` at `0x140194f52`
- `win32kbase!HMAssignmentLock` at `0x140194fd3`
- `win32kbase!HMAssignmentLock` at `0x140195081`
- `win32kbase!HMAssignmentUnlock` at `0x1401950a0`
- `win32kbase!HMAssignmentUnlock` at `0x1401950a0`
- `WIN32K!W32GetUserSessionState` at `0x140194871`
- `WIN32K!W32GetUserSessionState` at `0x140194965`
- `WIN32K!W32GetUserSessionState` at `0x14019499a`
- `WIN32K!W32GetUserSessionState` at `0x140194a57`
- `WIN32K!W32GetUserSessionState` at `0x140194abe`
- `WIN32K!W32GetUserSessionState` at `0x140194ae6`
- `WIN32K!W32GetUserSessionState` at `0x140194b0a`
- `WIN32K!W32GetUserSessionState` at `0x140194b3b`
- `WIN32K!W32GetUserSessionState` at `0x140194b54`
- `WIN32K!W32GetUserSessionState` at `0x140194b69`
- `WIN32K!W32GetUserSessionState` at `0x140194bb8`
- `WIN32K!W32GetUserSessionState` at `0x140194c01`
- `WIN32K!W32GetUserSessionState` at `0x140194cb8`
- `WIN32K!W32GetUserSessionState` at `0x140194cc4`
- `WIN32K!W32GetUserSessionState` at `0x140194cd9`
- `WIN32K!W32GetUserSessionState` at `0x140194cf6`
- `WIN32K!W32GetUserSessionState` at `0x140194d0b`
- `WIN32K!W32GetUserSessionState` at `0x140194d1e`
- `WIN32K!W32GetUserSessionState` at `0x140194d5f`
- `WIN32K!W32GetUserSessionState` at `0x140194d78`
- `WIN32K!W32GetUserSessionState` at `0x140194d9e`
- `WIN32K!W32GetUserSessionState` at `0x140194db8`
- `WIN32K!W32GetUserSessionState` at `0x140194ddc`
- `WIN32K!W32GetUserSessionState` at `0x140194e2a`
- `WIN32K!W32GetUserSessionState` at `0x140194e3f`
- `WIN32K!W32GetUserSessionState` at `0x140194e5b`
- `WIN32K!W32GetUserSessionState` at `0x140194e7a`
- `WIN32K!W32GetUserSessionState` at `0x140194e92`
- `WIN32K!W32GetUserSessionState` at `0x140194ea7`
- `WIN32K!W32GetUserSessionState` at `0x140194ecc`
- `WIN32K!W32GetUserSessionState` at `0x140194ee5`
- `WIN32K!W32GetUserSessionState` at `0x140194efa`
- `WIN32K!W32GetUserSessionState` at `0x140194f1f`
- `WIN32K!W32GetUserSessionState` at `0x140194f32`
- `WIN32K!W32GetUserSessionState` at `0x140194f5e`
- `WIN32K!W32GetUserSessionState` at `0x140194f77`
- `WIN32K!W32GetUserSessionState` at `0x140194fa0`
- `WIN32K!W32GetUserSessionState` at `0x140194fb3`
- `WIN32K!W32GetUserSessionState` at `0x140194fe4`
- `WIN32K!W32GetUserSessionState` at `0x140194ff7`
- `WIN32K!W32GetUserSessionState` at `0x140195010`
- `WIN32K!W32GetUserSessionState` at `0x140195029`
- `WIN32K!W32GetUserSessionState` at `0x14019504e`
- `WIN32K!W32GetUserSessionState` at `0x140195061`
- `WIN32K!W32GetUserSessionState` at `0x14019508d`
- `WIN32K!W32GetUserSessionState` at `0x1401950ac`
- `WIN32K!W32GetUserSessionState` at `0x1401950ce`
- `WIN32K!W32GetUserSessionState` at `0x1401950eb`
- `WIN32K!W32GetUserSessionState` at `0x140195138`
- `WIN32K!W32GetUserSessionState` at `0x1401951b1`
- `WIN32K!W32GetUserSessionState` at `0x1401951ed`
- `WIN32K!W32GetUserSessionState` at `0x14019527a`
- `WIN32K!W32GetUserSessionState` at `0x1401952ba`
- `WIN32K!W32GetUserSessionState` at `0x1401952f0`
- `WIN32K!W32GetUserSessionState` at `0x140195322`
- `WIN32K!W32GetUserSessionState` at `0x140195396`
- `WIN32K!W32GetUserSessionState` at `0x1401953c2`
- `WIN32K!W32GetUserSessionState` at `0x140195420`
- `WIN32K!W32GetUserSessionState` at `0x140195501`
- `WIN32K!W32GetUserSessionState` at `0x140195568`
- `WIN32K!W32GetUserSessionState` at `0x140195587`
- `WIN32K!W32GetUserSessionState` at `0x1401955c8`
- `WIN32K!W32GetUserSessionState` at `0x1401955dd`
- `WIN32K!W32GetUserSessionState` at `0x14019568e`
- `WIN32K!W32GetUserSessionState` at `0x140194871`
- `WIN32K!W32GetUserSessionState` at `0x140194965`
- `WIN32K!W32GetUserSessionState` at `0x14019499a`
- `WIN32K!W32GetUserSessionState` at `0x140194a57`
- `WIN32K!W32GetUserSessionState` at `0x140194abe`
- `WIN32K!W32GetUserSessionState` at `0x140194ae6`
- `WIN32K!W32GetUserSessionState` at `0x140194b0a`
- `WIN32K!W32GetUserSessionState` at `0x140194b3b`
- `WIN32K!W32GetUserSessionState` at `0x140194b54`
- `WIN32K!W32GetUserSessionState` at `0x140194b69`
- `WIN32K!W32GetUserSessionState` at `0x140194bb8`
- `WIN32K!W32GetUserSessionState` at `0x140194c01`
- `WIN32K!W32GetUserSessionState` at `0x140194cb8`
- `WIN32K!W32GetUserSessionState` at `0x140194cc4`
- `WIN32K!W32GetUserSessionState` at `0x140194cd9`
- `WIN32K!W32GetUserSessionState` at `0x140194cf6`
- `WIN32K!W32GetUserSessionState` at `0x140194d0b`
- `WIN32K!W32GetUserSessionState` at `0x140194d1e`
- `WIN32K!W32GetUserSessionState` at `0x140194d5f`
- `WIN32K!W32GetUserSessionState` at `0x140194d78`
- `WIN32K!W32GetUserSessionState` at `0x140194d9e`
- `WIN32K!W32GetUserSessionState` at `0x140194db8`
- `WIN32K!W32GetUserSessionState` at `0x140194ddc`
- `WIN32K!W32GetUserSessionState` at `0x140194e2a`
- `WIN32K!W32GetUserSessionState` at `0x140194e3f`
- `WIN32K!W32GetUserSessionState` at `0x140194e5b`
- `WIN32K!W32GetUserSessionState` at `0x140194e7a`
- `WIN32K!W32GetUserSessionState` at `0x140194e92`
- `WIN32K!W32GetUserSessionState` at `0x140194ea7`
- `WIN32K!W32GetUserSessionState` at `0x140194ecc`
- `WIN32K!W32GetUserSessionState` at `0x140194ee5`
- `WIN32K!W32GetUserSessionState` at `0x140194efa`
- `WIN32K!W32GetUserSessionState` at `0x140194f1f`
- `WIN32K!W32GetUserSessionState` at `0x140194f32`
- `WIN32K!W32GetUserSessionState` at `0x140194f5e`
- `WIN32K!W32GetUserSessionState` at `0x140194f77`
- `WIN32K!W32GetUserSessionState` at `0x140194fa0`
- `WIN32K!W32GetUserSessionState` at `0x140194fb3`
- `WIN32K!W32GetUserSessionState` at `0x140194fe4`
- `WIN32K!W32GetUserSessionState` at `0x140194ff7`
- `WIN32K!W32GetUserSessionState` at `0x140195010`
- `WIN32K!W32GetUserSessionState` at `0x140195029`
- `WIN32K!W32GetUserSessionState` at `0x14019504e`
- `WIN32K!W32GetUserSessionState` at `0x140195061`
- `WIN32K!W32GetUserSessionState` at `0x14019508d`
- `WIN32K!W32GetUserSessionState` at `0x1401950ac`
- `WIN32K!W32GetUserSessionState` at `0x1401950ce`
- `WIN32K!W32GetUserSessionState` at `0x1401950eb`
- `WIN32K!W32GetUserSessionState` at `0x140195138`
- `WIN32K!W32GetUserSessionState` at `0x1401951b1`
- `WIN32K!W32GetUserSessionState` at `0x1401951ed`
- `WIN32K!W32GetUserSessionState` at `0x14019527a`
- `WIN32K!W32GetUserSessionState` at `0x1401952ba`
- `WIN32K!W32GetUserSessionState` at `0x1401952f0`
- `WIN32K!W32GetUserSessionState` at `0x140195322`
- `WIN32K!W32GetUserSessionState` at `0x140195396`
- `WIN32K!W32GetUserSessionState` at `0x1401953c2`
- `WIN32K!W32GetUserSessionState` at `0x140195420`
- `WIN32K!W32GetUserSessionState` at `0x140195501`
- `WIN32K!W32GetUserSessionState` at `0x140195568`
- `WIN32K!W32GetUserSessionState` at `0x140195587`
- `WIN32K!W32GetUserSessionState` at `0x1401955c8`

## pseudocode

```c
__int64 __fastcall xxxSwitchDesktop(__int64 a1, __int64 a2, char a3)
{
  __int64 v5; // rcx
  struct MOVESIZEDATA *v7; // rcx
  char v8; // si
  char v9; // bl
  bool v10; // r12
  __int64 v11; // rcx
  __int64 UserSessionState; // rax
  int v13; // r8d
  int v14; // edx
  struct MOVESIZEDATA *v15; // rcx
  char v16; // r14
  bool v17; // r15
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rbx
  __int64 v21; // rax
  int v22; // r8d
  int v23; // edx
  struct _KTHREAD *CurrentThread; // r14
  __int64 v25; // rcx
  HANDLE v26; // rbx
  __int64 v27; // rcx
  __int64 v28; // rcx
  struct MOVESIZEDATA *v29; // rcx
  bool v30; // bl
  __int64 v31; // rax
  int v32; // r8d
  int v33; // edx
  __int64 v34; // rax
  int v35; // r12d
  void *v36; // rbx
  struct tagTHREADINFO *v37; // rax
  ULONG_PTR v38; // r14
  _QWORD *v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rbx
  __int64 v45; // rcx
  __int64 v46; // rax
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rax
  __int64 v51; // rcx
  __int64 v52; // rax
  __int64 v53; // rcx
  __int64 v54; // rax
  struct tagEDGY_DATA *v55; // rdx
  __int64 v56; // rax
  __int64 v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rax
  __int64 v60; // rcx
  __int64 v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rax
  __int64 v64; // rcx
  __int64 v65; // rax
  __int64 v66; // rbx
  __int64 v67; // rcx
  __int64 v68; // rax
  __int64 v69; // rbx
  __int64 v70; // rcx
  __int64 v71; // rax
  __int64 v72; // rcx
  __int64 v73; // rcx
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rcx
  __int64 **v77; // rax
  __int64 v78; // rbx
  struct tagWND **v79; // rcx
  __int64 v80; // rax
  int v81; // r14d
  __int64 v82; // rcx
  __int64 v83; // rcx
  __int64 v84; // rdx
  __int64 v85; // rcx
  void *v86; // rax
  __int64 **v87; // rax
  __int64 v88; // r15
  BOOL v89; // r14d
  _QWORD *v90; // rax
  unsigned int v91; // ebx
  __int64 v92; // rax
  __int64 v93; // rcx
  ULONG_PTR v94; // r13
  __int64 v95; // rcx
  int v96; // r15d
  int v97; // ebx
  __int64 v98; // rax
  __int64 v99; // rcx
  struct tagWND *i; // rbx
  __int64 v101; // rcx
  __int64 v102; // rcx
  __int64 v103; // rcx
  __int64 v104; // r9
  __int64 v105; // rcx
  __int64 v106; // rcx
  __int64 v107; // rax
  __int64 v108; // rcx
  __int64 v109; // rdx
  __int64 v110; // rcx
  HANDLE v111; // rbx
  int v112; // eax
  bool v113; // bl
  __int64 v114; // rax
  int v115; // r8d
  int v116; // edx
  ULONG_PTR v117; // [rsp+58h] [rbp-39h] BYREF
  __int64 v118; // [rsp+60h] [rbp-31h]
  void *Handle; // [rsp+68h] [rbp-29h] BYREF
  ULONG_PTR BugCheckParameter3[2]; // [rsp+70h] [rbp-21h] BYREF
  PETHREAD Thread; // [rsp+80h] [rbp-11h]
  _QWORD v122[2]; // [rsp+88h] [rbp-9h] BYREF
  __int64 v123; // [rsp+98h] [rbp+7h]
  _BYTE v124[16]; // [rsp+A0h] [rbp+Fh] BYREF
  __int64 v125; // [rsp+B0h] [rbp+1Fh]
  __int64 v126; // [rsp+100h] [rbp+6Fh]

  BugCheckParameter3[0] = (ULONG_PTR)PtiCurrent();
  Handle = 0;
  if ( !a2 )
    return 3221225473LL;
  if ( a2 == *(_QWORD *)(W32GetUserSessionState(v5) + 19216) )
    return 0;
  if ( (*(_DWORD *)(a2 + 48) & 8) != 0 )
    return 3221225485LL;
  if ( !a1 )
    a1 = *(_QWORD *)(a2 + 40);
  if ( (*(_DWORD *)(a1 + 32) & 4) != 0 )
    return 3221225485LL;
  v126 = *(_QWORD *)(a1 + 24);
  v7 = WPP_GLOBAL_Control;
  v8 = 1;
  if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) == 0
    || (v9 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v9 = 0;
  }
  v10 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v9 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    if ( ObQueryNameInfo(a2) && ObQueryNameInfo(a2) != -8 && ObQueryNameInfo(a2) )
      ObQueryNameInfo(a2);
    UserSessionState = W32GetUserSessionState(v11);
    LOBYTE(v13) = v10;
    LOBYTE(v14) = v9;
    WPP_RECORDER_AND_TRACE_SF_SL(*((_QWORD *)WPP_GLOBAL_Control + 3), v14, v13, *(_QWORD *)(UserSessionState + 69152));
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v7) + 19216) )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) == 0
      || (v16 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
    {
      v16 = 0;
    }
    v17 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v16 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      if ( !ObQueryNameInfo(a2) || ObQueryNameInfo(a2) == -8 )
      {
        v20 = 0;
      }
      else
      {
        if ( ObQueryNameInfo(a2) )
          v19 = ObQueryNameInfo(a2) + 16;
        else
          v19 = 8;
        v20 = *(_QWORD *)v19;
      }
      v21 = W32GetUserSessionState(v18);
      LOBYTE(v22) = v17;
      LOBYTE(v23) = v16;
      WPP_RECORDER_AND_TRACE_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v23,
        v22,
        *(_QWORD *)(v21 + 69152),
        4,
        3,
        27,
        (__int64)WPP_8482796ea87931402564603ebe19074e_Traceguids,
        v20);
    }
  }
  CurrentThread = KeGetCurrentThread();
  Thread = CurrentThread;
  if ( a2 != *(_QWORD *)(W32GetUserSessionState(v15) + 62752)
    && !PsIsSystemThread(CurrentThread)
    && a2 != *(_QWORD *)(W32GetUserSessionState(v25) + 62744)
    && (*(_DWORD *)(a1 + 32) & 1) != 0
    && (a3 & 2) == 0 )
  {
    v26 = *(HANDLE *)(W32GetUserSessionState(v25) + 63312);
    if ( PsGetThreadProcessId(CurrentThread) != v26 )
      return 3221225506LL;
  }
  if ( *(_DWORD *)(W32GetUserSessionState(v25) + 62600)
    && (!*(_QWORD *)(W32GetUserSessionState(v27) + 62752) || a2 != *(_QWORD *)(W32GetUserSessionState(v28) + 62752)) )
  {
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
    {
      v8 = 0;
    }
    v30 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v8 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v31 = W32GetUserSessionState(WPP_GLOBAL_Control);
      LOBYTE(v32) = v30;
      LOBYTE(v33) = v8;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v33,
        v32,
        *(_QWORD *)(v31 + 69152),
        4,
        8,
        28,
        (__int64)WPP_8482796ea87931402564603ebe19074e_Traceguids);
    }
    v34 = W32GetUserSessionState(v29);
    LockObjectAssignment(v34 + 19224, a2);
    return 0;
  }
  v35 = 0;
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(v124, a2);
  ObOpenObjectByPointer((PVOID)a2, 0x200u, 0, 0x1F0003u, (POBJECT_TYPE)ExDesktopObjectType, 0, &Handle);
  v36 = Handle;
  v37 = PtiCurrent();
  v38 = BugCheckParameter3[0];
  v122[0] = *((_QWORD *)v37 + 47);
  v39 = v122;
  *((_QWORD *)v37 + 47) = v122;
  v123 = (__int64)AllowDesktopDestruction;
  v122[1] = v36;
  if ( *(_QWORD *)(v38 + 488) )
  {
    zzzDesktopSwitchSideEffects();
    ResetPointerDevices(1);
    W32GetUserSessionState(v40);
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v39) + 19216) )
  {
    v42 = *(_QWORD *)(W32GetUserSessionState(v41) + 19216);
    if ( *(_QWORD *)(*(_QWORD *)(v42 + 8) + 24LL) )
    {
      if ( *(_QWORD *)(W32GetUserSessionState(v42) + 18968) )
      {
        v44 = *(_QWORD *)(W32GetUserSessionState(v43) + 19216);
        v46 = W32GetUserSessionState(v45);
        tagUNIQUE_WINDOW_HANDLE::Set(
          (tagUNIQUE_WINDOW_HANDLE *)(v44 + 88),
          *(const struct tagWND **)(*(_QWORD *)(v46 + 18968) + 128LL));
        xxxSetForegroundWindow2(0, v38, 0x20u);
      }
    }
  }
  UpdateKeyboardStateOnDesktopSwitch(1);
  if ( *(_QWORD *)(W32GetUserSessionState(v47) + 19216) )
  {
    v48 = **(_QWORD **)(*(_QWORD *)(W32GetUserSessionState(v48) + 19216) + 8LL);
    if ( (*(_DWORD *)(v48 + 64) & 1) != 0 )
    {
      if ( *(_QWORD *)(W32GetUserSessionState(v48) + 42800) )
        StopFade();
      v50 = W32GetUserSessionState(v49);
      bSetDevDragRect(*(HDEV *)(*(_QWORD *)(v50 + 56744) + 40LL));
      v52 = W32GetUserSessionState(v51);
      ComposeWindow(*(struct tagWND **)(*(_QWORD *)(*(_QWORD *)(v52 + 19216) + 8LL) + 24LL));
      GreLockDynamicModeChange();
      GreUnlockDynamicModeChange();
      v48 = *(_QWORD *)(a1 + 88);
      if ( v48 )
        EraseBitmap();
      v35 = 1;
    }
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v48) + 19216) )
  {
    v53 = *(_QWORD *)(W32GetUserSessionState(v53) + 19216);
    if ( *(_QWORD *)(v53 + 248) )
    {
      v54 = W32GetUserSessionState(v53);
      Edgy::FreeEdgyFrameData(*(Edgy **)(*(_QWORD *)(v54 + 19216) + 248LL), v55);
    }
  }
  v56 = W32GetUserSessionState(v53);
  ResetWindowKeyProcessing(*(struct tagDESKTOP **)(v56 + 19216));
  if ( *(_QWORD *)(W32GetUserSessionState(v57) + 19216) )
  {
    v59 = W32GetUserSessionState(v58);
    *(_DWORD *)(*(_QWORD *)(v59 + 19216) + 48LL) |= 0x1000u;
  }
  if ( (unsigned int)Feature_PreserveActiveHklInDesktopSwitching__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( a2 == *(_QWORD *)(W32GetUserSessionState(v60) + 62744) )
    {
      if ( *(_QWORD *)(W32GetUserSessionState(v61) + 14184) )
      {
        v63 = W32GetUserSessionState(v62);
        if ( (*(_BYTE *)(_HMPheFromObject(*(_QWORD *)(v63 + 14184)) + 25) & 1) == 0 )
        {
          v118 = *(_QWORD *)(W32GetUserSessionState(v62) + 14184);
          v117 = W32GetUserSessionState(v64) + 14192;
          HMAssignmentLock(&v117, 0);
        }
      }
      if ( *(_QWORD *)(W32GetUserSessionState(v62) + 14216) )
      {
        v65 = W32GetUserSessionState(v60);
        if ( (*(_BYTE *)(_HMPheFromObject(*(_QWORD *)(v65 + 14216)) + 25) & 1) == 0 )
        {
          v66 = *(_QWORD *)(W32GetUserSessionState(v60) + 14216);
          v68 = W32GetUserSessionState(v67);
          v118 = v66;
          v117 = v68 + 14184;
          HMAssignmentLock(&v117, 0);
        }
      }
    }
    else
    {
      v69 = *(_QWORD *)(W32GetUserSessionState(v61) + 19216);
      if ( v69 == *(_QWORD *)(W32GetUserSessionState(v70) + 62744) )
      {
        if ( *(_QWORD *)(W32GetUserSessionState(v60) + 14192) )
        {
          v71 = W32GetUserSessionState(v60);
          if ( (*(_BYTE *)(_HMPheFromObject(*(_QWORD *)(v71 + 14192)) + 25) & 1) == 0 )
          {
            v118 = *(_QWORD *)(W32GetUserSessionState(v60) + 14192);
            v117 = W32GetUserSessionState(v72) + 14184;
            HMAssignmentLock(&v117, 0);
            v74 = W32GetUserSessionState(v73);
            HMAssignmentUnlock(v74 + 14192);
          }
        }
      }
    }
  }
  v75 = W32GetUserSessionState(v60);
  LockObjectAssignment(v75 + 19216, a2);
  v77 = *(__int64 ***)(*(_QWORD *)(W32GetUserSessionState(v76) + 19216) + 8LL);
  v78 = **v77;
  *(_QWORD *)(W32GetUserSessionState(*v77) + 18760) = v78;
  SynchronizeContext();
  UpdateInUserCritUpdatedPointerRedirectedGlobalsOnDesktopSwitch();
  CitDesktopSwitch();
  v79 = *(struct tagWND ***)(a2 + 8);
  if ( (*((_DWORD *)*v79 + 16) & 1) != 0 )
    ComposeWindow(v79[3]);
  v80 = W32GetUserSessionState(v79);
  v81 = zzzSetDesktop(*(_QWORD *)(v80 + 18752), a2, 0);
  if ( v81 >= 0 )
  {
    if ( *(_QWORD *)(*(_QWORD *)(v126 + 16) + 464LL) != *(_QWORD *)(v126 + 24) )
    {
      AllocQueue(0);
      tagQ::zzzAttachToQueue(*(tagQ **)(v126 + 24), *(struct tagTHREADINFO **)(v126 + 16), 0, 0);
    }
    v81 = zzzSetDesktop(*(_QWORD *)(v126 + 16), a2, 0);
    if ( v81 >= 0 )
    {
      v83 = *(_QWORD *)(W32GetUserSessionState(v82) + 19216);
      if ( *(_QWORD *)(*(_QWORD *)(v126 + 16) + 488LL) != v83 )
        MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4202);
      if ( a2 != *(_QWORD *)(W32GetUserSessionState(v83) + 19216) )
        MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4203);
      v85 = **(_QWORD **)(a2 + 8);
      if ( (*(_DWORD *)(v85 + 64) & 1) != 0 )
      {
        UserSessionSwitchLeaveCrit(v85, v84);
        v86 = (void *)UserReferenceDwmApiPort();
        DwmSyncDesktopSwitch(v86);
        EnterCrit(1, 0);
      }
      if ( !gbIgnoreStressedOutStuff && a2 != *(_QWORD *)(W32GetUserSessionState(v85) + 19216) )
        MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4217);
      v87 = *(__int64 ***)(a2 + 8);
      v88 = **v87;
      v89 = v35 && (*(_DWORD *)(**(_QWORD **)(*(_QWORD *)(W32GetUserSessionState(*v87) + 19216) + 8LL) + 64LL) & 1) != 0;
      v90 = *(_QWORD **)(a2 + 8);
      v91 = *(_DWORD *)(*v90 + 64LL) & 1;
      v92 = W32GetUserSessionState(*v90);
      v81 = GreDesktopSwitch(*(_QWORD *)(*(_QWORD *)(v92 + 56744) + 40LL), v91, v89, v88);
      if ( v81 >= 0 )
      {
        if ( v35 == (*(_DWORD *)(**(_QWORD **)(*(_QWORD *)(W32GetUserSessionState(v93) + 19216) + 8LL) + 64LL) & 1) )
          ResetCursorPointerInternal();
        else
          zzzEnableDwmPointerSupport(*(_DWORD *)(**(_QWORD **)(a2 + 8) + 64LL) & 1, 0);
        v94 = BugCheckParameter3[0];
        Win32HM_LockIntoThread<1>(BugCheckParameter3[0], *(_QWORD *)(*(_QWORD *)(a2 + 8) + 24LL), &v117);
        GreLddmProcessDesktopSwitch();
        v95 = **(_QWORD **)(a2 + 8);
        v96 = 4 * (*(_DWORD *)(v95 + 64) & 1);
        if ( !v35
          || (v97 = 9,
              v95 = **(_QWORD **)(*(_QWORD *)(W32GetUserSessionState(v95) + 19216) + 8LL),
              (*(_DWORD *)(v95 + 64) & 1) == 0) )
        {
          v97 = 1;
        }
        v98 = W32GetUserSessionState(v95);
        GreSuspendDirectDraw(*(_QWORD *)(*(_QWORD *)(v98 + 56744) + 40LL), v96 | (unsigned int)v97, 0);
        xxxSetWindowPos(*(struct tagWND **)(*(_QWORD *)(a2 + 8) + 24LL), 0, 0, 339);
        if ( !gbIgnoreStressedOutStuff && a2 != *(_QWORD *)(W32GetUserSessionState(v99) + 19216) )
          MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4283);
        GreResumeDirectDraw(0);
        i = tagUNIQUE_WINDOW_HANDLE::Get((tagUNIQUE_WINDOW_HANDLE *)(a2 + 88));
        if ( !(unsigned __int8)lambda_74a3533f2c879f4574bc0a0461c8b857_::operator()(v101, i)
          || (unsigned int)IsWindowUnderActiveLockScreen(i) )
        {
          for ( i = *(struct tagWND **)(*(_QWORD *)(*(_QWORD *)(a2 + 8) + 24LL) + 112LL);
                i;
                i = (struct tagWND *)*((_QWORD *)i + 11) )
          {
            if ( (unsigned int)IsWindowUnderActiveLockScreen(i) )
            {
              i = 0;
              break;
            }
            if ( (unsigned __int8)lambda_74a3533f2c879f4574bc0a0461c8b857_::operator()(v102, i) )
              break;
          }
        }
        Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)&v117);
        tagUNIQUE_WINDOW_HANDLE::Clear((tagUNIQUE_WINDOW_HANDLE *)(a2 + 88));
        UpdateKeyboardStateOnDesktopSwitch(0);
        if ( i )
        {
          if ( !gbIgnoreStressedOutStuff
            && *(_QWORD *)(*((_QWORD *)i + 2) + 488LL) != *(_QWORD *)(W32GetUserSessionState(v103) + 19216) )
          {
            MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4368);
          }
          Win32HM_LockIntoThread<0>(v94, i, BugCheckParameter3, v104);
          xxxSetForegroundWindowWithOptions(i, 31, 32, 0);
          Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)BugCheckParameter3);
        }
        else
        {
          xxxSetForegroundWindow2(0, 0, 0x20u);
        }
        v106 = *(_QWORD *)(W32GetUserSessionState(v105) + 19160);
        if ( v106 )
          IPostQuitMessage(v106, 0);
        v107 = W32GetUserSessionState(v106);
        KePulseEvent(*(PRKEVENT *)(v107 + 62736), 1, 0);
        xxxWindowEvent(0x20u, 0, 0, 0, 6);
        zzzUpdateCursorImage();
        if ( a2 == *(_QWORD *)(W32GetUserSessionState(v108) + 62744) )
        {
          v111 = *(HANDLE *)(W32GetUserSessionState(v110) + 63312);
          if ( PsGetThreadProcessId(Thread) == v111 )
          {
            v110 = *(unsigned int *)(*(_QWORD *)(a2 + 40) + 32LL);
            if ( (v110 & 1) != 0 )
              SetTimerCoalescingTolerance(3);
          }
        }
        v112 = *(_DWORD *)(a2 + 48);
        if ( (v112 & 0x20) != 0 )
        {
          v110 = *(_QWORD *)(a2 + 8);
          if ( v110 )
          {
            if ( *(_QWORD *)(v110 + 24) )
            {
              *(_DWORD *)(a2 + 48) = v112 & 0xFFFFFFDF;
              xxxBroadcastDisplaySettingsChange(a2, 1, 0, 0);
            }
          }
        }
        DrvOcclusionStateChangeNotify(v110, v109);
        xxxRefreshDisplayOrientation();
      }
    }
  }
  if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
  {
    v8 = 0;
  }
  v113 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v8 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v114 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v115) = v113;
    LOBYTE(v116) = v8;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v116,
      v115,
      *(_QWORD *)(v114 + 69152),
      4,
      3,
      29,
      (__int64)WPP_8482796ea87931402564603ebe19074e_Traceguids,
      v81);
  }
  PopAndFreeW32ThreadLock(v122);
  v123 = -1;
  if ( v125 != -1 )
    PopAndFreeW32ThreadLock(v124);
  return (unsigned int)v81;
}

```

## disassembly

```asm
0x140194824  mov     rax, rsp
0x140194827  mov     [rax+8], rbx
0x14019482b  mov     [rax+20h], r9d
0x14019482f  mov     [rax+18h], r8d
0x140194833  push    rbp
0x140194834  push    rsi
0x140194835  push    rdi
0x140194836  push    r12
0x140194838  push    r13
0x14019483a  push    r14
0x14019483c  push    r15
0x14019483e  lea     rbp, [rax-5Fh]
0x140194842  sub     rsp, 0B0h
0x140194849  mov     r14d, r8d
0x14019484c  mov     rdi, rdx
0x14019484f  mov     r13, rcx
0x140194852  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140194857  xor     r15d, r15d
0x14019485a  mov     [rbp+57h+BugCheckParameter3], rax
0x14019485e  mov     [rbp+57h+var_80], r15
0x140194862  test    rdi, rdi
0x140194865  jnz     short loc_140194871
0x140194867  mov     eax, 0C0000001h
0x14019486c  jmp     loc_140195707
0x140194871  call    cs:__imp_W32GetUserSessionState
0x140194878  nop     dword ptr [rax+rax+00h]
0x14019487d  cmp     rdi, [rax+4B10h]
0x140194884  jnz     short loc_14019488D
0x140194886  xor     eax, eax
0x140194888  jmp     loc_140195707
0x14019488d  mov     eax, [rdi+30h]
0x140194890  test    al, 8
0x140194892  jnz     loc_140195702
0x140194898  test    r13, r13
0x14019489b  jnz     short loc_1401948A1
0x14019489d  mov     r13, [rdi+28h]
0x1401948a1  mov     eax, [r13+20h]
0x1401948a5  mov     dl, 4
0x1401948a7  test    dl, al
0x1401948a9  jnz     loc_140195702
0x1401948af  mov     rax, [r13+18h]
0x1401948b3  mov     [rbp+57h+arg_8], rax
0x1401948b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1401948be  lea     rax, WPP_GLOBAL_Control
0x1401948c5  mov     esi, 1
0x1401948ca  cmp     rcx, rax
0x1401948cd  jz      short loc_1401948DE
0x1401948cf  mov     eax, [rcx+2Ch]
0x1401948d2  test    dl, al
0x1401948d4  jz      short loc_1401948DE
0x1401948d6  mov     bl, sil
0x1401948d9  cmp     [rcx+29h], dl
0x1401948dc  jnb     short loc_1401948E1
0x1401948de  mov     bl, r15b
0x1401948e1  lea     rax, WPP_RECORDER_INITIALIZED
0x1401948e8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1401948ef  setnz   r12b
0x1401948f3  test    bl, bl
0x1401948f5  jnz     short loc_140194900
0x1401948f7  test    r12b, r12b
0x1401948fa  jz      loc_14019499A
0x140194900  mov     r15d, r14d
0x140194903  mov     rcx, rdi
0x140194906  and     r15d, esi
0x140194909  call    cs:__imp_ObQueryNameInfo
0x140194910  nop     dword ptr [rax+rax+00h]
0x140194915  test    rax, rax
0x140194918  jz      short loc_140194962
0x14019491a  mov     rcx, rdi
0x14019491d  call    cs:__imp_ObQueryNameInfo
0x140194924  nop     dword ptr [rax+rax+00h]
0x140194929  add     rax, 8
0x14019492d  jz      short loc_140194962
0x14019492f  mov     rcx, rdi
0x140194932  call    cs:__imp_ObQueryNameInfo
0x140194939  nop     dword ptr [rax+rax+00h]
0x14019493e  test    rax, rax
0x140194941  jz      short loc_140194958
0x140194943  mov     rcx, rdi
0x140194946  call    cs:__imp_ObQueryNameInfo
0x14019494d  nop     dword ptr [rax+rax+00h]
0x140194952  add     rax, 10h
0x140194956  jmp     short loc_14019495D
0x140194958  mov     eax, 8
0x14019495d  mov     r14, [rax]
0x140194960  jmp     short loc_140194965
0x140194962  xor     r14d, r14d
0x140194965  call    cs:__imp_W32GetUserSessionState
0x14019496c  nop     dword ptr [rax+rax+00h]
0x140194971  mov     rcx, cs:WPP_GLOBAL_Control
0x140194978  mov     r8b, r12b
0x14019497b  mov     [rsp+48h], r15d
0x140194980  mov     dl, bl
0x140194982  mov     qword ptr [rsp+0E0h+var_A0], r14
0x140194987  mov     r9, [rax+10E20h]
0x14019498e  mov     rcx, [rcx+18h]
0x140194992  call    WPP_RECORDER_AND_TRACE_SF_SL
0x140194997  xor     r15d, r15d
0x14019499a  call    cs:__imp_W32GetUserSessionState
0x1401949a1  nop     dword ptr [rax+rax+00h]
0x1401949a6  cmp     [rax+4B10h], r15
0x1401949ad  jz      loc_140194AAA
0x1401949b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1401949ba  lea     r12, WPP_GLOBAL_Control
0x1401949c1  cmp     rcx, r12
0x1401949c4  jz      short loc_1401949D6
0x1401949c6  mov     eax, [rcx+2Ch]
0x1401949c9  test    al, 4
0x1401949cb  jz      short loc_1401949D6
0x1401949cd  cmp     byte ptr [rcx+29h], 4
0x1401949d1  mov     r14b, sil
0x1401949d4  jnb     short loc_1401949D9
0x1401949d6  mov     r14b, r15b
0x1401949d9  lea     rax, WPP_RECORDER_INITIALIZED
0x1401949e0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1401949e7  setnz   r15b
0x1401949eb  test    r14b, r14b
0x1401949ee  jnz     short loc_1401949F9
0x1401949f0  test    r15b, r15b
0x1401949f3  jz      loc_140194AA5
0x1401949f9  mov     rcx, rdi
0x1401949fc  call    cs:__imp_ObQueryNameInfo
0x140194a03  nop     dword ptr [rax+rax+00h]
0x140194a08  test    rax, rax
0x140194a0b  jz      short loc_140194A55
0x140194a0d  mov     rcx, rdi
0x140194a10  call    cs:__imp_ObQueryNameInfo
0x140194a17  nop     dword ptr [rax+rax+00h]
0x140194a1c  add     rax, 8
0x140194a20  jz      short loc_140194A55
0x140194a22  mov     rcx, rdi
0x140194a25  call    cs:__imp_ObQueryNameInfo
0x140194a2c  nop     dword ptr [rax+rax+00h]
0x140194a31  test    rax, rax
0x140194a34  jz      short loc_140194A4B
0x140194a36  mov     rcx, rdi
0x140194a39  call    cs:__imp_ObQueryNameInfo
0x140194a40  nop     dword ptr [rax+rax+00h]
0x140194a45  add     rax, 10h
0x140194a49  jmp     short loc_140194A50
0x140194a4b  mov     eax, 8
0x140194a50  mov     rbx, [rax]
0x140194a53  jmp     short loc_140194A57
0x140194a55  xor     ebx, ebx
0x140194a57  call    cs:__imp_W32GetUserSessionState
0x140194a5e  nop     dword ptr [rax+rax+00h]
0x140194a63  mov     qword ptr [rsp+0E0h+var_A0], rbx
0x140194a68  lea     rcx, WPP_8482796ea87931402564603ebe19074e_Traceguids
0x140194a6f  mov     [rsp+0E0h+var_A8], rcx
0x140194a74  mov     r8b, r15b
0x140194a77  mov     rcx, cs:WPP_GLOBAL_Control
0x140194a7e  mov     dl, r14b
0x140194a81  mov     r9, [rax+10E20h]
0x140194a88  mov     word ptr [rsp+0E0h+Handle], 1Bh
0x140194a8f  mov     dword ptr [rsp+0E0h+AccessMode], 3
0x140194a97  mov     rcx, [rcx+18h]
0x140194a9b  mov     byte ptr [rsp+0E0h+ObjectType], 4
0x140194aa0  call    WPP_RECORDER_AND_TRACE_SF_S
0x140194aa5  xor     r15d, r15d
0x140194aa8  jmp     short loc_140194AB1
0x140194aaa  lea     r12, WPP_GLOBAL_Control
0x140194ab1  mov     r14, gs:188h
0x140194aba  mov     [rbp+57h+Thread], r14
0x140194abe  call    cs:__imp_W32GetUserSessionState
0x140194ac5  nop     dword ptr [rax+rax+00h]
0x140194aca  cmp     rdi, [rax+0F520h]
0x140194ad1  jz      short loc_140194B3B
0x140194ad3  mov     rcx, r14; Thread
0x140194ad6  call    cs:__imp_PsIsSystemThread
0x140194add  nop     dword ptr [rax+rax+00h]
0x140194ae2  test    al, al
0x140194ae4  jnz     short loc_140194B3B
0x140194ae6  call    cs:__imp_W32GetUserSessionState
0x140194aed  nop     dword ptr [rax+rax+00h]
0x140194af2  cmp     rdi, [rax+0F518h]
0x140194af9  jz      short loc_140194B3B
0x140194afb  mov     eax, [r13+20h]
0x140194aff  test    sil, al
0x140194b02  jz      short loc_140194B3B
0x140194b04  test    [rbp+57h+arg_10], 2
0x140194b08  jnz     short loc_140194B3B
0x140194b0a  call    cs:__imp_W32GetUserSessionState
0x140194b11  nop     dword ptr [rax+rax+00h]
0x140194b16  mov     rcx, r14; Thread
0x140194b19  mov     rbx, [rax+0F750h]
0x140194b20  call    cs:__imp_PsGetThreadProcessId
0x140194b27  nop     dword ptr [rax+rax+00h]
0x140194b2c  cmp     rax, rbx
0x140194b2f  jz      short loc_140194B3B
0x140194b31  mov     eax, 0C0000022h
0x140194b36  jmp     loc_140195707
0x140194b3b  call    cs:__imp_W32GetUserSessionState
0x140194b42  nop     dword ptr [rax+rax+00h]
0x140194b47  cmp     [rax+0F488h], r15d
0x140194b4e  jz      loc_140194C28
0x140194b54  call    cs:__imp_W32GetUserSessionState
0x140194b5b  nop     dword ptr [rax+rax+00h]
0x140194b60  cmp     [rax+0F520h], r15
0x140194b67  jz      short loc_140194B82
0x140194b69  call    cs:__imp_W32GetUserSessionState
0x140194b70  nop     dword ptr [rax+rax+00h]
0x140194b75  cmp     rdi, [rax+0F520h]
0x140194b7c  jz      loc_140194C28
0x140194b82  mov     rcx, cs:WPP_GLOBAL_Control
0x140194b89  cmp     rcx, r12
0x140194b8c  jz      short loc_140194B9B
0x140194b8e  mov     eax, [rcx+2Ch]
0x140194b91  test    al, al
0x140194b93  jns     short loc_140194B9B
0x140194b95  cmp     byte ptr [rcx+29h], 4
0x140194b99  jnb     short loc_140194B9E
0x140194b9b  mov     sil, r15b
0x140194b9e  lea     rax, WPP_RECORDER_INITIALIZED
0x140194ba5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140194bac  setnz   bl
0x140194baf  test    sil, sil
0x140194bb2  jnz     short loc_140194BB8
0x140194bb4  test    bl, bl
0x140194bb6  jz      short loc_140194C01
0x140194bb8  call    cs:__imp_W32GetUserSessionState
0x140194bbf  nop     dword ptr [rax+rax+00h]
0x140194bc4  lea     rcx, WPP_8482796ea87931402564603ebe19074e_Traceguids
0x140194bcb  mov     r8b, bl
0x140194bce  mov     [rsp+0E0h+var_A8], rcx
0x140194bd3  mov     dl, sil
0x140194bd6  mov     rcx, cs:WPP_GLOBAL_Control
0x140194bdd  mov     r9, [rax+10E20h]
0x140194be4  mov     word ptr [rsp+0E0h+Handle], 1Ch
0x140194beb  mov     dword ptr [rsp+0E0h+AccessMode], 8
0x140194bf3  mov     rcx, [rcx+18h]
0x140194bf7  mov     byte ptr [rsp+0E0h+ObjectType], 4
0x140194bfc  call    WPP_RECORDER_AND_TRACE_SF_
0x140194c01  call    cs:__imp_W32GetUserSessionState
0x140194c08  nop     dword ptr [rax+rax+00h]
0x140194c0d  mov     rdx, rdi
0x140194c10  lea     rcx, [rax+4B18h]
0x140194c17  call    cs:__imp_LockObjectAssignment
0x140194c1e  nop     dword ptr [rax+rax+00h]
0x140194c23  jmp     loc_140194886
0x140194c28  mov     rdx, rdi
0x140194c2b  lea     rcx, [rbp+57h+var_48]
0x140194c2f  mov     r12d, r15d
0x140194c32  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@PEAUtagDESKTOP@@@Z; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(tagDESKTOP *)
0x140194c37  lea     rax, [rbp+57h+var_80]
0x140194c3b  mov     r9d, 1F0003h; DesiredAccess
0x140194c41  mov     [rsp+0E0h+Handle], rax; Handle
0x140194c46  xor     r8d, r8d; PassedAccessState
0x140194c49  mov     rax, cs:ExDesktopObjectType
0x140194c50  mov     edx, 200h; HandleAttributes
0x140194c55  mov     [rsp+0E0h+AccessMode], r15b; AccessMode
0x140194c5a  mov     rcx, [rax]
0x140194c5d  mov     [rsp+0E0h+ObjectType], rcx; ObjectType
0x140194c62  mov     rcx, rdi; Object
0x140194c65  call    cs:__imp_ObOpenObjectByPointer
0x140194c6c  nop     dword ptr [rax+rax+00h]
0x140194c71  mov     rbx, [rbp+57h+var_80]
0x140194c75  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140194c7a  mov     r14, [rbp+57h+BugCheckParameter3]
0x140194c7e  mov     rcx, [rax+178h]
0x140194c85  mov     [rbp+57h+var_60], rcx
0x140194c89  lea     rcx, [rbp+57h+var_60]
0x140194c8d  mov     [rax+178h], rcx
0x140194c94  lea     rax, ?AllowDesktopDestruction@@YAXPEAX@Z; AllowDesktopDestruction(void *)
0x140194c9b  mov     [rbp+57h+var_50], rax
0x140194c9f  mov     [rbp+57h+var_58], rbx
0x140194ca3  cmp     [r14+1E8h], r15
0x140194caa  jz      short loc_140194CC4
0x140194cac  call    zzzDesktopSwitchSideEffects
0x140194cb1  mov     ecx, esi
0x140194cb3  call    ?ResetPointerDevices@@YAXW4ResetPointerDevicesStrategy@@@Z; ResetPointerDevices(ResetPointerDevicesStrategy)
0x140194cb8  call    cs:__imp_W32GetUserSessionState
0x140194cbf  nop     dword ptr [rax+rax+00h]
0x140194cc4  call    cs:__imp_W32GetUserSessionState
0x140194ccb  nop     dword ptr [rax+rax+00h]
0x140194cd0  cmp     [rax+4B10h], r15
0x140194cd7  jz      short loc_140194D58
0x140194cd9  call    cs:__imp_W32GetUserSessionState
0x140194ce0  nop     dword ptr [rax+rax+00h]
0x140194ce5  mov     rcx, [rax+4B10h]
0x140194cec  mov     rax, [rcx+8]
0x140194cf0  cmp     [rax+18h], r15
0x140194cf4  jz      short loc_140194D58
0x140194cf6  call    cs:__imp_W32GetUserSessionState
0x140194cfd  nop     dword ptr [rax+rax+00h]
0x140194d02  cmp     [rax+4A18h], r15
0x140194d09  jz      short loc_140194D58
0x140194d0b  call    cs:__imp_W32GetUserSessionState
0x140194d12  nop     dword ptr [rax+rax+00h]
0x140194d17  mov     rbx, [rax+4B10h]
0x140194d1e  call    cs:__imp_W32GetUserSessionState
0x140194d25  nop     dword ptr [rax+rax+00h]
0x140194d2a  lea     rcx, [rbx+58h]
0x140194d2e  mov     rdx, [rax+4A18h]
0x140194d35  mov     rdx, [rdx+80h]
0x140194d3c  call    cs:__imp_?Set@tagUNIQUE_WINDOW_HANDLE@@QEAAXPEBUtagWND@@@Z; tagUNIQUE_WINDOW_HANDLE::Set(tagWND const *)
0x140194d43  nop     dword ptr [rax+rax+00h]
0x140194d48  mov     r8d, 20h ; ' '
0x140194d4e  mov     rdx, r14
0x140194d51  xor     ecx, ecx
0x140194d53  call    ?xxxSetForegroundWindow2@@YAHPEAUtagWND@@PEAUtagTHREADINFO@@W4SetForegroundBehaviors@@@Z; xxxSetForegroundWindow2(tagWND *,tagTHREADINFO *,SetForegroundBehaviors)
  ... truncated ...
```
