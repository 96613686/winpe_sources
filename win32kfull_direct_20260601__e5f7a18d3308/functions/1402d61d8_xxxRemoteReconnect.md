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
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 UserSessionState; // r14
  __int64 v6; // rdx
  __int64 RemoteContext; // r13
  bool v8; // bl
  unsigned int *v9; // rcx
  bool v10; // di
  __int64 v11; // rax
  int v12; // r8d
  int v13; // edx
  __int64 v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v18; // rax
  _DWORD *v19; // rbx
  _OWORD *v20; // rax
  _OWORD *v21; // rcx
  __int64 v22; // rdx
  _OWORD *v23; // rax
  _OWORD *v24; // rcx
  __int64 v25; // rdx
  int v26; // edi
  int v27; // eax
  __int64 v28; // rdx
  NTSTATUS v29; // esi
  BOOL v30; // edi
  int v31; // ebx
  int v32; // ebx
  __int64 v33; // rdx
  __int64 v34; // rcx
  char *v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // rax
  wchar_t *v38; // rax
  __int64 v39; // rdx
  __int64 v40; // rcx
  int v41; // ebx
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rax
  _WORD *v47; // rcx
  __int64 v48; // rax
  size_t v49; // rbx
  void *v50; // rax
  void *v51; // rbx
  __int64 v52; // rdi
  struct _FILE_OBJECT *v53; // rcx
  __int64 v54; // rcx
  PVOID v55; // rdi
  __int64 v56; // rbx
  int v57; // eax
  __int64 v58; // rbx
  int inited; // eax
  void *v60; // rcx
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int16 v63; // ax
  unsigned __int16 v64; // bx
  __int64 v65; // rax
  __int64 v66; // rdx
  __int64 v67; // rcx
  __int64 v68; // rdx
  __int64 v69; // rcx
  NTSTATUS v70; // eax
  int v71; // eax
  __int64 v72; // rdx
  __int64 v73; // rcx
  __int64 v74; // rax
  __int64 v75; // rdx
  __int64 v76; // rcx
  unsigned int CurrentWin32kSessionId; // eax
  __int64 v78; // rdx
  __int64 v79; // r8
  __int64 v80; // r9
  __int64 v81; // rdx
  __int64 v82; // rcx
  int v83; // eax
  __int64 v84; // rdx
  __int64 v85; // rcx
  __int64 v86; // rax
  __int64 v87; // rax
  __int64 v88; // rdx
  __int64 v89; // rcx
  __int64 v90; // rax
  char v91; // bl
  bool v92; // di
  __int64 v93; // rax
  int v94; // r8d
  int v95; // edx
  __int64 v96; // rdx
  __int64 v97; // rcx
  __int64 v98; // rax
  unsigned int v99; // ebx
  __int64 v100; // rdx
  __int64 v101; // rcx
  __int64 v102; // rdx
  __int64 v103; // rcx
  __int64 v104; // r8
  __int64 v105; // rax
  __int64 v106; // rdx
  __int64 v107; // rcx
  __int64 v108; // rdx
  __int64 v109; // rcx
  __int64 v110; // rdx
  __int64 v111; // rcx
  __int64 v112; // rdx
  __int64 v113; // rcx
  __int64 v114; // rdx
  __int64 v115; // rcx
  __int64 v116; // rdx
  __int64 v117; // rcx
  bool v118; // di
  void (__fastcall *v119)(__int64, _QWORD); // rbx
  unsigned int RemoteDeviceCount; // eax
  __int64 v121; // rcx
  __int64 v122; // rdx
  __int64 v123; // rcx
  __int64 v124; // rdx
  PVOID *Object; // [rsp+20h] [rbp-4A8h]
  PVOID *Objecta; // [rsp+20h] [rbp-4A8h]
  int HandleInformation; // [rsp+28h] [rbp-4A0h]
  BOOL v128; // [rsp+60h] [rbp-468h]
  void *v129; // [rsp+68h] [rbp-460h]
  int v130; // [rsp+70h] [rbp-458h] BYREF
  int v131; // [rsp+74h] [rbp-454h]
  PVOID v132; // [rsp+78h] [rbp-450h] BYREF
  unsigned __int16 v133; // [rsp+80h] [rbp-448h]
  int v134; // [rsp+84h] [rbp-444h]
  int v135; // [rsp+88h] [rbp-440h]
  int v136; // [rsp+8Ch] [rbp-43Ch]
  unsigned int v137; // [rsp+90h] [rbp-438h]
  int v138; // [rsp+94h] [rbp-434h]
  void *Src; // [rsp+98h] [rbp-430h]
  struct _DXGK_DISPLAY_SCENARIO_CONTEXT *v140; // [rsp+A0h] [rbp-428h]
  unsigned __int8 v141[8]; // [rsp+A8h] [rbp-420h] BYREF
  struct _DXGK_DISPLAY_SCENARIO_CONTEXT *v142; // [rsp+B0h] [rbp-418h] BYREF
  _BYTE v143[320]; // [rsp+C0h] [rbp-408h] BYREF
  _BYTE v144[320]; // [rsp+200h] [rbp-2C8h] BYREF
  _BYTE v145[32]; // [rsp+340h] [rbp-188h] BYREF
  __int64 v146; // [rsp+360h] [rbp-168h]
  __int64 v147; // [rsp+368h] [rbp-160h]
  __int64 v148; // [rsp+370h] [rbp-158h]
  __int64 v149; // [rsp+378h] [rbp-150h]
  __int64 v150; // [rsp+380h] [rbp-148h]
  __int128 v151; // [rsp+390h] [rbp-138h]
  __int128 v152; // [rsp+3A0h] [rbp-128h]
  __int128 v153; // [rsp+3B0h] [rbp-118h]
  __int128 v154; // [rsp+3C0h] [rbp-108h]
  _BYTE v155[58]; // [rsp+3D0h] [rbp-F8h] BYREF
  __int128 v156; // [rsp+40Ah] [rbp-BEh]
  __int16 v157; // [rsp+41Ah] [rbp-AEh]
  __int128 v158; // [rsp+41Ch] [rbp-ACh]
  int v159; // [rsp+42Ch] [rbp-9Ch]
  int v160; // [rsp+430h] [rbp-98h]
  int v161; // [rsp+434h] [rbp-94h]
  unsigned __int16 v162; // [rsp+448h] [rbp-80h]
  __int64 v163; // [rsp+44Ch] [rbp-7Ch]
  int v164; // [rsp+454h] [rbp-74h]
  int v165; // [rsp+458h] [rbp-70h]
  int v166; // [rsp+45Ch] [rbp-6Ch]
  int v167; // [rsp+464h] [rbp-64h]
  GUID v168; // [rsp+480h] [rbp-48h] BYREF

  Src = a1;
  v141[0] = 0;
  v168 = 0;
  EtwActivityIdControl(3u, &v168);
  DisplayScenarioContextEnsureAndAssociate(&v168, 0x16u, 0, &v142, v141);
  v140 = v142;
  v131 = *(_DWORD *)(W32GetUserSessionState(v2, v1) + 16240);
  UserSessionState = W32GetUserSessionState(v4, v3);
  v133 = *(_WORD *)(UserSessionState + 68736);
  memset_0(v145, 0, 0x140u);
  v130 = 0;
  RemoteContext = GreGetRemoteContext();
  v8 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v9 = &WPP_RECORDER_INITIALIZED;
  v10 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v8 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v11 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, v6);
    LOBYTE(v12) = v10;
    LOBYTE(v13) = v8;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v13,
      v12,
      *(_QWORD *)(v11 + 69152),
      4,
      3,
      16,
      (__int64)WPP_4ba15321700d32c32d46c236c92eb934_Traceguids);
  }
  v14 = *(_QWORD *)(W32GetUserGdiSessionState(v9) + 40);
  if ( PsGetCurrentProcess() != v14 )
  {
    CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)v141);
    return 3221225506LL;
  }
  v18 = W32GetUserSessionState(v16, v15);
  *(_DWORD *)(v18 + 68920) |= 0x20u;
  memset_0(v143, 0, sizeof(v143));
  v19 = Src;
  RtlCopyFromUser(v143, Src, 0x140u);
  v20 = v144;
  v21 = v143;
  v22 = 2;
  do
  {
    *v20 = *v21;
    v20[1] = v21[1];
    v20[2] = v21[2];
    v20[3] = v21[3];
    v20[4] = v21[4];
    v20[5] = v21[5];
    v20[6] = v21[6];
    v20[7] = v21[7];
    v20 += 8;
    v21 += 8;
    --v22;
  }
  while ( v22 );
  *v20 = *v21;
  v20[1] = v21[1];
  v20[2] = v21[2];
  v20[3] = v21[3];
  v23 = v145;
  v24 = v144;
  v25 = 2;
  do
  {
    *v23 = *v24;
    v23[1] = v24[1];
    v23[2] = v24[2];
    v23[3] = v24[3];
    v23[4] = v24[4];
    v23[5] = v24[5];
    v23[6] = v24[6];
    v23[7] = v24[7];
    v23 += 8;
    v24 += 8;
    --v25;
  }
  while ( v25 );
  *v23 = *v24;
  v23[1] = v24[1];
  v23[2] = v24[2];
  v23[3] = v24[3];
  if ( *(_DWORD *)(UserSessionState + 68836) )
  {
    v26 = -1073741823;
LABEL_20:
    CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)v141);
    return (unsigned int)v26;
  }
  SetConsoleSwitchInProgress(1, 0, 2, 128);
  SetMouseTrails(0);
  *(_QWORD *)(UserSessionState + 68912) = UserSessionState + 68936;
  v26 = PopulateUMKMHandlePair(v148, UserSessionState + 68624);
  if ( v26 < 0 )
    goto LABEL_20;
  v27 = PopulateUMKMHandlePair(v149, UserSessionState + 68640);
  v29 = v27;
  if ( v27 < 0 )
  {
    v26 = v27;
    goto LABEL_20;
  }
  v30 = 0;
  v128 = 0;
  v134 = 0;
  v135 = 0;
  v137 = v131 + 1;
  v131 = 0;
  v136 = 0;
  v129 = 0;
  *(_QWORD *)&v168.Data1 = 0;
  *(_DWORD *)(UserSessionState + 68616) = v19[5];
  *(_DWORD *)(UserSessionState + 68620) = v19[6];
  *(_QWORD *)(UserSessionState + 68608) = v146;
  *(_QWORD *)(UserSessionState + 68656) = v147;
  *(_QWORD *)(UserSessionState + 68672) = v150;
  *(_QWORD *)(UserSessionState + 68824) = v163;
  *(_DWORD *)(UserSessionState + 68832) = v164;
  v31 = v160;
  *(_DWORD *)(W32GetUserSessionState(0, v28) + 16216) = v31;
  v32 = v161;
  *(_DWORD *)(W32GetUserSessionState(v34, v33) + 13980) = v32;
  v138 = *(_DWORD *)(UserSessionState + 68600);
  *(_DWORD *)(UserSessionState + 68600) = v167;
  *(_DWORD *)(RemoteContext + 64) = v167;
  v35 = (char *)Src;
  *(_QWORD *)(UserSessionState + 68680) = *((_QWORD *)Src + 38);
  *(_DWORD *)(UserSessionState + 68688) = *((_DWORD *)v35 + 78);
  *(_OWORD *)(UserSessionState + 68692) = *(_OWORD *)(v35 + 162);
  *(_OWORD *)(UserSessionState + 68708) = *(_OWORD *)(v35 + 178);
  *(_QWORD *)(UserSessionState + 68724) = *(_QWORD *)(v35 + 194);
  v37 = W32GetUserSessionState(v35, v36);
  *(_OWORD *)(v37 + 63888) = v151;
  *(_OWORD *)(v37 + 63904) = v152;
  *(_OWORD *)(v37 + 63920) = v153;
  *(_OWORD *)(v37 + 63936) = v154;
  *(_OWORD *)(v37 + 63328) = v156;
  *(_WORD *)(v37 + 63344) = v157;
  *(_OWORD *)(v37 + 63348) = v158;
  *(_DWORD *)(v37 + 63364) = v159;
  v38 = wcschr((const wchar_t *)(v37 + 63888), 0x23u);
  v41 = 0;
  if ( v38 )
    *v38 = 0;
  if ( !(unsigned int)IsRemoteConnection(v40, v39)
    || (HandleInformation = 0, Object = (PVOID *)&v130, FastGetProfileIntW(0, 39, L"CursorBlinkEnable"), v130) )
  {
    v46 = W32GetUserSessionState(v43, v42);
    *(_DWORD *)(*(_QWORD *)(v46 + 19704) + 2236LL) |= 4u;
  }
  else
  {
    v44 = W32GetUserSessionState(v43, v42);
    *(_DWORD *)(*(_QWORD *)(v44 + 19704) + 2236LL) &= ~4u;
  }
  v47 = *(_WORD **)(RemoteContext + 40);
  if ( v47 )
  {
    v48 = -1;
    do
      ++v48;
    while ( v47[v48] );
    *(_QWORD *)&v168.Data1 = v48 + 1;
    v49 = 2 * (v48 + 1);
    v50 = (void *)Win32AllocPoolWithQuotaZInit(v49, 2020897621);
    v129 = v50;
    if ( !v50 )
    {
      v29 = -1073741801;
      v51 = 0;
      goto LABEL_76;
    }
    memmove(v50, *(const void **)(RemoteContext + 40), v49);
    v41 = 0;
  }
  v52 = *(_QWORD *)(UserSessionState + 68896);
  if ( v52 || (v47 = *(_WORD **)(UserSessionState + 68608)) == 0 )
  {
    if ( !*(_QWORD *)(UserSessionState + 68608) )
    {
      v58 = *(_QWORD *)(UserSessionState + 68904);
      LODWORD(Object) = *(_DWORD *)(W32GetUserSessionState(v47, v45) + 68620);
      inited = GreMultiUserInitSession(
                 RemoteContext,
                 *(_QWORD *)(UserSessionState + 68672),
                 *(_QWORD *)(UserSessionState + 68912),
                 *(unsigned int *)(UserSessionState + 68616),
                 Object,
                 v52,
                 v58,
                 8,
                 v155,
                 19,
                 UserSessionState + 68692);
      v41 = 0;
      if ( !inited )
        v29 = -1073741823;
    }
  }
  else
  {
    v132 = 0;
    v29 = ObReferenceObjectByHandle(v47, 0, 0, 0, &v132, 0);
    if ( v29 >= 0 )
    {
      v53 = (struct _FILE_OBJECT *)v132;
      *(_QWORD *)(UserSessionState + 68896) = v132;
      IoGetRelatedDeviceObject(v53);
      v132 = 0;
      v29 = ObReferenceObjectByHandle(*(HANDLE *)(UserSessionState + 68672), 0, 0, 0, &v132, 0);
      v55 = v132;
      *(_QWORD *)(UserSessionState + 68904) = v132;
      if ( v29 >= 0 )
      {
        v56 = *(_QWORD *)(UserSessionState + 68896);
        LODWORD(Objecta) = *(_DWORD *)(W32GetUserSessionState(v54, v45) + 68620);
        v57 = GreMultiUserInitSession(
                RemoteContext,
                *(_QWORD *)(UserSessionState + 68672),
                *(_QWORD *)(UserSessionState + 68912),
                *(unsigned int *)(UserSessionState + 68616),
                Objecta,
                v56,
                v55,
                8,
                v155,
                19,
                UserSessionState + 68692);
        v41 = 0;
        if ( !v57 )
          v29 = -1073741823;
      }
    }
  }
  if ( v29 < 0 )
    goto LABEL_74;
  v60 = *(void **)(UserSessionState + 68656);
  if ( v60 )
  {
    v132 = 0;
    v29 = ObReferenceObjectByHandle(v60, 0, 0, 0, &v132, 0);
    *(_QWORD *)(UserSessionState + 68664) = v132;
  }
  if ( v29 < 0 )
    goto LABEL_74;
  if ( *(_DWORD *)(W32GetUserSessionState(v60, v45) + 68888) )
    xxxRemoteStopScreenUpdates();
  v63 = *(_WORD *)(UserSessionState + 69032);
  if ( v162 == v63 || !v63 )
  {
LABEL_60:
    SetProtocolType(v162);
    if ( !*(_WORD *)(W32GetUserSessionState(v67, v66) + 68736) )
      DrvNotifySessionStateChange(3);
    v136 = 1;
    if ( (unsigned int)UserRemoteConnectedSessionUsingXddm() )
    {
      if ( *(_WORD *)(UserSessionState + 68736) == *(_WORD *)(UserSessionState + 69032) )
      {
        v70 = GreDrvReconnect(RemoteContext);
      }
      else
      {
        v41 = 1;
        v70 = GreDrvConnect(RemoteContext);
      }
      v29 = v70;
      v128 = v70 >= 0;
    }
    else
    {
      v41 = 1;
      if ( !*(_WORD *)(W32GetUserSessionState(v69, v68) + 68736) )
      {
        v29 = DrvOpenLocalGraphicsDevices();
        if ( v29 < 0 )
        {
LABEL_74:
          v51 = v129;
          goto LABEL_75;
        }
        v135 = 1;
      }
    }
    v131 = 1;
    v71 = DrvSetGraphicsDevices(v155);
    v73 = 0;
    if ( v71 )
    {
      if ( (v165 || *(_WORD *)(UserSessionState + 68736) != *(_WORD *)(UserSessionState + 69032) || v166)
        && ((v87 = W32GetUserSessionState(0, v72),
             v29 = 0,
             !(unsigned int)DrvIsNotUsingGraphicsDevice(*(_QWORD *)(*(_QWORD *)(v87 + 56744) + 16LL)))
         || (unsigned int)DrvSessionHasAnyGraphicsDevice())
        && (DispBrokerUpdateKernelDisplayPolicies(),
            v90 = W32GetUserSessionState(v89, v88),
            LOBYTE(HandleInformation) = 0,
            v29 = xxxUserSetDisplayConfig(
                    0,
                    0,
                    v166 != 0 ? 2447 : 2191,
                    2050,
                    *(_QWORD *)(v90 + 19224),
                    HandleInformation,
                    0,
                    0,
                    0,
                    v140,
                    0),
            v72 = 0,
            v29 < 0) )
      {
        if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) == 0
          || (v91 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
        {
          v91 = 0;
        }
        v92 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
        if ( v91 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v93 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, 0);
          LOBYTE(v94) = v92;
          LOBYTE(v95) = v91;
          WPP_RECORDER_AND_TRACE_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v95,
            v94,
            *(_QWORD *)(v93 + 69152),
            4,
            3,
            17,
            (__int64)WPP_4ba15321700d32c32d46c236c92eb934_Traceguids);
        }
      }
      else
      {
        if ( (unsigned int)IsRemoteConnection(v73, v72) )
        {
          if ( v41 )
          {
            v98 = W32GetUserSessionState(v97, v96);
            v99 = 2;
            if ( !(unsigned int)DrvEscapeRemoteDrivers(
                                  *(_QWORD *)(*(_QWORD *)(v98 + 56744) + 16LL),
                                  *(unsigned __int16 *)(UserSessionState + 68736),
                                  *(_QWORD *)(RemoteContext + 40),
                                  2,
                                  *(_QWORD *)(UserSessionState + 68928),
                                  8) )
              v29 = -1073741823;
          }
          else
          {
            v99 = 2;
          }
          AttachInputDevices(0);
        }
        else
        {
          if ( *(_WORD *)(UserSessionState + 69032) )
            RemoveInputDevices();
          AttachInputDevices(1);
          xxxUserReinitializeAutoRotation();
          UserSessionSwitchLeaveCrit(v103, v102, v104);
          RegisterCDROMNotify();
          v134 = 1;
          EnterCrit(1, 0);
          v99 = 2;
        }
        v105 = W32GetUserSessionState(v101, v100);
        RemoteRedrawScreen(v105 + 19224);
        InitKeyboard();
        UpdateKeyLights(0);
        SetPointer(1);
        *(_DWORD *)(W32GetUserSessionState(v107, v106) + 36172) = 9;
        TransitionCursorSuppressionState(10);
        if ( *(_DWORD *)(W32GetUserSessionState(v109, v108) + 36172) == 1
          || *(_DWORD *)(W32GetUserSessionState(v111, v110) + 36172) == 5 )
        {
          v99 = *(_DWORD *)(W32GetUserSessionState(v111, v110) + 36172);
        }
        TransitionCursorSuppressionState(v99);
        SetConnectedState(1, *(unsigned int *)(UserSessionState + 68744));
        if ( !(unsigned int)IsRemoteConnection(v113, v112) || (FastGetProfileIntW(0, 39, L"CursorBlinkEnable"), v130) )
        {
          v117 = *(_QWORD *)(W32GetUserSessionState(v115, v114) + 19704);
          *(_DWORD *)(v117 + 2236) |= 4u;
        }
        else
        {
          v117 = *(_QWORD *)(W32GetUserSessionState(v115, v114) + 19704);
          *(_DWORD *)(v117 + 2236) &= ~4u;
        }
        v118 = *(_WORD *)(W32GetUserSessionState(v117, v116) + 68736) == 0;
        v119 = *(void (__fastcall **)(__int64, _QWORD))(DxDdGetDxgkWin32kInterface() + 384);
        RemoteDeviceCount = DrvGetRemoteDeviceCount();
        LOBYTE(v121) = v118;
        v119(v121, RemoteDeviceCount);
        LOBYTE(v124) = *(_WORD *)(W32GetUserSessionState(v123, v122) + 68736) == 0;
        CitSessionConnectChange(1, v124);
      }
    }
    else
    {
      if ( *(_DWORD *)(UserSessionState + 68888) )
      {
        v74 = W32GetUserSessionState(0, v72);
        RemoteRedrawScreen(v74 + 19224);
      }
      v29 = -1073741823;
    }
    goto LABEL_74;
  }
  v51 = v129;
  if ( v129 && !(unsigned int)GreMultiUserSetDisplayDriverName(RemoteContext, v168.Data1 - 1, v129) )
  {
    v29 = -1073741823;
LABEL_75:
    v30 = v128;
    goto LABEL_76;
  }
  v64 = *(_WORD *)(UserSessionState + 68736);
  v65 = W32GetUserSessionState(v62, v61);
  v29 = xxxRemoteSetDisconnectDisplayMode(*(struct tagDESKTOP **)(v65 + 19216), v64, v140);
  if ( v29 >= 0 )
  {
    if ( *((_DWORD *)Src + 72) )
      DrvCloseRemoteGraphicsDevices();
    v51 = v129;
    if ( v129 && !(unsigned int)GreMultiUserSetDisplayDriverName(RemoteContext, 8, v155) )
    {
      v29 = -1073741823;
      v30 = 0;
      goto LABEL_76;
    }
    v41 = 0;
    goto LABEL_60;
  }
  v30 = 0;
  v51 = v129;
