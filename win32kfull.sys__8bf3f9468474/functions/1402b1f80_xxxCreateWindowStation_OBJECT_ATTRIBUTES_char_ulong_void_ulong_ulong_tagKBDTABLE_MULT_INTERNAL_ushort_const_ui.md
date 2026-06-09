# xxxCreateWindowStation(_OBJECT_ATTRIBUTES *,char,ulong,void *,ulong,ulong,tagKBDTABLE_MULT_INTERNAL *,ushort const *,uint,tagWINDOWSTATIONFLAGS,ulong,HWINSTA__ * *)

- ea: `0x1402b1f80`
- end: `0x1402b280b`
- name: `?xxxCreateWindowStation@@YAJPEAU_OBJECT_ATTRIBUTES@@DKPEAXKKPEAUtagKBDTABLE_MULT_INTERNAL@@PEBGIW4tagWINDOWSTATIONFLAGS@@KPEAPEAUHWINSTA__@@@Z`
- size: `2187`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, unsigned int, int, __int64, __int64, int, __int16, int, HANDLE *)`
- caller_count: `2`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140173b1c`
- `0x1402b5d80`

## callees

- `0x14002b948`
- `0x1400373d0`
- `0x1400381a8`
- `0x14005c4a0`
- `0x140077ab8`
- `0x140077cc8`
- `0x1400b1334`
- `0x1400b13c8`
- `0x1400bcaa0`
- `0x1400c138c`
- `0x1400d0bd0`
- `0x1401494f4`
- `0x140198928`
- `0x1401ffb00`
- `0x14025ad4c`
- `0x140274b90`
- `0x1402874a8`
- `0x1402878a8`
- `0x1402913f0`
- `0x1402b1f80`
- `0x1402b2814`
- `0x140342540`

## import_xrefs

- `ntoskrnl!ObInsertObject` at `0x1402b2544`
- `ntoskrnl!ObInsertObject` at `0x1402b2544`
- `ntoskrnl!RtlCopySid` at `0x1402b24ca`
- `ntoskrnl!RtlCopySid` at `0x1402b24ca`
- `ntoskrnl!SeExports` at `0x1402b245b`
- `ntoskrnl!SeExports` at `0x1402b24b9`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1402b2084`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1402b2084`
- `ntoskrnl!ObCreateObject` at `0x1402b2044`
- `ntoskrnl!ObCreateObject` at `0x1402b2044`
- `ntoskrnl!ObfReferenceObject` at `0x1402b21b3`
- `ntoskrnl!ObfReferenceObject` at `0x1402b21b3`
- `ntoskrnl!ObCloseHandle` at `0x1402b27b9`
- `ntoskrnl!ObCloseHandle` at `0x1402b27b9`
- `ntoskrnl!ExWindowStationObjectType` at `0x1402b2005`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1402b2288`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1402b229e`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1402b2288`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1402b229e`
- `ntoskrnl!RtlLengthSid` at `0x1402b246c`
- `ntoskrnl!RtlLengthSid` at `0x1402b246c`
- `ntoskrnl!ObfDereferenceObject` at `0x1402b243c`
- `ntoskrnl!ObfDereferenceObject` at `0x1402b26b7`
- `ntoskrnl!ObfDereferenceObject` at `0x1402b26f6`
- `ntoskrnl!ObfDereferenceObject` at `0x1402b27e1`
- `ntoskrnl!ObfDereferenceObject` at `0x1402b243c`
- `ntoskrnl!ObfDereferenceObject` at `0x1402b26b7`
- `ntoskrnl!ObfDereferenceObject` at `0x1402b26f6`
- `ntoskrnl!ObfDereferenceObject` at `0x1402b27e1`
- `win32kbase!?hModuleWin@@3PEAXEA` at `0x1402b22d7`
- `win32kbase!LockObjectAssignment` at `0x1402b25a8`
- `win32kbase!LockObjectAssignment` at `0x1402b25a8`
- `win32kbase!CreateSecurityDescriptor` at `0x1402b24de`
- `win32kbase!CreateSecurityDescriptor` at `0x1402b24de`
- `win32kbase!CreateGlobalAtomTable` at `0x1402b2113`
- `win32kbase!CreateGlobalAtomTable` at `0x1402b2113`
- `win32kbase!ApplySecurityAttributesToWinsta` at `0x1402b256d`
- `win32kbase!ApplySecurityAttributesToWinsta` at `0x1402b256d`
- `win32kbase!xxxSafeLoadKeyboardLayoutEx` at `0x1402b2631`
- `win32kbase!xxxSafeLoadKeyboardLayoutEx` at `0x1402b2631`
- `win32kbase!UserDereferenceObject` at `0x1402b25ff`
- `win32kbase!?SetPolicy@tagWINDOWSTATION@@QEAAXW4WindowStationPolicy@@@Z` at `0x1402b26a7`
- `win32kbase!?SetPolicy@tagWINDOWSTATION@@QEAAXW4WindowStationPolicy@@@Z` at `0x1402b26a7`
- `win32kbase!HMChangeOwnerThread` at `0x1402b23da`
- `win32kbase!HMChangeOwnerThread` at `0x1402b2760`
- `win32kbase!HMChangeOwnerThread` at `0x1402b23da`
- `win32kbase!HMChangeOwnerThread` at `0x1402b2760`
- `win32kbase!IsImmersiveAppRestricted` at `0x1402b22be`
- `win32kbase!IsImmersiveAppRestricted` at `0x1402b22be`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1402b2485`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1402b2485`
- `win32kbase!HMAssignmentLock` at `0x1402b23a7`
- `win32kbase!HMAssignmentLock` at `0x1402b23a7`
- `win32kbase!Win32FreePool` at `0x1402b24f0`
- `win32kbase!Win32FreePool` at `0x1402b2516`
- `win32kbase!Win32FreePool` at `0x1402b27cd`
- `win32kbase!Win32FreePool` at `0x1402b24f0`
- `win32kbase!Win32FreePool` at `0x1402b2516`
- `win32kbase!Win32FreePool` at `0x1402b27cd`
- `WIN32K!W32GetUserSessionState` at `0x1402b1fc3`
- `WIN32K!W32GetUserSessionState` at `0x1402b1fd9`
- `WIN32K!W32GetUserSessionState` at `0x1402b1fee`
- `WIN32K!W32GetUserSessionState` at `0x1402b2071`
- `WIN32K!W32GetUserSessionState` at `0x1402b21e9`
- `WIN32K!W32GetUserSessionState` at `0x1402b2583`
- `WIN32K!W32GetUserSessionState` at `0x1402b270a`
- `WIN32K!W32GetUserSessionState` at `0x1402b1fc3`
- `WIN32K!W32GetUserSessionState` at `0x1402b1fd9`
- `WIN32K!W32GetUserSessionState` at `0x1402b1fee`
- `WIN32K!W32GetUserSessionState` at `0x1402b2071`
- `WIN32K!W32GetUserSessionState` at `0x1402b21e9`
- `WIN32K!W32GetUserSessionState` at `0x1402b2583`
- `WIN32K!W32GetUserSessionState` at `0x1402b270a`

