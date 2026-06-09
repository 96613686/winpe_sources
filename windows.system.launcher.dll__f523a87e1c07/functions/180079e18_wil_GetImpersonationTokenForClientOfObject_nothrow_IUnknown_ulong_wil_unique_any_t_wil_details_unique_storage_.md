# wil::GetImpersonationTokenForClientOfObject_nothrow(IUnknown *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x180079e18`
- end: `0x180079fab`
- name: `?GetImpersonationTokenForClientOfObject_nothrow@wil@@YAJPEAUIUnknown@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@@Z`
- size: `403`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180079db8`
- `0x1800e61b0`

## callees

- `0x180010c04`
- `0x18003f5d8`
- `0x180042254`
- `0x180042590`
- `0x180066ed8`
- `0x180067258`
- `0x180079e18`

## import_xrefs

- `combase!__imp_CoImpersonateClientOfObject` at `0x180079e35`
- `combase!__imp_CoImpersonateClientOfObject` at `0x180079e35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180079e8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180079e8f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180079ea4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180079ea4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180079ee0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180079ee0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180079ef3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180079ef3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079eb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079eb2`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180079f8a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180079f98`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180079f8a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180079f98`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180079f2a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180079f2a`

## pseudocode

```c
__int64 __fastcall wil::GetImpersonationTokenForClientOfObject_nothrow(__int64 a1, __int64 a2, void **a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  bool v7; // bl
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rax
  const char *v11; // r9
  __int64 v12; // rdx
  unsigned int v13; // edi
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-18h]
  TOKEN_TYPE TokenTypea; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v17; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+20h] BYREF

  v17 = 0;
  v4 = CoImpersonateClientOfObject(a1, &v17);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x157,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
      (const char *)(unsigned int)v4,
      TokenType);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
      (const char *)v5,
      TokenTypea);
    return v5;
  }
  v7 = v17 != 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    a3,
    0);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, a3) )
    goto LABEL_17;
  LastError = GetLastError();
  if ( !v7 && LastError == 1008 )
  {
    TokenHandle = 0;
    wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
    {
      v12 = 386;
LABEL_11:
      v5 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v12,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
             v11);
      wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      return v5;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      a3,
      0);
    if ( !DuplicateTokenEx(TokenHandle, 8u, 0, SecurityImpersonation, TokenImpersonation, a3) )
    {
      v12 = 388;
      goto LABEL_11;
    }
    wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return 0;
  }
  if ( !LastError )
  {
LABEL_17:
    if ( v7 )
      CoRevertToSelf();
    return 0;
  }
  v13 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x188,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
          (const char *)LastError,
          TokenType);
  if ( v7 )
    CoRevertToSelf();
  return v13;
}

```

## disassembly

```asm
0x180079e18  mov     rax, rsp
0x180079e1b  mov     [rax+8], rbx
0x180079e1f  mov     [rax+10h], edx
0x180079e22  push    rdi
0x180079e23  sub     rsp, 30h
0x180079e27  lea     rdx, [rax+10h]
0x180079e2b  mov     dword ptr [rax+10h], 0
0x180079e32  mov     rdi, r8
0x180079e35  call    cs:__imp_CoImpersonateClientOfObject
0x180079e3b  mov     ebx, eax
0x180079e3d  test    eax, eax
0x180079e3f  jns     short loc_180079E7A
0x180079e41  mov     rcx, [rsp+38h]; this
0x180079e46  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x180079e4d  mov     r9d, eax; char *
0x180079e50  mov     edx, 157h; void *
0x180079e55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079e5a  mov     rcx, [rsp+38h]; this
0x180079e5f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x180079e66  mov     r9d, ebx; char *
0x180079e69  mov     edx, 177h; void *
0x180079e6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079e73  mov     eax, ebx
0x180079e75  jmp     loc_180079FA0
0x180079e7a  xor     bl, bl
0x180079e7c  cmp     [rsp+38h+arg_8], 0
0x180079e81  jz      short loc_180079E85
0x180079e83  mov     bl, 1
0x180079e85  xor     edx, edx
0x180079e87  mov     rcx, rdi
0x180079e8a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180079e8f  call    cs:__imp_GetCurrentThread
0x180079e95  mov     edx, 8; DesiredAccess
0x180079e9a  mov     r9, rdi; TokenHandle
0x180079e9d  mov     rcx, rax; ThreadHandle
0x180079ea0  lea     r8d, [rdx-7]; OpenAsSelf
0x180079ea4  call    cs:__imp_OpenThreadToken
0x180079eaa  test    eax, eax
0x180079eac  jnz     loc_180079F94
0x180079eb2  call    cs:__imp_GetLastError
0x180079eb8  test    bl, bl
0x180079eba  jnz     loc_180079F67
0x180079ec0  cmp     eax, 3F0h
0x180079ec5  jnz     loc_180079F67
0x180079ecb  xor     edx, edx
0x180079ecd  mov     [rsp+38h+TokenHandle], 0
0x180079ed6  lea     rcx, [rsp+38h+TokenHandle]
0x180079edb  call    ?reset@?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180079ee0  call    cs:__imp_GetCurrentProcess
0x180079ee6  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180079eeb  mov     edx, 0Ah; DesiredAccess
0x180079ef0  mov     rcx, rax; ProcessHandle
0x180079ef3  call    cs:__imp_OpenProcessToken
0x180079ef9  test    eax, eax
0x180079efb  jnz     short loc_180079F04
0x180079efd  mov     edx, 182h
0x180079f02  jmp     short loc_180079F39
0x180079f04  xor     edx, edx
0x180079f06  mov     rcx, rdi
0x180079f09  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180079f0e  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x180079f13  mov     r9d, 2; ImpersonationLevel
0x180079f19  mov     [rsp+38h+phNewToken], rdi; phNewToken
0x180079f1e  xor     r8d, r8d; lpTokenAttributes
0x180079f21  mov     [rsp+38h+TokenType], r9d; TokenType
0x180079f26  lea     edx, [r9+6]; dwDesiredAccess
0x180079f2a  call    cs:__imp_DuplicateTokenEx
0x180079f30  test    eax, eax
0x180079f32  jnz     short loc_180079F5B
0x180079f34  mov     edx, 184h; void *
0x180079f39  mov     rcx, [rsp+38h]; this
0x180079f3e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x180079f45  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180079f4a  lea     rcx, [rsp+38h+TokenHandle]
0x180079f4f  mov     ebx, eax
0x180079f51  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180079f56  jmp     loc_180079E73
0x180079f5b  lea     rcx, [rsp+38h+TokenHandle]
0x180079f60  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180079f65  jmp     short loc_180079F9E
0x180079f67  test    eax, eax
0x180079f69  jz      short loc_180079F94
0x180079f6b  mov     rcx, [rsp+38h]; this
0x180079f70  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x180079f77  mov     r9d, eax; char *
0x180079f7a  mov     edx, 188h; void *
0x180079f7f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180079f84  mov     edi, eax
0x180079f86  test    bl, bl
0x180079f88  jz      short loc_180079F90
0x180079f8a  call    cs:__imp_CoRevertToSelf
0x180079f90  mov     eax, edi
0x180079f92  jmp     short loc_180079FA0
0x180079f94  test    bl, bl
0x180079f96  jz      short loc_180079F9E
0x180079f98  call    cs:__imp_CoRevertToSelf
0x180079f9e  xor     eax, eax
0x180079fa0  mov     rbx, [rsp+38h+arg_0]
0x180079fa5  add     rsp, 30h
0x180079fa9  pop     rdi
0x180079faa  retn
```
