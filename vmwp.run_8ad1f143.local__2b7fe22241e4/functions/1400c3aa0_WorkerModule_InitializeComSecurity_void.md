# WorkerModule::InitializeComSecurity(void)

- ea: `0x1400c3aa0`
- end: `0x1400c3cf8`
- name: `?InitializeComSecurity@WorkerModule@@QEAAXXZ`
- size: `600`
- prototype: `void __fastcall(WorkerModule *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400c3740`

## callees

- `0x14005b648`
- `0x14006af58`
- `0x1400c3aa0`
- `0x1400c3e4c`
- `0x1400c3ed8`
- `0x1400c3f64`
- `0x1400c40ec`
- `0x1400c41bc`
- `0x1400c42b0`
- `0x1400c4378`
- `0x1400c43b4`
- `0x1400c5c8c`
- `0x140132960`
- `0x14013361c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400c3b4d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400c3b4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400c3b35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400c3b35`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1400c3c71`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1400c3c71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400c3ba7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400c3ca5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400c3cce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400c3ba7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400c3ca5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400c3cce`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1400c3c15`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1400c3c15`

## string_xrefs

- `0x1400c3b61`: `onecore\vm\common\vml\VmSecurity.h`
- `0x1400c3c29`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall WorkerModule::InitializeComSecurity(WorkerModule *this, __int64 a2, unsigned int a3)
{
  HANDLE CurrentProcess; // rax
  enum _TOKEN_INFORMATION_CLASS v4; // edx
  const char *v5; // r9
  struct _ACL *Information; // rbx
  const struct _ACL *Dacl; // rax
  const struct _ACL *v8; // rax
  unsigned int v9; // r8d
  unsigned int v10; // r9d
  PSECURITY_DESCRIPTOR v11; // rbx
  const char *v12; // r9
  HRESULT v13; // eax
  enum _ACCESS_MODE dwAuthnLevel; // [rsp+20h] [rbp-69h]
  DWORD dwAuthnLevela; // [rsp+20h] [rbp-69h]
  PSECURITY_DESCRIPTOR pSecurityDescriptor[2]; // [rsp+50h] [rbp-39h] BYREF
  PACL pDacl[2]; // [rsp+60h] [rbp-29h] BYREF
  void *TokenHandle[2]; // [rsp+70h] [rbp-19h] BYREF
  void *v19; // [rsp+80h] [rbp-9h] BYREF
  int v20; // [rsp+88h] [rbp-1h]
  __int128 v21; // [rsp+90h] [rbp+7h]
  __m128i si128; // [rsp+A0h] [rbp+17h]
  __int128 v23; // [rsp+B0h] [rbp+27h]
  __m128i v24; // [rsp+C0h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  *(_OWORD *)pSecurityDescriptor = 0;
  Vml::VmSecurityDescriptor::Assign(
    (Vml::VmSecurityDescriptor *)pSecurityDescriptor,
    L"O:BAG:BAD:(A;OICI;0x3;;;SY)(A;OICI;0x3;;;BA)(A;OICI;0x3;;;HA)",
    a3);
  Vml::VmSecurityDescriptor::MakeAbsolute((Vml::VmSecurityDescriptor *)pSecurityDescriptor);
  TokenHandle[0] = 0;
  memset_0(&v19, 0, 0x50u);
  v19 = 0;
  v20 = 7;
  v21 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v21) = 0;
  v23 = 0;
  v24 = si128;
  LOWORD(v23) = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, TokenHandle) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CE7,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v5);
  *(_OWORD *)pDacl = 0;
  Information = (struct _ACL *)Vml::VmAccessToken::_GetInformation((Vml::VmAccessToken *)TokenHandle, v4);
  pDacl[0] = Information;
  Vml::VmSid::Assign((Vml::VmSid *)&v19, *(void **)Information);
  if ( Information )
    LocalFree(Information);
  *(_OWORD *)pDacl = 0;
  Dacl = Vml::VmSecurityDescriptor::GetDacl((Vml::VmSecurityDescriptor *)pSecurityDescriptor);
  pDacl[0] = 0;
  Vml::VmAcl::Assign((Vml::VmAcl *)pDacl, Dacl);
  v8 = Vml::VmSecurityDescriptor::GetDacl((Vml::VmSecurityDescriptor *)pSecurityDescriptor);
  Vml::VmAcl::Assign((Vml::VmAcl *)pDacl, v8);
  Vml::VmAcl::UpdateAccess((Vml::VmAcl *)pDacl, v19, v9, v10, dwAuthnLevel);
  Vml::VmSecurityDescriptor::MakeAbsolute((Vml::VmSecurityDescriptor *)pSecurityDescriptor);
  v11 = pSecurityDescriptor[0];
  if ( !SetSecurityDescriptorDacl(pSecurityDescriptor[0], 1, pDacl[0], 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xDD6,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v12);
  v13 = CoInitializeSecurity(v11, -1, 0, 0, 5u, 2u, 0, 0x5002u, 0);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x477,
      (unsigned int)"onecore\\vm\\worker\\wpexe\\workermodule.cpp",
      (const char *)(unsigned int)v13,
      dwAuthnLevela);
  if ( pDacl[0] )
    LocalFree(pDacl[0]);
  Vml::VmSid::~VmSid((Vml::VmSid *)&v19);
  Vml::VmAccessToken::~VmAccessToken((Vml::VmAccessToken *)TokenHandle);
  if ( v11 )
    LocalFree(v11);
}

