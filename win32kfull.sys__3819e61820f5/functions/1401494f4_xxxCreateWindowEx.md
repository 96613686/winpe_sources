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
  __int64 v54; // rcx
  struct tagWND *v55; // rbx
  struct tagTHREADINFO *v56; // rax
  __int64 v57; // rax
  __int64 v58; // r8
  __int64 v59; // rcx
  int v60; // ebx
  __int64 v61; // rdx
  int v62; // ecx
  wchar_t *v63; // rcx
  unsigned int CurrentThreadDpiAwarenessContext; // eax
  __int64 v65; // rdx
  __int64 v66; // r8
  __int64 v67; // r9
  __int64 v68; // rax
  __int64 v69; // rdx
  __int64 v70; // rdx
  __int64 v71; // r8
  __int64 v72; // r9
  __int16 v73; // bx
  __int64 v74; // rdx
  __int64 *v75; // rax
  __int64 v76; // rcx
  __int64 v77; // rdi
  __int64 v78; // r8
  __int64 v79; // r13
  int v80; // eax
  LONG v81; // r9d
  int v82; // r10d
  struct _HEAD *v83; // rax
  LONG v84; // edx
  LONG v85; // eax
  LONG v86; // ecx
  int v87; // edx
  unsigned int v88; // eax
  struct tagMONITOR *InheritedMonitor; // rbx
  _DWORD *v90; // rax
  __int64 MessageWindow; // rax
  const struct tagWND *ThreadDesktopWindow; // rdx
  __int64 v93; // r9
  __int64 v94; // rdx
  __int64 v95; // rcx
  __int64 v96; // r8
  char v97; // r12
  __int64 v98; // rax
  int v99; // r13d
  __int64 v100; // rax
  char v101; // r12
  Scrollbar::NonClient *v102; // rcx
  Scrollbar::NonClient *v103; // rcx
  bool v104; // al
  __int64 v105; // rdx
  int v106; // r8d
  unsigned int v107; // ecx
  unsigned int ClientExtraBytesTotalSize; // eax
  __int64 v109; // rdi
  _QWORD *v110; // rdx
  __int64 v111; // rcx
  int v112; // ebx
  __int64 v113; // r8
  __int64 v114; // r9
  __int64 v115; // rcx
  __int64 v116; // rdx
  __int64 v117; // rdx
  __int64 v118; // r8
  __int64 v119; // r9
  __int64 v120; // rdx
  __int64 v121; // rcx
  __int64 v122; // r8
  __int64 v123; // r9
  __int16 v124; // di
  __int64 v125; // rdx
  __int64 v126; // rcx
  __int64 v127; // r8
  __int64 v128; // r9
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
  __int64 v141; // rdx
  __int64 v142; // rcx
  __int64 v143; // r8
  __int64 v144; // r9
  __int64 v145; // rdx
  __int64 v146; // rcx
  __int64 v147; // r8
  __int64 v148; // r9
  __int64 v149; // rdx
  __int64 v150; // rcx
  __int64 v151; // r8
  __int64 v152; // r9
  __int16 v153; // bx
  unsigned __int16 v154; // bx
  char v155; // di
  int v156; // eax
  __int64 v157; // rcx
  int v158; // edx
  int v159; // r12d
  int v160; // edi
  unsigned int v161; // ecx
  __int64 v162; // rdx
  __int64 v163; // r8
  __int64 v164; // r9
  int v165; // r8d
  int v166; // r9d
  __int64 v167; // rbx
  __int16 v168; // di
  __int64 v169; // rdx
  int v170; // eax
  __int64 v171; // r8
  __int64 v172; // rcx
  struct tagMONITOR *v173; // rax
  unsigned int v174; // edx
  int v175; // ecx
  __int16 v176; // ax
  _QWORD *v177; // r8
  unsigned int v178; // eax
  int *MonitorRect; // rax
  int v180; // r8d
  int v181; // r9d
  int v182; // r10d
  int v183; // eax
  __int64 v184; // rbx
  __int64 v185; // r8
  __int64 v186; // rcx
  __int64 v187; // rax
  unsigned int WindowCloakStateComponentUIAware; // r12d
  struct _HEAD *v189; // rcx
  struct _HEAD *v190; // rcx
  __int64 v191; // rcx
  __int64 NonChildAncestor; // rbx
  __int64 v193; // rdi
  __int64 v194; // rdx
  __int64 v195; // rcx
  __int64 v196; // r8
  __int64 v197; // r9
  __int64 v198; // rcx
  struct tagTHREADINFO *v199; // rdx
  int IsEnabledDeviceUsageNoInline; // eax
  int v201; // ecx
  bool v202; // zf
  unsigned int v203; // eax
  int v204; // edx
  struct tagTHREADINFO *v205; // rdi
  __int64 KernelEvent; // rax
  __int64 v207; // rdi
  struct tagWND **v208; // r13
  __int64 v209; // rdx
  __int64 v210; // rbx
  NTSTATUS v211; // eax
  ULONG v212; // eax
  __int64 v213; // rdx
  __int64 v214; // r8
  struct tagWND *v215; // r9
  __int64 v216; // rcx
  struct tagTHREADINFO **v217; // rax
  __int64 v218; // rax
  __int64 v219; // rax
  int v220; // eax
  int v221; // eax
  __int64 v222; // rax
  struct tagMONITOR *v223; // rbx
  __int64 v224; // rcx
  __int64 *v225; // rbx
  __int64 StyleWindow; // rbx
  unsigned int v227; // edx
  __int64 v228; // rdx
  __int64 v229; // r8
  __int64 v230; // r9
  int v231; // ebx
  __int64 v232; // r9
  struct tagTHREADINFO *v233; // rdx
  unsigned __int128 v234; // rax
  unsigned int v235; // ecx
  __int64 v236; // rcx
  __int64 SystemMenu; // rax
  struct _LARGE_UNICODE_STRING *StrName; // rax
  struct tagWND **v239; // rbx
  struct tagWND *DefaultImeWindow; // rax
  int v241; // ecx
  struct tagWND *v242; // rcx
  unsigned __int64 CompositeAppFrameWindowOrSelf; // rbx
  __int64 v244; // rax
  int v245; // ebx
  __int64 v246; // r8
  __int64 v247; // r9
  __int64 v248; // rcx
  struct tagWND *v249; // rdx
  const struct tagWND *v250; // rax
  __int64 TopMostInsertAfter; // rax
  __int64 *v252; // rbx
  __int64 v253; // r9
  int v254; // edx
  int v255; // r8d
  __int64 v256; // rdx
  __int64 v257; // rcx
  __int64 v258; // r8
  void *v259; // rax
  __int64 v260; // rdx
  __int64 v261; // rcx
  __int64 v262; // r8
  void *v263; // rax
  __int64 v264; // rdx
  __int64 v265; // rcx
  __int64 v266; // r8
  __int64 v267; // r9
  __int64 v268; // r8
  __int64 v269; // r9
  __int64 DesktopWindow; // rax
  __int64 v271; // rdx
  unsigned int v272; // ebx
  __int64 *v273; // rdi
  char v274; // cl
  __int64 v275; // rdx
  __int64 v276; // rdx
  __int64 v277; // rcx
  __int64 v278; // r8
  __int64 v279; // r9
  __int64 v280; // rax
  _QWORD *v281; // rbx
  __int64 v282; // rax
  __int64 v283; // rbx
  unsigned int v284; // [rsp+50h] [rbp-2D8h]
  unsigned __int64 v285; // [rsp+54h] [rbp-2D4h]
  __int16 v286; // [rsp+5Ch] [rbp-2CCh]
  int v287; // [rsp+5Ch] [rbp-2CCh]
  __int64 v288; // [rsp+68h] [rbp-2C0h]
  unsigned __int16 v289; // [rsp+70h] [rbp-2B8h]
  int v290; // [rsp+70h] [rbp-2B8h]
  unsigned int v291; // [rsp+74h] [rbp-2B4h]
  struct tagWND *v292; // [rsp+78h] [rbp-2B0h]
  int v293; // [rsp+8Ch] [rbp-29Ch]
  int v294; // [rsp+8Ch] [rbp-29Ch]
  _QWORD v295[2]; // [rsp+90h] [rbp-298h] BYREF
  _QWORD *v296; // [rsp+A0h] [rbp-288h]
  wchar_t *Str1; // [rsp+A8h] [rbp-280h]
  int *v298; // [rsp+B0h] [rbp-278h]
  int v299; // [rsp+B8h] [rbp-270h]
  int Atom; // [rsp+C0h] [rbp-268h]
  int v301; // [rsp+C4h] [rbp-264h]
  __int64 *v302; // [rsp+C8h] [rbp-260h]
  struct tagRECT v303; // [rsp+D0h] [rbp-258h] BYREF
  int v304; // [rsp+E0h] [rbp-248h]
  int v305; // [rsp+E4h] [rbp-244h]
  _QWORD v306[2]; // [rsp+E8h] [rbp-240h] BYREF
  struct _HEAD *v307; // [rsp+F8h] [rbp-230h]
  ULONG_PTR v308[2]; // [rsp+100h] [rbp-228h] BYREF
  unsigned __int16 v309; // [rsp+110h] [rbp-218h]
  __int64 v310; // [rsp+118h] [rbp-210h]
  void *v311; // [rsp+120h] [rbp-208h]
  ULONG_PTR v312[2]; // [rsp+128h] [rbp-200h] BYREF
  __int64 v313; // [rsp+138h] [rbp-1F0h]
  __int64 v314; // [rsp+140h] [rbp-1E8h]
  __int64 v315; // [rsp+148h] [rbp-1E0h] BYREF
  __int64 v316; // [rsp+150h] [rbp-1D8h]
  struct tagWND *v317; // [rsp+158h] [rbp-1D0h]
  _QWORD *v318; // [rsp+160h] [rbp-1C8h]
  ULONG_PTR v319[2]; // [rsp+170h] [rbp-1B8h] BYREF
  __int128 v320; // [rsp+180h] [rbp-1A8h] BYREF
  int v321; // [rsp+190h] [rbp-198h]
  int v322; // [rsp+1BCh] [rbp-16Ch]
  _QWORD v323[2]; // [rsp+1D0h] [rbp-158h] BYREF
  struct _HEAD *v324; // [rsp+1E0h] [rbp-148h]
  __int64 v325; // [rsp+1E8h] [rbp-140h]
  unsigned int v326; // [rsp+1F0h] [rbp-138h]
  int v327; // [rsp+1F4h] [rbp-134h]
  LONG v328; // [rsp+1F8h] [rbp-130h]
  unsigned int v329; // [rsp+1FCh] [rbp-12Ch]
  unsigned int v330; // [rsp+200h] [rbp-128h]
  __int64 v331; // [rsp+208h] [rbp-120h]
  wchar_t *v332; // [rsp+210h] [rbp-118h]
  unsigned int v333; // [rsp+218h] [rbp-110h]
  int v334; // [rsp+220h] [rbp-108h]
  int v335; // [rsp+224h] [rbp-104h]
  __int64 v336; // [rsp+228h] [rbp-100h]
  __int128 v337; // [rsp+230h] [rbp-F8h] BYREF
  wchar_t *v338; // [rsp+240h] [rbp-E8h]
  struct tagTHREADINFO **v339; // [rsp+248h] [rbp-E0h]
  _QWORD *v340; // [rsp+250h] [rbp-D8h]
  ULONG_PTR BugCheckParameter3[2]; // [rsp+258h] [rbp-D0h] BYREF
  int v342; // [rsp+268h] [rbp-C0h]
  int *v343; // [rsp+270h] [rbp-B8h] BYREF
  __int128 v344; // [rsp+280h] [rbp-A8h] BYREF
  __int64 v345; // [rsp+290h] [rbp-98h]
  _BYTE v346[40]; // [rsp+2A0h] [rbp-88h] BYREF
  __int128 v347; // [rsp+2C8h] [rbp-60h] BYREF
  __int128 v348; // [rsp+2D8h] [rbp-50h] BYREF

  v343 = a4;
  v338 = a2;
  v304 = a1;
  v284 = a1;
  v299 = a1;
  Str1 = a2;
  v314 = a3;
  v298 = a4;
  v18 = (__int64)a10;
  v292 = a10;
  v310 = (__int64)a10;
  v311 = a12;
  *(_QWORD *)&v303.left = a13;
  SmartObjStackRef<tagCLS>::SmartObjStackRef<tagCLS>(v295);
  v348 = 0;
  v347 = 0;
  memset_0(v323, 0, 0x70u);
  v19 = PtiCurrent();
  Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(v312);
  v344 = 0;
  v345 = 0;
  v296 = (_QWORD *)((char *)v19 + 456);
  v20 = *(_DWORD *)(*((_QWORD *)v19 + 57) + 12LL);
  v320 = 0;
  SmartObjStackRef<tagMENU>::SmartObjStackRef<tagMENU>(v306, a11);
  AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)&v315);
  if ( (*(_DWORD *)(*((_QWORD *)v19 + 57) + 12LL) & 0x10000000) == 0 && !(unsigned int)RegisterIconTitleClass() )
    goto LABEL_3;
  if ( a1 < 0 )
  {
    v284 = a1 & 0x7FFFFFFF;
    v299 = a1 & 0x7FFFFFFF;
  }
  v23 = 800;
  if ( a1 >= 0 )
    v23 = 0;
  v289 = v23;
  v24 = *((_QWORD *)v19 + 61);
  v318 = (_QWORD *)v24;
  v319[0] = v24;
  if ( a10 )
  {
    if ( *((_QWORD *)a10 + 3) != v24 )
      goto LABEL_3;
  }
  v25 = 0;
  if ( (a16 & 1) != 0 )
  {
    if ( (unsigned int)IsDesktopApp(*v296) )
    {
LABEL_45:
      v21 = 5;
      goto LABEL_4;
    }
    v25 = 1;
  }
  v305 = a16 & 2;
  if ( (a16 & 2) != 0 && !(unsigned int)IsImmersiveBroker(*v296) )
    goto LABEL_45;
  v26 = a14;
  if ( !a14 )
  {
LABEL_26:
    v27 = v296;
    goto LABEL_27;
  }
  if ( !(unsigned int)IsValidBand(a14) || a14 == 15 )
    goto LABEL_3;
  v27 = v296;
  v28 = *(_QWORD *)(*v296 + 808LL);
  if ( (v28 & 0x30) == 0x10 && (v28 & 0x200) == 0 && a14 == 1 && !v25 )
  {
    if ( !(unsigned int)HasMessageRootWindow(a10) )
      goto LABEL_3;
    goto LABEL_26;
  }
