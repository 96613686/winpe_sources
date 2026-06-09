# UmpoRpcIsAdministrator

- ea: `0x180014b38`
- end: `0x180014c71`
- name: `UmpoRpcIsAdministrator`
- size: `313`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c88c`
- `0x1800150f0`

## callees

- `0x18000f3dc`
- `0x180010070`
- `0x180014b38`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180014c22`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180014c22`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180014bfe`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180014bfe`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180014c51`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180014c51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c0c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014b97`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014b97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180014b83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180014b83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014c42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014c42`
- `RPCRT4!RpcRevertToSelf` at `0x180014b9f`
- `RPCRT4!RpcRevertToSelf` at `0x180014b9f`
- `RPCRT4!RpcImpersonateClient` at `0x180014b73`
- `RPCRT4!RpcImpersonateClient` at `0x180014b73`

## pseudocode

```c
__int64 UmpoRpcIsAdministrator()
{
  unsigned int LastError; // ebx
  HANDLE CurrentThread; // rax
  BOOL v2; // edi
  WINBOOL IsMember; // [rsp+60h] [rbp+7h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+Fh] BYREF
  PSID SidToCheck; // [rsp+70h] [rbp+17h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+78h] [rbp+1Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  IsMember = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  TokenHandle = (void *)-1LL;
  LastError = RpcImpersonateClient(0);
  if ( !LastError )
  {
    CurrentThread = GetCurrentThread();
    v2 = OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle);
    LastError = RpcRevertToSelf();
    if ( LastError )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      goto LABEL_11;
    }
    if ( !v2 )
    {
      LastError = GetLastError();
      TokenHandle = (void *)-1LL;
      goto LABEL_13;
    }
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
    {
      SidToCheck = 0;
LABEL_8:
      LastError = GetLastError();
      goto LABEL_11;
    }
    if ( !CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) )
      goto LABEL_8;
    LastError = IsMember == 0 ? 5 : 0;
  }
LABEL_11:
  if ( TokenHandle != (void *)-1LL )
    CloseHandle(TokenHandle);
LABEL_13:
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return LastError;
}

```

## disassembly

```asm
0x180014b38  push    rbp
0x180014b3a  push    rbx
0x180014b3b  push    rsi
0x180014b3c  push    rdi
0x180014b3d  lea     rbp, [rsp-3Fh]
0x180014b42  sub     rsp, 98h
0x180014b49  mov     rax, cs:__security_cookie
0x180014b50  xor     rax, rsp
0x180014b53  mov     [rbp+57h+var_30], rax
0x180014b57  xor     esi, esi
0x180014b59  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180014b5f  xor     ecx, ecx; BindingHandle
0x180014b61  mov     [rbp+57h+IsMember], esi
0x180014b64  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x180014b67  mov     [rbp+57h+SidToCheck], rsi
0x180014b6b  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180014b73  call    cs:__imp_RpcImpersonateClient
0x180014b79  mov     ebx, eax
0x180014b7b  test    eax, eax
0x180014b7d  jnz     loc_180014C38
0x180014b83  call    cs:__imp_GetCurrentThread
0x180014b89  mov     rcx, rax; ThreadHandle
0x180014b8c  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180014b90  lea     edx, [rsi+8]; DesiredAccess
0x180014b93  lea     r8d, [rsi+1]; OpenAsSelf
0x180014b97  call    cs:__imp_OpenThreadToken
0x180014b9d  mov     edi, eax
0x180014b9f  call    cs:__imp_RpcRevertToSelf
0x180014ba5  mov     ebx, eax
0x180014ba7  test    eax, eax
0x180014ba9  jz      short loc_180014BB5
0x180014bab  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180014bb0  jmp     loc_180014C38
0x180014bb5  test    edi, edi
0x180014bb7  jnz     short loc_180014BCB
0x180014bb9  call    cs:__imp_GetLastError
0x180014bbf  mov     ebx, eax
0x180014bc1  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180014bc9  jmp     short loc_180014C48
0x180014bcb  lea     rax, [rbp+57h+SidToCheck]
0x180014bcf  mov     r9d, 220h; nSubAuthority1
0x180014bd5  mov     [rsp+0B0h+pSid], rax; pSid
0x180014bda  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180014bde  mov     [rsp+0B0h+nSubAuthority7], esi; nSubAuthority7
0x180014be2  mov     r8d, 20h ; ' '; nSubAuthority0
0x180014be8  mov     [rsp+0B0h+nSubAuthority6], esi; nSubAuthority6
0x180014bec  mov     dl, 2; nSubAuthorityCount
0x180014bee  mov     [rsp+0B0h+nSubAuthority5], esi; nSubAuthority5
0x180014bf2  mov     [rsp+0B0h+nSubAuthority4], esi; nSubAuthority4
0x180014bf6  mov     [rsp+0B0h+nSubAuthority3], esi; nSubAuthority3
0x180014bfa  mov     [rsp+0B0h+nSubAuthority2], esi; nSubAuthority2
0x180014bfe  call    cs:__imp_AllocateAndInitializeSid
0x180014c04  test    eax, eax
0x180014c06  jnz     short loc_180014C16
0x180014c08  mov     [rbp+57h+SidToCheck], rsi
0x180014c0c  call    cs:__imp_GetLastError
0x180014c12  mov     ebx, eax
0x180014c14  jmp     short loc_180014C38
0x180014c16  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x180014c1a  lea     r8, [rbp+57h+IsMember]; IsMember
0x180014c1e  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180014c22  call    cs:__imp_CheckTokenMembership
0x180014c28  test    eax, eax
0x180014c2a  jz      short loc_180014C0C
0x180014c2c  mov     eax, [rbp+57h+IsMember]
0x180014c2f  neg     eax
0x180014c31  sbb     ebx, ebx
0x180014c33  not     ebx
0x180014c35  and     ebx, 5
0x180014c38  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180014c3c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180014c40  jz      short loc_180014C48
0x180014c42  call    cs:__imp_CloseHandle
0x180014c48  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x180014c4c  test    rcx, rcx
0x180014c4f  jz      short loc_180014C57
0x180014c51  call    cs:__imp_FreeSid
0x180014c57  mov     eax, ebx
0x180014c59  mov     rcx, [rbp+57h+var_30]
0x180014c5d  xor     rcx, rsp; StackCookie
0x180014c60  call    __security_check_cookie
0x180014c65  add     rsp, 98h
0x180014c6c  pop     rdi
0x180014c6d  pop     rsi
0x180014c6e  pop     rbx
0x180014c6f  pop     rbp
0x180014c70  retn
```
