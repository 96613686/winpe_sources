# xxxCreateDesktopEx

- ea: `0x140174168`
- end: `0x1401751eb`
- name: `xxxCreateDesktopEx`
- size: `4227`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, int, HANDLE *, int)`
- caller_count: `4`
- callee_count: `38`
- tags: `broker_com_uri`

## callers

- `0x1401734b8`
- `0x140173b1c`
- `0x1401e48a0`
- `0x1402b5c00`

## callees

- `0x140004cbc`
- `0x14002b638`
- `0x1400373d0`
- `0x140037730`
- `0x1400381a8`
- `0x14003a0c0`
- `0x14003a784`
- `0x14005c4a0`
- `0x140077cc8`
- `0x1400911b0`
- `0x1400a82e0`
- `0x1400b1334`
- `0x1400b13c8`
- `0x1400b3de0`
- `0x1400b71ac`
- `0x1400ba610`
- `0x1400bcaa0`
- `0x1400be32c`
- `0x1400c11d8`
- `0x1400c2a64`
- `0x1400c2ab8`
- `0x1400c2dd8`
- `0x1400de254`
- `0x140130ec0`
- `0x140131f10`
- `0x1401494f4`
- `0x1401734b8`
- `0x140173948`
- `0x140173acc`
- `0x140174168`
- `0x1401751f4`
- `0x140198928`
- `0x1401e32a8`
- `0x140248960`
- `0x1402913f0`
- `0x140294394`
- `0x140298418`
- `0x1402a4da8`

## import_xrefs

- `ntoskrnl!ObOpenObjectByName` at `0x140174232`
- `ntoskrnl!ObOpenObjectByName` at `0x140174232`
- `ntoskrnl!KeSetEvent` at `0x140174c8d`
- `ntoskrnl!KeSetEvent` at `0x140174e8d`
- `ntoskrnl!KeSetEvent` at `0x140174c8d`
- `ntoskrnl!KeSetEvent` at `0x140174e8d`
- `ntoskrnl!KeWaitForSingleObject` at `0x140174d0b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140174d0b`
- `ntoskrnl!ExDesktopObjectType` at `0x1401741f2`
- `ntoskrnl!ExDesktopObjectType` at `0x1401742d6`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401742ea`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401742ea`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140174676`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140174698`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140174797`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401747b9`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140174676`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140174698`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140174797`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401747b9`
- `ntoskrnl!ObfDereferenceObject` at `0x140174d5a`
- `ntoskrnl!ObfDereferenceObject` at `0x140174d5a`
- `win32kbase!?hModuleWin@@3PEAXEA` at `0x1401746cf`
- `win32kbase!?hModuleWin@@3PEAXEA` at `0x1401747f8`
- `win32kbase!W32SetCurrentThreadDpiAwarenessContext` at `0x140174635`
- `win32kbase!W32SetCurrentThreadDpiAwarenessContext` at `0x140174b14`
- `win32kbase!W32SetCurrentThreadDpiAwarenessContext` at `0x140174fb8`
- `win32kbase!W32SetCurrentThreadDpiAwarenessContext` at `0x140174635`
- `win32kbase!W32SetCurrentThreadDpiAwarenessContext` at `0x140174b14`
- `win32kbase!W32SetCurrentThreadDpiAwarenessContext` at `0x140174fb8`
- `win32kbase!UserDereferenceObject` at `0x14017432a`
- `win32kbase!UserSleep` at `0x140174d1e`
- `win32kbase!UserSleep` at `0x140174d1e`
- `win32kbase!HMChangeOwnerThread` at `0x140174aed`
- `win32kbase!HMChangeOwnerThread` at `0x140174b01`
- `win32kbase!HMChangeOwnerThread` at `0x140174aed`
- `win32kbase!HMChangeOwnerThread` at `0x140174b01`
- `win32kbase!SetHandleFlag` at `0x140174273`
- `win32kbase!SetHandleFlag` at `0x1401743be`
- `win32kbase!SetHandleFlag` at `0x140174f85`
- `win32kbase!SetHandleFlag` at `0x140174273`
- `win32kbase!SetHandleFlag` at `0x1401743be`
- `win32kbase!SetHandleFlag` at `0x140174f85`
- `win32kbase!IsImmersiveAppRestricted` at `0x1401746b8`
- `win32kbase!IsImmersiveAppRestricted` at `0x1401747d9`
- `win32kbase!IsImmersiveAppRestricted` at `0x1401746b8`
- `win32kbase!IsImmersiveAppRestricted` at `0x1401747d9`
- `win32kbase!DereferenceDwmApiPort` at `0x1401744fb`
- `win32kbase!DereferenceDwmApiPort` at `0x140175100`
- `win32kbase!DereferenceDwmApiPort` at `0x1401744fb`
- `win32kbase!DereferenceDwmApiPort` at `0x140175100`
- `win32kbase!HMAssignmentLock` at `0x14017495b`
- `win32kbase!HMAssignmentLock` at `0x140174993`
- `win32kbase!HMAssignmentLock` at `0x1401749f3`
- `win32kbase!HMAssignmentLock` at `0x140174a47`
- `win32kbase!HMAssignmentLock` at `0x14017495b`
- `win32kbase!HMAssignmentLock` at `0x140174993`
- `win32kbase!HMAssignmentLock` at `0x1401749f3`
- `win32kbase!HMAssignmentLock` at `0x140174a47`
- `win32kbase!HMAssignmentUnlock` at `0x140174a0f`
- `win32kbase!HMAssignmentUnlock` at `0x140174a99`
- `win32kbase!HMAssignmentUnlock` at `0x140174fdd`
- `win32kbase!HMAssignmentUnlock` at `0x14017500e`
- `win32kbase!HMAssignmentUnlock` at `0x140174a0f`
- `win32kbase!HMAssignmentUnlock` at `0x140174a99`
- `win32kbase!HMAssignmentUnlock` at `0x140174fdd`
- `win32kbase!HMAssignmentUnlock` at `0x14017500e`
- `win32kbase!ReferenceDwmApiPort` at `0x1401744aa`
- `win32kbase!ReferenceDwmApiPort` at `0x1401744d1`
- `win32kbase!ReferenceDwmApiPort` at `0x1401750be`
- `win32kbase!ReferenceDwmApiPort` at `0x1401750e6`
- `win32kbase!ReferenceDwmApiPort` at `0x1401744aa`
- `win32kbase!ReferenceDwmApiPort` at `0x1401744d1`
- `win32kbase!ReferenceDwmApiPort` at `0x1401750be`
- `win32kbase!ReferenceDwmApiPort` at `0x1401750e6`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401743ff`
- `WIN32K!W32GetUserGdiSessionState` at `0x140174431`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401743ff`
- `WIN32K!W32GetUserGdiSessionState` at `0x140174431`
- `WIN32K!W32GetUserSessionState` at `0x1401745dc`
- `WIN32K!W32GetUserSessionState` at `0x140174811`
- `WIN32K!W32GetUserSessionState` at `0x140174824`
- `WIN32K!W32GetUserSessionState` at `0x140174aa5`
- `WIN32K!W32GetUserSessionState` at `0x140174ac3`
- `WIN32K!W32GetUserSessionState` at `0x140174c06`
- `WIN32K!W32GetUserSessionState` at `0x140174c36`
- `WIN32K!W32GetUserSessionState` at `0x140174cb2`
- `WIN32K!W32GetUserSessionState` at `0x140174cc2`
- `WIN32K!W32GetUserSessionState` at `0x140174ce3`
- `WIN32K!W32GetUserSessionState` at `0x140174d2a`
- `WIN32K!W32GetUserSessionState` at `0x140174d6b`
- `WIN32K!W32GetUserSessionState` at `0x140174d89`
- `WIN32K!W32GetUserSessionState` at `0x140174dde`
- `WIN32K!W32GetUserSessionState` at `0x140174df7`
- `WIN32K!W32GetUserSessionState` at `0x140174e74`
- `WIN32K!W32GetUserSessionState` at `0x140174e99`
- `WIN32K!W32GetUserSessionState` at `0x140174f26`
- `WIN32K!W32GetUserSessionState` at `0x1401745dc`
- `WIN32K!W32GetUserSessionState` at `0x140174811`
- `WIN32K!W32GetUserSessionState` at `0x140174824`
- `WIN32K!W32GetUserSessionState` at `0x140174aa5`
- `WIN32K!W32GetUserSessionState` at `0x140174ac3`
- `WIN32K!W32GetUserSessionState` at `0x140174c06`
- `WIN32K!W32GetUserSessionState` at `0x140174c36`
- `WIN32K!W32GetUserSessionState` at `0x140174cb2`
- `WIN32K!W32GetUserSessionState` at `0x140174cc2`
- `WIN32K!W32GetUserSessionState` at `0x140174ce3`
- `WIN32K!W32GetUserSessionState` at `0x140174d2a`
- `WIN32K!W32GetUserSessionState` at `0x140174d6b`
- `WIN32K!W32GetUserSessionState` at `0x140174d89`
- `WIN32K!W32GetUserSessionState` at `0x140174dde`
- `WIN32K!W32GetUserSessionState` at `0x140174df7`
- `WIN32K!W32GetUserSessionState` at `0x140174e74`
- `WIN32K!W32GetUserSessionState` at `0x140174e99`
- `WIN32K!W32GetUserSessionState` at `0x140174f26`

## pseudocode

```c
__int64 __fastcall xxxCreateDesktopEx(__int64 a1, unsigned int a2, int a3, int a4, HANDLE *a5, int a6)
{
  struct tagWND *Window; // r13
  struct tagTHREADINFO *v10; // rsi
  __int64 v11; // r8
  int v12; // eax
  int v13; // ebx
  int v14; // r12d
  NTSTATUS v15; // eax
  __int64 v16; // r9
  char *v17; // r15
  struct tagWINDOWSTATION *v18; // rbx
  __int64 v19; // r12
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // rdi
  __int64 v24; // r8
  __int64 v25; // r9
  void *v26; // rax
  __int64 v27; // rcx
  __int64 UserSessionState; // rax
  int v29; // edi
  DWORD *PhysicalScreenRect; // rax
  DWORD v31; // r13d
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 CurrentProcessWin32Process; // rax
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 v38; // rdx
  __int64 v39; // rax
  __int64 v40; // rcx
  int v41; // edi
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // r8
  __int64 v45; // r9
  __int64 v46; // rax
  __int64 v47; // r8
  __int64 v48; // r9
  __int64 v49; // rdx
  __int64 v50; // rax
  __int64 v51; // rcx
  __int64 v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // r8
  __int64 v55; // r9
  int v56; // edi
  __int64 v57; // rdx
  __int64 v58; // rcx
  __int64 v59; // r8
  __int64 v60; // r9
  __int64 v61; // rax
  struct tagWND *v62; // rbx
  int v63; // ecx
  _QWORD *v64; // rdi
  __int64 v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // r8
  __int64 v68; // r9
  __int64 v69; // rdx
  __int64 v70; // rcx
  __int64 v71; // r8
  __int64 v72; // r9
  __int64 v73; // rdx
  volatile signed __int32 *v74; // rcx
  __int64 v75; // r8
  __int64 v76; // r9
  __int64 v77; // rax
  struct tagWINDOWSTATION *v78; // rdx
  __int64 v79; // rax
  __int64 v80; // rdx
  __int64 v81; // r8
  __int64 v82; // r9
  __int64 v83; // rdx
  __int64 v84; // rcx
  __int64 v85; // r8
  __int64 v86; // r9
  __int64 i; // rax
  __int64 v88; // rdx
  __int64 v89; // rcx
  __int64 v90; // r8
  __int64 v91; // r9
  __int64 v92; // rdx
  __int64 v93; // rcx
  __int64 v94; // r8
  __int64 v95; // r9
  __int64 v96; // rax
  __int64 v97; // rdx
  __int64 v98; // rcx
  __int64 v99; // r8
  __int64 v100; // r9
  void *v101; // rcx
  __int64 v102; // rdx
  __int64 v103; // rcx
  __int64 v104; // r8
  __int64 v105; // r9
  __int64 v106; // rdx
  __int64 v107; // rcx
  __int64 v108; // r8
  __int64 v109; // r9
  __int64 v110; // rdx
  __int64 v111; // rcx
  __int64 v112; // r8
  __int64 v113; // r9
  __int64 v114; // rax
  __int64 v115; // rdx
  __int64 v116; // rcx
  __int64 v117; // r8
  __int64 v118; // r9
  __int64 v119; // rax
  struct tagWND *v120; // rbx
  bool v121; // bl
  bool v122; // r12
  __int64 v123; // rax
  int v124; // r8d
  int v125; // edx
  _QWORD *v126; // rcx
  __int64 v127; // rdx
  __int64 v128; // rcx
  __int64 v129; // r8
  __int64 v130; // r12
  __int64 v131; // r8
  void *v132; // rax
  char v134; // [rsp+90h] [rbp-188h]
  bool v135; // [rsp+91h] [rbp-187h]
  DWORD v136; // [rsp+94h] [rbp-184h]
  int v137; // [rsp+94h] [rbp-184h]
  HANDLE Handle; // [rsp+98h] [rbp-180h] BYREF
  _BYTE v139[4]; // [rsp+A0h] [rbp-178h] BYREF
  unsigned int v140; // [rsp+A4h] [rbp-174h]
  union _LARGE_INTEGER Timeout[2]; // [rsp+B0h] [rbp-168h] BYREF
  struct tagWND *v142; // [rsp+C0h] [rbp-158h]
  BOOL v143; // [rsp+C8h] [rbp-150h]
  signed __int32 v144; // [rsp+CCh] [rbp-14Ch]
  int v145; // [rsp+D0h] [rbp-148h]
  _BYTE v146[16]; // [rsp+D8h] [rbp-140h] BYREF
  DWORD v147; // [rsp+E8h] [rbp-130h]
  __int64 v148; // [rsp+100h] [rbp-118h] BYREF
  struct tagWINDOWSTATION *v149; // [rsp+108h] [rbp-110h]
  PVOID Object; // [rsp+110h] [rbp-108h] BYREF
  _QWORD *v151; // [rsp+118h] [rbp-100h]
  __int64 v152; // [rsp+120h] [rbp-F8h]
  __int64 v153; // [rsp+128h] [rbp-F0h]
  __int64 v154; // [rsp+130h] [rbp-E8h]
  __int64 v155; // [rsp+138h] [rbp-E0h]
  ULONG_PTR BugCheckParameter3[2]; // [rsp+140h] [rbp-D8h] BYREF
  ULONG_PTR v157[2]; // [rsp+150h] [rbp-C8h] BYREF
  HWINSTA v158[2]; // [rsp+160h] [rbp-B8h] BYREF
  _BYTE v159[24]; // [rsp+170h] [rbp-A8h] BYREF
  _QWORD v160[5]; // [rsp+188h] [rbp-90h] BYREF
  int v161; // [rsp+1B0h] [rbp-68h]
  int v162; // [rsp+1B4h] [rbp-64h]
  _BYTE v163[16]; // [rsp+1B8h] [rbp-60h] BYREF
  HWINSTA v164; // [rsp+1C8h] [rbp-50h]
  _BYTE v165[32]; // [rsp+1D0h] [rbp-48h] BYREF

  Window = 0;
  Handle = 0;
  v148 = 0;
  v10 = PtiCurrent();
  Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(v157);
  Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(BugCheckParameter3);
  v158[0] = *(HWINSTA *)(a1 + 8);
  v164 = v158[0];
  LODWORD(v148) = W32GetCurrentWin32kSessionId();
  HIDWORD(v148) = a4;
  LOBYTE(v11) = a6 == 0;
  v12 = ObOpenObjectByName(a1, ExDesktopObjectType, v11, 0, a3, &v148, &Handle);
  v13 = v12;
  if ( v12 < 0 )
  {
    SetLastNtError((unsigned int)v12);
    CleanupDirtyDesktops();
LABEL_9:
    *a5 = 0;
    goto LABEL_126;
  }
  v14 = 0;
  if ( v12 == 0x40000000 )
  {
    if ( !(unsigned int)SetHandleFlag(Handle, 1, 1) )
    {
      SetLastNtError(3221225495LL);
      CloseProtectedHandle(Handle);
      v13 = -1073741801;
      goto LABEL_9;
    }
    *a5 = Handle;
    v14 = 1;
  }
  Object = 0;
  v15 = ObReferenceObjectByHandle(Handle, 0, (POBJECT_TYPE)ExDesktopObjectType, 1, &Object, 0);
  v13 = v15;
  if ( v15 < 0 )
  {
    SetLastNtError((unsigned int)v15);
    CloseProtectedHandle(Handle);
    goto LABEL_9;
  }
  v17 = (char *)Object;
  Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>::Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>(
    v159,
    Object,
    UserDereferenceObject,
    v16);
  if ( v14 )
  {
    v13 = OpenDesktopCompletion(v17, Handle, a2);
    if ( v13 >= 0 )
    {
LABEL_14:
      Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>::~Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>(v159);
      goto LABEL_126;
    }
    CloseProtectedHandle(Handle);
LABEL_13:
    *a5 = 0;
    goto LABEL_14;
  }
  v18 = (struct tagWINDOWSTATION *)*((_QWORD *)v17 + 5);
  v149 = v18;
  v19 = *((_QWORD *)v18 + 3);
  v151 = (_QWORD *)*((_QWORD *)v17 + 1);
  v151[22] = 0;
  if ( !(unsigned int)SetHandleFlag(Handle, 0, a2 & 1) )
  {
    CloseProtectedHandle(Handle);
    *a5 = 0;
    Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>::~Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>(v159);
    v13 = -1073741801;
    goto LABEL_126;
  }
  if ( *(_QWORD *)(W32GetUserGdiSessionState() + 40) )
  {
    v160[0] = 0;
    v160[1] = 0;
    v160[2] = 1;
    v160[3] = *(_QWORD *)(W32GetUserGdiSessionState() + 40);
    v160[4] = v17;
    v161 = 0;
    v162 = 1;
    v13 = MapDesktop(v160);
    if ( v13 < 0 )
    {
      CloseProtectedHandle(Handle);
      SetLastNtError(3221225506LL);
      goto LABEL_13;
    }
    v18 = v149;
  }
  v142 = 0;
  v145 = 0;
  v23 = ReferenceDwmApiPort(v21, v20, v22);
  if ( v23 )
  {
    if ( (*((_DWORD *)v18 + 8) & 0x200) != 0 )
    {
      v26 = (void *)ReferenceDwmApiPort(*((_QWORD *)v17 + 1), **((_QWORD **)v17 + 1), v24);
      DwmAsyncDesktopCreate(v26);
      zzzComposeDesktop((struct tagDESKTOP *)v17);
      v145 = 1;
    }
    DereferenceDwmApiPort(v23);
  }
  v152 = *((_QWORD *)v10 + 57);
  v155 = *(_QWORD *)(v152 + 344);
  v144 = _InterlockedCompareExchange((volatile signed __int32 *)v10 + 130, 0, 0) & 0x20000000;
  v135 = v144 != 0;
  v27 = *(_QWORD *)(*(_QWORD *)(v19 + 16) + 456LL);
  *((_QWORD *)v10 + 57) = v27;
  if ( (*(_DWORD *)(v27 + 12) & 0x2000000) != 0 )
    _InterlockedOr((volatile signed __int32 *)v10 + 130, 0x20000000u);
  else
    _InterlockedAnd((volatile signed __int32 *)v10 + 130, 0xDFFFFFFF);
  v143 = (_InterlockedCompareExchange((volatile signed __int32 *)v10 + 130, 0, 0) & 0x20000000) != 0;
  if ( (_InterlockedCompareExchange((volatile signed __int32 *)v10 + 130, 0, 0) & 0x10000000) != 0 )
  {
    v134 = 0;
  }
  else
  {
    v134 = 1;
    _InterlockedOr((volatile signed __int32 *)v10 + 130, 0x10000000u);
  }
  v154 = *((_QWORD *)v10 + 61);
  v153 = *((_QWORD *)v10 + 78);
  UserSessionState = W32GetUserSessionState(0x10000000, 0x20000000, v24, v25);
  ++*(_DWORD *)(UserSessionState + 70592);
  AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)v146);
  v29 = zzzSetDesktop(v10, v17, Handle);
  if ( v29 < 0 )
  {
    v140 = 0;
    goto LABEL_33;
  }
  v140 = W32SetCurrentThreadDpiAwarenessContext(18);
  PhysicalScreenRect = (DWORD *)GetPhysicalScreenRect(v163);
  Timeout[0].LowPart = *PhysicalScreenRect;
  v136 = PhysicalScreenRect[1];
  v147 = PhysicalScreenRect[2];
  v31 = PhysicalScreenRect[3];
  CurrentProcessWin32Process = PsGetCurrentProcessWin32Process(v147, v32, v33, v34);
  if ( !CurrentProcessWin32Process )
    goto LABEL_40;
  v38 = -(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0);
  if ( (v38 & CurrentProcessWin32Process) == 0 )
    goto LABEL_40;
  v39 = PsGetCurrentProcessWin32Process(-*(_QWORD *)CurrentProcessWin32Process, v38, v36, v37);
  v40 = v39;
  if ( v39 )
    v40 = ((unsigned __int128)-(__int128)*(unsigned __int64 *)v39 >> 64) & v39;
  if ( (unsigned int)IsImmersiveAppRestricted(v40) )
    v41 = 1;
  else
