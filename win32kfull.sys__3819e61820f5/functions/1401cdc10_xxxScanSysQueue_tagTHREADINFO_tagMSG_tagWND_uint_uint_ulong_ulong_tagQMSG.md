# xxxScanSysQueue(tagTHREADINFO *,tagMSG *,tagWND *,uint,uint,ulong,ulong,tagQMSG * *)

- ea: `0x1401cdc10`
- end: `0x1401d2c4e`
- name: `?xxxScanSysQueue@@YA?AW4_SCANSYSQUEUERESULT@@PEAUtagTHREADINFO@@PEAUtagMSG@@PEAUtagWND@@IIKKPEAPEAUtagQMSG@@@Z`
- size: `20542`
- prototype: ``
- caller_count: `1`
- callee_count: `112`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1400354a0`

## callees

- `0x140004cbc`
- `0x140004cd8`
- `0x14000550c`
- `0x1400055d8`
- `0x140008690`
- `0x14000cd90`
- `0x14001070c`
- `0x140016f5c`
- `0x14001cb40`
- `0x14001ec90`
- `0x140020d30`
- `0x1400218e0`
- `0x14002193c`
- `0x140024100`
- `0x140025930`
- `0x1400271f0`
- `0x140027d10`
- `0x140027d44`
- `0x1400282f8`
- `0x140028660`
- `0x1400286dc`
- `0x1400292ec`
- `0x14002b638`
- `0x14002b900`
- `0x1400303e0`
- `0x140030960`
- `0x140030a90`
- `0x140030ea0`
- `0x1400327d0`
- `0x140033080`
- `0x14003345c`
- `0x1400381a8`
- `0x14005b480`
- `0x140084eb0`
- `0x140085e30`
- `0x1400a7314`
- `0x1400af078`
- `0x1400b4c60`
- `0x1400ba610`
- `0x1400bc81c`
- `0x1400bcaa0`
- `0x1400bcac8`
- `0x1400c027c`
- `0x1400c4270`
- `0x1400c53dc`
- `0x1400d2888`
- `0x1400dcc84`
- `0x1400dcf20`
- `0x1400dd0f0`
- `0x1400dd1d0`

## import_xrefs

- `ntoskrnl!PsGetWin32KFilterSet` at `0x1401ceb91`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x1401d04be`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x1401ceb91`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x1401d04be`
- `ntoskrnl!KeBugCheckEx` at `0x1401d1047`
- `ntoskrnl!KeBugCheckEx` at `0x1401d1047`
- `win32kbase!GetTouchTimeFromCPLValue` at `0x1401d08fc`
- `win32kbase!GetTouchTimeFromCPLValue` at `0x1401d08fc`
- `win32kbase!EtwTraceRetrieveInputMessage` at `0x1401ce5b2`
- `win32kbase!EtwTraceRetrieveInputMessage` at `0x1401ce5b2`
- `win32kbase!?UpdateLastInputData@tagTHREADINFO@@QEAAXPEBUtagQMSG@@@Z` at `0x1401cef25`
- `win32kbase!?UpdateLastInputData@tagTHREADINFO@@QEAAXPEBUtagQMSG@@@Z` at `0x1401cef25`
- `win32kbase!EtwTraceEndPointerMessageRetrieve` at `0x1401cf4bc`
- `win32kbase!EtwTraceEndPointerMessageRetrieve` at `0x1401cf4bc`
- `win32kbase!EtwTraceBeginPointerMessageRetrieve` at `0x1401cf37d`
- `win32kbase!EtwTraceBeginPointerMessageRetrieve` at `0x1401cf37d`
- `win32kbase!ProcessTranslatedChar` at `0x1401d1aaf`
- `win32kbase!ProcessTranslatedChar` at `0x1401d1aaf`
- `win32kbase!CheckImEnabled` at `0x1401d1a4f`
- `win32kbase!CheckImEnabled` at `0x1401d1a4f`
- `win32kbase!?UpdateInputSource@tagTHREADINFO@@QEAAXAEBUtagINPUT_MESSAGE_SOURCE@@@Z` at `0x1401d0108`
- `win32kbase!?UpdateInputSource@tagTHREADINFO@@QEAAXAEBUtagINPUT_MESSAGE_SOURCE@@@Z` at `0x1401d0b98`
- `win32kbase!?UpdateInputSource@tagTHREADINFO@@QEAAXAEBUtagINPUT_MESSAGE_SOURCE@@@Z` at `0x1401d0108`
- `win32kbase!?UpdateInputSource@tagTHREADINFO@@QEAAXAEBUtagINPUT_MESSAGE_SOURCE@@@Z` at `0x1401d0b98`
- `win32kbase!GetMouseKeyFlags` at `0x1401cee08`
- `win32kbase!GetMouseKeyFlags` at `0x1401d03c1`
- `win32kbase!GetMouseKeyFlags` at `0x1401cee08`
- `win32kbase!GetMouseKeyFlags` at `0x1401d03c1`
- `win32kbase!IsMessageInputSourcePen` at `0x1401d0de1`
- `win32kbase!IsMessageInputSourcePen` at `0x1401d0de1`
- `win32kbase!IsMessageInputSourceTouch` at `0x1401d0db6`
- `win32kbase!IsMessageInputSourceTouch` at `0x1401d0db6`
- `win32kbase!EtwTraceUIPIMsgError` at `0x1401d2314`
- `win32kbase!EtwTraceUIPIMsgError` at `0x1401d2314`
- `win32kbase!MiPCheckMsgFilter` at `0x1401ceabd`
- `win32kbase!MiPCheckMsgFilter` at `0x1401d035b`
- `win32kbase!MiPCheckMsgFilter` at `0x1401d1cf2`
- `win32kbase!MiPCheckMsgFilter` at `0x1401ceabd`
- `win32kbase!MiPCheckMsgFilter` at `0x1401d035b`
- `win32kbase!MiPCheckMsgFilter` at `0x1401d1cf2`
- `win32kbase!EtwTraceRetrieveQueueEventMessage` at `0x1401ce30a`
- `win32kbase!EtwTraceRetrieveQueueEventMessage` at `0x1401ce30a`
- `win32kbase!ShouldDeferMessage` at `0x1401ce2a7`
- `win32kbase!ShouldDeferMessage` at `0x1401ce2a7`
- `win32kbase!DeferSysPeekMsg` at `0x1401ce2c7`
- `win32kbase!DeferSysPeekMsg` at `0x1401d0f74`
- `win32kbase!DeferSysPeekMsg` at `0x1401d12db`
- `win32kbase!DeferSysPeekMsg` at `0x1401ce2c7`
- `win32kbase!DeferSysPeekMsg` at `0x1401d0f74`
- `win32kbase!DeferSysPeekMsg` at `0x1401d12db`
- `win32kbase!EtwTraceInputQueueLocked` at `0x1401cf63f`
- `win32kbase!EtwTraceInputQueueLocked` at `0x1401cf63f`
- `win32kbase!EtwTraceInputQueueLockedPeekRecursion` at `0x1401cf7e3`
- `win32kbase!EtwTraceInputQueueLockedPeekRecursion` at `0x1401cf7e3`
- `win32kbase!EtwTraceInputProcessDelay` at `0x1401ce571`
- `win32kbase!EtwTraceInputProcessDelay` at `0x1401ce571`
- `win32kbase!IsGenuineMouseInput` at `0x1401cf8f3`
- `win32kbase!IsGenuineMouseInput` at `0x1401cf972`
- `win32kbase!IsGenuineMouseInput` at `0x1401d09cc`
- `win32kbase!IsGenuineMouseInput` at `0x1401d1f68`
- `win32kbase!IsGenuineMouseInput` at `0x1401cf8f3`
- `win32kbase!IsGenuineMouseInput` at `0x1401cf972`
- `win32kbase!IsGenuineMouseInput` at `0x1401d09cc`
- `win32kbase!IsGenuineMouseInput` at `0x1401d1f68`
- `win32kbase!IsMiPMouseMessage` at `0x1401cf8db`
- `win32kbase!IsMiPMouseMessage` at `0x1401d09e3`
- `win32kbase!IsMiPMouseMessage` at `0x1401d1f50`
- `win32kbase!IsMiPMouseMessage` at `0x1401cf8db`
- `win32kbase!IsMiPMouseMessage` at `0x1401d09e3`
- `win32kbase!IsMiPMouseMessage` at `0x1401d1f50`
- `win32kbase!ReferenceW32Thread` at `0x1401cf749`
- `win32kbase!ReferenceW32Thread` at `0x1401cf749`
- `win32kbase!IsDesktopApp` at `0x1401d1890`
- `win32kbase!IsDesktopApp` at `0x1401d1890`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1401d235c`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1401d235c`
- `win32kbase!IsWindowDesktopComposed` at `0x1401cff4a`
- `win32kbase!IsWindowDesktopComposed` at `0x1401cff4a`
- `win32kbase!ValidateHwnd` at `0x1401d219b`
- `win32kbase!ValidateHwnd` at `0x1401d219b`
- `WIN32K!W32GetUserSessionState` at `0x1401ce846`
- `WIN32K!W32GetUserSessionState` at `0x1401cf17a`
- `WIN32K!W32GetUserSessionState` at `0x1401cf306`
- `WIN32K!W32GetUserSessionState` at `0x1401cf68b`
- `WIN32K!W32GetUserSessionState` at `0x1401cf932`
- `WIN32K!W32GetUserSessionState` at `0x1401cfcc8`
- `WIN32K!W32GetUserSessionState` at `0x1401d0189`
- `WIN32K!W32GetUserSessionState` at `0x1401d0a60`
- `WIN32K!W32GetUserSessionState` at `0x1401d0a78`
- `WIN32K!W32GetUserSessionState` at `0x1401d0a8c`
- `WIN32K!W32GetUserSessionState` at `0x1401d0fc8`
- `WIN32K!W32GetUserSessionState` at `0x1401d115e`
- `WIN32K!W32GetUserSessionState` at `0x1401d1202`
- `WIN32K!W32GetUserSessionState` at `0x1401d1399`
- `WIN32K!W32GetUserSessionState` at `0x1401d1400`
- `WIN32K!W32GetUserSessionState` at `0x1401d197f`
- `WIN32K!W32GetUserSessionState` at `0x1401d1af5`
- `WIN32K!W32GetUserSessionState` at `0x1401d216f`
- `WIN32K!W32GetUserSessionState` at `0x1401d2225`
- `WIN32K!W32GetUserSessionState` at `0x1401d2320`
- `WIN32K!W32GetUserSessionState` at `0x1401d23e7`
- `WIN32K!W32GetUserSessionState` at `0x1401d2457`
- `WIN32K!W32GetUserSessionState` at `0x1401d2489`
- `WIN32K!W32GetUserSessionState` at `0x1401d24bb`
- `WIN32K!W32GetUserSessionState` at `0x1401d24eb`
- `WIN32K!W32GetUserSessionState` at `0x1401ce846`
- `WIN32K!W32GetUserSessionState` at `0x1401cf17a`
- `WIN32K!W32GetUserSessionState` at `0x1401cf306`
- `WIN32K!W32GetUserSessionState` at `0x1401cf68b`
- `WIN32K!W32GetUserSessionState` at `0x1401cf932`
- `WIN32K!W32GetUserSessionState` at `0x1401cfcc8`
- `WIN32K!W32GetUserSessionState` at `0x1401d0189`
- `WIN32K!W32GetUserSessionState` at `0x1401d0a60`
- `WIN32K!W32GetUserSessionState` at `0x1401d0a78`
- `WIN32K!W32GetUserSessionState` at `0x1401d0a8c`
- `WIN32K!W32GetUserSessionState` at `0x1401d0fc8`
- `WIN32K!W32GetUserSessionState` at `0x1401d115e`
- `WIN32K!W32GetUserSessionState` at `0x1401d1202`
- `WIN32K!W32GetUserSessionState` at `0x1401d1399`
- `WIN32K!W32GetUserSessionState` at `0x1401d1400`
- `WIN32K!W32GetUserSessionState` at `0x1401d197f`
- `WIN32K!W32GetUserSessionState` at `0x1401d1af5`
- `WIN32K!W32GetUserSessionState` at `0x1401d216f`
- `WIN32K!W32GetUserSessionState` at `0x1401d2225`
- `WIN32K!W32GetUserSessionState` at `0x1401d2320`
- `WIN32K!W32GetUserSessionState` at `0x1401d23e7`
- `WIN32K!W32GetUserSessionState` at `0x1401d2457`
- `WIN32K!W32GetUserSessionState` at `0x1401d2489`
- `WIN32K!W32GetUserSessionState` at `0x1401d24bb`
- `WIN32K!W32GetUserSessionState` at `0x1401d24eb`

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
  __int64 v153; // r8
  __int64 v154; // r9
  const struct tagWND *v155; // rdi
  char v156; // di
  char v157; // bl
  __int64 v158; // rdx
  __int64 v159; // rcx
  __int64 v160; // r8
  __int64 v161; // r9
  int v162; // r15d
  int v163; // r13d
  __int64 v164; // rdi
  unsigned int v165; // ebx
  __int64 v166; // r8
  __int64 v167; // r9
  __int64 v168; // rax
  __int64 v169; // rcx
  __int64 v170; // rdx
  ULONG_PTR v171; // r15
  __int64 v172; // rcx
  __int64 v173; // rcx
  int v174; // eax
  struct tagWND *v175; // rbx
  int v176; // eax
  unsigned int MouseKeyFlags; // eax
  __int64 v178; // rcx
  char MiPWindowFlags; // al
  struct tagQ **v180; // rcx
  __int64 v181; // rax
  __int128 v182; // xmm6
  __int128 v183; // xmm7
  __int128 v184; // xmm8
  __int128 v185; // xmm9
  __int128 v186; // xmm10
  __int128 v187; // xmm11
  struct tagWND *v188; // rcx
  unsigned int v189; // ecx
  __int64 v190; // rcx
  __int64 v191; // rcx
  int v192; // eax
  int v193; // ecx
  int TouchTimeFromCPLValue; // eax
  __int64 v195; // rdx
  int v196; // eax
  struct tagWND *v197; // rbx
  __int64 v198; // rcx
  __int64 v199; // rdx
  __int64 v200; // rcx
  __int64 v201; // r8
  __int64 v202; // r9
  char v203; // r8
  unsigned int v204; // ecx
  unsigned int v205; // edx
  __int64 v206; // rcx
  _QWORD *v207; // rax
  unsigned __int64 v208; // rbx
  ULONG_PTR v209; // r13
  unsigned __int64 v210; // r9
  unsigned int v211; // eax
  __int64 ThreadDesktopWindow; // rax
  int v213; // ebx
  __int64 v214; // rbx
  __int64 v215; // rdx
  __int64 v216; // rdx
  struct tagWND *v217; // rax
  __int64 v218; // rax
  char v219; // al
  int v220; // ecx
  __int64 v221; // rax
  __int64 v222; // r8
  __int64 v223; // r9
  char v224; // r15
  unsigned int v225; // r15d
  unsigned __int64 v226; // rcx
  __int64 v227; // rax
  __int64 v228; // rcx
  struct tagTHREADINFO *BugCheckParameter4; // rax
  float v230; // xmm2_4
  __int64 v231; // r8
  struct tagQ *v232; // rdi
  __int64 v233; // rbx
  __int64 v234; // rax
  int v235; // r8d
  int v236; // edx
  struct tagQ *v237; // rdi
  __int64 v238; // rbx
  __int64 v239; // rax
  int v240; // r8d
  int v241; // edx
  int v242; // r15d
  struct tagQ *v243; // rdi
  __int64 v244; // rbx
  __int64 v245; // rax
  int v246; // r8d
  int v247; // edx
  struct tagQ *v248; // rdi
  __int64 v249; // rbx
  __int64 v250; // rax
  int v251; // r8d
  int v252; // edx
  int v253; // ebx
  struct tagWND *CompositeAppFrameWindowOrSelf; // rdi
  BOOL v255; // ebx
  struct tagQ *v256; // rcx
  __int64 v257; // rax
  __int64 v258; // rcx
  __int64 v259; // rcx
  __int64 v260; // rbx
  struct tagQ *v261; // rdi
  __int64 v262; // rbx
  __int64 v263; // rax
  int v264; // r8d
  int v265; // edx
  __int64 v266; // rdx
  HWND *v267; // rdx
  __int64 v268; // rdx
  __int64 v269; // rdx
  Win32RawLockedW32Thread *v270; // rcx
  int v271; // eax
  int v272; // r9d
  _DWORD *v273; // rax
  _DWORD *v274; // rax
  __int64 v275; // rcx
  __int64 v276; // rcx
  __int64 v277; // rax
  __int64 v278; // r8
  __int64 v279; // rdx
  __int64 v280; // rax
  int v281; // r8d
  int v282; // edx
  __int64 v283; // rdx
  __int64 v284; // rax
  __int64 v285; // rcx
  LONG v286; // eax
  __int64 v287; // rdx
  __int64 v288; // r8
  __int64 v289; // r9
  __int64 v290; // rax
  __int64 v291; // rcx
  __int64 v292; // rdx
  __int64 v293; // kr00_8
  __int64 v294; // r8
  __int64 v295; // r9
  __int64 v296; // rdx
  __int64 v297; // kr08_8
  __int64 v298; // r8
  __int64 v299; // r9
  __int64 v300; // rax
  __int64 v301; // rcx
  __int64 v302; // rdx
  __int64 v303; // rt2
  __int64 v304; // r8
  __int64 v305; // r9
  __int64 v306; // rcx
  const struct tagWND *v307; // rcx
  struct tagWND *v308; // rax
  const struct tagWND *TopLevelWindow; // rax
  __int64 v310; // r8
  __int64 v311; // r8
  __int64 v312; // rax
  __int64 v313; // rbx
  int v314; // edx
  int v315; // eax
  struct tagTHREADINFO *v316; // rcx
  int InteractiveControlInputMessage; // eax
  char v318; // [rsp+48h] [rbp-690h]
  unsigned int v319; // [rsp+70h] [rbp-668h] BYREF
  _BYTE v320[12]; // [rsp+74h] [rbp-664h] BYREF
  int v321; // [rsp+80h] [rbp-658h]
  BOOL v322; // [rsp+84h] [rbp-654h]
  bool v323; // [rsp+88h] [rbp-650h]
  struct tagPOINT v324; // [rsp+90h] [rbp-648h] BYREF
  void *v325; // [rsp+98h] [rbp-640h] BYREF
  unsigned __int64 v326; // [rsp+A0h] [rbp-638h] BYREF
  int v327; // [rsp+A8h] [rbp-630h] BYREF
  int v328; // [rsp+ACh] [rbp-62Ch] BYREF
  struct tagQ **v329; // [rsp+B0h] [rbp-628h]
  unsigned int v330; // [rsp+B8h] [rbp-620h]
  unsigned int v331; // [rsp+BCh] [rbp-61Ch]
  bool v332; // [rsp+C0h] [rbp-618h]
  bool v333; // [rsp+C1h] [rbp-617h]
  char v334[2]; // [rsp+C2h] [rbp-616h] BYREF
  int v335; // [rsp+C4h] [rbp-614h]
  int v336; // [rsp+C8h] [rbp-610h]
  unsigned int v337; // [rsp+CCh] [rbp-60Ch]
  int v338; // [rsp+D0h] [rbp-608h]
  int v339; // [rsp+D4h] [rbp-604h]
  struct tagQMSG *v340; // [rsp+D8h] [rbp-600h]
  struct tagQMSG **v341; // [rsp+E0h] [rbp-5F8h]
  __int64 v342; // [rsp+E8h] [rbp-5F0h]
  __int64 v343; // [rsp+F0h] [rbp-5E8h]
  ULONG_PTR v344; // [rsp+F8h] [rbp-5E0h]
  __int64 v345; // [rsp+100h] [rbp-5D8h]
  int v346; // [rsp+108h] [rbp-5D0h]
  __int64 v347; // [rsp+110h] [rbp-5C8h]
  __int128 v348; // [rsp+118h] [rbp-5C0h]
  struct _W32THREAD *v349; // [rsp+128h] [rbp-5B0h]
  int v350; // [rsp+130h] [rbp-5A8h]
  int v351; // [rsp+134h] [rbp-5A4h]
  unsigned int v352; // [rsp+138h] [rbp-5A0h]
  unsigned int v353; // [rsp+140h] [rbp-598h]
  unsigned int v354; // [rsp+144h] [rbp-594h]
  struct tagTHREADINFO *v355; // [rsp+148h] [rbp-590h]
  struct _W32THREAD *v356; // [rsp+150h] [rbp-588h]
  ULONG_PTR BugCheckParameter2[2]; // [rsp+158h] [rbp-580h] BYREF
  __int64 v358; // [rsp+168h] [rbp-570h]
  ULONG_PTR v359[2]; // [rsp+170h] [rbp-568h] BYREF
  __int64 v360; // [rsp+180h] [rbp-558h]
  struct tagMSG *v361; // [rsp+188h] [rbp-550h]
  __int64 v362; // [rsp+190h] [rbp-548h]
  __int64 v363; // [rsp+1A8h] [rbp-530h]
  struct tagMSG *v364; // [rsp+1B0h] [rbp-528h]
  __int64 v365; // [rsp+1C8h] [rbp-510h]
  __int64 v366; // [rsp+1D0h] [rbp-508h]
  __int64 v367; // [rsp+1D8h] [rbp-500h]
  __int64 v368; // [rsp+1E0h] [rbp-4F8h]
  char v369[8]; // [rsp+1E8h] [rbp-4F0h] BYREF
  unsigned int v370; // [rsp+1F0h] [rbp-4E8h] BYREF
  unsigned int v371; // [rsp+1F4h] [rbp-4E4h]
  int v372; // [rsp+1F8h] [rbp-4E0h]
  int v373; // [rsp+1FCh] [rbp-4DCh]
  int v374; // [rsp+200h] [rbp-4D8h]
  struct tagMSG *v375; // [rsp+208h] [rbp-4D0h]
  ULONG_PTR v376[2]; // [rsp+210h] [rbp-4C8h] BYREF
  __int64 v377; // [rsp+220h] [rbp-4B8h]
  _BYTE v378[24]; // [rsp+228h] [rbp-4B0h] BYREF
  _BYTE v379[24]; // [rsp+240h] [rbp-498h] BYREF
  _BYTE v380[24]; // [rsp+258h] [rbp-480h] BYREF
  _BYTE v381[24]; // [rsp+270h] [rbp-468h] BYREF
  _BYTE v382[48]; // [rsp+288h] [rbp-450h] BYREF
  ULONG_PTR v383[2]; // [rsp+2B8h] [rbp-420h] BYREF
  ULONG_PTR v384[2]; // [rsp+2C8h] [rbp-410h] BYREF
  ULONG_PTR v385[3]; // [rsp+2D8h] [rbp-400h] BYREF
  ULONG_PTR BugCheckParameter3[2]; // [rsp+2F0h] [rbp-3E8h] BYREF
  __int128 v387; // [rsp+300h] [rbp-3D8h] BYREF
  HWND v388[2]; // [rsp+310h] [rbp-3C8h]
  unsigned __int64 v389[2]; // [rsp+320h] [rbp-3B8h]
  __int128 v390; // [rsp+330h] [rbp-3A8h]
  __int128 v391; // [rsp+340h] [rbp-398h]
  struct tagPOINT v392[2]; // [rsp+350h] [rbp-388h] BYREF
  __int128 v393; // [rsp+360h] [rbp-378h]
  __int128 v394; // [rsp+370h] [rbp-368h] BYREF
  __int128 v395; // [rsp+380h] [rbp-358h]
  __int128 v396; // [rsp+390h] [rbp-348h]
  __int64 v397; // [rsp+3A0h] [rbp-338h]
  __int64 v398[2]; // [rsp+3B0h] [rbp-328h] BYREF
  __int128 v399; // [rsp+3C0h] [rbp-318h]
  __int64 v400; // [rsp+3D0h] [rbp-308h]
  _OWORD v401[3]; // [rsp+3E0h] [rbp-2F8h] BYREF
  __int128 v402; // [rsp+410h] [rbp-2C8h]
  __int128 v403; // [rsp+420h] [rbp-2B8h]
  __int128 v404; // [rsp+430h] [rbp-2A8h]
  __int128 v405; // [rsp+440h] [rbp-298h]
  __int128 v406; // [rsp+450h] [rbp-288h]
  __int128 v407; // [rsp+460h] [rbp-278h]
  __int128 v408; // [rsp+470h] [rbp-268h]
  __int64 v409; // [rsp+480h] [rbp-258h]
  __int128 v410; // [rsp+490h] [rbp-248h] BYREF
  __int128 v411; // [rsp+4A0h] [rbp-238h]
  __int128 v412; // [rsp+4B0h] [rbp-228h]
  __int128 v413; // [rsp+4C0h] [rbp-218h]
  __int128 v414; // [rsp+4D0h] [rbp-208h]
  __int128 v415; // [rsp+4E0h] [rbp-1F8h]
  __int128 v416; // [rsp+4F0h] [rbp-1E8h]
  __int128 v417; // [rsp+500h] [rbp-1D8h]
  __int128 v418; // [rsp+510h] [rbp-1C8h]
  __int128 v419; // [rsp+520h] [rbp-1B8h]
  __int64 v420; // [rsp+530h] [rbp-1A8h]
  _OWORD v421[10]; // [rsp+540h] [rbp-198h] BYREF
  __int64 v422; // [rsp+5E0h] [rbp-F8h]

  v331 = a4;
  v345 = a3;
  v364 = a2;
  v360 = a1;
  v365 = a1;
  v375 = a2;
  v355 = (struct tagTHREADINFO *)a1;
  v366 = a1;
  v361 = a2;
  v368 = a3;
  v352 = a4;
  v341 = a8;
  memset_0(&v387, 0, 0xA8u);
  *(_DWORD *)&v320[8] = 0;
  v319 = 0;
  v326 = 0;
  v325 = 0;
  v324 = 0;
  v328 = 0;
  v327 = 0;
  *(_OWORD *)v398 = 0;
  v399 = 0;
  v400 = 0;
  v9 = 1;
  v10 = a6 & 1;
  *(_QWORD *)v320 = v10;
  *a8 = 0;
  v11 = (struct tagQ **)(a1 + 464);
  v329 = (struct tagQ **)(a1 + 464);
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
    v329 = (struct tagQ **)(a1 + 464);
  }
  v367 = a1 + 464;
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
        (__int64)WPP_b198703289513b726a6724fd49b6e756_Traceguids,
        (char)v13,
        a1,
        a1);
      v12 = a7;
    }
    v11 = v329;
    *((_QWORD *)*v329 + 9) = a1;
    **(_DWORD **)(a1 + 480) |= 1u;
    LODWORD(v10) = *(_DWORD *)v320;
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
  v363 = a1;
  v354 = a5;
  v377 = a1;
  v353 = v331;
  v350 = 0;
  v339 = 0;
  v330 = 0;
  v322 = 0;
  v323 = 0;
  v344 = 0;
  v346 = 0;
  v335 = 0;
  v321 = 0;
  v342 = 0;
  v362 = 0;
  v356 = 0;
  v347 = 0;
  v349 = 0;
  v343 = 0;
  Win32RawLockedW32Thread::Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v379, 0);
  Win32RawLockedW32Thread::Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v378, 0);
  Win32RawLockedW32Thread::Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v380, 0);
  Win32RawLockedW32Thread::Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v382, 0);
  Win32RawLockedW32Thread::Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v381, 0);
  *(_QWORD *)&v320[4] = 0;
  Win32HMOptionalThreadLock<tagWND>::Win32HMOptionalThreadLock<tagWND>(v359, a1, 0);
  CManageInScanSysQueueBit::CManageInScanSysQueueBit((CManageInScanSysQueueBit *)v334);
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
      v232 = *v11;
      v233 = *((_QWORD *)*v11 + 11);
      v234 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v16, v17);
      LOBYTE(v235) = v19;
      LOBYTE(v236) = v9;
      WPP_RECORDER_AND_TRACE_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v236,
        v235,
        *(_QWORD *)(v234 + 69152),
        5,
        18,
        30,
        (__int64)WPP_b198703289513b726a6724fd49b6e756_Traceguids,
        (char)v232,
        v233);
      v11 = v329;
    }
    *((_QWORD *)*v11 + 11) = 0;
