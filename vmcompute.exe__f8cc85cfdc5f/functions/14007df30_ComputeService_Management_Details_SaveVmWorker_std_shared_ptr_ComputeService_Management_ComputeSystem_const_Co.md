# ComputeService::Management::Details::SaveVmWorker(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::ActiveStateOperation)

- ea: `0x14007df30`
- end: `0x14007e620`
- name: `?SaveVmWorker@Details@Management@ComputeService@@YAXAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@VActiveStateOperation@23@@Z`
- size: `1776`
- prototype: ``
- caller_count: `0`
- callee_count: `42`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x140020890`
- `0x140021f9c`
- `0x14002436c`
- `0x140026a3c`
- `0x140026a80`
- `0x14002716c`
- `0x140027194`
- `0x140027e64`
- `0x14002ac78`
- `0x14002f9e8`
- `0x14007d4a8`
- `0x14007deb8`
- `0x14007df30`
- `0x14007eb7c`
- `0x14007ed7c`
- `0x14007edc4`
- `0x14007ef00`
- `0x14007f03c`
- `0x14007f7e0`
- `0x140080180`
- `0x1400894fc`
- `0x14008d820`
- `0x1400a02f8`
- `0x1400a4514`
- `0x1400c40e0`
- `0x1400c7fe4`
- `0x1400c8278`
- `0x1400c9060`
- `0x1400fdc74`
- `0x1400feb24`
- `0x1401034f8`
- `0x1401332f0`
- `0x1401b1eac`
- `0x1401b2178`
- `0x1401b665c`
- `0x1401c9930`
- `0x1401cb12c`
- `0x1401cb9b8`
- `0x1401d0c0c`
- `0x1402661bc`
- `0x1402a0e5c`
- `0x1402c4010`

## import_xrefs

- `vid!VidOpenStatisticsHandle` at `0x14007e515`
- `vid!VidOpenStatisticsHandle` at `0x14007e515`
- `vid!VidCloneTemplateDetach` at `0x14007e573`
- `vid!VidCloneTemplateDetach` at `0x14007e573`

## string_xrefs

- `0x14007dfef`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x14007e02e`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x14007e117`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x14007e2d5`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x14007e326`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x14007e3bf`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x14007e418`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x14007e482`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x14007e4c6`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x14007e503`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x14007e544`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x14007e58a`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x14007dfa7`: `onecore\vm\compute\management\computesystem\computesystem.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall ComputeService::Management::Details::SaveVmWorker(
        __int64 a1,
        ComputeService::Management::ActiveStateOperation *a2)
{
  _QWORD *v4; // rsi
  __int64 v5; // rax
  __int64 v6; // rdi
  __int64 v8; // rax
  int v9; // ebx
  __int64 v10; // rax
  __int64 v11; // r9
  __int64 v12; // rax
  __int64 v13; // r8
  char v14; // al
  const struct ComputeService::Vmwp::WorkerProcessContext **v15; // r15
  __int64 v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // r8
  __int64 v21; // r9
  int v22; // r8d
  char v23; // dl
  char v24; // al
  int v25; // ecx
  _QWORD *v26; // rax
  __int64 (__fastcall ***v27)(_QWORD, GUID *, _QWORD **); // rbx
  int v28; // eax
  _QWORD *v29; // rax
  struct ComputeService::Vmwp::WorkerProcessContext *v30; // rbx
  int v31; // eax
  struct IVmSimpleTask *v32; // r8
  unsigned int v33; // r9d
  wil::details::in1diag3 *v34; // rcx
  int v35; // eax
  int v36; // eax
  __int64 *v37; // rbx
  __int64 v38; // rax
  int v39; // ecx
  int v40; // r8d
  int v41; // eax
  __int64 v42; // rcx
  int v43; // eax
  __int64 v44; // rcx
  int v45; // eax
  __int64 v46; // rax
  const char *v47; // r9
  int v49; // [rsp+20h] [rbp-E0h]
  int v50; // [rsp+20h] [rbp-E0h]
  char v51; // [rsp+60h] [rbp-A0h] BYREF
  bool v52; // [rsp+61h] [rbp-9Fh] BYREF
  struct ComputeService::Vmwp::WorkerProcessContext *v53; // [rsp+68h] [rbp-98h] BYREF
  __int128 v54; // [rsp+70h] [rbp-90h] BYREF
  _QWORD *v55; // [rsp+80h] [rbp-80h] BYREF
  int v56; // [rsp+88h] [rbp-78h]
  char v57; // [rsp+8Ch] [rbp-74h]
  int v58; // [rsp+90h] [rbp-70h] BYREF
  int v59; // [rsp+94h] [rbp-6Ch] BYREF
  __int64 v60; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v61[3]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v62; // [rsp+B8h] [rbp-48h] BYREF
  __int64 (__fastcall ***v63)(_QWORD, GUID *, _QWORD **); // [rsp+C0h] [rbp-40h] BYREF
  __int64 v64; // [rsp+C8h] [rbp-38h]
  __int128 v65; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v66; // [rsp+E0h] [rbp-20h]
  __int128 v67; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v68; // [rsp+F8h] [rbp-8h]
  int v69; // [rsp+100h] [rbp+0h] BYREF
  char v70[32]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v71[32]; // [rsp+128h] [rbp+28h] BYREF
  int v72; // [rsp+148h] [rbp+48h]
  __int64 v73; // [rsp+14Ch] [rbp+4Ch]
  int v74; // [rsp+154h] [rbp+54h]
  char v75; // [rsp+158h] [rbp+58h]
  char v76; // [rsp+15Ch] [rbp+5Ch]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v61[2] = a2;
  LODWORD(v61[0]) = 0;
  v4 = (_QWORD *)_RTDynamicCast_0(
                   *(_QWORD *)(*(_QWORD *)a1 + 8LL),
                   0,
                   &ComputeService::Management::ComputeSystemState `RTTI Type Descriptor',
                   &ComputeService::Management::VirtualMachineState `RTTI Type Descriptor');
  if ( !v4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\vm\\compute\\management\\computesystem\\computesystem.h",
      (const char *)0x80004001LL,
      0);
  v5 = ComputeService::Management::StateOperation::GetContextAs<ComputeService::Management::Details::SaveVirtualMachineContext>(**(_QWORD **)a2);
  v6 = v5;
  if ( *(_DWORD *)(v5 + 8) == 1 && (*(_QWORD *)(v5 + 32) || *(_QWORD *)(v5 + 64)) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBE6,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
      (const char *)0x80070057LL,
      0);
  v53 = 0;
  wil::AcquireSRWLockExclusive(&v53, v4 + 16);
  if ( v4[25] )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBEC,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
      (const char *)0x80070032LL,
      0);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
    &v53,
    0);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v53);
  v51 = *(_BYTE *)(v6 + 100);
  v58 = v51 != 0;
  v59 = v58;
  v53 = 0;
  v52 = v51 == 0;
  v8 = Vml::VmComMultiInstanceObject<ComputeService::Vmwp::Task>::CreateInstance<bool,_GUID &,unsigned short const (&)[11]>(
         &v52,
         v4 + 78);
  Vml::VmComPtr<IStream>::Attach<Vml::VmComFixedMemStream>(&v53, v8);
  v68 = 0;
  v67 = 0;
  v9 = *(_DWORD *)(*(_QWORD *)(**(_QWORD **)a2 + 48LL) + 28LL);
  v10 = Vml::VmComPtr<IVmSimpleTask>::VmComPtr<IVmSimpleTask>(&v60, &v53);
  v12 = std::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>(
          &v54,
          a1,
          v10,
          v11);
  ComputeService::Management::Details::RegisterTaskForNotifications(v12, a2, v13, &v67);
  v66 = 0;
  v65 = 0;
  v60 = 0;
  if ( (v9 & 2) == 0 || (v14 = 1, v4[339]) )
    v14 = 0;
  if ( v14 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC02,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
      (const char *)0x80070006LL,
      0);
  v15 = (const struct ComputeService::Vmwp::WorkerProcessContext **)(v4 + 339);
  if ( v4[339] )
  {
    ComputeService::Management::ActiveStateOperation::MakeComputeSystemNotificationInfo(a2, &v69);
    v69 = 23;
    v55 = a2;
    *(_QWORD *)&v54 = 0;
    LODWORD(v61[0]) = 1;
    v16 = Vml::VmComMultiInstanceObject_ComputeService::Management::WorkerProcessTaskEventSink_::CreateInstance_std::shared_ptr_ComputeService::Management::ComputeSystem__const___ComputeService::Management::ComputeSystemNotificationInfo__lambda_c988bf7d8964b0e088c76cc30ff03d02___(
            a1,
            &v69,
            &v55);
    Vml::VmComPtr<DmWorkerProcessTracker>::Attach<DmWorkerProcessTracker>(&v54, v16);
    Vml::VmComPtr<ComputeService::Management::WorkerProcessTaskEventSink>::operator=(&v60, &v54);
    Vml::VmComPtr<Vml::VmComLocalMemStream>::~VmComPtr<Vml::VmComLocalMemStream>(&v54);
    v17 = Vml::VmComPtr<ComputeService::Management::WorkerProcessTaskEventSink>::VmComPtr<ComputeService::Management::WorkerProcessTaskEventSink>(
            &v55,
            &v60);
    v18 = Vml::VmComPtr<IVmSimpleTask>::VmComPtr<IVmSimpleTask>(&v54, v4 + 339);
    ComputeService::Vmwp::ComTaskEventRAII<IVmSimpleTask,ComputeService::Management::WorkerProcessTaskEventSink>::RegisterNotification(
      &v65,
      v18,
      v17);
    std::_Variant_base<std::monostate,Schema::Responses::Service::ResultError,Schema::Responses::System::SystemExitStatus,std::wstring>::_Destroy(v71);
  }
  v19 = Vml::VmComPtr<IVmSimpleTask>::VmComPtr<IVmSimpleTask>(&v55, &v53);
  ComputeService::Management::Details::AddTaskToServerOperation(&v54, a2, v19);
  v55 = v61;
  std::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>(
    v61,
    a1,
    v20,
    v21);
  *(_QWORD *)&v54 = &v69;
  v69 = *(_DWORD *)(v6 + 8);
  std::wstring::wstring(v70);
  std::wstring::wstring(v71);
  v72 = *(_DWORD *)(v6 + 80);
  v73 = *(_QWORD *)(v6 + 84);
  v74 = *(_DWORD *)(v6 + 92);
  v75 = *(_BYTE *)(v6 + 96);
  v76 = *(_BYTE *)(v6 + 100);
  v58 = ComputeService::Management::Details::ConfigureSaveFlags((ComputeService::Management::Details::SystemControlContext *)&v69);
  ComputeService::Resources::ResourceCollection<ComputeService::Resources::ServerResource>::RetrieveByType<wil::com_ptr_t<IUnknown,wil::err_exception_policy>>(
    *(_QWORD *)(**(_QWORD **)a2 + 48LL) + 72LL,
    &v63);
  v23 = v64;
  if ( !v51 )
    goto LABEL_24;
  if ( !*(_BYTE *)(v6 + 100) )
    __fastfail(5u);
  v55 = *(_QWORD **)(v6 + 84);
  v56 = *(_DWORD *)(v6 + 92);
  v57 = *(_BYTE *)(v6 + 96);
  if ( !(unsigned __int8)ComputeService::Management::Details::IsHandleBrokeringConfigured(&v55, v64) || (v24 = 1, v23) )
