# xxxScanSysQueue(tagTHREADINFO *,tagMSG *,tagWND *,uint,uint,ulong,ulong,tagQMSG * *)

- ea: `0x1401ca020`
- end: `0x1401cf05e`
- name: `?xxxScanSysQueue@@YA?AW4_SCANSYSQUEUERESULT@@PEAUtagTHREADINFO@@PEAUtagMSG@@PEAUtagWND@@IIKKPEAPEAUtagQMSG@@@Z`
- size: `20542`
- prototype: ``
- caller_count: `1`
- callee_count: `112`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x140030e20`

## callees

- `0x140009874`
- `0x14000a3ec`
- `0x14000a408`
- `0x14000d1c4`
- `0x14000d74c`
- `0x14000d7b4`
- `0x14000fea4`
- `0x140010140`
- `0x140010310`
- `0x1400103f0`
- `0x140018328`
- `0x1400186e0`
- `0x14001b9c0`
- `0x14001c710`
- `0x14001c76c`
- `0x14001ef90`
- `0x140020840`
- `0x140022100`
- `0x140022c20`
- `0x140022c54`
- `0x140023208`
- `0x140023570`
- `0x1400235ec`
- `0x1400241fc`
- `0x140026568`
- `0x140026840`
- `0x1400295a4`
- `0x14002bd60`
- `0x14002c2e0`
- `0x14002c410`
- `0x14002c820`
- `0x14002e150`
- `0x14002ea00`
- `0x14002eddc`
- `0x140033b58`
- `0x140035d14`
- `0x140080d30`
- `0x1400814d0`
- `0x140081b40`
- `0x14008f0dc`
- `0x140094860`
- `0x140096200`
- `0x1400ba214`
- `0x1400bbd30`
- `0x1400c1a1c`
- `0x1400c6fb4`
- `0x1400c83b0`
- `0x1400c847c`
- `0x1400cb390`
- `0x1400d0e30`

## import_xrefs

- `ntoskrnl!PsGetWin32KFilterSet` at `0x1401cafa1`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x1401cc8ce`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x1401cafa1`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x1401cc8ce`
- `ntoskrnl!KeBugCheckEx` at `0x1401cd457`
- `ntoskrnl!KeBugCheckEx` at `0x1401cd457`
- `win32kbase!GetTouchTimeFromCPLValue` at `0x1401ccd0c`
- `win32kbase!GetTouchTimeFromCPLValue` at `0x1401ccd0c`
- `win32kbase!EtwTraceRetrieveInputMessage` at `0x1401ca9c2`
- `win32kbase!EtwTraceRetrieveInputMessage` at `0x1401ca9c2`
- `win32kbase!?UpdateLastInputData@tagTHREADINFO@@QEAAXPEBUtagQMSG@@@Z` at `0x1401cb335`
- `win32kbase!?UpdateLastInputData@tagTHREADINFO@@QEAAXPEBUtagQMSG@@@Z` at `0x1401cb335`
- `win32kbase!EtwTraceEndPointerMessageRetrieve` at `0x1401cb8cc`
- `win32kbase!EtwTraceEndPointerMessageRetrieve` at `0x1401cb8cc`
- `win32kbase!EtwTraceBeginPointerMessageRetrieve` at `0x1401cb78d`
- `win32kbase!EtwTraceBeginPointerMessageRetrieve` at `0x1401cb78d`
- `win32kbase!ProcessTranslatedChar` at `0x1401cdebf`
- `win32kbase!ProcessTranslatedChar` at `0x1401cdebf`
- `win32kbase!CheckImEnabled` at `0x1401cde5f`
- `win32kbase!CheckImEnabled` at `0x1401cde5f`
- `win32kbase!?UpdateInputSource@tagTHREADINFO@@QEAAXAEBUtagINPUT_MESSAGE_SOURCE@@@Z` at `0x1401cc518`
- `win32kbase!?UpdateInputSource@tagTHREADINFO@@QEAAXAEBUtagINPUT_MESSAGE_SOURCE@@@Z` at `0x1401ccfa8`
- `win32kbase!?UpdateInputSource@tagTHREADINFO@@QEAAXAEBUtagINPUT_MESSAGE_SOURCE@@@Z` at `0x1401cc518`
- `win32kbase!?UpdateInputSource@tagTHREADINFO@@QEAAXAEBUtagINPUT_MESSAGE_SOURCE@@@Z` at `0x1401ccfa8`
- `win32kbase!GetMouseKeyFlags` at `0x1401cb218`
- `win32kbase!GetMouseKeyFlags` at `0x1401cc7d1`
- `win32kbase!GetMouseKeyFlags` at `0x1401cb218`
- `win32kbase!GetMouseKeyFlags` at `0x1401cc7d1`
- `win32kbase!IsMessageInputSourcePen` at `0x1401cd1f1`
- `win32kbase!IsMessageInputSourcePen` at `0x1401cd1f1`
- `win32kbase!IsMessageInputSourceTouch` at `0x1401cd1c6`
- `win32kbase!IsMessageInputSourceTouch` at `0x1401cd1c6`
- `win32kbase!EtwTraceUIPIMsgError` at `0x1401ce724`
- `win32kbase!EtwTraceUIPIMsgError` at `0x1401ce724`
- `win32kbase!MiPCheckMsgFilter` at `0x1401caecd`
- `win32kbase!MiPCheckMsgFilter` at `0x1401cc76b`
- `win32kbase!MiPCheckMsgFilter` at `0x1401ce102`
- `win32kbase!MiPCheckMsgFilter` at `0x1401caecd`
- `win32kbase!MiPCheckMsgFilter` at `0x1401cc76b`
- `win32kbase!MiPCheckMsgFilter` at `0x1401ce102`
- `win32kbase!EtwTraceRetrieveQueueEventMessage` at `0x1401ca71a`
- `win32kbase!EtwTraceRetrieveQueueEventMessage` at `0x1401ca71a`
- `win32kbase!ShouldDeferMessage` at `0x1401ca6b7`
- `win32kbase!ShouldDeferMessage` at `0x1401ca6b7`
- `win32kbase!DeferSysPeekMsg` at `0x1401ca6d7`
- `win32kbase!DeferSysPeekMsg` at `0x1401cd384`
- `win32kbase!DeferSysPeekMsg` at `0x1401cd6eb`
- `win32kbase!DeferSysPeekMsg` at `0x1401ca6d7`
- `win32kbase!DeferSysPeekMsg` at `0x1401cd384`
- `win32kbase!DeferSysPeekMsg` at `0x1401cd6eb`
- `win32kbase!EtwTraceInputQueueLocked` at `0x1401cba4f`
- `win32kbase!EtwTraceInputQueueLocked` at `0x1401cba4f`
- `win32kbase!EtwTraceInputQueueLockedPeekRecursion` at `0x1401cbbf3`
- `win32kbase!EtwTraceInputQueueLockedPeekRecursion` at `0x1401cbbf3`
- `win32kbase!EtwTraceInputProcessDelay` at `0x1401ca981`
- `win32kbase!EtwTraceInputProcessDelay` at `0x1401ca981`
- `win32kbase!IsGenuineMouseInput` at `0x1401cbd03`
- `win32kbase!IsGenuineMouseInput` at `0x1401cbd82`
- `win32kbase!IsGenuineMouseInput` at `0x1401ccddc`
- `win32kbase!IsGenuineMouseInput` at `0x1401ce378`
- `win32kbase!IsGenuineMouseInput` at `0x1401cbd03`
- `win32kbase!IsGenuineMouseInput` at `0x1401cbd82`
- `win32kbase!IsGenuineMouseInput` at `0x1401ccddc`
- `win32kbase!IsGenuineMouseInput` at `0x1401ce378`
- `win32kbase!IsMiPMouseMessage` at `0x1401cbceb`
- `win32kbase!IsMiPMouseMessage` at `0x1401ccdf3`
- `win32kbase!IsMiPMouseMessage` at `0x1401ce360`
- `win32kbase!IsMiPMouseMessage` at `0x1401cbceb`
- `win32kbase!IsMiPMouseMessage` at `0x1401ccdf3`
- `win32kbase!IsMiPMouseMessage` at `0x1401ce360`
- `win32kbase!ReferenceW32Thread` at `0x1401cbb59`
- `win32kbase!ReferenceW32Thread` at `0x1401cbb59`
- `win32kbase!IsDesktopApp` at `0x1401cdca0`
- `win32kbase!IsDesktopApp` at `0x1401cdca0`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1401ce76c`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1401ce76c`
- `win32kbase!IsWindowDesktopComposed` at `0x1401cc35a`
- `win32kbase!IsWindowDesktopComposed` at `0x1401cc35a`
- `win32kbase!ValidateHwnd` at `0x1401ce5ab`
- `win32kbase!ValidateHwnd` at `0x1401ce5ab`
- `WIN32K!W32GetUserSessionState` at `0x1401cac56`
- `WIN32K!W32GetUserSessionState` at `0x1401cb58a`
- `WIN32K!W32GetUserSessionState` at `0x1401cb716`
- `WIN32K!W32GetUserSessionState` at `0x1401cba9b`
- `WIN32K!W32GetUserSessionState` at `0x1401cbd42`
- `WIN32K!W32GetUserSessionState` at `0x1401cc0d8`
- `WIN32K!W32GetUserSessionState` at `0x1401cc599`
- `WIN32K!W32GetUserSessionState` at `0x1401cce70`
- `WIN32K!W32GetUserSessionState` at `0x1401cce88`
- `WIN32K!W32GetUserSessionState` at `0x1401cce9c`
- `WIN32K!W32GetUserSessionState` at `0x1401cd3d8`
- `WIN32K!W32GetUserSessionState` at `0x1401cd56e`
- `WIN32K!W32GetUserSessionState` at `0x1401cd612`
- `WIN32K!W32GetUserSessionState` at `0x1401cd7a9`
- `WIN32K!W32GetUserSessionState` at `0x1401cd810`
- `WIN32K!W32GetUserSessionState` at `0x1401cdd8f`
- `WIN32K!W32GetUserSessionState` at `0x1401cdf05`
- `WIN32K!W32GetUserSessionState` at `0x1401ce57f`
- `WIN32K!W32GetUserSessionState` at `0x1401ce635`
- `WIN32K!W32GetUserSessionState` at `0x1401ce730`
- `WIN32K!W32GetUserSessionState` at `0x1401ce7f7`
- `WIN32K!W32GetUserSessionState` at `0x1401ce867`
- `WIN32K!W32GetUserSessionState` at `0x1401ce899`
- `WIN32K!W32GetUserSessionState` at `0x1401ce8cb`
- `WIN32K!W32GetUserSessionState` at `0x1401ce8fb`
- `WIN32K!W32GetUserSessionState` at `0x1401cac56`
- `WIN32K!W32GetUserSessionState` at `0x1401cb58a`
- `WIN32K!W32GetUserSessionState` at `0x1401cb716`
- `WIN32K!W32GetUserSessionState` at `0x1401cba9b`
- `WIN32K!W32GetUserSessionState` at `0x1401cbd42`
- `WIN32K!W32GetUserSessionState` at `0x1401cc0d8`
- `WIN32K!W32GetUserSessionState` at `0x1401cc599`
- `WIN32K!W32GetUserSessionState` at `0x1401cce70`
- `WIN32K!W32GetUserSessionState` at `0x1401cce88`
- `WIN32K!W32GetUserSessionState` at `0x1401cce9c`
- `WIN32K!W32GetUserSessionState` at `0x1401cd3d8`
- `WIN32K!W32GetUserSessionState` at `0x1401cd56e`
- `WIN32K!W32GetUserSessionState` at `0x1401cd612`
- `WIN32K!W32GetUserSessionState` at `0x1401cd7a9`
- `WIN32K!W32GetUserSessionState` at `0x1401cd810`
- `WIN32K!W32GetUserSessionState` at `0x1401cdd8f`
- `WIN32K!W32GetUserSessionState` at `0x1401cdf05`
- `WIN32K!W32GetUserSessionState` at `0x1401ce57f`
- `WIN32K!W32GetUserSessionState` at `0x1401ce635`
- `WIN32K!W32GetUserSessionState` at `0x1401ce730`
- `WIN32K!W32GetUserSessionState` at `0x1401ce7f7`
- `WIN32K!W32GetUserSessionState` at `0x1401ce867`
- `WIN32K!W32GetUserSessionState` at `0x1401ce899`
- `WIN32K!W32GetUserSessionState` at `0x1401ce8cb`
- `WIN32K!W32GetUserSessionState` at `0x1401ce8fb`

## pseudocode