LABEL_22:
    v9 = 1;
LABEL_23:
    LOBYTE(i) = v322;
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
                    v374 = v21;
                    v22 = *v11;
                    if ( *((_QWORD *)*v11 + 11) )
                    {
                      if ( !(_BYTE)i )
                      {
                        v322 = ((v330 - 1) & 0xFFFFFFFD) == 0;
                        v323 = ((v330 - 1) & 0xFFFFFFFD) == 0;
                      }
                    }
                    else
                    {
                      v330 = 0;
                      v322 = 0;
                      v323 = 0;
                    }
                    v326 = 0;
                    NextSysMsg = xxxGetNextSysMsg(
                                   (struct tagTHREADINFO *)a1,
                                   *((struct tagQMSG **)v22 + 11),
                                   (struct tagQMSG *)&v387);
                    v340 = NextSysMsg;
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
                      v237 = *v11;
                      v238 = *((_QWORD *)*v11 + 11);
                      v239 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v24, v25);
                      v318 = (char)v237;
                      NextSysMsg = v340;
                      LOBYTE(v240) = v26;
                      LOBYTE(v241) = v9;
                      WPP_RECORDER_AND_TRACE_SF_qqq(
                        *((_QWORD *)WPP_GLOBAL_Control + 3),
                        v241,
                        v240,
                        *(_QWORD *)(v239 + 69152),
                        5,
                        18,
                        31,
                        (__int64)WPP_b198703289513b726a6724fd49b6e756_Traceguids,
                        (char)v340,
                        v318,
                        v238);
                      v11 = v329;
                    }
                    *((_QWORD *)*v11 + 11) = NextSysMsg;
                    if ( !NextSysMsg )
                      goto LABEL_33;
                    v34 = DWORD1(v393);
                    if ( (BYTE4(v393) & 0x20) != 0 )
                    {
                      i = (__int64)v341;
                      *v341 = NextSysMsg;
                      *((_DWORD *)NextSysMsg + 25) |= 0x100u;
                      *(_DWORD *)v320 = 0;
                      v34 = DWORD1(v393);
                      if ( (DWORD1(v393) & 0x8000000) != 0 )
                      {
                        *(_DWORD *)(*(_QWORD *)i + 100LL) |= 0x8000000u;
                        v34 = DWORD1(v393);
                      }
                    }
                    if ( (v34 & 0x2000) == 0 )
                      break;
                    v242 = v330;
                    v9 = 1;
                    if ( *((_QWORD *)&v393 + 1) == a1 )
                      v242 = 1;
                    v330 = v242;
                    LOBYTE(i) = 1;
                    v322 = i;
                    v323 = 1;
                  }
                  LOBYTE(i) = v322;
                  if ( (v34 & 0x10000) == 0 )
                    break;
                  v9 = 1;
                  if ( *((_QWORD *)&v393 + 1) == a1 )
                  {
                    v330 = 3;
                    goto LABEL_23;
                  }
                }
                if ( (_DWORD)v393 == 4 && v322 )
                {
                  DeferSysPeekMsg(a1, 3);
                  goto LABEL_22;
                }
                if ( (v34 & 0x4000) == 0 )
                  break;
                v9 = 1;
                if ( *((_QWORD *)&v393 + 1) == a1 )
                  v330 = 2;
              }
              if ( (unsigned int)ShouldDeferMessage(v330, &v387) )
              {
                DeferSysPeekMsg(a1, 3);
                v330 = 3;
                goto LABEL_22;
              }
