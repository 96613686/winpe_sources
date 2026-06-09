# ComputeService::ComputeSystemUtilities::InitializeHvSocketProviderProperties(void)

- ea: `0x1400e4348`
- end: `0x1400e489d`
- name: `?InitializeHvSocketProviderProperties@ComputeSystemUtilities@ComputeService@@YAXXZ`
- size: `1365`
- prototype: `void __fastcall(ComputeService::ComputeSystemUtilities *__hidden this)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14025bd9c`

## callees

- `0x140017040`
- `0x140018f8c`
- `0x14001bce0`
- `0x14001d490`
- `0x140024030`
- `0x1400286f0`
- `0x140033a7c`
- `0x1400421f0`
- `0x1400429e4`
- `0x14005bac8`
- `0x140067da4`
- `0x140080180`
- `0x1400a97c8`
- `0x1400b0660`
- `0x1400b1dd0`
- `0x1400b20e4`
- `0x1400c40e0`
- `0x1400e4348`
- `0x1400e4fc4`
- `0x1400f6494`
- `0x1401332f0`
- `0x14013624c`
- `0x1401365b9`
- `0x1401d9dd4`
- `0x1401db628`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400e4557`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400e4557`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400e467d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400e467d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400e4791`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400e4791`

## string_xrefs

- `0x1400e440f`: `HvSocket\WildcardDescriptors`
- `0x1400e43f8`: `onecore\vm\compute\management\computesystem\computesystemutilities.cpp`
- `0x1400e457b`: `onecore\vm\compute\management\computesystem\computesystemutilities.cpp`
- `0x1400e46a7`: `onecore\vm\compute\management\computesystem\computesystemutilities.cpp`
- `0x1400e47a1`: `onecore\vm\compute\management\computesystem\computesystemutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall ComputeService::ComputeSystemUtilities::InitializeHvSocketProviderProperties(
        ComputeService::ComputeSystemUtilities *this)
{
  __int128 v1; // xmm0
  unsigned int v2; // edi
  unsigned __int16 **v3; // rdx
  const char *v4; // r9
  const unsigned __int16 *v5; // rdx
  __int128 v6; // xmm6
  const WCHAR *v7; // rcx
  BOOL v8; // ebx
  const char *v9; // r9
  LPVOID v10; // rbx
  _QWORD *v11; // rdx
  const WCHAR *v12; // rcx
  char *FileW; // rbx
  const char *v14; // r9
  unsigned int v15; // r14d
  void *v16; // rax
  _OWORD *v17; // rdi
  const char *v18; // r9
  const char *v19; // r9
  int dwCreationDisposition; // [rsp+20h] [rbp-178h]
  char *v21; // [rsp+40h] [rbp-158h] BYREF
  LPVOID *p_lpInBuffer; // [rsp+48h] [rbp-150h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp-148h] BYREF
  char v24; // [rsp+58h] [rbp-140h]
  __int128 v25; // [rsp+60h] [rbp-138h] BYREF
  LPVOID v26; // [rsp+70h] [rbp-128h]
  __int128 v27; // [rsp+78h] [rbp-120h] BYREF
  LPVOID lpInBuffer; // [rsp+88h] [rbp-110h] BYREF
  int v29; // [rsp+90h] [rbp-108h] BYREF
  HKEY v30; // [rsp+98h] [rbp-100h] BYREF
  void *Src[2]; // [rsp+A0h] [rbp-F8h] BYREF
  void *v32; // [rsp+B0h] [rbp-E8h]
  DWORD BytesReturned; // [rsp+B8h] [rbp-E0h] BYREF
  HKEY phkResult; // [rsp+C0h] [rbp-D8h] BYREF
  __int128 v35; // [rsp+C8h] [rbp-D0h] BYREF
  __int64 v36; // [rsp+D8h] [rbp-C0h]
  unsigned __int16 *v37[3]; // [rsp+E0h] [rbp-B8h] BYREF
  unsigned __int64 v38; // [rsp+F8h] [rbp-A0h]
  LPCWSTR StringSecurityDescriptor[4]; // [rsp+100h] [rbp-98h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+120h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  v1 = 0;
  *(_OWORD *)Src = 0;
  v32 = 0;
  *(double *)&v1 = std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(Src);
  v35 = v1;
  v36 = 0;
  std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(&v35);
  try
  {
    phkResult = 0;
    v30 = 0;
    if ( !(unsigned int)Vml::VmRegistryKey::Open(
                          &phkResult,
                          HKEY_LOCAL_MACHINE,
                          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization",
                          0xF003Fu) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x83,
        (unsigned int)"onecore\\vm\\compute\\management\\computesystem\\computesystemutilities.cpp",
        (const char *)0x8000FFFFLL,
        dwCreationDisposition);
    if ( (unsigned int)Vml::VmRegistryKey::Open(&v30, phkResult, L"HvSocket\\WildcardDescriptors", 0x20019u) )
    {
      v2 = 0;
      v29 = 0;
      std::wstring::wstring(v37);
      std::wstring::wstring(StringSecurityDescriptor);
      while ( (unsigned int)Vml::VmRegistryKey::EnumValue(&v30, v2, v37, &v29) )
      {
        LODWORD(v21) = ++v2;
        if ( v29 == 1 )
        {
          v3 = v37;
          if ( v38 > 7 )
            v3 = (unsigned __int16 **)v37[0];
          try
          {
            if ( (unsigned int)Vml::VmRegistryKey::QueryValue(&v30, v3, StringSecurityDescriptor)
              && StringSecurityDescriptor[2] )
            {
              v5 = (const unsigned __int16 *)v37;
              if ( v38 > 7 )
                v5 = v37[0];
              Vml::VmGuid::Assign((Vml::VmGuid *)&v27, v5);
              v26 = 0;
              v6 = v27;
              v25 = v27;
              lpInBuffer = 0;
              p_lpInBuffer = &lpInBuffer;
              SecurityDescriptor = 0;
              v24 = 1;
              v7 = (const WCHAR *)StringSecurityDescriptor;
              if ( StringSecurityDescriptor[3] > (LPCWSTR)7 )
                v7 = StringSecurityDescriptor[0];
              v8 = ConvertStringSecurityDescriptorToSecurityDescriptorW(v7, 1u, &SecurityDescriptor, 0);
              wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_lpInBuffer);
              if ( v8 )
              {
                v10 = lpInBuffer;
                v26 = lpInBuffer;
                std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::_Emplace_one_at_back<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(
                  &v35,
                  &lpInBuffer);
                v11 = Src[1];
                if ( Src[1] == v32 )
                {
                  std::vector<VmMemorySettings::ValidationResult>::_Emplace_reallocate<VmMemorySettings::ValidationResult>(
                    Src,
                    Src[1],
                    &v25);
                }
                else
                {
                  *(_OWORD *)Src[1] = v6;
                  v11[2] = v10;
                  Src[1] = (char *)Src[1] + 24;
                }
                Vml::VmLocalPtr<_TOKEN_PRIMARY_GROUP>::~VmLocalPtr<_TOKEN_PRIMARY_GROUP>(&lpInBuffer);
              }
              else
              {
                wil::details::in1diag3::_Log_GetLastError(
                  retaddr,
                  (void *)0xA1,
                  (unsigned int)"onecore\\vm\\compute\\management\\computesystem\\computesystemutilities.cpp",
                  v9);
                Vml::VmLocalPtr<_TOKEN_PRIMARY_GROUP>::~VmLocalPtr<_TOKEN_PRIMARY_GROUP>(&lpInBuffer);
              }
            }
          }
          catch ( ... )
          {
            wil::details::in1diag3::Log_CaughtException(
              retaddr,
              (void *)0xAB,
              (unsigned int)"onecore\\vm\\compute\\management\\computesystem\\computesystemutilities.cpp",
              v4);
            v2 = (unsigned int)v21;
            continue;
          }
        }
      }
      Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)StringSecurityDescriptor);
      Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v37);
    }
    std::wstring::wstring(lpFileName, L"\\\\.\\HvSocketSystem\\HvSocketControl");
    v12 = (const WCHAR *)lpFileName;
    if ( lpFileName[3] > (LPCWSTR)7 )
      v12 = lpFileName[0];
    FileW = (char *)CreateFileW(v12, 0xC0000000, 0, 0, 1u, 0, 0);
    v21 = FileW;
    if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xBC,
        (unsigned int)"onecore\\vm\\compute\\management\\computesystem\\computesystemutilities.cpp",
        v14);
    lpInBuffer = 0;
    v15 = 8 * (((char *)Src[1] - (char *)Src[0]) >> 3);
    v16 = operator new[](v15 + 40LL);
    std::unique_ptr<unsigned char [0]>::reset<unsigned char *,0>(&lpInBuffer, v16);
    v17 = lpInBuffer;
    *((_DWORD *)lpInBuffer + 8) = v15;
    memcpy_0((char *)v17 + 40, Src[0], 8 * (((char *)Src[1] - (char *)Src[0]) >> 3));
    *v17 = xmmword_14031E3B0;
    v17[1] = *(_OWORD *)VirtualizationSettings::HyperVLowMemoryThresholdInMBDefault;
    BytesReturned = 0;
    if ( !DeviceIoControl(FileW, 0x21C018u, v17, v15 + 40, 0, 0, &BytesReturned, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xDF,
        (unsigned int)"onecore\\vm\\compute\\management\\computesystem\\computesystemutilities.cpp",
        v18);
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpInBuffer);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v21);
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)lpFileName);
    Vml::VmRegistryKey::~VmRegistryKey((Vml::VmRegistryKey *)&v30);
    Vml::VmRegistryKey::~VmRegistryKey((Vml::VmRegistryKey *)&phkResult);
    if ( (_QWORD)v35 )
    {
      std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>(
        v35,
        *((_QWORD *)&v35 + 1));
      std::_Deallocate<16>(v35, (v36 - v35) & 0xFFFFFFFFFFFFFFF8uLL);
      v35 = 0;
      v36 = 0;
    }
    if ( Src[0] )
      std::_Deallocate<16>(Src[0], 8 * ((signed __int64)((__int64)v32 - (unsigned __int64)Src[0]) >> 3));
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xE1,
      (unsigned int)"onecore\\vm\\compute\\management\\computesystem\\computesystemutilities.cpp",
      v19);
  }
}

```

