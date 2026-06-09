# xxxDesktopThread

- ea: `0x140276b20`
- end: `0x140277473`
- name: `xxxDesktopThread`
- size: `2387`
- prototype: `__int64 __fastcall(struct tagTERMINAL *)`
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140030864`
- `0x14004cd80`
- `0x14007fc08`
- `0x1400a4824`
- `0x1400dd43c`
- `0x1400e2cb0`
- `0x140235d48`
- `0x14024c1ec`
- `0x14025c440`
- `0x140275be0`
- `0x140276b20`
- `0x1402938dc`
- `0x1402aae2c`
- `0x140342fa0`
- `0x140343500`

## import_xrefs

- `ntoskrnl!ZwSetInformationProcess` at `0x140277166`
- `ntoskrnl!ZwSetInformationProcess` at `0x1402773c6`
- `ntoskrnl!ZwSetInformationProcess` at `0x140277166`
- `ntoskrnl!ZwSetInformationProcess` at `0x1402773c6`
- `ntoskrnl!ObReferenceObjectByPointer` at `0x140276eee`
- `ntoskrnl!ObReferenceObjectByPointer` at `0x140276eee`
- `ntoskrnl!ExEventObjectType` at `0x140276ed5`
- `ntoskrnl!KeSetEvent` at `0x140276cb4`
- `ntoskrnl!KeSetEvent` at `0x140276ec9`
- `ntoskrnl!KeSetEvent` at `0x140277028`
- `ntoskrnl!KeSetEvent` at `0x140277400`
- `ntoskrnl!KeSetEvent` at `0x140276cb4`
- `ntoskrnl!KeSetEvent` at `0x140276ec9`
- `ntoskrnl!KeSetEvent` at `0x140277028`
- `ntoskrnl!KeSetEvent` at `0x140277400`
- `ntoskrnl!KeWaitForSingleObject` at `0x140276f1c`
- `ntoskrnl!KeWaitForSingleObject` at `0x140276f1c`
- `ntoskrnl!RtlInitUnicodeString` at `0x140276c20`
- `ntoskrnl!RtlInitUnicodeString` at `0x140276c20`
- `ntoskrnl!ObfDereferenceObject` at `0x140276f3c`
- `ntoskrnl!ObfDereferenceObject` at `0x140277084`
- `ntoskrnl!ObfDereferenceObject` at `0x140276f3c`
- `ntoskrnl!ObfDereferenceObject` at `0x140277084`
- `win32kbase!?SetDTEThread@tagTERMINAL@@QEAAXXZ` at `0x140276eb2`
- `win32kbase!?SetDTEThread@tagTERMINAL@@QEAAXXZ` at `0x140277141`
- `win32kbase!?SetDTEThread@tagTERMINAL@@QEAAXXZ` at `0x140276eb2`
- `win32kbase!?SetDTEThread@tagTERMINAL@@QEAAXXZ` at `0x140277141`
- `win32kbase!?ClearDTEThread@tagTERMINAL@@QEAAXXZ` at `0x1402770a0`
- `win32kbase!?ClearDTEThread@tagTERMINAL@@QEAAXXZ` at `0x1402773d5`
- `win32kbase!?ClearDTEThread@tagTERMINAL@@QEAAXXZ` at `0x1402770a0`
- `win32kbase!?ClearDTEThread@tagTERMINAL@@QEAAXXZ` at `0x1402773d5`
- `win32kbase!zzzDestroyQueue` at `0x140277351`
- `win32kbase!zzzDestroyQueue` at `0x140277351`
- `win32kbase!CleanupSensorExplicitly` at `0x1402770b4`
- `win32kbase!CleanupSensorExplicitly` at `0x140277365`
- `win32kbase!CleanupSensorExplicitly` at `0x1402770b4`
- `win32kbase!CleanupSensorExplicitly` at `0x140277365`
- `win32kbase!?RegisterDispatcherObject@CBaseInput@@QEAAJPEAVIRegisterInputDispatcherObjects@@@Z` at `0x140277211`
- `win32kbase!?RegisterDispatcherObject@CBaseInput@@QEAAJPEAVIRegisterInputDispatcherObjects@@@Z` at `0x140277211`
- `win32kbase!?Initialize@LegacyInputDispatcher@@QEAAJD_NIIPEAULegacyDispatcherObject@@@Z` at `0x1402771e0`
- `win32kbase!?Initialize@LegacyInputDispatcher@@QEAAJD_NIIPEAULegacyDispatcherObject@@@Z` at `0x1402771e0`
- `win32kbase!?Create@LegacyInputDispatcher@@SAJPEAPEAV1@@Z` at `0x140276c93`
- `win32kbase!?Create@LegacyInputDispatcher@@SAJPEAPEAV1@@Z` at `0x140276d19`
- `win32kbase!?Create@LegacyInputDispatcher@@SAJPEAPEAV1@@Z` at `0x140276c93`
- `win32kbase!?Create@LegacyInputDispatcher@@SAJPEAPEAV1@@Z` at `0x140276d19`
- `win32kbase!?Read@CBaseInput@@QEAAJXZ` at `0x140276e58`
- `win32kbase!?Read@CBaseInput@@QEAAJXZ` at `0x140276e58`
- `win32kbase!?InitializeSensor@CBaseInput@@QEAAJXZ` at `0x140276dea`
- `win32kbase!?InitializeSensor@CBaseInput@@QEAAJXZ` at `0x140276e79`
- `win32kbase!?InitializeSensor@CBaseInput@@QEAAJXZ` at `0x140276dea`
- `win32kbase!?InitializeSensor@CBaseInput@@QEAAJXZ` at `0x140276e79`
- `win32kbase!InitSystemThread` at `0x140276c55`
- `win32kbase!InitSystemThread` at `0x140276c55`
- `win32kbase!SetThreadBasePriority` at `0x140276b9a`
- `win32kbase!SetThreadBasePriority` at `0x140276b9a`
- `win32kbase!SetThreadName` at `0x140276c45`
- `win32kbase!SetThreadName` at `0x140276c45`
- `win32kbase!CreateKernelEvent` at `0x140276be4`
- `win32kbase!CreateKernelEvent` at `0x140276be4`
- `win32kbase!?HandleTSRequest@CBaseInput@@QEAAXW4InputTSRequest@@@Z` at `0x140276e2d`
- `win32kbase!?HandleTSRequest@CBaseInput@@QEAAXW4InputTSRequest@@@Z` at `0x140276e2d`
- `win32kbase!EnterCrit` at `0x140276e0c`
- `win32kbase!EnterCrit` at `0x140276e8e`
- `win32kbase!EnterCrit` at `0x140276f2d`
- `win32kbase!EnterCrit` at `0x140276e0c`
- `win32kbase!EnterCrit` at `0x140276e8e`
- `win32kbase!EnterCrit` at `0x140276f2d`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x140276e39`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x140276efa`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1402773e1`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x140276e39`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x140276efa`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1402773e1`
- `win32kbase!Win32FreePool` at `0x14027711d`
- `win32kbase!Win32FreePool` at `0x14027739d`
- `win32kbase!Win32FreePool` at `0x14027743b`
- `win32kbase!Win32FreePool` at `0x14027711d`
- `win32kbase!Win32FreePool` at `0x14027739d`
- `win32kbase!Win32FreePool` at `0x14027743b`
- `win32kbase!HMAssignmentUnlock` at `0x1402772c8`
- `win32kbase!HMAssignmentUnlock` at `0x1402772f0`
- `win32kbase!HMAssignmentUnlock` at `0x1402772c8`
- `win32kbase!HMAssignmentUnlock` at `0x1402772f0`
- `WIN32K!W32GetUserSessionState` at `0x140276b6e`
- `WIN32K!W32GetUserSessionState` at `0x140276bae`
- `WIN32K!W32GetUserSessionState` at `0x140276bf3`
- `WIN32K!W32GetUserSessionState` at `0x140276c6d`
- `WIN32K!W32GetUserSessionState` at `0x140276ceb`
- `WIN32K!W32GetUserSessionState` at `0x140276d3b`
- `WIN32K!W32GetUserSessionState` at `0x140276d6a`
- `WIN32K!W32GetUserSessionState` at `0x140276d96`
- `WIN32K!W32GetUserSessionState` at `0x140276dd7`
- `WIN32K!W32GetUserSessionState` at `0x140276e18`
- `WIN32K!W32GetUserSessionState` at `0x140276e45`
- `WIN32K!W32GetUserSessionState` at `0x140276e66`
- `WIN32K!W32GetUserSessionState` at `0x140276fa9`
- `WIN32K!W32GetUserSessionState` at `0x1402770d6`
- `WIN32K!W32GetUserSessionState` at `0x140277107`
- `WIN32K!W32GetUserSessionState` at `0x1402771b2`
- `WIN32K!W32GetUserSessionState` at `0x1402771fa`
- `WIN32K!W32GetUserSessionState` at `0x14027722a`
- `WIN32K!W32GetUserSessionState` at `0x140277272`
- `WIN32K!W32GetUserSessionState` at `0x140277289`
- `WIN32K!W32GetUserSessionState` at `0x1402772fc`
- `WIN32K!W32GetUserSessionState` at `0x140277387`
- `WIN32K!W32GetUserSessionState` at `0x140277410`
- `WIN32K!W32GetUserSessionState` at `0x140277425`
- `WIN32K!W32GetUserSessionState` at `0x140276b6e`
- `WIN32K!W32GetUserSessionState` at `0x140276bae`
- `WIN32K!W32GetUserSessionState` at `0x140276bf3`
- `WIN32K!W32GetUserSessionState` at `0x140276c6d`
- `WIN32K!W32GetUserSessionState` at `0x140276ceb`
- `WIN32K!W32GetUserSessionState` at `0x140276d3b`
- `WIN32K!W32GetUserSessionState` at `0x140276d6a`
- `WIN32K!W32GetUserSessionState` at `0x140276d96`
- `WIN32K!W32GetUserSessionState` at `0x140276dd7`
- `WIN32K!W32GetUserSessionState` at `0x140276e18`
- `WIN32K!W32GetUserSessionState` at `0x140276e45`
- `WIN32K!W32GetUserSessionState` at `0x140276e66`
- `WIN32K!W32GetUserSessionState` at `0x140276fa9`
- `WIN32K!W32GetUserSessionState` at `0x1402770d6`
- `WIN32K!W32GetUserSessionState` at `0x140277107`
- `WIN32K!W32GetUserSessionState` at `0x1402771b2`
- `WIN32K!W32GetUserSessionState` at `0x1402771fa`
- `WIN32K!W32GetUserSessionState` at `0x14027722a`
- `WIN32K!W32GetUserSessionState` at `0x140277272`
- `WIN32K!W32GetUserSessionState` at `0x140277289`
- `WIN32K!W32GetUserSessionState` at `0x1402772fc`
- `WIN32K!W32GetUserSessionState` at `0x140277387`
- `WIN32K!W32GetUserSessionState` at `0x140277410`
- `WIN32K!W32GetUserSessionState` at `0x140277425`

## string_xrefs

- `0x140276c2c`: `Win32k Desktop Thread (IO_DT)`
- `0x140276c3e`: `Win32k Desktop Thread (NOIO_DT)`

## pseudocode

```c
void __fastcall xxxDesktopThread(PRKEVENT *a1)
{
  int v2; // esi
  __int64 v3; // rdx
  __int64 v4; // rcx
  int v5; // r12d
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 KernelEvent; // rbx
  __int64 v9; // rdx
  __int64 v10; // rcx
  const WCHAR *v11; // rdx
  const wchar_t *v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  struct tagTHREADINFO *v17; // rax
  struct tagTHREADINFO *v18; // r15
  struct _KEVENT *v19; // r14
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  unsigned int v24; // r13d
  unsigned int v25; // r13d
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rbx
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // r8
  __int64 v43; // rax
  __int64 v44; // rax
  PRKEVENT v45; // rbx
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // r8
  __int64 v49; // rdx
  int v50; // eax
  bool v51; // zf
  bool v52; // bl
  bool v53; // r12
  __int64 v54; // rax
  int v55; // r8d
  int v56; // edx
  struct _KEVENT *v57; // rcx
  PRKEVENT v58; // rcx
  __int64 v59; // rdx
  __int64 v60; // r8
  LegacyInputDispatcher *v61; // rcx
  __int64 v62; // rdx
  __int64 v63; // rcx
  __int64 v64; // rbx
  __int64 v65; // rdx
  __int64 v66; // rcx
  unsigned int v67; // r12d
  __int64 v68; // rdx
  __int64 v69; // rcx
  __int64 v70; // rax
  __int64 v71; // rax
  LegacyInputDispatcher *v72; // rcx
  __int64 v73; // rdx
  __int64 v74; // rdx
  __int64 v75; // rcx
  __int64 v76; // rax
  __int64 v77; // rdx
  _QWORD *v78; // rcx
  __int64 v79; // rax
  __int64 v80; // rdx
  LegacyInputDispatcher *v81; // rcx
  __int64 v82; // rbx
  __int64 v83; // rdx
  __int64 v84; // rcx
  __int64 UserSessionState; // rbx
  signed __int32 v86[8]; // [rsp+0h] [rbp-B9h] BYREF
  char v87; // [rsp+40h] [rbp-79h]
  int v88; // [rsp+44h] [rbp-75h]
  LegacyInputDispatcher *v89; // [rsp+48h] [rbp-71h] BYREF
  int ProcessInformation; // [rsp+50h] [rbp-69h] BYREF
  int v91; // [rsp+54h] [rbp-65h]
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-61h] BYREF
  __int64 v93; // [rsp+70h] [rbp-49h] BYREF
  _QWORD v94[9]; // [rsp+78h] [rbp-41h]

  ProcessInformation = 0;
  v89 = 0;
  DestinationString = 0;
  memset_0(&v93, 0, 0x50u);
  v2 = *(_DWORD *)a1 & 2;
  v5 = *(_DWORD *)(W32GetUserSessionState(v4, v3) + 19176);
  v91 = v5;
  SetThreadBasePriority(KeGetCurrentThread(), v2 != 0 ? 12 : 16);
  if ( !v2 )
  {
    if ( *(_QWORD *)(W32GetUserSessionState(v7, v6) + 62960) )
    {
      v88 = 0x20000;
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 846);
    }
    KernelEvent = CreateKernelEvent(1, 0);
    *(_QWORD *)(W32GetUserSessionState(v10, v9) + 62960) = KernelEvent;
  }
  v11 = L"IO_DT";
  if ( v2 )
    v11 = L"NOIO_DT";
  RtlInitUnicodeString(&DestinationString, v11);
  v12 = L"Win32k Desktop Thread (IO_DT)";
  if ( v2 )
    v12 = L"Win32k Desktop Thread (NOIO_DT)";
  SetThreadName(-2, v12);
  if ( (int)InitSystemThread(&DestinationString) < 0 || !v2 && !*(_QWORD *)(W32GetUserSessionState(v14, v13) + 62960) )
  {
    *(_DWORD *)a1 |= 8u;
    _InterlockedOr(v86, 0);
    KeSetEvent(a1[5], 1, 0);
    if ( v2 || !*(_QWORD *)(W32GetUserSessionState(v84, v83) + 62960) )
      return;
LABEL_103:
    UserSessionState = W32GetUserSessionState(v16, v15);
    Win32FreePool(*(void **)(UserSessionState + 62960));
    *(_QWORD *)(UserSessionState + 62960) = 0;
    return;
  }
  if ( (unsigned int)Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline()
    && (int)LegacyInputDispatcher::Create(&v89) < 0 )
  {
    goto LABEL_14;
  }
  v17 = PtiCurrent();
  a1[2] = (PRKEVENT)v17;
  v18 = v17;
  v19 = (struct _KEVENT *)*((_QWORD *)v17 + 58);
  a1[3] = v19;
  ++LODWORD(v19[21].Header.WaitListHead.Flink);
  *((_QWORD *)v17 + 62) = *(_QWORD *)(W32GetUserSessionState(v21, v20) + 62688);
  *((_QWORD *)v18 + 81) = 0;
  if ( !(unsigned int)Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline()
    && (int)LegacyInputDispatcher::Create(&v89) < 0 )
  {
LABEL_14:
    *(_DWORD *)a1 |= 8u;
    _InterlockedOr(v86, 0);
    KeSetEvent(a1[5], 1, 0);
    if ( v2 )
      return;
    goto LABEL_103;
  }
  v87 = 0;
  v24 = 0;
  if ( !v2 )
  {
    v25 = 1;
    v27 = *(_QWORD *)(W32GetUserSessionState(v23, v22) + 36144);
    v93 = *(_QWORD *)(v27 + 72);
    v94[0] = OnPointerCursorOperation;
    if ( !v5 )
    {
      v25 = 2;
      v27 = *(_QWORD *)(W32GetUserSessionState(v27, v26) + 16776);
      v94[2] = OnPTPMouseOperation;
      v94[1] = v27;
    }
    v28 = 2LL * v25;
    v24 = v25 + 1;
    v29 = *(_QWORD *)(W32GetUserSessionState(v27, v26) + 62960);
    v94[v28] = lambda_4b651d6c306d13f8deac809f2617e82f_::_lambda_invoker_cdecl_;
    v94[v28 - 1] = v29;
    if ( (unsigned int)IsCurrentSessionServiceSession() )
    {
      v44 = W32GetUserSessionState(v31, v30);
      CBaseInput::InitializeSensor(*(CBaseInput **)(v44 + 3048));
      v87 = 1;
    }
    else if ( !v5 )
    {
      v87 = 1;
      v32 = W32GetUserSessionState(v31, v30);
      if ( (int)CBaseInput::InitializeSensor(*(CBaseInput **)(v32 + 3048)) >= 0 )
      {
        if ( (unsigned int)IsRemoteConnection(v34, v33) )
        {
          EnterCrit(1, 0);
          v39 = W32GetUserSessionState(v38, v37);
          CBaseInput::HandleTSRequest(*(_QWORD *)(v39 + 3048), 0);
          UserSessionSwitchLeaveCrit(v41, v40, v42);
        }
        v43 = W32GetUserSessionState(v36, v35);
        CBaseInput::Read(*(CBaseInput **)(v43 + 3048));
      }
    }
  }
  EnterCrit(1, 0);
  if ( !(unsigned int)Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline() )
    *(_DWORD *)a1 |= 4u;
  if ( (unsigned int)Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline() )
    tagTERMINAL::SetDTEThread((tagTERMINAL *)a1);
  KeSetEvent(a1[5], 1, 0);
  v45 = a1[7];
  ObReferenceObjectByPointer(v45, 0x1F0003u, (POBJECT_TYPE)ExEventObjectType, 0);
  UserSessionSwitchLeaveCrit(v47, v46, v48);
  KeWaitForSingleObject(v45, WrUserRequest, 0, 0, 0);
  EnterCrit(1, 0);
  ObfDereferenceObject(v45);
  v51 = (unsigned int)Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline() == 0;
  v50 = *(_DWORD *)a1;
  if ( v51 )
    v51 = (v50 & 8) == 0;
  else
    v51 = (v50 & 0x10) == 0;
  if ( v51 )
  {
    if ( !(unsigned int)Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline() )
      tagTERMINAL::SetDTEThread((tagTERMINAL *)a1);
    ProcessInformation = 1;
    ZwSetInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessBreakOnTermination, &ProcessInformation, 4u);
    v66 = 2LL * v24;
    v94[2 * v24 - 1] = *((_QWORD *)v18 + 201);
    if ( v24 + 1 > 5 )
    {
      v88 = 0x20000;
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1155);
    }
    if ( v2 || v5 )
    {
      v67 = v24 + 1;
    }
    else
    {
      W32GetUserSessionState(v66, v65);
      v67 = v24 + 10;
    }
    LegacyInputDispatcher::Initialize(v89, 1, 0, v67, v24 + 1, (struct LegacyDispatcherObject *)&v93);
    if ( v67 != v24 + 1 && !v91 )
    {
      v70 = W32GetUserSessionState(v69, v68);
      CBaseInput::RegisterDispatcherObject(*(CBaseInput **)(v70 + 3048), v89);
    }
    *((_DWORD *)v89 + 15) = v24;
    v71 = W32GetUserSessionState(v69, v68);
    if ( v2 )
    {
      *(_QWORD *)(v71 + 19240) = v89;
    }
    else
    {
      v72 = v89;
      *(_QWORD *)(v71 + 19232) = v89;
    }
    do
    {
      do
        LOBYTE(v72) = 1;
      while ( (unsigned int)xxxDesktopThreadWaiter(v72, 0) != v24 );
    }
    while ( (unsigned int)xxxHandleDesktopMessages(v18, (struct tagTERMINAL *)a1) );
    if ( a1 == (PRKEVENT *)(W32GetUserSessionState(v72, v73) + 68448) )
    {
      v76 = W32GetUserSessionState(v75, v74);
      *(_DWORD *)(v76 + 68920) |= 0x100000u;
    }
    a1[2] = 0;
    a1[3] = 0;
    *((_DWORD *)a1 + 8) = 0;
    if ( !(unsigned int)Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline() )
      *(_DWORD *)a1 = 0;
    v78 = (_QWORD *)*((_QWORD *)v18 + 61);
    if ( v78 )
    {
      HMAssignmentUnlock(v78 + 24);
      v79 = *((_QWORD *)v18 + 61);
      v78 = (_QWORD *)(*(_QWORD *)(v79 + 8) + 24LL);
      if ( *v78 )
      {
        *(_QWORD *)(**(_QWORD **)(v79 + 8) + 8LL) = 0;
        HMAssignmentUnlock(v78);
      }
    }
    *((_QWORD *)v18 + 62) = *(_QWORD *)(W32GetUserSessionState(v78, v77) + 62688);
    if ( !LODWORD(v19[21].Header.WaitListHead.Flink) )
    {
      v88 = 0x20000;
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1259);
    }
    --LODWORD(v19[21].Header.WaitListHead.Flink);
    if ( *((struct _KEVENT **)v18 + 58) != v19 )
      zzzDestroyQueue(v19, v18);
    if ( v87 )
      CleanupSensorExplicitly(0);
    v81 = v89;
    if ( v89 )
      LegacyInputDispatcher::`scalar deleting destructor'(v89, v80);
    v89 = 0;
    if ( !v2 )
    {
      v82 = W32GetUserSessionState(v81, v80);
      Win32FreePool(*(void **)(v82 + 62960));
      *(_QWORD *)(v82 + 62960) = 0;
    }
    ProcessInformation = 0;
    ZwSetInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessBreakOnTermination, &ProcessInformation, 4u);
    tagTERMINAL::ClearDTEThread((tagTERMINAL *)a1);
  }
  else
  {
    v52 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80000) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v53 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v52 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v54 = W32GetUserSessionState(WPP_GLOBAL_Control, v49);
      LOBYTE(v55) = v53;
      LOBYTE(v56) = v52;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v56,
        v55,
        *(_QWORD *)(v54 + 69152),
        4,
        20,
        23,
        (__int64)WPP_8482796ea87931402564603ebe19074e_Traceguids);
    }
    _InterlockedOr(v86, 0);
    if ( a1[1] )
      xxxCleanupMotherDesktopWindow((struct tagTERMINAL *)a1);
    if ( (unsigned int)Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline() )
      DestroyPendingDesktops(v18, (struct tagTERMINAL *)a1);
    v57 = a1[5];
    if ( v57 )
      KeSetEvent(v57, 1, 0);
    v51 = LODWORD(v19[21].Header.WaitListHead.Flink)-- == 1;
    if ( v51 && !tagQ::IsAnyThreadAttached((tagQ *)v19) && (v19[21].Header.SignalState & 0x4000000) != 0 )
    {
      v88 = 0x20000;
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1101);
    }
    v58 = a1[7];
    a1[2] = 0;
    a1[3] = 0;
    if ( v58 )
    {
      ObfDereferenceObject(v58);
      a1[7] = 0;
    }
    if ( (unsigned int)Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline() )
      tagTERMINAL::ClearDTEThread((tagTERMINAL *)a1);
    if ( v87 )
      CleanupSensorExplicitly(0);
    v61 = v89;
    if ( v89 )
      LegacyInputDispatcher::`scalar deleting destructor'(v89, v59);
    if ( !v2 )
    {
      if ( !*(_QWORD *)(W32GetUserSessionState(v61, v59) + 62960) )
      {
        v88 = 0x20000;
        MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1128);
      }
      v64 = W32GetUserSessionState(v63, v62);
      Win32FreePool(*(void **)(v64 + 62960));
      *(_QWORD *)(v64 + 62960) = 0;
    }
  }
  UserSessionSwitchLeaveCrit(v61, v59, v60);
}

