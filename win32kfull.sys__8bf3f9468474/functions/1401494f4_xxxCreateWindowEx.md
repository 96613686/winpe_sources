# xxxCreateWindowEx

- ea: `0x1401494f4`
- end: `0x14014c90b`
- name: `xxxCreateWindowEx`
- size: `13335`
- prototype: ``
- caller_count: `8`
- callee_count: `141`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400045b0`
- `0x1400a64a8`
- `0x140130ab0`
- `0x140131090`
- `0x1401490ec`
- `0x140174168`
- `0x14024c1a8`
- `0x1402b1f80`

## callees

- `0x140004c3c`
- `0x140004cbc`
- `0x14000b34c`
- `0x14000b370`
- `0x14000b5bc`
- `0x1400150d0`
- `0x140015750`
- `0x14001584c`
- `0x14001a190`
- `0x14001aac0`
- `0x14001bd40`
- `0x14001cb40`
- `0x14001dbdc`
- `0x14001eeb4`
- `0x14001f108`
- `0x14001f284`
- `0x14001f2ac`
- `0x14001f33c`
- `0x1400209c0`
- `0x140020ba0`
- `0x140020cf0`
- `0x140023be8`
- `0x140024100`
- `0x140027d44`
- `0x140028660`
- `0x1400286dc`
- `0x1400292ec`
- `0x14002b638`
- `0x14002b844`
- `0x14002b948`
- `0x14002c2d0`
- `0x14002d3e4`
- `0x14002da38`
- `0x14002de48`
- `0x1400381a8`
- `0x140059150`
- `0x1400591b0`
- `0x140059dd0`
- `0x14005d094`
- `0x14005dba0`
- `0x140085c00`
- `0x140085e30`
- `0x1400911b0`
- `0x1400a864c`
- `0x1400aa20c`
- `0x1400ab7e4`
- `0x1400af078`
- `0x1400b0ba0`
- `0x1400b1334`
- `0x1400b162c`

## import_xrefs

- `ntoskrnl!PsGetWin32KFilterSet` at `0x140149bb5`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x14014a74d`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x14014a78a`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x14014a875`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x14014a97e`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x140149bb5`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x14014a74d`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x14014a78a`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x14014a875`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x14014a97e`
- `ntoskrnl!RtlNtStatusToDosError` at `0x14014b925`
- `ntoskrnl!RtlNtStatusToDosError` at `0x14014b925`
- `ntoskrnl!PsGetThreadId` at `0x140149cdb`
- `ntoskrnl!PsGetThreadId` at `0x140149cdb`
- `ntoskrnl!PsGetProcessPeb` at `0x14014ab40`
- `ntoskrnl!PsGetProcessPeb` at `0x14014ab40`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14014992f`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14014a085`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14014992f`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14014a085`
- `win32kbase!UserFindAtom` at `0x140149a46`
- `win32kbase!UserFindAtom` at `0x140149a46`
- `win32kbase!ShouldSetNoOwner` at `0x1401497f4`
- `win32kbase!ShouldSetNoOwner` at `0x1401497f4`
- `win32kbase!?LockInitialize@tagObjLock@@QEBAXXZ` at `0x140149cc4`
- `win32kbase!?LockInitialize@tagObjLock@@QEBAXXZ` at `0x140149db1`
- `win32kbase!?LockInitialize@tagObjLock@@QEBAXXZ` at `0x140149cc4`
- `win32kbase!?LockInitialize@tagObjLock@@QEBAXXZ` at `0x140149db1`
- `win32kbase!?LockUnInitializeThreadCreator@tagObjLock@@QEBAXXZ` at `0x140149d8e`
- `win32kbase!?LockUnInitializeThreadCreator@tagObjLock@@QEBAXXZ` at `0x140149fce`
- `win32kbase!?LockUnInitializeThreadCreator@tagObjLock@@QEBAXXZ` at `0x140149ff0`
- `win32kbase!?LockUnInitializeThreadCreator@tagObjLock@@QEBAXXZ` at `0x140149d8e`
- `win32kbase!?LockUnInitializeThreadCreator@tagObjLock@@QEBAXXZ` at `0x140149fce`
- `win32kbase!?LockUnInitializeThreadCreator@tagObjLock@@QEBAXXZ` at `0x140149ff0`
- `win32kbase!W32GetCurrentThreadDpiHostingBehavior` at `0x140149e0d`
- `win32kbase!W32GetCurrentThreadDpiHostingBehavior` at `0x140149e0d`
- `win32kbase!CreateCacheDC` at `0x14014bd00`
- `win32kbase!CreateCacheDC` at `0x14014bd00`
- `win32kbase!IsImmersiveBroker` at `0x140149743`
- `win32kbase!IsImmersiveBroker` at `0x140149743`
- `win32kbase!CreateKernelEvent` at `0x14014b7aa`
- `win32kbase!CreateKernelEvent` at `0x14014b7aa`
- `win32kbase!IsDesktopApp` at `0x14014970e`
- `win32kbase!IsDesktopApp` at `0x14014970e`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x140149ed2`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x14014a05b`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x140149ed2`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x14014a05b`
- `win32kbase!GetDispInfo` at `0x14014b09b`
- `win32kbase!GetDispInfo` at `0x14014b09b`
- `win32kbase!_HMPheFromObject` at `0x14014a842`
- `win32kbase!_HMPheFromObject` at `0x14014ad31`
- `win32kbase!_HMPheFromObject` at `0x14014c86a`
- `win32kbase!_HMPheFromObject` at `0x14014a842`
- `win32kbase!_HMPheFromObject` at `0x14014ad31`
- `win32kbase!_HMPheFromObject` at `0x14014c86a`
- `win32kbase!GreUnlockVisRgn` at `0x14014bc6b`
- `win32kbase!GreUnlockVisRgn` at `0x14014bc82`
- `win32kbase!GreUnlockVisRgn` at `0x14014bd11`
- `win32kbase!GreUnlockVisRgn` at `0x14014bd28`
- `win32kbase!GreUnlockVisRgn` at `0x14014bc6b`
- `win32kbase!GreUnlockVisRgn` at `0x14014bc82`
- `win32kbase!GreUnlockVisRgn` at `0x14014bd11`
- `win32kbase!GreUnlockVisRgn` at `0x14014bd28`
- `win32kbase!GreLockVisRgn` at `0x14014bc42`
- `win32kbase!GreLockVisRgn` at `0x14014bcdd`
- `win32kbase!GreLockVisRgn` at `0x14014bc42`
- `win32kbase!GreLockVisRgn` at `0x14014bcdd`
- `win32kbase!IsWindowDesktopComposed` at `0x14014a5ae`
- `win32kbase!IsWindowDesktopComposed` at `0x14014c559`
- `win32kbase!IsWindowDesktopComposed` at `0x14014a5ae`
- `win32kbase!IsWindowDesktopComposed` at `0x14014c559`
- `win32kbase!ValidateHmonitorNoRip` at `0x14014a4ae`
- `win32kbase!ValidateHmonitorNoRip` at `0x14014bbb8`
- `win32kbase!ValidateHmonitorNoRip` at `0x14014a4ae`
- `win32kbase!ValidateHmonitorNoRip` at `0x14014bbb8`
- `win32kbase!HMAllocObject` at `0x140149c61`
- `win32kbase!HMAllocObject` at `0x140149c61`
- `win32kbase!HMFreeObject` at `0x140149d9d`
- `win32kbase!HMFreeObject` at `0x140149fff`
- `win32kbase!HMFreeObject` at `0x140149d9d`
- `win32kbase!HMFreeObject` at `0x140149fff`
- `win32kbase!ValidateHmonitor` at `0x14014b06d`
- `win32kbase!ValidateHmonitor` at `0x14014b0bf`
- `win32kbase!ValidateHmonitor` at `0x14014b06d`
- `win32kbase!ValidateHmonitor` at `0x14014b0bf`
- `win32kbase!HMAssignmentLock` at `0x14014a59f`
- `win32kbase!HMAssignmentLock` at `0x14014b530`
- `win32kbase!HMAssignmentLock` at `0x14014b5dc`
- `win32kbase!HMAssignmentLock` at `0x14014b693`
- `win32kbase!HMAssignmentLock` at `0x14014b7e5`
- `win32kbase!HMAssignmentLock` at `0x14014b8a5`
- `win32kbase!HMAssignmentLock` at `0x14014c0e0`
- `win32kbase!HMAssignmentLock` at `0x14014a59f`
- `win32kbase!HMAssignmentLock` at `0x14014b530`
- `win32kbase!HMAssignmentLock` at `0x14014b5dc`
- `win32kbase!HMAssignmentLock` at `0x14014b693`
- `win32kbase!HMAssignmentLock` at `0x14014b7e5`
- `win32kbase!HMAssignmentLock` at `0x14014b8a5`
- `win32kbase!HMAssignmentLock` at `0x14014c0e0`
- `win32kbase!Win32AllocPoolZInit` at `0x140149d73`
- `win32kbase!Win32AllocPoolZInit` at `0x14014a6f5`
- `win32kbase!Win32AllocPoolZInit` at `0x140149d73`
- `win32kbase!Win32AllocPoolZInit` at `0x14014a6f5`
- `win32kbase!Win32FreePool` at `0x140149fe1`
- `win32kbase!Win32FreePool` at `0x140149fe1`
- `win32kbase!ReferenceDwmApiPort` at `0x14014c572`
- `win32kbase!ReferenceDwmApiPort` at `0x14014c5b6`
- `win32kbase!ReferenceDwmApiPort` at `0x14014c572`
- `win32kbase!ReferenceDwmApiPort` at `0x14014c5b6`
- `WIN32K!W32GetUserSessionState` at `0x140149a13`
- `WIN32K!W32GetUserSessionState` at `0x14014a142`
- `WIN32K!W32GetUserSessionState` at `0x14014a8b7`
- `WIN32K!W32GetUserSessionState` at `0x14014a9d7`
- `WIN32K!W32GetUserSessionState` at `0x14014a9fe`
- `WIN32K!W32GetUserSessionState` at `0x14014aa1e`
- `WIN32K!W32GetUserSessionState` at `0x14014aa3e`
- `WIN32K!W32GetUserSessionState` at `0x14014aa5e`
- `WIN32K!W32GetUserSessionState` at `0x14014aa7a`
- `WIN32K!W32GetUserSessionState` at `0x14014aa96`
- `WIN32K!W32GetUserSessionState` at `0x14014aab2`
- `WIN32K!W32GetUserSessionState` at `0x14014aace`
- `WIN32K!W32GetUserSessionState` at `0x14014b61f`
- `WIN32K!W32GetUserSessionState` at `0x14014ba5e`
- `WIN32K!W32GetUserSessionState` at `0x14014c068`
- `WIN32K!W32GetUserSessionState` at `0x14014c365`
- `WIN32K!W32GetUserSessionState` at `0x14014c684`
- `WIN32K!W32GetUserSessionState` at `0x14014c79a`
- `WIN32K!W32GetUserSessionState` at `0x140149a13`
- `WIN32K!W32GetUserSessionState` at `0x14014a142`
- `WIN32K!W32GetUserSessionState` at `0x14014a8b7`
- `WIN32K!W32GetUserSessionState` at `0x14014a9d7`
- `WIN32K!W32GetUserSessionState` at `0x14014a9fe`
- `WIN32K!W32GetUserSessionState` at `0x14014aa1e`
- `WIN32K!W32GetUserSessionState` at `0x14014aa3e`
- `WIN32K!W32GetUserSessionState` at `0x14014aa5e`
- `WIN32K!W32GetUserSessionState` at `0x14014aa7a`
- `WIN32K!W32GetUserSessionState` at `0x14014aa96`
- `WIN32K!W32GetUserSessionState` at `0x14014aab2`
- `WIN32K!W32GetUserSessionState` at `0x14014aace`
- `WIN32K!W32GetUserSessionState` at `0x14014b61f`
- `WIN32K!W32GetUserSessionState` at `0x14014ba5e`
- `WIN32K!W32GetUserSessionState` at `0x14014c068`
- `WIN32K!W32GetUserSessionState` at `0x14014c365`
- `WIN32K!W32GetUserSessionState` at `0x14014c684`
- `WIN32K!W32GetUserSessionState` at `0x14014c79a`

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
  __int64 v31; // rcx
  __int64 v32; // r9
  int v33; // edx
  __int64 CurrentProcessWin32Process; // rax
  __int64 v35; // rdx
  int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 UserSessionState; // rax
  __int64 v42; // r10
  unsigned __int16 v43; // r9
  _QWORD *ClassPtr; // rax
  __int64 v45; // r8
  int v46; // r9d
  unsigned int v47; // r9d
  __int64 v48; // rax
  __int64 v49; // r14
  tagObjLock *v50; // r13
  __int64 v51; // rbx
  tagObjLock *v52; // rax
  unsigned int CurrentThreadDpiHostingBehavior; // eax
  struct tagWND *v54; // rdx
  __int64 v55; // r8
  __int64 v56; // r9
  __int64 v57; // rcx
  struct tagWND *v58; // rbx
  struct tagTHREADINFO *v59; // rax
  __int64 v60; // rax
  __int64 v61; // r8
  __int64 v62; // rcx
  int v63; // ebx
  __int64 v64; // rdx
  int v65; // ecx
  wchar_t *v66; // rcx
  unsigned int CurrentThreadDpiAwarenessContext; // eax
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 v70; // r9
  __int64 v71; // rax
  __int64 v72; // rdx
  __int64 v73; // rdx
  __int64 v74; // r8
  __int64 v75; // r9
  __int16 v76; // bx
  __int64 v77; // rdx
  __int64 *v78; // rax
  __int64 v79; // rcx
  __int64 v80; // rdi
  __int64 v81; // r8
  __int64 v82; // r13
  int v83; // eax
  LONG v84; // r9d
  int v85; // r10d
  struct _HEAD *v86; // rax
  LONG v87; // edx
  LONG v88; // eax
  LONG v89; // ecx
  int v90; // edx
  unsigned int v91; // eax
  struct tagMONITOR *InheritedMonitor; // rbx
  _DWORD *v93; // rax
  __int64 MessageWindow; // rax
  const struct tagWND *ThreadDesktopWindow; // rdx
  __int64 v96; // r9
  __int64 v97; // rdx
  __int64 v98; // rcx
  __int64 v99; // r8
  char v100; // r12
  __int64 v101; // rax
  int v102; // r13d
  __int64 v103; // rax
  char v104; // r12
  Scrollbar::NonClient *v105; // rcx
  Scrollbar::NonClient *v106; // rcx
  bool v107; // al
  __int64 v108; // rdx
  int v109; // r8d
  unsigned int v110; // ecx
  unsigned int ClientExtraBytesTotalSize; // eax
  __int64 v112; // rdi
  _QWORD *v113; // rdx
  __int64 v114; // rcx
  int v115; // ebx
  __int64 v116; // r8
  __int64 v117; // r9
  __int64 v118; // rcx
  __int64 v119; // rdx
  __int64 v120; // rdx
  __int64 v121; // r8
  __int64 v122; // r9
  __int64 v123; // rdx
  __int64 v124; // rcx
  __int64 v125; // r8
  __int64 v126; // r9
  __int16 v127; // di
  __int64 v128; // rdx
  __int64 v129; // rcx
  __int64 v130; // r8
  __int64 v131; // r9
  __int64 v132; // rdx
  __int64 v133; // rcx
  __int64 v134; // r8
  __int64 v135; // r9
  __int64 v136; // rdx
  __int64 v137; // rcx
  __int64 v138; // r8
  __int64 v139; // r9
  __int64 v140; // rdx
  __int64 v141; // rcx
  __int64 v142; // r8
  __int64 v143; // r9
  __int64 v144; // rdx
  __int64 v145; // rcx
  __int64 v146; // r8
  __int64 v147; // r9
  __int64 v148; // rdx
  __int64 v149; // rcx
  __int64 v150; // r8
  __int64 v151; // r9
  __int64 v152; // rdx
  __int64 v153; // rcx
  __int64 v154; // r8
  __int64 v155; // r9
  __int16 v156; // bx
  unsigned __int16 v157; // bx
  char v158; // di
  int v159; // eax
  __int64 v160; // rcx
  int v161; // edx
  int v162; // r12d
  int v163; // edi
  unsigned int v164; // ecx
  int v165; // r8d
  int v166; // r9d
  __int64 v167; // rbx
  __int16 v168; // di
  int v169; // eax
  int v170; // edx
  __int64 v171; // rcx
  struct tagMONITOR *v172; // rax
  unsigned int v173; // edx
  int v174; // ecx
  __int16 v175; // ax
  _QWORD *v176; // r8
  unsigned int v177; // eax
  int *MonitorRect; // rax
  int v179; // r8d
  int v180; // r9d
  int v181; // r10d
  int v182; // eax
  __int64 v183; // rbx
  __int64 v184; // r8
  __int64 v185; // rcx
  __int64 v186; // rax
  unsigned int WindowCloakStateComponentUIAware; // r12d
  struct _HEAD *v188; // rcx
  struct _HEAD *v189; // rcx
  __int64 v190; // rcx
  __int64 NonChildAncestor; // rbx
  __int64 v192; // rdi
  __int64 v193; // rdx
  __int64 v194; // rcx
  __int64 v195; // r8
  __int64 v196; // r9
  __int64 v197; // rcx
  struct tagTHREADINFO *v198; // rdx
  int IsEnabledDeviceUsageNoInline; // eax
  int v200; // ecx
  bool v201; // zf
  unsigned int v202; // eax
  int v203; // edx
  struct tagTHREADINFO *v204; // rdi
  __int64 KernelEvent; // rax
  __int64 v206; // rdi
  struct tagWND **v207; // r13
  __int64 v208; // rdx
  __int64 v209; // rbx
  NTSTATUS v210; // eax
  ULONG v211; // eax
  __int64 v212; // rdx
  __int64 v213; // r8
  struct tagWND *v214; // r9
  __int64 v215; // rcx
  struct tagTHREADINFO **v216; // rax
  __int64 v217; // rax
  __int64 v218; // rax
  int v219; // eax
  int v220; // eax
  __int64 v221; // rax
  struct tagMONITOR *v222; // rbx
  __int64 v223; // rcx
  __int64 *v224; // rbx
  __int64 StyleWindow; // rbx
  unsigned int v226; // edx
  __int64 v227; // rdx
  __int64 v228; // r8
  __int64 v229; // r9
  int v230; // ebx
  __int64 v231; // r9
  struct tagTHREADINFO *v232; // rdx
  unsigned __int128 v233; // rax
  unsigned int v234; // ecx
  __int64 v235; // rcx
  __int64 SystemMenu; // rax
  struct _LARGE_UNICODE_STRING *StrName; // rax
  struct tagWND **v238; // rbx
  struct tagWND *DefaultImeWindow; // rax
  int v240; // ecx
  struct tagWND *v241; // rcx
  unsigned __int64 CompositeAppFrameWindowOrSelf; // rbx
  __int64 v243; // rax
  int v244; // ebx
  __int64 v245; // r8
  __int64 v246; // r9
  __int64 v247; // rcx
  struct tagWND *v248; // rdx
  const struct tagWND *v249; // rax
  __int64 TopMostInsertAfter; // rax
  __int64 *v251; // rbx
  __int64 v252; // r9
  int v253; // edx
  int v254; // r8d
  __int64 v255; // rdx
  __int64 v256; // rcx
  __int64 v257; // r8
  void *v258; // rax
  __int64 v259; // rdx
  __int64 v260; // rcx
  __int64 v261; // r8
  void *v262; // rax
  __int64 v263; // rdx
  __int64 v264; // rcx
  __int64 v265; // r8
  __int64 v266; // r9
  __int64 DesktopWindow; // rax
  __int64 v268; // rdx
  unsigned int v269; // ebx
  __int64 *v270; // rdi
  char v271; // cl
  __int64 v272; // rdx
  __int64 v273; // rdx
  __int64 v274; // rcx
  __int64 v275; // r8
  __int64 v276; // r9
  __int64 v277; // rax
  _QWORD *v278; // rbx
  __int64 v279; // rax
  __int64 v280; // rbx
  unsigned int v281; // [rsp+50h] [rbp-2D8h]
  unsigned __int64 v282; // [rsp+54h] [rbp-2D4h]
  __int16 v283; // [rsp+5Ch] [rbp-2CCh]
  int v284; // [rsp+5Ch] [rbp-2CCh]
  __int64 v285; // [rsp+68h] [rbp-2C0h]
  unsigned __int16 v286; // [rsp+70h] [rbp-2B8h]
  int v287; // [rsp+70h] [rbp-2B8h]
  unsigned int v288; // [rsp+74h] [rbp-2B4h]
  struct tagWND *v289; // [rsp+78h] [rbp-2B0h]
  int v290; // [rsp+8Ch] [rbp-29Ch]
  int v291; // [rsp+8Ch] [rbp-29Ch]
  _QWORD v292[2]; // [rsp+90h] [rbp-298h] BYREF
  _QWORD *v293; // [rsp+A0h] [rbp-288h]
  wchar_t *Str1; // [rsp+A8h] [rbp-280h]
  int *v295; // [rsp+B0h] [rbp-278h]
  int v296; // [rsp+B8h] [rbp-270h]
  int Atom; // [rsp+C0h] [rbp-268h]
  int v298; // [rsp+C4h] [rbp-264h]
  __int64 *v299; // [rsp+C8h] [rbp-260h]
  struct tagRECT v300; // [rsp+D0h] [rbp-258h] BYREF
  int v301; // [rsp+E0h] [rbp-248h]
  int v302; // [rsp+E4h] [rbp-244h]
  _QWORD v303[2]; // [rsp+E8h] [rbp-240h] BYREF
  struct _HEAD *v304; // [rsp+F8h] [rbp-230h]
  ULONG_PTR v305[2]; // [rsp+100h] [rbp-228h] BYREF
  unsigned __int16 v306; // [rsp+110h] [rbp-218h]
  __int64 v307; // [rsp+118h] [rbp-210h]
  void *v308; // [rsp+120h] [rbp-208h]
  ULONG_PTR v309[2]; // [rsp+128h] [rbp-200h] BYREF
  __int64 v310; // [rsp+138h] [rbp-1F0h]
  __int64 v311; // [rsp+140h] [rbp-1E8h]
  __int64 v312; // [rsp+148h] [rbp-1E0h] BYREF
  __int64 v313; // [rsp+150h] [rbp-1D8h]
  struct tagWND *v314; // [rsp+158h] [rbp-1D0h]
  _QWORD *v315; // [rsp+160h] [rbp-1C8h]
  ULONG_PTR v316[2]; // [rsp+170h] [rbp-1B8h] BYREF
  __int128 v317; // [rsp+180h] [rbp-1A8h] BYREF
  int v318; // [rsp+190h] [rbp-198h]
  int v319; // [rsp+1BCh] [rbp-16Ch]
  _QWORD v320[2]; // [rsp+1D0h] [rbp-158h] BYREF
  struct _HEAD *v321; // [rsp+1E0h] [rbp-148h]
  __int64 v322; // [rsp+1E8h] [rbp-140h]
  unsigned int v323; // [rsp+1F0h] [rbp-138h]
  int v324; // [rsp+1F4h] [rbp-134h]
  LONG v325; // [rsp+1F8h] [rbp-130h]
  unsigned int v326; // [rsp+1FCh] [rbp-12Ch]
  unsigned int v327; // [rsp+200h] [rbp-128h]
  __int64 v328; // [rsp+208h] [rbp-120h]
  wchar_t *v329; // [rsp+210h] [rbp-118h]
  unsigned int v330; // [rsp+218h] [rbp-110h]
  int v331; // [rsp+220h] [rbp-108h]
  int v332; // [rsp+224h] [rbp-104h]
  __int64 v333; // [rsp+228h] [rbp-100h]
  __int128 v334; // [rsp+230h] [rbp-F8h] BYREF
  wchar_t *v335; // [rsp+240h] [rbp-E8h]
  struct tagTHREADINFO **v336; // [rsp+248h] [rbp-E0h]
  _QWORD *v337; // [rsp+250h] [rbp-D8h]
  ULONG_PTR BugCheckParameter3[2]; // [rsp+258h] [rbp-D0h] BYREF
  int v339; // [rsp+268h] [rbp-C0h]
  int *v340; // [rsp+270h] [rbp-B8h] BYREF
  __int128 v341; // [rsp+280h] [rbp-A8h] BYREF
  __int64 v342; // [rsp+290h] [rbp-98h]
  _BYTE v343[40]; // [rsp+2A0h] [rbp-88h] BYREF
  __int128 v344; // [rsp+2C8h] [rbp-60h] BYREF
  __int128 v345; // [rsp+2D8h] [rbp-50h] BYREF

  v340 = a4;
  v335 = a2;
  v301 = a1;
  v281 = a1;
  v296 = a1;
  Str1 = a2;
  v311 = a3;
  v295 = a4;
  v18 = (__int64)a10;
  v289 = a10;
  v307 = (__int64)a10;
  v308 = a12;
  *(_QWORD *)&v300.left = a13;
  SmartObjStackRef<tagCLS>::SmartObjStackRef<tagCLS>(v292);
  v345 = 0;
  v344 = 0;
  memset_0(v320, 0, 0x70u);
  v19 = PtiCurrent();
  Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(v309);
  v341 = 0;
  v342 = 0;
  v293 = (_QWORD *)((char *)v19 + 456);
  v20 = *(_DWORD *)(*((_QWORD *)v19 + 57) + 12LL);
  v317 = 0;
  SmartObjStackRef<tagMENU>::SmartObjStackRef<tagMENU>(v303, a11);
  AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)&v312);
  if ( (*(_DWORD *)(*((_QWORD *)v19 + 57) + 12LL) & 0x10000000) == 0 && !(unsigned int)RegisterIconTitleClass() )
    goto LABEL_3;
  if ( a1 < 0 )
  {
    v281 = a1 & 0x7FFFFFFF;
    v296 = a1 & 0x7FFFFFFF;
  }
  v23 = 800;
  if ( a1 >= 0 )
    v23 = 0;
  v286 = v23;
  v24 = *((_QWORD *)v19 + 61);
  v315 = (_QWORD *)v24;
  v316[0] = v24;
  if ( a10 )
  {
    if ( *((_QWORD *)a10 + 3) != v24 )
      goto LABEL_3;
  }
  v25 = 0;
  if ( (a16 & 1) != 0 )
  {
    if ( (unsigned int)IsDesktopApp(*v293) )
    {
LABEL_45:
      v21 = 5;
      goto LABEL_4;
    }
    v25 = 1;
  }
  v302 = a16 & 2;
  if ( (a16 & 2) != 0 && !(unsigned int)IsImmersiveBroker(*v293) )
    goto LABEL_45;
  v26 = a14;
  if ( !a14 )
  {
LABEL_26:
    v27 = v293;
    goto LABEL_27;
  }
  if ( !(unsigned int)IsValidBand(a14) || a14 == 15 )
    goto LABEL_3;
  v27 = v293;
  v28 = *(_QWORD *)(*v293 + 808LL);
  if ( (v28 & 0x30) == 0x10 && (v28 & 0x200) == 0 && a14 == 1 && !v25 )
  {
    if ( !(unsigned int)HasMessageRootWindow(a10) )
      goto LABEL_3;
    goto LABEL_26;
  }
