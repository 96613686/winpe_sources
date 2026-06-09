# xxxCreateDesktopEx

- ea: `0x1400b66fc`
- end: `0x1400b777f`
- name: `xxxCreateDesktopEx`
- size: `4227`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, int, HANDLE *, int)`
- caller_count: `4`
- callee_count: `38`
- tags: `broker_com_uri`

## callers

- `0x1400b59e4`
- `0x1400b604c`
- `0x1401d5de0`
- `0x1402b7910`

## callees

- `0x140005a18`
- `0x14000a3ec`
- `0x1400114a4`
- `0x1400138bc`
- `0x140026568`
- `0x140032d50`
- `0x1400330e0`
- `0x140033b58`
- `0x140033e08`
- `0x140035d14`
- `0x140049df8`
- `0x140086f20`
- `0x140097650`
- `0x1400a4a38`
- `0x1400b59e4`
- `0x1400b5e78`
- `0x1400b5ffc`
- `0x1400b6698`
- `0x1400b66fc`
- `0x1400d75c4`
- `0x1400d7658`
- `0x1400da070`
- `0x1400dd43c`
- `0x1400e2cb0`
- `0x1400e453c`
- `0x1400e73e8`
- `0x1400e8c74`
- `0x1400e8f88`
- `0x1401219dc`
- `0x14013f4b4`
- `0x14018ad70`
- `0x1401e09d8`
- `0x140214aac`
- `0x140249ab0`
- `0x1402938dc`
- `0x1402968e4`
- `0x14029a8e8`
- `0x1402a71e8`

## import_xrefs

- `ntoskrnl!ObOpenObjectByName` at `0x1400b67c6`
- `ntoskrnl!ObOpenObjectByName` at `0x1400b67c6`
- `ntoskrnl!KeSetEvent` at `0x1400b7221`
- `ntoskrnl!KeSetEvent` at `0x1400b7421`
- `ntoskrnl!KeSetEvent` at `0x1400b7221`
- `ntoskrnl!KeSetEvent` at `0x1400b7421`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b729f`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b729f`
- `ntoskrnl!ExDesktopObjectType` at `0x1400b6786`
- `ntoskrnl!ExDesktopObjectType` at `0x1400b686a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400b687e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400b687e`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400b6c0a`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400b6c2c`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400b6d2b`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400b6d4d`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400b6c0a`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400b6c2c`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400b6d2b`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400b6d4d`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b72ee`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b72ee`
- `win32kbase!?hModuleWin@@3PEAXEA` at `0x1400b6c63`
- `win32kbase!?hModuleWin@@3PEAXEA` at `0x1400b6d8c`
- `win32kbase!W32SetCurrentThreadDpiAwarenessContext` at `0x1400b6bc9`
- `win32kbase!W32SetCurrentThreadDpiAwarenessContext` at `0x1400b70a8`
- `win32kbase!W32SetCurrentThreadDpiAwarenessContext` at `0x1400b754c`
- `win32kbase!W32SetCurrentThreadDpiAwarenessContext` at `0x1400b6bc9`
- `win32kbase!W32SetCurrentThreadDpiAwarenessContext` at `0x1400b70a8`
- `win32kbase!W32SetCurrentThreadDpiAwarenessContext` at `0x1400b754c`
- `win32kbase!UserDereferenceObject` at `0x1400b68be`
- `win32kbase!UserSleep` at `0x1400b72b2`
- `win32kbase!UserSleep` at `0x1400b72b2`
- `win32kbase!HMChangeOwnerThread` at `0x1400b7081`
- `win32kbase!HMChangeOwnerThread` at `0x1400b7095`
- `win32kbase!HMChangeOwnerThread` at `0x1400b7081`
- `win32kbase!HMChangeOwnerThread` at `0x1400b7095`
- `win32kbase!SetHandleFlag` at `0x1400b6807`
- `win32kbase!SetHandleFlag` at `0x1400b6952`
- `win32kbase!SetHandleFlag` at `0x1400b7519`
- `win32kbase!SetHandleFlag` at `0x1400b6807`
- `win32kbase!SetHandleFlag` at `0x1400b6952`
- `win32kbase!SetHandleFlag` at `0x1400b7519`
- `win32kbase!IsImmersiveAppRestricted` at `0x1400b6c4c`
- `win32kbase!IsImmersiveAppRestricted` at `0x1400b6d6d`
- `win32kbase!IsImmersiveAppRestricted` at `0x1400b6c4c`
- `win32kbase!IsImmersiveAppRestricted` at `0x1400b6d6d`
- `win32kbase!DereferenceDwmApiPort` at `0x1400b6a8f`
- `win32kbase!DereferenceDwmApiPort` at `0x1400b7694`
- `win32kbase!DereferenceDwmApiPort` at `0x1400b6a8f`
- `win32kbase!DereferenceDwmApiPort` at `0x1400b7694`
- `win32kbase!HMAssignmentLock` at `0x1400b6eef`
- `win32kbase!HMAssignmentLock` at `0x1400b6f27`
- `win32kbase!HMAssignmentLock` at `0x1400b6f87`
- `win32kbase!HMAssignmentLock` at `0x1400b6fdb`
- `win32kbase!HMAssignmentLock` at `0x1400b6eef`
- `win32kbase!HMAssignmentLock` at `0x1400b6f27`
- `win32kbase!HMAssignmentLock` at `0x1400b6f87`
- `win32kbase!HMAssignmentLock` at `0x1400b6fdb`
- `win32kbase!HMAssignmentUnlock` at `0x1400b6fa3`
- `win32kbase!HMAssignmentUnlock` at `0x1400b702d`
- `win32kbase!HMAssignmentUnlock` at `0x1400b7571`
- `win32kbase!HMAssignmentUnlock` at `0x1400b75a2`
- `win32kbase!HMAssignmentUnlock` at `0x1400b6fa3`
- `win32kbase!HMAssignmentUnlock` at `0x1400b702d`
- `win32kbase!HMAssignmentUnlock` at `0x1400b7571`
- `win32kbase!HMAssignmentUnlock` at `0x1400b75a2`
- `win32kbase!ReferenceDwmApiPort` at `0x1400b6a3e`
- `win32kbase!ReferenceDwmApiPort` at `0x1400b6a65`
- `win32kbase!ReferenceDwmApiPort` at `0x1400b7652`
- `win32kbase!ReferenceDwmApiPort` at `0x1400b767a`
- `win32kbase!ReferenceDwmApiPort` at `0x1400b6a3e`
- `win32kbase!ReferenceDwmApiPort` at `0x1400b6a65`
- `win32kbase!ReferenceDwmApiPort` at `0x1400b7652`
- `win32kbase!ReferenceDwmApiPort` at `0x1400b767a`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400b6993`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400b69c5`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400b6993`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400b69c5`
- `WIN32K!W32GetUserSessionState` at `0x1400b6b70`
- `WIN32K!W32GetUserSessionState` at `0x1400b6da5`
- `WIN32K!W32GetUserSessionState` at `0x1400b6db8`
- `WIN32K!W32GetUserSessionState` at `0x1400b7039`
- `WIN32K!W32GetUserSessionState` at `0x1400b7057`
- `WIN32K!W32GetUserSessionState` at `0x1400b719a`
- `WIN32K!W32GetUserSessionState` at `0x1400b71ca`
- `WIN32K!W32GetUserSessionState` at `0x1400b7246`
- `WIN32K!W32GetUserSessionState` at `0x1400b7256`
- `WIN32K!W32GetUserSessionState` at `0x1400b7277`
- `WIN32K!W32GetUserSessionState` at `0x1400b72be`
- `WIN32K!W32GetUserSessionState` at `0x1400b72ff`
- `WIN32K!W32GetUserSessionState` at `0x1400b731d`
- `WIN32K!W32GetUserSessionState` at `0x1400b7372`
- `WIN32K!W32GetUserSessionState` at `0x1400b738b`
- `WIN32K!W32GetUserSessionState` at `0x1400b7408`
- `WIN32K!W32GetUserSessionState` at `0x1400b742d`
- `WIN32K!W32GetUserSessionState` at `0x1400b74ba`
- `WIN32K!W32GetUserSessionState` at `0x1400b6b70`
- `WIN32K!W32GetUserSessionState` at `0x1400b6da5`
- `WIN32K!W32GetUserSessionState` at `0x1400b6db8`
- `WIN32K!W32GetUserSessionState` at `0x1400b7039`
- `WIN32K!W32GetUserSessionState` at `0x1400b7057`
- `WIN32K!W32GetUserSessionState` at `0x1400b719a`
- `WIN32K!W32GetUserSessionState` at `0x1400b71ca`
- `WIN32K!W32GetUserSessionState` at `0x1400b7246`
- `WIN32K!W32GetUserSessionState` at `0x1400b7256`
- `WIN32K!W32GetUserSessionState` at `0x1400b7277`
- `WIN32K!W32GetUserSessionState` at `0x1400b72be`
- `WIN32K!W32GetUserSessionState` at `0x1400b72ff`
- `WIN32K!W32GetUserSessionState` at `0x1400b731d`
- `WIN32K!W32GetUserSessionState` at `0x1400b7372`
- `WIN32K!W32GetUserSessionState` at `0x1400b738b`
- `WIN32K!W32GetUserSessionState` at `0x1400b7408`
- `WIN32K!W32GetUserSessionState` at `0x1400b742d`
- `WIN32K!W32GetUserSessionState` at `0x1400b74ba`

## pseudocode

```c
__int64 __fastcall xxxCreateDesktopEx(__int64 a1, unsigned int a2, int a3, int a4, HANDLE *a5, int a6)
{
  struct tagWND *Window; // r13
  struct tagTHREADINFO *v10; // rsi
  __int64 v11; // r8
  NTSTATUS v12; // eax
  int v13; // ebx
  __int64 v14; // rdx
  int v15; // r12d
  int v16; // eax
  char *v17; // r15
  struct tagWINDOWSTATION *v18; // rbx
  __int64 v19; // r12
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // rdi
  __int64 v25; // r8
  __int64 v26; // r9
  void *v27; // rax
  __int64 v28; // rcx
  __int64 UserSessionState; // rax
  __int64 v30; // r9
  int v31; // edi
  DWORD *PhysicalScreenRect; // rax
  DWORD v33; // r13d
  __int64 CurrentProcessWin32Process; // rax
  __int64 v35; // rax
  __int64 v36; // rcx
  char v37; // di
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // r8
  __int64 v45; // r9
  unsigned int v46; // edi
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // r8
  __int64 v50; // r9
  __int64 v51; // rax
  struct tagWND *v52; // rbx
  int v53; // ecx
  _QWORD *v54; // rdi
  __int64 v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // r8
  __int64 v58; // r9
  __int64 v59; // rdx
  __int64 v60; // rcx
  __int64 v61; // r8
  __int64 v62; // r9
  __int64 v63; // r9
  __int64 v64; // rdx
  volatile signed __int32 *v65; // rcx
  __int64 v66; // r8
  __int64 v67; // r9
  __int64 v68; // rax
  struct tagWINDOWSTATION *v69; // rdx
  __int64 v70; // rax
  __int64 v71; // r9
  __int64 v72; // rdx
  __int64 v73; // r8
  __int64 v74; // r9
  __int64 v75; // rdx
  __int64 v76; // rcx
  __int64 v77; // r8
  __int64 v78; // r9
  __int64 i; // rax
  __int64 v80; // rdx
  __int64 v81; // rcx
  __int64 v82; // r8
  __int64 v83; // r9
  __int64 v84; // rdx
  __int64 v85; // rcx
  __int64 v86; // r8
  __int64 v87; // r9
  __int64 v88; // rax
  __int64 v89; // rdx
  __int64 v90; // rcx
  __int64 v91; // r8
  __int64 v92; // r9
  void *v93; // rcx
  __int64 v94; // rdx
  __int64 v95; // rcx
  __int64 v96; // r8
  __int64 v97; // r9
  __int64 v98; // rdx
  __int64 v99; // rcx
  __int64 v100; // r8
  __int64 v101; // r9
  __int64 v102; // rdx
  __int64 v103; // rcx
  __int64 v104; // r8
  __int64 v105; // r9
  __int64 v106; // rdx
  __int64 v107; // rax
  __int64 v108; // rdx
  __int64 v109; // rcx
  __int64 v110; // r8
  __int64 v111; // r9
  __int64 v112; // rax
  struct tagWND *v113; // rbx
  bool v114; // bl
  bool v115; // r12
  __int64 v116; // rax
  int v117; // r8d
  int v118; // edx
  _QWORD *v119; // rcx
  __int64 v120; // r9
  __int64 v121; // rdx
  __int64 v122; // rcx
  __int64 v123; // r8
  __int64 v124; // r8
  __int64 v125; // r9
  __int64 v126; // r12
  __int64 v127; // r8
  void *v128; // rax
  __int64 v129; // rdx
  char v131; // [rsp+90h] [rbp-188h]
  bool v132; // [rsp+91h] [rbp-187h]
  LONG v133; // [rsp+94h] [rbp-184h]
  char v134; // [rsp+94h] [rbp-184h]
  HANDLE Handle; // [rsp+98h] [rbp-180h] BYREF
  _BYTE v136[4]; // [rsp+A0h] [rbp-178h] BYREF
  unsigned int v137; // [rsp+A4h] [rbp-174h]
  union _LARGE_INTEGER Timeout[2]; // [rsp+B0h] [rbp-168h] BYREF
  struct tagWND *v139; // [rsp+C0h] [rbp-158h]
  BOOL v140; // [rsp+C8h] [rbp-150h]
  signed __int32 v141; // [rsp+CCh] [rbp-14Ch]
  int v142; // [rsp+D0h] [rbp-148h]
  _BYTE v143[16]; // [rsp+D8h] [rbp-140h] BYREF
  DWORD v144; // [rsp+E8h] [rbp-130h]
  __int64 v145; // [rsp+100h] [rbp-118h] BYREF
  struct tagWINDOWSTATION *v146; // [rsp+108h] [rbp-110h]
  PVOID Object; // [rsp+110h] [rbp-108h] BYREF
  _QWORD *v148; // [rsp+118h] [rbp-100h]
  __int64 v149; // [rsp+120h] [rbp-F8h]
  void *v150; // [rsp+128h] [rbp-F0h]
  __int64 v151; // [rsp+130h] [rbp-E8h]
  __int64 v152; // [rsp+138h] [rbp-E0h]
  ULONG_PTR BugCheckParameter3[2]; // [rsp+140h] [rbp-D8h] BYREF
  ULONG_PTR v154[2]; // [rsp+150h] [rbp-C8h] BYREF
  HWINSTA v155[2]; // [rsp+160h] [rbp-B8h] BYREF
  _QWORD v156[3]; // [rsp+170h] [rbp-A8h] BYREF
  _QWORD v157[5]; // [rsp+188h] [rbp-90h] BYREF
  int v158; // [rsp+1B0h] [rbp-68h]
  int v159; // [rsp+1B4h] [rbp-64h]
  _BYTE v160[16]; // [rsp+1B8h] [rbp-60h] BYREF
  HWINSTA v161; // [rsp+1C8h] [rbp-50h]
  _BYTE v162[32]; // [rsp+1D0h] [rbp-48h] BYREF

  Window = 0;
  Handle = 0;
  v145 = 0;
  v10 = PtiCurrent();
  Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(v154);
  Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(BugCheckParameter3);
  v155[0] = *(HWINSTA *)(a1 + 8);
  v161 = v155[0];
  LODWORD(v145) = W32GetCurrentWin32kSessionId();
  HIDWORD(v145) = a4;
  LOBYTE(v11) = a6 == 0;
  v12 = ObOpenObjectByName(a1, ExDesktopObjectType, v11, 0, a3, &v145, &Handle);
  v13 = v12;
  if ( v12 < 0 )
  {
    SetLastNtError(v12);
    CleanupDirtyDesktops();
LABEL_9:
    *a5 = 0;
    goto LABEL_126;
  }
  v15 = 0;
  if ( v12 == 0x40000000 )
  {
    if ( !(unsigned int)SetHandleFlag(Handle, 1, 1) )
    {
      SetLastNtError(-1073741801);
      CloseProtectedHandle(Handle, 0);
      v13 = -1073741801;
      goto LABEL_9;
    }
    *a5 = Handle;
    v15 = 1;
  }
  Object = 0;
  v16 = ObReferenceObjectByHandle(Handle, 0, (POBJECT_TYPE)ExDesktopObjectType, 1, &Object, 0);
  v13 = v16;
  if ( v16 < 0 )
  {
    SetLastNtError(v16);
    CloseProtectedHandle(Handle, 0);
    goto LABEL_9;
  }
  v17 = (char *)Object;
  Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>::Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>(
    v156,
    (__int64)Object,
    UserDereferenceObject);
  if ( v15 )
  {
    v13 = OpenDesktopCompletion(v17, Handle, a2);
    if ( v13 >= 0 )
    {
LABEL_14:
      Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>::~Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>(v156);
      goto LABEL_126;
    }
    CloseProtectedHandle(Handle, 0);
LABEL_13:
    *a5 = 0;
    goto LABEL_14;
  }
  v18 = (struct tagWINDOWSTATION *)*((_QWORD *)v17 + 5);
  v146 = v18;
  v19 = *((_QWORD *)v18 + 3);
  v148 = (_QWORD *)*((_QWORD *)v17 + 1);
  v148[22] = 0;
  if ( !(unsigned int)SetHandleFlag(Handle, 0, a2 & 1) )
  {
    CloseProtectedHandle(Handle, 0);
    *a5 = 0;
    Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>::~Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>(v156);
    v13 = -1073741801;
    goto LABEL_126;
  }
  if ( *(_QWORD *)(W32GetUserGdiSessionState(v20) + 40) )
  {
    v157[0] = 0;
    v157[1] = 0;
    v157[2] = 1;
    v157[3] = *(_QWORD *)(W32GetUserGdiSessionState(v22) + 40);
    v157[4] = v17;
    v158 = 0;
    v159 = 1;
    v13 = MapDesktop((__int64)v157);
    if ( v13 < 0 )
    {
      CloseProtectedHandle(Handle, 0);
      SetLastNtError(-1073741790);
      goto LABEL_13;
    }
    v18 = v146;
  }
  v139 = 0;
  v142 = 0;
  v24 = ReferenceDwmApiPort(v22, v21, v23);
  if ( v24 )
  {
    if ( (*((_DWORD *)v18 + 8) & 0x200) != 0 )
    {
      v27 = (void *)ReferenceDwmApiPort(*((_QWORD *)v17 + 1), **((_QWORD **)v17 + 1), v25);
      DwmAsyncDesktopCreate(v27);
      zzzComposeDesktop((struct tagDESKTOP *)v17);
      v142 = 1;
    }
    DereferenceDwmApiPort(v24);
  }
  v149 = *((_QWORD *)v10 + 57);
  v152 = *(_QWORD *)(v149 + 344);
  v141 = _InterlockedCompareExchange((volatile signed __int32 *)v10 + 130, 0, 0) & 0x20000000;
  v132 = v141 != 0;
  v28 = *(_QWORD *)(*(_QWORD *)(v19 + 16) + 456LL);
  *((_QWORD *)v10 + 57) = v28;
  if ( (*(_DWORD *)(v28 + 12) & 0x2000000) != 0 )
    _InterlockedOr((volatile signed __int32 *)v10 + 130, 0x20000000u);
  else
    _InterlockedAnd((volatile signed __int32 *)v10 + 130, 0xDFFFFFFF);
  v140 = (_InterlockedCompareExchange((volatile signed __int32 *)v10 + 130, 0, 0) & 0x20000000) != 0;
  if ( (_InterlockedCompareExchange((volatile signed __int32 *)v10 + 130, 0, 0) & 0x10000000) != 0 )
  {
    v131 = 0;
  }
  else
  {
    v131 = 1;
    _InterlockedOr((volatile signed __int32 *)v10 + 130, 0x10000000u);
  }
  v151 = *((_QWORD *)v10 + 61);
  v150 = (void *)*((_QWORD *)v10 + 78);
  UserSessionState = W32GetUserSessionState(0x10000000, 0x20000000, v25, v26);
  ++*(_DWORD *)(UserSessionState + 70592);
  AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)v143);
  v31 = zzzSetDesktop((__int64)v10, (__int64)v17, Handle, v30);
  if ( v31 < 0 )
  {
    v137 = 0;
    goto LABEL_33;
  }
  v137 = W32SetCurrentThreadDpiAwarenessContext(18);
  PhysicalScreenRect = (DWORD *)GetPhysicalScreenRect(v160);
  Timeout[0].LowPart = *PhysicalScreenRect;
  v133 = PhysicalScreenRect[1];
  v144 = PhysicalScreenRect[2];
  v33 = PhysicalScreenRect[3];
  CurrentProcessWin32Process = PsGetCurrentProcessWin32Process(v144);
  if ( !CurrentProcessWin32Process
    || (-(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0) & CurrentProcessWin32Process) == 0 )
  {
    goto LABEL_40;
  }
  v35 = PsGetCurrentProcessWin32Process(-*(_QWORD *)CurrentProcessWin32Process);
  v36 = v35;
  if ( v35 )
    v36 = ((unsigned __int128)-(__int128)*(unsigned __int64 *)v35 >> 64) & v35;
  if ( (unsigned int)IsImmersiveAppRestricted(v36) )
    v37 = 1;
  else
