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
  int v10; // edx
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
  int v24; // r15d
  __int64 v25; // rdx
  __int64 v26; // rax
  struct tagQ *v27; // rax
  int v28; // r15d
  int v29; // eax
  __int64 v30; // r15
  char v31; // r15
  bool v32; // r15
  __int64 v33; // rbx
  __int64 v34; // r12
  struct _W32THREAD *v35; // r15
  __int64 v36; // rdi
  __int64 v37; // rcx
  struct tagTHREADINFO *v38; // rax
  unsigned __int64 v40; // rax
  struct tagTHREADINFO *v41; // rax
  char *v42; // rax
  int v43; // eax
  bool v44; // zf
  int v45; // ecx
  int v46; // ecx
  int v47; // ecx
  int v48; // r8d
  __int64 v49; // rax
  HWND *v50; // rdx
  __int64 v51; // rcx
  int v52; // r8d
  struct tagWND *v53; // rbx
  int v54; // r9d
  __int64 v55; // rdx
  HWND v56; // rbx
  struct tagWND *v57; // rax
  __int64 v58; // rdx
  int v59; // ebx
  __int64 v60; // rcx
  const struct tagUIPI_INFO *v61; // r8
  struct tagPOINT v62; // rbx
  __int64 v63; // rcx
  int v64; // edx
  int v65; // edx
  int v66; // eax
  int v67; // r13d
  int v68; // eax
  __int64 v69; // rcx
  __int128 v70; // xmm12
  __int128 v71; // xmm13
  __int128 v72; // xmm14
  __int128 v73; // xmm15
  int v74; // r12d
  __int64 v75; // rcx
  __int64 v76; // rdx
  char v77; // bl
  struct tagMSG *v78; // r15
  __int64 v79; // rcx
  int v80; // ecx
  __int64 v81; // rdx
  unsigned int v82; // r13d
  __int64 v83; // rcx
  __int64 v84; // r8
  int v85; // edx
  unsigned __int64 MiPWindowFlags; // rax
  BOOL v87; // edi
  Scrollbar::NonClient *v88; // rcx
  unsigned int v89; // eax
  __int64 v90; // r8
  __int64 UserSessionState; // rax
  int v92; // r8d
  int v93; // edx
  __int64 v94; // rbx
  __int64 v95; // rcx
  int v96; // ebx
  int v97; // ebx
  int v98; // ebx
  _DWORD *v99; // rax
  __int16 v100; // ax
  _QWORD *v101; // rax
  __int64 v102; // rcx
  LONG v103; // eax
  __int64 v104; // rdi
  __int64 v105; // rbx
  __int64 v106; // rax
  int v107; // r8d
  int v108; // edx
  char v109; // r13
  int v110; // eax
  int v111; // eax
  unsigned int v112; // eax
  __int64 v113; // rax
  unsigned int *v114; // rax
  _DWORD *v115; // rax
  __int64 v116; // r15
  __int64 v117; // rcx
  __int64 v118; // rdx
  const struct tagQMSG *v119; // r8
  __int64 v120; // rax
  struct tagWND *v121; // rbx
  unsigned __int64 v122; // rcx
  struct tagQ *v123; // rax
  __int64 v124; // rcx
  __int64 v125; // rcx
  int v126; // eax
  int v127; // r13d
  bool v128; // al
  __int64 v129; // rax
  struct tagWND *v130; // r8
  float *v131; // rbx
  const struct tagWND *TopLevelOrDpiBoundaryWindow; // rax
  const struct tagWND *v133; // rdi
  char v134; // di
  char v135; // bl
  __int64 v136; // rdx
  __int64 v137; // rcx
  int v138; // r15d
  int v139; // r13d
  __int64 v140; // rdi
  unsigned int v141; // ebx
  __int64 v142; // rax
  __int64 v143; // rcx
  ULONG_PTR v144; // r15
  __int64 v145; // rcx
  __int64 v146; // rcx
  int v147; // eax
  struct tagWND *v148; // rbx
  int v149; // eax
  unsigned int MouseKeyFlags; // eax
  int v151; // r9d
  __int64 v152; // rcx
  struct tagQ **v153; // rcx
  __int64 v154; // rax
  __int128 v155; // xmm6
  __int128 v156; // xmm7
  __int128 v157; // xmm8
  __int128 v158; // xmm9
  __int128 v159; // xmm10
  __int128 v160; // xmm11
  struct tagWND *v161; // rcx
  unsigned int v162; // ecx
  __int64 v163; // rcx
  __int64 v164; // rcx
  int v165; // eax
  int v166; // ecx
  int TouchTimeFromCPLValue; // eax
  __int64 v168; // rdx
  int v169; // eax
  struct tagWND *v170; // rbx
  __int64 v171; // rcx
  __int64 v172; // rcx
  char v173; // r8
  unsigned int v174; // ecx
  unsigned int v175; // edx
  __int64 v176; // rcx
  _QWORD *v177; // rax
  unsigned __int64 v178; // rbx
  ULONG_PTR v179; // r13
  unsigned __int64 v180; // r9
  unsigned int v181; // eax
  int v182; // ebx
  __int64 v183; // rbx
  __int64 v184; // rdx
  __int64 v185; // rdx
  struct tagWND *v186; // rax
  __int64 v187; // rax
  char v188; // al
  __int64 v189; // rdx
  int v190; // ecx
  __int64 v191; // rax
  char v192; // r15
  unsigned int v193; // r15d
  unsigned __int64 v194; // rcx
  __int64 v195; // rax
  __int64 v196; // rcx
  struct tagTHREADINFO *BugCheckParameter4; // rax
  float v198; // xmm2_4
  __int64 v199; // r8
  struct tagQ *v200; // rdi
  __int64 v201; // rbx
  __int64 v202; // rax
  int v203; // r8d
  int v204; // edx
  struct tagQ *v205; // rdi
  __int64 v206; // rbx
  __int64 v207; // rax
  int v208; // r8d
  int v209; // edx
  int v210; // r15d
  struct tagQ *v211; // rdi
  __int64 v212; // rbx
  __int64 v213; // rax
  int v214; // r8d
  int v215; // edx
  struct tagQ *v216; // rdi
  __int64 v217; // rbx
  __int64 v218; // rax
  int v219; // r8d
  int v220; // edx
  int v221; // ebx
  struct tagWND *CompositeAppFrameWindowOrSelf; // rdi
  BOOL v223; // ebx
  struct tagQ *v224; // rcx
  __int64 v225; // rax
  __int64 v226; // rcx
  __int64 v227; // rcx
  __int64 v228; // rbx
  struct tagQ *v229; // rdi
  __int64 v230; // rbx
  __int64 v231; // rax
  int v232; // r8d
  int v233; // edx
  __int64 v234; // rdx
  HWND *v235; // rdx
  __int64 v236; // rdx
  __int64 v237; // rdx
  Win32RawLockedW32Thread *v238; // rcx
  int v239; // eax
  int v240; // r9d
  _DWORD *v241; // rax
  _DWORD *v242; // rax
  __int64 v243; // rcx
  __int64 v244; // rcx
  __int64 v245; // rax
  __int64 v246; // r8
  __int64 v247; // rdx
  __int64 v248; // rax
  int v249; // r8d
  int v250; // edx
  __int64 v251; // rdx
  __int64 v252; // rax
  __int64 v253; // rcx
  LONG v254; // eax
  __int64 v255; // rax
  __int64 v256; // rcx
  __int64 v257; // rax
  __int64 v258; // rcx
  __int64 v259; // rcx
  const struct tagWND *v260; // rcx
  struct tagWND *v261; // rax
  const struct tagWND *TopLevelWindow; // rax
  __int64 v263; // r8
  __int64 v264; // r8
  __int64 v265; // rax
  __int64 v266; // rbx
  int v267; // edx
  int v268; // eax
  struct tagTHREADINFO *v269; // rcx
  int InteractiveControlInputMessage; // eax
  char v271; // [rsp+48h] [rbp-690h]
  unsigned int v272; // [rsp+70h] [rbp-668h] BYREF
  _BYTE v273[12]; // [rsp+74h] [rbp-664h] BYREF
  int v274; // [rsp+80h] [rbp-658h]
  BOOL v275; // [rsp+84h] [rbp-654h]
  bool v276; // [rsp+88h] [rbp-650h]
  struct tagPOINT v277; // [rsp+90h] [rbp-648h] BYREF
  void *v278; // [rsp+98h] [rbp-640h] BYREF
  unsigned __int64 v279; // [rsp+A0h] [rbp-638h] BYREF
  int v280; // [rsp+A8h] [rbp-630h] BYREF
  int v281; // [rsp+ACh] [rbp-62Ch] BYREF
  struct tagQ **v282; // [rsp+B0h] [rbp-628h]
  unsigned int v283; // [rsp+B8h] [rbp-620h]
  unsigned int v284; // [rsp+BCh] [rbp-61Ch]
  bool v285; // [rsp+C0h] [rbp-618h]
  bool v286; // [rsp+C1h] [rbp-617h]
  char v287[2]; // [rsp+C2h] [rbp-616h] BYREF
  int v288; // [rsp+C4h] [rbp-614h]
  int v289; // [rsp+C8h] [rbp-610h]
  unsigned int v290; // [rsp+CCh] [rbp-60Ch]
  int v291; // [rsp+D0h] [rbp-608h]
  int v292; // [rsp+D4h] [rbp-604h]
  struct tagQMSG *v293; // [rsp+D8h] [rbp-600h]
  struct tagQMSG **v294; // [rsp+E0h] [rbp-5F8h]
  __int64 v295; // [rsp+E8h] [rbp-5F0h]
  __int64 v296; // [rsp+F0h] [rbp-5E8h]
  ULONG_PTR v297; // [rsp+F8h] [rbp-5E0h]
  __int64 v298; // [rsp+100h] [rbp-5D8h]
  int v299; // [rsp+108h] [rbp-5D0h]
  __int64 v300; // [rsp+110h] [rbp-5C8h]
  __int128 v301; // [rsp+118h] [rbp-5C0h]
  struct _W32THREAD *v302; // [rsp+128h] [rbp-5B0h]
  int v303; // [rsp+130h] [rbp-5A8h]
  int v304; // [rsp+134h] [rbp-5A4h]
  unsigned int v305; // [rsp+138h] [rbp-5A0h]
  unsigned int v306; // [rsp+140h] [rbp-598h]
  unsigned int v307; // [rsp+144h] [rbp-594h]
  struct tagTHREADINFO *v308; // [rsp+148h] [rbp-590h]
  struct _W32THREAD *v309; // [rsp+150h] [rbp-588h]
  ULONG_PTR BugCheckParameter2[2]; // [rsp+158h] [rbp-580h] BYREF
  __int64 v311; // [rsp+168h] [rbp-570h]
  ULONG_PTR v312[2]; // [rsp+170h] [rbp-568h] BYREF
  __int64 v313; // [rsp+180h] [rbp-558h]
  struct tagMSG *v314; // [rsp+188h] [rbp-550h]
  __int64 v315; // [rsp+190h] [rbp-548h]
  __int64 v316; // [rsp+1A8h] [rbp-530h]
  struct tagMSG *v317; // [rsp+1B0h] [rbp-528h]
  __int64 v318; // [rsp+1C8h] [rbp-510h]
  __int64 v319; // [rsp+1D0h] [rbp-508h]
  __int64 v320; // [rsp+1D8h] [rbp-500h]
  __int64 v321; // [rsp+1E0h] [rbp-4F8h]
  char v322[8]; // [rsp+1E8h] [rbp-4F0h] BYREF
  unsigned int v323; // [rsp+1F0h] [rbp-4E8h] BYREF
  unsigned int v324; // [rsp+1F4h] [rbp-4E4h]
  int v325; // [rsp+1F8h] [rbp-4E0h]
  int v326; // [rsp+1FCh] [rbp-4DCh]
  int v327; // [rsp+200h] [rbp-4D8h]
  struct tagMSG *v328; // [rsp+208h] [rbp-4D0h]
  ULONG_PTR v329[2]; // [rsp+210h] [rbp-4C8h] BYREF
  __int64 v330; // [rsp+220h] [rbp-4B8h]
  _BYTE v331[24]; // [rsp+228h] [rbp-4B0h] BYREF
  _BYTE v332[24]; // [rsp+240h] [rbp-498h] BYREF
  _BYTE v333[24]; // [rsp+258h] [rbp-480h] BYREF
  _BYTE v334[24]; // [rsp+270h] [rbp-468h] BYREF
  _BYTE v335[48]; // [rsp+288h] [rbp-450h] BYREF
  ULONG_PTR v336[2]; // [rsp+2B8h] [rbp-420h] BYREF
  ULONG_PTR v337[2]; // [rsp+2C8h] [rbp-410h] BYREF
  ULONG_PTR v338[3]; // [rsp+2D8h] [rbp-400h] BYREF
  ULONG_PTR BugCheckParameter3[2]; // [rsp+2F0h] [rbp-3E8h] BYREF
  __int128 v340; // [rsp+300h] [rbp-3D8h] BYREF
  HWND v341[2]; // [rsp+310h] [rbp-3C8h]
  unsigned __int64 v342[2]; // [rsp+320h] [rbp-3B8h]
  __int128 v343; // [rsp+330h] [rbp-3A8h]
  __int128 v344; // [rsp+340h] [rbp-398h]
  struct tagPOINT v345[2]; // [rsp+350h] [rbp-388h] BYREF
  __int128 v346; // [rsp+360h] [rbp-378h]
  __int128 v347; // [rsp+370h] [rbp-368h] BYREF
  __int128 v348; // [rsp+380h] [rbp-358h]
  __int128 v349; // [rsp+390h] [rbp-348h]
  __int64 v350; // [rsp+3A0h] [rbp-338h]
  __int64 v351[2]; // [rsp+3B0h] [rbp-328h] BYREF
  __int128 v352; // [rsp+3C0h] [rbp-318h]
  __int64 v353; // [rsp+3D0h] [rbp-308h]
  _OWORD v354[3]; // [rsp+3E0h] [rbp-2F8h] BYREF
  __int128 v355; // [rsp+410h] [rbp-2C8h]
  __int128 v356; // [rsp+420h] [rbp-2B8h]
  __int128 v357; // [rsp+430h] [rbp-2A8h]
  __int128 v358; // [rsp+440h] [rbp-298h]
  __int128 v359; // [rsp+450h] [rbp-288h]
  __int128 v360; // [rsp+460h] [rbp-278h]
  __int128 v361; // [rsp+470h] [rbp-268h]
  __int64 v362; // [rsp+480h] [rbp-258h]
  __int128 v363; // [rsp+490h] [rbp-248h] BYREF
  __int128 v364; // [rsp+4A0h] [rbp-238h]
  __int128 v365; // [rsp+4B0h] [rbp-228h]
  __int128 v366; // [rsp+4C0h] [rbp-218h]
  __int128 v367; // [rsp+4D0h] [rbp-208h]
  __int128 v368; // [rsp+4E0h] [rbp-1F8h]
  __int128 v369; // [rsp+4F0h] [rbp-1E8h]
  __int128 v370; // [rsp+500h] [rbp-1D8h]
  __int128 v371; // [rsp+510h] [rbp-1C8h]
  __int128 v372; // [rsp+520h] [rbp-1B8h]
  __int64 v373; // [rsp+530h] [rbp-1A8h]
  _OWORD v374[10]; // [rsp+540h] [rbp-198h] BYREF
  __int64 v375; // [rsp+5E0h] [rbp-F8h]

  v284 = a4;
  v298 = a3;
  v317 = a2;
  v313 = a1;
  v318 = a1;
  v328 = a2;
  v308 = (struct tagTHREADINFO *)a1;
  v319 = a1;
  v314 = a2;
  v321 = a3;
  v305 = a4;
  v294 = a8;
  memset_0(&v340, 0, 0xA8u);
  *(_DWORD *)&v273[8] = 0;
  v272 = 0;
  v279 = 0;
  v278 = 0;
  v277 = 0;
  v281 = 0;
  v280 = 0;
  *(_OWORD *)v351 = 0;
  v352 = 0;
  v353 = 0;
  v9 = 1;
  v10 = a6 & 1;
  *(_QWORD *)v273 = a6 & 1;
  *a8 = 0;
  v11 = (struct tagQ **)(a1 + 464);
  v282 = (struct tagQ **)(a1 + 464);
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
    v282 = (struct tagQ **)(a1 + 464);
  }
  v320 = a1 + 464;
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
      UserSessionState = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED);
      LOBYTE(v92) = v15;
      LOBYTE(v93) = v14;
      WPP_RECORDER_AND_TRACE_SF_qqq(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v93,
        v92,
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
    v11 = v282;
    *((_QWORD *)*v282 + 9) = a1;
    **(_DWORD **)(a1 + 480) |= 1u;
    v10 = *(_DWORD *)v273;
  }
  if ( (v12 & 0x1C07) != 0 )
  {
    v111 = *((_DWORD *)*v11 + 127);
    if ( v10 )
      v112 = v111 & 0xFFFFFBFF;
    else
      v112 = v111 | 0x400;
    *((_DWORD *)*v11 + 127) = v112;
  }
  if ( *((_QWORD *)*v11 + 9) != a1 )
  {
    EtwTraceInputQueueLocked();
    return 2;
  }
  v316 = a1;
  v307 = a5;
  v330 = a1;
  v306 = v284;
  v303 = 0;
  v292 = 0;
  v283 = 0;
  v275 = 0;
  v276 = 0;
  v297 = 0;
  v299 = 0;
  v288 = 0;
  v274 = 0;
  v295 = 0;
  v315 = 0;
  v309 = 0;
  v300 = 0;
  v302 = 0;
  v296 = 0;
  Win32RawLockedW32Thread::Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v332, 0);
  Win32RawLockedW32Thread::Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v331, 0);
  Win32RawLockedW32Thread::Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v333, 0);
  Win32RawLockedW32Thread::Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v335, 0);
  Win32RawLockedW32Thread::Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v334, 0);
  *(_QWORD *)&v273[4] = 0;
  Win32HMOptionalThreadLock<tagWND>::Win32HMOptionalThreadLock<tagWND>(v312, a1, 0);
  CManageInScanSysQueueBit::CManageInScanSysQueueBit((CManageInScanSysQueueBit *)v287);
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
      v200 = *v11;
      v201 = *((_QWORD *)*v11 + 11);
      v202 = W32GetUserSessionState(WPP_GLOBAL_Control);
      LOBYTE(v203) = v17;
      LOBYTE(v204) = v9;
      WPP_RECORDER_AND_TRACE_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v204,
        v203,
        *(_QWORD *)(v202 + 69152),
        5,
        18,
        30,
        (__int64)WPP_49cdbed1bece331d44f23b214bd7a204_Traceguids,
        (char)v200,
        v201);
      v11 = v282;
    }
    *((_QWORD *)*v11 + 11) = 0;