LABEL_40:
    v41 = 0;
  SmartObjStackRef<tagMENU>::SmartObjStackRef<tagMENU>(v165, 0);
  Window = (struct tagWND *)xxxCreateWindowEx(
                              0,
                              32769,
                              32769,
                              0,
                              -2113929216,
                              Timeout[0].LowPart,
                              v136,
                              v147 - Timeout[0].LowPart,
                              v31 - v136,
                              0,
                              (__int64)v165,
                              (__int64)hModuleWin,
                              0,
                              1,
                              778,
                              v41,
                              0);
  SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(v165);
  if ( !Window )
    goto LABEL_42;
  Win32HMThreadLockBase<tagMENU,1,1>::ManualLock<void>(v157, Window);
  v46 = PsGetCurrentProcessWin32Process(v43, v42, v44, v45);
  if ( !v46 )
    goto LABEL_48;
  v49 = -(__int64)(*(_QWORD *)v46 != 0);
  if ( (v49 & v46) == 0 )
    goto LABEL_48;
  v50 = PsGetCurrentProcessWin32Process(-*(_QWORD *)v46, v49, v47, v48);
  v51 = v50;
  if ( v50 )
    v51 = ((unsigned __int128)-(__int128)*(unsigned __int64 *)v50 >> 64) & v50;
  v137 = 1;
  if ( !(unsigned int)IsImmersiveAppRestricted(v51) )
