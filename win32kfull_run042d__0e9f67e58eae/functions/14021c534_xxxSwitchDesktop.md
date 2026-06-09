# xxxSwitchDesktop

- ea: `0x14021c534`
- end: `0x14021d433`
- name: `xxxSwitchDesktop`
- size: `3839`
- prototype: ``
- caller_count: `6`
- callee_count: `43`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14004ba38`
- `0x14021c174`
- `0x14021c2c0`
- `0x14023fbb0`
- `0x1402702c0`
- `0x140275be0`

## callees

- `0x140004350`
- `0x1400114a4`
- `0x14001ef90`
- `0x140023570`
- `0x1400241fc`
- `0x140025b90`
- `0x140027f94`
- `0x140032d50`
- `0x140049fec`
- `0x14004b3e4`
- `0x140094860`
- `0x1400c0e10`
- `0x1400c0e50`
- `0x1400dd43c`
- `0x1400e2cb0`
- `0x14011ae80`
- `0x14013e870`
- `0x14013eb50`
- `0x140150d0c`
- `0x14016f3c4`
- `0x14017cc14`
- `0x14019e730`
- `0x1401a9acc`
- `0x1401dc5cc`
- `0x1401f70c4`
- `0x1401fd034`
- `0x140216be0`
- `0x14021c534`
- `0x140220d7c`
- `0x140229aa4`
- `0x14022d290`
- `0x1402314e8`
- `0x1402367b0`
- `0x14023f984`
- `0x140241e00`
- `0x140271cc4`
- `0x140276934`
- `0x140277b1c`
- `0x140287b94`
- `0x140288f68`
- `0x1402938dc`
- `0x1402b17c4`
- `0x1402c76a8`

## import_xrefs

- `ntoskrnl!KePulseEvent` at `0x14021d2af`
- `ntoskrnl!KePulseEvent` at `0x14021d2af`
- `ntoskrnl!PsIsSystemThread` at `0x14021c7e6`
- `ntoskrnl!PsIsSystemThread` at `0x14021c7e6`
- `ntoskrnl!PsGetThreadProcessId` at `0x14021c830`
- `ntoskrnl!PsGetThreadProcessId` at `0x14021d304`
- `ntoskrnl!PsGetThreadProcessId` at `0x14021c830`
- `ntoskrnl!PsGetThreadProcessId` at `0x14021d304`
- `ntoskrnl!ObQueryNameInfo` at `0x14021c619`
- `ntoskrnl!ObQueryNameInfo` at `0x14021c62d`
- `ntoskrnl!ObQueryNameInfo` at `0x14021c642`
- `ntoskrnl!ObQueryNameInfo` at `0x14021c656`
- `ntoskrnl!ObQueryNameInfo` at `0x14021c70c`
- `ntoskrnl!ObQueryNameInfo` at `0x14021c720`
- `ntoskrnl!ObQueryNameInfo` at `0x14021c735`
- `ntoskrnl!ObQueryNameInfo` at `0x14021c749`
- `ntoskrnl!ObQueryNameInfo` at `0x14021c619`
- `ntoskrnl!ObQueryNameInfo` at `0x14021c62d`
- `ntoskrnl!ObQueryNameInfo` at `0x14021c642`
- `ntoskrnl!ObQueryNameInfo` at `0x14021c656`
- `ntoskrnl!ObQueryNameInfo` at `0x14021c70c`
- `ntoskrnl!ObQueryNameInfo` at `0x14021c720`
- `ntoskrnl!ObQueryNameInfo` at `0x14021c735`
- `ntoskrnl!ObQueryNameInfo` at `0x14021c749`
- `ntoskrnl!ExDesktopObjectType` at `0x14021c959`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14021c975`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14021c975`
- `win32kbase!LockObjectAssignment` at `0x14021c927`
- `win32kbase!LockObjectAssignment` at `0x14021cdd2`
- `win32kbase!LockObjectAssignment` at `0x14021c927`
- `win32kbase!LockObjectAssignment` at `0x14021cdd2`
- `win32kbase!?Clear@tagUNIQUE_WINDOW_HANDLE@@QEAAXXZ` at `0x14021d1db`
- `win32kbase!?Clear@tagUNIQUE_WINDOW_HANDLE@@QEAAXXZ` at `0x14021d1db`
- `win32kbase!?Set@tagUNIQUE_WINDOW_HANDLE@@QEAAXPEBUtagWND@@@Z` at `0x14021ca4c`
- `win32kbase!?Set@tagUNIQUE_WINDOW_HANDLE@@QEAAXPEBUtagWND@@@Z` at `0x14021ca4c`
- `win32kbase!SynchronizeContext` at `0x14021ce0e`
- `win32kbase!SynchronizeContext` at `0x14021ce0e`
- `win32kbase!CitDesktopSwitch` at `0x14021ce1f`
- `win32kbase!CitDesktopSwitch` at `0x14021ce1f`
- `win32kbase!UserReferenceDwmApiPort` at `0x14021cf53`
- `win32kbase!UserReferenceDwmApiPort` at `0x14021cf53`
- `win32kbase!GreSuspendDirectDraw` at `0x14021d0ee`
- `win32kbase!GreSuspendDirectDraw` at `0x14021d0ee`
- `win32kbase!GreResumeDirectDraw` at `0x14021d163`
- `win32kbase!GreResumeDirectDraw` at `0x14021d163`
- `win32kbase!?Get@tagUNIQUE_WINDOW_HANDLE@@QEBAPEAUtagWND@@XZ` at `0x14021d173`
- `win32kbase!?Get@tagUNIQUE_WINDOW_HANDLE@@QEBAPEAUtagWND@@XZ` at `0x14021d173`
- `win32kbase!GreLockDynamicModeChange` at `0x14021cb11`
- `win32kbase!GreLockDynamicModeChange` at `0x14021cb11`
- `win32kbase!GreUnlockDynamicModeChange` at `0x14021cb1d`
- `win32kbase!GreUnlockDynamicModeChange` at `0x14021cb1d`
- `win32kbase!AllocQueue` at `0x14021ce88`
- `win32kbase!AllocQueue` at `0x14021ce88`
- `win32kbase!?gbIgnoreStressedOutStuff@@3HA` at `0x14021cf7e`
- `win32kbase!?gbIgnoreStressedOutStuff@@3HA` at `0x14021d124`
- `win32kbase!?gbIgnoreStressedOutStuff@@3HA` at `0x14021d205`
- `win32kbase!_HMPheFromObject` at `0x14021cc1d`
- `win32kbase!_HMPheFromObject` at `0x14021cc9a`
- `win32kbase!_HMPheFromObject` at `0x14021cd4c`
- `win32kbase!_HMPheFromObject` at `0x14021cc1d`
- `win32kbase!_HMPheFromObject` at `0x14021cc9a`
- `win32kbase!_HMPheFromObject` at `0x14021cd4c`
- `win32kbase!EnterCrit` at `0x14021cf72`
- `win32kbase!EnterCrit` at `0x14021cf72`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x14021cf3d`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x14021cf3d`
- `win32kbase!HMAssignmentLock` at `0x14021cc62`
- `win32kbase!HMAssignmentLock` at `0x14021cce3`
- `win32kbase!HMAssignmentLock` at `0x14021cd91`
- `win32kbase!HMAssignmentLock` at `0x14021cc62`
- `win32kbase!HMAssignmentLock` at `0x14021cce3`
- `win32kbase!HMAssignmentLock` at `0x14021cd91`
- `win32kbase!HMAssignmentUnlock` at `0x14021cdb0`
- `win32kbase!HMAssignmentUnlock` at `0x14021cdb0`
- `WIN32K!W32GetUserSessionState` at `0x14021c581`
- `WIN32K!W32GetUserSessionState` at `0x14021c675`
- `WIN32K!W32GetUserSessionState` at `0x14021c6aa`
- `WIN32K!W32GetUserSessionState` at `0x14021c767`
- `WIN32K!W32GetUserSessionState` at `0x14021c7ce`
- `WIN32K!W32GetUserSessionState` at `0x14021c7f6`
- `WIN32K!W32GetUserSessionState` at `0x14021c81a`
- `WIN32K!W32GetUserSessionState` at `0x14021c84b`
- `WIN32K!W32GetUserSessionState` at `0x14021c864`
- `WIN32K!W32GetUserSessionState` at `0x14021c879`
- `WIN32K!W32GetUserSessionState` at `0x14021c8c8`
- `WIN32K!W32GetUserSessionState` at `0x14021c911`
- `WIN32K!W32GetUserSessionState` at `0x14021c9c8`
- `WIN32K!W32GetUserSessionState` at `0x14021c9d4`
- `WIN32K!W32GetUserSessionState` at `0x14021c9e9`
- `WIN32K!W32GetUserSessionState` at `0x14021ca06`
- `WIN32K!W32GetUserSessionState` at `0x14021ca1b`
- `WIN32K!W32GetUserSessionState` at `0x14021ca2e`
- `WIN32K!W32GetUserSessionState` at `0x14021ca6f`
- `WIN32K!W32GetUserSessionState` at `0x14021ca88`
- `WIN32K!W32GetUserSessionState` at `0x14021caae`
- `WIN32K!W32GetUserSessionState` at `0x14021cac8`
- `WIN32K!W32GetUserSessionState` at `0x14021caec`
- `WIN32K!W32GetUserSessionState` at `0x14021cb3a`
- `WIN32K!W32GetUserSessionState` at `0x14021cb4f`
- `WIN32K!W32GetUserSessionState` at `0x14021cb6b`
- `WIN32K!W32GetUserSessionState` at `0x14021cb8a`
- `WIN32K!W32GetUserSessionState` at `0x14021cba2`
- `WIN32K!W32GetUserSessionState` at `0x14021cbb7`
- `WIN32K!W32GetUserSessionState` at `0x14021cbdc`
- `WIN32K!W32GetUserSessionState` at `0x14021cbf5`
- `WIN32K!W32GetUserSessionState` at `0x14021cc0a`
- `WIN32K!W32GetUserSessionState` at `0x14021cc2f`
- `WIN32K!W32GetUserSessionState` at `0x14021cc42`
- `WIN32K!W32GetUserSessionState` at `0x14021cc6e`
- `WIN32K!W32GetUserSessionState` at `0x14021cc87`
- `WIN32K!W32GetUserSessionState` at `0x14021ccb0`
- `WIN32K!W32GetUserSessionState` at `0x14021ccc3`
- `WIN32K!W32GetUserSessionState` at `0x14021ccf4`
- `WIN32K!W32GetUserSessionState` at `0x14021cd07`
- `WIN32K!W32GetUserSessionState` at `0x14021cd20`
- `WIN32K!W32GetUserSessionState` at `0x14021cd39`
- `WIN32K!W32GetUserSessionState` at `0x14021cd5e`
- `WIN32K!W32GetUserSessionState` at `0x14021cd71`
- `WIN32K!W32GetUserSessionState` at `0x14021cd9d`
- `WIN32K!W32GetUserSessionState` at `0x14021cdbc`
- `WIN32K!W32GetUserSessionState` at `0x14021cdde`
- `WIN32K!W32GetUserSessionState` at `0x14021cdfb`
- `WIN32K!W32GetUserSessionState` at `0x14021ce48`
- `WIN32K!W32GetUserSessionState` at `0x14021cec1`
- `WIN32K!W32GetUserSessionState` at `0x14021cefd`
- `WIN32K!W32GetUserSessionState` at `0x14021cf8a`
- `WIN32K!W32GetUserSessionState` at `0x14021cfca`
- `WIN32K!W32GetUserSessionState` at `0x14021d000`
- `WIN32K!W32GetUserSessionState` at `0x14021d032`
- `WIN32K!W32GetUserSessionState` at `0x14021d0a6`
- `WIN32K!W32GetUserSessionState` at `0x14021d0d2`
- `WIN32K!W32GetUserSessionState` at `0x14021d130`
- `WIN32K!W32GetUserSessionState` at `0x14021d211`
- `WIN32K!W32GetUserSessionState` at `0x14021d278`
- `WIN32K!W32GetUserSessionState` at `0x14021d297`
- `WIN32K!W32GetUserSessionState` at `0x14021d2d8`
- `WIN32K!W32GetUserSessionState` at `0x14021d2ed`
- `WIN32K!W32GetUserSessionState` at `0x14021d39e`
- `WIN32K!W32GetUserSessionState` at `0x14021c581`
- `WIN32K!W32GetUserSessionState` at `0x14021c675`
- `WIN32K!W32GetUserSessionState` at `0x14021c6aa`
- `WIN32K!W32GetUserSessionState` at `0x14021c767`
- `WIN32K!W32GetUserSessionState` at `0x14021c7ce`
- `WIN32K!W32GetUserSessionState` at `0x14021c7f6`
- `WIN32K!W32GetUserSessionState` at `0x14021c81a`
- `WIN32K!W32GetUserSessionState` at `0x14021c84b`
- `WIN32K!W32GetUserSessionState` at `0x14021c864`
- `WIN32K!W32GetUserSessionState` at `0x14021c879`
- `WIN32K!W32GetUserSessionState` at `0x14021c8c8`
- `WIN32K!W32GetUserSessionState` at `0x14021c911`
- `WIN32K!W32GetUserSessionState` at `0x14021c9c8`
- `WIN32K!W32GetUserSessionState` at `0x14021c9d4`
- `WIN32K!W32GetUserSessionState` at `0x14021c9e9`
- `WIN32K!W32GetUserSessionState` at `0x14021ca06`
- `WIN32K!W32GetUserSessionState` at `0x14021ca1b`
- `WIN32K!W32GetUserSessionState` at `0x14021ca2e`
- `WIN32K!W32GetUserSessionState` at `0x14021ca6f`
- `WIN32K!W32GetUserSessionState` at `0x14021ca88`
- `WIN32K!W32GetUserSessionState` at `0x14021caae`
- `WIN32K!W32GetUserSessionState` at `0x14021cac8`
- `WIN32K!W32GetUserSessionState` at `0x14021caec`
- `WIN32K!W32GetUserSessionState` at `0x14021cb3a`
- `WIN32K!W32GetUserSessionState` at `0x14021cb4f`
- `WIN32K!W32GetUserSessionState` at `0x14021cb6b`
- `WIN32K!W32GetUserSessionState` at `0x14021cb8a`
- `WIN32K!W32GetUserSessionState` at `0x14021cba2`
- `WIN32K!W32GetUserSessionState` at `0x14021cbb7`
- `WIN32K!W32GetUserSessionState` at `0x14021cbdc`
- `WIN32K!W32GetUserSessionState` at `0x14021cbf5`
- `WIN32K!W32GetUserSessionState` at `0x14021cc0a`
- `WIN32K!W32GetUserSessionState` at `0x14021cc2f`
- `WIN32K!W32GetUserSessionState` at `0x14021cc42`
- `WIN32K!W32GetUserSessionState` at `0x14021cc6e`
- `WIN32K!W32GetUserSessionState` at `0x14021cc87`
- `WIN32K!W32GetUserSessionState` at `0x14021ccb0`
- `WIN32K!W32GetUserSessionState` at `0x14021ccc3`
- `WIN32K!W32GetUserSessionState` at `0x14021ccf4`
- `WIN32K!W32GetUserSessionState` at `0x14021cd07`
- `WIN32K!W32GetUserSessionState` at `0x14021cd20`
- `WIN32K!W32GetUserSessionState` at `0x14021cd39`
- `WIN32K!W32GetUserSessionState` at `0x14021cd5e`
- `WIN32K!W32GetUserSessionState` at `0x14021cd71`
- `WIN32K!W32GetUserSessionState` at `0x14021cd9d`
- `WIN32K!W32GetUserSessionState` at `0x14021cdbc`
- `WIN32K!W32GetUserSessionState` at `0x14021cdde`
- `WIN32K!W32GetUserSessionState` at `0x14021cdfb`
- `WIN32K!W32GetUserSessionState` at `0x14021ce48`
- `WIN32K!W32GetUserSessionState` at `0x14021cec1`
- `WIN32K!W32GetUserSessionState` at `0x14021cefd`
- `WIN32K!W32GetUserSessionState` at `0x14021cf8a`
- `WIN32K!W32GetUserSessionState` at `0x14021cfca`
- `WIN32K!W32GetUserSessionState` at `0x14021d000`
- `WIN32K!W32GetUserSessionState` at `0x14021d032`
- `WIN32K!W32GetUserSessionState` at `0x14021d0a6`
- `WIN32K!W32GetUserSessionState` at `0x14021d0d2`
- `WIN32K!W32GetUserSessionState` at `0x14021d130`
- `WIN32K!W32GetUserSessionState` at `0x14021d211`
- `WIN32K!W32GetUserSessionState` at `0x14021d278`
- `WIN32K!W32GetUserSessionState` at `0x14021d297`
- `WIN32K!W32GetUserSessionState` at `0x14021d2d8`

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
0x14021c534  mov     rax, rsp
0x14021c537  mov     [rax+8], rbx
0x14021c53b  mov     [rax+20h], r9d
0x14021c53f  mov     [rax+18h], r8d
0x14021c543  push    rbp
0x14021c544  push    rsi
0x14021c545  push    rdi
0x14021c546  push    r12
0x14021c548  push    r13
0x14021c54a  push    r14
0x14021c54c  push    r15
0x14021c54e  lea     rbp, [rax-5Fh]
0x14021c552  sub     rsp, 0B0h
0x14021c559  mov     r14d, r8d
0x14021c55c  mov     rdi, rdx
0x14021c55f  mov     r13, rcx
0x14021c562  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14021c567  xor     r15d, r15d
0x14021c56a  mov     [rbp+57h+BugCheckParameter3], rax
0x14021c56e  mov     [rbp+57h+var_80], r15
0x14021c572  test    rdi, rdi
0x14021c575  jnz     short loc_14021C581
0x14021c577  mov     eax, 0C0000001h
0x14021c57c  jmp     loc_14021D417
0x14021c581  call    cs:__imp_W32GetUserSessionState
0x14021c588  nop     dword ptr [rax+rax+00h]
0x14021c58d  cmp     rdi, [rax+4B10h]
0x14021c594  jnz     short loc_14021C59D
0x14021c596  xor     eax, eax
0x14021c598  jmp     loc_14021D417
0x14021c59d  mov     eax, [rdi+30h]
0x14021c5a0  test    al, 8
0x14021c5a2  jnz     loc_14021D412
0x14021c5a8  test    r13, r13
0x14021c5ab  jnz     short loc_14021C5B1
0x14021c5ad  mov     r13, [rdi+28h]
0x14021c5b1  mov     eax, [r13+20h]
0x14021c5b5  mov     dl, 4
0x14021c5b7  test    dl, al
0x14021c5b9  jnz     loc_14021D412
0x14021c5bf  mov     rax, [r13+18h]
0x14021c5c3  mov     [rbp+57h+arg_8], rax
0x14021c5c7  mov     rcx, cs:WPP_GLOBAL_Control
0x14021c5ce  lea     rax, WPP_GLOBAL_Control
0x14021c5d5  mov     esi, 1
0x14021c5da  cmp     rcx, rax
0x14021c5dd  jz      short loc_14021C5EE
0x14021c5df  mov     eax, [rcx+2Ch]
0x14021c5e2  test    dl, al
0x14021c5e4  jz      short loc_14021C5EE
0x14021c5e6  mov     bl, sil
0x14021c5e9  cmp     [rcx+29h], dl
0x14021c5ec  jnb     short loc_14021C5F1
0x14021c5ee  mov     bl, r15b
0x14021c5f1  lea     rax, WPP_RECORDER_INITIALIZED
0x14021c5f8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14021c5ff  setnz   r12b
0x14021c603  test    bl, bl
0x14021c605  jnz     short loc_14021C610
0x14021c607  test    r12b, r12b
0x14021c60a  jz      loc_14021C6AA
0x14021c610  mov     r15d, r14d
0x14021c613  mov     rcx, rdi
0x14021c616  and     r15d, esi
0x14021c619  call    cs:__imp_ObQueryNameInfo
0x14021c620  nop     dword ptr [rax+rax+00h]
0x14021c625  test    rax, rax
0x14021c628  jz      short loc_14021C672
0x14021c62a  mov     rcx, rdi
0x14021c62d  call    cs:__imp_ObQueryNameInfo
0x14021c634  nop     dword ptr [rax+rax+00h]
0x14021c639  add     rax, 8
0x14021c63d  jz      short loc_14021C672
0x14021c63f  mov     rcx, rdi
0x14021c642  call    cs:__imp_ObQueryNameInfo
0x14021c649  nop     dword ptr [rax+rax+00h]
0x14021c64e  test    rax, rax
0x14021c651  jz      short loc_14021C668
0x14021c653  mov     rcx, rdi
0x14021c656  call    cs:__imp_ObQueryNameInfo
0x14021c65d  nop     dword ptr [rax+rax+00h]
0x14021c662  add     rax, 10h
0x14021c666  jmp     short loc_14021C66D
0x14021c668  mov     eax, 8
0x14021c66d  mov     r14, [rax]
0x14021c670  jmp     short loc_14021C675
0x14021c672  xor     r14d, r14d
0x14021c675  call    cs:__imp_W32GetUserSessionState
0x14021c67c  nop     dword ptr [rax+rax+00h]
0x14021c681  mov     rcx, cs:WPP_GLOBAL_Control
0x14021c688  mov     r8b, r12b
0x14021c68b  mov     [rsp+48h], r15d
0x14021c690  mov     dl, bl
0x14021c692  mov     qword ptr [rsp+0E0h+var_A0], r14
0x14021c697  mov     r9, [rax+10E20h]
0x14021c69e  mov     rcx, [rcx+18h]
0x14021c6a2  call    WPP_RECORDER_AND_TRACE_SF_SL
0x14021c6a7  xor     r15d, r15d
0x14021c6aa  call    cs:__imp_W32GetUserSessionState
0x14021c6b1  nop     dword ptr [rax+rax+00h]
0x14021c6b6  cmp     [rax+4B10h], r15
0x14021c6bd  jz      loc_14021C7BA
0x14021c6c3  mov     rcx, cs:WPP_GLOBAL_Control
0x14021c6ca  lea     r12, WPP_GLOBAL_Control
0x14021c6d1  cmp     rcx, r12
0x14021c6d4  jz      short loc_14021C6E6
0x14021c6d6  mov     eax, [rcx+2Ch]
0x14021c6d9  test    al, 4
0x14021c6db  jz      short loc_14021C6E6
0x14021c6dd  cmp     byte ptr [rcx+29h], 4
0x14021c6e1  mov     r14b, sil
0x14021c6e4  jnb     short loc_14021C6E9
0x14021c6e6  mov     r14b, r15b
0x14021c6e9  lea     rax, WPP_RECORDER_INITIALIZED
0x14021c6f0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14021c6f7  setnz   r15b
0x14021c6fb  test    r14b, r14b
0x14021c6fe  jnz     short loc_14021C709
0x14021c700  test    r15b, r15b
0x14021c703  jz      loc_14021C7B5
0x14021c709  mov     rcx, rdi
0x14021c70c  call    cs:__imp_ObQueryNameInfo
0x14021c713  nop     dword ptr [rax+rax+00h]
0x14021c718  test    rax, rax
0x14021c71b  jz      short loc_14021C765
0x14021c71d  mov     rcx, rdi
0x14021c720  call    cs:__imp_ObQueryNameInfo
0x14021c727  nop     dword ptr [rax+rax+00h]
0x14021c72c  add     rax, 8
0x14021c730  jz      short loc_14021C765
0x14021c732  mov     rcx, rdi
0x14021c735  call    cs:__imp_ObQueryNameInfo
0x14021c73c  nop     dword ptr [rax+rax+00h]
0x14021c741  test    rax, rax
0x14021c744  jz      short loc_14021C75B
0x14021c746  mov     rcx, rdi
0x14021c749  call    cs:__imp_ObQueryNameInfo
0x14021c750  nop     dword ptr [rax+rax+00h]
0x14021c755  add     rax, 10h
0x14021c759  jmp     short loc_14021C760
0x14021c75b  mov     eax, 8
0x14021c760  mov     rbx, [rax]
0x14021c763  jmp     short loc_14021C767
0x14021c765  xor     ebx, ebx
0x14021c767  call    cs:__imp_W32GetUserSessionState
0x14021c76e  nop     dword ptr [rax+rax+00h]
0x14021c773  mov     qword ptr [rsp+0E0h+var_A0], rbx
0x14021c778  lea     rcx, WPP_8482796ea87931402564603ebe19074e_Traceguids
0x14021c77f  mov     [rsp+0E0h+var_A8], rcx
0x14021c784  mov     r8b, r15b
0x14021c787  mov     rcx, cs:WPP_GLOBAL_Control
0x14021c78e  mov     dl, r14b
0x14021c791  mov     r9, [rax+10E20h]
0x14021c798  mov     word ptr [rsp+0E0h+Handle], 1Bh
0x14021c79f  mov     dword ptr [rsp+0E0h+AccessMode], 3
0x14021c7a7  mov     rcx, [rcx+18h]
0x14021c7ab  mov     byte ptr [rsp+0E0h+ObjectType], 4
0x14021c7b0  call    WPP_RECORDER_AND_TRACE_SF_S
0x14021c7b5  xor     r15d, r15d
0x14021c7b8  jmp     short loc_14021C7C1
0x14021c7ba  lea     r12, WPP_GLOBAL_Control
0x14021c7c1  mov     r14, gs:188h
0x14021c7ca  mov     [rbp+57h+Thread], r14
0x14021c7ce  call    cs:__imp_W32GetUserSessionState
0x14021c7d5  nop     dword ptr [rax+rax+00h]
0x14021c7da  cmp     rdi, [rax+0F520h]
0x14021c7e1  jz      short loc_14021C84B
0x14021c7e3  mov     rcx, r14; Thread
0x14021c7e6  call    cs:__imp_PsIsSystemThread
0x14021c7ed  nop     dword ptr [rax+rax+00h]
0x14021c7f2  test    al, al
0x14021c7f4  jnz     short loc_14021C84B
0x14021c7f6  call    cs:__imp_W32GetUserSessionState
0x14021c7fd  nop     dword ptr [rax+rax+00h]
0x14021c802  cmp     rdi, [rax+0F518h]
0x14021c809  jz      short loc_14021C84B
0x14021c80b  mov     eax, [r13+20h]
0x14021c80f  test    sil, al
0x14021c812  jz      short loc_14021C84B
0x14021c814  test    [rbp+57h+arg_10], 2
0x14021c818  jnz     short loc_14021C84B
0x14021c81a  call    cs:__imp_W32GetUserSessionState
0x14021c821  nop     dword ptr [rax+rax+00h]
0x14021c826  mov     rcx, r14; Thread
0x14021c829  mov     rbx, [rax+0F750h]
0x14021c830  call    cs:__imp_PsGetThreadProcessId
0x14021c837  nop     dword ptr [rax+rax+00h]
0x14021c83c  cmp     rax, rbx
0x14021c83f  jz      short loc_14021C84B
0x14021c841  mov     eax, 0C0000022h
0x14021c846  jmp     loc_14021D417
0x14021c84b  call    cs:__imp_W32GetUserSessionState
0x14021c852  nop     dword ptr [rax+rax+00h]
0x14021c857  cmp     [rax+0F488h], r15d
0x14021c85e  jz      loc_14021C938
0x14021c864  call    cs:__imp_W32GetUserSessionState
0x14021c86b  nop     dword ptr [rax+rax+00h]
0x14021c870  cmp     [rax+0F520h], r15
0x14021c877  jz      short loc_14021C892
0x14021c879  call    cs:__imp_W32GetUserSessionState
0x14021c880  nop     dword ptr [rax+rax+00h]
0x14021c885  cmp     rdi, [rax+0F520h]
0x14021c88c  jz      loc_14021C938
0x14021c892  mov     rcx, cs:WPP_GLOBAL_Control
0x14021c899  cmp     rcx, r12
0x14021c89c  jz      short loc_14021C8AB
0x14021c89e  mov     eax, [rcx+2Ch]
0x14021c8a1  test    al, al
0x14021c8a3  jns     short loc_14021C8AB
0x14021c8a5  cmp     byte ptr [rcx+29h], 4
0x14021c8a9  jnb     short loc_14021C8AE
0x14021c8ab  mov     sil, r15b
0x14021c8ae  lea     rax, WPP_RECORDER_INITIALIZED
0x14021c8b5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14021c8bc  setnz   bl
0x14021c8bf  test    sil, sil
0x14021c8c2  jnz     short loc_14021C8C8
0x14021c8c4  test    bl, bl
0x14021c8c6  jz      short loc_14021C911
0x14021c8c8  call    cs:__imp_W32GetUserSessionState
0x14021c8cf  nop     dword ptr [rax+rax+00h]
0x14021c8d4  lea     rcx, WPP_8482796ea87931402564603ebe19074e_Traceguids
0x14021c8db  mov     r8b, bl
0x14021c8de  mov     [rsp+0E0h+var_A8], rcx
0x14021c8e3  mov     dl, sil
0x14021c8e6  mov     rcx, cs:WPP_GLOBAL_Control
0x14021c8ed  mov     r9, [rax+10E20h]
0x14021c8f4  mov     word ptr [rsp+0E0h+Handle], 1Ch
0x14021c8fb  mov     dword ptr [rsp+0E0h+AccessMode], 8
0x14021c903  mov     rcx, [rcx+18h]
0x14021c907  mov     byte ptr [rsp+0E0h+ObjectType], 4
0x14021c90c  call    WPP_RECORDER_AND_TRACE_SF_
0x14021c911  call    cs:__imp_W32GetUserSessionState
0x14021c918  nop     dword ptr [rax+rax+00h]
0x14021c91d  mov     rdx, rdi
0x14021c920  lea     rcx, [rax+4B18h]
0x14021c927  call    cs:__imp_LockObjectAssignment
0x14021c92e  nop     dword ptr [rax+rax+00h]
0x14021c933  jmp     loc_14021C596
0x14021c938  mov     rdx, rdi
0x14021c93b  lea     rcx, [rbp+57h+var_48]
0x14021c93f  mov     r12d, r15d
0x14021c942  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@PEAUtagDESKTOP@@@Z; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(tagDESKTOP *)
0x14021c947  lea     rax, [rbp+57h+var_80]
0x14021c94b  mov     r9d, 1F0003h; DesiredAccess
0x14021c951  mov     [rsp+0E0h+Handle], rax; Handle
0x14021c956  xor     r8d, r8d; PassedAccessState
0x14021c959  mov     rax, cs:ExDesktopObjectType
0x14021c960  mov     edx, 200h; HandleAttributes
0x14021c965  mov     [rsp+0E0h+AccessMode], r15b; AccessMode
0x14021c96a  mov     rcx, [rax]
0x14021c96d  mov     [rsp+0E0h+ObjectType], rcx; ObjectType
0x14021c972  mov     rcx, rdi; Object
0x14021c975  call    cs:__imp_ObOpenObjectByPointer
0x14021c97c  nop     dword ptr [rax+rax+00h]
0x14021c981  mov     rbx, [rbp+57h+var_80]
0x14021c985  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14021c98a  mov     r14, [rbp+57h+BugCheckParameter3]
0x14021c98e  mov     rcx, [rax+178h]
0x14021c995  mov     [rbp+57h+var_60], rcx
0x14021c999  lea     rcx, [rbp+57h+var_60]
0x14021c99d  mov     [rax+178h], rcx
0x14021c9a4  lea     rax, ?AllowDesktopDestruction@@YAXPEAX@Z; AllowDesktopDestruction(void *)
0x14021c9ab  mov     [rbp+57h+var_50], rax
0x14021c9af  mov     [rbp+57h+var_58], rbx
0x14021c9b3  cmp     [r14+1E8h], r15
0x14021c9ba  jz      short loc_14021C9D4
0x14021c9bc  call    zzzDesktopSwitchSideEffects
0x14021c9c1  mov     ecx, esi
0x14021c9c3  call    ?ResetPointerDevices@@YAXW4ResetPointerDevicesStrategy@@@Z; ResetPointerDevices(ResetPointerDevicesStrategy)
0x14021c9c8  call    cs:__imp_W32GetUserSessionState
0x14021c9cf  nop     dword ptr [rax+rax+00h]
0x14021c9d4  call    cs:__imp_W32GetUserSessionState
0x14021c9db  nop     dword ptr [rax+rax+00h]
0x14021c9e0  cmp     [rax+4B10h], r15
0x14021c9e7  jz      short loc_14021CA68
0x14021c9e9  call    cs:__imp_W32GetUserSessionState
0x14021c9f0  nop     dword ptr [rax+rax+00h]
0x14021c9f5  mov     rcx, [rax+4B10h]
0x14021c9fc  mov     rax, [rcx+8]
0x14021ca00  cmp     [rax+18h], r15
0x14021ca04  jz      short loc_14021CA68
0x14021ca06  call    cs:__imp_W32GetUserSessionState
0x14021ca0d  nop     dword ptr [rax+rax+00h]
0x14021ca12  cmp     [rax+4A18h], r15
0x14021ca19  jz      short loc_14021CA68
0x14021ca1b  call    cs:__imp_W32GetUserSessionState
0x14021ca22  nop     dword ptr [rax+rax+00h]
0x14021ca27  mov     rbx, [rax+4B10h]
0x14021ca2e  call    cs:__imp_W32GetUserSessionState
0x14021ca35  nop     dword ptr [rax+rax+00h]
0x14021ca3a  lea     rcx, [rbx+58h]
0x14021ca3e  mov     rdx, [rax+4A18h]
0x14021ca45  mov     rdx, [rdx+80h]
0x14021ca4c  call    cs:__imp_?Set@tagUNIQUE_WINDOW_HANDLE@@QEAAXPEBUtagWND@@@Z; tagUNIQUE_WINDOW_HANDLE::Set(tagWND const *)
0x14021ca53  nop     dword ptr [rax+rax+00h]
0x14021ca58  mov     r8d, 20h ; ' '
0x14021ca5e  mov     rdx, r14
0x14021ca61  xor     ecx, ecx
0x14021ca63  call    ?xxxSetForegroundWindow2@@YAHPEAUtagWND@@PEAUtagTHREADINFO@@W4SetForegroundBehaviors@@@Z; xxxSetForegroundWindow2(tagWND *,tagTHREADINFO *,SetForegroundBehaviors)
  ... truncated ...
```
