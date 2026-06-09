# GetCallerTokenFromComCall(void * *)

- ea: `0x18000ca64`
- end: `0x18000cbcb`
- name: `?GetCallerTokenFromComCall@@YAJPEAPEAX@Z`
- size: `359`
- prototype: `__int64 __fastcall(PHANDLE phNewToken)`
- caller_count: `22`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c8d4`
- `0x18000c988`
- `0x180025cf4`
- `0x1800391d4`
- `0x18003a088`
- `0x18004180c`
- `0x180042820`
- `0x1800458e0`
- `0x180048bc0`
- `0x180064d8c`
- `0x180066e60`
- `0x180067f60`
- `0x180069a44`
- `0x180069d4c`
- `0x18007ecf0`
- `0x1800949c0`
- `0x1800b8948`
- `0x1800b8998`
- `0x1800b89e8`
- `0x1800ca320`
- `0x1800cce54`
- `0x1800ccf40`

## callees

- `0x180008b10`
- `0x18000acdc`
- `0x18000ca64`
- `0x18004e58c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000ca91`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000ca91`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000cadb`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000cadb`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000cb8b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000cb8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000cab0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000cb24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000cab0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000cb24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000cb4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000cb4f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000cb62`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000cb62`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000cac5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000cb39`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000cac5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000cb39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cbc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cbc0`

## string_xrefs

- `0x18000cb00`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000cb12`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000cb9e`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000cbae`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetCallerTokenFromComCall(PHANDLE phNewToken)
{
  HRESULT v2; // eax
  HANDLE v3; // rax
  const char *v4; // r9
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  const char *v8; // r9
  const char *v9; // r9
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  char v12; // [rsp+50h] [rbp+8h]
  void *TokenHandle; // [rsp+58h] [rbp+10h] BYREF

  v12 = 0;
  TokenHandle = 0;
  *phNewToken = 0;
  v2 = CoImpersonateClient();
  if ( v2 == -2147417833 )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, phNewToken) )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &TokenHandle,
        0);
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x56,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
          v8);
      if ( !DuplicateTokenEx(TokenHandle, 0, 0, SecurityImpersonation, TokenImpersonation, phNewToken) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x5C,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
          v9);
    }
  }
  else
  {
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x61,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
        (const char *)(unsigned int)v2,
        TokenType);
    v12 = 1;
    v3 = GetCurrentThread();
    if ( !OpenThreadToken(v3, 8u, 1, phNewToken) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x63,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
        v4);
  }
  if ( v12 )
    CoRevertToSelf();
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x18000ca64  push    rbx
0x18000ca66  sub     rsp, 40h
0x18000ca6a  mov     rbx, rcx
0x18000ca6d  mov     [rsp+48h+arg_0], 0
0x18000ca72  mov     [rsp+48h+TokenHandle], 0
0x18000ca7b  mov     qword ptr [rcx], 0
0x18000ca82  lea     rax, [rsp+48h+arg_0]
0x18000ca87  mov     [rsp+48h+var_18], rax
0x18000ca8c  mov     [rsp+48h+var_10], 1
0x18000ca91  call    cs:__imp_CoImpersonateClient
0x18000ca97  cmp     eax, 80010117h
0x18000ca9c  jz      loc_18000CB24
0x18000caa2  mov     rcx, [rsp+48h]; this
0x18000caa7  test    eax, eax
0x18000caa9  js      short loc_18000CAFD
0x18000caab  mov     [rsp+48h+arg_0], 1
0x18000cab0  call    cs:__imp_GetCurrentThread
0x18000cab6  mov     rcx, rax; ThreadHandle
0x18000cab9  mov     r9, rbx; TokenHandle
0x18000cabc  mov     edx, 8; DesiredAccess
0x18000cac1  lea     r8d, [rdx-7]; OpenAsSelf
0x18000cac5  call    cs:__imp_OpenThreadToken
0x18000cacb  mov     rcx, [rsp+48h]; this
0x18000cad0  test    eax, eax
0x18000cad2  jz      short loc_18000CB12
0x18000cad4  cmp     [rsp+48h+arg_0], 0
0x18000cad9  jz      short loc_18000CAE2
0x18000cadb  call    cs:__imp_CoRevertToSelf
0x18000cae1  nop
0x18000cae2  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x18000cae7  lea     rax, [rcx-1]
0x18000caeb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000caef  jbe     loc_18000CBC0
0x18000caf5  xor     eax, eax
0x18000caf7  add     rsp, 40h
0x18000cafb  pop     rbx
0x18000cafc  retn
0x18000cafd  mov     r9d, eax; char *
0x18000cb00  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x18000cb07  mov     edx, 61h ; 'a'; void *
0x18000cb0c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000cb12  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x18000cb19  mov     edx, 63h ; 'c'; void *
0x18000cb1e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000cb24  call    cs:__imp_GetCurrentThread
0x18000cb2a  mov     rcx, rax; ThreadHandle
0x18000cb2d  mov     r9, rbx; TokenHandle
0x18000cb30  mov     edx, 8; DesiredAccess
0x18000cb35  lea     r8d, [rdx-7]; OpenAsSelf
0x18000cb39  call    cs:__imp_OpenThreadToken
0x18000cb3f  test    eax, eax
0x18000cb41  jnz     short loc_18000CAD4
0x18000cb43  xor     edx, edx
0x18000cb45  lea     rcx, [rsp+48h+TokenHandle]
0x18000cb4a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18000cb4f  call    cs:__imp_GetCurrentProcess
0x18000cb55  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x18000cb5a  mov     edx, 0Ah; DesiredAccess
0x18000cb5f  mov     rcx, rax; ProcessHandle
0x18000cb62  call    cs:__imp_OpenProcessToken
0x18000cb68  mov     rcx, [rsp+48h]; this
0x18000cb6d  test    eax, eax
0x18000cb6f  jz      short loc_18000CBAE
0x18000cb71  mov     [rsp+48h+phNewToken], rbx; phNewToken
0x18000cb76  mov     r9d, 2; ImpersonationLevel
0x18000cb7c  mov     [rsp+48h+TokenType], r9d; TokenType
0x18000cb81  xor     r8d, r8d; lpTokenAttributes
0x18000cb84  xor     edx, edx; dwDesiredAccess
0x18000cb86  mov     rcx, [rsp+48h+TokenHandle]; hExistingToken
0x18000cb8b  call    cs:__imp_DuplicateTokenEx
0x18000cb91  mov     rcx, [rsp+48h]; this
0x18000cb96  test    eax, eax
0x18000cb98  jnz     loc_18000CAD4
0x18000cb9e  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x18000cba5  lea     edx, [rax+5Ch]; void *
0x18000cba8  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000cbae  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x18000cbb5  mov     edx, 56h ; 'V'; void *
0x18000cbba  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000cbc0  call    cs:__imp_CloseHandle
0x18000cbc6  jmp     loc_18000CAF5
```
