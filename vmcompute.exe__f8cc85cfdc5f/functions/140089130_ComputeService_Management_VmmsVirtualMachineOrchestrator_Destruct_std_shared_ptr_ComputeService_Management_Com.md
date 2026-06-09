# ComputeService::Management::VmmsVirtualMachineOrchestrator::Destruct(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::DestructInfo const &)

- ea: `0x140089130`
- end: `0x1400894f3`
- name: `?Destruct@VmmsVirtualMachineOrchestrator@Management@ComputeService@@UEAA_NAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@AEBUDestructInfo@23@@Z`
- size: `963`
- prototype: ``
- caller_count: `0`
- callee_count: `30`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x14001629c`
- `0x140017040`
- `0x14001bce0`
- `0x140020890`
- `0x140021ea4`
- `0x14002f9e8`
- `0x14005bdc8`
- `0x1400602cc`
- `0x140080124`
- `0x1400890f8`
- `0x140089130`
- `0x1400894fc`
- `0x14008a2c4`
- `0x14008a83c`
- `0x14008b6f0`
- `0x14008b8b4`
- `0x14008c800`
- `0x14008d084`
- `0x14008d230`
- `0x14009236c`
- `0x1400c40e0`
- `0x1400f3b1c`
- `0x1400f5344`
- `0x140101940`
- `0x1401332f0`
- `0x140133314`
- `0x140134048`
- `0x1401d8e88`
- `0x1402373c0`
- `0x1402a0e5c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x14008934f`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x14008934f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008935f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008935f`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x1400893cb`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x1400893ff`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x1400893cb`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x1400893ff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1400892e9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1400892e9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1400892d1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1400892d1`

## string_xrefs

