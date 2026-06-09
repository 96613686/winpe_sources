# ComputeService::VirtualMachine::Details::CreateRdpConnectionNamedPipe(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_GUID const &)

- ea: `0x1400b1df4`
- end: `0x1400b20dc`
- name: `?CreateRdpConnectionNamedPipe@Details@VirtualMachine@ComputeService@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@AEBU_GUID@@@Z`
- size: `744`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400b19a8`
- `0x1401ff62c`

## callees

- `0x14001bce0`
- `0x140033a7c`
- `0x140080180`
- `0x1400b1dd0`
- `0x1400b1df4`
- `0x1400b2108`
- `0x1400bd968`
- `0x1400be4dc`
- `0x1400e91a8`
- `0x1400f6494`
- `0x1400f64f4`
- `0x1400fcedc`
- `0x1400fd28c`
- `0x1401332f0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1400b1fd4`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1400b1fd4`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1400b1fa0`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1400b1fa0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1400b1e74`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1400b1edf`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1400b1e74`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1400b1edf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400b2078`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400b2078`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x1400b2038`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x1400b2038`

## string_xrefs

- `0x1400b1ef3`: `onecore\vm\compute\management\orchestration\shared\vmconfig\configurationhelpers.cpp`
- `0x1400b1f05`: `onecore\vm\compute\management\orchestration\shared\vmconfig\configurationhelpers.cpp`
- `0x1400b1fb4`: `onecore\vm\compute\management\orchestration\shared\vmconfig\configurationhelpers.cpp`
- `0x1400b1fe8`: `onecore\vm\compute\management\orchestration\shared\vmconfig\configurationhelpers.cpp`
- `0x1400b205d`: `onecore\vm\compute\management\orchestration\shared\vmconfig\configurationhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall ComputeService::VirtualMachine::Details::CreateRdpConnectionNamedPipe(
        _QWORD *a1,
        __int64 a2,
        const WCHAR *a3,
        DWORD *a4)
{
  const struct _GUID *v7; // rdx
  __int64 v8; // rbx
  __int64 v9; // r14
  const WCHAR *v10; // rcx
  const char *v11; // r9
  const char *v12; // r9
  unsigned int v13; // edx
  void **i; // rbx
  void **v15; // r14
  const char *v16; // r9
  const char *v17; // r9
  char *v18; // rax
  const char *v19; // r9
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+50h] [rbp-49h] BYREF
  PSID Sid; // [rsp+68h] [rbp-31h] BYREF
  PSID v23; // [rsp+70h] [rbp-29h] BYREF
  __int128 v24; // [rsp+78h] [rbp-21h] BYREF
  __int64 v25; // [rsp+88h] [rbp-11h]
  PACL pDacl[2]; // [rsp+90h] [rbp-9h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v28; // [rsp+C0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v24 = 0;
  v25 = 0;
  std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(&v24);
  v8 = *(_QWORD *)&v7->Data1;
  v9 = *(_QWORD *)v7->Data4;
  while ( v8 != v9 )
  {
    Sid = 0;
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &Sid,
      0);
    if ( *(_QWORD *)(v8 + 24) <= 7u )
      v10 = (const WCHAR *)v8;
    else
      v10 = *(const WCHAR **)v8;
    if ( !ConvertStringSidToSidW(v10, &Sid) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x8F7,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmconfig\\configurationhelpers.cpp",
        v11);
    std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::emplace_back<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(
      &v24,
      &Sid);
    Vml::VmLocalPtr<_TOKEN_PRIMARY_GROUP>::~VmLocalPtr<_TOKEN_PRIMARY_GROUP>(&Sid);
    v8 += 32;
  }
  Sid = WpSecurity::AllocateVirtualMachineSid(a4, v7);
  std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::emplace_back<void *>(
    &v24,
    &Sid);
  v23 = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &v23,
    0);
  if ( !ConvertStringSidToSidW(
          L"S-1-15-3-1024-2268835264-3721307629-241982045-173645152-1490879176-104643441-2915960892-1612460704",
          &v23) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x8FF,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmconfig\\configurationhelpers.cpp",
      v12);
  std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::emplace_back<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(
    &v24,
    &v23);
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 1;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v28 = 0;
  SecurityAttributes.lpSecurityDescriptor = pSecurityDescriptor;
  *(_OWORD *)pDacl = 0;
  Vml::VmDacl::VmDacl((Vml::VmDacl *)pDacl, 0);
  Vml::VmAcl::Initialize((Vml::VmAcl *)pDacl, v13);
  v15 = (void **)*((_QWORD *)&v24 + 1);
  for ( i = (void **)v24; i != v15; ++i )
    Vml::VmAcl::UpdateAccess((Vml::VmAcl *)pDacl, *i, 0x1F01FFu, 0, GRANT_ACCESS);
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x910,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmconfig\\configurationhelpers.cpp",
      v16);
  if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pDacl[0], 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x911,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmconfig\\configurationhelpers.cpp",
      v17);
  *a1 = 0;
  if ( *((_QWORD *)a3 + 3) > 7u )
    a3 = *(const WCHAR **)a3;
  v18 = (char *)CreateNamedPipeW(a3, 0x40000003u, 0, 0xFFu, 0x8000u, 0x8000u, 0, &SecurityAttributes);
  *a1 = v18;
  if ( (unsigned __int64)(v18 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x91D,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmconfig\\configurationhelpers.cpp",
      v19);
  if ( pDacl[0] )
    LocalFree(pDacl[0]);
  Vml::VmLocalPtr<_TOKEN_PRIMARY_GROUP>::~VmLocalPtr<_TOKEN_PRIMARY_GROUP>(&v23);
  if ( (_QWORD)v24 )
  {
    std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>(
      v24,
      *((_QWORD *)&v24 + 1));
    std::_Deallocate<16>(v24, (v25 - v24) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  return a1;
}

```

