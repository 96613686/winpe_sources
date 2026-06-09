# WorkerTaskMigrationTarget::RestoreWorkerProcess(IVmSimpleTask *)

- ea: `0x1400698d4`
- end: `0x14006a450`
- name: `?RestoreWorkerProcess@WorkerTaskMigrationTarget@@AEAAJPEAUIVmSimpleTask@@@Z`
- size: `2940`
- prototype: `__int64 __fastcall(WorkerTaskMigrationTarget *__hidden this, struct IVmSimpleTask *)`
- caller_count: `1`
- callee_count: `37`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14021ad74`

## callees

- `0x140022888`
- `0x1400364a0`
- `0x14003b720`
- `0x14003c680`
- `0x14003d828`
- `0x140053de8`
- `0x140053f10`
- `0x1400544a8`
- `0x14005f278`
- `0x14005f6dc`
- `0x1400696e4`
- `0x1400698d4`
- `0x14006b204`
- `0x14006b2c4`
- `0x14006b424`
- `0x14006b4b0`
- `0x14006caa0`
- `0x140070ecc`
- `0x140078628`
- `0x14008b4fc`
- `0x14008bdbc`
- `0x1400ad84c`
- `0x1400c4fe8`
- `0x1400dc8cc`
- `0x1400de398`
- `0x1400e7314`
- `0x1400ececc`
- `0x140102580`
- `0x14011ea40`
- `0x14014af28`
- `0x1401db2d0`
- `0x140209bbc`
- `0x140215f84`
- `0x140218358`
- `0x140219514`
- `0x140227370`
- `0x1402cb010`

## import_xrefs

- `vid!VidChangePartitionLifeState` at `0x140069c55`
- `vid!VidChangePartitionLifeState` at `0x140069ca9`
- `vid!VidChangePartitionLifeState` at `0x140069c55`
- `vid!VidChangePartitionLifeState` at `0x140069ca9`

## string_xrefs

- `0x140069960`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140069a3d`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140069a65`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140069b82`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140069bd8`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140069c20`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140069d63`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140069e37`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140069ef1`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140069f2d`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x140069fd7`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14006a03a`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14006a2a8`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14006a2d2`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`

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
        VmlDebugTraceEx(16866, &off_1402E4840);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5DA,
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
        (void *)0x5ED,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v4,
        v37);
    v5 = WorkerTaskMigrationTarget::PrepareVmForRestore(v2);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5F0,
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
        (void *)0x60A,
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
        (void *)0x613,
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
          (void *)0x622,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v11,
          v37);
      v12 = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)*v3 + 128) + 24LL))(*((_QWORD *)*v3 + 128) + 24LL);
      if ( !(unsigned int)VidChangePartitionLifeState(v12, 0, 0, 0) && (unsigned int)VmlIsDebugTraceEnabled(16866) )
        VmlDebugTraceEx(16866, &off_1402E4A18);
      v13 = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)*v3 + 128) + 24LL))(*((_QWORD *)*v3 + 128) + 24LL);
      if ( !(unsigned int)VidChangePartitionLifeState(v13, 2, 0, 0) && (unsigned int)VmlIsDebugTraceEnabled(16866) )
        VmlDebugTraceEx(16866, &off_1402E4750);
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
        VmlDebugTraceWithError(16866, &off_1402E4800, (unsigned int)v15);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x653,
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
        VmlDebugTraceWithError(16866, &off_1402E48D0, (unsigned int)v19);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x669,
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
        VmlDebugTraceWithError(16866, &off_1402E47A0, (unsigned int)v20);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x679,
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
        (void *)0x683,
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
          (void *)0x691,
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
            (void *)0x6A9,
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
          (void *)0x6D9,
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
            (void *)0x6E6,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
            (const char *)LODWORD(v42[1]),
            v38);
        v30 = HyperVRepository::Compact(v29, 1);
        if ( v30 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6E7,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
            (const char *)(unsigned int)v30,
            v38);
        VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v42);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x6E9,
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
          (void *)0x6EF,
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
          (void *)0x6F8,
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
                                           (unsigned __int16)&off_1402E4830,
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
0x1400698d4  mov     [rsp+arg_10], rbx
0x1400698d9  mov     [rsp+arg_18], rsi
0x1400698de  mov     [rsp+arg_8], rdx
0x1400698e3  push    r12
0x1400698e5  push    r13
0x1400698e7  push    r14
0x1400698e9  sub     rsp, 290h
0x1400698f0  mov     rax, cs:__security_cookie
0x1400698f7  xor     rax, rsp
0x1400698fa  mov     [rsp+2A8h+var_28], rax
0x140069902  mov     r14, rcx
0x140069905  mov     [rsp+2A8h+var_248], rcx
0x14006990a  mov     [rsp+2A8h+var_268], 0
0x140069912  lea     rsi, [rcx+10h]
0x140069916  test    byte ptr [rcx+1E0h], 20h
0x14006991d  jz      short loc_140069971
0x14006991f  mov     edx, 1
0x140069924  lea     r8d, [rdx+12h]
0x140069928  mov     rcx, [rsi]
0x14006992b  call    ?SetState@VirtualMachine@@QEAAHW4_VM_STATE@@W4_VM_STATE_REASON_CODE@@@Z; VirtualMachine::SetState(_VM_STATE,_VM_STATE_REASON_CODE)
0x140069930  test    eax, eax
0x140069932  jnz     short loc_140069971
0x140069934  mov     ebx, 41E2h
0x140069939  mov     ecx, ebx
0x14006993b  call    VmlIsDebugTraceEnabled
0x140069940  test    eax, eax
0x140069942  jz      short loc_140069952
0x140069944  lea     rdx, off_1402E4840; "Failed to set state of VM to starting."
0x14006994b  mov     ecx, ebx
0x14006994d  call    VmlDebugTraceEx
0x140069952  mov     rcx, [rsp+2A8h]; this
0x14006995a  mov     r9d, 8000FFFFh; char *
0x140069960  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x140069967  mov     edx, 5DAh; void *
0x14006996c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140069971  mov     [rsp+2A8h+var_250], rsi
0x140069976  xorps   xmm0, xmm0
0x140069979  movups  xmmword ptr [rsp+2A8h+var_240.Data1], xmm0
0x14006997e  lea     rbx, [r14+19Ch]
0x140069985  lea     r9, [rsp+2A8h+var_240]; struct _GUID *
0x14006998a  mov     r8, rbx; struct _GUID *
0x14006998d  lea     rdx, ?g_MigrationPerfTrace@@3VVmPerfTraceComponent@Vml@@A; struct Vml::VmPerfTraceComponent *
0x140069994  lea     rcx, [rsp+2A8h+var_F8]; this
0x14006999c  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x1400699a1  nop
0x1400699a2  xorps   xmm0, xmm0
0x1400699a5  movups  xmmword ptr [rsp+2A8h+var_240.Data1], xmm0
0x1400699aa  lea     r9, [rsp+2A8h+var_240]; struct _GUID *
0x1400699af  mov     r8, rbx; struct _GUID *
0x1400699b2  lea     rdx, ?g_MigrationPerfTrace@@3VVmPerfTraceComponent@Vml@@A; struct Vml::VmPerfTraceComponent *
0x1400699b9  lea     rcx, [rsp+2A8h+var_188]; this
0x1400699c1  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x1400699c6  nop
0x1400699c7  mov     rcx, [rsi]
0x1400699ca  add     rcx, 10h; this
0x1400699ce  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400699d3  mov     [rsp+2A8h+var_278], rax
0x1400699d8  lea     r8, [rsp+2A8h+var_278]
0x1400699dd  lea     rdx, VMWP_PERF_MIGRATION_TARGET_RESTORE_WORKER_START; EventDescriptor
0x1400699e4  lea     rcx, [rsp+2A8h+var_F8]; this
0x1400699ec  call    ??$BeginOperation@PEBG@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@$$QEAPEBG@Z; Vml::VmPerfTraceOperation::BeginOperation<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const * &&)
0x1400699f1  xorps   xmm0, xmm0
0x1400699f4  xor     eax, eax
0x1400699f6  movups  [rsp+2A8h+var_220], xmm0
0x1400699fe  mov     [rsp+2A8h+var_210], rax
0x140069a06  lea     rax, [rsp+2A8h+var_F8]
0x140069a0e  mov     qword ptr [rsp+2A8h+var_220], rax
0x140069a16  mov     qword ptr [rsp+2A8h+var_220+8], r14
0x140069a1e  mov     byte ptr [rsp+2A8h+var_210], 1
0x140069a26  mov     rcx, r14; this
0x140069a29  call    ?CheckCancel@WorkerTaskMigrationTarget@@AEAAJXZ; WorkerTaskMigrationTarget::CheckCancel(void)
0x140069a2e  mov     rcx, [rsp+2A8h]; this
0x140069a36  test    eax, eax
0x140069a38  jns     short loc_140069A4E
0x140069a3a  mov     r9d, eax; char *
0x140069a3d  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x140069a44  mov     edx, 5EDh; void *
0x140069a49  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140069a4e  mov     rcx, r14; this
0x140069a51  call    ?PrepareVmForRestore@WorkerTaskMigrationTarget@@AEAAJXZ; WorkerTaskMigrationTarget::PrepareVmForRestore(void)
0x140069a56  mov     rcx, [rsp+2A8h]; this
0x140069a5e  test    eax, eax
0x140069a60  jns     short loc_140069A76
0x140069a62  mov     r9d, eax; char *
0x140069a65  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x140069a6c  mov     edx, 5F0h; void *
0x140069a71  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140069a76  mov     rcx, [rsi]
0x140069a79  add     rcx, 10h; this
0x140069a7d  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x140069a82  mov     [rsp+2A8h+var_278], rax
0x140069a87  lea     r8, [rsp+2A8h+var_278]
0x140069a8c  lea     rdx, VMWP_PERF_MIGRATION_TARGET_RESTORE_VSM_START; EventDescriptor
0x140069a93  lea     rcx, [rsp+2A8h+var_188]; this
0x140069a9b  call    ??$BeginOperation@PEBG@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@$$QEAPEBG@Z; Vml::VmPerfTraceOperation::BeginOperation<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const * &&)
0x140069aa0  mov     rax, [rsi]
0x140069aa3  mov     rcx, [rax+400h]
0x140069aaa  lea     r12, [r14+238h]
0x140069ab1  mov     rax, [rcx]
0x140069ab4  mov     rdx, [r12]
0x140069ab8  mov     rax, [rax+108h]
0x140069abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140069ac4  mov     rcx, [r14+1D0h]
0x140069acb  mov     rax, [rcx]
0x140069ace  xor     r8d, r8d
0x140069ad1  mov     rdx, [r12]
0x140069ad5  mov     rax, [rax+198h]
0x140069adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140069ae1  mov     rcx, [rsi]
0x140069ae4  add     rcx, 10h; this
0x140069ae8  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x140069aed  mov     [rsp+2A8h+var_278], rax
0x140069af2  lea     r8, [rsp+2A8h+var_278]; __int64
0x140069af7  lea     rdx, VMWP_PERF_MIGRATION_TARGET_RESTORE_VSM_STOP; EventDescriptor
0x140069afe  lea     rcx, [rsp+2A8h+var_188]; this
0x140069b06  call    ??$EndOperation@PEBG@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@$$QEAPEBG@Z; Vml::VmPerfTraceOperation::EndOperation<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const * &&)
0x140069b0b  mov     [rsp+2A8h+var_170], 0
0x140069b17  mov     [rsp+2A8h+var_168], 0
0x140069b23  mov     [rsp+2A8h+var_17C], 1
0x140069b2e  mov     rcx, [rsi]
0x140069b31  add     rcx, 10h; this
0x140069b35  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x140069b3a  mov     [rsp+2A8h+var_278], rax
0x140069b3f  lea     r8, [rsp+2A8h+var_278]
0x140069b44  lea     rdx, VMWP_PERF_MIGRATION_TARGET_RESTORE_RUNTIME_CHANGES_START; EventDescriptor
0x140069b4b  lea     rcx, [rsp+2A8h+var_188]; this
0x140069b53  call    ??$BeginOperation@PEBG@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@$$QEAPEBG@Z; Vml::VmPerfTraceOperation::BeginOperation<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const * &&)
0x140069b58  mov     rbx, [rsi]
0x140069b5b  mov     rdx, r12
0x140069b5e  lea     rcx, [rsp+2A8h+var_278]
0x140069b63  call    ??0?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@QEAA@AEBV01@@Z; Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> const &)
0x140069b68  mov     rdx, rax
0x140069b6b  mov     rcx, rbx
0x140069b6e  call    ?ApplyMigrationRuntimeStateChanges@VirtualMachine@@QEAAJV?$VmReferencePtr@VSavedStateRepository@@VVmUserReferenceTraits@Vml@@@Vml@@@Z; VirtualMachine::ApplyMigrationRuntimeStateChanges(Vml::VmReferencePtr<SavedStateRepository,Vml::VmUserReferenceTraits>)
0x140069b73  mov     rcx, [rsp+2A8h]; this
0x140069b7b  test    eax, eax
0x140069b7d  jns     short loc_140069B93
0x140069b7f  mov     r9d, eax; char *
0x140069b82  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x140069b89  mov     edx, 60Ah; void *
0x140069b8e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140069b93  mov     rcx, [rsi]
0x140069b96  add     rcx, 10h; this
0x140069b9a  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x140069b9f  mov     [rsp+2A8h+var_278], rax
0x140069ba4  lea     r8, [rsp+2A8h+var_278]; __int64
0x140069ba9  lea     rdx, VMWP_PERF_MIGRATION_TARGET_RESTORE_RUNTIME_CHANGES_STOP; EventDescriptor
0x140069bb0  lea     rcx, [rsp+2A8h+var_188]; this
0x140069bb8  call    ??$EndOperation@PEBG@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@$$QEAPEBG@Z; Vml::VmPerfTraceOperation::EndOperation<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const * &&)
0x140069bbd  mov     rdx, [r12]; struct VmRepository *
0x140069bc1  mov     rcx, r14; this
0x140069bc4  call    ?RestoreVmb@WorkerTaskMigrationTarget@@AEAAJPEAVVmRepository@@@Z; WorkerTaskMigrationTarget::RestoreVmb(VmRepository *)
0x140069bc9  mov     rcx, [rsp+2A8h]; this
0x140069bd1  test    eax, eax
0x140069bd3  jns     short loc_140069BE9
0x140069bd5  mov     r9d, eax; char *
0x140069bd8  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x140069bdf  mov     edx, 613h; void *
0x140069be4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140069be9  lea     rax, [r14+1C0h]
0x140069bf0  mov     [rsp+2A8h+var_278], rax
0x140069bf5  mov     dword ptr [rax], 6
0x140069bfb  cmp     byte ptr [r14+199h], 0
0x140069c03  jz      loc_140069CD4
0x140069c09  mov     rcx, r14; this
0x140069c0c  call    ?DoTdxImportEnd@WorkerTaskMigrationTarget@@AEAAJXZ; WorkerTaskMigrationTarget::DoTdxImportEnd(void)
0x140069c11  mov     rcx, [rsp+2A8h]; this
0x140069c19  test    eax, eax
0x140069c1b  jns     short loc_140069C31
0x140069c1d  mov     r9d, eax; char *
0x140069c20  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x140069c27  mov     edx, 622h; void *
0x140069c2c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140069c31  mov     rax, [rsi]
0x140069c34  mov     rcx, [rax+400h]
0x140069c3b  add     rcx, 18h
0x140069c3f  mov     rax, [rcx]
0x140069c42  mov     rax, [rax]
0x140069c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140069c4a  xor     r9d, r9d
0x140069c4d  xor     r8d, r8d
0x140069c50  xor     edx, edx
0x140069c52  mov     rcx, rax
0x140069c55  call    cs:__imp_VidChangePartitionLifeState
0x140069c5c  nop     dword ptr [rax+rax+00h]
0x140069c61  mov     ebx, 41E2h
0x140069c66  test    eax, eax
0x140069c68  jnz     short loc_140069C83
0x140069c6a  mov     ecx, ebx
0x140069c6c  call    VmlIsDebugTraceEnabled
0x140069c71  test    eax, eax
0x140069c73  jz      short loc_140069C83
0x140069c75  lea     rdx, off_1402E4A18; "Failed to transition partition into sec"...
0x140069c7c  mov     ecx, ebx
0x140069c7e  call    VmlDebugTraceEx
0x140069c83  mov     rax, [rsi]
0x140069c86  mov     rcx, [rax+400h]
0x140069c8d  add     rcx, 18h
0x140069c91  mov     rax, [rcx]
0x140069c94  mov     rax, [rax]
0x140069c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140069c9c  xor     r9d, r9d
0x140069c9f  xor     r8d, r8d
0x140069ca2  lea     edx, [r9+2]
0x140069ca6  mov     rcx, rax
0x140069ca9  call    cs:__imp_VidChangePartitionLifeState
0x140069cb0  nop     dword ptr [rax+rax+00h]
0x140069cb5  test    eax, eax
0x140069cb7  jnz     short loc_140069CD9
0x140069cb9  mov     ecx, ebx
0x140069cbb  call    VmlIsDebugTraceEnabled
0x140069cc0  test    eax, eax
0x140069cc2  jz      short loc_140069CD9
0x140069cc4  lea     rdx, off_1402E4750; "Failed to transition partition into com"...
0x140069ccb  mov     ecx, ebx
0x140069ccd  call    VmlDebugTraceEx
0x140069cd2  jmp     short loc_140069CD9
0x140069cd4  mov     ebx, 41E2h
0x140069cd9  mov     [rsp+2A8h+var_170], 0
0x140069ce5  mov     [rsp+2A8h+var_168], 0
0x140069cf1  mov     [rsp+2A8h+var_17C], 1
0x140069cfc  mov     rcx, [rsi]
0x140069cff  add     rcx, 10h; this
0x140069d03  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x140069d08  mov     [rsp+2A8h+var_270], rax
0x140069d0d  lea     r8, [rsp+2A8h+var_270]
0x140069d12  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_RESTORE_PARTITION_START; EventDescriptor
0x140069d19  lea     rcx, [rsp+2A8h+var_188]; this
0x140069d21  call    ??$BeginOperation@PEBG@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@$$QEAPEBG@Z; Vml::VmPerfTraceOperation::BeginOperation<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const * &&)
0x140069d26  xor     r8d, r8d; bool
0x140069d29  mov     rdx, [r12]; struct VmRepository *
0x140069d2d  mov     rcx, [rsi]; this
0x140069d30  call    ?RestorePartitionStates@VirtualMachine@@QEAAJPEAVVmRepository@@_NI@Z; VirtualMachine::RestorePartitionStates(VmRepository *,bool,uint)
0x140069d35  mov     r13d, eax
0x140069d38  test    eax, eax
0x140069d3a  jns     short loc_140069D74
0x140069d3c  mov     ecx, ebx
0x140069d3e  call    VmlIsDebugTraceEnabled
0x140069d43  test    eax, eax
0x140069d45  jz      short loc_140069D58
0x140069d47  mov     r8d, r13d
0x140069d4a  lea     rdx, off_1402E4800; "Failed to restore partition state"
0x140069d51  mov     ecx, ebx
0x140069d53  call    VmlDebugTraceWithError
0x140069d58  mov     rcx, [rsp+2A8h]; this
0x140069d60  mov     r9d, r13d; char *
0x140069d63  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x140069d6a  mov     edx, 653h; void *
0x140069d6f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140069d74  mov     rax, [rsi]
0x140069d77  mov     r13, [rax+3E0h]
0x140069d7e  mov     rdx, [r13+0]
0x140069d82  mov     rcx, r13
0x140069d85  cmp     byte ptr [rax+0A69h], 0
0x140069d8c  jz      short loc_140069DA4
0x140069d8e  mov     rax, [rdx+208h]
0x140069d95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140069d9a  mov     [rsp+2A8h+var_198], rax
0x140069da2  jmp     short loc_140069DB8
0x140069da4  mov     rax, [rdx+200h]
0x140069dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140069db0  mov     [rsp+2A8h+var_198], rax
0x140069db8  mov     rax, [rsi]
0x140069dbb  mov     rax, [rax+420h]
0x140069dc2  mov     [rsp+2A8h+var_270], rax
0x140069dc7  mov     rax, [rax]
0x140069dca  mov     rax, [rax+18h]
0x140069dce  mov     [rsp+2A8h+var_228], rax
0x140069dd6  mov     rdx, [r13+0]
0x140069dda  mov     rcx, r13
0x140069ddd  mov     rax, [rdx+210h]
0x140069de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140069de9  xor     r9d, r9d
0x140069dec  mov     r8, rax
0x140069def  mov     rdx, [rsp+2A8h+var_198]
0x140069df7  mov     rcx, [rsp+2A8h+var_270]
0x140069dfc  mov     rax, [rsp+2A8h+var_228]
0x140069e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140069e09  mov     r13d, eax
0x140069e0c  test    eax, eax
0x140069e0e  jns     short loc_140069E48
0x140069e10  mov     ecx, ebx
0x140069e12  call    VmlIsDebugTraceEnabled
0x140069e17  test    eax, eax
0x140069e19  jz      short loc_140069E2C
0x140069e1b  mov     r8d, r13d
0x140069e1e  lea     rdx, off_1402E48D0; "Failed to restore saved state manager s"...
0x140069e25  mov     ecx, ebx
0x140069e27  call    VmlDebugTraceWithError
0x140069e2c  mov     rcx, [rsp+2A8h]; this
0x140069e34  mov     r9d, r13d; char *
0x140069e37  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x140069e3e  mov     edx, 669h; void *
0x140069e43  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140069e48  mov     rcx, [rsi]
0x140069e4b  add     rcx, 10h; this
0x140069e4f  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x140069e54  mov     [rsp+2A8h+var_270], rax
0x140069e59  lea     r8, [rsp+2A8h+var_270]; __int64
0x140069e5e  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_RESTORE_PARTITION_STOP; EventDescriptor
  ... truncated ...
```
