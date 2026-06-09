# ComputeService::VmSharedMemoryUtilities::OpenObDirectoryForVmSharedMemory(_GUID const &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &)

- ea: `0x140041ad8`
- end: `0x140041fb2`
- name: `?OpenObDirectoryForVmSharedMemory@VmSharedMemoryUtilities@ComputeService@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBU_GUID@@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `1242`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14019d128`
- `0x1401cdb60`

## callees

- `0x140017040`
- `0x140018d70`
- `0x140041ad8`
- `0x1400421f0`
- `0x140042468`
- `0x14004249c`
- `0x1400425e4`
- `0x140064c5c`
- `0x140080180`
- `0x140087ef4`
- `0x140088698`
- `0x1400bc8f4`
- `0x1400bd968`
- `0x1400bdc70`
- `0x1400bf1c4`
- `0x1400c40e0`
- `0x1400c4154`
- `0x1400d2e2c`
- `0x1400e91a8`
- `0x1400f74cc`
- `0x1401332f0`
- `0x1401336bc`
- `0x140134048`
- `0x140142dac`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x140041cd7`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x140041cd7`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x140041ca3`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x140041ca3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x140041e90`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x140041e90`
- `ntdll!NtCreateDirectoryObject` at `0x140041d51`
- `ntdll!NtCreateDirectoryObject` at `0x140041d51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140041d7e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140041d93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140041dba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140041d7e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140041d93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140041dba`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x140041c5b`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x140041c5b`

## string_xrefs

- `0x140041f2a`: `onecore\vm\common\vml\VmSecurity.h`
- `0x140041f3c`: `onecore\vm\common\vml\VmSecurity.h`
- `0x140041f4e`: `onecore\vm\common\vml\VmSecurity.h`
- `0x140041f04`: `onecore\vm\compute\management\orchestration\shared\vmsharedmemory\vmsharedmemoryutilities.cpp`
- `0x140041f63`: `onecore\vm\compute\management\orchestration\shared\vmsharedmemory\vmsharedmemoryutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
_QWORD *__fastcall ComputeService::VmSharedMemoryUtilities::OpenObDirectoryForVmSharedMemory(
        _QWORD *a1,
        DWORD *a2,
        _QWORD *a3)
{
  __int64 v6; // r8
  char v7; // al
  void **v8; // r9
  void **v9; // rax
  const struct _GUID *v10; // rdx
  void *VirtualMachineSid; // rbx
  PSID v12; // r14
  DWORD v13; // eax
  struct _ACL *v14; // rdi
  __int64 v15; // rbx
  __int64 v16; // r15
  const char *v17; // r9
  PSECURITY_DESCRIPTOR v18; // rbx
  const char *v19; // r9
  void **v20; // rax
  NTSTATUS v21; // eax
  struct _ACL *v22; // rdx
  void *v23; // rcx
  void *v24; // rdx
  PACL v25; // rcx
  const WCHAR *v27; // rcx
  enum _ACCESS_MODE v28; // [rsp+20h] [rbp-E0h]
  void *v29[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v30; // [rsp+40h] [rbp-C0h] BYREF
  int v31; // [rsp+50h] [rbp-B0h]
  PACL NewAcl; // [rsp+58h] [rbp-A8h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor[2]; // [rsp+90h] [rbp-70h] BYREF
  void *v35[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v36; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v37; // [rsp+B8h] [rbp-48h]
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+C0h] [rbp-40h] BYREF
  void *v39[3]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int64 v40; // [rsp+128h] [rbp+28h]
  __int128 v41; // [rsp+130h] [rbp+30h] BYREF
  PSID pOwner; // [rsp+140h] [rbp+40h] BYREF
  int v43; // [rsp+148h] [rbp+48h]
  _BYTE v44[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v45[32]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v29[0] = a1;
  v31 = 0;
  ComputeService::VmSharedMemoryUtilities::SetupVmSharedMemoryRoot((ComputeService::VmSharedMemoryUtilities *)a1);
  if ( a3[1] == *a3 || (v7 = 0, !*(_QWORD *)(*a3 + 16LL)) )
    v7 = 1;
  if ( v7 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x69,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmsharedmemory\\vmsharedmemoryutilities.cpp",
      (const char *)0x80070057LL,
      v28);
  LOBYTE(v6) = 1;
  Vml::GuidToString(v39, a2, v6);
  v8 = v39;
  if ( v40 > 7 )
    v8 = (void **)v39[0];
  Vml::FormatString(v35, L"%s\\%s", L"\\VmSharedMemory\\Host", v8);
  v9 = v35;
  if ( v37 > 7 )
    v9 = (void **)v35[0];
  WORD3(v30) = 0;
  *((_QWORD *)&v30 + 1) = v9;
  LOWORD(v30) = 2 * v36;
  *(_DWORD *)((char *)&v30 + 2) = (unsigned __int16)(2 * v36);
  v41 = v30;
  pSecurityDescriptor[1] = 0;
  pSecurityDescriptor[0] = 0;
  Vml::VmSecurityDescriptor::Initialize((Vml::VmSecurityDescriptor *)pSecurityDescriptor);
  memset_0(&pOwner, 0, 0x50u);
  VirtualMachineSid = WpSecurity::AllocateVirtualMachineSid(a2, v10);
  pOwner = 0;
  v43 = 7;
  std::wstring::wstring(v44);
  std::wstring::wstring(v45);
  if ( VirtualMachineSid )
    Vml::VmSid::Assign((Vml::VmSid *)&pOwner, VirtualMachineSid);
  v30 = 0u;
  *(_QWORD *)&pListOfExplicitEntries.grfInheritance = 3;
  pListOfExplicitEntries.grfAccessPermissions = 0x10000000;
  pListOfExplicitEntries.grfAccessMode = SET_ACCESS;
  memset(&pListOfExplicitEntries.Trustee, 0, 24);
  v12 = pOwner;
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pOwner;
  NewAcl = 0;
  v13 = SetEntriesInAclW(1u, &pListOfExplicitEntries, 0, &NewAcl);
  if ( v13 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1713,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      (const char *)v13,
      v28);
  v14 = NewAcl;
  *(_QWORD *)&v30 = NewAcl;
  v15 = *a3;
  v16 = a3[1];
  if ( v15 != v16 )
  {
    do
    {
      memset_0(&pListOfExplicitEntries, 0, 0x50u);
      Vml::VmSid::VmSid((Vml::VmSid *)&pListOfExplicitEntries, 0);
      if ( *(_QWORD *)(v15 + 24) <= 7u )
        v27 = (const WCHAR *)v15;
      else
        v27 = *(const WCHAR **)v15;
      ConvertStringSidToSidW(v27, (PSID *)&pListOfExplicitEntries);
      Vml::VmAcl::UpdateAccess(
        (Vml::VmAcl *)&v30,
        *(void **)&pListOfExplicitEntries.grfAccessPermissions,
        0x80000000,
        0,
        GRANT_ACCESS);
      Vml::VmAcl::UpdateAccess(
        (Vml::VmAcl *)&v30,
        *(void **)&pListOfExplicitEntries.grfAccessPermissions,
        0x10000000u,
        1u,
        GRANT_ACCESS);
      Vml::VmSid::~VmSid((Vml::VmSid *)&pListOfExplicitEntries);
      v15 += 32;
    }
    while ( v15 != v16 );
    v14 = (struct _ACL *)v30;
  }
  Vml::VmSecurityDescriptor::MakeAbsolute((Vml::VmSecurityDescriptor *)pSecurityDescriptor);
  if ( !SetSecurityDescriptorOwner(pSecurityDescriptor[0], v12, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xD50,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v17);
  Vml::VmSecurityDescriptor::MakeAbsolute((Vml::VmSecurityDescriptor *)pSecurityDescriptor);
  v18 = pSecurityDescriptor[0];
  if ( !SetSecurityDescriptorDacl(pSecurityDescriptor[0], 1, v14, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xDD6,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v19);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v41;
  ObjectAttributes.SecurityDescriptor = v18;
  ObjectAttributes.SecurityQualityOfService = 0;
  *a1 = 0;
  v31 = 1;
  memset(&pListOfExplicitEntries, 0, 24);
  Vml::TemporaryPrivilege::TemporaryPrivilege((struct _LUID *)&pListOfExplicitEntries, 18);
  v20 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(a1);
  v21 = NtCreateDirectoryObject(v20, 0xF000Fu, &ObjectAttributes);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x95,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmsharedmemory\\vmsharedmemoryutilities.cpp",
      (const char *)(unsigned int)v21,
      v28);
  Vml::TemporaryPrivilege::~TemporaryPrivilege((struct _LUID *)&pListOfExplicitEntries);
  if ( v14 )
    LocalFree(v14);
  if ( v12 )
    LocalFree(v12);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v45);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v44);
  if ( v18 )
    LocalFree(v18);
  if ( v37 > 7 )
  {
    v22 = (struct _ACL *)(2 * v37 + 2);
    NewAcl = v22;
    v23 = v35[0];
    v29[0] = v35[0];
    if ( (unsigned __int64)v22 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(v29, (unsigned __int64 *)&NewAcl);
      v22 = NewAcl;
      v23 = v29[0];
    }
    operator delete(v23, (const struct std::nothrow_t *)v22);
  }
  v36 = 0;
  v37 = 7;
  LOWORD(v35[0]) = 0;
  if ( v40 > 7 )
  {
    v24 = (void *)(2 * v40 + 2);
    v29[0] = v24;
    v25 = (PACL)v39[0];
    NewAcl = (PACL)v39[0];
    if ( (unsigned __int64)v24 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned((void **)&NewAcl, (unsigned __int64 *)v29);
      v24 = v29[0];
      v25 = NewAcl;
    }
    operator delete(v25, (const struct std::nothrow_t *)v24);
  }
  return a1;
}

```

## disassembly

```asm
0x140041ad8  mov     [rsp-8+arg_18], rbx
0x140041add  push    rbp
0x140041ade  push    rsi
0x140041adf  push    rdi
0x140041ae0  push    r12
0x140041ae2  push    r13
0x140041ae4  push    r14
0x140041ae6  push    r15
0x140041ae8  lea     rbp, [rsp-0A0h]
0x140041af0  sub     rsp, 1A0h
0x140041af7  mov     rax, cs:__security_cookie
0x140041afe  xor     rax, rsp
0x140041b01  mov     [rbp+0D0h+var_40], rax
0x140041b08  mov     r15, r8
0x140041b0b  mov     rbx, rdx
0x140041b0e  mov     rsi, rcx
0x140041b11  mov     [rsp+1D0h+var_1A0], rcx
0x140041b16  xor     r12d, r12d
0x140041b19  mov     [rsp+1D0h+var_180], r12d
0x140041b1e  call    ?SetupVmSharedMemoryRoot@VmSharedMemoryUtilities@ComputeService@@YAXXZ; ComputeService::VmSharedMemoryUtilities::SetupVmSharedMemoryRoot(void)
0x140041b23  mov     rcx, [r15]
0x140041b26  lea     r13d, [r12+1]
0x140041b2b  cmp     [r15+8], rcx
0x140041b2f  jz      loc_140041EF6
0x140041b35  cmp     [rcx+10h], r12
0x140041b39  mov     al, r12b
0x140041b3c  jz      loc_140041EF6
0x140041b42  mov     rcx, [rbp+0D8h]; this
0x140041b49  test    al, al
0x140041b4b  jnz     loc_140041EFE
0x140041b51  mov     r8b, r13b
0x140041b54  mov     rdx, rbx
0x140041b57  lea     rcx, [rbp+0D0h+var_C0]
0x140041b5b  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x140041b60  nop
0x140041b61  lea     r9, [rbp+0D0h+var_C0]
0x140041b65  cmp     [rbp+0D0h+var_A8], 7
0x140041b6a  cmova   r9, [rbp+0D0h+var_C0]
0x140041b6f  lea     r8, aVmsharedmemory_0; "\\VmSharedMemory\\Host"
0x140041b76  lea     rdx, aSS; "%s\\%s"
0x140041b7d  lea     rcx, [rbp+0D0h+var_130]
0x140041b81  call    ?FormatString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(ushort const *,...)
0x140041b86  nop
0x140041b87  lea     rax, [rbp+0D0h+var_130]
0x140041b8b  cmp     [rbp+0D0h+var_118], 7
0x140041b90  cmova   rax, [rbp+0D0h+var_130]
0x140041b95  mov     rcx, [rbp+0D0h+var_120]
0x140041b99  mov     dword ptr [rsp+1D0h+var_190+4], r12d
0x140041b9e  mov     qword ptr [rsp+1D0h+var_190+8], rax
0x140041ba3  add     cx, cx
0x140041ba6  mov     word ptr [rsp+1D0h+var_190], cx
0x140041bab  mov     word ptr [rsp+1D0h+var_190+2], cx
0x140041bb0  movaps  xmm0, [rsp+1D0h+var_190]
0x140041bb5  movdqa  [rbp+0D0h+var_A0], xmm0
0x140041bba  xorps   xmm1, xmm1
0x140041bbd  movups  xmmword ptr [rbp+0D0h+pSecurityDescriptor], xmm1
0x140041bc1  mov     [rbp+0D0h+pSecurityDescriptor], r12
0x140041bc5  lea     rcx, [rbp+0D0h+pSecurityDescriptor]; this
0x140041bc9  call    ?Initialize@VmSecurityDescriptor@Vml@@QEAAXXZ; Vml::VmSecurityDescriptor::Initialize(void)
0x140041bce  xor     edx, edx; Val
0x140041bd0  lea     r8d, [rdx+50h]; Size
0x140041bd4  lea     rcx, [rbp+0D0h+pOwner]; void *
0x140041bd8  call    memset_0
0x140041bdd  mov     rcx, rbx; this
0x140041be0  call    ?AllocateVirtualMachineSid@WpSecurity@@YAPEAXAEBU_GUID@@@Z; WpSecurity::AllocateVirtualMachineSid(_GUID const &)
0x140041be5  mov     rbx, rax
0x140041be8  mov     [rbp+0D0h+pOwner], r12
0x140041bec  mov     [rbp+0D0h+var_88], 7
0x140041bf3  lea     rcx, [rbp+0D0h+var_80]; void *
0x140041bf7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140041bfc  nop
0x140041bfd  lea     rcx, [rbp+0D0h+var_60]; void *
0x140041c01  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140041c06  nop
0x140041c07  test    rbx, rbx
0x140041c0a  jnz     loc_140041F16
0x140041c10  xorps   xmm0, xmm0
0x140041c13  movups  [rsp+1D0h+var_190], xmm0
0x140041c18  mov     qword ptr [rsp+1D0h+var_190], r12
0x140041c1d  mov     qword ptr [rbp+0D0h+pListOfExplicitEntries.grfInheritance], 3
0x140041c25  mov     qword ptr [rbp+0D0h+pListOfExplicitEntries.Trustee.TrusteeType], r12
0x140041c29  mov     [rbp+0D0h+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x140041c30  mov     [rbp+0D0h+pListOfExplicitEntries.grfAccessMode], 2
0x140041c37  mov     [rbp+0D0h+pListOfExplicitEntries.Trustee.pMultipleTrustee], r12
0x140041c3b  mov     qword ptr [rbp+0D0h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], r12
0x140041c3f  mov     r14, [rbp+0D0h+pOwner]
0x140041c43  mov     [rbp+0D0h+pListOfExplicitEntries.Trustee.ptstrName], r14
0x140041c47  mov     [rsp+1D0h+NewAcl], r12
0x140041c4c  lea     r9, [rsp+1D0h+NewAcl]; NewAcl
0x140041c51  xor     r8d, r8d; OldAcl
0x140041c54  lea     rdx, [rbp+0D0h+pListOfExplicitEntries]; pListOfExplicitEntries
0x140041c58  mov     ecx, r13d; cCountOfExplicitEntries
0x140041c5b  call    cs:__imp_SetEntriesInAclW
0x140041c62  nop     dword ptr [rax+rax+00h]
0x140041c67  mov     rcx, [rbp+0D8h]; this
0x140041c6e  test    eax, eax
0x140041c70  jnz     loc_140041F27
0x140041c76  mov     rdi, [rsp+1D0h+NewAcl]
0x140041c7b  mov     qword ptr [rsp+1D0h+var_190], rdi
0x140041c80  mov     rbx, [r15]
0x140041c83  mov     r15, [r15+8]
0x140041c87  cmp     rbx, r15
0x140041c8a  jnz     loc_140041E67
0x140041c90  lea     rcx, [rbp+0D0h+pSecurityDescriptor]; this
0x140041c94  call    ?MakeAbsolute@VmSecurityDescriptor@Vml@@QEAAXXZ; Vml::VmSecurityDescriptor::MakeAbsolute(void)
0x140041c99  xor     r8d, r8d; bOwnerDefaulted
0x140041c9c  mov     rdx, r14; pOwner
0x140041c9f  mov     rcx, [rbp+0D0h+pSecurityDescriptor]; pSecurityDescriptor
0x140041ca3  call    cs:__imp_SetSecurityDescriptorOwner
0x140041caa  nop     dword ptr [rax+rax+00h]
0x140041caf  mov     rcx, [rbp+0D8h]; this
0x140041cb6  test    eax, eax
0x140041cb8  jz      loc_140041F3C
0x140041cbe  lea     rcx, [rbp+0D0h+pSecurityDescriptor]; this
0x140041cc2  call    ?MakeAbsolute@VmSecurityDescriptor@Vml@@QEAAXXZ; Vml::VmSecurityDescriptor::MakeAbsolute(void)
0x140041cc7  xor     r9d, r9d; bDaclDefaulted
0x140041cca  mov     r8, rdi; pDacl
0x140041ccd  mov     edx, r13d; bDaclPresent
0x140041cd0  mov     rbx, [rbp+0D0h+pSecurityDescriptor]
0x140041cd4  mov     rcx, rbx; pSecurityDescriptor
0x140041cd7  call    cs:__imp_SetSecurityDescriptorDacl
0x140041cde  nop     dword ptr [rax+rax+00h]
0x140041ce3  mov     rcx, [rbp+0D8h]; this
0x140041cea  test    eax, eax
0x140041cec  jz      loc_140041F4E
0x140041cf2  mov     qword ptr [rsp+1D0h+ObjectAttributes.Length], 30h ; '0'
0x140041cfb  mov     qword ptr [rsp+1D0h+ObjectAttributes.Attributes], 40h ; '@'
0x140041d04  mov     [rsp+1D0h+ObjectAttributes.RootDirectory], r12
0x140041d09  lea     rax, [rbp+0D0h+var_A0]
0x140041d0d  mov     [rsp+1D0h+ObjectAttributes.ObjectName], rax
0x140041d12  mov     [rbp+0D0h+ObjectAttributes.SecurityDescriptor], rbx
0x140041d16  mov     [rbp+0D0h+ObjectAttributes.SecurityQualityOfService], r12
0x140041d1a  mov     [rsi], r12
0x140041d1d  mov     [rsp+1D0h+var_180], r13d
0x140041d22  xorps   xmm0, xmm0
0x140041d25  xor     eax, eax
0x140041d27  movups  xmmword ptr [rbp+0D0h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x140041d2b  mov     [rbp+0D0h+pListOfExplicitEntries.Trustee.pMultipleTrustee], rax
0x140041d2f  lea     edx, [rax+12h]; int
0x140041d32  lea     rcx, [rbp+0D0h+pListOfExplicitEntries]; this
0x140041d36  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x140041d3b  nop
0x140041d3c  mov     rcx, rsi
0x140041d3f  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x140041d44  lea     r8, [rsp+1D0h+ObjectAttributes]; ObjectAttributes
0x140041d49  mov     edx, 0F000Fh; DesiredAccess
0x140041d4e  mov     rcx, rax; DirectoryHandle
0x140041d51  call    cs:__imp_NtCreateDirectoryObject
0x140041d58  nop     dword ptr [rax+rax+00h]
0x140041d5d  mov     rcx, [rbp+0D8h]; this
0x140041d64  test    eax, eax
0x140041d66  js      loc_140041F60
0x140041d6c  lea     rcx, [rbp+0D0h+pListOfExplicitEntries]; this
0x140041d70  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x140041d75  nop
0x140041d76  test    rdi, rdi
0x140041d79  jz      short loc_140041D8B
0x140041d7b  mov     rcx, rdi; hMem
0x140041d7e  call    cs:__imp_LocalFree
0x140041d85  nop     dword ptr [rax+rax+00h]
0x140041d8a  nop
0x140041d8b  test    r14, r14
0x140041d8e  jz      short loc_140041D9F
0x140041d90  mov     rcx, r14; hMem
0x140041d93  call    cs:__imp_LocalFree
0x140041d9a  nop     dword ptr [rax+rax+00h]
0x140041d9f  lea     rcx, [rbp+0D0h+var_60]; this
0x140041da3  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140041da8  lea     rcx, [rbp+0D0h+var_80]; this
0x140041dac  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140041db1  nop
0x140041db2  test    rbx, rbx
0x140041db5  jz      short loc_140041DC7
0x140041db7  mov     rcx, rbx; hMem
0x140041dba  call    cs:__imp_LocalFree
0x140041dc1  nop     dword ptr [rax+rax+00h]
0x140041dc6  nop
0x140041dc7  mov     rdx, [rbp+0D0h+var_118]
0x140041dcb  mov     ebx, 1000h
0x140041dd0  cmp     rdx, 7
0x140041dd4  jbe     short loc_140041DFA
0x140041dd6  lea     rdx, ds:2[rdx*2]; struct std::nothrow_t *
0x140041dde  mov     [rsp+1D0h+NewAcl], rdx
0x140041de3  mov     rcx, [rbp+0D0h+var_130]; void *
0x140041de7  mov     [rsp+1D0h+var_1A0], rcx
0x140041dec  cmp     rdx, rbx
0x140041def  jnb     loc_140041F75
0x140041df5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140041dfa  mov     [rbp+0D0h+var_120], r12
0x140041dfe  mov     [rbp+0D0h+var_118], 7
0x140041e06  mov     word ptr [rbp+0D0h+var_130], r12w
0x140041e0b  mov     rdx, [rbp+0D0h+var_A8]
0x140041e0f  cmp     rdx, 7
0x140041e13  jbe     short loc_140041E39
0x140041e15  lea     rdx, ds:2[rdx*2]; struct std::nothrow_t *
0x140041e1d  mov     [rsp+1D0h+var_1A0], rdx
0x140041e22  mov     rcx, [rbp+0D0h+var_C0]; void *
0x140041e26  mov     [rsp+1D0h+NewAcl], rcx
0x140041e2b  cmp     rdx, rbx
0x140041e2e  jnb     loc_140041F93
0x140041e34  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140041e39  mov     rax, rsi
0x140041e3c  mov     rcx, [rbp+0D0h+var_40]
0x140041e43  xor     rcx, rsp; StackCookie
0x140041e46  call    __security_check_cookie
0x140041e4b  mov     rbx, [rsp+1D0h+arg_18]
0x140041e53  add     rsp, 1A0h
0x140041e5a  pop     r15
0x140041e5c  pop     r14
0x140041e5e  pop     r13
0x140041e60  pop     r12
0x140041e62  pop     rdi
0x140041e63  pop     rsi
0x140041e64  pop     rbp
0x140041e65  retn
0x140041e67  xor     edx, edx; Val
0x140041e69  lea     r8d, [rdx+50h]; Size
0x140041e6d  lea     rcx, [rbp+0D0h+pListOfExplicitEntries]; void *
0x140041e71  call    memset_0
0x140041e76  xor     edx, edx; pSourceSid
0x140041e78  lea     rcx, [rbp+0D0h+pListOfExplicitEntries]; this
0x140041e7c  call    ??0VmSid@Vml@@QEAA@PEAX@Z; Vml::VmSid::VmSid(void *)
0x140041e81  nop
0x140041e82  cmp     qword ptr [rbx+18h], 7
0x140041e87  jbe     short loc_140041EF1
0x140041e89  mov     rcx, [rbx]; StringSid
0x140041e8c  lea     rdx, [rbp+0D0h+pListOfExplicitEntries]; Sid
0x140041e90  call    cs:__imp_ConvertStringSidToSidW
0x140041e97  nop     dword ptr [rax+rax+00h]
0x140041e9c  mov     [rsp+1D0h+var_1B0], r13d; enum _ACCESS_MODE
0x140041ea1  xor     r9d, r9d; unsigned int
0x140041ea4  mov     r8d, 80000000h; unsigned int
0x140041eaa  mov     rdx, qword ptr [rbp+0D0h+pListOfExplicitEntries.grfAccessPermissions]; void *
0x140041eae  lea     rcx, [rsp+1D0h+var_190]; this
0x140041eb3  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x140041eb8  mov     [rsp+1D0h+var_1B0], r13d; enum _ACCESS_MODE
0x140041ebd  mov     r9d, r13d; unsigned int
0x140041ec0  mov     r8d, 10000000h; unsigned int
0x140041ec6  mov     rdx, qword ptr [rbp+0D0h+pListOfExplicitEntries.grfAccessPermissions]; void *
0x140041eca  lea     rcx, [rsp+1D0h+var_190]; this
0x140041ecf  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x140041ed4  nop
0x140041ed5  lea     rcx, [rbp+0D0h+pListOfExplicitEntries]; this
0x140041ed9  call    ??1VmSid@Vml@@QEAA@XZ; Vml::VmSid::~VmSid(void)
0x140041ede  add     rbx, 20h ; ' '
0x140041ee2  cmp     rbx, r15
0x140041ee5  jnz     short loc_140041E67
0x140041ee7  mov     rdi, qword ptr [rsp+1D0h+var_190]
0x140041eec  jmp     loc_140041C90
0x140041ef1  mov     rcx, rbx
0x140041ef4  jmp     short loc_140041E8C
0x140041ef6  mov     al, r13b
0x140041ef9  jmp     loc_140041B42
0x140041efe  mov     r9d, 80070057h; char *
0x140041f04  lea     r8, aOnecoreVmCompu_124; "onecore\\vm\\compute\\management\\orche"...
0x140041f0b  mov     edx, 69h ; 'i'; void *
0x140041f10  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140041f16  mov     rdx, rbx; pSourceSid
0x140041f19  lea     rcx, [rbp+0D0h+pOwner]; this
0x140041f1d  call    ?Assign@VmSid@Vml@@QEAAXPEAX@Z; Vml::VmSid::Assign(void *)
0x140041f22  jmp     loc_140041C10
0x140041f27  mov     r9d, eax; char *
0x140041f2a  lea     r8, aOnecoreVmCommo_54; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x140041f31  mov     edx, 1713h; void *
0x140041f36  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140041f3c  lea     r8, aOnecoreVmCommo_54; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x140041f43  mov     edx, 0D50h; void *
0x140041f48  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140041f4e  lea     r8, aOnecoreVmCommo_54; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x140041f55  mov     edx, 0DD6h; void *
0x140041f5a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140041f60  mov     r9d, eax; char *
0x140041f63  lea     r8, aOnecoreVmCompu_124; "onecore\\vm\\compute\\management\\orche"...
0x140041f6a  mov     edx, 95h; void *
0x140041f6f  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x140041f75  lea     rdx, [rsp+1D0h+NewAcl]; unsigned __int64 *
0x140041f7a  lea     rcx, [rsp+1D0h+var_1A0]; void **
0x140041f7f  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x140041f84  mov     rdx, [rsp+1D0h+NewAcl]
0x140041f89  mov     rcx, [rsp+1D0h+var_1A0]
0x140041f8e  jmp     loc_140041DF5
0x140041f93  lea     rdx, [rsp+1D0h+var_1A0]; unsigned __int64 *
0x140041f98  lea     rcx, [rsp+1D0h+NewAcl]; void **
0x140041f9d  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x140041fa2  mov     rdx, [rsp+1D0h+var_1A0]
0x140041fa7  mov     rcx, [rsp+1D0h+NewAcl]
0x140041fac  jmp     loc_140041E34
```
