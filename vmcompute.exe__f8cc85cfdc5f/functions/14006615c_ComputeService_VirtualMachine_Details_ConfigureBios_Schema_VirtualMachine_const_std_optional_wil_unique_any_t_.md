# ComputeService::VirtualMachine::Details::ConfigureBios(Schema::VirtualMachine const &,std::optional<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>> const &,uint,uint,IVmHandleBroker *)

- ea: `0x14006615c`
- end: `0x140066e7c`
- name: `?ConfigureBios@Details@VirtualMachine@ComputeService@@YA?AUBiosLoader@Bios@Devices@Config@@AEBU2Schema@@AEBV?$optional@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IIPEAUIVmHandleBroker@@@Z`
- size: `3360`
- prototype: `__int64 __usercall@<rax>(Config::Devices::Bios::BiosLoader *this@<rcx>, int, __int64)`
- caller_count: `1`
- callee_count: `40`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400d7cd4`

## callees

- `0x1400142a0`
- `0x140017040`
- `0x14001d490`
- `0x140024030`
- `0x140026a3c`
- `0x14002d818`
- `0x140043a64`
- `0x140044974`
- `0x140044aec`
- `0x1400451a0`
- `0x140061118`
- `0x14006615c`
- `0x140076340`
- `0x140077620`
- `0x140077ce4`
- `0x140077d4c`
- `0x1400851f0`
- `0x1400857b4`
- `0x140085800`
- `0x14009c7dc`
- `0x14009d75c`
- `0x1400a2114`
- `0x1400b1adc`
- `0x1400c40e0`
- `0x1400d46bc`
- `0x140109e40`
- `0x14010db64`
- `0x14010ddb4`
- `0x140131efc`
- `0x1401332f0`
- `0x140189f38`
- `0x14018c240`
- `0x140190b40`
- `0x140199d30`
- `0x1401afb38`
- `0x1401b04b8`
- `0x1401b0e4c`
- `0x1401fc08c`
- `0x1401fea50`
- `0x140200fd0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140066b07`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140066be8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140066b07`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140066be8`

## string_xrefs

- `0x1400661b3`: `onecore\vm\compute\management\orchestration\shared\vmconfig\configurationhelpers.cpp`
- `0x1400661e7`: `onecore\vm\compute\management\orchestration\shared\vmconfig\configurationhelpers.cpp`
- `0x140066255`: `onecore\vm\compute\management\orchestration\shared\vmconfig\configurationhelpers.cpp`
- `0x14006647d`: `onecore\vm\compute\management\orchestration\shared\vmconfig\configurationhelpers.cpp`
- `0x140066740`: `onecore\vm\compute\management\orchestration\shared\vmconfig\configurationhelpers.cpp`
- `0x140066b40`: `onecore\vm\compute\management\orchestration\shared\vmconfig\configurationhelpers.cpp`
- `0x140066c21`: `onecore\vm\compute\management\orchestration\shared\vmconfig\configurationhelpers.cpp`
- `0x140066d0e`: `onecore\vm\compute\management\orchestration\shared\vmconfig\configurationhelpers.cpp`
- `0x140066d78`: `onecore\vm\compute\management\orchestration\shared\vmconfig\configurationhelpers.cpp`
- `0x140066e2d`: `onecore\vm\compute\management\orchestration\shared\vmconfig\configurationhelpers.cpp`
- `0x140066751`: `RegistryChanges.AddHiveUri and RegistryChange.AddValues/DeleteValues both defined`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
Config::Devices::Bios::BiosLoader *__fastcall ComputeService::VirtualMachine::Details::ConfigureBios(
        Config::Devices::Bios::BiosLoader *this,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        __int64 a6)
{
  _BYTE *v9; // rax
  int v10; // ebx
  char **v11; // rcx
  char *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  BOOL AzureFeatureSetEnabled; // ebx
  const struct Schema::Registry::RegistryChanges *v16; // rdx
  int v17; // ecx
  int v18; // eax
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  _QWORD *v22; // r8
  __int64 v23; // rdx
  unsigned int i; // r8d
  __int64 v25; // r8
  _DWORD *j; // rdx
  __int64 v27; // rax
  __int64 v28; // rax
  bool HasSystemHiveChanges; // al
  __int64 v30; // rcx
  __int64 ImcDataFromHive; // rax
  char v32; // dl
  char v33; // dl
  char v34; // dl
  const WCHAR *v35; // rdi
  char *FileW; // rbx
  const WCHAR *v37; // rdi
  char *v38; // rbx
  __int64 v39; // rax
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  char *v42; // [rsp+40h] [rbp-C0h] BYREF
  int v43; // [rsp+48h] [rbp-B8h]
  _BYTE v44[32]; // [rsp+50h] [rbp-B0h] BYREF
  int v45; // [rsp+70h] [rbp-90h]
  _BYTE v46[40]; // [rsp+78h] [rbp-88h] BYREF
  Config::Devices::Bios::BiosLoader *v47; // [rsp+A0h] [rbp-60h]
  _BYTE v48[40]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 p_lpFileName; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v50; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v51; // [rsp+F0h] [rbp-10h]
  __int64 v52; // [rsp+100h] [rbp+0h] BYREF
  LPCWSTR lpFileName; // [rsp+110h] [rbp+10h] BYREF
  char v54[12]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v55[20]; // [rsp+124h] [rbp+24h] BYREF
  __int16 v56; // [rsp+138h] [rbp+38h] BYREF
  _QWORD v57[2]; // [rsp+140h] [rbp+40h] BYREF
  char v58[8]; // [rsp+150h] [rbp+50h] BYREF
  char v59[24]; // [rsp+158h] [rbp+58h] BYREF
  char v60; // [rsp+170h] [rbp+70h]
  char v61[32]; // [rsp+178h] [rbp+78h] BYREF
  char v62[40]; // [rsp+198h] [rbp+98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  v47 = this;
  v43 = 0;
  if ( !a6 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x58A,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmconfig\\configurationhelpers.cpp",
      (const char *)0x80004003LL,
      dwCreationDisposition);
  v9 = (_BYTE *)(a2 + 472);
  if ( *(_BYTE *)(a2 + 224) && *v9 )
  {
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x590,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmconfig\\configurationhelpers.cpp",
      (const char *)0x8007000DLL,
      dwCreationDisposition);
    LODWORD(v42) = 5;
    std::pair<std::wstring,enum Marshal::UnmarshalError>::pair<std::wstring,enum Marshal::UnmarshalError>(
      v48,
      L"Uefi and LinuxKernelDirect both defined",
      &v42);
    ComputeService::Reporting::FormatUnMarshalError(v46, v48);
    ComputeService::Reporting::LogAndThrowComputeError<std::wstring>(-2147024883);
  }
  if ( *(_BYTE *)(a2 + 256) && *v9 )
  {
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x596,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmconfig\\configurationhelpers.cpp",
      (const char *)0x8007000DLL,
      dwCreationDisposition);
    LODWORD(v42) = 5;
    std::pair<std::wstring,enum Marshal::UnmarshalError>::pair<std::wstring,enum Marshal::UnmarshalError>(
      v44,
      L"Pcat and LinuxKernelDirect both defined",
      &v42);
    ComputeService::Reporting::FormatUnMarshalError(&v50, v44);
    ComputeService::Reporting::LogAndThrowComputeError<std::wstring>(-2147024883);
  }
  if ( a4 < 0x900 )
  {
    if ( a4 < 0x803 )
    {
      if ( a4 < 0x802 )
      {
        if ( a4 < 0x801 )
        {
          v50 = 0;
          v11 = (char **)std::make_unique<Vml::VmMachineLocalSettingsStore,,0>(&p_lpFileName);
          v12 = *v11;
          *v11 = 0;
          v42 = v12;
          VirtualizationSettings::VirtualizationSettings(&v50, v13, v14, &v42);
          std::unique_ptr<ComputeService::Management::ComputeSystemConfiguration>::~unique_ptr<ComputeService::Management::ComputeSystemConfiguration>(&v42);
          std::unique_ptr<ComputeService::Management::ComputeSystemConfiguration>::~unique_ptr<ComputeService::Management::ComputeSystemConfiguration>(&p_lpFileName);
          AzureFeatureSetEnabled = VirtualizationSettings::GetAzureFeatureSetEnabled((VirtualizationSettings *)&v50);
          std::unique_ptr<ComputeService::Management::ComputeSystemConfiguration>::~unique_ptr<ComputeService::Management::ComputeSystemConfiguration>((char *)&v50 + 8);
          v10 = (AzureFeatureSetEnabled + 4) << 8;
        }
        else
        {
          v10 = 1280;
        }
      }
      else
      {
        v10 = 1536;
      }
    }
    else
    {
      v10 = 1792;
    }
  }
  else
  {
    v10 = 2048;
  }
  Config::Devices::Bios::BiosLoader::BiosLoader(this);
  v43 = 1;
  *(_DWORD *)this = v10;
  if ( *(_BYTE *)(a2 + 224) || *(_BYTE *)(a2 + 256) )
  {
    ComputeService::VirtualMachine::ConfigurationHelpers::GetDevicePlatformSettings(&lpFileName, a2);
    *(_OWORD *)((char *)this + 8) = *(_OWORD *)v55;
    std::wstring::operator=((char *)this + 24, &v56);
    std::wstring::operator=((char *)this + 64, v59);
    std::wstring::operator=((char *)this + 96, v61);
    std::wstring::operator=((char *)this + 128, v62);
    *((_BYTE *)this + 496) = v55[18];
    *((_BYTE *)this + 56) = *(_BYTE *)(a2 + 264) == 0;
    Config::Devices::Chipset::HclDevicePlatformSettings::~HclDevicePlatformSettings((Config::Devices::Chipset::HclDevicePlatformSettings *)&lpFileName);
    if ( *(_BYTE *)(a2 + 256) )
    {
      *((_DWORD *)this + 114) = 1;
      *((_BYTE *)this + 184) = 0;
      *((_DWORD *)this + 47) = 4;
      *((_BYTE *)this + 212) = 0;
      v22 = (_QWORD *)(a2 + 232);
      if ( !*(_BYTE *)(a2 + 256) )
        __fastfail(5u);
      v23 = *(_QWORD *)(a2 + 240);
      if ( *v22 == v23 )
      {
        for ( i = 0; i < 4; ++i )
          *((_DWORD *)this + i + 49) = (0x76540321u >> (4 * i)) & 3;
      }
      else
      {
        v50 = 0;
        v51 = 0;
        std::vector<enum Schema::VirtualMachines::Resources::BootDevice>::_Construct_n<enum Schema::VirtualMachines::Resources::BootDevice * const &,enum Schema::VirtualMachines::Resources::BootDevice * const &>(
          &v50,
          (v23 - *v22) >> 2);
        v25 = 0;
        for ( j = (_DWORD *)v50; j != *((_DWORD **)&v50 + 1); ++j )
        {
          *((_DWORD *)this + (int)v25 + 49) = *j;
          v25 = (unsigned int)(v25 + 1);
        }
        std::vector<enum Schema::Requests::System::NetworkProperty>::_Tidy(&v50, j, v25);
      }
      goto LABEL_144;
    }
  }
  if ( *(_BYTE *)(a2 + 224) )
  {
    if ( *(_BYTE *)(a2 + 36) )
    {
      *((_BYTE *)this + 160) = 1;
      if ( !*(_BYTE *)(a2 + 224) )
        __fastfail(5u);
      if ( !*(_BYTE *)(a2 + 36) )
        __fastfail(5u);
      *(_OWORD *)((char *)this + 164) = *(_OWORD *)(a2 + 20);
    }
    if ( !*(_BYTE *)(a2 + 224) )
      __fastfail(5u);
    v17 = *(_DWORD *)(a2 + 40);
    if ( !v17 || (v18 = 1, v17 != 1) )
      v18 = 0;
    *((_DWORD *)this + 153) = v18;
    *((_DWORD *)this + 45) = 0;
    if ( !*(_BYTE *)(a2 + 224) )
      __fastfail(5u);
    if ( *(_BYTE *)(a2 + 16) )
      *((_DWORD *)this + 45) = 1;
    *((_BYTE *)this + 184) = 0;
    *((_DWORD *)this + 47) = 4;
    if ( !*(_BYTE *)(a2 + 224) )
      __fastfail(5u);
    *((_BYTE *)this + 608) = *(_BYTE *)(a2 + 172);
    *((_BYTE *)this + 616) = *(_BYTE *)(a2 + 1396);
    if ( !*(_BYTE *)(a2 + 224) )
      __fastfail(5u);
    v19 = *(_DWORD *)(a2 + 168);
    if ( v19 )
    {
      v20 = v19 - 1;
      if ( v20 )
      {
        v21 = v20 - 1;
        if ( v21 )
        {
          if ( v21 != 1 )
          {
            wil::details::in1diag3::Log_Hr(
              retaddr,
              (void *)0x611,
              (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmconfig\\configurationhelpers.cpp",
              (const char *)0x8007000DLL,
              dwCreationDisposition);
            LODWORD(v42) = 8;
            std::pair<std::wstring,enum Marshal::UnmarshalError>::pair<std::wstring,enum Marshal::UnmarshalError>(
              v44,
              L"SerialConsole",
              &v42);
            ComputeService::Reporting::FormatUnMarshalError(&v50, v44);
            ComputeService::Reporting::LogAndThrowComputeError<std::wstring>(-2147024883);
          }
          *((_DWORD *)this + 48) = 2;
        }
        else
        {
          *((_DWORD *)this + 48) = 1;
        }
      }
      else
      {
        *((_DWORD *)this + 48) = 3;
      }
    }
    else
    {
      *((_DWORD *)this + 48) = 0;
    }
    if ( !*(_BYTE *)(a2 + 224) )
      __fastfail(5u);
    if ( *(_BYTE *)(a2 + 160) )
    {
      Schema::VirtualMachines::Resources::UefiBootEntry::UefiBootEntry((Schema::VirtualMachines::Resources::UefiBootEntry *)&lpFileName);
      if ( !*(_BYTE *)(a2 + 224) )
        __fastfail(5u);
      if ( !*(_BYTE *)(a2 + 160) )
        __fastfail(5u);
      LODWORD(lpFileName) = *(_DWORD *)(a2 + 48);
      v56 = *(_WORD *)(a2 + 88);
      std::wstring::operator=(v57, a2 + 96);
      v27 = lambda_bffcbee7f2770ed84e920f222a7c63ec_::_lambda_bffcbee7f2770ed84e920f222a7c63ec_(&v50, &lpFileName, a2);
      v28 = lambda_74e1a5e0ac4310b1415dfc28133860d9_::operator()(v27, v46);
      std::wstring::operator=(v54, v28);
      Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v46);
      Schema::VirtualMachines::Resources::UefiBootEntry::operator=((char *)this + 336, &lpFileName);
      *((_BYTE *)this + 448) = 1;
      Schema::VirtualMachines::Resources::UefiBootEntry::~UefiBootEntry((Schema::VirtualMachines::Resources::UefiBootEntry *)&lpFileName);
    }
    HasSystemHiveChanges = ComputeService::ContainerDefinition::HasSystemHiveChanges(
                             (ComputeService::ContainerDefinition *)(a2 + 2224),
                             v16);
    if ( *(_BYTE *)(a3 + 8) )
    {
      if ( HasSystemHiveChanges )
      {
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x639,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmconfig\\configurationhelpers.cpp",
          (const char *)0x8007000DLL,
          dwCreationDisposition);
        std::wstring::wstring(v44, L"RegistryChanges.AddHiveUri and RegistryChange.AddValues/DeleteValues both defined");
        v45 = 5;
        ComputeService::Reporting::FormatUnMarshalError(&v50, v44);
        ComputeService::Reporting::LogAndThrowComputeError<std::wstring>(-2147024883);
      }
      ImcDataFromHive = ComputeService::ContainerDefinition::GetImcDataFromHive(&v50, a3);
    }
    else
    {
      if ( !HasSystemHiveChanges )
      {
LABEL_75:
        if ( *(_BYTE *)(a2 + 696) )
        {
          if ( *(_QWORD *)(a2 + 496) )
            std::wstring::operator=((char *)this + 624, a2 + 480);
          if ( !*(_BYTE *)(a2 + 696) )
            __fastfail(5u);
          if ( *(_QWORD *)(a2 + 528) )
            std::wstring::operator=((char *)this + 656, a2 + 512);
          if ( !*(_BYTE *)(a2 + 696) )
            __fastfail(5u);
          if ( *(_QWORD *)(a2 + 560) )
            std::wstring::operator=((char *)this + 688, a2 + 544);
          if ( !*(_BYTE *)(a2 + 696) )
            __fastfail(5u);
          if ( *(_QWORD *)(a2 + 592) )
            std::wstring::operator=((char *)this + 24, a2 + 576);
          if ( !*(_BYTE *)(a2 + 696) )
            __fastfail(5u);
          if ( *(_BYTE *)(a2 + 624) )
            *(_OWORD *)((char *)this + 8) = *(_OWORD *)(a2 + 608);
          if ( !*(_BYTE *)(a2 + 696) )
            __fastfail(5u);
          if ( *(_QWORD *)(a2 + 648) )
            std::wstring::operator=((char *)this + 720, a2 + 632);
          if ( !*(_BYTE *)(a2 + 696) )
            __fastfail(5u);
          if ( *(_QWORD *)(a2 + 680) )
            std::wstring::operator=((char *)this + 752, a2 + 664);
        }
        if ( *(_QWORD *)(a2 + 720) )
          std::wstring::operator=((char *)this + 784, a2 + 704);
        if ( !*(_BYTE *)(a2 + 224) )
          __fastfail(5u);
        if ( *(_BYTE *)(a2 + 173) )
          *((_DWORD *)this + 45) |= 2u;
        if ( !*(_BYTE *)(a2 + 224) )
          __fastfail(5u);
        v32 = *(_BYTE *)(a2 + 174);
        if ( v32 )
          *((_BYTE *)this + 184) = v32;
        if ( !*(_BYTE *)(a2 + 224) )
          __fastfail(5u);
        if ( *(_QWORD *)(a2 + 176) != *(_QWORD *)(a2 + 184) )
          std::vector<unsigned char>::operator=((char *)this + 240, a2 + 176);
        if ( !*(_BYTE *)(a2 + 224) )
          __fastfail(5u);
        if ( *(_BYTE *)(a2 + 201) )
          vmstd::optional<bool>::operator=((char *)this + 264);
        if ( !*(_BYTE *)(a2 + 224) )
          __fastfail(5u);
        v33 = *(_BYTE *)(a2 + 202);
        if ( v33 )
          *((_BYTE *)this + 816) = v33;
        if ( !*(_BYTE *)(a2 + 224) )
          __fastfail(5u);
        v34 = *(_BYTE *)(a2 + 203);
        if ( v34 )
          *((_BYTE *)this + 212) = v34;
        if ( !*(_BYTE *)(a2 + 224) )
          __fastfail(5u);
        if ( *(_BYTE *)(a2 + 220) )
          vmstd::optional<_GUID>::operator=((char *)this + 216);
        goto LABEL_144;
      }
      ImcDataFromHive = ComputeService::ContainerDefinition::ApplyRegistryChangesToOfflineHive(&v50, v30);
    }
    std::vector<unsigned char>::operator=((char *)this + 240, ImcDataFromHive);
    std::vector<unsigned char>::_Tidy(&v50);
    goto LABEL_75;
  }
  p_lpFileName = (__int64)&lpFileName;
  std::wstring::wstring(&lpFileName);
  std::wstring::wstring(&v55[12]);
  std::wstring::wstring(v58);
  v60 = *(_BYTE *)(a2 + 472);
  if ( !v60 )
  {
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x6C2,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmconfig\\configurationhelpers.cpp",
      (const char *)0x8007000DLL,
      dwCreationDisposition);
    std::wstring::wstring(v44, L"Neither Uefi nor LinuxKernelDirect defined");
    v45 = 5;
    ComputeService::Reporting::FormatUnMarshalError(v46, v44);
    ComputeService::Reporting::LogAndThrowComputeError<std::wstring>(-2147024883);
  }
  Schema::VirtualMachines::Resources::LinuxKernelDirect::operator=((char *)this + 504, &lpFileName);
  *((_BYTE *)this + 600) = 1;
  *((_DWORD *)this + 114) = 2;
  if ( !v60 )
    __fastfail(5u);
  v35 = (const WCHAR *)&lpFileName;
  if ( *(_QWORD *)&v55[4] > 7u )
    v35 = lpFileName;
  FileW = (char *)CreateFileW(v35, 0x80000000, 5u, 0, 3u, 0x80u, 0);
  p_lpFileName = (__int64)FileW;
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x6A9,
    (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmconfig\\configurationhelpers.cpp",
    (const char *)((unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL),
    (bool)"%ls",
    (const char *)v35);
  v52 = (__int64)&v42;
  v42 = FileW;
  p_lpFileName = -1;
  std::wstring::wstring(&v50, L"kernel");
  VmHandleBrokerUtils::PutHandle(a6, &v50, 0, &v42);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)&v50);
  if ( !v60 )
    __fastfail(5u);
  if ( v57[0] )
  {
    v37 = (const WCHAR *)&v55[12];
    if ( v57[1] > 7u )
      v37 = *(const WCHAR **)&v55[12];
    v38 = (char *)CreateFileW(v37, 0x80000000, 5u, 0, 3u, 0x80u, 0);
    v52 = (__int64)v38;
    wil::details::in1diag3::Throw_GetLastErrorIfMsg(
      retaddr,
      (void *)0x6B9,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmconfig\\configurationhelpers.cpp",
      (const char *)((unsigned __int64)(v38 - 1) > 0xFFFFFFFFFFFFFFFDuLL),
      (bool)"%ls",
      (const char *)v37);
    *(_QWORD *)&v50 = &v42;
    v42 = v38;
    v52 = -1;
    std::wstring::wstring(v46, L"initrd");
    VmHandleBrokerUtils::PutHandle(a6, v46, 0, &v42);
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v46);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v52);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&p_lpFileName);
  Schema::VirtualMachines::Resources::LinuxKernelDirect::~LinuxKernelDirect((Schema::VirtualMachines::Resources::LinuxKernelDirect *)&lpFileName);
LABEL_144:
  if ( *(_BYTE *)(a2 + 3008) && *(_DWORD *)(a2 + 2816) )
    *((_DWORD *)this + 114) = 3;
  if ( *(_BYTE *)(a2 + 752) )
  {
    if ( *(_BYTE *)(a2 + 696) )
    {
      if ( !*(_BYTE *)(a2 + 752) )
        __fastfail(5u);
      if ( !*(_BYTE *)(a2 + 624) )
        __fastfail(5u);
      v39 = *(_QWORD *)(a2 + 608) - *(_QWORD *)(a2 + 736);
      if ( !v39 )
        v39 = *(_QWORD *)(a2 + 616) - *(_QWORD *)(a2 + 744);
      if ( v39 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6D1,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmconfig\\configurationhelpers.cpp",
          (const char *)0x80070057LL,
          dwCreationDisposition);
    }
    if ( !*(_BYTE *)(a2 + 752) )
      __fastfail(5u);
    *(_OWORD *)((char *)this + 8) = *(_OWORD *)(a2 + 736);
  }
  if ( *(_BYTE *)(a2 + 792) )
  {
    if ( *(_BYTE *)(a2 + 696) )
    {
      if ( !*(_BYTE *)(a2 + 792) )
        __fastfail(5u);
      if ( (unsigned __int8)std::operator!=<unsigned short>(a2 + 576) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6D8,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmconfig\\configurationhelpers.cpp",
          (const char *)0x80070057LL,
          dwCreationDisposition);
    }
    if ( !*(_BYTE *)(a2 + 792) )
      __fastfail(5u);
    std::wstring::operator=((char *)this + 24, a2 + 760);
  }
  if ( *(_BYTE *)(a2 + 876) )
    *((_DWORD *)this + 47) = *(_DWORD *)(a2 + 872);
  if ( *(_BYTE *)(a2 + 912) )
    std::wstring::operator=((char *)this + 464, a2 + 880);
  if ( *(_BYTE *)(a2 + 801) || *(_BYTE *)(a2 + 864) )
    *((_DWORD *)this + 114) = 3;
  return this;
}

```