## disassembly

```asm
0x1400b1df4  mov     [rsp-8+arg_18], rbx
0x1400b1df9  push    rbp
0x1400b1dfa  push    rsi
0x1400b1dfb  push    rdi
0x1400b1dfc  push    r14
0x1400b1dfe  push    r15
0x1400b1e00  lea     rbp, [rsp-37h]
0x1400b1e05  sub     rsp, 0D0h
0x1400b1e0c  mov     rax, cs:__security_cookie
0x1400b1e13  xor     rax, rsp
0x1400b1e16  mov     [rbp+57h+var_28], rax
0x1400b1e1a  mov     r15, r9
0x1400b1e1d  mov     rdi, r8
0x1400b1e20  mov     rsi, rcx
0x1400b1e23  mov     [rbp+57h+var_A8], rcx
0x1400b1e27  mov     [rbp+57h+var_B0], 0
0x1400b1e2e  xorps   xmm0, xmm0
0x1400b1e31  xor     eax, eax
0x1400b1e33  movups  [rbp+57h+var_78], xmm0
0x1400b1e37  mov     [rbp+57h+var_68], rax
0x1400b1e3b  lea     rcx, [rbp+57h+var_78]
0x1400b1e3f  call    ??0?$vector@UVpSubnodeMetadata@VirtualMachine@Config@@V?$allocator@UVpSubnodeMetadata@VirtualMachine@Config@@@std@@@std@@QEAA@XZ; std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(void)
0x1400b1e44  nop
0x1400b1e45  mov     rbx, [rdx]
0x1400b1e48  mov     r14, [rdx+8]
0x1400b1e4c  jmp     short loc_1400B1EA3
0x1400b1e4e  mov     [rbp+57h+Sid], 0
0x1400b1e56  xor     edx, edx
0x1400b1e58  lea     rcx, [rbp+57h+Sid]
0x1400b1e5c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1400b1e61  cmp     qword ptr [rbx+18h], 7
0x1400b1e66  jbe     short loc_1400B1E6D
0x1400b1e68  mov     rcx, [rbx]
0x1400b1e6b  jmp     short loc_1400B1E70
0x1400b1e6d  mov     rcx, rbx; StringSid
0x1400b1e70  lea     rdx, [rbp+57h+Sid]; Sid
0x1400b1e74  call    cs:__imp_ConvertStringSidToSidW
0x1400b1e7b  nop     dword ptr [rax+rax+00h]
0x1400b1e80  mov     rcx, [rbp+5Fh]; this
0x1400b1e84  test    eax, eax
0x1400b1e86  jz      short loc_1400B1F05
0x1400b1e88  lea     rdx, [rbp+57h+Sid]
0x1400b1e8c  lea     rcx, [rbp+57h+var_78]
0x1400b1e90  call    ??$emplace_back@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::emplace_back<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&)
0x1400b1e95  nop
0x1400b1e96  lea     rcx, [rbp+57h+Sid]
0x1400b1e9a  call    ??1?$VmLocalPtr@U_TOKEN_PRIMARY_GROUP@@@Vml@@QEAA@XZ; Vml::VmLocalPtr<_TOKEN_PRIMARY_GROUP>::~VmLocalPtr<_TOKEN_PRIMARY_GROUP>(void)
0x1400b1e9f  add     rbx, 20h ; ' '
0x1400b1ea3  cmp     rbx, r14
0x1400b1ea6  jnz     short loc_1400B1E4E
0x1400b1ea8  mov     rcx, r15; this
0x1400b1eab  call    ?AllocateVirtualMachineSid@WpSecurity@@YAPEAXAEBU_GUID@@@Z; WpSecurity::AllocateVirtualMachineSid(_GUID const &)
0x1400b1eb0  mov     [rbp+57h+Sid], rax
0x1400b1eb4  lea     rdx, [rbp+57h+Sid]
0x1400b1eb8  lea     rcx, [rbp+57h+var_78]
0x1400b1ebc  call    ??$emplace_back@PEAX@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@$$QEAPEAX@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::emplace_back<void *>(void * &&)
0x1400b1ec1  mov     [rbp+57h+var_80], 0
0x1400b1ec9  xor     edx, edx
0x1400b1ecb  lea     rcx, [rbp+57h+var_80]
0x1400b1ecf  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1400b1ed4  lea     rdx, [rbp+57h+var_80]; Sid
0x1400b1ed8  lea     rcx, StringSid; "S-1-15-3-1024-2268835264-3721307629-241"...
0x1400b1edf  call    cs:__imp_ConvertStringSidToSidW
0x1400b1ee6  nop     dword ptr [rax+rax+00h]
0x1400b1eeb  mov     rcx, [rbp+5Fh]; this
0x1400b1eef  test    eax, eax
0x1400b1ef1  jnz     short loc_1400B1F17
0x1400b1ef3  lea     r8, aOnecoreVmCompu_72; "onecore\\vm\\compute\\management\\orche"...
0x1400b1efa  mov     edx, 8FFh; void *
0x1400b1eff  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400b1f05  lea     r8, aOnecoreVmCompu_72; "onecore\\vm\\compute\\management\\orche"...
0x1400b1f0c  mov     edx, 8F7h; void *
0x1400b1f11  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400b1f17  lea     rdx, [rbp+57h+var_80]
0x1400b1f1b  lea     rcx, [rbp+57h+var_78]
0x1400b1f1f  call    ??$emplace_back@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::emplace_back<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&)
0x1400b1f24  mov     qword ptr [rbp+57h+SecurityAttributes.nLength], 18h
0x1400b1f2c  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], 1
0x1400b1f34  xorps   xmm0, xmm0
0x1400b1f37  xor     eax, eax
0x1400b1f39  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x1400b1f3d  movups  [rbp+57h+var_40], xmm0
0x1400b1f41  mov     [rbp+57h+var_30], rax
0x1400b1f45  lea     rax, [rbp+57h+pSecurityDescriptor]
0x1400b1f49  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x1400b1f4d  mov     r15d, 1
0x1400b1f53  movups  xmmword ptr [rbp+57h+pDacl], xmm0
0x1400b1f57  xor     edx, edx; struct _ACL *
0x1400b1f59  lea     rcx, [rbp+57h+pDacl]; this
0x1400b1f5d  call    ??0VmDacl@Vml@@QEAA@PEBU_ACL@@@Z; Vml::VmDacl::VmDacl(_ACL const *)
0x1400b1f62  nop
0x1400b1f63  lea     rcx, [rbp+57h+pDacl]; this
0x1400b1f67  call    ?Initialize@VmAcl@Vml@@QEAAXK@Z; Vml::VmAcl::Initialize(ulong)
0x1400b1f6c  mov     rbx, qword ptr [rbp+57h+var_78]
0x1400b1f70  mov     r14, qword ptr [rbp+57h+var_78+8]
0x1400b1f74  jmp     short loc_1400B1F94
0x1400b1f76  mov     [rsp+0F0h+nOutBufferSize], r15d; enum _ACCESS_MODE
0x1400b1f7b  xor     r9d, r9d; unsigned int
0x1400b1f7e  mov     r8d, 1F01FFh; unsigned int
0x1400b1f84  mov     rdx, [rbx]; void *
0x1400b1f87  lea     rcx, [rbp+57h+pDacl]; this
0x1400b1f8b  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x1400b1f90  add     rbx, 8
0x1400b1f94  cmp     rbx, r14
0x1400b1f97  jnz     short loc_1400B1F76
0x1400b1f99  mov     edx, r15d; dwRevision
0x1400b1f9c  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1400b1fa0  call    cs:__imp_InitializeSecurityDescriptor
0x1400b1fa7  nop     dword ptr [rax+rax+00h]
0x1400b1fac  mov     rcx, [rbp+5Fh]; this
0x1400b1fb0  test    eax, eax
0x1400b1fb2  jnz     short loc_1400B1FC6
0x1400b1fb4  lea     r8, aOnecoreVmCompu_72; "onecore\\vm\\compute\\management\\orche"...
0x1400b1fbb  mov     edx, 910h; void *
0x1400b1fc0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400b1fc6  xor     r9d, r9d; bDaclDefaulted
0x1400b1fc9  mov     r8, [rbp+57h+pDacl]; pDacl
0x1400b1fcd  mov     edx, r15d; bDaclPresent
0x1400b1fd0  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1400b1fd4  call    cs:__imp_SetSecurityDescriptorDacl
0x1400b1fdb  nop     dword ptr [rax+rax+00h]
0x1400b1fe0  mov     rcx, [rbp+5Fh]; this
0x1400b1fe4  test    eax, eax
0x1400b1fe6  jnz     short loc_1400B1FFA
0x1400b1fe8  lea     r8, aOnecoreVmCompu_72; "onecore\\vm\\compute\\management\\orche"...
0x1400b1fef  mov     edx, 911h; void *
0x1400b1ff4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400b1ffa  xor     eax, eax
0x1400b1ffc  mov     [rsi], rax
0x1400b1fff  cmp     qword ptr [rdi+18h], 7
0x1400b2004  jbe     short loc_1400B2009
0x1400b2006  mov     rdi, [rdi]
0x1400b2009  lea     rax, [rbp+57h+SecurityAttributes]
0x1400b200d  mov     [rsp+0F0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x1400b2012  mov     [rsp+0F0h+nDefaultTimeOut], 0; nDefaultTimeOut
0x1400b201a  mov     eax, 8000h
0x1400b201f  mov     [rsp+0F0h+nInBufferSize], eax; nInBufferSize
0x1400b2023  mov     [rsp+0F0h+nOutBufferSize], eax; nOutBufferSize
0x1400b2027  mov     r9d, 0FFh; nMaxInstances
0x1400b202d  xor     r8d, r8d; dwPipeMode
0x1400b2030  mov     edx, 40000003h; dwOpenMode
0x1400b2035  mov     rcx, rdi; lpName
0x1400b2038  call    cs:__imp_CreateNamedPipeW
0x1400b203f  nop     dword ptr [rax+rax+00h]
0x1400b2044  mov     [rsi], rax
0x1400b2047  mov     [rbp+57h+var_B0], r15d
0x1400b204b  dec     rax
0x1400b204e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400b2052  setnbe  al
0x1400b2055  mov     rcx, [rbp+5Fh]; this
0x1400b2059  test    al, al
0x1400b205b  jz      short loc_1400B206F
0x1400b205d  lea     r8, aOnecoreVmCompu_72; "onecore\\vm\\compute\\management\\orche"...
0x1400b2064  mov     edx, 91Dh; void *
0x1400b2069  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400b206f  mov     rcx, [rbp+57h+pDacl]; hMem
0x1400b2073  test    rcx, rcx
0x1400b2076  jz      short loc_1400B2085
0x1400b2078  call    cs:__imp_LocalFree
0x1400b207f  nop     dword ptr [rax+rax+00h]
0x1400b2084  nop
0x1400b2085  lea     rcx, [rbp+57h+var_80]
0x1400b2089  call    ??1?$VmLocalPtr@U_TOKEN_PRIMARY_GROUP@@@Vml@@QEAA@XZ; Vml::VmLocalPtr<_TOKEN_PRIMARY_GROUP>::~VmLocalPtr<_TOKEN_PRIMARY_GROUP>(void)
0x1400b208e  nop
0x1400b208f  mov     rcx, qword ptr [rbp+57h+var_78]
0x1400b2093  test    rcx, rcx
0x1400b2096  jz      short loc_1400B20B5
0x1400b2098  mov     rdx, qword ptr [rbp+57h+var_78+8]
0x1400b209c  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>> &)
0x1400b20a1  mov     rcx, qword ptr [rbp+57h+var_78]
0x1400b20a5  mov     rdx, [rbp+57h+var_68]
0x1400b20a9  sub     rdx, rcx
0x1400b20ac  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1400b20b0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1400b20b5  mov     rax, rsi
0x1400b20b8  mov     rcx, [rbp+57h+var_28]
0x1400b20bc  xor     rcx, rsp; StackCookie
0x1400b20bf  call    __security_check_cookie
0x1400b20c4  mov     rbx, [rsp+0F0h+arg_18]
0x1400b20cc  add     rsp, 0D0h
0x1400b20d3  pop     r15
0x1400b20d5  pop     r14
0x1400b20d7  pop     rdi
0x1400b20d8  pop     rsi
0x1400b20d9  pop     rbp
0x1400b20da  retn
```