LABEL_48:
    v137 = 0;
  SmartObjStackRef<tagMENU>::SmartObjStackRef<tagMENU>(v160, 0);
  v56 = *(unsigned __int16 *)(W32GetUserSessionState(v53, v52, v54, v55) + 41168);
  v61 = W32GetUserSessionState(v58, v57, v59, v60);
  v62 = (struct tagWND *)xxxCreateWindowEx(
                           0,
                           *(unsigned __int16 *)(v61 + 41168),
                           v56,
                           0,
                           -2113929216,
                           0,
                           0,
                           100,
                           100,
                           0,
                           (__int64)v160,
                           (__int64)hModuleWin,
                           0,
                           1,
                           778,
                           v137,
                           0);
  v142 = v62;
  SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(v160);
  if ( !v62 )
  {
LABEL_42:
    v29 = -1073741801;
    goto LABEL_33;
  }
  v63 = *(unsigned __int16 *)(*((_QWORD *)v62 + 5) + 42LL);
  if ( (v63 & 0xFFFF3FFF) != 0 )
  {
    if ( (v63 & 0x1000) != 0 )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 2345);
    v29 = -1073741790;
  }
  else
  {
    Win32HMThreadLockBase<tagMENU,1,1>::ManualLock<void>(BugCheckParameter3, v62);
    *(_WORD *)(*((_QWORD *)v62 + 5) + 42LL) = *(_WORD *)(*((_QWORD *)v62 + 5) + 42LL) & 0xC000 | 0x29F;
    v64 = v151 + 3;
    *(_QWORD *)(*v151 + 8LL) = *((_QWORD *)Window + 6);
    Timeout[0].QuadPart = (LONGLONG)v64;
    Timeout[1].QuadPart = (LONGLONG)Window;
    HMAssignmentLock(Timeout, 0);
    *(_OWORD *)&Timeout[0].LowPart = *(_OWORD *)LockPointer(v163, (char *)v62 + 104, *(_QWORD *)(v19 + 8));
    HMAssignmentLock(Timeout, 0);
    AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)Timeout);
    xxxInheritWindowMonitor(v62);
    AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)Timeout);
    LinkWindow(v62);
    Timeout[0].QuadPart = (LONGLONG)(v17 + 112);
    Timeout[1].QuadPart = (LONGLONG)v62;
    HMAssignmentLock(Timeout, 0);
    *(_QWORD *)(*((_QWORD *)v62 + 5) + 64LL) = 0;
    HMAssignmentUnlock((char *)v62 + 120);
    *(_OWORD *)&Timeout[0].LowPart = *(_OWORD *)LockPointer(v163, (char *)Window + 104, *(_QWORD *)(v19 + 8));
    HMAssignmentLock(Timeout, 0);
    AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)Timeout);
    xxxInheritWindowMonitor(Window);
    AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)Timeout);
    LinkWindow(Window);
    *(_QWORD *)(*((_QWORD *)Window + 5) + 64LL) = 0;
    HMAssignmentUnlock((char *)Window + 120);
    v69 = *(_QWORD *)(W32GetUserSessionState(v66, v65, v67, v68) + 56744);
    if ( (*(_DWORD *)(v69 + 132) & 1) == 0 )
      *(_QWORD *)(*((_QWORD *)Window + 5) + 168LL) = *(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v70, v69, v71, v72)
                                                                           + 56744)
                                                               + 120LL);
    HMChangeOwnerThread(*v64, *(_QWORD *)(v19 + 16));
    HMChangeOwnerThread(v62, *(_QWORD *)(v19 + 16));
    W32SetCurrentThreadDpiAwarenessContext(v140);
    v140 = 0;
    *((_QWORD *)v10 + 57) = v152;
    if ( (_InterlockedCompareExchange((volatile signed __int32 *)v10 + 130, 0, 0) & 0x10000000) == 0 )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 2417);
    if ( v134 )
      _InterlockedAnd((volatile signed __int32 *)v10 + 130, 0xEFFFFFFF);
    if ( v143 != v135 )
    {
      if ( v144 )
        _InterlockedOr((volatile signed __int32 *)v10 + 130, 0x20000000u);
      else
        _InterlockedAnd((volatile signed __int32 *)v10 + 130, 0xDFFFFFFF);
    }
    v29 = zzzSetDesktop(v10, v154, v153);
    if ( v29 >= 0 )
    {
      AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v146);
      EditionEndDeferWinEventNotify();
      if ( *(_QWORD *)(v19 + 56) )
      {
        if ( (*(_DWORD *)v19 & 2) != 0 )
        {
          v79 = W32GetUserSessionState(v74, v73, v75, v76);
          ++*(_DWORD *)(v79 + 70592);
          AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)v146);
          v29 = zzzSetDesktop(*(_QWORD *)(v19 + 16), v17, 0);
          if ( v29 < 0 )
            goto LABEL_33;
          AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v146);
          EditionEndDeferWinEventNotify();
        }
        else
        {
          v77 = W32GetUserSessionState(v74, v73, v75, v76);
          v78 = v149;
          *(_QWORD *)(*(_QWORD *)(v77 + 18752) + 648LL) = v149;
          *(_QWORD *)(*(_QWORD *)(v19 + 16) + 648LL) = v78;
        }
        KeSetEvent(*(PRKEVENT *)(v19 + 56), 1, 0);
        if ( (*(_DWORD *)v19 & 2) == 0 )
        {
          LeaveEnterCrit::LeaveEnterCrit((LeaveEnterCrit *)v139);
          for ( i = W32GetUserSessionState(v84, v83, v85, v86);
                !*(_QWORD *)(i + 19216);
                i = W32GetUserSessionState(v98, v97, v99, v100) )
          {
            if ( *(_QWORD *)(W32GetUserSessionState(v89, v88, v90, v91) + 62736) )
            {
              Timeout[0].QuadPart = -200000;
              v96 = W32GetUserSessionState(v93, v92, v94, v95);
              KeWaitForSingleObject(*(PVOID *)(v96 + 62736), Executive, 0, 0, Timeout);
            }
            else
            {
              UserSleep(20);
            }
          }
          LeaveEnterCrit::~LeaveEnterCrit((LeaveEnterCrit *)v139);
        }
        v101 = *(void **)(v19 + 56);
        if ( v101 )
        {
          ObfDereferenceObject(v101);
          *(_QWORD *)(v19 + 56) = 0;
        }
        v74 = *(volatile signed __int32 **)(W32GetUserSessionState(v101, v80, v81, v82) + 19704);
        _InterlockedOr(v74, 0x800u);
      }
      if ( v19 == W32GetUserSessionState(v74, v73, v75, v76) + 68448 )
        xxxSetWindowPos(Window, 0, 0, 1115);
      if ( !v155 )
        DeferrableUnlockObjectAssignment<tagDESKTOP>(*((_QWORD *)v10 + 57) + 344LL);
      if ( !*(_QWORD *)(W32GetUserSessionState(v103, v102, v104, v105) + 62752)
        && v17 == *(char **)(W32GetUserSessionState(v107, v106, v108, v109) + 62744) )
      {
        if ( !xxxCreateDisconnectDesktop(v158[0], v149) )
        {
          Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)BugCheckParameter3);
          Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)v157);
          CloseDesktop(Handle);
          *a5 = 0;
          Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>::~Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>(v159);
          v13 = -1073741823;
          goto LABEL_126;
        }
        v114 = W32GetUserSessionState(v111, v110, v112, v113);
        KeSetEvent(*(PRKEVENT *)(v114 + 62576), 1, 0);
        v119 = W32GetUserSessionState(v116, v115, v117, v118);
        *(_DWORD *)(v119 + 68920) |= 0x40000u;
      }
      v120 = v142;
      goto LABEL_91;
    }
  }