- `0x1400891ec`: `onecore\vm\compute\management\computesystem\computesystem.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall ComputeService::Management::VmmsVirtualMachineOrchestrator::Destruct(
        __int64 a1,
        __int64 a2,
        _DWORD *a3)
{
  _QWORD *v5; // rcx
  __int64 v6; // rax
  __int64 v7; // r15
  volatile signed __int8 *v8; // rcx
  __int64 v9; // r14
  unsigned int v10; // edi
  _DWORD *v11; // rsi
  __int64 v12; // rax
  struct _TP_WAIT *v13; // rcx
  char v14; // bl
  unsigned int v15; // r9d
  void *v16; // rdx
  const struct _GUID *v17; // r8
  const struct _GUID *v18; // r8
  const struct ComputeService::Vmwp::WorkerProcessContext *v19; // rdx
  enum ResourceType v20; // r8d
  const unsigned __int16 *v21; // rdx
  ComputeService::RecoveryStore *v22; // rcx
  int v23; // ebx
  void *v24; // rax
  int v25; // r8d
  int v26; // r9d
  std::_Ref_count_base *v28[2]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v29; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v30[32]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v31[56]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE CompareAddress[16]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v33[336]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  memset_0(v33, 0, sizeof(v33));
  LODWORD(v28[0]) = *a3;
  v5 = (_QWORD *)(**(_QWORD **)a2 + 8LL);
  if ( *(_QWORD *)(**(_QWORD **)a2 + 32LL) > 7u )
    v5 = (_QWORD *)*v5;
  v29 = v5;
  ComputeService::Diagnostics::TraceProvider::VirtualMachine_Destruct::Start<unsigned short const *,unsigned int,int const &>(
    v33,
    &v29,
    v28,
    a3 + 2);
  v6 = _RTDynamicCast_0(
         *(_QWORD *)(*(_QWORD *)a2 + 8LL),
         0,
         &ComputeService::Management::ComputeSystemState `RTTI Type Descriptor',
         &ComputeService::Management::VirtualMachineState `RTTI Type Descriptor');
  v7 = v6;
  if ( !v6 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\vm\\compute\\management\\computesystem\\computesystem.h",
      (const char *)0x80004001LL,
      0);
  v8 = (volatile signed __int8 *)(v6 + 2600);
  if ( (*(_BYTE *)a3 & 8) != 0 )
    *v8 = 1;
  if ( !_InterlockedCompareExchange8(v8, 1, 0) )
  {
    v9 = *(_QWORD *)(v6 + 112);
    v10 = ComputeService::Management::StatusFromDestructFlags((unsigned int)*a3);
    v11 = operator new(0x40u);
    v29 = v11;
    *(_OWORD *)v11 = 0;
    v11[2] = 1;
    v11[3] = 1;
    *(_QWORD *)v11 = &std::_Ref_count_obj2<ComputeService::Management::OperationResult>::`vftable';
    std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(v30);
    ComputeService::Management::OperationResult::OperationResult(v11 + 4, v10, v12);
    v28[0] = (std::_Ref_count_base *)(v11 + 4);
    v28[1] = (std::_Ref_count_base *)v11;
    ComputeService::Management::CancellationProvider::TryCancel(v9, v31, v28);
    std::_Optional_destruct_base<ComputeService::Management::OperationResult,0>::~_Optional_destruct_base<ComputeService::Management::OperationResult,0>(v31);
    if ( v28[1] )
      std::_Ref_count_base::_Decref(v28[1]);
    if ( (*a3 & 0x1000) == 0 )
    {
      v13 = *(struct _TP_WAIT **)(v7 + 664);
      if ( v13 )
      {
        SetThreadpoolWait(v13, 0, 0);
        WaitForThreadpoolWaitCallbacks(*(PTP_WAIT *)(v7 + 664), 1);
      }
      if ( *(_QWORD *)(v7 + 640) )
      {
        v28[0] = 0;
        wil::AcquireSRWLockExclusive(v28, v7 + 2640);
        *(_BYTE *)(v7 + 2649) = 1;
        v14 = *(_BYTE *)(v7 + 2648);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v28);
        while ( v14 )
        {
          CompareAddress[0] = 0;
          if ( !WaitOnAddress((volatile void *)(v7 + 2648), CompareAddress, 1u, 0x493E0u) && GetLastError() == 1460 )
            wil::details::SetEvent(*(wil::details **)(v7 + 2688), v16);
          v28[0] = 0;
          wil::AcquireSRWLockShared(v28, v7 + 2640);
          v14 = *(_BYTE *)(v7 + 2648);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v28);
        }
        v17 = (const struct _GUID *)*(unsigned int *)(v7 + 680);
        if ( (_DWORD)v17 != -1 )
        {
          Vml::VmComEventDisconnect(*(Vml **)(v7 + 640), (struct IUnknown *)&IID_IVmGuestCrashEvents, v17, v15);
          CoDisconnectObject(*(LPUNKNOWN *)(v7 + 672), 0);
        }
        v18 = (const struct _GUID *)*(unsigned int *)(v7 + 696);
        if ( (_DWORD)v18 != -1 )
        {
          Vml::VmComEventDisconnect(*(Vml **)(v7 + 640), (struct IUnknown *)&IID_IVmVirtualMachineEvents, v18, v15);
          CoDisconnectObject(*(LPUNKNOWN *)(v7 + 688), 0);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&void CloseThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
      v7 + 664,
      0);
    if ( (*a3 & 0x9000) == 0 )
      ComputeService::Vmwp::TerminateWorkerProcess((ComputeService::Vmwp *)(v7 + 624), v19);
    ComputeService::Resource::FreeResourceType((ComputeService::Resource *)(v7 + 752), 0, v20);
    wil::com_ptr_t<IVmHandleBrokerManager,wil::err_exception_policy>::reset(v7 + 1736);
    v22 = (ComputeService::RecoveryStore *)(**(_QWORD **)a2 + 8LL);
    if ( *(_QWORD *)(**(_QWORD **)a2 + 32LL) > 7u )
      v22 = *(ComputeService::RecoveryStore **)v22;
    ComputeService::RecoveryStore::RemoveSystem(v22, v21);
    v23 = ~(unsigned __int8)(*a3 >> 14) & 2 | 1;
    v24 = (void *)Marshal::ToJson<Schema::Responses::System::SystemExitStatus const &,>(v30, a3 + 2);
    ComputeService::ComputeSystemUtilities::NotifyComputeSystem(*(_QWORD *)a2, v23, v25, v26, 0, v24);
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v30);
    ComputeService::Telemetry::DecrementDensityCounters(*(unsigned int *)(**(_QWORD **)a2 + 40LL));
  }
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v33,
    0);
  ComputeService::Diagnostics::TraceProvider::VirtualMachine_Destruct::~VirtualMachine_Destruct((ComputeService::Diagnostics::TraceProvider::VirtualMachine_Destruct *)v33);
  return 0;
}

