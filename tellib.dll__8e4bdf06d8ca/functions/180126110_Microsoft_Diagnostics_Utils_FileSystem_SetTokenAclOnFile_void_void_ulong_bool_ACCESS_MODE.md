# Microsoft::Diagnostics::Utils::FileSystem::SetTokenAclOnFile(void *,void *,ulong,bool,_ACCESS_MODE)

- ea: `0x180126110`
- end: `0x180126439`
- name: `?SetTokenAclOnFile@FileSystem@Utils@Diagnostics@Microsoft@@SAJPEAX0K_NW4_ACCESS_MODE@@@Z`
- size: `809`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, HANDLE handle, unsigned int, bool, enum _ACCESS_MODE)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801260b4`
- `0x1802300a0`

## callees

- `0x180026ecc`
- `0x18006dd98`
- `0x18006f66c`
- `0x18007fae8`
- `0x18008bd1c`
- `0x1800d0d7c`
- `0x1800d0df0`
- `0x1800edba8`
- `0x180126110`
- `0x180170014`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801261eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801261eb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801261db`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180126285`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801261db`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180126285`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180126176`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180126176`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1801263a2`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1801263a2`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18012632c`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18012632c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Diagnostics::Utils::FileSystem::SetTokenAclOnFile(
        HANDLE TokenHandle,
        HANDLE handle,
        __int64 a3,
        char a4)
{
  DWORD SecurityInfo; // eax
  unsigned int v7; // ebx
  __int64 result; // rax
  BOOL v9; // eax
  DWORD v10; // eax
  const struct std::nothrow_t *v11; // rax
  LPWCH *v12; // rbx
  const char *v13; // r9
  unsigned int LastError; // ebx
  const char *v15; // r9
  DWORD v16; // eax
  unsigned int v17; // ebx
  DWORD v18; // eax
  unsigned int v19; // ebx
  unsigned int ppsidGroup; // [rsp+20h] [rbp-98h]
  int ppsidGroupa; // [rsp+20h] [rbp-98h]
  unsigned int ppsidGroupb; // [rsp+20h] [rbp-98h]
  unsigned int ppsidGroupc; // [rsp+20h] [rbp-98h]
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+40h] [rbp-78h] BYREF
  LPVOID TokenInformation; // [rsp+48h] [rbp-70h] BYREF
  PACL NewAcl; // [rsp+50h] [rbp-68h] BYREF
  PACL OldAcl; // [rsp+58h] [rbp-60h] BYREF
  _BYTE v28[8]; // [rsp+60h] [rbp-58h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+68h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  DWORD ReturnLength; // [rsp+D8h] [rbp+20h] BYREF

  LOBYTE(ReturnLength) = a4;
  ppSecurityDescriptor = 0;
  OldAcl = 0;
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
    &ppSecurityDescriptor,
    0);
  SecurityInfo = GetSecurityInfo(handle, SE_FILE_OBJECT, 4u, 0, 0, &OldAcl, 0, &ppSecurityDescriptor);
  if ( SecurityInfo )
  {
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x5F2,
           (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
           (const char *)SecurityInfo,
           ppsidGroup);
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&ppSecurityDescriptor);
    return v7;
  }
  else
  {
    ReturnLength = 0;
    TokenInformation = 0;
    v9 = GetTokenInformation(TokenHandle, TokenUser, 0, 0, &ReturnLength);
    if ( v9 || (v10 = GetLastError(), v10 == 122) )
    {
      try
      {
        v11 = (const struct std::nothrow_t *)std::make_unique<unsigned char [0],0>(v28, ReturnLength);
        std::unique_ptr<enum gsl::byte [0]>::operator=<std::default_delete<enum gsl::byte [0]>,0>(
          &TokenInformation,
          v11);
        std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(v28);
        v12 = (LPWCH *)TokenInformation;
        if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, ReturnLength, &ReturnLength) )
        {
          *(_QWORD *)&pListOfExplicitEntries.grfInheritance = 3;
          pListOfExplicitEntries.Trustee.ptstrName = 0;
          pListOfExplicitEntries.grfAccessPermissions = 0x10000000;
          pListOfExplicitEntries.grfAccessMode = REVOKE_ACCESS;
          pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
          *(_QWORD *)&pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = 0;
          *(_QWORD *)&pListOfExplicitEntries.Trustee.TrusteeType = 1;
          pListOfExplicitEntries.Trustee.ptstrName = *v12;
          NewAcl = 0;
          v16 = SetEntriesInAclW(1u, &pListOfExplicitEntries, OldAcl, &NewAcl);
          if ( v16 )
          {
            v17 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x617,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
                    (const char *)v16,
                    ppsidGroupb);
            wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>(&NewAcl);
            std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&TokenInformation);
            wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&ppSecurityDescriptor);
            result = v17;
          }
          else
          {
            v18 = SetSecurityInfo(handle, SE_FILE_OBJECT, 4u, 0, 0, NewAcl, 0);
            if ( v18 )
            {
              v19 = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x61A,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
                      (const char *)v18,
                      ppsidGroupc);
              wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>(&NewAcl);
              std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&TokenInformation);
              wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&ppSecurityDescriptor);
              result = v19;
            }
            else
            {
              wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>(&NewAcl);
              std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&TokenInformation);
              wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&ppSecurityDescriptor);
              result = 0;
            }
          }
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x601,
                        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
                        v13);
          std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&TokenInformation);
          wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&ppSecurityDescriptor);
          result = LastError;
        }
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x61E,
                               (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
                               v15);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5FC,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
        (const char *)0x80004005LL,
        ppsidGroupa);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&TokenInformation);
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&ppSecurityDescriptor);
      return 2147500037LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180126110  mov     rax, rsp
