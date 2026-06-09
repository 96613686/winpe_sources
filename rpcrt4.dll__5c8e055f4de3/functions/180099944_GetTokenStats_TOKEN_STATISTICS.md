# GetTokenStats(_TOKEN_STATISTICS *)

- ea: `0x180099944`
- end: `0x1800999ca`
- name: `?GetTokenStats@@YAJPEAU_TOKEN_STATISTICS@@@Z`
- size: `134`
- prototype: `__int64 __fastcall(struct _TOKEN_STATISTICS *TokenInformation)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800998e0`

## callees

- `0x180099944`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x180099974`
- `ntdll!NtOpenThreadToken` at `0x180099974`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800999c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800999c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800999ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800999ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009995e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009995e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009999a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009999a`

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
0x180099944  push    rbx
0x180099946  sub     rsp, 30h
0x18009994a  mov     rbx, rcx
0x18009994d  mov     [rsp+38h+TokenHandle], 0
0x180099956  mov     [rsp+38h+arg_8], 0
0x18009995e  call    cs:__imp_GetCurrentThread
0x180099964  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180099969  mov     r8b, 1; OpenAsSelf
0x18009996c  mov     rcx, rax; ThreadHandle
0x18009996f  mov     edx, 20008h; DesiredAccess
0x180099974  call    cs:__imp_NtOpenThreadToken
0x18009997a  test    eax, eax
0x18009997c  js      short loc_1800999B9
0x18009997e  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180099983  lea     rax, [rsp+38h+arg_8]
0x180099988  mov     r9d, 38h ; '8'; TokenInformationLength
0x18009998e  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180099993  mov     r8, rbx; TokenInformation
0x180099996  lea     edx, [r9-2Eh]; TokenInformationClass
0x18009999a  call    cs:__imp_GetTokenInformation
0x1800999a0  test    eax, eax
0x1800999a2  jz      short loc_1800999C0
0x1800999a4  xor     ebx, ebx
0x1800999a6  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1800999ab  call    cs:__imp_CloseHandle
0x1800999b1  mov     eax, ebx
0x1800999b3  add     rsp, 30h
0x1800999b7  pop     rbx
0x1800999b8  retn
0x1800999b9  mov     eax, 5
0x1800999be  jmp     short loc_1800999B3
0x1800999c0  call    cs:__imp_GetLastError
0x1800999c6  mov     ebx, eax
0x1800999c8  jmp     short loc_1800999A6
```
