# pAcquirePrivilege(long)

- ea: `0x140056398`
- end: `0x140056464`
- name: `?pAcquirePrivilege@@YAHJ@Z`
- size: `204`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140025e3c`

## callees

- `0x140056398`
- `0x140091560`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140056403`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140056403`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140056432`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140056432`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400563d8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400563d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400563c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400563c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140056444`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140056444`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x14005642a`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x14005642a`

## pseudocode

```c
BOOL __fastcall pAcquirePrivilege(int a1)
{
  LUID v1; // rbx
  HANDLE CurrentProcess; // rax
  BOOL result; // eax
  BOOL v4; // ebx
  BOOL v5; // edi
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-20h] BYREF

  v1 = (LUID)a1;
  NewState = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  result = OpenProcessToken(CurrentProcess, 0x2000000u, &TokenHandle);
  if ( result )
  {
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Luid = v1;
    NewState.Privileges[0].Attributes = 2;
    SetLastError(0);
    v4 = AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0);
    v5 = 0;
    if ( !GetLastError() )
      v5 = v4;
    CloseHandle(TokenHandle);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x140056398  mov     [rsp+arg_0], rbx
0x14005639d  push    rdi
0x14005639e  sub     rsp, 50h
0x1400563a2  mov     rax, cs:__security_cookie
0x1400563a9  xor     rax, rsp
0x1400563ac  mov     [rsp+58h+var_10], rax
0x1400563b1  xorps   xmm0, xmm0
0x1400563b4  movsxd  rbx, ecx
0x1400563b7  movups  xmmword ptr [rsp+58h+NewState.PrivilegeCount], xmm0
0x1400563bc  mov     [rsp+58h+TokenHandle], 0
0x1400563c5  call    cs:__imp_GetCurrentProcess
0x1400563cb  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x1400563d0  mov     edx, 2000000h; DesiredAccess
0x1400563d5  mov     rcx, rax; ProcessHandle
0x1400563d8  call    cs:__imp_OpenProcessToken
0x1400563de  test    eax, eax
0x1400563e0  jz      short loc_14005644C
0x1400563e2  mov     rcx, rbx
0x1400563e5  mov     [rsp+58h+NewState.PrivilegeCount], 1
0x1400563ed  shr     rcx, 20h
0x1400563f1  mov     [rsp+58h+NewState.Privileges.Luid.HighPart], ecx
0x1400563f5  xor     ecx, ecx; dwErrCode
0x1400563f7  mov     [rsp+58h+NewState.Privileges.Luid.LowPart], ebx
0x1400563fb  mov     [rsp+58h+NewState.Privileges.Attributes], 2
0x140056403  call    cs:__imp_SetLastError
0x140056409  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x14005640e  lea     r8, [rsp+58h+NewState]; NewState
0x140056413  xor     r9d, r9d; BufferLength
0x140056416  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x14005641f  xor     edx, edx; DisableAllPrivileges
0x140056421  mov     [rsp+58h+PreviousState], 0; PreviousState
0x14005642a  call    cs:__imp_AdjustTokenPrivileges
0x140056430  mov     ebx, eax
0x140056432  call    cs:__imp_GetLastError
0x140056438  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x14005643d  xor     edi, edi
0x14005643f  test    eax, eax
0x140056441  cmovz   edi, ebx
0x140056444  call    cs:__imp_CloseHandle
0x14005644a  mov     eax, edi
0x14005644c  mov     rcx, [rsp+58h+var_10]
0x140056451  xor     rcx, rsp; StackCookie
0x140056454  call    __security_check_cookie
0x140056459  mov     rbx, [rsp+58h+arg_0]
0x14005645e  add     rsp, 50h
0x140056462  pop     rdi
0x140056463  retn
```
