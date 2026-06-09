# ComputeService::Management::VmmsVirtualMachineOrchestrator::Construct(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::OrchestratorCallContext,IVmHandleBrokerManager *,ComputeService::Management::IComputeSystemStore *)

- ea: `0x1401de020`
- end: `0x1401df055`
- name: `?Construct@VmmsVirtualMachineOrchestrator@Management@ComputeService@@UEAA_NAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@UOrchestratorCallContext@23@PEAUIVmHandleBrokerManager@@PEAVIComputeSystemStore@23@@Z`
- size: `4149`
- prototype: ``
- caller_count: `0`
- callee_count: `77`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1400142a0`
- `0x140017040`
- `0x140018d70`
- `0x14001bc28`
- `0x14001d490`
- `0x140021ea4`
- `0x140021ff4`
- `0x140024030`
- `0x14002436c`
- `0x140024f6c`
- `0x14002d7f0`
- `0x14002fa20`
- `0x1400316cc`
- `0x140038268`
- `0x14003f568`
- `0x1400421f0`
- `0x140042468`
- `0x140044974`
- `0x140058738`
- `0x14006512c`
- `0x1400692a8`
- `0x140076388`
- `0x140076488`
- `0x140077dbc`
- `0x140079c9c`
- `0x14007ef00`
- `0x140080180`
- `0x1400958a8`
- `0x140095918`
- `0x1400959a0`
- `0x140095b70`
- `0x1400a1518`
- `0x1400a5eb0`
- `0x1400a864c`
- `0x1400ad53c`
- `0x1400b1b08`
- `0x1400b2a44`
- `0x1400b3034`
- `0x1400b3bc4`
- `0x1400b4cc8`
- `0x1400b538c`
- `0x1400b5488`
- `0x1400c40e0`
- `0x1400c4154`
- `0x1400da39c`
- `0x1400e74e4`
- `0x1400fed74`
- `0x140106acc`
- `0x14011fcb4`
- `0x14012b25c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401dece4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401dece4`
- `vid!VidOpenResourcePartition` at `0x1401de299`
- `vid!VidOpenResourcePartition` at `0x1401de299`
- `vid!VidQueryResourcePartitionComponent` at `0x1401decd4`
- `vid!VidQueryResourcePartitionComponent` at `0x1401decd4`

## string_xrefs

- `0x1401deebc`: `onecore\vm\compute\management\orchestration\vmmsvirtualmachine\vmmsvirtualmachineorchestrator.cpp`
- `0x1401deed1`: `onecore\vm\compute\management\orchestration\vmmsvirtualmachine\vmmsvirtualmachineorchestrator.cpp`
- `0x1401def19`: `onecore\vm\compute\management\orchestration\vmmsvirtualmachine\vmmsvirtualmachineorchestrator.cpp`
- `0x1401def2b`: `onecore\vm\compute\management\orchestration\vmmsvirtualmachine\vmmsvirtualmachineorchestrator.cpp`
- `0x1401def40`: `onecore\vm\compute\management\orchestration\vmmsvirtualmachine\vmmsvirtualmachineorchestrator.cpp`
- `0x1401def55`: `onecore\vm\compute\management\orchestration\vmmsvirtualmachine\vmmsvirtualmachineorchestrator.cpp`
- `0x1401def67`: `onecore\vm\compute\management\orchestration\vmmsvirtualmachine\vmmsvirtualmachineorchestrator.cpp`
- `0x1401def7f`: `onecore\vm\compute\management\orchestration\vmmsvirtualmachine\vmmsvirtualmachineorchestrator.cpp`
- `0x1401def94`: `onecore\vm\compute\management\orchestration\vmmsvirtualmachine\vmmsvirtualmachineorchestrator.cpp`
- `0x1401defa9`: `onecore\vm\compute\management\orchestration\vmmsvirtualmachine\vmmsvirtualmachineorchestrator.cpp`
- `0x1401defcc`: `onecore\vm\compute\management\orchestration\vmmsvirtualmachine\vmmsvirtualmachineorchestrator.cpp`
- `0x1401defe1`: `onecore\vm\compute\management\orchestration\vmmsvirtualmachine\vmmsvirtualmachineorchestrator.cpp`
- `0x1401df004`: `onecore\vm\compute\management\orchestration\vmmsvirtualmachine\vmmsvirtualmachineorchestrator.cpp`
- `0x1401df019`: `onecore\vm\compute\management\orchestration\vmmsvirtualmachine\vmmsvirtualmachineorchestrator.cpp`
- `0x1401df02b`: `onecore\vm\compute\management\orchestration\vmmsvirtualmachine\vmmsvirtualmachineorchestrator.cpp`
- `0x1401df043`: `onecore\vm\compute\management\orchestration\vmmsvirtualmachine\vmmsvirtualmachineorchestrator.cpp`
- `0x1401def01`: `onecore\vm\compute\management\computesystem\computesystem.h`
- `0x1401deee9`: `onecore\vm\compute\management\computesystem\ComputeSystem.h`
- `0x1401de5f1`: `COM%d`
- `0x1401deeb0`: `Job object provided by both resource partition and handle broker`

## pseudocode

```c
// Hidden C++ exception states: #wind=39
char __fastcall ComputeService::Management::VmmsVirtualMachineOrchestrator::Construct(
        __int64 a1,
        __int64 **a2,
        ComputeService::Management::OrchestratorCallContext *a3,
        VmHandleBrokerUtils *a4)
{
  ComputeService::Management::OrchestratorCallContext *v5; // r12
  HyperVRepository *v8; // rcx
  char *v9; // r15
  const unsigned __int16 *v10; // rdx
  __int64 v11; // rdi
  ComputeService::VmCommonHelpers *v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rdx
  _QWORD *v15; // rcx
  struct IVmHandleBrokerManager *v16; // r8
  __int64 *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // r14
  __int64 v20; // rax
  const char *v21; // r9
  __int64 *v22; // rcx
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rax
  __int64 MemoryBalancerInformation; // rax
  __int64 v27; // rbx
  __int64 v28; // r8
  unsigned __int8 i; // si
  __int64 v30; // rbx
  __int64 v31; // rdx
  __int64 *v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  __int64 v35; // r14
  __int64 (__fastcall *v36)(__int64, _OWORD *, _QWORD *, __int64 *); // r15
  __int64 v37; // rcx
  int v38; // eax
  __int64 v39; // rax
  int v40; // eax
  HyperVRepository *v41; // rdx
  __int128 v42; // xmm6
  __int64 *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  __int64 v46; // rbx
  __int64 (__fastcall *v47)(__int64, __int128 *, _OWORD *, __int64 *); // rsi
  __int64 v48; // rcx
  int v49; // eax
  unsigned int v50; // esi
  __int64 v51; // rbx
  __int64 v52; // r14
  __int64 v53; // rdx
  __int64 *v54; // rcx
  __int64 v55; // rax
  int v56; // eax
  __int64 v57; // rax
  __int64 v58; // rcx
  _QWORD *PathForVirtualDevice; // rax
  int v60; // eax
  __int64 *v61; // rsi
  bool v62; // dl
  ComputeService::Management::VirtualMachineUtils *v63; // rcx
  HyperVRepository *v64; // rbx
  struct IUnknown *v65; // rbx
  struct IUnknown *v66; // rsi
  char NumaSpanningSetting; // al
  unsigned __int16 *v68; // rcx
  __int64 v69; // r14
  DWORD LastError; // eax
  _QWORD *v71; // r8
  __int64 v72; // rax
  const struct ComputeService::Management::VirtualMachineConfiguration *v73; // rdx
  unsigned int v75; // eax
  unsigned int v76; // eax
  unsigned int v77; // eax
  int v78; // [rsp+28h] [rbp-E0h]
  unsigned int v79; // [rsp+28h] [rbp-E0h]
  char *v80; // [rsp+30h] [rbp-D8h]
  HyperVRepository *v81; // [rsp+58h] [rbp-B0h] BYREF
  HyperVRepository *v82[2]; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD v83[3]; // [rsp+70h] [rbp-98h] BYREF
  char *v84[2]; // [rsp+88h] [rbp-80h] BYREF
  __int128 v85; // [rsp+98h] [rbp-70h] BYREF
  struct IUnknown *v86[2]; // [rsp+A8h] [rbp-60h] BYREF
  _OWORD v87[2]; // [rsp+B8h] [rbp-50h] BYREF
  _QWORD v88[2]; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v89; // [rsp+E8h] [rbp-20h]
  _QWORD *v90; // [rsp+F0h] [rbp-18h] BYREF
  char v91[16]; // [rsp+F8h] [rbp-10h] BYREF
  unsigned __int64 v92; // [rsp+108h] [rbp+0h]
  __int64 **v93; // [rsp+110h] [rbp+8h]
  ComputeService::Management::OrchestratorCallContext *v94; // [rsp+118h] [rbp+10h]
  __int64 v95; // [rsp+120h] [rbp+18h] BYREF
  int v96; // [rsp+128h] [rbp+20h] BYREF
  __int64 v97; // [rsp+130h] [rbp+28h] BYREF
  __int64 v98; // [rsp+138h] [rbp+30h] BYREF
  int v99[2]; // [rsp+140h] [rbp+38h] BYREF
  char v100[8]; // [rsp+148h] [rbp+40h] BYREF
  _BYTE v101[24]; // [rsp+150h] [rbp+48h] BYREF
  __int64 v102; // [rsp+168h] [rbp+60h] BYREF
  _BYTE v103[32]; // [rsp+170h] [rbp+68h] BYREF
  __int64 v104; // [rsp+190h] [rbp+88h]
  __int64 v105; // [rsp+198h] [rbp+90h] BYREF
  __int128 v106; // [rsp+1A0h] [rbp+98h] BYREF
  __int64 v107; // [rsp+1B0h] [rbp+A8h] BYREF
  __int128 v108; // [rsp+1B8h] [rbp+B0h]
  __int128 v109; // [rsp+1C8h] [rbp+C0h]
  __int64 v110; // [rsp+1D8h] [rbp+D0h]
  __int16 v111; // [rsp+1E0h] [rbp+D8h]
  char v112; // [rsp+1E2h] [rbp+DAh]
  int v113; // [rsp+1E3h] [rbp+DBh]
  char v114; // [rsp+1E7h] [rbp+DFh]
  __int128 v115; // [rsp+1E8h] [rbp+E0h] BYREF
  _BYTE v116[32]; // [rsp+1F8h] [rbp+F0h] BYREF
  _BYTE v117[32]; // [rsp+218h] [rbp+110h] BYREF
  char v118; // [rsp+238h] [rbp+130h]
  int v119; // [rsp+239h] [rbp+131h]
  __int16 v120; // [rsp+23Dh] [rbp+135h]
  char v121; // [rsp+23Fh] [rbp+137h]
  __int64 v122; // [rsp+248h] [rbp+140h] BYREF
  __int128 v123; // [rsp+250h] [rbp+148h] BYREF
  __int128 v124; // [rsp+260h] [rbp+158h]
  _BYTE v125[24]; // [rsp+270h] [rbp+168h] BYREF
  _BYTE v126[136]; // [rsp+288h] [rbp+180h] BYREF
  __int16 v127; // [rsp+310h] [rbp+208h]
  int v128; // [rsp+312h] [rbp+20Ah]
  __int16 v129; // [rsp+316h] [rbp+20Eh]
  char v130[8]; // [rsp+318h] [rbp+210h] BYREF
  _BYTE v131[200]; // [rsp+320h] [rbp+218h] BYREF
  _BYTE v132[336]; // [rsp+3E8h] [rbp+2E0h] BYREF
  _BYTE v133[1952]; // [rsp+538h] [rbp+430h] BYREF
  _BYTE Buf1[304]; // [rsp+CD8h] [rbp+BD0h] BYREF
  __int64 *v135; // [rsp+E08h] [rbp+D00h]
  char v136[32]; // [rsp+EC0h] [rbp+DB8h] BYREF
  _QWORD v137[3]; // [rsp+EE0h] [rbp+DD8h] BYREF
  _OWORD v138[2]; // [rsp+EF8h] [rbp+DF0h] BYREF
  __int64 v139; // [rsp+F18h] [rbp+E10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F70h] [rbp+E68h]

  v5 = a3;
  *(_QWORD *)&v85 = a3;
  v93 = a2;
  v94 = a3;
  v115 = *(_OWORD *)ComputeService::Management::GetComputeSystemGuid(v87, **a2 + 8);
  memset_0(v132, 0, sizeof(v132));
  v8 = (HyperVRepository *)(**a2 + 8);
  if ( *(_QWORD *)(**a2 + 32) > 7u )
    v8 = *(HyperVRepository **)v8;
  v82[0] = v8;
  ComputeService::Diagnostics::TraceProvider::VirtualMachine_Construct::Start<unsigned short const *>(v132, v82);
  v9 = (char *)_RTDynamicCast_0(
                 **a2,
                 0,
                 &ComputeService::Management::ComputeSystemConfiguration `RTTI Type Descriptor',
                 &ComputeService::Management::VirtualMachineConfiguration `RTTI Type Descriptor');
  v84[0] = v9;
  if ( !v9 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\vm\\compute\\management\\computesystem\\ComputeSystem.h",
      (const char *)0x80004001LL,
      0);
  v11 = _RTDynamicCast_0(
          (*a2)[1],
          0,
          &ComputeService::Management::ComputeSystemState `RTTI Type Descriptor',
          &ComputeService::Management::VirtualMachineState `RTTI Type Descriptor');
  if ( !v11 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\vm\\compute\\management\\computesystem\\computesystem.h",
      (const char *)0x80004001LL,
      0);
  if ( *(_BYTE *)(a1 + 24) )
  {
    v12 = (ComputeService::VmCommonHelpers *)(**a2 + 8);
    if ( *(_QWORD *)(**a2 + 32) > 7u )
      v12 = *(ComputeService::VmCommonHelpers **)v12;
    ComputeService::VmCommonHelpers::VerifyHyperVInstalled(v12, v10);
  }
  *(_BYTE *)(v11 + 1728) = *(_BYTE *)(a1 + 24);
  v89 = 257;
  v88[0] = a1;
  v88[1] = a2;
  ComputeService::Telemetry::IncrementDensityCounters(*(unsigned int *)(**a2 + 40));
  v13 = **a2;
  v14 = *(unsigned int *)(v13 + 40);
  v15 = (_QWORD *)(v13 + 8);
  if ( v15[3] > 7u )
    v15 = (_QWORD *)*v15;
  ComputeService::RecoveryStore::RecordSystem(v15, v14);
  v81 = 0;
  ComputeService::Vmwp::CreateRepository(&v81, &v115);
  if ( *(_QWORD *)(v11 + 2624) )
    ComputeService::Management::VmmsConfigHelpers::LoadRepositoryContents(&v81, v11 + 2608);
  Config::VmWorkerProcess::Configuration::Configuration((Config::VmWorkerProcess::Configuration *)v133);
  if ( !*(_BYTE *)Marshal::FromRepositoryXml<Vml::VmReferencePtr<HyperVRepository,Vml::VmUserReferenceTraits> &,Config::VmWorkerProcess::Configuration,>(
                    v100,
                    &v81,
                    v133) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x225,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmmsvirtualmachine\\vmmsvirtualmachineorchestrator.cpp",
      (const char *)0x80070057LL,
      0);
  std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(v101);
  std::wstring::operator=(v11 + 2656, v136);
  if ( a4 )
  {
    VmHandleBrokerUtils::DuplicateManager(a4, *(struct IVmHandleBrokerManager **)(v11 + 1736), v16);
  }
  else
  {
    v53 = *v135;
    v95 = *v135;
    while ( !*(_BYTE *)(v53 + 25) )
    {
      std::pair<unsigned __int64 const,Config::Devices::Manifest::DeviceEntry>::pair<unsigned __int64 const,Config::Devices::Manifest::DeviceEntry>(
        &v122,
        v53 + 32);
      v98 = 0;
      v54 = *(__int64 **)(v11 + 1736);
      v55 = *v54;
      v98 = 0;
      *(_OWORD *)&v83[1] = v123;
      *(_OWORD *)v86 = v124;
      v56 = (*(__int64 (__fastcall **)(__int64 *, struct IUnknown **, _QWORD *, __int64 *))(v55 + 24))(
              v54,
              v86,
              &v83[1],
              &v98);
      if ( v56 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x241,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmmsvirtualmachine\\vmmsvirtualmachineorchestrator.cpp",
          (const char *)(unsigned int)v56,
          0);
      HvsComPtr<IXmlReader>::~HvsComPtr<IXmlReader>(&v98);
      Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v125);
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Schema::VirtualMachines::Resources::Vpci::VirtualPciDevice>>>,std::_Iterator_base0>::operator++(&v95);
      v53 = v95;
    }
  }
  v97 = 0;
  v17 = *(__int64 **)(v11 + 1736);
  v18 = *v17;
  v97 = 0;
  *(GUID *)&v83[1] = GUID_NULL;
  (*(void (__fastcall **)(__int64 *, _QWORD *, __int64 *))(v18 + 32))(v17, &v83[1], &v97);
  v19 = -1;
  v98 = -1;
  if ( memcmp_0(Buf1, &GUID_NULL, 0x10u) )
  {
    v20 = VidOpenResourcePartition(Buf1);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v98,
      v20);
    v19 = v98;
    if ( (unsigned __int64)(v98 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x25B,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmmsvirtualmachine\\vmmsvirtualmachineorchestrator.cpp",
        v21);
    if ( !v97 )
    {
      v22 = *(__int64 **)(v11 + 1736);
      v23 = *v22;
      v97 = 0;
      *(GUID *)&v83[1] = GUID_NULL;
      *(GUID *)v86 = GUID_NULL;
      v24 = (*(__int64 (__fastcall **)(__int64 *, struct IUnknown **, _QWORD *, __int64 *))(v23 + 24))(
              v22,
              v86,
              &v83[1],
              &v97);
      if ( v24 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x25E,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmmsvirtualmachine\\vmmsvirtualmachineorchestrator.cpp",
          (const char *)(unsigned int)v24,
          0);
    }
    std::wstring::wstring(v100, L"hcs:/VirtualMachine/ResourcePartition");
    VmHandleBrokerUtils::PutHandle(v97, v100, 0, v19);
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v100);
  }
  v25 = Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(
          v82,
          &v81);
  ComputeService::Management::VirtualMachineUtils::AllocateResources(v9, v11, v25, v11 + 1744, v19);
  *(_OWORD *)v86 = 0;
  MemoryBalancerInformation = ComputeService::VmCommonHelpers::GetMemoryBalancerInformation(&v83[1], v11 + 752);
  std::pair<Vml::VmComPtr<IMemoryBalancer>,Vml::VmComPtr<IVmSimpleTask>>::operator=<std::pair<Vml::VmComPtr<IMemoryBalancer>,Vml::VmComPtr<IVmSimpleTask>>,0>(
    v86,
    MemoryBalancerInformation);
  std::pair<Vml::VmComPtr<IMemoryBalancer>,Vml::VmComPtr<IVmSimpleTask>>::~pair<Vml::VmComPtr<IMemoryBalancer>,Vml::VmComPtr<IVmSimpleTask>>(&v83[1]);
  v95 = 0;
  std::_Tree<std::_Tmap_traits<_GUID,Marshal::DelayedBase<Config::Devices::Device,Marshal::Details::DelayedXmlTraits>,Marshal::GuidLess,std::allocator<std::pair<_GUID const,Marshal::DelayedBase<Config::Devices::Device,Marshal::Details::DelayedXmlTraits>>>,0>>::find(
    v137,
    &v95,
    &SERIAL_CONTROLLER_DEVICE_ID);
  v27 = v95;
  if ( v95 != v137[0] )
  {
    v122 = 0;
    memset_0(&v123, 0, 0xC0u);
    `eh vector constructor iterator'(
      &v123,
      0x30u,
      4u,
      (void (*)(void *))Config::Devices::Serial::Port::Port,
      (void (*)(void *))Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump);
    v127 = 0;
    v128 = 0;
    v129 = 0;
    Marshal::DelayedBase<Config::Devices::Device,Marshal::Details::DelayedXmlTraits>::Unmarshal<Config::Devices::Serial::SerialController>(
      v27 + 48,
      v100,
      &v122);
    if ( v100[0] )
    {
      Config::Devices::Serial::SerialController::SerialController((Config::Devices::Serial::SerialController *)v130);
      *(_OWORD *)v82 = 0;
      VmRepositoryAutoLock::VmRepositoryAutoLock(v82, v81, 1);
      if ( SLODWORD(v82[1]) < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x27F,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmmsvirtualmachine\\vmmsvirtualmachineorchestrator.cpp",
          (const char *)LODWORD(v82[1]),
          v78);
      if ( !*(_BYTE *)Marshal::FromDeviceRepositoryXml<Config::Devices::Serial::SerialController>(&v90, v81, v28, v130) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x280,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmmsvirtualmachine\\vmmsvirtualmachineorchestrator.cpp",
          (const char *)0x8007000DLL,
          v78);
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(v91);
      for ( i = 0; i < 4u; ++i )
      {
        v30 = 48LL * i;
        std::wstring::assign(&v131[v30], &szPassword);
        if ( (unsigned __int8)ComputeService::VmCommonHelpers::IsSerialPortNamedPipe((char *)&v123 + v30) )
        {
          if ( !*(_DWORD *)&v125[48 * i + 4] )
            *(_DWORD *)&v125[48 * i + 4] = 0x2000;
          v95 = 0;
          v32 = *(__int64 **)(v11 + 1736);
          v33 = *v32;
          v95 = 0;
          *(struct _GUID *)&v83[1] = SERIAL_CONTROLLER_DEVICE_ID;
          v34 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *, __int64 *))(v33 + 32))(v32, &v83[1], &v95);
          if ( v34 < 0 )
          {
            if ( v34 != -2147023728 )
            {
              v76 = wil::verify_BOOL<int>((unsigned int)v34);
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x2A4,
                (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmmsvirtualmachine\\vmmsvirtualmachineorchestrator.cpp",
                (const char *)v76,
                v78);
            }
            v35 = *(_QWORD *)(v11 + 1736);
            v36 = *(__int64 (__fastcall **)(__int64, _OWORD *, _QWORD *, __int64 *))(*(_QWORD *)v35 + 24LL);
            v37 = v95;
            v95 = 0;
            if ( v37 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
            *(struct _GUID *)&v83[1] = SERIAL_CONTROLLER_DEVICE_ID;
            v87[0] = SERIAL_CONTROLLER_DEVICE_ID;
            v38 = v36(v35, v87, &v83[1], &v95);
            if ( v38 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x2A0,
                (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmmsvirtualmachine\\vmmsvirtualmachineorchestrator.cpp",
                (const char *)(unsigned int)v38,
                v78);
          }
          ComputeService::VmCommonHelpers::CreateSerialNamedPipe(
            (unsigned int)&v96,
            (unsigned int)(&v123 + 3 * i),
            *(_DWORD *)&v125[48 * i + 4],
            (unsigned int)&v115,
            i,
            v95);
          if ( (_BYTE)v96 )
          {
            v39 = Vml::FormatString(&v90, L"COM%d", (unsigned int)i + 1);
            std::wstring::operator=(&v131[v30], v39);
            Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)&v90);
            *(_DWORD *)&v131[48 * i + 36] = *(_DWORD *)&v125[48 * i + 4];
            v131[48 * i + 40] = BYTE1(v96);
          }
          HvsComPtr<IXmlReader>::~HvsComPtr<IXmlReader>(&v95);
        }
      }
      Marshal::ToDeviceRepositoryXml<Config::Devices::Serial::SerialController &>(v81, v31, v130);
      v40 = HyperVRepository::Commit(v81);
      if ( v40 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2B9,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmmsvirtualmachine\\vmmsvirtualmachineorchestrator.cpp",
          (const char *)(unsigned int)v40,
          v78);
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v82);
      `eh vector destructor iterator'(
        v131,
        0x30u,
        4u,
        (void (*)(void *))Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump);
      v9 = v84[0];
      v5 = (ComputeService::Management::OrchestratorCallContext *)v85;
    }
    std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(v101);
    `eh vector destructor iterator'(
      &v123,
      0x30u,
      4u,
      (void (*)(void *))Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump);
  }
  v41 = (HyperVRepository *)*v135;
  v82[0] = (HyperVRepository *)*v135;
  while ( !*((_BYTE *)v41 + 25) )
  {
    std::pair<unsigned __int64 const,Config::Devices::Manifest::DeviceEntry>::pair<unsigned __int64 const,Config::Devices::Manifest::DeviceEntry>(
      &v122,
      (char *)v41 + 32);
    if ( !memcmp_0(&v123, &FLEXIO_DEVICE_ID, 0x10u) )
    {
      v42 = v124;
      *(_OWORD *)&v83[1] = v124;
      v84[0] = 0;
      std::_Tree<std::_Tmap_traits<_GUID,Marshal::DelayedBase<Config::Devices::Device,Marshal::Details::DelayedXmlTraits>,Marshal::GuidLess,std::allocator<std::pair<_GUID const,Marshal::DelayedBase<Config::Devices::Device,Marshal::Details::DelayedXmlTraits>>>,0>>::find(
        v137,
        v84,
        &v83[1]);
      v105 = 0;
      v106 = 0;
      v107 = 0;
      v108 = 0;
      v109 = 0;
      v110 = 0;
      v111 = 0;
      v112 = 0;
      v113 = 0;
      v114 = 0;
      Marshal::DelayedBase<Config::Devices::Device,Marshal::Details::DelayedXmlTraits>::Unmarshal<Config::Devices::Vpci::FlexIoDevice>(
        v84[0] + 48,
        v100,
        &v105);
      if ( v100[0] && !memcmp_0(&v106, &VIRTIO_SERIAL_DEVICE_ID, 0x10u) )
      {
        if ( !(((__int64)v108 - v107) >> 5) )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2C9,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmmsvirtualmachine\\vmmsvirtualmachineorchestrator.cpp",
            (const char *)0x80070057LL,
            v78);
        v95 = 0;
        v43 = *(__int64 **)(v11 + 1736);
        v44 = *v43;
        v95 = 0;
        v87[0] = v42;
        v45 = (*(__int64 (__fastcall **)(__int64 *, _OWORD *, __int64 *))(v44 + 32))(v43, v87, &v95);
        if ( v45 < 0 )
        {
          if ( v45 != -2147023728 )
          {
            v77 = wil::verify_BOOL<int>((unsigned int)v45);
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x2DD,
              (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmmsvirtualmachine\\vmmsvirtualmachineorchestrator.cpp",
              (const char *)v77,
              v78);
          }
          v46 = *(_QWORD *)(v11 + 1736);
          v47 = *(__int64 (__fastcall **)(__int64, __int128 *, _OWORD *, __int64 *))(*(_QWORD *)v46 + 24LL);
          v48 = v95;
          v95 = 0;
          if ( v48 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
          v87[0] = FLEXIO_DEVICE_ID;
          v85 = v42;
          v49 = v47(v46, &v85, v87, &v95);
          if ( v49 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x2D9,
              (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmmsvirtualmachine\\vmmsvirtualmachineorchestrator.cpp",
              (const char *)(unsigned int)v49,
              v78);
        }
        v50 = 0;
        v51 = v107;
        v52 = v108;
        while ( v51 != v52 )
        {
          std::wstring::wstring(v116);
          std::wstring::wstring(v117);
          v118 = 0;
          v119 = 0;
          v120 = 0;
          v121 = 0;
          v87[0] = *(_OWORD *)std::wstring::operator std::basic_string_view<unsigned short>(v51, &v90);
          ComputeService::MarshalUtilities::FromJsonThrow<Schema::VirtualMachines::Resources::VirtioSerialPort>(
            v87,
            v116);
          v102 = 0;
          std::wstring::wstring(v103);
          v104 = 0;
          if ( (unsigned __int8)ComputeService::VmCommonHelpers::IsSerialPortNamedPipe(v116) )
          {
            ComputeService::VmCommonHelpers::CreateSerialNamedPipe(
              (unsigned int)&v96,
              (unsigned int)v116,
              0x2000,
              (unsigned int)&v115,
              v50,
              v95);
            if ( (_BYTE)v96 )
            {
              LODWORD(v104) = 0x2000;
              BYTE4(v104) = BYTE1(v96);
            }
          }
          LODWORD(v102) = v50;
          std::wstring::operator=(v103, v117);
          BYTE5(v104) = v118;
          v57 = Marshal::ToJson<Config::Devices::VirtioSerial::VirtioSerialPort &,>(v87, &v102);
          v58 = 32LL * v50++ + v107;
          std::wstring::operator=(v58, v57);
          Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v87);
          Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v103);
          std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>((Schema::Responses::System::CrashReportProcessDump *)v116);
          v51 += 32;
        }
        *(_OWORD *)v84 = 0;
        VmRepositoryAutoLock::VmRepositoryAutoLock(v84, v81, 1);
        if ( SLODWORD(v84[1]) < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x304,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmmsvirtualmachine\\vmmsvirtualmachineorchestrator.cpp",
            (const char *)LODWORD(v84[1]),
            v78);
        *(_QWORD *)&v85 = v81;
        PathForVirtualDevice = (_QWORD *)Marshal::Details::GetPathForVirtualDevice(v87, &v83[1]);
        if ( PathForVirtualDevice[3] > 7u )
          PathForVirtualDevice = (_QWORD *)*PathForVirtualDevice;
        Marshal::ToRepositoryXml<VmRepository * &,Config::Devices::Vpci::FlexIoDevice &,>(
          &v85,
          PathForVirtualDevice,
          &v105);
        Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v87);
        v60 = HyperVRepository::Commit(v81);
        if ( v60 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x306,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmmsvirtualmachine\\vmmsvirtualmachineorchestrator.cpp",
            (const char *)(unsigned int)v60,
            v78);
        VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v84);
        HvsComPtr<IXmlReader>::~HvsComPtr<IXmlReader>(&v95);
      }
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(v101);
      std::vector<std::wstring>::_Tidy(&v107);
    }
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v125);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Schema::VirtualMachines::Resources::Vpci::VirtualPciDevice>>>,std::_Iterator_base0>::operator++(v82);
    v41 = v82[0];
  }
  v138[0] = CRASHDUMP_DEVICE_VTL2_INSTANCE_ID;
  v138[1] = CRASHDUMP_DEVICE_ID;
  v61 = (__int64 *)v138;
  do
  {
    v82[0] = 0;
    std::_Tree<std::_Tmap_traits<_GUID,Marshal::DelayedBase<Config::Devices::Device,Marshal::Details::DelayedXmlTraits>,Marshal::GuidLess,std::allocator<std::pair<_GUID const,Marshal::DelayedBase<Config::Devices::Device,Marshal::Details::DelayedXmlTraits>>>,0>>::find(
      v137,
      v82,
      v61);
    v64 = v82[0];
    if ( v82[0] != (HyperVRepository *)v137[0] )
    {
      Config::Devices::CrashDump::CrashDumpDevice::CrashDumpDevice((Config::Devices::CrashDump::CrashDumpDevice *)&v122);
      Marshal::DelayedBase<Config::Devices::Device,Marshal::Details::DelayedXmlTraits>::Unmarshal<Config::Devices::CrashDump::CrashDumpDevice>(
        (char *)v64 + 48,
        v100,
        &v122);
      if ( v100[0] )
      {
        if ( v125[16] )
          std::wstring::operator=(v11 + 984, &v123);
        if ( v126[48] )
          std::wstring::operator=(v11 + 984, v126);
      }
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(v101);
      Schema::VirtualMachines::Resources::GuestCrashReporting::~GuestCrashReporting((Schema::VirtualMachines::Resources::GuestCrashReporting *)&v123);
    }
    v61 += 2;
  }
  while ( v61 != &v139 );
  *(_QWORD *)v99 = 0;
  v65 = v86[1];
  v66 = v86[0];
  LOBYTE(v63) = *(_BYTE *)(v11 + 2040);
  NumaSpanningSetting = ComputeService::Management::VirtualMachineUtils::GetNumaSpanningSetting(v63, v62);
  v68 = (unsigned __int16 *)(v9 + 80);
  if ( *((_QWORD *)v9 + 13) > 7u )
    v68 = *(unsigned __int16 **)v68;
  v82[0] = 0;
  ComputeService::Vmwp::CreateWorkerProcessInitializationContext(
    (__int64 *)v99,
    (__int64)v81,
    (struct IUnknown **)v82,
    v11 + 1744,
    *((_DWORD *)v9 + 1088),
    v68,
    NumaSpanningSetting,
    v66,
    v65);
  v69 = v98;
  if ( (unsigned __int64)(v98 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v95 = 0;
    v96 = 5;
    LODWORD(v80) = 8;
    v79 = wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v95);
    if ( (unsigned int)VidQueryResourcePartitionComponent(v69, 1, &v96) )
    {
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
        v11 + 816,
        &v95);
    }
    else
    {
      LastError = GetLastError();
      if ( LastError != 1168 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x347,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmmsvirtualmachine\\vmmsvirtualmachineorchestrator.cpp",
          (const char *)LastError,
          v79);
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v95);
  }
  if ( v97 )
  {
    v95 = 0;
    std::wstring::wstring(&v90, L"hcs:/VirtualMachine/WorkerJob");
    v71 = &v90;
    if ( v92 > 7 )
      v71 = v90;
    anonymous_namespace_::GetHandleHelper_nothrow_wil::unique_any_t_wil::details::unique_storage_wil::details::handle_null_resource_policy_int____cdecl___void_____CloseHandle______IVmHandleBroker_(
      v84,
      v97,
      v71);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &v95,
      v84);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v84);
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)&v90);
    if ( (unsigned __int64)(*(_QWORD *)(v11 + 816) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL
      && (unsigned __int64)(v95 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v75 = wil::verify_BOOL<int>(2147944010LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x356,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmmsvirtualmachine\\vmmsvirtualmachineorchestrator.cpp",
        (const char *)v75,
        (int)"Job object provided by both resource partition and handle broker",
        v80);
    }
    if ( (unsigned __int64)(v95 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
        v11 + 816,
        &v95);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v95);
  }
  v72 = Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(
          &v85,
          &v81);
  ComputeService::Management::VmmsDetails::StartWorkerProcess(
    (_DWORD)v93,
    v99[0],
    (_DWORD)v9,
    v11,
    *(_QWORD *)(v11 + 1736),
    v72);
  ComputeService::Management::VmmsDetails::StoreRecoveryData((ComputeService::Management::VmmsDetails *)v9, v73);
  BYTE1(v89) = 0;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v132,
    0);
  Vml::VmComPtr<IVmSimpleTaskEvents>::~VmComPtr<IVmSimpleTaskEvents>(v99);
  std::pair<Vml::VmComPtr<IMemoryBalancer>,Vml::VmComPtr<IVmSimpleTask>>::~pair<Vml::VmComPtr<IMemoryBalancer>,Vml::VmComPtr<IVmSimpleTask>>(v86);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v98);
  HvsComPtr<IXmlReader>::~HvsComPtr<IXmlReader>(&v97);
  Config::VmWorkerProcess::Configuration::~Configuration((Config::VmWorkerProcess::Configuration *)v133);
  Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(&v81);
  wil::details::ScopeExitFnGuard__lambda_ecc385351a6df5df3c5d149b6b8395a2___::operator()(v88);
  ComputeService::Diagnostics::TraceProvider::VirtualMachine_Construct::~VirtualMachine_Construct((ComputeService::Diagnostics::TraceProvider::VirtualMachine_Construct *)v132);
  ComputeService::Management::OrchestratorCallContext::~OrchestratorCallContext(v5);
  return 1;
}

```

