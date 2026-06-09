# ComputeService::Management::VmDirectOrchestrator::Construct(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::OrchestratorCallContext,IVmHandleBrokerManager *,ComputeService::Management::IComputeSystemStore *)

- ea: `0x1400a4860`
- end: `0x1400a4ecd`
- name: `?Construct@VmDirectOrchestrator@Management@ComputeService@@UEAA_NAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@UOrchestratorCallContext@23@PEAUIVmHandleBrokerManager@@PEAVIComputeSystemStore@23@@Z`
- size: `1645`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140005360`
- `0x140006098`
- `0x140008760`
- `0x140009f8c`
- `0x14000ea44`
- `0x14000ea60`
- `0x14001e4f4`
- `0x1400341ac`
- `0x14003f374`
- `0x14003f698`
- `0x14003f850`
- `0x14003fa78`
- `0x14004199c`
- `0x14004fc5c`
- `0x14005b2e4`
- `0x14008853c`
- `0x14008ae64`
- `0x1400a1e40`
- `0x1400a3f94`
- `0x1400a4860`
- `0x1400ae7f8`
- `0x1400b8a0c`
- `0x1400d8f8c`
- `0x1400d9228`
- `0x1400dc6e8`
- `0x1400e6a64`
- `0x1400e6b98`
- `0x1400f4eb8`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400a4cf1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400a4cf1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400a4be5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400a4be5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400a4b64`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400a4b64`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400a4bbd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400a4bbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400a4d56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400a4d56`
- `api-ms-win-core-timezone-l1-1-0!SetDynamicTimeZoneInformation` at `0x1400a4afc`
- `api-ms-win-core-timezone-l1-1-0!SetDynamicTimeZoneInformation` at `0x1400a4afc`

## string_xrefs

