# xxxUpdatePerUserSystemParameters

- ea: `0x14023f1a0`
- end: `0x140240741`
- name: `xxxUpdatePerUserSystemParameters`
- size: `5537`
- prototype: ``
- caller_count: `1`
- callee_count: `37`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14023f0d0`

## callees

- `0x1400150d0`
- `0x14003a604`
- `0x14003cc60`
- `0x140077cc8`
- `0x1400b0b40`
- `0x1400b1334`
- `0x1400b162c`
- `0x1400c2a10`
- `0x1400c9ff4`
- `0x1400ca268`
- `0x1400ca574`
- `0x1400caa08`
- `0x1400cf408`
- `0x1400d0a70`
- `0x1400d1f04`
- `0x1400d5474`
- `0x1400ec110`
- `0x1401830b0`
- `0x140192cd4`
- `0x140200450`
- `0x140202070`
- `0x14020aa94`
- `0x14021aee8`
- `0x14021b4d8`
- `0x14021f0d0`
- `0x1402313dc`
- `0x1402355fc`
- `0x140237064`
- `0x14023f1a0`
- `0x140245ad0`
- `0x140255320`
- `0x14025a000`
- `0x140267a5c`
- `0x14027d464`
- `0x1402ab4fc`
- `0x140341ff0`
- `0x140342540`

## import_xrefs

- `ntoskrnl!ExRaiseHardError` at `0x14024065a`
- `ntoskrnl!ExRaiseHardError` at `0x14024065a`
- `ntoskrnl!ZwQueryDefaultUILanguage` at `0x14023fd10`
- `ntoskrnl!ZwQueryDefaultUILanguage` at `0x14023fd10`
- `ntoskrnl!ZwSetDefaultUILanguage` at `0x14023fcea`
- `ntoskrnl!ZwSetDefaultUILanguage` at `0x14023fcea`
- `ntoskrnl!ZwSetDefaultLocale` at `0x14023fcdc`
- `ntoskrnl!ZwSetDefaultLocale` at `0x14023fcdc`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14023f7b7`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14023f901`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14023f7b7`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14023f901`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14023f9b8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14023f9b8`
- `ntoskrnl!ZwClose` at `0x140240474`
- `ntoskrnl!ZwClose` at `0x140240474`
- `win32kbase!OpenCacheKeyEx` at `0x14024043f`
- `win32kbase!OpenCacheKeyEx` at `0x14024043f`
- `win32kbase!FastGetProfileIntW` at `0x140240247`
- `win32kbase!FastGetProfileIntW` at `0x140240247`
- `win32kbase!xxxSystemParametersInfo` at `0x14023fe72`
- `win32kbase!xxxSystemParametersInfo` at `0x14023fec5`
- `win32kbase!xxxSystemParametersInfo` at `0x14023ff58`
- `win32kbase!xxxSystemParametersInfo` at `0x14023fe72`
- `win32kbase!xxxSystemParametersInfo` at `0x14023fec5`
- `win32kbase!xxxSystemParametersInfo` at `0x14023ff58`
- `win32kbase!CheckDesktopPolicyChange` at `0x14023f9eb`
- `win32kbase!CheckDesktopPolicyChange` at `0x14023f9eb`
- `win32kbase!UserRemoteConnectedSessionUsingWddm` at `0x14023fb1b`
- `win32kbase!UserRemoteConnectedSessionUsingWddm` at `0x14023fb1b`
- `win32kbase!FastGetProfileDwordEx` at `0x14023fb52`
- `win32kbase!FastGetProfileDwordEx` at `0x14023fb52`
- `win32kbase!DrvInitializeDxgkrnlDpiCache` at `0x14023fb67`
- `win32kbase!DrvInitializeDxgkrnlDpiCache` at `0x14023fb67`
- `win32kbase!GreReinitializeDpiSetting` at `0x14023fbbf`
- `win32kbase!GreReinitializeDpiSetting` at `0x14023fbbf`
- `win32kbase!xxxUserSetDisplayConfig` at `0x14023fc0d`
- `win32kbase!xxxUserSetDisplayConfig` at `0x14023fc0d`
- `win32kbase!?UpdateWakeOnInputDeviceTypesFromRegistry@CInputGlobals@@QEAAXXZ` at `0x14023fc6f`
- `win32kbase!?UpdateWakeOnInputDeviceTypesFromRegistry@CInputGlobals@@QEAAXXZ` at `0x14023fc6f`
- `win32kbase!xxxODI_ColorInit` at `0x14023fc91`
- `win32kbase!xxxODI_ColorInit` at `0x14023fc91`
- `win32kbase!FastGetProfileIntsW` at `0x14023fe98`
- `win32kbase!FastGetProfileIntsW` at `0x14023ff97`
- `win32kbase!FastGetProfileIntsW` at `0x14023fe98`
- `win32kbase!FastGetProfileIntsW` at `0x14023ff97`
- `win32kbase!EnableMouseAcceleration` at `0x14023feac`
- `win32kbase!EnableMouseAcceleration` at `0x14023feac`
- `win32kbase!GreGetDeviceCaps` at `0x140240036`
- `win32kbase!GreGetDeviceCaps` at `0x140240036`
- `win32kbase!FastWriteProfileStringW` at `0x1402400de`
- `win32kbase!FastWriteProfileStringW` at `0x1402400de`
- `win32kbase!UpdateMouseSensitivity` at `0x1402401bb`
- `win32kbase!UpdateMouseSensitivity` at `0x1402401bb`
- `win32kbase!ReadDefaultAccelerationCurves` at `0x1402401d3`
- `win32kbase!ReadDefaultAccelerationCurves` at `0x1402401d3`
- `win32kbase!ResetAccelerationCurves` at `0x1402401e1`
- `win32kbase!ResetAccelerationCurves` at `0x1402401e1`
- `win32kbase!ReadRawMouseThrottlingThresholds` at `0x14024039b`
- `win32kbase!ReadRawMouseThrottlingThresholds` at `0x14024039b`
- `win32kbase!xxxUpdatePerUserAccessPackSettings` at `0x14024041c`
- `win32kbase!xxxUpdatePerUserAccessPackSettings` at `0x14024041c`
- `win32kbase!UserLogError` at `0x140240626`
- `win32kbase!UserLogError` at `0x140240626`
- `win32kbase!xxxDwmControl` at `0x14024067d`
- `win32kbase!xxxDwmControl` at `0x14024067d`
- `win32kbase!SendCrosshairEnabledStatusChanged` at `0x1402406a0`
- `win32kbase!SendCrosshairEnabledStatusChanged` at `0x1402406a0`
- `win32kbase!ReadPointerDeviceSettings` at `0x1402405cc`
- `win32kbase!ReadPointerDeviceSettings` at `0x1402406b9`
- `win32kbase!ReadPointerDeviceSettings` at `0x1402405cc`
- `win32kbase!ReadPointerDeviceSettings` at `0x1402406b9`
- `win32kbase!SendCrosshairPropertiesChanged` at `0x1402406cc`
- `win32kbase!SendCrosshairPropertiesChanged` at `0x1402406cc`
- `win32kbase!ReadInputHapticSettings` at `0x1402406d8`
- `win32kbase!ReadInputHapticSettings` at `0x1402406d8`
- `win32kbase!SetTouchInputStatus` at `0x1402405e7`
- `win32kbase!SetTouchInputStatus` at `0x1402405e7`
- `win32kbase!InitScancodeMap` at `0x1402403af`
- `win32kbase!InitScancodeMap` at `0x1402403af`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14023fb90`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14023fb90`
- `win32kbase!?CreateProfileUserName@@YAPEAU_UNICODE_STRING@@PEAU?$Win32RawOptionalLockedItemAlways@UtagPROFILEUSERNAME@@$1?Win32FreePool@@YAXPEAX@Z@@@Z` at `0x14023f91a`
- `win32kbase!?CreateProfileUserName@@YAPEAU_UNICODE_STRING@@PEAU?$Win32RawOptionalLockedItemAlways@UtagPROFILEUSERNAME@@$1?Win32FreePool@@YAXPEAX@Z@@@Z` at `0x14023f91a`
- `win32kbase!FastGetProfileValue` at `0x14023fa84`
- `win32kbase!FastGetProfileValue` at `0x14023fa84`
- `win32kbase!RtlLoadStringOrError` at `0x1402400be`
- `win32kbase!RtlLoadStringOrError` at `0x1402400be`
- `win32kbase!FastGetProfileIntFromID` at `0x14023fe4e`
- `win32kbase!FastGetProfileIntFromID` at `0x14023ff03`
- `win32kbase!FastGetProfileIntFromID` at `0x14023ff37`
- `win32kbase!FastGetProfileIntFromID` at `0x140240161`
- `win32kbase!FastGetProfileIntFromID` at `0x1402401ab`
- `win32kbase!FastGetProfileIntFromID` at `0x140240212`
- `win32kbase!FastGetProfileIntFromID` at `0x14024029f`
- `win32kbase!FastGetProfileIntFromID` at `0x1402402ee`
- `win32kbase!FastGetProfileIntFromID` at `0x140240336`
- `win32kbase!FastGetProfileIntFromID` at `0x14023fe4e`
- `win32kbase!FastGetProfileIntFromID` at `0x14023ff03`
- `win32kbase!FastGetProfileIntFromID` at `0x14023ff37`
- `win32kbase!FastGetProfileIntFromID` at `0x140240161`
- `win32kbase!FastGetProfileIntFromID` at `0x1402401ab`
- `win32kbase!FastGetProfileIntFromID` at `0x140240212`
- `win32kbase!FastGetProfileIntFromID` at `0x14024029f`
- `win32kbase!FastGetProfileIntFromID` at `0x1402402ee`
- `win32kbase!FastGetProfileIntFromID` at `0x140240336`
- `win32kbase!FastGetProfileDword` at `0x1402403e3`
- `win32kbase!FastGetProfileDword` at `0x140240585`
- `win32kbase!FastGetProfileDword` at `0x1402403e3`
- `win32kbase!FastGetProfileDword` at `0x140240585`
- `win32kbase!?HandleDirectStartStopDeviceReadRequest@CHidInput@@QEAAXXZ` at `0x14023f8ce`
- `win32kbase!?HandleDirectStartStopDeviceReadRequest@CHidInput@@QEAAXXZ` at `0x14023f8ce`
- `win32kbase!UPDWORDPointer` at `0x1402404c7`
- `win32kbase!UPDWORDPointer` at `0x1402404eb`
- `win32kbase!UPDWORDPointer` at `0x14024051e`
- `win32kbase!UPDWORDPointer` at `0x14024068e`
- `win32kbase!UPDWORDPointer` at `0x1402404c7`
- `win32kbase!UPDWORDPointer` at `0x1402404eb`
- `win32kbase!UPDWORDPointer` at `0x14024051e`
- `win32kbase!UPDWORDPointer` at `0x14024068e`
- `win32kbase!EnterCrit` at `0x14024066a`
- `win32kbase!EnterCrit` at `0x14024066a`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x140240632`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x140240632`
- `win32kbase!Win32AllocPoolZInit` at `0x14023f985`
- `win32kbase!Win32AllocPoolZInit` at `0x14023f985`
- `win32kbase!Win32FreePool` at `0x14023f971`
- `win32kbase!Win32FreePool` at `0x14023f971`
- `WIN32K!W32GetSessionState` at `0x14023f1dd`
- `WIN32K!W32GetSessionState` at `0x140240503`
- `WIN32K!W32GetSessionState` at `0x14024054a`
- `WIN32K!W32GetSessionState` at `0x14023f1dd`
- `WIN32K!W32GetSessionState` at `0x140240503`
- `WIN32K!W32GetSessionState` at `0x14024054a`
- `WIN32K!W32GetUserSessionState` at `0x14023f200`
- `WIN32K!W32GetUserSessionState` at `0x14023f236`
- `WIN32K!W32GetUserSessionState` at `0x14023f542`
- `WIN32K!W32GetUserSessionState` at `0x14023f59b`
- `WIN32K!W32GetUserSessionState` at `0x14023f5d5`
- `WIN32K!W32GetUserSessionState` at `0x14023f656`
- `WIN32K!W32GetUserSessionState` at `0x14023f687`
- `WIN32K!W32GetUserSessionState` at `0x14023f6e4`
- `WIN32K!W32GetUserSessionState` at `0x14023f716`
- `WIN32K!W32GetUserSessionState` at `0x14023f769`
- `WIN32K!W32GetUserSessionState` at `0x14023f7a4`
- `WIN32K!W32GetUserSessionState` at `0x14023f7ed`
- `WIN32K!W32GetUserSessionState` at `0x14023f84d`
- `WIN32K!W32GetUserSessionState` at `0x14023f899`
- `WIN32K!W32GetUserSessionState` at `0x14023f8bb`
- `WIN32K!W32GetUserSessionState` at `0x14023f8ee`
- `WIN32K!W32GetUserSessionState` at `0x14023f939`
- `WIN32K!W32GetUserSessionState` at `0x14023f952`
- `WIN32K!W32GetUserSessionState` at `0x14023fa28`
- `WIN32K!W32GetUserSessionState` at `0x14023fa50`
- `WIN32K!W32GetUserSessionState` at `0x14023fa90`
- `WIN32K!W32GetUserSessionState` at `0x14023faa5`
- `WIN32K!W32GetUserSessionState` at `0x14023fab8`
- `WIN32K!W32GetUserSessionState` at `0x14023fad1`
- `WIN32K!W32GetUserSessionState` at `0x14023fae3`
- `WIN32K!W32GetUserSessionState` at `0x14023faf5`
- `WIN32K!W32GetUserSessionState` at `0x14023fc28`
- `WIN32K!W32GetUserSessionState` at `0x14023fc5c`
- `WIN32K!W32GetUserSessionState` at `0x14023fcf6`
- `WIN32K!W32GetUserSessionState` at `0x14023fd21`
- `WIN32K!W32GetUserSessionState` at `0x14023fd43`
- `WIN32K!W32GetUserSessionState` at `0x14023fdec`
- `WIN32K!W32GetUserSessionState` at `0x14023fed6`
- `WIN32K!W32GetUserSessionState` at `0x14023ffa9`
- `WIN32K!W32GetUserSessionState` at `0x14023ffc5`
- `WIN32K!W32GetUserSessionState` at `0x14023ffe5`
- `WIN32K!W32GetUserSessionState` at `0x14023fffb`
- `WIN32K!W32GetUserSessionState` at `0x14024001a`
- `WIN32K!W32GetUserSessionState` at `0x140240046`
- `WIN32K!W32GetUserSessionState` at `0x14024005c`
- `WIN32K!W32GetUserSessionState` at `0x140240079`
- `WIN32K!W32GetUserSessionState` at `0x1402400f0`
- `WIN32K!W32GetUserSessionState` at `0x140240106`
- `WIN32K!W32GetUserSessionState` at `0x14024011a`
- `WIN32K!W32GetUserSessionState` at `0x14024025c`
- `WIN32K!W32GetUserSessionState` at `0x14024026f`
- `WIN32K!W32GetUserSessionState` at `0x1402402ab`
- `WIN32K!W32GetUserSessionState` at `0x1402402be`
- `WIN32K!W32GetUserSessionState` at `0x1402402fa`
- `WIN32K!W32GetUserSessionState` at `0x14024030d`
- `WIN32K!W32GetUserSessionState` at `0x140240342`
- `WIN32K!W32GetUserSessionState` at `0x140240357`
- `WIN32K!W32GetUserSessionState` at `0x14024036d`
- `WIN32K!W32GetUserSessionState` at `0x140240386`
- `WIN32K!W32GetUserSessionState` at `0x1402403bb`
- `WIN32K!W32GetUserSessionState` at `0x1402403ef`
- `WIN32K!W32GetUserSessionState` at `0x140240407`
- `WIN32K!W32GetUserSessionState` at `0x140240453`
- `WIN32K!W32GetUserSessionState` at `0x140240487`
- `WIN32K!W32GetUserSessionState` at `0x140240531`
- `WIN32K!W32GetUserSessionState` at `0x140240597`
- `WIN32K!W32GetUserSessionState` at `0x1402405f3`
- `WIN32K!W32GetUserSessionState` at `0x14024060c`
- `WIN32K!W32GetUserSessionState` at `0x1402406ee`
- `WIN32K!W32GetUserSessionState` at `0x14023f200`
- `WIN32K!W32GetUserSessionState` at `0x14023f236`

