# xxxCreateWindowStation(_OBJECT_ATTRIBUTES *,char,ulong,void *,ulong,ulong,tagKBDTABLE_MULT_INTERNAL *,ushort const *,uint,tagWINDOWSTATIONFLAGS,ulong,HWINSTA__ * *)

- ea: `0x1402b3930`
- end: `0x1402b41bb`
- name: `?xxxCreateWindowStation@@YAJPEAU_OBJECT_ATTRIBUTES@@DKPEAXKKPEAUtagKBDTABLE_MULT_INTERNAL@@PEBGIW4tagWINDOWSTATIONFLAGS@@KPEAPEAUHWINSTA__@@@Z`
- size: `2187`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, unsigned int, int, __int64, __int64, int, __int16, int, HANDLE *)`
- caller_count: `2`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400b604c`
- `0x1402b7a90`

## callees

- `0x140005a18`
- `0x140026888`
- `0x140032d50`
- `0x140033b58`
- `0x140097650`
- `0x1400a4824`
- `0x1400a4a38`
- `0x1400b8df0`
- `0x1400d75c4`
- `0x1400d7658`
- `0x1400e2cb0`
- `0x1400e759c`
- `0x14013f4b4`
- `0x140200500`
- `0x14025c440`
- `0x14027821c`
- `0x140288e68`
- `0x140289268`
- `0x1402938dc`
- `0x1402b3930`
- `0x1402b41c4`
- `0x140343500`

## import_xrefs

