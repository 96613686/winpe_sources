# ComputeService::Management::UtilityVmTemplateOrchestrator::Construct(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::OrchestratorCallContext,IVmHandleBrokerManager *,ComputeService::Management::IComputeSystemStore *)

- ea: `0x14009dad0`
- end: `0x14009e225`
- name: `?Construct@UtilityVmTemplateOrchestrator@Management@ComputeService@@UEAA_NAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@UOrchestratorCallContext@23@PEAUIVmHandleBrokerManager@@PEAVIComputeSystemStore@23@@Z`
- size: `1877`
- prototype: ``
- caller_count: `0`
- callee_count: `56`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1400142a0`
- `0x14001629c`
- `0x140017040`
- `0x14001bce0`
- `0x14001f12c`
- `0x14001fc70`
- `0x140020890`
- `0x140021de0`
- `0x140021ea4`
- `0x140021ff4`
- `0x14002716c`
- `0x14002885c`
- `0x14002a9cc`
- `0x14002f9e8`
- `0x1400421f0`
- `0x14007da0c`
- `0x14007deb8`
- `0x14007ef00`
- `0x140080124`
- `0x140080180`
- `0x14008d924`
- `0x14009dad0`
- `0x14009f344`
- `0x1400a0058`
- `0x1400a4514`
- `0x1400a7470`
- `0x1400b3bc4`
- `0x1400b5c8c`
- `0x1400b61e0`
- `0x1400bcc70`
- `0x1400bf5c0`
- `0x1400bf7bc`
- `0x1400bfbc0`
- `0x1400bfdac`
- `0x1400c40e0`
- `0x1400c7d80`
- `0x1400cd89c`
- `0x1400da2a0`
- `0x1400e74e4`
- `0x1400f4c18`
- `0x140104510`
- `0x1401332f0`
- `0x140134048`
- `0x14016719c`
- `0x14017d808`
- `0x14017d83c`
- `0x14017d868`
- `0x14017df6c`
- `0x14017e450`
- `0x14017fa48`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14009dc93`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14009dc93`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14009e13e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14009e13e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14009dc4a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14009dc4a`

## string_xrefs

