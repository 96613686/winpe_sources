# xxxRemoteReconnect

- ea: `0x1402d4318`
- end: `0x1402d5305`
- name: `xxxRemoteReconnect`
- size: `4077`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1402be830`

## callees

- `0x140038be0`
- `0x14003a604`
- `0x14003bb20`
- `0x140077cc8`
- `0x1400b71ac`
- `0x140192348`
- `0x140192724`
- `0x140192ac4`
- `0x1401939d0`
- `0x140193fac`
- `0x140194120`
- `0x140194224`
- `0x1402368a0`
- `0x140257540`
- `0x1402587b0`
- `0x140260c40`
- `0x140263878`
- `0x140285ed8`
- `0x140285ffc`
- `0x140286080`
- `0x140288d4c`
- `0x1402a4d38`
- `0x1402ab4fc`
- `0x1402d4318`
- `0x140327a94`
- `0x140341ff0`
- `0x1403420d0`
- `0x140342240`
- `0x140342540`

## import_xrefs

- `ntoskrnl!RtlSetActiveConsoleId` at `0x1402d4d9f`
- `ntoskrnl!RtlSetActiveConsoleId` at `0x1402d4d9f`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1402d49bb`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1402d49bb`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1402d4999`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1402d49ea`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1402d4b5a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1402d4999`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1402d49ea`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1402d4b5a`
- `ntoskrnl!EtwActivityIdControl` at `0x1402d4366`
- `ntoskrnl!EtwActivityIdControl` at `0x1402d4366`
- `ntoskrnl!PsGetCurrentProcess` at `0x1402d44b9`
- `ntoskrnl!PsGetCurrentProcess` at `0x1402d44b9`
- `ntoskrnl!wcschr` at `0x1402d4877`
- `ntoskrnl!wcschr` at `0x1402d4877`
- `watchdog!DisplayScenarioContextEnsureAndAssociate` at `0x1402d4395`
- `watchdog!DisplayScenarioContextEnsureAndAssociate` at `0x1402d4395`
- `win32kbase!FastGetProfileIntW` at `0x1402d48b4`
- `win32kbase!FastGetProfileIntW` at `0x1402d5209`
- `win32kbase!FastGetProfileIntW` at `0x1402d48b4`
- `win32kbase!FastGetProfileIntW` at `0x1402d5209`
- `win32kbase!xxxUserSetDisplayConfig` at `0x1402d4fce`
- `win32kbase!xxxUserSetDisplayConfig` at `0x1402d4fce`
- `win32kbase!UpdateKeyLights` at `0x1402d5153`
- `win32kbase!UpdateKeyLights` at `0x1402d5153`
- `win32kbase!DispBrokerAsyncSessionStateChanged` at `0x1402d4edb`
- `win32kbase!DispBrokerAsyncSessionStateChanged` at `0x1402d4edb`
- `win32kbase!SetProtocolType` at `0x1402d4c62`
- `win32kbase!SetProtocolType` at `0x1402d4e4b`
- `win32kbase!SetProtocolType` at `0x1402d4c62`
- `win32kbase!SetProtocolType` at `0x1402d4e4b`
- `win32kbase!DrvIsNotUsingGraphicsDevice` at `0x1402d4f3a`
- `win32kbase!DrvIsNotUsingGraphicsDevice` at `0x1402d4f3a`
- `win32kbase!SetConsoleSwitchInProgress` at `0x1402d4639`
- `win32kbase!SetConsoleSwitchInProgress` at `0x1402d4de4`
- `win32kbase!SetConsoleSwitchInProgress` at `0x1402d4639`
- `win32kbase!SetConsoleSwitchInProgress` at `0x1402d4de4`
- `win32kbase!DrvCloseGraphicsDevices` at `0x1402d4e2e`
- `win32kbase!DrvCloseGraphicsDevices` at `0x1402d4e2e`
- `win32kbase!SetConnectedState` at `0x1402d51d6`
- `win32kbase!SetConnectedState` at `0x1402d51d6`
- `win32kbase!CitSessionConnectChange` at `0x1402d52a8`
- `win32kbase!CitSessionConnectChange` at `0x1402d52a8`
- `win32kbase!DrvSetGraphicsDevices` at `0x1402d4d1f`
- `win32kbase!DrvSetGraphicsDevices` at `0x1402d4e65`
- `win32kbase!DrvSetGraphicsDevices` at `0x1402d4d1f`
- `win32kbase!DrvSetGraphicsDevices` at `0x1402d4e65`
- `win32kbase!CleanupRemoteHandles` at `0x1402d4dd6`
- `win32kbase!CleanupRemoteHandles` at `0x1402d4dd6`
- `win32kbase!PopulateUMKMHandlePair` at `0x1402d4669`
- `win32kbase!PopulateUMKMHandlePair` at `0x1402d468a`
- `win32kbase!PopulateUMKMHandlePair` at `0x1402d4669`
- `win32kbase!PopulateUMKMHandlePair` at `0x1402d468a`
- `win32kbase!GreMultiUserInitSession` at `0x1402d4a74`
- `win32kbase!GreMultiUserInitSession` at `0x1402d4b0b`
- `win32kbase!GreMultiUserInitSession` at `0x1402d4a74`
- `win32kbase!GreMultiUserInitSession` at `0x1402d4b0b`
- `win32kbase!UserRemoteConnectedSessionUsingXddm` at `0x1402d4c9c`
- `win32kbase!UserRemoteConnectedSessionUsingXddm` at `0x1402d4c9c`
- `win32kbase!GreDrvConnect` at `0x1402d4ccb`
- `win32kbase!GreDrvConnect` at `0x1402d4ccb`
- `win32kbase!DrvSessionHasAnyGraphicsDevice` at `0x1402d4f4c`
- `win32kbase!DrvSessionHasAnyGraphicsDevice` at `0x1402d4f4c`
- `win32kbase!DispBrokerUpdateKernelDisplayPolicies` at `0x1402d4f60`
- `win32kbase!DispBrokerUpdateKernelDisplayPolicies` at `0x1402d4f60`
- `win32kbase!DxgkEngNotifyDisplayChange` at `0x1402d4df2`
- `win32kbase!DxgkEngNotifyDisplayChange` at `0x1402d4df2`
- `win32kbase!DxDdGetDxgkWin32kInterface` at `0x1402d5268`
- `win32kbase!DxDdGetDxgkWin32kInterface` at `0x1402d5268`
- `win32kbase!DrvEscapeRemoteDrivers` at `0x1402d4ec2`
- `win32kbase!DrvEscapeRemoteDrivers` at `0x1402d50c4`
- `win32kbase!DrvEscapeRemoteDrivers` at `0x1402d4ec2`
- `win32kbase!DrvEscapeRemoteDrivers` at `0x1402d50c4`
- `win32kbase!DrvNotifySessionStateChange` at `0x1402d4c88`
- `win32kbase!DrvNotifySessionStateChange` at `0x1402d4dc3`
- `win32kbase!DrvNotifySessionStateChange` at `0x1402d4c88`
- `win32kbase!DrvNotifySessionStateChange` at `0x1402d4dc3`
- `win32kbase!GreGetRemoteContext` at `0x1402d43fe`
- `win32kbase!GreGetRemoteContext` at `0x1402d43fe`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1402d4929`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1402d4929`
- `win32kbase!EnterCrit` at `0x1402d5123`
- `win32kbase!EnterCrit` at `0x1402d5123`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1402d5105`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1402d5105`
- `win32kbase!Win32FreePool` at `0x1402d4e79`
- `win32kbase!Win32FreePool` at `0x1402d4e79`
- `WIN32K!W32GetUserGdiSessionState` at `0x1402d44a9`
- `WIN32K!W32GetUserGdiSessionState` at `0x1402d44a9`
- `WIN32K!W32GetUserSessionState` at `0x1402d43b1`
- `WIN32K!W32GetUserSessionState` at `0x1402d43c7`
- `WIN32K!W32GetUserSessionState` at `0x1402d445f`
- `WIN32K!W32GetUserSessionState` at `0x1402d44e1`
- `WIN32K!W32GetUserSessionState` at `0x1402d4755`
- `WIN32K!W32GetUserSessionState` at `0x1402d476e`
- `WIN32K!W32GetUserSessionState` at `0x1402d47f3`
- `WIN32K!W32GetUserSessionState` at `0x1402d48c6`
- `WIN32K!W32GetUserSessionState` at `0x1402d48e2`
- `WIN32K!W32GetUserSessionState` at `0x1402d4a13`
- `WIN32K!W32GetUserSessionState` at `0x1402d4aaa`
- `WIN32K!W32GetUserSessionState` at `0x1402d4b7c`
- `WIN32K!W32GetUserSessionState` at `0x1402d4be6`
- `WIN32K!W32GetUserSessionState` at `0x1402d4c6e`
- `WIN32K!W32GetUserSessionState` at `0x1402d4ce8`
- `WIN32K!W32GetUserSessionState` at `0x1402d4d3e`
- `WIN32K!W32GetUserSessionState` at `0x1402d4d83`
- `WIN32K!W32GetUserSessionState` at `0x1402d4dab`
- `WIN32K!W32GetUserSessionState` at `0x1402d4e92`
- `WIN32K!W32GetUserSessionState` at `0x1402d4f23`
- `WIN32K!W32GetUserSessionState` at `0x1402d4f6c`
- `WIN32K!W32GetUserSessionState` at `0x1402d502b`
- `WIN32K!W32GetUserSessionState` at `0x1402d5085`
- `WIN32K!W32GetUserSessionState` at `0x1402d5134`
- `WIN32K!W32GetUserSessionState` at `0x1402d5167`
- `WIN32K!W32GetUserSessionState` at `0x1402d5187`
- `WIN32K!W32GetUserSessionState` at `0x1402d519c`
- `WIN32K!W32GetUserSessionState` at `0x1402d51b1`
- `WIN32K!W32GetUserSessionState` at `0x1402d521b`
- `WIN32K!W32GetUserSessionState` at `0x1402d5237`
- `WIN32K!W32GetUserSessionState` at `0x1402d5251`
- `WIN32K!W32GetUserSessionState` at `0x1402d528d`
- `WIN32K!W32GetUserSessionState` at `0x1402d43b1`
- `WIN32K!W32GetUserSessionState` at `0x1402d43c7`
- `WIN32K!W32GetUserSessionState` at `0x1402d445f`
- `WIN32K!W32GetUserSessionState` at `0x1402d44e1`
- `WIN32K!W32GetUserSessionState` at `0x1402d4755`
- `WIN32K!W32GetUserSessionState` at `0x1402d476e`
- `WIN32K!W32GetUserSessionState` at `0x1402d47f3`
- `WIN32K!W32GetUserSessionState` at `0x1402d48c6`
- `WIN32K!W32GetUserSessionState` at `0x1402d48e2`
- `WIN32K!W32GetUserSessionState` at `0x1402d4a13`
- `WIN32K!W32GetUserSessionState` at `0x1402d4aaa`
- `WIN32K!W32GetUserSessionState` at `0x1402d4b7c`
- `WIN32K!W32GetUserSessionState` at `0x1402d4be6`
- `WIN32K!W32GetUserSessionState` at `0x1402d4c6e`
- `WIN32K!W32GetUserSessionState` at `0x1402d4ce8`
- `WIN32K!W32GetUserSessionState` at `0x1402d4d3e`
- `WIN32K!W32GetUserSessionState` at `0x1402d4d83`
- `WIN32K!W32GetUserSessionState` at `0x1402d4dab`
- `WIN32K!W32GetUserSessionState` at `0x1402d4e92`
- `WIN32K!W32GetUserSessionState` at `0x1402d4f23`
- `WIN32K!W32GetUserSessionState` at `0x1402d4f6c`
- `WIN32K!W32GetUserSessionState` at `0x1402d502b`
- `WIN32K!W32GetUserSessionState` at `0x1402d5085`
- `WIN32K!W32GetUserSessionState` at `0x1402d5134`
- `WIN32K!W32GetUserSessionState` at `0x1402d5167`
- `WIN32K!W32GetUserSessionState` at `0x1402d5187`
- `WIN32K!W32GetUserSessionState` at `0x1402d519c`
- `WIN32K!W32GetUserSessionState` at `0x1402d51b1`
- `WIN32K!W32GetUserSessionState` at `0x1402d521b`
- `WIN32K!W32GetUserSessionState` at `0x1402d5237`
- `WIN32K!W32GetUserSessionState` at `0x1402d5251`
- `WIN32K!W32GetUserSessionState` at `0x1402d528d`