- `ntoskrnl!ObInsertObject` at `0x1402b3ef4`
- `ntoskrnl!ObInsertObject` at `0x1402b3ef4`
- `ntoskrnl!RtlCopySid` at `0x1402b3e7a`
- `ntoskrnl!RtlCopySid` at `0x1402b3e7a`
- `ntoskrnl!SeExports` at `0x1402b3e0b`
- `ntoskrnl!SeExports` at `0x1402b3e69`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1402b3a34`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1402b3a34`
- `ntoskrnl!ObCreateObject` at `0x1402b39f4`
- `ntoskrnl!ObCreateObject` at `0x1402b39f4`
- `ntoskrnl!ObfReferenceObject` at `0x1402b3b63`
- `ntoskrnl!ObfReferenceObject` at `0x1402b3b63`
- `ntoskrnl!ObCloseHandle` at `0x1402b4169`
- `ntoskrnl!ObCloseHandle` at `0x1402b4169`
- `ntoskrnl!ExWindowStationObjectType` at `0x1402b39b5`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1402b3c38`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1402b3c4e`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1402b3c38`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1402b3c4e`
- `ntoskrnl!RtlLengthSid` at `0x1402b3e1c`
- `ntoskrnl!RtlLengthSid` at `0x1402b3e1c`
- `ntoskrnl!ObfDereferenceObject` at `0x1402b3dec`
- `ntoskrnl!ObfDereferenceObject` at `0x1402b4067`
- `ntoskrnl!ObfDereferenceObject` at `0x1402b40a6`
- `ntoskrnl!ObfDereferenceObject` at `0x1402b4191`
- `ntoskrnl!ObfDereferenceObject` at `0x1402b3dec`
- `ntoskrnl!ObfDereferenceObject` at `0x1402b4067`
- `ntoskrnl!ObfDereferenceObject` at `0x1402b40a6`
- `ntoskrnl!ObfDereferenceObject` at `0x1402b4191`
- `win32kbase!?hModuleWin@@3PEAXEA` at `0x1402b3c87`
- `win32kbase!LockObjectAssignment` at `0x1402b3f58`
- `win32kbase!LockObjectAssignment` at `0x1402b3f58`
- `win32kbase!CreateSecurityDescriptor` at `0x1402b3e8e`
- `win32kbase!CreateSecurityDescriptor` at `0x1402b3e8e`
- `win32kbase!CreateGlobalAtomTable` at `0x1402b3ac3`
- `win32kbase!CreateGlobalAtomTable` at `0x1402b3ac3`
- `win32kbase!ApplySecurityAttributesToWinsta` at `0x1402b3f1d`
- `win32kbase!ApplySecurityAttributesToWinsta` at `0x1402b3f1d`
- `win32kbase!xxxSafeLoadKeyboardLayoutEx` at `0x1402b3fe1`
- `win32kbase!xxxSafeLoadKeyboardLayoutEx` at `0x1402b3fe1`
- `win32kbase!UserDereferenceObject` at `0x1402b3faf`
- `win32kbase!?SetPolicy@tagWINDOWSTATION@@QEAAXW4WindowStationPolicy@@@Z` at `0x1402b4057`
- `win32kbase!?SetPolicy@tagWINDOWSTATION@@QEAAXW4WindowStationPolicy@@@Z` at `0x1402b4057`
- `win32kbase!HMChangeOwnerThread` at `0x1402b3d8a`
- `win32kbase!HMChangeOwnerThread` at `0x1402b4110`
- `win32kbase!HMChangeOwnerThread` at `0x1402b3d8a`
- `win32kbase!HMChangeOwnerThread` at `0x1402b4110`
- `win32kbase!IsImmersiveAppRestricted` at `0x1402b3c6e`
- `win32kbase!IsImmersiveAppRestricted` at `0x1402b3c6e`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1402b3e35`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1402b3e35`
- `win32kbase!HMAssignmentLock` at `0x1402b3d57`
- `win32kbase!HMAssignmentLock` at `0x1402b3d57`
- `win32kbase!Win32FreePool` at `0x1402b3ea0`
- `win32kbase!Win32FreePool` at `0x1402b3ec6`
- `win32kbase!Win32FreePool` at `0x1402b417d`
- `win32kbase!Win32FreePool` at `0x1402b3ea0`
- `win32kbase!Win32FreePool` at `0x1402b3ec6`
- `win32kbase!Win32FreePool` at `0x1402b417d`
- `WIN32K!W32GetUserSessionState` at `0x1402b3973`
- `WIN32K!W32GetUserSessionState` at `0x1402b3989`
- `WIN32K!W32GetUserSessionState` at `0x1402b399e`
- `WIN32K!W32GetUserSessionState` at `0x1402b3a21`
- `WIN32K!W32GetUserSessionState` at `0x1402b3b99`
- `WIN32K!W32GetUserSessionState` at `0x1402b3f33`
- `WIN32K!W32GetUserSessionState` at `0x1402b40ba`
- `WIN32K!W32GetUserSessionState` at `0x1402b3973`
- `WIN32K!W32GetUserSessionState` at `0x1402b3989`
- `WIN32K!W32GetUserSessionState` at `0x1402b399e`
- `WIN32K!W32GetUserSessionState` at `0x1402b3a21`
- `WIN32K!W32GetUserSessionState` at `0x1402b3b99`
- `WIN32K!W32GetUserSessionState` at `0x1402b3f33`
- `WIN32K!W32GetUserSessionState` at `0x1402b40ba`

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
  _QWORD *v19; // r14
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
  NTSTATUS GlobalAtomTable; // eax
  __int64 v35; // rcx
  _QWORD *v36; // r12
  struct tagTHREADINFO *v37; // rax
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // rcx
  __int64 v41; // rbx
  __int64 v42; // rdx
  __int64 v43; // rax
  _QWORD *CurrentProcessWin32Process; // rax
  __int64 v45; // rax
  __int64 v46; // rcx
  char v47; // di
  __int64 Window; // rbx
  __int64 v49; // r8
  __int64 v50; // r8
  ULONG v51; // r12d
  ULONG v52; // edi
  __int64 v53; // rax
  void *v54; // rbx
  NTSTATUS inserted; // eax
  __int64 v56; // rdx
  __int64 v57; // rcx
  __int64 v58; // r8
  __int64 v59; // r9
  _QWORD *i; // rcx
  PVOID v61; // r13
  struct tagTHREADINFO *v62; // rax
  unsigned int v63; // ebx
  __int64 v64; // rdx
  __int64 v65; // r8
  __int64 v66; // r9
  PVOID v67; // rcx
  __int64 v68; // rax
  char v69; // r12
  __int64 v70; // rbx
  PVOID Object; // [rsp+98h] [rbp-59h] BYREF
  int v72; // [rsp+A0h] [rbp-51h]
  char v73[8]; // [rsp+A8h] [rbp-49h] BYREF
  __int64 v74; // [rsp+B0h] [rbp-41h]
  __int64 v75; // [rsp+B8h] [rbp-39h]
  HANDLE Handle; // [rsp+C0h] [rbp-31h] BYREF
  _QWORD *v77; // [rsp+C8h] [rbp-29h] BYREF
  __int64 v78; // [rsp+D0h] [rbp-21h]
  __int64 v79; // [rsp+D8h] [rbp-19h]
  __int64 v80; // [rsp+E8h] [rbp-9h]
  __int64 v81; // [rsp+F0h] [rbp-1h]
  char v82; // [rsp+138h] [rbp+47h]
  ACCESS_MASK DesiredAccess; // [rsp+148h] [rbp+57h]

  DesiredAccess = a3;
  v12 = a2;
  v81 = *(_QWORD *)(a1 + 32);
  Object = 0;
  Handle = 0;
  if ( *(_QWORD *)(W32GetUserSessionState(a1, a2, a3, a4) + 63288) )
  {
    v19 = (_QWORD *)(W32GetUserSessionState(v15, v14, v16, v17) + 68520);
    *(_DWORD *)v19 |= 2u;
  }
  else
  {
    v19 = (_QWORD *)(W32GetUserSessionState(v15, v14, v16, v17) + 68448);
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
  v72 = 0;
  v29 = 0;
  SecurityDescriptor = 0;
  UserSessionState = (struct _EX_RUNDOWN_REF *)W32GetUserSessionState(v22, v21, v23, v24);
  if ( !ExAcquireRundownProtection(UserSessionState + 7912) )
  {
    DesktopNotificationEvent = -1073741790;
LABEL_79:
    SetLastNtError((unsigned int)DesktopNotificationEvent);
    v67 = Object;
    if ( Object )
      ObfDereferenceObject(Object);
    if ( v27 )
    {
      v68 = W32GetUserSessionState(v67, v64, v65, v66);
      ++*(_DWORD *)(v68 + 70592);
      if ( (_InterlockedCompareExchange((volatile signed __int32 *)v28 + 130, 0, 0) & 0x10000000) != 0 )
      {
        v69 = 0;
      }
      else
      {
        v69 = 1;
        _InterlockedOr((volatile signed __int32 *)v28 + 130, 0x10000000u);
      }
      v70 = *((_QWORD *)v28 + 57);
      *((_QWORD *)v28 + 57) = *(_QWORD *)(v19[2] + 456LL);
      HMChangeOwnerThread(v19[1], v28);
      v73[0] = 0;
      v74 = 0;
      AtomicExecutionCheck::Arm((AtomicExecutionCheck *)v73);
      xxxCleanupMotherDesktopWindow((struct tagTERMINAL *)v19);
      AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v73);
      *((_QWORD *)v28 + 57) = v70;
      if ( v69 )
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
  v36 = v19 + 1;
  if ( !v19[1] )
  {
    v37 = PtiCurrent();
    v40 = v19[2];
    v28 = v37;
    v41 = *((_QWORD *)v37 + 57);
    v29 = (void *)*((_QWORD *)v37 + 61);
    v42 = *(_QWORD *)(v40 + 456);
    *((_QWORD *)v37 + 57) = v42;
    v75 = *((_QWORD *)v37 + 78);
    v80 = v41;
    if ( v29 )
    {
      ObfReferenceObject(v29);
    }
    else if ( *((struct tagTHREADINFO **)v37 + 96) != (struct tagTHREADINFO *)((char *)v37 + 768) )
    {
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 540);
    }
    v43 = W32GetUserSessionState(v40, v42, v38, v39);
    v73[0] = 0;
    v74 = 0;
    ++*(_DWORD *)(v43 + 70592);
    AtomicExecutionCheck::Arm((AtomicExecutionCheck *)v73);
    DesktopNotificationEvent = zzzSetDesktop(v28, 0, 0);
    if ( DesktopNotificationEvent < 0 )
    {
      if ( !*((_QWORD *)v28 + 61) && v29 )
        zzzSetDesktop(v28, v29, v75);
      AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v73);
      EditionEndDeferWinEventNotify();
      *((_QWORD *)v28 + 57) = v41;
      goto LABEL_30;
    }
    if ( (_InterlockedCompareExchange((volatile signed __int32 *)v28 + 130, 0, 0) & 0x10000000) != 0 )
    {
      v82 = 0;
    }
    else
    {
      v82 = 1;
      _InterlockedOr((volatile signed __int32 *)v28 + 130, 0x10000000u);
    }
    CurrentProcessWin32Process = (_QWORD *)PsGetCurrentProcessWin32Process();
    if ( !CurrentProcessWin32Process || !*CurrentProcessWin32Process )
      goto LABEL_40;
    v45 = PsGetCurrentProcessWin32Process();
    v46 = v45;
    if ( v45 )
      v46 = ((unsigned __int128)-(__int128)*(unsigned __int64 *)v45 >> 64) & v45;
    if ( (unsigned int)IsImmersiveAppRestricted(v46) )
      v47 = 1;
    else
LABEL_40:
      v47 = 0;
    SmartObjStackRef<tagMENU>::SmartObjStackRef<tagMENU>(&v77, 0);
    Window = xxxCreateWindowEx(
               0,
               (wchar_t *)0x8001,
               32769,
               0,
               0x82000000,
               -32768,
               -32768,
               0xFFFF,
               0xFFFFu,
               0,
               (__int64)&v77,
               hModuleWin,
               0,
               1u,
               0x30Au,
               v47,
               0);
    SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(&v77);
    if ( !Window )
    {
      DesktopNotificationEvent = -1073741801;
      AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v73);
      EditionEndDeferWinEventNotify();
      v49 = v75;
      *((_QWORD *)v28 + 57) = v80;
      zzzSetDesktop(v28, v29, v49);
LABEL_30:
      AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v73);
      v27 = 0;
      goto LABEL_79;
    }
    v77 = v19 + 1;
    v78 = Window;
    HMAssignmentLock(&v77, 0);
    if ( v82 )
      _InterlockedAnd((volatile signed __int32 *)v28 + 130, 0xEFFFFFFF);
    SetVisible(*v36, 1);
    HMChangeOwnerThread(*v36, v19[2]);
    v27 = 1;
    v50 = v75;
    *((_QWORD *)v28 + 57) = v80;
    v72 = 1;
    DesktopNotificationEvent = zzzSetDesktop(v28, v29, v50);
    if ( DesktopNotificationEvent < 0 )
    {
      AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v73);
      EditionEndDeferWinEventNotify();
      AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v73);
      goto LABEL_79;
    }
    AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v73);
    EditionEndDeferWinEventNotify();
    if ( v29 )
    {
      ObfDereferenceObject(v29);
      v29 = 0;
    }
  }
  if ( (*((_DWORD *)Object + 8) & 4) == 0 )
  {
    v51 = RtlLengthSid(SeExports->SeWorldSid);
    v52 = v51 + 8;
    v53 = Win32AllocPoolWithQuotaZInit(v51 + 8, 1702064981);
    v54 = (void *)v53;
    if ( v53
      && (*(_WORD *)v53 = 0,
          *(_WORD *)(v53 + 2) = v52,
          *(_DWORD *)(v53 + 4) = 0x100000,
          RtlCopySid(v51, (PSID)(v53 + 8), SeExports->SeWorldSid),
          SecurityDescriptor = (void *)CreateSecurityDescriptor(v54, v52, 0),
          Win32FreePool(v54),
          SecurityDescriptor) )
    {
      DesktopNotificationEvent = CreateDesktopNotificationEvent(SecurityDescriptor);
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
    v27 = v72;
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
    DesktopNotificationEvent = ApplySecurityAttributesToWinsta(Object, v81);
    if ( DesktopNotificationEvent < 0 )
      goto LABEL_77;
    for ( i = (_QWORD *)(W32GetUserSessionState(v57, v56, v58, v59) + 63288); *i; i = (_QWORD *)(*i + 8LL) )
      ;
    LockObjectAssignment(i, Object);
    v61 = Object;
    if ( (*((_DWORD *)Object + 8) & 4) == 0 && a8 )
    {
      v62 = PtiCurrent();
      v77 = (_QWORD *)*((_QWORD *)v62 + 47);
      *((_QWORD *)v62 + 47) = &v77;
      v79 = UserDereferenceObject;
      v78 = (__int64)v61;
      if ( !xxxSafeLoadKeyboardLayoutEx(Object, a4, 0, a5, a6, a7, a8, a9, -2147483647) )
        DesktopNotificationEvent = -1073741823;
      *((_QWORD *)PtiCurrent() + 47) = v77;
    }
    if ( DesktopNotificationEvent < 0 )
      goto LABEL_77;
  }
  if ( !(unsigned int)IsCurrentSessionServiceSession() && (*((_DWORD *)Object + 8) & 0x804) == 0 )
  {
    v63 = Feature_AgenticSessionNoBoostPolicy__private_IsEnabledDeviceUsageNoInline() != 0;
    if ( (unsigned int)Feature_AgenticSessionCapQoSPolicy__private_IsEnabledDeviceUsageNoInline() )
      v63 |= 2u;
    if ( (unsigned int)Feature_LowLatencyProfile__private_IsEnabledDeviceUsageNoInline() )
      v63 |= 4u;
    if ( v63 )
      tagWINDOWSTATION::SetPolicy(Object, v63);
  }
  ObfDereferenceObject(Object);
  *a12 = Handle;
  return 0;
}

