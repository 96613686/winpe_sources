# ComputeService::Management::Details::ModifySiloContainerSettingsWorker(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::ActiveStateOperation)

- ea: `0x140074120`
- end: `0x14007486a`
- name: `?ModifySiloContainerSettingsWorker@Details@Management@ComputeService@@YAXAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@VActiveStateOperation@23@@Z`
- size: `1866`
- prototype: ``
- caller_count: `1`
- callee_count: `43`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x140171a90`

## callees

- `0x140017040`
- `0x14001bc28`
- `0x140021f9c`
- `0x14002ac78`
- `0x1400421f0`
- `0x140044974`
- `0x140060e88`
- `0x140073a74`
- `0x140074120`
- `0x140077dbc`
- `0x1400831e0`
- `0x1400849c0`
- `0x14009cb5c`
- `0x1400b2a44`
- `0x1400c40e0`
- `0x1400d4520`
- `0x1400d5370`
- `0x1400d5dc4`
- `0x1400fc75c`
- `0x140109a30`
- `0x14010e4ac`
- `0x14011cffc`
- `0x14012f784`
- `0x14012f91c`
- `0x140132918`
- `0x1401332f0`
- `0x140133d94`
- `0x14015e4f8`
- `0x14015e52c`
- `0x14015e56c`
- `0x140169654`
- `0x14016cd6c`
- `0x14016cee8`
- `0x14016d4c8`
- `0x14016d8cc`
- `0x140171cd0`
- `0x14017386c`
- `0x140173ea4`
- `0x140177b0c`
- `0x140177cc4`
- `0x140214cbc`
- `0x1402159ac`
- `0x140215bf8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400744fd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400744fd`
- `container!WcSetRegistryFlushState` at `0x140074725`
- `container!WcSetRegistryFlushState` at `0x140074725`

## string_xrefs

- `0x1400741cc`: `onecore\vm\compute\management\orchestration\silocontainer\silocontainerorchestrator.cpp`
- `0x140074280`: `onecore\vm\compute\management\orchestration\silocontainer\silocontainerorchestrator.cpp`
- `0x14007437f`: `onecore\vm\compute\management\orchestration\silocontainer\silocontainerorchestrator.cpp`
- `0x1400744ae`: `onecore\vm\compute\management\orchestration\silocontainer\silocontainerorchestrator.cpp`
- `0x140074539`: `onecore\vm\compute\management\orchestration\silocontainer\silocontainerorchestrator.cpp`
- `0x140074614`: `onecore\vm\compute\management\orchestration\silocontainer\silocontainerorchestrator.cpp`
- `0x1400746b2`: `onecore\vm\compute\management\orchestration\silocontainer\silocontainerorchestrator.cpp`
- `0x1400746da`: `onecore\vm\compute\management\orchestration\silocontainer\silocontainerorchestrator.cpp`
- `0x140074743`: `onecore\vm\compute\management\orchestration\silocontainer\silocontainerorchestrator.cpp`
- `0x14007477f`: `onecore\vm\compute\management\orchestration\silocontainer\silocontainerorchestrator.cpp`
- `0x140074858`: `onecore\vm\compute\management\orchestration\silocontainer\silocontainerorchestrator.cpp`
- `0x140074846`: `Unsupported resource path %ws.`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall ComputeService::Management::Details::ModifySiloContainerSettingsWorker(
        _QWORD *a1,
        ComputeService::Management::ActiveStateOperation *a2)
{
  __int64 v3; // rdi
  _QWORD *v4; // rsi
  _QWORD *v5; // rsi
  char v6; // bl
  __int64 v7; // rax
  __int64 v8; // rcx
  char v9; // bl
  __int64 v10; // rax
  const struct Schema::Containers::Resources::MappedDirectory *v11; // r8
  __int64 v12; // rbx
  __int64 v13; // r14
  __int64 i; // rsi
  char v15; // bl
  __int64 v16; // rax
  const struct Schema::Containers::Resources::MappedPipe *v17; // r8
  int v18; // edx
  const struct Schema::Containers::Resources::MappedPipe *v19; // rsi
  const struct Schema::Containers::Resources::MappedPipe *v20; // r12
  Schema::Responses::System::CrashReportProcessDump *v21; // rax
  Schema::Responses::System::CrashReportProcessDump *v22; // r15
  _QWORD *v23; // rdx
  Schema::Responses::System::CrashReportProcessDump *v24; // rcx
  int v25; // ebx
  __int64 v26; // rcx
  ComputeService::ContainerUtilities *v27; // rcx
  char v28; // bl
  __int64 v29; // rax
  char v30; // bl
  __int64 v31; // rax
  __int64 v32; // rdx
  int v33; // eax
  __int64 v34; // rax
  int v36; // [rsp+20h] [rbp-E0h]
  char *v37; // [rsp+28h] [rbp-D8h]
  char v38[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v39[64]; // [rsp+48h] [rbp-B8h] BYREF
  ComputeService::Management::ActiveStateOperation *v40; // [rsp+88h] [rbp-78h] BYREF
  char v41[8]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v42; // [rsp+98h] [rbp-68h] BYREF
  __int128 v43; // [rsp+A0h] [rbp-60h]
  __int128 v44; // [rsp+B0h] [rbp-50h]
  _QWORD v45[5]; // [rsp+C0h] [rbp-40h] BYREF
  struct _GUID v46[2]; // [rsp+E8h] [rbp-18h] BYREF
  char v47; // [rsp+108h] [rbp+8h]
  char v48; // [rsp+109h] [rbp+9h]
  _BYTE v49[80]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v40 = a2;
  v3 = ComputeService::Management::ComputeSystem::GetStateAs<ComputeService::Management::SiloContainerState>(*a1);
  v4 = *(_QWORD **)(**(_QWORD **)a2 + 392LL);
  if ( v4 )
    _castguard_slow_path_check_fastfail(*v4, 232, 0);
  else
    v4 = 0;
  v5 = v4 + 1;
  v6 = *(_BYTE *)(ComputeService::Management::MatchResourcePath<0>(v38) + 32);
  std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(v38);
  if ( v6 )
  {
    if ( *((_DWORD *)v5 + 8) > 1u )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3FA,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\silocontainer\\silocontainerorchestrator.cpp",
        (const char *)0x80070032LL,
        v36);
    std::wstring::wstring(&v42);
    v7 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<std::wstring>(v5 + 5, v38, &v42);
    Marshal::ThrowOnUnmarshalError(v7, 3224830221LL);
    std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(v39);
    v8 = *(_QWORD *)(v3 + 128);
    if ( *((_DWORD *)v5 + 8) )
      ComputeService::ContainerUtilities::RemoveDeviceInterface(v8, &v42);
    else
      ComputeService::ContainerUtilities::AddDeviceInterface(v8, &v42);
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)&v42);
  }
  else
  {
    v9 = *(_BYTE *)(ComputeService::Management::MatchResourcePath<0>(v38) + 32);
    std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(v38);
    if ( v9 )
    {
      if ( *((_DWORD *)v5 + 8) > 1u )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x40C,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\silocontainer\\silocontainerorchestrator.cpp",
          (const char *)0x80070032LL,
          v36);
      Schema::Containers::Resources::MappedDirectory::MappedDirectory((Schema::Containers::Resources::MappedDirectory *)v49);
      v10 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Schema::Containers::Resources::MappedDirectory>(
              v5 + 5,
              v38,
              v49);
      Marshal::ThrowOnUnmarshalError(v10, 3224830221LL);
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(v39);
      ComputeService::ContainerUtilities::NormalizeMappedDirectory(v45, v49);
      if ( *((_DWORD *)v5 + 8) )
      {
        if ( *((_DWORD *)v5 + 8) == 1 )
        {
          v42 = 0;
          std::find_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_Schema::Containers::Resources::MappedDirectory_______lambda_ca7641d4ba7a5b3de947fe0abe371a51___(
            &v42,
            *(_QWORD *)(v3 + 432),
            *(_QWORD *)(v3 + 440),
            v45);
          v12 = v42;
          if ( v42 == *(_QWORD *)(v3 + 440) )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x42E,
              (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\silocontainer\\silocontainerorchestrator.cpp",
              (const char *)0x80070490LL,
              v36);
          ComputeService::ContainerUtilities::RemoveMappedDirectory(
            *(_QWORD *)(v3 + 128),
            v3 + 144,
            v46,
            *(_BYTE *)(v3 + 177));
          v13 = *(_QWORD *)(v3 + 440);
          for ( i = v12 + 80; i != v13; i += 80 )
          {
            std::wstring::operator=(v12, i);
            *(_DWORD *)(v12 + 32) = *(_DWORD *)(i + 32);
            std::wstring::operator=(v12 + 40, i + 40);
            *(_BYTE *)(v12 + 72) = *(_BYTE *)(i + 72);
            *(_BYTE *)(v12 + 73) = *(_BYTE *)(i + 73);
            v12 += 80;
          }
          Schema::Containers::Resources::MappedDirectory::~MappedDirectory((Schema::Containers::Resources::MappedDirectory *)(*(_QWORD *)(v3 + 440) - 80LL));
          *(_QWORD *)(v3 + 440) -= 80LL;
        }
      }
      else if ( ComputeService::Management::Details::ValidateNewMappedDirectory(
                  (ComputeService::Management::Details *)v3,
                  (const struct ComputeService::Management::SiloContainerState *)v45,
                  v11) )
      {
        ComputeService::ContainerUtilities::AddMappedDirectoryFromPaths(
          *(_QWORD *)(v3 + 128),
          v3 + 144,
          (char *)v45,
          (ComputeService::Storage *)v46,
          v47,
          v48,
          1,
          *(_BYTE *)(v3 + 177));
        std::vector<Schema::Containers::Resources::MappedDirectory>::_Emplace_one_at_back<Schema::Containers::Resources::MappedDirectory>(
          v3 + 432,
          v45);
      }
      Schema::Containers::Resources::MappedDirectory::~MappedDirectory((Schema::Containers::Resources::MappedDirectory *)v45);
      Schema::Containers::Resources::MappedDirectory::~MappedDirectory((Schema::Containers::Resources::MappedDirectory *)v49);
    }
    else
    {
      v15 = *(_BYTE *)(ComputeService::Management::MatchResourcePath<0>(v38) + 32);
      std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(v38);
      if ( v15 )
      {
        Schema::Containers::Resources::MappedPipe::MappedPipe((Schema::Containers::Resources::MappedPipe *)v45);
        v16 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Schema::Containers::Resources::MappedPipe>(
                v5 + 5,
                v38,
                v45);
        Marshal::ThrowOnUnmarshalError(v16, 3224830221LL);
        std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(v39);
        v18 = *((_DWORD *)v5 + 8);
        if ( v18 )
        {
          if ( v18 != 1 )
          {
            LODWORD(v37) = *((_DWORD *)v5 + 8);
            wil::details::in1diag3::Throw_Win32Msg(
              retaddr,
              (void *)0x453,
              (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\silocontainer\\silocontainerorchestrator.cpp",
              (const char *)0x32,
              (unsigned int)"request type %d",
              v37);
          }
          v19 = *(const struct Schema::Containers::Resources::MappedPipe **)(v3 + 456);
          v20 = *(const struct Schema::Containers::Resources::MappedPipe **)(v3 + 464);
          while ( v19 != v20 )
          {
            v21 = (Schema::Responses::System::CrashReportProcessDump *)Schema::Containers::Resources::MappedPipe::MappedPipe(
                                                                         (Schema::Containers::Resources::MappedPipe *)v38,
                                                                         v19);
            v22 = v21;
            v23 = v45;
            if ( v45[3] > 7u )
              v23 = (_QWORD *)v45[0];
            v24 = *((_QWORD *)v21 + 3) <= 7u ? v21 : *(Schema::Responses::System::CrashReportProcessDump **)v21;
            v25 = _o__wcsicmp(v24, v23);
            std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(v22);
            if ( !v25 )
              break;
            v19 = (const struct Schema::Containers::Resources::MappedPipe *)((char *)v19 + 72);
          }
          if ( v19 == *(const struct Schema::Containers::Resources::MappedPipe **)(v3 + 464) )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x44D,
              (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\silocontainer\\silocontainerorchestrator.cpp",
              (const char *)0x80070490LL,
              v36);
          v26 = 0;
          if ( !*(_BYTE *)(v3 + 177) )
            v26 = *(_QWORD *)(v3 + 128);
          ComputeService::ContainerUtilities::RemoveMappedPipe(v26, v45);
          std::vector<Schema::Containers::Resources::MappedPipe>::erase(v3 + 456, &v40, v19);
        }
        else
        {
          v27 = 0;
          if ( !*(_BYTE *)(v3 + 177) )
            v27 = *(ComputeService::ContainerUtilities **)(v3 + 128);
          ComputeService::ContainerUtilities::AddMappedPipe(v27, v45, v17);
          if ( *(_QWORD *)(v3 + 464) == *(_QWORD *)(v3 + 472) )
          {
            std::vector<Schema::Containers::Resources::MappedPipe>::_Emplace_reallocate<Schema::Containers::Resources::MappedPipe>(
              v3 + 456,
              *(_QWORD *)(v3 + 464),
              v45);
          }
          else
          {
            Schema::Containers::Resources::MappedPipe::MappedPipe(*(_QWORD *)(v3 + 464), v45);
            *(_QWORD *)(v3 + 464) += 72LL;
          }
        }
        std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>((Schema::Responses::System::CrashReportProcessDump *)v45);
      }
      else
      {
        v28 = *(_BYTE *)(ComputeService::Management::MatchResourcePath<0>(v38) + 32);
        std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(v38);
        if ( v28 )
        {
          if ( *((_DWORD *)v5 + 8) != 2 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x459,
              (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\silocontainer\\silocontainerorchestrator.cpp",
              (const char *)0x80070032LL,
              v36);
          v42 = 0;
          v29 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<unsigned __int64>(
                  v5 + 5,
                  v38,
                  &v42);
          Marshal::ThrowOnUnmarshalError(v29, 3224830221LL);
          std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(v39);
          LOBYTE(v43) = 1;
          ComputeService::ContainerUtilities::SetContainerMemoryResourceControls(*(HANDLE *)(v3 + 128));
        }
        else
        {
          v30 = *(_BYTE *)(ComputeService::Management::MatchResourcePath<0>(v38) + 32);
          std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(v38);
          if ( v30 )
          {
            if ( *((_DWORD *)v5 + 8) != 2 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x463,
                (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\silocontainer\\silocontainerorchestrator.cpp",
                (const char *)0x80070032LL,
                v36);
            if ( *(_BYTE *)(v3 + 177) )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x466,
                (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\silocontainer\\silocontainerorchestrator.cpp",
                (const char *)0x80070032LL,
                v36);
            v41[0] = 0;
            v31 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Schema::Containers::Resources::RegistryFlushState>(
                    v5 + 5,
                    v38,
                    v41);
            Marshal::ThrowOnUnmarshalError(v31, 3224830221LL);
            std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(v39);
            LOBYTE(v32) = v41[0];
            v33 = WcSetRegistryFlushState(*(_QWORD *)(v3 + 128), v32);
            if ( v33 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x46A,
                (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\silocontainer\\silocontainerorchestrator.cpp",
                (const char *)(unsigned int)v33,
                v36);
          }
          else
          {
            if ( (unsigned int)std::wstring::compare(v5, L"Container/Processor") )
            {
              if ( v5[3] > 7u )
                v5 = (_QWORD *)*v5;
              wil::details::in1diag3::Throw_HrMsg(
                retaddr,
                (void *)0x478,
                (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\silocontainer\\silocontainerorchestrator.cpp",
                (const char *)0x80070032LL,
                (int)"Unsupported resource path %ws.",
                (const char *)v5);
            }
            if ( *((_DWORD *)v5 + 8) != 2 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x46F,
                (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\silocontainer\\silocontainerorchestrator.cpp",
                (const char *)0x80070032LL,
                v36);
            v42 = 0;
            v43 = 0u;
            v44 = 0u;
            v34 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Schema::Containers::Resources::Processor>(
                    v5 + 5,
                    v38,
                    &v42);
            Marshal::ThrowOnUnmarshalError(v34, 3224830221LL);
            std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(v39);
            ComputeService::ContainerUtilities::SetContainerProcessorResourceControls(*(HANDLE *)(v3 + 128));
          }
        }
      }
    }
  }
  ComputeService::Management::ActiveStateOperation::Complete(a2, 0);
  return std::unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>::~unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>(a2);
}

```

