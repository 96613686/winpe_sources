# RpcpCreateResourceManager(AUTHZ_RESOURCE_MANAGER_HANDLE__ * *)

- ea: `0x18000b8d0`
- end: `0x18000baa3`
- name: `?RpcpCreateResourceManager@@YAJPEAPEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@@Z`
- size: `467`
- prototype: `__int64 __fastcall(PAUTHZ_RESOURCE_MANAGER_HANDLE phAuthzResourceManager)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000b878`

## callees

- `0x18000b8d0`
- `0x1800ceda0`

## import_xrefs

- `ntdll!NtPrivilegeCheck` at `0x18000b9ef`
- `ntdll!NtPrivilegeCheck` at `0x18000b9ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b98f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b98f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ba01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ba6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ba01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ba6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b967`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b967`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000b92f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000b92f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b911`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b911`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000b97f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000b97f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000ba60`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000ba60`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000b94b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000b94b`
- `ext-ms-win-authz-context-l1-1-0!AuthzInitializeResourceManager` at `0x18000ba34`
- `ext-ms-win-authz-context-l1-1-0!AuthzInitializeResourceManager` at `0x18000ba34`

## pseudocode

```c
__int64 __fastcall RpcpCreateResourceManager(PAUTHZ_RESOURCE_MANAGER_HANDLE phAuthzResourceManager)
{
  HANDLE CurrentThread; // rax
  DWORD v3; // esi
  DWORD v4; // edi
  BOOL v5; // r15d
  void *v6; // r14
  DWORD v7; // ebx
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  NTSTATUS v11; // ebx
  unsigned __int8 Result[8]; // [rsp+30h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-28h] BYREF
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+40h] [rbp-20h] BYREF

  TokenHandle = 0;
  memset(&RequiredPrivileges, 0, sizeof(RequiredPrivileges));
  Result[0] = 0;
  CurrentThread = GetCurrentThread();
  v3 = 1;
  v4 = 5;
  v5 = OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle);
  if ( v5 )
  {
    v6 = TokenHandle;
    v7 = 0;
    v5 = RevertToSelf();
  }
  else
  {
    v6 = 0;
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError != 1008 && LastError != 5 )
      return 14;
  }
  if ( v5 || v7 != 5 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      RequiredPrivileges.PrivilegeCount = 1;
      RequiredPrivileges.Control = 1;
      RequiredPrivileges.Privilege[0].Luid = (LUID)21LL;
      RequiredPrivileges.Privilege[0].Attributes = 2;
      v11 = NtPrivilegeCheck(TokenHandle, &RequiredPrivileges, Result);
      CloseHandle(TokenHandle);
      if ( v11 < 0 )
        goto LABEL_17;
      if ( Result[0] )
        v3 = 0;
    }
    else if ( GetLastError() != 5 )
    {
      v4 = 14;
      goto LABEL_17;
    }
  }
  if ( AuthzInitializeResourceManager(v3, 0, 0, 0, &Src, phAuthzResourceManager) )
    v4 = 0;
  else
    v4 = GetLastError();
LABEL_17:
  if ( v6 )
  {
    SetThreadToken(0, v6);
    CloseHandle(v6);
  }
  return v4;
}

```

## disassembly