LABEL_33:
              if ( !*((_QWORD *)*v11 + 11) )
              {
                if ( a7 == 0x2000 )
                  _InterlockedAnd((volatile signed __int32 *)(*(_QWORD *)(a1 + 480) + 8LL), 0xFFFFDFFF);
                goto LABEL_75;
              }
              Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)v359);
              v9 = 1;
              LOBYTE(v27) = 1;
              *(_QWORD *)&v320[4] = HMValidateHandleNoSecure(v388[0], v27);
              Win32HM_LockIntoThread<1>(a1, *(_QWORD *)&v320[4], v359);
              v28 = (unsigned int)v393;
              if ( !(_DWORD)v393 )
                break;
              if ( (_DWORD)v393 == 4 )
              {
                LOBYTE(i) = v322;
                if ( *((_QWORD *)*v11 + 11) != *((_QWORD *)*v11 + 3) )
                  continue;
              }
              if ( (_DWORD)v393 != 9 || LODWORD(v388[1]) != 96 )
                goto LABEL_65;
              for ( i = *((_QWORD *)&v387 + 1); i && (unsigned int)IsHiddenByInputService(); i = *(_QWORD *)(i + 8) )
                ;
              v51 = i == 0;
              LOBYTE(i) = v322;
              if ( v51 )
              {
LABEL_65:
                v35 = *((_QWORD *)&v393 + 1);
                if ( !*((_QWORD *)&v393 + 1) || *((_QWORD *)&v393 + 1) == a1 )
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
                    v248 = *v11;
                    v249 = *((_QWORD *)*v11 + 11);
                    v250 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v36, v37);
                    LOBYTE(v251) = v38;
                    LOBYTE(v252) = v9;
                    WPP_RECORDER_AND_TRACE_SF_qq(
                      *((_QWORD *)WPP_GLOBAL_Control + 3),
                      v252,
                      v251,
                      *(_QWORD *)(v250 + 69152),
                      5,
                      18,
                      33,
                      (__int64)WPP_b198703289513b726a6724fd49b6e756_Traceguids,
                      (char)v248,
                      v249);
                    v11 = v329;
                  }
                  *((_QWORD *)*v11 + 11) = 0;
                  xxxProcessEventMessage(a1, &v387);
                  v9 = 1;
                  goto LABEL_14;
                }
                if ( *(struct tagQ **)(*((_QWORD *)&v393 + 1) + 464LL) != *v11 )
                {
                  CleanEventMessage(*((struct tagQMSG **)*v11 + 11));
                  DelQEntry((char *)*v11 + 24, *((_QWORD *)*v11 + 11), 1);
                  goto LABEL_14;
                }
                ReferenceW32Thread(*((_QWORD *)&v393 + 1));
                ExchangeW32ThreadLock(v35, v380);
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
                  v243 = *v11;
                  v244 = *((_QWORD *)*v11 + 11);
                  v245 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v24, v25);
                  LOBYTE(v246) = v9;
                  LOBYTE(v247) = v127;
                  WPP_RECORDER_AND_TRACE_SF_qq(
                    *((_QWORD *)WPP_GLOBAL_Control + 3),
                    v247,
                    v246,
                    *(_QWORD *)(v245 + 69152),
                    5,
                    18,
                    32,
                    (__int64)WPP_b198703289513b726a6724fd49b6e756_Traceguids,
                    (char)v243,
                    v244);
                  v11 = v329;
                }
                *((_QWORD *)*v11 + 11) = 0;
                v347 = v35;
                goto LABEL_75;
              }
            }
            i = v322;
          }
          while ( a7 == 0x2000 );
          v29 = 0;
          v338 = 0;
          v336 = 0;
          v337 = 0;
          v319 = (unsigned int)v388[1];
          if ( LODWORD(v388[1]) > 0x24A )
          {
            if ( LODWORD(v388[1]) <= 0x2ED )
            {
              if ( LODWORD(v388[1]) == 749 )
                goto LABEL_873;
              if ( LODWORD(v388[1]) == 593 || LODWORD(v388[1]) == 594 || LODWORD(v388[1]) == 595 )
                goto LABEL_210;
              v52 = LODWORD(v388[1]) - 744;
              v51 = LODWORD(v388[1]) == 744;
              goto LABEL_124;
            }
            if ( LODWORD(v388[1]) != 750 && LODWORD(v388[1]) != 751 && LODWORD(v388[1]) != 752 )
            {
              v52 = LODWORD(v388[1]) - 753;
              v51 = LODWORD(v388[1]) == 753;
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
            if ( v331 || a5 != -1 )
            {
              if ( v331 <= a5 )
              {
                if ( LODWORD(v388[1]) >= v353 && LODWORD(v388[1]) <= v354 )
                  goto LABEL_883;
                v315 = 0;
              }
              else
              {
                if ( LODWORD(v388[1]) >= v354 && LODWORD(v388[1]) <= v353 )
                  goto LABEL_75;
                v315 = 1;
              }
              if ( !v315 )
                goto LABEL_75;
            }
LABEL_883:
            if ( !(unsigned int)IsInsideMenuLoop(a1) )
            {
              if ( *(_DWORD *)v320 )
                xxxSkipSysMsgEx(v316, (struct tagQMSG *)&v387, 1);
              if ( !*(_QWORD *)&v320[4] )
                *(_QWORD *)&v320[4] = *(_QWORD *)(*(_QWORD *)(a1 + 464) + 120LL);
              v326 = v389[0];
              v325 = (void *)v389[1];
              InteractiveControlInputMessage = xxxRetrieveInteractiveControlInputMessage(
                                                 LOWORD(v389[0]),
                                                 WORD1(v389[0]));
              if ( InteractiveControlInputMessage == 1 )
                goto LABEL_198;
              if ( InteractiveControlInputMessage == 2 )
                goto LABEL_75;
            }
            goto LABEL_51;
          }
          if ( LODWORD(v388[1]) == 586 )
            goto LABEL_210;
          if ( LODWORD(v388[1]) > 0x11B )
            break;
          switch ( LODWORD(v388[1]) )
          {
            case 0x11B:
              goto LABEL_106;
            case 0x23:
              v326 = 0;
              v325 = (void *)v389[1];
              if ( !*(_QWORD *)&v320[4] || (v269 = *(_QWORD *)(*(_QWORD *)&v320[4] + 16LL), v269 == a1) )
              {
                if ( (unsigned int)MiPCheckMsgFilter(NextSysMsg, v319, v331, a5) )
                {
LABEL_736:
                  if ( *(_DWORD *)v320 )
                    xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v387, 1);
                  goto LABEL_198;
                }
              }
              else
              {
                if ( *(struct tagQ **)(v269 + 464) != *v11 )
                  goto LABEL_51;
                if ( !v342 )
                {
                  v342 = *(_QWORD *)(*(_QWORD *)&v320[4] + 16LL);
                  v270 = (Win32RawLockedW32Thread *)v378;
                  goto LABEL_734;
                }
              }
LABEL_75:
              v9 = 1;
              goto LABEL_76;
            case 0xFE:
LABEL_110:
              v326 = v389[0];
              v325 = (void *)v389[1];
              if ( !*(_QWORD *)&v320[4] )
                goto LABEL_51;
              if ( CheckCrossThreadInput(*(struct tagWND *const *)&v320[4], NextSysMsg, &v328, (int *)v320, v341) )
                goto LABEL_75;
              if ( v328 )
                goto LABEL_51;
              if ( !v331 && a5 == -1 )
              {
LABEL_749:
                v271 = CheckPwndFilter(*(_QWORD *)&v320[4], v345);
                LOBYTE(i) = v322;
                if ( v271 )
                  goto LABEL_736;
              }
              else
              {
                if ( v331 <= a5 )
                {
                  if ( v319 >= v331 && v319 <= a5 )
                    goto LABEL_749;
                  v50 = 0;
                  goto LABEL_748;
                }
                if ( v319 < a5 || (LOBYTE(i) = v322, v319 > v331) )
                {
                  v50 = 1;
LABEL_748:
                  LOBYTE(i) = v322;
                  if ( v50 )
                    goto LABEL_749;
                }
              }
              break;
            case 0xFF:
              v326 = v389[0];
              v325 = (void *)v389[1];
              if ( !DeleteHidDataIfAlreadyHandledByGRIB((struct tagTHREADINFO *)a1, v389[1]) )
              {
                *(_QWORD *)&v320[4] = 0;
                v30 = 0;
                if ( v325 )
                {
                  LOBYTE(v30) = 18;
                  v31 = HMValidateHandleNoSecure(v325, v30);
                  v30 = v31;
                  if ( v31 )
                    *(_QWORD *)&v320[4] = *(_QWORD *)(v31 + 24);
                }
                if ( !*(_QWORD *)&v320[4] )
                {
                  v32 = *v11;
                  *(_QWORD *)&v320[4] = *((_QWORD *)*v11 + 15);
                  if ( !*(_QWORD *)&v320[4] )
                  {
                    *(_QWORD *)&v320[4] = *((_QWORD *)v32 + 16);
                    if ( !*(_QWORD *)&v320[4] )
                    {
                      InputTraceLogging::RawInput::SSQResult(v325, 0);
                      goto LABEL_51;
                    }
                  }
                }
                if ( v30 && *(_QWORD *)(v30 + 16) != *(_QWORD *)(*(_QWORD *)&v320[4] + 16LL) )
                {
                  v351 = 0x20000;
                  MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 10065);
                }
                Win32HM_ExchangeThreadLock<1>(*(_QWORD *)&v320[4], v359);
                if ( CheckCrossThreadInput(*(struct tagWND *const *)&v320[4], NextSysMsg, &v328, (int *)v320, v341) )
                {
                  v266 = 0;
                  goto LABEL_713;
                }
                if ( !v328 )
                  goto LABEL_241;
                if ( *(struct tagQ **)(*(_QWORD *)(*(_QWORD *)&v320[4] + 16LL) + 464LL) != *v11 )
                  goto LABEL_51;
                if ( (unsigned int)IsInsideMenuLoop(a1) )
                {
                  v267 = *(HWND **)(**(_QWORD **)(a1 + 640) + 8LL);
                }
                else
                {
                  v268 = *(_QWORD *)(a1 + 704);
                  if ( v268 )
                    v267 = *(HWND **)(v268 + 16);
                  else
                    v267 = 0;
                }
                if ( v267 )
                  InputTraceLogging::RawInput::IgnoreModalLoop(v325, *v267);
                if ( !v349 )
                {
                  v349 = *(struct _W32THREAD **)(*(_QWORD *)&v320[4] + 16LL);
                  Win32RawLockedW32Thread::Exchange((Win32RawLockedW32Thread *)v382, v349);
                }
LABEL_241:
                if ( !v331 && a5 == -1 )
                  goto LABEL_243;
                if ( v331 > a5 )
                {
                  if ( v319 >= a5 && v319 <= v331 )
                    goto LABEL_302;
                  v128 = 1;
                }
                else
                {
                  if ( v319 >= v331 && v319 <= a5 )
                  {
LABEL_243:
                    if ( (unsigned int)CheckPwndFilter(*(_QWORD *)&v320[4], v345) )
                    {
                      if ( !v328 )
                      {
                        if ( *(_DWORD *)v320 )
                          xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v387, 1);
                        InputTraceLogging::RawInput::SSQResult(v325, 4);
                        goto LABEL_198;
                      }
                      v266 = 3;
LABEL_713:
                      InputTraceLogging::RawInput::SSQResult(v325, v266);
                      goto LABEL_76;
                    }
LABEL_302:
                    InputTraceLogging::RawInput::SSQResult(v325, 2);
                    goto LABEL_23;
                  }
                  v128 = 0;
                }
                if ( !v128 )
                  goto LABEL_302;
                goto LABEL_243;
              }
LABEL_51:
              v33 = v321;
              goto LABEL_52;
            case 0x100:
              goto LABEL_350;
            case 0x101:
LABEL_355:
              v326 = LOBYTE(v389[0]);
              v142 = v389[0];
              if ( LOBYTE(v389[0]) == 231 )
                v142 = 231;
              v389[0] = v142;
              if ( !*(_DWORD *)v320 || (WORD2(v393) & 0x8000) == 0 )
              {
                if ( *(_DWORD *)(W32GetUserSessionState(v142, v28, v24, v25) + 14224) )
                {
                  if ( (GetAppImeCompatFlags(0) & 0x800000) == 0 && BYTE2(v389[1]) == 41 )
                  {
                    if ( *(_DWORD *)v320 )
                    {
                      v256 = *v11;
                      if ( (*((_BYTE *)*v11 + 356) & 0x15) == 0
                        && (*((_BYTE *)v256 + 374) & 0x40) == 0
                        && (*((_BYTE *)v256 + 375) & 1) == 0 )
                      {
                        v257 = *((_QWORD *)v256 + 15);
                        *(_QWORD *)&v320[4] = v257;
                        if ( !v257 )
                        {
                          v257 = *((_QWORD *)v256 + 16);
                          *(_QWORD *)&v320[4] = v257;
                        }
                        if ( !v257 || *(_QWORD *)(v257 + 16) == a1 )
                        {
                          xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v387, 1);
                          if ( !v346 && *(_QWORD *)&v320[4] )
                          {
                            *(_QWORD *)&v401[0] = **(_QWORD **)&v320[4];
                            *((_QWORD *)&v401[0] + 1) = 80;
                            memset(&v401[1], 0, 32);
                            xxxCallCtfHook(3, 0, 1, v401);
                          }
                          goto LABEL_14;
                        }
                      }
                    }
                  }
                }
              }
              if ( v326 == 121 )
                v319 |= 4u;
              if ( (*((_BYTE *)*v11 + 356) & 4) != 0 && v326 == 27 )
                v319 |= 4u;
              if ( (_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 520), 0, 0) & 8) == 0 )
                v389[1] &= ~0x2000000uLL;
LABEL_364:
              v326 = LOBYTE(v389[0]);
              v143 = *v11;
              v144 = *((_QWORD *)*v11 + 15);
              *(_QWORD *)&v320[4] = v144;
              if ( !*((_QWORD *)v143 + 15) )
              {
                v144 = *((_QWORD *)v143 + 16);
                *(_QWORD *)&v320[4] = v144;
                if ( !v144 )
                  goto LABEL_51;
                if ( v319 - 256 <= 3 )
                  v319 += 4;
              }
              Win32HM_ExchangeThreadLock<1>(v144, v359);
              v145 = *(_QWORD *)(*(_QWORD *)&v320[4] + 16LL);
              v328 = v145 != v366;
              if ( v145 != v360 )
              {
                if ( *(struct tagQ **)(*(_QWORD *)(*(_QWORD *)&v320[4] + 16LL) + 464LL) != *v11 )
                  goto LABEL_51;
                if ( (unsigned int)IsInsideMenuLoop(a1) )
                {
                  v258 = *(_QWORD *)(**(_QWORD **)(a1 + 640) + 8LL);
                }
                else
                {
                  v259 = *(_QWORD *)(a1 + 704);
                  if ( v259 )
                    v258 = *(_QWORD *)(v259 + 16);
                  else
                    v258 = 0;
                }
                if ( v258 )
                {
                  *(_QWORD *)&v320[4] = v258;
                  v328 = *(_QWORD *)(v258 + 16) != v377;
                  Win32HM_ExchangeThreadLock<1>(v258, v359);
                }
                if ( !v356 )
                {
                  v356 = *(struct _W32THREAD **)(*(_QWORD *)&v320[4] + 16LL);
                  Win32RawLockedW32Thread::Exchange((Win32RawLockedW32Thread *)v379, v356);
                }
              }
              if ( v331 || a5 != -1 )
              {
                if ( v331 > a5 )
                {
                  if ( v319 < a5 || (LOBYTE(i) = v322, v319 > v331) )
                  {
                    v196 = 1;
                    goto LABEL_513;
                  }
                }
                else
                {
                  if ( v319 >= v331 && v319 <= a5 )
                    goto LABEL_368;
                  v196 = 0;
LABEL_513:
                  LOBYTE(i) = v322;
                  if ( v196 )
                    goto LABEL_368;
                }
              }
              else
              {
LABEL_368:
                v146 = CheckPwndFilter(*(_QWORD *)&v320[4], v345);
                LOBYTE(i) = v322;
                if ( v146 )
                {
                  if ( v328 )
                    goto LABEL_75;
                  if ( *(_DWORD *)v320 )
                  {
                    if ( (WORD2(v393) & 0x8000) != 0 )
                      goto LABEL_403;
                    if ( !(unsigned int)IsInsideMenuLoop(a1) )
                    {
                      if ( v326 == 93 && v319 == 257 )
                      {
                        if ( *(_QWORD *)&v320[4] )
                          v231 = **(_QWORD **)&v320[4];
                        else
                          LODWORD(v231) = 0;
                        PostTransformableMessage(*(_DWORD *)&v320[4], 123, v231, -1, 0);
                      }
                      if ( v326 == 112 && v319 == 256 )
                        PostMessage(*(_QWORD *)&v320[4], 77, 0, 0);
                    }
                  }
                  if ( v326 == 16 && !v346 )
                  {
                    v260 = v389[1] & 0x1000000;
                    if ( ((unsigned __int8)(v260 != 0 ? 1 : 4) & *((_BYTE *)*v329 + 392)) != 0 )
                    {
                      if ( (unsigned int)IsDesktopApp(*(_QWORD *)(a1 + 456))
                        && (_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 520), 0, 0) & 8) == 0 )
                      {
                        v389[0] = (v260 != 0) + 160LL;
LABEL_681:
                        xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v387, 1);
                        goto LABEL_846;
                      }
                      v11 = v329;
                    }
                    else
                    {
                      v11 = v329;
                    }
                  }
                  v350 = *((unsigned __int8 *)*v11 + ((unsigned __int64)(unsigned __int8)v326 >> 2) + 352)
                       & (1 << (2 * (v326 & 3)));
                  if ( !v350 )
                    goto LABEL_403;
                  if ( *(_DWORD *)v320 )
                  {
                    if ( NextSysMsg )
                      *((_QWORD *)NextSysMsg + 5) |= 0x40000000uLL;
LABEL_403:
                    if ( *(_DWORD *)v320 )
                    {
                      if ( (WORD2(v393) & 0x8000) == 0 && NextSysMsg && (*(_DWORD *)(a1 + 1360) & 0x10000000) != 0 )
                        v344 = (ULONG_PTR)xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v387, 0);
                      else
                        xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v387, 1);
                    }
                  }
                  v325 = (void *)v389[1];
                  v326 = v389[0];
                  if ( v350 )
                    v325 = (void *)(v389[1] | 0x40000000);
                  if ( v319 == 257 || v319 == 261 )
                    v325 = (void *)((unsigned __int64)v325 | 0x80000000);
                  if ( (*((_BYTE *)*v11 + 356) & 0x10) != 0 )
                    v325 = (void *)((unsigned __int64)v325 | 0x20000000);
                  if ( (unsigned int)IsMenuStarted(a1) )
                    v325 = (void *)((unsigned __int64)v325 | 0x10000000);
                  if ( (*(_DWORD *)(v158 + 508) & 0x4000) != 0 )
                    v325 = (void *)((unsigned __int64)v325 | 0x8000000);
                  if ( !v21 && !*(_QWORD *)(W32GetUserSessionState(v159, v158, v160, v161) + 12888)
                    || (WORD2(v393) & 0x8000) != 0 )
                  {
                    goto LABEL_416;
                  }
                  if ( !*(_DWORD *)v320 )
                  {
LABEL_417:
                    LOBYTE(v162) = v336;
                    goto LABEL_418;
                  }
                  if ( (unsigned int)IsMenuStarted(a1)
                    || (_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 520), 0, 0) & 0x2000000) != 0
                    || !*(_QWORD *)&v320[4] )
                  {
LABEL_416:
                    if ( !*(_DWORD *)v320 )
                      goto LABEL_417;
                    v162 = v336;
                    if ( (WORD2(v393) & 0x8000) != 0 )
                    {
                      if ( (DWORD1(v393) & 0x4000000) != 0 )
                        v162 = 2;
                      v336 = v162;
                      v337 = v162;
                    }
                  }
                  else
                  {
                    v208 = v326;
                    if ( v326 == 231 )
                      v208 = ((unsigned __int64)*(unsigned __int16 *)(a1 + 914) << 16) | 0xE7;
                    tagTHREADINFO::UpdateInputSource(
                      (tagTHREADINFO *)a1,
                      (const struct tagINPUT_MESSAGE_SOURCE *)((char *)&v394 + 12));
                    tagTLBLOCK::_unnamed_type_list_::_unnamed_type_list_((tagTLBLOCK::_unnamed_type_list_ *)BugCheckParameter2);
                    v209 = v344;
                    if ( v344 )
                      Win32RawLockedItemBase<tagQMSG,0,1,1,1>::ManualLock<void>((ULONG_PTR)BugCheckParameter2, v344);
                    v210 = v208;
                    v11 = v329;
                    v211 = xxxImmProcessKey(*v329, *(struct tagWND **)&v320[4], v319, v210, (__int64)v325);
                    LOBYTE(v162) = v211;
                    v336 = v211;
                    v337 = v211;
                    if ( (v211 & 0x11) != 0 )
                    {
                      if ( v209 )
                      {
                        Win32RawLockedItemBase<tagQMSG,0,1,1,1>::UnlockWorker((ULONG_PTR)BugCheckParameter2);
                        v344 = 0;
                      }
                      Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
                      goto LABEL_51;
                    }
                    if ( v209 )
                      Win32RawLockedItemBase<tagQMSG,0,1,1,1>::UnlockWorker((ULONG_PTR)BugCheckParameter2);
                    Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
                  }
