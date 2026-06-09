# WorkerTaskMigrationSource::DoStateTransferSteps(__int64 &)

- ea: `0x14005905c`
- end: `0x140059d49`
- name: `?DoStateTransferSteps@WorkerTaskMigrationSource@@AEAAJAEA_J@Z`
- size: `3309`
- prototype: `__int64 __fastcall(WorkerTaskMigrationSource *__hidden this, __int64 *)`
- caller_count: `1`
- callee_count: `52`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140059d50`

## callees

- `0x1400364a0`
- `0x14003b720`
- `0x14003d828`
- `0x140053de8`
- `0x140053f10`
- `0x1400544a8`
- `0x14005905c`
- `0x14005bac0`
- `0x14006ab00`
- `0x14006b204`
- `0x14006b2c4`
- `0x14006b390`
- `0x140070ecc`
- `0x140078628`
- `0x14007cee4`
- `0x14007f764`
- `0x14008230c`
- `0x140082334`
- `0x1400823ec`
- `0x140082878`
- `0x14008a328`
- `0x14008bdbc`
- `0x1400ad84c`
- `0x1400bc420`
- `0x1400da040`
- `0x1400dc8cc`
- `0x1400de398`
- `0x1400e22a8`
- `0x14011c570`
- `0x14011ea40`
- `0x14011f6fc`
- `0x140138ce8`
- `0x14013adbc`
- `0x14014b4e4`
- `0x14015ea30`
- `0x14015ee50`
- `0x140160e80`
- `0x14016152c`
- `0x140161720`
- `0x1401cdda0`
- `0x1401d0e14`
- `0x1401db940`
- `0x140209bbc`
- `0x140209c00`
- `0x14020a224`
- `0x14020b4f4`
- `0x14020ccc0`
- `0x140212488`
- `0x140215d6c`
- `0x140215e6c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14005917c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140059b51`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14005917c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140059b51`
- `vid!VidTdxExportPause` at `0x14005948c`
- `vid!VidTdxExportPause` at `0x14005948c`

## string_xrefs

