# ComputeService::Management::Details::ConstructSiloContainerWorker(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::ActiveStateOperation)

- ea: `0x140087d00`
- end: `0x1400884cc`
- name: `?ConstructSiloContainerWorker@Details@Management@ComputeService@@YAXAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@VActiveStateOperation@23@@Z`
- size: `1996`
- prototype: ``
- caller_count: `1`
- callee_count: `33`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400878e0`

## callees

- `0x140005360`
- `0x140008760`
- `0x14000ea60`
- `0x14001bfa4`
- `0x14001e4f4`
- `0x14002c998`
- `0x14002dd18`
- `0x140039d38`
- `0x14003f850`
- `0x14004199c`
- `0x140043b08`
- `0x140043c2c`
- `0x140043e78`
- `0x14007d7bc`
- `0x140085ee4`
- `0x1400864a8`
- `0x140087720`
- `0x140087d00`
- `0x14008853c`
- `0x140088664`
- `0x140093ee8`
- `0x1400bec20`
- `0x1400d3aa4`
- `0x1400d3e5c`
- `0x1400d4c20`
- `0x1400d50d8`
- `0x1400d5534`
- `0x1400d55e8`
- `0x1400d930c`
- `0x1400dbfa0`
- `0x1400eb8b4`
- `0x1400f4eb8`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140087e9c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140088123`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140087e9c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140088123`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140087e89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008810e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140087e89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008810e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140087e94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140087ec0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14008811b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140088148`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14008824e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140087e94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140087ec0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14008811b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140088148`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14008824e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140087f7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140087f7b`
- `IPHLPAPI!GetJobCompartmentId` at `0x140088237`
- `IPHLPAPI!GetJobCompartmentId` at `0x14008826f`
- `IPHLPAPI!GetJobCompartmentId` at `0x140088237`
- `IPHLPAPI!GetJobCompartmentId` at `0x14008826f`
- `IPHLPAPI!SetJobCompartmentId` at `0x140088267`
- `IPHLPAPI!SetJobCompartmentId` at `0x140088267`

## string_xrefs