```

## disassembly

```asm
0x1402b3930  mov     rax, rsp
0x1402b3933  mov     [rax+10h], rbx
0x1402b3937  mov     [rax+20h], r9
0x1402b393b  mov     [rax+18h], r8d
0x1402b393f  push    rbp
0x1402b3940  push    rsi
0x1402b3941  push    rdi
0x1402b3942  push    r12
0x1402b3944  push    r13
0x1402b3946  push    r14
0x1402b3948  push    r15
0x1402b394a  lea     rbp, [rax-3Fh]
0x1402b394e  sub     rsp, 0F0h
0x1402b3955  mov     rax, [rcx+20h]
0x1402b3959  mov     dil, dl
0x1402b395c  mov     [rbp+37h+var_38], rax
0x1402b3960  mov     rbx, rcx
0x1402b3963  mov     [rbp+37h+Object], 0
0x1402b396b  mov     [rbp+37h+var_68], 0
0x1402b3973  call    cs:__imp_W32GetUserSessionState
0x1402b397a  nop     dword ptr [rax+rax+00h]
0x1402b397f  cmp     qword ptr [rax+0F738h], 0
0x1402b3987  jnz     short loc_1402B399E
0x1402b3989  call    cs:__imp_W32GetUserSessionState
0x1402b3990  nop     dword ptr [rax+rax+00h]
0x1402b3995  lea     r14, [rax+10B60h]
0x1402b399c  jmp     short loc_1402B39B5
0x1402b399e  call    cs:__imp_W32GetUserSessionState
0x1402b39a5  nop     dword ptr [rax+rax+00h]
0x1402b39aa  lea     r14, [rax+10BA8h]
0x1402b39b1  or      dword ptr [r14], 2
0x1402b39b5  mov     rdx, cs:__imp_ExWindowStationObjectType
0x1402b39bc  lea     rax, [rbp+37h+Object]
0x1402b39c0  mov     [rsp+120h+var_E0], rax
0x1402b39c5  mov     r12d, 0E8h
0x1402b39cb  mov     dword ptr [rsp+120h+var_E8], 0
0x1402b39d3  mov     r9b, dil
0x1402b39d6  mov     [rsp+120h+var_F0], 0
0x1402b39de  mov     r8, rbx
0x1402b39e1  mov     rdx, [rdx]
0x1402b39e4  xor     ecx, ecx
0x1402b39e6  mov     dword ptr [rsp+120h+Handle], r12d
0x1402b39eb  mov     [rsp+120h+NewObject], 0
0x1402b39f4  call    cs:__imp_ObCreateObject
0x1402b39fb  nop     dword ptr [rax+rax+00h]
0x1402b3a00  mov     ebx, eax
0x1402b3a02  test    eax, eax
0x1402b3a04  jns     short loc_1402B3A14
0x1402b3a06  mov     ecx, eax
0x1402b3a08  call    SetLastNtError
0x1402b3a0d  mov     eax, ebx
0x1402b3a0f  jmp     loc_1402B419F
0x1402b3a14  xor     ebx, ebx
0x1402b3a16  xor     esi, esi
0x1402b3a18  mov     [rbp+37h+var_88], ebx
0x1402b3a1b  xor     r15d, r15d
0x1402b3a1e  xor     r13d, r13d
0x1402b3a21  call    cs:__imp_W32GetUserSessionState
0x1402b3a28  nop     dword ptr [rax+rax+00h]
0x1402b3a2d  lea     rcx, [rax+0F740h]; RunRef
0x1402b3a34  call    cs:__imp_ExAcquireRundownProtection
0x1402b3a3b  nop     dword ptr [rax+rax+00h]
0x1402b3a40  test    al, al
0x1402b3a42  jnz     short loc_1402B3A4E
0x1402b3a44  mov     edi, 0C0000022h
0x1402b3a49  jmp     loc_1402B4096
0x1402b3a4e  mov     rcx, [rbp+37h+Object]; void *
0x1402b3a52  mov     r8, r12; Size
0x1402b3a55  xor     edx, edx; Val
0x1402b3a57  call    memset_0
0x1402b3a5c  mov     rax, [rbp+37h+Object]
0x1402b3a60  add     rax, 0C8h
0x1402b3a66  mov     [rax+8], rax
0x1402b3a6a  mov     [rax], rax
0x1402b3a6d  call    W32GetCurrentWin32kSessionId
0x1402b3a72  mov     rcx, [rbp+37h+Object]
0x1402b3a76  mov     [rcx], eax
0x1402b3a78  mov     rax, [rbp+37h+Object]
0x1402b3a7c  mov     ecx, [rbp+37h+arg_50]
0x1402b3a82  mov     [rax+0B8h], ecx
0x1402b3a88  mov     rax, [rbp+37h+Object]
0x1402b3a8c  mov     [rax+18h], r14
0x1402b3a90  mov     eax, [r14]
0x1402b3a93  test    al, 2
0x1402b3a95  jz      short loc_1402B3AA4
0x1402b3a97  mov     rax, [rbp+37h+Object]
0x1402b3a9b  mov     dword ptr [rax+20h], 4
0x1402b3aa2  jmp     short loc_1402B3AB8
0x1402b3aa4  mov     ecx, 800h
0x1402b3aa9  test    dword ptr [rbp+37h+arg_48], ecx
0x1402b3aaf  jz      short loc_1402B3AB8
0x1402b3ab1  mov     rax, [rbp+37h+Object]
0x1402b3ab5  or      [rax+20h], ecx
0x1402b3ab8  mov     rcx, [rbp+37h+Object]
0x1402b3abc  add     rcx, 88h
0x1402b3ac3  call    cs:__imp_CreateGlobalAtomTable
0x1402b3aca  nop     dword ptr [rax+rax+00h]
0x1402b3acf  mov     edi, eax
0x1402b3ad1  test    eax, eax
0x1402b3ad3  jns     short loc_1402B3AE1
0x1402b3ad5  mov     ecx, eax
0x1402b3ad7  call    SetLastNtError
0x1402b3adc  jmp     loc_1402B4096
0x1402b3ae1  mov     eax, [r14]
0x1402b3ae4  test    al, 1
0x1402b3ae6  jnz     short loc_1402B3AF6
0x1402b3ae8  mov     rcx, r14; struct tagTERMINAL *
0x1402b3aeb  call    ?xxxInitTerminal@@YAJPEAUtagTERMINAL@@@Z; xxxInitTerminal(tagTERMINAL *)
0x1402b3af0  mov     edi, eax
0x1402b3af2  test    eax, eax
0x1402b3af4  js      short loc_1402B3AD5
0x1402b3af6  mov     rax, [rbp+37h+Object]
0x1402b3afa  mov     ecx, [rax+20h]
0x1402b3afd  test    cl, 4
0x1402b3b00  jnz     short loc_1402B3B14
0x1402b3b02  call    xxxInitWindowStation
0x1402b3b07  test    eax, eax
0x1402b3b09  jnz     short loc_1402B3B14
0x1402b3b0b  mov     edi, 0C0000017h
0x1402b3b10  mov     ecx, edi
0x1402b3b12  jmp     short loc_1402B3AD7
0x1402b3b14  lea     r12, [r14+8]
0x1402b3b18  xor     edi, edi
0x1402b3b1a  cmp     [r12], rdi
0x1402b3b1e  jnz     loc_1402B3DFB
0x1402b3b24  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1402b3b29  mov     rcx, [r14+10h]
0x1402b3b2d  mov     rsi, rax
0x1402b3b30  mov     rbx, [rax+1C8h]
0x1402b3b37  mov     r15, [rax+1E8h]
0x1402b3b3e  mov     rdx, [rcx+1C8h]
0x1402b3b45  mov     [rax+1C8h], rdx
0x1402b3b4c  mov     rax, [rax+270h]
0x1402b3b53  mov     [rbp+37h+var_70], rax
0x1402b3b57  mov     [rbp+37h+var_40], rbx
0x1402b3b5b  test    r15, r15
0x1402b3b5e  jz      short loc_1402B3B71
0x1402b3b60  mov     rcx, r15; Object
0x1402b3b63  call    cs:__imp_ObfReferenceObject
0x1402b3b6a  nop     dword ptr [rax+rax+00h]
0x1402b3b6f  jmp     short loc_1402B3B99
0x1402b3b71  lea     rax, [rsi+300h]
0x1402b3b78  cmp     [rax], rax
0x1402b3b7b  jz      short loc_1402B3B99
0x1402b3b7d  mov     [rbp+37h+arg_0], 20000h
0x1402b3b84  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1402b3b8b  mov     edx, [rbp+37h+arg_0]
0x1402b3b8e  mov     r8d, 21Ch
0x1402b3b94  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1402b3b99  call    cs:__imp_W32GetUserSessionState
0x1402b3ba0  nop     dword ptr [rax+rax+00h]
0x1402b3ba5  lea     rcx, [rbp+37h+var_80]; this
0x1402b3ba9  mov     [rbp+37h+var_80], dil
0x1402b3bad  mov     [rbp+37h+var_78], rdi
0x1402b3bb1  inc     dword ptr [rax+113C0h]
0x1402b3bb7  call    ?Arm@AtomicExecutionCheck@@QEAAXXZ; AtomicExecutionCheck::Arm(void)
0x1402b3bbc  xor     r8d, r8d
0x1402b3bbf  xor     edx, edx
0x1402b3bc1  mov     rcx, rsi
0x1402b3bc4  call    zzzSetDesktop
0x1402b3bc9  mov     edi, eax
0x1402b3bcb  test    eax, eax
0x1402b3bcd  jns     short loc_1402B3C12
0x1402b3bcf  cmp     [rsi+1E8h], r13
0x1402b3bd6  jnz     short loc_1402B3BEC
0x1402b3bd8  test    r15, r15
0x1402b3bdb  jz      short loc_1402B3BEC
0x1402b3bdd  mov     r8, [rbp+37h+var_70]
0x1402b3be1  mov     rdx, r15
0x1402b3be4  mov     rcx, rsi
0x1402b3be7  call    zzzSetDesktop
0x1402b3bec  lea     rcx, [rbp+37h+var_80]; this
0x1402b3bf0  call    ?Disarm@AtomicExecutionCheck@@QEAAXXZ; AtomicExecutionCheck::Disarm(void)
0x1402b3bf5  call    EditionEndDeferWinEventNotify
0x1402b3bfa  mov     [rsi+1C8h], rbx
0x1402b3c01  lea     rcx, [rbp+37h+var_80]; this
0x1402b3c05  call    ?Disarm@AtomicExecutionCheck@@QEAAXXZ; AtomicExecutionCheck::Disarm(void)
0x1402b3c0a  mov     ebx, r13d
0x1402b3c0d  jmp     loc_1402B4096
0x1402b3c12  xor     ecx, ecx
0x1402b3c14  xor     eax, eax
0x1402b3c16  lock cmpxchg [rsi+208h], ecx
0x1402b3c1e  mov     ecx, 10000000h
0x1402b3c23  test    ecx, eax
0x1402b3c25  jnz     short loc_1402B3C34
0x1402b3c27  mov     byte ptr [rbp+37h+arg_0], 1
0x1402b3c2b  lock or [rsi+208h], ecx
0x1402b3c32  jmp     short loc_1402B3C38
0x1402b3c34  mov     byte ptr [rbp+37h+arg_0], r13b
0x1402b3c38  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1402b3c3f  nop     dword ptr [rax+rax+00h]
0x1402b3c44  test    rax, rax
0x1402b3c47  jz      short loc_1402B3C85
0x1402b3c49  cmp     [rax], r13
0x1402b3c4c  jz      short loc_1402B3C85
0x1402b3c4e  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1402b3c55  nop     dword ptr [rax+rax+00h]
0x1402b3c5a  mov     rcx, rax
0x1402b3c5d  test    rax, rax
0x1402b3c60  jz      short loc_1402B3C6E
0x1402b3c62  mov     rax, [rax]
0x1402b3c65  neg     rax
0x1402b3c68  sbb     rdx, rdx
0x1402b3c6b  and     rcx, rdx
0x1402b3c6e  call    cs:__imp_IsImmersiveAppRestricted
0x1402b3c75  nop     dword ptr [rax+rax+00h]
0x1402b3c7a  test    eax, eax
0x1402b3c7c  jz      short loc_1402B3C85
0x1402b3c7e  mov     edi, 1
0x1402b3c83  jmp     short loc_1402B3C87
0x1402b3c85  xor     edi, edi
0x1402b3c87  mov     rax, cs:__imp_?hModuleWin@@3PEAXEA; void * hModuleWin
0x1402b3c8e  lea     rcx, [rbp+37h+var_60]
0x1402b3c92  xor     edx, edx
0x1402b3c94  mov     rbx, [rax]
0x1402b3c97  call    ??0?$SmartObjStackRef@UtagMENU@@@@QEAA@H@Z; SmartObjStackRef<tagMENU>::SmartObjStackRef<tagMENU>(int)
0x1402b3c9c  mov     [rsp+80h], r13
0x1402b3ca4  lea     rax, [rbp+37h+var_60]
0x1402b3ca8  mov     dword ptr [rsp+120h+var_A8], edi
0x1402b3cac  mov     edx, 8001h
0x1402b3cb1  mov     [rsp+120h+var_B0], 30Ah
0x1402b3cb9  xor     edi, edi
0x1402b3cbb  mov     [rsp+120h+var_B8], 1
0x1402b3cc3  xor     r9d, r9d
0x1402b3cc6  mov     qword ptr [rsp+120h+var_C0], rdi
0x1402b3ccb  mov     r8d, edx
0x1402b3cce  mov     [rsp+120h+var_C8], rbx
0x1402b3cd3  xor     ecx, ecx
0x1402b3cd5  mov     [rsp+120h+var_D0], rax
0x1402b3cda  mov     eax, 0FFFFh
0x1402b3cdf  mov     [rsp+120h+var_D8], rdi
0x1402b3ce4  mov     dword ptr [rsp+120h+var_E0], eax
0x1402b3ce8  mov     dword ptr [rsp+120h+var_E8], eax
0x1402b3cec  mov     eax, 0FFFF8000h
0x1402b3cf1  mov     [rsp+120h+var_F0], eax
0x1402b3cf5  mov     dword ptr [rsp+120h+Handle], eax
0x1402b3cf9  mov     dword ptr [rsp+120h+NewObject], 82000000h
0x1402b3d01  call    xxxCreateWindowEx
0x1402b3d06  lea     rcx, [rbp+37h+var_60]
0x1402b3d0a  mov     rbx, rax
0x1402b3d0d  call    ??1?$SmartObjStackRef@UtagMENU@@@@QEAA@XZ; SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(void)
0x1402b3d12  test    rbx, rbx
0x1402b3d15  jnz     short loc_1402B3D49
0x1402b3d17  lea     rcx, [rbp+37h+var_80]; this
0x1402b3d1b  mov     edi, 0C0000017h
0x1402b3d20  call    ?Disarm@AtomicExecutionCheck@@QEAAXXZ; AtomicExecutionCheck::Disarm(void)
0x1402b3d25  call    EditionEndDeferWinEventNotify
0x1402b3d2a  mov     rax, [rbp+37h+var_40]
0x1402b3d2e  mov     rdx, r15
0x1402b3d31  mov     r8, [rbp+37h+var_70]
0x1402b3d35  mov     rcx, rsi
0x1402b3d38  mov     [rsi+1C8h], rax
0x1402b3d3f  call    zzzSetDesktop
0x1402b3d44  jmp     loc_1402B3C01
0x1402b3d49  xor     edx, edx
0x1402b3d4b  mov     [rbp+37h+var_60], r12
0x1402b3d4f  lea     rcx, [rbp+37h+var_60]
0x1402b3d53  mov     [rbp+37h+var_58], rbx
0x1402b3d57  call    cs:__imp_HMAssignmentLock
0x1402b3d5e  nop     dword ptr [rax+rax+00h]
0x1402b3d63  cmp     byte ptr [rbp+37h+arg_0], dil
0x1402b3d67  jz      short loc_1402B3D74
0x1402b3d69  lock and dword ptr [rsi+208h], 0EFFFFFFFh
0x1402b3d74  mov     rcx, [r12]
0x1402b3d78  mov     edx, 1
0x1402b3d7d  call    ?SetVisible@@YA_NPEAUtagWND@@W4SetVisibleOptions@@@Z; SetVisible(tagWND *,SetVisibleOptions)
0x1402b3d82  mov     rdx, [r14+10h]
0x1402b3d86  mov     rcx, [r12]
0x1402b3d8a  call    cs:__imp_HMChangeOwnerThread
0x1402b3d91  nop     dword ptr [rax+rax+00h]
0x1402b3d96  mov     rax, [rbp+37h+var_40]
0x1402b3d9a  mov     ebx, 1
0x1402b3d9f  mov     r8, [rbp+37h+var_70]
0x1402b3da3  mov     rdx, r15
0x1402b3da6  mov     rcx, rsi
0x1402b3da9  mov     [rsi+1C8h], rax
0x1402b3db0  mov     [rbp+37h+var_88], ebx
0x1402b3db3  call    zzzSetDesktop
0x1402b3db8  lea     rcx, [rbp+37h+var_80]; this
0x1402b3dbc  mov     edi, eax
0x1402b3dbe  test    eax, eax
0x1402b3dc0  jns     short loc_1402B3DDA
0x1402b3dc2  call    ?Disarm@AtomicExecutionCheck@@QEAAXXZ; AtomicExecutionCheck::Disarm(void)
0x1402b3dc7  call    EditionEndDeferWinEventNotify
0x1402b3dcc  lea     rcx, [rbp+37h+var_80]; this
0x1402b3dd0  call    ?Disarm@AtomicExecutionCheck@@QEAAXXZ; AtomicExecutionCheck::Disarm(void)
0x1402b3dd5  jmp     loc_1402B4096
0x1402b3dda  call    ?Disarm@AtomicExecutionCheck@@QEAAXXZ; AtomicExecutionCheck::Disarm(void)
0x1402b3ddf  call    EditionEndDeferWinEventNotify
0x1402b3de4  test    r15, r15
0x1402b3de7  jz      short loc_1402B3DFB
0x1402b3de9  mov     rcx, r15; Object
0x1402b3dec  call    cs:__imp_ObfDereferenceObject
0x1402b3df3  nop     dword ptr [rax+rax+00h]
0x1402b3df8  xor     r15d, r15d
0x1402b3dfb  mov     rax, [rbp+37h+Object]
0x1402b3dff  mov     ecx, [rax+20h]
0x1402b3e02  test    cl, 4
0x1402b3e05  jnz     loc_1402B3ED2
0x1402b3e0b  mov     rax, cs:__imp_SeExports
  ... truncated ...
```