## string_xrefs

- `0x1402d48a7`: `CursorBlinkEnable`
- `0x1402d51fc`: `CursorBlinkEnable`

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
  bool v15; // di
  __int64 v16; // rax
  int v17; // r8d
  int v18; // edx
  __int64 v19; // rbx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v25; // rax
  _DWORD *v26; // rbx
  _OWORD *v27; // rax
  _OWORD *v28; // rcx
  __int64 v29; // rdx
  _OWORD *v30; // rax
  _OWORD *v31; // rcx
  __int64 v32; // rdx
  int v33; // edi
  int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  NTSTATUS v38; // esi
  BOOL v39; // edi
  int v40; // ebx
  int v41; // ebx
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // r8
  __int64 v45; // r9
  char *v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 v50; // rax
  wchar_t *v51; // rax
  int v52; // ebx
  __int64 v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // r8
  __int64 v56; // r9
  __int64 v57; // rax
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 v60; // r9
  __int64 v61; // rax
  _WORD *v62; // rcx
  __int64 v63; // rax
  size_t v64; // rbx
  void *v65; // rax
  void *v66; // rbx
  __int64 v67; // rdi
  struct _FILE_OBJECT *v68; // rcx
  __int64 v69; // rcx
  PVOID v70; // rdi
  __int64 v71; // rbx
  int v72; // eax
  __int64 v73; // rbx
  int inited; // eax
  void *v75; // rcx
  __int64 v76; // rdx
  __int64 v77; // rcx
  __int64 v78; // r8
  __int64 v79; // r9
  __int16 v80; // ax
  unsigned __int16 v81; // bx
  __int64 v82; // rax
  __int64 v83; // rdx
  __int64 v84; // rcx
  __int64 v85; // r8
  __int64 v86; // r9
  __int64 v87; // rdx
  __int64 v88; // rcx
  __int64 v89; // r8
  __int64 v90; // r9
  NTSTATUS v91; // eax
  int v92; // eax
  __int64 v93; // rdx
  __int64 v94; // r8
  __int64 v95; // r9
  __int64 v96; // rcx
  __int64 v97; // rax
  __int64 v98; // rdx
  __int64 v99; // rcx
  __int64 v100; // r8
  __int64 v101; // r9
  unsigned int CurrentWin32kSessionId; // eax
  __int64 v103; // rdx
  __int64 v104; // r8
  __int64 v105; // r9
  __int64 v106; // rdx
  __int64 v107; // rcx
  int v108; // eax
  __int64 v109; // rdx
  __int64 v110; // rcx
  __int64 v111; // r8
  __int64 v112; // r9
  __int64 v113; // rax
  __int64 v114; // rax
  __int64 v115; // rdx
  __int64 v116; // rcx
  __int64 v117; // r8
  __int64 v118; // r9
  __int64 v119; // rax
  __int64 v120; // r8
  __int64 v121; // r9
  char v122; // bl
  bool v123; // di
  __int64 v124; // rax
  int v125; // r8d
  int v126; // edx
  __int64 v127; // rdx
  __int64 v128; // rcx
  __int64 v129; // r8
  __int64 v130; // r9
  __int64 v131; // rax
  unsigned int v132; // ebx
  __int64 v133; // rdx
  __int64 v134; // rcx
  __int64 v135; // r8
  __int64 v136; // r9
  __int64 v137; // rdx
  __int64 v138; // rcx
  __int64 v139; // r8
  __int64 v140; // rax
  __int64 v141; // rdx
  __int64 v142; // rcx
  __int64 v143; // r8
  __int64 v144; // r9
  __int64 v145; // rdx
  __int64 v146; // rcx
  __int64 v147; // r8
  __int64 v148; // r9
  __int64 v149; // rdx
  __int64 v150; // rcx
  __int64 v151; // r8
  __int64 v152; // r9
  __int64 v153; // rdx
  __int64 v154; // rcx
  __int64 v155; // rdx
  __int64 v156; // rcx
  __int64 v157; // r8
  __int64 v158; // r9
  __int64 v159; // rdx
  __int64 v160; // rcx
  __int64 v161; // r8
  __int64 v162; // r9
  bool v163; // di
  void (__fastcall *v164)(__int64, _QWORD); // rbx
  unsigned int RemoteDeviceCount; // eax
  __int64 v166; // rcx
  __int64 v167; // rdx
  __int64 v168; // rcx
  __int64 v169; // r8
  __int64 v170; // r9
  __int64 v171; // rdx
  PVOID *Object; // [rsp+20h] [rbp-4A8h]
  PVOID *Objecta; // [rsp+20h] [rbp-4A8h]
  int HandleInformation; // [rsp+28h] [rbp-4A0h]
  BOOL v175; // [rsp+60h] [rbp-468h]
  void *v176; // [rsp+68h] [rbp-460h]
  int v177; // [rsp+70h] [rbp-458h] BYREF
  int v178; // [rsp+74h] [rbp-454h]
  PVOID v179; // [rsp+78h] [rbp-450h] BYREF
  unsigned __int16 v180; // [rsp+80h] [rbp-448h]
  int v181; // [rsp+84h] [rbp-444h]
  int v182; // [rsp+88h] [rbp-440h]
  int v183; // [rsp+8Ch] [rbp-43Ch]
  unsigned int v184; // [rsp+90h] [rbp-438h]
  int v185; // [rsp+94h] [rbp-434h]
  void *Src; // [rsp+98h] [rbp-430h]
  struct _DXGK_DISPLAY_SCENARIO_CONTEXT *v187; // [rsp+A0h] [rbp-428h]
  unsigned __int8 v188[8]; // [rsp+A8h] [rbp-420h] BYREF
  struct _DXGK_DISPLAY_SCENARIO_CONTEXT *v189; // [rsp+B0h] [rbp-418h] BYREF
  _BYTE v190[320]; // [rsp+C0h] [rbp-408h] BYREF
  _BYTE v191[320]; // [rsp+200h] [rbp-2C8h] BYREF
  _BYTE v192[32]; // [rsp+340h] [rbp-188h] BYREF
  __int64 v193; // [rsp+360h] [rbp-168h]
  __int64 v194; // [rsp+368h] [rbp-160h]
  __int64 v195; // [rsp+370h] [rbp-158h]
  __int64 v196; // [rsp+378h] [rbp-150h]
  __int64 v197; // [rsp+380h] [rbp-148h]
  __int128 v198; // [rsp+390h] [rbp-138h]
  __int128 v199; // [rsp+3A0h] [rbp-128h]
  __int128 v200; // [rsp+3B0h] [rbp-118h]
  __int128 v201; // [rsp+3C0h] [rbp-108h]
  _BYTE v202[58]; // [rsp+3D0h] [rbp-F8h] BYREF
  __int128 v203; // [rsp+40Ah] [rbp-BEh]
  __int16 v204; // [rsp+41Ah] [rbp-AEh]
  __int128 v205; // [rsp+41Ch] [rbp-ACh]
  int v206; // [rsp+42Ch] [rbp-9Ch]
  int v207; // [rsp+430h] [rbp-98h]
  int v208; // [rsp+434h] [rbp-94h]
  unsigned __int16 v209; // [rsp+448h] [rbp-80h]
  __int64 v210; // [rsp+44Ch] [rbp-7Ch]
  int v211; // [rsp+454h] [rbp-74h]
  int v212; // [rsp+458h] [rbp-70h]
  int v213; // [rsp+45Ch] [rbp-6Ch]
  int v214; // [rsp+464h] [rbp-64h]
  GUID v215; // [rsp+480h] [rbp-48h] BYREF

  Src = a1;
  v188[0] = 0;
  v215 = 0;
  EtwActivityIdControl(3u, &v215);
  DisplayScenarioContextEnsureAndAssociate(&v215, 0x16u, 0, &v189, v188);
  v187 = v189;
  v178 = *(_DWORD *)(W32GetUserSessionState(v2, v1, v3, v4) + 16240);
  UserSessionState = W32GetUserSessionState(v6, v5, v7, v8);
  v180 = *(_WORD *)(UserSessionState + 68736);
  memset_0(v192, 0, 0x140u);
  v177 = 0;
  RemoteContext = GreGetRemoteContext();
  v14 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v15 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v14 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v16 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, v10, v11, v12);
    LOBYTE(v17) = v15;
    LOBYTE(v18) = v14;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v18,
      v17,
      *(_QWORD *)(v16 + 69152),
      4,
      3,
      16,
      (__int64)WPP_4ba15321700d32c32d46c236c92eb934_Traceguids);
  }
  v19 = *(_QWORD *)(W32GetUserGdiSessionState() + 40);
  if ( PsGetCurrentProcess() != v19 )
  {
    CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)v188);
    return 3221225506LL;
  }
  v25 = W32GetUserSessionState(v21, v20, v22, v23);
  *(_DWORD *)(v25 + 68920) |= 0x20u;
  memset_0(v190, 0, sizeof(v190));
  v26 = Src;
  RtlCopyFromUser(v190, Src, 0x140u);
  v27 = v191;
  v28 = v190;
  v29 = 2;
  do
  {
    *v27 = *v28;
    v27[1] = v28[1];
    v27[2] = v28[2];
    v27[3] = v28[3];
    v27[4] = v28[4];
    v27[5] = v28[5];
    v27[6] = v28[6];
    v27[7] = v28[7];
    v27 += 8;
    v28 += 8;
    --v29;
  }
  while ( v29 );
  *v27 = *v28;
  v27[1] = v28[1];
  v27[2] = v28[2];
  v27[3] = v28[3];
  v30 = v192;
  v31 = v191;
  v32 = 2;
  do
  {
    *v30 = *v31;
    v30[1] = v31[1];
    v30[2] = v31[2];
    v30[3] = v31[3];
    v30[4] = v31[4];
    v30[5] = v31[5];
    v30[6] = v31[6];
    v30[7] = v31[7];
    v30 += 8;
    v31 += 8;
    --v32;
  }
  while ( v32 );
  *v30 = *v31;
  v30[1] = v31[1];
  v30[2] = v31[2];
  v30[3] = v31[3];
  if ( *(_DWORD *)(UserSessionState + 68836) )
  {
    v33 = -1073741823;
LABEL_20:
    CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)v188);
    return (unsigned int)v33;
  }
  SetConsoleSwitchInProgress(1, 0, 2, 128);
  SetMouseTrails(0);
  *(_QWORD *)(UserSessionState + 68912) = UserSessionState + 68936;
  v33 = PopulateUMKMHandlePair(v195, UserSessionState + 68624);
  if ( v33 < 0 )
    goto LABEL_20;
  v34 = PopulateUMKMHandlePair(v196, UserSessionState + 68640);
  v38 = v34;
  if ( v34 < 0 )
  {
    v33 = v34;
    goto LABEL_20;
  }
  v39 = 0;
  v175 = 0;
  v181 = 0;
  v182 = 0;
  v184 = v178 + 1;
  v178 = 0;
  v183 = 0;
  v176 = 0;
  *(_QWORD *)&v215.Data1 = 0;
  *(_DWORD *)(UserSessionState + 68616) = v26[5];
  *(_DWORD *)(UserSessionState + 68620) = v26[6];
  *(_QWORD *)(UserSessionState + 68608) = v193;
  *(_QWORD *)(UserSessionState + 68656) = v194;
  *(_QWORD *)(UserSessionState + 68672) = v197;
  *(_QWORD *)(UserSessionState + 68824) = v210;
  *(_DWORD *)(UserSessionState + 68832) = v211;
  v40 = v207;
  *(_DWORD *)(W32GetUserSessionState(0, v35, v36, v37) + 16216) = v40;
  v41 = v208;
  *(_DWORD *)(W32GetUserSessionState(v43, v42, v44, v45) + 13980) = v41;
  v185 = *(_DWORD *)(UserSessionState + 68600);
  *(_DWORD *)(UserSessionState + 68600) = v214;
  *(_DWORD *)(RemoteContext + 64) = v214;
  v46 = (char *)Src;
  *(_QWORD *)(UserSessionState + 68680) = *((_QWORD *)Src + 38);
  *(_DWORD *)(UserSessionState + 68688) = *((_DWORD *)v46 + 78);
  *(_OWORD *)(UserSessionState + 68692) = *(_OWORD *)(v46 + 162);
  *(_OWORD *)(UserSessionState + 68708) = *(_OWORD *)(v46 + 178);
  *(_QWORD *)(UserSessionState + 68724) = *(_QWORD *)(v46 + 194);
  v50 = W32GetUserSessionState(v46, v47, v48, v49);
  *(_OWORD *)(v50 + 63888) = v198;
  *(_OWORD *)(v50 + 63904) = v199;
  *(_OWORD *)(v50 + 63920) = v200;
  *(_OWORD *)(v50 + 63936) = v201;
  *(_OWORD *)(v50 + 63328) = v203;
  *(_WORD *)(v50 + 63344) = v204;
  *(_OWORD *)(v50 + 63348) = v205;
  *(_DWORD *)(v50 + 63364) = v206;
  v51 = wcschr((const wchar_t *)(v50 + 63888), 0x23u);
  v52 = 0;
  if ( v51 )
    *v51 = 0;
  if ( !(unsigned int)((__int64 (*)(void))IsRemoteConnection)()
    || (HandleInformation = 0, Object = (PVOID *)&v177, FastGetProfileIntW(0, 39, L"CursorBlinkEnable"), v177) )
  {
    v61 = W32GetUserSessionState(v54, v53, v55, v56);
    *(_DWORD *)(*(_QWORD *)(v61 + 19704) + 2236LL) |= 4u;
  }
  else
  {
    v57 = W32GetUserSessionState(v54, v53, v55, v56);
    *(_DWORD *)(*(_QWORD *)(v57 + 19704) + 2236LL) &= ~4u;
  }
  v62 = *(_WORD **)(RemoteContext + 40);
  if ( v62 )
  {
    v63 = -1;
    do
      ++v63;
    while ( v62[v63] );
    *(_QWORD *)&v215.Data1 = v63 + 1;
    v64 = 2 * (v63 + 1);
    v65 = (void *)Win32AllocPoolWithQuotaZInit(v64, 2020897621);
    v176 = v65;
    if ( !v65 )
    {
      v38 = -1073741801;
      v66 = 0;
      goto LABEL_76;
    }
    memmove(v65, *(const void **)(RemoteContext + 40), v64);
    v52 = 0;
  }
  v67 = *(_QWORD *)(UserSessionState + 68896);
  if ( v67 || (v62 = *(_WORD **)(UserSessionState + 68608)) == 0 )
  {
    if ( !*(_QWORD *)(UserSessionState + 68608) )
    {
      v73 = *(_QWORD *)(UserSessionState + 68904);
      LODWORD(Object) = *(_DWORD *)(W32GetUserSessionState(v62, v58, v59, v60) + 68620);
      inited = GreMultiUserInitSession(
                 RemoteContext,
                 *(_QWORD *)(UserSessionState + 68672),
                 *(_QWORD *)(UserSessionState + 68912),
                 *(unsigned int *)(UserSessionState + 68616),
                 Object,
                 v67,
                 v73,
                 8,
                 v202,
                 19,
                 UserSessionState + 68692);
      v52 = 0;
      if ( !inited )
        v38 = -1073741823;
    }
  }
  else
  {
    v179 = 0;
    v38 = ObReferenceObjectByHandle(v62, 0, 0, 0, &v179, 0);
    if ( v38 >= 0 )
    {
      v68 = (struct _FILE_OBJECT *)v179;
      *(_QWORD *)(UserSessionState + 68896) = v179;
      IoGetRelatedDeviceObject(v68);
      v179 = 0;
      v38 = ObReferenceObjectByHandle(*(HANDLE *)(UserSessionState + 68672), 0, 0, 0, &v179, 0);
      v70 = v179;
      *(_QWORD *)(UserSessionState + 68904) = v179;
      if ( v38 >= 0 )
      {
        v71 = *(_QWORD *)(UserSessionState + 68896);
        LODWORD(Objecta) = *(_DWORD *)(W32GetUserSessionState(v69, v58, v59, v60) + 68620);
        v72 = GreMultiUserInitSession(
                RemoteContext,
                *(_QWORD *)(UserSessionState + 68672),
                *(_QWORD *)(UserSessionState + 68912),
                *(unsigned int *)(UserSessionState + 68616),
                Objecta,
                v71,
                v70,
                8,
                v202,
                19,
                UserSessionState + 68692);
        v52 = 0;
        if ( !v72 )
          v38 = -1073741823;
      }
    }
  }
  if ( v38 < 0 )
    goto LABEL_74;
  v75 = *(void **)(UserSessionState + 68656);
  if ( v75 )
  {
    v179 = 0;
    v38 = ObReferenceObjectByHandle(v75, 0, 0, 0, &v179, 0);
    *(_QWORD *)(UserSessionState + 68664) = v179;
  }
  if ( v38 < 0 )
    goto LABEL_74;
  if ( *(_DWORD *)(W32GetUserSessionState(v75, v58, v59, v60) + 68888) )
    xxxRemoteStopScreenUpdates();
  v80 = *(_WORD *)(UserSessionState + 69032);
  if ( v209 == v80 || !v80 )
  {
LABEL_60:
    SetProtocolType(v209);
    if ( !*(_WORD *)(W32GetUserSessionState(v84, v83, v85, v86) + 68736) )
      DrvNotifySessionStateChange(3);
    v183 = 1;
    if ( (unsigned int)UserRemoteConnectedSessionUsingXddm() )
    {
      if ( *(_WORD *)(UserSessionState + 68736) == *(_WORD *)(UserSessionState + 69032) )
      {
        v91 = GreDrvReconnect(RemoteContext);
      }
      else
      {
        v52 = 1;
        v91 = GreDrvConnect(RemoteContext);
      }
      v38 = v91;
      v175 = v91 >= 0;
    }
    else
    {
      v52 = 1;
      if ( !*(_WORD *)(W32GetUserSessionState(v88, v87, v89, v90) + 68736) )
      {
        v38 = DrvOpenLocalGraphicsDevices();
        if ( v38 < 0 )
        {
LABEL_74:
          v66 = v176;
          goto LABEL_75;
        }
        v182 = 1;
      }
    }
    v178 = 1;
    v92 = DrvSetGraphicsDevices(v202);
    v96 = 0;
    if ( v92 )
    {
      if ( (v212 || *(_WORD *)(UserSessionState + 68736) != *(_WORD *)(UserSessionState + 69032) || v213)
        && ((v114 = W32GetUserSessionState(0, v93, v94, v95),
             v38 = 0,
             !(unsigned int)DrvIsNotUsingGraphicsDevice(*(_QWORD *)(*(_QWORD *)(v114 + 56744) + 16LL)))
         || (unsigned int)DrvSessionHasAnyGraphicsDevice())
        && (DispBrokerUpdateKernelDisplayPolicies(),
            v119 = W32GetUserSessionState(v116, v115, v117, v118),
            LOBYTE(HandleInformation) = 0,
            v38 = xxxUserSetDisplayConfig(
                    0,
                    0,
                    v213 != 0 ? 2447 : 2191,
                    2050,
                    *(_QWORD *)(v119 + 19224),
                    HandleInformation,
                    0,
                    0,
                    0,
                    v187,
                    0),
            v93 = 0,
            v38 < 0) )
      {
        if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) == 0
          || (v122 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
        {
          v122 = 0;
        }
        v123 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
        if ( v122 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v124 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, 0, v120, v121);
          LOBYTE(v125) = v123;
          LOBYTE(v126) = v122;
          WPP_RECORDER_AND_TRACE_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v126,
            v125,
            *(_QWORD *)(v124 + 69152),
            4,
            3,
            17,
            (__int64)WPP_4ba15321700d32c32d46c236c92eb934_Traceguids);
        }
      }
      else
      {
        if ( (unsigned int)IsRemoteConnection(v96, v93) )
        {
          if ( v52 )
          {
            v131 = W32GetUserSessionState(v128, v127, v129, v130);
            v132 = 2;
            if ( !(unsigned int)DrvEscapeRemoteDrivers(
                                  *(_QWORD *)(*(_QWORD *)(v131 + 56744) + 16LL),
                                  *(unsigned __int16 *)(UserSessionState + 68736),
                                  *(_QWORD *)(RemoteContext + 40),
                                  2,
                                  *(_QWORD *)(UserSessionState + 68928),
                                  8) )
              v38 = -1073741823;
          }
          else
          {
            v132 = 2;
          }
          AttachInputDevices(0);
        }
        else
        {
          if ( *(_WORD *)(UserSessionState + 69032) )
            RemoveInputDevices();
          AttachInputDevices(1);
          xxxUserReinitializeAutoRotation();
          UserSessionSwitchLeaveCrit(v138, v137, v139);
          RegisterCDROMNotify();
          v181 = 1;
          EnterCrit(1, 0);
          v132 = 2;
        }
        v140 = W32GetUserSessionState(v134, v133, v135, v136);
        RemoteRedrawScreen(v140 + 19224);
        InitKeyboard();
        UpdateKeyLights(0);
        SetPointer(1);
        *(_DWORD *)(W32GetUserSessionState(v142, v141, v143, v144) + 36172) = 9;
        TransitionCursorSuppressionState(10);
        if ( *(_DWORD *)(W32GetUserSessionState(v146, v145, v147, v148) + 36172) == 1
          || *(_DWORD *)(W32GetUserSessionState(v150, v149, v151, v152) + 36172) == 5 )
        {
          v132 = *(_DWORD *)(W32GetUserSessionState(v150, v149, v151, v152) + 36172);
        }
        TransitionCursorSuppressionState(v132);
        SetConnectedState(1, *(unsigned int *)(UserSessionState + 68744));
        if ( !(unsigned int)IsRemoteConnection(v154, v153) || (FastGetProfileIntW(0, 39, L"CursorBlinkEnable"), v177) )
        {
          v160 = *(_QWORD *)(W32GetUserSessionState(v156, v155, v157, v158) + 19704);
          *(_DWORD *)(v160 + 2236) |= 4u;
        }
        else
        {
          v160 = *(_QWORD *)(W32GetUserSessionState(v156, v155, v157, v158) + 19704);
          *(_DWORD *)(v160 + 2236) &= ~4u;
        }
        v163 = *(_WORD *)(W32GetUserSessionState(v160, v159, v161, v162) + 68736) == 0;
        v164 = *(void (__fastcall **)(__int64, _QWORD))(DxDdGetDxgkWin32kInterface() + 384);
        RemoteDeviceCount = DrvGetRemoteDeviceCount();
        LOBYTE(v166) = v163;
        v164(v166, RemoteDeviceCount);
        LOBYTE(v171) = *(_WORD *)(W32GetUserSessionState(v168, v167, v169, v170) + 68736) == 0;
        CitSessionConnectChange(1, v171);
      }
    }
    else
    {
      if ( *(_DWORD *)(UserSessionState + 68888) )
      {
        v97 = W32GetUserSessionState(0, v93, v94, v95);
        RemoteRedrawScreen(v97 + 19224);
      }
      v38 = -1073741823;
    }
    goto LABEL_74;
  }
  v66 = v176;
  if ( v176 && !(unsigned int)GreMultiUserSetDisplayDriverName(RemoteContext, v215.Data1 - 1, v176) )
  {
    v38 = -1073741823;
LABEL_75:
    v39 = v175;
    goto LABEL_76;
  }
  v81 = *(_WORD *)(UserSessionState + 68736);
  v82 = W32GetUserSessionState(v77, v76, v78, v79);
  v38 = xxxRemoteSetDisconnectDisplayMode(*(struct tagDESKTOP **)(v82 + 19216), v81, v187);
  if ( v38 >= 0 )
  {
    if ( *((_DWORD *)Src + 72) )
      DrvCloseRemoteGraphicsDevices();
    v66 = v176;
    if ( v176 && !(unsigned int)GreMultiUserSetDisplayDriverName(RemoteContext, 8, v202) )
    {
      v38 = -1073741823;
      v39 = 0;
      goto LABEL_76;
    }
    v52 = 0;
    goto LABEL_60;
  }
  v39 = 0;
  v66 = v176;
