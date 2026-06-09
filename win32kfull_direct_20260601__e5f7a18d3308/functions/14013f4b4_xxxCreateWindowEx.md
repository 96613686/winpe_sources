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
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 UserSessionState; // rax
  __int64 v38; // r10
  unsigned __int16 v39; // r9
  _QWORD *ClassPtr; // rax
  __int64 v41; // r8
  int v42; // r9d
  unsigned int v43; // r9d
  __int64 v44; // rax
  __int64 v45; // r14
  tagObjLock *v46; // r13
  __int64 v47; // rbx
  tagObjLock *v48; // rax
  unsigned int CurrentThreadDpiHostingBehavior; // eax
  __int64 v50; // rcx
  struct tagWND *v51; // rbx
  struct tagTHREADINFO *v52; // rax
  __int64 v53; // rax
  __int64 v54; // r8
  __int64 v55; // rcx
  int v56; // ebx
  __int64 v57; // rdx
  int v58; // ecx
  unsigned int v59; // r8d
  wchar_t *v60; // rcx
  __int64 v61; // rax
  __int64 v62; // rdx
  __int64 v63; // rdx
  __int16 v64; // bx
  __int64 v65; // rdx
  __int64 *v66; // rax
  __int64 v67; // rcx
  __int64 v68; // rdi
  __int64 v69; // r8
  __int64 v70; // r13
  int v71; // eax
  LONG v72; // r9d
  int v73; // r10d
  struct _HEAD *v74; // rax
  LONG v75; // edx
  LONG v76; // eax
  LONG v77; // ecx
  int v78; // edx
  unsigned int v79; // eax
  struct tagMONITOR *InheritedMonitor; // rbx
  __int64 v81; // rdx
  __int64 v82; // r8
  __int64 v83; // r9
  _DWORD *v84; // rax
  __int64 MessageWindow; // rax
  const struct tagWND *ThreadDesktopWindow; // rdx
  __int64 v87; // r9
  __int64 v88; // rdx
  __int64 v89; // rcx
  __int64 v90; // r8
  char v91; // r12
  __int64 v92; // rax
  int v93; // r13d
  __int64 v94; // rax
  char v95; // r12
  Scrollbar::NonClient *v96; // rcx
  Scrollbar::NonClient *v97; // rcx
  bool v98; // al
  __int64 v99; // rdx
  int v100; // r8d
  unsigned int v101; // ecx
  unsigned int ClientExtraBytesTotalSize; // eax
  __int64 v103; // rdx
  volatile void *v104; // rdi
  _QWORD *v105; // rdx
  __int64 v106; // rcx
  int v107; // ebx
  __int64 v108; // rcx
  __int64 v109; // rdx
  __int64 v110; // rdx
  __int64 v111; // rdx
  __int64 v112; // rcx
  __int16 v113; // di
  __int64 v114; // rdx
  __int64 v115; // rcx
  __int64 v116; // rdx
  __int64 v117; // rcx
  __int64 v118; // rdx
  __int64 v119; // rcx
  __int64 v120; // rdx
  __int64 v121; // rcx
  __int64 v122; // rdx
  __int64 v123; // rcx
  __int64 v124; // rdx
  __int64 v125; // rcx
  __int64 v126; // rdx
  __int64 v127; // rcx
  __int16 v128; // bx
  unsigned __int16 v129; // bx
  char v130; // di
  int v131; // eax
  __int64 v132; // rcx
  int v133; // edx
  int v134; // r12d
  int v135; // edi
  unsigned int v136; // ecx
  __int64 v137; // rdx
  __int64 v138; // r8
  int v139; // r8d
  int v140; // r9d
  __int64 v141; // rbx
  __int16 v142; // di
  int v143; // eax
  int v144; // edx
  __int64 v145; // rcx
  struct tagMONITOR *v146; // rax
  unsigned int v147; // edx
  int v148; // ecx
  __int16 v149; // ax
  _QWORD *v150; // r8
  unsigned int v151; // eax
  int *MonitorRect; // rax
  int v153; // r8d
  int v154; // r9d
  int v155; // r10d
  int v156; // eax
  __int64 v157; // rbx
  __int64 v158; // r8
  __int64 v159; // rcx
  unsigned __int8 *Menu; // rax
  unsigned int WindowCloakStateComponentUIAware; // r12d
  struct _HEAD *v162; // rcx
  struct _HEAD *v163; // rcx
  __int64 NonChildAncestor; // rbx
  __int64 v165; // rdi
  __int64 v166; // rdx
  __int64 v167; // rcx
  __int64 v168; // rcx
  struct tagTHREADINFO *v169; // rdx
  int IsEnabledDeviceUsageNoInline; // eax
  int v171; // ecx
  bool v172; // zf
  unsigned int v173; // eax
  int v174; // edx
  struct tagTHREADINFO *v175; // rdi
  __int64 KernelEvent; // rax
  __int64 v177; // rdi
  struct tagWND **v178; // r13
  __int64 v179; // rdx
  __int64 v180; // rbx
  NTSTATUS v181; // eax
  ULONG v182; // eax
  __int64 v183; // rdx
  __int64 v184; // rcx
  struct tagTHREADINFO **v185; // rax
  __int64 v186; // rax
  struct tagWND *v187; // r9
  __int64 v188; // rax
  int v189; // eax
  int v190; // eax
  __int64 v191; // rax
  struct tagMONITOR *v192; // rbx
  __int64 v193; // rcx
  __int64 v194; // rbx
  __int64 StyleWindow; // rbx
  unsigned int v196; // edx
  __int64 v197; // rdx
  int v198; // ebx
  __int64 v199; // r9
  struct tagTHREADINFO *v200; // rdx
  unsigned __int128 v201; // rax
  unsigned int v202; // ecx
  __int64 v203; // rcx
  __int64 SystemMenu; // rax
  struct _LARGE_UNICODE_STRING *StrName; // rax
  struct tagWND **v206; // rbx
  struct tagWND *DefaultImeWindow; // rax
  int v208; // ecx
  struct tagWND *v209; // rcx
  unsigned __int64 CompositeAppFrameWindowOrSelf; // rbx
  __int64 v211; // rax
  int v212; // ebx
  __int64 v213; // rcx
  struct tagWND *v214; // rdx
  const struct tagWND *v215; // rax
  __int64 TopMostInsertAfter; // rax
  __int64 v217; // rbx
  __int64 v218; // r9
  int v219; // edx
  int v220; // r8d
  __int64 v221; // rdx
  __int64 v222; // r8
  __int64 v223; // r9
  __int64 v224; // rdx
  __int64 v225; // rcx
  __int64 v226; // r8
  void *v227; // rax
  __int64 v228; // rdx
  __int64 v229; // rcx
  __int64 v230; // r8
  void *v231; // rax
  __int64 v232; // rdx
  __int64 v233; // rcx
  __int64 v234; // r8
  __int64 DesktopWindow; // rax
  __int64 v236; // rdx
  unsigned int v237; // ebx
  __int64 v238; // rdi
  char v239; // cl
  __int64 v240; // rdx
  __int64 v241; // rdx
  __int64 v242; // rcx
  __int64 v243; // rax
  _QWORD *v244; // rbx
  __int64 v245; // rax
  __int64 v246; // rbx
  unsigned int v247; // [rsp+50h] [rbp-2D8h]
  unsigned __int64 v248; // [rsp+54h] [rbp-2D4h]
  __int16 v249; // [rsp+5Ch] [rbp-2CCh]
  int v250; // [rsp+5Ch] [rbp-2CCh]
  __int64 v251; // [rsp+68h] [rbp-2C0h]
  unsigned __int16 v252; // [rsp+70h] [rbp-2B8h]
  int v253; // [rsp+70h] [rbp-2B8h]
  unsigned int v254; // [rsp+74h] [rbp-2B4h]
  struct tagWND *v255; // [rsp+78h] [rbp-2B0h]
  int v256; // [rsp+8Ch] [rbp-29Ch]
  int v257; // [rsp+8Ch] [rbp-29Ch]
  _QWORD v258[2]; // [rsp+90h] [rbp-298h] BYREF
  _QWORD *v259; // [rsp+A0h] [rbp-288h]
  wchar_t *Str1; // [rsp+A8h] [rbp-280h]
  int *v261; // [rsp+B0h] [rbp-278h]
  int v262; // [rsp+B8h] [rbp-270h]
  int Atom; // [rsp+C0h] [rbp-268h]
  int v264; // [rsp+C4h] [rbp-264h]
  __int64 v265; // [rsp+C8h] [rbp-260h]
  struct tagRECT v266; // [rsp+D0h] [rbp-258h] BYREF
  int v267; // [rsp+E0h] [rbp-248h]
  int v268; // [rsp+E4h] [rbp-244h]
  _QWORD v269[2]; // [rsp+E8h] [rbp-240h] BYREF
  struct _HEAD *v270; // [rsp+F8h] [rbp-230h]
  ULONG_PTR v271[2]; // [rsp+100h] [rbp-228h] BYREF
  unsigned __int16 v272; // [rsp+110h] [rbp-218h]
  __int64 v273; // [rsp+118h] [rbp-210h]
  void *v274; // [rsp+120h] [rbp-208h]
  ULONG_PTR v275[2]; // [rsp+128h] [rbp-200h] BYREF
  __int64 v276; // [rsp+138h] [rbp-1F0h]
  __int64 v277; // [rsp+140h] [rbp-1E8h]
  __int64 v278; // [rsp+148h] [rbp-1E0h] BYREF
  __int64 v279; // [rsp+150h] [rbp-1D8h]
  struct tagWND *v280; // [rsp+158h] [rbp-1D0h]
  _QWORD *v281; // [rsp+160h] [rbp-1C8h]
  ULONG_PTR v282[2]; // [rsp+170h] [rbp-1B8h] BYREF
  __int128 v283; // [rsp+180h] [rbp-1A8h] BYREF
  int v284; // [rsp+190h] [rbp-198h]
  int v285; // [rsp+1BCh] [rbp-16Ch]
  _QWORD v286[2]; // [rsp+1D0h] [rbp-158h] BYREF
  struct _HEAD *v287; // [rsp+1E0h] [rbp-148h]
  __int64 v288; // [rsp+1E8h] [rbp-140h]
  unsigned int v289; // [rsp+1F0h] [rbp-138h]
  int v290; // [rsp+1F4h] [rbp-134h]
  LONG v291; // [rsp+1F8h] [rbp-130h]
  unsigned int v292; // [rsp+1FCh] [rbp-12Ch]
  unsigned int v293; // [rsp+200h] [rbp-128h]
  __int64 v294; // [rsp+208h] [rbp-120h]
  wchar_t *v295; // [rsp+210h] [rbp-118h]
  unsigned int v296; // [rsp+218h] [rbp-110h]
  int v297; // [rsp+220h] [rbp-108h]
  int v298; // [rsp+224h] [rbp-104h]
  __int64 v299; // [rsp+228h] [rbp-100h]
  __int128 v300; // [rsp+230h] [rbp-F8h] BYREF
  wchar_t *v301; // [rsp+240h] [rbp-E8h]
  struct tagTHREADINFO **v302; // [rsp+248h] [rbp-E0h]
  _QWORD *v303; // [rsp+250h] [rbp-D8h]
  ULONG_PTR BugCheckParameter3[2]; // [rsp+258h] [rbp-D0h] BYREF
  int v305; // [rsp+268h] [rbp-C0h]
  int *v306; // [rsp+270h] [rbp-B8h] BYREF
  __int128 v307; // [rsp+280h] [rbp-A8h] BYREF
  __int64 v308; // [rsp+290h] [rbp-98h]
  _BYTE v309[40]; // [rsp+2A0h] [rbp-88h] BYREF
  __int128 v310; // [rsp+2C8h] [rbp-60h] BYREF
  __int128 v311; // [rsp+2D8h] [rbp-50h] BYREF

  v306 = a4;
  v301 = a2;
  v267 = a1;
  v247 = a1;
  v262 = a1;
  Str1 = a2;
  v277 = a3;
  v261 = a4;
  v18 = (__int64)a10;
  v255 = a10;
  v273 = (__int64)a10;
  v274 = a12;
  *(_QWORD *)&v266.left = a13;
  SmartObjStackRef<tagCLS>::SmartObjStackRef<tagCLS>(v258);
  v311 = 0;
  v310 = 0;
  memset_0(v286, 0, 0x70u);
  v19 = PtiCurrent();
  Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(v275);
  v307 = 0;
  v308 = 0;
  v259 = (_QWORD *)((char *)v19 + 456);
  v20 = *(_DWORD *)(*((_QWORD *)v19 + 57) + 12LL);
  v283 = 0;
  SmartObjStackRef<tagMENU>::SmartObjStackRef<tagMENU>(v269, a11);
  AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)&v278);
  if ( (*(_DWORD *)(*((_QWORD *)v19 + 57) + 12LL) & 0x10000000) == 0 && !(unsigned int)RegisterIconTitleClass() )
    goto LABEL_3;
  if ( a1 < 0 )
  {
    v247 = a1 & 0x7FFFFFFF;
    v262 = a1 & 0x7FFFFFFF;
  }
  v23 = 800;
  if ( a1 >= 0 )
    v23 = 0;
  v252 = v23;
  v24 = *((_QWORD *)v19 + 61);
  v281 = (_QWORD *)v24;
  v282[0] = v24;
  if ( a10 )
  {
    if ( *((_QWORD *)a10 + 3) != v24 )
      goto LABEL_3;
  }
  v25 = 0;
  if ( (a16 & 1) != 0 )
  {
    if ( (unsigned int)IsDesktopApp(*v259) )
    {
LABEL_45:
      v21 = 5;
      goto LABEL_4;
    }
    v25 = 1;
  }
  v268 = a16 & 2;
  if ( (a16 & 2) != 0 && !(unsigned int)IsImmersiveBroker(*v259) )
    goto LABEL_45;
  v26 = a14;
  if ( !a14 )
  {
LABEL_26:
    v27 = v259;
    goto LABEL_27;
  }
  if ( !(unsigned int)IsValidBand(a14) || a14 == 15 )
    goto LABEL_3;
  v27 = v259;
  v28 = *(_QWORD *)(*v259 + 808LL);
  if ( (v28 & 0x30) == 0x10 && (v28 & 0x200) == 0 && a14 == 1 && !v25 )
  {
    if ( !(unsigned int)HasMessageRootWindow(a10) )
      goto LABEL_3;
    goto LABEL_26;
  }
