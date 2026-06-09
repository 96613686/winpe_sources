# xxxScanSysQueue(tagTHREADINFO *,tagMSG *,tagWND *,uint,uint,ulong,ulong,tagQMSG * *)

- ea: `0x1401ca020`
- end: `0x1401cf05e`
- name: `?xxxScanSysQueue@@YA?AW4_SCANSYSQUEUERESULT@@PEAUtagTHREADINFO@@PEAUtagMSG@@PEAUtagWND@@IIKKPEAPEAUtagQMSG@@@Z`
- size: `20542`
- prototype: `__int64 __fastcall(__int64, struct tagMSG *, __int64, unsigned int, unsigned int, char, unsigned int, struct tagQMSG **)`
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
        unsigned int a7,
        struct tagQMSG **a8)
{
  char v9; // r12
  __int64 v10; // rdx
  struct tagQ **v11; // rbx
  __int16 v12; // r9
  struct tagQ *v13; // r15
  char v14; // bl
  bool v15; // di
  __int64 v16; // r8
  __int64 v17; // r9
  float v18; // xmm6_4
  char v19; // r15
  __int64 i; // rcx
  int v21; // r13d
  struct tagQ *v22; // rdx
  struct tagQMSG *NextSysMsg; // rdi
  const struct tagUIPI_INFO *v24; // r8
  _QWORD *v25; // r9
  char v26; // r15
  __int64 v27; // rdx
  __int64 v28; // rdx
  int v29; // r15d
  __int64 v30; // rdx
  __int64 v31; // rax
  struct tagQ *v32; // rax
  int v33; // r15d
  int v34; // eax
  __int64 v35; // r15
  __int64 v36; // r8
  __int64 v37; // r9
  char v38; // r15
  bool v39; // r15
  __int64 v40; // rbx
  __int64 v41; // r12
  struct _W32THREAD *v42; // r15
  __int64 v43; // rdi
  __int64 v44; // rcx
  struct tagTHREADINFO *v45; // rax
  unsigned __int64 v47; // rax
  struct tagTHREADINFO *v48; // rax
  char *v49; // rax
  int v50; // eax
  bool v51; // zf
  int v52; // ecx
  int v53; // ecx
  int v54; // ecx
  int v55; // r8d
  __int64 v56; // rax
  HWND *v57; // rdx
  __int64 v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // r8
  __int64 v61; // r9
  struct tagWND *v62; // rbx
  int v63; // r9d
  __int64 v64; // rdx
  HWND v65; // rbx
  struct tagWND *v66; // rax
  __int64 v67; // rdx
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 v70; // r9
  int v71; // ebx
  __int64 v72; // rcx
  __int64 v73; // rcx
  struct tagPOINT v74; // rbx
  __int64 v75; // rcx
  int v76; // edx
  __int64 v77; // rdx
  int v78; // eax
  __int64 v79; // rdx
  __int64 v80; // r8
  __int64 v81; // r9
  int v82; // r13d
  int v83; // eax
  __int64 v84; // rdx
  __int64 v85; // rcx
  __int64 v86; // r8
  __int64 v87; // r9
  __int128 v88; // xmm12
  __int128 v89; // xmm13
  __int128 v90; // xmm14
  __int128 v91; // xmm15
  int v92; // r12d
  __int64 v93; // rcx
  __int64 v94; // rdx
  char v95; // bl
  struct tagMSG *v96; // r15
  __int64 v97; // rcx
  int v98; // ecx
  __int64 v99; // rdx
  unsigned int v100; // r13d
  __int64 v101; // rcx
  __int64 v102; // r8
  int v103; // edx
  unsigned __int64 v104; // rax
  BOOL v105; // edi
  Scrollbar::NonClient *v106; // rcx
  unsigned int v107; // eax
  __int64 v108; // r8
  __int64 UserSessionState; // rax
  int v110; // r8d
  int v111; // edx
  __int64 v112; // rbx
  __int64 v113; // rcx
  int v114; // ebx
  int v115; // ebx
  int v116; // ebx
  _DWORD *v117; // rax
  __int16 v118; // ax
  _QWORD *v119; // rax
  __int64 v120; // rcx
  LONG v121; // eax
  __int64 v122; // rdi
  __int64 v123; // rbx
  __int64 v124; // rax
  int v125; // r8d
  int v126; // edx
  char v127; // r13
  int v128; // eax
  int v129; // eax
  unsigned int v130; // eax
  __int64 v131; // rax
  unsigned int *v132; // rax
  _DWORD *v133; // rax
  __int64 v134; // rdx
  __int64 v135; // r8
  __int64 v136; // r9
  __int64 v137; // r15
  __int64 v138; // rcx
  const struct tagQMSG *v139; // r8
  __int64 v140; // rax
  struct tagWND *v141; // rbx
  unsigned __int64 v142; // rcx
  struct tagQ *v143; // rax
  __int64 v144; // rcx
  __int64 v145; // rcx
  int v146; // eax
  int v147; // r13d
  bool v148; // al
  __int64 v149; // rax
  struct tagWND *v150; // r8
  float *v151; // rbx
  const struct tagWND *TopLevelOrDpiBoundaryWindow; // rax
  __int64 v153; // rdx
  __int64 v154; // r8
  __int64 v155; // r9
  const struct tagWND *v156; // rdi
  char v157; // di
  char v158; // bl
  __int64 v159; // rdx
  __int64 v160; // rcx
  __int64 v161; // r8
  __int64 v162; // r9
  int v163; // r15d
  int v164; // r13d
  __int64 v165; // rdi
  unsigned int v166; // ebx
  __int64 v167; // r8
  __int64 v168; // r9
  __int64 v169; // rax
  __int64 v170; // rcx
  __int64 v171; // rdx
  _DWORD *v172; // r15
  __int64 v173; // r9
  __int64 v174; // rcx
  __int64 v175; // rcx
  int v176; // eax
  struct tagWND *v177; // rbx
  int v178; // eax
  unsigned int MouseKeyFlags; // eax
  __int64 v180; // rcx
  char MiPWindowFlags; // al
  struct tagQ **v182; // rcx
  __int64 v183; // rax
  __int128 v184; // xmm6
  __int128 v185; // xmm7
  __int128 v186; // xmm8
  __int128 v187; // xmm9
  __int128 v188; // xmm10
  __int128 v189; // xmm11
  struct tagWND *v190; // rcx
  unsigned int v191; // ecx
  __int64 v192; // rcx
  __int64 v193; // rcx
  int v194; // eax
  int v195; // ecx
  int TouchTimeFromCPLValue; // eax
  __int64 v197; // rdx
  int v198; // eax
  struct tagWND *v199; // rbx
  __int64 v200; // rcx
  __int64 v201; // rdx
  __int64 v202; // rcx
  __int64 v203; // r8
  __int64 v204; // r9
  char v205; // r8
  unsigned int v206; // ecx
  unsigned int v207; // edx
  __int64 v208; // rcx
  _QWORD *v209; // rax
  unsigned __int64 v210; // rbx
  ULONG_PTR v211; // r13
  unsigned __int64 v212; // r9
  unsigned int v213; // eax
  __int64 ThreadDesktopWindow; // rax
  int v215; // ebx
  __int64 v216; // rbx
  __int64 v217; // rdx
  __int64 v218; // rdx
  struct tagWND *v219; // rax
  __int64 v220; // rax
  char v221; // al
  int v222; // ecx
  __int64 v223; // rax
  __int64 v224; // r8
  __int64 v225; // r9
  char v226; // r15
  unsigned int v227; // r15d
  unsigned __int64 v228; // rcx
  __int64 v229; // rax
  __int64 v230; // rcx
  struct tagTHREADINFO *BugCheckParameter4; // rax
  float v232; // xmm2_4
  __int64 v233; // r8
  struct tagQ *v234; // rdi
  __int64 v235; // rbx
  __int64 v236; // rax
  int v237; // r8d
  int v238; // edx
  struct tagQ *v239; // rdi
  __int64 v240; // rbx
  __int64 v241; // rax
  int v242; // r8d
  int v243; // edx
  int v244; // r15d
  struct tagQ *v245; // rdi
  __int64 v246; // rbx
  __int64 v247; // rax
  int v248; // r8d
  int v249; // edx
  struct tagQ *v250; // rdi
  __int64 v251; // rbx
  __int64 v252; // rax
  int v253; // r8d
  int v254; // edx
  int v255; // ebx
  struct tagWND *CompositeAppFrameWindowOrSelf; // rdi
  BOOL v257; // ebx
  struct tagQ *v258; // rcx
  __int64 v259; // rax
  __int64 v260; // rcx
  __int64 v261; // rcx
  __int64 v262; // rbx
  struct tagQ *v263; // rdi
  __int64 v264; // rbx
  __int64 v265; // rax
  int v266; // r8d
  int v267; // edx
  __int64 v268; // rdx
  HWND *v269; // rdx
  __int64 v270; // rdx
  __int64 v271; // rdx
  Win32RawLockedW32Thread *v272; // rcx
  int v273; // eax
  int v274; // r9d
  _DWORD *v275; // rax
  _DWORD *v276; // rax
  __int64 v277; // rcx
  __int64 v278; // rcx
  __int64 v279; // rax
  __int64 v280; // r8
  __int64 v281; // rdx
  __int64 v282; // rax
  int v283; // r8d
  int v284; // edx
  __int64 v285; // rdx
  __int64 v286; // rax
  __int64 v287; // rcx
  LONG v288; // eax
  __int64 v289; // rdx
  __int64 v290; // r8
  __int64 v291; // r9
  __int64 v292; // rax
  __int64 v293; // rcx
  __int64 v294; // rdx
  __int64 v295; // kr00_8
  __int64 v296; // r8
  __int64 v297; // r9
  __int64 v298; // rdx
  __int64 v299; // kr08_8
  __int64 v300; // r8
  __int64 v301; // r9
  __int64 v302; // rax
  __int64 v303; // rcx
  __int64 v304; // rdx
  __int64 v305; // rt2
  __int64 v306; // r8
  __int64 v307; // r9
  __int64 v308; // rcx
  const struct tagWND *v309; // rcx
  struct tagWND *v310; // rax
  const struct tagWND *TopLevelWindow; // rax
  __int64 v312; // r8
  __int64 v313; // r8
  __int64 v314; // rax
  __int64 v315; // rbx
  int v316; // edx
  int v317; // eax
  struct tagTHREADINFO *v318; // rcx
  int InteractiveControlInputMessage; // eax
  char v320; // [rsp+48h] [rbp-690h]
  unsigned int v321; // [rsp+70h] [rbp-668h] BYREF
  _BYTE v322[12]; // [rsp+74h] [rbp-664h] BYREF
  int v323; // [rsp+80h] [rbp-658h]
  BOOL v324; // [rsp+84h] [rbp-654h]
  bool v325; // [rsp+88h] [rbp-650h]
  struct tagPOINT v326; // [rsp+90h] [rbp-648h] BYREF
  void *v327; // [rsp+98h] [rbp-640h] BYREF
  unsigned __int64 v328; // [rsp+A0h] [rbp-638h] BYREF
  int v329; // [rsp+A8h] [rbp-630h] BYREF
  int v330; // [rsp+ACh] [rbp-62Ch] BYREF
  struct tagQ **v331; // [rsp+B0h] [rbp-628h]
  unsigned int v332; // [rsp+B8h] [rbp-620h]
  unsigned int v333; // [rsp+BCh] [rbp-61Ch]
  bool v334; // [rsp+C0h] [rbp-618h]
  bool v335; // [rsp+C1h] [rbp-617h]
  char v336[2]; // [rsp+C2h] [rbp-616h] BYREF
  int v337; // [rsp+C4h] [rbp-614h]
  int v338; // [rsp+C8h] [rbp-610h]
  unsigned int v339; // [rsp+CCh] [rbp-60Ch]
  int v340; // [rsp+D0h] [rbp-608h]
  int v341; // [rsp+D4h] [rbp-604h]
  struct tagQMSG *v342; // [rsp+D8h] [rbp-600h]
  struct tagQMSG **v343; // [rsp+E0h] [rbp-5F8h]
  __int64 v344; // [rsp+E8h] [rbp-5F0h]
  __int64 v345; // [rsp+F0h] [rbp-5E8h]
  ULONG_PTR v346; // [rsp+F8h] [rbp-5E0h]
  __int64 v347; // [rsp+100h] [rbp-5D8h]
  int v348; // [rsp+108h] [rbp-5D0h]
  __int64 v349; // [rsp+110h] [rbp-5C8h]
  __int128 v350; // [rsp+118h] [rbp-5C0h]
  struct _W32THREAD *v351; // [rsp+128h] [rbp-5B0h]
  int v352; // [rsp+130h] [rbp-5A8h]
  int v353; // [rsp+134h] [rbp-5A4h]
  unsigned int v354; // [rsp+138h] [rbp-5A0h]
  unsigned int v355; // [rsp+140h] [rbp-598h]
  unsigned int v356; // [rsp+144h] [rbp-594h]
  struct tagTHREADINFO *v357; // [rsp+148h] [rbp-590h]
  struct _W32THREAD *v358; // [rsp+150h] [rbp-588h]
  ULONG_PTR BugCheckParameter2[2]; // [rsp+158h] [rbp-580h] BYREF
  __int64 v360; // [rsp+168h] [rbp-570h]
  ULONG_PTR v361[2]; // [rsp+170h] [rbp-568h] BYREF
  __int64 v362; // [rsp+180h] [rbp-558h]
  struct tagMSG *v363; // [rsp+188h] [rbp-550h]
  __int64 v364; // [rsp+190h] [rbp-548h]
  __int64 v365; // [rsp+1A8h] [rbp-530h]
  struct tagMSG *v366; // [rsp+1B0h] [rbp-528h]
  __int64 v367; // [rsp+1C8h] [rbp-510h]
  __int64 v368; // [rsp+1D0h] [rbp-508h]
  __int64 v369; // [rsp+1D8h] [rbp-500h]
  __int64 v370; // [rsp+1E0h] [rbp-4F8h]
  char v371[8]; // [rsp+1E8h] [rbp-4F0h] BYREF
  unsigned int v372; // [rsp+1F0h] [rbp-4E8h] BYREF
  unsigned int v373; // [rsp+1F4h] [rbp-4E4h]
  int v374; // [rsp+1F8h] [rbp-4E0h]
  int v375; // [rsp+1FCh] [rbp-4DCh]
  int v376; // [rsp+200h] [rbp-4D8h]
  struct tagMSG *v377; // [rsp+208h] [rbp-4D0h]
  ULONG_PTR v378[2]; // [rsp+210h] [rbp-4C8h] BYREF
  __int64 v379; // [rsp+220h] [rbp-4B8h]
  _BYTE v380[24]; // [rsp+228h] [rbp-4B0h] BYREF
  _BYTE v381[24]; // [rsp+240h] [rbp-498h] BYREF
  _BYTE v382[24]; // [rsp+258h] [rbp-480h] BYREF
  _BYTE v383[24]; // [rsp+270h] [rbp-468h] BYREF
  _BYTE v384[48]; // [rsp+288h] [rbp-450h] BYREF
  ULONG_PTR v385[2]; // [rsp+2B8h] [rbp-420h] BYREF
  ULONG_PTR v386[2]; // [rsp+2C8h] [rbp-410h] BYREF
  ULONG_PTR v387[3]; // [rsp+2D8h] [rbp-400h] BYREF
  ULONG_PTR BugCheckParameter3[2]; // [rsp+2F0h] [rbp-3E8h] BYREF
  __int128 v389; // [rsp+300h] [rbp-3D8h] BYREF
  HWND v390[2]; // [rsp+310h] [rbp-3C8h]
  unsigned __int64 v391[2]; // [rsp+320h] [rbp-3B8h]
  __int128 v392; // [rsp+330h] [rbp-3A8h]
  __int128 v393; // [rsp+340h] [rbp-398h]
  struct tagPOINT v394[2]; // [rsp+350h] [rbp-388h] BYREF
  __int128 v395; // [rsp+360h] [rbp-378h]
  __int128 v396; // [rsp+370h] [rbp-368h] BYREF
  __int128 v397; // [rsp+380h] [rbp-358h]
  __int128 v398; // [rsp+390h] [rbp-348h]
  __int64 v399; // [rsp+3A0h] [rbp-338h]
  __int64 v400[2]; // [rsp+3B0h] [rbp-328h] BYREF
  __int128 v401; // [rsp+3C0h] [rbp-318h]
  __int64 v402; // [rsp+3D0h] [rbp-308h]
  _OWORD v403[3]; // [rsp+3E0h] [rbp-2F8h] BYREF
  __int128 v404; // [rsp+410h] [rbp-2C8h]
  __int128 v405; // [rsp+420h] [rbp-2B8h]
  __int128 v406; // [rsp+430h] [rbp-2A8h]
  __int128 v407; // [rsp+440h] [rbp-298h]
  __int128 v408; // [rsp+450h] [rbp-288h]
  __int128 v409; // [rsp+460h] [rbp-278h]
  __int128 v410; // [rsp+470h] [rbp-268h]
  __int64 v411; // [rsp+480h] [rbp-258h]
  __int128 v412; // [rsp+490h] [rbp-248h] BYREF
  __int128 v413; // [rsp+4A0h] [rbp-238h]
  __int128 v414; // [rsp+4B0h] [rbp-228h]
  __int128 v415; // [rsp+4C0h] [rbp-218h]
  __int128 v416; // [rsp+4D0h] [rbp-208h]
  __int128 v417; // [rsp+4E0h] [rbp-1F8h]
  __int128 v418; // [rsp+4F0h] [rbp-1E8h]
  __int128 v419; // [rsp+500h] [rbp-1D8h]
  __int128 v420; // [rsp+510h] [rbp-1C8h]
  __int128 v421; // [rsp+520h] [rbp-1B8h]
  __int64 v422; // [rsp+530h] [rbp-1A8h]
  _OWORD v423[10]; // [rsp+540h] [rbp-198h] BYREF
  __int64 v424; // [rsp+5E0h] [rbp-F8h]

