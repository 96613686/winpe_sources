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
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v8; // rdx
  struct MOVESIZEDATA *v9; // rcx
  char v10; // si
  char v11; // bl
  bool v12; // r12
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 UserSessionState; // rax
  int v16; // r8d
  int v17; // edx
  __int64 v18; // rdx
  struct MOVESIZEDATA *v19; // rcx
  char v20; // r14
  bool v21; // r15
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rbx
  __int64 v26; // rax
  int v27; // r8d
  int v28; // edx
  struct _KTHREAD *CurrentThread; // r14
  __int64 v30; // rdx
  __int64 v31; // rcx
  HANDLE v32; // rbx
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rcx
  struct MOVESIZEDATA *v37; // rcx
  bool v38; // bl
  __int64 v39; // rax
  int v40; // r8d
  int v41; // edx
  __int64 v42; // rax
  int v43; // r12d
  void *v44; // rbx
  struct tagTHREADINFO *v45; // rax
  __int64 v46; // rdx
  ULONG_PTR v47; // r14
  _QWORD *v48; // rcx
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // rdx
  __int64 v52; // rcx
  __int64 v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // rbx
  __int64 v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // rax
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // rdx
  __int64 v64; // rcx
  __int64 v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // rax
  __int64 v68; // rdx
  __int64 v69; // rcx
  __int64 v70; // rax
  __int64 v71; // rdx
  __int64 v72; // rcx
  __int64 v73; // rax
  struct tagEDGY_DATA *v74; // rdx
  __int64 v75; // rax
  __int64 v76; // rdx
  __int64 v77; // rcx
  __int64 v78; // rdx
  __int64 v79; // rcx
  __int64 v80; // rax
  __int64 v81; // rdx
  __int64 v82; // rcx
  __int64 v83; // rdx
  __int64 v84; // rcx
  __int64 v85; // rdx
  __int64 v86; // rcx
  __int64 v87; // rax
  __int64 v88; // rdx
  __int64 v89; // rcx
  __int64 v90; // rax
  __int64 v91; // rbx
  __int64 v92; // rdx
  __int64 v93; // rcx
  __int64 v94; // rax
  __int64 v95; // rbx
  __int64 v96; // rdx
  __int64 v97; // rcx
  __int64 v98; // rax
  __int64 v99; // rdx
  __int64 v100; // rcx
  __int64 v101; // rdx
  __int64 v102; // rcx
  __int64 v103; // rax
  __int64 v104; // rax
  __int64 v105; // rdx
  __int64 v106; // rcx
  __int64 **v107; // rax
  __int64 v108; // rbx
  __int64 v109; // rdx
  struct tagWND **v110; // rcx
  __int64 v111; // rdx
  __int64 v112; // rax
  __int64 v113; // rdx
  int v114; // r14d
  __int64 v115; // rcx
  __int64 v116; // rdx
  __int64 v117; // rcx
  __int64 v118; // rdx
  __int64 v119; // r8
  __int64 v120; // rcx
  void *v121; // rax
  __int64 **v122; // rax
  __int64 v123; // r15
  BOOL v124; // r14d
  _QWORD *v125; // rax
  unsigned int v126; // ebx
  __int64 v127; // rax
  __int64 v128; // rcx
  ULONG_PTR v129; // r13
  __int64 v130; // rdx
  __int64 v131; // rcx
  int v132; // r15d
  int v133; // ebx
  __int64 v134; // rax
  __int64 v135; // rdx
  __int64 v136; // rcx
  struct tagWND *i; // rbx
  __int64 v138; // rcx
  __int64 v139; // rcx
  __int64 v140; // rdx
  __int64 v141; // rcx
  __int64 v142; // rdx
  __int64 v143; // rcx
  __int64 v144; // rdx
  __int64 v145; // rcx
  __int64 v146; // rax
  __int64 v147; // rdx
  __int64 v148; // rcx
  __int64 v149; // rdx
  __int64 v150; // rcx
  HANDLE v151; // rbx
  int v152; // eax
  __int64 v153; // rcx
  bool v154; // bl
  __int64 v155; // rax
  int v156; // r8d
  int v157; // edx
  ULONG_PTR v158; // [rsp+58h] [rbp-39h] BYREF
  __int64 v159; // [rsp+60h] [rbp-31h]
  void *Handle; // [rsp+68h] [rbp-29h] BYREF
  ULONG_PTR BugCheckParameter3[2]; // [rsp+70h] [rbp-21h] BYREF
  PETHREAD Thread; // [rsp+80h] [rbp-11h]
  _QWORD v163[2]; // [rsp+88h] [rbp-9h] BYREF
  __int64 v164; // [rsp+98h] [rbp+7h]
  _BYTE v165[16]; // [rsp+A0h] [rbp+Fh] BYREF
  __int64 v166; // [rsp+B0h] [rbp+1Fh]
  __int64 v167; // [rsp+100h] [rbp+6Fh]

  BugCheckParameter3[0] = (ULONG_PTR)PtiCurrent();
  Handle = 0;
  if ( !a2 )
    return 3221225473LL;
  if ( a2 == *(_QWORD *)(W32GetUserSessionState(v6, v5) + 19216) )
    return 0;
  if ( (*(_DWORD *)(a2 + 48) & 8) != 0 )
    return 3221225485LL;
  if ( !a1 )
    a1 = *(_QWORD *)(a2 + 40);
  LOBYTE(v8) = 4;
  if ( (*(_DWORD *)(a1 + 32) & 4) != 0 )
    return 3221225485LL;
  v167 = *(_QWORD *)(a1 + 24);
  v9 = WPP_GLOBAL_Control;
  v10 = 1;
  if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) == 0
    || (v11 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v11 = 0;
  }
  v12 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v11 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    if ( ObQueryNameInfo(a2) && ObQueryNameInfo(a2) != -8 && ObQueryNameInfo(a2) )
      ObQueryNameInfo(a2);
    UserSessionState = W32GetUserSessionState(v14, v13);
    LOBYTE(v16) = v12;
    LOBYTE(v17) = v11;
    WPP_RECORDER_AND_TRACE_SF_SL(*((_QWORD *)WPP_GLOBAL_Control + 3), v17, v16, *(_QWORD *)(UserSessionState + 69152));
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v9, v8) + 19216) )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) == 0
      || (v20 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
    {
      v20 = 0;
    }
    v21 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v20 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      if ( !ObQueryNameInfo(a2) || ObQueryNameInfo(a2) == -8 )
      {
        v25 = 0;
      }
      else
      {
        if ( ObQueryNameInfo(a2) )
          v24 = ObQueryNameInfo(a2) + 16;
        else
          v24 = 8;
        v25 = *(_QWORD *)v24;
      }
      v26 = W32GetUserSessionState(v23, v22);
      LOBYTE(v27) = v21;
      LOBYTE(v28) = v20;
      WPP_RECORDER_AND_TRACE_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v28,
        v27,
        *(_QWORD *)(v26 + 69152),
        4,
        3,
        27,
        (__int64)WPP_8482796ea87931402564603ebe19074e_Traceguids,
        v25);
    }
  }
  CurrentThread = KeGetCurrentThread();
  Thread = CurrentThread;
  if ( a2 != *(_QWORD *)(W32GetUserSessionState(v19, v18) + 62752)
    && !PsIsSystemThread(CurrentThread)
    && a2 != *(_QWORD *)(W32GetUserSessionState(v31, v30) + 62744)
    && (*(_DWORD *)(a1 + 32) & 1) != 0
    && (a3 & 2) == 0 )
  {
    v32 = *(HANDLE *)(W32GetUserSessionState(v31, v30) + 63312);
    if ( PsGetThreadProcessId(CurrentThread) != v32 )
      return 3221225506LL;
  }
  if ( *(_DWORD *)(W32GetUserSessionState(v31, v30) + 62600)
    && (!*(_QWORD *)(W32GetUserSessionState(v34, v33) + 62752)
     || a2 != *(_QWORD *)(W32GetUserSessionState(v36, v35) + 62752)) )
  {
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
    {
      v10 = 0;
    }
    v38 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v10 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v39 = W32GetUserSessionState(WPP_GLOBAL_Control, v35);
      LOBYTE(v40) = v38;
      LOBYTE(v41) = v10;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v41,
        v40,
        *(_QWORD *)(v39 + 69152),
        4,
        8,
        28,
        (__int64)WPP_8482796ea87931402564603ebe19074e_Traceguids);
    }
    v42 = W32GetUserSessionState(v37, v35);
    LockObjectAssignment(v42 + 19224, a2);
    return 0;
  }
  v43 = 0;
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(v165, a2);
  ObOpenObjectByPointer((PVOID)a2, 0x200u, 0, 0x1F0003u, (POBJECT_TYPE)ExDesktopObjectType, 0, &Handle);
  v44 = Handle;
  v45 = PtiCurrent();
  v47 = BugCheckParameter3[0];
  v163[0] = *((_QWORD *)v45 + 47);
  v48 = v163;
  *((_QWORD *)v45 + 47) = v163;
  v164 = (__int64)AllowDesktopDestruction;
  v163[1] = v44;
  if ( *(_QWORD *)(v47 + 488) )
  {
    zzzDesktopSwitchSideEffects();
    ResetPointerDevices(1);
    W32GetUserSessionState(v50, v49);
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v48, v46) + 19216) )
  {
    v54 = *(_QWORD *)(W32GetUserSessionState(v52, v51) + 19216);
    if ( *(_QWORD *)(*(_QWORD *)(v54 + 8) + 24LL) )
    {
      if ( *(_QWORD *)(W32GetUserSessionState(v54, v53) + 18968) )
      {
        v57 = *(_QWORD *)(W32GetUserSessionState(v56, v55) + 19216);
        v60 = W32GetUserSessionState(v59, v58);
        tagUNIQUE_WINDOW_HANDLE::Set(
          (tagUNIQUE_WINDOW_HANDLE *)(v57 + 88),
          *(const struct tagWND **)(*(_QWORD *)(v60 + 18968) + 128LL));
        xxxSetForegroundWindow2(0, v47, 0x20u);
      }
    }
  }
  UpdateKeyboardStateOnDesktopSwitch(1);
  if ( *(_QWORD *)(W32GetUserSessionState(v62, v61) + 19216) )
  {
    v64 = **(_QWORD **)(*(_QWORD *)(W32GetUserSessionState(v64, v63) + 19216) + 8LL);
    if ( (*(_DWORD *)(v64 + 64) & 1) != 0 )
    {
      if ( *(_QWORD *)(W32GetUserSessionState(v64, v63) + 42800) )
        StopFade();
      v67 = W32GetUserSessionState(v66, v65);
      bSetDevDragRect(*(HDEV *)(*(_QWORD *)(v67 + 56744) + 40LL));
      v70 = W32GetUserSessionState(v69, v68);
      ComposeWindow(*(struct tagWND **)(*(_QWORD *)(*(_QWORD *)(v70 + 19216) + 8LL) + 24LL));
      GreLockDynamicModeChange();
      GreUnlockDynamicModeChange();
      v64 = *(_QWORD *)(a1 + 88);
      if ( v64 )
        EraseBitmap();
      v43 = 1;
    }
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v64, v63) + 19216) )
  {
    v72 = *(_QWORD *)(W32GetUserSessionState(v72, v71) + 19216);
    if ( *(_QWORD *)(v72 + 248) )
    {
      v73 = W32GetUserSessionState(v72, v71);
      Edgy::FreeEdgyFrameData(*(Edgy **)(*(_QWORD *)(v73 + 19216) + 248LL), v74);
    }
  }
  v75 = W32GetUserSessionState(v72, v71);
  ResetWindowKeyProcessing(*(struct tagDESKTOP **)(v75 + 19216));
  if ( *(_QWORD *)(W32GetUserSessionState(v77, v76) + 19216) )
  {
    v80 = W32GetUserSessionState(v79, v78);
    *(_DWORD *)(*(_QWORD *)(v80 + 19216) + 48LL) |= 0x1000u;
  }
  if ( (unsigned int)Feature_PreserveActiveHklInDesktopSwitching__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( a2 == *(_QWORD *)(W32GetUserSessionState(v82, v81) + 62744) )
    {
      if ( *(_QWORD *)(W32GetUserSessionState(v84, v83) + 14184) )
      {
        v87 = W32GetUserSessionState(v86, v85);
        if ( (*(_BYTE *)(_HMPheFromObject(*(_QWORD *)(v87 + 14184)) + 25) & 1) == 0 )
        {
          v159 = *(_QWORD *)(W32GetUserSessionState(v86, v85) + 14184);
          v158 = W32GetUserSessionState(v89, v88) + 14192;
          HMAssignmentLock(&v158, 0);
        }
      }
      if ( *(_QWORD *)(W32GetUserSessionState(v86, v85) + 14216) )
      {
        v90 = W32GetUserSessionState(v82, v81);
        if ( (*(_BYTE *)(_HMPheFromObject(*(_QWORD *)(v90 + 14216)) + 25) & 1) == 0 )
        {
          v91 = *(_QWORD *)(W32GetUserSessionState(v82, v81) + 14216);
          v94 = W32GetUserSessionState(v93, v92);
          v159 = v91;
          v158 = v94 + 14184;
          HMAssignmentLock(&v158, 0);
        }
      }
    }
    else
    {
      v95 = *(_QWORD *)(W32GetUserSessionState(v84, v83) + 19216);
      if ( v95 == *(_QWORD *)(W32GetUserSessionState(v97, v96) + 62744) )
      {
        if ( *(_QWORD *)(W32GetUserSessionState(v82, v81) + 14192) )
        {
          v98 = W32GetUserSessionState(v82, v81);
          if ( (*(_BYTE *)(_HMPheFromObject(*(_QWORD *)(v98 + 14192)) + 25) & 1) == 0 )
          {
            v159 = *(_QWORD *)(W32GetUserSessionState(v82, v81) + 14192);
            v158 = W32GetUserSessionState(v100, v99) + 14184;
            HMAssignmentLock(&v158, 0);
            v103 = W32GetUserSessionState(v102, v101);
            HMAssignmentUnlock(v103 + 14192);
          }
        }
      }
    }
  }
  v104 = W32GetUserSessionState(v82, v81);
  LockObjectAssignment(v104 + 19216, a2);
  v107 = *(__int64 ***)(*(_QWORD *)(W32GetUserSessionState(v106, v105) + 19216) + 8LL);
  v108 = **v107;
  *(_QWORD *)(W32GetUserSessionState(*v107, v109) + 18760) = v108;
  SynchronizeContext();
  UpdateInUserCritUpdatedPointerRedirectedGlobalsOnDesktopSwitch();
  CitDesktopSwitch();
  v110 = *(struct tagWND ***)(a2 + 8);
  v111 = *((unsigned int *)*v110 + 16);
  if ( (v111 & 1) != 0 )
    ComposeWindow(v110[3]);
  v112 = W32GetUserSessionState(v110, v111);
  v114 = zzzSetDesktop(*(_QWORD *)(v112 + 18752), a2, 0);
  if ( v114 >= 0 )
  {
    if ( *(_QWORD *)(*(_QWORD *)(v167 + 16) + 464LL) != *(_QWORD *)(v167 + 24) )
    {
      AllocQueue(0);
      tagQ::zzzAttachToQueue(*(tagQ **)(v167 + 24), *(struct tagTHREADINFO **)(v167 + 16), 0, 0);
    }
    v114 = zzzSetDesktop(*(_QWORD *)(v167 + 16), a2, 0);
    if ( v114 >= 0 )
    {
      v117 = *(_QWORD *)(W32GetUserSessionState(v115, v113) + 19216);
      if ( *(_QWORD *)(*(_QWORD *)(v167 + 16) + 488LL) != v117 )
        MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4202);
      if ( a2 != *(_QWORD *)(W32GetUserSessionState(v117, v116) + 19216) )
        MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4203);
      v120 = **(_QWORD **)(a2 + 8);
      if ( (*(_DWORD *)(v120 + 64) & 1) != 0 )
      {
        UserSessionSwitchLeaveCrit(v120, v118, v119);
        v121 = (void *)UserReferenceDwmApiPort();
        DwmSyncDesktopSwitch(v121);
        EnterCrit(1, 0);
      }
      if ( !gbIgnoreStressedOutStuff && a2 != *(_QWORD *)(W32GetUserSessionState(v120, v118) + 19216) )
        MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4217);
      v122 = *(__int64 ***)(a2 + 8);
      v123 = **v122;
      v124 = v43
          && (*(_DWORD *)(**(_QWORD **)(*(_QWORD *)(W32GetUserSessionState(*v122, v118) + 19216) + 8LL) + 64LL) & 1) != 0;
      v125 = *(_QWORD **)(a2 + 8);
      v126 = *(_DWORD *)(*v125 + 64LL) & 1;
      v127 = W32GetUserSessionState(*v125, v118);
      v114 = GreDesktopSwitch(*(_QWORD *)(*(_QWORD *)(v127 + 56744) + 40LL), v126, v124, v123);
      if ( v114 >= 0 )
      {
        if ( v43 == (*(_DWORD *)(**(_QWORD **)(*(_QWORD *)(W32GetUserSessionState(v128, v113) + 19216) + 8LL) + 64LL) & 1) )
          ResetCursorPointerInternal();
        else
          zzzEnableDwmPointerSupport(*(_DWORD *)(**(_QWORD **)(a2 + 8) + 64LL) & 1, 0);
        v129 = BugCheckParameter3[0];
        Win32HM_LockIntoThread<1>(BugCheckParameter3[0], *(_QWORD *)(*(_QWORD *)(a2 + 8) + 24LL), &v158);
        GreLddmProcessDesktopSwitch();
        v131 = **(_QWORD **)(a2 + 8);
        v132 = 4 * (*(_DWORD *)(v131 + 64) & 1);
        if ( !v43
          || (v133 = 9,
              v131 = **(_QWORD **)(*(_QWORD *)(W32GetUserSessionState(v131, v130) + 19216) + 8LL),
              (*(_DWORD *)(v131 + 64) & 1) == 0) )
        {
          v133 = 1;
        }
        v134 = W32GetUserSessionState(v131, v130);
        GreSuspendDirectDraw(*(_QWORD *)(*(_QWORD *)(v134 + 56744) + 40LL), v132 | (unsigned int)v133, 0);
        xxxSetWindowPos(*(struct tagWND **)(*(_QWORD *)(a2 + 8) + 24LL), 0, 0, 339);
        if ( !gbIgnoreStressedOutStuff && a2 != *(_QWORD *)(W32GetUserSessionState(v136, v135) + 19216) )
          MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4283);
        GreResumeDirectDraw(0);
        i = tagUNIQUE_WINDOW_HANDLE::Get((tagUNIQUE_WINDOW_HANDLE *)(a2 + 88));
        if ( !(unsigned __int8)lambda_74a3533f2c879f4574bc0a0461c8b857_::operator()(v138, i)
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
            if ( (unsigned __int8)lambda_74a3533f2c879f4574bc0a0461c8b857_::operator()(v139, i) )
              break;
          }
        }
        Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)&v158);
        tagUNIQUE_WINDOW_HANDLE::Clear((tagUNIQUE_WINDOW_HANDLE *)(a2 + 88));
        UpdateKeyboardStateOnDesktopSwitch(0);
        if ( i )
        {
          if ( !gbIgnoreStressedOutStuff
            && *(_QWORD *)(*((_QWORD *)i + 2) + 488LL) != *(_QWORD *)(W32GetUserSessionState(v141, v140) + 19216) )
          {
            MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4368);
          }
          Win32HM_LockIntoThread<0>(v129, i, BugCheckParameter3);
          xxxSetForegroundWindowWithOptions(i, 31, 32, 0);
          Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)BugCheckParameter3);
        }
        else
        {
          xxxSetForegroundWindow2(0, 0, 0x20u);
        }
        v145 = *(_QWORD *)(W32GetUserSessionState(v143, v142) + 19160);
        if ( v145 )
          IPostQuitMessage(v145, 0);
        v146 = W32GetUserSessionState(v145, v144);
        KePulseEvent(*(PRKEVENT *)(v146 + 62736), 1, 0);
        xxxWindowEvent(0x20u, 0, 0, 0, 6);
        zzzUpdateCursorImage();
        if ( a2 == *(_QWORD *)(W32GetUserSessionState(v148, v147) + 62744) )
        {
          v151 = *(HANDLE *)(W32GetUserSessionState(v150, v149) + 63312);
          if ( PsGetThreadProcessId(Thread) == v151 && (*(_DWORD *)(*(_QWORD *)(a2 + 40) + 32LL) & 1) != 0 )
            SetTimerCoalescingTolerance(3);
        }
        v152 = *(_DWORD *)(a2 + 48);
        if ( (v152 & 0x20) != 0 )
        {
          v153 = *(_QWORD *)(a2 + 8);
          if ( v153 )
          {
            if ( *(_QWORD *)(v153 + 24) )
            {
              *(_DWORD *)(a2 + 48) = v152 & 0xFFFFFFDF;
              xxxBroadcastDisplaySettingsChange(a2, 1, 0, 0);
            }
          }
        }
        DrvOcclusionStateChangeNotify();
        xxxRefreshDisplayOrientation();
      }
    }
  }
  if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
  {
    v10 = 0;
  }
  v154 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v10 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v155 = W32GetUserSessionState(WPP_GLOBAL_Control, v113);
    LOBYTE(v156) = v154;
    LOBYTE(v157) = v10;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v157,
      v156,
      *(_QWORD *)(v155 + 69152),
      4,
      3,
      29,
      (__int64)WPP_8482796ea87931402564603ebe19074e_Traceguids,
      v114);
  }
  PopAndFreeW32ThreadLock(v163);
  v164 = -1;
  if ( v166 != -1 )
    PopAndFreeW32ThreadLock(v165);
  return (unsigned int)v114;
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
