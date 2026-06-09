# ComputeService::Management::Details::ModifySiloContainerSettingsWorker(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::ActiveStateOperation)

- ea: `0x14008b7f0`
- end: `0x14008c2bf`
- name: `?ModifySiloContainerSettingsWorker@Details@Management@ComputeService@@YAXAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@VActiveStateOperation@23@@Z`
- size: `2767`
- prototype: ``
- caller_count: `1`
- callee_count: `37`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x14008b220`

## callees

- `0x140005360`
- `0x140005384`
- `0x140005e70`
- `0x1400083bc`
- `0x140008760`
- `0x14000ea60`
- `0x14000f93c`
- `0x140027858`
- `0x14002dd18`
- `0x140034170`
- `0x1400393b8`
- `0x14003a9ac`
- `0x14003bc74`
- `0x14003f850`
- `0x14004199c`
- `0x14007d98c`
- `0x14007da04`
- `0x14007da7c`
- `0x14007f49c`
- `0x140080c1c`
- `0x140080efc`
- `0x1400811dc`
- `0x140081630`
- `0x140081ce4`
- `0x14008b7f0`
- `0x14008c2c8`
- `0x14008f640`
- `0x14008fe5c`
- `0x1400d33f4`
- `0x1400d5124`
- `0x1400d5534`
- `0x1400d55e8`
- `0x1400d90a0`
- `0x1400d930c`
- `0x1400da39c`
- `0x1400da790`
- `0x1400f4eb8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14008bc9b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14008bc9b`
- `container!WcSetRegistryFlushState` at `0x14008bf19`
- `container!WcSetRegistryFlushState` at `0x14008bf19`

## string_xrefs

- `0x14008c0c1`: `onecore\vm\compute\management\computeSystem\ComputeSystem.h`
- `0x14008c09d`: `Unsupported resource path %ws.`
- `0x14008c067`: `onecore\vm\compute\management\orchestration\silocontainer\silocontainerorchestrator.cpp`
- `0x14008c0a9`: `onecore\vm\compute\management\orchestration\silocontainer\silocontainerorchestrator.cpp`
- `0x14008c0d9`: `onecore\vm\compute\management\orchestration\silocontainer\silocontainerorchestrator.cpp`
- `0x14008c13c`: `onecore\vm\compute\management\orchestration\silocontainer\silocontainerorchestrator.cpp`
- `0x14008c162`: `onecore\vm\compute\management\orchestration\silocontainer\silocontainerorchestrator.cpp`
- `0x14008c191`: `onecore\vm\compute\management\orchestration\silocontainer\silocontainerorchestrator.cpp`
- `0x14008c1b7`: `onecore\vm\compute\management\orchestration\silocontainer\silocontainerorchestrator.cpp`
- `0x14008c1cf`: `onecore\vm\compute\management\orchestration\silocontainer\silocontainerorchestrator.cpp`
- `0x14008c1e7`: `onecore\vm\compute\management\orchestration\silocontainer\silocontainerorchestrator.cpp`
- `0x14008c1ff`: `onecore\vm\compute\management\orchestration\silocontainer\silocontainerorchestrator.cpp`
- `0x14008c262`: `onecore\vm\compute\management\orchestration\silocontainer\silocontainerorchestrator.cpp`
- `0x14008c052`: `onecore\vm\compute\management\shared\compute\stateoperation.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall ComputeService::Management::Details::ModifySiloContainerSettingsWorker(__int64 a1, __int64 **a2)
{
  __int64 v3; // rdi
  _QWORD *v4; // rbx
  _QWORD *v5; // rbx
  char v6; // si
  _BYTE *v7; // rax
  __int64 v8; // rcx
  __int128 *v9; // rcx
  char v10; // si
  __int64 v11; // rdx
  const struct Schema::Containers::Resources::MappedDirectory *v12; // r8
  __int64 v13; // r9
  __int64 v14; // rbx
  __int64 v15; // r14
  const wchar_t *v16; // rdx
  const wchar_t *v17; // rcx
  bool v18; // si
  __int64 v19; // r14
  __int64 i; // rsi
  __int64 v21; // rbx
  char v22; // si
  __m128i v23; // xmm6
  const struct Schema::Containers::Resources::MappedPipe *v24; // r8
  __int64 v25; // rdx
  __int64 v26; // rsi
  __int64 v27; // r14
  __int128 *v28; // rdx
  _QWORD *v29; // rcx
  int v30; // ebx
  __int64 v31; // rcx
  __int64 v32; // r14
  __int64 j; // rbx
  __int64 v34; // rbx
  ComputeService::ContainerUtilities *v35; // rcx
  __int64 v36; // rdx
  char v37; // si
  char v38; // si
  _BYTE *v39; // rax
  __int64 v40; // rdx
  int v41; // eax
  unsigned __int64 v42; // rsi
  unsigned __int64 v43; // r14
  const wchar_t *v44; // rcx
  size_t v45; // r8
  _BYTE *v46; // rax
  __int64 v47; // rdx
  __int64 v49; // rax
  unsigned int v50; // eax
  const char *v51; // rdx
  __int64 v52; // rax
  __int64 v53; // rax
  unsigned int v54; // eax
  const char *v55; // rdx
  unsigned int v56; // eax
  unsigned int v57; // eax
  __int64 v58; // rax
  __int64 v59; // rax
  unsigned int v60; // eax
  const char *v61; // rdx
  __int64 v62; // rax
  __int64 v63; // rax
  unsigned int v64; // eax
  const char *v65; // rdx
  int v66; // [rsp+28h] [rbp-E0h]
  char *v67; // [rsp+30h] [rbp-D8h]
  _BYTE v68[32]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v69; // [rsp+68h] [rbp-A0h]
  wchar_t *S1[2]; // [rsp+70h] [rbp-98h] BYREF
  size_t N; // [rsp+80h] [rbp-88h]
  unsigned __int64 v72; // [rsp+88h] [rbp-80h]
  char v73; // [rsp+90h] [rbp-78h]
  char v74; // [rsp+91h] [rbp-77h]
  __int64 **v75; // [rsp+98h] [rbp-70h]
  _BYTE v76[8]; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v77; // [rsp+A8h] [rbp-60h] BYREF
  __m128i v78; // [rsp+B8h] [rbp-50h]
  __m256i v79; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v80; // [rsp+E8h] [rbp-20h]
  __int16 v81; // [rsp+F0h] [rbp-18h]
  __int128 v82; // [rsp+F8h] [rbp-10h] BYREF
  __m128i si128; // [rsp+108h] [rbp+0h]
  __int64 v84; // [rsp+118h] [rbp+10h]
  _QWORD v85[4]; // [rsp+128h] [rbp+20h] BYREF
  _BYTE v86[8]; // [rsp+148h] [rbp+40h] BYREF
  wchar_t *S2[3]; // [rsp+150h] [rbp+48h] BYREF
  unsigned __int64 v88; // [rsp+168h] [rbp+60h]
  char v89; // [rsp+170h] [rbp+68h]
  char v90; // [rsp+171h] [rbp+69h]
  wil::details::in1diag3 *retaddr; // [rsp+1D0h] [rbp+C8h]

  v75 = a2;
  v66 = 0;
  v3 = _RTDynamicCast_0(
         *(_QWORD *)(*(_QWORD *)a1 + 8LL),
         0,
         &ComputeService::Management::ComputeSystemState `RTTI Type Descriptor',
         &ComputeService::Management::SiloContainerState `RTTI Type Descriptor');
  if ( !v3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\vm\\compute\\management\\computeSystem\\ComputeSystem.h",
      (const char *)0x80004001LL,
      0);
  v4 = *(_QWORD **)(**a2 + 392);
  if ( v4 )
    _castguard_slow_path_check_fastfail(*v4, 216, 0);
  else
    v4 = 0;
  v5 = v4 + 1;
  v6 = *(_BYTE *)(ComputeService::Management::MatchResourcePath<0>(&v77) + 32);
  if ( v79.m256i_i8[0] )
    `eh vector destructor iterator'(&v77, 0x20u, 1u, std::wstring::~wstring);
  if ( v6 )
  {
    if ( *((_DWORD *)v5 + 8) > 1u )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3FA,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\silocontainer\\silocontainerorchestrator.cpp",
        (const char *)0x80070032LL,
        0);
    v82 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v82) = 0;
    v7 = (_BYTE *)Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<std::wstring>(
                    v5 + 5,
                    &v77,
                    &v82);
    if ( !*v7 )
    {
      v52 = std::shared_ptr<ComputeService::Management::ComputeSystem>::operator-><ComputeService::Management::ComputeSystem,0>((__int64)(v7 + 8));
      v53 = std::wstring::c_str(v52);
      v54 = wil::verify_hresult<long>(3224830221LL, v53);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x1F,
        (unsigned int)"OneCore\\Internal\\VM\\inc\\MarshalUtilities.h",
        (const char *)v54,
        (int)"%ls",
        v55);
    }
    std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy((char *)&v77 + 8);
    v8 = *(_QWORD *)(v3 + 128);
    if ( *((_DWORD *)v5 + 8) )
      ComputeService::ContainerUtilities::RemoveDeviceInterface(v8, &v82);
    else
      ComputeService::ContainerUtilities::AddDeviceInterface(v8, &v82);
    v9 = &v82;
LABEL_67:
    std::wstring::~wstring(v9);
    goto LABEL_94;
  }
  v10 = *(_BYTE *)(ComputeService::Management::MatchResourcePath<0>(&v77) + 32);
  if ( v79.m256i_i8[0] )
    `eh vector destructor iterator'(&v77, 0x20u, 1u, std::wstring::~wstring);
  if ( v10 )
  {
    if ( *((_DWORD *)v5 + 8) > 1u )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x40C,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\silocontainer\\silocontainerorchestrator.cpp",
        (const char *)0x80070032LL,
        0);
    v77 = 0;
    v78 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v77) = 0;
    v79.m256i_i32[0] = 0;
    memset(&v79.m256i_u64[1], 0, 24);
    v80 = 7;
    v79.m256i_i16[4] = 0;
    v81 = 0;
    ComputeService::MarshalUtilities::FromDelayedThrow<void,Marshal::Details::DelayedJsonTraits,Schema::Containers::Resources::MappedDirectory,>(
      (__int64)(v5 + 5),
      (__int64)&v77);
    ComputeService::ContainerUtilities::NormalizeMappedDirectory(v85, &v77);
    if ( *((_DWORD *)v5 + 8) )
    {
      if ( *((_DWORD *)v5 + 8) == 1 )
      {
        v14 = *(_QWORD *)(v3 + 432);
        v15 = *(_QWORD *)(v3 + 440);
        while ( v14 != v15 )
        {
          *(_QWORD *)&v82 = v68;
          std::wstring::wstring(v68, v14);
          LODWORD(v69) = *(_DWORD *)(v14 + 32);
          std::wstring::wstring(S1, v14 + 40);
          v73 = *(_BYTE *)(v14 + 72);
          v74 = *(_BYTE *)(v14 + 73);
          v16 = (const wchar_t *)S2;
          if ( v88 > 7 )
            v16 = S2[0];
          v17 = (const wchar_t *)S1;
          if ( v72 > 7 )
            v17 = S1[0];
          v18 = (wchar_t *)N == S2[2] && (!N || wmemcmp(v17, v16, N) == 0);
          std::wstring::~wstring(S1);
          std::wstring::~wstring(v68);
          if ( v18 )
            break;
          v14 += 80;
        }
        if ( v14 == *(_QWORD *)(v3 + 440) )
        {
          v56 = wil::verify_hresult<long>(2147943568LL, v11);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x42E,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\silocontainer\\silocontainerorchestrator.cpp",
            (const char *)v56,
            0);
        }
        LOBYTE(v13) = *(_BYTE *)(v3 + 177);
        ComputeService::ContainerUtilities::RemoveMappedDirectory(*(_QWORD *)(v3 + 128), v3 + 144, S2, v13, 0);
        v19 = *(_QWORD *)(v3 + 440);
        for ( i = v14 + 80; i != v19; i += 80 )
        {
          std::wstring::operator=(v14, i);
          *(_DWORD *)(v14 + 32) = *(_DWORD *)(i + 32);
          std::wstring::operator=(v14 + 40, i + 40);
          *(_BYTE *)(v14 + 72) = *(_BYTE *)(i + 72);
          *(_BYTE *)(v14 + 73) = *(_BYTE *)(i + 73);
          v14 += 80;
        }
        v21 = *(_QWORD *)(v3 + 440);
        std::wstring::~wstring((void *)(v21 - 40));
        std::wstring::~wstring((void *)(v21 - 80));
        *(_QWORD *)(v3 + 440) -= 80LL;
      }
    }
    else if ( ComputeService::Management::Details::ValidateNewMappedDirectory(
                (ComputeService::Management::Details *)v3,
                (const struct ComputeService::Management::SiloContainerState *)v85,
                v12) )
    {
      LOBYTE(v66) = v89;
      ComputeService::ContainerUtilities::AddMappedDirectoryFromPaths(
        *(_QWORD *)(v3 + 128),
        v3 + 144,
        v85,
        S2,
        v66,
        v90);
      std::vector<Schema::Containers::Resources::MappedDirectory>::_Emplace_one_at_back<Schema::Containers::Resources::MappedDirectory>(
        v3 + 432,
        (__int64)v85);
    }
    std::wstring::~wstring(S2);
    std::wstring::~wstring(v85);
    std::wstring::~wstring(&v79.m256i_u64[1]);
    v9 = &v77;
    goto LABEL_67;
  }
  v22 = *(_BYTE *)(ComputeService::Management::MatchResourcePath<0>(&v77) + 32);
  if ( v79.m256i_i8[0] )
    `eh vector destructor iterator'(&v77, 0x20u, 1u, std::wstring::~wstring);
  if ( v22 )
  {
    v77 = 0;
    v23 = _mm_load_si128((const __m128i *)&_xmm);
    v78 = v23;
    LOWORD(v77) = 0;
    *(_OWORD *)v79.m256i_i8 = 0;
    *(__m128i *)&v79.m256i_u64[2] = v23;
    v79.m256i_i16[0] = 0;
    LODWORD(v80) = 0;
    ComputeService::MarshalUtilities::FromDelayedThrow<void,Marshal::Details::DelayedJsonTraits,Schema::Containers::Resources::MappedPipe,>(
      (__int64)(v5 + 5),
      (__int64)&v77);
    v25 = *((unsigned int *)v5 + 8);
    if ( (_DWORD)v25 )
    {
      if ( (_DWORD)v25 != 1 )
      {
        LODWORD(v67) = *((_DWORD *)v5 + 8);
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x453,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\silocontainer\\silocontainerorchestrator.cpp",
          (const char *)0x32,
          (unsigned int)"request type %d",
          v67);
      }
      v26 = *(_QWORD *)(v3 + 456);
      v27 = *(_QWORD *)(v3 + 464);
      while ( v26 != v27 )
      {
        *(_QWORD *)&v82 = v85;
        std::wstring::wstring(v85, v26);
        std::wstring::wstring(v86, v26 + 32);
        LODWORD(v88) = *(_DWORD *)(v26 + 64);
        v28 = &v77;
        if ( v78.m128i_i64[1] > 7uLL )
          v28 = (__int128 *)v77;
        v29 = v85;
        if ( v85[3] > 7u )
          v29 = (_QWORD *)v85[0];
        v30 = _o__wcsicmp(v29, v28);
        std::wstring::~wstring(v86);
        std::wstring::~wstring(v85);
        if ( !v30 )
          break;
        v26 += 72;
      }
      if ( v26 == *(_QWORD *)(v3 + 464) )
      {
        v57 = wil::verify_hresult<long>(2147943568LL, v25);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x44D,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\silocontainer\\silocontainerorchestrator.cpp",
          (const char *)v57,
          0);
      }
      v31 = 0;
      if ( !*(_BYTE *)(v3 + 177) )
        v31 = *(_QWORD *)(v3 + 128);
      ComputeService::ContainerUtilities::RemoveMappedPipe(v31, &v77);
      v32 = *(_QWORD *)(v3 + 464);
      for ( j = v26 + 72; j != v32; j += 72 )
      {
        std::wstring::operator=(v26, j);
        std::wstring::operator=(v26 + 32, j + 32);
        *(_DWORD *)(v26 + 64) = *(_DWORD *)(j + 64);
        v26 += 72;
      }
      v34 = *(_QWORD *)(v3 + 464);
      std::wstring::~wstring((void *)(v34 - 40));
      std::wstring::~wstring((void *)(v34 - 72));
      *(_QWORD *)(v3 + 464) -= 72LL;
    }
    else
    {
      v35 = 0;
      if ( !*(_BYTE *)(v3 + 177) )
        v35 = *(ComputeService::ContainerUtilities **)(v3 + 128);
      ComputeService::ContainerUtilities::AddMappedPipe(v35, &v77, v24);
      v36 = *(_QWORD *)(v3 + 464);
      if ( v36 == *(_QWORD *)(v3 + 472) )
      {
        std::vector<Schema::Containers::Resources::MappedPipe>::_Emplace_reallocate<Schema::Containers::Resources::MappedPipe>(
          v3 + 456,
          v36,
          &v77);
      }
      else
      {
        *(_OWORD *)v36 = 0;
        *(_QWORD *)(v36 + 16) = 0;
        *(_QWORD *)(v36 + 24) = 0;
        *(_OWORD *)v36 = v77;
        *(__m128i *)(v36 + 16) = v78;
        v78 = v23;
        LOWORD(v77) = 0;
        *(_OWORD *)(v36 + 32) = 0;
        *(_QWORD *)(v36 + 48) = 0;
        *(_QWORD *)(v36 + 56) = 0;
        *(__m256i *)(v36 + 32) = v79;
        *(__m128i *)&v79.m256i_u64[2] = v23;
        v79.m256i_i16[0] = 0;
        *(_DWORD *)(v36 + 64) = v80;
        *(_QWORD *)(v3 + 464) += 72LL;
      }
    }
    std::wstring::~wstring(&v79);
    v9 = &v77;
    goto LABEL_67;
  }
  v37 = *(_BYTE *)(ComputeService::Management::MatchResourcePath<0>(&v77) + 32);
  if ( v79.m256i_i8[0] )
    `eh vector destructor iterator'(&v77, 0x20u, 1u, std::wstring::~wstring);
  if ( v37 )
  {
    if ( *((_DWORD *)v5 + 8) != 2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x459,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\silocontainer\\silocontainerorchestrator.cpp",
        (const char *)0x80070032LL,
        0);
    *(_QWORD *)&v82 = 0;
    Marshal::FromDelayedThrow<void,Marshal::Details::DelayedJsonTraits,unsigned __int64,>((__int64)(v5 + 5), &v82);
    BYTE8(v82) = 1;
    ComputeService::ContainerUtilities::SetContainerMemoryResourceControls(*(HANDLE *)(v3 + 128));
  }
  else
  {
    v38 = *(_BYTE *)(ComputeService::Management::MatchResourcePath<0>(&v77) + 32);
    if ( v79.m256i_i8[0] )
      `eh vector destructor iterator'(&v77, 0x20u, 1u, std::wstring::~wstring);
    if ( v38 )
    {
      if ( *((_DWORD *)v5 + 8) != 2 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x463,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\silocontainer\\silocontainerorchestrator.cpp",
          (const char *)0x80070032LL,
          0);
      if ( *(_BYTE *)(v3 + 177) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x466,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\silocontainer\\silocontainerorchestrator.cpp",
          (const char *)0x80070032LL,
          0);
      v76[0] = 0;
      v39 = (_BYTE *)Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Schema::Containers::Resources::RegistryFlushState>(
                       v5 + 5,
                       &v77,
                       v76);
      if ( !*v39 )
      {
        v58 = std::shared_ptr<ComputeService::Management::ComputeSystem>::operator-><ComputeService::Management::ComputeSystem,0>((__int64)(v39 + 8));
        v59 = std::wstring::c_str(v58);
        v60 = wil::verify_hresult<long>(3224830221LL, v59);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x1F,
          (unsigned int)"OneCore\\Internal\\VM\\inc\\MarshalUtilities.h",
          (const char *)v60,
          (int)"%ls",
          v61);
      }
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy((char *)&v77 + 8);
      LOBYTE(v40) = v76[0];
      v41 = WcSetRegistryFlushState(*(_QWORD *)(v3 + 128), v40);
      if ( v41 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x46A,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\silocontainer\\silocontainerorchestrator.cpp",
          (const char *)(unsigned int)v41,
          0);
    }
    else
    {
      v42 = -1;
      do
        ++v42;
      while ( aContainerProce[v42] );
      v43 = v5[2];
      if ( v5[3] <= 7u )
        v44 = (const wchar_t *)v5;
      else
        v44 = (const wchar_t *)*v5;
      v45 = v5[2];
      if ( v42 < v43 )
        v45 = v42;
      if ( wmemcmp(v44, L"Container/Processor", v45) || v43 < v42 || v43 > v42 )
      {
        v49 = std::wstring::c_str(v5);
        v50 = wil::verify_hresult<long>(2147942450LL, v49);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x478,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\silocontainer\\silocontainerorchestrator.cpp",
          (const char *)v50,
          (int)"Unsupported resource path %ws.",
          v51);
      }
      if ( *((_DWORD *)v5 + 8) != 2 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x46F,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\silocontainer\\silocontainerorchestrator.cpp",
          (const char *)0x80070032LL,
          0);
      v82 = 0u;
      si128 = 0u;
      v84 = 0;
      v46 = (_BYTE *)Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Schema::Containers::Resources::Processor>(
                       v5 + 5,
                       &v77,
                       &v82);
      if ( !*v46 )
      {
        v62 = std::shared_ptr<ComputeService::Management::ComputeSystem>::operator-><ComputeService::Management::ComputeSystem,0>((__int64)(v46 + 8));
        v63 = std::wstring::c_str(v62);
        v64 = wil::verify_hresult<long>(3224830221LL, v63);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x1F,
          (unsigned int)"OneCore\\Internal\\VM\\inc\\MarshalUtilities.h",
          (const char *)v64,
          (int)"%ls",
          v65);
      }
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy((char *)&v77 + 8);
      ComputeService::ContainerUtilities::SetContainerProcessorResourceControls(*(HANDLE *)(v3 + 128));
    }
  }
LABEL_94:
  v47 = **a2;
  if ( *(_BYTE *)(v47 + 112) )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x157,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\stateoperation.cpp",
      (const char *)0x8007139FLL,
      v66);
  *(_BYTE *)(v47 + 112) = 1;
  *(_DWORD *)(v47 + 128) = 0;
  return std::unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>::~unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>(a2);
}

```

## disassembly

```asm
0x14008b7f0  mov     rax, rsp
0x14008b7f3  mov     [rax+18h], rbx
0x14008b7f7  push    rbp
0x14008b7f8  push    rsi
0x14008b7f9  push    rdi
0x14008b7fa  push    r12
0x14008b7fc  push    r13
0x14008b7fe  push    r14
0x14008b800  push    r15
0x14008b802  lea     rbp, [rax-0C8h]
0x14008b809  sub     rsp, 190h
0x14008b810  movaps  xmmword ptr [rax-48h], xmm6
0x14008b814  mov     rax, cs:__security_cookie
0x14008b81b  xor     rax, rsp
0x14008b81e  mov     [rbp+0C0h+var_50], rax
0x14008b822  mov     r15, rdx
0x14008b825  mov     [rbp+0C0h+var_130], rdx
0x14008b829  mov     rcx, [rcx]
0x14008b82c  xor     r12d, r12d
0x14008b82f  mov     [rsp+1C0h+var_1A0], r12d; int
0x14008b834  lea     r9, ??_R0?AUSiloContainerState@Management@ComputeService@@@8; ComputeService::Management::SiloContainerState `RTTI Type Descriptor'
0x14008b83b  lea     r8, ??_R0?AUComputeSystemState@Management@ComputeService@@@8; ComputeService::Management::ComputeSystemState `RTTI Type Descriptor'
0x14008b842  xor     edx, edx
0x14008b844  mov     rcx, [rcx+8]
0x14008b848  call    __RTDynamicCast_0
0x14008b84d  mov     rdi, rax
0x14008b850  mov     rcx, [rbp+0C8h]; this
0x14008b857  test    rax, rax
0x14008b85a  jz      loc_14008C0BB
0x14008b860  mov     rax, [r15]
0x14008b863  mov     rcx, [rax]
0x14008b866  mov     rbx, [rcx+188h]
0x14008b86d  test    rbx, rbx
0x14008b870  jz      short loc_14008B884
0x14008b872  xor     r8d, r8d
0x14008b875  mov     edx, 0D8h
0x14008b87a  mov     rcx, [rbx]
0x14008b87d  call    __castguard_slow_path_check_fastfail
0x14008b882  jmp     short loc_14008B887
0x14008b884  mov     rbx, r12
0x14008b887  add     rbx, 8
0x14008b88b  lea     r8, qword_14015FCF0
0x14008b892  mov     rdx, rbx
0x14008b895  lea     rcx, [rbp+0C0h+var_120]; void *
0x14008b899  call    ??$MatchResourcePath@$0A@@Management@ComputeService@@YA?AV?$optional@V?$array@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@AEBV?$basic_regex@GV?$regex_traits@G@std@@@3@@Z; ComputeService::Management::MatchResourcePath<0>(std::wstring const &,std::basic_regex<ushort,std::regex_traits<ushort>> const &)
0x14008b89e  mov     sil, [rax+20h]
0x14008b8a2  lea     r14, ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14008b8a9  mov     r13d, 1
0x14008b8af  cmp     byte ptr [rbp+0C0h+var_100], r12b
0x14008b8b3  jz      short loc_14008B8C9
0x14008b8b5  mov     r9, r14; void (*)(void *)
0x14008b8b8  mov     r8d, r13d; unsigned __int64
0x14008b8bb  lea     edx, [r13+1Fh]; unsigned __int64
0x14008b8bf  lea     rcx, [rbp+0C0h+var_120]; void *
0x14008b8c3  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14008b8c8  nop
0x14008b8c9  test    sil, sil
0x14008b8cc  jz      short loc_14008B948
0x14008b8ce  cmp     [rbx+20h], r13d
0x14008b8d2  setnbe  al
0x14008b8d5  mov     rcx, [rbp+0C8h]; this
0x14008b8dc  test    al, al
0x14008b8de  jnz     loc_14008C0D3
0x14008b8e4  xorps   xmm0, xmm0
0x14008b8e7  movups  [rbp+0C0h+var_D0], xmm0
0x14008b8eb  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14008b8f3  movdqu  [rbp+0C0h+var_C0], xmm1
0x14008b8f8  mov     word ptr [rbp+0C0h+var_D0], r12w
0x14008b8fd  lea     rcx, [rbx+28h]
0x14008b901  lea     r8, [rbp+0C0h+var_D0]
0x14008b905  lea     rdx, [rbp+0C0h+var_120]
0x14008b909  call    ??$Unmarshal@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEBA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<std::wstring>(std::wstring *)
0x14008b90e  nop
0x14008b90f  cmp     [rax], r12b
0x14008b912  jz      loc_14008C0EB
0x14008b918  lea     rcx, [rbp+0C0h+var_120+8]
0x14008b91c  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x14008b921  mov     rcx, [rdi+80h]
0x14008b928  lea     rdx, [rbp+0C0h+var_D0]
0x14008b92c  cmp     [rbx+20h], r12d
0x14008b930  jnz     short loc_14008B939
0x14008b932  call    ?AddDeviceInterface@ContainerUtilities@ComputeService@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ComputeService::ContainerUtilities::AddDeviceInterface(void *,std::wstring const &)
0x14008b937  jmp     short loc_14008B93F
0x14008b939  call    ?RemoveDeviceInterface@ContainerUtilities@ComputeService@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ComputeService::ContainerUtilities::RemoveDeviceInterface(void *,std::wstring const &)
0x14008b93e  nop
0x14008b93f  lea     rcx, [rbp+0C0h+var_D0]
0x14008b943  jmp     loc_14008BE07
0x14008b948  lea     r8, qword_14015FD18
0x14008b94f  mov     rdx, rbx
0x14008b952  lea     rcx, [rbp+0C0h+var_120]; void *
0x14008b956  call    ??$MatchResourcePath@$0A@@Management@ComputeService@@YA?AV?$optional@V?$array@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@AEBV?$basic_regex@GV?$regex_traits@G@std@@@3@@Z; ComputeService::Management::MatchResourcePath<0>(std::wstring const &,std::basic_regex<ushort,std::regex_traits<ushort>> const &)
0x14008b95b  mov     sil, [rax+20h]
0x14008b95f  cmp     byte ptr [rbp+0C0h+var_100], r12b
0x14008b963  jz      short loc_14008B97A
0x14008b965  mov     r9, r14; void (*)(void *)
0x14008b968  mov     r8, r13; unsigned __int64
0x14008b96b  mov     edx, 20h ; ' '; unsigned __int64
0x14008b970  lea     rcx, [rbp+0C0h+var_120]; void *
0x14008b974  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14008b979  nop
0x14008b97a  test    sil, sil
0x14008b97d  jz      loc_14008BBC0
0x14008b983  cmp     [rbx+20h], r13d
0x14008b987  setnbe  al
0x14008b98a  mov     rcx, [rbp+0C8h]; this
0x14008b991  test    al, al
0x14008b993  jnz     loc_14008C136
0x14008b999  xorps   xmm0, xmm0
0x14008b99c  movups  [rbp+0C0h+var_120], xmm0
0x14008b9a0  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14008b9a8  movdqa  [rbp+0C0h+var_110], xmm1
0x14008b9ad  mov     word ptr [rbp+0C0h+var_120], r12w
0x14008b9b2  mov     dword ptr [rbp+0C0h+var_100], r12d
0x14008b9b6  movups  [rbp+0C0h+var_100+8], xmm0
0x14008b9ba  mov     qword ptr [rbp+0C0h+var_F0+8], r12
0x14008b9be  mov     [rbp+0C0h+var_E0], 7
0x14008b9c6  mov     word ptr [rbp+0C0h+var_100+8], r12w
0x14008b9cb  mov     [rbp+0C0h+var_D8], r12w
0x14008b9d0  lea     rcx, [rbx+28h]
0x14008b9d4  lea     rdx, [rbp+0C0h+var_120]
0x14008b9d8  call    ??$FromDelayedThrow@XUDelayedJsonTraits@Details@Marshal@@UMappedDirectory@Resources@Containers@Schema@@$$V@MarshalUtilities@ComputeService@@YAXAEBV?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@PEAUMappedDirectory@Resources@Containers@Schema@@@Z; ComputeService::MarshalUtilities::FromDelayedThrow<void,Marshal::Details::DelayedJsonTraits,Schema::Containers::Resources::MappedDirectory,>(Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits> const &,Schema::Containers::Resources::MappedDirectory *)
0x14008b9dd  lea     rdx, [rbp+0C0h+var_120]
0x14008b9e1  lea     rcx, [rbp+0C0h+var_A0]
0x14008b9e5  call    ?NormalizeMappedDirectory@ContainerUtilities@ComputeService@@YA?AUMappedDirectory@Resources@Containers@Schema@@AEBU3456@@Z; ComputeService::ContainerUtilities::NormalizeMappedDirectory(Schema::Containers::Resources::MappedDirectory const &)
0x14008b9ea  nop
0x14008b9eb  cmp     [rbx+20h], r12d
0x14008b9ef  jnz     short loc_14008BA4D
0x14008b9f1  lea     rdx, [rbp+0C0h+var_A0]; struct ComputeService::Management::SiloContainerState *
0x14008b9f5  mov     rcx, rdi; this
0x14008b9f8  call    ?ValidateNewMappedDirectory@Details@Management@ComputeService@@YA_NPEBUSiloContainerState@23@AEBUMappedDirectory@Resources@Containers@Schema@@@Z; ComputeService::Management::Details::ValidateNewMappedDirectory(ComputeService::Management::SiloContainerState const *,Schema::Containers::Resources::MappedDirectory const &)
0x14008b9fd  test    al, al
0x14008b9ff  jz      loc_14008BB9B
0x14008ba05  lea     rdx, [rdi+90h]
0x14008ba0c  mov     al, [rdi+0B1h]
0x14008ba12  mov     [rsp+1C0h+var_188], al
0x14008ba16  mov     al, [rbp+0C0h+var_57]
0x14008ba19  mov     byte ptr [rsp+1C0h+var_198], al
0x14008ba1d  mov     al, [rbp+0C0h+var_58]
0x14008ba20  mov     byte ptr [rsp+1C0h+var_1A0], al
0x14008ba24  lea     r9, [rbp+0C0h+S2]
0x14008ba28  lea     r8, [rbp+0C0h+var_A0]
0x14008ba2c  mov     rcx, [rdi+80h]
0x14008ba33  call    ?AddMappedDirectoryFromPaths@ContainerUtilities@ComputeService@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11_N222@Z; ComputeService::ContainerUtilities::AddMappedDirectoryFromPaths(void *,std::wstring const &,std::wstring const &,std::wstring const &,bool,bool,bool,bool)
0x14008ba38  lea     rcx, [rdi+1B0h]
0x14008ba3f  lea     rdx, [rbp+0C0h+var_A0]
0x14008ba43  call    ??$_Emplace_one_at_back@UMappedDirectory@Resources@Containers@Schema@@@?$vector@UMappedDirectory@Resources@Containers@Schema@@V?$allocator@UMappedDirectory@Resources@Containers@Schema@@@std@@@std@@AEAAAEAUMappedDirectory@Resources@Containers@Schema@@$$QEAU2345@@Z; std::vector<Schema::Containers::Resources::MappedDirectory>::_Emplace_one_at_back<Schema::Containers::Resources::MappedDirectory>(Schema::Containers::Resources::MappedDirectory &&)
0x14008ba48  jmp     loc_14008BB9B
0x14008ba4d  cmp     [rbx+20h], r13d
0x14008ba51  jnz     loc_14008BB9B
0x14008ba57  mov     rbx, [rdi+1B0h]
0x14008ba5e  mov     r14, [rdi+1B8h]
0x14008ba65  jmp     loc_14008BB02
0x14008ba6a  lea     rax, [rsp+1C0h+var_180]
0x14008ba6f  mov     qword ptr [rbp+0C0h+var_D0], rax
0x14008ba73  mov     rdx, rbx
0x14008ba76  lea     rcx, [rsp+1C0h+var_180]
0x14008ba7b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14008ba80  nop
0x14008ba81  mov     eax, [rbx+20h]
0x14008ba84  mov     dword ptr [rsp+1C0h+var_160], eax
0x14008ba88  lea     rdx, [rbx+28h]
0x14008ba8c  lea     rcx, [rsp+1C0h+S1]
0x14008ba91  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14008ba96  mov     al, [rbx+48h]
0x14008ba99  mov     [rbp+0C0h+var_138], al
0x14008ba9c  mov     al, [rbx+49h]
0x14008ba9f  mov     [rbp+0C0h+var_137], al
0x14008baa2  lea     rdx, [rbp+0C0h+S2]
0x14008baa6  cmp     [rbp+0C0h+var_60], 7
0x14008baab  cmova   rdx, [rbp+0C0h+S2]; S2
0x14008bab0  mov     r8, [rsp+1C0h+N]; N
0x14008bab5  lea     rcx, [rsp+1C0h+S1]
0x14008baba  cmp     [rbp+0C0h+var_140], 7
0x14008babf  cmova   rcx, [rsp+1C0h+S1]; S1
0x14008bac5  cmp     r8, [rbp+0C0h+var_68]
0x14008bac9  jz      short loc_14008BAD0
0x14008bacb  mov     sil, r12b
0x14008bace  jmp     short loc_14008BAE5
0x14008bad0  test    r8, r8
0x14008bad3  jnz     short loc_14008BADA
0x14008bad5  mov     sil, r13b
0x14008bad8  jmp     short loc_14008BAE5
0x14008bada  call    wmemcmp
0x14008badf  test    eax, eax
0x14008bae1  setz    sil
0x14008bae5  lea     rcx, [rsp+1C0h+S1]; void *
0x14008baea  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14008baef  lea     rcx, [rsp+1C0h+var_180]; void *
0x14008baf4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14008baf9  test    sil, sil
0x14008bafc  jnz     short loc_14008BB0B
0x14008bafe  add     rbx, 50h ; 'P'
0x14008bb02  cmp     rbx, r14
0x14008bb05  jnz     loc_14008BA6A
0x14008bb0b  cmp     rbx, [rdi+1B8h]
0x14008bb12  jz      loc_14008C14E
0x14008bb18  lea     rdx, [rdi+90h]
0x14008bb1f  mov     r9b, [rdi+0B1h]
0x14008bb26  lea     r8, [rbp+0C0h+S2]
0x14008bb2a  mov     rcx, [rdi+80h]
0x14008bb31  call    ?RemoveMappedDirectory@ContainerUtilities@ComputeService@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1_N@Z; ComputeService::ContainerUtilities::RemoveMappedDirectory(void *,std::wstring const &,std::wstring const &,bool)
0x14008bb36  mov     r14, [rdi+1B8h]
0x14008bb3d  lea     rsi, [rbx+50h]
0x14008bb41  jmp     short loc_14008BB75
0x14008bb43  mov     rdx, rsi
0x14008bb46  mov     rcx, rbx
0x14008bb49  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14008bb4e  mov     eax, [rsi+20h]
0x14008bb51  mov     [rbx+20h], eax
0x14008bb54  lea     rdx, [rsi+28h]
0x14008bb58  lea     rcx, [rbx+28h]
0x14008bb5c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14008bb61  mov     al, [rsi+48h]
0x14008bb64  mov     [rbx+48h], al
0x14008bb67  mov     al, [rsi+49h]
0x14008bb6a  mov     [rbx+49h], al
0x14008bb6d  add     rbx, 50h ; 'P'
0x14008bb71  add     rsi, 50h ; 'P'
0x14008bb75  cmp     rsi, r14
0x14008bb78  jnz     short loc_14008BB43
0x14008bb7a  mov     rbx, [rdi+1B8h]
0x14008bb81  lea     rcx, [rbx-28h]; void *
0x14008bb85  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14008bb8a  lea     rcx, [rbx-50h]; void *
0x14008bb8e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14008bb93  add     qword ptr [rdi+1B8h], 0FFFFFFFFFFFFFFB0h
0x14008bb9b  lea     rcx, [rbp+0C0h+S2]; void *
0x14008bb9f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14008bba4  lea     rcx, [rbp+0C0h+var_A0]; void *
0x14008bba8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14008bbad  nop
0x14008bbae  lea     rcx, [rbp+0C0h+var_100+8]; void *
0x14008bbb2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14008bbb7  lea     rcx, [rbp+0C0h+var_120]
0x14008bbbb  jmp     loc_14008BE07
0x14008bbc0  lea     r8, qword_14015FD40
0x14008bbc7  mov     rdx, rbx
0x14008bbca  lea     rcx, [rbp+0C0h+var_120]; void *
0x14008bbce  call    ??$MatchResourcePath@$0A@@Management@ComputeService@@YA?AV?$optional@V?$array@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@AEBV?$basic_regex@GV?$regex_traits@G@std@@@3@@Z; ComputeService::Management::MatchResourcePath<0>(std::wstring const &,std::basic_regex<ushort,std::regex_traits<ushort>> const &)
0x14008bbd3  mov     sil, [rax+20h]
0x14008bbd7  cmp     byte ptr [rbp+0C0h+var_100], r12b
0x14008bbdb  jz      short loc_14008BBF2
0x14008bbdd  mov     r9, r14; void (*)(void *)
0x14008bbe0  mov     r8, r13; unsigned __int64
0x14008bbe3  mov     edx, 20h ; ' '; unsigned __int64
0x14008bbe8  lea     rcx, [rbp+0C0h+var_120]; void *
0x14008bbec  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14008bbf1  nop
0x14008bbf2  test    sil, sil
0x14008bbf5  jz      loc_14008BE11
0x14008bbfb  xorps   xmm0, xmm0
0x14008bbfe  movups  [rbp+0C0h+var_120], xmm0
0x14008bc02  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x14008bc0a  movdqa  [rbp+0C0h+var_110], xmm6
0x14008bc0f  mov     word ptr [rbp+0C0h+var_120], r12w
0x14008bc14  movups  [rbp+0C0h+var_100], xmm0
0x14008bc18  movdqa  [rbp+0C0h+var_F0], xmm6
0x14008bc1d  mov     word ptr [rbp+0C0h+var_100], r12w
0x14008bc22  mov     dword ptr [rbp+0C0h+var_E0], r12d
0x14008bc26  lea     rcx, [rbx+28h]
0x14008bc2a  lea     rdx, [rbp+0C0h+var_120]
0x14008bc2e  call    ??$FromDelayedThrow@XUDelayedJsonTraits@Details@Marshal@@UMappedPipe@Resources@Containers@Schema@@$$V@MarshalUtilities@ComputeService@@YAXAEBV?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@PEAUMappedPipe@Resources@Containers@Schema@@@Z; ComputeService::MarshalUtilities::FromDelayedThrow<void,Marshal::Details::DelayedJsonTraits,Schema::Containers::Resources::MappedPipe,>(Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits> const &,Schema::Containers::Resources::MappedPipe *)
0x14008bc33  mov     edx, [rbx+20h]
0x14008bc36  test    edx, edx
0x14008bc38  jz      loc_14008BD49
0x14008bc3e  cmp     edx, 1
0x14008bc41  jnz     loc_14008C174
0x14008bc47  mov     rsi, [rdi+1C8h]
0x14008bc4e  mov     r14, [rdi+1D0h]
0x14008bc55  jmp     short loc_14008BCBD
0x14008bc57  lea     rax, [rbp+0C0h+var_A0]
0x14008bc5b  mov     qword ptr [rbp+0C0h+var_D0], rax
0x14008bc5f  mov     rdx, rsi
0x14008bc62  lea     rcx, [rbp+0C0h+var_A0]
0x14008bc66  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14008bc6b  nop
0x14008bc6c  lea     rdx, [rsi+20h]
0x14008bc70  lea     rcx, [rbp+0C0h+var_80]
0x14008bc74  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14008bc79  mov     eax, [rsi+40h]
0x14008bc7c  mov     dword ptr [rbp+0C0h+var_60], eax
0x14008bc7f  lea     rdx, [rbp+0C0h+var_120]
0x14008bc83  cmp     qword ptr [rbp+0C0h+var_110+8], 7
0x14008bc88  cmova   rdx, qword ptr [rbp+0C0h+var_120]
0x14008bc8d  lea     rcx, [rbp+0C0h+var_A0]
0x14008bc91  cmp     [rbp+0C0h+var_88], 7
0x14008bc96  cmova   rcx, [rbp+0C0h+var_A0]
0x14008bc9b  call    cs:__imp__o__wcsicmp
0x14008bca1  mov     ebx, eax
0x14008bca3  lea     rcx, [rbp+0C0h+var_80]; void *
0x14008bca7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14008bcac  lea     rcx, [rbp+0C0h+var_A0]; void *
0x14008bcb0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14008bcb5  test    ebx, ebx
0x14008bcb7  jz      short loc_14008BCC2
0x14008bcb9  add     rsi, 48h ; 'H'
0x14008bcbd  cmp     rsi, r14
0x14008bcc0  jnz     short loc_14008BC57
0x14008bcc2  cmp     rsi, [rdi+1D0h]
0x14008bcc9  jz      loc_14008C1A3
  ... truncated ...
```