```

## disassembly

```asm
0x1400c3aa0  mov     [rsp-8+arg_0], rbx
0x1400c3aa5  push    rbp
0x1400c3aa6  lea     rbp, [rsp-57h]
0x1400c3aab  sub     rsp, 0E0h
0x1400c3ab2  mov     rax, cs:__security_cookie
0x1400c3ab9  xor     rax, rsp
0x1400c3abc  mov     [rbp+57h+var_10], rax
0x1400c3ac0  xorps   xmm0, xmm0
0x1400c3ac3  movups  xmmword ptr [rbp+57h+pSecurityDescriptor], xmm0
0x1400c3ac7  mov     [rbp+57h+pSecurityDescriptor], 0
0x1400c3acf  lea     rdx, aOBagBadAOici0x; "O:BAG:BAD:(A;OICI;0x3;;;SY)(A;OICI;0x3;"...
0x1400c3ad6  lea     rcx, [rbp+57h+pSecurityDescriptor]; this
0x1400c3ada  call    ?Assign@VmSecurityDescriptor@Vml@@QEAAXPEBGK@Z; Vml::VmSecurityDescriptor::Assign(ushort const *,ulong)
0x1400c3adf  lea     rcx, [rbp+57h+pSecurityDescriptor]; this
0x1400c3ae3  call    ?MakeAbsolute@VmSecurityDescriptor@Vml@@QEAAXXZ; Vml::VmSecurityDescriptor::MakeAbsolute(void)
0x1400c3ae8  mov     [rbp+57h+TokenHandle], 0
0x1400c3af0  xor     edx, edx; Val
0x1400c3af2  lea     r8d, [rdx+50h]; Size
0x1400c3af6  lea     rcx, [rbp+57h+var_60]; void *
0x1400c3afa  call    memset_0
0x1400c3aff  mov     [rbp+57h+var_60], 0
0x1400c3b07  mov     [rbp+57h+var_58], 7
0x1400c3b0e  xorps   xmm0, xmm0
0x1400c3b11  movups  [rbp+57h+var_50], xmm0
0x1400c3b15  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1400c3b1d  movdqa  [rbp+57h+var_40], xmm1
0x1400c3b22  xor     eax, eax
0x1400c3b24  mov     word ptr [rbp+57h+var_50], ax
0x1400c3b28  movups  [rbp+57h+var_30], xmm0
0x1400c3b2c  movdqa  [rbp+57h+var_20], xmm1
0x1400c3b31  mov     word ptr [rbp+57h+var_30], ax
0x1400c3b35  call    cs:__imp_GetCurrentProcess
0x1400c3b3c  nop     dword ptr [rax+rax+00h]
0x1400c3b41  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1400c3b45  mov     edx, 8; DesiredAccess
0x1400c3b4a  mov     rcx, rax; ProcessHandle
0x1400c3b4d  call    cs:__imp_OpenProcessToken
0x1400c3b54  nop     dword ptr [rax+rax+00h]
0x1400c3b59  mov     rcx, [rbp+5Fh]; this
0x1400c3b5d  test    eax, eax
0x1400c3b5f  jnz     short loc_1400C3B73
0x1400c3b61  lea     r8, aOnecoreVmCommo_90; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400c3b68  mov     edx, 1CE7h; void *
0x1400c3b6d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400c3b73  xorps   xmm0, xmm0
0x1400c3b76  movups  xmmword ptr [rbp+57h+pDacl], xmm0
0x1400c3b7a  mov     [rbp+57h+pDacl], 0
0x1400c3b82  lea     rcx, [rbp+57h+TokenHandle]; this
0x1400c3b86  call    ?_GetInformation@VmAccessToken@Vml@@AEBAPEAXW4_TOKEN_INFORMATION_CLASS@@@Z; Vml::VmAccessToken::_GetInformation(_TOKEN_INFORMATION_CLASS)
0x1400c3b8b  mov     rbx, rax
0x1400c3b8e  mov     [rbp+57h+pDacl], rax
0x1400c3b92  mov     rdx, [rax]; void *
0x1400c3b95  lea     rcx, [rbp+57h+var_60]; this
0x1400c3b99  call    ?Assign@VmSid@Vml@@QEAAXPEAX@Z; Vml::VmSid::Assign(void *)
0x1400c3b9e  nop
0x1400c3b9f  test    rbx, rbx
0x1400c3ba2  jz      short loc_1400C3BB3
0x1400c3ba4  mov     rcx, rbx; hMem
0x1400c3ba7  call    cs:__imp_LocalFree
0x1400c3bae  nop     dword ptr [rax+rax+00h]
0x1400c3bb3  xorps   xmm0, xmm0
0x1400c3bb6  movups  xmmword ptr [rbp+57h+pDacl], xmm0
0x1400c3bba  lea     rcx, [rbp+57h+pSecurityDescriptor]; this
0x1400c3bbe  call    ?GetDacl@VmSecurityDescriptor@Vml@@QEBAPEBU_ACL@@XZ; Vml::VmSecurityDescriptor::GetDacl(void)
0x1400c3bc3  mov     [rbp+57h+pDacl], 0
0x1400c3bcb  mov     rdx, rax; struct _ACL *
0x1400c3bce  lea     rcx, [rbp+57h+pDacl]; this
0x1400c3bd2  call    ?Assign@VmAcl@Vml@@QEAAXPEBU_ACL@@@Z; Vml::VmAcl::Assign(_ACL const *)
0x1400c3bd7  nop
0x1400c3bd8  lea     rcx, [rbp+57h+pSecurityDescriptor]; this
0x1400c3bdc  call    ?GetDacl@VmSecurityDescriptor@Vml@@QEBAPEBU_ACL@@XZ; Vml::VmSecurityDescriptor::GetDacl(void)
0x1400c3be1  mov     rdx, rax; struct _ACL *
0x1400c3be4  lea     rcx, [rbp+57h+pDacl]; this
0x1400c3be8  call    ?Assign@VmAcl@Vml@@QEAAXPEBU_ACL@@@Z; Vml::VmAcl::Assign(_ACL const *)
0x1400c3bed  mov     rdx, [rbp+57h+var_60]; void *
0x1400c3bf1  lea     rcx, [rbp+57h+pDacl]; this
0x1400c3bf5  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x1400c3bfa  lea     rcx, [rbp+57h+pSecurityDescriptor]; this
0x1400c3bfe  call    ?MakeAbsolute@VmSecurityDescriptor@Vml@@QEAAXXZ; Vml::VmSecurityDescriptor::MakeAbsolute(void)
0x1400c3c03  xor     r9d, r9d; bDaclDefaulted
0x1400c3c06  mov     r8, [rbp+57h+pDacl]; pDacl
0x1400c3c0a  lea     edx, [r9+1]; bDaclPresent
0x1400c3c0e  mov     rbx, [rbp+57h+pSecurityDescriptor]
0x1400c3c12  mov     rcx, rbx; pSecurityDescriptor
0x1400c3c15  call    cs:__imp_SetSecurityDescriptorDacl
0x1400c3c1c  nop     dword ptr [rax+rax+00h]
0x1400c3c21  mov     rcx, [rbp+5Fh]; this
0x1400c3c25  test    eax, eax
0x1400c3c27  jnz     short loc_1400C3C3B
0x1400c3c29  lea     r8, aOnecoreVmCommo_90; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400c3c30  mov     edx, 0DD6h; void *
0x1400c3c35  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400c3c3b  mov     [rsp+0E0h+pReserved3], 0; pReserved3
0x1400c3c44  mov     [rsp+0E0h+dwCapabilities], 5002h; dwCapabilities
0x1400c3c4c  mov     [rsp+0E0h+pAuthList], 0; pAuthList
0x1400c3c55  mov     [rsp+0E0h+dwImpLevel], 2; dwImpLevel
0x1400c3c5d  mov     [rsp+0E0h+dwAuthnLevel], 5; int
0x1400c3c65  xor     r9d, r9d; pReserved1
0x1400c3c68  xor     r8d, r8d; asAuthSvc
0x1400c3c6b  or      edx, 0FFFFFFFFh; cAuthSvc
0x1400c3c6e  mov     rcx, rbx; pSecDesc
0x1400c3c71  call    cs:__imp_CoInitializeSecurity
0x1400c3c78  nop     dword ptr [rax+rax+00h]
0x1400c3c7d  mov     rcx, [rbp+5Fh]; this
0x1400c3c81  test    eax, eax
0x1400c3c83  jns     short loc_1400C3C9A
0x1400c3c85  mov     r9d, eax; char *
0x1400c3c88  lea     r8, aOnecoreVmWorke_1; "onecore\\vm\\worker\\wpexe\\workermodul"...
0x1400c3c8f  mov     edx, 477h; void *
0x1400c3c94  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400c3c9a  cmp     [rbp+57h+pDacl], 0
0x1400c3c9f  jz      short loc_1400C3CB2
0x1400c3ca1  mov     rcx, [rbp+57h+pDacl]; hMem
0x1400c3ca5  call    cs:__imp_LocalFree
0x1400c3cac  nop     dword ptr [rax+rax+00h]
0x1400c3cb1  nop
0x1400c3cb2  lea     rcx, [rbp+57h+var_60]; this
0x1400c3cb6  call    ??1VmSid@Vml@@QEAA@XZ; Vml::VmSid::~VmSid(void)
0x1400c3cbb  nop
0x1400c3cbc  lea     rcx, [rbp+57h+TokenHandle]; this
0x1400c3cc0  call    ??1VmAccessToken@Vml@@QEAA@XZ; Vml::VmAccessToken::~VmAccessToken(void)
0x1400c3cc5  nop
0x1400c3cc6  test    rbx, rbx
0x1400c3cc9  jz      short loc_1400C3CDA
0x1400c3ccb  mov     rcx, rbx; hMem
0x1400c3cce  call    cs:__imp_LocalFree
0x1400c3cd5  nop     dword ptr [rax+rax+00h]
0x1400c3cda  mov     rcx, [rbp+57h+var_10]
0x1400c3cde  xor     rcx, rsp; StackCookie
0x1400c3ce1  call    __security_check_cookie
0x1400c3ce6  mov     rbx, [rsp+0E0h+arg_0]
0x1400c3cee  add     rsp, 0E0h
0x1400c3cf5  pop     rbp
0x1400c3cf6  retn
```