## disassembly

```asm
0x14006615c  push    rbp
0x14006615e  push    rbx
0x14006615f  push    rsi
0x140066160  push    rdi
0x140066161  push    r13
0x140066163  push    r14
0x140066165  push    r15
0x140066167  lea     rbp, [rsp-0D0h]
0x14006616f  sub     rsp, 1D0h
0x140066176  mov     rax, cs:__security_cookie
0x14006617d  xor     rax, rsp
0x140066180  mov     [rbp+100h+var_40], rax
0x140066187  mov     rdi, r8
0x14006618a  mov     rsi, rdx
0x14006618d  mov     r15, rcx
0x140066190  mov     [rbp+100h+var_160], rcx
0x140066194  mov     r13, [rbp+100h+arg_28]
0x14006619b  xor     ebx, ebx
0x14006619d  mov     [rsp+200h+var_1B8], ebx
0x1400661a1  mov     rcx, [rbp+108h]; this
0x1400661a8  test    r13, r13
0x1400661ab  jnz     short loc_1400661C5
0x1400661ad  mov     r9d, 80004003h; char *
0x1400661b3  lea     r8, aOnecoreVmCompu_72; "onecore\\vm\\compute\\management\\orche"...
0x1400661ba  mov     edx, 58Ah; void *
0x1400661bf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400661c5  lea     rax, [rdx+1D8h]
0x1400661cc  cmp     [rdx+0E0h], bl
0x1400661d2  jz      short loc_14006623A
0x1400661d4  cmp     [rax], bl
0x1400661d6  jz      short loc_14006623A
0x1400661d8  mov     rcx, [rbp+108h]; this
0x1400661df  mov     ebx, 8007000Dh
0x1400661e4  mov     r9d, ebx; char *
0x1400661e7  lea     r8, aOnecoreVmCompu_72; "onecore\\vm\\compute\\management\\orche"...
0x1400661ee  mov     edx, 590h; void *
0x1400661f3  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1400661f8  mov     r14d, 5
0x1400661fe  mov     dword ptr [rsp+200h+var_1C0], r14d
0x140066203  lea     r8, [rsp+200h+var_1C0]
0x140066208  lea     rdx, aUefiAndLinuxke; "Uefi and LinuxKernelDirect both defined"
0x14006620f  lea     rcx, [rbp+100h+var_150]
0x140066213  call    ??$?0AEAY07$$CBGW4UnmarshalError@Marshal@@$0A@@?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@QEAA@AEAY07$$CBG$$QEAW4UnmarshalError@Marshal@@@Z; std::pair<std::wstring,Marshal::UnmarshalError>::pair<std::wstring,Marshal::UnmarshalError>(ushort const (&)[8],Marshal::UnmarshalError &&)
0x140066218  nop
0x140066219  lea     rdx, [rbp+100h+var_150]
0x14006621d  lea     rcx, [rsp+200h+var_188]
0x140066222  call    ?FormatUnMarshalError@Reporting@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@4@@Z; ComputeService::Reporting::FormatUnMarshalError(std::pair<std::wstring,Marshal::UnmarshalError> const &)
0x140066227  nop
0x140066228  mov     r8, rax
0x14006622b  lea     rdx, MSVCOMP_INVALID_CONFIGURATION_DOCUMENT
0x140066232  mov     ecx, ebx; int
0x140066234  call    ??$LogAndThrowComputeError@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Reporting@ComputeService@@YAXJPEBU_EVENT_DESCRIPTOR@@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ComputeService::Reporting::LogAndThrowComputeError<std::wstring>(long,_EVENT_DESCRIPTOR const *,std::wstring &&)
0x14006623a  cmp     [rdx+100h], bl
0x140066240  jz      short loc_1400662A9
0x140066242  cmp     [rax], bl
0x140066244  jz      short loc_1400662A9
0x140066246  mov     rcx, [rbp+108h]; this
0x14006624d  mov     ebx, 8007000Dh
0x140066252  mov     r9d, ebx; char *
0x140066255  lea     r8, aOnecoreVmCompu_72; "onecore\\vm\\compute\\management\\orche"...
0x14006625c  mov     edx, 596h; void *
0x140066261  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x140066266  mov     r14d, 5
0x14006626c  mov     dword ptr [rsp+200h+var_1C0], r14d
0x140066271  lea     r8, [rsp+200h+var_1C0]
0x140066276  lea     rdx, aPcatAndLinuxke; "Pcat and LinuxKernelDirect both defined"
0x14006627d  lea     rcx, [rsp+200h+var_1B0]
0x140066282  call    ??$?0AEAY07$$CBGW4UnmarshalError@Marshal@@$0A@@?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@QEAA@AEAY07$$CBG$$QEAW4UnmarshalError@Marshal@@@Z; std::pair<std::wstring,Marshal::UnmarshalError>::pair<std::wstring,Marshal::UnmarshalError>(ushort const (&)[8],Marshal::UnmarshalError &&)
0x140066287  nop
0x140066288  lea     rdx, [rsp+200h+var_1B0]
0x14006628d  lea     rcx, [rbp+100h+var_120]
0x140066291  call    ?FormatUnMarshalError@Reporting@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@4@@Z; ComputeService::Reporting::FormatUnMarshalError(std::pair<std::wstring,Marshal::UnmarshalError> const &)
0x140066296  nop
0x140066297  mov     r8, rax
0x14006629a  lea     rdx, MSVCOMP_INVALID_CONFIGURATION_DOCUMENT
0x1400662a1  mov     ecx, ebx; int
0x1400662a3  call    ??$LogAndThrowComputeError@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Reporting@ComputeService@@YAXJPEBU_EVENT_DESCRIPTOR@@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ComputeService::Reporting::LogAndThrowComputeError<std::wstring>(long,_EVENT_DESCRIPTOR const *,std::wstring &&)
0x1400662a9  cmp     r9d, 900h
0x1400662b0  jb      short loc_1400662BC
0x1400662b2  mov     ebx, 800h
0x1400662b7  jmp     loc_140066348
0x1400662bc  cmp     r9d, 803h
0x1400662c3  jb      short loc_1400662CC
0x1400662c5  mov     ebx, 700h
0x1400662ca  jmp     short loc_140066348
0x1400662cc  cmp     r9d, 802h
0x1400662d3  jb      short loc_1400662DC
0x1400662d5  mov     ebx, 600h
0x1400662da  jmp     short loc_140066348
0x1400662dc  cmp     r9d, 801h
0x1400662e3  jb      short loc_1400662EC
0x1400662e5  mov     ebx, 500h
0x1400662ea  jmp     short loc_140066348
0x1400662ec  xorps   xmm0, xmm0
0x1400662ef  movups  [rbp+100h+var_120], xmm0
0x1400662f3  lea     rcx, [rbp+100h+var_128]
0x1400662f7  call    ??$make_unique@VVmMachineLocalSettingsStore@Vml@@$$V$0A@@std@@YA?AV?$unique_ptr@VVmMachineLocalSettingsStore@Vml@@U?$default_delete@VVmMachineLocalSettingsStore@Vml@@@std@@@0@XZ; std::make_unique<Vml::VmMachineLocalSettingsStore,,0>(void)
0x1400662fc  mov     rcx, rax
0x1400662ff  mov     rax, [rax]
0x140066302  mov     [rcx], rbx
0x140066305  mov     [rsp+200h+var_1C0], rax
0x14006630a  lea     r9, [rsp+200h+var_1C0]
0x14006630f  lea     rcx, [rbp+100h+var_120]
0x140066313  call    ??0VirtualizationSettings@@QEAA@_NPEBG$$QEAV?$unique_ptr@VISettingsStore@@U?$default_delete@VISettingsStore@@@std@@@std@@@Z; VirtualizationSettings::VirtualizationSettings(bool,ushort const *,std::unique_ptr<ISettingsStore> &&)
0x140066318  nop
0x140066319  lea     rcx, [rsp+200h+var_1C0]
0x14006631e  call    ??1?$unique_ptr@UComputeSystemConfiguration@Management@ComputeService@@U?$default_delete@UComputeSystemConfiguration@Management@ComputeService@@@std@@@std@@QEAA@XZ; std::unique_ptr<ComputeService::Management::ComputeSystemConfiguration>::~unique_ptr<ComputeService::Management::ComputeSystemConfiguration>(void)
0x140066323  nop
0x140066324  lea     rcx, [rbp+100h+var_128]
0x140066328  call    ??1?$unique_ptr@UComputeSystemConfiguration@Management@ComputeService@@U?$default_delete@UComputeSystemConfiguration@Management@ComputeService@@@std@@@std@@QEAA@XZ; std::unique_ptr<ComputeService::Management::ComputeSystemConfiguration>::~unique_ptr<ComputeService::Management::ComputeSystemConfiguration>(void)
0x14006632d  lea     rcx, [rbp+100h+var_120]; this
0x140066331  call    ?GetAzureFeatureSetEnabled@VirtualizationSettings@@UEBA_NXZ; VirtualizationSettings::GetAzureFeatureSetEnabled(void)
0x140066336  movzx   ebx, al
0x140066339  lea     rcx, [rbp+100h+var_120+8]
0x14006633d  call    ??1?$unique_ptr@UComputeSystemConfiguration@Management@ComputeService@@U?$default_delete@UComputeSystemConfiguration@Management@ComputeService@@@std@@@std@@QEAA@XZ; std::unique_ptr<ComputeService::Management::ComputeSystemConfiguration>::~unique_ptr<ComputeService::Management::ComputeSystemConfiguration>(void)
0x140066342  add     ebx, 4
0x140066345  shl     ebx, 8
0x140066348  mov     rcx, r15; this
0x14006634b  call    ??0BiosLoader@Bios@Devices@Config@@QEAA@XZ; Config::Devices::Bios::BiosLoader::BiosLoader(void)
0x140066350  mov     r10d, 1
0x140066356  mov     [rsp+200h+var_1B8], r10d
0x14006635b  mov     [r15], ebx
0x14006635e  xor     ebx, ebx
0x140066360  cmp     [rsi+0E0h], bl
0x140066366  jnz     loc_1400664CE
0x14006636c  cmp     [rsi+100h], bl
0x140066372  jnz     loc_1400664CE
0x140066378  cmp     [rsi+0E0h], bl
0x14006637e  jz      loc_140066A59
0x140066384  mov     r14d, 5
0x14006638a  cmp     [rsi+24h], bl
0x14006638d  jz      short loc_1400663BA
0x14006638f  mov     [r15+0A0h], r10b
0x140066396  cmp     [rsi+0E0h], bl
0x14006639c  jnz     short loc_1400663A3
0x14006639e  mov     ecx, r14d
0x1400663a1  int     29h; Win8: RtlFailFast(ecx)
0x1400663a3  cmp     [rsi+24h], bl
0x1400663a6  jnz     short loc_1400663AD
0x1400663a8  mov     rcx, r14
0x1400663ab  int     29h; Win8: RtlFailFast(ecx)
0x1400663ad  movups  xmm0, xmmword ptr [rsi+14h]
0x1400663b1  movdqu  xmmword ptr [r15+0A4h], xmm0
0x1400663ba  cmp     [rsi+0E0h], bl
0x1400663c0  jnz     short loc_1400663C7
0x1400663c2  mov     rcx, r14
0x1400663c5  int     29h; Win8: RtlFailFast(ecx)
0x1400663c7  mov     ecx, [rsi+28h]
0x1400663ca  test    ecx, ecx
0x1400663cc  jz      short loc_1400663D6
0x1400663ce  cmp     ecx, 1
0x1400663d1  mov     eax, r10d
0x1400663d4  jz      short loc_1400663D8
0x1400663d6  mov     eax, ebx
0x1400663d8  mov     [r15+264h], eax
0x1400663df  mov     [r15+0B4h], ebx
0x1400663e6  cmp     [rsi+0E0h], bl
0x1400663ec  jnz     short loc_1400663F3
0x1400663ee  mov     rcx, r14
0x1400663f1  int     29h; Win8: RtlFailFast(ecx)
0x1400663f3  cmp     [rsi+10h], bl
0x1400663f6  jz      short loc_1400663FF
0x1400663f8  mov     [r15+0B4h], r10d
0x1400663ff  mov     [r15+0B8h], bl
0x140066406  mov     dword ptr [r15+0BCh], 4
0x140066411  cmp     [rsi+0E0h], bl
0x140066417  jnz     short loc_14006641E
0x140066419  mov     rcx, r14
0x14006641c  int     29h; Win8: RtlFailFast(ecx)
0x14006641e  mov     al, [rsi+0ACh]
0x140066424  mov     [r15+260h], al
0x14006642b  mov     al, [rsi+574h]
0x140066431  mov     [r15+268h], al
0x140066438  cmp     [rsi+0E0h], bl
0x14006643e  jnz     short loc_140066445
0x140066440  mov     rcx, r14
0x140066443  int     29h; Win8: RtlFailFast(ecx)
0x140066445  mov     ecx, [rsi+0A8h]
0x14006644b  test    ecx, ecx
0x14006644d  jz      loc_14006663C
0x140066453  sub     ecx, 1
0x140066456  jz      loc_14006662F
0x14006645c  sub     ecx, 1
0x14006645f  jz      loc_140066626
0x140066465  cmp     ecx, 1
0x140066468  jz      loc_140066619
0x14006646e  mov     rcx, [rbp+108h]; this
0x140066475  mov     ebx, 8007000Dh
0x14006647a  mov     r9d, ebx; char *
0x14006647d  lea     r8, aOnecoreVmCompu_72; "onecore\\vm\\compute\\management\\orche"...
0x140066484  mov     edx, 611h; void *
0x140066489  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x14006648e  mov     dword ptr [rsp+200h+var_1C0], 8
0x140066496  lea     r8, [rsp+200h+var_1C0]
0x14006649b  lea     rdx, aSerialconsole; "SerialConsole"
0x1400664a2  lea     rcx, [rsp+200h+var_1B0]
0x1400664a7  call    ??$?0AEAY07$$CBGW4UnmarshalError@Marshal@@$0A@@?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@QEAA@AEAY07$$CBG$$QEAW4UnmarshalError@Marshal@@@Z; std::pair<std::wstring,Marshal::UnmarshalError>::pair<std::wstring,Marshal::UnmarshalError>(ushort const (&)[8],Marshal::UnmarshalError &&)
0x1400664ac  nop
0x1400664ad  lea     rdx, [rsp+200h+var_1B0]
0x1400664b2  lea     rcx, [rbp+100h+var_120]
0x1400664b6  call    ?FormatUnMarshalError@Reporting@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@4@@Z; ComputeService::Reporting::FormatUnMarshalError(std::pair<std::wstring,Marshal::UnmarshalError> const &)
0x1400664bb  nop
0x1400664bc  mov     r8, rax
0x1400664bf  lea     rdx, MSVCOMP_INVALID_CONFIGURATION_DOCUMENT
0x1400664c6  mov     ecx, ebx; int
0x1400664c8  call    ??$LogAndThrowComputeError@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Reporting@ComputeService@@YAXJPEBU_EVENT_DESCRIPTOR@@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ComputeService::Reporting::LogAndThrowComputeError<std::wstring>(long,_EVENT_DESCRIPTOR const *,std::wstring &&)
0x1400664ce  mov     rdx, rsi
0x1400664d1  lea     rcx, [rbp+100h+lpFileName]
0x1400664d5  call    ?GetDevicePlatformSettings@ConfigurationHelpers@VirtualMachine@ComputeService@@YA?AUHclDevicePlatformSettings@Chipset@Devices@Config@@AEBU2Schema@@@Z; ComputeService::VirtualMachine::ConfigurationHelpers::GetDevicePlatformSettings(Schema::VirtualMachine const &)
0x1400664da  nop
0x1400664db  movups  xmm0, xmmword ptr [rbp+100h+var_DC]
0x1400664df  movdqu  xmmword ptr [r15+8], xmm0
0x1400664e5  lea     rcx, [r15+18h]
0x1400664e9  lea     rdx, [rbp+100h+var_C8]
0x1400664ed  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1400664f2  lea     rcx, [r15+40h]
0x1400664f6  lea     rdx, [rbp+100h+var_A8]
0x1400664fa  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1400664ff  lea     rcx, [r15+60h]
0x140066503  lea     rdx, [rbp+100h+var_88]
0x140066507  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14006650c  lea     rcx, [r15+80h]
0x140066513  lea     rdx, [rbp+100h+var_68]
0x14006651a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14006651f  mov     al, [rbp+100h+var_CA]
0x140066522  mov     [r15+1F0h], al
0x140066529  cmp     [rsi+108h], bl
0x14006652f  setz    al
0x140066532  mov     [r15+38h], al
0x140066536  lea     rcx, [rbp+100h+lpFileName]; this
0x14006653a  call    ??1HclDevicePlatformSettings@Chipset@Devices@Config@@QEAA@XZ; Config::Devices::Chipset::HclDevicePlatformSettings::~HclDevicePlatformSettings(void)
0x14006653f  mov     r10d, 1
0x140066545  cmp     [rsi+100h], bl
0x14006654b  jz      loc_140066378
0x140066551  mov     [r15+1C8h], r10d
0x140066558  mov     [r15+0B8h], bl
0x14006655f  mov     dword ptr [r15+0BCh], 4
0x14006656a  mov     [r15+0D4h], bl
0x140066571  lea     r8, [rsi+0E8h]
0x140066578  mov     al, [r8+18h]
0x14006657c  lea     r14d, [r10+4]
0x140066580  test    al, al
0x140066582  jnz     short loc_140066589
0x140066584  mov     ecx, r14d
0x140066587  int     29h; Win8: RtlFailFast(ecx)
0x140066589  lea     r9, [r8+8]
0x14006658d  mov     rdx, [r9]
0x140066590  cmp     [r8], rdx
0x140066593  jnz     short loc_1400665C3
0x140066595  mov     r8d, ebx
0x140066598  lea     ecx, ds:0[r8*4]
0x1400665a0  mov     edx, 76540321h
0x1400665a5  shr     edx, cl
0x1400665a7  and     edx, 3
0x1400665aa  mov     eax, r8d
0x1400665ad  mov     [r15+rax*4+0C4h], edx
0x1400665b5  add     r8d, r10d
0x1400665b8  cmp     r8d, 4
0x1400665bc  jb      short loc_140066598
0x1400665be  jmp     loc_140066C99
0x1400665c3  test    al, al
0x1400665c5  jnz     short loc_1400665CC
0x1400665c7  mov     rcx, r14
0x1400665ca  int     29h; Win8: RtlFailFast(ecx)
0x1400665cc  xorps   xmm0, xmm0
0x1400665cf  movdqu  [rbp+100h+var_120], xmm0
0x1400665d4  mov     [rbp+100h+var_110], rbx
0x1400665d8  sub     rdx, [r8]
0x1400665db  sar     rdx, 2
0x1400665df  lea     rcx, [rbp+100h+var_120]
0x1400665e3  call    ??$_Construct_n@AEBQEAW4BootDevice@Resources@VirtualMachines@Schema@@AEBQEAW41234@@?$vector@W4BootDevice@Resources@VirtualMachines@Schema@@V?$allocator@W4BootDevice@Resources@VirtualMachines@Schema@@@std@@@std@@AEAAX_KAEBQEAW4BootDevice@Resources@VirtualMachines@Schema@@1@Z; std::vector<Schema::VirtualMachines::Resources::BootDevice>::_Construct_n<Schema::VirtualMachines::Resources::BootDevice * const &,Schema::VirtualMachines::Resources::BootDevice * const &>(unsigned __int64,Schema::VirtualMachines::Resources::BootDevice * const &,Schema::VirtualMachines::Resources::BootDevice * const &)
0x1400665e8  mov     r8d, ebx
0x1400665eb  mov     rdx, qword ptr [rbp+100h+var_120]
0x1400665ef  jmp     short loc_140066605
0x1400665f1  movsxd  rcx, r8d
0x1400665f4  mov     eax, [rdx]
0x1400665f6  mov     [r15+rcx*4+0C4h], eax
0x1400665fe  inc     r8d
0x140066601  add     rdx, 4
0x140066605  cmp     rdx, qword ptr [rbp+100h+var_120+8]
0x140066609  jnz     short loc_1400665F1
0x14006660b  lea     rcx, [rbp+100h+var_120]
0x14006660f  call    ?_Tidy@?$vector@W4NetworkProperty@System@Requests@Schema@@V?$allocator@W4NetworkProperty@System@Requests@Schema@@@std@@@std@@AEAAXXZ; std::vector<Schema::Requests::System::NetworkProperty>::_Tidy(void)
0x140066614  jmp     loc_140066C99
0x140066619  mov     dword ptr [r15+0C0h], 2
0x140066624  jmp     short loc_140066643
0x140066626  mov     [r15+0C0h], r10d
0x14006662d  jmp     short loc_140066643
0x14006662f  mov     dword ptr [r15+0C0h], 3
0x14006663a  jmp     short loc_140066643
0x14006663c  mov     [r15+0C0h], ebx
0x140066643  cmp     [rsi+0E0h], bl
0x140066649  jnz     short loc_140066650
0x14006664b  mov     rcx, r14
0x14006664e  int     29h; Win8: RtlFailFast(ecx)
0x140066650  cmp     [rsi+0A0h], bl
0x140066656  jz      loc_14006671C
0x14006665c  lea     rcx, [rbp+100h+lpFileName]; this
0x140066660  call    ??0UefiBootEntry@Resources@VirtualMachines@Schema@@QEAA@XZ; Schema::VirtualMachines::Resources::UefiBootEntry::UefiBootEntry(void)
0x140066665  nop
  ... truncated ...
```
