# GetCurrentLuid

- ea: `0x18002b904`
- end: `0x18002ba1b`
- name: `GetCurrentLuid`
- size: `279`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800164a0`
- `0x180017854`

## callees

- `0x18002b904`
- `0x180034510`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002b9f2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002b9f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002b94a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002b94a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002b9dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002b9dd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002b968`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002b968`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b9aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b9aa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002b996`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002b996`

## pseudocode

```c
BOOL __fastcall GetCurrentLuid(_QWORD *a1)
{
  HANDLE CurrentThread; // rax
  char v3; // di
  BOOL result; // eax
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-50h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-48h] BYREF
  _OWORD TokenInformation[3]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v9; // [rsp+70h] [rbp-10h]

  TokenHandle = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  v9 = 0;
  ReturnLength = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    CurrentProcess = GetCurrentProcess();
    result = OpenProcessToken(CurrentProcess, 8u, &TokenHandle);
    if ( !result )
      goto LABEL_7;
  }
  v3 = 0;
  if ( GetTokenInformation(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength) )
  {
    v3 = 1;
    *a1 = *((_QWORD *)&TokenInformation[0] + 1);
  }
  result = CloseHandle(TokenHandle);
  if ( !v3 )
LABEL_7:
    *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x18002b904  mov     [rsp-8+arg_8], rbx
0x18002b909  mov     [rsp-8+arg_10], rdi
0x18002b90e  push    rbp
0x18002b90f  mov     rbp, rsp
0x18002b912  sub     rsp, 80h
0x18002b919  mov     rax, cs:__security_cookie
0x18002b920  xor     rax, rsp
0x18002b923  mov     [rbp+var_8], rax
0x18002b927  xorps   xmm0, xmm0
0x18002b92a  mov     [rbp+TokenHandle], 0
0x18002b932  xor     eax, eax
0x18002b934  mov     rbx, rcx
0x18002b937  movups  [rbp+TokenInformation], xmm0
0x18002b93b  mov     [rbp+var_10], rax
0x18002b93f  movups  [rbp+var_30], xmm0
0x18002b943  mov     [rbp+var_48], eax
0x18002b946  movups  [rbp+var_20], xmm0
0x18002b94a  call    cs:__imp_GetCurrentThread
0x18002b951  nop     dword ptr [rax+rax+00h]
0x18002b956  mov     edi, 8
0x18002b95b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18002b95f  mov     rcx, rax; ThreadHandle
0x18002b962  mov     edx, edi; DesiredAccess
0x18002b964  lea     r8d, [rdi-7]; OpenAsSelf
0x18002b968  call    cs:__imp_OpenThreadToken
0x18002b96f  nop     dword ptr [rax+rax+00h]
0x18002b974  test    eax, eax
0x18002b976  jz      short loc_18002B9DD
0x18002b978  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002b97c  lea     rax, [rbp+var_48]
0x18002b980  mov     r9d, 38h ; '8'; TokenInformationLength
0x18002b986  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x18002b98b  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18002b98f  xor     dil, dil
0x18002b992  lea     edx, [r9-2Eh]; TokenInformationClass
0x18002b996  call    cs:__imp_GetTokenInformation
0x18002b99d  nop     dword ptr [rax+rax+00h]
0x18002b9a2  test    eax, eax
0x18002b9a4  jnz     short loc_18002BA0F
0x18002b9a6  mov     rcx, [rbp+TokenHandle]; hObject
0x18002b9aa  call    cs:__imp_CloseHandle
0x18002b9b1  nop     dword ptr [rax+rax+00h]
0x18002b9b6  test    dil, dil
0x18002b9b9  jz      short loc_18002BA06
0x18002b9bb  mov     rcx, [rbp+var_8]
0x18002b9bf  xor     rcx, rsp; StackCookie
0x18002b9c2  call    __security_check_cookie
0x18002b9c7  lea     r11, [rsp+80h+var_s0]
0x18002b9cf  mov     rbx, [r11+18h]
0x18002b9d3  mov     rdi, [r11+20h]
0x18002b9d7  mov     rsp, r11
0x18002b9da  pop     rbp
0x18002b9db  retn
0x18002b9dd  call    cs:__imp_GetCurrentProcess
0x18002b9e4  nop     dword ptr [rax+rax+00h]
0x18002b9e9  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18002b9ed  mov     edx, edi; DesiredAccess
0x18002b9ef  mov     rcx, rax; ProcessHandle
0x18002b9f2  call    cs:__imp_OpenProcessToken
0x18002b9f9  nop     dword ptr [rax+rax+00h]
0x18002b9fe  test    eax, eax
0x18002ba00  jnz     loc_18002B978
0x18002ba06  mov     qword ptr [rbx], 0
0x18002ba0d  jmp     short loc_18002B9BB
0x18002ba0f  mov     rax, qword ptr [rbp+TokenInformation+8]
0x18002ba13  mov     dil, 1
0x18002ba16  mov     [rbx], rax
0x18002ba19  jmp     short loc_18002B9A6
```
