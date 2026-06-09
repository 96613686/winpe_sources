# xxxUpdatePerUserSystemParameters

- ea: `0x140240100`
- end: `0x1402416a1`
- name: `xxxUpdatePerUserSystemParameters`
- size: `5537`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `37`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140240030`

## callees

- `0x140038660`
- `0x14004af90`
- `0x14004c454`
- `0x1400a4a38`
- `0x1400b7870`
- `0x1400b8c90`
- `0x1400b9890`
- `0x1400bce74`
- `0x1400bdb44`
- `0x1400bdf60`
- `0x1400c4a40`
- `0x1400d6dd0`
- `0x1400d75c4`
- `0x1400d78bc`
- `0x1400e8c20`
- `0x140105fb4`
- `0x140106228`
- `0x140106534`
- `0x1401069c8`
- `0x14017cc14`
- `0x140200e50`
- `0x140219a28`
- `0x14021aa68`
- `0x1402206d0`
- `0x140231f54`
- `0x140235c6c`
- `0x140237714`
- `0x140240100`
- `0x140246b70`
- `0x140249d70`
- `0x140256c10`
- `0x14025b7e0`
- `0x14026af7c`
- `0x14027f624`
- `0x1402ad93c`
- `0x140342fa0`
- `0x140343500`

## import_xrefs

- `ntoskrnl!ExRaiseHardError` at `0x1402415ba`
- `ntoskrnl!ExRaiseHardError` at `0x1402415ba`
- `ntoskrnl!ZwQueryDefaultUILanguage` at `0x140240c70`
- `ntoskrnl!ZwQueryDefaultUILanguage` at `0x140240c70`
- `ntoskrnl!ZwSetDefaultUILanguage` at `0x140240c4a`
- `ntoskrnl!ZwSetDefaultUILanguage` at `0x140240c4a`
- `ntoskrnl!ZwSetDefaultLocale` at `0x140240c3c`
- `ntoskrnl!ZwSetDefaultLocale` at `0x140240c3c`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140240717`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140240861`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140240717`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140240861`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140240918`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140240918`
- `ntoskrnl!ZwClose` at `0x1402413d4`
- `ntoskrnl!ZwClose` at `0x1402413d4`
- `win32kbase!OpenCacheKeyEx` at `0x14024139f`
- `win32kbase!OpenCacheKeyEx` at `0x14024139f`
- `win32kbase!FastGetProfileIntW` at `0x1402411a7`
- `win32kbase!FastGetProfileIntW` at `0x1402411a7`
- `win32kbase!xxxSystemParametersInfo` at `0x140240dd2`
- `win32kbase!xxxSystemParametersInfo` at `0x140240e25`
- `win32kbase!xxxSystemParametersInfo` at `0x140240eb8`
- `win32kbase!xxxSystemParametersInfo` at `0x140240dd2`
- `win32kbase!xxxSystemParametersInfo` at `0x140240e25`
- `win32kbase!xxxSystemParametersInfo` at `0x140240eb8`
- `win32kbase!CheckDesktopPolicyChange` at `0x14024094b`
- `win32kbase!CheckDesktopPolicyChange` at `0x14024094b`
- `win32kbase!UserRemoteConnectedSessionUsingWddm` at `0x140240a7b`
- `win32kbase!UserRemoteConnectedSessionUsingWddm` at `0x140240a7b`
- `win32kbase!FastGetProfileDwordEx` at `0x140240ab2`
- `win32kbase!FastGetProfileDwordEx` at `0x140240ab2`
- `win32kbase!DrvInitializeDxgkrnlDpiCache` at `0x140240ac7`
- `win32kbase!DrvInitializeDxgkrnlDpiCache` at `0x140240ac7`
- `win32kbase!GreReinitializeDpiSetting` at `0x140240b1f`
- `win32kbase!GreReinitializeDpiSetting` at `0x140240b1f`
- `win32kbase!xxxUserSetDisplayConfig` at `0x140240b6d`
- `win32kbase!xxxUserSetDisplayConfig` at `0x140240b6d`
- `win32kbase!?UpdateWakeOnInputDeviceTypesFromRegistry@CInputGlobals@@QEAAXXZ` at `0x140240bcf`
- `win32kbase!?UpdateWakeOnInputDeviceTypesFromRegistry@CInputGlobals@@QEAAXXZ` at `0x140240bcf`
- `win32kbase!xxxODI_ColorInit` at `0x140240bf1`
- `win32kbase!xxxODI_ColorInit` at `0x140240bf1`
- `win32kbase!FastGetProfileIntsW` at `0x140240df8`
- `win32kbase!FastGetProfileIntsW` at `0x140240ef7`
- `win32kbase!FastGetProfileIntsW` at `0x140240df8`
- `win32kbase!FastGetProfileIntsW` at `0x140240ef7`
- `win32kbase!EnableMouseAcceleration` at `0x140240e0c`
- `win32kbase!EnableMouseAcceleration` at `0x140240e0c`
- `win32kbase!GreGetDeviceCaps` at `0x140240f96`
- `win32kbase!GreGetDeviceCaps` at `0x140240f96`
- `win32kbase!FastWriteProfileStringW` at `0x14024103e`
- `win32kbase!FastWriteProfileStringW` at `0x14024103e`
- `win32kbase!UpdateMouseSensitivity` at `0x14024111b`
- `win32kbase!UpdateMouseSensitivity` at `0x14024111b`
- `win32kbase!ReadDefaultAccelerationCurves` at `0x140241133`
- `win32kbase!ReadDefaultAccelerationCurves` at `0x140241133`
- `win32kbase!ResetAccelerationCurves` at `0x140241141`
- `win32kbase!ResetAccelerationCurves` at `0x140241141`
- `win32kbase!ReadRawMouseThrottlingThresholds` at `0x1402412fb`
- `win32kbase!ReadRawMouseThrottlingThresholds` at `0x1402412fb`
- `win32kbase!xxxUpdatePerUserAccessPackSettings` at `0x14024137c`
- `win32kbase!xxxUpdatePerUserAccessPackSettings` at `0x14024137c`
- `win32kbase!UserLogError` at `0x140241586`
- `win32kbase!UserLogError` at `0x140241586`
- `win32kbase!xxxDwmControl` at `0x1402415dd`
- `win32kbase!xxxDwmControl` at `0x1402415dd`
- `win32kbase!SendCrosshairEnabledStatusChanged` at `0x140241600`
- `win32kbase!SendCrosshairEnabledStatusChanged` at `0x140241600`
- `win32kbase!ReadPointerDeviceSettings` at `0x14024152c`
- `win32kbase!ReadPointerDeviceSettings` at `0x140241619`
- `win32kbase!ReadPointerDeviceSettings` at `0x14024152c`
- `win32kbase!ReadPointerDeviceSettings` at `0x140241619`
- `win32kbase!SendCrosshairPropertiesChanged` at `0x14024162c`
- `win32kbase!SendCrosshairPropertiesChanged` at `0x14024162c`
- `win32kbase!ReadInputHapticSettings` at `0x140241638`
- `win32kbase!ReadInputHapticSettings` at `0x140241638`
- `win32kbase!SetTouchInputStatus` at `0x140241547`
- `win32kbase!SetTouchInputStatus` at `0x140241547`
- `win32kbase!InitScancodeMap` at `0x14024130f`
- `win32kbase!InitScancodeMap` at `0x14024130f`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140240af0`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140240af0`
- `win32kbase!?CreateProfileUserName@@YAPEAU_UNICODE_STRING@@PEAU?$Win32RawOptionalLockedItemAlways@UtagPROFILEUSERNAME@@$1?Win32FreePool@@YAXPEAX@Z@@@Z` at `0x14024087a`
- `win32kbase!?CreateProfileUserName@@YAPEAU_UNICODE_STRING@@PEAU?$Win32RawOptionalLockedItemAlways@UtagPROFILEUSERNAME@@$1?Win32FreePool@@YAXPEAX@Z@@@Z` at `0x14024087a`
- `win32kbase!FastGetProfileValue` at `0x1402409e4`
- `win32kbase!FastGetProfileValue` at `0x1402409e4`
- `win32kbase!RtlLoadStringOrError` at `0x14024101e`
- `win32kbase!RtlLoadStringOrError` at `0x14024101e`
- `win32kbase!FastGetProfileIntFromID` at `0x140240dae`
- `win32kbase!FastGetProfileIntFromID` at `0x140240e63`
- `win32kbase!FastGetProfileIntFromID` at `0x140240e97`
- `win32kbase!FastGetProfileIntFromID` at `0x1402410c1`
- `win32kbase!FastGetProfileIntFromID` at `0x14024110b`
- `win32kbase!FastGetProfileIntFromID` at `0x140241172`
- `win32kbase!FastGetProfileIntFromID` at `0x1402411ff`
- `win32kbase!FastGetProfileIntFromID` at `0x14024124e`
- `win32kbase!FastGetProfileIntFromID` at `0x140241296`
- `win32kbase!FastGetProfileIntFromID` at `0x140240dae`
- `win32kbase!FastGetProfileIntFromID` at `0x140240e63`
- `win32kbase!FastGetProfileIntFromID` at `0x140240e97`
- `win32kbase!FastGetProfileIntFromID` at `0x1402410c1`
- `win32kbase!FastGetProfileIntFromID` at `0x14024110b`
- `win32kbase!FastGetProfileIntFromID` at `0x140241172`
- `win32kbase!FastGetProfileIntFromID` at `0x1402411ff`
- `win32kbase!FastGetProfileIntFromID` at `0x14024124e`
- `win32kbase!FastGetProfileIntFromID` at `0x140241296`
- `win32kbase!FastGetProfileDword` at `0x140241343`
- `win32kbase!FastGetProfileDword` at `0x1402414e5`
- `win32kbase!FastGetProfileDword` at `0x140241343`
- `win32kbase!FastGetProfileDword` at `0x1402414e5`
- `win32kbase!?HandleDirectStartStopDeviceReadRequest@CHidInput@@QEAAXXZ` at `0x14024082e`
- `win32kbase!?HandleDirectStartStopDeviceReadRequest@CHidInput@@QEAAXXZ` at `0x14024082e`
- `win32kbase!UPDWORDPointer` at `0x140241427`
- `win32kbase!UPDWORDPointer` at `0x14024144b`
- `win32kbase!UPDWORDPointer` at `0x14024147e`
- `win32kbase!UPDWORDPointer` at `0x1402415ee`
- `win32kbase!UPDWORDPointer` at `0x140241427`
- `win32kbase!UPDWORDPointer` at `0x14024144b`
- `win32kbase!UPDWORDPointer` at `0x14024147e`
- `win32kbase!UPDWORDPointer` at `0x1402415ee`
- `win32kbase!EnterCrit` at `0x1402415ca`
- `win32kbase!EnterCrit` at `0x1402415ca`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x140241592`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x140241592`
- `win32kbase!Win32AllocPoolZInit` at `0x1402408e5`
- `win32kbase!Win32AllocPoolZInit` at `0x1402408e5`
- `win32kbase!Win32FreePool` at `0x1402408d1`
- `win32kbase!Win32FreePool` at `0x1402408d1`
- `WIN32K!W32GetSessionState` at `0x14024013d`
- `WIN32K!W32GetSessionState` at `0x140241463`
- `WIN32K!W32GetSessionState` at `0x1402414aa`
- `WIN32K!W32GetSessionState` at `0x14024013d`
- `WIN32K!W32GetSessionState` at `0x140241463`
- `WIN32K!W32GetSessionState` at `0x1402414aa`
- `WIN32K!W32GetUserSessionState` at `0x140240160`
- `WIN32K!W32GetUserSessionState` at `0x140240196`
- `WIN32K!W32GetUserSessionState` at `0x1402404a2`
- `WIN32K!W32GetUserSessionState` at `0x1402404fb`
- `WIN32K!W32GetUserSessionState` at `0x140240535`
- `WIN32K!W32GetUserSessionState` at `0x1402405b6`
- `WIN32K!W32GetUserSessionState` at `0x1402405e7`
- `WIN32K!W32GetUserSessionState` at `0x140240644`
- `WIN32K!W32GetUserSessionState` at `0x140240676`
- `WIN32K!W32GetUserSessionState` at `0x1402406c9`
- `WIN32K!W32GetUserSessionState` at `0x140240704`
- `WIN32K!W32GetUserSessionState` at `0x14024074d`
- `WIN32K!W32GetUserSessionState` at `0x1402407ad`
- `WIN32K!W32GetUserSessionState` at `0x1402407f9`
- `WIN32K!W32GetUserSessionState` at `0x14024081b`
- `WIN32K!W32GetUserSessionState` at `0x14024084e`
- `WIN32K!W32GetUserSessionState` at `0x140240899`
- `WIN32K!W32GetUserSessionState` at `0x1402408b2`
- `WIN32K!W32GetUserSessionState` at `0x140240988`
- `WIN32K!W32GetUserSessionState` at `0x1402409b0`
- `WIN32K!W32GetUserSessionState` at `0x1402409f0`
- `WIN32K!W32GetUserSessionState` at `0x140240a05`
- `WIN32K!W32GetUserSessionState` at `0x140240a18`
- `WIN32K!W32GetUserSessionState` at `0x140240a31`
- `WIN32K!W32GetUserSessionState` at `0x140240a43`
- `WIN32K!W32GetUserSessionState` at `0x140240a55`
- `WIN32K!W32GetUserSessionState` at `0x140240b88`
- `WIN32K!W32GetUserSessionState` at `0x140240bbc`
- `WIN32K!W32GetUserSessionState` at `0x140240c56`
- `WIN32K!W32GetUserSessionState` at `0x140240c81`
- `WIN32K!W32GetUserSessionState` at `0x140240ca3`
- `WIN32K!W32GetUserSessionState` at `0x140240d4c`
- `WIN32K!W32GetUserSessionState` at `0x140240e36`
- `WIN32K!W32GetUserSessionState` at `0x140240f09`
- `WIN32K!W32GetUserSessionState` at `0x140240f25`
- `WIN32K!W32GetUserSessionState` at `0x140240f45`
- `WIN32K!W32GetUserSessionState` at `0x140240f5b`
- `WIN32K!W32GetUserSessionState` at `0x140240f7a`
- `WIN32K!W32GetUserSessionState` at `0x140240fa6`
- `WIN32K!W32GetUserSessionState` at `0x140240fbc`
- `WIN32K!W32GetUserSessionState` at `0x140240fd9`
- `WIN32K!W32GetUserSessionState` at `0x140241050`
- `WIN32K!W32GetUserSessionState` at `0x140241066`
- `WIN32K!W32GetUserSessionState` at `0x14024107a`
- `WIN32K!W32GetUserSessionState` at `0x1402411bc`
- `WIN32K!W32GetUserSessionState` at `0x1402411cf`
- `WIN32K!W32GetUserSessionState` at `0x14024120b`
- `WIN32K!W32GetUserSessionState` at `0x14024121e`
- `WIN32K!W32GetUserSessionState` at `0x14024125a`
- `WIN32K!W32GetUserSessionState` at `0x14024126d`
- `WIN32K!W32GetUserSessionState` at `0x1402412a2`
- `WIN32K!W32GetUserSessionState` at `0x1402412b7`
- `WIN32K!W32GetUserSessionState` at `0x1402412cd`
- `WIN32K!W32GetUserSessionState` at `0x1402412e6`
- `WIN32K!W32GetUserSessionState` at `0x14024131b`
- `WIN32K!W32GetUserSessionState` at `0x14024134f`
- `WIN32K!W32GetUserSessionState` at `0x140241367`
- `WIN32K!W32GetUserSessionState` at `0x1402413b3`
- `WIN32K!W32GetUserSessionState` at `0x1402413e7`
- `WIN32K!W32GetUserSessionState` at `0x140241491`
- `WIN32K!W32GetUserSessionState` at `0x1402414f7`
- `WIN32K!W32GetUserSessionState` at `0x140241553`
- `WIN32K!W32GetUserSessionState` at `0x14024156c`
- `WIN32K!W32GetUserSessionState` at `0x14024164e`
- `WIN32K!W32GetUserSessionState` at `0x140240160`
- `WIN32K!W32GetUserSessionState` at `0x140240196`

## pseudocode

```c
__int64 __fastcall xxxUpdatePerUserSystemParameters(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  char v4; // bl
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // ecx
  __int64 UserSessionState; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rax
  char v32; // di
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  __int64 v46; // r9
  int v47; // r12d
  __int64 v48; // rdx
  __int64 v49; // rcx
  __int64 v50; // r8
  __int64 v51; // r9
  int v52; // r13d
  int v53; // r15d
  HANDLE v54; // rbx
  __int64 v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // r8
  __int64 v58; // r9
  __int64 v59; // rcx
  __int64 v60; // rdx
  __int64 v61; // r8
  __int64 v62; // r9
  struct MOVESIZEDATA *v63; // rcx
  bool v64; // si
  char CurrentWin32kSessionId; // bl
  __int64 v66; // rdx
  __int64 v67; // rcx
  __int64 v68; // r8
  __int64 v69; // r9
  __int64 v70; // rax
  int v71; // r8d
  int v72; // edx
  __int64 v73; // rdx
  __int64 v74; // rcx
  __int64 v75; // r8
  __int64 v76; // r9
  __int64 v77; // rax
  HANDLE v78; // rbx
  __int64 v79; // rdx
  __int64 v80; // rcx
  struct _UNICODE_STRING *v81; // rdi
  __int64 v82; // r8
  __int64 v83; // r9
  int v84; // r14d
  __int64 v85; // rdx
  __int64 v86; // rcx
  __int64 v87; // r8
  __int64 v88; // r9
  __int64 v89; // rbx
  void *v90; // rcx
  __int64 v91; // rax
  __int64 v93; // rax
  unsigned int v94; // esi
  __int64 v95; // rax
  __int64 v96; // rdx
  __int64 v97; // rcx
  __int64 v98; // r8
  __int64 v99; // r9
  __int64 v100; // rdx
  __int64 v101; // rcx
  __int64 v102; // r8
  __int64 v103; // r9
  __int64 v104; // rax
  __int64 v105; // rdx
  __int64 v106; // rcx
  __int64 v107; // r8
  __int64 v108; // r9
  int v109; // ebx
  __int64 v110; // rdx
  __int64 v111; // rcx
  __int64 v112; // r8
  __int64 v113; // r9
  __int64 v114; // rax
  __int64 v115; // rdx
  __int64 v116; // rcx
  __int64 v117; // r8
  __int64 v118; // r9
  __int64 v119; // r14
  int v120; // ebx
  Gre::Base *v121; // rcx
  int v122; // r12d
  struct Gre::Base::SESSION_GLOBALS *v123; // rax
  __int64 v124; // rax
  __int64 v125; // rax
  __int64 v126; // r8
  __int64 v127; // r9
  __int64 v128; // rdx
  __int64 v129; // rcx
  __int64 v130; // r8
  __int64 v131; // r9
  __int64 v132; // rax
  __int64 v133; // rdx
  __int64 v134; // rcx
  __int64 v135; // r8
  __int64 v136; // r9
  __int64 v137; // rdx
  __int64 v138; // rcx
  __int64 v139; // r8
  __int64 v140; // r9
  __int64 v141; // rdx
  __int64 v142; // rcx
  __int64 v143; // r8
  __int64 v144; // r9
  _QWORD *i; // rbx
  __int64 v146; // rdx
  struct _HEAD *v147; // rcx
  __int64 v148; // rdx
  struct _HEAD *v149; // rcx
  __int64 v150; // rax
  unsigned int j; // r14d
  __int64 v152; // rcx
  __int64 v153; // rdx
  __int64 v154; // rcx
  __int64 v155; // r8
  __int64 v156; // r9
  unsigned int k; // r14d
  unsigned int v158; // edx
  __int64 v159; // rdx
  __int64 v160; // rcx
  __int64 v161; // r8
  __int64 v162; // r9
  __int64 v163; // rdx
  volatile signed __int32 *v164; // rcx
  __int64 v165; // r8
  __int64 v166; // r9
  __int64 v167; // rax
  __int64 v168; // rdx
  __int64 v169; // rcx
  __int64 v170; // r8
  __int64 v171; // r9
  __int64 v172; // rax
  __int64 v173; // rax
  __int64 v174; // rdx
  __int64 v175; // rcx
  __int64 v176; // r8
  __int64 v177; // r9
  __int64 v178; // rax
  __int64 v179; // rdx
  __int64 v180; // rcx
  __int64 v181; // r8
  __int64 v182; // r9
  __int64 v183; // rax
  __int64 v184; // rax
  __int64 v185; // rax
  __int64 v186; // rax
  unsigned int m; // ebx
  __int64 v188; // rdx
  __int64 v189; // rcx
  __int64 v190; // r8
  __int64 v191; // r9
  __int64 v192; // rdx
  __int64 v193; // rcx
  __int64 v194; // r8
  __int64 v195; // r9
  __int64 v196; // rdx
  __int64 v197; // rcx
  __int64 v198; // r8
  __int64 v199; // r9
  __int64 v200; // rdx
  __int64 v201; // rcx
  __int64 v202; // r8
  __int64 v203; // r9
  __int64 v204; // rdx
  __int64 v205; // rcx
  __int64 v206; // r8
  __int64 v207; // r9
  __int64 v208; // rdx
  __int64 v209; // rcx
  __int64 v210; // r8
  __int64 v211; // r9
  __int64 v212; // rdx
  __int64 v213; // rcx
  __int64 v214; // r8
  __int64 v215; // r9
  __int64 v216; // rdx
  __int64 v217; // rcx
  __int64 v218; // r8
  __int64 v219; // r9
  __int64 v220; // rdx
  __int64 v221; // rcx
  __int64 v222; // r8
  __int64 v223; // r9
  __int64 v224; // rdx
  __int64 v225; // rcx
  __int64 v226; // rdx
  __int64 v227; // rcx
  __int64 v228; // r8
  __int64 v229; // r9
  __int64 v230; // rdx
  __int64 v231; // rcx
  __int64 v232; // r8
  __int64 v233; // r9
  int v234; // ebx
  __int64 v235; // rdx
  __int64 v236; // rcx
  __int64 v237; // r8
  __int64 v238; // r9
  __int64 v239; // rdx
  __int64 v240; // rcx
  void *v241; // rbx
  __int64 v242; // r8
  __int64 v243; // r9
  __int64 v244; // rax
  __int64 v245; // rdx
  __int64 v246; // rcx
  int v247; // ebx
  __int64 v248; // r8
  __int64 v249; // r9
  unsigned int *v250; // rax
  __int64 v251; // rdx
  __int64 v252; // rcx
  __int64 v253; // r8
  __int64 v254; // r9
  int v255; // ebx
  __int64 v256; // rdx
  __int64 v257; // rcx
  __int64 v258; // r8
  __int64 v259; // r9
  __int64 v260; // rdx
  __int64 v261; // rcx
  __int64 v262; // r8
  __int64 v263; // r9
  __int64 v264; // rdx
  __int64 v265; // rcx
  __int64 v266; // r8
  __int64 v267; // r9
  __int64 v268; // rdx
  __int64 v269; // rcx
  __int64 v270; // r8
  __int64 v271; // rcx
  __int64 v272; // rdx
  __int64 v273; // rcx
  __int64 v274; // r8
  __int64 v275; // r9
  unsigned int *v276; // [rsp+20h] [rbp-E0h]
  int *v277; // [rsp+20h] [rbp-E0h]
  int v278; // [rsp+28h] [rbp-D8h]
  unsigned int v279; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v280[4]; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v281; // [rsp+68h] [rbp-98h]
  unsigned int v282[2]; // [rsp+6Ch] [rbp-94h] BYREF
  int v283; // [rsp+74h] [rbp-8Ch] BYREF
  int v284; // [rsp+78h] [rbp-88h] BYREF
  int v285; // [rsp+7Ch] [rbp-84h] BYREF
  int v286; // [rsp+80h] [rbp-80h] BYREF
  int v287; // [rsp+84h] [rbp-7Ch] BYREF
  int v288; // [rsp+88h] [rbp-78h] BYREF
  int v289; // [rsp+8Ch] [rbp-74h] BYREF
  int v290; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v291; // [rsp+94h] [rbp-6Ch] BYREF
  __int128 v292; // [rsp+98h] [rbp-68h] BYREF
  __int64 v293; // [rsp+A8h] [rbp-58h]
  _QWORD v294[2]; // [rsp+B0h] [rbp-50h] BYREF
  struct _HEAD *v295; // [rsp+C0h] [rbp-40h]
  int v296; // [rsp+D0h] [rbp-30h]
  int v297; // [rsp+D4h] [rbp-2Ch]
  __int64 v298; // [rsp+D8h] [rbp-28h]
  int v299; // [rsp+E0h] [rbp-20h]
  int v300; // [rsp+E4h] [rbp-1Ch]
  __int64 v301; // [rsp+E8h] [rbp-18h]
  int v302; // [rsp+F0h] [rbp-10h]
  int v303; // [rsp+F4h] [rbp-Ch]
  int v304; // [rsp+F8h] [rbp-8h]
  int v305; // [rsp+FCh] [rbp-4h]
  int v306; // [rsp+100h] [rbp+0h]
  int v307; // [rsp+104h] [rbp+4h]
  int v308; // [rsp+108h] [rbp+8h]
  int v309; // [rsp+10Ch] [rbp+Ch]
  int v310; // [rsp+110h] [rbp+10h]
  int v311; // [rsp+114h] [rbp+14h]
  int v312; // [rsp+118h] [rbp+18h]
  int v313; // [rsp+11Ch] [rbp+1Ch]
  int v314; // [rsp+120h] [rbp+20h]
  int v315; // [rsp+124h] [rbp+24h]
  int v316; // [rsp+128h] [rbp+28h]
  int v317; // [rsp+12Ch] [rbp+2Ch]
  int v318; // [rsp+130h] [rbp+30h]
  int v319; // [rsp+134h] [rbp+34h]
  int v320; // [rsp+138h] [rbp+38h]
  int v321; // [rsp+13Ch] [rbp+3Ch]
  int v322; // [rsp+140h] [rbp+40h]
  int v323; // [rsp+144h] [rbp+44h]
  int v324; // [rsp+148h] [rbp+48h]
  int v325; // [rsp+14Ch] [rbp+4Ch]
  int v326; // [rsp+150h] [rbp+50h]
  int v327; // [rsp+154h] [rbp+54h]
  int v328; // [rsp+158h] [rbp+58h]
  int v329; // [rsp+15Ch] [rbp+5Ch]
  int v330; // [rsp+160h] [rbp+60h]
  int v331; // [rsp+164h] [rbp+64h]
  int v332; // [rsp+168h] [rbp+68h]
  int v333; // [rsp+16Ch] [rbp+6Ch]
  int v334; // [rsp+170h] [rbp+70h]
  int v335; // [rsp+174h] [rbp+74h]
  __int64 v336; // [rsp+178h] [rbp+78h]
  int v337; // [rsp+180h] [rbp+80h]
  int v338; // [rsp+184h] [rbp+84h]
  __int64 v339; // [rsp+188h] [rbp+88h]
  int v340; // [rsp+190h] [rbp+90h]
  int v341; // [rsp+194h] [rbp+94h]
  int v342; // [rsp+198h] [rbp+98h]
  int v343; // [rsp+19Ch] [rbp+9Ch]
  int v344; // [rsp+1A0h] [rbp+A0h]
  int v345; // [rsp+1A4h] [rbp+A4h]
  int v346; // [rsp+1A8h] [rbp+A8h]
  int v347; // [rsp+1ACh] [rbp+ACh]
  int v348; // [rsp+1B0h] [rbp+B0h]
  int v349; // [rsp+1B4h] [rbp+B4h]
  int v350; // [rsp+1B8h] [rbp+B8h]
  int v351; // [rsp+1BCh] [rbp+BCh]
  int v352; // [rsp+1C0h] [rbp+C0h]
  int v353; // [rsp+1C4h] [rbp+C4h]
  int v354; // [rsp+1C8h] [rbp+C8h]
  int v355; // [rsp+1CCh] [rbp+CCh]
  int v356; // [rsp+1D0h] [rbp+D0h]
  int v357; // [rsp+1D4h] [rbp+D4h]
  __int64 v358; // [rsp+1D8h] [rbp+D8h]
  int v359; // [rsp+1E0h] [rbp+E0h]
  int v360; // [rsp+1E4h] [rbp+E4h]
  __int64 v361; // [rsp+1E8h] [rbp+E8h]
  int v362; // [rsp+1F0h] [rbp+F0h]
  int v363; // [rsp+1F4h] [rbp+F4h]
  int v364; // [rsp+1F8h] [rbp+F8h]
  int v365; // [rsp+1FCh] [rbp+FCh]
  int v366; // [rsp+200h] [rbp+100h]
  int v367; // [rsp+204h] [rbp+104h]
  int v368; // [rsp+208h] [rbp+108h]
  int v369; // [rsp+20Ch] [rbp+10Ch]
  int v370; // [rsp+210h] [rbp+110h]
  int v371; // [rsp+214h] [rbp+114h]
  int v372; // [rsp+218h] [rbp+118h]
  int v373; // [rsp+21Ch] [rbp+11Ch]
  int v374; // [rsp+220h] [rbp+120h]
  int v375; // [rsp+224h] [rbp+124h]
  int v376; // [rsp+228h] [rbp+128h]
  int v377; // [rsp+22Ch] [rbp+12Ch]
  int v378; // [rsp+230h] [rbp+130h]
  int v379; // [rsp+234h] [rbp+134h]
  int v380; // [rsp+238h] [rbp+138h]
  int v381; // [rsp+23Ch] [rbp+13Ch]
  int v382; // [rsp+240h] [rbp+140h]
  int v383; // [rsp+244h] [rbp+144h]
  int v384; // [rsp+248h] [rbp+148h]
  int v385; // [rsp+24Ch] [rbp+14Ch]
  int v386; // [rsp+250h] [rbp+150h]
  int v387; // [rsp+254h] [rbp+154h]
  int v388; // [rsp+258h] [rbp+158h]
  int v389; // [rsp+25Ch] [rbp+15Ch]
  int v390; // [rsp+260h] [rbp+160h]
  int v391; // [rsp+264h] [rbp+164h]
  __int64 v392; // [rsp+268h] [rbp+168h]
  __int64 v393; // [rsp+270h] [rbp+170h]
  int v394; // [rsp+280h] [rbp+180h] BYREF
  __int64 v395; // [rsp+288h] [rbp+188h]
  int v396; // [rsp+290h] [rbp+190h]
  __int64 v397; // [rsp+298h] [rbp+198h]
  int v398; // [rsp+2A0h] [rbp+1A0h]
  __int64 v399; // [rsp+2A8h] [rbp+1A8h]
  int v400; // [rsp+2B0h] [rbp+1B0h]
  __int64 v401; // [rsp+2B8h] [rbp+1B8h]
  int v402; // [rsp+2C0h] [rbp+1C0h]
  __int64 v403; // [rsp+2C8h] [rbp+1C8h]
  int v404; // [rsp+2D0h] [rbp+1D0h]
  int *v405; // [rsp+2D8h] [rbp+1D8h]
  int v406; // [rsp+2E0h] [rbp+1E0h]
  __int64 v407; // [rsp+2E8h] [rbp+1E8h]
  int v408; // [rsp+2F0h] [rbp+1F0h]
  __int64 v409; // [rsp+2F8h] [rbp+1F8h]
  int v410; // [rsp+300h] [rbp+200h] BYREF
  __int64 v411; // [rsp+308h] [rbp+208h]
  int v412; // [rsp+310h] [rbp+210h]
  __int64 v413; // [rsp+318h] [rbp+218h]
  int v414; // [rsp+320h] [rbp+220h]
  __int64 v415; // [rsp+328h] [rbp+228h]
  int v416; // [rsp+330h] [rbp+230h]
  int *v417; // [rsp+338h] [rbp+238h]
  int v418; // [rsp+340h] [rbp+240h]
  __int64 v419; // [rsp+348h] [rbp+248h]
  int v420; // [rsp+350h] [rbp+250h]
  __int64 v421; // [rsp+358h] [rbp+258h]
  int v422; // [rsp+360h] [rbp+260h]
  __int64 v423; // [rsp+368h] [rbp+268h]
  int v424; // [rsp+370h] [rbp+270h]
  __int64 v425; // [rsp+378h] [rbp+278h]
  int v426; // [rsp+380h] [rbp+280h]
  __int64 v427; // [rsp+388h] [rbp+288h]
  int v428; // [rsp+390h] [rbp+290h]
  int *v429; // [rsp+398h] [rbp+298h]
  int v430; // [rsp+3A0h] [rbp+2A0h]
  __int64 v431; // [rsp+3A8h] [rbp+2A8h]
  int v432; // [rsp+3B0h] [rbp+2B0h]
  int *v433; // [rsp+3B8h] [rbp+2B8h]
  int v434; // [rsp+3C0h] [rbp+2C0h]
  __int64 v435; // [rsp+3C8h] [rbp+2C8h]
  int v436; // [rsp+3D0h] [rbp+2D0h]
  __int64 v437; // [rsp+3D8h] [rbp+2D8h]
  int v438; // [rsp+3E0h] [rbp+2E0h]
  __int64 v439; // [rsp+3E8h] [rbp+2E8h]
  int v440; // [rsp+3F0h] [rbp+2F0h]
  __int64 v441; // [rsp+3F8h] [rbp+2F8h]
  int v442; // [rsp+400h] [rbp+300h]
  __int64 v443; // [rsp+408h] [rbp+308h]
  int v444; // [rsp+410h] [rbp+310h]
  int *v445; // [rsp+418h] [rbp+318h]
  unsigned __int16 v446[14]; // [rsp+420h] [rbp+320h] BYREF
  int v447; // [rsp+43Ch] [rbp+33Ch]
  _BYTE v448[80]; // [rsp+470h] [rbp+370h] BYREF

  v393 = a2;
  v4 = a1;
  v284 = a1;
  v5 = *(_QWORD *)(W32GetSessionState(a1, a2, a3, a4) + 96);
  v283 = *(_DWORD *)(v5 + 20348);
  v282[0] = 96;
  v9 = *(_DWORD *)(W32GetUserSessionState(v6, v5, v7, v8) + 66784) & 0x100000;
  v293 = -1;
  v289 = v9;
  v292 = 0;
  v279 = 0;
  v287 = 0;
  v297 = 4135;
  v296 = 4;
  v298 = 112;
  v13 = *(_DWORD *)(W32GetUserSessionState(v9, v10, v11, v12) + 66784);
  v290 = 0;
  v286 = 1;
  v288 = v13 & 0x10000;
  v299 = 4;
  v300 = 17;
  v301 = 100;
  v302 = 4;
  v303 = 77;
  v304 = 199;
  v305 = 4;
  v306 = 4;
  v307 = 76;
  v308 = 198;
  v309 = 4;
  v310 = 4;
  v311 = 105;
  v312 = 14;
  v313 = 3;
  v314 = 4;
  v315 = 109;
  v316 = 15;
  v317 = 3;
  v318 = 4;
  v319 = 131;
  v320 = 18;
  v321 = 1;
  v322 = 4;
  v323 = 141;
  v324 = 624;
  v325 = 1;
  v326 = 4;
  v327 = 145;
  v328 = 625;
  v329 = 1;
  v330 = 4;
  v331 = 143;
  v332 = 626;
  v333 = 1;
  v334 = 4;
  v335 = 159;
  v336 = 628;
  v337 = 13;
  v338 = 23;
  v339 = 106;
  v340 = 13;
  v341 = 11;
  v342 = 13;
  v343 = 15;
  v372 = 17;
  v357 = 96;
  v353 = 30;
  v373 = 30;
  v381 = 30;
  v361 = 96;
  v385 = 50;
  v389 = 50;
  v344 = 12;
  v345 = 32;
  v346 = 6;
  v347 = 500;
  v348 = 12;
  v349 = 29;
  v350 = 97;
  v351 = 4;
  v352 = 12;
  v354 = 98;
  v355 = 4;
  v356 = 12;
  v358 = 7;
  v359 = 3;
  v360 = 28;
  v362 = 35;
  v363 = 111;
  v364 = 236;
  v365 = 1;
  v366 = 12;
  v367 = 127;
  v368 = 16;
  v369 = 1;
  v370 = 12;
  v371 = 129;
  v374 = 12;
  v375 = 133;
  v376 = 19;
  v377 = 20;
  v378 = 12;
  v379 = 135;
  v380 = 20;
  v382 = 12;
  v383 = 137;
  v384 = 21;
  v386 = 12;
  v387 = 139;
  v388 = 22;
  v390 = 4;
  v391 = 169;
  v392 = 205;
  v410 = 4;
  v411 = 94;
  v412 = 400;
  UserSessionState = W32GetUserSessionState(20, 1, 4, 12);
  v415 = 107;
  v414 = 4;
  v413 = UserSessionState + 65800;
  v417 = &v289;
  v416 = 2;
  v418 = 4;
  v419 = 159;
  v420 = 3;
  v19 = *(_QWORD *)(W32GetUserSessionState(v16, v15, v17, v18) + 19704) + 4996LL;
  v422 = 4;
  v421 = v19;
  v423 = 160;
  v424 = 3;
  v425 = *(_QWORD *)(W32GetUserSessionState(v19, v20, v21, v22) + 19704) + 5000LL;
  v429 = &v283;
  v433 = &v287;
  v426 = 4;
  v427 = 200;
  v428 = 0;
  v430 = 4;
  v431 = 618;
  v432 = 0;
  v434 = 4;
  v435 = 621;
  v436 = 5000;
  v26 = W32GetUserSessionState(v425, v23, v24, v25);
  v438 = 4;
  v437 = v26 + 69104;
  v439 = 622;
  v440 = 5000;
  v31 = W32GetUserSessionState(v28, v27, v29, v30);
  v442 = 23;
  v443 = 149;
  v441 = v31 + 36248;
  v32 = 1;
  v444 = 1;
  v445 = &v288;
  v394 = 12;
  v395 = 10;
  v396 = 6;
  v37 = W32GetUserSessionState(v34, v33, v35, v36);
  v398 = 12;
  v399 = 11;
  v397 = v37 + 16232;
  v400 = 10;
  v42 = W32GetUserSessionState(v39, v38, v40, v41);
  v402 = 12;
  v401 = v42 + 16236;
  v405 = &v286;
  v403 = 12;
  v404 = 1;
  v406 = 35;
  v407 = 237;
  v408 = 0;
  v47 = v4 & 4;
  v409 = W32GetUserSessionState(v44, v43, v45, v46) + 14652;
  v52 = v4 & 2;
  v282[1] = v47;
  v53 = v4 & 1;
  if ( (v4 & 0x10) != 0 )
  {
    v54 = *(HANDLE *)(W32GetUserSessionState(v49, v48, v50, v51) + 63312);
    if ( PsGetCurrentProcessId() != v54 )
    {
LABEL_3:
      v59 = 5;
LABEL_32:
      UserSetLastError(v59);
      goto LABEL_33;
    }
    if ( v52 || v53 || v47 )
    {
      v59 = 87;
      goto LABEL_32;
    }
    if ( *(_DWORD *)(W32GetUserSessionState(v56, v55, v57, v58) + 308) )
    {
      v63 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
      {
        v32 = 0;
      }
      v64 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v32 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        CurrentWin32kSessionId = W32GetCurrentWin32kSessionId();
        v70 = W32GetUserSessionState(v67, v66, v68, v69);
        LOBYTE(v71) = v64;
        LOBYTE(v72) = v32;
        WPP_RECORDER_AND_TRACE_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v72,
          v71,
          *(_QWORD *)(v70 + 69152),
          4,
          20,
          11,
          (__int64)WPP_6f3f2e22ce9e317051f30d9635f1d0e7_Traceguids,
          CurrentWin32kSessionId);
      }
      *(_DWORD *)(W32GetUserSessionState(v63, v60, v61, v62) + 308) = 0;
      AttachInputDevices(1);
      v77 = W32GetUserSessionState(v74, v73, v75, v76);
      CHidInput::HandleDirectStartStopDeviceReadRequest(*(CHidInput **)(v77 + 16792));
    }
  }
  else
  {
    if ( (v4 & 2) == 0 )
    {
      v78 = *(HANDLE *)(W32GetUserSessionState(v49, v48, v50, v51) + 63312);
      if ( PsGetCurrentProcessId() != v78 )
        goto LABEL_3;
    }
    v81 = (struct _UNICODE_STRING *)CreateProfileUserName(&v292);
    if ( !v81 )
    {
LABEL_33:
      if ( v293 != -1 )
        PopAndFreeAlwaysW32ThreadLock(&v292);
      return 0;
    }
    v84 = 0;
    v281 = 0;
    if ( *(_QWORD *)(W32GetUserSessionState(v80, v79, v82, v83) + 63288) )
    {
      v89 = *(_QWORD *)(W32GetUserSessionState(v86, v85, v87, v88) + 63288);
      v90 = *(void **)(v89 + 176);
      if ( v90 )
        Win32FreePool(v90);
      v91 = Win32AllocPoolZInit(v81->Length, 1852863317);
      *(_QWORD *)(v89 + 176) = v91;
      if ( v91 )
      {
        *(_WORD *)(v89 + 170) = v81->Length;
        *(_WORD *)(v89 + 168) = 0;
        RtlCopyUnicodeString((PUNICODE_STRING)(v89 + 168), v81);
      }
      if ( v53 )
        WakeRIT(64);
    }
    if ( v52 && !v47 )
    {
      v281 = CheckEasPolicyChange();
      if ( !(unsigned int)CheckDesktopPolicyChange(v81) && !v281 )
      {
        v59 = 0;
        goto LABEL_32;
      }
      v84 = 16;
    }
    if ( v53 )
    {
      v93 = W32GetUserSessionState(v86, v85, v87, v88);
      *(_DWORD *)(v93 + 62552) |= 2u;
    }
    v279 = 300;
    v94 = v84 | 8;
    if ( !v47 )
      v94 = v84;
    v95 = W32GetUserSessionState(v86, v85, v87, v88);
    FastGetProfileValue(v81, 4, 607, &v279, v95 + 63968, 4, v94);
    if ( *(int *)(W32GetUserSessionState(v97, v96, v98, v99) + 63968) > 0 )
    {
      v109 = 1000;
      if ( *(int *)(W32GetUserSessionState(v101, v100, v102, v103) + 63968) < 1000 )
        v109 = *(_DWORD *)(W32GetUserSessionState(v111, v110, v112, v113) + 63968);
      v104 = W32GetUserSessionState(v111, v110, v112, v113);
    }
    else
    {
      v104 = W32GetUserSessionState(v101, v100, v102, v103);
      v109 = 1000;
    }
    *(_DWORD *)(v104 + 63968) = v109;
    v114 = W32GetUserSessionState(v106, v105, v107, v108);
    v119 = v114;
    if ( v53 )
    {
      if ( !*(_DWORD *)(v114 + 66048) && !(unsigned int)UserRemoteConnectedSessionUsingWddm() )
      {
        FastGetProfileDwordEx(v81, 4, L"LogPixels", 0, v94, v282, 0);
        v285 = 0;
        v120 = DrvInitializeDxgkrnlDpiCache(&v285);
        v122 = PerformLegacyDpiUpgrade(v81, v282[0]);
        if ( v120 < 0
          || v285
          || (v123 = Gre::Base::Globals(v121),
              v116 = *((unsigned __int16 *)v123 + 584),
              *((_WORD *)v123 + 585) != (_WORD)v116)
          || v122
          || v282[0] )
        {
          GreReinitializeDpiSetting();
          v280[0] = 0;
          LOBYTE(v278) = 0;
          if ( (int)xxxUserSetDisplayConfig(0, 0, 2191, 516, 0, v278, 0, 0, v280, v393, 0) >= 0 )
          {
            if ( v280[0] )
              xxxUserResetDisplayDevice();
            v124 = W32GetUserSessionState(v116, v115, v117, v118);
            UserReinitializeStockFonts(*(unsigned __int16 *)(*(_QWORD *)(v124 + 19704) + 6998LL), 1);
            *(_DWORD *)(v119 + 66048) = 1;
          }
        }
      }
    }
    v125 = W32GetUserSessionState(v116, v115, v117, v118);
    CInputGlobals::UpdateWakeOnInputDeviceTypesFromRegistry(*(CInputGlobals **)(v125 + 3008));
    LoadCPUserPreferences(v81, v94, v126, v127);
    if ( !v52 )
    {
      xxxODI_ColorInit(v81);
      LW_LoadResources(v81);
      if ( (unsigned int)GreTextInitialized() )
        xxxSetWindowNCMetrics(v81, 0, -1);
      SetMinMetrics(v81);
      SetIconMetrics(v81, 0);
      GetKbdLangSwitch(v81);
      ZwSetDefaultLocale(1u, 0);
      ZwSetDefaultUILanguage(0);
      v132 = W32GetUserSessionState(v129, v128, v130, v131);
      ZwQueryDefaultUILanguage((LANGID *)(*(_QWORD *)(v132 + 19704) + 7012LL));
      xxxLoadSomeStrings();
      if ( *(_QWORD *)(W32GetUserSessionState(v134, v133, v135, v136) + 63288) )
      {
        SmartObjStackRef<tagMENU>::SmartObjStackRef<tagMENU>(v294);
        for ( i = *(_QWORD **)(*(_QWORD *)(W32GetUserSessionState(v142, v141, v143, v144) + 63288) + 16LL);
              i;
              i = (_QWORD *)i[4] )
        {
          v146 = i[7];
          if ( v146 )
          {
            v295 = 0;
            SmartObjStackRefBase<tagMENU>::operator=(v294, v146);
            if ( UnlockDesktopSysMenu(i + 7) )
            {
              v147 = v295;
              if ( !v295 )
                v147 = *(struct _HEAD **)v294[0];
              DestroyMenu(v147);
            }
          }
          v148 = i[8];
          if ( v148 )
          {
            v295 = 0;
            SmartObjStackRefBase<tagMENU>::operator=(v294, v148);
            if ( UnlockDesktopSysMenu(i + 8) )
            {
              v149 = v295;
              if ( !v295 )
                v149 = *(struct _HEAD **)v294[0];
              DestroyMenu(v149);
            }
          }
        }
        SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(v294);
      }
      v150 = W32GetUserSessionState(v138, v137, v139, v140);
      CCursorSizes::zzzRefreshSizes(*(CCursorSizes **)(v150 + 36176));
      xxxUpdateSystemCursorsFromRegistry(v81, 1);
      xxxUpdateSystemIconsFromRegistry(v81);
      for ( j = 0; j < 0xF; ++j )
      {
        v278 = 0;
        v276 = &v279;
        if ( (unsigned int)FastGetProfileIntFromID(
                             v81,
                             (unsigned int)*(&v337 + 4 * (int)j),
                             *((unsigned int *)&v339 + 4 * (int)j)) )
          xxxSystemParametersInfo((unsigned int)*(&v338 + 4 * (int)j), v279, 0, 0x8000, &v279, 0);
      }
      FastGetProfileIntsW(v81, &v394, 4);
      LOBYTE(v152) = v286 != 0;
      EnableMouseAcceleration(v152);
    }
    xxxSystemParametersInfo(21, 0xFFFFFFFFLL, 0, 0, v276, v278);
    if ( v53 )
    {
      W32GetUserSessionState(v154, v153, v155, v156);
      FastGetProfileIntFromID(v81, 35, 236);
    }
    for ( k = 0; k < 0xB; ++k )
    {
      if ( (unsigned int)FastGetProfileIntFromID(
                           v81,
                           (unsigned int)*(&v296 + 4 * (int)k),
                           *((unsigned int *)&v298 + 4 * (int)k)) )
        xxxSystemParametersInfo((unsigned int)*(&v297 + 4 * (int)k), v279, 0, 0x8000, &v279, v94);
    }
    v158 = v94;
    if ( v281 )
      v158 = 2;
    CalcScreenSaverTimeout(v81, v158);
    FastGetProfileIntsW(v81, &v410, 9);
    if ( v287 )
    {
      v164 = *(volatile signed __int32 **)(W32GetUserSessionState(v160, v159, v161, v162) + 19704);
      _InterlockedOr(v164, 0x200u);
    }
    else
    {
      v164 = *(volatile signed __int32 **)(W32GetUserSessionState(v160, v159, v161, v162) + 19704);
      _InterlockedAnd(v164, 0xFFFFFDFF);
    }
    if ( v288 )
    {
      v167 = W32GetUserSessionState(v164, v163, v165, v166);
      *(_DWORD *)(v167 + 66784) |= 0x10000u;
    }
    else
    {
      v172 = W32GetUserSessionState(v164, v163, v165, v166);
      *(_DWORD *)(v172 + 66784) &= ~0x10000u;
    }
    if ( v289 == 2 )
    {
      v173 = W32GetUserSessionState(v169, v168, v170, v171);
      if ( (unsigned int)GreGetDeviceCaps(*(_QWORD *)(*(_QWORD *)(v173 + 56744) + 56LL), 119) )
      {
        v183 = W32GetUserSessionState(v175, v174, v176, v177);
        *(_DWORD *)(v183 + 66784) &= ~0x100000u;
      }
      else
      {
        v178 = W32GetUserSessionState(v175, v174, v176, v177);
        *(_DWORD *)(v178 + 66784) |= 0x100000u;
      }
      if ( v53 )
      {
        v184 = W32GetUserSessionState(v180, v179, v181, v182);
        RtlStringCchPrintfW(v446, 0x28u, L"%d", (*(_DWORD *)(v184 + 66784) >> 20) & 1);
        RtlLoadStringOrError(107, v448);
        FastWriteProfileStringW(v81, 4, v448, v446);
      }
    }
    else if ( v289 )
    {
      v185 = W32GetUserSessionState(v169, v168, v170, v171);
      *(_DWORD *)(v185 + 66784) |= 0x100000u;
    }
    else
    {
      v186 = W32GetUserSessionState(v169, v168, v170, v171);
      *(_DWORD *)(v186 + 66784) &= ~0x100000u;
    }
    v279 = *(_DWORD *)(*(_QWORD *)(W32GetUserSessionState(v180, v179, v181, v182) + 19704) + 4984LL);
    if ( (unsigned int)FastGetProfileIntFromID(v81, 4, 4) )
      SetCaretBlinkTime(v279);
    if ( !v52 )
    {
      v281 = 0;
      FastGetProfileIntFromID(v81, 12, 608);
      UpdateMouseSensitivity(v281);
      for ( m = 0; m < 2; ++m )
      {
        ReadDefaultAccelerationCurves(m, v81);
        ResetAccelerationCurves(m);
      }
      FastGetProfileIntFromID(v81, 12, 613);
      SetMouseTrails(v279);
      FastGetProfileIntW(v81, 7, L"TTOnly");
      GreSetFontEnumeration(v279);
      W32GetUserSessionState(v189, v188, v190, v191);
      W32GetUserSessionState(v193, v192, v194, v195);
      FastGetProfileIntFromID(v81, 12, 91);
      W32GetUserSessionState(v197, v196, v198, v199);
      W32GetUserSessionState(v201, v200, v202, v203);
      FastGetProfileIntFromID(v81, 12, 92);
      W32GetUserSessionState(v205, v204, v206, v207);
      W32GetUserSessionState(v209, v208, v210, v211);
      FastGetProfileIntFromID(v81, 12, 93);
      if ( *(_DWORD *)(W32GetUserSessionState(v213, v212, v214, v215) + 16228) < 0xAu )
        *(_DWORD *)(W32GetUserSessionState(v217, v216, v218, v219) + 16228) = 10;
      if ( *(_DWORD *)(W32GetUserSessionState(v217, v216, v218, v219) + 16228) > 0x7FFFFFFFu )
        *(_DWORD *)(W32GetUserSessionState(v221, v220, v222, v223) + 16228) = 0x7FFFFFFF;
      ReadRawMouseThrottlingThresholds(v81);
      UpdatePerUserKeyboardIndicators(v81);
      InitScancodeMap(v225, v224);
      W32GetUserSessionState(v227, v226, v228, v229);
      FastGetProfileDword(v81, 24, L"Attributes");
      v234 = (*(_DWORD *)(W32GetUserSessionState(v231, v230, v232, v233) + 14128) >> 15) & 2;
      *(_DWORD *)(W32GetUserSessionState(v236, v235, v237, v238) + 14128) = v234;
      xxxUpdatePerUserAccessPackSettings(v81);
    }
    v241 = (void *)OpenCacheKeyEx(0, 22, 131097);
    if ( v241 )
    {
      *(_DWORD *)(*(_QWORD *)(W32GetUserSessionState(v240, v239, v242, v243) + 19704) + 2148LL) = 1;
      ZwClose(v241);
    }
    v244 = W32GetUserSessionState(v240, v239, v242, v243);
    *(_DWORD *)(*(_QWORD *)(v244 + 19704) + 2148LL) |= 2u;
    GreSetFontEnumeration(4);
    GreSetFontEnumeration(32);
    if ( (v283 & 2) != 0 )
      GreSetFontEnumeration(v283 | 4u);
    if ( (*(_DWORD *)UPDWORDPointer(8202) & 2) != 0 )
      GreSetFontEnumeration(v283 | 0x30u);
    v247 = *(_DWORD *)UPDWORDPointer(8204);
    if ( !v247 )
      v247 = 1200;
    *(_DWORD *)(*(_QWORD *)(W32GetSessionState(v246, v245, v248, v249) + 96) + 13448LL) = v247;
    v250 = (unsigned int *)UPDWORDPointer(8210);
    GreSetLCDOrientation(*v250);
    v255 = *(_DWORD *)(W32GetUserSessionState(v252, v251, v253, v254) + 66792) & 0x400;
    *(_DWORD *)(*(_QWORD *)(W32GetSessionState(v257, v256, v258, v259) + 96) + 24304LL) = v255;
    if ( v284 == 2 )
      xxxUserResetDisplayDevice();
    v277 = &v290;
    FastGetProfileDword(0, 49, L"RestrictDebuggerForeground");
    if ( v290 )
      *(_DWORD *)(W32GetUserSessionState(v261, v260, v262, v263) + 18940) = 1;
    if ( v53 )
    {
      memset_0(v446, 0, 0x44u);
      if ( (unsigned int)ReadPointerDeviceSettings(146, v446) )
      {
        if ( !v447 )
          SetTouchInputStatus(0);
      }
    }
    if ( *(_DWORD *)(W32GetUserSessionState(v261, v260, v262, v263) + 62704) == 1 )
    {
      v284 = 0;
      *(_DWORD *)(W32GetUserSessionState(v265, v264, v266, v267) + 62704) = 0;
      UserLogError(3221226518LL);
      UserSessionSwitchLeaveCrit(v269, v268, v270);
      LODWORD(v277) = 7;
      ExRaiseHardError(3221226518LL, 0, 0, 0, v277, &v284);
      EnterCrit(1, 0);
    }
    xxxDwmControl(1037, 0);
    LOBYTE(v271) = *(_DWORD *)UPDWORDPointer(8244) != 0;
    SendCrosshairEnabledStatusChanged(v271);
    v291 = 0;
    if ( (unsigned int)ReadPointerDeviceSettings(178, &v291) )
      SendCrosshairPropertiesChanged(v291);
    ReadInputHapticSettings();
    if ( v53 )
    {
      TraceLoggingAutoRotationStateEvent();
      _InterlockedOr(*(volatile signed __int32 **)(W32GetUserSessionState(v273, v272, v274, v275) + 19704), 0x400u);
    }
  }
  if ( v293 != -1 )
    PopAndFreeAlwaysW32ThreadLock(&v292);
  return 1;
}