LABEL_27:
  v283 = HIWORD(a5) & 0xC000;
  v319 = (HIWORD(a5) & 0xC000) == 0x4000;
  if ( (HIWORD(a5) & 0xC000) != 0x4000 )
  {
    if ( (unsigned int)ShouldSetNoOwner(*v27, a10) )
      v18 = 0;
    v289 = (struct tagWND *)v18;
    v307 = v18;
  }
  if ( !v18 || (unsigned int)IsDesktopWindow(v18) )
  {
    if ( !a14 )
    {
      if ( (unsigned int)IsImmersiveAppIORestricted(*v293) )
      {
        v25 = 1;
        v26 = 15;
      }
      else if ( (*(_BYTE *)(v30 + 808) & 2) != 0 && (v281 & 8) != 0 )
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
  if ( !(unsigned __int8)IsValidBandForProcess(*v293, v26, v18) )
    goto LABEL_45;
  v33 = v281;
  if ( (v281 & 0x400000) == 0 )
  {
    if ( v18 )
    {
      if ( v283 != 0x4000 || (*(_BYTE *)(*(_QWORD *)(v18 + 40) + 26LL) & 0x50) != 0x40 )
        goto LABEL_58;
      v33 = v281 | 0x400000;
    }
    else
    {
      if ( ((unsigned __int64)Str1 & 0xFFFFFFFFFFFF0000uLL) == 0 )
      {
        v31 = 32770;
        if ( (_WORD)Str1 == 0x8002 )
          goto LABEL_58;
      }
      CurrentProcessWin32Process = PsGetCurrentProcessWin32Process(v31, v281, 0x400000, v32);
      v35 = CurrentProcessWin32Process;
      if ( CurrentProcessWin32Process )
        v35 = -(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0) & CurrentProcessWin32Process;
      v36 = *(_DWORD *)(v35 + 816);
      v33 = v281;
      if ( (v36 & 1) == 0 )
        goto LABEL_58;
      v33 = v281 | 0x400000;
    }
    v296 = v33;
    v281 = v33;
  }
LABEL_58:
  if ( (v33 & 0x2200000) == 0x2200000 )
    goto LABEL_3;
  if ( *((_QWORD *)v19 + 78) && !(unsigned int)CheckGrantedAccess(*((unsigned int *)v19 + 232), 2) )
    goto LABEL_5;
  if ( v283 == 0x4000 )
  {
    if ( !v18 )
    {
      v21 = 1406;
LABEL_4:
      UserSetLastError(v21);
LABEL_5:
      AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)&v312);
LABEL_6:
      SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(v303);
      Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)v309);
      SmartObjStackRef<tagPOPUPMENU>::~SmartObjStackRef<tagPOPUPMENU>(v292);
      return 0;
    }
    if ( !(unsigned int)ValidateParentDepth(0, v18) )
    {
LABEL_3:
      v21 = 87;
      goto LABEL_4;
    }
  }
  v290 = v20 & 0x2000;
  v310 = v18;
  while ( 1 )
  {
    if ( (v311 & 0xFFFFFFFFFFFF0000uLL) != 0 )
    {
      AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)v305);
      UserSessionState = W32GetUserSessionState(v38, v37, v39, v40);
      if ( (int)RtlStringCchCopyW(
                  (unsigned __int16 *)(UserSessionState + 41556),
                  0x100u,
                  *(const unsigned __int16 **)(v311 + 8)) < 0 )
      {
        Atom = 0;
        v290 = 1;
        v318 = 1;
      }
      else
      {
        Atom = (unsigned __int16)UserFindAtom(v42);
      }
      AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v305);
    }
    else
    {
      v43 = v311;
      Atom = v311;
    }
    if ( v43 )
    {
      ClassPtr = (_QWORD *)GetClassPtr(v43, *v293, v308);
      if ( ClassPtr )
        break;
    }
