# ComputeService::Management::HyperVContainerOrchestrator::ModifySettings(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::OrchestratorCallContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void *)

- ea: `0x140098ed0`
- end: `0x14009a96f`
- name: `?ModifySettings@HyperVContainerOrchestrator@Management@ComputeService@@UEAA_NAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@UOrchestratorCallContext@23@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@PEAX@Z`
- size: `6815`
- prototype: ``
- caller_count: `0`
- callee_count: `100`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1400142a0`
- `0x140017040`
- `0x14001bc28`
- `0x14001bce0`
- `0x14001d490`
- `0x140021de0`
- `0x140021f9c`
- `0x140021ff4`
- `0x1400231d0`
- `0x140024030`
- `0x1400243f0`
- `0x1400249e4`
- `0x140026f88`
- `0x140029350`
- `0x14002a5e4`
- `0x14002aa44`
- `0x14002ac78`
- `0x14002d7f0`
- `0x14002ecd8`
- `0x14002f868`
- `0x14002fa20`
- `0x140031210`
- `0x1400421f0`
- `0x140044280`
- `0x140044974`
- `0x140048514`
- `0x140068b1c`
- `0x140073a74`
- `0x1400763b0`
- `0x140076488`
- `0x140076734`
- `0x140077dbc`
- `0x140084c44`
- `0x140085610`
- `0x140085654`
- `0x140097e34`
- `0x140097f24`
- `0x140098274`
- `0x14009829c`
- `0x14009838c`
- `0x140098444`
- `0x1400985d4`
- `0x14009867c`
- `0x1400987dc`
- `0x140098810`
- `0x140098b98`
- `0x140098e18`
- `0x140098ed0`
- `0x14009a978`
- `0x14009a9a4`

## string_xrefs

- `0x140099130`: `onecore\vm\compute\management\orchestration\hypervcontainer\hypervcontainerorchestrator.cpp`
- `0x140099152`: `onecore\vm\compute\management\orchestration\hypervcontainer\hypervcontainerorchestrator.cpp`
- `0x14009925d`: `onecore\vm\compute\management\orchestration\hypervcontainer\hypervcontainerorchestrator.cpp`
- `0x1400992e0`: `onecore\vm\compute\management\orchestration\hypervcontainer\hypervcontainerorchestrator.cpp`
- `0x140099390`: `onecore\vm\compute\management\orchestration\hypervcontainer\hypervcontainerorchestrator.cpp`
- `0x1400993e4`: `onecore\vm\compute\management\orchestration\hypervcontainer\hypervcontainerorchestrator.cpp`
- `0x1400994b7`: `onecore\vm\compute\management\orchestration\hypervcontainer\hypervcontainerorchestrator.cpp`
- `0x1400996bd`: `onecore\vm\compute\management\orchestration\hypervcontainer\hypervcontainerorchestrator.cpp`
- `0x14009985f`: `onecore\vm\compute\management\orchestration\hypervcontainer\hypervcontainerorchestrator.cpp`
- `0x1400998c8`: `onecore\vm\compute\management\orchestration\hypervcontainer\hypervcontainerorchestrator.cpp`
- `0x140099a8c`: `onecore\vm\compute\management\orchestration\hypervcontainer\hypervcontainerorchestrator.cpp`
- `0x140099b13`: `onecore\vm\compute\management\orchestration\hypervcontainer\hypervcontainerorchestrator.cpp`
- `0x140099c01`: `onecore\vm\compute\management\orchestration\hypervcontainer\hypervcontainerorchestrator.cpp`
- `0x14009a005`: `onecore\vm\compute\management\orchestration\hypervcontainer\hypervcontainerorchestrator.cpp`
- `0x14009a059`: `onecore\vm\compute\management\orchestration\hypervcontainer\hypervcontainerorchestrator.cpp`
- `0x14009a0dd`: `onecore\vm\compute\management\orchestration\hypervcontainer\hypervcontainerorchestrator.cpp`
- `0x14009a248`: `onecore\vm\compute\management\orchestration\hypervcontainer\hypervcontainerorchestrator.cpp`
- `0x14009a71a`: `onecore\vm\compute\management\orchestration\hypervcontainer\hypervcontainerorchestrator.cpp`
- `0x14009a7c1`: `onecore\vm\compute\management\orchestration\hypervcontainer\hypervcontainerorchestrator.cpp`
- `0x140099b01`: `Unsupported protocol version %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=46
char __fastcall ComputeService::Management::HyperVContainerOrchestrator::ModifySettings(
        __int64 a1,
        _QWORD *a2,
        ComputeService::Management::OrchestratorCallContext *a3,
        __int64 a4)
{
  _QWORD *v7; // rcx
  __int64 active; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rbx
  struct ComputeService::VmCommonHelpers::VirtualGpu::GpuEnvironment *v12; // rdx
  struct ComputeService::VmCommonHelpers::VirtualGpu::GpuEnvironment *v13; // r8
  ComputeService::VmCommonHelpers::VirtualGpu *v14; // rcx
  unsigned int v15; // ebx
  __int64 v16; // rax
  struct Config::Containers::MappedVirtualDisk *v17; // r9
  ComputeService::UtilityVm *v18; // rcx
  ComputeService::UtilityVm *v19; // rcx
  unsigned int v20; // ebx
  __int64 v21; // rax
  __int64 v22; // rax
  _QWORD *v23; // rax
  int v24; // eax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rdi
  void (__fastcall *v28)(__int64, __int64, struct _GUID ***); // rbx
  __int64 v29; // rcx
  unsigned int v30; // ebx
  __int64 v31; // rax
  struct ComputeService::Resource::ResourceState *v32; // r8
  __int64 v33; // rdi
  void (__fastcall *v34)(__int64, __int64, struct _GUID ***); // rbx
  const struct _GUID *v35; // r8
  __int64 v36; // rax
  _QWORD *v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rdi
  void (__fastcall *v41)(__int64, __int64, _BYTE *); // rbx
  const struct Config::Containers::VmHosted::NetworkAdapter *v42; // r8
  __int64 v43; // rdi
  void (__fastcall *v44)(__int64, __int64, _BYTE *); // rbx
  __int64 v45; // rbx
  _QWORD *v46; // rdx
  unsigned int v47; // ebx
  __int64 v48; // rax
  _OWORD *v49; // rax
  __m128i v50; // xmm6
  __int64 v51; // r9
  unsigned __int64 v52; // rbx
  __int64 v53; // rcx
  struct _GUID ***p_Src; // rdx
  __int64 v55; // rax
  __int64 v56; // rdi
  void (__fastcall *v57)(__int64, __int64, _BYTE *); // rbx
  __int64 v58; // rax
  unsigned int v59; // ebx
  struct ComputeService::UtilityVm::Environment *UtilityVmMemorySize; // rbx
  ComputeService::Management::Details *v61; // rdi
  _QWORD *v62; // rax
  const struct ComputeService::Resource::ModifyContext *v63; // r9
  __int64 v64; // rdi
  void (__fastcall *v65)(__int64, __int64, struct _GUID ***); // rbx
  unsigned int v67; // eax
  wil *v68; // rcx
  unsigned int v69; // eax
  _QWORD *v70; // rcx
  int v71; // [rsp+20h] [rbp-5F8h]
  int v72; // [rsp+20h] [rbp-5F8h]
  char *v73; // [rsp+28h] [rbp-5F0h]
  ComputeService::Management::Details *v75; // [rsp+38h] [rbp-5E0h] BYREF
  unsigned __int16 v76[8]; // [rsp+40h] [rbp-5D8h] BYREF
  __int64 v77; // [rsp+50h] [rbp-5C8h]
  char v78; // [rsp+58h] [rbp-5C0h]
  unsigned __int64 v79[3]; // [rsp+60h] [rbp-5B8h] BYREF
  char v80; // [rsp+78h] [rbp-5A0h]
  _QWORD v81[2]; // [rsp+80h] [rbp-598h] BYREF
  struct _GUID **Src; // [rsp+90h] [rbp-588h] BYREF
  ComputeService::Management::Details **v83; // [rsp+98h] [rbp-580h] BYREF
  _QWORD *v84; // [rsp+A0h] [rbp-578h]
  unsigned __int64 v85; // [rsp+A8h] [rbp-570h]
  _BYTE v86[25]; // [rsp+D0h] [rbp-548h] BYREF
  _BYTE v87[32]; // [rsp+F0h] [rbp-528h] BYREF
  char v88; // [rsp+110h] [rbp-508h]
  __int64 v89; // [rsp+120h] [rbp-4F8h] BYREF
  struct _GUID v90; // [rsp+128h] [rbp-4F0h] BYREF
  int v91; // [rsp+150h] [rbp-4C8h] BYREF
  __int128 v92; // [rsp+154h] [rbp-4C4h] BYREF
  __int64 v93; // [rsp+168h] [rbp-4B0h] BYREF
  _OWORD v94[2]; // [rsp+170h] [rbp-4A8h] BYREF
  __int128 v95; // [rsp+190h] [rbp-488h] BYREF
  int v96; // [rsp+1A0h] [rbp-478h]
  _BYTE v97[8]; // [rsp+1B0h] [rbp-468h] BYREF
  unsigned int v98; // [rsp+1B8h] [rbp-460h]
  _BYTE v99[24]; // [rsp+1C8h] [rbp-450h] BYREF
  _BYTE v100[24]; // [rsp+1E0h] [rbp-438h] BYREF
  __int64 v101; // [rsp+1F8h] [rbp-420h]
  __int64 v102; // [rsp+200h] [rbp-418h]
  __int64 v103; // [rsp+208h] [rbp-410h]
  char v104; // [rsp+210h] [rbp-408h]
  int v105; // [rsp+211h] [rbp-407h]
  __int16 v106; // [rsp+215h] [rbp-403h]
  char v107; // [rsp+217h] [rbp-401h]
  _BYTE v108[32]; // [rsp+220h] [rbp-3F8h] BYREF
  _BYTE v109[32]; // [rsp+240h] [rbp-3D8h] BYREF
  __int64 v110; // [rsp+260h] [rbp-3B8h]
  _BYTE v111[24]; // [rsp+268h] [rbp-3B0h] BYREF
  _BYTE v112[24]; // [rsp+280h] [rbp-398h] BYREF
  _BYTE v113[24]; // [rsp+298h] [rbp-380h] BYREF
  _BYTE v114[24]; // [rsp+2B0h] [rbp-368h] BYREF
  __int64 v115; // [rsp+2C8h] [rbp-350h]
  __int64 v116; // [rsp+2D0h] [rbp-348h]
  __int64 v117; // [rsp+2D8h] [rbp-340h]
  char v118; // [rsp+2E0h] [rbp-338h]
  int v119; // [rsp+2E1h] [rbp-337h]
  __int16 v120; // [rsp+2E5h] [rbp-333h]
  char v121; // [rsp+2E7h] [rbp-331h]
  struct _GUID *v122; // [rsp+350h] [rbp-2C8h] BYREF
  __int64 v123; // [rsp+358h] [rbp-2C0h] BYREF
  __int128 v124; // [rsp+360h] [rbp-2B8h]
  __int128 v125; // [rsp+370h] [rbp-2A8h]
  __int128 v126; // [rsp+380h] [rbp-298h]
  int v127; // [rsp+390h] [rbp-288h]
  struct _GUID *v128; // [rsp+3A0h] [rbp-278h] BYREF
  __int64 v129; // [rsp+3A8h] [rbp-270h] BYREF
  __int128 v130; // [rsp+3B0h] [rbp-268h]
  __int128 v131; // [rsp+3C0h] [rbp-258h]
  __int128 v132; // [rsp+3D0h] [rbp-248h]
  int v133; // [rsp+3E0h] [rbp-238h]
  _BYTE v134[8]; // [rsp+3F0h] [rbp-228h] BYREF
  _BYTE v135[24]; // [rsp+3F8h] [rbp-220h] BYREF
  _BYTE v136[36]; // [rsp+410h] [rbp-208h] BYREF
  __int16 v137; // [rsp+434h] [rbp-1E4h]
  _QWORD v138[42]; // [rsp+470h] [rbp-1A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+618h] [rbp+0h]

  v81[0] = a2;
  memset_0(v138, 0, sizeof(v138));
  v7 = (_QWORD *)(*(_QWORD *)*a2 + 8LL);
  if ( *(_QWORD *)(*(_QWORD *)*a2 + 32LL) > 7u )
    v7 = (_QWORD *)*v7;
  *(_QWORD *)v76 = v7;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v138,
    "HyperVContainer_ModifySettings");
  v138[0] = &ComputeService::Diagnostics::TraceProvider::HyperVContainer_ModifySettings::`vftable';
  ComputeService::Diagnostics::TraceProvider::HyperVContainer_ModifySettings::StartActivity<unsigned short const *>(
    v138,
    v76);
  v75 = (ComputeService::Management::Details *)ComputeService::Management::ComputeSystem::GetStateAs<ComputeService::Management::HyperVContainerState>(*a2);
  v89 = 0;
  v90 = 0;
  active = ComputeService::Management::ActiveServerOperation::ActiveServerOperation(&Src, a3);
  ComputeService::Management::BeginOperation_ModifySettings<ComputeService::Diagnostics::TraceProvider::HyperVContainer_ModifySettings>(
    &v89,
    a2,
    active,
    v138);
  v128 = 0;
  memset_0(&v129, 0, 0x40u);
  v129 = 0;
  v130 = 0;
  v131 = 0;
  v132 = 0;
  v133 = 0;
  v122 = 0;
  memset_0(&v123, 0, 0x40u);
  v123 = 0;
  v124 = 0;
  v125 = 0;
  v126 = 0;
  v127 = 0;
  *(_OWORD *)v76 = *(_OWORD *)std::wstring::operator std::basic_string_view<unsigned short>(a4, &v90);
  v9 = Marshal::FromJson<Resource::Common::ResourceModificationRequestResponse,>(&Src, v76, &v128);
  Marshal::ThrowOnUnmarshalError(v9, 3224830221LL);
  std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&v83);
  v122 = v128;
  if ( (_DWORD)v128 )
  {
    switch ( (_DWORD)v128 )
    {
      case 7:
        if ( HIDWORD(v128) )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x4E6,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\hypervcontainer\\hypervcontainerorchestrator.cpp",
            (const char *)0x80070032LL,
            (int)&v90);
        v47 = *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)v75 + 21) + 48LL))(
                           *((_QWORD *)v75 + 21),
                           v134);
        Compute::Containers::BridgeMessage::GcsCapabilities::~GcsCapabilities((Compute::Containers::BridgeMessage::GcsCapabilities *)v135);
        if ( v47 < 3 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x4EA,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\hypervcontainer\\hypervcontainerorchestrator.cpp",
            (const char *)0x32,
            (unsigned int)&v90);
        Config::Containers::MappedDirectory::MappedDirectory((Config::Containers::MappedDirectory *)&v91);
        v48 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Config::Containers::MappedDirectory>(
                &v129,
                &Src,
                &v91);
        Marshal::ThrowOnUnmarshalError(v48, 3224830221LL);
        std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&v83);
        if ( BYTE5(v95) && ((*((_DWORD *)v75 + 196) - 3) & 0xFFFFFFFD) != 0 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x4F4,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\hypervcontainer\\hypervcontainerorchestrator.cpp",
            (const char *)0x32,
            (unsigned int)&v90);
        LOBYTE(v79[0]) = BYTE4(v95) != 0;
        BYTE1(v79[0]) = BYTE4(v95) != 0;
        BYTE2(v79[0]) = BYTE4(v95) != 0;
        *(unsigned __int64 *)((char *)v79 + 3) = 0;
        BYTE3(v79[1]) = 0;
        BYTE4(v79[1]) = BYTE4(v95) != 0;
        *(unsigned __int64 *)((char *)&v79[1] + 5) = 0;
        *(_WORD *)((char *)&v79[2] + 5) = 0;
        HIBYTE(v79[2]) = 0;
        v80 = BYTE6(v95);
        v49 = (_OWORD *)ComputeService::Storage::AdjustShareOptionsForCacheMode(v76, v79, v98);
        *(_OWORD *)v86 = *v49;
        v50 = *(__m128i *)((char *)v49 + 9);
        *(__m128i *)&v86[9] = v50;
        LOBYTE(v51) = 1;
        if ( !(unsigned __int8)ComputeService::ContainerUtilities::ValidateNewMappedDirectory(
                                 *((_QWORD *)v75 + 84) + 488LL,
                                 *((_QWORD *)v75 + 84) + 456LL,
                                 &v91,
                                 v51) )
        {
          ComputeService::Storage::BuildShareNameForDirectory(&Src);
          v81[0] = 0;
          std::_Tree<std::_Tmap_traits<std::wstring,Schema::Responses::System::NetworkProperty,std::less<void>,std::allocator<std::pair<std::wstring const,Schema::Responses::System::NetworkProperty>>,0>>::_Find_lower_bound<std::wstring>(
            (char *)v75 + 832,
            v79,
            &Src);
          v52 = v79[2];
          if ( !(unsigned __int8)std::_Tree<std::_Tmap_traits<std::wstring,Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>,std::less<void>,std::allocator<std::pair<std::wstring const,Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>>>,0>>::_Lower_bound_duplicate<std::wstring>(
                                   v53,
                                   v79[2],
                                   &Src) )
            v52 = *((_QWORD *)v75 + 104);
          v81[0] = v52;
          if ( v52 == *((_QWORD *)v75 + 104) )
          {
            *(_QWORD *)&v90.Data1 = 0;
            ComputeService::Storage::OpenVsmbRootShare(
              &v90,
              (const wchar_t *)&v91,
              *(_QWORD *)(*((_QWORD *)v75 + 84) + 576LL),
              v86,
              v98,
              (HANDLE)0xFFFFFFFFFFFFFFFFLL);
            std::_Tree<std::_Tmap_traits<std::wstring,Config::Containers::MappedDirectory,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Config::Containers::MappedDirectory>>,0>>::_Emplace<std::wstring &,Config::Containers::MappedDirectory &>((_DWORD)v75 + 832);
            v81[0] = *(_QWORD *)v76;
            v79[0] = (unsigned __int64)&v75;
            v79[1] = (unsigned __int64)v81;
            LOBYTE(v79[2]) = 1;
            std::wstring::wstring(v108);
            std::wstring::wstring(v109);
            v110 = 0;
            std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(v111);
            std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(v112);
            std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(v113);
            std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(v114);
            v115 = 0;
            v116 = 0;
            v117 = 0;
            v118 = 0;
            v119 = 0;
            v120 = 0;
            v121 = 0;
            std::wstring::operator=(v108, &Src);
            std::wstring::operator=(v109, &v91);
            v115 = *(_QWORD *)v86;
            LOBYTE(v116) = v86[8];
            BYTE1(v116) = _mm_cvtsi128_si32(v50);
            BYTE2(v116) = _mm_cvtsi128_si32(_mm_srli_si128(v50, 1));
            BYTE3(v116) = _mm_cvtsi128_si32(_mm_srli_si128(v50, 2));
            BYTE4(v116) = _mm_cvtsi128_si32(_mm_srli_si128(v50, 3));
            BYTE5(v116) = _mm_cvtsi128_si32(_mm_srli_si128(v50, 4));
            BYTE6(v116) = _mm_cvtsi128_si32(_mm_srli_si128(v50, 5));
            HIBYTE(v116) = _mm_cvtsi128_si32(_mm_srli_si128(v50, 6));
            LOBYTE(v117) = _mm_cvtsi128_si32(_mm_srli_si128(v50, 7));
            BYTE1(v117) = _mm_cvtsi128_si32(_mm_srli_si128(v50, 8));
            BYTE2(v117) = _mm_cvtsi128_si32(_mm_srli_si128(v50, 9));
            BYTE3(v117) = _mm_cvtsi128_si32(_mm_srli_si128(v50, 10));
            BYTE4(v117) = _mm_cvtsi128_si32(_mm_srli_si128(v50, 11));
            BYTE5(v117) = _mm_cvtsi128_si32(_mm_srli_si128(v50, 12));
            BYTE6(v117) = _mm_cvtsi128_si32(_mm_srli_si128(v50, 13));
            HIBYTE(v117) = _mm_cvtsi128_si32(_mm_srli_si128(v50, 14));
            v118 = _mm_cvtsi128_si32(_mm_srli_si128(v50, 15));
            *(_QWORD *)v76 = *(_QWORD *)&v90.Data1;
            *(_QWORD *)&v90.Data1 = -1;
            ComputeService::Vmwp::AddSmbShare(*((_QWORD *)v75 + 84) + 112LL, v108, v76);
            Schema::VirtualMachines::Resources::Storage::VirtualSmbShare::~VirtualSmbShare((Schema::VirtualMachines::Resources::Storage::VirtualSmbShare *)v108);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v90);
          }
          else if ( (unsigned __int8)std::operator!=<unsigned short>(v52 + 64)
                 || *(_BYTE *)(v81[0] + 132LL) != BYTE4(v95) )
          {
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0x534,
              (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\hypervcontainer\\hypervcontainerorchestrator.cpp",
              (const char *)0x32,
              (unsigned int)&v90);
          }
          Config::Containers::MappedDirectory::MappedDirectory((Config::Containers::MappedDirectory *)v134);
          p_Src = &Src;
          if ( v85 > 7 )
            p_Src = (struct _GUID ***)Src;
          v55 = ComputeService::Storage::BuildVSMBSharePath(v86, p_Src);
          std::wstring::operator=(v134, v55);
          Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v86);
          std::wstring::operator=(v136, v94);
          v137 = WORD2(v95);
          Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(
            v86,
            v134);
          Marshal::DelayedBase<Schema::Responses::System::CacheQueryStatsResponse,Marshal::Details::DelayedJsonTraits>::operator=(
            &v123,
            v86);
          Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(v86);
          v56 = *((_QWORD *)v75 + 17);
          v57 = *(void (__fastcall **)(__int64, __int64, _BYTE *))(*(_QWORD *)v56 + 48LL);
          Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(
            v86,
            &v122);
          v57(v56, *(_QWORD *)*a2 + 8LL, v86);
          Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(v86);
          std::vector<Config::Containers::MappedDirectory>::_Emplace_one_at_back<Config::Containers::MappedDirectory>(
            *((_QWORD *)v75 + 84) + 488LL,
            &v91);
          std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>((Schema::Responses::System::CrashReportProcessDump *)v134);
          Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)&Src);
        }
        std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>((Schema::Responses::System::CrashReportProcessDump *)&v91);
        break;
      case 9:
        v30 = *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)v75 + 21) + 48LL))(
                           *((_QWORD *)v75 + 21),
                           &v91);
        Compute::Containers::BridgeMessage::GcsCapabilities::~GcsCapabilities((Compute::Containers::BridgeMessage::GcsCapabilities *)((char *)&v92 + 4));
        if ( v30 < 2 )
        {
          LODWORD(v73) = *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)v75 + 21) + 48LL))(
                                      *((_QWORD *)v75 + 21),
                                      &v91);
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x5D8,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\hypervcontainer\\hypervcontainerorchestrator.cpp",
            (const char *)0x80070032LL,
            (int)"Unsupported protocol version %d.",
            v73,
            a3);
        }
        *(_OWORD *)v76 = 0;
        Config::Containers::VmHosted::NetworkAdapter::NetworkAdapter((Config::Containers::VmHosted::NetworkAdapter *)v108);
        std::wstring::wstring(&v90);
        v31 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<_GUID>(&v129, &Src, v76);
        Marshal::ThrowOnUnmarshalError(v31, 3224830221LL);
        std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&v83);
        try
        {
          ComputeService::Net::HnsQueryEndpoint();
        }
        catch ( ... )
        {
          v67 = wil::ResultFromCaughtException((wil *)&Src);
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0x5EA,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\hypervcontainer\\hypervcontainerorchestrator.cpp",
            (const char *)v67,
            v71);
          v69 = wil::ResultFromCaughtException(v68);
          v70 = (_QWORD *)(**(_QWORD **)v81[0] + 8LL);
          if ( *(_QWORD *)(**(_QWORD **)v81[0] + 32LL) > 7u )
            v70 = (_QWORD *)*v70;
          ComputeService::Reporting::LogAndThrowComputeSystemError<_GUID &>(v70, v69, "H/", v76);
        }
        ((void (*)(void))Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>)();
        Marshal::DelayedBase<Schema::Responses::System::CacheQueryStatsResponse,Marshal::Details::DelayedJsonTraits>::operator=(
          &v123,
          &Src);
        Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(&Src);
        if ( HIDWORD(v128) )
        {
          if ( HIDWORD(v128) != 1 )
          {
            LODWORD(v73) = HIDWORD(v128);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x62F,
              (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\hypervcontainer\\hypervcontainerorchestrator.cpp",
              (const char *)0x80070032LL,
              (int)"Unsupported request type %d.",
              v73,
              a3);
          }
          ComputeService::Net::HnsDetachEndpointVNic((ComputeService::Net *)v76, (const struct _GUID *)1);
          ComputeService::Resource::RequestManager::FreeNetworkResourceState(
            (ComputeService::Resource::RequestManager *)v76,
            (const struct _GUID *)(*((_QWORD *)v75 + 84) + 928LL),
            v32);
          v33 = *((_QWORD *)v75 + 17);
          v34 = *(void (__fastcall **)(__int64, __int64, struct _GUID ***))(*(_QWORD *)v33 + 48LL);
          Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(
            &Src,
            &v122);
          v34(v33, *(_QWORD *)*a2 + 8LL, &Src);
          Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(&Src);
          ComputeService::Management::Details::RemoveContainerNetworkAdapter(
            v75,
            (struct ComputeService::Management::HyperVContainerState *)v76,
            v35);
          v36 = std::_Tree<std::_Tmap_traits<_GUID,Config::Containers::VmHosted::NetworkAdapter,Vml::GuidLess,std::allocator<std::pair<_GUID const,Config::Containers::VmHosted::NetworkAdapter>>,0>>::_Find<_GUID>(
                  *((_QWORD *)v75 + 84) + 168LL,
                  v76);
          v37 = (_QWORD *)(*((_QWORD *)v75 + 84) + 168LL);
          if ( v36 != *v37 )
          {
            v38 = std::_Tree_val<std::_Tree_simple_types<Vml::VmComConnectData>>::_Extract(v37, v36);
            std::_Tree_node<std::pair<_GUID const,Config::Containers::VmHosted::NetworkAdapter>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<_GUID const,Config::Containers::VmHosted::NetworkAdapter>,void *>>>(
              v39,
              v38);
          }
        }
        else
        {
          Src = &v122;
          v83 = &v75;
          v84 = a2;
          LOWORD(v85) = 257;
          v91 = 0;
          v92 = 0;
          memset_0(&v93, 0, 0x40u);
          v93 = 0;
          memset(v94, 0, sizeof(v94));
          v95 = 0;
          v96 = 0;
          Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(
            v86,
            v108);
          Marshal::DelayedBase<Schema::Responses::System::CacheQueryStatsResponse,Marshal::Details::DelayedJsonTraits>::operator=(
            &v93,
            v86);
          Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(v86);
          v91 = 0;
          Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(
            v86,
            &v91);
          Marshal::DelayedBase<Schema::Responses::System::CacheQueryStatsResponse,Marshal::Details::DelayedJsonTraits>::operator=(
            &v123,
            v86);
          Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(v86);
          v40 = *((_QWORD *)v75 + 17);
          v41 = *(void (__fastcall **)(__int64, __int64, _BYTE *))(*(_QWORD *)v40 + 48LL);
          Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(
            v86,
            &v122);
          v41(v40, *(_QWORD *)*a2 + 8LL, v86);
          Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(v86);
          v42 = (const struct Config::Containers::VmHosted::NetworkAdapter *)(*(_QWORD *)*a2 + 8LL);
          if ( *(_QWORD *)(*(_QWORD *)*a2 + 32LL) > 7u )
            v42 = *(const struct Config::Containers::VmHosted::NetworkAdapter **)v42;
          ComputeService::Management::Details::AddContainerNetworkAdapter(
            v75,
            (struct ComputeService::Management::HyperVContainerState *)v108,
            v42,
            v76,
            &v90);
          v79[0] = (unsigned __int64)&v75;
          v79[1] = (unsigned __int64)v76;
          LOWORD(v79[2]) = 257;
          v91 = 1;
          Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(
            v86,
            &v91);
          Marshal::DelayedBase<Schema::Responses::System::CacheQueryStatsResponse,Marshal::Details::DelayedJsonTraits>::operator=(
            &v123,
            v86);
          Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(v86);
          v43 = *((_QWORD *)v75 + 17);
          v44 = *(void (__fastcall **)(__int64, __int64, _BYTE *))(*(_QWORD *)v43 + 48LL);
          Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(
            v86,
            &v122);
          v44(v43, *(_QWORD *)*a2 + 8LL, v86);
          Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(v86);
          BYTE1(v79[2]) = 0;
          wil::details::ScopeExitFnGuard__lambda_6d0277a7cf3794e5d513745bffd9e017___::operator()(v79);
          BYTE1(v85) = 0;
          v45 = *((_QWORD *)v75 + 84);
          v46 = (_QWORD *)(*(_QWORD *)*a2 + 8LL);
          if ( *(_QWORD *)(*(_QWORD *)*a2 + 32LL) > 7u )
            v46 = (_QWORD *)*v46;
          std::wstring::wstring(v86, v46);
          ComputeService::Resource::RequestManager::AllocateNetworkResourceState(v86, v76, v45 + 928);
          Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v86);
          std::_Tree<std::_Tmap_traits<_GUID,Config::Containers::VmHosted::NetworkAdapter,Vml::GuidLess,std::allocator<std::pair<_GUID const,Config::Containers::VmHosted::NetworkAdapter>>,0>>::_Emplace<_GUID &,Config::Containers::VmHosted::NetworkAdapter &>(
            *((_QWORD *)v75 + 84) + 168LL,
            v81,
            v76,
            v108);
          Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(&v93);
          wil::details::ScopeExitFnGuard__lambda_6cfc97976ee7a654f0b235c750234841___::operator()(&Src);
        }
        Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)&v90);
        Config::Containers::VmHosted::NetworkAdapter::~NetworkAdapter((Config::Containers::VmHosted::NetworkAdapter *)v108);
        break;
      case 0xA:
        v20 = *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)v75 + 21) + 48LL))(
                           *((_QWORD *)v75 + 21),
                           &v91);
        Compute::Containers::BridgeMessage::GcsCapabilities::~GcsCapabilities((Compute::Containers::BridgeMessage::GcsCapabilities *)((char *)&v92 + 4));
        if ( v20 < 3 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x54D,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\hypervcontainer\\hypervcontainerorchestrator.cpp",
            (const char *)0x32,
            (unsigned int)&v90);
        Config::Containers::MappedPipe::MappedPipe((Config::Containers::MappedPipe *)v86);
        v21 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Config::Containers::MappedPipe>(
                &v129,
                &Src,
                v86);
        Marshal::ThrowOnUnmarshalError(v21, 3224830221LL);
        std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&v83);
        *(_QWORD *)v76 = 0;
        *(_QWORD *)&v76[4] = 0x1000000;
        v77 = 0;
        v78 = 0;
        memset(v79, 0, sizeof(v79));
        std::vector<std::wstring>::vector<std::wstring>(v79, (char *)v75 + 808);
        if ( HIDWORD(v128) )
        {
          if ( HIDWORD(v128) != 1 )
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0x580,
              (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\hypervcontainer\\hypervcontainerorchestrator.cpp",
              (const char *)0x32,
              (unsigned int)&v90);
          *(_QWORD *)v76 = 0;
          std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::wstring>(
            v76,
            v79[0],
            v79[1],
            v87);
          if ( *(_QWORD *)v76 == v79[1] )
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0x579,
              (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\hypervcontainer\\hypervcontainerorchestrator.cpp",
              (const char *)2,
              (unsigned int)&v90);
          std::vector<std::wstring>::erase(v79, v76);
        }
        else
        {
          if ( v88 && ((*((_DWORD *)v75 + 196) - 3) & 0xFFFFFFFD) != 0 )
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0x55D,
              (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\hypervcontainer\\hypervcontainerorchestrator.cpp",
              (const char *)0x32,
              (unsigned int)&v90);
          if ( !*((_BYTE *)v75 + 800) )
          {
            std::wstring::wstring(&Src, L"\\\\.\\pipe\\");
            v81[0] = 0;
            ComputeService::Storage::OpenVsmbRootShare(
              v81,
              (const wchar_t *)&Src,
              0,
              v76,
              0,
              (HANDLE)0xFFFFFFFFFFFFFFFFLL);
            std::wstring::wstring(&v91);
            std::wstring::wstring(v94);
            *(_QWORD *)&v95 = 0;
            std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>((char *)&v95 + 8);
            std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(v97);
            std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(v99);
            std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(v100);
            v101 = 0;
            v102 = 0;
            v103 = 0;
            v104 = 0;
            v105 = 0;
            v106 = 0;
            v107 = 0;
            std::wstring::assign(&v91, L"IPC$");
            std::wstring::operator=(v94, &Src);
            v101 = 0;
            v102 = 0x1000000;
            v103 = 0;
            v104 = 0;
            *(_QWORD *)v76 = v81[0];
            v81[0] = -1;
            ComputeService::Vmwp::AddSmbShare(*((_QWORD *)v75 + 84) + 112LL, &v91, v76);
            *((_BYTE *)v75 + 800) = 1;
            Schema::VirtualMachines::Resources::Storage::VirtualSmbShare::~VirtualSmbShare((Schema::VirtualMachines::Resources::Storage::VirtualSmbShare *)&v91);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v81);
            Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)&Src);
          }
          std::vector<std::wstring>::_Emplace_one_at_back<std::wstring const &>(v79, v87);
        }
        std::wstring::wstring(v108);
        std::wstring::wstring(v109);
        v110 = 0;
        std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(v111);
        std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(v112);
        std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(v113);
        std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(v114);
        v115 = 0;
        v116 = 0;
        v117 = 0;
        v118 = 0;
        v119 = 0;
        v120 = 0;
        v121 = 0;
        std::wstring::assign(v108, L"IPC$");
        v115 = 0;
        v116 = 0x1000000;
        v117 = 0;
        v118 = 0;
        std::vector<std::wstring>::operator=(v111, v79);
        *(_QWORD *)&v90.Data1 = 0;
        wil::MakeOrThrow<VmHandleBroker,_GUID &,_GUID const &>(&v90, &CLSID_VSmb, &CLSID_VSmb);
        *(_QWORD *)v76 = *(_QWORD *)&v90.Data1;
        v22 = std::variant<Schema::VirtualMachines::Resources::Storage::VirtualSmbShare>::variant<Schema::VirtualMachines::Resources::Storage::VirtualSmbShare>(
                &v91,
                v108);
        v23 = (_QWORD *)Marshal::ToJson<std::variant<Schema::VirtualMachines::Resources::Storage::VirtualSmbShare>,>(
                          &Src,
                          v22);
        if ( v23[3] > 7u )
          v23 = (_QWORD *)*v23;
        v81[0] = v23;
        v24 = ___InvokeWorkerProcessMethod_UIVmVirtualDeviceAccess__AEBU_GUID__PEBGPEAUIVmHandleBroker____ZAEBU2_PEBGPEAVVmHandleBroker___Vmwp_ComputeService__YAJAEBUWorkerProcessContext_01_P8IVmVirtualDeviceAccess__EAAJAEBU_GUID__PEBGPEAUIVmHandleBroker___Z1__QEAPEBG__QEAPEAVVmHandleBroker___Z(
                (unsigned int)*((_QWORD *)v75 + 84) + 112,
                (unsigned int) IVmVirtualDeviceAccess::`vcall'{72,{flat}},
                (unsigned int)&CLSID_VSmb,
                (unsigned int)v81,
                (__int64)v76);
        if ( v24 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x590,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\hypervcontainer\\hypervcontainerorchestrator.cpp",
            (const char *)(unsigned int)v24,
            v72);
        Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)&Src);
        std::_Variant_destroy_layer_<Schema::VirtualMachines::Resources::Storage::VirtualSmbShare>::~_Variant_destroy_layer_<Schema::VirtualMachines::Resources::Storage::VirtualSmbShare>(&v91);
        wil::details::lambda_call_log__lambda_974c2228fc33edd13226e7de0a6d34c8___::__autoclassinit2(&v91);
        v25 = lambda_974c2228fc33edd13226e7de0a6d34c8_::_lambda_974c2228fc33edd13226e7de0a6d34c8_(v76, v108, &v75, &v90);
        Src = (struct _GUID **)retaddr;
        v83 = (ComputeService::Management::Details **)"onecore\\vm\\compute\\management\\orchestration\\hypervcontainer\\"
                                                      "hypervcontainerorchestrator.cpp";
        v84 = 0;
        LOWORD(v85) = 1427;
        wil::scope_exit_log__lambda_3b597af51af261d054dd6cfe5229bb74___(&v91, &Src, v25);
        Config::Containers::MappedPipe::MappedPipe((Config::Containers::MappedPipe *)v134);
        v26 = ComputeService::Storage::BuildVSMBPipePath(&Src);
        std::wstring::operator=(v136, v26);
        Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)&Src);
        std::wstring::operator=(v134, v86);
        v136[32] = v88;
        Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(
          &Src,
          v134);
        Marshal::DelayedBase<Schema::Responses::System::CacheQueryStatsResponse,Marshal::Details::DelayedJsonTraits>::operator=(
          &v123,
          &Src);
        Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(&Src);
        v27 = *((_QWORD *)v75 + 17);
        v28 = *(void (__fastcall **)(__int64, __int64, struct _GUID ***))(*(_QWORD *)v27 + 48LL);
        Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(
          &Src,
          &v122);
        v28(v27, *(_QWORD *)*a2 + 8LL, &Src);
        Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(&Src);
        LOBYTE(v95) = 0;
        std::vector<std::wstring>::operator=((char *)v75 + 808, v111);
        std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>((Schema::Responses::System::CrashReportProcessDump *)v134);
        wil::details::lambda_call_log__lambda_974c2228fc33edd13226e7de0a6d34c8___::_lambda_call_log__lambda_974c2228fc33edd13226e7de0a6d34c8___(&v91);
        v29 = *(_QWORD *)&v90.Data1;
        if ( *(_QWORD *)&v90.Data1 )
        {
          *(_QWORD *)&v90.Data1 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        }
        Schema::VirtualMachines::Resources::Storage::VirtualSmbShare::~VirtualSmbShare((Schema::VirtualMachines::Resources::Storage::VirtualSmbShare *)v108);
        std::vector<std::wstring>::_Tidy(v79);
        std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>((Schema::Responses::System::CrashReportProcessDump *)v86);
        break;
      case 0xB:
        v15 = *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)v75 + 21) + 48LL))(
                           *((_QWORD *)v75 + 21),
                           v134);
        Compute::Containers::BridgeMessage::GcsCapabilities::~GcsCapabilities((Compute::Containers::BridgeMessage::GcsCapabilities *)v135);
        if ( v15 < 3 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x5B0,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\hypervcontainer\\hypervcontainerorchestrator.cpp",
            (const char *)0x32,
            (unsigned int)&v90);
        Config::Containers::MappedVirtualDisk::MappedVirtualDisk((Config::Containers::MappedVirtualDisk *)&v91);
        v16 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Config::Containers::MappedVirtualDisk>(
                &v129,
                &Src,
                &v91);
        Marshal::ThrowOnUnmarshalError(v16, 3224830221LL);
        std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&v83);
        if ( BYTE1(v95) && ((*((_DWORD *)v75 + 196) - 3) & 0xFFFFFFFD) != 0 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x5BA,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\hypervcontainer\\hypervcontainerorchestrator.cpp",
            (const char *)0x32,
            (unsigned int)&v90);
        if ( HIDWORD(v128) )
        {
          if ( HIDWORD(v128) != 1 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x5CD,
              (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\hypervcontainer\\hypervcontainerorchestrator.cpp",
              (const char *)0x80070032LL,
              (int)&v90);
          v19 = (ComputeService::UtilityVm *)(*(_QWORD *)*a2 + 8LL);
          if ( *(_QWORD *)(*(_QWORD *)*a2 + 32LL) > 7u )
            v19 = *(ComputeService::UtilityVm **)v19;
          ComputeService::UtilityVm::ProcessRemoveMappedVirtualDisk(
            v19,
            *((const unsigned __int16 **)v75 + 84),
            (struct ComputeService::UtilityVm::Environment *)&v91,
            0,
            (struct ComputeService::UtilityVm::GuestServiceState *)&v90);
        }
        else
        {
          v17 = (ComputeService::Management::Details *)((char *)v75 + 128);
          if ( !v75 )
            v17 = 0;
          v18 = (ComputeService::UtilityVm *)(*(_QWORD *)*a2 + 8LL);
          if ( *(_QWORD *)(*(_QWORD *)*a2 + 32LL) > 7u )
            v18 = *(ComputeService::UtilityVm **)v18;
          ComputeService::UtilityVm::ProcessAddMappedVirtualDisk(
            v18,
            *((const unsigned __int16 **)v75 + 84),
            (struct ComputeService::UtilityVm::Environment *)&v91,
            v17,
            (struct ComputeService::UtilityVm::GuestServiceState *)&v90);
        }
        std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>((Schema::Responses::System::CrashReportProcessDump *)&v91);
        break;
      case 0xD:
        if ( HIDWORD(v128) != 2 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x66F,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\hypervcontainer\\hypervcontainerorchestrator.cpp",
            (const char *)0x80070032LL,
            (int)&v90);
        Schema::VirtualMachines::Resources::Gpu::GpuConfiguration::GpuConfiguration((Schema::VirtualMachines::Resources::Gpu::GpuConfiguration *)&Src);
        v10 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Schema::VirtualMachines::Resources::Gpu::GpuConfiguration>(
                &v129,
                v86,
                &Src);
        Marshal::ThrowOnUnmarshalError(v10, 3224830221LL);
        std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&v86[8]);
        v11 = *((_QWORD *)v75 + 84);
        Schema::VirtualMachines::Resources::Gpu::GpuConfiguration::operator=(v11 + 360, &Src);
        if ( *(_DWORD *)(v11 + 360) )
        {
          v14 = (ComputeService::VmCommonHelpers::VirtualGpu *)(*(_QWORD *)*a2 + 8LL);
          if ( *(_QWORD *)(*(_QWORD *)*a2 + 32LL) > 7u )
            v14 = *(ComputeService::VmCommonHelpers::VirtualGpu **)v14;
          ComputeService::VmCommonHelpers::VirtualGpu::SetupGpus(v14, (const unsigned __int16 *)(v11 + 320), v13);
        }
        else
        {
          LOBYTE(v12) = 1;
          ComputeService::VmCommonHelpers::VirtualGpu::CleanupGpus(
            (ComputeService::VmCommonHelpers::VirtualGpu *)(v11 + 320),
            v12,
            (bool)v13);
        }
        std::_Tree<std::_Tmap_traits<std::wstring,unsigned short,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned short>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned short,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned short>>,0>>(&v83);
        break;
      default:
        LODWORD(v73) = (_DWORD)v128;
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x687,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\hypervcontainer\\hypervcontainerorchestrator.cpp",
          (const char *)0x80070032LL,
          (int)"Unsupported resource type %d.",
          v73,
          a3);
    }
  }
  else
  {
    if ( HIDWORD(v128) != 2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x637,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\hypervcontainer\\hypervcontainerorchestrator.cpp",
        (const char *)0x80070032LL,
        (int)&v90);
    v81[0] = 0;
    v58 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Config::Containers::MemorySettings>(
            &v129,
            &Src,
            v81);
    Marshal::ThrowOnUnmarshalError(v58, 3224830221LL);
    std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&v83);
    if ( v81[0] != *((_QWORD *)v75 + 106) )
    {
      v59 = *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)v75 + 21) + 48LL))(
                         *((_QWORD *)v75 + 21),
                         &v91);
      Compute::Containers::BridgeMessage::GcsCapabilities::~GcsCapabilities((Compute::Containers::BridgeMessage::GcsCapabilities *)((char *)&v92 + 4));
      if ( v59 < 3 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x645,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\hypervcontainer\\hypervcontainerorchestrator.cpp",
          (const char *)0x32,
          (unsigned int)&v90);
      UtilityVmMemorySize = (struct ComputeService::UtilityVm::Environment *)ComputeService::HyperVContainer::GetUtilityVmMemorySize(
                                                                               v81[0],
                                                                               *((unsigned int *)v75 + 196));
      v61 = v75;
      v62 = (_QWORD *)*((_QWORD *)v75 + 84);
      if ( v62[121] )
      {
        ComputeService::JobUtilities::UpdatePageFileForPartition(
          v62[72],
          v62 + 119,
          (char *)UtilityVmMemorySize + v62[123],
          (char *)UtilityVmMemorySize + v62[123]);
        v61 = v75;
      }
      if ( UtilityVmMemorySize != *(struct ComputeService::UtilityVm::Environment **)(*((_QWORD *)v61 + 84) + 944LL) )
      {
        v79[0] = 10000;
        ComputeService::Management::ActiveStateOperation::CreateCancellationToken(&v89, &v79[1]);
        ComputeService::UtilityVm::ResizeMemory(
          *((ComputeService::UtilityVm **)v75 + 84),
          UtilityVmMemorySize,
          (unsigned __int64)v79,
          v63);
        if ( v79[2] )
          std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v79[2]);
        v61 = v75;
      }
      if ( *((_DWORD *)v61 + 196) != 5 )
      {
        v64 = *((_QWORD *)v61 + 17);
        v65 = *(void (__fastcall **)(__int64, __int64, struct _GUID ***))(*(_QWORD *)v64 + 48LL);
        Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(
          &Src,
          &v128);
        v65(v64, *(_QWORD *)*a2 + 8LL, &Src);
        Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(&Src);
        *((_QWORD *)v75 + 106) = v81[0];
      }
    }
  }
  ComputeService::Management::ActiveStateOperation::Complete(
    (ComputeService::Management::ActiveStateOperation *)&v89,
    0);
  Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(&v123);
  Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(&v129);
  std::unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>::~unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>(&v89);
  ComputeService::Diagnostics::TraceProvider::HyperVContainer_ModifySettings::~HyperVContainer_ModifySettings((ComputeService::Diagnostics::TraceProvider::HyperVContainer_ModifySettings *)v138);
  ComputeService::Management::OrchestratorCallContext::~OrchestratorCallContext(a3);
  return 1;
}

