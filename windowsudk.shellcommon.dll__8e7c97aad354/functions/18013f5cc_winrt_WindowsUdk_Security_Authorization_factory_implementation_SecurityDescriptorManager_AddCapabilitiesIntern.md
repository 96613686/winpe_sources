# winrt::WindowsUdk::Security::Authorization::factory_implementation::SecurityDescriptorManager::AddCapabilitiesInternal(_SE_OBJECT_TYPE,wchar_t const *,winrt::array_view<winrt::hstring const>)

- ea: `0x18013f5cc`
- end: `0x18013f983`
- name: `?AddCapabilitiesInternal@SecurityDescriptorManager@factory_implementation@Authorization@Security@WindowsUdk@winrt@@AEAAXW4_SE_OBJECT_TYPE@@PEB_WU?$array_view@$$CBUhstring@winrt@@@6@@Z`
- size: `951`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180155764`

## callees

- `0x180025348`
- `0x180026860`
- `0x180062160`
- `0x1800795e4`
- `0x18008fc6c`
- `0x1800902fc`
- `0x1800a8430`
- `0x1800e3810`
- `0x18013f5cc`
- `0x18013f98c`
- `0x18013fa00`
- `0x1801588c4`
- `0x18015cb00`
- `0x18015d868`
- `0x1802777a4`
- `0x1802b0c58`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18013f7a3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18013f7a3`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18013f8c8`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18013f8c8`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18013f866`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18013f866`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18013f69d`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18013f69d`
- `api-ms-win-security-trustee-l1-1-1!GetEffectiveRightsFromAclW` at `0x18013f7dc`
- `api-ms-win-security-trustee-l1-1-1!GetEffectiveRightsFromAclW` at `0x18013f7dc`

## string_xrefs