```c
__int64 __fastcall xxxScanSysQueue(
        __int64 a1,
        struct tagMSG *a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        char a6,
        int a7,
        struct tagQMSG **a8)
{
  char v9; // r12
  __int64 v10; // rdx
  struct tagQ **v11; // rbx
  __int16 v12; // r9
  struct tagQ *v13; // r15
  char v14; // bl
  bool v15; // di
  float v16; // xmm6_4
  char v17; // r15
  __int64 i; // rcx
  int v19; // r13d
  struct tagQ *v20; // rdx
  struct tagQMSG *NextSysMsg; // rdi
  char v22; // r15
  __int64 v23; // rdx
  __int64 v24; // rdx
  int v25; // r15d
  __int64 v26; // rdx
  __int64 v27; // rax
  struct tagQ *v28; // rax
  int v29; // r15d
  int v30; // eax
  __int64 v31; // r15
  char v32; // r15
  bool v33; // r15
  __int64 v34; // rbx
  __int64 v35; // r12
  struct _W32THREAD *v36; // r15
  __int64 v37; // rdi
  __int64 v38; // rcx
  struct tagTHREADINFO *v39; // rax
  unsigned __int64 v41; // rax
  struct tagTHREADINFO *v42; // rax
  char *v43; // rax
  int v44; // eax
  bool v45; // zf
  int v46; // ecx
  int v47; // ecx
  int v48; // ecx
  int v49; // r8d
  __int64 v50; // rax
  HWND *v51; // rdx
  __int64 v52; // rdx
  __int64 v53; // rcx
  int v54; // r8d
  struct tagWND *v55; // rbx
  int v56; // r9d
  __int64 v57; // rdx
  HWND v58; // rbx
  struct tagWND *v59; // rax
  __int64 v60; // rdx
  __int64 v61; // rdx
  int v62; // ebx
  __int64 v63; // rcx
  __int64 v64; // rcx
  const struct tagUIPI_INFO *v65; // r8
  struct tagPOINT v66; // rbx
  __int64 v67; // rcx
  int v68; // edx
  __int64 v69; // rdx
  int v70; // eax
  __int64 v71; // rdx
  int v72; // r13d
  int v73; // eax
  __int64 v74; // rdx
  __int64 v75; // rcx
  __int128 v76; // xmm12
  __int128 v77; // xmm13
  __int128 v78; // xmm14
  __int128 v79; // xmm15
  int v80; // r12d
  __int64 v81; // rcx
  __int64 v82; // rdx
  char v83; // bl
  struct tagMSG *v84; // r15
  __int64 v85; // rcx
  int v86; // ecx
  __int64 v87; // rdx
  unsigned int v88; // r13d
  __int64 v89; // rcx
  __int64 v90; // r8
  int v91; // edx
  unsigned __int64 v92; // rax
  BOOL v93; // edi
  Scrollbar::NonClient *v94; // rcx
  unsigned int v95; // eax
  __int64 v96; // r8
  __int64 UserSessionState; // rax
  int v98; // r8d
  int v99; // edx
  __int64 v100; // rbx
  __int64 v101; // rcx
  int v102; // ebx
  int v103; // ebx
  int v104; // ebx
  _DWORD *v105; // rax
  __int16 v106; // ax
  _QWORD *v107; // rax
  __int64 v108; // rcx
  LONG v109; // eax
  __int64 v110; // rdi
  __int64 v111; // rbx
  __int64 v112; // rax
  int v113; // r8d
  int v114; // edx
  char v115; // r13
  int v116; // eax
  int v117; // eax
  unsigned int v118; // eax
  __int64 v119; // rax
  unsigned int *v120; // rax
  _DWORD *v121; // rax
  __int64 v122; // rdx
  __int64 v123; // r15
  __int64 v124; // rcx
  const struct tagQMSG *v125; // r8
  __int64 v126; // rax
  struct tagWND *v127; // rbx
  unsigned __int64 v128; // rcx
  struct tagQ *v129; // rax
  __int64 v130; // rcx
  __int64 v131; // rcx
  int v132; // eax
  int v133; // r13d
  bool v134; // al
  __int64 v135; // rax
  struct tagWND *v136; // r8
  float *v137; // rbx
  const struct tagWND *TopLevelOrDpiBoundaryWindow; // rax
  __int64 v139; // rdx
  __int64 v140; // r8
  __int64 v141; // r9
  const struct tagWND *v142; // rdi
  char v143; // di
  char v144; // bl
  __int64 v145; // rdx
  __int64 v146; // rcx
  int v147; // r15d
  int v148; // r13d
  __int64 v149; // rdi
  unsigned int v150; // ebx
  __int64 v151; // rax
  __int64 v152; // rcx
  __int64 v153; // rdx
  ULONG_PTR v154; // r15
  __int64 v155; // rcx
  __int64 v156; // rcx
  int v157; // eax
  struct tagWND *v158; // rbx
  int v159; // eax
  unsigned int MouseKeyFlags; // eax
  int v161; // r9d
  __int64 v162; // rcx
  char MiPWindowFlags; // al
  struct tagQ **v164; // rcx
  __int64 v165; // rax
  __int128 v166; // xmm6
  __int128 v167; // xmm7
  __int128 v168; // xmm8
  __int128 v169; // xmm9
  __int128 v170; // xmm10
  __int128 v171; // xmm11
  struct tagWND *v172; // rcx
  unsigned int v173; // ecx
  __int64 v174; // rcx
  __int64 v175; // rcx
  int v176; // eax
  int v177; // ecx
  int TouchTimeFromCPLValue; // eax
  __int64 v179; // rdx
  int v180; // eax
  struct tagWND *v181; // rbx
  __int64 v182; // rcx
  __int64 v183; // rdx
  __int64 v184; // rcx
  char v185; // r8
  unsigned int v186; // ecx
  unsigned int v187; // edx
  __int64 v188; // rcx
  _QWORD *v189; // rax
  unsigned __int64 v190; // rbx
  ULONG_PTR v191; // r13
  unsigned __int64 v192; // r9
  unsigned int v193; // eax
  __int64 ThreadDesktopWindow; // rax
  int v195; // ebx
  __int64 v196; // rbx
  __int64 v197; // rdx
  __int64 v198; // rdx
  struct tagWND *v199; // rax
  __int64 v200; // rax
  char v201; // al
  int v202; // ecx
  __int64 v203; // rax
  char v204; // r15
  unsigned int v205; // r15d
  unsigned __int64 v206; // rcx
  __int64 v207; // rax
  __int64 v208; // rcx
  struct tagTHREADINFO *BugCheckParameter4; // rax
  float v210; // xmm2_4
  __int64 v211; // r8
  struct tagQ *v212; // rdi
  __int64 v213; // rbx
  __int64 v214; // rax
  int v215; // r8d
  int v216; // edx
  struct tagQ *v217; // rdi
  __int64 v218; // rbx
  __int64 v219; // rax
  int v220; // r8d
  int v221; // edx
  int v222; // r15d
  struct tagQ *v223; // rdi
  __int64 v224; // rbx
  __int64 v225; // rax
  int v226; // r8d
  int v227; // edx
  struct tagQ *v228; // rdi
  __int64 v229; // rbx
  __int64 v230; // rax
  int v231; // r8d
  int v232; // edx
  int v233; // ebx
  struct tagWND *CompositeAppFrameWindowOrSelf; // rdi
  BOOL v235; // ebx
  struct tagQ *v236; // rcx
  __int64 v237; // rax
  __int64 v238; // rcx
  __int64 v239; // rcx
  __int64 v240; // rbx
  struct tagQ *v241; // rdi
  __int64 v242; // rbx
  __int64 v243; // rax
  int v244; // r8d
  int v245; // edx
  __int64 v246; // rdx
  HWND *v247; // rdx
  __int64 v248; // rdx
  __int64 v249; // rdx
  Win32RawLockedW32Thread *v250; // rcx
  int v251; // eax
  int v252; // r9d
  _DWORD *v253; // rax
  _DWORD *v254; // rax
  __int64 v255; // rcx
  __int64 v256; // rcx
  __int64 v257; // rax
  __int64 v258; // r8
  __int64 v259; // rdx
  __int64 v260; // rax
  int v261; // r8d
  int v262; // edx
  __int64 v263; // rdx
  __int64 v264; // rax
  __int64 v265; // rcx
  LONG v266; // eax
  __int64 v267; // rdx
  __int64 v268; // rax
  __int64 v269; // rcx
  __int64 v270; // rdx
  __int64 v271; // kr00_8
  __int64 v272; // rdx
  __int64 v273; // kr08_8
  __int64 v274; // rax
  __int64 v275; // rcx
  __int64 v276; // rdx
  __int64 v277; // rt2
  __int64 v278; // rcx
  const struct tagWND *v279; // rcx
  struct tagWND *v280; // rax
  const struct tagWND *TopLevelWindow; // rax
  __int64 v282; // r8
  __int64 v283; // r8
  __int64 v284; // rax
  __int64 v285; // rbx
  int v286; // edx
  int v287; // eax
  struct tagTHREADINFO *v288; // rcx
  int InteractiveControlInputMessage; // eax
  char v290; // [rsp+48h] [rbp-690h]
  unsigned int v291; // [rsp+70h] [rbp-668h] BYREF
  _BYTE v292[12]; // [rsp+74h] [rbp-664h] BYREF
  int v293; // [rsp+80h] [rbp-658h]
  BOOL v294; // [rsp+84h] [rbp-654h]
  bool v295; // [rsp+88h] [rbp-650h]
  struct tagPOINT v296; // [rsp+90h] [rbp-648h] BYREF
  void *v297; // [rsp+98h] [rbp-640h] BYREF
  unsigned __int64 v298; // [rsp+A0h] [rbp-638h] BYREF
  int v299; // [rsp+A8h] [rbp-630h] BYREF
  int v300; // [rsp+ACh] [rbp-62Ch] BYREF
  struct tagQ **v301; // [rsp+B0h] [rbp-628h]
  unsigned int v302; // [rsp+B8h] [rbp-620h]
  unsigned int v303; // [rsp+BCh] [rbp-61Ch]
  bool v304; // [rsp+C0h] [rbp-618h]
  bool v305; // [rsp+C1h] [rbp-617h]
  char v306[2]; // [rsp+C2h] [rbp-616h] BYREF
  int v307; // [rsp+C4h] [rbp-614h]
  int v308; // [rsp+C8h] [rbp-610h]
  unsigned int v309; // [rsp+CCh] [rbp-60Ch]
  int v310; // [rsp+D0h] [rbp-608h]
  int v311; // [rsp+D4h] [rbp-604h]
  struct tagQMSG *v312; // [rsp+D8h] [rbp-600h]
  struct tagQMSG **v313; // [rsp+E0h] [rbp-5F8h]
  __int64 v314; // [rsp+E8h] [rbp-5F0h]
  __int64 v315; // [rsp+F0h] [rbp-5E8h]
  ULONG_PTR v316; // [rsp+F8h] [rbp-5E0h]
  __int64 v317; // [rsp+100h] [rbp-5D8h]
  int v318; // [rsp+108h] [rbp-5D0h]
  __int64 v319; // [rsp+110h] [rbp-5C8h]
  __int128 v320; // [rsp+118h] [rbp-5C0h]
  struct _W32THREAD *v321; // [rsp+128h] [rbp-5B0h]
  int v322; // [rsp+130h] [rbp-5A8h]
  int v323; // [rsp+134h] [rbp-5A4h]
  unsigned int v324; // [rsp+138h] [rbp-5A0h]
  unsigned int v325; // [rsp+140h] [rbp-598h]
  unsigned int v326; // [rsp+144h] [rbp-594h]
  struct tagTHREADINFO *v327; // [rsp+148h] [rbp-590h]
  struct _W32THREAD *v328; // [rsp+150h] [rbp-588h]
  ULONG_PTR BugCheckParameter2[2]; // [rsp+158h] [rbp-580h] BYREF
  __int64 v330; // [rsp+168h] [rbp-570h]
  ULONG_PTR v331[2]; // [rsp+170h] [rbp-568h] BYREF
  __int64 v332; // [rsp+180h] [rbp-558h]
  struct tagMSG *v333; // [rsp+188h] [rbp-550h]
  __int64 v334; // [rsp+190h] [rbp-548h]
  __int64 v335; // [rsp+1A8h] [rbp-530h]
  struct tagMSG *v336; // [rsp+1B0h] [rbp-528h]
  __int64 v337; // [rsp+1C8h] [rbp-510h]
  __int64 v338; // [rsp+1D0h] [rbp-508h]
  __int64 v339; // [rsp+1D8h] [rbp-500h]
  __int64 v340; // [rsp+1E0h] [rbp-4F8h]
  char v341[8]; // [rsp+1E8h] [rbp-4F0h] BYREF
  unsigned int v342; // [rsp+1F0h] [rbp-4E8h] BYREF
  unsigned int v343; // [rsp+1F4h] [rbp-4E4h]
  int v344; // [rsp+1F8h] [rbp-4E0h]
  int v345; // [rsp+1FCh] [rbp-4DCh]
  int v346; // [rsp+200h] [rbp-4D8h]
  struct tagMSG *v347; // [rsp+208h] [rbp-4D0h]
  ULONG_PTR v348[2]; // [rsp+210h] [rbp-4C8h] BYREF
  __int64 v349; // [rsp+220h] [rbp-4B8h]
  _BYTE v350[24]; // [rsp+228h] [rbp-4B0h] BYREF
  _BYTE v351[24]; // [rsp+240h] [rbp-498h] BYREF
  _BYTE v352[24]; // [rsp+258h] [rbp-480h] BYREF
  _BYTE v353[24]; // [rsp+270h] [rbp-468h] BYREF
  _BYTE v354[48]; // [rsp+288h] [rbp-450h] BYREF
  ULONG_PTR v355[2]; // [rsp+2B8h] [rbp-420h] BYREF
  ULONG_PTR v356[2]; // [rsp+2C8h] [rbp-410h] BYREF
  ULONG_PTR v357[3]; // [rsp+2D8h] [rbp-400h] BYREF
  ULONG_PTR BugCheckParameter3[2]; // [rsp+2F0h] [rbp-3E8h] BYREF
  __int128 v359; // [rsp+300h] [rbp-3D8h] BYREF
  HWND v360[2]; // [rsp+310h] [rbp-3C8h]
  unsigned __int64 v361[2]; // [rsp+320h] [rbp-3B8h]
  __int128 v362; // [rsp+330h] [rbp-3A8h]
  __int128 v363; // [rsp+340h] [rbp-398h]
  struct tagPOINT v364[2]; // [rsp+350h] [rbp-388h] BYREF
  __int128 v365; // [rsp+360h] [rbp-378h]
  __int128 v366; // [rsp+370h] [rbp-368h] BYREF
  __int128 v367; // [rsp+380h] [rbp-358h]
  __int128 v368; // [rsp+390h] [rbp-348h]
  __int64 v369; // [rsp+3A0h] [rbp-338h]
  __int64 v370[2]; // [rsp+3B0h] [rbp-328h] BYREF
  __int128 v371; // [rsp+3C0h] [rbp-318h]
  __int64 v372; // [rsp+3D0h] [rbp-308h]
  _OWORD v373[3]; // [rsp+3E0h] [rbp-2F8h] BYREF
  __int128 v374; // [rsp+410h] [rbp-2C8h]
  __int128 v375; // [rsp+420h] [rbp-2B8h]
  __int128 v376; // [rsp+430h] [rbp-2A8h]
  __int128 v377; // [rsp+440h] [rbp-298h]
  __int128 v378; // [rsp+450h] [rbp-288h]
  __int128 v379; // [rsp+460h] [rbp-278h]
  __int128 v380; // [rsp+470h] [rbp-268h]
  __int64 v381; // [rsp+480h] [rbp-258h]
  __int128 v382; // [rsp+490h] [rbp-248h] BYREF
  __int128 v383; // [rsp+4A0h] [rbp-238h]
  __int128 v384; // [rsp+4B0h] [rbp-228h]
  __int128 v385; // [rsp+4C0h] [rbp-218h]
  __int128 v386; // [rsp+4D0h] [rbp-208h]
  __int128 v387; // [rsp+4E0h] [rbp-1F8h]
  __int128 v388; // [rsp+4F0h] [rbp-1E8h]
  __int128 v389; // [rsp+500h] [rbp-1D8h]
  __int128 v390; // [rsp+510h] [rbp-1C8h]
  __int128 v391; // [rsp+520h] [rbp-1B8h]
  __int64 v392; // [rsp+530h] [rbp-1A8h]
  _OWORD v393[10]; // [rsp+540h] [rbp-198h] BYREF
  __int64 v394; // [rsp+5E0h] [rbp-F8h]

  v303 = a4;
  v317 = a3;
  v336 = a2;
  v332 = a1;
  v337 = a1;
  v347 = a2;
  v327 = (struct tagTHREADINFO *)a1;
  v338 = a1;
  v333 = a2;
  v340 = a3;
  v324 = a4;
  v313 = a8;
  memset_0(&v359, 0, 0xA8u);
  *(_DWORD *)&v292[8] = 0;
  v291 = 0;
  v298 = 0;
  v297 = 0;
  v296 = 0;
  v300 = 0;
  v299 = 0;
  *(_OWORD *)v370 = 0;
  v371 = 0;
  v372 = 0;
  v9 = 1;
  v10 = a6 & 1;
  *(_QWORD *)v292 = v10;
  *a8 = 0;
  v11 = (struct tagQ **)(a1 + 464);
  v301 = (struct tagQ **)(a1 + 464);
  v12 = a7;
  if ( a7 == 0x2000 )
  {
    if ( *((_QWORD *)*v11 + 11) )
    {
      EtwTraceInputQueueLockedPeekRecursion();
      return 0;
    }
  }
  else
  {
    v301 = (struct tagQ **)(a1 + 464);
  }
  v339 = a1 + 464;
  v13 = *v11;
  if ( !*((_QWORD *)*v11 + 9) )
  {
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20000) == 0
      || (v14 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
    {
      v14 = 0;
    }
    v15 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v14 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      UserSessionState = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, v10);
      LOBYTE(v98) = v15;
      LOBYTE(v99) = v14;
      WPP_RECORDER_AND_TRACE_SF_qqq(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v99,
        v98,
        *(_QWORD *)(UserSessionState + 69152),
        4,
        18,
        29,
        (__int64)WPP_49cdbed1bece331d44f23b214bd7a204_Traceguids,
        (char)v13,
        a1,
        a1);
      v12 = a7;
    }
    v11 = v301;
    *((_QWORD *)*v301 + 9) = a1;
    **(_DWORD **)(a1 + 480) |= 1u;
    LODWORD(v10) = *(_DWORD *)v292;
  }
  if ( (v12 & 0x1C07) != 0 )
  {
    v117 = *((_DWORD *)*v11 + 127);
    if ( (_DWORD)v10 )
      v118 = v117 & 0xFFFFFBFF;
    else
      v118 = v117 | 0x400;
    *((_DWORD *)*v11 + 127) = v118;
  }
  if ( *((_QWORD *)*v11 + 9) != a1 )
  {
    EtwTraceInputQueueLocked();
    return 2;
  }
  v335 = a1;
  v326 = a5;
  v349 = a1;
  v325 = v303;
  v322 = 0;
  v311 = 0;
  v302 = 0;
  v294 = 0;
  v295 = 0;
  v316 = 0;
  v318 = 0;
  v307 = 0;
  v293 = 0;
  v314 = 0;
  v334 = 0;
  v328 = 0;
  v319 = 0;
  v321 = 0;
  v315 = 0;
  Win32RawLockedW32Thread::Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v351, 0);
  Win32RawLockedW32Thread::Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v350, 0);
  Win32RawLockedW32Thread::Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v352, 0);
  Win32RawLockedW32Thread::Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v354, 0);
  Win32RawLockedW32Thread::Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v353, 0);
  *(_QWORD *)&v292[4] = 0;
  Win32HMOptionalThreadLock<tagWND>::Win32HMOptionalThreadLock<tagWND>(v331, a1, 0);
  CManageInScanSysQueueBit::CManageInScanSysQueueBit((CManageInScanSysQueueBit *)v306);
LABEL_13:
  v16 = FLOAT_1_0;
LABEL_14:
  while ( 2 )
  {
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u )
    {
      v9 = 0;
    }
    if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
      || (v17 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
    {
      v17 = 0;
    }
    if ( v9 || v17 )
    {
      v212 = *v11;
      v213 = *((_QWORD *)*v11 + 11);
      v214 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED);
      LOBYTE(v215) = v17;
      LOBYTE(v216) = v9;
      WPP_RECORDER_AND_TRACE_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v216,
        v215,
        *(_QWORD *)(v214 + 69152),
        5,
        18,
        30,
        (__int64)WPP_49cdbed1bece331d44f23b214bd7a204_Traceguids,
        (char)v212,
        v213);
      v11 = v301;
    }
    *((_QWORD *)*v11 + 11) = 0;
LABEL_22:
    v9 = 1;
LABEL_23:
    LOBYTE(i) = v294;
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          do
          {
            while ( 1 )
            {
              while ( 1 )
              {
                while ( 1 )
                {
                  while ( 1 )
                  {
                    v19 = (**(_DWORD **)(a1 + 512) >> 9) & 1;
                    v346 = v19;
                    v20 = *v11;
                    if ( *((_QWORD *)*v11 + 11) )
                    {
                      if ( !(_BYTE)i )
                      {
                        v294 = ((v302 - 1) & 0xFFFFFFFD) == 0;
                        v295 = ((v302 - 1) & 0xFFFFFFFD) == 0;
                      }
                    }
                    else
                    {
                      v302 = 0;
                      v294 = 0;
                      v295 = 0;
                    }
                    v298 = 0;
                    NextSysMsg = xxxGetNextSysMsg(
                                   (struct tagTHREADINFO *)a1,
                                   *((struct tagQMSG **)v20 + 11),
                                   (struct tagQMSG *)&v359);
                    v312 = NextSysMsg;
                    LODWORD(i) = (_DWORD)WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
                      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20000) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u )
                    {
                      v9 = 0;
                    }
                    if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
                      || (v22 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
                    {
                      v22 = 0;
                    }
                    if ( v9 || v22 )
                    {
                      v217 = *v11;
                      v218 = *((_QWORD *)*v11 + 11);
                      v219 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED);
                      v290 = (char)v217;
                      NextSysMsg = v312;
                      LOBYTE(v220) = v22;
                      LOBYTE(v221) = v9;
                      WPP_RECORDER_AND_TRACE_SF_qqq(
                        *((_QWORD *)WPP_GLOBAL_Control + 3),
                        v221,
                        v220,
                        *(_QWORD *)(v219 + 69152),
                        5,
                        18,
                        31,
                        (__int64)WPP_49cdbed1bece331d44f23b214bd7a204_Traceguids,
                        (char)v312,
                        v290,
                        v218);
                      v11 = v301;
                    }
                    *((_QWORD *)*v11 + 11) = NextSysMsg;
                    if ( !NextSysMsg )
                      goto LABEL_33;
                    v30 = DWORD1(v365);
                    if ( (BYTE4(v365) & 0x20) != 0 )
                    {
                      i = (__int64)v313;
                      *v313 = NextSysMsg;
                      *((_DWORD *)NextSysMsg + 25) |= 0x100u;
                      *(_DWORD *)v292 = 0;
                      v30 = DWORD1(v365);
                      if ( (DWORD1(v365) & 0x8000000) != 0 )
                      {
                        *(_DWORD *)(*(_QWORD *)i + 100LL) |= 0x8000000u;
                        v30 = DWORD1(v365);
                      }
                    }
                    if ( (v30 & 0x2000) == 0 )
                      break;
                    v222 = v302;
                    v9 = 1;
                    if ( *((_QWORD *)&v365 + 1) == a1 )
                      v222 = 1;
                    v302 = v222;
                    LOBYTE(i) = 1;
                    v294 = i;
                    v295 = 1;
                  }
                  LOBYTE(i) = v294;
                  if ( (v30 & 0x10000) == 0 )
                    break;
                  v9 = 1;
                  if ( *((_QWORD *)&v365 + 1) == a1 )
                  {
                    v302 = 3;
                    goto LABEL_23;
                  }
                }
                if ( (_DWORD)v365 == 4 && v294 )
                {
                  DeferSysPeekMsg(a1, 3);
                  goto LABEL_22;
                }
                if ( (v30 & 0x4000) == 0 )
                  break;
                v9 = 1;
                if ( *((_QWORD *)&v365 + 1) == a1 )
                  v302 = 2;
              }
              if ( (unsigned int)ShouldDeferMessage(v302, &v359) )
              {
                DeferSysPeekMsg(a1, 3);
                v302 = 3;
                goto LABEL_22;
              }
LABEL_33:
              if ( !*((_QWORD *)*v11 + 11) )
              {
                if ( a7 == 0x2000 )
                  _InterlockedAnd((volatile signed __int32 *)(*(_QWORD *)(a1 + 480) + 8LL), 0xFFFFDFFF);
                goto LABEL_75;
              }
              Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)v331);
              v9 = 1;
              LOBYTE(v23) = 1;
              *(_QWORD *)&v292[4] = HMValidateHandleNoSecure(v360[0], v23);
              Win32HM_LockIntoThread<1>(a1, *(_QWORD *)&v292[4], v331);
              v24 = (unsigned int)v365;
              if ( !(_DWORD)v365 )
                break;
              if ( (_DWORD)v365 == 4 )
              {
                LOBYTE(i) = v294;
                if ( *((_QWORD *)*v11 + 11) != *((_QWORD *)*v11 + 3) )
                  continue;
              }
              if ( (_DWORD)v365 != 9 || LODWORD(v360[1]) != 96 )
                goto LABEL_65;
              for ( i = *((_QWORD *)&v359 + 1); i && (unsigned int)IsHiddenByInputService(); i = *(_QWORD *)(i + 8) )
                ;
              v45 = i == 0;
              LOBYTE(i) = v294;
              if ( v45 )
              {
LABEL_65:
                v31 = *((_QWORD *)&v365 + 1);
                if ( !*((_QWORD *)&v365 + 1) || *((_QWORD *)&v365 + 1) == a1 )
                {
                  EtwTraceRetrieveQueueEventMessage(*((_QWORD *)*v11 + 11));
                  DelQEntry((char *)*v11 + 24, *((_QWORD *)*v11 + 11), 1);
                  if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
                    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20000) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u )
                  {
                    v9 = 0;
                  }
                  if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
                    || (v32 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
                  {
                    v32 = 0;
                  }
                  if ( v9 || v32 )
                  {
                    v228 = *v11;
                    v229 = *((_QWORD *)*v11 + 11);
                    v230 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED);
                    LOBYTE(v231) = v32;
                    LOBYTE(v232) = v9;
                    WPP_RECORDER_AND_TRACE_SF_qq(
                      *((_QWORD *)WPP_GLOBAL_Control + 3),
                      v232,
                      v231,
                      *(_QWORD *)(v230 + 69152),
                      5,
                      18,
                      33,
                      (__int64)WPP_49cdbed1bece331d44f23b214bd7a204_Traceguids,
                      (char)v228,
                      v229);
                    v11 = v301;
                  }
                  *((_QWORD *)*v11 + 11) = 0;
                  xxxProcessEventMessage(a1, &v359);
                  v9 = 1;
                  goto LABEL_14;
                }
                if ( *(struct tagQ **)(*((_QWORD *)&v365 + 1) + 464LL) != *v11 )
                {
                  CleanEventMessage(*((struct tagQMSG **)*v11 + 11));
                  DelQEntry((char *)*v11 + 24, *((_QWORD *)*v11 + 11), 1);
                  goto LABEL_14;
                }
                ReferenceW32Thread(*((_QWORD *)&v365 + 1));
                ExchangeW32ThreadLock(v31, v352);
                if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20000) == 0
                  || (v115 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
                {
                  v115 = 0;
                }
                if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
                  || !*((_WORD *)WPP_GLOBAL_Control + 36) )
                {
                  v9 = 0;
                }
                if ( v115 || v9 )
                {
                  v223 = *v11;
                  v224 = *((_QWORD *)*v11 + 11);
                  v225 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED);
                  LOBYTE(v226) = v9;
                  LOBYTE(v227) = v115;
                  WPP_RECORDER_AND_TRACE_SF_qq(
                    *((_QWORD *)WPP_GLOBAL_Control + 3),
                    v227,
                    v226,
                    *(_QWORD *)(v225 + 69152),
                    5,
                    18,
                    32,
                    (__int64)WPP_49cdbed1bece331d44f23b214bd7a204_Traceguids,
                    (char)v223,
                    v224);
                  v11 = v301;
                }
                *((_QWORD *)*v11 + 11) = 0;
                v319 = v31;
                goto LABEL_75;
              }
            }
            i = v294;
          }
          while ( a7 == 0x2000 );
          v25 = 0;
          v310 = 0;
          v308 = 0;
          v309 = 0;
          v291 = (unsigned int)v360[1];
          if ( LODWORD(v360[1]) > 0x24A )
          {
            if ( LODWORD(v360[1]) <= 0x2ED )
            {
              if ( LODWORD(v360[1]) == 749 )
                goto LABEL_873;
              if ( LODWORD(v360[1]) == 593 || LODWORD(v360[1]) == 594 || LODWORD(v360[1]) == 595 )
                goto LABEL_210;
              v46 = LODWORD(v360[1]) - 744;
              v45 = LODWORD(v360[1]) == 744;
              goto LABEL_124;
            }
            if ( LODWORD(v360[1]) != 750 && LODWORD(v360[1]) != 751 && LODWORD(v360[1]) != 752 )
            {
              v46 = LODWORD(v360[1]) - 753;
              v45 = LODWORD(v360[1]) == 753;
LABEL_124:
              if ( v45 )
                goto LABEL_873;
              v47 = v46 - 1;
              if ( !v47 )
                goto LABEL_873;
              v48 = v47 - 1;
              if ( !v48 || (unsigned int)(v48 - 1) < 2 )
                goto LABEL_873;
              goto LABEL_128;
            }
LABEL_873:
            if ( v303 || a5 != -1 )
            {
              if ( v303 <= a5 )
              {
                if ( LODWORD(v360[1]) >= v325 && LODWORD(v360[1]) <= v326 )
                  goto LABEL_883;
                v287 = 0;
              }
              else
              {
                if ( LODWORD(v360[1]) >= v326 && LODWORD(v360[1]) <= v325 )
                  goto LABEL_75;
                v287 = 1;
              }
              if ( !v287 )
                goto LABEL_75;
            }
LABEL_883:
            if ( !(unsigned int)IsInsideMenuLoop(a1) )
            {
              if ( *(_DWORD *)v292 )
                xxxSkipSysMsgEx(v288, (struct tagQMSG *)&v359, 1);
              if ( !*(_QWORD *)&v292[4] )
                *(_QWORD *)&v292[4] = *(_QWORD *)(*(_QWORD *)(a1 + 464) + 120LL);
              v298 = v361[0];
              v297 = (void *)v361[1];
              InteractiveControlInputMessage = xxxRetrieveInteractiveControlInputMessage(
                                                 LOWORD(v361[0]),
                                                 WORD1(v361[0]));
              if ( InteractiveControlInputMessage == 1 )
                goto LABEL_198;
              if ( InteractiveControlInputMessage == 2 )
                goto LABEL_75;
            }
            goto LABEL_51;
          }
          if ( LODWORD(v360[1]) == 586 )
            goto LABEL_210;
          if ( LODWORD(v360[1]) > 0x11B )
            break;
          switch ( LODWORD(v360[1]) )
          {
            case 0x11B:
              goto LABEL_106;
            case 0x23:
              v298 = 0;
              v297 = (void *)v361[1];
              if ( !*(_QWORD *)&v292[4] || (v249 = *(_QWORD *)(*(_QWORD *)&v292[4] + 16LL), v249 == a1) )
              {
                if ( (unsigned int)MiPCheckMsgFilter(NextSysMsg, v291, v303, a5) )
                {
LABEL_736:
                  if ( *(_DWORD *)v292 )
                    xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v359, 1);
                  goto LABEL_198;
                }
              }
              else
              {
                if ( *(struct tagQ **)(v249 + 464) != *v11 )
                  goto LABEL_51;
                if ( !v314 )
                {
                  v314 = *(_QWORD *)(*(_QWORD *)&v292[4] + 16LL);
                  v250 = (Win32RawLockedW32Thread *)v350;
                  goto LABEL_734;
                }
              }
LABEL_75:
              v9 = 1;
              goto LABEL_76;
            case 0xFE:
LABEL_110:
              v298 = v361[0];
              v297 = (void *)v361[1];
              if ( !*(_QWORD *)&v292[4] )
                goto LABEL_51;
              if ( CheckCrossThreadInput(*(struct tagWND *const *)&v292[4], NextSysMsg, &v300, (int *)v292, v313) )
                goto LABEL_75;
              if ( v300 )
                goto LABEL_51;
              if ( !v303 && a5 == -1 )
              {
LABEL_749:
                v251 = CheckPwndFilter(*(_QWORD *)&v292[4], v317);
                LOBYTE(i) = v294;
                if ( v251 )
                  goto LABEL_736;
              }
              else
              {
                if ( v303 <= a5 )
                {
                  if ( v291 >= v303 && v291 <= a5 )
                    goto LABEL_749;
                  v44 = 0;
                  goto LABEL_748;
                }
                if ( v291 < a5 || (LOBYTE(i) = v294, v291 > v303) )
                {
                  v44 = 1;
LABEL_748:
                  LOBYTE(i) = v294;
                  if ( v44 )
                    goto LABEL_749;
                }
              }
              break;
            case 0xFF:
              v298 = v361[0];
              v297 = (void *)v361[1];
              if ( !DeleteHidDataIfAlreadyHandledByGRIB((struct tagTHREADINFO *)a1, v361[1]) )
              {
                *(_QWORD *)&v292[4] = 0;
                v26 = 0;
                if ( v297 )
                {
                  LOBYTE(v26) = 18;
                  v27 = HMValidateHandleNoSecure(v297, v26);
                  v26 = v27;
                  if ( v27 )
                    *(_QWORD *)&v292[4] = *(_QWORD *)(v27 + 24);
                }
                if ( !*(_QWORD *)&v292[4] )
                {
                  v28 = *v11;
                  *(_QWORD *)&v292[4] = *((_QWORD *)*v11 + 15);
                  if ( !*(_QWORD *)&v292[4] )
                  {
                    *(_QWORD *)&v292[4] = *((_QWORD *)v28 + 16);
                    if ( !*(_QWORD *)&v292[4] )
                    {
                      InputTraceLogging::RawInput::SSQResult(v297, 0);
                      goto LABEL_51;
                    }
                  }
                }
                if ( v26 && *(_QWORD *)(v26 + 16) != *(_QWORD *)(*(_QWORD *)&v292[4] + 16LL) )
                {
                  v323 = 0x20000;
                  MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 10065);
                }
                Win32HM_ExchangeThreadLock<1>(*(_QWORD *)&v292[4], v331);
                if ( CheckCrossThreadInput(*(struct tagWND *const *)&v292[4], NextSysMsg, &v300, (int *)v292, v313) )
                {
                  v246 = 0;
                  goto LABEL_713;
                }
                if ( !v300 )
                  goto LABEL_241;
                if ( *(struct tagQ **)(*(_QWORD *)(*(_QWORD *)&v292[4] + 16LL) + 464LL) != *v11 )
                  goto LABEL_51;
                if ( (unsigned int)IsInsideMenuLoop(a1) )
                {
                  v247 = *(HWND **)(**(_QWORD **)(a1 + 640) + 8LL);
                }
                else
                {
                  v248 = *(_QWORD *)(a1 + 704);
                  if ( v248 )
                    v247 = *(HWND **)(v248 + 16);
                  else
                    v247 = 0;
                }
                if ( v247 )
                  InputTraceLogging::RawInput::IgnoreModalLoop(v297, *v247);
                if ( !v321 )
                {
                  v321 = *(struct _W32THREAD **)(*(_QWORD *)&v292[4] + 16LL);
                  Win32RawLockedW32Thread::Exchange((Win32RawLockedW32Thread *)v354, v321);
                }
LABEL_241:
                if ( !v303 && a5 == -1 )
                  goto LABEL_243;
                if ( v303 > a5 )
                {
                  if ( v291 >= a5 && v291 <= v303 )
                    goto LABEL_302;
                  v116 = 1;
                }
                else
                {
                  if ( v291 >= v303 && v291 <= a5 )
                  {
LABEL_243:
                    if ( (unsigned int)CheckPwndFilter(*(_QWORD *)&v292[4], v317) )
                    {
                      if ( !v300 )
                      {
                        if ( *(_DWORD *)v292 )
                          xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v359, 1);
                        InputTraceLogging::RawInput::SSQResult(v297, 4);
                        goto LABEL_198;
                      }
                      v246 = 3;
LABEL_713:
                      InputTraceLogging::RawInput::SSQResult(v297, v246);
                      goto LABEL_76;
                    }
LABEL_302:
                    InputTraceLogging::RawInput::SSQResult(v297, 2);
                    goto LABEL_23;
                  }
                  v116 = 0;
                }
                if ( !v116 )
                  goto LABEL_302;
                goto LABEL_243;
              }
LABEL_51:
              v29 = v293;
              goto LABEL_52;
            case 0x100:
              goto LABEL_350;
            case 0x101:
LABEL_355:
              v298 = LOBYTE(v361[0]);
              v128 = v361[0];
              if ( LOBYTE(v361[0]) == 231 )
                v128 = 231;
              v361[0] = v128;
              if ( !*(_DWORD *)v292 || (WORD2(v365) & 0x8000) == 0 )
              {
                if ( *(_DWORD *)(W32GetUserSessionState(v128, v24) + 14224) )
                {
                  if ( (GetAppImeCompatFlags(0) & 0x800000) == 0 && BYTE2(v361[1]) == 41 )
                  {
                    if ( *(_DWORD *)v292 )
                    {
                      v236 = *v11;
                      if ( (*((_BYTE *)*v11 + 356) & 0x15) == 0
                        && (*((_BYTE *)v236 + 374) & 0x40) == 0
                        && (*((_BYTE *)v236 + 375) & 1) == 0 )
                      {
                        v237 = *((_QWORD *)v236 + 15);
                        *(_QWORD *)&v292[4] = v237;
                        if ( !v237 )
                        {
                          v237 = *((_QWORD *)v236 + 16);
                          *(_QWORD *)&v292[4] = v237;
                        }
                        if ( !v237 || *(_QWORD *)(v237 + 16) == a1 )
                        {
                          xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v359, 1);
                          if ( !v318 && *(_QWORD *)&v292[4] )
                          {
                            *(_QWORD *)&v373[0] = **(_QWORD **)&v292[4];
                            *((_QWORD *)&v373[0] + 1) = 80;
                            memset(&v373[1], 0, 32);
                            xxxCallCtfHook(3, 0, 1, v373);
                          }
                          goto LABEL_14;
                        }
                      }
                    }
                  }
                }
              }
              if ( v298 == 121 )
                v291 |= 4u;
              if ( (*((_BYTE *)*v11 + 356) & 4) != 0 && v298 == 27 )
                v291 |= 4u;
              if ( (_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 520), 0, 0) & 8) == 0 )
                v361[1] &= ~0x2000000uLL;
LABEL_364:
              v298 = LOBYTE(v361[0]);
              v129 = *v11;
              v130 = *((_QWORD *)*v11 + 15);
              *(_QWORD *)&v292[4] = v130;
              if ( !*((_QWORD *)v129 + 15) )
              {
                v130 = *((_QWORD *)v129 + 16);
                *(_QWORD *)&v292[4] = v130;
                if ( !v130 )
                  goto LABEL_51;
                if ( v291 - 256 <= 3 )
                  v291 += 4;
              }
              Win32HM_ExchangeThreadLock<1>(v130, v331);
              v131 = *(_QWORD *)(*(_QWORD *)&v292[4] + 16LL);
              v300 = v131 != v338;
              if ( v131 != v332 )
              {
                if ( *(struct tagQ **)(*(_QWORD *)(*(_QWORD *)&v292[4] + 16LL) + 464LL) != *v11 )
                  goto LABEL_51;
                if ( (unsigned int)IsInsideMenuLoop(a1) )
                {
                  v238 = *(_QWORD *)(**(_QWORD **)(a1 + 640) + 8LL);
                }
                else
                {
                  v239 = *(_QWORD *)(a1 + 704);
                  if ( v239 )
                    v238 = *(_QWORD *)(v239 + 16);
                  else
                    v238 = 0;
                }
                if ( v238 )
                {
                  *(_QWORD *)&v292[4] = v238;
                  v300 = *(_QWORD *)(v238 + 16) != v349;
                  Win32HM_ExchangeThreadLock<1>(v238, v331);
                }
                if ( !v328 )
                {
                  v328 = *(struct _W32THREAD **)(*(_QWORD *)&v292[4] + 16LL);
                  Win32RawLockedW32Thread::Exchange((Win32RawLockedW32Thread *)v351, v328);
                }
              }
              if ( v303 || a5 != -1 )
              {
                if ( v303 > a5 )
                {
                  if ( v291 < a5 || (LOBYTE(i) = v294, v291 > v303) )
                  {
                    v180 = 1;
                    goto LABEL_513;
                  }
                }
                else
                {
                  if ( v291 >= v303 && v291 <= a5 )
                    goto LABEL_368;
                  v180 = 0;
LABEL_513:
                  LOBYTE(i) = v294;
                  if ( v180 )
                    goto LABEL_368;
                }
              }
              else
              {
LABEL_368:
                v132 = CheckPwndFilter(*(_QWORD *)&v292[4], v317);
                LOBYTE(i) = v294;
                if ( v132 )
                {
                  if ( v300 )
                    goto LABEL_75;
                  if ( *(_DWORD *)v292 )
                  {
                    if ( (WORD2(v365) & 0x8000) != 0 )
                      goto LABEL_403;
                    if ( !(unsigned int)IsInsideMenuLoop(a1) )
                    {
                      if ( v298 == 93 && v291 == 257 )
                      {
                        if ( *(_QWORD *)&v292[4] )
                          v211 = **(_QWORD **)&v292[4];
                        else
                          LODWORD(v211) = 0;
                        PostTransformableMessage(*(_DWORD *)&v292[4], 123, v211, -1, 0);
                      }
                      if ( v298 == 112 && v291 == 256 )
                        PostMessage(*(_QWORD *)&v292[4], 77, 0);
                    }
                  }
                  if ( v298 == 16 && !v318 )
                  {
                    v240 = v361[1] & 0x1000000;
                    if ( ((unsigned __int8)(v240 != 0 ? 1 : 4) & *((_BYTE *)*v301 + 392)) != 0 )
                    {
                      if ( (unsigned int)IsDesktopApp(*(_QWORD *)(a1 + 456))
                        && (_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 520), 0, 0) & 8) == 0 )
                      {
                        v361[0] = (v240 != 0) + 160LL;
LABEL_681:
                        xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v359, 1);
                        goto LABEL_846;
                      }
                      v11 = v301;
                    }
                    else
                    {
                      v11 = v301;
                    }
                  }
                  v322 = *((unsigned __int8 *)*v11 + ((unsigned __int64)(unsigned __int8)v298 >> 2) + 352)
                       & (1 << (2 * (v298 & 3)));
                  if ( !v322 )
                    goto LABEL_403;
                  if ( *(_DWORD *)v292 )
                  {
                    if ( NextSysMsg )
                      *((_QWORD *)NextSysMsg + 5) |= 0x40000000uLL;
LABEL_403:
                    if ( *(_DWORD *)v292 )
                    {
                      if ( (WORD2(v365) & 0x8000) == 0 && NextSysMsg && (*(_DWORD *)(a1 + 1360) & 0x10000000) != 0 )
                        v316 = (ULONG_PTR)xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v359, 0);
                      else
                        xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v359, 1);
                    }
                  }
                  v297 = (void *)v361[1];
                  v298 = v361[0];
                  if ( v322 )
                    v297 = (void *)(v361[1] | 0x40000000);
                  if ( v291 == 257 || v291 == 261 )
                    v297 = (void *)((unsigned __int64)v297 | 0x80000000);
                  if ( (*((_BYTE *)*v11 + 356) & 0x10) != 0 )
                    v297 = (void *)((unsigned __int64)v297 | 0x20000000);
                  if ( (unsigned int)IsMenuStarted(a1) )
                    v297 = (void *)((unsigned __int64)v297 | 0x10000000);
                  if ( (*(_DWORD *)(v145 + 508) & 0x4000) != 0 )
                    v297 = (void *)((unsigned __int64)v297 | 0x8000000);
                  if ( !v19 && !*(_QWORD *)(W32GetUserSessionState(v146, v145) + 12888) || (WORD2(v365) & 0x8000) != 0 )
                    goto LABEL_416;
                  if ( !*(_DWORD *)v292 )
                  {
LABEL_417:
                    LOBYTE(v147) = v308;
                    goto LABEL_418;
                  }
                  if ( (unsigned int)IsMenuStarted(a1)
                    || (_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 520), 0, 0) & 0x2000000) != 0
                    || !*(_QWORD *)&v292[4] )
                  {
LABEL_416:
                    if ( !*(_DWORD *)v292 )
                      goto LABEL_417;
                    v147 = v308;
                    if ( (WORD2(v365) & 0x8000) != 0 )
                    {
                      if ( (DWORD1(v365) & 0x4000000) != 0 )
                        v147 = 2;
                      v308 = v147;
                      v309 = v147;
                    }
                  }
                  else
                  {
                    v190 = v298;
                    if ( v298 == 231 )
                      v190 = ((unsigned __int64)*(unsigned __int16 *)(a1 + 914) << 16) | 0xE7;
                    tagTHREADINFO::UpdateInputSource(
                      (tagTHREADINFO *)a1,
                      (const struct tagINPUT_MESSAGE_SOURCE *)((char *)&v366 + 12));
                    tagTLBLOCK::_unnamed_type_list_::_unnamed_type_list_((tagTLBLOCK::_unnamed_type_list_ *)BugCheckParameter2);
                    v191 = v316;
                    if ( v316 )
                      Win32RawLockedItemBase<tagQMSG,0,1,1,1>::ManualLock<void>((ULONG_PTR)BugCheckParameter2, v316);
                    v192 = v190;
                    v11 = v301;
                    v193 = xxxImmProcessKey(*v301, *(struct tagWND **)&v292[4], v291, v192, (__int64)v297);
                    LOBYTE(v147) = v193;
                    v308 = v193;
                    v309 = v193;
                    if ( (v193 & 0x11) != 0 )
                    {
                      if ( v191 )
                      {
                        Win32RawLockedItemBase<tagQMSG,0,1,1,1>::UnlockWorker((ULONG_PTR)BugCheckParameter2);
                        v316 = 0;
                      }
                      Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
                      goto LABEL_51;
                    }
                    if ( v191 )
                      Win32RawLockedItemBase<tagQMSG,0,1,1,1>::UnlockWorker((ULONG_PTR)BugCheckParameter2);
                    Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
                  }
LABEL_418:
                  if ( !*(_DWORD *)v292 )
                    goto LABEL_432;
                  v293 = 1;
                  v148 = 0;
                  if ( (WORD2(v365) & 0x8000) == 0 )
                  {
                    v149 = *((_QWORD *)*v11 + 65);
                    *((_QWORD *)*v11 + 65) = *((_QWORD *)&v363 + 1);
                    v150 = v147 & 2;
                    tagTHREADINFO::UpdateInputSource(
                      (tagTHREADINFO *)a1,
                      (const struct tagINPUT_MESSAGE_SOURCE *)((char *)&v366 + 12));
                    *(_QWORD *)&v373[0] = 0;
                    v373[1] = 0;
                    *((_QWORD *)&v373[0] + 1) = v297;
                    *(_QWORD *)&v320 = (unsigned int)Feature_WebThreatDefenseToggle__private_featureState;
                    if ( (Feature_WebThreatDefenseToggle__private_featureState & 0x10) == 0 )
                    {
                      LODWORD(v320) = Feature_WebThreatDefenseToggle__private_featureState | 1;
                      wil_details_FeatureReporting_ReportUsageToService(
                        Feature_WebThreatDefenseToggle__private_descriptor,
                        v320,
                        3,
                        1);
                      wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
                        v320,
                        3,
                        Feature_WebThreatDefenseToggle__private_descriptor);
                    }
                    v151 = *(_QWORD *)(a1 + 1376);
                    v152 = *(_QWORD *)(a1 + 456);
                    v153 = *(unsigned int *)(v152 + 276);
                    if ( (v153 & 4) != 0
                      && (_DWORD)v151 == 1
                      && (v151 & 0x500000000LL) != 0
                      && *(_QWORD *)(a1 + 488) != *(_QWORD *)(W32GetUserSessionState(v152, v153) + 62744)
                      && CheckImEnabled() )
                    {
                      LOWORD(v373[1]) = 1;
                    }
                    tagTLBLOCK::_unnamed_type_list_::_unnamed_type_list_((tagTLBLOCK::_unnamed_type_list_ *)BugCheckParameter2);
                    v154 = v316;
                    if ( v316 )
                      Win32RawLockedItemBase<tagQMSG,0,1,1,1>::ManualLock<void>((ULONG_PTR)BugCheckParameter2, v316);
                    v148 = xxxCallCtfHook(2, v150, v298, v373);
                    if ( (BYTE2(v373[1]) & 1) != 0 )
                    {
                      if ( (*(_BYTE *)(*(_QWORD *)(a1 + 456) + 808LL) & 0x30) == 0x10 )
                        WORD1(v373[1]) |= 0x10u;
                      ProcessTranslatedChar((struct _CHARHOOKSTRUCT *)v373);
                    }
                    v11 = v301;
                    *((_QWORD *)*v301 + 65) = v149;
                    if ( !v154 )
                      goto LABEL_430;
                    if ( (unsigned int)(v148 - 2) > 1
                      || (*(_DWORD *)(a1 + 1360) & 0x20000000) != 0
                      || !AllocQEntryEx((char *)*v11 + 24, v154, 2) )
                    {
                      v316 = 0;
LABEL_430:
                      Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
                      NextSysMsg = v312;
                      goto LABEL_431;
                    }
                    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
                      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20000) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u )
                    {
                      v9 = 0;
                    }
                    if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
                      || (v204 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
                    {
                      v204 = 0;
                    }
                    if ( v9 || v204 )
                    {
                      v241 = *v11;
                      v242 = *((_QWORD *)*v11 + 11);
                      v243 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED);
                      LOBYTE(v244) = v204;
                      LOBYTE(v245) = v9;
                      WPP_RECORDER_AND_TRACE_SF_qqq(
                        *((_QWORD *)WPP_GLOBAL_Control + 3),
                        v245,
                        v244,
                        *(_QWORD *)(v243 + 69152),
                        5,
                        18,
                        35,
                        (__int64)WPP_49cdbed1bece331d44f23b214bd7a204_Traceguids,
                        v316,
                        (char)v241,
                        v242);
                      v11 = v301;
                    }
                    if ( v330 == -1 )
                    {
                      BugCheckParameter4 = PtiCurrent();
                      KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)BugCheckParameter2, 0, (ULONG_PTR)BugCheckParameter4);
                    }
                    *((_QWORD *)PtiCurrent() + 47) = BugCheckParameter2[0];
                    v330 = -1;
                    *((_QWORD *)*v11 + 11) = v316;
                    v9 = 1;
                    if ( v148 == 2 )
                    {
                      v205 = 1;
                      v302 = 1;
                    }
                    else
                    {
                      v205 = v302;
                      if ( v148 == 3 )
                        v205 = 2;
                      v302 = v205;
                    }
                    DeferSysPeekMsg(a1, v205);
                    v316 = 0;
                    Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
                    goto LABEL_23;
                  }
LABEL_431:
                  if ( v148 )
                  {
                    v29 = 1;
                    goto LABEL_52;
                  }
LABEL_432:
                  if ( ((*(_BYTE *)(a1 + 712) | *(_BYTE *)(**(_QWORD **)(a1 + 496) + 16LL)) & 8) == 0 )
                  {
                    v29 = v293;
LABEL_434:
                    if ( v29
                      && *(_DWORD *)v292
                      && ((*(_BYTE *)(a1 + 712) | *(_BYTE *)(**(_QWORD **)(a1 + 496) + 16LL)) & 0x40) != 0 )
                    {
                      xxxCallHook(7, v298, (__int64)v297, 5);
                    }
                    goto LABEL_198;
                  }
                  v29 = 1;
                  v293 = 1;
                  if ( !(unsigned int)xxxCallHook(*(_DWORD *)v292 == 0 ? 3 : 0, v298, (__int64)v297, 2) )
                    goto LABEL_434;
LABEL_52:
                  xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v359, 1);
                  if ( v307 )
                  {
                    if ( ((*(_BYTE *)(a1 + 712) | *(_BYTE *)(**(_QWORD **)(a1 + 496) + 16LL)) & 0x40) != 0 )
                      xxxCallHook(6, v291, (__int64)v370, 5);
                    v307 = 0;
                  }
                  if ( v29 )
                  {
                    if ( ((*(_BYTE *)(a1 + 712) | *(_BYTE *)(**(_QWORD **)(a1 + 496) + 16LL)) & 0x40) != 0 )
                      xxxCallHook(7, v298, (__int64)v297, 5);
                    v293 = 0;
                  }
                  v16 = FLOAT_1_0;
                  v11 = v301;
                  LOBYTE(i) = v294;
                  if ( *(_DWORD *)v292 )
                    goto LABEL_13;
                }
              }
              break;
            case 0x102:
              goto LABEL_364;
            case 0x104:
LABEL_350:
              if ( (_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 520), 0, 0) & 0x400) != 0
                && (int)CheckProcessForeground((struct tagTHREADINFO *)a1) < 0 )
              {
                goto LABEL_75;
              }
              v318 = 1;
              v298 = LOBYTE(v361[0]);
              if ( *(_DWORD *)v292 && (WORD2(v365) & 0x8000) != 0 )
              {
LABEL_353:
                if ( v298 == 231 )
                {
                  *(_WORD *)(a1 + 914) = WORD1(v361[0]);
                  v361[0] = 231;
                }
                goto LABEL_355;
              }
              if ( LOBYTE(v361[0]) != 18 )
                *((_DWORD *)*v11 + 127) &= 0xFFFFFFF3;
              if ( v298 != 44 )
              {
LABEL_527:
                if ( *(_DWORD *)(W32GetUserSessionState(i, v24) + 16256)
                  && (!*(_DWORD *)(W32GetUserSessionState(v182, v24) + 14652)
                   || (*(_BYTE *)(W32GetUserSessionState(v184, v183) + 14648) & 2) == 0) )
                {
                  v185 = *((_BYTE *)*v11 + 356);
                  v186 = v298 | 0x400;
                  if ( (v185 & 0x10) == 0 )
                    v186 = v298;
                  v187 = v186 | 0x200;
                  if ( (v185 & 4) == 0 )
                    v187 = v186;
                  v188 = v187;
                  LODWORD(v188) = v187 | 0x100;
                  if ( (v185 & 1) == 0 )
                    v188 = v187;
                  v189 = (_QWORD *)HotKeyToWindow(v188);
                  if ( v189 )
                  {
                    if ( *(_QWORD *)(a1 + 488) == *(_QWORD *)(v189[2] + 488LL) )
                    {
                      PostTransformableMessage(*((_QWORD *)*v11 + 16), 274, 61776, *v189, 0);
                      xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v359, 1);
                      goto LABEL_14;
                    }
                  }
                }
                goto LABEL_353;
              }
              i = 16;
              v233 = *((_BYTE *)*v11 + 356) & 0x10;
              if ( (!v233 || (*(_DWORD *)(a1 + 916) & 0x10) != 0) && (v233 || (*(_DWORD *)(a1 + 916) & 0x20) != 0) )
              {
                v11 = v301;
                goto LABEL_527;
              }
              xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v359, 1);
              if ( v233 || (v361[1] & 0xFF0000) == 0x10000 )
              {
                v11 = v301;
                if ( !*((_QWORD *)*v301 + 16) )
                  goto LABEL_14;
                CompositeAppFrameWindowOrSelf = CoreWindowProp::GetCompositeAppFrameWindowOrSelf(*((const struct tagWND **)*v301
                                                                                                 + 16));
              }
              else
              {
                CompositeAppFrameWindowOrSelf = *(struct tagWND **)(*(_QWORD *)(*(_QWORD *)(a1 + 488) + 8LL) + 24LL);
                v11 = v301;
              }
              if ( CompositeAppFrameWindowOrSelf )
              {
                v235 = v367 != 1;
                Win32HMThreadLockAlways<tagHOOK>::Win32HMThreadLockAlways<tagHOOK>(
                  v355,
                  a1,
                  CompositeAppFrameWindowOrSelf);
                xxxSnapWindow(CompositeAppFrameWindowOrSelf, v235);
                Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)v355);
                goto LABEL_846;
              }
              goto LABEL_14;
            case 0x105:
              goto LABEL_355;
            case 0x119:
              goto LABEL_106;
            default:
              goto LABEL_128;
          }
        }
        if ( LODWORD(v360[1]) != 522 && LODWORD(v360[1]) != 526 )
          break;
        if ( (_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 520), 0, 0) & 0x400) != 0
          && (int)CheckProcessForeground((struct tagTHREADINFO *)a1) < 0 )
        {
          goto LABEL_75;
        }
        if ( (unsigned int)IsInsideMenuLoop(a1) )
          goto LABEL_51;
        if ( (DWORD1(v365) & 0x100000) != 0 )
        {
          v155 = *((_QWORD *)*v11 + 15);
          *(_QWORD *)&v292[4] = v155;
        }
        else
        {
          if ( *(_QWORD *)&v292[4] && IsCompositionInputWindowForHitTest(*(struct tagWND **)&v292[4]) )
          {
            v195 = 1;
            if ( (unsigned int)CoreWindowProp::IsCompositeAppOrSelfDisabled(*(const struct tagWND **)&v292[4]) )
              goto LABEL_51;
            ThreadDesktopWindow = *(_QWORD *)&v292[4];
          }
          else
          {
            ThreadDesktopWindow = GetThreadDesktopWindow(0);
            *(_QWORD *)&v292[4] = ThreadDesktopWindow;
            v195 = 0;
          }
          Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(v356, ThreadDesktopWindow);
          v196 = xxxDCEWindowHitTest(*(_QWORD *)&v292[4], 512, v361[0], v361[1], *(_QWORD *)v364, &v299, 4 * v195 + 9);
          LOBYTE(v197) = 1;
          *(_QWORD *)&v292[4] = HMValidateHandleNoSecure(v196, v197);
          LOBYTE(v198) = 1;
          v199 = (struct tagWND *)HMValidateHandleNoSecure(v196, v198);
          InputTraceLogging::Mouse::SecondaryHitTest((const struct tagQMSG *)&v359, v364, v199);
          Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)v356);
          v155 = *(_QWORD *)&v292[4];
          v11 = v301;
        }
        if ( !v155 )
          goto LABEL_51;
        Win32HM_ExchangeThreadLock<1>(v155, v331);
        v156 = *(_QWORD *)(*(_QWORD *)&v292[4] + 16LL);
        v300 = v156 != v338;
        if ( v156 != v332 )
        {
          v179 = *(_QWORD *)(*(_QWORD *)&v292[4] + 16LL);
          if ( *(struct tagQ **)(v179 + 464) != *v11 )
            goto LABEL_51;
          if ( !v328 )
          {
            v328 = *(struct _W32THREAD **)(*(_QWORD *)&v292[4] + 16LL);
            Win32RawLockedW32Thread::Exchange((Win32RawLockedW32Thread *)v351, (struct _W32THREAD *)v179);
          }
        }
        v88 = v303;
        v157 = MiPCheckMsgFilter(NextSysMsg, v291, v303, a5);
        LOBYTE(i) = v294;
        if ( v157 )
        {
          v158 = *(struct tagWND **)&v292[4];
          v159 = CheckPwndFilter(*(_QWORD *)&v292[4], v317);
          LOBYTE(i) = v294;
          if ( v159 )
          {
            if ( v300 )
              goto LABEL_75;
            if ( NextSysMsg && (unsigned int)IsMiPActive(a1, NextSysMsg) )
            {
              if ( _bittest((const signed __int32 *)NextSysMsg + 25, 0xAu) )
              {
                memset_0(v373, 0, 0xA8u);
                if ( ShouldGenerateMipMessage((struct tagTHREADINFO *)a1, NextSysMsg, v158, *(int *)v292)
                  && GeneratePointerMessageFromMouse((struct tagQMSG *)v373, v291, NextSysMsg, v158, v252) )
                {
                  v359 = v373[0];
                  *(_OWORD *)v360 = v373[1];
                  *(_OWORD *)v361 = v373[2];
                  v362 = v374;
                  v363 = v375;
                  *(_OWORD *)&v364[0].x = v376;
                  v365 = v377;
                  v366 = v378;
                  v367 = v379;
                  v368 = v380;
                  v369 = v381;
                  v25 = 1;
                  v310 = 1;
                  if ( *(_DWORD *)v292 )
                    *((_DWORD *)NextSysMsg + 25) &= ~0x400u;
                  goto LABEL_211;
                }
                if ( !*(_DWORD *)v292 )
                  goto LABEL_452;
                *((_DWORD *)NextSysMsg + 25) &= ~0x400u;
              }
              else
              {
                if ( !*(_DWORD *)v292 )
                {
LABEL_452:
                  MouseKeyFlags = GetMouseKeyFlags(*(_QWORD *)(a1 + 464));
                  v298 = v361[0] | MouseKeyFlags;
                  v297 = (void *)v361[1];
                  v296.x = SLOWORD(v361[1]);
                  v296.y = SWORD1(v361[1]);
                  PhysicalToLogicalDPIPointWithHitTest(&v296, &v296, 0, *(const struct tagWND **)&v292[4]);
                  v297 = (void *)((LOWORD(v296.y) << 16) | LOWORD(v296.x));
                  *(struct tagPOINT *)((char *)&v362 + 4) = v296;
                  v370[0] = (__int64)v296;
                  if ( *(_QWORD *)&v292[4] )
                    v370[1] = **(_QWORD **)&v292[4];
                  else
                    v370[1] = 0;
                  LODWORD(v371) = 0;
                  *((_QWORD *)&v371 + 1) = *((_QWORD *)&v363 + 1);
                  LODWORD(v372) = v361[0];
                  if ( *(_DWORD *)v292 )
                  {
                    v307 = 1;
                    if ( (unsigned int)xxxCallCtfHook(7, 0, v291, v370) )
                      goto LABEL_51;
                  }
                  if ( ((*(_DWORD *)(a1 + 712) | *(_DWORD *)(**(_QWORD **)(a1 + 496) + 16LL)) & 0x100) != 0 )
                  {
                    v307 = 1;
                    if ( (unsigned int)xxxCallMouseHook(v291, v370, *(unsigned int *)v292) )
                      goto LABEL_51;
                  }
                  if ( (unsigned int)PsGetWin32KFilterSet() == 5 )
                  {
                    v255 = *((_QWORD *)PtiCurrent() + 64);
                    v304 = 0;
                    v304 = *(_QWORD *)(v255 + 248) != 0;
                    if ( v304 )
                    {
                      if ( xxxClientCallLocalMouseHooks(v291, (__int64)v370, *(int *)v292) )
                        goto LABEL_51;
                    }
                  }
                  if ( v307
                    && *(_DWORD *)v292
                    && ((*(_BYTE *)(a1 + 712) | *(_BYTE *)(**(_QWORD **)(a1 + 496) + 16LL)) & 0x40) != 0 )
                  {
                    xxxCallHook(6, v291, (__int64)v370, 5);
                  }
LABEL_198:
                  if ( *(_QWORD *)(a1 + 788) != *(_QWORD *)((char *)&v362 + 4) )
                    _InterlockedOr((volatile signed __int32 *)(a1 + 520), 0x100000u);
                  if ( NextSysMsg && ((BYTE4(v365) & 0x20) != 0 || (DWORD1(v365) & 0x8000000) != 0) )
                  {
                    if ( *((_DWORD *)NextSysMsg + 6) == 512 )
                    {
                      if ( *(_QWORD *)&v292[4] )
                        v119 = **(_QWORD **)&v292[4];
                      else
                        v119 = 0;
                      *((_QWORD *)NextSysMsg + 2) = v119;
                      *((_DWORD *)NextSysMsg + 25) |= 0x200u;
                    }
                    *((_QWORD *)NextSysMsg + 8) = v297;
                  }
                  *(_DWORD *)(a1 + 788) = DWORD1(v362);
                  v82 = v335;
                  *(_DWORD *)(v335 + 792) = DWORD2(v362);
                  *(_DWORD *)(v82 + 796) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)&v292[4] + 40LL) + 288LL);
                  *(struct tagPOINT *)(a1 + 800) = v364[0];
                  *(_DWORD *)(a1 + 600) = v362;
                  *(_QWORD *)(*(_QWORD *)(a1 + 464) + 520LL) = *((_QWORD *)&v363 + 1);
                  if ( v291 == 514 || v291 == 162 )
                    *(struct tagPOINT *)(a1 + 808) = v364[0];
                  *(_QWORD *)(*(_QWORD *)(a1 + 464) + 80LL) = 1;
                  *(_QWORD *)(a1 + 608) = 1;
                  tagTHREADINFO::UpdateLastInputData((tagTHREADINFO *)a1, (const struct tagQMSG *)&v359);
                  **(_DWORD **)(a1 + 480) &= ~8u;
                  **(_QWORD **)(a1 + 512) &= 0x7FFFFFFFuLL;
                  v83 = v308;
                  v84 = v336;
                  if ( *(_DWORD *)v292 )
                  {
                    v107 = *(_QWORD **)(a1 + 512);
                    if ( (BYTE4(v365) & 1) != 0 )
                      *v107 |= 0x1000uLL;
                    else
                      *v107 &= ~0x1000uLL;
                  }
                  TransferWakeBit(a1, v291);
                  v85 = *(_QWORD *)(a1 + 464);
                  if ( !*(_DWORD *)(v85 + 40) )
                    _InterlockedAnd(
                      (volatile signed __int32 *)(*(_QWORD *)(a1 + 480) + 8LL),
                      (*(_DWORD *)(v85 + 508) >> 4) & 2 | 0xFFFF83F8);
                  v86 = *(_DWORD *)v292;
                  if ( *(_DWORD *)v292 )
                  {
                    if ( v310 )
                    {
                      v105 = *(_DWORD **)(a1 + 1512);
                      if ( v105 )
                      {
                        if ( (*v105 & 1) != 0 && (*v105 & 4) != 0 )
                        {
                          SetMiPWakeBit((struct tagTHREADINFO *)a1);
                          v86 = *(_DWORD *)v292;
                        }
                      }
                    }
                  }
                  v87 = 0;
                  if ( *(_QWORD *)&v292[4] )
                    v87 = **(_QWORD **)&v292[4];
                  *(_QWORD *)v347 = v87;
                  *((_DWORD *)v84 + 2) = v291;
                  v41 = v298;
                  if ( (v83 & 2) != 0 )
                    v41 = 229;
                  *((_QWORD *)v84 + 2) = v41;
                  *((_QWORD *)v84 + 3) = v297;
                  *((_DWORD *)v84 + 8) = v362;
                  *(_QWORD *)((char *)v84 + 36) = *(_QWORD *)((char *)&v362 + 4);
                  InputTraceLogging::Delivery::ScanSysQueue(
                    (const struct tagQMSG *)&v359,
                    v84,
                    (const struct tagTHREADINFO *)a1,
                    v86 != 0);
                  if ( *(_DWORD *)v292 )
                  {
                    EtwTraceInputProcessDelay(a1);
                    *(_DWORD *)(*(_QWORD *)(a1 + 464) + 528LL) = (MEMORY[0xFFFFF78000000320]
                                                                * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
                  }
                  EtwTraceRetrieveInputMessage(v84);
                  if ( v306[0] )
                  {
                    v42 = PtiCurrent();
                    *((_QWORD *)v42 + 170) &= ~0x1000000000uLL;
                  }
                  Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)v331);
                  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v353);
                  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v354);
                  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v352);
                  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v350);
                  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v351);
                  return 1;
                }
                if ( (unsigned int)IsMiPMouseMessage(*((unsigned int *)NextSysMsg + 6)) )
                {
                  if ( (unsigned int)IsGenuineMouseInput((char *)NextSysMsg + 124) )
                  {
                    v253 = *(_DWORD **)(a1 + 1512);
                    if ( v253 )
                    {
                      if ( (*v253 & 2) == 0 && (*v253 & 4) == 0 )
                        goto LABEL_681;
                    }
                  }
                  v254 = *(_DWORD **)(a1 + 1512);
                  if ( v254 )
                    *v254 &= ~2u;
                }
              }
            }
            if ( *(_DWORD *)v292 )
              xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v359, 1);
            goto LABEL_452;
          }
          v11 = v301;
        }
      }
      switch ( LODWORD(v360[1]) )
      {
        case 0x238:
          goto LABEL_110;
        case 0x240:
LABEL_106:
          if ( !*(_QWORD *)&v292[4] )
            goto LABEL_51;
          v43 = *(char **)(*(_QWORD *)&v292[4] + 40LL);
          if ( v43[20] < 0 || v43[19] < 0 || (v43[31] & 0x18) != 0x10 )
            goto LABEL_51;
          goto LABEL_110;
        case 0x245:
        case 0x246:
        case 0x247:
        case 0x249:
          goto LABEL_210;
      }
LABEL_128:
      v296.x = SLOWORD(v361[1]);
      v296.y = SWORD1(v361[1]);
      v299 = 1;
      if ( (BYTE4(v365) & 0x20) == 0 && (DWORD1(v365) & 0x8000000) == 0
        || !*(_QWORD *)&v292[4]
        || (((unsigned __int16)(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)&v292[4] + 40LL) + 288LL) >> 8)
           ^ (unsigned __int16)(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v292[4] + 16LL) + 456LL) + 268LL) >> 8))
          & 0x1FF) != 0 )
      {
        if ( !*(_QWORD *)&v292[4]
          || (v134 = IsCompositionInputWindowForHitTest(*(struct tagWND **)&v292[4]), v49 = 1, !v134) )
        {
          v49 = 0;
        }
        v311 = v49;
        v50 = *(_QWORD *)(a1 + 464);
        v51 = *(HWND **)(v50 + 112);
        if ( v51 )
        {
          *(_QWORD *)&v292[4] = *(_QWORD *)(v50 + 112);
          InputTraceLogging::Mouse::RedirectForCapture((const struct tagQMSG *)&v359, *v51);
        }
        else
        {
          Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(v348);
          if ( v54 )
          {
            v55 = *(struct tagWND **)&v292[4];
          }
          else
          {
            v55 = *(struct tagWND **)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v53, v52) + 18752)
                                                            + 488LL)
                                                + 8LL)
                                    + 24LL);
            Win32HM_LockIntoThread<1>(a1, v55, v348);
          }
          if ( (unsigned int)IsThreadDesktopComposed((const struct tagTHREADINFO *)a1) )
          {
            *(_QWORD *)&v373[0] = LODWORD(v360[1]);
            *((_QWORD *)&v373[0] + 1) = v361[0];
            *(_QWORD *)&v373[1] = v361[1];
            *((_QWORD *)&v373[1] + 1) = &v299;
            LODWORD(v373[2]) = v56;
            BYTE4(v373[2]) = 0;
            *(_WORD *)((char *)&v373[2] + 5) = 0;
            BYTE7(v373[2]) = 0;
            *((_QWORD *)&v373[2] + 1) = &v364[1];
            v374 = 0u;
            v58 = xxxDCEWindowHitTestIndirect(v55, v364[0], 0, (struct tagDCE_WINDOW_HIT_TEST_ARGS *)v373);
            if ( v58 && (_BYTE)v374 )
            {
              v361[1] = *(_QWORD *)&v373[1];
              DWORD1(v362) = SLOWORD(v373[1]);
              v57 = *(_QWORD *)&v373[1] >> 16;
              DWORD2(v362) = SWORD1(v373[1]);
              v296 = *(struct tagPOINT *)((char *)&v362 + 4);
            }
          }
          else
          {
            v58 = (HWND)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))xxxWindowHitTest)(v55, v296, &v299);
          }
          LOBYTE(v57) = 1;
          v59 = (struct tagWND *)HMValidateHandleNoSecure(v58, v57);
          InputTraceLogging::Mouse::SecondaryHitTest((const struct tagQMSG *)&v359, &v296, v59);
          if ( !v311 )
            Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)v348);
          LOBYTE(v60) = 1;
          *(_QWORD *)&v292[4] = HMValidateHandleNoSecure(v58, v60);
          if ( !*(_QWORD *)&v292[4] )
          {
            v256 = *(_QWORD *)(*(_QWORD *)(a1 + 488) + 8LL);
            *(_QWORD *)&v292[4] = *(_QWORD *)(v256 + 24);
            if ( !*(_QWORD *)&v292[4] )
              *(_QWORD *)&v292[4] = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v256, v61)
                                                                                  + 18752)
                                                                      + 488LL)
                                                          + 8LL)
                                              + 24LL);
          }
          v62 = 0;
          if ( !*(_QWORD *)(a1 + 640) )
          {
            if ( (unsigned int)IsMiPEnabledForThread(a1) )
            {
              v63 = *(_QWORD *)(*(_QWORD *)(a1 + 464) + 560LL);
              if ( v63 )
              {
                v257 = ValidateHwnd(v63);
                if ( v257 )
                {
                  v258 = *(_QWORD *)(a1 + 464);
                  v259 = *(_QWORD *)(v257 + 16);
                  if ( *(_QWORD *)(v259 + 464) == v258 || *(_QWORD *)(v259 + 456) == *(_QWORD *)(a1 + 456) )
                  {
                    *(_QWORD *)&v292[4] = v257;
                    v299 = 1;
                    *(_DWORD *)(v258 + 156) = 0;
                    v62 = 1;
                  }
                }
              }
            }
          }
          if ( !v62 )
            *(_DWORD *)(*(_QWORD *)(v335 + 464) + 156LL) = v299 != 1;
          Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)v348);
        }
        if ( *(_QWORD *)&v292[4] == *(_QWORD *)(*(_QWORD *)(a1 + 464) + 112LL) )
        {
          v135 = PtiMouseFromQ(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v292[4] + 16LL) + 464LL));
          if ( (((unsigned __int16)(*(_DWORD *)(*((_QWORD *)v136 + 5) + 288LL) >> 8)
               ^ (unsigned __int16)(*(_DWORD *)(*(_QWORD *)(v135 + 456) + 268LL) >> 8))
              & 0x1FF) != 0
            || (unsigned int)IsOleDragDropCaptureWindow(v136) )
          {
            v296 = v364[0];
            v137 = 0;
            TopLevelOrDpiBoundaryWindow = GetTopLevelOrDpiBoundaryWindow(*(const struct tagWND **)&v292[4]);
            v142 = TopLevelOrDpiBoundaryWindow;
            if ( TopLevelOrDpiBoundaryWindow
              && (unsigned int)IsWindowDesktopComposed(TopLevelOrDpiBoundaryWindow, v139, v140, v141) )
            {
              v137 = (float *)*((_QWORD *)v142 + 27);
            }
            if ( v137 )
            {
              v210 = v16 / v137[5];
              v296.x = (int)(float)((float)((float)(FixedPointSubPixel(v364[1].x) + (float)v296.x) - v137[12])
                                  * (float)(v16 / *v137));
              v296.y = (int)(float)((float)((float)(FixedPointSubPixel(v364[1].y) + (float)v296.y) - v137[13]) * v210);
            }
            if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80000) == 0
              || (v143 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
            {
              v143 = 0;
            }
            if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
              || (v144 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
            {
              v144 = 0;
            }
            if ( v143 || v144 )
            {
              v260 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED);
              LOBYTE(v261) = v144;
              LOBYTE(v262) = v143;
              WPP_RECORDER_AND_TRACE_SF_dddd(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v262,
                v261,
                *(_QWORD *)(v260 + 69152),
                5,
                20,
                34,
                (__int64)WPP_49cdbed1bece331d44f23b214bd7a204_Traceguids,
                v364[0].x,
                v364[0].y,
                v296.x,
                v296.y);
            }
            v297 = (void *)((LOWORD(v296.y) << 16) | LOWORD(v296.x));
            *(struct tagPOINT *)((char *)&v362 + 4) = v296;
            NextSysMsg = v312;
          }
        }
      }
      Win32HM_ExchangeThreadLock<1>(*(_QWORD *)&v292[4], v331);
      if ( CheckCrossThreadInput(*(struct tagWND *const *)&v292[4], NextSysMsg, &v300, (int *)v292, v313) )
        goto LABEL_75;
      if ( v300 )
      {
        v263 = *(_QWORD *)(*(_QWORD *)&v292[4] + 16LL);
        if ( *(_QWORD *)(v263 + 464) != *(_QWORD *)(a1 + 464) )
          goto LABEL_799;
        if ( !v314 )
        {
          v314 = *(_QWORD *)(*(_QWORD *)&v292[4] + 16LL);
          v334 = v263;
          Win32RawLockedW32Thread::Exchange((Win32RawLockedW32Thread *)v350, (struct _W32THREAD *)v263);
        }
      }
      else if ( (WORD2(v365) & 0x800) != 0
             && !UIPrivilegeIsolation::CheckAccess(
                   (UIPrivilegeIsolation *)&v366,
                   (const struct tagUIPI_INFO *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v292[4] + 16LL) + 456LL) + 864LL),
                   v65) )
      {
        EtwTraceUIPIMsgError(0, *(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v292[4] + 16LL) + 456LL), v291, v361[0], v361[1]);
LABEL_799:
        v264 = W32GetUserSessionState(v64, v263);
        zzzSetCursor(*(struct tagCURSOR **)(v264 + 21712));
        goto LABEL_51;
      }
      v66 = v296;
      v67 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v292[4] + 16LL) + 464LL);
      v68 = *(_DWORD *)(v67 + 156);
      if ( v68 && (v69 = (unsigned int)(v68 - 2), (_DWORD)v69) )
      {
        if ( (_DWORD)v69 != 1 )
          goto LABEL_153;
        v265 = *(_QWORD *)(*(_QWORD *)&v292[4] + 40LL);
        if ( (*(_BYTE *)(v265 + 26) & 0x40) != 0 )
          v266 = *(_DWORD *)(v265 + 96) - v296.x;
        else
          v266 = v296.x - *(_DWORD *)(v265 + 88);
        v296.x = v266;
        v67 = (unsigned int)(v296.y - *(_DWORD *)(*(_QWORD *)(*(_QWORD *)&v292[4] + 40LL) + 92LL));
      }
      else
      {
        v69 = *(_QWORD *)&v292[4];
        v108 = *(_QWORD *)(*(_QWORD *)&v292[4] + 40LL);
        if ( (*(_BYTE *)(v108 + 26) & 0x40) != 0 )
          v109 = *(_DWORD *)(v108 + 112) - v296.x;
        else
          v109 = v296.x - *(_DWORD *)(v108 + 104);
        v296.x = v109;
        v67 = (unsigned int)(v296.y - *(_DWORD *)(*(_QWORD *)(*(_QWORD *)&v292[4] + 40LL) + 108LL));
      }
      v296.y = v67;
LABEL_153:
      if ( !v300 && *(_QWORD *)(a1 + 464) == *(_QWORD *)(W32GetUserSessionState(v67, v69) + 19248) )
      {
        v93 = *(_QWORD *)(*(_QWORD *)(a1 + 488) + 192LL) != *(_QWORD *)&v292[4];
        if ( (unsigned int)Feature_UserModeNonClientScrollBars2__private_IsEnabledDeviceUsageNoInline()
          && Scrollbar::NonClient::UserModeSupportsUserModeScrollBars(v94) )
        {
          v95 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))xxxFindNCHitEx)(
                  *(_QWORD *)&v292[4],
                  (unsigned int)v299,
                  v296);
        }
        else
        {
          v95 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))FindNCHitEx)(
                  *(_QWORD *)&v292[4],
                  (unsigned int)v299,
                  v296);
        }
        if ( v291 != 512 || v93 || *(_DWORD *)(*(_QWORD *)(a1 + 488) + 200LL) != v95 )
          xxxTrackMouseMove(*(struct tagDESKTOP **)&v292[4], (struct tagWND *)v95);
        if ( !v93 )
        {
          v96 = *(_QWORD *)(a1 + 488);
          if ( (*(_DWORD *)(v96 + 48) & 0x40) != 0
            && (v291 != 512 || !(unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD))PtInRect)(v96 + 204, v66)) )
          {
            ResetMouseHover((struct tagDESKTOP *)v96, v66);
          }
        }
        NextSysMsg = v312;
      }
      v70 = CheckPwndFilter(*(_QWORD *)&v292[4], v317);
      v11 = v301;
      LOBYTE(i) = v294;
      if ( v70 )
      {
        v72 = 0;
        LODWORD(v320) = 0;
        switch ( v291 )
        {
          case 0x201u:
            v45 = (unsigned __int8)IsMessageInputSourceTouch(&v359) == 0;
            v200 = *(_QWORD *)(a1 + 464);
            if ( v45 )
              *(_DWORD *)(v200 + 508) &= ~0x800000u;
            else
              *(_DWORD *)(v200 + 508) |= 0x800000u;
            v201 = IsMessageInputSourcePen(&v359);
            v71 = *(_QWORD *)(v335 + 464);
            v202 = *(_DWORD *)(v71 + 508);
            if ( v201 )
              v173 = v202 | 0x1000000;
            else
              v173 = v202 & 0xFEFFFFFF;
            *(_DWORD *)(v71 + 508) = v173;
LABEL_497:
            if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v292[4] + 136LL) + 8LL) + 8LL) & 8) != 0
              || *(_DWORD *)(*(_QWORD *)(a1 + 464) + 156LL) == 1
              || (unsigned int)IsMenuStarted(a1) )
            {
              v72 = 1;
              LODWORD(v320) = 1;
              v174 = *(_QWORD *)(a1 + 464);
              if ( (unsigned int)v362 <= *(_DWORD *)(v174 + 168)
                && !*(_DWORD *)(W32GetUserSessionState(v174, v71) + 16216) )
              {
                v268 = *(_QWORD *)&v292[4] ? **(_QWORD **)&v292[4] : 0LL;
                v269 = *(_QWORD *)(a1 + 464);
                if ( v268 == *(_QWORD *)(v269 + 176)
                  && v291 == *(_DWORD *)(v269 + 160)
                  && (v291 != 523 || WORD1(v361[0]) == *(_WORD *)(v269 + 164)) )
                {
                  v271 = *(int *)(*(_QWORD *)(W32GetUserSessionState(v269, v267) + 19704) + 2040LL);
                  v270 = HIDWORD(v271);
                  LODWORD(v270) = v271 % 2;
                  v342 = *(_DWORD *)(*(_QWORD *)(a1 + 464) + 184LL) - v271 / 2;
                  v273 = *(int *)(*(_QWORD *)(W32GetUserSessionState(v342, v270) + 19704) + 2044LL);
                  v272 = HIDWORD(v273);
                  LODWORD(v272) = v273 % 2;
                  v343 = *(_DWORD *)(*(_QWORD *)(a1 + 464) + 188LL) - v273 / 2;
                  v274 = W32GetUserSessionState(v343, v272);
                  v275 = *(_QWORD *)(a1 + 464);
                  LODWORD(v276) = *(int *)(*(_QWORD *)(v274 + 19704) + 2040LL) >> 31;
                  LODWORD(v274) = *(_DWORD *)(*(_QWORD *)(v274 + 19704) + 2040LL);
                  v276 = (unsigned int)v276;
                  v277 = __SPAIR64__(v276, v274) % 2;
                  LODWORD(v274) = __SPAIR64__(v276, v274) / 2;
                  LODWORD(v276) = v277;
                  v344 = *(_DWORD *)(v275 + 184) + v274;
                  v345 = *(_DWORD *)(*(_QWORD *)(a1 + 464) + 188LL)
                       + *(_DWORD *)(*(_QWORD *)(W32GetUserSessionState(v275, v276) + 19704) + 2044LL) / 2;
                  if ( (unsigned int)PtInRect(&v342, *(_QWORD *)((char *)&v362 + 4)) )
                  {
                    v291 += 2;
                    v72 = 2;
                    LODWORD(v320) = 2;
                  }
                }
              }
            }
LABEL_499:
            v175 = *(_QWORD *)(a1 + 464);
            v176 = *(_DWORD *)(v175 + 508);
            if ( (v176 & 8) != 0 )
              *(_DWORD *)(v175 + 508) = v176 | 4;
            if ( v291 - 514 <= 0xA )
            {
              v177 = 1097;
              if ( _bittest(&v177, v291 - 514) )
              {
                if ( *(_DWORD *)(*(_QWORD *)(a1 + 464) + 168LL) && ((HIDWORD(v366) - 4) & 0xFFFFFFFB) == 0 )
                {
                  if ( HIDWORD(v366) == 4 )
                    TouchTimeFromCPLValue = GetTouchTimeFromCPLValue(300, 180, 5, 1);
                  else
                    TouchTimeFromCPLValue = GetPenDoubleClickTime();
                  *(_DWORD *)(*(_QWORD *)(a1 + 464) + 168LL) = v369 + TouchTimeFromCPLValue;
                }
              }
            }
            break;
          case 0x202u:
            goto LABEL_499;
          case 0x204u:
            goto LABEL_497;
          case 0x205u:
            goto LABEL_499;
          case 0x207u:
            goto LABEL_497;
          case 0x208u:
            goto LABEL_499;
          case 0x20Bu:
            goto LABEL_497;
          case 0x20Cu:
            goto LABEL_499;
        }
        if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v292[4] + 16LL) + 464LL) + 156LL) == 1 )
        {
          v291 -= 352;
          v298 = (unsigned int)v299;
        }
        v73 = MiPCheckMsgFilter(NextSysMsg, v291, v303, a5);
        v11 = v301;
        LOBYTE(i) = v294;
        if ( v73 )
        {
          if ( v300 )
            goto LABEL_75;
          if ( v291 - 512 > 0xE )
            break;
          v106 = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 520), 0, 0);
          LOBYTE(i) = v294;
          if ( (v106 & 0x8000) == 0 )
            break;
        }
      }
    }
    if ( (_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 520), 0, 0) & 0x100000) != 0 )
    {
      _InterlockedAnd((volatile signed __int32 *)(a1 + 520), 0xFFEFFFFF);
      xxxWindowEvent(0x800Bu, 0, -9, 0, 1);
    }
    v370[0] = *(_QWORD *)((char *)&v362 + 4);
    if ( *(_QWORD *)&v292[4] )
      v370[1] = **(_QWORD **)&v292[4];
    else
      v370[1] = 0;
    LODWORD(v371) = v299;
    *((_QWORD *)&v371 + 1) = *((_QWORD *)&v363 + 1);
    LODWORD(v372) = v361[0];
    if ( *(_DWORD *)v292 )
    {
      if ( v291 != 512 && v291 != 160 )
      {
        v307 = 1;
        if ( (unsigned int)xxxCallCtfHook(7, 0, v291, v370) )
          goto LABEL_51;
      }
    }
    if ( ((*(_DWORD *)(a1 + 712) | *(_DWORD *)(**(_QWORD **)(a1 + 496) + 16LL)) & 0x100) != 0 )
    {
      v307 = 1;
      if ( (unsigned int)xxxCallMouseHook(v291, v370, *(unsigned int *)v292) )
        goto LABEL_51;
    }
    if ( (unsigned int)PsGetWin32KFilterSet() == 5 )
    {
      v278 = *((_QWORD *)PtiCurrent() + 64);
      v305 = 0;
      v305 = *(_QWORD *)(v278 + 248) != 0;
      if ( v305 )
      {
        if ( xxxClientCallLocalMouseHooks(v291, (__int64)v370, *(int *)v292) )
          goto LABEL_51;
      }
    }
    if ( (*(_DWORD *)(a1 + 1360) & 0x2000LL) == 0 && (!v299 || v299 == -2) )
    {
      v181 = 0;
      if ( v311 )
      {
        v280 = (unsigned int)IsIndependentInputWindow(*(const struct tagWND **)&v292[4])
             ? GetCompositionInputWindowUIOwner(v279)
             : *(struct tagWND **)&v292[4];
        TopLevelWindow = (const struct tagWND *)GetTopLevelWindow(v280);
        v181 = TopLevelWindow;
        if ( TopLevelWindow )
        {
          v181 = CoreWindowProp::GetCompositeAppFrameWindowOrSelf(TopLevelWindow);
          Win32HMOptionalThreadLock<tagWND>::Win32HMOptionalThreadLock<tagWND>(v357, a1, v181);
          v282 = 0;
          if ( v181 )
            v282 = *(_QWORD *)v181;
          xxxSendMessage(v181, 32, v282, (unsigned __int16)v299 | (LOWORD(v360[1]) << 16));
          Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)v357);
        }
      }
      if ( !v181 )
      {
        if ( *(_QWORD *)&v292[4] )
          v283 = **(_QWORD **)&v292[4];
        else
          v283 = 0;
        xxxSendMessage(*(_QWORD *)&v292[4], 32, v283, (unsigned __int16)v299 | (LOWORD(v360[1]) << 16));
      }
      if ( *(struct tagQMSG **)(*(_QWORD *)(a1 + 464) + 88LL) == NextSysMsg
        && NextSysMsg
        && (unsigned int)IsMiPActive(a1, NextSysMsg)
        && (*((_DWORD *)NextSysMsg + 25) & 0x400) != 0
        && (unsigned int)IsGenuineMouseInput((char *)NextSysMsg + 124)
        && (unsigned int)IsMiPMouseMessage(*((unsigned int *)NextSysMsg + 6)) )
      {
        memset_0(v373, 0, 0xA8u);
        GeneratePointerMessageFromMouse(
          (struct tagQMSG *)v373,
          v291,
          NextSysMsg,
          *(struct tagWND **)&v292[4],
          *(int *)v292);
        SetMiPPromotion(*(_QWORD *)(*(_QWORD *)&v292[4] + 16LL), DWORD2(v373[1]));
      }
      goto LABEL_51;
    }
    if ( *(struct tagQMSG **)(*(_QWORD *)(a1 + 464) + 88LL) != NextSysMsg )
      goto LABEL_75;
    memset_0(v373, 0, 0x60u);
    v76 = v373[0];
    v77 = v373[1];
    v78 = v373[2];
    v79 = v374;
    v320 = v375;
    *(_OWORD *)BugCheckParameter2 = v376;
    v80 = 0;
    v382 = v359;
    v383 = *(_OWORD *)v360;
    v384 = *(_OWORD *)v361;
    v385 = v362;
    v386 = v363;
    v387 = *(_OWORD *)&v364[0].x;
    v388 = v365;
    v389 = v366;
    v390 = v367;
    v391 = v368;
    v392 = v369;
    if ( NextSysMsg && (unsigned int)IsMiPActive(a1, NextSysMsg) )
    {
      DWORD2(v383) = v291;
      *(_QWORD *)&v384 = v298;
      if ( (*((_DWORD *)NextSysMsg + 25) & 0x400) != 0 )
      {
        memset_0(v373, 0, 0xA8u);
        if ( ShouldGenerateMipMessage((struct tagTHREADINFO *)a1, NextSysMsg, *(struct tagWND **)&v292[4], *(int *)v292) )
        {
          v81 = *(_QWORD *)(a1 + 1512);
          if ( v81 && (*(_DWORD *)v81 & 1) != 0 )
          {
            v76 = *(_OWORD *)(v81 + 24);
            v77 = *(_OWORD *)(v81 + 40);
            v78 = *(_OWORD *)(v81 + 56);
            v79 = *(_OWORD *)(v81 + 72);
            v320 = *(_OWORD *)(v81 + 88);
            *(_OWORD *)BugCheckParameter2 = *(_OWORD *)(v81 + 104);
            v80 = 1;
          }
          if ( GeneratePointerMessageFromMouse(
                 (struct tagQMSG *)v373,
                 v291,
                 NextSysMsg,
                 *(struct tagWND **)&v292[4],
                 *(int *)v292) )
          {
            v359 = v373[0];
            *(_OWORD *)v360 = v373[1];
            *(_OWORD *)v361 = v373[2];
            v362 = v374;
            v363 = v375;
            *(_OWORD *)&v364[0].x = v376;
            v365 = v377;
            v366 = v378;
            v367 = v379;
            v368 = v380;
            v369 = v381;
            v25 = 1;
            v310 = 1;
            v161 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v373[1], 8));
            if ( v161 == 582 && (unsigned int)IsMiPEnabledForWindow(*(_QWORD *)&v292[4]) )
            {
              if ( v75 )
                v75 = **(_QWORD **)&v292[4];
              else
                v75 = 0;
              *(_QWORD *)(*(_QWORD *)(a1 + 464) + 560LL) = v75;
            }
            else if ( ((v161 - 579) & 0xFFFFFFFB) == 0 )
            {
              *(_QWORD *)(*(_QWORD *)(a1 + 464) + 560LL) = 0;
            }
          }
        }
        if ( *(_DWORD *)v292 )
        {
          *((_DWORD *)NextSysMsg + 25) &= ~0x400u;
          goto LABEL_189;
        }
LABEL_190:
        v9 = 1;
        goto LABEL_191;
      }
      if ( !*(_DWORD *)v292 )
        goto LABEL_190;
      if ( (unsigned int)IsMiPMouseMessage(*((unsigned int *)NextSysMsg + 6)) )
      {
        if ( (unsigned int)IsGenuineMouseInput((char *)NextSysMsg + 124) )
        {
          v120 = *(unsigned int **)(a1 + 1512);
          if ( v120 )
          {
            v75 = *v120;
            if ( (v75 & 2) == 0 && (v75 & 4) == 0 )
            {
              v9 = 1;
              xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v359, 1);
              goto LABEL_845;
            }
          }
        }
        v121 = *(_DWORD **)(a1 + 1512);
        if ( v121 )
          *v121 &= ~2u;
      }
    }
LABEL_189:
    if ( !*(_DWORD *)v292 )
      goto LABEL_190;
    v123 = W32GetUserSessionState(v75, v74);
    if ( DWORD2(v383) == 512 || DWORD2(v383) == 160 )
    {
      v124 = *(_QWORD *)&v292[4] ? **(_QWORD **)&v292[4] : 0LL;
      if ( v124 != *(_QWORD *)(v123 + 16288) && (unsigned int)IsGenuineMouseInput((char *)NextSysMsg + 124) )
      {
        LOBYTE(v122) = 1;
        v126 = HMValidateHandleNoSecure(*(_QWORD *)(v123 + 16288), v122);
        v127 = (struct tagWND *)v126;
        if ( v126 )
        {
          v162 = *(_QWORD *)(v126 + 16);
          if ( !*(_QWORD *)(v162 + 640) )
          {
            if ( (unsigned int)IsMiPEnabledForThread(v162) )
            {
              MiPWindowFlags = GetMiPWindowFlags(v127);
              v122 = 1;
              if ( (MiPWindowFlags & 1) == 0 )
              {
                v164 = (struct tagQ **)*((_QWORD *)v127 + 2);
                if ( v164 == (struct tagQ **)a1 )
                {
                  v165 = *(_QWORD *)(a1 + 1512);
                  v166 = *(_OWORD *)(v165 + 24);
                  v167 = *(_OWORD *)(v165 + 40);
                  v168 = *(_OWORD *)(v165 + 56);
                  v169 = *(_OWORD *)(v165 + 72);
                  v170 = *(_OWORD *)(v165 + 88);
                  v171 = *(_OWORD *)(v165 + 104);
                  if ( v80 )
                  {
                    *(_OWORD *)(v165 + 24) = v76;
                    *(_OWORD *)(v165 + 40) = v77;
                    *(_OWORD *)(v165 + 56) = v78;
                    *(_OWORD *)(v165 + 72) = v79;
                    *(_OWORD *)(v165 + 88) = v320;
                    *(_OWORD *)(v165 + 104) = *(_OWORD *)BugCheckParameter2;
                  }
                  memset((char *)&v373[1] + 8, 0, 24);
                  Win32HMThreadLockBase<tagWND,0,0>::Win32HMThreadLockBase<tagWND,0,0>(BugCheckParameter3, v127);
                  FindTimer((_DWORD)v127, 65523, 2, 1, 0);
                  if ( (unsigned int)IsMiPEnabledForWindow(v127) )
                    xxxSendTransformableMessageTimeout(v172, 0x24Au, 0, 0, 0, 1, 0);
                  if ( v80 )
                  {
                    v203 = *(_QWORD *)(a1 + 1512);
                    *(_OWORD *)(v203 + 24) = v166;
                    *(_OWORD *)(v203 + 40) = v167;
                    *(_OWORD *)(v203 + 56) = v168;
                    *(_OWORD *)(v203 + 72) = v169;
                    *(_OWORD *)(v203 + 88) = v170;
                    *(_OWORD *)(v203 + 104) = v171;
                  }
                  Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)BugCheckParameter3);
                  NextSysMsg = v312;
                }
                else
                {
                  PostEventMessageEx((struct tagTHREADINFO *)v164, v164[58], 0x15u, v127, 0, 0, 0, 0);
                }
              }
            }
          }
        }
        if ( v310 )
        {
          if ( *(_QWORD *)&v292[4] )
            v284 = **(_QWORD **)&v292[4];
          else
            v284 = 0;
          *(_QWORD *)(v123 + 16288) = v284;
        }
        else
        {
          *(_QWORD *)(v123 + 16288) = 0;
        }
      }
    }
    v25 = v310;
    if ( !v310 )
    {
      v133 = v72 - 1;
      if ( v133 )
      {
        if ( v133 == 1 )
          *(_DWORD *)(*(_QWORD *)(a1 + 464) + 168LL) = 0;
      }
      else
      {
        *(_DWORD *)(*(_QWORD *)(a1 + 464) + 160LL) = v360[1];
        v206 = v361[0] >> 16;
        *(_WORD *)(*(_QWORD *)(a1 + 464) + 164LL) = WORD1(v361[0]);
        v207 = W32GetUserSessionState(v206, v122);
        *(_DWORD *)(*(_QWORD *)(a1 + 464) + 168LL) = v362 + *(_DWORD *)(v207 + 14664);
        if ( *(_QWORD *)&v292[4] )
          v208 = **(_QWORD **)&v292[4];
        else
          v208 = 0;
        *(_QWORD *)(*(_QWORD *)(a1 + 464) + 176LL) = v208;
        *(_QWORD *)(*(_QWORD *)(a1 + 464) + 184LL) = *(_QWORD *)((char *)&v362 + 4);
      }
    }
    v125 = (const struct tagQMSG *)&v359;
    if ( v25 )
      v125 = (const struct tagQMSG *)&v382;
    if ( xxxMouseActivate((struct tagTHREADINFO *)a1, *(struct tagWND **)&v292[4], v125, v299) == 1 )
    {
      v9 = 1;
      goto LABEL_51;
    }
    if ( !*(_DWORD *)v292 )
      goto LABEL_190;
    v9 = 1;
    xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v359, 1);
LABEL_191:
    if ( *(_DWORD *)v292 && v307 && ((*(_BYTE *)(a1 + 712) | *(_BYTE *)(**(_QWORD **)(a1 + 496) + 16LL)) & 0x40) != 0 )
      xxxCallHook(6, v291, (__int64)v370, 5);
    v307 = 0;
    v297 = (void *)((LOWORD(v296.y) << 16) | LOWORD(v296.x));
    if ( v291 >= 0x200 )
      v298 = (unsigned int)GetMouseKeyFlags(*(_QWORD *)(a1 + 464));
    if ( (v291 - 171 <= 2 || v291 - 523 <= 2) && !v25 )
      v298 |= v361[0];
    if ( v299 == 5 )
    {
      if ( *(_DWORD *)v292 )
      {
        v285 = *(_QWORD *)(a1 + 640);
        if ( v285 )
        {
          if ( (*(_DWORD *)(v285 + 8) & 0x100) != 0 && *(_QWORD *)v285 && (**(_DWORD **)v285 & 1) != 0 )
          {
            MenuStateOwnerLockxxxUnlock::MenuStateOwnerLockxxxUnlock(
              (MenuStateOwnerLockxxxUnlock *)v341,
              *(struct tagMENUSTATE **)(a1 + 640));
            if ( !(unsigned int)xxxCallHandleMenuMessages(v285, *(_DWORD *)&v292[4], v291, v298, (__int64)v297) )
            {
              MenuStateOwnerLockxxxUnlock::~MenuStateOwnerLockxxxUnlock((MenuStateOwnerLockxxxUnlock *)v341);
              break;
            }
            MenuStateOwnerLockxxxUnlock::~MenuStateOwnerLockxxxUnlock((MenuStateOwnerLockxxxUnlock *)v341);
LABEL_845:
            v16 = FLOAT_1_0;
LABEL_846:
            v11 = v301;
            continue;
          }
        }
      }
    }
    break;
  }
  if ( !v25 )
    goto LABEL_198;
  v16 = FLOAT_1_0;
LABEL_210:
  v88 = v303;
LABEL_211:
  if ( ((HIDWORD(v366) - 2) & 0xFFFFFFCF) == 0 && HIDWORD(v366) != 50 )
  {
    v291 = (unsigned int)v360[1];
    v298 = v361[0];
    v297 = (void *)v361[1];
LABEL_214:
    if ( *(_DWORD *)v292 )
    {
      if ( !*(_QWORD *)(a1 + 640) && (unsigned int)IsMiPEnabledForThread(a1) && v25 )
      {
        if ( *(_QWORD *)&v292[4] )
          v89 = **(_QWORD **)&v292[4];
        else
          v89 = 0;
        *(_QWORD *)(*(_QWORD *)(a1 + 1512) + 48LL) = v89;
        v90 = *(_QWORD *)(a1 + 1512);
        v91 = *(_DWORD *)(v90 + 36);
        if ( (v91 & 0x400000) != 0 && (*(_DWORD *)(*(_QWORD *)&v292[4] + 380LL) & 0x40000000) == 0 )
          *(_DWORD *)(v90 + 36) = v91 & 0xFFBFFFFF;
        v92 = GetMiPWindowFlags(*(struct tagWND **)&v292[4]);
        SetMiPWindowFlags(*(struct tagWND **)&v292[4], v92 & 0xFFFFFFFFFFFFFFFEuLL);
        if ( ((LODWORD(v360[1]) - 578) & 0xFFFFFFFB) != 0 )
        {
          if ( ((LODWORD(v360[1]) - 579) & 0xFFFFFFFB) == 0 )
            **(_DWORD **)(a1 + 1512) &= ~8u;
        }
        else
        {
          v286 = 0;
          if ( LODWORD(v360[1]) == 578 )
            v286 = 8;
          **(_DWORD **)(a1 + 1512) = v286 | **(_DWORD **)(a1 + 1512) & 0xFFFFFFF7;
        }
      }
      else
      {
        xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v359, 1);
      }
    }
    if ( (unsigned int)IsPointerMessageTouchpad((struct tagTHREADINFO *)a1, v361[1], v25) )
    {
      if ( !*(_DWORD *)v292 && !ShouldReceiveTouchpadMessages((const struct tagTHREADINFO *)a1, v360[0]) )
        xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v359, 1);
      if ( v291 == 595 )
        v297 = (void *)-1LL;
    }
    goto LABEL_198;
  }
  EtwTraceBeginPointerMessageRetrieve(NextSysMsg, LOWORD(v361[0]), LODWORD(v360[1]));
  v393[0] = *(_OWORD *)NextSysMsg;
  v393[1] = *((_OWORD *)NextSysMsg + 1);
  v393[2] = *((_OWORD *)NextSysMsg + 2);
  v393[3] = *((_OWORD *)NextSysMsg + 3);
  v393[4] = *((_OWORD *)NextSysMsg + 4);
  v393[5] = *((_OWORD *)NextSysMsg + 5);
  v393[6] = *((_OWORD *)NextSysMsg + 6);
  v393[7] = *((_OWORD *)NextSysMsg + 7);
  v393[8] = *((_OWORD *)NextSysMsg + 8);
  v393[9] = *((_OWORD *)NextSysMsg + 9);
  v394 = *((_QWORD *)NextSysMsg + 20);
  v100 = (unsigned int)xxxRetrievePointerInputMessage(
                         a1,
                         v317,
                         v88,
                         a5,
                         1,
                         0,
                         (int *)v292,
                         NextSysMsg,
                         (__int64)&v292[4],
                         (__int64)&v291,
                         (__int64)&v298,
                         (__int64)&v297,
                         &v300,
                         v313);
  InputTraceLogging::Pointer::RetrieveMessage(v393, 0, v100);
  EtwTraceEndPointerMessageRetrieve(v393, LOWORD(v361[0]), LODWORD(v360[1]));
  v101 = *(_QWORD *)&v292[4];
  if ( *(_QWORD *)&v292[4] )
    Win32HM_ExchangeThreadLock<1>(*(_QWORD *)&v292[4], v331);
  v102 = v100 - 1;
  if ( !v102 )
    goto LABEL_214;
  v103 = v102 - 1;
  if ( v103 )
  {
    v104 = v103 - 1;
    if ( v104 )
    {
      *v313 = 0;
      if ( v104 == 1 )
      {
        v11 = v301;
        goto LABEL_23;
      }
    }
    else
    {
      xxxDefPointerProc(v101, LODWORD(v360[1]), v361[0], v361[1]);
      *v313 = 0;
    }
    goto LABEL_51;
  }
  if ( !v300 )
    goto LABEL_75;
  v315 = *(_QWORD *)(*(_QWORD *)&v292[4] + 16LL);
  v249 = v315;
  v250 = (Win32RawLockedW32Thread *)v353;
LABEL_734:
  Win32RawLockedW32Thread::Exchange(v250, (struct _W32THREAD *)v249);
LABEL_76:
  *(_QWORD *)(*(_QWORD *)(a1 + 464) + 80LL) = 0;
  if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20000) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
  {
    v9 = 0;
  }
  v33 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v9 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v110 = *(_QWORD *)(a1 + 464);
    v111 = *(_QWORD *)(v110 + 72);
    v112 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED);
    LOBYTE(v113) = v33;
    LOBYTE(v114) = v9;
    WPP_RECORDER_AND_TRACE_SF_qqq(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v114,
      v113,
      *(_QWORD *)(v112 + 69152),
      4,
      18,
      36,
      (__int64)WPP_49cdbed1bece331d44f23b214bd7a204_Traceguids,
      v110,
      a1,
      v111);
  }
  *(_QWORD *)(*(_QWORD *)(a1 + 464) + 72LL) = 0;
  **(_DWORD **)(a1 + 480) &= ~1u;
  v34 = v314;
  v35 = v319;
  v36 = v321;
  v37 = v315;
  if ( v328 )
  {
    SetWakeBit(v328, 16385);
    ClearWakeBit((struct tagTHREADINFO *)a1, 0x4001u, 0);
  }
  else if ( !v314 && !v319 && !v321 && !v315 )
  {
    v38 = *(_QWORD *)(a1 + 464);
    if ( !*(_DWORD *)(v38 + 40) )
      _InterlockedAnd(
        (volatile signed __int32 *)(*(_QWORD *)(a1 + 480) + 8LL),
        (*(_DWORD *)(v38 + 508) >> 4) & 2 | 0xFFFF83F8);
    goto LABEL_87;
  }
  if ( v34 )
  {
    SetWakeBit(v34, 16390);
    ClearWakeBit((struct tagTHREADINFO *)a1, 0x4006u, 0);
  }
  if ( v36 )
  {
    SetWakeBit(v36, 17408);
    ClearWakeBit((struct tagTHREADINFO *)a1, 0x4400u, 0);
  }
  if ( v37 )
  {
    SetWakeBit(v37, 20480);
    ClearWakeBit((struct tagTHREADINFO *)a1, 0x5000u, 0);
  }
  if ( v35 )
  {
    SetWakeBit(v35, 8256);
    _InterlockedAnd((volatile signed __int32 *)(*(_QWORD *)(a1 + 480) + 8LL), 0xFFFFDFFF);
  }
LABEL_87:
  if ( v306[0] )
  {
    v39 = PtiCurrent();
    *((_QWORD *)v39 + 170) &= ~0x1000000000uLL;
  }
  Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)v331);
  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v353);
  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v354);
  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v352);
  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v350);
  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v351);
  return 0;
}

```

