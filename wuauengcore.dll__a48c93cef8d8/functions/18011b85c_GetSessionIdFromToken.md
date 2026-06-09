# GetSessionIdFromToken

- ea: `0x18011b85c`
- end: `0x18011b98f`
- name: `GetSessionIdFromToken`
- size: `307`
- prototype: `__int64 __fastcall(LPVOID TokenInformation, HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003ded8`
- `0x1801051cc`

## callees

- `0x18000def4`
- `0x18000df20`
- `0x18011b85c`
- `0x180238960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011b8d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011b8d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18011b901`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18011b901`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18011b914`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18011b914`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18011b8ca`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18011b8ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18011b8b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18011b8b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011b8f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011b974`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011b8f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011b974`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18011b944`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18011b944`

## string_xrefs

- `0x18011b892`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`
- `0x18011b958`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`

## pseudocode

```c
__int64 __fastcall GetSessionIdFromToken(LPVOID TokenInformation, HANDLE TokenHandle)
{
  HANDLE v2; // rax
  unsigned int LastError; // ebx
  HANDLE CurrentThread; // rax
  const char *v6; // r9
  __int64 v7; // rdx
  HANDLE CurrentProcess; // rax
  int ReturnLength; // [rsp+20h] [rbp-38h]
  void *TokenHandlea; // [rsp+30h] [rbp-28h] BYREF
  DWORD v12; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v12 = 0;
  v2 = TokenHandle;
  TokenHandlea = 0;
  if ( !TokenInformation )
  {
    LastError = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDE,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
      (const char *)0x80004003LL,
      ReturnLength);
    goto LABEL_16;
  }
  if ( !TokenHandle )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandlea) )
    {
      if ( GetLastError() != 1008 )
      {
        v7 = 228;
LABEL_14:
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)v7,
                      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
                      v6);
        goto LABEL_16;
      }
      if ( TokenHandlea )
      {
        CloseHandle(TokenHandlea);
        TokenHandlea = 0;
      }
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandlea) )
      {
        v7 = 230;
        goto LABEL_14;
      }
    }
    v2 = TokenHandlea;
  }
  if ( !GetTokenInformation(v2, TokenSessionId, TokenInformation, 4u, &v12) )
  {
    v7 = 238;
    goto LABEL_14;
  }
  LastError = 0;
LABEL_16:
  if ( TokenHandlea )
    CloseHandle(TokenHandlea);
  return LastError;
}

```

## disassembly

```asm
0x18011b85c  push    rbx
0x18011b85e  sub     rsp, 50h
0x18011b862  mov     rax, cs:__security_cookie
0x18011b869  xor     rax, rsp
0x18011b86c  mov     [rsp+58h+var_18], rax
0x18011b871  mov     [rsp+58h+var_20], 0
0x18011b879  mov     rax, rdx
0x18011b87c  mov     [rsp+58h+TokenHandle], 0
0x18011b885  mov     rbx, rcx
0x18011b888  test    rcx, rcx
0x18011b88b  jnz     short loc_18011B8B0
0x18011b88d  mov     rcx, [rsp+58h]; this
0x18011b892  lea     r8, aCW1SSrcClientL_45; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18011b899  mov     ebx, 80004003h
0x18011b89e  mov     edx, 0DEh; void *
0x18011b8a3  mov     r9d, ebx; char *
0x18011b8a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011b8ab  jmp     loc_18011B96A
0x18011b8b0  test    rax, rax
0x18011b8b3  jnz     short loc_18011B92A
0x18011b8b5  call    cs:__imp_GetCurrentThread
0x18011b8bb  xor     r8d, r8d; OpenAsSelf
0x18011b8be  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x18011b8c3  mov     rcx, rax; ThreadHandle
0x18011b8c6  lea     edx, [r8+8]; DesiredAccess
0x18011b8ca  call    cs:__imp_OpenThreadToken
0x18011b8d0  test    eax, eax
0x18011b8d2  jnz     short loc_18011B925
0x18011b8d4  call    cs:__imp_GetLastError
0x18011b8da  cmp     eax, 3F0h
0x18011b8df  jz      short loc_18011B8E8
0x18011b8e1  mov     edx, 0E4h
0x18011b8e6  jmp     short loc_18011B953
0x18011b8e8  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18011b8ed  test    rcx, rcx
0x18011b8f0  jz      short loc_18011B901
0x18011b8f2  call    cs:__imp_CloseHandle
0x18011b8f8  mov     [rsp+58h+TokenHandle], 0
0x18011b901  call    cs:__imp_GetCurrentProcess
0x18011b907  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x18011b90c  mov     edx, 8; DesiredAccess
0x18011b911  mov     rcx, rax; ProcessHandle
0x18011b914  call    cs:__imp_OpenProcessToken
0x18011b91a  test    eax, eax
0x18011b91c  jnz     short loc_18011B925
0x18011b91e  mov     edx, 0E6h
0x18011b923  jmp     short loc_18011B953
0x18011b925  mov     rax, [rsp+58h+TokenHandle]
0x18011b92a  mov     r9d, 4; TokenInformationLength
0x18011b930  lea     rcx, [rsp+58h+var_20]
0x18011b935  mov     qword ptr [rsp+58h+ReturnLength], rcx; ReturnLength
0x18011b93a  mov     r8, rbx; TokenInformation
0x18011b93d  mov     rcx, rax; TokenHandle
0x18011b940  lea     edx, [r9+8]; TokenInformationClass
0x18011b944  call    cs:__imp_GetTokenInformation
0x18011b94a  test    eax, eax
0x18011b94c  jnz     short loc_18011B968
0x18011b94e  mov     edx, 0EEh; void *
0x18011b953  mov     rcx, [rsp+58h]; this
0x18011b958  lea     r8, aCW1SSrcClientL_45; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18011b95f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18011b964  mov     ebx, eax
0x18011b966  jmp     short loc_18011B96A
0x18011b968  xor     ebx, ebx
0x18011b96a  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18011b96f  test    rcx, rcx
0x18011b972  jz      short loc_18011B97A
0x18011b974  call    cs:__imp_CloseHandle
0x18011b97a  mov     eax, ebx
0x18011b97c  mov     rcx, [rsp+58h+var_18]
0x18011b981  xor     rcx, rsp; StackCookie
0x18011b984  call    __security_check_cookie
0x18011b989  add     rsp, 50h
0x18011b98d  pop     rbx
0x18011b98e  retn
```