```

## disassembly

```asm
0x140276b20  push    rbp
0x140276b22  push    rbx
0x140276b23  push    rsi
0x140276b24  push    rdi
0x140276b25  push    r12
0x140276b27  push    r13
0x140276b29  push    r14
0x140276b2b  push    r15
0x140276b2d  lea     rbp, [rsp-1Fh]
0x140276b32  sub     rsp, 0D8h
0x140276b39  mov     rax, cs:__security_cookie
0x140276b40  xor     rax, rsp
0x140276b43  mov     [rbp+57h+var_50], rax
0x140276b47  xor     ebx, ebx
0x140276b49  mov     rdi, rcx
0x140276b4c  xorps   xmm0, xmm0
0x140276b4f  mov     [rbp+57h+ProcessInformation], ebx
0x140276b52  xor     edx, edx; Val
0x140276b54  mov     [rbp+57h+var_C8], rbx
0x140276b58  lea     rcx, [rbp+57h+var_A0]; void *
0x140276b5c  lea     r8d, [rbx+50h]; Size
0x140276b60  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140276b64  call    memset_0
0x140276b69  mov     esi, [rdi]
0x140276b6b  and     esi, 2
0x140276b6e  call    cs:__imp_W32GetUserSessionState
0x140276b75  nop     dword ptr [rax+rax+00h]
0x140276b7a  mov     rcx, gs:188h
0x140276b83  mov     r12d, [rax+4AE8h]
0x140276b8a  mov     eax, esi
0x140276b8c  neg     eax
0x140276b8e  mov     [rbp+57h+var_BC], r12d
0x140276b92  sbb     edx, edx
0x140276b94  and     edx, 0FFFFFFFCh
0x140276b97  add     edx, 10h
0x140276b9a  call    cs:__imp_SetThreadBasePriority
0x140276ba1  nop     dword ptr [rax+rax+00h]
0x140276ba6  lea     r13d, [rbx+1]
0x140276baa  test    esi, esi
0x140276bac  jnz     short loc_140276C08
0x140276bae  call    cs:__imp_W32GetUserSessionState
0x140276bb5  nop     dword ptr [rax+rax+00h]
0x140276bba  cmp     [rax+0F5F0h], rbx
0x140276bc1  jz      short loc_140276BDF
0x140276bc3  mov     [rbp+57h+var_CC], 20000h
0x140276bca  lea     rcx, aIxptelassert; "IXPTelAssert"
0x140276bd1  mov     edx, [rbp+57h+var_CC]
0x140276bd4  mov     r8d, 34Eh
0x140276bda  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x140276bdf  xor     edx, edx
0x140276be1  mov     ecx, r13d
0x140276be4  call    cs:__imp_CreateKernelEvent
0x140276beb  nop     dword ptr [rax+rax+00h]
0x140276bf0  mov     rbx, rax
0x140276bf3  call    cs:__imp_W32GetUserSessionState
0x140276bfa  nop     dword ptr [rax+rax+00h]
0x140276bff  mov     [rax+0F5F0h], rbx
0x140276c06  xor     ebx, ebx
0x140276c08  lea     rax, aNoioDt; "NOIO_DT"
0x140276c0f  test    esi, esi
0x140276c11  lea     rdx, aIoDt; "IO_DT"
0x140276c18  cmovnz  rdx, rax; SourceString
0x140276c1c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140276c20  call    cs:__imp_RtlInitUnicodeString
0x140276c27  nop     dword ptr [rax+rax+00h]
0x140276c2c  lea     rdx, aWin32kDesktopT; "Win32k Desktop Thread (IO_DT)"
0x140276c33  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x140276c3a  test    esi, esi
0x140276c3c  jz      short loc_140276C45
0x140276c3e  lea     rdx, aWin32kDesktopT_0; "Win32k Desktop Thread (NOIO_DT)"
0x140276c45  call    cs:__imp_SetThreadName
0x140276c4c  nop     dword ptr [rax+rax+00h]
0x140276c51  lea     rcx, [rbp+57h+DestinationString]
0x140276c55  call    cs:__imp_InitSystemThread
0x140276c5c  nop     dword ptr [rax+rax+00h]
0x140276c61  test    eax, eax
0x140276c63  js      loc_1402773EF
0x140276c69  test    esi, esi
0x140276c6b  jnz     short loc_140276C86
0x140276c6d  call    cs:__imp_W32GetUserSessionState
0x140276c74  nop     dword ptr [rax+rax+00h]
0x140276c79  cmp     [rax+0F5F0h], rbx
0x140276c80  jz      loc_1402773EF
0x140276c86  call    Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline
0x140276c8b  test    eax, eax
0x140276c8d  jz      short loc_140276CCD
0x140276c8f  lea     rcx, [rbp+57h+var_C8]
0x140276c93  call    cs:__imp_?Create@LegacyInputDispatcher@@SAJPEAPEAV1@@Z; LegacyInputDispatcher::Create(LegacyInputDispatcher * *)
0x140276c9a  nop     dword ptr [rax+rax+00h]
0x140276c9f  test    eax, eax
0x140276ca1  jns     short loc_140276CCD
0x140276ca3  or      dword ptr [rdi], 8
0x140276ca6  lock or [rsp+110h+var_110], ebx
0x140276caa  mov     rcx, [rdi+28h]; Event
0x140276cae  xor     r8d, r8d; Wait
0x140276cb1  mov     edx, r13d; Increment
0x140276cb4  call    cs:__imp_KeSetEvent
0x140276cbb  nop     dword ptr [rax+rax+00h]
0x140276cc0  test    esi, esi
0x140276cc2  jnz     loc_140277452
0x140276cc8  jmp     loc_140277425
0x140276ccd  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140276cd2  mov     [rdi+10h], rax
0x140276cd6  mov     r15, rax
0x140276cd9  mov     r14, [rax+1D0h]
0x140276ce0  mov     [rdi+18h], r14
0x140276ce4  add     [r14+200h], r13d
0x140276ceb  call    cs:__imp_W32GetUserSessionState
0x140276cf2  nop     dword ptr [rax+rax+00h]
0x140276cf7  mov     rcx, [rax+0F4E0h]
0x140276cfe  mov     [r15+1F0h], rcx
0x140276d05  mov     [r15+288h], rbx
0x140276d0c  call    Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline
0x140276d11  test    eax, eax
0x140276d13  jnz     short loc_140276D2D
0x140276d15  lea     rcx, [rbp+57h+var_C8]
0x140276d19  call    cs:__imp_?Create@LegacyInputDispatcher@@SAJPEAPEAV1@@Z; LegacyInputDispatcher::Create(LegacyInputDispatcher * *)
0x140276d20  nop     dword ptr [rax+rax+00h]
0x140276d25  test    eax, eax
0x140276d27  js      loc_140276CA3
0x140276d2d  mov     [rbp+57h+var_D0], bl
0x140276d30  mov     r13d, ebx
0x140276d33  test    esi, esi
0x140276d35  jnz     loc_140276E89
0x140276d3b  call    cs:__imp_W32GetUserSessionState
0x140276d42  nop     dword ptr [rax+rax+00h]
0x140276d47  lea     r13d, [rsi+1]
0x140276d4b  mov     rcx, [rax+8D30h]
0x140276d52  mov     rax, [rcx+48h]
0x140276d56  mov     [rbp+57h+var_A0], rax
0x140276d5a  lea     rax, ?OnPointerCursorOperation@@YAXXZ; OnPointerCursorOperation(void)
0x140276d61  mov     [rbp+57h+var_98], rax
0x140276d65  test    r12d, r12d
0x140276d68  jnz     short loc_140276D90
0x140276d6a  call    cs:__imp_W32GetUserSessionState
0x140276d71  nop     dword ptr [rax+rax+00h]
0x140276d76  lea     r13d, [rsi+2]
0x140276d7a  mov     rcx, [rax+4188h]
0x140276d81  lea     rax, OnPTPMouseOperation
0x140276d88  mov     [rbp+57h+var_88], rax
0x140276d8c  mov     [rbp+57h+var_90], rcx
0x140276d90  mov     ebx, r13d
0x140276d93  add     rbx, rbx
0x140276d96  call    cs:__imp_W32GetUserSessionState
0x140276d9d  nop     dword ptr [rax+rax+00h]
0x140276da2  inc     r13d
0x140276da5  mov     rcx, [rax+0F5F0h]
0x140276dac  lea     rax, _lambda_4b651d6c306d13f8deac809f2617e82f____lambda_invoker_cdecl_
0x140276db3  mov     [rbp+rbx*8+57h+var_98], rax
0x140276db8  mov     [rbp+rbx*8+57h+var_A0], rcx
0x140276dbd  call    IsCurrentSessionServiceSession
0x140276dc2  test    eax, eax
0x140276dc4  jnz     loc_140276E66
0x140276dca  test    r12d, r12d
0x140276dcd  jnz     loc_140276E89
0x140276dd3  mov     [rbp+57h+var_D0], 1
0x140276dd7  call    cs:__imp_W32GetUserSessionState
0x140276dde  nop     dword ptr [rax+rax+00h]
0x140276de3  mov     rcx, [rax+0BE8h]
0x140276dea  call    cs:__imp_?InitializeSensor@CBaseInput@@QEAAJXZ; CBaseInput::InitializeSensor(void)
0x140276df1  nop     dword ptr [rax+rax+00h]
0x140276df6  test    eax, eax
0x140276df8  js      loc_140276E89
0x140276dfe  call    IsRemoteConnection
0x140276e03  test    eax, eax
0x140276e05  jz      short loc_140276E45
0x140276e07  xor     edx, edx
0x140276e09  lea     ecx, [rdx+1]
0x140276e0c  call    cs:__imp_EnterCrit
0x140276e13  nop     dword ptr [rax+rax+00h]
0x140276e18  call    cs:__imp_W32GetUserSessionState
0x140276e1f  nop     dword ptr [rax+rax+00h]
0x140276e24  xor     edx, edx
0x140276e26  mov     rcx, [rax+0BE8h]
0x140276e2d  call    cs:__imp_?HandleTSRequest@CBaseInput@@QEAAXW4InputTSRequest@@@Z; CBaseInput::HandleTSRequest(InputTSRequest)
0x140276e34  nop     dword ptr [rax+rax+00h]
0x140276e39  call    cs:__imp_UserSessionSwitchLeaveCrit
0x140276e40  nop     dword ptr [rax+rax+00h]
0x140276e45  call    cs:__imp_W32GetUserSessionState
0x140276e4c  nop     dword ptr [rax+rax+00h]
0x140276e51  mov     rcx, [rax+0BE8h]
0x140276e58  call    cs:__imp_?Read@CBaseInput@@QEAAJXZ; CBaseInput::Read(void)
0x140276e5f  nop     dword ptr [rax+rax+00h]
0x140276e64  jmp     short loc_140276E89
0x140276e66  call    cs:__imp_W32GetUserSessionState
0x140276e6d  nop     dword ptr [rax+rax+00h]
0x140276e72  mov     rcx, [rax+0BE8h]
0x140276e79  call    cs:__imp_?InitializeSensor@CBaseInput@@QEAAJXZ; CBaseInput::InitializeSensor(void)
0x140276e80  nop     dword ptr [rax+rax+00h]
0x140276e85  mov     [rbp+57h+var_D0], 1
0x140276e89  xor     edx, edx
0x140276e8b  lea     ecx, [rdx+1]
0x140276e8e  call    cs:__imp_EnterCrit
0x140276e95  nop     dword ptr [rax+rax+00h]
0x140276e9a  call    Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline
0x140276e9f  test    eax, eax
0x140276ea1  jnz     short loc_140276EA6
0x140276ea3  or      dword ptr [rdi], 4
0x140276ea6  call    Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline
0x140276eab  test    eax, eax
0x140276ead  jz      short loc_140276EBE
0x140276eaf  mov     rcx, rdi
0x140276eb2  call    cs:__imp_?SetDTEThread@tagTERMINAL@@QEAAXXZ; tagTERMINAL::SetDTEThread(void)
0x140276eb9  nop     dword ptr [rax+rax+00h]
0x140276ebe  mov     rcx, [rdi+28h]; Event
0x140276ec2  xor     r8d, r8d; Wait
0x140276ec5  lea     edx, [r8+1]; Increment
0x140276ec9  call    cs:__imp_KeSetEvent
0x140276ed0  nop     dword ptr [rax+rax+00h]
0x140276ed5  mov     r8, cs:ExEventObjectType
0x140276edc  xor     r9d, r9d; AccessMode
0x140276edf  mov     rbx, [rdi+38h]
0x140276ee3  mov     edx, 1F0003h; DesiredAccess
0x140276ee8  mov     rcx, rbx; Object
0x140276eeb  mov     r8, [r8]; ObjectType
0x140276eee  call    cs:__imp_ObReferenceObjectByPointer
0x140276ef5  nop     dword ptr [rax+rax+00h]
0x140276efa  call    cs:__imp_UserSessionSwitchLeaveCrit
0x140276f01  nop     dword ptr [rax+rax+00h]
0x140276f06  xor     r9d, r9d; Alertable
0x140276f09  mov     [rsp+110h+Timeout], 0; Timeout
0x140276f12  xor     r8d, r8d; WaitMode
0x140276f15  mov     rcx, rbx; Object
0x140276f18  lea     edx, [r9+0Dh]; WaitReason
0x140276f1c  call    cs:__imp_KeWaitForSingleObject
0x140276f23  nop     dword ptr [rax+rax+00h]
0x140276f28  xor     edx, edx
0x140276f2a  lea     ecx, [rdx+1]
0x140276f2d  call    cs:__imp_EnterCrit
0x140276f34  nop     dword ptr [rax+rax+00h]
0x140276f39  mov     rcx, rbx; Object
0x140276f3c  call    cs:__imp_ObfDereferenceObject
0x140276f43  nop     dword ptr [rax+rax+00h]
0x140276f48  call    Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline
0x140276f4d  test    eax, eax
0x140276f4f  mov     eax, [rdi]
0x140276f51  jnz     short loc_140276F57
0x140276f53  test    al, 8
0x140276f55  jmp     short loc_140276F59
0x140276f57  test    al, 10h
0x140276f59  jz      loc_140277135
0x140276f5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140276f66  lea     rax, WPP_GLOBAL_Control
0x140276f6d  cmp     rcx, rax
0x140276f70  jz      short loc_140276F88
0x140276f72  test    dword ptr [rcx+2Ch], 80000h
0x140276f79  jz      short loc_140276F88
0x140276f7b  cmp     byte ptr [rcx+29h], 4
0x140276f7f  jb      short loc_140276F88
0x140276f81  mov     bl, 1
0x140276f83  xor     r13d, r13d
0x140276f86  jmp     short loc_140276F8E
0x140276f88  xor     r13d, r13d
0x140276f8b  mov     bl, r13b
0x140276f8e  lea     rax, WPP_RECORDER_INITIALIZED
0x140276f95  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140276f9c  setnz   r12b
0x140276fa0  test    bl, bl
0x140276fa2  jnz     short loc_140276FA9
0x140276fa4  test    r12b, r12b
0x140276fa7  jz      short loc_140276FF1
0x140276fa9  call    cs:__imp_W32GetUserSessionState
0x140276fb0  nop     dword ptr [rax+rax+00h]
0x140276fb5  mov     rcx, cs:WPP_GLOBAL_Control
0x140276fbc  mov     r8b, r12b
0x140276fbf  mov     dl, bl
0x140276fc1  mov     r9, [rax+10E20h]
0x140276fc8  lea     rax, WPP_8482796ea87931402564603ebe19074e_Traceguids
0x140276fcf  mov     rcx, [rcx+18h]
0x140276fd3  mov     [rsp+110h+var_D8], rax
0x140276fd8  mov     [rsp+110h+var_E0], 17h
0x140276fdf  mov     dword ptr [rsp+110h+var_E8], 14h
0x140276fe7  mov     byte ptr [rsp+110h+Timeout], 4
0x140276fec  call    WPP_RECORDER_AND_TRACE_SF_
0x140276ff1  lock or [rsp+110h+var_110], r13d
0x140276ff6  cmp     [rdi+8], r13
0x140276ffa  jz      short loc_140277004
0x140276ffc  mov     rcx, rdi; struct tagTERMINAL *
0x140276fff  call    ?xxxCleanupMotherDesktopWindow@@YAXPEAUtagTERMINAL@@@Z; xxxCleanupMotherDesktopWindow(tagTERMINAL *)
0x140277004  call    Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline
0x140277009  test    eax, eax
0x14027700b  jz      short loc_140277018
0x14027700d  mov     rdx, rdi; struct tagTERMINAL *
0x140277010  mov     rcx, r15; struct tagTHREADINFO *
0x140277013  call    ?DestroyPendingDesktops@@YAXPEAUtagTHREADINFO@@PEAUtagTERMINAL@@@Z; DestroyPendingDesktops(tagTHREADINFO *,tagTERMINAL *)
0x140277018  mov     rcx, [rdi+28h]; Event
0x14027701c  test    rcx, rcx
0x14027701f  jz      short loc_140277034
0x140277021  xor     r8d, r8d; Wait
0x140277024  lea     edx, [r8+1]; Increment
0x140277028  call    cs:__imp_KeSetEvent
0x14027702f  nop     dword ptr [rax+rax+00h]
0x140277034  add     dword ptr [r14+200h], 0FFFFFFFFh
0x14027703c  jnz     short loc_140277073
0x14027703e  mov     rcx, r14; this
0x140277041  call    ?IsAnyThreadAttached@tagQ@@QEBA_NXZ; tagQ::IsAnyThreadAttached(void)
0x140277046  test    al, al
0x140277048  jnz     short loc_140277073
0x14027704a  test    dword ptr [r14+1FCh], 4000000h
0x140277055  jz      short loc_140277073
  ... truncated ...
```
