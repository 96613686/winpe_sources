# CThreadContext::PrivilegeEnabled(ulong)

- ea: `0x180005d48`
- end: `0x180005e02`
- name: `?PrivilegeEnabled@CThreadContext@@QEAAHK@Z`
- size: `186`
- prototype: `__int64 __fastcall(CThreadContext *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005b78`

## callees

- `0x180005d48`
- `0x18000e640`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180005d90`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180005d90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180005d74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180005d74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ddb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ddb`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x180005dcb`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x180005dcb`

## pseudocode

```c
_BOOL8 __fastcall CThreadContext::PrivilegeEnabled(CThreadContext *this, DWORD a2)
{
  HANDLE CurrentThread; // rax
  BOOL pfResult; // [rsp+20h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-28h] BYREF
  struct _PRIVILEGE_SET RequiredPrivileges; // [rsp+30h] [rbp-20h] BYREF

  pfResult = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    RequiredPrivileges.Control = 1;
    RequiredPrivileges.PrivilegeCount = 1;
    RequiredPrivileges.Privilege[0].Luid.LowPart = a2;
    RequiredPrivileges.Privilege[0].Luid.HighPart = 0;
    RequiredPrivileges.Privilege[0].Attributes = 2;
    PrivilegeCheck(TokenHandle, &RequiredPrivileges, &pfResult);
    CloseHandle(TokenHandle);
  }
  return pfResult;
}

```

## disassembly

```asm
0x180005d48  mov     [rsp-8+arg_0], rbx
0x180005d4d  push    rbp
0x180005d4e  mov     rbp, rsp
0x180005d51  sub     rsp, 50h
0x180005d55  mov     rax, cs:__security_cookie
0x180005d5c  xor     rax, rsp
0x180005d5f  mov     [rbp+var_8], rax
0x180005d63  mov     ebx, edx
0x180005d65  mov     [rbp+pfResult], 0
0x180005d6c  mov     [rbp+TokenHandle], 0
0x180005d74  call    cs:__imp_GetCurrentThread
0x180005d7b  nop     dword ptr [rax+rax+00h]
0x180005d80  mov     edx, 8; DesiredAccess
0x180005d85  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180005d89  mov     rcx, rax; ThreadHandle
0x180005d8c  lea     r8d, [rdx-7]; OpenAsSelf
0x180005d90  call    cs:__imp_OpenThreadToken
0x180005d97  nop     dword ptr [rax+rax+00h]
0x180005d9c  test    eax, eax
0x180005d9e  jz      short loc_180005DE7
0x180005da0  mov     rcx, [rbp+TokenHandle]; ClientToken
0x180005da4  lea     r8, [rbp+pfResult]; pfResult
0x180005da8  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x180005dac  mov     [rbp+RequiredPrivileges.Control], 1
0x180005db3  mov     [rbp+RequiredPrivileges.PrivilegeCount], 1
0x180005dba  mov     [rbp+RequiredPrivileges.Privilege.Luid.LowPart], ebx
0x180005dbd  mov     [rbp+RequiredPrivileges.Privilege.Luid.HighPart], 0
0x180005dc4  mov     [rbp+RequiredPrivileges.Privilege.Attributes], 2
0x180005dcb  call    cs:__imp_PrivilegeCheck
0x180005dd2  nop     dword ptr [rax+rax+00h]
0x180005dd7  mov     rcx, [rbp+TokenHandle]; hObject
0x180005ddb  call    cs:__imp_CloseHandle
0x180005de2  nop     dword ptr [rax+rax+00h]
0x180005de7  mov     eax, [rbp+pfResult]
0x180005dea  mov     rcx, [rbp+var_8]
0x180005dee  xor     rcx, rsp; StackCookie
0x180005df1  call    __security_check_cookie
0x180005df6  mov     rbx, [rsp+50h+arg_0]
0x180005dfb  add     rsp, 50h
0x180005dff  pop     rbp
0x180005e00  retn
```
