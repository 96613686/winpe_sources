# ComputeService::Management::VmmsVirtualMachineOrchestrator::ModifySettings(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::OrchestratorCallContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void *)

- ea: `0x140072200`
- end: `0x140072f8a`
- name: `?ModifySettings@VmmsVirtualMachineOrchestrator@Management@ComputeService@@UEAA_NAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@UOrchestratorCallContext@23@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@PEAX@Z`
- size: `3466`
- prototype: ``
- caller_count: `0`
- callee_count: `61`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x14001629c`
- `0x140017040`
- `0x14001bc28`
- `0x14001d490`
- `0x140021ea4`
- `0x140021f9c`
- `0x140021ff4`
- `0x140024030`
- `0x14002436c`
- `0x1400243f0`
- `0x140026a80`
- `0x140029350`
- `0x14002a5e4`
- `0x14002aa44`
- `0x14002ac78`
- `0x14002d2d8`
- `0x14002d5a8`
- `0x14002d7f0`
- `0x14002e6ec`
- `0x14002ec30`
- `0x14002f868`
- `0x14003f93c`
- `0x1400421f0`
- `0x14006892c`
- `0x140072200`
- `0x140072f90`
- `0x140073a74`
- `0x140073fb4`
- `0x1400a864c`
- `0x1400b1b08`
- `0x1400c40e0`
- `0x1400c62bc`
- `0x1400c62e0`
- `0x1400c6500`
- `0x1400c6a74`
- `0x1400c6e6c`
- `0x1400c6f74`
- `0x1400c8444`
- `0x1400c980c`
- `0x1400c9b28`
- `0x1400f3944`
- `0x140114548`
- `0x14011a154`
- `0x14012f3dc`
- `0x1401316c0`
- `0x1401332f0`
- `0x140134048`
- `0x14016cee8`
- `0x14016f814`
- `0x140180040`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1400725a3`
- `OLEAUT32!__imp_SysAllocString` at `0x1400725a3`
- `OLEAUT32!__imp_SysFreeString` at `0x1400725e2`
- `OLEAUT32!__imp_SysFreeString` at `0x1400725e2`
- `OLEAUT32!__imp_VariantClear` at `0x14007267e`
- `OLEAUT32!__imp_VariantClear` at `0x14007267e`

## string_xrefs

