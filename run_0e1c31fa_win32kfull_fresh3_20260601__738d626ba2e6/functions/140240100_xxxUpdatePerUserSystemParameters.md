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
__int64 __fastcall xxxUpdatePerUserSystemParameters(__int64 a1, __int64 a2)
{
  char v2; // bl
  __int64 v3; // rcx
  __int64 v4; // rcx
  int v5; // ecx
  __int64 UserSessionState; // rax
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  char v12; // di
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  int v18; // r12d
  __int64 v19; // rcx
  int v20; // r13d
  int v21; // r15d
  HANDLE v22; // rbx
  __int64 v23; // rcx
  __int64 v24; // rcx
  struct MOVESIZEDATA *v25; // rcx
  bool v26; // si
  char CurrentWin32kSessionId; // bl
  __int64 v28; // rcx
  __int64 v29; // rax
  int v30; // r8d
  int v31; // edx
  __int64 v32; // rcx
  __int64 v33; // rax
  HANDLE v34; // rbx
  __int64 v35; // rcx
  struct _UNICODE_STRING *v36; // rdi
  int v37; // r14d
  __int64 v38; // rcx
  __int64 v39; // rbx
  void *v40; // rcx
  __int64 v41; // rax
  __int64 v43; // rax
  unsigned int v44; // esi
  __int64 v45; // rax
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rax
  __int64 v49; // rcx
  int v50; // ebx
  __int64 v51; // rcx
  __int64 v52; // rax
  __int64 v53; // rcx
  __int64 v54; // r14
  int v55; // ebx
  Gre::Base *v56; // rcx
  int v57; // r12d
  struct Gre::Base::SESSION_GLOBALS *v58; // rax
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // rcx
  __int64 v62; // rax
  __int64 v63; // rcx
  __int64 v64; // rcx
  __int64 v65; // rcx
  _QWORD *i; // rbx
  struct _HEAD *v67; // rcx
  struct _HEAD *v68; // rcx
  __int64 v69; // rax
  unsigned int j; // r14d
  __int64 v71; // rcx
  __int64 v72; // rcx
  unsigned int k; // r14d
  unsigned int v74; // edx
  __int64 v75; // rcx
  volatile signed __int32 *v76; // rcx
  __int64 v77; // rax
  __int64 v78; // rcx
  __int64 v79; // rax
  __int64 v80; // rax
  __int64 v81; // rcx
  __int64 v82; // rax
  __int64 v83; // rcx
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 v86; // rax
  __int64 v87; // rax
  unsigned int m; // ebx
  __int64 v89; // rcx
  __int64 v90; // rcx
  __int64 v91; // rcx
  __int64 v92; // rcx
  __int64 v93; // rcx
  __int64 v94; // rcx
  __int64 v95; // rcx
  __int64 v96; // rcx
  __int64 v97; // rcx
  __int64 v98; // rdx
  __int64 v99; // rcx
  __int64 v100; // rcx
  __int64 v101; // rcx
  int v102; // ebx
  __int64 v103; // rcx
  __int64 v104; // rcx
  void *v105; // rbx
  __int64 v106; // rax
  __int64 v107; // rcx
  int v108; // ebx
  unsigned int *v109; // rax
  __int64 v110; // rcx
  int v111; // ebx
  __int64 v112; // rcx
  __int64 v113; // rcx
  __int64 v114; // rcx
  __int64 v115; // rcx
  __int64 v116; // rcx
  unsigned int *v117; // [rsp+20h] [rbp-E0h]
  int *v118; // [rsp+20h] [rbp-E0h]
  int v119; // [rsp+28h] [rbp-D8h]
  unsigned int v120; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v121[4]; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v122; // [rsp+68h] [rbp-98h]
  unsigned int v123[2]; // [rsp+6Ch] [rbp-94h] BYREF
  int v124; // [rsp+74h] [rbp-8Ch] BYREF
  int v125; // [rsp+78h] [rbp-88h] BYREF
  int v126; // [rsp+7Ch] [rbp-84h] BYREF
  int v127; // [rsp+80h] [rbp-80h] BYREF
  int v128; // [rsp+84h] [rbp-7Ch] BYREF
  int v129; // [rsp+88h] [rbp-78h] BYREF
  int v130; // [rsp+8Ch] [rbp-74h] BYREF
  int v131; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v132; // [rsp+94h] [rbp-6Ch] BYREF
  __int128 v133; // [rsp+98h] [rbp-68h] BYREF
  __int64 v134; // [rsp+A8h] [rbp-58h]
  _QWORD v135[2]; // [rsp+B0h] [rbp-50h] BYREF
  struct _HEAD *v136; // [rsp+C0h] [rbp-40h]
  int v137; // [rsp+D0h] [rbp-30h]
  int v138; // [rsp+D4h] [rbp-2Ch]
  __int64 v139; // [rsp+D8h] [rbp-28h]
  int v140; // [rsp+E0h] [rbp-20h]
  int v141; // [rsp+E4h] [rbp-1Ch]
  __int64 v142; // [rsp+E8h] [rbp-18h]
  int v143; // [rsp+F0h] [rbp-10h]
  int v144; // [rsp+F4h] [rbp-Ch]
  int v145; // [rsp+F8h] [rbp-8h]
  int v146; // [rsp+FCh] [rbp-4h]
  int v147; // [rsp+100h] [rbp+0h]
  int v148; // [rsp+104h] [rbp+4h]
  int v149; // [rsp+108h] [rbp+8h]
  int v150; // [rsp+10Ch] [rbp+Ch]
  int v151; // [rsp+110h] [rbp+10h]
  int v152; // [rsp+114h] [rbp+14h]
  int v153; // [rsp+118h] [rbp+18h]
  int v154; // [rsp+11Ch] [rbp+1Ch]
  int v155; // [rsp+120h] [rbp+20h]
  int v156; // [rsp+124h] [rbp+24h]
  int v157; // [rsp+128h] [rbp+28h]
  int v158; // [rsp+12Ch] [rbp+2Ch]
  int v159; // [rsp+130h] [rbp+30h]
  int v160; // [rsp+134h] [rbp+34h]
  int v161; // [rsp+138h] [rbp+38h]
  int v162; // [rsp+13Ch] [rbp+3Ch]
  int v163; // [rsp+140h] [rbp+40h]
  int v164; // [rsp+144h] [rbp+44h]
  int v165; // [rsp+148h] [rbp+48h]
  int v166; // [rsp+14Ch] [rbp+4Ch]
  int v167; // [rsp+150h] [rbp+50h]
  int v168; // [rsp+154h] [rbp+54h]
  int v169; // [rsp+158h] [rbp+58h]
  int v170; // [rsp+15Ch] [rbp+5Ch]
  int v171; // [rsp+160h] [rbp+60h]
  int v172; // [rsp+164h] [rbp+64h]
  int v173; // [rsp+168h] [rbp+68h]
  int v174; // [rsp+16Ch] [rbp+6Ch]
  int v175; // [rsp+170h] [rbp+70h]
  int v176; // [rsp+174h] [rbp+74h]
  __int64 v177; // [rsp+178h] [rbp+78h]
  int v178; // [rsp+180h] [rbp+80h]
  int v179; // [rsp+184h] [rbp+84h]
  __int64 v180; // [rsp+188h] [rbp+88h]
  int v181; // [rsp+190h] [rbp+90h]
  int v182; // [rsp+194h] [rbp+94h]
  int v183; // [rsp+198h] [rbp+98h]
  int v184; // [rsp+19Ch] [rbp+9Ch]
  int v185; // [rsp+1A0h] [rbp+A0h]
  int v186; // [rsp+1A4h] [rbp+A4h]
  int v187; // [rsp+1A8h] [rbp+A8h]
  int v188; // [rsp+1ACh] [rbp+ACh]
  int v189; // [rsp+1B0h] [rbp+B0h]
  int v190; // [rsp+1B4h] [rbp+B4h]
  int v191; // [rsp+1B8h] [rbp+B8h]
  int v192; // [rsp+1BCh] [rbp+BCh]
  int v193; // [rsp+1C0h] [rbp+C0h]
  int v194; // [rsp+1C4h] [rbp+C4h]
  int v195; // [rsp+1C8h] [rbp+C8h]
  int v196; // [rsp+1CCh] [rbp+CCh]
  int v197; // [rsp+1D0h] [rbp+D0h]
  int v198; // [rsp+1D4h] [rbp+D4h]
  __int64 v199; // [rsp+1D8h] [rbp+D8h]
  int v200; // [rsp+1E0h] [rbp+E0h]
  int v201; // [rsp+1E4h] [rbp+E4h]
  __int64 v202; // [rsp+1E8h] [rbp+E8h]
  int v203; // [rsp+1F0h] [rbp+F0h]
  int v204; // [rsp+1F4h] [rbp+F4h]
  int v205; // [rsp+1F8h] [rbp+F8h]
  int v206; // [rsp+1FCh] [rbp+FCh]
  int v207; // [rsp+200h] [rbp+100h]
  int v208; // [rsp+204h] [rbp+104h]
  int v209; // [rsp+208h] [rbp+108h]
  int v210; // [rsp+20Ch] [rbp+10Ch]
  int v211; // [rsp+210h] [rbp+110h]
  int v212; // [rsp+214h] [rbp+114h]
  int v213; // [rsp+218h] [rbp+118h]
  int v214; // [rsp+21Ch] [rbp+11Ch]
  int v215; // [rsp+220h] [rbp+120h]
  int v216; // [rsp+224h] [rbp+124h]
  int v217; // [rsp+228h] [rbp+128h]
  int v218; // [rsp+22Ch] [rbp+12Ch]
  int v219; // [rsp+230h] [rbp+130h]
  int v220; // [rsp+234h] [rbp+134h]
  int v221; // [rsp+238h] [rbp+138h]
  int v222; // [rsp+23Ch] [rbp+13Ch]
  int v223; // [rsp+240h] [rbp+140h]
  int v224; // [rsp+244h] [rbp+144h]
  int v225; // [rsp+248h] [rbp+148h]
  int v226; // [rsp+24Ch] [rbp+14Ch]
  int v227; // [rsp+250h] [rbp+150h]
  int v228; // [rsp+254h] [rbp+154h]
  int v229; // [rsp+258h] [rbp+158h]
  int v230; // [rsp+25Ch] [rbp+15Ch]
  int v231; // [rsp+260h] [rbp+160h]
  int v232; // [rsp+264h] [rbp+164h]
  __int64 v233; // [rsp+268h] [rbp+168h]
  __int64 v234; // [rsp+270h] [rbp+170h]
  int v235; // [rsp+280h] [rbp+180h] BYREF
  __int64 v236; // [rsp+288h] [rbp+188h]
  int v237; // [rsp+290h] [rbp+190h]
  __int64 v238; // [rsp+298h] [rbp+198h]
  int v239; // [rsp+2A0h] [rbp+1A0h]
  __int64 v240; // [rsp+2A8h] [rbp+1A8h]
  int v241; // [rsp+2B0h] [rbp+1B0h]
  __int64 v242; // [rsp+2B8h] [rbp+1B8h]
  int v243; // [rsp+2C0h] [rbp+1C0h]
  __int64 v244; // [rsp+2C8h] [rbp+1C8h]
  int v245; // [rsp+2D0h] [rbp+1D0h]
  int *v246; // [rsp+2D8h] [rbp+1D8h]
  int v247; // [rsp+2E0h] [rbp+1E0h]
  __int64 v248; // [rsp+2E8h] [rbp+1E8h]
  int v249; // [rsp+2F0h] [rbp+1F0h]
  __int64 v250; // [rsp+2F8h] [rbp+1F8h]
  int v251; // [rsp+300h] [rbp+200h] BYREF
  __int64 v252; // [rsp+308h] [rbp+208h]
  int v253; // [rsp+310h] [rbp+210h]
  __int64 v254; // [rsp+318h] [rbp+218h]
  int v255; // [rsp+320h] [rbp+220h]
  __int64 v256; // [rsp+328h] [rbp+228h]
  int v257; // [rsp+330h] [rbp+230h]
  int *v258; // [rsp+338h] [rbp+238h]
  int v259; // [rsp+340h] [rbp+240h]
  __int64 v260; // [rsp+348h] [rbp+248h]
  int v261; // [rsp+350h] [rbp+250h]
  __int64 v262; // [rsp+358h] [rbp+258h]
  int v263; // [rsp+360h] [rbp+260h]
  __int64 v264; // [rsp+368h] [rbp+268h]
  int v265; // [rsp+370h] [rbp+270h]
  __int64 v266; // [rsp+378h] [rbp+278h]
  int v267; // [rsp+380h] [rbp+280h]
  __int64 v268; // [rsp+388h] [rbp+288h]
  int v269; // [rsp+390h] [rbp+290h]
  int *v270; // [rsp+398h] [rbp+298h]
  int v271; // [rsp+3A0h] [rbp+2A0h]
  __int64 v272; // [rsp+3A8h] [rbp+2A8h]
  int v273; // [rsp+3B0h] [rbp+2B0h]
  int *v274; // [rsp+3B8h] [rbp+2B8h]
  int v275; // [rsp+3C0h] [rbp+2C0h]
  __int64 v276; // [rsp+3C8h] [rbp+2C8h]
  int v277; // [rsp+3D0h] [rbp+2D0h]
  __int64 v278; // [rsp+3D8h] [rbp+2D8h]
  int v279; // [rsp+3E0h] [rbp+2E0h]
  __int64 v280; // [rsp+3E8h] [rbp+2E8h]
  int v281; // [rsp+3F0h] [rbp+2F0h]
  __int64 v282; // [rsp+3F8h] [rbp+2F8h]
  int v283; // [rsp+400h] [rbp+300h]
  __int64 v284; // [rsp+408h] [rbp+308h]
  int v285; // [rsp+410h] [rbp+310h]
  int *v286; // [rsp+418h] [rbp+318h]
  unsigned __int16 v287[14]; // [rsp+420h] [rbp+320h] BYREF
  int v288; // [rsp+43Ch] [rbp+33Ch]
  _BYTE v289[80]; // [rsp+470h] [rbp+370h] BYREF

  v234 = a2;
  v2 = a1;
  v125 = a1;
  v124 = *(_DWORD *)(*(_QWORD *)(W32GetSessionState(a1) + 96) + 20348LL);
  v123[0] = 96;
  v4 = *(_DWORD *)(W32GetUserSessionState(v3) + 66784) & 0x100000;
  v134 = -1;
  v130 = v4;
  v133 = 0;
  v120 = 0;
  v128 = 0;
  v138 = 4135;
  v137 = 4;
  v139 = 112;
  v5 = *(_DWORD *)(W32GetUserSessionState(v4) + 66784);
  v131 = 0;
  v127 = 1;
  v129 = v5 & 0x10000;
  v140 = 4;
  v141 = 17;
  v142 = 100;
  v143 = 4;
  v144 = 77;
  v145 = 199;
  v146 = 4;
  v147 = 4;
  v148 = 76;
  v149 = 198;
  v150 = 4;
  v151 = 4;
  v152 = 105;
  v153 = 14;
  v154 = 3;
  v155 = 4;
  v156 = 109;
  v157 = 15;
  v158 = 3;
  v159 = 4;
  v160 = 131;
  v161 = 18;
  v162 = 1;
  v163 = 4;
  v164 = 141;
  v165 = 624;
  v166 = 1;
  v167 = 4;
  v168 = 145;
  v169 = 625;
  v170 = 1;
  v171 = 4;
  v172 = 143;
  v173 = 626;
  v174 = 1;
  v175 = 4;
  v176 = 159;
  v177 = 628;
  v178 = 13;
  v179 = 23;
  v180 = 106;
  v181 = 13;
  v182 = 11;
  v183 = 13;
  v184 = 15;
  v213 = 17;
  v198 = 96;
  v194 = 30;
  v214 = 30;
  v222 = 30;
  v202 = 96;
  v226 = 50;
  v230 = 50;
  v185 = 12;
  v186 = 32;
  v187 = 6;
  v188 = 500;
  v189 = 12;
  v190 = 29;
  v191 = 97;
  v192 = 4;
  v193 = 12;
  v195 = 98;
  v196 = 4;
  v197 = 12;
  v199 = 7;
  v200 = 3;
  v201 = 28;
  v203 = 35;
  v204 = 111;
  v205 = 236;
  v206 = 1;
  v207 = 12;
  v208 = 127;
  v209 = 16;
  v210 = 1;
  v211 = 12;
  v212 = 129;
  v215 = 12;
  v216 = 133;
  v217 = 19;
  v218 = 20;
  v219 = 12;
  v220 = 135;
  v221 = 20;
  v223 = 12;
  v224 = 137;
  v225 = 21;
  v227 = 12;
  v228 = 139;
  v229 = 22;
  v231 = 4;
  v232 = 169;
  v233 = 205;
  v251 = 4;
  v252 = 94;
  v253 = 400;
  UserSessionState = W32GetUserSessionState(20);
  v256 = 107;
  v255 = 4;
  v254 = UserSessionState + 65800;
  v258 = &v130;
  v257 = 2;
  v259 = 4;
  v260 = 159;
  v261 = 3;
  v8 = *(_QWORD *)(W32GetUserSessionState(v7) + 19704) + 4996LL;
  v263 = 4;
  v262 = v8;
  v264 = 160;
  v265 = 3;
  v266 = *(_QWORD *)(W32GetUserSessionState(v8) + 19704) + 5000LL;
  v270 = &v124;
  v274 = &v128;
  v267 = 4;
  v268 = 200;
  v269 = 0;
  v271 = 4;
  v272 = 618;
  v273 = 0;
  v275 = 4;
  v276 = 621;
  v277 = 5000;
  v9 = W32GetUserSessionState(v266);
  v279 = 4;
  v278 = v9 + 69104;
  v280 = 622;
  v281 = 5000;
  v11 = W32GetUserSessionState(v10);
  v283 = 23;
  v284 = 149;
  v282 = v11 + 36248;
  v12 = 1;
  v285 = 1;
  v286 = &v129;
  v235 = 12;
  v236 = 10;
  v237 = 6;
  v14 = W32GetUserSessionState(v13);
  v239 = 12;
  v240 = 11;
  v238 = v14 + 16232;
  v241 = 10;
  v16 = W32GetUserSessionState(v15);
  v243 = 12;
  v242 = v16 + 16236;
  v246 = &v127;
  v244 = 12;
  v245 = 1;
  v247 = 35;
  v248 = 237;
  v249 = 0;
  v18 = v2 & 4;
  v250 = W32GetUserSessionState(v17) + 14652;
  v20 = v2 & 2;
  v123[1] = v18;
  v21 = v2 & 1;
  if ( (v2 & 0x10) != 0 )
  {
    v22 = *(HANDLE *)(W32GetUserSessionState(v19) + 63312);
    if ( PsGetCurrentProcessId() != v22 )
    {
LABEL_3:
      v24 = 5;
LABEL_32:
      UserSetLastError(v24);
      goto LABEL_33;
    }
    if ( v20 || v21 || v18 )
    {
      v24 = 87;
      goto LABEL_32;
    }
    if ( *(_DWORD *)(W32GetUserSessionState(v23) + 308) )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
      {
        v12 = 0;
      }
      v26 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v12 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        CurrentWin32kSessionId = W32GetCurrentWin32kSessionId();
        v29 = W32GetUserSessionState(v28);
        LOBYTE(v30) = v26;
        LOBYTE(v31) = v12;
        WPP_RECORDER_AND_TRACE_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v31,
          v30,
          *(_QWORD *)(v29 + 69152),
          4,
          20,
          11,
          (__int64)WPP_6f3f2e22ce9e317051f30d9635f1d0e7_Traceguids,
          CurrentWin32kSessionId);
      }
      *(_DWORD *)(W32GetUserSessionState(v25) + 308) = 0;
      AttachInputDevices(1);
      v33 = W32GetUserSessionState(v32);
      CHidInput::HandleDirectStartStopDeviceReadRequest(*(CHidInput **)(v33 + 16792));
    }
  }
  else
  {
    if ( (v2 & 2) == 0 )
    {
      v34 = *(HANDLE *)(W32GetUserSessionState(v19) + 63312);
      if ( PsGetCurrentProcessId() != v34 )
        goto LABEL_3;
    }
    v36 = (struct _UNICODE_STRING *)CreateProfileUserName(&v133);
    if ( !v36 )
    {
LABEL_33:
      if ( v134 != -1 )
        PopAndFreeAlwaysW32ThreadLock(&v133);
      return 0;
    }
    v37 = 0;
    v122 = 0;
    if ( *(_QWORD *)(W32GetUserSessionState(v35) + 63288) )
    {
      v39 = *(_QWORD *)(W32GetUserSessionState(v38) + 63288);
      v40 = *(void **)(v39 + 176);
      if ( v40 )
        Win32FreePool(v40);
      v41 = Win32AllocPoolZInit(v36->Length, 1852863317);
      *(_QWORD *)(v39 + 176) = v41;
      if ( v41 )
      {
        *(_WORD *)(v39 + 170) = v36->Length;
        *(_WORD *)(v39 + 168) = 0;
        RtlCopyUnicodeString((PUNICODE_STRING)(v39 + 168), v36);
      }
      if ( v21 )
        WakeRIT(64);
    }
    if ( v20 && !v18 )
    {
      v122 = CheckEasPolicyChange();
      if ( !(unsigned int)CheckDesktopPolicyChange(v36) && !v122 )
      {
        v24 = 0;
        goto LABEL_32;
      }
      v37 = 16;
    }
    if ( v21 )
    {
      v43 = W32GetUserSessionState(v38);
      *(_DWORD *)(v43 + 62552) |= 2u;
    }
    v120 = 300;
    v44 = v37 | 8;
    if ( !v18 )
      v44 = v37;
    v45 = W32GetUserSessionState(v38);
    FastGetProfileValue(v36, 4, 607, &v120, v45 + 63968, 4, v44);
    if ( *(int *)(W32GetUserSessionState(v46) + 63968) > 0 )
    {
      v50 = 1000;
      if ( *(int *)(W32GetUserSessionState(v47) + 63968) < 1000 )
        v50 = *(_DWORD *)(W32GetUserSessionState(v51) + 63968);
      v48 = W32GetUserSessionState(v51);
    }
    else
    {
      v48 = W32GetUserSessionState(v47);
      v50 = 1000;
    }
    *(_DWORD *)(v48 + 63968) = v50;
    v52 = W32GetUserSessionState(v49);
    v54 = v52;
    if ( v21 )
    {
      if ( !*(_DWORD *)(v52 + 66048) && !(unsigned int)UserRemoteConnectedSessionUsingWddm() )
      {
        FastGetProfileDwordEx(v36, 4, L"LogPixels", 0, v44, v123, 0);
        v126 = 0;
        v55 = DrvInitializeDxgkrnlDpiCache(&v126);
        v57 = PerformLegacyDpiUpgrade(v36, v123[0]);
        if ( v55 < 0
          || v126
          || (v58 = Gre::Base::Globals(v56), v53 = *((unsigned __int16 *)v58 + 584), *((_WORD *)v58 + 585) != (_WORD)v53)
          || v57
          || v123[0] )
        {
          GreReinitializeDpiSetting();
          v121[0] = 0;
          LOBYTE(v119) = 0;
          if ( (int)xxxUserSetDisplayConfig(0, 0, 2191, 516, 0, v119, 0, 0, v121, v234, 0) >= 0 )
          {
            if ( v121[0] )
              xxxUserResetDisplayDevice();
            v59 = W32GetUserSessionState(v53);
            UserReinitializeStockFonts(*(unsigned __int16 *)(*(_QWORD *)(v59 + 19704) + 6998LL), 1);
            *(_DWORD *)(v54 + 66048) = 1;
          }
        }
      }
    }
    v60 = W32GetUserSessionState(v53);
    CInputGlobals::UpdateWakeOnInputDeviceTypesFromRegistry(*(CInputGlobals **)(v60 + 3008));
    LoadCPUserPreferences(v36, v44);
    if ( !v20 )
    {
      xxxODI_ColorInit(v36);
      LW_LoadResources(v36);
      if ( (unsigned int)GreTextInitialized() )
        xxxSetWindowNCMetrics(v36, 0);
      SetMinMetrics(v36);
      SetIconMetrics(v36);
      GetKbdLangSwitch(v36);
      ZwSetDefaultLocale(1u, 0);
      ZwSetDefaultUILanguage(0);
      v62 = W32GetUserSessionState(v61);
      ZwQueryDefaultUILanguage((LANGID *)(*(_QWORD *)(v62 + 19704) + 7012LL));
      xxxLoadSomeStrings();
      if ( *(_QWORD *)(W32GetUserSessionState(v63) + 63288) )
      {
        SmartObjStackRef<tagMENU>::SmartObjStackRef<tagMENU>(v135);
        for ( i = *(_QWORD **)(*(_QWORD *)(W32GetUserSessionState(v65) + 63288) + 16LL); i; i = (_QWORD *)i[4] )
        {
          if ( i[7] )
          {
            v136 = 0;
            SmartObjStackRefBase<tagMENU>::operator=(v135);
            if ( UnlockDesktopSysMenu(i + 7) )
            {
              v67 = v136;
              if ( !v136 )
                v67 = *(struct _HEAD **)v135[0];
              DestroyMenu(v67);
            }
          }
          if ( i[8] )
          {
            v136 = 0;
            SmartObjStackRefBase<tagMENU>::operator=(v135);
            if ( UnlockDesktopSysMenu(i + 8) )
            {
              v68 = v136;
              if ( !v136 )
                v68 = *(struct _HEAD **)v135[0];
              DestroyMenu(v68);
            }
          }
        }
        SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(v135);
      }
      v69 = W32GetUserSessionState(v64);
      CCursorSizes::zzzRefreshSizes(*(CCursorSizes **)(v69 + 36176));
      xxxUpdateSystemCursorsFromRegistry(v36, 1);
      xxxUpdateSystemIconsFromRegistry(v36);
      for ( j = 0; j < 0xF; ++j )
      {
        v119 = 0;
        v117 = &v120;
        if ( (unsigned int)FastGetProfileIntFromID(
                             v36,
                             (unsigned int)*(&v178 + 4 * (int)j),
                             *((unsigned int *)&v180 + 4 * (int)j)) )
          xxxSystemParametersInfo((unsigned int)*(&v179 + 4 * (int)j), v120, 0, 0x8000, &v120, 0);
      }
      FastGetProfileIntsW(v36, &v235, 4);
      LOBYTE(v71) = v127 != 0;
      EnableMouseAcceleration(v71);
    }
    xxxSystemParametersInfo(21, 0xFFFFFFFFLL, 0, 0, v117, v119);
    if ( v21 )
    {
      W32GetUserSessionState(v72);
      FastGetProfileIntFromID(v36, 35, 236);
    }
    for ( k = 0; k < 0xB; ++k )
    {
      if ( (unsigned int)FastGetProfileIntFromID(
                           v36,
                           (unsigned int)*(&v137 + 4 * (int)k),
                           *((unsigned int *)&v139 + 4 * (int)k)) )
        xxxSystemParametersInfo((unsigned int)*(&v138 + 4 * (int)k), v120, 0, 0x8000, &v120, v44);
    }
    v74 = v44;
    if ( v122 )
      v74 = 2;
    CalcScreenSaverTimeout(v36, v74);
    FastGetProfileIntsW(v36, &v251, 9);
    if ( v128 )
    {
      v76 = *(volatile signed __int32 **)(W32GetUserSessionState(v75) + 19704);
      _InterlockedOr(v76, 0x200u);
    }
    else
    {
      v76 = *(volatile signed __int32 **)(W32GetUserSessionState(v75) + 19704);
      _InterlockedAnd(v76, 0xFFFFFDFF);
    }
    if ( v129 )
    {
      v77 = W32GetUserSessionState(v76);
      *(_DWORD *)(v77 + 66784) |= 0x10000u;
    }
    else
    {
      v79 = W32GetUserSessionState(v76);
      *(_DWORD *)(v79 + 66784) &= ~0x10000u;
    }
    if ( v130 == 2 )
    {
      v80 = W32GetUserSessionState(v78);
      if ( (unsigned int)GreGetDeviceCaps(*(_QWORD *)(*(_QWORD *)(v80 + 56744) + 56LL), 119) )
      {
        v84 = W32GetUserSessionState(v81);
        *(_DWORD *)(v84 + 66784) &= ~0x100000u;
      }
      else
      {
        v82 = W32GetUserSessionState(v81);
        *(_DWORD *)(v82 + 66784) |= 0x100000u;
      }
      if ( v21 )
      {
        v85 = W32GetUserSessionState(v83);
        RtlStringCchPrintfW(v287, 0x28u, L"%d", (*(_DWORD *)(v85 + 66784) >> 20) & 1);
        RtlLoadStringOrError(107, v289);
        FastWriteProfileStringW(v36, 4, v289, v287);
      }
    }
    else if ( v130 )
    {
      v86 = W32GetUserSessionState(v78);
      *(_DWORD *)(v86 + 66784) |= 0x100000u;
    }
    else
    {
      v87 = W32GetUserSessionState(v78);
      *(_DWORD *)(v87 + 66784) &= ~0x100000u;
    }
    v120 = *(_DWORD *)(*(_QWORD *)(W32GetUserSessionState(v83) + 19704) + 4984LL);
    if ( (unsigned int)FastGetProfileIntFromID(v36, 4, 4) )
      SetCaretBlinkTime(v120);
    if ( !v20 )
    {
      v122 = 0;
      FastGetProfileIntFromID(v36, 12, 608);
      UpdateMouseSensitivity(v122);
      for ( m = 0; m < 2; ++m )
      {
        ReadDefaultAccelerationCurves(m, v36);
        ResetAccelerationCurves(m);
      }
      FastGetProfileIntFromID(v36, 12, 613);
      SetMouseTrails(v120);
      FastGetProfileIntW(v36, 7, L"TTOnly");
      GreSetFontEnumeration(v120);
      W32GetUserSessionState(v89);
      W32GetUserSessionState(v90);
      FastGetProfileIntFromID(v36, 12, 91);
      W32GetUserSessionState(v91);
      W32GetUserSessionState(v92);
      FastGetProfileIntFromID(v36, 12, 92);
      W32GetUserSessionState(v93);
      W32GetUserSessionState(v94);
      FastGetProfileIntFromID(v36, 12, 93);
      if ( *(_DWORD *)(W32GetUserSessionState(v95) + 16228) < 0xAu )
        *(_DWORD *)(W32GetUserSessionState(v96) + 16228) = 10;
      if ( *(_DWORD *)(W32GetUserSessionState(v96) + 16228) > 0x7FFFFFFFu )
        *(_DWORD *)(W32GetUserSessionState(v97) + 16228) = 0x7FFFFFFF;
      ReadRawMouseThrottlingThresholds(v36);
      UpdatePerUserKeyboardIndicators(v36);
      InitScancodeMap(v99, v98);
      W32GetUserSessionState(v100);
      FastGetProfileDword(v36, 24, L"Attributes");
      v102 = (*(_DWORD *)(W32GetUserSessionState(v101) + 14128) >> 15) & 2;
      *(_DWORD *)(W32GetUserSessionState(v103) + 14128) = v102;
      xxxUpdatePerUserAccessPackSettings(v36);
    }
    v105 = (void *)OpenCacheKeyEx(0, 22, 131097);
    if ( v105 )
    {
      *(_DWORD *)(*(_QWORD *)(W32GetUserSessionState(v104) + 19704) + 2148LL) = 1;
      ZwClose(v105);
    }
    v106 = W32GetUserSessionState(v104);
    *(_DWORD *)(*(_QWORD *)(v106 + 19704) + 2148LL) |= 2u;
    GreSetFontEnumeration(4);
    GreSetFontEnumeration(32);
    if ( (v124 & 2) != 0 )
      GreSetFontEnumeration(v124 | 4u);
    if ( (*(_DWORD *)UPDWORDPointer(8202) & 2) != 0 )
      GreSetFontEnumeration(v124 | 0x30u);
    v108 = *(_DWORD *)UPDWORDPointer(8204);
    if ( !v108 )
      v108 = 1200;
    *(_DWORD *)(*(_QWORD *)(W32GetSessionState(v107) + 96) + 13448LL) = v108;
    v109 = (unsigned int *)UPDWORDPointer(8210);
    GreSetLCDOrientation(*v109);
    v111 = *(_DWORD *)(W32GetUserSessionState(v110) + 66792) & 0x400;
    *(_DWORD *)(*(_QWORD *)(W32GetSessionState(v112) + 96) + 24304LL) = v111;
    if ( v125 == 2 )
      xxxUserResetDisplayDevice();
    v118 = &v131;
    FastGetProfileDword(0, 49, L"RestrictDebuggerForeground");
    if ( v131 )
      *(_DWORD *)(W32GetUserSessionState(v113) + 18940) = 1;
    if ( v21 )
    {
      memset_0(v287, 0, 0x44u);
      if ( (unsigned int)ReadPointerDeviceSettings(146, v287) )
      {
        if ( !v288 )
          SetTouchInputStatus(0);
      }
    }
    if ( *(_DWORD *)(W32GetUserSessionState(v113) + 62704) == 1 )
    {
      v125 = 0;
      *(_DWORD *)(W32GetUserSessionState(v114) + 62704) = 0;
      UserLogError(3221226518LL);
      UserSessionSwitchLeaveCrit();
      LODWORD(v118) = 7;
      ExRaiseHardError(3221226518LL, 0, 0, 0, v118, &v125);
      EnterCrit(1, 0);
    }
    xxxDwmControl(1037, 0);
    LOBYTE(v115) = *(_DWORD *)UPDWORDPointer(8244) != 0;
    SendCrosshairEnabledStatusChanged(v115);
    v132 = 0;
    if ( (unsigned int)ReadPointerDeviceSettings(178, &v132) )
      SendCrosshairPropertiesChanged(v132);
    ReadInputHapticSettings();
    if ( v21 )
    {
      TraceLoggingAutoRotationStateEvent();
      _InterlockedOr(*(volatile signed __int32 **)(W32GetUserSessionState(v116) + 19704), 0x400u);
    }
  }
  if ( v134 != -1 )
    PopAndFreeAlwaysW32ThreadLock(&v133);
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
