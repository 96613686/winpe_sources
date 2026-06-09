# IsProcessConsideredForegroundForDatasense(void)

- ea: `0x180005410`
- end: `0x1800054ac`
- name: `?IsProcessConsideredForegroundForDatasense@@YAHXZ`
- size: `156`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014ca0`

## callees

- `0x180005410`
- `0x180008a90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000547f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000547f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005450`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005450`
- `RMCLIENT!RmAccessCheck` at `0x180005492`
- `RMCLIENT!RmAccessCheck` at `0x180005492`

## pseudocode

```c
_BOOL8 IsProcessConsideredForegroundForDatasense(void)
{
  DWORD CurrentProcessId; // eax
  int TokenInformation; // [rsp+30h] [rbp-18h] BYREF
  DWORD ReturnLength; // [rsp+34h] [rbp-14h] BYREF

  TokenInformation = 0;
  ReturnLength = 0;
  if ( !GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength)
    || !TokenInformation )
  {
    return 1;
  }
  CurrentProcessId = GetCurrentProcessId();
  return (unsigned int)RmAccessCheck(30, CurrentProcessId) != -2147024891;
}

```

## disassembly

```asm
0x180005410  push    rbx
0x180005412  sub     rsp, 40h
0x180005416  mov     rax, cs:__security_cookie
0x18000541d  xor     rax, rsp
0x180005420  mov     [rsp+48h+var_10], rax
0x180005425  xor     ebx, ebx
0x180005427  lea     rax, [rsp+48h+var_14]
0x18000542c  mov     r9d, 4; TokenInformationLength
0x180005432  mov     [rsp+48h+TokenInformation], ebx
0x180005436  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x18000543b  mov     [rsp+48h+var_14], ebx
0x18000543f  mov     edx, 1Dh; TokenInformationClass
0x180005444  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180005449  mov     rcx, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x180005450  call    cs:__imp_GetTokenInformation
0x180005457  nop     dword ptr [rax+rax+00h]
0x18000545c  test    eax, eax
0x18000545e  jz      short loc_180005466
0x180005460  cmp     [rsp+48h+TokenInformation], ebx
0x180005464  jnz     short loc_18000547F
0x180005466  mov     eax, 1
0x18000546b  mov     rcx, [rsp+48h+var_10]
0x180005470  xor     rcx, rsp; StackCookie
0x180005473  call    __security_check_cookie
0x180005478  add     rsp, 40h
0x18000547c  pop     rbx
0x18000547d  retn
0x18000547f  call    cs:__imp_GetCurrentProcessId
0x180005486  nop     dword ptr [rax+rax+00h]
0x18000548b  mov     edx, eax
0x18000548d  mov     ecx, 1Eh
0x180005492  call    cs:__imp_RmAccessCheck
0x180005499  nop     dword ptr [rax+rax+00h]
0x18000549e  cmp     eax, 80070005h
0x1800054a3  mov     ecx, ebx
0x1800054a5  setnz   cl
0x1800054a8  mov     eax, ecx
0x1800054aa  jmp     short loc_18000546B
```
