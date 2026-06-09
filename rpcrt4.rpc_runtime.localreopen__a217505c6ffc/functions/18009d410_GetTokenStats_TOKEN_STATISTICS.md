# GetTokenStats(_TOKEN_STATISTICS *)

- ea: `0x18009d410`
- end: `0x18009d4b5`
- name: `?GetTokenStats@@YAJPEAU_TOKEN_STATISTICS@@@Z`
- size: `165`
- prototype: `__int64 __fastcall(struct _TOKEN_STATISTICS *TokenInformation)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18009d3a8`

## callees

- `0x18009d410`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x18009d446`
- `ntdll!NtOpenThreadToken` at `0x18009d446`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d4a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d4a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009d489`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009d489`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009d42a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009d42a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009d472`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009d472`

## pseudocode

```c
__int64 __fastcall GetTokenStats(struct _TOKEN_STATISTICS *TokenInformation)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  TokenHandle = 0;
  ReturnLength = 0;
  CurrentThread = GetCurrentThread();
  if ( NtOpenThreadToken(CurrentThread, 0x20008u, 1u, &TokenHandle) < 0 )
    return 5;
  if ( GetTokenInformation(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength) )
    LastError = 0;
  else
    LastError = GetLastError();
  CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x18009d410  push    rbx
0x18009d412  sub     rsp, 30h
0x18009d416  mov     rbx, rcx
0x18009d419  mov     [rsp+38h+TokenHandle], 0
0x18009d422  mov     [rsp+38h+arg_8], 0
0x18009d42a  call    cs:__imp_GetCurrentThread
0x18009d431  nop     dword ptr [rax+rax+00h]
0x18009d436  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x18009d43b  mov     r8b, 1; OpenAsSelf
0x18009d43e  mov     rcx, rax; ThreadHandle
0x18009d441  mov     edx, 20008h; DesiredAccess
0x18009d446  call    cs:__imp_NtOpenThreadToken
0x18009d44d  nop     dword ptr [rax+rax+00h]
0x18009d452  test    eax, eax
0x18009d454  js      short loc_18009D49E
0x18009d456  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18009d45b  lea     rax, [rsp+38h+arg_8]
0x18009d460  mov     r9d, 38h ; '8'; TokenInformationLength
0x18009d466  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18009d46b  mov     r8, rbx; TokenInformation
0x18009d46e  lea     edx, [r9-2Eh]; TokenInformationClass
0x18009d472  call    cs:__imp_GetTokenInformation
0x18009d479  nop     dword ptr [rax+rax+00h]
0x18009d47e  test    eax, eax
0x18009d480  jz      short loc_18009D4A5
0x18009d482  xor     ebx, ebx
0x18009d484  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18009d489  call    cs:__imp_CloseHandle
0x18009d490  nop     dword ptr [rax+rax+00h]
0x18009d495  mov     eax, ebx
0x18009d497  add     rsp, 30h
0x18009d49b  pop     rbx
0x18009d49c  retn
0x18009d49e  mov     eax, 5
0x18009d4a3  jmp     short loc_18009D497
0x18009d4a5  call    cs:__imp_GetLastError
0x18009d4ac  nop     dword ptr [rax+rax+00h]
0x18009d4b1  mov     ebx, eax
0x18009d4b3  jmp     short loc_18009D484
```