LABEL_107:
    if ( v290
      || (*(_DWORD *)(*((_QWORD *)PtiCurrent() + 57) + 12LL) & 0x2000) != 0
      || (((unsigned __int64)Str1 & 0xFFFFFFFFFFFF0000uLL) == 0
        ? (v66 = Str1)
        : (v66 = (wchar_t *)*((_QWORD *)Str1 + 1)),
          !(unsigned int)RegisterDefaultClass(v66)) )
    {
      v21 = 1407;
      goto LABEL_4;
    }
    v290 = 1;
    v24 = (ULONG_PTR)v315;
  }
  SmartObjStackRefBase<tagCLS>::operator=(v292, *ClassPtr);
  if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)v292[0] + 8LL) + 6LL) & 1) != 0 && (unsigned int)PsGetWin32KFilterSet() == 5 )
    goto LABEL_5;
  v306 = a15;
  if ( (unsigned int)NeedsWindowEdge(a5, v281, a15 >= 0x400u) )
    v47 = v46 | 0x100;
  else
    v47 = v46 & 0xFFFFFEFF;
  v296 = v47;
  v281 = v47;
  if ( (_InterlockedCompareExchange((volatile signed __int32 *)v19 + 130, 0, 0) & 1) != 0 )
  {
    v298 = 0x20000;
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 853);
  }
  LOBYTE(v45) = 1;
  v48 = HMAllocObject(v19, v24, v45);
  v49 = v48;
  v314 = (struct tagWND *)v48;
  if ( !v48 )
  {
    if ( (unsigned int)UserGetLastError() == 8 )
      TraceLoggingCreateWindowFailed(
        1u,
        (((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
       * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64);
    goto LABEL_5;
  }
  v50 = (tagObjLock *)(v48 + 56);
  tagObjLock::LockInitialize((tagObjLock *)(v48 + 56));
  v51 = v49 + 40;
  v285 = v49 + 40;
  *(_DWORD *)(*(_QWORD *)(v49 + 40) + 328LL) = (unsigned int)PsGetThreadId(*(PETHREAD *)v19);
  *(_DWORD *)(*(_QWORD *)(v49 + 40) + 332LL) = *(_DWORD *)(*v293 + 56LL);
  *(_QWORD *)(v49 + 328) = v49 + 320;
  *(_QWORD *)(v49 + 320) = v49 + 320;
  *(_QWORD *)(v49 + 344) = v49 + 336;
  *(_QWORD *)(v49 + 336) = v49 + 336;
  *(_QWORD *)(v49 + 360) = v49 + 352;
  *(_QWORD *)(v49 + 352) = v49 + 352;
  *(_QWORD *)(v49 + 408) = v49 + 400;
  *(_QWORD *)(v49 + 400) = v49 + 400;
  *(_DWORD *)(v49 + 396) = 5;
  *(_DWORD *)(v49 + 392) = 1;
  v52 = (tagObjLock *)Win32AllocPoolZInit(32, 1752200021);
  *(_QWORD *)(v49 + 144) = v52;
  if ( !v52 )
  {
    tagObjLock::LockUnInitializeThreadCreator(v50);
    HMFreeObject(v49);
    goto LABEL_5;
  }
  tagObjLock::LockInitialize(v52);
  v336 = (struct tagTHREADINFO **)(v49 + 16);
  if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v49 + 16) + 456LL) + 808LL) & 0x1000000) != 0 )
    *(_DWORD *)(v49 + 384) |= 1u;
  *(_QWORD *)(*(_QWORD *)v51 + 296LL) = 0;
  *(_QWORD *)(v49 + 280) = 0;
  *(_DWORD *)(v49 + 180) = -1;
  *(_QWORD *)(*(_QWORD *)v51 + 168LL) = 0;
  CurrentThreadDpiHostingBehavior = W32GetCurrentThreadDpiHostingBehavior();
  v57 = CurrentThreadDpiHostingBehavior;
  *(_DWORD *)(*(_QWORD *)v51 + 292LL) = CurrentThreadDpiHostingBehavior;
  if ( v283 == 0x4000 )
  {
    if ( v289 && v289 != (struct tagWND *)GetThreadDesktopWindow(0) )
    {
      v58 = 0;
      v59 = PtiCurrent();
      if ( v59 )
      {
        v60 = *((_QWORD *)v59 + 61);
        if ( v60 )
          v58 = *(struct tagWND **)(v60 + 112);
      }
      v54 = v289;
      if ( v289 != v58 )
      {
        v57 = *(_QWORD *)(*((_QWORD *)v289 + 2) + 456LL);
        if ( *v293 == v57 && !IsChildWindowDpiIsolationEnabled(0, v289) )
        {
          v61 = v310;
          v62 = *(_QWORD *)v285;
          *(_DWORD *)(v62 + 288) = *(_DWORD *)(*(_QWORD *)(v310 + 40) + 288LL);
          v63 = *(_DWORD *)(*(_QWORD *)(v61 + 40) + 288LL);
          if ( (((unsigned __int8)v63
               ^ (unsigned __int8)W32GetCurrentThreadDpiAwarenessContext(v62, v285, v61, v56))
              & 0xF) != 0 )
            TraceChildWindowDpiTelemetry(v49, v289, 0);
          v51 = v49 + 40;
          goto LABEL_100;
        }
      }
    }
    v51 = v49 + 40;
  }
  CurrentThreadDpiAwarenessContext = W32GetCurrentThreadDpiAwarenessContext(v57, v54, v55, v56);
  *(_DWORD *)(*(_QWORD *)v51 + 288LL) = CurrentThreadDpiAwarenessContext;
  if ( (*(_DWORD *)(*(_QWORD *)v51 + 288LL) & 0x4000000F) == 0 )
  {
    v71 = PsGetCurrentProcessWin32Process(CurrentThreadDpiAwarenessContext, v68, v69, v70);
    v72 = v71;
    if ( v71 )
      v72 = -(__int64)(*(_QWORD *)v71 != 0) & v71;
    if ( (*(_DWORD *)(v72 + 12) & 0x20000000) != 0 )
      *(_DWORD *)(*(_QWORD *)v51 + 288LL) |= 0x40000000u;
  }