```

## disassembly

```asm
0x140089130  mov     [rsp-8+arg_0], rbx
0x140089135  push    rbp
0x140089136  push    rsi
0x140089137  push    rdi
0x140089138  push    r12
0x14008913a  push    r13
0x14008913c  push    r14
0x14008913e  push    r15
0x140089140  lea     rbp, [rsp-110h]
0x140089148  sub     rsp, 210h
0x14008914f  mov     rax, cs:__security_cookie
0x140089156  xor     rax, rsp
0x140089159  mov     [rbp+140h+var_40], rax
0x140089160  mov     r12, r8
0x140089163  mov     r13, rdx
0x140089166  xor     edx, edx; Val
0x140089168  mov     r8d, 150h; Size
0x14008916e  lea     rcx, [rbp+140h+var_190]; void *
0x140089172  call    memset_0
0x140089177  mov     eax, [r12]
0x14008917b  mov     dword ptr [rsp+240h+var_210], eax
0x14008917f  mov     rax, [r13+0]
0x140089183  mov     rcx, [rax]
0x140089186  add     rcx, 8
0x14008918a  cmp     qword ptr [rcx+18h], 7
0x14008918f  jbe     short loc_140089194
0x140089191  mov     rcx, [rcx]
0x140089194  mov     [rsp+240h+var_200], rcx
0x140089199  lea     r9, [r12+8]
0x14008919e  lea     r8, [rsp+240h+var_210]
0x1400891a3  lea     rdx, [rsp+240h+var_200]
0x1400891a8  lea     rcx, [rbp+140h+var_190]
0x1400891ac  call    ??$Start@PEBGIAEBH@VirtualMachine_Destruct@TraceProvider@Diagnostics@ComputeService@@SA?AV0123@$$QEAPEBG$$QEAIAEBH@Z; ComputeService::Diagnostics::TraceProvider::VirtualMachine_Destruct::Start<ushort const *,uint,int const &>(ushort const * &&,uint &&,int const &)
0x1400891b1  nop
0x1400891b2  mov     rcx, [r13+0]
0x1400891b6  mov     [rsp+240h+var_220], 0; int
0x1400891be  lea     r9, ??_R0?AUVirtualMachineState@Management@ComputeService@@@8; ComputeService::Management::VirtualMachineState `RTTI Type Descriptor'
0x1400891c5  lea     r8, ??_R0?AUComputeSystemState@Management@ComputeService@@@8; ComputeService::Management::ComputeSystemState `RTTI Type Descriptor'
0x1400891cc  xor     edx, edx
0x1400891ce  mov     rcx, [rcx+8]
0x1400891d2  call    __RTDynamicCast_0
0x1400891d7  mov     r15, rax
0x1400891da  mov     rcx, [rbp+148h]; this
0x1400891e1  test    rax, rax
0x1400891e4  jnz     short loc_1400891FC
0x1400891e6  mov     r9d, 80004001h; char *
0x1400891ec  lea     r8, aOnecoreVmCompu_31; "onecore\\vm\\compute\\management\\compu"...
0x1400891f3  lea     edx, [rax+5Dh]; void *
0x1400891f6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400891fc  lea     rcx, [rax+0A28h]
0x140089203  mov     ebx, 1
0x140089208  test    byte ptr [r12], 8
0x14008920d  jz      short loc_140089213
0x14008920f  mov     eax, ebx
0x140089211  xchg    al, [rcx]
0x140089213  xor     eax, eax
0x140089215  lock cmpxchg [rcx], bl
0x140089219  jnz     loc_1400894B1
0x14008921f  mov     r14, [r15+70h]
0x140089223  mov     ecx, [r12]
0x140089227  call    ?StatusFromDestructFlags@Management@ComputeService@@YAJW4DestructFlags@12@@Z; ComputeService::Management::StatusFromDestructFlags(ComputeService::Management::DestructFlags)
0x14008922c  mov     edi, eax
0x14008922e  mov     ecx, 40h ; '@'; Size
0x140089233  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140089238  mov     rsi, rax
0x14008923b  mov     [rsp+240h+var_200], rax
0x140089240  xorps   xmm0, xmm0
0x140089243  movups  xmmword ptr [rax], xmm0
0x140089246  mov     [rax+8], ebx
0x140089249  mov     [rax+0Ch], ebx
0x14008924c  lea     rax, ??_7?$_Ref_count_obj2@UOperationResult@Management@ComputeService@@@std@@6B@; const std::_Ref_count_obj2<ComputeService::Management::OperationResult>::`vftable'
0x140089253  mov     [rsi], rax
0x140089256  lea     rbx, [rsi+10h]
0x14008925a  lea     rcx, [rsp+240h+var_1F8]
0x14008925f  call    ??0?$vector@UVpSubnodeMetadata@VirtualMachine@Config@@V?$allocator@UVpSubnodeMetadata@VirtualMachine@Config@@@std@@@std@@QEAA@XZ; std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(void)
0x140089264  mov     r8, rax
0x140089267  mov     edx, edi
0x140089269  mov     rcx, rbx
0x14008926c  call    ??0OperationResult@Management@ComputeService@@QEAA@JV?$vector@UAttributionRecord@Attribution@Responses@Schema@@V?$allocator@UAttributionRecord@Attribution@Responses@Schema@@@std@@@std@@@Z; ComputeService::Management::OperationResult::OperationResult(long,std::vector<Schema::Responses::Attribution::AttributionRecord>)
0x140089271  xorps   xmm0, xmm0
0x140089274  movups  xmmword ptr [rsp+240h+var_210], xmm0
0x140089279  mov     [rsp+240h+var_210], rbx
0x14008927e  mov     [rsp+240h+var_210+8], rsi
0x140089283  lea     r8, [rsp+240h+var_210]
0x140089288  lea     rdx, [rsp+240h+var_1D8]
0x14008928d  mov     rcx, r14
0x140089290  call    ?TryCancel@CancellationProvider@Management@ComputeService@@QEAA?AV?$optional@UOperationResult@Management@ComputeService@@@std@@AEBV?$shared_ptr@UOperationResult@Management@ComputeService@@@5@@Z; ComputeService::Management::CancellationProvider::TryCancel(std::shared_ptr<ComputeService::Management::OperationResult> const &)
0x140089295  lea     rcx, [rsp+240h+var_1D8]
0x14008929a  call    ??1?$_Optional_destruct_base@UOperationResult@Management@ComputeService@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<ComputeService::Management::OperationResult,0>::~_Optional_destruct_base<ComputeService::Management::OperationResult,0>(void)
0x14008929f  nop
0x1400892a0  mov     rcx, [rsp+240h+var_210+8]; this
0x1400892a5  xor     r14d, r14d
0x1400892a8  test    rcx, rcx
0x1400892ab  jz      short loc_1400892B2
0x1400892ad  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400892b2  test    dword ptr [r12], 1000h
0x1400892ba  jnz     loc_14008940B
0x1400892c0  mov     rcx, [r15+298h]; pwa
0x1400892c7  test    rcx, rcx
0x1400892ca  jz      short loc_1400892F5
0x1400892cc  xor     r8d, r8d; pftTimeout
0x1400892cf  xor     edx, edx; h
0x1400892d1  call    cs:__imp_SetThreadpoolWait
0x1400892d8  nop     dword ptr [rax+rax+00h]
0x1400892dd  mov     edx, 1; fCancelPendingCallbacks
0x1400892e2  mov     rcx, [r15+298h]; pwa
0x1400892e9  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1400892f0  nop     dword ptr [rax+rax+00h]
0x1400892f5  cmp     [r15+280h], r14
0x1400892fc  jz      loc_14008940B
0x140089302  mov     [rsp+240h+var_210], r14
0x140089307  lea     rsi, [r15+0A50h]
0x14008930e  mov     rdx, rsi
0x140089311  lea     rcx, [rsp+240h+var_210]
0x140089316  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x14008931b  mov     byte ptr [r15+0A59h], 1
0x140089323  lea     rdi, [r15+0A58h]
0x14008932a  mov     bl, [rdi]
0x14008932c  lea     rcx, [rsp+240h+var_210]
0x140089331  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140089336  jmp     short loc_14008939C
0x140089338  mov     [rbp+140h+CompareAddress], r14b
0x14008933c  mov     r9d, 493E0h; dwMilliseconds
0x140089342  mov     r8d, 1; AddressSize
0x140089348  lea     rdx, [rbp+140h+CompareAddress]; CompareAddress
0x14008934c  mov     rcx, rdi; Address
0x14008934f  call    cs:__imp_WaitOnAddress
0x140089356  nop     dword ptr [rax+rax+00h]
0x14008935b  test    eax, eax
0x14008935d  jnz     short loc_14008937E
0x14008935f  call    cs:__imp_GetLastError
0x140089366  nop     dword ptr [rax+rax+00h]
0x14008936b  cmp     eax, 5B4h
0x140089370  jnz     short loc_14008937E
0x140089372  mov     rcx, [r15+0A80h]; this
0x140089379  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x14008937e  mov     [rsp+240h+var_210], r14
0x140089383  mov     rdx, rsi
0x140089386  lea     rcx, [rsp+240h+var_210]
0x14008938b  call    ?AcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockShared(_RTL_SRWLOCK *)
0x140089390  mov     bl, [rdi]
0x140089392  lea     rcx, [rsp+240h+var_210]
0x140089397  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14008939c  test    bl, bl
0x14008939e  jnz     short loc_140089338
0x1400893a0  mov     r8d, [r15+2A8h]; struct _GUID *
0x1400893a7  or      ebx, 0FFFFFFFFh
0x1400893aa  cmp     r8d, ebx
0x1400893ad  jz      short loc_1400893D7
0x1400893af  lea     rdx, IID_IVmGuestCrashEvents; struct IUnknown *
0x1400893b6  mov     rcx, [r15+280h]; this
0x1400893bd  call    ?VmComEventDisconnect@Vml@@YAXPEAUIUnknown@@AEBU_GUID@@K@Z; Vml::VmComEventDisconnect(IUnknown *,_GUID const &,ulong)
0x1400893c2  xor     edx, edx; dwReserved
0x1400893c4  mov     rcx, [r15+2A0h]; pUnk
0x1400893cb  call    cs:__imp_CoDisconnectObject
0x1400893d2  nop     dword ptr [rax+rax+00h]
0x1400893d7  mov     r8d, [r15+2B8h]; struct _GUID *
0x1400893de  cmp     r8d, ebx
0x1400893e1  jz      short loc_14008940B
0x1400893e3  lea     rdx, IID_IVmVirtualMachineEvents; struct IUnknown *
0x1400893ea  mov     rcx, [r15+280h]; this
0x1400893f1  call    ?VmComEventDisconnect@Vml@@YAXPEAUIUnknown@@AEBU_GUID@@K@Z; Vml::VmComEventDisconnect(IUnknown *,_GUID const &,ulong)
0x1400893f6  xor     edx, edx; dwReserved
0x1400893f8  mov     rcx, [r15+2B0h]; pUnk
0x1400893ff  call    cs:__imp_CoDisconnectObject
0x140089406  nop     dword ptr [rax+rax+00h]
0x14008940b  lea     rcx, [r15+298h]
0x140089412  xor     edx, edx
0x140089414  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?CloseThreadpoolWait@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&CloseThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x140089419  test    dword ptr [r12], 9000h
0x140089421  jnz     short loc_14008942F
0x140089423  lea     rcx, [r15+270h]; this
0x14008942a  call    ?TerminateWorkerProcess@Vmwp@ComputeService@@YAXAEBUWorkerProcessContext@12@@Z; ComputeService::Vmwp::TerminateWorkerProcess(ComputeService::Vmwp::WorkerProcessContext const &)
0x14008942f  lea     rcx, [r15+2F0h]; this
0x140089436  xor     edx, edx; struct ComputeService::Resource::ResourceState *
0x140089438  call    ?FreeResourceType@Resource@ComputeService@@YAXAEBUResourceState@12@W4ResourceType@12@@Z; ComputeService::Resource::FreeResourceType(ComputeService::Resource::ResourceState const &,ComputeService::Resource::ResourceType)
0x14008943d  lea     rcx, [r15+6C8h]
0x140089444  call    ?reset@?$com_ptr_t@UIVmHandleBrokerManager@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IVmHandleBrokerManager,wil::err_exception_policy>::reset(void)
0x140089449  mov     rax, [r13+0]
0x14008944d  mov     rcx, [rax]
0x140089450  add     rcx, 8
0x140089454  cmp     qword ptr [rcx+18h], 7
0x140089459  jbe     short loc_14008945E
0x14008945b  mov     rcx, [rcx]; this
0x14008945e  call    ?RemoveSystem@RecoveryStore@ComputeService@@YAXPEBG@Z; ComputeService::RecoveryStore::RemoveSystem(ushort const *)
0x140089463  mov     ebx, [r12]
0x140089467  shr     ebx, 0Eh
0x14008946a  not     ebx
0x14008946c  and     ebx, 2
0x14008946f  or      ebx, 1
0x140089472  lea     rdx, [r12+8]
0x140089477  lea     rcx, [rsp+240h+var_1F8]
0x14008947c  call    ??$ToJson@AEBUSystemExitStatus@System@Responses@Schema@@$$V@Marshal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUSystemExitStatus@System@Responses@Schema@@W4MarshalFlags@0@@Z; Marshal::ToJson<Schema::Responses::System::SystemExitStatus const &,>(Schema::Responses::System::SystemExitStatus const &,Marshal::MarshalFlags)
0x140089481  nop
0x140089482  mov     [rsp+240h+var_218], rax; void *
0x140089487  mov     [rsp+240h+var_220], r14d; int
0x14008948c  mov     edx, ebx; int
0x14008948e  mov     rcx, [r13+0]; int
0x140089492  call    ?NotifyComputeSystem@ComputeSystemUtilities@ComputeService@@YAXPEAVComputeSystem@Management@2@W4NotificationType@System@Compute@@W4ActiveOperation@67@_KJ$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ComputeService::ComputeSystemUtilities::NotifyComputeSystem(ComputeService::Management::ComputeSystem *,Compute::System::NotificationType,Compute::System::ActiveOperation,unsigned __int64,long,std::wstring &&)
0x140089497  nop
0x140089498  lea     rcx, [rsp+240h+var_1F8]; this
0x14008949d  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400894a2  mov     rax, [r13+0]
0x1400894a6  mov     rcx, [rax]
0x1400894a9  mov     ecx, [rcx+28h]
0x1400894ac  call    ?DecrementDensityCounters@Telemetry@ComputeService@@YAXW4ComputeSystemType@Management@2@@Z; ComputeService::Telemetry::DecrementDensityCounters(ComputeService::Management::ComputeSystemType)
0x1400894b1  xor     edx, edx
0x1400894b3  lea     rcx, [rbp+140h+var_190]
0x1400894b7  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400894bc  nop
0x1400894bd  lea     rcx, [rbp+140h+var_190]; this
0x1400894c1  call    ??1VirtualMachine_Destruct@TraceProvider@Diagnostics@ComputeService@@QEAA@XZ; ComputeService::Diagnostics::TraceProvider::VirtualMachine_Destruct::~VirtualMachine_Destruct(void)
0x1400894c6  xor     al, al
0x1400894c8  mov     rcx, [rbp+140h+var_40]
0x1400894cf  xor     rcx, rsp; StackCookie
0x1400894d2  call    __security_check_cookie
0x1400894d7  mov     rbx, [rsp+240h+arg_0]
0x1400894df  add     rsp, 210h
0x1400894e6  pop     r15
0x1400894e8  pop     r14
0x1400894ea  pop     r13
0x1400894ec  pop     r12
0x1400894ee  pop     rdi
0x1400894ef  pop     rsi
0x1400894f0  pop     rbp
0x1400894f1  retn
```