  v333 = a4;
  v347 = a3;
  v366 = a2;
  v362 = a1;
  v367 = a1;
  v377 = a2;
  v357 = (struct tagTHREADINFO *)a1;
  v368 = a1;
  v363 = a2;
  v370 = a3;
  v354 = a4;
  v343 = a8;
  memset_0(&v389, 0, 0xA8u);
  *(_DWORD *)&v322[8] = 0;
  v321 = 0;
  v328 = 0;
  v327 = 0;
  v326 = 0;
  v330 = 0;
  v329 = 0;
  *(_OWORD *)v400 = 0;
  v401 = 0;
  v402 = 0;
  v9 = 1;
  v10 = a6 & 1;
  *(_QWORD *)v322 = v10;
  *a8 = 0;
  v11 = (struct tagQ **)(a1 + 464);
  v331 = (struct tagQ **)(a1 + 464);
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
    v331 = (struct tagQ **)(a1 + 464);
  }
  v369 = a1 + 464;
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
      UserSessionState = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, v10, &WPP_GLOBAL_Control, a7);
      LOBYTE(v110) = v15;
      LOBYTE(v111) = v14;
      WPP_RECORDER_AND_TRACE_SF_qqq(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v111,
        v110,
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
    v11 = v331;
    *((_QWORD *)*v331 + 9) = a1;
    **(_DWORD **)(a1 + 480) |= 1u;
    LODWORD(v10) = *(_DWORD *)v322;
  }
  if ( (v12 & 0x1C07) != 0 )
  {
    v129 = *((_DWORD *)*v11 + 127);
    if ( (_DWORD)v10 )
      v130 = v129 & 0xFFFFFBFF;
    else
      v130 = v129 | 0x400;
    *((_DWORD *)*v11 + 127) = v130;
  }
  if ( *((_QWORD *)*v11 + 9) != a1 )
  {
    EtwTraceInputQueueLocked();
    return 2;
  }
  v365 = a1;
  v356 = a5;
  v379 = a1;
  v355 = v333;
  v352 = 0;
  v341 = 0;
  v332 = 0;
  v324 = 0;
  v325 = 0;
  v346 = 0;
  v348 = 0;
  v337 = 0;
  v323 = 0;
  v344 = 0;
  v364 = 0;
  v358 = 0;
  v349 = 0;
  v351 = 0;
  v345 = 0;
  Win32RawLockedW32Thread::Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v381, 0);
  Win32RawLockedW32Thread::Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v380, 0);
  Win32RawLockedW32Thread::Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v382, 0);
  Win32RawLockedW32Thread::Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v384, 0);
  Win32RawLockedW32Thread::Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v383, 0);
  *(_QWORD *)&v322[4] = 0;
  Win32HMOptionalThreadLock<tagWND>::Win32HMOptionalThreadLock<tagWND>(v361, a1, 0);
  CManageInScanSysQueueBit::CManageInScanSysQueueBit((CManageInScanSysQueueBit *)v336);
LABEL_13:
  v18 = FLOAT_1_0;
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
      || (v19 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
    {
      v19 = 0;
    }
    if ( v9 || v19 )
    {
      v234 = *v11;
      v235 = *((_QWORD *)*v11 + 11);
      v236 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v16, v17);
      LOBYTE(v237) = v19;
      LOBYTE(v238) = v9;
      WPP_RECORDER_AND_TRACE_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v238,
        v237,
        *(_QWORD *)(v236 + 69152),
        5,
        18,
        30,
        (__int64)WPP_49cdbed1bece331d44f23b214bd7a204_Traceguids,
        (char)v234,
        v235);
      v11 = v331;
    }
    *((_QWORD *)*v11 + 11) = 0;
LABEL_22:
    v9 = 1;
LABEL_23:
    LOBYTE(i) = v324;
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
                    v21 = (**(_DWORD **)(a1 + 512) >> 9) & 1;
                    v376 = v21;
                    v22 = *v11;
                    if ( *((_QWORD *)*v11 + 11) )
                    {
                      if ( !(_BYTE)i )
                      {
                        v324 = ((v332 - 1) & 0xFFFFFFFD) == 0;
                        v325 = ((v332 - 1) & 0xFFFFFFFD) == 0;
                      }
                    }
                    else
                    {
                      v332 = 0;
                      v324 = 0;
                      v325 = 0;
                    }
                    v328 = 0;
                    NextSysMsg = xxxGetNextSysMsg(
                                   (struct tagTHREADINFO *)a1,
                                   *((struct tagQMSG **)v22 + 11),
                                   (struct tagQMSG *)&v389);
                    v342 = NextSysMsg;
                    LODWORD(i) = (_DWORD)WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
                      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20000) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u )
                    {
                      v9 = 0;
                    }
                    if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
                      || (v26 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
                    {
                      v26 = 0;
                    }
                    if ( v9 || v26 )
                    {
                      v239 = *v11;
                      v240 = *((_QWORD *)*v11 + 11);
                      v241 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v24, v25);
                      v320 = (char)v239;
                      NextSysMsg = v342;
                      LOBYTE(v242) = v26;
                      LOBYTE(v243) = v9;
                      WPP_RECORDER_AND_TRACE_SF_qqq(
                        *((_QWORD *)WPP_GLOBAL_Control + 3),
                        v243,
                        v242,
                        *(_QWORD *)(v241 + 69152),
                        5,
                        18,
                        31,
                        (__int64)WPP_49cdbed1bece331d44f23b214bd7a204_Traceguids,
                        (char)v342,
                        v320,
                        v240);
                      v11 = v331;
                    }
                    *((_QWORD *)*v11 + 11) = NextSysMsg;
                    if ( !NextSysMsg )
                      goto LABEL_33;
                    v34 = DWORD1(v395);
                    if ( (BYTE4(v395) & 0x20) != 0 )
                    {
                      i = (__int64)v343;
                      *v343 = NextSysMsg;
                      *((_DWORD *)NextSysMsg + 25) |= 0x100u;
                      *(_DWORD *)v322 = 0;
                      v34 = DWORD1(v395);
                      if ( (DWORD1(v395) & 0x8000000) != 0 )
                      {
                        *(_DWORD *)(*(_QWORD *)i + 100LL) |= 0x8000000u;
                        v34 = DWORD1(v395);
                      }
                    }
                    if ( (v34 & 0x2000) == 0 )
                      break;
                    v244 = v332;
                    v9 = 1;
                    if ( *((_QWORD *)&v395 + 1) == a1 )
                      v244 = 1;
                    v332 = v244;
                    LOBYTE(i) = 1;
                    v324 = i;
                    v325 = 1;
                  }
                  LOBYTE(i) = v324;
                  if ( (v34 & 0x10000) == 0 )
                    break;
                  v9 = 1;
                  if ( *((_QWORD *)&v395 + 1) == a1 )
                  {
                    v332 = 3;
                    goto LABEL_23;
                  }
                }
                if ( (_DWORD)v395 == 4 && v324 )
                {
                  DeferSysPeekMsg(a1, 3);
                  goto LABEL_22;
                }
                if ( (v34 & 0x4000) == 0 )
                  break;
                v9 = 1;
                if ( *((_QWORD *)&v395 + 1) == a1 )
                  v332 = 2;
              }
              if ( (unsigned int)ShouldDeferMessage(v332, &v389) )
              {
                DeferSysPeekMsg(a1, 3);
                v332 = 3;
                goto LABEL_22;
              }