- `0x18013f6b1`: `shellcommon\undockeddevkit\libs\windowsudk.security.authorization\securitydescriptormanager.cpp`
- `0x18013f87a`: `shellcommon\undockeddevkit\libs\windowsudk.security.authorization\securitydescriptormanager.cpp`
- `0x18013f8dc`: `shellcommon\undockeddevkit\libs\windowsudk.security.authorization\securitydescriptormanager.cpp`
- `0x18013f958`: `shellcommon\undockeddevkit\libs\windowsudk.security.authorization\securitydescriptormanager.cpp`
- `0x18013f971`: `shellcommon\undockeddevkit\libs\windowsudk.security.authorization\securitydescriptormanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall winrt::WindowsUdk::Security::Authorization::factory_implementation::SecurityDescriptorManager::AddCapabilitiesInternal(
        __int64 a1,
        SE_OBJECT_TYPE a2,
        __int64 a3,
        __int64 a4)
{
  const char *v7; // r9
  _BYTE *v8; // rax
  __m256i *p_pObjectName; // rcx
  DWORD NamedSecurityInfoW; // eax
  struct _EXPLICIT_ACCESS_W *v11; // r14
  char *v12; // r13
  ULONG v13; // ebx
  winrt::hstring *v14; // rsi
  PSID *v15; // r12
  const WCHAR *v16; // rax
  const char *v17; // r9
  __int64 v18; // rax
  DWORD v19; // eax
  struct _ACL *v20; // rbx
  __m256i *v21; // rcx
  DWORD v22; // eax
  unsigned int ppsidGroup; // [rsp+20h] [rbp-E0h]
  unsigned int ppsidGroupa; // [rsp+20h] [rbp-E0h]
  DWORD pAccessRights[2]; // [rsp+40h] [rbp-C0h] BYREF
  PACL pacl; // [rsp+48h] [rbp-B8h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v29; // [rsp+58h] [rbp-A8h]
  char *v30; // [rsp+60h] [rbp-A0h] BYREF
  struct _EXPLICIT_ACCESS_W *v31; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v32[16]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v33[8]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v34[232]; // [rsp+88h] [rbp-78h] BYREF
  __m256i pObjectName; // [rsp+170h] [rbp+70h] BYREF
  __int128 pTrustee_16; // [rsp+190h] [rbp+90h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v32);
  if ( a2 == SE_REGISTRY_KEY )
  {
    v8 = (_BYTE *)std::operator<<<wchar_t,std::char_traits<wchar_t>>(v33, L"CURRENT_USER\\");
  }
  else
  {
    if ( a2 != SE_FILE_OBJECT )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x51,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.security.authorization\\securitydescriptormanager.cpp",
        v7);
    v8 = v33;
  }
  std::operator<<<wchar_t,std::char_traits<wchar_t>>(v8, a3);
  ppSecurityDescriptor = 0;
  pacl = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &ppSecurityDescriptor,
    0);
  std::wstringbuf::str(v34, &pObjectName);
  p_pObjectName = &pObjectName;
  if ( pObjectName.m256i_i64[3] > 7uLL )
    p_pObjectName = (__m256i *)pObjectName.m256i_i64[0];
  NamedSecurityInfoW = GetNamedSecurityInfoW((LPCWSTR)p_pObjectName, a2, 4u, 0, 0, &pacl, 0, &ppSecurityDescriptor);
  if ( NamedSecurityInfoW )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x60,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.security.authorization\\securitydescriptormanager.cpp",
      (const char *)NamedSecurityInfoW,
      ppsidGroup);
  std::filesystem::path::~path((std::filesystem::path *)&pObjectName);
  v11 = (struct _EXPLICIT_ACCESS_W *)operator new[](0x300u);
  memset_0(v11, 0, 0x300u);
  v31 = v11;
  memset_0(v11, 0, 0x300u);
  v12 = (char *)operator new[](0x80u);
  memset_0(v12, 0, 0x80u);
  v30 = v12;
  memset_0(v12, 0, 0x80u);
  v13 = 0;
  v14 = *(winrt::hstring **)a4;
  v29 = *(_QWORD *)a4 + 8LL * *(unsigned int *)(a4 + 8);
  if ( v14 != (winrt::hstring *)v29 )
  {
    do
    {
      memset((char *)&pObjectName.m256i_u64[1] + 4, 0, 20);
      pTrustee_16 = 2u;
      pObjectName.m256i_i64[0] = 0x110000000LL;
      pObjectName.m256i_i32[2] = 3;
      v15 = (PSID *)&v12[8 * v13];
      v16 = winrt::hstring::c_str(v14);
      if ( !ConvertStringSidToSidW(v16, v15) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x76,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.security.authorization\\securitydescriptormanager.cpp",
          v17);
      *((_QWORD *)&pTrustee_16 + 1) = *v15;
      pAccessRights[0] = 0;
      GetEffectiveRightsFromAclW(pacl, (PTRUSTEE_W)&pObjectName.m256i_u64[2], pAccessRights);
      if ( (a2 != SE_REGISTRY_KEY || pAccessRights[0] != 983103)
        && (a2 != SE_FILE_OBJECT || pAccessRights[0] != 2032127) )
      {
        v18 = v13;
        *(__m256i *)&v11[v18].grfAccessPermissions = pObjectName;
        *(_OWORD *)&v11[v18].Trustee.TrusteeType = pTrustee_16;
        ++v13;
      }
      v14 = (winrt::hstring *)((char *)v14 + 8);
    }
    while ( v14 != (winrt::hstring *)v29 );
    if ( v13 )
    {
      *(_QWORD *)pAccessRights = 0;
      v19 = SetEntriesInAclW(v13, v11, pacl, (PACL *)pAccessRights);
      if ( v19 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x8F,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.security.authorization\\securitydescriptormanager.cpp",
          (const char *)v19,
          ppsidGroup);
      v20 = *(struct _ACL **)pAccessRights;
      std::wstringbuf::str(v34, &pObjectName);
      v21 = &pObjectName;
      if ( pObjectName.m256i_i64[3] > 7uLL )
        v21 = (__m256i *)pObjectName.m256i_i64[0];
      v22 = SetNamedSecurityInfoW((LPWSTR)v21, a2, 4u, 0, 0, v20, 0);
      if ( v22 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x98,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.security.authorization\\securitydescriptormanager.cpp",
          (const char *)v22,
          ppsidGroupa);
      std::filesystem::path::~path((std::filesystem::path *)&pObjectName);
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(pAccessRights);
    }
  }
  std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&v30);
  std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&v31);
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&ppSecurityDescriptor);
  return std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(v32);
}

```

## disassembly