- `0x140072b61`: `hcs:/VirtualMachine/AccessTrackingBufferSection`
- `0x140072bd1`: `hcs:/VirtualMachine/AccessTrackingBufferSection`
- `0x140072665`: `onecore\vm\compute\management\orchestration\vmmsvirtualmachine\vmmsvirtualmachineorchestrator.cpp`
- `0x1400728ad`: `onecore\vm\compute\management\orchestration\vmmsvirtualmachine\vmmsvirtualmachineorchestrator.cpp`
- `0x140072904`: `onecore\vm\compute\management\orchestration\vmmsvirtualmachine\vmmsvirtualmachineorchestrator.cpp`
- `0x1400729a9`: `onecore\vm\compute\management\orchestration\vmmsvirtualmachine\vmmsvirtualmachineorchestrator.cpp`
- `0x140072a38`: `onecore\vm\compute\management\orchestration\vmmsvirtualmachine\vmmsvirtualmachineorchestrator.cpp`
- `0x140072ac7`: `onecore\vm\compute\management\orchestration\vmmsvirtualmachine\vmmsvirtualmachineorchestrator.cpp`
- `0x140072b1d`: `onecore\vm\compute\management\orchestration\vmmsvirtualmachine\vmmsvirtualmachineorchestrator.cpp`
- `0x140072b8b`: `onecore\vm\compute\management\orchestration\vmmsvirtualmachine\vmmsvirtualmachineorchestrator.cpp`
- `0x140072f78`: `onecore\vm\compute\management\orchestration\vmmsvirtualmachine\vmmsvirtualmachineorchestrator.cpp`
- `0x140072318`: `onecore\vm\compute\management\computesystem\computesystem.h`
- `0x1400725c4`: `onecore\vm\common\vml\VmBstr.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=35
char __fastcall ComputeService::Management::VmmsVirtualMachineOrchestrator::ModifySettings(
        __int64 a1,
        __int64 a2,
        ComputeService::Management::OrchestratorCallContext *a3,
        __int64 a4)
{
  _QWORD *v7; // rcx
  __int64 active; // rax
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // r8
  __int64 v13; // r9
  int *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // rax
  int v19; // edx
  BSTR v20; // rdi
  int v21; // eax
  __int64 v22; // rax
  unsigned int v23; // r8d
  __int64 v24; // rax
  unsigned int v25; // r8d
  __int64 v26; // rax
  DWORD v27; // edi
  __int64 v28; // rsi
  unsigned __int8 v29; // r15
  __int64 SerialNamedPipe; // rax
  int v31; // eax
  __int64 v32; // rdx
  int v33; // eax
  __int64 v34; // rax
  unsigned int v35; // r8d
  __int64 v36; // rax
  unsigned int v37; // r8d
  __int64 v38; // rax
  unsigned int v39; // r8d
  __int64 v40; // rdi
  __int64 v41; // rbx
  __int64 v42; // rax
  struct ComputeService::Vmwp::WorkerProcessContext *v43; // rbx
  __int64 v44; // rax
  struct ComputeService::Vmwp::WorkerProcessContext *v45; // rcx
  __int64 v46; // rax
  __int64 v47; // rax
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rcx
  __int64 v49; // rax
  __int64 v50; // rax
  std::_Ref_count_base **v52; // [rsp+20h] [rbp-E0h]
  int v53; // [rsp+20h] [rbp-E0h]
  int v54; // [rsp+20h] [rbp-E0h]
  void **v55; // [rsp+28h] [rbp-D8h]
  std::_Ref_count_base *v56[2]; // [rsp+30h] [rbp-D0h] BYREF
  ComputeService::Management::OrchestratorCallContext *v57; // [rsp+50h] [rbp-B0h]
  _BYTE v58[336]; // [rsp+60h] [rbp-A0h] BYREF
  struct ComputeService::Vmwp::WorkerProcessContext *v59; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v60[8]; // [rsp+1B8h] [rbp+B8h] BYREF
  struct _GUID bstrString; // [rsp+1C0h] [rbp+C0h] BYREF
  std::_Ref_count_base *v62[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  std::_Ref_count_base *v63; // [rsp+1E0h] [rbp+E0h]
  _QWORD v64[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int128 v65; // [rsp+200h] [rbp+100h] BYREF
  __int128 v66; // [rsp+210h] [rbp+110h]
  __int64 v67; // [rsp+220h] [rbp+120h]
  __int128 v68; // [rsp+228h] [rbp+128h]
  std::_Ref_count_base *v69; // [rsp+238h] [rbp+138h]
  unsigned __int64 v70; // [rsp+240h] [rbp+140h]
  __int16 v71; // [rsp+248h] [rbp+148h]
  int v72; // [rsp+24Ah] [rbp+14Ah]
  __int16 v73; // [rsp+24Eh] [rbp+14Eh]
  int v74[4]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v75; // [rsp+260h] [rbp+160h]
  VARIANTARG pvarg; // [rsp+268h] [rbp+168h] BYREF
  __int64 v77; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int64 v78; // [rsp+2C8h] [rbp+1C8h] BYREF
  __int128 v79; // [rsp+2D0h] [rbp+1D0h]
  __int128 v80; // [rsp+2E0h] [rbp+1E0h]
  __int128 v81; // [rsp+2F0h] [rbp+1F0h]
  int v82; // [rsp+300h] [rbp+200h]
  __int128 v83; // [rsp+310h] [rbp+210h] BYREF
  __int64 v84; // [rsp+320h] [rbp+220h]
  DWORD v85; // [rsp+338h] [rbp+238h]
  __int64 v86; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v87[8]; // [rsp+368h] [rbp+268h] BYREF
  std::_Ref_count_base *v88; // [rsp+370h] [rbp+270h]
  _BYTE v89[336]; // [rsp+380h] [rbp+280h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+518h] [rbp+418h]

  v57 = a3;
  memset_0(v89, 0, sizeof(v89));
  v7 = (_QWORD *)(**(_QWORD **)a2 + 8LL);
  if ( *(_QWORD *)(**(_QWORD **)a2 + 32LL) > 7u )
    v7 = (_QWORD *)*v7;
  *(_QWORD *)&bstrString.Data1 = v7;
  ComputeService::Diagnostics::TraceProvider::VirtualMachine_ModifySettings::Start<unsigned short const *>(
    v89,
    &bstrString);
  v64[0] = 0;
  *(_OWORD *)v62 = 0;
  ComputeService::Diagnostics::TraceProvider::VirtualMachine_ModifySettings::Split(v89, v58);
  active = ComputeService::Management::ActiveServerOperation::ActiveServerOperation(&pvarg, a3);
  v52 = v62;
  ComputeService::Management::BeginGenericOperation_AnyState<ComputeService::Diagnostics::TraceProvider::VirtualMachine_ModifySettings>(
    v64,
    a2,
    active);
  ComputeService::Diagnostics::TraceProvider::VirtualMachine_ModifySettings::~VirtualMachine_ModifySettings((ComputeService::Diagnostics::TraceProvider::VirtualMachine_ModifySettings *)v58);
  LODWORD(v52) = 0;
  v9 = _RTDynamicCast_0(
         *(_QWORD *)(*(_QWORD *)a2 + 8LL),
         0,
         &ComputeService::Management::ComputeSystemState `RTTI Type Descriptor',
         &ComputeService::Management::VirtualMachineState `RTTI Type Descriptor');
  if ( !v9 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\vm\\compute\\management\\computesystem\\computesystem.h",
      (const char *)0x80004001LL,
      0);
  v77 = 0;
  memset_0(&v78, 0, 0x40u);
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  *(_OWORD *)v62 = *(_OWORD *)std::wstring::operator std::basic_string_view<unsigned short>(a4, v56);
  v10 = Marshal::FromJson<Resource::Common::ResourceModificationRequestResponse,>(&pvarg, v62, &v77);
  Marshal::ThrowOnUnmarshalError(v10, 3224830221LL);
  std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&pvarg.decVal.Lo32);
  switch ( (_DWORD)v77 )
  {
    case 0:
      *(_OWORD *)v74 = 0;
      v75 = 0;
      ComputeService::Resource::GetResourceInstances(v74, v9 + 752, 2);
      *(_OWORD *)v56 = 0;
      v11 = std::vector<std::shared_ptr<ComputeService::Resource::IResourceInstance>>::at(v74);
      std::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>(
        v56,
        v11,
        v12,
        v13);
      v62[0] = (std::_Ref_count_base *)10000;
      ComputeService::Management::ActiveStateOperation::CreateCancellationToken(v64, &v62[1]);
      memset_0(&v65, 0, 0x40u);
      (*(void (__fastcall **)(std::_Ref_count_base *, __int128 *, __int64 *, std::_Ref_count_base **, std::_Ref_count_base **))(*(_QWORD *)v56[0] + 48LL))(
        v56[0],
        &v65,
        &v78,
        v62,
        v52);
      Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(&v65);
      if ( v63 )
        std::_Ref_count_base::_Decwref(v63);
      if ( v56[1] )
        std::_Ref_count_base::_Decref(v56[1]);
      v14 = v74;
LABEL_23:
      std::vector<std::shared_ptr<ComputeService::Diagnostics::SystemEntryInner>>::_Tidy(v14);
      goto LABEL_66;
    case 2:
      v59 = 0;
      v83 = 0;
      v84 = 0;
      ComputeService::Resource::GetResourceInstances(&v83, v9 + 752, 3);
      *(_OWORD *)v62 = 0;
      v15 = std::vector<std::shared_ptr<ComputeService::Resource::IResourceInstance>>::at(&v83);
      std::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>(
        v62,
        v15,
        v16,
        v17);
      v86 = 10000;
      ComputeService::Management::ActiveStateOperation::CreateCancellationToken(v64, v87);
      memset_0(&v65, 0, 0x40u);
      (*(void (__fastcall **)(std::_Ref_count_base *, __int128 *, __int64 *, __int64 *))(*(_QWORD *)v62[0] + 48LL))(
        v62[0],
        &v65,
        &v78,
        &v86);
      v18 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<unsigned __int64>(&v65, v56, &v59);
      Marshal::ThrowOnUnmarshalError(v18, 3224830221LL);
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&v56[1]);
      *(_QWORD *)&bstrString.Data1 = 0;
      v20 = SysAllocString(L"CPUGROUP");
      if ( !v20 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x254,
          (unsigned int)"onecore\\vm\\common\\vml\\VmBstr.h",
          (const char *)0x8007000ELL,
          0);
      if ( *(_QWORD *)&bstrString.Data1 )
        SysFreeString(*(BSTR *)&bstrString.Data1);
      *(_QWORD *)&bstrString.Data1 = v20;
      pvarg.vt = 21;
      pvarg.llVal = (LONGLONG)v59;
      *(_QWORD *)v74 = &pvarg;
      v56[0] = (std::_Ref_count_base *)&bstrString;
      LODWORD(v59) = 1;
      v21 = ___InvokeWorkerProcessMethod_UIVmVirtualMachine__KPEAPEAGPEBUtagVARIANT____ZHPEAPEAGPEAU2__Vmwp_ComputeService__YAJAEBUWorkerProcessContext_01_P8IVmVirtualMachine__EAAJKPEAPEAGPEBUtagVARIANT___Z__QEAH__QEAPEAPEAG__QEAPEAU4__Z(
              (int)v9 + 624,
              v19,
              (unsigned int)&v59,
              (unsigned int)v56,
              (__int64)v74);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x588,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmmsvirtualmachine\\vmmsvirtualmachineorchestrator.cpp",
          (const char *)(unsigned int)v21,
          v53);
      VariantClear(&pvarg);
      Vml::VmBstr::~VmBstr((Vml::VmBstr *)&bstrString);
      Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(&v65);
      if ( v88 )
        std::_Ref_count_base::_Decwref(v88);
      if ( v62[1] )
        std::_Ref_count_base::_Decref(v62[1]);
      v14 = (int *)&v83;
      goto LABEL_23;
    case 0x12:
      LODWORD(v59) = 0;
      v22 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<unsigned long>(&v78, &pvarg, &v59);
      Marshal::ThrowOnUnmarshalError(v22, 3224830221LL);
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&pvarg.decVal.Lo32);
      ComputeService::Vmwp::SetResourceAllocationId(
        (ComputeService::Vmwp *)(v9 + 624),
        (const struct ComputeService::Vmwp::WorkerProcessContext *)(unsigned int)v59,
        v23);
      goto LABEL_66;
    case 0x13:
      LODWORD(v59) = 0;
      v24 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<unsigned long>(&v78, &pvarg, &v59);
      Marshal::ThrowOnUnmarshalError(v24, 3224830221LL);
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&pvarg.decVal.Lo32);
      ComputeService::Vmwp::SetResourceMonitoringId(
        (ComputeService::Vmwp *)(v9 + 624),
        (const struct ComputeService::Vmwp::WorkerProcessContext *)(unsigned int)v59,
        v25);
      goto LABEL_66;
    case 0x15:
      LOBYTE(v83) = 0;
      std::wstring::wstring((char *)&v83 + 8);
      v85 = 0;
      v26 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Resource::Serial::SerialModificationRequest>(
              &v78,
              &pvarg,
              &v83);
      Marshal::ThrowOnUnmarshalError(v26, 3224830221LL);
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&pvarg.decVal.Lo32);
      v27 = v85;
      if ( !v85 )
        v27 = 0x2000;
      v28 = -1;
      v56[0] = (std::_Ref_count_base *)-1LL;
      v29 = 0;
      LOBYTE(v56[1]) = 0;
      if ( (unsigned __int8)ComputeService::VmCommonHelpers::IsSerialPortNamedPipe((char *)&v83 + 8) )
      {
        *(_OWORD *)v62 = *(_OWORD *)ComputeService::Management::GetComputeSystemGuid(v62, **(_QWORD **)a2 + 8LL);
        SerialNamedPipe = ComputeService::VmCommonHelpers::CreateSerialNamedPipe(
                            (__int64)v74,
                            (const WCHAR *)&v83 + 4,
                            v27);
        std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>::operator=<std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>,0>(
          v56,
          SerialNamedPipe);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v74);
        v29 = (unsigned __int8)v56[1];
        v28 = (__int64)v56[0];
      }
      *(_QWORD *)&bstrString.Data1 = 0;
      v31 = ComputeService::Vmwp::LookupWorkerProcessDevice(
              (ComputeService::Vmwp *)(v9 + 624),
              (const struct ComputeService::Vmwp::WorkerProcessContext *)&SERIAL_CONTROLLER_DEVICE_ID,
              &SERIAL_CONTROLLER_DEVICE_ID,
              &GUID_451c9ad2_6fe6_4d07_ab13_45aeff7a4bb3,
              &bstrString,
              v55);
      if ( v31 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5B0,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmmsvirtualmachine\\vmmsvirtualmachineorchestrator.cpp",
          (const char *)(unsigned int)v31,
          v54);
      LOBYTE(v32) = v83;
      v33 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD))(**(_QWORD **)&bstrString.Data1 + 32LL))(
              *(_QWORD *)&bstrString.Data1,
              v32,
              v28 & -(__int64)((unsigned __int64)(v28 - 1) <= 0xFFFFFFFFFFFFFFFDuLL),
              v29);
      if ( v33 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5B6,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmmsvirtualmachine\\vmmsvirtualmachineorchestrator.cpp",
          (const char *)(unsigned int)v33,
          v27);
      HvsComPtr<IXmlReader>::~HvsComPtr<IXmlReader>(&bstrString);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v56);
      Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)((char *)&v83 + 8));
      goto LABEL_66;
    case 0x18:
      LODWORD(v59) = 0;
      v34 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<unsigned long>(&v78, &pvarg, &v59);
      Marshal::ThrowOnUnmarshalError(v34, 3224830221LL);
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&pvarg.decVal.Lo32);
      if ( ((*(_QWORD *)(v9 + 648) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5BD,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmmsvirtualmachine\\vmmsvirtualmachineorchestrator.cpp",
          (const char *)0x80070032LL,
          0);
      ComputeService::Vmwp::SetCpuFrequencyPowerCap(
        (ComputeService::Vmwp *)(v9 + 624),
        (const struct ComputeService::Vmwp::WorkerProcessContext *)(unsigned int)v59,
        v35);
      goto LABEL_66;
    case 0x1D:
      LODWORD(v59) = 0;
      v36 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<unsigned long>(&v78, &pvarg, &v59);
      Marshal::ThrowOnUnmarshalError(v36, 3224830221LL);
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&pvarg.decVal.Lo32);
      if ( ((*(_QWORD *)(v9 + 648) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5C5,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmmsvirtualmachine\\vmmsvirtualmachineorchestrator.cpp",
          (const char *)0x80070032LL,
          0);
      ComputeService::Vmwp::SetCpuThrottlePriority(
        (ComputeService::Vmwp *)(v9 + 624),
        (const struct ComputeService::Vmwp::WorkerProcessContext *)(unsigned int)v59,
        v37);
      goto LABEL_66;
    case 0x1E:
      LODWORD(v59) = 0;
      v38 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<unsigned long>(&v78, &pvarg, &v59);
      Marshal::ThrowOnUnmarshalError(v38, 3224830221LL);
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&pvarg.decVal.Lo32);
      if ( ((*(_QWORD *)(v9 + 648) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5CD,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmmsvirtualmachine\\vmmsvirtualmachineorchestrator.cpp",
          (const char *)0x80070032LL,
          0);
      ComputeService::Vmwp::SetCpuBoostPriority(
        (ComputeService::Vmwp *)(v9 + 624),
        (const struct ComputeService::Vmwp::WorkerProcessContext *)(unsigned int)v59,
        v39);
      goto LABEL_66;
  }
  if ( (_DWORD)v77 != 27 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x607,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmmsvirtualmachine\\vmmsvirtualmachineorchestrator.cpp",
      (const char *)0x80070057LL,
      0);
  v40 = v9 + 624;
  if ( ((*(_QWORD *)(v9 + 648) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D2,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmmsvirtualmachine\\vmmsvirtualmachineorchestrator.cpp",
      (const char *)0x80070032LL,
      0);
  switch ( HIDWORD(v77) )
  {
    case 0:
      Schema::Resources::Memory::GuestMemoryAccessTrackingRegisterOperation::GuestMemoryAccessTrackingRegisterOperation((Schema::Resources::Memory::GuestMemoryAccessTrackingRegisterOperation *)&pvarg);
      v49 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Schema::Resources::Memory::GuestMemoryAccessTrackingRegisterOperation>(
              &v78,
              &v83,
              &pvarg);
      Marshal::ThrowOnUnmarshalError(v49, 3224830221LL);
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy((char *)&v83 + 8);
      v65 = 0;
      v66 = 0;
      v67 = 0;
      v70 = vmstd::optional<Schema::Resources::Memory::GuestMemoryAccessTrackingRegisterOperation>::optional<Schema::Resources::Memory::GuestMemoryAccessTrackingRegisterOperation>(&v65).m128_u64[1];
      v68 = 0u;
      v69 = 0;
      LOBYTE(v70) = 0;
      v71 = 0;
      v72 = 0;
      v73 = 0;
      vmstd::optional<Schema::Resources::Memory::GuestMemoryAccessTrackingRegisterOperation>::operator=<Schema::Resources::Memory::GuestMemoryAccessTrackingRegisterOperation &,void>(
        &v65,
        &pvarg);
      v50 = Schema::Resources::Memory::GuestMemoryAccessTrackingOperation::GuestMemoryAccessTrackingOperation(
              (Schema::Resources::Memory::GuestMemoryAccessTrackingOperation *)&v83,
              (const struct Schema::Resources::Memory::GuestMemoryAccessTrackingOperation *)&v65);
      ComputeService::Vmwp::ModifyGuestMemoryAccessTracking(v9 + 624, v50, 0);
      std::vector<Schema::Containers::Definition::InterfaceClass>::_Tidy((char *)&v65 + 8);
      p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&pvarg.llVal;
      goto LABEL_65;
    case 1:
      v60[0] = 0;
      v46 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Schema::Resources::Memory::GuestMemoryAccessTrackingUnregisterOperation>(
              &v78,
              &pvarg,
              v60);
      Marshal::ThrowOnUnmarshalError(v46, 3224830221LL);
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&pvarg.decVal.Lo32);
      v65 = 0;
      v66 = 0;
      v67 = 0;
      v70 = vmstd::optional<Schema::Resources::Memory::GuestMemoryAccessTrackingRegisterOperation>::optional<Schema::Resources::Memory::GuestMemoryAccessTrackingRegisterOperation>(&v65).m128_u64[1];
      v68 = 0u;
      v69 = 0;
      LOBYTE(v70) = 0;
      v71 = 256;
      v72 = 0;
      v73 = 0;
      v47 = Schema::Resources::Memory::GuestMemoryAccessTrackingOperation::GuestMemoryAccessTrackingOperation(
              (Schema::Resources::Memory::GuestMemoryAccessTrackingOperation *)&pvarg,
              (const struct Schema::Resources::Memory::GuestMemoryAccessTrackingOperation *)&v65);
      ComputeService::Vmwp::ModifyGuestMemoryAccessTracking(v9 + 624, v47, 0);
      p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)((char *)&v65 + 8);
LABEL_65:
      std::vector<Schema::Containers::Definition::InterfaceClass>::_Tidy(p_llVal);
      break;
    case 2:
      ComputeService::Resources::ResourceCollection<ComputeService::Resources::ServerResource>::RetrieveByType<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(
        *(_QWORD *)(*(_QWORD *)v64[0] + 48LL) + 72LL,
        v74,
        L"hcs:/VirtualMachine/AccessTrackingBufferSection");
      if ( !LOBYTE(v74[2]) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5F4,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmmsvirtualmachine\\vmmsvirtualmachineorchestrator.cpp",
          (const char *)0x80070057LL,
          0);
      v59 = 0;
      wil::MakeOrThrow<VmHandleBroker,_GUID &,_GUID const &>(&v59, &GUID_NULL, &GUID_NULL);
      if ( !LOBYTE(v74[2]) )
        std::_Throw_bad_optional_access();
      v41 = *(_QWORD *)v74;
      std::wstring::wstring(&pvarg, L"hcs:/VirtualMachine/AccessTrackingBufferSection");
      VmHandleBrokerUtils::PutHandle(v59, &pvarg, 4, v41);
      Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)&pvarg);
      LODWORD(v62[0]) = 0;
      v62[1] = 0;
      v63 = 0;
      v42 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Schema::Resources::Memory::GuestMemoryAccessTrackingQueryOperation>(
              &v78,
              &pvarg,
              v62);
      Marshal::ThrowOnUnmarshalError(v42, 3224830221LL);
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&pvarg.decVal.Lo32);
      v65 = 0;
      v66 = 0;
      v67 = 0;
      v70 = vmstd::optional<Schema::Resources::Memory::GuestMemoryAccessTrackingRegisterOperation>::optional<Schema::Resources::Memory::GuestMemoryAccessTrackingRegisterOperation>(&v65).m128_u64[1];
      v71 = 0;
      v72 = 0;
      v73 = 0;
      v68 = *(_OWORD *)v62;
      v69 = v63;
      LOBYTE(v70) = 1;
      v43 = v59;
      v44 = Schema::Resources::Memory::GuestMemoryAccessTrackingOperation::GuestMemoryAccessTrackingOperation(
              (Schema::Resources::Memory::GuestMemoryAccessTrackingOperation *)&pvarg,
              (const struct Schema::Resources::Memory::GuestMemoryAccessTrackingOperation *)&v65);
      ComputeService::Vmwp::ModifyGuestMemoryAccessTracking(v40, v44, v43);
      std::vector<Schema::Containers::Definition::InterfaceClass>::_Tidy((char *)&v65 + 8);
      v45 = v59;
      if ( v59 )
      {
        v59 = 0;
        (*(void (__fastcall **)(struct ComputeService::Vmwp::WorkerProcessContext *))(*(_QWORD *)v45 + 16LL))(v45);
      }
      std::_Optional_destruct_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,0>::~_Optional_destruct_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,0>(v74);
      break;
  }
LABEL_66:
  Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(&v78);
  ComputeService::Management::ActiveStateOperation::Complete((ComputeService::Management::ActiveStateOperation *)v64, 0);
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v89,
    0);
  std::unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>::~unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>(v64);
  ComputeService::Diagnostics::TraceProvider::VirtualMachine_ModifySettings::~VirtualMachine_ModifySettings((ComputeService::Diagnostics::TraceProvider::VirtualMachine_ModifySettings *)v89);
  ComputeService::Management::OrchestratorCallContext::~OrchestratorCallContext(a3);
  return 1;
}

```