- `0x14008847e`: `onecore\vm\compute\management\computeSystem\ComputeSystem.h`
- `0x140088493`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`
- `0x1400884ba`: `onecore\vm\compute\shared\net\NetworkUtilities.h`
- `0x1400884a8`: `onecore\vm\compute\management\orchestration\silocontainer\silocontainerorchestrator.cpp`
- `0x140088466`: `onecore\vm\compute\management\computesystem\computesystem.h`
- `0x14008844e`: `onecore\vm\compute\management\shared\compute\stateoperation.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall ComputeService::Management::Details::ConstructSiloContainerWorker(_QWORD **a1, __int64 **a2)
{
  __int64 v4; // rdi
  __int64 v5; // rsi
  char v6; // al
  const WCHAR **v7; // r14
  const WCHAR *v8; // rdx
  __int64 v9; // rax
  void **WindowsContainer; // rax
  const struct Schema::Containers::Definition::Container *v11; // r9
  void **v12; // r12
  struct _GUID **v13; // r15
  struct _GUID *v14; // rax
  struct _GUID *v15; // r13
  DWORD LastError; // ebx
  HANDLE v17; // rcx
  unsigned __int64 v18; // r12
  _QWORD *v19; // rdx
  int v20; // eax
  void *v21; // rbx
  unsigned __int64 v22; // r8
  __int64 v23; // r8
  int *v24; // rax
  __int128 *v25; // r9
  int v26; // eax
  __int128 *v27; // rdx
  int *v28; // rdx
  const struct Schema::Containers::Resources::MappedPipe *v29; // r8
  char *v30; // r14
  char *i; // rbx
  ComputeService::ContainerUtilities *v32; // rcx
  const struct _GUID *v33; // r9
  char v34; // r14
  __int64 v35; // rbx
  unsigned __int16 *v36; // rdx
  HANDLE *HvSocketAddressInfo; // rax
  void *v38; // r8
  const char *v39; // r9
  HANDLE *v40; // r13
  const struct Schema::Containers::Resources::HvSocket **v41; // r14
  DWORD v42; // ebx
  unsigned __int16 *v43; // rdx
  __int64 v44; // rbx
  __int64 (__fastcall *v45)(__int64, UUID *, _OWORD *); // r14
  const unsigned __int16 *v46; // rdx
  HANDLE *WindowsContainerJobHandleQuery; // rax
  NET_IF_COMPARTMENT_ID JobCompartmentId; // ebx
  NET_IF_COMPARTMENT_ID v49; // edx
  struct _GUID *v50; // rcx
  __int64 v51; // r14
  UUID *p_Uuid; // rsi
  __int64 **v53; // rbx
  __int64 v54; // rdx
  int v56; // [rsp+20h] [rbp-E0h]
  int v57; // [rsp+20h] [rbp-E0h]
  int v58; // [rsp+20h] [rbp-E0h]
  HANDLE JobHandle; // [rsp+40h] [rbp-C0h] BYREF
  char v60; // [rsp+48h] [rbp-B8h]
  UUID v61; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv[2]; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hObject[2]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v64; // [rsp+88h] [rbp-78h]
  UUID Uuid; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD Src[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 **v67; // [rsp+D0h] [rbp-30h]
  __int64 **v68; // [rsp+D8h] [rbp-28h]
  __int128 v69; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v70; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v71; // [rsp+F8h] [rbp-8h]
  int v72[4]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int64 v73; // [rsp+110h] [rbp+10h]
  unsigned __int64 v74; // [rsp+118h] [rbp+18h]
  _BYTE v75[608]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+2C8h]

  v67 = a2;
  v68 = a2;
  LODWORD(hObject[0]) = 0;
  v4 = _RTDynamicCast_0(
         **a1,
         0,
         &ComputeService::Management::ComputeSystemConfiguration `RTTI Type Descriptor',
         &ComputeService::Management::SiloContainerConfiguration `RTTI Type Descriptor');
  if ( !v4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\vm\\compute\\management\\computesystem\\computesystem.h",
      (const char *)0x80004001LL,
      0);
  v5 = _RTDynamicCast_0(
         (*a1)[1],
         0,
         &ComputeService::Management::ComputeSystemState `RTTI Type Descriptor',
         &ComputeService::Management::SiloContainerState `RTTI Type Descriptor');
  if ( !v5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\vm\\compute\\management\\computeSystem\\ComputeSystem.h",
      (const char *)0x80004001LL,
      0);
  if ( !*(_BYTE *)(v4 + 812) || (v6 = 1, *(_DWORD *)(v4 + 808) != 1) )
    v6 = 0;
  *(_BYTE *)(v5 + 177) = v6;
  v7 = (const WCHAR **)(v4 + 104);
  if ( *(_QWORD *)(v4 + 128) <= 7u )
    v8 = (const WCHAR *)(v4 + 104);
  else
    v8 = *v7;
  v9 = ComputeService::Storage::ResolveContainerStoragePath(Src, v8);
  std::wstring::operator=(v5 + 144, v9);
  std::wstring::~wstring(Src);
  ComputeService::Management::Details::CreateDefinitionObject(v75, v4, v5);
  ComputeService::Resources::ResourceCollection<ComputeService::Resources::ServerResource>::RetrieveByType<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(
    *(_QWORD *)(**a2 + 48) + 72LL,
    &JobHandle);
  WindowsContainer = (void **)ComputeService::ContainerUtilities::CreateWindowsContainer(
                                hObject,
                                (RPC_WSTR)(v4 + 8),
                                v75,
                                v4 + 856,
                                (__int64)&JobHandle);
  v12 = WindowsContainer;
  v13 = (struct _GUID **)(v5 + 128);
  if ( (void **)(v5 + 128) != WindowsContainer )
  {
    v14 = (struct _GUID *)*WindowsContainer;
    pv[0] = v14;
    v15 = *v13;
    if ( (unsigned __int64)&(*v13)[-1].Data4[7] <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      CloseHandle(v15);
      SetLastError(LastError);
      v14 = (struct _GUID *)pv[0];
    }
    *v13 = v14;
    *v12 = 0;
  }
  v17 = hObject[0];
  if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(hObject[0]);
  v18 = -1;
  if ( *(_BYTE *)(v5 + 177) )
  {
    v69 = 0;
    v70 = 0;
    v71 = 7;
    LOWORD(v69) = 0;
    if ( *(_BYTE *)(v4 + 192) )
    {
      v19 = (_QWORD *)(v4 + 160);
      if ( &v69 != (__int128 *)(v4 + 160) )
      {
        if ( *(_QWORD *)(v4 + 184) > 7u )
          v19 = (_QWORD *)*v19;
        std::wstring::_Assign<unsigned short>((void **)&v69, v19, *(_QWORD *)(v4 + 176));
      }
    }
    else
    {
      pv[0] = 0;
      LODWORD(hObject[0]) = 1;
      v20 = wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
              (__int64)v17,
              (char *)pv);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x250,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
          (const char *)(unsigned int)v20,
          v56);
      v21 = pv[0];
      v22 = -1;
      do
        ++v22;
      while ( *((_WORD *)pv[0] + v22) );
      std::wstring::_Assign<unsigned short>((void **)&v69, pv[0], v22);
      if ( v21 )
        CoTaskMemFree(v21);
    }
    if ( *(_QWORD *)(v4 + 128) > 7u )
      v7 = (const WCHAR **)*v7;
    ComputeService::Storage::ResolveDirectoryPath(v72, v7);
    v24 = v72;
    if ( v74 > 7 )
      LODWORD(v24) = v72[0];
    v25 = &v69;
    if ( v71 > 7 )
      v25 = (__int128 *)v69;
    v57 = (int)v24;
    v26 = BfSetupFilterInternal(7, *v13, v23, v25);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x33E,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\silocontainer\\silocontainerorchestrator.cpp",
        (const char *)(unsigned int)v26,
        v57);
    if ( (__int128 *)(v5 + 504) != &v69 )
    {
      v27 = &v69;
      if ( v71 > 7 )
        v27 = (__int128 *)v69;
      std::wstring::_Assign<unsigned short>((void **)(v5 + 504), v27, v70);
    }
    if ( (int *)(v5 + 536) != v72 )
    {
      v28 = v72;
      if ( v74 > 7 )
        v28 = *(int **)v72;
      std::wstring::_Assign<unsigned short>((void **)(v5 + 536), v28, v73);
    }
    std::wstring::~wstring(v72);
    std::wstring::~wstring(&v69);
  }
  ComputeService::Management::Details::AddMappedDirectories(
    (ComputeService::Management::Details *)v4,
    (const struct ComputeService::Management::SiloContainerConfiguration *)v5,
    (struct ComputeService::Management::SiloContainerState *)v75,
    v11);
  v30 = *(char **)(v4 + 232);
  for ( i = *(char **)(v4 + 224); i != v30; i += 72 )
  {
    v32 = 0;
    if ( !*(_BYTE *)(v5 + 177) )
      v32 = (ComputeService::ContainerUtilities *)*v13;
    ComputeService::ContainerUtilities::AddMappedPipe(v32, i, v29);
  }
  *(struct _GUID *)pv = *ComputeService::ContainerUtilities::QuerySiloContainerIdentifier(
                           (ComputeService::ContainerUtilities *)Src,
                           *v13,
                           v29);
  v34 = *(_BYTE *)(v5 + 497);
  *(_OWORD *)hObject = 0;
  v35 = v4 + 8;
  if ( *(_QWORD *)(v4 + 32) <= 7u )
    v36 = (unsigned __int16 *)(v4 + 8);
  else
    v36 = *(unsigned __int16 **)v35;
  ComputeService::Management::ConvertIdToGuid(
    &Uuid,
    v36,
    &`ComputeService::Management::GetComputeSystemGuid'::`2'::c_ComputeSystemSeedId,
    v33);
  v61 = Uuid;
  HvSocketAddressInfo = (HANDLE *)ComputeService::ContainerUtilities::CreateHvSocketAddressInfo(
                                    (unsigned int)&JobHandle,
                                    (unsigned int)&v61,
                                    (unsigned int)hObject,
                                    (unsigned int)pv,
                                    v34);
  v40 = HvSocketAddressInfo;
  v41 = (const struct Schema::Containers::Resources::HvSocket **)(v5 + 488);
  if ( (HANDLE *)(v5 + 488) != HvSocketAddressInfo )
  {
    hObject[0] = *HvSocketAddressInfo;
    pv[0] = *v41;
    if ( (unsigned __int64)pv[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v42 = GetLastError();
      CloseHandle(pv[0]);
      SetLastError(v42);
      v35 = v4 + 8;
    }
    *v41 = (const struct Schema::Containers::Resources::HvSocket *)hObject[0];
    *v40 = (HANDLE)-1LL;
  }
  if ( (char *)JobHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(JobHandle);
  if ( !*(_BYTE *)(v5 + 497) )
    ComputeService::Management::Details::ConfigureHvSocketServices(
      (ComputeService::Management::Details *)(v4 + 448),
      *v41,
      v38);
  if ( !*(_BYTE *)(v5 + 177) )
  {
    if ( *(_QWORD *)(v35 + 24) <= 7u )
      v43 = (unsigned __int16 *)v35;
    else
      v43 = *(unsigned __int16 **)v35;
    if ( *(_QWORD *)(v4 + 376) )
    {
      WindowsContainerJobHandleQuery = (HANDLE *)ComputeService::ContainerUtilities::GetWindowsContainerJobHandleQuery(&JobHandle);
      JobCompartmentId = GetJobCompartmentId(*WindowsContainerJobHandleQuery);
      if ( (char *)JobHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(JobHandle);
      *(_DWORD *)(v5 + 192) = JobCompartmentId;
    }
    else if ( *(_QWORD *)(v4 + 408) )
    {
      v44 = ComputeService::Net::NetworkingInterface::m_interface;
      if ( !ComputeService::Net::NetworkingInterface::m_interface )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0x8D,
          (unsigned int)"onecore\\vm\\compute\\shared\\net\\NetworkUtilities.h",
          v39);
      v45 = *(__int64 (__fastcall **)(__int64, UUID *, _OWORD *))(*(_QWORD *)ComputeService::Net::NetworkingInterface::m_interface
                                                                + 32LL);
      memset(Src, 0, sizeof(Src));
      do
        ++v18;
      while ( v43[v18] );
      std::wstring::_Construct<1,unsigned short const *>((__int64)Src, v43, v18);
      v46 = (const unsigned __int16 *)(v4 + 392);
      if ( *(_QWORD *)(v4 + 416) > 7u )
        v46 = *(const unsigned __int16 **)v46;
      Vml::VmGuid::Assign((Vml::VmGuid *)&v61, v46);
      *(_DWORD *)(v5 + 192) = v45(v44, &v61, Src);
      std::wstring::~wstring(Src);
    }
    v49 = *(_DWORD *)(v5 + 192);
    v50 = *v13;
    if ( v49 )
      SetJobCompartmentId(v50, v49);
    else
      *(_DWORD *)(v5 + 192) = GetJobCompartmentId(v50);
  }
  if ( *(_BYTE *)(v4 + 264) )
  {
    JobHandle = *(HANDLE *)(v4 + 248);
    v60 = 1;
  }
  else
  {
    v61 = 0;
  }
  ComputeService::ContainerUtilities::SetContainerMemoryResourceControls(*v13);
  if ( *(_BYTE *)(v4 + 312) )
  {
    hObject[0] = *(HANDLE *)(v4 + 296);
    LOBYTE(hObject[1]) = *(_BYTE *)(v4 + 304);
    *(_QWORD *)&Uuid.Data1 = *(_QWORD *)(v4 + 280);
    Uuid.Data4[0] = *(_BYTE *)(v4 + 288);
    LODWORD(pv[0]) = *(_DWORD *)(v4 + 272);
    BYTE4(pv[0]) = *(_BYTE *)(v4 + 276);
  }
  else
  {
    v61 = 0;
    Src[0] = 0;
    JobHandle = 0;
  }
  ComputeService::ContainerUtilities::SetContainerProcessorResourceControls(*v13);
  v51 = ComputeService::Management::V2SchemaUtilities::TranslateMappedDirectoriesToV1(pv, v4 + 200);
  if ( *(_BYTE *)(v4 + 152) )
  {
    *(_QWORD *)&Uuid.Data1 = *(_QWORD *)(v4 + 144);
    Uuid.Data4[0] = 1;
    p_Uuid = &Uuid;
    JobHandle = *(HANDLE *)(v4 + 136);
    v60 = 1;
  }
  else
  {
    Src[0] = 0;
    p_Uuid = (UUID *)Src;
    v61 = 0;
  }
  *(_OWORD *)hObject = 0;
  v64 = 0;
  std::wstring::_Construct<1,unsigned short const *>((__int64)hObject, &szPassword, 0);
  ComputeService::Storage::SetVolumeResourceControls(*v13, (__int64)p_Uuid, v51);
  std::wstring::~wstring(hObject);
  std::vector<Config::Containers::MappedDirectory>::_Tidy(pv);
  v53 = v67;
  v54 = **v67;
  if ( *(_BYTE *)(v54 + 112) )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x157,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\stateoperation.cpp",
      (const char *)0x8007139FLL,
      v58);
  *(_BYTE *)(v54 + 112) = 1;
  *(_DWORD *)(v54 + 128) = 0;
  Schema::Containers::Definition::Namespace::~Namespace((Schema::Containers::Definition::Namespace *)v75);
  return std::unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>::~unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>(v53);
}