## pseudocode

```c
__int64 __fastcall xxxUpdatePerUserSystemParameters(__int64 a1, __int64 a2)
{
  char v2; // bl
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // ecx
  __int64 UserSessionState; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // rax
  char v30; // di
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // rax
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // rax
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // r8
  __int64 v44; // r9
  int v45; // r12d
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // r8
  __int64 v49; // r9
  int v50; // r13d
  int v51; // r15d
  HANDLE v52; // rbx
  __int64 v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // r8
  __int64 v56; // r9
  __int64 v57; // rcx
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 v60; // r9
  struct MOVESIZEDATA *v61; // rcx
  bool v62; // si
  char CurrentWin32kSessionId; // bl
  __int64 v64; // rdx
  __int64 v65; // rcx
  __int64 v66; // r8
  __int64 v67; // r9
  __int64 v68; // rax
  int v69; // r8d
  int v70; // edx
  __int64 v71; // rdx
  __int64 v72; // rcx
  __int64 v73; // r8
  __int64 v74; // r9
  __int64 v75; // rax
  HANDLE v76; // rbx
  __int64 v77; // rdx
  __int64 v78; // rcx
  struct _UNICODE_STRING *v79; // rdi
  __int64 v80; // r8
  __int64 v81; // r9
  int v82; // r14d
  __int64 v83; // rdx
  __int64 v84; // rcx
  __int64 v85; // r8
  __int64 v86; // r9
  __int64 v87; // rbx
  void *v88; // rcx
  __int64 v89; // rax
  __int64 v91; // rax
  unsigned int v92; // esi
  __int64 v93; // rax
  __int64 v94; // rdx
  __int64 v95; // rcx
  __int64 v96; // r8
  __int64 v97; // r9
  __int64 v98; // rdx
  __int64 v99; // rcx
  __int64 v100; // r8
  __int64 v101; // r9
  __int64 v102; // rax
  __int64 v103; // rdx
  __int64 v104; // rcx
  __int64 v105; // r8
  __int64 v106; // r9
  int v107; // ebx
  __int64 v108; // rdx
  __int64 v109; // rcx
  __int64 v110; // r8
  __int64 v111; // r9
  __int64 v112; // rax
  __int64 v113; // rdx
  __int64 v114; // rcx
  __int64 v115; // r8
  __int64 v116; // r9
  __int64 v117; // r14
  int v118; // ebx
  Gre::Base *v119; // rcx
  int v120; // r12d
  struct Gre::Base::SESSION_GLOBALS *v121; // rax
  __int64 v122; // rax
  __int64 v123; // rax
  __int64 v124; // rdx
  __int64 v125; // rcx
  __int64 v126; // r8
  __int64 v127; // r9
  __int64 v128; // rax
  __int64 v129; // rdx
  __int64 v130; // rcx
  __int64 v131; // r8
  __int64 v132; // r9
  __int64 v133; // rdx
  __int64 v134; // rcx
  __int64 v135; // r8
  __int64 v136; // r9
  __int64 v137; // rdx
  __int64 v138; // rcx
  __int64 v139; // r8
  __int64 v140; // r9
  _QWORD *i; // rbx
  __int64 v142; // rdx
  struct _HEAD *v143; // rcx
  __int64 v144; // rdx
  struct _HEAD *v145; // rcx
  __int64 v146; // rax
  unsigned int j; // r14d
  __int64 v148; // rcx
  __int64 v149; // rdx
  __int64 v150; // rcx
  __int64 v151; // r8
  __int64 v152; // r9
  unsigned int k; // r14d
  unsigned int v154; // edx
  __int64 v155; // rdx
  __int64 v156; // rcx
  __int64 v157; // r8
  __int64 v158; // r9
  __int64 v159; // rdx
  volatile signed __int32 *v160; // rcx
  __int64 v161; // r8
  __int64 v162; // r9
  __int64 v163; // rax
  __int64 v164; // rdx
  __int64 v165; // rcx
  __int64 v166; // r8
  __int64 v167; // r9
  __int64 v168; // rax
  __int64 v169; // rax
  __int64 v170; // rdx
  __int64 v171; // rcx
  __int64 v172; // r8
  __int64 v173; // r9
  __int64 v174; // rax
  __int64 v175; // rdx
  __int64 v176; // rcx
  __int64 v177; // r8
  __int64 v178; // r9
  __int64 v179; // rax
  __int64 v180; // rax
  __int64 v181; // rax
  __int64 v182; // rax
  unsigned int m; // ebx
  __int64 v184; // rdx
  __int64 v185; // rcx
  __int64 v186; // r8
  __int64 v187; // r9
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
  __int64 v222; // rdx
  __int64 v223; // rcx
  __int64 v224; // r8
  __int64 v225; // r9
  __int64 v226; // rdx
  __int64 v227; // rcx
  __int64 v228; // r8
  __int64 v229; // r9
  int v230; // ebx
  __int64 v231; // rdx
  __int64 v232; // rcx
  __int64 v233; // r8
  __int64 v234; // r9
  __int64 v235; // rdx
  __int64 v236; // rcx
  void *v237; // rbx
  __int64 v238; // r8
  __int64 v239; // r9
  __int64 v240; // rax
  __int64 v241; // rcx
  int v242; // ebx
  unsigned int *v243; // rax
  __int64 v244; // rdx
  __int64 v245; // rcx
  __int64 v246; // r8
  __int64 v247; // r9
  int v248; // ebx
  __int64 v249; // rcx
  __int64 v250; // rdx
  __int64 v251; // rcx
  __int64 v252; // r8
  __int64 v253; // r9
  __int64 v254; // rdx
  __int64 v255; // rcx
  __int64 v256; // r8
  __int64 v257; // r9
  __int64 v258; // rdx
  __int64 v259; // rcx
  __int64 v260; // r8
  __int64 v261; // rcx
  __int64 v262; // rdx
  __int64 v263; // rcx
  __int64 v264; // r8
  __int64 v265; // r9
  unsigned int *v266; // [rsp+20h] [rbp-E0h]
  int *v267; // [rsp+20h] [rbp-E0h]
  int v268; // [rsp+28h] [rbp-D8h]
  unsigned int v269; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v270[4]; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v271; // [rsp+68h] [rbp-98h]
  unsigned int v272[2]; // [rsp+6Ch] [rbp-94h] BYREF
  int v273; // [rsp+74h] [rbp-8Ch] BYREF
  int v274; // [rsp+78h] [rbp-88h] BYREF
  int v275; // [rsp+7Ch] [rbp-84h] BYREF
  int v276; // [rsp+80h] [rbp-80h] BYREF
  int v277; // [rsp+84h] [rbp-7Ch] BYREF
  int v278; // [rsp+88h] [rbp-78h] BYREF
  int v279; // [rsp+8Ch] [rbp-74h] BYREF
  int v280; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v281; // [rsp+94h] [rbp-6Ch] BYREF
  __int128 v282; // [rsp+98h] [rbp-68h] BYREF
  __int64 v283; // [rsp+A8h] [rbp-58h]
  _QWORD v284[2]; // [rsp+B0h] [rbp-50h] BYREF
  struct _HEAD *v285; // [rsp+C0h] [rbp-40h]
  int v286; // [rsp+D0h] [rbp-30h]
  int v287; // [rsp+D4h] [rbp-2Ch]
  __int64 v288; // [rsp+D8h] [rbp-28h]
  int v289; // [rsp+E0h] [rbp-20h]
  int v290; // [rsp+E4h] [rbp-1Ch]
  __int64 v291; // [rsp+E8h] [rbp-18h]
  int v292; // [rsp+F0h] [rbp-10h]
  int v293; // [rsp+F4h] [rbp-Ch]
  int v294; // [rsp+F8h] [rbp-8h]
  int v295; // [rsp+FCh] [rbp-4h]
  int v296; // [rsp+100h] [rbp+0h]
  int v297; // [rsp+104h] [rbp+4h]
  int v298; // [rsp+108h] [rbp+8h]
  int v299; // [rsp+10Ch] [rbp+Ch]
  int v300; // [rsp+110h] [rbp+10h]
  int v301; // [rsp+114h] [rbp+14h]
  int v302; // [rsp+118h] [rbp+18h]
  int v303; // [rsp+11Ch] [rbp+1Ch]
  int v304; // [rsp+120h] [rbp+20h]
  int v305; // [rsp+124h] [rbp+24h]
  int v306; // [rsp+128h] [rbp+28h]
  int v307; // [rsp+12Ch] [rbp+2Ch]
  int v308; // [rsp+130h] [rbp+30h]
  int v309; // [rsp+134h] [rbp+34h]
  int v310; // [rsp+138h] [rbp+38h]
  int v311; // [rsp+13Ch] [rbp+3Ch]
  int v312; // [rsp+140h] [rbp+40h]
  int v313; // [rsp+144h] [rbp+44h]
  int v314; // [rsp+148h] [rbp+48h]
  int v315; // [rsp+14Ch] [rbp+4Ch]
  int v316; // [rsp+150h] [rbp+50h]
  int v317; // [rsp+154h] [rbp+54h]
  int v318; // [rsp+158h] [rbp+58h]
  int v319; // [rsp+15Ch] [rbp+5Ch]
  int v320; // [rsp+160h] [rbp+60h]
  int v321; // [rsp+164h] [rbp+64h]
  int v322; // [rsp+168h] [rbp+68h]
  int v323; // [rsp+16Ch] [rbp+6Ch]
  int v324; // [rsp+170h] [rbp+70h]
  int v325; // [rsp+174h] [rbp+74h]
  __int64 v326; // [rsp+178h] [rbp+78h]
  int v327; // [rsp+180h] [rbp+80h]
  int v328; // [rsp+184h] [rbp+84h]
  __int64 v329; // [rsp+188h] [rbp+88h]
  int v330; // [rsp+190h] [rbp+90h]
  int v331; // [rsp+194h] [rbp+94h]
  int v332; // [rsp+198h] [rbp+98h]
  int v333; // [rsp+19Ch] [rbp+9Ch]
  int v334; // [rsp+1A0h] [rbp+A0h]
  int v335; // [rsp+1A4h] [rbp+A4h]
  int v336; // [rsp+1A8h] [rbp+A8h]
  int v337; // [rsp+1ACh] [rbp+ACh]
  int v338; // [rsp+1B0h] [rbp+B0h]
  int v339; // [rsp+1B4h] [rbp+B4h]
  int v340; // [rsp+1B8h] [rbp+B8h]
  int v341; // [rsp+1BCh] [rbp+BCh]
  int v342; // [rsp+1C0h] [rbp+C0h]
  int v343; // [rsp+1C4h] [rbp+C4h]
  int v344; // [rsp+1C8h] [rbp+C8h]
  int v345; // [rsp+1CCh] [rbp+CCh]
  int v346; // [rsp+1D0h] [rbp+D0h]
  int v347; // [rsp+1D4h] [rbp+D4h]
  __int64 v348; // [rsp+1D8h] [rbp+D8h]
  int v349; // [rsp+1E0h] [rbp+E0h]
  int v350; // [rsp+1E4h] [rbp+E4h]
  __int64 v351; // [rsp+1E8h] [rbp+E8h]
  int v352; // [rsp+1F0h] [rbp+F0h]
  int v353; // [rsp+1F4h] [rbp+F4h]
  int v354; // [rsp+1F8h] [rbp+F8h]
  int v355; // [rsp+1FCh] [rbp+FCh]
  int v356; // [rsp+200h] [rbp+100h]
  int v357; // [rsp+204h] [rbp+104h]
  int v358; // [rsp+208h] [rbp+108h]
  int v359; // [rsp+20Ch] [rbp+10Ch]
  int v360; // [rsp+210h] [rbp+110h]
  int v361; // [rsp+214h] [rbp+114h]
  int v362; // [rsp+218h] [rbp+118h]
  int v363; // [rsp+21Ch] [rbp+11Ch]
  int v364; // [rsp+220h] [rbp+120h]
  int v365; // [rsp+224h] [rbp+124h]
  int v366; // [rsp+228h] [rbp+128h]
  int v367; // [rsp+22Ch] [rbp+12Ch]
  int v368; // [rsp+230h] [rbp+130h]
  int v369; // [rsp+234h] [rbp+134h]
  int v370; // [rsp+238h] [rbp+138h]
  int v371; // [rsp+23Ch] [rbp+13Ch]
  int v372; // [rsp+240h] [rbp+140h]
  int v373; // [rsp+244h] [rbp+144h]
  int v374; // [rsp+248h] [rbp+148h]
  int v375; // [rsp+24Ch] [rbp+14Ch]
  int v376; // [rsp+250h] [rbp+150h]
  int v377; // [rsp+254h] [rbp+154h]
  int v378; // [rsp+258h] [rbp+158h]
  int v379; // [rsp+25Ch] [rbp+15Ch]
  int v380; // [rsp+260h] [rbp+160h]
  int v381; // [rsp+264h] [rbp+164h]
  __int64 v382; // [rsp+268h] [rbp+168h]
  __int64 v383; // [rsp+270h] [rbp+170h]
  int v384; // [rsp+280h] [rbp+180h] BYREF
  __int64 v385; // [rsp+288h] [rbp+188h]
  int v386; // [rsp+290h] [rbp+190h]
  __int64 v387; // [rsp+298h] [rbp+198h]
  int v388; // [rsp+2A0h] [rbp+1A0h]
  __int64 v389; // [rsp+2A8h] [rbp+1A8h]
  int v390; // [rsp+2B0h] [rbp+1B0h]
  __int64 v391; // [rsp+2B8h] [rbp+1B8h]
  int v392; // [rsp+2C0h] [rbp+1C0h]
  __int64 v393; // [rsp+2C8h] [rbp+1C8h]
  int v394; // [rsp+2D0h] [rbp+1D0h]
  int *v395; // [rsp+2D8h] [rbp+1D8h]
  int v396; // [rsp+2E0h] [rbp+1E0h]
  __int64 v397; // [rsp+2E8h] [rbp+1E8h]
  int v398; // [rsp+2F0h] [rbp+1F0h]
  __int64 v399; // [rsp+2F8h] [rbp+1F8h]
  int v400; // [rsp+300h] [rbp+200h] BYREF
  __int64 v401; // [rsp+308h] [rbp+208h]
  int v402; // [rsp+310h] [rbp+210h]
  __int64 v403; // [rsp+318h] [rbp+218h]
  int v404; // [rsp+320h] [rbp+220h]
  __int64 v405; // [rsp+328h] [rbp+228h]
  int v406; // [rsp+330h] [rbp+230h]
  int *v407; // [rsp+338h] [rbp+238h]
  int v408; // [rsp+340h] [rbp+240h]
  __int64 v409; // [rsp+348h] [rbp+248h]
  int v410; // [rsp+350h] [rbp+250h]
  __int64 v411; // [rsp+358h] [rbp+258h]
  int v412; // [rsp+360h] [rbp+260h]
  __int64 v413; // [rsp+368h] [rbp+268h]
  int v414; // [rsp+370h] [rbp+270h]
  __int64 v415; // [rsp+378h] [rbp+278h]
  int v416; // [rsp+380h] [rbp+280h]
  __int64 v417; // [rsp+388h] [rbp+288h]
  int v418; // [rsp+390h] [rbp+290h]
  int *v419; // [rsp+398h] [rbp+298h]
  int v420; // [rsp+3A0h] [rbp+2A0h]
  __int64 v421; // [rsp+3A8h] [rbp+2A8h]
  int v422; // [rsp+3B0h] [rbp+2B0h]
  int *v423; // [rsp+3B8h] [rbp+2B8h]
  int v424; // [rsp+3C0h] [rbp+2C0h]
  __int64 v425; // [rsp+3C8h] [rbp+2C8h]
  int v426; // [rsp+3D0h] [rbp+2D0h]
  __int64 v427; // [rsp+3D8h] [rbp+2D8h]
  int v428; // [rsp+3E0h] [rbp+2E0h]
  __int64 v429; // [rsp+3E8h] [rbp+2E8h]
  int v430; // [rsp+3F0h] [rbp+2F0h]
  __int64 v431; // [rsp+3F8h] [rbp+2F8h]
  int v432; // [rsp+400h] [rbp+300h]
  __int64 v433; // [rsp+408h] [rbp+308h]
  int v434; // [rsp+410h] [rbp+310h]
  int *v435; // [rsp+418h] [rbp+318h]
  unsigned __int16 v436[14]; // [rsp+420h] [rbp+320h] BYREF
  int v437; // [rsp+43Ch] [rbp+33Ch]
  _BYTE v438[80]; // [rsp+470h] [rbp+370h] BYREF

  v383 = a2;
  v2 = a1;
  v274 = a1;
  v3 = *(_QWORD *)(W32GetSessionState(a1) + 96);
  v273 = *(_DWORD *)(v3 + 20348);
  v272[0] = 96;
  v7 = *(_DWORD *)(W32GetUserSessionState(v4, v3, v5, v6) + 66784) & 0x100000;
  v283 = -1;
  v279 = v7;
  v282 = 0;
  v269 = 0;
  v277 = 0;
  v287 = 4135;
  v286 = 4;
  v288 = 112;
  v11 = *(_DWORD *)(W32GetUserSessionState(v7, v8, v9, v10) + 66784);
  v280 = 0;
  v276 = 1;
  v278 = v11 & 0x10000;
  v289 = 4;
  v290 = 17;
  v291 = 100;
  v292 = 4;
  v293 = 77;
  v294 = 199;
  v295 = 4;
  v296 = 4;
  v297 = 76;
  v298 = 198;
  v299 = 4;
  v300 = 4;
  v301 = 105;
  v302 = 14;
  v303 = 3;
  v304 = 4;
  v305 = 109;
  v306 = 15;
  v307 = 3;
  v308 = 4;
  v309 = 131;
  v310 = 18;
  v311 = 1;
  v312 = 4;
  v313 = 141;
  v314 = 624;
  v315 = 1;
  v316 = 4;
  v317 = 145;
  v318 = 625;
  v319 = 1;
  v320 = 4;
  v321 = 143;
  v322 = 626;
  v323 = 1;
  v324 = 4;
  v325 = 159;
  v326 = 628;
  v327 = 13;
  v328 = 23;
  v329 = 106;
  v330 = 13;
  v331 = 11;
  v332 = 13;
  v333 = 15;
  v362 = 17;
  v347 = 96;
  v343 = 30;
  v363 = 30;
  v371 = 30;
  v351 = 96;
  v375 = 50;
  v379 = 50;
  v334 = 12;
  v335 = 32;
  v336 = 6;
  v337 = 500;
  v338 = 12;
  v339 = 29;
  v340 = 97;
  v341 = 4;
  v342 = 12;
  v344 = 98;
  v345 = 4;
  v346 = 12;
  v348 = 7;
  v349 = 3;
  v350 = 28;
  v352 = 35;
  v353 = 111;
  v354 = 236;
  v355 = 1;
  v356 = 12;
  v357 = 127;
  v358 = 16;
  v359 = 1;
  v360 = 12;
  v361 = 129;
  v364 = 12;
  v365 = 133;
  v366 = 19;
  v367 = 20;
  v368 = 12;
  v369 = 135;
  v370 = 20;
  v372 = 12;
  v373 = 137;
  v374 = 21;
  v376 = 12;
  v377 = 139;
  v378 = 22;
  v380 = 4;
  v381 = 169;
  v382 = 205;
  v400 = 4;
  v401 = 94;
  v402 = 400;
  UserSessionState = W32GetUserSessionState(20, 1, 4, 12);
  v405 = 107;
  v404 = 4;
  v403 = UserSessionState + 65800;
  v407 = &v279;
  v406 = 2;
  v408 = 4;
  v409 = 159;
  v410 = 3;
  v17 = *(_QWORD *)(W32GetUserSessionState(v14, v13, v15, v16) + 19704) + 4996LL;
  v412 = 4;
  v411 = v17;
  v413 = 160;
  v414 = 3;
  v415 = *(_QWORD *)(W32GetUserSessionState(v17, v18, v19, v20) + 19704) + 5000LL;
  v419 = &v273;
  v423 = &v277;
  v416 = 4;
  v417 = 200;
  v418 = 0;
  v420 = 4;
  v421 = 618;
  v422 = 0;
  v424 = 4;
  v425 = 621;
  v426 = 5000;
  v24 = W32GetUserSessionState(v415, v21, v22, v23);
  v428 = 4;
  v427 = v24 + 69104;
  v429 = 622;
  v430 = 5000;
  v29 = W32GetUserSessionState(v26, v25, v27, v28);
  v432 = 23;
  v433 = 149;
  v431 = v29 + 36248;
  v30 = 1;
  v434 = 1;
  v435 = &v278;
  v384 = 12;
  v385 = 10;
  v386 = 6;
  v35 = W32GetUserSessionState(v32, v31, v33, v34);
  v388 = 12;
  v389 = 11;
  v387 = v35 + 16232;
  v390 = 10;
  v40 = W32GetUserSessionState(v37, v36, v38, v39);
  v392 = 12;
  v391 = v40 + 16236;
  v395 = &v276;
  v393 = 12;
  v394 = 1;
  v396 = 35;
  v397 = 237;
  v398 = 0;
  v45 = v2 & 4;
  v399 = W32GetUserSessionState(v42, v41, v43, v44) + 14652;
  v50 = v2 & 2;
  v272[1] = v45;
  v51 = v2 & 1;
  if ( (v2 & 0x10) != 0 )
  {
    v52 = *(HANDLE *)(W32GetUserSessionState(v47, v46, v48, v49) + 63312);
    if ( PsGetCurrentProcessId() != v52 )
    {
LABEL_3:
      v57 = 5;
LABEL_32:
      UserSetLastError(v57);
      goto LABEL_33;
    }
    if ( v50 || v51 || v45 )
    {
      v57 = 87;
      goto LABEL_32;
    }
    if ( *(_DWORD *)(W32GetUserSessionState(v54, v53, v55, v56) + 308) )
    {
      v61 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
      {
        v30 = 0;
      }
      v62 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v30 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        CurrentWin32kSessionId = W32GetCurrentWin32kSessionId();
        v68 = W32GetUserSessionState(v65, v64, v66, v67);
        LOBYTE(v69) = v62;
        LOBYTE(v70) = v30;
        WPP_RECORDER_AND_TRACE_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v70,
          v69,
          *(_QWORD *)(v68 + 69152),
          4,
          20,
          11,
          (__int64)WPP_6f3f2e22ce9e317051f30d9635f1d0e7_Traceguids,
          CurrentWin32kSessionId);
      }
      *(_DWORD *)(W32GetUserSessionState(v61, v58, v59, v60) + 308) = 0;
      AttachInputDevices(1);
      v75 = W32GetUserSessionState(v72, v71, v73, v74);
      CHidInput::HandleDirectStartStopDeviceReadRequest(*(CHidInput **)(v75 + 16792));
    }
  }
  else
  {
    if ( (v2 & 2) == 0 )
    {
      v76 = *(HANDLE *)(W32GetUserSessionState(v47, v46, v48, v49) + 63312);
      if ( PsGetCurrentProcessId() != v76 )
        goto LABEL_3;
    }
    v79 = (struct _UNICODE_STRING *)CreateProfileUserName(&v282);
    if ( !v79 )
    {
LABEL_33:
      if ( v283 != -1 )
        PopAndFreeAlwaysW32ThreadLock(&v282);
      return 0;
    }
    v82 = 0;
    v271 = 0;
    if ( *(_QWORD *)(W32GetUserSessionState(v78, v77, v80, v81) + 63288) )
    {
      v87 = *(_QWORD *)(W32GetUserSessionState(v84, v83, v85, v86) + 63288);
      v88 = *(void **)(v87 + 176);
      if ( v88 )
        Win32FreePool(v88);
      v89 = Win32AllocPoolZInit(v79->Length, 1852863317);
      *(_QWORD *)(v87 + 176) = v89;
      if ( v89 )
      {
        *(_WORD *)(v87 + 170) = v79->Length;
        *(_WORD *)(v87 + 168) = 0;
        RtlCopyUnicodeString((PUNICODE_STRING)(v87 + 168), v79);
      }
      if ( v51 )
        WakeRIT(64);
    }
    if ( v50 && !v45 )
    {
      v271 = CheckEasPolicyChange();
      if ( !(unsigned int)CheckDesktopPolicyChange(v79) && !v271 )
      {
        v57 = 0;
        goto LABEL_32;
      }
      v82 = 16;
    }
    if ( v51 )
    {
      v91 = W32GetUserSessionState(v84, v83, v85, v86);
      *(_DWORD *)(v91 + 62552) |= 2u;
    }
    v269 = 300;
    v92 = v82 | 8;
    if ( !v45 )
      v92 = v82;
    v93 = W32GetUserSessionState(v84, v83, v85, v86);
    FastGetProfileValue(v79, 4, 607, &v269, v93 + 63968, 4, v92);
    if ( *(int *)(W32GetUserSessionState(v95, v94, v96, v97) + 63968) > 0 )
    {
      v107 = 1000;
      if ( *(int *)(W32GetUserSessionState(v99, v98, v100, v101) + 63968) < 1000 )
        v107 = *(_DWORD *)(W32GetUserSessionState(v109, v108, v110, v111) + 63968);
      v102 = W32GetUserSessionState(v109, v108, v110, v111);
    }
    else
    {
      v102 = W32GetUserSessionState(v99, v98, v100, v101);
      v107 = 1000;
    }
    *(_DWORD *)(v102 + 63968) = v107;
    v112 = W32GetUserSessionState(v104, v103, v105, v106);
    v117 = v112;
    if ( v51 )
    {
      if ( !*(_DWORD *)(v112 + 66048) && !(unsigned int)UserRemoteConnectedSessionUsingWddm() )
      {
        FastGetProfileDwordEx(v79, 4, L"LogPixels", 0, v92, v272, 0);
        v275 = 0;
        v118 = DrvInitializeDxgkrnlDpiCache(&v275);
        v120 = PerformLegacyDpiUpgrade(v79, v272[0]);
        if ( v118 < 0
          || v275
          || (v121 = Gre::Base::Globals(v119),
              v114 = *((unsigned __int16 *)v121 + 584),
              *((_WORD *)v121 + 585) != (_WORD)v114)
          || v120
          || v272[0] )
        {
          GreReinitializeDpiSetting();
          v270[0] = 0;
          LOBYTE(v268) = 0;
          if ( (int)xxxUserSetDisplayConfig(0, 0, 2191, 516, 0, v268, 0, 0, v270, v383, 0) >= 0 )
          {
            if ( v270[0] )
              xxxUserResetDisplayDevice();
            v122 = W32GetUserSessionState(v114, v113, v115, v116);
            UserReinitializeStockFonts(*(unsigned __int16 *)(*(_QWORD *)(v122 + 19704) + 6998LL), 1);
            *(_DWORD *)(v117 + 66048) = 1;
          }
        }
      }
    }
    v123 = W32GetUserSessionState(v114, v113, v115, v116);
    CInputGlobals::UpdateWakeOnInputDeviceTypesFromRegistry(*(CInputGlobals **)(v123 + 3008));
    LoadCPUserPreferences(v79, v92);
    if ( !v50 )
    {
      xxxODI_ColorInit(v79);
      LW_LoadResources(v79);
      if ( (unsigned int)GreTextInitialized() )
        xxxSetWindowNCMetrics(v79);
      SetMinMetrics(v79);
      SetIconMetrics(v79);
      GetKbdLangSwitch(v79);
      ZwSetDefaultLocale(1u, 0);
      ZwSetDefaultUILanguage(0);
      v128 = W32GetUserSessionState(v125, v124, v126, v127);
      ZwQueryDefaultUILanguage((LANGID *)(*(_QWORD *)(v128 + 19704) + 7012LL));
      xxxLoadSomeStrings();
      if ( *(_QWORD *)(W32GetUserSessionState(v130, v129, v131, v132) + 63288) )
      {
        SmartObjStackRef<tagMENU>::SmartObjStackRef<tagMENU>(v284);
        for ( i = *(_QWORD **)(*(_QWORD *)(W32GetUserSessionState(v138, v137, v139, v140) + 63288) + 16LL);
              i;
              i = (_QWORD *)i[4] )
        {
          v142 = i[7];
          if ( v142 )
          {
            v285 = 0;
            SmartObjStackRefBase<tagMENU>::operator=(v284, v142);
            if ( UnlockDesktopSysMenu(i + 7) )
            {
              v143 = v285;
              if ( !v285 )
                v143 = *(struct _HEAD **)v284[0];
              DestroyMenu(v143);
            }
          }
          v144 = i[8];
          if ( v144 )
          {
            v285 = 0;
            SmartObjStackRefBase<tagMENU>::operator=(v284, v144);
            if ( UnlockDesktopSysMenu(i + 8) )
            {
              v145 = v285;
              if ( !v285 )
                v145 = *(struct _HEAD **)v284[0];
              DestroyMenu(v145);
            }
          }
        }
        SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(v284);
      }
      v146 = W32GetUserSessionState(v134, v133, v135, v136);
      CCursorSizes::zzzRefreshSizes(*(CCursorSizes **)(v146 + 36176));
      xxxUpdateSystemCursorsFromRegistry(v79, 1);
      xxxUpdateSystemIconsFromRegistry(v79);
      for ( j = 0; j < 0xF; ++j )
      {
        v268 = 0;
        v266 = &v269;
        if ( (unsigned int)FastGetProfileIntFromID(
                             v79,
                             (unsigned int)*(&v327 + 4 * (int)j),
                             *((unsigned int *)&v329 + 4 * (int)j)) )
          xxxSystemParametersInfo((unsigned int)*(&v328 + 4 * (int)j), v269, 0, 0x8000, &v269, 0);
      }
      FastGetProfileIntsW(v79, &v384, 4);
      LOBYTE(v148) = v276 != 0;
      EnableMouseAcceleration(v148);
    }
    xxxSystemParametersInfo(21, 0xFFFFFFFFLL, 0, 0, v266, v268);
    if ( v51 )
    {
      W32GetUserSessionState(v150, v149, v151, v152);
      FastGetProfileIntFromID(v79, 35, 236);
    }
    for ( k = 0; k < 0xB; ++k )
    {
      if ( (unsigned int)FastGetProfileIntFromID(
                           v79,
                           (unsigned int)*(&v286 + 4 * (int)k),
                           *((unsigned int *)&v288 + 4 * (int)k)) )
        xxxSystemParametersInfo((unsigned int)*(&v287 + 4 * (int)k), v269, 0, 0x8000, &v269, v92);
    }
    v154 = v92;
    if ( v271 )
      v154 = 2;
    CalcScreenSaverTimeout(v79, v154);
    FastGetProfileIntsW(v79, &v400, 9);
    if ( v277 )
    {
      v160 = *(volatile signed __int32 **)(W32GetUserSessionState(v156, v155, v157, v158) + 19704);
      _InterlockedOr(v160, 0x200u);
    }
    else
    {
      v160 = *(volatile signed __int32 **)(W32GetUserSessionState(v156, v155, v157, v158) + 19704);
      _InterlockedAnd(v160, 0xFFFFFDFF);
    }
    if ( v278 )
    {
      v163 = W32GetUserSessionState(v160, v159, v161, v162);
      *(_DWORD *)(v163 + 66784) |= 0x10000u;
    }
    else
    {
      v168 = W32GetUserSessionState(v160, v159, v161, v162);
      *(_DWORD *)(v168 + 66784) &= ~0x10000u;
    }
    if ( v279 == 2 )
    {
      v169 = W32GetUserSessionState(v165, v164, v166, v167);
      if ( (unsigned int)GreGetDeviceCaps(*(_QWORD *)(*(_QWORD *)(v169 + 56744) + 56LL), 119) )
      {
        v179 = W32GetUserSessionState(v171, v170, v172, v173);
        *(_DWORD *)(v179 + 66784) &= ~0x100000u;
      }
      else
      {
        v174 = W32GetUserSessionState(v171, v170, v172, v173);
        *(_DWORD *)(v174 + 66784) |= 0x100000u;
      }
      if ( v51 )
      {
        v180 = W32GetUserSessionState(v176, v175, v177, v178);
        RtlStringCchPrintfW(v436, 0x28u, L"%d", (*(_DWORD *)(v180 + 66784) >> 20) & 1);
        RtlLoadStringOrError(107, v438, 40);
        FastWriteProfileStringW(v79, 4, v438, v436);
      }
    }
    else if ( v279 )
    {
      v181 = W32GetUserSessionState(v165, v164, v166, v167);
      *(_DWORD *)(v181 + 66784) |= 0x100000u;
    }
    else
    {
      v182 = W32GetUserSessionState(v165, v164, v166, v167);
      *(_DWORD *)(v182 + 66784) &= ~0x100000u;
    }
    v269 = *(_DWORD *)(*(_QWORD *)(W32GetUserSessionState(v176, v175, v177, v178) + 19704) + 4984LL);
    if ( (unsigned int)FastGetProfileIntFromID(v79, 4, 4) )
      SetCaretBlinkTime(v269);
    if ( !v50 )
    {
      v271 = 0;
      FastGetProfileIntFromID(v79, 12, 608);
      UpdateMouseSensitivity(v271);
      for ( m = 0; m < 2; ++m )
      {
        ReadDefaultAccelerationCurves(m, v79);
        ResetAccelerationCurves(m);
      }
      FastGetProfileIntFromID(v79, 12, 613);
      SetMouseTrails(v269);
      FastGetProfileIntW(v79, 7, L"TTOnly");
      GreSetFontEnumeration(v269);
      W32GetUserSessionState(v185, v184, v186, v187);
      W32GetUserSessionState(v189, v188, v190, v191);
      FastGetProfileIntFromID(v79, 12, 91);
      W32GetUserSessionState(v193, v192, v194, v195);
      W32GetUserSessionState(v197, v196, v198, v199);
      FastGetProfileIntFromID(v79, 12, 92);
      W32GetUserSessionState(v201, v200, v202, v203);
      W32GetUserSessionState(v205, v204, v206, v207);
      FastGetProfileIntFromID(v79, 12, 93);
      if ( *(_DWORD *)(W32GetUserSessionState(v209, v208, v210, v211) + 16228) < 0xAu )
        *(_DWORD *)(W32GetUserSessionState(v213, v212, v214, v215) + 16228) = 10;
      if ( *(_DWORD *)(W32GetUserSessionState(v213, v212, v214, v215) + 16228) > 0x7FFFFFFFu )
        *(_DWORD *)(W32GetUserSessionState(v217, v216, v218, v219) + 16228) = 0x7FFFFFFF;
      ReadRawMouseThrottlingThresholds(v79);
      UpdatePerUserKeyboardIndicators(v79);
      InitScancodeMap(v221, v220);
      W32GetUserSessionState(v223, v222, v224, v225);
      FastGetProfileDword(v79, 24, L"Attributes");
      v230 = (*(_DWORD *)(W32GetUserSessionState(v227, v226, v228, v229) + 14128) >> 15) & 2;
      *(_DWORD *)(W32GetUserSessionState(v232, v231, v233, v234) + 14128) = v230;
      xxxUpdatePerUserAccessPackSettings(v79);
    }
    v237 = (void *)OpenCacheKeyEx(0, 22, 131097);
    if ( v237 )
    {
      *(_DWORD *)(*(_QWORD *)(W32GetUserSessionState(v236, v235, v238, v239) + 19704) + 2148LL) = 1;
      ZwClose(v237);
    }
    v240 = W32GetUserSessionState(v236, v235, v238, v239);
    *(_DWORD *)(*(_QWORD *)(v240 + 19704) + 2148LL) |= 2u;
    GreSetFontEnumeration(4);
    GreSetFontEnumeration(32);
    if ( (v273 & 2) != 0 )
      GreSetFontEnumeration(v273 | 4u);
    if ( (*(_DWORD *)UPDWORDPointer(8202) & 2) != 0 )
      GreSetFontEnumeration(v273 | 0x30u);
    v242 = *(_DWORD *)UPDWORDPointer(8204);
    if ( !v242 )
      v242 = 1200;
    *(_DWORD *)(*(_QWORD *)(W32GetSessionState(v241) + 96) + 13448LL) = v242;
    v243 = (unsigned int *)UPDWORDPointer(8210);
    GreSetLCDOrientation(*v243);
    v248 = *(_DWORD *)(W32GetUserSessionState(v245, v244, v246, v247) + 66792) & 0x400;
    *(_DWORD *)(*(_QWORD *)(W32GetSessionState(v249) + 96) + 24304LL) = v248;
    if ( v274 == 2 )
      xxxUserResetDisplayDevice();
    v267 = &v280;
    FastGetProfileDword(0, 49, L"RestrictDebuggerForeground");
    if ( v280 )
      *(_DWORD *)(W32GetUserSessionState(v251, v250, v252, v253) + 18940) = 1;
    if ( v51 )
    {
      memset_0(v436, 0, 0x44u);
      if ( (unsigned int)ReadPointerDeviceSettings(146, v436) )
      {
        if ( !v437 )
          SetTouchInputStatus(0);
      }
    }
    if ( *(_DWORD *)(W32GetUserSessionState(v251, v250, v252, v253) + 62704) == 1 )
    {
      v274 = 0;
      *(_DWORD *)(W32GetUserSessionState(v255, v254, v256, v257) + 62704) = 0;
      UserLogError(3221226518LL);
      UserSessionSwitchLeaveCrit(v259, v258, v260);
      LODWORD(v267) = 7;
      ExRaiseHardError(3221226518LL, 0, 0, 0, v267, &v274);
      EnterCrit(1, 0);
    }
    xxxDwmControl(1037, 0);
    LOBYTE(v261) = *(_DWORD *)UPDWORDPointer(8244) != 0;
    SendCrosshairEnabledStatusChanged(v261);
    v281 = 0;
    if ( (unsigned int)ReadPointerDeviceSettings(178, &v281) )
      SendCrosshairPropertiesChanged(v281);
    ReadInputHapticSettings();
    if ( v51 )
    {
      TraceLoggingAutoRotationStateEvent();
      _InterlockedOr(*(volatile signed __int32 **)(W32GetUserSessionState(v263, v262, v264, v265) + 19704), 0x400u);
    }
  }
  if ( v283 != -1 )
    PopAndFreeAlwaysW32ThreadLock(&v282);
  return 1;
}

```