LABEL_33:
              if ( !*((_QWORD *)*v11 + 11) )
              {
                if ( a7 == 0x2000 )
                  _InterlockedAnd((volatile signed __int32 *)(*(_QWORD *)(a1 + 480) + 8LL), 0xFFFFDFFF);
                goto LABEL_75;
              }
              Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)v361);
              v9 = 1;
              LOBYTE(v27) = 1;
              *(_QWORD *)&v322[4] = HMValidateHandleNoSecure(v390[0], v27);
              Win32HM_LockIntoThread<1>(a1, *(_QWORD *)&v322[4], v361);
              v28 = (unsigned int)v395;
              if ( !(_DWORD)v395 )
                break;
              if ( (_DWORD)v395 == 4 )
              {
                LOBYTE(i) = v324;
                if ( *((_QWORD *)*v11 + 11) != *((_QWORD *)*v11 + 3) )
                  continue;
              }
              if ( (_DWORD)v395 != 9 || LODWORD(v390[1]) != 96 )
                goto LABEL_65;
              for ( i = *((_QWORD *)&v389 + 1); i && (unsigned int)IsHiddenByInputService(); i = *(_QWORD *)(i + 8) )
                ;
              v51 = i == 0;
              LOBYTE(i) = v324;
              if ( v51 )
              {
LABEL_65:
                v35 = *((_QWORD *)&v395 + 1);
                if ( !*((_QWORD *)&v395 + 1) || *((_QWORD *)&v395 + 1) == a1 )
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
                    || (v38 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
                  {
                    v38 = 0;
                  }
                  if ( v9 || v38 )
                  {
                    v250 = *v11;
                    v251 = *((_QWORD *)*v11 + 11);
                    v252 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v36, v37);
                    LOBYTE(v253) = v38;
                    LOBYTE(v254) = v9;
                    WPP_RECORDER_AND_TRACE_SF_qq(
                      *((_QWORD *)WPP_GLOBAL_Control + 3),
                      v254,
                      v253,
                      *(_QWORD *)(v252 + 69152),
                      5,
                      18,
                      33,
                      (__int64)WPP_49cdbed1bece331d44f23b214bd7a204_Traceguids,
                      (char)v250,
                      v251);
                    v11 = v331;
                  }
                  *((_QWORD *)*v11 + 11) = 0;
                  xxxProcessEventMessage(a1, &v389);
                  v9 = 1;
                  goto LABEL_14;
                }
                if ( *(struct tagQ **)(*((_QWORD *)&v395 + 1) + 464LL) != *v11 )
                {
                  CleanEventMessage(*((struct tagQMSG **)*v11 + 11));
                  DelQEntry((char *)*v11 + 24, *((_QWORD *)*v11 + 11), 1);
                  goto LABEL_14;
                }
                ReferenceW32Thread(*((_QWORD *)&v395 + 1));
                ExchangeW32ThreadLock(v35, v382);
                if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20000) == 0
                  || (v127 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
                {
                  v127 = 0;
                }
                if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
                  || !*((_WORD *)WPP_GLOBAL_Control + 36) )
                {
                  v9 = 0;
                }
                if ( v127 || v9 )
                {
                  v245 = *v11;
                  v246 = *((_QWORD *)*v11 + 11);
                  v247 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v24, v25);
                  LOBYTE(v248) = v9;
                  LOBYTE(v249) = v127;
                  WPP_RECORDER_AND_TRACE_SF_qq(
                    *((_QWORD *)WPP_GLOBAL_Control + 3),
                    v249,
                    v248,
                    *(_QWORD *)(v247 + 69152),
                    5,
                    18,
                    32,
                    (__int64)WPP_49cdbed1bece331d44f23b214bd7a204_Traceguids,
                    (char)v245,
                    v246);
                  v11 = v331;
                }
                *((_QWORD *)*v11 + 11) = 0;
                v349 = v35;
                goto LABEL_75;
              }
            }
            i = v324;
          }
          while ( a7 == 0x2000 );
          v29 = 0;
          v340 = 0;
          v338 = 0;
          v339 = 0;
          v321 = (unsigned int)v390[1];
          if ( LODWORD(v390[1]) > 0x24A )
          {
            if ( LODWORD(v390[1]) <= 0x2ED )
            {
              if ( LODWORD(v390[1]) == 749 )
                goto LABEL_873;
              if ( LODWORD(v390[1]) == 593 || LODWORD(v390[1]) == 594 || LODWORD(v390[1]) == 595 )
                goto LABEL_210;
              v52 = LODWORD(v390[1]) - 744;
              v51 = LODWORD(v390[1]) == 744;
              goto LABEL_124;
            }
            if ( LODWORD(v390[1]) != 750 && LODWORD(v390[1]) != 751 && LODWORD(v390[1]) != 752 )
            {
              v52 = LODWORD(v390[1]) - 753;
              v51 = LODWORD(v390[1]) == 753;
LABEL_124:
              if ( v51 )
                goto LABEL_873;
              v53 = v52 - 1;
              if ( !v53 )
                goto LABEL_873;
              v54 = v53 - 1;
              if ( !v54 || (unsigned int)(v54 - 1) < 2 )
                goto LABEL_873;
              goto LABEL_128;
            }
LABEL_873:
            if ( v333 || a5 != -1 )
            {
              if ( v333 <= a5 )
              {
                if ( LODWORD(v390[1]) >= v355 && LODWORD(v390[1]) <= v356 )
                  goto LABEL_883;
                v317 = 0;
              }
              else
              {
                if ( LODWORD(v390[1]) >= v356 && LODWORD(v390[1]) <= v355 )
                  goto LABEL_75;
                v317 = 1;
              }
              if ( !v317 )
                goto LABEL_75;
            }
LABEL_883:
            if ( !(unsigned int)IsInsideMenuLoop(a1) )
            {
              if ( *(_DWORD *)v322 )
                xxxSkipSysMsgEx(v318, (struct tagQMSG *)&v389, 1);
              if ( !*(_QWORD *)&v322[4] )
                *(_QWORD *)&v322[4] = *(_QWORD *)(*(_QWORD *)(a1 + 464) + 120LL);
              v328 = v391[0];
              v327 = (void *)v391[1];
              InteractiveControlInputMessage = xxxRetrieveInteractiveControlInputMessage(
                                                 LOWORD(v391[0]),
                                                 WORD1(v391[0]));
              if ( InteractiveControlInputMessage == 1 )
                goto LABEL_198;
              if ( InteractiveControlInputMessage == 2 )
                goto LABEL_75;
            }
            goto LABEL_51;
          }
          if ( LODWORD(v390[1]) == 586 )
            goto LABEL_210;
          if ( LODWORD(v390[1]) > 0x11B )
            break;
          switch ( LODWORD(v390[1]) )
          {
            case 0x11B:
              goto LABEL_106;
            case 0x23:
              v328 = 0;
              v327 = (void *)v391[1];
              if ( !*(_QWORD *)&v322[4] || (v271 = *(_QWORD *)(*(_QWORD *)&v322[4] + 16LL), v271 == a1) )
              {
                if ( (unsigned int)MiPCheckMsgFilter(NextSysMsg, v321, v333, a5) )
                {
LABEL_736:
                  if ( *(_DWORD *)v322 )
                    xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v389, 1);
                  goto LABEL_198;
                }
              }
              else
              {
                if ( *(struct tagQ **)(v271 + 464) != *v11 )
                  goto LABEL_51;
                if ( !v344 )
                {
                  v344 = *(_QWORD *)(*(_QWORD *)&v322[4] + 16LL);
                  v272 = (Win32RawLockedW32Thread *)v380;
                  goto LABEL_734;
                }
              }
LABEL_75:
              v9 = 1;
              goto LABEL_76;
            case 0xFE:
LABEL_110:
              v328 = v391[0];
              v327 = (void *)v391[1];
              if ( !*(_QWORD *)&v322[4] )
                goto LABEL_51;
              if ( CheckCrossThreadInput(*(struct tagWND *const *)&v322[4], NextSysMsg, &v330, (int *)v322, v343) )
                goto LABEL_75;
              if ( v330 )
                goto LABEL_51;
              if ( !v333 && a5 == -1 )
              {
LABEL_749:
                v273 = CheckPwndFilter(*(_QWORD *)&v322[4], v347);
                LOBYTE(i) = v324;
                if ( v273 )
                  goto LABEL_736;
              }
              else
              {
                if ( v333 <= a5 )
                {
                  if ( v321 >= v333 && v321 <= a5 )
                    goto LABEL_749;
                  v50 = 0;
                  goto LABEL_748;
                }
                if ( v321 < a5 || (LOBYTE(i) = v324, v321 > v333) )
                {
                  v50 = 1;
LABEL_748:
                  LOBYTE(i) = v324;
                  if ( v50 )
                    goto LABEL_749;
                }
              }
              break;
            case 0xFF:
              v328 = v391[0];
              v327 = (void *)v391[1];
              if ( !DeleteHidDataIfAlreadyHandledByGRIB((struct tagTHREADINFO *)a1, v391[1]) )
              {
                *(_QWORD *)&v322[4] = 0;
                v30 = 0;
                if ( v327 )
                {
                  LOBYTE(v30) = 18;
                  v31 = HMValidateHandleNoSecure(v327, v30);
                  v30 = v31;
                  if ( v31 )
                    *(_QWORD *)&v322[4] = *(_QWORD *)(v31 + 24);
                }
                if ( !*(_QWORD *)&v322[4] )
                {
                  v32 = *v11;
                  *(_QWORD *)&v322[4] = *((_QWORD *)*v11 + 15);
                  if ( !*(_QWORD *)&v322[4] )
                  {
                    *(_QWORD *)&v322[4] = *((_QWORD *)v32 + 16);
                    if ( !*(_QWORD *)&v322[4] )
                    {
                      InputTraceLogging::RawInput::SSQResult(v327, 0);
                      goto LABEL_51;
                    }
                  }
                }
                if ( v30 && *(_QWORD *)(v30 + 16) != *(_QWORD *)(*(_QWORD *)&v322[4] + 16LL) )
                {
                  v353 = 0x20000;
                  MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 10065);
                }
                Win32HM_ExchangeThreadLock<1>(*(_QWORD *)&v322[4], v361);
                if ( CheckCrossThreadInput(*(struct tagWND *const *)&v322[4], NextSysMsg, &v330, (int *)v322, v343) )
                {
                  v268 = 0;
                  goto LABEL_713;
                }
                if ( !v330 )
                  goto LABEL_241;
                if ( *(struct tagQ **)(*(_QWORD *)(*(_QWORD *)&v322[4] + 16LL) + 464LL) != *v11 )
                  goto LABEL_51;
                if ( (unsigned int)IsInsideMenuLoop(a1) )
                {
                  v269 = *(HWND **)(**(_QWORD **)(a1 + 640) + 8LL);
                }
                else
                {
                  v270 = *(_QWORD *)(a1 + 704);
                  if ( v270 )
                    v269 = *(HWND **)(v270 + 16);
                  else
                    v269 = 0;
                }
                if ( v269 )
                  InputTraceLogging::RawInput::IgnoreModalLoop(v327, *v269);
                if ( !v351 )
                {
                  v351 = *(struct _W32THREAD **)(*(_QWORD *)&v322[4] + 16LL);
                  Win32RawLockedW32Thread::Exchange((Win32RawLockedW32Thread *)v384, v351);
                }
LABEL_241:
                if ( !v333 && a5 == -1 )
                  goto LABEL_243;
                if ( v333 > a5 )
                {
                  if ( v321 >= a5 && v321 <= v333 )
                    goto LABEL_302;
                  v128 = 1;
                }
                else
                {
                  if ( v321 >= v333 && v321 <= a5 )
                  {
LABEL_243:
                    if ( (unsigned int)CheckPwndFilter(*(_QWORD *)&v322[4], v347) )
                    {
                      if ( !v330 )
                      {
                        if ( *(_DWORD *)v322 )
                          xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v389, 1);
                        InputTraceLogging::RawInput::SSQResult(v327, 4);
                        goto LABEL_198;
                      }
                      v268 = 3;
LABEL_713:
                      InputTraceLogging::RawInput::SSQResult(v327, v268);
                      goto LABEL_76;
                    }
LABEL_302:
                    InputTraceLogging::RawInput::SSQResult(v327, 2);
                    goto LABEL_23;
                  }
                  v128 = 0;
                }
                if ( !v128 )
                  goto LABEL_302;
                goto LABEL_243;
              }
LABEL_51:
              v33 = v323;
              goto LABEL_52;
            case 0x100:
              goto LABEL_350;
            case 0x101:
LABEL_355:
              v328 = LOBYTE(v391[0]);
              v142 = v391[0];
              if ( LOBYTE(v391[0]) == 231 )
                v142 = 231;
              v391[0] = v142;
              if ( !*(_DWORD *)v322 || (WORD2(v395) & 0x8000) == 0 )
              {
                if ( *(_DWORD *)(W32GetUserSessionState(v142, v28, v24, v25) + 14224) )
                {
                  if ( (GetAppImeCompatFlags(0) & 0x800000) == 0 && BYTE2(v391[1]) == 41 )
                  {
                    if ( *(_DWORD *)v322 )
                    {
                      v258 = *v11;
                      if ( (*((_BYTE *)*v11 + 356) & 0x15) == 0
                        && (*((_BYTE *)v258 + 374) & 0x40) == 0
                        && (*((_BYTE *)v258 + 375) & 1) == 0 )
                      {
                        v259 = *((_QWORD *)v258 + 15);
                        *(_QWORD *)&v322[4] = v259;
                        if ( !v259 )
                        {
                          v259 = *((_QWORD *)v258 + 16);
                          *(_QWORD *)&v322[4] = v259;
                        }
                        if ( !v259 || *(_QWORD *)(v259 + 16) == a1 )
                        {
                          xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v389, 1);
                          if ( !v348 && *(_QWORD *)&v322[4] )
                          {
                            *(_QWORD *)&v403[0] = **(_QWORD **)&v322[4];
                            *((_QWORD *)&v403[0] + 1) = 80;
                            memset(&v403[1], 0, 32);
                            xxxCallCtfHook(3, 0, 1, v403);
                          }
                          goto LABEL_14;
                        }
                      }
                    }
                  }
                }
              }
              if ( v328 == 121 )
                v321 |= 4u;
              if ( (*((_BYTE *)*v11 + 356) & 4) != 0 && v328 == 27 )
                v321 |= 4u;
              if ( (_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 520), 0, 0) & 8) == 0 )
                v391[1] &= ~0x2000000uLL;
