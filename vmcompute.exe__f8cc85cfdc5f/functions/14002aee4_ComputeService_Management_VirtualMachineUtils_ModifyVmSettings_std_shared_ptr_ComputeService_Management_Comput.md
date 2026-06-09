# ComputeService::Management::VirtualMachineUtils::ModifyVmSettings(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,Schema::Requests::System::ModifySettingRequest,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,ComputeService::Management::ActiveStateOperation &)

- ea: `0x14002aee4`
- end: `0x14002d269`
- name: `?ModifyVmSettings@VirtualMachineUtils@Management@ComputeService@@YAXAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@UModifySettingRequest@System@Requests@Schema@@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEAVActiveStateOperation@23@@Z`
- size: `9093`
- prototype: ``
- caller_count: `1`
- callee_count: `103`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14002ab30`

## callees

- `0x14001629c`
- `0x140017040`
- `0x14001bc28`
- `0x14001fc70`
- `0x14001fcac`
- `0x140020890`
- `0x140024030`
- `0x14002436c`
- `0x140025774`
- `0x140026a3c`
- `0x140026a80`
- `0x14002a5e4`
- `0x14002aa44`
- `0x14002ad60`
- `0x14002aee4`
- `0x14002d270`
- `0x14002d29c`
- `0x14002d2d8`
- `0x14002d5a8`
- `0x14002e6ec`
- `0x14002ec30`
- `0x14002f868`
- `0x14002f9e8`
- `0x140031240`
- `0x14003f93c`
- `0x1400421f0`
- `0x140060e88`
- `0x14006eb64`
- `0x14006ecfc`
- `0x1400704e8`
- `0x140072fbc`
- `0x140073a74`
- `0x140073fb4`
- `0x140075c68`
- `0x140095464`
- `0x14009c7dc`
- `0x14009ce6c`
- `0x14009d75c`
- `0x1400a864c`
- `0x1400b2a44`
- `0x1400b903c`
- `0x1400c40e0`
- `0x1400c57c0`
- `0x1400c62bc`
- `0x1400c62e0`
- `0x1400c6500`
- `0x1400c6a74`
- `0x1400c6e6c`
- `0x1400c6f74`
- `0x1400c7cb8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x14002b0b5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x14002b0b5`
- `RPCRT4!UuidFromStringW` at `0x14002c585`
- `RPCRT4!UuidFromStringW` at `0x14002c585`
- `OLEAUT32!__imp_SysAllocString` at `0x14002b465`
- `OLEAUT32!__imp_SysAllocString` at `0x14002c6e8`
- `OLEAUT32!__imp_SysAllocString` at `0x14002b465`
- `OLEAUT32!__imp_SysAllocString` at `0x14002c6e8`
- `OLEAUT32!__imp_SysFreeString` at `0x14002b4a6`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c729`
- `OLEAUT32!__imp_SysFreeString` at `0x14002b4a6`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c729`
- `OLEAUT32!__imp_VariantClear` at `0x14002b556`
- `OLEAUT32!__imp_VariantClear` at `0x14002c7e9`
- `OLEAUT32!__imp_VariantClear` at `0x14002b556`
- `OLEAUT32!__imp_VariantClear` at `0x14002c7e9`

## string_xrefs

- `0x14002af82`: `onecore\vm\compute\management\computesystem\computesystem.h`
- `0x14002b487`: `onecore\vm\common\vml\VmBstr.h`
- `0x14002c70a`: `onecore\vm\common\vml\VmBstr.h`
- `0x14002c2a8`: `EnableHostOSInfoKvpItems can only be updated with Update request`
- `0x14002b53c`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualmachineutils.cpp`
- `0x14002b9a1`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualmachineutils.cpp`
- `0x14002ba3a`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualmachineutils.cpp`
- `0x14002bc0f`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualmachineutils.cpp`
- `0x14002bccf`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualmachineutils.cpp`
- `0x14002bdaa`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualmachineutils.cpp`
- `0x14002bf80`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualmachineutils.cpp`
- `0x14002c02a`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualmachineutils.cpp`
- `0x14002c0d4`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualmachineutils.cpp`
- `0x14002c19e`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualmachineutils.cpp`
- `0x14002c1d7`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualmachineutils.cpp`
- `0x14002c21f`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualmachineutils.cpp`
- `0x14002c259`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualmachineutils.cpp`
- `0x14002c2ba`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualmachineutils.cpp`
- `0x14002c43e`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualmachineutils.cpp`
- `0x14002c4de`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualmachineutils.cpp`
- `0x14002c5ae`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualmachineutils.cpp`
- `0x14002c638`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualmachineutils.cpp`
- `0x14002c7cf`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualmachineutils.cpp`
- `0x14002c8d1`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualmachineutils.cpp`
- `0x14002cc44`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualmachineutils.cpp`
- `0x14002cc7d`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualmachineutils.cpp`
- `0x14002cfe6`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualmachineutils.cpp`
- `0x14002d025`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualmachineutils.cpp`
- `0x14002d05a`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualmachineutils.cpp`
- `0x14002d134`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualmachineutils.cpp`
- `0x14002c050`: `VirtualMachine/ComputeTopology/Processor/CpuBoostPriority`
- `0x14002cbff`: `VirtualMachine/ComputeTopology/Memory/GuestAccessTracking`
- `0x14002bfa6`: `VirtualMachine/ComputeTopology/Processor/CpuThrottlePriority`
- `0x14002c0fa`: `VirtualMachine/Services/KvpExchange`
- `0x14002c302`: `VirtualMachine/ComputeTopology/Processor/Limits`
- `0x14002cad0`: `VirtualMachine/ComputeTopology/Memory/PrepareForMigration`
- `0x14002c89c`: `VirtualMachine/ComputeTopology/Processor/CpuidResult`

## pseudocode

```c
// Hidden C++ exception states: #wind=61
void __fastcall ComputeService::Management::VirtualMachineUtils::ModifyVmSettings(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4)
{
  __int64 *v4; // r12
  unsigned __int8 v7; // di
  char Data1; // r15
  __int64 v9; // rax
  char v10; // bl
  __int64 v11; // rax
  float v12; // xmm0_4
  float v13; // xmm0_4
  unsigned __int64 v14; // rax
  std::_Ref_count_base *v15; // rbx
  __int64 v16; // rax
  __int64 v17; // r8
  __int64 v18; // r9
  std::_Ref_count_base *v19; // rdi
  void (__fastcall *v20)(std::_Ref_count_base *, _BYTE *, _BYTE *, _OWORD *, _DWORD); // rbx
  __int128 *v21; // rcx
  char v22; // bl
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // r8
  __int64 v26; // r9
  std::_Ref_count_base *v27; // rdi
  void (__fastcall *v28)(std::_Ref_count_base *, _SYSTEM_INFO *, _BYTE *, _OWORD *); // rbx
  __int64 v29; // rax
  int v30; // edx
  BSTR v31; // rbx
  int v32; // eax
  bool v33; // bl
  __int64 v34; // rax
  int v35; // eax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  char v39; // bl
  char v40; // bl
  wchar_t *v41; // rdx
  char v42; // bl
  unsigned int v43; // eax
  __int64 v44; // r9
  __int64 v45; // rax
  unsigned int v46; // eax
  char v47; // bl
  __int64 v48; // rax
  int v49; // r9d
  __int64 v50; // rax
  __int64 v51; // rax
  char v52; // bl
  _QWORD *v53; // rdx
  char v54; // bl
  unsigned int v55; // eax
  char v56; // r15
  __int64 v57; // rax
  unsigned int v58; // r12d
  int v59; // eax
  __int64 v60; // rbx
  __int64 v61; // rax
  __int64 v62; // rdx
  int v63; // eax
  char v64; // bl
  __int64 v65; // rax
  __int64 v66; // rax
  char v67; // bl
  __int64 v68; // rax
  unsigned int v69; // r8d
  __int64 v70; // rax
  unsigned int v71; // r8d
  __int64 v72; // rax
  unsigned int v73; // r8d
  __int64 v74; // rax
  int v75; // eax
  __int64 v76; // rdx
  int v77; // ecx
  int v78; // ecx
  int v79; // eax
  int v80; // eax
  __int64 v81; // rax
  ComputeService::VirtualMachine::CapabilityHelpers *v82; // rcx
  int v83; // edx
  int v84; // eax
  __int64 v85; // rax
  unsigned __int16 *v86; // rcx
  char v87; // al
  __int64 v88; // rax
  __int64 v89; // rax
  int v90; // edx
  BSTR v91; // rbx
  int v92; // eax
  unsigned int v93; // eax
  unsigned int v94; // r8d
  unsigned int v95; // eax
  unsigned int v96; // r8d
  int v97; // ecx
  __int64 v98; // rax
  std::_Ref_count_base **v99; // rdx
  __int64 v100; // rax
  __int64 v101; // rax
  __int64 v102; // r8
  __int64 v103; // r9
  int v104; // ecx
  int v105; // ecx
  __int64 v106; // rax
  __int64 v107; // rax
  __int64 v108; // rax
  __int64 v109; // rax
  __int64 v110; // rax
  __int64 v111; // rax
  __int64 v112; // r8
  int v113; // eax
  __int64 v114; // rdx
  __int64 v115; // rbx
  _BYTE *v116; // rdx
  const char *v117; // r9
  int v118; // [rsp+20h] [rbp-5C8h]
  int v119; // [rsp+20h] [rbp-5C8h]
  int v120; // [rsp+20h] [rbp-5C8h]
  int v121; // [rsp+20h] [rbp-5C8h]
  int v122; // [rsp+20h] [rbp-5C8h]
  void **v123; // [rsp+28h] [rbp-5C0h]
  const char *v124; // [rsp+28h] [rbp-5C0h]
  char v125; // [rsp+60h] [rbp-588h]
  std::_Ref_count_base *v126[2]; // [rsp+68h] [rbp-580h] BYREF
  std::_Ref_count_base *v127[2]; // [rsp+78h] [rbp-570h] BYREF
  _BYTE v128[28]; // [rsp+88h] [rbp-560h]
  char v129; // [rsp+A4h] [rbp-544h]
  __int64 v130; // [rsp+A8h] [rbp-540h]
  int v131; // [rsp+B0h] [rbp-538h]
  char v132; // [rsp+B4h] [rbp-534h]
  _QWORD v133[3]; // [rsp+C8h] [rbp-520h] BYREF
  _QWORD v134[2]; // [rsp+E0h] [rbp-508h] BYREF
  _BYTE v135[8]; // [rsp+F0h] [rbp-4F8h] BYREF
  struct _GUID v136; // [rsp+F8h] [rbp-4F0h] BYREF
  _BYTE pvarg[64]; // [rsp+110h] [rbp-4D8h] BYREF
  unsigned __int64 v138; // [rsp+150h] [rbp-498h]
  __int64 v139; // [rsp+158h] [rbp-490h]
  __int64 v140; // [rsp+160h] [rbp-488h]
  __int16 v141; // [rsp+168h] [rbp-480h]
  _OWORD v142[2]; // [rsp+170h] [rbp-478h] BYREF
  int v143[4]; // [rsp+190h] [rbp-458h] BYREF
  __int128 v144; // [rsp+1B0h] [rbp-438h] BYREF
  _BYTE v145[40]; // [rsp+1C0h] [rbp-428h] BYREF
  __int64 v146; // [rsp+1E8h] [rbp-400h]
  unsigned __int64 v147; // [rsp+1F0h] [rbp-3F8h]
  __int16 v148; // [rsp+1F8h] [rbp-3F0h]
  int v149; // [rsp+1FAh] [rbp-3EEh]
  __int16 v150; // [rsp+1FEh] [rbp-3EAh]
  std::_Ref_count_base *v151[2]; // [rsp+210h] [rbp-3D8h] BYREF
  _OWORD Uuid[2]; // [rsp+220h] [rbp-3C8h] BYREF
  char v153; // [rsp+240h] [rbp-3A8h]
  wchar_t v154[4]; // [rsp+250h] [rbp-398h] BYREF
  __int128 v155; // [rsp+258h] [rbp-390h] BYREF
  int v156[4]; // [rsp+268h] [rbp-380h] BYREF
  _OWORD v157[2]; // [rsp+278h] [rbp-370h] BYREF
  _BYTE v158[56]; // [rsp+2A0h] [rbp-348h] BYREF
  _BYTE *v159; // [rsp+2D8h] [rbp-310h]
  wchar_t v160[16]; // [rsp+2E0h] [rbp-308h] BYREF
  char v161; // [rsp+300h] [rbp-2E8h]
  _SYSTEM_INFO SystemInfo; // [rsp+320h] [rbp-2C8h] BYREF
  wchar_t v163[16]; // [rsp+360h] [rbp-288h] BYREF
  char v164; // [rsp+380h] [rbp-268h]
  _BYTE v165[64]; // [rsp+3A0h] [rbp-248h] BYREF
  unsigned __int16 StringUuid[4]; // [rsp+3E0h] [rbp-208h] BYREF
  unsigned __int64 v167; // [rsp+3F8h] [rbp-1F0h]
  char v168; // [rsp+400h] [rbp-1E8h]
  _BYTE v169[64]; // [rsp+410h] [rbp-1D8h] BYREF
  _BYTE v170[64]; // [rsp+450h] [rbp-198h] BYREF
  _BYTE v171[64]; // [rsp+490h] [rbp-158h] BYREF
  wchar_t v172[16]; // [rsp+4D0h] [rbp-118h] BYREF
  wchar_t v173[16]; // [rsp+4F0h] [rbp-F8h] BYREF
  char v174; // [rsp+510h] [rbp-D8h]
  _BYTE v175[8]; // [rsp+520h] [rbp-C8h] BYREF
  _BYTE v176[24]; // [rsp+528h] [rbp-C0h] BYREF
  wchar_t String[16]; // [rsp+540h] [rbp-A8h] BYREF
  char v178; // [rsp+560h] [rbp-88h]
  wil::details::in1diag3 *retaddr; // [rsp+5E8h] [rbp+0h]

  v4 = a3;
  *(_QWORD *)v143 = a3;
  v134[1] = a2;
  v133[2] = a3;
  v7 = 0;
  Data1 = 0;
  v136.Data1 = 0;
  *(_OWORD *)v151 = 0;
  ComputeService::Management::ActiveStateOperation::CreateCancellationToken(a4, v151);
  v9 = _RTDynamicCast_0(
         *(_QWORD *)(*(_QWORD *)a1 + 8LL),
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
  v134[0] = v9;
  v133[0] = a2;
  v133[1] = v134;
  if ( !*(_QWORD *)(a2 + 16) || *(_DWORD *)(a2 + 32) == 1 )
  {
    v125 = 1;
    lambda_7e4873b95fb23f1a585bbbef82530f52_::operator()(v133);
  }
  else
  {
    v125 = 0;
  }
  v159 = 0;
  if ( *(_QWORD *)(a2 + 16) )
  {
    v10 = *(_BYTE *)(ComputeService::Management::MatchResourcePath<0>(&SystemInfo) + 32);
    std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(&SystemInfo);
    if ( v10 )
    {
      *(_QWORD *)v143 = 0;
      LOBYTE(v143[2]) = 0;
      *(int *)((char *)&v143[2] + 1) = 0;
      *(_WORD *)((char *)&v143[3] + 1) = 0;
      HIBYTE(v143[3]) = 0;
      if ( !(unsigned __int8)ComputeService::MarshalUtilities::TryFromDelayed<void,Marshal::Details::DelayedJsonTraits,Schema::VirtualMachines::Resources::Compute::MemoryResizeRequest,>(
                               a2 + 40,
                               v143) )
      {
        LOBYTE(v143[2]) = 0;
        v11 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<unsigned __int64>(
                a2 + 40,
                pvarg,
                v143);
        Marshal::ThrowOnUnmarshalError(v11, 3224830221LL);
        std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&pvarg[8]);
      }
      memset(&SystemInfo, 0, sizeof(SystemInfo));
      GetSystemInfo(&SystemInfo);
      if ( *(__int64 *)v143 < 0 )
        v12 = (float)(int)(v143[0] & 1 | (*(_QWORD *)v143 >> 1)) + (float)(int)(v143[0] & 1 | (*(_QWORD *)v143 >> 1));
      else
        v12 = (float)v143[0];
      v13 = o_ceilf_0((float)(1048576.0 / (float)(int)SystemInfo.dwPageSize) * v12);
      v14 = 0;
      if ( v13 >= 9.223372e18 )
      {
        v13 = v13 - 9.223372e18;
        if ( v13 < 9.223372e18 )
          v14 = 0x8000000000000000uLL;
      }
      v15 = (std::_Ref_count_base *)(v14 + (unsigned int)(int)v13);
      memset(v142, 0, 24);
      ComputeService::Resource::GetResourceInstances(v142, v134[0] + 752LL, 2);
      *(_OWORD *)v126 = 0;
      v16 = std::vector<std::shared_ptr<ComputeService::Resource::IResourceInstance>>::at(v142);
      std::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>(
        v126,
        v16,
        v17,
        v18);
      LODWORD(v127[0]) = 0;
      v127[1] = v15;
      LODWORD(Uuid[0]) = LOBYTE(v143[2]) != 0 ? -1 : 10000;
      memset((char *)Uuid + 4, 0, 20);
      if ( v151[1] )
      {
        *((std::_Ref_count_base **)&Uuid[0] + 1) = v151[0];
        *(std::_Ref_count_base **)&Uuid[1] = v151[1];
        _InterlockedIncrement((volatile signed __int32 *)v151[1] + 3);
      }
      v19 = v126[0];
      v20 = *(void (__fastcall **)(std::_Ref_count_base *, _BYTE *, _BYTE *, _OWORD *, _DWORD))(*(_QWORD *)v126[0] + 48LL);
      Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(
        v165,
        v127);
      v20(v19, v171, v165, Uuid, 0);
      Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(v171);
      Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(v165);
      if ( *(_QWORD *)&Uuid[1] )
        std::_Ref_count_base::_Decwref(*(std::_Ref_count_base **)&Uuid[1]);
      if ( v126[1] )
        std::_Ref_count_base::_Decref(v126[1]);
      v21 = v142;
LABEL_38:
      std::vector<std::shared_ptr<ComputeService::Diagnostics::SystemEntryInner>>::_Tidy(v21);
      goto LABEL_39;
    }
    v22 = *(_BYTE *)(ComputeService::Management::MatchResourcePath<0>(&SystemInfo) + 32);
    std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(&SystemInfo);
    if ( v22 )
    {
      Uuid[0] = 0;
      v23 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Schema::VirtualMachines::Resources::Compute::CpuGroup>(
              a2 + 40,
              v127,
              Uuid);
      Marshal::ThrowOnUnmarshalError(v23, 3224830221LL);
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&v127[1]);
      v144 = 0;
      *(_QWORD *)v145 = 0;
      ComputeService::Resource::GetResourceInstances(&v144, v134[0] + 752LL, 3);
      *(_OWORD *)v127 = 0;
      v24 = std::vector<std::shared_ptr<ComputeService::Resource::IResourceInstance>>::at(&v144);
      std::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>(
        v127,
        v24,
        v25,
        v26);
      *(_OWORD *)v143 = Uuid[0];
      v142[0] = 0x2710u;
      if ( v151[1] )
      {
        *((std::_Ref_count_base **)&v142[0] + 1) = v151[0];
        *(std::_Ref_count_base **)&v142[1] = v151[1];
        _InterlockedIncrement((volatile signed __int32 *)v151[1] + 3);
      }
      memset_0(&SystemInfo, 0, 0x40u);
      v27 = v127[0];
      v28 = *(void (__fastcall **)(std::_Ref_count_base *, _SYSTEM_INFO *, _BYTE *, _OWORD *))(*(_QWORD *)v127[0] + 48LL);
      Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(
        v165,
        v143);
      v28(v27, &SystemInfo, v165, v142);
      Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(v165);
      *(_QWORD *)&v136.Data1 = 0;
      v29 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<unsigned __int64>(
              &SystemInfo,
              v143,
              &v136);
      Marshal::ThrowOnUnmarshalError(v29, 3224830221LL);
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&v143[2]);
      *(_QWORD *)v136.Data4 = 0;
      v31 = SysAllocString(L"CPUGROUP");
      if ( !v31 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x254,
          (unsigned int)"onecore\\vm\\common\\vml\\VmBstr.h",
          (const char *)0x8007000ELL,
          0);
      if ( *(_QWORD *)v136.Data4 )
        SysFreeString(*(BSTR *)v136.Data4);
      *(_QWORD *)v136.Data4 = v31;
      *(_WORD *)pvarg = 21;
      *(_QWORD *)&pvarg[8] = *(_QWORD *)&v136.Data1;
      v126[0] = (std::_Ref_count_base *)pvarg;
      *(_QWORD *)v143 = v136.Data4;
      v136.Data1 = 1;
      v32 = ___InvokeWorkerProcessMethod_UIVmVirtualMachine__KPEAPEAGPEBUtagVARIANT____ZHPEAPEAGPEAU2__Vmwp_ComputeService__YAJAEBUWorkerProcessContext_01_P8IVmVirtualMachine__EAAJKPEAPEAGPEBUtagVARIANT___Z__QEAH__QEAPEAPEAG__QEAPEAU4__Z(
              LODWORD(v134[0]) + 624,
              v30,
              (unsigned int)&v136,
              (unsigned int)v143,
              (__int64)v126);
      if ( v32 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2B3,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualmachineutils.cpp",
          (const char *)(unsigned int)v32,
          v118);
      VariantClear((VARIANTARG *)pvarg);
      Vml::VmBstr::~VmBstr((Vml::VmBstr *)v136.Data4);
      Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(&SystemInfo);
      if ( *(_QWORD *)&v142[1] )
        std::_Ref_count_base::_Decwref(*(std::_Ref_count_base **)&v142[1]);
      if ( v127[1] )
        std::_Ref_count_base::_Decref(v127[1]);
      v21 = &v144;
      goto LABEL_38;
    }
    ComputeService::Management::MatchResourcePath<1>(&SystemInfo);
    if ( LOBYTE(SystemInfo.dwNumberOfProcessors) )
    {
      std::wstring::wstring(pvarg);
      v34 = ComputeService::VirtualMachine::ModifyHelpers::ModifyNetworkSettings(
              v165,
              v134[0],
              a2,
              pvarg,
              v134[0] + 624LL);
      std::function<void (void)>::operator=(v158, v34);
      std::_Func_class<void,>::_Tidy(v165);
      Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)pvarg);