```

## disassembly

```asm
0x140087d00  mov     [rsp-8+arg_10], rbx
0x140087d05  push    rbp
0x140087d06  push    rsi
0x140087d07  push    rdi
0x140087d08  push    r12
0x140087d0a  push    r13
0x140087d0c  push    r14
0x140087d0e  push    r15
0x140087d10  lea     rbp, [rsp-290h]
0x140087d18  sub     rsp, 390h
0x140087d1f  mov     rax, cs:__security_cookie
0x140087d26  xor     rax, rsp
0x140087d29  mov     [rbp+2C0h+var_40], rax
0x140087d30  mov     r15, rdx
0x140087d33  mov     [rbp+2C0h+var_2F0], rdx
0x140087d37  mov     rbx, rcx
0x140087d3a  mov     [rbp+2C0h+var_2E8], rdx
0x140087d3e  xor     r13d, r13d
0x140087d41  mov     dword ptr [rsp+3C0h+hObject], r13d
0x140087d46  mov     rcx, [rcx]
0x140087d49  mov     dword ptr [rsp+3C0h+var_3A0], r13d; int
0x140087d4e  lea     r9, ??_R0?AUSiloContainerConfiguration@Management@ComputeService@@@8; ComputeService::Management::SiloContainerConfiguration `RTTI Type Descriptor'
0x140087d55  lea     r8, ??_R0?AUComputeSystemConfiguration@Management@ComputeService@@@8; ComputeService::Management::ComputeSystemConfiguration `RTTI Type Descriptor'
0x140087d5c  xor     edx, edx
0x140087d5e  mov     rcx, [rcx]
0x140087d61  call    __RTDynamicCast_0
0x140087d66  mov     rdi, rax
0x140087d69  mov     rcx, [rbp+2C8h]; this
0x140087d70  test    rax, rax
0x140087d73  jz      loc_140088460
0x140087d79  mov     rcx, [rbx]
0x140087d7c  mov     dword ptr [rsp+3C0h+var_3A0], r13d; int
0x140087d81  lea     r9, ??_R0?AUSiloContainerState@Management@ComputeService@@@8; ComputeService::Management::SiloContainerState `RTTI Type Descriptor'
0x140087d88  lea     r8, ??_R0?AUComputeSystemState@Management@ComputeService@@@8; ComputeService::Management::ComputeSystemState `RTTI Type Descriptor'
0x140087d8f  xor     edx, edx
0x140087d91  mov     rcx, [rcx+8]
0x140087d95  call    __RTDynamicCast_0
0x140087d9a  mov     rsi, rax
0x140087d9d  mov     rcx, [rbp+2C8h]; this
0x140087da4  test    rax, rax
0x140087da7  jz      loc_140088478
0x140087dad  lea     r12d, [r13+1]
0x140087db1  cmp     [rdi+32Ch], r13b
0x140087db8  jz      short loc_140087DC6
0x140087dba  cmp     [rdi+328h], r12d
0x140087dc1  mov     al, r12b
0x140087dc4  jz      short loc_140087DC9
0x140087dc6  mov     al, r13b
0x140087dc9  mov     [rsi+0B1h], al
0x140087dcf  lea     r14, [rdi+68h]
0x140087dd3  cmp     qword ptr [r14+18h], 7
0x140087dd8  jbe     short loc_140087DDF
0x140087dda  mov     rdx, [r14]
0x140087ddd  jmp     short loc_140087DE2
0x140087ddf  mov     rdx, r14; pszPathIn
0x140087de2  lea     rcx, [rbp+2C0h+Src]; Src
0x140087de6  call    ?ResolveContainerStoragePath@Storage@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; ComputeService::Storage::ResolveContainerStoragePath(ushort const *)
0x140087deb  lea     rcx, [rsi+90h]
0x140087df2  mov     rdx, rax
0x140087df5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140087dfa  lea     rcx, [rbp+2C0h+Src]; void *
0x140087dfe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140087e03  mov     r8, rsi
0x140087e06  mov     rdx, rdi
0x140087e09  lea     rcx, [rbp+2C0h+var_2A0]
0x140087e0d  call    ?CreateDefinitionObject@Details@Management@ComputeService@@YA?AUContainer@Definition@Containers@Schema@@PEBUSiloContainerConfiguration@23@PEAUSiloContainerState@23@@Z; ComputeService::Management::Details::CreateDefinitionObject(ComputeService::Management::SiloContainerConfiguration const *,ComputeService::Management::SiloContainerState *)
0x140087e12  nop
0x140087e13  mov     ebx, r13d
0x140087e16  cmp     [rsi+0B1h], r13b
0x140087e1d  cmovnz  ebx, r12d
0x140087e21  mov     rax, [r15]
0x140087e24  mov     rcx, [rax]
0x140087e27  mov     rcx, [rcx+30h]
0x140087e2b  add     rcx, 48h ; 'H'
0x140087e2f  lea     rdx, [rsp+3C0h+JobHandle]
0x140087e34  call    ??$RetrieveByType@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@?$ResourceCollection@VServerResource@Resources@ComputeService@@@Resources@ComputeService@@AEAA?AV?$optional@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@PEBG@Z; ComputeService::Resources::ResourceCollection<ComputeService::Resources::ServerResource>::RetrieveByType<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(ushort const *)
0x140087e39  nop
0x140087e3a  lea     rdx, [rdi+8]; StringUuid
0x140087e3e  lea     rax, [rdi+358h]
0x140087e45  lea     rcx, [rsp+3C0h+JobHandle]
0x140087e4a  mov     [rsp+3C0h+var_398], rcx; __int64
0x140087e4f  mov     [rsp+3C0h+var_3A0], rax; int
0x140087e54  mov     r9d, ebx
0x140087e57  lea     r8, [rbp+2C0h+var_2A0]; void *
0x140087e5b  lea     rcx, [rsp+3C0h+hObject]; JobHandle
0x140087e60  call    ?CreateWindowsContainer@ContainerUtilities@ComputeService@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUContainer@Definition@Containers@Schema@@W4WindowsContainerFlags@12@0V?$optional@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@6@@Z; ComputeService::ContainerUtilities::CreateWindowsContainer(std::wstring const &,Schema::Containers::Definition::Container &,ComputeService::ContainerUtilities::WindowsContainerFlags,std::wstring const &,std::optional<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>)
0x140087e65  mov     r12, rax
0x140087e68  lea     r15, [rsi+80h]
0x140087e6f  cmp     r15, rax
0x140087e72  jz      short loc_140087EB1
0x140087e74  mov     rax, [rax]
0x140087e77  mov     [rsp+3C0h+pv], rax
0x140087e7c  mov     r13, [r15]
0x140087e7f  lea     rdx, [r13-1]
0x140087e83  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x140087e87  ja      short loc_140087EA7
0x140087e89  call    cs:__imp_GetLastError
0x140087e8f  mov     ebx, eax
0x140087e91  mov     rcx, r13; hObject
0x140087e94  call    cs:__imp_CloseHandle
0x140087e9a  mov     ecx, ebx; dwErrCode
0x140087e9c  call    cs:__imp_SetLastError
0x140087ea2  mov     rax, [rsp+3C0h+pv]
0x140087ea7  mov     [r15], rax
0x140087eaa  xor     r13d, r13d
0x140087ead  mov     [r12], r13
0x140087eb1  mov     rcx, [rsp+3C0h+hObject]; hObject
0x140087eb6  lea     rax, [rcx-1]
0x140087eba  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140087ebe  ja      short loc_140087EC6
0x140087ec0  call    cs:__imp_CloseHandle
0x140087ec6  or      r12, 0FFFFFFFFFFFFFFFFh
0x140087eca  cmp     [rsi+0B1h], r13b
0x140087ed1  jz      loc_140088037
0x140087ed7  xorps   xmm0, xmm0
0x140087eda  movups  [rbp+2C0h+var_2E0], xmm0
0x140087ede  mov     [rbp+2C0h+var_2D0], r13
0x140087ee2  mov     [rbp+2C0h+var_2C8], 7
0x140087eea  mov     word ptr [rbp+2C0h+var_2E0], r13w
0x140087eef  cmp     [rdi+0C0h], r13b
0x140087ef6  jz      short loc_140087F2E
0x140087ef8  lea     rdx, [rdi+0A0h]
0x140087eff  cmp     [rdx+20h], r13b
0x140087f03  jnz     short loc_140087F0C
0x140087f05  lea     ecx, [r12+6]
0x140087f0a  int     29h; Win8: RtlFailFast(ecx)
0x140087f0c  lea     rax, [rbp+2C0h+var_2E0]
0x140087f10  cmp     rax, rdx
0x140087f13  jz      short loc_140087F81
0x140087f15  mov     r8, [rdx+10h]
0x140087f19  cmp     qword ptr [rdx+18h], 7
0x140087f1e  jbe     short loc_140087F23
0x140087f20  mov     rdx, [rdx]
0x140087f23  lea     rcx, [rbp+2C0h+var_2E0]
0x140087f27  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x140087f2c  jmp     short loc_140087F81
0x140087f2e  mov     [rsp+3C0h+pv], r13
0x140087f33  mov     dword ptr [rsp+3C0h+hObject], 1
0x140087f3b  lea     rdx, [rsp+3C0h+pv]
0x140087f40  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x140087f45  mov     rcx, [rbp+2C8h]; this
0x140087f4c  test    eax, eax
0x140087f4e  js      loc_140088490
0x140087f54  mov     rbx, [rsp+3C0h+pv]
0x140087f59  mov     r8, r12
0x140087f5c  inc     r8
0x140087f5f  cmp     [rbx+r8*2], r13w
0x140087f64  jnz     short loc_140087F5C
0x140087f66  mov     rdx, rbx
0x140087f69  lea     rcx, [rbp+2C0h+var_2E0]
0x140087f6d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x140087f72  nop
0x140087f73  test    rbx, rbx
0x140087f76  jz      short loc_140087F81
0x140087f78  mov     rcx, rbx; pv
0x140087f7b  call    cs:__imp_CoTaskMemFree
0x140087f81  cmp     qword ptr [r14+18h], 7
0x140087f86  jbe     short loc_140087F8B
0x140087f88  mov     r14, [r14]
0x140087f8b  mov     rdx, r14
0x140087f8e  lea     rcx, [rbp+2C0h+var_2C0]
0x140087f92  call    ?ResolveDirectoryPath@Storage@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; ComputeService::Storage::ResolveDirectoryPath(ushort const *)
0x140087f97  nop
0x140087f98  lea     rax, [rbp+2C0h+var_2C0]
0x140087f9c  cmp     [rbp+2C0h+var_2A8], 7
0x140087fa1  cmova   rax, qword ptr [rbp+2C0h+var_2C0]
0x140087fa6  lea     r9, [rbp+2C0h+var_2E0]
0x140087faa  cmp     [rbp+2C0h+var_2C8], 7
0x140087faf  cmova   r9, qword ptr [rbp+2C0h+var_2E0]
0x140087fb4  mov     [rsp+3C0h+var_3A0], rax; int
0x140087fb9  mov     rdx, [r15]
0x140087fbc  mov     ecx, 7
0x140087fc1  call    BfSetupFilterInternal
0x140087fc6  mov     rcx, [rbp+2C8h]; this
0x140087fcd  test    eax, eax
0x140087fcf  js      loc_1400884A5
0x140087fd5  lea     rcx, [rsi+1F8h]
0x140087fdc  lea     rax, [rbp+2C0h+var_2E0]
0x140087fe0  cmp     rcx, rax
0x140087fe3  jz      short loc_140087FFC
0x140087fe5  lea     rdx, [rbp+2C0h+var_2E0]
0x140087fe9  cmp     [rbp+2C0h+var_2C8], 7
0x140087fee  cmova   rdx, qword ptr [rbp+2C0h+var_2E0]
0x140087ff3  mov     r8, [rbp+2C0h+var_2D0]
0x140087ff7  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x140087ffc  lea     rcx, [rsi+218h]
0x140088003  lea     rax, [rbp+2C0h+var_2C0]
0x140088007  cmp     rcx, rax
0x14008800a  jz      short loc_140088024
0x14008800c  lea     rdx, [rbp+2C0h+var_2C0]
0x140088010  cmp     [rbp+2C0h+var_2A8], 7
0x140088015  cmova   rdx, qword ptr [rbp+2C0h+var_2C0]
0x14008801a  mov     r8, [rbp+2C0h+var_2B0]
0x14008801e  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x140088023  nop
0x140088024  lea     rcx, [rbp+2C0h+var_2C0]; void *
0x140088028  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14008802d  nop
0x14008802e  lea     rcx, [rbp+2C0h+var_2E0]; void *
0x140088032  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140088037  lea     r8, [rbp+2C0h+var_2A0]; struct ComputeService::Management::SiloContainerState *
0x14008803b  mov     rdx, rsi; struct ComputeService::Management::SiloContainerConfiguration *
0x14008803e  mov     rcx, rdi; this
0x140088041  call    ?AddMappedDirectories@Details@Management@ComputeService@@YAXPEBUSiloContainerConfiguration@23@PEAUSiloContainerState@23@AEBUContainer@Definition@Containers@Schema@@@Z; ComputeService::Management::Details::AddMappedDirectories(ComputeService::Management::SiloContainerConfiguration const *,ComputeService::Management::SiloContainerState *,Schema::Containers::Definition::Container const &)
0x140088046  mov     r14, [rdi+0E8h]
0x14008804d  mov     rbx, [rdi+0E0h]
0x140088054  jmp     short loc_140088071
0x140088056  cmp     [rsi+0B1h], r13b
0x14008805d  mov     rcx, r13
0x140088060  jnz     short loc_140088065
0x140088062  mov     rcx, [r15]; this
0x140088065  mov     rdx, rbx; void *
0x140088068  call    ?AddMappedPipe@ContainerUtilities@ComputeService@@YAXPEAXAEBUMappedPipe@Resources@Containers@Schema@@@Z; ComputeService::ContainerUtilities::AddMappedPipe(void *,Schema::Containers::Resources::MappedPipe const &)
0x14008806d  add     rbx, 48h ; 'H'
0x140088071  cmp     rbx, r14
0x140088074  jnz     short loc_140088056
0x140088076  mov     rdx, [r15]; retstr
0x140088079  lea     rcx, [rbp+2C0h+Src]; this
0x14008807d  call    ?QuerySiloContainerIdentifier@ContainerUtilities@ComputeService@@YA?AU_GUID@@PEAX@Z; ComputeService::ContainerUtilities::QuerySiloContainerIdentifier(void *)
0x140088082  movups  xmm0, xmmword ptr [rax]
0x140088085  movdqu  xmmword ptr [rsp+3C0h+pv], xmm0
0x14008808b  mov     r14b, [rsi+1F1h]
0x140088092  xorps   xmm0, xmm0
0x140088095  movups  xmmword ptr [rsp+3C0h+hObject], xmm0
0x14008809a  lea     rbx, [rdi+8]
0x14008809e  cmp     qword ptr [rbx+18h], 7
0x1400880a3  jbe     short loc_1400880AA
0x1400880a5  mov     rdx, [rbx]
0x1400880a8  jmp     short loc_1400880AD
0x1400880aa  mov     rdx, rbx; StringUuid
0x1400880ad  lea     r8, ?c_ComputeSystemSeedId@?1??GetComputeSystemGuid@Management@ComputeService@@YA?AU_GUID@@PEBG@Z@4U4@B; retstr
0x1400880b4  lea     rcx, [rbp+2C0h+Uuid]; Uuid
0x1400880b8  call    ?ConvertIdToGuid@Management@ComputeService@@YA?AU_GUID@@PEBGAEBU3@@Z; ComputeService::Management::ConvertIdToGuid(ushort const *,_GUID const &)
0x1400880bd  movaps  xmm0, xmmword ptr [rbp+2C0h+Uuid.Data1]
0x1400880c1  movdqa  [rsp+3C0h+var_370], xmm0
0x1400880c7  mov     byte ptr [rsp+3C0h+var_3A0], r14b
0x1400880cc  lea     r9, [rsp+3C0h+pv]
0x1400880d1  lea     r8, [rsp+3C0h+hObject]
0x1400880d6  lea     rdx, [rsp+3C0h+var_370]
0x1400880db  lea     rcx, [rsp+3C0h+JobHandle]
0x1400880e0  call    ?CreateHvSocketAddressInfo@ContainerUtilities@ComputeService@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBU_GUID@@00_N@Z; ComputeService::ContainerUtilities::CreateHvSocketAddressInfo(_GUID const &,_GUID const &,_GUID const &,bool)
0x1400880e5  mov     r13, rax
0x1400880e8  lea     r14, [rsi+1E8h]
0x1400880ef  cmp     r14, rax
0x1400880f2  jz      short loc_140088139
0x1400880f4  mov     rax, [rax]
0x1400880f7  mov     [rsp+3C0h+hObject], rax
0x1400880fc  mov     rax, [r14]
0x1400880ff  mov     [rsp+3C0h+pv], rax
0x140088104  lea     rdx, [rax-1]
0x140088108  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14008810c  ja      short loc_14008812D
0x14008810e  call    cs:__imp_GetLastError
0x140088114  mov     ebx, eax
0x140088116  mov     rcx, [rsp+3C0h+pv]; hObject
0x14008811b  call    cs:__imp_CloseHandle
0x140088121  mov     ecx, ebx; dwErrCode
0x140088123  call    cs:__imp_SetLastError
0x140088129  lea     rbx, [rdi+8]
0x14008812d  mov     rax, [rsp+3C0h+hObject]
0x140088132  mov     [r14], rax
0x140088135  mov     [r13+0], r12
0x140088139  mov     rcx, [rsp+3C0h+JobHandle]; hObject
0x14008813e  lea     rax, [rcx-1]
0x140088142  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140088146  ja      short loc_14008814E
0x140088148  call    cs:__imp_CloseHandle
0x14008814e  xor     r13d, r13d
0x140088151  cmp     [rsi+1F1h], r13b
0x140088158  jnz     short loc_140088169
0x14008815a  lea     rcx, [rdi+1C0h]; this
0x140088161  mov     rdx, [r14]; struct Schema::Containers::Resources::HvSocket *
0x140088164  call    ?ConfigureHvSocketServices@Details@Management@ComputeService@@YAXAEBUHvSocket@Resources@Containers@Schema@@QEAX@Z; ComputeService::Management::Details::ConfigureHvSocketServices(Schema::Containers::Resources::HvSocket const &,void * const)
0x140088169  cmp     [rsi+0B1h], r13b
0x140088170  jnz     loc_14008827B
0x140088176  cmp     qword ptr [rbx+18h], 7
0x14008817b  jbe     short loc_140088182
0x14008817d  mov     rdx, [rbx]
0x140088180  jmp     short loc_140088185
0x140088182  mov     rdx, rbx
0x140088185  cmp     [rdi+178h], r13
0x14008818c  jnz     loc_140088223
0x140088192  cmp     [rdi+198h], r13
0x140088199  jz      loc_14008825A
0x14008819f  mov     rcx, [rbp+2C8h]; this
0x1400881a6  mov     rbx, cs:?m_interface@NetworkingInterface@Net@ComputeService@@0V?$unique_ptr@VNetworkingInterface@Net@ComputeService@@U?$default_delete@VNetworkingInterface@Net@ComputeService@@@std@@@std@@A; std::unique_ptr<ComputeService::Net::NetworkingInterface> ComputeService::Net::NetworkingInterface::m_interface
0x1400881ad  test    rbx, rbx
0x1400881b0  jz      loc_1400884BA
0x1400881b6  mov     rax, [rbx]
0x1400881b9  mov     r14, [rax+20h]
0x1400881bd  xorps   xmm0, xmm0
0x1400881c0  movups  [rbp+2C0h+Src], xmm0
0x1400881c4  xorps   xmm1, xmm1
0x1400881c7  movdqu  [rbp+2C0h+var_300], xmm1
0x1400881cc  inc     r12
0x1400881cf  cmp     [rdx+r12*2], r13w
0x1400881d4  jnz     short loc_1400881CC
0x1400881d6  mov     r8, r12
0x1400881d9  lea     rcx, [rbp+2C0h+Src]
0x1400881dd  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
  ... truncated ...
```
