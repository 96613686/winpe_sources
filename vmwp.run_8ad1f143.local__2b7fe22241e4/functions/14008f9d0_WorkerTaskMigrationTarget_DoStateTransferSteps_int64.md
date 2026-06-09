# WorkerTaskMigrationTarget::DoStateTransferSteps(__int64 &)

- ea: `0x14008f9d0`
- end: `0x14008ff82`
- name: `?DoStateTransferSteps@WorkerTaskMigrationTarget@@AEAAJAEA_J@Z`
- size: `1458`
- prototype: `__int64 __fastcall(WorkerTaskMigrationTarget *__hidden this, __int64 *)`
- caller_count: `1`
- callee_count: `29`
- tags: `service_task, broker_com_uri`

## callers

- `0x140091500`

## callees

- `0x140031ca8`
- `0x140042260`
- `0x1400544a8`
- `0x1400545d0`
- `0x14005497c`
- `0x14006af58`
- `0x14007a74c`
- `0x140088428`
- `0x1400890a4`
- `0x14008f9d0`
- `0x14008ff88`
- `0x1400903b0`
- `0x140090460`
- `0x140092e58`
- `0x1400930b8`
- `0x1400a0874`
- `0x1400a0a00`
- `0x1400a0ed0`
- `0x1400a22b4`
- `0x1400ccc60`
- `0x1400edc20`
- `0x14010ac00`
- `0x140111090`
- `0x140117cc8`
- `0x14012fa14`
- `0x140132960`
- `0x1401eb8e0`
- `0x1402239c4`
- `0x1402c2010`

## string_xrefs