LABEL_40:
    v37 = 0;
  SmartObjStackRef<tagMENU>::SmartObjStackRef<tagMENU>(v162, 0);
  Window = (struct tagWND *)xxxCreateWindowEx(
                              0,
                              (wchar_t *)0x8001,
                              32769,
                              0,
                              0x82000000,
                              Timeout[0].LowPart,
                              v133,
                              v144 - Timeout[0].LowPart,
                              v33 - v133,
                              0,
                              (__int64)v162,
                              hModuleWin,
                              0,
                              1u,
                              0x30Au,
                              v37,
                              0);
  SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(v162);
  if ( !Window )
    goto LABEL_42;
  Win32HMThreadLockBase<tagMENU,1,1>::ManualLock<void>((__int64 *)v154, (__int64)Window);
  v39 = PsGetCurrentProcessWin32Process(v38);
  if ( !v39 || (-(__int64)(*(_QWORD *)v39 != 0) & v39) == 0 )
    goto LABEL_48;
  v40 = PsGetCurrentProcessWin32Process(-*(_QWORD *)v39);
  v41 = v40;
  if ( v40 )
    v41 = ((unsigned __int128)-(__int128)*(unsigned __int64 *)v40 >> 64) & v40;
  v134 = 1;
  if ( !(unsigned int)IsImmersiveAppRestricted(v41) )