LABEL_27:
  v249 = HIWORD(a5) & 0xC000;
  v285 = (HIWORD(a5) & 0xC000) == 0x4000;
  if ( (HIWORD(a5) & 0xC000) != 0x4000 )
  {
    if ( (unsigned int)ShouldSetNoOwner(*v27, a10) )
      v18 = 0;
    v255 = (struct tagWND *)v18;
    v273 = v18;
  }
  if ( !v18 || (unsigned int)IsDesktopWindow(v18) )
  {
    if ( !a14 )
    {
      if ( (unsigned int)IsImmersiveAppIORestricted(*v259) )
      {
        v25 = 1;
        v26 = 15;
      }
      else if ( (*(_BYTE *)(v30 + 808) & 2) != 0 && (v247 & 8) != 0 )
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
  if ( !(unsigned __int8)IsValidBandForProcess(*v259, v26, v18) )
    goto LABEL_45;
  v31 = v247;
  if ( (v247 & 0x400000) == 0 )
  {
    if ( v18 )
    {
      if ( v249 != 0x4000 || (*(_BYTE *)(*(_QWORD *)(v18 + 40) + 26LL) & 0x50) != 0x40 )
        goto LABEL_58;
      v31 = v247 | 0x400000;
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
      v31 = v247;
      if ( (v34 & 1) == 0 )
        goto LABEL_58;
      v31 = v247 | 0x400000;
    }
    v262 = v31;
    v247 = v31;
  }
LABEL_58:
  if ( (v31 & 0x2200000) == 0x2200000 )
    goto LABEL_3;
  if ( *((_QWORD *)v19 + 78) && !(unsigned int)CheckGrantedAccess(*((unsigned int *)v19 + 232), 2) )
    goto LABEL_5;
  if ( v249 == 0x4000 )
  {
    if ( !v18 )
    {
      v21 = 1406;
LABEL_4:
      UserSetLastError(v21);
LABEL_5:
      AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)&v278);
LABEL_6:
      SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(v269);
      Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)v275);
      SmartObjStackRef<tagPOPUPMENU>::~SmartObjStackRef<tagPOPUPMENU>(v258);
      return 0;
    }
    if ( !(unsigned int)ValidateParentDepth(0, v18) )
    {
LABEL_3:
      v21 = 87;
      goto LABEL_4;
    }
  }
  v256 = v20 & 0x2000;
  v276 = v18;
  while ( 1 )
  {
    if ( (v277 & 0xFFFFFFFFFFFF0000uLL) != 0 )
    {
      AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)v271);
      UserSessionState = W32GetUserSessionState(v36, v35);
      if ( (int)RtlStringCchCopyW(
                  (unsigned __int16 *)(UserSessionState + 41556),
                  0x100u,
                  *(const unsigned __int16 **)(v277 + 8)) < 0 )
      {
        Atom = 0;
        v256 = 1;
        v284 = 1;
      }
      else
      {
        Atom = (unsigned __int16)UserFindAtom(v38);
      }
      AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v271);
    }
    else
    {
      v39 = v277;
      Atom = v277;
    }
    if ( v39 )
    {
      ClassPtr = (_QWORD *)GetClassPtr(v39, *v259, v274);
      if ( ClassPtr )
        break;
    }
