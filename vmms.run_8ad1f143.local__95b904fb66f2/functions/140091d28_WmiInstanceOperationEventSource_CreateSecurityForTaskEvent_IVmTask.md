# WmiInstanceOperationEventSource::CreateSecurityForTaskEvent(IVmTask *)

- ea: `0x140091d28`
- end: `0x1400920d1`
- name: `?CreateSecurityForTaskEvent@WmiInstanceOperationEventSource@@AEAAPEAU_SECURITY_DESCRIPTOR@@PEAUIVmTask@@@Z`
- size: `937`
- prototype: `struct _SECURITY_DESCRIPTOR *__fastcall(WmiInstanceOperationEventSource *__hidden this, struct IVmTask *)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x14008fee0`
- `0x1406e2840`

## callees

- `0x140091d28`
- `0x1400920d8`
- `0x140092260`
- `0x1400923e8`
- `0x140092bb8`
- `0x140092d3c`
- `0x140092ec0`
- `0x1400acf04`
- `0x1400eaaac`
- `0x14011640c`
- `0x14017902c`
- `0x140188e18`
- `0x140237a2c`
- `0x1404828e0`
- `0x1404835a0`
- `0x1406e21f8`
- `0x1408aa010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14009207a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14009207a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140091e16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140091e93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140091f8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14009208f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140091e16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140091e93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140091f8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14009208f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x140091fc3`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x140091fc3`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x140092004`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x140092004`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x140092043`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x140092043`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x140091dda`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x140091e57`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x140091f4f`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x140091dda`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x140091e57`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x140091f4f`

## string_xrefs

- `0x140091df4`: `onecore\vm\common\vml\VmSecurity.h`
- `0x140091e71`: `onecore\vm\common\vml\VmSecurity.h`
- `0x140091f69`: `onecore\vm\common\vml\VmSecurity.h`
- `0x140091fda`: `onecore\vm\common\vml\VmSecurity.h`
- `0x14009201b`: `onecore\vm\common\vml\VmSecurity.h`
- `0x14009205a`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
struct _SECURITY_DESCRIPTOR *__fastcall WmiInstanceOperationEventSource::CreateSecurityForTaskEvent(
        WmiInstanceOperationEventSource *this,
        struct IVmTask *a2)
{
  unsigned int v3; // edx
  PACL v4; // rbx
  DWORD v5; // eax
  struct _ACL *v6; // rdi
  DWORD v7; // eax
  AuthorizationUtilities::Details *v8; // rcx
  struct _ACL *v9; // rbx
  void **v10; // rax
  int v11; // eax
  DWORD v12; // eax
  struct _ACL *v13; // rdi
  PSID v14; // rbx
  const char *v15; // r9
  PSID v16; // rbx
  const char *v17; // r9
  const char *v18; // r9
  enum _ACCESS_MODE v20; // [rsp+20h] [rbp-E0h]
  PSID pOwner[10]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v22[10]; // [rsp+80h] [rbp-80h] BYREF
  PACL NewAcl[2]; // [rsp+D0h] [rbp-30h] BYREF
  PACL OldAcl[2]; // [rsp+E0h] [rbp-20h] BYREF
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+F0h] [rbp-10h] BYREF
  LPVOID pv[2]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  memset_0(pOwner, 0, sizeof(pOwner));
  Vml::Sids::Administrators(pOwner);
  memset_0(v22, 0, sizeof(v22));
  Vml::Sids::HyperVAdministrators(v22);
  OldAcl[1] = 0;
  OldAcl[0] = 0;
  Vml::VmAcl::Initialize((Vml::VmAcl *)OldAcl, v3);
  memset(&pListOfExplicitEntries.grfInheritance, 0, 32);
  pListOfExplicitEntries.grfAccessPermissions = 64;
  pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pOwner[0];
  NewAcl[0] = 0;
  v4 = OldAcl[0];
  v5 = SetEntriesInAclW(1u, &pListOfExplicitEntries, OldAcl[0], NewAcl);
  if ( v5 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1713,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      (const char *)v5,
      v20);
  v6 = NewAcl[0];
  OldAcl[0] = NewAcl[0];
  if ( v4 )
    LocalFree(v4);
  memset(&pListOfExplicitEntries.grfInheritance, 0, 32);
  pListOfExplicitEntries.grfAccessPermissions = 64;
  pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)v22[0];
  NewAcl[0] = 0;
  v7 = SetEntriesInAclW(1u, &pListOfExplicitEntries, v6, NewAcl);
  v8 = retaddr;
  if ( v7 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1713,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      (const char *)v7,
      v20);
  v9 = NewAcl[0];
  OldAcl[0] = NewAcl[0];
  if ( v6 )
    LocalFree(v6);
  if ( (AuthorizationUtilities::Details::GetAccessCheckFlags(v8) & 1) != 0 )
  {
    v10 = (void **)Vml::Sids::AllApplicationPackages(&pListOfExplicitEntries);
    Vml::VmAcl::UpdateAccess((Vml::VmAcl *)OldAcl, *v10, 0x40u, 0, GRANT_ACCESS);
    Vml::VmSid::~VmSid((Vml::VmSid *)&pListOfExplicitEntries);
    v9 = OldAcl[0];
  }
  pv[1] = 0;
  pv[0] = 0;
  v11 = (*(__int64 (__fastcall **)(struct IVmTask *, LPVOID *))(*(_QWORD *)a2 + 176LL))(a2, pv);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4DD,
      (unsigned int)"onecore\\vm\\vmms\\wmi\\wmiinstanceoperationeventsource.cpp",
      (const char *)(unsigned int)v11,
      v20);
  memset(&pListOfExplicitEntries.grfInheritance, 0, 32);
  pListOfExplicitEntries.grfAccessPermissions = 64;
  pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pv[0];
  NewAcl[0] = 0;
  v12 = SetEntriesInAclW(1u, &pListOfExplicitEntries, v9, NewAcl);
  if ( v12 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1713,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      (const char *)v12,
      v20);
  v13 = NewAcl[0];
  OldAcl[0] = NewAcl[0];
  if ( v9 )
    LocalFree(v9);
  NewAcl[1] = 0;
  NewAcl[0] = 0;
  Vml::VmSecurityDescriptor::Initialize((Vml::VmSecurityDescriptor *)NewAcl);
  v14 = pOwner[0];
  Vml::VmSecurityDescriptor::MakeAbsolute((Vml::VmSecurityDescriptor *)NewAcl);
  if ( !SetSecurityDescriptorOwner(NewAcl[0], v14, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xD50,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v15);
  v16 = pOwner[0];
  Vml::VmSecurityDescriptor::MakeAbsolute((Vml::VmSecurityDescriptor *)NewAcl);
  if ( !SetSecurityDescriptorGroup(NewAcl[0], v16, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xD91,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v17);
  Vml::VmSecurityDescriptor::MakeAbsolute((Vml::VmSecurityDescriptor *)NewAcl);
  if ( !SetSecurityDescriptorDacl(NewAcl[0], 1, v13, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xDD6,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v18);
  Vml::VmSecurityDescriptor::MakeSelfRelative((Vml::VmSecurityDescriptor *)NewAcl);
  CoTaskMemFree(pv[0]);
  if ( v13 )
    LocalFree(v13);
  Vml::VmSid::~VmSid((Vml::VmSid *)v22);
  Vml::VmSid::~VmSid((Vml::VmSid *)pOwner);
  return (struct _SECURITY_DESCRIPTOR *)NewAcl[0];
}

```