LABEL_48:
    v134 = 0;
  SmartObjStackRef<tagMENU>::SmartObjStackRef<tagMENU>(v157, 0);
  v46 = *(unsigned __int16 *)(W32GetUserSessionState(v43, v42, v44, v45) + 41168);
  v51 = W32GetUserSessionState(v48, v47, v49, v50);
  v52 = (struct tagWND *)xxxCreateWindowEx(
                           0,
                           (wchar_t *)*(unsigned __int16 *)(v51 + 41168),
                           v46,
                           0,
                           0x82000000,
                           0,
                           0,
                           100,
                           0x64u,
                           0,
                           (__int64)v157,
                           hModuleWin,
                           0,
                           1u,
                           0x30Au,
                           v134,
                           0);
  v139 = v52;
  SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(v157);
  if ( !v52 )
  {
LABEL_42:
    v31 = -1073741801;
    goto LABEL_33;
  }
  v53 = *(unsigned __int16 *)(*((_QWORD *)v52 + 5) + 42LL);
  if ( (v53 & 0xFFFF3FFF) != 0 )
  {
    if ( (v53 & 0x1000) != 0 )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTellMeIf", 0x20000, 2345);
    v31 = -1073741790;
  }
  else
  {
    Win32HMThreadLockBase<tagMENU,1,1>::ManualLock<void>((__int64 *)BugCheckParameter3, (__int64)v52);
    *(_WORD *)(*((_QWORD *)v52 + 5) + 42LL) = *(_WORD *)(*((_QWORD *)v52 + 5) + 42LL) & 0xC000 | 0x29F;
    v54 = v148 + 3;
    *(_QWORD *)(*v148 + 8LL) = *((_QWORD *)Window + 6);
    Timeout[0].QuadPart = (LONGLONG)v54;
    Timeout[1].QuadPart = (LONGLONG)Window;
    HMAssignmentLock(Timeout, 0);
    *(_OWORD *)&Timeout[0].LowPart = *(_OWORD *)LockPointer(v160, (char *)v52 + 104, *(_QWORD *)(v19 + 8));
    HMAssignmentLock(Timeout, 0);
    AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)Timeout);
    xxxInheritWindowMonitor(v52);
    AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)Timeout);
    LinkWindow((struct tagWND **)v52, 0, *(__int64 **)(v19 + 8));
    Timeout[0].QuadPart = (LONGLONG)(v17 + 112);
    Timeout[1].QuadPart = (LONGLONG)v52;
    HMAssignmentLock(Timeout, 0);
    *(_QWORD *)(*((_QWORD *)v52 + 5) + 64LL) = 0;
    HMAssignmentUnlock((char *)v52 + 120);
    *(_OWORD *)&Timeout[0].LowPart = *(_OWORD *)LockPointer(v160, (char *)Window + 104, *(_QWORD *)(v19 + 8));
    HMAssignmentLock(Timeout, 0);
    AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)Timeout);
    xxxInheritWindowMonitor(Window);
    AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)Timeout);
    LinkWindow((struct tagWND **)Window, 0, *(__int64 **)(v19 + 8));
    *(_QWORD *)(*((_QWORD *)Window + 5) + 64LL) = 0;
    HMAssignmentUnlock((char *)Window + 120);
    v59 = *(_QWORD *)(W32GetUserSessionState(v56, v55, v57, v58) + 56744);
    if ( (*(_DWORD *)(v59 + 132) & 1) == 0 )
      *(_QWORD *)(*((_QWORD *)Window + 5) + 168LL) = *(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v60, v59, v61, v62)
                                                                           + 56744)
                                                               + 120LL);
    HMChangeOwnerThread(*v54, *(_QWORD *)(v19 + 16));
    HMChangeOwnerThread(v52, *(_QWORD *)(v19 + 16));
    W32SetCurrentThreadDpiAwarenessContext(v137);
    v137 = 0;
    *((_QWORD *)v10 + 57) = v149;
    if ( (_InterlockedCompareExchange((volatile signed __int32 *)v10 + 130, 0, 0) & 0x10000000) == 0 )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 2417);
    if ( v131 )
      _InterlockedAnd((volatile signed __int32 *)v10 + 130, 0xEFFFFFFF);
    if ( v140 != v132 )
    {
      if ( v141 )
        _InterlockedOr((volatile signed __int32 *)v10 + 130, 0x20000000u);
      else
        _InterlockedAnd((volatile signed __int32 *)v10 + 130, 0xDFFFFFFF);
    }
    v31 = zzzSetDesktop((__int64)v10, v151, v150, v63);
    if ( v31 >= 0 )
    {
      AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v143);
      EditionEndDeferWinEventNotify();
      if ( *(_QWORD *)(v19 + 56) )
      {
        if ( (*(_DWORD *)v19 & 2) != 0 )
        {
          v70 = W32GetUserSessionState(v65, v64, v66, v67);
          ++*(_DWORD *)(v70 + 70592);
          AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)v143);
          v31 = zzzSetDesktop(*(_QWORD *)(v19 + 16), (__int64)v17, 0, v71);
          if ( v31 < 0 )
            goto LABEL_33;
          AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v143);
          EditionEndDeferWinEventNotify();
        }
        else
        {
          v68 = W32GetUserSessionState(v65, v64, v66, v67);
          v69 = v146;
          *(_QWORD *)(*(_QWORD *)(v68 + 18752) + 648LL) = v146;
          *(_QWORD *)(*(_QWORD *)(v19 + 16) + 648LL) = v69;
        }
        KeSetEvent(*(PRKEVENT *)(v19 + 56), 1, 0);
        if ( (*(_DWORD *)v19 & 2) == 0 )
        {
          LeaveEnterCrit::LeaveEnterCrit((LeaveEnterCrit *)v136);
          for ( i = W32GetUserSessionState(v76, v75, v77, v78);
                !*(_QWORD *)(i + 19216);
                i = W32GetUserSessionState(v90, v89, v91, v92) )
          {
            if ( *(_QWORD *)(W32GetUserSessionState(v81, v80, v82, v83) + 62736) )
            {
              Timeout[0].QuadPart = -200000;
              v88 = W32GetUserSessionState(v85, v84, v86, v87);
              KeWaitForSingleObject(*(PVOID *)(v88 + 62736), Executive, 0, 0, Timeout);
            }
            else
            {
              UserSleep(20);
            }
          }
          LeaveEnterCrit::~LeaveEnterCrit((LeaveEnterCrit *)v136);
        }
        v93 = *(void **)(v19 + 56);
        if ( v93 )
        {
          ObfDereferenceObject(v93);
          *(_QWORD *)(v19 + 56) = 0;
        }
        v65 = *(volatile signed __int32 **)(W32GetUserSessionState(v93, v72, v73, v74) + 19704);
        _InterlockedOr(v65, 0x800u);
      }
      if ( v19 == W32GetUserSessionState(v65, v64, v66, v67) + 68448 )
        xxxSetWindowPos(Window, 1, 0, 0, 0, 0, 1115);
      if ( !v152 )
        DeferrableUnlockObjectAssignment<tagDESKTOP>(*((_QWORD *)v10 + 57) + 344LL);
      if ( !*(_QWORD *)(W32GetUserSessionState(v95, v94, v96, v97) + 62752)
        && v17 == *(char **)(W32GetUserSessionState(v99, v98, v100, v101) + 62744) )
      {
        if ( !(unsigned int)xxxCreateDisconnectDesktop(v155[0], v146) )
        {
          Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>(BugCheckParameter3, v102);
          Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>(v154, v106);
          CloseDesktop((unsigned __int64)Handle, 0);
          *a5 = 0;
          Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>::~Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>(v156);
          v13 = -1073741823;
          goto LABEL_126;
        }
        v107 = W32GetUserSessionState(v103, v102, v104, v105);
        KeSetEvent(*(PRKEVENT *)(v107 + 62576), 1, 0);
        v112 = W32GetUserSessionState(v109, v108, v110, v111);
        *(_DWORD *)(v112 + 68920) |= 0x40000u;
      }
      v113 = v139;
      goto LABEL_91;
    }
  }