LABEL_76:
  SetMouseTrails(v184);
  if ( v38 < 0 && v39 )
    GreDrvDisconnect(RemoteContext);
  if ( !v38 && !*(_WORD *)(W32GetUserSessionState(v99, v98, v100, v101) + 68736) )
  {
    CurrentWin32kSessionId = W32GetCurrentWin32kSessionId();
    RtlSetActiveConsoleId(CurrentWin32kSessionId);
  }
  if ( !*(_WORD *)(W32GetUserSessionState(v99, v98, v100, v101) + 68736) )
    DrvNotifySessionStateChange(4);
  if ( v38 < 0 )
    CleanupRemoteHandles(RemoteContext);
  SetConsoleSwitchInProgress(0, v103, v104, v105);
  DxgkEngNotifyDisplayChange(0);
  if ( v38 < 0 )
  {
    v108 = v185;
    *(_DWORD *)(UserSessionState + 68600) = v185;
    *(_DWORD *)(RemoteContext + 64) = v108;
    if ( v181 )
      UnregisterDeviceClassNotifications();
    if ( v182 )
      DrvCloseGraphicsDevices(1);
    if ( v183 )
      SetProtocolType(v180);
    if ( v178 )
      DrvSetGraphicsDevices(v202);
  }
  if ( v66 )
    Win32FreePool(v66);
  if ( !v38 )
  {
    if ( (unsigned int)IsRemoteConnection(v107, v106) )
    {
      v113 = W32GetUserSessionState(v110, v109, v111, v112);
      DrvEscapeRemoteDrivers(
        *(_QWORD *)(*(_QWORD *)(v113 + 56744) + 16LL),
        *(unsigned __int16 *)(UserSessionState + 68736),
        *(_QWORD *)(RemoteContext + 40),
        6,
        0,
        0);
    }
  }
  DrvOcclusionStateChangeNotify();
  DispBrokerAsyncSessionStateChanged(v187);
  CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)v188);
  return (unsigned int)v38;
}

