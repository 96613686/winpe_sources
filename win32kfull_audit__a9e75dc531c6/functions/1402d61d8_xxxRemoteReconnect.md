# xxxRemoteReconnect

- ea: `0x1402d61d8`
- end: `0x1402d71c5`
- name: `xxxRemoteReconnect`
- size: `4077`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1402c0720`

## callees

- `0x14004ab00`
- `0x14004af90`
- `0x14004b410`
- `0x14004ba38`
- `0x14004bd0c`
- `0x14004cd80`
- `0x1400a4a38`
- `0x1400dd43c`
- `0x14021b998`
- `0x14021bd74`
- `0x14021befc`
- `0x14021c070`
- `0x140236ee0`
- `0x140258c50`
- `0x140259f70`
- `0x1402632f0`
- `0x140266d9c`
- `0x140287a70`
- `0x140287b94`
- `0x140287c18`
- `0x14028b23c`
- `0x1402a7178`
- `0x1402ad93c`
- `0x1402d61d8`
- `0x140328ea4`
- `0x140342fa0`
- `0x140343080`
- `0x140343200`
- `0x140343500`

## import_xrefs

- `ntoskrnl!RtlSetActiveConsoleId` at `0x1402d6c5f`
- `ntoskrnl!RtlSetActiveConsoleId` at `0x1402d6c5f`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1402d687b`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1402d687b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1402d6859`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1402d68aa`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1402d6a1a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1402d6859`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1402d68aa`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1402d6a1a`
- `ntoskrnl!EtwActivityIdControl` at `0x1402d6226`
- `ntoskrnl!EtwActivityIdControl` at `0x1402d6226`
- `ntoskrnl!PsGetCurrentProcess` at `0x1402d6379`
- `ntoskrnl!PsGetCurrentProcess` at `0x1402d6379`
- `ntoskrnl!wcschr` at `0x1402d6737`
- `ntoskrnl!wcschr` at `0x1402d6737`
- `watchdog!DisplayScenarioContextEnsureAndAssociate` at `0x1402d6255`
- `watchdog!DisplayScenarioContextEnsureAndAssociate` at `0x1402d6255`
- `win32kbase!FastGetProfileIntW` at `0x1402d6774`
- `win32kbase!FastGetProfileIntW` at `0x1402d70c9`
- `win32kbase!FastGetProfileIntW` at `0x1402d6774`
- `win32kbase!FastGetProfileIntW` at `0x1402d70c9`
- `win32kbase!xxxUserSetDisplayConfig` at `0x1402d6e8e`
- `win32kbase!xxxUserSetDisplayConfig` at `0x1402d6e8e`
- `win32kbase!UpdateKeyLights` at `0x1402d7013`
- `win32kbase!UpdateKeyLights` at `0x1402d7013`
- `win32kbase!DispBrokerAsyncSessionStateChanged` at `0x1402d6d9b`
- `win32kbase!DispBrokerAsyncSessionStateChanged` at `0x1402d6d9b`
- `win32kbase!SetProtocolType` at `0x1402d6b22`
- `win32kbase!SetProtocolType` at `0x1402d6d0b`
- `win32kbase!SetProtocolType` at `0x1402d6b22`
- `win32kbase!SetProtocolType` at `0x1402d6d0b`
- `win32kbase!DrvIsNotUsingGraphicsDevice` at `0x1402d6dfa`
- `win32kbase!DrvIsNotUsingGraphicsDevice` at `0x1402d6dfa`
- `win32kbase!SetConsoleSwitchInProgress` at `0x1402d64f9`
- `win32kbase!SetConsoleSwitchInProgress` at `0x1402d6ca4`
- `win32kbase!SetConsoleSwitchInProgress` at `0x1402d64f9`
- `win32kbase!SetConsoleSwitchInProgress` at `0x1402d6ca4`
- `win32kbase!DrvCloseGraphicsDevices` at `0x1402d6cee`
- `win32kbase!DrvCloseGraphicsDevices` at `0x1402d6cee`
- `win32kbase!SetConnectedState` at `0x1402d7096`
- `win32kbase!SetConnectedState` at `0x1402d7096`
- `win32kbase!CitSessionConnectChange` at `0x1402d7168`
- `win32kbase!CitSessionConnectChange` at `0x1402d7168`
- `win32kbase!DrvSetGraphicsDevices` at `0x1402d6bdf`
- `win32kbase!DrvSetGraphicsDevices` at `0x1402d6d25`
- `win32kbase!DrvSetGraphicsDevices` at `0x1402d6bdf`
- `win32kbase!DrvSetGraphicsDevices` at `0x1402d6d25`
- `win32kbase!CleanupRemoteHandles` at `0x1402d6c96`
- `win32kbase!CleanupRemoteHandles` at `0x1402d6c96`
- `win32kbase!PopulateUMKMHandlePair` at `0x1402d6529`
- `win32kbase!PopulateUMKMHandlePair` at `0x1402d654a`
- `win32kbase!PopulateUMKMHandlePair` at `0x1402d6529`
- `win32kbase!PopulateUMKMHandlePair` at `0x1402d654a`
- `win32kbase!GreMultiUserInitSession` at `0x1402d6934`
- `win32kbase!GreMultiUserInitSession` at `0x1402d69cb`
- `win32kbase!GreMultiUserInitSession` at `0x1402d6934`
- `win32kbase!GreMultiUserInitSession` at `0x1402d69cb`
- `win32kbase!UserRemoteConnectedSessionUsingXddm` at `0x1402d6b5c`
- `win32kbase!UserRemoteConnectedSessionUsingXddm` at `0x1402d6b5c`
- `win32kbase!GreDrvConnect` at `0x1402d6b8b`
- `win32kbase!GreDrvConnect` at `0x1402d6b8b`
- `win32kbase!DrvSessionHasAnyGraphicsDevice` at `0x1402d6e0c`
- `win32kbase!DrvSessionHasAnyGraphicsDevice` at `0x1402d6e0c`
- `win32kbase!DispBrokerUpdateKernelDisplayPolicies` at `0x1402d6e20`
- `win32kbase!DispBrokerUpdateKernelDisplayPolicies` at `0x1402d6e20`
- `win32kbase!DxgkEngNotifyDisplayChange` at `0x1402d6cb2`
- `win32kbase!DxgkEngNotifyDisplayChange` at `0x1402d6cb2`
- `win32kbase!DxDdGetDxgkWin32kInterface` at `0x1402d7128`
- `win32kbase!DxDdGetDxgkWin32kInterface` at `0x1402d7128`
- `win32kbase!DrvEscapeRemoteDrivers` at `0x1402d6d82`
- `win32kbase!DrvEscapeRemoteDrivers` at `0x1402d6f84`
- `win32kbase!DrvEscapeRemoteDrivers` at `0x1402d6d82`
- `win32kbase!DrvEscapeRemoteDrivers` at `0x1402d6f84`
- `win32kbase!DrvNotifySessionStateChange` at `0x1402d6b48`
- `win32kbase!DrvNotifySessionStateChange` at `0x1402d6c83`
- `win32kbase!DrvNotifySessionStateChange` at `0x1402d6b48`
- `win32kbase!DrvNotifySessionStateChange` at `0x1402d6c83`
- `win32kbase!GreGetRemoteContext` at `0x1402d62be`
- `win32kbase!GreGetRemoteContext` at `0x1402d62be`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1402d67e9`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1402d67e9`
- `win32kbase!EnterCrit` at `0x1402d6fe3`
- `win32kbase!EnterCrit` at `0x1402d6fe3`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1402d6fc5`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1402d6fc5`
- `win32kbase!Win32FreePool` at `0x1402d6d39`
- `win32kbase!Win32FreePool` at `0x1402d6d39`
- `WIN32K!W32GetUserGdiSessionState` at `0x1402d6369`
- `WIN32K!W32GetUserGdiSessionState` at `0x1402d6369`
- `WIN32K!W32GetUserSessionState` at `0x1402d6271`
- `WIN32K!W32GetUserSessionState` at `0x1402d6287`
- `WIN32K!W32GetUserSessionState` at `0x1402d631f`
- `WIN32K!W32GetUserSessionState` at `0x1402d63a1`
- `WIN32K!W32GetUserSessionState` at `0x1402d6615`
- `WIN32K!W32GetUserSessionState` at `0x1402d662e`
- `WIN32K!W32GetUserSessionState` at `0x1402d66b3`
- `WIN32K!W32GetUserSessionState` at `0x1402d6786`
- `WIN32K!W32GetUserSessionState` at `0x1402d67a2`
- `WIN32K!W32GetUserSessionState` at `0x1402d68d3`
- `WIN32K!W32GetUserSessionState` at `0x1402d696a`
- `WIN32K!W32GetUserSessionState` at `0x1402d6a3c`
- `WIN32K!W32GetUserSessionState` at `0x1402d6aa6`
- `WIN32K!W32GetUserSessionState` at `0x1402d6b2e`
- `WIN32K!W32GetUserSessionState` at `0x1402d6ba8`
- `WIN32K!W32GetUserSessionState` at `0x1402d6bfe`
- `WIN32K!W32GetUserSessionState` at `0x1402d6c43`
- `WIN32K!W32GetUserSessionState` at `0x1402d6c6b`
- `WIN32K!W32GetUserSessionState` at `0x1402d6d52`
- `WIN32K!W32GetUserSessionState` at `0x1402d6de3`
- `WIN32K!W32GetUserSessionState` at `0x1402d6e2c`
- `WIN32K!W32GetUserSessionState` at `0x1402d6eeb`
- `WIN32K!W32GetUserSessionState` at `0x1402d6f45`
- `WIN32K!W32GetUserSessionState` at `0x1402d6ff4`
- `WIN32K!W32GetUserSessionState` at `0x1402d7027`
- `WIN32K!W32GetUserSessionState` at `0x1402d7047`
- `WIN32K!W32GetUserSessionState` at `0x1402d705c`
- `WIN32K!W32GetUserSessionState` at `0x1402d7071`
- `WIN32K!W32GetUserSessionState` at `0x1402d70db`
- `WIN32K!W32GetUserSessionState` at `0x1402d70f7`
- `WIN32K!W32GetUserSessionState` at `0x1402d7111`
- `WIN32K!W32GetUserSessionState` at `0x1402d714d`
- `WIN32K!W32GetUserSessionState` at `0x1402d6271`
- `WIN32K!W32GetUserSessionState` at `0x1402d6287`
- `WIN32K!W32GetUserSessionState` at `0x1402d631f`
- `WIN32K!W32GetUserSessionState` at `0x1402d63a1`
- `WIN32K!W32GetUserSessionState` at `0x1402d6615`
- `WIN32K!W32GetUserSessionState` at `0x1402d662e`
- `WIN32K!W32GetUserSessionState` at `0x1402d66b3`
- `WIN32K!W32GetUserSessionState` at `0x1402d6786`
- `WIN32K!W32GetUserSessionState` at `0x1402d67a2`
- `WIN32K!W32GetUserSessionState` at `0x1402d68d3`
- `WIN32K!W32GetUserSessionState` at `0x1402d696a`
- `WIN32K!W32GetUserSessionState` at `0x1402d6a3c`
- `WIN32K!W32GetUserSessionState` at `0x1402d6aa6`
- `WIN32K!W32GetUserSessionState` at `0x1402d6b2e`
- `WIN32K!W32GetUserSessionState` at `0x1402d6ba8`
- `WIN32K!W32GetUserSessionState` at `0x1402d6bfe`
- `WIN32K!W32GetUserSessionState` at `0x1402d6c43`
- `WIN32K!W32GetUserSessionState` at `0x1402d6c6b`
- `WIN32K!W32GetUserSessionState` at `0x1402d6d52`
- `WIN32K!W32GetUserSessionState` at `0x1402d6de3`
- `WIN32K!W32GetUserSessionState` at `0x1402d6e2c`
- `WIN32K!W32GetUserSessionState` at `0x1402d6eeb`
- `WIN32K!W32GetUserSessionState` at `0x1402d6f45`
- `WIN32K!W32GetUserSessionState` at `0x1402d6ff4`
- `WIN32K!W32GetUserSessionState` at `0x1402d7027`
- `WIN32K!W32GetUserSessionState` at `0x1402d7047`
- `WIN32K!W32GetUserSessionState` at `0x1402d705c`
- `WIN32K!W32GetUserSessionState` at `0x1402d7071`
- `WIN32K!W32GetUserSessionState` at `0x1402d70db`
- `WIN32K!W32GetUserSessionState` at `0x1402d70f7`
- `WIN32K!W32GetUserSessionState` at `0x1402d7111`
- `WIN32K!W32GetUserSessionState` at `0x1402d714d`

## string_xrefs

- `0x1402d6767`: `CursorBlinkEnable`
- `0x1402d70bc`: `CursorBlinkEnable`

## pseudocode

```c
__int64 __fastcall xxxRemoteReconnect(void *a1)
{
  __int64 v1; // rdx
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 UserSessionState; // r14
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 RemoteContext; // r13
  bool v14; // bl
  unsigned int *v15; // rcx
  bool v16; // di
  __int64 v17; // rax
  int v18; // r8d
  int v19; // edx
  __int64 v20; // rbx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v26; // rax
  _DWORD *v27; // rbx
  _OWORD *v28; // rax
  _OWORD *v29; // rcx
  __int64 v30; // rdx
  _OWORD *v31; // rax
  _OWORD *v32; // rcx
  __int64 v33; // rdx
  int v34; // edi
  int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  NTSTATUS v39; // esi
  BOOL v40; // edi
  int v41; // ebx
  int v42; // ebx
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  __int64 v46; // r9
  char *v47; // rcx
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // r9
  __int64 v51; // rax
  wchar_t *v52; // rax
  __int64 v53; // rdx
  __int64 v54; // rcx
  int v55; // ebx
  __int64 v56; // rdx
  __int64 v57; // rcx
  __int64 v58; // r8
  __int64 v59; // r9
  __int64 v60; // rax
  __int64 v61; // rdx
  __int64 v62; // r8
  __int64 v63; // r9
  __int64 v64; // rax
  _WORD *v65; // rcx
  __int64 v66; // rax
  size_t v67; // rbx
  void *v68; // rax
  void *v69; // rbx
  __int64 v70; // rdi
  struct _FILE_OBJECT *v71; // rcx
  __int64 v72; // rcx
  PVOID v73; // rdi
  __int64 v74; // rbx
  int v75; // eax
  __int64 v76; // rbx
  int inited; // eax
  void *v78; // rcx
  __int64 v79; // rdx
  __int64 v80; // rcx
  __int64 v81; // r8
  __int64 v82; // r9
  __int16 v83; // ax
  unsigned __int16 v84; // bx
  __int64 v85; // rax
  __int64 v86; // rdx
  __int64 v87; // rcx
  __int64 v88; // r8
  __int64 v89; // r9
  __int64 v90; // rdx
  __int64 v91; // rcx
  __int64 v92; // r8
  __int64 v93; // r9
  NTSTATUS v94; // eax
  int v95; // eax
  __int64 v96; // rdx
  __int64 v97; // r8
  __int64 v98; // r9
  __int64 v99; // rcx
  __int64 v100; // rax
  __int64 v101; // rdx
  __int64 v102; // rcx
  __int64 v103; // r8
  __int64 v104; // r9
  unsigned int CurrentWin32kSessionId; // eax
  __int64 v106; // rdx
  __int64 v107; // r8
  __int64 v108; // r9
  __int64 v109; // rdx
  __int64 v110; // rcx
  int v111; // eax
  __int64 v112; // rdx
  __int64 v113; // rcx
  __int64 v114; // r8
  __int64 v115; // r9
  __int64 v116; // rax
  __int64 v117; // rax
  __int64 v118; // rdx
  __int64 v119; // rcx
  __int64 v120; // r8
  __int64 v121; // r9
  __int64 v122; // rax
  __int64 v123; // r8
  __int64 v124; // r9
  char v125; // bl
  bool v126; // di
  __int64 v127; // rax
  int v128; // r8d
  int v129; // edx
  __int64 v130; // rdx
  __int64 v131; // rcx
  __int64 v132; // r8
  __int64 v133; // r9
  __int64 v134; // rax
  unsigned int v135; // ebx
  __int64 v136; // rdx
  __int64 v137; // rcx
  __int64 v138; // r8
  __int64 v139; // r9
  __int64 v140; // rdx
  __int64 v141; // rcx
  __int64 v142; // r8
  __int64 v143; // rax
  __int64 v144; // rdx
  __int64 v145; // rcx
  __int64 v146; // r8
  __int64 v147; // r9
  __int64 v148; // rdx
  __int64 v149; // rcx
  __int64 v150; // r8
  __int64 v151; // r9
  __int64 v152; // rdx
  __int64 v153; // rcx
  __int64 v154; // r8
  __int64 v155; // r9
  __int64 v156; // rdx
  __int64 v157; // rcx
  __int64 v158; // rdx
  __int64 v159; // rcx
  __int64 v160; // r8
  __int64 v161; // r9
  __int64 v162; // rdx
  __int64 v163; // rcx
  __int64 v164; // r8
  __int64 v165; // r9
  bool v166; // di
  void (__fastcall *v167)(__int64, _QWORD); // rbx
  unsigned int RemoteDeviceCount; // eax
  __int64 v169; // rcx
  __int64 v170; // rdx
  __int64 v171; // rcx
  __int64 v172; // r8
  __int64 v173; // r9
  __int64 v174; // rdx
  PVOID *Object; // [rsp+20h] [rbp-4A8h]
  PVOID *Objecta; // [rsp+20h] [rbp-4A8h]
  int HandleInformation; // [rsp+28h] [rbp-4A0h]
  BOOL v178; // [rsp+60h] [rbp-468h]
  void *v179; // [rsp+68h] [rbp-460h]
  int v180; // [rsp+70h] [rbp-458h] BYREF
  int v181; // [rsp+74h] [rbp-454h]
  PVOID v182; // [rsp+78h] [rbp-450h] BYREF
  unsigned __int16 v183; // [rsp+80h] [rbp-448h]
  int v184; // [rsp+84h] [rbp-444h]
  int v185; // [rsp+88h] [rbp-440h]
  int v186; // [rsp+8Ch] [rbp-43Ch]
  unsigned int v187; // [rsp+90h] [rbp-438h]
  int v188; // [rsp+94h] [rbp-434h]
  void *Src; // [rsp+98h] [rbp-430h]
  struct _DXGK_DISPLAY_SCENARIO_CONTEXT *v190; // [rsp+A0h] [rbp-428h]
  unsigned __int8 v191[8]; // [rsp+A8h] [rbp-420h] BYREF
  struct _DXGK_DISPLAY_SCENARIO_CONTEXT *v192; // [rsp+B0h] [rbp-418h] BYREF
  _BYTE v193[320]; // [rsp+C0h] [rbp-408h] BYREF
  _BYTE v194[320]; // [rsp+200h] [rbp-2C8h] BYREF
  _BYTE v195[32]; // [rsp+340h] [rbp-188h] BYREF
  __int64 v196; // [rsp+360h] [rbp-168h]
  __int64 v197; // [rsp+368h] [rbp-160h]
  __int64 v198; // [rsp+370h] [rbp-158h]
  __int64 v199; // [rsp+378h] [rbp-150h]
  __int64 v200; // [rsp+380h] [rbp-148h]
  __int128 v201; // [rsp+390h] [rbp-138h]
  __int128 v202; // [rsp+3A0h] [rbp-128h]
  __int128 v203; // [rsp+3B0h] [rbp-118h]
  __int128 v204; // [rsp+3C0h] [rbp-108h]
  _BYTE v205[58]; // [rsp+3D0h] [rbp-F8h] BYREF
  __int128 v206; // [rsp+40Ah] [rbp-BEh]
  __int16 v207; // [rsp+41Ah] [rbp-AEh]
  __int128 v208; // [rsp+41Ch] [rbp-ACh]
  int v209; // [rsp+42Ch] [rbp-9Ch]
  int v210; // [rsp+430h] [rbp-98h]
  int v211; // [rsp+434h] [rbp-94h]
  unsigned __int16 v212; // [rsp+448h] [rbp-80h]
  __int64 v213; // [rsp+44Ch] [rbp-7Ch]
  int v214; // [rsp+454h] [rbp-74h]
  int v215; // [rsp+458h] [rbp-70h]
  int v216; // [rsp+45Ch] [rbp-6Ch]
  int v217; // [rsp+464h] [rbp-64h]
  GUID v218; // [rsp+480h] [rbp-48h] BYREF

  Src = a1;
  v191[0] = 0;
  v218 = 0;
  EtwActivityIdControl(3u, &v218);
  DisplayScenarioContextEnsureAndAssociate(&v218, 0x16u, 0, &v192, v191);
  v190 = v192;
  v181 = *(_DWORD *)(W32GetUserSessionState(v2, v1, v3, v4) + 16240);
  UserSessionState = W32GetUserSessionState(v6, v5, v7, v8);
  v183 = *(_WORD *)(UserSessionState + 68736);
  memset_0(v195, 0, 0x140u);
  v180 = 0;
  RemoteContext = GreGetRemoteContext();
  v14 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v15 = &WPP_RECORDER_INITIALIZED;
  v16 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v14 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v17 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, v10, v11, v12);
    LOBYTE(v18) = v16;
    LOBYTE(v19) = v14;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v19,
      v18,
      *(_QWORD *)(v17 + 69152),
      4,
      3,
      16,
      (__int64)WPP_4ba15321700d32c32d46c236c92eb934_Traceguids);
  }
  v20 = *(_QWORD *)(W32GetUserGdiSessionState(v15) + 40);
  if ( PsGetCurrentProcess() != v20 )
  {
    CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)v191);
    return 3221225506LL;
  }
  v26 = W32GetUserSessionState(v22, v21, v23, v24);
  *(_DWORD *)(v26 + 68920) |= 0x20u;
  memset_0(v193, 0, sizeof(v193));
  v27 = Src;
  RtlCopyFromUser(v193, Src, 0x140u);
  v28 = v194;
  v29 = v193;
  v30 = 2;
  do
  {
    *v28 = *v29;
    v28[1] = v29[1];
    v28[2] = v29[2];
    v28[3] = v29[3];
    v28[4] = v29[4];
    v28[5] = v29[5];
    v28[6] = v29[6];
    v28[7] = v29[7];
    v28 += 8;
    v29 += 8;
    --v30;
  }
  while ( v30 );
  *v28 = *v29;
  v28[1] = v29[1];
  v28[2] = v29[2];
  v28[3] = v29[3];
  v31 = v195;
  v32 = v194;
  v33 = 2;
  do
  {
    *v31 = *v32;
    v31[1] = v32[1];
    v31[2] = v32[2];
    v31[3] = v32[3];
    v31[4] = v32[4];
    v31[5] = v32[5];
    v31[6] = v32[6];
    v31[7] = v32[7];
    v31 += 8;
    v32 += 8;
    --v33;
  }
  while ( v33 );
  *v31 = *v32;
  v31[1] = v32[1];
  v31[2] = v32[2];
  v31[3] = v32[3];
  if ( *(_DWORD *)(UserSessionState + 68836) )
  {
    v34 = -1073741823;
LABEL_20:
    CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)v191);
    return (unsigned int)v34;
  }
  SetConsoleSwitchInProgress(1, 0, 2, 128);
  SetMouseTrails(0);
  *(_QWORD *)(UserSessionState + 68912) = UserSessionState + 68936;
  v34 = PopulateUMKMHandlePair(v198, UserSessionState + 68624);
  if ( v34 < 0 )
    goto LABEL_20;
  v35 = PopulateUMKMHandlePair(v199, UserSessionState + 68640);
  v39 = v35;
  if ( v35 < 0 )
  {
    v34 = v35;
    goto LABEL_20;
  }
  v40 = 0;
  v178 = 0;
  v184 = 0;
  v185 = 0;
  v187 = v181 + 1;
  v181 = 0;
  v186 = 0;
  v179 = 0;
  *(_QWORD *)&v218.Data1 = 0;
  *(_DWORD *)(UserSessionState + 68616) = v27[5];
  *(_DWORD *)(UserSessionState + 68620) = v27[6];
  *(_QWORD *)(UserSessionState + 68608) = v196;
  *(_QWORD *)(UserSessionState + 68656) = v197;
  *(_QWORD *)(UserSessionState + 68672) = v200;
  *(_QWORD *)(UserSessionState + 68824) = v213;
  *(_DWORD *)(UserSessionState + 68832) = v214;
  v41 = v210;
  *(_DWORD *)(W32GetUserSessionState(0, v36, v37, v38) + 16216) = v41;
  v42 = v211;
  *(_DWORD *)(W32GetUserSessionState(v44, v43, v45, v46) + 13980) = v42;
  v188 = *(_DWORD *)(UserSessionState + 68600);
  *(_DWORD *)(UserSessionState + 68600) = v217;
  *(_DWORD *)(RemoteContext + 64) = v217;
  v47 = (char *)Src;
  *(_QWORD *)(UserSessionState + 68680) = *((_QWORD *)Src + 38);
  *(_DWORD *)(UserSessionState + 68688) = *((_DWORD *)v47 + 78);
  *(_OWORD *)(UserSessionState + 68692) = *(_OWORD *)(v47 + 162);
  *(_OWORD *)(UserSessionState + 68708) = *(_OWORD *)(v47 + 178);
  *(_QWORD *)(UserSessionState + 68724) = *(_QWORD *)(v47 + 194);
  v51 = W32GetUserSessionState(v47, v48, v49, v50);
  *(_OWORD *)(v51 + 63888) = v201;
  *(_OWORD *)(v51 + 63904) = v202;
  *(_OWORD *)(v51 + 63920) = v203;
  *(_OWORD *)(v51 + 63936) = v204;
  *(_OWORD *)(v51 + 63328) = v206;
  *(_WORD *)(v51 + 63344) = v207;
  *(_OWORD *)(v51 + 63348) = v208;
  *(_DWORD *)(v51 + 63364) = v209;
  v52 = wcschr((const wchar_t *)(v51 + 63888), 0x23u);
  v55 = 0;
  if ( v52 )
    *v52 = 0;
  if ( !(unsigned int)IsRemoteConnection(v54, v53)
    || (HandleInformation = 0, Object = (PVOID *)&v180, FastGetProfileIntW(0, 39, L"CursorBlinkEnable"), v180) )
  {
    v64 = W32GetUserSessionState(v57, v56, v58, v59);
    *(_DWORD *)(*(_QWORD *)(v64 + 19704) + 2236LL) |= 4u;
  }
  else
  {
    v60 = W32GetUserSessionState(v57, v56, v58, v59);
    *(_DWORD *)(*(_QWORD *)(v60 + 19704) + 2236LL) &= ~4u;
  }
  v65 = *(_WORD **)(RemoteContext + 40);
  if ( v65 )
  {
    v66 = -1;
    do
      ++v66;
    while ( v65[v66] );
    *(_QWORD *)&v218.Data1 = v66 + 1;
    v67 = 2 * (v66 + 1);
    v68 = (void *)Win32AllocPoolWithQuotaZInit(v67, 2020897621);
    v179 = v68;
    if ( !v68 )
    {
      v39 = -1073741801;
      v69 = 0;
      goto LABEL_76;
    }
    memmove(v68, *(const void **)(RemoteContext + 40), v67);
    v55 = 0;
  }
  v70 = *(_QWORD *)(UserSessionState + 68896);
  if ( v70 || (v65 = *(_WORD **)(UserSessionState + 68608)) == 0 )
  {
    if ( !*(_QWORD *)(UserSessionState + 68608) )
    {
      v76 = *(_QWORD *)(UserSessionState + 68904);
      LODWORD(Object) = *(_DWORD *)(W32GetUserSessionState(v65, v61, v62, v63) + 68620);
      inited = GreMultiUserInitSession(
                 RemoteContext,
                 *(_QWORD *)(UserSessionState + 68672),
                 *(_QWORD *)(UserSessionState + 68912),
                 *(unsigned int *)(UserSessionState + 68616),
                 Object,
                 v70,
                 v76,
                 8,
                 v205,
                 19,
                 UserSessionState + 68692);
      v55 = 0;
      if ( !inited )
        v39 = -1073741823;
    }
  }
  else
  {
    v182 = 0;
    v39 = ObReferenceObjectByHandle(v65, 0, 0, 0, &v182, 0);
    if ( v39 >= 0 )
    {
      v71 = (struct _FILE_OBJECT *)v182;
      *(_QWORD *)(UserSessionState + 68896) = v182;
      IoGetRelatedDeviceObject(v71);
      v182 = 0;
      v39 = ObReferenceObjectByHandle(*(HANDLE *)(UserSessionState + 68672), 0, 0, 0, &v182, 0);
      v73 = v182;
      *(_QWORD *)(UserSessionState + 68904) = v182;
      if ( v39 >= 0 )
      {
        v74 = *(_QWORD *)(UserSessionState + 68896);
        LODWORD(Objecta) = *(_DWORD *)(W32GetUserSessionState(v72, v61, v62, v63) + 68620);
        v75 = GreMultiUserInitSession(
                RemoteContext,
                *(_QWORD *)(UserSessionState + 68672),
                *(_QWORD *)(UserSessionState + 68912),
                *(unsigned int *)(UserSessionState + 68616),
                Objecta,
                v74,
                v73,
                8,
                v205,
                19,
                UserSessionState + 68692);
        v55 = 0;
        if ( !v75 )
          v39 = -1073741823;
      }
    }
  }
  if ( v39 < 0 )
    goto LABEL_74;
  v78 = *(void **)(UserSessionState + 68656);
  if ( v78 )
  {
    v182 = 0;
    v39 = ObReferenceObjectByHandle(v78, 0, 0, 0, &v182, 0);
    *(_QWORD *)(UserSessionState + 68664) = v182;
  }
  if ( v39 < 0 )
    goto LABEL_74;
  if ( *(_DWORD *)(W32GetUserSessionState(v78, v61, v62, v63) + 68888) )
    xxxRemoteStopScreenUpdates();
  v83 = *(_WORD *)(UserSessionState + 69032);
  if ( v212 == v83 || !v83 )
  {
LABEL_60:
    SetProtocolType(v212);
    if ( !*(_WORD *)(W32GetUserSessionState(v87, v86, v88, v89) + 68736) )
      DrvNotifySessionStateChange(3);
    v186 = 1;
    if ( (unsigned int)UserRemoteConnectedSessionUsingXddm() )
    {
      if ( *(_WORD *)(UserSessionState + 68736) == *(_WORD *)(UserSessionState + 69032) )
      {
        v94 = GreDrvReconnect(RemoteContext);
      }
      else
      {
        v55 = 1;
        v94 = GreDrvConnect(RemoteContext);
      }
      v39 = v94;
      v178 = v94 >= 0;
    }
    else
    {
      v55 = 1;
      if ( !*(_WORD *)(W32GetUserSessionState(v91, v90, v92, v93) + 68736) )
      {
        v39 = DrvOpenLocalGraphicsDevices();
        if ( v39 < 0 )
        {
LABEL_74:
          v69 = v179;
          goto LABEL_75;
        }
        v185 = 1;
      }
    }
    v181 = 1;
    v95 = DrvSetGraphicsDevices(v205);
    v99 = 0;
    if ( v95 )
    {
      if ( (v215 || *(_WORD *)(UserSessionState + 68736) != *(_WORD *)(UserSessionState + 69032) || v216)
        && ((v117 = W32GetUserSessionState(0, v96, v97, v98),
             v39 = 0,
             !(unsigned int)DrvIsNotUsingGraphicsDevice(*(_QWORD *)(*(_QWORD *)(v117 + 56744) + 16LL)))
         || (unsigned int)DrvSessionHasAnyGraphicsDevice())
        && (DispBrokerUpdateKernelDisplayPolicies(),
            v122 = W32GetUserSessionState(v119, v118, v120, v121),
            LOBYTE(HandleInformation) = 0,
            v39 = xxxUserSetDisplayConfig(
                    0,
                    0,
                    v216 != 0 ? 2447 : 2191,
                    2050,
                    *(_QWORD *)(v122 + 19224),
                    HandleInformation,
                    0,
                    0,
                    0,
                    v190,
                    0),
            v96 = 0,
            v39 < 0) )
      {
        if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) == 0
          || (v125 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
        {
          v125 = 0;
        }
        v126 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
        if ( v125 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v127 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, 0, v123, v124);
          LOBYTE(v128) = v126;
          LOBYTE(v129) = v125;
          WPP_RECORDER_AND_TRACE_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v129,
            v128,
            *(_QWORD *)(v127 + 69152),
            4,
            3,
            17,
            (__int64)WPP_4ba15321700d32c32d46c236c92eb934_Traceguids);
        }
      }
      else
      {
        if ( (unsigned int)IsRemoteConnection(v99, v96) )
        {
          if ( v55 )
          {
            v134 = W32GetUserSessionState(v131, v130, v132, v133);
            v135 = 2;
            if ( !(unsigned int)DrvEscapeRemoteDrivers(
                                  *(_QWORD *)(*(_QWORD *)(v134 + 56744) + 16LL),
                                  *(unsigned __int16 *)(UserSessionState + 68736),
                                  *(_QWORD *)(RemoteContext + 40),
                                  2,
                                  *(_QWORD *)(UserSessionState + 68928),
                                  8) )
              v39 = -1073741823;
          }
          else
          {
            v135 = 2;
          }
          AttachInputDevices(0);
        }
        else
        {
          if ( *(_WORD *)(UserSessionState + 69032) )
            RemoveInputDevices();
          AttachInputDevices(1);
          xxxUserReinitializeAutoRotation();
          UserSessionSwitchLeaveCrit(v141, v140, v142);
          RegisterCDROMNotify();
          v184 = 1;
          EnterCrit(1, 0);
          v135 = 2;
        }
        v143 = W32GetUserSessionState(v137, v136, v138, v139);
        RemoteRedrawScreen(v143 + 19224);
        InitKeyboard();
        UpdateKeyLights(0);
        SetPointer(1);
        *(_DWORD *)(W32GetUserSessionState(v145, v144, v146, v147) + 36172) = 9;
        TransitionCursorSuppressionState(10);
        if ( *(_DWORD *)(W32GetUserSessionState(v149, v148, v150, v151) + 36172) == 1
          || *(_DWORD *)(W32GetUserSessionState(v153, v152, v154, v155) + 36172) == 5 )
        {
          v135 = *(_DWORD *)(W32GetUserSessionState(v153, v152, v154, v155) + 36172);
        }
        TransitionCursorSuppressionState(v135);
        SetConnectedState(1, *(unsigned int *)(UserSessionState + 68744));
        if ( !(unsigned int)IsRemoteConnection(v157, v156) || (FastGetProfileIntW(0, 39, L"CursorBlinkEnable"), v180) )
        {
          v163 = *(_QWORD *)(W32GetUserSessionState(v159, v158, v160, v161) + 19704);
          *(_DWORD *)(v163 + 2236) |= 4u;
        }
        else
        {
          v163 = *(_QWORD *)(W32GetUserSessionState(v159, v158, v160, v161) + 19704);
          *(_DWORD *)(v163 + 2236) &= ~4u;
        }
        v166 = *(_WORD *)(W32GetUserSessionState(v163, v162, v164, v165) + 68736) == 0;
        v167 = *(void (__fastcall **)(__int64, _QWORD))(DxDdGetDxgkWin32kInterface() + 384);
        RemoteDeviceCount = DrvGetRemoteDeviceCount();
        LOBYTE(v169) = v166;
        v167(v169, RemoteDeviceCount);
        LOBYTE(v174) = *(_WORD *)(W32GetUserSessionState(v171, v170, v172, v173) + 68736) == 0;
        CitSessionConnectChange(1, v174);
      }
    }
    else
    {
      if ( *(_DWORD *)(UserSessionState + 68888) )
      {
        v100 = W32GetUserSessionState(0, v96, v97, v98);
        RemoteRedrawScreen(v100 + 19224);
      }
      v39 = -1073741823;
    }
    goto LABEL_74;
  }
  v69 = v179;
  if ( v179 && !(unsigned int)GreMultiUserSetDisplayDriverName(RemoteContext, v218.Data1 - 1, v179) )
  {
    v39 = -1073741823;
LABEL_75:
    v40 = v178;
    goto LABEL_76;
  }
  v84 = *(_WORD *)(UserSessionState + 68736);
  v85 = W32GetUserSessionState(v80, v79, v81, v82);
  v39 = xxxRemoteSetDisconnectDisplayMode(*(struct tagDESKTOP **)(v85 + 19216), v84, v190);
  if ( v39 >= 0 )
  {
    if ( *((_DWORD *)Src + 72) )
      DrvCloseRemoteGraphicsDevices();
    v69 = v179;
    if ( v179 && !(unsigned int)GreMultiUserSetDisplayDriverName(RemoteContext, 8, v205) )
    {
      v39 = -1073741823;
      v40 = 0;
      goto LABEL_76;
    }
    v55 = 0;
    goto LABEL_60;
  }
  v40 = 0;
  v69 = v179;