LABEL_107:
    if ( v256
      || (*(_DWORD *)(*((_QWORD *)PtiCurrent() + 57) + 12LL) & 0x2000) != 0
      || (((unsigned __int64)Str1 & 0xFFFFFFFFFFFF0000uLL) == 0
        ? (v60 = Str1)
        : (v60 = (wchar_t *)*((_QWORD *)Str1 + 1)),
          !(unsigned int)RegisterDefaultClass(v60)) )
    {
      v21 = 1407;
      goto LABEL_4;
    }
    v256 = 1;
    v24 = (ULONG_PTR)v281;
  }
  SmartObjStackRefBase<tagCLS>::operator=(v258, *ClassPtr);
  if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)v258[0] + 8LL) + 6LL) & 1) != 0 && (unsigned int)PsGetWin32KFilterSet() == 5 )
    goto LABEL_5;
  v272 = a15;
  if ( (unsigned int)NeedsWindowEdge(a5, v247, a15 >= 0x400u) )
    v43 = v42 | 0x100;
  else
    v43 = v42 & 0xFFFFFEFF;
  v262 = v43;
  v247 = v43;
  if ( (_InterlockedCompareExchange((volatile signed __int32 *)v19 + 130, 0, 0) & 1) != 0 )
  {
    v264 = 0x20000;
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 853);
  }
  LOBYTE(v41) = 1;
  v44 = HMAllocObject(v19, v24, v41, 416);
  v45 = v44;
  v280 = (struct tagWND *)v44;
  if ( !v44 )
  {
    if ( (unsigned int)UserGetLastError() == 8 )
      TraceLoggingCreateWindowFailed(
        1u,
        (((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
       * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64);
    goto LABEL_5;
  }
  v46 = (tagObjLock *)(v44 + 56);
  tagObjLock::LockInitialize((tagObjLock *)(v44 + 56));
  v47 = v45 + 40;
  v251 = v45 + 40;
  *(_DWORD *)(*(_QWORD *)(v45 + 40) + 328LL) = (unsigned int)PsGetThreadId(*(PETHREAD *)v19);
  *(_DWORD *)(*(_QWORD *)(v45 + 40) + 332LL) = *(_DWORD *)(*v259 + 56LL);
  *(_QWORD *)(v45 + 328) = v45 + 320;
  *(_QWORD *)(v45 + 320) = v45 + 320;
  *(_QWORD *)(v45 + 344) = v45 + 336;
  *(_QWORD *)(v45 + 336) = v45 + 336;
  *(_QWORD *)(v45 + 360) = v45 + 352;
  *(_QWORD *)(v45 + 352) = v45 + 352;
  *(_QWORD *)(v45 + 408) = v45 + 400;
  *(_QWORD *)(v45 + 400) = v45 + 400;
  *(_DWORD *)(v45 + 396) = 5;
  *(_DWORD *)(v45 + 392) = 1;
  v48 = (tagObjLock *)Win32AllocPoolZInit(32, 1752200021);
  *(_QWORD *)(v45 + 144) = v48;
  if ( !v48 )
  {
    tagObjLock::LockUnInitializeThreadCreator(v46);
    HMFreeObject(v45);
    goto LABEL_5;
  }
  tagObjLock::LockInitialize(v48);
  v302 = (struct tagTHREADINFO **)(v45 + 16);
  if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v45 + 16) + 456LL) + 808LL) & 0x1000000) != 0 )
    *(_DWORD *)(v45 + 384) |= 1u;
  *(_QWORD *)(*(_QWORD *)v47 + 296LL) = 0;
  *(_QWORD *)(v45 + 280) = 0;
  *(_DWORD *)(v45 + 180) = -1;
  *(_QWORD *)(*(_QWORD *)v47 + 168LL) = 0;
  CurrentThreadDpiHostingBehavior = W32GetCurrentThreadDpiHostingBehavior();
  v50 = CurrentThreadDpiHostingBehavior;
  *(_DWORD *)(*(_QWORD *)v47 + 292LL) = CurrentThreadDpiHostingBehavior;
  if ( v249 == 0x4000 )
  {
    if ( v255 && v255 != (struct tagWND *)GetThreadDesktopWindow(0) )
    {
      v51 = 0;
      v52 = PtiCurrent();
      if ( v52 )
      {
        v53 = *((_QWORD *)v52 + 61);
        if ( v53 )
          v51 = *(struct tagWND **)(v53 + 112);
      }
      if ( v255 != v51 )
      {
        v50 = *(_QWORD *)(*((_QWORD *)v255 + 2) + 456LL);
        if ( *v259 == v50 && !IsChildWindowDpiIsolationEnabled(0, v255) )
        {
          v54 = v276;
          v55 = *(_QWORD *)v251;
          *(_DWORD *)(v55 + 288) = *(_DWORD *)(*(_QWORD *)(v276 + 40) + 288LL);
          v56 = *(_DWORD *)(*(_QWORD *)(v54 + 40) + 288LL);
          if ( (((unsigned __int8)v56 ^ (unsigned __int8)W32GetCurrentThreadDpiAwarenessContext(v55)) & 0xF) != 0 )
            TraceChildWindowDpiTelemetry(v45, v255, 0);
          v47 = v45 + 40;
          goto LABEL_100;
        }
      }
    }
    v47 = v45 + 40;
  }
  *(_DWORD *)(*(_QWORD *)v47 + 288LL) = W32GetCurrentThreadDpiAwarenessContext(v50);
  if ( (*(_DWORD *)(*(_QWORD *)v47 + 288LL) & 0x4000000F) == 0 )
  {
    v61 = PsGetCurrentProcessWin32Process();
    v62 = v61;
    if ( v61 )
      v62 = -(__int64)(*(_QWORD *)v61 != 0) & v61;
    if ( (*(_DWORD *)(v62 + 12) & 0x20000000) != 0 )
      *(_DWORD *)(*(_QWORD *)v47 + 288LL) |= 0x40000000u;
  }