LABEL_22:
    v9 = 1;
LABEL_23:
    LOBYTE(i) = v275;
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
                    v327 = v19;
                    v20 = *v11;
                    if ( *((_QWORD *)*v11 + 11) )
                    {
                      if ( !(_BYTE)i )
                      {
                        v275 = ((v283 - 1) & 0xFFFFFFFD) == 0;
                        v276 = ((v283 - 1) & 0xFFFFFFFD) == 0;
                      }
                    }
                    else
                    {
                      v283 = 0;
                      v275 = 0;
                      v276 = 0;
                    }
                    v279 = 0;
                    NextSysMsg = xxxGetNextSysMsg(
                                   (struct tagTHREADINFO *)a1,
                                   *((struct tagQMSG **)v20 + 11),
                                   (struct tagQMSG *)&v340);
                    v293 = NextSysMsg;
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
                      v205 = *v11;
                      v206 = *((_QWORD *)*v11 + 11);
                      v207 = W32GetUserSessionState(WPP_GLOBAL_Control);
                      v271 = (char)v205;
                      NextSysMsg = v293;
                      LOBYTE(v208) = v22;
                      LOBYTE(v209) = v9;
                      WPP_RECORDER_AND_TRACE_SF_qqq(
                        *((_QWORD *)WPP_GLOBAL_Control + 3),
                        v209,
                        v208,
                        *(_QWORD *)(v207 + 69152),
                        5,
                        18,
                        31,
                        (__int64)WPP_49cdbed1bece331d44f23b214bd7a204_Traceguids,
                        (char)v293,
                        v271,
                        v206);
                      v11 = v282;
                    }
                    *((_QWORD *)*v11 + 11) = NextSysMsg;
                    if ( !NextSysMsg )
                      goto LABEL_33;
                    v29 = DWORD1(v346);
                    if ( (BYTE4(v346) & 0x20) != 0 )
                    {
                      i = (__int64)v294;
                      *v294 = NextSysMsg;
                      *((_DWORD *)NextSysMsg + 25) |= 0x100u;
                      *(_DWORD *)v273 = 0;
                      v29 = DWORD1(v346);
                      if ( (DWORD1(v346) & 0x8000000) != 0 )
                      {
                        *(_DWORD *)(*(_QWORD *)i + 100LL) |= 0x8000000u;
                        v29 = DWORD1(v346);
                      }
                    }
                    if ( (v29 & 0x2000) == 0 )
                      break;
                    v210 = v283;
                    v9 = 1;
                    if ( *((_QWORD *)&v346 + 1) == a1 )
                      v210 = 1;
                    v283 = v210;
                    LOBYTE(i) = 1;
                    v275 = i;
                    v276 = 1;
                  }
                  LOBYTE(i) = v275;
                  if ( (v29 & 0x10000) == 0 )
                    break;
                  v9 = 1;
                  if ( *((_QWORD *)&v346 + 1) == a1 )
                  {
                    v283 = 3;
                    goto LABEL_23;
                  }
                }
                if ( (_DWORD)v346 == 4 && v275 )
                {
                  DeferSysPeekMsg(a1, 3);
                  goto LABEL_22;
                }
                if ( (v29 & 0x4000) == 0 )
                  break;
                v9 = 1;
                if ( *((_QWORD *)&v346 + 1) == a1 )
                  v283 = 2;
              }
              if ( (unsigned int)ShouldDeferMessage(v283, &v340) )
              {
                DeferSysPeekMsg(a1, 3);
                v283 = 3;
                goto LABEL_22;
              }
LABEL_33:
              if ( !*((_QWORD *)*v11 + 11) )
              {
                if ( a7 == 0x2000 )
                  _InterlockedAnd((volatile signed __int32 *)(*(_QWORD *)(a1 + 480) + 8LL), 0xFFFFDFFF);
                goto LABEL_75;
              }
              Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)v312);
              v9 = 1;
              LOBYTE(v23) = 1;
              *(_QWORD *)&v273[4] = HMValidateHandleNoSecure(v341[0], v23);
              Win32HM_LockIntoThread<1>(a1, *(_QWORD *)&v273[4], v312);
              if ( !(_DWORD)v346 )
                break;
              if ( (_DWORD)v346 == 4 )
              {
                LOBYTE(i) = v275;
                if ( *((_QWORD *)*v11 + 11) != *((_QWORD *)*v11 + 3) )
                  continue;
              }
              if ( (_DWORD)v346 != 9 || LODWORD(v341[1]) != 96 )
                goto LABEL_65;
              for ( i = *((_QWORD *)&v340 + 1); i && (unsigned int)IsHiddenByInputService(); i = *(_QWORD *)(i + 8) )
                ;
              v44 = i == 0;
              LOBYTE(i) = v275;
              if ( v44 )
              {
LABEL_65:
                v30 = *((_QWORD *)&v346 + 1);
                if ( !*((_QWORD *)&v346 + 1) || *((_QWORD *)&v346 + 1) == a1 )
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
                    || (v31 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
                  {
                    v31 = 0;
                  }
                  if ( v9 || v31 )
                  {
                    v216 = *v11;
                    v217 = *((_QWORD *)*v11 + 11);
                    v218 = W32GetUserSessionState(WPP_GLOBAL_Control);
                    LOBYTE(v219) = v31;
                    LOBYTE(v220) = v9;
                    WPP_RECORDER_AND_TRACE_SF_qq(
                      *((_QWORD *)WPP_GLOBAL_Control + 3),
                      v220,
                      v219,
                      *(_QWORD *)(v218 + 69152),
                      5,
                      18,
                      33,
                      (__int64)WPP_49cdbed1bece331d44f23b214bd7a204_Traceguids,
                      (char)v216,
                      v217);
                    v11 = v282;
                  }
                  *((_QWORD *)*v11 + 11) = 0;
                  xxxProcessEventMessage(a1, &v340);
                  v9 = 1;
                  goto LABEL_14;
                }
                if ( *(struct tagQ **)(*((_QWORD *)&v346 + 1) + 464LL) != *v11 )
                {
                  CleanEventMessage(*((struct tagQMSG **)*v11 + 11));
                  DelQEntry((char *)*v11 + 24, *((_QWORD *)*v11 + 11), 1);
                  goto LABEL_14;
                }
                ReferenceW32Thread(*((_QWORD *)&v346 + 1));
                ExchangeW32ThreadLock(v30, v333);
                if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20000) == 0
                  || (v109 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
                {
                  v109 = 0;
                }
                if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
                  || !*((_WORD *)WPP_GLOBAL_Control + 36) )
                {
                  v9 = 0;
                }
                if ( v109 || v9 )
                {
                  v211 = *v11;
                  v212 = *((_QWORD *)*v11 + 11);
                  v213 = W32GetUserSessionState(WPP_GLOBAL_Control);
                  LOBYTE(v214) = v9;
                  LOBYTE(v215) = v109;
                  WPP_RECORDER_AND_TRACE_SF_qq(
                    *((_QWORD *)WPP_GLOBAL_Control + 3),
                    v215,
                    v214,
                    *(_QWORD *)(v213 + 69152),
                    5,
                    18,
                    32,
                    (__int64)WPP_49cdbed1bece331d44f23b214bd7a204_Traceguids,
                    (char)v211,
                    v212);
                  v11 = v282;
                }
                *((_QWORD *)*v11 + 11) = 0;
                v300 = v30;
                goto LABEL_75;
              }
            }
            i = v275;
          }
          while ( a7 == 0x2000 );
          v24 = 0;
          v291 = 0;
          v289 = 0;
          v290 = 0;
          v272 = (unsigned int)v341[1];
          if ( LODWORD(v341[1]) > 0x24A )
          {
            if ( LODWORD(v341[1]) <= 0x2ED )
            {
              if ( LODWORD(v341[1]) == 749 )
                goto LABEL_873;
              if ( LODWORD(v341[1]) == 593 || LODWORD(v341[1]) == 594 || LODWORD(v341[1]) == 595 )
                goto LABEL_210;
              v45 = LODWORD(v341[1]) - 744;
              v44 = LODWORD(v341[1]) == 744;
              goto LABEL_124;
            }
            if ( LODWORD(v341[1]) != 750 && LODWORD(v341[1]) != 751 && LODWORD(v341[1]) != 752 )
            {
              v45 = LODWORD(v341[1]) - 753;
              v44 = LODWORD(v341[1]) == 753;
LABEL_124:
              if ( v44 )
                goto LABEL_873;
              v46 = v45 - 1;
              if ( !v46 )
                goto LABEL_873;
              v47 = v46 - 1;
              if ( !v47 || (unsigned int)(v47 - 1) < 2 )
                goto LABEL_873;
              goto LABEL_128;
            }
LABEL_873:
            if ( v284 || a5 != -1 )
            {
              if ( v284 <= a5 )
              {
                if ( LODWORD(v341[1]) >= v306 && LODWORD(v341[1]) <= v307 )
                  goto LABEL_883;
                v268 = 0;
              }
              else
              {
                if ( LODWORD(v341[1]) >= v307 && LODWORD(v341[1]) <= v306 )
                  goto LABEL_75;
                v268 = 1;
              }
              if ( !v268 )
                goto LABEL_75;
            }
LABEL_883:
            if ( !(unsigned int)IsInsideMenuLoop(a1) )
            {
              if ( *(_DWORD *)v273 )
                xxxSkipSysMsgEx(v269, (struct tagQMSG *)&v340, 1);
              if ( !*(_QWORD *)&v273[4] )
                *(_QWORD *)&v273[4] = *(_QWORD *)(*(_QWORD *)(a1 + 464) + 120LL);
              v279 = v342[0];
              v278 = (void *)v342[1];
              InteractiveControlInputMessage = xxxRetrieveInteractiveControlInputMessage(
                                                 LOWORD(v342[0]),
                                                 WORD1(v342[0]));
              if ( InteractiveControlInputMessage == 1 )
                goto LABEL_198;
              if ( InteractiveControlInputMessage == 2 )
                goto LABEL_75;
            }
            goto LABEL_51;
          }
          if ( LODWORD(v341[1]) == 586 )
            goto LABEL_210;
          if ( LODWORD(v341[1]) > 0x11B )
            break;
          switch ( LODWORD(v341[1]) )
          {
            case 0x11B:
              goto LABEL_106;
            case 0x23:
              v279 = 0;
              v278 = (void *)v342[1];
              if ( !*(_QWORD *)&v273[4] || (v237 = *(_QWORD *)(*(_QWORD *)&v273[4] + 16LL), v237 == a1) )
              {
                if ( (unsigned int)MiPCheckMsgFilter(NextSysMsg, v272, v284, a5) )
                {
LABEL_736:
                  if ( *(_DWORD *)v273 )
                    xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v340, 1);
                  goto LABEL_198;
                }
              }
              else
              {
                if ( *(struct tagQ **)(v237 + 464) != *v11 )
                  goto LABEL_51;
                if ( !v295 )
                {
                  v295 = *(_QWORD *)(*(_QWORD *)&v273[4] + 16LL);
                  v238 = (Win32RawLockedW32Thread *)v331;
                  goto LABEL_734;
                }
              }