LABEL_364:
              v328 = LOBYTE(v391[0]);
              v143 = *v11;
              v144 = *((_QWORD *)*v11 + 15);
              *(_QWORD *)&v322[4] = v144;
              if ( !*((_QWORD *)v143 + 15) )
              {
                v144 = *((_QWORD *)v143 + 16);
                *(_QWORD *)&v322[4] = v144;
                if ( !v144 )
                  goto LABEL_51;
                if ( v321 - 256 <= 3 )
                  v321 += 4;
              }
              Win32HM_ExchangeThreadLock<1>(v144, v361);
              v145 = *(_QWORD *)(*(_QWORD *)&v322[4] + 16LL);
              v330 = v145 != v368;
              if ( v145 != v362 )
              {
                if ( *(struct tagQ **)(*(_QWORD *)(*(_QWORD *)&v322[4] + 16LL) + 464LL) != *v11 )
                  goto LABEL_51;
                if ( (unsigned int)IsInsideMenuLoop(a1) )
                {
                  v260 = *(_QWORD *)(**(_QWORD **)(a1 + 640) + 8LL);
                }
                else
                {
                  v261 = *(_QWORD *)(a1 + 704);
                  if ( v261 )
                    v260 = *(_QWORD *)(v261 + 16);
                  else
                    v260 = 0;
                }
                if ( v260 )
                {
                  *(_QWORD *)&v322[4] = v260;
                  v330 = *(_QWORD *)(v260 + 16) != v379;
                  Win32HM_ExchangeThreadLock<1>(v260, v361);
                }
                if ( !v358 )
                {
                  v358 = *(struct _W32THREAD **)(*(_QWORD *)&v322[4] + 16LL);
                  Win32RawLockedW32Thread::Exchange((Win32RawLockedW32Thread *)v381, v358);
                }
              }
              if ( v333 || a5 != -1 )
              {
                if ( v333 > a5 )
                {
                  if ( v321 < a5 || (LOBYTE(i) = v324, v321 > v333) )
                  {
                    v198 = 1;
                    goto LABEL_513;
                  }
                }
                else
                {
                  if ( v321 >= v333 && v321 <= a5 )
                    goto LABEL_368;
                  v198 = 0;
LABEL_513:
                  LOBYTE(i) = v324;
                  if ( v198 )
                    goto LABEL_368;
                }
              }
              else
              {
LABEL_368:
                v146 = CheckPwndFilter(*(_QWORD *)&v322[4], v347);
                LOBYTE(i) = v324;
                if ( v146 )
                {
                  if ( v330 )
                    goto LABEL_75;
                  if ( *(_DWORD *)v322 )
                  {
                    if ( (WORD2(v395) & 0x8000) != 0 )
                      goto LABEL_403;
                    if ( !(unsigned int)IsInsideMenuLoop(a1) )
                    {
                      if ( v328 == 93 && v321 == 257 )
                      {
                        if ( *(_QWORD *)&v322[4] )
                          v233 = **(_QWORD **)&v322[4];
                        else
                          LODWORD(v233) = 0;
                        PostTransformableMessage(*(_DWORD *)&v322[4], 123, v233, -1, 0);
                      }
                      if ( v328 == 112 && v321 == 256 )
                        PostMessage(*(_QWORD *)&v322[4], 77, 0);
                    }
                  }
                  if ( v328 == 16 && !v348 )
                  {
                    v262 = v391[1] & 0x1000000;
                    if ( ((unsigned __int8)(v262 != 0 ? 1 : 4) & *((_BYTE *)*v331 + 392)) != 0 )
                    {
                      if ( (unsigned int)IsDesktopApp(*(_QWORD *)(a1 + 456))
                        && (_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 520), 0, 0) & 8) == 0 )
                      {
                        v391[0] = (v262 != 0) + 160LL;
LABEL_681:
                        xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v389, 1);
                        goto LABEL_846;
                      }
                      v11 = v331;
                    }
                    else
                    {
                      v11 = v331;
                    }
                  }
                  v352 = *((unsigned __int8 *)*v11 + ((unsigned __int64)(unsigned __int8)v328 >> 2) + 352)
                       & (1 << (2 * (v328 & 3)));
                  if ( !v352 )
                    goto LABEL_403;
                  if ( *(_DWORD *)v322 )
                  {
                    if ( NextSysMsg )
                      *((_QWORD *)NextSysMsg + 5) |= 0x40000000uLL;
LABEL_403:
                    if ( *(_DWORD *)v322 )
                    {
                      if ( (WORD2(v395) & 0x8000) == 0 && NextSysMsg && (*(_DWORD *)(a1 + 1360) & 0x10000000) != 0 )
                        v346 = (ULONG_PTR)xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v389, 0);
                      else
                        xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v389, 1);
                    }
                  }
                  v327 = (void *)v391[1];
                  v328 = v391[0];
                  if ( v352 )
                    v327 = (void *)(v391[1] | 0x40000000);
                  if ( v321 == 257 || v321 == 261 )
                    v327 = (void *)((unsigned __int64)v327 | 0x80000000);
                  if ( (*((_BYTE *)*v11 + 356) & 0x10) != 0 )
                    v327 = (void *)((unsigned __int64)v327 | 0x20000000);
                  if ( (unsigned int)IsMenuStarted(a1) )
                    v327 = (void *)((unsigned __int64)v327 | 0x10000000);
                  if ( (*(_DWORD *)(v159 + 508) & 0x4000) != 0 )
                    v327 = (void *)((unsigned __int64)v327 | 0x8000000);
                  if ( !v21 && !*(_QWORD *)(W32GetUserSessionState(v160, v159, v161, v162) + 12888)
                    || (WORD2(v395) & 0x8000) != 0 )
                  {
                    goto LABEL_416;
                  }
                  if ( !*(_DWORD *)v322 )
                  {
LABEL_417:
                    LOBYTE(v163) = v338;
                    goto LABEL_418;
                  }
                  if ( (unsigned int)IsMenuStarted(a1)
                    || (_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 520), 0, 0) & 0x2000000) != 0
                    || !*(_QWORD *)&v322[4] )
                  {
LABEL_416:
                    if ( !*(_DWORD *)v322 )
                      goto LABEL_417;
                    v163 = v338;
                    if ( (WORD2(v395) & 0x8000) != 0 )
                    {
                      if ( (DWORD1(v395) & 0x4000000) != 0 )
                        v163 = 2;
                      v338 = v163;
                      v339 = v163;
                    }
                  }
                  else
                  {
                    v210 = v328;
                    if ( v328 == 231 )
                      v210 = ((unsigned __int64)*(unsigned __int16 *)(a1 + 914) << 16) | 0xE7;
                    tagTHREADINFO::UpdateInputSource(
                      (tagTHREADINFO *)a1,
                      (const struct tagINPUT_MESSAGE_SOURCE *)((char *)&v396 + 12));
                    tagTLBLOCK::_unnamed_type_list_::_unnamed_type_list_((tagTLBLOCK::_unnamed_type_list_ *)BugCheckParameter2);
                    v211 = v346;
                    if ( v346 )
                      Win32RawLockedItemBase<tagQMSG,0,1,1,1>::ManualLock<void>((ULONG_PTR)BugCheckParameter2, v346);
                    v212 = v210;
                    v11 = v331;
                    v213 = xxxImmProcessKey(*v331, *(struct tagWND **)&v322[4], v321, v212, (__int64)v327);
                    LOBYTE(v163) = v213;
                    v338 = v213;
                    v339 = v213;
                    if ( (v213 & 0x11) != 0 )
                    {
                      if ( v211 )
                      {
                        Win32RawLockedItemBase<tagQMSG,0,1,1,1>::UnlockWorker((ULONG_PTR)BugCheckParameter2);
                        v346 = 0;
                      }
                      Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
                      goto LABEL_51;
                    }
                    if ( v211 )
                      Win32RawLockedItemBase<tagQMSG,0,1,1,1>::UnlockWorker((ULONG_PTR)BugCheckParameter2);
                    Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
                  }
LABEL_418:
                  if ( !*(_DWORD *)v322 )
                    goto LABEL_432;
                  v323 = 1;
                  v164 = 0;
                  if ( (WORD2(v395) & 0x8000) == 0 )
                  {
                    v165 = *((_QWORD *)*v11 + 65);
                    *((_QWORD *)*v11 + 65) = *((_QWORD *)&v393 + 1);
                    v166 = v163 & 2;
                    tagTHREADINFO::UpdateInputSource(
                      (tagTHREADINFO *)a1,
                      (const struct tagINPUT_MESSAGE_SOURCE *)((char *)&v396 + 12));
                    *(_QWORD *)&v403[0] = 0;
                    v403[1] = 0;
                    *((_QWORD *)&v403[0] + 1) = v327;
                    *(_QWORD *)&v350 = (unsigned int)Feature_WebThreatDefenseToggle__private_featureState;
                    if ( (Feature_WebThreatDefenseToggle__private_featureState & 0x10) == 0 )
                    {
                      LODWORD(v350) = Feature_WebThreatDefenseToggle__private_featureState | 1;
                      wil_details_FeatureReporting_ReportUsageToService(
                        Feature_WebThreatDefenseToggle__private_descriptor,
                        v350,
                        3,
                        1);
                      wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
                        v350,
                        3,
                        Feature_WebThreatDefenseToggle__private_descriptor);
                    }
                    v169 = *(_QWORD *)(a1 + 1376);
                    v170 = *(_QWORD *)(a1 + 456);
                    v171 = *(unsigned int *)(v170 + 276);
                    if ( (v171 & 4) != 0
                      && (_DWORD)v169 == 1
                      && (v169 & 0x500000000LL) != 0
                      && *(_QWORD *)(a1 + 488) != *(_QWORD *)(W32GetUserSessionState(v170, v171, v167, v168) + 62744)
                      && CheckImEnabled() )
                    {
                      LOWORD(v403[1]) = 1;
                    }
                    tagTLBLOCK::_unnamed_type_list_::_unnamed_type_list_((tagTLBLOCK::_unnamed_type_list_ *)BugCheckParameter2);
                    v172 = (_DWORD *)v346;
                    if ( v346 )
                      Win32RawLockedItemBase<tagQMSG,0,1,1,1>::ManualLock<void>((ULONG_PTR)BugCheckParameter2, v346);
                    v164 = xxxCallCtfHook(2, v166, v328, v403);
                    if ( (BYTE2(v403[1]) & 1) != 0 )
                    {
                      if ( (*(_BYTE *)(*(_QWORD *)(a1 + 456) + 808LL) & 0x30) == 0x10 )
                        WORD1(v403[1]) |= 0x10u;
                      ProcessTranslatedChar((struct _CHARHOOKSTRUCT *)v403);
                    }
                    v11 = v331;
                    *((_QWORD *)*v331 + 65) = v165;
                    if ( !v172 )
                      goto LABEL_430;
                    if ( (unsigned int)(v164 - 2) > 1
                      || (*(_DWORD *)(a1 + 1360) & 0x20000000) != 0
                      || !AllocQEntryEx((__int64)*v11 + 24, v172, 2, v173) )
                    {
                      v346 = 0;
LABEL_430:
                      Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
                      NextSysMsg = v342;
                      goto LABEL_431;
                    }
                    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
                      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20000) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u )
                    {
                      v9 = 0;
                    }
                    if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
                      || (v226 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
                    {
                      v226 = 0;
                    }
                    if ( v9 || v226 )
                    {
                      v263 = *v11;
                      v264 = *((_QWORD *)*v11 + 11);
                      v265 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v224, v225);
                      LOBYTE(v266) = v226;
                      LOBYTE(v267) = v9;
                      WPP_RECORDER_AND_TRACE_SF_qqq(
                        *((_QWORD *)WPP_GLOBAL_Control + 3),
                        v267,
                        v266,
                        *(_QWORD *)(v265 + 69152),
                        5,
                        18,
                        35,
                        (__int64)WPP_49cdbed1bece331d44f23b214bd7a204_Traceguids,
                        v346,
                        (char)v263,
                        v264);
                      v11 = v331;
                    }
                    if ( v360 == -1 )
                    {
                      BugCheckParameter4 = PtiCurrent();
                      KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)BugCheckParameter2, 0, (ULONG_PTR)BugCheckParameter4);
                    }
                    *((_QWORD *)PtiCurrent() + 47) = BugCheckParameter2[0];
                    v360 = -1;
                    *((_QWORD *)*v11 + 11) = v346;
                    v9 = 1;
                    if ( v164 == 2 )
                    {
                      v227 = 1;
                      v332 = 1;
                    }
                    else
                    {
                      v227 = v332;
                      if ( v164 == 3 )
                        v227 = 2;
                      v332 = v227;
                    }
                    DeferSysPeekMsg(a1, v227);
                    v346 = 0;
                    Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
                    goto LABEL_23;
                  }
LABEL_431:
                  if ( v164 )
                  {
                    v33 = 1;
                    goto LABEL_52;
                  }
LABEL_432:
                  if ( ((*(_BYTE *)(a1 + 712) | *(_BYTE *)(**(_QWORD **)(a1 + 496) + 16LL)) & 8) == 0 )
                  {
                    v33 = v323;
LABEL_434:
                    if ( v33
                      && *(_DWORD *)v322
                      && ((*(_BYTE *)(a1 + 712) | *(_BYTE *)(**(_QWORD **)(a1 + 496) + 16LL)) & 0x40) != 0 )
                    {
                      xxxCallHook(7, v328, (__int64)v327, 5);
                    }
                    goto LABEL_198;
                  }
                  v33 = 1;
                  v323 = 1;
                  if ( !(unsigned int)xxxCallHook(*(_DWORD *)v322 == 0 ? 3 : 0, v328, (__int64)v327, 2) )
                    goto LABEL_434;