LABEL_100:
  v57 = *(_QWORD *)v47;
  v58 = *(_DWORD *)(*(_QWORD *)v47 + 288LL);
  if ( (v58 & 0xF) == 2 && (v58 & 0xF0) == 0x20 )
    *(_DWORD *)(v45 + 380) |= 0x180000u;
  if ( (*(_BYTE *)(v57 + 288) & 0xF) == 3 )
    *(_DWORD *)(v45 + 380) |= 0x80000u;
  v303 = (_QWORD *)(v45 + 136);
  tagWND::SharedMixedObjectPointerFieldpcls<tagCLS>::operator=(v45 + 136, *(_QWORD *)v258[0]);
  *(_DWORD *)(*(_QWORD *)v47 + 28LL) = a5 & 0xEFFFFFFF;
  *(_DWORD *)(*(_QWORD *)v47 + 24LL) = v247 & 0xFDF7FFFF;
  *(_DWORD *)(*(_QWORD *)v47 + 200LL) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v258[0] + 8LL) + 80LL);
  *(_DWORD *)(*(_QWORD *)v47 + 248LL) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v258[0] + 8LL) + 84LL);
  if ( !(unsigned int)ReferenceClass(*(_QWORD *)v258[0], v45, v59) )
    goto LABEL_106;
  v265 = v47;
  SmartObjStackRefBase<tagCLS>::operator=(v258, *v303);
  if ( !(unsigned int)ClassLock(*(_QWORD *)v258[0], &v307) )
  {
    DereferenceClass(*v259, v45);
LABEL_106:
    tagObjLock::LockUnInitializeThreadCreator(*(tagObjLock **)(v45 + 144));
    Win32FreePool(*(void **)(v45 + 144));
    tagObjLock::LockUnInitializeThreadCreator(v46);
    HMFreeObject(v45);
    goto LABEL_107;
  }
  v257 = 0;
  *(_QWORD *)(*(_QWORD *)v47 + 224LL) = a17;
  v64 = *(_WORD *)(*(_QWORD *)(*(_QWORD *)v258[0] + 8LL) + 2LL);
  if ( v64 == *(_WORD *)(*(_QWORD *)(W32GetUserSessionState(*(_QWORD *)v258[0], v63) + 19704) + 868LL) )
  {
    v65 = v45 + 40;
    *(_QWORD *)(*(_QWORD *)v251 + 208LL) = 0;
  }
  else
  {
    v66 = (__int64 *)*((_QWORD *)v19 + 103);
    v67 = 0;
    if ( v66 )
      v67 = *v66;
    v65 = v45 + 40;
    *(_QWORD *)(*(_QWORD *)v251 + 208LL) = v67;
  }
  *(_DWORD *)(*(_QWORD *)v65 + 236LL) = v26;
  v68 = v45 + 40;
  v69 = *(_QWORD *)v251;
  v70 = (__int64)v255;
  if ( *(_DWORD *)(*(_QWORD *)v251 + 236LL) == 1 )
    v71 = 0;
  else
    v71 = IsTopLevelParent(v255);
  if ( v71 )
    *(_DWORD *)(v69 + 24) |= 8u;
  if ( v25 )
    SetOrClrWF(1, v45, 55360, 0);
  v282[0] = (ULONG_PTR)v19 + 932;
  ++*((_DWORD *)v19 + 233);
  memset_0(v286, 0, 0x70u);
  v296 = v247;
  v286[1] = v274;
  if ( ((unsigned __int64)Str1 & 0xFFFFFFFFFFFF0000uLL) != 0 )
  {
    if ( v267 >= 0 )
    {
      v295 = (wchar_t *)*((_QWORD *)Str1 + 1);
      v300 = *(_OWORD *)v301;
    }
    else
    {
      v295 = *(wchar_t **)(*(_QWORD *)v258[0] + 104LL);
      if ( ((unsigned __int64)v295 & 0xFFFFFFFFFFFF0000uLL) != 0 )
        RtlInitLargeAnsiString(&v300);
    }
  }
  else
  {
    v295 = Str1;
  }
  if ( v261 )
  {
    v294 = *((_QWORD *)v261 + 1);
    v297 = *v306;
    v298 = v306[1];
    v299 = *((_QWORD *)v306 + 1);
  }
  v293 = a5;
  v72 = a6;
  v248 = __PAIR64__(a7, a6);
  v292 = a6;
  v291 = a7;
  v73 = a8;
  LODWORD(Str1) = a8;
  v290 = a8;
  v254 = a9;
  v289 = a9;
  if ( v255 )
    v288 = *(_QWORD *)v255;
  else
    v288 = 0;
  if ( v249 == 0x4000 )
  {
    v74 = v270;
    if ( !v270 )
      v74 = *(struct _HEAD **)v269[0];
    v287 = v74;
    *(_DWORD *)(*(_QWORD *)v251 + 24LL) |= *(_DWORD *)(*(_QWORD *)(v276 + 40) + 24LL) & 0xC4000000;
    v75 = a7;
  }
  else if ( (unsigned __int8)SmartObjStackRef<tagMENU>::operator==(v269) )
  {
    v287 = 0;
  }
  else
  {
    v287 = **(struct _HEAD ***)v269[0];
  }
  v286[0] = *(_QWORD *)&v266.left;
  *(_QWORD *)&v266.left = 0;
  if ( v72 == 0x80000000 || (v76 = v72, v72 == 0x8000) )
    v76 = 0;
  v266.left = v76;
  if ( v75 == 0x80000000 || v75 == 0x8000 )
  {
    v77 = 0;
    v266.top = 0;
  }
  else
  {
    v77 = v75;
    v266.top = v75;
  }
  if ( v73 == 0x80000000 || (v78 = v73, v73 == 0x8000) )
    v78 = 0;
  v266.right = v78 + v76;
  if ( a9 == 0x80000000 || (v79 = a9, a9 == 0x8000) )
    v79 = 0;
  v266.bottom = v77 + v79;
  InheritedMonitor = (struct tagMONITOR *)GetInheritedMonitor((struct tagWND *)v45);
  if ( InheritedMonitor )
  {
    v264 = 1;
  }
  else
  {
    v264 = 0;
    if ( v255 )
      InheritedMonitor = (struct tagMONITOR *)ValidateHmonitorNoRip(*(_QWORD *)(*(_QWORD *)(v276 + 40) + 256LL));
  }
  if ( !InheritedMonitor )
    InheritedMonitor = (struct tagMONITOR *)MonitorFromRect(&v266, 2);
  UpdateWindowMonitorAndDpiInfoHelper((struct tagWND *)v45, InheritedMonitor);
  *(_WORD *)(*(_QWORD *)v251 + 286LL) = 0;
  *(_QWORD *)(v45 + 296) = 0;
  if ( v249 != 0x4000 || IsDpiBoundaryBetweenWindows((const struct tagWND *)v45, v255) )
    UpdateTopLevelWindowDPITransform(v45, InheritedMonitor);
  if ( v249 == 0x4000 )
  {
    if ( v255 )
    {
      *(_WORD *)(*(_QWORD *)v251 + 286LL) = *(_WORD *)(*(_QWORD *)(v276 + 40) + 286LL);
      v84 = (_DWORD *)*((_QWORD *)v255 + 37);
      if ( v84 )
      {
        *(_QWORD *)(v45 + 296) = v84;
        ++*v84;
      }
    }
  }
  v281 = (_QWORD *)(v45 + 24);
  if ( *(_QWORD *)(v45 + 24) )
  {
    MessageWindow = GetMessageWindow(v45);
    *(_OWORD *)v271 = *(_OWORD *)LockPointer(&v306, v45 + 104, MessageWindow);
    HMAssignmentLock(v271, 0);
  }
  if ( (unsigned int)IsWindowDesktopComposed(v45, v81, v82, v83) )
  {
    ThreadDesktopWindow = v255;
    if ( v249 != 0x4000 && (!v255 || v255 != *(struct tagWND **)(*((_QWORD *)v255 + 3) + 112LL)) )
      ThreadDesktopWindow = (const struct tagWND *)GetThreadDesktopWindow(0);
    DwmWindowCreate((struct tagWND *)v45, ThreadDesktopWindow, &v266);
  }
  *(_QWORD *)(*(_QWORD *)v251 + 32LL) = v274;
  *(_QWORD *)(*(_QWORD *)v251 + 120LL) = MapClientNeuterToClientPfn(*(_QWORD *)v258[0], 0, v252);
  v87 = 1;
  v88 = v45;
  if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)v258[0] + 8LL) + 6LL) & 1) != 0 )
  {
    SetOrClrWF(1, v45, 516, 1);
    v89 = 1;
    v88 = v45;
    v90 = 55812;
    v87 = 0;
  }
  else
  {
    v89 = 0;
    v90 = 516;
  }
  SetOrClrWF(v89, v88, v90, v87);
  if ( (*(_BYTE *)(*(_QWORD *)v251 + 30LL) & 0x30) != 0 && (*(_BYTE *)(*(_QWORD *)v251 + 234LL) & 4) != 0 )
  {
    LODWORD(v261) = 0x20000;
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 1206);
  }
  AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)&v278);
  Win32HMThreadLockAlways<tagHOOK>::Win32HMThreadLockAlways<tagHOOK>(BugCheckParameter3, v19, v45);
  v91 = *(_BYTE *)(*(_QWORD *)v251 + 18LL);
  if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v258[0] + 8LL) + 84LL) )
  {
    v92 = Win32AllocPoolZInit(*(unsigned int *)(*(_QWORD *)(*(_QWORD *)v258[0] + 8LL) + 84LL), 1937208149);
    *(_QWORD *)(v45 + 280) = v92;
    if ( !v92 )
    {
      v93 = 5;
      v94 = *(_QWORD *)v251;
      goto LABEL_192;
    }
  }
  v95 = v91 & 4;
  LODWORD(v261) = 0;
  if ( (unsigned int)PsGetWin32KFilterSet() != 5 )
  {
LABEL_196:
    if ( v95 )
      goto LABEL_205;
    if ( (unsigned int)PsGetWin32KFilterSet() == 5 )
    {
      *(_DWORD *)(*(_QWORD *)v251 + 200LL) = (*(_DWORD *)(*(_QWORD *)v251 + 200LL) + 7) & 0xFFFFFFF8;
    }
    else
    {
      if ( !(unsigned int)Feature_UserModeNonClientScrollBars2__private_IsEnabledDeviceUsageNoInline()
        || !Scrollbar::NonClient::UserModeSupportsUserModeScrollBars(v96) )
      {
        goto LABEL_205;
      }
      v98 = Scrollbar::NonClient::UserModeSupportsPartitionedExtraBytes(v97);
      v99 = *(_QWORD *)v251;
      v100 = *(_DWORD *)(*(_QWORD *)v251 + 200LL);
      v101 = (v100 + 7) & 0xFFFFFFF8;
      if ( v98 )
      {
        *(_DWORD *)(v99 + 336) = v101 - v100;
        *(_DWORD *)(*(_QWORD *)v251 + 336LL) += 48;
        goto LABEL_205;
      }
      *(_DWORD *)(v99 + 200) = v101;
    }
    *(_DWORD *)(*(_QWORD *)v251 + 200LL) += 48;
    goto LABEL_205;
  }
  if ( !v95 )
  {
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 1245);
    goto LABEL_196;
  }
