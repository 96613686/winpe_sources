# xxxCreateWindowEx

- ea: `0x14013f4b4`
- end: `0x1401428cb`
- name: `xxxCreateWindowEx`
- size: `13335`
- prototype: ``
- caller_count: `8`
- callee_count: `141`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140008a0c`
- `0x140009ce0`
- `0x140086b10`
- `0x1400872e4`
- `0x1400b66fc`
- `0x14013f0ac`
- `0x14024d548`
- `0x1402b3930`

## callees

- `0x140005a18`
- `0x140005f8c`
- `0x140006354`
- `0x140007e18`
- `0x140007e50`
- `0x140007f14`
- `0x1400080f0`
- `0x140008864`
- `0x14000a36c`
- `0x14000a3ec`
- `0x14000b354`
- `0x14000b61c`
- `0x14000e5a0`
- `0x140010534`
- `0x140011878`
- `0x14001242c`
- `0x140012790`
- `0x1400138bc`
- `0x140018328`
- `0x140019430`
- `0x14001af00`
- `0x14001b0e0`
- `0x14001b230`
- `0x14001b760`
- `0x14001ba04`
- `0x14001bc58`
- `0x14001bdd4`
- `0x14001bdfc`
- `0x14001ea78`
- `0x14001ef90`
- `0x140022c54`
- `0x140023570`
- `0x1400235ec`
- `0x1400241fc`
- `0x140026568`
- `0x140026790`
- `0x140026888`
- `0x140027210`
- `0x140028324`
- `0x140028978`
- `0x140028d88`
- `0x140033b58`
- `0x140035d14`
- `0x14007ed10`
- `0x14007ee28`
- `0x140086f20`
- `0x140092310`
- `0x140092c40`
- `0x140093ec0`
- `0x140094860`

## import_xrefs

- `ntoskrnl!PsGetWin32KFilterSet` at `0x14013fb75`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x14014070d`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x14014074a`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x140140835`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x14014093e`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x14013fb75`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x14014070d`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x14014074a`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x140140835`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x14014093e`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1401418e5`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1401418e5`
- `ntoskrnl!PsGetThreadId` at `0x14013fc9b`
- `ntoskrnl!PsGetThreadId` at `0x14013fc9b`
- `ntoskrnl!PsGetProcessPeb` at `0x140140b00`
- `ntoskrnl!PsGetProcessPeb` at `0x140140b00`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14013f8ef`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140140045`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14013f8ef`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140140045`
- `win32kbase!UserFindAtom` at `0x14013fa06`
- `win32kbase!UserFindAtom` at `0x14013fa06`
- `win32kbase!ShouldSetNoOwner` at `0x14013f7b4`
- `win32kbase!ShouldSetNoOwner` at `0x14013f7b4`
- `win32kbase!?LockInitialize@tagObjLock@@QEBAXXZ` at `0x14013fc84`
- `win32kbase!?LockInitialize@tagObjLock@@QEBAXXZ` at `0x14013fd71`
- `win32kbase!?LockInitialize@tagObjLock@@QEBAXXZ` at `0x14013fc84`
- `win32kbase!?LockInitialize@tagObjLock@@QEBAXXZ` at `0x14013fd71`
- `win32kbase!?LockUnInitializeThreadCreator@tagObjLock@@QEBAXXZ` at `0x14013fd4e`
- `win32kbase!?LockUnInitializeThreadCreator@tagObjLock@@QEBAXXZ` at `0x14013ff8e`
- `win32kbase!?LockUnInitializeThreadCreator@tagObjLock@@QEBAXXZ` at `0x14013ffb0`
- `win32kbase!?LockUnInitializeThreadCreator@tagObjLock@@QEBAXXZ` at `0x14013fd4e`
- `win32kbase!?LockUnInitializeThreadCreator@tagObjLock@@QEBAXXZ` at `0x14013ff8e`
- `win32kbase!?LockUnInitializeThreadCreator@tagObjLock@@QEBAXXZ` at `0x14013ffb0`
- `win32kbase!W32GetCurrentThreadDpiHostingBehavior` at `0x14013fdcd`
- `win32kbase!W32GetCurrentThreadDpiHostingBehavior` at `0x14013fdcd`
- `win32kbase!CreateCacheDC` at `0x140141cc0`
- `win32kbase!CreateCacheDC` at `0x140141cc0`
- `win32kbase!IsImmersiveBroker` at `0x14013f703`
- `win32kbase!IsImmersiveBroker` at `0x14013f703`
- `win32kbase!CreateKernelEvent` at `0x14014176a`
- `win32kbase!CreateKernelEvent` at `0x14014176a`
- `win32kbase!IsDesktopApp` at `0x14013f6ce`
- `win32kbase!IsDesktopApp` at `0x14013f6ce`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x14013fe92`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x14014001b`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x14013fe92`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x14014001b`
- `win32kbase!GetDispInfo` at `0x14014105b`
- `win32kbase!GetDispInfo` at `0x14014105b`
- `win32kbase!_HMPheFromObject` at `0x140140802`
- `win32kbase!_HMPheFromObject` at `0x140140cf1`
- `win32kbase!_HMPheFromObject` at `0x14014282a`
- `win32kbase!_HMPheFromObject` at `0x140140802`
- `win32kbase!_HMPheFromObject` at `0x140140cf1`
- `win32kbase!_HMPheFromObject` at `0x14014282a`
- `win32kbase!GreUnlockVisRgn` at `0x140141c2b`
- `win32kbase!GreUnlockVisRgn` at `0x140141c42`
- `win32kbase!GreUnlockVisRgn` at `0x140141cd1`
- `win32kbase!GreUnlockVisRgn` at `0x140141ce8`
- `win32kbase!GreUnlockVisRgn` at `0x140141c2b`
- `win32kbase!GreUnlockVisRgn` at `0x140141c42`
- `win32kbase!GreUnlockVisRgn` at `0x140141cd1`
- `win32kbase!GreUnlockVisRgn` at `0x140141ce8`
- `win32kbase!GreLockVisRgn` at `0x140141c02`
- `win32kbase!GreLockVisRgn` at `0x140141c9d`
- `win32kbase!GreLockVisRgn` at `0x140141c02`
- `win32kbase!GreLockVisRgn` at `0x140141c9d`
- `win32kbase!IsWindowDesktopComposed` at `0x14014056e`
- `win32kbase!IsWindowDesktopComposed` at `0x140142519`
- `win32kbase!IsWindowDesktopComposed` at `0x14014056e`
- `win32kbase!IsWindowDesktopComposed` at `0x140142519`
- `win32kbase!ValidateHmonitorNoRip` at `0x14014046e`
- `win32kbase!ValidateHmonitorNoRip` at `0x140141b78`
- `win32kbase!ValidateHmonitorNoRip` at `0x14014046e`
- `win32kbase!ValidateHmonitorNoRip` at `0x140141b78`
- `win32kbase!HMAllocObject` at `0x14013fc21`
- `win32kbase!HMAllocObject` at `0x14013fc21`
- `win32kbase!HMFreeObject` at `0x14013fd5d`
- `win32kbase!HMFreeObject` at `0x14013ffbf`
- `win32kbase!HMFreeObject` at `0x14013fd5d`
- `win32kbase!HMFreeObject` at `0x14013ffbf`
- `win32kbase!ValidateHmonitor` at `0x14014102d`
- `win32kbase!ValidateHmonitor` at `0x14014107f`
- `win32kbase!ValidateHmonitor` at `0x14014102d`
- `win32kbase!ValidateHmonitor` at `0x14014107f`
- `win32kbase!HMAssignmentLock` at `0x14014055f`
- `win32kbase!HMAssignmentLock` at `0x1401414f0`
- `win32kbase!HMAssignmentLock` at `0x14014159c`
- `win32kbase!HMAssignmentLock` at `0x140141653`
- `win32kbase!HMAssignmentLock` at `0x1401417a5`
- `win32kbase!HMAssignmentLock` at `0x140141865`
- `win32kbase!HMAssignmentLock` at `0x1401420a0`
- `win32kbase!HMAssignmentLock` at `0x14014055f`
- `win32kbase!HMAssignmentLock` at `0x1401414f0`
- `win32kbase!HMAssignmentLock` at `0x14014159c`
- `win32kbase!HMAssignmentLock` at `0x140141653`
- `win32kbase!HMAssignmentLock` at `0x1401417a5`
- `win32kbase!HMAssignmentLock` at `0x140141865`
- `win32kbase!HMAssignmentLock` at `0x1401420a0`
- `win32kbase!Win32AllocPoolZInit` at `0x14013fd33`
- `win32kbase!Win32AllocPoolZInit` at `0x1401406b5`
- `win32kbase!Win32AllocPoolZInit` at `0x14013fd33`
- `win32kbase!Win32AllocPoolZInit` at `0x1401406b5`
- `win32kbase!Win32FreePool` at `0x14013ffa1`
- `win32kbase!Win32FreePool` at `0x14013ffa1`
- `win32kbase!ReferenceDwmApiPort` at `0x140142532`
- `win32kbase!ReferenceDwmApiPort` at `0x140142576`
- `win32kbase!ReferenceDwmApiPort` at `0x140142532`
- `win32kbase!ReferenceDwmApiPort` at `0x140142576`
- `WIN32K!W32GetUserSessionState` at `0x14013f9d3`
- `WIN32K!W32GetUserSessionState` at `0x140140102`
- `WIN32K!W32GetUserSessionState` at `0x140140877`
- `WIN32K!W32GetUserSessionState` at `0x140140997`
- `WIN32K!W32GetUserSessionState` at `0x1401409be`
- `WIN32K!W32GetUserSessionState` at `0x1401409de`
- `WIN32K!W32GetUserSessionState` at `0x1401409fe`
- `WIN32K!W32GetUserSessionState` at `0x140140a1e`
- `WIN32K!W32GetUserSessionState` at `0x140140a3a`
- `WIN32K!W32GetUserSessionState` at `0x140140a56`
- `WIN32K!W32GetUserSessionState` at `0x140140a72`
- `WIN32K!W32GetUserSessionState` at `0x140140a8e`
- `WIN32K!W32GetUserSessionState` at `0x1401415df`
- `WIN32K!W32GetUserSessionState` at `0x140141a1e`
- `WIN32K!W32GetUserSessionState` at `0x140142028`
- `WIN32K!W32GetUserSessionState` at `0x140142325`
- `WIN32K!W32GetUserSessionState` at `0x140142644`
- `WIN32K!W32GetUserSessionState` at `0x14014275a`
- `WIN32K!W32GetUserSessionState` at `0x14013f9d3`
- `WIN32K!W32GetUserSessionState` at `0x140140102`
- `WIN32K!W32GetUserSessionState` at `0x140140877`
- `WIN32K!W32GetUserSessionState` at `0x140140997`
- `WIN32K!W32GetUserSessionState` at `0x1401409be`
- `WIN32K!W32GetUserSessionState` at `0x1401409de`
- `WIN32K!W32GetUserSessionState` at `0x1401409fe`
- `WIN32K!W32GetUserSessionState` at `0x140140a1e`
- `WIN32K!W32GetUserSessionState` at `0x140140a3a`
- `WIN32K!W32GetUserSessionState` at `0x140140a56`
- `WIN32K!W32GetUserSessionState` at `0x140140a72`
- `WIN32K!W32GetUserSessionState` at `0x140140a8e`
- `WIN32K!W32GetUserSessionState` at `0x1401415df`
- `WIN32K!W32GetUserSessionState` at `0x140141a1e`
- `WIN32K!W32GetUserSessionState` at `0x140142028`
- `WIN32K!W32GetUserSessionState` at `0x140142325`
- `WIN32K!W32GetUserSessionState` at `0x140142644`
- `WIN32K!W32GetUserSessionState` at `0x14014275a`

## pseudocode