LABEL_418:
                  if ( !*(_DWORD *)v320 )
                    goto LABEL_432;
                  v321 = 1;
                  v163 = 0;
                  if ( (WORD2(v393) & 0x8000) == 0 )
                  {
                    v164 = *((_QWORD *)*v11 + 65);
                    *((_QWORD *)*v11 + 65) = *((_QWORD *)&v391 + 1);
                    v165 = v162 & 2;
                    tagTHREADINFO::UpdateInputSource(
                      (tagTHREADINFO *)a1,
                      (const struct tagINPUT_MESSAGE_SOURCE *)((char *)&v394 + 12));
                    *(_QWORD *)&v401[0] = 0;
                    v401[1] = 0;
                    *((_QWORD *)&v401[0] + 1) = v325;
                    *(_QWORD *)&v348 = (unsigned int)Feature_WebThreatDefenseToggle__private_featureState;
                    if ( (Feature_WebThreatDefenseToggle__private_featureState & 0x10) == 0 )
                    {
                      LODWORD(v348) = Feature_WebThreatDefenseToggle__private_featureState | 1;
                      wil_details_FeatureReporting_ReportUsageToService(
                        Feature_WebThreatDefenseToggle__private_descriptor,
                        v348,
                        3,
                        1);
                      wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
                        v348,
                        3,
                        Feature_WebThreatDefenseToggle__private_descriptor);
                    }
                    v168 = *(_QWORD *)(a1 + 1376);
                    v169 = *(_QWORD *)(a1 + 456);
                    v170 = *(unsigned int *)(v169 + 276);
                    if ( (v170 & 4) != 0
                      && (_DWORD)v168 == 1
                      && (v168 & 0x500000000LL) != 0
                      && *(_QWORD *)(a1 + 488) != *(_QWORD *)(W32GetUserSessionState(v169, v170, v166, v167) + 62744)
                      && CheckImEnabled() )
                    {
                      LOWORD(v401[1]) = 1;
                    }
                    tagTLBLOCK::_unnamed_type_list_::_unnamed_type_list_((tagTLBLOCK::_unnamed_type_list_ *)BugCheckParameter2);
                    v171 = v344;
                    if ( v344 )
                      Win32RawLockedItemBase<tagQMSG,0,1,1,1>::ManualLock<void>((ULONG_PTR)BugCheckParameter2, v344);
                    v163 = xxxCallCtfHook(2, v165, v326, v401);
                    if ( (BYTE2(v401[1]) & 1) != 0 )
                    {
                      if ( (*(_BYTE *)(*(_QWORD *)(a1 + 456) + 808LL) & 0x30) == 0x10 )
                        WORD1(v401[1]) |= 0x10u;
                      ProcessTranslatedChar((struct _CHARHOOKSTRUCT *)v401);
                    }
                    v11 = v329;
                    *((_QWORD *)*v329 + 65) = v164;
                    if ( !v171 )
                      goto LABEL_430;
                    if ( (unsigned int)(v163 - 2) > 1
                      || (*(_DWORD *)(a1 + 1360) & 0x20000000) != 0
                      || !AllocQEntryEx((char *)*v11 + 24, v171, 2) )
                    {
                      v344 = 0;
LABEL_430:
                      Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
                      NextSysMsg = v340;
                      goto LABEL_431;
                    }
                    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
                      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20000) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u )
                    {
                      v9 = 0;
                    }
                    if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
                      || (v224 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
                    {
                      v224 = 0;
                    }
                    if ( v9 || v224 )
                    {
                      v261 = *v11;
                      v262 = *((_QWORD *)*v11 + 11);
                      v263 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v222, v223);
                      LOBYTE(v264) = v224;
                      LOBYTE(v265) = v9;
                      WPP_RECORDER_AND_TRACE_SF_qqq(
                        *((_QWORD *)WPP_GLOBAL_Control + 3),
                        v265,
                        v264,
                        *(_QWORD *)(v263 + 69152),
                        5,
                        18,
                        35,
                        (__int64)WPP_b198703289513b726a6724fd49b6e756_Traceguids,
                        v344,
                        (char)v261,
                        v262);
                      v11 = v329;
                    }
                    if ( v358 == -1 )
                    {
                      BugCheckParameter4 = PtiCurrent();
                      KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)BugCheckParameter2, 0, (ULONG_PTR)BugCheckParameter4);
                    }
                    *((_QWORD *)PtiCurrent() + 47) = BugCheckParameter2[0];
                    v358 = -1;
                    *((_QWORD *)*v11 + 11) = v344;
                    v9 = 1;
                    if ( v163 == 2 )
                    {
                      v225 = 1;
                      v330 = 1;
                    }
                    else
                    {
                      v225 = v330;
                      if ( v163 == 3 )
                        v225 = 2;
                      v330 = v225;
                    }
                    DeferSysPeekMsg(a1, v225);
                    v344 = 0;
                    Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
                    goto LABEL_23;
                  }
LABEL_431:
                  if ( v163 )
                  {
                    v33 = 1;
                    goto LABEL_52;
                  }
LABEL_432:
                  if ( ((*(_BYTE *)(a1 + 712) | *(_BYTE *)(**(_QWORD **)(a1 + 496) + 16LL)) & 8) == 0 )
                  {
                    v33 = v321;
LABEL_434:
                    if ( v33
                      && *(_DWORD *)v320
                      && ((*(_BYTE *)(a1 + 712) | *(_BYTE *)(**(_QWORD **)(a1 + 496) + 16LL)) & 0x40) != 0 )
                    {
                      xxxCallHook(7, v326, (__int64)v325, 5);
                    }
                    goto LABEL_198;
                  }
                  v33 = 1;
                  v321 = 1;
                  if ( !(unsigned int)xxxCallHook(*(_DWORD *)v320 == 0 ? 3 : 0, v326, (__int64)v325, 2) )
                    goto LABEL_434;