LABEL_52:
                  xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v389, 1);
                  if ( v337 )
                  {
                    if ( ((*(_BYTE *)(a1 + 712) | *(_BYTE *)(**(_QWORD **)(a1 + 496) + 16LL)) & 0x40) != 0 )
                      xxxCallHook(6, v321, (__int64)v400, 5);
                    v337 = 0;
                  }
                  if ( v33 )
                  {
                    if ( ((*(_BYTE *)(a1 + 712) | *(_BYTE *)(**(_QWORD **)(a1 + 496) + 16LL)) & 0x40) != 0 )
                      xxxCallHook(7, v328, (__int64)v327, 5);
                    v323 = 0;
                  }
                  v18 = FLOAT_1_0;
                  v11 = v331;
                  LOBYTE(i) = v324;
                  if ( *(_DWORD *)v322 )
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
              v348 = 1;
              v328 = LOBYTE(v391[0]);
              if ( *(_DWORD *)v322 && (WORD2(v395) & 0x8000) != 0 )
              {
LABEL_353:
                if ( v328 == 231 )
                {
                  *(_WORD *)(a1 + 914) = WORD1(v391[0]);
                  v391[0] = 231;
                }
                goto LABEL_355;
              }
              if ( LOBYTE(v391[0]) != 18 )
                *((_DWORD *)*v11 + 127) &= 0xFFFFFFF3;
              if ( v328 != 44 )
              {
LABEL_527:
                if ( *(_DWORD *)(W32GetUserSessionState(i, v28, v24, v25) + 16256)
                  && (!*(_DWORD *)(W32GetUserSessionState(v200, v28, v24, v25) + 14652)
                   || (*(_BYTE *)(W32GetUserSessionState(v202, v201, v203, v204) + 14648) & 2) == 0) )
                {
                  v205 = *((_BYTE *)*v11 + 356);
                  v206 = v328 | 0x400;
                  if ( (v205 & 0x10) == 0 )
                    v206 = v328;
                  v207 = v206 | 0x200;
                  if ( (v205 & 4) == 0 )
                    v207 = v206;
                  v208 = v207;
                  LODWORD(v208) = v207 | 0x100;
                  if ( (v205 & 1) == 0 )
                    v208 = v207;
                  v209 = (_QWORD *)HotKeyToWindow(v208);
                  v25 = v209;
                  if ( v209 )
                  {
                    if ( *(_QWORD *)(a1 + 488) == *(_QWORD *)(v209[2] + 488LL) )
                    {
                      PostTransformableMessage(*((_QWORD *)*v11 + 16), 274, 61776, *v209, 0);
                      xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v389, 1);
                      goto LABEL_14;
                    }
                  }
                }
                goto LABEL_353;
              }
              i = 16;
              v255 = *((_BYTE *)*v11 + 356) & 0x10;
              if ( (!v255 || (*(_DWORD *)(a1 + 916) & 0x10) != 0) && (v255 || (*(_DWORD *)(a1 + 916) & 0x20) != 0) )
              {
                v11 = v331;
                goto LABEL_527;
              }
              xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v389, 1);
              if ( v255 || (v391[1] & 0xFF0000) == 0x10000 )
              {
                v11 = v331;
                if ( !*((_QWORD *)*v331 + 16) )
                  goto LABEL_14;
                CompositeAppFrameWindowOrSelf = CoreWindowProp::GetCompositeAppFrameWindowOrSelf(*((const struct tagWND **)*v331
                                                                                                 + 16));
              }
              else
              {
                CompositeAppFrameWindowOrSelf = *(struct tagWND **)(*(_QWORD *)(*(_QWORD *)(a1 + 488) + 8LL) + 24LL);
                v11 = v331;
              }
              if ( CompositeAppFrameWindowOrSelf )
              {
                v257 = v397 != 1;
                Win32HMThreadLockAlways<tagHOOK>::Win32HMThreadLockAlways<tagHOOK>(
                  v385,
                  a1,
                  CompositeAppFrameWindowOrSelf);
                xxxSnapWindow(CompositeAppFrameWindowOrSelf, v257);
                Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)v385);
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
        if ( LODWORD(v390[1]) != 522 && LODWORD(v390[1]) != 526 )
          break;
        if ( (_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 520), 0, 0) & 0x400) != 0
          && (int)CheckProcessForeground((struct tagTHREADINFO *)a1) < 0 )
        {
          goto LABEL_75;
        }
        if ( (unsigned int)IsInsideMenuLoop(a1) )
          goto LABEL_51;
        if ( (DWORD1(v395) & 0x100000) != 0 )
        {
          v174 = *((_QWORD *)*v11 + 15);
          *(_QWORD *)&v322[4] = v174;
        }
        else
        {
          if ( *(_QWORD *)&v322[4] && IsCompositionInputWindowForHitTest(*(struct tagWND **)&v322[4]) )
          {
            v215 = 1;
            if ( (unsigned int)CoreWindowProp::IsCompositeAppOrSelfDisabled(*(const struct tagWND **)&v322[4]) )
              goto LABEL_51;
            ThreadDesktopWindow = *(_QWORD *)&v322[4];
          }
          else
          {
            ThreadDesktopWindow = GetThreadDesktopWindow(0);
            *(_QWORD *)&v322[4] = ThreadDesktopWindow;
            v215 = 0;
          }
          Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(v386, ThreadDesktopWindow);
          v216 = xxxDCEWindowHitTest(*(_QWORD *)&v322[4], 512, v391[0], v391[1], *(_QWORD *)v394, &v329, 4 * v215 + 9);
          LOBYTE(v217) = 1;
          *(_QWORD *)&v322[4] = HMValidateHandleNoSecure(v216, v217);
          LOBYTE(v218) = 1;
          v219 = (struct tagWND *)HMValidateHandleNoSecure(v216, v218);
          InputTraceLogging::Mouse::SecondaryHitTest((const struct tagQMSG *)&v389, v394, v219);
          Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)v386);
          v174 = *(_QWORD *)&v322[4];
          v11 = v331;
        }
        if ( !v174 )
          goto LABEL_51;
        Win32HM_ExchangeThreadLock<1>(v174, v361);
        v175 = *(_QWORD *)(*(_QWORD *)&v322[4] + 16LL);
        v330 = v175 != v368;
        if ( v175 != v362 )
        {
          v197 = *(_QWORD *)(*(_QWORD *)&v322[4] + 16LL);
          if ( *(struct tagQ **)(v197 + 464) != *v11 )
            goto LABEL_51;
          if ( !v358 )
          {
            v358 = *(struct _W32THREAD **)(*(_QWORD *)&v322[4] + 16LL);
            Win32RawLockedW32Thread::Exchange((Win32RawLockedW32Thread *)v381, (struct _W32THREAD *)v197);
          }
        }
        v100 = v333;
        v176 = MiPCheckMsgFilter(NextSysMsg, v321, v333, a5);
        LOBYTE(i) = v324;
        if ( v176 )
        {
          v177 = *(struct tagWND **)&v322[4];
          v178 = CheckPwndFilter(*(_QWORD *)&v322[4], v347);
          LOBYTE(i) = v324;
          if ( v178 )
          {
            if ( v330 )
              goto LABEL_75;
            if ( NextSysMsg && (unsigned int)IsMiPActive(a1, NextSysMsg) )
            {
              if ( _bittest((const signed __int32 *)NextSysMsg + 25, 0xAu) )
              {
                memset_0(v403, 0, 0xA8u);
                if ( ShouldGenerateMipMessage((struct tagTHREADINFO *)a1, NextSysMsg, v177, *(int *)v322)
                  && GeneratePointerMessageFromMouse((struct tagQMSG *)v403, v321, NextSysMsg, v177, v274) )
                {
                  v389 = v403[0];
                  *(_OWORD *)v390 = v403[1];
                  *(_OWORD *)v391 = v403[2];
                  v392 = v404;
                  v393 = v405;
                  *(_OWORD *)&v394[0].x = v406;
                  v395 = v407;
                  v396 = v408;
                  v397 = v409;
                  v398 = v410;
                  v399 = v411;
                  v29 = 1;
                  v340 = 1;
                  if ( *(_DWORD *)v322 )
                    *((_DWORD *)NextSysMsg + 25) &= ~0x400u;
                  goto LABEL_211;
                }
                if ( !*(_DWORD *)v322 )
                  goto LABEL_452;
                *((_DWORD *)NextSysMsg + 25) &= ~0x400u;
              }
              else
              {
                if ( !*(_DWORD *)v322 )
                {
LABEL_452:
                  MouseKeyFlags = GetMouseKeyFlags(*(_QWORD *)(a1 + 464));
                  v328 = v391[0] | MouseKeyFlags;
                  v327 = (void *)v391[1];
                  v326.x = SLOWORD(v391[1]);
                  v326.y = SWORD1(v391[1]);
                  PhysicalToLogicalDPIPointWithHitTest(&v326, &v326, 0, *(const struct tagWND **)&v322[4]);
                  v327 = (void *)((LOWORD(v326.y) << 16) | LOWORD(v326.x));
                  *(struct tagPOINT *)((char *)&v392 + 4) = v326;
                  v400[0] = (__int64)v326;
                  if ( *(_QWORD *)&v322[4] )
                    v400[1] = **(_QWORD **)&v322[4];
                  else
                    v400[1] = 0;
                  LODWORD(v401) = 0;
                  *((_QWORD *)&v401 + 1) = *((_QWORD *)&v393 + 1);
                  LODWORD(v402) = v391[0];
                  if ( *(_DWORD *)v322 )
                  {
                    v337 = 1;
                    if ( (unsigned int)xxxCallCtfHook(7, 0, v321, v400) )
                      goto LABEL_51;
                  }
                  if ( ((*(_DWORD *)(a1 + 712) | *(_DWORD *)(**(_QWORD **)(a1 + 496) + 16LL)) & 0x100) != 0 )
                  {
                    v337 = 1;
                    if ( (unsigned int)xxxCallMouseHook(v321, v400, *(unsigned int *)v322) )
                      goto LABEL_51;
                  }
                  if ( (unsigned int)PsGetWin32KFilterSet() == 5 )
                  {
                    v277 = *((_QWORD *)PtiCurrent() + 64);
                    v334 = 0;
                    v334 = *(_QWORD *)(v277 + 248) != 0;
                    if ( v334 )
                    {
                      if ( xxxClientCallLocalMouseHooks(v321, v400, *(unsigned int *)v322) )
                        goto LABEL_51;
                    }
                  }
                  if ( v337
                    && *(_DWORD *)v322
                    && ((*(_BYTE *)(a1 + 712) | *(_BYTE *)(**(_QWORD **)(a1 + 496) + 16LL)) & 0x40) != 0 )
                  {
                    xxxCallHook(6, v321, (__int64)v400, 5);
                  }
LABEL_198:
                  if ( *(_QWORD *)(a1 + 788) != *(_QWORD *)((char *)&v392 + 4) )
                    _InterlockedOr((volatile signed __int32 *)(a1 + 520), 0x100000u);
                  if ( NextSysMsg && ((BYTE4(v395) & 0x20) != 0 || (DWORD1(v395) & 0x8000000) != 0) )
                  {
                    if ( *((_DWORD *)NextSysMsg + 6) == 512 )
                    {
                      if ( *(_QWORD *)&v322[4] )
                        v131 = **(_QWORD **)&v322[4];
                      else
                        v131 = 0;
                      *((_QWORD *)NextSysMsg + 2) = v131;
                      *((_DWORD *)NextSysMsg + 25) |= 0x200u;
                    }
                    *((_QWORD *)NextSysMsg + 8) = v327;
                  }
                  *(_DWORD *)(a1 + 788) = DWORD1(v392);
                  v94 = v365;
                  *(_DWORD *)(v365 + 792) = DWORD2(v392);
                  *(_DWORD *)(v94 + 796) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)&v322[4] + 40LL) + 288LL);
                  *(struct tagPOINT *)(a1 + 800) = v394[0];
                  *(_DWORD *)(a1 + 600) = v392;
                  *(_QWORD *)(*(_QWORD *)(a1 + 464) + 520LL) = *((_QWORD *)&v393 + 1);
                  if ( v321 == 514 || v321 == 162 )
                    *(struct tagPOINT *)(a1 + 808) = v394[0];
                  *(_QWORD *)(*(_QWORD *)(a1 + 464) + 80LL) = 1;
                  *(_QWORD *)(a1 + 608) = 1;
                  tagTHREADINFO::UpdateLastInputData((tagTHREADINFO *)a1, (const struct tagQMSG *)&v389);
                  **(_DWORD **)(a1 + 480) &= ~8u;
                  **(_QWORD **)(a1 + 512) &= 0x7FFFFFFFuLL;
                  v95 = v338;
                  v96 = v366;
                  if ( *(_DWORD *)v322 )
                  {
                    v119 = *(_QWORD **)(a1 + 512);
                    if ( (BYTE4(v395) & 1) != 0 )
                      *v119 |= 0x1000uLL;
                    else
                      *v119 &= ~0x1000uLL;
                  }
                  TransferWakeBit(a1, v321);
                  v97 = *(_QWORD *)(a1 + 464);
                  if ( !*(_DWORD *)(v97 + 40) )
                    _InterlockedAnd(
                      (volatile signed __int32 *)(*(_QWORD *)(a1 + 480) + 8LL),
                      (*(_DWORD *)(v97 + 508) >> 4) & 2 | 0xFFFF83F8);
                  v98 = *(_DWORD *)v322;
                  if ( *(_DWORD *)v322 )
                  {
                    if ( v340 )
                    {
                      v117 = *(_DWORD **)(a1 + 1512);
                      if ( v117 )
                      {
                        if ( (*v117 & 1) != 0 && (*v117 & 4) != 0 )
                        {
                          SetMiPWakeBit((struct tagTHREADINFO *)a1);
                          v98 = *(_DWORD *)v322;
                        }
                      }
                    }
                  }
                  v99 = 0;
                  if ( *(_QWORD *)&v322[4] )
                    v99 = **(_QWORD **)&v322[4];
                  *(_QWORD *)v377 = v99;
                  *((_DWORD *)v96 + 2) = v321;
                  v47 = v328;
                  if ( (v95 & 2) != 0 )
                    v47 = 229;
                  *((_QWORD *)v96 + 2) = v47;
                  *((_QWORD *)v96 + 3) = v327;
                  *((_DWORD *)v96 + 8) = v392;
                  *(_QWORD *)((char *)v96 + 36) = *(_QWORD *)((char *)&v392 + 4);
                  InputTraceLogging::Delivery::ScanSysQueue(
                    (const struct tagQMSG *)&v389,
                    v96,
                    (const struct tagTHREADINFO *)a1,
                    v98 != 0);
                  if ( *(_DWORD *)v322 )
                  {
                    EtwTraceInputProcessDelay(a1);
                    *(_DWORD *)(*(_QWORD *)(a1 + 464) + 528LL) = (MEMORY[0xFFFFF78000000320]
                                                                * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
                  }
                  EtwTraceRetrieveInputMessage(v96);
                  if ( v336[0] )
                  {
                    v48 = PtiCurrent();
                    *((_QWORD *)v48 + 170) &= ~0x1000000000uLL;
                  }
                  Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)v361);
                  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v383);
                  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v384);
                  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v382);
                  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v380);
                  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v381);
                  return 1;
                }
                if ( (unsigned int)IsMiPMouseMessage(*((unsigned int *)NextSysMsg + 6)) )
                {
                  if ( (unsigned int)IsGenuineMouseInput((char *)NextSysMsg + 124) )
                  {
                    v275 = *(_DWORD **)(a1 + 1512);
                    if ( v275 )
                    {
                      if ( (*v275 & 2) == 0 && (*v275 & 4) == 0 )
                        goto LABEL_681;
                    }
                  }
                  v276 = *(_DWORD **)(a1 + 1512);
                  if ( v276 )
                    *v276 &= ~2u;
                }
              }
            }
            if ( *(_DWORD *)v322 )
              xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v389, 1);
            goto LABEL_452;
          }
          v11 = v331;
        }
      }
      switch ( LODWORD(v390[1]) )
      {
        case 0x238:
          goto LABEL_110;
        case 0x240:
LABEL_106:
          if ( !*(_QWORD *)&v322[4] )
            goto LABEL_51;
          v49 = *(char **)(*(_QWORD *)&v322[4] + 40LL);
          if ( v49[20] < 0 || v49[19] < 0 || (v49[31] & 0x18) != 0x10 )
            goto LABEL_51;
          goto LABEL_110;
        case 0x245:
        case 0x246:
        case 0x247:
        case 0x249:
          goto LABEL_210;
      }