- `0x140059a63`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x140059a88`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x140059ac6`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x140059aeb`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x140059c23`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x140059c67`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x140059c7b`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x140059c8d`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x140059ca1`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x140059cb5`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x140059cc9`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x140059cde`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x140059d22`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x140059d36`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall WorkerTaskMigrationSource::DoStateTransferSteps(WorkerTaskMigrationSource *this, __int64 *a2)
{
  WorkerTaskMigrationSource *v3; // rsi
  const struct _GUID *v4; // rbx
  VirtualMachine **v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 future; // r14
  __int64 v9; // rax
  __int64 v10; // rax
  _BYTE *v11; // r14
  VirtualMachine *v12; // rcx
  __int64 v13; // rax
  VirtualMachine *v14; // r15
  const unsigned __int16 *v15; // rcx
  __int64 v16; // rax
  void *v17; // rdx
  wil::details ***v18; // rcx
  wil::details *v19; // rcx
  _DWORD *v20; // r13
  VirtualMachine *v21; // rcx
  int v22; // eax
  SavedStateRepository **v23; // r15
  int v24; // eax
  int v25; // eax
  int v26; // eax
  const char *v27; // r9
  WorkerTaskMigrationSource *v28; // r15
  __int64 v29; // rax
  int v30; // eax
  __int64 v31; // rax
  __int64 v32; // rax
  VirtualMachine *v33; // rbx
  __int64 v34; // rcx
  unsigned int v35; // edx
  int v36; // eax
  const char *v37; // r9
  int v38; // r15d
  __int64 *v39; // r12
  int v40; // eax
  int v41; // ebx
  int v42; // eax
  int v43; // ebx
  const char *v45; // r9
  unsigned int v46; // eax
  unsigned int v47; // eax
  __int64 v48; // rax
  __int64 v49; // rax
  int v50; // [rsp+20h] [rbp-358h]
  int v51; // [rsp+30h] [rbp-348h] BYREF
  int v52; // [rsp+34h] [rbp-344h] BYREF
  __int64 VmName; // [rsp+38h] [rbp-340h] BYREF
  __int64 v54[2]; // [rsp+40h] [rbp-338h] BYREF
  __int64 v55[2]; // [rsp+50h] [rbp-328h] BYREF
  char *v56[2]; // [rsp+60h] [rbp-318h] BYREF
  WorkerTaskMigrationSource *v57; // [rsp+70h] [rbp-308h]
  WorkerTaskMigrationSource *v58; // [rsp+78h] [rbp-300h]
  VirtualMachine **v59; // [rsp+80h] [rbp-2F8h] BYREF
  __int64 v60; // [rsp+88h] [rbp-2F0h] BYREF
  __int64 (__fastcall *v61)(WorkerAsyncTaskBase *); // [rsp+90h] [rbp-2E8h] BYREF
  __int64 v62; // [rsp+98h] [rbp-2E0h]
  WorkerTaskMigrationSource *v63; // [rsp+A8h] [rbp-2D0h]
  __int64 *v64; // [rsp+B0h] [rbp-2C8h]
  __int64 *v65; // [rsp+B8h] [rbp-2C0h]
  ULONGLONG TickCount64; // [rsp+C0h] [rbp-2B8h]
  __m128i si128; // [rsp+D0h] [rbp-2A8h] BYREF
  _OWORD v68[3]; // [rsp+E0h] [rbp-298h] BYREF
  __int64 v69; // [rsp+110h] [rbp-268h]
  int v70; // [rsp+118h] [rbp-260h]
  struct _GUID v71; // [rsp+120h] [rbp-258h] BYREF
  _BYTE v72[24]; // [rsp+130h] [rbp-248h] BYREF
  char v73; // [rsp+148h] [rbp-230h]
  _BYTE v74[24]; // [rsp+150h] [rbp-228h] BYREF
  char v75; // [rsp+168h] [rbp-210h]
  __int128 v76; // [rsp+170h] [rbp-208h] BYREF
  __int64 v77; // [rsp+180h] [rbp-1F8h]
  _BYTE v78[12]; // [rsp+190h] [rbp-1E8h] BYREF
  int v79; // [rsp+19Ch] [rbp-1DCh]
  __int64 v80; // [rsp+1A8h] [rbp-1D0h]
  __int64 v81; // [rsp+1B0h] [rbp-1C8h]
  char v82[72]; // [rsp+1B8h] [rbp-1C0h] BYREF
  _BYTE v83[24]; // [rsp+200h] [rbp-178h] BYREF
  __int64 v84; // [rsp+218h] [rbp-160h]
  __int64 v85; // [rsp+220h] [rbp-158h]
  char v86[72]; // [rsp+228h] [rbp-150h] BYREF
  _BYTE v87[96]; // [rsp+270h] [rbp-108h] BYREF
  char v88[40]; // [rsp+2D0h] [rbp-A8h] BYREF
  char v89[72]; // [rsp+2F8h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+378h] [rbp+0h]

  v64 = a2;
  v3 = this;
  v58 = this;
  v57 = this;
  v65 = a2;
  v52 = 0;
  v71 = 0;
  v4 = (const struct _GUID *)((char *)this + 412);
  Vml::VmPerfTraceOperation::VmPerfTraceOperation(
    (Vml::VmPerfTraceOperation *)v83,
    (struct Vml::VmPerfTraceComponent *)&g_MigrationPerfTrace,
    (const struct _GUID *)((char *)this + 412),
    &v71);
  v71 = 0;
  Vml::VmPerfTraceOperation::VmPerfTraceOperation(
    (Vml::VmPerfTraceOperation *)v78,
    (struct Vml::VmPerfTraceComponent *)&g_MigrationPerfTrace,
    v4,
    &v71);
  v71 = 0;
  Vml::VmPerfTraceOperation::VmPerfTraceOperation(
    (Vml::VmPerfTraceOperation *)v88,
    (struct Vml::VmPerfTraceComponent *)&g_MigrationPerfTrace,
    v4,
    &v71);
  v84 = *a2;
  v60 = (__int64)v3 + 16;
  v5 = (VirtualMachine **)((char *)v3 + 16);
  v59 = (VirtualMachine **)((char *)v3 + 16);
  VmName = (__int64)VirtualMachine::GetVmName((VirtualMachine *)(*((_QWORD *)v3 + 2) + 16LL));
  Vml::VmPerfTraceOperation::BeginOperation<unsigned short const *>(
    (Vml::VmPerfTraceOperation *)v83,
    &VMWP_PERF_MIGRATION_SOURCE_MOVE_START);
  TickCount64 = GetTickCount64();
  *(_QWORD *)&v71.Data1 = 0;
  *(_QWORD *)v71.Data4 = 0;
  std::promise<long>::promise<long>(v72);
  v73 = 1;
  std::promise<long>::promise<long>(v74);
  try
  {
    v75 = 1;
    v76 = 0;
    v77 = 0;
    v61 = WorkerTaskMigrationSource::SendVmState;
    v62 = 0;
    v63 = v3;
    ____0V___Binder_U_Unforced_std__P8WorkerTaskMigrationSource__EAAJV__future_J_2_0__EPEAV3_AEBU___Ph__00_2_AEBU___Ph__01_2__std___0A____packaged_task___A6AJV__future_J_std__0_Z_std__QEAA___QEAV___Binder_U_Unforced_std__P8WorkerTaskMigrationSource__EAAJV__future_J_2_0__EPEAV3_AEBU___Ph__00_2_AEBU___Ph__01_2__1__Z(
      &v76,
      &v61);
    v6 = *(_QWORD *)std::_Promise<long>::_Get_state_for_future(&v76);
    LOBYTE(v62) = 1;
    if ( v6 )
      _InterlockedAdd((volatile signed __int32 *)(v6 + 8), 1u);
    v61 = 0;
    *(_QWORD *)&v71.Data1 = v6;
    v71.Data4[0] = 1;
    std::_State_manager<int>::~_State_manager<int>(&v61);
    v7 = std::optional<EndpointTransferRuntimeStats::RuntimeStatistics>::value(v74);
    future = std::packaged_task<long (void)>::get_future(v7, v56);
    v9 = std::optional<EndpointTransferRuntimeStats::RuntimeStatistics>::value(v72);
    v10 = std::packaged_task<long (void)>::get_future(v9, v54);
    std::thread::_Start<std::packaged_task<long (std::future<long>,std::future<long>)>,std::future<long>,std::future<long>>(
      &v61,
      &v76,
      v10,
      future);
    std::thread::detach((std::thread *)&v61);
    std::thread::~thread((std::thread *)&v61);
    std::_State_manager<int>::~_State_manager<int>(v54);
    std::_State_manager<int>::~_State_manager<int>(v56);
    VmName = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)*v5 + 16));
    Vml::VmPerfTraceOperation::BeginOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v78,
      &VMWP_PERF_MIGRATION_SOURCE_PAUSE_VM_START);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    si128.m128i_i32[2] = 0;
    si128.m128i_i8[12] = 0;
    memset_0(v68, 0, 0x40u);
    memset(v68, 0, sizeof(v68));
    v69 = 0;
    v70 = 0;
    std::variant<std::monostate,Compute::Responses::System::WorkerCoreNotification,Schema::Responses::System::OperationSystemMigrationNotificationInfo>::variant<std::monostate,Compute::Responses::System::WorkerCoreNotification,Schema::Responses::System::OperationSystemMigrationNotificationInfo>(
      v87,
      &si128);
    v61 = (__int64 (__fastcall *)(WorkerAsyncTaskBase *))((char *)v3 + 1016);
    (*(void (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)v3 + 127) + 128LL))(*((_QWORD *)v3 + 127), v87);
    if ( !(unsigned int)VirtualMachine::SetState(*v5, 9, 26) )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16866) )
        VmlDebugTraceEx(16866, &off_1402E4568);
      v45 = (const char *)(unsigned int)wil::verify_hresult<long>(2147549183LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x605,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        v45,
        v50);
    }
    if ( *((_DWORD *)v3 + 248) == 2 )
    {
      v12 = *v5;
      VmName = (__int64)*v5 + 1152;
      v55[0] = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)v12 + 16));
      VmEventWrite<unsigned short const *,unsigned short const *>(
        &MSVM_WORKER_MIGRATION_ENTER_BLACKOUT,
        1u,
        (__int64)&VmName);
      *((struct _FILETIME *)v3 + 156) = CurrentFileTime();
      v11 = (char *)v3 + 1028;
      VirtualMachine::StopVm(*v5, *((_DWORD *)v3 + 257) & 0x20 | 0x11u, 18);
      if ( *((_BYTE *)v3 + 409) )
      {
        v13 = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)*v5 + 128) + 24LL))(*((_QWORD *)*v5 + 128) + 24LL);
        if ( !(unsigned int)VidTdxExportPause(v13) )
        {
          if ( (unsigned int)VmlIsDebugTraceEnabled(16866) )
            VmlDebugTraceEx(16866, &off_1402E41F0);
          v46 = wil::verify_hresult<long>(2147549183LL);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x622,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
            (const char *)v46,
            v50);
        }
        v14 = *v5;
        v15 = VirtualMachine::GetVmName((VirtualMachine *)((char *)*v5 + 16));
        v16 = -1;
        do
          ++v16;
        while ( v15[v16] );
        v54[0] = (__int64)v15;
        v54[1] = v16;
        v56[0] = "ExportPause";
        v56[1] = (char *)11;
        VmWorkerTrace::CvmLmProtocolEvent(v56, (char *)v14 + 1136, v54);
      }
      if ( (unsigned __int8)_is_valid___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEBA_NXZ((char *)v3 + 1328) )
      {
        if ( *v18 )
          v19 = **v18;
        else
          v19 = 0;
        wil::details::SetEvent(v19, v17);
      }
    }
    else
    {
      v11 = (char *)v3 + 1028;
    }
    VmName = (__int64)v11;
    v20 = (_DWORD *)((char *)v3 + 996);
    v54[0] = (__int64)v3 + 996;
    *((_DWORD *)v3 + 249) = 5;
    *(_BYTE *)(*((_QWORD *)v3 + 58) + 992LL) = 1;
    v55[0] = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)*v5 + 16));
    Vml::VmPerfTraceOperation::EndOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v78,
      &VMWP_PERF_MIGRATION_SOURCE_PAUSE_VM_STOP,
      (__int64)v55);
    if ( (*v11 & 0x20) != 0 )
    {
      v21 = *v5;
      v55[0] = (__int64)*v5 + 1152;
      v56[0] = (char *)VirtualMachine::GetVmName((VirtualMachine *)((char *)v21 + 16));
      VmEventWrite<unsigned short const *,unsigned short const *>(
        &MSVM_WORKER_MIGRATION_SOURCE_PAUSE_VM_STOP,
        1u,
        (__int64)v55);
    }
    v22 = WorkerTaskMigrationSource::CheckCancel((WorkerTaskMigrationSource *)((char *)v3 + 400));
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x64D,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)(unsigned int)v22,
        v50);
    *(_OWORD *)v56 = 0;
    v23 = (SavedStateRepository **)((char *)v3 + 448);
    v55[0] = (__int64)v3 + 448;
    VmRepositoryAutoLock::VmRepositoryAutoLock(v56, *((_QWORD *)v3 + 56), 1);
    if ( SLODWORD(v56[1]) < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x655,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)LODWORD(v56[1]),
        v50);
    v24 = SavedStateRepository::WriteInteger(*v23, L"/migration/blackout_start_timestamp", *((_QWORD *)v3 + 156));
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x659,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)(unsigned int)v24,
        v50);
    v25 = SavedStateRepository::WriteInteger(*v23, L"/migration/clock_drift", *((_QWORD *)v3 + 157));
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x65D,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)(unsigned int)v25,
        v50);
    v26 = SavedStateRepository::Commit(*v23);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x65F,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)(unsigned int)v26,
        v50);
    VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v56);
    v80 = 0;
    v81 = 0;
    v79 = 1;
    v56[0] = (char *)VirtualMachine::GetVmName((VirtualMachine *)((char *)*v5 + 16));
    Vml::VmPerfTraceOperation::BeginOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v78,
      &VMWP_PERF_MIGRATION_SOURCE_SAVE_VSM_START);
    (*(void (__fastcall **)(_QWORD, SavedStateRepository *))(**((_QWORD **)*v5 + 128) + 256LL))(
      *((_QWORD *)*v5 + 128),
      *v23);
    try
    {
      (*(void (__fastcall **)(_QWORD, SavedStateRepository *))(**((_QWORD **)*v5 + 124) + 416LL))(
        *((_QWORD *)*v5 + 124),
        *v23);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x671,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        v27);
      v52 = 0;
      v5 = v59;
      v3 = v58;
      v64 = v65;
      v11 = (_BYTE *)VmName;
      v20 = (_DWORD *)v54[0];
      v23 = (SavedStateRepository **)v55[0];
    }
    (*(void (__fastcall **)(_QWORD, SavedStateRepository *))(**((_QWORD **)*v5 + 124) + 400LL))(
      *((_QWORD *)*v5 + 124),
      *v23);
    v28 = v57;
    if ( (*v11 & 1) != 0 && (*v11 & 0x10) == 0 && *((_BYTE *)v57 + 937) )
      WorkerTaskMigrationSource::SetupSkippedForProtectionBitmapsForChecksum(v3);
    v54[0] = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)*v5 + 16));
    Vml::VmPerfTraceOperation::EndOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v78,
      &VMWP_PERF_MIGRATION_SOURCE_SAVE_VSM_STOP,
      (__int64)v54);
    if ( !*((_BYTE *)v28 + 938) )
    {
      v29 = std::optional<EndpointTransferRuntimeStats::RuntimeStatistics>::value(v72);
      v51 = 0;
      std::promise<long>::set_value(v29, &v51);
      std::_Optional_destruct_base<std::promise<long>,0>::reset(v72);
    }
    v80 = 0;
    v81 = 0;
    v79 = 1;
    v54[0] = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)*v5 + 16));
    Vml::VmPerfTraceOperation::BeginOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v78,
      &VMWP_PERF_MIGRATION_SOURCE_MOVE_SAVE_STATE_START);
    v30 = WorkerTaskMigrationSource::SaveVmState(v3);
    if ( v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x68F,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)(unsigned int)v30,
        v50);
    v54[0] = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)*v5 + 16));
    Vml::VmPerfTraceOperation::EndOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v78,
      &VMWP_PERF_MIGRATION_SOURCE_MOVE_SAVE_STATE_STOP,
      (__int64)v54);
    v31 = std::optional<EndpointTransferRuntimeStats::RuntimeStatistics>::value(v74);
    v51 = 0;
    std::promise<long>::set_value(v31, &v51);
    std::_Optional_destruct_base<std::promise<long>,0>::reset(v74);
    v80 = 0;
    v81 = 0;
    v79 = 1;
    v54[0] = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)*v5 + 16));
    Vml::VmPerfTraceOperation::BeginOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v78,
      &VMWP_PERF_MIGRATION_SOURCE_MOVE_POWER_OFF_START);
    WorkerTaskMigrationSource::PowerOffDevices(v3);
    v54[0] = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)*v5 + 16));
    Vml::VmPerfTraceOperation::EndOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v78,
      &VMWP_PERF_MIGRATION_SOURCE_MOVE_POWER_OFF_STOP,
      (__int64)v54);
    if ( *((_BYTE *)v28 + 938) )
    {
      v32 = std::optional<EndpointTransferRuntimeStats::RuntimeStatistics>::value(v72);
      v51 = 0;
      std::promise<long>::set_value(v32, &v51);
      std::_Optional_destruct_base<std::promise<long>,0>::reset(v72);
    }
    VirtualMachine::UnloadConfiguration(*v5);
    *v20 = 9;
    if ( (*v11 & 0x20) != 0 )
    {
      if ( !(unsigned int)VirtualMachine::SetState(*v5, 7, 24) )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(16866) )
          VmlDebugTraceEx(16866, &off_1402E4538);
        v47 = wil::verify_hresult<long>(2147549183LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6BE,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
          (const char *)v47,
          v50);
      }
      v33 = *v5;
      v54[0] = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)v33 + 16));
      v59 = (VirtualMachine **)((char *)v33 + 1152);
      Vml::VmPerfTraceComponent::LogEvent<unsigned short const *,unsigned short const *>(
        v34,
        VMWP_PERF_MIGRATION_SOURCE_MIGRATING_SUSPENDED,
        &v59,
        v54);
    }
    (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v61 + 24LL))(*(_QWORD *)v61, 0);
    *v20 = 10;
    if ( (*v11 & 0x20) != 0 )
    {
      v36 = MigrationManager::WaitForInMigratingSuspendedState(*((MigrationManager **)v3 + 54), v35);
      if ( v36 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6CF,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
          (const char *)(unsigned int)v36,
          v50);
      v51 = 0;
      WorkerAsyncTaskBase::UpdateStatusProgress(v3, 0x64u, &v51);
    }
    *v20 = 11;
    std::_Variant_destroy_layer_<std::monostate,Compute::Responses::System::WorkerCoreNotification,Schema::Responses::System::OperationSystemMigrationNotificationInfo>::~_Variant_destroy_layer_<std::monostate,Compute::Responses::System::WorkerCoreNotification,Schema::Responses::System::OperationSystemMigrationNotificationInfo>(v87);
    Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::~DelayedBase<void,Marshal::Details::DelayedJsonTraits>(v68);
    std::packaged_task<long (std::future<long>,std::future<long>)>::~packaged_task<long (std::future<long>,std::future<long>)>(&v76);
    v38 = v52;
    v39 = v64;
  }
  catch ( ... )
  {
    v51 = wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0x6DC,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
            v37);
    if ( v73 )
    {
      v48 = std::optional<EndpointTransferRuntimeStats::RuntimeStatistics>::value(v72);
      v52 = -2147467260;
      std::promise<long>::set_value(v48, &v52);
      std::_Optional_destruct_base<std::promise<long>,0>::reset(v72);
    }
    if ( v75 )
    {
      v49 = std::optional<EndpointTransferRuntimeStats::RuntimeStatistics>::value(v74);
      v52 = -2147467260;
      std::promise<long>::set_value(v49, &v52);
      std::_Optional_destruct_base<std::promise<long>,0>::reset(v74);
    }
    VmMigrationConnection::Cancel(*((VmMigrationConnection **)v58 + 55), 1);
    v3 = v58;
    v11 = (char *)v58 + 1028;
    v38 = v51;
    v39 = v65;
  }
  if ( (unsigned __int8)std::_State_manager<long>::valid(&v71) )
  {
    v40 = std::future<long>::get(&v71);
    v41 = v40;
    if ( v40 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6F5,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)(unsigned int)v40,
        v50);
    if ( v38 >= 0 && v41 < 0 )
      v38 = wil::details::in1diag3::Log_Hr(
              retaddr,
              (void *)0x6F9,
              (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
              (const char *)(unsigned int)v41,
              v50);
    if ( (*v11 & 0x20) != 0 )
    {
      v42 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 127) + 40LL))(*((_QWORD *)v3 + 127));
      v43 = v42;
      if ( v42 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x6FE,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
          (const char *)(unsigned int)v42,
          v50);
      if ( v38 >= 0 && v43 < 0 )
        v38 = wil::details::in1diag3::Log_Hr(
                retaddr,
                (void *)0x702,
                (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
                (const char *)(unsigned int)v43,
                v50);
    }
  }
  *(_BYTE *)(*((_QWORD *)v3 + 58) + 992LL) = 0;
  v60 = (__int64)VirtualMachine::GetVmName((VirtualMachine *)(*(_QWORD *)v60 + 16LL));
  Vml::VmPerfTraceOperation::EndOperation<unsigned short const *>(
    (Vml::VmPerfTraceOperation *)v83,
    &VMWP_PERF_MIGRATION_SOURCE_MOVE_STOP,
    (__int64)&v60);
  *v39 = v85;
  *((_QWORD *)v3 + 133) = GetTickCount64() - TickCount64;
  std::_Optional_destruct_base<std::promise<long>,0>::~_Optional_destruct_base<std::promise<long>,0>(v74);
  std::_Optional_destruct_base<std::promise<long>,0>::~_Optional_destruct_base<std::promise<long>,0>(v72);
  std::_State_manager<int>::~_State_manager<int>(&v71);
  std::wstring::_Tidy_deallocate(v89);
  std::wstring::_Tidy_deallocate(v82);
  std::wstring::_Tidy_deallocate(v86);
  return (unsigned int)v38;
}

```