LABEL_100:
  v64 = *(_QWORD *)v51;
  v65 = *(_DWORD *)(*(_QWORD *)v51 + 288LL);
  if ( (v65 & 0xF) == 2 && (v65 & 0xF0) == 0x20 )
    *(_DWORD *)(v49 + 380) |= 0x180000u;
  if ( (*(_BYTE *)(v64 + 288) & 0xF) == 3 )
    *(_DWORD *)(v49 + 380) |= 0x80000u;
  v337 = (_QWORD *)(v49 + 136);
  tagWND::SharedMixedObjectPointerFieldpcls<tagCLS>::operator=(v49 + 136, *(_QWORD *)v292[0]);
  *(_DWORD *)(*(_QWORD *)v51 + 28LL) = a5 & 0xEFFFFFFF;
  *(_DWORD *)(*(_QWORD *)v51 + 24LL) = v281 & 0xFDF7FFFF;
  *(_DWORD *)(*(_QWORD *)v51 + 200LL) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v292[0] + 8LL) + 80LL);
  *(_DWORD *)(*(_QWORD *)v51 + 248LL) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v292[0] + 8LL) + 84LL);
  if ( !(unsigned int)ReferenceClass(*(_QWORD *)v292[0], v49) )
    goto LABEL_106;
  v299 = (__int64 *)v51;
  SmartObjStackRefBase<tagCLS>::operator=(v292, *v337);
  if ( !(unsigned int)ClassLock(*(_QWORD *)v292[0], &v341) )
  {
    DereferenceClass(*v293, v49);
LABEL_106:
    tagObjLock::LockUnInitializeThreadCreator(*(tagObjLock **)(v49 + 144));
    Win32FreePool(*(void **)(v49 + 144));
    tagObjLock::LockUnInitializeThreadCreator(v50);
    HMFreeObject(v49);
    goto LABEL_107;
  }
  v291 = 0;
  *(_QWORD *)(*(_QWORD *)v51 + 224LL) = a17;
  v76 = *(_WORD *)(*(_QWORD *)(*(_QWORD *)v292[0] + 8LL) + 2LL);
  if ( v76 == *(_WORD *)(*(_QWORD *)(W32GetUserSessionState(*(_QWORD *)v292[0], v73, v74, v75) + 19704) + 868LL) )
  {
    v77 = v49 + 40;
    *(_QWORD *)(*(_QWORD *)v285 + 208LL) = 0;
  }
  else
  {
    v78 = (__int64 *)*((_QWORD *)v19 + 103);
    v79 = 0;
    if ( v78 )
      v79 = *v78;
    v77 = v49 + 40;
    *(_QWORD *)(*(_QWORD *)v285 + 208LL) = v79;
  }
  *(_DWORD *)(*(_QWORD *)v77 + 236LL) = v26;
  v80 = v49 + 40;
  v81 = *(_QWORD *)v285;
  v82 = (__int64)v289;
  if ( *(_DWORD *)(*(_QWORD *)v285 + 236LL) == 1 )
    v83 = 0;
  else
    v83 = IsTopLevelParent(v289);
  if ( v83 )
    *(_DWORD *)(v81 + 24) |= 8u;
  if ( v25 )
    SetOrClrWF(1, v49, 55360, 0);
  v316[0] = (ULONG_PTR)v19 + 932;
  ++*((_DWORD *)v19 + 233);
  memset_0(v320, 0, 0x70u);
  v330 = v281;
  v320[1] = v308;
  if ( ((unsigned __int64)Str1 & 0xFFFFFFFFFFFF0000uLL) != 0 )
  {
    if ( v301 >= 0 )
    {
      v329 = (wchar_t *)*((_QWORD *)Str1 + 1);
      v334 = *(_OWORD *)v335;
    }
    else
    {
      v329 = *(wchar_t **)(*(_QWORD *)v292[0] + 104LL);
      if ( ((unsigned __int64)v329 & 0xFFFFFFFFFFFF0000uLL) != 0 )
        RtlInitLargeAnsiString(&v334);
    }
  }
  else
  {
    v329 = Str1;
  }
  if ( v295 )
  {
    v328 = *((_QWORD *)v295 + 1);
    v331 = *v340;
    v332 = v340[1];
    v333 = *((_QWORD *)v340 + 1);
  }
  v327 = a5;
  v84 = a6;
  v282 = __PAIR64__(a7, a6);
  v326 = a6;
  v325 = a7;
  v85 = a8;
  LODWORD(Str1) = a8;
  v324 = a8;
  v288 = a9;
  v323 = a9;
  if ( v289 )
    v322 = *(_QWORD *)v289;
  else
    v322 = 0;
  if ( v283 == 0x4000 )
  {
    v86 = v304;
    if ( !v304 )
      v86 = *(struct _HEAD **)v303[0];
    v321 = v86;
    *(_DWORD *)(*(_QWORD *)v285 + 24LL) |= *(_DWORD *)(*(_QWORD *)(v310 + 40) + 24LL) & 0xC4000000;
    v87 = a7;
  }
  else if ( (unsigned __int8)SmartObjStackRef<tagMENU>::operator==(v303) )
  {
    v321 = 0;
  }
  else
  {
    v321 = **(struct _HEAD ***)v303[0];
  }
  v320[0] = *(_QWORD *)&v300.left;
  *(_QWORD *)&v300.left = 0;
  if ( v84 == 0x80000000 || (v88 = v84, v84 == 0x8000) )
    v88 = 0;
  v300.left = v88;
  if ( v87 == 0x80000000 || v87 == 0x8000 )
  {
    v89 = 0;
    v300.top = 0;
  }
  else
  {
    v89 = v87;
    v300.top = v87;
  }
  if ( v85 == 0x80000000 || (v90 = v85, v85 == 0x8000) )
    v90 = 0;
  v300.right = v90 + v88;
  if ( a9 == 0x80000000 || (v91 = a9, a9 == 0x8000) )
    v91 = 0;
  v300.bottom = v89 + v91;
  InheritedMonitor = (struct tagMONITOR *)GetInheritedMonitor((struct tagWND *)v49);
  if ( InheritedMonitor )
  {
    v298 = 1;
  }
  else
  {
    v298 = 0;
    if ( v289 )
      InheritedMonitor = (struct tagMONITOR *)ValidateHmonitorNoRip(*(_QWORD *)(*(_QWORD *)(v310 + 40) + 256LL));
  }
  if ( !InheritedMonitor )
    InheritedMonitor = (struct tagMONITOR *)MonitorFromRect(&v300, 2);
  UpdateWindowMonitorAndDpiInfoHelper((struct tagWND *)v49, InheritedMonitor);
  *(_WORD *)(*(_QWORD *)v285 + 286LL) = 0;
  *(_QWORD *)(v49 + 296) = 0;
  if ( v283 != 0x4000 || IsDpiBoundaryBetweenWindows((const struct tagWND *)v49, v289) )
    UpdateTopLevelWindowDPITransform(v49, InheritedMonitor);
  if ( v283 == 0x4000 )
  {
    if ( v289 )
    {
      *(_WORD *)(*(_QWORD *)v285 + 286LL) = *(_WORD *)(*(_QWORD *)(v310 + 40) + 286LL);
      v93 = (_DWORD *)*((_QWORD *)v289 + 37);
      if ( v93 )
      {
        *(_QWORD *)(v49 + 296) = v93;
        ++*v93;
      }
    }
  }
  v315 = (_QWORD *)(v49 + 24);
  if ( *(_QWORD *)(v49 + 24) )
  {
    MessageWindow = GetMessageWindow(v49);
    *(_OWORD *)v305 = *(_OWORD *)LockPointer(&v340, v49 + 104, MessageWindow);
    HMAssignmentLock(v305, 0);
  }
  if ( (unsigned int)IsWindowDesktopComposed(v49) )
  {
    ThreadDesktopWindow = v289;
    if ( v283 != 0x4000 && (!v289 || v289 != *(struct tagWND **)(*((_QWORD *)v289 + 3) + 112LL)) )
      ThreadDesktopWindow = (const struct tagWND *)GetThreadDesktopWindow(0);
    DwmWindowCreate((struct tagWND *)v49, ThreadDesktopWindow, &v300);
  }
  *(_QWORD *)(*(_QWORD *)v285 + 32LL) = v308;
  *(_QWORD *)(*(_QWORD *)v285 + 120LL) = MapClientNeuterToClientPfn(*(_QWORD *)v292[0], 0, v286);
  v96 = 1;
  v97 = v49;
  if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)v292[0] + 8LL) + 6LL) & 1) != 0 )
  {
    SetOrClrWF(1, v49, 516, 1);
    v98 = 1;
    v97 = v49;
    v99 = 55812;
    v96 = 0;
  }
  else
  {
    v98 = 0;
    v99 = 516;
  }
  SetOrClrWF(v98, v97, v99, v96);
  if ( (*(_BYTE *)(*(_QWORD *)v285 + 30LL) & 0x30) != 0 && (*(_BYTE *)(*(_QWORD *)v285 + 234LL) & 4) != 0 )
  {
    LODWORD(v295) = 0x20000;
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 1206);
  }
  AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)&v312);
  Win32HMThreadLockAlways<tagHOOK>::Win32HMThreadLockAlways<tagHOOK>(BugCheckParameter3, v19, v49);
  v100 = *(_BYTE *)(*(_QWORD *)v285 + 18LL);
  if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v292[0] + 8LL) + 84LL) )
  {
    v101 = Win32AllocPoolZInit(*(unsigned int *)(*(_QWORD *)(*(_QWORD *)v292[0] + 8LL) + 84LL), 1937208149);
    *(_QWORD *)(v49 + 280) = v101;
    if ( !v101 )
    {
      v102 = 5;
      v103 = *(_QWORD *)v285;
      goto LABEL_192;
    }
  }
  v104 = v100 & 4;
  LODWORD(v295) = 0;
  if ( (unsigned int)PsGetWin32KFilterSet() != 5 )
  {
LABEL_196:
    if ( v104 )
      goto LABEL_205;
    if ( (unsigned int)PsGetWin32KFilterSet() == 5 )
    {
      *(_DWORD *)(*(_QWORD *)v285 + 200LL) = (*(_DWORD *)(*(_QWORD *)v285 + 200LL) + 7) & 0xFFFFFFF8;
    }
    else
    {
      if ( !(unsigned int)Feature_UserModeNonClientScrollBars2__private_IsEnabledDeviceUsageNoInline()
        || !Scrollbar::NonClient::UserModeSupportsUserModeScrollBars(v105) )
      {
        goto LABEL_205;
      }
      v107 = Scrollbar::NonClient::UserModeSupportsPartitionedExtraBytes(v106);
      v108 = *(_QWORD *)v285;
      v109 = *(_DWORD *)(*(_QWORD *)v285 + 200LL);
      v110 = (v109 + 7) & 0xFFFFFFF8;
      if ( v107 )
      {
        *(_DWORD *)(v108 + 336) = v110 - v109;
        *(_DWORD *)(*(_QWORD *)v285 + 336LL) += 48;
        goto LABEL_205;
      }
      *(_DWORD *)(v108 + 200) = v110;
    }
    *(_DWORD *)(*(_QWORD *)v285 + 200LL) += 48;
    goto LABEL_205;
  }
  if ( !v104 )
  {
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 1245);
    goto LABEL_196;
  }
LABEL_205:
  ClientExtraBytesTotalSize = GetClientExtraBytesTotalSize((const struct tagWND *)v49);
  if ( ClientExtraBytesTotalSize )
  {
    v112 = xxxClientAllocWindowClassExtraBytes(ClientExtraBytesTotalSize);
    if ( !v112 )
    {
      v102 = 2;
      v103 = *(_QWORD *)v285;
LABEL_192:
      *(_QWORD *)(v103 + 120) = 0;
      SetOrClrWF(1, v49, 516, 1);
LABEL_476:
      v230 = *(_BYTE *)(*v299 + 31) & 0x10;
      if ( v291 )
        Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)v309);
      SetOrClrWF(1, v49, 1152, 1);
      SetOrClrWF(1, v49, 896, 1);
      if ( v230 )
        SetVisible(v49, 0);
      if ( *(_QWORD *)(v49 + 104) )
      {
        if ( v230 )
          zzzLockDisplayAreaAndInvalidateDCCache(*(_QWORD *)(v49 + 104), 16, 0);
        if ( (*(_BYTE *)(*v299 + 31) & 0xC0) == 0x40 && !(unsigned int)IsTopLevelWindow(v49) )
        {
          v232 = *(struct tagTHREADINFO **)(v231 + 16);
          if ( v19 != v232 )
            zzzAttachThreadInput(*v336, v232);
        }
        UnlinkWindow((struct tagWND *)v49);
      }
      ClassUnlock(*(struct tagCLS **)v292[0]);
      xxxFreeWindow(v19, (struct tagWND *)v49);
      if ( v102 )
      {
        v233 = ((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
             * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8);
        v234 = v102;
        goto LABEL_542;
      }
      goto LABEL_543;
    }
    if ( (unsigned int)IsWindowBeingDestroyed(v49)
      || (*(_BYTE *)(_HMPheFromObject(v49) + 25) & 1) != 0
      || *(_QWORD *)(*(_QWORD *)v285 + 296LL) )
    {
      UserSetLastError(87);
      *(_QWORD *)(*(_QWORD *)v285 + 120LL) = 0;
      SetOrClrWF(1, v49, 516, 1);
      v102 = 0;
      goto LABEL_476;
    }
    *(_QWORD *)(*(_QWORD *)v285 + 296LL) = v112;
    v80 = v49 + 40;
  }
  if ( (unsigned int)PsGetWin32KFilterSet() != 5 || v104 )
  {
    v115 = v301;
  }
  else
  {
    v113 = (_QWORD *)GETCLIENTWNDINFO(v49);
    v114 = *(_QWORD *)(*v299 + 120);
    *v113 = v114;
    v115 = v301;
    v118 = *(_QWORD *)(W32GetUserSessionState(v114, v113, v116, v117) + 19704);
    if ( v115 >= 0 )
      v119 = *(_QWORD *)(v118 + 768);
    else
      v119 = *(_QWORD *)(v118 + 576);
    *(_QWORD *)(*(_QWORD *)v80 + 120LL) = v119;
  }
  if ( *(_QWORD *)(*(_QWORD *)v292[0] + 80LL)
    && !*(_QWORD *)(*(_QWORD *)v292[0] + 112LL)
    && (unsigned int)PsGetWin32KFilterSet() != 5 )
  {
    xxxCreateClassSmIcon(v292);
  }
  SetOrClrWF(1, v49, v286, 1);
  if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)v292[0] + 8LL) + 6LL) & 2) != 0 )
    goto LABEL_235;
  if ( v115 < 0 )
  {
    v124 = *(_QWORD *)(W32GetUserSessionState(*(_QWORD *)v292[0], v120, v121, v122) + 19704);
    v127 = Atom;
    if ( (_WORD)Atom == *(_WORD *)(v124 + 868)
      || (v129 = *(_QWORD *)(W32GetUserSessionState(v124, v123, v125, v126) + 19704), v127 == *(_WORD *)(v129 + 878))
      || (v133 = *(_QWORD *)(W32GetUserSessionState(v129, v128, v130, v131) + 19704), v127 == *(_WORD *)(v133 + 882))
      || (v137 = *(_QWORD *)(W32GetUserSessionState(v133, v132, v134, v135) + 19704), v127 == *(_WORD *)(v137 + 904))
      || (v141 = *(_QWORD *)(W32GetUserSessionState(v137, v136, v138, v139) + 19704), v127 == *(_WORD *)(v141 + 870))
      || (v145 = *(_QWORD *)(W32GetUserSessionState(v141, v140, v142, v143) + 19704), v127 == *(_WORD *)(v145 + 874))
      || (v149 = *(_QWORD *)(W32GetUserSessionState(v145, v144, v146, v147) + 19704), v127 == *(_WORD *)(v149 + 880))
      || (v153 = *(_QWORD *)(W32GetUserSessionState(v149, v148, v150, v151) + 19704), v127 == *(_WORD *)(v153 + 898))
      || v127 == *(_WORD *)(*(_QWORD *)(W32GetUserSessionState(v153, v152, v154, v155) + 19704) + 872LL) )
    {
LABEL_235:
      SetOrClrWF(1, v49, 520, 1);
    }
  }
  if ( ((*(_BYTE *)(*(_QWORD *)(*(_QWORD *)v292[0] + 8LL) + 6LL) & 2) != 0 || v115 < 0)
    && v283 != 0x4000
    && (*(_QWORD *)&v300.left = PsGetProcessPeb(**((_QWORD **)*v336 + 57))) != 0 )
  {
    v156 = *(_WORD *)(*(_QWORD *)&v300.left + 844LL);
    if ( v156 == -535 )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 1404);
    if ( v156 == -10600 )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 1405);
    v157 = a15;
    v158 = v281;
  }
  else
  {
    v157 = a15;
    v158 = v281;
  }
  if ( (GetAppCompatFlags(v19) & 0x8000000) != 0 )
  {
    SetOrClrWF(1, v49, 1032, 1);
    v281 = v158 & 0x3F;
    v330 &= 0x3Fu;
  }
  SetOrClrWF(1, v49, 1281, 1);
  SetOrClrWF(1, v49, 1282, 1);
  SetOrClrWF(1, v49, 1284, 1);
  v159 = v157;
  if ( v157 <= *((_WORD *)v19 + 334) )
    v159 = *((_DWORD *)v19 + 167);
  *(_DWORD *)(v49 + 256) = v159;
  if ( (GetAppCompatFlags2(39168) & 0x10000000) != 0 )
    SetOrClrWF(1, v49, 2688, 1);
  if ( (unsigned int)IsInsideUserApiHook() )
    xxxLoadUserApiHook();
  if ( (unsigned int)WantImeWindow(v289, (struct tagWND *)v49) )
  {
    v160 = *((_QWORD *)v19 + 102);
    if ( v160
      && ((*(_BYTE *)(_HMPheFromObject(v160) + 25) & 1) != 0
       || (unsigned int)IsWindowBeingDestroyed(*((_QWORD *)v19 + 102))) )
    {
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1489);
    }
    *(_DWORD *)(v49 + 380) |= 0x10000000u;
    ++*((_DWORD *)v19 + 235);
  }
  if ( ((*((_BYTE *)v19 + 712) | *(_BYTE *)(**((_QWORD **)v19 + 62) + 16LL)) & 0x40) != 0 )
  {
    v312 = (__int64)v320;
    v313 = 0;
    if ( (unsigned int)xxxCallHook(3, *(_QWORD *)v49, (__int64)&v312, 5) )
    {
      v102 = 6;
      goto LABEL_476;
    }
    v282 = __PAIR64__(v325, v326);
    LODWORD(Str1) = v324;
    v288 = v323;
    v307 = v313;
  }
  else
  {
    v307 = 0;
  }
  if ( (*(_BYTE *)(*(_QWORD *)v285 + 31LL) & 0xC0) != 0x40 )
  {
    v161 = 0;
    v284 = 0;
    goto LABEL_269;
  }
  v161 = 1;
  v284 = 1;
  if ( !v289 )
    goto LABEL_475;
