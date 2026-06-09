# RpcpCreateResourceManager(AUTHZ_RESOURCE_MANAGER_HANDLE__ * *)

- ea: `0x18006b58c`
- end: `0x18006b710`
- name: `?RpcpCreateResourceManager@@YAJPEAPEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(PAUTHZ_RESOURCE_MANAGER_HANDLE phAuthzResourceManager)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006b538`

## callees

- `0x18006b58c`
- `0x1800ca140`

## import_xrefs

- `ntdll!NtPrivilegeCheck` at `0x18006b681`
- `ntdll!NtPrivilegeCheck` at `0x18006b681`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b62d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b6c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b62d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b6c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006b68d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006b6e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006b68d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006b6e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006b611`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006b611`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006b5e5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006b5e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006b5cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006b5cd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18006b623`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18006b623`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18006b6da`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18006b6da`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006b5fb`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006b5fb`
- `ext-ms-win-authz-context-l1-1-0!AuthzInitializeResourceManager` at `0x18006b6ba`
- `ext-ms-win-authz-context-l1-1-0!AuthzInitializeResourceManager` at `0x18006b6ba`

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
  struct _PRIVILEGE_SET RequiredPrivileges; // [rsp+40h] [rbp-20h] BYREF

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
0x18006b58c  mov     [rsp-28h+arg_8], rbx
0x18006b591  mov     [rsp-28h+arg_10], rsi
0x18006b596  push    rbp
0x18006b597  push    rdi
0x18006b598  push    r12
0x18006b59a  push    r14
0x18006b59c  push    r15
0x18006b59e  mov     rbp, rsp
0x18006b5a1  sub     rsp, 60h
0x18006b5a5  mov     rax, cs:__security_cookie
0x18006b5ac  xor     rax, rsp
0x18006b5af  mov     [rbp+var_8], rax
0x18006b5b3  xor     eax, eax
0x18006b5b5  mov     [rbp+TokenHandle], 0
0x18006b5bd  xorps   xmm0, xmm0
0x18006b5c0  mov     [rbp+RequiredPrivileges.Privilege.Attributes], eax
0x18006b5c3  movups  xmmword ptr [rbp+RequiredPrivileges.PrivilegeCount], xmm0
0x18006b5c7  mov     [rbp+Result], al
0x18006b5ca  mov     r12, rcx
0x18006b5cd  call    cs:__imp_GetCurrentThread
0x18006b5d3  mov     esi, 1
0x18006b5d8  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18006b5dc  mov     rcx, rax; ThreadHandle
0x18006b5df  mov     r8d, esi; OpenAsSelf
0x18006b5e2  lea     edx, [rsi+0Bh]; DesiredAccess
0x18006b5e5  call    cs:__imp_OpenThreadToken
0x18006b5eb  lea     edi, [rsi+4]
0x18006b5ee  mov     r15d, eax
0x18006b5f1  test    eax, eax
0x18006b5f3  jz      short loc_18006B641
0x18006b5f5  mov     r14, [rbp+TokenHandle]
0x18006b5f9  xor     ebx, ebx
0x18006b5fb  call    cs:__imp_RevertToSelf
0x18006b601  mov     r15d, eax
0x18006b604  test    r15d, r15d
0x18006b607  jnz     short loc_18006B611
0x18006b609  cmp     ebx, edi
0x18006b60b  jz      loc_18006B69F
0x18006b611  call    cs:__imp_GetCurrentProcess
0x18006b617  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18006b61b  mov     edx, 8; DesiredAccess
0x18006b620  mov     rcx, rax; ProcessHandle
0x18006b623  call    cs:__imp_OpenProcessToken
0x18006b629  test    eax, eax
0x18006b62b  jnz     short loc_18006B660
0x18006b62d  call    cs:__imp_GetLastError
0x18006b633  cmp     eax, edi
0x18006b635  jz      short loc_18006B69F
0x18006b637  mov     edi, 0Eh
0x18006b63c  jmp     loc_18006B6D0
0x18006b641  xor     r14d, r14d
0x18006b644  call    cs:__imp_GetLastError
0x18006b64a  mov     ebx, eax
0x18006b64c  cmp     eax, 3F0h
0x18006b651  jz      short loc_18006B604
0x18006b653  cmp     eax, edi
0x18006b655  jz      short loc_18006B604
0x18006b657  lea     eax, [r14+0Eh]
0x18006b65b  jmp     loc_18006B6EB
0x18006b660  mov     rcx, [rbp+TokenHandle]; ClientToken
0x18006b664  lea     r8, [rbp+Result]; Result
0x18006b668  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x18006b66c  mov     [rbp+RequiredPrivileges.PrivilegeCount], esi
0x18006b66f  mov     [rbp+RequiredPrivileges.Control], esi
0x18006b672  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.LowPart], 15h
0x18006b67a  mov     [rbp+RequiredPrivileges.Privilege.Attributes], 2
0x18006b681  call    cs:__imp_NtPrivilegeCheck
0x18006b687  mov     rcx, [rbp+TokenHandle]; hObject
0x18006b68b  mov     ebx, eax
0x18006b68d  call    cs:__imp_CloseHandle
0x18006b693  test    ebx, ebx
0x18006b695  js      short loc_18006B6D0
0x18006b697  xor     eax, eax
0x18006b699  cmp     [rbp+Result], al
0x18006b69c  cmovnz  esi, eax
0x18006b69f  lea     rax, Src
0x18006b6a6  mov     [rsp+60h+phAuthzResourceManager], r12; phAuthzResourceManager
0x18006b6ab  xor     r9d, r9d; pfnFreeDynamicGroups
0x18006b6ae  mov     [rsp+60h+szResourceManagerName], rax; szResourceManagerName
0x18006b6b3  xor     r8d, r8d; pfnComputeDynamicGroups
0x18006b6b6  xor     edx, edx; pfnDynamicAccessCheck
0x18006b6b8  mov     ecx, esi; Flags
0x18006b6ba  call    cs:__imp_AuthzInitializeResourceManager
0x18006b6c0  test    eax, eax
0x18006b6c2  jnz     short loc_18006B6CE
0x18006b6c4  call    cs:__imp_GetLastError
0x18006b6ca  mov     edi, eax
0x18006b6cc  jmp     short loc_18006B6D0
0x18006b6ce  xor     edi, edi
0x18006b6d0  test    r14, r14
0x18006b6d3  jz      short loc_18006B6E9
0x18006b6d5  mov     rdx, r14; Token
0x18006b6d8  xor     ecx, ecx; Thread
0x18006b6da  call    cs:__imp_SetThreadToken
0x18006b6e0  mov     rcx, r14; hObject
0x18006b6e3  call    cs:__imp_CloseHandle
0x18006b6e9  mov     eax, edi
0x18006b6eb  mov     rcx, [rbp+var_8]
0x18006b6ef  xor     rcx, rsp; StackCookie
0x18006b6f2  call    __security_check_cookie
0x18006b6f7  lea     r11, [rsp+60h+var_s0]
0x18006b6fc  mov     rbx, [r11+38h]
0x18006b700  mov     rsi, [r11+40h]
0x18006b704  mov     rsp, r11
0x18006b707  pop     r15
0x18006b709  pop     r14
0x18006b70b  pop     r12
0x18006b70d  pop     rdi
0x18006b70e  pop     rbp
0x18006b70f  retn
```