LABEL_204:
      std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(&SystemInfo);
      goto LABEL_39;
    }
    ComputeService::Management::MatchResourcePath<2>(v175);
    if ( v178 )
    {
      std::wstring::wstring(pvarg);
      v35 = std::stoul(String);
      v36 = ComputeService::VirtualMachine::ModifyHelpers::ModifyScsiResourceSettings(v165, v134[0], a2, pvarg, v35);
      std::function<void (void)>::operator=(v158, v36);
      std::_Func_class<void,>::_Tidy(v165);
      Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)pvarg);
LABEL_203:
      std::_Optional_destruct_base<std::array<std::wstring,2>,0>::~_Optional_destruct_base<std::array<std::wstring,2>,0>(v175);
      goto LABEL_204;
    }
    ComputeService::Management::MatchResourcePath<1>(v165);
    if ( v165[32] )
    {
      std::wstring::wstring(pvarg);
      v37 = ComputeService::VirtualMachine::ModifyHelpers::ModifyBatchedScsiResourceSettings(
              v171,
              v134[0],
              a2,
              pvarg,
              0);
      std::function<void (void)>::operator=(v158, v37);
      std::_Func_class<void,>::_Tidy(v171);
      Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)pvarg);
LABEL_202:
      std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(v165);
      goto LABEL_203;
    }
    ComputeService::Management::MatchResourcePath<1>(v171);
    if ( v171[32] )
    {
      std::wstring::wstring(pvarg);
      v38 = ComputeService::VirtualMachine::ModifyHelpers::ModifyMappedPipeSettings(
              (unsigned int)v160,
              v134[0],
              a2,
              (unsigned int)pvarg,
              *v4);
      std::function<void (void)>::operator=(v158, v38);
      std::_Func_class<void,>::_Tidy(v160);
      Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)pvarg);
