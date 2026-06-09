# FvepAcquirePrivilege

- ea: `0x180071c68`
- end: `0x180071e17`
- name: `FvepAcquirePrivilege`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180071e20`

## callees

- `0x180071c68`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x180071cea`
- `KERNEL32!GetCurrentProcess` at `0x180071cea`
- `KERNEL32!GetCurrentThread` at `0x180071cac`
- `KERNEL32!GetCurrentThread` at `0x180071cac`
- `KERNEL32!GetLastError` at `0x180071cd5`
- `KERNEL32!GetLastError` at `0x180071d0f`
- `KERNEL32!GetLastError` at `0x180071d67`
- `KERNEL32!GetLastError` at `0x180071cd5`
- `KERNEL32!GetLastError` at `0x180071d0f`
- `KERNEL32!GetLastError` at `0x180071d67`
- `KERNEL32!CloseHandle` at `0x180071ddd`
- `KERNEL32!CloseHandle` at `0x180071df3`
- `KERNEL32!CloseHandle` at `0x180071ddd`
- `KERNEL32!CloseHandle` at `0x180071df3`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180071da3`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180071da3`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180071d57`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180071d57`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180071cff`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180071cff`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180071db9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180071db9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180071cc5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180071cc5`

## pseudocode

```c
__int64 __fastcall FvepAcquirePrivilege(__int64 a1, _QWORD *a2)
{
  HANDLE CurrentThread; // rax
  void *v4; // rdi
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v7; // ebx
  void *v8; // rcx
  signed int v9; // eax
  void *TokenHandle; // [rsp+30h] [rbp-38h] BYREF
  HANDLE Token; // [rsp+38h] [rbp-30h] BYREF
  _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-28h] BYREF

  TokenHandle = (void *)-1LL;
  NewState.Privileges[0].Attributes = 2;
  Token = (HANDLE)-1LL;
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Luid = (LUID)17LL;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 6u, 0, &TokenHandle) )
  {
    v8 = TokenHandle;
    v4 = TokenHandle;
  }
  else
  {
    if ( GetLastError() != 1008
      || (v4 = 0, CurrentProcess = GetCurrentProcess(), !OpenProcessToken(CurrentProcess, 2u, &TokenHandle)) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
LABEL_15:
      if ( TokenHandle != (void *)-1LL )
        CloseHandle(TokenHandle);
      goto LABEL_17;
    }
    v8 = TokenHandle;
  }
  if ( DuplicateTokenEx(v8, 0x2Cu, 0, SecurityImpersonation, TokenImpersonation, &Token)
    && AdjustTokenPrivileges(Token, 0, &NewState, 0, 0, 0)
    && SetThreadToken(0, Token) )
  {
    v7 = 0;
    *a2 = v4;
  }
  else
  {
    v9 = GetLastError();
    v7 = v9;
    if ( v9 > 0 )
      v7 = (unsigned __int16)v9 | 0x80070000;
  }
  if ( !v4 )
    goto LABEL_15;
LABEL_17:
  if ( Token != (HANDLE)-1LL )
    CloseHandle(Token);
  return v7;
}