LABEL_27:
  v286 = HIWORD(a5) & 0xC000;
  v322 = (HIWORD(a5) & 0xC000) == 0x4000;
  if ( (HIWORD(a5) & 0xC000) != 0x4000 )
  {
    if ( (unsigned int)ShouldSetNoOwner(*v27, a10) )
      v18 = 0;
    v292 = (struct tagWND *)v18;
    v310 = v18;
  }
  if ( !v18 || (unsigned int)IsDesktopWindow(v18) )
  {
    if ( !a14 )
    {
      if ( (unsigned int)IsImmersiveAppIORestricted(*v296) )
      {
        v25 = 1;
        v26 = 15;
      }
      else if ( (*(_BYTE *)(v30 + 808) & 2) != 0 && (v284 & 8) != 0 )
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
  if ( !(unsigned __int8)IsValidBandForProcess(*v296, v26, v18) )
    goto LABEL_45;
  v33 = v284;
  if ( (v284 & 0x400000) == 0 )
  {
    if ( v18 )
    {
      if ( v286 != 0x4000 || (*(_BYTE *)(*(_QWORD *)(v18 + 40) + 26LL) & 0x50) != 0x40 )
        goto LABEL_58;
      v33 = v284 | 0x400000;
    }
    else
    {
      if ( ((unsigned __int64)Str1 & 0xFFFFFFFFFFFF0000uLL) == 0 )
      {
        v31 = 32770;
        if ( (_WORD)Str1 == 0x8002 )
          goto LABEL_58;
      }
      CurrentProcessWin32Process = PsGetCurrentProcessWin32Process(v31, v284, 0x400000, v32);
      v35 = CurrentProcessWin32Process;
      if ( CurrentProcessWin32Process )
        v35 = -(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0) & CurrentProcessWin32Process;
      v36 = *(_DWORD *)(v35 + 816);
      v33 = v284;
      if ( (v36 & 1) == 0 )
        goto LABEL_58;
      v33 = v284 | 0x400000;
    }
    v299 = v33;
    v284 = v33;
  }
LABEL_58:
  if ( (v33 & 0x2200000) == 0x2200000 )
    goto LABEL_3;
  if ( *((_QWORD *)v19 + 78) && !(unsigned int)CheckGrantedAccess(*((unsigned int *)v19 + 232), 2) )
    goto LABEL_5;
  if ( v286 == 0x4000 )
  {
    if ( !v18 )
    {
      v21 = 1406;
LABEL_4:
      UserSetLastError(v21);
LABEL_5:
      AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)&v315);
LABEL_6:
      SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(v306);
      Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)v312);
      SmartObjStackRef<tagPOPUPMENU>::~SmartObjStackRef<tagPOPUPMENU>(v295);
      return 0;
    }
    if ( !(unsigned int)ValidateParentDepth(0, v18) )
    {
LABEL_3:
      v21 = 87;
      goto LABEL_4;
    }
  }
  v293 = v20 & 0x2000;
  v313 = v18;
  while ( 1 )
  {
    if ( (v314 & 0xFFFFFFFFFFFF0000uLL) != 0 )
    {
      AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)v308);
      UserSessionState = W32GetUserSessionState(v38, v37, v39, v40);
      if ( (int)RtlStringCchCopyW(
                  (unsigned __int16 *)(UserSessionState + 41556),
                  0x100u,
                  *(const unsigned __int16 **)(v314 + 8)) < 0 )
      {
        Atom = 0;
        v293 = 1;
        v321 = 1;
      }
      else
      {
        Atom = (unsigned __int16)UserFindAtom(v42);
      }
      AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v308);
    }
    else
    {
      v43 = v314;
      Atom = v314;
    }
    if ( v43 )
    {
      ClassPtr = (_QWORD *)GetClassPtr(v43, *v296, v311);
      if ( ClassPtr )
        break;
    }