LABEL_128:
      v326.x = SLOWORD(v391[1]);
      v326.y = SWORD1(v391[1]);
      v329 = 1;
      if ( (BYTE4(v395) & 0x20) == 0 && (DWORD1(v395) & 0x8000000) == 0
        || !*(_QWORD *)&v322[4]
        || (((unsigned __int16)(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)&v322[4] + 40LL) + 288LL) >> 8)
           ^ (unsigned __int16)(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v322[4] + 16LL) + 456LL) + 268LL) >> 8))
          & 0x1FF) != 0 )
      {
        if ( !*(_QWORD *)&v322[4]
          || (v148 = IsCompositionInputWindowForHitTest(*(struct tagWND **)&v322[4]), v55 = 1, !v148) )
        {
          v55 = 0;
        }
        v341 = v55;
        v56 = *(_QWORD *)(a1 + 464);
        v57 = *(HWND **)(v56 + 112);
        if ( v57 )
        {
          *(_QWORD *)&v322[4] = *(_QWORD *)(v56 + 112);
          InputTraceLogging::Mouse::RedirectForCapture((const struct tagQMSG *)&v389, *v57);
        }
        else
        {
          Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(v378);
          if ( (_DWORD)v60 )
          {
            v62 = *(struct tagWND **)&v322[4];
          }
          else
          {
            v62 = *(struct tagWND **)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v59, v58, v60, v61)
                                                                        + 18752)
                                                            + 488LL)
                                                + 8LL)
                                    + 24LL);
            Win32HM_LockIntoThread<1>(a1, v62, v378);
          }
          if ( (unsigned int)IsThreadDesktopComposed((const struct tagTHREADINFO *)a1) )
          {
            *(_QWORD *)&v403[0] = LODWORD(v390[1]);
            *((_QWORD *)&v403[0] + 1) = v391[0];
            *(_QWORD *)&v403[1] = v391[1];
            *((_QWORD *)&v403[1] + 1) = &v329;
            LODWORD(v403[2]) = v63;
            BYTE4(v403[2]) = 0;
            *(_WORD *)((char *)&v403[2] + 5) = 0;
            BYTE7(v403[2]) = 0;
            *((_QWORD *)&v403[2] + 1) = &v394[1];
            v404 = 0u;
            v65 = xxxDCEWindowHitTestIndirect(v62, v394[0], 0, (struct tagDCE_WINDOW_HIT_TEST_ARGS *)v403);
            if ( v65 && (_BYTE)v404 )
            {
              v391[1] = *(_QWORD *)&v403[1];
              DWORD1(v392) = SLOWORD(v403[1]);
              v64 = *(_QWORD *)&v403[1] >> 16;
              DWORD2(v392) = SWORD1(v403[1]);
              v326 = *(struct tagPOINT *)((char *)&v392 + 4);
            }
          }
          else
          {
            v65 = (HWND)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))xxxWindowHitTest)(v62, v326, &v329);
          }
          LOBYTE(v64) = 1;
          v66 = (struct tagWND *)HMValidateHandleNoSecure(v65, v64);
          InputTraceLogging::Mouse::SecondaryHitTest((const struct tagQMSG *)&v389, &v326, v66);
          if ( !v341 )
            Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)v378);
          LOBYTE(v67) = 1;
          *(_QWORD *)&v322[4] = HMValidateHandleNoSecure(v65, v67);
          if ( !*(_QWORD *)&v322[4] )
          {
            v278 = *(_QWORD *)(*(_QWORD *)(a1 + 488) + 8LL);
            *(_QWORD *)&v322[4] = *(_QWORD *)(v278 + 24);
            if ( !*(_QWORD *)&v322[4] )
              *(_QWORD *)&v322[4] = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(
                                                                                      v278,
                                                                                      v68,
                                                                                      v69,
                                                                                      v70)
                                                                                  + 18752)
                                                                      + 488LL)
                                                          + 8LL)
                                              + 24LL);
          }
          v71 = 0;
          if ( !*(_QWORD *)(a1 + 640) )
          {
            if ( (unsigned int)IsMiPEnabledForThread(a1) )
            {
              v72 = *(_QWORD *)(*(_QWORD *)(a1 + 464) + 560LL);
              if ( v72 )
              {
                v279 = ValidateHwnd(v72);
                if ( v279 )
                {
                  v280 = *(_QWORD *)(a1 + 464);
                  v281 = *(_QWORD *)(v279 + 16);
                  if ( *(_QWORD *)(v281 + 464) == v280 || *(_QWORD *)(v281 + 456) == *(_QWORD *)(a1 + 456) )
                  {
                    *(_QWORD *)&v322[4] = v279;
                    v329 = 1;
                    *(_DWORD *)(v280 + 156) = 0;
                    v71 = 1;
                  }
                }
              }
            }
          }
          if ( !v71 )
            *(_DWORD *)(*(_QWORD *)(v365 + 464) + 156LL) = v329 != 1;
          Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)v378);
        }
        if ( *(_QWORD *)&v322[4] == *(_QWORD *)(*(_QWORD *)(a1 + 464) + 112LL) )
        {
          v149 = PtiMouseFromQ(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v322[4] + 16LL) + 464LL));
          if ( (((unsigned __int16)(*(_DWORD *)(*((_QWORD *)v150 + 5) + 288LL) >> 8)
               ^ (unsigned __int16)(*(_DWORD *)(*(_QWORD *)(v149 + 456) + 268LL) >> 8))
              & 0x1FF) != 0
            || (unsigned int)IsOleDragDropCaptureWindow(v150) )
          {
            v326 = v394[0];
            v151 = 0;
            TopLevelOrDpiBoundaryWindow = GetTopLevelOrDpiBoundaryWindow(*(const struct tagWND **)&v322[4]);
            v156 = TopLevelOrDpiBoundaryWindow;
            if ( TopLevelOrDpiBoundaryWindow
              && (unsigned int)IsWindowDesktopComposed(TopLevelOrDpiBoundaryWindow, v153, v154, v155) )
            {
              v151 = (float *)*((_QWORD *)v156 + 27);
            }
            if ( v151 )
            {
              v232 = v18 / v151[5];
              v326.x = (int)(float)((float)((float)(FixedPointSubPixel(v394[1].x) + (float)v326.x) - v151[12])
                                  * (float)(v18 / *v151));
              v326.y = (int)(float)((float)((float)(FixedPointSubPixel(v394[1].y) + (float)v326.y) - v151[13]) * v232);
            }
            if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80000) == 0
              || (v157 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
            {
              v157 = 0;
            }
            if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
              || (v158 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
            {
              v158 = 0;
            }
            if ( v157 || v158 )
            {
              v282 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v154, v155);
              LOBYTE(v283) = v158;
              LOBYTE(v284) = v157;
              WPP_RECORDER_AND_TRACE_SF_dddd(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v284,
                v283,
                *(_QWORD *)(v282 + 69152),
                5,
                20,
                34,
                (__int64)WPP_49cdbed1bece331d44f23b214bd7a204_Traceguids,
                v394[0].x,
                v394[0].y,
                v326.x,
                v326.y);
            }
            v327 = (void *)((LOWORD(v326.y) << 16) | LOWORD(v326.x));
            *(struct tagPOINT *)((char *)&v392 + 4) = v326;
            NextSysMsg = v342;
          }
        }
      }
      Win32HM_ExchangeThreadLock<1>(*(_QWORD *)&v322[4], v361);
      if ( CheckCrossThreadInput(*(struct tagWND *const *)&v322[4], NextSysMsg, &v330, (int *)v322, v343) )
        goto LABEL_75;
      if ( v330 )
      {
        v285 = *(_QWORD *)(*(_QWORD *)&v322[4] + 16LL);
        if ( *(_QWORD *)(v285 + 464) != *(_QWORD *)(a1 + 464) )
          goto LABEL_799;
        if ( !v344 )
        {
          v344 = *(_QWORD *)(*(_QWORD *)&v322[4] + 16LL);
          v364 = v285;
          Win32RawLockedW32Thread::Exchange((Win32RawLockedW32Thread *)v380, (struct _W32THREAD *)v285);
        }
      }
      else if ( (WORD2(v395) & 0x800) != 0
             && !UIPrivilegeIsolation::CheckAccess(
                   (UIPrivilegeIsolation *)&v396,
                   (const struct tagUIPI_INFO *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v322[4] + 16LL) + 456LL) + 864LL),
                   v24) )
      {
        EtwTraceUIPIMsgError(0, *(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v322[4] + 16LL) + 456LL), v321, v391[0], v391[1]);
LABEL_799:
        v286 = W32GetUserSessionState(v73, v285, v24, v25);
        zzzSetCursor(*(struct tagCURSOR **)(v286 + 21712));
        goto LABEL_51;
      }
      v74 = v326;
      v75 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v322[4] + 16LL) + 464LL);
      v76 = *(_DWORD *)(v75 + 156);
      if ( v76 && (v77 = (unsigned int)(v76 - 2), (_DWORD)v77) )
      {
        if ( (_DWORD)v77 != 1 )
          goto LABEL_153;
        v287 = *(_QWORD *)(*(_QWORD *)&v322[4] + 40LL);
        if ( (*(_BYTE *)(v287 + 26) & 0x40) != 0 )
          v288 = *(_DWORD *)(v287 + 96) - v326.x;
        else
          v288 = v326.x - *(_DWORD *)(v287 + 88);
        v326.x = v288;
        v75 = (unsigned int)(v326.y - *(_DWORD *)(*(_QWORD *)(*(_QWORD *)&v322[4] + 40LL) + 92LL));
      }
      else
      {
        v77 = *(_QWORD *)&v322[4];
        v120 = *(_QWORD *)(*(_QWORD *)&v322[4] + 40LL);
        if ( (*(_BYTE *)(v120 + 26) & 0x40) != 0 )
          v121 = *(_DWORD *)(v120 + 112) - v326.x;
        else
          v121 = v326.x - *(_DWORD *)(v120 + 104);
        v326.x = v121;
        v75 = (unsigned int)(v326.y - *(_DWORD *)(*(_QWORD *)(*(_QWORD *)&v322[4] + 40LL) + 108LL));
      }
      v326.y = v75;