LABEL_75:
              v9 = 1;
              goto LABEL_76;
            case 0xFE:
LABEL_110:
              v279 = v342[0];
              v278 = (void *)v342[1];
              if ( !*(_QWORD *)&v273[4] )
                goto LABEL_51;
              if ( CheckCrossThreadInput(*(struct tagWND *const *)&v273[4], NextSysMsg, &v281, (int *)v273, v294) )
                goto LABEL_75;
              if ( v281 )
                goto LABEL_51;
              if ( !v284 && a5 == -1 )
              {
LABEL_749:
                v239 = CheckPwndFilter(*(_QWORD *)&v273[4], v298);
                LOBYTE(i) = v275;
                if ( v239 )
                  goto LABEL_736;
              }
              else
              {
                if ( v284 <= a5 )
                {
                  if ( v272 >= v284 && v272 <= a5 )
                    goto LABEL_749;
                  v43 = 0;
                  goto LABEL_748;
                }
                if ( v272 < a5 || (LOBYTE(i) = v275, v272 > v284) )
                {
                  v43 = 1;
LABEL_748:
                  LOBYTE(i) = v275;
                  if ( v43 )
                    goto LABEL_749;
                }
              }
              break;
            case 0xFF:
              v279 = v342[0];
              v278 = (void *)v342[1];
              if ( !DeleteHidDataIfAlreadyHandledByGRIB((struct tagTHREADINFO *)a1, v342[1]) )
              {
                *(_QWORD *)&v273[4] = 0;
                v25 = 0;
                if ( v278 )
                {
                  LOBYTE(v25) = 18;
                  v26 = HMValidateHandleNoSecure(v278, v25);
                  v25 = v26;
                  if ( v26 )
                    *(_QWORD *)&v273[4] = *(_QWORD *)(v26 + 24);
                }
                if ( !*(_QWORD *)&v273[4] )
                {
                  v27 = *v11;
                  *(_QWORD *)&v273[4] = *((_QWORD *)*v11 + 15);
                  if ( !*(_QWORD *)&v273[4] )
                  {
                    *(_QWORD *)&v273[4] = *((_QWORD *)v27 + 16);
                    if ( !*(_QWORD *)&v273[4] )
                    {
                      InputTraceLogging::RawInput::SSQResult(v278, 0);
                      goto LABEL_51;
                    }
                  }
                }
                if ( v25 && *(_QWORD *)(v25 + 16) != *(_QWORD *)(*(_QWORD *)&v273[4] + 16LL) )
                {
                  v304 = 0x20000;
                  MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 10065);
                }
                Win32HM_ExchangeThreadLock<1>(*(_QWORD *)&v273[4], v312);
                if ( CheckCrossThreadInput(*(struct tagWND *const *)&v273[4], NextSysMsg, &v281, (int *)v273, v294) )
                {
                  v234 = 0;
                  goto LABEL_713;
                }
                if ( !v281 )
                  goto LABEL_241;
                if ( *(struct tagQ **)(*(_QWORD *)(*(_QWORD *)&v273[4] + 16LL) + 464LL) != *v11 )
                  goto LABEL_51;
                if ( (unsigned int)IsInsideMenuLoop(a1) )
                {
                  v235 = *(HWND **)(**(_QWORD **)(a1 + 640) + 8LL);
                }
                else
                {
                  v236 = *(_QWORD *)(a1 + 704);
                  if ( v236 )
                    v235 = *(HWND **)(v236 + 16);
                  else
                    v235 = 0;
                }
                if ( v235 )
                  InputTraceLogging::RawInput::IgnoreModalLoop(v278, *v235);
                if ( !v302 )
                {
                  v302 = *(struct _W32THREAD **)(*(_QWORD *)&v273[4] + 16LL);
                  Win32RawLockedW32Thread::Exchange((Win32RawLockedW32Thread *)v335, v302);
                }
LABEL_241:
                if ( !v284 && a5 == -1 )
                  goto LABEL_243;
                if ( v284 > a5 )
                {
                  if ( v272 >= a5 && v272 <= v284 )
                    goto LABEL_302;
                  v110 = 1;
                }
                else
                {
                  if ( v272 >= v284 && v272 <= a5 )
                  {
LABEL_243:
                    if ( (unsigned int)CheckPwndFilter(*(_QWORD *)&v273[4], v298) )
                    {
                      if ( !v281 )
                      {
                        if ( *(_DWORD *)v273 )
                          xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v340, 1);
                        InputTraceLogging::RawInput::SSQResult(v278, 4);
                        goto LABEL_198;
                      }
                      v234 = 3;
LABEL_713:
                      InputTraceLogging::RawInput::SSQResult(v278, v234);
                      goto LABEL_76;
                    }
LABEL_302:
                    InputTraceLogging::RawInput::SSQResult(v278, 2);
                    goto LABEL_23;
                  }
                  v110 = 0;
                }
                if ( !v110 )
                  goto LABEL_302;
                goto LABEL_243;
              }
LABEL_51:
              v28 = v274;
              goto LABEL_52;
            case 0x100:
              goto LABEL_350;
            case 0x101:
LABEL_355:
              v279 = LOBYTE(v342[0]);
              v122 = v342[0];
              if ( LOBYTE(v342[0]) == 231 )
                v122 = 231;
              v342[0] = v122;
              if ( !*(_DWORD *)v273 || (WORD2(v346) & 0x8000) == 0 )
              {
                if ( *(_DWORD *)(W32GetUserSessionState(v122) + 14224) )
                {
                  if ( (GetAppImeCompatFlags(0) & 0x800000) == 0 && BYTE2(v342[1]) == 41 )
                  {
                    if ( *(_DWORD *)v273 )
                    {
                      v224 = *v11;
                      if ( (*((_BYTE *)*v11 + 356) & 0x15) == 0
                        && (*((_BYTE *)v224 + 374) & 0x40) == 0
                        && (*((_BYTE *)v224 + 375) & 1) == 0 )
                      {
                        v225 = *((_QWORD *)v224 + 15);
                        *(_QWORD *)&v273[4] = v225;
                        if ( !v225 )
                        {
                          v225 = *((_QWORD *)v224 + 16);
                          *(_QWORD *)&v273[4] = v225;
                        }
                        if ( !v225 || *(_QWORD *)(v225 + 16) == a1 )
                        {
                          xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v340, 1);
                          if ( !v299 && *(_QWORD *)&v273[4] )
                          {
                            *(_QWORD *)&v354[0] = **(_QWORD **)&v273[4];
                            *((_QWORD *)&v354[0] + 1) = 80;
                            memset(&v354[1], 0, 32);
                            xxxCallCtfHook(3, 0, 1, v354);
                          }
                          goto LABEL_14;
                        }
                      }
                    }
                  }
                }
              }
              if ( v279 == 121 )
                v272 |= 4u;
              if ( (*((_BYTE *)*v11 + 356) & 4) != 0 && v279 == 27 )
                v272 |= 4u;
              if ( (_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 520), 0, 0) & 8) == 0 )
                v342[1] &= ~0x2000000uLL;