LABEL_107:
    if ( v293
      || (*(_DWORD *)(*((_QWORD *)PtiCurrent() + 57) + 12LL) & 0x2000) != 0
      || (((unsigned __int64)Str1 & 0xFFFFFFFFFFFF0000uLL) == 0
        ? (v63 = Str1)
        : (v63 = (wchar_t *)*((_QWORD *)Str1 + 1)),
          !(unsigned int)RegisterDefaultClass(v63)) )
    {
      v21 = 1407;
      goto LABEL_4;
    }
    v293 = 1;
    v24 = (ULONG_PTR)v318;
  }
  SmartObjStackRefBase<tagCLS>::operator=(v295, *ClassPtr);
  if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)v295[0] + 8LL) + 6LL) & 1) != 0 && (unsigned int)PsGetWin32KFilterSet() == 5 )
    goto LABEL_5;
  v309 = a15;
  if ( (unsigned int)NeedsWindowEdge(a5, v284, a15 >= 0x400u) )
    v47 = v46 | 0x100;
  else
    v47 = v46 & 0xFFFFFEFF;
  v299 = v47;
  v284 = v47;
  if ( (_InterlockedCompareExchange((volatile signed __int32 *)v19 + 130, 0, 0) & 1) != 0 )
  {
    v301 = 0x20000;
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 853);
  }
  LOBYTE(v45) = 1;
  v48 = HMAllocObject(v19, v24, v45);
  v49 = v48;
  v317 = (struct tagWND *)v48;
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
  v288 = v49 + 40;
  *(_DWORD *)(*(_QWORD *)(v49 + 40) + 328LL) = (unsigned int)PsGetThreadId(*(PETHREAD *)v19);
  *(_DWORD *)(*(_QWORD *)(v49 + 40) + 332LL) = *(_DWORD *)(*v296 + 56LL);
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
  v339 = (struct tagTHREADINFO **)(v49 + 16);
  if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v49 + 16) + 456LL) + 808LL) & 0x1000000) != 0 )
    *(_DWORD *)(v49 + 384) |= 1u;
  *(_QWORD *)(*(_QWORD *)v51 + 296LL) = 0;
  *(_QWORD *)(v49 + 280) = 0;
  *(_DWORD *)(v49 + 180) = -1;
  *(_QWORD *)(*(_QWORD *)v51 + 168LL) = 0;
  CurrentThreadDpiHostingBehavior = W32GetCurrentThreadDpiHostingBehavior();
  v54 = CurrentThreadDpiHostingBehavior;
  *(_DWORD *)(*(_QWORD *)v51 + 292LL) = CurrentThreadDpiHostingBehavior;
  if ( v286 == 0x4000 )
  {
    if ( v292 && v292 != (struct tagWND *)GetThreadDesktopWindow(0) )
    {
      v55 = 0;
      v56 = PtiCurrent();
      if ( v56 )
      {
        v57 = *((_QWORD *)v56 + 61);
        if ( v57 )
          v55 = *(struct tagWND **)(v57 + 112);
      }
      if ( v292 != v55 )
      {
        v54 = *(_QWORD *)(*((_QWORD *)v292 + 2) + 456LL);
        if ( *v296 == v54 && !IsChildWindowDpiIsolationEnabled(0, v292) )
        {
          v58 = v313;
          v59 = *(_QWORD *)v288;
          *(_DWORD *)(v59 + 288) = *(_DWORD *)(*(_QWORD *)(v313 + 40) + 288LL);
          v60 = *(_DWORD *)(*(_QWORD *)(v58 + 40) + 288LL);
          if ( (((unsigned __int8)v60 ^ (unsigned __int8)W32GetCurrentThreadDpiAwarenessContext(v59)) & 0xF) != 0 )
            TraceChildWindowDpiTelemetry(v49, v292, 0);
          v51 = v49 + 40;
          goto LABEL_100;
        }
      }
    }
    v51 = v49 + 40;
  }
  CurrentThreadDpiAwarenessContext = W32GetCurrentThreadDpiAwarenessContext(v54);
  *(_DWORD *)(*(_QWORD *)v51 + 288LL) = CurrentThreadDpiAwarenessContext;
  if ( (*(_DWORD *)(*(_QWORD *)v51 + 288LL) & 0x4000000F) == 0 )
  {
    v68 = PsGetCurrentProcessWin32Process(CurrentThreadDpiAwarenessContext, v65, v66, v67);
    v69 = v68;
    if ( v68 )
      v69 = -(__int64)(*(_QWORD *)v68 != 0) & v68;
    if ( (*(_DWORD *)(v69 + 12) & 0x20000000) != 0 )
      *(_DWORD *)(*(_QWORD *)v51 + 288LL) |= 0x40000000u;
  }