## disassembly

```asm
0x140072200  mov     [rsp-8+arg_0], rbx
0x140072205  push    rbp
0x140072206  push    rsi
0x140072207  push    rdi
0x140072208  push    r12
0x14007220a  push    r13
0x14007220c  push    r14
0x14007220e  push    r15
0x140072210  lea     rbp, [rsp-3E0h]
0x140072218  sub     rsp, 4E0h
0x14007221f  mov     rax, cs:__security_cookie
0x140072226  xor     rax, rsp
0x140072229  mov     [rbp+410h+var_40], rax
0x140072230  mov     rdi, r9
0x140072233  mov     r12, r8
0x140072236  mov     r14, rdx
0x140072239  mov     [rsp+510h+var_4C0], r8
0x14007223e  xor     edx, edx; Val
0x140072240  mov     r8d, 150h; Size
0x140072246  lea     rcx, [rbp+410h+var_190]; void *
0x14007224d  call    memset_0
0x140072252  mov     rax, [r14]
0x140072255  mov     rcx, [rax]
0x140072258  add     rcx, 8
0x14007225c  cmp     qword ptr [rcx+18h], 7
0x140072261  jbe     short loc_140072266
0x140072263  mov     rcx, [rcx]
0x140072266  mov     qword ptr [rbp+410h+bstrString], rcx
0x14007226d  lea     rdx, [rbp+410h+bstrString]
0x140072274  lea     rcx, [rbp+410h+var_190]
0x14007227b  call    ??$Start@PEBG@VirtualMachine_ModifySettings@TraceProvider@Diagnostics@ComputeService@@SA?AV0123@$$QEAPEBG@Z; ComputeService::Diagnostics::TraceProvider::VirtualMachine_ModifySettings::Start<ushort const *>(ushort const * &&)
0x140072280  nop
0x140072281  xor     r13d, r13d
0x140072284  mov     [rbp+410h+var_320], r13
0x14007228b  xorps   xmm0, xmm0
0x14007228e  movdqu  xmmword ptr [rbp+410h+var_340], xmm0
0x140072296  lea     rdx, [rsp+510h+var_4B0]
0x14007229b  lea     rcx, [rbp+410h+var_190]
0x1400722a2  call    ?Split@VirtualMachine_ModifySettings@TraceProvider@Diagnostics@ComputeService@@QEAA?AV1234@XZ; ComputeService::Diagnostics::TraceProvider::VirtualMachine_ModifySettings::Split(void)
0x1400722a7  mov     r9, rax
0x1400722aa  mov     rdx, r12
0x1400722ad  lea     rcx, [rbp+410h+pvarg]
0x1400722b4  call    ??0ActiveServerOperation@Management@ComputeService@@QEAA@$$QEAV012@@Z; ComputeService::Management::ActiveServerOperation::ActiveServerOperation(ComputeService::Management::ActiveServerOperation &&)
0x1400722b9  lea     rcx, [rbp+410h+var_340]
0x1400722c0  mov     [rsp+510h+var_4F0], rcx
0x1400722c5  mov     r8, rax
0x1400722c8  mov     rdx, r14
0x1400722cb  lea     rcx, [rbp+410h+var_320]
0x1400722d2  call    ??$BeginGenericOperation_AnyState@VVirtualMachine_ModifySettings@TraceProvider@Diagnostics@ComputeService@@@Management@ComputeService@@YA?AVActiveStateOperation@01@AEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@VActiveServerOperation@01@$$QEAVVirtualMachine_ModifySettings@TraceProvider@Diagnostics@1@V?$shared_ptr@UStateOperationContext@Management@ComputeService@@@4@@Z; ComputeService::Management::BeginGenericOperation_AnyState<ComputeService::Diagnostics::TraceProvider::VirtualMachine_ModifySettings>(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::ActiveServerOperation,ComputeService::Diagnostics::TraceProvider::VirtualMachine_ModifySettings &&,std::shared_ptr<ComputeService::Management::StateOperationContext>)
0x1400722d7  nop
0x1400722d8  lea     rcx, [rsp+510h+var_4B0]; this
0x1400722dd  call    ??1VirtualMachine_ModifySettings@TraceProvider@Diagnostics@ComputeService@@QEAA@XZ; ComputeService::Diagnostics::TraceProvider::VirtualMachine_ModifySettings::~VirtualMachine_ModifySettings(void)
0x1400722e2  mov     rcx, [r14]
0x1400722e5  mov     dword ptr [rsp+510h+var_4F0], r13d; int
0x1400722ea  lea     r9, ??_R0?AUVirtualMachineState@Management@ComputeService@@@8; ComputeService::Management::VirtualMachineState `RTTI Type Descriptor'
0x1400722f1  lea     r8, ??_R0?AUComputeSystemState@Management@ComputeService@@@8; ComputeService::Management::ComputeSystemState `RTTI Type Descriptor'
0x1400722f8  xor     edx, edx
0x1400722fa  mov     rcx, [rcx+8]
0x1400722fe  call    __RTDynamicCast_0
0x140072303  mov     rbx, rax
0x140072306  mov     rcx, [rbp+418h]; this
0x14007230d  test    rax, rax
0x140072310  jnz     short loc_140072328
0x140072312  mov     r9d, 80004001h; char *
0x140072318  lea     r8, aOnecoreVmCompu_31; "onecore\\vm\\compute\\management\\compu"...
0x14007231f  lea     edx, [rax+5Dh]; void *
0x140072322  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140072328  mov     [rbp+410h+var_250], r13
0x14007232f  mov     r15d, 40h ; '@'
0x140072335  mov     r8d, r15d; Size
0x140072338  xor     edx, edx; Val
0x14007233a  lea     rcx, [rbp+410h+var_248]; void *
0x140072341  call    memset_0
0x140072346  mov     [rbp+410h+var_248], r13
0x14007234d  xorps   xmm0, xmm0
0x140072350  movdqa  [rbp+410h+var_240], xmm0
0x140072358  xorps   xmm1, xmm1
0x14007235b  movdqa  [rbp+410h+var_230], xmm1
0x140072363  movdqa  [rbp+410h+var_220], xmm0
0x14007236b  mov     [rbp+410h+var_210], r13d
0x140072372  lea     rdx, [rsp+510h+var_4E0]
0x140072377  mov     rcx, rdi
0x14007237a  call    ??B?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@1@XZ; std::wstring::operator std::basic_string_view<ushort>(void)
0x14007237f  movups  xmm0, xmmword ptr [rax]
0x140072382  movdqu  xmmword ptr [rbp+410h+var_340], xmm0
0x14007238a  lea     r8, [rbp+410h+var_250]
0x140072391  lea     rdx, [rbp+410h+var_340]
0x140072398  lea     rcx, [rbp+410h+pvarg]
0x14007239f  call    ??$FromJson@UResourceModificationRequestResponse@Common@Resource@@$$V@Marshal@@YA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@PEAUResourceModificationRequestResponse@Common@Resource@@W4UnmarshalFlags@0@@Z; Marshal::FromJson<Resource::Common::ResourceModificationRequestResponse,>(std::basic_string_view<ushort>,Resource::Common::ResourceModificationRequestResponse *,Marshal::UnmarshalFlags)
0x1400723a4  nop
0x1400723a5  mov     esi, 0C037010Dh
0x1400723aa  mov     edx, esi
0x1400723ac  mov     rcx, rax
0x1400723af  call    ?ThrowOnUnmarshalError@Marshal@@YAXAEBU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@J@Z; Marshal::ThrowOnUnmarshalError(std::pair<bool,std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>> const &,long)
0x1400723b4  nop
0x1400723b5  lea     rcx, [rbp+410h+pvarg+8]
0x1400723bc  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x1400723c1  mov     eax, dword ptr [rbp+410h+var_250]
0x1400723c7  test    eax, eax
0x1400723c9  jnz     loc_1400724AD
0x1400723cf  xorps   xmm0, xmm0
0x1400723d2  xor     eax, eax
0x1400723d4  movups  xmmword ptr [rbp+410h+var_2C0], xmm0
0x1400723db  mov     [rbp+410h+var_2B0], rax
0x1400723e2  lea     rdx, [rbx+2F0h]
0x1400723e9  lea     r8d, [r15-3Eh]
0x1400723ed  lea     rcx, [rbp+410h+var_2C0]
0x1400723f4  call    ?GetResourceInstances@Resource@ComputeService@@YA?AV?$vector@V?$shared_ptr@VIResourceInstance@Resource@ComputeService@@@std@@V?$allocator@V?$shared_ptr@VIResourceInstance@Resource@ComputeService@@@std@@@2@@std@@AEBUResourceState@12@W4ResourceType@12@@Z; ComputeService::Resource::GetResourceInstances(ComputeService::Resource::ResourceState const &,ComputeService::Resource::ResourceType)
0x1400723f9  nop
0x1400723fa  xorps   xmm0, xmm0
0x1400723fd  movups  xmmword ptr [rsp+510h+var_4E0], xmm0
0x140072402  lea     rcx, [rbp+410h+var_2C0]
0x140072409  call    ?at@?$vector@V?$shared_ptr@VIResourceInstance@Resource@ComputeService@@@std@@V?$allocator@V?$shared_ptr@VIResourceInstance@Resource@ComputeService@@@std@@@2@@std@@QEAAAEAV?$shared_ptr@VIResourceInstance@Resource@ComputeService@@@2@_K@Z; std::vector<std::shared_ptr<ComputeService::Resource::IResourceInstance>>::at(unsigned __int64)
0x14007240e  mov     rdx, rax
0x140072411  lea     rcx, [rsp+510h+var_4E0]
0x140072416  call    ??0?$shared_ptr@VINetworkResourceAllocator@Resource@ComputeService@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>(std::shared_ptr<ComputeService::Resource::INetworkResourceAllocator> const &)
0x14007241b  nop
0x14007241c  mov     [rbp+410h+var_340], 2710h
0x140072427  lea     rdx, [rbp+410h+var_340+8]
0x14007242e  lea     rcx, [rbp+410h+var_320]
0x140072435  call    ?CreateCancellationToken@ActiveStateOperation@Management@ComputeService@@QEAA?AVCancellationToken@23@XZ; ComputeService::Management::ActiveStateOperation::CreateCancellationToken(void)
0x14007243a  nop
0x14007243b  mov     r8d, r15d; Size
0x14007243e  xor     edx, edx; Val
0x140072440  lea     rcx, [rbp+410h+var_310]; void *
0x140072447  call    memset_0
0x14007244c  mov     rcx, [rsp+510h+var_4E0]
0x140072451  mov     rax, [rcx]
0x140072454  lea     r9, [rbp+410h+var_340]
0x14007245b  lea     r8, [rbp+410h+var_248]
0x140072462  lea     rdx, [rbp+410h+var_310]
0x140072469  mov     rax, [rax+30h]
0x14007246d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140072472  lea     rcx, [rbp+410h+var_310]
0x140072479  call    ??1?$DelayedBase@UMemoryTopology@System@Responses@Schema@@UDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAA@XZ; Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(void)
0x14007247e  nop
0x14007247f  mov     rcx, [rbp+410h+var_330]; this
0x140072486  test    rcx, rcx
0x140072489  jz      short loc_140072491
0x14007248b  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x140072490  nop
0x140072491  mov     rcx, [rsp+510h+var_4E0+8]; this
0x140072496  test    rcx, rcx
0x140072499  jz      short loc_1400724A1
0x14007249b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400724a0  nop
0x1400724a1  lea     rcx, [rbp+410h+var_2C0]
0x1400724a8  jmp     loc_1400726D0
0x1400724ad  cmp     eax, 2
0x1400724b0  jnz     loc_1400726DA
0x1400724b6  mov     [rbp+410h+var_360], r13
0x1400724bd  xorps   xmm0, xmm0
0x1400724c0  xor     eax, eax
0x1400724c2  movups  [rbp+410h+var_200], xmm0
0x1400724c9  mov     [rbp+410h+var_1F0], rax
0x1400724d0  lea     rdx, [rbx+2F0h]
0x1400724d7  lea     r8d, [rax+3]
0x1400724db  lea     rcx, [rbp+410h+var_200]
0x1400724e2  call    ?GetResourceInstances@Resource@ComputeService@@YA?AV?$vector@V?$shared_ptr@VIResourceInstance@Resource@ComputeService@@@std@@V?$allocator@V?$shared_ptr@VIResourceInstance@Resource@ComputeService@@@std@@@2@@std@@AEBUResourceState@12@W4ResourceType@12@@Z; ComputeService::Resource::GetResourceInstances(ComputeService::Resource::ResourceState const &,ComputeService::Resource::ResourceType)
0x1400724e7  nop
0x1400724e8  xorps   xmm0, xmm0
0x1400724eb  movups  xmmword ptr [rbp+410h+var_340], xmm0
0x1400724f2  lea     rcx, [rbp+410h+var_200]
0x1400724f9  call    ?at@?$vector@V?$shared_ptr@VIResourceInstance@Resource@ComputeService@@@std@@V?$allocator@V?$shared_ptr@VIResourceInstance@Resource@ComputeService@@@std@@@2@@std@@QEAAAEAV?$shared_ptr@VIResourceInstance@Resource@ComputeService@@@2@_K@Z; std::vector<std::shared_ptr<ComputeService::Resource::IResourceInstance>>::at(unsigned __int64)
0x1400724fe  mov     rdx, rax
0x140072501  lea     rcx, [rbp+410h+var_340]
0x140072508  call    ??0?$shared_ptr@VINetworkResourceAllocator@Resource@ComputeService@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>(std::shared_ptr<ComputeService::Resource::INetworkResourceAllocator> const &)
0x14007250d  nop
0x14007250e  mov     [rbp+410h+var_1B0], 2710h
0x140072519  lea     rdx, [rbp+410h+var_1A8]
0x140072520  lea     rcx, [rbp+410h+var_320]
0x140072527  call    ?CreateCancellationToken@ActiveStateOperation@Management@ComputeService@@QEAA?AVCancellationToken@23@XZ; ComputeService::Management::ActiveStateOperation::CreateCancellationToken(void)
0x14007252c  nop
0x14007252d  mov     r8, r15; Size
0x140072530  xor     edx, edx; Val
0x140072532  lea     rcx, [rbp+410h+var_310]; void *
0x140072539  call    memset_0
0x14007253e  mov     rcx, [rbp+410h+var_340]
0x140072545  mov     rax, [rcx]
0x140072548  lea     r9, [rbp+410h+var_1B0]
0x14007254f  lea     r8, [rbp+410h+var_248]
0x140072556  lea     rdx, [rbp+410h+var_310]
0x14007255d  mov     rax, [rax+30h]
0x140072561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140072566  nop
0x140072567  lea     r8, [rbp+410h+var_360]
0x14007256e  lea     rdx, [rsp+510h+var_4E0]
0x140072573  lea     rcx, [rbp+410h+var_310]
0x14007257a  call    ??$Unmarshal@_K@?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEBA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@PEA_K@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<unsigned __int64>(unsigned __int64 *)
0x14007257f  nop
0x140072580  mov     edx, esi
0x140072582  mov     rcx, rax
0x140072585  call    ?ThrowOnUnmarshalError@Marshal@@YAXAEBU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@J@Z; Marshal::ThrowOnUnmarshalError(std::pair<bool,std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>> const &,long)
0x14007258a  nop
0x14007258b  lea     rcx, [rsp+510h+var_4E0+8]
0x140072590  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x140072595  mov     qword ptr [rbp+410h+bstrString], r13
0x14007259c  lea     rcx, psz; "CPUGROUP"
0x1400725a3  call    cs:__imp_SysAllocString
0x1400725aa  nop     dword ptr [rax+rax+00h]
0x1400725af  mov     rdi, rax
0x1400725b2  test    rax, rax
0x1400725b5  jnz     short loc_1400725D6
0x1400725b7  mov     rcx, [rbp+418h]; this
0x1400725be  mov     r9d, 8007000Eh; char *
0x1400725c4  lea     r8, aOnecoreVmCommo_30; "onecore\\vm\\common\\vml\\VmBstr.h"
0x1400725cb  mov     edx, 254h; void *
0x1400725d0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400725d6  mov     rcx, qword ptr [rbp+410h+bstrString]; bstrString
0x1400725dd  test    rcx, rcx
0x1400725e0  jz      short loc_1400725EE
0x1400725e2  call    cs:__imp_SysFreeString
0x1400725e9  nop     dword ptr [rax+rax+00h]
0x1400725ee  mov     qword ptr [rbp+410h+bstrString], rdi
0x1400725f5  mov     ecx, 15h
0x1400725fa  mov     word ptr [rbp+410h+pvarg], cx
0x140072601  mov     rax, [rbp+410h+var_360]
0x140072608  mov     qword ptr [rbp+410h+pvarg+8], rax
0x14007260f  lea     rax, [rbp+410h+pvarg]
0x140072616  mov     qword ptr [rbp+410h+var_2C0], rax
0x14007261d  lea     rax, [rbp+410h+bstrString]
0x140072624  mov     [rsp+510h+var_4E0], rax
0x140072629  mov     dword ptr [rbp+410h+var_360], 1
0x140072633  lea     rcx, [rbx+270h]
0x14007263a  lea     rax, [rbp+410h+var_2C0]
0x140072641  mov     [rsp+510h+var_4F0], rax; int
0x140072646  lea     r9, [rsp+510h+var_4E0]
0x14007264b  lea     r8, [rbp+410h+var_360]
0x140072652  call    ??$InvokeWorkerProcessMethod@UIVmVirtualMachine@@KPEAPEAGPEBUtagVARIANT@@$$ZHPEAPEAGPEAU2@@Vmwp@ComputeService@@YAJAEBUWorkerProcessContext@01@P8IVmVirtualMachine@@EAAJKPEAPEAGPEBUtagVARIANT@@@Z$$QEAH$$QEAPEAPEAG$$QEAPEAU4@@Z
0x140072657  mov     rcx, [rbp+418h]; this
0x14007265e  test    eax, eax
0x140072660  jns     short loc_140072677
0x140072662  mov     r9d, eax; char *
0x140072665  lea     r8, aOnecoreVmCompu_43; "onecore\\vm\\compute\\management\\orche"...
0x14007266c  mov     edx, 588h; void *
0x140072671  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140072677  lea     rcx, [rbp+410h+pvarg]; pvarg
0x14007267e  call    cs:__imp_VariantClear
0x140072685  nop     dword ptr [rax+rax+00h]
0x14007268a  nop
0x14007268b  lea     rcx, [rbp+410h+bstrString]; this
0x140072692  call    ??1VmBstr@Vml@@QEAA@XZ; Vml::VmBstr::~VmBstr(void)
0x140072697  nop
0x140072698  lea     rcx, [rbp+410h+var_310]
0x14007269f  call    ??1?$DelayedBase@UMemoryTopology@System@Responses@Schema@@UDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAA@XZ; Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(void)
0x1400726a4  nop
0x1400726a5  mov     rcx, [rbp+410h+var_1A0]; this
0x1400726ac  test    rcx, rcx
0x1400726af  jz      short loc_1400726B7
0x1400726b1  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1400726b6  nop
0x1400726b7  mov     rcx, [rbp+410h+var_340+8]; this
0x1400726be  test    rcx, rcx
0x1400726c1  jz      short loc_1400726C9
0x1400726c3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400726c8  nop
0x1400726c9  lea     rcx, [rbp+410h+var_200]
0x1400726d0  call    ?_Tidy@?$vector@V?$shared_ptr@VSystemEntryInner@Diagnostics@ComputeService@@@std@@V?$allocator@V?$shared_ptr@VSystemEntryInner@Diagnostics@ComputeService@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<ComputeService::Diagnostics::SystemEntryInner>>::_Tidy(void)
0x1400726d5  jmp     loc_140072EFA
0x1400726da  cmp     eax, 12h
0x1400726dd  jnz     short loc_14007272F
0x1400726df  mov     dword ptr [rbp+410h+var_360], r13d
0x1400726e6  lea     r8, [rbp+410h+var_360]
0x1400726ed  lea     rdx, [rbp+410h+pvarg]
0x1400726f4  lea     rcx, [rbp+410h+var_248]
0x1400726fb  call    ??$Unmarshal@K@?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEBA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@PEAK@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<ulong>(ulong *)
0x140072700  nop
0x140072701  mov     edx, esi
0x140072703  mov     rcx, rax
0x140072706  call    ?ThrowOnUnmarshalError@Marshal@@YAXAEBU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@J@Z; Marshal::ThrowOnUnmarshalError(std::pair<bool,std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>> const &,long)
0x14007270b  nop
0x14007270c  lea     rcx, [rbp+410h+pvarg+8]
0x140072713  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x140072718  lea     rcx, [rbx+270h]; this
0x14007271f  mov     edx, dword ptr [rbp+410h+var_360]; struct ComputeService::Vmwp::WorkerProcessContext *
0x140072725  call    ?SetResourceAllocationId@Vmwp@ComputeService@@YAXAEBUWorkerProcessContext@12@I@Z; ComputeService::Vmwp::SetResourceAllocationId(ComputeService::Vmwp::WorkerProcessContext const &,uint)
0x14007272a  jmp     loc_140072EFA
0x14007272f  cmp     eax, 13h
0x140072732  jnz     short loc_140072784
0x140072734  mov     dword ptr [rbp+410h+var_360], r13d
0x14007273b  lea     r8, [rbp+410h+var_360]
0x140072742  lea     rdx, [rbp+410h+pvarg]
0x140072749  lea     rcx, [rbp+410h+var_248]
0x140072750  call    ??$Unmarshal@K@?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEBA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@PEAK@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<ulong>(ulong *)
0x140072755  nop
0x140072756  mov     edx, esi
0x140072758  mov     rcx, rax
0x14007275b  call    ?ThrowOnUnmarshalError@Marshal@@YAXAEBU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@J@Z; Marshal::ThrowOnUnmarshalError(std::pair<bool,std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>> const &,long)
0x140072760  nop
0x140072761  lea     rcx, [rbp+410h+pvarg+8]
0x140072768  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x14007276d  lea     rcx, [rbx+270h]; this
0x140072774  mov     edx, dword ptr [rbp+410h+var_360]; struct ComputeService::Vmwp::WorkerProcessContext *
0x14007277a  call    ?SetResourceMonitoringId@Vmwp@ComputeService@@YAXAEBUWorkerProcessContext@12@I@Z; ComputeService::Vmwp::SetResourceMonitoringId(ComputeService::Vmwp::WorkerProcessContext const &,uint)
0x14007277f  jmp     loc_140072EFA
0x140072784  mov     ecx, 15h
0x140072789  cmp     eax, ecx
0x14007278b  jnz     loc_14007293F
0x140072791  mov     byte ptr [rbp+410h+var_200], r13b
0x140072798  lea     rcx, [rbp+410h+var_200+8]; void *
  ... truncated ...
```