LABEL_364:
              v279 = LOBYTE(v342[0]);
              v123 = *v11;
              v124 = *((_QWORD *)*v11 + 15);
              *(_QWORD *)&v273[4] = v124;
              if ( !*((_QWORD *)v123 + 15) )
              {
                v124 = *((_QWORD *)v123 + 16);
                *(_QWORD *)&v273[4] = v124;
                if ( !v124 )
                  goto LABEL_51;
                if ( v272 - 256 <= 3 )
                  v272 += 4;
              }
              Win32HM_ExchangeThreadLock<1>(v124, v312);
              v125 = *(_QWORD *)(*(_QWORD *)&v273[4] + 16LL);
              v281 = v125 != v319;
              if ( v125 != v313 )
              {
                if ( *(struct tagQ **)(*(_QWORD *)(*(_QWORD *)&v273[4] + 16LL) + 464LL) != *v11 )
                  goto LABEL_51;
                if ( (unsigned int)IsInsideMenuLoop(a1) )
                {
                  v226 = *(_QWORD *)(**(_QWORD **)(a1 + 640) + 8LL);
                }
                else
                {
                  v227 = *(_QWORD *)(a1 + 704);
                  if ( v227 )
                    v226 = *(_QWORD *)(v227 + 16);
                  else
                    v226 = 0;
                }
                if ( v226 )
                {
                  *(_QWORD *)&v273[4] = v226;
                  v281 = *(_QWORD *)(v226 + 16) != v330;
                  Win32HM_ExchangeThreadLock<1>(v226, v312);
                }
                if ( !v309 )
                {
                  v309 = *(struct _W32THREAD **)(*(_QWORD *)&v273[4] + 16LL);
                  Win32RawLockedW32Thread::Exchange((Win32RawLockedW32Thread *)v332, v309);
                }
              }
              if ( v284 || a5 != -1 )
              {
                if ( v284 > a5 )
                {
                  if ( v272 < a5 || (LOBYTE(i) = v275, v272 > v284) )
                  {
                    v169 = 1;
                    goto LABEL_513;
                  }
                }
                else
                {
                  if ( v272 >= v284 && v272 <= a5 )
                    goto LABEL_368;
                  v169 = 0;
LABEL_513:
                  LOBYTE(i) = v275;
                  if ( v169 )
                    goto LABEL_368;
                }
              }
              else
              {
LABEL_368:
                v126 = CheckPwndFilter(*(_QWORD *)&v273[4], v298);
                LOBYTE(i) = v275;
                if ( v126 )
                {
                  if ( v281 )
                    goto LABEL_75;
                  if ( *(_DWORD *)v273 )
                  {
                    if ( (WORD2(v346) & 0x8000) != 0 )
                      goto LABEL_403;
                    if ( !(unsigned int)IsInsideMenuLoop(a1) )
                    {
                      if ( v279 == 93 && v272 == 257 )
                      {
                        if ( *(_QWORD *)&v273[4] )
                          v199 = **(_QWORD **)&v273[4];
                        else
                          LODWORD(v199) = 0;
                        PostTransformableMessage(*(_DWORD *)&v273[4], 123, v199, -1, 0);
                      }
                      if ( v279 == 112 && v272 == 256 )
                        PostMessage(*(_QWORD *)&v273[4], 77, 0);
                    }
                  }
                  if ( v279 == 16 && !v299 )
                  {
                    v228 = v342[1] & 0x1000000;
                    if ( ((unsigned __int8)(v228 != 0 ? 1 : 4) & *((_BYTE *)*v282 + 392)) != 0 )
                    {
                      if ( (unsigned int)IsDesktopApp(*(_QWORD *)(a1 + 456))
                        && (_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 520), 0, 0) & 8) == 0 )
                      {
                        v342[0] = (v228 != 0) + 160LL;
LABEL_681:
                        xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v340, 1);
                        goto LABEL_846;
                      }
                      v11 = v282;
                    }
                    else
                    {
                      v11 = v282;
                    }
                  }
                  v303 = *((unsigned __int8 *)*v11 + ((unsigned __int64)(unsigned __int8)v279 >> 2) + 352)
                       & (1 << (2 * (v279 & 3)));
                  if ( !v303 )
                    goto LABEL_403;
                  if ( *(_DWORD *)v273 )
                  {
                    if ( NextSysMsg )
                      *((_QWORD *)NextSysMsg + 5) |= 0x40000000uLL;
LABEL_403:
                    if ( *(_DWORD *)v273 )
                    {
                      if ( (WORD2(v346) & 0x8000) == 0 && NextSysMsg && (*(_DWORD *)(a1 + 1360) & 0x10000000) != 0 )
                        v297 = (ULONG_PTR)xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v340, 0);
                      else
                        xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v340, 1);
                    }
                  }
                  v278 = (void *)v342[1];
                  v279 = v342[0];
                  if ( v303 )
                    v278 = (void *)(v342[1] | 0x40000000);
                  if ( v272 == 257 || v272 == 261 )
                    v278 = (void *)((unsigned __int64)v278 | 0x80000000);
                  if ( (*((_BYTE *)*v11 + 356) & 0x10) != 0 )
                    v278 = (void *)((unsigned __int64)v278 | 0x20000000);
                  if ( (unsigned int)IsMenuStarted(a1) )
                    v278 = (void *)((unsigned __int64)v278 | 0x10000000);
                  if ( (*(_DWORD *)(v136 + 508) & 0x4000) != 0 )
                    v278 = (void *)((unsigned __int64)v278 | 0x8000000);
                  if ( !v19 && !*(_QWORD *)(W32GetUserSessionState(v137) + 12888) || (WORD2(v346) & 0x8000) != 0 )
                    goto LABEL_416;
                  if ( !*(_DWORD *)v273 )
                  {
LABEL_417:
                    LOBYTE(v138) = v289;
                    goto LABEL_418;
                  }
                  if ( (unsigned int)IsMenuStarted(a1)
                    || (_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 520), 0, 0) & 0x2000000) != 0
                    || !*(_QWORD *)&v273[4] )
                  {
LABEL_416:
                    if ( !*(_DWORD *)v273 )
                      goto LABEL_417;
                    v138 = v289;
                    if ( (WORD2(v346) & 0x8000) != 0 )
                    {
                      if ( (DWORD1(v346) & 0x4000000) != 0 )
                        v138 = 2;
                      v289 = v138;
                      v290 = v138;
                    }
                  }
                  else
                  {
                    v178 = v279;
                    if ( v279 == 231 )
                      v178 = ((unsigned __int64)*(unsigned __int16 *)(a1 + 914) << 16) | 0xE7;
                    tagTHREADINFO::UpdateInputSource(
                      (tagTHREADINFO *)a1,
                      (const struct tagINPUT_MESSAGE_SOURCE *)((char *)&v347 + 12));
                    tagTLBLOCK::_unnamed_type_list_::_unnamed_type_list_((tagTLBLOCK::_unnamed_type_list_ *)BugCheckParameter2);
                    v179 = v297;
                    if ( v297 )
                      Win32RawLockedItemBase<tagQMSG,0,1,1,1>::ManualLock<void>((ULONG_PTR)BugCheckParameter2, v297);
                    v180 = v178;
                    v11 = v282;
                    v181 = xxxImmProcessKey(*v282, *(struct tagWND **)&v273[4], v272, v180, (__int64)v278);
                    LOBYTE(v138) = v181;
                    v289 = v181;
                    v290 = v181;
                    if ( (v181 & 0x11) != 0 )
                    {
                      if ( v179 )
                      {
                        Win32RawLockedItemBase<tagQMSG,0,1,1,1>::UnlockWorker((ULONG_PTR)BugCheckParameter2);
                        v297 = 0;
                      }
                      Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
                      goto LABEL_51;
                    }
                    if ( v179 )
                      Win32RawLockedItemBase<tagQMSG,0,1,1,1>::UnlockWorker((ULONG_PTR)BugCheckParameter2);
                    Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
                  }
LABEL_418:
                  if ( !*(_DWORD *)v273 )
                    goto LABEL_432;
                  v274 = 1;
                  v139 = 0;
                  if ( (WORD2(v346) & 0x8000) == 0 )
                  {
                    v140 = *((_QWORD *)*v11 + 65);
                    *((_QWORD *)*v11 + 65) = *((_QWORD *)&v344 + 1);
                    v141 = v138 & 2;
                    tagTHREADINFO::UpdateInputSource(
                      (tagTHREADINFO *)a1,
                      (const struct tagINPUT_MESSAGE_SOURCE *)((char *)&v347 + 12));
                    *(_QWORD *)&v354[0] = 0;
                    v354[1] = 0;
                    *((_QWORD *)&v354[0] + 1) = v278;
                    *(_QWORD *)&v301 = (unsigned int)Feature_WebThreatDefenseToggle__private_featureState;
                    if ( (Feature_WebThreatDefenseToggle__private_featureState & 0x10) == 0 )
                    {
                      LODWORD(v301) = Feature_WebThreatDefenseToggle__private_featureState | 1;
                      wil_details_FeatureReporting_ReportUsageToService(
                        Feature_WebThreatDefenseToggle__private_descriptor,
                        v301,
                        3,
                        1);
                      wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
                        v301,
                        3,
                        Feature_WebThreatDefenseToggle__private_descriptor);
                    }
                    v142 = *(_QWORD *)(a1 + 1376);
                    v143 = *(_QWORD *)(a1 + 456);
                    if ( (*(_DWORD *)(v143 + 276) & 4) != 0
                      && (_DWORD)v142 == 1
                      && (v142 & 0x500000000LL) != 0
                      && *(_QWORD *)(a1 + 488) != *(_QWORD *)(W32GetUserSessionState(v143) + 62744)
                      && CheckImEnabled() )
                    {
                      LOWORD(v354[1]) = 1;
                    }
                    tagTLBLOCK::_unnamed_type_list_::_unnamed_type_list_((tagTLBLOCK::_unnamed_type_list_ *)BugCheckParameter2);
                    v144 = v297;
                    if ( v297 )
                      Win32RawLockedItemBase<tagQMSG,0,1,1,1>::ManualLock<void>((ULONG_PTR)BugCheckParameter2, v297);
                    v139 = xxxCallCtfHook(2, v141, v279, v354);
                    if ( (BYTE2(v354[1]) & 1) != 0 )
                    {
                      if ( (*(_BYTE *)(*(_QWORD *)(a1 + 456) + 808LL) & 0x30) == 0x10 )
                        WORD1(v354[1]) |= 0x10u;
                      ProcessTranslatedChar((struct _CHARHOOKSTRUCT *)v354);
                    }
                    v11 = v282;
                    *((_QWORD *)*v282 + 65) = v140;
                    if ( !v144 )
                      goto LABEL_430;
                    if ( (unsigned int)(v139 - 2) > 1
                      || (*(_DWORD *)(a1 + 1360) & 0x20000000) != 0
                      || !AllocQEntryEx((char *)*v11 + 24, v144, 2) )
                    {
                      v297 = 0;
LABEL_430:
                      Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
                      NextSysMsg = v293;
                      goto LABEL_431;
                    }
                    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
                      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20000) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u )
                    {
                      v9 = 0;
                    }
                    if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
                      || (v192 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
                    {
                      v192 = 0;
                    }
                    if ( v9 || v192 )
                    {
                      v229 = *v11;
                      v230 = *((_QWORD *)*v11 + 11);
                      v231 = W32GetUserSessionState(WPP_GLOBAL_Control);
                      LOBYTE(v232) = v192;
                      LOBYTE(v233) = v9;
                      WPP_RECORDER_AND_TRACE_SF_qqq(
                        *((_QWORD *)WPP_GLOBAL_Control + 3),
                        v233,
                        v232,
                        *(_QWORD *)(v231 + 69152),
                        5,
                        18,
                        35,
                        (__int64)WPP_49cdbed1bece331d44f23b214bd7a204_Traceguids,
                        v297,
                        (char)v229,
                        v230);
                      v11 = v282;
                    }
                    if ( v311 == -1 )
                    {
                      BugCheckParameter4 = PtiCurrent();
                      KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)BugCheckParameter2, 0, (ULONG_PTR)BugCheckParameter4);
                    }
                    *((_QWORD *)PtiCurrent() + 47) = BugCheckParameter2[0];
                    v311 = -1;
                    *((_QWORD *)*v11 + 11) = v297;
                    v9 = 1;
                    if ( v139 == 2 )
                    {
                      v193 = 1;
                      v283 = 1;
                    }
                    else
                    {
                      v193 = v283;
                      if ( v139 == 3 )
                        v193 = 2;
                      v283 = v193;
                    }
                    DeferSysPeekMsg(a1, v193);
                    v297 = 0;
                    Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
                    goto LABEL_23;
                  }
LABEL_431:
                  if ( v139 )
                  {
                    v28 = 1;
                    goto LABEL_52;
                  }
LABEL_432:
                  if ( ((*(_BYTE *)(a1 + 712) | *(_BYTE *)(**(_QWORD **)(a1 + 496) + 16LL)) & 8) == 0 )
                  {
                    v28 = v274;
LABEL_434:
                    if ( v28
                      && *(_DWORD *)v273
                      && ((*(_BYTE *)(a1 + 712) | *(_BYTE *)(**(_QWORD **)(a1 + 496) + 16LL)) & 0x40) != 0 )
                    {
                      xxxCallHook(7, v279, (__int64)v278, 5);
                    }
                    goto LABEL_198;
                  }
                  v28 = 1;
                  v274 = 1;
                  if ( !(unsigned int)xxxCallHook(*(_DWORD *)v273 == 0 ? 3 : 0, v279, (__int64)v278, 2) )
                    goto LABEL_434;