0x180126113  mov     [rax+8], rbx
0x180126117  mov     [rax+10h], rsi
0x18012611b  mov     [rax+20h], r9b
0x18012611f  push    rdi
0x180126120  push    r14
0x180126122  push    r15
0x180126124  sub     rsp, 0A0h
0x18012612b  mov     rdi, rdx
0x18012612e  mov     rsi, rcx
0x180126131  xor     r14d, r14d
0x180126134  mov     [rax-78h], r14
0x180126138  mov     [rax-60h], r14
0x18012613c  xor     edx, edx
0x18012613e  lea     rcx, [rax-78h]
0x180126142  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x180126147  lea     rax, [rsp+0B8h+var_78]
0x18012614c  mov     [rsp+0B8h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180126151  mov     [rsp+0B8h+ppSacl], r14; ppSacl
0x180126156  lea     rax, [rsp+0B8h+OldAcl]
0x18012615b  mov     [rsp+0B8h+ppDacl], rax; ppDacl
0x180126160  mov     [rsp+0B8h+ppsidGroup], r14; unsigned int
0x180126165  xor     r9d, r9d; ppsidOwner
0x180126168  lea     r8d, [r14+4]; SecurityInfo
0x18012616c  lea     r15d, [r14+1]
0x180126170  mov     edx, r15d; ObjectType
0x180126173  mov     rcx, rdi; handle
0x180126176  call    cs:__imp_GetSecurityInfo
0x18012617d  nop     dword ptr [rax+rax+00h]
0x180126182  test    eax, eax
0x180126184  jz      short loc_1801261B5
0x180126186  mov     rcx, [rsp+0B8h]; this
0x18012618e  mov     r9d, eax; char *
0x180126191  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x180126198  mov     edx, 5F2h; void *
0x18012619d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801261a2  mov     ebx, eax
0x1801261a4  lea     rcx, [rsp+0B8h+var_78]
0x1801261a9  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1801261ae  mov     eax, ebx
0x1801261b0  jmp     loc_18012641F
0x1801261b5  mov     [rsp+0B8h+ReturnLength], r14d
0x1801261bd  mov     [rsp+0B8h+TokenInformation], r14
0x1801261c2  lea     rax, [rsp+0B8h+ReturnLength]
0x1801261ca  mov     [rsp+0B8h+ppsidGroup], rax; int
0x1801261cf  xor     r9d, r9d; TokenInformationLength
0x1801261d2  xor     r8d, r8d; TokenInformation
0x1801261d5  mov     edx, r15d; TokenInformationClass
0x1801261d8  mov     rcx, rsi; TokenHandle
0x1801261db  call    cs:__imp_GetTokenInformation
0x1801261e2  nop     dword ptr [rax+rax+00h]
0x1801261e7  test    eax, eax
0x1801261e9  jnz     short loc_18012623A
0x1801261eb  call    cs:__imp_GetLastError
0x1801261f2  nop     dword ptr [rax+rax+00h]
0x1801261f7  cmp     eax, 7Ah ; 'z'
0x1801261fa  jz      short loc_18012623A
0x1801261fc  mov     rcx, [rsp+0B8h]; this
0x180126204  mov     ebx, 80004005h
0x180126209  mov     r9d, ebx; char *
0x18012620c  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x180126213  mov     edx, 5FCh; void *
0x180126218  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012621d  nop
0x18012621e  lea     rcx, [rsp+0B8h+TokenInformation]
0x180126223  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x180126228  nop
0x180126229  lea     rcx, [rsp+0B8h+var_78]
0x18012622e  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180126233  mov     eax, ebx
0x180126235  jmp     loc_18012641F
0x18012623a  mov     edx, [rsp+0B8h+ReturnLength]
0x180126241  lea     rcx, [rsp+0B8h+var_58]
0x180126246  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x18012624b  mov     rdx, rax
0x18012624e  lea     rcx, [rsp+0B8h+TokenInformation]
0x180126253  call    ??$?4U?$default_delete@$$BY0A@W4byte@gsl@@@std@@$0A@@?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<gsl::byte [0]>::operator=<std::default_delete<gsl::byte [0]>,0>(std::unique_ptr<gsl::byte [0]> &&)
0x180126258  lea     rcx, [rsp+0B8h+var_58]
0x18012625d  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x180126262  lea     rax, [rsp+0B8h+ReturnLength]
0x18012626a  mov     [rsp+0B8h+ppsidGroup], rax; unsigned int
0x18012626f  mov     r9d, [rsp+0B8h+ReturnLength]; TokenInformationLength
0x180126277  mov     rbx, [rsp+0B8h+TokenInformation]
0x18012627c  mov     r8, rbx; TokenInformation
0x18012627f  mov     edx, r15d; TokenInformationClass
0x180126282  mov     rcx, rsi; TokenHandle
0x180126285  call    cs:__imp_GetTokenInformation
0x18012628c  nop     dword ptr [rax+rax+00h]
0x180126291  test    eax, eax
0x180126293  jnz     short loc_1801262CC
0x180126295  mov     rcx, [rsp+0B8h]; this
0x18012629d  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x1801262a4  mov     edx, 601h; void *
0x1801262a9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801262ae  mov     ebx, eax
0x1801262b0  lea     rcx, [rsp+0B8h+TokenInformation]
0x1801262b5  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x1801262ba  nop
0x1801262bb  lea     rcx, [rsp+0B8h+var_78]
0x1801262c0  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1801262c5  mov     eax, ebx
0x1801262c7  jmp     loc_18012641F
0x1801262cc  mov     qword ptr [rsp+0B8h+pListOfExplicitEntries.grfInheritance], 3
0x1801262d5  mov     qword ptr [rsp+0B8h+pListOfExplicitEntries.Trustee+14h], r14
0x1801262dd  mov     dword ptr [rsp+0B8h+pListOfExplicitEntries.Trustee.ptstrName+4], r14d
0x1801262e5  mov     [rsp+0B8h+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x1801262ed  mov     [rsp+0B8h+pListOfExplicitEntries.grfAccessMode], 4
0x1801262f5  mov     [rsp+0B8h+pListOfExplicitEntries.Trustee.pMultipleTrustee], r14
0x1801262fa  mov     qword ptr [rsp+0B8h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], r14
0x180126302  mov     [rsp+0B8h+pListOfExplicitEntries.Trustee.TrusteeType], r15d
0x18012630a  mov     rax, [rbx]
0x18012630d  mov     [rsp+0B8h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180126315  mov     [rsp+0B8h+NewAcl], r14
0x18012631a  lea     r9, [rsp+0B8h+NewAcl]; NewAcl
0x18012631f  mov     r8, [rsp+0B8h+OldAcl]; OldAcl
0x180126324  lea     rdx, [rsp+0B8h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180126329  mov     ecx, r15d; cCountOfExplicitEntries
0x18012632c  call    cs:__imp_SetEntriesInAclW
0x180126333  nop     dword ptr [rax+rax+00h]
0x180126338  test    eax, eax
0x18012633a  jz      short loc_180126381
0x18012633c  mov     rcx, [rsp+0B8h]; this
0x180126344  mov     r9d, eax; char *
0x180126347  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x18012634e  mov     edx, 617h; void *
0x180126353  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180126358  mov     ebx, eax
0x18012635a  lea     rcx, [rsp+0B8h+NewAcl]
0x18012635f  call    ??1?$unique_storage@U?$resource_policy@PEAU_ACL@@$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>(void)
0x180126364  nop
0x180126365  lea     rcx, [rsp+0B8h+TokenInformation]
0x18012636a  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x18012636f  nop
0x180126370  lea     rcx, [rsp+0B8h+var_78]
0x180126375  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18012637a  mov     eax, ebx
0x18012637c  jmp     loc_18012641F
0x180126381  mov     [rsp+0B8h+ppSacl], r14; pSacl
0x180126386  mov     rax, [rsp+0B8h+NewAcl]
0x18012638b  mov     [rsp+0B8h+ppDacl], rax; pDacl
0x180126390  mov     [rsp+0B8h+ppsidGroup], r14; unsigned int
0x180126395  xor     r9d, r9d; psidOwner
0x180126398  lea     r8d, [r9+4]; SecurityInfo
0x18012639c  mov     edx, r15d; ObjectType
0x18012639f  mov     rcx, rdi; handle
0x1801263a2  call    cs:__imp_SetSecurityInfo
0x1801263a9  nop     dword ptr [rax+rax+00h]
0x1801263ae  test    eax, eax
0x1801263b0  jz      short loc_1801263F4
0x1801263b2  mov     rcx, [rsp+0B8h]; this
0x1801263ba  mov     r9d, eax; char *
0x1801263bd  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x1801263c4  mov     edx, 61Ah; void *
0x1801263c9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801263ce  mov     ebx, eax
0x1801263d0  lea     rcx, [rsp+0B8h+NewAcl]
0x1801263d5  call    ??1?$unique_storage@U?$resource_policy@PEAU_ACL@@$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>(void)
0x1801263da  nop
0x1801263db  lea     rcx, [rsp+0B8h+TokenInformation]
0x1801263e0  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x1801263e5  nop
0x1801263e6  lea     rcx, [rsp+0B8h+var_78]
0x1801263eb  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1801263f0  mov     eax, ebx
0x1801263f2  jmp     short loc_18012641F
0x1801263f4  lea     rcx, [rsp+0B8h+NewAcl]
0x1801263f9  call    ??1?$unique_storage@U?$resource_policy@PEAU_ACL@@$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>(void)
0x1801263fe  nop
0x1801263ff  lea     rcx, [rsp+0B8h+TokenInformation]
0x180126404  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x180126409  nop
0x18012640a  lea     rcx, [rsp+0B8h+var_78]
0x18012640f  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180126414  xor     eax, eax
0x180126416  jmp     short loc_18012641F
0x180126418  mov     eax, [rsp+0B8h+ReturnLength]
0x18012641f  lea     r11, [rsp+0B8h+var_18]
0x180126427  mov     rbx, [r11+20h]
0x18012642b  mov     rsi, [r11+28h]
0x18012642f  mov     rsp, r11
0x180126432  pop     r15
0x180126434  pop     r14
0x180126436  pop     rdi
0x180126437  retn
```
