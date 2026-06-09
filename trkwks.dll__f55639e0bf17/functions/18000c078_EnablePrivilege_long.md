# EnablePrivilege(long)

- ea: `0x18000c078`
- end: `0x18000c12d`
- name: `?EnablePrivilege@@YAHJ@Z`
- size: `181`
- prototype: `_BOOL8 __fastcall()`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800012c8`

## callees

- `0x18000c078`
- `0x180011000`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c0f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c0f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c10d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c10d`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000c0f1`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000c0f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c0a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c0a4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000c0b5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000c0b5`

## pseudocode

```c
_BOOL8 __fastcall EnablePrivilege()
{
  BOOL v0; // ebx
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-20h] BYREF

  TokenHandle = (void *)-1LL;
  NewState = 0;
  v0 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Luid = (LUID)18LL;
    NewState.Privileges[0].Attributes = 2;
    AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, 0, 0);
    v0 = GetLastError() == 0;
  }
  if ( TokenHandle != (void *)-1LL )
    CloseHandle(TokenHandle);
  return v0;
}

```

## disassembly

```asm
0x18000c078  mov     [rsp+arg_0], rbx
0x18000c07d  push    rdi
0x18000c07e  sub     rsp, 50h
0x18000c082  mov     rax, cs:__security_cookie
0x18000c089  xor     rax, rsp
0x18000c08c  mov     [rsp+58h+var_10], rax
0x18000c091  xorps   xmm0, xmm0
0x18000c094  mov     [rsp+58h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18000c09d  movups  xmmword ptr [rsp+58h+NewState.PrivilegeCount], xmm0
0x18000c0a2  xor     ebx, ebx
0x18000c0a4  call    cs:__imp_GetCurrentProcess
0x18000c0aa  mov     rcx, rax; ProcessHandle
0x18000c0ad  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x18000c0b2  lea     edx, [rbx+28h]; DesiredAccess
0x18000c0b5  call    cs:__imp_OpenProcessToken
0x18000c0bb  test    eax, eax
0x18000c0bd  jz      short loc_18000C102
0x18000c0bf  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18000c0c4  lea     edi, [rbx+1]
0x18000c0c7  mov     [rsp+58h+ReturnLength], rbx; ReturnLength
0x18000c0cc  lea     r9d, [rbx+10h]; BufferLength
0x18000c0d0  lea     r8, [rsp+58h+NewState]; NewState
0x18000c0d5  mov     [rsp+58h+NewState.PrivilegeCount], edi
0x18000c0d9  xor     edx, edx; DisableAllPrivileges
0x18000c0db  mov     qword ptr [rsp+58h+NewState.Privileges.Luid.LowPart], 12h
0x18000c0e4  mov     [rsp+58h+NewState.Privileges.Attributes], 2
0x18000c0ec  mov     [rsp+58h+PreviousState], rbx; PreviousState
0x18000c0f1  call    cs:__imp_AdjustTokenPrivileges
0x18000c0f7  call    cs:__imp_GetLastError
0x18000c0fd  test    eax, eax
0x18000c0ff  cmovz   ebx, edi
0x18000c102  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18000c107  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c10b  jz      short loc_18000C113
0x18000c10d  call    cs:__imp_CloseHandle
0x18000c113  mov     eax, ebx
0x18000c115  mov     rcx, [rsp+58h+var_10]
0x18000c11a  xor     rcx, rsp; StackCookie
0x18000c11d  call    __security_check_cookie
0x18000c122  mov     rbx, [rsp+58h+arg_0]
0x18000c127  add     rsp, 50h
0x18000c12b  pop     rdi
0x18000c12c  retn
```