LABEL_33:
  AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v143);
  while ( 1 )
  {
    AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)v143);
    if ( v137 )
      W32SetCurrentThreadDpiAwarenessContext(v137);
    v113 = v139;
    if ( v139 )
    {
      xxxDestroyWindow(v139);
      HMAssignmentUnlock(v17 + 112);
    }
    if ( Window )
    {
      xxxDestroyWindow(Window);
      v119 = v148 + 3;
      *(_QWORD *)(*v148 + 8LL) = 0;
      HMAssignmentUnlock(v119);
    }
    *((_QWORD *)v10 + 57) = v149;
    if ( v131 )
      _InterlockedAnd((volatile signed __int32 *)v10 + 130, 0xEFFFFFFF);
    if ( v140 != v132 )
    {
      if ( v141 )
        _InterlockedOr((volatile signed __int32 *)v10 + 130, 0x20000000u);
      else
        _InterlockedAnd((volatile signed __int32 *)v10 + 130, 0xDFFFFFFF);
    }
    AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v143);
    EditionEndDeferWinEventNotify();
    AtomicExecutionCheck::AtomicExecutionCheck((AtomicExecutionCheck *)v155);
    zzzSetDesktop((__int64)v10, v151, v150, v120);
    AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v155);
    if ( v142 )
    {
      v126 = ReferenceDwmApiPort(v122, v121, v123);
      if ( v126 )
      {
        zzzDecomposeDesktop((struct tagDESKTOP *)v17, 0, v124, v125);
        v128 = (void *)ReferenceDwmApiPort(*((_QWORD *)v17 + 1), **((_QWORD **)v17 + 1), v127);
        DwmAsyncDesktopFree(v128);
        DereferenceDwmApiPort(v126);
        v113 = v139;
      }
    }
    CloseProtectedHandle(Handle, 0);
    Handle = 0;
    if ( !v152 )
      DeferrableUnlockObjectAssignment<tagDESKTOP>(*((_QWORD *)v10 + 57) + 344LL);
