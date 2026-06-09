# CLuaSettingsChecktoid::GetTokenType(void)

- ea: `0x180003cd8`
- end: `0x180003d88`
- name: `?GetTokenType@CLuaSettingsChecktoid@@CAKXZ`
- size: `176`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180003920`
- `0x180003a80`

## callees

- `0x180003cd8`
- `0x180003d90`
- `0x180005650`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d80`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180003cfc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180003cfc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003ce7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003ce7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d5d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003d3a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003d3a`

## pseudocode

```c
__int64 CLuaSettingsChecktoid::GetTokenType(void)
{
  HANDLE CurrentThread; // rax
  unsigned int v1; // ebx
  int TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    if ( (unsigned int)CLuaSettingsChecktoid::IsTokenBuiltInAdministrator(TokenHandle) )
    {
      v1 = 0;
    }
    else
    {
      ReturnLength = 0;
      TokenInformation = 0;
      v1 = 1;
      if ( GetTokenInformation(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength) )
      {
        if ( TokenInformation == 1 && !(unsigned int)RunningAsAdministrator() )
          v1 = 2;
      }
      else
      {
        GetLastError();
      }
    }
    CloseHandle(TokenHandle);
  }
  else
  {
    v1 = 0;
    GetLastError();
  }
  return v1;
}

```

## disassembly

```asm
0x180003cd8  push    rbx
0x180003cda  sub     rsp, 30h
0x180003cde  mov     [rsp+38h+TokenHandle], 0
0x180003ce7  call    cs:__imp_GetCurrentThread
0x180003ced  xor     r8d, r8d; OpenAsSelf
0x180003cf0  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180003cf5  mov     rcx, rax; ThreadHandle
0x180003cf8  lea     edx, [r8+8]; DesiredAccess
0x180003cfc  call    cs:__imp_OpenThreadToken
0x180003d02  test    eax, eax
0x180003d04  jz      short loc_180003D7E
0x180003d06  mov     rcx, [rsp+38h+TokenHandle]; void *
0x180003d0b  call    ?IsTokenBuiltInAdministrator@CLuaSettingsChecktoid@@CAHPEAX@Z; CLuaSettingsChecktoid::IsTokenBuiltInAdministrator(void *)
0x180003d10  test    eax, eax
0x180003d12  jnz     short loc_180003D73
0x180003d14  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180003d19  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180003d1e  mov     r9d, 4; TokenInformationLength
0x180003d24  mov     [rsp+38h+arg_8], eax
0x180003d28  mov     [rsp+38h+TokenInformation], eax
0x180003d2c  lea     rax, [rsp+38h+arg_8]
0x180003d31  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180003d36  lea     edx, [r9+0Eh]; TokenInformationClass
0x180003d3a  call    cs:__imp_GetTokenInformation
0x180003d40  mov     ebx, 1
0x180003d45  test    eax, eax
0x180003d47  jz      short loc_180003D6B
0x180003d49  cmp     [rsp+38h+TokenInformation], ebx
0x180003d4d  jnz     short loc_180003D58
0x180003d4f  call    RunningAsAdministrator
0x180003d54  test    eax, eax
0x180003d56  jz      short loc_180003D77
0x180003d58  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180003d5d  call    cs:__imp_CloseHandle
0x180003d63  mov     eax, ebx
0x180003d65  add     rsp, 30h
0x180003d69  pop     rbx
0x180003d6a  retn
0x180003d6b  call    cs:__imp_GetLastError
0x180003d71  jmp     short loc_180003D58
0x180003d73  xor     ebx, ebx
0x180003d75  jmp     short loc_180003D58
0x180003d77  mov     ebx, 2
0x180003d7c  jmp     short loc_180003D58
0x180003d7e  xor     ebx, ebx
0x180003d80  call    cs:__imp_GetLastError
0x180003d86  jmp     short loc_180003D63
```
