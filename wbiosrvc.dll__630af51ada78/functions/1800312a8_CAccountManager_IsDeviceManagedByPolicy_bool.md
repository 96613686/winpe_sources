# CAccountManager::IsDeviceManagedByPolicy(bool *)

- ea: `0x1800312a8`
- end: `0x1800314d9`
- name: `?IsDeviceManagedByPolicy@CAccountManager@@CAJPEA_N@Z`
- size: `561`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008dd0`

## callees

- `0x1800312a8`
- `0x1800314e0`
- `0x180031510`
- `0x18005388c`
- `0x1800538b0`
- `0x180068f60`
- `0x180069cc8`
- `0x180072410`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180031351`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180031351`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800313a0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800313a0`
- `dsreg!DsrIsDeviceJoined` at `0x18003140b`
- `dsreg!DsrIsDeviceJoined` at `0x18003140b`
- `MDMRegistration!IsDeviceRegisteredWithManagement` at `0x18003146b`
- `MDMRegistration!IsDeviceRegisteredWithManagement` at `0x18003146b`

## string_xrefs

- `0x1800312df`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`
- `0x180031362`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`
- `0x1800313b1`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`
- `0x18003142e`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`
- `0x180031488`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`

## pseudocode

```c
int __fastcall CAccountManager::IsDeviceManagedByPolicy(bool *a1)
{
  int v2; // ebx
  NTSTATUS v3; // eax
  NTSTATUS v5; // eax
  unsigned int IsDeviceJoined; // eax
  unsigned int v7; // eax
  int v8; // [rsp+20h] [rbp-E0h] BYREF
  int v9; // [rsp+24h] [rbp-DCh] BYREF
  PVOID PolicyHandle; // [rsp+28h] [rbp-D8h] BYREF
  PVOID Buffer; // [rsp+30h] [rbp-D0h] BYREF
  PVOID *p_Buffer; // [rsp+38h] [rbp-C8h] BYREF
  __int16 v13; // [rsp+40h] [rbp-C0h]
  PVOID *p_PolicyHandle; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v15; // [rsp+50h] [rbp-B0h]
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v17[6]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v18[528]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  if ( a1 )
  {
    *a1 = 0;
    ObjectAttributes.SecurityQualityOfService = v17;
    v17[2] = 1;
    v17[0] = 12;
    v17[1] = 2;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.RootDirectory, 0, 32);
    PolicyHandle = 0;
    v3 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
    if ( v3 < 0 )
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x49C,
               (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
               (const char *)(unsigned int)v3,
               v8);
    p_PolicyHandle = &PolicyHandle;
    v15 = 256;
    Buffer = 0;
    v5 = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffer);
    if ( v5 >= 0 )
    {
      v13 = 256;
      p_Buffer = &Buffer;
      if ( *((_WORD *)Buffer + 8) || *((_WORD *)Buffer + 16) || *((_QWORD *)Buffer + 8) )
        goto LABEL_18;
      v8 = 0;
      IsDeviceJoined = DsrIsDeviceJoined(&v8, 0);
      if ( (int)(IsDeviceJoined + 0x80000000) >= 0 && IsDeviceJoined != -2147024894 )
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x4BA,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
          (const char *)IsDeviceJoined,
          v8);
      if ( v8 )
        goto LABEL_18;
      memset_0(v18, 0, 0x208u);
      v9 = 0;
      v7 = IsDeviceRegisteredWithManagement(&v9, 260, v18);
      if ( ((v7 + 0x80000000) & 0x80000000) == 0 && v7 != -2147024894 )
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x4C8,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
          (const char *)v7,
          v8);
      if ( v9 )
LABEL_18:
        *a1 = 1;
      wil::details::ScopeExitFnGuard__lambda_a6fab2d3507c99b67da459f570bec198___::operator()(&p_Buffer);
      v2 = 0;
    }
    else
    {
      v2 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x4A6,
             (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
             (const char *)(unsigned int)v5,
             v8);
    }
    wil::details::ScopeExitFnGuard__lambda_a04f81a4ef424f8f186875a88ad2ddcc___::operator()(&p_PolicyHandle);
  }
  else
  {
    v2 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x480,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
      (const char *)0x80004003LL,
      v8);
  }
  return v2;
}