LABEL_205:
  ClientExtraBytesTotalSize = GetClientExtraBytesTotalSize((const struct tagWND *)v45);
  if ( ClientExtraBytesTotalSize )
  {
    v104 = xxxClientAllocWindowClassExtraBytes(ClientExtraBytesTotalSize, v103);
    if ( !v104 )
    {
      v93 = 2;
      v94 = *(_QWORD *)v251;
LABEL_192:
      *(_QWORD *)(v94 + 120) = 0;
      SetOrClrWF(1, v45, 516, 1);
LABEL_476:
      v198 = *(_BYTE *)(*(_QWORD *)v265 + 31LL) & 0x10;
      if ( v257 )
        Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)v275);
      SetOrClrWF(1, v45, 1152, 1);
      SetOrClrWF(1, v45, 896, 1);
      if ( v198 )
        SetVisible(v45, 0);
      if ( *(_QWORD *)(v45 + 104) )
      {
        if ( v198 )
          zzzLockDisplayAreaAndInvalidateDCCache(*(_QWORD *)(v45 + 104), 16);
        if ( (*(_BYTE *)(*(_QWORD *)v265 + 31LL) & 0xC0) == 0x40 && !(unsigned int)IsTopLevelWindow(v45) )
        {
          v200 = *(struct tagTHREADINFO **)(v199 + 16);
          if ( v19 != v200 )
            zzzAttachThreadInput(*v302, v200);
        }
        UnlinkWindow((struct tagWND *)v45);
      }
      ClassUnlock(*(struct tagCLS **)v258[0]);
      xxxFreeWindow(v19, (struct tagWND *)v45);
      if ( v93 )
      {
        v201 = ((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
             * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8);
        v202 = v93;
        goto LABEL_542;
      }
      goto LABEL_543;
    }
    if ( (unsigned int)IsWindowBeingDestroyed(v45)
      || (*(_BYTE *)(_HMPheFromObject(v45) + 25) & 1) != 0
      || *(_QWORD *)(*(_QWORD *)v251 + 296LL) )
    {
      UserSetLastError(87);
      *(_QWORD *)(*(_QWORD *)v251 + 120LL) = 0;
      SetOrClrWF(1, v45, 516, 1);
      v93 = 0;
      goto LABEL_476;
    }
    *(_QWORD *)(*(_QWORD *)v251 + 296LL) = v104;
    v68 = v45 + 40;
  }
  if ( (unsigned int)PsGetWin32KFilterSet() != 5 || v95 )
  {
    v107 = v267;
  }
  else
  {
    v105 = (_QWORD *)GETCLIENTWNDINFO(v45);
    v106 = *(_QWORD *)(*(_QWORD *)v265 + 120LL);
    *v105 = v106;
    v107 = v267;
    v108 = *(_QWORD *)(W32GetUserSessionState(v106, v105) + 19704);
    if ( v107 >= 0 )
      v109 = *(_QWORD *)(v108 + 768);
    else
      v109 = *(_QWORD *)(v108 + 576);
    *(_QWORD *)(*(_QWORD *)v68 + 120LL) = v109;
  }
  if ( *(_QWORD *)(*(_QWORD *)v258[0] + 80LL)
    && !*(_QWORD *)(*(_QWORD *)v258[0] + 112LL)
    && (unsigned int)PsGetWin32KFilterSet() != 5 )
  {
    xxxCreateClassSmIcon(v258);
  }
  SetOrClrWF(1, v45, v252, 1);
  if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)v258[0] + 8LL) + 6LL) & 2) != 0 )
    goto LABEL_235;
  if ( v107 < 0 )
  {
    v112 = *(_QWORD *)(W32GetUserSessionState(*(_QWORD *)v258[0], v110) + 19704);
    v113 = Atom;
    if ( (_WORD)Atom == *(_WORD *)(v112 + 868)
      || (v115 = *(_QWORD *)(W32GetUserSessionState(v112, v111) + 19704), v113 == *(_WORD *)(v115 + 878))
      || (v117 = *(_QWORD *)(W32GetUserSessionState(v115, v114) + 19704), v113 == *(_WORD *)(v117 + 882))
      || (v119 = *(_QWORD *)(W32GetUserSessionState(v117, v116) + 19704), v113 == *(_WORD *)(v119 + 904))
      || (v121 = *(_QWORD *)(W32GetUserSessionState(v119, v118) + 19704), v113 == *(_WORD *)(v121 + 870))
      || (v123 = *(_QWORD *)(W32GetUserSessionState(v121, v120) + 19704), v113 == *(_WORD *)(v123 + 874))
      || (v125 = *(_QWORD *)(W32GetUserSessionState(v123, v122) + 19704), v113 == *(_WORD *)(v125 + 880))
      || (v127 = *(_QWORD *)(W32GetUserSessionState(v125, v124) + 19704), v113 == *(_WORD *)(v127 + 898))
      || v113 == *(_WORD *)(*(_QWORD *)(W32GetUserSessionState(v127, v126) + 19704) + 872LL) )
    {
LABEL_235:
      SetOrClrWF(1, v45, 520, 1);
    }
  }
  if ( ((*(_BYTE *)(*(_QWORD *)(*(_QWORD *)v258[0] + 8LL) + 6LL) & 2) != 0 || v107 < 0)
    && v249 != 0x4000
    && (*(_QWORD *)&v266.left = PsGetProcessPeb(**((_QWORD **)*v302 + 57))) != 0 )
  {
    v128 = *(_WORD *)(*(_QWORD *)&v266.left + 844LL);
    if ( v128 == -535 )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 1404);
    if ( v128 == -10600 )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 1405);
    v129 = a15;
    v130 = v247;
  }
  else
  {
    v129 = a15;
    v130 = v247;
  }
  if ( (GetAppCompatFlags(v19) & 0x8000000) != 0 )
  {
    SetOrClrWF(1, v45, 1032, 1);
    v247 = v130 & 0x3F;
    v296 &= 0x3Fu;
  }
  SetOrClrWF(1, v45, 1281, 1);
  SetOrClrWF(1, v45, 1282, 1);
  SetOrClrWF(1, v45, 1284, 1);
  v131 = v129;
  if ( v129 <= *((_WORD *)v19 + 334) )
    v131 = *((_DWORD *)v19 + 167);
  *(_DWORD *)(v45 + 256) = v131;
  if ( (GetAppCompatFlags2(39168) & 0x10000000) != 0 )
    SetOrClrWF(1, v45, 2688, 1);
  if ( (unsigned int)IsInsideUserApiHook() )
    xxxLoadUserApiHook();
  if ( (unsigned int)WantImeWindow(v255, (struct tagWND *)v45) )
  {
    v132 = *((_QWORD *)v19 + 102);
    if ( v132
      && ((*(_BYTE *)(_HMPheFromObject(v132) + 25) & 1) != 0
       || (unsigned int)IsWindowBeingDestroyed(*((_QWORD *)v19 + 102))) )
    {
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1489);
    }
    *(_DWORD *)(v45 + 380) |= 0x10000000u;
    ++*((_DWORD *)v19 + 235);
  }
  if ( ((*((_BYTE *)v19 + 712) | *(_BYTE *)(**((_QWORD **)v19 + 62) + 16LL)) & 0x40) != 0 )
  {
    v278 = (__int64)v286;
    v279 = 0;
    if ( (unsigned int)xxxCallHook(3, *(_QWORD *)v45, (__int64)&v278, 5) )
    {
      v93 = 6;
      goto LABEL_476;
    }
    v248 = __PAIR64__(v291, v292);
    LODWORD(Str1) = v290;
    v254 = v289;
    v273 = v279;
  }
  else
  {
    v273 = 0;
  }
  if ( (*(_BYTE *)(*(_QWORD *)v251 + 31LL) & 0xC0) != 0x40 )
  {
    v133 = 0;
    v250 = 0;
    goto LABEL_269;
  }
  v133 = 1;
  v250 = 1;
  if ( !v255 )
    goto LABEL_475;
LABEL_269:
  v134 = 0;
  v253 = 5;
  if ( v133 != v285 )
  {
    v270 = 0;
    SmartObjStackRefBase<tagMENU>::operator=(v269, 0);
    v133 = v250;
  }
  if ( (*(_BYTE *)(*(_QWORD *)v251 + 31LL) & 0xC0) != 0 )
  {
    v135 = 0;
    if ( (_DWORD)v248 == 0x80000000 || (_DWORD)v248 == 0x8000 )
      v248 = 0;
    v136 = (unsigned int)Str1;
    if ( (_DWORD)Str1 == 0x80000000 || (_DWORD)Str1 == 0x8000 )
    {
      v136 = 0;
      LODWORD(Str1) = 0;
      v254 = 0;
    }
  }
  else
  {
    v135 = 1;
    v136 = (unsigned int)Str1;
  }
  *(_QWORD *)&v310 = v248;
  *((_QWORD *)&v310 + 1) = __PAIR64__(v254, v136);
  if ( v133 )
  {
    v283 = *(_OWORD *)(*(_QWORD *)(v276 + 40) + 104LL);
    if ( IsDpiBoundaryBetweenWindows((const struct tagWND *)v45, v255) )
    {
      *(_DWORD *)(v45 + 224) = 0;
      *(_DWORD *)(v45 + 228) = 0;
      LogicalToPhysicalInPlaceRectWithSubpixel(v255, &v283, v45 + 224);
      PhysicalToLogicalInPlaceRectWithSubpixel(v45, &v283, v45 + 224);
      v138 = (unsigned int)v310;
    }
    if ( v255 != (struct tagWND *)GetDesktopWindow(v45, v137, v138) )
    {
      LODWORD(v310) = v283 + v139;
      DWORD1(v310) = DWORD1(v283) + v140;
    }
    v273 = 1;
  }
  if ( v135 )
  {
    v141 = 0;
    SetOrClrWF(1, v45, 3844, 1);
    v142 = 192;
    SetOrClrWF(1, v45, 2305, 1);
    SetOrClrWF(1, v45, 16, 1);
    v143 = v248;
    if ( (_DWORD)v248 == 0x80000000 || (_DWORD)v248 == 0x8000 )
    {
      if ( DWORD1(v310) != 0x80000000 )
      {
        v144 = 5;
        if ( DWORD1(v310) != 0x8000 )
          v144 = DWORD1(v310);
        v253 = v144;
      }
      v143 = v248;
    }
    if ( !v264 && (v143 == 0x80000000 || v143 == 0x8000 || (_DWORD)Str1 == 0x80000000 || (_DWORD)Str1 == 0x8000) )
    {
      v145 = *(_QWORD *)(*v259 + 680LL);
      if ( v145 )
      {
        v146 = (struct tagMONITOR *)ValidateHmonitor(v145);
        goto LABEL_302;
      }
      if ( v255 )
      {
        v146 = _MonitorFromWindowInternal(v255, 2u, 0);
LABEL_302:
        v141 = (__int64)v146;
      }
      if ( !v141 )
      {
        v141 = *(_QWORD *)(GetDispInfo(v145) + 96);
        goto LABEL_305;
      }
    }
    else
    {
LABEL_305:
      if ( !v141 )
      {
        v141 = ValidateHmonitor(*(_QWORD *)(*(_QWORD *)v251 + 256LL));
        if ( !v141 )
        {
          if ( v264 )
            v141 = GetInheritedMonitor((struct tagWND *)v45);
          else
            v141 = 0;
          if ( !v141 )
            v141 = MonitorFromRect(*(_QWORD *)v251 + 88LL, 2);
          UpdateWindowMonitorAndDpiInfoHelper((struct tagWND *)v45, (struct tagMONITOR *)v141);
          UpdateTopLevelWindowDPITransform(v45, v141);
        }
      }
    }
    SetTiledRect(v45, &v311, v141);
    v147 = v248;
    if ( (_DWORD)v248 == 0x80000000 || (_DWORD)v248 == 0x8000 )
    {
      v150 = v259;
      if ( (*(_DWORD *)(*v259 + 792LL) & 4) != 0 )
      {
        v134 = 1;
        v147 = *(_DWORD *)(*v259 + 776LL);
        LODWORD(v310) = v147;
        v151 = *(_DWORD *)(*v259 + 780LL);
      }
      else
      {
        v147 = v311;
        LODWORD(v310) = v311;
        v151 = DWORD1(v311);
      }
      DWORD1(v310) = v151;
      v248 = __PAIR64__(v151, v147);
      v148 = 1;
    }
    else
    {
      v148 = 0;
      v149 = *(_WORD *)(v141 + 74);
      v150 = v259;
      if ( v149 )
        *(_WORD *)(v141 + 74) = v149 - 1;
    }
    if ( DWORD2(v310) == 0x80000000 || DWORD2(v310) == 0x8000 )
    {
      if ( (*(_DWORD *)(*v150 + 792LL) & 2) != 0 )
      {
        v134 = 1;
        *((_QWORD *)&v310 + 1) = *(_QWORD *)(*v150 + 784LL);
      }
      else
      {
        DWORD2(v310) = DWORD2(v311) - v147;
        HIDWORD(v310) = HIDWORD(v311) - HIDWORD(v248);
      }
    }
    else if ( v148 )
    {
      MonitorRect = (int *)GetMonitorRect(v271, v141);
      v153 = MonitorRect[1];
      v154 = v310 + DWORD2(v310) - MonitorRect[2];
      v155 = DWORD1(v310) + HIDWORD(v310) - MonitorRect[3];
      if ( v154 > 0 )
      {
        v156 = *MonitorRect;
        LODWORD(v248) = v248 - v154;
        LODWORD(v310) = v248;
        if ( (int)v248 < v156 )
        {
          LODWORD(v248) = v156;
          LODWORD(v310) = v156;
        }
      }
      if ( v155 > 0 )
      {
        HIDWORD(v248) -= v155;
        DWORD1(v310) = HIDWORD(v248);
        if ( SHIDWORD(v248) < v153 )
        {
          HIDWORD(v248) = v153;
          DWORD1(v310) = v153;
        }
      }
    }
  }
  else
  {
    v142 = 0;
  }
  if ( v134 )
    *(_DWORD *)(*v259 + 792LL) &= 0xFFFFFFF9;
  v157 = v45 + 40;
  if ( (((*(_BYTE *)(*(_QWORD *)v251 + 31LL) & 0xC0) + 0x80) & 0xBF) == 0 )
    SetOrClrWF(1, v45, 3844, 1);
  *(_WORD *)(*(_QWORD *)v251 + 30LL) |= v142;
  if ( (unsigned __int8)SmartObjStackRef<tagMENU>::operator==(v269) && !v250 && *(_QWORD *)(*(_QWORD *)v258[0] + 96LL) )
  {
    v266 = 0;
    v159 = v45;
    if ( *(_QWORD *)(v45 + 104) )
      v159 = *(_QWORD *)(v45 + 104);
    zzzLockDisplayAreaAndInvalidateDCCache(v159, 16);
    RtlInitUnicodeStringOrId(&v266, *(_QWORD *)(*(_QWORD *)v258[0] + 96LL));
    Menu = xxxClientLoadMenu(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v258[0] + 8LL) + 64LL), (char **)&v266);
    v270 = 0;
    SmartObjStackRefBase<tagMENU>::operator=(v269, Menu);
    if ( (*(_BYTE *)(*(_QWORD *)v251 + 31LL) & 0xC0) != 0x40 && !(unsigned int)IsWindowBeingDestroyed(v45) )
    {
      if ( (unsigned __int8)SmartObjStackRef<tagMENU>::operator==(v269) )
        v287 = 0;
      else
        v287 = **(struct _HEAD ***)v269[0];
      goto LABEL_347;
    }
    v163 = v270;
    if ( !v270 )
      v163 = *(struct _HEAD **)v269[0];
    DestroyMenu(v163);
    v270 = 0;
    SmartObjStackRefBase<tagMENU>::operator=(v269, 0);