## disassembly

```asm
0x14005905c  mov     r11, rsp
0x14005905f  mov     [r11+18h], rbx
0x140059063  mov     [r11+20h], rsi
0x140059067  push    rdi
0x140059068  push    r12
0x14005906a  push    r13
0x14005906c  push    r14
0x14005906e  push    r15
0x140059070  sub     rsp, 350h
0x140059077  mov     rax, cs:__security_cookie
0x14005907e  xor     rax, rsp
0x140059081  mov     [rsp+378h+var_38], rax
0x140059089  mov     r14, rdx
0x14005908c  mov     [rsp+378h+var_2C8], rdx
0x140059094  mov     rsi, rcx
0x140059097  mov     [rsp+378h+var_300], rcx
0x14005909c  mov     [rsp+378h+var_308], rcx
0x1400590a1  mov     [rsp+378h+var_2C0], rdx
0x1400590a9  xor     edi, edi
0x1400590ab  mov     [rsp+378h+var_344], edi
0x1400590af  xorps   xmm0, xmm0
0x1400590b2  movups  xmmword ptr [rsp+378h+var_258.Data1], xmm0
0x1400590ba  lea     rbx, [rcx+19Ch]
0x1400590c1  lea     r9, [r11-258h]; struct _GUID *
0x1400590c8  mov     r8, rbx; struct _GUID *
0x1400590cb  lea     r15, ?g_MigrationPerfTrace@@3VVmPerfTraceComponent@Vml@@A; Vml::VmPerfTraceComponent g_MigrationPerfTrace
0x1400590d2  mov     rdx, r15; struct Vml::VmPerfTraceComponent *
0x1400590d5  lea     rcx, [r11-178h]; this
0x1400590dc  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x1400590e1  nop
0x1400590e2  xorps   xmm0, xmm0
0x1400590e5  movups  xmmword ptr [rsp+378h+var_258.Data1], xmm0
0x1400590ed  lea     r9, [rsp+378h+var_258]; struct _GUID *
0x1400590f5  mov     r8, rbx; struct _GUID *
0x1400590f8  mov     rdx, r15; struct Vml::VmPerfTraceComponent *
0x1400590fb  lea     rcx, [rsp+378h+var_1E8]; this
0x140059103  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x140059108  nop
0x140059109  xorps   xmm0, xmm0
0x14005910c  movups  xmmword ptr [rsp+378h+var_258.Data1], xmm0
0x140059114  lea     r9, [rsp+378h+var_258]; struct _GUID *
0x14005911c  mov     r8, rbx; struct _GUID *
0x14005911f  mov     rdx, r15; struct Vml::VmPerfTraceComponent *
0x140059122  lea     rcx, [rsp+378h+var_A8]; this
0x14005912a  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x14005912f  nop
0x140059130  mov     rax, [r14]
0x140059133  mov     [rsp+378h+var_160], rax
0x14005913b  lea     rax, [rsi+10h]
0x14005913f  mov     [rsp+378h+var_2F0], rax
0x140059147  mov     rbx, rax
0x14005914a  mov     [rsp+378h+var_2F8], rax
0x140059152  mov     rcx, [rax]
0x140059155  add     rcx, 10h; this
0x140059159  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x14005915e  mov     [rsp+378h+var_340], rax
0x140059163  lea     r8, [rsp+378h+var_340]
0x140059168  lea     rdx, VMWP_PERF_MIGRATION_SOURCE_MOVE_START; EventDescriptor
0x14005916f  lea     rcx, [rsp+378h+var_178]; this
0x140059177  call    ??$BeginOperation@PEBG@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@$$QEAPEBG@Z; Vml::VmPerfTraceOperation::BeginOperation<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const * &&)
0x14005917c  call    cs:__imp_GetTickCount64
0x140059183  nop     dword ptr [rax+rax+00h]
0x140059188  mov     [rsp+378h+var_2B8], rax
0x140059190  xorps   xmm0, xmm0
0x140059193  movups  xmmword ptr [rsp+378h+var_258.Data1], xmm0
0x14005919b  mov     qword ptr [rsp+378h+var_258.Data1], rdi
0x1400591a3  mov     [rsp+378h+var_258.Data4], dil
0x1400591ab  lea     rcx, [rsp+378h+var_248]
0x1400591b3  call    ??0?$promise@J@std@@QEAA@XZ; std::promise<long>::promise<long>(void)
0x1400591b8  lea     r12d, [rdi+1]
0x1400591bc  mov     [rsp+378h+var_230], r12b
0x1400591c4  lea     rcx, [rsp+378h+var_228]
0x1400591cc  call    ??0?$promise@J@std@@QEAA@XZ; std::promise<long>::promise<long>(void)
0x1400591d1  mov     [rsp+378h+var_210], r12b
0x1400591d9  xorps   xmm0, xmm0
0x1400591dc  xor     eax, eax
0x1400591de  movups  [rsp+378h+var_208], xmm0
0x1400591e6  mov     [rsp+378h+var_1F8], rax
0x1400591ee  lea     rax, ?SendVmState@WorkerTaskMigrationSource@@AEAAJV?$future@J@std@@0@Z; WorkerTaskMigrationSource::SendVmState(std::future<long>,std::future<long>)
0x1400591f5  mov     [rsp+378h+var_2E8], rax
0x1400591fd  mov     [rsp+378h+var_2E0], rdi
0x140059205  mov     [rsp+378h+var_2D0], rsi
0x14005920d  lea     rdx, [rsp+378h+var_2E8]
0x140059215  lea     rcx, [rsp+378h+var_208]
0x14005921d  call    ??$?0V?$_Binder@U_Unforced@std@@P8WorkerTaskMigrationSource@@EAAJV?$future@J@2@0@_EPEAV3@AEBU?$_Ph@$00@2@AEBU?$_Ph@$01@2@@std@@$0A@@?$packaged_task@$$A6AJV?$future@J@std@@0@Z@std@@QEAA@$$QEAV?$_Binder@U_Unforced@std@@P8WorkerTaskMigrationSource@@EAAJV?$future@J@2@0@_EPEAV3@AEBU?$_Ph@$00@2@AEBU?$_Ph@$01@2@@1@@Z
0x140059222  nop
0x140059223  lea     rcx, [rsp+378h+var_208]
0x14005922b  call    ?_Get_state_for_future@?$_Promise@J@std@@QEAAAEAV?$_State_manager@J@2@XZ; std::_Promise<long>::_Get_state_for_future(void)
0x140059230  mov     rax, [rax]
0x140059233  mov     byte ptr [rsp+378h+var_2E0], r12b
0x14005923b  test    rax, rax
0x14005923e  jz      short loc_140059245
0x140059240  lock add [rax+8], r12d
0x140059245  mov     [rsp+378h+var_2E8], rdi
0x14005924d  mov     qword ptr [rsp+378h+var_258.Data1], rax
0x140059255  mov     [rsp+378h+var_258.Data4], r12b
0x14005925d  lea     rcx, [rsp+378h+var_2E8]
0x140059265  call    ??1?$_State_manager@H@std@@QEAA@XZ; std::_State_manager<int>::~_State_manager<int>(void)
0x14005926a  lea     rcx, [rsp+378h+var_228]
0x140059272  call    ?value@?$optional@URuntimeStatistics@EndpointTransferRuntimeStats@@@std@@QEGAAAEAURuntimeStatistics@EndpointTransferRuntimeStats@@XZ; std::optional<EndpointTransferRuntimeStats::RuntimeStatistics>::value(void)
0x140059277  lea     rdx, [rsp+378h+var_318]
0x14005927c  mov     rcx, rax
0x14005927f  call    ?get_future@?$packaged_task@$$A6AJXZ@std@@QEAA?AV?$future@J@2@XZ; std::packaged_task<long (void)>::get_future(void)
0x140059284  mov     r14, rax
0x140059287  lea     rcx, [rsp+378h+var_248]
0x14005928f  call    ?value@?$optional@URuntimeStatistics@EndpointTransferRuntimeStats@@@std@@QEGAAAEAURuntimeStatistics@EndpointTransferRuntimeStats@@XZ; std::optional<EndpointTransferRuntimeStats::RuntimeStatistics>::value(void)
0x140059294  lea     rdx, [rsp+378h+var_338]
0x140059299  mov     rcx, rax
0x14005929c  call    ?get_future@?$packaged_task@$$A6AJXZ@std@@QEAA?AV?$future@J@2@XZ; std::packaged_task<long (void)>::get_future(void)
0x1400592a1  nop
0x1400592a2  mov     r9, r14
0x1400592a5  mov     r8, rax
0x1400592a8  lea     rdx, [rsp+378h+var_208]
0x1400592b0  lea     rcx, [rsp+378h+var_2E8]
0x1400592b8  call    ??$_Start@V?$packaged_task@$$A6AJV?$future@J@std@@0@Z@std@@V?$future@J@2@V32@@thread@std@@AEAAX$$QEAV?$packaged_task@$$A6AJV?$future@J@std@@0@Z@1@$$QEAV?$future@J@1@1@Z; std::thread::_Start<std::packaged_task<long (std::future<long>,std::future<long>)>,std::future<long>,std::future<long>>(std::packaged_task<long (std::future<long>,std::future<long>)> &&,std::future<long> &&,std::future<long> &&)
0x1400592bd  nop
0x1400592be  lea     rcx, [rsp+378h+var_2E8]; this
0x1400592c6  call    ?detach@thread@std@@QEAAXXZ; std::thread::detach(void)
0x1400592cb  nop
0x1400592cc  lea     rcx, [rsp+378h+var_2E8]; this
0x1400592d4  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x1400592d9  nop
0x1400592da  lea     rcx, [rsp+378h+var_338]
0x1400592df  call    ??1?$_State_manager@H@std@@QEAA@XZ; std::_State_manager<int>::~_State_manager<int>(void)
0x1400592e4  nop
0x1400592e5  lea     rcx, [rsp+378h+var_318]
0x1400592ea  call    ??1?$_State_manager@H@std@@QEAA@XZ; std::_State_manager<int>::~_State_manager<int>(void)
0x1400592ef  mov     rcx, [rbx]
0x1400592f2  add     rcx, 10h; this
0x1400592f6  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400592fb  mov     [rsp+378h+var_340], rax
0x140059300  lea     r8, [rsp+378h+var_340]
0x140059305  lea     rdx, VMWP_PERF_MIGRATION_SOURCE_PAUSE_VM_START; EventDescriptor
0x14005930c  lea     rcx, [rsp+378h+var_1E8]; this
0x140059314  call    ??$BeginOperation@PEBG@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@$$QEAPEBG@Z; Vml::VmPerfTraceOperation::BeginOperation<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const * &&)
0x140059319  movdqa  xmm0, cs:__xmm@00000000000000000000000200000000
0x140059321  movdqa  [rsp+378h+var_2A8], xmm0
0x14005932a  mov     dword ptr [rsp+378h+var_2A8+8], edi
0x140059331  mov     byte ptr [rsp+378h+var_2A8+0Ch], dil
0x140059339  xor     edx, edx; Val
0x14005933b  lea     r8d, [rdx+40h]; Size
0x14005933f  lea     rcx, [rsp+378h+var_298]; void *
0x140059347  call    memset_0
0x14005934c  xorps   xmm0, xmm0
0x14005934f  movdqa  [rsp+378h+var_298], xmm0
0x140059358  xorps   xmm1, xmm1
0x14005935b  movdqa  [rsp+378h+var_288], xmm1
0x140059364  movdqa  [rsp+378h+var_278], xmm0
0x14005936d  mov     [rsp+378h+var_268], rdi
0x140059375  mov     [rsp+378h+var_260], edi
0x14005937c  lea     rdx, [rsp+378h+var_2A8]
0x140059384  lea     rcx, [rsp+378h+var_108]
0x14005938c  call    ??$?0UOperationSystemMigrationNotificationInfo@System@Responses@Schema@@$0A@$0A@@?$variant@Umonostate@std@@UWorkerCoreNotification@System@Responses@Compute@@UOperationSystemMigrationNotificationInfo@45Schema@@@std@@QEAA@$$QEAUOperationSystemMigrationNotificationInfo@System@Responses@Schema@@@Z; std::variant<std::monostate,Compute::Responses::System::WorkerCoreNotification,Schema::Responses::System::OperationSystemMigrationNotificationInfo>::variant<std::monostate,Compute::Responses::System::WorkerCoreNotification,Schema::Responses::System::OperationSystemMigrationNotificationInfo>(Schema::Responses::System::OperationSystemMigrationNotificationInfo &&)
0x140059391  nop
0x140059392  lea     rax, [rsi+3F8h]
0x140059399  mov     [rsp+378h+var_2E8], rax
0x1400593a1  mov     rcx, [rax]
0x1400593a4  mov     rax, [rcx]
0x1400593a7  lea     rdx, [rsp+378h+var_108]
0x1400593af  mov     rax, [rax+80h]
0x1400593b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400593bb  mov     edx, 9
0x1400593c0  lea     r8d, [rdx+11h]
0x1400593c4  mov     rcx, [rbx]
0x1400593c7  call    ?SetState@VirtualMachine@@QEAAHW4_VM_STATE@@W4_VM_STATE_REASON_CODE@@@Z; VirtualMachine::SetState(_VM_STATE,_VM_STATE_REASON_CODE)
0x1400593cc  test    eax, eax
0x1400593ce  jz      loc_140059BF0
0x1400593d4  cmp     dword ptr [rsi+3E0h], 2
0x1400593db  jz      short loc_1400593E9
0x1400593dd  lea     r14, [rsi+404h]
0x1400593e4  jmp     loc_140059516
0x1400593e9  mov     rcx, [rbx]
0x1400593ec  lea     rax, [rcx+480h]
0x1400593f3  mov     [rsp+378h+var_340], rax
0x1400593f8  add     rcx, 10h; this
0x1400593fc  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x140059401  mov     [rsp+378h+var_328], rax
0x140059406  lea     rax, [rsp+378h+var_340]
0x14005940b  mov     qword ptr [rsp+378h+var_358], rax; int
0x140059410  lea     r9, [rsp+378h+var_328]
0x140059415  mov     edx, r12d; unsigned int
0x140059418  lea     rcx, MSVM_WORKER_MIGRATION_ENTER_BLACKOUT; EventDescriptor
0x14005941f  call    ??$VmEventWrite@PEBGPEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@$$QEAPEBG2@Z; VmEventWrite<ushort const *,ushort const *>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const * &&,ushort const * &&)
0x140059424  call    ?CurrentFileTime@@YA?AU_FILETIME@@XZ; CurrentFileTime(void)
0x140059429  mov     rdx, rax
0x14005942c  mov     rcx, 0FFFFFFFF00000000h
0x140059436  and     rdx, rcx
0x140059439  mov     ecx, eax
0x14005943b  add     rdx, rcx
0x14005943e  mov     [rsi+4E0h], rdx
0x140059445  lea     r14, [rsi+404h]
0x14005944c  mov     edx, [r14]
0x14005944f  and     edx, 20h
0x140059452  or      edx, 11h
0x140059455  mov     r8d, 12h
0x14005945b  mov     rcx, [rbx]
0x14005945e  call    ?StopVm@VirtualMachine@@QEAAXIW4__MIDL___MIDL_itf_vmbservices_0000_0011_0003@@@Z; VirtualMachine::StopVm(uint,__MIDL___MIDL_itf_vmbservices_0000_0011_0003)
0x140059463  cmp     [rsi+199h], dil
0x14005946a  jz      loc_1400594F1
0x140059470  mov     rax, [rbx]
0x140059473  mov     rcx, [rax+400h]
0x14005947a  add     rcx, 18h
0x14005947e  mov     rax, [rcx]
0x140059481  mov     rax, [rax]
0x140059484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059489  mov     rcx, rax
0x14005948c  call    cs:__imp_VidTdxExportPause
0x140059493  nop     dword ptr [rax+rax+00h]
0x140059498  test    eax, eax
0x14005949a  jz      loc_140059C34
0x1400594a0  mov     r15, [rbx]
0x1400594a3  lea     rcx, [r15+10h]; this
0x1400594a7  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400594ac  mov     rcx, rax
0x1400594af  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400594b3  inc     rax
0x1400594b6  cmp     [rcx+rax*2], di
0x1400594ba  jnz     short loc_1400594B3
0x1400594bc  mov     [rsp+378h+var_338], rcx
0x1400594c1  mov     [rsp+378h+var_330], rax
0x1400594c6  lea     rax, aExportpause; "ExportPause"
0x1400594cd  mov     [rsp+378h+var_318], rax
0x1400594d2  mov     [rsp+378h+var_318+8], 0Bh
0x1400594db  lea     rdx, [r15+470h]
0x1400594e2  lea     r8, [rsp+378h+var_338]
0x1400594e7  lea     rcx, [rsp+378h+var_318]
0x1400594ec  call    ?CvmLmProtocolEvent@VmWorkerTrace@@SAXV?$basic_string_view@DU?$char_traits@D@std@@@std@@AEBU_GUID@@V?$basic_string_view@GU?$char_traits@G@std@@@3@@Z; VmWorkerTrace::CvmLmProtocolEvent(std::string_view,_GUID const &,std::basic_string_view<ushort>)
0x1400594f1  lea     rcx, [rsi+530h]
0x1400594f8  call    ?is_valid@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEBA_NXZ
0x1400594fd  test    al, al
0x1400594ff  jz      short loc_140059516
0x140059501  mov     rax, [rcx]
0x140059504  test    rax, rax
0x140059507  jz      short loc_14005950E
0x140059509  mov     rcx, [rax]
0x14005950c  jmp     short loc_140059511
0x14005950e  mov     rcx, rdi; this
0x140059511  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x140059516  mov     [rsp+378h+var_340], r14
0x14005951b  lea     r13, [rsi+3E4h]
0x140059522  mov     [rsp+378h+var_338], r13
0x140059527  mov     dword ptr [r13+0], 5
0x14005952f  mov     rax, [rsi+1D0h]
0x140059536  mov     [rax+3E0h], r12b
0x14005953d  mov     rcx, [rbx]
0x140059540  add     rcx, 10h; this
0x140059544  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x140059549  mov     [rsp+378h+var_328], rax
0x14005954e  lea     r8, [rsp+378h+var_328]; __int64
0x140059553  lea     rdx, VMWP_PERF_MIGRATION_SOURCE_PAUSE_VM_STOP; EventDescriptor
0x14005955a  lea     rcx, [rsp+378h+var_1E8]; this
0x140059562  call    ??$EndOperation@PEBG@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@$$QEAPEBG@Z; Vml::VmPerfTraceOperation::EndOperation<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const * &&)
0x140059567  test    byte ptr [r14], 20h
0x14005956b  jz      short loc_1400595A8
0x14005956d  mov     rcx, [rbx]
0x140059570  lea     rax, [rcx+480h]
0x140059577  mov     [rsp+378h+var_328], rax
0x14005957c  add     rcx, 10h; this
0x140059580  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x140059585  mov     [rsp+378h+var_318], rax
0x14005958a  lea     rax, [rsp+378h+var_328]
0x14005958f  mov     qword ptr [rsp+378h+var_358], rax; int
0x140059594  lea     r9, [rsp+378h+var_318]
0x140059599  mov     edx, r12d; unsigned int
0x14005959c  lea     rcx, MSVM_WORKER_MIGRATION_SOURCE_PAUSE_VM_STOP; EventDescriptor
0x1400595a3  call    ??$VmEventWrite@PEBGPEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@$$QEAPEBG2@Z; VmEventWrite<ushort const *,ushort const *>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const * &&,ushort const * &&)
0x1400595a8  lea     rcx, [rsi+190h]; this
0x1400595af  call    ?CheckCancel@WorkerTaskMigrationSource@@UEAAJXZ; WorkerTaskMigrationSource::CheckCancel(void)
0x1400595b4  mov     rcx, [rsp+378h]; this
0x1400595bc  test    eax, eax
0x1400595be  js      loc_140059C78
0x1400595c4  xorps   xmm0, xmm0
0x1400595c7  movups  xmmword ptr [rsp+378h+var_318], xmm0
0x1400595cc  lea     r15, [rsi+1C0h]
0x1400595d3  mov     [rsp+378h+var_328], r15
0x1400595d8  mov     r8d, r12d
0x1400595db  mov     rdx, [r15]
0x1400595de  lea     rcx, [rsp+378h+var_318]
0x1400595e3  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x1400595e8  nop
0x1400595e9  mov     r9d, dword ptr [rsp+378h+var_318+8]; char *
0x1400595ee  mov     rcx, [rsp+378h]; this
0x1400595f6  test    r9d, r9d
0x1400595f9  js      loc_140059C8D
0x1400595ff  mov     r8, [rsi+4E0h]; __int64
0x140059606  lea     rdx, ?VM_MIGRATION_BLACKOUT_START_TIMESTAMP_XPATH@@3QBGB; "/migration/blackout_start_timestamp"
0x14005960d  mov     rcx, [r15]; this
0x140059610  call    ?WriteInteger@SavedStateRepository@@UEAAJPEBG_J@Z; SavedStateRepository::WriteInteger(ushort const *,__int64)
0x140059615  mov     rcx, [rsp+378h]; this
0x14005961d  test    eax, eax
0x14005961f  js      loc_140059C9E
0x140059625  mov     r8, [rsi+4E8h]; __int64
0x14005962c  lea     rdx, ?VM_MIGRATION_CLOCK_DRIFT_XPATH@@3QBGB; "/migration/clock_drift"
0x140059633  mov     rcx, [r15]; this
0x140059636  call    ?WriteInteger@SavedStateRepository@@UEAAJPEBG_J@Z; SavedStateRepository::WriteInteger(ushort const *,__int64)
0x14005963b  mov     rcx, [rsp+378h]; this
0x140059643  test    eax, eax
0x140059645  js      loc_140059CB2
0x14005964b  mov     rcx, [r15]; this
0x14005964e  call    ?Commit@SavedStateRepository@@UEAAJXZ; SavedStateRepository::Commit(void)
  ... truncated ...
```
