# WorkerTaskMigrationTarget::DoStateTransferSteps(__int64 &)

- ea: `0x14005ecc0`
- end: `0x14005f272`
- name: `?DoStateTransferSteps@WorkerTaskMigrationTarget@@AEAAJAEA_J@Z`
- size: `1458`
- prototype: `__int64 __fastcall(WorkerTaskMigrationTarget *__hidden this, __int64 *)`
- caller_count: `1`
- callee_count: `29`
- tags: `service_task, broker_com_uri`

## callers

- `0x140219680`

## callees

- `0x1400364a0`
- `0x14003d828`
- `0x140053de8`
- `0x140053f10`
- `0x1400544a8`
- `0x140058dfc`
- `0x14005ecc0`
- `0x14005f278`
- `0x14005f6dc`
- `0x14006b4b0`
- `0x140078628`
- `0x14008bdbc`
- `0x14009e464`
- `0x1400a13d8`
- `0x1400b2810`
- `0x1400b344c`
- `0x1400b5438`
- `0x1400d51bc`
- `0x1400debcc`
- `0x1400e96b0`
- `0x1400e983c`
- `0x1400fb5fc`
- `0x140102580`
- `0x14011ea40`
- `0x1401db2d0`
- `0x14021852c`
- `0x140218848`
- `0x14021ad74`
- `0x1402cb010`

## string_xrefs