LABEL_91:
    if ( v113 )
      v139 = (struct tagWND *)Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>(BugCheckParameter3, v98);
    if ( Window )
      Window = (struct tagWND *)Win32HMThreadLockBase<tagCURSOR,1,1>::ManualUnlock<void>(v154, v98);
    v114 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v115 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v114 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v116 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, v98, v100, v101);
      LOBYTE(v117) = v115;
      LOBYTE(v118) = v114;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v118,
        v117,
        *(_QWORD *)(v116 + 69152),
        4,
        3,
        24,
        (__int64)WPP_8482796ea87931402564603ebe19074e_Traceguids);
    }
    if ( !Handle || (unsigned int)SetHandleFlag(Handle, 1, 1) )
      break;
    v31 = -1073741801;
  }
  if ( v31 >= 0 )
    *((_DWORD *)v17 + 12) |= 0x10u;
  *a5 = Handle;
  Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>::~Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>(v156);
  v13 = v31;
LABEL_126:
  Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>(BugCheckParameter3, v14);
  Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>(v154, v129);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400b66fc  mov     rax, rsp
0x1400b66ff  mov     [rax+10h], rbx
0x1400b6703  mov     [rax+18h], rsi
0x1400b6707  mov     [rax+8], rcx
0x1400b670b  push    rdi
0x1400b670c  push    r12
0x1400b670e  push    r13
0x1400b6710  push    r14
0x1400b6712  push    r15
0x1400b6714  sub     rsp, 1F0h
0x1400b671b  mov     ebx, r9d
0x1400b671e  mov     r14d, r8d
0x1400b6721  mov     edi, edx
0x1400b6723  xor     r13d, r13d
0x1400b6726  mov     [rax-180h], r13
0x1400b672d  mov     [rax-118h], r13
0x1400b6734  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400b6739  mov     rsi, rax
0x1400b673c  lea     rcx, [rsp+218h+var_C8]
0x1400b6744  call    ??0?$Win32HMOptionalThreadLockAlways@UtagMENU@@@@QEAA@XZ; Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(void)
0x1400b6749  lea     rcx, [rsp+218h+BugCheckParameter3]
0x1400b6751  call    ??0?$Win32HMOptionalThreadLockAlways@UtagMENU@@@@QEAA@XZ; Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(void)
0x1400b6756  nop
0x1400b6757  mov     rax, [rsp+218h+arg_0]
0x1400b675f  mov     rax, [rax+8]
0x1400b6763  mov     [rsp+218h+var_B8], rax
0x1400b676b  mov     [rsp+218h+var_50], rax
0x1400b6773  call    W32GetCurrentWin32kSessionId
0x1400b6778  mov     [rsp+218h+var_118], eax
0x1400b677f  mov     [rsp+218h+var_114], ebx
0x1400b6786  mov     rax, cs:ExDesktopObjectType
0x1400b678d  mov     rdx, [rax]
0x1400b6790  cmp     [rsp+218h+arg_28], r13d
0x1400b6798  setz    r8b
0x1400b679c  lea     rax, [rsp+218h+Handle]
0x1400b67a4  mov     qword ptr [rsp+218h+var_1E8], rax
0x1400b67a9  lea     rax, [rsp+218h+var_118]
0x1400b67b1  mov     [rsp+218h+HandleInformation], rax
0x1400b67b6  mov     dword ptr [rsp+218h+Object], r14d
0x1400b67bb  xor     r9d, r9d
0x1400b67be  mov     rcx, [rsp+218h+arg_0]
0x1400b67c6  call    cs:__imp_ObOpenObjectByName
0x1400b67cd  nop     dword ptr [rax+rax+00h]
0x1400b67d2  mov     ebx, eax
0x1400b67d4  test    eax, eax
0x1400b67d6  jns     short loc_1400B67E9
0x1400b67d8  mov     ecx, eax
0x1400b67da  call    SetLastNtError
0x1400b67df  call    ?CleanupDirtyDesktops@@YAXXZ; CleanupDirtyDesktops(void)
0x1400b67e4  jmp     loc_1400B68A6
0x1400b67e9  mov     r12d, r13d
0x1400b67ec  mov     r14d, 1
0x1400b67f2  cmp     eax, 40000000h
0x1400b67f7  jnz     short loc_1400B684D
0x1400b67f9  mov     r8d, r14d
0x1400b67fc  mov     edx, r14d
0x1400b67ff  mov     rcx, [rsp+218h+Handle]
0x1400b6807  call    cs:__imp_SetHandleFlag
0x1400b680e  nop     dword ptr [rax+rax+00h]
0x1400b6813  test    eax, eax
0x1400b6815  jnz     short loc_1400B6837
0x1400b6817  mov     ecx, 0C0000017h
0x1400b681c  call    SetLastNtError
0x1400b6821  xor     edx, edx
0x1400b6823  mov     rcx, [rsp+218h+Handle]; Handle
0x1400b682b  call    CloseProtectedHandle
0x1400b6830  mov     ebx, 0C0000017h
0x1400b6835  jmp     short loc_1400B68A6
0x1400b6837  mov     rcx, [rsp+218h+Handle]
0x1400b683f  mov     rax, [rsp+218h+arg_20]
0x1400b6847  mov     [rax], rcx
0x1400b684a  mov     r12d, r14d
0x1400b684d  mov     [rsp+218h+var_108], r13
0x1400b6855  mov     [rsp+218h+HandleInformation], r13; HandleInformation
0x1400b685a  lea     rax, [rsp+218h+var_108]
0x1400b6862  mov     [rsp+218h+Object], rax; Object
0x1400b6867  mov     r9b, r14b; AccessMode
0x1400b686a  mov     r8, cs:ExDesktopObjectType
0x1400b6871  mov     r8, [r8]; ObjectType
0x1400b6874  xor     edx, edx; DesiredAccess
0x1400b6876  mov     rcx, [rsp+218h+Handle]; Handle
0x1400b687e  call    cs:__imp_ObReferenceObjectByHandle
0x1400b6885  nop     dword ptr [rax+rax+00h]
0x1400b688a  mov     ebx, eax
0x1400b688c  test    eax, eax
0x1400b688e  jns     short loc_1400B68B6
0x1400b6890  mov     ecx, eax
0x1400b6892  call    SetLastNtError
0x1400b6897  xor     edx, edx
0x1400b6899  mov     rcx, [rsp+218h+Handle]; Handle
0x1400b68a1  call    CloseProtectedHandle
0x1400b68a6  mov     rax, [rsp+218h+arg_20]
0x1400b68ae  mov     [rax], r13
0x1400b68b1  jmp     loc_1400B7715
0x1400b68b6  mov     r15, [rsp+218h+var_108]
0x1400b68be  mov     r8, cs:__imp_UserDereferenceObject
0x1400b68c5  mov     rdx, r15
0x1400b68c8  lea     rcx, [rsp+218h+var_A8]
0x1400b68d0  call    ??0?$Win32RawLockedItemNoCleanup@U_ACCESS_ALLOWED_ACE@@$0A@@@QEAA@PEAU_ACCESS_ALLOWED_ACE@@P6AXPEAX@Z@Z; Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>::Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>(_ACCESS_ALLOWED_ACE *,void (*)(void *))
0x1400b68d5  test    r12d, r12d
0x1400b68d8  jz      short loc_1400B691F
0x1400b68da  mov     r8d, edi
0x1400b68dd  mov     rdx, [rsp+218h+Handle]
0x1400b68e5  mov     rcx, r15
0x1400b68e8  call    OpenDesktopCompletion
0x1400b68ed  mov     ebx, eax
0x1400b68ef  test    eax, eax
0x1400b68f1  jns     short loc_1400B690D
0x1400b68f3  xor     edx, edx
0x1400b68f5  mov     rcx, [rsp+218h+Handle]; Handle
0x1400b68fd  call    CloseProtectedHandle
0x1400b6902  mov     rcx, [rsp+218h+arg_20]
0x1400b690a  mov     [rcx], r13
0x1400b690d  lea     rcx, [rsp+218h+var_A8]
0x1400b6915  call    ??1?$Win32RawLockedItem@UtagEVENT_PACKET_TARGETS@@$0A@@@QEAA@XZ; Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>::~Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>(void)
0x1400b691a  jmp     loc_1400B7715
0x1400b691f  mov     rbx, [r15+28h]
0x1400b6923  mov     [rsp+218h+var_110], rbx
0x1400b692b  mov     r12, [rbx+18h]
0x1400b692f  mov     rax, [r15+8]
0x1400b6933  mov     [rsp+218h+var_100], rax
0x1400b693b  mov     [rax+0B0h], r13
0x1400b6942  and     edi, r14d
0x1400b6945  mov     r8d, edi
0x1400b6948  xor     edx, edx
0x1400b694a  mov     rcx, [rsp+218h+Handle]
0x1400b6952  call    cs:__imp_SetHandleFlag
0x1400b6959  nop     dword ptr [rax+rax+00h]
0x1400b695e  test    eax, eax
0x1400b6960  jnz     short loc_1400B6993
0x1400b6962  xor     edx, edx
0x1400b6964  mov     rcx, [rsp+218h+Handle]; Handle
0x1400b696c  call    CloseProtectedHandle
0x1400b6971  mov     rax, [rsp+218h+arg_20]
0x1400b6979  mov     [rax], r13
0x1400b697c  lea     rcx, [rsp+218h+var_A8]
0x1400b6984  call    ??1?$Win32RawLockedItem@UtagEVENT_PACKET_TARGETS@@$0A@@@QEAA@XZ; Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>::~Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>(void)
0x1400b6989  mov     ebx, 0C0000017h
0x1400b698e  jmp     loc_1400B7715
0x1400b6993  call    cs:__imp_W32GetUserGdiSessionState
0x1400b699a  nop     dword ptr [rax+rax+00h]
0x1400b699f  cmp     [rax+28h], r13
0x1400b69a3  jz      loc_1400B6A2E
0x1400b69a9  mov     [rsp+218h+var_90], r13
0x1400b69b1  mov     [rsp+218h+var_88], r13
0x1400b69b9  mov     [rsp+218h+var_80], 1
0x1400b69c5  call    cs:__imp_W32GetUserGdiSessionState
0x1400b69cc  nop     dword ptr [rax+rax+00h]
0x1400b69d1  mov     rcx, [rax+28h]
0x1400b69d5  mov     [rsp+218h+var_78], rcx
0x1400b69dd  mov     [rsp+218h+var_70], r15
0x1400b69e5  mov     [rsp+218h+var_68], r13d
0x1400b69ed  mov     [rsp+218h+var_64], r14d
0x1400b69f5  lea     rcx, [rsp+218h+var_90]
0x1400b69fd  call    MapDesktop
0x1400b6a02  mov     ebx, eax
0x1400b6a04  test    eax, eax
0x1400b6a06  jns     short loc_1400B6A26
0x1400b6a08  xor     edx, edx
0x1400b6a0a  mov     rcx, [rsp+218h+Handle]; Handle
0x1400b6a12  call    CloseProtectedHandle
0x1400b6a17  mov     ecx, 0C0000022h
0x1400b6a1c  call    SetLastNtError
0x1400b6a21  jmp     loc_1400B6902
0x1400b6a26  mov     rbx, [rsp+218h+var_110]
0x1400b6a2e  mov     [rsp+218h+var_158], r13
0x1400b6a36  mov     [rsp+218h+var_148], r13d
0x1400b6a3e  call    cs:__imp_ReferenceDwmApiPort
0x1400b6a45  nop     dword ptr [rax+rax+00h]
0x1400b6a4a  mov     rdi, rax
0x1400b6a4d  test    rax, rax
0x1400b6a50  jz      short loc_1400B6A9B
0x1400b6a52  test    dword ptr [rbx+20h], 200h
0x1400b6a59  jz      short loc_1400B6A8C
0x1400b6a5b  mov     rcx, [r15+8]
0x1400b6a5f  mov     rdx, [rcx]
0x1400b6a62  mov     rbx, [rdx]
0x1400b6a65  call    cs:__imp_ReferenceDwmApiPort
0x1400b6a6c  nop     dword ptr [rax+rax+00h]
0x1400b6a71  mov     rdx, rbx
0x1400b6a74  mov     rcx, rax; Object
0x1400b6a77  call    DwmAsyncDesktopCreate
0x1400b6a7c  mov     rcx, r15; struct tagDESKTOP *
0x1400b6a7f  call    zzzComposeDesktop
0x1400b6a84  mov     [rsp+218h+var_148], r14d
0x1400b6a8c  mov     rcx, rdi
0x1400b6a8f  call    cs:__imp_DereferenceDwmApiPort
0x1400b6a96  nop     dword ptr [rax+rax+00h]
0x1400b6a9b  mov     rax, [rsi+1C8h]
0x1400b6aa2  mov     [rsp+218h+var_F8], rax
0x1400b6aaa  mov     rax, [rax+158h]
0x1400b6ab1  mov     [rsp+218h+var_E0], rax
0x1400b6ab9  mov     ecx, r13d
0x1400b6abc  xor     eax, eax
0x1400b6abe  lock cmpxchg [rsi+208h], ecx
0x1400b6ac6  mov     edx, 20000000h
0x1400b6acb  and     eax, edx
0x1400b6acd  mov     [rsp+218h+var_14C], eax
0x1400b6ad4  setnz   [rsp+218h+var_187]
0x1400b6adc  mov     rcx, [r12+10h]
0x1400b6ae1  mov     rcx, [rcx+1C8h]
0x1400b6ae8  mov     [rsi+1C8h], rcx
0x1400b6aef  test    dword ptr [rcx+0Ch], 2000000h
0x1400b6af6  jz      short loc_1400B6B01
0x1400b6af8  lock or [rsi+208h], edx
0x1400b6aff  jmp     short loc_1400B6B0C
0x1400b6b01  lock and dword ptr [rsi+208h], 0DFFFFFFFh
0x1400b6b0c  mov     ecx, r13d
0x1400b6b0f  xor     eax, eax
0x1400b6b11  lock cmpxchg [rsi+208h], ecx
0x1400b6b19  shr     eax, 1Dh
0x1400b6b1c  and     al, r14b
0x1400b6b1f  mov     [rsp+218h+var_150], eax
0x1400b6b26  xor     eax, eax
0x1400b6b28  lock cmpxchg [rsi+208h], ecx
0x1400b6b30  mov     ecx, 10000000h
0x1400b6b35  test    ecx, eax
0x1400b6b37  jnz     short loc_1400B6B4A
0x1400b6b39  mov     [rsp+218h+var_188], r14b
0x1400b6b41  lock or [rsi+208h], ecx
0x1400b6b48  jmp     short loc_1400B6B52
0x1400b6b4a  mov     [rsp+218h+var_188], r13b
0x1400b6b52  mov     rax, [rsi+1E8h]
0x1400b6b59  mov     [rsp+218h+var_E8], rax
0x1400b6b61  mov     rax, [rsi+270h]
0x1400b6b68  mov     [rsp+218h+var_F0], rax
0x1400b6b70  call    cs:__imp_W32GetUserSessionState
0x1400b6b77  nop     dword ptr [rax+rax+00h]
0x1400b6b7c  add     [rax+113C0h], r14d
0x1400b6b83  lea     rcx, [rsp+218h+var_140]; this
0x1400b6b8b  call    ??0AtomicExecutionCheck@@QEAA@XZ; AtomicExecutionCheck::AtomicExecutionCheck(void)
0x1400b6b90  mov     r8, [rsp+218h+Handle]
0x1400b6b98  mov     rdx, r15
0x1400b6b9b  mov     rcx, rsi
0x1400b6b9e  call    zzzSetDesktop
0x1400b6ba3  mov     edi, eax
0x1400b6ba5  test    eax, eax
0x1400b6ba7  jns     short loc_1400B6BC4
0x1400b6ba9  xor     ecx, ecx
0x1400b6bab  mov     [rsp+218h+var_174], ecx
0x1400b6bb2  lea     rcx, [rsp+218h+var_140]; this
0x1400b6bba  call    ?Disarm@AtomicExecutionCheck@@QEAAXXZ; AtomicExecutionCheck::Disarm(void)
0x1400b6bbf  jmp     loc_1400B7532
0x1400b6bc4  mov     ecx, 12h
0x1400b6bc9  call    cs:__imp_W32SetCurrentThreadDpiAwarenessContext
0x1400b6bd0  nop     dword ptr [rax+rax+00h]
0x1400b6bd5  mov     [rsp+218h+var_174], eax
0x1400b6bdc  lea     rcx, [rsp+218h+var_60]
0x1400b6be4  call    GetPhysicalScreenRect
0x1400b6be9  mov     ecx, [rax]
0x1400b6beb  mov     dword ptr [rsp+218h+Timeout], ecx
0x1400b6bf2  mov     ecx, [rax+4]
0x1400b6bf5  mov     [rsp+218h+var_184], ecx
0x1400b6bfc  mov     ecx, [rax+8]
0x1400b6bff  mov     [rsp+218h+var_130], ecx
0x1400b6c06  mov     r13d, [rax+0Ch]
0x1400b6c0a  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1400b6c11  nop     dword ptr [rax+rax+00h]
0x1400b6c16  test    rax, rax
0x1400b6c19  jz      short loc_1400B6C61
0x1400b6c1b  mov     rcx, [rax]
0x1400b6c1e  neg     rcx
0x1400b6c21  sbb     rdx, rdx
0x1400b6c24  and     rax, rdx
0x1400b6c27  test    rax, rax
0x1400b6c2a  jz      short loc_1400B6C61
0x1400b6c2c  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1400b6c33  nop     dword ptr [rax+rax+00h]
0x1400b6c38  mov     rcx, rax
0x1400b6c3b  test    rax, rax
0x1400b6c3e  jz      short loc_1400B6C4C
0x1400b6c40  mov     rax, [rax]
0x1400b6c43  neg     rax
0x1400b6c46  sbb     rdx, rdx
0x1400b6c49  and     rcx, rdx
0x1400b6c4c  call    cs:__imp_IsImmersiveAppRestricted
0x1400b6c53  nop     dword ptr [rax+rax+00h]
0x1400b6c58  test    eax, eax
0x1400b6c5a  jz      short loc_1400B6C61
0x1400b6c5c  mov     edi, r14d
0x1400b6c5f  jmp     short loc_1400B6C63
0x1400b6c61  xor     edi, edi
0x1400b6c63  mov     rax, cs:__imp_?hModuleWin@@3PEAXEA; void * hModuleWin
0x1400b6c6a  mov     rbx, [rax]
0x1400b6c6d  xor     edx, edx
0x1400b6c6f  lea     rcx, [rsp+218h+var_48]
0x1400b6c77  call    ??0?$SmartObjStackRef@UtagMENU@@@@QEAA@H@Z; SmartObjStackRef<tagMENU>::SmartObjStackRef<tagMENU>(int)
0x1400b6c7c  mov     edx, [rsp+218h+var_184]
0x1400b6c83  sub     r13d, edx
0x1400b6c86  mov     eax, [rsp+218h+var_130]
0x1400b6c8d  mov     ecx, dword ptr [rsp+218h+Timeout]
0x1400b6c94  sub     eax, ecx
0x1400b6c96  mov     [rsp+218h+var_198], 0
0x1400b6ca2  mov     [rsp+218h+var_1A0], edi
0x1400b6ca6  mov     [rsp+218h+var_1A8], 30Ah
0x1400b6cae  mov     [rsp+218h+var_1B0], r14d
0x1400b6cb3  xor     edi, edi
0x1400b6cb5  mov     [rsp+218h+var_1B8], rdi
0x1400b6cba  mov     [rsp+218h+var_1C0], rbx
0x1400b6cbf  lea     r8, [rsp+218h+var_48]
  ... truncated ...
```
