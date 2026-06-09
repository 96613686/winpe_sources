# ComputeService::VmCommonHelpers::CreateSerialNamedPipe(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,uint,_GUID const &)

- ea: `0x14003f93c`
- end: `0x14003fdb7`
- name: `?CreateSerialNamedPipe@VmCommonHelpers@ComputeService@@YA?AU?$pair@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@_N@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@IAEBU_GUID@@@Z`
- size: `1147`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14002aee4`
- `0x14003f568`
- `0x140072200`

## callees

- `0x140017040`
- `0x14001bce0`
- `0x140024030`
- `0x140024f6c`
- `0x140033a7c`
- `0x14003f93c`
- `0x1400412a0`
- `0x140080180`
- `0x1400b1dd0`
- `0x1400bd968`
- `0x1400e91a8`
- `0x1400f6494`
- `0x1400f64f4`
- `0x1401332f0`
- `0x1401d9dd4`
- `0x1401efc0c`
- `0x1401efd20`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x14003fc15`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x14003fc15`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x14003fbe1`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x14003fbe1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x14003f9c6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x14003f9c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003fa93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003fae7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003fb3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003fb90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003fc9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003fcb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003fd9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003fa93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003fae7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003fb3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003fb90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003fc9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003fcb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003fd9b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14003fc6d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14003fc6d`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x14003fd3b`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x14003fd3b`

## string_xrefs

- `0x14003f9da`: `onecore\vm\compute\management\orchestration\shared\vmcommon\serial.cpp`
- `0x14003fbf5`: `onecore\vm\compute\management\orchestration\shared\vmcommon\serial.cpp`
- `0x14003fc29`: `onecore\vm\compute\management\orchestration\shared\vmcommon\serial.cpp`
- `0x14003fd6b`: `onecore\vm\compute\management\orchestration\shared\vmcommon\serial.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ComputeService::VmCommonHelpers::CreateSerialNamedPipe(__int64 a1, const WCHAR *a2, DWORD a3)
{
  const struct _GUID *v6; // rdx
  DWORD *v7; // r9
  struct _ACL *VirtualMachineSid; // rax
  const char *v9; // r9
  unsigned int v10; // edx
  char v11; // bl
  void **i; // rdi
  void **v13; // r15
  const char *v14; // r9
  PACL v15; // rdi
  const char *v16; // r9
  const WCHAR *v17; // rcx
  struct _ACL *v18; // rcx
  HANDLE v20; // rax
  const char *v21; // r9
  HLOCAL hMem[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v23[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v24[32]; // [rsp+80h] [rbp-80h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+A0h] [rbp-60h] BYREF
  PACL pDacl[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v27; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v28; // [rsp+D8h] [rbp-28h]
  PSID Sid; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v31; // [rsp+108h] [rbp+8h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v27 = 0;
  v28 = 0;
  std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(&v27);
  VirtualMachineSid = (struct _ACL *)WpSecurity::AllocateVirtualMachineSid(v7, v6);
  pDacl[0] = VirtualMachineSid;
  if ( *((_QWORD *)&v27 + 1) == v28 )
  {
    std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::_Emplace_reallocate<void *>(
      &v27,
      *((_QWORD *)&v27 + 1),
      pDacl);
  }
  else
  {
    **((_QWORD **)&v27 + 1) = VirtualMachineSid;
    *((_QWORD *)&v27 + 1) += 8LL;
  }
  Sid = 0;
  if ( !ConvertStringSidToSidW(
          L"S-1-15-3-1024-2268835264-3721307629-241982045-173645152-1490879176-104643441-2915960892-1612460704",
          &Sid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x50,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\serial.cpp",
      v9);
  v10 = DWORD2(v27);
  if ( *((_QWORD *)&v27 + 1) == v28 )
  {
    std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(
      &v27,
      *((_QWORD *)&v27 + 1),
      &Sid);
  }
  else
  {
    **((_QWORD **)&v27 + 1) = Sid;
    Sid = 0;
    *((_QWORD *)&v27 + 1) += 8LL;
  }
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 1;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v31 = 0;
  SecurityAttributes.lpSecurityDescriptor = pSecurityDescriptor;
  v11 = 1;
  *(_OWORD *)pDacl = 0;
  Vml::VmAcl::Initialize((Vml::VmAcl *)pDacl, v10);
  Vml::VmSid::VmSid((Vml::VmSid *)hMem, WinLocalSystemSid, 0);
  Vml::VmAcl::UpdateAccess((Vml::VmAcl *)pDacl, hMem[0], 0x10000000u, 0, GRANT_ACCESS);
  if ( hMem[0] )
    LocalFree(hMem[0]);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v24);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v23);
  Vml::VmSid::VmSid((Vml::VmSid *)hMem, WinBuiltinAdministratorsSid, 0);
  Vml::VmAcl::UpdateAccess((Vml::VmAcl *)pDacl, hMem[0], 0x10000000u, 0, GRANT_ACCESS);
  if ( hMem[0] )
    LocalFree(hMem[0]);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v24);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v23);
  Vml::VmSid::VmSid((Vml::VmSid *)hMem, WinBuiltinHyperVAdminsSid, 0);
  Vml::VmAcl::UpdateAccess((Vml::VmAcl *)pDacl, hMem[0], 0x10000000u, 0, GRANT_ACCESS);
  if ( hMem[0] )
    LocalFree(hMem[0]);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v24);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v23);
  Vml::VmSid::VmSid((Vml::VmSid *)hMem, WinWorldSid, 0);
  Vml::VmAcl::UpdateAccess((Vml::VmAcl *)pDacl, hMem[0], 0x80120000, 0, GRANT_ACCESS);
  if ( hMem[0] )
    LocalFree(hMem[0]);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v24);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v23);
  v13 = (void **)*((_QWORD *)&v27 + 1);
  for ( i = (void **)v27; i != v13; ++i )
    Vml::VmAcl::UpdateAccess((Vml::VmAcl *)pDacl, *i, 0x1F01FFu, 0, GRANT_ACCESS);
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x65,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\serial.cpp",
      v14);
  v15 = pDacl[0];
  if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pDacl[0], 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x66,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\serial.cpp",
      v16);
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v17 = a2;
  else
    v17 = *(const WCHAR **)a2;
  v18 = (struct _ACL *)CreateFileW(v17, 0xC0000000, 0, &SecurityAttributes, 3u, 0x40100000u, 0);
  pDacl[0] = v18;
  if ( (unsigned __int64)&v18[-1].Sbz2 + 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v11 = 0;
LABEL_29:
    *(_QWORD *)a1 = v18;
    *(_BYTE *)(a1 + 8) = v11;
    if ( v15 )
      LocalFree(v15);
    if ( Sid )
      LocalFree(Sid);
    goto LABEL_33;
  }
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const WCHAR **)a2;
  v20 = CreateNamedPipeW(a2, 0x40000003u, 0, 1u, 0x2000u, a3, 0x64u, &SecurityAttributes);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    pDacl,
    v20);
  v18 = pDacl[0];
  if ( ((unsigned __int64)&pDacl[0]->Sbz1 & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    goto LABEL_29;
  wil::details::in1diag3::_Log_GetLastError(
    retaddr,
    (void *)0x85,
    (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\serial.cpp",
    v21);
  *(_QWORD *)a1 = -1;
  *(_BYTE *)(a1 + 8) = 0;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(pDacl);
  if ( v15 )
    LocalFree(v15);
  Vml::VmLocalPtr<_TOKEN_PRIMARY_GROUP>::~VmLocalPtr<_TOKEN_PRIMARY_GROUP>(&Sid);
LABEL_33:
  if ( (_QWORD)v27 )
  {
    std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>(
      v27,
      *((_QWORD *)&v27 + 1));
    std::_Deallocate<16>(v27, (v28 - v27) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  return a1;
}

```

## disassembly

```asm
0x14003f93c  push    rbp
0x14003f93e  push    rbx
0x14003f93f  push    rsi
0x14003f940  push    rdi
0x14003f941  push    r12
0x14003f943  push    r14
0x14003f945  push    r15
0x14003f947  lea     rbp, [rsp-20h]
0x14003f94c  sub     rsp, 120h
0x14003f953  mov     rax, cs:__security_cookie
0x14003f95a  xor     rax, rsp
0x14003f95d  mov     [rbp+50h+var_40], rax
0x14003f961  mov     r12d, r8d
0x14003f964  mov     rsi, rdx
0x14003f967  mov     r14, rcx
0x14003f96a  mov     [rbp+50h+pDacl], rcx
0x14003f96e  xorps   xmm0, xmm0
0x14003f971  xor     eax, eax
0x14003f973  movups  [rbp+50h+var_88], xmm0
0x14003f977  mov     [rbp+50h+var_78], rax
0x14003f97b  lea     rcx, [rbp+50h+var_88]
0x14003f97f  call    ??0?$vector@UVpSubnodeMetadata@VirtualMachine@Config@@V?$allocator@UVpSubnodeMetadata@VirtualMachine@Config@@@std@@@std@@QEAA@XZ; std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(void)
0x14003f984  nop
0x14003f985  mov     rcx, r9; this
0x14003f988  call    ?AllocateVirtualMachineSid@WpSecurity@@YAPEAXAEBU_GUID@@@Z; WpSecurity::AllocateVirtualMachineSid(_GUID const &)
0x14003f98d  mov     [rbp+50h+pDacl], rax
0x14003f991  mov     rdx, qword ptr [rbp+50h+var_88+8]
0x14003f995  cmp     rdx, [rbp+50h+var_78]
0x14003f999  jz      short loc_14003F9A5
0x14003f99b  mov     [rdx], rax
0x14003f99e  add     qword ptr [rbp+50h+var_88+8], 8
0x14003f9a3  jmp     short loc_14003F9B3
0x14003f9a5  lea     r8, [rbp+50h+pDacl]
0x14003f9a9  lea     rcx, [rbp+50h+var_88]
0x14003f9ad  call    ??$_Emplace_reallocate@PEAX@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV23@$$QEAPEAX@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::_Emplace_reallocate<void *>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> * const,void * &&)
0x14003f9b2  nop
0x14003f9b3  mov     [rbp+50h+Sid], 0
0x14003f9bb  lea     rdx, [rbp+50h+Sid]; Sid
0x14003f9bf  lea     rcx, StringSid; "S-1-15-3-1024-2268835264-3721307629-241"...
0x14003f9c6  call    cs:__imp_ConvertStringSidToSidW
0x14003f9cd  nop     dword ptr [rax+rax+00h]
0x14003f9d2  mov     rcx, [rbp+58h]; this
0x14003f9d6  test    eax, eax
0x14003f9d8  jnz     short loc_14003F9EA
0x14003f9da  lea     r8, aOnecoreVmCompu_107; "onecore\\vm\\compute\\management\\orche"...
0x14003f9e1  lea     edx, [rax+50h]; void *
0x14003f9e4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14003f9ea  mov     rdx, qword ptr [rbp+50h+var_88+8]
0x14003f9ee  cmp     rdx, [rbp+50h+var_78]
0x14003f9f2  jz      short loc_14003FA0A
0x14003f9f4  mov     rax, [rbp+50h+Sid]
0x14003f9f8  mov     [rdx], rax
0x14003f9fb  mov     [rbp+50h+Sid], 0
0x14003fa03  add     qword ptr [rbp+50h+var_88+8], 8
0x14003fa08  jmp     short loc_14003FA17
0x14003fa0a  lea     r8, [rbp+50h+Sid]
0x14003fa0e  lea     rcx, [rbp+50h+var_88]
0x14003fa12  call    ??$_Emplace_reallocate@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&)
0x14003fa17  mov     qword ptr [rbp+50h+SecurityAttributes.nLength], 18h
0x14003fa1f  mov     qword ptr [rbp+50h+SecurityAttributes.bInheritHandle], 1
0x14003fa27  xorps   xmm0, xmm0
0x14003fa2a  xor     eax, eax
0x14003fa2c  movups  [rbp+50h+pSecurityDescriptor], xmm0
0x14003fa30  movups  [rbp+50h+var_58], xmm0
0x14003fa34  mov     [rbp+50h+var_48], rax
0x14003fa38  lea     rax, [rbp+50h+pSecurityDescriptor]
0x14003fa3c  mov     [rbp+50h+SecurityAttributes.lpSecurityDescriptor], rax
0x14003fa40  mov     ebx, 1
0x14003fa45  movups  xmmword ptr [rbp+50h+pDacl], xmm0
0x14003fa49  mov     [rbp+50h+pDacl], 0
0x14003fa51  lea     rcx, [rbp+50h+pDacl]; this
0x14003fa55  call    ?Initialize@VmAcl@Vml@@QEAAXK@Z; Vml::VmAcl::Initialize(ulong)
0x14003fa5a  xor     r8d, r8d; DomainSid
0x14003fa5d  lea     edx, [rbx+15h]; WellKnownSidType
0x14003fa60  lea     rcx, [rsp+150h+hMem]; this
0x14003fa65  call    ??0VmSid@Vml@@QEAA@W4WELL_KNOWN_SID_TYPE@@PEAX@Z; Vml::VmSid::VmSid(WELL_KNOWN_SID_TYPE,void *)
0x14003fa6a  nop
0x14003fa6b  mov     [rsp+150h+dwCreationDisposition], ebx; enum _ACCESS_MODE
0x14003fa6f  xor     r9d, r9d; unsigned int
0x14003fa72  mov     edi, 10000000h
0x14003fa77  mov     r8d, edi; unsigned int
0x14003fa7a  mov     rdx, [rsp+150h+hMem]; void *
0x14003fa7f  lea     rcx, [rbp+50h+pDacl]; this
0x14003fa83  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x14003fa88  nop
0x14003fa89  mov     rcx, [rsp+150h+hMem]; hMem
0x14003fa8e  test    rcx, rcx
0x14003fa91  jz      short loc_14003FA9F
0x14003fa93  call    cs:__imp_LocalFree
0x14003fa9a  nop     dword ptr [rax+rax+00h]
0x14003fa9f  lea     rcx, [rbp+50h+var_D0]; this
0x14003faa3  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14003faa8  lea     rcx, [rsp+150h+var_F0]; this
0x14003faad  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14003fab2  xor     r8d, r8d; DomainSid
0x14003fab5  lea     edx, [r8+1Ah]; WellKnownSidType
0x14003fab9  lea     rcx, [rsp+150h+hMem]; this
0x14003fabe  call    ??0VmSid@Vml@@QEAA@W4WELL_KNOWN_SID_TYPE@@PEAX@Z; Vml::VmSid::VmSid(WELL_KNOWN_SID_TYPE,void *)
0x14003fac3  nop
0x14003fac4  mov     [rsp+150h+dwCreationDisposition], ebx; enum _ACCESS_MODE
0x14003fac8  xor     r9d, r9d; unsigned int
0x14003facb  mov     r8d, edi; unsigned int
0x14003face  mov     rdx, [rsp+150h+hMem]; void *
0x14003fad3  lea     rcx, [rbp+50h+pDacl]; this
0x14003fad7  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x14003fadc  nop
0x14003fadd  mov     rcx, [rsp+150h+hMem]; hMem
0x14003fae2  test    rcx, rcx
0x14003fae5  jz      short loc_14003FAF3
0x14003fae7  call    cs:__imp_LocalFree
0x14003faee  nop     dword ptr [rax+rax+00h]
0x14003faf3  lea     rcx, [rbp+50h+var_D0]; this
0x14003faf7  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14003fafc  lea     rcx, [rsp+150h+var_F0]; this
0x14003fb01  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14003fb06  xor     r8d, r8d; DomainSid
0x14003fb09  lea     edx, [r8+63h]; WellKnownSidType
0x14003fb0d  lea     rcx, [rsp+150h+hMem]; this
0x14003fb12  call    ??0VmSid@Vml@@QEAA@W4WELL_KNOWN_SID_TYPE@@PEAX@Z; Vml::VmSid::VmSid(WELL_KNOWN_SID_TYPE,void *)
0x14003fb17  nop
0x14003fb18  mov     [rsp+150h+dwCreationDisposition], ebx; enum _ACCESS_MODE
0x14003fb1c  xor     r9d, r9d; unsigned int
0x14003fb1f  mov     r8d, edi; unsigned int
0x14003fb22  mov     rdx, [rsp+150h+hMem]; void *
0x14003fb27  lea     rcx, [rbp+50h+pDacl]; this
0x14003fb2b  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x14003fb30  nop
0x14003fb31  mov     rcx, [rsp+150h+hMem]; hMem
0x14003fb36  test    rcx, rcx
0x14003fb39  jz      short loc_14003FB47
0x14003fb3b  call    cs:__imp_LocalFree
0x14003fb42  nop     dword ptr [rax+rax+00h]
0x14003fb47  lea     rcx, [rbp+50h+var_D0]; this
0x14003fb4b  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14003fb50  lea     rcx, [rsp+150h+var_F0]; this
0x14003fb55  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14003fb5a  xor     r8d, r8d; DomainSid
0x14003fb5d  mov     edx, ebx; WellKnownSidType
0x14003fb5f  lea     rcx, [rsp+150h+hMem]; this
0x14003fb64  call    ??0VmSid@Vml@@QEAA@W4WELL_KNOWN_SID_TYPE@@PEAX@Z; Vml::VmSid::VmSid(WELL_KNOWN_SID_TYPE,void *)
0x14003fb69  nop
0x14003fb6a  mov     [rsp+150h+dwCreationDisposition], ebx; enum _ACCESS_MODE
0x14003fb6e  xor     r9d, r9d; unsigned int
0x14003fb71  mov     r8d, 80120000h; unsigned int
0x14003fb77  mov     rdx, [rsp+150h+hMem]; void *
0x14003fb7c  lea     rcx, [rbp+50h+pDacl]; this
0x14003fb80  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x14003fb85  nop
0x14003fb86  mov     rcx, [rsp+150h+hMem]; hMem
0x14003fb8b  test    rcx, rcx
0x14003fb8e  jz      short loc_14003FB9C
0x14003fb90  call    cs:__imp_LocalFree
0x14003fb97  nop     dword ptr [rax+rax+00h]
0x14003fb9c  lea     rcx, [rbp+50h+var_D0]; this
0x14003fba0  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14003fba5  lea     rcx, [rsp+150h+var_F0]; this
0x14003fbaa  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14003fbaf  mov     rdi, qword ptr [rbp+50h+var_88]
0x14003fbb3  mov     r15, qword ptr [rbp+50h+var_88+8]
0x14003fbb7  jmp     short loc_14003FBD6
0x14003fbb9  mov     [rsp+150h+dwCreationDisposition], ebx; enum _ACCESS_MODE
0x14003fbbd  xor     r9d, r9d; unsigned int
0x14003fbc0  mov     r8d, 1F01FFh; unsigned int
0x14003fbc6  mov     rdx, [rdi]; void *
0x14003fbc9  lea     rcx, [rbp+50h+pDacl]; this
0x14003fbcd  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x14003fbd2  add     rdi, 8
0x14003fbd6  cmp     rdi, r15
0x14003fbd9  jnz     short loc_14003FBB9
0x14003fbdb  mov     edx, ebx; dwRevision
0x14003fbdd  lea     rcx, [rbp+50h+pSecurityDescriptor]; pSecurityDescriptor
0x14003fbe1  call    cs:__imp_InitializeSecurityDescriptor
0x14003fbe8  nop     dword ptr [rax+rax+00h]
0x14003fbed  mov     rcx, [rbp+58h]; this
0x14003fbf1  test    eax, eax
0x14003fbf3  jnz     short loc_14003FC05
0x14003fbf5  lea     r8, aOnecoreVmCompu_107; "onecore\\vm\\compute\\management\\orche"...
0x14003fbfc  lea     edx, [rax+65h]; void *
0x14003fbff  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14003fc05  xor     r9d, r9d; bDaclDefaulted
0x14003fc08  mov     rdi, [rbp+50h+pDacl]
0x14003fc0c  mov     r8, rdi; pDacl
0x14003fc0f  mov     edx, ebx; bDaclPresent
0x14003fc11  lea     rcx, [rbp+50h+pSecurityDescriptor]; pSecurityDescriptor
0x14003fc15  call    cs:__imp_SetSecurityDescriptorDacl
0x14003fc1c  nop     dword ptr [rax+rax+00h]
0x14003fc21  mov     rcx, [rbp+58h]; this
0x14003fc25  test    eax, eax
0x14003fc27  jnz     short loc_14003FC39
0x14003fc29  lea     r8, aOnecoreVmCompu_107; "onecore\\vm\\compute\\management\\orche"...
0x14003fc30  lea     edx, [rax+66h]; void *
0x14003fc33  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14003fc39  cmp     qword ptr [rsi+18h], 7
0x14003fc3e  jbe     short loc_14003FC45
0x14003fc40  mov     rcx, [rsi]
0x14003fc43  jmp     short loc_14003FC48
0x14003fc45  mov     rcx, rsi; lpFileName
0x14003fc48  mov     [rsp+150h+hTemplateFile], 0; hTemplateFile
0x14003fc51  mov     [rsp+150h+dwFlagsAndAttributes], 40100000h; dwFlagsAndAttributes
0x14003fc59  mov     [rsp+150h+dwCreationDisposition], 3; dwCreationDisposition
0x14003fc61  lea     r9, [rbp+50h+SecurityAttributes]; lpSecurityAttributes
0x14003fc65  xor     r8d, r8d; dwShareMode
0x14003fc68  mov     edx, 0C0000000h; dwDesiredAccess
0x14003fc6d  call    cs:__imp_CreateFileW
0x14003fc74  nop     dword ptr [rax+rax+00h]
0x14003fc79  mov     rcx, rax
0x14003fc7c  mov     [rbp+50h+pDacl], rax
0x14003fc80  dec     rax
0x14003fc83  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14003fc87  ja      short loc_14003FD05
0x14003fc89  xor     bl, bl
0x14003fc8b  mov     [r14], rcx
0x14003fc8e  mov     [r14+8], bl
0x14003fc92  test    rdi, rdi
0x14003fc95  jz      short loc_14003FCA7
0x14003fc97  mov     rcx, rdi; hMem
0x14003fc9a  call    cs:__imp_LocalFree
0x14003fca1  nop     dword ptr [rax+rax+00h]
0x14003fca6  nop
0x14003fca7  mov     rcx, [rbp+50h+Sid]; hMem
0x14003fcab  test    rcx, rcx
0x14003fcae  jz      short loc_14003FCBD
0x14003fcb0  call    cs:__imp_LocalFree
0x14003fcb7  nop     dword ptr [rax+rax+00h]
0x14003fcbc  nop
0x14003fcbd  mov     rcx, qword ptr [rbp+50h+var_88]
0x14003fcc1  test    rcx, rcx
0x14003fcc4  jz      short loc_14003FCE3
0x14003fcc6  mov     rdx, qword ptr [rbp+50h+var_88+8]
0x14003fcca  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>> &)
0x14003fccf  mov     rcx, qword ptr [rbp+50h+var_88]
0x14003fcd3  mov     rdx, [rbp+50h+var_78]
0x14003fcd7  sub     rdx, rcx
0x14003fcda  and     rdx, 0FFFFFFFFFFFFFFF8h
0x14003fcde  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14003fce3  mov     rax, r14
0x14003fce6  mov     rcx, [rbp+50h+var_40]
0x14003fcea  xor     rcx, rsp; StackCookie
0x14003fced  call    __security_check_cookie
0x14003fcf2  add     rsp, 120h
0x14003fcf9  pop     r15
0x14003fcfb  pop     r14
0x14003fcfd  pop     r12
0x14003fcff  pop     rdi
0x14003fd00  pop     rsi
0x14003fd01  pop     rbx
0x14003fd02  pop     rbp
0x14003fd03  retn
0x14003fd05  cmp     qword ptr [rsi+18h], 7
0x14003fd0a  jbe     short loc_14003FD0F
0x14003fd0c  mov     rsi, [rsi]
0x14003fd0f  lea     rax, [rbp+50h+SecurityAttributes]
0x14003fd13  mov     [rsp+150h+lpSecurityAttributes], rax; lpSecurityAttributes
0x14003fd18  mov     dword ptr [rsp+150h+hTemplateFile], 64h ; 'd'; nDefaultTimeOut
0x14003fd20  mov     [rsp+150h+dwFlagsAndAttributes], r12d; nInBufferSize
0x14003fd25  mov     [rsp+150h+dwCreationDisposition], 2000h; nOutBufferSize
0x14003fd2d  mov     r9d, ebx; nMaxInstances
0x14003fd30  xor     r8d, r8d; dwPipeMode
0x14003fd33  mov     edx, 40000003h; dwOpenMode
0x14003fd38  mov     rcx, rsi; lpName
0x14003fd3b  call    cs:__imp_CreateNamedPipeW
0x14003fd42  nop     dword ptr [rax+rax+00h]
0x14003fd47  mov     rdx, rax
0x14003fd4a  lea     rcx, [rbp+50h+pDacl]
0x14003fd4e  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14003fd53  mov     rcx, [rbp+50h+pDacl]
0x14003fd57  lea     rax, [rcx+1]
0x14003fd5b  test    rax, 0FFFFFFFFFFFFFFFEh
0x14003fd61  jnz     loc_14003FC8B
0x14003fd67  mov     rcx, [rbp+58h]; this
0x14003fd6b  lea     r8, aOnecoreVmCompu_107; "onecore\\vm\\compute\\management\\orche"...
0x14003fd72  mov     edx, 85h; void *
0x14003fd77  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x14003fd7c  xor     eax, eax
0x14003fd7e  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x14003fd85  mov     [r14+8], al
0x14003fd89  lea     rcx, [rbp+50h+pDacl]; void *
0x14003fd8d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14003fd92  nop
0x14003fd93  test    rdi, rdi
0x14003fd96  jz      short loc_14003FDA8
0x14003fd98  mov     rcx, rdi; hMem
0x14003fd9b  call    cs:__imp_LocalFree
0x14003fda2  nop     dword ptr [rax+rax+00h]
0x14003fda7  nop
0x14003fda8  lea     rcx, [rbp+50h+Sid]
0x14003fdac  call    ??1?$VmLocalPtr@U_TOKEN_PRIMARY_GROUP@@@Vml@@QEAA@XZ; Vml::VmLocalPtr<_TOKEN_PRIMARY_GROUP>::~VmLocalPtr<_TOKEN_PRIMARY_GROUP>(void)
0x14003fdb1  jmp     loc_14003FCBD
```