- `0x1400a4e06`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400a4e8e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400a4e1e`: `onecore\vm\compute\management\computesystem\computesystem.h`
- `0x1400a4e36`: `onecore\vm\compute\management\computesystem\computesystem.h`
- `0x1400a4e4b`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmdirectorchestrator.cpp`
- `0x1400a4e60`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmdirectorchestrator.cpp`
- `0x1400a4e75`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmdirectorchestrator.cpp`
- `0x1400a4ea3`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmdirectorchestrator.cpp`
- `0x1400a4ebb`: `onecore\vm\compute\management\shared\compute\stateoperation.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
char __fastcall ComputeService::Management::VmDirectOrchestrator::Construct(__int64 a1, _QWORD **a2, __int128 *a3)
{
  HKEY v5; // rcx
  _QWORD *v6; // rdi
  __int64 v7; // rax
  __int64 v8; // r15
  HKEY *v9; // rax
  HKEY v10; // rcx
  volatile signed __int32 *v11; // rbx
  struct _TIME_DYNAMIC_ZONE_INFORMATION *v12; // r8
  const struct _GUID *v13; // r9
  unsigned __int16 *v14; // rdx
  unsigned int v15; // eax
  __int64 v16; // r8
  const BYTE *v17; // rcx
  unsigned int v18; // eax
  const struct Config::Containers::MappedPipe *v19; // r8
  __int64 v20; // rbx
  __int64 v21; // rsi
  char *v22; // rsi
  char *i; // rbx
  __int64 v24; // rbx
  __int64 v25; // rdi
  int v26; // r9d
  int ServiceStartEvent; // eax
  HKEY v28; // rbx
  DWORD v29; // eax
  const char *v30; // r9
  __int64 v31; // rax
  int ServiceBinding; // eax
  __int64 v33; // rdx
  const char *v34; // r9
  volatile signed __int32 *v35; // rbx
  unsigned int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  void (__fastcall ***v39)(_QWORD, __int64); // [rsp+50h] [rbp-B0h] BYREF
  UUID Uuid; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v41; // [rsp+70h] [rbp-90h] BYREF
  __int128 v42; // [rsp+80h] [rbp-80h] BYREF
  __int128 v43; // [rsp+90h] [rbp-70h]
  UUID *p_Uuid; // [rsp+A0h] [rbp-60h]
  __int128 *v45; // [rsp+A8h] [rbp-58h]
  __int128 *v46; // [rsp+B0h] [rbp-50h]
  HKEY hKey; // [rsp+B8h] [rbp-48h] BYREF
  __int64 *v48; // [rsp+C0h] [rbp-40h] BYREF
  BYTE *lpData[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v50; // [rsp+D8h] [rbp-28h]
  __int128 v51; // [rsp+E8h] [rbp-18h]
  _QWORD v52[42]; // [rsp+100h] [rbp+0h] BYREF
  DYNAMIC_TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+250h] [rbp+150h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+448h] [rbp+348h]

  v45 = a3;
  memset_0(v52, 0, sizeof(v52));
  v5 = (HKEY)(**a2 + 8LL);
  if ( *(_QWORD *)(**a2 + 32LL) > 7u )
    v5 = *(HKEY *)v5;
  hKey = v5;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v52,
    "VmDirect_Construct");
  v52[0] = &ComputeService::Diagnostics::TraceProvider::VmDirect_Construct::`vftable';
  ComputeService::Diagnostics::TraceProvider::VmDirect_Construct::StartActivity<unsigned short const *>(v52, &hKey);
  v6 = (_QWORD *)_RTDynamicCast_0(
                   **a2,
                   0,
                   &ComputeService::Management::ComputeSystemConfiguration `RTTI Type Descriptor',
                   &ComputeService::Management::VmHostedContainerConfiguration `RTTI Type Descriptor');
  if ( !v6 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\vm\\compute\\management\\computesystem\\computesystem.h",
      (const char *)0x80004001LL,
      0);
  v7 = _RTDynamicCast_0(
         (*a2)[1],
         0,
         &ComputeService::Management::ComputeSystemState `RTTI Type Descriptor',
         &ComputeService::Management::VmHostedComputeSystemState `RTTI Type Descriptor');
  v8 = v7;
  if ( !v7 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\vm\\compute\\management\\computesystem\\computesystem.h",
      (const char *)0x80004001LL,
      0);
  *(_DWORD *)(v7 + 392) = 0;
  v48 = 0;
  v41 = *a3;
  *(_QWORD *)a3 = 0;
  *((_QWORD *)a3 + 1) = 0;
  v42 = a3[1];
  *((_QWORD *)a3 + 2) = 0;
  *((_QWORD *)a3 + 3) = 0;
  v43 = a3[2];
  *((_QWORD *)a3 + 4) = 0;
  *((_QWORD *)a3 + 5) = 0;
  v46 = &v41;
  p_Uuid = &Uuid;
  Uuid = 0;
  v9 = (HKEY *)std::make_unique<ComputeService::Management::ActivityHolderImpl<ComputeService::Diagnostics::TraceProvider::VmDirect_Construct>,ComputeService::Diagnostics::TraceProvider::VmDirect_Construct,0>(
                 &v39,
                 v52);
  v10 = *v9;
  *v9 = 0;
  hKey = v10;
  *(_OWORD *)lpData = v41;
  v41 = 0;
  v50 = v42;
  v42 = 0;
  v51 = v43;
  v43 = 0;
  ComputeService::Management::BeginOperation_ConstructImpl(
    (unsigned int)&v48,
    (_DWORD)a2,
    (unsigned int)lpData,
    (unsigned int)&hKey,
    (__int64)&Uuid,
    (__int64)lambda_50ceb1ef45f5aeeb8cb5a499fa00ca8e_::_lambda_invoker_cdecl_);
  if ( v39 )
    (**v39)(v39, 1);
  ComputeService::Management::RetireServerOperation::~RetireServerOperation((ComputeService::Management::RetireServerOperation *)&v42);
  v11 = (volatile signed __int32 *)*((_QWORD *)&v41 + 1);
  if ( *((_QWORD *)&v41 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v41 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  *(_DWORD *)(*v48 + 136) = 1;
  memset_0(&TimeZoneInformation, 0, sizeof(TimeZoneInformation));
  ComputeService::Communication::BridgeUtilities::HostedContainerSettingsToTimeZoneInfo(
    (ComputeService::Communication::BridgeUtilities *)(v6 + 59),
    (const struct Schema::VirtualMachines::Resources::TimeZoneInformation *)&TimeZoneInformation,
    v12);
  SetDynamicTimeZoneInformation(&TimeZoneInformation);
  v14 = (unsigned __int16 *)(v6 + 1);
  if ( v6[4] > 7u )
    v14 = *(unsigned __int16 **)v14;
  ComputeService::Management::ConvertIdToGuid(
    &Uuid,
    v14,
    &`ComputeService::Management::GetComputeSystemGuid'::`2'::c_ComputeSystemSeedId,
    v13);
  hKey = 0;
  v15 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\SQMClient", 0, 0, 0, 0x20006u, 0, &hKey, 0);
  if ( v15 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x4C,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmdirectorchestrator.cpp",
      (const char *)v15,
      dwOptions);
  LOBYTE(v16) = 1;
  Vml::GuidToString(lpData, &Uuid, v16);
  v17 = (const BYTE *)lpData;
  if ( *((_QWORD *)&v50 + 1) > 7u )
    v17 = lpData[0];
  v18 = RegSetValueExW(hKey, L"MachineId", 0, 1u, v17, 2 * v50 + 2);
  if ( v18 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmdirectorchestrator.cpp",
      (const char *)v18,
      dwOptionsa);
  std::wstring::~wstring(lpData);
  if ( hKey )
    RegCloseKey(hKey);
  v20 = v6[50];
  v21 = v6[51];
  while ( v20 != v21 )
  {
    *(_OWORD *)lpData = 0;
    v50 = 0;
    std::wstring::_Construct<1,unsigned short const *>((__int64)lpData, L"C:\\", 3u);
    ComputeService::ContainerUtilities::AddMappedDirectory(0, lpData, v20);
    std::wstring::~wstring(lpData);
    v20 += 112;
  }
  v22 = (char *)v6[54];
  for ( i = (char *)v6[53]; i != v22; i += 72 )
    ComputeService::ContainerUtilities::AddMappedPipe(0, i, v19);
  v24 = v6[56];
  v25 = v6[57];
  while ( v24 != v25 )
  {
    *(_OWORD *)lpData = 0;
    v50 = 0;
    std::wstring::_Construct<1,unsigned short const *>((__int64)lpData, L"C:\\", 3u);
    LOBYTE(v26) = 1;
    ComputeService::Management::VmHostedContainer::AddMappedVirtualDisk(0, (unsigned int)lpData, v24, v26, 0);
    std::wstring::~wstring(lpData);
    v24 += 80;
  }
  hKey = 0;
  ServiceStartEvent = ContainerGetServiceStartEvent(0, &hKey);
  if ( ServiceStartEvent < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x20D,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmdirectorchestrator.cpp",
      (const char *)(unsigned int)ServiceStartEvent,
      dwOptionsa);
  v28 = hKey;
  v29 = WaitForSingleObjectEx(hKey, 0x1D4C0u, 0);
  if ( v29 != 258 && v29 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xB0F,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v30);
  v31 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator&(v8 + 184);
  ServiceBinding = ContainerGetServiceBinding(0, v31);
  if ( ServiceBinding < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x20F,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmdirectorchestrator.cpp",
      (const char *)(unsigned int)ServiceBinding,
      dwOptionsa);
  v33 = *v48;
  if ( *(_BYTE *)(*v48 + 112) )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x157,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\stateoperation.cpp",
      (const char *)0x8007139FLL,
      dwOptionsa);
  *(_BYTE *)(v33 + 112) = 1;
  *(_DWORD *)(v33 + 128) = 0;
  if ( v28 && !CloseHandle(v28) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v34);
  std::unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>::~unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>(&v48);
  v52[0] = &ComputeService::Diagnostics::TraceProvider::VmDirect_Construct::`vftable';
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v52);
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(v52);
  ComputeService::Management::RetireServerOperation::~RetireServerOperation((ComputeService::Management::RetireServerOperation *)(a3 + 1));
  v35 = (volatile signed __int32 *)*((_QWORD *)a3 + 1);
  if ( v35 )
  {
    if ( _InterlockedExchangeAdd(v35 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v35)(v35);
      if ( _InterlockedExchangeAdd(v35 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v35 + 8LL))(v35);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1400a4860  mov     [rsp-8+arg_0], rbx
0x1400a4865  push    rbp
0x1400a4866  push    rsi
0x1400a4867  push    rdi
0x1400a4868  push    r12
0x1400a486a  push    r13
0x1400a486c  push    r14
0x1400a486e  push    r15
0x1400a4870  lea     rbp, [rsp-310h]
0x1400a4878  sub     rsp, 410h
0x1400a487f  mov     rax, cs:__security_cookie
0x1400a4886  xor     rax, rsp
0x1400a4889  mov     [rbp+340h+var_40], rax
0x1400a4890  mov     r14, r8
0x1400a4893  mov     rbx, rdx
0x1400a4896  mov     [rbp+340h+var_398], r8
0x1400a489a  xor     r13d, r13d
0x1400a489d  xor     edx, edx; Val
0x1400a489f  mov     r8d, 150h; Size
0x1400a48a5  lea     rcx, [rbp+340h+var_340]; void *
0x1400a48a9  call    memset_0
0x1400a48ae  mov     rax, [rbx]
0x1400a48b1  mov     rcx, [rax]
0x1400a48b4  add     rcx, 8
0x1400a48b8  cmp     qword ptr [rcx+18h], 7
0x1400a48bd  jbe     short loc_1400A48C2
0x1400a48bf  mov     rcx, [rcx]
0x1400a48c2  mov     [rbp+340h+hKey], rcx
0x1400a48c6  lea     rdx, aVmdirectConstr; "VmDirect_Construct"
0x1400a48cd  lea     rcx, [rbp+340h+var_340]
0x1400a48d1  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400a48d6  lea     rax, ??_7VmDirect_Construct@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::VmDirect_Construct::`vftable'
0x1400a48dd  mov     [rbp+340h+var_340], rax
0x1400a48e1  lea     rdx, [rbp+340h+hKey]
0x1400a48e5  lea     rcx, [rbp+340h+var_340]
0x1400a48e9  call    ??$StartActivity@PEBG@VmDirect_Construct@TraceProvider@Diagnostics@ComputeService@@QEAAX$$QEAPEBG@Z; ComputeService::Diagnostics::TraceProvider::VmDirect_Construct::StartActivity<ushort const *>(ushort const * &&)
0x1400a48ee  nop
0x1400a48ef  mov     rcx, [rbx]
0x1400a48f2  mov     [rsp+440h+dwOptions], r13d; int
0x1400a48f7  lea     r9, ??_R0?AUVmHostedContainerConfiguration@Management@ComputeService@@@8; ComputeService::Management::VmHostedContainerConfiguration `RTTI Type Descriptor'
0x1400a48fe  lea     r8, ??_R0?AUComputeSystemConfiguration@Management@ComputeService@@@8; ComputeService::Management::ComputeSystemConfiguration `RTTI Type Descriptor'
0x1400a4905  xor     edx, edx
0x1400a4907  mov     rcx, [rcx]
0x1400a490a  call    __RTDynamicCast_0
0x1400a490f  mov     rdi, rax
0x1400a4912  mov     rcx, [rbp+348h]; this
0x1400a4919  test    rax, rax
0x1400a491c  jz      loc_1400A4E18
0x1400a4922  mov     rcx, [rbx]
0x1400a4925  mov     [rsp+440h+dwOptions], r13d; int
0x1400a492a  lea     r9, ??_R0?AUVmHostedComputeSystemState@Management@ComputeService@@@8; ComputeService::Management::VmHostedComputeSystemState `RTTI Type Descriptor'
0x1400a4931  lea     r8, ??_R0?AUComputeSystemState@Management@ComputeService@@@8; ComputeService::Management::ComputeSystemState `RTTI Type Descriptor'
0x1400a4938  xor     edx, edx
0x1400a493a  mov     rcx, [rcx+8]
0x1400a493e  call    __RTDynamicCast_0
0x1400a4943  mov     r15, rax
0x1400a4946  mov     rcx, [rbp+348h]; this
0x1400a494d  test    rax, rax
0x1400a4950  jz      loc_1400A4E30
0x1400a4956  mov     [rax+188h], r13d
0x1400a495d  mov     [rbp+340h+var_380], r13
0x1400a4961  mov     rax, [r14]
0x1400a4964  mov     qword ptr [rsp+440h+var_3D0], rax
0x1400a4969  mov     rax, [r14+8]
0x1400a496d  mov     qword ptr [rsp+440h+var_3D0+8], rax
0x1400a4972  mov     [r14], r13
0x1400a4975  mov     [r14+8], r13
0x1400a4979  lea     r12, [r14+10h]
0x1400a497d  mov     rax, [r12]
0x1400a4981  mov     qword ptr [rbp+340h+var_3C0], rax
0x1400a4985  mov     rax, [r12+8]
0x1400a498a  mov     qword ptr [rbp+340h+var_3C0+8], rax
0x1400a498e  mov     [r12], r13
0x1400a4992  mov     [r12+8], r13
0x1400a4997  mov     rax, [r12+10h]
0x1400a499c  mov     qword ptr [rbp+340h+var_3B0], rax
0x1400a49a0  mov     rax, [r12+18h]
0x1400a49a5  mov     qword ptr [rbp+340h+var_3B0+8], rax
0x1400a49a9  mov     [r12+10h], r13
0x1400a49ae  mov     [r12+18h], r13
0x1400a49b3  lea     rax, [rsp+440h+var_3D0]
0x1400a49b8  mov     [rbp+340h+var_390], rax
0x1400a49bc  lea     rax, [rsp+440h+Uuid]
0x1400a49c1  mov     [rbp+340h+var_3A0], rax
0x1400a49c5  xorps   xmm0, xmm0
0x1400a49c8  movdqu  xmmword ptr [rsp+440h+Uuid.Data1], xmm0
0x1400a49ce  lea     rdx, [rbp+340h+var_340]
0x1400a49d2  lea     rcx, [rsp+440h+var_3F0]
0x1400a49d7  call    ??$make_unique@V?$ActivityHolderImpl@VVmDirect_Construct@TraceProvider@Diagnostics@ComputeService@@@Management@ComputeService@@VVmDirect_Construct@TraceProvider@Diagnostics@3@$0A@@std@@YA?AV?$unique_ptr@V?$ActivityHolderImpl@VVmDirect_Construct@TraceProvider@Diagnostics@ComputeService@@@Management@ComputeService@@U?$default_delete@V?$ActivityHolderImpl@VVmDirect_Construct@TraceProvider@Diagnostics@ComputeService@@@Management@ComputeService@@@std@@@0@$$QEAVVmDirect_Construct@TraceProvider@Diagnostics@ComputeService@@@Z; std::make_unique<ComputeService::Management::ActivityHolderImpl<ComputeService::Diagnostics::TraceProvider::VmDirect_Construct>,ComputeService::Diagnostics::TraceProvider::VmDirect_Construct,0>(ComputeService::Diagnostics::TraceProvider::VmDirect_Construct &&)
0x1400a49dc  nop
0x1400a49dd  mov     rcx, [rax]
0x1400a49e0  mov     [rax], r13
0x1400a49e3  mov     [rbp+340h+hKey], rcx
0x1400a49e7  mov     rax, qword ptr [rsp+440h+var_3D0]
0x1400a49ec  mov     [rbp+340h+lpData], rax
0x1400a49f0  mov     rax, qword ptr [rsp+440h+var_3D0+8]
0x1400a49f5  mov     [rbp+340h+lpData+8], rax
0x1400a49f9  xorps   xmm0, xmm0
0x1400a49fc  movdqu  [rsp+440h+var_3D0], xmm0
0x1400a4a02  mov     rax, qword ptr [rbp+340h+var_3C0]
0x1400a4a06  mov     qword ptr [rbp+340h+var_368], rax
0x1400a4a0a  mov     rax, qword ptr [rbp+340h+var_3C0+8]
0x1400a4a0e  mov     qword ptr [rbp+340h+var_368+8], rax
0x1400a4a12  movdqu  [rbp+340h+var_3C0], xmm0
0x1400a4a17  mov     rax, qword ptr [rbp+340h+var_3B0]
0x1400a4a1b  mov     qword ptr [rbp+340h+var_358], rax
0x1400a4a1f  mov     rax, qword ptr [rbp+340h+var_3B0+8]
0x1400a4a23  mov     qword ptr [rbp+340h+var_358+8], rax
0x1400a4a27  movdqu  [rbp+340h+var_3B0], xmm0
0x1400a4a2c  lea     rax, _lambda_50ceb1ef45f5aeeb8cb5a499fa00ca8e____lambda_invoker_cdecl_
0x1400a4a33  mov     qword ptr [rsp+440h+samDesired], rax
0x1400a4a38  lea     rax, [rsp+440h+Uuid]
0x1400a4a3d  mov     qword ptr [rsp+440h+dwOptions], rax
0x1400a4a42  lea     r9, [rbp+340h+hKey]
0x1400a4a46  lea     r8, [rbp+340h+lpData]
0x1400a4a4a  mov     rdx, rbx
0x1400a4a4d  lea     rcx, [rbp+340h+var_380]
0x1400a4a51  call    ?BeginOperation_ConstructImpl@Management@ComputeService@@YA?AVActiveStateOperation@12@AEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@VActiveServerOperation@12@V?$unique_ptr@VActivityHolder@Management@ComputeService@@U?$default_delete@VActivityHolder@Management@ComputeService@@@std@@@5@V?$shared_ptr@UStateOperationContext@Management@ComputeService@@@5@P6AX0AEAVCompletedStateOperation@12@@Z@Z; ComputeService::Management::BeginOperation_ConstructImpl(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::ActiveServerOperation,std::unique_ptr<ComputeService::Management::ActivityHolder>,std::shared_ptr<ComputeService::Management::StateOperationContext>,void (*)(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::CompletedStateOperation &))
0x1400a4a56  nop
0x1400a4a57  mov     rcx, [rsp+440h+var_3F0]
0x1400a4a5c  test    rcx, rcx
0x1400a4a5f  jz      short loc_1400A4A72
0x1400a4a61  mov     rax, [rcx]
0x1400a4a64  mov     edx, 1
0x1400a4a69  mov     rax, [rax]
0x1400a4a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a4a71  nop
0x1400a4a72  lea     rcx, [rbp+340h+var_3C0]; this
0x1400a4a76  call    ??1RetireServerOperation@Management@ComputeService@@QEAA@XZ; ComputeService::Management::RetireServerOperation::~RetireServerOperation(void)
0x1400a4a7b  mov     rbx, qword ptr [rsp+440h+var_3D0+8]
0x1400a4a80  or      esi, 0FFFFFFFFh
0x1400a4a83  test    rbx, rbx
0x1400a4a86  jz      short loc_1400A4ABC
0x1400a4a88  mov     eax, esi
0x1400a4a8a  lock xadd [rbx+8], eax
0x1400a4a8f  add     eax, esi
0x1400a4a91  jnz     short loc_1400A4ABC
0x1400a4a93  mov     rax, [rbx]
0x1400a4a96  mov     rcx, rbx
0x1400a4a99  mov     rax, [rax]
0x1400a4a9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a4aa1  mov     eax, esi
0x1400a4aa3  lock xadd [rbx+0Ch], eax
0x1400a4aa8  add     eax, esi
0x1400a4aaa  jnz     short loc_1400A4ABC
0x1400a4aac  mov     rax, [rbx]
0x1400a4aaf  mov     rcx, rbx
0x1400a4ab2  mov     rax, [rax+8]
0x1400a4ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a4abb  nop
0x1400a4abc  mov     rax, [rbp+340h+var_380]
0x1400a4ac0  mov     rcx, [rax]
0x1400a4ac3  mov     ebx, 1
0x1400a4ac8  mov     [rcx+88h], ebx
0x1400a4ace  xor     edx, edx; Val
0x1400a4ad0  mov     r8d, 1B0h; Size
0x1400a4ad6  lea     rcx, [rbp+340h+TimeZoneInformation]; void *
0x1400a4add  call    memset_0
0x1400a4ae2  lea     rcx, [rdi+1D8h]; this
0x1400a4ae9  lea     rdx, [rbp+340h+TimeZoneInformation]; struct Schema::VirtualMachines::Resources::TimeZoneInformation *
0x1400a4af0  call    ?HostedContainerSettingsToTimeZoneInfo@BridgeUtilities@Communication@ComputeService@@YAXAEBUTimeZoneInformation@Resources@VirtualMachines@Schema@@AEAU_TIME_DYNAMIC_ZONE_INFORMATION@@@Z; ComputeService::Communication::BridgeUtilities::HostedContainerSettingsToTimeZoneInfo(Schema::VirtualMachines::Resources::TimeZoneInformation const &,_TIME_DYNAMIC_ZONE_INFORMATION &)
0x1400a4af5  lea     rcx, [rbp+340h+TimeZoneInformation]; lpTimeZoneInformation
0x1400a4afc  call    cs:__imp_SetDynamicTimeZoneInformation
0x1400a4b02  lea     rdx, [rdi+8]
0x1400a4b06  cmp     qword ptr [rdx+18h], 7
0x1400a4b0b  jbe     short loc_1400A4B10
0x1400a4b0d  mov     rdx, [rdx]; StringUuid
0x1400a4b10  lea     r8, ?c_ComputeSystemSeedId@?1??GetComputeSystemGuid@Management@ComputeService@@YA?AU_GUID@@PEBG@Z@4U4@B; retstr
0x1400a4b17  lea     rcx, [rsp+440h+Uuid]; Uuid
0x1400a4b1c  call    ?ConvertIdToGuid@Management@ComputeService@@YA?AU_GUID@@PEBGAEBU3@@Z; ComputeService::Management::ConvertIdToGuid(ushort const *,_GUID const &)
0x1400a4b21  movaps  xmm0, xmmword ptr [rsp+440h+Uuid.Data1]
0x1400a4b26  movdqa  xmmword ptr [rsp+440h+Uuid.Data1], xmm0
0x1400a4b2c  mov     [rbp+340h+hKey], r13
0x1400a4b30  mov     [rsp+440h+lpdwDisposition], r13; lpdwDisposition
0x1400a4b35  lea     rax, [rbp+340h+hKey]
0x1400a4b39  mov     [rsp+440h+phkResult], rax; phkResult
0x1400a4b3e  mov     [rsp+440h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1400a4b43  mov     [rsp+440h+samDesired], 20006h; samDesired
0x1400a4b4b  mov     [rsp+440h+dwOptions], r13d; unsigned int
0x1400a4b50  xor     r9d, r9d; lpClass
0x1400a4b53  xor     r8d, r8d; Reserved
0x1400a4b56  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\SQMClient"
0x1400a4b5d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400a4b64  call    cs:__imp_RegCreateKeyExW
0x1400a4b6a  mov     rcx, [rbp+348h]; this
0x1400a4b71  test    eax, eax
0x1400a4b73  jnz     loc_1400A4E48
0x1400a4b79  mov     r8b, bl
0x1400a4b7c  lea     rdx, [rsp+440h+Uuid]
0x1400a4b81  lea     rcx, [rbp+340h+lpData]
0x1400a4b85  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x1400a4b8a  nop
0x1400a4b8b  mov     eax, dword ptr [rbp+340h+var_368]
0x1400a4b8e  lea     rcx, [rbp+340h+lpData]
0x1400a4b92  cmp     qword ptr [rbp+340h+var_368+8], 7
0x1400a4b97  cmova   rcx, [rbp+340h+lpData]
0x1400a4b9c  lea     eax, ds:2[rax*2]
0x1400a4ba3  mov     [rsp+440h+samDesired], eax; cbData
0x1400a4ba7  mov     qword ptr [rsp+440h+dwOptions], rcx; unsigned int
0x1400a4bac  mov     r9d, ebx; dwType
0x1400a4baf  xor     r8d, r8d; Reserved
0x1400a4bb2  lea     rdx, aMachineid; "MachineId"
0x1400a4bb9  mov     rcx, [rbp+340h+hKey]; hKey
0x1400a4bbd  call    cs:__imp_RegSetValueExW
0x1400a4bc3  mov     rcx, [rbp+348h]; this
0x1400a4bca  test    eax, eax
0x1400a4bcc  jnz     loc_1400A4E5D
0x1400a4bd2  lea     rcx, [rbp+340h+lpData]; void *
0x1400a4bd6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400a4bdb  nop
0x1400a4bdc  mov     rcx, [rbp+340h+hKey]; hKey
0x1400a4be0  test    rcx, rcx
0x1400a4be3  jz      short loc_1400A4BEB
0x1400a4be5  call    cs:__imp_RegCloseKey
0x1400a4beb  mov     rbx, [rdi+190h]
0x1400a4bf2  mov     rsi, [rdi+198h]
0x1400a4bf9  jmp     short loc_1400A4C3D
0x1400a4bfb  xorps   xmm0, xmm0
0x1400a4bfe  movups  xmmword ptr [rbp+340h+lpData], xmm0
0x1400a4c02  xorps   xmm1, xmm1
0x1400a4c05  movdqu  [rbp+340h+var_368], xmm1
0x1400a4c0a  mov     r8d, 3
0x1400a4c10  lea     rdx, pszPathIn; "C:\\"
0x1400a4c17  lea     rcx, [rbp+340h+lpData]
0x1400a4c1b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400a4c20  nop
0x1400a4c21  mov     r8, rbx
0x1400a4c24  lea     rdx, [rbp+340h+lpData]
0x1400a4c28  xor     ecx, ecx
0x1400a4c2a  call    ?AddMappedDirectory@ContainerUtilities@ComputeService@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUMappedDirectory@Containers@Config@@_N@Z; ComputeService::ContainerUtilities::AddMappedDirectory(void *,std::wstring const &,Config::Containers::MappedDirectory const &,bool)
0x1400a4c2f  nop
0x1400a4c30  lea     rcx, [rbp+340h+lpData]; void *
0x1400a4c34  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400a4c39  add     rbx, 70h ; 'p'
0x1400a4c3d  cmp     rbx, rsi
0x1400a4c40  jnz     short loc_1400A4BFB
0x1400a4c42  mov     rsi, [rdi+1B0h]
0x1400a4c49  mov     rbx, [rdi+1A8h]
0x1400a4c50  jmp     short loc_1400A4C60
0x1400a4c52  mov     rdx, rbx; void *
0x1400a4c55  xor     ecx, ecx; this
0x1400a4c57  call    ?AddMappedPipe@ContainerUtilities@ComputeService@@YAXPEAXAEBUMappedPipe@Containers@Config@@@Z; ComputeService::ContainerUtilities::AddMappedPipe(void *,Config::Containers::MappedPipe const &)
0x1400a4c5c  add     rbx, 48h ; 'H'
0x1400a4c60  cmp     rbx, rsi
0x1400a4c63  jnz     short loc_1400A4C52
0x1400a4c65  mov     rbx, [rdi+1C0h]
0x1400a4c6c  mov     rdi, [rdi+1C8h]
0x1400a4c73  jmp     short loc_1400A4CBF
0x1400a4c75  xorps   xmm0, xmm0
0x1400a4c78  movups  xmmword ptr [rbp+340h+lpData], xmm0
0x1400a4c7c  xorps   xmm1, xmm1
0x1400a4c7f  movdqu  [rbp+340h+var_368], xmm1
0x1400a4c84  mov     r8d, 3
0x1400a4c8a  lea     rdx, pszPathIn; "C:\\"
0x1400a4c91  lea     rcx, [rbp+340h+lpData]
0x1400a4c95  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400a4c9a  nop
0x1400a4c9b  mov     [rsp+440h+dwOptions], r13d; int
0x1400a4ca0  mov     r9b, 1
0x1400a4ca3  mov     r8, rbx
0x1400a4ca6  lea     rdx, [rbp+340h+lpData]
0x1400a4caa  xor     ecx, ecx
0x1400a4cac  call    ?AddMappedVirtualDisk@VmHostedContainer@Management@ComputeService@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUMappedVirtualDisk@Containers@Config@@_NH@Z; ComputeService::Management::VmHostedContainer::AddMappedVirtualDisk(void *,std::wstring const &,Config::Containers::MappedVirtualDisk const &,bool,int)
0x1400a4cb1  nop
0x1400a4cb2  lea     rcx, [rbp+340h+lpData]; void *
0x1400a4cb6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400a4cbb  add     rbx, 50h ; 'P'
0x1400a4cbf  cmp     rbx, rdi
0x1400a4cc2  jnz     short loc_1400A4C75
0x1400a4cc4  mov     [rbp+340h+hKey], r13
0x1400a4cc8  lea     rdx, [rbp+340h+hKey]
0x1400a4ccc  xor     ecx, ecx
0x1400a4cce  call    ContainerGetServiceStartEvent
0x1400a4cd3  mov     rcx, [rbp+348h]; this
0x1400a4cda  test    eax, eax
0x1400a4cdc  js      loc_1400A4E72
0x1400a4ce2  xor     r8d, r8d; bAlertable
0x1400a4ce5  mov     edx, 1D4C0h; dwMilliseconds
0x1400a4cea  mov     rbx, [rbp+340h+hKey]
0x1400a4cee  mov     rcx, rbx; hHandle
0x1400a4cf1  call    cs:__imp_WaitForSingleObjectEx
0x1400a4cf7  cmp     eax, 102h
0x1400a4cfc  jz      short loc_1400A4D06
0x1400a4cfe  test    eax, eax
0x1400a4d00  jnz     loc_1400A4E87
0x1400a4d06  lea     rcx, [r15+0B8h]
0x1400a4d0d  call    ??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator&(void)
0x1400a4d12  mov     rdx, rax
0x1400a4d15  xor     ecx, ecx
0x1400a4d17  call    ContainerGetServiceBinding
0x1400a4d1c  mov     rcx, [rbp+348h]; this
0x1400a4d23  test    eax, eax
0x1400a4d25  js      loc_1400A4EA0
0x1400a4d2b  mov     rax, [rbp+340h+var_380]
0x1400a4d2f  mov     rdx, [rax]
0x1400a4d32  mov     rcx, [rbp+348h]; this
0x1400a4d39  cmp     [rdx+70h], r13b
0x1400a4d3d  jnz     loc_1400A4EB5
0x1400a4d43  mov     byte ptr [rdx+70h], 1
0x1400a4d47  mov     [rdx+80h], r13d
  ... truncated ...
```
