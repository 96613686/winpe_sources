# CLuaSettingsChecktoid::IsRebootNeeded(void)

- ea: `0x180003e40`
- end: `0x180003f78`
- name: `?IsRebootNeeded@CLuaSettingsChecktoid@@CAHXZ`
- size: `312`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180034b30`

## callees

- `0x180003e40`
- `0x180005650`
- `0x18003fc30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f70`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180003e7e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180003e7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003e68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003e68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f55`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180003ef1`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180003ef1`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180003f01`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180003f01`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003ede`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003f36`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003ede`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003f36`

## pseudocode

```c
__int64 CLuaSettingsChecktoid::IsRebootNeeded(void)
{
  unsigned int v0; // ebx
  HANDLE CurrentThread; // rax
  PUCHAR SidSubAuthorityCount; // rax
  DWORD ReturnLength; // [rsp+30h] [rbp-98h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-90h] BYREF
  DWORD v6[4]; // [rsp+40h] [rbp-88h] BYREF
  PSID TokenInformation[12]; // [rsp+50h] [rbp-78h] BYREF

  TokenHandle = 0;
  v0 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    ReturnLength = 0;
    if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength) )
    {
      SidSubAuthorityCount = GetSidSubAuthorityCount(TokenInformation[0]);
      if ( *GetSidSubAuthority(TokenInformation[0], (unsigned int)*SidSubAuthorityCount - 1) == 500 )
      {
LABEL_10:
        CloseHandle(TokenHandle);
        return v0;
      }
    }
    else
    {
      GetLastError();
    }
    v6[0] = 0;
    ReturnLength = 0;
    if ( GetTokenInformation(TokenHandle, TokenElevationType, &ReturnLength, 4u, v6) )
    {
      if ( ReturnLength == 1 && (unsigned int)RunningAsAdministrator() )
        v0 = 1;
    }
    else
    {
      GetLastError();
    }
    goto LABEL_10;
  }
  GetLastError();
  return v0;
}

```

## disassembly

```asm
0x180003e40  mov     [rsp+arg_8], rbx
0x180003e45  push    rdi
0x180003e46  sub     rsp, 0C0h
0x180003e4d  mov     rax, cs:__security_cookie
0x180003e54  xor     rax, rsp
0x180003e57  mov     [rsp+0C8h+var_18], rax
0x180003e5f  xor     edi, edi
0x180003e61  mov     [rsp+0C8h+TokenHandle], rdi
0x180003e66  mov     ebx, edi
0x180003e68  call    cs:__imp_GetCurrentThread
0x180003e6e  lea     r9, [rsp+0C8h+TokenHandle]; TokenHandle
0x180003e73  xor     r8d, r8d; OpenAsSelf
0x180003e76  mov     rcx, rax; ThreadHandle
0x180003e79  mov     edx, 8; DesiredAccess
0x180003e7e  call    cs:__imp_OpenThreadToken
0x180003e84  test    eax, eax
0x180003e86  jnz     short loc_180003EB1
0x180003e88  call    cs:__imp_GetLastError
0x180003e8e  mov     eax, ebx
0x180003e90  mov     rcx, [rsp+0C8h+var_18]
0x180003e98  xor     rcx, rsp; StackCookie
0x180003e9b  call    __security_check_cookie
0x180003ea0  mov     rbx, [rsp+0C8h+arg_8]
0x180003ea8  add     rsp, 0C0h
0x180003eaf  pop     rdi
0x180003eb0  retn
0x180003eb1  mov     rcx, [rsp+0C8h+TokenHandle]; TokenHandle
0x180003eb6  lea     rax, [rsp+0C8h+var_98]
0x180003ebb  mov     [rsp+0C8h+arg_0], rsi
0x180003ec3  lea     r8, [rsp+0C8h+TokenInformation]; TokenInformation
0x180003ec8  mov     esi, 1
0x180003ecd  mov     [rsp+0C8h+var_98], edi
0x180003ed1  mov     edx, esi; TokenInformationClass
0x180003ed3  mov     [rsp+0C8h+ReturnLength], rax; ReturnLength
0x180003ed8  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180003ede  call    cs:__imp_GetTokenInformation
0x180003ee4  test    eax, eax
0x180003ee6  jz      loc_180003F70
0x180003eec  mov     rcx, [rsp+0C8h+TokenInformation]; pSid
0x180003ef1  call    cs:__imp_GetSidSubAuthorityCount
0x180003ef7  mov     rcx, [rsp+0C8h+TokenInformation]; pSid
0x180003efc  movzx   edx, byte ptr [rax]
0x180003eff  dec     edx; nSubAuthority
0x180003f01  call    cs:__imp_GetSidSubAuthority
0x180003f07  cmp     dword ptr [rax], 1F4h
0x180003f0d  jz      short loc_180003F50
0x180003f0f  mov     rcx, [rsp+0C8h+TokenHandle]; TokenHandle
0x180003f14  lea     rax, [rsp+0C8h+var_88]
0x180003f19  mov     r9d, 4; TokenInformationLength
0x180003f1f  mov     [rsp+0C8h+ReturnLength], rax; ReturnLength
0x180003f24  lea     r8, [rsp+0C8h+var_98]; TokenInformation
0x180003f29  mov     [rsp+0C8h+var_88], edi
0x180003f2d  mov     edx, 12h; TokenInformationClass
0x180003f32  mov     [rsp+0C8h+var_98], edi
0x180003f36  call    cs:__imp_GetTokenInformation
0x180003f3c  test    eax, eax
0x180003f3e  jz      short loc_180003F68
0x180003f40  cmp     [rsp+0C8h+var_98], esi
0x180003f44  jnz     short loc_180003F50
0x180003f46  call    RunningAsAdministrator
0x180003f4b  test    eax, eax
0x180003f4d  cmovnz  ebx, esi
0x180003f50  mov     rcx, [rsp+0C8h+TokenHandle]; hObject
0x180003f55  call    cs:__imp_CloseHandle
0x180003f5b  mov     rsi, [rsp+0C8h+arg_0]
0x180003f63  jmp     loc_180003E8E
0x180003f68  call    cs:__imp_GetLastError
0x180003f6e  jmp     short loc_180003F50
0x180003f70  call    cs:__imp_GetLastError
0x180003f76  jmp     short loc_180003F0F
```