LABEL_76:
  SetMouseTrails(v187);
  if ( v39 < 0 && v40 )
    GreDrvDisconnect(RemoteContext);
  if ( !v39 && !*(_WORD *)(W32GetUserSessionState(v102, v101, v103, v104) + 68736) )
  {
    CurrentWin32kSessionId = W32GetCurrentWin32kSessionId();
    RtlSetActiveConsoleId(CurrentWin32kSessionId);
  }
  if ( !*(_WORD *)(W32GetUserSessionState(v102, v101, v103, v104) + 68736) )
    DrvNotifySessionStateChange(4);
  if ( v39 < 0 )
    CleanupRemoteHandles(RemoteContext);
  SetConsoleSwitchInProgress(0, v106, v107, v108);
  DxgkEngNotifyDisplayChange(0);
  if ( v39 < 0 )
  {
    v111 = v188;
    *(_DWORD *)(UserSessionState + 68600) = v188;
    *(_DWORD *)(RemoteContext + 64) = v111;
    if ( v184 )
      UnregisterDeviceClassNotifications();
    if ( v185 )
      DrvCloseGraphicsDevices(1);
    if ( v186 )
      SetProtocolType(v183);
    if ( v181 )
      DrvSetGraphicsDevices(v205);
  }
  if ( v69 )
    Win32FreePool(v69);
  if ( !v39 )
  {
    if ( (unsigned int)IsRemoteConnection(v110, v109) )
    {
      v116 = W32GetUserSessionState(v113, v112, v114, v115);
      DrvEscapeRemoteDrivers(
        *(_QWORD *)(*(_QWORD *)(v116 + 56744) + 16LL),
        *(unsigned __int16 *)(UserSessionState + 68736),
        *(_QWORD *)(RemoteContext + 40),
        6,
        0,
        0);
    }
  }
  DrvOcclusionStateChangeNotify();
  DispBrokerAsyncSessionStateChanged(v190);
  CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)v191);
  return (unsigned int)v39;
}