## disassembly

```asm
0x1401ca020  mov     rax, rsp
0x1401ca023  push    rbx
0x1401ca024  push    rsi
0x1401ca025  push    rdi
0x1401ca026  push    r12
0x1401ca028  push    r13
0x1401ca02a  push    r14
0x1401ca02c  push    r15
0x1401ca02e  sub     rsp, 6A0h
0x1401ca035  movaps  xmmword ptr [rax-48h], xmm6
0x1401ca039  movaps  xmmword ptr [rax-58h], xmm7
0x1401ca03d  movaps  xmmword ptr [rax-68h], xmm8
0x1401ca042  movaps  xmmword ptr [rax-78h], xmm9
0x1401ca047  movaps  xmmword ptr [rax-88h], xmm10
0x1401ca04f  movaps  xmmword ptr [rax-98h], xmm11
0x1401ca057  movaps  xmmword ptr [rax-0A8h], xmm12
0x1401ca05f  movaps  xmmword ptr [rax-0B8h], xmm13
0x1401ca067  movaps  xmmword ptr [rax-0C8h], xmm14
0x1401ca06f  movaps  xmmword ptr [rax-0D8h], xmm15
0x1401ca077  mov     rax, cs:__security_cookie
0x1401ca07e  xor     rax, rsp
0x1401ca081  mov     [rsp+6D8h+var_E8], rax
0x1401ca089  mov     eax, r9d
0x1401ca08c  mov     [rsp+6D8h+var_61C], eax
0x1401ca093  mov     [rsp+6D8h+var_5D8], r8
0x1401ca09b  mov     [rsp+6D8h+var_528], rdx
0x1401ca0a3  mov     [rsp+6D8h+var_558], rcx
0x1401ca0ab  mov     [rsp+6D8h+var_510], rcx
0x1401ca0b3  mov     [rsp+6D8h+var_4D0], rdx
0x1401ca0bb  mov     r14, rcx
0x1401ca0be  mov     [rsp+6D8h+var_590], rcx
0x1401ca0c6  mov     [rsp+6D8h+var_508], rcx
0x1401ca0ce  mov     [rsp+6D8h+var_550], rdx
0x1401ca0d6  mov     [rsp+6D8h+var_4F8], r8
0x1401ca0de  mov     [rsp+6D8h+var_5A0], eax
0x1401ca0e5  mov     rbx, [rsp+6D8h+arg_38]
0x1401ca0ed  mov     [rsp+6D8h+var_5F8], rbx
0x1401ca0f5  xor     edx, edx; Val
0x1401ca0f7  mov     r8d, 0A8h; Size
0x1401ca0fd  lea     rcx, [rsp+6D8h+var_3D8]; void *
0x1401ca105  call    memset_0
0x1401ca10a  xor     esi, esi
0x1401ca10c  mov     [rsp+6D8h+var_660], rsi
0x1401ca111  mov     [rsp+6D8h+var_668], esi
0x1401ca115  mov     [rsp+6D8h+var_638], rsi
0x1401ca11d  mov     [rsp+6D8h+var_640], rsi
0x1401ca125  mov     qword ptr [rsp+6D8h+var_648.x], rsi
0x1401ca12d  mov     [rsp+6D8h+var_62C], esi
0x1401ca134  mov     [rsp+6D8h+var_630], esi
0x1401ca13b  xorps   xmm0, xmm0
0x1401ca13e  xor     eax, eax
0x1401ca140  movups  xmmword ptr [rsp+6D8h+var_328], xmm0
0x1401ca148  movups  [rsp+6D8h+var_318], xmm0
0x1401ca150  mov     [rsp+6D8h+var_308], rax
0x1401ca158  mov     edx, dword ptr [rsp+6D8h+arg_28]
0x1401ca15f  lea     r12d, [rsi+1]
0x1401ca163  and     edx, r12d
0x1401ca166  mov     [rsp+6D8h+var_664], edx
0x1401ca16a  mov     [rbx], rsi
0x1401ca16d  lea     rbx, [r14+1D0h]
0x1401ca174  mov     [rsp+6D8h+var_628], rbx
0x1401ca17c  mov     r9d, [rsp+6D8h+arg_30]
0x1401ca184  cmp     r9d, 2000h
0x1401ca18b  jz      loc_1401CBBE6
0x1401ca191  mov     [rsp+6D8h+var_628], rbx
0x1401ca199  mov     [rsp+6D8h+var_500], rbx
0x1401ca1a1  mov     r15, [rbx]
0x1401ca1a4  cmp     [r15+48h], rsi
0x1401ca1a8  jnz     short loc_1401CA20D
0x1401ca1aa  lea     r8, WPP_GLOBAL_Control
0x1401ca1b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1401ca1b8  cmp     rcx, r8
0x1401ca1bb  jz      short loc_1401CA1CA
0x1401ca1bd  test    dword ptr [rcx+2Ch], 20000h
0x1401ca1c4  jnz     loc_1401CD546
0x1401ca1ca  mov     bl, sil
0x1401ca1cd  lea     rcx, WPP_RECORDER_INITIALIZED
0x1401ca1d4  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1401ca1db  setnz   dil
0x1401ca1df  test    bl, bl
0x1401ca1e1  jnz     loc_1401CB716
0x1401ca1e7  test    dil, dil
0x1401ca1ea  jnz     loc_1401CB716
0x1401ca1f0  mov     rbx, [rsp+6D8h+var_628]
0x1401ca1f8  mov     rax, [rbx]
0x1401ca1fb  mov     [rax+48h], r14
0x1401ca1ff  mov     rax, [r14+1E0h]
0x1401ca206  or      [rax], r12d
0x1401ca209  mov     edx, [rsp+6D8h+var_664]
0x1401ca20d  test    r9d, 1C07h
0x1401ca214  jnz     loc_1401CBC53
0x1401ca21a  mov     rcx, [rbx]
0x1401ca21d  cmp     [rcx+48h], r14
0x1401ca221  jnz     loc_1401CBA4F
0x1401ca227  mov     [rsp+6D8h+var_530], r14
0x1401ca22f  mov     ecx, [rsp+6D8h+arg_20]
0x1401ca236  mov     [rsp+6D8h+var_594], ecx
0x1401ca23d  mov     [rsp+6D8h+var_4B8], r14
0x1401ca245  mov     r15d, [rsp+6D8h+var_61C]
0x1401ca24d  mov     [rsp+6D8h+var_598], r15d
0x1401ca255  mov     [rsp+6D8h+var_5A8], esi
0x1401ca25c  mov     [rsp+6D8h+var_604], esi
0x1401ca263  mov     eax, esi
0x1401ca265  mov     [rsp+6D8h+var_620], eax
0x1401ca26c  mov     [rsp+6D8h+var_654], eax
0x1401ca273  mov     [rsp+6D8h+var_650], al
0x1401ca27a  mov     [rsp+6D8h+var_5E0], rsi
0x1401ca282  mov     [rsp+6D8h+var_5D0], esi
0x1401ca289  mov     [rsp+6D8h+var_614], esi
0x1401ca290  mov     [rsp+6D8h+var_658], esi
0x1401ca297  mov     rax, rsi
0x1401ca29a  mov     [rsp+6D8h+var_5F0], rax
0x1401ca2a2  mov     [rsp+6D8h+var_548], rax
0x1401ca2aa  mov     [rsp+6D8h+var_588], rsi
0x1401ca2b2  mov     [rsp+6D8h+var_5C8], rax
0x1401ca2ba  mov     [rsp+6D8h+var_5B0], rsi
0x1401ca2c2  mov     [rsp+6D8h+var_5E8], rax
0x1401ca2ca  xor     edx, edx; struct _W32THREAD *
0x1401ca2cc  lea     rcx, [rsp+6D8h+var_498]; this
0x1401ca2d4  call    ??0Win32RawLockedW32Thread@@QEAA@PEAU_W32THREAD@@@Z; Win32RawLockedW32Thread::Win32RawLockedW32Thread(_W32THREAD *)
0x1401ca2d9  xor     edx, edx; struct _W32THREAD *
0x1401ca2db  lea     rcx, [rsp+6D8h+var_4B0]; this
0x1401ca2e3  call    ??0Win32RawLockedW32Thread@@QEAA@PEAU_W32THREAD@@@Z; Win32RawLockedW32Thread::Win32RawLockedW32Thread(_W32THREAD *)
0x1401ca2e8  xor     edx, edx; struct _W32THREAD *
0x1401ca2ea  lea     rcx, [rsp+6D8h+var_480]; this
0x1401ca2f2  call    ??0Win32RawLockedW32Thread@@QEAA@PEAU_W32THREAD@@@Z; Win32RawLockedW32Thread::Win32RawLockedW32Thread(_W32THREAD *)
0x1401ca2f7  xor     edx, edx; struct _W32THREAD *
0x1401ca2f9  lea     rcx, [rsp+6D8h+var_450]; this
0x1401ca301  call    ??0Win32RawLockedW32Thread@@QEAA@PEAU_W32THREAD@@@Z; Win32RawLockedW32Thread::Win32RawLockedW32Thread(_W32THREAD *)
0x1401ca306  xor     edx, edx; struct _W32THREAD *
0x1401ca308  lea     rcx, [rsp+6D8h+var_468]; this
0x1401ca310  call    ??0Win32RawLockedW32Thread@@QEAA@PEAU_W32THREAD@@@Z; Win32RawLockedW32Thread::Win32RawLockedW32Thread(_W32THREAD *)
0x1401ca315  mov     [rsp+6D8h+var_660], rsi
0x1401ca31a  xor     r8d, r8d
0x1401ca31d  mov     rdx, r14
0x1401ca320  lea     rcx, [rsp+6D8h+var_568]
0x1401ca328  call    ??0?$Win32HMOptionalThreadLock@UtagWND@@@@QEAA@PEAUtagTHREADINFO@@PEAUtagWND@@@Z; Win32HMOptionalThreadLock<tagWND>::Win32HMOptionalThreadLock<tagWND>(tagTHREADINFO *,tagWND *)
0x1401ca32d  lea     rcx, [rsp+6D8h+var_616]; this
0x1401ca335  call    ??0CManageInScanSysQueueBit@@QEAA@XZ; CManageInScanSysQueueBit::CManageInScanSysQueueBit(void)
0x1401ca33a  movss   xmm6, cs:__real@3f800000
0x1401ca342  mov     rcx, cs:WPP_GLOBAL_Control
0x1401ca349  lea     rax, WPP_GLOBAL_Control
0x1401ca350  cmp     rcx, rax
0x1401ca353  jz      short loc_1401CA362
0x1401ca355  test    dword ptr [rcx+2Ch], 20000h
0x1401ca35c  jnz     loc_1401CD558
0x1401ca362  mov     r12b, sil
0x1401ca365  lea     rdx, WPP_RECORDER_INITIALIZED
0x1401ca36c  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1401ca373  jnz     loc_1401CAA45
0x1401ca379  mov     r15b, sil
0x1401ca37c  test    r12b, r12b
0x1401ca37f  jnz     loc_1401CD567
0x1401ca385  test    r15b, r15b
0x1401ca388  jnz     loc_1401CD567
0x1401ca38e  mov     rax, [rbx]
0x1401ca391  mov     [rax+58h], rsi
0x1401ca395  mov     r12d, 1
0x1401ca39b  mov     ecx, [rsp+6D8h+var_654]
0x1401ca3a2  nop
0x1401ca3a3  mov     rax, [r14+200h]
0x1401ca3aa  mov     r13d, [rax]
0x1401ca3ad  shr     r13, 9
0x1401ca3b1  and     r13d, r12d
0x1401ca3b4  mov     [rsp+6D8h+var_4D8], r13d
0x1401ca3bc  jmp     short loc_1401CA3FE
0x1401ca3be  xor     esi, esi
0x1401ca3c0  lea     r12d, [rsi+1]
0x1401ca3c4  lea     rdx, WPP_RECORDER_INITIALIZED
0x1401ca3cb  lea     r13d, [rsi+2]
0x1401ca3cf  mov     rax, [rsp+6D8h+var_548]
0x1401ca3d7  mov     [rsp+6D8h+var_5F0], rax
0x1401ca3df  mov     ecx, esi
0x1401ca3e1  mov     [rsp+6D8h+var_5C8], rcx
0x1401ca3e9  mov     [rsp+6D8h+var_5E8], rcx
0x1401ca3f1  mov     r14, [rsp+6D8h+var_590]
0x1401ca3f9  jmp     loc_1401CA7C2
0x1401ca3fe  mov     rdx, [rbx]
0x1401ca401  cmp     [rdx+58h], rsi
0x1401ca405  jnz     loc_1401CD5DB
0x1401ca40b  mov     eax, esi
0x1401ca40d  mov     [rsp+6D8h+var_620], eax
0x1401ca414  mov     al, sil
0x1401ca417  mov     [rsp+6D8h+var_654], eax
0x1401ca41e  mov     [rsp+6D8h+var_650], al
0x1401ca425  mov     [rsp+6D8h+var_638], rsi
0x1401ca42d  lea     r8, [rsp+6D8h+var_3D8]; struct tagQMSG *
0x1401ca435  mov     rdx, [rdx+58h]; struct tagQMSG *
0x1401ca439  mov     rcx, r14; struct tagTHREADINFO *
0x1401ca43c  call    ?xxxGetNextSysMsg@@YAPEAUtagQMSG@@PEAUtagTHREADINFO@@PEAU1@1@Z; xxxGetNextSysMsg(tagTHREADINFO *,tagQMSG *,tagQMSG *)
0x1401ca441  mov     rdi, rax
0x1401ca444  mov     [rsp+6D8h+var_600], rax
0x1401ca44c  mov     rcx, cs:WPP_GLOBAL_Control
0x1401ca453  lea     rax, WPP_GLOBAL_Control
0x1401ca45a  cmp     rcx, rax
0x1401ca45d  jnz     loc_1401CB6FA
0x1401ca463  mov     r12b, sil
0x1401ca466  lea     rdx, WPP_RECORDER_INITIALIZED
0x1401ca46d  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1401ca474  jnz     loc_1401CC243
0x1401ca47a  mov     r15b, sil
0x1401ca47d  test    r12b, r12b
0x1401ca480  jnz     loc_1401CD60B
0x1401ca486  test    r15b, r15b
0x1401ca489  jnz     loc_1401CD60B
0x1401ca48f  mov     rax, [rbx]
0x1401ca492  mov     [rax+58h], rdi
0x1401ca496  test    rdi, rdi
0x1401ca499  jnz     loc_1401CA666
0x1401ca49f  mov     rax, [rbx]
0x1401ca4a2  cmp     [rax+58h], rsi
0x1401ca4a6  jz      loc_1401CA79E
0x1401ca4ac  lea     rcx, [rsp+6D8h+var_568]; BugCheckParameter3
0x1401ca4b4  call    ??$ManualUnlock@X@?$Win32HMThreadLockBase@UtagCURSOR@@$00$00@@QEAAPEAUtagCURSOR@@XZ; Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>(void)
0x1401ca4b9  mov     r12d, 1
0x1401ca4bf  mov     dl, r12b
0x1401ca4c2  mov     rcx, [rsp+6D8h+var_3C8]
0x1401ca4ca  call    HMValidateHandleNoSecure
0x1401ca4cf  mov     [rsp+6D8h+var_660], rax
0x1401ca4d4  lea     r8, [rsp+6D8h+var_568]
0x1401ca4dc  mov     rdx, rax
0x1401ca4df  mov     rcx, r14
0x1401ca4e2  call    ??$Win32HM_LockIntoThread@$00@@YAXPEAUtagTHREADINFO@@PEAU_HEAD@@PEAU_Win32HMThreadLockItem@@@Z; Win32HM_LockIntoThread<1>(tagTHREADINFO *,_HEAD *,_Win32HMThreadLockItem *)
0x1401ca4e7  mov     edx, dword ptr [rsp+6D8h+var_378]
0x1401ca4ee  test    edx, edx
0x1401ca4f0  jnz     loc_1401CA6F0
0x1401ca4f6  cmp     [rsp+6D8h+arg_30], 2000h
0x1401ca501  mov     ecx, [rsp+6D8h+var_654]
0x1401ca508  jz      loc_1401CA3A2
0x1401ca50e  mov     r15d, esi
0x1401ca511  mov     [rsp+6D8h+var_608], esi
0x1401ca518  mov     eax, esi
0x1401ca51a  mov     [rsp+6D8h+var_610], eax
0x1401ca521  mov     [rsp+6D8h+var_60C], eax
0x1401ca528  mov     eax, dword ptr [rsp+6D8h+var_3C8+8]
0x1401ca52f  mov     [rsp+6D8h+var_668], eax
0x1401ca533  cmp     eax, 24Ah
0x1401ca538  ja      loc_1401CAB6B
0x1401ca53e  jz      loc_1401CB425
0x1401ca544  cmp     eax, 11Bh
0x1401ca549  ja      loc_1401CC6BE
0x1401ca54f  jz      loc_1401CAA8D
0x1401ca555  sub     eax, 23h ; '#'
0x1401ca558  jz      loc_1401CE06A
0x1401ca55e  sub     eax, 0DBh
0x1401ca563  jz      loc_1401CAAC0
0x1401ca569  sub     eax, r12d
0x1401ca56c  jnz     loc_1401CAA57
0x1401ca572  mov     rax, [rsp+6D8h+var_3B8]
0x1401ca57a  mov     [rsp+6D8h+var_638], rax
0x1401ca582  mov     rdx, [rsp+6D8h+var_3B8+8]; __int64
0x1401ca58a  mov     [rsp+6D8h+var_640], rdx
0x1401ca592  mov     rcx, r14; struct tagTHREADINFO *
0x1401ca595  call    ?DeleteHidDataIfAlreadyHandledByGRIB@@YA_NPEAUtagTHREADINFO@@_J@Z; DeleteHidDataIfAlreadyHandledByGRIB(tagTHREADINFO *,__int64)
0x1401ca59a  test    al, al
0x1401ca59c  jnz     short loc_1401CA60F
0x1401ca59e  mov     [rsp+6D8h+var_660], rsi
0x1401ca5a3  mov     rdx, rsi
0x1401ca5a6  mov     rcx, [rsp+6D8h+var_640]
0x1401ca5ae  test    rcx, rcx
0x1401ca5b1  jz      short loc_1401CA5CB
0x1401ca5b3  mov     dl, 12h
0x1401ca5b5  call    HMValidateHandleNoSecure
0x1401ca5ba  mov     rdx, rax
0x1401ca5bd  test    rax, rax
0x1401ca5c0  jz      short loc_1401CA5CB
0x1401ca5c2  mov     rcx, [rax+18h]
0x1401ca5c6  mov     [rsp+6D8h+var_660], rcx
0x1401ca5cb  cmp     [rsp+6D8h+var_660], rsi
0x1401ca5d0  jnz     loc_1401CB634
0x1401ca5d6  mov     rax, [rbx]
0x1401ca5d9  mov     rcx, [rax+78h]
0x1401ca5dd  mov     [rsp+6D8h+var_660], rcx
0x1401ca5e2  test    rcx, rcx
0x1401ca5e5  jnz     loc_1401CB634
0x1401ca5eb  mov     rax, [rax+80h]
0x1401ca5f2  mov     [rsp+6D8h+var_660], rax
0x1401ca5f7  test    rax, rax
0x1401ca5fa  jnz     loc_1401CB634
0x1401ca600  xor     edx, edx
0x1401ca602  mov     rcx, [rsp+6D8h+var_640]
0x1401ca60a  call    ?SSQResult@RawInput@InputTraceLogging@@SAXPEAXW4SsqResult@12@@Z; InputTraceLogging::RawInput::SSQResult(void *,InputTraceLogging::RawInput::SsqResult)
0x1401ca60f  mov     r15d, [rsp+6D8h+var_658]
0x1401ca617  mov     r8d, r12d; int
0x1401ca61a  lea     rdx, [rsp+6D8h+var_3D8]; struct tagQMSG *
0x1401ca622  mov     rcx, r14; struct tagTHREADINFO *
0x1401ca625  call    ?xxxSkipSysMsgEx@@YAPEAUtagQMSG@@PEAUtagTHREADINFO@@PEAU1@H@Z; xxxSkipSysMsgEx(tagTHREADINFO *,tagQMSG *,int)
0x1401ca62a  cmp     [rsp+6D8h+var_614], esi
0x1401ca631  jnz     loc_1401CEF15
0x1401ca637  test    r15d, r15d
0x1401ca63a  jnz     loc_1401CEF55
0x1401ca640  cmp     [rsp+6D8h+var_664], esi
0x1401ca644  movss   xmm6, cs:__real@3f800000
0x1401ca64c  mov     rbx, [rsp+6D8h+var_628]
0x1401ca654  mov     ecx, [rsp+6D8h+var_654]
0x1401ca65b  jz      loc_1401CA3A2
0x1401ca661  jmp     loc_1401CA33A
0x1401ca666  mov     eax, dword ptr [rsp+6D8h+var_378+4]
0x1401ca66d  test    al, 20h
0x1401ca66f  jnz     loc_1401CD06A
  ... truncated ...
```