LABEL_76:
  SetMouseTrails(v137);
  if ( v29 < 0 && v30 )
    GreDrvDisconnect(RemoteContext);
  if ( !v29 && !*(_WORD *)(W32GetUserSessionState(v76, v75) + 68736) )
  {
    CurrentWin32kSessionId = W32GetCurrentWin32kSessionId();
    RtlSetActiveConsoleId(CurrentWin32kSessionId);
  }
  if ( !*(_WORD *)(W32GetUserSessionState(v76, v75) + 68736) )
    DrvNotifySessionStateChange(4);
  if ( v29 < 0 )
    CleanupRemoteHandles(RemoteContext);
  SetConsoleSwitchInProgress(0, v78, v79, v80);
  DxgkEngNotifyDisplayChange(0);
  if ( v29 < 0 )
  {
    v83 = v138;
    *(_DWORD *)(UserSessionState + 68600) = v138;
    *(_DWORD *)(RemoteContext + 64) = v83;
    if ( v134 )
      UnregisterDeviceClassNotifications();
    if ( v135 )
      DrvCloseGraphicsDevices(1);
    if ( v136 )
      SetProtocolType(v133);
    if ( v131 )
      DrvSetGraphicsDevices(v155);
  }
  if ( v51 )
    Win32FreePool(v51);
  if ( !v29 )
  {
    if ( (unsigned int)IsRemoteConnection(v82, v81) )
    {
      v86 = W32GetUserSessionState(v85, v84);
      DrvEscapeRemoteDrivers(
        *(_QWORD *)(*(_QWORD *)(v86 + 56744) + 16LL),
        *(unsigned __int16 *)(UserSessionState + 68736),
        *(_QWORD *)(RemoteContext + 40),
        6,
        0,
        0);
    }
  }
  DrvOcclusionStateChangeNotify();
  DispBrokerAsyncSessionStateChanged(v140);
  CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)v141);
  return (unsigned int)v29;
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