## pseudocode

```c
__int64 __fastcall xxxCreateWindowStation(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        int a6,
        __int64 a7,
        __int64 a8,
        int a9,
        __int16 a10,
        int a11,
        HANDLE *a12)
{
  char v12; // di
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // r9
  __int64 v19; // r14
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  unsigned int v25; // ebx
  int v27; // ebx
  struct tagTHREADINFO *v28; // rsi
  void *v29; // r15
  void *SecurityDescriptor; // r13
  struct _EX_RUNDOWN_REF *UserSessionState; // rax
  int DesktopNotificationEvent; // edi
  _QWORD *v33; // rax
  int GlobalAtomTable; // eax
  __int64 v35; // rcx
  _QWORD *v36; // r12
  struct tagTHREADINFO *v37; // rax
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // rcx
  __int64 v41; // rbx
  __int64 v42; // rdx
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // r9
  _QWORD *CurrentProcessWin32Process; // rax
  __int64 v48; // rdx
  __int64 v49; // rcx
  __int64 v50; // r8
  __int64 v51; // r9
  __int64 v52; // rax
  __int64 v53; // rcx
  int v54; // edi
  __int64 Window; // rbx
  __int64 v56; // r8
  __int64 v57; // r8
  ULONG v58; // r12d
  ULONG v59; // edi
  __int64 v60; // rax
  void *v61; // rbx
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // r9
  NTSTATUS inserted; // eax
  __int64 v66; // rdx
  __int64 v67; // rcx
  __int64 v68; // r8
  __int64 v69; // r9
  _QWORD *i; // rcx
  PVOID v71; // r13
  struct tagTHREADINFO *v72; // rax
  unsigned int v73; // ebx
  __int64 v74; // rdx
  __int64 v75; // r8
  __int64 v76; // r9
  PVOID v77; // rcx
  __int64 v78; // rax
  char v79; // r12
  __int64 v80; // rbx
  PVOID Object; // [rsp+98h] [rbp-59h] BYREF
  int v82; // [rsp+A0h] [rbp-51h]
  char v83[8]; // [rsp+A8h] [rbp-49h] BYREF
  __int64 v84; // [rsp+B0h] [rbp-41h]
  __int64 v85; // [rsp+B8h] [rbp-39h]
  HANDLE Handle; // [rsp+C0h] [rbp-31h] BYREF
  __int64 v87; // [rsp+C8h] [rbp-29h] BYREF
  __int64 v88; // [rsp+D0h] [rbp-21h]
  __int64 v89; // [rsp+D8h] [rbp-19h]
  __int64 v90; // [rsp+E8h] [rbp-9h]
  __int64 v91; // [rsp+F0h] [rbp-1h]
  char v92; // [rsp+138h] [rbp+47h]
  ACCESS_MASK DesiredAccess; // [rsp+148h] [rbp+57h]

  DesiredAccess = a3;
  v12 = a2;
  v91 = *(_QWORD *)(a1 + 32);
  Object = 0;
  Handle = 0;
  if ( *(_QWORD *)(W32GetUserSessionState(a1, a2, a3, a4) + 63288) )
  {
    v19 = W32GetUserSessionState(v15, v14, v16, v17) + 68520;
    *(_DWORD *)v19 |= 2u;
  }
  else
  {
    v19 = W32GetUserSessionState(v15, v14, v16, v17) + 68448;
  }
  LOBYTE(v18) = v12;
  v20 = ObCreateObject(0, ExWindowStationObjectType, a1, v18, 0, 232, 0, 0, &Object);
  v25 = v20;
  if ( v20 < 0 )
  {
    SetLastNtError((unsigned int)v20);
    return v25;
  }
  v27 = 0;
  v28 = 0;
  v82 = 0;
  v29 = 0;
  SecurityDescriptor = 0;
  UserSessionState = (struct _EX_RUNDOWN_REF *)W32GetUserSessionState(v22, v21, v23, v24);
  if ( !ExAcquireRundownProtection(UserSessionState + 7912) )
  {
    DesktopNotificationEvent = -1073741790;
LABEL_79:
    SetLastNtError((unsigned int)DesktopNotificationEvent);
    v77 = Object;
    if ( Object )
      ObfDereferenceObject(Object);
    if ( v27 )
    {
      v78 = W32GetUserSessionState(v77, v74, v75, v76);
      ++*(_DWORD *)(v78 + 70592);
      if ( (_InterlockedCompareExchange((volatile signed __int32 *)v28 + 130, 0, 0) & 0x10000000) != 0 )
      {
        v79 = 0;
      }
      else
      {
        v79 = 1;
        _InterlockedOr((volatile signed __int32 *)v28 + 130, 0x10000000u);
      }
      v80 = *((_QWORD *)v28 + 57);
      *((_QWORD *)v28 + 57) = *(_QWORD *)(*(_QWORD *)(v19 + 16) + 456LL);
      HMChangeOwnerThread(*(_QWORD *)(v19 + 8), v28);
      v83[0] = 0;
      v84 = 0;
      AtomicExecutionCheck::Arm((AtomicExecutionCheck *)v83);
      xxxCleanupMotherDesktopWindow((struct tagTERMINAL *)v19);
      AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v83);
      *((_QWORD *)v28 + 57) = v80;
      if ( v79 )
        _InterlockedAnd((volatile signed __int32 *)v28 + 130, 0xEFFFFFFF);
      EditionEndDeferWinEventNotify();
    }
    if ( Handle )
      ObCloseHandle(Handle, 1);
    if ( SecurityDescriptor )
      Win32FreePool(SecurityDescriptor);
    if ( v29 )
      ObfDereferenceObject(v29);
    return (unsigned int)DesktopNotificationEvent;
  }
  memset_0(Object, 0, 0xE8u);
  v33 = (char *)Object + 200;
  *((_QWORD *)Object + 26) = (char *)Object + 200;
  *v33 = v33;
  *(_DWORD *)Object = W32GetCurrentWin32kSessionId();
  *((_DWORD *)Object + 46) = a11;
  *((_QWORD *)Object + 3) = v19;
  if ( (*(_DWORD *)v19 & 2) != 0 )
  {
    *((_DWORD *)Object + 8) = 4;
  }
  else if ( (a10 & 0x800) != 0 )
  {
    *((_DWORD *)Object + 8) |= 0x800u;
  }
  GlobalAtomTable = CreateGlobalAtomTable((char *)Object + 136);
  DesktopNotificationEvent = GlobalAtomTable;
  if ( GlobalAtomTable < 0
    || (*(_DWORD *)v19 & 1) == 0
    && (GlobalAtomTable = xxxInitTerminal((struct tagTERMINAL *)v19),
        DesktopNotificationEvent = GlobalAtomTable,
        GlobalAtomTable < 0) )
  {
    v35 = (unsigned int)GlobalAtomTable;
LABEL_14:
    SetLastNtError(v35);
    goto LABEL_79;
  }
  if ( (*((_DWORD *)Object + 8) & 4) == 0 && !(unsigned int)xxxInitWindowStation() )
  {
    DesktopNotificationEvent = -1073741801;
    v35 = 3221225495LL;
    goto LABEL_14;
  }
  v36 = (_QWORD *)(v19 + 8);
  if ( !*(_QWORD *)(v19 + 8) )
  {
    v37 = PtiCurrent();
    v40 = *(_QWORD *)(v19 + 16);
    v28 = v37;
    v41 = *((_QWORD *)v37 + 57);
    v29 = (void *)*((_QWORD *)v37 + 61);
    v42 = *(_QWORD *)(v40 + 456);
    *((_QWORD *)v37 + 57) = v42;
    v85 = *((_QWORD *)v37 + 78);
    v90 = v41;
    if ( v29 )
    {
      ObfReferenceObject(v29);
    }
    else if ( *((struct tagTHREADINFO **)v37 + 96) != (struct tagTHREADINFO *)((char *)v37 + 768) )
    {
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 540);
    }
    v43 = W32GetUserSessionState(v40, v42, v38, v39);
    v83[0] = 0;
    v84 = 0;
    ++*(_DWORD *)(v43 + 70592);
    AtomicExecutionCheck::Arm((AtomicExecutionCheck *)v83);
    DesktopNotificationEvent = zzzSetDesktop(v28, 0, 0);
    if ( DesktopNotificationEvent < 0 )
    {
      if ( !*((_QWORD *)v28 + 61) && v29 )
        zzzSetDesktop(v28, v29, v85);
      AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v83);
      EditionEndDeferWinEventNotify();
      *((_QWORD *)v28 + 57) = v41;
      goto LABEL_30;
    }
    if ( (_InterlockedCompareExchange((volatile signed __int32 *)v28 + 130, 0, 0) & 0x10000000) != 0 )
    {
      v92 = 0;
    }
    else
    {
      v92 = 1;
      _InterlockedOr((volatile signed __int32 *)v28 + 130, 0x10000000u);
    }
    CurrentProcessWin32Process = (_QWORD *)PsGetCurrentProcessWin32Process(0x10000000, v44, v45, v46);
    if ( !CurrentProcessWin32Process || !*CurrentProcessWin32Process )
      goto LABEL_40;
    v52 = PsGetCurrentProcessWin32Process(v49, v48, v50, v51);
    v53 = v52;
    if ( v52 )
      v53 = ((unsigned __int128)-(__int128)*(unsigned __int64 *)v52 >> 64) & v52;
    if ( (unsigned int)IsImmersiveAppRestricted(v53) )
      v54 = 1;
    else
LABEL_40:
      v54 = 0;
    SmartObjStackRef<tagMENU>::SmartObjStackRef<tagMENU>(&v87, 0);
    Window = xxxCreateWindowEx(
               0,
               32769,
               32769,
               0,
               -2113929216,
               -32768,
               -32768,
               0xFFFF,
               0xFFFF,
               0,
               (__int64)&v87,
               (__int64)hModuleWin,
               0,
               1,
               778,
               v54,
               0);
    SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(&v87);
    if ( !Window )
    {
      DesktopNotificationEvent = -1073741801;
      AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v83);
      EditionEndDeferWinEventNotify();
      v56 = v85;
      *((_QWORD *)v28 + 57) = v90;
      zzzSetDesktop(v28, v29, v56);
LABEL_30:
      AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v83);
      v27 = 0;
      goto LABEL_79;
    }
    v87 = v19 + 8;
    v88 = Window;
    HMAssignmentLock(&v87, 0);
    if ( v92 )
      _InterlockedAnd((volatile signed __int32 *)v28 + 130, 0xEFFFFFFF);
    SetVisible(*v36, 1);
    HMChangeOwnerThread(*v36, *(_QWORD *)(v19 + 16));
    v27 = 1;
    v57 = v85;
    *((_QWORD *)v28 + 57) = v90;
    v82 = 1;
    DesktopNotificationEvent = zzzSetDesktop(v28, v29, v57);
    if ( DesktopNotificationEvent < 0 )
    {
      AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v83);
      EditionEndDeferWinEventNotify();
      AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v83);
      goto LABEL_79;
    }
    AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v83);
    EditionEndDeferWinEventNotify();
    if ( v29 )
    {
      ObfDereferenceObject(v29);
      v29 = 0;
    }
  }
  if ( (*((_DWORD *)Object + 8) & 4) == 0 )
  {
    v58 = RtlLengthSid(SeExports->SeWorldSid);
    v59 = v58 + 8;
    v60 = Win32AllocPoolWithQuotaZInit(v58 + 8, 1702064981);
    v61 = (void *)v60;
    if ( v60
      && (*(_WORD *)v60 = 0,
          *(_WORD *)(v60 + 2) = v59,
          *(_DWORD *)(v60 + 4) = 0x100000,
          RtlCopySid(v58, (PSID)(v60 + 8), SeExports->SeWorldSid),
          SecurityDescriptor = (void *)CreateSecurityDescriptor(v61, v59, 0),
          Win32FreePool(v61),
          SecurityDescriptor) )
    {
      DesktopNotificationEvent = CreateDesktopNotificationEvent(SecurityDescriptor, v62, v63, v64);
      if ( DesktopNotificationEvent >= 0 )
      {
        Win32FreePool(SecurityDescriptor);
        goto LABEL_55;
      }
    }
    else
    {
      DesktopNotificationEvent = -1073741801;
    }
LABEL_78:
    v27 = v82;
    goto LABEL_79;
  }
LABEL_55:
  inserted = ObInsertObject(Object, 0, DesiredAccess, 1u, &Object, &Handle);
  DesktopNotificationEvent = inserted;
  if ( inserted < 0 )
  {
    Object = 0;
LABEL_77:
    SecurityDescriptor = 0;
    goto LABEL_78;
  }
  if ( inserted != 0x40000000 )
  {
    DesktopNotificationEvent = ApplySecurityAttributesToWinsta(Object, v91);
    if ( DesktopNotificationEvent < 0 )
      goto LABEL_77;
    for ( i = (_QWORD *)(W32GetUserSessionState(v67, v66, v68, v69) + 63288); *i; i = (_QWORD *)(*i + 8LL) )
      ;
    LockObjectAssignment(i, Object);
    v71 = Object;
    if ( (*((_DWORD *)Object + 8) & 4) == 0 && a8 )
    {
      v72 = PtiCurrent();
      v87 = *((_QWORD *)v72 + 47);
      *((_QWORD *)v72 + 47) = &v87;
      v89 = UserDereferenceObject;
      v88 = (__int64)v71;
      if ( !xxxSafeLoadKeyboardLayoutEx(Object, a4, 0, a5, a6, a7, a8, a9, -2147483647) )
        DesktopNotificationEvent = -1073741823;
      *((_QWORD *)PtiCurrent() + 47) = v87;
    }
    if ( DesktopNotificationEvent < 0 )
      goto LABEL_77;
  }
  if ( !(unsigned int)IsCurrentSessionServiceSession() && (*((_DWORD *)Object + 8) & 0x804) == 0 )
  {
    v73 = Feature_AgenticSessionNoBoostPolicy__private_IsEnabledDeviceUsageNoInline() != 0;
    if ( (unsigned int)Feature_AgenticSessionCapQoSPolicy__private_IsEnabledDeviceUsageNoInline() )
      v73 |= 2u;
    if ( (unsigned int)Feature_LowLatencyProfile__private_IsEnabledDeviceUsageNoInline() )
      v73 |= 4u;
    if ( v73 )
      tagWINDOWSTATION::SetPolicy(Object, v73);
  }
  ObfDereferenceObject(Object);
  *a12 = Handle;
  return 0;
}

```