LABEL_475:
    v93 = (int)v261;
    goto LABEL_476;
  }
LABEL_347:
  WindowCloakStateComponentUIAware = 0;
  if ( (*(_BYTE *)(*(_QWORD *)v251 + 31LL) & 0xC0) == 0x40 )
  {
    v162 = v270;
    if ( !v270 )
      v162 = *(struct _HEAD **)v269[0];
    *(_QWORD *)(*(_QWORD *)v251 + 320LL) = v162;
    *(_QWORD *)(*(_QWORD *)(v45 + 40) + 152LL) = 0;
    *(_QWORD *)(v45 + 168) = 0;
  }
  else
  {
    *(_QWORD *)(*(_QWORD *)v251 + 320LL) = 0;
    LockWndMenuWorker(v45, 0, v269);
  }
  if ( (*(_BYTE *)(*(_QWORD *)v251 + 31LL) & 0xC0) != 0x40 )
  {
    if ( (a16 & 4) != 0 )
    {
      LOBYTE(v158) = 1;
      CoreWindowProp::ChangeRole(v45, 1, v158);
    }
    *(_OWORD *)v271 = *(_OWORD *)LockPointer(&v266, v45 + 200, v45);
    HMAssignmentLock(v271, 0);
    if ( (unsigned int)IsTopLevelParent(v255) )
    {
      v165 = v45 + 120;
      *(_QWORD *)(*(_QWORD *)(v45 + 40) + 64LL) = 0;
      *(_QWORD *)&v266.left = v45 + 120;
      *(_QWORD *)&v266.right = 0;
      HMAssignmentLock(&v266, 0);
    }
    else
    {
      NonChildAncestor = GetNonChildAncestor();
      if ( !(unsigned int)ValidateOwnerDepth(v45, NonChildAncestor) )
        goto LABEL_360;
      if ( NonChildAncestor )
      {
        *(_DWORD *)(*(_QWORD *)v251 + 236LL) = *(_DWORD *)(*(_QWORD *)(NonChildAncestor + 40) + 236LL);
        SetOrClrWF(*(_BYTE *)(*(_QWORD *)(NonChildAncestor + 40) + 232LL) & 0x40, v45, 55360, 1);
        WindowCloakStateComponentUIAware = GetWindowCloakStateComponentUIAware(NonChildAncestor);
      }
      v165 = v45 + 120;
      *(_OWORD *)v271 = *(_OWORD *)LockPointer(&v266, v45 + 120, NonChildAncestor);
      HMAssignmentLock(v271, 1);
      if ( *(_QWORD *)(v45 + 120)
        && ((*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v45 + 120) + 40LL) + 24LL) & 8) != 0
         || *(_DWORD *)(*(_QWORD *)v251 + 236LL) != 1) )
      {
        SetOrClrWF(1, v45, 2056, 1);
      }
      v168 = *(_QWORD *)(W32GetUserSessionState(v167, v166) + 19704);
      if ( (_WORD)Atom != *(_WORD *)(v168 + 898) )
      {
        if ( *(_QWORD *)v165 )
        {
          v169 = *(struct tagTHREADINFO **)(*(_QWORD *)v165 + 16LL);
          if ( v169 != v19 )
            zzzAttachThreadInput(v19, v169);
        }
      }
      v157 = v45 + 40;
    }
    IsEnabledDeviceUsageNoInline = Feature_Scoobe_ShellHost__private_IsEnabledDeviceUsageNoInline();
    if ( !*(_QWORD *)v165 )
    {
      if ( IsEnabledDeviceUsageNoInline )
      {
        if ( (unsigned int)CoreWindowProp::IsComponent((const struct tagWND *)v45) )
          goto LABEL_389;
        v171 = *(_DWORD *)(*(_QWORD *)v157 + 236LL);
        if ( (unsigned int)(v171 - 8) <= 3 || v171 == 15 )
          goto LABEL_388;
        v172 = (*(_BYTE *)(*(_QWORD *)v157 + 232LL) & 0x40) == 0;
      }
      else
      {
        if ( (unsigned int)CoreWindowProp::IsComponent((const struct tagWND *)v45) )
          goto LABEL_389;
        v173 = *(_DWORD *)(*(_QWORD *)v157 + 236LL);
        if ( v173 <= 0xF )
        {
          v174 = 44800;
          if ( _bittest(&v174, v173) )
            goto LABEL_388;
        }
        v172 = (*(_BYTE *)(*(_QWORD *)v157 + 232LL) & 0x40) == 0;
      }
      if ( !v172 )
LABEL_388:
        WindowCloakStateComponentUIAware = 2;
    }
LABEL_389:
    if ( v255 && v255 == *(struct tagWND **)(*((_QWORD *)v255 + 3) + 112LL) )
    {
      v175 = v19;
    }
    else
    {
      v70 = GetThreadDesktopWindow(0);
      v255 = (struct tagWND *)v70;
      v175 = v19;
      Win32HM_LockIntoThread<1>(v19, v70, v275);
      v257 = 1;
    }
    if ( !v268 )
      goto LABEL_399;
    if ( !*((_QWORD *)v175 + 198) )
    {
      SetOrClrWF(1, v45, 55424, 1);
      *((_QWORD *)v175 + 170) |= 0x40000uLL;
      *(_DWORD *)(*((_QWORD *)v175 + 58) + 508LL) |= 0x2000000u;
      if ( !*((_QWORD *)v175 + 197) )
      {
        KernelEvent = CreateKernelEvent(1, 0);
        *((_QWORD *)v175 + 197) = KernelEvent;
        if ( !KernelEvent )
        {
          v93 = 7;
          goto LABEL_476;
        }
      }
      *(_QWORD *)&v266.left = (char *)v175 + 1584;
      *(_QWORD *)&v266.right = v45;
      HMAssignmentLock(&v266, 0);
      goto LABEL_399;
    }
LABEL_360:
    UserSetLastError(87);
    goto LABEL_475;
  }
  if ( !v255 )
    goto LABEL_475;
  if ( v268 )
    goto LABEL_360;