LABEL_24:
    v24 = 0;
  v25 = (int)retaddr;
  if ( v24 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC18,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
      (const char *)0x80070057LL,
      0);
  v26 = 0;
  v62 = 0;
  if ( v23 )
  {
    v27 = v63;
    wil::com_ptr_t<IVmHandleBrokerManager,wil::err_exception_policy>::reset(&v62);
    v28 = (**v27)(v27, &GUID_3dbe3936_af72_4dbd_b314_f689784f692e, &v62);
    v25 = (int)retaddr;
    if ( v28 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC1E,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
        (const char *)(unsigned int)v28,
        0);
    v26 = v62;
  }
  v55 = v26;
  v29 = (_QWORD *)(v6 + 16);
  if ( *(_QWORD *)(v6 + 64) )
    v29 = (_QWORD *)(v6 + 48);
  if ( v29[3] > 7u )
    v29 = (_QWORD *)*v29;
  *(_QWORD *)&v54 = v29;
  v30 = v53;
  v61[0] = v53;
  v31 = ___InvokeWorkerProcessMethod_UIVmVirtualMachine__PEAUIVmSimpleTask__W4__MIDL___MIDL_itf_vmwrkr_0000_0006_0001__W4__MIDL___MIDL_itf_vmwrkr_0000_0006_0002__PEBGPEBGPEBGPEAU2_PEAUIVmHandleBrokerManager____ZPEAU2_AEAW43_AEBW44_AEAY00__CBGAEAY00__CBGPEBGAEAV__VmComPtr_UIVmSimpleTask___Vml__PEAU5__Vmwp_ComputeService__YAJAEBUWorkerProcessContext_01_PEAUIUnknown__P8IVmVirtualMachine__EAAJPEAUIVmSimpleTask__W4__MIDL___MIDL_itf_vmwrkr_0000_0006_0001__W4__MIDL___MIDL_itf_vmwrkr_0000_0006_0002__PEBG552PEAUIVmHandleBrokerManager___Z__QEAPEAU5_AEAW46_AEBW47_AEAY00__CBGAEAY00__CBG__QEAPEBGAEAV__VmComPtr_UIVmSimpleTask___Vml____QEAPEAU8__Z(
          v25,
          v4[80],
          v22,
          (unsigned int)v61,
          (__int64)&v59,
          (__int64)&v58,
          (unsigned int)&szPassword,
          (__int64)&szPassword,
          (__int64)&v54,
          (__int64)(v4 + 339),
          (__int64)&v55);
  v34 = retaddr;
  if ( v31 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC2D,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
      (const char *)(unsigned int)v31,
      v49);
  v35 = -2147023436;
  if ( *v15 )
    v35 = ComputeService::Vmwp::WaitForWorkerProcessTask(
            (ComputeService::Vmwp *)(v4 + 78),
            *v15,
            (struct IVmSimpleTask *)0xFFFFFFFFLL,
            v33);
  if ( *v15 )
  {
    if ( v35 < 0 )
    {
      v59 = -2147467260;
      v36 = ___InvokeWorkerProcessMethod_UIVmVirtualMachine__J__ZJ_Vmwp_ComputeService__YAJAEBUWorkerProcessContext_01_PEAUIUnknown__P8IVmVirtualMachine__EAAJJ_Z__QEAJ_Z(
              v34,
              v4[80],
              v32,
              &v59);
      if ( v36 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC43,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
          (const char *)(unsigned int)v36,
          v49);
    }
  }
  ComputeService::Vmwp::WaitForWorkerProcessTaskThrow((ComputeService::Vmwp *)(v4 + 78), v30, v32, v33);
  if ( *(_DWORD *)(v6 + 8) == 1 )
  {
    v37 = v4 + 120;
    v38 = Vml::VmComMultiInstanceObject<Vml::VmComLocalMemStream>::CreateInstance<>();
    Vml::VmComPtr<IStream>::Attach<Vml::VmComFixedMemStream>(v4 + 120, v38);
    v51 = 0;
    v41 = ___InvokeWorkerProcessMethod_UIVmVirtualMachine__PEAUIStream__H__ZAEAV__VmComPtr_UIStream___Vml___N_Vmwp_ComputeService__YAJAEBUWorkerProcessContext_01_PEAUIUnknown__P8IVmVirtualMachine__EAAJPEAUIStream__H_ZAEAV__VmComPtr_UIStream___Vml____QEA_N_Z(
            v39,
            v4[80],
            v40,
            (int)v4 + 960,
            (__int64)&v51);
    if ( v41 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC52,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
        (const char *)(unsigned int)v41,
        v50);
    v42 = *v37;
    *(_QWORD *)&v54 = 0;
    v43 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD *))(*(_QWORD *)v42 + 40LL))(v42, 0, 2, v4 + 121);
    if ( v43 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC53,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
        (const char *)(unsigned int)v43,
        v50);
    v44 = *v37;
    *(_QWORD *)&v54 = 0;
    v45 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v44 + 40LL))(v44, 0, 0, 0);
    if ( v45 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC54,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
        (const char *)(unsigned int)v45,
        v50);
    v46 = VidOpenStatisticsHandle(retaddr);
    v55 = (_QWORD *)v46;
    if ( ((v46 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC59,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
        (const char *)0x8000FFFFLL,
        v50);
    v54 = *((_OWORD *)v4 + 39);
    if ( !(unsigned int)VidCloneTemplateDetach(v46, &v54, v4 + 118) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xC5C,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
        v47);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>(&v55);
  }
  ComputeService::Management::ActiveStateOperation::Complete(a2, 0);
  HvsComPtr<IXmlReader>::~HvsComPtr<IXmlReader>(&v62);
  std::_Optional_destruct_base<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,0>::~_Optional_destruct_base<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,0>(&v63);
  Vml::VmComPtr<Vml::VmComLocalMemStream>::~VmComPtr<Vml::VmComLocalMemStream>(&v60);
  ComputeService::Vmwp::ComTaskEventRAII<IVmSimpleTask,ComputeService::Management::WorkerProcessTaskEventSink>::~ComTaskEventRAII<IVmSimpleTask,ComputeService::Management::WorkerProcessTaskEventSink>(&v65);
  ComputeService::Vmwp::ComTaskEventRAII<IVmSimpleTask,ComputeService::Management::WorkerProcessTaskEventSink>::~ComTaskEventRAII<IVmSimpleTask,ComputeService::Management::WorkerProcessTaskEventSink>(&v67);
  Vml::VmComPtr<IVmSimpleTaskEvents>::~VmComPtr<IVmSimpleTaskEvents>(&v53);
  return std::unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>::~unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>(a2);
}