LABEL_52:
                  xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v340, 1);
                  if ( v288 )
                  {
                    if ( ((*(_BYTE *)(a1 + 712) | *(_BYTE *)(**(_QWORD **)(a1 + 496) + 16LL)) & 0x40) != 0 )
                      xxxCallHook(6, v272, (__int64)v351, 5);
                    v288 = 0;
                  }
                  if ( v28 )
                  {
                    if ( ((*(_BYTE *)(a1 + 712) | *(_BYTE *)(**(_QWORD **)(a1 + 496) + 16LL)) & 0x40) != 0 )
                      xxxCallHook(7, v279, (__int64)v278, 5);
                    v274 = 0;
                  }
                  v16 = FLOAT_1_0;
                  v11 = v282;
                  LOBYTE(i) = v275;
                  if ( *(_DWORD *)v273 )
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
              v299 = 1;
              v279 = LOBYTE(v342[0]);
              if ( *(_DWORD *)v273 && (WORD2(v346) & 0x8000) != 0 )
              {
LABEL_353:
                if ( v279 == 231 )
                {
                  *(_WORD *)(a1 + 914) = WORD1(v342[0]);
                  v342[0] = 231;
                }
                goto LABEL_355;
              }
              if ( LOBYTE(v342[0]) != 18 )
                *((_DWORD *)*v11 + 127) &= 0xFFFFFFF3;
              if ( v279 != 44 )
              {
LABEL_527:
                if ( *(_DWORD *)(W32GetUserSessionState(i) + 16256)
                  && (!*(_DWORD *)(W32GetUserSessionState(v171) + 14652)
                   || (*(_BYTE *)(W32GetUserSessionState(v172) + 14648) & 2) == 0) )
                {
                  v173 = *((_BYTE *)*v11 + 356);
                  v174 = v279 | 0x400;
                  if ( (v173 & 0x10) == 0 )
                    v174 = v279;
                  v175 = v174 | 0x200;
                  if ( (v173 & 4) == 0 )
                    v175 = v174;
                  v176 = v175;
                  LODWORD(v176) = v175 | 0x100;
                  if ( (v173 & 1) == 0 )
                    v176 = v175;
                  v177 = (_QWORD *)HotKeyToWindow(v176);
                  if ( v177 )
                  {
                    if ( *(_QWORD *)(a1 + 488) == *(_QWORD *)(v177[2] + 488LL) )
                    {
                      PostTransformableMessage(*((_QWORD *)*v11 + 16), 274, 61776, *v177, 0);
                      xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v340, 1);
                      goto LABEL_14;
                    }
                  }
                }
                goto LABEL_353;
              }
              i = 16;
              v221 = *((_BYTE *)*v11 + 356) & 0x10;
              if ( (!v221 || (*(_DWORD *)(a1 + 916) & 0x10) != 0) && (v221 || (*(_DWORD *)(a1 + 916) & 0x20) != 0) )
              {
                v11 = v282;
                goto LABEL_527;
              }
              xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v340, 1);
              if ( v221 || (v342[1] & 0xFF0000) == 0x10000 )
              {
                v11 = v282;
                if ( !*((_QWORD *)*v282 + 16) )
                  goto LABEL_14;
                CompositeAppFrameWindowOrSelf = CoreWindowProp::GetCompositeAppFrameWindowOrSelf(*((const struct tagWND **)*v282
                                                                                                 + 16));
              }
              else
              {
                CompositeAppFrameWindowOrSelf = *(struct tagWND **)(*(_QWORD *)(*(_QWORD *)(a1 + 488) + 8LL) + 24LL);
                v11 = v282;
              }
              if ( CompositeAppFrameWindowOrSelf )
              {
                v223 = v348 != 1;
                Win32HMThreadLockAlways<tagHOOK>::Win32HMThreadLockAlways<tagHOOK>(
                  v336,
                  a1,
                  CompositeAppFrameWindowOrSelf);
                xxxSnapWindow(CompositeAppFrameWindowOrSelf, v223);
                Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)v336);
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
        if ( LODWORD(v341[1]) != 522 && LODWORD(v341[1]) != 526 )
          break;
        if ( (_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 520), 0, 0) & 0x400) != 0
          && (int)CheckProcessForeground((struct tagTHREADINFO *)a1) < 0 )
        {
          goto LABEL_75;
        }
        if ( (unsigned int)IsInsideMenuLoop(a1) )
          goto LABEL_51;
        if ( (DWORD1(v346) & 0x100000) != 0 )
        {
          v145 = *((_QWORD *)*v11 + 15);
          *(_QWORD *)&v273[4] = v145;
        }
        else
        {
          if ( *(_QWORD *)&v273[4] && IsCompositionInputWindowForHitTest(*(struct tagWND **)&v273[4]) )
          {
            v182 = 1;
            if ( (unsigned int)CoreWindowProp::IsCompositeAppOrSelfDisabled(*(const struct tagWND **)&v273[4]) )
              goto LABEL_51;
          }
          else
          {
            *(_QWORD *)&v273[4] = GetThreadDesktopWindow(0);
            v182 = 0;
          }
          Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(v337);
          v183 = xxxDCEWindowHitTest(*(_QWORD *)&v273[4], 512, v342[0], v342[1], *(_QWORD *)v345, &v280, 4 * v182 + 9);
          LOBYTE(v184) = 1;
          *(_QWORD *)&v273[4] = HMValidateHandleNoSecure(v183, v184);
          LOBYTE(v185) = 1;
          v186 = (struct tagWND *)HMValidateHandleNoSecure(v183, v185);
          InputTraceLogging::Mouse::SecondaryHitTest((const struct tagQMSG *)&v340, v345, v186);
          Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)v337);
          v145 = *(_QWORD *)&v273[4];
          v11 = v282;
        }
        if ( !v145 )
          goto LABEL_51;
        Win32HM_ExchangeThreadLock<1>(v145, v312);
        v146 = *(_QWORD *)(*(_QWORD *)&v273[4] + 16LL);
        v281 = v146 != v319;
        if ( v146 != v313 )
        {
          v168 = *(_QWORD *)(*(_QWORD *)&v273[4] + 16LL);
          if ( *(struct tagQ **)(v168 + 464) != *v11 )
            goto LABEL_51;
          if ( !v309 )
          {
            v309 = *(struct _W32THREAD **)(*(_QWORD *)&v273[4] + 16LL);
            Win32RawLockedW32Thread::Exchange((Win32RawLockedW32Thread *)v332, (struct _W32THREAD *)v168);
          }
        }
        v82 = v284;
        v147 = MiPCheckMsgFilter(NextSysMsg, v272, v284, a5);
        LOBYTE(i) = v275;
        if ( v147 )
        {
          v148 = *(struct tagWND **)&v273[4];
          v149 = CheckPwndFilter(*(_QWORD *)&v273[4], v298);
          LOBYTE(i) = v275;
          if ( v149 )
          {
            if ( v281 )
              goto LABEL_75;
            if ( NextSysMsg && (unsigned int)IsMiPActive(a1, NextSysMsg) )
            {
              if ( _bittest((const signed __int32 *)NextSysMsg + 25, 0xAu) )
              {
                memset_0(v354, 0, 0xA8u);
                if ( ShouldGenerateMipMessage((struct tagTHREADINFO *)a1, NextSysMsg, v148, *(int *)v273)
                  && GeneratePointerMessageFromMouse((struct tagQMSG *)v354, v272, NextSysMsg, v148, v240) )
                {
                  v340 = v354[0];
                  *(_OWORD *)v341 = v354[1];
                  *(_OWORD *)v342 = v354[2];
                  v343 = v355;
                  v344 = v356;
                  *(_OWORD *)&v345[0].x = v357;
                  v346 = v358;
                  v347 = v359;
                  v348 = v360;
                  v349 = v361;
                  v350 = v362;
                  v24 = 1;
                  v291 = 1;
                  if ( *(_DWORD *)v273 )
                    *((_DWORD *)NextSysMsg + 25) &= ~0x400u;
                  goto LABEL_211;
                }
                if ( !*(_DWORD *)v273 )
                  goto LABEL_452;
                *((_DWORD *)NextSysMsg + 25) &= ~0x400u;
              }
              else
              {
                if ( !*(_DWORD *)v273 )
                {
LABEL_452:
                  MouseKeyFlags = GetMouseKeyFlags(*(_QWORD *)(a1 + 464));
                  v279 = v342[0] | MouseKeyFlags;
                  v278 = (void *)v342[1];
                  v277.x = SLOWORD(v342[1]);
                  v277.y = SWORD1(v342[1]);
                  PhysicalToLogicalDPIPointWithHitTest(&v277, &v277, 0, *(const struct tagWND **)&v273[4]);
                  v278 = (void *)((LOWORD(v277.y) << 16) | LOWORD(v277.x));
                  *(struct tagPOINT *)((char *)&v343 + 4) = v277;
                  v351[0] = (__int64)v277;
                  if ( *(_QWORD *)&v273[4] )
                    v351[1] = **(_QWORD **)&v273[4];
                  else
                    v351[1] = 0;
                  LODWORD(v352) = 0;
                  *((_QWORD *)&v352 + 1) = *((_QWORD *)&v344 + 1);
                  LODWORD(v353) = v342[0];
                  if ( *(_DWORD *)v273 )
                  {
                    v288 = 1;
                    if ( (unsigned int)xxxCallCtfHook(7, 0, v272, v351) )
                      goto LABEL_51;
                  }
                  if ( ((*(_DWORD *)(a1 + 712) | *(_DWORD *)(**(_QWORD **)(a1 + 496) + 16LL)) & 0x100) != 0 )
                  {
                    v288 = 1;
                    if ( (unsigned int)xxxCallMouseHook(v272, v351, *(unsigned int *)v273) )
                      goto LABEL_51;
                  }
                  if ( (unsigned int)PsGetWin32KFilterSet() == 5 )
                  {
                    v243 = *((_QWORD *)PtiCurrent() + 64);
                    v285 = 0;
                    v285 = *(_QWORD *)(v243 + 248) != 0;
                    if ( v285 )
                    {
                      if ( xxxClientCallLocalMouseHooks(v272, v351, *(unsigned int *)v273) )
                        goto LABEL_51;
                    }
                  }
                  if ( v288
                    && *(_DWORD *)v273
                    && ((*(_BYTE *)(a1 + 712) | *(_BYTE *)(**(_QWORD **)(a1 + 496) + 16LL)) & 0x40) != 0 )
                  {
                    xxxCallHook(6, v272, (__int64)v351, 5);
                  }
LABEL_198:
                  if ( *(_QWORD *)(a1 + 788) != *(_QWORD *)((char *)&v343 + 4) )
                    _InterlockedOr((volatile signed __int32 *)(a1 + 520), 0x100000u);
                  if ( NextSysMsg && ((BYTE4(v346) & 0x20) != 0 || (DWORD1(v346) & 0x8000000) != 0) )
                  {
                    if ( *((_DWORD *)NextSysMsg + 6) == 512 )
                    {
                      if ( *(_QWORD *)&v273[4] )
                        v113 = **(_QWORD **)&v273[4];
                      else
                        v113 = 0;
                      *((_QWORD *)NextSysMsg + 2) = v113;
                      *((_DWORD *)NextSysMsg + 25) |= 0x200u;
                    }
                    *((_QWORD *)NextSysMsg + 8) = v278;
                  }
                  *(_DWORD *)(a1 + 788) = DWORD1(v343);
                  v76 = v316;
                  *(_DWORD *)(v316 + 792) = DWORD2(v343);
                  *(_DWORD *)(v76 + 796) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)&v273[4] + 40LL) + 288LL);
                  *(struct tagPOINT *)(a1 + 800) = v345[0];
                  *(_DWORD *)(a1 + 600) = v343;
                  *(_QWORD *)(*(_QWORD *)(a1 + 464) + 520LL) = *((_QWORD *)&v344 + 1);
                  if ( v272 == 514 || v272 == 162 )
                    *(struct tagPOINT *)(a1 + 808) = v345[0];
                  *(_QWORD *)(*(_QWORD *)(a1 + 464) + 80LL) = 1;
                  *(_QWORD *)(a1 + 608) = 1;
                  tagTHREADINFO::UpdateLastInputData((tagTHREADINFO *)a1, (const struct tagQMSG *)&v340);
                  **(_DWORD **)(a1 + 480) &= ~8u;
                  **(_QWORD **)(a1 + 512) &= 0x7FFFFFFFuLL;
                  v77 = v289;
                  v78 = v317;
                  if ( *(_DWORD *)v273 )
                  {
                    v101 = *(_QWORD **)(a1 + 512);
                    if ( (BYTE4(v346) & 1) != 0 )
                      *v101 |= 0x1000uLL;
                    else
                      *v101 &= ~0x1000uLL;
                  }
                  TransferWakeBit(a1, v272);
                  v79 = *(_QWORD *)(a1 + 464);
                  if ( !*(_DWORD *)(v79 + 40) )
                    _InterlockedAnd(
                      (volatile signed __int32 *)(*(_QWORD *)(a1 + 480) + 8LL),
                      (*(_DWORD *)(v79 + 508) >> 4) & 2 | 0xFFFF83F8);
                  v80 = *(_DWORD *)v273;
                  if ( *(_DWORD *)v273 )
                  {
                    if ( v291 )
                    {
                      v99 = *(_DWORD **)(a1 + 1512);
                      if ( v99 )
                      {
                        if ( (*v99 & 1) != 0 && (*v99 & 4) != 0 )
                        {
                          SetMiPWakeBit((struct tagTHREADINFO *)a1);
                          v80 = *(_DWORD *)v273;
                        }
                      }
                    }
                  }
                  v81 = 0;
                  if ( *(_QWORD *)&v273[4] )
                    v81 = **(_QWORD **)&v273[4];
                  *(_QWORD *)v328 = v81;
                  *((_DWORD *)v78 + 2) = v272;
                  v40 = v279;
                  if ( (v77 & 2) != 0 )
                    v40 = 229;
                  *((_QWORD *)v78 + 2) = v40;
                  *((_QWORD *)v78 + 3) = v278;
                  *((_DWORD *)v78 + 8) = v343;
                  *(_QWORD *)((char *)v78 + 36) = *(_QWORD *)((char *)&v343 + 4);
                  InputTraceLogging::Delivery::ScanSysQueue(
                    (const struct tagQMSG *)&v340,
                    v78,
                    (const struct tagTHREADINFO *)a1,
                    v80 != 0);
                  if ( *(_DWORD *)v273 )
                  {
                    EtwTraceInputProcessDelay(a1);
                    *(_DWORD *)(*(_QWORD *)(a1 + 464) + 528LL) = (MEMORY[0xFFFFF78000000320]
                                                                * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
                  }
                  EtwTraceRetrieveInputMessage(v78);
                  if ( v287[0] )
                  {
                    v41 = PtiCurrent();
                    *((_QWORD *)v41 + 170) &= ~0x1000000000uLL;
                  }
                  Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)v312);
                  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v334);
                  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v335);
                  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v333);
                  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v331);
                  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v332);
                  return 1;
                }
                if ( (unsigned int)IsMiPMouseMessage(*((unsigned int *)NextSysMsg + 6)) )
                {
                  if ( (unsigned int)IsGenuineMouseInput((char *)NextSysMsg + 124) )
                  {
                    v241 = *(_DWORD **)(a1 + 1512);
                    if ( v241 )
                    {
                      if ( (*v241 & 2) == 0 && (*v241 & 4) == 0 )
                        goto LABEL_681;
                    }
                  }
                  v242 = *(_DWORD **)(a1 + 1512);
                  if ( v242 )
                    *v242 &= ~2u;
                }
              }
            }
            if ( *(_DWORD *)v273 )
              xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v340, 1);
            goto LABEL_452;
          }
          v11 = v282;
        }
      }
      switch ( LODWORD(v341[1]) )
      {
        case 0x238:
          goto LABEL_110;
        case 0x240:
LABEL_106:
          if ( !*(_QWORD *)&v273[4] )
            goto LABEL_51;
          v42 = *(char **)(*(_QWORD *)&v273[4] + 40LL);
          if ( v42[20] < 0 || v42[19] < 0 || (v42[31] & 0x18) != 0x10 )
            goto LABEL_51;
          goto LABEL_110;
        case 0x245:
        case 0x246:
        case 0x247:
        case 0x249:
          goto LABEL_210;
      }