LABEL_153:
      if ( !v330
        && *(_QWORD *)(a1 + 464) == *(_QWORD *)(W32GetUserSessionState(v75, v77, *(_QWORD *)&v322[4], v25) + 19248) )
      {
        v105 = *(_QWORD *)(*(_QWORD *)(a1 + 488) + 192LL) != *(_QWORD *)&v322[4];
        if ( (unsigned int)Feature_UserModeNonClientScrollBars2__private_IsEnabledDeviceUsageNoInline()
          && Scrollbar::NonClient::UserModeSupportsUserModeScrollBars(v106) )
        {
          v107 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))xxxFindNCHitEx)(
                   *(_QWORD *)&v322[4],
                   (unsigned int)v329,
                   v326);
        }
        else
        {
          v107 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))FindNCHitEx)(
                   *(_QWORD *)&v322[4],
                   (unsigned int)v329,
                   v326);
        }
        if ( v321 != 512 || v105 || *(_DWORD *)(*(_QWORD *)(a1 + 488) + 200LL) != v107 )
          xxxTrackMouseMove(*(struct tagDESKTOP **)&v322[4], (struct tagWND *)v107);
        if ( !v105 )
        {
          v108 = *(_QWORD *)(a1 + 488);
          if ( (*(_DWORD *)(v108 + 48) & 0x40) != 0
            && (v321 != 512 || !(unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD))PtInRect)(v108 + 204, v74)) )
          {
            ResetMouseHover((struct tagDESKTOP *)v108, v74);
          }
        }
        NextSysMsg = v342;
      }
      v78 = CheckPwndFilter(*(_QWORD *)&v322[4], v347);
      v11 = v331;
      LOBYTE(i) = v324;
      if ( v78 )
      {
        v82 = 0;
        LODWORD(v350) = 0;
        switch ( v321 )
        {
          case 0x201u:
            v51 = (unsigned __int8)IsMessageInputSourceTouch(&v389) == 0;
            v220 = *(_QWORD *)(a1 + 464);
            if ( v51 )
              *(_DWORD *)(v220 + 508) &= ~0x800000u;
            else
              *(_DWORD *)(v220 + 508) |= 0x800000u;
            v221 = IsMessageInputSourcePen(&v389);
            v79 = *(_QWORD *)(v365 + 464);
            v222 = *(_DWORD *)(v79 + 508);
            if ( v221 )
              v191 = v222 | 0x1000000;
            else
              v191 = v222 & 0xFEFFFFFF;
            *(_DWORD *)(v79 + 508) = v191;
LABEL_497:
            if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v322[4] + 136LL) + 8LL) + 8LL) & 8) != 0
              || *(_DWORD *)(*(_QWORD *)(a1 + 464) + 156LL) == 1
              || (unsigned int)IsMenuStarted(a1) )
            {
              v82 = 1;
              LODWORD(v350) = 1;
              v192 = *(_QWORD *)(a1 + 464);
              if ( (unsigned int)v392 <= *(_DWORD *)(v192 + 168)
                && !*(_DWORD *)(W32GetUserSessionState(v192, v79, v80, v81) + 16216) )
              {
                v292 = *(_QWORD *)&v322[4] ? **(_QWORD **)&v322[4] : 0LL;
                v293 = *(_QWORD *)(a1 + 464);
                if ( v292 == *(_QWORD *)(v293 + 176)
                  && v321 == *(_DWORD *)(v293 + 160)
                  && (v321 != 523 || WORD1(v391[0]) == *(_WORD *)(v293 + 164)) )
                {
                  v295 = *(int *)(*(_QWORD *)(W32GetUserSessionState(v293, v289, v290, v291) + 19704) + 2040LL);
                  v294 = HIDWORD(v295);
                  LODWORD(v294) = v295 % 2;
                  v372 = *(_DWORD *)(*(_QWORD *)(a1 + 464) + 184LL) - v295 / 2;
                  v299 = *(int *)(*(_QWORD *)(W32GetUserSessionState(v372, v294, v296, v297) + 19704) + 2044LL);
                  v298 = HIDWORD(v299);
                  LODWORD(v298) = v299 % 2;
                  v373 = *(_DWORD *)(*(_QWORD *)(a1 + 464) + 188LL) - v299 / 2;
                  v302 = W32GetUserSessionState(v373, v298, v300, v301);
                  v303 = *(_QWORD *)(a1 + 464);
                  LODWORD(v304) = *(int *)(*(_QWORD *)(v302 + 19704) + 2040LL) >> 31;
                  LODWORD(v302) = *(_DWORD *)(*(_QWORD *)(v302 + 19704) + 2040LL);
                  v304 = (unsigned int)v304;
                  v305 = __SPAIR64__(v304, v302) % 2;
                  LODWORD(v302) = __SPAIR64__(v304, v302) / 2;
                  LODWORD(v304) = v305;
                  v374 = *(_DWORD *)(v303 + 184) + v302;
                  v375 = *(_DWORD *)(*(_QWORD *)(a1 + 464) + 188LL)
                       + *(_DWORD *)(*(_QWORD *)(W32GetUserSessionState(v303, v304, v306, v307) + 19704) + 2044LL) / 2;
                  if ( (unsigned int)PtInRect(&v372, *(_QWORD *)((char *)&v392 + 4)) )
                  {
                    v321 += 2;
                    v82 = 2;
                    LODWORD(v350) = 2;
                  }
                }
              }
            }
LABEL_499:
            v193 = *(_QWORD *)(a1 + 464);
            v194 = *(_DWORD *)(v193 + 508);
            if ( (v194 & 8) != 0 )
              *(_DWORD *)(v193 + 508) = v194 | 4;
            if ( v321 - 514 <= 0xA )
            {
              v195 = 1097;
              if ( _bittest(&v195, v321 - 514) )
              {
                if ( *(_DWORD *)(*(_QWORD *)(a1 + 464) + 168LL) && ((HIDWORD(v396) - 4) & 0xFFFFFFFB) == 0 )
                {
                  if ( HIDWORD(v396) == 4 )
                    TouchTimeFromCPLValue = GetTouchTimeFromCPLValue(300, 180, 5, 1);
                  else
                    TouchTimeFromCPLValue = GetPenDoubleClickTime();
                  *(_DWORD *)(*(_QWORD *)(a1 + 464) + 168LL) = v399 + TouchTimeFromCPLValue;
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
        if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v322[4] + 16LL) + 464LL) + 156LL) == 1 )
        {
          v321 -= 352;
          v328 = (unsigned int)v329;
        }
        v83 = MiPCheckMsgFilter(NextSysMsg, v321, v333, a5);
        v11 = v331;
        LOBYTE(i) = v324;
        if ( v83 )
        {
          if ( v330 )
            goto LABEL_75;
          if ( v321 - 512 > 0xE )
            break;
          v118 = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 520), 0, 0);
          LOBYTE(i) = v324;
          if ( (v118 & 0x8000) == 0 )
            break;
        }
      }
    }
    if ( (_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 520), 0, 0) & 0x100000) != 0 )
    {
      _InterlockedAnd((volatile signed __int32 *)(a1 + 520), 0xFFEFFFFF);
      xxxWindowEvent(0x800Bu, 1);
    }
    v400[0] = *(_QWORD *)((char *)&v392 + 4);
    if ( *(_QWORD *)&v322[4] )
      v400[1] = **(_QWORD **)&v322[4];
    else
      v400[1] = 0;
    LODWORD(v401) = v329;
    *((_QWORD *)&v401 + 1) = *((_QWORD *)&v393 + 1);
    LODWORD(v402) = v391[0];
    if ( *(_DWORD *)v322 )
    {
      if ( v321 != 512 && v321 != 160 )
      {
        v337 = 1;
        if ( (unsigned int)xxxCallCtfHook(7, 0, v321, v400) )
          goto LABEL_51;
      }
    }
    if ( ((*(_DWORD *)(a1 + 712) | *(_DWORD *)(**(_QWORD **)(a1 + 496) + 16LL)) & 0x100) != 0 )
    {
      v337 = 1;
      if ( (unsigned int)xxxCallMouseHook(v321, v400, *(unsigned int *)v322) )
        goto LABEL_51;
    }
    if ( (unsigned int)PsGetWin32KFilterSet() == 5 )
    {
      v308 = *((_QWORD *)PtiCurrent() + 64);
      v335 = 0;
      v335 = *(_QWORD *)(v308 + 248) != 0;
      if ( v335 )
      {
        if ( xxxClientCallLocalMouseHooks(v321, v400, *(unsigned int *)v322) )
          goto LABEL_51;
      }
    }
    if ( (*(_DWORD *)(a1 + 1360) & 0x2000LL) == 0 && (!v329 || v329 == -2) )
    {
      v199 = 0;
      if ( v341 )
      {
        v310 = (unsigned int)IsIndependentInputWindow(*(const struct tagWND **)&v322[4])
             ? GetCompositionInputWindowUIOwner(v309)
             : *(struct tagWND **)&v322[4];
        TopLevelWindow = (const struct tagWND *)GetTopLevelWindow(v310);
        v199 = TopLevelWindow;
        if ( TopLevelWindow )
        {
          v199 = CoreWindowProp::GetCompositeAppFrameWindowOrSelf(TopLevelWindow);
          Win32HMOptionalThreadLock<tagWND>::Win32HMOptionalThreadLock<tagWND>(v387, a1, v199);
          v312 = 0;
          if ( v199 )
            v312 = *(_QWORD *)v199;
          xxxSendMessage(v199, 32, v312, (unsigned __int16)v329 | (LOWORD(v390[1]) << 16));
          Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)v387);
        }
      }
      if ( !v199 )
      {
        if ( *(_QWORD *)&v322[4] )
          v313 = **(_QWORD **)&v322[4];
        else
          v313 = 0;
        xxxSendMessage(*(_QWORD *)&v322[4], 32, v313, (unsigned __int16)v329 | (LOWORD(v390[1]) << 16));
      }
      if ( *(struct tagQMSG **)(*(_QWORD *)(a1 + 464) + 88LL) == NextSysMsg
        && NextSysMsg
        && (unsigned int)IsMiPActive(a1, NextSysMsg)
        && (*((_DWORD *)NextSysMsg + 25) & 0x400) != 0
        && (unsigned int)IsGenuineMouseInput((char *)NextSysMsg + 124)
        && (unsigned int)IsMiPMouseMessage(*((unsigned int *)NextSysMsg + 6)) )
      {
        memset_0(v403, 0, 0xA8u);
        GeneratePointerMessageFromMouse(
          (struct tagQMSG *)v403,
          v321,
          NextSysMsg,
          *(struct tagWND **)&v322[4],
          *(int *)v322);
        SetMiPPromotion(*(_QWORD *)(*(_QWORD *)&v322[4] + 16LL), DWORD2(v403[1]));
      }
      goto LABEL_51;
    }
    if ( *(struct tagQMSG **)(*(_QWORD *)(a1 + 464) + 88LL) != NextSysMsg )
      goto LABEL_75;
    memset_0(v403, 0, 0x60u);
    v88 = v403[0];
    v89 = v403[1];
    v90 = v403[2];
    v91 = v404;
    v350 = v405;
    *(_OWORD *)BugCheckParameter2 = v406;
    v92 = 0;
    v412 = v389;
    v413 = *(_OWORD *)v390;
    v414 = *(_OWORD *)v391;
    v415 = v392;
    v416 = v393;
    v417 = *(_OWORD *)&v394[0].x;
    v418 = v395;
    v419 = v396;
    v420 = v397;
    v421 = v398;
    v422 = v399;
    if ( NextSysMsg && (unsigned int)IsMiPActive(a1, NextSysMsg) )
    {
      DWORD2(v413) = v321;
      *(_QWORD *)&v414 = v328;
      if ( (*((_DWORD *)NextSysMsg + 25) & 0x400) != 0 )
      {
        memset_0(v403, 0, 0xA8u);
        if ( ShouldGenerateMipMessage((struct tagTHREADINFO *)a1, NextSysMsg, *(struct tagWND **)&v322[4], *(int *)v322) )
        {
          v93 = *(_QWORD *)(a1 + 1512);
          if ( v93 && (*(_DWORD *)v93 & 1) != 0 )
          {
            v88 = *(_OWORD *)(v93 + 24);
            v89 = *(_OWORD *)(v93 + 40);
            v90 = *(_OWORD *)(v93 + 56);
            v91 = *(_OWORD *)(v93 + 72);
            v350 = *(_OWORD *)(v93 + 88);
            *(_OWORD *)BugCheckParameter2 = *(_OWORD *)(v93 + 104);
            v92 = 1;
          }
          if ( GeneratePointerMessageFromMouse(
                 (struct tagQMSG *)v403,
                 v321,
                 NextSysMsg,
                 *(struct tagWND **)&v322[4],
                 *(int *)v322) )
          {
            v389 = v403[0];
            *(_OWORD *)v390 = v403[1];
            *(_OWORD *)v391 = v403[2];
            v392 = v404;
            v393 = v405;
            *(_OWORD *)&v394[0].x = v406;
            v395 = v407;
            v396 = v408;
            v397 = v409;
            v398 = v410;
            v399 = v411;
            v29 = 1;
            v340 = 1;
            v87 = (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128((__m128i)v403[1], 8));
            if ( (_DWORD)v87 == 582 && (unsigned int)IsMiPEnabledForWindow(*(_QWORD *)&v322[4]) )
            {
              if ( v85 )
                v85 = **(_QWORD **)&v322[4];
              else
                v85 = 0;
              *(_QWORD *)(*(_QWORD *)(a1 + 464) + 560LL) = v85;
            }
            else if ( (((_DWORD)v87 - 579) & 0xFFFFFFFB) == 0 )
            {
              *(_QWORD *)(*(_QWORD *)(a1 + 464) + 560LL) = 0;
            }
          }
        }
        if ( *(_DWORD *)v322 )
        {
          *((_DWORD *)NextSysMsg + 25) &= ~0x400u;
          goto LABEL_189;
        }
LABEL_190:
        v9 = 1;
        goto LABEL_191;
      }
      if ( !*(_DWORD *)v322 )
        goto LABEL_190;
      if ( (unsigned int)IsMiPMouseMessage(*((unsigned int *)NextSysMsg + 6)) )
      {
        if ( (unsigned int)IsGenuineMouseInput((char *)NextSysMsg + 124) )
        {
          v132 = *(unsigned int **)(a1 + 1512);
          if ( v132 )
          {
            v85 = *v132;
            if ( (v85 & 2) == 0 && (v85 & 4) == 0 )
            {
              v9 = 1;
              xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v389, 1);
              goto LABEL_845;
            }
          }
        }
        v133 = *(_DWORD **)(a1 + 1512);
        if ( v133 )
          *v133 &= ~2u;
      }
    }