```

## disassembly

```asm
0x140240100  mov     [rsp-8+arg_10], rbx
0x140240105  push    rbp
0x140240106  push    rsi
0x140240107  push    rdi
0x140240108  push    r12
0x14024010a  push    r13
0x14024010c  push    r14
0x14024010e  push    r15
0x140240110  lea     rbp, [rsp-3D0h]
0x140240118  sub     rsp, 4D0h
0x14024011f  mov     rax, cs:__security_cookie
0x140240126  xor     rax, rsp
0x140240129  mov     [rbp+400h+var_40], rax
0x140240130  mov     [rbp+400h+var_290], rdx
0x140240137  mov     ebx, ecx
0x140240139  mov     [rsp+500h+var_488], ecx
0x14024013d  call    cs:__imp_W32GetSessionState
0x140240144  nop     dword ptr [rax+rax+00h]
0x140240149  mov     esi, 60h ; '`'
0x14024014e  mov     rdx, [rax+60h]
0x140240152  mov     eax, [rdx+4F7Ch]
0x140240158  mov     [rsp+500h+var_48C], eax
0x14024015c  mov     [rsp+500h+var_494], esi
0x140240160  call    cs:__imp_W32GetUserSessionState
0x140240167  nop     dword ptr [rax+rax+00h]
0x14024016c  xorps   xmm0, xmm0
0x14024016f  xor     r13d, r13d
0x140240172  mov     ecx, [rax+104E0h]
0x140240178  and     ecx, 100000h
0x14024017e  mov     [rbp+400h+var_458], 0FFFFFFFFFFFFFFFFh
0x140240186  mov     [rbp+400h+var_474], ecx
0x140240189  movups  [rbp+400h+var_468], xmm0
0x14024018d  mov     [rsp+500h+var_4A0], r13d
0x140240192  mov     [rbp+400h+var_47C], r13d
0x140240196  call    cs:__imp_W32GetUserSessionState
0x14024019d  nop     dword ptr [rax+rax+00h]
0x1402401a2  lea     r8d, [rsi-5Ch]
0x1402401a6  mov     [rbp+400h+var_42C], 1027h
0x1402401ad  lea     edx, [rsi-5Fh]
0x1402401b0  mov     [rbp+400h+var_430], r8d
0x1402401b4  lea     r15d, [rsi-5Dh]
0x1402401b8  mov     [rbp+400h+var_428], 70h ; 'p'
0x1402401c0  mov     ecx, [rax+104E0h]
0x1402401c6  lea     r9d, [rsi-51h]
0x1402401ca  lea     eax, [rsi-53h]
0x1402401cd  mov     [rbp+400h+var_470], r13d
0x1402401d1  and     ecx, 10000h
0x1402401d7  mov     [rbp+400h+var_480], edx
0x1402401da  mov     [rbp+400h+var_478], ecx
0x1402401dd  lea     edi, [rsi+3Fh]
0x1402401e0  lea     ecx, [rsi-4Fh]
0x1402401e3  mov     [rbp+400h+var_420], r8d
0x1402401e7  lea     r12d, [rsi-49h]
0x1402401eb  mov     [rbp+400h+var_41C], ecx
0x1402401ee  mov     [rbp+400h+var_418], 64h ; 'd'
0x1402401f6  mov     [rbp+400h+var_410], r8d
0x1402401fa  mov     [rbp+400h+var_40C], 4Dh ; 'M'
0x140240201  mov     [rbp+400h+var_408], 0C7h
0x140240208  mov     [rbp+400h+var_404], r8d
0x14024020c  mov     [rbp+400h+var_400], r8d
0x140240210  mov     [rbp+400h+var_3FC], 4Ch ; 'L'
0x140240217  mov     [rbp+400h+var_3F8], 0C6h
0x14024021e  mov     [rbp+400h+var_3F4], r8d
0x140240222  mov     [rbp+400h+var_3F0], r8d
0x140240226  mov     [rbp+400h+var_3EC], 69h ; 'i'
0x14024022d  mov     [rbp+400h+var_3E8], 0Eh
0x140240234  mov     [rbp+400h+var_3E4], r15d
0x140240238  mov     [rbp+400h+var_3E0], r8d
0x14024023c  mov     [rbp+400h+var_3DC], 6Dh ; 'm'
0x140240243  mov     [rbp+400h+var_3D8], r9d
0x140240247  mov     [rbp+400h+var_3D4], r15d
0x14024024b  mov     [rbp+400h+var_3D0], r8d
0x14024024f  mov     [rbp+400h+var_3CC], 83h
0x140240256  mov     [rbp+400h+var_3C8], 12h
0x14024025d  mov     [rbp+400h+var_3C4], edx
0x140240260  mov     [rbp+400h+var_3C0], r8d
0x140240264  mov     [rbp+400h+var_3BC], 8Dh
0x14024026b  mov     [rbp+400h+var_3B8], 270h
0x140240272  mov     [rbp+400h+var_3B4], edx
0x140240275  mov     [rbp+400h+var_3B0], r8d
0x140240279  mov     [rbp+400h+var_3AC], 91h
0x140240280  mov     [rbp+400h+var_3A8], 271h
0x140240287  mov     [rbp+400h+var_3A4], edx
0x14024028a  mov     [rbp+400h+var_3A0], r8d
0x14024028e  mov     [rbp+400h+var_39C], 8Fh
0x140240295  mov     [rbp+400h+var_398], 272h
0x14024029c  mov     [rbp+400h+var_394], edx
0x14024029f  mov     [rbp+400h+var_390], r8d
0x1402402a3  mov     [rbp+400h+var_38C], edi
0x1402402a6  mov     [rbp+400h+var_388], 274h
0x1402402ae  mov     [rbp+400h+var_380], eax
0x1402402b4  mov     [rbp+400h+var_37C], r12d
0x1402402bb  mov     [rbp+400h+var_378], 6Ah ; 'j'
0x1402402c6  mov     [rbp+400h+var_370], eax
0x1402402cc  mov     [rbp+400h+var_36C], 0Bh
0x1402402d6  mov     [rbp+400h+var_368], eax
0x1402402dc  mov     [rbp+400h+var_364], r9d
0x1402402e3  lea     r9d, [rsi-54h]
0x1402402e7  mov     [rbp+400h+var_2E8], ecx
0x1402402ed  lea     eax, [rsi-42h]
0x1402402f0  mov     [rbp+400h+var_32C], esi
0x1402402f6  lea     ecx, [rdx+13h]
0x1402402f9  mov     [rbp+400h+var_33C], eax
0x1402402ff  mov     [rbp+400h+var_2E4], eax
0x140240305  lea     r14d, [rsi-5Ah]
0x140240309  mov     [rbp+400h+var_2C4], eax
0x14024030f  lea     eax, [rdx+31h]
0x140240312  mov     [rbp+400h+var_318], rsi
0x140240319  xor     esi, esi
0x14024031b  mov     [rbp+400h+var_2B4], eax
0x140240321  mov     [rbp+400h+var_2A4], eax
0x140240327  mov     [rbp+400h+var_360], r9d
0x14024032e  mov     [rbp+400h+var_35C], 20h ; ' '
0x140240338  mov     [rbp+400h+var_358], r14d
0x14024033f  mov     [rbp+400h+var_354], 1F4h
0x140240349  mov     [rbp+400h+var_350], r9d
0x140240350  mov     [rbp+400h+var_34C], 1Dh
0x14024035a  mov     [rbp+400h+var_348], 61h ; 'a'
0x140240364  mov     [rbp+400h+var_344], r8d
0x14024036b  mov     [rbp+400h+var_340], r9d
0x140240372  mov     [rbp+400h+var_338], 62h ; 'b'
0x14024037c  mov     [rbp+400h+var_334], r8d
0x140240383  mov     [rbp+400h+var_330], r9d
0x14024038a  mov     [rbp+400h+var_328], 7
0x140240395  mov     [rbp+400h+var_320], r15d
0x14024039c  mov     [rbp+400h+var_31C], 1Ch
0x1402403a6  mov     [rbp+400h+var_310], 23h ; '#'
0x1402403b0  mov     [rbp+400h+var_30C], 6Fh ; 'o'
0x1402403ba  mov     [rbp+400h+var_308], 0ECh
0x1402403c4  mov     [rbp+400h+var_304], edx
0x1402403ca  mov     [rbp+400h+var_300], r9d
0x1402403d1  mov     [rbp+400h+var_2FC], 7Fh
0x1402403db  mov     [rbp+400h+var_2F8], 10h
0x1402403e5  mov     [rbp+400h+var_2F4], edx
0x1402403eb  mov     [rbp+400h+var_2F0], r9d
0x1402403f2  mov     [rbp+400h+var_2EC], 81h
0x1402403fc  mov     [rbp+400h+var_2E0], r9d
0x140240403  mov     [rbp+400h+var_2DC], 85h
0x14024040d  mov     [rbp+400h+var_2D8], 13h
0x140240417  mov     [rbp+400h+var_2D4], ecx
0x14024041d  mov     [rbp+400h+var_2D0], r9d
0x140240424  mov     [rbp+400h+var_2CC], 87h
0x14024042e  mov     [rbp+400h+var_2C8], ecx
0x140240434  mov     [rbp+400h+var_2C0], r9d
0x14024043b  mov     [rbp+400h+var_2BC], 89h
0x140240445  mov     [rbp+400h+var_2B8], 15h
0x14024044f  mov     [rbp+400h+var_2B0], r9d
0x140240456  mov     [rbp+400h+var_2AC], 8Bh
0x140240460  mov     [rbp+400h+var_2A8], 16h
0x14024046a  mov     [rbp+400h+var_2A0], r8d
0x140240471  mov     [rbp+400h+var_29C], 0A9h
0x14024047b  mov     [rbp+400h+var_298], 0CDh
0x140240486  mov     [rbp+400h+var_200], r8d
0x14024048d  mov     [rbp+400h+var_1F8], 5Eh ; '^'
0x140240498  mov     [rbp+400h+var_1F0], 190h
0x1402404a2  call    cs:__imp_W32GetUserSessionState
0x1402404a9  nop     dword ptr [rax+rax+00h]
0x1402404ae  lea     r13d, [r15+1]
0x1402404b2  mov     [rbp+400h+var_1D8], 6Bh ; 'k'
0x1402404bd  add     rax, 10108h
0x1402404c3  mov     [rbp+400h+var_1E0], r13d
0x1402404ca  mov     [rbp+400h+var_1E8], rax
0x1402404d1  lea     rax, [rbp+400h+var_474]
0x1402404d5  mov     [rbp+400h+var_1C8], rax
0x1402404dc  mov     [rbp+400h+var_1D0], 2
0x1402404e6  mov     [rbp+400h+var_1C0], r13d
0x1402404ed  mov     [rbp+400h+var_1B8], rdi
0x1402404f4  mov     [rbp+400h+var_1B0], r15d
0x1402404fb  call    cs:__imp_W32GetUserSessionState
0x140240502  nop     dword ptr [rax+rax+00h]
0x140240507  mov     rcx, [rax+4CF8h]
0x14024050e  add     rcx, 1384h
0x140240515  mov     [rbp+400h+var_1A0], r13d
0x14024051c  mov     [rbp+400h+var_1A8], rcx
0x140240523  mov     [rbp+400h+var_198], 0A0h
0x14024052e  mov     [rbp+400h+var_190], r15d
0x140240535  call    cs:__imp_W32GetUserSessionState
0x14024053c  nop     dword ptr [rax+rax+00h]
0x140240541  mov     edi, 1388h
0x140240546  mov     rcx, [rax+4CF8h]
0x14024054d  add     rcx, rdi
0x140240550  lea     rax, [rsp+500h+var_48C]
0x140240555  mov     [rbp+400h+var_188], rcx
0x14024055c  mov     [rbp+400h+var_168], rax
0x140240563  lea     rax, [rbp+400h+var_47C]
0x140240567  mov     [rbp+400h+var_148], rax
0x14024056e  mov     [rbp+400h+var_180], r13d
0x140240575  mov     [rbp+400h+var_178], 0C8h
0x140240580  mov     [rbp+400h+var_170], esi
0x140240586  mov     [rbp+400h+var_160], r13d
0x14024058d  mov     [rbp+400h+var_158], 26Ah
0x140240598  mov     [rbp+400h+var_150], esi
0x14024059e  mov     [rbp+400h+var_140], r13d
0x1402405a5  mov     [rbp+400h+var_138], 26Dh
0x1402405b0  mov     [rbp+400h+var_130], edi
0x1402405b6  call    cs:__imp_W32GetUserSessionState
0x1402405bd  nop     dword ptr [rax+rax+00h]
0x1402405c2  add     rax, 10DF0h
0x1402405c8  mov     [rbp+400h+var_120], r13d
0x1402405cf  mov     [rbp+400h+var_128], rax
0x1402405d6  mov     [rbp+400h+var_118], 26Eh
0x1402405e1  mov     [rbp+400h+var_110], edi
0x1402405e7  call    cs:__imp_W32GetUserSessionState
0x1402405ee  nop     dword ptr [rax+rax+00h]
0x1402405f3  mov     [rbp+400h+var_100], r12d
0x1402405fa  lea     r15d, [r12-0Bh]
0x1402405ff  add     rax, 8D98h
0x140240605  mov     [rbp+400h+var_F8], 95h
0x140240610  mov     [rbp+400h+var_108], rax
0x140240617  lea     edi, [rsi+1]
0x14024061a  lea     rax, [rbp+400h+var_478]
0x14024061e  mov     [rbp+400h+var_F0], edi
0x140240624  lea     r12d, [r14+4]
0x140240628  mov     [rbp+400h+var_E8], rax
0x14024062f  mov     [rbp+400h+var_280], r15d
0x140240636  mov     [rbp+400h+var_278], r12
0x14024063d  mov     [rbp+400h+var_270], r14d
0x140240644  call    cs:__imp_W32GetUserSessionState
0x14024064b  nop     dword ptr [rax+rax+00h]
0x140240650  lea     r14d, [rsi+0Bh]
0x140240654  mov     [rbp+400h+var_260], r15d
0x14024065b  add     rax, 3F68h
0x140240661  mov     [rbp+400h+var_258], r14
0x140240668  mov     [rbp+400h+var_268], rax
0x14024066f  mov     [rbp+400h+var_250], r12d
0x140240676  call    cs:__imp_W32GetUserSessionState
0x14024067d  nop     dword ptr [rax+rax+00h]
0x140240682  add     rax, 3F6Ch
0x140240688  mov     [rbp+400h+var_240], r15d
0x14024068f  mov     [rbp+400h+var_248], rax
0x140240696  lea     rax, [rbp+400h+var_480]
0x14024069a  mov     [rbp+400h+var_228], rax
0x1402406a1  mov     [rbp+400h+var_238], r15
0x1402406a8  mov     [rbp+400h+var_230], edi
0x1402406ae  mov     [rbp+400h+var_220], 23h ; '#'
0x1402406b8  mov     [rbp+400h+var_218], 0EDh
0x1402406c3  mov     [rbp+400h+var_210], esi
0x1402406c9  call    cs:__imp_W32GetUserSessionState
0x1402406d0  nop     dword ptr [rax+rax+00h]
0x1402406d5  mov     r13d, ebx
0x1402406d8  mov     r15d, ebx
0x1402406db  add     rax, 393Ch
0x1402406e1  mov     r12d, ebx
0x1402406e4  and     r12d, 4
0x1402406e8  mov     [rbp+400h+var_208], rax
0x1402406ef  and     r13d, 2
0x1402406f3  mov     [rsp+500h+var_490], r12d
0x1402406f8  and     r15d, edi
0x1402406fb  test    bl, 10h
0x1402406fe  jz      loc_140240849
0x140240704  call    cs:__imp_W32GetUserSessionState
0x14024070b  nop     dword ptr [rax+rax+00h]
0x140240710  mov     rbx, [rax+0F750h]
0x140240717  call    cs:__imp_PsGetCurrentProcessId
0x14024071e  nop     dword ptr [rax+rax+00h]
0x140240723  cmp     rax, rbx
0x140240726  jz      short loc_140240732
0x140240728  mov     ecx, 5
0x14024072d  jmp     loc_140240961
0x140240732  test    r13d, r13d
0x140240735  jnz     loc_14024083F
0x14024073b  test    r15d, r15d
0x14024073e  jnz     loc_14024083F
0x140240744  test    r12d, r12d
0x140240747  jnz     loc_14024083F
0x14024074d  call    cs:__imp_W32GetUserSessionState
0x140240754  nop     dword ptr [rax+rax+00h]
0x140240759  cmp     [rax+134h], esi
0x14024075f  jz      loc_140241664
0x140240765  mov     rcx, cs:WPP_GLOBAL_Control
0x14024076c  lea     rax, WPP_GLOBAL_Control
0x140240773  cmp     rcx, rax
0x140240776  jz      short loc_140240787
0x140240778  test    dword ptr [rcx+2Ch], 80000h
0x14024077f  jz      short loc_140240787
0x140240781  cmp     byte ptr [rcx+29h], 4
0x140240785  jnb     short loc_14024078A
0x140240787  mov     dil, sil
0x14024078a  lea     rax, WPP_RECORDER_INITIALIZED
0x140240791  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140240798  setnz   sil
0x14024079c  test    dil, dil
0x14024079f  jnz     short loc_1402407A6
0x1402407a1  test    sil, sil
0x1402407a4  jz      short loc_1402407F9
0x1402407a6  call    W32GetCurrentWin32kSessionId
0x1402407ab  mov     ebx, eax
0x1402407ad  call    cs:__imp_W32GetUserSessionState
0x1402407b4  nop     dword ptr [rax+rax+00h]
0x1402407b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1402407c0  mov     r8b, sil
0x1402407c3  mov     dword ptr [rsp+500h+var_4C0], ebx
0x1402407c7  mov     dl, dil
0x1402407ca  mov     r9, [rax+10E20h]
0x1402407d1  lea     rax, WPP_6f3f2e22ce9e317051f30d9635f1d0e7_Traceguids
0x1402407d8  mov     rcx, [rcx+18h]
0x1402407dc  mov     [rsp+500h+var_4C8], rax
0x1402407e1  mov     word ptr [rsp+500h+var_4D0], r14w
0x1402407e7  mov     dword ptr [rsp+500h+var_4D8], 14h
0x1402407ef  mov     byte ptr [rsp+500h+var_4E0], 4
  ... truncated ...
```