## disassembly

```asm
0x14023f1a0  mov     [rsp-8+arg_10], rbx
0x14023f1a5  push    rbp
0x14023f1a6  push    rsi
0x14023f1a7  push    rdi
0x14023f1a8  push    r12
0x14023f1aa  push    r13
0x14023f1ac  push    r14
0x14023f1ae  push    r15
0x14023f1b0  lea     rbp, [rsp-3D0h]
0x14023f1b8  sub     rsp, 4D0h
0x14023f1bf  mov     rax, cs:__security_cookie
0x14023f1c6  xor     rax, rsp
0x14023f1c9  mov     [rbp+400h+var_40], rax
0x14023f1d0  mov     [rbp+400h+var_290], rdx
0x14023f1d7  mov     ebx, ecx
0x14023f1d9  mov     [rsp+500h+var_488], ecx
0x14023f1dd  call    cs:__imp_W32GetSessionState
0x14023f1e4  nop     dword ptr [rax+rax+00h]
0x14023f1e9  mov     esi, 60h ; '`'
0x14023f1ee  mov     rdx, [rax+60h]
0x14023f1f2  mov     eax, [rdx+4F7Ch]
0x14023f1f8  mov     [rsp+500h+var_48C], eax
0x14023f1fc  mov     [rsp+500h+var_494], esi
0x14023f200  call    cs:__imp_W32GetUserSessionState
0x14023f207  nop     dword ptr [rax+rax+00h]
0x14023f20c  xorps   xmm0, xmm0
0x14023f20f  xor     r13d, r13d
0x14023f212  mov     ecx, [rax+104E0h]
0x14023f218  and     ecx, 100000h
0x14023f21e  mov     [rbp+400h+var_458], 0FFFFFFFFFFFFFFFFh
0x14023f226  mov     [rbp+400h+var_474], ecx
0x14023f229  movups  [rbp+400h+var_468], xmm0
0x14023f22d  mov     [rsp+500h+var_4A0], r13d
0x14023f232  mov     [rbp+400h+var_47C], r13d
0x14023f236  call    cs:__imp_W32GetUserSessionState
0x14023f23d  nop     dword ptr [rax+rax+00h]
0x14023f242  lea     r8d, [rsi-5Ch]
0x14023f246  mov     [rbp+400h+var_42C], 1027h
0x14023f24d  lea     edx, [rsi-5Fh]
0x14023f250  mov     [rbp+400h+var_430], r8d
0x14023f254  lea     r15d, [rsi-5Dh]
0x14023f258  mov     [rbp+400h+var_428], 70h ; 'p'
0x14023f260  mov     ecx, [rax+104E0h]
0x14023f266  lea     r9d, [rsi-51h]
0x14023f26a  lea     eax, [rsi-53h]
0x14023f26d  mov     [rbp+400h+var_470], r13d
0x14023f271  and     ecx, 10000h
0x14023f277  mov     [rbp+400h+var_480], edx
0x14023f27a  mov     [rbp+400h+var_478], ecx
0x14023f27d  lea     edi, [rsi+3Fh]
0x14023f280  lea     ecx, [rsi-4Fh]
0x14023f283  mov     [rbp+400h+var_420], r8d
0x14023f287  lea     r12d, [rsi-49h]
0x14023f28b  mov     [rbp+400h+var_41C], ecx
0x14023f28e  mov     [rbp+400h+var_418], 64h ; 'd'
0x14023f296  mov     [rbp+400h+var_410], r8d
0x14023f29a  mov     [rbp+400h+var_40C], 4Dh ; 'M'
0x14023f2a1  mov     [rbp+400h+var_408], 0C7h
0x14023f2a8  mov     [rbp+400h+var_404], r8d
0x14023f2ac  mov     [rbp+400h+var_400], r8d
0x14023f2b0  mov     [rbp+400h+var_3FC], 4Ch ; 'L'
0x14023f2b7  mov     [rbp+400h+var_3F8], 0C6h
0x14023f2be  mov     [rbp+400h+var_3F4], r8d
0x14023f2c2  mov     [rbp+400h+var_3F0], r8d
0x14023f2c6  mov     [rbp+400h+var_3EC], 69h ; 'i'
0x14023f2cd  mov     [rbp+400h+var_3E8], 0Eh
0x14023f2d4  mov     [rbp+400h+var_3E4], r15d
0x14023f2d8  mov     [rbp+400h+var_3E0], r8d
0x14023f2dc  mov     [rbp+400h+var_3DC], 6Dh ; 'm'
0x14023f2e3  mov     [rbp+400h+var_3D8], r9d
0x14023f2e7  mov     [rbp+400h+var_3D4], r15d
0x14023f2eb  mov     [rbp+400h+var_3D0], r8d
0x14023f2ef  mov     [rbp+400h+var_3CC], 83h
0x14023f2f6  mov     [rbp+400h+var_3C8], 12h
0x14023f2fd  mov     [rbp+400h+var_3C4], edx
0x14023f300  mov     [rbp+400h+var_3C0], r8d
0x14023f304  mov     [rbp+400h+var_3BC], 8Dh
0x14023f30b  mov     [rbp+400h+var_3B8], 270h
0x14023f312  mov     [rbp+400h+var_3B4], edx
0x14023f315  mov     [rbp+400h+var_3B0], r8d
0x14023f319  mov     [rbp+400h+var_3AC], 91h
0x14023f320  mov     [rbp+400h+var_3A8], 271h
0x14023f327  mov     [rbp+400h+var_3A4], edx
0x14023f32a  mov     [rbp+400h+var_3A0], r8d
0x14023f32e  mov     [rbp+400h+var_39C], 8Fh
0x14023f335  mov     [rbp+400h+var_398], 272h
0x14023f33c  mov     [rbp+400h+var_394], edx
0x14023f33f  mov     [rbp+400h+var_390], r8d
0x14023f343  mov     [rbp+400h+var_38C], edi
0x14023f346  mov     [rbp+400h+var_388], 274h
0x14023f34e  mov     [rbp+400h+var_380], eax
0x14023f354  mov     [rbp+400h+var_37C], r12d
0x14023f35b  mov     [rbp+400h+var_378], 6Ah ; 'j'
0x14023f366  mov     [rbp+400h+var_370], eax
0x14023f36c  mov     [rbp+400h+var_36C], 0Bh
0x14023f376  mov     [rbp+400h+var_368], eax
0x14023f37c  mov     [rbp+400h+var_364], r9d
0x14023f383  lea     r9d, [rsi-54h]
0x14023f387  mov     [rbp+400h+var_2E8], ecx
0x14023f38d  lea     eax, [rsi-42h]
0x14023f390  mov     [rbp+400h+var_32C], esi
0x14023f396  lea     ecx, [rdx+13h]
0x14023f399  mov     [rbp+400h+var_33C], eax
0x14023f39f  mov     [rbp+400h+var_2E4], eax
0x14023f3a5  lea     r14d, [rsi-5Ah]
0x14023f3a9  mov     [rbp+400h+var_2C4], eax
0x14023f3af  lea     eax, [rdx+31h]
0x14023f3b2  mov     [rbp+400h+var_318], rsi
0x14023f3b9  xor     esi, esi
0x14023f3bb  mov     [rbp+400h+var_2B4], eax
0x14023f3c1  mov     [rbp+400h+var_2A4], eax
0x14023f3c7  mov     [rbp+400h+var_360], r9d
0x14023f3ce  mov     [rbp+400h+var_35C], 20h ; ' '
0x14023f3d8  mov     [rbp+400h+var_358], r14d
0x14023f3df  mov     [rbp+400h+var_354], 1F4h
0x14023f3e9  mov     [rbp+400h+var_350], r9d
0x14023f3f0  mov     [rbp+400h+var_34C], 1Dh
0x14023f3fa  mov     [rbp+400h+var_348], 61h ; 'a'
0x14023f404  mov     [rbp+400h+var_344], r8d
0x14023f40b  mov     [rbp+400h+var_340], r9d
0x14023f412  mov     [rbp+400h+var_338], 62h ; 'b'
0x14023f41c  mov     [rbp+400h+var_334], r8d
0x14023f423  mov     [rbp+400h+var_330], r9d
0x14023f42a  mov     [rbp+400h+var_328], 7
0x14023f435  mov     [rbp+400h+var_320], r15d
0x14023f43c  mov     [rbp+400h+var_31C], 1Ch
0x14023f446  mov     [rbp+400h+var_310], 23h ; '#'
0x14023f450  mov     [rbp+400h+var_30C], 6Fh ; 'o'
0x14023f45a  mov     [rbp+400h+var_308], 0ECh
0x14023f464  mov     [rbp+400h+var_304], edx
0x14023f46a  mov     [rbp+400h+var_300], r9d
0x14023f471  mov     [rbp+400h+var_2FC], 7Fh
0x14023f47b  mov     [rbp+400h+var_2F8], 10h
0x14023f485  mov     [rbp+400h+var_2F4], edx
0x14023f48b  mov     [rbp+400h+var_2F0], r9d
0x14023f492  mov     [rbp+400h+var_2EC], 81h
0x14023f49c  mov     [rbp+400h+var_2E0], r9d
0x14023f4a3  mov     [rbp+400h+var_2DC], 85h
0x14023f4ad  mov     [rbp+400h+var_2D8], 13h
0x14023f4b7  mov     [rbp+400h+var_2D4], ecx
0x14023f4bd  mov     [rbp+400h+var_2D0], r9d
0x14023f4c4  mov     [rbp+400h+var_2CC], 87h
0x14023f4ce  mov     [rbp+400h+var_2C8], ecx
0x14023f4d4  mov     [rbp+400h+var_2C0], r9d
0x14023f4db  mov     [rbp+400h+var_2BC], 89h
0x14023f4e5  mov     [rbp+400h+var_2B8], 15h
0x14023f4ef  mov     [rbp+400h+var_2B0], r9d
0x14023f4f6  mov     [rbp+400h+var_2AC], 8Bh
0x14023f500  mov     [rbp+400h+var_2A8], 16h
0x14023f50a  mov     [rbp+400h+var_2A0], r8d
0x14023f511  mov     [rbp+400h+var_29C], 0A9h
0x14023f51b  mov     [rbp+400h+var_298], 0CDh
0x14023f526  mov     [rbp+400h+var_200], r8d
0x14023f52d  mov     [rbp+400h+var_1F8], 5Eh ; '^'
0x14023f538  mov     [rbp+400h+var_1F0], 190h
0x14023f542  call    cs:__imp_W32GetUserSessionState
0x14023f549  nop     dword ptr [rax+rax+00h]
0x14023f54e  lea     r13d, [r15+1]
0x14023f552  mov     [rbp+400h+var_1D8], 6Bh ; 'k'
0x14023f55d  add     rax, 10108h
0x14023f563  mov     [rbp+400h+var_1E0], r13d
0x14023f56a  mov     [rbp+400h+var_1E8], rax
0x14023f571  lea     rax, [rbp+400h+var_474]
0x14023f575  mov     [rbp+400h+var_1C8], rax
0x14023f57c  mov     [rbp+400h+var_1D0], 2
0x14023f586  mov     [rbp+400h+var_1C0], r13d
0x14023f58d  mov     [rbp+400h+var_1B8], rdi
0x14023f594  mov     [rbp+400h+var_1B0], r15d
0x14023f59b  call    cs:__imp_W32GetUserSessionState
0x14023f5a2  nop     dword ptr [rax+rax+00h]
0x14023f5a7  mov     rcx, [rax+4CF8h]
0x14023f5ae  add     rcx, 1384h
0x14023f5b5  mov     [rbp+400h+var_1A0], r13d
0x14023f5bc  mov     [rbp+400h+var_1A8], rcx
0x14023f5c3  mov     [rbp+400h+var_198], 0A0h
0x14023f5ce  mov     [rbp+400h+var_190], r15d
0x14023f5d5  call    cs:__imp_W32GetUserSessionState
0x14023f5dc  nop     dword ptr [rax+rax+00h]
0x14023f5e1  mov     edi, 1388h
0x14023f5e6  mov     rcx, [rax+4CF8h]
0x14023f5ed  add     rcx, rdi
0x14023f5f0  lea     rax, [rsp+500h+var_48C]
0x14023f5f5  mov     [rbp+400h+var_188], rcx
0x14023f5fc  mov     [rbp+400h+var_168], rax
0x14023f603  lea     rax, [rbp+400h+var_47C]
0x14023f607  mov     [rbp+400h+var_148], rax
0x14023f60e  mov     [rbp+400h+var_180], r13d
0x14023f615  mov     [rbp+400h+var_178], 0C8h
0x14023f620  mov     [rbp+400h+var_170], esi
0x14023f626  mov     [rbp+400h+var_160], r13d
0x14023f62d  mov     [rbp+400h+var_158], 26Ah
0x14023f638  mov     [rbp+400h+var_150], esi
0x14023f63e  mov     [rbp+400h+var_140], r13d
0x14023f645  mov     [rbp+400h+var_138], 26Dh
0x14023f650  mov     [rbp+400h+var_130], edi
0x14023f656  call    cs:__imp_W32GetUserSessionState
0x14023f65d  nop     dword ptr [rax+rax+00h]
0x14023f662  add     rax, 10DF0h
0x14023f668  mov     [rbp+400h+var_120], r13d
0x14023f66f  mov     [rbp+400h+var_128], rax
0x14023f676  mov     [rbp+400h+var_118], 26Eh
0x14023f681  mov     [rbp+400h+var_110], edi
0x14023f687  call    cs:__imp_W32GetUserSessionState
0x14023f68e  nop     dword ptr [rax+rax+00h]
0x14023f693  mov     [rbp+400h+var_100], r12d
0x14023f69a  lea     r15d, [r12-0Bh]
0x14023f69f  add     rax, 8D98h
0x14023f6a5  mov     [rbp+400h+var_F8], 95h
0x14023f6b0  mov     [rbp+400h+var_108], rax
0x14023f6b7  lea     edi, [rsi+1]
0x14023f6ba  lea     rax, [rbp+400h+var_478]
0x14023f6be  mov     [rbp+400h+var_F0], edi
0x14023f6c4  lea     r12d, [r14+4]
0x14023f6c8  mov     [rbp+400h+var_E8], rax
0x14023f6cf  mov     [rbp+400h+var_280], r15d
0x14023f6d6  mov     [rbp+400h+var_278], r12
0x14023f6dd  mov     [rbp+400h+var_270], r14d
0x14023f6e4  call    cs:__imp_W32GetUserSessionState
0x14023f6eb  nop     dword ptr [rax+rax+00h]
0x14023f6f0  lea     r14d, [rsi+0Bh]
0x14023f6f4  mov     [rbp+400h+var_260], r15d
0x14023f6fb  add     rax, 3F68h
0x14023f701  mov     [rbp+400h+var_258], r14
0x14023f708  mov     [rbp+400h+var_268], rax
0x14023f70f  mov     [rbp+400h+var_250], r12d
0x14023f716  call    cs:__imp_W32GetUserSessionState
0x14023f71d  nop     dword ptr [rax+rax+00h]
0x14023f722  add     rax, 3F6Ch
0x14023f728  mov     [rbp+400h+var_240], r15d
0x14023f72f  mov     [rbp+400h+var_248], rax
0x14023f736  lea     rax, [rbp+400h+var_480]
0x14023f73a  mov     [rbp+400h+var_228], rax
0x14023f741  mov     [rbp+400h+var_238], r15
0x14023f748  mov     [rbp+400h+var_230], edi
0x14023f74e  mov     [rbp+400h+var_220], 23h ; '#'
0x14023f758  mov     [rbp+400h+var_218], 0EDh
0x14023f763  mov     [rbp+400h+var_210], esi
0x14023f769  call    cs:__imp_W32GetUserSessionState
0x14023f770  nop     dword ptr [rax+rax+00h]
0x14023f775  mov     r13d, ebx
0x14023f778  mov     r15d, ebx
0x14023f77b  add     rax, 393Ch
0x14023f781  mov     r12d, ebx
0x14023f784  and     r12d, 4
0x14023f788  mov     [rbp+400h+var_208], rax
0x14023f78f  and     r13d, 2
0x14023f793  mov     [rsp+500h+var_490], r12d
0x14023f798  and     r15d, edi
0x14023f79b  test    bl, 10h
0x14023f79e  jz      loc_14023F8E9
0x14023f7a4  call    cs:__imp_W32GetUserSessionState
0x14023f7ab  nop     dword ptr [rax+rax+00h]
0x14023f7b0  mov     rbx, [rax+0F750h]
0x14023f7b7  call    cs:__imp_PsGetCurrentProcessId
0x14023f7be  nop     dword ptr [rax+rax+00h]
0x14023f7c3  cmp     rax, rbx
0x14023f7c6  jz      short loc_14023F7D2
0x14023f7c8  mov     ecx, 5
0x14023f7cd  jmp     loc_14023FA01
0x14023f7d2  test    r13d, r13d
0x14023f7d5  jnz     loc_14023F8DF
0x14023f7db  test    r15d, r15d
0x14023f7de  jnz     loc_14023F8DF
0x14023f7e4  test    r12d, r12d
0x14023f7e7  jnz     loc_14023F8DF
0x14023f7ed  call    cs:__imp_W32GetUserSessionState
0x14023f7f4  nop     dword ptr [rax+rax+00h]
0x14023f7f9  cmp     [rax+134h], esi
0x14023f7ff  jz      loc_140240704
0x14023f805  mov     rcx, cs:WPP_GLOBAL_Control
0x14023f80c  lea     rax, WPP_GLOBAL_Control
0x14023f813  cmp     rcx, rax
0x14023f816  jz      short loc_14023F827
0x14023f818  test    dword ptr [rcx+2Ch], 80000h
0x14023f81f  jz      short loc_14023F827
0x14023f821  cmp     byte ptr [rcx+29h], 4
0x14023f825  jnb     short loc_14023F82A
0x14023f827  mov     dil, sil
0x14023f82a  lea     rax, WPP_RECORDER_INITIALIZED
0x14023f831  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14023f838  setnz   sil
0x14023f83c  test    dil, dil
0x14023f83f  jnz     short loc_14023F846
0x14023f841  test    sil, sil
0x14023f844  jz      short loc_14023F899
0x14023f846  call    W32GetCurrentWin32kSessionId
0x14023f84b  mov     ebx, eax
0x14023f84d  call    cs:__imp_W32GetUserSessionState
0x14023f854  nop     dword ptr [rax+rax+00h]
0x14023f859  mov     rcx, cs:WPP_GLOBAL_Control
0x14023f860  mov     r8b, sil
0x14023f863  mov     dword ptr [rsp+500h+var_4C0], ebx
0x14023f867  mov     dl, dil
0x14023f86a  mov     r9, [rax+10E20h]
0x14023f871  lea     rax, WPP_6f3f2e22ce9e317051f30d9635f1d0e7_Traceguids
0x14023f878  mov     rcx, [rcx+18h]
0x14023f87c  mov     [rsp+500h+var_4C8], rax
0x14023f881  mov     word ptr [rsp+500h+var_4D0], r14w
0x14023f887  mov     dword ptr [rsp+500h+var_4D8], 14h
0x14023f88f  mov     byte ptr [rsp+500h+var_4E0], 4
  ... truncated ...
```