LABEL_100:
  v61 = *(_QWORD *)v51;
  v62 = *(_DWORD *)(*(_QWORD *)v51 + 288LL);
  if ( (v62 & 0xF) == 2 && (v62 & 0xF0) == 0x20 )
    *(_DWORD *)(v49 + 380) |= 0x180000u;
  if ( (*(_BYTE *)(v61 + 288) & 0xF) == 3 )
    *(_DWORD *)(v49 + 380) |= 0x80000u;
  v340 = (_QWORD *)(v49 + 136);
  tagWND::SharedMixedObjectPointerFieldpcls<tagCLS>::operator=(v49 + 136, *(_QWORD *)v295[0]);
  *(_DWORD *)(*(_QWORD *)v51 + 28LL) = a5 & 0xEFFFFFFF;
  *(_DWORD *)(*(_QWORD *)v51 + 24LL) = v284 & 0xFDF7FFFF;
  *(_DWORD *)(*(_QWORD *)v51 + 200LL) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v295[0] + 8LL) + 80LL);
  *(_DWORD *)(*(_QWORD *)v51 + 248LL) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v295[0] + 8LL) + 84LL);
  if ( !(unsigned int)ReferenceClass(*(_QWORD *)v295[0], v49) )
    goto LABEL_106;
  v302 = (__int64 *)v51;
  SmartObjStackRefBase<tagCLS>::operator=(v295, *v340);
  if ( !(unsigned int)ClassLock(*(_QWORD *)v295[0], &v344) )
  {
    DereferenceClass(*v296, v49);
LABEL_106:
    tagObjLock::LockUnInitializeThreadCreator(*(tagObjLock **)(v49 + 144));
    Win32FreePool(*(void **)(v49 + 144));
    tagObjLock::LockUnInitializeThreadCreator(v50);
    HMFreeObject(v49);
    goto LABEL_107;
  }
  v294 = 0;
  *(_QWORD *)(*(_QWORD *)v51 + 224LL) = a17;
  v73 = *(_WORD *)(*(_QWORD *)(*(_QWORD *)v295[0] + 8LL) + 2LL);
  if ( v73 == *(_WORD *)(*(_QWORD *)(W32GetUserSessionState(*(_QWORD *)v295[0], v70, v71, v72) + 19704) + 868LL) )
  {
    v74 = v49 + 40;
    *(_QWORD *)(*(_QWORD *)v288 + 208LL) = 0;
  }
  else
  {
    v75 = (__int64 *)*((_QWORD *)v19 + 103);
    v76 = 0;
    if ( v75 )
      v76 = *v75;
    v74 = v49 + 40;
    *(_QWORD *)(*(_QWORD *)v288 + 208LL) = v76;
  }
  *(_DWORD *)(*(_QWORD *)v74 + 236LL) = v26;
  v77 = v49 + 40;
  v78 = *(_QWORD *)v288;
  v79 = (__int64)v292;
  if ( *(_DWORD *)(*(_QWORD *)v288 + 236LL) == 1 )
    v80 = 0;
  else
    v80 = IsTopLevelParent(v292);
  if ( v80 )
    *(_DWORD *)(v78 + 24) |= 8u;
  if ( v25 )
    SetOrClrWF(1, v49, 55360, 0);
  v319[0] = (ULONG_PTR)v19 + 932;
  ++*((_DWORD *)v19 + 233);
  memset_0(v323, 0, 0x70u);
  v333 = v284;
  v323[1] = v311;
  if ( ((unsigned __int64)Str1 & 0xFFFFFFFFFFFF0000uLL) != 0 )
  {
    if ( v304 >= 0 )
    {
      v332 = (wchar_t *)*((_QWORD *)Str1 + 1);
      v337 = *(_OWORD *)v338;
    }
    else
    {
      v332 = *(wchar_t **)(*(_QWORD *)v295[0] + 104LL);
      if ( ((unsigned __int64)v332 & 0xFFFFFFFFFFFF0000uLL) != 0 )
        RtlInitLargeAnsiString(&v337);
    }
  }
  else
  {
    v332 = Str1;
  }
  if ( v298 )
  {
    v331 = *((_QWORD *)v298 + 1);
    v334 = *v343;
    v335 = v343[1];
    v336 = *((_QWORD *)v343 + 1);
  }
  v330 = a5;
  v81 = a6;
  v285 = __PAIR64__(a7, a6);
  v329 = a6;
  v328 = a7;
  v82 = a8;
  LODWORD(Str1) = a8;
  v327 = a8;
  v291 = a9;
  v326 = a9;
  if ( v292 )
    v325 = *(_QWORD *)v292;
  else
    v325 = 0;
  if ( v286 == 0x4000 )
  {
    v83 = v307;
    if ( !v307 )
      v83 = *(struct _HEAD **)v306[0];
    v324 = v83;
    *(_DWORD *)(*(_QWORD *)v288 + 24LL) |= *(_DWORD *)(*(_QWORD *)(v313 + 40) + 24LL) & 0xC4000000;
    v84 = a7;
  }
  else if ( (unsigned __int8)SmartObjStackRef<tagMENU>::operator==(v306) )
  {
    v324 = 0;
  }
  else
  {
    v324 = **(struct _HEAD ***)v306[0];
  }
  v323[0] = *(_QWORD *)&v303.left;
  *(_QWORD *)&v303.left = 0;
  if ( v81 == 0x80000000 || (v85 = v81, v81 == 0x8000) )
    v85 = 0;
  v303.left = v85;
  if ( v84 == 0x80000000 || v84 == 0x8000 )
  {
    v86 = 0;
    v303.top = 0;
  }
  else
  {
    v86 = v84;
    v303.top = v84;
  }
  if ( v82 == 0x80000000 || (v87 = v82, v82 == 0x8000) )
    v87 = 0;
  v303.right = v87 + v85;
  if ( a9 == 0x80000000 || (v88 = a9, a9 == 0x8000) )
    v88 = 0;
  v303.bottom = v86 + v88;
  InheritedMonitor = (struct tagMONITOR *)GetInheritedMonitor((struct tagWND *)v49);
  if ( InheritedMonitor )
  {
    v301 = 1;
  }
  else
  {
    v301 = 0;
    if ( v292 )
      InheritedMonitor = (struct tagMONITOR *)ValidateHmonitorNoRip(*(_QWORD *)(*(_QWORD *)(v313 + 40) + 256LL));
  }
  if ( !InheritedMonitor )
    InheritedMonitor = (struct tagMONITOR *)MonitorFromRect(&v303, 2);
  UpdateWindowMonitorAndDpiInfoHelper((struct tagWND *)v49, InheritedMonitor);
  *(_WORD *)(*(_QWORD *)v288 + 286LL) = 0;
  *(_QWORD *)(v49 + 296) = 0;
  if ( v286 != 0x4000 || IsDpiBoundaryBetweenWindows((const struct tagWND *)v49, v292) )
    UpdateTopLevelWindowDPITransform(v49, InheritedMonitor);
  if ( v286 == 0x4000 )
  {
    if ( v292 )
    {
      *(_WORD *)(*(_QWORD *)v288 + 286LL) = *(_WORD *)(*(_QWORD *)(v313 + 40) + 286LL);
      v90 = (_DWORD *)*((_QWORD *)v292 + 37);
      if ( v90 )
      {
        *(_QWORD *)(v49 + 296) = v90;
        ++*v90;
      }
    }
  }
  v318 = (_QWORD *)(v49 + 24);
  if ( *(_QWORD *)(v49 + 24) )
  {
    MessageWindow = GetMessageWindow(v49);
    *(_OWORD *)v308 = *(_OWORD *)LockPointer(&v343, v49 + 104, MessageWindow);
    HMAssignmentLock(v308, 0);
  }
  if ( (unsigned int)IsWindowDesktopComposed(v49) )
  {
    ThreadDesktopWindow = v292;
    if ( v286 != 0x4000 && (!v292 || v292 != *(struct tagWND **)(*((_QWORD *)v292 + 3) + 112LL)) )
      ThreadDesktopWindow = (const struct tagWND *)GetThreadDesktopWindow(0);
    DwmWindowCreate((struct tagWND *)v49, ThreadDesktopWindow, &v303);
  }
  *(_QWORD *)(*(_QWORD *)v288 + 32LL) = v311;
  *(_QWORD *)(*(_QWORD *)v288 + 120LL) = MapClientNeuterToClientPfn(*(_QWORD *)v295[0], 0, v289);
  v93 = 1;
  v94 = v49;
  if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)v295[0] + 8LL) + 6LL) & 1) != 0 )
  {
    SetOrClrWF(1, v49, 516, 1);
    v95 = 1;
    v94 = v49;
    v96 = 55812;
    v93 = 0;
  }
  else
  {
    v95 = 0;
    v96 = 516;
  }
  SetOrClrWF(v95, v94, v96, v93);
  if ( (*(_BYTE *)(*(_QWORD *)v288 + 30LL) & 0x30) != 0 && (*(_BYTE *)(*(_QWORD *)v288 + 234LL) & 4) != 0 )
  {
    LODWORD(v298) = 0x20000;
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 1206);
  }
  AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)&v315);
  Win32HMThreadLockAlways<tagHOOK>::Win32HMThreadLockAlways<tagHOOK>(BugCheckParameter3, v19, v49);
  v97 = *(_BYTE *)(*(_QWORD *)v288 + 18LL);
  if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v295[0] + 8LL) + 84LL) )
  {
    v98 = Win32AllocPoolZInit(*(unsigned int *)(*(_QWORD *)(*(_QWORD *)v295[0] + 8LL) + 84LL), 1937208149);
    *(_QWORD *)(v49 + 280) = v98;
    if ( !v98 )
    {
      v99 = 5;
      v100 = *(_QWORD *)v288;
      goto LABEL_192;
    }
  }
  v101 = v97 & 4;
  LODWORD(v298) = 0;
  if ( (unsigned int)PsGetWin32KFilterSet() != 5 )
  {
LABEL_196:
    if ( v101 )
      goto LABEL_205;
    if ( (unsigned int)PsGetWin32KFilterSet() == 5 )
    {
      *(_DWORD *)(*(_QWORD *)v288 + 200LL) = (*(_DWORD *)(*(_QWORD *)v288 + 200LL) + 7) & 0xFFFFFFF8;
    }
    else
    {
      if ( !(unsigned int)Feature_UserModeNonClientScrollBars2__private_IsEnabledDeviceUsageNoInline()
        || !Scrollbar::NonClient::UserModeSupportsUserModeScrollBars(v102) )
      {
        goto LABEL_205;
      }
      v104 = Scrollbar::NonClient::UserModeSupportsPartitionedExtraBytes(v103);
      v105 = *(_QWORD *)v288;
      v106 = *(_DWORD *)(*(_QWORD *)v288 + 200LL);
      v107 = (v106 + 7) & 0xFFFFFFF8;
      if ( v104 )
      {
        *(_DWORD *)(v105 + 336) = v107 - v106;
        *(_DWORD *)(*(_QWORD *)v288 + 336LL) += 48;
        goto LABEL_205;
      }
      *(_DWORD *)(v105 + 200) = v107;
    }
    *(_DWORD *)(*(_QWORD *)v288 + 200LL) += 48;
    goto LABEL_205;
  }
  if ( !v101 )
  {
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 1245);
    goto LABEL_196;
  }