```

## disassembly

```asm
0x14007df30  mov     [rsp-8+arg_10], rbx
0x14007df35  push    rbp
0x14007df36  push    rsi
0x14007df37  push    rdi
0x14007df38  push    r12
0x14007df3a  push    r13
0x14007df3c  push    r14
0x14007df3e  push    r15
0x14007df40  lea     rbp, [rsp-0A0h]
0x14007df48  sub     rsp, 1A0h
0x14007df4f  mov     rax, cs:__security_cookie
0x14007df56  xor     rax, rsp
0x14007df59  mov     [rbp+0D0h+var_40], rax
0x14007df60  mov     r14, rdx
0x14007df63  mov     r12, rcx
0x14007df66  mov     [rbp+0D0h+var_120], rdx
0x14007df6a  xor     r15d, r15d
0x14007df6d  mov     dword ptr [rbp+0D0h+var_130], r15d
0x14007df71  mov     rcx, [rcx]
0x14007df74  mov     [rsp+1D0h+var_1B0], r15d; int
0x14007df79  lea     r9, ??_R0?AUVirtualMachineState@Management@ComputeService@@@8; ComputeService::Management::VirtualMachineState `RTTI Type Descriptor'
0x14007df80  lea     r8, ??_R0?AUComputeSystemState@Management@ComputeService@@@8; ComputeService::Management::ComputeSystemState `RTTI Type Descriptor'
0x14007df87  xor     edx, edx
0x14007df89  mov     rcx, [rcx+8]
0x14007df8d  call    __RTDynamicCast_0
0x14007df92  mov     rsi, rax
0x14007df95  mov     rcx, [rbp+0D8h]; this
0x14007df9c  test    rax, rax
0x14007df9f  jnz     short loc_14007DFB7
0x14007dfa1  mov     r9d, 80004001h; char *
0x14007dfa7  lea     r8, aOnecoreVmCompu_31; "onecore\\vm\\compute\\management\\compu"...
0x14007dfae  lea     edx, [rax+5Dh]; void *
0x14007dfb1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007dfb7  mov     rcx, [r14]
0x14007dfba  mov     rcx, [rcx]
0x14007dfbd  call    ??$GetContextAs@USaveVirtualMachineContext@Details@Management@ComputeService@@@StateOperation@Management@ComputeService@@QEBAPEAUSaveVirtualMachineContext@Details@12@XZ; ComputeService::Management::StateOperation::GetContextAs<ComputeService::Management::Details::SaveVirtualMachineContext>(void)
0x14007dfc2  mov     rdi, rax
0x14007dfc5  cmp     dword ptr [rax+8], 1
0x14007dfc9  jnz     short loc_14007DFDB
0x14007dfcb  cmp     [rax+20h], r15
0x14007dfcf  jnz     short loc_14007DFD7
0x14007dfd1  cmp     [rax+40h], r15
0x14007dfd5  jz      short loc_14007DFDB
0x14007dfd7  mov     al, 1
0x14007dfd9  jmp     short loc_14007DFDE
0x14007dfdb  mov     al, r15b
0x14007dfde  mov     rcx, [rbp+0D8h]; this
0x14007dfe5  test    al, al
0x14007dfe7  jz      short loc_14007E001
0x14007dfe9  mov     r9d, 80070057h; char *
0x14007dfef  lea     r8, aOnecoreVmCompu_36; "onecore\\vm\\compute\\management\\orche"...
0x14007dff6  mov     edx, 0BE6h; void *
0x14007dffb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007e001  mov     [rsp+1D0h+var_168], r15
0x14007e006  lea     rdx, [rsi+80h]
0x14007e00d  lea     rcx, [rsp+1D0h+var_168]
0x14007e012  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x14007e017  nop
0x14007e018  cmp     [rsi+0C8h], r15
0x14007e01f  jz      short loc_14007E040
0x14007e021  mov     rcx, [rbp+0D8h]; this
0x14007e028  mov     r9d, 80070032h; char *
0x14007e02e  lea     r8, aOnecoreVmCompu_36; "onecore\\vm\\compute\\management\\orche"...
0x14007e035  mov     edx, 0BECh; void *
0x14007e03a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007e040  xor     edx, edx
0x14007e042  lea     rcx, [rsp+1D0h+var_168]
0x14007e047  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x14007e04c  nop
0x14007e04d  lea     rcx, [rsp+1D0h+var_168]
0x14007e052  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14007e057  mov     al, [rdi+64h]
0x14007e05a  mov     byte ptr [rsp+1D0h+var_170], al
0x14007e05e  mov     ecx, r15d
0x14007e061  test    al, al
0x14007e063  setnz   cl
0x14007e066  mov     [rbp+0D0h+var_140], ecx
0x14007e069  mov     [rbp+0D0h+var_13C], ecx
0x14007e06c  mov     [rsp+1D0h+var_168], r15
0x14007e071  lea     r13, [rsi+270h]
0x14007e078  test    al, al
0x14007e07a  setz    byte ptr [rsp+1D0h+var_170+1]
0x14007e07f  mov     rdx, r13
0x14007e082  lea     rcx, [rsp+1D0h+var_170+1]
0x14007e087  call    ??$CreateInstance@_NAEAU_GUID@@AEAY0L@$$CBG@?$VmComMultiInstanceObject@VTask@Vmwp@ComputeService@@@Vml@@SAPEAVTask@Vmwp@ComputeService@@$$QEA_NAEAU_GUID@@AEAY0L@$$CBG@Z; Vml::VmComMultiInstanceObject<ComputeService::Vmwp::Task>::CreateInstance<bool,_GUID &,ushort const (&)[11]>(bool &&,_GUID &,ushort const (&)[11])
0x14007e08c  mov     rdx, rax
0x14007e08f  lea     rcx, [rsp+1D0h+var_168]
0x14007e094  call    ??$Attach@VVmComFixedMemStream@Vml@@@?$VmComPtr@UIStream@@@Vml@@QEAAXPEAVVmComFixedMemStream@1@@Z; Vml::VmComPtr<IStream>::Attach<Vml::VmComFixedMemStream>(Vml::VmComFixedMemStream *)
0x14007e099  xor     eax, eax
0x14007e09b  mov     [rbp+0D0h+var_D8], rax
0x14007e09f  xorps   xmm1, xmm1
0x14007e0a2  movdqu  [rbp+0D0h+var_E8], xmm1
0x14007e0a7  mov     rax, [r14]
0x14007e0aa  mov     rcx, [rax]
0x14007e0ad  mov     rax, [rcx+30h]
0x14007e0b1  mov     ebx, [rax+1Ch]
0x14007e0b4  lea     rdx, [rsp+1D0h+var_168]
0x14007e0b9  lea     rcx, [rbp+0D0h+var_138]
0x14007e0bd  call    ??0?$VmComPtr@UIVmSimpleTask@@@Vml@@QEAA@AEBV01@@Z; Vml::VmComPtr<IVmSimpleTask>::VmComPtr<IVmSimpleTask>(Vml::VmComPtr<IVmSimpleTask> const &)
0x14007e0c2  mov     r8, rax
0x14007e0c5  mov     rdx, r12
0x14007e0c8  lea     rcx, [rsp+1D0h+var_160]
0x14007e0cd  call    ??0?$shared_ptr@VINetworkResourceAllocator@Resource@ComputeService@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>(std::shared_ptr<ComputeService::Resource::INetworkResourceAllocator> const &)
0x14007e0d2  lea     r9, [rbp+0D0h+var_E8]
0x14007e0d6  mov     rdx, r14
0x14007e0d9  mov     rcx, rax
0x14007e0dc  call    ?RegisterTaskForNotifications@Details@Management@ComputeService@@YAXV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@AEAVActiveStateOperation@23@V?$VmComPtr@UIVmSimpleTask@@@Vml@@AEAV?$ComTaskEventRAII@UIVmSimpleTask@@VWorkerProcessTaskEventSink@Management@ComputeService@@@Vmwp@3@@Z; ComputeService::Management::Details::RegisterTaskForNotifications(std::shared_ptr<ComputeService::Management::ComputeSystem>,ComputeService::Management::ActiveStateOperation &,Vml::VmComPtr<IVmSimpleTask>,ComputeService::Vmwp::ComTaskEventRAII<IVmSimpleTask,ComputeService::Management::WorkerProcessTaskEventSink> &)
0x14007e0e1  xor     eax, eax
0x14007e0e3  mov     [rbp+0D0h+var_F0], rax
0x14007e0e7  xorps   xmm1, xmm1
0x14007e0ea  movdqu  [rbp+0D0h+var_100], xmm1
0x14007e0ef  mov     [rbp+0D0h+var_138], r15
0x14007e0f3  test    bl, 2
0x14007e0f6  jz      short loc_14007E103
0x14007e0f8  cmp     [rsi+0A98h], r15
0x14007e0ff  mov     al, 1
0x14007e101  jz      short loc_14007E106
0x14007e103  mov     al, r15b
0x14007e106  mov     rcx, [rbp+0D8h]; this
0x14007e10d  test    al, al
0x14007e10f  jz      short loc_14007E129
0x14007e111  mov     r9d, 80070006h; char *
0x14007e117  lea     r8, aOnecoreVmCompu_36; "onecore\\vm\\compute\\management\\orche"...
0x14007e11e  mov     edx, 0C02h; void *
0x14007e123  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007e129  lea     r15, [rsi+0A98h]
0x14007e130  cmp     qword ptr [r15], 0
0x14007e134  jz      loc_14007E1CE
0x14007e13a  lea     rdx, [rbp+0D0h+var_D0]
0x14007e13e  mov     rcx, r14
0x14007e141  call    ?MakeComputeSystemNotificationInfo@ActiveStateOperation@Management@ComputeService@@QEAA?AUComputeSystemNotificationInfo@23@XZ; ComputeService::Management::ActiveStateOperation::MakeComputeSystemNotificationInfo(void)
0x14007e146  nop
0x14007e147  mov     [rbp+0D0h+var_D0], 17h
0x14007e14e  mov     [rbp+0D0h+var_150], r14
0x14007e152  mov     qword ptr [rsp+1D0h+var_160], 0
0x14007e15b  mov     dword ptr [rbp+0D0h+var_130], 1
0x14007e162  lea     r8, [rbp+0D0h+var_150]
0x14007e166  lea     rdx, [rbp+0D0h+var_D0]
0x14007e16a  mov     rcx, r12
0x14007e16d  call    Vml__VmComMultiInstanceObject_ComputeService__Management__WorkerProcessTaskEventSink___CreateInstance_std__shared_ptr_ComputeService__Management__ComputeSystem__const___ComputeService__Management__ComputeSystemNotificationInfo__lambda_c988bf7d8964b0e088c76cc30ff03d02___
0x14007e172  mov     rdx, rax
0x14007e175  lea     rcx, [rsp+1D0h+var_160]
0x14007e17a  call    ??$Attach@VDmWorkerProcessTracker@@@?$VmComPtr@VDmWorkerProcessTracker@@@Vml@@QEAAXPEAVDmWorkerProcessTracker@@@Z; Vml::VmComPtr<DmWorkerProcessTracker>::Attach<DmWorkerProcessTracker>(DmWorkerProcessTracker *)
0x14007e17f  lea     rdx, [rsp+1D0h+var_160]
0x14007e184  lea     rcx, [rbp+0D0h+var_138]
0x14007e188  call    ??4?$VmComPtr@VWorkerProcessTaskEventSink@Management@ComputeService@@@Vml@@QEAAAEBV01@$$QEAV01@@Z; Vml::VmComPtr<ComputeService::Management::WorkerProcessTaskEventSink>::operator=(Vml::VmComPtr<ComputeService::Management::WorkerProcessTaskEventSink> &&)
0x14007e18d  nop
0x14007e18e  lea     rcx, [rsp+1D0h+var_160]
0x14007e193  call    ??1?$VmComPtr@VVmComLocalMemStream@Vml@@@Vml@@QEAA@XZ; Vml::VmComPtr<Vml::VmComLocalMemStream>::~VmComPtr<Vml::VmComLocalMemStream>(void)
0x14007e198  lea     rdx, [rbp+0D0h+var_138]
0x14007e19c  lea     rcx, [rbp+0D0h+var_150]
0x14007e1a0  call    ??0?$VmComPtr@VWorkerProcessTaskEventSink@Management@ComputeService@@@Vml@@QEAA@AEBV01@@Z; Vml::VmComPtr<ComputeService::Management::WorkerProcessTaskEventSink>::VmComPtr<ComputeService::Management::WorkerProcessTaskEventSink>(Vml::VmComPtr<ComputeService::Management::WorkerProcessTaskEventSink> const &)
0x14007e1a5  mov     rbx, rax
0x14007e1a8  mov     rdx, r15
0x14007e1ab  lea     rcx, [rsp+1D0h+var_160]
0x14007e1b0  call    ??0?$VmComPtr@UIVmSimpleTask@@@Vml@@QEAA@AEBV01@@Z; Vml::VmComPtr<IVmSimpleTask>::VmComPtr<IVmSimpleTask>(Vml::VmComPtr<IVmSimpleTask> const &)
0x14007e1b5  mov     r8, rbx
0x14007e1b8  mov     rdx, rax
0x14007e1bb  lea     rcx, [rbp+0D0h+var_100]
0x14007e1bf  call    ?RegisterNotification@?$ComTaskEventRAII@UIVmSimpleTask@@VWorkerProcessTaskEventSink@Management@ComputeService@@@Vmwp@ComputeService@@QEAAXV?$VmComPtr@UIVmSimpleTask@@@Vml@@V?$VmComPtr@VWorkerProcessTaskEventSink@Management@ComputeService@@@5@@Z; ComputeService::Vmwp::ComTaskEventRAII<IVmSimpleTask,ComputeService::Management::WorkerProcessTaskEventSink>::RegisterNotification(Vml::VmComPtr<IVmSimpleTask>,Vml::VmComPtr<ComputeService::Management::WorkerProcessTaskEventSink>)
0x14007e1c4  nop
0x14007e1c5  lea     rcx, [rbp+0D0h+var_A8]
0x14007e1c9  call    ?_Destroy@?$_Variant_base@Umonostate@std@@UResultError@Service@Responses@Schema@@USystemExitStatus@System@56@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@std@@QEAAXXZ; std::_Variant_base<std::monostate,Schema::Responses::Service::ResultError,Schema::Responses::System::SystemExitStatus,std::wstring>::_Destroy(void)
0x14007e1ce  lea     rdx, [rsp+1D0h+var_168]
0x14007e1d3  lea     rcx, [rbp+0D0h+var_150]
0x14007e1d7  call    ??0?$VmComPtr@UIVmSimpleTask@@@Vml@@QEAA@AEBV01@@Z; Vml::VmComPtr<IVmSimpleTask>::VmComPtr<IVmSimpleTask>(Vml::VmComPtr<IVmSimpleTask> const &)
0x14007e1dc  mov     r8, rax
0x14007e1df  mov     rdx, r14
0x14007e1e2  lea     rcx, [rsp+1D0h+var_160]
0x14007e1e7  call    ?AddTaskToServerOperation@Details@Management@ComputeService@@YA?AU_GUID@@AEAVActiveStateOperation@23@V?$VmComPtr@UIVmSimpleTask@@@Vml@@@Z; ComputeService::Management::Details::AddTaskToServerOperation(ComputeService::Management::ActiveStateOperation &,Vml::VmComPtr<IVmSimpleTask>)
0x14007e1ec  lea     rax, [rbp+0D0h+var_130]
0x14007e1f0  mov     [rbp+0D0h+var_150], rax
0x14007e1f4  mov     rdx, r12
0x14007e1f7  lea     rcx, [rbp+0D0h+var_130]
0x14007e1fb  call    ??0?$shared_ptr@VINetworkResourceAllocator@Resource@ComputeService@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>(std::shared_ptr<ComputeService::Resource::INetworkResourceAllocator> const &)
0x14007e200  mov     rbx, rax
0x14007e203  lea     rax, [rbp+0D0h+var_D0]
0x14007e207  mov     qword ptr [rsp+1D0h+var_160], rax
0x14007e20c  mov     ecx, [rdi+8]
0x14007e20f  mov     [rbp+0D0h+var_D0], ecx
0x14007e212  lea     rdx, [rdi+10h]
0x14007e216  lea     rcx, [rbp+0D0h+var_C8]
0x14007e21a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14007e21f  nop
0x14007e220  lea     rdx, [rdi+30h]
0x14007e224  lea     rcx, [rbp+0D0h+var_A8]
0x14007e228  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14007e22d  mov     eax, [rdi+50h]
0x14007e230  mov     [rbp+0D0h+var_88], eax
0x14007e233  movsd   xmm0, qword ptr [rdi+54h]
0x14007e238  movsd   [rbp+0D0h+var_84], xmm0
0x14007e23d  mov     eax, [rdi+5Ch]
0x14007e240  mov     [rbp+0D0h+var_7C], eax
0x14007e243  mov     al, [rdi+60h]
0x14007e246  mov     [rbp+0D0h+var_78], al
0x14007e249  mov     al, [rdi+64h]
0x14007e24c  mov     [rbp+0D0h+var_74], al
0x14007e24f  mov     r9d, [rbp+0D0h+var_140]
0x14007e253  mov     r8, rbx
0x14007e256  mov     rdx, rsi
0x14007e259  lea     rcx, [rbp+0D0h+var_D0]; this
0x14007e25d  call    ?ConfigureSaveFlags@Details@Management@ComputeService@@YA?AW4__MIDL___MIDL_itf_vmwrkr_0000_0006_0002@@USaveOptions@Options@Schema@@PEAUVirtualMachineState@23@V?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@W4__MIDL___MIDL_itf_vmwrkr_0000_0006_0001@@@Z; ComputeService::Management::Details::ConfigureSaveFlags(Schema::Options::SaveOptions,ComputeService::Management::VirtualMachineState *,std::shared_ptr<ComputeService::Management::ComputeSystem>,__MIDL___MIDL_itf_vmwrkr_0000_0006_0001)
0x14007e262  mov     [rbp+0D0h+var_140], eax
0x14007e265  mov     rax, [r14]
0x14007e268  mov     rcx, [rax]
0x14007e26b  mov     rcx, [rcx+30h]
0x14007e26f  add     rcx, 48h ; 'H'
0x14007e273  lea     rdx, [rbp+0D0h+var_110]
0x14007e277  call    ??$RetrieveByType@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@@?$ResourceCollection@VServerResource@Resources@ComputeService@@@Resources@ComputeService@@AEAA?AV?$optional@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@@std@@PEBG@Z; ComputeService::Resources::ResourceCollection<ComputeService::Resources::ServerResource>::RetrieveByType<wil::com_ptr_t<IUnknown,wil::err_exception_policy>>(ushort const *)
0x14007e27c  nop
0x14007e27d  mov     rdx, [rbp+0D0h+var_108]
0x14007e281  xor     r12d, r12d
0x14007e284  cmp     byte ptr [rsp+1D0h+var_170], r12b
0x14007e289  jz      short loc_14007E2C1
0x14007e28b  cmp     [rdi+64h], r12b
0x14007e28f  jnz     short loc_14007E298
0x14007e291  lea     ecx, [r12+5]
0x14007e296  int     29h; Win8: RtlFailFast(ecx)
0x14007e298  movsd   xmm0, qword ptr [rdi+54h]
0x14007e29d  movsd   [rbp+0D0h+var_150], xmm0
0x14007e2a2  mov     eax, [rdi+5Ch]
0x14007e2a5  mov     [rbp+0D0h+var_148], eax
0x14007e2a8  mov     al, [rdi+60h]
0x14007e2ab  mov     [rbp+0D0h+var_144], al
0x14007e2ae  lea     rcx, [rbp+0D0h+var_150]
0x14007e2b2  call    ?IsHandleBrokeringConfigured@Details@Management@ComputeService@@YA_NU?$optional@UFeatureOptions@VMPHU@Schema@@@vmstd@@@Z; ComputeService::Management::Details::IsHandleBrokeringConfigured(vmstd::optional<Schema::VMPHU::FeatureOptions>)
0x14007e2b7  test    al, al
0x14007e2b9  jz      short loc_14007E2C1
0x14007e2bb  test    dl, dl
0x14007e2bd  mov     al, 1
0x14007e2bf  jz      short loc_14007E2C4
0x14007e2c1  mov     al, r12b
0x14007e2c4  mov     rcx, [rbp+0D8h]; this
0x14007e2cb  test    al, al
0x14007e2cd  jz      short loc_14007E2E7
0x14007e2cf  mov     r9d, 80070057h; char *
0x14007e2d5  lea     r8, aOnecoreVmCompu_36; "onecore\\vm\\compute\\management\\orche"...
0x14007e2dc  mov     edx, 0C18h; void *
0x14007e2e1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007e2e7  mov     rax, r12
0x14007e2ea  mov     [rbp+0D0h+var_118], rax
0x14007e2ee  test    dl, dl
0x14007e2f0  jz      short loc_14007E33C
0x14007e2f2  mov     rbx, [rbp+0D0h+var_110]
0x14007e2f6  lea     rcx, [rbp+0D0h+var_118]
0x14007e2fa  call    ?reset@?$com_ptr_t@UIVmHandleBrokerManager@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IVmHandleBrokerManager,wil::err_exception_policy>::reset(void)
0x14007e2ff  mov     rax, [rbx]
0x14007e302  lea     r8, [rbp+0D0h+var_118]
0x14007e306  lea     rdx, _GUID_3dbe3936_af72_4dbd_b314_f689784f692e
0x14007e30d  mov     rcx, rbx
0x14007e310  mov     rax, [rax]
0x14007e313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007e318  mov     rcx, [rbp+0D8h]; this
0x14007e31f  test    eax, eax
0x14007e321  jns     short loc_14007E338
0x14007e323  mov     r9d, eax; char *
0x14007e326  lea     r8, aOnecoreVmCompu_36; "onecore\\vm\\compute\\management\\orche"...
0x14007e32d  mov     edx, 0C1Eh; void *
0x14007e332  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007e338  mov     rax, [rbp+0D0h+var_118]
0x14007e33c  mov     [rbp+0D0h+var_150], rax
0x14007e340  cmp     [rdi+40h], r12
0x14007e344  lea     rax, [rdi+10h]
0x14007e348  jz      short loc_14007E34E
0x14007e34a  lea     rax, [rdi+30h]
0x14007e34e  cmp     qword ptr [rax+18h], 7
0x14007e353  jbe     short loc_14007E358
0x14007e355  mov     rax, [rax]
0x14007e358  mov     qword ptr [rsp+1D0h+var_160], rax
0x14007e35d  mov     rbx, [rsp+1D0h+var_168]
0x14007e362  mov     [rbp+0D0h+var_130], rbx
0x14007e366  lea     rax, [rbp+0D0h+var_150]
0x14007e36a  mov     [rsp+1D0h+var_180], rax
0x14007e36f  mov     [rsp+1D0h+var_188], r15
0x14007e374  lea     rax, [rsp+1D0h+var_160]
0x14007e379  mov     [rsp+1D0h+var_190], rax
0x14007e37e  lea     rax, szPassword
0x14007e385  mov     [rsp+1D0h+var_198], rax
0x14007e38a  mov     [rsp+1D0h+var_1A0], rax
0x14007e38f  lea     rax, [rbp+0D0h+var_140]
0x14007e393  mov     [rsp+1D0h+var_1A8], rax
0x14007e398  lea     rax, [rbp+0D0h+var_13C]
0x14007e39c  mov     qword ptr [rsp+1D0h+var_1B0], rax; int
0x14007e3a1  lea     r9, [rbp+0D0h+var_130]
0x14007e3a5  mov     rdx, [rsi+280h]
0x14007e3ac  call    ??$InvokeWorkerProcessMethod@UIVmVirtualMachine@@PEAUIVmSimpleTask@@W4__MIDL___MIDL_itf_vmwrkr_0000_0006_0001@@W4__MIDL___MIDL_itf_vmwrkr_0000_0006_0002@@PEBGPEBGPEBGPEAU2@PEAUIVmHandleBrokerManager@@$$ZPEAU2@AEAW43@AEBW44@AEAY00$$CBGAEAY00$$CBGPEBGAEAV?$VmComPtr@UIVmSimpleTask@@@Vml@@PEAU5@@Vmwp@ComputeService@@YAJAEBUWorkerProcessContext@01@PEAUIUnknown@@P8IVmVirtualMachine@@EAAJPEAUIVmSimpleTask@@W4__MIDL___MIDL_itf_vmwrkr_0000_0006_0001@@W4__MIDL___MIDL_itf_vmwrkr_0000_0006_0002@@PEBG552PEAUIVmHandleBrokerManager@@@Z$$QEAPEAU5@AEAW46@AEBW47@AEAY00$$CBGAEAY00$$CBG$$QEAPEBGAEAV?$VmComPtr@UIVmSimpleTask@@@Vml@@$$QEAPEAU8@@Z
0x14007e3b1  mov     rcx, [rbp+0D8h]; this
0x14007e3b8  test    eax, eax
0x14007e3ba  jns     short loc_14007E3D1
0x14007e3bc  mov     r9d, eax; char *
0x14007e3bf  lea     r8, aOnecoreVmCompu_36; "onecore\\vm\\compute\\management\\orche"...
0x14007e3c6  mov     edx, 0C2Dh; void *
0x14007e3cb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007e3d1  mov     eax, 800705B4h
0x14007e3d6  mov     rdx, [r15]; struct ComputeService::Vmwp::WorkerProcessContext *
0x14007e3d9  test    rdx, rdx
0x14007e3dc  jz      short loc_14007E3EA
0x14007e3de  or      r8d, 0FFFFFFFFh; struct IVmSimpleTask *
0x14007e3e2  mov     rcx, r13; this
0x14007e3e5  call    ?WaitForWorkerProcessTask@Vmwp@ComputeService@@YAJAEBUWorkerProcessContext@12@PEAUIVmSimpleTask@@K@Z; ComputeService::Vmwp::WaitForWorkerProcessTask(ComputeService::Vmwp::WorkerProcessContext const &,IVmSimpleTask *,ulong)
  ... truncated ...
```