```

## disassembly

```asm
0x1402d61d8  mov     r11, rsp
0x1402d61db  mov     [r11+10h], rbx
0x1402d61df  mov     [r11+18h], rsi
0x1402d61e3  push    rdi
0x1402d61e4  push    r12
0x1402d61e6  push    r13
0x1402d61e8  push    r14
0x1402d61ea  push    r15
0x1402d61ec  sub     rsp, 4A0h
0x1402d61f3  mov     rax, cs:__security_cookie
0x1402d61fa  xor     rax, rsp
0x1402d61fd  mov     [rsp+4C8h+var_38], rax
0x1402d6205  mov     [rsp+4C8h+Src], rcx
0x1402d620d  xor     esi, esi
0x1402d620f  mov     [rsp+4C8h+var_420], sil
0x1402d6217  xorps   xmm0, xmm0
0x1402d621a  movups  xmmword ptr [r11-48h], xmm0
0x1402d621f  lea     rdx, [r11-48h]; ActivityId
0x1402d6223  lea     ecx, [rsi+3]; ControlCode
0x1402d6226  call    cs:__imp_EtwActivityIdControl
0x1402d622d  nop     dword ptr [rax+rax+00h]
0x1402d6232  lea     rax, [rsp+4C8h+var_420]
0x1402d623a  mov     [rsp+4C8h+Object], rax
0x1402d623f  lea     r9, [rsp+4C8h+var_418]
0x1402d6247  xor     r8d, r8d
0x1402d624a  lea     edx, [rsi+16h]
0x1402d624d  lea     rcx, [rsp+4C8h+var_48]
0x1402d6255  call    cs:__imp_?DisplayScenarioContextEnsureAndAssociate@@YAXAEBU_GUID@@IIAEAPEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@AEAE@Z; DisplayScenarioContextEnsureAndAssociate(_GUID const &,uint,uint,_DXGK_DISPLAY_SCENARIO_CONTEXT * &,uchar &)
0x1402d625c  nop     dword ptr [rax+rax+00h]
0x1402d6261  mov     rax, [rsp+4C8h+var_418]
0x1402d6269  mov     [rsp+4C8h+var_428], rax
0x1402d6271  call    cs:__imp_W32GetUserSessionState
0x1402d6278  nop     dword ptr [rax+rax+00h]
0x1402d627d  mov     eax, [rax+3F70h]
0x1402d6283  mov     [rsp+4C8h+var_454], eax
0x1402d6287  call    cs:__imp_W32GetUserSessionState
0x1402d628e  nop     dword ptr [rax+rax+00h]
0x1402d6293  mov     r14, rax
0x1402d6296  movzx   eax, word ptr [rax+10C80h]
0x1402d629d  mov     [rsp+4C8h+var_448], ax
0x1402d62a5  xor     edx, edx; Val
0x1402d62a7  mov     r8d, 140h; Size
0x1402d62ad  lea     rcx, [rsp+4C8h+var_188]; void *
0x1402d62b5  call    memset_0
0x1402d62ba  mov     [rsp+4C8h+var_458], esi
0x1402d62be  call    cs:__imp_GreGetRemoteContext
0x1402d62c5  nop     dword ptr [rax+rax+00h]
0x1402d62ca  mov     r13, rax
0x1402d62cd  lea     rcx, WPP_GLOBAL_Control
0x1402d62d4  mov     rax, cs:WPP_GLOBAL_Control
0x1402d62db  lea     r12d, [rsi+4]
0x1402d62df  cmp     rax, rcx
0x1402d62e2  jz      short loc_1402D62FB
0x1402d62e4  mov     ecx, [rax+2Ch]
0x1402d62e7  test    r12b, cl
0x1402d62ea  jz      short loc_1402D62FB
0x1402d62ec  cmp     [rax+29h], r12b
0x1402d62f0  jb      short loc_1402D62FB
0x1402d62f2  lea     r15d, [rsi+1]
0x1402d62f6  mov     bl, r15b
0x1402d62f9  jmp     short loc_1402D6304
0x1402d62fb  mov     bl, sil
0x1402d62fe  mov     r15d, 1
0x1402d6304  lea     rcx, WPP_RECORDER_INITIALIZED
0x1402d630b  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1402d6312  setnz   dil
0x1402d6316  test    bl, bl
0x1402d6318  jnz     short loc_1402D631F
0x1402d631a  test    dil, dil
0x1402d631d  jz      short loc_1402D6369
0x1402d631f  call    cs:__imp_W32GetUserSessionState
0x1402d6326  nop     dword ptr [rax+rax+00h]
0x1402d632b  mov     r9, [rax+10E20h]
0x1402d6332  lea     rsi, WPP_4ba15321700d32c32d46c236c92eb934_Traceguids
0x1402d6339  mov     [rsp+4C8h+var_490], rsi
0x1402d633e  mov     word ptr [rsp+4C8h+var_498], 10h
0x1402d6345  mov     dword ptr [rsp+4C8h+HandleInformation], 3
0x1402d634d  mov     byte ptr [rsp+4C8h+Object], r12b
0x1402d6352  mov     r8b, dil
0x1402d6355  mov     dl, bl
0x1402d6357  mov     rcx, cs:WPP_GLOBAL_Control
0x1402d635e  mov     rcx, [rcx+18h]
0x1402d6362  call    WPP_RECORDER_AND_TRACE_SF_
0x1402d6367  xor     esi, esi
0x1402d6369  call    cs:__imp_W32GetUserGdiSessionState
0x1402d6370  nop     dword ptr [rax+rax+00h]
0x1402d6375  mov     rbx, [rax+28h]
0x1402d6379  call    cs:__imp_PsGetCurrentProcess
0x1402d6380  nop     dword ptr [rax+rax+00h]
0x1402d6385  cmp     rax, rbx
0x1402d6388  jz      short loc_1402D63A1
0x1402d638a  lea     rcx, [rsp+4C8h+var_420]; this
0x1402d6392  call    ??1CDisplayScenarioContextScope@@QEAA@XZ; CDisplayScenarioContextScope::~CDisplayScenarioContextScope(void)
0x1402d6397  mov     eax, 0C0000022h
0x1402d639c  jmp     loc_1402D7197
0x1402d63a1  call    cs:__imp_W32GetUserSessionState
0x1402d63a8  nop     dword ptr [rax+rax+00h]
0x1402d63ad  or      dword ptr [rax+10D38h], 20h
0x1402d63b4  mov     ebx, 140h
0x1402d63b9  mov     r8d, ebx; Size
0x1402d63bc  xor     edx, edx; Val
0x1402d63be  lea     rcx, [rsp+4C8h+var_408]; void *
0x1402d63c6  call    memset_0
0x1402d63cb  mov     r8d, ebx; Size
0x1402d63ce  mov     rbx, [rsp+4C8h+Src]
0x1402d63d6  mov     rdx, rbx; Src
0x1402d63d9  lea     rcx, [rsp+4C8h+var_408]; void *
0x1402d63e1  call    RtlCopyFromUser
0x1402d63e6  lea     rax, [rsp+4C8h+var_2C8]
0x1402d63ee  lea     rcx, [rsp+4C8h+var_408]
0x1402d63f6  mov     r8d, 2
0x1402d63fc  mov     edx, r8d
0x1402d63ff  lea     r9d, [r8+7Eh]
0x1402d6403  movups  xmm0, xmmword ptr [rcx]
0x1402d6406  movups  xmmword ptr [rax], xmm0
0x1402d6409  movups  xmm1, xmmword ptr [rcx+10h]
0x1402d640d  movups  xmmword ptr [rax+10h], xmm1
0x1402d6411  movups  xmm0, xmmword ptr [rcx+20h]
0x1402d6415  movups  xmmword ptr [rax+20h], xmm0
0x1402d6419  movups  xmm1, xmmword ptr [rcx+30h]
0x1402d641d  movups  xmmword ptr [rax+30h], xmm1
0x1402d6421  movups  xmm0, xmmword ptr [rcx+40h]
0x1402d6425  movups  xmmword ptr [rax+40h], xmm0
0x1402d6429  movups  xmm1, xmmword ptr [rcx+50h]
0x1402d642d  movups  xmmword ptr [rax+50h], xmm1
0x1402d6431  movups  xmm0, xmmword ptr [rcx+60h]
0x1402d6435  movups  xmmword ptr [rax+60h], xmm0
0x1402d6439  movups  xmm1, xmmword ptr [rcx+70h]
0x1402d643d  movups  xmmword ptr [rax+70h], xmm1
0x1402d6441  add     rax, r9
0x1402d6444  add     rcx, r9
0x1402d6447  sub     rdx, 1
0x1402d644b  jnz     short loc_1402D6403
0x1402d644d  movups  xmm0, xmmword ptr [rcx]
0x1402d6450  movups  xmmword ptr [rax], xmm0
0x1402d6453  movups  xmm1, xmmword ptr [rcx+10h]
0x1402d6457  movups  xmmword ptr [rax+10h], xmm1
0x1402d645b  movups  xmm0, xmmword ptr [rcx+20h]
0x1402d645f  movups  xmmword ptr [rax+20h], xmm0
0x1402d6463  movups  xmm1, xmmword ptr [rcx+30h]
0x1402d6467  movups  xmmword ptr [rax+30h], xmm1
0x1402d646b  lea     rax, [rsp+4C8h+var_188]
0x1402d6473  lea     rcx, [rsp+4C8h+var_2C8]
0x1402d647b  mov     rdx, r8
0x1402d647e  movups  xmm0, xmmword ptr [rcx]
0x1402d6481  movups  xmmword ptr [rax], xmm0
0x1402d6484  movups  xmm1, xmmword ptr [rcx+10h]
0x1402d6488  movups  xmmword ptr [rax+10h], xmm1
0x1402d648c  movups  xmm0, xmmword ptr [rcx+20h]
0x1402d6490  movups  xmmword ptr [rax+20h], xmm0
0x1402d6494  movups  xmm1, xmmword ptr [rcx+30h]
0x1402d6498  movups  xmmword ptr [rax+30h], xmm1
0x1402d649c  movups  xmm0, xmmword ptr [rcx+40h]
0x1402d64a0  movups  xmmword ptr [rax+40h], xmm0
0x1402d64a4  movups  xmm1, xmmword ptr [rcx+50h]
0x1402d64a8  movups  xmmword ptr [rax+50h], xmm1
0x1402d64ac  movups  xmm0, xmmword ptr [rcx+60h]
0x1402d64b0  movups  xmmword ptr [rax+60h], xmm0
0x1402d64b4  movups  xmm1, xmmword ptr [rcx+70h]
0x1402d64b8  movups  xmmword ptr [rax+70h], xmm1
0x1402d64bc  add     rax, r9
0x1402d64bf  add     rcx, r9
0x1402d64c2  sub     rdx, 1
0x1402d64c6  jnz     short loc_1402D647E
0x1402d64c8  movups  xmm0, xmmword ptr [rcx]
0x1402d64cb  movups  xmmword ptr [rax], xmm0
0x1402d64ce  movups  xmm1, xmmword ptr [rcx+10h]
0x1402d64d2  movups  xmmword ptr [rax+10h], xmm1
0x1402d64d6  movups  xmm0, xmmword ptr [rcx+20h]
0x1402d64da  movups  xmmword ptr [rax+20h], xmm0
0x1402d64de  movups  xmm1, xmmword ptr [rcx+30h]
0x1402d64e2  movups  xmmword ptr [rax+30h], xmm1
0x1402d64e6  cmp     [r14+10CE4h], esi
0x1402d64ed  jz      short loc_1402D64F6
0x1402d64ef  mov     edi, 0C0000001h
0x1402d64f4  jmp     short loc_1402D6560
0x1402d64f6  mov     ecx, r15d
0x1402d64f9  call    cs:__imp_SetConsoleSwitchInProgress
0x1402d6500  nop     dword ptr [rax+rax+00h]
0x1402d6505  xor     ecx, ecx
0x1402d6507  call    SetMouseTrails
0x1402d650c  lea     rax, [r14+10D48h]
0x1402d6513  mov     [r14+10D30h], rax
0x1402d651a  lea     rdx, [r14+10C10h]
0x1402d6521  mov     rcx, [rsp+4C8h+var_158]
0x1402d6529  call    cs:__imp_PopulateUMKMHandlePair
0x1402d6530  nop     dword ptr [rax+rax+00h]
0x1402d6535  mov     edi, eax
0x1402d6537  test    eax, eax
0x1402d6539  js      short loc_1402D6560
0x1402d653b  lea     rdx, [r14+10C20h]
0x1402d6542  mov     rcx, [rsp+4C8h+var_150]
0x1402d654a  call    cs:__imp_PopulateUMKMHandlePair
0x1402d6551  nop     dword ptr [rax+rax+00h]
0x1402d6556  mov     esi, eax
0x1402d6558  xor     ecx, ecx
0x1402d655a  test    eax, eax
0x1402d655c  jns     short loc_1402D6574
0x1402d655e  mov     edi, eax
0x1402d6560  lea     rcx, [rsp+4C8h+var_420]; this
0x1402d6568  call    ??1CDisplayScenarioContextScope@@QEAA@XZ; CDisplayScenarioContextScope::~CDisplayScenarioContextScope(void)
0x1402d656d  mov     eax, edi
0x1402d656f  jmp     loc_1402D7197
0x1402d6574  mov     edi, ecx
0x1402d6576  mov     [rsp+4C8h+var_468], ecx
0x1402d657a  mov     [rsp+4C8h+var_444], ecx
0x1402d6581  mov     [rsp+4C8h+var_440], ecx
0x1402d6588  mov     eax, [rsp+4C8h+var_454]
0x1402d658c  inc     eax
0x1402d658e  mov     [rsp+4C8h+var_438], eax
0x1402d6595  mov     [rsp+4C8h+var_454], ecx
0x1402d6599  mov     [rsp+4C8h+var_43C], ecx
0x1402d65a0  mov     [rsp+4C8h+var_460], rcx
0x1402d65a5  mov     qword ptr [rsp+4C8h+var_48], rcx
0x1402d65ad  mov     eax, [rbx+14h]
0x1402d65b0  mov     [r14+10C08h], eax
0x1402d65b7  mov     eax, [rbx+18h]
0x1402d65ba  mov     [r14+10C0Ch], eax
0x1402d65c1  mov     rax, [rsp+4C8h+var_168]
0x1402d65c9  mov     [r14+10C00h], rax
0x1402d65d0  mov     rax, [rsp+4C8h+var_160]
0x1402d65d8  mov     [r14+10C30h], rax
0x1402d65df  mov     rax, [rsp+4C8h+var_148]
0x1402d65e7  mov     [r14+10C40h], rax
0x1402d65ee  movsd   xmm0, [rsp+4C8h+var_7C]
0x1402d65f7  movsd   qword ptr [r14+10CD8h], xmm0
0x1402d6600  mov     eax, [rsp+4C8h+var_74]
0x1402d6607  mov     [r14+10CE0h], eax
0x1402d660e  mov     ebx, [rsp+4C8h+var_98]
0x1402d6615  call    cs:__imp_W32GetUserSessionState
0x1402d661c  nop     dword ptr [rax+rax+00h]
0x1402d6621  mov     [rax+3F58h], ebx
0x1402d6627  mov     ebx, [rsp+4C8h+var_94]
0x1402d662e  call    cs:__imp_W32GetUserSessionState
0x1402d6635  nop     dword ptr [rax+rax+00h]
0x1402d663a  mov     [rax+369Ch], ebx
0x1402d6640  mov     eax, [r14+10BF8h]
0x1402d6647  mov     [rsp+4C8h+var_434], eax
0x1402d664e  mov     eax, [rsp+4C8h+var_64]
0x1402d6655  mov     [r14+10BF8h], eax
0x1402d665c  mov     eax, [rsp+4C8h+var_64]
0x1402d6663  mov     [r13+40h], eax
0x1402d6667  mov     rcx, [rsp+4C8h+Src]
0x1402d666f  mov     rax, [rcx+130h]
0x1402d6676  mov     [r14+10C48h], rax
0x1402d667d  mov     eax, [rcx+138h]
0x1402d6683  mov     [r14+10C50h], eax
0x1402d668a  lea     rax, [r14+10C54h]
0x1402d6691  movups  xmm0, xmmword ptr [rcx+0A2h]
0x1402d6698  movups  xmmword ptr [rax], xmm0
0x1402d669b  movups  xmm1, xmmword ptr [rcx+0B2h]
0x1402d66a2  movups  xmmword ptr [rax+10h], xmm1
0x1402d66a6  movsd   xmm0, qword ptr [rcx+0C2h]
0x1402d66ae  movsd   qword ptr [rax+20h], xmm0
0x1402d66b3  call    cs:__imp_W32GetUserSessionState
0x1402d66ba  nop     dword ptr [rax+rax+00h]
0x1402d66bf  mov     rdx, rax
0x1402d66c2  lea     rcx, [rax+0F990h]; Str
0x1402d66c9  movaps  xmm0, [rsp+4C8h+var_138]
0x1402d66d1  movups  xmmword ptr [rcx], xmm0
0x1402d66d4  movaps  xmm1, [rsp+4C8h+var_128]
0x1402d66dc  movups  xmmword ptr [rcx+10h], xmm1
0x1402d66e0  movaps  xmm0, [rsp+4C8h+var_118]
0x1402d66e8  movups  xmmword ptr [rcx+20h], xmm0
0x1402d66ec  movaps  xmm1, [rsp+4C8h+var_108]
0x1402d66f4  movups  xmmword ptr [rcx+30h], xmm1
0x1402d66f8  movups  xmm0, [rsp+4C8h+var_BE]
0x1402d6700  movups  xmmword ptr [rax+0F760h], xmm0
0x1402d6707  movzx   eax, [rsp+4C8h+var_AE]
0x1402d670f  mov     [rdx+0F770h], ax
0x1402d6716  movups  xmm0, [rsp+4C8h+var_AC]
0x1402d671e  movups  xmmword ptr [rdx+0F774h], xmm0
0x1402d6725  mov     eax, [rsp+4C8h+var_9C]
0x1402d672c  mov     [rdx+0F784h], eax
0x1402d6732  mov     edx, 23h ; '#'; Ch
0x1402d6737  call    cs:__imp_wcschr
0x1402d673e  nop     dword ptr [rax+rax+00h]
0x1402d6743  xor     ebx, ebx
0x1402d6745  test    rax, rax
0x1402d6748  jz      short loc_1402D674D
0x1402d674a  mov     [rax], bx
0x1402d674d  call    IsRemoteConnection
0x1402d6752  test    eax, eax
0x1402d6754  jz      short loc_1402D67A2
0x1402d6756  mov     dword ptr [rsp+4C8h+HandleInformation], ebx
0x1402d675a  lea     rax, [rsp+4C8h+var_458]
0x1402d675f  mov     [rsp+4C8h+Object], rax
0x1402d6764  xor     r9d, r9d
0x1402d6767  lea     r8, aCursorblinkena; "CursorBlinkEnable"
0x1402d676e  lea     edx, [r9+27h]
0x1402d6772  xor     ecx, ecx
0x1402d6774  call    cs:__imp_FastGetProfileIntW
0x1402d677b  nop     dword ptr [rax+rax+00h]
0x1402d6780  cmp     [rsp+4C8h+var_458], ebx
0x1402d6784  jnz     short loc_1402D67A2
0x1402d6786  call    cs:__imp_W32GetUserSessionState
0x1402d678d  nop     dword ptr [rax+rax+00h]
0x1402d6792  mov     rcx, [rax+4CF8h]
0x1402d6799  and     dword ptr [rcx+8BCh], 0FFFFFFFBh
0x1402d67a0  jmp     short loc_1402D67BC
  ... truncated ...
```