LABEL_205:
  ClientExtraBytesTotalSize = GetClientExtraBytesTotalSize((const struct tagWND *)v49);
  if ( ClientExtraBytesTotalSize )
  {
    v109 = xxxClientAllocWindowClassExtraBytes(ClientExtraBytesTotalSize);
    if ( !v109 )
    {
      v99 = 2;
      v100 = *(_QWORD *)v288;
LABEL_192:
      *(_QWORD *)(v100 + 120) = 0;
      SetOrClrWF(1, v49, 516, 1);
LABEL_476:
      v231 = *(_BYTE *)(*v302 + 31) & 0x10;
      if ( v294 )
        Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)v312);
      SetOrClrWF(1, v49, 1152, 1);
      SetOrClrWF(1, v49, 896, 1);
      if ( v231 )
        SetVisible(v49, 0);
      if ( *(_QWORD *)(v49 + 104) )
      {
        if ( v231 )
          zzzLockDisplayAreaAndInvalidateDCCache(*(_QWORD *)(v49 + 104), 16);
        if ( (*(_BYTE *)(*v302 + 31) & 0xC0) == 0x40 && !(unsigned int)IsTopLevelWindow(v49) )
        {
          v233 = *(struct tagTHREADINFO **)(v232 + 16);
          if ( v19 != v233 )
            zzzAttachThreadInput(*v339, v233);
        }
        UnlinkWindow((struct tagWND *)v49);
      }
      ClassUnlock(*(struct tagCLS **)v295[0]);
      xxxFreeWindow(v19, (struct tagWND *)v49);
      if ( v99 )
      {
        v234 = ((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
             * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8);
        v235 = v99;
        goto LABEL_542;
      }
      goto LABEL_543;
    }
    if ( (unsigned int)IsWindowBeingDestroyed(v49)
      || (*(_BYTE *)(_HMPheFromObject(v49) + 25) & 1) != 0
      || *(_QWORD *)(*(_QWORD *)v288 + 296LL) )
    {
      UserSetLastError(87);
      *(_QWORD *)(*(_QWORD *)v288 + 120LL) = 0;
      SetOrClrWF(1, v49, 516, 1);
      v99 = 0;
      goto LABEL_476;
    }
    *(_QWORD *)(*(_QWORD *)v288 + 296LL) = v109;
    v77 = v49 + 40;
  }
  if ( (unsigned int)PsGetWin32KFilterSet() != 5 || v101 )
  {
    v112 = v304;
  }
  else
  {
    v110 = (_QWORD *)GETCLIENTWNDINFO(v49);
    v111 = *(_QWORD *)(*v302 + 120);
    *v110 = v111;
    v112 = v304;
    v115 = *(_QWORD *)(W32GetUserSessionState(v111, v110, v113, v114) + 19704);
    if ( v112 >= 0 )
      v116 = *(_QWORD *)(v115 + 768);
    else
      v116 = *(_QWORD *)(v115 + 576);
    *(_QWORD *)(*(_QWORD *)v77 + 120LL) = v116;
  }
  if ( *(_QWORD *)(*(_QWORD *)v295[0] + 80LL)
    && !*(_QWORD *)(*(_QWORD *)v295[0] + 112LL)
    && (unsigned int)PsGetWin32KFilterSet() != 5 )
  {
    xxxCreateClassSmIcon(v295);
  }
  SetOrClrWF(1, v49, v289, 1);
  if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)v295[0] + 8LL) + 6LL) & 2) != 0 )
    goto LABEL_235;
  if ( v112 < 0 )
  {
    v121 = *(_QWORD *)(W32GetUserSessionState(*(_QWORD *)v295[0], v117, v118, v119) + 19704);
    v124 = Atom;
    if ( (_WORD)Atom == *(_WORD *)(v121 + 868)
      || (v126 = *(_QWORD *)(W32GetUserSessionState(v121, v120, v122, v123) + 19704), v124 == *(_WORD *)(v126 + 878))
      || (v130 = *(_QWORD *)(W32GetUserSessionState(v126, v125, v127, v128) + 19704), v124 == *(_WORD *)(v130 + 882))
      || (v134 = *(_QWORD *)(W32GetUserSessionState(v130, v129, v131, v132) + 19704), v124 == *(_WORD *)(v134 + 904))
      || (v138 = *(_QWORD *)(W32GetUserSessionState(v134, v133, v135, v136) + 19704), v124 == *(_WORD *)(v138 + 870))
      || (v142 = *(_QWORD *)(W32GetUserSessionState(v138, v137, v139, v140) + 19704), v124 == *(_WORD *)(v142 + 874))
      || (v146 = *(_QWORD *)(W32GetUserSessionState(v142, v141, v143, v144) + 19704), v124 == *(_WORD *)(v146 + 880))
      || (v150 = *(_QWORD *)(W32GetUserSessionState(v146, v145, v147, v148) + 19704), v124 == *(_WORD *)(v150 + 898))
      || v124 == *(_WORD *)(*(_QWORD *)(W32GetUserSessionState(v150, v149, v151, v152) + 19704) + 872LL) )
    {
LABEL_235:
      SetOrClrWF(1, v49, 520, 1);
    }
  }
  if ( ((*(_BYTE *)(*(_QWORD *)(*(_QWORD *)v295[0] + 8LL) + 6LL) & 2) != 0 || v112 < 0)
    && v286 != 0x4000
    && (*(_QWORD *)&v303.left = PsGetProcessPeb(**((_QWORD **)*v339 + 57))) != 0 )
  {
    v153 = *(_WORD *)(*(_QWORD *)&v303.left + 844LL);
    if ( v153 == -535 )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 1404);
    if ( v153 == -10600 )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 1405);
    v154 = a15;
    v155 = v284;
  }
  else
  {
    v154 = a15;
    v155 = v284;
  }
  if ( (GetAppCompatFlags(v19) & 0x8000000) != 0 )
  {
    SetOrClrWF(1, v49, 1032, 1);
    v284 = v155 & 0x3F;
    v333 &= 0x3Fu;
  }
  SetOrClrWF(1, v49, 1281, 1);
  SetOrClrWF(1, v49, 1282, 1);
  SetOrClrWF(1, v49, 1284, 1);
  v156 = v154;
  if ( v154 <= *((_WORD *)v19 + 334) )
    v156 = *((_DWORD *)v19 + 167);
  *(_DWORD *)(v49 + 256) = v156;
  if ( (GetAppCompatFlags2(39168) & 0x10000000) != 0 )
    SetOrClrWF(1, v49, 2688, 1);
  if ( (unsigned int)IsInsideUserApiHook() )
    xxxLoadUserApiHook();
  if ( (unsigned int)WantImeWindow(v292, (struct tagWND *)v49) )
  {
    v157 = *((_QWORD *)v19 + 102);
    if ( v157
      && ((*(_BYTE *)(_HMPheFromObject(v157) + 25) & 1) != 0
       || (unsigned int)IsWindowBeingDestroyed(*((_QWORD *)v19 + 102))) )
    {
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1489);
    }
    *(_DWORD *)(v49 + 380) |= 0x10000000u;
    ++*((_DWORD *)v19 + 235);
  }
  if ( ((*((_BYTE *)v19 + 712) | *(_BYTE *)(**((_QWORD **)v19 + 62) + 16LL)) & 0x40) != 0 )
  {
    v315 = (__int64)v323;
    v316 = 0;
    if ( (unsigned int)xxxCallHook(3, *(_QWORD *)v49, (__int64)&v315, 5) )
    {
      v99 = 6;
      goto LABEL_476;
    }
    v285 = __PAIR64__(v328, v329);
    LODWORD(Str1) = v327;
    v291 = v326;
    v310 = v316;
  }
  else
  {
    v310 = 0;
  }
  if ( (*(_BYTE *)(*(_QWORD *)v288 + 31LL) & 0xC0) != 0x40 )
  {
    v158 = 0;
    v287 = 0;
    goto LABEL_269;
  }
  v158 = 1;
  v287 = 1;
  if ( !v292 )
    goto LABEL_475;
LABEL_269:
  v159 = 0;
  v290 = 5;
  if ( v158 != v322 )
  {
    v307 = 0;
    SmartObjStackRefBase<tagMENU>::operator=(v306, 0);
    v158 = v287;
  }
  if ( (*(_BYTE *)(*(_QWORD *)v288 + 31LL) & 0xC0) != 0 )
  {
    v160 = 0;
    if ( (_DWORD)v285 == 0x80000000 || (_DWORD)v285 == 0x8000 )
      v285 = 0;
    v161 = (unsigned int)Str1;
    if ( (_DWORD)Str1 == 0x80000000 || (_DWORD)Str1 == 0x8000 )
    {
      v161 = 0;
      LODWORD(Str1) = 0;
      v291 = 0;
    }
  }
  else
  {
    v160 = 1;
    v161 = (unsigned int)Str1;
  }
  *(_QWORD *)&v347 = v285;
  *((_QWORD *)&v347 + 1) = __PAIR64__(v291, v161);
  if ( v158 )
  {
    v320 = *(_OWORD *)(*(_QWORD *)(v313 + 40) + 104LL);
    if ( IsDpiBoundaryBetweenWindows((const struct tagWND *)v49, v292) )
    {
      *(_DWORD *)(v49 + 224) = 0;
      *(_DWORD *)(v49 + 228) = 0;
      LogicalToPhysicalInPlaceRectWithSubpixel(v292, &v320, v49 + 224);
      PhysicalToLogicalInPlaceRectWithSubpixel(v49, &v320, v49 + 224);
      v164 = DWORD1(v347);
      v163 = (unsigned int)v347;
    }
    if ( v292 != (struct tagWND *)GetDesktopWindow(v49, v162, v163, v164) )
    {
      LODWORD(v347) = v320 + v165;
      DWORD1(v347) = DWORD1(v320) + v166;
    }
    v310 = 1;
  }
  if ( v160 )
  {
    v167 = 0;
    SetOrClrWF(1, v49, 3844, 1);
    v168 = 192;
    SetOrClrWF(1, v49, 2305, 1);
    SetOrClrWF(1, v49, 16, 1);
    v170 = v285;
    v171 = 0x8000;
    if ( (_DWORD)v285 == 0x80000000 || (_DWORD)v285 == 0x8000 )
    {
      if ( DWORD1(v347) != 0x80000000 )
      {
        v169 = 5;
        if ( DWORD1(v347) != 0x8000 )
          v169 = DWORD1(v347);
        v290 = v169;
      }
      v170 = v285;
    }
    if ( !v301 && (v170 == 0x80000000 || v170 == 0x8000 || (_DWORD)Str1 == 0x80000000 || (_DWORD)Str1 == 0x8000) )
    {
      v172 = *(_QWORD *)(*v296 + 680LL);
      if ( v172 )
      {
        v173 = (struct tagMONITOR *)ValidateHmonitor(v172, v169, 0x8000);
        goto LABEL_302;
      }
      if ( v292 )
      {
        v173 = _MonitorFromWindowInternal(v292, 2u, 0);
LABEL_302:
        v167 = (__int64)v173;
      }
      if ( !v167 )
      {
        v167 = *(_QWORD *)(GetDispInfo(v172) + 96);
        goto LABEL_305;
      }
    }
    else
    {
LABEL_305:
      if ( !v167 )
      {
        v167 = ValidateHmonitor(*(_QWORD *)(*(_QWORD *)v288 + 256LL), v169, v171);
        if ( !v167 )
        {
          if ( v301 )
            v167 = GetInheritedMonitor((struct tagWND *)v49);
          else
            v167 = 0;
          if ( !v167 )
            v167 = MonitorFromRect(*(_QWORD *)v288 + 88LL, 2);
          UpdateWindowMonitorAndDpiInfoHelper((struct tagWND *)v49, (struct tagMONITOR *)v167);
          UpdateTopLevelWindowDPITransform(v49, v167);
        }
      }
    }
    SetTiledRect(v49, &v348, v167);
    v174 = v285;
    if ( (_DWORD)v285 == 0x80000000 || (_DWORD)v285 == 0x8000 )
    {
      v177 = v296;
      if ( (*(_DWORD *)(*v296 + 792LL) & 4) != 0 )
      {
        v159 = 1;
        v174 = *(_DWORD *)(*v296 + 776LL);
        LODWORD(v347) = v174;
        v178 = *(_DWORD *)(*v296 + 780LL);
      }
      else
      {
        v174 = v348;
        LODWORD(v347) = v348;
        v178 = DWORD1(v348);
      }
      DWORD1(v347) = v178;
      v285 = __PAIR64__(v178, v174);
      v175 = 1;
    }
    else
    {
      v175 = 0;
      v176 = *(_WORD *)(v167 + 74);
      v177 = v296;
      if ( v176 )
        *(_WORD *)(v167 + 74) = v176 - 1;
    }
    if ( DWORD2(v347) == 0x80000000 || DWORD2(v347) == 0x8000 )
    {
      if ( (*(_DWORD *)(*v177 + 792LL) & 2) != 0 )
      {
        v159 = 1;
        *((_QWORD *)&v347 + 1) = *(_QWORD *)(*v177 + 784LL);
      }
      else
      {
        DWORD2(v347) = DWORD2(v348) - v174;
        HIDWORD(v347) = HIDWORD(v348) - HIDWORD(v285);
      }
    }
    else if ( v175 )
    {
      MonitorRect = (int *)GetMonitorRect(v308, v167);
      v180 = MonitorRect[1];
      v181 = v347 + DWORD2(v347) - MonitorRect[2];
      v182 = DWORD1(v347) + HIDWORD(v347) - MonitorRect[3];
      if ( v181 > 0 )
      {
        v183 = *MonitorRect;
        LODWORD(v285) = v285 - v181;
        LODWORD(v347) = v285;
        if ( (int)v285 < v183 )
        {
          LODWORD(v285) = v183;
          LODWORD(v347) = v183;
        }
      }
      if ( v182 > 0 )
      {
        HIDWORD(v285) -= v182;
        DWORD1(v347) = HIDWORD(v285);
        if ( SHIDWORD(v285) < v180 )
        {
          HIDWORD(v285) = v180;
          DWORD1(v347) = v180;
        }
      }
    }
  }
  else
  {
    v168 = 0;
  }
  if ( v159 )
    *(_DWORD *)(*v296 + 792LL) &= 0xFFFFFFF9;
  v184 = v49 + 40;
  if ( (((*(_BYTE *)(*(_QWORD *)v288 + 31LL) & 0xC0) + 0x80) & 0xBF) == 0 )
    SetOrClrWF(1, v49, 3844, 1);
  *(_WORD *)(*(_QWORD *)v288 + 30LL) |= v168;
  if ( (unsigned __int8)SmartObjStackRef<tagMENU>::operator==(v306) && !v287 && *(_QWORD *)(*(_QWORD *)v295[0] + 96LL) )
  {
    v303 = 0;
    v186 = v49;
    if ( *(_QWORD *)(v49 + 104) )
      v186 = *(_QWORD *)(v49 + 104);
    zzzLockDisplayAreaAndInvalidateDCCache(v186, 16);
    RtlInitUnicodeStringOrId(&v303, *(_QWORD *)(*(_QWORD *)v295[0] + 96LL));
    v187 = xxxClientLoadMenu(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v295[0] + 8LL) + 64LL), &v303);
    v307 = 0;
    SmartObjStackRefBase<tagMENU>::operator=(v306, v187);
    if ( (*(_BYTE *)(*(_QWORD *)v288 + 31LL) & 0xC0) != 0x40 && !(unsigned int)IsWindowBeingDestroyed(v49) )
    {
      if ( (unsigned __int8)SmartObjStackRef<tagMENU>::operator==(v306) )
        v324 = 0;
      else
        v324 = **(struct _HEAD ***)v306[0];
      goto LABEL_347;
    }
    v190 = v307;
    if ( !v307 )
      v190 = *(struct _HEAD **)v306[0];
    DestroyMenu(v190);
    v307 = 0;
    SmartObjStackRefBase<tagMENU>::operator=(v306, 0);