```c
__int64 __fastcall xxxCreateWindowEx(
        int a1,
        wchar_t *a2,
        __int64 a3,
        int *a4,
        unsigned int a5,
        LONG a6,
        LONG a7,
        int a8,
        unsigned int a9,
        struct tagWND *a10,
        __int64 a11,
        void *a12,
        __int64 a13,
        unsigned int a14,
        unsigned __int16 a15,
        char a16,
        __int64 a17)
{
  __int64 v18; // r13
  struct tagTHREADINFO *v19; // r15
  int v20; // r14d
  __int64 v21; // rcx
  __int16 v23; // cx
  ULONG_PTR v24; // rbx
  int v25; // r12d
  unsigned int v26; // edi
  _QWORD *v27; // r8
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  int v31; // edx
  __int64 CurrentProcessWin32Process; // rax
  __int64 v33; // rdx
  int v34; // eax
  __int64 v35; // rcx
  __int64 UserSessionState; // rax
  __int64 v37; // r10
  unsigned __int16 v38; // r9
  _QWORD *ClassPtr; // rax
  __int64 v40; // r8
  int v41; // r9d
  unsigned int v42; // r9d
  __int64 v43; // rax
  __int64 v44; // r14
  tagObjLock *v45; // r13
  __int64 v46; // rbx
  tagObjLock *v47; // rax
  unsigned int CurrentThreadDpiHostingBehavior; // eax
  __int64 v49; // rcx
  struct tagWND *v50; // rbx
  struct tagTHREADINFO *v51; // rax
  __int64 v52; // rax
  __int64 v53; // r8
  __int64 v54; // rcx
  int v55; // ebx
  __int64 v56; // rdx
  int v57; // ecx
  wchar_t *v58; // rcx
  __int64 v59; // rax
  __int64 v60; // rdx
  __int16 v61; // bx
  __int64 v62; // rdx
  __int64 *v63; // rax
  __int64 v64; // rcx
  __int64 v65; // rdi
  __int64 v66; // r8
  __int64 v67; // r13
  int v68; // eax
  LONG v69; // r9d
  int v70; // r10d
  struct _HEAD *v71; // rax
  LONG v72; // edx
  LONG v73; // eax
  LONG v74; // ecx
  int v75; // edx
  unsigned int v76; // eax
  struct tagMONITOR *InheritedMonitor; // rbx
  _DWORD *v78; // rax
  __int64 MessageWindow; // rax
  const struct tagWND *ThreadDesktopWindow; // rdx
  __int64 v81; // r9
  __int64 v82; // rdx
  __int64 v83; // rcx
  __int64 v84; // r8
  char v85; // r12
  __int64 v86; // rax
  int v87; // r13d
  __int64 v88; // rax
  char v89; // r12
  Scrollbar::NonClient *v90; // rcx
  Scrollbar::NonClient *v91; // rcx
  bool v92; // al
  __int64 v93; // rdx
  int v94; // r8d
  unsigned int v95; // ecx
  unsigned int ClientExtraBytesTotalSize; // eax
  __int64 v97; // rdi
  _QWORD *v98; // rdx
  __int64 v99; // rcx
  int v100; // ebx
  __int64 v101; // rcx
  __int64 v102; // rdx
  __int64 v103; // rcx
  __int16 v104; // di
  __int64 v105; // rcx
  __int64 v106; // rcx
  __int64 v107; // rcx
  __int64 v108; // rcx
  __int64 v109; // rcx
  __int64 v110; // rcx
  __int64 v111; // rcx
  __int16 v112; // bx
  unsigned __int16 v113; // bx
  char v114; // di
  int v115; // eax
  __int64 v116; // rcx
  int v117; // edx
  int v118; // r12d
  int v119; // edi
  unsigned int v120; // ecx
  __int64 v121; // rdx
  __int64 v122; // r8
  __int64 v123; // r9
  int v124; // r8d
  int v125; // r9d
  __int64 v126; // rbx
  __int16 v127; // di
  __int64 v128; // rdx
  int v129; // eax
  __int64 v130; // r8
  __int64 v131; // rcx
  struct tagMONITOR *v132; // rax
  unsigned int v133; // edx
  int v134; // ecx
  __int16 v135; // ax
  _QWORD *v136; // r8
  unsigned int v137; // eax
  int *MonitorRect; // rax
  int v139; // r8d
  int v140; // r9d
  int v141; // r10d
  int v142; // eax
  __int64 v143; // rbx
  __int64 v144; // r8
  __int64 v145; // rcx
  unsigned int WindowCloakStateComponentUIAware; // r12d
  struct _HEAD *v147; // rcx
  struct _HEAD *v148; // rcx
  __int64 NonChildAncestor; // rbx
  __int64 v150; // rdi
  __int64 v151; // rcx
  __int64 v152; // rcx
  struct tagTHREADINFO *v153; // rdx
  int IsEnabledDeviceUsageNoInline; // eax
  int v155; // ecx
  bool v156; // zf
  unsigned int v157; // eax
  int v158; // edx
  struct tagTHREADINFO *v159; // rdi
  __int64 KernelEvent; // rax
  __int64 v161; // rdi
  struct tagWND **v162; // r13
  __int64 v163; // rdx
  __int64 v164; // rbx
  NTSTATUS v165; // eax
  ULONG v166; // eax
  __int64 v167; // rcx
  struct tagTHREADINFO **v168; // rax
  __int64 v169; // rax
  struct tagWND *v170; // r9
  __int64 v171; // rax
  int v172; // eax
  int v173; // eax
  __int64 v174; // rax
  struct tagMONITOR *v175; // rbx
  __int64 v176; // rcx
  __int64 *v177; // rbx
  __int64 StyleWindow; // rbx
  unsigned int v179; // edx
  int v180; // ebx
  __int64 v181; // r9
  struct tagTHREADINFO *v182; // rdx
  unsigned __int128 v183; // rax
  unsigned int v184; // ecx
  __int64 v185; // rcx
  struct _LARGE_UNICODE_STRING *StrName; // rax
  struct tagWND **v187; // rbx
  struct tagWND *DefaultImeWindow; // rax
  int v189; // ecx
  struct tagWND *v190; // rcx
  unsigned __int64 CompositeAppFrameWindowOrSelf; // rbx
  __int64 v192; // rax
  int v193; // ebx
  __int64 v194; // rcx
  struct tagWND *v195; // rdx
  const struct tagWND *v196; // rax
  __int64 TopMostInsertAfter; // rax
  __int64 *v198; // rbx
  __int64 v199; // r9
  int v200; // edx
  int v201; // r8d
  void *v202; // rax
  void *v203; // rax
  __int64 v204; // rcx
  __int64 v205; // r8
  __int64 v206; // r9
  __int64 DesktopWindow; // rax
  __int64 v208; // rdx
  unsigned int v209; // ebx
  __int64 *v210; // rdi
  char v211; // cl
  __int64 v212; // rdx
  __int64 v213; // rcx
  __int64 v214; // rax
  _QWORD *v215; // rbx
  __int64 v216; // rax
  __int64 v217; // rbx
  unsigned int v218; // [rsp+50h] [rbp-2D8h]
  unsigned __int64 v219; // [rsp+54h] [rbp-2D4h]
  __int16 v220; // [rsp+5Ch] [rbp-2CCh]
  int v221; // [rsp+5Ch] [rbp-2CCh]
  __int64 v222; // [rsp+68h] [rbp-2C0h]
  unsigned __int16 v223; // [rsp+70h] [rbp-2B8h]
  int v224; // [rsp+70h] [rbp-2B8h]
  unsigned int v225; // [rsp+74h] [rbp-2B4h]
  struct tagWND *v226; // [rsp+78h] [rbp-2B0h]
  int v227; // [rsp+8Ch] [rbp-29Ch]
  int v228; // [rsp+8Ch] [rbp-29Ch]
  _QWORD v229[2]; // [rsp+90h] [rbp-298h] BYREF
  _QWORD *v230; // [rsp+A0h] [rbp-288h]
  wchar_t *Str1; // [rsp+A8h] [rbp-280h]
  int *v232; // [rsp+B0h] [rbp-278h]
  int v233; // [rsp+B8h] [rbp-270h]
  int Atom; // [rsp+C0h] [rbp-268h]
  int v235; // [rsp+C4h] [rbp-264h]
  __int64 *v236; // [rsp+C8h] [rbp-260h]
  struct tagRECT v237; // [rsp+D0h] [rbp-258h] BYREF
  int v238; // [rsp+E0h] [rbp-248h]
  int v239; // [rsp+E4h] [rbp-244h]
  _QWORD v240[2]; // [rsp+E8h] [rbp-240h] BYREF
  struct _HEAD *v241; // [rsp+F8h] [rbp-230h]
  ULONG_PTR v242[2]; // [rsp+100h] [rbp-228h] BYREF
  unsigned __int16 v243; // [rsp+110h] [rbp-218h]
  __int64 v244; // [rsp+118h] [rbp-210h]
  void *v245; // [rsp+120h] [rbp-208h]
  ULONG_PTR v246[2]; // [rsp+128h] [rbp-200h] BYREF
  __int64 v247; // [rsp+138h] [rbp-1F0h]
  __int64 v248; // [rsp+140h] [rbp-1E8h]
  __int64 v249; // [rsp+148h] [rbp-1E0h] BYREF
  __int64 v250; // [rsp+150h] [rbp-1D8h]
  struct tagWND *v251; // [rsp+158h] [rbp-1D0h]
  _QWORD *v252; // [rsp+160h] [rbp-1C8h]
  ULONG_PTR v253[2]; // [rsp+170h] [rbp-1B8h] BYREF
  __int128 v254; // [rsp+180h] [rbp-1A8h] BYREF
  int v255; // [rsp+190h] [rbp-198h]
  int v256; // [rsp+1BCh] [rbp-16Ch]
  _QWORD v257[2]; // [rsp+1D0h] [rbp-158h] BYREF
  struct _HEAD *v258; // [rsp+1E0h] [rbp-148h]
  __int64 v259; // [rsp+1E8h] [rbp-140h]
  unsigned int v260; // [rsp+1F0h] [rbp-138h]
  int v261; // [rsp+1F4h] [rbp-134h]
  LONG v262; // [rsp+1F8h] [rbp-130h]
  unsigned int v263; // [rsp+1FCh] [rbp-12Ch]
  unsigned int v264; // [rsp+200h] [rbp-128h]
  __int64 v265; // [rsp+208h] [rbp-120h]
  wchar_t *v266; // [rsp+210h] [rbp-118h]
  unsigned int v267; // [rsp+218h] [rbp-110h]
  int v268; // [rsp+220h] [rbp-108h]
  int v269; // [rsp+224h] [rbp-104h]
  __int64 v270; // [rsp+228h] [rbp-100h]
  __int128 v271; // [rsp+230h] [rbp-F8h] BYREF
  wchar_t *v272; // [rsp+240h] [rbp-E8h]
  struct tagTHREADINFO **v273; // [rsp+248h] [rbp-E0h]
  _QWORD *v274; // [rsp+250h] [rbp-D8h]
  ULONG_PTR BugCheckParameter3[2]; // [rsp+258h] [rbp-D0h] BYREF
  int v276; // [rsp+268h] [rbp-C0h]
  int *v277; // [rsp+270h] [rbp-B8h] BYREF
  __int128 v278; // [rsp+280h] [rbp-A8h] BYREF
  __int64 v279; // [rsp+290h] [rbp-98h]
  _BYTE v280[40]; // [rsp+2A0h] [rbp-88h] BYREF
  __int128 v281; // [rsp+2C8h] [rbp-60h] BYREF
  __int128 v282; // [rsp+2D8h] [rbp-50h] BYREF

  v277 = a4;
  v272 = a2;
  v238 = a1;
  v218 = a1;
  v233 = a1;
  Str1 = a2;
  v248 = a3;
  v232 = a4;
  v18 = (__int64)a10;
  v226 = a10;
  v244 = (__int64)a10;
  v245 = a12;
  *(_QWORD *)&v237.left = a13;
  SmartObjStackRef<tagCLS>::SmartObjStackRef<tagCLS>(v229);
  v282 = 0;
  v281 = 0;
  memset_0(v257, 0, 0x70u);
  v19 = PtiCurrent();
  Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(v246);
  v278 = 0;
  v279 = 0;
  v230 = (_QWORD *)((char *)v19 + 456);
  v20 = *(_DWORD *)(*((_QWORD *)v19 + 57) + 12LL);
  v254 = 0;
  SmartObjStackRef<tagMENU>::SmartObjStackRef<tagMENU>(v240, a11);
  AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)&v249);
  if ( (*(_DWORD *)(*((_QWORD *)v19 + 57) + 12LL) & 0x10000000) == 0 && !(unsigned int)RegisterIconTitleClass() )
    goto LABEL_3;
  if ( a1 < 0 )
  {
    v218 = a1 & 0x7FFFFFFF;
    v233 = a1 & 0x7FFFFFFF;
  }
  v23 = 800;
  if ( a1 >= 0 )
    v23 = 0;
  v223 = v23;
  v24 = *((_QWORD *)v19 + 61);
  v252 = (_QWORD *)v24;
  v253[0] = v24;
  if ( a10 )
  {
    if ( *((_QWORD *)a10 + 3) != v24 )
      goto LABEL_3;
  }
  v25 = 0;
  if ( (a16 & 1) != 0 )
  {
    if ( (unsigned int)IsDesktopApp(*v230) )
    {
LABEL_45:
      v21 = 5;
      goto LABEL_4;
    }
    v25 = 1;
  }
  v239 = a16 & 2;
  if ( (a16 & 2) != 0 && !(unsigned int)IsImmersiveBroker(*v230) )
    goto LABEL_45;
  v26 = a14;
  if ( !a14 )
  {
LABEL_26:
    v27 = v230;
    goto LABEL_27;
  }
  if ( !(unsigned int)IsValidBand(a14) || a14 == 15 )
    goto LABEL_3;
  v27 = v230;
  v28 = *(_QWORD *)(*v230 + 808LL);
  if ( (v28 & 0x30) == 0x10 && (v28 & 0x200) == 0 && a14 == 1 && !v25 )
  {
    if ( !(unsigned int)HasMessageRootWindow(a10) )
      goto LABEL_3;
    goto LABEL_26;
  }
LABEL_27:
  v220 = HIWORD(a5) & 0xC000;
  v256 = (HIWORD(a5) & 0xC000) == 0x4000;
  if ( (HIWORD(a5) & 0xC000) != 0x4000 )
  {
    if ( (unsigned int)ShouldSetNoOwner(*v27, a10) )
      v18 = 0;
    v226 = (struct tagWND *)v18;
    v244 = v18;
  }
  if ( !v18 || (unsigned int)IsDesktopWindow(v18) )
  {
    if ( !a14 )
    {
      if ( (unsigned int)IsImmersiveAppIORestricted(*v230) )
      {
        v25 = 1;
        v26 = 15;
      }
      else if ( (*(_BYTE *)(v30 + 808) & 2) != 0 && (v218 & 8) != 0 )
      {
        v26 = 2;
      }
      else
      {
        v26 = 1;
      }
    }
  }
  else
  {
    v29 = *(_QWORD *)(v18 + 40);
    if ( a14 )
    {
      if ( a14 != *(_DWORD *)(v29 + 236) )
        goto LABEL_3;
    }
    else
    {
      v26 = *(_DWORD *)(v29 + 236);
    }
    v25 = *(_BYTE *)(v29 + 232) & 0x40;
  }
  if ( !(unsigned __int8)IsValidBandForProcess(*v230, v26, v18) )
    goto LABEL_45;
  v31 = v218;
  if ( (v218 & 0x400000) == 0 )
  {
    if ( v18 )
    {
      if ( v220 != 0x4000 || (*(_BYTE *)(*(_QWORD *)(v18 + 40) + 26LL) & 0x50) != 0x40 )
        goto LABEL_58;
      v31 = v218 | 0x400000;
    }
    else
    {
      if ( ((unsigned __int64)Str1 & 0xFFFFFFFFFFFF0000uLL) == 0 && (_WORD)Str1 == 0x8002 )
        goto LABEL_58;
      CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
      v33 = CurrentProcessWin32Process;
      if ( CurrentProcessWin32Process )
        v33 = -(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0) & CurrentProcessWin32Process;
      v34 = *(_DWORD *)(v33 + 816);
      v31 = v218;
      if ( (v34 & 1) == 0 )
        goto LABEL_58;
      v31 = v218 | 0x400000;
    }
    v233 = v31;
    v218 = v31;
  }
LABEL_58:
  if ( (v31 & 0x2200000) == 0x2200000 )
    goto LABEL_3;
  if ( *((_QWORD *)v19 + 78) && !(unsigned int)CheckGrantedAccess(*((unsigned int *)v19 + 232), 2) )
    goto LABEL_5;
  if ( v220 == 0x4000 )
  {
    if ( !v18 )
    {
      v21 = 1406;
LABEL_4:
      UserSetLastError(v21);
LABEL_5:
      AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)&v249);
LABEL_6:
      SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(v240);
      Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)v246);
      SmartObjStackRef<tagPOPUPMENU>::~SmartObjStackRef<tagPOPUPMENU>(v229);
      return 0;
    }
    if ( !(unsigned int)ValidateParentDepth(0, v18) )
    {
LABEL_3:
      v21 = 87;
      goto LABEL_4;
    }
  }
  v227 = v20 & 0x2000;
  v247 = v18;
  while ( 1 )
  {
    if ( (v248 & 0xFFFFFFFFFFFF0000uLL) != 0 )
    {
      AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)v242);
      UserSessionState = W32GetUserSessionState(v35);
      if ( (int)RtlStringCchCopyW(
                  (unsigned __int16 *)(UserSessionState + 41556),
                  0x100u,
                  *(const unsigned __int16 **)(v248 + 8)) < 0 )
      {
        Atom = 0;
        v227 = 1;
        v255 = 1;
      }
      else
      {
        Atom = (unsigned __int16)UserFindAtom(v37);
      }
      AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v242);
    }
    else
    {
      v38 = v248;
      Atom = v248;
    }
    if ( v38 )
    {
      ClassPtr = (_QWORD *)GetClassPtr(v38, *v230, v245);
      if ( ClassPtr )
        break;
    }
LABEL_107:
    if ( v227
      || (*(_DWORD *)(*((_QWORD *)PtiCurrent() + 57) + 12LL) & 0x2000) != 0
      || (((unsigned __int64)Str1 & 0xFFFFFFFFFFFF0000uLL) == 0
        ? (v58 = Str1)
        : (v58 = (wchar_t *)*((_QWORD *)Str1 + 1)),
          !(unsigned int)RegisterDefaultClass(v58)) )
    {
      v21 = 1407;
      goto LABEL_4;
    }
    v227 = 1;
    v24 = (ULONG_PTR)v252;
  }
  SmartObjStackRefBase<tagCLS>::operator=(v229, *ClassPtr);
  if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)v229[0] + 8LL) + 6LL) & 1) != 0 && (unsigned int)PsGetWin32KFilterSet() == 5 )
    goto LABEL_5;
  v243 = a15;
  if ( (unsigned int)NeedsWindowEdge(a5, v218, a15 >= 0x400u) )
    v42 = v41 | 0x100;
  else
    v42 = v41 & 0xFFFFFEFF;
  v233 = v42;
  v218 = v42;
  if ( (_InterlockedCompareExchange((volatile signed __int32 *)v19 + 130, 0, 0) & 1) != 0 )
  {
    v235 = 0x20000;
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 853);
  }
  LOBYTE(v40) = 1;
  v43 = HMAllocObject(v19, v24, v40, 416);
  v44 = v43;
  v251 = (struct tagWND *)v43;
  if ( !v43 )
  {
    if ( (unsigned int)UserGetLastError() == 8 )
      TraceLoggingCreateWindowFailed(
        1u,
        (((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
       * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64);
    goto LABEL_5;
  }
  v45 = (tagObjLock *)(v43 + 56);
  tagObjLock::LockInitialize((tagObjLock *)(v43 + 56));
  v46 = v44 + 40;
  v222 = v44 + 40;
  *(_DWORD *)(*(_QWORD *)(v44 + 40) + 328LL) = (unsigned int)PsGetThreadId(*(PETHREAD *)v19);
  *(_DWORD *)(*(_QWORD *)(v44 + 40) + 332LL) = *(_DWORD *)(*v230 + 56LL);
  *(_QWORD *)(v44 + 328) = v44 + 320;
  *(_QWORD *)(v44 + 320) = v44 + 320;
  *(_QWORD *)(v44 + 344) = v44 + 336;
  *(_QWORD *)(v44 + 336) = v44 + 336;
  *(_QWORD *)(v44 + 360) = v44 + 352;
  *(_QWORD *)(v44 + 352) = v44 + 352;
  *(_QWORD *)(v44 + 408) = v44 + 400;
  *(_QWORD *)(v44 + 400) = v44 + 400;
  *(_DWORD *)(v44 + 396) = 5;
  *(_DWORD *)(v44 + 392) = 1;
  v47 = (tagObjLock *)Win32AllocPoolZInit(32, 1752200021);
  *(_QWORD *)(v44 + 144) = v47;
  if ( !v47 )
  {
    tagObjLock::LockUnInitializeThreadCreator(v45);
    HMFreeObject(v44);
    goto LABEL_5;
  }
  tagObjLock::LockInitialize(v47);
  v273 = (struct tagTHREADINFO **)(v44 + 16);
  if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v44 + 16) + 456LL) + 808LL) & 0x1000000) != 0 )
    *(_DWORD *)(v44 + 384) |= 1u;
  *(_QWORD *)(*(_QWORD *)v46 + 296LL) = 0;
  *(_QWORD *)(v44 + 280) = 0;
  *(_DWORD *)(v44 + 180) = -1;
  *(_QWORD *)(*(_QWORD *)v46 + 168LL) = 0;
  CurrentThreadDpiHostingBehavior = W32GetCurrentThreadDpiHostingBehavior();
  v49 = CurrentThreadDpiHostingBehavior;
  *(_DWORD *)(*(_QWORD *)v46 + 292LL) = CurrentThreadDpiHostingBehavior;
  if ( v220 == 0x4000 )
  {
    if ( v226 && v226 != (struct tagWND *)GetThreadDesktopWindow(0) )
    {
      v50 = 0;
      v51 = PtiCurrent();
      if ( v51 )
      {
        v52 = *((_QWORD *)v51 + 61);
        if ( v52 )
          v50 = *(struct tagWND **)(v52 + 112);
      }
      if ( v226 != v50 )
      {
        v49 = *(_QWORD *)(*((_QWORD *)v226 + 2) + 456LL);
        if ( *v230 == v49 && !IsChildWindowDpiIsolationEnabled(0, v226) )
        {
          v53 = v247;
          v54 = *(_QWORD *)v222;
          *(_DWORD *)(v54 + 288) = *(_DWORD *)(*(_QWORD *)(v247 + 40) + 288LL);
          v55 = *(_DWORD *)(*(_QWORD *)(v53 + 40) + 288LL);
          if ( (((unsigned __int8)v55 ^ (unsigned __int8)W32GetCurrentThreadDpiAwarenessContext(v54)) & 0xF) != 0 )
            TraceChildWindowDpiTelemetry(v44, v226, 0);
          v46 = v44 + 40;
          goto LABEL_100;
        }
      }
    }
    v46 = v44 + 40;
  }
  *(_DWORD *)(*(_QWORD *)v46 + 288LL) = W32GetCurrentThreadDpiAwarenessContext(v49);
  if ( (*(_DWORD *)(*(_QWORD *)v46 + 288LL) & 0x4000000F) == 0 )
  {
    v59 = PsGetCurrentProcessWin32Process();
    v60 = v59;
    if ( v59 )
      v60 = -(__int64)(*(_QWORD *)v59 != 0) & v59;
    if ( (*(_DWORD *)(v60 + 12) & 0x20000000) != 0 )
      *(_DWORD *)(*(_QWORD *)v46 + 288LL) |= 0x40000000u;
  }
LABEL_100:
  v56 = *(_QWORD *)v46;
  v57 = *(_DWORD *)(*(_QWORD *)v46 + 288LL);
  if ( (v57 & 0xF) == 2 && (v57 & 0xF0) == 0x20 )
    *(_DWORD *)(v44 + 380) |= 0x180000u;
  if ( (*(_BYTE *)(v56 + 288) & 0xF) == 3 )
    *(_DWORD *)(v44 + 380) |= 0x80000u;
  v274 = (_QWORD *)(v44 + 136);
  tagWND::SharedMixedObjectPointerFieldpcls<tagCLS>::operator=(v44 + 136, *(_QWORD *)v229[0]);
  *(_DWORD *)(*(_QWORD *)v46 + 28LL) = a5 & 0xEFFFFFFF;
  *(_DWORD *)(*(_QWORD *)v46 + 24LL) = v218 & 0xFDF7FFFF;
  *(_DWORD *)(*(_QWORD *)v46 + 200LL) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v229[0] + 8LL) + 80LL);
  *(_DWORD *)(*(_QWORD *)v46 + 248LL) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v229[0] + 8LL) + 84LL);
  if ( !(unsigned int)ReferenceClass(*(_QWORD *)v229[0], v44) )
    goto LABEL_106;
  v236 = (__int64 *)v46;
  SmartObjStackRefBase<tagCLS>::operator=(v229, *v274);
  if ( !(unsigned int)ClassLock(*(_QWORD *)v229[0], &v278) )
  {
    DereferenceClass(*v230, v44);
LABEL_106:
    tagObjLock::LockUnInitializeThreadCreator(*(tagObjLock **)(v44 + 144));
    Win32FreePool(*(void **)(v44 + 144));
    tagObjLock::LockUnInitializeThreadCreator(v45);
    HMFreeObject(v44);
    goto LABEL_107;
  }
  v228 = 0;
  *(_QWORD *)(*(_QWORD *)v46 + 224LL) = a17;
  v61 = *(_WORD *)(*(_QWORD *)(*(_QWORD *)v229[0] + 8LL) + 2LL);
  if ( v61 == *(_WORD *)(*(_QWORD *)(W32GetUserSessionState(*(_QWORD *)v229[0]) + 19704) + 868LL) )
  {
    v62 = v44 + 40;
    *(_QWORD *)(*(_QWORD *)v222 + 208LL) = 0;
  }
  else
  {
    v63 = (__int64 *)*((_QWORD *)v19 + 103);
    v64 = 0;
    if ( v63 )
      v64 = *v63;
    v62 = v44 + 40;
    *(_QWORD *)(*(_QWORD *)v222 + 208LL) = v64;
  }
  *(_DWORD *)(*(_QWORD *)v62 + 236LL) = v26;
  v65 = v44 + 40;
  v66 = *(_QWORD *)v222;
  v67 = (__int64)v226;
  if ( *(_DWORD *)(*(_QWORD *)v222 + 236LL) == 1 )
    v68 = 0;
  else
    v68 = IsTopLevelParent(v226);
  if ( v68 )
    *(_DWORD *)(v66 + 24) |= 8u;
  if ( v25 )
    SetOrClrWF(1, v44, 55360, 0);
  v253[0] = (ULONG_PTR)v19 + 932;
  ++*((_DWORD *)v19 + 233);
  memset_0(v257, 0, 0x70u);
  v267 = v218;
  v257[1] = v245;
  if ( ((unsigned __int64)Str1 & 0xFFFFFFFFFFFF0000uLL) != 0 )
  {
    if ( v238 >= 0 )
    {
      v266 = (wchar_t *)*((_QWORD *)Str1 + 1);
      v271 = *(_OWORD *)v272;
    }
    else
    {
      v266 = *(wchar_t **)(*(_QWORD *)v229[0] + 104LL);
      if ( ((unsigned __int64)v266 & 0xFFFFFFFFFFFF0000uLL) != 0 )
        RtlInitLargeAnsiString(&v271);
    }
  }
  else
  {
    v266 = Str1;
  }
  if ( v232 )
  {
    v265 = *((_QWORD *)v232 + 1);
    v268 = *v277;
    v269 = v277[1];
    v270 = *((_QWORD *)v277 + 1);
  }
  v264 = a5;
  v69 = a6;
  v219 = __PAIR64__(a7, a6);
  v263 = a6;
  v262 = a7;
  v70 = a8;
  LODWORD(Str1) = a8;
  v261 = a8;
  v225 = a9;
  v260 = a9;
  if ( v226 )
    v259 = *(_QWORD *)v226;
  else
    v259 = 0;
  if ( v220 == 0x4000 )
  {
    v71 = v241;
    if ( !v241 )
      v71 = *(struct _HEAD **)v240[0];
    v258 = v71;
    *(_DWORD *)(*(_QWORD *)v222 + 24LL) |= *(_DWORD *)(*(_QWORD *)(v247 + 40) + 24LL) & 0xC4000000;
    v72 = a7;
  }
  else if ( (unsigned __int8)SmartObjStackRef<tagMENU>::operator==(v240) )
  {
    v258 = 0;
  }
  else
  {
    v258 = **(struct _HEAD ***)v240[0];
  }
  v257[0] = *(_QWORD *)&v237.left;
  *(_QWORD *)&v237.left = 0;
  if ( v69 == 0x80000000 || (v73 = v69, v69 == 0x8000) )
    v73 = 0;
  v237.left = v73;
  if ( v72 == 0x80000000 || v72 == 0x8000 )
  {
    v74 = 0;
    v237.top = 0;
  }
  else
  {
    v74 = v72;
    v237.top = v72;
  }
  if ( v70 == 0x80000000 || (v75 = v70, v70 == 0x8000) )
    v75 = 0;
  v237.right = v75 + v73;
  if ( a9 == 0x80000000 || (v76 = a9, a9 == 0x8000) )
    v76 = 0;
  v237.bottom = v74 + v76;
  InheritedMonitor = (struct tagMONITOR *)GetInheritedMonitor((struct tagWND *)v44);
  if ( InheritedMonitor )
  {
    v235 = 1;
  }
  else
  {
    v235 = 0;
    if ( v226 )
      InheritedMonitor = (struct tagMONITOR *)ValidateHmonitorNoRip(*(_QWORD *)(*(_QWORD *)(v247 + 40) + 256LL));
  }
  if ( !InheritedMonitor )
    InheritedMonitor = (struct tagMONITOR *)MonitorFromRect(&v237, 2);
  UpdateWindowMonitorAndDpiInfoHelper((struct tagWND *)v44, InheritedMonitor);
  *(_WORD *)(*(_QWORD *)v222 + 286LL) = 0;
  *(_QWORD *)(v44 + 296) = 0;
  if ( v220 != 0x4000 || IsDpiBoundaryBetweenWindows((const struct tagWND *)v44, v226) )
    UpdateTopLevelWindowDPITransform(v44, InheritedMonitor);
  if ( v220 == 0x4000 )
  {
    if ( v226 )
    {
      *(_WORD *)(*(_QWORD *)v222 + 286LL) = *(_WORD *)(*(_QWORD *)(v247 + 40) + 286LL);
      v78 = (_DWORD *)*((_QWORD *)v226 + 37);
      if ( v78 )
      {
        *(_QWORD *)(v44 + 296) = v78;
        ++*v78;
      }
    }
  }
  v252 = (_QWORD *)(v44 + 24);
  if ( *(_QWORD *)(v44 + 24) )
  {
    MessageWindow = GetMessageWindow(v44);
    *(_OWORD *)v242 = *(_OWORD *)LockPointer(&v277, v44 + 104, MessageWindow);
    HMAssignmentLock(v242, 0);
  }
  if ( (unsigned int)IsWindowDesktopComposed(v44) )
  {
    ThreadDesktopWindow = v226;
    if ( v220 != 0x4000 && (!v226 || v226 != *(struct tagWND **)(*((_QWORD *)v226 + 3) + 112LL)) )
      ThreadDesktopWindow = (const struct tagWND *)GetThreadDesktopWindow(0);
    DwmWindowCreate((struct tagWND *)v44, ThreadDesktopWindow, &v237);
  }
  *(_QWORD *)(*(_QWORD *)v222 + 32LL) = v245;
  *(_QWORD *)(*(_QWORD *)v222 + 120LL) = MapClientNeuterToClientPfn(*(_QWORD *)v229[0], 0, v223);
  v81 = 1;
  v82 = v44;
  if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)v229[0] + 8LL) + 6LL) & 1) != 0 )
  {
    SetOrClrWF(1, v44, 516, 1);
    v83 = 1;
    v82 = v44;
    v84 = 55812;
    v81 = 0;
  }
  else
  {
    v83 = 0;
    v84 = 516;
  }
  SetOrClrWF(v83, v82, v84, v81);
  if ( (*(_BYTE *)(*(_QWORD *)v222 + 30LL) & 0x30) != 0 && (*(_BYTE *)(*(_QWORD *)v222 + 234LL) & 4) != 0 )
  {
    LODWORD(v232) = 0x20000;
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 1206);
  }
  AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)&v249);
  Win32HMThreadLockAlways<tagHOOK>::Win32HMThreadLockAlways<tagHOOK>(BugCheckParameter3, v19, v44);
  v85 = *(_BYTE *)(*(_QWORD *)v222 + 18LL);
  if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v229[0] + 8LL) + 84LL) )
  {
    v86 = Win32AllocPoolZInit(*(unsigned int *)(*(_QWORD *)(*(_QWORD *)v229[0] + 8LL) + 84LL), 1937208149);
    *(_QWORD *)(v44 + 280) = v86;
    if ( !v86 )
    {
      v87 = 5;
      v88 = *(_QWORD *)v222;
      goto LABEL_192;
    }
  }
  v89 = v85 & 4;
  LODWORD(v232) = 0;
  if ( (unsigned int)PsGetWin32KFilterSet() != 5 )
  {
LABEL_196:
    if ( v89 )
      goto LABEL_205;
    if ( (unsigned int)PsGetWin32KFilterSet() == 5 )
    {
      *(_DWORD *)(*(_QWORD *)v222 + 200LL) = (*(_DWORD *)(*(_QWORD *)v222 + 200LL) + 7) & 0xFFFFFFF8;
    }
    else
    {
      if ( !(unsigned int)Feature_UserModeNonClientScrollBars2__private_IsEnabledDeviceUsageNoInline()
        || !Scrollbar::NonClient::UserModeSupportsUserModeScrollBars(v90) )
      {
        goto LABEL_205;
      }
      v92 = Scrollbar::NonClient::UserModeSupportsPartitionedExtraBytes(v91);
      v93 = *(_QWORD *)v222;
      v94 = *(_DWORD *)(*(_QWORD *)v222 + 200LL);
      v95 = (v94 + 7) & 0xFFFFFFF8;
      if ( v92 )
      {
        *(_DWORD *)(v93 + 336) = v95 - v94;
        *(_DWORD *)(*(_QWORD *)v222 + 336LL) += 48;
        goto LABEL_205;
      }
      *(_DWORD *)(v93 + 200) = v95;
    }
    *(_DWORD *)(*(_QWORD *)v222 + 200LL) += 48;
    goto LABEL_205;
  }
  if ( !v89 )
  {
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 1245);
    goto LABEL_196;
  }
LABEL_205:
  ClientExtraBytesTotalSize = GetClientExtraBytesTotalSize((const struct tagWND *)v44);
  if ( ClientExtraBytesTotalSize )
  {
    v97 = xxxClientAllocWindowClassExtraBytes(ClientExtraBytesTotalSize);
    if ( !v97 )
    {
      v87 = 2;
      v88 = *(_QWORD *)v222;
LABEL_192:
      *(_QWORD *)(v88 + 120) = 0;
      SetOrClrWF(1, v44, 516, 1);
LABEL_476:
      v180 = *(_BYTE *)(*v236 + 31) & 0x10;
      if ( v228 )
        Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)v246);
      SetOrClrWF(1, v44, 1152, 1);
      SetOrClrWF(1, v44, 896, 1);
      if ( v180 )
        SetVisible(v44, 0);
      if ( *(_QWORD *)(v44 + 104) )
      {
        if ( v180 )
          zzzLockDisplayAreaAndInvalidateDCCache(*(_QWORD *)(v44 + 104), 16);
        if ( (*(_BYTE *)(*v236 + 31) & 0xC0) == 0x40 && !(unsigned int)IsTopLevelWindow(v44) )
        {
          v182 = *(struct tagTHREADINFO **)(v181 + 16);
          if ( v19 != v182 )
            zzzAttachThreadInput(*v273, v182);
        }
        UnlinkWindow((struct tagWND *)v44);
      }
      ClassUnlock(*(struct tagCLS **)v229[0]);
      xxxFreeWindow(v19, (struct tagWND *)v44);
      if ( v87 )
      {
        v183 = ((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
             * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8);
        v184 = v87;
        goto LABEL_542;
      }
      goto LABEL_543;
    }
    if ( (unsigned int)IsWindowBeingDestroyed(v44)
      || (*(_BYTE *)(_HMPheFromObject(v44) + 25) & 1) != 0
      || *(_QWORD *)(*(_QWORD *)v222 + 296LL) )
    {
      UserSetLastError(87);
      *(_QWORD *)(*(_QWORD *)v222 + 120LL) = 0;
      SetOrClrWF(1, v44, 516, 1);
      v87 = 0;
      goto LABEL_476;
    }
    *(_QWORD *)(*(_QWORD *)v222 + 296LL) = v97;
    v65 = v44 + 40;
  }
  if ( (unsigned int)PsGetWin32KFilterSet() != 5 || v89 )
  {
    v100 = v238;
  }
  else
  {
    v98 = (_QWORD *)GETCLIENTWNDINFO(v44);
    v99 = *(_QWORD *)(*v236 + 120);
    *v98 = v99;
    v100 = v238;
    v101 = *(_QWORD *)(W32GetUserSessionState(v99) + 19704);
    if ( v100 >= 0 )
      v102 = *(_QWORD *)(v101 + 768);
    else
      v102 = *(_QWORD *)(v101 + 576);
    *(_QWORD *)(*(_QWORD *)v65 + 120LL) = v102;
  }
  if ( *(_QWORD *)(*(_QWORD *)v229[0] + 80LL)
    && !*(_QWORD *)(*(_QWORD *)v229[0] + 112LL)
    && (unsigned int)PsGetWin32KFilterSet() != 5 )
  {
    xxxCreateClassSmIcon(v229);
  }
  SetOrClrWF(1, v44, v223, 1);
  if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)v229[0] + 8LL) + 6LL) & 2) != 0 )
    goto LABEL_235;
  if ( v100 < 0 )
  {
    v103 = *(_QWORD *)(W32GetUserSessionState(*(_QWORD *)v229[0]) + 19704);
    v104 = Atom;
    if ( (_WORD)Atom == *(_WORD *)(v103 + 868)
      || (v105 = *(_QWORD *)(W32GetUserSessionState(v103) + 19704), v104 == *(_WORD *)(v105 + 878))
      || (v106 = *(_QWORD *)(W32GetUserSessionState(v105) + 19704), v104 == *(_WORD *)(v106 + 882))
      || (v107 = *(_QWORD *)(W32GetUserSessionState(v106) + 19704), v104 == *(_WORD *)(v107 + 904))
      || (v108 = *(_QWORD *)(W32GetUserSessionState(v107) + 19704), v104 == *(_WORD *)(v108 + 870))
      || (v109 = *(_QWORD *)(W32GetUserSessionState(v108) + 19704), v104 == *(_WORD *)(v109 + 874))
      || (v110 = *(_QWORD *)(W32GetUserSessionState(v109) + 19704), v104 == *(_WORD *)(v110 + 880))
      || (v111 = *(_QWORD *)(W32GetUserSessionState(v110) + 19704), v104 == *(_WORD *)(v111 + 898))
      || v104 == *(_WORD *)(*(_QWORD *)(W32GetUserSessionState(v111) + 19704) + 872LL) )
    {
LABEL_235:
      SetOrClrWF(1, v44, 520, 1);
    }
  }
  if ( ((*(_BYTE *)(*(_QWORD *)(*(_QWORD *)v229[0] + 8LL) + 6LL) & 2) != 0 || v100 < 0)
    && v220 != 0x4000
    && (*(_QWORD *)&v237.left = PsGetProcessPeb(**((_QWORD **)*v273 + 57))) != 0 )
  {
    v112 = *(_WORD *)(*(_QWORD *)&v237.left + 844LL);
    if ( v112 == -535 )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 1404);
    if ( v112 == -10600 )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 1405);
    v113 = a15;
    v114 = v218;
  }
  else
  {
    v113 = a15;
    v114 = v218;
  }
  if ( (GetAppCompatFlags(v19) & 0x8000000) != 0 )
  {
    SetOrClrWF(1, v44, 1032, 1);
    v218 = v114 & 0x3F;
    v267 &= 0x3Fu;
  }
  SetOrClrWF(1, v44, 1281, 1);
  SetOrClrWF(1, v44, 1282, 1);
  SetOrClrWF(1, v44, 1284, 1);
  v115 = v113;
  if ( v113 <= *((_WORD *)v19 + 334) )
    v115 = *((_DWORD *)v19 + 167);
  *(_DWORD *)(v44 + 256) = v115;
  if ( (GetAppCompatFlags2(39168) & 0x10000000) != 0 )
    SetOrClrWF(1, v44, 2688, 1);
  if ( (unsigned int)IsInsideUserApiHook() )
    xxxLoadUserApiHook();
  if ( (unsigned int)WantImeWindow(v226, (struct tagWND *)v44) )
  {
    v116 = *((_QWORD *)v19 + 102);
    if ( v116
      && ((*(_BYTE *)(_HMPheFromObject(v116) + 25) & 1) != 0
       || (unsigned int)IsWindowBeingDestroyed(*((_QWORD *)v19 + 102))) )
    {
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1489);
    }
    *(_DWORD *)(v44 + 380) |= 0x10000000u;
    ++*((_DWORD *)v19 + 235);
  }
  if ( ((*((_BYTE *)v19 + 712) | *(_BYTE *)(**((_QWORD **)v19 + 62) + 16LL)) & 0x40) != 0 )
  {
    v249 = (__int64)v257;
    v250 = 0;
    if ( (unsigned int)xxxCallHook(3, *(_QWORD *)v44, (__int64)&v249, 5) )
    {
      v87 = 6;
      goto LABEL_476;
    }
    v219 = __PAIR64__(v262, v263);
    LODWORD(Str1) = v261;
    v225 = v260;
    v244 = v250;
  }
  else
  {
    v244 = 0;
  }
  if ( (*(_BYTE *)(*(_QWORD *)v222 + 31LL) & 0xC0) != 0x40 )
  {
    v117 = 0;
    v221 = 0;
    goto LABEL_269;
  }
  v117 = 1;
  v221 = 1;
  if ( !v226 )
    goto LABEL_475;
LABEL_269:
  v118 = 0;
  v224 = 5;
  if ( v117 != v256 )
  {
    v241 = 0;
    SmartObjStackRefBase<tagMENU>::operator=(v240);
    v117 = v221;
  }
  if ( (*(_BYTE *)(*(_QWORD *)v222 + 31LL) & 0xC0) != 0 )
  {
    v119 = 0;
    if ( (_DWORD)v219 == 0x80000000 || (_DWORD)v219 == 0x8000 )
      v219 = 0;
    v120 = (unsigned int)Str1;
    if ( (_DWORD)Str1 == 0x80000000 || (_DWORD)Str1 == 0x8000 )
    {
      v120 = 0;
      LODWORD(Str1) = 0;
      v225 = 0;
    }
  }
  else
  {
    v119 = 1;
    v120 = (unsigned int)Str1;
  }
  *(_QWORD *)&v281 = v219;
  *((_QWORD *)&v281 + 1) = __PAIR64__(v225, v120);
  if ( v117 )
  {
    v254 = *(_OWORD *)(*(_QWORD *)(v247 + 40) + 104LL);
    if ( IsDpiBoundaryBetweenWindows((const struct tagWND *)v44, v226) )
    {
      *(_DWORD *)(v44 + 224) = 0;
      *(_DWORD *)(v44 + 228) = 0;
      LogicalToPhysicalInPlaceRectWithSubpixel(v226, &v254, v44 + 224);
      PhysicalToLogicalInPlaceRectWithSubpixel(v44, &v254, v44 + 224);
      v123 = DWORD1(v281);
      v122 = (unsigned int)v281;
    }
    if ( v226 != (struct tagWND *)GetDesktopWindow(v44, v121, v122, v123) )
    {
      LODWORD(v281) = v254 + v124;
      DWORD1(v281) = DWORD1(v254) + v125;
    }
    v244 = 1;
  }
  if ( v119 )
  {
    v126 = 0;
    SetOrClrWF(1, v44, 3844, 1);
    v127 = 192;
    SetOrClrWF(1, v44, 2305, 1);
    SetOrClrWF(1, v44, 16, 1);
    v129 = v219;
    v130 = 0x8000;
    if ( (_DWORD)v219 == 0x80000000 || (_DWORD)v219 == 0x8000 )
    {
      if ( DWORD1(v281) != 0x80000000 )
      {
        v128 = 5;
        if ( DWORD1(v281) != 0x8000 )
          v128 = DWORD1(v281);
        v224 = v128;
      }
      v129 = v219;
    }
    if ( !v235 && (v129 == 0x80000000 || v129 == 0x8000 || (_DWORD)Str1 == 0x80000000 || (_DWORD)Str1 == 0x8000) )
    {
      v131 = *(_QWORD *)(*v230 + 680LL);
      if ( v131 )
      {
        v132 = (struct tagMONITOR *)ValidateHmonitor(v131, v128, 0x8000);
        goto LABEL_302;
      }
      if ( v226 )
      {
        v132 = _MonitorFromWindowInternal(v226, 2u, 0);
LABEL_302:
        v126 = (__int64)v132;
      }
      if ( !v126 )
      {
        v126 = *(_QWORD *)(GetDispInfo(v131) + 96);
        goto LABEL_305;
      }
    }
    else
    {
LABEL_305:
      if ( !v126 )
      {
        v126 = ValidateHmonitor(*(_QWORD *)(*(_QWORD *)v222 + 256LL), v128, v130);
        if ( !v126 )
        {
          if ( v235 )
            v126 = GetInheritedMonitor((struct tagWND *)v44);
          else
            v126 = 0;
          if ( !v126 )
            v126 = MonitorFromRect(*(_QWORD *)v222 + 88LL, 2);
          UpdateWindowMonitorAndDpiInfoHelper((struct tagWND *)v44, (struct tagMONITOR *)v126);
          UpdateTopLevelWindowDPITransform(v44, v126);
        }
      }
    }
    SetTiledRect(v44, &v282, v126);
    v133 = v219;
    if ( (_DWORD)v219 == 0x80000000 || (_DWORD)v219 == 0x8000 )
    {
      v136 = v230;
      if ( (*(_DWORD *)(*v230 + 792LL) & 4) != 0 )
      {
        v118 = 1;
        v133 = *(_DWORD *)(*v230 + 776LL);
        LODWORD(v281) = v133;
        v137 = *(_DWORD *)(*v230 + 780LL);
      }
      else
      {
        v133 = v282;
        LODWORD(v281) = v282;
        v137 = DWORD1(v282);
      }
      DWORD1(v281) = v137;
      v219 = __PAIR64__(v137, v133);
      v134 = 1;
    }
    else
    {
      v134 = 0;
      v135 = *(_WORD *)(v126 + 74);
      v136 = v230;
      if ( v135 )
        *(_WORD *)(v126 + 74) = v135 - 1;
    }
    if ( DWORD2(v281) == 0x80000000 || DWORD2(v281) == 0x8000 )
    {
      if ( (*(_DWORD *)(*v136 + 792LL) & 2) != 0 )
      {
        v118 = 1;
        *((_QWORD *)&v281 + 1) = *(_QWORD *)(*v136 + 784LL);
      }
      else
      {
        DWORD2(v281) = DWORD2(v282) - v133;
        HIDWORD(v281) = HIDWORD(v282) - HIDWORD(v219);
      }
    }
    else if ( v134 )
    {
      MonitorRect = (int *)GetMonitorRect(v242, v126);
      v139 = MonitorRect[1];
      v140 = v281 + DWORD2(v281) - MonitorRect[2];
      v141 = DWORD1(v281) + HIDWORD(v281) - MonitorRect[3];
      if ( v140 > 0 )
      {
        v142 = *MonitorRect;
        LODWORD(v219) = v219 - v140;
        LODWORD(v281) = v219;
        if ( (int)v219 < v142 )
        {
          LODWORD(v219) = v142;
          LODWORD(v281) = v142;
        }
      }
      if ( v141 > 0 )
      {
        HIDWORD(v219) -= v141;
        DWORD1(v281) = HIDWORD(v219);
        if ( SHIDWORD(v219) < v139 )
        {
          HIDWORD(v219) = v139;
          DWORD1(v281) = v139;
        }
      }
    }
  }
  else
  {
    v127 = 0;
  }
  if ( v118 )
    *(_DWORD *)(*v230 + 792LL) &= 0xFFFFFFF9;
  v143 = v44 + 40;
  if ( (((*(_BYTE *)(*(_QWORD *)v222 + 31LL) & 0xC0) + 0x80) & 0xBF) == 0 )
    SetOrClrWF(1, v44, 3844, 1);
  *(_WORD *)(*(_QWORD *)v222 + 30LL) |= v127;
  if ( (unsigned __int8)SmartObjStackRef<tagMENU>::operator==(v240) && !v221 && *(_QWORD *)(*(_QWORD *)v229[0] + 96LL) )
  {
    v237 = 0;
    v145 = v44;
    if ( *(_QWORD *)(v44 + 104) )
      v145 = *(_QWORD *)(v44 + 104);
    zzzLockDisplayAreaAndInvalidateDCCache(v145, 16);
    RtlInitUnicodeStringOrId(&v237, *(_QWORD *)(*(_QWORD *)v229[0] + 96LL));
    xxxClientLoadMenu(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v229[0] + 8LL) + 64LL), &v237);
    v241 = 0;
    SmartObjStackRefBase<tagMENU>::operator=(v240);
    if ( (*(_BYTE *)(*(_QWORD *)v222 + 31LL) & 0xC0) != 0x40 && !(unsigned int)IsWindowBeingDestroyed(v44) )
    {
      if ( (unsigned __int8)SmartObjStackRef<tagMENU>::operator==(v240) )
        v258 = 0;
      else
        v258 = **(struct _HEAD ***)v240[0];
      goto LABEL_347;
    }
    v148 = v241;
    if ( !v241 )
      v148 = *(struct _HEAD **)v240[0];
    DestroyMenu(v148);
    v241 = 0;
    SmartObjStackRefBase<tagMENU>::operator=(v240);
LABEL_475:
    v87 = (int)v232;
    goto LABEL_476;
  }
LABEL_347:
  WindowCloakStateComponentUIAware = 0;
  if ( (*(_BYTE *)(*(_QWORD *)v222 + 31LL) & 0xC0) == 0x40 )
  {
    v147 = v241;
    if ( !v241 )
      v147 = *(struct _HEAD **)v240[0];
    *(_QWORD *)(*(_QWORD *)v222 + 320LL) = v147;
    *(_QWORD *)(*(_QWORD *)(v44 + 40) + 152LL) = 0;
    *(_QWORD *)(v44 + 168) = 0;
  }
  else
  {
    *(_QWORD *)(*(_QWORD *)v222 + 320LL) = 0;
    LockWndMenuWorker(v44, 0, v240);
  }
  if ( (*(_BYTE *)(*(_QWORD *)v222 + 31LL) & 0xC0) != 0x40 )
  {
    if ( (a16 & 4) != 0 )
    {
      LOBYTE(v144) = 1;
      CoreWindowProp::ChangeRole(v44, 1, v144);
    }
    *(_OWORD *)v242 = *(_OWORD *)LockPointer(&v237, v44 + 200, v44);
    HMAssignmentLock(v242, 0);
    if ( (unsigned int)IsTopLevelParent(v226) )
    {
      v150 = v44 + 120;
      *(_QWORD *)(*(_QWORD *)(v44 + 40) + 64LL) = 0;
      *(_QWORD *)&v237.left = v44 + 120;
      *(_QWORD *)&v237.right = 0;
      HMAssignmentLock(&v237, 0);
    }
    else
    {
      NonChildAncestor = GetNonChildAncestor();
      if ( !(unsigned int)ValidateOwnerDepth(v44, NonChildAncestor) )
        goto LABEL_360;
      if ( NonChildAncestor )
      {
        *(_DWORD *)(*(_QWORD *)v222 + 236LL) = *(_DWORD *)(*(_QWORD *)(NonChildAncestor + 40) + 236LL);
        SetOrClrWF(*(_BYTE *)(*(_QWORD *)(NonChildAncestor + 40) + 232LL) & 0x40, v44, 55360, 1);
        WindowCloakStateComponentUIAware = GetWindowCloakStateComponentUIAware(NonChildAncestor);
      }
      v150 = v44 + 120;
      *(_OWORD *)v242 = *(_OWORD *)LockPointer(&v237, v44 + 120, NonChildAncestor);
      HMAssignmentLock(v242, 1);
      if ( *(_QWORD *)(v44 + 120)
        && ((*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v44 + 120) + 40LL) + 24LL) & 8) != 0
         || *(_DWORD *)(*(_QWORD *)v222 + 236LL) != 1) )
      {
        SetOrClrWF(1, v44, 2056, 1);
      }
      v152 = *(_QWORD *)(W32GetUserSessionState(v151) + 19704);
      if ( (_WORD)Atom != *(_WORD *)(v152 + 898) )
      {
        if ( *(_QWORD *)v150 )
        {
          v153 = *(struct tagTHREADINFO **)(*(_QWORD *)v150 + 16LL);
          if ( v153 != v19 )
            zzzAttachThreadInput(v19, v153);
        }
      }
      v143 = v44 + 40;
    }
    IsEnabledDeviceUsageNoInline = Feature_Scoobe_ShellHost__private_IsEnabledDeviceUsageNoInline();
    if ( !*(_QWORD *)v150 )
    {
      if ( IsEnabledDeviceUsageNoInline )
      {
        if ( (unsigned int)CoreWindowProp::IsComponent((const struct tagWND *)v44) )
          goto LABEL_389;
        v155 = *(_DWORD *)(*(_QWORD *)v143 + 236LL);
        if ( (unsigned int)(v155 - 8) <= 3 || v155 == 15 )
          goto LABEL_388;
        v156 = (*(_BYTE *)(*(_QWORD *)v143 + 232LL) & 0x40) == 0;
      }
      else
      {
        if ( (unsigned int)CoreWindowProp::IsComponent((const struct tagWND *)v44) )
          goto LABEL_389;
        v157 = *(_DWORD *)(*(_QWORD *)v143 + 236LL);
        if ( v157 <= 0xF )
        {
          v158 = 44800;
          if ( _bittest(&v158, v157) )
            goto LABEL_388;
        }
        v156 = (*(_BYTE *)(*(_QWORD *)v143 + 232LL) & 0x40) == 0;
      }
      if ( !v156 )
LABEL_388:
        WindowCloakStateComponentUIAware = 2;
    }
LABEL_389:
    if ( v226 && v226 == *(struct tagWND **)(*((_QWORD *)v226 + 3) + 112LL) )
    {
      v159 = v19;
    }
    else
    {
      v67 = GetThreadDesktopWindow(0);
      v226 = (struct tagWND *)v67;
      v159 = v19;
      Win32HM_LockIntoThread<1>(v19, v67, v246);
      v228 = 1;
    }
    if ( !v239 )
      goto LABEL_399;
    if ( !*((_QWORD *)v159 + 198) )
    {
      SetOrClrWF(1, v44, 55424, 1);
      *((_QWORD *)v159 + 170) |= 0x40000uLL;
      *(_DWORD *)(*((_QWORD *)v159 + 58) + 508LL) |= 0x2000000u;
      if ( !*((_QWORD *)v159 + 197) )
      {
        KernelEvent = CreateKernelEvent(1, 0);
        *((_QWORD *)v159 + 197) = KernelEvent;
        if ( !KernelEvent )
        {
          v87 = 7;
          goto LABEL_476;
        }
      }
      *(_QWORD *)&v237.left = (char *)v159 + 1584;
      *(_QWORD *)&v237.right = v44;
      HMAssignmentLock(&v237, 0);
      goto LABEL_399;
    }
LABEL_360:
    UserSetLastError(87);
    goto LABEL_475;
  }
  if ( !v226 )
    goto LABEL_475;
  if ( v239 )
    goto LABEL_360;
LABEL_399:
  v161 = 0;
  if ( (*(_DWORD *)(v44 + 380) & 0x1000000) != 0 )
  {
    v161 = *(_QWORD *)(v44 + 104);
    UnlinkWindow((struct tagWND *)v44);
  }
  if ( !(unsigned int)IsTopLevelParent(v67) )
  {
    *(_DWORD *)(*(_QWORD *)v222 + 236LL) = *(_DWORD *)(*(_QWORD *)(v67 + 40) + 236LL);
    SetOrClrWF(*(_BYTE *)(*(_QWORD *)(v67 + 40) + 232LL) & 0x40, v44, 55360, 1);
  }
  if ( v67 && !(unsigned int)ValidateNewParent(v44, v67, 1) )
  {
    v87 = 9;
    goto LABEL_476;
  }
  v162 = (struct tagWND **)(v44 + 104);
  *(_OWORD *)v242 = *(_OWORD *)LockPointer(&v237, v44 + 104, v226);
  HMAssignmentLock(v242, 0);
  if ( v226 )
    v163 = (unsigned int)-__CFSHR__(*(_DWORD *)(*((_QWORD *)v226 + 5) + 232LL), 10);
  else
    v163 = 0;
  SetWindowSubtreeCoreWindowStatus(v44, v163);
  v164 = *(_QWORD *)(v44 + 40);
  if ( (*(_DWORD *)(v164 + 288) & 0xF) == 2 )
    *(_DWORD *)(v164 + 232) = *(_DWORD *)(v164 + 232) & 0xFFFFFBFF
                            | (ShouldUseLogPixelsForWindowMetrics((struct tagWND *)v44) << 10);
  if ( (WindowCloakStateComponentUIAware & 2) == 0 )
    *(_DWORD *)(v44 + 384) |= 4u;
  if ( WindowCloakStateComponentUIAware )
  {
    v165 = zzzSetWindowCompositionCloak(v44, WindowCloakStateComponentUIAware);
    if ( v165 < 0 )
    {
      v166 = RtlNtStatusToDosError(v165);
      UserSetLastError(v166);
      v87 = 8;
      goto LABEL_476;
    }
  }
  AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)v242);
  if ( v161 )
    zzzLockDisplayAreaAndInvalidateDCCache(v161, 16);
  if ( v226 )
    zzzLockDisplayAreaAndInvalidateDCCache(v226, 16);
  AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v242);
  v167 = *(_QWORD *)(v44 + 40);
  if ( (*(_BYTE *)(v167 + 31) & 0xC0) == 0x40 && !(unsigned int)IsTopLevelWindow(v44) )
  {
    v168 = (struct tagTHREADINFO **)*v162;
    if ( *v162 )
    {
      if ( v19 != v168[2] )
      {
        if ( v226 != (struct tagWND *)v168 )
        {
          v239 = 0x20000;
          MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 2199);
        }
        zzzAttachThreadInput(v19, *((struct tagTHREADINFO **)*v162 + 2));
        v169 = GetMessageWindow(v44);
        if ( v170 != (struct tagWND *)v169 )
        {
          v167 = *(unsigned int *)(*v236 + 288);
          if ( (((unsigned __int8)v167 ^ *(_BYTE *)(*((_QWORD *)v170 + 5) + 288LL)) & 0xF) != 0
            && !IsChildWindowDpiIsolationEnabled((struct tagWND *)v44, v170) )
          {
            xxxForceUpdateProcessDpiAwarenessContext((struct tagWND *)v44, *(_DWORD *)(*((_QWORD *)*v162 + 5) + 288LL));
          }
        }
      }
    }
  }
  v171 = W32GetUserSessionState(v167);
  if ( v248 != *(unsigned __int16 *)(v171 + 41168) && v248 != 32769 && !*(_DWORD *)v253[0] )
  {
    _InterlockedExchange(
      (volatile __int32 *)(*((_QWORD *)v19 + 60) + 20LL),
      (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24);
    xxxUpdateInputHangInfo(0, 1);
  }
  xxxAdjustSize((struct tagWND *)v44);
  ConstrainWindowSIZERECT(&v281);
  if ( *v252 && (*(_BYTE *)(*v236 + 31) & 0x40) == 0 && *(char *)(*v236 + 24) >= 0 )
    CheckFullScreen((struct tagWND *)v44);
  v172 = DWORD2(v281);
  if ( SDWORD2(v281) < 0 )
    v172 = 0;
  DWORD2(v281) = v172;
  v173 = HIDWORD(v281);
  if ( v281 < 0 )
    v173 = 0;
  HIDWORD(v281) = v173;
  RECTFromSIZERECT(*v236 + 88, &v281);
  if ( v221 )
  {
    v174 = ValidateHmonitorNoRip(*(_QWORD *)(*((_QWORD *)v226 + 5) + 256LL));
LABEL_447:
    v175 = (struct tagMONITOR *)v174;
  }
  else
  {
    if ( v235 )
    {
      v174 = GetInheritedMonitor((struct tagWND *)v44);
      goto LABEL_447;
    }
    v175 = 0;
  }
  if ( v175 || (v175 = (struct tagMONITOR *)MonitorFromRect(*v236 + 88, 2), v176 = 0, v175) )
    v176 = *(_QWORD *)v175;
  if ( v176 != *(_QWORD *)(*v236 + 256) )
  {
    UpdateWindowMonitorAndDpiInfoHelper((struct tagWND *)v44, v175);
    if ( !v221 )
      UpdateTopLevelWindowDPITransform(v44, v175);
  }
  v177 = v236;
  if ( (*(_BYTE *)(*v236 + 27) & 0x20) != 0 && GetRedirectionBitmap(v44) )
  {
    GreLockVisRgn();
    if ( (int)RecreateRedirectionBitmap((struct tagWND *)v44, 0, 0) < 0 )
    {
      GreUnlockVisRgn();
      v87 = 3;
      goto LABEL_476;
    }
    GreUnlockVisRgn();
  }
  if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)v229[0] + 8LL) + 8LL) & 0x20) != 0
    || (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)v229[0] + 8LL) + 8LL) & 0x40) != 0 && !*(_QWORD *)(*(_QWORD *)v229[0] + 40LL) )
  {
    StyleWindow = GetStyleWindow(v44, 2848);
    GreLockVisRgn();
    if ( !CreateCacheDC(v44, StyleWindow != 0 ? 49152 : 0x8000, 0) )
    {
      GreUnlockVisRgn();
      v87 = 10;
      goto LABEL_476;
    }
    GreUnlockVisRgn();
    v177 = v236;
  }
  v179 = v218;
  if ( (v218 & 0x80000) != 0 && (*(_BYTE *)(*v177 + 26) & 8) == 0 )
  {
    if ( (int)xxxSetLayeredWindow((struct tagWND *)v44) < 0 )
    {
      v87 = 11;
      goto LABEL_476;
    }
    v179 = v218;
  }
  if ( (v179 & 0x2000000) != 0 && !GetStyleWindow(*v162, 2818) )
  {
    SetOrClrWF(1, v44, 2818, 1);
    if ( (int)SetRedirectedWindow((struct tagWND *)v44) < 0 )
    {
      SetOrClrWF(0, v44, 2818, 1);
      v87 = 12;
      goto LABEL_476;
    }
  }
  v262 = HIDWORD(v219);
  v263 = v219;
  v261 = (int)Str1;
  v260 = v225;
  if ( !xxxSendTransformableMessageTimeout((struct tagWND *)v44, 0x81u, 0, 0, 0, 1, 1) )
    goto LABEL_475;
  v185 = *(_QWORD *)(*v274 + 8LL);
  if ( (*(_BYTE *)(v185 + 9) & 2) != 0 )
  {
    xxxGetSystemMenu((struct tagWND *)v44);
    v241 = 0;
    SmartObjStackRefBase<tagMENU>::operator=(v240);
    if ( !(unsigned __int8)SmartObjStackRef<tagMENU>::operator==(v240) )
    {
      Win32HMThreadLock<tagMENU>::Win32HMThreadLock<tagMENU>(v242, v240);
      xxxRemoveDeleteMenuHelper(v240, 5, 1024, 1);
      xxxRemoveDeleteMenuHelper(v240, 5, 1024, 1);
      Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)v242);
    }
  }
  if ( (*(_BYTE *)(*v177 + 18) & 2) != 0 && (!v270 || v268 || *(_QWORD *)(v44 + 184)) )
  {
    *(_OWORD *)v242 = 0;
    v265 = *(_QWORD *)(v44 + 184);
    StrName = tagWND::ProtectedLargeUnicodeStringWNDstrName::getStrName(
                (tagWND::ProtectedLargeUnicodeStringWNDstrName *)(v44 + 184),
                (struct _LARGE_UNICODE_STRING *)v242);
    v268 = *(_DWORD *)StrName;
    v185 = *((unsigned int *)StrName + 1);
    v269 = *((_DWORD *)StrName + 1);
    v270 = *((_QWORD *)StrName + 1);
  }
  if ( (**(_DWORD **)(W32GetUserSessionState(v185) + 19704) & 4) != 0 )
  {
    v187 = (struct tagWND **)((char *)v19 + 816);
    if ( !*((_QWORD *)v19 + 102) && (*(_DWORD *)(v44 + 380) & 0x10000000) != 0 )
    {
      DefaultImeWindow = xxxCreateDefaultImeWindow((struct tagWND *)v44, Atom, v245);
      v253[0] = (ULONG_PTR)v19 + 816;
      v253[1] = (ULONG_PTR)DefaultImeWindow;
      HMAssignmentLock(v253, 0);
      if ( *v187 )
      {
        Win32HMThreadLockAlways<tagHOOK>::Win32HMThreadLockAlways<tagHOOK>(v242, v19, *v187);
        xxxSendTransformableMessageTimeout(*v187, 0x287u, 0, 0, 0, 1, 1);
        Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)v242);
      }
      v189 = (**((_DWORD **)v19 + 64) >> 6) & 1;
      v276 = v189;
      if ( *v187 && v189 )
      {
        Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(v253);
        xxxSendTransformableMessageTimeout(*v187, 0x287u, 0, 0, 0, 1, 1);
        **((_QWORD **)v19 + 64) &= ~0x40uLL;
        Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)v253);
      }
    }
  }
  v190 = v226;
  if ( v226 && ((*(_DWORD *)(v44 + 380) & 0x1000000) == 0 || *v162 == v226) )
  {
    CompositeAppFrameWindowOrSelf = PWInsertAfter(v244);
    if ( !(unsigned int)IsPseudoPwnd(CompositeAppFrameWindowOrSelf)
      && *(struct tagWND **)(CompositeAppFrameWindowOrSelf + 104) != *v162 )
    {
      CompositeAppFrameWindowOrSelf = v221 != 0;
    }
    v192 = *(_QWORD *)(v44 + 120);
    if ( v192 )
    {
      *(_DWORD *)(*v236 + 236) = *(_DWORD *)(*(_QWORD *)(v192 + 40) + 236LL);
      SetOrClrWF(*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v44 + 120) + 40LL) + 232LL) & 0x40, v44, 55360, 1);
    }
    if ( !(unsigned int)ValidateNewParent(v44, v226, 1) )
    {
      v193 = 9;
      goto LABEL_536;
    }
    UnlinkWindow((struct tagWND *)v44);
    v194 = *v236;
    v195 = v226;
    if ( (*(_BYTE *)(*v236 + 31) & 0xC0) != 0x40 && v226 != *(struct tagWND **)(*((_QWORD *)v226 + 3) + 112LL) )
    {
      if ( (*(_BYTE *)(v194 + 24) & 8) != 0 )
      {
        if ( *(_QWORD *)(W32GetUserSessionState(v194) + 19160) )
        {
          TopMostInsertAfter = GetTopMostInsertAfter(v44);
          if ( TopMostInsertAfter )
            CompositeAppFrameWindowOrSelf = TopMostInsertAfter;
        }
      }
      else if ( !CompositeAppFrameWindowOrSelf
             || !(unsigned int)IsPseudoPwnd(CompositeAppFrameWindowOrSelf)
             && (*(_BYTE *)(*(_QWORD *)(CompositeAppFrameWindowOrSelf + 40) + 24LL) & 8) != 0 )
      {
        v196 = (const struct tagWND *)CalcForegroundInsertAfter(v44, v195);
        CompositeAppFrameWindowOrSelf = (unsigned __int64)v196;
        if ( !*(_QWORD *)(v44 + 120) )
          CompositeAppFrameWindowOrSelf = (unsigned __int64)CoreWindowProp::GetCompositeAppFrameWindowOrSelf(v196);
      }
    }
    if ( CompositeAppFrameWindowOrSelf >= 2 && (unsigned int)IsPseudoPwnd(CompositeAppFrameWindowOrSelf) )
    {
      v193 = 13;
      goto LABEL_536;
    }
    LinkWindow((struct tagWND *)v44);
    zzzLockDisplayAreaAndInvalidateDCCache(v226, 16);
    v190 = v226;
  }
  v198 = v236;
  v199 = *v236;
  if ( (*(_BYTE *)(*v236 + 31) & 0xC0) == 0x40 && (*(_BYTE *)(*((_QWORD *)v190 + 5) + 26LL) & 0x40) != 0 )
  {
    v200 = *(_DWORD *)(v199 + 96);
    v201 = *(_DWORD *)(v199 + 88);
    *(_DWORD *)(v199 + 96) = DWORD2(v254) + v254 - v201;
    *(_DWORD *)(*v198 + 88) = v201 + *(_DWORD *)(*v198 + 96) - v200;
  }
  v282 = *(_OWORD *)(*v198 + 88);
  xxxSendTransformableMessageTimeout((struct tagWND *)v44, 0x83u, 0, 0, 0, 1, 0);
  *(_OWORD *)(*v198 + 104) = v282;
  if ( xxxSendTransformableMessageTimeout((struct tagWND *)v44, 1u, 0, 0, 0, 1, 1) == -1 )
  {
    v193 = (int)v232;
LABEL_536:
    if ( v228 )
      Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)v246);
    if ( Win32HMThreadLockBase<tagMENU,0,1>::ManualUnlock<void>((ULONG_PTR)BugCheckParameter3) )
      xxxDestroyWindow((struct tagWND *)v44);
    ClassUnlock(*(struct tagCLS **)v229[0]);
    if ( v193 )
    {
      v183 = ((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
           * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8);
      v184 = v193;
LABEL_542:
      TraceLoggingCreateWindowFailed(v184, *((unsigned __int64 *)&v183 + 1));
    }
LABEL_543:
    Win32HMOptionalThreadLockAlways<tagMENU>::~Win32HMOptionalThreadLockAlways<tagMENU>((ULONG_PTR)BugCheckParameter3);
    goto LABEL_6;
  }
  SetOrClrWF(1, v44, 1920, 1);
  xxxConsiderPreferredDpiChange((struct tagWND *)v44);
  if ( (unsigned int)IsWindowDesktopComposed(v44) )
  {
    v202 = (void *)ReferenceDwmApiPort();
    DwmAsyncChildStyleChange(v202);
    DwmChildRectChange((struct tagWND *)v44);
    DirtyVisRgnTrackers((struct tagWND *)v44);
    v203 = (void *)ReferenceDwmApiPort();
    DwmAsyncOwnerChange(v203);
    v198 = v236;
  }
  xxxWindowEvent(0x8000u, (struct tagWND *)v44, 0, 0, 0);
  if ( (*(_BYTE *)(*v198 + 16) & 0x10) == 0 )
  {
    xxxSendSizeMessage((struct tagWND *)v44);
    if ( v226 )
    {
      DesktopWindow = GetDesktopWindow(v44, v226, v205, v206);
      if ( DesktopWindow != v208 )
      {
        LODWORD(v282) = v282 - v254;
        DWORD1(v282) -= DWORD1(v254);
      }
    }
    xxxSendTransformableMessageTimeout((struct tagWND *)v44, 3u, 0, 0, 0, 1, 0);
  }
  v209 = *(_DWORD *)(W32GetUserSessionState(v204) + 66784) & 0x10000 | 1;
  v210 = v236;
  v211 = *(_BYTE *)(*v236 + 31);
  if ( (v211 & 0x20) != 0 )
  {
    SetMinimize(v44, 0);
    v212 = 7;
    goto LABEL_555;
  }
  if ( (v211 & 1) != 0 )
  {
    SetOrClrWF(0, v44, 3841, 1);
    v209 |= 0x10u;
    v212 = 3;
LABEL_555:
    xxxMinMaximize(v44, v212, v209);
  }
  CalcWindowFullScreen((struct tagWND *)v44);
  if ( (*(_BYTE *)(*v210 + 31) & 0xC0) == 0x40 && (*(_BYTE *)(*v210 + 24) & 4) == 0 && *v162 )
  {
    Win32HMThreadLockAlways<tagWND>::Win32HMThreadLockAlways<tagWND>(v242, v19, v44 + 104);
    xxxSendTransformableMessageTimeout(*v162, 0x210u, 0, 0, 0, 1, 0);
    Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)v242);
  }
  xxxInheritWindowMonitor((struct tagWND *)v44);
  CDwmWindowNotifyBatch::CDwmWindowNotifyBatch((CDwmWindowNotifyBatch *)v280, (struct tagWND *)v44);
  if ( (a5 & 0x10000000) != 0 )
  {
    v214 = W32GetUserSessionState(v213);
    xxxShowWindowEx(
      v44,
      v224 | *(_DWORD *)(v214 + 66784) & 0x10000u,
      v224 & 0x10000 | *(_DWORD *)(v214 + 66784) & 0x10000u);
  }
  CDwmWindowNotifyBatch::~CDwmWindowNotifyBatch((CDwmWindowNotifyBatch *)v280);
  if ( (*(_BYTE *)(*v210 + 31) & 0xC0) == 0 || (*(_BYTE *)(*v210 + 26) & 4) != 0 )
  {
    v215 = v230;
    if ( *(_DWORD *)(*v230 + 676LL) )
    {
      xxxSendTransformableMessageTimeout((struct tagWND *)v44, 0x32u, 0, 0, 0, 1, 1);
      *(_DWORD *)(*v215 + 676LL) = 0;
    }
  }
  if ( v228 )
    Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)v246);
  ClassUnlock(*(struct tagCLS **)v229[0]);
  v216 = Win32HMThreadLockBase<tagMENU,0,1>::ManualUnlock<void>((ULONG_PTR)BugCheckParameter3);
  v217 = v216;
  if ( !v216 || (*(_BYTE *)(_HMPheFromObject(v216) + 25) & 1) != 0 )
    v217 = 0;
  Win32HMOptionalThreadLockAlways<tagMENU>::~Win32HMOptionalThreadLockAlways<tagMENU>((ULONG_PTR)BugCheckParameter3);
  SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(v240);
  Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)v246);
  SmartObjStackRef<tagPOPUPMENU>::~SmartObjStackRef<tagPOPUPMENU>(v229);
  return v217;
}

```

