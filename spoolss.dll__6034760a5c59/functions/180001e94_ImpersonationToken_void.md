# ImpersonationToken(void *)

- ea: `0x180001e94`
- end: `0x180001f0a`
- name: `?ImpersonationToken@@YAHPEAX@Z`
- size: `118`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001e38`

## callees

- `0x180001e94`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180001edb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180001edb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001eba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001eba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001ef2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001ef2`

## pseudocode

```c
_BOOL8 __fastcall ImpersonationToken(HANDLE TokenHandle)
{
  BOOL v2; // edi
  DWORD LastError; // esi
  int TokenInformation; // [rsp+48h] [rbp+10h] BYREF
  DWORD ReturnLength; // [rsp+50h] [rbp+18h] BYREF

  TokenInformation = 0;
  v2 = 1;
  ReturnLength = 0;
  LastError = GetLastError();
  if ( GetTokenInformation(TokenHandle, TokenType, &TokenInformation, 4u, &ReturnLength) )
    v2 = TokenInformation == 2;
  SetLastError(LastError);
  return v2;
}

```

## disassembly

```asm
0x180001e94  mov     rax, rsp
0x180001e97  mov     [rax+8], rbx
0x180001e9b  mov     [rax+20h], rsi
0x180001e9f  push    rdi
0x180001ea0  sub     rsp, 30h
0x180001ea4  mov     rbx, rcx
0x180001ea7  mov     dword ptr [rax+10h], 0
0x180001eae  mov     edi, 1
0x180001eb3  mov     dword ptr [rax+18h], 0
0x180001eba  call    cs:__imp_GetLastError
0x180001ec0  lea     r9d, [rdi+3]; TokenInformationLength
0x180001ec4  mov     rcx, rbx; TokenHandle
0x180001ec7  mov     esi, eax
0x180001ec9  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180001ece  lea     rax, [rsp+38h+arg_10]
0x180001ed3  lea     edx, [rdi+7]; TokenInformationClass
0x180001ed6  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180001edb  call    cs:__imp_GetTokenInformation
0x180001ee1  test    eax, eax
0x180001ee3  jz      short loc_180001EF0
0x180001ee5  xor     edi, edi
0x180001ee7  cmp     [rsp+38h+TokenInformation], 2
0x180001eec  setz    dil
0x180001ef0  mov     ecx, esi; dwErrCode
0x180001ef2  call    cs:__imp_SetLastError
0x180001ef8  mov     rbx, [rsp+38h+arg_0]
0x180001efd  mov     eax, edi
0x180001eff  mov     rsi, [rsp+38h+arg_18]
0x180001f04  add     rsp, 30h
0x180001f08  pop     rdi
0x180001f09  retn
```