LABEL_269:
  v162 = 0;
  v287 = 5;
  if ( v161 != v319 )
  {
    v304 = 0;
    SmartObjStackRefBase<tagMENU>::operator=(v303, 0);
    v161 = v284;
  }
  if ( (*(_BYTE *)(*(_QWORD *)v285 + 31LL) & 0xC0) != 0 )
  {
    v163 = 0;
    if ( (_DWORD)v282 == 0x80000000 || (_DWORD)v282 == 0x8000 )
      v282 = 0;
    v164 = (unsigned int)Str1;
    if ( (_DWORD)Str1 == 0x80000000 || (_DWORD)Str1 == 0x8000 )
    {
      v164 = 0;
      LODWORD(Str1) = 0;
      v288 = 0;
    }
  }
  else
  {
    v163 = 1;
    v164 = (unsigned int)Str1;
  }
  *(_QWORD *)&v344 = v282;
  *((_QWORD *)&v344 + 1) = __PAIR64__(v288, v164);
  if ( v161 )
  {
    v317 = *(_OWORD *)(*(_QWORD *)(v310 + 40) + 104LL);
    if ( IsDpiBoundaryBetweenWindows((const struct tagWND *)v49, v289) )
    {
      *(_DWORD *)(v49 + 224) = 0;
      *(_DWORD *)(v49 + 228) = 0;
      LogicalToPhysicalInPlaceRectWithSubpixel(v289, &v317, v49 + 224);
      PhysicalToLogicalInPlaceRectWithSubpixel(v49, &v317, v49 + 224);
    }
    if ( v289 != (struct tagWND *)GetDesktopWindow(v49) )
    {
      LODWORD(v344) = v317 + v165;
      DWORD1(v344) = DWORD1(v317) + v166;
    }
    v307 = 1;
  }
  if ( v163 )
  {
    v167 = 0;
    SetOrClrWF(1, v49, 3844, 1);
    v168 = 192;
    SetOrClrWF(1, v49, 2305, 1);
    SetOrClrWF(1, v49, 16, 1);
    v169 = v282;
    if ( (_DWORD)v282 == 0x80000000 || (_DWORD)v282 == 0x8000 )
    {
      if ( DWORD1(v344) != 0x80000000 )
      {
        v170 = 5;
        if ( DWORD1(v344) != 0x8000 )
          v170 = DWORD1(v344);
        v287 = v170;
      }
      v169 = v282;
    }
    if ( !v298 && (v169 == 0x80000000 || v169 == 0x8000 || (_DWORD)Str1 == 0x80000000 || (_DWORD)Str1 == 0x8000) )
    {
      v171 = *(_QWORD *)(*v293 + 680LL);
      if ( v171 )
      {
        v172 = (struct tagMONITOR *)ValidateHmonitor(v171);
        goto LABEL_302;
      }
      if ( v289 )
      {
        v172 = _MonitorFromWindowInternal(v289, 2u, 0);
LABEL_302:
        v167 = (__int64)v172;
      }
      if ( !v167 )
      {
        v167 = *(_QWORD *)(GetDispInfo(v171) + 96);
        goto LABEL_305;
      }
    }
    else
    {
LABEL_305:
      if ( !v167 )
      {
        v167 = ValidateHmonitor(*(_QWORD *)(*(_QWORD *)v285 + 256LL));
        if ( !v167 )
        {
          if ( v298 )
            v167 = GetInheritedMonitor((struct tagWND *)v49);
          else
            v167 = 0;
          if ( !v167 )
            v167 = MonitorFromRect(*(_QWORD *)v285 + 88LL, 2);
          UpdateWindowMonitorAndDpiInfoHelper((struct tagWND *)v49, (struct tagMONITOR *)v167);
          UpdateTopLevelWindowDPITransform(v49, v167);
        }
      }
    }
    SetTiledRect(v49, &v345, v167);
    v173 = v282;
    if ( (_DWORD)v282 == 0x80000000 || (_DWORD)v282 == 0x8000 )
    {
      v176 = v293;
      if ( (*(_DWORD *)(*v293 + 792LL) & 4) != 0 )
      {
        v162 = 1;
        v173 = *(_DWORD *)(*v293 + 776LL);
        LODWORD(v344) = v173;
        v177 = *(_DWORD *)(*v293 + 780LL);
      }
      else
      {
        v173 = v345;
        LODWORD(v344) = v345;
        v177 = DWORD1(v345);
      }
      DWORD1(v344) = v177;
      v282 = __PAIR64__(v177, v173);
      v174 = 1;
    }
    else
    {
      v174 = 0;
      v175 = *(_WORD *)(v167 + 74);
      v176 = v293;
      if ( v175 )
        *(_WORD *)(v167 + 74) = v175 - 1;
    }
    if ( DWORD2(v344) == 0x80000000 || DWORD2(v344) == 0x8000 )
    {
      if ( (*(_DWORD *)(*v176 + 792LL) & 2) != 0 )
      {
        v162 = 1;
        *((_QWORD *)&v344 + 1) = *(_QWORD *)(*v176 + 784LL);
      }
      else
      {
        DWORD2(v344) = DWORD2(v345) - v173;
        HIDWORD(v344) = HIDWORD(v345) - HIDWORD(v282);
      }
    }
    else if ( v174 )
    {
      MonitorRect = (int *)GetMonitorRect(v305, v167);
      v179 = MonitorRect[1];
      v180 = v344 + DWORD2(v344) - MonitorRect[2];
      v181 = DWORD1(v344) + HIDWORD(v344) - MonitorRect[3];
      if ( v180 > 0 )
      {
        v182 = *MonitorRect;
        LODWORD(v282) = v282 - v180;
        LODWORD(v344) = v282;
        if ( (int)v282 < v182 )
        {
          LODWORD(v282) = v182;
          LODWORD(v344) = v182;
        }
      }
      if ( v181 > 0 )
      {
        HIDWORD(v282) -= v181;
        DWORD1(v344) = HIDWORD(v282);
        if ( SHIDWORD(v282) < v179 )
        {
          HIDWORD(v282) = v179;
          DWORD1(v344) = v179;
        }
      }
    }
  }
  else
  {
    v168 = 0;
  }
  if ( v162 )
    *(_DWORD *)(*v293 + 792LL) &= 0xFFFFFFF9;
  v183 = v49 + 40;
  if ( (((*(_BYTE *)(*(_QWORD *)v285 + 31LL) & 0xC0) + 0x80) & 0xBF) == 0 )
    SetOrClrWF(1, v49, 3844, 1);
  *(_WORD *)(*(_QWORD *)v285 + 30LL) |= v168;
  if ( (unsigned __int8)SmartObjStackRef<tagMENU>::operator==(v303) && !v284 && *(_QWORD *)(*(_QWORD *)v292[0] + 96LL) )
  {
    v300 = 0;
    v185 = v49;
    if ( *(_QWORD *)(v49 + 104) )
      v185 = *(_QWORD *)(v49 + 104);
    zzzLockDisplayAreaAndInvalidateDCCache(v185, 16, 0);
    RtlInitUnicodeStringOrId(&v300, *(_QWORD *)(*(_QWORD *)v292[0] + 96LL));
    v186 = xxxClientLoadMenu(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v292[0] + 8LL) + 64LL), &v300);
    v304 = 0;
    SmartObjStackRefBase<tagMENU>::operator=(v303, v186);
    if ( (*(_BYTE *)(*(_QWORD *)v285 + 31LL) & 0xC0) != 0x40 && !(unsigned int)IsWindowBeingDestroyed(v49) )
    {
      if ( (unsigned __int8)SmartObjStackRef<tagMENU>::operator==(v303) )
        v321 = 0;
      else
        v321 = **(struct _HEAD ***)v303[0];
      goto LABEL_347;
    }
    v189 = v304;
    if ( !v304 )
      v189 = *(struct _HEAD **)v303[0];
    DestroyMenu(v189);
    v304 = 0;
    SmartObjStackRefBase<tagMENU>::operator=(v303, 0);
LABEL_475:
    v102 = (int)v295;
    goto LABEL_476;
  }