LABEL_128:
      v277.x = SLOWORD(v342[1]);
      v277.y = SWORD1(v342[1]);
      v280 = 1;
      if ( (BYTE4(v346) & 0x20) == 0 && (DWORD1(v346) & 0x8000000) == 0
        || !*(_QWORD *)&v273[4]
        || (((unsigned __int16)(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)&v273[4] + 40LL) + 288LL) >> 8)
           ^ (unsigned __int16)(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v273[4] + 16LL) + 456LL) + 268LL) >> 8))
          & 0x1FF) != 0 )
      {
        if ( !*(_QWORD *)&v273[4]
          || (v128 = IsCompositionInputWindowForHitTest(*(struct tagWND **)&v273[4]), v48 = 1, !v128) )
        {
          v48 = 0;
        }
        v292 = v48;
        v49 = *(_QWORD *)(a1 + 464);
        v50 = *(HWND **)(v49 + 112);
        if ( v50 )
        {
          *(_QWORD *)&v273[4] = *(_QWORD *)(v49 + 112);
          InputTraceLogging::Mouse::RedirectForCapture((const struct tagQMSG *)&v340, *v50);
        }
        else
        {
          Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(v329);
          if ( v52 )
          {
            v53 = *(struct tagWND **)&v273[4];
          }
          else
          {
            v53 = *(struct tagWND **)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v51) + 18752) + 488LL)
                                                + 8LL)
                                    + 24LL);
            Win32HM_LockIntoThread<1>(a1, v53, v329);
          }
          if ( (unsigned int)IsThreadDesktopComposed((const struct tagTHREADINFO *)a1) )
          {
            *(_QWORD *)&v354[0] = LODWORD(v341[1]);
            *((_QWORD *)&v354[0] + 1) = v342[0];
            *(_QWORD *)&v354[1] = v342[1];
            *((_QWORD *)&v354[1] + 1) = &v280;
            LODWORD(v354[2]) = v54;
            BYTE4(v354[2]) = 0;
            *(_WORD *)((char *)&v354[2] + 5) = 0;
            BYTE7(v354[2]) = 0;
            *((_QWORD *)&v354[2] + 1) = &v345[1];
            v355 = 0u;
            v56 = xxxDCEWindowHitTestIndirect(v53, v345[0], 0, (struct tagDCE_WINDOW_HIT_TEST_ARGS *)v354);
            if ( v56 && (_BYTE)v355 )
            {
              v342[1] = *(_QWORD *)&v354[1];
              DWORD1(v343) = SLOWORD(v354[1]);
              v55 = *(_QWORD *)&v354[1] >> 16;
              DWORD2(v343) = SWORD1(v354[1]);
              v277 = *(struct tagPOINT *)((char *)&v343 + 4);
            }
          }
          else
          {
            v56 = (HWND)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))xxxWindowHitTest)(v53, v277, &v280);
          }
          LOBYTE(v55) = 1;
          v57 = (struct tagWND *)HMValidateHandleNoSecure(v56, v55);
          InputTraceLogging::Mouse::SecondaryHitTest((const struct tagQMSG *)&v340, &v277, v57);
          if ( !v292 )
            Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)v329);
          LOBYTE(v58) = 1;
          *(_QWORD *)&v273[4] = HMValidateHandleNoSecure(v56, v58);
          if ( !*(_QWORD *)&v273[4] )
          {
            v244 = *(_QWORD *)(*(_QWORD *)(a1 + 488) + 8LL);
            *(_QWORD *)&v273[4] = *(_QWORD *)(v244 + 24);
            if ( !*(_QWORD *)&v273[4] )
              *(_QWORD *)&v273[4] = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v244) + 18752)
                                                                      + 488LL)
                                                          + 8LL)
                                              + 24LL);
          }
          v59 = 0;
          if ( !*(_QWORD *)(a1 + 640) )
          {
            if ( (unsigned int)IsMiPEnabledForThread(a1) )
            {
              if ( *(_QWORD *)(*(_QWORD *)(a1 + 464) + 560LL) )
              {
                v245 = ValidateHwnd();
                if ( v245 )
                {
                  v246 = *(_QWORD *)(a1 + 464);
                  v247 = *(_QWORD *)(v245 + 16);
                  if ( *(_QWORD *)(v247 + 464) == v246 || *(_QWORD *)(v247 + 456) == *(_QWORD *)(a1 + 456) )
                  {
                    *(_QWORD *)&v273[4] = v245;
                    v280 = 1;
                    *(_DWORD *)(v246 + 156) = 0;
                    v59 = 1;
                  }
                }
              }
            }
          }
          if ( !v59 )
            *(_DWORD *)(*(_QWORD *)(v316 + 464) + 156LL) = v280 != 1;
          Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)v329);
        }
        if ( *(_QWORD *)&v273[4] == *(_QWORD *)(*(_QWORD *)(a1 + 464) + 112LL) )
        {
          v129 = PtiMouseFromQ(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v273[4] + 16LL) + 464LL));
          if ( (((unsigned __int16)(*(_DWORD *)(*((_QWORD *)v130 + 5) + 288LL) >> 8)
               ^ (unsigned __int16)(*(_DWORD *)(*(_QWORD *)(v129 + 456) + 268LL) >> 8))
              & 0x1FF) != 0
            || (unsigned int)IsOleDragDropCaptureWindow(v130) )
          {
            v277 = v345[0];
            v131 = 0;
            TopLevelOrDpiBoundaryWindow = GetTopLevelOrDpiBoundaryWindow(*(const struct tagWND **)&v273[4]);
            v133 = TopLevelOrDpiBoundaryWindow;
            if ( TopLevelOrDpiBoundaryWindow && (unsigned int)IsWindowDesktopComposed(TopLevelOrDpiBoundaryWindow) )
              v131 = (float *)*((_QWORD *)v133 + 27);
            if ( v131 )
            {
              v198 = v16 / v131[5];
              v277.x = (int)(float)((float)((float)(FixedPointSubPixel(v345[1].x) + (float)v277.x) - v131[12])
                                  * (float)(v16 / *v131));
              v277.y = (int)(float)((float)((float)(FixedPointSubPixel(v345[1].y) + (float)v277.y) - v131[13]) * v198);
            }
            if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80000) == 0
              || (v134 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
            {
              v134 = 0;
            }
            if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
              || (v135 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
            {
              v135 = 0;
            }
            if ( v134 || v135 )
            {
              v248 = W32GetUserSessionState(WPP_GLOBAL_Control);
              LOBYTE(v249) = v135;
              LOBYTE(v250) = v134;
              WPP_RECORDER_AND_TRACE_SF_dddd(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v250,
                v249,
                *(_QWORD *)(v248 + 69152),
                5,
                20,
                34,
                (__int64)WPP_49cdbed1bece331d44f23b214bd7a204_Traceguids,
                v345[0].x,
                v345[0].y,
                v277.x,
                v277.y);
            }
            v278 = (void *)((LOWORD(v277.y) << 16) | LOWORD(v277.x));
            *(struct tagPOINT *)((char *)&v343 + 4) = v277;
            NextSysMsg = v293;
          }
        }
      }
      Win32HM_ExchangeThreadLock<1>(*(_QWORD *)&v273[4], v312);
      if ( CheckCrossThreadInput(*(struct tagWND *const *)&v273[4], NextSysMsg, &v281, (int *)v273, v294) )
        goto LABEL_75;
      if ( v281 )
      {
        v251 = *(_QWORD *)(*(_QWORD *)&v273[4] + 16LL);
        if ( *(_QWORD *)(v251 + 464) != *(_QWORD *)(a1 + 464) )
          goto LABEL_799;
        if ( !v295 )
        {
          v295 = *(_QWORD *)(*(_QWORD *)&v273[4] + 16LL);
          v315 = v251;
          Win32RawLockedW32Thread::Exchange((Win32RawLockedW32Thread *)v331, (struct _W32THREAD *)v251);
        }
      }
      else if ( (WORD2(v346) & 0x800) != 0
             && !UIPrivilegeIsolation::CheckAccess(
                   (UIPrivilegeIsolation *)&v347,
                   (const struct tagUIPI_INFO *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v273[4] + 16LL) + 456LL) + 864LL),
                   v61) )
      {
        EtwTraceUIPIMsgError(0, *(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v273[4] + 16LL) + 456LL), v272, v342[0], v342[1]);
LABEL_799:
        v252 = W32GetUserSessionState(v60);
        zzzSetCursor(*(struct tagCURSOR **)(v252 + 21712));
        goto LABEL_51;
      }
      v62 = v277;
      v63 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v273[4] + 16LL) + 464LL);
      v64 = *(_DWORD *)(v63 + 156);
      if ( v64 && (v65 = v64 - 2) != 0 )
      {
        if ( v65 != 1 )
          goto LABEL_153;
        v253 = *(_QWORD *)(*(_QWORD *)&v273[4] + 40LL);
        if ( (*(_BYTE *)(v253 + 26) & 0x40) != 0 )
          v254 = *(_DWORD *)(v253 + 96) - v277.x;
        else
          v254 = v277.x - *(_DWORD *)(v253 + 88);
        v277.x = v254;
        v63 = (unsigned int)(v277.y - *(_DWORD *)(*(_QWORD *)(*(_QWORD *)&v273[4] + 40LL) + 92LL));
      }
      else
      {
        v102 = *(_QWORD *)(*(_QWORD *)&v273[4] + 40LL);
        if ( (*(_BYTE *)(v102 + 26) & 0x40) != 0 )
          v103 = *(_DWORD *)(v102 + 112) - v277.x;
        else
          v103 = v277.x - *(_DWORD *)(v102 + 104);
        v277.x = v103;
        v63 = (unsigned int)(v277.y - *(_DWORD *)(*(_QWORD *)(*(_QWORD *)&v273[4] + 40LL) + 108LL));
      }
      v277.y = v63;