LABEL_399:
  v177 = 0;
  if ( (*(_DWORD *)(v45 + 380) & 0x1000000) != 0 )
  {
    v177 = *(_QWORD *)(v45 + 104);
    UnlinkWindow((struct tagWND *)v45);
  }
  if ( !(unsigned int)IsTopLevelParent(v70) )
  {
    *(_DWORD *)(*(_QWORD *)v251 + 236LL) = *(_DWORD *)(*(_QWORD *)(v70 + 40) + 236LL);
    SetOrClrWF(*(_BYTE *)(*(_QWORD *)(v70 + 40) + 232LL) & 0x40, v45, 55360, 1);
  }
  if ( v70 && !(unsigned int)ValidateNewParent(v45, v70, 1) )
  {
    v93 = 9;
    goto LABEL_476;
  }
  v178 = (struct tagWND **)(v45 + 104);
  *(_OWORD *)v271 = *(_OWORD *)LockPointer(&v266, v45 + 104, v255);
  HMAssignmentLock(v271, 0);
  if ( v255 )
    v179 = (unsigned int)-__CFSHR__(*(_DWORD *)(*((_QWORD *)v255 + 5) + 232LL), 10);
  else
    v179 = 0;
  SetWindowSubtreeCoreWindowStatus(v45, v179);
  v180 = *(_QWORD *)(v45 + 40);
  if ( (*(_DWORD *)(v180 + 288) & 0xF) == 2 )
    *(_DWORD *)(v180 + 232) = *(_DWORD *)(v180 + 232) & 0xFFFFFBFF
                            | (ShouldUseLogPixelsForWindowMetrics((struct tagWND *)v45) << 10);
  if ( (WindowCloakStateComponentUIAware & 2) == 0 )
    *(_DWORD *)(v45 + 384) |= 4u;
  if ( WindowCloakStateComponentUIAware )
  {
    v181 = zzzSetWindowCompositionCloak(v45, WindowCloakStateComponentUIAware);
    if ( v181 < 0 )
    {
      v182 = RtlNtStatusToDosError(v181);
      UserSetLastError(v182);
      v93 = 8;
      goto LABEL_476;
    }
  }
  AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)v271);
  if ( v177 )
    zzzLockDisplayAreaAndInvalidateDCCache(v177, 16);
  if ( v255 )
    zzzLockDisplayAreaAndInvalidateDCCache(v255, 16);
  AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v271);
  v184 = *(_QWORD *)(v45 + 40);
  if ( (*(_BYTE *)(v184 + 31) & 0xC0) == 0x40 && !(unsigned int)IsTopLevelWindow(v45) )
  {
    v185 = (struct tagTHREADINFO **)*v178;
    if ( *v178 )
    {
      if ( v19 != v185[2] )
      {
        if ( v255 != (struct tagWND *)v185 )
        {
          v268 = 0x20000;
          MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 2199);
        }
        zzzAttachThreadInput(v19, *((struct tagTHREADINFO **)*v178 + 2));
        v186 = GetMessageWindow(v45);
        if ( v187 != (struct tagWND *)v186 )
        {
          v184 = *(unsigned int *)(*(_QWORD *)v265 + 288LL);
          if ( (((unsigned __int8)v184 ^ *(_BYTE *)(*((_QWORD *)v187 + 5) + 288LL)) & 0xF) != 0
            && !IsChildWindowDpiIsolationEnabled((struct tagWND *)v45, v187) )
          {
            xxxForceUpdateProcessDpiAwarenessContext((struct tagWND *)v45, *(_DWORD *)(*((_QWORD *)*v178 + 5) + 288LL));
          }
        }
      }
    }
  }
  v188 = W32GetUserSessionState(v184, v183);
  if ( v277 != *(unsigned __int16 *)(v188 + 41168) && v277 != 32769 && !*(_DWORD *)v282[0] )
  {
    _InterlockedExchange(
      (volatile __int32 *)(*((_QWORD *)v19 + 60) + 20LL),
      (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24);
    xxxUpdateInputHangInfo(0, 1);
  }
  xxxAdjustSize((struct tagWND *)v45);
  ConstrainWindowSIZERECT(&v310);
  if ( *v281 && (*(_BYTE *)(*(_QWORD *)v265 + 31LL) & 0x40) == 0 && *(char *)(*(_QWORD *)v265 + 24LL) >= 0 )
    CheckFullScreen((struct tagWND *)v45);
  v189 = DWORD2(v310);
  if ( SDWORD2(v310) < 0 )
    v189 = 0;
  DWORD2(v310) = v189;
  v190 = HIDWORD(v310);
  if ( v310 < 0 )
    v190 = 0;
  HIDWORD(v310) = v190;
  RECTFromSIZERECT(*(_QWORD *)v265 + 88LL, &v310);
  if ( v250 )
  {
    v191 = ValidateHmonitorNoRip(*(_QWORD *)(*((_QWORD *)v255 + 5) + 256LL));
LABEL_447:
    v192 = (struct tagMONITOR *)v191;
  }
  else
  {
    if ( v264 )
    {
      v191 = GetInheritedMonitor((struct tagWND *)v45);
      goto LABEL_447;
    }
    v192 = 0;
  }
  if ( v192 || (v192 = (struct tagMONITOR *)MonitorFromRect(*(_QWORD *)v265 + 88LL, 2), v193 = 0, v192) )
    v193 = *(_QWORD *)v192;
  if ( v193 != *(_QWORD *)(*(_QWORD *)v265 + 256LL) )
  {
    UpdateWindowMonitorAndDpiInfoHelper((struct tagWND *)v45, v192);
    if ( !v250 )
      UpdateTopLevelWindowDPITransform(v45, v192);
  }
  v194 = v265;
  if ( (*(_BYTE *)(*(_QWORD *)v265 + 27LL) & 0x20) != 0 && GetRedirectionBitmap(v45) )
  {
    GreLockVisRgn();
    if ( (int)RecreateRedirectionBitmap((struct tagWND *)v45, 0, 0) < 0 )
    {
      GreUnlockVisRgn();
      v93 = 3;
      goto LABEL_476;
    }
    GreUnlockVisRgn();
  }
  if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)v258[0] + 8LL) + 8LL) & 0x20) != 0
    || (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)v258[0] + 8LL) + 8LL) & 0x40) != 0 && !*(_QWORD *)(*(_QWORD *)v258[0] + 40LL) )
  {
    StyleWindow = GetStyleWindow(v45, 2848);
    GreLockVisRgn();
    if ( !CreateCacheDC(v45, StyleWindow != 0 ? 49152 : 0x8000, 0) )
    {
      GreUnlockVisRgn();
      v93 = 10;
      goto LABEL_476;
    }
    GreUnlockVisRgn();
    v194 = v265;
  }
  v196 = v247;
  if ( (v247 & 0x80000) != 0 && (*(_BYTE *)(*(_QWORD *)v194 + 26LL) & 8) == 0 )
  {
    if ( (int)xxxSetLayeredWindow((struct tagWND *)v45) < 0 )
    {
      v93 = 11;
      goto LABEL_476;
    }
    v196 = v247;
  }
  if ( (v196 & 0x2000000) != 0 && !GetStyleWindow(*v178, 2818) )
  {
    SetOrClrWF(1, v45, 2818, 1);
    if ( (int)SetRedirectedWindow((struct tagWND *)v45) < 0 )
    {
      SetOrClrWF(0, v45, 2818, 1);
      v93 = 12;
      goto LABEL_476;
    }
  }
  v291 = HIDWORD(v248);
  v292 = v248;
  v290 = (int)Str1;
  v289 = v254;
  if ( !xxxSendTransformableMessageTimeout((struct tagWND *)v45, 0x81u, 0, 0, 0, 1, 1) )
    goto LABEL_475;
  v203 = *(_QWORD *)(*v303 + 8LL);
  if ( (*(_BYTE *)(v203 + 9) & 2) != 0 )
  {
    SystemMenu = xxxGetSystemMenu((struct tagWND *)v45);
    v270 = 0;
    SmartObjStackRefBase<tagMENU>::operator=(v269, SystemMenu);
    if ( !(unsigned __int8)SmartObjStackRef<tagMENU>::operator==(v269) )
    {
      Win32HMThreadLock<tagMENU>::Win32HMThreadLock<tagMENU>(v271, v269);
      xxxRemoveDeleteMenuHelper((__int64)v269, 5u, 1024, 1u);
      xxxRemoveDeleteMenuHelper((__int64)v269, 5u, 1024, 1u);
      Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)v271);
    }
  }
  if ( (*(_BYTE *)(*(_QWORD *)v194 + 18LL) & 2) != 0 && (!v299 || v297 || *(_QWORD *)(v45 + 184)) )
  {
    *(_OWORD *)v271 = 0;
    v294 = *(_QWORD *)(v45 + 184);
    StrName = tagWND::ProtectedLargeUnicodeStringWNDstrName::getStrName(
                (tagWND::ProtectedLargeUnicodeStringWNDstrName *)(v45 + 184),
                (struct _LARGE_UNICODE_STRING *)v271);
    v297 = *(_DWORD *)StrName;
    v203 = *((unsigned int *)StrName + 1);
    v298 = *((_DWORD *)StrName + 1);
    v299 = *((_QWORD *)StrName + 1);
  }
  if ( (**(_DWORD **)(W32GetUserSessionState(v203, v197) + 19704) & 4) != 0 )
  {
    v206 = (struct tagWND **)((char *)v19 + 816);
    if ( !*((_QWORD *)v19 + 102) && (*(_DWORD *)(v45 + 380) & 0x10000000) != 0 )
    {
      DefaultImeWindow = xxxCreateDefaultImeWindow((struct tagWND *)v45, Atom, v274);
      v282[0] = (ULONG_PTR)v19 + 816;
      v282[1] = (ULONG_PTR)DefaultImeWindow;
      HMAssignmentLock(v282, 0);
      if ( *v206 )
      {
        Win32HMThreadLockAlways<tagHOOK>::Win32HMThreadLockAlways<tagHOOK>(v271, v19, *v206);
        xxxSendTransformableMessageTimeout(*v206, 0x287u, 0, 0, 0, 1, 1);
        Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)v271);
      }
      v208 = (**((_DWORD **)v19 + 64) >> 6) & 1;
      v305 = v208;
      if ( *v206 && v208 )
      {
        Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(v282, *v206);
        xxxSendTransformableMessageTimeout(*v206, 0x287u, 0, 0, 0, 1, 1);
        **((_QWORD **)v19 + 64) &= ~0x40uLL;
        Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)v282);
      }
    }
  }
  v209 = v255;
  if ( v255 && ((*(_DWORD *)(v45 + 380) & 0x1000000) == 0 || *v178 == v255) )
  {
    CompositeAppFrameWindowOrSelf = PWInsertAfter(v273);
    if ( !(unsigned int)IsPseudoPwnd(CompositeAppFrameWindowOrSelf)
      && *(struct tagWND **)(CompositeAppFrameWindowOrSelf + 104) != *v178 )
    {
      CompositeAppFrameWindowOrSelf = v250 != 0;
    }
    v211 = *(_QWORD *)(v45 + 120);
    if ( v211 )
    {
      *(_DWORD *)(*(_QWORD *)v265 + 236LL) = *(_DWORD *)(*(_QWORD *)(v211 + 40) + 236LL);
      SetOrClrWF(*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v45 + 120) + 40LL) + 232LL) & 0x40, v45, 55360, 1);
    }
    if ( !(unsigned int)ValidateNewParent(v45, v255, 1) )
    {
      v212 = 9;
      goto LABEL_536;
    }
    UnlinkWindow((struct tagWND *)v45);
    v213 = *(_QWORD *)v265;
    v214 = v255;
    if ( (*(_BYTE *)(*(_QWORD *)v265 + 31LL) & 0xC0) != 0x40
      && v255 != *(struct tagWND **)(*((_QWORD *)v255 + 3) + 112LL) )
    {
      if ( (*(_BYTE *)(v213 + 24) & 8) != 0 )
      {
        if ( *(_QWORD *)(W32GetUserSessionState(v213, v255) + 19160) )
        {
          TopMostInsertAfter = GetTopMostInsertAfter(v45);
          if ( TopMostInsertAfter )
            CompositeAppFrameWindowOrSelf = TopMostInsertAfter;
        }
      }
      else if ( !CompositeAppFrameWindowOrSelf
             || !(unsigned int)IsPseudoPwnd(CompositeAppFrameWindowOrSelf)
             && (*(_BYTE *)(*(_QWORD *)(CompositeAppFrameWindowOrSelf + 40) + 24LL) & 8) != 0 )
      {
        v215 = (const struct tagWND *)CalcForegroundInsertAfter(v45, v214);
        CompositeAppFrameWindowOrSelf = (unsigned __int64)v215;
        if ( !*(_QWORD *)(v45 + 120) )
          CompositeAppFrameWindowOrSelf = (unsigned __int64)CoreWindowProp::GetCompositeAppFrameWindowOrSelf(v215);
      }
    }
    if ( CompositeAppFrameWindowOrSelf >= 2 && (unsigned int)IsPseudoPwnd(CompositeAppFrameWindowOrSelf) )
    {
      v212 = 13;
      goto LABEL_536;
    }
    LinkWindow((struct tagWND *)v45);
    zzzLockDisplayAreaAndInvalidateDCCache(v255, 16);
    v209 = v255;
  }
  v217 = v265;
  v218 = *(_QWORD *)v265;
  if ( (*(_BYTE *)(*(_QWORD *)v265 + 31LL) & 0xC0) == 0x40 && (*(_BYTE *)(*((_QWORD *)v209 + 5) + 26LL) & 0x40) != 0 )
  {
    v219 = *(_DWORD *)(v218 + 96);
    v220 = *(_DWORD *)(v218 + 88);
    *(_DWORD *)(v218 + 96) = DWORD2(v283) + v283 - v220;
    *(_DWORD *)(*(_QWORD *)v217 + 88LL) = v220 + *(_DWORD *)(*(_QWORD *)v217 + 96LL) - v219;
  }
  v311 = *(_OWORD *)(*(_QWORD *)v217 + 88LL);
  xxxSendTransformableMessageTimeout((struct tagWND *)v45, 0x83u, 0, 0, 0, 1, 0);
  *(_OWORD *)(*(_QWORD *)v217 + 104LL) = v311;
  if ( xxxSendTransformableMessageTimeout((struct tagWND *)v45, 1u, 0, 0, 0, 1, 1) == -1 )
  {
    v212 = (int)v261;
LABEL_536:
    if ( v257 )
      Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)v275);
    if ( Win32HMThreadLockBase<tagMENU,0,1>::ManualUnlock<void>((ULONG_PTR)BugCheckParameter3) )
      xxxDestroyWindow((struct tagWND *)v45);
    ClassUnlock(*(struct tagCLS **)v258[0]);
    if ( v212 )
    {
      v201 = ((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
           * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8);
      v202 = v212;
LABEL_542:
      TraceLoggingCreateWindowFailed(v202, *((unsigned __int64 *)&v201 + 1));
    }
LABEL_543:
    Win32HMOptionalThreadLockAlways<tagMENU>::~Win32HMOptionalThreadLockAlways<tagMENU>((ULONG_PTR)BugCheckParameter3);
    goto LABEL_6;
  }
  SetOrClrWF(1, v45, 1920, 1);
  xxxConsiderPreferredDpiChange((struct tagWND *)v45);
  if ( (unsigned int)IsWindowDesktopComposed(v45, v221, v222, v223) )
  {
    v227 = (void *)ReferenceDwmApiPort(v225, v224, v226);
    DwmAsyncChildStyleChange(v227);
    DwmChildRectChange((struct tagWND *)v45);
    DirtyVisRgnTrackers((struct tagWND *)v45);
    v231 = (void *)ReferenceDwmApiPort(v229, v228, v230);
    DwmAsyncOwnerChange(v231);
    v217 = v265;
  }
  xxxWindowEvent(0x8000u, (struct tagWND *)v45, 0, 0, 0);
  if ( (*(_BYTE *)(*(_QWORD *)v217 + 16LL) & 0x10) == 0 )
  {
    xxxSendSizeMessage((struct tagWND *)v45);
    if ( v255 )
    {
      DesktopWindow = GetDesktopWindow(v45, v255, v234);
      if ( DesktopWindow != v236 )
      {
        LODWORD(v311) = v311 - v283;
        DWORD1(v311) -= DWORD1(v283);
      }
    }
    xxxSendTransformableMessageTimeout((struct tagWND *)v45, 3u, 0, 0, 0, 1, 0);
  }
  v237 = *(_DWORD *)(W32GetUserSessionState(v233, v232) + 66784) & 0x10000 | 1;
  v238 = v265;
  v239 = *(_BYTE *)(*(_QWORD *)v265 + 31LL);
  if ( (v239 & 0x20) != 0 )
  {
    SetMinimize(v45, 0);
    v240 = 7;
    goto LABEL_555;
  }
  if ( (v239 & 1) != 0 )
  {
    SetOrClrWF(0, v45, 3841, 1);
    v237 |= 0x10u;
    v240 = 3;
LABEL_555:
    xxxMinMaximize(v45, v240, v237);
  }
  CalcWindowFullScreen((struct tagWND *)v45);
  if ( (*(_BYTE *)(*(_QWORD *)v238 + 31LL) & 0xC0) == 0x40 && (*(_BYTE *)(*(_QWORD *)v238 + 24LL) & 4) == 0 && *v178 )
  {
    Win32HMThreadLockAlways<tagWND>::Win32HMThreadLockAlways<tagWND>(v271, v19, v45 + 104);
    xxxSendTransformableMessageTimeout(*v178, 0x210u, 0, 0, 0, 1, 0);
    Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)v271);
  }
  xxxInheritWindowMonitor((struct tagWND *)v45);
  CDwmWindowNotifyBatch::CDwmWindowNotifyBatch((CDwmWindowNotifyBatch *)v309, (struct tagWND *)v45);
  if ( (a5 & 0x10000000) != 0 )
  {
    v243 = W32GetUserSessionState(v242, v241);
    xxxShowWindowEx(
      v45,
      v253 | *(_DWORD *)(v243 + 66784) & 0x10000u,
      v253 & 0x10000 | *(_DWORD *)(v243 + 66784) & 0x10000u);
  }
  CDwmWindowNotifyBatch::~CDwmWindowNotifyBatch((CDwmWindowNotifyBatch *)v309);
  if ( (*(_BYTE *)(*(_QWORD *)v238 + 31LL) & 0xC0) == 0 || (*(_BYTE *)(*(_QWORD *)v238 + 26LL) & 4) != 0 )
  {
    v244 = v259;
    if ( *(_DWORD *)(*v259 + 676LL) )
    {
      xxxSendTransformableMessageTimeout((struct tagWND *)v45, 0x32u, 0, 0, 0, 1, 1);
      *(_DWORD *)(*v244 + 676LL) = 0;
    }
  }
  if ( v257 )
    Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)v275);
  ClassUnlock(*(struct tagCLS **)v258[0]);
  v245 = Win32HMThreadLockBase<tagMENU,0,1>::ManualUnlock<void>((ULONG_PTR)BugCheckParameter3);
  v246 = v245;
  if ( !v245 || (*(_BYTE *)(_HMPheFromObject(v245) + 25) & 1) != 0 )
    v246 = 0;
  Win32HMOptionalThreadLockAlways<tagMENU>::~Win32HMOptionalThreadLockAlways<tagMENU>((ULONG_PTR)BugCheckParameter3);
  SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(v269);
  Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)v275);
  SmartObjStackRef<tagPOPUPMENU>::~SmartObjStackRef<tagPOPUPMENU>(v258);
  return v246;
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