```asm
0x18013f5cc  mov     [rsp-8+arg_0], rbx
0x18013f5d1  push    rbp
0x18013f5d2  push    rsi
0x18013f5d3  push    rdi
0x18013f5d4  push    r12
0x18013f5d6  push    r13
0x18013f5d8  push    r14
0x18013f5da  push    r15
0x18013f5dc  lea     rbp, [rsp-0B0h]
0x18013f5e4  sub     rsp, 1B0h
0x18013f5eb  mov     rax, cs:__security_cookie
0x18013f5f2  xor     rax, rsp
0x18013f5f5  mov     [rbp+0E0h+var_40], rax
0x18013f5fc  mov     r15, r9
0x18013f5ff  mov     rbx, r8
0x18013f602  mov     edi, edx
0x18013f604  xor     r12d, r12d
0x18013f607  lea     rcx, [rsp+1E0h+var_170]
0x18013f60c  call    ??0?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)
0x18013f611  nop
0x18013f612  cmp     edi, 4
0x18013f615  jnz     short loc_18013F629
0x18013f617  lea     rdx, aCurrentUser; "CURRENT_USER\\"
0x18013f61e  lea     rcx, [rbp+0E0h+var_160]
0x18013f622  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x18013f627  jmp     short loc_18013F636
0x18013f629  cmp     edi, 1
0x18013f62c  jnz     loc_18013F96A
0x18013f632  lea     rax, [rbp+0E0h+var_160]
0x18013f636  mov     rdx, rbx
0x18013f639  mov     rcx, rax
0x18013f63c  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x18013f641  mov     [rsp+1E0h+var_190], r12
0x18013f646  mov     [rsp+1E0h+pacl], r12
0x18013f64b  xor     edx, edx
0x18013f64d  lea     rcx, [rsp+1E0h+var_190]
0x18013f652  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18013f657  lea     rdx, [rbp+0E0h+pObjectName]
0x18013f65b  lea     rcx, [rbp+0E0h+var_158]
0x18013f65f  call    ?str@?$basic_stringbuf@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::wstringbuf::str(void)
0x18013f664  nop
0x18013f665  lea     rcx, [rbp+0E0h+pObjectName]
0x18013f669  cmp     qword ptr [rbp+0E0h+pTrustee.MultipleTrusteeOperation], 7
0x18013f671  cmova   rcx, [rbp+0E0h+pObjectName]; pObjectName
0x18013f676  lea     rax, [rsp+1E0h+var_190]
0x18013f67b  mov     [rsp+1E0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18013f680  mov     [rsp+1E0h+ppSacl], r12; ppSacl
0x18013f685  lea     rax, [rsp+1E0h+pacl]
0x18013f68a  mov     [rsp+1E0h+ppDacl], rax; ppDacl
0x18013f68f  mov     [rsp+1E0h+ppsidGroup], r12; unsigned int
0x18013f694  xor     r9d, r9d; ppsidOwner
0x18013f697  lea     r8d, [r9+4]; SecurityInfo
0x18013f69b  mov     edx, edi; ObjectType
0x18013f69d  call    cs:__imp_GetNamedSecurityInfoW
0x18013f6a3  mov     rcx, [rbp+0E8h]; this
0x18013f6aa  test    eax, eax
0x18013f6ac  jz      short loc_18013F6C3
0x18013f6ae  mov     r9d, eax; char *
0x18013f6b1  lea     r8, aShellcommonUnd_130; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18013f6b8  mov     edx, 60h ; '`'; void *
0x18013f6bd  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18013f6c3  lea     rcx, [rbp+0E0h+pObjectName]; this
0x18013f6c7  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18013f6cc  mov     ebx, 300h
0x18013f6d1  mov     ecx, ebx; unsigned __int64
0x18013f6d3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18013f6d8  mov     r14, rax
0x18013f6db  mov     r8d, ebx; Size
0x18013f6de  xor     edx, edx; Val
0x18013f6e0  mov     rcx, rax; void *
0x18013f6e3  call    memset_0
0x18013f6e8  mov     [rsp+1E0h+var_178], r14
0x18013f6ed  mov     r8d, ebx; Size
0x18013f6f0  xor     edx, edx; Val
0x18013f6f2  mov     rcx, r14; void *
0x18013f6f5  call    memset_0
0x18013f6fa  mov     ebx, 80h
0x18013f6ff  mov     ecx, ebx; unsigned __int64
0x18013f701  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18013f706  mov     r13, rax
0x18013f709  mov     r8d, ebx; Size
0x18013f70c  xor     edx, edx; Val
0x18013f70e  mov     rcx, rax; void *
0x18013f711  call    memset_0
0x18013f716  mov     [rsp+1E0h+var_180], r13
0x18013f71b  mov     r8d, ebx; Size
0x18013f71e  xor     edx, edx; Val
0x18013f720  mov     rcx, r13; void *
0x18013f723  call    memset_0
0x18013f728  mov     ebx, r12d
0x18013f72b  mov     rsi, [r15]
0x18013f72e  mov     eax, [r15+8]
0x18013f732  lea     rax, [rsi+rax*8]
0x18013f736  mov     [rsp+1E0h+var_188], rax
0x18013f73b  cmp     rsi, rax
0x18013f73e  jz      loc_18013F903
0x18013f744  mov     [rbp+0E0h+pObjectName+0Ch], r12
0x18013f748  mov     qword ptr [rbp+84h], 0
0x18013f753  mov     qword ptr [rbp+0E0h+pTrustee+14h], r12
0x18013f75a  mov     dword ptr [rbp+0E0h+pTrustee.ptstrName+4], r12d
0x18013f761  mov     dword ptr [rbp+0E0h+pObjectName], 10000000h
0x18013f768  mov     dword ptr [rbp+0E0h+pObjectName+4], 1
0x18013f76f  mov     dword ptr [rbp+0E0h+pObjectName+8], 3
0x18013f776  mov     [rbp+0E0h+pTrustee.TrusteeForm], r12d
0x18013f77d  mov     [rbp+0E0h+pTrustee.TrusteeType], 2
0x18013f787  mov     r15d, ebx
0x18013f78a  lea     r12, ds:0[r15*8]
0x18013f792  add     r12, r13
0x18013f795  mov     rcx, rsi; this
0x18013f798  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x18013f79d  mov     rcx, rax; StringSid
0x18013f7a0  mov     rdx, r12; Sid
0x18013f7a3  call    cs:__imp_ConvertStringSidToSidW
0x18013f7a9  mov     rcx, [rbp+0E8h]; this
0x18013f7b0  test    eax, eax
0x18013f7b2  jz      loc_18013F958
0x18013f7b8  mov     rax, [r12]
0x18013f7bc  mov     [rbp+0E0h+pTrustee.ptstrName], rax
0x18013f7c3  xor     r12d, r12d
0x18013f7c6  mov     [rsp+1E0h+pAccessRights], r12d
0x18013f7cb  lea     r8, [rsp+1E0h+pAccessRights]; pAccessRights
0x18013f7d0  lea     rdx, [rbp+0E0h+pTrustee]; pTrustee
0x18013f7d7  mov     rcx, [rsp+1E0h+pacl]; pacl
0x18013f7dc  call    cs:__imp_GetEffectiveRightsFromAclW
0x18013f7e2  mov     eax, [rsp+1E0h+pAccessRights]
0x18013f7e6  cmp     edi, 4
0x18013f7e9  jnz     short loc_18013F7F2
0x18013f7eb  cmp     eax, 0F003Fh
0x18013f7f0  jz      short loc_18013F83B
0x18013f7f2  cmp     edi, 1
0x18013f7f5  jnz     short loc_18013F7FE
0x18013f7f7  cmp     eax, 1F01FFh
0x18013f7fc  jz      short loc_18013F83B
0x18013f7fe  cmp     edi, 4
0x18013f801  jz      short loc_18013F80F
0x18013f803  cmp     edi, 1
0x18013f806  jz      short loc_18013F80F
0x18013f808  cmp     eax, 0F8000000h
0x18013f80d  jz      short loc_18013F83B
0x18013f80f  lea     rax, [r15+r15*2]
0x18013f813  add     rax, rax
0x18013f816  movups  xmm0, xmmword ptr [rbp+0E0h+pObjectName]
0x18013f81a  movups  xmmword ptr [r14+rax*8], xmm0
0x18013f81f  movups  xmm1, xmmword ptr [rbp+80h]
0x18013f826  movups  xmmword ptr [r14+rax*8+10h], xmm1
0x18013f82c  movups  xmm0, xmmword ptr [rbp+0E0h+pTrustee.TrusteeType]
0x18013f833  movups  xmmword ptr [r14+rax*8+20h], xmm0
0x18013f839  inc     ebx
0x18013f83b  add     rsi, 8
0x18013f83f  cmp     rsi, [rsp+1E0h+var_188]
0x18013f844  jnz     loc_18013F744
0x18013f84a  test    ebx, ebx
0x18013f84c  jz      loc_18013F903
0x18013f852  mov     qword ptr [rsp+1E0h+pAccessRights], r12
0x18013f857  lea     r9, [rsp+1E0h+pAccessRights]; NewAcl
0x18013f85c  mov     r8, [rsp+1E0h+pacl]; OldAcl
0x18013f861  mov     rdx, r14; pListOfExplicitEntries
0x18013f864  mov     ecx, ebx; cCountOfExplicitEntries
0x18013f866  call    cs:__imp_SetEntriesInAclW
0x18013f86c  mov     rcx, [rbp+0E8h]; this
0x18013f873  test    eax, eax
0x18013f875  jz      short loc_18013F88C
0x18013f877  mov     r9d, eax; char *
0x18013f87a  lea     r8, aShellcommonUnd_130; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18013f881  mov     edx, 8Fh; void *
0x18013f886  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18013f88c  mov     rbx, qword ptr [rsp+1E0h+pAccessRights]
0x18013f891  lea     rdx, [rbp+0E0h+pObjectName]
0x18013f895  lea     rcx, [rbp+0E0h+var_158]
0x18013f899  call    ?str@?$basic_stringbuf@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::wstringbuf::str(void)
0x18013f89e  nop
0x18013f89f  lea     rcx, [rbp+0E0h+pObjectName]
0x18013f8a3  cmp     qword ptr [rbp+0E0h+pTrustee.MultipleTrusteeOperation], 7
0x18013f8ab  cmova   rcx, [rbp+0E0h+pObjectName]; pObjectName
0x18013f8b0  mov     [rsp+1E0h+ppSacl], r12; pSacl
0x18013f8b5  mov     [rsp+1E0h+ppDacl], rbx; pDacl
0x18013f8ba  mov     [rsp+1E0h+ppsidGroup], r12; unsigned int
0x18013f8bf  xor     r9d, r9d; psidOwner
0x18013f8c2  lea     r8d, [r9+4]; SecurityInfo
0x18013f8c6  mov     edx, edi; ObjectType
0x18013f8c8  call    cs:__imp_SetNamedSecurityInfoW
0x18013f8ce  mov     rcx, [rbp+0E8h]; this
0x18013f8d5  test    eax, eax
0x18013f8d7  jz      short loc_18013F8EE
0x18013f8d9  mov     r9d, eax; char *
0x18013f8dc  lea     r8, aShellcommonUnd_130; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18013f8e3  mov     edx, 98h; void *
0x18013f8e8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18013f8ee  lea     rcx, [rbp+0E0h+pObjectName]; this
0x18013f8f2  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18013f8f7  nop
0x18013f8f8  lea     rcx, [rsp+1E0h+pAccessRights]
0x18013f8fd  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18013f902  nop
0x18013f903  lea     rcx, [rsp+1E0h+var_180]
0x18013f908  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x18013f90d  nop
0x18013f90e  lea     rcx, [rsp+1E0h+var_178]
0x18013f913  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x18013f918  nop
0x18013f919  lea     rcx, [rsp+1E0h+var_190]
0x18013f91e  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18013f923  nop
0x18013f924  lea     rcx, [rsp+1E0h+var_170]
0x18013f929  call    ??_D?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAXXZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(void)
0x18013f92e  mov     rcx, [rbp+0E0h+var_40]
0x18013f935  xor     rcx, rsp; StackCookie
0x18013f938  call    __security_check_cookie
0x18013f93d  mov     rbx, [rsp+1E0h+arg_0]
0x18013f945  add     rsp, 1B0h
0x18013f94c  pop     r15
0x18013f94e  pop     r14
0x18013f950  pop     r13
0x18013f952  pop     r12
0x18013f954  pop     rdi
0x18013f955  pop     rsi
0x18013f956  pop     rbp
0x18013f957  retn
0x18013f958  lea     r8, aShellcommonUnd_130; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18013f95f  mov     edx, 76h ; 'v'; void *
0x18013f964  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18013f96a  mov     rcx, [rbp+0E8h]; this
0x18013f971  lea     r8, aShellcommonUnd_130; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18013f978  mov     edx, 51h ; 'Q'; void *
0x18013f97d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