```

## disassembly

```asm
0x1800312a8  push    rbp
0x1800312aa  push    rbx
0x1800312ab  push    rdi
0x1800312ac  push    r14
0x1800312ae  lea     rbp, [rsp-1C8h]
0x1800312b6  sub     rsp, 2C8h
0x1800312bd  mov     rax, cs:__security_cookie
0x1800312c4  xor     rax, rsp
0x1800312c7  mov     [rbp+1E0h+var_30], rax
0x1800312ce  xor     edi, edi
0x1800312d0  mov     rbx, rcx
0x1800312d3  test    rcx, rcx
0x1800312d6  jnz     short loc_1800312FD
0x1800312d8  mov     rcx, [rbp+1E8h]; this
0x1800312df  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x1800312e6  mov     ebx, 80004003h
0x1800312eb  mov     edx, 480h; void *
0x1800312f0  mov     r9d, ebx; char *
0x1800312f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800312f8  jmp     loc_1800314BB
0x1800312fd  mov     [rcx], dil
0x180031300  lea     rax, [rbp+1E0h+var_258]
0x180031304  xor     ecx, ecx; SystemName
0x180031306  mov     [rbp+1E0h+ObjectAttributes.SecurityQualityOfService], rax
0x18003130a  lea     r9, [rsp+2E0h+PolicyHandle]; PolicyHandle
0x18003130f  mov     [rbp+1E0h+var_250], 1
0x180031316  mov     r8d, 1; DesiredAccess
0x18003131c  mov     [rbp+1E0h+var_258], 0Ch
0x180031323  lea     rdx, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x180031328  mov     [rbp+1E0h+var_254], 2
0x18003132f  mov     qword ptr [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x180031338  mov     qword ptr [rsp+2E0h+ObjectAttributes.Attributes], rdi
0x18003133d  mov     [rsp+2E0h+ObjectAttributes.RootDirectory], rdi
0x180031342  mov     [rsp+2E0h+ObjectAttributes.ObjectName], rdi
0x180031347  mov     [rsp+2E0h+ObjectAttributes.SecurityDescriptor], rdi
0x18003134c  mov     [rsp+2E0h+PolicyHandle], rdi
0x180031351  call    cs:__imp_LsaOpenPolicy
0x180031357  test    eax, eax
0x180031359  jns     short loc_18003137B
0x18003135b  mov     rcx, [rbp+1E8h]; this
0x180031362  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x180031369  mov     r9d, eax; char *
0x18003136c  mov     edx, 49Ch; void *
0x180031371  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180031376  jmp     loc_1800314BD
0x18003137b  mov     rcx, [rsp+2E0h+PolicyHandle]; PolicyHandle
0x180031380  lea     rax, [rsp+2E0h+PolicyHandle]
0x180031385  lea     r8, [rsp+2E0h+Buffer]; Buffer
0x18003138a  mov     [rsp+2E0h+var_298], rax
0x18003138f  mov     edx, 0Ch; InformationClass
0x180031394  mov     [rsp+2E0h+var_290], 100h
0x18003139b  mov     [rsp+2E0h+Buffer], rdi
0x1800313a0  call    cs:__imp_LsaQueryInformationPolicy
0x1800313a6  test    eax, eax
0x1800313a8  jns     short loc_1800313CC
0x1800313aa  mov     rcx, [rbp+1E8h]; this
0x1800313b1  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x1800313b8  mov     r9d, eax; char *
0x1800313bb  mov     edx, 4A6h; void *
0x1800313c0  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800313c5  mov     ebx, eax
0x1800313c7  jmp     loc_1800314B1
0x1800313cc  lea     rax, [rsp+2E0h+Buffer]
0x1800313d1  mov     [rsp+2E0h+var_2A0], 100h
0x1800313d8  mov     [rsp+2E0h+var_2A8], rax
0x1800313dd  mov     rax, [rsp+2E0h+Buffer]
0x1800313e2  cmp     [rax+10h], di
0x1800313e6  jnz     loc_1800314A2
0x1800313ec  cmp     [rax+20h], di
0x1800313f0  jnz     loc_1800314A2
0x1800313f6  cmp     [rax+40h], rdi
0x1800313fa  jnz     loc_1800314A2
0x180031400  xor     edx, edx
0x180031402  mov     [rsp+2E0h+var_2C0], edi; int
0x180031406  lea     rcx, [rsp+2E0h+var_2C0]
0x18003140b  call    cs:__imp_DsrIsDeviceJoined
0x180031411  mov     r14d, 80000000h
0x180031417  lea     ecx, [rax+r14]
0x18003141b  test    r14d, ecx
0x18003141e  jnz     short loc_180031442
0x180031420  cmp     eax, 80070002h
0x180031425  jz      short loc_180031442
0x180031427  mov     rcx, [rbp+1E8h]; this
0x18003142e  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x180031435  mov     r9d, eax; char *
0x180031438  mov     edx, 4BAh; void *
0x18003143d  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180031442  cmp     [rsp+2E0h+var_2C0], edi
0x180031446  jnz     short loc_1800314A2
0x180031448  xor     edx, edx; Val
0x18003144a  lea     rcx, [rbp+1E0h+var_240]; void *
0x18003144e  mov     r8d, 208h; Size
0x180031454  call    memset_0
0x180031459  lea     r8, [rbp+1E0h+var_240]
0x18003145d  mov     [rsp+2E0h+var_2BC], edi
0x180031461  mov     edx, 104h
0x180031466  lea     rcx, [rsp+2E0h+var_2BC]
0x18003146b  call    cs:__imp_IsDeviceRegisteredWithManagement
0x180031471  lea     ecx, [rax+r14]
0x180031475  test    r14d, ecx
0x180031478  jnz     short loc_18003149C
0x18003147a  cmp     eax, 80070002h
0x18003147f  jz      short loc_18003149C
0x180031481  mov     rcx, [rbp+1E8h]; this
0x180031488  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x18003148f  mov     r9d, eax; char *
0x180031492  mov     edx, 4C8h; void *
0x180031497  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18003149c  cmp     [rsp+2E0h+var_2BC], edi
0x1800314a0  jz      short loc_1800314A5
0x1800314a2  mov     byte ptr [rbx], 1
0x1800314a5  lea     rcx, [rsp+2E0h+var_2A8]
0x1800314aa  call    wil__details__ScopeExitFnGuard__lambda_a6fab2d3507c99b67da459f570bec198_____operator__
0x1800314af  mov     ebx, edi
0x1800314b1  lea     rcx, [rsp+2E0h+var_298]
0x1800314b6  call    wil__details__ScopeExitFnGuard__lambda_a04f81a4ef424f8f186875a88ad2ddcc_____operator__
0x1800314bb  mov     eax, ebx
0x1800314bd  mov     rcx, [rbp+1E0h+var_30]
0x1800314c4  xor     rcx, rsp; StackCookie
0x1800314c7  call    __security_check_cookie
0x1800314cc  add     rsp, 2C8h
0x1800314d3  pop     r14
0x1800314d5  pop     rdi
0x1800314d6  pop     rbx
0x1800314d7  pop     rbp
0x1800314d8  retn
```
