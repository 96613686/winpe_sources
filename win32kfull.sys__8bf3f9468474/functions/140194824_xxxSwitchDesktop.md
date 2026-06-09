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
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  struct MOVESIZEDATA *v13; // rcx
  char v14; // si
  char v15; // bl
  bool v16; // r12
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 UserSessionState; // rax
  int v22; // r8d
  int v23; // edx
  __int64 v24; // rdx
  struct MOVESIZEDATA *v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  char v28; // r14
  bool v29; // r15
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // rax
  __int64 v35; // rbx
  __int64 v36; // rax
  int v37; // r8d
  int v38; // edx
  struct _KTHREAD *CurrentThread; // r14
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // r8
  __int64 v43; // r9
  HANDLE v44; // rbx
  __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // r8
  __int64 v48; // r9
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // r8
  __int64 v52; // r9
  struct MOVESIZEDATA *v53; // rcx
  bool v54; // bl
  __int64 v55; // rax
  int v56; // r8d
  int v57; // edx
  __int64 v58; // rax
  int v59; // r12d
  void *v60; // rbx
  struct tagTHREADINFO *v61; // rax
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // r9
  ULONG_PTR v65; // r14
  _QWORD *v66; // rcx
  __int64 v67; // rdx
  __int64 v68; // rcx
  __int64 v69; // r8
  __int64 v70; // r9
  __int64 v71; // rdx
  __int64 v72; // rcx
  __int64 v73; // r8
  __int64 v74; // r9
  __int64 v75; // rdx
  __int64 v76; // rcx
  __int64 v77; // r8
  __int64 v78; // r9
  __int64 v79; // rdx
  __int64 v80; // rcx
  __int64 v81; // r8
  __int64 v82; // r9
  __int64 v83; // rbx
  __int64 v84; // rdx
  __int64 v85; // rcx
  __int64 v86; // r8
  __int64 v87; // r9
  __int64 v88; // rax
  __int64 v89; // rdx
  __int64 v90; // rcx
  __int64 v91; // r8
  __int64 v92; // r9
  __int64 v93; // rdx
  __int64 v94; // rcx
  __int64 v95; // r8
  __int64 v96; // r9
  __int64 v97; // rdx
  __int64 v98; // rcx
  __int64 v99; // r8
  __int64 v100; // r9
  __int64 v101; // rax
  __int64 v102; // rdx
  __int64 v103; // rcx
  __int64 v104; // r8
  __int64 v105; // r9
  __int64 v106; // rax
  __int64 v107; // rdx
  __int64 v108; // rcx
  __int64 v109; // r8
  __int64 v110; // r9
  __int64 v111; // rax
  struct tagEDGY_DATA *v112; // rdx
  __int64 v113; // rax
  __int64 v114; // rdx
  __int64 v115; // rcx
  __int64 v116; // r8
  __int64 v117; // r9
  __int64 v118; // rdx
  __int64 v119; // rcx
  __int64 v120; // r8
  __int64 v121; // r9
  __int64 v122; // rax
  __int64 v123; // rdx
  __int64 v124; // rcx
  __int64 v125; // r8
  __int64 v126; // r9
  __int64 v127; // rdx
  __int64 v128; // rcx
  __int64 v129; // r8
  __int64 v130; // r9
  __int64 v131; // rdx
  __int64 v132; // rcx
  __int64 v133; // r8
  __int64 v134; // r9
  __int64 v135; // rax
  __int64 v136; // rdx
  __int64 v137; // rcx
  __int64 v138; // r8
  __int64 v139; // r9
  __int64 v140; // rax
  __int64 v141; // rbx
  __int64 v142; // rdx
  __int64 v143; // rcx
  __int64 v144; // r8
  __int64 v145; // r9
  __int64 v146; // rax
  __int64 v147; // rbx
  __int64 v148; // rdx
  __int64 v149; // rcx
  __int64 v150; // r8
  __int64 v151; // r9
  __int64 v152; // rax
  __int64 v153; // rdx
  __int64 v154; // rcx
  __int64 v155; // r8
  __int64 v156; // r9
  __int64 v157; // rdx
  __int64 v158; // rcx
  __int64 v159; // r8
  __int64 v160; // r9
  __int64 v161; // rax
  __int64 v162; // rax
  __int64 v163; // rdx
  __int64 v164; // rcx
  __int64 v165; // r8
  __int64 v166; // r9
  __int64 **v167; // rax
  __int64 v168; // rbx
  __int64 v169; // rdx
  __int64 v170; // r8
  __int64 v171; // r9
  __int64 v172; // r8
  __int64 v173; // r9
  struct tagWND **v174; // rcx
  __int64 v175; // rdx
  __int64 v176; // rax
  __int64 v177; // rdx
  __int64 v178; // r8
  __int64 v179; // r9
  int v180; // r14d
  __int64 v181; // rcx
  __int64 v182; // rdx
  __int64 v183; // rcx
  __int64 v184; // r8
  __int64 v185; // r9
  __int64 v186; // rdx
  __int64 v187; // r8
  __int64 v188; // r9
  __int64 v189; // rcx
  void *v190; // rax
  __int64 **v191; // rax
  __int64 v192; // r15
  BOOL v193; // r14d
  _QWORD *v194; // rax
  unsigned int v195; // ebx
  __int64 v196; // rax
  __int64 v197; // rcx
  ULONG_PTR v198; // r13
  __int64 v199; // rdx
  __int64 v200; // r8
  __int64 v201; // r9
  __int64 v202; // rcx
  int v203; // r15d
  int v204; // ebx
  __int64 v205; // rax
  __int64 v206; // rdx
  __int64 v207; // rcx
  __int64 v208; // r8
  __int64 v209; // r9
  struct tagWND *i; // rbx
  __int64 v211; // rcx
  __int64 v212; // rcx
  __int64 v213; // rdx
  __int64 v214; // rcx
  __int64 v215; // r8
  __int64 v216; // r9
  __int64 v217; // rdx
  __int64 v218; // rcx
  __int64 v219; // r8
  __int64 v220; // r9
  __int64 v221; // rdx
  __int64 v222; // rcx
  __int64 v223; // r8
  __int64 v224; // r9
  __int64 v225; // rax
  __int64 v226; // rdx
  __int64 v227; // rcx
  __int64 v228; // r8
  __int64 v229; // r9
  __int64 v230; // rdx
  __int64 v231; // rcx
  __int64 v232; // r8
  __int64 v233; // r9
  HANDLE v234; // rbx
  int v235; // eax
  __int64 v236; // rcx
  bool v237; // bl
  __int64 v238; // rax
  int v239; // r8d
  int v240; // edx
  ULONG_PTR v241; // [rsp+58h] [rbp-39h] BYREF
  __int64 v242; // [rsp+60h] [rbp-31h]
  void *Handle; // [rsp+68h] [rbp-29h] BYREF
  ULONG_PTR BugCheckParameter3[2]; // [rsp+70h] [rbp-21h] BYREF
  PETHREAD Thread; // [rsp+80h] [rbp-11h]
  _QWORD v246[2]; // [rsp+88h] [rbp-9h] BYREF
  __int64 v247; // [rsp+98h] [rbp+7h]
  _BYTE v248[16]; // [rsp+A0h] [rbp+Fh] BYREF
  __int64 v249; // [rsp+B0h] [rbp+1Fh]
  __int64 v250; // [rsp+100h] [rbp+6Fh]

  BugCheckParameter3[0] = (ULONG_PTR)PtiCurrent();
  Handle = 0;
  if ( !a2 )
    return 3221225473LL;
  if ( a2 == *(_QWORD *)(W32GetUserSessionState(v6, v5, v7, v8) + 19216) )
    return 0;
  if ( (*(_DWORD *)(a2 + 48) & 8) != 0 )
    return 3221225485LL;
  if ( !a1 )
    a1 = *(_QWORD *)(a2 + 40);
  LOBYTE(v10) = 4;
  if ( (*(_DWORD *)(a1 + 32) & 4) != 0 )
    return 3221225485LL;
  v250 = *(_QWORD *)(a1 + 24);
  v13 = WPP_GLOBAL_Control;
  v14 = 1;
  if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) == 0
    || (v15 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v15 = 0;
  }
  v16 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v15 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    if ( ObQueryNameInfo(a2) && ObQueryNameInfo(a2) != -8 && ObQueryNameInfo(a2) )
      ObQueryNameInfo(a2);
    UserSessionState = W32GetUserSessionState(v18, v17, v19, v20);
    LOBYTE(v22) = v16;
    LOBYTE(v23) = v15;
    WPP_RECORDER_AND_TRACE_SF_SL(*((_QWORD *)WPP_GLOBAL_Control + 3), v23, v22, *(_QWORD *)(UserSessionState + 69152));
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v13, v10, v11, v12) + 19216) )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) == 0
      || (v28 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
    {
      v28 = 0;
    }
    v29 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v28 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      if ( !ObQueryNameInfo(a2) || ObQueryNameInfo(a2) == -8 )
      {
        v35 = 0;
      }
      else
      {
        if ( ObQueryNameInfo(a2) )
          v34 = ObQueryNameInfo(a2) + 16;
        else
          v34 = 8;
        v35 = *(_QWORD *)v34;
      }
      v36 = W32GetUserSessionState(v31, v30, v32, v33);
      LOBYTE(v37) = v29;
      LOBYTE(v38) = v28;
      WPP_RECORDER_AND_TRACE_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v38,
        v37,
        *(_QWORD *)(v36 + 69152),
        4,
        3,
        27,
        (__int64)WPP_8482796ea87931402564603ebe19074e_Traceguids,
        v35);
    }
  }
  CurrentThread = KeGetCurrentThread();
  Thread = CurrentThread;
  if ( a2 != *(_QWORD *)(W32GetUserSessionState(v25, v24, v26, v27) + 62752)
    && !PsIsSystemThread(CurrentThread)
    && a2 != *(_QWORD *)(W32GetUserSessionState(v41, v40, v42, v43) + 62744)
    && (*(_DWORD *)(a1 + 32) & 1) != 0
    && (a3 & 2) == 0 )
  {
    v44 = *(HANDLE *)(W32GetUserSessionState(v41, v40, v42, v43) + 63312);
    if ( PsGetThreadProcessId(CurrentThread) != v44 )
      return 3221225506LL;
  }
  if ( *(_DWORD *)(W32GetUserSessionState(v41, v40, v42, v43) + 62600)
    && (!*(_QWORD *)(W32GetUserSessionState(v46, v45, v47, v48) + 62752)
     || a2 != *(_QWORD *)(W32GetUserSessionState(v50, v49, v51, v52) + 62752)) )
  {
    v53 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
    {
      v14 = 0;
    }
    v54 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v14 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v55 = W32GetUserSessionState(WPP_GLOBAL_Control, v49, v51, v52);
      LOBYTE(v56) = v54;
      LOBYTE(v57) = v14;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v57,
        v56,
        *(_QWORD *)(v55 + 69152),
        4,
        8,
        28,
        (__int64)WPP_8482796ea87931402564603ebe19074e_Traceguids);
    }
    v58 = W32GetUserSessionState(v53, v49, v51, v52);
    LockObjectAssignment(v58 + 19224, a2);
    return 0;
  }
  v59 = 0;
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(v248, a2);
  ObOpenObjectByPointer((PVOID)a2, 0x200u, 0, 0x1F0003u, (POBJECT_TYPE)ExDesktopObjectType, 0, &Handle);
  v60 = Handle;
  v61 = PtiCurrent();
  v65 = BugCheckParameter3[0];
  v246[0] = *((_QWORD *)v61 + 47);
  v66 = v246;
  *((_QWORD *)v61 + 47) = v246;
  v247 = (__int64)AllowDesktopDestruction;
  v246[1] = v60;
  if ( *(_QWORD *)(v65 + 488) )
  {
    zzzDesktopSwitchSideEffects();
    ResetPointerDevices(1);
    W32GetUserSessionState(v68, v67, v69, v70);
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v66, v62, v63, v64) + 19216) )
  {
    v76 = *(_QWORD *)(W32GetUserSessionState(v72, v71, v73, v74) + 19216);
    if ( *(_QWORD *)(*(_QWORD *)(v76 + 8) + 24LL) )
    {
      if ( *(_QWORD *)(W32GetUserSessionState(v76, v75, v77, v78) + 18968) )
      {
        v83 = *(_QWORD *)(W32GetUserSessionState(v80, v79, v81, v82) + 19216);
        v88 = W32GetUserSessionState(v85, v84, v86, v87);
        tagUNIQUE_WINDOW_HANDLE::Set(
          (tagUNIQUE_WINDOW_HANDLE *)(v83 + 88),
          *(const struct tagWND **)(*(_QWORD *)(v88 + 18968) + 128LL));
        xxxSetForegroundWindow2(0, v65, 0x20u);
      }
    }
  }
  UpdateKeyboardStateOnDesktopSwitch(1);
  if ( *(_QWORD *)(W32GetUserSessionState(v90, v89, v91, v92) + 19216) )
  {
    v94 = **(_QWORD **)(*(_QWORD *)(W32GetUserSessionState(v94, v93, v95, v96) + 19216) + 8LL);
    if ( (*(_DWORD *)(v94 + 64) & 1) != 0 )
    {
      if ( *(_QWORD *)(W32GetUserSessionState(v94, v93, v95, v96) + 42800) )
        StopFade();
      v101 = W32GetUserSessionState(v98, v97, v99, v100);
      bSetDevDragRect(*(HDEV *)(*(_QWORD *)(v101 + 56744) + 40LL));
      v106 = W32GetUserSessionState(v103, v102, v104, v105);
      ComposeWindow(*(struct tagWND **)(*(_QWORD *)(*(_QWORD *)(v106 + 19216) + 8LL) + 24LL));
      GreLockDynamicModeChange();
      GreUnlockDynamicModeChange();
      v94 = *(_QWORD *)(a1 + 88);
      if ( v94 )
        EraseBitmap();
      v59 = 1;
    }
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v94, v93, v95, v96) + 19216) )
  {
    v108 = *(_QWORD *)(W32GetUserSessionState(v108, v107, v109, v110) + 19216);
    if ( *(_QWORD *)(v108 + 248) )
    {
      v111 = W32GetUserSessionState(v108, v107, v109, v110);
      Edgy::FreeEdgyFrameData(*(Edgy **)(*(_QWORD *)(v111 + 19216) + 248LL), v112);
    }
  }
  v113 = W32GetUserSessionState(v108, v107, v109, v110);
  ResetWindowKeyProcessing(*(struct tagDESKTOP **)(v113 + 19216));
  if ( *(_QWORD *)(W32GetUserSessionState(v115, v114, v116, v117) + 19216) )
  {
    v122 = W32GetUserSessionState(v119, v118, v120, v121);
    *(_DWORD *)(*(_QWORD *)(v122 + 19216) + 48LL) |= 0x1000u;
  }
  if ( (unsigned int)Feature_PreserveActiveHklInDesktopSwitching__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( a2 == *(_QWORD *)(W32GetUserSessionState(v124, v123, v125, v126) + 62744) )
    {
      if ( *(_QWORD *)(W32GetUserSessionState(v128, v127, v129, v130) + 14184) )
      {
        v135 = W32GetUserSessionState(v132, v131, v133, v134);
        if ( (*(_BYTE *)(_HMPheFromObject(*(_QWORD *)(v135 + 14184)) + 25) & 1) == 0 )
        {
          v242 = *(_QWORD *)(W32GetUserSessionState(v132, v131, v133, v134) + 14184);
          v241 = W32GetUserSessionState(v137, v136, v138, v139) + 14192;
          HMAssignmentLock(&v241, 0);
        }
      }
      if ( *(_QWORD *)(W32GetUserSessionState(v132, v131, v133, v134) + 14216) )
      {
        v140 = W32GetUserSessionState(v124, v123, v125, v126);
        if ( (*(_BYTE *)(_HMPheFromObject(*(_QWORD *)(v140 + 14216)) + 25) & 1) == 0 )
        {
          v141 = *(_QWORD *)(W32GetUserSessionState(v124, v123, v125, v126) + 14216);
          v146 = W32GetUserSessionState(v143, v142, v144, v145);
          v242 = v141;
          v241 = v146 + 14184;
          HMAssignmentLock(&v241, 0);
        }
      }
    }
    else
    {
      v147 = *(_QWORD *)(W32GetUserSessionState(v128, v127, v129, v130) + 19216);
      if ( v147 == *(_QWORD *)(W32GetUserSessionState(v149, v148, v150, v151) + 62744) )
      {
        if ( *(_QWORD *)(W32GetUserSessionState(v124, v123, v125, v126) + 14192) )
        {
          v152 = W32GetUserSessionState(v124, v123, v125, v126);
          if ( (*(_BYTE *)(_HMPheFromObject(*(_QWORD *)(v152 + 14192)) + 25) & 1) == 0 )
          {
            v242 = *(_QWORD *)(W32GetUserSessionState(v124, v123, v125, v126) + 14192);
            v241 = W32GetUserSessionState(v154, v153, v155, v156) + 14184;
            HMAssignmentLock(&v241, 0);
            v161 = W32GetUserSessionState(v158, v157, v159, v160);
            HMAssignmentUnlock(v161 + 14192);
          }
        }
      }
    }
  }
  v162 = W32GetUserSessionState(v124, v123, v125, v126);
  LockObjectAssignment(v162 + 19216, a2);
  v167 = *(__int64 ***)(*(_QWORD *)(W32GetUserSessionState(v164, v163, v165, v166) + 19216) + 8LL);
  v168 = **v167;
  *(_QWORD *)(W32GetUserSessionState(*v167, v169, v170, v171) + 18760) = v168;
  SynchronizeContext();
  UpdateInUserCritUpdatedPointerRedirectedGlobalsOnDesktopSwitch();
  CitDesktopSwitch();
  v174 = *(struct tagWND ***)(a2 + 8);
  v175 = *((unsigned int *)*v174 + 16);
  if ( (v175 & 1) != 0 )
    ComposeWindow(v174[3]);
  v176 = W32GetUserSessionState(v174, v175, v172, v173);
  v180 = zzzSetDesktop(*(_QWORD *)(v176 + 18752), a2, 0);
  if ( v180 >= 0 )
  {
    if ( *(_QWORD *)(*(_QWORD *)(v250 + 16) + 464LL) != *(_QWORD *)(v250 + 24) )
    {
      AllocQueue(0);
      tagQ::zzzAttachToQueue(*(tagQ **)(v250 + 24), *(struct tagTHREADINFO **)(v250 + 16), 0, 0);
    }
    v180 = zzzSetDesktop(*(_QWORD *)(v250 + 16), a2, 0);
    if ( v180 >= 0 )
    {
      v183 = *(_QWORD *)(W32GetUserSessionState(v181, v177, v178, v179) + 19216);
      if ( *(_QWORD *)(*(_QWORD *)(v250 + 16) + 488LL) != v183 )
        MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4202);
      if ( a2 != *(_QWORD *)(W32GetUserSessionState(v183, v182, v184, v185) + 19216) )
        MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4203);
      v189 = **(_QWORD **)(a2 + 8);
      if ( (*(_DWORD *)(v189 + 64) & 1) != 0 )
      {
        UserSessionSwitchLeaveCrit(v189, v186, v187);
        v190 = (void *)UserReferenceDwmApiPort(**(_QWORD **)(a2 + 8));
        DwmSyncDesktopSwitch(v190);
        EnterCrit(1, 0);
      }
      if ( !gbIgnoreStressedOutStuff && a2 != *(_QWORD *)(W32GetUserSessionState(v189, v186, v187, v188) + 19216) )
        MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4217);
      v191 = *(__int64 ***)(a2 + 8);
      v192 = **v191;
      v193 = v59
          && (*(_DWORD *)(**(_QWORD **)(*(_QWORD *)(W32GetUserSessionState(*v191, v186, v187, v188) + 19216) + 8LL)
                        + 64LL)
            & 1) != 0;
      v194 = *(_QWORD **)(a2 + 8);
      v195 = *(_DWORD *)(*v194 + 64LL) & 1;
      v196 = W32GetUserSessionState(*v194, v186, v187, v188);
      v180 = GreDesktopSwitch(*(_QWORD *)(*(_QWORD *)(v196 + 56744) + 40LL), v195, v193, v192);
      if ( v180 >= 0 )
      {
        if ( v59 == (*(_DWORD *)(**(_QWORD **)(*(_QWORD *)(W32GetUserSessionState(v197, v177, v178, v179) + 19216) + 8LL)
                               + 64LL)
                   & 1) )
          ResetCursorPointerInternal();
        else
          zzzEnableDwmPointerSupport(*(_DWORD *)(**(_QWORD **)(a2 + 8) + 64LL) & 1, 0);
        v198 = BugCheckParameter3[0];
        Win32HM_LockIntoThread<1>(BugCheckParameter3[0], *(_QWORD *)(*(_QWORD *)(a2 + 8) + 24LL), &v241);
        GreLddmProcessDesktopSwitch();
        v202 = **(_QWORD **)(a2 + 8);
        v203 = 4 * (*(_DWORD *)(v202 + 64) & 1);
        if ( !v59
          || (v204 = 9,
              v202 = **(_QWORD **)(*(_QWORD *)(W32GetUserSessionState(v202, v199, v200, v201) + 19216) + 8LL),
              (*(_DWORD *)(v202 + 64) & 1) == 0) )
        {
          v204 = 1;
        }
        v205 = W32GetUserSessionState(v202, v199, v200, v201);
        GreSuspendDirectDraw(*(_QWORD *)(*(_QWORD *)(v205 + 56744) + 40LL), v203 | (unsigned int)v204, 0);
        xxxSetWindowPos(*(struct tagWND **)(*(_QWORD *)(a2 + 8) + 24LL), 0, 0, 339);
        if ( !gbIgnoreStressedOutStuff && a2 != *(_QWORD *)(W32GetUserSessionState(v207, v206, v208, v209) + 19216) )
          MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4283);
        GreResumeDirectDraw(0);
        i = tagUNIQUE_WINDOW_HANDLE::Get((tagUNIQUE_WINDOW_HANDLE *)(a2 + 88));
        if ( !(unsigned __int8)lambda_74a3533f2c879f4574bc0a0461c8b857_::operator()(v211, i)
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
            if ( (unsigned __int8)lambda_74a3533f2c879f4574bc0a0461c8b857_::operator()(v212, i) )
              break;
          }
        }
        Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)&v241);
        tagUNIQUE_WINDOW_HANDLE::Clear((tagUNIQUE_WINDOW_HANDLE *)(a2 + 88));
        UpdateKeyboardStateOnDesktopSwitch(0);
        if ( i )
        {
          if ( !gbIgnoreStressedOutStuff
            && *(_QWORD *)(*((_QWORD *)i + 2) + 488LL) != *(_QWORD *)(W32GetUserSessionState(v214, v213, v215, v216)
                                                                    + 19216) )
          {
            MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4368);
          }
          Win32HM_LockIntoThread<0>(v198, i, BugCheckParameter3);
          xxxSetForegroundWindowWithOptions(i, 31, 32, 0);
          Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)BugCheckParameter3);
        }
        else
        {
          xxxSetForegroundWindow2(0, 0, 0x20u);
        }
        v222 = *(_QWORD *)(W32GetUserSessionState(v218, v217, v219, v220) + 19160);
        if ( v222 )
          IPostQuitMessage(v222, 0);
        v225 = W32GetUserSessionState(v222, v221, v223, v224);
        KePulseEvent(*(PRKEVENT *)(v225 + 62736), 1, 0);
        xxxWindowEvent(0x20u, 0, 0, 0, 6);
        zzzUpdateCursorImage();
        if ( a2 == *(_QWORD *)(W32GetUserSessionState(v227, v226, v228, v229) + 62744) )
        {
          v234 = *(HANDLE *)(W32GetUserSessionState(v231, v230, v232, v233) + 63312);
          if ( PsGetThreadProcessId(Thread) == v234 && (*(_DWORD *)(*(_QWORD *)(a2 + 40) + 32LL) & 1) != 0 )
            SetTimerCoalescingTolerance(3);
        }
        v235 = *(_DWORD *)(a2 + 48);
        if ( (v235 & 0x20) != 0 )
        {
          v236 = *(_QWORD *)(a2 + 8);
          if ( v236 )
          {
            if ( *(_QWORD *)(v236 + 24) )
            {
              *(_DWORD *)(a2 + 48) = v235 & 0xFFFFFFDF;
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
    v14 = 0;
  }
  v237 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v14 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v238 = W32GetUserSessionState(WPP_GLOBAL_Control, v177, v178, v179);
    LOBYTE(v239) = v237;
    LOBYTE(v240) = v14;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v240,
      v239,
      *(_QWORD *)(v238 + 69152),
      4,
      3,
      29,
      (__int64)WPP_8482796ea87931402564603ebe19074e_Traceguids,
      v180);
  }
  PopAndFreeW32ThreadLock(v246);
  v247 = -1;
  if ( v249 != -1 )
    PopAndFreeW32ThreadLock(v248);
  return (unsigned int)v180;
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