```

## disassembly

```asm
0x140098ed0  mov     rax, rsp
0x140098ed3  push    rbx
0x140098ed4  push    rsi
0x140098ed5  push    rdi
0x140098ed6  push    r12
0x140098ed8  push    r13
0x140098eda  push    r14
0x140098edc  push    r15
0x140098ede  sub     rsp, 5E0h
0x140098ee5  movaps  xmmword ptr [rax-48h], xmm6
0x140098ee9  mov     rax, cs:__security_cookie
0x140098ef0  xor     rax, rsp
0x140098ef3  mov     [rsp+618h+var_58], rax
0x140098efb  mov     rbx, r9
0x140098efe  mov     r15, r8
0x140098f01  mov     r14, rdx
0x140098f04  mov     [rsp+618h+var_598], rdx
0x140098f0c  mov     [rsp+618h+var_5E8], r8
0x140098f11  xor     edx, edx; Val
0x140098f13  mov     r8d, 150h; Size
0x140098f19  lea     rcx, [rsp+618h+var_1A8]; void *
0x140098f21  call    memset_0
0x140098f26  mov     rax, [r14]
0x140098f29  mov     rcx, [rax]
0x140098f2c  add     rcx, 8
0x140098f30  cmp     qword ptr [rcx+18h], 7
0x140098f35  jbe     short loc_140098F3A
0x140098f37  mov     rcx, [rcx]
0x140098f3a  mov     qword ptr [rsp+618h+var_5D8], rcx
0x140098f3f  lea     rdx, aHypervcontaine_5; "HyperVContainer_ModifySettings"
0x140098f46  lea     rcx, [rsp+618h+var_1A8]
0x140098f4e  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140098f53  lea     rax, ??_7HyperVContainer_ModifySettings@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::HyperVContainer_ModifySettings::`vftable'
0x140098f5a  mov     [rsp+618h+var_1A8], rax
0x140098f62  lea     rdx, [rsp+618h+var_5D8]
0x140098f67  lea     rcx, [rsp+618h+var_1A8]
0x140098f6f  call    ??$StartActivity@PEBG@HyperVContainer_ModifySettings@TraceProvider@Diagnostics@ComputeService@@QEAAX$$QEAPEBG@Z; ComputeService::Diagnostics::TraceProvider::HyperVContainer_ModifySettings::StartActivity<ushort const *>(ushort const * &&)
0x140098f74  nop
0x140098f75  mov     rcx, [r14]
0x140098f78  call    ??$GetStateAs@UHyperVContainerState@Management@ComputeService@@@ComputeSystem@Management@ComputeService@@QEAAPEAUHyperVContainerState@12@XZ; ComputeService::Management::ComputeSystem::GetStateAs<ComputeService::Management::HyperVContainerState>(void)
0x140098f7d  mov     [rsp+618h+var_5E0], rax
0x140098f82  xor     r12d, r12d
0x140098f85  mov     [rsp+618h+var_4F8], r12
0x140098f8d  xorps   xmm0, xmm0
0x140098f90  movdqu  xmmword ptr [rsp+618h+var_4F0.Data1], xmm0
0x140098f99  mov     rdx, r15
0x140098f9c  lea     rcx, [rsp+618h+Src]
0x140098fa4  call    ??0ActiveServerOperation@Management@ComputeService@@QEAA@$$QEAV012@@Z; ComputeService::Management::ActiveServerOperation::ActiveServerOperation(ComputeService::Management::ActiveServerOperation &&)
0x140098fa9  lea     rcx, [rsp+618h+var_4F0]
0x140098fb1  mov     [rsp+618h+var_5F8], rcx; unsigned int
0x140098fb6  lea     r9, [rsp+618h+var_1A8]
0x140098fbe  mov     r8, rax
0x140098fc1  mov     rdx, r14
0x140098fc4  lea     rcx, [rsp+618h+var_4F8]
0x140098fcc  call    ??$BeginOperation_ModifySettings@VHyperVContainer_ModifySettings@TraceProvider@Diagnostics@ComputeService@@@Management@ComputeService@@YA?AVActiveStateOperation@01@AEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@VActiveServerOperation@01@$$QEAVHyperVContainer_ModifySettings@TraceProvider@Diagnostics@1@V?$shared_ptr@UStateOperationContext@Management@ComputeService@@@4@@Z; ComputeService::Management::BeginOperation_ModifySettings<ComputeService::Diagnostics::TraceProvider::HyperVContainer_ModifySettings>(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::ActiveServerOperation,ComputeService::Diagnostics::TraceProvider::HyperVContainer_ModifySettings &&,std::shared_ptr<ComputeService::Management::StateOperationContext>)
0x140098fd1  nop
0x140098fd2  mov     [rsp+618h+var_278], r12
0x140098fda  lea     r13d, [r12+40h]
0x140098fdf  mov     r8d, r13d; Size
0x140098fe2  xor     edx, edx; Val
0x140098fe4  lea     rcx, [rsp+618h+var_270]; void *
0x140098fec  call    memset_0
0x140098ff1  mov     [rsp+618h+var_270], r12
0x140098ff9  xorps   xmm0, xmm0
0x140098ffc  movdqa  [rsp+618h+var_268], xmm0
0x140099005  xorps   xmm1, xmm1
0x140099008  movdqa  [rsp+618h+var_258], xmm1
0x140099011  movdqa  [rsp+618h+var_248], xmm0
0x14009901a  mov     [rsp+618h+var_238], r12d
0x140099022  mov     [rsp+618h+var_2C8], r12
0x14009902a  mov     r8d, r13d; Size
0x14009902d  xor     edx, edx; Val
0x14009902f  lea     rcx, [rsp+618h+var_2C0]; void *
0x140099037  call    memset_0
0x14009903c  mov     [rsp+618h+var_2C0], r12
0x140099044  xorps   xmm0, xmm0
0x140099047  movdqa  [rsp+618h+var_2B8], xmm0
0x140099050  xorps   xmm1, xmm1
0x140099053  movdqa  [rsp+618h+var_2A8], xmm1
0x14009905c  movdqa  [rsp+618h+var_298], xmm0
0x140099065  mov     [rsp+618h+var_288], r12d
0x14009906d  lea     rdx, [rsp+618h+var_4F0]
0x140099075  mov     rcx, rbx
0x140099078  call    ??B?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@1@XZ; std::wstring::operator std::basic_string_view<ushort>(void)
0x14009907d  movups  xmm0, xmmword ptr [rax]
0x140099080  movdqu  xmmword ptr [rsp+618h+var_5D8], xmm0
0x140099086  lea     r8, [rsp+618h+var_278]
0x14009908e  lea     rdx, [rsp+618h+var_5D8]
0x140099093  lea     rcx, [rsp+618h+Src]
0x14009909b  call    ??$FromJson@UResourceModificationRequestResponse@Common@Resource@@$$V@Marshal@@YA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@PEAUResourceModificationRequestResponse@Common@Resource@@W4UnmarshalFlags@0@@Z; Marshal::FromJson<Resource::Common::ResourceModificationRequestResponse,>(std::basic_string_view<ushort>,Resource::Common::ResourceModificationRequestResponse *,Marshal::UnmarshalFlags)
0x1400990a0  nop
0x1400990a1  mov     edi, 0C037010Dh
0x1400990a6  mov     edx, edi
0x1400990a8  mov     rcx, rax
0x1400990ab  call    ?ThrowOnUnmarshalError@Marshal@@YAXAEBU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@J@Z; Marshal::ThrowOnUnmarshalError(std::pair<bool,std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>> const &,long)
0x1400990b0  nop
0x1400990b1  lea     rcx, [rsp+618h+var_580]
0x1400990b9  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x1400990be  mov     r8d, dword ptr [rsp+618h+var_278]
0x1400990c6  mov     dword ptr [rsp+618h+var_2C8], r8d
0x1400990ce  mov     edx, dword ptr [rsp+618h+var_278+4]
0x1400990d5  mov     dword ptr [rsp+618h+var_2C8+4], edx
0x1400990dc  mov     ecx, r8d
0x1400990df  test    r8d, r8d
0x1400990e2  jz      loc_14009A702
0x1400990e8  sub     ecx, 7
0x1400990eb  jz      loc_140099FEE
0x1400990f1  sub     ecx, 2
0x1400990f4  jz      loc_140099A9E
0x1400990fa  sub     ecx, 1
0x1400990fd  jz      loc_1400993A2
0x140099103  sub     ecx, 1
0x140099106  jz      loc_14009921B
0x14009910c  sub     ecx, 2
0x14009910f  mov     rcx, [rsp+618h]; this
0x140099117  jz      short loc_140099142
0x140099119  mov     dword ptr [rsp+618h+var_5F0], r8d; char *
0x14009911e  lea     rax, aUnsupportedRes_0; "Unsupported resource type %d."
0x140099125  mov     [rsp+618h+var_5F8], rax; int
0x14009912a  mov     r9d, 80070032h; char *
0x140099130  lea     r8, aOnecoreVmCompu_108; "onecore\\vm\\compute\\management\\orche"...
0x140099137  mov     edx, 687h; void *
0x14009913c  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x140099142  cmp     edx, 2
0x140099145  setnz   al
0x140099148  test    al, al
0x14009914a  jz      short loc_140099164
0x14009914c  mov     r9d, 80070032h; char *
0x140099152  lea     r8, aOnecoreVmCompu_108; "onecore\\vm\\compute\\management\\orche"...
0x140099159  mov     edx, 66Fh; void *
0x14009915e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140099164  lea     rcx, [rsp+618h+Src]; this
0x14009916c  call    ??0GpuConfiguration@Gpu@Resources@VirtualMachines@Schema@@QEAA@XZ; Schema::VirtualMachines::Resources::Gpu::GpuConfiguration::GpuConfiguration(void)
0x140099171  nop
0x140099172  lea     r8, [rsp+618h+Src]
0x14009917a  lea     rdx, [rsp+618h+var_548]
0x140099182  lea     rcx, [rsp+618h+var_270]
0x14009918a  call    ??$Unmarshal@UGpuConfiguration@Gpu@Resources@VirtualMachines@Schema@@@?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEBA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@PEAUGpuConfiguration@Gpu@Resources@VirtualMachines@Schema@@@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Schema::VirtualMachines::Resources::Gpu::GpuConfiguration>(Schema::VirtualMachines::Resources::Gpu::GpuConfiguration *)
0x14009918f  nop
0x140099190  mov     edx, edi
0x140099192  mov     rcx, rax
0x140099195  call    ?ThrowOnUnmarshalError@Marshal@@YAXAEBU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@J@Z; Marshal::ThrowOnUnmarshalError(std::pair<bool,std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>> const &,long)
0x14009919a  nop
0x14009919b  lea     rcx, [rsp+618h+var_548+8]
0x1400991a3  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x1400991a8  mov     rax, [rsp+618h+var_5E0]
0x1400991ad  mov     rbx, [rax+2A0h]
0x1400991b4  lea     rdi, [rbx+140h]
0x1400991bb  lea     rcx, [rdi+28h]
0x1400991bf  lea     rdx, [rsp+618h+Src]
0x1400991c7  call    ??4GpuConfiguration@Gpu@Resources@VirtualMachines@Schema@@QEAAAEAU01234@AEBU01234@@Z; Schema::VirtualMachines::Resources::Gpu::GpuConfiguration::operator=(Schema::VirtualMachines::Resources::Gpu::GpuConfiguration const &)
0x1400991cc  cmp     [rbx+168h], r12d
0x1400991d3  jz      short loc_1400991F8
0x1400991d5  mov     rax, [r14]
0x1400991d8  mov     rcx, [rax]
0x1400991db  add     rcx, 8
0x1400991df  cmp     qword ptr [rcx+18h], 7
0x1400991e4  jbe     short loc_1400991E9
0x1400991e6  mov     rcx, [rcx]; this
0x1400991e9  mov     rdx, rdi; unsigned __int16 *
0x1400991ec  call    ?SetupGpus@VirtualGpu@VmCommonHelpers@ComputeService@@YAXPEBGAEAUGpuEnvironment@123@@Z; ComputeService::VmCommonHelpers::VirtualGpu::SetupGpus(ushort const *,ComputeService::VmCommonHelpers::VirtualGpu::GpuEnvironment &)
0x1400991f1  mov     esi, 1
0x1400991f6  jmp     short loc_140099209
0x1400991f8  mov     esi, 1
0x1400991fd  mov     dl, sil; struct ComputeService::VmCommonHelpers::VirtualGpu::GpuEnvironment *
0x140099200  mov     rcx, rdi; this
0x140099203  call    ?CleanupGpus@VirtualGpu@VmCommonHelpers@ComputeService@@YAXAEAUGpuEnvironment@123@_N@Z; ComputeService::VmCommonHelpers::VirtualGpu::CleanupGpus(ComputeService::VmCommonHelpers::VirtualGpu::GpuEnvironment &,bool)
0x140099208  nop
0x140099209  lea     rcx, [rsp+618h+var_580]
0x140099211  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@G@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,ushort,std::less<void>,std::allocator<std::pair<std::wstring const,ushort>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,ushort,std::less<void>,std::allocator<std::pair<std::wstring const,ushort>>,0>>(void)
0x140099216  jmp     loc_14009A8F0
0x14009921b  mov     rax, [rsp+618h+var_5E0]
0x140099220  mov     rcx, [rax+0A8h]
0x140099227  mov     rax, [rcx]
0x14009922a  lea     rdx, [rsp+618h+var_228]
0x140099232  mov     rax, [rax+30h]
0x140099236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009923b  mov     ebx, [rax]
0x14009923d  lea     rcx, [rsp+618h+var_220]; this
0x140099245  call    ??1GcsCapabilities@BridgeMessage@Containers@Compute@@QEAA@XZ; Compute::Containers::BridgeMessage::GcsCapabilities::~GcsCapabilities(void)
0x14009924a  cmp     ebx, 3
0x14009924d  jnb     short loc_14009926F
0x14009924f  mov     rcx, [rsp+618h]; this
0x140099257  mov     r9d, 32h ; '2'; char *
0x14009925d  lea     r8, aOnecoreVmCompu_108; "onecore\\vm\\compute\\management\\orche"...
0x140099264  mov     edx, 5B0h; void *
0x140099269  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14009926f  lea     rcx, [rsp+618h+var_4C8]; this
0x140099277  call    ??0MappedVirtualDisk@Containers@Config@@QEAA@XZ; Config::Containers::MappedVirtualDisk::MappedVirtualDisk(void)
0x14009927c  nop
0x14009927d  lea     r8, [rsp+618h+var_4C8]
0x140099285  lea     rdx, [rsp+618h+Src]
0x14009928d  lea     rcx, [rsp+618h+var_270]
0x140099295  call    ??$Unmarshal@UMappedVirtualDisk@Containers@Config@@@?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEBA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@PEAUMappedVirtualDisk@Containers@Config@@@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Config::Containers::MappedVirtualDisk>(Config::Containers::MappedVirtualDisk *)
0x14009929a  nop
0x14009929b  mov     edx, edi
0x14009929d  mov     rcx, rax
0x1400992a0  call    ?ThrowOnUnmarshalError@Marshal@@YAXAEBU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@J@Z; Marshal::ThrowOnUnmarshalError(std::pair<bool,std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>> const &,long)
0x1400992a5  nop
0x1400992a6  lea     rcx, [rsp+618h+var_580]
0x1400992ae  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x1400992b3  mov     rcx, [rsp+618h+var_5E0]
0x1400992b8  cmp     byte ptr [rsp+618h+var_488+1], r12b
0x1400992c0  jz      short loc_1400992F2
0x1400992c2  mov     eax, [rcx+310h]
0x1400992c8  sub     eax, 3
0x1400992cb  test    eax, 0FFFFFFFDh
0x1400992d0  jz      short loc_1400992F2
0x1400992d2  mov     rcx, [rsp+618h]; this
0x1400992da  mov     r9d, 32h ; '2'; char *
0x1400992e0  lea     r8, aOnecoreVmCompu_108; "onecore\\vm\\compute\\management\\orche"...
0x1400992e7  mov     edx, 5BAh; void *
0x1400992ec  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400992f2  mov     eax, dword ptr [rsp+618h+var_278+4]
0x1400992f9  test    eax, eax
0x1400992fb  jnz     short loc_14009933B
0x1400992fd  test    rcx, rcx
0x140099300  lea     r9, [rcx+80h]
0x140099307  jnz     short loc_14009930C
0x140099309  mov     r9, r12; struct Config::Containers::MappedVirtualDisk *
0x14009930c  mov     rdx, [rcx+2A0h]; unsigned __int16 *
0x140099313  mov     rax, [r14]
0x140099316  mov     rcx, [rax]
0x140099319  add     rcx, 8
0x14009931d  cmp     qword ptr [rcx+18h], 7
0x140099322  jbe     short loc_140099327
0x140099324  mov     rcx, [rcx]; this
0x140099327  lea     r8, [rsp+618h+var_4C8]; struct ComputeService::UtilityVm::Environment *
0x14009932f  call    ?ProcessAddMappedVirtualDisk@UtilityVm@ComputeService@@YAXPEBGPEAUEnvironment@12@AEAUMappedVirtualDisk@Containers@Config@@PEAUGuestServiceState@12@@Z; ComputeService::UtilityVm::ProcessAddMappedVirtualDisk(ushort const *,ComputeService::UtilityVm::Environment *,Config::Containers::MappedVirtualDisk &,ComputeService::UtilityVm::GuestServiceState *)
0x140099334  mov     esi, 1
0x140099339  jmp     short loc_140099370
0x14009933b  mov     esi, 1
0x140099340  cmp     eax, esi
0x140099342  jnz     short loc_140099382
0x140099344  mov     rdx, [rcx+2A0h]; unsigned __int16 *
0x14009934b  mov     rax, [r14]
0x14009934e  mov     rcx, [rax]
0x140099351  add     rcx, 8
0x140099355  cmp     qword ptr [rcx+18h], 7
0x14009935a  jbe     short loc_14009935F
0x14009935c  mov     rcx, [rcx]; this
0x14009935f  xor     r9d, r9d; struct Config::Containers::MappedVirtualDisk *
0x140099362  lea     r8, [rsp+618h+var_4C8]; struct ComputeService::UtilityVm::Environment *
0x14009936a  call    ?ProcessRemoveMappedVirtualDisk@UtilityVm@ComputeService@@YAXPEBGPEAUEnvironment@12@AEBUMappedVirtualDisk@Containers@Config@@PEAUGuestServiceState@12@@Z; ComputeService::UtilityVm::ProcessRemoveMappedVirtualDisk(ushort const *,ComputeService::UtilityVm::Environment *,Config::Containers::MappedVirtualDisk const &,ComputeService::UtilityVm::GuestServiceState *)
0x14009936f  nop
0x140099370  lea     rcx, [rsp+618h+var_4C8]; this
0x140099378  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x14009937d  jmp     loc_14009A8F0
0x140099382  mov     rcx, [rsp+618h]; this
0x14009938a  mov     r9d, 80070032h; char *
0x140099390  lea     r8, aOnecoreVmCompu_108; "onecore\\vm\\compute\\management\\orche"...
0x140099397  mov     edx, 5CDh; void *
0x14009939c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400993a2  mov     rax, [rsp+618h+var_5E0]
0x1400993a7  mov     rcx, [rax+0A8h]
0x1400993ae  mov     rax, [rcx]
0x1400993b1  lea     rdx, [rsp+618h+var_4C8]
0x1400993b9  mov     rax, [rax+30h]
0x1400993bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400993c2  mov     ebx, [rax]
0x1400993c4  lea     rcx, [rsp+618h+var_4C0]; this
0x1400993cc  call    ??1GcsCapabilities@BridgeMessage@Containers@Compute@@QEAA@XZ; Compute::Containers::BridgeMessage::GcsCapabilities::~GcsCapabilities(void)
0x1400993d1  cmp     ebx, 3
0x1400993d4  jnb     short loc_1400993F6
0x1400993d6  mov     rcx, [rsp+618h]; this
0x1400993de  mov     r9d, 32h ; '2'; char *
0x1400993e4  lea     r8, aOnecoreVmCompu_108; "onecore\\vm\\compute\\management\\orche"...
0x1400993eb  mov     edx, 54Dh; void *
0x1400993f0  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400993f6  lea     rcx, [rsp+618h+var_548]; this
0x1400993fe  call    ??0MappedPipe@Containers@Config@@QEAA@XZ; Config::Containers::MappedPipe::MappedPipe(void)
0x140099403  nop
0x140099404  lea     r8, [rsp+618h+var_548]
0x14009940c  lea     rdx, [rsp+618h+Src]
0x140099414  lea     rcx, [rsp+618h+var_270]
0x14009941c  call    ??$Unmarshal@UMappedPipe@Containers@Config@@@?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEBA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@PEAUMappedPipe@Containers@Config@@@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Config::Containers::MappedPipe>(Config::Containers::MappedPipe *)
0x140099421  nop
0x140099422  mov     edx, edi
0x140099424  mov     rcx, rax
0x140099427  call    ?ThrowOnUnmarshalError@Marshal@@YAXAEBU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@J@Z; Marshal::ThrowOnUnmarshalError(std::pair<bool,std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>> const &,long)
0x14009942c  nop
0x14009942d  lea     rcx, [rsp+618h+var_580]
0x140099435  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x14009943a  mov     qword ptr [rsp+618h+var_5D8], r12
0x14009943f  mov     qword ptr [rsp+618h+var_5D8+8], 1000000h
0x140099448  mov     [rsp+618h+var_5C8], r12
0x14009944d  mov     [rsp+618h+var_5C0], r12b
0x140099452  mov     esi, 1
0x140099457  xorps   xmm0, xmm0
0x14009945a  xor     eax, eax
0x14009945c  movups  xmmword ptr [rsp+618h+var_5B8], xmm0
0x140099461  mov     [rsp+618h+var_5A8], rax
0x140099466  mov     rdx, [rsp+618h+var_5E0]
0x14009946b  add     rdx, 328h
0x140099472  lea     rcx, [rsp+618h+var_5B8]
0x140099477  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x14009947c  nop
0x14009947d  mov     eax, dword ptr [rsp+618h+var_278+4]
0x140099484  test    eax, eax
0x140099486  jnz     loc_14009967A
  ... truncated ...
```