LABEL_475:
    v99 = (int)v298;
    goto LABEL_476;
  }
LABEL_347:
  WindowCloakStateComponentUIAware = 0;
  if ( (*(_BYTE *)(*(_QWORD *)v288 + 31LL) & 0xC0) == 0x40 )
  {
    v189 = v307;
    if ( !v307 )
      v189 = *(struct _HEAD **)v306[0];
    *(_QWORD *)(*(_QWORD *)v288 + 320LL) = v189;
    *(_QWORD *)(*(_QWORD *)(v49 + 40) + 152LL) = 0;
    *(_QWORD *)(v49 + 168) = 0;
  }
  else
  {
    *(_QWORD *)(*(_QWORD *)v288 + 320LL) = 0;
    LockWndMenuWorker(v49, 0, v306);
  }
  if ( (*(_BYTE *)(*(_QWORD *)v288 + 31LL) & 0xC0) != 0x40 )
  {
    if ( (a16 & 4) != 0 )
    {
      LOBYTE(v185) = 1;
      CoreWindowProp::ChangeRole(v49, 1, v185);
    }
    *(_OWORD *)v308 = *(_OWORD *)LockPointer(&v303, v49 + 200, v49);
    HMAssignmentLock(v308, 0);
    if ( (unsigned int)IsTopLevelParent(v292) )
    {
      v193 = v49 + 120;
      *(_QWORD *)(*(_QWORD *)(v49 + 40) + 64LL) = 0;
      *(_QWORD *)&v303.left = v49 + 120;
      *(_QWORD *)&v303.right = 0;
      HMAssignmentLock(&v303, 0);
    }
    else
    {
      NonChildAncestor = GetNonChildAncestor(v191);
      if ( !(unsigned int)ValidateOwnerDepth(v49, NonChildAncestor) )
        goto LABEL_360;
      if ( NonChildAncestor )
      {
        *(_DWORD *)(*(_QWORD *)v288 + 236LL) = *(_DWORD *)(*(_QWORD *)(NonChildAncestor + 40) + 236LL);
        SetOrClrWF(*(_BYTE *)(*(_QWORD *)(NonChildAncestor + 40) + 232LL) & 0x40, v49, 55360, 1);
        WindowCloakStateComponentUIAware = GetWindowCloakStateComponentUIAware(NonChildAncestor);
      }
      v193 = v49 + 120;
      *(_OWORD *)v308 = *(_OWORD *)LockPointer(&v303, v49 + 120, NonChildAncestor);
      HMAssignmentLock(v308, 1);
      if ( *(_QWORD *)(v49 + 120)
        && ((*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v49 + 120) + 40LL) + 24LL) & 8) != 0
         || *(_DWORD *)(*(_QWORD *)v288 + 236LL) != 1) )
      {
        SetOrClrWF(1, v49, 2056, 1);
      }
      v198 = *(_QWORD *)(W32GetUserSessionState(v195, v194, v196, v197) + 19704);
      if ( (_WORD)Atom != *(_WORD *)(v198 + 898) )
      {
        if ( *(_QWORD *)v193 )
        {
          v199 = *(struct tagTHREADINFO **)(*(_QWORD *)v193 + 16LL);
          if ( v199 != v19 )
            zzzAttachThreadInput(v19, v199);
        }
      }
      v184 = v49 + 40;
    }
    IsEnabledDeviceUsageNoInline = Feature_Scoobe_ShellHost__private_IsEnabledDeviceUsageNoInline();
    if ( !*(_QWORD *)v193 )
    {
      if ( IsEnabledDeviceUsageNoInline )
      {
        if ( (unsigned int)CoreWindowProp::IsComponent((const struct tagWND *)v49) )
          goto LABEL_389;
        v201 = *(_DWORD *)(*(_QWORD *)v184 + 236LL);
        if ( (unsigned int)(v201 - 8) <= 3 || v201 == 15 )
          goto LABEL_388;
        v202 = (*(_BYTE *)(*(_QWORD *)v184 + 232LL) & 0x40) == 0;
      }
      else
      {
        if ( (unsigned int)CoreWindowProp::IsComponent((const struct tagWND *)v49) )
          goto LABEL_389;
        v203 = *(_DWORD *)(*(_QWORD *)v184 + 236LL);
        if ( v203 <= 0xF )
        {
          v204 = 44800;
          if ( _bittest(&v204, v203) )
            goto LABEL_388;
        }
        v202 = (*(_BYTE *)(*(_QWORD *)v184 + 232LL) & 0x40) == 0;
      }
      if ( !v202 )
LABEL_388:
        WindowCloakStateComponentUIAware = 2;
    }
LABEL_389:
    if ( v292 && v292 == *(struct tagWND **)(*((_QWORD *)v292 + 3) + 112LL) )
    {
      v205 = v19;
    }
    else
    {
      v79 = GetThreadDesktopWindow(0);
      v292 = (struct tagWND *)v79;
      v205 = v19;
      Win32HM_LockIntoThread<1>(v19, v79, v312);
      v294 = 1;
    }
    if ( !v305 )
      goto LABEL_399;
    if ( !*((_QWORD *)v205 + 198) )
    {
      SetOrClrWF(1, v49, 55424, 1);
      *((_QWORD *)v205 + 170) |= 0x40000uLL;
      *(_DWORD *)(*((_QWORD *)v205 + 58) + 508LL) |= 0x2000000u;
      if ( !*((_QWORD *)v205 + 197) )
      {
        KernelEvent = CreateKernelEvent(1, 0);
        *((_QWORD *)v205 + 197) = KernelEvent;
        if ( !KernelEvent )
        {
          v99 = 7;
          goto LABEL_476;
        }
      }
      *(_QWORD *)&v303.left = (char *)v205 + 1584;
      *(_QWORD *)&v303.right = v49;
      HMAssignmentLock(&v303, 0);
      goto LABEL_399;
    }
LABEL_360:
    UserSetLastError(87);
    goto LABEL_475;
  }
  if ( !v292 )
    goto LABEL_475;
  if ( v305 )
    goto LABEL_360;