LABEL_347:
  WindowCloakStateComponentUIAware = 0;
  if ( (*(_BYTE *)(*(_QWORD *)v285 + 31LL) & 0xC0) == 0x40 )
  {
    v188 = v304;
    if ( !v304 )
      v188 = *(struct _HEAD **)v303[0];
    *(_QWORD *)(*(_QWORD *)v285 + 320LL) = v188;
    *(_QWORD *)(*(_QWORD *)(v49 + 40) + 152LL) = 0;
    *(_QWORD *)(v49 + 168) = 0;
  }
  else
  {
    *(_QWORD *)(*(_QWORD *)v285 + 320LL) = 0;
    LockWndMenuWorker(v49, 0, v303);
  }
  if ( (*(_BYTE *)(*(_QWORD *)v285 + 31LL) & 0xC0) != 0x40 )
  {
    if ( (a16 & 4) != 0 )
    {
      LOBYTE(v184) = 1;
      CoreWindowProp::ChangeRole(v49, 1, v184);
    }
    *(_OWORD *)v305 = *(_OWORD *)LockPointer(&v300, v49 + 200, v49);
    HMAssignmentLock(v305, 0);
    if ( (unsigned int)IsTopLevelParent(v289) )
    {
      v192 = v49 + 120;
      *(_QWORD *)(*(_QWORD *)(v49 + 40) + 64LL) = 0;
      *(_QWORD *)&v300.left = v49 + 120;
      *(_QWORD *)&v300.right = 0;
      HMAssignmentLock(&v300, 0);
    }
    else
    {
      NonChildAncestor = GetNonChildAncestor(v190);
      if ( !(unsigned int)ValidateOwnerDepth(v49, NonChildAncestor) )
        goto LABEL_360;
      if ( NonChildAncestor )
      {
        *(_DWORD *)(*(_QWORD *)v285 + 236LL) = *(_DWORD *)(*(_QWORD *)(NonChildAncestor + 40) + 236LL);
        SetOrClrWF(*(_BYTE *)(*(_QWORD *)(NonChildAncestor + 40) + 232LL) & 0x40, v49, 55360, 1);
        WindowCloakStateComponentUIAware = GetWindowCloakStateComponentUIAware(NonChildAncestor);
      }
      v192 = v49 + 120;
      *(_OWORD *)v305 = *(_OWORD *)LockPointer(&v300, v49 + 120, NonChildAncestor);
      HMAssignmentLock(v305, 1);
      if ( *(_QWORD *)(v49 + 120)
        && ((*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v49 + 120) + 40LL) + 24LL) & 8) != 0
         || *(_DWORD *)(*(_QWORD *)v285 + 236LL) != 1) )
      {
        SetOrClrWF(1, v49, 2056, 1);
      }
      v197 = *(_QWORD *)(W32GetUserSessionState(v194, v193, v195, v196) + 19704);
      if ( (_WORD)Atom != *(_WORD *)(v197 + 898) )
      {
        if ( *(_QWORD *)v192 )
        {
          v198 = *(struct tagTHREADINFO **)(*(_QWORD *)v192 + 16LL);
          if ( v198 != v19 )
            zzzAttachThreadInput(v19, v198);
        }
      }
      v183 = v49 + 40;
    }
    IsEnabledDeviceUsageNoInline = Feature_Scoobe_ShellHost__private_IsEnabledDeviceUsageNoInline();
    if ( !*(_QWORD *)v192 )
    {
      if ( IsEnabledDeviceUsageNoInline )
      {
        if ( (unsigned int)CoreWindowProp::IsComponent((const struct tagWND *)v49) )
          goto LABEL_389;
        v200 = *(_DWORD *)(*(_QWORD *)v183 + 236LL);
        if ( (unsigned int)(v200 - 8) <= 3 || v200 == 15 )
          goto LABEL_388;
        v201 = (*(_BYTE *)(*(_QWORD *)v183 + 232LL) & 0x40) == 0;
      }
      else
      {
        if ( (unsigned int)CoreWindowProp::IsComponent((const struct tagWND *)v49) )
          goto LABEL_389;
        v202 = *(_DWORD *)(*(_QWORD *)v183 + 236LL);
        if ( v202 <= 0xF )
        {
          v203 = 44800;
          if ( _bittest(&v203, v202) )
            goto LABEL_388;
        }
        v201 = (*(_BYTE *)(*(_QWORD *)v183 + 232LL) & 0x40) == 0;
      }
      if ( !v201 )
LABEL_388:
        WindowCloakStateComponentUIAware = 2;
    }
LABEL_389:
    if ( v289 && v289 == *(struct tagWND **)(*((_QWORD *)v289 + 3) + 112LL) )
    {
      v204 = v19;
    }
    else
    {
      v82 = GetThreadDesktopWindow(0);
      v289 = (struct tagWND *)v82;
      v204 = v19;
      Win32HM_LockIntoThread<1>(v19, v82, v309);
      v291 = 1;
    }
    if ( !v302 )
      goto LABEL_399;
    if ( !*((_QWORD *)v204 + 198) )
    {
      SetOrClrWF(1, v49, 55424, 1);
      *((_QWORD *)v204 + 170) |= 0x40000uLL;
      *(_DWORD *)(*((_QWORD *)v204 + 58) + 508LL) |= 0x2000000u;
      if ( !*((_QWORD *)v204 + 197) )
      {
        KernelEvent = CreateKernelEvent(1, 0);
        *((_QWORD *)v204 + 197) = KernelEvent;
        if ( !KernelEvent )
        {
          v102 = 7;
          goto LABEL_476;
        }
      }
      *(_QWORD *)&v300.left = (char *)v204 + 1584;
      *(_QWORD *)&v300.right = v49;
      HMAssignmentLock(&v300, 0);
      goto LABEL_399;
    }
LABEL_360:
    UserSetLastError(87);
    goto LABEL_475;
  }
  if ( !v289 )
    goto LABEL_475;
  if ( v302 )
    goto LABEL_360;
