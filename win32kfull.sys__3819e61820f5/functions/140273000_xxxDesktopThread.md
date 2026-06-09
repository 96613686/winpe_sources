# xxxDesktopThread

- ea: `0x140273000`
- end: `0x140273953`
- name: `xxxDesktopThread`
- size: `2387`
- prototype: `__int64 __fastcall(struct tagTERMINAL *)`
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140034ee4`
- `0x140077ab8`
- `0x1400b71ac`
- `0x1400bcaa0`
- `0x140107aa8`
- `0x1401939d0`
- `0x1402356d8`
- `0x14024ae0c`
- `0x14025ad4c`
- `0x1402720c0`
- `0x140273000`
- `0x1402913f0`
- `0x1402a8a4c`
- `0x140341ff0`
- `0x140342540`

## import_xrefs

- `ntoskrnl!ZwSetInformationProcess` at `0x140273646`
- `ntoskrnl!ZwSetInformationProcess` at `0x1402738a6`
- `ntoskrnl!ZwSetInformationProcess` at `0x140273646`
- `ntoskrnl!ZwSetInformationProcess` at `0x1402738a6`
- `ntoskrnl!ObReferenceObjectByPointer` at `0x1402733ce`
- `ntoskrnl!ObReferenceObjectByPointer` at `0x1402733ce`
- `ntoskrnl!ExEventObjectType` at `0x1402733b5`
- `ntoskrnl!KeSetEvent` at `0x140273194`
- `ntoskrnl!KeSetEvent` at `0x1402733a9`
- `ntoskrnl!KeSetEvent` at `0x140273508`
- `ntoskrnl!KeSetEvent` at `0x1402738e0`
- `ntoskrnl!KeSetEvent` at `0x140273194`
- `ntoskrnl!KeSetEvent` at `0x1402733a9`
- `ntoskrnl!KeSetEvent` at `0x140273508`
- `ntoskrnl!KeSetEvent` at `0x1402738e0`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402733fc`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402733fc`
- `ntoskrnl!RtlInitUnicodeString` at `0x140273100`
- `ntoskrnl!RtlInitUnicodeString` at `0x140273100`
- `ntoskrnl!ObfDereferenceObject` at `0x14027341c`
- `ntoskrnl!ObfDereferenceObject` at `0x140273564`
- `ntoskrnl!ObfDereferenceObject` at `0x14027341c`
- `ntoskrnl!ObfDereferenceObject` at `0x140273564`
- `win32kbase!?SetDTEThread@tagTERMINAL@@QEAAXXZ` at `0x140273392`
- `win32kbase!?SetDTEThread@tagTERMINAL@@QEAAXXZ` at `0x140273621`
- `win32kbase!?SetDTEThread@tagTERMINAL@@QEAAXXZ` at `0x140273392`
- `win32kbase!?SetDTEThread@tagTERMINAL@@QEAAXXZ` at `0x140273621`
- `win32kbase!?ClearDTEThread@tagTERMINAL@@QEAAXXZ` at `0x140273580`
- `win32kbase!?ClearDTEThread@tagTERMINAL@@QEAAXXZ` at `0x1402738b5`
- `win32kbase!?ClearDTEThread@tagTERMINAL@@QEAAXXZ` at `0x140273580`
- `win32kbase!?ClearDTEThread@tagTERMINAL@@QEAAXXZ` at `0x1402738b5`
- `win32kbase!zzzDestroyQueue` at `0x140273831`
- `win32kbase!zzzDestroyQueue` at `0x140273831`
- `win32kbase!CleanupSensorExplicitly` at `0x140273594`
- `win32kbase!CleanupSensorExplicitly` at `0x140273845`
- `win32kbase!CleanupSensorExplicitly` at `0x140273594`
- `win32kbase!CleanupSensorExplicitly` at `0x140273845`
- `win32kbase!?RegisterDispatcherObject@CBaseInput@@QEAAJPEAVIRegisterInputDispatcherObjects@@@Z` at `0x1402736f1`
- `win32kbase!?RegisterDispatcherObject@CBaseInput@@QEAAJPEAVIRegisterInputDispatcherObjects@@@Z` at `0x1402736f1`
- `win32kbase!?Initialize@LegacyInputDispatcher@@QEAAJD_NIIPEAULegacyDispatcherObject@@@Z` at `0x1402736c0`
- `win32kbase!?Initialize@LegacyInputDispatcher@@QEAAJD_NIIPEAULegacyDispatcherObject@@@Z` at `0x1402736c0`
- `win32kbase!?Create@LegacyInputDispatcher@@SAJPEAPEAV1@@Z` at `0x140273173`
- `win32kbase!?Create@LegacyInputDispatcher@@SAJPEAPEAV1@@Z` at `0x1402731f9`
- `win32kbase!?Create@LegacyInputDispatcher@@SAJPEAPEAV1@@Z` at `0x140273173`
- `win32kbase!?Create@LegacyInputDispatcher@@SAJPEAPEAV1@@Z` at `0x1402731f9`
- `win32kbase!?Read@CBaseInput@@QEAAJXZ` at `0x140273338`
- `win32kbase!?Read@CBaseInput@@QEAAJXZ` at `0x140273338`
- `win32kbase!?InitializeSensor@CBaseInput@@QEAAJXZ` at `0x1402732ca`
- `win32kbase!?InitializeSensor@CBaseInput@@QEAAJXZ` at `0x140273359`
- `win32kbase!?InitializeSensor@CBaseInput@@QEAAJXZ` at `0x1402732ca`
- `win32kbase!?InitializeSensor@CBaseInput@@QEAAJXZ` at `0x140273359`
- `win32kbase!InitSystemThread` at `0x140273135`
- `win32kbase!InitSystemThread` at `0x140273135`
- `win32kbase!SetThreadBasePriority` at `0x14027307a`
- `win32kbase!SetThreadBasePriority` at `0x14027307a`
- `win32kbase!SetThreadName` at `0x140273125`
- `win32kbase!SetThreadName` at `0x140273125`
- `win32kbase!CreateKernelEvent` at `0x1402730c4`
- `win32kbase!CreateKernelEvent` at `0x1402730c4`
- `win32kbase!?HandleTSRequest@CBaseInput@@QEAAXW4InputTSRequest@@@Z` at `0x14027330d`
- `win32kbase!?HandleTSRequest@CBaseInput@@QEAAXW4InputTSRequest@@@Z` at `0x14027330d`
- `win32kbase!EnterCrit` at `0x1402732ec`
- `win32kbase!EnterCrit` at `0x14027336e`
- `win32kbase!EnterCrit` at `0x14027340d`
- `win32kbase!EnterCrit` at `0x1402732ec`
- `win32kbase!EnterCrit` at `0x14027336e`
- `win32kbase!EnterCrit` at `0x14027340d`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x140273319`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1402733da`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1402738c1`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x140273319`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1402733da`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1402738c1`
- `win32kbase!Win32FreePool` at `0x1402735fd`
- `win32kbase!Win32FreePool` at `0x14027387d`
- `win32kbase!Win32FreePool` at `0x14027391b`
- `win32kbase!Win32FreePool` at `0x1402735fd`
- `win32kbase!Win32FreePool` at `0x14027387d`
- `win32kbase!Win32FreePool` at `0x14027391b`
- `win32kbase!HMAssignmentUnlock` at `0x1402737a8`
- `win32kbase!HMAssignmentUnlock` at `0x1402737d0`
- `win32kbase!HMAssignmentUnlock` at `0x1402737a8`
- `win32kbase!HMAssignmentUnlock` at `0x1402737d0`
- `WIN32K!W32GetUserSessionState` at `0x14027304e`
- `WIN32K!W32GetUserSessionState` at `0x14027308e`
- `WIN32K!W32GetUserSessionState` at `0x1402730d3`
- `WIN32K!W32GetUserSessionState` at `0x14027314d`
- `WIN32K!W32GetUserSessionState` at `0x1402731cb`
- `WIN32K!W32GetUserSessionState` at `0x14027321b`
- `WIN32K!W32GetUserSessionState` at `0x14027324a`
- `WIN32K!W32GetUserSessionState` at `0x140273276`
- `WIN32K!W32GetUserSessionState` at `0x1402732b7`
- `WIN32K!W32GetUserSessionState` at `0x1402732f8`
- `WIN32K!W32GetUserSessionState` at `0x140273325`
- `WIN32K!W32GetUserSessionState` at `0x140273346`
- `WIN32K!W32GetUserSessionState` at `0x140273489`
- `WIN32K!W32GetUserSessionState` at `0x1402735b6`
- `WIN32K!W32GetUserSessionState` at `0x1402735e7`
- `WIN32K!W32GetUserSessionState` at `0x140273692`
- `WIN32K!W32GetUserSessionState` at `0x1402736da`
- `WIN32K!W32GetUserSessionState` at `0x14027370a`
- `WIN32K!W32GetUserSessionState` at `0x140273752`
- `WIN32K!W32GetUserSessionState` at `0x140273769`
- `WIN32K!W32GetUserSessionState` at `0x1402737dc`
- `WIN32K!W32GetUserSessionState` at `0x140273867`
- `WIN32K!W32GetUserSessionState` at `0x1402738f0`
- `WIN32K!W32GetUserSessionState` at `0x140273905`
- `WIN32K!W32GetUserSessionState` at `0x14027304e`
- `WIN32K!W32GetUserSessionState` at `0x14027308e`
- `WIN32K!W32GetUserSessionState` at `0x1402730d3`
- `WIN32K!W32GetUserSessionState` at `0x14027314d`
- `WIN32K!W32GetUserSessionState` at `0x1402731cb`
- `WIN32K!W32GetUserSessionState` at `0x14027321b`
- `WIN32K!W32GetUserSessionState` at `0x14027324a`
- `WIN32K!W32GetUserSessionState` at `0x140273276`
- `WIN32K!W32GetUserSessionState` at `0x1402732b7`
- `WIN32K!W32GetUserSessionState` at `0x1402732f8`
- `WIN32K!W32GetUserSessionState` at `0x140273325`
- `WIN32K!W32GetUserSessionState` at `0x140273346`
- `WIN32K!W32GetUserSessionState` at `0x140273489`
- `WIN32K!W32GetUserSessionState` at `0x1402735b6`
- `WIN32K!W32GetUserSessionState` at `0x1402735e7`
- `WIN32K!W32GetUserSessionState` at `0x140273692`
- `WIN32K!W32GetUserSessionState` at `0x1402736da`
- `WIN32K!W32GetUserSessionState` at `0x14027370a`
- `WIN32K!W32GetUserSessionState` at `0x140273752`
- `WIN32K!W32GetUserSessionState` at `0x140273769`
- `WIN32K!W32GetUserSessionState` at `0x1402737dc`
- `WIN32K!W32GetUserSessionState` at `0x140273867`
- `WIN32K!W32GetUserSessionState` at `0x1402738f0`
- `WIN32K!W32GetUserSessionState` at `0x140273905`

## string_xrefs

- `0x14027311e`: `Win32k Desktop Thread (NOIO_DT)`
- `0x14027310c`: `Win32k Desktop Thread (IO_DT)`

## pseudocode

```c
void __fastcall xxxDesktopThread(PRKEVENT *a1)
{
  int v2; // esi
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  int v7; // r12d
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 KernelEvent; // rbx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  const WCHAR *v17; // rdx
  const wchar_t *v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  struct tagTHREADINFO *v27; // rax
  struct tagTHREADINFO *v28; // r15
  struct _KEVENT *v29; // r14
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // r9
  unsigned int v38; // r13d
  unsigned int v39; // r13d
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // rbx
  __int64 v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 v50; // rax
  __int64 v51; // rdx
  __int64 v52; // rcx
  __int64 v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // r8
  __int64 v56; // r9
  __int64 v57; // rdx
  __int64 v58; // rcx
  __int64 v59; // r8
  __int64 v60; // r9
  __int64 v61; // rax
  __int64 v62; // rdx
  __int64 v63; // rcx
  __int64 v64; // r8
  __int64 v65; // rax
  __int64 v66; // rax
  PRKEVENT v67; // rbx
  __int64 v68; // rdx
  __int64 v69; // rcx
  __int64 v70; // r8
  __int64 v71; // rdx
  __int64 v72; // r8
  __int64 v73; // r9
  int v74; // eax
  bool v75; // zf
  bool v76; // bl
  bool v77; // r12
  __int64 v78; // rax
  int v79; // r8d
  int v80; // edx
  struct _KEVENT *v81; // rcx
  PRKEVENT v82; // rcx
  __int64 v83; // rdx
  __int64 v84; // r8
  __int64 v85; // r9
  LegacyInputDispatcher *v86; // rcx
  __int64 v87; // rdx
  __int64 v88; // rcx
  __int64 v89; // r8
  __int64 v90; // r9
  __int64 v91; // rbx
  __int64 v92; // rdx
  __int64 v93; // r8
  __int64 v94; // r9
  __int64 v95; // rcx
  unsigned int v96; // r12d
  __int64 v97; // rdx
  __int64 v98; // rcx
  __int64 v99; // r8
  __int64 v100; // r9
  __int64 v101; // rax
  __int64 v102; // rax
  LegacyInputDispatcher *v103; // rcx
  __int64 v104; // rdx
  __int64 v105; // r8
  __int64 v106; // r9
  __int64 v107; // rdx
  __int64 v108; // rcx
  __int64 v109; // r8
  __int64 v110; // r9
  __int64 v111; // rax
  __int64 v112; // rdx
  __int64 v113; // r8
  __int64 v114; // r9
  _QWORD *v115; // rcx
  __int64 v116; // rax
  __int64 v117; // rdx
  __int64 v118; // r8
  __int64 v119; // r9
  LegacyInputDispatcher *v120; // rcx
  __int64 v121; // rbx
  __int64 v122; // rdx
  __int64 v123; // rcx
  __int64 v124; // r8
  __int64 v125; // r9
  __int64 UserSessionState; // rbx
  signed __int32 v127[8]; // [rsp+0h] [rbp-B9h] BYREF
  char v128; // [rsp+40h] [rbp-79h]
  int v129; // [rsp+44h] [rbp-75h]
  LegacyInputDispatcher *v130; // [rsp+48h] [rbp-71h] BYREF
  int ProcessInformation; // [rsp+50h] [rbp-69h] BYREF
  int v132; // [rsp+54h] [rbp-65h]
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-61h] BYREF
  __int64 v134; // [rsp+70h] [rbp-49h] BYREF
  _QWORD v135[9]; // [rsp+78h] [rbp-41h]

  ProcessInformation = 0;
  v130 = 0;
  DestinationString = 0;
  memset_0(&v134, 0, 0x50u);
  v2 = *(_DWORD *)a1 & 2;
  v7 = *(_DWORD *)(W32GetUserSessionState(v4, v3, v5, v6) + 19176);
  v132 = v7;
  SetThreadBasePriority(KeGetCurrentThread(), v2 != 0 ? 12 : 16);
  if ( !v2 )
  {
    if ( *(_QWORD *)(W32GetUserSessionState(v9, v8, v10, v11) + 62960) )
    {
      v129 = 0x20000;
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 846);
    }
    KernelEvent = CreateKernelEvent(1, 0);
    *(_QWORD *)(W32GetUserSessionState(v14, v13, v15, v16) + 62960) = KernelEvent;
  }
  v17 = L"IO_DT";
  if ( v2 )
    v17 = L"NOIO_DT";
  RtlInitUnicodeString(&DestinationString, v17);
  v18 = L"Win32k Desktop Thread (IO_DT)";
  if ( v2 )
    v18 = L"Win32k Desktop Thread (NOIO_DT)";
  SetThreadName(-2, v18);
  if ( (int)InitSystemThread(&DestinationString) < 0
    || !v2 && !*(_QWORD *)(W32GetUserSessionState(v20, v19, v21, v22) + 62960) )
  {
    *(_DWORD *)a1 |= 8u;
    _InterlockedOr(v127, 0);
    KeSetEvent(a1[5], 1, 0);
    if ( v2 || !*(_QWORD *)(W32GetUserSessionState(v123, v122, v124, v125) + 62960) )
      return;
LABEL_103:
    UserSessionState = W32GetUserSessionState(v24, v23, v25, v26);
    Win32FreePool(*(void **)(UserSessionState + 62960));
    *(_QWORD *)(UserSessionState + 62960) = 0;
    return;
  }
  if ( (unsigned int)Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline()
    && (int)LegacyInputDispatcher::Create(&v130) < 0 )
  {
    goto LABEL_14;
  }
  v27 = PtiCurrent();
  a1[2] = (PRKEVENT)v27;
  v28 = v27;
  v29 = (struct _KEVENT *)*((_QWORD *)v27 + 58);
  a1[3] = v29;
  ++LODWORD(v29[21].Header.WaitListHead.Flink);
  *((_QWORD *)v27 + 62) = *(_QWORD *)(W32GetUserSessionState(v31, v30, v32, v33) + 62688);
  *((_QWORD *)v28 + 81) = 0;
  if ( !(unsigned int)Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline()
    && (int)LegacyInputDispatcher::Create(&v130) < 0 )
  {
LABEL_14:
    *(_DWORD *)a1 |= 8u;
    _InterlockedOr(v127, 0);
    KeSetEvent(a1[5], 1, 0);
    if ( v2 )
      return;
    goto LABEL_103;
  }
  v128 = 0;
  v38 = 0;
  if ( !v2 )
  {
    v39 = 1;
    v41 = *(_QWORD *)(W32GetUserSessionState(v35, v34, v36, v37) + 36144);
    v134 = *(_QWORD *)(v41 + 72);
    v135[0] = OnPointerCursorOperation;
    if ( !v7 )
    {
      v39 = 2;
      v41 = *(_QWORD *)(W32GetUserSessionState(v41, v40, v42, v43) + 16776);
      v135[2] = OnPTPMouseOperation;
      v135[1] = v41;
    }
    v44 = 2LL * v39;
    v38 = v39 + 1;
    v45 = *(_QWORD *)(W32GetUserSessionState(v41, v40, v42, v43) + 62960);
    v135[v44] = lambda_4b651d6c306d13f8deac809f2617e82f_::_lambda_invoker_cdecl_;
    v135[v44 - 1] = v45;
    if ( (unsigned int)IsCurrentSessionServiceSession() )
    {
      v66 = W32GetUserSessionState(v47, v46, v48, v49);
      CBaseInput::InitializeSensor(*(CBaseInput **)(v66 + 3048));
      v128 = 1;
    }
    else if ( !v7 )
    {
      v128 = 1;
      v50 = W32GetUserSessionState(v47, v46, v48, v49);
      if ( (int)CBaseInput::InitializeSensor(*(CBaseInput **)(v50 + 3048)) >= 0 )
      {
        if ( (unsigned int)IsRemoteConnection(v52, v51) )
        {
          EnterCrit(1, 0);
          v61 = W32GetUserSessionState(v58, v57, v59, v60);
          CBaseInput::HandleTSRequest(*(_QWORD *)(v61 + 3048), 0);
          UserSessionSwitchLeaveCrit(v63, v62, v64);
        }
        v65 = W32GetUserSessionState(v54, v53, v55, v56);
        CBaseInput::Read(*(CBaseInput **)(v65 + 3048));
      }
    }
  }
  EnterCrit(1, 0);
  if ( !(unsigned int)Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline() )
    *(_DWORD *)a1 |= 4u;
  if ( (unsigned int)Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline() )
    tagTERMINAL::SetDTEThread((tagTERMINAL *)a1);
  KeSetEvent(a1[5], 1, 0);
  v67 = a1[7];
  ObReferenceObjectByPointer(v67, 0x1F0003u, (POBJECT_TYPE)ExEventObjectType, 0);
  UserSessionSwitchLeaveCrit(v69, v68, v70);
  KeWaitForSingleObject(v67, WrUserRequest, 0, 0, 0);
  EnterCrit(1, 0);
  ObfDereferenceObject(v67);
  v75 = (unsigned int)Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline() == 0;
  v74 = *(_DWORD *)a1;
  if ( v75 )
    v75 = (v74 & 8) == 0;
  else
    v75 = (v74 & 0x10) == 0;
  if ( v75 )
  {
    if ( !(unsigned int)Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline() )
      tagTERMINAL::SetDTEThread((tagTERMINAL *)a1);
    ProcessInformation = 1;
    ZwSetInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessBreakOnTermination, &ProcessInformation, 4u);
    v95 = 2LL * v38;
    v135[2 * v38 - 1] = *((_QWORD *)v28 + 201);
    if ( v38 + 1 > 5 )
    {
      v129 = 0x20000;
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1155);
    }
    if ( v2 || v7 )
    {
      v96 = v38 + 1;
    }
    else
    {
      W32GetUserSessionState(v95, v92, v93, v94);
      v96 = v38 + 10;
    }
    LegacyInputDispatcher::Initialize(v130, 1, 0, v96, v38 + 1, (struct LegacyDispatcherObject *)&v134);
    if ( v96 != v38 + 1 && !v132 )
    {
      v101 = W32GetUserSessionState(v98, v97, v99, v100);
      CBaseInput::RegisterDispatcherObject(*(CBaseInput **)(v101 + 3048), v130);
    }
    *((_DWORD *)v130 + 15) = v38;
    v102 = W32GetUserSessionState(v98, v97, v99, v100);
    if ( v2 )
    {
      *(_QWORD *)(v102 + 19240) = v130;
    }
    else
    {
      v103 = v130;
      *(_QWORD *)(v102 + 19232) = v130;
    }
    do
    {
      do
        LOBYTE(v103) = 1;
      while ( (unsigned int)xxxDesktopThreadWaiter(v103, 0) != v38 );
    }
    while ( (unsigned int)xxxHandleDesktopMessages(v28, (struct tagTERMINAL *)a1) );
    if ( a1 == (PRKEVENT *)(W32GetUserSessionState(v103, v104, v105, v106) + 68448) )
    {
      v111 = W32GetUserSessionState(v108, v107, v109, v110);
      *(_DWORD *)(v111 + 68920) |= 0x100000u;
    }
    a1[2] = 0;
    a1[3] = 0;
    *((_DWORD *)a1 + 8) = 0;
    if ( !(unsigned int)Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline() )
      *(_DWORD *)a1 = 0;
    v115 = (_QWORD *)*((_QWORD *)v28 + 61);
    if ( v115 )
    {
      HMAssignmentUnlock(v115 + 24);
      v116 = *((_QWORD *)v28 + 61);
      v115 = (_QWORD *)(*(_QWORD *)(v116 + 8) + 24LL);
      if ( *v115 )
      {
        *(_QWORD *)(**(_QWORD **)(v116 + 8) + 8LL) = 0;
        HMAssignmentUnlock(v115);
      }
    }
    *((_QWORD *)v28 + 62) = *(_QWORD *)(W32GetUserSessionState(v115, v112, v113, v114) + 62688);
    if ( !LODWORD(v29[21].Header.WaitListHead.Flink) )
    {
      v129 = 0x20000;
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1259);
    }
    --LODWORD(v29[21].Header.WaitListHead.Flink);
    if ( *((struct _KEVENT **)v28 + 58) != v29 )
      zzzDestroyQueue(v29, v28);
    if ( v128 )
      CleanupSensorExplicitly(0);
    v120 = v130;
    if ( v130 )
      LegacyInputDispatcher::`scalar deleting destructor'(v130, v117);
    v130 = 0;
    if ( !v2 )
    {
      v121 = W32GetUserSessionState(v120, v117, v118, v119);
      Win32FreePool(*(void **)(v121 + 62960));
      *(_QWORD *)(v121 + 62960) = 0;
    }
    ProcessInformation = 0;
    ZwSetInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessBreakOnTermination, &ProcessInformation, 4u);
    tagTERMINAL::ClearDTEThread((tagTERMINAL *)a1);
  }
  else
  {
    v76 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80000) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v77 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v76 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v78 = W32GetUserSessionState(WPP_GLOBAL_Control, v71, v72, v73);
      LOBYTE(v79) = v77;
      LOBYTE(v80) = v76;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v80,
        v79,
        *(_QWORD *)(v78 + 69152),
        4,
        20,
        23,
        (__int64)WPP_8482796ea87931402564603ebe19074e_Traceguids);
    }
    _InterlockedOr(v127, 0);
    if ( a1[1] )
      xxxCleanupMotherDesktopWindow((struct tagTERMINAL *)a1);
    if ( (unsigned int)Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline() )
      DestroyPendingDesktops(v28, (struct tagTERMINAL *)a1);
    v81 = a1[5];
    if ( v81 )
      KeSetEvent(v81, 1, 0);
    v75 = LODWORD(v29[21].Header.WaitListHead.Flink)-- == 1;
    if ( v75 && !tagQ::IsAnyThreadAttached((tagQ *)v29) && (v29[21].Header.SignalState & 0x4000000) != 0 )
    {
      v129 = 0x20000;
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1101);
    }
    v82 = a1[7];
    a1[2] = 0;
    a1[3] = 0;
    if ( v82 )
    {
      ObfDereferenceObject(v82);
      a1[7] = 0;
    }
    if ( (unsigned int)Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline() )
      tagTERMINAL::ClearDTEThread((tagTERMINAL *)a1);
    if ( v128 )
      CleanupSensorExplicitly(0);
    v86 = v130;
    if ( v130 )
      LegacyInputDispatcher::`scalar deleting destructor'(v130, v83);
    if ( !v2 )
    {
      if ( !*(_QWORD *)(W32GetUserSessionState(v86, v83, v84, v85) + 62960) )
      {
        v129 = 0x20000;
        MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1128);
      }
      v91 = W32GetUserSessionState(v88, v87, v89, v90);
      Win32FreePool(*(void **)(v91 + 62960));
      *(_QWORD *)(v91 + 62960) = 0;
    }
  }
  UserSessionSwitchLeaveCrit(v86, v83, v84);
}