```asm
0x18000b8d0  mov     [rsp-28h+arg_8], rbx
0x18000b8d5  mov     [rsp-28h+arg_10], rsi
0x18000b8da  push    rbp
0x18000b8db  push    rdi
0x18000b8dc  push    r12
0x18000b8de  push    r14
0x18000b8e0  push    r15
0x18000b8e2  mov     rbp, rsp
0x18000b8e5  sub     rsp, 60h
0x18000b8e9  mov     rax, cs:__security_cookie
0x18000b8f0  xor     rax, rsp
0x18000b8f3  mov     [rbp+var_8], rax
0x18000b8f7  xor     eax, eax
0x18000b8f9  mov     [rbp+TokenHandle], 0
0x18000b901  xorps   xmm0, xmm0
0x18000b904  mov     [rbp+RequiredPrivileges.Privilege.Attributes], eax
0x18000b907  movups  xmmword ptr [rbp+RequiredPrivileges.PrivilegeCount], xmm0
0x18000b90b  mov     [rbp+Result], al
0x18000b90e  mov     r12, rcx
0x18000b911  call    cs:__imp_GetCurrentThread
0x18000b918  nop     dword ptr [rax+rax+00h]
0x18000b91d  mov     esi, 1
0x18000b922  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18000b926  mov     rcx, rax; ThreadHandle
0x18000b929  mov     r8d, esi; OpenAsSelf
0x18000b92c  lea     edx, [rsi+0Bh]; DesiredAccess
0x18000b92f  call    cs:__imp_OpenThreadToken
0x18000b936  nop     dword ptr [rax+rax+00h]
0x18000b93b  lea     edi, [rsi+4]
0x18000b93e  mov     r15d, eax
0x18000b941  test    eax, eax
0x18000b943  jz      short loc_18000B9A9
0x18000b945  mov     r14, [rbp+TokenHandle]
0x18000b949  xor     ebx, ebx
0x18000b94b  call    cs:__imp_RevertToSelf
0x18000b952  nop     dword ptr [rax+rax+00h]
0x18000b957  mov     r15d, eax
0x18000b95a  test    r15d, r15d
0x18000b95d  jnz     short loc_18000B967
0x18000b95f  cmp     ebx, edi
0x18000b961  jz      loc_18000BA19
0x18000b967  call    cs:__imp_GetCurrentProcess
0x18000b96e  nop     dword ptr [rax+rax+00h]
0x18000b973  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000b977  mov     edx, 8; DesiredAccess
0x18000b97c  mov     rcx, rax; ProcessHandle
0x18000b97f  call    cs:__imp_OpenProcessToken
0x18000b986  nop     dword ptr [rax+rax+00h]
0x18000b98b  test    eax, eax
0x18000b98d  jnz     short loc_18000B9CE
0x18000b98f  call    cs:__imp_GetLastError
0x18000b996  nop     dword ptr [rax+rax+00h]
0x18000b99b  cmp     eax, edi
0x18000b99d  jz      short loc_18000BA19
0x18000b99f  mov     edi, 0Eh
0x18000b9a4  jmp     loc_18000BA56
0x18000b9a9  xor     r14d, r14d
0x18000b9ac  call    cs:__imp_GetLastError
0x18000b9b3  nop     dword ptr [rax+rax+00h]
0x18000b9b8  mov     ebx, eax
0x18000b9ba  cmp     eax, 3F0h
0x18000b9bf  jz      short loc_18000B95A
0x18000b9c1  cmp     eax, edi
0x18000b9c3  jz      short loc_18000B95A
0x18000b9c5  lea     eax, [r14+0Eh]
0x18000b9c9  jmp     loc_18000BA7D
0x18000b9ce  mov     rcx, [rbp+TokenHandle]; ClientToken
0x18000b9d2  lea     r8, [rbp+Result]; Result
0x18000b9d6  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x18000b9da  mov     [rbp+RequiredPrivileges.PrivilegeCount], esi
0x18000b9dd  mov     [rbp+RequiredPrivileges.Control], esi
0x18000b9e0  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.LowPart], 15h
0x18000b9e8  mov     [rbp+RequiredPrivileges.Privilege.Attributes], 2
0x18000b9ef  call    cs:__imp_NtPrivilegeCheck
0x18000b9f6  nop     dword ptr [rax+rax+00h]
0x18000b9fb  mov     rcx, [rbp+TokenHandle]; hObject
0x18000b9ff  mov     ebx, eax
0x18000ba01  call    cs:__imp_CloseHandle
0x18000ba08  nop     dword ptr [rax+rax+00h]
0x18000ba0d  test    ebx, ebx
0x18000ba0f  js      short loc_18000BA56
0x18000ba11  xor     eax, eax
0x18000ba13  cmp     [rbp+Result], al
0x18000ba16  cmovnz  esi, eax
0x18000ba19  lea     rax, Src
0x18000ba20  mov     [rsp+60h+phAuthzResourceManager], r12; phAuthzResourceManager
0x18000ba25  xor     r9d, r9d; pfnFreeDynamicGroups
0x18000ba28  mov     [rsp+60h+szResourceManagerName], rax; szResourceManagerName
0x18000ba2d  xor     r8d, r8d; pfnComputeDynamicGroups
0x18000ba30  xor     edx, edx; pfnDynamicAccessCheck
0x18000ba32  mov     ecx, esi; Flags
0x18000ba34  call    cs:__imp_AuthzInitializeResourceManager
0x18000ba3b  nop     dword ptr [rax+rax+00h]
0x18000ba40  test    eax, eax
0x18000ba42  jnz     short loc_18000BA54
0x18000ba44  call    cs:__imp_GetLastError
0x18000ba4b  nop     dword ptr [rax+rax+00h]
0x18000ba50  mov     edi, eax
0x18000ba52  jmp     short loc_18000BA56
0x18000ba54  xor     edi, edi
0x18000ba56  test    r14, r14
0x18000ba59  jz      short loc_18000BA7B
0x18000ba5b  mov     rdx, r14; Token
0x18000ba5e  xor     ecx, ecx; Thread
0x18000ba60  call    cs:__imp_SetThreadToken
0x18000ba67  nop     dword ptr [rax+rax+00h]
0x18000ba6c  mov     rcx, r14; hObject
0x18000ba6f  call    cs:__imp_CloseHandle
0x18000ba76  nop     dword ptr [rax+rax+00h]
0x18000ba7b  mov     eax, edi
0x18000ba7d  mov     rcx, [rbp+var_8]
0x18000ba81  xor     rcx, rsp; StackCookie
0x18000ba84  call    __security_check_cookie
0x18000ba89  lea     r11, [rsp+60h+var_s0]
0x18000ba8e  mov     rbx, [r11+38h]
0x18000ba92  mov     rsi, [r11+40h]
0x18000ba96  mov     rsp, r11
0x18000ba99  pop     r15
0x18000ba9b  pop     r14
0x18000ba9d  pop     r12
0x18000ba9f  pop     rdi
0x18000baa0  pop     rbp
0x18000baa1  retn
```