LABEL_153:
      if ( !v281 && *(_QWORD *)(a1 + 464) == *(_QWORD *)(W32GetUserSessionState(v63) + 19248) )
      {
        v87 = *(_QWORD *)(*(_QWORD *)(a1 + 488) + 192LL) != *(_QWORD *)&v273[4];
        if ( (unsigned int)Feature_UserModeNonClientScrollBars2__private_IsEnabledDeviceUsageNoInline()
          && Scrollbar::NonClient::UserModeSupportsUserModeScrollBars(v88) )
        {
          v89 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))xxxFindNCHitEx)(
                  *(_QWORD *)&v273[4],
                  (unsigned int)v280,
                  v277);
        }
        else
        {
          v89 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))FindNCHitEx)(
                  *(_QWORD *)&v273[4],
                  (unsigned int)v280,
                  v277);
        }
        if ( v272 != 512 || v87 || *(_DWORD *)(*(_QWORD *)(a1 + 488) + 200LL) != v89 )
          xxxTrackMouseMove(*(struct tagDESKTOP **)&v273[4], (struct tagWND *)v89);
        if ( !v87 )
        {
          v90 = *(_QWORD *)(a1 + 488);
          if ( (*(_DWORD *)(v90 + 48) & 0x40) != 0
            && (v272 != 512 || !(unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD))PtInRect)(v90 + 204, v62)) )
          {
            ResetMouseHover((struct tagDESKTOP *)v90, v62);
          }
        }
        NextSysMsg = v293;
      }
      v66 = CheckPwndFilter(*(_QWORD *)&v273[4], v298);
      v11 = v282;
      LOBYTE(i) = v275;
      if ( v66 )
      {
        v67 = 0;
        LODWORD(v301) = 0;
        switch ( v272 )
        {
          case 0x201u:
            v44 = (unsigned __int8)IsMessageInputSourceTouch(&v340) == 0;
            v187 = *(_QWORD *)(a1 + 464);
            if ( v44 )
              *(_DWORD *)(v187 + 508) &= ~0x800000u;
            else
              *(_DWORD *)(v187 + 508) |= 0x800000u;
            v188 = IsMessageInputSourcePen(&v340);
            v189 = *(_QWORD *)(v316 + 464);
            v190 = *(_DWORD *)(v189 + 508);
            if ( v188 )
              v162 = v190 | 0x1000000;
            else
              v162 = v190 & 0xFEFFFFFF;
            *(_DWORD *)(v189 + 508) = v162;
LABEL_497:
            if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v273[4] + 136LL) + 8LL) + 8LL) & 8) != 0
              || *(_DWORD *)(*(_QWORD *)(a1 + 464) + 156LL) == 1
              || (unsigned int)IsMenuStarted(a1) )
            {
              v67 = 1;
              LODWORD(v301) = 1;
              v163 = *(_QWORD *)(a1 + 464);
              if ( (unsigned int)v343 <= *(_DWORD *)(v163 + 168) && !*(_DWORD *)(W32GetUserSessionState(v163) + 16216) )
              {
                v255 = *(_QWORD *)&v273[4] ? **(_QWORD **)&v273[4] : 0LL;
                v256 = *(_QWORD *)(a1 + 464);
                if ( v255 == *(_QWORD *)(v256 + 176)
                  && v272 == *(_DWORD *)(v256 + 160)
                  && (v272 != 523 || WORD1(v342[0]) == *(_WORD *)(v256 + 164)) )
                {
                  v323 = *(_DWORD *)(*(_QWORD *)(a1 + 464) + 184LL)
                       - *(_DWORD *)(*(_QWORD *)(W32GetUserSessionState(v256) + 19704) + 2040LL) / 2;
                  v324 = *(_DWORD *)(*(_QWORD *)(a1 + 464) + 188LL)
                       - *(_DWORD *)(*(_QWORD *)(W32GetUserSessionState(v323) + 19704) + 2044LL) / 2;
                  v257 = W32GetUserSessionState(v324);
                  v258 = *(_QWORD *)(a1 + 464);
                  v325 = *(_DWORD *)(v258 + 184) + *(_DWORD *)(*(_QWORD *)(v257 + 19704) + 2040LL) / 2;
                  v326 = *(_DWORD *)(*(_QWORD *)(a1 + 464) + 188LL)
                       + *(_DWORD *)(*(_QWORD *)(W32GetUserSessionState(v258) + 19704) + 2044LL) / 2;
                  if ( (unsigned int)PtInRect(&v323, *(_QWORD *)((char *)&v343 + 4)) )
                  {
                    v272 += 2;
                    v67 = 2;
                    LODWORD(v301) = 2;
                  }
                }
              }
            }
LABEL_499:
            v164 = *(_QWORD *)(a1 + 464);
            v165 = *(_DWORD *)(v164 + 508);
            if ( (v165 & 8) != 0 )
              *(_DWORD *)(v164 + 508) = v165 | 4;
            if ( v272 - 514 <= 0xA )
            {
              v166 = 1097;
              if ( _bittest(&v166, v272 - 514) )
              {
                if ( *(_DWORD *)(*(_QWORD *)(a1 + 464) + 168LL) && ((HIDWORD(v347) - 4) & 0xFFFFFFFB) == 0 )
                {
                  if ( HIDWORD(v347) == 4 )
                    TouchTimeFromCPLValue = GetTouchTimeFromCPLValue(300, 180, 5, 1);
                  else
                    TouchTimeFromCPLValue = GetPenDoubleClickTime();
                  *(_DWORD *)(*(_QWORD *)(a1 + 464) + 168LL) = v350 + TouchTimeFromCPLValue;
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
        if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v273[4] + 16LL) + 464LL) + 156LL) == 1 )
        {
          v272 -= 352;
          v279 = (unsigned int)v280;
        }
        v68 = MiPCheckMsgFilter(NextSysMsg, v272, v284, a5);
        v11 = v282;
        LOBYTE(i) = v275;
        if ( v68 )
        {
          if ( v281 )
            goto LABEL_75;
          if ( v272 - 512 > 0xE )
            break;
          v100 = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 520), 0, 0);
          LOBYTE(i) = v275;
          if ( (v100 & 0x8000) == 0 )
            break;
        }
      }
    }
    if ( (_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 520), 0, 0) & 0x100000) != 0 )
    {
      _InterlockedAnd((volatile signed __int32 *)(a1 + 520), 0xFFEFFFFF);
      xxxWindowEvent(0x800Bu, 0, -9, 0, 1);
    }
    v351[0] = *(_QWORD *)((char *)&v343 + 4);
    if ( *(_QWORD *)&v273[4] )
      v351[1] = **(_QWORD **)&v273[4];
    else
      v351[1] = 0;
    LODWORD(v352) = v280;
    *((_QWORD *)&v352 + 1) = *((_QWORD *)&v344 + 1);
    LODWORD(v353) = v342[0];
    if ( *(_DWORD *)v273 )
    {
      if ( v272 != 512 && v272 != 160 )
      {
        v288 = 1;
        if ( (unsigned int)xxxCallCtfHook(7, 0, v272, v351) )
          goto LABEL_51;
      }
    }
    if ( ((*(_DWORD *)(a1 + 712) | *(_DWORD *)(**(_QWORD **)(a1 + 496) + 16LL)) & 0x100) != 0 )
    {
      v288 = 1;
      if ( (unsigned int)xxxCallMouseHook(v272, v351, *(unsigned int *)v273) )
        goto LABEL_51;
    }
    if ( (unsigned int)PsGetWin32KFilterSet() == 5 )
    {
      v259 = *((_QWORD *)PtiCurrent() + 64);
      v286 = 0;
      v286 = *(_QWORD *)(v259 + 248) != 0;
      if ( v286 )
      {
        if ( xxxClientCallLocalMouseHooks(v272, v351, *(unsigned int *)v273) )
          goto LABEL_51;
      }
    }
    if ( (*(_DWORD *)(a1 + 1360) & 0x2000LL) == 0 && (!v280 || v280 == -2) )
    {
      v170 = 0;
      if ( v292 )
      {
        v261 = (unsigned int)IsIndependentInputWindow(*(const struct tagWND **)&v273[4])
             ? GetCompositionInputWindowUIOwner(v260)
             : *(struct tagWND **)&v273[4];
        TopLevelWindow = (const struct tagWND *)GetTopLevelWindow(v261);
        v170 = TopLevelWindow;
        if ( TopLevelWindow )
        {
          v170 = CoreWindowProp::GetCompositeAppFrameWindowOrSelf(TopLevelWindow);
          Win32HMOptionalThreadLock<tagWND>::Win32HMOptionalThreadLock<tagWND>(v338, a1, v170);
          v263 = 0;
          if ( v170 )
            v263 = *(_QWORD *)v170;
          xxxSendMessage(v170, 32, v263, (unsigned __int16)v280 | (LOWORD(v341[1]) << 16));
          Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)v338);
        }
      }
      if ( !v170 )
      {
        if ( *(_QWORD *)&v273[4] )
          v264 = **(_QWORD **)&v273[4];
        else
          v264 = 0;
        xxxSendMessage(*(_QWORD *)&v273[4], 32, v264, (unsigned __int16)v280 | (LOWORD(v341[1]) << 16));
      }
      if ( *(struct tagQMSG **)(*(_QWORD *)(a1 + 464) + 88LL) == NextSysMsg
        && NextSysMsg
        && (unsigned int)IsMiPActive(a1, NextSysMsg)
        && (*((_DWORD *)NextSysMsg + 25) & 0x400) != 0
        && (unsigned int)IsGenuineMouseInput((char *)NextSysMsg + 124)
        && (unsigned int)IsMiPMouseMessage(*((unsigned int *)NextSysMsg + 6)) )
      {
        memset_0(v354, 0, 0xA8u);
        GeneratePointerMessageFromMouse(
          (struct tagQMSG *)v354,
          v272,
          NextSysMsg,
          *(struct tagWND **)&v273[4],
          *(int *)v273);
        SetMiPPromotion(*(_QWORD *)(*(_QWORD *)&v273[4] + 16LL), DWORD2(v354[1]));
      }
      goto LABEL_51;
    }
    if ( *(struct tagQMSG **)(*(_QWORD *)(a1 + 464) + 88LL) != NextSysMsg )
      goto LABEL_75;
    memset_0(v354, 0, 0x60u);
    v70 = v354[0];
    v71 = v354[1];
    v72 = v354[2];
    v73 = v355;
    v301 = v356;
    *(_OWORD *)BugCheckParameter2 = v357;
    v74 = 0;
    v363 = v340;
    v364 = *(_OWORD *)v341;
    v365 = *(_OWORD *)v342;
    v366 = v343;
    v367 = v344;
    v368 = *(_OWORD *)&v345[0].x;
    v369 = v346;
    v370 = v347;
    v371 = v348;
    v372 = v349;
    v373 = v350;
    if ( NextSysMsg && (unsigned int)IsMiPActive(a1, NextSysMsg) )
    {
      DWORD2(v364) = v272;
      *(_QWORD *)&v365 = v279;
      if ( (*((_DWORD *)NextSysMsg + 25) & 0x400) != 0 )
      {
        memset_0(v354, 0, 0xA8u);
        if ( ShouldGenerateMipMessage((struct tagTHREADINFO *)a1, NextSysMsg, *(struct tagWND **)&v273[4], *(int *)v273) )
        {
          v75 = *(_QWORD *)(a1 + 1512);
          if ( v75 && (*(_DWORD *)v75 & 1) != 0 )
          {
            v70 = *(_OWORD *)(v75 + 24);
            v71 = *(_OWORD *)(v75 + 40);
            v72 = *(_OWORD *)(v75 + 56);
            v73 = *(_OWORD *)(v75 + 72);
            v301 = *(_OWORD *)(v75 + 88);
            *(_OWORD *)BugCheckParameter2 = *(_OWORD *)(v75 + 104);
            v74 = 1;
          }
          if ( GeneratePointerMessageFromMouse(
                 (struct tagQMSG *)v354,
                 v272,
                 NextSysMsg,
                 *(struct tagWND **)&v273[4],
                 *(int *)v273) )
          {
            v340 = v354[0];
            *(_OWORD *)v341 = v354[1];
            *(_OWORD *)v342 = v354[2];
            v343 = v355;
            v344 = v356;
            *(_OWORD *)&v345[0].x = v357;
            v346 = v358;
            v347 = v359;
            v348 = v360;
            v349 = v361;
            v350 = v362;
            v24 = 1;
            v291 = 1;
            v151 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v354[1], 8));
            if ( v151 == 582 && (unsigned int)IsMiPEnabledForWindow(*(_QWORD *)&v273[4]) )
            {
              if ( v69 )
                v69 = **(_QWORD **)&v273[4];
              else
                v69 = 0;
              *(_QWORD *)(*(_QWORD *)(a1 + 464) + 560LL) = v69;
            }
            else if ( ((v151 - 579) & 0xFFFFFFFB) == 0 )
            {
              *(_QWORD *)(*(_QWORD *)(a1 + 464) + 560LL) = 0;
            }
          }
        }
        if ( *(_DWORD *)v273 )
        {
          *((_DWORD *)NextSysMsg + 25) &= ~0x400u;
          goto LABEL_189;
        }
LABEL_190:
        v9 = 1;
        goto LABEL_191;
      }
      if ( !*(_DWORD *)v273 )
        goto LABEL_190;
      if ( (unsigned int)IsMiPMouseMessage(*((unsigned int *)NextSysMsg + 6)) )
      {
        if ( (unsigned int)IsGenuineMouseInput((char *)NextSysMsg + 124) )
        {
          v114 = *(unsigned int **)(a1 + 1512);
          if ( v114 )
          {
            v69 = *v114;
            if ( (v69 & 2) == 0 && (v69 & 4) == 0 )
            {
              v9 = 1;
              xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v340, 1);
              goto LABEL_845;
            }
          }
        }
        v115 = *(_DWORD **)(a1 + 1512);
        if ( v115 )
          *v115 &= ~2u;
      }
    }
