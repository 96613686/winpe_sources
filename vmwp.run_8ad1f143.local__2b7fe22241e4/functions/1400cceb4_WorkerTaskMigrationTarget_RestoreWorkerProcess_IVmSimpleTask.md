# WorkerTaskMigrationTarget::RestoreWorkerProcess(IVmSimpleTask *)

- ea: `0x1400cceb4`
- end: `0x1400cda30`
- name: `?RestoreWorkerProcess@WorkerTaskMigrationTarget@@AEAAJPEAUIVmSimpleTask@@@Z`
- size: `2940`
- prototype: `__int64 __fastcall(WorkerTaskMigrationTarget *__hidden this, struct IVmSimpleTask *)`
- caller_count: `1`
- callee_count: `37`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1402239c4`

## callees

- `0x140022318`
- `0x14002ecf0`
- `0x140030120`
- `0x140031ca8`
- `0x140042260`
- `0x1400544a8`
- `0x1400545d0`
- `0x14005497c`
- `0x140062e20`
- `0x14006af58`
- `0x140079e8c`
- `0x14007a74c`
- `0x14008ff88`
- `0x1400903b0`
- `0x1400941fc`
- `0x1400b3830`
- `0x1400b7b08`
- `0x1400cc1d4`
- `0x1400cc204`
- `0x1400ccb20`
- `0x1400ccc60`
- `0x1400ccd94`
- `0x1400cceb4`
- `0x1400ce7e4`
- `0x1400ce8a4`
- `0x1400eb548`
- `0x1400ed118`
- `0x1400f59b4`
- `0x140111090`
- `0x14011a0a4`
- `0x140132960`
- `0x1401eb8e0`
- `0x140217fe8`
- `0x1402214a4`
- `0x140222b74`
- `0x14022e3d0`
- `0x1402c2010`

## import_xrefs

- `vid!VidChangePartitionLifeState` at `0x1400cd235`
- `vid!VidChangePartitionLifeState` at `0x1400cd289`
- `vid!VidChangePartitionLifeState` at `0x1400cd235`
- `vid!VidChangePartitionLifeState` at `0x1400cd289`

## string_xrefs

- `0x1400ccf40`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400cd01d`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400cd045`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400cd162`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400cd1b8`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400cd200`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400cd343`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400cd417`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400cd4d1`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400cd50d`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400cd5b7`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400cd61a`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400cd888`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400cd8b2`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall WorkerTaskMigrationTarget::RestoreWorkerProcess(
        WorkerTaskMigrationTarget *this,
        struct IVmSimpleTask *a2)
{
  WorkerTaskMigrationTarget *v2; // r14
  VirtualMachine **v3; // rsi
  int v4; // eax
  int v5; // eax
  struct VmRepository **v6; // r12
  VirtualMachine *v7; // rbx
  __int64 v8; // rax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  __int64 v12; // rax
  __int64 v13; // rax
  unsigned int v14; // r9d
  int v15; // r13d
  __int64 *v16; // r13
  __int64 v17; // rdx
  __int64 v18; // rax
  int v19; // r13d
  int v20; // r13d
  int v21; // eax
  __int64 v22; // r13
  int started; // eax
  __int64 (__fastcall *v24)(__int64, __int64, __int64, _QWORD); // rbx
  __int64 v25; // rax
  _QWORD *v26; // rax
  VirtualMachine *v27; // rcx
  const char *v28; // r9
  HyperVRepository *v29; // rbx
  int v30; // eax
  const char *v31; // r9
  const char *v32; // r9
  const char *v33; // r9
  VirtualMachine *v34; // rcx
  const struct Vml::ExceptionTraceParameters *v35; // r8
  int v37; // [rsp+20h] [rbp-288h]
  int v38; // [rsp+20h] [rbp-288h]
  __int64 VmName; // [rsp+30h] [rbp-278h] BYREF
  __int64 v40; // [rsp+38h] [rbp-270h] BYREF
  int HResultFromThrownExceptionAndTrace; // [rsp+40h] [rbp-268h]
  char *v42[2]; // [rsp+48h] [rbp-260h] BYREF
  VirtualMachine **v43; // [rsp+58h] [rbp-250h]
  WorkerTaskMigrationTarget *v44; // [rsp+60h] [rbp-248h]
  struct _GUID v45; // [rsp+68h] [rbp-240h] BYREF
  unsigned __int64 v46; // [rsp+78h] [rbp-230h]
  __int64 (__fastcall *v47)(__int64, __int64, __int64, _QWORD); // [rsp+80h] [rbp-228h]
  _BYTE *v48; // [rsp+88h] [rbp-220h]
  WorkerTaskMigrationTarget *v49; // [rsp+90h] [rbp-218h]
  __int64 v50; // [rsp+98h] [rbp-210h]
  _DWORD v51[3]; // [rsp+A0h] [rbp-208h] BYREF
  char v52; // [rsp+ACh] [rbp-1FCh]
  _BYTE v53[64]; // [rsp+B0h] [rbp-1F8h] BYREF
  wchar_t Buffer[16]; // [rsp+F0h] [rbp-1B8h] BYREF
  __int64 v55; // [rsp+110h] [rbp-198h] BYREF
  __int64 v56; // [rsp+118h] [rbp-190h] BYREF
  _BYTE v57[12]; // [rsp+120h] [rbp-188h] BYREF
  int v58; // [rsp+12Ch] [rbp-17Ch]
  __int64 v59; // [rsp+138h] [rbp-170h]
  __int64 v60; // [rsp+140h] [rbp-168h]
  _BYTE v61[72]; // [rsp+148h] [rbp-160h] BYREF
  _QWORD v62[4]; // [rsp+190h] [rbp-118h] BYREF
  _BYTE v63[40]; // [rsp+1B0h] [rbp-F8h] BYREF
  _BYTE v64[72]; // [rsp+1D8h] [rbp-D0h] BYREF
  _BYTE v65[96]; // [rsp+220h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  try
  {
    v2 = this;
    v44 = this;
    HResultFromThrownExceptionAndTrace = 0;
    v3 = (VirtualMachine **)((char *)this + 16);
    if ( (*((_BYTE *)this + 480) & 0x20) != 0 && !(unsigned int)VirtualMachine::SetState(*v3, 1, 19) )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16866) )
        VmlDebugTraceEx(16866, &off_1402DB310);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5AB,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)0x8000FFFFLL,
        v37);
    }
    v43 = v3;
    v45 = 0;
    Vml::VmPerfTraceOperation::VmPerfTraceOperation(
      (Vml::VmPerfTraceOperation *)v63,
      (struct Vml::VmPerfTraceComponent *)&g_MigrationPerfTrace,
      (const struct _GUID *)((char *)v2 + 412),
      &v45);
    v45 = 0;
    Vml::VmPerfTraceOperation::VmPerfTraceOperation(
      (Vml::VmPerfTraceOperation *)v57,
      (struct Vml::VmPerfTraceComponent *)&g_MigrationPerfTrace,
      (const struct _GUID *)((char *)v2 + 412),
      &v45);
    VmName = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)*v3 + 16));
    Vml::VmPerfTraceOperation::BeginOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v63,
      &VMWP_PERF_MIGRATION_TARGET_RESTORE_WORKER_START);
    v50 = 1;
    v48 = v63;
    v49 = v2;
    v4 = WorkerTaskMigrationTarget::CheckCancel(v2);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5BE,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v4,
        v37);
    v5 = WorkerTaskMigrationTarget::PrepareVmForRestore(v2);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5C1,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v5,
        v37);
    VmName = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)*v3 + 16));
    Vml::VmPerfTraceOperation::BeginOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v57,
      &VMWP_PERF_MIGRATION_TARGET_RESTORE_VSM_START);
    v6 = (struct VmRepository **)((char *)v2 + 568);
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)*v3 + 128) + 264LL))(
      *((_QWORD *)*v3 + 128),
      *((_QWORD *)v2 + 71));
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)v2 + 58) + 408LL))(
      *((_QWORD *)v2 + 58),
      *((_QWORD *)v2 + 71),
      0);
    VmName = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)*v3 + 16));
    Vml::VmPerfTraceOperation::EndOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v57,
      &VMWP_PERF_MIGRATION_TARGET_RESTORE_VSM_STOP,
      (__int64)&VmName);
    v59 = 0;
    v60 = 0;
    v58 = 1;
    VmName = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)*v3 + 16));
    Vml::VmPerfTraceOperation::BeginOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v57,
      &VMWP_PERF_MIGRATION_TARGET_RESTORE_RUNTIME_CHANGES_START);
    v7 = *v3;
    v8 = Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(
           &VmName,
           (char *)v2 + 568);
    v9 = VirtualMachine::ApplyMigrationRuntimeStateChanges(v7, v8);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5DB,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v9,
        v37);
    VmName = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)*v3 + 16));
    Vml::VmPerfTraceOperation::EndOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v57,
      &VMWP_PERF_MIGRATION_TARGET_RESTORE_RUNTIME_CHANGES_STOP,
      (__int64)&VmName);
    v10 = WorkerTaskMigrationTarget::RestoreVmb(v2, *v6);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5E4,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v10,
        v37);
    VmName = (__int64)v2 + 448;
    *((_DWORD *)v2 + 112) = 6;
    if ( *((_BYTE *)v2 + 409) )
    {
      v11 = WorkerTaskMigrationTarget::DoTdxImportEnd(v2);
      if ( v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5F3,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v11,
          v37);
      v12 = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)*v3 + 128) + 24LL))(*((_QWORD *)*v3 + 128) + 24LL);
      if ( !(unsigned int)VidChangePartitionLifeState(v12, 0, 0, 0) && (unsigned int)VmlIsDebugTraceEnabled(16866) )
        VmlDebugTraceEx(16866, &off_1402DB4F0);
      v13 = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)*v3 + 128) + 24LL))(*((_QWORD *)*v3 + 128) + 24LL);
      if ( !(unsigned int)VidChangePartitionLifeState(v13, 2, 0, 0) && (unsigned int)VmlIsDebugTraceEnabled(16866) )
        VmlDebugTraceEx(16866, &off_1402DB220);
    }
    v59 = 0;
    v60 = 0;
    v58 = 1;
    v40 = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)*v3 + 16));
    Vml::VmPerfTraceOperation::BeginOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v57,
      &VMWP_PERF_MIGRATION_TARGET_MOVE_RESTORE_PARTITION_START);
    v15 = VirtualMachine::RestorePartitionStates(*v3, *v6, 0, v14);
    if ( v15 < 0 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16866) )
        VmlDebugTraceWithError(16866, &off_1402DB2A0, (unsigned int)v15);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x624,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v15,
        v37);
    }
    v16 = (__int64 *)*((_QWORD *)*v3 + 124);
    v17 = *v16;
    if ( *((_BYTE *)*v3 + 2665) )
      v55 = (*(__int64 (__fastcall **)(__int64 *))(v17 + 520))(v16);
    else
      v55 = (*(__int64 (__fastcall **)(__int64 *))(v17 + 512))(v16);
    v40 = *((_QWORD *)*v3 + 132);
    v47 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v40 + 24LL);
    v18 = (*(__int64 (__fastcall **)(__int64 *))(*v16 + 528))(v16);
    v19 = v47(v40, v55, v18, 0);
    if ( v19 < 0 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16866) )
        VmlDebugTraceWithError(16866, &off_1402DB3A0, (unsigned int)v19);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x63A,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v19,
        v37);
    }
    v40 = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)*v3 + 16));
    Vml::VmPerfTraceOperation::EndOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v57,
      &VMWP_PERF_MIGRATION_TARGET_MOVE_RESTORE_PARTITION_STOP,
      (__int64)&v40);
    v59 = 0;
    v60 = 0;
    v58 = 1;
    Vml::VmPerfTraceOperation::BeginOperation<>(
      (Vml::VmPerfTraceOperation *)v57,
      &VMWP_PERF_MIGRATION_TARGET_MOVE_RESTORE_METRICS_START);
    v20 = (*(__int64 (__fastcall **)(_QWORD, struct VmRepository *))(**((_QWORD **)*v3 + 133) + 40LL))(
            *((_QWORD *)*v3 + 133),
            *v6);
    if ( v20 < 0 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16866) )
        VmlDebugTraceWithError(16866, &off_1402DB258, (unsigned int)v20);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x64A,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v20,
        v37);
    }
    Vml::VmPerfTraceOperation::EndOperation<>(
      (Vml::VmPerfTraceOperation *)v57,
      &VMWP_PERF_MIGRATION_TARGET_MOVE_RESTORE_METRICS_STOP);
    v21 = WorkerTaskMigrationTarget::CheckCancel(v2);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x654,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v21,
        v37);
    *(_DWORD *)VmName = 7;
    v59 = 0;
    v60 = 0;
    v58 = 1;
    v40 = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)*v3 + 16));
    Vml::VmPerfTraceOperation::BeginOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v57,
      &VMWP_PERF_MIGRATION_TARGET_MOVE_RESUME_VM_START);
    *(_QWORD *)&v45.Data1 = (char *)v2 + 432;
    if ( !*(_DWORD *)(*((_QWORD *)v2 + 54) + 88LL) )
    {
      v22 = (__int64)v3;
      v40 = (__int64)v3;
      started = VirtualMachine::StartVm(*v3, 32, 15);
      if ( started < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x662,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)started,
          v37);
      try
      {
        v24 = (__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD))CurrentFileTime();
        v47 = v24;
        std::wstring::wstring(v62, L"n/a");
        *(_OWORD *)v42 = 0;
        VmRepositoryAutoLock::VmRepositoryAutoLock(v42, *v6, 0);
        if ( SLODWORD(v42[1]) < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x67A,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
            (const char *)LODWORD(v42[1]),
            v37);
        v46 = 0;
        v56 = 0;
        if ( (int)SavedStateRepository::ReadInteger(*v6, L"/migration/blackout_start_timestamp", &v56) >= 0 )
        {
          v46 = ((unsigned __int64)HIDWORD(v47) << 32) + (unsigned int)v24;
          v55 = 0;
          SavedStateRepository::ReadInteger(*v6, L"/migration/clock_drift", &v55);
          v46 += v55 - v56;
          v25 = Vml::FormatString(Buffer);
          std::wstring::operator=(v62, v25);
          std::wstring::_Tidy_deallocate(Buffer);
        }
        VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v42);
        v26 = v62;
        if ( v62[3] > 7u )
          v26 = (_QWORD *)v62[0];
        v56 = (__int64)v26;
        v27 = *v3;
        v55 = (__int64)*v3 + 1152;
        v42[0] = (char *)VirtualMachine::GetVmName((VirtualMachine *)((char *)v27 + 16));
        VmEventWrite<unsigned short const *,unsigned short const *,unsigned short const *>(
          &MSVM_WORKER_MIGRATION_LEAVE_BLACKOUT,
          (__int64)&v55,
          (__int64)&v56);
        v42[0] = (char *)(v46 / 0x2710);
        v42[1] = (char *)__PAIR64__(HIDWORD(v47), (unsigned int)v24);
        v51[0] = 1;
        v51[1] = 4;
        v51[2] = 1;
        v52 = 1;
        Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(
          v53,
          v42);
        std::variant<std::monostate,Compute::Responses::System::WorkerCoreNotification,Schema::Responses::System::OperationSystemMigrationNotificationInfo>::variant<std::monostate,Compute::Responses::System::WorkerCoreNotification,Schema::Responses::System::OperationSystemMigrationNotificationInfo>(
          v65,
          v51);
        (*(void (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)v2 + 57) + 128LL))(*((_QWORD *)v2 + 57), v65);
        std::_Variant_destroy_layer_<std::monostate,Compute::Responses::System::WorkerCoreNotification,Schema::Responses::System::OperationSystemMigrationNotificationInfo>::~_Variant_destroy_layer_<std::monostate,Compute::Responses::System::WorkerCoreNotification,Schema::Responses::System::OperationSystemMigrationNotificationInfo>(v65);
        Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::~DelayedBase<void,Marshal::Details::DelayedJsonTraits>(v53);
        std::wstring::_Tidy_deallocate(v62);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x6AA,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          v28);
        v22 = v40;
        v2 = v44;
        v3 = v43;
      }
      try
      {
        v29 = *(HyperVRepository **)(*(_QWORD *)(*(_QWORD *)v22 + 1416LL) + 88LL);
        *(_OWORD *)v42 = 0;
        VmRepositoryAutoLock::VmRepositoryAutoLock(v42, v29, 1);
        if ( SLODWORD(v42[1]) < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6B7,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
            (const char *)LODWORD(v42[1]),
            v38);
        v30 = HyperVRepository::Compact(v29, 1);
        if ( v30 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6B8,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
            (const char *)(unsigned int)v30,
            v38);
        VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v42);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x6BA,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          v31);
        v22 = v40;
        v2 = v44;
        v3 = v43;
      }
      try
      {
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)v22 + 1064LL) + 56LL))(*(_QWORD *)(*(_QWORD *)v22 + 1064LL));
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x6C0,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          v32);
        v2 = v44;
        v3 = v43;
      }
      try
      {
        VirtualDeviceMigrationTargetCollection::OnMigrationResumeCompletionAtTarget(*((VirtualDeviceMigrationTargetCollection **)v2
                                                                                    + 84));
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x6C9,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          v33);
        v2 = v44;
        v3 = v43;
      }
    }
    *(_DWORD *)VmName = 8;
    v34 = *v3;
    if ( *(_DWORD *)(**(_QWORD **)&v45.Data1 + 88LL) )
      VirtualMachine::SetState(v34, 3, 24);
    else
      VirtualMachine::SetState(v34, 2, 24);
    *(_QWORD *)&v45.Data1 = VirtualMachine::GetVmName((VirtualMachine *)((char *)*v3 + 16));
    Vml::VmPerfTraceOperation::EndOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v57,
      &VMWP_PERF_MIGRATION_TARGET_MOVE_RESUME_VM_STOP,
      (__int64)&v45);
    *(_QWORD *)&v45.Data1 = VirtualMachine::GetVmName((VirtualMachine *)(*((_QWORD *)v49 + 2) + 16LL));
    Vml::VmPerfTraceOperation::EndOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v63,
      &VMWP_PERF_MIGRATION_TARGET_RESTORE_WORKER_STOP,
      (__int64)&v45);
    std::wstring::_Tidy_deallocate(v61);
    std::wstring::_Tidy_deallocate(v64);
  }
  catch ( ... )
  {
    HResultFromThrownExceptionAndTrace = Vml::GetHResultFromThrownExceptionAndTrace(
                                           (Vml *)0x41E2,
                                           (unsigned __int16)&off_1402DB300,
                                           v35);
    v2 = v44;
  }
  if ( a2 && HResultFromThrownExceptionAndTrace >= 0 )
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)v2 + 78) + 96LL))(*((_QWORD *)v2 + 78), 0, 0);
  return (unsigned int)HResultFromThrownExceptionAndTrace;
}