LABEL_52:
                  xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v387, 1);
                  if ( v335 )
                  {
                    if ( ((*(_BYTE *)(a1 + 712) | *(_BYTE *)(**(_QWORD **)(a1 + 496) + 16LL)) & 0x40) != 0 )
                      xxxCallHook(6, v319, (__int64)v398, 5);
                    v335 = 0;
                  }
                  if ( v33 )
                  {
                    if ( ((*(_BYTE *)(a1 + 712) | *(_BYTE *)(**(_QWORD **)(a1 + 496) + 16LL)) & 0x40) != 0 )
                      xxxCallHook(7, v326, (__int64)v325, 5);
                    v321 = 0;
                  }
                  v18 = FLOAT_1_0;
                  v11 = v329;
                  LOBYTE(i) = v322;
                  if ( *(_DWORD *)v320 )
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
              v346 = 1;
              v326 = LOBYTE(v389[0]);
              if ( *(_DWORD *)v320 && (WORD2(v393) & 0x8000) != 0 )
              {
LABEL_353:
                if ( v326 == 231 )
                {
                  *(_WORD *)(a1 + 914) = WORD1(v389[0]);
                  v389[0] = 231;
                }
                goto LABEL_355;
              }
              if ( LOBYTE(v389[0]) != 18 )
                *((_DWORD *)*v11 + 127) &= 0xFFFFFFF3;
              if ( v326 != 44 )
              {
LABEL_527:
                if ( *(_DWORD *)(W32GetUserSessionState(i, v28, v24, v25) + 16256)
                  && (!*(_DWORD *)(W32GetUserSessionState(v198, v28, v24, v25) + 14652)
                   || (*(_BYTE *)(W32GetUserSessionState(v200, v199, v201, v202) + 14648) & 2) == 0) )
                {
                  v203 = *((_BYTE *)*v11 + 356);
                  v204 = v326 | 0x400;
                  if ( (v203 & 0x10) == 0 )
                    v204 = v326;
                  v205 = v204 | 0x200;
                  if ( (v203 & 4) == 0 )
                    v205 = v204;
                  v206 = v205;
                  LODWORD(v206) = v205 | 0x100;
                  if ( (v203 & 1) == 0 )
                    v206 = v205;
                  v207 = (_QWORD *)HotKeyToWindow(v206);
                  v25 = v207;
                  if ( v207 )
                  {
                    if ( *(_QWORD *)(a1 + 488) == *(_QWORD *)(v207[2] + 488LL) )
                    {
                      PostTransformableMessage(*((_QWORD *)*v11 + 16), 274, 61776, *v207, 0);
                      xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v387, 1);
                      goto LABEL_14;
                    }
                  }
                }
                goto LABEL_353;
              }
              i = 16;
              v253 = *((_BYTE *)*v11 + 356) & 0x10;
              if ( (!v253 || (*(_DWORD *)(a1 + 916) & 0x10) != 0) && (v253 || (*(_DWORD *)(a1 + 916) & 0x20) != 0) )
              {
                v11 = v329;
                goto LABEL_527;
              }
              xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v387, 1);
              if ( v253 || (v389[1] & 0xFF0000) == 0x10000 )
              {
                v11 = v329;
                if ( !*((_QWORD *)*v329 + 16) )
                  goto LABEL_14;
                CompositeAppFrameWindowOrSelf = CoreWindowProp::GetCompositeAppFrameWindowOrSelf(*((const struct tagWND **)*v329
                                                                                                 + 16));
              }
              else
              {
                CompositeAppFrameWindowOrSelf = *(struct tagWND **)(*(_QWORD *)(*(_QWORD *)(a1 + 488) + 8LL) + 24LL);
                v11 = v329;
              }
              if ( CompositeAppFrameWindowOrSelf )
              {
                v255 = v395 != 1;
                Win32HMThreadLockAlways<tagHOOK>::Win32HMThreadLockAlways<tagHOOK>(
                  v383,
                  a1,
                  CompositeAppFrameWindowOrSelf);
                xxxSnapWindow(CompositeAppFrameWindowOrSelf, v255);
                Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)v383);
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
        if ( LODWORD(v388[1]) != 522 && LODWORD(v388[1]) != 526 )
          break;
        if ( (_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 520), 0, 0) & 0x400) != 0
          && (int)CheckProcessForeground((struct tagTHREADINFO *)a1) < 0 )
        {
          goto LABEL_75;
        }
        if ( (unsigned int)IsInsideMenuLoop(a1) )
          goto LABEL_51;
        if ( (DWORD1(v393) & 0x100000) != 0 )
        {
          v172 = *((_QWORD *)*v11 + 15);
          *(_QWORD *)&v320[4] = v172;
        }
        else
        {
          if ( *(_QWORD *)&v320[4] && IsCompositionInputWindowForHitTest(*(struct tagWND **)&v320[4]) )
          {
            v213 = 1;
            if ( (unsigned int)CoreWindowProp::IsCompositeAppOrSelfDisabled(*(const struct tagWND **)&v320[4]) )
              goto LABEL_51;
            ThreadDesktopWindow = *(_QWORD *)&v320[4];
          }
          else
          {
            ThreadDesktopWindow = GetThreadDesktopWindow(0);
            *(_QWORD *)&v320[4] = ThreadDesktopWindow;
            v213 = 0;
          }
          Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(v384, ThreadDesktopWindow);
          v214 = xxxDCEWindowHitTest(*(_QWORD *)&v320[4], 512, v389[0], v389[1], *(_QWORD *)v392, &v327, 4 * v213 + 9);
          LOBYTE(v215) = 1;
          *(_QWORD *)&v320[4] = HMValidateHandleNoSecure(v214, v215);
          LOBYTE(v216) = 1;
          v217 = (struct tagWND *)HMValidateHandleNoSecure(v214, v216);
          InputTraceLogging::Mouse::SecondaryHitTest((const struct tagQMSG *)&v387, v392, v217);
          Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)v384);
          v172 = *(_QWORD *)&v320[4];
          v11 = v329;
        }
        if ( !v172 )
          goto LABEL_51;
        Win32HM_ExchangeThreadLock<1>(v172, v359);
        v173 = *(_QWORD *)(*(_QWORD *)&v320[4] + 16LL);
        v328 = v173 != v366;
        if ( v173 != v360 )
        {
          v195 = *(_QWORD *)(*(_QWORD *)&v320[4] + 16LL);
          if ( *(struct tagQ **)(v195 + 464) != *v11 )
            goto LABEL_51;
          if ( !v356 )
          {
            v356 = *(struct _W32THREAD **)(*(_QWORD *)&v320[4] + 16LL);
            Win32RawLockedW32Thread::Exchange((Win32RawLockedW32Thread *)v379, (struct _W32THREAD *)v195);
          }
        }
        v100 = v331;
        v174 = MiPCheckMsgFilter(NextSysMsg, v319, v331, a5);
        LOBYTE(i) = v322;
        if ( v174 )
        {
          v175 = *(struct tagWND **)&v320[4];
          v176 = CheckPwndFilter(*(_QWORD *)&v320[4], v345);
          LOBYTE(i) = v322;
          if ( v176 )
          {
            if ( v328 )
              goto LABEL_75;
            if ( NextSysMsg && (unsigned int)IsMiPActive(a1, NextSysMsg) )
            {
              if ( _bittest((const signed __int32 *)NextSysMsg + 25, 0xAu) )
              {
                memset_0(v401, 0, 0xA8u);
                if ( ShouldGenerateMipMessage((struct tagTHREADINFO *)a1, NextSysMsg, v175, *(int *)v320)
                  && GeneratePointerMessageFromMouse((struct tagQMSG *)v401, v319, NextSysMsg, v175, v272) )
                {
                  v387 = v401[0];
                  *(_OWORD *)v388 = v401[1];
                  *(_OWORD *)v389 = v401[2];
                  v390 = v402;
                  v391 = v403;
                  *(_OWORD *)&v392[0].x = v404;
                  v393 = v405;
                  v394 = v406;
                  v395 = v407;
                  v396 = v408;
                  v397 = v409;
                  v29 = 1;
                  v338 = 1;
                  if ( *(_DWORD *)v320 )
                    *((_DWORD *)NextSysMsg + 25) &= ~0x400u;
                  goto LABEL_211;
                }
                if ( !*(_DWORD *)v320 )
                  goto LABEL_452;
                *((_DWORD *)NextSysMsg + 25) &= ~0x400u;
              }
              else
              {
                if ( !*(_DWORD *)v320 )
                {
LABEL_452:
                  MouseKeyFlags = GetMouseKeyFlags(*(_QWORD *)(a1 + 464));
                  v326 = v389[0] | MouseKeyFlags;
                  v325 = (void *)v389[1];
                  v324.x = SLOWORD(v389[1]);
                  v324.y = SWORD1(v389[1]);
                  PhysicalToLogicalDPIPointWithHitTest(&v324, &v324, 0, *(const struct tagWND **)&v320[4]);
                  v325 = (void *)((LOWORD(v324.y) << 16) | LOWORD(v324.x));
                  *(struct tagPOINT *)((char *)&v390 + 4) = v324;
                  v398[0] = (__int64)v324;
                  if ( *(_QWORD *)&v320[4] )
                    v398[1] = **(_QWORD **)&v320[4];
                  else
                    v398[1] = 0;
                  LODWORD(v399) = 0;
                  *((_QWORD *)&v399 + 1) = *((_QWORD *)&v391 + 1);
                  LODWORD(v400) = v389[0];
                  if ( *(_DWORD *)v320 )
                  {
                    v335 = 1;
                    if ( (unsigned int)xxxCallCtfHook(7, 0, v319, v398) )
                      goto LABEL_51;
                  }
                  if ( ((*(_DWORD *)(a1 + 712) | *(_DWORD *)(**(_QWORD **)(a1 + 496) + 16LL)) & 0x100) != 0 )
                  {
                    v335 = 1;
                    if ( (unsigned int)xxxCallMouseHook(v319, v398, *(unsigned int *)v320) )
                      goto LABEL_51;
                  }
                  if ( (unsigned int)PsGetWin32KFilterSet() == 5 )
                  {
                    v275 = *((_QWORD *)PtiCurrent() + 64);
                    v332 = 0;
                    v332 = *(_QWORD *)(v275 + 248) != 0;
                    if ( v332 )
                    {
                      if ( xxxClientCallLocalMouseHooks(v319, v398, *(unsigned int *)v320) )
                        goto LABEL_51;
                    }
                  }
                  if ( v335
                    && *(_DWORD *)v320
                    && ((*(_BYTE *)(a1 + 712) | *(_BYTE *)(**(_QWORD **)(a1 + 496) + 16LL)) & 0x40) != 0 )
                  {
                    xxxCallHook(6, v319, (__int64)v398, 5);
                  }
LABEL_198:
                  if ( *(_QWORD *)(a1 + 788) != *(_QWORD *)((char *)&v390 + 4) )
                    _InterlockedOr((volatile signed __int32 *)(a1 + 520), 0x100000u);
                  if ( NextSysMsg && ((BYTE4(v393) & 0x20) != 0 || (DWORD1(v393) & 0x8000000) != 0) )
                  {
                    if ( *((_DWORD *)NextSysMsg + 6) == 512 )
                    {
                      if ( *(_QWORD *)&v320[4] )
                        v131 = **(_QWORD **)&v320[4];
                      else
                        v131 = 0;
                      *((_QWORD *)NextSysMsg + 2) = v131;
                      *((_DWORD *)NextSysMsg + 25) |= 0x200u;
                    }
                    *((_QWORD *)NextSysMsg + 8) = v325;
                  }
                  *(_DWORD *)(a1 + 788) = DWORD1(v390);
                  v94 = v363;
                  *(_DWORD *)(v363 + 792) = DWORD2(v390);
                  *(_DWORD *)(v94 + 796) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)&v320[4] + 40LL) + 288LL);
                  *(struct tagPOINT *)(a1 + 800) = v392[0];
                  *(_DWORD *)(a1 + 600) = v390;
                  *(_QWORD *)(*(_QWORD *)(a1 + 464) + 520LL) = *((_QWORD *)&v391 + 1);
                  if ( v319 == 514 || v319 == 162 )
                    *(struct tagPOINT *)(a1 + 808) = v392[0];
                  *(_QWORD *)(*(_QWORD *)(a1 + 464) + 80LL) = 1;
                  *(_QWORD *)(a1 + 608) = 1;
                  tagTHREADINFO::UpdateLastInputData((tagTHREADINFO *)a1, (const struct tagQMSG *)&v387);
                  **(_DWORD **)(a1 + 480) &= ~8u;
                  **(_QWORD **)(a1 + 512) &= 0x7FFFFFFFuLL;
                  v95 = v336;
                  v96 = v364;
                  if ( *(_DWORD *)v320 )
                  {
                    v119 = *(_QWORD **)(a1 + 512);
                    if ( (BYTE4(v393) & 1) != 0 )
                      *v119 |= 0x1000uLL;
                    else
                      *v119 &= ~0x1000uLL;
                  }
                  TransferWakeBit(a1, v319);
                  v97 = *(_QWORD *)(a1 + 464);
                  if ( !*(_DWORD *)(v97 + 40) )
                    _InterlockedAnd(
                      (volatile signed __int32 *)(*(_QWORD *)(a1 + 480) + 8LL),
                      (*(_DWORD *)(v97 + 508) >> 4) & 2 | 0xFFFF83F8);
                  v98 = *(_DWORD *)v320;
                  if ( *(_DWORD *)v320 )
                  {
                    if ( v338 )
                    {
                      v117 = *(_DWORD **)(a1 + 1512);
                      if ( v117 )
                      {
                        if ( (*v117 & 1) != 0 && (*v117 & 4) != 0 )
                        {
                          SetMiPWakeBit((struct tagTHREADINFO *)a1);
                          v98 = *(_DWORD *)v320;
                        }
                      }
                    }
                  }
                  v99 = 0;
                  if ( *(_QWORD *)&v320[4] )
                    v99 = **(_QWORD **)&v320[4];
                  *(_QWORD *)v375 = v99;
                  *((_DWORD *)v96 + 2) = v319;
                  v47 = v326;
                  if ( (v95 & 2) != 0 )
                    v47 = 229;
                  *((_QWORD *)v96 + 2) = v47;
                  *((_QWORD *)v96 + 3) = v325;
                  *((_DWORD *)v96 + 8) = v390;
                  *(_QWORD *)((char *)v96 + 36) = *(_QWORD *)((char *)&v390 + 4);
                  InputTraceLogging::Delivery::ScanSysQueue(
                    (const struct tagQMSG *)&v387,
                    v96,
                    (const struct tagTHREADINFO *)a1,
                    v98 != 0);
                  if ( *(_DWORD *)v320 )
                  {
                    EtwTraceInputProcessDelay(a1);
                    *(_DWORD *)(*(_QWORD *)(a1 + 464) + 528LL) = (MEMORY[0xFFFFF78000000320]
                                                                * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
                  }
                  EtwTraceRetrieveInputMessage(v96);
                  if ( v334[0] )
                  {
                    v48 = PtiCurrent();
                    *((_QWORD *)v48 + 170) &= ~0x1000000000uLL;
                  }
                  Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)v359);
                  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v381);
                  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v382);
                  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v380);
                  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v378);
                  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v379);
                  return 1;
                }
                if ( (unsigned int)IsMiPMouseMessage(*((unsigned int *)NextSysMsg + 6)) )
                {
                  if ( (unsigned int)IsGenuineMouseInput((char *)NextSysMsg + 124) )
                  {
                    v273 = *(_DWORD **)(a1 + 1512);
                    if ( v273 )
                    {
                      if ( (*v273 & 2) == 0 && (*v273 & 4) == 0 )
                        goto LABEL_681;
                    }
                  }
                  v274 = *(_DWORD **)(a1 + 1512);
                  if ( v274 )
                    *v274 &= ~2u;
                }
              }
            }
            if ( *(_DWORD *)v320 )
              xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v387, 1);
            goto LABEL_452;
          }
          v11 = v329;
        }
      }
      switch ( LODWORD(v388[1]) )
      {
        case 0x238:
          goto LABEL_110;
        case 0x240:
LABEL_106:
          if ( !*(_QWORD *)&v320[4] )
            goto LABEL_51;
          v49 = *(char **)(*(_QWORD *)&v320[4] + 40LL);
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
      v324.x = SLOWORD(v389[1]);
      v324.y = SWORD1(v389[1]);
      v327 = 1;
      if ( (BYTE4(v393) & 0x20) == 0 && (DWORD1(v393) & 0x8000000) == 0
        || !*(_QWORD *)&v320[4]
        || (((unsigned __int16)(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)&v320[4] + 40LL) + 288LL) >> 8)
           ^ (unsigned __int16)(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v320[4] + 16LL) + 456LL) + 268LL) >> 8))
          & 0x1FF) != 0 )
      {
        if ( !*(_QWORD *)&v320[4]
          || (v148 = IsCompositionInputWindowForHitTest(*(struct tagWND **)&v320[4]), v55 = 1, !v148) )
        {
          v55 = 0;
        }
        v339 = v55;
        v56 = *(_QWORD *)(a1 + 464);
        v57 = *(HWND **)(v56 + 112);
        if ( v57 )
        {
          *(_QWORD *)&v320[4] = *(_QWORD *)(v56 + 112);
          InputTraceLogging::Mouse::RedirectForCapture((const struct tagQMSG *)&v387, *v57);
        }
        else
        {
          Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(v376);
          if ( (_DWORD)v60 )
          {
            v62 = *(struct tagWND **)&v320[4];
          }
          else
          {
            v62 = *(struct tagWND **)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v59, v58, v60, v61)
                                                                        + 18752)
                                                            + 488LL)
                                                + 8LL)
                                    + 24LL);
            Win32HM_LockIntoThread<1>(a1, v62, v376);
          }
          if ( (unsigned int)IsThreadDesktopComposed((const struct tagTHREADINFO *)a1) )
          {
            *(_QWORD *)&v401[0] = LODWORD(v388[1]);
            *((_QWORD *)&v401[0] + 1) = v389[0];
            *(_QWORD *)&v401[1] = v389[1];
            *((_QWORD *)&v401[1] + 1) = &v327;
            LODWORD(v401[2]) = v63;
            BYTE4(v401[2]) = 0;
            *(_WORD *)((char *)&v401[2] + 5) = 0;
            BYTE7(v401[2]) = 0;
            *((_QWORD *)&v401[2] + 1) = &v392[1];
            v402 = 0u;
            v65 = xxxDCEWindowHitTestIndirect(v62, v392[0], 0, (struct tagDCE_WINDOW_HIT_TEST_ARGS *)v401);
            if ( v65 && (_BYTE)v402 )
            {
              v389[1] = *(_QWORD *)&v401[1];
              DWORD1(v390) = SLOWORD(v401[1]);
              v64 = *(_QWORD *)&v401[1] >> 16;
              DWORD2(v390) = SWORD1(v401[1]);
              v324 = *(struct tagPOINT *)((char *)&v390 + 4);
            }
          }
          else
          {
            v65 = (HWND)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))xxxWindowHitTest)(v62, v324, &v327);
          }
          LOBYTE(v64) = 1;
          v66 = (struct tagWND *)HMValidateHandleNoSecure(v65, v64);
          InputTraceLogging::Mouse::SecondaryHitTest((const struct tagQMSG *)&v387, &v324, v66);
          if ( !v339 )
            Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)v376);
          LOBYTE(v67) = 1;
          *(_QWORD *)&v320[4] = HMValidateHandleNoSecure(v65, v67);
          if ( !*(_QWORD *)&v320[4] )
          {
            v276 = *(_QWORD *)(*(_QWORD *)(a1 + 488) + 8LL);
            *(_QWORD *)&v320[4] = *(_QWORD *)(v276 + 24);
            if ( !*(_QWORD *)&v320[4] )
              *(_QWORD *)&v320[4] = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(
                                                                                      v276,
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
                v277 = ValidateHwnd(v72);
                if ( v277 )
                {
                  v278 = *(_QWORD *)(a1 + 464);
                  v279 = *(_QWORD *)(v277 + 16);
                  if ( *(_QWORD *)(v279 + 464) == v278 || *(_QWORD *)(v279 + 456) == *(_QWORD *)(a1 + 456) )
                  {
                    *(_QWORD *)&v320[4] = v277;
                    v327 = 1;
                    *(_DWORD *)(v278 + 156) = 0;
                    v71 = 1;
                  }
                }
              }
            }
          }
          if ( !v71 )
            *(_DWORD *)(*(_QWORD *)(v363 + 464) + 156LL) = v327 != 1;
          Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)v376);
        }
        if ( *(_QWORD *)&v320[4] == *(_QWORD *)(*(_QWORD *)(a1 + 464) + 112LL) )
        {
          v149 = PtiMouseFromQ(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v320[4] + 16LL) + 464LL));
          if ( (((unsigned __int16)(*(_DWORD *)(*((_QWORD *)v150 + 5) + 288LL) >> 8)
               ^ (unsigned __int16)(*(_DWORD *)(*(_QWORD *)(v149 + 456) + 268LL) >> 8))
              & 0x1FF) != 0
            || (unsigned int)IsOleDragDropCaptureWindow(v150) )
          {
            v324 = v392[0];
            v151 = 0;
            TopLevelOrDpiBoundaryWindow = GetTopLevelOrDpiBoundaryWindow(*(const struct tagWND **)&v320[4]);
            v155 = TopLevelOrDpiBoundaryWindow;
            if ( TopLevelOrDpiBoundaryWindow && (unsigned int)IsWindowDesktopComposed(TopLevelOrDpiBoundaryWindow) )
              v151 = (float *)*((_QWORD *)v155 + 27);
            if ( v151 )
            {
              v230 = v18 / v151[5];
              v324.x = (int)(float)((float)((float)(FixedPointSubPixel(v392[1].x) + (float)v324.x) - v151[12])
                                  * (float)(v18 / *v151));
              v324.y = (int)(float)((float)((float)(FixedPointSubPixel(v392[1].y) + (float)v324.y) - v151[13]) * v230);
            }
            if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80000) == 0
              || (v156 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
            {
              v156 = 0;
            }
            if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
              || (v157 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
            {
              v157 = 0;
            }
            if ( v156 || v157 )
            {
              v280 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v153, v154);
              LOBYTE(v281) = v157;
              LOBYTE(v282) = v156;
              WPP_RECORDER_AND_TRACE_SF_dddd(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v282,
                v281,
                *(_QWORD *)(v280 + 69152),
                5,
                20,
                34,
                (__int64)WPP_b198703289513b726a6724fd49b6e756_Traceguids,
                v392[0].x,
                v392[0].y,
                v324.x,
                v324.y);
            }
            v325 = (void *)((LOWORD(v324.y) << 16) | LOWORD(v324.x));
            *(struct tagPOINT *)((char *)&v390 + 4) = v324;
            NextSysMsg = v340;
          }
        }
      }
      Win32HM_ExchangeThreadLock<1>(*(_QWORD *)&v320[4], v359);
      if ( CheckCrossThreadInput(*(struct tagWND *const *)&v320[4], NextSysMsg, &v328, (int *)v320, v341) )
        goto LABEL_75;
      if ( v328 )
      {
        v283 = *(_QWORD *)(*(_QWORD *)&v320[4] + 16LL);
        if ( *(_QWORD *)(v283 + 464) != *(_QWORD *)(a1 + 464) )
          goto LABEL_799;
        if ( !v342 )
        {
          v342 = *(_QWORD *)(*(_QWORD *)&v320[4] + 16LL);
          v362 = v283;
          Win32RawLockedW32Thread::Exchange((Win32RawLockedW32Thread *)v378, (struct _W32THREAD *)v283);
        }
      }
      else if ( (WORD2(v393) & 0x800) != 0
             && !UIPrivilegeIsolation::CheckAccess(
                   (UIPrivilegeIsolation *)&v394,
                   (const struct tagUIPI_INFO *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v320[4] + 16LL) + 456LL) + 864LL),
                   v24) )
      {
        EtwTraceUIPIMsgError(0, *(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v320[4] + 16LL) + 456LL), v319, v389[0], v389[1]);