- `0x14005edd0`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14005ee01`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14005ee29`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14005ee51`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14005ee8b`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14005eec6`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14005ef1b`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14005ef88`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14005efd1`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14005f029`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14005f08d`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14005f0ba`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14005f13a`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14005f177`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14005f1b1`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WorkerTaskMigrationTarget::DoStateTransferSteps(WorkerTaskMigrationTarget *this, __int64 *a2)
{
  __int64 *v2; // r12
  const struct _GUID *v4; // r15
  unsigned int v5; // r13d
  int v6; // esi
  int v7; // eax
  int v8; // eax
  int started; // eax
  SavedStateRepository **v10; // r14
  int Instance; // eax
  bool v12; // r8
  int v13; // esi
  unsigned int Integer; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  bool v18; // r8
  int v19; // eax
  int v20; // eax
  int v21; // eax
  const struct Vml::ExceptionTraceParameters *v22; // r8
  int v24; // [rsp+20h] [rbp-158h]
  SavedStateMigrationNetwork *v25; // [rsp+30h] [rbp-148h] BYREF
  struct _GUID v26; // [rsp+38h] [rbp-140h] BYREF
  __int64 *v27; // [rsp+48h] [rbp-130h]
  char *v28[2]; // [rsp+50h] [rbp-128h] BYREF
  _BYTE v29[12]; // [rsp+60h] [rbp-118h] BYREF
  int v30; // [rsp+6Ch] [rbp-10Ch]
  __int64 v31; // [rsp+78h] [rbp-100h]
  __int64 v32; // [rsp+80h] [rbp-F8h]
  _BYTE v33[72]; // [rsp+88h] [rbp-F0h] BYREF
  _BYTE v34[24]; // [rsp+D0h] [rbp-A8h] BYREF
  __int64 v35; // [rsp+E8h] [rbp-90h]
  __int64 v36; // [rsp+F0h] [rbp-88h]
  _BYTE v37[72]; // [rsp+F8h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  v2 = a2;
  v27 = a2;
  v26 = 0;
  v4 = (const struct _GUID *)((char *)this + 412);
  Vml::VmPerfTraceOperation::VmPerfTraceOperation(
    (Vml::VmPerfTraceOperation *)v34,
    (struct Vml::VmPerfTraceComponent *)&g_MigrationPerfTrace,
    (const struct _GUID *)((char *)this + 412),
    &v26);
  v26 = 0;
  Vml::VmPerfTraceOperation::VmPerfTraceOperation(
    (Vml::VmPerfTraceOperation *)v29,
    (struct Vml::VmPerfTraceComponent *)&g_MigrationPerfTrace,
    v4,
    &v26);
  v35 = *v2;
  Vml::VmPerfTraceOperation::BeginOperation<>((Vml::VmPerfTraceOperation *)v34, &VMWP_PERF_MIGRATION_TARGET_MOVE_START);
  v31 = *v2;
  Vml::VmPerfTraceOperation::BeginOperation<>(
    (Vml::VmPerfTraceOperation *)v29,
    &VMWP_PERF_MIGRATION_TARGET_MOVE_RECEIVE_STATE_START);
  v5 = 0;
  try
  {
    v25 = 0;
    v6 = SavedStateMigrationNetwork::CreateInstance(
           *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 1416LL) + 376LL),
           &v25);
    if ( v6 < 0 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16866) )
        VmlDebugTraceWithError(16866, &off_1402E4910, (unsigned int)v6);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4AA,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v6,
        v24);
    }
    if ( *((_BYTE *)this + 409) )
    {
      v7 = WorkerTaskMigrationTarget::DoTdxMutableStateImport(this);
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4B0,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v7,
          v24);
      v8 = WorkerTaskMigrationTarget::DoTdxVpStateImport(this);
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4B1,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v8,
          v24);
      started = WorkerTaskMigrationTarget::DoTdxStartTokenImport(this);
      if ( started < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4B2,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)started,
          v24);
    }
    v10 = (SavedStateRepository **)((char *)this + 568);
    Instance = SavedStateRepository::CreateInstance(v4, v25, (struct SavedStateRepository **)this + 71);
    if ( Instance < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4B6,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)Instance,
        v24);
    *(_OWORD *)v28 = 0;
    VmSavedStateStorageAutoLock::VmSavedStateStorageAutoLock((VmSavedStateStorageAutoLock *)v28, v25, v12);
    if ( SLODWORD(v28[1]) < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4BA,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)LODWORD(v28[1]),
        v24);
    v13 = SavedStateMigrationNetwork::Import(v25, *((struct VmMigrationConnection **)this + 55));
    if ( v13 < 0 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16866) )
        VmlDebugTraceWithError(16866, &off_1402E4738, (unsigned int)v13);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4C2,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v13,
        v24);
    }
    VmSavedStateStorageAutoLock::~VmSavedStateStorageAutoLock((VmSavedStateStorageAutoLock *)v28);
    if ( (*((_BYTE *)this + 480) & 0x20) != 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 57) + 72LL))(*((_QWORD *)this + 57));
    v28[0] = 0;
    v26 = 0;
    VmRepositoryAutoLock::VmRepositoryAutoLock(&v26, *v10, 1);
    if ( *(int *)v26.Data4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4D6,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)*(unsigned int *)v26.Data4,
        v24);
    v28[0] = 0;
    Integer = SavedStateRepository::ReadInteger(*v10, L"/savedVM/migration_run_state", (__int64 *)v28);
    if ( (int)(Integer + 0x80000000) >= 0 && Integer != -2147188715 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4DF,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)Integer,
        v24);
    *(_DWORD *)(*((_QWORD *)this + 54) + 88LL) = v28[0] == (char *)1;
    VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)&v26);
    Vml::VmPerfTraceOperation::EndOperation<>(
      (Vml::VmPerfTraceOperation *)v29,
      &VMWP_PERF_MIGRATION_TARGET_MOVE_RECEIVE_STATE_STOP);
    v15 = WorkerTaskMigrationTarget::CheckCancel(this);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4EC,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v15,
        v24);
    if ( (*((_BYTE *)this + 480) & 1) != 0 && !*((_DWORD *)this + 122) )
    {
      v31 = 0;
      v32 = 0;
      v30 = 1;
      Vml::VmPerfTraceOperation::BeginOperation<>(
        (Vml::VmPerfTraceOperation *)v29,
        &VMWP_PERF_MIGRATION_TARGET_MOVE_CHECKSUMS_START);
      v16 = WorkerTaskMigrationTarget::VerifyRamChecksums(this);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x502,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v16,
          v24);
      v17 = WorkerTaskMigrationTarget::VerifyRuntimeStateChecksum(this, v25);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x505,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v17,
          v24);
      Vml::VmPerfTraceOperation::EndOperation<>(
        (Vml::VmPerfTraceOperation *)v29,
        &VMWP_PERF_MIGRATION_TARGET_MOVE_CHECKSUMS_STOP);
    }
    if ( (*((_BYTE *)this + 480) & 0x20) == 0 )
    {
      LODWORD(v28[0]) = 0;
      v31 = 0;
      v32 = 0;
      v30 = 1;
      Vml::VmPerfTraceOperation::BeginOperation<>(
        (Vml::VmPerfTraceOperation *)v29,
        &VMWP_PERF_MIGRATION_TARGET_MOVE_WAIT_OWNER_START);
      v19 = MigrationManager::WaitForFinalStateTransition(
              *((MigrationManager **)this + 54),
              0x12Cu,
              v18,
              (enum MigrationManager::FINAL_STATE_TRANSITION *)v28,
              0);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x51C,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v19,
          v24);
      Vml::VmPerfTraceOperation::EndOperation<>(
        (Vml::VmPerfTraceOperation *)v29,
        &VMWP_PERF_MIGRATION_TARGET_MOVE_WAIT_OWNER_STOP);
      v20 = WorkerTaskMigrationTarget::TransitionWorkerProcess(this, LODWORD(v28[0]));
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x523,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v20,
          v24);
    }
    v21 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 1072LL) + 240LL))(*(_QWORD *)(*((_QWORD *)this + 2) + 1072LL));
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x529,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v21,
        v24);
    if ( (int)WorkerTaskMigrationTarget::IndicateStatusToSource(this, 8) < 0
      && (unsigned int)VmlIsDebugTraceEnabled(33250) )
    {
      VmlDebugTraceEx(33250, &off_1402E4818);
    }
    Vml::VmReferencePtr<IVmMigrationTransport,Vml::VmUserReferenceTraits>::~VmReferencePtr<IVmMigrationTransport,Vml::VmUserReferenceTraits>(&v25);
  }
  catch ( ... )
  {
    LODWORD(v28[0]) = Vml::GetHResultFromThrownExceptionAndTrace((Vml *)0x41E2, (unsigned __int16)&off_1402E4768, v22);
    v5 = (unsigned int)v28[0];
    v2 = v27;
  }
  Vml::VmPerfTraceOperation::EndOperation<>((Vml::VmPerfTraceOperation *)v34, &VMWP_PERF_MIGRATION_TARGET_MOVE_STOP);
  *v2 = v36;
  std::wstring::_Tidy_deallocate(v33);
  std::wstring::_Tidy_deallocate(v37);
  return v5;
}

