# ComputeService::Management::VmHostedContainer::ProcessManagement::SignalProcess(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::OrchestratorCallContext,ulong,Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits> const &)

- ea: `0x1400ab740`
- end: `0x1400abbcb`
- name: `?SignalProcess@ProcessManagement@VmHostedContainer@Management@ComputeService@@UEAAXAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@UOrchestratorCallContext@34@KAEBV?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@@Z`
- size: `1163`
- prototype: ``
- caller_count: `0`
- callee_count: `27`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140005360`
- `0x140006098`
- `0x1400083bc`
- `0x14000ddac`
- `0x14000ea60`
- `0x14000f93c`
- `0x140034170`
- `0x1400341ac`
- `0x1400393b8`
- `0x14003a9ac`
- `0x14003f374`
- `0x14003f698`
- `0x14003f850`
- `0x14003fa78`
- `0x14003ff0c`
- `0x1400a9d9c`
- `0x1400aa03c`
- `0x1400aa31c`
- `0x1400ab1d4`
- `0x1400ab278`
- `0x1400ab740`
- `0x1400b8624`
- `0x1400dc6e8`
- `0x1400e2ab8`
- `0x1400e6c9c`
- `0x1400f4eb8`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400ab944`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400ab944`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400ab8c8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400ab8c8`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400ab952`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400ab952`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400ab974`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400ab974`

## string_xrefs