LABEL_33:
  AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v146);
  while ( 1 )
  {
    AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)v146);
    if ( v140 )
      W32SetCurrentThreadDpiAwarenessContext(v140);
    v120 = v142;
    if ( v142 )
    {
      xxxDestroyWindow(v142);
      HMAssignmentUnlock(v17 + 112);
    }
    if ( Window )
    {
      xxxDestroyWindow(Window);
      v126 = v151 + 3;
      *(_QWORD *)(*v151 + 8LL) = 0;
      HMAssignmentUnlock(v126);
    }
    *((_QWORD *)v10 + 57) = v152;
    if ( v134 )
      _InterlockedAnd((volatile signed __int32 *)v10 + 130, 0xEFFFFFFF);
    if ( v143 != v135 )
    {
      if ( v144 )
        _InterlockedOr((volatile signed __int32 *)v10 + 130, 0x20000000u);
      else
        _InterlockedAnd((volatile signed __int32 *)v10 + 130, 0xDFFFFFFF);
    }
    AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v146);
    EditionEndDeferWinEventNotify();
    AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)v158);
    zzzSetDesktop(v10, v154, v153);
    AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v158);
    if ( v145 )
    {
      v130 = ReferenceDwmApiPort(v128, v127, v129);
      if ( v130 )
      {
        zzzDecomposeDesktop((struct tagDESKTOP *)v17);
        v132 = (void *)ReferenceDwmApiPort(*((_QWORD *)v17 + 1), **((_QWORD **)v17 + 1), v131);
        DwmAsyncDesktopFree(v132);
        DereferenceDwmApiPort(v130);
        v120 = v142;
      }
    }
    CloseProtectedHandle(Handle);
    Handle = 0;
    if ( !v155 )
      DeferrableUnlockObjectAssignment<tagDESKTOP>(*((_QWORD *)v10 + 57) + 344LL);