```

## disassembly

```asm
0x140273000  push    rbp
0x140273002  push    rbx
0x140273003  push    rsi
0x140273004  push    rdi
0x140273005  push    r12
0x140273007  push    r13
0x140273009  push    r14
0x14027300b  push    r15
0x14027300d  lea     rbp, [rsp-1Fh]
0x140273012  sub     rsp, 0D8h
0x140273019  mov     rax, cs:__security_cookie
0x140273020  xor     rax, rsp
0x140273023  mov     [rbp+57h+var_50], rax
0x140273027  xor     ebx, ebx
0x140273029  mov     rdi, rcx
0x14027302c  xorps   xmm0, xmm0
0x14027302f  mov     [rbp+57h+ProcessInformation], ebx
0x140273032  xor     edx, edx; Val
0x140273034  mov     [rbp+57h+var_C8], rbx
0x140273038  lea     rcx, [rbp+57h+var_A0]; void *
0x14027303c  lea     r8d, [rbx+50h]; Size
0x140273040  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140273044  call    memset_0
0x140273049  mov     esi, [rdi]
0x14027304b  and     esi, 2
0x14027304e  call    cs:__imp_W32GetUserSessionState
0x140273055  nop     dword ptr [rax+rax+00h]
0x14027305a  mov     rcx, gs:188h
0x140273063  mov     r12d, [rax+4AE8h]
0x14027306a  mov     eax, esi
0x14027306c  neg     eax
0x14027306e  mov     [rbp+57h+var_BC], r12d
0x140273072  sbb     edx, edx
0x140273074  and     edx, 0FFFFFFFCh
0x140273077  add     edx, 10h
0x14027307a  call    cs:__imp_SetThreadBasePriority
0x140273081  nop     dword ptr [rax+rax+00h]
0x140273086  lea     r13d, [rbx+1]
0x14027308a  test    esi, esi
0x14027308c  jnz     short loc_1402730E8
0x14027308e  call    cs:__imp_W32GetUserSessionState
0x140273095  nop     dword ptr [rax+rax+00h]
0x14027309a  cmp     [rax+0F5F0h], rbx
0x1402730a1  jz      short loc_1402730BF
0x1402730a3  mov     [rbp+57h+var_CC], 20000h
0x1402730aa  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1402730b1  mov     edx, [rbp+57h+var_CC]
0x1402730b4  mov     r8d, 34Eh
0x1402730ba  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1402730bf  xor     edx, edx
0x1402730c1  mov     ecx, r13d
0x1402730c4  call    cs:__imp_CreateKernelEvent
0x1402730cb  nop     dword ptr [rax+rax+00h]
0x1402730d0  mov     rbx, rax
0x1402730d3  call    cs:__imp_W32GetUserSessionState
0x1402730da  nop     dword ptr [rax+rax+00h]
0x1402730df  mov     [rax+0F5F0h], rbx
0x1402730e6  xor     ebx, ebx
0x1402730e8  lea     rax, aNoioDt; "NOIO_DT"
0x1402730ef  test    esi, esi
0x1402730f1  lea     rdx, aIoDt; "IO_DT"
0x1402730f8  cmovnz  rdx, rax; SourceString
0x1402730fc  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140273100  call    cs:__imp_RtlInitUnicodeString
0x140273107  nop     dword ptr [rax+rax+00h]
0x14027310c  lea     rdx, aWin32kDesktopT; "Win32k Desktop Thread (IO_DT)"
0x140273113  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x14027311a  test    esi, esi
0x14027311c  jz      short loc_140273125
0x14027311e  lea     rdx, aWin32kDesktopT_0; "Win32k Desktop Thread (NOIO_DT)"
0x140273125  call    cs:__imp_SetThreadName
0x14027312c  nop     dword ptr [rax+rax+00h]
0x140273131  lea     rcx, [rbp+57h+DestinationString]
0x140273135  call    cs:__imp_InitSystemThread
0x14027313c  nop     dword ptr [rax+rax+00h]
0x140273141  test    eax, eax
0x140273143  js      loc_1402738CF
0x140273149  test    esi, esi
0x14027314b  jnz     short loc_140273166
0x14027314d  call    cs:__imp_W32GetUserSessionState
0x140273154  nop     dword ptr [rax+rax+00h]
0x140273159  cmp     [rax+0F5F0h], rbx
0x140273160  jz      loc_1402738CF
0x140273166  call    Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline
0x14027316b  test    eax, eax
0x14027316d  jz      short loc_1402731AD
0x14027316f  lea     rcx, [rbp+57h+var_C8]
0x140273173  call    cs:__imp_?Create@LegacyInputDispatcher@@SAJPEAPEAV1@@Z; LegacyInputDispatcher::Create(LegacyInputDispatcher * *)
0x14027317a  nop     dword ptr [rax+rax+00h]
0x14027317f  test    eax, eax
0x140273181  jns     short loc_1402731AD
0x140273183  or      dword ptr [rdi], 8
0x140273186  lock or [rsp+110h+var_110], ebx
0x14027318a  mov     rcx, [rdi+28h]; Event
0x14027318e  xor     r8d, r8d; Wait
0x140273191  mov     edx, r13d; Increment
0x140273194  call    cs:__imp_KeSetEvent
0x14027319b  nop     dword ptr [rax+rax+00h]
0x1402731a0  test    esi, esi
0x1402731a2  jnz     loc_140273932
0x1402731a8  jmp     loc_140273905
0x1402731ad  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1402731b2  mov     [rdi+10h], rax
0x1402731b6  mov     r15, rax
0x1402731b9  mov     r14, [rax+1D0h]
0x1402731c0  mov     [rdi+18h], r14
0x1402731c4  add     [r14+200h], r13d
0x1402731cb  call    cs:__imp_W32GetUserSessionState
0x1402731d2  nop     dword ptr [rax+rax+00h]
0x1402731d7  mov     rcx, [rax+0F4E0h]
0x1402731de  mov     [r15+1F0h], rcx
0x1402731e5  mov     [r15+288h], rbx
0x1402731ec  call    Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline
0x1402731f1  test    eax, eax
0x1402731f3  jnz     short loc_14027320D
0x1402731f5  lea     rcx, [rbp+57h+var_C8]
0x1402731f9  call    cs:__imp_?Create@LegacyInputDispatcher@@SAJPEAPEAV1@@Z; LegacyInputDispatcher::Create(LegacyInputDispatcher * *)
0x140273200  nop     dword ptr [rax+rax+00h]
0x140273205  test    eax, eax
0x140273207  js      loc_140273183
0x14027320d  mov     [rbp+57h+var_D0], bl
0x140273210  mov     r13d, ebx
0x140273213  test    esi, esi
0x140273215  jnz     loc_140273369
0x14027321b  call    cs:__imp_W32GetUserSessionState
0x140273222  nop     dword ptr [rax+rax+00h]
0x140273227  lea     r13d, [rsi+1]
0x14027322b  mov     rcx, [rax+8D30h]
0x140273232  mov     rax, [rcx+48h]
0x140273236  mov     [rbp+57h+var_A0], rax
0x14027323a  lea     rax, ?OnPointerCursorOperation@@YAXXZ; OnPointerCursorOperation(void)
0x140273241  mov     [rbp+57h+var_98], rax
0x140273245  test    r12d, r12d
0x140273248  jnz     short loc_140273270
0x14027324a  call    cs:__imp_W32GetUserSessionState
0x140273251  nop     dword ptr [rax+rax+00h]
0x140273256  lea     r13d, [rsi+2]
0x14027325a  mov     rcx, [rax+4188h]
0x140273261  lea     rax, OnPTPMouseOperation
0x140273268  mov     [rbp+57h+var_88], rax
0x14027326c  mov     [rbp+57h+var_90], rcx
0x140273270  mov     ebx, r13d
0x140273273  add     rbx, rbx
0x140273276  call    cs:__imp_W32GetUserSessionState
0x14027327d  nop     dword ptr [rax+rax+00h]
0x140273282  inc     r13d
0x140273285  mov     rcx, [rax+0F5F0h]
0x14027328c  lea     rax, _lambda_4b651d6c306d13f8deac809f2617e82f____lambda_invoker_cdecl_
0x140273293  mov     [rbp+rbx*8+57h+var_98], rax
0x140273298  mov     [rbp+rbx*8+57h+var_A0], rcx
0x14027329d  call    IsCurrentSessionServiceSession
0x1402732a2  test    eax, eax
0x1402732a4  jnz     loc_140273346
0x1402732aa  test    r12d, r12d
0x1402732ad  jnz     loc_140273369
0x1402732b3  mov     [rbp+57h+var_D0], 1
0x1402732b7  call    cs:__imp_W32GetUserSessionState
0x1402732be  nop     dword ptr [rax+rax+00h]
0x1402732c3  mov     rcx, [rax+0BE8h]
0x1402732ca  call    cs:__imp_?InitializeSensor@CBaseInput@@QEAAJXZ; CBaseInput::InitializeSensor(void)
0x1402732d1  nop     dword ptr [rax+rax+00h]
0x1402732d6  test    eax, eax
0x1402732d8  js      loc_140273369
0x1402732de  call    IsRemoteConnection
0x1402732e3  test    eax, eax
0x1402732e5  jz      short loc_140273325
0x1402732e7  xor     edx, edx
0x1402732e9  lea     ecx, [rdx+1]
0x1402732ec  call    cs:__imp_EnterCrit
0x1402732f3  nop     dword ptr [rax+rax+00h]
0x1402732f8  call    cs:__imp_W32GetUserSessionState
0x1402732ff  nop     dword ptr [rax+rax+00h]
0x140273304  xor     edx, edx
0x140273306  mov     rcx, [rax+0BE8h]
0x14027330d  call    cs:__imp_?HandleTSRequest@CBaseInput@@QEAAXW4InputTSRequest@@@Z; CBaseInput::HandleTSRequest(InputTSRequest)
0x140273314  nop     dword ptr [rax+rax+00h]
0x140273319  call    cs:__imp_UserSessionSwitchLeaveCrit
0x140273320  nop     dword ptr [rax+rax+00h]
0x140273325  call    cs:__imp_W32GetUserSessionState
0x14027332c  nop     dword ptr [rax+rax+00h]
0x140273331  mov     rcx, [rax+0BE8h]
0x140273338  call    cs:__imp_?Read@CBaseInput@@QEAAJXZ; CBaseInput::Read(void)
0x14027333f  nop     dword ptr [rax+rax+00h]
0x140273344  jmp     short loc_140273369
0x140273346  call    cs:__imp_W32GetUserSessionState
0x14027334d  nop     dword ptr [rax+rax+00h]
0x140273352  mov     rcx, [rax+0BE8h]
0x140273359  call    cs:__imp_?InitializeSensor@CBaseInput@@QEAAJXZ; CBaseInput::InitializeSensor(void)
0x140273360  nop     dword ptr [rax+rax+00h]
0x140273365  mov     [rbp+57h+var_D0], 1
0x140273369  xor     edx, edx
0x14027336b  lea     ecx, [rdx+1]
0x14027336e  call    cs:__imp_EnterCrit
0x140273375  nop     dword ptr [rax+rax+00h]
0x14027337a  call    Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline
0x14027337f  test    eax, eax
0x140273381  jnz     short loc_140273386
0x140273383  or      dword ptr [rdi], 4
0x140273386  call    Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline
0x14027338b  test    eax, eax
0x14027338d  jz      short loc_14027339E
0x14027338f  mov     rcx, rdi
0x140273392  call    cs:__imp_?SetDTEThread@tagTERMINAL@@QEAAXXZ; tagTERMINAL::SetDTEThread(void)
0x140273399  nop     dword ptr [rax+rax+00h]
0x14027339e  mov     rcx, [rdi+28h]; Event
0x1402733a2  xor     r8d, r8d; Wait
0x1402733a5  lea     edx, [r8+1]; Increment
0x1402733a9  call    cs:__imp_KeSetEvent
0x1402733b0  nop     dword ptr [rax+rax+00h]
0x1402733b5  mov     r8, cs:ExEventObjectType
0x1402733bc  xor     r9d, r9d; AccessMode
0x1402733bf  mov     rbx, [rdi+38h]
0x1402733c3  mov     edx, 1F0003h; DesiredAccess
0x1402733c8  mov     rcx, rbx; Object
0x1402733cb  mov     r8, [r8]; ObjectType
0x1402733ce  call    cs:__imp_ObReferenceObjectByPointer
0x1402733d5  nop     dword ptr [rax+rax+00h]
0x1402733da  call    cs:__imp_UserSessionSwitchLeaveCrit
0x1402733e1  nop     dword ptr [rax+rax+00h]
0x1402733e6  xor     r9d, r9d; Alertable
0x1402733e9  mov     [rsp+110h+Timeout], 0; Timeout
0x1402733f2  xor     r8d, r8d; WaitMode
0x1402733f5  mov     rcx, rbx; Object
0x1402733f8  lea     edx, [r9+0Dh]; WaitReason
0x1402733fc  call    cs:__imp_KeWaitForSingleObject
0x140273403  nop     dword ptr [rax+rax+00h]
0x140273408  xor     edx, edx
0x14027340a  lea     ecx, [rdx+1]
0x14027340d  call    cs:__imp_EnterCrit
0x140273414  nop     dword ptr [rax+rax+00h]
0x140273419  mov     rcx, rbx; Object
0x14027341c  call    cs:__imp_ObfDereferenceObject
0x140273423  nop     dword ptr [rax+rax+00h]
0x140273428  call    Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline
0x14027342d  test    eax, eax
0x14027342f  mov     eax, [rdi]
0x140273431  jnz     short loc_140273437
0x140273433  test    al, 8
0x140273435  jmp     short loc_140273439
0x140273437  test    al, 10h
0x140273439  jz      loc_140273615
0x14027343f  mov     rcx, cs:WPP_GLOBAL_Control
0x140273446  lea     rax, WPP_GLOBAL_Control
0x14027344d  cmp     rcx, rax
0x140273450  jz      short loc_140273468
0x140273452  test    dword ptr [rcx+2Ch], 80000h
0x140273459  jz      short loc_140273468
0x14027345b  cmp     byte ptr [rcx+29h], 4
0x14027345f  jb      short loc_140273468
0x140273461  mov     bl, 1
0x140273463  xor     r13d, r13d
0x140273466  jmp     short loc_14027346E
0x140273468  xor     r13d, r13d
0x14027346b  mov     bl, r13b
0x14027346e  lea     rax, WPP_RECORDER_INITIALIZED
0x140273475  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14027347c  setnz   r12b
0x140273480  test    bl, bl
0x140273482  jnz     short loc_140273489
0x140273484  test    r12b, r12b
0x140273487  jz      short loc_1402734D1
0x140273489  call    cs:__imp_W32GetUserSessionState
0x140273490  nop     dword ptr [rax+rax+00h]
0x140273495  mov     rcx, cs:WPP_GLOBAL_Control
0x14027349c  mov     r8b, r12b
0x14027349f  mov     dl, bl
0x1402734a1  mov     r9, [rax+10E20h]
0x1402734a8  lea     rax, WPP_8482796ea87931402564603ebe19074e_Traceguids
0x1402734af  mov     rcx, [rcx+18h]
0x1402734b3  mov     [rsp+110h+var_D8], rax
0x1402734b8  mov     [rsp+110h+var_E0], 17h
0x1402734bf  mov     dword ptr [rsp+110h+var_E8], 14h
0x1402734c7  mov     byte ptr [rsp+110h+Timeout], 4
0x1402734cc  call    WPP_RECORDER_AND_TRACE_SF_
0x1402734d1  lock or [rsp+110h+var_110], r13d
0x1402734d6  cmp     [rdi+8], r13
0x1402734da  jz      short loc_1402734E4
0x1402734dc  mov     rcx, rdi; struct tagTERMINAL *
0x1402734df  call    ?xxxCleanupMotherDesktopWindow@@YAXPEAUtagTERMINAL@@@Z; xxxCleanupMotherDesktopWindow(tagTERMINAL *)
0x1402734e4  call    Feature_TERMNOIO_CSRSS_Session_Fix__private_IsEnabledDeviceUsageNoInline
0x1402734e9  test    eax, eax
0x1402734eb  jz      short loc_1402734F8
0x1402734ed  mov     rdx, rdi; struct tagTERMINAL *
0x1402734f0  mov     rcx, r15; struct tagTHREADINFO *
0x1402734f3  call    ?DestroyPendingDesktops@@YAXPEAUtagTHREADINFO@@PEAUtagTERMINAL@@@Z; DestroyPendingDesktops(tagTHREADINFO *,tagTERMINAL *)
0x1402734f8  mov     rcx, [rdi+28h]; Event
0x1402734fc  test    rcx, rcx
0x1402734ff  jz      short loc_140273514
0x140273501  xor     r8d, r8d; Wait
0x140273504  lea     edx, [r8+1]; Increment
0x140273508  call    cs:__imp_KeSetEvent
0x14027350f  nop     dword ptr [rax+rax+00h]
0x140273514  add     dword ptr [r14+200h], 0FFFFFFFFh
0x14027351c  jnz     short loc_140273553
0x14027351e  mov     rcx, r14; this
0x140273521  call    ?IsAnyThreadAttached@tagQ@@QEBA_NXZ; tagQ::IsAnyThreadAttached(void)
0x140273526  test    al, al
0x140273528  jnz     short loc_140273553
0x14027352a  test    dword ptr [r14+1FCh], 4000000h
0x140273535  jz      short loc_140273553
  ... truncated ...
```