LABEL_799:
        v284 = W32GetUserSessionState(v73, v283, v24, v25);
        zzzSetCursor(*(struct tagCURSOR **)(v284 + 21712));
        goto LABEL_51;
      }
      v74 = v324;
      v75 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v320[4] + 16LL) + 464LL);
      v76 = *(_DWORD *)(v75 + 156);
      if ( v76 && (v77 = (unsigned int)(v76 - 2), (_DWORD)v77) )
      {
        if ( (_DWORD)v77 != 1 )
          goto LABEL_153;
        v285 = *(_QWORD *)(*(_QWORD *)&v320[4] + 40LL);
        if ( (*(_BYTE *)(v285 + 26) & 0x40) != 0 )
          v286 = *(_DWORD *)(v285 + 96) - v324.x;
        else
          v286 = v324.x - *(_DWORD *)(v285 + 88);
        v324.x = v286;
        v75 = (unsigned int)(v324.y - *(_DWORD *)(*(_QWORD *)(*(_QWORD *)&v320[4] + 40LL) + 92LL));
      }
      else
      {
        v77 = *(_QWORD *)&v320[4];
        v120 = *(_QWORD *)(*(_QWORD *)&v320[4] + 40LL);
        if ( (*(_BYTE *)(v120 + 26) & 0x40) != 0 )
          v121 = *(_DWORD *)(v120 + 112) - v324.x;
        else
          v121 = v324.x - *(_DWORD *)(v120 + 104);
        v324.x = v121;
        v75 = (unsigned int)(v324.y - *(_DWORD *)(*(_QWORD *)(*(_QWORD *)&v320[4] + 40LL) + 108LL));
      }
      v324.y = v75;
LABEL_153:
      if ( !v328
        && *(_QWORD *)(a1 + 464) == *(_QWORD *)(W32GetUserSessionState(v75, v77, *(_QWORD *)&v320[4], v25) + 19248) )
      {
        v105 = *(_QWORD *)(*(_QWORD *)(a1 + 488) + 192LL) != *(_QWORD *)&v320[4];
        if ( (unsigned int)Feature_UserModeNonClientScrollBars2__private_IsEnabledDeviceUsageNoInline()
          && Scrollbar::NonClient::UserModeSupportsUserModeScrollBars(v106) )
        {
          v107 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))xxxFindNCHitEx)(
                   *(_QWORD *)&v320[4],
                   (unsigned int)v327,
                   v324);
        }
        else
        {
          v107 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))FindNCHitEx)(
                   *(_QWORD *)&v320[4],
                   (unsigned int)v327,
                   v324);
        }
        if ( v319 != 512 || v105 || *(_DWORD *)(*(_QWORD *)(a1 + 488) + 200LL) != v107 )
          xxxTrackMouseMove(*(struct tagDESKTOP **)&v320[4], (struct tagWND *)v107);
        if ( !v105 )
        {
          v108 = *(_QWORD *)(a1 + 488);
          if ( (*(_DWORD *)(v108 + 48) & 0x40) != 0
            && (v319 != 512 || !(unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD))PtInRect)(v108 + 204, v74)) )
          {
            ResetMouseHover((struct tagDESKTOP *)v108, v74);
          }
        }
        NextSysMsg = v340;
      }
      v78 = CheckPwndFilter(*(_QWORD *)&v320[4], v345);
      v11 = v329;
      LOBYTE(i) = v322;
      if ( v78 )
      {
        v82 = 0;
        LODWORD(v348) = 0;
        switch ( v319 )
        {
          case 0x201u:
            v51 = (unsigned __int8)IsMessageInputSourceTouch(&v387) == 0;
            v218 = *(_QWORD *)(a1 + 464);
            if ( v51 )
              *(_DWORD *)(v218 + 508) &= ~0x800000u;
            else
              *(_DWORD *)(v218 + 508) |= 0x800000u;
            v219 = IsMessageInputSourcePen(&v387);
            v79 = *(_QWORD *)(v363 + 464);
            v220 = *(_DWORD *)(v79 + 508);
            if ( v219 )
              v189 = v220 | 0x1000000;
            else
              v189 = v220 & 0xFEFFFFFF;
            *(_DWORD *)(v79 + 508) = v189;
LABEL_497:
            if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v320[4] + 136LL) + 8LL) + 8LL) & 8) != 0
              || *(_DWORD *)(*(_QWORD *)(a1 + 464) + 156LL) == 1
              || (unsigned int)IsMenuStarted(a1) )
            {
              v82 = 1;
              LODWORD(v348) = 1;
              v190 = *(_QWORD *)(a1 + 464);
              if ( (unsigned int)v390 <= *(_DWORD *)(v190 + 168)
                && !*(_DWORD *)(W32GetUserSessionState(v190, v79, v80, v81) + 16216) )
              {
                v290 = *(_QWORD *)&v320[4] ? **(_QWORD **)&v320[4] : 0LL;
                v291 = *(_QWORD *)(a1 + 464);
                if ( v290 == *(_QWORD *)(v291 + 176)
                  && v319 == *(_DWORD *)(v291 + 160)
                  && (v319 != 523 || WORD1(v389[0]) == *(_WORD *)(v291 + 164)) )
                {
                  v293 = *(int *)(*(_QWORD *)(W32GetUserSessionState(v291, v287, v288, v289) + 19704) + 2040LL);
                  v292 = HIDWORD(v293);
                  LODWORD(v292) = v293 % 2;
                  v370 = *(_DWORD *)(*(_QWORD *)(a1 + 464) + 184LL) - v293 / 2;
                  v297 = *(int *)(*(_QWORD *)(W32GetUserSessionState(v370, v292, v294, v295) + 19704) + 2044LL);
                  v296 = HIDWORD(v297);
                  LODWORD(v296) = v297 % 2;
                  v371 = *(_DWORD *)(*(_QWORD *)(a1 + 464) + 188LL) - v297 / 2;
                  v300 = W32GetUserSessionState(v371, v296, v298, v299);
                  v301 = *(_QWORD *)(a1 + 464);
                  LODWORD(v302) = *(int *)(*(_QWORD *)(v300 + 19704) + 2040LL) >> 31;
                  LODWORD(v300) = *(_DWORD *)(*(_QWORD *)(v300 + 19704) + 2040LL);
                  v302 = (unsigned int)v302;
                  v303 = __SPAIR64__(v302, v300) % 2;
                  LODWORD(v300) = __SPAIR64__(v302, v300) / 2;
                  LODWORD(v302) = v303;
                  v372 = *(_DWORD *)(v301 + 184) + v300;
                  v373 = *(_DWORD *)(*(_QWORD *)(a1 + 464) + 188LL)
                       + *(_DWORD *)(*(_QWORD *)(W32GetUserSessionState(v301, v302, v304, v305) + 19704) + 2044LL) / 2;
                  if ( (unsigned int)PtInRect(&v370, *(_QWORD *)((char *)&v390 + 4)) )
                  {
                    v319 += 2;
                    v82 = 2;
                    LODWORD(v348) = 2;
                  }
                }
              }
            }
LABEL_499:
            v191 = *(_QWORD *)(a1 + 464);
            v192 = *(_DWORD *)(v191 + 508);
            if ( (v192 & 8) != 0 )
              *(_DWORD *)(v191 + 508) = v192 | 4;
            if ( v319 - 514 <= 0xA )
            {
              v193 = 1097;
              if ( _bittest(&v193, v319 - 514) )
              {
                if ( *(_DWORD *)(*(_QWORD *)(a1 + 464) + 168LL) && ((HIDWORD(v394) - 4) & 0xFFFFFFFB) == 0 )
                {
                  if ( HIDWORD(v394) == 4 )
                    TouchTimeFromCPLValue = GetTouchTimeFromCPLValue(300, 180, 5, 1);
                  else
                    TouchTimeFromCPLValue = GetPenDoubleClickTime();
                  *(_DWORD *)(*(_QWORD *)(a1 + 464) + 168LL) = v397 + TouchTimeFromCPLValue;
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
        if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v320[4] + 16LL) + 464LL) + 156LL) == 1 )
        {
          v319 -= 352;
          v326 = (unsigned int)v327;
        }
        v83 = MiPCheckMsgFilter(NextSysMsg, v319, v331, a5);
        v11 = v329;
        LOBYTE(i) = v322;
        if ( v83 )
        {
          if ( v328 )
            goto LABEL_75;
          if ( v319 - 512 > 0xE )
            break;
          v118 = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 520), 0, 0);
          LOBYTE(i) = v322;
          if ( (v118 & 0x8000) == 0 )
            break;
        }
      }
    }
    if ( (_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 520), 0, 0) & 0x100000) != 0 )
    {
      _InterlockedAnd((volatile signed __int32 *)(a1 + 520), 0xFFEFFFFF);
      xxxWindowEvent(0x800Bu, 0, -9, 0, 1);
    }
    v398[0] = *(_QWORD *)((char *)&v390 + 4);
    if ( *(_QWORD *)&v320[4] )
      v398[1] = **(_QWORD **)&v320[4];
    else
      v398[1] = 0;
    LODWORD(v399) = v327;
    *((_QWORD *)&v399 + 1) = *((_QWORD *)&v391 + 1);
    LODWORD(v400) = v389[0];
    if ( *(_DWORD *)v320 )
    {
      if ( v319 != 512 && v319 != 160 )
      {
        v335 = 1;
        if ( (unsigned int)xxxCallCtfHook(7, 0, v319, v398) )
          goto LABEL_51;
      }
    }
    if ( ((*(_DWORD *)(a1 + 712) | *(_DWORD *)(**(_QWORD **)(a1 + 496) + 16LL)) & 0x100) != 0 )
    {
      v335 = 1;
      if ( (unsigned int)xxxCallMouseHook(v319, v398, *(unsigned int *)v320) )
        goto LABEL_51;
    }
    if ( (unsigned int)PsGetWin32KFilterSet() == 5 )
    {
      v306 = *((_QWORD *)PtiCurrent() + 64);
      v333 = 0;
      v333 = *(_QWORD *)(v306 + 248) != 0;
      if ( v333 )
      {
        if ( xxxClientCallLocalMouseHooks(v319, v398, *(unsigned int *)v320) )
          goto LABEL_51;
      }
    }
    if ( (*(_DWORD *)(a1 + 1360) & 0x2000LL) == 0 && (!v327 || v327 == -2) )
    {
      v197 = 0;
      if ( v339 )
      {
        v308 = (unsigned int)IsIndependentInputWindow(*(const struct tagWND **)&v320[4])
             ? GetCompositionInputWindowUIOwner(v307)
             : *(struct tagWND **)&v320[4];
        TopLevelWindow = (const struct tagWND *)GetTopLevelWindow(v308);
        v197 = TopLevelWindow;
        if ( TopLevelWindow )
        {
          v197 = CoreWindowProp::GetCompositeAppFrameWindowOrSelf(TopLevelWindow);
          Win32HMOptionalThreadLock<tagWND>::Win32HMOptionalThreadLock<tagWND>(v385, a1, v197);
          v310 = 0;
          if ( v197 )
            v310 = *(_QWORD *)v197;
          xxxSendMessage(v197, 32, v310, (unsigned __int16)v327 | (LOWORD(v388[1]) << 16));
          Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)v385);
        }
      }
      if ( !v197 )
      {
        if ( *(_QWORD *)&v320[4] )
          v311 = **(_QWORD **)&v320[4];
        else
          v311 = 0;
        xxxSendMessage(*(_QWORD *)&v320[4], 32, v311, (unsigned __int16)v327 | (LOWORD(v388[1]) << 16));
      }
      if ( *(struct tagQMSG **)(*(_QWORD *)(a1 + 464) + 88LL) == NextSysMsg
        && NextSysMsg
        && (unsigned int)IsMiPActive(a1, NextSysMsg)
        && (*((_DWORD *)NextSysMsg + 25) & 0x400) != 0
        && (unsigned int)IsGenuineMouseInput((char *)NextSysMsg + 124)
        && (unsigned int)IsMiPMouseMessage(*((unsigned int *)NextSysMsg + 6)) )
      {
        memset_0(v401, 0, 0xA8u);
        GeneratePointerMessageFromMouse(
          (struct tagQMSG *)v401,
          v319,
          NextSysMsg,
          *(struct tagWND **)&v320[4],
          *(int *)v320);
        SetMiPPromotion(*(_QWORD *)(*(_QWORD *)&v320[4] + 16LL), DWORD2(v401[1]));
      }
      goto LABEL_51;
    }
    if ( *(struct tagQMSG **)(*(_QWORD *)(a1 + 464) + 88LL) != NextSysMsg )
      goto LABEL_75;
    memset_0(v401, 0, 0x60u);
    v88 = v401[0];
    v89 = v401[1];
    v90 = v401[2];
    v91 = v402;
    v348 = v403;
    *(_OWORD *)BugCheckParameter2 = v404;
    v92 = 0;
    v410 = v387;
    v411 = *(_OWORD *)v388;
    v412 = *(_OWORD *)v389;
    v413 = v390;
    v414 = v391;
    v415 = *(_OWORD *)&v392[0].x;
    v416 = v393;
    v417 = v394;
    v418 = v395;
    v419 = v396;
    v420 = v397;
    if ( NextSysMsg && (unsigned int)IsMiPActive(a1, NextSysMsg) )
    {
      DWORD2(v411) = v319;
      *(_QWORD *)&v412 = v326;
      if ( (*((_DWORD *)NextSysMsg + 25) & 0x400) != 0 )
      {
        memset_0(v401, 0, 0xA8u);
        if ( ShouldGenerateMipMessage((struct tagTHREADINFO *)a1, NextSysMsg, *(struct tagWND **)&v320[4], *(int *)v320) )
        {
          v93 = *(_QWORD *)(a1 + 1512);
          if ( v93 && (*(_DWORD *)v93 & 1) != 0 )
          {
            v88 = *(_OWORD *)(v93 + 24);
            v89 = *(_OWORD *)(v93 + 40);
            v90 = *(_OWORD *)(v93 + 56);
            v91 = *(_OWORD *)(v93 + 72);
            v348 = *(_OWORD *)(v93 + 88);
            *(_OWORD *)BugCheckParameter2 = *(_OWORD *)(v93 + 104);
            v92 = 1;
          }
          if ( GeneratePointerMessageFromMouse(
                 (struct tagQMSG *)v401,
                 v319,
                 NextSysMsg,
                 *(struct tagWND **)&v320[4],
                 *(int *)v320) )
          {
            v387 = v401[0];
            *(_OWORD *)v388 = v401[1];
            *(_OWORD *)v389 = v401[2];
            v390 = v402;
            v391 = v403;
            *(_OWORD *)&v392[0].x = v404;
            v393 = v405;
            v394 = v406;
            v395 = v407;
            v396 = v408;
            v397 = v409;
            v29 = 1;
            v338 = 1;
            v87 = (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128((__m128i)v401[1], 8));
            if ( (_DWORD)v87 == 582 && (unsigned int)IsMiPEnabledForWindow(*(_QWORD *)&v320[4]) )
            {
              if ( v85 )
                v85 = **(_QWORD **)&v320[4];
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
        if ( *(_DWORD *)v320 )
        {
          *((_DWORD *)NextSysMsg + 25) &= ~0x400u;
          goto LABEL_189;
        }
LABEL_190:
        v9 = 1;
        goto LABEL_191;
      }
      if ( !*(_DWORD *)v320 )
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
              xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v387, 1);
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
    if ( !*(_DWORD *)v320 )
      goto LABEL_190;
    v137 = W32GetUserSessionState(v85, v84, v86, v87);
    if ( DWORD2(v411) == 512 || DWORD2(v411) == 160 )
    {
      v138 = *(_QWORD *)&v320[4] ? **(_QWORD **)&v320[4] : 0LL;
      if ( v138 != *(_QWORD *)(v137 + 16288) && (unsigned int)IsGenuineMouseInput((char *)NextSysMsg + 124) )
      {
        LOBYTE(v134) = 1;
        v140 = HMValidateHandleNoSecure(*(_QWORD *)(v137 + 16288), v134);
        v141 = (struct tagWND *)v140;
        if ( v140 )
        {
          v178 = *(_QWORD *)(v140 + 16);
          if ( !*(_QWORD *)(v178 + 640) )
          {
            if ( (unsigned int)IsMiPEnabledForThread(v178) )
            {
              MiPWindowFlags = GetMiPWindowFlags(v141);
              v134 = 1;
              if ( (MiPWindowFlags & 1) == 0 )
              {
                v180 = (struct tagQ **)*((_QWORD *)v141 + 2);
                if ( v180 == (struct tagQ **)a1 )
                {
                  v181 = *(_QWORD *)(a1 + 1512);
                  v182 = *(_OWORD *)(v181 + 24);
                  v183 = *(_OWORD *)(v181 + 40);
                  v184 = *(_OWORD *)(v181 + 56);
                  v185 = *(_OWORD *)(v181 + 72);
                  v186 = *(_OWORD *)(v181 + 88);
                  v187 = *(_OWORD *)(v181 + 104);
                  if ( v92 )
                  {
                    *(_OWORD *)(v181 + 24) = v88;
                    *(_OWORD *)(v181 + 40) = v89;
                    *(_OWORD *)(v181 + 56) = v90;
                    *(_OWORD *)(v181 + 72) = v91;
                    *(_OWORD *)(v181 + 88) = v348;
                    *(_OWORD *)(v181 + 104) = *(_OWORD *)BugCheckParameter2;
                  }
                  memset((char *)&v401[1] + 8, 0, 24);
                  Win32HMThreadLockBase<tagWND,0,0>::Win32HMThreadLockBase<tagWND,0,0>(BugCheckParameter3, v141);
                  FindTimer((_DWORD)v141, 65523, 2, 1, 0);
                  if ( (unsigned int)IsMiPEnabledForWindow(v141) )
                    xxxSendTransformableMessageTimeout(v188, 0x24Au, 0, 0, 0, 1, 0);
                  if ( v92 )
                  {
                    v221 = *(_QWORD *)(a1 + 1512);
                    *(_OWORD *)(v221 + 24) = v182;
                    *(_OWORD *)(v221 + 40) = v183;
                    *(_OWORD *)(v221 + 56) = v184;
                    *(_OWORD *)(v221 + 72) = v185;
                    *(_OWORD *)(v221 + 88) = v186;
                    *(_OWORD *)(v221 + 104) = v187;
                  }
                  Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)BugCheckParameter3);
                  NextSysMsg = v340;
                }
                else
                {
                  PostEventMessageEx((struct tagTHREADINFO *)v180, v180[58], 0x15u, v141, 0, 0, 0, 0);
                }
              }
            }
          }
        }
        if ( v338 )
        {
          if ( *(_QWORD *)&v320[4] )
            v312 = **(_QWORD **)&v320[4];
          else
            v312 = 0;
          *(_QWORD *)(v137 + 16288) = v312;
        }
        else
        {
          *(_QWORD *)(v137 + 16288) = 0;
        }
      }
    }
    v29 = v338;
    if ( !v338 )
    {
      v147 = v82 - 1;
      if ( v147 )
      {
        if ( v147 == 1 )
          *(_DWORD *)(*(_QWORD *)(a1 + 464) + 168LL) = 0;
      }
      else
      {
        *(_DWORD *)(*(_QWORD *)(a1 + 464) + 160LL) = v388[1];
        v226 = v389[0] >> 16;
        *(_WORD *)(*(_QWORD *)(a1 + 464) + 164LL) = WORD1(v389[0]);
        v227 = W32GetUserSessionState(v226, v134, v135, v136);
        *(_DWORD *)(*(_QWORD *)(a1 + 464) + 168LL) = v390 + *(_DWORD *)(v227 + 14664);
        if ( *(_QWORD *)&v320[4] )
          v228 = **(_QWORD **)&v320[4];
        else
          v228 = 0;
        *(_QWORD *)(*(_QWORD *)(a1 + 464) + 176LL) = v228;
        *(_QWORD *)(*(_QWORD *)(a1 + 464) + 184LL) = *(_QWORD *)((char *)&v390 + 4);
      }
    }
    v139 = (const struct tagQMSG *)&v387;
    if ( v29 )
      v139 = (const struct tagQMSG *)&v410;
    if ( xxxMouseActivate((struct tagTHREADINFO *)a1, *(struct tagWND **)&v320[4], v139, v327) == 1 )
    {
      v9 = 1;
      goto LABEL_51;
    }
    if ( !*(_DWORD *)v320 )
      goto LABEL_190;
    v9 = 1;
    xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v387, 1);
