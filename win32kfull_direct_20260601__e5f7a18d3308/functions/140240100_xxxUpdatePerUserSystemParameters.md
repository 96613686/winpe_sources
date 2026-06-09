# xxxUpdatePerUserSystemParameters

- ea: `0x140240100`
- end: `0x1402416a1`
- name: `xxxUpdatePerUserSystemParameters`
- size: `5537`
- prototype: ``
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
  __int64 v7; // rcx
  __int64 v8; // rdx
  int v9; // ecx
  __int64 UserSessionState; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rax
  char v20; // di
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  int v29; // r12d
  __int64 v30; // rdx
  __int64 v31; // rcx
  int v32; // r13d
  int v33; // r15d
  HANDLE v34; // rbx
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rdx
  struct MOVESIZEDATA *v39; // rcx
  bool v40; // si
  char CurrentWin32kSessionId; // bl
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // rax
  int v45; // r8d
  int v46; // edx
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rax
  HANDLE v50; // rbx
  __int64 v51; // rdx
  __int64 v52; // rcx
  struct _UNICODE_STRING *v53; // rdi
  int v54; // r14d
  __int64 v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // rbx
  void *v58; // rcx
  __int64 v59; // rax
  __int64 v61; // rax
  unsigned int v62; // esi
  __int64 v63; // rax
  __int64 v64; // rdx
  __int64 v65; // rcx
  __int64 v66; // rdx
  __int64 v67; // rcx
  __int64 v68; // rax
  __int64 v69; // rdx
  __int64 v70; // rcx
  int v71; // ebx
  __int64 v72; // rdx
  __int64 v73; // rcx
  __int64 v74; // rax
  __int64 v75; // rdx
  __int64 v76; // rcx
  __int64 v77; // r14
  int v78; // ebx
  Gre::Base *v79; // rcx
  int v80; // r12d
  struct Gre::Base::SESSION_GLOBALS *v81; // rax
  __int64 v82; // rax
  __int64 v83; // rax
  __int64 v84; // rdx
  __int64 v85; // rcx
  __int64 v86; // rax
  __int64 v87; // rdx
  __int64 v88; // rcx
  __int64 v89; // rdx
  __int64 v90; // rcx
  __int64 v91; // rdx
  __int64 v92; // rcx
  __int64 v93; // rdx
  __int64 v94; // rcx
  _QWORD *i; // rbx
  __int64 v96; // rdx
  struct _HEAD *v97; // rcx
  __int64 v98; // rdx
  struct _HEAD *v99; // rcx
  __int64 v100; // rax
  unsigned int j; // r14d
  __int64 v102; // rcx
  __int64 v103; // rdx
  __int64 v104; // rcx
  unsigned int k; // r14d
  unsigned int v106; // edx
  __int64 v107; // rdx
  __int64 v108; // rcx
  __int64 v109; // rdx
  volatile signed __int32 *v110; // rcx
  __int64 v111; // rax
  __int64 v112; // rdx
  __int64 v113; // rcx
  __int64 v114; // rax
  __int64 v115; // rax
  __int64 v116; // rdx
  __int64 v117; // rcx
  __int64 v118; // rax
  __int64 v119; // rdx
  __int64 v120; // rcx
  __int64 v121; // rax
  __int64 v122; // rax
  __int64 v123; // rax
  __int64 v124; // rax
  unsigned int m; // ebx
  __int64 v126; // rdx
  __int64 v127; // rcx
  __int64 v128; // rdx
  __int64 v129; // rcx
  __int64 v130; // rdx
  __int64 v131; // rcx
  __int64 v132; // rdx
  __int64 v133; // rcx
  __int64 v134; // rdx
  __int64 v135; // rcx
  __int64 v136; // rdx
  __int64 v137; // rcx
  __int64 v138; // rdx
  __int64 v139; // rcx
  __int64 v140; // rdx
  __int64 v141; // rcx
  __int64 v142; // rdx
  __int64 v143; // rcx
  __int64 v144; // rdx
  __int64 v145; // rcx
  __int64 v146; // rdx
  __int64 v147; // rcx
  __int64 v148; // rdx
  __int64 v149; // rcx
  int v150; // ebx
  __int64 v151; // rdx
  __int64 v152; // rcx
  __int64 v153; // rdx
  __int64 v154; // rcx
  void *v155; // rbx
  __int64 v156; // rax
  __int64 v157; // rdx
  __int64 v158; // rcx
  int v159; // ebx
  __int64 v160; // r8
  __int64 v161; // r9
  unsigned int *v162; // rax
  __int64 v163; // rdx
  __int64 v164; // rcx
  int v165; // ebx
  __int64 v166; // rdx
  __int64 v167; // rcx
  __int64 v168; // r8
  __int64 v169; // r9
  __int64 v170; // rdx
  __int64 v171; // rcx
  __int64 v172; // rdx
  __int64 v173; // rcx
  __int64 v174; // rdx
  __int64 v175; // rcx
  __int64 v176; // r8
  __int64 v177; // rcx
  __int64 v178; // rdx
  __int64 v179; // rcx
  unsigned int *v180; // [rsp+20h] [rbp-E0h]
  int *v181; // [rsp+20h] [rbp-E0h]
  int v182; // [rsp+28h] [rbp-D8h]
  unsigned int v183; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v184[4]; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v185; // [rsp+68h] [rbp-98h]
  unsigned int v186[2]; // [rsp+6Ch] [rbp-94h] BYREF
  int v187; // [rsp+74h] [rbp-8Ch] BYREF
  int v188; // [rsp+78h] [rbp-88h] BYREF
  int v189; // [rsp+7Ch] [rbp-84h] BYREF
  int v190; // [rsp+80h] [rbp-80h] BYREF
  int v191; // [rsp+84h] [rbp-7Ch] BYREF
  int v192; // [rsp+88h] [rbp-78h] BYREF
  int v193; // [rsp+8Ch] [rbp-74h] BYREF
  int v194; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v195; // [rsp+94h] [rbp-6Ch] BYREF
  __int128 v196; // [rsp+98h] [rbp-68h] BYREF
  __int64 v197; // [rsp+A8h] [rbp-58h]
  _QWORD v198[2]; // [rsp+B0h] [rbp-50h] BYREF
  struct _HEAD *v199; // [rsp+C0h] [rbp-40h]
  int v200; // [rsp+D0h] [rbp-30h]
  int v201; // [rsp+D4h] [rbp-2Ch]
  __int64 v202; // [rsp+D8h] [rbp-28h]
  int v203; // [rsp+E0h] [rbp-20h]
  int v204; // [rsp+E4h] [rbp-1Ch]
  __int64 v205; // [rsp+E8h] [rbp-18h]
  int v206; // [rsp+F0h] [rbp-10h]
  int v207; // [rsp+F4h] [rbp-Ch]
  int v208; // [rsp+F8h] [rbp-8h]
  int v209; // [rsp+FCh] [rbp-4h]
  int v210; // [rsp+100h] [rbp+0h]
  int v211; // [rsp+104h] [rbp+4h]
  int v212; // [rsp+108h] [rbp+8h]
  int v213; // [rsp+10Ch] [rbp+Ch]
  int v214; // [rsp+110h] [rbp+10h]
  int v215; // [rsp+114h] [rbp+14h]
  int v216; // [rsp+118h] [rbp+18h]
  int v217; // [rsp+11Ch] [rbp+1Ch]
  int v218; // [rsp+120h] [rbp+20h]
  int v219; // [rsp+124h] [rbp+24h]
  int v220; // [rsp+128h] [rbp+28h]
  int v221; // [rsp+12Ch] [rbp+2Ch]
  int v222; // [rsp+130h] [rbp+30h]
  int v223; // [rsp+134h] [rbp+34h]
  int v224; // [rsp+138h] [rbp+38h]
  int v225; // [rsp+13Ch] [rbp+3Ch]
  int v226; // [rsp+140h] [rbp+40h]
  int v227; // [rsp+144h] [rbp+44h]
  int v228; // [rsp+148h] [rbp+48h]
  int v229; // [rsp+14Ch] [rbp+4Ch]
  int v230; // [rsp+150h] [rbp+50h]
  int v231; // [rsp+154h] [rbp+54h]
  int v232; // [rsp+158h] [rbp+58h]
  int v233; // [rsp+15Ch] [rbp+5Ch]
  int v234; // [rsp+160h] [rbp+60h]
  int v235; // [rsp+164h] [rbp+64h]
  int v236; // [rsp+168h] [rbp+68h]
  int v237; // [rsp+16Ch] [rbp+6Ch]
  int v238; // [rsp+170h] [rbp+70h]
  int v239; // [rsp+174h] [rbp+74h]
  __int64 v240; // [rsp+178h] [rbp+78h]
  int v241; // [rsp+180h] [rbp+80h]
  int v242; // [rsp+184h] [rbp+84h]
  __int64 v243; // [rsp+188h] [rbp+88h]
  int v244; // [rsp+190h] [rbp+90h]
  int v245; // [rsp+194h] [rbp+94h]
  int v246; // [rsp+198h] [rbp+98h]
  int v247; // [rsp+19Ch] [rbp+9Ch]
  int v248; // [rsp+1A0h] [rbp+A0h]
  int v249; // [rsp+1A4h] [rbp+A4h]
  int v250; // [rsp+1A8h] [rbp+A8h]
  int v251; // [rsp+1ACh] [rbp+ACh]
  int v252; // [rsp+1B0h] [rbp+B0h]
  int v253; // [rsp+1B4h] [rbp+B4h]
  int v254; // [rsp+1B8h] [rbp+B8h]
  int v255; // [rsp+1BCh] [rbp+BCh]
  int v256; // [rsp+1C0h] [rbp+C0h]
  int v257; // [rsp+1C4h] [rbp+C4h]
  int v258; // [rsp+1C8h] [rbp+C8h]
  int v259; // [rsp+1CCh] [rbp+CCh]
  int v260; // [rsp+1D0h] [rbp+D0h]
  int v261; // [rsp+1D4h] [rbp+D4h]
  __int64 v262; // [rsp+1D8h] [rbp+D8h]
  int v263; // [rsp+1E0h] [rbp+E0h]
  int v264; // [rsp+1E4h] [rbp+E4h]
  __int64 v265; // [rsp+1E8h] [rbp+E8h]
  int v266; // [rsp+1F0h] [rbp+F0h]
  int v267; // [rsp+1F4h] [rbp+F4h]
  int v268; // [rsp+1F8h] [rbp+F8h]
  int v269; // [rsp+1FCh] [rbp+FCh]
  int v270; // [rsp+200h] [rbp+100h]
  int v271; // [rsp+204h] [rbp+104h]
  int v272; // [rsp+208h] [rbp+108h]
  int v273; // [rsp+20Ch] [rbp+10Ch]
  int v274; // [rsp+210h] [rbp+110h]
  int v275; // [rsp+214h] [rbp+114h]
  int v276; // [rsp+218h] [rbp+118h]
  int v277; // [rsp+21Ch] [rbp+11Ch]
  int v278; // [rsp+220h] [rbp+120h]
  int v279; // [rsp+224h] [rbp+124h]
  int v280; // [rsp+228h] [rbp+128h]
  int v281; // [rsp+22Ch] [rbp+12Ch]
  int v282; // [rsp+230h] [rbp+130h]
  int v283; // [rsp+234h] [rbp+134h]
  int v284; // [rsp+238h] [rbp+138h]
  int v285; // [rsp+23Ch] [rbp+13Ch]
  int v286; // [rsp+240h] [rbp+140h]
  int v287; // [rsp+244h] [rbp+144h]
  int v288; // [rsp+248h] [rbp+148h]
  int v289; // [rsp+24Ch] [rbp+14Ch]
  int v290; // [rsp+250h] [rbp+150h]
  int v291; // [rsp+254h] [rbp+154h]
  int v292; // [rsp+258h] [rbp+158h]
  int v293; // [rsp+25Ch] [rbp+15Ch]
  int v294; // [rsp+260h] [rbp+160h]
  int v295; // [rsp+264h] [rbp+164h]
  __int64 v296; // [rsp+268h] [rbp+168h]
  __int64 v297; // [rsp+270h] [rbp+170h]
  int v298; // [rsp+280h] [rbp+180h] BYREF
  __int64 v299; // [rsp+288h] [rbp+188h]
  int v300; // [rsp+290h] [rbp+190h]
  __int64 v301; // [rsp+298h] [rbp+198h]
  int v302; // [rsp+2A0h] [rbp+1A0h]
  __int64 v303; // [rsp+2A8h] [rbp+1A8h]
  int v304; // [rsp+2B0h] [rbp+1B0h]
  __int64 v305; // [rsp+2B8h] [rbp+1B8h]
  int v306; // [rsp+2C0h] [rbp+1C0h]
  __int64 v307; // [rsp+2C8h] [rbp+1C8h]
  int v308; // [rsp+2D0h] [rbp+1D0h]
  int *v309; // [rsp+2D8h] [rbp+1D8h]
  int v310; // [rsp+2E0h] [rbp+1E0h]
  __int64 v311; // [rsp+2E8h] [rbp+1E8h]
  int v312; // [rsp+2F0h] [rbp+1F0h]
  __int64 v313; // [rsp+2F8h] [rbp+1F8h]
  int v314; // [rsp+300h] [rbp+200h] BYREF
  __int64 v315; // [rsp+308h] [rbp+208h]
  int v316; // [rsp+310h] [rbp+210h]
  __int64 v317; // [rsp+318h] [rbp+218h]
  int v318; // [rsp+320h] [rbp+220h]
  __int64 v319; // [rsp+328h] [rbp+228h]
  int v320; // [rsp+330h] [rbp+230h]
  int *v321; // [rsp+338h] [rbp+238h]
  int v322; // [rsp+340h] [rbp+240h]
  __int64 v323; // [rsp+348h] [rbp+248h]
  int v324; // [rsp+350h] [rbp+250h]
  __int64 v325; // [rsp+358h] [rbp+258h]
  int v326; // [rsp+360h] [rbp+260h]
  __int64 v327; // [rsp+368h] [rbp+268h]
  int v328; // [rsp+370h] [rbp+270h]
  __int64 v329; // [rsp+378h] [rbp+278h]
  int v330; // [rsp+380h] [rbp+280h]
  __int64 v331; // [rsp+388h] [rbp+288h]
  int v332; // [rsp+390h] [rbp+290h]
  int *v333; // [rsp+398h] [rbp+298h]
  int v334; // [rsp+3A0h] [rbp+2A0h]
  __int64 v335; // [rsp+3A8h] [rbp+2A8h]
  int v336; // [rsp+3B0h] [rbp+2B0h]
  int *v337; // [rsp+3B8h] [rbp+2B8h]
  int v338; // [rsp+3C0h] [rbp+2C0h]
  __int64 v339; // [rsp+3C8h] [rbp+2C8h]
  int v340; // [rsp+3D0h] [rbp+2D0h]
  __int64 v341; // [rsp+3D8h] [rbp+2D8h]
  int v342; // [rsp+3E0h] [rbp+2E0h]
  __int64 v343; // [rsp+3E8h] [rbp+2E8h]
  int v344; // [rsp+3F0h] [rbp+2F0h]
  __int64 v345; // [rsp+3F8h] [rbp+2F8h]
  int v346; // [rsp+400h] [rbp+300h]
  __int64 v347; // [rsp+408h] [rbp+308h]
  int v348; // [rsp+410h] [rbp+310h]
  int *v349; // [rsp+418h] [rbp+318h]
  unsigned __int16 v350[14]; // [rsp+420h] [rbp+320h] BYREF
  int v351; // [rsp+43Ch] [rbp+33Ch]
  _BYTE v352[80]; // [rsp+470h] [rbp+370h] BYREF

  v297 = a2;
  v4 = a1;
  v188 = a1;
  v5 = *(_QWORD *)(W32GetSessionState(a1, a2, a3, a4) + 96);
  v187 = *(_DWORD *)(v5 + 20348);
  v186[0] = 96;
  v7 = *(_DWORD *)(W32GetUserSessionState(v6, v5) + 66784) & 0x100000;
  v197 = -1;
  v193 = v7;
  v196 = 0;
  v183 = 0;
  v191 = 0;
  v201 = 4135;
  v200 = 4;
  v202 = 112;
  v9 = *(_DWORD *)(W32GetUserSessionState(v7, v8) + 66784);
  v194 = 0;
  v190 = 1;
  v192 = v9 & 0x10000;
  v203 = 4;
  v204 = 17;
  v205 = 100;
  v206 = 4;
  v207 = 77;
  v208 = 199;
  v209 = 4;
  v210 = 4;
  v211 = 76;
  v212 = 198;
  v213 = 4;
  v214 = 4;
  v215 = 105;
  v216 = 14;
  v217 = 3;
  v218 = 4;
  v219 = 109;
  v220 = 15;
  v221 = 3;
  v222 = 4;
  v223 = 131;
  v224 = 18;
  v225 = 1;
  v226 = 4;
  v227 = 141;
  v228 = 624;
  v229 = 1;
  v230 = 4;
  v231 = 145;
  v232 = 625;
  v233 = 1;
  v234 = 4;
  v235 = 143;
  v236 = 626;
  v237 = 1;
  v238 = 4;
  v239 = 159;
  v240 = 628;
  v241 = 13;
  v242 = 23;
  v243 = 106;
  v244 = 13;
  v245 = 11;
  v246 = 13;
  v247 = 15;
  v276 = 17;
  v261 = 96;
  v257 = 30;
  v277 = 30;
  v285 = 30;
  v265 = 96;
  v289 = 50;
  v293 = 50;
  v248 = 12;
  v249 = 32;
  v250 = 6;
  v251 = 500;
  v252 = 12;
  v253 = 29;
  v254 = 97;
  v255 = 4;
  v256 = 12;
  v258 = 98;
  v259 = 4;
  v260 = 12;
  v262 = 7;
  v263 = 3;
  v264 = 28;
  v266 = 35;
  v267 = 111;
  v268 = 236;
  v269 = 1;
  v270 = 12;
  v271 = 127;
  v272 = 16;
  v273 = 1;
  v274 = 12;
  v275 = 129;
  v278 = 12;
  v279 = 133;
  v280 = 19;
  v281 = 20;
  v282 = 12;
  v283 = 135;
  v284 = 20;
  v286 = 12;
  v287 = 137;
  v288 = 21;
  v290 = 12;
  v291 = 139;
  v292 = 22;
  v294 = 4;
  v295 = 169;
  v296 = 205;
  v314 = 4;
  v315 = 94;
  v316 = 400;
  UserSessionState = W32GetUserSessionState(20, 1);
  v319 = 107;
  v318 = 4;
  v317 = UserSessionState + 65800;
  v321 = &v193;
  v320 = 2;
  v322 = 4;
  v323 = 159;
  v324 = 3;
  v13 = *(_QWORD *)(W32GetUserSessionState(v12, v11) + 19704) + 4996LL;
  v326 = 4;
  v325 = v13;
  v327 = 160;
  v328 = 3;
  v329 = *(_QWORD *)(W32GetUserSessionState(v13, v14) + 19704) + 5000LL;
  v333 = &v187;
  v337 = &v191;
  v330 = 4;
  v331 = 200;
  v332 = 0;
  v334 = 4;
  v335 = 618;
  v336 = 0;
  v338 = 4;
  v339 = 621;
  v340 = 5000;
  v16 = W32GetUserSessionState(v329, v15);
  v342 = 4;
  v341 = v16 + 69104;
  v343 = 622;
  v344 = 5000;
  v19 = W32GetUserSessionState(v18, v17);
  v346 = 23;
  v347 = 149;
  v345 = v19 + 36248;
  v20 = 1;
  v348 = 1;
  v349 = &v192;
  v298 = 12;
  v299 = 10;
  v300 = 6;
  v23 = W32GetUserSessionState(v22, v21);
  v302 = 12;
  v303 = 11;
  v301 = v23 + 16232;
  v304 = 10;
  v26 = W32GetUserSessionState(v25, v24);
  v306 = 12;
  v305 = v26 + 16236;
  v309 = &v190;
  v307 = 12;
  v308 = 1;
  v310 = 35;
  v311 = 237;
  v312 = 0;
  v29 = v4 & 4;
  v313 = W32GetUserSessionState(v28, v27) + 14652;
  v32 = v4 & 2;
  v186[1] = v29;
  v33 = v4 & 1;
  if ( (v4 & 0x10) != 0 )
  {
    v34 = *(HANDLE *)(W32GetUserSessionState(v31, v30) + 63312);
    if ( PsGetCurrentProcessId() != v34 )
    {
LABEL_3:
      v37 = 5;
LABEL_32:
      UserSetLastError(v37);
      goto LABEL_33;
    }
    if ( v32 || v33 || v29 )
    {
      v37 = 87;
      goto LABEL_32;
    }
    if ( *(_DWORD *)(W32GetUserSessionState(v36, v35) + 308) )
    {
      v39 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
      {
        v20 = 0;
      }
      v40 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v20 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        CurrentWin32kSessionId = W32GetCurrentWin32kSessionId();
        v44 = W32GetUserSessionState(v43, v42);
        LOBYTE(v45) = v40;
        LOBYTE(v46) = v20;
        WPP_RECORDER_AND_TRACE_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v46,
          v45,
          *(_QWORD *)(v44 + 69152),
          4,
          20,
          11,
          (__int64)WPP_6f3f2e22ce9e317051f30d9635f1d0e7_Traceguids,
          CurrentWin32kSessionId);
      }
      *(_DWORD *)(W32GetUserSessionState(v39, v38) + 308) = 0;
      AttachInputDevices(1);
      v49 = W32GetUserSessionState(v48, v47);
      CHidInput::HandleDirectStartStopDeviceReadRequest(*(CHidInput **)(v49 + 16792));
    }
  }
  else
  {
    if ( (v4 & 2) == 0 )
    {
      v50 = *(HANDLE *)(W32GetUserSessionState(v31, v30) + 63312);
      if ( PsGetCurrentProcessId() != v50 )
        goto LABEL_3;
    }
    v53 = (struct _UNICODE_STRING *)CreateProfileUserName(&v196);
    if ( !v53 )
    {
LABEL_33:
      if ( v197 != -1 )
        PopAndFreeAlwaysW32ThreadLock(&v196);
      return 0;
    }
    v54 = 0;
    v185 = 0;
    if ( *(_QWORD *)(W32GetUserSessionState(v52, v51) + 63288) )
    {
      v57 = *(_QWORD *)(W32GetUserSessionState(v56, v55) + 63288);
      v58 = *(void **)(v57 + 176);
      if ( v58 )
        Win32FreePool(v58);
      v59 = Win32AllocPoolZInit(v53->Length, 1852863317);
      *(_QWORD *)(v57 + 176) = v59;
      if ( v59 )
      {
        *(_WORD *)(v57 + 170) = v53->Length;
        *(_WORD *)(v57 + 168) = 0;
        RtlCopyUnicodeString((PUNICODE_STRING)(v57 + 168), v53);
      }
      if ( v33 )
        WakeRIT(64);
    }
    if ( v32 && !v29 )
    {
      v185 = CheckEasPolicyChange();
      if ( !(unsigned int)CheckDesktopPolicyChange(v53) && !v185 )
      {
        v37 = 0;
        goto LABEL_32;
      }
      v54 = 16;
    }
    if ( v33 )
    {
      v61 = W32GetUserSessionState(v56, v55);
      *(_DWORD *)(v61 + 62552) |= 2u;
    }
    v183 = 300;
    v62 = v54 | 8;
    if ( !v29 )
      v62 = v54;
    v63 = W32GetUserSessionState(v56, v55);
    FastGetProfileValue(v53, 4, 607, &v183, v63 + 63968, 4, v62);
    if ( *(int *)(W32GetUserSessionState(v65, v64) + 63968) > 0 )
    {
      v71 = 1000;
      if ( *(int *)(W32GetUserSessionState(v67, v66) + 63968) < 1000 )
        v71 = *(_DWORD *)(W32GetUserSessionState(v73, v72) + 63968);
      v68 = W32GetUserSessionState(v73, v72);
    }
    else
    {
      v68 = W32GetUserSessionState(v67, v66);
      v71 = 1000;
    }
    *(_DWORD *)(v68 + 63968) = v71;
    v74 = W32GetUserSessionState(v70, v69);
    v77 = v74;
    if ( v33 )
    {
      if ( !*(_DWORD *)(v74 + 66048) && !(unsigned int)UserRemoteConnectedSessionUsingWddm() )
      {
        FastGetProfileDwordEx(v53, 4, L"LogPixels", 0, v62, v186, 0);
        v189 = 0;
        v78 = DrvInitializeDxgkrnlDpiCache(&v189);
        v80 = PerformLegacyDpiUpgrade(v53, v186[0]);
        if ( v78 < 0
          || v189
          || (v81 = Gre::Base::Globals(v79), v76 = *((unsigned __int16 *)v81 + 584), *((_WORD *)v81 + 585) != (_WORD)v76)
          || v80
          || v186[0] )
        {
          GreReinitializeDpiSetting();
          v184[0] = 0;
          LOBYTE(v182) = 0;
          if ( (int)xxxUserSetDisplayConfig(0, 0, 2191, 516, 0, v182, 0, 0, v184, v297, 0) >= 0 )
          {
            if ( v184[0] )
              xxxUserResetDisplayDevice();
            v82 = W32GetUserSessionState(v76, v75);
            UserReinitializeStockFonts(*(unsigned __int16 *)(*(_QWORD *)(v82 + 19704) + 6998LL), 1);
            *(_DWORD *)(v77 + 66048) = 1;
          }
        }
      }
    }
    v83 = W32GetUserSessionState(v76, v75);
    CInputGlobals::UpdateWakeOnInputDeviceTypesFromRegistry(*(CInputGlobals **)(v83 + 3008));
    LoadCPUserPreferences(v53, v62);
    if ( !v32 )
    {
      xxxODI_ColorInit(v53);
      LW_LoadResources(v53);
      if ( (unsigned int)GreTextInitialized() )
        xxxSetWindowNCMetrics(v53, 0);
      SetMinMetrics(v53);
      SetIconMetrics(v53);
      GetKbdLangSwitch(v53);
      ZwSetDefaultLocale(1u, 0);
      ZwSetDefaultUILanguage(0);
      v86 = W32GetUserSessionState(v85, v84);
      ZwQueryDefaultUILanguage((LANGID *)(*(_QWORD *)(v86 + 19704) + 7012LL));
      xxxLoadSomeStrings(v88, v87);
      if ( *(_QWORD *)(W32GetUserSessionState(v90, v89) + 63288) )
      {
        SmartObjStackRef<tagMENU>::SmartObjStackRef<tagMENU>(v198);
        for ( i = *(_QWORD **)(*(_QWORD *)(W32GetUserSessionState(v94, v93) + 63288) + 16LL); i; i = (_QWORD *)i[4] )
        {
          v96 = i[7];
          if ( v96 )
          {
            v199 = 0;
            SmartObjStackRefBase<tagMENU>::operator=(v198, v96);
            if ( UnlockDesktopSysMenu(i + 7) )
            {
              v97 = v199;
              if ( !v199 )
                v97 = *(struct _HEAD **)v198[0];
              DestroyMenu(v97);
            }
          }
          v98 = i[8];
          if ( v98 )
          {
            v199 = 0;
            SmartObjStackRefBase<tagMENU>::operator=(v198, v98);
            if ( UnlockDesktopSysMenu(i + 8) )
            {
              v99 = v199;
              if ( !v199 )
                v99 = *(struct _HEAD **)v198[0];
              DestroyMenu(v99);
            }
          }
        }
        SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(v198);
      }
      v100 = W32GetUserSessionState(v92, v91);
      CCursorSizes::zzzRefreshSizes(*(CCursorSizes **)(v100 + 36176));
      xxxUpdateSystemCursorsFromRegistry(v53, 1);
      xxxUpdateSystemIconsFromRegistry(v53);
      for ( j = 0; j < 0xF; ++j )
      {
        v182 = 0;
        v180 = &v183;
        if ( (unsigned int)FastGetProfileIntFromID(
                             v53,
                             (unsigned int)*(&v241 + 4 * (int)j),
                             *((unsigned int *)&v243 + 4 * (int)j)) )
          xxxSystemParametersInfo((unsigned int)*(&v242 + 4 * (int)j), v183, 0, 0x8000, &v183, 0);
      }
      FastGetProfileIntsW(v53, &v298, 4);
      LOBYTE(v102) = v190 != 0;
      EnableMouseAcceleration(v102);
    }
    xxxSystemParametersInfo(21, 0xFFFFFFFFLL, 0, 0, v180, v182);
    if ( v33 )
    {
      W32GetUserSessionState(v104, v103);
      FastGetProfileIntFromID(v53, 35, 236);
    }
    for ( k = 0; k < 0xB; ++k )
    {
      if ( (unsigned int)FastGetProfileIntFromID(
                           v53,
                           (unsigned int)*(&v200 + 4 * (int)k),
                           *((unsigned int *)&v202 + 4 * (int)k)) )
        xxxSystemParametersInfo((unsigned int)*(&v201 + 4 * (int)k), v183, 0, 0x8000, &v183, v62);
    }
    v106 = v62;
    if ( v185 )
      v106 = 2;
    CalcScreenSaverTimeout(v53, v106);
    FastGetProfileIntsW(v53, &v314, 9);
    if ( v191 )
    {
      v110 = *(volatile signed __int32 **)(W32GetUserSessionState(v108, v107) + 19704);
      _InterlockedOr(v110, 0x200u);
    }
    else
    {
      v110 = *(volatile signed __int32 **)(W32GetUserSessionState(v108, v107) + 19704);
      _InterlockedAnd(v110, 0xFFFFFDFF);
    }
    if ( v192 )
    {
      v111 = W32GetUserSessionState(v110, v109);
      *(_DWORD *)(v111 + 66784) |= 0x10000u;
    }
    else
    {
      v114 = W32GetUserSessionState(v110, v109);
      *(_DWORD *)(v114 + 66784) &= ~0x10000u;
    }
    if ( v193 == 2 )
    {
      v115 = W32GetUserSessionState(v113, v112);
      if ( (unsigned int)GreGetDeviceCaps(*(_QWORD *)(*(_QWORD *)(v115 + 56744) + 56LL), 119) )
      {
        v121 = W32GetUserSessionState(v117, v116);
        *(_DWORD *)(v121 + 66784) &= ~0x100000u;
      }
      else
      {
        v118 = W32GetUserSessionState(v117, v116);
        *(_DWORD *)(v118 + 66784) |= 0x100000u;
      }
      if ( v33 )
      {
        v122 = W32GetUserSessionState(v120, v119);
        RtlStringCchPrintfW(v350, 0x28u, L"%d", (*(_DWORD *)(v122 + 66784) >> 20) & 1);
        RtlLoadStringOrError(107, v352);
        FastWriteProfileStringW(v53, 4, v352, v350);
      }
    }
    else if ( v193 )
    {
      v123 = W32GetUserSessionState(v113, v112);
      *(_DWORD *)(v123 + 66784) |= 0x100000u;
    }
    else
    {
      v124 = W32GetUserSessionState(v113, v112);
      *(_DWORD *)(v124 + 66784) &= ~0x100000u;
    }
    v183 = *(_DWORD *)(*(_QWORD *)(W32GetUserSessionState(v120, v119) + 19704) + 4984LL);
    if ( (unsigned int)FastGetProfileIntFromID(v53, 4, 4) )
      SetCaretBlinkTime(v183);
    if ( !v32 )
    {
      v185 = 0;
      FastGetProfileIntFromID(v53, 12, 608);
      UpdateMouseSensitivity(v185);
      for ( m = 0; m < 2; ++m )
      {
        ReadDefaultAccelerationCurves(m, v53);
        ResetAccelerationCurves(m);
      }
      FastGetProfileIntFromID(v53, 12, 613);
      SetMouseTrails(v183);
      FastGetProfileIntW(v53, 7, L"TTOnly");
      GreSetFontEnumeration(v183);
      W32GetUserSessionState(v127, v126);
      W32GetUserSessionState(v129, v128);
      FastGetProfileIntFromID(v53, 12, 91);
      W32GetUserSessionState(v131, v130);
      W32GetUserSessionState(v133, v132);
      FastGetProfileIntFromID(v53, 12, 92);
      W32GetUserSessionState(v135, v134);
      W32GetUserSessionState(v137, v136);
      FastGetProfileIntFromID(v53, 12, 93);
      if ( *(_DWORD *)(W32GetUserSessionState(v139, v138) + 16228) < 0xAu )
        *(_DWORD *)(W32GetUserSessionState(v141, v140) + 16228) = 10;
      if ( *(_DWORD *)(W32GetUserSessionState(v141, v140) + 16228) > 0x7FFFFFFFu )
        *(_DWORD *)(W32GetUserSessionState(v143, v142) + 16228) = 0x7FFFFFFF;
      ReadRawMouseThrottlingThresholds(v53);
      UpdatePerUserKeyboardIndicators(v53);
      InitScancodeMap(v145, v144);
      W32GetUserSessionState(v147, v146);
      FastGetProfileDword(v53, 24, L"Attributes");
      v150 = (*(_DWORD *)(W32GetUserSessionState(v149, v148) + 14128) >> 15) & 2;
      *(_DWORD *)(W32GetUserSessionState(v152, v151) + 14128) = v150;
      xxxUpdatePerUserAccessPackSettings(v53);
    }
    v155 = (void *)OpenCacheKeyEx(0, 22, 131097);
    if ( v155 )
    {
      *(_DWORD *)(*(_QWORD *)(W32GetUserSessionState(v154, v153) + 19704) + 2148LL) = 1;
      ZwClose(v155);
    }
    v156 = W32GetUserSessionState(v154, v153);
    *(_DWORD *)(*(_QWORD *)(v156 + 19704) + 2148LL) |= 2u;
    GreSetFontEnumeration(4);
    GreSetFontEnumeration(32);
    if ( (v187 & 2) != 0 )
      GreSetFontEnumeration(v187 | 4u);
    if ( (*(_DWORD *)UPDWORDPointer(8202) & 2) != 0 )
      GreSetFontEnumeration(v187 | 0x30u);
    v159 = *(_DWORD *)UPDWORDPointer(8204);
    if ( !v159 )
      v159 = 1200;
    *(_DWORD *)(*(_QWORD *)(W32GetSessionState(v158, v157, v160, v161) + 96) + 13448LL) = v159;
    v162 = (unsigned int *)UPDWORDPointer(8210);
    GreSetLCDOrientation(*v162);
    v165 = *(_DWORD *)(W32GetUserSessionState(v164, v163) + 66792) & 0x400;
    *(_DWORD *)(*(_QWORD *)(W32GetSessionState(v167, v166, v168, v169) + 96) + 24304LL) = v165;
    if ( v188 == 2 )
      xxxUserResetDisplayDevice();
    v181 = &v194;
    FastGetProfileDword(0, 49, L"RestrictDebuggerForeground");
    if ( v194 )
      *(_DWORD *)(W32GetUserSessionState(v171, v170) + 18940) = 1;
    if ( v33 )
    {
      memset_0(v350, 0, 0x44u);
      if ( (unsigned int)ReadPointerDeviceSettings(146, v350) )
      {
        if ( !v351 )
          SetTouchInputStatus(0);
      }
    }
    if ( *(_DWORD *)(W32GetUserSessionState(v171, v170) + 62704) == 1 )
    {
      v188 = 0;
      *(_DWORD *)(W32GetUserSessionState(v173, v172) + 62704) = 0;
      UserLogError(3221226518LL);
      UserSessionSwitchLeaveCrit(v175, v174, v176);
      LODWORD(v181) = 7;
      ExRaiseHardError(3221226518LL, 0, 0, 0, v181, &v188);
      EnterCrit(1, 0);
    }
    xxxDwmControl(1037, 0);
    LOBYTE(v177) = *(_DWORD *)UPDWORDPointer(8244) != 0;
    SendCrosshairEnabledStatusChanged(v177);
    v195 = 0;
    if ( (unsigned int)ReadPointerDeviceSettings(178, &v195) )
      SendCrosshairPropertiesChanged(v195);
    ReadInputHapticSettings();
    if ( v33 )
    {
      TraceLoggingAutoRotationStateEvent();
      _InterlockedOr(*(volatile signed __int32 **)(W32GetUserSessionState(v179, v178) + 19704), 0x400u);
    }
  }
  if ( v197 != -1 )
    PopAndFreeAlwaysW32ThreadLock(&v196);
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