LABEL_201:
      std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(v171);
      goto LABEL_202;
    }
    v39 = *(_BYTE *)(ComputeService::Management::MatchResourcePath<0>(v160) + 32);
    std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(v160);
    if ( v39 )
    {
      ComputeService::VirtualMachine::ModifyHelpers::Details::ModifyShareWithRollback<Schema::VirtualMachines::Resources::Storage::VirtualSmbShare>((int)v160);
      Data1 = 2;
LABEL_55:
      v41 = v160;
LABEL_58:
      std::function<void (void)>::operator=(v158, v41);
      std::_Func_class<void,>::_Tidy(v160);
      goto LABEL_201;
    }
    v40 = *(_BYTE *)(ComputeService::Management::MatchResourcePath<0>(v160) + 32);
    std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(v160);
    if ( v40 )
    {
      ComputeService::VirtualMachine::ModifyHelpers::Details::ModifyShareWithRollback<Schema::VirtualMachines::Resources::Storage::Plan9Share>((int)v160);
      Data1 = 4;
      goto LABEL_55;
    }
    v42 = *(_BYTE *)(ComputeService::Management::MatchResourcePath<0>(v160) + 32);
    std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(v160);
    if ( v42 )
    {
      v41 = (wchar_t *)ComputeService::VirtualMachine::ModifyHelpers::ModifySharedMemoryRegionSettings(
                         v160,
                         v134[0],
                         a2);
      goto LABEL_58;
    }
    ComputeService::Management::MatchResourcePath<1>(v160);
    if ( v161 )
    {
      v43 = std::stoul(v160);
      if ( v43 > 0xFF )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2DF,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualmachineutils.cpp",
          (const char *)0x80070057LL,
          0);
      LOBYTE(v44) = v43;
      v45 = ComputeService::VirtualMachine::ModifyHelpers::ModifyVPMemDevice(v170, v134[0], a2, v44, 0);
      std::function<void (void)>::operator=(v158, v45);
      std::_Func_class<void,>::_Tidy(v170);
      goto LABEL_200;
    }
    ComputeService::Management::MatchResourcePath<2>(v172);
    if ( v174 )
    {
      v46 = std::stoul(v172);
      v47 = v46;
      if ( v46 > 0xFF )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2E7,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualmachineutils.cpp",
          (const char *)0x80070057LL,
          0);
      v48 = std::stoull(v173);
      LOBYTE(v49) = v47;
      v50 = ComputeService::VirtualMachine::ModifyHelpers::ModifyVPMemMapping((unsigned int)v170, v134[0], a2, v49, v48);
      std::function<void (void)>::operator=(v158, v50);
      std::_Func_class<void,>::_Tidy(v170);
      goto LABEL_199;
    }
    ComputeService::Management::MatchResourcePath<1>(v170);
    if ( v170[32] )
    {
      Uuid[0] = *(_OWORD *)ComputeService::Management::ConvertIdToGuid(v127, v170, &FLEXIO_DEVICE_ID);
      v51 = ComputeService::VirtualMachine::ModifyHelpers::ModifyFlexIovSettings(v163, v134[0], a2, Uuid, 0);
LABEL_75:
      std::function<void (void)>::operator=(v158, v51);
      std::_Func_class<void,>::_Tidy(v163);
LABEL_198:
      std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(v170);
LABEL_199:
      std::_Optional_destruct_base<std::array<std::wstring,2>,0>::~_Optional_destruct_base<std::array<std::wstring,2>,0>(v172);
LABEL_200:
      std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(v160);
      goto LABEL_201;
    }
    v52 = *(_BYTE *)(ComputeService::Management::MatchResourcePath<0>(v163) + 32);
    std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(v163);
    if ( v52 )
    {
      v53 = (_QWORD *)(**(_QWORD **)a1 + 8LL);
      if ( *(_QWORD *)(**(_QWORD **)a1 + 32LL) > 7u )
        v53 = (_QWORD *)*v53;
      v51 = ComputeService::VirtualMachine::ModifyHelpers::ModifyGpuSettings(v163, v53, v134[0], a2, 0);
      goto LABEL_75;
    }
    v54 = *(_BYTE *)(ComputeService::Management::MatchResourcePath<0>(v163) + 32);
    std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(v163);
    if ( v54 )
    {
      v51 = ComputeService::VirtualMachine::ModifyHelpers::ModifyLicensingSettings(v163, v134[0], a2);
      goto LABEL_75;
    }
    ComputeService::Management::MatchResourcePath<1>(v163);
    if ( v164 )
    {
      v55 = std::stoul(v163);
      v56 = v55;
      if ( v55 > 1 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2FE,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualmachineutils.cpp",
          (const char *)0x80070057LL,
          0);
      std::wstring::wstring(&v144);
      *(_WORD *)&v145[16] = 0;
      *(_DWORD *)&v145[20] = 0;
      v57 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Schema::VirtualMachines::Resources::ComPort>(
              a2 + 40,
              pvarg,
              &v144);
      Marshal::ThrowOnUnmarshalError(v57, 3224830221LL);
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&pvarg[8]);
      v58 = *(_DWORD *)&v145[20];
      if ( !*(_DWORD *)&v145[20] )
        v58 = 0x2000;
      *(_QWORD *)v136.Data4 = 0;
      v59 = ComputeService::Vmwp::LookupWorkerProcessDevice(
              (ComputeService::Vmwp *)(v134[0] + 624LL),
              (const struct ComputeService::Vmwp::WorkerProcessContext *)&SERIAL_CONTROLLER_DEVICE_ID,
              &SERIAL_CONTROLLER_DEVICE_ID,
              &GUID_451c9ad2_6fe6_4d07_ab13_45aeff7a4bb3,
              (const struct _GUID *)v136.Data4,
              v123);
      if ( v59 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x30A,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualmachineutils.cpp",
          (const char *)(unsigned int)v59,
          v119);
      v60 = -1;
      v126[0] = (std::_Ref_count_base *)-1LL;
      LOBYTE(v126[1]) = 0;
      if ( (unsigned __int8)ComputeService::VmCommonHelpers::IsSerialPortNamedPipe(&v144) && *(_DWORD *)(a2 + 32) != 1 )
      {
        Uuid[0] = *(_OWORD *)ComputeService::Management::GetComputeSystemGuid(Uuid, **(_QWORD **)a1 + 8LL);
        v61 = ComputeService::VmCommonHelpers::CreateSerialNamedPipe(v127, &v144, v58, Uuid);
        std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>::operator=<std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>,0>(
          v126,
          v61);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v127);
        v7 = (unsigned __int8)v126[1];
        v60 = (__int64)v126[0];
      }
      v62 = v60 - 1;
      LOBYTE(v62) = v56;
      v63 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD))(**(_QWORD **)v136.Data4 + 32LL))(
              *(_QWORD *)v136.Data4,
              v62,
              v60 & -(__int64)((unsigned __int64)(v60 - 1) <= 0xFFFFFFFFFFFFFFFDuLL),
              v7);
      if ( v63 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x31F,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualmachineutils.cpp",
          (const char *)(unsigned int)v63,
          v58);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v126);
      HvsComPtr<IXmlReader>::~HvsComPtr<IXmlReader>(v136.Data4);
      Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)&v144);
      Data1 = v136.Data1;
      v4 = *(__int64 **)v143;
      goto LABEL_197;
    }
    v64 = *(_BYTE *)(ComputeService::Management::MatchResourcePath<0>(v169) + 32);
    std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(v169);
    if ( v64 )
    {
      v65 = ComputeService::VirtualMachine::ModifyHelpers::ModifyIdledProcSettings(v169, v134[0], a2);
      std::function<void (void)>::operator=(v158, v65);
      std::_Func_class<void,>::_Tidy(v169);
LABEL_197:
      std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(v163);
      goto LABEL_198;
    }
    ComputeService::Management::MatchResourcePath<1>(v169);
    if ( v169[32] )
    {
      std::wstring::wstring(pvarg);
      v66 = ComputeService::VirtualMachine::ModifyHelpers::ModifyVirtualPciSettings(v154, v134[0], a2, pvarg, 0);
      std::function<void (void)>::operator=(v158, v66);
      std::_Func_class<void,>::_Tidy(v154);
      Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)pvarg);
