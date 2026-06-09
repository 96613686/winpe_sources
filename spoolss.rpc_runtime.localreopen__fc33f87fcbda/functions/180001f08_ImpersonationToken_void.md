# ImpersonationToken(void *)

- ea: `0x180001f08`
- end: `0x180001f91`
- name: `?ImpersonationToken@@YAHPEAX@Z`
- size: `137`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001e98`

## callees

- `0x180001f08`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180001f55`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180001f55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f2e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001f72`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001f72`

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
0x180001f08  mov     rax, rsp
0x180001f0b  mov     [rax+8], rbx
0x180001f0f  mov     [rax+20h], rsi
0x180001f13  push    rdi
0x180001f14  sub     rsp, 30h
0x180001f18  mov     rbx, rcx
0x180001f1b  mov     dword ptr [rax+10h], 0
0x180001f22  mov     edi, 1
0x180001f27  mov     dword ptr [rax+18h], 0
0x180001f2e  call    cs:__imp_GetLastError
0x180001f35  nop     dword ptr [rax+rax+00h]
0x180001f3a  lea     r9d, [rdi+3]; TokenInformationLength
0x180001f3e  mov     rcx, rbx; TokenHandle
0x180001f41  mov     esi, eax
0x180001f43  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180001f48  lea     rax, [rsp+38h+arg_10]
0x180001f4d  lea     edx, [rdi+7]; TokenInformationClass
0x180001f50  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180001f55  call    cs:__imp_GetTokenInformation
0x180001f5c  nop     dword ptr [rax+rax+00h]
0x180001f61  test    eax, eax
0x180001f63  jz      short loc_180001F70
0x180001f65  xor     edi, edi
0x180001f67  cmp     [rsp+38h+TokenInformation], 2
0x180001f6c  setz    dil
0x180001f70  mov     ecx, esi; dwErrCode
0x180001f72  call    cs:__imp_SetLastError
0x180001f79  nop     dword ptr [rax+rax+00h]
0x180001f7e  mov     rbx, [rsp+38h+arg_0]
0x180001f83  mov     eax, edi
0x180001f85  mov     rsi, [rsp+38h+arg_18]
0x180001f8a  add     rsp, 30h
0x180001f8e  pop     rdi
0x180001f8f  retn
```