LABEL_91:
    if ( v120 )
      v142 = (struct tagWND *)Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)BugCheckParameter3);
    if ( Window )
      Window = (struct tagWND *)Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>((ULONG_PTR)v157);
    v121 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v122 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v121 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v123 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, v106, v108, v109);
      LOBYTE(v124) = v122;
      LOBYTE(v125) = v121;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v125,
        v124,
        *(_QWORD *)(v123 + 69152),
        4,
        3,
        24,
        (__int64)WPP_8482796ea87931402564603ebe19074e_Traceguids);
    }
    if ( !Handle || (unsigned int)SetHandleFlag(Handle, 1, 1) )
      break;
    v29 = -1073741801;
  }
  if ( v29 >= 0 )
    *((_DWORD *)v17 + 12) |= 0x10u;
  *a5 = Handle;
  Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>::~Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>(v159);
  v13 = v29;
LABEL_126:
  Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)BugCheckParameter3);
  Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)v157);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140174168  mov     rax, rsp
0x14017416b  mov     [rax+10h], rbx
0x14017416f  mov     [rax+18h], rsi
0x140174173  mov     [rax+8], rcx
0x140174177  push    rdi
0x140174178  push    r12
0x14017417a  push    r13
0x14017417c  push    r14
0x14017417e  push    r15
0x140174180  sub     rsp, 1F0h
0x140174187  mov     ebx, r9d
0x14017418a  mov     r14d, r8d
0x14017418d  mov     edi, edx
0x14017418f  xor     r13d, r13d
0x140174192  mov     [rax-180h], r13
0x140174199  mov     [rax-118h], r13
0x1401741a0  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401741a5  mov     rsi, rax
0x1401741a8  lea     rcx, [rsp+218h+var_C8]
0x1401741b0  call    ??0?$Win32HMOptionalThreadLockAlways@UtagMENU@@@@QEAA@XZ; Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(void)
0x1401741b5  lea     rcx, [rsp+218h+BugCheckParameter3]
0x1401741bd  call    ??0?$Win32HMOptionalThreadLockAlways@UtagMENU@@@@QEAA@XZ; Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(void)
0x1401741c2  nop
0x1401741c3  mov     rax, [rsp+218h+arg_0]
0x1401741cb  mov     rax, [rax+8]
0x1401741cf  mov     [rsp+218h+var_B8], rax
0x1401741d7  mov     [rsp+218h+var_50], rax
0x1401741df  call    W32GetCurrentWin32kSessionId
0x1401741e4  mov     [rsp+218h+var_118], eax
0x1401741eb  mov     [rsp+218h+var_114], ebx
0x1401741f2  mov     rax, cs:ExDesktopObjectType
0x1401741f9  mov     rdx, [rax]
0x1401741fc  cmp     [rsp+218h+arg_28], r13d
0x140174204  setz    r8b
0x140174208  lea     rax, [rsp+218h+Handle]
0x140174210  mov     qword ptr [rsp+218h+var_1E8], rax
0x140174215  lea     rax, [rsp+218h+var_118]
0x14017421d  mov     [rsp+218h+HandleInformation], rax
0x140174222  mov     dword ptr [rsp+218h+Object], r14d
0x140174227  xor     r9d, r9d
0x14017422a  mov     rcx, [rsp+218h+arg_0]
0x140174232  call    cs:__imp_ObOpenObjectByName
0x140174239  nop     dword ptr [rax+rax+00h]
0x14017423e  mov     ebx, eax
0x140174240  test    eax, eax
0x140174242  jns     short loc_140174255
0x140174244  mov     ecx, eax
0x140174246  call    SetLastNtError
0x14017424b  call    ?CleanupDirtyDesktops@@YAXXZ; CleanupDirtyDesktops(void)
0x140174250  jmp     loc_140174312
0x140174255  mov     r12d, r13d
0x140174258  mov     r14d, 1
0x14017425e  cmp     eax, 40000000h
0x140174263  jnz     short loc_1401742B9
0x140174265  mov     r8d, r14d
0x140174268  mov     edx, r14d
0x14017426b  mov     rcx, [rsp+218h+Handle]
0x140174273  call    cs:__imp_SetHandleFlag
0x14017427a  nop     dword ptr [rax+rax+00h]
0x14017427f  test    eax, eax
0x140174281  jnz     short loc_1401742A3
0x140174283  mov     ecx, 0C0000017h
0x140174288  call    SetLastNtError
0x14017428d  xor     edx, edx
0x14017428f  mov     rcx, [rsp+218h+Handle]; Handle
0x140174297  call    CloseProtectedHandle
0x14017429c  mov     ebx, 0C0000017h
0x1401742a1  jmp     short loc_140174312
0x1401742a3  mov     rcx, [rsp+218h+Handle]
0x1401742ab  mov     rax, [rsp+218h+arg_20]
0x1401742b3  mov     [rax], rcx
0x1401742b6  mov     r12d, r14d
0x1401742b9  mov     [rsp+218h+var_108], r13
0x1401742c1  mov     [rsp+218h+HandleInformation], r13; HandleInformation
0x1401742c6  lea     rax, [rsp+218h+var_108]
0x1401742ce  mov     [rsp+218h+Object], rax; Object
0x1401742d3  mov     r9b, r14b; AccessMode
0x1401742d6  mov     r8, cs:ExDesktopObjectType
0x1401742dd  mov     r8, [r8]; ObjectType
0x1401742e0  xor     edx, edx; DesiredAccess
0x1401742e2  mov     rcx, [rsp+218h+Handle]; Handle
0x1401742ea  call    cs:__imp_ObReferenceObjectByHandle
0x1401742f1  nop     dword ptr [rax+rax+00h]
0x1401742f6  mov     ebx, eax
0x1401742f8  test    eax, eax
0x1401742fa  jns     short loc_140174322
0x1401742fc  mov     ecx, eax
0x1401742fe  call    SetLastNtError
0x140174303  xor     edx, edx
0x140174305  mov     rcx, [rsp+218h+Handle]; Handle
0x14017430d  call    CloseProtectedHandle
0x140174312  mov     rax, [rsp+218h+arg_20]
0x14017431a  mov     [rax], r13
0x14017431d  jmp     loc_140175181
0x140174322  mov     r15, [rsp+218h+var_108]
0x14017432a  mov     r8, cs:__imp_UserDereferenceObject
0x140174331  mov     rdx, r15
0x140174334  lea     rcx, [rsp+218h+var_A8]
0x14017433c  call    ??0?$Win32RawLockedItemNoCleanup@U_ACCESS_ALLOWED_ACE@@$0A@@@QEAA@PEAU_ACCESS_ALLOWED_ACE@@P6AXPEAX@Z@Z; Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>::Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>(_ACCESS_ALLOWED_ACE *,void (*)(void *))
0x140174341  test    r12d, r12d
0x140174344  jz      short loc_14017438B
0x140174346  mov     r8d, edi
0x140174349  mov     rdx, [rsp+218h+Handle]
0x140174351  mov     rcx, r15
0x140174354  call    OpenDesktopCompletion
0x140174359  mov     ebx, eax
0x14017435b  test    eax, eax
0x14017435d  jns     short loc_140174379
0x14017435f  xor     edx, edx
0x140174361  mov     rcx, [rsp+218h+Handle]; Handle
0x140174369  call    CloseProtectedHandle
0x14017436e  mov     rcx, [rsp+218h+arg_20]
0x140174376  mov     [rcx], r13
0x140174379  lea     rcx, [rsp+218h+var_A8]
0x140174381  call    ??1?$Win32RawLockedItem@UtagEVENT_PACKET_TARGETS@@$0A@@@QEAA@XZ; Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>::~Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>(void)
0x140174386  jmp     loc_140175181
0x14017438b  mov     rbx, [r15+28h]
0x14017438f  mov     [rsp+218h+var_110], rbx
0x140174397  mov     r12, [rbx+18h]
0x14017439b  mov     rax, [r15+8]
0x14017439f  mov     [rsp+218h+var_100], rax
0x1401743a7  mov     [rax+0B0h], r13
0x1401743ae  and     edi, r14d
0x1401743b1  mov     r8d, edi
0x1401743b4  xor     edx, edx
0x1401743b6  mov     rcx, [rsp+218h+Handle]
0x1401743be  call    cs:__imp_SetHandleFlag
0x1401743c5  nop     dword ptr [rax+rax+00h]
0x1401743ca  test    eax, eax
0x1401743cc  jnz     short loc_1401743FF
0x1401743ce  xor     edx, edx
0x1401743d0  mov     rcx, [rsp+218h+Handle]; Handle
0x1401743d8  call    CloseProtectedHandle
0x1401743dd  mov     rax, [rsp+218h+arg_20]
0x1401743e5  mov     [rax], r13
0x1401743e8  lea     rcx, [rsp+218h+var_A8]
0x1401743f0  call    ??1?$Win32RawLockedItem@UtagEVENT_PACKET_TARGETS@@$0A@@@QEAA@XZ; Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>::~Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>(void)
0x1401743f5  mov     ebx, 0C0000017h
0x1401743fa  jmp     loc_140175181
0x1401743ff  call    cs:__imp_W32GetUserGdiSessionState
0x140174406  nop     dword ptr [rax+rax+00h]
0x14017440b  cmp     [rax+28h], r13
0x14017440f  jz      loc_14017449A
0x140174415  mov     [rsp+218h+var_90], r13
0x14017441d  mov     [rsp+218h+var_88], r13
0x140174425  mov     [rsp+218h+var_80], 1
0x140174431  call    cs:__imp_W32GetUserGdiSessionState
0x140174438  nop     dword ptr [rax+rax+00h]
0x14017443d  mov     rcx, [rax+28h]
0x140174441  mov     [rsp+218h+var_78], rcx
0x140174449  mov     [rsp+218h+var_70], r15
0x140174451  mov     [rsp+218h+var_68], r13d
0x140174459  mov     [rsp+218h+var_64], r14d
0x140174461  lea     rcx, [rsp+218h+var_90]
0x140174469  call    MapDesktop
0x14017446e  mov     ebx, eax
0x140174470  test    eax, eax
0x140174472  jns     short loc_140174492
0x140174474  xor     edx, edx
0x140174476  mov     rcx, [rsp+218h+Handle]; Handle
0x14017447e  call    CloseProtectedHandle
0x140174483  mov     ecx, 0C0000022h
0x140174488  call    SetLastNtError
0x14017448d  jmp     loc_14017436E
0x140174492  mov     rbx, [rsp+218h+var_110]
0x14017449a  mov     [rsp+218h+var_158], r13
0x1401744a2  mov     [rsp+218h+var_148], r13d
0x1401744aa  call    cs:__imp_ReferenceDwmApiPort
0x1401744b1  nop     dword ptr [rax+rax+00h]
0x1401744b6  mov     rdi, rax
0x1401744b9  test    rax, rax
0x1401744bc  jz      short loc_140174507
0x1401744be  test    dword ptr [rbx+20h], 200h
0x1401744c5  jz      short loc_1401744F8
0x1401744c7  mov     rcx, [r15+8]
0x1401744cb  mov     rdx, [rcx]
0x1401744ce  mov     rbx, [rdx]
0x1401744d1  call    cs:__imp_ReferenceDwmApiPort
0x1401744d8  nop     dword ptr [rax+rax+00h]
0x1401744dd  mov     rdx, rbx
0x1401744e0  mov     rcx, rax; Object
0x1401744e3  call    DwmAsyncDesktopCreate
0x1401744e8  mov     rcx, r15; struct tagDESKTOP *
0x1401744eb  call    zzzComposeDesktop
0x1401744f0  mov     [rsp+218h+var_148], r14d
0x1401744f8  mov     rcx, rdi
0x1401744fb  call    cs:__imp_DereferenceDwmApiPort
0x140174502  nop     dword ptr [rax+rax+00h]
0x140174507  mov     rax, [rsi+1C8h]
0x14017450e  mov     [rsp+218h+var_F8], rax
0x140174516  mov     rax, [rax+158h]
0x14017451d  mov     [rsp+218h+var_E0], rax
0x140174525  mov     ecx, r13d
0x140174528  xor     eax, eax
0x14017452a  lock cmpxchg [rsi+208h], ecx
0x140174532  mov     edx, 20000000h
0x140174537  and     eax, edx
0x140174539  mov     [rsp+218h+var_14C], eax
0x140174540  setnz   [rsp+218h+var_187]
0x140174548  mov     rcx, [r12+10h]
0x14017454d  mov     rcx, [rcx+1C8h]
0x140174554  mov     [rsi+1C8h], rcx
0x14017455b  test    dword ptr [rcx+0Ch], 2000000h
0x140174562  jz      short loc_14017456D
0x140174564  lock or [rsi+208h], edx
0x14017456b  jmp     short loc_140174578
0x14017456d  lock and dword ptr [rsi+208h], 0DFFFFFFFh
0x140174578  mov     ecx, r13d
0x14017457b  xor     eax, eax
0x14017457d  lock cmpxchg [rsi+208h], ecx
0x140174585  shr     eax, 1Dh
0x140174588  and     al, r14b
0x14017458b  mov     [rsp+218h+var_150], eax
0x140174592  xor     eax, eax
0x140174594  lock cmpxchg [rsi+208h], ecx
0x14017459c  mov     ecx, 10000000h
0x1401745a1  test    ecx, eax
0x1401745a3  jnz     short loc_1401745B6
0x1401745a5  mov     [rsp+218h+var_188], r14b
0x1401745ad  lock or [rsi+208h], ecx
0x1401745b4  jmp     short loc_1401745BE
0x1401745b6  mov     [rsp+218h+var_188], r13b
0x1401745be  mov     rax, [rsi+1E8h]
0x1401745c5  mov     [rsp+218h+var_E8], rax
0x1401745cd  mov     rax, [rsi+270h]
0x1401745d4  mov     [rsp+218h+var_F0], rax
0x1401745dc  call    cs:__imp_W32GetUserSessionState
0x1401745e3  nop     dword ptr [rax+rax+00h]
0x1401745e8  add     [rax+113C0h], r14d
0x1401745ef  lea     rcx, [rsp+218h+var_140]; this
0x1401745f7  call    ??0AtomicExecutionCheck@@QEAA@XZ; AtomicExecutionCheck::AtomicExecutionCheck(void)
0x1401745fc  mov     r8, [rsp+218h+Handle]
0x140174604  mov     rdx, r15
0x140174607  mov     rcx, rsi
0x14017460a  call    zzzSetDesktop
0x14017460f  mov     edi, eax
0x140174611  test    eax, eax
0x140174613  jns     short loc_140174630
0x140174615  xor     ecx, ecx
0x140174617  mov     [rsp+218h+var_174], ecx
0x14017461e  lea     rcx, [rsp+218h+var_140]; this
0x140174626  call    ?Disarm@AtomicExecutionCheck@@QEAAXXZ; AtomicExecutionCheck::Disarm(void)
0x14017462b  jmp     loc_140174F9E
0x140174630  mov     ecx, 12h
0x140174635  call    cs:__imp_W32SetCurrentThreadDpiAwarenessContext
0x14017463c  nop     dword ptr [rax+rax+00h]
0x140174641  mov     [rsp+218h+var_174], eax
0x140174648  lea     rcx, [rsp+218h+var_60]
0x140174650  call    GetPhysicalScreenRect
0x140174655  mov     ecx, [rax]
0x140174657  mov     dword ptr [rsp+218h+Timeout], ecx
0x14017465e  mov     ecx, [rax+4]
0x140174661  mov     [rsp+218h+var_184], ecx
0x140174668  mov     ecx, [rax+8]
0x14017466b  mov     [rsp+218h+var_130], ecx
0x140174672  mov     r13d, [rax+0Ch]
0x140174676  call    cs:__imp_PsGetCurrentProcessWin32Process
0x14017467d  nop     dword ptr [rax+rax+00h]
0x140174682  test    rax, rax
0x140174685  jz      short loc_1401746CD
0x140174687  mov     rcx, [rax]
0x14017468a  neg     rcx
0x14017468d  sbb     rdx, rdx
0x140174690  and     rax, rdx
0x140174693  test    rax, rax
0x140174696  jz      short loc_1401746CD
0x140174698  call    cs:__imp_PsGetCurrentProcessWin32Process
0x14017469f  nop     dword ptr [rax+rax+00h]
0x1401746a4  mov     rcx, rax
0x1401746a7  test    rax, rax
0x1401746aa  jz      short loc_1401746B8
0x1401746ac  mov     rax, [rax]
0x1401746af  neg     rax
0x1401746b2  sbb     rdx, rdx
0x1401746b5  and     rcx, rdx
0x1401746b8  call    cs:__imp_IsImmersiveAppRestricted
0x1401746bf  nop     dword ptr [rax+rax+00h]
0x1401746c4  test    eax, eax
0x1401746c6  jz      short loc_1401746CD
0x1401746c8  mov     edi, r14d
0x1401746cb  jmp     short loc_1401746CF
0x1401746cd  xor     edi, edi
0x1401746cf  mov     rax, cs:__imp_?hModuleWin@@3PEAXEA; void * hModuleWin
0x1401746d6  mov     rbx, [rax]
0x1401746d9  xor     edx, edx
0x1401746db  lea     rcx, [rsp+218h+var_48]
0x1401746e3  call    ??0?$SmartObjStackRef@UtagMENU@@@@QEAA@H@Z; SmartObjStackRef<tagMENU>::SmartObjStackRef<tagMENU>(int)
0x1401746e8  mov     edx, [rsp+218h+var_184]
0x1401746ef  sub     r13d, edx
0x1401746f2  mov     eax, [rsp+218h+var_130]
0x1401746f9  mov     ecx, dword ptr [rsp+218h+Timeout]
0x140174700  sub     eax, ecx
0x140174702  mov     [rsp+218h+var_198], 0
0x14017470e  mov     [rsp+218h+var_1A0], edi
0x140174712  mov     [rsp+218h+var_1A8], 30Ah
0x14017471a  mov     [rsp+218h+var_1B0], r14d
0x14017471f  xor     edi, edi
0x140174721  mov     [rsp+218h+var_1B8], rdi
0x140174726  mov     [rsp+218h+var_1C0], rbx
0x14017472b  lea     r8, [rsp+218h+var_48]
  ... truncated ...
```