## disassembly

```asm
0x14013f4b4  push    rbx
0x14013f4b6  push    rsi
0x14013f4b7  push    rdi
0x14013f4b8  push    r12
0x14013f4ba  push    r13
0x14013f4bc  push    r14
0x14013f4be  push    r15
0x14013f4c0  sub     rsp, 2F0h
0x14013f4c7  mov     rax, cs:__security_cookie
0x14013f4ce  xor     rax, rsp
0x14013f4d1  mov     [rsp+328h+var_40], rax
0x14013f4d9  mov     rax, r9
0x14013f4dc  mov     [rsp+328h+var_B8], rax
0x14013f4e4  mov     [rsp+328h+var_E8], rdx
0x14013f4ec  mov     [rsp+328h+var_248], ecx
0x14013f4f3  mov     [rsp+328h+var_2C8], ecx
0x14013f4f7  mov     edi, ecx
0x14013f4f9  mov     [rsp+328h+var_2D8], ecx
0x14013f4fd  mov     [rsp+328h+var_270], ecx
0x14013f504  mov     [rsp+328h+Str1], rdx
0x14013f50c  mov     [rsp+328h+var_1E8], r8
0x14013f514  mov     [rsp+328h+var_278], rax
0x14013f51c  mov     r13, [rsp+328h+arg_48]
0x14013f524  mov     [rsp+328h+var_2B0], r13
0x14013f529  mov     [rsp+328h+var_210], r13
0x14013f531  mov     rbx, [rsp+328h+arg_50]
0x14013f539  mov     rax, [rsp+328h+arg_58]
0x14013f541  mov     [rsp+328h+var_208], rax
0x14013f549  mov     rax, [rsp+328h+arg_60]
0x14013f551  mov     qword ptr [rsp+328h+var_258.left], rax
0x14013f559  lea     rcx, [rsp+328h+var_298]
0x14013f561  call    ??0?$SmartObjStackRef@UtagCLS@@@@QEAA@XZ; SmartObjStackRef<tagCLS>::SmartObjStackRef<tagCLS>(void)
0x14013f566  xorps   xmm0, xmm0
0x14013f569  movups  [rsp+328h+var_50], xmm0
0x14013f571  xorps   xmm1, xmm1
0x14013f574  movups  [rsp+328h+var_60], xmm1
0x14013f57c  xor     edx, edx; Val
0x14013f57e  lea     r8d, [rdx+70h]; Size
0x14013f582  lea     rcx, [rsp+328h+var_158]; void *
0x14013f58a  call    memset_0
0x14013f58f  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14013f594  mov     r15, rax
0x14013f597  mov     [rsp+328h+var_2A8], rax
0x14013f59f  lea     rcx, [rsp+328h+var_200]
0x14013f5a7  call    ??0?$Win32HMOptionalThreadLockAlways@UtagMENU@@@@QEAA@XZ; Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(void)
0x14013f5ac  xorps   xmm0, xmm0
0x14013f5af  xor     eax, eax
0x14013f5b1  movups  [rsp+328h+var_A8], xmm0
0x14013f5b9  mov     [rsp+328h+var_98], rax
0x14013f5c1  lea     rsi, [r15+1C8h]
0x14013f5c8  mov     [rsp+328h+var_288], rsi
0x14013f5d0  mov     rax, [rsi]
0x14013f5d3  mov     r14d, [rax+0Ch]
0x14013f5d7  movups  [rsp+328h+var_1A8], xmm0
0x14013f5df  mov     rdx, rbx
0x14013f5e2  lea     rcx, [rsp+328h+var_240]
0x14013f5ea  call    ??0?$SmartObjStackRef@UtagMENU@@@@QEAA@AEBV0@@Z; SmartObjStackRef<tagMENU>::SmartObjStackRef<tagMENU>(SmartObjStackRef<tagMENU> const &)
0x14013f5ef  lea     rcx, [rsp+328h+var_1E0]; this
0x14013f5f7  call    ??0AtomicExecutionCheck@@QEAA@XZ; AtomicExecutionCheck::AtomicExecutionCheck(void)
0x14013f5fc  mov     rax, [rsi]
0x14013f5ff  test    dword ptr [rax+0Ch], 10000000h
0x14013f606  jnz     short loc_14013F659
0x14013f608  call    RegisterIconTitleClass
0x14013f60d  xor     esi, esi
0x14013f60f  test    eax, eax
0x14013f611  jnz     short loc_14013F65B
0x14013f613  mov     ecx, 57h ; 'W'
0x14013f618  call    UserSetLastError
0x14013f61d  lea     rcx, [rsp+328h+var_1E0]; this
0x14013f625  call    ?Disarm@AtomicExecutionCheck@@QEAAXXZ; AtomicExecutionCheck::Disarm(void)
0x14013f62a  lea     rcx, [rsp+328h+var_240]
0x14013f632  call    ??1?$SmartObjStackRef@UtagMENU@@@@QEAA@XZ; SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(void)
0x14013f637  lea     rcx, [rsp+328h+var_200]; BugCheckParameter3
0x14013f63f  call    ??1?$Win32HMOptionalThreadLock@UtagHOOK@@@@QEAA@XZ; Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>(void)
0x14013f644  lea     rcx, [rsp+328h+var_298]
0x14013f64c  call    ??1?$SmartObjStackRef@UtagPOPUPMENU@@@@QEAA@XZ; SmartObjStackRef<tagPOPUPMENU>::~SmartObjStackRef<tagPOPUPMENU>(void)
0x14013f651  xor     eax, eax
0x14013f653  jmp     loc_1401428A8
0x14013f659  xor     esi, esi
0x14013f65b  mov     eax, edi
0x14013f65d  test    edi, edi
0x14013f65f  jns     short loc_14013F670
0x14013f661  btr     edi, 1Fh
0x14013f665  mov     [rsp+328h+var_2D8], edi
0x14013f669  mov     [rsp+328h+var_270], edi
0x14013f670  mov     ecx, 320h
0x14013f675  test    eax, eax
0x14013f677  cmovns  cx, si
0x14013f67b  mov     [rsp+328h+var_2B8], ecx
0x14013f67f  mov     word ptr [rsp+328h+var_2D4], cx
0x14013f684  mov     rbx, [r15+1E8h]
0x14013f68b  mov     [rsp+328h+var_1C8], rbx
0x14013f693  mov     [rsp+328h+var_1B8], rbx
0x14013f69b  test    r13, r13
0x14013f69e  jz      short loc_14013F6AA
0x14013f6a0  cmp     [r13+18h], rbx
0x14013f6a4  jnz     loc_14013F613
0x14013f6aa  mov     r12d, esi
0x14013f6ad  mov     [rsp+328h+var_2B4], esi
0x14013f6b1  mov     r15d, 1
0x14013f6b7  mov     edi, dword ptr [rsp+328h+arg_78]
0x14013f6be  test    r15b, dil
0x14013f6c1  jz      short loc_14013F6EA
0x14013f6c3  mov     rcx, [rsp+328h+var_288]
0x14013f6cb  mov     rcx, [rcx]
0x14013f6ce  call    cs:__imp_IsDesktopApp
0x14013f6d5  nop     dword ptr [rax+rax+00h]
0x14013f6da  test    eax, eax
0x14013f6dc  jnz     loc_14013F88B
0x14013f6e2  mov     r12d, r15d
0x14013f6e5  mov     [rsp+328h+var_2B4], r15d
0x14013f6ea  mov     eax, edi
0x14013f6ec  and     eax, 2
0x14013f6ef  mov     [rsp+328h+var_244], eax
0x14013f6f6  jz      short loc_14013F717
0x14013f6f8  mov     rax, [rsp+328h+var_288]
0x14013f700  mov     rcx, [rax]
0x14013f703  call    cs:__imp_IsImmersiveBroker
0x14013f70a  nop     dword ptr [rax+rax+00h]
0x14013f70f  test    eax, eax
0x14013f711  jz      loc_14013F88B
0x14013f717  mov     edi, [rsp+328h+arg_68]
0x14013f71e  test    edi, edi
0x14013f720  jz      short loc_14013F775
0x14013f722  mov     ecx, edi
0x14013f724  call    IsValidBand
0x14013f729  test    eax, eax
0x14013f72b  jz      loc_14013F613
0x14013f731  cmp     edi, 0Fh
0x14013f734  jz      loc_14013F613
0x14013f73a  mov     r8, [rsp+328h+var_288]
0x14013f742  mov     rax, [r8]
0x14013f745  mov     rcx, [rax+328h]
0x14013f74c  mov     al, cl
0x14013f74e  and     al, 30h
0x14013f750  cmp     al, 10h
0x14013f752  jnz     short loc_14013F77D
0x14013f754  bt      rcx, 9
0x14013f759  jb      short loc_14013F77D
0x14013f75b  cmp     edi, r15d
0x14013f75e  jnz     short loc_14013F77D
0x14013f760  test    r12d, r12d
0x14013f763  jnz     short loc_14013F77D
0x14013f765  mov     rcx, r13
0x14013f768  call    HasMessageRootWindow
0x14013f76d  test    eax, eax
0x14013f76f  jz      loc_14013F613
0x14013f775  mov     r8, [rsp+328h+var_288]
0x14013f77d  mov     ecx, [rsp+328h+arg_20]
0x14013f784  shr     ecx, 10h
0x14013f787  mov     eax, 0C000h
0x14013f78c  and     cx, ax
0x14013f78f  mov     [rsp+328h+var_2CC], ecx
0x14013f793  mov     word ptr [rsp+328h+var_2D4+4], cx
0x14013f798  mov     edx, 4000h
0x14013f79d  mov     eax, esi
0x14013f79f  cmp     cx, dx
0x14013f7a2  setz    al
0x14013f7a5  mov     [rsp+328h+var_16C], eax
0x14013f7ac  jz      short loc_14013F7D3
0x14013f7ae  mov     rdx, r13
0x14013f7b1  mov     rcx, [r8]
0x14013f7b4  call    cs:__imp_ShouldSetNoOwner
0x14013f7bb  nop     dword ptr [rax+rax+00h]
0x14013f7c0  test    eax, eax
0x14013f7c2  cmovnz  r13, rsi
0x14013f7c6  mov     [rsp+328h+var_2B0], r13
0x14013f7cb  mov     [rsp+328h+var_210], r13
0x14013f7d3  test    r13, r13
0x14013f7d6  jz      short loc_14013F818
0x14013f7d8  mov     rcx, r13
0x14013f7db  call    IsDesktopWindow
0x14013f7e0  test    eax, eax
0x14013f7e2  jnz     short loc_14013F818
0x14013f7e4  mov     rcx, [r13+28h]
0x14013f7e8  mov     eax, [rcx+0ECh]
0x14013f7ee  test    edi, edi
0x14013f7f0  jnz     short loc_14013F7FD
0x14013f7f2  mov     edi, eax
0x14013f7f4  mov     [rsp+328h+arg_68], eax
0x14013f7fb  jmp     short loc_14013F805
0x14013f7fd  cmp     edi, eax
0x14013f7ff  jnz     loc_14013F613
0x14013f805  movzx   r12d, byte ptr [rcx+0E8h]
0x14013f80d  and     r12d, 40h
0x14013f811  mov     [rsp+328h+var_2B4], r12d
0x14013f816  jmp     short loc_14013F872
0x14013f818  test    edi, edi
0x14013f81a  jnz     short loc_14013F872
0x14013f81c  mov     rax, [rsp+328h+var_288]
0x14013f824  mov     rcx, [rax]
0x14013f827  call    IsImmersiveAppIORestricted
0x14013f82c  test    eax, eax
0x14013f82e  jz      short loc_14013F846
0x14013f830  mov     r12d, r15d
0x14013f833  mov     [rsp+328h+var_2B4], r15d
0x14013f838  mov     edi, 0Fh
0x14013f83d  mov     [rsp+328h+arg_68], edi
0x14013f844  jmp     short loc_14013F872
0x14013f846  mov     al, [rcx+328h]
0x14013f84c  mov     ecx, 2
0x14013f851  test    cl, al
0x14013f853  jz      short loc_14013F867
0x14013f855  test    byte ptr [rsp+328h+var_2D8], 8
0x14013f85a  jz      short loc_14013F867
0x14013f85c  mov     edi, ecx
0x14013f85e  mov     [rsp+328h+arg_68], ecx
0x14013f865  jmp     short loc_14013F872
0x14013f867  mov     edi, r15d
0x14013f86a  mov     [rsp+328h+arg_68], r15d
0x14013f872  mov     r8, r13
0x14013f875  mov     edx, edi
0x14013f877  mov     rax, [rsp+328h+var_288]
0x14013f87f  mov     rcx, [rax]
0x14013f882  call    ?IsValidBandForProcess@@YA_NPEBUtagPROCESSINFO@@W4ZBID@@PEAUtagWND@@@Z; IsValidBandForProcess(tagPROCESSINFO const *,ZBID,tagWND *)
0x14013f887  test    al, al
0x14013f889  jnz     short loc_14013F895
0x14013f88b  mov     ecx, 5
0x14013f890  jmp     loc_14013F618
0x14013f895  mov     r8d, 400000h
0x14013f89b  mov     edx, [rsp+328h+var_2D8]
0x14013f89f  test    r8d, edx
0x14013f8a2  jnz     loc_14013F92D
0x14013f8a8  test    r13, r13
0x14013f8ab  jz      short loc_14013F8CD
0x14013f8ad  mov     eax, 4000h
0x14013f8b2  cmp     word ptr [rsp+328h+var_2CC], ax
0x14013f8b7  jnz     short loc_14013F92D
0x14013f8b9  mov     rax, [r13+28h]
0x14013f8bd  mov     cl, [rax+1Ah]
0x14013f8c0  and     cl, 50h
0x14013f8c3  cmp     cl, 40h ; '@'
0x14013f8c6  jnz     short loc_14013F92D
0x14013f8c8  or      edx, r8d
0x14013f8cb  jmp     short loc_14013F922
0x14013f8cd  mov     rax, [rsp+328h+Str1]
0x14013f8d5  test    rax, 0FFFFFFFFFFFF0000h
0x14013f8db  jnz     short loc_14013F8EF
0x14013f8dd  mov     rax, [rsp+328h+Str1]
0x14013f8e5  mov     ecx, 8002h
0x14013f8ea  cmp     ax, cx
0x14013f8ed  jz      short loc_14013F92D
0x14013f8ef  call    cs:__imp_PsGetCurrentProcessWin32Process
0x14013f8f6  nop     dword ptr [rax+rax+00h]
0x14013f8fb  mov     rdx, rax
0x14013f8fe  test    rax, rax
0x14013f901  jz      short loc_14013F90F
0x14013f903  mov     rax, [rax]
0x14013f906  neg     rax
0x14013f909  sbb     rcx, rcx
0x14013f90c  and     rdx, rcx
0x14013f90f  mov     eax, [rdx+330h]
0x14013f915  mov     edx, [rsp+328h+var_2D8]
0x14013f919  test    r15b, al
0x14013f91c  jz      short loc_14013F92D
0x14013f91e  bts     edx, 16h
0x14013f922  mov     [rsp+328h+var_270], edx
0x14013f929  mov     [rsp+328h+var_2D8], edx
0x14013f92d  mov     eax, edx
0x14013f92f  mov     ecx, 2200000h
0x14013f934  and     eax, ecx
0x14013f936  cmp     eax, ecx
0x14013f938  jz      loc_14013F613
0x14013f93e  mov     rax, [rsp+328h+var_2A8]
0x14013f946  cmp     [rax+270h], rsi
0x14013f94d  jz      short loc_14013F967
0x14013f94f  mov     edx, 2
0x14013f954  mov     ecx, [rax+3A0h]
0x14013f95a  call    CheckGrantedAccess
0x14013f95f  test    eax, eax
0x14013f961  jz      loc_14013F61D
0x14013f967  mov     eax, 4000h
0x14013f96c  cmp     word ptr [rsp+328h+var_2CC], ax
0x14013f971  jnz     short loc_14013F994
0x14013f973  test    r13, r13
0x14013f976  jnz     short loc_14013F982
0x14013f978  mov     ecx, 57Eh
0x14013f97d  jmp     loc_14013F618
0x14013f982  mov     rdx, r13
0x14013f985  xor     ecx, ecx
0x14013f987  call    ValidateParentDepth
0x14013f98c  test    eax, eax
0x14013f98e  jz      loc_14013F613
0x14013f994  and     r14d, 2000h
0x14013f99b  mov     [rsp+328h+var_29C], r14d
0x14013f9a3  mov     [rsp+328h+var_1F0], r13
0x14013f9ab  mov     r14d, 400h
0x14013f9b1  mov     rax, [rsp+328h+var_1E8]
0x14013f9b9  test    rax, 0FFFFFFFFFFFF0000h
0x14013f9bf  jz      loc_14013FB08
0x14013f9c5  lea     rcx, [rsp+328h+var_228]; this
0x14013f9cd  call    ??0AtomicExecutionCheck@@QEAA@XZ; AtomicExecutionCheck::AtomicExecutionCheck(void)
0x14013f9d2  nop
0x14013f9d3  call    cs:__imp_W32GetUserSessionState
0x14013f9da  nop     dword ptr [rax+rax+00h]
0x14013f9df  lea     r10, [rax+0A254h]
0x14013f9e6  mov     r8, [rsp+328h+var_1E8]
0x14013f9ee  mov     r8, [r8+8]; unsigned __int16 *
0x14013f9f2  mov     edx, 100h; unsigned __int64
0x14013f9f7  mov     rcx, r10; unsigned __int16 *
  ... truncated ...
```