- `0x14008fae0`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008fb11`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008fb39`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008fb61`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008fb9b`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008fbd6`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008fc2b`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008fc98`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008fce1`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008fd39`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008fd9d`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008fdca`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008fe4a`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008fe87`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008fec1`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`

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
        VmlDebugTraceWithError(16866, &off_1402DB3E0, (unsigned int)v6);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x47B,
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
          (void *)0x481,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v7,
          v24);
      v8 = WorkerTaskMigrationTarget::DoTdxVpStateImport(this);
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x482,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v8,
          v24);
      started = WorkerTaskMigrationTarget::DoTdxStartTokenImport(this);
      if ( started < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x483,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)started,
          v24);
    }
    v10 = (SavedStateRepository **)((char *)this + 568);
    Instance = SavedStateRepository::CreateInstance(v4, v25, (struct SavedStateRepository **)this + 71);
    if ( Instance < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x487,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)Instance,
        v24);
    *(_OWORD *)v28 = 0;
    VmSavedStateStorageAutoLock::VmSavedStateStorageAutoLock((VmSavedStateStorageAutoLock *)v28, v25, v12);
    if ( SLODWORD(v28[1]) < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x48B,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)LODWORD(v28[1]),
        v24);
    v13 = SavedStateMigrationNetwork::Import(v25, *((struct VmMigrationConnection **)this + 55));
    if ( v13 < 0 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16866) )
        VmlDebugTraceWithError(16866, &off_1402DB208, (unsigned int)v13);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x493,
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
        (void *)0x4A7,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)*(unsigned int *)v26.Data4,
        v24);
    v28[0] = 0;
    Integer = SavedStateRepository::ReadInteger(*v10, L"/savedVM/migration_run_state", (__int64 *)v28);
    if ( (int)(Integer + 0x80000000) >= 0 && Integer != -2147188715 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4B0,
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
        (void *)0x4BD,
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
          (void *)0x4D3,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v16,
          v24);
      v17 = WorkerTaskMigrationTarget::VerifyRuntimeStateChecksum(this, v25);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4D6,
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
          (void *)0x4ED,
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
          (void *)0x4F4,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v20,
          v24);
    }
    v21 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 1072LL) + 240LL))(*(_QWORD *)(*((_QWORD *)this + 2) + 1072LL));
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4FA,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v21,
        v24);
    if ( (int)WorkerTaskMigrationTarget::IndicateStatusToSource(this, 8) < 0
      && (unsigned int)VmlIsDebugTraceEnabled(33250) )
    {
      VmlDebugTraceEx(33250, &off_1402DB2D0);
    }
    Vml::VmReferencePtr<IVmMigrationTransport,Vml::VmUserReferenceTraits>::~VmReferencePtr<IVmMigrationTransport,Vml::VmUserReferenceTraits>(&v25);
  }
  catch ( ... )
  {
    LODWORD(v28[0]) = Vml::GetHResultFromThrownExceptionAndTrace((Vml *)0x41E2, (unsigned __int16)&off_1402DB238, v22);
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
0x14008f9d0  mov     [rsp+arg_10], rsi
0x14008f9d5  push    rdi
0x14008f9d6  push    r12
0x14008f9d8  push    r13
0x14008f9da  push    r14
0x14008f9dc  push    r15
0x14008f9de  sub     rsp, 150h
0x14008f9e5  mov     rax, cs:__security_cookie
0x14008f9ec  xor     rax, rsp
0x14008f9ef  mov     [rsp+178h+var_38], rax
0x14008f9f7  mov     r12, rdx
0x14008f9fa  mov     rdi, rcx
0x14008f9fd  mov     [rsp+178h+var_130], rdx
0x14008fa02  xorps   xmm0, xmm0
0x14008fa05  movups  xmmword ptr [rsp+178h+var_140.Data1], xmm0
0x14008fa0a  lea     r15, [rcx+19Ch]
0x14008fa11  lea     r9, [rsp+178h+var_140]; struct _GUID *
0x14008fa16  mov     r8, r15; struct _GUID *
0x14008fa19  lea     rdx, ?g_MigrationPerfTrace@@3VVmPerfTraceComponent@Vml@@A; struct Vml::VmPerfTraceComponent *
0x14008fa20  lea     rcx, [rsp+178h+var_A8]; this
0x14008fa28  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x14008fa2d  nop
0x14008fa2e  xorps   xmm0, xmm0
0x14008fa31  movups  xmmword ptr [rsp+178h+var_140.Data1], xmm0
0x14008fa36  lea     r9, [rsp+178h+var_140]; struct _GUID *
0x14008fa3b  mov     r8, r15; struct _GUID *
0x14008fa3e  lea     rdx, ?g_MigrationPerfTrace@@3VVmPerfTraceComponent@Vml@@A; struct Vml::VmPerfTraceComponent *
0x14008fa45  lea     rcx, [rsp+178h+var_118]; this
0x14008fa4a  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x14008fa4f  nop
0x14008fa50  mov     rax, [r12]
0x14008fa54  mov     [rsp+178h+var_90], rax
0x14008fa5c  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_START; EventDescriptor
0x14008fa63  lea     rcx, [rsp+178h+var_A8]; this
0x14008fa6b  call    ??$BeginOperation@$$V@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@@Z; Vml::VmPerfTraceOperation::BeginOperation<>(_EVENT_DESCRIPTOR const &)
0x14008fa70  mov     rax, [r12]
0x14008fa74  mov     [rsp+178h+var_100], rax
0x14008fa79  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_RECEIVE_STATE_START; EventDescriptor
0x14008fa80  lea     rcx, [rsp+178h+var_118]; this
0x14008fa85  call    ??$BeginOperation@$$V@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@@Z; Vml::VmPerfTraceOperation::BeginOperation<>(_EVENT_DESCRIPTOR const &)
0x14008fa8a  xor     r13d, r13d
0x14008fa8d  mov     [rsp+178h+var_148], r13
0x14008fa92  mov     rax, [rdi+10h]
0x14008fa96  mov     rcx, [rax+588h]
0x14008fa9d  lea     rdx, [rsp+178h+var_148]; struct SavedStateMigrationNetwork **
0x14008faa2  mov     ecx, [rcx+178h]; unsigned int
0x14008faa8  call    ?CreateInstance@SavedStateMigrationNetwork@@SAJIPEAPEAV1@@Z; SavedStateMigrationNetwork::CreateInstance(uint,SavedStateMigrationNetwork * *)
0x14008faad  mov     esi, eax
0x14008faaf  test    eax, eax
0x14008fab1  jns     short loc_14008FAF1
0x14008fab3  mov     ecx, 41E2h
0x14008fab8  call    VmlIsDebugTraceEnabled
0x14008fabd  test    eax, eax
0x14008fabf  jz      short loc_14008FAD5
0x14008fac1  mov     r8d, esi
0x14008fac4  lea     rdx, off_1402DB3E0; "Failed to create runtime state storage."
0x14008facb  mov     ecx, 41E2h
0x14008fad0  call    VmlDebugTraceWithError
0x14008fad5  mov     rcx, [rsp+178h]; this
0x14008fadd  mov     r9d, esi; char *
0x14008fae0  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fae7  mov     edx, 47Bh; void *
0x14008faec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008faf1  cmp     byte ptr [rdi+199h], 0
0x14008faf8  jz      short loc_14008FB72
0x14008fafa  mov     rcx, rdi; this
0x14008fafd  call    ?DoTdxMutableStateImport@WorkerTaskMigrationTarget@@AEAAJXZ; WorkerTaskMigrationTarget::DoTdxMutableStateImport(void)
0x14008fb02  mov     rcx, [rsp+178h]; this
0x14008fb0a  test    eax, eax
0x14008fb0c  jns     short loc_14008FB22
0x14008fb0e  mov     r9d, eax; char *
0x14008fb11  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fb18  mov     edx, 481h; void *
0x14008fb1d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008fb22  mov     rcx, rdi; this
0x14008fb25  call    ?DoTdxVpStateImport@WorkerTaskMigrationTarget@@AEAAJXZ; WorkerTaskMigrationTarget::DoTdxVpStateImport(void)
0x14008fb2a  mov     rcx, [rsp+178h]; this
0x14008fb32  test    eax, eax
0x14008fb34  jns     short loc_14008FB4A
0x14008fb36  mov     r9d, eax; char *
0x14008fb39  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fb40  mov     edx, 482h; void *
0x14008fb45  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008fb4a  mov     rcx, rdi; this
0x14008fb4d  call    ?DoTdxStartTokenImport@WorkerTaskMigrationTarget@@AEAAJXZ; WorkerTaskMigrationTarget::DoTdxStartTokenImport(void)
0x14008fb52  mov     rcx, [rsp+178h]; this
0x14008fb5a  test    eax, eax
0x14008fb5c  jns     short loc_14008FB72
0x14008fb5e  mov     r9d, eax; char *
0x14008fb61  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fb68  mov     edx, 483h; void *
0x14008fb6d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008fb72  lea     r14, [rdi+238h]
0x14008fb79  mov     r8, r14; struct SavedStateRepository **
0x14008fb7c  mov     rdx, [rsp+178h+var_148]; struct ISavedStateStorage *
0x14008fb81  mov     rcx, r15; struct _GUID *
0x14008fb84  call    ?CreateInstance@SavedStateRepository@@SAJAEBU_GUID@@PEAVISavedStateStorage@@PEAPEAV1@@Z; SavedStateRepository::CreateInstance(_GUID const &,ISavedStateStorage *,SavedStateRepository * *)
0x14008fb89  mov     rcx, [rsp+178h]; this
0x14008fb91  xor     r15d, r15d
0x14008fb94  test    eax, eax
0x14008fb96  jns     short loc_14008FBAC
0x14008fb98  mov     r9d, eax; char *
0x14008fb9b  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fba2  mov     edx, 487h; void *
0x14008fba7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008fbac  xorps   xmm0, xmm0
0x14008fbaf  movups  xmmword ptr [rsp+178h+var_128], xmm0
0x14008fbb4  mov     rdx, [rsp+178h+var_148]; struct SavedStateStorage *
0x14008fbb9  lea     rcx, [rsp+178h+var_128]; this
0x14008fbbe  call    ??0VmSavedStateStorageAutoLock@@QEAA@PEAVSavedStateStorage@@_N@Z; VmSavedStateStorageAutoLock::VmSavedStateStorageAutoLock(SavedStateStorage *,bool)
0x14008fbc3  nop
0x14008fbc4  mov     r9d, dword ptr [rsp+178h+var_128+8]; char *
0x14008fbc9  mov     rcx, [rsp+178h]; this
0x14008fbd1  test    r9d, r9d
0x14008fbd4  jns     short loc_14008FBE7
0x14008fbd6  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fbdd  mov     edx, 48Bh; void *
0x14008fbe2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008fbe7  mov     rdx, [rdi+1B8h]; struct VmMigrationConnection *
0x14008fbee  mov     rcx, [rsp+178h+var_148]; this
0x14008fbf3  call    ?Import@SavedStateMigrationNetwork@@QEAAJPEAVVmMigrationConnection@@@Z; SavedStateMigrationNetwork::Import(VmMigrationConnection *)
0x14008fbf8  mov     esi, eax
0x14008fbfa  test    eax, eax
0x14008fbfc  jns     short loc_14008FC3D
0x14008fbfe  mov     ecx, 41E2h
0x14008fc03  call    VmlIsDebugTraceEnabled
0x14008fc08  test    eax, eax
0x14008fc0a  jz      short loc_14008FC20
0x14008fc0c  mov     r8d, esi
0x14008fc0f  lea     rdx, off_1402DB208; "Failed to receive the VM runtime-state "...
0x14008fc16  mov     ecx, 41E2h
0x14008fc1b  call    VmlDebugTraceWithError
0x14008fc20  mov     rcx, [rsp+178h]; this
0x14008fc28  mov     r9d, esi; char *
0x14008fc2b  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fc32  mov     edx, 493h; void *
0x14008fc37  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008fc3d  lea     rcx, [rsp+178h+var_128]; this
0x14008fc42  call    ??1VmSavedStateStorageAutoLock@@QEAA@XZ; VmSavedStateStorageAutoLock::~VmSavedStateStorageAutoLock(void)
0x14008fc47  test    byte ptr [rdi+1E0h], 20h
0x14008fc4e  jz      short loc_14008FC63
0x14008fc50  mov     rcx, [rdi+1C8h]
0x14008fc57  mov     rax, [rcx]
0x14008fc5a  mov     rax, [rax+48h]
0x14008fc5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008fc63  mov     [rsp+178h+var_128], r15
0x14008fc68  xorps   xmm0, xmm0
0x14008fc6b  movups  xmmword ptr [rsp+178h+var_140.Data1], xmm0
0x14008fc70  mov     esi, 1
0x14008fc75  mov     r8d, esi
0x14008fc78  mov     rdx, [r14]
0x14008fc7b  lea     rcx, [rsp+178h+var_140]
0x14008fc80  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x14008fc85  nop
0x14008fc86  mov     r9d, dword ptr [rsp+178h+var_140.Data4]; char *
0x14008fc8b  mov     rcx, [rsp+178h]; this
0x14008fc93  test    r9d, r9d
0x14008fc96  jns     short loc_14008FCA9
0x14008fc98  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fc9f  mov     edx, 4A7h; void *
0x14008fca4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008fca9  mov     [rsp+178h+var_128], r15
0x14008fcae  lea     r8, [rsp+178h+var_128]; __int64 *
0x14008fcb3  lea     rdx, ?VM_MIGRATION_RUN_STATE_XPATH@@3QBGB; "/savedVM/migration_run_state"
0x14008fcba  mov     rcx, [r14]; this
0x14008fcbd  call    ?ReadInteger@SavedStateRepository@@UEBAJPEBGAEA_J@Z; SavedStateRepository::ReadInteger(ushort const *,__int64 &)
0x14008fcc2  mov     r9d, eax; char *
0x14008fcc5  mov     ecx, 80000000h
0x14008fcca  add     eax, ecx
0x14008fccc  test    ecx, eax
0x14008fcce  jnz     short loc_14008FCF2
0x14008fcd0  cmp     r9d, 80048015h
0x14008fcd7  jz      short loc_14008FCF2
0x14008fcd9  mov     rcx, [rsp+178h]; this
0x14008fce1  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fce8  mov     edx, 4B0h; void *
0x14008fced  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008fcf2  mov     rcx, [rdi+1B0h]
0x14008fcf9  mov     eax, r15d
0x14008fcfc  cmp     [rsp+178h+var_128], rsi
0x14008fd01  setz    al
0x14008fd04  mov     [rcx+58h], eax
0x14008fd07  lea     rcx, [rsp+178h+var_140]; this
0x14008fd0c  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x14008fd11  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_RECEIVE_STATE_STOP; EventDescriptor
0x14008fd18  lea     rcx, [rsp+178h+var_118]; this
0x14008fd1d  call    ??$EndOperation@$$V@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@@Z; Vml::VmPerfTraceOperation::EndOperation<>(_EVENT_DESCRIPTOR const &)
0x14008fd22  mov     rcx, rdi; this
0x14008fd25  call    ?CheckCancel@WorkerTaskMigrationTarget@@AEAAJXZ; WorkerTaskMigrationTarget::CheckCancel(void)
0x14008fd2a  mov     rcx, [rsp+178h]; this
0x14008fd32  test    eax, eax
0x14008fd34  jns     short loc_14008FD4A
0x14008fd36  mov     r9d, eax; char *
0x14008fd39  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fd40  mov     edx, 4BDh; void *
0x14008fd45  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008fd4a  test    [rdi+1E0h], sil
0x14008fd51  jz      loc_14008FDEC
0x14008fd57  cmp     [rdi+1E8h], r15d
0x14008fd5e  jnz     loc_14008FDEC
0x14008fd64  mov     [rsp+178h+var_100], r15
0x14008fd69  mov     [rsp+178h+var_F8], r15
0x14008fd71  mov     [rsp+178h+var_10C], esi
0x14008fd75  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_CHECKSUMS_START; EventDescriptor
0x14008fd7c  lea     rcx, [rsp+178h+var_118]; this
0x14008fd81  call    ??$BeginOperation@$$V@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@@Z; Vml::VmPerfTraceOperation::BeginOperation<>(_EVENT_DESCRIPTOR const &)
0x14008fd86  mov     rcx, rdi; this
0x14008fd89  call    ?VerifyRamChecksums@WorkerTaskMigrationTarget@@AEAAJXZ; WorkerTaskMigrationTarget::VerifyRamChecksums(void)
0x14008fd8e  mov     rcx, [rsp+178h]; this
0x14008fd96  test    eax, eax
0x14008fd98  jns     short loc_14008FDAE
0x14008fd9a  mov     r9d, eax; char *
0x14008fd9d  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fda4  mov     edx, 4D3h; void *
0x14008fda9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008fdae  mov     rdx, [rsp+178h+var_148]; struct SavedStateMigrationNetwork *
0x14008fdb3  mov     rcx, rdi; this
0x14008fdb6  call    ?VerifyRuntimeStateChecksum@WorkerTaskMigrationTarget@@AEAAJPEAVSavedStateMigrationNetwork@@@Z; WorkerTaskMigrationTarget::VerifyRuntimeStateChecksum(SavedStateMigrationNetwork *)
0x14008fdbb  mov     rcx, [rsp+178h]; this
0x14008fdc3  test    eax, eax
0x14008fdc5  jns     short loc_14008FDDB
0x14008fdc7  mov     r9d, eax; char *
0x14008fdca  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fdd1  mov     edx, 4D6h; void *
0x14008fdd6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008fddb  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_CHECKSUMS_STOP; EventDescriptor
0x14008fde2  lea     rcx, [rsp+178h+var_118]; this
0x14008fde7  call    ??$EndOperation@$$V@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@@Z; Vml::VmPerfTraceOperation::EndOperation<>(_EVENT_DESCRIPTOR const &)
0x14008fdec  test    byte ptr [rdi+1E0h], 20h
0x14008fdf3  jnz     loc_14008FE98
0x14008fdf9  mov     dword ptr [rsp+178h+var_128], r15d
0x14008fdfe  mov     [rsp+178h+var_100], r15
0x14008fe03  mov     [rsp+178h+var_F8], r15
0x14008fe0b  mov     [rsp+178h+var_10C], esi
0x14008fe0f  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_WAIT_OWNER_START; EventDescriptor
0x14008fe16  lea     rcx, [rsp+178h+var_118]; this
0x14008fe1b  call    ??$BeginOperation@$$V@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@@Z; Vml::VmPerfTraceOperation::BeginOperation<>(_EVENT_DESCRIPTOR const &)
0x14008fe20  mov     qword ptr [rsp+178h+var_158], r15; int
0x14008fe25  lea     r9, [rsp+178h+var_128]; enum MigrationManager::FINAL_STATE_TRANSITION *
0x14008fe2a  mov     edx, 12Ch; unsigned int
0x14008fe2f  mov     rcx, [rdi+1B0h]; this
0x14008fe36  call    ?WaitForFinalStateTransition@MigrationManager@@QEAAJI_NAEAW4FINAL_STATE_TRANSITION@1@PEAPEAUIVmSimpleTask@@@Z; MigrationManager::WaitForFinalStateTransition(uint,bool,MigrationManager::FINAL_STATE_TRANSITION &,IVmSimpleTask * *)
0x14008fe3b  mov     rcx, [rsp+178h]; this
0x14008fe43  test    eax, eax
0x14008fe45  jns     short loc_14008FE5B
0x14008fe47  mov     r9d, eax; char *
0x14008fe4a  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fe51  mov     edx, 4EDh; void *
0x14008fe56  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008fe5b  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_WAIT_OWNER_STOP; EventDescriptor
0x14008fe62  lea     rcx, [rsp+178h+var_118]; this
0x14008fe67  call    ??$EndOperation@$$V@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@@Z; Vml::VmPerfTraceOperation::EndOperation<>(_EVENT_DESCRIPTOR const &)
0x14008fe6c  mov     edx, dword ptr [rsp+178h+var_128]
0x14008fe70  mov     rcx, rdi
0x14008fe73  call    ?TransitionWorkerProcess@WorkerTaskMigrationTarget@@AEAAJW4FINAL_STATE_TRANSITION@MigrationManager@@@Z; WorkerTaskMigrationTarget::TransitionWorkerProcess(MigrationManager::FINAL_STATE_TRANSITION)
0x14008fe78  mov     rcx, [rsp+178h]; this
0x14008fe80  test    eax, eax
0x14008fe82  jns     short loc_14008FE98
0x14008fe84  mov     r9d, eax; char *
0x14008fe87  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fe8e  mov     edx, 4F4h; void *
0x14008fe93  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008fe98  mov     rax, [rdi+10h]
0x14008fe9c  mov     rcx, [rax+430h]
0x14008fea3  mov     rax, [rcx]
0x14008fea6  mov     rax, [rax+0F0h]
0x14008fead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008feb2  mov     rcx, [rsp+178h]; this
0x14008feba  test    eax, eax
0x14008febc  jns     short loc_14008FED2
0x14008febe  mov     r9d, eax; char *
0x14008fec1  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fec8  mov     edx, 4FAh; void *
0x14008fecd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008fed2  mov     edx, 8
0x14008fed7  mov     rcx, rdi
0x14008feda  call    ?IndicateStatusToSource@WorkerTaskMigrationTarget@@AEAAJW4MESSAGE_SEQUENCE_TYPE@VmMigrationConnection@@KJ@Z; WorkerTaskMigrationTarget::IndicateStatusToSource(VmMigrationConnection::MESSAGE_SEQUENCE_TYPE,ulong,long)
0x14008fedf  test    eax, eax
0x14008fee1  jns     short loc_14008FF03
0x14008fee3  mov     ecx, 81E2h
0x14008fee8  call    VmlIsDebugTraceEnabled
0x14008feed  test    eax, eax
0x14008feef  jz      short loc_14008FF03
0x14008fef1  lea     rdx, off_1402DB2D0; "Failed to signal migration completion t"...
0x14008fef8  mov     ecx, 81E2h
0x14008fefd  call    VmlDebugTraceEx
0x14008ff02  nop
0x14008ff03  lea     rcx, [rsp+178h+var_148]
0x14008ff08  call    ??1?$VmReferencePtr@VIVmMigrationTransport@@VVmUserReferenceTraits@Vml@@@Vml@@QEAA@XZ; Vml::VmReferencePtr<IVmMigrationTransport,Vml::VmUserReferenceTraits>::~VmReferencePtr<IVmMigrationTransport,Vml::VmUserReferenceTraits>(void)
0x14008ff0d  nop
0x14008ff0e  jmp     short loc_14008FF1A
0x14008ff10  mov     r13d, dword ptr [rsp+178h+var_128]
0x14008ff15  mov     r12, [rsp+178h+var_130]
0x14008ff1a  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_STOP; EventDescriptor
0x14008ff21  lea     rcx, [rsp+178h+var_A8]; this
0x14008ff29  call    ??$EndOperation@$$V@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@@Z; Vml::VmPerfTraceOperation::EndOperation<>(_EVENT_DESCRIPTOR const &)
0x14008ff2e  mov     rcx, [rsp+178h+var_88]
0x14008ff36  mov     [r12], rcx
0x14008ff3a  lea     rcx, [rsp+178h+var_F0]
0x14008ff42  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
  ... truncated ...
```