## disassembly

```asm
0x1400e4348  mov     r11, rsp
0x1400e434b  push    rbx
0x1400e434c  push    rsi
0x1400e434d  push    rdi
0x1400e434e  push    r12
0x1400e4350  push    r14
0x1400e4352  push    r15
0x1400e4354  sub     rsp, 168h
0x1400e435b  movaps  xmmword ptr [r11-48h], xmm6
0x1400e4360  mov     rax, cs:__security_cookie
0x1400e4367  xor     rax, rsp
0x1400e436a  mov     [rsp+198h+var_58], rax
0x1400e4372  xorps   xmm0, xmm0
0x1400e4375  xor     eax, eax
0x1400e4377  movups  xmmword ptr [rsp+198h+Src], xmm0
0x1400e437f  mov     [r11-0E8h], rax
0x1400e4386  lea     rcx, [r11-0F8h]
0x1400e438d  call    ??0?$vector@UVpSubnodeMetadata@VirtualMachine@Config@@V?$allocator@UVpSubnodeMetadata@VirtualMachine@Config@@@std@@@std@@QEAA@XZ; std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(void)
0x1400e4392  nop
0x1400e4393  xor     eax, eax
0x1400e4395  movups  [rsp+198h+var_D0], xmm0
0x1400e439d  mov     [rsp+198h+var_C0], rax
0x1400e43a5  lea     rcx, [rsp+198h+var_D0]
0x1400e43ad  call    ??0?$vector@UVpSubnodeMetadata@VirtualMachine@Config@@V?$allocator@UVpSubnodeMetadata@VirtualMachine@Config@@@std@@@std@@QEAA@XZ; std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(void)
0x1400e43b2  nop
0x1400e43b3  xor     esi, esi
0x1400e43b5  mov     [rsp+198h+phkResult], rsi
0x1400e43bd  mov     [rsp+198h+var_100], rsi
0x1400e43c5  mov     r9d, 0F003Fh; unsigned int
0x1400e43cb  lea     r8, ?g_SettingsRegistryPath@Vml@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1400e43d2  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1400e43d9  lea     rcx, [rsp+198h+phkResult]; phkResult
0x1400e43e1  call    ?Open@VmRegistryKey@Vml@@QEAAHPEAUHKEY__@@PEBGK@Z; Vml::VmRegistryKey::Open(HKEY__ *,ushort const *,ulong)
0x1400e43e6  mov     rcx, [rsp+198h]; this
0x1400e43ee  test    eax, eax
0x1400e43f0  jnz     short loc_1400E4409
0x1400e43f2  mov     r9d, 8000FFFFh; char *
0x1400e43f8  lea     r8, aOnecoreVmCompu_4; "onecore\\vm\\compute\\management\\compu"...
0x1400e43ff  mov     edx, 83h; void *
0x1400e4404  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400e4409  mov     r9d, 20019h; unsigned int
0x1400e440f  lea     r8, aHvsocketWildca; "HvSocket\\WildcardDescriptors"
0x1400e4416  mov     rdx, [rsp+198h+phkResult]; hKey
0x1400e441e  lea     rcx, [rsp+198h+var_100]; phkResult
0x1400e4426  call    ?Open@VmRegistryKey@Vml@@QEAAHPEAUHKEY__@@PEBGK@Z; Vml::VmRegistryKey::Open(HKEY__ *,ushort const *,ulong)
0x1400e442b  test    eax, eax
0x1400e442d  jz      loc_1400E4632
0x1400e4433  mov     edi, esi
0x1400e4435  mov     [rsp+198h+var_108], esi
0x1400e443c  lea     rcx, [rsp+198h+var_B8]; void *
0x1400e4444  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1400e4449  nop
0x1400e444a  lea     rcx, [rsp+198h+StringSecurityDescriptor]; void *
0x1400e4452  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1400e4457  nop
0x1400e4458  lea     r9, [rsp+198h+var_108]
0x1400e4460  lea     r8, [rsp+198h+var_B8]
0x1400e4468  mov     edx, edi
0x1400e446a  lea     rcx, [rsp+198h+var_100]
0x1400e4472  call    ?EnumValue@VmRegistryKey@Vml@@QEBAHKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAK1@Z; Vml::VmRegistryKey::EnumValue(ulong,std::wstring &,ulong *,ulong *)
0x1400e4477  test    eax, eax
0x1400e4479  jz      loc_1400E4617
0x1400e447f  inc     edi
0x1400e4481  mov     dword ptr [rsp+198h+var_158], edi
0x1400e4485  cmp     [rsp+198h+var_108], 1
0x1400e448d  jz      short loc_1400E4491
0x1400e448f  jmp     short loc_1400E4458
0x1400e4491  lea     rdx, [rsp+198h+var_B8]
0x1400e4499  cmp     [rsp+198h+var_A0], 7
0x1400e44a2  cmova   rdx, [rsp+198h+var_B8]
0x1400e44ab  lea     r8, [rsp+198h+StringSecurityDescriptor]
0x1400e44b3  lea     rcx, [rsp+198h+var_100]
0x1400e44bb  call    ?QueryValue@VmRegistryKey@Vml@@QEBAHPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; Vml::VmRegistryKey::QueryValue(ushort const *,std::wstring &,bool)
0x1400e44c0  test    eax, eax
0x1400e44c2  jz      loc_1400E4607
0x1400e44c8  cmp     [rsp+198h+var_88], rsi
0x1400e44d0  jz      loc_1400E4607
0x1400e44d6  lea     rdx, [rsp+198h+var_B8]
0x1400e44de  cmp     [rsp+198h+var_A0], 7
0x1400e44e7  cmova   rdx, [rsp+198h+var_B8]; unsigned __int16 *
0x1400e44f0  lea     rcx, [rsp+198h+var_120]; this
0x1400e44f5  call    ?Assign@VmGuid@Vml@@QEAAXQEBG@Z; Vml::VmGuid::Assign(ushort const * const)
0x1400e44fa  xorps   xmm0, xmm0
0x1400e44fd  xor     eax, eax
0x1400e44ff  movups  [rsp+198h+var_134], xmm0
0x1400e4504  mov     [rsp+198h+var_124], eax
0x1400e4508  movups  xmm6, [rsp+198h+var_120]
0x1400e450d  movups  xmmword ptr [rsp+60h], xmm6
0x1400e4512  mov     [rsp+198h+lpInBuffer], rsi
0x1400e451a  lea     rax, [rsp+198h+lpInBuffer]
0x1400e4522  mov     [rsp+198h+var_150], rax
0x1400e4527  mov     [rsp+198h+SecurityDescriptor], rsi
0x1400e452c  mov     [rsp+198h+var_140], 1
0x1400e4531  lea     rcx, [rsp+198h+StringSecurityDescriptor]
0x1400e4539  cmp     [rsp+198h+var_80], 7
0x1400e4542  cmova   rcx, [rsp+198h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1400e454b  xor     r9d, r9d; SecurityDescriptorSize
0x1400e454e  lea     r8, [rsp+198h+SecurityDescriptor]; SecurityDescriptor
0x1400e4553  lea     edx, [r9+1]; StringSDRevision
0x1400e4557  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1400e455e  nop     dword ptr [rax+rax+00h]
0x1400e4563  mov     ebx, eax
0x1400e4565  lea     rcx, [rsp+198h+var_150]
0x1400e456a  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x1400e456f  test    ebx, ebx
0x1400e4571  jnz     short loc_1400E45A0
0x1400e4573  mov     rcx, [rsp+198h]; this
0x1400e457b  lea     r8, aOnecoreVmCompu_4; "onecore\\vm\\compute\\management\\compu"...
0x1400e4582  mov     edx, 0A1h; void *
0x1400e4587  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1400e458c  nop
0x1400e458d  lea     rcx, [rsp+198h+lpInBuffer]
0x1400e4595  call    ??1?$VmLocalPtr@U_TOKEN_PRIMARY_GROUP@@@Vml@@QEAA@XZ; Vml::VmLocalPtr<_TOKEN_PRIMARY_GROUP>::~VmLocalPtr<_TOKEN_PRIMARY_GROUP>(void)
0x1400e459a  nop
0x1400e459b  jmp     loc_1400E4458
0x1400e45a0  mov     rbx, [rsp+198h+lpInBuffer]
0x1400e45a8  mov     qword ptr [rsp+198h+var_134+0Ch], rbx
0x1400e45ad  lea     rdx, [rsp+198h+lpInBuffer]
0x1400e45b5  lea     rcx, [rsp+198h+var_D0]
0x1400e45bd  call    ??$_Emplace_one_at_back@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::_Emplace_one_at_back<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&)
0x1400e45c2  mov     rdx, [rsp+198h+Src+8]
0x1400e45ca  cmp     rdx, [rsp+198h+var_E8]
0x1400e45d2  jz      short loc_1400E45E6
0x1400e45d4  movups  xmmword ptr [rdx], xmm6
0x1400e45d7  mov     [rdx+10h], rbx
0x1400e45db  add     [rsp+198h+Src+8], 18h
0x1400e45e4  jmp     short loc_1400E45F9
0x1400e45e6  lea     r8, [rsp+198h+var_138]
0x1400e45eb  lea     rcx, [rsp+198h+Src]
0x1400e45f3  call    ??$_Emplace_reallocate@UValidationResult@VmMemorySettings@@@?$vector@UValidationResult@VmMemorySettings@@V?$allocator@UValidationResult@VmMemorySettings@@@std@@@std@@AEAAPEAUValidationResult@VmMemorySettings@@QEAU23@$$QEAU23@@Z; std::vector<VmMemorySettings::ValidationResult>::_Emplace_reallocate<VmMemorySettings::ValidationResult>(VmMemorySettings::ValidationResult * const,VmMemorySettings::ValidationResult &&)
0x1400e45f8  nop
0x1400e45f9  lea     rcx, [rsp+198h+lpInBuffer]
0x1400e4601  call    ??1?$VmLocalPtr@U_TOKEN_PRIMARY_GROUP@@@Vml@@QEAA@XZ; Vml::VmLocalPtr<_TOKEN_PRIMARY_GROUP>::~VmLocalPtr<_TOKEN_PRIMARY_GROUP>(void)
0x1400e4606  nop
0x1400e4607  jmp     loc_1400E4458
0x1400e460c  xor     esi, esi
0x1400e460e  mov     edi, dword ptr [rsp+198h+var_158]
0x1400e4612  jmp     loc_1400E4458
0x1400e4617  lea     rcx, [rsp+198h+StringSecurityDescriptor]; this
0x1400e461f  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400e4624  nop
0x1400e4625  lea     rcx, [rsp+198h+var_B8]; this
0x1400e462d  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400e4632  lea     rdx, aHvsocketsystem; "\\\\.\\HvSocketSystem\\HvSocketControl"
0x1400e4639  lea     rcx, [rsp+198h+lpFileName]
0x1400e4641  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400e4646  nop
0x1400e4647  lea     rcx, [rsp+198h+lpFileName]
0x1400e464f  cmp     [rsp+198h+var_60], 7
0x1400e4658  cmova   rcx, [rsp+198h+lpFileName]; lpFileName
0x1400e4661  mov     [rsp+198h+hTemplateFile], rsi; hTemplateFile
0x1400e4666  mov     [rsp+198h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x1400e466a  mov     [rsp+198h+dwCreationDisposition], 1; dwCreationDisposition
0x1400e4672  xor     r9d, r9d; lpSecurityAttributes
0x1400e4675  xor     r8d, r8d; dwShareMode
0x1400e4678  mov     edx, 0C0000000h; dwDesiredAccess
0x1400e467d  call    cs:__imp_CreateFileW
0x1400e4684  nop     dword ptr [rax+rax+00h]
0x1400e4689  mov     rbx, rax
0x1400e468c  mov     [rsp+198h+var_158], rax
0x1400e4691  dec     rax
0x1400e4694  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400e4698  setnbe  al
0x1400e469b  mov     rcx, [rsp+198h]; this
0x1400e46a3  test    al, al
0x1400e46a5  jz      short loc_1400E46B8
0x1400e46a7  lea     r8, aOnecoreVmCompu_4; "onecore\\vm\\compute\\management\\compu"...
0x1400e46ae  mov     edx, 0BCh; void *
0x1400e46b3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400e46b8  mov     [rsp+198h+lpInBuffer], rsi
0x1400e46c0  mov     rax, [rsp+198h+Src+8]
0x1400e46c8  sub     rax, [rsp+198h+Src]
0x1400e46d0  sar     rax, 3
0x1400e46d4  mov     r12, 0AAAAAAAAAAAAAAABh
0x1400e46de  imul    rax, r12
0x1400e46e2  lea     eax, [rax+rax*2]
0x1400e46e5  lea     r14d, ds:0[rax*8]
0x1400e46ed  mov     ecx, r14d
0x1400e46f0  add     rcx, 28h ; '('; unsigned __int64
0x1400e46f4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400e46f9  mov     rdx, rax
0x1400e46fc  lea     rcx, [rsp+198h+lpInBuffer]
0x1400e4704  call    ??$reset@PEAE$0A@@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAXPEAE@Z; std::unique_ptr<uchar [0]>::reset<uchar *,0>(uchar *)
0x1400e4709  mov     rdi, [rsp+198h+lpInBuffer]
0x1400e4711  mov     [rdi+20h], r14d
0x1400e4715  mov     rax, [rsp+198h+Src+8]
0x1400e471d  mov     rdx, [rsp+198h+Src]; Src
0x1400e4725  sub     rax, rdx
0x1400e4728  sar     rax, 3
0x1400e472c  imul    rax, r12
0x1400e4730  lea     r8, [rax+rax*2]
0x1400e4734  shl     r8, 3; Size
0x1400e4738  lea     rcx, [rdi+28h]; void *
0x1400e473c  call    memcpy_0
0x1400e4741  movups  xmm0, cs:xmmword_14031E3B0
0x1400e4748  movdqu  xmmword ptr [rdi], xmm0
0x1400e474c  movups  xmm1, xmmword ptr cs:?HyperVLowMemoryThresholdInMBDefault@VirtualizationSettings@@2V?$optional@_K@std@@B; std::optional<unsigned __int64> const VirtualizationSettings::HyperVLowMemoryThresholdInMBDefault
0x1400e4753  movdqu  xmmword ptr [rdi+10h], xmm1
0x1400e4758  mov     [rsp+198h+BytesReturned], esi
0x1400e475f  mov     r15, [rsp+198h]
0x1400e4767  lea     r9d, [r14+28h]; nInBufferSize
0x1400e476b  mov     [rsp+198h+lpOverlapped], rsi; lpOverlapped
0x1400e4770  lea     rax, [rsp+198h+BytesReturned]
0x1400e4778  mov     [rsp+198h+hTemplateFile], rax; lpBytesReturned
0x1400e477d  mov     [rsp+198h+dwFlagsAndAttributes], esi; nOutBufferSize
0x1400e4781  mov     qword ptr [rsp+198h+dwCreationDisposition], rsi; lpOutBuffer
0x1400e4786  mov     r8, rdi; lpInBuffer
0x1400e4789  mov     edx, 21C018h; dwIoControlCode
0x1400e478e  mov     rcx, rbx; hDevice
0x1400e4791  call    cs:__imp_DeviceIoControl
0x1400e4798  nop     dword ptr [rax+rax+00h]
0x1400e479d  test    eax, eax
0x1400e479f  jnz     short loc_1400E47B6
0x1400e47a1  lea     r8, aOnecoreVmCompu_4; "onecore\\vm\\compute\\management\\compu"...
0x1400e47a8  mov     edx, 0DFh; void *
0x1400e47ad  mov     rcx, r15; this
0x1400e47b0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400e47b6  lea     rcx, [rsp+198h+lpInBuffer]
0x1400e47be  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1400e47c3  nop
0x1400e47c4  lea     rcx, [rsp+198h+var_158]; void *
0x1400e47c9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400e47ce  nop
0x1400e47cf  lea     rcx, [rsp+198h+lpFileName]; this
0x1400e47d7  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400e47dc  nop
0x1400e47dd  lea     rcx, [rsp+198h+var_100]; this
0x1400e47e5  call    ??1VmRegistryKey@Vml@@QEAA@XZ; Vml::VmRegistryKey::~VmRegistryKey(void)
0x1400e47ea  nop
0x1400e47eb  lea     rcx, [rsp+198h+phkResult]; this
0x1400e47f3  call    ??1VmRegistryKey@Vml@@QEAA@XZ; Vml::VmRegistryKey::~VmRegistryKey(void)
0x1400e47f8  nop
0x1400e47f9  mov     rcx, qword ptr [rsp+198h+var_D0]
0x1400e4801  test    rcx, rcx
0x1400e4804  jz      short loc_1400E4843
0x1400e4806  mov     rdx, qword ptr [rsp+198h+var_D0+8]
0x1400e480e  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>> &)
0x1400e4813  mov     rcx, qword ptr [rsp+198h+var_D0]
0x1400e481b  mov     rdx, [rsp+198h+var_C0]
0x1400e4823  sub     rdx, rcx
0x1400e4826  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1400e482a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1400e482f  xorps   xmm0, xmm0
0x1400e4832  movdqu  [rsp+198h+var_D0], xmm0
0x1400e483b  mov     [rsp+198h+var_C0], rsi
0x1400e4843  mov     rcx, [rsp+198h+Src]
0x1400e484b  test    rcx, rcx
0x1400e484e  jz      short loc_1400E4871
0x1400e4850  mov     rax, [rsp+198h+var_E8]
0x1400e4858  sub     rax, rcx
0x1400e485b  sar     rax, 3
0x1400e485f  imul    rax, r12
0x1400e4863  lea     rdx, [rax+rax*2]
0x1400e4867  shl     rdx, 3
0x1400e486b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1400e4870  nop
0x1400e4871  jmp     short $+2
0x1400e4873  mov     rcx, [rsp+198h+var_58]
0x1400e487b  xor     rcx, rsp; StackCookie
0x1400e487e  call    __security_check_cookie
0x1400e4883  movaps  xmm6, [rsp+198h+var_48]
0x1400e488b  add     rsp, 168h
0x1400e4892  pop     r15
0x1400e4894  pop     r14
0x1400e4896  pop     r12
0x1400e4898  pop     rdi
0x1400e4899  pop     rsi
0x1400e489a  pop     rbx
0x1400e489b  retn
```