LABEL_189:
    if ( !*(_DWORD *)v273 )
      goto LABEL_190;
    v116 = W32GetUserSessionState(v69);
    if ( DWORD2(v364) == 512 || DWORD2(v364) == 160 )
    {
      v117 = *(_QWORD *)&v273[4] ? **(_QWORD **)&v273[4] : 0LL;
      if ( v117 != *(_QWORD *)(v116 + 16288) && (unsigned int)IsGenuineMouseInput((char *)NextSysMsg + 124) )
      {
        LOBYTE(v118) = 1;
        v120 = HMValidateHandleNoSecure(*(_QWORD *)(v116 + 16288), v118);
        v121 = (struct tagWND *)v120;
        if ( v120 )
        {
          v152 = *(_QWORD *)(v120 + 16);
          if ( !*(_QWORD *)(v152 + 640)
            && (unsigned int)IsMiPEnabledForThread(v152)
            && (GetMiPWindowFlags(v121) & 1) == 0 )
          {
            v153 = (struct tagQ **)*((_QWORD *)v121 + 2);
            if ( v153 == (struct tagQ **)a1 )
            {
              v154 = *(_QWORD *)(a1 + 1512);
              v155 = *(_OWORD *)(v154 + 24);
              v156 = *(_OWORD *)(v154 + 40);
              v157 = *(_OWORD *)(v154 + 56);
              v158 = *(_OWORD *)(v154 + 72);
              v159 = *(_OWORD *)(v154 + 88);
              v160 = *(_OWORD *)(v154 + 104);
              if ( v74 )
              {
                *(_OWORD *)(v154 + 24) = v70;
                *(_OWORD *)(v154 + 40) = v71;
                *(_OWORD *)(v154 + 56) = v72;
                *(_OWORD *)(v154 + 72) = v73;
                *(_OWORD *)(v154 + 88) = v301;
                *(_OWORD *)(v154 + 104) = *(_OWORD *)BugCheckParameter2;
              }
              memset((char *)&v354[1] + 8, 0, 24);
              Win32HMThreadLockBase<tagWND,0,0>::Win32HMThreadLockBase<tagWND,0,0>(BugCheckParameter3, v121);
              FindTimer((_DWORD)v121, 65523, 2, 1, 0);
              if ( (unsigned int)IsMiPEnabledForWindow(v121) )
                xxxSendTransformableMessageTimeout(v161, 0x24Au, 0, 0, 0, 1, 0);
              if ( v74 )
              {
                v191 = *(_QWORD *)(a1 + 1512);
                *(_OWORD *)(v191 + 24) = v155;
                *(_OWORD *)(v191 + 40) = v156;
                *(_OWORD *)(v191 + 56) = v157;
                *(_OWORD *)(v191 + 72) = v158;
                *(_OWORD *)(v191 + 88) = v159;
                *(_OWORD *)(v191 + 104) = v160;
              }
              Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)BugCheckParameter3);
              NextSysMsg = v293;
            }
            else
            {
              PostEventMessageEx((struct tagTHREADINFO *)v153, v153[58], 0x15u, v121, 0, 0, 0, 0);
            }
          }
        }
        if ( v291 )
        {
          if ( *(_QWORD *)&v273[4] )
            v265 = **(_QWORD **)&v273[4];
          else
            v265 = 0;
          *(_QWORD *)(v116 + 16288) = v265;
        }
        else
        {
          *(_QWORD *)(v116 + 16288) = 0;
        }
      }
    }
    v24 = v291;
    if ( !v291 )
    {
      v127 = v67 - 1;
      if ( v127 )
      {
        if ( v127 == 1 )
          *(_DWORD *)(*(_QWORD *)(a1 + 464) + 168LL) = 0;
      }
      else
      {
        *(_DWORD *)(*(_QWORD *)(a1 + 464) + 160LL) = v341[1];
        v194 = v342[0] >> 16;
        *(_WORD *)(*(_QWORD *)(a1 + 464) + 164LL) = WORD1(v342[0]);
        v195 = W32GetUserSessionState(v194);
        *(_DWORD *)(*(_QWORD *)(a1 + 464) + 168LL) = v343 + *(_DWORD *)(v195 + 14664);
        if ( *(_QWORD *)&v273[4] )
          v196 = **(_QWORD **)&v273[4];
        else
          v196 = 0;
        *(_QWORD *)(*(_QWORD *)(a1 + 464) + 176LL) = v196;
        *(_QWORD *)(*(_QWORD *)(a1 + 464) + 184LL) = *(_QWORD *)((char *)&v343 + 4);
      }
    }
    v119 = (const struct tagQMSG *)&v340;
    if ( v24 )
      v119 = (const struct tagQMSG *)&v363;
    if ( xxxMouseActivate((struct tagTHREADINFO *)a1, *(struct tagWND **)&v273[4], v119, v280) == 1 )
    {
      v9 = 1;
      goto LABEL_51;
    }
    if ( !*(_DWORD *)v273 )
      goto LABEL_190;
    v9 = 1;
    xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v340, 1);
LABEL_191:
    if ( *(_DWORD *)v273 && v288 && ((*(_BYTE *)(a1 + 712) | *(_BYTE *)(**(_QWORD **)(a1 + 496) + 16LL)) & 0x40) != 0 )
      xxxCallHook(6, v272, (__int64)v351, 5);
    v288 = 0;
    v278 = (void *)((LOWORD(v277.y) << 16) | LOWORD(v277.x));
    if ( v272 >= 0x200 )
      v279 = (unsigned int)GetMouseKeyFlags(*(_QWORD *)(a1 + 464));
    if ( (v272 - 171 <= 2 || v272 - 523 <= 2) && !v24 )
      v279 |= v342[0];
    if ( v280 == 5 )
    {
      if ( *(_DWORD *)v273 )
      {
        v266 = *(_QWORD *)(a1 + 640);
        if ( v266 )
        {
          if ( (*(_DWORD *)(v266 + 8) & 0x100) != 0 && *(_QWORD *)v266 && (**(_DWORD **)v266 & 1) != 0 )
          {
            MenuStateOwnerLockxxxUnlock::MenuStateOwnerLockxxxUnlock(
              (MenuStateOwnerLockxxxUnlock *)v322,
              *(struct tagMENUSTATE **)(a1 + 640));
            if ( !(unsigned int)xxxCallHandleMenuMessages(v266, *(_DWORD *)&v273[4], v272, v279, (__int64)v278) )
            {
              MenuStateOwnerLockxxxUnlock::~MenuStateOwnerLockxxxUnlock((MenuStateOwnerLockxxxUnlock *)v322);
              break;
            }
            MenuStateOwnerLockxxxUnlock::~MenuStateOwnerLockxxxUnlock((MenuStateOwnerLockxxxUnlock *)v322);
LABEL_845:
            v16 = FLOAT_1_0;
LABEL_846:
            v11 = v282;
            continue;
          }
        }
      }
    }
    break;
  }
  if ( !v24 )
    goto LABEL_198;
  v16 = FLOAT_1_0;
LABEL_210:
  v82 = v284;
LABEL_211:
  if ( ((HIDWORD(v347) - 2) & 0xFFFFFFCF) == 0 && HIDWORD(v347) != 50 )
  {
    v272 = (unsigned int)v341[1];
    v279 = v342[0];
    v278 = (void *)v342[1];
LABEL_214:
    if ( *(_DWORD *)v273 )
    {
      if ( !*(_QWORD *)(a1 + 640) && (unsigned int)IsMiPEnabledForThread(a1) && v24 )
      {
        if ( *(_QWORD *)&v273[4] )
          v83 = **(_QWORD **)&v273[4];
        else
          v83 = 0;
        *(_QWORD *)(*(_QWORD *)(a1 + 1512) + 48LL) = v83;
        v84 = *(_QWORD *)(a1 + 1512);
        v85 = *(_DWORD *)(v84 + 36);
        if ( (v85 & 0x400000) != 0 && (*(_DWORD *)(*(_QWORD *)&v273[4] + 380LL) & 0x40000000) == 0 )
          *(_DWORD *)(v84 + 36) = v85 & 0xFFBFFFFF;
        MiPWindowFlags = GetMiPWindowFlags(*(struct tagWND **)&v273[4]);
        SetMiPWindowFlags(*(struct tagWND **)&v273[4], MiPWindowFlags & 0xFFFFFFFFFFFFFFFEuLL);
        if ( ((LODWORD(v341[1]) - 578) & 0xFFFFFFFB) != 0 )
        {
          if ( ((LODWORD(v341[1]) - 579) & 0xFFFFFFFB) == 0 )
            **(_DWORD **)(a1 + 1512) &= ~8u;
        }
        else
        {
          v267 = 0;
          if ( LODWORD(v341[1]) == 578 )
            v267 = 8;
          **(_DWORD **)(a1 + 1512) = v267 | **(_DWORD **)(a1 + 1512) & 0xFFFFFFF7;
        }
      }
      else
      {
        xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v340, 1);
      }
    }
    if ( (unsigned int)IsPointerMessageTouchpad((struct tagTHREADINFO *)a1, v342[1], v24) )
    {
      if ( !*(_DWORD *)v273 && !ShouldReceiveTouchpadMessages((const struct tagTHREADINFO *)a1, v341[0]) )
        xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v340, 1);
      if ( v272 == 595 )
        v278 = (void *)-1LL;
    }
    goto LABEL_198;
  }
  EtwTraceBeginPointerMessageRetrieve(NextSysMsg, LOWORD(v342[0]), LODWORD(v341[1]));
  v374[0] = *(_OWORD *)NextSysMsg;
  v374[1] = *((_OWORD *)NextSysMsg + 1);
  v374[2] = *((_OWORD *)NextSysMsg + 2);
  v374[3] = *((_OWORD *)NextSysMsg + 3);
  v374[4] = *((_OWORD *)NextSysMsg + 4);
  v374[5] = *((_OWORD *)NextSysMsg + 5);
  v374[6] = *((_OWORD *)NextSysMsg + 6);
  v374[7] = *((_OWORD *)NextSysMsg + 7);
  v374[8] = *((_OWORD *)NextSysMsg + 8);
  v374[9] = *((_OWORD *)NextSysMsg + 9);
  v375 = *((_QWORD *)NextSysMsg + 20);
  v94 = (unsigned int)xxxRetrievePointerInputMessage(
                        a1,
                        v298,
                        v82,
                        a5,
                        1,
                        0,
                        (int *)v273,
                        NextSysMsg,
                        (__int64)&v273[4],
                        (__int64)&v272,
                        (__int64)&v279,
                        (__int64)&v278,
                        &v281,
                        v294);
  InputTraceLogging::Pointer::RetrieveMessage(v374, 0, v94);
  EtwTraceEndPointerMessageRetrieve(v374, LOWORD(v342[0]), LODWORD(v341[1]));
  v95 = *(_QWORD *)&v273[4];
  if ( *(_QWORD *)&v273[4] )
    Win32HM_ExchangeThreadLock<1>(*(_QWORD *)&v273[4], v312);
  v96 = v94 - 1;
  if ( !v96 )
    goto LABEL_214;
  v97 = v96 - 1;
  if ( v97 )
  {
    v98 = v97 - 1;
    if ( v98 )
    {
      *v294 = 0;
      if ( v98 == 1 )
      {
        v11 = v282;
        goto LABEL_23;
      }
    }
    else
    {
      xxxDefPointerProc(v95, LODWORD(v341[1]), v342[0], v342[1]);
      *v294 = 0;
    }
    goto LABEL_51;
  }
  if ( !v281 )
    goto LABEL_75;
  v296 = *(_QWORD *)(*(_QWORD *)&v273[4] + 16LL);
  v237 = v296;
  v238 = (Win32RawLockedW32Thread *)v334;
LABEL_734:
  Win32RawLockedW32Thread::Exchange(v238, (struct _W32THREAD *)v237);
LABEL_76:
  *(_QWORD *)(*(_QWORD *)(a1 + 464) + 80LL) = 0;
  if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20000) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
  {
    v9 = 0;
  }
  v32 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v9 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v104 = *(_QWORD *)(a1 + 464);
    v105 = *(_QWORD *)(v104 + 72);
    v106 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v107) = v32;
    LOBYTE(v108) = v9;
    WPP_RECORDER_AND_TRACE_SF_qqq(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v108,
      v107,
      *(_QWORD *)(v106 + 69152),
      4,
      18,
      36,
      (__int64)WPP_49cdbed1bece331d44f23b214bd7a204_Traceguids,
      v104,
      a1,
      v105);
  }
  *(_QWORD *)(*(_QWORD *)(a1 + 464) + 72LL) = 0;
  **(_DWORD **)(a1 + 480) &= ~1u;
  v33 = v295;
  v34 = v300;
  v35 = v302;
  v36 = v296;
  if ( v309 )
  {
    SetWakeBit(v309, 16385);
    ClearWakeBit((struct tagTHREADINFO *)a1, 0x4001u, 0);
  }
  else if ( !v295 && !v300 && !v302 && !v296 )
  {
    v37 = *(_QWORD *)(a1 + 464);
    if ( !*(_DWORD *)(v37 + 40) )
      _InterlockedAnd(
        (volatile signed __int32 *)(*(_QWORD *)(a1 + 480) + 8LL),
        (*(_DWORD *)(v37 + 508) >> 4) & 2 | 0xFFFF83F8);
    goto LABEL_87;
  }
  if ( v33 )
  {
    SetWakeBit(v33, 16390);
    ClearWakeBit((struct tagTHREADINFO *)a1, 0x4006u, 0);
  }
  if ( v35 )
  {
    SetWakeBit(v35, 17408);
    ClearWakeBit((struct tagTHREADINFO *)a1, 0x4400u, 0);
  }
  if ( v36 )
  {
    SetWakeBit(v36, 20480);
    ClearWakeBit((struct tagTHREADINFO *)a1, 0x5000u, 0);
  }
  if ( v34 )
  {
    SetWakeBit(v34, 8256);
    _InterlockedAnd((volatile signed __int32 *)(*(_QWORD *)(a1 + 480) + 8LL), 0xFFFFDFFF);
  }
LABEL_87:
  if ( v287[0] )
  {
    v38 = PtiCurrent();
    *((_QWORD *)v38 + 170) &= ~0x1000000000uLL;
  }
  Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)v312);
  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v334);
  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v335);
  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v333);
  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v331);
  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v332);
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