## disassembly

```asm
0x140091d28  push    rbp
0x140091d2a  push    rbx
0x140091d2b  push    rsi
0x140091d2c  push    rdi
0x140091d2d  push    r14
0x140091d2f  push    r15
0x140091d31  lea     rbp, [rsp-68h]
0x140091d36  sub     rsp, 168h
0x140091d3d  mov     rax, cs:__security_cookie
0x140091d44  xor     rax, rsp
0x140091d47  mov     [rbp+90h+var_40], rax
0x140091d4b  mov     rsi, rdx
0x140091d4e  mov     ebx, 50h ; 'P'
0x140091d53  mov     r8d, ebx; Size
0x140091d56  xor     edx, edx; Val
0x140091d58  lea     rcx, [rsp+190h+pOwner]; void *
0x140091d5d  call    memset_0
0x140091d62  lea     rcx, [rsp+190h+pOwner]
0x140091d67  call    ?Administrators@Sids@Vml@@YA?AVVmSid@2@XZ; Vml::Sids::Administrators(void)
0x140091d6c  nop
0x140091d6d  mov     r8d, ebx; Size
0x140091d70  xor     edx, edx; Val
0x140091d72  lea     rcx, [rbp+90h+var_110]; void *
0x140091d76  call    memset_0
0x140091d7b  lea     rcx, [rbp+90h+var_110]
0x140091d7f  call    ?HyperVAdministrators@Sids@Vml@@YA?AVVmSid@2@XZ; Vml::Sids::HyperVAdministrators(void)
0x140091d84  nop
0x140091d85  xorps   xmm0, xmm0
0x140091d88  movups  xmmword ptr [rbp+90h+OldAcl], xmm0
0x140091d8c  xor     r14d, r14d
0x140091d8f  mov     [rbp+90h+OldAcl], r14
0x140091d93  lea     rcx, [rbp+90h+OldAcl]; this
0x140091d97  call    ?Initialize@VmAcl@Vml@@QEAAXK@Z; Vml::VmAcl::Initialize(ulong)
0x140091d9c  mov     qword ptr [rbp+90h+pListOfExplicitEntries.grfInheritance], r14
0x140091da0  mov     qword ptr [rbp+90h+pListOfExplicitEntries.Trustee.TrusteeType], r14
0x140091da4  mov     [rbp+90h+pListOfExplicitEntries.grfAccessPermissions], 40h ; '@'
0x140091dab  lea     r15d, [rbx-4Fh]
0x140091daf  mov     [rbp+90h+pListOfExplicitEntries.grfAccessMode], r15d
0x140091db3  mov     [rbp+90h+pListOfExplicitEntries.Trustee.pMultipleTrustee], r14
0x140091db7  mov     qword ptr [rbp+90h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], r14
0x140091dbb  mov     rax, [rsp+190h+pOwner]
0x140091dc0  mov     [rbp+90h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x140091dc4  mov     [rbp+90h+NewAcl], r14
0x140091dc8  lea     r9, [rbp+90h+NewAcl]; NewAcl
0x140091dcc  mov     rbx, [rbp+90h+OldAcl]
0x140091dd0  mov     r8, rbx; OldAcl
0x140091dd3  lea     rdx, [rbp+90h+pListOfExplicitEntries]; pListOfExplicitEntries
0x140091dd7  mov     ecx, r15d; cCountOfExplicitEntries
0x140091dda  call    cs:__imp_SetEntriesInAclW
0x140091de1  nop     dword ptr [rax+rax+00h]
0x140091de6  mov     rcx, [rbp+98h]; this
0x140091ded  test    eax, eax
0x140091def  jz      short loc_140091E06
0x140091df1  mov     r9d, eax; char *
0x140091df4  lea     r8, aOnecoreVmCommo_107; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x140091dfb  mov     edx, 1713h; void *
0x140091e00  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140091e06  mov     rdi, [rbp+90h+NewAcl]
0x140091e0a  mov     [rbp+90h+OldAcl], rdi
0x140091e0e  test    rbx, rbx
0x140091e11  jz      short loc_140091E22
0x140091e13  mov     rcx, rbx; hMem
0x140091e16  call    cs:__imp_LocalFree
0x140091e1d  nop     dword ptr [rax+rax+00h]
0x140091e22  mov     qword ptr [rbp+90h+pListOfExplicitEntries.grfInheritance], r14
0x140091e26  mov     qword ptr [rbp+90h+pListOfExplicitEntries.Trustee.TrusteeType], r14
0x140091e2a  mov     [rbp+90h+pListOfExplicitEntries.grfAccessPermissions], 40h ; '@'
0x140091e31  mov     [rbp+90h+pListOfExplicitEntries.grfAccessMode], r15d
0x140091e35  mov     [rbp+90h+pListOfExplicitEntries.Trustee.pMultipleTrustee], r14
0x140091e39  mov     qword ptr [rbp+90h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], r14
0x140091e3d  mov     rax, [rbp+90h+var_110]
0x140091e41  mov     [rbp+90h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x140091e45  mov     [rbp+90h+NewAcl], r14
0x140091e49  lea     r9, [rbp+90h+NewAcl]; NewAcl
0x140091e4d  mov     r8, rdi; OldAcl
0x140091e50  lea     rdx, [rbp+90h+pListOfExplicitEntries]; pListOfExplicitEntries
0x140091e54  mov     ecx, r15d; cCountOfExplicitEntries
0x140091e57  call    cs:__imp_SetEntriesInAclW
0x140091e5e  nop     dword ptr [rax+rax+00h]
0x140091e63  mov     rcx, [rbp+98h]; this
0x140091e6a  test    eax, eax
0x140091e6c  jz      short loc_140091E83
0x140091e6e  mov     r9d, eax; char *
0x140091e71  lea     r8, aOnecoreVmCommo_107; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x140091e78  mov     edx, 1713h; void *
0x140091e7d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140091e83  mov     rbx, [rbp+90h+NewAcl]
0x140091e87  mov     [rbp+90h+OldAcl], rbx
0x140091e8b  test    rdi, rdi
0x140091e8e  jz      short loc_140091E9F
0x140091e90  mov     rcx, rdi; hMem
0x140091e93  call    cs:__imp_LocalFree
0x140091e9a  nop     dword ptr [rax+rax+00h]
0x140091e9f  call    ?GetAccessCheckFlags@Details@AuthorizationUtilities@@YAKXZ; AuthorizationUtilities::Details::GetAccessCheckFlags(void)
0x140091ea4  test    r15b, al
0x140091ea7  jz      short loc_140091ED9
0x140091ea9  lea     rcx, [rbp+90h+pListOfExplicitEntries]
0x140091ead  call    ?AllApplicationPackages@Sids@Vml@@YA?AVVmSid@2@XZ; Vml::Sids::AllApplicationPackages(void)
0x140091eb2  nop
0x140091eb3  mov     [rsp+190h+var_170], r15d; unsigned int
0x140091eb8  xor     r9d, r9d; unsigned int
0x140091ebb  lea     r8d, [r9+40h]; unsigned int
0x140091ebf  mov     rdx, [rax]; void *
0x140091ec2  lea     rcx, [rbp+90h+OldAcl]; this
0x140091ec6  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x140091ecb  nop
0x140091ecc  lea     rcx, [rbp+90h+pListOfExplicitEntries]; this
0x140091ed0  call    ??1VmSid@Vml@@QEAA@XZ; Vml::VmSid::~VmSid(void)
0x140091ed5  mov     rbx, [rbp+90h+OldAcl]
0x140091ed9  xorps   xmm0, xmm0
0x140091edc  movups  xmmword ptr [rbp+90h+pv], xmm0
0x140091ee0  mov     [rbp+90h+pv], r14
0x140091ee4  mov     rax, [rsi]
0x140091ee7  lea     rdx, [rbp+90h+pv]
0x140091eeb  mov     rcx, rsi
0x140091eee  mov     rax, [rax+0B0h]
0x140091ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140091efa  mov     rcx, [rbp+98h]; this
0x140091f01  test    eax, eax
0x140091f03  jns     short loc_140091F1A
0x140091f05  mov     r9d, eax; char *
0x140091f08  lea     r8, aOnecoreVmVmmsW_133; "onecore\\vm\\vmms\\wmi\\wmiinstanceoper"...
0x140091f0f  mov     edx, 4DDh; void *
0x140091f14  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140091f1a  mov     qword ptr [rbp+90h+pListOfExplicitEntries.grfInheritance], r14
0x140091f1e  mov     qword ptr [rbp+90h+pListOfExplicitEntries.Trustee.TrusteeType], r14
0x140091f22  mov     [rbp+90h+pListOfExplicitEntries.grfAccessPermissions], 40h ; '@'
0x140091f29  mov     [rbp+90h+pListOfExplicitEntries.grfAccessMode], r15d
0x140091f2d  mov     [rbp+90h+pListOfExplicitEntries.Trustee.pMultipleTrustee], r14
0x140091f31  mov     qword ptr [rbp+90h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], r14
0x140091f35  mov     rax, [rbp+90h+pv]
0x140091f39  mov     [rbp+90h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x140091f3d  mov     [rbp+90h+NewAcl], r14
0x140091f41  lea     r9, [rbp+90h+NewAcl]; NewAcl
0x140091f45  mov     r8, rbx; OldAcl
0x140091f48  lea     rdx, [rbp+90h+pListOfExplicitEntries]; pListOfExplicitEntries
0x140091f4c  mov     ecx, r15d; cCountOfExplicitEntries
0x140091f4f  call    cs:__imp_SetEntriesInAclW
0x140091f56  nop     dword ptr [rax+rax+00h]
0x140091f5b  mov     rcx, [rbp+98h]; this
0x140091f62  test    eax, eax
0x140091f64  jz      short loc_140091F7B
0x140091f66  mov     r9d, eax; char *
0x140091f69  lea     r8, aOnecoreVmCommo_107; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x140091f70  mov     edx, 1713h; void *
0x140091f75  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140091f7b  mov     rdi, [rbp+90h+NewAcl]
0x140091f7f  mov     [rbp+90h+OldAcl], rdi
0x140091f83  test    rbx, rbx
0x140091f86  jz      short loc_140091F97
0x140091f88  mov     rcx, rbx; hMem
0x140091f8b  call    cs:__imp_LocalFree
0x140091f92  nop     dword ptr [rax+rax+00h]
0x140091f97  xorps   xmm0, xmm0
0x140091f9a  movups  xmmword ptr [rbp+90h+NewAcl], xmm0
0x140091f9e  mov     [rbp+90h+NewAcl], r14
0x140091fa2  lea     rcx, [rbp+90h+NewAcl]; this
0x140091fa6  call    ?Initialize@VmSecurityDescriptor@Vml@@QEAAXXZ; Vml::VmSecurityDescriptor::Initialize(void)
0x140091fab  mov     rbx, [rsp+190h+pOwner]
0x140091fb0  lea     rcx, [rbp+90h+NewAcl]; this
0x140091fb4  call    ?MakeAbsolute@VmSecurityDescriptor@Vml@@QEAAXXZ; Vml::VmSecurityDescriptor::MakeAbsolute(void)
0x140091fb9  xor     r8d, r8d; bOwnerDefaulted
0x140091fbc  mov     rdx, rbx; pOwner
0x140091fbf  mov     rcx, [rbp+90h+NewAcl]; pSecurityDescriptor
0x140091fc3  call    cs:__imp_SetSecurityDescriptorOwner
0x140091fca  nop     dword ptr [rax+rax+00h]
0x140091fcf  mov     rcx, [rbp+98h]; this
0x140091fd6  test    eax, eax
0x140091fd8  jnz     short loc_140091FEC
0x140091fda  lea     r8, aOnecoreVmCommo_107; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x140091fe1  mov     edx, 0D50h; void *
0x140091fe6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140091fec  mov     rbx, [rsp+190h+pOwner]
0x140091ff1  lea     rcx, [rbp+90h+NewAcl]; this
0x140091ff5  call    ?MakeAbsolute@VmSecurityDescriptor@Vml@@QEAAXXZ; Vml::VmSecurityDescriptor::MakeAbsolute(void)
0x140091ffa  xor     r8d, r8d; bGroupDefaulted
0x140091ffd  mov     rdx, rbx; pGroup
0x140092000  mov     rcx, [rbp+90h+NewAcl]; pSecurityDescriptor
0x140092004  call    cs:__imp_SetSecurityDescriptorGroup
0x14009200b  nop     dword ptr [rax+rax+00h]
0x140092010  mov     rcx, [rbp+98h]; this
0x140092017  test    eax, eax
0x140092019  jnz     short loc_14009202D
0x14009201b  lea     r8, aOnecoreVmCommo_107; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x140092022  mov     edx, 0D91h; void *
0x140092027  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14009202d  lea     rcx, [rbp+90h+NewAcl]; this
0x140092031  call    ?MakeAbsolute@VmSecurityDescriptor@Vml@@QEAAXXZ; Vml::VmSecurityDescriptor::MakeAbsolute(void)
0x140092036  xor     r9d, r9d; bDaclDefaulted
0x140092039  mov     r8, rdi; pDacl
0x14009203c  mov     edx, r15d; bDaclPresent
0x14009203f  mov     rcx, [rbp+90h+NewAcl]; pSecurityDescriptor
0x140092043  call    cs:__imp_SetSecurityDescriptorDacl
0x14009204a  nop     dword ptr [rax+rax+00h]
0x14009204f  mov     rcx, [rbp+98h]; this
0x140092056  test    eax, eax
0x140092058  jnz     short loc_14009206C
0x14009205a  lea     r8, aOnecoreVmCommo_107; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x140092061  mov     edx, 0DD6h; void *
0x140092066  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14009206c  lea     rcx, [rbp+90h+NewAcl]; this
0x140092070  call    ?MakeSelfRelative@VmSecurityDescriptor@Vml@@QEAAXXZ; Vml::VmSecurityDescriptor::MakeSelfRelative(void)
0x140092075  nop
0x140092076  mov     rcx, [rbp+90h+pv]; pv
0x14009207a  call    cs:__imp_CoTaskMemFree
0x140092081  nop     dword ptr [rax+rax+00h]
0x140092086  nop
0x140092087  test    rdi, rdi
0x14009208a  jz      short loc_14009209C
0x14009208c  mov     rcx, rdi; hMem
0x14009208f  call    cs:__imp_LocalFree
0x140092096  nop     dword ptr [rax+rax+00h]
0x14009209b  nop
0x14009209c  lea     rcx, [rbp+90h+var_110]; this
0x1400920a0  call    ??1VmSid@Vml@@QEAA@XZ; Vml::VmSid::~VmSid(void)
0x1400920a5  nop
0x1400920a6  lea     rcx, [rsp+190h+pOwner]; this
0x1400920ab  call    ??1VmSid@Vml@@QEAA@XZ; Vml::VmSid::~VmSid(void)
0x1400920b0  mov     rax, [rbp+90h+NewAcl]
0x1400920b4  mov     rcx, [rbp+90h+var_40]
0x1400920b8  xor     rcx, rsp; StackCookie
0x1400920bb  call    __security_check_cookie
0x1400920c0  add     rsp, 168h
0x1400920c7  pop     r15
0x1400920c9  pop     r14
0x1400920cb  pop     rdi
0x1400920cc  pop     rsi
0x1400920cd  pop     rbx
0x1400920ce  pop     rbp
0x1400920cf  retn
```