```

## disassembly

```asm
0x180071c68  push    rbp
0x180071c6a  push    rbx
0x180071c6b  push    rsi
0x180071c6c  push    rdi
0x180071c6d  mov     rbp, rsp
0x180071c70  sub     rsp, 68h
0x180071c74  mov     rax, cs:__security_cookie
0x180071c7b  xor     rax, rsp
0x180071c7e  mov     [rbp+var_18], rax
0x180071c82  mov     ebx, 2
0x180071c87  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180071c8f  mov     [rbp+NewState.Privileges.Attributes], ebx
0x180071c92  mov     rsi, rdx
0x180071c95  mov     [rbp+Token], 0FFFFFFFFFFFFFFFFh
0x180071c9d  mov     [rbp+NewState.PrivilegeCount], 1
0x180071ca4  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 11h
0x180071cac  call    cs:__imp_GetCurrentThread
0x180071cb3  nop     dword ptr [rax+rax+00h]
0x180071cb8  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180071cbc  xor     r8d, r8d; OpenAsSelf
0x180071cbf  mov     rcx, rax; ThreadHandle
0x180071cc2  lea     edx, [rbx+4]; DesiredAccess
0x180071cc5  call    cs:__imp_OpenThreadToken
0x180071ccc  nop     dword ptr [rax+rax+00h]
0x180071cd1  test    eax, eax
0x180071cd3  jnz     short loc_180071D39
0x180071cd5  call    cs:__imp_GetLastError
0x180071cdc  nop     dword ptr [rax+rax+00h]
0x180071ce1  cmp     eax, 3F0h
0x180071ce6  jnz     short loc_180071D0F
0x180071ce8  xor     edi, edi
0x180071cea  call    cs:__imp_GetCurrentProcess
0x180071cf1  nop     dword ptr [rax+rax+00h]
0x180071cf6  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180071cfa  mov     edx, ebx; DesiredAccess
0x180071cfc  mov     rcx, rax; ProcessHandle
0x180071cff  call    cs:__imp_OpenProcessToken
0x180071d06  nop     dword ptr [rax+rax+00h]
0x180071d0b  test    eax, eax
0x180071d0d  jnz     short loc_180071D33
0x180071d0f  call    cs:__imp_GetLastError
0x180071d16  nop     dword ptr [rax+rax+00h]
0x180071d1b  mov     ebx, eax
0x180071d1d  test    eax, eax
0x180071d1f  jle     loc_180071DD3
0x180071d25  movzx   ebx, ax
0x180071d28  or      ebx, 80070000h
0x180071d2e  jmp     loc_180071DD3
0x180071d33  mov     rcx, [rbp+TokenHandle]
0x180071d37  jmp     short loc_180071D40
0x180071d39  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x180071d3d  mov     rdi, rcx
0x180071d40  xor     r8d, r8d; lpTokenAttributes
0x180071d43  lea     rax, [rbp+Token]
0x180071d47  mov     [rsp+68h+phNewToken], rax; phNewToken
0x180071d4c  mov     r9d, ebx; ImpersonationLevel
0x180071d4f  mov     [rsp+68h+TokenType], ebx; TokenType
0x180071d53  lea     edx, [r8+2Ch]; dwDesiredAccess
0x180071d57  call    cs:__imp_DuplicateTokenEx
0x180071d5e  nop     dword ptr [rax+rax+00h]
0x180071d63  test    eax, eax
0x180071d65  jnz     short loc_180071D84
0x180071d67  call    cs:__imp_GetLastError
0x180071d6e  nop     dword ptr [rax+rax+00h]
0x180071d73  mov     ebx, eax
0x180071d75  test    eax, eax
0x180071d77  jle     short loc_180071DCE
0x180071d79  movzx   ebx, ax
0x180071d7c  or      ebx, 80070000h
0x180071d82  jmp     short loc_180071DCE
0x180071d84  mov     rcx, [rbp+Token]; TokenHandle
0x180071d88  lea     r8, [rbp+NewState]; NewState
0x180071d8c  mov     [rsp+68h+phNewToken], 0; ReturnLength
0x180071d95  xor     r9d, r9d; BufferLength
0x180071d98  xor     edx, edx; DisableAllPrivileges
0x180071d9a  mov     qword ptr [rsp+68h+TokenType], 0; PreviousState
0x180071da3  call    cs:__imp_AdjustTokenPrivileges
0x180071daa  nop     dword ptr [rax+rax+00h]
0x180071daf  test    eax, eax
0x180071db1  jz      short loc_180071D67
0x180071db3  mov     rdx, [rbp+Token]; Token
0x180071db7  xor     ecx, ecx; Thread
0x180071db9  call    cs:__imp_SetThreadToken
0x180071dc0  nop     dword ptr [rax+rax+00h]
0x180071dc5  test    eax, eax
0x180071dc7  jz      short loc_180071D67
0x180071dc9  xor     ebx, ebx
0x180071dcb  mov     [rsi], rdi
0x180071dce  test    rdi, rdi
0x180071dd1  jnz     short loc_180071DE9
0x180071dd3  mov     rcx, [rbp+TokenHandle]; hObject
0x180071dd7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180071ddb  jz      short loc_180071DE9
0x180071ddd  call    cs:__imp_CloseHandle
0x180071de4  nop     dword ptr [rax+rax+00h]
0x180071de9  mov     rcx, [rbp+Token]; hObject
0x180071ded  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180071df1  jz      short loc_180071DFF
0x180071df3  call    cs:__imp_CloseHandle
0x180071dfa  nop     dword ptr [rax+rax+00h]
0x180071dff  mov     eax, ebx
0x180071e01  mov     rcx, [rbp+var_18]
0x180071e05  xor     rcx, rsp; StackCookie
0x180071e08  call    __security_check_cookie
0x180071e0d  add     rsp, 68h
0x180071e11  pop     rdi
0x180071e12  pop     rsi
0x180071e13  pop     rbx
0x180071e14  pop     rbp
0x180071e15  retn
```