LABEL_399:
  v206 = 0;
  if ( (*(_DWORD *)(v49 + 380) & 0x1000000) != 0 )
  {
    v206 = *(_QWORD *)(v49 + 104);
    UnlinkWindow((struct tagWND *)v49);
  }
  if ( !(unsigned int)IsTopLevelParent(v82) )
  {
    *(_DWORD *)(*(_QWORD *)v285 + 236LL) = *(_DWORD *)(*(_QWORD *)(v82 + 40) + 236LL);
    SetOrClrWF(*(_BYTE *)(*(_QWORD *)(v82 + 40) + 232LL) & 0x40, v49, 55360, 1);
  }
  if ( v82 && !(unsigned int)ValidateNewParent(v49, v82, 1) )
  {
    v102 = 9;
    goto LABEL_476;
  }
  v207 = (struct tagWND **)(v49 + 104);
  *(_OWORD *)v305 = *(_OWORD *)LockPointer(&v300, v49 + 104, v289);
  HMAssignmentLock(v305, 0);
  if ( v289 )
    v208 = (unsigned int)-__CFSHR__(*(_DWORD *)(*((_QWORD *)v289 + 5) + 232LL), 10);
  else
    v208 = 0;
  SetWindowSubtreeCoreWindowStatus(v49, v208);
  v209 = *(_QWORD *)(v49 + 40);
  if ( (*(_DWORD *)(v209 + 288) & 0xF) == 2 )
    *(_DWORD *)(v209 + 232) = *(_DWORD *)(v209 + 232) & 0xFFFFFBFF
                            | (ShouldUseLogPixelsForWindowMetrics((struct tagWND *)v49) << 10);
  if ( (WindowCloakStateComponentUIAware & 2) == 0 )
    *(_DWORD *)(v49 + 384) |= 4u;
  if ( WindowCloakStateComponentUIAware )
  {
    v210 = zzzSetWindowCompositionCloak(v49, WindowCloakStateComponentUIAware);
    if ( v210 < 0 )
    {
      v211 = RtlNtStatusToDosError(v210);
      UserSetLastError(v211);
      v102 = 8;
      goto LABEL_476;
    }
  }
  AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)v305);
  if ( v206 )
    zzzLockDisplayAreaAndInvalidateDCCache(v206, 16, 0);
  if ( v289 )
    zzzLockDisplayAreaAndInvalidateDCCache(v289, 16, 0);
  AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v305);
  v215 = *(_QWORD *)(v49 + 40);
  if ( (*(_BYTE *)(v215 + 31) & 0xC0) == 0x40 && !(unsigned int)IsTopLevelWindow(v49) )
  {
    v216 = (struct tagTHREADINFO **)*v207;
    if ( *v207 )
    {
      if ( v19 != v216[2] )
      {
        if ( v289 != (struct tagWND *)v216 )
        {
          v302 = 0x20000;
          MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 2199);
        }
        zzzAttachThreadInput(v19, *((struct tagTHREADINFO **)*v207 + 2));
        v217 = GetMessageWindow(v49);
        if ( v214 != (struct tagWND *)v217 )
        {
          v213 = *((_QWORD *)v214 + 5);
          v215 = *(unsigned int *)(*v299 + 288);
          if ( (((unsigned __int8)v215 ^ *(_BYTE *)(v213 + 288)) & 0xF) != 0
            && !IsChildWindowDpiIsolationEnabled((struct tagWND *)v49, v214) )
          {
            xxxForceUpdateProcessDpiAwarenessContext((struct tagWND *)v49, *(_DWORD *)(*((_QWORD *)*v207 + 5) + 288LL));
          }
        }
      }
    }
  }
  v218 = W32GetUserSessionState(v215, v212, v213, v214);
  if ( v311 != *(unsigned __int16 *)(v218 + 41168) && v311 != 32769 && !*(_DWORD *)v316[0] )
  {
    _InterlockedExchange(
      (volatile __int32 *)(*((_QWORD *)v19 + 60) + 20LL),
      (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24);
    xxxUpdateInputHangInfo(0, 1);
  }
  xxxAdjustSize((struct tagWND *)v49);
  ConstrainWindowSIZERECT(&v344);
  if ( *v315 && (*(_BYTE *)(*v299 + 31) & 0x40) == 0 && *(char *)(*v299 + 24) >= 0 )
    CheckFullScreen((struct tagWND *)v49);
  v219 = DWORD2(v344);
  if ( SDWORD2(v344) < 0 )
    v219 = 0;
  DWORD2(v344) = v219;
  v220 = HIDWORD(v344);
  if ( v344 < 0 )
    v220 = 0;
  HIDWORD(v344) = v220;
  RECTFromSIZERECT(*v299 + 88, &v344);
  if ( v284 )
  {
    v221 = ValidateHmonitorNoRip(*(_QWORD *)(*((_QWORD *)v289 + 5) + 256LL));
LABEL_447:
    v222 = (struct tagMONITOR *)v221;
  }
  else
  {
    if ( v298 )
    {
      v221 = GetInheritedMonitor((struct tagWND *)v49);
      goto LABEL_447;
    }
    v222 = 0;
  }
  if ( v222 || (v222 = (struct tagMONITOR *)MonitorFromRect(*v299 + 88, 2), v223 = 0, v222) )
    v223 = *(_QWORD *)v222;
  if ( v223 != *(_QWORD *)(*v299 + 256) )
  {
    UpdateWindowMonitorAndDpiInfoHelper((struct tagWND *)v49, v222);
    if ( !v284 )
      UpdateTopLevelWindowDPITransform(v49, v222);
  }
  v224 = v299;
  if ( (*(_BYTE *)(*v299 + 27) & 0x20) != 0 && GetRedirectionBitmap(v49) )
  {
    GreLockVisRgn();
    if ( (int)RecreateRedirectionBitmap((struct tagWND *)v49, 0, 0) < 0 )
    {
      GreUnlockVisRgn();
      v102 = 3;
      goto LABEL_476;
    }
    GreUnlockVisRgn();
  }
  if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)v292[0] + 8LL) + 8LL) & 0x20) != 0
    || (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)v292[0] + 8LL) + 8LL) & 0x40) != 0 && !*(_QWORD *)(*(_QWORD *)v292[0] + 40LL) )
  {
    StyleWindow = GetStyleWindow(v49, 2848);
    GreLockVisRgn();
    if ( !CreateCacheDC(v49, StyleWindow != 0 ? 49152 : 0x8000, 0) )
    {
      GreUnlockVisRgn();
      v102 = 10;
      goto LABEL_476;
    }
    GreUnlockVisRgn();
    v224 = v299;
  }
  v226 = v281;
  if ( (v281 & 0x80000) != 0 && (*(_BYTE *)(*v224 + 26) & 8) == 0 )
  {
    if ( (int)xxxSetLayeredWindow((struct tagWND *)v49) < 0 )
    {
      v102 = 11;
      goto LABEL_476;
    }
    v226 = v281;
  }
  if ( (v226 & 0x2000000) != 0 && !GetStyleWindow(*v207, 2818) )
  {
    SetOrClrWF(1, v49, 2818, 1);
    if ( (int)SetRedirectedWindow((struct tagWND *)v49) < 0 )
    {
      SetOrClrWF(0, v49, 2818, 1);
      v102 = 12;
      goto LABEL_476;
    }
  }
  v325 = HIDWORD(v282);
  v326 = v282;
  v324 = (int)Str1;
  v323 = v288;
  if ( !xxxSendTransformableMessageTimeout((struct tagWND *)v49, 0x81u, 0, 0, 0, 1, 1) )
    goto LABEL_475;
  v235 = *(_QWORD *)(*v337 + 8LL);
  if ( (*(_BYTE *)(v235 + 9) & 2) != 0 )
  {
    SystemMenu = xxxGetSystemMenu((struct tagWND *)v49);
    v304 = 0;
    SmartObjStackRefBase<tagMENU>::operator=(v303, SystemMenu);
    if ( !(unsigned __int8)SmartObjStackRef<tagMENU>::operator==(v303) )
    {
      Win32HMThreadLock<tagMENU>::Win32HMThreadLock<tagMENU>(v305, v303);
      xxxRemoveDeleteMenuHelper(v303, 5, 1024, 1);
      xxxRemoveDeleteMenuHelper(v303, 5, 1024, 1);
      Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)v305);
    }
  }
  if ( (*(_BYTE *)(*v224 + 18) & 2) != 0 && (!v333 || v331 || *(_QWORD *)(v49 + 184)) )
  {
    *(_OWORD *)v305 = 0;
    v328 = *(_QWORD *)(v49 + 184);
    StrName = tagWND::ProtectedLargeUnicodeStringWNDstrName::getStrName(
                (tagWND::ProtectedLargeUnicodeStringWNDstrName *)(v49 + 184),
                (struct _LARGE_UNICODE_STRING *)v305);
    v331 = *(_DWORD *)StrName;
    v235 = *((unsigned int *)StrName + 1);
    v332 = *((_DWORD *)StrName + 1);
    v333 = *((_QWORD *)StrName + 1);
  }
  if ( (**(_DWORD **)(W32GetUserSessionState(v235, v227, v228, v229) + 19704) & 4) != 0 )
  {
    v238 = (struct tagWND **)((char *)v19 + 816);
    if ( !*((_QWORD *)v19 + 102) && (*(_DWORD *)(v49 + 380) & 0x10000000) != 0 )
    {
      DefaultImeWindow = xxxCreateDefaultImeWindow((struct tagWND *)v49, Atom, v308);
      v316[0] = (ULONG_PTR)v19 + 816;
      v316[1] = (ULONG_PTR)DefaultImeWindow;
      HMAssignmentLock(v316, 0);
      if ( *v238 )
      {
        Win32HMThreadLockAlways<tagHOOK>::Win32HMThreadLockAlways<tagHOOK>(v305, v19, *v238);
        xxxSendTransformableMessageTimeout(*v238, 0x287u, 0, 0, 0, 1, 1);
        Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)v305);
      }
      v240 = (**((_DWORD **)v19 + 64) >> 6) & 1;
      v339 = v240;
      if ( *v238 && v240 )
      {
        Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(v316, *v238);
        xxxSendTransformableMessageTimeout(*v238, 0x287u, 0, 0, 0, 1, 1);
        **((_QWORD **)v19 + 64) &= ~0x40uLL;
        Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)v316);
      }
    }
  }
  v241 = v289;
  if ( v289 && ((*(_DWORD *)(v49 + 380) & 0x1000000) == 0 || *v207 == v289) )
  {
    CompositeAppFrameWindowOrSelf = PWInsertAfter(v307);
    if ( !(unsigned int)IsPseudoPwnd(CompositeAppFrameWindowOrSelf)
      && *(struct tagWND **)(CompositeAppFrameWindowOrSelf + 104) != *v207 )
    {
      CompositeAppFrameWindowOrSelf = v284 != 0;
    }
    v243 = *(_QWORD *)(v49 + 120);
    if ( v243 )
    {
      *(_DWORD *)(*v299 + 236) = *(_DWORD *)(*(_QWORD *)(v243 + 40) + 236LL);
      SetOrClrWF(*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v49 + 120) + 40LL) + 232LL) & 0x40, v49, 55360, 1);
    }
    if ( !(unsigned int)ValidateNewParent(v49, v289, 1) )
    {
      v244 = 9;
      goto LABEL_536;
    }
    UnlinkWindow((struct tagWND *)v49);
    v247 = *v299;
    v248 = v289;
    if ( (*(_BYTE *)(*v299 + 31) & 0xC0) != 0x40 && v289 != *(struct tagWND **)(*((_QWORD *)v289 + 3) + 112LL) )
    {
      if ( (*(_BYTE *)(v247 + 24) & 8) != 0 )
      {
        if ( *(_QWORD *)(W32GetUserSessionState(v247, v289, v245, v246) + 19160) )
        {
          TopMostInsertAfter = GetTopMostInsertAfter(v49);
          if ( TopMostInsertAfter )
            CompositeAppFrameWindowOrSelf = TopMostInsertAfter;
        }
      }
      else if ( !CompositeAppFrameWindowOrSelf
             || !(unsigned int)IsPseudoPwnd(CompositeAppFrameWindowOrSelf)
             && (*(_BYTE *)(*(_QWORD *)(CompositeAppFrameWindowOrSelf + 40) + 24LL) & 8) != 0 )
      {
        v249 = (const struct tagWND *)CalcForegroundInsertAfter(v49, v248);
        CompositeAppFrameWindowOrSelf = (unsigned __int64)v249;
        if ( !*(_QWORD *)(v49 + 120) )
          CompositeAppFrameWindowOrSelf = (unsigned __int64)CoreWindowProp::GetCompositeAppFrameWindowOrSelf(v249);
      }
    }
    if ( CompositeAppFrameWindowOrSelf >= 2 && (unsigned int)IsPseudoPwnd(CompositeAppFrameWindowOrSelf) )
    {
      v244 = 13;
      goto LABEL_536;
    }
    LinkWindow((struct tagWND *)v49);
    zzzLockDisplayAreaAndInvalidateDCCache(v289, 16, 0);
    v241 = v289;
  }
  v251 = v299;
  v252 = *v299;
  if ( (*(_BYTE *)(*v299 + 31) & 0xC0) == 0x40 && (*(_BYTE *)(*((_QWORD *)v241 + 5) + 26LL) & 0x40) != 0 )
  {
    v253 = *(_DWORD *)(v252 + 96);
    v254 = *(_DWORD *)(v252 + 88);
    *(_DWORD *)(v252 + 96) = DWORD2(v317) + v317 - v254;
    *(_DWORD *)(*v251 + 88) = v254 + *(_DWORD *)(*v251 + 96) - v253;
  }
  v345 = *(_OWORD *)(*v251 + 88);
  xxxSendTransformableMessageTimeout((struct tagWND *)v49, 0x83u, 0, 0, 0, 1, 0);
  *(_OWORD *)(*v251 + 104) = v345;
  if ( xxxSendTransformableMessageTimeout((struct tagWND *)v49, 1u, 0, 0, 0, 1, 1) == -1 )
  {
    v244 = (int)v295;
LABEL_536:
    if ( v291 )
      Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)v309);
    if ( Win32HMThreadLockBase<tagMENU,0,1>::ManualUnlock<void>((ULONG_PTR)BugCheckParameter3) )
      xxxDestroyWindow((struct tagWND *)v49);
    ClassUnlock(*(struct tagCLS **)v292[0]);
    if ( v244 )
    {
      v233 = ((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
           * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8);
      v234 = v244;
LABEL_542:
      TraceLoggingCreateWindowFailed(v234, *((unsigned __int64 *)&v233 + 1));
    }
LABEL_543:
    Win32HMOptionalThreadLockAlways<tagMENU>::~Win32HMOptionalThreadLockAlways<tagMENU>((ULONG_PTR)BugCheckParameter3);
    goto LABEL_6;
  }
  SetOrClrWF(1, v49, 1920, 1);
  xxxConsiderPreferredDpiChange((struct tagWND *)v49);
  if ( (unsigned int)IsWindowDesktopComposed(v49) )
  {
    v258 = (void *)ReferenceDwmApiPort(v256, v255, v257);
    DwmAsyncChildStyleChange(v258);
    DwmChildRectChange((struct tagWND *)v49);
    DirtyVisRgnTrackers((struct tagWND *)v49);
    v262 = (void *)ReferenceDwmApiPort(v260, v259, v261);
    DwmAsyncOwnerChange(v262);
    v251 = v299;
  }
  xxxWindowEvent(0x8000u, (struct tagWND *)v49, 0, 0, 0);
  if ( (*(_BYTE *)(*v251 + 16) & 0x10) == 0 )
  {
    xxxSendSizeMessage((struct tagWND *)v49);
    if ( v289 )
    {
      DesktopWindow = GetDesktopWindow(v49);
      if ( DesktopWindow != v268 )
      {
        LODWORD(v345) = v345 - v317;
        DWORD1(v345) -= DWORD1(v317);
      }
    }
    xxxSendTransformableMessageTimeout((struct tagWND *)v49, 3u, 0, 0, 0, 1, 0);
  }
  v269 = *(_DWORD *)(W32GetUserSessionState(v264, v263, v265, v266) + 66784) & 0x10000 | 1;
  v270 = v299;
  v271 = *(_BYTE *)(*v299 + 31);
  if ( (v271 & 0x20) != 0 )
  {
    SetMinimize(v49, 0);
    v272 = 7;
    goto LABEL_555;
  }
  if ( (v271 & 1) != 0 )
  {
    SetOrClrWF(0, v49, 3841, 1);
    v269 |= 0x10u;
    v272 = 3;
LABEL_555:
    xxxMinMaximize(v49, v272, v269);
  }
  CalcWindowFullScreen((struct tagWND *)v49);
  if ( (*(_BYTE *)(*v270 + 31) & 0xC0) == 0x40 && (*(_BYTE *)(*v270 + 24) & 4) == 0 && *v207 )
  {
    Win32HMThreadLockAlways<tagWND>::Win32HMThreadLockAlways<tagWND>(v305, v19, v49 + 104);
    xxxSendTransformableMessageTimeout(*v207, 0x210u, 0, 0, 0, 1, 0);
    Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)v305);
  }
  xxxInheritWindowMonitor((struct tagWND *)v49);
  CDwmWindowNotifyBatch::CDwmWindowNotifyBatch((CDwmWindowNotifyBatch *)v343, (struct tagWND *)v49);
  if ( (a5 & 0x10000000) != 0 )
  {
    v277 = W32GetUserSessionState(v274, v273, v275, v276);
    xxxShowWindowEx(
      v49,
      v287 | *(_DWORD *)(v277 + 66784) & 0x10000u,
      v287 & 0x10000 | *(_DWORD *)(v277 + 66784) & 0x10000u);
  }
  CDwmWindowNotifyBatch::~CDwmWindowNotifyBatch((CDwmWindowNotifyBatch *)v343);
  if ( (*(_BYTE *)(*v270 + 31) & 0xC0) == 0 || (*(_BYTE *)(*v270 + 26) & 4) != 0 )
  {
    v278 = v293;
    if ( *(_DWORD *)(*v293 + 676LL) )
    {
      xxxSendTransformableMessageTimeout((struct tagWND *)v49, 0x32u, 0, 0, 0, 1, 1);
      *(_DWORD *)(*v278 + 676LL) = 0;
    }
  }
  if ( v291 )
    Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)v309);
  ClassUnlock(*(struct tagCLS **)v292[0]);
  v279 = Win32HMThreadLockBase<tagMENU,0,1>::ManualUnlock<void>((ULONG_PTR)BugCheckParameter3);
  v280 = v279;
  if ( !v279 || (*(_BYTE *)(_HMPheFromObject(v279) + 25) & 1) != 0 )
    v280 = 0;
  Win32HMOptionalThreadLockAlways<tagMENU>::~Win32HMOptionalThreadLockAlways<tagMENU>((ULONG_PTR)BugCheckParameter3);
  SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(v303);
  Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)v309);
  SmartObjStackRef<tagPOPUPMENU>::~SmartObjStackRef<tagPOPUPMENU>(v292);
  return v280;
}

