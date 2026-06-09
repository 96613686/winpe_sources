# WorkerModule::InitializeComSecurity(void)

- ea: `0x14006570c`
- end: `0x140065964`
- name: `?InitializeComSecurity@WorkerModule@@QEAAXXZ`
- size: `600`
- prototype: `void __fastcall(WorkerModule *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400652b0`

## callees

- `0x14006570c`
- `0x140065ab8`
- `0x140065b44`
- `0x140065bd0`
- `0x140065d58`
- `0x140065e28`
- `0x140065f1c`
- `0x140065fe4`
- `0x140066020`
- `0x14006713c`
- `0x140078628`
- `0x140083990`
- `0x14011ea40`
- `0x14011f6fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400657a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400657a1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400657b9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400657b9`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1400658dd`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1400658dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140065813`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140065911`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14006593a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140065813`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140065911`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14006593a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x140065881`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x140065881`

## string_xrefs

- `0x1400657cd`: `onecore\vm\common\vml\VmSecurity.h`
- `0x140065895`: `onecore\vm\common\vml\VmSecurity.h`

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
0x14006570c  mov     [rsp-8+arg_0], rbx
0x140065711  push    rbp
0x140065712  lea     rbp, [rsp-57h]
0x140065717  sub     rsp, 0E0h
0x14006571e  mov     rax, cs:__security_cookie
0x140065725  xor     rax, rsp
0x140065728  mov     [rbp+57h+var_10], rax
0x14006572c  xorps   xmm0, xmm0
0x14006572f  movups  xmmword ptr [rbp+57h+pSecurityDescriptor], xmm0
0x140065733  mov     [rbp+57h+pSecurityDescriptor], 0
0x14006573b  lea     rdx, aOBagBadAOici0x; "O:BAG:BAD:(A;OICI;0x3;;;SY)(A;OICI;0x3;"...
0x140065742  lea     rcx, [rbp+57h+pSecurityDescriptor]; this
0x140065746  call    ?Assign@VmSecurityDescriptor@Vml@@QEAAXPEBGK@Z; Vml::VmSecurityDescriptor::Assign(ushort const *,ulong)
0x14006574b  lea     rcx, [rbp+57h+pSecurityDescriptor]; this
0x14006574f  call    ?MakeAbsolute@VmSecurityDescriptor@Vml@@QEAAXXZ; Vml::VmSecurityDescriptor::MakeAbsolute(void)
0x140065754  mov     [rbp+57h+TokenHandle], 0
0x14006575c  xor     edx, edx; Val
0x14006575e  lea     r8d, [rdx+50h]; Size
0x140065762  lea     rcx, [rbp+57h+var_60]; void *
0x140065766  call    memset_0
0x14006576b  mov     [rbp+57h+var_60], 0
0x140065773  mov     [rbp+57h+var_58], 7
0x14006577a  xorps   xmm0, xmm0
0x14006577d  movups  [rbp+57h+var_50], xmm0
0x140065781  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140065789  movdqa  [rbp+57h+var_40], xmm1
0x14006578e  xor     eax, eax
0x140065790  mov     word ptr [rbp+57h+var_50], ax
0x140065794  movups  [rbp+57h+var_30], xmm0
0x140065798  movdqa  [rbp+57h+var_20], xmm1
0x14006579d  mov     word ptr [rbp+57h+var_30], ax
0x1400657a1  call    cs:__imp_GetCurrentProcess
0x1400657a8  nop     dword ptr [rax+rax+00h]
0x1400657ad  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1400657b1  mov     edx, 8; DesiredAccess
0x1400657b6  mov     rcx, rax; ProcessHandle
0x1400657b9  call    cs:__imp_OpenProcessToken
0x1400657c0  nop     dword ptr [rax+rax+00h]
0x1400657c5  mov     rcx, [rbp+5Fh]; this
0x1400657c9  test    eax, eax
0x1400657cb  jnz     short loc_1400657DF
0x1400657cd  lea     r8, aOnecoreVmCommo_90; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400657d4  mov     edx, 1CE7h; void *
0x1400657d9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400657df  xorps   xmm0, xmm0
0x1400657e2  movups  xmmword ptr [rbp+57h+pDacl], xmm0
0x1400657e6  mov     [rbp+57h+pDacl], 0
0x1400657ee  lea     rcx, [rbp+57h+TokenHandle]; this
0x1400657f2  call    ?_GetInformation@VmAccessToken@Vml@@AEBAPEAXW4_TOKEN_INFORMATION_CLASS@@@Z; Vml::VmAccessToken::_GetInformation(_TOKEN_INFORMATION_CLASS)
0x1400657f7  mov     rbx, rax
0x1400657fa  mov     [rbp+57h+pDacl], rax
0x1400657fe  mov     rdx, [rax]; void *
0x140065801  lea     rcx, [rbp+57h+var_60]; this
0x140065805  call    ?Assign@VmSid@Vml@@QEAAXPEAX@Z; Vml::VmSid::Assign(void *)
0x14006580a  nop
0x14006580b  test    rbx, rbx
0x14006580e  jz      short loc_14006581F
0x140065810  mov     rcx, rbx; hMem
0x140065813  call    cs:__imp_LocalFree
0x14006581a  nop     dword ptr [rax+rax+00h]
0x14006581f  xorps   xmm0, xmm0
0x140065822  movups  xmmword ptr [rbp+57h+pDacl], xmm0
0x140065826  lea     rcx, [rbp+57h+pSecurityDescriptor]; this
0x14006582a  call    ?GetDacl@VmSecurityDescriptor@Vml@@QEBAPEBU_ACL@@XZ; Vml::VmSecurityDescriptor::GetDacl(void)
0x14006582f  mov     [rbp+57h+pDacl], 0
0x140065837  mov     rdx, rax; struct _ACL *
0x14006583a  lea     rcx, [rbp+57h+pDacl]; this
0x14006583e  call    ?Assign@VmAcl@Vml@@QEAAXPEBU_ACL@@@Z; Vml::VmAcl::Assign(_ACL const *)
0x140065843  nop
0x140065844  lea     rcx, [rbp+57h+pSecurityDescriptor]; this
0x140065848  call    ?GetDacl@VmSecurityDescriptor@Vml@@QEBAPEBU_ACL@@XZ; Vml::VmSecurityDescriptor::GetDacl(void)
0x14006584d  mov     rdx, rax; struct _ACL *
0x140065850  lea     rcx, [rbp+57h+pDacl]; this
0x140065854  call    ?Assign@VmAcl@Vml@@QEAAXPEBU_ACL@@@Z; Vml::VmAcl::Assign(_ACL const *)
0x140065859  mov     rdx, [rbp+57h+var_60]; void *
0x14006585d  lea     rcx, [rbp+57h+pDacl]; this
0x140065861  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x140065866  lea     rcx, [rbp+57h+pSecurityDescriptor]; this
0x14006586a  call    ?MakeAbsolute@VmSecurityDescriptor@Vml@@QEAAXXZ; Vml::VmSecurityDescriptor::MakeAbsolute(void)
0x14006586f  xor     r9d, r9d; bDaclDefaulted
0x140065872  mov     r8, [rbp+57h+pDacl]; pDacl
0x140065876  lea     edx, [r9+1]; bDaclPresent
0x14006587a  mov     rbx, [rbp+57h+pSecurityDescriptor]
0x14006587e  mov     rcx, rbx; pSecurityDescriptor
0x140065881  call    cs:__imp_SetSecurityDescriptorDacl
0x140065888  nop     dword ptr [rax+rax+00h]
0x14006588d  mov     rcx, [rbp+5Fh]; this
0x140065891  test    eax, eax
0x140065893  jnz     short loc_1400658A7
0x140065895  lea     r8, aOnecoreVmCommo_90; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x14006589c  mov     edx, 0DD6h; void *
0x1400658a1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400658a7  mov     [rsp+0E0h+pReserved3], 0; pReserved3
0x1400658b0  mov     [rsp+0E0h+dwCapabilities], 5002h; dwCapabilities
0x1400658b8  mov     [rsp+0E0h+pAuthList], 0; pAuthList
0x1400658c1  mov     [rsp+0E0h+dwImpLevel], 2; dwImpLevel
0x1400658c9  mov     [rsp+0E0h+dwAuthnLevel], 5; int
0x1400658d1  xor     r9d, r9d; pReserved1
0x1400658d4  xor     r8d, r8d; asAuthSvc
0x1400658d7  or      edx, 0FFFFFFFFh; cAuthSvc
0x1400658da  mov     rcx, rbx; pSecDesc
0x1400658dd  call    cs:__imp_CoInitializeSecurity
0x1400658e4  nop     dword ptr [rax+rax+00h]
0x1400658e9  mov     rcx, [rbp+5Fh]; this
0x1400658ed  test    eax, eax
0x1400658ef  jns     short loc_140065906
0x1400658f1  mov     r9d, eax; char *
0x1400658f4  lea     r8, aOnecoreVmWorke_1; "onecore\\vm\\worker\\wpexe\\workermodul"...
0x1400658fb  mov     edx, 477h; void *
0x140065900  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140065906  cmp     [rbp+57h+pDacl], 0
0x14006590b  jz      short loc_14006591E
0x14006590d  mov     rcx, [rbp+57h+pDacl]; hMem
0x140065911  call    cs:__imp_LocalFree
0x140065918  nop     dword ptr [rax+rax+00h]
0x14006591d  nop
0x14006591e  lea     rcx, [rbp+57h+var_60]; this
0x140065922  call    ??1VmSid@Vml@@QEAA@XZ; Vml::VmSid::~VmSid(void)
0x140065927  nop
0x140065928  lea     rcx, [rbp+57h+TokenHandle]; this
0x14006592c  call    ??1VmAccessToken@Vml@@QEAA@XZ; Vml::VmAccessToken::~VmAccessToken(void)
0x140065931  nop
0x140065932  test    rbx, rbx
0x140065935  jz      short loc_140065946
0x140065937  mov     rcx, rbx; hMem
0x14006593a  call    cs:__imp_LocalFree
0x140065941  nop     dword ptr [rax+rax+00h]
0x140065946  mov     rcx, [rbp+57h+var_10]
0x14006594a  xor     rcx, rsp; StackCookie
0x14006594d  call    __security_check_cookie
0x140065952  mov     rbx, [rsp+0E0h+arg_0]
0x14006595a  add     rsp, 0E0h
0x140065961  pop     rbp
0x140065962  retn
```
