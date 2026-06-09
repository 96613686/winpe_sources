# GetClientLogonId

- ea: `0x1800143e0`
- end: `0x180014460`
- name: `GetClientLogonId`
- size: `128`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014468`

## callees

- `0x1800143e0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001444d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001444d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800143fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800143fd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014412`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014412`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001443a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001443a`

## pseudocode

```c
__int64 GetClientLogonId()
{
  HANDLE CurrentThread; // rax
  unsigned int TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  TokenInformation = 0;
  TokenHandle = 0;
  ReturnLength = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
    return 0;
  if ( !GetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
    TokenInformation = 0;
  CloseHandle(TokenHandle);
  return TokenInformation;
}

```

## disassembly

```asm
0x1800143e0  sub     rsp, 38h
0x1800143e4  mov     [rsp+38h+TokenInformation], 0
0x1800143ec  mov     [rsp+38h+TokenHandle], 0
0x1800143f5  mov     [rsp+38h+arg_8], 0
0x1800143fd  call    cs:__imp_GetCurrentThread
0x180014403  xor     r8d, r8d; OpenAsSelf
0x180014406  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x18001440b  mov     rcx, rax; ThreadHandle
0x18001440e  lea     edx, [r8+8]; DesiredAccess
0x180014412  call    cs:__imp_OpenThreadToken
0x180014418  test    eax, eax
0x18001441a  jz      short loc_180014459
0x18001441c  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180014421  lea     rax, [rsp+38h+arg_8]
0x180014426  mov     r9d, 4; TokenInformationLength
0x18001442c  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180014431  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180014436  lea     edx, [r9+8]; TokenInformationClass
0x18001443a  call    cs:__imp_GetTokenInformation
0x180014440  test    eax, eax
0x180014442  jnz     short loc_180014448
0x180014444  mov     [rsp+38h+TokenInformation], eax
0x180014448  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18001444d  call    cs:__imp_CloseHandle
0x180014453  mov     eax, [rsp+38h+TokenInformation]
0x180014457  jmp     short loc_18001445B
0x180014459  xor     eax, eax
0x18001445b  add     rsp, 38h
0x18001445f  retn
```