LABEL_196:
      std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(v169);
      goto LABEL_197;
    }
    v67 = *(_BYTE *)(ComputeService::Management::MatchResourcePath<0>(v154) + 32);
    std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(v154);
    if ( v67 )
    {
      v136.Data1 = 0;
      v68 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<unsigned long>(
              a2 + 40,
              pvarg,
              &v136);
      Marshal::ThrowOnUnmarshalError(v68, 3224830221LL);
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&pvarg[8]);
      if ( ((*(_QWORD *)(v134[0] + 648LL) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x330,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualmachineutils.cpp",
          (const char *)0x80070032LL,
          0);
      ComputeService::Vmwp::SetCpuFrequencyPowerCap(
        (ComputeService::Vmwp *)(v134[0] + 624LL),
        (const struct ComputeService::Vmwp::WorkerProcessContext *)v136.Data1,
        v69);
      goto LABEL_196;
    }
    if ( !(unsigned int)std::wstring::compare(a2, L"VirtualMachine/ComputeTopology/Processor/CpuThrottlePriority") )
    {
      v136.Data1 = 0;
      v70 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<unsigned long>(
              a2 + 40,
              pvarg,
              &v136);
      Marshal::ThrowOnUnmarshalError(v70, 3224830221LL);
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&pvarg[8]);
      if ( ((*(_QWORD *)(v134[0] + 648LL) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x339,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualmachineutils.cpp",
          (const char *)0x80070032LL,
          0);
      ComputeService::Vmwp::SetCpuThrottlePriority(
        (ComputeService::Vmwp *)(v134[0] + 624LL),
        (const struct ComputeService::Vmwp::WorkerProcessContext *)v136.Data1,
        v71);
      goto LABEL_196;
    }
    if ( !(unsigned int)std::wstring::compare(a2, L"VirtualMachine/ComputeTopology/Processor/CpuBoostPriority") )
    {
      v136.Data1 = 0;
      v72 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<unsigned long>(
              a2 + 40,
              pvarg,
              &v136);
      Marshal::ThrowOnUnmarshalError(v72, 3224830221LL);
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&pvarg[8]);
      if ( ((*(_QWORD *)(v134[0] + 648LL) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x342,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualmachineutils.cpp",
          (const char *)0x80070032LL,
          0);
      ComputeService::Vmwp::SetCpuBoostPriority(
        (ComputeService::Vmwp *)(v134[0] + 624LL),
        (const struct ComputeService::Vmwp::WorkerProcessContext *)v136.Data1,
        v73);
      goto LABEL_196;
    }
    if ( !(unsigned int)std::wstring::compare(a2, L"VirtualMachine/Services/KvpExchange") )
    {
      Schema::VirtualMachines::Resources::KvpExchange::KvpExchange((Schema::VirtualMachines::Resources::KvpExchange *)v154);
      v74 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Schema::VirtualMachines::Resources::KvpExchange>(
              a2 + 40,
              pvarg,
              v154);
      Marshal::ThrowOnUnmarshalError(v74, 3224830221LL);
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&pvarg[8]);
      *(_QWORD *)&v136.Data1 = 0;
      v75 = ComputeService::Vmwp::LookupWorkerProcessDevice(
              (ComputeService::Vmwp *)(v134[0] + 624LL),
              (const struct ComputeService::Vmwp::WorkerProcessContext *)&IC_KVPEXCHANGE_DEVICE_CLASS_ID,
              &IC_KVPEXCHANGE_DEVICE_CLASS_ID,
              &GUID_28e0ea98_099d_462e_b5b7_a03fdd1d8752,
              &v136,
              v123);
      if ( v75 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x34F,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualmachineutils.cpp",
          (const char *)(unsigned int)v75,
          v120);
      v77 = *(_DWORD *)(a2 + 32);
      if ( v77 )
      {
        v78 = v77 - 1;
        if ( v78 )
        {
          if ( v78 != 1 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x37D,
              (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualmachineutils.cpp",
              (const char *)0x80070057LL,
              v120);
          if ( *(_DWORD *)v154 == 1 )
          {
            v80 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)&v136.Data1 + 64LL))(
                    *(_QWORD *)&v136.Data1,
                    1);
            if ( v80 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x36C,
                (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualmachineutils.cpp",
                (const char *)(unsigned int)v80,
                v120);
          }
          else if ( *(_DWORD *)v154 == 2 )
          {
            v79 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)&v136.Data1 + 64LL))(
                    *(_QWORD *)&v136.Data1,
                    0);
            if ( v79 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x367,
                (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualmachineutils.cpp",
                (const char *)(unsigned int)v79,
                v120);
          }
          ComputeService::Management::VirtualMachineUtils::AddKeysFromKvpIC(&v136, v76, &v155);
        }
        ComputeService::Management::VirtualMachineUtils::RemoveKeysFromKvpIC(&v136, v76, v156);
      }
      else
      {
        if ( *(_DWORD *)v154 )
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x359,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualmachineutils.cpp",
            (const char *)0x80070057LL,
            (int)"EnableHostOSInfoKvpItems can only be updated with Update request",
            v124);
        ComputeService::Management::VirtualMachineUtils::AddKeysFromKvpIC(&v136, v76, &v155);
      }
      HvsComPtr<IXmlReader>::~HvsComPtr<IXmlReader>(&v136);
      Schema::VirtualMachines::Resources::KvpExchange::~KvpExchange((Schema::VirtualMachines::Resources::KvpExchange *)v154);
      goto LABEL_196;
    }
    if ( !(unsigned int)std::wstring::compare(a2, L"VirtualMachine/ComputeTopology/Processor/Limits") )
    {
      memset(pvarg, 0, sizeof(pvarg));
      v138 = 0;
      v139 = 0;
      v140 = 0;
      v141 = 0;
      ComputeService::MarshalUtilities::FromDelayedThrow<void,Marshal::Details::DelayedJsonTraits,Schema::VirtualMachines::Resources::Compute::ProcessorLimits,>(
        a2 + 40,
        pvarg);
      v81 = Schema::VirtualMachines::Resources::Compute::ProcessorLimits::ProcessorLimits(
              (Schema::VirtualMachines::Resources::Compute::ProcessorLimits *)&v144,
              (const struct Schema::VirtualMachines::Resources::Compute::ProcessorLimits *)pvarg);
      ComputeService::VirtualMachine::ConfigurationHelpers::ProcessorQosOrDefault(v154, v81);
      if ( LOBYTE(v154[0]) )
      {
        if ( ComputeService::VirtualMachine::CapabilityHelpers::IsHypervisorRootSchedulerEnabled(v82) )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x38A,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualmachineutils.cpp",
            (const char *)0x80070307LL,
            0);
        v84 = ___InvokeWorkerProcessMethod_UIVmVirtualMachine___J_J_JIIIIIH__ZAEA_JAEA_JAEA_JAEAIAEAIAEAIAEAIAEAIAEAH_Vmwp_ComputeService__YAJAEBUWorkerProcessContext_01_P8IVmVirtualMachine__EAAJ_J11IIIIIH_ZAEA_J33AEAI4444AEAH_Z(
                LODWORD(v134[0]) + 624,
                v83,
                (unsigned int)&v155,
                (unsigned int)&v155 + 8,
                (__int64)v156,
                (__int64)&v156[2],
                (__int64)&v156[3],
                (__int64)v157,
                (__int64)v157 + 4,
                (__int64)v157 + 8,
                (__int64)v157 + 12);
        if ( v84 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x396,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualmachineutils.cpp",
            (const char *)(unsigned int)v84,
            v121);
        v85 = v134[0];
        *(_OWORD *)(v134[0] + 1680LL) = v155;
        *(_OWORD *)(v85 + 1696) = *(_OWORD *)v156;
        *(_OWORD *)(v85 + 1712) = v157[0];
      }
      goto LABEL_196;
    }
    ComputeService::Management::MatchResourcePath<1>(StringUuid);
    if ( !v168 )
    {
      if ( (unsigned int)std::wstring::compare(a2, L"VirtualMachine/StopOnReset") )
      {
        ComputeService::Management::MatchResourcePath<1>(v154);
        if ( LOBYTE(v156[2]) )
        {
          v93 = std::stoul(v154);
          ComputeService::Vmwp::SetResourceAllocationId(
            (ComputeService::Vmwp *)(v134[0] + 624LL),
            (const struct ComputeService::Vmwp::WorkerProcessContext *)v93,
            v94);
        }
        else
        {
          ComputeService::Management::MatchResourcePath<1>(Uuid);
          if ( v153 )
          {
            v95 = std::stoul((wchar_t *)Uuid);
            ComputeService::Vmwp::SetResourceMonitoringId(
              (ComputeService::Vmwp *)(v134[0] + 624LL),
              (const struct ComputeService::Vmwp::WorkerProcessContext *)v95,
              v96);
          }
          else if ( (unsigned int)std::wstring::compare(a2, L"VirtualMachine/ComputeTopology/Processor/CpuidResult") )
          {
            if ( (unsigned int)std::wstring::compare(a2, L"VirtualMachine/ComputeTopology/Memory/PrepareForMigration") )
            {
              if ( (unsigned int)std::wstring::compare(a2, L"VirtualMachine/ComputeTopology/Memory/GuestAccessTracking") )
              {
                ComputeService::Management::MatchResourcePath<1>(pvarg);
                if ( !pvarg[32] )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x428,
                    (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualmachineutils.cpp",
                    (const char *)0x80070057LL,
                    0);
                v136.Data1 = std::stoul((wchar_t *)pvarg);
                if ( !v136.Data1 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x41C,
                    (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualmachineutils.cpp",
                    (const char *)0x80070057LL,
                    0);
                if ( ((*(_QWORD *)(v134[0] + 648LL) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x41E,
                    (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualmachineutils.cpp",
                    (const char *)0x80070032LL,
                    0);
                v113 = ___InvokeWorkerProcessMethod_UIVmVirtualMachine__K__ZAEAK_Vmwp_ComputeService__YAJAEBUWorkerProcessContext_01_PEAUIUnknown__P8IVmVirtualMachine__EAAJK_ZAEAK_Z(
                         retaddr,
                         *(_QWORD *)(v134[0] + 640LL),
                         v112,
                         &v136);
                if ( v113 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x424,
                    (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualmachineutils.cpp",
                    (const char *)(unsigned int)v113,
                    0);
                std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(pvarg);
              }
              else
              {
                if ( ((*(_QWORD *)(v134[0] + 648LL) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x3F4,
                    (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualmachineutils.cpp",
                    (const char *)0x80070032LL,
                    0);
                v104 = *(_DWORD *)(a2 + 32);
                if ( v104 )
                {
                  v105 = v104 - 1;
                  if ( v105 )
                  {
                    if ( v105 != 1 )
                      wil::details::in1diag3::Throw_Hr(
                        retaddr,
                        (void *)0x413,
                        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualmachineutils.cpp",
                        (const char *)0x80070057LL,
                        0);
                    LODWORD(v142[0]) = 0;
                    *((_QWORD *)&v142[0] + 1) = 0;
                    *(_QWORD *)&v142[1] = 0;
                    v106 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Schema::Resources::Memory::GuestMemoryAccessTrackingQueryOperation>(
                             a2 + 40,
                             pvarg,
                             v142);
                    Marshal::ThrowOnUnmarshalError(v106, 3224830221LL);
                    std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&pvarg[8]);
                    memset(pvarg, 0, 40);
                    v138 = vmstd::optional<Schema::Resources::Memory::GuestMemoryAccessTrackingRegisterOperation>::optional<Schema::Resources::Memory::GuestMemoryAccessTrackingRegisterOperation>(pvarg).m128_u64[1];
                    v139 = 0;
                    *(_OWORD *)&pvarg[40] = v142[0];
                    *(_QWORD *)&pvarg[56] = *(_QWORD *)&v142[1];
                    LOBYTE(v138) = 1;
                    v107 = Schema::Resources::Memory::GuestMemoryAccessTrackingOperation::GuestMemoryAccessTrackingOperation(
                             (Schema::Resources::Memory::GuestMemoryAccessTrackingOperation *)&v144,
                             (const struct Schema::Resources::Memory::GuestMemoryAccessTrackingOperation *)pvarg);
                    ComputeService::Vmwp::ModifyGuestMemoryAccessTracking(v134[0] + 624LL, v107, 0);
                  }
                  else
                  {
                    v135[0] = 0;
                    v108 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Schema::Resources::Memory::GuestMemoryAccessTrackingUnregisterOperation>(
                             a2 + 40,
                             pvarg,
                             v135);
                    Marshal::ThrowOnUnmarshalError(v108, 3224830221LL);
                    std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&pvarg[8]);
                    memset(pvarg, 0, 40);
                    v138 = vmstd::optional<Schema::Resources::Memory::GuestMemoryAccessTrackingRegisterOperation>::optional<Schema::Resources::Memory::GuestMemoryAccessTrackingRegisterOperation>(pvarg).m128_u64[1];
                    memset(&pvarg[40], 0, 24);
                    LOBYTE(v138) = 0;
                    v139 = 256;
                    v109 = Schema::Resources::Memory::GuestMemoryAccessTrackingOperation::GuestMemoryAccessTrackingOperation(
                             (Schema::Resources::Memory::GuestMemoryAccessTrackingOperation *)&v144,
                             (const struct Schema::Resources::Memory::GuestMemoryAccessTrackingOperation *)pvarg);
                    ComputeService::Vmwp::ModifyGuestMemoryAccessTracking(v134[0] + 624LL, v109, 0);
                  }
                }
                else
                {
                  Schema::Resources::Memory::GuestMemoryAccessTrackingRegisterOperation::GuestMemoryAccessTrackingRegisterOperation((Schema::Resources::Memory::GuestMemoryAccessTrackingRegisterOperation *)pvarg);
                  v110 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Schema::Resources::Memory::GuestMemoryAccessTrackingRegisterOperation>(
                           a2 + 40,
                           &v144,
                           pvarg);
                  Marshal::ThrowOnUnmarshalError(v110, 3224830221LL);
                  std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy((char *)&v144 + 8);
                  v144 = 0;
                  memset(v145, 0, 24);
                  v147 = vmstd::optional<Schema::Resources::Memory::GuestMemoryAccessTrackingRegisterOperation>::optional<Schema::Resources::Memory::GuestMemoryAccessTrackingRegisterOperation>(&v144).m128_u64[1];
                  *(_OWORD *)&v145[24] = 0u;
                  v146 = 0;
                  LOBYTE(v147) = 0;
                  v148 = 0;
                  v149 = 0;
                  v150 = 0;
                  vmstd::optional<Schema::Resources::Memory::GuestMemoryAccessTrackingRegisterOperation>::operator=<Schema::Resources::Memory::GuestMemoryAccessTrackingRegisterOperation &,void>(
                    &v144,
                    pvarg);
                  v111 = Schema::Resources::Memory::GuestMemoryAccessTrackingOperation::GuestMemoryAccessTrackingOperation(
                           (Schema::Resources::Memory::GuestMemoryAccessTrackingOperation *)v127,
                           (const struct Schema::Resources::Memory::GuestMemoryAccessTrackingOperation *)&v144);
                  ComputeService::Vmwp::ModifyGuestMemoryAccessTracking(v134[0] + 624LL, v111, 0);
                  std::vector<Schema::Containers::Definition::InterfaceClass>::_Tidy((char *)&v144 + 8);
                }
                std::vector<Schema::Containers::Definition::InterfaceClass>::_Tidy(&pvarg[8]);
              }
            }
            else
            {
              v144 = 0;
              *(_QWORD *)v145 = 0;
              ComputeService::Resource::GetResourceInstances(&v144, v134[0] + 752LL, 2);
              *(_OWORD *)v127 = 0;
              v101 = std::vector<std::shared_ptr<ComputeService::Resource::IResourceInstance>>::at(&v144);
              std::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>(
                v127,
                v101,
                v102,
                v103);
              v142[0] = 0x2710u;
              if ( v151[1] )
              {
                *((std::_Ref_count_base **)&v142[0] + 1) = v151[0];
                *(std::_Ref_count_base **)&v142[1] = v151[1];
                _InterlockedIncrement((volatile signed __int32 *)v151[1] + 3);
              }
              memset_0(pvarg, 0, sizeof(pvarg));
              (*(void (__fastcall **)(std::_Ref_count_base *, _BYTE *, __int64, _OWORD *, _DWORD))(*(_QWORD *)v127[0]
                                                                                                 + 48LL))(
                v127[0],
                pvarg,
                a2 + 40,
                v142,
                0);
              Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(pvarg);
              if ( *(_QWORD *)&v142[1] )
                std::_Ref_count_base::_Decwref(*(std::_Ref_count_base **)&v142[1]);
              if ( v127[1] )
                std::_Ref_count_base::_Decref(v127[1]);
              std::vector<std::shared_ptr<ComputeService::Diagnostics::SystemEntryInner>>::_Tidy(&v144);
            }
          }
          else
          {
            v97 = *(_DWORD *)(a2 + 32);
            if ( v97 )
            {
              if ( v97 != 1 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x3E3,
                  (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualmachineutils.cpp",
                  (const char *)0x80070057LL,
                  0);
              *(_QWORD *)v143 = 0;
              LOBYTE(v143[2]) = 0;
              v98 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Schema::Resources::Processor::CpuidResultUnregisterOperation>(
                      a2 + 40,
                      pvarg,
                      v143);
              Marshal::ThrowOnUnmarshalError(v98, 3224830221LL);
              std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&pvarg[8]);
              memset(pvarg, 0, 44);
              v144 = 0u;
              memset(v145, 0, 29);
              *(_QWORD *)&v145[32] = *(_QWORD *)v143;
              LODWORD(v146) = v143[2];
              BYTE4(v146) = 1;
              v99 = (std::_Ref_count_base **)&v144;
            }
            else
            {
              v144 = 0u;
              memset(v145, 0, 26);
              v100 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Schema::Resources::Processor::CpuidResultRegisterOperation>(
                       a2 + 40,
                       pvarg,
                       &v144);
              Marshal::ThrowOnUnmarshalError(v100, 3224830221LL);
              std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&pvarg[8]);
              *(_DWORD *)&pvarg[60] = 0;
              *(_QWORD *)&pvarg[48] = 0;
              pvarg[56] = 0;
              *(_WORD *)&pvarg[57] = 0;
              pvarg[59] = 0;
              *(_OWORD *)v127 = v144;
              *(_OWORD *)v128 = *(_OWORD *)v145;
              *(_OWORD *)&v128[12] = *(_OWORD *)&v145[12];
              v129 = 1;
              v130 = 0;
              v131 = 0;
              v132 = 0;
              v99 = v127;
            }
            ComputeService::Vmwp::SetCpuidResult(v134[0] + 624LL, v99);
          }
          std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(Uuid);
        }
        std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(v154);
      }
      else
      {
        if ( *(_QWORD *)(v134[0] + 136LL) )
        {
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0x3AD,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualmachineutils.cpp",
            (const char *)0x80070032LL,
            0);
          v136.Data1 = 5;
          std::pair<std::wstring,enum Marshal::UnmarshalError>::pair<std::wstring,enum Marshal::UnmarshalError>(
            v154,
            L"GuestConnection",
            &v136);
          ComputeService::Reporting::FormatUnMarshalError(pvarg, v154);
          ComputeService::Reporting::LogAndThrowComputeError<std::wstring>(-2147024846);
        }
        v135[0] = 0;
        v89 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<bool>(a2 + 40, pvarg, v135);
        Marshal::ThrowOnUnmarshalError(v89, 3224830221LL);
        std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&pvarg[8]);
        *(_QWORD *)v136.Data4 = 0;
        v91 = SysAllocString(L"STOPONRESET");
        if ( !v91 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x254,
            (unsigned int)"onecore\\vm\\common\\vml\\VmBstr.h",
            (const char *)0x8007000ELL,
            0);
        if ( *(_QWORD *)v136.Data4 )
          SysFreeString(*(BSTR *)v136.Data4);
        *(_QWORD *)v136.Data4 = v91;
        LOWORD(v144) = 11;
        if ( v135[0] )
          WORD4(v144) = -1;
        else
          WORD4(v144) = 0;
        *(_QWORD *)v143 = &v144;
        v126[0] = (std::_Ref_count_base *)v136.Data4;
        v136.Data1 = 1;
        v92 = ___InvokeWorkerProcessMethod_UIVmVirtualMachine__KPEAPEAGPEBUtagVARIANT____ZHPEAPEAGPEAU2__Vmwp_ComputeService__YAJAEBUWorkerProcessContext_01_P8IVmVirtualMachine__EAAJKPEAPEAGPEBUtagVARIANT___Z__QEAH__QEAPEAPEAG__QEAPEAU4__Z(
                LODWORD(v134[0]) + 624,
                v90,
                (unsigned int)&v136,
                (unsigned int)v126,
                (__int64)v143);
        if ( v92 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x3BA,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualmachineutils.cpp",
            (const char *)(unsigned int)v92,
            v122);
        VariantClear((VARIANTARG *)&v144);
        Vml::VmBstr::~VmBstr((Vml::VmBstr *)v136.Data4);
      }
      goto LABEL_195;
    }
    Uuid[0] = 0;
    if ( v167 <= 7 )
    {
      v86 = StringUuid;
    }
    else
    {
      v86 = *(unsigned __int16 **)StringUuid;
      if ( !*(_QWORD *)StringUuid )
        goto LABEL_137;
    }
    if ( !UuidFromStringW(v86, (UUID *)Uuid) )
    {
      v87 = 0;
      goto LABEL_139;
    }
LABEL_137:
    v87 = 1;
LABEL_139:
    if ( v87 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x39F,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualmachineutils.cpp",
        (const char *)0x80070057LL,
        0);
    v88 = ComputeService::VirtualMachine::ModifyHelpers::ModifyHvSocketServiceEntry(v154, v134[0], a2, Uuid, 0);
    std::function<void (void)>::operator=(v158, v88);
    std::_Func_class<void,>::_Tidy(v154);
LABEL_195:
    std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(StringUuid);
    goto LABEL_196;
  }
LABEL_39:
  if ( !v125 )
  {
    try
    {
      lambda_7e4873b95fb23f1a585bbbef82530f52_::operator()(v133);
    }
    catch ( ... )
    {
      if ( v159 )
      {
        try
        {
          std::_Func_class<void,std::wstring const &,ComputeService::Management::ComputeSystemNotificationInfo_2 const &>::operator()();
        }
        catch ( ... )
        {
          wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0x43A,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualmachineutils.cpp",
            v117);
        }
      }
      throw;
    }
  }
  v33 = 0;
  if ( *(_QWORD *)(v134[0] + 136LL) )
  {
    Data1 |= 1u;
    if ( *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v134[0] + 168LL) + 48LL))(
                      *(_QWORD *)(v134[0] + 168LL),
                      v175) < 4u )
      v33 = 1;
  }
  if ( (Data1 & 1) != 0 )
    Compute::Containers::BridgeMessage::GcsCapabilities::~GcsCapabilities((Compute::Containers::BridgeMessage::GcsCapabilities *)v176);
  if ( v33 )
  {
    *(_QWORD *)v136.Data4 = 0;
    if ( v134[0] )
      v114 = v134[0] + 128LL;
    else
      v114 = 0;
    wil::AcquireSRWLockExclusive(v136.Data4, v114);
    v115 = v134[0];
    if ( !*(_QWORD *)(v134[0] + 200LL) )
    {
      if ( *(_QWORD *)(v134[0] + 216LL) == *(_QWORD *)(v134[0] + 224LL) )
      {
        std::vector<Schema::Requests::System::ModifySettingRequest>::_Emplace_reallocate<Schema::Requests::System::ModifySettingRequest const &>(
          v134[0] + 208LL,
          *(_QWORD *)(v134[0] + 216LL),
          a2);
      }
      else
      {
        Schema::Requests::System::ModifySettingRequest::ModifySettingRequest(
          *(Schema::Requests::System::ModifySettingRequest **)(v134[0] + 216LL),
          (const struct Schema::Requests::System::ModifySettingRequest *)a2);
        *(_QWORD *)(v115 + 216) += 168LL;
      }
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v136.Data4);
  }
  if ( v159 )
  {
    v116 = v158;
    LOBYTE(v116) = v159 != v158;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v159 + 32LL))(v159, v116);
    v159 = 0;
  }
  if ( v151[1] )
    std::_Ref_count_base::_Decwref(v151[1]);
  Schema::Requests::System::ModifySettingRequest::~ModifySettingRequest((Schema::Requests::System::ModifySettingRequest *)a2);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v4);
}