LABEL_189:
    if ( !*(_DWORD *)v322 )
      goto LABEL_190;
    v137 = W32GetUserSessionState(v85, v84, v86, v87);
    if ( DWORD2(v413) == 512 || DWORD2(v413) == 160 )
    {
      v138 = *(_QWORD *)&v322[4] ? **(_QWORD **)&v322[4] : 0LL;
      if ( v138 != *(_QWORD *)(v137 + 16288) && (unsigned int)IsGenuineMouseInput((char *)NextSysMsg + 124) )
      {
        LOBYTE(v134) = 1;
        v140 = HMValidateHandleNoSecure(*(_QWORD *)(v137 + 16288), v134);
        v141 = (struct tagWND *)v140;
        if ( v140 )
        {
          v180 = *(_QWORD *)(v140 + 16);
          if ( !*(_QWORD *)(v180 + 640) )
          {
            if ( (unsigned int)IsMiPEnabledForThread(v180) )
            {
              MiPWindowFlags = GetMiPWindowFlags(v141);
              v134 = 1;
              if ( (MiPWindowFlags & 1) == 0 )
              {
                v182 = (struct tagQ **)*((_QWORD *)v141 + 2);
                if ( v182 == (struct tagQ **)a1 )
                {
                  v183 = *(_QWORD *)(a1 + 1512);
                  v184 = *(_OWORD *)(v183 + 24);
                  v185 = *(_OWORD *)(v183 + 40);
                  v186 = *(_OWORD *)(v183 + 56);
                  v187 = *(_OWORD *)(v183 + 72);
                  v188 = *(_OWORD *)(v183 + 88);
                  v189 = *(_OWORD *)(v183 + 104);
                  if ( v92 )
                  {
                    *(_OWORD *)(v183 + 24) = v88;
                    *(_OWORD *)(v183 + 40) = v89;
                    *(_OWORD *)(v183 + 56) = v90;
                    *(_OWORD *)(v183 + 72) = v91;
                    *(_OWORD *)(v183 + 88) = v350;
                    *(_OWORD *)(v183 + 104) = *(_OWORD *)BugCheckParameter2;
                  }
                  memset((char *)&v403[1] + 8, 0, 24);
                  Win32HMThreadLockBase<tagWND,0,0>::Win32HMThreadLockBase<tagWND,0,0>(BugCheckParameter3, v141);
                  FindTimer((_DWORD)v141, 65523, 2, 1, 0);
                  if ( (unsigned int)IsMiPEnabledForWindow(v141) )
                    xxxSendTransformableMessageTimeout(v190, 0x24Au, 0, 0, 0, 1, 0);
                  if ( v92 )
                  {
                    v223 = *(_QWORD *)(a1 + 1512);
                    *(_OWORD *)(v223 + 24) = v184;
                    *(_OWORD *)(v223 + 40) = v185;
                    *(_OWORD *)(v223 + 56) = v186;
                    *(_OWORD *)(v223 + 72) = v187;
                    *(_OWORD *)(v223 + 88) = v188;
                    *(_OWORD *)(v223 + 104) = v189;
                  }
                  Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)BugCheckParameter3);
                  NextSysMsg = v342;
                }
                else
                {
                  PostEventMessageEx((struct tagTHREADINFO *)v182, v182[58], 0x15u, v141, 0, 0, 0, 0);
                }
              }
            }
          }
        }
        if ( v340 )
        {
          if ( *(_QWORD *)&v322[4] )
            v314 = **(_QWORD **)&v322[4];
          else
            v314 = 0;
          *(_QWORD *)(v137 + 16288) = v314;
        }
        else
        {
          *(_QWORD *)(v137 + 16288) = 0;
        }
      }
    }
    v29 = v340;
    if ( !v340 )
    {
      v147 = v82 - 1;
      if ( v147 )
      {
        if ( v147 == 1 )
          *(_DWORD *)(*(_QWORD *)(a1 + 464) + 168LL) = 0;
      }
      else
      {
        *(_DWORD *)(*(_QWORD *)(a1 + 464) + 160LL) = v390[1];
        v228 = v391[0] >> 16;
        *(_WORD *)(*(_QWORD *)(a1 + 464) + 164LL) = WORD1(v391[0]);
        v229 = W32GetUserSessionState(v228, v134, v135, v136);
        *(_DWORD *)(*(_QWORD *)(a1 + 464) + 168LL) = v392 + *(_DWORD *)(v229 + 14664);
        if ( *(_QWORD *)&v322[4] )
          v230 = **(_QWORD **)&v322[4];
        else
          v230 = 0;
        *(_QWORD *)(*(_QWORD *)(a1 + 464) + 176LL) = v230;
        *(_QWORD *)(*(_QWORD *)(a1 + 464) + 184LL) = *(_QWORD *)((char *)&v392 + 4);
      }
    }
    v139 = (const struct tagQMSG *)&v389;
    if ( v29 )
      v139 = (const struct tagQMSG *)&v412;
    if ( xxxMouseActivate((struct tagTHREADINFO *)a1, *(struct tagWND **)&v322[4], v139, v329) == 1 )
    {
      v9 = 1;
      goto LABEL_51;
    }
    if ( !*(_DWORD *)v322 )
      goto LABEL_190;
    v9 = 1;
    xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v389, 1);
LABEL_191:
    if ( *(_DWORD *)v322 && v337 && ((*(_BYTE *)(a1 + 712) | *(_BYTE *)(**(_QWORD **)(a1 + 496) + 16LL)) & 0x40) != 0 )
      xxxCallHook(6, v321, (__int64)v400, 5);
    v337 = 0;
    v327 = (void *)((LOWORD(v326.y) << 16) | LOWORD(v326.x));
    if ( v321 >= 0x200 )
      v328 = (unsigned int)GetMouseKeyFlags(*(_QWORD *)(a1 + 464));
    if ( (v321 - 171 <= 2 || v321 - 523 <= 2) && !v29 )
      v328 |= v391[0];
    if ( v329 == 5 )
    {
      if ( *(_DWORD *)v322 )
      {
        v315 = *(_QWORD *)(a1 + 640);
        if ( v315 )
        {
          if ( (*(_DWORD *)(v315 + 8) & 0x100) != 0 && *(_QWORD *)v315 && (**(_DWORD **)v315 & 1) != 0 )
          {
            MenuStateOwnerLockxxxUnlock::MenuStateOwnerLockxxxUnlock(
              (MenuStateOwnerLockxxxUnlock *)v371,
              *(struct tagMENUSTATE **)(a1 + 640));
            if ( !(unsigned int)xxxCallHandleMenuMessages(v315, *(_DWORD *)&v322[4], v321, v328, (__int64)v327) )
            {
              MenuStateOwnerLockxxxUnlock::~MenuStateOwnerLockxxxUnlock((MenuStateOwnerLockxxxUnlock *)v371);
              break;
            }
            MenuStateOwnerLockxxxUnlock::~MenuStateOwnerLockxxxUnlock((MenuStateOwnerLockxxxUnlock *)v371);
LABEL_845:
            v18 = FLOAT_1_0;
LABEL_846:
            v11 = v331;
            continue;
          }
        }
      }
    }
    break;
  }
  if ( !v29 )
    goto LABEL_198;
  v18 = FLOAT_1_0;
LABEL_210:
  v100 = v333;
LABEL_211:
  if ( ((HIDWORD(v396) - 2) & 0xFFFFFFCF) == 0 && HIDWORD(v396) != 50 )
  {
    v321 = (unsigned int)v390[1];
    v328 = v391[0];
    v327 = (void *)v391[1];
LABEL_214:
    if ( *(_DWORD *)v322 )
    {
      if ( !*(_QWORD *)(a1 + 640) && (unsigned int)IsMiPEnabledForThread(a1) && v29 )
      {
        if ( *(_QWORD *)&v322[4] )
          v101 = **(_QWORD **)&v322[4];
        else
          v101 = 0;
        *(_QWORD *)(*(_QWORD *)(a1 + 1512) + 48LL) = v101;
        v102 = *(_QWORD *)(a1 + 1512);
        v103 = *(_DWORD *)(v102 + 36);
        if ( (v103 & 0x400000) != 0 && (*(_DWORD *)(*(_QWORD *)&v322[4] + 380LL) & 0x40000000) == 0 )
          *(_DWORD *)(v102 + 36) = v103 & 0xFFBFFFFF;
        v104 = GetMiPWindowFlags(*(struct tagWND **)&v322[4]);
        SetMiPWindowFlags(*(struct tagWND **)&v322[4], v104 & 0xFFFFFFFFFFFFFFFEuLL);
        if ( ((LODWORD(v390[1]) - 578) & 0xFFFFFFFB) != 0 )
        {
          if ( ((LODWORD(v390[1]) - 579) & 0xFFFFFFFB) == 0 )
            **(_DWORD **)(a1 + 1512) &= ~8u;
        }
        else
        {
          v316 = 0;
          if ( LODWORD(v390[1]) == 578 )
            v316 = 8;
          **(_DWORD **)(a1 + 1512) = v316 | **(_DWORD **)(a1 + 1512) & 0xFFFFFFF7;
        }
      }
      else
      {
        xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v389, 1);
      }
    }
    if ( (unsigned int)IsPointerMessageTouchpad((struct tagTHREADINFO *)a1, v391[1], v29) )
    {
      if ( !*(_DWORD *)v322 && !ShouldReceiveTouchpadMessages((const struct tagTHREADINFO *)a1, v390[0]) )
        xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v389, 1);
      if ( v321 == 595 )
        v327 = (void *)-1LL;
    }
    goto LABEL_198;
  }
  EtwTraceBeginPointerMessageRetrieve(NextSysMsg, LOWORD(v391[0]), LODWORD(v390[1]));
  v423[0] = *(_OWORD *)NextSysMsg;
  v423[1] = *((_OWORD *)NextSysMsg + 1);
  v423[2] = *((_OWORD *)NextSysMsg + 2);
  v423[3] = *((_OWORD *)NextSysMsg + 3);
  v423[4] = *((_OWORD *)NextSysMsg + 4);
  v423[5] = *((_OWORD *)NextSysMsg + 5);
  v423[6] = *((_OWORD *)NextSysMsg + 6);
  v423[7] = *((_OWORD *)NextSysMsg + 7);
  v423[8] = *((_OWORD *)NextSysMsg + 8);
  v423[9] = *((_OWORD *)NextSysMsg + 9);
  v424 = *((_QWORD *)NextSysMsg + 20);
  v112 = (unsigned int)xxxRetrievePointerInputMessage(
                         a1,
                         v347,
                         v100,
                         a5,
                         1,
                         0,
                         (int *)v322,
                         NextSysMsg,
                         (struct tagWND **)&v322[4],
                         &v321,
                         &v328,
                         (unsigned __int64 *)&v327,
                         &v330,
                         v343);
  InputTraceLogging::Pointer::RetrieveMessage(v423, 0, v112);
  EtwTraceEndPointerMessageRetrieve(v423, LOWORD(v391[0]), LODWORD(v390[1]));
  v113 = *(_QWORD *)&v322[4];
  if ( *(_QWORD *)&v322[4] )
    Win32HM_ExchangeThreadLock<1>(*(_QWORD *)&v322[4], v361);
  v114 = v112 - 1;
  if ( !v114 )
    goto LABEL_214;
  v115 = v114 - 1;
  if ( v115 )
  {
    v116 = v115 - 1;
    if ( v116 )
    {
      *v343 = 0;
      if ( v116 == 1 )
      {
        v11 = v331;
        goto LABEL_23;
      }
    }
    else
    {
      xxxDefPointerProc(v113, LODWORD(v390[1]), v391[0], v391[1]);
      *v343 = 0;
    }
    goto LABEL_51;
  }
  if ( !v330 )
    goto LABEL_75;
  v345 = *(_QWORD *)(*(_QWORD *)&v322[4] + 16LL);
  v271 = v345;
  v272 = (Win32RawLockedW32Thread *)v383;
LABEL_734:
  Win32RawLockedW32Thread::Exchange(v272, (struct _W32THREAD *)v271);
LABEL_76:
  *(_QWORD *)(*(_QWORD *)(a1 + 464) + 80LL) = 0;
  if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20000) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
  {
    v9 = 0;
  }
  v39 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v9 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v122 = *(_QWORD *)(a1 + 464);
    v123 = *(_QWORD *)(v122 + 72);
    v124 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v24, v25);
    LOBYTE(v125) = v39;
    LOBYTE(v126) = v9;
    WPP_RECORDER_AND_TRACE_SF_qqq(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v126,
      v125,
      *(_QWORD *)(v124 + 69152),
      4,
      18,
      36,
      (__int64)WPP_49cdbed1bece331d44f23b214bd7a204_Traceguids,
      v122,
      a1,
      v123);
  }
  *(_QWORD *)(*(_QWORD *)(a1 + 464) + 72LL) = 0;
  **(_DWORD **)(a1 + 480) &= ~1u;
  v40 = v344;
  v41 = v349;
  v42 = v351;
  v43 = v345;
  if ( v358 )
  {
    SetWakeBit(v358, 16385);
    ClearWakeBit((struct tagTHREADINFO *)a1, 0x4001u, 0);
  }
  else if ( !v344 && !v349 && !v351 && !v345 )
  {
    v44 = *(_QWORD *)(a1 + 464);
    if ( !*(_DWORD *)(v44 + 40) )
      _InterlockedAnd(
        (volatile signed __int32 *)(*(_QWORD *)(a1 + 480) + 8LL),
        (*(_DWORD *)(v44 + 508) >> 4) & 2 | 0xFFFF83F8);
    goto LABEL_87;
  }
  if ( v40 )
  {
    SetWakeBit(v40, 16390);
    ClearWakeBit((struct tagTHREADINFO *)a1, 0x4006u, 0);
  }
  if ( v42 )
  {
    SetWakeBit(v42, 17408);
    ClearWakeBit((struct tagTHREADINFO *)a1, 0x4400u, 0);
  }
  if ( v43 )
  {
    SetWakeBit(v43, 20480);
    ClearWakeBit((struct tagTHREADINFO *)a1, 0x5000u, 0);
  }
  if ( v41 )
  {
    SetWakeBit(v41, 8256);
    _InterlockedAnd((volatile signed __int32 *)(*(_QWORD *)(a1 + 480) + 8LL), 0xFFFFDFFF);
  }
LABEL_87:
  if ( v336[0] )
  {
    v45 = PtiCurrent();
    *((_QWORD *)v45 + 170) &= ~0x1000000000uLL;
  }
  Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)v361);
  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v383);
  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v384);
  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v382);
  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v380);
  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v381);
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