- `0x1400abae0`: `onecore\vm\compute\management\computeSystem\ComputeSystem.h`
- `0x1400abb0d`: `onecore\vm\compute\management\computeSystem\ComputeSystem.h`
- `0x1400abb25`: `onecore\vm\compute\management\computeSystem\ComputeSystem.h`
- `0x1400abb6e`: `onecore\vm\compute\management\computeSystem\ComputeSystem.h`
- `0x1400abaf5`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\processmanagement.cpp`
- `0x1400abb37`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\processmanagement.cpp`
- `0x1400abb56`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\processmanagement.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall ComputeService::Management::VmHostedContainer::ProcessManagement::SignalProcess(
        __int64 a1,
        __int64 **a2,
        _QWORD *a3,
        unsigned int a4,
        _QWORD *a5)
{
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r8
  RTL_SRWLOCK *v11; // rax
  RTL_SRWLOCK *v12; // rsi
  char *v13; // rbx
  char *Ptr; // rdx
  char *v15; // rcx
  char *v16; // r8
  __int64 *v17; // rax
  void **v18; // rax
  const char *v19; // r9
  volatile signed __int32 *v20; // rbx
  struct ComputeService::Management::VmHostedProcessExecutionState *v21; // r12
  _BYTE *v22; // rax
  __int64 v23; // r8
  unsigned int v24; // r8d
  unsigned int v25; // r9d
  unsigned int v26; // ebx
  void *ServiceBinding; // rax
  int v28; // eax
  __int64 v29; // rax
  __int64 v30; // rax
  unsigned int v31; // eax
  const char *v32; // rdx
  void *v33; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v34[7]; // [rsp+38h] [rbp-C8h] BYREF
  char v35[8]; // [rsp+70h] [rbp-90h] BYREF
  char v36[4]; // [rsp+78h] [rbp-88h] BYREF
  int v37; // [rsp+7Ch] [rbp-84h]
  unsigned int v38[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v39; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v40[42]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  v34[6] = a3;
  memset_0(v40, 0, sizeof(v40));
  v8 = (_QWORD *)(**a2 + 8);
  if ( *(_QWORD *)(**a2 + 32) > 7u )
    v8 = (_QWORD *)*v8;
  *(_QWORD *)v38 = v8;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v40,
    "VmHostedContainer_SignalProcess");
  v40[0] = &ComputeService::Diagnostics::TraceProvider::VmHostedContainer_SignalProcess::`vftable';
  ComputeService::Diagnostics::TraceProvider::VmHostedContainer_SignalProcess::StartActivity<unsigned short const *>(
    v40,
    v38);
  v9 = _RTDynamicCast_0(
         (*a2)[1],
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
  v39 = 0;
  v34[0] = *a3;
  v34[1] = a3[1];
  *a3 = 0;
  a3[1] = 0;
  v34[2] = a3[2];
  v34[3] = a3[3];
  a3[2] = 0;
  a3[3] = 0;
  v34[4] = a3[4];
  v34[5] = a3[5];
  a3[4] = 0;
  a3[5] = 0;
  ComputeService::Management::BeginGenericOperation_InState(&v39, v9, v10, v34);
  v11 = (RTL_SRWLOCK *)_RTDynamicCast_0(
                         (*a2)[1],
                         0,
                         &ComputeService::Management::ComputeSystemState `RTTI Type Descriptor',
                         &ComputeService::Management::VmHostedProcessExecutionState `RTTI Type Descriptor');
  v12 = v11;
  if ( !v11 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\vm\\compute\\management\\computeSystem\\ComputeSystem.h",
      (const char *)0x80004001LL,
      0);
  if ( *a5 || a5[2] )
  {
    v21 = (struct ComputeService::Management::VmHostedProcessExecutionState *)_RTDynamicCast_0(
                                                                                (*a2)[1],
                                                                                0,
                                                                                &ComputeService::Management::ComputeSystemState `RTTI Type Descriptor',
                                                                                &ComputeService::Management::ServerContainerState `RTTI Type Descriptor');
    if ( !v21 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5D,
        (unsigned int)"onecore\\vm\\compute\\management\\computeSystem\\ComputeSystem.h",
        (const char *)0x80004001LL,
        0);
    v38[0] = 0;
    v22 = (_BYTE *)Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Schema::Options::SignalProcessOptions>(
                     a5,
                     v35,
                     v38);
    if ( !*v22 )
    {
      v29 = std::shared_ptr<ComputeService::Management::ComputeSystem>::operator-><ComputeService::Management::ComputeSystem,0>((__int64)(v22 + 8));
      v30 = std::wstring::c_str(v29);
      v31 = wil::verify_hresult<long>(3224830221LL, v30);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x1F,
        (unsigned int)"OneCore\\Internal\\VM\\inc\\MarshalUtilities.h",
        (const char *)v31,
        (int)"%ls",
        v32);
    }
    std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(v36);
    v23 = **a2;
    if ( !v23 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5D,
        (unsigned int)"onecore\\vm\\compute\\management\\computeSystem\\ComputeSystem.h",
        (const char *)0x80004001LL,
        0);
    if ( ComputeService::Management::VmHostedContainer::ProcessManagement::IsHostProcessContainer(
           (__int64)retaddr,
           a2,
           v23) )
    {
      CExec::SignalProcess((CExec *)a4, v38[0], v24);
    }
    else
    {
      v26 = v38[0];
      ServiceBinding = ComputeService::Management::VmHostedContainer::GetServiceBinding(
                         (ComputeService::Management::VmHostedContainer *)v12,
                         v21,
                         (struct ComputeService::Management::ServerContainerState *)a4,
                         v25);
      v28 = ContainerSignalProcess(ServiceBinding, a4, v26);
      if ( v28 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1B7,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\processmanagement.cpp",
          (const char *)(unsigned int)v28,
          0);
    }
  }
  else
  {
    v13 = 0;
    v33 = 0;
    AcquireSRWLockExclusive(v11);
    *(_QWORD *)v38 = v12;
    Ptr = (char *)v12[1].Ptr;
    v15 = (char *)*((_QWORD *)Ptr + 1);
    v37 = 0;
    v16 = Ptr;
    while ( !v15[25] )
    {
      if ( *((_DWORD *)v15 + 8) >= a4 )
        v16 = v15;
      v17 = (__int64 *)(v15 + 16);
      if ( *((_DWORD *)v15 + 8) >= a4 )
        v17 = (__int64 *)v15;
      v15 = (char *)*v17;
    }
    if ( v16[25] || a4 < *((_DWORD *)v16 + 8) || v16 == Ptr )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1C4,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\processmanagement.cpp",
        (const char *)0x490,
        0);
    v18 = (void **)(v16 + 56);
    if ( &v33 != (void **)(v16 + 56) )
    {
      v13 = (char *)*v18;
      v33 = *v18;
      *v18 = 0;
    }
    std::_Tree<std::_Tmap_traits<unsigned long,ComputeService::Management::ProcessState,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,ComputeService::Management::ProcessState>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,ComputeService::Management::ProcessState>>>>,0>(
      (__int64)&v12[1],
      (__int64 **)v38,
      (__int64 *)v16);
    ReleaseSRWLockExclusive(v12);
    if ( !TerminateProcess(v13, 0x42Bu) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1CB,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\processmanagement.cpp",
        v19);
    if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v13);
  }
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v40,
    0);
  std::unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>::~unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>(&v39);
  v40[0] = &ComputeService::Diagnostics::TraceProvider::VmHostedContainer_SignalProcess::`vftable';
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v40);
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(v40);
  ComputeService::Management::RetireServerOperation::~RetireServerOperation((ComputeService::Management::RetireServerOperation *)(a3 + 2));
  v20 = (volatile signed __int32 *)a3[1];
  if ( v20 && _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
    if ( !_InterlockedDecrement(v20 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
  }
}

```

## disassembly

```asm
0x1400ab740  mov     [rsp-8+arg_0], rbx
0x1400ab745  mov     [rsp-8+arg_10], r8
0x1400ab74a  push    rbp
0x1400ab74b  push    rsi
0x1400ab74c  push    rdi
0x1400ab74d  push    r12
0x1400ab74f  push    r13
0x1400ab751  push    r14
0x1400ab753  push    r15
0x1400ab755  lea     rbp, [rsp-100h]
0x1400ab75d  sub     rsp, 200h
0x1400ab764  mov     rax, cs:__security_cookie
0x1400ab76b  xor     rax, rsp
0x1400ab76e  mov     [rbp+130h+var_40], rax
0x1400ab775  mov     edi, r9d
0x1400ab778  mov     r15, r8
0x1400ab77b  mov     rbx, rdx
0x1400ab77e  mov     r14, [rbp+130h+arg_20]
0x1400ab785  mov     [rsp+230h+var_1C8], r8
0x1400ab78a  xor     edx, edx; Val
0x1400ab78c  mov     r8d, 150h; Size
0x1400ab792  lea     rcx, [rbp+130h+var_190]; void *
0x1400ab796  call    memset_0
0x1400ab79b  mov     rax, [rbx]
0x1400ab79e  mov     rcx, [rax]
0x1400ab7a1  add     rcx, 8
0x1400ab7a5  cmp     qword ptr [rcx+18h], 7
0x1400ab7aa  jbe     short loc_1400AB7AF
0x1400ab7ac  mov     rcx, [rcx]
0x1400ab7af  mov     qword ptr [rbp+130h+var_1A0], rcx
0x1400ab7b3  lea     rdx, aVmhostedcontai_8; "VmHostedContainer_SignalProcess"
0x1400ab7ba  lea     rcx, [rbp+130h+var_190]
0x1400ab7be  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400ab7c3  lea     rax, ??_7VmHostedContainer_SignalProcess@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::VmHostedContainer_SignalProcess::`vftable'
0x1400ab7ca  mov     [rbp+130h+var_190], rax
0x1400ab7ce  lea     rdx, [rbp+130h+var_1A0]
0x1400ab7d2  lea     rcx, [rbp+130h+var_190]
0x1400ab7d6  call    ??$StartActivity@PEBG@VmHostedContainer_SignalProcess@TraceProvider@Diagnostics@ComputeService@@QEAAX$$QEAPEBG@Z; ComputeService::Diagnostics::TraceProvider::VmHostedContainer_SignalProcess::StartActivity<ushort const *>(ushort const * &&)
0x1400ab7db  nop
0x1400ab7dc  mov     rcx, [rbx]
0x1400ab7df  xor     r12d, r12d
0x1400ab7e2  mov     [rsp+230h+var_210], r12d; int
0x1400ab7e7  lea     r9, ??_R0?AUBaseStateMachine@Management@ComputeService@@@8; ComputeService::Management::BaseStateMachine `RTTI Type Descriptor'
0x1400ab7ee  lea     r8, ??_R0?AUComputeSystemState@Management@ComputeService@@@8; ComputeService::Management::ComputeSystemState `RTTI Type Descriptor'
0x1400ab7f5  xor     edx, edx
0x1400ab7f7  mov     rcx, [rcx+8]
0x1400ab7fb  call    __RTDynamicCast_0
0x1400ab800  mov     rdx, rax
0x1400ab803  mov     rcx, [rbp+138h]; this
0x1400ab80a  test    rax, rax
0x1400ab80d  jz      loc_1400ABB07
0x1400ab813  mov     [rbp+130h+var_198], r12
0x1400ab817  mov     rax, [r15]
0x1400ab81a  mov     [rsp+230h+var_1F8], rax
0x1400ab81f  mov     rax, [r15+8]
0x1400ab823  mov     [rsp+230h+var_1F0], rax
0x1400ab828  mov     [r15], r12
0x1400ab82b  mov     [r15+8], r12
0x1400ab82f  lea     r13, [r15+10h]
0x1400ab833  mov     rax, [r13+0]
0x1400ab837  mov     [rsp+230h+var_1E8], rax
0x1400ab83c  mov     rax, [r13+8]
0x1400ab840  mov     [rsp+230h+var_1E0], rax
0x1400ab845  mov     [r13+0], r12
0x1400ab849  mov     [r13+8], r12
0x1400ab84d  mov     rax, [r13+10h]
0x1400ab851  mov     [rsp+230h+var_1D8], rax
0x1400ab856  mov     rax, [r13+18h]
0x1400ab85a  mov     [rsp+230h+var_1D0], rax
0x1400ab85f  mov     [r13+10h], r12
0x1400ab863  mov     [r13+18h], r12
0x1400ab867  lea     r9, [rsp+230h+var_1F8]
0x1400ab86c  lea     rcx, [rbp+130h+var_198]
0x1400ab870  call    ?BeginGenericOperation_InState@Management@ComputeService@@YA?AVActiveStateOperation@12@PEAUBaseStateMachine@12@W4SystemState@12@VActiveServerOperation@12@@Z; ComputeService::Management::BeginGenericOperation_InState(ComputeService::Management::BaseStateMachine *,ComputeService::Management::SystemState,ComputeService::Management::ActiveServerOperation)
0x1400ab875  nop
0x1400ab876  mov     rcx, [rbx]
0x1400ab879  mov     [rsp+230h+var_210], r12d; int
0x1400ab87e  lea     r9, ??_R0?AUVmHostedProcessExecutionState@Management@ComputeService@@@8; ComputeService::Management::VmHostedProcessExecutionState `RTTI Type Descriptor'
0x1400ab885  lea     r8, ??_R0?AUComputeSystemState@Management@ComputeService@@@8; ComputeService::Management::ComputeSystemState `RTTI Type Descriptor'
0x1400ab88c  xor     edx, edx
0x1400ab88e  mov     rcx, [rcx+8]
0x1400ab892  call    __RTDynamicCast_0
0x1400ab897  mov     rsi, rax
0x1400ab89a  mov     rcx, [rbp+138h]; this
0x1400ab8a1  test    rax, rax
0x1400ab8a4  jz      loc_1400ABB1F
0x1400ab8aa  cmp     [r14], r12
0x1400ab8ad  jnz     loc_1400ABA1F
0x1400ab8b3  cmp     [r14+10h], r12
0x1400ab8b7  jnz     loc_1400ABA1F
0x1400ab8bd  mov     ebx, r12d
0x1400ab8c0  mov     [rsp+230h+var_200], rbx
0x1400ab8c5  mov     rcx, rax; SRWLock
0x1400ab8c8  call    cs:__imp_AcquireSRWLockExclusive
0x1400ab8ce  mov     qword ptr [rbp+130h+var_1A0], rsi
0x1400ab8d2  mov     rdx, [rsi+8]
0x1400ab8d6  mov     rcx, [rdx+8]
0x1400ab8da  xor     eax, eax
0x1400ab8dc  mov     [rsp+230h+var_1B4], eax
0x1400ab8e0  mov     r8, rdx
0x1400ab8e3  jmp     short loc_1400AB8F7
0x1400ab8e5  cmp     [rcx+20h], edi
0x1400ab8e8  cmovnb  r8, rcx
0x1400ab8ec  lea     rax, [rcx+10h]
0x1400ab8f0  cmovnb  rax, rcx
0x1400ab8f4  mov     rcx, [rax]
0x1400ab8f7  cmp     [rcx+19h], r12b
0x1400ab8fb  jz      short loc_1400AB8E5
0x1400ab8fd  cmp     [r8+19h], r12b
0x1400ab901  jnz     loc_1400ABB49
0x1400ab907  cmp     edi, [r8+20h]
0x1400ab90b  jb      loc_1400ABB49
0x1400ab911  cmp     r8, rdx
0x1400ab914  jz      loc_1400ABB49
0x1400ab91a  lea     rax, [r8+38h]
0x1400ab91e  lea     rcx, [rsp+230h+var_200]
0x1400ab923  cmp     rcx, rax
0x1400ab926  jz      short loc_1400AB933
0x1400ab928  mov     rbx, [rax]
0x1400ab92b  mov     [rsp+230h+var_200], rbx
0x1400ab930  mov     [rax], r12
0x1400ab933  lea     rdx, [rbp+130h+var_1A0]
0x1400ab937  lea     rcx, [rsi+8]
0x1400ab93b  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUProcessState@Management@ComputeService@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@KUProcessState@Management@ComputeService@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUProcessState@Management@ComputeService@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUProcessState@Management@ComputeService@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<ulong,ComputeService::Management::ProcessState,std::less<ulong>,std::allocator<std::pair<ulong const,ComputeService::Management::ProcessState>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,ComputeService::Management::ProcessState>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,ComputeService::Management::ProcessState>>>>)
0x1400ab940  nop
0x1400ab941  mov     rcx, rsi; SRWLock
0x1400ab944  call    cs:__imp_ReleaseSRWLockExclusive
0x1400ab94a  mov     edx, 42Bh; uExitCode
0x1400ab94f  mov     rcx, rbx; hProcess
0x1400ab952  call    cs:__imp_TerminateProcess
0x1400ab958  mov     rcx, [rbp+138h]; this
0x1400ab95f  test    eax, eax
0x1400ab961  jz      loc_1400ABB37
0x1400ab967  lea     rax, [rbx-1]
0x1400ab96b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400ab96f  ja      short loc_1400AB97A
0x1400ab971  mov     rcx, rbx; hObject
0x1400ab974  call    cs:__imp_CloseHandle
0x1400ab97a  xor     edx, edx
0x1400ab97c  lea     rcx, [rbp+130h+var_190]
0x1400ab980  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400ab985  nop
0x1400ab986  lea     rcx, [rbp+130h+var_198]
0x1400ab98a  call    ??1?$unique_ptr@UActiveStateOperationContext@ActiveStateOperation@Management@ComputeService@@U?$default_delete@UActiveStateOperationContext@ActiveStateOperation@Management@ComputeService@@@std@@@std@@QEAA@XZ; std::unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>::~unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>(void)
0x1400ab98f  nop
0x1400ab990  lea     rax, ??_7VmHostedContainer_SignalProcess@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::VmHostedContainer_SignalProcess::`vftable'
0x1400ab997  mov     [rbp+130h+var_190], rax
0x1400ab99b  lea     rcx, [rbp+130h+var_190]
0x1400ab99f  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1400ab9a4  lea     rcx, [rbp+130h+var_190]
0x1400ab9a8  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1400ab9ad  nop
0x1400ab9ae  mov     rcx, r13; this
0x1400ab9b1  call    ??1RetireServerOperation@Management@ComputeService@@QEAA@XZ; ComputeService::Management::RetireServerOperation::~RetireServerOperation(void)
0x1400ab9b6  mov     rbx, [r15+8]
0x1400ab9ba  test    rbx, rbx
0x1400ab9bd  jz      short loc_1400AB9F5
0x1400ab9bf  or      edi, 0FFFFFFFFh
0x1400ab9c2  mov     eax, edi
0x1400ab9c4  lock xadd [rbx+8], eax
0x1400ab9c9  add     eax, edi
0x1400ab9cb  jnz     short loc_1400AB9F5
0x1400ab9cd  mov     rax, [rbx]
0x1400ab9d0  mov     rcx, rbx
0x1400ab9d3  mov     rax, [rax]
0x1400ab9d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ab9db  mov     eax, edi
0x1400ab9dd  lock xadd [rbx+0Ch], eax
0x1400ab9e2  add     eax, edi
0x1400ab9e4  jnz     short loc_1400AB9F5
0x1400ab9e6  mov     rax, [rbx]
0x1400ab9e9  mov     rcx, rbx
0x1400ab9ec  mov     rax, [rax+8]
0x1400ab9f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ab9f5  mov     rcx, [rbp+130h+var_40]
0x1400ab9fc  xor     rcx, rsp; StackCookie
0x1400ab9ff  call    __security_check_cookie
0x1400aba04  mov     rbx, [rsp+230h+arg_0]
0x1400aba0c  add     rsp, 200h
0x1400aba13  pop     r15
0x1400aba15  pop     r14
0x1400aba17  pop     r13
0x1400aba19  pop     r12
0x1400aba1b  pop     rdi
0x1400aba1c  pop     rsi
0x1400aba1d  pop     rbp
0x1400aba1e  retn
0x1400aba1f  mov     rcx, [rbx]
0x1400aba22  mov     [rsp+230h+var_210], r12d; int
0x1400aba27  lea     r9, ??_R0?AUServerContainerState@Management@ComputeService@@@8; ComputeService::Management::ServerContainerState `RTTI Type Descriptor'
0x1400aba2e  lea     r8, ??_R0?AUComputeSystemState@Management@ComputeService@@@8; ComputeService::Management::ComputeSystemState `RTTI Type Descriptor'
0x1400aba35  xor     edx, edx
0x1400aba37  mov     rcx, [rcx+8]
0x1400aba3b  call    __RTDynamicCast_0
0x1400aba40  mov     r12, rax
0x1400aba43  mov     rcx, [rbp+138h]; this
0x1400aba4a  test    rax, rax
0x1400aba4d  jz      loc_1400ABB68
0x1400aba53  mov     [rbp+130h+var_1A0], 0
0x1400aba5a  lea     r8, [rbp+130h+var_1A0]
0x1400aba5e  lea     rdx, [rsp+230h+var_1C0]
0x1400aba63  mov     rcx, r14
0x1400aba66  call    ??$Unmarshal@USignalProcessOptions@Options@Schema@@@?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEBA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@PEAUSignalProcessOptions@Options@Schema@@@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Schema::Options::SignalProcessOptions>(Schema::Options::SignalProcessOptions *)
0x1400aba6b  nop
0x1400aba6c  cmp     byte ptr [rax], 0
0x1400aba6f  jz      loc_1400ABB80
0x1400aba75  lea     rcx, [rsp+230h+var_1B8]
0x1400aba7a  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x1400aba7f  mov     rax, [rbx]
0x1400aba82  mov     r8, [rax]
0x1400aba85  mov     rcx, [rbp+138h]; this
0x1400aba8c  test    r8, r8
0x1400aba8f  jz      short loc_1400ABADA
0x1400aba91  mov     rdx, rbx
0x1400aba94  call    ?IsHostProcessContainer@ProcessManagement@VmHostedContainer@Management@ComputeService@@AEAA_NAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@PEBUComputeSystemConfiguration@34@@Z; ComputeService::Management::VmHostedContainer::ProcessManagement::IsHostProcessContainer(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::ComputeSystemConfiguration const *)
0x1400aba99  test    al, al
0x1400aba9b  jz      short loc_1400ABAAC
0x1400aba9d  mov     edx, [rbp+130h+var_1A0]; unsigned int
0x1400abaa0  mov     ecx, edi; this
0x1400abaa2  call    ?SignalProcess@CExec@@YAXKI@Z; CExec::SignalProcess(ulong,uint)
0x1400abaa7  jmp     loc_1400AB97A
0x1400abaac  mov     ebx, [rbp+130h+var_1A0]
0x1400abaaf  mov     r8d, edi; struct ComputeService::Management::ServerContainerState *
0x1400abab2  mov     rdx, r12; struct ComputeService::Management::VmHostedProcessExecutionState *
0x1400abab5  mov     rcx, rsi; this
0x1400abab8  call    ?GetServiceBinding@VmHostedContainer@Management@ComputeService@@YAPEAXPEAUVmHostedProcessExecutionState@23@PEAUServerContainerState@23@K@Z; ComputeService::Management::VmHostedContainer::GetServiceBinding(ComputeService::Management::VmHostedProcessExecutionState *,ComputeService::Management::ServerContainerState *,ulong)
0x1400ababd  mov     r8d, ebx
0x1400abac0  mov     edx, edi
0x1400abac2  mov     rcx, rax
0x1400abac5  call    ContainerSignalProcess
0x1400abaca  mov     rcx, [rbp+138h]; this
0x1400abad1  test    eax, eax
0x1400abad3  js      short loc_1400ABAF2
0x1400abad5  jmp     loc_1400AB97A
0x1400abada  mov     r9d, 80004001h; char *
0x1400abae0  lea     r8, aOnecoreVmCompu_32; "onecore\\vm\\compute\\management\\compu"...
0x1400abae7  mov     edx, 5Dh ; ']'; void *
0x1400abaec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400abaf2  mov     r9d, eax; char *
0x1400abaf5  lea     r8, aOnecoreVmCompu_46; "onecore\\vm\\compute\\management\\orche"...
0x1400abafc  mov     edx, 1B7h; void *
0x1400abb01  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400abb07  mov     r9d, 80004001h; char *
0x1400abb0d  lea     r8, aOnecoreVmCompu_32; "onecore\\vm\\compute\\management\\compu"...
0x1400abb14  mov     edx, 5Dh ; ']'; void *
0x1400abb19  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400abb1f  mov     r9d, 80004001h; char *
0x1400abb25  lea     r8, aOnecoreVmCompu_32; "onecore\\vm\\compute\\management\\compu"...
0x1400abb2c  mov     edx, 5Dh ; ']'; void *
0x1400abb31  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400abb37  lea     r8, aOnecoreVmCompu_46; "onecore\\vm\\compute\\management\\orche"...
0x1400abb3e  mov     edx, 1CBh; void *
0x1400abb43  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400abb49  mov     rcx, [rbp+138h]; this
0x1400abb50  mov     r9d, 490h; char *
0x1400abb56  lea     r8, aOnecoreVmCompu_46; "onecore\\vm\\compute\\management\\orche"...
0x1400abb5d  mov     edx, 1C4h; void *
0x1400abb62  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400abb68  mov     r9d, 80004001h; char *
0x1400abb6e  lea     r8, aOnecoreVmCompu_32; "onecore\\vm\\compute\\management\\compu"...
0x1400abb75  mov     edx, 5Dh ; ']'; void *
0x1400abb7a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400abb80  lea     rcx, [rax+8]
0x1400abb84  call    ??$?CVComputeSystem@Management@ComputeService@@$0A@@?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@QEBAPEAVComputeSystem@Management@ComputeService@@XZ; std::shared_ptr<ComputeService::Management::ComputeSystem>::operator-><ComputeService::Management::ComputeSystem,0>(void)
0x1400abb89  mov     rcx, rax
0x1400abb8c  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x1400abb91  mov     rdx, rax
0x1400abb94  mov     ecx, 0C037010Dh
0x1400abb99  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1400abb9e  mov     r9d, eax; char *
0x1400abba1  mov     rcx, [rbp+138h]; this
0x1400abba8  mov     [rsp+230h+var_208], rdx; char *
0x1400abbad  lea     rax, aLs; "%ls"
0x1400abbb4  mov     qword ptr [rsp+230h+var_210], rax; int
0x1400abbb9  lea     r8, aOnecoreInterna; "OneCore\\Internal\\VM\\inc\\MarshalUtil"...
0x1400abbc0  mov     edx, 1Fh; void *
0x1400abbc5  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