```

## disassembly

```asm
0x14002aee4  mov     r11, rsp
0x14002aee7  push    rbx
0x14002aee8  push    rsi
0x14002aee9  push    rdi
0x14002aeea  push    r12
0x14002aeec  push    r13
0x14002aeee  push    r15
0x14002aef0  sub     rsp, 5B8h
0x14002aef7  mov     rax, cs:__security_cookie
0x14002aefe  xor     rax, rsp
0x14002af01  mov     [rsp+5E8h+var_48], rax
0x14002af09  mov     r12, r8
0x14002af0c  mov     [r11-458h], r8
0x14002af13  mov     rsi, rdx
0x14002af16  mov     r13, rcx
0x14002af19  mov     [r11-500h], rdx
0x14002af20  mov     [r11-510h], r8
0x14002af27  xor     edi, edi
0x14002af29  mov     r15d, edi
0x14002af2c  mov     [rsp+5E8h+var_4F0.Data1], edi
0x14002af33  xorps   xmm0, xmm0
0x14002af36  movups  xmmword ptr [rsp+5E8h+var_3D8], xmm0
0x14002af3e  lea     rdx, [r11-3D8h]
0x14002af45  mov     rcx, r9
0x14002af48  call    ?CreateCancellationToken@ActiveStateOperation@Management@ComputeService@@QEAA?AVCancellationToken@23@XZ; ComputeService::Management::ActiveStateOperation::CreateCancellationToken(void)
0x14002af4d  nop
0x14002af4e  mov     rcx, [r13+0]
0x14002af52  mov     dword ptr [rsp+5E8h+var_5C8], edi; int
0x14002af56  lea     r9, ??_R0?AUVirtualMachineState@Management@ComputeService@@@8; ComputeService::Management::VirtualMachineState `RTTI Type Descriptor'
0x14002af5d  lea     r8, ??_R0?AUComputeSystemState@Management@ComputeService@@@8; ComputeService::Management::ComputeSystemState `RTTI Type Descriptor'
0x14002af64  xor     edx, edx
0x14002af66  mov     rcx, [rcx+8]
0x14002af6a  call    __RTDynamicCast_0
0x14002af6f  mov     rcx, [rsp+5E8h]; this
0x14002af77  test    rax, rax
0x14002af7a  jnz     short loc_14002AF92
0x14002af7c  mov     r9d, 80004001h; char *
0x14002af82  lea     r8, aOnecoreVmCompu_31; "onecore\\vm\\compute\\management\\compu"...
0x14002af89  lea     edx, [rdi+5Dh]; void *
0x14002af8c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14002af92  mov     [rsp+5E8h+var_508], rax
0x14002af9a  mov     [rsp+5E8h+var_520], rsi
0x14002afa2  lea     rax, [rsp+5E8h+var_508]
0x14002afaa  mov     [rsp+5E8h+var_518], rax
0x14002afb2  cmp     [rsi+10h], rdi
0x14002afb6  jz      short loc_14002AFC5
0x14002afb8  cmp     dword ptr [rsi+20h], 1
0x14002afbc  jz      short loc_14002AFC5
0x14002afbe  mov     [rsp+5E8h+var_588], dil
0x14002afc3  jmp     short loc_14002AFD7
0x14002afc5  mov     [rsp+5E8h+var_588], 1
0x14002afca  lea     rcx, [rsp+5E8h+var_520]
0x14002afd2  call    _lambda_7e4873b95fb23f1a585bbbef82530f52___operator__
0x14002afd7  mov     [rsp+5E8h+var_310], rdi
0x14002afdf  cmp     [rsi+10h], rdi
0x14002afe3  jz      loc_14002B5B2
0x14002afe9  lea     r8, qword_1403DC7F8
0x14002aff0  mov     rdx, rsi
0x14002aff3  lea     rcx, [rsp+5E8h+SystemInfo]; void *
0x14002affb  call    ??$MatchResourcePath@$0A@@Management@ComputeService@@YA?AV?$optional@V?$array@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@AEBV?$basic_regex@GV?$regex_traits@G@std@@@3@@Z; ComputeService::Management::MatchResourcePath<0>(std::wstring const &,std::basic_regex<ushort,std::regex_traits<ushort>> const &)
0x14002b000  mov     bl, [rax+20h]
0x14002b003  lea     rcx, [rsp+5E8h+SystemInfo]
0x14002b00b  call    ??1?$_Optional_destruct_base@V?$array@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(void)
0x14002b010  test    bl, bl
0x14002b012  jz      loc_14002B290
0x14002b018  mov     qword ptr [rsp+5E8h+var_458], rdi
0x14002b020  mov     byte ptr [rsp+5E8h+var_458+8], dil
0x14002b028  xor     eax, eax
0x14002b02a  mov     [rsp+5E8h+var_458+9], eax
0x14002b031  mov     word ptr [rsp+5E8h+var_458+0Dh], ax
0x14002b039  mov     byte ptr [rsp+5E8h+var_458+0Fh], al
0x14002b040  lea     rdx, [rsp+5E8h+var_458]
0x14002b048  lea     rcx, [rsi+28h]
0x14002b04c  call    ??$TryFromDelayed@XUDelayedJsonTraits@Details@Marshal@@UMemoryResizeRequest@Compute@Resources@VirtualMachines@Schema@@$$V@MarshalUtilities@ComputeService@@YA_NAEBV?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@PEAUMemoryResizeRequest@Compute@Resources@VirtualMachines@Schema@@@Z; ComputeService::MarshalUtilities::TryFromDelayed<void,Marshal::Details::DelayedJsonTraits,Schema::VirtualMachines::Resources::Compute::MemoryResizeRequest,>(Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits> const &,Schema::VirtualMachines::Resources::Compute::MemoryResizeRequest *)
0x14002b051  test    al, al
0x14002b053  jnz     short loc_14002B092
0x14002b055  mov     byte ptr [rsp+5E8h+var_458+8], dil
0x14002b05d  lea     r8, [rsp+5E8h+var_458]
0x14002b065  lea     rdx, [rsp+5E8h+pvarg]
0x14002b06d  lea     rcx, [rsi+28h]
0x14002b071  call    ??$Unmarshal@_K@?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEBA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@PEA_K@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<unsigned __int64>(unsigned __int64 *)
0x14002b076  nop
0x14002b077  mov     edx, 0C037010Dh
0x14002b07c  mov     rcx, rax
0x14002b07f  call    ?ThrowOnUnmarshalError@Marshal@@YAXAEBU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@J@Z; Marshal::ThrowOnUnmarshalError(std::pair<bool,std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>> const &,long)
0x14002b084  nop
0x14002b085  lea     rcx, [rsp+5E8h+pvarg+8]
0x14002b08d  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x14002b092  xorps   xmm0, xmm0
0x14002b095  movups  xmmword ptr [rsp+5E8h+SystemInfo], xmm0
0x14002b09d  movups  xmmword ptr [rsp+5E8h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x14002b0a5  movups  xmmword ptr [rsp+5E8h+SystemInfo.dwNumberOfProcessors], xmm0
0x14002b0ad  lea     rcx, [rsp+5E8h+SystemInfo]; lpSystemInfo
0x14002b0b5  call    cs:__imp_GetSystemInfo
0x14002b0bc  nop     dword ptr [rax+rax+00h]
0x14002b0c1  mov     eax, [rsp+5E8h+SystemInfo.dwPageSize]
0x14002b0c8  xorps   xmm0, xmm0
0x14002b0cb  cvtsi2ss xmm0, rax
0x14002b0d0  movss   xmm1, cs:__real@49800000
0x14002b0d8  divss   xmm1, xmm0
0x14002b0dc  mov     rcx, qword ptr [rsp+5E8h+var_458]
0x14002b0e4  xorps   xmm0, xmm0
0x14002b0e7  test    rcx, rcx
0x14002b0ea  js      short loc_14002B0F3
0x14002b0ec  cvtsi2ss xmm0, rcx
0x14002b0f1  jmp     short loc_14002B108
0x14002b0f3  mov     rax, rcx
0x14002b0f6  shr     rax, 1
0x14002b0f9  and     ecx, 1
0x14002b0fc  or      rax, rcx
0x14002b0ff  cvtsi2ss xmm0, rax
0x14002b104  addss   xmm0, xmm0
0x14002b108  mulss   xmm1, xmm0
0x14002b10c  movaps  xmm0, xmm1; X
0x14002b10f  call    _o_ceilf_0
0x14002b114  xor     eax, eax
0x14002b116  movss   xmm1, cs:__real@5f000000
0x14002b11e  comiss  xmm0, xmm1
0x14002b121  jb      short loc_14002B139
0x14002b123  subss   xmm0, xmm1
0x14002b127  comiss  xmm0, xmm1
0x14002b12a  jnb     short loc_14002B139
0x14002b12c  mov     rcx, 8000000000000000h
0x14002b136  mov     rax, rcx
0x14002b139  cvttss2si rbx, xmm0
0x14002b13e  add     rbx, rax
0x14002b141  xorps   xmm0, xmm0
0x14002b144  xor     eax, eax
0x14002b146  movups  [rsp+5E8h+var_478], xmm0
0x14002b14e  mov     [rsp+5E8h+var_468], rax
0x14002b156  mov     rdx, [rsp+5E8h+var_508]
0x14002b15e  add     rdx, 2F0h
0x14002b165  lea     r8d, [rax+2]
0x14002b169  lea     rcx, [rsp+5E8h+var_478]
0x14002b171  call    ?GetResourceInstances@Resource@ComputeService@@YA?AV?$vector@V?$shared_ptr@VIResourceInstance@Resource@ComputeService@@@std@@V?$allocator@V?$shared_ptr@VIResourceInstance@Resource@ComputeService@@@std@@@2@@std@@AEBUResourceState@12@W4ResourceType@12@@Z; ComputeService::Resource::GetResourceInstances(ComputeService::Resource::ResourceState const &,ComputeService::Resource::ResourceType)
0x14002b176  nop
0x14002b177  xorps   xmm0, xmm0
0x14002b17a  movups  xmmword ptr [rsp+5E8h+var_580], xmm0
0x14002b17f  lea     rcx, [rsp+5E8h+var_478]
0x14002b187  call    ?at@?$vector@V?$shared_ptr@VIResourceInstance@Resource@ComputeService@@@std@@V?$allocator@V?$shared_ptr@VIResourceInstance@Resource@ComputeService@@@std@@@2@@std@@QEAAAEAV?$shared_ptr@VIResourceInstance@Resource@ComputeService@@@2@_K@Z; std::vector<std::shared_ptr<ComputeService::Resource::IResourceInstance>>::at(unsigned __int64)
0x14002b18c  mov     rdx, rax
0x14002b18f  lea     rcx, [rsp+5E8h+var_580]
0x14002b194  call    ??0?$shared_ptr@VINetworkResourceAllocator@Resource@ComputeService@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>(std::shared_ptr<ComputeService::Resource::INetworkResourceAllocator> const &)
0x14002b199  nop
0x14002b19a  mov     dword ptr [rsp+5E8h+var_570], edi
0x14002b19e  mov     [rsp+5E8h+var_570+8], rbx
0x14002b1a6  mov     al, byte ptr [rsp+5E8h+var_458+8]
0x14002b1ad  neg     al
0x14002b1af  sbb     ecx, ecx
0x14002b1b1  and     ecx, 0FFFFD8EFh
0x14002b1b7  add     ecx, 2710h
0x14002b1bd  mov     [rsp+5E8h+Uuid.Data1], ecx
0x14002b1c4  xor     eax, eax
0x14002b1c6  mov     dword ptr [rsp+5E8h+Uuid.Data2], eax
0x14002b1cd  xorps   xmm0, xmm0
0x14002b1d0  movdqu  xmmword ptr [rsp+5E8h+Uuid.Data4], xmm0
0x14002b1d9  mov     rcx, [rsp+5E8h+var_3D8+8]
0x14002b1e1  test    rcx, rcx
0x14002b1e4  jz      short loc_14002B202
0x14002b1e6  mov     rax, [rsp+5E8h+var_3D8]
0x14002b1ee  mov     qword ptr [rsp+5E8h+Uuid.Data4], rax
0x14002b1f6  mov     [rsp+230h], rcx
0x14002b1fe  lock inc dword ptr [rcx+0Ch]
0x14002b202  mov     rdi, [rsp+5E8h+var_580]
0x14002b207  mov     rax, [rdi]
0x14002b20a  mov     rbx, [rax+30h]
0x14002b20e  lea     rdx, [rsp+5E8h+var_570]
0x14002b213  lea     rcx, [rsp+5E8h+var_248]
0x14002b21b  call    ??$?0AEAUVmMemoryModificationRequest@Memory@Resources@Schema@@@?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAA@AEAUVmMemoryModificationRequest@Memory@Resources@Schema@@@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(Schema::Resources::Memory::VmMemoryModificationRequest &)
0x14002b220  nop
0x14002b221  lea     r9, [rsp+5E8h+Uuid]
0x14002b229  lea     r8, [rsp+5E8h+var_248]
0x14002b231  lea     rdx, [rsp+5E8h+var_158]
0x14002b239  mov     rcx, rdi
0x14002b23c  mov     rax, rbx
0x14002b23f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b244  lea     rcx, [rsp+5E8h+var_158]
0x14002b24c  call    ??1?$DelayedBase@UMemoryTopology@System@Responses@Schema@@UDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAA@XZ; Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(void)
0x14002b251  nop
0x14002b252  lea     rcx, [rsp+5E8h+var_248]
0x14002b25a  call    ??1?$DelayedBase@UMemoryTopology@System@Responses@Schema@@UDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAA@XZ; Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(void)
0x14002b25f  nop
0x14002b260  mov     rcx, [rsp+230h]; this
0x14002b268  test    rcx, rcx
0x14002b26b  jz      short loc_14002B273
0x14002b26d  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x14002b272  nop
0x14002b273  mov     rcx, [rsp+5E8h+var_580+8]; this
0x14002b278  test    rcx, rcx
0x14002b27b  jz      short loc_14002B283
0x14002b27d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14002b282  nop
0x14002b283  lea     rcx, [rsp+5E8h+var_478]
0x14002b28b  jmp     loc_14002B5AD
0x14002b290  lea     r8, qword_1403DCAE0
0x14002b297  mov     rdx, rsi
0x14002b29a  lea     rcx, [rsp+5E8h+SystemInfo]; void *
0x14002b2a2  call    ??$MatchResourcePath@$0A@@Management@ComputeService@@YA?AV?$optional@V?$array@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@AEBV?$basic_regex@GV?$regex_traits@G@std@@@3@@Z; ComputeService::Management::MatchResourcePath<0>(std::wstring const &,std::basic_regex<ushort,std::regex_traits<ushort>> const &)
0x14002b2a7  mov     bl, [rax+20h]
0x14002b2aa  lea     rcx, [rsp+5E8h+SystemInfo]
0x14002b2b2  call    ??1?$_Optional_destruct_base@V?$array@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(void)
0x14002b2b7  test    bl, bl
0x14002b2b9  jz      loc_14002B60C
0x14002b2bf  xorps   xmm0, xmm0
0x14002b2c2  movups  xmmword ptr [rsp+5E8h+Uuid.Data1], xmm0
0x14002b2ca  lea     rcx, [rsi+28h]
0x14002b2ce  lea     r8, [rsp+5E8h+Uuid]
0x14002b2d6  lea     rdx, [rsp+5E8h+var_570]
0x14002b2db  call    ??$Unmarshal@UCpuGroup@Compute@Resources@VirtualMachines@Schema@@@?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEBA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@PEAUCpuGroup@Compute@Resources@VirtualMachines@Schema@@@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Schema::VirtualMachines::Resources::Compute::CpuGroup>(Schema::VirtualMachines::Resources::Compute::CpuGroup *)
0x14002b2e0  nop
0x14002b2e1  mov     edx, 0C037010Dh
0x14002b2e6  mov     rcx, rax
0x14002b2e9  call    ?ThrowOnUnmarshalError@Marshal@@YAXAEBU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@J@Z; Marshal::ThrowOnUnmarshalError(std::pair<bool,std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>> const &,long)
0x14002b2ee  nop
0x14002b2ef  lea     rcx, [rsp+5E8h+var_570+8]
0x14002b2f7  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x14002b2fc  xorps   xmm0, xmm0
0x14002b2ff  xor     eax, eax
0x14002b301  movups  xmmword ptr [rsp+5E8h+var_438], xmm0
0x14002b309  mov     qword ptr [rsp+5E8h+var_438+10h], rax
0x14002b311  mov     rdx, [rsp+5E8h+var_508]
0x14002b319  add     rdx, 2F0h
0x14002b320  lea     r8d, [rax+3]
0x14002b324  lea     rcx, [rsp+5E8h+var_438]
0x14002b32c  call    ?GetResourceInstances@Resource@ComputeService@@YA?AV?$vector@V?$shared_ptr@VIResourceInstance@Resource@ComputeService@@@std@@V?$allocator@V?$shared_ptr@VIResourceInstance@Resource@ComputeService@@@std@@@2@@std@@AEBUResourceState@12@W4ResourceType@12@@Z; ComputeService::Resource::GetResourceInstances(ComputeService::Resource::ResourceState const &,ComputeService::Resource::ResourceType)
0x14002b331  nop
0x14002b332  xorps   xmm0, xmm0
0x14002b335  movups  xmmword ptr [rsp+5E8h+var_570], xmm0
0x14002b33a  lea     rcx, [rsp+5E8h+var_438]
0x14002b342  call    ?at@?$vector@V?$shared_ptr@VIResourceInstance@Resource@ComputeService@@@std@@V?$allocator@V?$shared_ptr@VIResourceInstance@Resource@ComputeService@@@std@@@2@@std@@QEAAAEAV?$shared_ptr@VIResourceInstance@Resource@ComputeService@@@2@_K@Z; std::vector<std::shared_ptr<ComputeService::Resource::IResourceInstance>>::at(unsigned __int64)
0x14002b347  mov     rdx, rax
0x14002b34a  lea     rcx, [rsp+5E8h+var_570]
0x14002b34f  call    ??0?$shared_ptr@VINetworkResourceAllocator@Resource@ComputeService@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>::shared_ptr<ComputeService::Resource::INetworkResourceAllocator>(std::shared_ptr<ComputeService::Resource::INetworkResourceAllocator> const &)
0x14002b354  nop
0x14002b355  movaps  xmm0, xmmword ptr [rsp+5E8h+Uuid.Data1]
0x14002b35d  movdqa  xmmword ptr [rsp+5E8h+var_458], xmm0
0x14002b366  mov     qword ptr [rsp+5E8h+var_478], 2710h
0x14002b372  xorps   xmm0, xmm0
0x14002b375  movdqu  [rsp+5E8h+var_478+8], xmm0
0x14002b37e  mov     rcx, [rsp+5E8h+var_3D8+8]
0x14002b386  test    rcx, rcx
0x14002b389  jz      short loc_14002B3A7
0x14002b38b  mov     rax, [rsp+5E8h+var_3D8]
0x14002b393  mov     qword ptr [rsp+5E8h+var_478+8], rax
0x14002b39b  mov     [rsp+5E8h+var_468], rcx
0x14002b3a3  lock inc dword ptr [rcx+0Ch]
0x14002b3a7  xor     edx, edx; Val
0x14002b3a9  lea     r8d, [rdx+40h]; Size
0x14002b3ad  lea     rcx, [rsp+5E8h+SystemInfo]; void *
0x14002b3b5  call    memset_0
0x14002b3ba  mov     rdi, [rsp+5E8h+var_570]
0x14002b3bf  mov     rax, [rdi]
0x14002b3c2  mov     rbx, [rax+30h]
0x14002b3c6  lea     rdx, [rsp+5E8h+var_458]
0x14002b3ce  lea     rcx, [rsp+5E8h+var_248]
0x14002b3d6  call    ??$?0AEAUSystemProcessorModificationRequest@Processor@Resources@Schema@@@?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAA@AEAUSystemProcessorModificationRequest@Processor@Resources@Schema@@@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(Schema::Resources::Processor::SystemProcessorModificationRequest &)
0x14002b3db  nop
0x14002b3dc  lea     r9, [rsp+5E8h+var_478]
0x14002b3e4  lea     r8, [rsp+5E8h+var_248]
0x14002b3ec  lea     rdx, [rsp+5E8h+SystemInfo]
0x14002b3f4  mov     rcx, rdi
0x14002b3f7  mov     rax, rbx
0x14002b3fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b3ff  nop
0x14002b400  lea     rcx, [rsp+5E8h+var_248]
0x14002b408  call    ??1?$DelayedBase@UMemoryTopology@System@Responses@Schema@@UDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAA@XZ; Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(void)
0x14002b40d  mov     qword ptr [rsp+5E8h+var_4F0.Data1], 0
0x14002b419  lea     r8, [rsp+5E8h+var_4F0]
0x14002b421  lea     rdx, [rsp+5E8h+var_458]
0x14002b429  lea     rcx, [rsp+5E8h+SystemInfo]
0x14002b431  call    ??$Unmarshal@_K@?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEBA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@PEA_K@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<unsigned __int64>(unsigned __int64 *)
0x14002b436  nop
0x14002b437  mov     edx, 0C037010Dh
0x14002b43c  mov     rcx, rax
0x14002b43f  call    ?ThrowOnUnmarshalError@Marshal@@YAXAEBU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@J@Z; Marshal::ThrowOnUnmarshalError(std::pair<bool,std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>> const &,long)
0x14002b444  nop
0x14002b445  lea     rcx, [rsp+5E8h+var_458+8]
0x14002b44d  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x14002b452  mov     qword ptr [rsp+5E8h+var_4F0.Data4], 0
0x14002b45e  lea     rcx, psz; "CPUGROUP"
0x14002b465  call    cs:__imp_SysAllocString
0x14002b46c  nop     dword ptr [rax+rax+00h]
0x14002b471  mov     rbx, rax
0x14002b474  test    rax, rax
0x14002b477  jnz     short loc_14002B499
0x14002b479  mov     rcx, [rsp+5E8h]; this
0x14002b481  mov     r9d, 8007000Eh; char *
0x14002b487  lea     r8, aOnecoreVmCommo_30; "onecore\\vm\\common\\vml\\VmBstr.h"
0x14002b48e  mov     edx, 254h; void *
0x14002b493  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14002b499  mov     rcx, qword ptr [rsp+5E8h+var_4F0.Data4]; bstrString
0x14002b4a1  test    rcx, rcx
0x14002b4a4  jz      short loc_14002B4B2
0x14002b4a6  call    cs:__imp_SysFreeString
0x14002b4ad  nop     dword ptr [rax+rax+00h]
0x14002b4b2  mov     qword ptr [rsp+5E8h+var_4F0.Data4], rbx
0x14002b4ba  mov     eax, 15h
0x14002b4bf  mov     word ptr [rsp+5E8h+pvarg], ax
0x14002b4c7  mov     rax, qword ptr [rsp+5E8h+var_4F0.Data1]
0x14002b4cf  mov     qword ptr [rsp+5E8h+pvarg+8], rax
  ... truncated ...
```