## disassembly

```asm
0x1402b1f80  mov     rax, rsp
0x1402b1f83  mov     [rax+10h], rbx
0x1402b1f87  mov     [rax+20h], r9
0x1402b1f8b  mov     [rax+18h], r8d
0x1402b1f8f  push    rbp
0x1402b1f90  push    rsi
0x1402b1f91  push    rdi
0x1402b1f92  push    r12
0x1402b1f94  push    r13
0x1402b1f96  push    r14
0x1402b1f98  push    r15
0x1402b1f9a  lea     rbp, [rax-3Fh]
0x1402b1f9e  sub     rsp, 0F0h
0x1402b1fa5  mov     rax, [rcx+20h]
0x1402b1fa9  mov     dil, dl
0x1402b1fac  mov     [rbp+37h+var_38], rax
0x1402b1fb0  mov     rbx, rcx
0x1402b1fb3  mov     [rbp+37h+Object], 0
0x1402b1fbb  mov     [rbp+37h+var_68], 0
0x1402b1fc3  call    cs:__imp_W32GetUserSessionState
0x1402b1fca  nop     dword ptr [rax+rax+00h]
0x1402b1fcf  cmp     qword ptr [rax+0F738h], 0
0x1402b1fd7  jnz     short loc_1402B1FEE
0x1402b1fd9  call    cs:__imp_W32GetUserSessionState
0x1402b1fe0  nop     dword ptr [rax+rax+00h]
0x1402b1fe5  lea     r14, [rax+10B60h]
0x1402b1fec  jmp     short loc_1402B2005
0x1402b1fee  call    cs:__imp_W32GetUserSessionState
0x1402b1ff5  nop     dword ptr [rax+rax+00h]
0x1402b1ffa  lea     r14, [rax+10BA8h]
0x1402b2001  or      dword ptr [r14], 2
0x1402b2005  mov     rdx, cs:__imp_ExWindowStationObjectType
0x1402b200c  lea     rax, [rbp+37h+Object]
0x1402b2010  mov     [rsp+120h+var_E0], rax
0x1402b2015  mov     r12d, 0E8h
0x1402b201b  mov     dword ptr [rsp+120h+var_E8], 0
0x1402b2023  mov     r9b, dil
0x1402b2026  mov     [rsp+120h+var_F0], 0
0x1402b202e  mov     r8, rbx
0x1402b2031  mov     rdx, [rdx]
0x1402b2034  xor     ecx, ecx
0x1402b2036  mov     dword ptr [rsp+120h+Handle], r12d
0x1402b203b  mov     [rsp+120h+NewObject], 0
0x1402b2044  call    cs:__imp_ObCreateObject
0x1402b204b  nop     dword ptr [rax+rax+00h]
0x1402b2050  mov     ebx, eax
0x1402b2052  test    eax, eax
0x1402b2054  jns     short loc_1402B2064
0x1402b2056  mov     ecx, eax
0x1402b2058  call    SetLastNtError
0x1402b205d  mov     eax, ebx
0x1402b205f  jmp     loc_1402B27EF
0x1402b2064  xor     ebx, ebx
0x1402b2066  xor     esi, esi
0x1402b2068  mov     [rbp+37h+var_88], ebx
0x1402b206b  xor     r15d, r15d
0x1402b206e  xor     r13d, r13d
0x1402b2071  call    cs:__imp_W32GetUserSessionState
0x1402b2078  nop     dword ptr [rax+rax+00h]
0x1402b207d  lea     rcx, [rax+0F740h]; RunRef
0x1402b2084  call    cs:__imp_ExAcquireRundownProtection
0x1402b208b  nop     dword ptr [rax+rax+00h]
0x1402b2090  test    al, al
0x1402b2092  jnz     short loc_1402B209E
0x1402b2094  mov     edi, 0C0000022h
0x1402b2099  jmp     loc_1402B26E6
0x1402b209e  mov     rcx, [rbp+37h+Object]; void *
0x1402b20a2  mov     r8, r12; Size
0x1402b20a5  xor     edx, edx; Val
0x1402b20a7  call    memset_0
0x1402b20ac  mov     rax, [rbp+37h+Object]
0x1402b20b0  add     rax, 0C8h
0x1402b20b6  mov     [rax+8], rax
0x1402b20ba  mov     [rax], rax
0x1402b20bd  call    W32GetCurrentWin32kSessionId
0x1402b20c2  mov     rcx, [rbp+37h+Object]
0x1402b20c6  mov     [rcx], eax
0x1402b20c8  mov     rax, [rbp+37h+Object]
0x1402b20cc  mov     ecx, [rbp+37h+arg_50]
0x1402b20d2  mov     [rax+0B8h], ecx
0x1402b20d8  mov     rax, [rbp+37h+Object]
0x1402b20dc  mov     [rax+18h], r14
0x1402b20e0  mov     eax, [r14]
0x1402b20e3  test    al, 2
0x1402b20e5  jz      short loc_1402B20F4
0x1402b20e7  mov     rax, [rbp+37h+Object]
0x1402b20eb  mov     dword ptr [rax+20h], 4
0x1402b20f2  jmp     short loc_1402B2108
0x1402b20f4  mov     ecx, 800h
0x1402b20f9  test    dword ptr [rbp+37h+arg_48], ecx
0x1402b20ff  jz      short loc_1402B2108
0x1402b2101  mov     rax, [rbp+37h+Object]
0x1402b2105  or      [rax+20h], ecx
0x1402b2108  mov     rcx, [rbp+37h+Object]
0x1402b210c  add     rcx, 88h
0x1402b2113  call    cs:__imp_CreateGlobalAtomTable
0x1402b211a  nop     dword ptr [rax+rax+00h]
0x1402b211f  mov     edi, eax
0x1402b2121  test    eax, eax
0x1402b2123  jns     short loc_1402B2131
0x1402b2125  mov     ecx, eax
0x1402b2127  call    SetLastNtError
0x1402b212c  jmp     loc_1402B26E6
0x1402b2131  mov     eax, [r14]
0x1402b2134  test    al, 1
0x1402b2136  jnz     short loc_1402B2146
0x1402b2138  mov     rcx, r14; struct tagTERMINAL *
0x1402b213b  call    ?xxxInitTerminal@@YAJPEAUtagTERMINAL@@@Z; xxxInitTerminal(tagTERMINAL *)
0x1402b2140  mov     edi, eax
0x1402b2142  test    eax, eax
0x1402b2144  js      short loc_1402B2125
0x1402b2146  mov     rax, [rbp+37h+Object]
0x1402b214a  mov     ecx, [rax+20h]
0x1402b214d  test    cl, 4
0x1402b2150  jnz     short loc_1402B2164
0x1402b2152  call    xxxInitWindowStation
0x1402b2157  test    eax, eax
0x1402b2159  jnz     short loc_1402B2164
0x1402b215b  mov     edi, 0C0000017h
0x1402b2160  mov     ecx, edi
0x1402b2162  jmp     short loc_1402B2127
0x1402b2164  lea     r12, [r14+8]
0x1402b2168  xor     edi, edi
0x1402b216a  cmp     [r12], rdi
0x1402b216e  jnz     loc_1402B244B
0x1402b2174  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1402b2179  mov     rcx, [r14+10h]
0x1402b217d  mov     rsi, rax
0x1402b2180  mov     rbx, [rax+1C8h]
0x1402b2187  mov     r15, [rax+1E8h]
0x1402b218e  mov     rdx, [rcx+1C8h]
0x1402b2195  mov     [rax+1C8h], rdx
0x1402b219c  mov     rax, [rax+270h]
0x1402b21a3  mov     [rbp+37h+var_70], rax
0x1402b21a7  mov     [rbp+37h+var_40], rbx
0x1402b21ab  test    r15, r15
0x1402b21ae  jz      short loc_1402B21C1
0x1402b21b0  mov     rcx, r15; Object
0x1402b21b3  call    cs:__imp_ObfReferenceObject
0x1402b21ba  nop     dword ptr [rax+rax+00h]
0x1402b21bf  jmp     short loc_1402B21E9
0x1402b21c1  lea     rax, [rsi+300h]
0x1402b21c8  cmp     [rax], rax
0x1402b21cb  jz      short loc_1402B21E9
0x1402b21cd  mov     [rbp+37h+arg_0], 20000h
0x1402b21d4  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1402b21db  mov     edx, [rbp+37h+arg_0]
0x1402b21de  mov     r8d, 21Ch
0x1402b21e4  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1402b21e9  call    cs:__imp_W32GetUserSessionState
0x1402b21f0  nop     dword ptr [rax+rax+00h]
0x1402b21f5  lea     rcx, [rbp+37h+var_80]; this
0x1402b21f9  mov     [rbp+37h+var_80], dil
0x1402b21fd  mov     [rbp+37h+var_78], rdi
0x1402b2201  inc     dword ptr [rax+113C0h]
0x1402b2207  call    ?Arm@AtomicExecutionCheck@@QEAAXXZ; AtomicExecutionCheck::Arm(void)
0x1402b220c  xor     r8d, r8d
0x1402b220f  xor     edx, edx
0x1402b2211  mov     rcx, rsi
0x1402b2214  call    zzzSetDesktop
0x1402b2219  mov     edi, eax
0x1402b221b  test    eax, eax
0x1402b221d  jns     short loc_1402B2262
0x1402b221f  cmp     [rsi+1E8h], r13
0x1402b2226  jnz     short loc_1402B223C
0x1402b2228  test    r15, r15
0x1402b222b  jz      short loc_1402B223C
0x1402b222d  mov     r8, [rbp+37h+var_70]
0x1402b2231  mov     rdx, r15
0x1402b2234  mov     rcx, rsi
0x1402b2237  call    zzzSetDesktop
0x1402b223c  lea     rcx, [rbp+37h+var_80]; this
0x1402b2240  call    ?Disarm@AtomicExecutionCheck@@QEAAXXZ; AtomicExecutionCheck::Disarm(void)
0x1402b2245  call    EditionEndDeferWinEventNotify
0x1402b224a  mov     [rsi+1C8h], rbx
0x1402b2251  lea     rcx, [rbp+37h+var_80]; this
0x1402b2255  call    ?Disarm@AtomicExecutionCheck@@QEAAXXZ; AtomicExecutionCheck::Disarm(void)
0x1402b225a  mov     ebx, r13d
0x1402b225d  jmp     loc_1402B26E6
0x1402b2262  xor     ecx, ecx
0x1402b2264  xor     eax, eax
0x1402b2266  lock cmpxchg [rsi+208h], ecx
0x1402b226e  mov     ecx, 10000000h
0x1402b2273  test    ecx, eax
0x1402b2275  jnz     short loc_1402B2284
0x1402b2277  mov     byte ptr [rbp+37h+arg_0], 1
0x1402b227b  lock or [rsi+208h], ecx
0x1402b2282  jmp     short loc_1402B2288
0x1402b2284  mov     byte ptr [rbp+37h+arg_0], r13b
0x1402b2288  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1402b228f  nop     dword ptr [rax+rax+00h]
0x1402b2294  test    rax, rax
0x1402b2297  jz      short loc_1402B22D5
0x1402b2299  cmp     [rax], r13
0x1402b229c  jz      short loc_1402B22D5
0x1402b229e  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1402b22a5  nop     dword ptr [rax+rax+00h]
0x1402b22aa  mov     rcx, rax
0x1402b22ad  test    rax, rax
0x1402b22b0  jz      short loc_1402B22BE
0x1402b22b2  mov     rax, [rax]
0x1402b22b5  neg     rax
0x1402b22b8  sbb     rdx, rdx
0x1402b22bb  and     rcx, rdx
0x1402b22be  call    cs:__imp_IsImmersiveAppRestricted
0x1402b22c5  nop     dword ptr [rax+rax+00h]
0x1402b22ca  test    eax, eax
0x1402b22cc  jz      short loc_1402B22D5
0x1402b22ce  mov     edi, 1
0x1402b22d3  jmp     short loc_1402B22D7
0x1402b22d5  xor     edi, edi
0x1402b22d7  mov     rax, cs:__imp_?hModuleWin@@3PEAXEA; void * hModuleWin
0x1402b22de  lea     rcx, [rbp+37h+var_60]
0x1402b22e2  xor     edx, edx
0x1402b22e4  mov     rbx, [rax]
0x1402b22e7  call    ??0?$SmartObjStackRef@UtagMENU@@@@QEAA@H@Z; SmartObjStackRef<tagMENU>::SmartObjStackRef<tagMENU>(int)
0x1402b22ec  mov     [rsp+80h], r13
0x1402b22f4  lea     rax, [rbp+37h+var_60]
0x1402b22f8  mov     dword ptr [rsp+120h+var_A8], edi
0x1402b22fc  mov     edx, 8001h
0x1402b2301  mov     [rsp+120h+var_B0], 30Ah
0x1402b2309  xor     edi, edi
0x1402b230b  mov     [rsp+120h+var_B8], 1
0x1402b2313  xor     r9d, r9d
0x1402b2316  mov     qword ptr [rsp+120h+var_C0], rdi
0x1402b231b  mov     r8d, edx
0x1402b231e  mov     [rsp+120h+var_C8], rbx
0x1402b2323  xor     ecx, ecx
0x1402b2325  mov     [rsp+120h+var_D0], rax
0x1402b232a  mov     eax, 0FFFFh
0x1402b232f  mov     [rsp+120h+var_D8], rdi
0x1402b2334  mov     dword ptr [rsp+120h+var_E0], eax
0x1402b2338  mov     dword ptr [rsp+120h+var_E8], eax
0x1402b233c  mov     eax, 0FFFF8000h
0x1402b2341  mov     [rsp+120h+var_F0], eax
0x1402b2345  mov     dword ptr [rsp+120h+Handle], eax
0x1402b2349  mov     dword ptr [rsp+120h+NewObject], 82000000h
0x1402b2351  call    xxxCreateWindowEx
0x1402b2356  lea     rcx, [rbp+37h+var_60]
0x1402b235a  mov     rbx, rax
0x1402b235d  call    ??1?$SmartObjStackRef@UtagMENU@@@@QEAA@XZ; SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(void)
0x1402b2362  test    rbx, rbx
0x1402b2365  jnz     short loc_1402B2399
0x1402b2367  lea     rcx, [rbp+37h+var_80]; this
0x1402b236b  mov     edi, 0C0000017h
0x1402b2370  call    ?Disarm@AtomicExecutionCheck@@QEAAXXZ; AtomicExecutionCheck::Disarm(void)
0x1402b2375  call    EditionEndDeferWinEventNotify
0x1402b237a  mov     rax, [rbp+37h+var_40]
0x1402b237e  mov     rdx, r15
0x1402b2381  mov     r8, [rbp+37h+var_70]
0x1402b2385  mov     rcx, rsi
0x1402b2388  mov     [rsi+1C8h], rax
0x1402b238f  call    zzzSetDesktop
0x1402b2394  jmp     loc_1402B2251
0x1402b2399  xor     edx, edx
0x1402b239b  mov     [rbp+37h+var_60], r12
0x1402b239f  lea     rcx, [rbp+37h+var_60]
0x1402b23a3  mov     [rbp+37h+var_58], rbx
0x1402b23a7  call    cs:__imp_HMAssignmentLock
0x1402b23ae  nop     dword ptr [rax+rax+00h]
0x1402b23b3  cmp     byte ptr [rbp+37h+arg_0], dil
0x1402b23b7  jz      short loc_1402B23C4
0x1402b23b9  lock and dword ptr [rsi+208h], 0EFFFFFFFh
0x1402b23c4  mov     rcx, [r12]
0x1402b23c8  mov     edx, 1
0x1402b23cd  call    ?SetVisible@@YA_NPEAUtagWND@@W4SetVisibleOptions@@@Z; SetVisible(tagWND *,SetVisibleOptions)
0x1402b23d2  mov     rdx, [r14+10h]
0x1402b23d6  mov     rcx, [r12]
0x1402b23da  call    cs:__imp_HMChangeOwnerThread
0x1402b23e1  nop     dword ptr [rax+rax+00h]
0x1402b23e6  mov     rax, [rbp+37h+var_40]
0x1402b23ea  mov     ebx, 1
0x1402b23ef  mov     r8, [rbp+37h+var_70]
0x1402b23f3  mov     rdx, r15
0x1402b23f6  mov     rcx, rsi
0x1402b23f9  mov     [rsi+1C8h], rax
0x1402b2400  mov     [rbp+37h+var_88], ebx
0x1402b2403  call    zzzSetDesktop
0x1402b2408  lea     rcx, [rbp+37h+var_80]; this
0x1402b240c  mov     edi, eax
0x1402b240e  test    eax, eax
0x1402b2410  jns     short loc_1402B242A
0x1402b2412  call    ?Disarm@AtomicExecutionCheck@@QEAAXXZ; AtomicExecutionCheck::Disarm(void)
0x1402b2417  call    EditionEndDeferWinEventNotify
0x1402b241c  lea     rcx, [rbp+37h+var_80]; this
0x1402b2420  call    ?Disarm@AtomicExecutionCheck@@QEAAXXZ; AtomicExecutionCheck::Disarm(void)
0x1402b2425  jmp     loc_1402B26E6
0x1402b242a  call    ?Disarm@AtomicExecutionCheck@@QEAAXXZ; AtomicExecutionCheck::Disarm(void)
0x1402b242f  call    EditionEndDeferWinEventNotify
0x1402b2434  test    r15, r15
0x1402b2437  jz      short loc_1402B244B
0x1402b2439  mov     rcx, r15; Object
0x1402b243c  call    cs:__imp_ObfDereferenceObject
0x1402b2443  nop     dword ptr [rax+rax+00h]
0x1402b2448  xor     r15d, r15d
0x1402b244b  mov     rax, [rbp+37h+Object]
0x1402b244f  mov     ecx, [rax+20h]
0x1402b2452  test    cl, 4
0x1402b2455  jnz     loc_1402B2522
0x1402b245b  mov     rax, cs:__imp_SeExports
  ... truncated ...
```