```

## disassembly

```asm
0x1402d4318  mov     r11, rsp
0x1402d431b  mov     [r11+10h], rbx
0x1402d431f  mov     [r11+18h], rsi
0x1402d4323  push    rdi
0x1402d4324  push    r12
0x1402d4326  push    r13
0x1402d4328  push    r14
0x1402d432a  push    r15
0x1402d432c  sub     rsp, 4A0h
0x1402d4333  mov     rax, cs:__security_cookie
0x1402d433a  xor     rax, rsp
0x1402d433d  mov     [rsp+4C8h+var_38], rax
0x1402d4345  mov     [rsp+4C8h+Src], rcx
0x1402d434d  xor     esi, esi
0x1402d434f  mov     [rsp+4C8h+var_420], sil
0x1402d4357  xorps   xmm0, xmm0
0x1402d435a  movups  xmmword ptr [r11-48h], xmm0
0x1402d435f  lea     rdx, [r11-48h]; ActivityId
0x1402d4363  lea     ecx, [rsi+3]; ControlCode
0x1402d4366  call    cs:__imp_EtwActivityIdControl
0x1402d436d  nop     dword ptr [rax+rax+00h]
0x1402d4372  lea     rax, [rsp+4C8h+var_420]
0x1402d437a  mov     [rsp+4C8h+Object], rax
0x1402d437f  lea     r9, [rsp+4C8h+var_418]
0x1402d4387  xor     r8d, r8d
0x1402d438a  lea     edx, [rsi+16h]
0x1402d438d  lea     rcx, [rsp+4C8h+var_48]
0x1402d4395  call    cs:__imp_?DisplayScenarioContextEnsureAndAssociate@@YAXAEBU_GUID@@IIAEAPEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@AEAE@Z; DisplayScenarioContextEnsureAndAssociate(_GUID const &,uint,uint,_DXGK_DISPLAY_SCENARIO_CONTEXT * &,uchar &)
0x1402d439c  nop     dword ptr [rax+rax+00h]
0x1402d43a1  mov     rax, [rsp+4C8h+var_418]
0x1402d43a9  mov     [rsp+4C8h+var_428], rax
0x1402d43b1  call    cs:__imp_W32GetUserSessionState
0x1402d43b8  nop     dword ptr [rax+rax+00h]
0x1402d43bd  mov     eax, [rax+3F70h]
0x1402d43c3  mov     [rsp+4C8h+var_454], eax
0x1402d43c7  call    cs:__imp_W32GetUserSessionState
0x1402d43ce  nop     dword ptr [rax+rax+00h]
0x1402d43d3  mov     r14, rax
0x1402d43d6  movzx   eax, word ptr [rax+10C80h]
0x1402d43dd  mov     [rsp+4C8h+var_448], ax
0x1402d43e5  xor     edx, edx; Val
0x1402d43e7  mov     r8d, 140h; Size
0x1402d43ed  lea     rcx, [rsp+4C8h+var_188]; void *
0x1402d43f5  call    memset_0
0x1402d43fa  mov     [rsp+4C8h+var_458], esi
0x1402d43fe  call    cs:__imp_GreGetRemoteContext
0x1402d4405  nop     dword ptr [rax+rax+00h]
0x1402d440a  mov     r13, rax
0x1402d440d  lea     rcx, WPP_GLOBAL_Control
0x1402d4414  mov     rax, cs:WPP_GLOBAL_Control
0x1402d441b  lea     r12d, [rsi+4]
0x1402d441f  cmp     rax, rcx
0x1402d4422  jz      short loc_1402D443B
0x1402d4424  mov     ecx, [rax+2Ch]
0x1402d4427  test    r12b, cl
0x1402d442a  jz      short loc_1402D443B
0x1402d442c  cmp     [rax+29h], r12b
0x1402d4430  jb      short loc_1402D443B
0x1402d4432  lea     r15d, [rsi+1]
0x1402d4436  mov     bl, r15b
0x1402d4439  jmp     short loc_1402D4444
0x1402d443b  mov     bl, sil
0x1402d443e  mov     r15d, 1
0x1402d4444  lea     rcx, WPP_RECORDER_INITIALIZED
0x1402d444b  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1402d4452  setnz   dil
0x1402d4456  test    bl, bl
0x1402d4458  jnz     short loc_1402D445F
0x1402d445a  test    dil, dil
0x1402d445d  jz      short loc_1402D44A9
0x1402d445f  call    cs:__imp_W32GetUserSessionState
0x1402d4466  nop     dword ptr [rax+rax+00h]
0x1402d446b  mov     r9, [rax+10E20h]
0x1402d4472  lea     rsi, WPP_4ba15321700d32c32d46c236c92eb934_Traceguids
0x1402d4479  mov     [rsp+4C8h+var_490], rsi
0x1402d447e  mov     word ptr [rsp+4C8h+var_498], 10h
0x1402d4485  mov     dword ptr [rsp+4C8h+HandleInformation], 3
0x1402d448d  mov     byte ptr [rsp+4C8h+Object], r12b
0x1402d4492  mov     r8b, dil
0x1402d4495  mov     dl, bl
0x1402d4497  mov     rcx, cs:WPP_GLOBAL_Control
0x1402d449e  mov     rcx, [rcx+18h]
0x1402d44a2  call    WPP_RECORDER_AND_TRACE_SF_
0x1402d44a7  xor     esi, esi
0x1402d44a9  call    cs:__imp_W32GetUserGdiSessionState
0x1402d44b0  nop     dword ptr [rax+rax+00h]
0x1402d44b5  mov     rbx, [rax+28h]
0x1402d44b9  call    cs:__imp_PsGetCurrentProcess
0x1402d44c0  nop     dword ptr [rax+rax+00h]
0x1402d44c5  cmp     rax, rbx
0x1402d44c8  jz      short loc_1402D44E1
0x1402d44ca  lea     rcx, [rsp+4C8h+var_420]; this
0x1402d44d2  call    ??1CDisplayScenarioContextScope@@QEAA@XZ; CDisplayScenarioContextScope::~CDisplayScenarioContextScope(void)
0x1402d44d7  mov     eax, 0C0000022h
0x1402d44dc  jmp     loc_1402D52D7
0x1402d44e1  call    cs:__imp_W32GetUserSessionState
0x1402d44e8  nop     dword ptr [rax+rax+00h]
0x1402d44ed  or      dword ptr [rax+10D38h], 20h
0x1402d44f4  mov     ebx, 140h
0x1402d44f9  mov     r8d, ebx; Size
0x1402d44fc  xor     edx, edx; Val
0x1402d44fe  lea     rcx, [rsp+4C8h+var_408]; void *
0x1402d4506  call    memset_0
0x1402d450b  mov     r8d, ebx; Size
0x1402d450e  mov     rbx, [rsp+4C8h+Src]
0x1402d4516  mov     rdx, rbx; Src
0x1402d4519  lea     rcx, [rsp+4C8h+var_408]; void *
0x1402d4521  call    RtlCopyFromUser
0x1402d4526  lea     rax, [rsp+4C8h+var_2C8]
0x1402d452e  lea     rcx, [rsp+4C8h+var_408]
0x1402d4536  mov     r8d, 2
0x1402d453c  mov     edx, r8d
0x1402d453f  lea     r9d, [r8+7Eh]
0x1402d4543  movups  xmm0, xmmword ptr [rcx]
0x1402d4546  movups  xmmword ptr [rax], xmm0
0x1402d4549  movups  xmm1, xmmword ptr [rcx+10h]
0x1402d454d  movups  xmmword ptr [rax+10h], xmm1
0x1402d4551  movups  xmm0, xmmword ptr [rcx+20h]
0x1402d4555  movups  xmmword ptr [rax+20h], xmm0
0x1402d4559  movups  xmm1, xmmword ptr [rcx+30h]
0x1402d455d  movups  xmmword ptr [rax+30h], xmm1
0x1402d4561  movups  xmm0, xmmword ptr [rcx+40h]
0x1402d4565  movups  xmmword ptr [rax+40h], xmm0
0x1402d4569  movups  xmm1, xmmword ptr [rcx+50h]
0x1402d456d  movups  xmmword ptr [rax+50h], xmm1
0x1402d4571  movups  xmm0, xmmword ptr [rcx+60h]
0x1402d4575  movups  xmmword ptr [rax+60h], xmm0
0x1402d4579  movups  xmm1, xmmword ptr [rcx+70h]
0x1402d457d  movups  xmmword ptr [rax+70h], xmm1
0x1402d4581  add     rax, r9
0x1402d4584  add     rcx, r9
0x1402d4587  sub     rdx, 1
0x1402d458b  jnz     short loc_1402D4543
0x1402d458d  movups  xmm0, xmmword ptr [rcx]
0x1402d4590  movups  xmmword ptr [rax], xmm0
0x1402d4593  movups  xmm1, xmmword ptr [rcx+10h]
0x1402d4597  movups  xmmword ptr [rax+10h], xmm1
0x1402d459b  movups  xmm0, xmmword ptr [rcx+20h]
0x1402d459f  movups  xmmword ptr [rax+20h], xmm0
0x1402d45a3  movups  xmm1, xmmword ptr [rcx+30h]
0x1402d45a7  movups  xmmword ptr [rax+30h], xmm1
0x1402d45ab  lea     rax, [rsp+4C8h+var_188]
0x1402d45b3  lea     rcx, [rsp+4C8h+var_2C8]
0x1402d45bb  mov     rdx, r8
0x1402d45be  movups  xmm0, xmmword ptr [rcx]
0x1402d45c1  movups  xmmword ptr [rax], xmm0
0x1402d45c4  movups  xmm1, xmmword ptr [rcx+10h]
0x1402d45c8  movups  xmmword ptr [rax+10h], xmm1
0x1402d45cc  movups  xmm0, xmmword ptr [rcx+20h]
0x1402d45d0  movups  xmmword ptr [rax+20h], xmm0
0x1402d45d4  movups  xmm1, xmmword ptr [rcx+30h]
0x1402d45d8  movups  xmmword ptr [rax+30h], xmm1
0x1402d45dc  movups  xmm0, xmmword ptr [rcx+40h]
0x1402d45e0  movups  xmmword ptr [rax+40h], xmm0
0x1402d45e4  movups  xmm1, xmmword ptr [rcx+50h]
0x1402d45e8  movups  xmmword ptr [rax+50h], xmm1
0x1402d45ec  movups  xmm0, xmmword ptr [rcx+60h]
0x1402d45f0  movups  xmmword ptr [rax+60h], xmm0
0x1402d45f4  movups  xmm1, xmmword ptr [rcx+70h]
0x1402d45f8  movups  xmmword ptr [rax+70h], xmm1
0x1402d45fc  add     rax, r9
0x1402d45ff  add     rcx, r9
0x1402d4602  sub     rdx, 1
0x1402d4606  jnz     short loc_1402D45BE
0x1402d4608  movups  xmm0, xmmword ptr [rcx]
0x1402d460b  movups  xmmword ptr [rax], xmm0
0x1402d460e  movups  xmm1, xmmword ptr [rcx+10h]
0x1402d4612  movups  xmmword ptr [rax+10h], xmm1
0x1402d4616  movups  xmm0, xmmword ptr [rcx+20h]
0x1402d461a  movups  xmmword ptr [rax+20h], xmm0
0x1402d461e  movups  xmm1, xmmword ptr [rcx+30h]
0x1402d4622  movups  xmmword ptr [rax+30h], xmm1
0x1402d4626  cmp     [r14+10CE4h], esi
0x1402d462d  jz      short loc_1402D4636
0x1402d462f  mov     edi, 0C0000001h
0x1402d4634  jmp     short loc_1402D46A0
0x1402d4636  mov     ecx, r15d
0x1402d4639  call    cs:__imp_SetConsoleSwitchInProgress
0x1402d4640  nop     dword ptr [rax+rax+00h]
0x1402d4645  xor     ecx, ecx
0x1402d4647  call    SetMouseTrails
0x1402d464c  lea     rax, [r14+10D48h]
0x1402d4653  mov     [r14+10D30h], rax
0x1402d465a  lea     rdx, [r14+10C10h]
0x1402d4661  mov     rcx, [rsp+4C8h+var_158]
0x1402d4669  call    cs:__imp_PopulateUMKMHandlePair
0x1402d4670  nop     dword ptr [rax+rax+00h]
0x1402d4675  mov     edi, eax
0x1402d4677  test    eax, eax
0x1402d4679  js      short loc_1402D46A0
0x1402d467b  lea     rdx, [r14+10C20h]
0x1402d4682  mov     rcx, [rsp+4C8h+var_150]
0x1402d468a  call    cs:__imp_PopulateUMKMHandlePair
0x1402d4691  nop     dword ptr [rax+rax+00h]
0x1402d4696  mov     esi, eax
0x1402d4698  xor     ecx, ecx
0x1402d469a  test    eax, eax
0x1402d469c  jns     short loc_1402D46B4
0x1402d469e  mov     edi, eax
0x1402d46a0  lea     rcx, [rsp+4C8h+var_420]; this
0x1402d46a8  call    ??1CDisplayScenarioContextScope@@QEAA@XZ; CDisplayScenarioContextScope::~CDisplayScenarioContextScope(void)
0x1402d46ad  mov     eax, edi
0x1402d46af  jmp     loc_1402D52D7
0x1402d46b4  mov     edi, ecx
0x1402d46b6  mov     [rsp+4C8h+var_468], ecx
0x1402d46ba  mov     [rsp+4C8h+var_444], ecx
0x1402d46c1  mov     [rsp+4C8h+var_440], ecx
0x1402d46c8  mov     eax, [rsp+4C8h+var_454]
0x1402d46cc  inc     eax
0x1402d46ce  mov     [rsp+4C8h+var_438], eax
0x1402d46d5  mov     [rsp+4C8h+var_454], ecx
0x1402d46d9  mov     [rsp+4C8h+var_43C], ecx
0x1402d46e0  mov     [rsp+4C8h+var_460], rcx
0x1402d46e5  mov     qword ptr [rsp+4C8h+var_48], rcx
0x1402d46ed  mov     eax, [rbx+14h]
0x1402d46f0  mov     [r14+10C08h], eax
0x1402d46f7  mov     eax, [rbx+18h]
0x1402d46fa  mov     [r14+10C0Ch], eax
0x1402d4701  mov     rax, [rsp+4C8h+var_168]
0x1402d4709  mov     [r14+10C00h], rax
0x1402d4710  mov     rax, [rsp+4C8h+var_160]
0x1402d4718  mov     [r14+10C30h], rax
0x1402d471f  mov     rax, [rsp+4C8h+var_148]
0x1402d4727  mov     [r14+10C40h], rax
0x1402d472e  movsd   xmm0, [rsp+4C8h+var_7C]
0x1402d4737  movsd   qword ptr [r14+10CD8h], xmm0
0x1402d4740  mov     eax, [rsp+4C8h+var_74]
0x1402d4747  mov     [r14+10CE0h], eax
0x1402d474e  mov     ebx, [rsp+4C8h+var_98]
0x1402d4755  call    cs:__imp_W32GetUserSessionState
0x1402d475c  nop     dword ptr [rax+rax+00h]
0x1402d4761  mov     [rax+3F58h], ebx
0x1402d4767  mov     ebx, [rsp+4C8h+var_94]
0x1402d476e  call    cs:__imp_W32GetUserSessionState
0x1402d4775  nop     dword ptr [rax+rax+00h]
0x1402d477a  mov     [rax+369Ch], ebx
0x1402d4780  mov     eax, [r14+10BF8h]
0x1402d4787  mov     [rsp+4C8h+var_434], eax
0x1402d478e  mov     eax, [rsp+4C8h+var_64]
0x1402d4795  mov     [r14+10BF8h], eax
0x1402d479c  mov     eax, [rsp+4C8h+var_64]
0x1402d47a3  mov     [r13+40h], eax
0x1402d47a7  mov     rcx, [rsp+4C8h+Src]
0x1402d47af  mov     rax, [rcx+130h]
0x1402d47b6  mov     [r14+10C48h], rax
0x1402d47bd  mov     eax, [rcx+138h]
0x1402d47c3  mov     [r14+10C50h], eax
0x1402d47ca  lea     rax, [r14+10C54h]
0x1402d47d1  movups  xmm0, xmmword ptr [rcx+0A2h]
0x1402d47d8  movups  xmmword ptr [rax], xmm0
0x1402d47db  movups  xmm1, xmmword ptr [rcx+0B2h]
0x1402d47e2  movups  xmmword ptr [rax+10h], xmm1
0x1402d47e6  movsd   xmm0, qword ptr [rcx+0C2h]
0x1402d47ee  movsd   qword ptr [rax+20h], xmm0
0x1402d47f3  call    cs:__imp_W32GetUserSessionState
0x1402d47fa  nop     dword ptr [rax+rax+00h]
0x1402d47ff  mov     rdx, rax
0x1402d4802  lea     rcx, [rax+0F990h]; Str
0x1402d4809  movaps  xmm0, [rsp+4C8h+var_138]
0x1402d4811  movups  xmmword ptr [rcx], xmm0
0x1402d4814  movaps  xmm1, [rsp+4C8h+var_128]
0x1402d481c  movups  xmmword ptr [rcx+10h], xmm1
0x1402d4820  movaps  xmm0, [rsp+4C8h+var_118]
0x1402d4828  movups  xmmword ptr [rcx+20h], xmm0
0x1402d482c  movaps  xmm1, [rsp+4C8h+var_108]
0x1402d4834  movups  xmmword ptr [rcx+30h], xmm1
0x1402d4838  movups  xmm0, [rsp+4C8h+var_BE]
0x1402d4840  movups  xmmword ptr [rax+0F760h], xmm0
0x1402d4847  movzx   eax, [rsp+4C8h+var_AE]
0x1402d484f  mov     [rdx+0F770h], ax
0x1402d4856  movups  xmm0, [rsp+4C8h+var_AC]
0x1402d485e  movups  xmmword ptr [rdx+0F774h], xmm0
0x1402d4865  mov     eax, [rsp+4C8h+var_9C]
0x1402d486c  mov     [rdx+0F784h], eax
0x1402d4872  mov     edx, 23h ; '#'; Ch
0x1402d4877  call    cs:__imp_wcschr
0x1402d487e  nop     dword ptr [rax+rax+00h]
0x1402d4883  xor     ebx, ebx
0x1402d4885  test    rax, rax
0x1402d4888  jz      short loc_1402D488D
0x1402d488a  mov     [rax], bx
0x1402d488d  call    IsRemoteConnection
0x1402d4892  test    eax, eax
0x1402d4894  jz      short loc_1402D48E2
0x1402d4896  mov     dword ptr [rsp+4C8h+HandleInformation], ebx
0x1402d489a  lea     rax, [rsp+4C8h+var_458]
0x1402d489f  mov     [rsp+4C8h+Object], rax
0x1402d48a4  xor     r9d, r9d
0x1402d48a7  lea     r8, aCursorblinkena; "CursorBlinkEnable"
0x1402d48ae  lea     edx, [r9+27h]
0x1402d48b2  xor     ecx, ecx
0x1402d48b4  call    cs:__imp_FastGetProfileIntW
0x1402d48bb  nop     dword ptr [rax+rax+00h]
0x1402d48c0  cmp     [rsp+4C8h+var_458], ebx
0x1402d48c4  jnz     short loc_1402D48E2
0x1402d48c6  call    cs:__imp_W32GetUserSessionState
0x1402d48cd  nop     dword ptr [rax+rax+00h]
0x1402d48d2  mov     rcx, [rax+4CF8h]
0x1402d48d9  and     dword ptr [rcx+8BCh], 0FFFFFFFBh
0x1402d48e0  jmp     short loc_1402D48FC
  ... truncated ...
```