```

## disassembly

```asm
0x14005ecc0  mov     [rsp+arg_10], rsi
0x14005ecc5  push    rdi
0x14005ecc6  push    r12
0x14005ecc8  push    r13
0x14005ecca  push    r14
0x14005eccc  push    r15
0x14005ecce  sub     rsp, 150h
0x14005ecd5  mov     rax, cs:__security_cookie
0x14005ecdc  xor     rax, rsp
0x14005ecdf  mov     [rsp+178h+var_38], rax
0x14005ece7  mov     r12, rdx
0x14005ecea  mov     rdi, rcx
0x14005eced  mov     [rsp+178h+var_130], rdx
0x14005ecf2  xorps   xmm0, xmm0
0x14005ecf5  movups  xmmword ptr [rsp+178h+var_140.Data1], xmm0
0x14005ecfa  lea     r15, [rcx+19Ch]
0x14005ed01  lea     r9, [rsp+178h+var_140]; struct _GUID *
0x14005ed06  mov     r8, r15; struct _GUID *
0x14005ed09  lea     rdx, ?g_MigrationPerfTrace@@3VVmPerfTraceComponent@Vml@@A; struct Vml::VmPerfTraceComponent *
0x14005ed10  lea     rcx, [rsp+178h+var_A8]; this
0x14005ed18  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x14005ed1d  nop
0x14005ed1e  xorps   xmm0, xmm0
0x14005ed21  movups  xmmword ptr [rsp+178h+var_140.Data1], xmm0
0x14005ed26  lea     r9, [rsp+178h+var_140]; struct _GUID *
0x14005ed2b  mov     r8, r15; struct _GUID *
0x14005ed2e  lea     rdx, ?g_MigrationPerfTrace@@3VVmPerfTraceComponent@Vml@@A; struct Vml::VmPerfTraceComponent *
0x14005ed35  lea     rcx, [rsp+178h+var_118]; this
0x14005ed3a  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x14005ed3f  nop
0x14005ed40  mov     rax, [r12]
0x14005ed44  mov     [rsp+178h+var_90], rax
0x14005ed4c  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_START; EventDescriptor
0x14005ed53  lea     rcx, [rsp+178h+var_A8]; this
0x14005ed5b  call    ??$BeginOperation@$$V@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@@Z; Vml::VmPerfTraceOperation::BeginOperation<>(_EVENT_DESCRIPTOR const &)
0x14005ed60  mov     rax, [r12]
0x14005ed64  mov     [rsp+178h+var_100], rax
0x14005ed69  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_RECEIVE_STATE_START; EventDescriptor
0x14005ed70  lea     rcx, [rsp+178h+var_118]; this
0x14005ed75  call    ??$BeginOperation@$$V@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@@Z; Vml::VmPerfTraceOperation::BeginOperation<>(_EVENT_DESCRIPTOR const &)
0x14005ed7a  xor     r13d, r13d
0x14005ed7d  mov     [rsp+178h+var_148], r13
0x14005ed82  mov     rax, [rdi+10h]
0x14005ed86  mov     rcx, [rax+588h]
0x14005ed8d  lea     rdx, [rsp+178h+var_148]; struct SavedStateMigrationNetwork **
0x14005ed92  mov     ecx, [rcx+178h]; unsigned int
0x14005ed98  call    ?CreateInstance@SavedStateMigrationNetwork@@SAJIPEAPEAV1@@Z; SavedStateMigrationNetwork::CreateInstance(uint,SavedStateMigrationNetwork * *)
0x14005ed9d  mov     esi, eax
0x14005ed9f  test    eax, eax
0x14005eda1  jns     short loc_14005EDE1
0x14005eda3  mov     ecx, 41E2h
0x14005eda8  call    VmlIsDebugTraceEnabled
0x14005edad  test    eax, eax
0x14005edaf  jz      short loc_14005EDC5
0x14005edb1  mov     r8d, esi
0x14005edb4  lea     rdx, off_1402E4910; "Failed to create runtime state storage."
0x14005edbb  mov     ecx, 41E2h
0x14005edc0  call    VmlDebugTraceWithError
0x14005edc5  mov     rcx, [rsp+178h]; this
0x14005edcd  mov     r9d, esi; char *
0x14005edd0  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14005edd7  mov     edx, 4AAh; void *
0x14005eddc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005ede1  cmp     byte ptr [rdi+199h], 0
0x14005ede8  jz      short loc_14005EE62
0x14005edea  mov     rcx, rdi; this
0x14005eded  call    ?DoTdxMutableStateImport@WorkerTaskMigrationTarget@@AEAAJXZ; WorkerTaskMigrationTarget::DoTdxMutableStateImport(void)
0x14005edf2  mov     rcx, [rsp+178h]; this
0x14005edfa  test    eax, eax
0x14005edfc  jns     short loc_14005EE12
0x14005edfe  mov     r9d, eax; char *
0x14005ee01  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14005ee08  mov     edx, 4B0h; void *
0x14005ee0d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005ee12  mov     rcx, rdi; this
0x14005ee15  call    ?DoTdxVpStateImport@WorkerTaskMigrationTarget@@AEAAJXZ; WorkerTaskMigrationTarget::DoTdxVpStateImport(void)
0x14005ee1a  mov     rcx, [rsp+178h]; this
0x14005ee22  test    eax, eax
0x14005ee24  jns     short loc_14005EE3A
0x14005ee26  mov     r9d, eax; char *
0x14005ee29  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14005ee30  mov     edx, 4B1h; void *
0x14005ee35  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005ee3a  mov     rcx, rdi; this
0x14005ee3d  call    ?DoTdxStartTokenImport@WorkerTaskMigrationTarget@@AEAAJXZ; WorkerTaskMigrationTarget::DoTdxStartTokenImport(void)
0x14005ee42  mov     rcx, [rsp+178h]; this
0x14005ee4a  test    eax, eax
0x14005ee4c  jns     short loc_14005EE62
0x14005ee4e  mov     r9d, eax; char *
0x14005ee51  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14005ee58  mov     edx, 4B2h; void *
0x14005ee5d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005ee62  lea     r14, [rdi+238h]
0x14005ee69  mov     r8, r14; struct SavedStateRepository **
0x14005ee6c  mov     rdx, [rsp+178h+var_148]; struct ISavedStateStorage *
0x14005ee71  mov     rcx, r15; struct _GUID *
0x14005ee74  call    ?CreateInstance@SavedStateRepository@@SAJAEBU_GUID@@PEAVISavedStateStorage@@PEAPEAV1@@Z; SavedStateRepository::CreateInstance(_GUID const &,ISavedStateStorage *,SavedStateRepository * *)
0x14005ee79  mov     rcx, [rsp+178h]; this
0x14005ee81  xor     r15d, r15d
0x14005ee84  test    eax, eax
0x14005ee86  jns     short loc_14005EE9C
0x14005ee88  mov     r9d, eax; char *
0x14005ee8b  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14005ee92  mov     edx, 4B6h; void *
0x14005ee97  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005ee9c  xorps   xmm0, xmm0
0x14005ee9f  movups  xmmword ptr [rsp+178h+var_128], xmm0
0x14005eea4  mov     rdx, [rsp+178h+var_148]; struct SavedStateStorage *
0x14005eea9  lea     rcx, [rsp+178h+var_128]; this
0x14005eeae  call    ??0VmSavedStateStorageAutoLock@@QEAA@PEAVSavedStateStorage@@_N@Z; VmSavedStateStorageAutoLock::VmSavedStateStorageAutoLock(SavedStateStorage *,bool)
0x14005eeb3  nop
0x14005eeb4  mov     r9d, dword ptr [rsp+178h+var_128+8]; char *
0x14005eeb9  mov     rcx, [rsp+178h]; this
0x14005eec1  test    r9d, r9d
0x14005eec4  jns     short loc_14005EED7
0x14005eec6  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14005eecd  mov     edx, 4BAh; void *
0x14005eed2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005eed7  mov     rdx, [rdi+1B8h]; struct VmMigrationConnection *
0x14005eede  mov     rcx, [rsp+178h+var_148]; this
0x14005eee3  call    ?Import@SavedStateMigrationNetwork@@QEAAJPEAVVmMigrationConnection@@@Z; SavedStateMigrationNetwork::Import(VmMigrationConnection *)
0x14005eee8  mov     esi, eax
0x14005eeea  test    eax, eax
0x14005eeec  jns     short loc_14005EF2D
0x14005eeee  mov     ecx, 41E2h
0x14005eef3  call    VmlIsDebugTraceEnabled
0x14005eef8  test    eax, eax
0x14005eefa  jz      short loc_14005EF10
0x14005eefc  mov     r8d, esi
0x14005eeff  lea     rdx, off_1402E4738; "Failed to receive the VM runtime-state "...
0x14005ef06  mov     ecx, 41E2h
0x14005ef0b  call    VmlDebugTraceWithError
0x14005ef10  mov     rcx, [rsp+178h]; this
0x14005ef18  mov     r9d, esi; char *
0x14005ef1b  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14005ef22  mov     edx, 4C2h; void *
0x14005ef27  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005ef2d  lea     rcx, [rsp+178h+var_128]; this
0x14005ef32  call    ??1VmSavedStateStorageAutoLock@@QEAA@XZ; VmSavedStateStorageAutoLock::~VmSavedStateStorageAutoLock(void)
0x14005ef37  test    byte ptr [rdi+1E0h], 20h
0x14005ef3e  jz      short loc_14005EF53
0x14005ef40  mov     rcx, [rdi+1C8h]
0x14005ef47  mov     rax, [rcx]
0x14005ef4a  mov     rax, [rax+48h]
0x14005ef4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005ef53  mov     [rsp+178h+var_128], r15
0x14005ef58  xorps   xmm0, xmm0
0x14005ef5b  movups  xmmword ptr [rsp+178h+var_140.Data1], xmm0
0x14005ef60  mov     esi, 1
0x14005ef65  mov     r8d, esi
0x14005ef68  mov     rdx, [r14]
0x14005ef6b  lea     rcx, [rsp+178h+var_140]
0x14005ef70  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x14005ef75  nop
0x14005ef76  mov     r9d, dword ptr [rsp+178h+var_140.Data4]; char *
0x14005ef7b  mov     rcx, [rsp+178h]; this
0x14005ef83  test    r9d, r9d
0x14005ef86  jns     short loc_14005EF99
0x14005ef88  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14005ef8f  mov     edx, 4D6h; void *
0x14005ef94  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005ef99  mov     [rsp+178h+var_128], r15
0x14005ef9e  lea     r8, [rsp+178h+var_128]; __int64 *
0x14005efa3  lea     rdx, ?VM_MIGRATION_RUN_STATE_XPATH@@3QBGB; "/savedVM/migration_run_state"
0x14005efaa  mov     rcx, [r14]; this
0x14005efad  call    ?ReadInteger@SavedStateRepository@@UEBAJPEBGAEA_J@Z; SavedStateRepository::ReadInteger(ushort const *,__int64 &)
0x14005efb2  mov     r9d, eax; char *
0x14005efb5  mov     ecx, 80000000h
0x14005efba  add     eax, ecx
0x14005efbc  test    ecx, eax
0x14005efbe  jnz     short loc_14005EFE2
0x14005efc0  cmp     r9d, 80048015h
0x14005efc7  jz      short loc_14005EFE2
0x14005efc9  mov     rcx, [rsp+178h]; this
0x14005efd1  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14005efd8  mov     edx, 4DFh; void *
0x14005efdd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005efe2  mov     rcx, [rdi+1B0h]
0x14005efe9  mov     eax, r15d
0x14005efec  cmp     [rsp+178h+var_128], rsi
0x14005eff1  setz    al
0x14005eff4  mov     [rcx+58h], eax
0x14005eff7  lea     rcx, [rsp+178h+var_140]; this
0x14005effc  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x14005f001  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_RECEIVE_STATE_STOP; EventDescriptor
0x14005f008  lea     rcx, [rsp+178h+var_118]; this
0x14005f00d  call    ??$EndOperation@$$V@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@@Z; Vml::VmPerfTraceOperation::EndOperation<>(_EVENT_DESCRIPTOR const &)
0x14005f012  mov     rcx, rdi; this
0x14005f015  call    ?CheckCancel@WorkerTaskMigrationTarget@@AEAAJXZ; WorkerTaskMigrationTarget::CheckCancel(void)
0x14005f01a  mov     rcx, [rsp+178h]; this
0x14005f022  test    eax, eax
0x14005f024  jns     short loc_14005F03A
0x14005f026  mov     r9d, eax; char *
0x14005f029  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14005f030  mov     edx, 4ECh; void *
0x14005f035  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005f03a  test    [rdi+1E0h], sil
0x14005f041  jz      loc_14005F0DC
0x14005f047  cmp     [rdi+1E8h], r15d
0x14005f04e  jnz     loc_14005F0DC
0x14005f054  mov     [rsp+178h+var_100], r15
0x14005f059  mov     [rsp+178h+var_F8], r15
0x14005f061  mov     [rsp+178h+var_10C], esi
0x14005f065  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_CHECKSUMS_START; EventDescriptor
0x14005f06c  lea     rcx, [rsp+178h+var_118]; this
0x14005f071  call    ??$BeginOperation@$$V@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@@Z; Vml::VmPerfTraceOperation::BeginOperation<>(_EVENT_DESCRIPTOR const &)
0x14005f076  mov     rcx, rdi; this
0x14005f079  call    ?VerifyRamChecksums@WorkerTaskMigrationTarget@@AEAAJXZ; WorkerTaskMigrationTarget::VerifyRamChecksums(void)
0x14005f07e  mov     rcx, [rsp+178h]; this
0x14005f086  test    eax, eax
0x14005f088  jns     short loc_14005F09E
0x14005f08a  mov     r9d, eax; char *
0x14005f08d  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14005f094  mov     edx, 502h; void *
0x14005f099  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005f09e  mov     rdx, [rsp+178h+var_148]; struct SavedStateMigrationNetwork *
0x14005f0a3  mov     rcx, rdi; this
0x14005f0a6  call    ?VerifyRuntimeStateChecksum@WorkerTaskMigrationTarget@@AEAAJPEAVSavedStateMigrationNetwork@@@Z; WorkerTaskMigrationTarget::VerifyRuntimeStateChecksum(SavedStateMigrationNetwork *)
0x14005f0ab  mov     rcx, [rsp+178h]; this
0x14005f0b3  test    eax, eax
0x14005f0b5  jns     short loc_14005F0CB
0x14005f0b7  mov     r9d, eax; char *
0x14005f0ba  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14005f0c1  mov     edx, 505h; void *
0x14005f0c6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005f0cb  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_CHECKSUMS_STOP; EventDescriptor
0x14005f0d2  lea     rcx, [rsp+178h+var_118]; this
0x14005f0d7  call    ??$EndOperation@$$V@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@@Z; Vml::VmPerfTraceOperation::EndOperation<>(_EVENT_DESCRIPTOR const &)
0x14005f0dc  test    byte ptr [rdi+1E0h], 20h
0x14005f0e3  jnz     loc_14005F188
0x14005f0e9  mov     dword ptr [rsp+178h+var_128], r15d
0x14005f0ee  mov     [rsp+178h+var_100], r15
0x14005f0f3  mov     [rsp+178h+var_F8], r15
0x14005f0fb  mov     [rsp+178h+var_10C], esi
0x14005f0ff  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_WAIT_OWNER_START; EventDescriptor
0x14005f106  lea     rcx, [rsp+178h+var_118]; this
0x14005f10b  call    ??$BeginOperation@$$V@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@@Z; Vml::VmPerfTraceOperation::BeginOperation<>(_EVENT_DESCRIPTOR const &)
0x14005f110  mov     qword ptr [rsp+178h+var_158], r15; int
0x14005f115  lea     r9, [rsp+178h+var_128]; enum MigrationManager::FINAL_STATE_TRANSITION *
0x14005f11a  mov     edx, 12Ch; unsigned int
0x14005f11f  mov     rcx, [rdi+1B0h]; this
0x14005f126  call    ?WaitForFinalStateTransition@MigrationManager@@QEAAJI_NAEAW4FINAL_STATE_TRANSITION@1@PEAPEAUIVmSimpleTask@@@Z; MigrationManager::WaitForFinalStateTransition(uint,bool,MigrationManager::FINAL_STATE_TRANSITION &,IVmSimpleTask * *)
0x14005f12b  mov     rcx, [rsp+178h]; this
0x14005f133  test    eax, eax
0x14005f135  jns     short loc_14005F14B
0x14005f137  mov     r9d, eax; char *
0x14005f13a  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14005f141  mov     edx, 51Ch; void *
0x14005f146  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005f14b  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_WAIT_OWNER_STOP; EventDescriptor
0x14005f152  lea     rcx, [rsp+178h+var_118]; this
0x14005f157  call    ??$EndOperation@$$V@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@@Z; Vml::VmPerfTraceOperation::EndOperation<>(_EVENT_DESCRIPTOR const &)
0x14005f15c  mov     edx, dword ptr [rsp+178h+var_128]
0x14005f160  mov     rcx, rdi
0x14005f163  call    ?TransitionWorkerProcess@WorkerTaskMigrationTarget@@AEAAJW4FINAL_STATE_TRANSITION@MigrationManager@@@Z; WorkerTaskMigrationTarget::TransitionWorkerProcess(MigrationManager::FINAL_STATE_TRANSITION)
0x14005f168  mov     rcx, [rsp+178h]; this
0x14005f170  test    eax, eax
0x14005f172  jns     short loc_14005F188
0x14005f174  mov     r9d, eax; char *
0x14005f177  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14005f17e  mov     edx, 523h; void *
0x14005f183  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005f188  mov     rax, [rdi+10h]
0x14005f18c  mov     rcx, [rax+430h]
0x14005f193  mov     rax, [rcx]
0x14005f196  mov     rax, [rax+0F0h]
0x14005f19d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005f1a2  mov     rcx, [rsp+178h]; this
0x14005f1aa  test    eax, eax
0x14005f1ac  jns     short loc_14005F1C2
0x14005f1ae  mov     r9d, eax; char *
0x14005f1b1  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14005f1b8  mov     edx, 529h; void *
0x14005f1bd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005f1c2  mov     edx, 8
0x14005f1c7  mov     rcx, rdi
0x14005f1ca  call    ?IndicateStatusToSource@WorkerTaskMigrationTarget@@AEAAJW4MESSAGE_SEQUENCE_TYPE@VmMigrationConnection@@KJ@Z; WorkerTaskMigrationTarget::IndicateStatusToSource(VmMigrationConnection::MESSAGE_SEQUENCE_TYPE,ulong,long)
0x14005f1cf  test    eax, eax
0x14005f1d1  jns     short loc_14005F1F3
0x14005f1d3  mov     ecx, 81E2h
0x14005f1d8  call    VmlIsDebugTraceEnabled
0x14005f1dd  test    eax, eax
0x14005f1df  jz      short loc_14005F1F3
0x14005f1e1  lea     rdx, off_1402E4818; "Failed to signal migration completion t"...
0x14005f1e8  mov     ecx, 81E2h
0x14005f1ed  call    VmlDebugTraceEx
0x14005f1f2  nop
0x14005f1f3  lea     rcx, [rsp+178h+var_148]
0x14005f1f8  call    ??1?$VmReferencePtr@VIVmMigrationTransport@@VVmUserReferenceTraits@Vml@@@Vml@@QEAA@XZ; Vml::VmReferencePtr<IVmMigrationTransport,Vml::VmUserReferenceTraits>::~VmReferencePtr<IVmMigrationTransport,Vml::VmUserReferenceTraits>(void)
0x14005f1fd  nop
0x14005f1fe  jmp     short loc_14005F20A
0x14005f200  mov     r13d, dword ptr [rsp+178h+var_128]
0x14005f205  mov     r12, [rsp+178h+var_130]
0x14005f20a  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_STOP; EventDescriptor
0x14005f211  lea     rcx, [rsp+178h+var_A8]; this
0x14005f219  call    ??$EndOperation@$$V@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@@Z; Vml::VmPerfTraceOperation::EndOperation<>(_EVENT_DESCRIPTOR const &)
0x14005f21e  mov     rcx, [rsp+178h+var_88]
0x14005f226  mov     [r12], rcx
0x14005f22a  lea     rcx, [rsp+178h+var_F0]
0x14005f232  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
  ... truncated ...
```