- `0x14009dcbf`: `onecore\vm\compute\management\orchestration\hypervcontainer\utilityvmtemplateorchestrator.cpp`
- `0x14009e0d8`: `onecore\vm\compute\management\orchestration\hypervcontainer\utilityvmtemplateorchestrator.cpp`
- `0x14009db40`: `UtilityVmTemplate_Construct`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
char __fastcall ComputeService::Management::UtilityVmTemplateOrchestrator::Construct(
        __int64 a1,
        _QWORD *a2,
        ComputeService::Management::Details *a3)
{
  _OWORD *v6; // rcx
  __int64 v7; // rdi
  _QWORD *v8; // rcx
  PTP_WAIT ThreadpoolWait; // rax
  const char *v10; // r9
  struct Schema::Registry::RegistryChanges *v11; // rdx
  struct Schema::Registry::RegistryChanges *v12; // rdx
  __int64 v13; // rax
  ComputeService::HyperVContainer *v14; // rcx
  __int64 v15; // rbx
  char NumaSpanningSetting; // si
  __int64 UtilityVmDataRoot; // rax
  ComputeService::HyperVContainer::Details *v18; // rdx
  ComputeService::HyperVContainer::Details **v19; // rax
  _QWORD *v20; // rsi
  enum ResourceType v21; // r8d
  struct VmRepository *v22; // r9
  __int64 v23; // rdx
  __int64 inited; // rax
  __int64 *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rdx
  std::_Ref_count_base *v28; // rcx
  int CancellationToken; // eax
  __int64 v30; // rax
  __int64 v31; // rax
  struct _FILETIME v32; // rcx
  const struct ComputeService::Vmwp::WorkerProcessContext *v33; // rbx
  int v34; // ecx
  int v35; // r8d
  int v36; // eax
  struct IVmSimpleTask *v37; // r8
  unsigned int v38; // r9d
  struct ComputeService::Management::TemplateVmSystemState *v39; // rdx
  const struct ComputeService::Management::TemplateVmSystemState *v40; // r8
  int v42; // [rsp+20h] [rbp-B08h]
  int v43; // [rsp+70h] [rbp-AB8h] BYREF
  _OWORD *v44; // [rsp+78h] [rbp-AB0h] BYREF
  const struct ComputeService::Vmwp::WorkerProcessContext *v45; // [rsp+80h] [rbp-AA8h] BYREF
  std::_Ref_count_base *v46; // [rsp+88h] [rbp-AA0h]
  _QWORD v47[2]; // [rsp+90h] [rbp-A98h] BYREF
  __int64 v48; // [rsp+A0h] [rbp-A88h]
  _QWORD v49[2]; // [rsp+A8h] [rbp-A80h] BYREF
  __int64 v50; // [rsp+B8h] [rbp-A70h] BYREF
  WCHAR pszPathOut[4]; // [rsp+C0h] [rbp-A68h] BYREF
  ComputeService::Management::Details **v52; // [rsp+C8h] [rbp-A60h]
  WCHAR *v53; // [rsp+F8h] [rbp-A30h]
  _QWORD v54[10]; // [rsp+100h] [rbp-A28h] BYREF
  _BYTE v55[856]; // [rsp+150h] [rbp-9D8h] BYREF
  ComputeService::Management::Details *v56[2]; // [rsp+4A8h] [rbp-680h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+4B8h] [rbp-670h] BYREF
  _BYTE v58[24]; // [rsp+4C0h] [rbp-668h] BYREF
  _BYTE v59[24]; // [rsp+4D8h] [rbp-650h] BYREF
  _BYTE v60[32]; // [rsp+4F0h] [rbp-638h] BYREF
  _QWORD v61[42]; // [rsp+510h] [rbp-618h] BYREF
  _BYTE v62[12]; // [rsp+660h] [rbp-4C8h] BYREF
  int v63; // [rsp+66Ch] [rbp-4BCh]
  _BYTE v64[160]; // [rsp+790h] [rbp-398h] BYREF
  _BYTE v65[704]; // [rsp+830h] [rbp-2F8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B28h] [rbp+0h]

  v56[1] = a3;
  v43 = 0;
  memset_0(v61, 0, sizeof(v61));
  v6 = (_OWORD *)(*(_QWORD *)*a2 + 8LL);
  if ( *(_QWORD *)(*(_QWORD *)*a2 + 32LL) > 7u )
    v6 = *(_OWORD **)v6;
  v44 = v6;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v61,
    "UtilityVmTemplate_Construct");
  v61[0] = &ComputeService::Diagnostics::TraceProvider::UtilityVmTemplate_Construct::`vftable';
  ComputeService::Diagnostics::TraceProvider::UtilityVmTemplate_Construct::StartActivity<unsigned short const *>(
    v61,
    &v44);
  v56[0] = (ComputeService::Management::Details *)ComputeService::Management::ComputeSystem::GetConfigurationAs<ComputeService::Management::TemplateVmSystemConfiguration>(*a2);
  v7 = ComputeService::Management::ComputeSystem::GetStateAs<ComputeService::Management::TemplateVmSystemState>(*a2);
  v44 = (_OWORD *)((char *)v56[0] + 296);
  v48 = 257;
  v47[0] = a1;
  v47[1] = a2;
  memset_0(v62, 0, 0x130u);
  *(_QWORD *)pszPathOut = &std::_Func_impl_no_alloc<_lambda_6edba6c7afa207de272e6701335f5b8a_,void,long,unsigned __int64>::`vftable';
  v52 = v56;
  v53 = pszPathOut;
  ComputeService::Telemetry::OperationTracker::OperationTracker(v62, pszPathOut);
  std::_Func_class<void,>::_Tidy(pszPathOut);
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  *(struct _FILETIME *)(v7 + 496) = SystemTimeAsFileTime;
  v8 = (_QWORD *)((char *)v56[0] + 8);
  if ( *((_QWORD *)v56[0] + 4) > 7u )
    v8 = (_QWORD *)*v8;
  ComputeService::RecoveryStore::RecordSystem(v8, 4);
  ThreadpoolWait = CreateThreadpoolWait(ComputeService::Management::Details::OnTemplateVmExit, (PVOID)(v7 + 72), 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&void CloseThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    v7 + 472,
    ThreadpoolWait);
  if ( !*(_QWORD *)(v7 + 472) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x238,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\hypervcontainer\\utilityvmtemplateorchestrator.cpp",
      v10);
  std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(v58);
  std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(v59);
  std::wstring::wstring(v60);
  ComputeService::UtilityVm::MirrorMMRegistrySettings((ComputeService::UtilityVm *)v58, v11);
  ComputeService::UtilityVm::MirrorDeltaHivePolicy((ComputeService::UtilityVm *)v58, v12);
  v13 = wil::MakeOrThrow<VmHandleBrokerManager,>(&SystemTimeAsFileTime);
  wil::com_ptr_t<IVmHandleBrokerManager,wil::err_exception_policy>::operator=<VmHandleBrokerManager,void>(v7 + 504, v13);
  v14 = (ComputeService::HyperVContainer *)SystemTimeAsFileTime;
  if ( SystemTimeAsFileTime )
  {
    SystemTimeAsFileTime = 0;
    (*(void (__fastcall **)(ComputeService::HyperVContainer *))(*(_QWORD *)v14 + 16LL))(v14);
  }
  v15 = *(_QWORD *)(v7 + 504);
  NumaSpanningSetting = ComputeService::HyperVContainer::GetNumaSpanningSetting(v14);
  UtilityVmDataRoot = ComputeService::HyperVContainer::GetUtilityVmDataRoot(pszPathOut);
  v18 = (ComputeService::Management::Details *)((char *)v56[0] + 8);
  if ( *((_QWORD *)v56[0] + 4) > 7u )
    v18 = *(ComputeService::HyperVContainer::Details **)v18;
  v19 = ComputeService::HyperVContainer::SetupUtilityVmEnvironment(
          (ComputeService::HyperVContainer::Details **)&SystemTimeAsFileTime,
          v18,
          (__int64)v56[0] + 48,
          (__int64)v58,
          0,
          0,
          0,
          UtilityVmDataRoot,
          NumaSpanningSetting,
          2u,
          0,
          v15,
          v44);
  v20 = (_QWORD *)(v7 + 464);
  std::unique_ptr<ComputeService::HyperVContainer::UtilityVmEnvironment>::operator=<std::default_delete<ComputeService::HyperVContainer::UtilityVmEnvironment>,0>(
    v7 + 464,
    v19);
  std::unique_ptr<ComputeService::HyperVContainer::UtilityVmEnvironment>::~unique_ptr<ComputeService::HyperVContainer::UtilityVmEnvironment>(&SystemTimeAsFileTime);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)pszPathOut);
  ComputeService::Resource::RequestManager::PopulateMemoryResourceState(
    LODWORD(v56[0]) + 8,
    LODWORD(v56[0]) + 8,
    v7 + 480,
    -1,
    *(_QWORD *)(*(_QWORD *)(v7 + 464) + 184LL),
    0);
  ComputeService::Resource::AllocateResourceType(
    (ComputeService::Resource *)(v7 + 480),
    (const struct ComputeService::Resource::ResourceState *)2,
    v21);
  ComputeService::Resource::QueryAllocationResults(
    (ComputeService::Resource *)(v7 + 480),
    (const struct ComputeService::Resource::ResourceState *)2,
    (enum ResourceType)*(_QWORD *)(*(_QWORD *)(v7 + 464) + 184LL),
    v22);
  ComputeService::VmCommonHelpers::GetMemoryBalancerInformation(pszPathOut, v7 + 480);
  try
  {
    Config::VirtualMachine::InitContext::InitContext((Config::VirtualMachine::InitContext *)v64);
    v23 = *v20;
    v64[153] = *(_BYTE *)(*v20 + 992LL);
    std::wstring::operator=(v65, v23 + 1000);
    inited = Config::VirtualMachine::InitContext::InitContext(
               (Config::VirtualMachine::InitContext *)v55,
               (const struct Config::VirtualMachine::InitContext *)v64);
    ComputeService::UtilityVm::StartUtilityVmWorkerProcess(*v20, 1, inited);
    v25 = (__int64 *)std::make_shared<ComputeService::Management::CancellationProvider,>(&v45);
    v26 = *v25;
    v27 = v25[1];
    *v25 = 0;
    v25[1] = 0;
    *(_QWORD *)(v7 + 448) = v26;
    v28 = *(std::_Ref_count_base **)(v7 + 456);
    *(_QWORD *)(v7 + 456) = v27;
    if ( v28 )
      std::_Ref_count_base::_Decref(v28);
    if ( v46 )
      std::_Ref_count_base::_Decref(v46);
    v45 = (const struct ComputeService::Vmwp::WorkerProcessContext *)v54;
    v54[0] = &std::_Func_impl_no_alloc<_lambda_80465676dd63bfe5a080de739d3b71e1_,void,ComputeService::Communication::BridgeNotification const &>::`vftable';
    v54[1] = v7;
    v54[7] = v54;
    LOWORD(v43) = 0;
    CancellationToken = ComputeService::Management::ActiveServerOperation::CreateCancellationToken(a3, v49);
    ComputeService::UtilityVm::SetupBridgeServer(
      *(_QWORD *)*a2 + 8,
      (_DWORD)v44,
      CancellationToken,
      (unsigned int)&v43,
      (__int64)v54,
      (ComputeService::UtilityVm *)((v7 + 128) & -(__int64)(v7 != 0)));
    v30 = v7 + 152;
    if ( !v7 )
      v30 = 24;
    (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v30 + 8LL))(*(_QWORD *)v30, 3224830218LL);
    SystemTimeAsFileTime = 0;
    v43 = 1;
    v31 = Vml::VmComMultiInstanceObject<ComputeService::Vmwp::Task>::CreateInstance<>();
    Vml::VmComPtr<DmWorkerProcessTracker>::Attach<DmWorkerProcessTracker>(&SystemTimeAsFileTime, v31);
    v32 = SystemTimeAsFileTime;
    SystemTimeAsFileTime = 0;
    v33 = (const struct ComputeService::Vmwp::WorkerProcessContext *)((*(_QWORD *)&v32 + 24LL)
                                                                    & ((unsigned __int128)-(__int128)*(unsigned __int64 *)&v32 >> 64));
    v45 = v33;
    Vml::VmComPtr<Vml::VmComLocalMemStream>::~VmComPtr<Vml::VmComLocalMemStream>(&SystemTimeAsFileTime);
    v44 = 0;
    v50 = 0;
    v43 = 2;
    SystemTimeAsFileTime.dwLowDateTime = 0;
    v49[0] = v33;
    v36 = ___InvokeWorkerProcessMethod_UIVmVirtualMachine__PEAUIVmSimpleTask__W4__MIDL___MIDL_itf_vmwrkr_0000_0006_0001__W4__MIDL___MIDL_itf_vmwrkr_0000_0006_0002__PEBGPEBGPEBGPEAU2_PEAUIVmHandleBrokerManager____ZPEAU2_W43_W44_AEAY00__CBGAEAY00__CBGAEAY00__CBG__T__T_Vmwp_ComputeService__YAJAEBUWorkerProcessContext_01_PEAUIUnknown__P8IVmVirtualMachine__EAAJPEAUIVmSimpleTask__W4__MIDL___MIDL_itf_vmwrkr_0000_0006_0001__W4__MIDL___MIDL_itf_vmwrkr_0000_0006_0002__PEBG552PEAUIVmHandleBrokerManager___Z__QEAPEAU5___QEAW46___QEAW47_AEAY00__CBGAEAY00__CBGAEAY00__CBG__QEA__T__QEA__T_Z(
            v34,
            *(_QWORD *)(*v20 + 128LL),
            v35,
            (unsigned int)v49,
            (__int64)&SystemTimeAsFileTime,
            (__int64)&v43,
            (unsigned int)&szPassword,
            (__int64)&szPassword,
            (__int64)&szPassword,
            (__int64)&v50,
            (__int64)&v44);
    if ( v36 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x288,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\hypervcontainer\\utilityvmtemplateorchestrator.cpp",
        (const char *)(unsigned int)v36,
        v42);
    ComputeService::Vmwp::WaitForWorkerProcessTaskThrow((ComputeService::Vmwp *)(*v20 + 112LL), v33, v37, v38);
  }
  catch ( ... )
  {
    ComputeService::Reporting::ComputeErrorFromThrownException(v54);
  }
  Vml::VmComPtr<IVmSimpleTaskEvents>::~VmComPtr<IVmSimpleTaskEvents>(&v45);
  Config::VirtualMachine::InitContext::~InitContext((Config::VirtualMachine::InitContext *)v64);
  ComputeService::Management::Details::SetupTemplateState((ComputeService::Management::Details *)v7, v39);
  ComputeService::Management::Details::StoreRecoveryData(
    v56[0],
    (const struct ComputeService::Management::TemplateVmSystemConfiguration *)v7,
    v40);
  SetThreadpoolWait(*(PTP_WAIT *)(v7 + 472), *(HANDLE *)(*v20 + 136LL), 0);
  v44 = 0;
  wil::AcquireSRWLockExclusive(&v44, *(_QWORD *)(v7 + 432) + 160LL);
  *(_DWORD *)(*(_QWORD *)(v7 + 432) + 152LL) = 2;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v44);
  BYTE1(v48) = 0;
  v62[8] = 1;
  v63 = 0;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v61,
    0);
  std::pair<Vml::VmComPtr<IMemoryBalancer>,Vml::VmComPtr<IVmSimpleTask>>::~pair<Vml::VmComPtr<IMemoryBalancer>,Vml::VmComPtr<IVmSimpleTask>>(pszPathOut);
  Schema::Registry::RegistryChanges::~RegistryChanges((Schema::Registry::RegistryChanges *)v58);
  ComputeService::Telemetry::OperationTracker::~OperationTracker((ComputeService::Telemetry::OperationTracker *)v62);
  wil::details::ScopeExitFnGuard__lambda_561f17c2b1c127d41df19d6d1bcc32b2___::operator()(v47);
  ComputeService::Diagnostics::TraceProvider::UtilityVmTemplate_Construct::~UtilityVmTemplate_Construct((ComputeService::Diagnostics::TraceProvider::UtilityVmTemplate_Construct *)v61);
  ComputeService::Management::OrchestratorCallContext::~OrchestratorCallContext(a3);
  return 1;
}

```

## disassembly

```asm
0x14009dad0  mov     r11, rsp
0x14009dad3  mov     [r11+8], rbx
0x14009dad7  mov     [r11+20h], rsi
0x14009dadb  push    rdi
0x14009dadc  push    r12
0x14009dade  push    r13
0x14009dae0  push    r14
0x14009dae2  push    r15
0x14009dae4  sub     rsp, 0B00h
0x14009daeb  mov     rax, cs:__security_cookie
0x14009daf2  xor     rax, rsp
0x14009daf5  mov     [rsp+0B28h+var_38], rax
0x14009dafd  mov     r12, r8
0x14009db00  mov     r15, rdx
0x14009db03  mov     rbx, rcx
0x14009db06  mov     [r11-678h], r8
0x14009db0d  xor     esi, esi
0x14009db0f  mov     [rsp+0B28h+var_AB8], esi
0x14009db13  xor     edx, edx; Val
0x14009db15  mov     r8d, 150h; Size
0x14009db1b  lea     rcx, [r11-618h]; void *
0x14009db22  call    memset_0
0x14009db27  mov     rax, [r15]
0x14009db2a  mov     rcx, [rax]
0x14009db2d  add     rcx, 8
0x14009db31  cmp     qword ptr [rcx+18h], 7
0x14009db36  jbe     short loc_14009DB3B
0x14009db38  mov     rcx, [rcx]
0x14009db3b  mov     [rsp+0B28h+var_AB0], rcx
0x14009db40  lea     rdx, aUtilityvmtempl_2; "UtilityVmTemplate_Construct"
0x14009db47  lea     rcx, [rsp+0B28h+var_618]
0x14009db4f  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14009db54  lea     rax, ??_7UtilityVmTemplate_Construct@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::UtilityVmTemplate_Construct::`vftable'
0x14009db5b  mov     [rsp+0B28h+var_618], rax
0x14009db63  lea     rdx, [rsp+0B28h+var_AB0]
0x14009db68  lea     rcx, [rsp+0B28h+var_618]
0x14009db70  call    ??$StartActivity@PEBG@UtilityVmTemplate_Construct@TraceProvider@Diagnostics@ComputeService@@QEAAX$$QEAPEBG@Z; ComputeService::Diagnostics::TraceProvider::UtilityVmTemplate_Construct::StartActivity<ushort const *>(ushort const * &&)
0x14009db75  nop
0x14009db76  mov     rcx, [r15]
0x14009db79  call    ??$GetConfigurationAs@UTemplateVmSystemConfiguration@Management@ComputeService@@@ComputeSystem@Management@ComputeService@@QEBAPEBUTemplateVmSystemConfiguration@12@XZ; ComputeService::Management::ComputeSystem::GetConfigurationAs<ComputeService::Management::TemplateVmSystemConfiguration>(void)
0x14009db7e  mov     [rsp+0B28h+var_680], rax
0x14009db86  mov     rcx, [r15]
0x14009db89  call    ??$GetStateAs@UTemplateVmSystemState@Management@ComputeService@@@ComputeSystem@Management@ComputeService@@QEAAPEAUTemplateVmSystemState@12@XZ; ComputeService::Management::ComputeSystem::GetStateAs<ComputeService::Management::TemplateVmSystemState>(void)
0x14009db8e  mov     rdi, rax
0x14009db91  mov     rax, [rsp+0B28h+var_680]
0x14009db99  add     rax, 128h
0x14009db9f  mov     [rsp+0B28h+var_AB0], rax
0x14009dba4  xorps   xmm0, xmm0
0x14009dba7  xor     eax, eax
0x14009dba9  movups  [rsp+0B28h+var_A98], xmm0
0x14009dbb1  mov     [rsp+0B28h+var_A88], rax
0x14009dbb9  mov     qword ptr [rsp+0B28h+var_A98], rbx
0x14009dbc1  mov     qword ptr [rsp+0B28h+var_A98+8], r15
0x14009dbc9  mov     word ptr [rsp+0B28h+var_A88], 101h
0x14009dbd3  xor     edx, edx; Val
0x14009dbd5  mov     r8d, 130h; Size
0x14009dbdb  lea     rcx, [rsp+0B28h+var_4C8]; void *
0x14009dbe3  call    memset_0
0x14009dbe8  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_6edba6c7afa207de272e6701335f5b8a_@@XJ_K@std@@6B@; const std::_Func_impl_no_alloc<_lambda_6edba6c7afa207de272e6701335f5b8a_,void,long,unsigned __int64>::`vftable'
0x14009dbef  mov     qword ptr [rsp+0B28h+pszPathOut], rax
0x14009dbf7  lea     rax, [rsp+0B28h+var_680]
0x14009dbff  mov     [rsp+0B28h+var_A60], rax
0x14009dc07  lea     rax, [rsp+0B28h+pszPathOut]
0x14009dc0f  mov     [rsp+0B28h+var_A30], rax
0x14009dc17  lea     rdx, [rsp+0B28h+pszPathOut]
0x14009dc1f  lea     rcx, [rsp+0B28h+var_4C8]
0x14009dc27  call    ??0OperationTracker@Telemetry@ComputeService@@QEAA@$$QEAV?$function@$$A6AXJ_K@Z@std@@@Z; ComputeService::Telemetry::OperationTracker::OperationTracker(std::function<void (long,unsigned __int64)> &&)
0x14009dc2c  nop
0x14009dc2d  lea     rcx, [rsp+0B28h+pszPathOut]; void *
0x14009dc35  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x14009dc3a  mov     qword ptr [rsp+0B28h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x14009dc42  lea     rcx, [rsp+0B28h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14009dc4a  call    cs:__imp_GetSystemTimeAsFileTime
0x14009dc51  nop     dword ptr [rax+rax+00h]
0x14009dc56  mov     rax, qword ptr [rsp+0B28h+SystemTimeAsFileTime.dwLowDateTime]
0x14009dc5e  mov     [rdi+1F0h], rax
0x14009dc65  mov     rcx, [rsp+0B28h+var_680]
0x14009dc6d  add     rcx, 8
0x14009dc71  cmp     qword ptr [rcx+18h], 7
0x14009dc76  jbe     short loc_14009DC7B
0x14009dc78  mov     rcx, [rcx]
0x14009dc7b  mov     edx, 4
0x14009dc80  call    ?RecordSystem@RecoveryStore@ComputeService@@YAXPEBGW4ComputeSystemType@Management@2@@Z; ComputeService::RecoveryStore::RecordSystem(ushort const *,ComputeService::Management::ComputeSystemType)
0x14009dc85  lea     rdx, [rdi+48h]; pv
0x14009dc89  xor     r8d, r8d; pcbe
0x14009dc8c  lea     rcx, ?OnTemplateVmExit@Details@Management@ComputeService@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x14009dc93  call    cs:__imp_CreateThreadpoolWait
0x14009dc9a  nop     dword ptr [rax+rax+00h]
0x14009dc9f  lea     r13, [rdi+1D8h]
0x14009dca6  mov     rdx, rax
0x14009dca9  mov     rcx, r13
0x14009dcac  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?CloseThreadpoolWait@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&CloseThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x14009dcb1  mov     rcx, [rsp+0B28h]; this
0x14009dcb9  cmp     [r13+0], rsi
0x14009dcbd  jnz     short loc_14009DCD1
0x14009dcbf  lea     r8, aOnecoreVmCompu_98; "onecore\\vm\\compute\\management\\orche"...
0x14009dcc6  mov     edx, 238h; void *
0x14009dccb  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14009dcd1  lea     rcx, [rsp+0B28h+var_668]
0x14009dcd9  call    ??0?$vector@UVpSubnodeMetadata@VirtualMachine@Config@@V?$allocator@UVpSubnodeMetadata@VirtualMachine@Config@@@std@@@std@@QEAA@XZ; std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(void)
0x14009dcde  lea     rcx, [rsp+0B28h+var_650]
0x14009dce6  call    ??0?$vector@UVpSubnodeMetadata@VirtualMachine@Config@@V?$allocator@UVpSubnodeMetadata@VirtualMachine@Config@@@std@@@std@@QEAA@XZ; std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(void)
0x14009dceb  lea     rcx, [rsp+0B28h+var_638]; void *
0x14009dcf3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14009dcf8  nop
0x14009dcf9  lea     rcx, [rsp+0B28h+var_668]; this
0x14009dd01  call    ?MirrorMMRegistrySettings@UtilityVm@ComputeService@@YAXAEAURegistryChanges@Registry@Schema@@@Z; ComputeService::UtilityVm::MirrorMMRegistrySettings(Schema::Registry::RegistryChanges &)
0x14009dd06  lea     rcx, [rsp+0B28h+var_668]; this
0x14009dd0e  call    ?MirrorDeltaHivePolicy@UtilityVm@ComputeService@@YAXAEAURegistryChanges@Registry@Schema@@@Z; ComputeService::UtilityVm::MirrorDeltaHivePolicy(Schema::Registry::RegistryChanges &)
0x14009dd13  lea     rcx, [rsp+0B28h+SystemTimeAsFileTime]
0x14009dd1b  call    ??$MakeOrThrow@VVmHandleBrokerManager@@$$V@wil@@YA?AV?$ComPtr@VVmHandleBrokerManager@@@WRL@Microsoft@@XZ; wil::MakeOrThrow<VmHandleBrokerManager,>(void)
0x14009dd20  lea     r14, [rdi+1F8h]
0x14009dd27  mov     rdx, rax
0x14009dd2a  mov     rcx, r14
0x14009dd2d  call    ??$?4VVmHandleBrokerManager@@X@?$com_ptr_t@UIVmHandleBrokerManager@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@$$QEAV?$ComPtr@VVmHandleBrokerManager@@@WRL@Microsoft@@@Z; wil::com_ptr_t<IVmHandleBrokerManager,wil::err_exception_policy>::operator=<VmHandleBrokerManager,void>(Microsoft::WRL::ComPtr<VmHandleBrokerManager> &&)
0x14009dd32  nop
0x14009dd33  mov     rcx, qword ptr [rsp+0B28h+SystemTimeAsFileTime.dwLowDateTime]
0x14009dd3b  test    rcx, rcx
0x14009dd3e  jz      short loc_14009DD55
0x14009dd40  mov     qword ptr [rsp+0B28h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x14009dd48  mov     rax, [rcx]
0x14009dd4b  mov     rax, [rax+10h]
0x14009dd4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009dd54  nop
0x14009dd55  mov     rbx, [r14]
0x14009dd58  call    ?GetNumaSpanningSetting@HyperVContainer@ComputeService@@YA_NXZ; ComputeService::HyperVContainer::GetNumaSpanningSetting(void)
0x14009dd5d  mov     sil, al
0x14009dd60  lea     rcx, [rsp+0B28h+pszPathOut]; pszPathOut
0x14009dd68  call    ?GetUtilityVmDataRoot@HyperVContainer@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ComputeService::HyperVContainer::GetUtilityVmDataRoot(void)
0x14009dd6d  nop
0x14009dd6e  mov     rcx, [rsp+0B28h+var_680]
0x14009dd76  lea     r8, [rcx+30h]
0x14009dd7a  lea     rdx, [rcx+8]
0x14009dd7e  cmp     qword ptr [rdx+18h], 7
0x14009dd83  jbe     short loc_14009DD88
0x14009dd85  mov     rdx, [rdx]
0x14009dd88  mov     rcx, [rsp+0B28h+var_AB0]
0x14009dd8d  mov     [rsp+0B28h+var_AC8], rcx
0x14009dd92  mov     [rsp+0B28h+var_AD0], rbx
0x14009dd97  xor     ecx, ecx
0x14009dd99  mov     byte ptr [rsp+0B28h+var_AD8], cl
0x14009dd9d  mov     dword ptr [rsp+0B28h+var_AE0], 2
0x14009dda5  mov     byte ptr [rsp+0B28h+var_AE8], sil
0x14009ddaa  mov     [rsp+0B28h+var_AF0], rax
0x14009ddaf  mov     [rsp+0B28h+var_AF8], rcx
0x14009ddb4  mov     [rsp+0B28h+var_B00], rcx
0x14009ddb9  mov     qword ptr [rsp+0B28h+var_B08], rcx
0x14009ddbe  lea     r9, [rsp+0B28h+var_668]
0x14009ddc6  lea     rcx, [rsp+0B28h+SystemTimeAsFileTime]
0x14009ddce  call    ?SetupUtilityVmEnvironment@HyperVContainer@ComputeService@@YA?AV?$unique_ptr@UUtilityVmEnvironment@HyperVContainer@ComputeService@@U?$default_delete@UUtilityVmEnvironment@HyperVContainer@ComputeService@@@std@@@std@@PEBGAEBUContainerSettings@Containers@Config@@AEBURegistryChanges@Registry@Schema@@00_K$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@_NW4UtilityVmType@UtilityVm@2@5PEAUIVmHandleBrokerManager@@AEBU_GUID@@@Z; ComputeService::HyperVContainer::SetupUtilityVmEnvironment(ushort const *,Config::Containers::ContainerSettings const &,Schema::Registry::RegistryChanges const &,ushort const *,ushort const *,unsigned __int64,std::wstring &&,bool,ComputeService::UtilityVm::UtilityVmType,bool,IVmHandleBrokerManager *,_GUID const &)
0x14009ddd3  lea     rsi, [rdi+1D0h]
0x14009ddda  mov     rdx, rax
0x14009dddd  mov     rcx, rsi
0x14009dde0  call    ??$?4U?$default_delete@UUtilityVmEnvironment@HyperVContainer@ComputeService@@@std@@$0A@@?$unique_ptr@UUtilityVmEnvironment@HyperVContainer@ComputeService@@U?$default_delete@UUtilityVmEnvironment@HyperVContainer@ComputeService@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<ComputeService::HyperVContainer::UtilityVmEnvironment>::operator=<std::default_delete<ComputeService::HyperVContainer::UtilityVmEnvironment>,0>(std::unique_ptr<ComputeService::HyperVContainer::UtilityVmEnvironment> &&)
0x14009dde5  lea     rcx, [rsp+0B28h+SystemTimeAsFileTime]
0x14009dded  call    ??1?$unique_ptr@UUtilityVmEnvironment@HyperVContainer@ComputeService@@U?$default_delete@UUtilityVmEnvironment@HyperVContainer@ComputeService@@@std@@@std@@QEAA@XZ; std::unique_ptr<ComputeService::HyperVContainer::UtilityVmEnvironment>::~unique_ptr<ComputeService::HyperVContainer::UtilityVmEnvironment>(void)
0x14009ddf2  nop
0x14009ddf3  lea     rcx, [rsp+0B28h+pszPathOut]; this
0x14009ddfb  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14009de00  lea     rbx, [rdi+1E0h]
0x14009de07  mov     rcx, [rsp+0B28h+var_680]
0x14009de0f  add     rcx, 8
0x14009de13  mov     rax, [rsi]
0x14009de16  mov     [rsp+0B28h+var_B00], 0
0x14009de1f  mov     rax, [rax+0B8h]
0x14009de26  mov     qword ptr [rsp+0B28h+var_B08], rax
0x14009de2b  or      r9, 0FFFFFFFFFFFFFFFFh
0x14009de2f  mov     r8, rbx
0x14009de32  mov     rdx, rcx
0x14009de35  call    ?PopulateMemoryResourceState@RequestManager@Resource@ComputeService@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAUResourceState@23@PEAXPEAVVmRepository@@PEBUInitContext@VirtualMachine@Config@@@Z; ComputeService::Resource::RequestManager::PopulateMemoryResourceState(std::wstring const &,std::wstring const &,ComputeService::Resource::ResourceState &,void *,VmRepository *,Config::VirtualMachine::InitContext const *)
0x14009de3a  mov     edx, 2; struct ComputeService::Resource::ResourceState *
0x14009de3f  mov     rcx, rbx; this
0x14009de42  call    ?AllocateResourceType@Resource@ComputeService@@YAXAEBUResourceState@12@W4ResourceType@12@@Z; ComputeService::Resource::AllocateResourceType(ComputeService::Resource::ResourceState const &,ComputeService::Resource::ResourceType)
0x14009de47  mov     r8, [rsi]
0x14009de4a  mov     r8, [r8+0B8h]; enum ResourceType
0x14009de51  mov     edx, 2; struct ComputeService::Resource::ResourceState *
0x14009de56  mov     rcx, rbx; this
0x14009de59  call    ?QueryAllocationResults@Resource@ComputeService@@YAXAEBUResourceState@12@W4ResourceType@12@PEAVVmRepository@@@Z; ComputeService::Resource::QueryAllocationResults(ComputeService::Resource::ResourceState const &,ComputeService::Resource::ResourceType,VmRepository *)
0x14009de5e  mov     rdx, rbx
0x14009de61  lea     rcx, [rsp+0B28h+pszPathOut]
0x14009de69  call    ?GetMemoryBalancerInformation@VmCommonHelpers@ComputeService@@YA?AU?$pair@V?$VmComPtr@UIMemoryBalancer@@@Vml@@V?$VmComPtr@UIVmSimpleTask@@@2@@std@@AEBUResourceState@Resource@2@@Z; ComputeService::VmCommonHelpers::GetMemoryBalancerInformation(ComputeService::Resource::ResourceState const &)
0x14009de6e  nop
0x14009de6f  lea     rcx, [rsp+0B28h+var_398]; this
0x14009de77  call    ??0InitContext@VirtualMachine@Config@@QEAA@XZ; Config::VirtualMachine::InitContext::InitContext(void)
0x14009de7c  nop
0x14009de7d  mov     rdx, [rsi]
0x14009de80  mov     al, [rdx+3E0h]
0x14009de86  mov     [rsp+0B28h+var_2FF], al
0x14009de8d  add     rdx, 3E8h
0x14009de94  lea     rcx, [rsp+0B28h+var_2F8]
0x14009de9c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14009dea1  mov     rbx, [r14]
0x14009dea4  lea     rdx, [rsp+0B28h+var_398]; struct Config::VirtualMachine::InitContext *
0x14009deac  lea     rcx, [rsp+0B28h+var_9D8]; this
0x14009deb4  call    ??0InitContext@VirtualMachine@Config@@QEAA@AEBU012@@Z; Config::VirtualMachine::InitContext::InitContext(Config::VirtualMachine::InitContext const &)
0x14009deb9  mov     [rsp+0B28h+var_AF8], rbx
0x14009debe  mov     rcx, [rsp+0B28h+var_A60]
0x14009dec6  mov     [rsp+0B28h+var_B00], rcx
0x14009decb  mov     rcx, qword ptr [rsp+0B28h+pszPathOut]
0x14009ded3  mov     qword ptr [rsp+0B28h+var_B08], rcx
0x14009ded8  xor     r9d, r9d
0x14009dedb  mov     r8, rax
0x14009dede  lea     edx, [r9+1]
0x14009dee2  mov     rcx, [rsi]
0x14009dee5  call    ?StartUtilityVmWorkerProcess@UtilityVm@ComputeService@@YAXPEAUEnvironment@12@IUInitContext@VirtualMachine@Config@@PEBGPEAUIMemoryBalancer@@PEAUIVmSimpleTask@@PEAUIVmHandleBrokerManager@@@Z; ComputeService::UtilityVm::StartUtilityVmWorkerProcess(ComputeService::UtilityVm::Environment *,uint,Config::VirtualMachine::InitContext,ushort const *,IMemoryBalancer *,IVmSimpleTask *,IVmHandleBrokerManager *)
0x14009deea  lea     rcx, [rsp+0B28h+var_AA8]
0x14009def2  call    ??$make_shared@VCancellationProvider@Management@ComputeService@@$$V@std@@YA?AV?$shared_ptr@VCancellationProvider@Management@ComputeService@@@0@XZ; std::make_shared<ComputeService::Management::CancellationProvider,>(void)
0x14009def7  mov     rcx, [rax]
0x14009defa  mov     rdx, [rax+8]
0x14009defe  xor     r14d, r14d
0x14009df01  mov     [rax], r14
0x14009df04  mov     [rax+8], r14
0x14009df08  mov     [rdi+1C0h], rcx
0x14009df0f  mov     rcx, [rdi+1C8h]; this
0x14009df16  mov     [rdi+1C8h], rdx
0x14009df1d  test    rcx, rcx
0x14009df20  jz      short loc_14009DF27
0x14009df22  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14009df27  mov     rcx, [rsp+0B28h+var_AA0]; this
0x14009df2f  test    rcx, rcx
0x14009df32  jz      short loc_14009DF39
0x14009df34  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14009df39  mov     rax, rdi
0x14009df3c  lea     rcx, [rdi+80h]
0x14009df43  neg     rax
0x14009df46  sbb     rbx, rbx
0x14009df49  and     rbx, rcx
0x14009df4c  lea     rax, [rsp+0B28h+var_A28]
0x14009df54  mov     [rsp+0B28h+var_AA8], rax
0x14009df5c  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_80465676dd63bfe5a080de739d3b71e1_@@XAEBUBridgeNotification@Communication@ComputeService@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_80465676dd63bfe5a080de739d3b71e1_,void,ComputeService::Communication::BridgeNotification const &>::`vftable'
0x14009df63  mov     [rsp+0B28h+var_A28], rax
0x14009df6b  mov     [rsp+0B28h+var_A20], rdi
0x14009df73  lea     rax, [rsp+0B28h+var_A28]
0x14009df7b  mov     [rsp+0B28h+var_9F0], rax
0x14009df83  mov     word ptr [rsp+0B28h+var_AB8], r14w
0x14009df89  lea     rdx, [rsp+0B28h+var_A80]
0x14009df91  mov     rcx, r12
0x14009df94  call    ?CreateCancellationToken@ActiveServerOperation@Management@ComputeService@@QEAA?AVCancellationToken@23@XZ; ComputeService::Management::ActiveServerOperation::CreateCancellationToken(void)
0x14009df99  mov     rcx, [r15]
0x14009df9c  mov     rcx, [rcx]
0x14009df9f  add     rcx, 8
0x14009dfa3  mov     [rsp+0B28h+var_B00], rbx
0x14009dfa8  lea     rdx, [rsp+0B28h+var_A28]
0x14009dfb0  mov     qword ptr [rsp+0B28h+var_B08], rdx
0x14009dfb5  lea     r9, [rsp+0B28h+var_AB8]
0x14009dfba  mov     r8, rax
0x14009dfbd  mov     rdx, [rsp+0B28h+var_AB0]
0x14009dfc2  call    ?SetupBridgeServer@UtilityVm@ComputeService@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@VCancellationToken@Management@2@AEBUBridgeOptions@Communication@2@V?$function@$$A6AXAEBUBridgeNotification@Communication@ComputeService@@@Z@4@PEAUGuestServiceState@12@@Z; ComputeService::UtilityVm::SetupBridgeServer(std::wstring const &,_GUID const &,ComputeService::Management::CancellationToken,ComputeService::Communication::BridgeOptions const &,std::function<void (ComputeService::Communication::BridgeNotification const &)>,ComputeService::UtilityVm::GuestServiceState *)
0x14009dfc7  lea     rax, [rdi+98h]
0x14009dfce  mov     ecx, 18h
0x14009dfd3  test    rdi, rdi
0x14009dfd6  cmovz   rax, rcx
0x14009dfda  mov     rcx, [rax]
0x14009dfdd  mov     rax, [rcx]
0x14009dfe0  mov     edx, 0C037010Ah
0x14009dfe5  mov     rax, [rax+8]
0x14009dfe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009dfee  nop
0x14009dfef  mov     qword ptr [rsp+0B28h+SystemTimeAsFileTime.dwLowDateTime], r14
0x14009dff7  mov     [rsp+0B28h+var_AB8], 1
0x14009dfff  call    ??$CreateInstance@$$V@?$VmComMultiInstanceObject@VTask@Vmwp@ComputeService@@@Vml@@SAPEAVTask@Vmwp@ComputeService@@XZ; Vml::VmComMultiInstanceObject<ComputeService::Vmwp::Task>::CreateInstance<>(void)
0x14009e004  mov     rdx, rax
0x14009e007  lea     rcx, [rsp+0B28h+SystemTimeAsFileTime]
0x14009e00f  call    ??$Attach@VDmWorkerProcessTracker@@@?$VmComPtr@VDmWorkerProcessTracker@@@Vml@@QEAAXPEAVDmWorkerProcessTracker@@@Z; Vml::VmComPtr<DmWorkerProcessTracker>::Attach<DmWorkerProcessTracker>(DmWorkerProcessTracker *)
0x14009e014  mov     rcx, qword ptr [rsp+0B28h+SystemTimeAsFileTime.dwLowDateTime]
0x14009e01c  mov     qword ptr [rsp+0B28h+SystemTimeAsFileTime.dwLowDateTime], r14
0x14009e024  lea     rax, [rcx+18h]
0x14009e028  neg     rcx
0x14009e02b  sbb     rbx, rbx
0x14009e02e  and     rbx, rax
0x14009e031  mov     [rsp+0B28h+var_AA8], rbx
0x14009e039  lea     rcx, [rsp+0B28h+SystemTimeAsFileTime]
0x14009e041  call    ??1?$VmComPtr@VVmComLocalMemStream@Vml@@@Vml@@QEAA@XZ; Vml::VmComPtr<Vml::VmComLocalMemStream>::~VmComPtr<Vml::VmComLocalMemStream>(void)
0x14009e046  mov     [rsp+0B28h+var_AB0], r14
0x14009e04b  mov     [rsp+0B28h+var_A70], r14
0x14009e053  mov     r15d, 2
0x14009e059  mov     [rsp+0B28h+var_AB8], r15d
0x14009e05e  mov     [rsp+0B28h+SystemTimeAsFileTime.dwLowDateTime], r14d
0x14009e066  mov     [rsp+0B28h+var_A80], rbx
0x14009e06e  mov     rdx, [rsi]
0x14009e071  lea     rax, [rsp+0B28h+var_AB0]
0x14009e076  mov     [rsp+0B28h+var_AD8], rax
0x14009e07b  lea     rax, [rsp+0B28h+var_A70]
0x14009e083  mov     [rsp+0B28h+var_AE0], rax
0x14009e088  lea     rax, szPassword
0x14009e08f  mov     [rsp+0B28h+var_AE8], rax
0x14009e094  mov     [rsp+0B28h+var_AF0], rax
0x14009e099  mov     [rsp+0B28h+var_AF8], rax
0x14009e09e  lea     rax, [rsp+0B28h+var_AB8]
0x14009e0a3  mov     [rsp+0B28h+var_B00], rax
0x14009e0a8  lea     rax, [rsp+0B28h+SystemTimeAsFileTime]
0x14009e0b0  mov     qword ptr [rsp+0B28h+var_B08], rax; int
0x14009e0b5  lea     r9, [rsp+0B28h+var_A80]
0x14009e0bd  mov     rdx, [rdx+80h]
0x14009e0c4  call    ??$InvokeWorkerProcessMethod@UIVmVirtualMachine@@PEAUIVmSimpleTask@@W4__MIDL___MIDL_itf_vmwrkr_0000_0006_0001@@W4__MIDL___MIDL_itf_vmwrkr_0000_0006_0002@@PEBGPEBGPEBGPEAU2@PEAUIVmHandleBrokerManager@@$$ZPEAU2@W43@W44@AEAY00$$CBGAEAY00$$CBGAEAY00$$CBG$$T$$T@Vmwp@ComputeService@@YAJAEBUWorkerProcessContext@01@PEAUIUnknown@@P8IVmVirtualMachine@@EAAJPEAUIVmSimpleTask@@W4__MIDL___MIDL_itf_vmwrkr_0000_0006_0001@@W4__MIDL___MIDL_itf_vmwrkr_0000_0006_0002@@PEBG552PEAUIVmHandleBrokerManager@@@Z$$QEAPEAU5@$$QEAW46@$$QEAW47@AEAY00$$CBGAEAY00$$CBGAEAY00$$CBG$$QEA$$T$$QEA$$T@Z
0x14009e0c9  mov     rcx, [rsp+0B28h]; this
0x14009e0d1  test    eax, eax
0x14009e0d3  jns     short loc_14009E0E9
0x14009e0d5  mov     r9d, eax; char *
0x14009e0d8  lea     r8, aOnecoreVmCompu_98; "onecore\\vm\\compute\\management\\orche"...
  ... truncated ...
```