```

## disassembly

```asm
0x1400cceb4  mov     [rsp+arg_10], rbx
0x1400cceb9  mov     [rsp+arg_18], rsi
0x1400ccebe  mov     [rsp+arg_8], rdx
0x1400ccec3  push    r12
0x1400ccec5  push    r13
0x1400ccec7  push    r14
0x1400ccec9  sub     rsp, 290h
0x1400cced0  mov     rax, cs:__security_cookie
0x1400cced7  xor     rax, rsp
0x1400cceda  mov     [rsp+2A8h+var_28], rax
0x1400ccee2  mov     r14, rcx
0x1400ccee5  mov     [rsp+2A8h+var_248], rcx
0x1400cceea  mov     [rsp+2A8h+var_268], 0
0x1400ccef2  lea     rsi, [rcx+10h]
0x1400ccef6  test    byte ptr [rcx+1E0h], 20h
0x1400ccefd  jz      short loc_1400CCF51
0x1400cceff  mov     edx, 1
0x1400ccf04  lea     r8d, [rdx+12h]
0x1400ccf08  mov     rcx, [rsi]
0x1400ccf0b  call    ?SetState@VirtualMachine@@QEAAHW4_VM_STATE@@W4_VM_STATE_REASON_CODE@@@Z; VirtualMachine::SetState(_VM_STATE,_VM_STATE_REASON_CODE)
0x1400ccf10  test    eax, eax
0x1400ccf12  jnz     short loc_1400CCF51
0x1400ccf14  mov     ebx, 41E2h
0x1400ccf19  mov     ecx, ebx
0x1400ccf1b  call    VmlIsDebugTraceEnabled
0x1400ccf20  test    eax, eax
0x1400ccf22  jz      short loc_1400CCF32
0x1400ccf24  lea     rdx, off_1402DB310; "Failed to set state of VM to starting."
0x1400ccf2b  mov     ecx, ebx
0x1400ccf2d  call    VmlDebugTraceEx
0x1400ccf32  mov     rcx, [rsp+2A8h]; this
0x1400ccf3a  mov     r9d, 8000FFFFh; char *
0x1400ccf40  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400ccf47  mov     edx, 5ABh; void *
0x1400ccf4c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400ccf51  mov     [rsp+2A8h+var_250], rsi
0x1400ccf56  xorps   xmm0, xmm0
0x1400ccf59  movups  xmmword ptr [rsp+2A8h+var_240.Data1], xmm0
0x1400ccf5e  lea     rbx, [r14+19Ch]
0x1400ccf65  lea     r9, [rsp+2A8h+var_240]; struct _GUID *
0x1400ccf6a  mov     r8, rbx; struct _GUID *
0x1400ccf6d  lea     rdx, ?g_MigrationPerfTrace@@3VVmPerfTraceComponent@Vml@@A; struct Vml::VmPerfTraceComponent *
0x1400ccf74  lea     rcx, [rsp+2A8h+var_F8]; this
0x1400ccf7c  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x1400ccf81  nop
0x1400ccf82  xorps   xmm0, xmm0
0x1400ccf85  movups  xmmword ptr [rsp+2A8h+var_240.Data1], xmm0
0x1400ccf8a  lea     r9, [rsp+2A8h+var_240]; struct _GUID *
0x1400ccf8f  mov     r8, rbx; struct _GUID *
0x1400ccf92  lea     rdx, ?g_MigrationPerfTrace@@3VVmPerfTraceComponent@Vml@@A; struct Vml::VmPerfTraceComponent *
0x1400ccf99  lea     rcx, [rsp+2A8h+var_188]; this
0x1400ccfa1  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x1400ccfa6  nop
0x1400ccfa7  mov     rcx, [rsi]
0x1400ccfaa  add     rcx, 10h; this
0x1400ccfae  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400ccfb3  mov     [rsp+2A8h+var_278], rax
0x1400ccfb8  lea     r8, [rsp+2A8h+var_278]
0x1400ccfbd  lea     rdx, VMWP_PERF_MIGRATION_TARGET_RESTORE_WORKER_START; EventDescriptor
0x1400ccfc4  lea     rcx, [rsp+2A8h+var_F8]; this
0x1400ccfcc  call    ??$BeginOperation@PEBG@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@$$QEAPEBG@Z; Vml::VmPerfTraceOperation::BeginOperation<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const * &&)
0x1400ccfd1  xorps   xmm0, xmm0
0x1400ccfd4  xor     eax, eax
0x1400ccfd6  movups  [rsp+2A8h+var_220], xmm0
0x1400ccfde  mov     [rsp+2A8h+var_210], rax
0x1400ccfe6  lea     rax, [rsp+2A8h+var_F8]
0x1400ccfee  mov     qword ptr [rsp+2A8h+var_220], rax
0x1400ccff6  mov     qword ptr [rsp+2A8h+var_220+8], r14
0x1400ccffe  mov     byte ptr [rsp+2A8h+var_210], 1
0x1400cd006  mov     rcx, r14; this
0x1400cd009  call    ?CheckCancel@WorkerTaskMigrationTarget@@AEAAJXZ; WorkerTaskMigrationTarget::CheckCancel(void)
0x1400cd00e  mov     rcx, [rsp+2A8h]; this
0x1400cd016  test    eax, eax
0x1400cd018  jns     short loc_1400CD02E
0x1400cd01a  mov     r9d, eax; char *
0x1400cd01d  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400cd024  mov     edx, 5BEh; void *
0x1400cd029  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cd02e  mov     rcx, r14; this
0x1400cd031  call    ?PrepareVmForRestore@WorkerTaskMigrationTarget@@AEAAJXZ; WorkerTaskMigrationTarget::PrepareVmForRestore(void)
0x1400cd036  mov     rcx, [rsp+2A8h]; this
0x1400cd03e  test    eax, eax
0x1400cd040  jns     short loc_1400CD056
0x1400cd042  mov     r9d, eax; char *
0x1400cd045  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400cd04c  mov     edx, 5C1h; void *
0x1400cd051  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cd056  mov     rcx, [rsi]
0x1400cd059  add     rcx, 10h; this
0x1400cd05d  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400cd062  mov     [rsp+2A8h+var_278], rax
0x1400cd067  lea     r8, [rsp+2A8h+var_278]
0x1400cd06c  lea     rdx, VMWP_PERF_MIGRATION_TARGET_RESTORE_VSM_START; EventDescriptor
0x1400cd073  lea     rcx, [rsp+2A8h+var_188]; this
0x1400cd07b  call    ??$BeginOperation@PEBG@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@$$QEAPEBG@Z; Vml::VmPerfTraceOperation::BeginOperation<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const * &&)
0x1400cd080  mov     rax, [rsi]
0x1400cd083  mov     rcx, [rax+400h]
0x1400cd08a  lea     r12, [r14+238h]
0x1400cd091  mov     rax, [rcx]
0x1400cd094  mov     rdx, [r12]
0x1400cd098  mov     rax, [rax+108h]
0x1400cd09f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cd0a4  mov     rcx, [r14+1D0h]
0x1400cd0ab  mov     rax, [rcx]
0x1400cd0ae  xor     r8d, r8d
0x1400cd0b1  mov     rdx, [r12]
0x1400cd0b5  mov     rax, [rax+198h]
0x1400cd0bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cd0c1  mov     rcx, [rsi]
0x1400cd0c4  add     rcx, 10h; this
0x1400cd0c8  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400cd0cd  mov     [rsp+2A8h+var_278], rax
0x1400cd0d2  lea     r8, [rsp+2A8h+var_278]; __int64
0x1400cd0d7  lea     rdx, VMWP_PERF_MIGRATION_TARGET_RESTORE_VSM_STOP; EventDescriptor
0x1400cd0de  lea     rcx, [rsp+2A8h+var_188]; this
0x1400cd0e6  call    ??$EndOperation@PEBG@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@$$QEAPEBG@Z; Vml::VmPerfTraceOperation::EndOperation<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const * &&)
0x1400cd0eb  mov     [rsp+2A8h+var_170], 0
0x1400cd0f7  mov     [rsp+2A8h+var_168], 0
0x1400cd103  mov     [rsp+2A8h+var_17C], 1
0x1400cd10e  mov     rcx, [rsi]
0x1400cd111  add     rcx, 10h; this
0x1400cd115  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400cd11a  mov     [rsp+2A8h+var_278], rax
0x1400cd11f  lea     r8, [rsp+2A8h+var_278]
0x1400cd124  lea     rdx, VMWP_PERF_MIGRATION_TARGET_RESTORE_RUNTIME_CHANGES_START; EventDescriptor
0x1400cd12b  lea     rcx, [rsp+2A8h+var_188]; this
0x1400cd133  call    ??$BeginOperation@PEBG@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@$$QEAPEBG@Z; Vml::VmPerfTraceOperation::BeginOperation<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const * &&)
0x1400cd138  mov     rbx, [rsi]
0x1400cd13b  mov     rdx, r12
0x1400cd13e  lea     rcx, [rsp+2A8h+var_278]
0x1400cd143  call    ??0?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@QEAA@AEBV01@@Z; Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> const &)
0x1400cd148  mov     rdx, rax
0x1400cd14b  mov     rcx, rbx
0x1400cd14e  call    ?ApplyMigrationRuntimeStateChanges@VirtualMachine@@QEAAJV?$VmReferencePtr@VSavedStateRepository@@VVmUserReferenceTraits@Vml@@@Vml@@@Z; VirtualMachine::ApplyMigrationRuntimeStateChanges(Vml::VmReferencePtr<SavedStateRepository,Vml::VmUserReferenceTraits>)
0x1400cd153  mov     rcx, [rsp+2A8h]; this
0x1400cd15b  test    eax, eax
0x1400cd15d  jns     short loc_1400CD173
0x1400cd15f  mov     r9d, eax; char *
0x1400cd162  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400cd169  mov     edx, 5DBh; void *
0x1400cd16e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cd173  mov     rcx, [rsi]
0x1400cd176  add     rcx, 10h; this
0x1400cd17a  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400cd17f  mov     [rsp+2A8h+var_278], rax
0x1400cd184  lea     r8, [rsp+2A8h+var_278]; __int64
0x1400cd189  lea     rdx, VMWP_PERF_MIGRATION_TARGET_RESTORE_RUNTIME_CHANGES_STOP; EventDescriptor
0x1400cd190  lea     rcx, [rsp+2A8h+var_188]; this
0x1400cd198  call    ??$EndOperation@PEBG@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@$$QEAPEBG@Z; Vml::VmPerfTraceOperation::EndOperation<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const * &&)
0x1400cd19d  mov     rdx, [r12]; struct VmRepository *
0x1400cd1a1  mov     rcx, r14; this
0x1400cd1a4  call    ?RestoreVmb@WorkerTaskMigrationTarget@@AEAAJPEAVVmRepository@@@Z; WorkerTaskMigrationTarget::RestoreVmb(VmRepository *)
0x1400cd1a9  mov     rcx, [rsp+2A8h]; this
0x1400cd1b1  test    eax, eax
0x1400cd1b3  jns     short loc_1400CD1C9
0x1400cd1b5  mov     r9d, eax; char *
0x1400cd1b8  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400cd1bf  mov     edx, 5E4h; void *
0x1400cd1c4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cd1c9  lea     rax, [r14+1C0h]
0x1400cd1d0  mov     [rsp+2A8h+var_278], rax
0x1400cd1d5  mov     dword ptr [rax], 6
0x1400cd1db  cmp     byte ptr [r14+199h], 0
0x1400cd1e3  jz      loc_1400CD2B4
0x1400cd1e9  mov     rcx, r14; this
0x1400cd1ec  call    ?DoTdxImportEnd@WorkerTaskMigrationTarget@@AEAAJXZ; WorkerTaskMigrationTarget::DoTdxImportEnd(void)
0x1400cd1f1  mov     rcx, [rsp+2A8h]; this
0x1400cd1f9  test    eax, eax
0x1400cd1fb  jns     short loc_1400CD211
0x1400cd1fd  mov     r9d, eax; char *
0x1400cd200  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400cd207  mov     edx, 5F3h; void *
0x1400cd20c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cd211  mov     rax, [rsi]
0x1400cd214  mov     rcx, [rax+400h]
0x1400cd21b  add     rcx, 18h
0x1400cd21f  mov     rax, [rcx]
0x1400cd222  mov     rax, [rax]
0x1400cd225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cd22a  xor     r9d, r9d
0x1400cd22d  xor     r8d, r8d
0x1400cd230  xor     edx, edx
0x1400cd232  mov     rcx, rax
0x1400cd235  call    cs:__imp_VidChangePartitionLifeState
0x1400cd23c  nop     dword ptr [rax+rax+00h]
0x1400cd241  mov     ebx, 41E2h
0x1400cd246  test    eax, eax
0x1400cd248  jnz     short loc_1400CD263
0x1400cd24a  mov     ecx, ebx
0x1400cd24c  call    VmlIsDebugTraceEnabled
0x1400cd251  test    eax, eax
0x1400cd253  jz      short loc_1400CD263
0x1400cd255  lea     rdx, off_1402DB4F0; "Failed to transition partition into sec"...
0x1400cd25c  mov     ecx, ebx
0x1400cd25e  call    VmlDebugTraceEx
0x1400cd263  mov     rax, [rsi]
0x1400cd266  mov     rcx, [rax+400h]
0x1400cd26d  add     rcx, 18h
0x1400cd271  mov     rax, [rcx]
0x1400cd274  mov     rax, [rax]
0x1400cd277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cd27c  xor     r9d, r9d
0x1400cd27f  xor     r8d, r8d
0x1400cd282  lea     edx, [r9+2]
0x1400cd286  mov     rcx, rax
0x1400cd289  call    cs:__imp_VidChangePartitionLifeState
0x1400cd290  nop     dword ptr [rax+rax+00h]
0x1400cd295  test    eax, eax
0x1400cd297  jnz     short loc_1400CD2B9
0x1400cd299  mov     ecx, ebx
0x1400cd29b  call    VmlIsDebugTraceEnabled
0x1400cd2a0  test    eax, eax
0x1400cd2a2  jz      short loc_1400CD2B9
0x1400cd2a4  lea     rdx, off_1402DB220; "Failed to transition partition into com"...
0x1400cd2ab  mov     ecx, ebx
0x1400cd2ad  call    VmlDebugTraceEx
0x1400cd2b2  jmp     short loc_1400CD2B9
0x1400cd2b4  mov     ebx, 41E2h
0x1400cd2b9  mov     [rsp+2A8h+var_170], 0
0x1400cd2c5  mov     [rsp+2A8h+var_168], 0
0x1400cd2d1  mov     [rsp+2A8h+var_17C], 1
0x1400cd2dc  mov     rcx, [rsi]
0x1400cd2df  add     rcx, 10h; this
0x1400cd2e3  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400cd2e8  mov     [rsp+2A8h+var_270], rax
0x1400cd2ed  lea     r8, [rsp+2A8h+var_270]
0x1400cd2f2  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_RESTORE_PARTITION_START; EventDescriptor
0x1400cd2f9  lea     rcx, [rsp+2A8h+var_188]; this
0x1400cd301  call    ??$BeginOperation@PEBG@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@$$QEAPEBG@Z; Vml::VmPerfTraceOperation::BeginOperation<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const * &&)
0x1400cd306  xor     r8d, r8d; bool
0x1400cd309  mov     rdx, [r12]; struct VmRepository *
0x1400cd30d  mov     rcx, [rsi]; this
0x1400cd310  call    ?RestorePartitionStates@VirtualMachine@@QEAAJPEAVVmRepository@@_NI@Z; VirtualMachine::RestorePartitionStates(VmRepository *,bool,uint)
0x1400cd315  mov     r13d, eax
0x1400cd318  test    eax, eax
0x1400cd31a  jns     short loc_1400CD354
0x1400cd31c  mov     ecx, ebx
0x1400cd31e  call    VmlIsDebugTraceEnabled
0x1400cd323  test    eax, eax
0x1400cd325  jz      short loc_1400CD338
0x1400cd327  mov     r8d, r13d
0x1400cd32a  lea     rdx, off_1402DB2A0; "Failed to restore partition state"
0x1400cd331  mov     ecx, ebx
0x1400cd333  call    VmlDebugTraceWithError
0x1400cd338  mov     rcx, [rsp+2A8h]; this
0x1400cd340  mov     r9d, r13d; char *
0x1400cd343  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400cd34a  mov     edx, 624h; void *
0x1400cd34f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cd354  mov     rax, [rsi]
0x1400cd357  mov     r13, [rax+3E0h]
0x1400cd35e  mov     rdx, [r13+0]
0x1400cd362  mov     rcx, r13
0x1400cd365  cmp     byte ptr [rax+0A69h], 0
0x1400cd36c  jz      short loc_1400CD384
0x1400cd36e  mov     rax, [rdx+208h]
0x1400cd375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cd37a  mov     [rsp+2A8h+var_198], rax
0x1400cd382  jmp     short loc_1400CD398
0x1400cd384  mov     rax, [rdx+200h]
0x1400cd38b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cd390  mov     [rsp+2A8h+var_198], rax
0x1400cd398  mov     rax, [rsi]
0x1400cd39b  mov     rax, [rax+420h]
0x1400cd3a2  mov     [rsp+2A8h+var_270], rax
0x1400cd3a7  mov     rax, [rax]
0x1400cd3aa  mov     rax, [rax+18h]
0x1400cd3ae  mov     [rsp+2A8h+var_228], rax
0x1400cd3b6  mov     rdx, [r13+0]
0x1400cd3ba  mov     rcx, r13
0x1400cd3bd  mov     rax, [rdx+210h]
0x1400cd3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cd3c9  xor     r9d, r9d
0x1400cd3cc  mov     r8, rax
0x1400cd3cf  mov     rdx, [rsp+2A8h+var_198]
0x1400cd3d7  mov     rcx, [rsp+2A8h+var_270]
0x1400cd3dc  mov     rax, [rsp+2A8h+var_228]
0x1400cd3e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cd3e9  mov     r13d, eax
0x1400cd3ec  test    eax, eax
0x1400cd3ee  jns     short loc_1400CD428
0x1400cd3f0  mov     ecx, ebx
0x1400cd3f2  call    VmlIsDebugTraceEnabled
0x1400cd3f7  test    eax, eax
0x1400cd3f9  jz      short loc_1400CD40C
0x1400cd3fb  mov     r8d, r13d
0x1400cd3fe  lea     rdx, off_1402DB3A0; "Failed to restore saved state manager s"...
0x1400cd405  mov     ecx, ebx
0x1400cd407  call    VmlDebugTraceWithError
0x1400cd40c  mov     rcx, [rsp+2A8h]; this
0x1400cd414  mov     r9d, r13d; char *
0x1400cd417  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400cd41e  mov     edx, 63Ah; void *
0x1400cd423  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cd428  mov     rcx, [rsi]
0x1400cd42b  add     rcx, 10h; this
0x1400cd42f  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400cd434  mov     [rsp+2A8h+var_270], rax
0x1400cd439  lea     r8, [rsp+2A8h+var_270]; __int64
0x1400cd43e  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_RESTORE_PARTITION_STOP; EventDescriptor
  ... truncated ...
```