LABEL_399:
  v207 = 0;
  if ( (*(_DWORD *)(v49 + 380) & 0x1000000) != 0 )
  {
    v207 = *(_QWORD *)(v49 + 104);
    UnlinkWindow((struct tagWND *)v49);
  }
  if ( !(unsigned int)IsTopLevelParent(v79) )
  {
    *(_DWORD *)(*(_QWORD *)v288 + 236LL) = *(_DWORD *)(*(_QWORD *)(v79 + 40) + 236LL);
    SetOrClrWF(*(_BYTE *)(*(_QWORD *)(v79 + 40) + 232LL) & 0x40, v49, 55360, 1);
  }
  if ( v79 && !(unsigned int)ValidateNewParent(v49, v79, 1) )
  {
    v99 = 9;
    goto LABEL_476;
  }
  v208 = (struct tagWND **)(v49 + 104);
  *(_OWORD *)v308 = *(_OWORD *)LockPointer(&v303, v49 + 104, v292);
  HMAssignmentLock(v308, 0);
  if ( v292 )
    v209 = (unsigned int)-__CFSHR__(*(_DWORD *)(*((_QWORD *)v292 + 5) + 232LL), 10);
  else
    v209 = 0;
  SetWindowSubtreeCoreWindowStatus(v49, v209);
  v210 = *(_QWORD *)(v49 + 40);
  if ( (*(_DWORD *)(v210 + 288) & 0xF) == 2 )
    *(_DWORD *)(v210 + 232) = *(_DWORD *)(v210 + 232) & 0xFFFFFBFF
                            | (ShouldUseLogPixelsForWindowMetrics((struct tagWND *)v49) << 10);
  if ( (WindowCloakStateComponentUIAware & 2) == 0 )
    *(_DWORD *)(v49 + 384) |= 4u;
  if ( WindowCloakStateComponentUIAware )
  {
    v211 = zzzSetWindowCompositionCloak(v49, WindowCloakStateComponentUIAware);
    if ( v211 < 0 )
    {
      v212 = RtlNtStatusToDosError(v211);
      UserSetLastError(v212);
      v99 = 8;
      goto LABEL_476;
    }
  }
  AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)v308);
  if ( v207 )
    zzzLockDisplayAreaAndInvalidateDCCache(v207, 16);
  if ( v292 )
    zzzLockDisplayAreaAndInvalidateDCCache(v292, 16);
  AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v308);
  v216 = *(_QWORD *)(v49 + 40);
  if ( (*(_BYTE *)(v216 + 31) & 0xC0) == 0x40 && !(unsigned int)IsTopLevelWindow(v49) )
  {
    v217 = (struct tagTHREADINFO **)*v208;
    if ( *v208 )
    {
      if ( v19 != v217[2] )
      {
        if ( v292 != (struct tagWND *)v217 )
        {
          v305 = 0x20000;
          MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 2199);
        }
        zzzAttachThreadInput(v19, *((struct tagTHREADINFO **)*v208 + 2));
        v218 = GetMessageWindow(v49);
        if ( v215 != (struct tagWND *)v218 )
        {
          v214 = *((_QWORD *)v215 + 5);
          v216 = *(unsigned int *)(*v302 + 288);
          if ( (((unsigned __int8)v216 ^ *(_BYTE *)(v214 + 288)) & 0xF) != 0
            && !IsChildWindowDpiIsolationEnabled((struct tagWND *)v49, v215) )
          {
            xxxForceUpdateProcessDpiAwarenessContext((struct tagWND *)v49, *(_DWORD *)(*((_QWORD *)*v208 + 5) + 288LL));
          }
        }
      }
    }
  }
  v219 = W32GetUserSessionState(v216, v213, v214, v215);
  if ( v314 != *(unsigned __int16 *)(v219 + 41168) && v314 != 32769 && !*(_DWORD *)v319[0] )
  {
    _InterlockedExchange(
      (volatile __int32 *)(*((_QWORD *)v19 + 60) + 20LL),
      (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24);
    xxxUpdateInputHangInfo(0, 1);
  }
  xxxAdjustSize((struct tagWND *)v49);
  ConstrainWindowSIZERECT(&v347);
  if ( *v318 && (*(_BYTE *)(*v302 + 31) & 0x40) == 0 && *(char *)(*v302 + 24) >= 0 )
    CheckFullScreen((struct tagWND *)v49);
  v220 = DWORD2(v347);
  if ( SDWORD2(v347) < 0 )
    v220 = 0;
  DWORD2(v347) = v220;
  v221 = HIDWORD(v347);
  if ( v347 < 0 )
    v221 = 0;
  HIDWORD(v347) = v221;
  RECTFromSIZERECT(*v302 + 88, &v347);
  if ( v287 )
  {
    v222 = ValidateHmonitorNoRip(*(_QWORD *)(*((_QWORD *)v292 + 5) + 256LL));
LABEL_447:
    v223 = (struct tagMONITOR *)v222;
  }
  else
  {
    if ( v301 )
    {
      v222 = GetInheritedMonitor((struct tagWND *)v49);
      goto LABEL_447;
    }
    v223 = 0;
  }
  if ( v223 || (v223 = (struct tagMONITOR *)MonitorFromRect(*v302 + 88, 2), v224 = 0, v223) )
    v224 = *(_QWORD *)v223;
  if ( v224 != *(_QWORD *)(*v302 + 256) )
  {
    UpdateWindowMonitorAndDpiInfoHelper((struct tagWND *)v49, v223);
    if ( !v287 )
      UpdateTopLevelWindowDPITransform(v49, v223);
  }
  v225 = v302;
  if ( (*(_BYTE *)(*v302 + 27) & 0x20) != 0 && GetRedirectionBitmap(v49) )
  {
    GreLockVisRgn();
    if ( (int)RecreateRedirectionBitmap((struct tagWND *)v49, 0, 0) < 0 )
    {
      GreUnlockVisRgn();
      v99 = 3;
      goto LABEL_476;
    }
    GreUnlockVisRgn();
  }
  if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)v295[0] + 8LL) + 8LL) & 0x20) != 0
    || (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)v295[0] + 8LL) + 8LL) & 0x40) != 0 && !*(_QWORD *)(*(_QWORD *)v295[0] + 40LL) )
  {
    StyleWindow = GetStyleWindow(v49, 2848);
    GreLockVisRgn();
    if ( !CreateCacheDC(v49, StyleWindow != 0 ? 49152 : 0x8000, 0) )
    {
      GreUnlockVisRgn();
      v99 = 10;
      goto LABEL_476;
    }
    GreUnlockVisRgn();
    v225 = v302;
  }
  v227 = v284;
  if ( (v284 & 0x80000) != 0 && (*(_BYTE *)(*v225 + 26) & 8) == 0 )
  {
    if ( (int)xxxSetLayeredWindow((struct tagWND *)v49) < 0 )
    {
      v99 = 11;
      goto LABEL_476;
    }
    v227 = v284;
  }
  if ( (v227 & 0x2000000) != 0 && !GetStyleWindow(*v208, 2818) )
  {
    SetOrClrWF(1, v49, 2818, 1);
    if ( (int)SetRedirectedWindow((struct tagWND *)v49) < 0 )
    {
      SetOrClrWF(0, v49, 2818, 1);
      v99 = 12;
      goto LABEL_476;
    }
  }
  v328 = HIDWORD(v285);
  v329 = v285;
  v327 = (int)Str1;
  v326 = v291;
  if ( !xxxSendTransformableMessageTimeout((struct tagWND *)v49, 0x81u, 0, 0, 0, 1, 1) )
    goto LABEL_475;
  v236 = *(_QWORD *)(*v340 + 8LL);
  if ( (*(_BYTE *)(v236 + 9) & 2) != 0 )
  {
    SystemMenu = xxxGetSystemMenu((struct tagWND *)v49);
    v307 = 0;
    SmartObjStackRefBase<tagMENU>::operator=(v306, SystemMenu);
    if ( !(unsigned __int8)SmartObjStackRef<tagMENU>::operator==(v306) )
    {
      Win32HMThreadLock<tagMENU>::Win32HMThreadLock<tagMENU>(v308, v306);
      xxxRemoveDeleteMenuHelper(v306, 5, 1024, 1);
      xxxRemoveDeleteMenuHelper(v306, 5, 1024, 1);
      Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)v308);
    }
  }
  if ( (*(_BYTE *)(*v225 + 18) & 2) != 0 && (!v336 || v334 || *(_QWORD *)(v49 + 184)) )
  {
    *(_OWORD *)v308 = 0;
    v331 = *(_QWORD *)(v49 + 184);
    StrName = tagWND::ProtectedLargeUnicodeStringWNDstrName::getStrName(
                (tagWND::ProtectedLargeUnicodeStringWNDstrName *)(v49 + 184),
                (struct _LARGE_UNICODE_STRING *)v308);
    v334 = *(_DWORD *)StrName;
    v236 = *((unsigned int *)StrName + 1);
    v335 = *((_DWORD *)StrName + 1);
    v336 = *((_QWORD *)StrName + 1);
  }
  if ( (**(_DWORD **)(W32GetUserSessionState(v236, v228, v229, v230) + 19704) & 4) != 0 )
  {
    v239 = (struct tagWND **)((char *)v19 + 816);
    if ( !*((_QWORD *)v19 + 102) && (*(_DWORD *)(v49 + 380) & 0x10000000) != 0 )
    {
      DefaultImeWindow = xxxCreateDefaultImeWindow((struct tagWND *)v49, Atom, v311);
      v319[0] = (ULONG_PTR)v19 + 816;
      v319[1] = (ULONG_PTR)DefaultImeWindow;
      HMAssignmentLock(v319, 0);
      if ( *v239 )
      {
        Win32HMThreadLockAlways<tagHOOK>::Win32HMThreadLockAlways<tagHOOK>(v308, v19, *v239);
        xxxSendTransformableMessageTimeout(*v239, 0x287u, 0, 0, 0, 1, 1);
        Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)v308);
      }
      v241 = (**((_DWORD **)v19 + 64) >> 6) & 1;
      v342 = v241;
      if ( *v239 && v241 )
      {
        Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(v319, *v239);
        xxxSendTransformableMessageTimeout(*v239, 0x287u, 0, 0, 0, 1, 1);
        **((_QWORD **)v19 + 64) &= ~0x40uLL;
        Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)v319);
      }
    }
  }
  v242 = v292;
  if ( v292 && ((*(_DWORD *)(v49 + 380) & 0x1000000) == 0 || *v208 == v292) )
  {
    CompositeAppFrameWindowOrSelf = PWInsertAfter(v310);
    if ( !(unsigned int)IsPseudoPwnd(CompositeAppFrameWindowOrSelf)
      && *(struct tagWND **)(CompositeAppFrameWindowOrSelf + 104) != *v208 )
    {
      CompositeAppFrameWindowOrSelf = v287 != 0;
    }
    v244 = *(_QWORD *)(v49 + 120);
    if ( v244 )
    {
      *(_DWORD *)(*v302 + 236) = *(_DWORD *)(*(_QWORD *)(v244 + 40) + 236LL);
      SetOrClrWF(*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v49 + 120) + 40LL) + 232LL) & 0x40, v49, 55360, 1);
    }
    if ( !(unsigned int)ValidateNewParent(v49, v292, 1) )
    {
      v245 = 9;
      goto LABEL_536;
    }
    UnlinkWindow((struct tagWND *)v49);
    v248 = *v302;
    v249 = v292;
    if ( (*(_BYTE *)(*v302 + 31) & 0xC0) != 0x40 && v292 != *(struct tagWND **)(*((_QWORD *)v292 + 3) + 112LL) )
    {
      if ( (*(_BYTE *)(v248 + 24) & 8) != 0 )
      {
        if ( *(_QWORD *)(W32GetUserSessionState(v248, v292, v246, v247) + 19160) )
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
        v250 = (const struct tagWND *)CalcForegroundInsertAfter(v49, v249);
        CompositeAppFrameWindowOrSelf = (unsigned __int64)v250;
        if ( !*(_QWORD *)(v49 + 120) )
          CompositeAppFrameWindowOrSelf = (unsigned __int64)CoreWindowProp::GetCompositeAppFrameWindowOrSelf(v250);
      }
    }
    if ( CompositeAppFrameWindowOrSelf >= 2 && (unsigned int)IsPseudoPwnd(CompositeAppFrameWindowOrSelf) )
    {
      v245 = 13;
      goto LABEL_536;
    }
    LinkWindow((struct tagWND *)v49);
    zzzLockDisplayAreaAndInvalidateDCCache(v292, 16);
    v242 = v292;
  }
  v252 = v302;
  v253 = *v302;
  if ( (*(_BYTE *)(*v302 + 31) & 0xC0) == 0x40 && (*(_BYTE *)(*((_QWORD *)v242 + 5) + 26LL) & 0x40) != 0 )
  {
    v254 = *(_DWORD *)(v253 + 96);
    v255 = *(_DWORD *)(v253 + 88);
    *(_DWORD *)(v253 + 96) = DWORD2(v320) + v320 - v255;
    *(_DWORD *)(*v252 + 88) = v255 + *(_DWORD *)(*v252 + 96) - v254;
  }
  v348 = *(_OWORD *)(*v252 + 88);
  xxxSendTransformableMessageTimeout((struct tagWND *)v49, 0x83u, 0, 0, 0, 1, 0);
  *(_OWORD *)(*v252 + 104) = v348;
  if ( xxxSendTransformableMessageTimeout((struct tagWND *)v49, 1u, 0, 0, 0, 1, 1) == -1 )
  {
    v245 = (int)v298;
LABEL_536:
    if ( v294 )
      Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)v312);
    if ( Win32HMThreadLockBase<tagMENU,0,1>::ManualUnlock<void>((ULONG_PTR)BugCheckParameter3) )
      xxxDestroyWindow((struct tagWND *)v49);
    ClassUnlock(*(struct tagCLS **)v295[0]);
    if ( v245 )
    {
      v234 = ((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
           * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8);
      v235 = v245;
LABEL_542:
      TraceLoggingCreateWindowFailed(v235, *((unsigned __int64 *)&v234 + 1));
    }
LABEL_543:
    Win32HMOptionalThreadLockAlways<tagMENU>::~Win32HMOptionalThreadLockAlways<tagMENU>((ULONG_PTR)BugCheckParameter3);
    goto LABEL_6;
  }
  SetOrClrWF(1, v49, 1920, 1);
  xxxConsiderPreferredDpiChange((struct tagWND *)v49);
  if ( (unsigned int)IsWindowDesktopComposed(v49) )
  {
    v259 = (void *)ReferenceDwmApiPort(v257, v256, v258);
    DwmAsyncChildStyleChange(v259);
    DwmChildRectChange((struct tagWND *)v49);
    DirtyVisRgnTrackers((struct tagWND *)v49);
    v263 = (void *)ReferenceDwmApiPort(v261, v260, v262);
    DwmAsyncOwnerChange(v263);
    v252 = v302;
  }
  xxxWindowEvent(0x8000u, (struct tagWND *)v49, 0, 0, 0);
  if ( (*(_BYTE *)(*v252 + 16) & 0x10) == 0 )
  {
    xxxSendSizeMessage((struct tagWND *)v49);
    if ( v292 )
    {
      DesktopWindow = GetDesktopWindow(v49, v292, v268, v269);
      if ( DesktopWindow != v271 )
      {
        LODWORD(v348) = v348 - v320;
        DWORD1(v348) -= DWORD1(v320);
      }
    }
    xxxSendTransformableMessageTimeout((struct tagWND *)v49, 3u, 0, 0, 0, 1, 0);
  }
  v272 = *(_DWORD *)(W32GetUserSessionState(v265, v264, v266, v267) + 66784) & 0x10000 | 1;
  v273 = v302;
  v274 = *(_BYTE *)(*v302 + 31);
  if ( (v274 & 0x20) != 0 )
  {
    SetMinimize(v49, 0);
    v275 = 7;
    goto LABEL_555;
  }
  if ( (v274 & 1) != 0 )
  {
    SetOrClrWF(0, v49, 3841, 1);
    v272 |= 0x10u;
    v275 = 3;
LABEL_555:
    xxxMinMaximize(v49, v275, v272);
  }
  CalcWindowFullScreen((struct tagWND *)v49);
  if ( (*(_BYTE *)(*v273 + 31) & 0xC0) == 0x40 && (*(_BYTE *)(*v273 + 24) & 4) == 0 && *v208 )
  {
    Win32HMThreadLockAlways<tagWND>::Win32HMThreadLockAlways<tagWND>(v308, v19, v49 + 104);
    xxxSendTransformableMessageTimeout(*v208, 0x210u, 0, 0, 0, 1, 0);
    Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)v308);
  }
  xxxInheritWindowMonitor((struct tagWND *)v49);
  CDwmWindowNotifyBatch::CDwmWindowNotifyBatch((CDwmWindowNotifyBatch *)v346, (struct tagWND *)v49);
  if ( (a5 & 0x10000000) != 0 )
  {
    v280 = W32GetUserSessionState(v277, v276, v278, v279);
    xxxShowWindowEx(
      v49,
      v290 | *(_DWORD *)(v280 + 66784) & 0x10000u,
      v290 & 0x10000 | *(_DWORD *)(v280 + 66784) & 0x10000u);
  }
  CDwmWindowNotifyBatch::~CDwmWindowNotifyBatch((CDwmWindowNotifyBatch *)v346);
  if ( (*(_BYTE *)(*v273 + 31) & 0xC0) == 0 || (*(_BYTE *)(*v273 + 26) & 4) != 0 )
  {
    v281 = v296;
    if ( *(_DWORD *)(*v296 + 676LL) )
    {
      xxxSendTransformableMessageTimeout((struct tagWND *)v49, 0x32u, 0, 0, 0, 1, 1);
      *(_DWORD *)(*v281 + 676LL) = 0;
    }
  }
  if ( v294 )
    Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)v312);
  ClassUnlock(*(struct tagCLS **)v295[0]);
  v282 = Win32HMThreadLockBase<tagMENU,0,1>::ManualUnlock<void>((ULONG_PTR)BugCheckParameter3);
  v283 = v282;
  if ( !v282 || (*(_BYTE *)(_HMPheFromObject(v282) + 25) & 1) != 0 )
    v283 = 0;
  Win32HMOptionalThreadLockAlways<tagMENU>::~Win32HMOptionalThreadLockAlways<tagMENU>((ULONG_PTR)BugCheckParameter3);
  SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(v306);
  Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)v312);
  SmartObjStackRef<tagPOPUPMENU>::~SmartObjStackRef<tagPOPUPMENU>(v295);
  return v283;
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