LABEL_191:
    if ( *(_DWORD *)v320 && v335 && ((*(_BYTE *)(a1 + 712) | *(_BYTE *)(**(_QWORD **)(a1 + 496) + 16LL)) & 0x40) != 0 )
      xxxCallHook(6, v319, (__int64)v398, 5);
    v335 = 0;
    v325 = (void *)((LOWORD(v324.y) << 16) | LOWORD(v324.x));
    if ( v319 >= 0x200 )
      v326 = (unsigned int)GetMouseKeyFlags(*(_QWORD *)(a1 + 464));
    if ( (v319 - 171 <= 2 || v319 - 523 <= 2) && !v29 )
      v326 |= v389[0];
    if ( v327 == 5 )
    {
      if ( *(_DWORD *)v320 )
      {
        v313 = *(_QWORD *)(a1 + 640);
        if ( v313 )
        {
          if ( (*(_DWORD *)(v313 + 8) & 0x100) != 0 && *(_QWORD *)v313 && (**(_DWORD **)v313 & 1) != 0 )
          {
            MenuStateOwnerLockxxxUnlock::MenuStateOwnerLockxxxUnlock(
              (MenuStateOwnerLockxxxUnlock *)v369,
              *(struct tagMENUSTATE **)(a1 + 640));
            if ( !(unsigned int)xxxCallHandleMenuMessages(v313, *(_DWORD *)&v320[4], v319, v326, (__int64)v325) )
            {
              MenuStateOwnerLockxxxUnlock::~MenuStateOwnerLockxxxUnlock((MenuStateOwnerLockxxxUnlock *)v369);
              break;
            }
            MenuStateOwnerLockxxxUnlock::~MenuStateOwnerLockxxxUnlock((MenuStateOwnerLockxxxUnlock *)v369);
LABEL_845:
            v18 = FLOAT_1_0;
LABEL_846:
            v11 = v329;
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
  v100 = v331;
LABEL_211:
  if ( ((HIDWORD(v394) - 2) & 0xFFFFFFCF) == 0 && HIDWORD(v394) != 50 )
  {
    v319 = (unsigned int)v388[1];
    v326 = v389[0];
    v325 = (void *)v389[1];
LABEL_214:
    if ( *(_DWORD *)v320 )
    {
      if ( !*(_QWORD *)(a1 + 640) && (unsigned int)IsMiPEnabledForThread(a1) && v29 )
      {
        if ( *(_QWORD *)&v320[4] )
          v101 = **(_QWORD **)&v320[4];
        else
          v101 = 0;
        *(_QWORD *)(*(_QWORD *)(a1 + 1512) + 48LL) = v101;
        v102 = *(_QWORD *)(a1 + 1512);
        v103 = *(_DWORD *)(v102 + 36);
        if ( (v103 & 0x400000) != 0 && (*(_DWORD *)(*(_QWORD *)&v320[4] + 380LL) & 0x40000000) == 0 )
          *(_DWORD *)(v102 + 36) = v103 & 0xFFBFFFFF;
        v104 = GetMiPWindowFlags(*(struct tagWND **)&v320[4]);
        SetMiPWindowFlags(*(struct tagWND **)&v320[4], v104 & 0xFFFFFFFFFFFFFFFEuLL);
        if ( ((LODWORD(v388[1]) - 578) & 0xFFFFFFFB) != 0 )
        {
          if ( ((LODWORD(v388[1]) - 579) & 0xFFFFFFFB) == 0 )
            **(_DWORD **)(a1 + 1512) &= ~8u;
        }
        else
        {
          v314 = 0;
          if ( LODWORD(v388[1]) == 578 )
            v314 = 8;
          **(_DWORD **)(a1 + 1512) = v314 | **(_DWORD **)(a1 + 1512) & 0xFFFFFFF7;
        }
      }
      else
      {
        xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v387, 1);
      }
    }
    if ( (unsigned int)IsPointerMessageTouchpad((struct tagTHREADINFO *)a1, v389[1], v29) )
    {
      if ( !*(_DWORD *)v320 && !ShouldReceiveTouchpadMessages((const struct tagTHREADINFO *)a1, v388[0]) )
        xxxSkipSysMsgEx((struct tagTHREADINFO *)a1, (struct tagQMSG *)&v387, 1);
      if ( v319 == 595 )
        v325 = (void *)-1LL;
    }
    goto LABEL_198;
  }
  EtwTraceBeginPointerMessageRetrieve(NextSysMsg, LOWORD(v389[0]), LODWORD(v388[1]));
  v421[0] = *(_OWORD *)NextSysMsg;
  v421[1] = *((_OWORD *)NextSysMsg + 1);
  v421[2] = *((_OWORD *)NextSysMsg + 2);
  v421[3] = *((_OWORD *)NextSysMsg + 3);
  v421[4] = *((_OWORD *)NextSysMsg + 4);
  v421[5] = *((_OWORD *)NextSysMsg + 5);
  v421[6] = *((_OWORD *)NextSysMsg + 6);
  v421[7] = *((_OWORD *)NextSysMsg + 7);
  v421[8] = *((_OWORD *)NextSysMsg + 8);
  v421[9] = *((_OWORD *)NextSysMsg + 9);
  v422 = *((_QWORD *)NextSysMsg + 20);
  v112 = (unsigned int)xxxRetrievePointerInputMessage(
                         a1,
                         v345,
                         v100,
                         a5,
                         1,
                         0,
                         (int *)v320,
                         NextSysMsg,
                         (__int64)&v320[4],
                         (__int64)&v319,
                         (__int64)&v326,
                         (__int64)&v325,
                         &v328,
                         v341);
  InputTraceLogging::Pointer::RetrieveMessage(v421, 0, v112);
  EtwTraceEndPointerMessageRetrieve(v421, LOWORD(v389[0]), LODWORD(v388[1]));
  v113 = *(_QWORD *)&v320[4];
  if ( *(_QWORD *)&v320[4] )
    Win32HM_ExchangeThreadLock<1>(*(_QWORD *)&v320[4], v359);
  v114 = v112 - 1;
  if ( !v114 )
    goto LABEL_214;
  v115 = v114 - 1;
  if ( v115 )
  {
    v116 = v115 - 1;
    if ( v116 )
    {
      *v341 = 0;
      if ( v116 == 1 )
      {
        v11 = v329;
        goto LABEL_23;
      }
    }
    else
    {
      xxxDefPointerProc(v113, LODWORD(v388[1]), v389[0], v389[1]);
      *v341 = 0;
    }
    goto LABEL_51;
  }
  if ( !v328 )
    goto LABEL_75;
  v343 = *(_QWORD *)(*(_QWORD *)&v320[4] + 16LL);
  v269 = v343;
  v270 = (Win32RawLockedW32Thread *)v381;
LABEL_734:
  Win32RawLockedW32Thread::Exchange(v270, (struct _W32THREAD *)v269);
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
      (__int64)WPP_b198703289513b726a6724fd49b6e756_Traceguids,
      v122,
      a1,
      v123);
  }
  *(_QWORD *)(*(_QWORD *)(a1 + 464) + 72LL) = 0;
  **(_DWORD **)(a1 + 480) &= ~1u;
  v40 = v342;
  v41 = v347;
  v42 = v349;
  v43 = v343;
  if ( v356 )
  {
    SetWakeBit(v356, 16385);
    ClearWakeBit((struct tagTHREADINFO *)a1, 0x4001u, 0);
  }
  else if ( !v342 && !v347 && !v349 && !v343 )
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
  if ( v334[0] )
  {
    v45 = PtiCurrent();
    *((_QWORD *)v45 + 170) &= ~0x1000000000uLL;
  }
  Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)v359);
  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v381);
  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v382);
  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v380);
  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v378);
  Win32RawLockedW32Thread::~Win32RawLockedW32Thread((Win32RawLockedW32Thread *)v379);
  return 0;
}