```

## disassembly

```asm
0x1401494f4  push    rbx
0x1401494f6  push    rsi
0x1401494f7  push    rdi
0x1401494f8  push    r12
0x1401494fa  push    r13
0x1401494fc  push    r14
0x1401494fe  push    r15
0x140149500  sub     rsp, 2F0h
0x140149507  mov     rax, cs:__security_cookie
0x14014950e  xor     rax, rsp
0x140149511  mov     [rsp+328h+var_40], rax
0x140149519  mov     rax, r9
0x14014951c  mov     [rsp+328h+var_B8], rax
0x140149524  mov     [rsp+328h+var_E8], rdx
0x14014952c  mov     [rsp+328h+var_248], ecx
0x140149533  mov     [rsp+328h+var_2C8], ecx
0x140149537  mov     edi, ecx
0x140149539  mov     [rsp+328h+var_2D8], ecx
0x14014953d  mov     [rsp+328h+var_270], ecx
0x140149544  mov     [rsp+328h+Str1], rdx
0x14014954c  mov     [rsp+328h+var_1E8], r8
0x140149554  mov     [rsp+328h+var_278], rax
0x14014955c  mov     r13, [rsp+328h+arg_48]
0x140149564  mov     [rsp+328h+var_2B0], r13
0x140149569  mov     [rsp+328h+var_210], r13
0x140149571  mov     rbx, [rsp+328h+arg_50]
0x140149579  mov     rax, [rsp+328h+arg_58]
0x140149581  mov     [rsp+328h+var_208], rax
0x140149589  mov     rax, [rsp+328h+arg_60]
0x140149591  mov     qword ptr [rsp+328h+var_258.left], rax
0x140149599  lea     rcx, [rsp+328h+var_298]
0x1401495a1  call    ??0?$SmartObjStackRef@UtagCLS@@@@QEAA@XZ; SmartObjStackRef<tagCLS>::SmartObjStackRef<tagCLS>(void)
0x1401495a6  xorps   xmm0, xmm0
0x1401495a9  movups  [rsp+328h+var_50], xmm0
0x1401495b1  xorps   xmm1, xmm1
0x1401495b4  movups  [rsp+328h+var_60], xmm1
0x1401495bc  xor     edx, edx; Val
0x1401495be  lea     r8d, [rdx+70h]; Size
0x1401495c2  lea     rcx, [rsp+328h+var_158]; void *
0x1401495ca  call    memset_0
0x1401495cf  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401495d4  mov     r15, rax
0x1401495d7  mov     [rsp+328h+var_2A8], rax
0x1401495df  lea     rcx, [rsp+328h+var_200]
0x1401495e7  call    ??0?$Win32HMOptionalThreadLockAlways@UtagMENU@@@@QEAA@XZ; Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(void)
0x1401495ec  xorps   xmm0, xmm0
0x1401495ef  xor     eax, eax
0x1401495f1  movups  [rsp+328h+var_A8], xmm0
0x1401495f9  mov     [rsp+328h+var_98], rax
0x140149601  lea     rsi, [r15+1C8h]
0x140149608  mov     [rsp+328h+var_288], rsi
0x140149610  mov     rax, [rsi]
0x140149613  mov     r14d, [rax+0Ch]
0x140149617  movups  [rsp+328h+var_1A8], xmm0
0x14014961f  mov     rdx, rbx
0x140149622  lea     rcx, [rsp+328h+var_240]
0x14014962a  call    ??0?$SmartObjStackRef@UtagMENU@@@@QEAA@AEBV0@@Z; SmartObjStackRef<tagMENU>::SmartObjStackRef<tagMENU>(SmartObjStackRef<tagMENU> const &)
0x14014962f  lea     rcx, [rsp+328h+var_1E0]; this
0x140149637  call    ??0AtomicExecutionCheck@@QEAA@XZ; AtomicExecutionCheck::AtomicExecutionCheck(void)
0x14014963c  mov     rax, [rsi]
0x14014963f  test    dword ptr [rax+0Ch], 10000000h
0x140149646  jnz     short loc_140149699
0x140149648  call    RegisterIconTitleClass
0x14014964d  xor     esi, esi
0x14014964f  test    eax, eax
0x140149651  jnz     short loc_14014969B
0x140149653  mov     ecx, 57h ; 'W'
0x140149658  call    UserSetLastError
0x14014965d  lea     rcx, [rsp+328h+var_1E0]; this
0x140149665  call    ?Disarm@AtomicExecutionCheck@@QEAAXXZ; AtomicExecutionCheck::Disarm(void)
0x14014966a  lea     rcx, [rsp+328h+var_240]
0x140149672  call    ??1?$SmartObjStackRef@UtagMENU@@@@QEAA@XZ; SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(void)
0x140149677  lea     rcx, [rsp+328h+var_200]; BugCheckParameter3
0x14014967f  call    ??1?$Win32HMOptionalThreadLock@UtagHOOK@@@@QEAA@XZ; Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>(void)
0x140149684  lea     rcx, [rsp+328h+var_298]
0x14014968c  call    ??1?$SmartObjStackRef@UtagPOPUPMENU@@@@QEAA@XZ; SmartObjStackRef<tagPOPUPMENU>::~SmartObjStackRef<tagPOPUPMENU>(void)
0x140149691  xor     eax, eax
0x140149693  jmp     loc_14014C8E8
0x140149699  xor     esi, esi
0x14014969b  mov     eax, edi
0x14014969d  test    edi, edi
0x14014969f  jns     short loc_1401496B0
0x1401496a1  btr     edi, 1Fh
0x1401496a5  mov     [rsp+328h+var_2D8], edi
0x1401496a9  mov     [rsp+328h+var_270], edi
0x1401496b0  mov     ecx, 320h
0x1401496b5  test    eax, eax
0x1401496b7  cmovns  cx, si
0x1401496bb  mov     [rsp+328h+var_2B8], ecx
0x1401496bf  mov     word ptr [rsp+328h+var_2D4], cx
0x1401496c4  mov     rbx, [r15+1E8h]
0x1401496cb  mov     [rsp+328h+var_1C8], rbx
0x1401496d3  mov     [rsp+328h+var_1B8], rbx
0x1401496db  test    r13, r13
0x1401496de  jz      short loc_1401496EA
0x1401496e0  cmp     [r13+18h], rbx
0x1401496e4  jnz     loc_140149653
0x1401496ea  mov     r12d, esi
0x1401496ed  mov     [rsp+328h+var_2B4], esi
0x1401496f1  mov     r15d, 1
0x1401496f7  mov     edi, dword ptr [rsp+328h+arg_78]
0x1401496fe  test    r15b, dil
0x140149701  jz      short loc_14014972A
0x140149703  mov     rcx, [rsp+328h+var_288]
0x14014970b  mov     rcx, [rcx]
0x14014970e  call    cs:__imp_IsDesktopApp
0x140149715  nop     dword ptr [rax+rax+00h]
0x14014971a  test    eax, eax
0x14014971c  jnz     loc_1401498CB
0x140149722  mov     r12d, r15d
0x140149725  mov     [rsp+328h+var_2B4], r15d
0x14014972a  mov     eax, edi
0x14014972c  and     eax, 2
0x14014972f  mov     [rsp+328h+var_244], eax
0x140149736  jz      short loc_140149757
0x140149738  mov     rax, [rsp+328h+var_288]
0x140149740  mov     rcx, [rax]
0x140149743  call    cs:__imp_IsImmersiveBroker
0x14014974a  nop     dword ptr [rax+rax+00h]
0x14014974f  test    eax, eax
0x140149751  jz      loc_1401498CB
0x140149757  mov     edi, [rsp+328h+arg_68]
0x14014975e  test    edi, edi
0x140149760  jz      short loc_1401497B5
0x140149762  mov     ecx, edi
0x140149764  call    IsValidBand
0x140149769  test    eax, eax
0x14014976b  jz      loc_140149653
0x140149771  cmp     edi, 0Fh
0x140149774  jz      loc_140149653
0x14014977a  mov     r8, [rsp+328h+var_288]
0x140149782  mov     rax, [r8]
0x140149785  mov     rcx, [rax+328h]
0x14014978c  mov     al, cl
0x14014978e  and     al, 30h
0x140149790  cmp     al, 10h
0x140149792  jnz     short loc_1401497BD
0x140149794  bt      rcx, 9
0x140149799  jb      short loc_1401497BD
0x14014979b  cmp     edi, r15d
0x14014979e  jnz     short loc_1401497BD
0x1401497a0  test    r12d, r12d
0x1401497a3  jnz     short loc_1401497BD
0x1401497a5  mov     rcx, r13
0x1401497a8  call    HasMessageRootWindow
0x1401497ad  test    eax, eax
0x1401497af  jz      loc_140149653
0x1401497b5  mov     r8, [rsp+328h+var_288]
0x1401497bd  mov     ecx, [rsp+328h+arg_20]
0x1401497c4  shr     ecx, 10h
0x1401497c7  mov     eax, 0C000h
0x1401497cc  and     cx, ax
0x1401497cf  mov     [rsp+328h+var_2CC], ecx
0x1401497d3  mov     word ptr [rsp+328h+var_2D4+4], cx
0x1401497d8  mov     edx, 4000h
0x1401497dd  mov     eax, esi
0x1401497df  cmp     cx, dx
0x1401497e2  setz    al
0x1401497e5  mov     [rsp+328h+var_16C], eax
0x1401497ec  jz      short loc_140149813
0x1401497ee  mov     rdx, r13
0x1401497f1  mov     rcx, [r8]
0x1401497f4  call    cs:__imp_ShouldSetNoOwner
0x1401497fb  nop     dword ptr [rax+rax+00h]
0x140149800  test    eax, eax
0x140149802  cmovnz  r13, rsi
0x140149806  mov     [rsp+328h+var_2B0], r13
0x14014980b  mov     [rsp+328h+var_210], r13
0x140149813  test    r13, r13
0x140149816  jz      short loc_140149858
0x140149818  mov     rcx, r13
0x14014981b  call    IsDesktopWindow
0x140149820  test    eax, eax
0x140149822  jnz     short loc_140149858
0x140149824  mov     rcx, [r13+28h]
0x140149828  mov     eax, [rcx+0ECh]
0x14014982e  test    edi, edi
0x140149830  jnz     short loc_14014983D
0x140149832  mov     edi, eax
0x140149834  mov     [rsp+328h+arg_68], eax
0x14014983b  jmp     short loc_140149845
0x14014983d  cmp     edi, eax
0x14014983f  jnz     loc_140149653
0x140149845  movzx   r12d, byte ptr [rcx+0E8h]
0x14014984d  and     r12d, 40h
0x140149851  mov     [rsp+328h+var_2B4], r12d
0x140149856  jmp     short loc_1401498B2
0x140149858  test    edi, edi
0x14014985a  jnz     short loc_1401498B2
0x14014985c  mov     rax, [rsp+328h+var_288]
0x140149864  mov     rcx, [rax]
0x140149867  call    IsImmersiveAppIORestricted
0x14014986c  test    eax, eax
0x14014986e  jz      short loc_140149886
0x140149870  mov     r12d, r15d
0x140149873  mov     [rsp+328h+var_2B4], r15d
0x140149878  mov     edi, 0Fh
0x14014987d  mov     [rsp+328h+arg_68], edi
0x140149884  jmp     short loc_1401498B2
0x140149886  mov     al, [rcx+328h]
0x14014988c  mov     ecx, 2
0x140149891  test    cl, al
0x140149893  jz      short loc_1401498A7
0x140149895  test    byte ptr [rsp+328h+var_2D8], 8
0x14014989a  jz      short loc_1401498A7
0x14014989c  mov     edi, ecx
0x14014989e  mov     [rsp+328h+arg_68], ecx
0x1401498a5  jmp     short loc_1401498B2
0x1401498a7  mov     edi, r15d
0x1401498aa  mov     [rsp+328h+arg_68], r15d
0x1401498b2  mov     r8, r13
0x1401498b5  mov     edx, edi
0x1401498b7  mov     rax, [rsp+328h+var_288]
0x1401498bf  mov     rcx, [rax]
0x1401498c2  call    ?IsValidBandForProcess@@YA_NPEBUtagPROCESSINFO@@W4ZBID@@PEAUtagWND@@@Z; IsValidBandForProcess(tagPROCESSINFO const *,ZBID,tagWND *)
0x1401498c7  test    al, al
0x1401498c9  jnz     short loc_1401498D5
0x1401498cb  mov     ecx, 5
0x1401498d0  jmp     loc_140149658
0x1401498d5  mov     r8d, 400000h
0x1401498db  mov     edx, [rsp+328h+var_2D8]
0x1401498df  test    r8d, edx
0x1401498e2  jnz     loc_14014996D
0x1401498e8  test    r13, r13
0x1401498eb  jz      short loc_14014990D
0x1401498ed  mov     eax, 4000h
0x1401498f2  cmp     word ptr [rsp+328h+var_2CC], ax
0x1401498f7  jnz     short loc_14014996D
0x1401498f9  mov     rax, [r13+28h]
0x1401498fd  mov     cl, [rax+1Ah]
0x140149900  and     cl, 50h
0x140149903  cmp     cl, 40h ; '@'
0x140149906  jnz     short loc_14014996D
0x140149908  or      edx, r8d
0x14014990b  jmp     short loc_140149962
0x14014990d  mov     rax, [rsp+328h+Str1]
0x140149915  test    rax, 0FFFFFFFFFFFF0000h
0x14014991b  jnz     short loc_14014992F
0x14014991d  mov     rax, [rsp+328h+Str1]
0x140149925  mov     ecx, 8002h
0x14014992a  cmp     ax, cx
0x14014992d  jz      short loc_14014996D
0x14014992f  call    cs:__imp_PsGetCurrentProcessWin32Process
0x140149936  nop     dword ptr [rax+rax+00h]
0x14014993b  mov     rdx, rax
0x14014993e  test    rax, rax
0x140149941  jz      short loc_14014994F
0x140149943  mov     rax, [rax]
0x140149946  neg     rax
0x140149949  sbb     rcx, rcx
0x14014994c  and     rdx, rcx
0x14014994f  mov     eax, [rdx+330h]
0x140149955  mov     edx, [rsp+328h+var_2D8]
0x140149959  test    r15b, al
0x14014995c  jz      short loc_14014996D
0x14014995e  bts     edx, 16h
0x140149962  mov     [rsp+328h+var_270], edx
0x140149969  mov     [rsp+328h+var_2D8], edx
0x14014996d  mov     eax, edx
0x14014996f  mov     ecx, 2200000h
0x140149974  and     eax, ecx
0x140149976  cmp     eax, ecx
0x140149978  jz      loc_140149653
0x14014997e  mov     rax, [rsp+328h+var_2A8]
0x140149986  cmp     [rax+270h], rsi
0x14014998d  jz      short loc_1401499A7
0x14014998f  mov     edx, 2
0x140149994  mov     ecx, [rax+3A0h]
0x14014999a  call    CheckGrantedAccess
0x14014999f  test    eax, eax
0x1401499a1  jz      loc_14014965D
0x1401499a7  mov     eax, 4000h
0x1401499ac  cmp     word ptr [rsp+328h+var_2CC], ax
0x1401499b1  jnz     short loc_1401499D4
0x1401499b3  test    r13, r13
0x1401499b6  jnz     short loc_1401499C2
0x1401499b8  mov     ecx, 57Eh
0x1401499bd  jmp     loc_140149658
0x1401499c2  mov     rdx, r13
0x1401499c5  xor     ecx, ecx
0x1401499c7  call    ValidateParentDepth
0x1401499cc  test    eax, eax
0x1401499ce  jz      loc_140149653
0x1401499d4  and     r14d, 2000h
0x1401499db  mov     [rsp+328h+var_29C], r14d
0x1401499e3  mov     [rsp+328h+var_1F0], r13
0x1401499eb  mov     r14d, 400h
0x1401499f1  mov     rax, [rsp+328h+var_1E8]
0x1401499f9  test    rax, 0FFFFFFFFFFFF0000h
0x1401499ff  jz      loc_140149B48
0x140149a05  lea     rcx, [rsp+328h+var_228]; this
0x140149a0d  call    ??0AtomicExecutionCheck@@QEAA@XZ; AtomicExecutionCheck::AtomicExecutionCheck(void)
0x140149a12  nop
0x140149a13  call    cs:__imp_W32GetUserSessionState
0x140149a1a  nop     dword ptr [rax+rax+00h]
0x140149a1f  lea     r10, [rax+0A254h]
0x140149a26  mov     r8, [rsp+328h+var_1E8]
0x140149a2e  mov     r8, [r8+8]; unsigned __int16 *
0x140149a32  mov     edx, 100h; unsigned __int64
0x140149a37  mov     rcx, r10; unsigned __int16 *
  ... truncated ...
```