## disassembly

```asm
0x1401de020  mov     rax, rsp
0x1401de023  mov     [rax+8], rbx
0x1401de027  push    rbp
0x1401de028  push    rsi
0x1401de029  push    rdi
0x1401de02a  push    r12
0x1401de02c  push    r13
0x1401de02e  push    r14
0x1401de030  push    r15
0x1401de032  lea     rbp, [rax-0E68h]
0x1401de039  sub     rsp, 0F30h
0x1401de040  movaps  xmmword ptr [rax-48h], xmm6
0x1401de044  mov     rax, cs:__security_cookie
0x1401de04b  xor     rax, rsp
0x1401de04e  mov     [rbp+0E60h+var_50], rax
0x1401de055  mov     rsi, r9
0x1401de058  mov     r12, r8
0x1401de05b  mov     qword ptr [rbp+0E60h+var_ED0], r8
0x1401de05f  mov     r14, rdx
0x1401de062  mov     [rbp+0E60h+var_E58], rdx
0x1401de066  mov     rbx, rcx
0x1401de069  mov     [rbp+0E60h+var_E50], r8
0x1401de06d  xor     r13d, r13d
0x1401de070  mov     rax, [rdx]
0x1401de073  mov     rdx, [rax]
0x1401de076  add     rdx, 8
0x1401de07a  lea     rcx, [rbp+0E60h+var_EB0]
0x1401de07e  call    ?GetComputeSystemGuid@Management@ComputeService@@YA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ComputeService::Management::GetComputeSystemGuid(std::wstring const &)
0x1401de083  movups  xmm0, xmmword ptr [rax]
0x1401de086  movdqu  [rbp+0E60h+var_D80], xmm0
0x1401de08e  xor     edx, edx; Val
0x1401de090  mov     r8d, 150h; Size
0x1401de096  lea     rcx, [rbp+0E60h+var_B80]; void *
0x1401de09d  call    memset_0
0x1401de0a2  mov     rax, [r14]
0x1401de0a5  mov     rcx, [rax]
0x1401de0a8  add     rcx, 8
0x1401de0ac  cmp     qword ptr [rcx+18h], 7
0x1401de0b1  jbe     short loc_1401DE0B6
0x1401de0b3  mov     rcx, [rcx]
0x1401de0b6  mov     [rsp+0F60h+var_F10+8], rcx
0x1401de0bb  lea     rdx, [rsp+0F60h+var_F10+8]
0x1401de0c0  lea     rcx, [rbp+0E60h+var_B80]
0x1401de0c7  call    ??$Start@PEBG@VirtualMachine_Construct@TraceProvider@Diagnostics@ComputeService@@SA?AV0123@$$QEAPEBG@Z; ComputeService::Diagnostics::TraceProvider::VirtualMachine_Construct::Start<ushort const *>(ushort const * &&)
0x1401de0cc  nop
0x1401de0cd  mov     rcx, [r14]
0x1401de0d0  mov     dword ptr [rsp+0F60h+var_F40], r13d; int
0x1401de0d5  lea     r9, ??_R0?AUVirtualMachineConfiguration@Management@ComputeService@@@8; ComputeService::Management::VirtualMachineConfiguration `RTTI Type Descriptor'
0x1401de0dc  lea     r8, ??_R0?AUComputeSystemConfiguration@Management@ComputeService@@@8; ComputeService::Management::ComputeSystemConfiguration `RTTI Type Descriptor'
0x1401de0e3  xor     edx, edx
0x1401de0e5  mov     rcx, [rcx]
0x1401de0e8  call    __RTDynamicCast_0
0x1401de0ed  mov     r15, rax
0x1401de0f0  mov     [rbp+0E60h+var_EE0], rax
0x1401de0f4  mov     rcx, [rbp+0E68h]; this
0x1401de0fb  test    rax, rax
0x1401de0fe  jz      loc_1401DEEE3
0x1401de104  mov     rcx, [r14]
0x1401de107  mov     dword ptr [rsp+0F60h+var_F40], r13d; int
0x1401de10c  lea     r9, ??_R0?AUVirtualMachineState@Management@ComputeService@@@8; ComputeService::Management::VirtualMachineState `RTTI Type Descriptor'
0x1401de113  lea     r8, ??_R0?AUComputeSystemState@Management@ComputeService@@@8; ComputeService::Management::ComputeSystemState `RTTI Type Descriptor'
0x1401de11a  xor     edx, edx
0x1401de11c  mov     rcx, [rcx+8]
0x1401de120  call    __RTDynamicCast_0
0x1401de125  mov     rdi, rax
0x1401de128  mov     rcx, [rbp+0E68h]; this
0x1401de12f  test    rax, rax
0x1401de132  jz      loc_1401DEEFB
0x1401de138  cmp     [rbx+18h], r13b
0x1401de13c  jz      short loc_1401DE157
0x1401de13e  mov     rax, [r14]
0x1401de141  mov     rcx, [rax]
0x1401de144  add     rcx, 8
0x1401de148  cmp     qword ptr [rcx+18h], 7
0x1401de14d  jbe     short loc_1401DE152
0x1401de14f  mov     rcx, [rcx]; this
0x1401de152  call    ?VerifyHyperVInstalled@VmCommonHelpers@ComputeService@@YAXPEBG@Z; ComputeService::VmCommonHelpers::VerifyHyperVInstalled(ushort const *)
0x1401de157  mov     al, [rbx+18h]
0x1401de15a  mov     [rdi+6C0h], al
0x1401de160  xorps   xmm0, xmm0
0x1401de163  xor     eax, eax
0x1401de165  movups  [rbp+0E60h+var_E90], xmm0
0x1401de169  mov     [rbp+0E60h+var_E80], rax
0x1401de16d  mov     qword ptr [rbp+0E60h+var_E90], rbx
0x1401de171  mov     qword ptr [rbp+0E60h+var_E90+8], r14
0x1401de175  mov     word ptr [rbp+0E60h+var_E80], 101h
0x1401de17b  mov     rax, [r14]
0x1401de17e  mov     rcx, [rax]
0x1401de181  mov     ecx, [rcx+28h]
0x1401de184  call    ?IncrementDensityCounters@Telemetry@ComputeService@@YAXW4ComputeSystemType@Management@2@@Z; ComputeService::Telemetry::IncrementDensityCounters(ComputeService::Management::ComputeSystemType)
0x1401de189  mov     rax, [r14]
0x1401de18c  mov     rcx, [rax]
0x1401de18f  mov     edx, [rcx+28h]
0x1401de192  add     rcx, 8
0x1401de196  cmp     qword ptr [rcx+18h], 7
0x1401de19b  jbe     short loc_1401DE1A0
0x1401de19d  mov     rcx, [rcx]
0x1401de1a0  call    ?RecordSystem@RecoveryStore@ComputeService@@YAXPEBGW4ComputeSystemType@Management@2@@Z; ComputeService::RecoveryStore::RecordSystem(ushort const *,ComputeService::Management::ComputeSystemType)
0x1401de1a5  mov     [rsp+0F60h+var_F10], r13
0x1401de1aa  lea     rdx, [rbp+0E60h+var_D80]
0x1401de1b1  lea     rcx, [rsp+0F60h+var_F10]
0x1401de1b6  call    ?CreateRepository@Vmwp@ComputeService@@YA?AV?$VmReferencePtr@VHyperVRepository@@VVmUserReferenceTraits@Vml@@@Vml@@AEBU_GUID@@@Z; ComputeService::Vmwp::CreateRepository(_GUID const &)
0x1401de1bb  nop
0x1401de1bc  lea     rdx, [rdi+0A30h]
0x1401de1c3  cmp     [rdx+10h], r13
0x1401de1c7  jz      short loc_1401DE1D3
0x1401de1c9  lea     rcx, [rsp+0F60h+var_F10]
0x1401de1ce  call    ?LoadRepositoryContents@VmmsConfigHelpers@Management@ComputeService@@YAXAEAV?$VmReferencePtr@VHyperVRepository@@VVmUserReferenceTraits@Vml@@@Vml@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ComputeService::Management::VmmsConfigHelpers::LoadRepositoryContents(Vml::VmReferencePtr<HyperVRepository,Vml::VmUserReferenceTraits> &,std::wstring const &)
0x1401de1d3  lea     rcx, [rbp+0E60h+var_A30]; this
0x1401de1da  call    ??0Configuration@VmWorkerProcess@Config@@QEAA@XZ; Config::VmWorkerProcess::Configuration::Configuration(void)
0x1401de1df  nop
0x1401de1e0  lea     r8, [rbp+0E60h+var_A30]
0x1401de1e7  lea     rdx, [rsp+0F60h+var_F10]
0x1401de1ec  lea     rcx, [rbp+0E60h+var_E20]
0x1401de1f0  call    ??$FromRepositoryXml@AEAV?$VmReferencePtr@VHyperVRepository@@VVmUserReferenceTraits@Vml@@@Vml@@UConfiguration@VmWorkerProcess@Config@@$$V@Marshal@@YA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@AEAV?$VmReferencePtr@VHyperVRepository@@VVmUserReferenceTraits@Vml@@@Vml@@PEAUConfiguration@VmWorkerProcess@Config@@W4UnmarshalFlags@0@@Z; Marshal::FromRepositoryXml<Vml::VmReferencePtr<HyperVRepository,Vml::VmUserReferenceTraits> &,Config::VmWorkerProcess::Configuration,>(Vml::VmReferencePtr<HyperVRepository,Vml::VmUserReferenceTraits> &,Config::VmWorkerProcess::Configuration *,Marshal::UnmarshalFlags)
0x1401de1f5  nop
0x1401de1f6  mov     rcx, [rbp+0E68h]; this
0x1401de1fd  cmp     [rax], r13b
0x1401de200  jz      loc_1401DEF13
0x1401de206  lea     rcx, [rbp+0E60h+var_E18]
0x1401de20a  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x1401de20f  lea     rcx, [rdi+0A60h]
0x1401de216  lea     rdx, [rbp+0E60h+var_A8]
0x1401de21d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1401de222  test    rsi, rsi
0x1401de225  jz      loc_1401DE8A3
0x1401de22b  mov     rdx, [rdi+6C8h]; struct IVmHandleBrokerManager *
0x1401de232  mov     rcx, rsi; this
0x1401de235  call    ?DuplicateManager@VmHandleBrokerUtils@@YAXPEAUIVmHandleBrokerManager@@0@Z; VmHandleBrokerUtils::DuplicateManager(IVmHandleBrokerManager *,IVmHandleBrokerManager *)
0x1401de23a  mov     [rbp+0E60h+var_E38], r13
0x1401de23e  mov     rcx, [rdi+6C8h]
0x1401de245  mov     rax, [rcx]
0x1401de248  mov     [rbp+0E60h+var_E38], r13
0x1401de24c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1401de253  movdqu  xmmword ptr [rsp+0F60h+var_EF8+8], xmm0
0x1401de259  lea     r8, [rbp+0E60h+var_E38]
0x1401de25d  lea     rdx, [rsp+0F60h+var_EF8+8]
0x1401de262  mov     rax, [rax+20h]
0x1401de266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401de26b  or      r14, 0FFFFFFFFFFFFFFFFh
0x1401de26f  mov     [rbp+0E60h+var_E30], r14
0x1401de273  lea     r8d, [r14+11h]; Size
0x1401de277  lea     rdx, GUID_NULL; Buf2
0x1401de27e  lea     rcx, [rbp+0E60h+Buf1]; Buf1
0x1401de285  call    memcmp_0
0x1401de28a  test    eax, eax
0x1401de28c  jz      loc_1401DE348
0x1401de292  lea     rcx, [rbp+0E60h+Buf1]
0x1401de299  call    cs:__imp_VidOpenResourcePartition
0x1401de2a0  nop     dword ptr [rax+rax+00h]
0x1401de2a5  mov     rdx, rax
0x1401de2a8  lea     rcx, [rbp+0E60h+var_E30]
0x1401de2ac  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1401de2b1  mov     r14, [rbp+0E60h+var_E30]
0x1401de2b5  lea     rax, [r14-1]
0x1401de2b9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1401de2bd  setnbe  al
0x1401de2c0  mov     rcx, [rbp+0E68h]; this
0x1401de2c7  test    al, al
0x1401de2c9  jnz     loc_1401DEF2B
0x1401de2cf  cmp     [rbp+0E60h+var_E38], r13
0x1401de2d3  jnz     short loc_1401DE31A
0x1401de2d5  mov     rcx, [rdi+6C8h]
0x1401de2dc  mov     rax, [rcx]
0x1401de2df  mov     [rbp+0E60h+var_E38], r13
0x1401de2e3  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1401de2ea  movdqu  xmmword ptr [rsp+0F60h+var_EF8+8], xmm0
0x1401de2f0  movdqu  xmmword ptr [rbp+0E60h+var_EC0], xmm0
0x1401de2f5  lea     r9, [rbp+0E60h+var_E38]
0x1401de2f9  lea     r8, [rsp+0F60h+var_EF8+8]
0x1401de2fe  lea     rdx, [rbp+0E60h+var_EC0]
0x1401de302  mov     rax, [rax+18h]
0x1401de306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401de30b  mov     rcx, [rbp+0E68h]; this
0x1401de312  test    eax, eax
0x1401de314  js      loc_1401DEF52
0x1401de31a  lea     rdx, aHcsVirtualmach; "hcs:/VirtualMachine/ResourcePartition"
0x1401de321  lea     rcx, [rbp+0E60h+var_E20]
0x1401de325  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1401de32a  nop
0x1401de32b  mov     r9, r14
0x1401de32e  xor     r8d, r8d
0x1401de331  lea     rdx, [rbp+0E60h+var_E20]
0x1401de335  mov     rcx, [rbp+0E60h+var_E38]
0x1401de339  call    ?PutHandle@VmHandleBrokerUtils@@YAXPEAUIVmHandleBroker@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4__MIDL___MIDL_itf_ivmhandlebrokeritfs_0000_0000_0001@@PEAX@Z; VmHandleBrokerUtils::PutHandle(IVmHandleBroker *,std::wstring const &,__MIDL___MIDL_itf_ivmhandlebrokeritfs_0000_0000_0001,void *)
0x1401de33e  nop
0x1401de33f  lea     rcx, [rbp+0E60h+var_E20]; this
0x1401de343  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1401de348  lea     rdx, [rsp+0F60h+var_F10]
0x1401de34d  lea     rcx, [rsp+0F60h+var_F10+8]
0x1401de352  call    ??$?0VSavedStateRepository@@@?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@QEAA@AEBV?$VmReferencePtr@VSavedStateRepository@@VVmUserReferenceTraits@Vml@@@1@@Z; Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(Vml::VmReferencePtr<SavedStateRepository,Vml::VmUserReferenceTraits> const &)
0x1401de357  lea     r9, [rdi+6D0h]
0x1401de35e  mov     [rsp+0F60h+var_F40], r14
0x1401de363  mov     r8, rax
0x1401de366  mov     rdx, rdi
0x1401de369  mov     rcx, r15
0x1401de36c  call    ?AllocateResources@VirtualMachineUtils@Management@ComputeService@@YAXPEBUVirtualMachineConfiguration@23@PEAUVirtualMachineState@23@V?$VmReferencePtr@VHyperVRepository@@VVmUserReferenceTraits@Vml@@@Vml@@AEAUInitContext@VirtualMachine@Config@@PEAX@Z; ComputeService::Management::VirtualMachineUtils::AllocateResources(ComputeService::Management::VirtualMachineConfiguration const *,ComputeService::Management::VirtualMachineState *,Vml::VmReferencePtr<HyperVRepository,Vml::VmUserReferenceTraits>,Config::VirtualMachine::InitContext &,void *)
0x1401de371  xorps   xmm0, xmm0
0x1401de374  movdqu  xmmword ptr [rbp+0E60h+var_EC0], xmm0
0x1401de379  lea     rdx, [rdi+2F0h]
0x1401de380  lea     rcx, [rsp+0F60h+var_EF8+8]
0x1401de385  call    ?GetMemoryBalancerInformation@VmCommonHelpers@ComputeService@@YA?AU?$pair@V?$VmComPtr@UIMemoryBalancer@@@Vml@@V?$VmComPtr@UIVmSimpleTask@@@2@@std@@AEBUResourceState@Resource@2@@Z; ComputeService::VmCommonHelpers::GetMemoryBalancerInformation(ComputeService::Resource::ResourceState const &)
0x1401de38a  mov     rdx, rax
0x1401de38d  lea     rcx, [rbp+0E60h+var_EC0]
0x1401de391  call    ??$?4U?$pair@V?$VmComPtr@UIMemoryBalancer@@@Vml@@V?$VmComPtr@UIVmSimpleTask@@@2@@std@@$0A@@?$pair@V?$VmComPtr@UIMemoryBalancer@@@Vml@@V?$VmComPtr@UIVmSimpleTask@@@2@@std@@QEAAAEAU01@$$QEAU01@@Z; std::pair<Vml::VmComPtr<IMemoryBalancer>,Vml::VmComPtr<IVmSimpleTask>>::operator=<std::pair<Vml::VmComPtr<IMemoryBalancer>,Vml::VmComPtr<IVmSimpleTask>>,0>(std::pair<Vml::VmComPtr<IMemoryBalancer>,Vml::VmComPtr<IVmSimpleTask>> &&)
0x1401de396  lea     rcx, [rsp+0F60h+var_EF8+8]; void *
0x1401de39b  call    ??1?$pair@V?$VmComPtr@UIMemoryBalancer@@@Vml@@V?$VmComPtr@UIVmSimpleTask@@@2@@std@@QEAA@XZ; std::pair<Vml::VmComPtr<IMemoryBalancer>,Vml::VmComPtr<IVmSimpleTask>>::~pair<Vml::VmComPtr<IMemoryBalancer>,Vml::VmComPtr<IVmSimpleTask>>(void)
0x1401de3a0  mov     [rbp+0E60h+var_E48], r13
0x1401de3a4  lea     r8, SERIAL_CONTROLLER_DEVICE_ID
0x1401de3ab  lea     rdx, [rbp+0E60h+var_E48]
0x1401de3af  lea     rcx, [rbp+0E60h+var_88]
0x1401de3b6  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$DelayedBase@UDevice@Devices@Config@@UDelayedXmlTraits@Details@Marshal@@@Marshal@@UGuidLess@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$DelayedBase@UDevice@Devices@Config@@UDelayedXmlTraits@Details@Marshal@@@Marshal@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$DelayedBase@UDevice@Devices@Config@@UDelayedXmlTraits@Details@Marshal@@@Marshal@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,Marshal::DelayedBase<Config::Devices::Device,Marshal::Details::DelayedXmlTraits>,Marshal::GuidLess,std::allocator<std::pair<_GUID const,Marshal::DelayedBase<Config::Devices::Device,Marshal::Details::DelayedXmlTraits>>>,0>>::find(_GUID const &)
0x1401de3bb  mov     r14d, 4
0x1401de3c1  mov     rbx, [rbp+0E60h+var_E48]
0x1401de3c5  cmp     rbx, [rbp+0E60h+var_88]
0x1401de3cc  jz      loc_1401DE6C9
0x1401de3d2  mov     [rbp+0E60h+var_D20], r13
0x1401de3d9  xor     edx, edx; Val
0x1401de3db  mov     r8d, 0C0h; Size
0x1401de3e1  lea     rcx, [rbp+0E60h+var_D18]; void *
0x1401de3e8  call    memset_0
0x1401de3ed  lea     rax, ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1401de3f4  mov     [rsp+0F60h+var_F40], rax; int
0x1401de3f9  lea     r9, ??0Port@Serial@Devices@Config@@QEAA@XZ; void (*)(void *)
0x1401de400  mov     r8d, r14d; unsigned __int64
0x1401de403  lea     edx, [r14+2Ch]; unsigned __int64
0x1401de407  lea     rcx, [rbp+0E60h+var_D18]; void *
0x1401de40e  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1401de413  mov     [rbp+0E60h+var_C58], r13w
0x1401de41b  xor     eax, eax
0x1401de41d  mov     [rbp+0E60h+var_C56], eax
0x1401de423  mov     [rbp+0E60h+var_C52], ax
0x1401de42a  lea     rcx, [rbx+30h]
0x1401de42e  lea     r8, [rbp+0E60h+var_D20]
0x1401de435  lea     rdx, [rbp+0E60h+var_E20]
0x1401de439  call    ??$Unmarshal@USerialController@Serial@Devices@Config@@@?$DelayedBase@UDevice@Devices@Config@@UDelayedXmlTraits@Details@Marshal@@@Marshal@@QEBA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@PEAUSerialController@Serial@Devices@Config@@@Z; Marshal::DelayedBase<Config::Devices::Device,Marshal::Details::DelayedXmlTraits>::Unmarshal<Config::Devices::Serial::SerialController>(Config::Devices::Serial::SerialController *)
0x1401de43e  nop
0x1401de43f  cmp     [rbp+0E60h+var_E20], r13b
0x1401de443  jz      loc_1401DE6A3
0x1401de449  lea     rcx, [rbp+0E60h+var_C50]; this
0x1401de450  call    ??0SerialController@Serial@Devices@Config@@QEAA@XZ; Config::Devices::Serial::SerialController::SerialController(void)
0x1401de455  nop
0x1401de456  xorps   xmm0, xmm0
0x1401de459  movups  xmmword ptr [rsp+0F60h+var_F10+8], xmm0
0x1401de45e  lea     r8d, [r14-3]
0x1401de462  mov     rdx, [rsp+0F60h+var_F10]
0x1401de467  lea     rcx, [rsp+0F60h+var_F10+8]
0x1401de46c  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x1401de471  nop
0x1401de472  mov     r9d, dword ptr [rsp+0F60h+var_F00]; char *
0x1401de477  mov     rcx, [rbp+0E68h]; this
0x1401de47e  test    r9d, r9d
0x1401de481  js      loc_1401DEF67
0x1401de487  lea     r9, [rbp+0E60h+var_C50]
0x1401de48e  mov     rdx, [rsp+0F60h+var_F10]
0x1401de493  lea     rcx, [rbp+0E60h+var_E78]
0x1401de497  call    ??$FromDeviceRepositoryXml@USerialController@Serial@Devices@Config@@@Marshal@@YA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@PEAVVmRepository@@AEBU_GUID@@PEAUSerialController@Serial@Devices@Config@@@Z; Marshal::FromDeviceRepositoryXml<Config::Devices::Serial::SerialController>(VmRepository *,_GUID const &,Config::Devices::Serial::SerialController *)
0x1401de49c  nop
0x1401de49d  mov     rcx, [rbp+0E68h]; this
0x1401de4a4  cmp     [rax], r13b
0x1401de4a7  jz      loc_1401DEF79
0x1401de4ad  lea     rcx, [rbp+0E60h+var_E70]
0x1401de4b1  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x1401de4b6  mov     sil, r13b
0x1401de4b9  movzx   eax, sil
0x1401de4bd  lea     rbx, [rax+rax*2]
0x1401de4c1  shl     rbx, 4
0x1401de4c5  lea     r13, [rbp+0E60h+var_C48]
0x1401de4cc  add     r13, rbx
0x1401de4cf  lea     rdx, szPassword
0x1401de4d6  mov     rcx, r13
0x1401de4d9  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1401de4de  lea     r12, [rbp+0E60h+var_D18]
0x1401de4e5  add     r12, rbx
0x1401de4e8  mov     rcx, r12
0x1401de4eb  call    ?IsSerialPortNamedPipe@VmCommonHelpers@ComputeService@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ComputeService::VmCommonHelpers::IsSerialPortNamedPipe(std::wstring const &)
0x1401de4f0  test    al, al
0x1401de4f2  jz      loc_1401DE63C
0x1401de4f8  cmp     [rbp+rbx+0E60h+var_CF4], 0
0x1401de500  jnz     short loc_1401DE50D
0x1401de502  mov     [rbp+rbx+0E60h+var_CF4], 2000h
0x1401de50d  mov     [rbp+0E60h+var_E48], 0
0x1401de515  mov     rcx, [rdi+6C8h]
0x1401de51c  mov     rax, [rcx]
0x1401de51f  mov     [rbp+0E60h+var_E48], 0
0x1401de527  movups  xmm0, xmmword ptr cs:SERIAL_CONTROLLER_DEVICE_ID.Data1
0x1401de52e  movdqu  xmmword ptr [rsp+0F60h+var_EF8+8], xmm0
0x1401de534  lea     r8, [rbp+0E60h+var_E48]
0x1401de538  lea     rdx, [rsp+0F60h+var_EF8+8]
0x1401de53d  mov     rax, [rax+20h]
0x1401de541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401de546  test    eax, eax
0x1401de548  jns     short loc_1401DE5BA
0x1401de54a  cmp     eax, 80070490h
0x1401de54f  jnz     loc_1401DEFBB
0x1401de555  mov     r14, [rdi+6C8h]
0x1401de55c  mov     rax, [r14]
0x1401de55f  mov     r15, [rax+18h]
0x1401de563  mov     rcx, [rbp+0E60h+var_E48]
0x1401de567  mov     [rbp+0E60h+var_E48], 0
  ... truncated ...
```