```

## disassembly

```asm
0x1401cdc10  mov     rax, rsp
0x1401cdc13  push    rbx
0x1401cdc14  push    rsi
0x1401cdc15  push    rdi
0x1401cdc16  push    r12
0x1401cdc18  push    r13
0x1401cdc1a  push    r14
0x1401cdc1c  push    r15
0x1401cdc1e  sub     rsp, 6A0h
0x1401cdc25  movaps  xmmword ptr [rax-48h], xmm6
0x1401cdc29  movaps  xmmword ptr [rax-58h], xmm7
0x1401cdc2d  movaps  xmmword ptr [rax-68h], xmm8
0x1401cdc32  movaps  xmmword ptr [rax-78h], xmm9
0x1401cdc37  movaps  xmmword ptr [rax-88h], xmm10
0x1401cdc3f  movaps  xmmword ptr [rax-98h], xmm11
0x1401cdc47  movaps  xmmword ptr [rax-0A8h], xmm12
0x1401cdc4f  movaps  xmmword ptr [rax-0B8h], xmm13
0x1401cdc57  movaps  xmmword ptr [rax-0C8h], xmm14
0x1401cdc5f  movaps  xmmword ptr [rax-0D8h], xmm15
0x1401cdc67  mov     rax, cs:__security_cookie
0x1401cdc6e  xor     rax, rsp
0x1401cdc71  mov     [rsp+6D8h+var_E8], rax
0x1401cdc79  mov     eax, r9d
0x1401cdc7c  mov     [rsp+6D8h+var_61C], eax
0x1401cdc83  mov     [rsp+6D8h+var_5D8], r8
0x1401cdc8b  mov     [rsp+6D8h+var_528], rdx
0x1401cdc93  mov     [rsp+6D8h+var_558], rcx
0x1401cdc9b  mov     [rsp+6D8h+var_510], rcx
0x1401cdca3  mov     [rsp+6D8h+var_4D0], rdx
0x1401cdcab  mov     r14, rcx
0x1401cdcae  mov     [rsp+6D8h+var_590], rcx
0x1401cdcb6  mov     [rsp+6D8h+var_508], rcx
0x1401cdcbe  mov     [rsp+6D8h+var_550], rdx
0x1401cdcc6  mov     [rsp+6D8h+var_4F8], r8
0x1401cdcce  mov     [rsp+6D8h+var_5A0], eax
0x1401cdcd5  mov     rbx, [rsp+6D8h+arg_38]
0x1401cdcdd  mov     [rsp+6D8h+var_5F8], rbx
0x1401cdce5  xor     edx, edx; Val
0x1401cdce7  mov     r8d, 0A8h; Size
0x1401cdced  lea     rcx, [rsp+6D8h+var_3D8]; void *
0x1401cdcf5  call    memset_0
0x1401cdcfa  xor     esi, esi
0x1401cdcfc  mov     [rsp+6D8h+var_660], rsi
0x1401cdd01  mov     [rsp+6D8h+var_668], esi
0x1401cdd05  mov     [rsp+6D8h+var_638], rsi
0x1401cdd0d  mov     [rsp+6D8h+var_640], rsi
0x1401cdd15  mov     qword ptr [rsp+6D8h+var_648.x], rsi
0x1401cdd1d  mov     [rsp+6D8h+var_62C], esi
0x1401cdd24  mov     [rsp+6D8h+var_630], esi
0x1401cdd2b  xorps   xmm0, xmm0
0x1401cdd2e  xor     eax, eax
0x1401cdd30  movups  xmmword ptr [rsp+6D8h+var_328], xmm0
0x1401cdd38  movups  [rsp+6D8h+var_318], xmm0
0x1401cdd40  mov     [rsp+6D8h+var_308], rax
0x1401cdd48  mov     edx, dword ptr [rsp+6D8h+arg_28]
0x1401cdd4f  lea     r12d, [rsi+1]
0x1401cdd53  and     edx, r12d
0x1401cdd56  mov     [rsp+6D8h+var_668+4], edx
0x1401cdd5a  mov     [rbx], rsi
0x1401cdd5d  lea     rbx, [r14+1D0h]
0x1401cdd64  mov     [rsp+6D8h+var_628], rbx
0x1401cdd6c  mov     r9d, [rsp+6D8h+arg_30]
0x1401cdd74  cmp     r9d, 2000h
0x1401cdd7b  jz      loc_1401CF7D6
0x1401cdd81  mov     [rsp+6D8h+var_628], rbx
0x1401cdd89  mov     [rsp+6D8h+var_500], rbx
0x1401cdd91  mov     r15, [rbx]
0x1401cdd94  cmp     [r15+48h], rsi
0x1401cdd98  jnz     short loc_1401CDDFD
0x1401cdd9a  lea     r8, WPP_GLOBAL_Control
0x1401cdda1  mov     rcx, cs:WPP_GLOBAL_Control
0x1401cdda8  cmp     rcx, r8
0x1401cddab  jz      short loc_1401CDDBA
0x1401cddad  test    dword ptr [rcx+2Ch], 20000h
0x1401cddb4  jnz     loc_1401D1136
0x1401cddba  mov     bl, sil
0x1401cddbd  lea     rcx, WPP_RECORDER_INITIALIZED
0x1401cddc4  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1401cddcb  setnz   dil
0x1401cddcf  test    bl, bl
0x1401cddd1  jnz     loc_1401CF306
0x1401cddd7  test    dil, dil
0x1401cddda  jnz     loc_1401CF306
0x1401cdde0  mov     rbx, [rsp+6D8h+var_628]
0x1401cdde8  mov     rax, [rbx]
0x1401cddeb  mov     [rax+48h], r14
0x1401cddef  mov     rax, [r14+1E0h]
0x1401cddf6  or      [rax], r12d
0x1401cddf9  mov     edx, [rsp+6D8h+var_668+4]
0x1401cddfd  test    r9d, 1C07h
0x1401cde04  jnz     loc_1401CF843
0x1401cde0a  mov     rcx, [rbx]
0x1401cde0d  cmp     [rcx+48h], r14
0x1401cde11  jnz     loc_1401CF63F
0x1401cde17  mov     [rsp+6D8h+var_530], r14
0x1401cde1f  mov     ecx, [rsp+6D8h+arg_20]
0x1401cde26  mov     [rsp+6D8h+var_594], ecx
0x1401cde2d  mov     [rsp+6D8h+var_4B8], r14
0x1401cde35  mov     r15d, [rsp+6D8h+var_61C]
0x1401cde3d  mov     [rsp+6D8h+var_598], r15d
0x1401cde45  mov     [rsp+6D8h+var_5A8], esi
0x1401cde4c  mov     [rsp+6D8h+var_604], esi
0x1401cde53  mov     eax, esi
0x1401cde55  mov     [rsp+6D8h+var_620], eax
0x1401cde5c  mov     [rsp+6D8h+var_654], eax
0x1401cde63  mov     [rsp+6D8h+var_650], al
0x1401cde6a  mov     [rsp+6D8h+var_5E0], rsi
0x1401cde72  mov     [rsp+6D8h+var_5D0], esi
0x1401cde79  mov     [rsp+6D8h+var_614], esi
0x1401cde80  mov     [rsp+6D8h+var_658], esi
0x1401cde87  mov     rax, rsi
0x1401cde8a  mov     [rsp+6D8h+var_5F0], rax
0x1401cde92  mov     [rsp+6D8h+var_548], rax
0x1401cde9a  mov     [rsp+6D8h+var_588], rsi
0x1401cdea2  mov     [rsp+6D8h+var_5C8], rax
0x1401cdeaa  mov     [rsp+6D8h+var_5B0], rsi
0x1401cdeb2  mov     [rsp+6D8h+var_5E8], rax
0x1401cdeba  xor     edx, edx; struct _W32THREAD *
0x1401cdebc  lea     rcx, [rsp+6D8h+var_498]; this
0x1401cdec4  call    ??0Win32RawLockedW32Thread@@QEAA@PEAU_W32THREAD@@@Z; Win32RawLockedW32Thread::Win32RawLockedW32Thread(_W32THREAD *)
0x1401cdec9  xor     edx, edx; struct _W32THREAD *
0x1401cdecb  lea     rcx, [rsp+6D8h+var_4B0]; this
0x1401cded3  call    ??0Win32RawLockedW32Thread@@QEAA@PEAU_W32THREAD@@@Z; Win32RawLockedW32Thread::Win32RawLockedW32Thread(_W32THREAD *)
0x1401cded8  xor     edx, edx; struct _W32THREAD *
0x1401cdeda  lea     rcx, [rsp+6D8h+var_480]; this
0x1401cdee2  call    ??0Win32RawLockedW32Thread@@QEAA@PEAU_W32THREAD@@@Z; Win32RawLockedW32Thread::Win32RawLockedW32Thread(_W32THREAD *)
0x1401cdee7  xor     edx, edx; struct _W32THREAD *
0x1401cdee9  lea     rcx, [rsp+6D8h+var_450]; this
0x1401cdef1  call    ??0Win32RawLockedW32Thread@@QEAA@PEAU_W32THREAD@@@Z; Win32RawLockedW32Thread::Win32RawLockedW32Thread(_W32THREAD *)
0x1401cdef6  xor     edx, edx; struct _W32THREAD *
0x1401cdef8  lea     rcx, [rsp+6D8h+var_468]; this
0x1401cdf00  call    ??0Win32RawLockedW32Thread@@QEAA@PEAU_W32THREAD@@@Z; Win32RawLockedW32Thread::Win32RawLockedW32Thread(_W32THREAD *)
0x1401cdf05  mov     [rsp+6D8h+var_660], rsi
0x1401cdf0a  xor     r8d, r8d
0x1401cdf0d  mov     rdx, r14
0x1401cdf10  lea     rcx, [rsp+6D8h+var_568]
0x1401cdf18  call    ??0?$Win32HMOptionalThreadLock@UtagWND@@@@QEAA@PEAUtagTHREADINFO@@PEAUtagWND@@@Z; Win32HMOptionalThreadLock<tagWND>::Win32HMOptionalThreadLock<tagWND>(tagTHREADINFO *,tagWND *)
0x1401cdf1d  lea     rcx, [rsp+6D8h+var_616]; this
0x1401cdf25  call    ??0CManageInScanSysQueueBit@@QEAA@XZ; CManageInScanSysQueueBit::CManageInScanSysQueueBit(void)
0x1401cdf2a  movss   xmm6, cs:__real@3f800000
0x1401cdf32  mov     rcx, cs:WPP_GLOBAL_Control
0x1401cdf39  lea     rax, WPP_GLOBAL_Control
0x1401cdf40  cmp     rcx, rax
0x1401cdf43  jz      short loc_1401CDF52
0x1401cdf45  test    dword ptr [rcx+2Ch], 20000h
0x1401cdf4c  jnz     loc_1401D1148
0x1401cdf52  mov     r12b, sil
0x1401cdf55  lea     rdx, WPP_RECORDER_INITIALIZED
0x1401cdf5c  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1401cdf63  jnz     loc_1401CE635
0x1401cdf69  mov     r15b, sil
0x1401cdf6c  test    r12b, r12b
0x1401cdf6f  jnz     loc_1401D1157
0x1401cdf75  test    r15b, r15b
0x1401cdf78  jnz     loc_1401D1157
0x1401cdf7e  mov     rax, [rbx]
0x1401cdf81  mov     [rax+58h], rsi
0x1401cdf85  mov     r12d, 1
0x1401cdf8b  mov     ecx, [rsp+6D8h+var_654]
0x1401cdf92  nop
0x1401cdf93  mov     rax, [r14+200h]
0x1401cdf9a  mov     r13d, [rax]
0x1401cdf9d  shr     r13, 9
0x1401cdfa1  and     r13d, r12d
0x1401cdfa4  mov     [rsp+6D8h+var_4D8], r13d
0x1401cdfac  jmp     short loc_1401CDFEE
0x1401cdfae  xor     esi, esi
0x1401cdfb0  lea     r12d, [rsi+1]
0x1401cdfb4  lea     rdx, WPP_RECORDER_INITIALIZED
0x1401cdfbb  lea     r13d, [rsi+2]
0x1401cdfbf  mov     rax, [rsp+6D8h+var_548]
0x1401cdfc7  mov     [rsp+6D8h+var_5F0], rax
0x1401cdfcf  mov     ecx, esi
0x1401cdfd1  mov     [rsp+6D8h+var_5C8], rcx
0x1401cdfd9  mov     [rsp+6D8h+var_5E8], rcx
0x1401cdfe1  mov     r14, [rsp+6D8h+var_590]
0x1401cdfe9  jmp     loc_1401CE3B2
0x1401cdfee  mov     rdx, [rbx]
0x1401cdff1  cmp     [rdx+58h], rsi
0x1401cdff5  jnz     loc_1401D11CB
0x1401cdffb  mov     eax, esi
0x1401cdffd  mov     [rsp+6D8h+var_620], eax
0x1401ce004  mov     al, sil
0x1401ce007  mov     [rsp+6D8h+var_654], eax
0x1401ce00e  mov     [rsp+6D8h+var_650], al
0x1401ce015  mov     [rsp+6D8h+var_638], rsi
0x1401ce01d  lea     r8, [rsp+6D8h+var_3D8]; struct tagQMSG *
0x1401ce025  mov     rdx, [rdx+58h]; struct tagQMSG *
0x1401ce029  mov     rcx, r14; struct tagTHREADINFO *
0x1401ce02c  call    ?xxxGetNextSysMsg@@YAPEAUtagQMSG@@PEAUtagTHREADINFO@@PEAU1@1@Z; xxxGetNextSysMsg(tagTHREADINFO *,tagQMSG *,tagQMSG *)
0x1401ce031  mov     rdi, rax
0x1401ce034  mov     [rsp+6D8h+var_600], rax
0x1401ce03c  mov     rcx, cs:WPP_GLOBAL_Control
0x1401ce043  lea     rax, WPP_GLOBAL_Control
0x1401ce04a  cmp     rcx, rax
0x1401ce04d  jnz     loc_1401CF2EA
0x1401ce053  mov     r12b, sil
0x1401ce056  lea     rdx, WPP_RECORDER_INITIALIZED
0x1401ce05d  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1401ce064  jnz     loc_1401CFE33
0x1401ce06a  mov     r15b, sil
0x1401ce06d  test    r12b, r12b
0x1401ce070  jnz     loc_1401D11FB
0x1401ce076  test    r15b, r15b
0x1401ce079  jnz     loc_1401D11FB
0x1401ce07f  mov     rax, [rbx]
0x1401ce082  mov     [rax+58h], rdi
0x1401ce086  test    rdi, rdi
0x1401ce089  jnz     loc_1401CE256
0x1401ce08f  mov     rax, [rbx]
0x1401ce092  cmp     [rax+58h], rsi
0x1401ce096  jz      loc_1401CE38E
0x1401ce09c  lea     rcx, [rsp+6D8h+var_568]; BugCheckParameter3
0x1401ce0a4  call    ??$ManualUnlock@X@?$Win32HMThreadLockBase@UtagCURSOR@@$00$00@@QEAAPEAUtagCURSOR@@XZ; Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>(void)
0x1401ce0a9  mov     r12d, 1
0x1401ce0af  mov     dl, r12b
0x1401ce0b2  mov     rcx, [rsp+6D8h+var_3C8]
0x1401ce0ba  call    HMValidateHandleNoSecure
0x1401ce0bf  mov     [rsp+6D8h+var_660], rax
0x1401ce0c4  lea     r8, [rsp+6D8h+var_568]
0x1401ce0cc  mov     rdx, rax
0x1401ce0cf  mov     rcx, r14
0x1401ce0d2  call    ??$Win32HM_LockIntoThread@$00@@YAXPEAUtagTHREADINFO@@PEAU_HEAD@@PEAU_Win32HMThreadLockItem@@@Z; Win32HM_LockIntoThread<1>(tagTHREADINFO *,_HEAD *,_Win32HMThreadLockItem *)
0x1401ce0d7  mov     edx, dword ptr [rsp+6D8h+var_378]
0x1401ce0de  test    edx, edx
0x1401ce0e0  jnz     loc_1401CE2E0
0x1401ce0e6  cmp     [rsp+6D8h+arg_30], 2000h
0x1401ce0f1  mov     ecx, [rsp+6D8h+var_654]
0x1401ce0f8  jz      loc_1401CDF92
0x1401ce0fe  mov     r15d, esi
0x1401ce101  mov     [rsp+6D8h+var_608], esi
0x1401ce108  mov     eax, esi
0x1401ce10a  mov     [rsp+6D8h+var_610], eax
0x1401ce111  mov     [rsp+6D8h+var_60C], eax
0x1401ce118  mov     eax, dword ptr [rsp+6D8h+var_3C8+8]
0x1401ce11f  mov     [rsp+6D8h+var_668], eax
0x1401ce123  cmp     eax, 24Ah
0x1401ce128  ja      loc_1401CE75B
0x1401ce12e  jz      loc_1401CF015
0x1401ce134  cmp     eax, 11Bh
0x1401ce139  ja      loc_1401D02AE
0x1401ce13f  jz      loc_1401CE67D
0x1401ce145  sub     eax, 23h ; '#'
0x1401ce148  jz      loc_1401D1C5A
0x1401ce14e  sub     eax, 0DBh
0x1401ce153  jz      loc_1401CE6B0
0x1401ce159  sub     eax, r12d
0x1401ce15c  jnz     loc_1401CE647
0x1401ce162  mov     rax, [rsp+6D8h+var_3B8]
0x1401ce16a  mov     [rsp+6D8h+var_638], rax
0x1401ce172  mov     rdx, [rsp+6D8h+var_3B8+8]; __int64
0x1401ce17a  mov     [rsp+6D8h+var_640], rdx
0x1401ce182  mov     rcx, r14; struct tagTHREADINFO *
0x1401ce185  call    ?DeleteHidDataIfAlreadyHandledByGRIB@@YA_NPEAUtagTHREADINFO@@_J@Z; DeleteHidDataIfAlreadyHandledByGRIB(tagTHREADINFO *,__int64)
0x1401ce18a  test    al, al
0x1401ce18c  jnz     short loc_1401CE1FF
0x1401ce18e  mov     [rsp+6D8h+var_660], rsi
0x1401ce193  mov     rdx, rsi
0x1401ce196  mov     rcx, [rsp+6D8h+var_640]
0x1401ce19e  test    rcx, rcx
0x1401ce1a1  jz      short loc_1401CE1BB
0x1401ce1a3  mov     dl, 12h
0x1401ce1a5  call    HMValidateHandleNoSecure
0x1401ce1aa  mov     rdx, rax
0x1401ce1ad  test    rax, rax
0x1401ce1b0  jz      short loc_1401CE1BB
0x1401ce1b2  mov     rcx, [rax+18h]
0x1401ce1b6  mov     [rsp+6D8h+var_660], rcx
0x1401ce1bb  cmp     [rsp+6D8h+var_660], rsi
0x1401ce1c0  jnz     loc_1401CF224
0x1401ce1c6  mov     rax, [rbx]
0x1401ce1c9  mov     rcx, [rax+78h]
0x1401ce1cd  mov     [rsp+6D8h+var_660], rcx
0x1401ce1d2  test    rcx, rcx
0x1401ce1d5  jnz     loc_1401CF224
0x1401ce1db  mov     rax, [rax+80h]
0x1401ce1e2  mov     [rsp+6D8h+var_660], rax
0x1401ce1e7  test    rax, rax
0x1401ce1ea  jnz     loc_1401CF224
0x1401ce1f0  xor     edx, edx
0x1401ce1f2  mov     rcx, [rsp+6D8h+var_640]
0x1401ce1fa  call    ?SSQResult@RawInput@InputTraceLogging@@SAXPEAXW4SsqResult@12@@Z; InputTraceLogging::RawInput::SSQResult(void *,InputTraceLogging::RawInput::SsqResult)
0x1401ce1ff  mov     r15d, [rsp+6D8h+var_658]
0x1401ce207  mov     r8d, r12d; int
0x1401ce20a  lea     rdx, [rsp+6D8h+var_3D8]; struct tagQMSG *
0x1401ce212  mov     rcx, r14; struct tagTHREADINFO *
0x1401ce215  call    ?xxxSkipSysMsgEx@@YAPEAUtagQMSG@@PEAUtagTHREADINFO@@PEAU1@H@Z; xxxSkipSysMsgEx(tagTHREADINFO *,tagQMSG *,int)
0x1401ce21a  cmp     [rsp+6D8h+var_614], esi
0x1401ce221  jnz     loc_1401D2B05
0x1401ce227  test    r15d, r15d
0x1401ce22a  jnz     loc_1401D2B45
0x1401ce230  cmp     [rsp+6D8h+var_668+4], esi
0x1401ce234  movss   xmm6, cs:__real@3f800000
0x1401ce23c  mov     rbx, [rsp+6D8h+var_628]
0x1401ce244  mov     ecx, [rsp+6D8h+var_654]
0x1401ce24b  jz      loc_1401CDF92
0x1401ce251  jmp     loc_1401CDF2A
0x1401ce256  mov     eax, dword ptr [rsp+6D8h+var_378+4]
0x1401ce25d  test    al, 20h
0x1401ce25f  jnz     loc_1401D0C5A
  ... truncated ...
```