## disassembly

```asm
0x140074120  mov     [rsp-8+arg_10], rbx
0x140074125  push    rbp
0x140074126  push    rsi
0x140074127  push    rdi
0x140074128  push    r12
0x14007412a  push    r13
0x14007412c  push    r14
0x14007412e  push    r15
0x140074130  lea     rbp, [rsp-70h]
0x140074135  sub     rsp, 170h
0x14007413c  mov     rax, cs:__security_cookie
0x140074143  xor     rax, rsp
0x140074146  mov     [rbp+0A0h+var_40], rax
0x14007414a  mov     r13, rdx
0x14007414d  mov     [rbp+0A0h+var_118], rdx
0x140074151  mov     rcx, [rcx]
0x140074154  call    ??$GetStateAs@USiloContainerState@Management@ComputeService@@@ComputeSystem@Management@ComputeService@@QEAAPEAUSiloContainerState@12@XZ; ComputeService::Management::ComputeSystem::GetStateAs<ComputeService::Management::SiloContainerState>(void)
0x140074159  mov     rdi, rax
0x14007415c  mov     rcx, [r13+0]
0x140074160  mov     rdx, [rcx]
0x140074163  mov     rsi, [rdx+188h]
0x14007416a  xor     r15d, r15d
0x14007416d  test    rsi, rsi
0x140074170  jz      short loc_140074184
0x140074172  xor     r8d, r8d
0x140074175  mov     edx, 0E8h
0x14007417a  mov     rcx, [rsi]
0x14007417d  call    __castguard_slow_path_check_fastfail
0x140074182  jmp     short loc_140074187
0x140074184  mov     rsi, r15
0x140074187  add     rsi, 8
0x14007418b  lea     r8, qword_1403DBCE8
0x140074192  mov     rdx, rsi
0x140074195  lea     rcx, [rsp+1A0h+var_160]; void *
0x14007419a  call    ??$MatchResourcePath@$0A@@Management@ComputeService@@YA?AV?$optional@V?$array@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@AEBV?$basic_regex@GV?$regex_traits@G@std@@@3@@Z; ComputeService::Management::MatchResourcePath<0>(std::wstring const &,std::basic_regex<ushort,std::regex_traits<ushort>> const &)
0x14007419f  mov     bl, [rax+20h]
0x1400741a2  lea     rcx, [rsp+1A0h+var_160]
0x1400741a7  call    ??1?$_Optional_destruct_base@V?$array@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(void)
0x1400741ac  test    bl, bl
0x1400741ae  jz      loc_14007423F
0x1400741b4  cmp     dword ptr [rsi+20h], 1
0x1400741b8  setnbe  al
0x1400741bb  mov     rcx, [rbp+0A8h]; this
0x1400741c2  test    al, al
0x1400741c4  jz      short loc_1400741DE
0x1400741c6  mov     r9d, 80070032h; char *
0x1400741cc  lea     r8, aOnecoreVmCompu_136; "onecore\\vm\\compute\\management\\orche"...
0x1400741d3  mov     edx, 3FAh; void *
0x1400741d8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400741de  lea     rcx, [rbp+0A0h+var_108]; void *
0x1400741e2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1400741e7  nop
0x1400741e8  lea     rcx, [rsi+28h]
0x1400741ec  lea     r8, [rbp+0A0h+var_108]
0x1400741f0  lea     rdx, [rsp+1A0h+var_160]
0x1400741f5  call    ??$Unmarshal@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEBA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<std::wstring>(std::wstring *)
0x1400741fa  nop
0x1400741fb  mov     edx, 0C037010Dh
0x140074200  mov     rcx, rax
0x140074203  call    ?ThrowOnUnmarshalError@Marshal@@YAXAEBU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@J@Z; Marshal::ThrowOnUnmarshalError(std::pair<bool,std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>> const &,long)
0x140074208  nop
0x140074209  lea     rcx, [rsp+1A0h+var_158]
0x14007420e  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x140074213  mov     rcx, [rdi+80h]
0x14007421a  lea     rdx, [rbp+0A0h+var_108]
0x14007421e  cmp     [rsi+20h], r15d
0x140074222  jnz     short loc_14007422B
0x140074224  call    ?AddDeviceInterface@ContainerUtilities@ComputeService@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ComputeService::ContainerUtilities::AddDeviceInterface(void *,std::wstring const &)
0x140074229  jmp     short loc_140074231
0x14007422b  call    ?RemoveDeviceInterface@ContainerUtilities@ComputeService@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ComputeService::ContainerUtilities::RemoveDeviceInterface(void *,std::wstring const &)
0x140074230  nop
0x140074231  lea     rcx, [rbp+0A0h+var_108]; this
0x140074235  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14007423a  jmp     loc_1400747F5
0x14007423f  lea     r8, qword_1403DBD10
0x140074246  mov     rdx, rsi
0x140074249  lea     rcx, [rsp+1A0h+var_160]; void *
0x14007424e  call    ??$MatchResourcePath@$0A@@Management@ComputeService@@YA?AV?$optional@V?$array@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@AEBV?$basic_regex@GV?$regex_traits@G@std@@@3@@Z; ComputeService::Management::MatchResourcePath<0>(std::wstring const &,std::basic_regex<ushort,std::regex_traits<ushort>> const &)
0x140074253  mov     bl, [rax+20h]
0x140074256  lea     rcx, [rsp+1A0h+var_160]
0x14007425b  call    ??1?$_Optional_destruct_base@V?$array@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(void)
0x140074260  test    bl, bl
0x140074262  jz      loc_140074423
0x140074268  cmp     dword ptr [rsi+20h], 1
0x14007426c  setnbe  al
0x14007426f  mov     rcx, [rbp+0A8h]; this
0x140074276  test    al, al
0x140074278  jz      short loc_140074292
0x14007427a  mov     r9d, 80070032h; char *
0x140074280  lea     r8, aOnecoreVmCompu_136; "onecore\\vm\\compute\\management\\orche"...
0x140074287  mov     edx, 40Ch; void *
0x14007428c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140074292  lea     rcx, [rbp+0A0h+var_90]; this
0x140074296  call    ??0MappedDirectory@Resources@Containers@Schema@@QEAA@XZ; Schema::Containers::Resources::MappedDirectory::MappedDirectory(void)
0x14007429b  nop
0x14007429c  lea     rcx, [rsi+28h]
0x1400742a0  lea     r8, [rbp+0A0h+var_90]
0x1400742a4  lea     rdx, [rsp+1A0h+var_160]
0x1400742a9  call    ??$Unmarshal@UMappedDirectory@Resources@Containers@Schema@@@?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEBA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@PEAUMappedDirectory@Resources@Containers@Schema@@@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Schema::Containers::Resources::MappedDirectory>(Schema::Containers::Resources::MappedDirectory *)
0x1400742ae  nop
0x1400742af  mov     edx, 0C037010Dh
0x1400742b4  mov     rcx, rax
0x1400742b7  call    ?ThrowOnUnmarshalError@Marshal@@YAXAEBU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@J@Z; Marshal::ThrowOnUnmarshalError(std::pair<bool,std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>> const &,long)
0x1400742bc  nop
0x1400742bd  lea     rcx, [rsp+1A0h+var_158]
0x1400742c2  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x1400742c7  lea     rdx, [rbp+0A0h+var_90]
0x1400742cb  lea     rcx, [rbp+0A0h+var_E0]
0x1400742cf  call    ?NormalizeMappedDirectory@ContainerUtilities@ComputeService@@YA?AUMappedDirectory@Resources@Containers@Schema@@AEBU3456@@Z; ComputeService::ContainerUtilities::NormalizeMappedDirectory(Schema::Containers::Resources::MappedDirectory const &)
0x1400742d4  nop
0x1400742d5  cmp     [rsi+20h], r15d
0x1400742d9  jnz     short loc_14007433C
0x1400742db  lea     rdx, [rbp+0A0h+var_E0]; struct ComputeService::Management::SiloContainerState *
0x1400742df  mov     rcx, rdi; this
0x1400742e2  call    ?ValidateNewMappedDirectory@Details@Management@ComputeService@@YA_NPEBUSiloContainerState@23@AEBUMappedDirectory@Resources@Containers@Schema@@@Z; ComputeService::Management::Details::ValidateNewMappedDirectory(ComputeService::Management::SiloContainerState const *,Schema::Containers::Resources::MappedDirectory const &)
0x1400742e7  test    al, al
0x1400742e9  jz      loc_14007440B
0x1400742ef  lea     rdx, [rdi+90h]
0x1400742f6  mov     al, [rdi+0B1h]
0x1400742fc  mov     [rsp+1A0h+var_168], al
0x140074300  mov     [rsp+1A0h+var_170], 1
0x140074305  mov     al, [rbp+0A0h+var_97]
0x140074308  mov     byte ptr [rsp+1A0h+var_178], al
0x14007430c  mov     al, [rbp+0A0h+var_98]
0x14007430f  mov     byte ptr [rsp+1A0h+var_180], al
0x140074313  lea     r9, [rbp+0A0h+var_B8]
0x140074317  lea     r8, [rbp+0A0h+var_E0]
0x14007431b  mov     rcx, [rdi+80h]
0x140074322  call    ?AddMappedDirectoryFromPaths@ContainerUtilities@ComputeService@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11_N222@Z; ComputeService::ContainerUtilities::AddMappedDirectoryFromPaths(void *,std::wstring const &,std::wstring const &,std::wstring const &,bool,bool,bool,bool)
0x140074327  lea     rcx, [rdi+1B0h]
0x14007432e  lea     rdx, [rbp+0A0h+var_E0]
0x140074332  call    ??$_Emplace_one_at_back@UMappedDirectory@Resources@Containers@Schema@@@?$vector@UMappedDirectory@Resources@Containers@Schema@@V?$allocator@UMappedDirectory@Resources@Containers@Schema@@@std@@@std@@AEAAAEAUMappedDirectory@Resources@Containers@Schema@@$$QEAU2345@@Z; std::vector<Schema::Containers::Resources::MappedDirectory>::_Emplace_one_at_back<Schema::Containers::Resources::MappedDirectory>(Schema::Containers::Resources::MappedDirectory &&)
0x140074337  jmp     loc_14007440B
0x14007433c  cmp     dword ptr [rsi+20h], 1
0x140074340  jnz     loc_14007440B
0x140074346  mov     [rbp+0A0h+var_108], r15
0x14007434a  lea     r9, [rbp+0A0h+var_E0]
0x14007434e  mov     r8, [rdi+1B8h]
0x140074355  mov     rdx, [rdi+1B0h]
0x14007435c  lea     rcx, [rbp+0A0h+var_108]
0x140074360  call    std__find_if_std___Vector_iterator_std___Vector_val_std___Simple_types_Schema__Containers__Resources__MappedDirectory_______lambda_ca7641d4ba7a5b3de947fe0abe371a51___
0x140074365  mov     rbx, [rbp+0A0h+var_108]
0x140074369  cmp     rbx, [rdi+1B8h]
0x140074370  jnz     short loc_140074391
0x140074372  mov     rcx, [rbp+0A8h]; this
0x140074379  mov     r9d, 80070490h; char *
0x14007437f  lea     r8, aOnecoreVmCompu_136; "onecore\\vm\\compute\\management\\orche"...
0x140074386  mov     edx, 42Eh; void *
0x14007438b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140074391  lea     rdx, [rdi+90h]
0x140074398  mov     r9b, [rdi+0B1h]
0x14007439f  lea     r8, [rbp+0A0h+var_B8]
0x1400743a3  mov     rcx, [rdi+80h]
0x1400743aa  call    ?RemoveMappedDirectory@ContainerUtilities@ComputeService@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1_N@Z; ComputeService::ContainerUtilities::RemoveMappedDirectory(void *,std::wstring const &,std::wstring const &,bool)
0x1400743af  mov     r14, [rdi+1B8h]
0x1400743b6  lea     rsi, [rbx+50h]
0x1400743ba  jmp     short loc_1400743EE
0x1400743bc  mov     rdx, rsi
0x1400743bf  mov     rcx, rbx
0x1400743c2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400743c7  mov     eax, [rsi+20h]
0x1400743ca  mov     [rbx+20h], eax
0x1400743cd  lea     rdx, [rsi+28h]
0x1400743d1  lea     rcx, [rbx+28h]
0x1400743d5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400743da  mov     al, [rsi+48h]
0x1400743dd  mov     [rbx+48h], al
0x1400743e0  mov     al, [rsi+49h]
0x1400743e3  mov     [rbx+49h], al
0x1400743e6  add     rbx, 50h ; 'P'
0x1400743ea  add     rsi, 50h ; 'P'
0x1400743ee  cmp     rsi, r14
0x1400743f1  jnz     short loc_1400743BC
0x1400743f3  mov     rcx, [rdi+1B8h]
0x1400743fa  sub     rcx, 50h ; 'P'; this
0x1400743fe  call    ??1MappedDirectory@Resources@Containers@Schema@@QEAA@XZ; Schema::Containers::Resources::MappedDirectory::~MappedDirectory(void)
0x140074403  add     qword ptr [rdi+1B8h], 0FFFFFFFFFFFFFFB0h
0x14007440b  lea     rcx, [rbp+0A0h+var_E0]; this
0x14007440f  call    ??1MappedDirectory@Resources@Containers@Schema@@QEAA@XZ; Schema::Containers::Resources::MappedDirectory::~MappedDirectory(void)
0x140074414  nop
0x140074415  lea     rcx, [rbp+0A0h+var_90]; this
0x140074419  call    ??1MappedDirectory@Resources@Containers@Schema@@QEAA@XZ; Schema::Containers::Resources::MappedDirectory::~MappedDirectory(void)
0x14007441e  jmp     loc_1400747F5
0x140074423  lea     r8, qword_1403DBD38
0x14007442a  mov     rdx, rsi
0x14007442d  lea     rcx, [rsp+1A0h+var_160]; void *
0x140074432  call    ??$MatchResourcePath@$0A@@Management@ComputeService@@YA?AV?$optional@V?$array@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@AEBV?$basic_regex@GV?$regex_traits@G@std@@@3@@Z; ComputeService::Management::MatchResourcePath<0>(std::wstring const &,std::basic_regex<ushort,std::regex_traits<ushort>> const &)
0x140074437  mov     bl, [rax+20h]
0x14007443a  lea     rcx, [rsp+1A0h+var_160]
0x14007443f  call    ??1?$_Optional_destruct_base@V?$array@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(void)
0x140074444  test    bl, bl
0x140074446  jz      loc_1400745DC
0x14007444c  lea     rcx, [rbp+0A0h+var_E0]; this
0x140074450  call    ??0MappedPipe@Resources@Containers@Schema@@QEAA@XZ; Schema::Containers::Resources::MappedPipe::MappedPipe(void)
0x140074455  nop
0x140074456  lea     rcx, [rsi+28h]
0x14007445a  lea     r8, [rbp+0A0h+var_E0]
0x14007445e  lea     rdx, [rsp+1A0h+var_160]
0x140074463  call    ??$Unmarshal@UMappedPipe@Resources@Containers@Schema@@@?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEBA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@PEAUMappedPipe@Resources@Containers@Schema@@@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Schema::Containers::Resources::MappedPipe>(Schema::Containers::Resources::MappedPipe *)
0x140074468  nop
0x140074469  mov     edx, 0C037010Dh
0x14007446e  mov     rcx, rax
0x140074471  call    ?ThrowOnUnmarshalError@Marshal@@YAXAEBU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@J@Z; Marshal::ThrowOnUnmarshalError(std::pair<bool,std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>> const &,long)
0x140074476  nop
0x140074477  lea     rcx, [rsp+1A0h+var_158]
0x14007447c  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x140074481  mov     edx, [rsi+20h]
0x140074484  test    edx, edx
0x140074486  jz      loc_140074578
0x14007448c  cmp     edx, 1
0x14007448f  jz      short loc_1400744C0
0x140074491  mov     rcx, [rbp+0A8h]; this
0x140074498  mov     dword ptr [rsp+1A0h+var_178], edx; char *
0x14007449c  lea     rax, aRequestTypeD; "request type %d"
0x1400744a3  mov     qword ptr [rsp+1A0h+var_180], rax; unsigned int
0x1400744a8  mov     r9d, 32h ; '2'; char *
0x1400744ae  lea     r8, aOnecoreVmCompu_136; "onecore\\vm\\compute\\management\\orche"...
0x1400744b5  mov     edx, 453h; void *
0x1400744ba  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1400744c0  lea     r14, [rdi+1C8h]
0x1400744c7  mov     rsi, [r14]
0x1400744ca  mov     r12, [r14+8]
0x1400744ce  jmp     short loc_14007451E
0x1400744d0  mov     rdx, rsi; struct Schema::Containers::Resources::MappedPipe *
0x1400744d3  lea     rcx, [rsp+1A0h+var_160]; this
0x1400744d8  call    ??0MappedPipe@Resources@Containers@Schema@@QEAA@AEBU0123@@Z; Schema::Containers::Resources::MappedPipe::MappedPipe(Schema::Containers::Resources::MappedPipe const &)
0x1400744dd  mov     r15, rax
0x1400744e0  lea     rdx, [rbp+0A0h+var_E0]
0x1400744e4  cmp     [rbp+0A0h+var_C8], 7
0x1400744e9  cmova   rdx, [rbp+0A0h+var_E0]
0x1400744ee  cmp     qword ptr [rax+18h], 7
0x1400744f3  jbe     short loc_1400744FA
0x1400744f5  mov     rcx, [rax]
0x1400744f8  jmp     short loc_1400744FD
0x1400744fa  mov     rcx, r15
0x1400744fd  call    cs:__imp__o__wcsicmp
0x140074504  nop     dword ptr [rax+rax+00h]
0x140074509  mov     ebx, eax
0x14007450b  mov     rcx, r15; this
0x14007450e  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x140074513  xor     r15d, r15d
0x140074516  test    ebx, ebx
0x140074518  jz      short loc_140074523
0x14007451a  add     rsi, 48h ; 'H'
0x14007451e  cmp     rsi, r12
0x140074521  jnz     short loc_1400744D0
0x140074523  cmp     rsi, [rdi+1D0h]
0x14007452a  jnz     short loc_14007454B
0x14007452c  mov     rcx, [rbp+0A8h]; this
0x140074533  mov     r9d, 80070490h; char *
0x140074539  lea     r8, aOnecoreVmCompu_136; "onecore\\vm\\compute\\management\\orche"...
0x140074540  mov     edx, 44Dh; void *
0x140074545  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007454b  cmp     [rdi+0B1h], r15b
0x140074552  mov     rcx, r15
0x140074555  jnz     short loc_14007455E
0x140074557  mov     rcx, [rdi+80h]
0x14007455e  lea     rdx, [rbp+0A0h+var_E0]
0x140074562  call    ?RemoveMappedPipe@ContainerUtilities@ComputeService@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ComputeService::ContainerUtilities::RemoveMappedPipe(void *,std::wstring const &)
0x140074567  mov     r8, rsi
0x14007456a  lea     rdx, [rbp+0A0h+var_118]
0x14007456e  mov     rcx, r14
0x140074571  call    ?erase@?$vector@UMappedPipe@Resources@Containers@Schema@@V?$allocator@UMappedPipe@Resources@Containers@Schema@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UMappedPipe@Resources@Containers@Schema@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UMappedPipe@Resources@Containers@Schema@@@std@@@std@@@2@@Z; std::vector<Schema::Containers::Resources::MappedPipe>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<Schema::Containers::Resources::MappedPipe>>>)
0x140074576  jmp     short loc_1400745CE
0x140074578  cmp     [rdi+0B1h], r15b
0x14007457f  mov     rcx, r15
0x140074582  jnz     short loc_14007458B
0x140074584  mov     rcx, [rdi+80h]; this
0x14007458b  lea     rdx, [rbp+0A0h+var_E0]; void *
0x14007458f  call    ?AddMappedPipe@ContainerUtilities@ComputeService@@YAXPEAXAEBUMappedPipe@Resources@Containers@Schema@@@Z; ComputeService::ContainerUtilities::AddMappedPipe(void *,Schema::Containers::Resources::MappedPipe const &)
0x140074594  mov     rax, [rdi+1D0h]
0x14007459b  cmp     rax, [rdi+1D8h]
0x1400745a2  jz      short loc_1400745BA
0x1400745a4  lea     rdx, [rbp+0A0h+var_E0]
0x1400745a8  mov     rcx, rax
0x1400745ab  call    ??0MappedPipe@Resources@Containers@Schema@@QEAA@$$QEAU0123@@Z; Schema::Containers::Resources::MappedPipe::MappedPipe(Schema::Containers::Resources::MappedPipe &&)
0x1400745b0  add     qword ptr [rdi+1D0h], 48h ; 'H'
0x1400745b8  jmp     short loc_1400745CE
0x1400745ba  lea     r8, [rbp+0A0h+var_E0]
0x1400745be  mov     rdx, rax
0x1400745c1  lea     rcx, [rdi+1C8h]
0x1400745c8  call    ??$_Emplace_reallocate@UMappedPipe@Resources@Containers@Schema@@@?$vector@UMappedPipe@Resources@Containers@Schema@@V?$allocator@UMappedPipe@Resources@Containers@Schema@@@std@@@std@@AEAAPEAUMappedPipe@Resources@Containers@Schema@@QEAU2345@$$QEAU2345@@Z; std::vector<Schema::Containers::Resources::MappedPipe>::_Emplace_reallocate<Schema::Containers::Resources::MappedPipe>(Schema::Containers::Resources::MappedPipe * const,Schema::Containers::Resources::MappedPipe &&)
0x1400745cd  nop
0x1400745ce  lea     rcx, [rbp+0A0h+var_E0]; this
0x1400745d2  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x1400745d7  jmp     loc_1400747F5
0x1400745dc  lea     r8, qword_1403DBD60
0x1400745e3  mov     rdx, rsi
0x1400745e6  lea     rcx, [rsp+1A0h+var_160]; void *
0x1400745eb  call    ??$MatchResourcePath@$0A@@Management@ComputeService@@YA?AV?$optional@V?$array@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@AEBV?$basic_regex@GV?$regex_traits@G@std@@@3@@Z; ComputeService::Management::MatchResourcePath<0>(std::wstring const &,std::basic_regex<ushort,std::regex_traits<ushort>> const &)
0x1400745f0  mov     bl, [rax+20h]
0x1400745f3  lea     rcx, [rsp+1A0h+var_160]
0x1400745f8  call    ??1?$_Optional_destruct_base@V?$array@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::array<std::wstring,0>,0>::~_Optional_destruct_base<std::array<std::wstring,0>,0>(void)
0x1400745fd  test    bl, bl
0x1400745ff  jz      short loc_140074676
0x140074601  mov     rcx, [rbp+0A8h]; this
0x140074608  cmp     dword ptr [rsi+20h], 2
0x14007460c  jz      short loc_140074626
0x14007460e  mov     r9d, 80070032h; char *
0x140074614  lea     r8, aOnecoreVmCompu_136; "onecore\\vm\\compute\\management\\orche"...
  ... truncated ...
```
