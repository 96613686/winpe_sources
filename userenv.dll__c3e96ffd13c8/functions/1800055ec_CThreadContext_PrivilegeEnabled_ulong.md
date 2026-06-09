# CThreadContext::PrivilegeEnabled(ulong)

- ea: `0x1800055ec`
- end: `0x18000568d`
- name: `?PrivilegeEnabled@CThreadContext@@QEAAHK@Z`
- size: `161`
- prototype: `_BOOL8 __fastcall(CThreadContext *this, DWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000542c`

## callees

- `0x1800055ec`
- `0x18000d9b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000562e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000562e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180005618`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180005618`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000566d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000566d`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x180005663`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x180005663`

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
0x1800055ec  mov     [rsp-8+arg_0], rbx
0x1800055f1  push    rbp
0x1800055f2  mov     rbp, rsp
0x1800055f5  sub     rsp, 50h
0x1800055f9  mov     rax, cs:__security_cookie
0x180005600  xor     rax, rsp
0x180005603  mov     [rbp+var_8], rax
0x180005607  mov     ebx, edx
0x180005609  mov     [rbp+pfResult], 0
0x180005610  mov     [rbp+TokenHandle], 0
0x180005618  call    cs:__imp_GetCurrentThread
0x18000561e  mov     edx, 8; DesiredAccess
0x180005623  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180005627  mov     rcx, rax; ThreadHandle
0x18000562a  lea     r8d, [rdx-7]; OpenAsSelf
0x18000562e  call    cs:__imp_OpenThreadToken
0x180005634  test    eax, eax
0x180005636  jz      short loc_180005673
0x180005638  mov     rcx, [rbp+TokenHandle]; ClientToken
0x18000563c  lea     r8, [rbp+pfResult]; pfResult
0x180005640  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x180005644  mov     [rbp+RequiredPrivileges.Control], 1
0x18000564b  mov     [rbp+RequiredPrivileges.PrivilegeCount], 1
0x180005652  mov     [rbp+RequiredPrivileges.Privilege.Luid.LowPart], ebx
0x180005655  mov     [rbp+RequiredPrivileges.Privilege.Luid.HighPart], 0
0x18000565c  mov     [rbp+RequiredPrivileges.Privilege.Attributes], 2
0x180005663  call    cs:__imp_PrivilegeCheck
0x180005669  mov     rcx, [rbp+TokenHandle]; hObject
0x18000566d  call    cs:__imp_CloseHandle
0x180005673  mov     eax, [rbp+pfResult]
0x180005676  mov     rcx, [rbp+var_8]
0x18000567a  xor     rcx, rsp; StackCookie
0x18000567d  call    __security_check_cookie
0x180005682  mov     rbx, [rsp+50h+arg_0]
0x180005687  add     rsp, 50h
0x18000568b  pop     rbp
0x18000568c  retn
```
