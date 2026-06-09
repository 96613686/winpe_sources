# NetpAccessCheck2

- ea: `0x1800426b4`
- end: `0x1800427d1`
- name: `NetpAccessCheck2`
- size: `285`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a390`

## callees

- `0x18001deb0`
- `0x1800426b4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180042782`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180042782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042737`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042737`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004272d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004272d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180042716`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180042716`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800427a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800427a5`
- `RPCRT4!RpcImpersonateClient` at `0x180042708`
- `RPCRT4!RpcImpersonateClient` at `0x180042708`
- `RPCRT4!RpcRevertToSelf` at `0x180042795`
- `RPCRT4!RpcRevertToSelf` at `0x180042795`

## pseudocode

```c
RPC_STATUS __fastcall NetpAccessCheck2(
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        __int64 a2,
        struct _GENERIC_MAPPING *a3)
{
  RPC_STATUS result; // eax
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  DWORD PrivilegeSetLength; // [rsp+40h] [rbp-C0h] BYREF
  WINBOOL AccessStatus; // [rsp+44h] [rbp-BCh] BYREF
  DWORD GrantedAccess; // [rsp+48h] [rbp-B8h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-B0h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+60h] [rbp-A0h] BYREF

  TokenHandle = 0;
  GrantedAccess = 0;
  AccessStatus = 0;
  PrivilegeSetLength = 0;
  result = RpcImpersonateClient(0);
  if ( !result )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle)
      && (PrivilegeSetLength = 500,
          AccessCheck(
            pSecurityDescriptor,
            TokenHandle,
            0x20000u,
            a3,
            &PrivilegeSet,
            &PrivilegeSetLength,
            &GrantedAccess,
            &AccessStatus))
      && AccessStatus )
    {
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
    }
    RpcRevertToSelf();
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    return LastError;
  }
  return result;
}

```

## disassembly

```asm
0x1800426b4  mov     [rsp-8+arg_8], rbx
0x1800426b9  mov     [rsp-8+arg_18], rdi
0x1800426be  push    rbp
0x1800426bf  lea     rbp, [rsp-170h]
0x1800426c7  sub     rsp, 270h
0x1800426ce  mov     rax, cs:__security_cookie
0x1800426d5  xor     rax, rsp
0x1800426d8  mov     [rbp+170h+var_10], rax
0x1800426df  mov     rbx, rcx
0x1800426e2  mov     [rsp+270h+TokenHandle], 0
0x1800426eb  xor     ecx, ecx; BindingHandle
0x1800426ed  mov     [rsp+270h+var_228], 0
0x1800426f5  mov     rdi, r8
0x1800426f8  mov     [rsp+270h+var_22C], 0
0x180042700  mov     [rsp+270h+var_230], 0
0x180042708  call    cs:__imp_RpcImpersonateClient
0x18004270e  test    eax, eax
0x180042710  jnz     loc_1800427AD
0x180042716  call    cs:__imp_GetCurrentThread
0x18004271c  mov     edx, 8; DesiredAccess
0x180042721  lea     r9, [rsp+270h+TokenHandle]; TokenHandle
0x180042726  mov     rcx, rax; ThreadHandle
0x180042729  lea     r8d, [rdx-7]; OpenAsSelf
0x18004272d  call    cs:__imp_OpenThreadToken
0x180042733  test    eax, eax
0x180042735  jnz     short loc_180042741
0x180042737  call    cs:__imp_GetLastError
0x18004273d  mov     ebx, eax
0x18004273f  jmp     short loc_180042795
0x180042741  mov     rdx, [rsp+270h+TokenHandle]; ClientToken
0x180042746  lea     rax, [rsp+270h+var_22C]
0x18004274b  mov     [rsp+270h+AccessStatus], rax; AccessStatus
0x180042750  mov     r9, rdi; GenericMapping
0x180042753  lea     rax, [rsp+270h+var_228]
0x180042758  mov     [rsp+270h+var_230], 1F4h
0x180042760  mov     [rsp+270h+GrantedAccess], rax; GrantedAccess
0x180042765  mov     r8d, 20000h; DesiredAccess
0x18004276b  lea     rax, [rsp+270h+var_230]
0x180042770  mov     rcx, rbx; pSecurityDescriptor
0x180042773  mov     [rsp+270h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180042778  lea     rax, [rsp+270h+var_210]
0x18004277d  mov     [rsp+270h+PrivilegeSet], rax; PrivilegeSet
0x180042782  call    cs:__imp_AccessCheck
0x180042788  test    eax, eax
0x18004278a  jz      short loc_180042737
0x18004278c  cmp     [rsp+270h+var_22C], 0
0x180042791  jz      short loc_180042737
0x180042793  xor     ebx, ebx
0x180042795  call    cs:__imp_RpcRevertToSelf
0x18004279b  mov     rcx, [rsp+270h+TokenHandle]; hObject
0x1800427a0  test    rcx, rcx
0x1800427a3  jz      short loc_1800427AB
0x1800427a5  call    cs:__imp_CloseHandle
0x1800427ab  mov     eax, ebx
0x1800427ad  mov     rcx, [rbp+170h+var_10]
0x1800427b4  xor     rcx, rsp; StackCookie
0x1800427b7  call    __security_check_cookie
0x1800427bc  lea     r11, [rsp+270h+var_s0]
0x1800427c4  mov     rbx, [r11+18h]
0x1800427c8  mov     rdi, [r11+28h]
0x1800427cc  mov     rsp, r11
0x1800427cf  pop     rbp
0x1800427d0  retn
```
