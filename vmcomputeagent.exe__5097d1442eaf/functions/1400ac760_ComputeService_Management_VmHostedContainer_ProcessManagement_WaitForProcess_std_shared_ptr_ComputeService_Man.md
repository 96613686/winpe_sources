# ComputeService::Management::VmHostedContainer::ProcessManagement::WaitForProcess(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::OrchestratorCallContext,ulong,ulong)

- ea: `0x1400ac760`
- end: `0x1400acc55`
- name: `?WaitForProcess@ProcessManagement@VmHostedContainer@Management@ComputeService@@UEAAKAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@UOrchestratorCallContext@34@KK@Z`
- size: `1269`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD dwMilliseconds)`
- caller_count: `0`
- callee_count: `20`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140005360`
- `0x140006098`
- `0x140009f8c`
- `0x14000ddac`
- `0x14000ea44`
- `0x14000ea60`
- `0x1400341ac`
- `0x14003f374`
- `0x14003f698`
- `0x14003f850`
- `0x14003fa78`
- `0x14003ff0c`
- `0x1400a9e7c`
- `0x1400aa31c`
- `0x1400aa61c`
- `0x1400ac760`
- `0x1400b8624`
- `0x1400dc6e8`
- `0x1400f4eb8`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400aca8c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400aca8c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400aca13`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400aca13`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400ac9b2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400ac9b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400ac99f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400ac99f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400ac8cf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400ac8cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400ac948`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400ac948`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ac935`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ac935`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400ac955`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400ac962`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400ac955`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400ac962`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1400ac9db`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1400ac9db`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1400ac987`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1400ac987`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400ac940`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400acb0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400ac940`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400acb0e`

## string_xrefs

- `0x1400acc31`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400acbee`: `onecore\vm\compute\management\computeSystem\ComputeSystem.h`
- `0x1400acc06`: `onecore\vm\compute\management\computeSystem\ComputeSystem.h`
- `0x1400acbb7`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\processmanagement.cpp`
- `0x1400acbd6`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\processmanagement.cpp`
- `0x1400acc18`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\processmanagement.cpp`
- `0x1400acc43`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\processmanagement.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ComputeService::Management::VmHostedContainer::ProcessManagement::WaitForProcess(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        unsigned int a4,
        DWORD dwMilliseconds)
{
  __int64 *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r8
  RTL_SRWLOCK *v11; // rax
  __int64 *v12; // rsi
  __int64 *v13; // r13
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdi
  __int64 *v17; // rax
  HANDLE v18; // r15
  DWORD LastError; // ebx
  HANDLE CurrentProcess; // rbx
  void *v21; // rdi
  HANDLE v22; // rax
  const char *v23; // r9
  DWORD v24; // eax
  const char *v25; // r9
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 *v29; // rax
  __int64 v30; // rdi
  volatile signed __int32 *v31; // rbx
  DWORD v32; // edi
  volatile signed __int32 *v33; // rbx
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-E0h]
  __int64 *v36; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v37; // [rsp+48h] [rbp-B8h]
  __int64 *v38; // [rsp+58h] [rbp-A8h] BYREF
  DWORD *p_ExitCode; // [rsp+60h] [rbp-A0h]
  char v40; // [rsp+68h] [rbp-98h]
  __int64 v41; // [rsp+70h] [rbp-90h] BYREF
  __int64 v42; // [rsp+78h] [rbp-88h]
  __int64 v43; // [rsp+80h] [rbp-80h]
  __int64 v44; // [rsp+88h] [rbp-78h]
  __int64 v45; // [rsp+90h] [rbp-70h]
  __int64 v46; // [rsp+98h] [rbp-68h]
  _QWORD *v47; // [rsp+A0h] [rbp-60h]
  DWORD ExitCode; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE hObject; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v50; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v51[42]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  v47 = a3;
  memset_0(v51, 0, sizeof(v51));
  v8 = (__int64 *)(**(_QWORD **)a2 + 8LL);
  if ( *(_QWORD *)(**(_QWORD **)a2 + 32LL) > 7u )
    v8 = (__int64 *)*v8;
  v36 = v8;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v51,
    "VmHostedContainer_WaitForProcess");
  v51[0] = &ComputeService::Diagnostics::TraceProvider::VmHostedContainer_WaitForProcess::`vftable';
  ComputeService::Diagnostics::TraceProvider::VmHostedContainer_WaitForProcess::StartActivity<unsigned short const *>(
    v51,
    &v36);
  v9 = _RTDynamicCast_0(
         *(_QWORD *)(*(_QWORD *)a2 + 8LL),
         0,
         &ComputeService::Management::ComputeSystemState `RTTI Type Descriptor',
         &ComputeService::Management::BaseStateMachine `RTTI Type Descriptor');
  if ( !v9 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\vm\\compute\\management\\computeSystem\\ComputeSystem.h",
      (const char *)0x80004001LL,
      0);
  v50 = 0;
  v41 = *a3;
  v42 = a3[1];
  *a3 = 0;
  a3[1] = 0;
  v43 = a3[2];
  v44 = a3[3];
  a3[2] = 0;
  a3[3] = 0;
  v45 = a3[4];
  v46 = a3[5];
  a3[4] = 0;
  a3[5] = 0;
  ComputeService::Management::BeginGenericOperation_InState(&v50, v9, v10, &v41);
  v11 = (RTL_SRWLOCK *)_RTDynamicCast_0(
                         *(_QWORD *)(*(_QWORD *)a2 + 8LL),
                         0,
                         &ComputeService::Management::ComputeSystemState `RTTI Type Descriptor',
                         &ComputeService::Management::VmHostedProcessExecutionState `RTTI Type Descriptor');
  v12 = (__int64 *)v11;
  if ( !v11 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\vm\\compute\\management\\computeSystem\\ComputeSystem.h",
      (const char *)0x80004001LL,
      0);
  hObject = 0;
  AcquireSRWLockShared(v11);
  v36 = v12;
  v13 = v12 + 1;
  v14 = v12[1];
  v15 = *(_QWORD *)(v14 + 8);
  HIDWORD(p_ExitCode) = 0;
  v16 = v14;
  while ( !*(_BYTE *)(v15 + 25) )
  {
    if ( *(_DWORD *)(v15 + 32) >= a4 )
      v16 = v15;
    v17 = (__int64 *)(v15 + 16);
    if ( *(_DWORD *)(v15 + 32) >= a4 )
      v17 = (__int64 *)v15;
    v15 = *v17;
  }
  if ( *(_BYTE *)(v16 + 25) || a4 < *(_DWORD *)(v16 + 32) || v16 == v14 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x13C,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\processmanagement.cpp",
      (const char *)0x490,
      0);
  v18 = hObject;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = GetLastError();
    CloseHandle(v18);
    SetLastError(LastError);
  }
  hObject = 0;
  CurrentProcess = GetCurrentProcess();
  v21 = *(void **)(v16 + 56);
  v22 = GetCurrentProcess();
  if ( !DuplicateHandle(v22, v21, CurrentProcess, &hObject, 0, 0, 2u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x145,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\processmanagement.cpp",
      v23);
  ReleaseSRWLockShared((PSRWLOCK)v12);
  v24 = WaitForSingleObjectEx(hObject, dwMilliseconds, 0);
  if ( v24 == 258 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x14A,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\processmanagement.cpp",
      (const char *)0x102,
      dwDesiredAccess);
  if ( v24 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xB0F,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)0x102);
  ExitCode = 0;
  if ( !GetExitCodeProcess(hObject, &ExitCode) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x14E,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\processmanagement.cpp",
      v25);
  v38 = &v50;
  p_ExitCode = &ExitCode;
  v40 = 1;
  v37 = 0;
  AcquireSRWLockExclusive((PSRWLOCK)v12);
  v26 = *v13;
  v27 = *(_QWORD *)(*v13 + 8);
  HIDWORD(v42) = 0;
  v28 = v26;
  while ( !*(_BYTE *)(v27 + 25) )
  {
    if ( *(_DWORD *)(v27 + 32) >= a4 )
      v28 = v27;
    v29 = (__int64 *)(v27 + 16);
    if ( *(_DWORD *)(v27 + 32) >= a4 )
      v29 = (__int64 *)v27;
    v27 = *v29;
  }
  if ( *(_BYTE *)(v28 + 25) || a4 < *(_DWORD *)(v28 + 32) || v28 == v26 )
  {
    v31 = (volatile signed __int32 *)*((_QWORD *)&v37 + 1);
    v30 = v37;
  }
  else
  {
    v30 = *(_QWORD *)(v28 + 40);
    v31 = *(volatile signed __int32 **)(v28 + 48);
    *(_QWORD *)(v28 + 40) = 0;
    *(_QWORD *)(v28 + 48) = 0;
    *(_QWORD *)&v37 = v30;
    *((_QWORD *)&v37 + 1) = v31;
    std::_Tree<std::_Tmap_traits<unsigned long,ComputeService::Management::ProcessState,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,ComputeService::Management::ProcessState>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,ComputeService::Management::ProcessState>>>>,0>(
      (__int64)(v12 + 1),
      &v36,
      (__int64 *)v28);
  }
  ReleaseSRWLockExclusive((PSRWLOCK)v12);
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 40LL))(v30);
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v51,
    0);
  v32 = ExitCode;
  if ( v31 )
  {
    if ( !_InterlockedDecrement(v31 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
      if ( !_InterlockedDecrement(v31 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
    }
  }
  v40 = 0;
  lambda_81977e5d0687d1423b337ad9db757513_::operator()(&v38);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  std::unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>::~unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>(&v50);
  v51[0] = &ComputeService::Diagnostics::TraceProvider::VmHostedContainer_WaitForProcess::`vftable';
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v51);
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(v51);
  ComputeService::Management::RetireServerOperation::~RetireServerOperation((ComputeService::Management::RetireServerOperation *)(a3 + 2));
  v33 = (volatile signed __int32 *)a3[1];
  if ( v33 )
  {
    if ( _InterlockedExchangeAdd(v33 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
      if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
    }
  }
  return v32;
}

```

## disassembly

```asm
0x1400ac760  mov     [rsp-8+arg_0], rbx
0x1400ac765  mov     [rsp-8+arg_10], r8
0x1400ac76a  push    rbp
0x1400ac76b  push    rsi
0x1400ac76c  push    rdi
0x1400ac76d  push    r12
0x1400ac76f  push    r13
0x1400ac771  push    r14
0x1400ac773  push    r15
0x1400ac775  lea     rbp, [rsp-120h]
0x1400ac77d  sub     rsp, 220h
0x1400ac784  mov     rax, cs:__security_cookie
0x1400ac78b  xor     rax, rsp
0x1400ac78e  mov     [rbp+150h+var_40], rax
0x1400ac795  mov     r14d, r9d
0x1400ac798  mov     r12, r8
0x1400ac79b  mov     rbx, rdx
0x1400ac79e  mov     [rbp+150h+var_1B0], r8
0x1400ac7a2  xor     edx, edx; Val
0x1400ac7a4  mov     r8d, 150h; Size
0x1400ac7aa  lea     rcx, [rbp+150h+var_190]; void *
0x1400ac7ae  call    memset_0
0x1400ac7b3  mov     rax, [rbx]
0x1400ac7b6  mov     rcx, [rax]
0x1400ac7b9  add     rcx, 8
0x1400ac7bd  cmp     qword ptr [rcx+18h], 7
0x1400ac7c2  jbe     short loc_1400AC7C7
0x1400ac7c4  mov     rcx, [rcx]
0x1400ac7c7  mov     [rsp+250h+var_210], rcx
0x1400ac7cc  lea     rdx, aVmhostedcontai_6; "VmHostedContainer_WaitForProcess"
0x1400ac7d3  lea     rcx, [rbp+150h+var_190]
0x1400ac7d7  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400ac7dc  lea     rax, ??_7VmHostedContainer_WaitForProcess@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::VmHostedContainer_WaitForProcess::`vftable'
0x1400ac7e3  mov     [rbp+150h+var_190], rax
0x1400ac7e7  lea     rdx, [rsp+250h+var_210]
0x1400ac7ec  lea     rcx, [rbp+150h+var_190]
0x1400ac7f0  call    ??$StartActivity@PEBG@VmHostedContainer_WaitForProcess@TraceProvider@Diagnostics@ComputeService@@QEAAX$$QEAPEBG@Z; ComputeService::Diagnostics::TraceProvider::VmHostedContainer_WaitForProcess::StartActivity<ushort const *>(ushort const * &&)
0x1400ac7f5  nop
0x1400ac7f6  mov     rcx, [rbx]
0x1400ac7f9  xor     r15d, r15d
0x1400ac7fc  mov     [rsp+250h+dwDesiredAccess], r15d; int
0x1400ac801  lea     r9, ??_R0?AUBaseStateMachine@Management@ComputeService@@@8; ComputeService::Management::BaseStateMachine `RTTI Type Descriptor'
0x1400ac808  lea     r8, ??_R0?AUComputeSystemState@Management@ComputeService@@@8; ComputeService::Management::ComputeSystemState `RTTI Type Descriptor'
0x1400ac80f  xor     edx, edx
0x1400ac811  mov     rcx, [rcx+8]
0x1400ac815  call    __RTDynamicCast_0
0x1400ac81a  mov     rdx, rax
0x1400ac81d  mov     rcx, [rbp+158h]; this
0x1400ac824  test    rax, rax
0x1400ac827  jz      loc_1400ACBE8
0x1400ac82d  mov     [rbp+150h+var_198], r15
0x1400ac831  mov     rax, [r12]
0x1400ac835  mov     [rsp+250h+var_1E0], rax
0x1400ac83a  mov     rax, [r12+8]
0x1400ac83f  mov     [rsp+250h+var_1D8], rax
0x1400ac844  mov     [r12], r15
0x1400ac848  mov     [r12+8], r15
0x1400ac84d  mov     rax, [r12+10h]
0x1400ac852  mov     [rbp+150h+var_1D0], rax
0x1400ac856  mov     rax, [r12+18h]
0x1400ac85b  mov     [rbp+150h+var_1C8], rax
0x1400ac85f  mov     [r12+10h], r15
0x1400ac864  mov     [r12+18h], r15
0x1400ac869  mov     rax, [r12+20h]
0x1400ac86e  mov     [rbp+150h+var_1C0], rax
0x1400ac872  mov     rax, [r12+28h]
0x1400ac877  mov     [rbp+150h+var_1B8], rax
0x1400ac87b  mov     [r12+20h], r15
0x1400ac880  mov     [r12+28h], r15
0x1400ac885  lea     r9, [rsp+250h+var_1E0]
0x1400ac88a  lea     rcx, [rbp+150h+var_198]
0x1400ac88e  call    ?BeginGenericOperation_InState@Management@ComputeService@@YA?AVActiveStateOperation@12@PEAUBaseStateMachine@12@W4SystemState@12@VActiveServerOperation@12@@Z; ComputeService::Management::BeginGenericOperation_InState(ComputeService::Management::BaseStateMachine *,ComputeService::Management::SystemState,ComputeService::Management::ActiveServerOperation)
0x1400ac893  nop
0x1400ac894  mov     rcx, [rbx]
0x1400ac897  mov     [rsp+250h+dwDesiredAccess], r15d; int
0x1400ac89c  lea     r9, ??_R0?AUVmHostedProcessExecutionState@Management@ComputeService@@@8; ComputeService::Management::VmHostedProcessExecutionState `RTTI Type Descriptor'
0x1400ac8a3  lea     r8, ??_R0?AUComputeSystemState@Management@ComputeService@@@8; ComputeService::Management::ComputeSystemState `RTTI Type Descriptor'
0x1400ac8aa  xor     edx, edx
0x1400ac8ac  mov     rcx, [rcx+8]
0x1400ac8b0  call    __RTDynamicCast_0
0x1400ac8b5  mov     rsi, rax
0x1400ac8b8  mov     rcx, [rbp+158h]; this
0x1400ac8bf  test    rax, rax
0x1400ac8c2  jz      loc_1400ACC00
0x1400ac8c8  mov     [rbp+150h+hObject], r15
0x1400ac8cc  mov     rcx, rax; SRWLock
0x1400ac8cf  call    cs:__imp_AcquireSRWLockShared
0x1400ac8d5  mov     [rsp+250h+var_210], rsi
0x1400ac8da  lea     r13, [rsi+8]
0x1400ac8de  mov     rdx, [r13+0]
0x1400ac8e2  mov     rcx, [rdx+8]
0x1400ac8e6  xor     eax, eax
0x1400ac8e8  mov     [rsp+250h+var_1EC], eax
0x1400ac8ec  mov     rdi, rdx
0x1400ac8ef  jmp     short loc_1400AC904
0x1400ac8f1  cmp     [rcx+20h], r14d
0x1400ac8f5  cmovnb  rdi, rcx
0x1400ac8f9  lea     rax, [rcx+10h]
0x1400ac8fd  cmovnb  rax, rcx
0x1400ac901  mov     rcx, [rax]
0x1400ac904  cmp     [rcx+19h], r15b
0x1400ac908  jz      short loc_1400AC8F1
0x1400ac90a  cmp     [rdi+19h], r15b
0x1400ac90e  jnz     loc_1400ACBC9
0x1400ac914  cmp     r14d, [rdi+20h]
0x1400ac918  jb      loc_1400ACBC9
0x1400ac91e  cmp     rdi, rdx
0x1400ac921  jz      loc_1400ACBC9
0x1400ac927  mov     r15, [rbp+150h+hObject]
0x1400ac92b  lea     rax, [r15-1]
0x1400ac92f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400ac933  ja      short loc_1400AC94E
0x1400ac935  call    cs:__imp_GetLastError
0x1400ac93b  mov     ebx, eax
0x1400ac93d  mov     rcx, r15; hObject
0x1400ac940  call    cs:__imp_CloseHandle
0x1400ac946  mov     ecx, ebx; dwErrCode
0x1400ac948  call    cs:__imp_SetLastError
0x1400ac94e  xor     r15d, r15d
0x1400ac951  mov     [rbp+150h+hObject], r15
0x1400ac955  call    cs:__imp_GetCurrentProcess
0x1400ac95b  mov     rbx, rax
0x1400ac95e  mov     rdi, [rdi+38h]
0x1400ac962  call    cs:__imp_GetCurrentProcess
0x1400ac968  mov     [rsp+250h+dwOptions], 2; dwOptions
0x1400ac970  mov     [rsp+250h+bInheritHandle], r15d; bInheritHandle
0x1400ac975  mov     [rsp+250h+dwDesiredAccess], r15d; unsigned int
0x1400ac97a  lea     r9, [rbp+150h+hObject]; lpTargetHandle
0x1400ac97e  mov     r8, rbx; hTargetProcessHandle
0x1400ac981  mov     rdx, rdi; hSourceHandle
0x1400ac984  mov     rcx, rax; hSourceProcessHandle
0x1400ac987  call    cs:__imp_DuplicateHandle
0x1400ac98d  mov     rcx, [rbp+158h]; this
0x1400ac994  test    eax, eax
0x1400ac996  jz      loc_1400ACC18
0x1400ac99c  mov     rcx, rsi; SRWLock
0x1400ac99f  call    cs:__imp_ReleaseSRWLockShared
0x1400ac9a5  xor     r8d, r8d; bAlertable
0x1400ac9a8  mov     edx, [rbp+150h+dwMilliseconds]; dwMilliseconds
0x1400ac9ae  mov     rcx, [rbp+150h+hObject]; hHandle
0x1400ac9b2  call    cs:__imp_WaitForSingleObjectEx
0x1400ac9b8  mov     r9d, 102h; char *
0x1400ac9be  cmp     eax, r9d
0x1400ac9c1  jz      loc_1400ACBB0
0x1400ac9c7  test    eax, eax
0x1400ac9c9  jnz     loc_1400ACC2A
0x1400ac9cf  mov     [rbp+150h+ExitCode], r15d
0x1400ac9d3  lea     rdx, [rbp+150h+ExitCode]; lpExitCode
0x1400ac9d7  mov     rcx, [rbp+150h+hObject]; hProcess
0x1400ac9db  call    cs:__imp_GetExitCodeProcess
0x1400ac9e1  mov     rcx, [rbp+158h]; this
0x1400ac9e8  test    eax, eax
0x1400ac9ea  jz      loc_1400ACC43
0x1400ac9f0  lea     rax, [rbp+150h+var_198]
0x1400ac9f4  mov     [rsp+250h+var_1F8], rax
0x1400ac9f9  lea     rax, [rbp+150h+ExitCode]
0x1400ac9fd  mov     [rsp+60h], rax
0x1400aca02  mov     [rsp+250h+var_1E8], 1
0x1400aca07  xorps   xmm1, xmm1
0x1400aca0a  movdqu  [rsp+250h+var_208], xmm1
0x1400aca10  mov     rcx, rsi; SRWLock
0x1400aca13  call    cs:__imp_AcquireSRWLockExclusive
0x1400aca19  mov     rdx, [r13+0]
0x1400aca1d  mov     rcx, [rdx+8]
0x1400aca21  xor     eax, eax
0x1400aca23  mov     dword ptr [rsp+250h+var_1D8+4], eax
0x1400aca27  mov     r8, rdx
0x1400aca2a  jmp     short loc_1400ACA3F
0x1400aca2c  cmp     [rcx+20h], r14d
0x1400aca30  cmovnb  r8, rcx
0x1400aca34  lea     rax, [rcx+10h]
0x1400aca38  cmovnb  rax, rcx
0x1400aca3c  mov     rcx, [rax]
0x1400aca3f  cmp     [rcx+19h], r15b
0x1400aca43  jz      short loc_1400ACA2C
0x1400aca45  cmp     [r8+19h], r15b
0x1400aca49  jnz     short loc_1400ACA7F
0x1400aca4b  cmp     r14d, [r8+20h]
0x1400aca4f  jb      short loc_1400ACA7F
0x1400aca51  cmp     r8, rdx
0x1400aca54  jz      short loc_1400ACA7F
0x1400aca56  mov     rdi, [r8+28h]
0x1400aca5a  mov     rbx, [r8+30h]
0x1400aca5e  mov     [r8+28h], r15
0x1400aca62  mov     [r8+30h], r15
0x1400aca66  mov     qword ptr [rsp+250h+var_208], rdi
0x1400aca6b  mov     qword ptr [rsp+250h+var_208+8], rbx
0x1400aca70  lea     rdx, [rsp+250h+var_210]
0x1400aca75  mov     rcx, r13
0x1400aca78  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUProcessState@Management@ComputeService@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@KUProcessState@Management@ComputeService@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUProcessState@Management@ComputeService@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUProcessState@Management@ComputeService@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<ulong,ComputeService::Management::ProcessState,std::less<ulong>,std::allocator<std::pair<ulong const,ComputeService::Management::ProcessState>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,ComputeService::Management::ProcessState>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,ComputeService::Management::ProcessState>>>>)
0x1400aca7d  jmp     short loc_1400ACA89
0x1400aca7f  mov     rbx, qword ptr [rsp+250h+var_208+8]
0x1400aca84  mov     rdi, qword ptr [rsp+250h+var_208]
0x1400aca89  mov     rcx, rsi; SRWLock
0x1400aca8c  call    cs:__imp_ReleaseSRWLockExclusive
0x1400aca92  test    rdi, rdi
0x1400aca95  jz      short loc_1400ACAA6
0x1400aca97  mov     rax, [rdi]
0x1400aca9a  mov     rcx, rdi
0x1400aca9d  mov     rax, [rax+28h]
0x1400acaa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400acaa6  xor     edx, edx
0x1400acaa8  lea     rcx, [rbp+150h+var_190]
0x1400acaac  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400acab1  mov     edi, [rbp+150h+ExitCode]
0x1400acab4  or      esi, 0FFFFFFFFh
0x1400acab7  test    rbx, rbx
0x1400acaba  jz      short loc_1400ACAF0
0x1400acabc  mov     eax, esi
0x1400acabe  lock xadd [rbx+8], eax
0x1400acac3  add     eax, esi
0x1400acac5  jnz     short loc_1400ACAF0
0x1400acac7  mov     rax, [rbx]
0x1400acaca  mov     rcx, rbx
0x1400acacd  mov     rax, [rax]
0x1400acad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400acad5  mov     eax, esi
0x1400acad7  lock xadd [rbx+0Ch], eax
0x1400acadc  add     eax, esi
0x1400acade  jnz     short loc_1400ACAF0
0x1400acae0  mov     rax, [rbx]
0x1400acae3  mov     rcx, rbx
0x1400acae6  mov     rax, [rax+8]
0x1400acaea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400acaef  nop
0x1400acaf0  mov     [rsp+250h+var_1E8], r15b
0x1400acaf5  lea     rcx, [rsp+250h+var_1F8]
0x1400acafa  call    _lambda_81977e5d0687d1423b337ad9db757513___operator__
0x1400acaff  nop
0x1400acb00  mov     rcx, [rbp+150h+hObject]; hObject
0x1400acb04  lea     rax, [rcx-1]
0x1400acb08  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400acb0c  ja      short loc_1400ACB15
0x1400acb0e  call    cs:__imp_CloseHandle
0x1400acb14  nop
0x1400acb15  lea     rcx, [rbp+150h+var_198]
0x1400acb19  call    ??1?$unique_ptr@UActiveStateOperationContext@ActiveStateOperation@Management@ComputeService@@U?$default_delete@UActiveStateOperationContext@ActiveStateOperation@Management@ComputeService@@@std@@@std@@QEAA@XZ; std::unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>::~unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>(void)
0x1400acb1e  nop
0x1400acb1f  lea     rax, ??_7VmHostedContainer_WaitForProcess@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::VmHostedContainer_WaitForProcess::`vftable'
0x1400acb26  mov     [rbp+150h+var_190], rax
0x1400acb2a  lea     rcx, [rbp+150h+var_190]
0x1400acb2e  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1400acb33  lea     rcx, [rbp+150h+var_190]
0x1400acb37  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1400acb3c  nop
0x1400acb3d  lea     rcx, [r12+10h]; this
0x1400acb42  call    ??1RetireServerOperation@Management@ComputeService@@QEAA@XZ; ComputeService::Management::RetireServerOperation::~RetireServerOperation(void)
0x1400acb47  mov     rbx, [r12+8]
0x1400acb4c  test    rbx, rbx
0x1400acb4f  jz      short loc_1400ACB84
0x1400acb51  mov     eax, esi
0x1400acb53  lock xadd [rbx+8], eax
0x1400acb58  add     eax, esi
0x1400acb5a  jnz     short loc_1400ACB84
0x1400acb5c  mov     rax, [rbx]
0x1400acb5f  mov     rcx, rbx
0x1400acb62  mov     rax, [rax]
0x1400acb65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400acb6a  mov     edx, esi
0x1400acb6c  lock xadd [rbx+0Ch], edx
0x1400acb71  add     edx, esi
0x1400acb73  jnz     short loc_1400ACB84
0x1400acb75  mov     rdx, [rbx]
0x1400acb78  mov     rcx, rbx
0x1400acb7b  mov     rax, [rdx+8]
0x1400acb7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400acb84  mov     eax, edi
0x1400acb86  mov     rcx, [rbp+150h+var_40]
0x1400acb8d  xor     rcx, rsp; StackCookie
0x1400acb90  call    __security_check_cookie
0x1400acb95  mov     rbx, [rsp+250h+arg_0]
0x1400acb9d  add     rsp, 220h
0x1400acba4  pop     r15
0x1400acba6  pop     r14
0x1400acba8  pop     r13
0x1400acbaa  pop     r12
0x1400acbac  pop     rdi
0x1400acbad  pop     rsi
0x1400acbae  pop     rbp
0x1400acbaf  retn
0x1400acbb0  mov     rcx, [rbp+158h]; this
0x1400acbb7  lea     r8, aOnecoreVmCompu_46; "onecore\\vm\\compute\\management\\orche"...
0x1400acbbe  mov     edx, 14Ah; void *
0x1400acbc3  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400acbc9  mov     rcx, [rbp+158h]; this
0x1400acbd0  mov     r9d, 490h; char *
0x1400acbd6  lea     r8, aOnecoreVmCompu_46; "onecore\\vm\\compute\\management\\orche"...
0x1400acbdd  mov     edx, 13Ch; void *
0x1400acbe2  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400acbe8  mov     r9d, 80004001h; char *
0x1400acbee  lea     r8, aOnecoreVmCompu_32; "onecore\\vm\\compute\\management\\compu"...
0x1400acbf5  mov     edx, 5Dh ; ']'; void *
0x1400acbfa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400acc00  mov     r9d, 80004001h; char *
0x1400acc06  lea     r8, aOnecoreVmCompu_32; "onecore\\vm\\compute\\management\\compu"...
0x1400acc0d  mov     edx, 5Dh ; ']'; void *
0x1400acc12  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400acc18  lea     r8, aOnecoreVmCompu_46; "onecore\\vm\\compute\\management\\orche"...
0x1400acc1f  mov     edx, 145h; void *
0x1400acc24  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
  ... truncated ...
```
