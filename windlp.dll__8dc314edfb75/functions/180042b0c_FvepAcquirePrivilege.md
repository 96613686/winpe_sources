# FvepAcquirePrivilege

- ea: `0x180042b0c`
- end: `0x180042c72`
- name: `FvepAcquirePrivilege`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180042c78`

## callees

- `0x180042b0c`
- `0x18007ed40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180042c27`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180042c27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180042b7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180042b7c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180042b8b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180042b8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180042b50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180042b50`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180042b63`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180042b63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042b6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042b95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042be1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042b6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042b95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042be1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042c45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042c55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042c45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042c55`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180042bd7`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180042bd7`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180042c17`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180042c17`

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
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-28h] BYREF

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
0x180042b0c  push    rbp
0x180042b0e  push    rbx
0x180042b0f  push    rsi
0x180042b10  push    rdi
0x180042b11  mov     rbp, rsp
0x180042b14  sub     rsp, 68h
0x180042b18  mov     rax, cs:__security_cookie
0x180042b1f  xor     rax, rsp
0x180042b22  mov     [rbp+var_18], rax
0x180042b26  mov     ebx, 2
0x180042b2b  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180042b33  mov     [rbp+NewState.Privileges.Attributes], ebx
0x180042b36  mov     rsi, rdx
0x180042b39  mov     [rbp+Token], 0FFFFFFFFFFFFFFFFh
0x180042b41  mov     [rbp+NewState.PrivilegeCount], 1
0x180042b48  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 11h
0x180042b50  call    cs:__imp_GetCurrentThread
0x180042b56  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180042b5a  xor     r8d, r8d; OpenAsSelf
0x180042b5d  mov     rcx, rax; ThreadHandle
0x180042b60  lea     edx, [rbx+4]; DesiredAccess
0x180042b63  call    cs:__imp_OpenThreadToken
0x180042b69  test    eax, eax
0x180042b6b  jnz     short loc_180042BB9
0x180042b6d  call    cs:__imp_GetLastError
0x180042b73  cmp     eax, 3F0h
0x180042b78  jnz     short loc_180042B95
0x180042b7a  xor     edi, edi
0x180042b7c  call    cs:__imp_GetCurrentProcess
0x180042b82  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180042b86  mov     edx, ebx; DesiredAccess
0x180042b88  mov     rcx, rax; ProcessHandle
0x180042b8b  call    cs:__imp_OpenProcessToken
0x180042b91  test    eax, eax
0x180042b93  jnz     short loc_180042BB3
0x180042b95  call    cs:__imp_GetLastError
0x180042b9b  mov     ebx, eax
0x180042b9d  test    eax, eax
0x180042b9f  jle     loc_180042C3B
0x180042ba5  movzx   ebx, ax
0x180042ba8  or      ebx, 80070000h
0x180042bae  jmp     loc_180042C3B
0x180042bb3  mov     rcx, [rbp+TokenHandle]
0x180042bb7  jmp     short loc_180042BC0
0x180042bb9  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x180042bbd  mov     rdi, rcx
0x180042bc0  xor     r8d, r8d; lpTokenAttributes
0x180042bc3  lea     rax, [rbp+Token]
0x180042bc7  mov     [rsp+68h+phNewToken], rax; phNewToken
0x180042bcc  mov     r9d, ebx; ImpersonationLevel
0x180042bcf  mov     [rsp+68h+TokenType], ebx; TokenType
0x180042bd3  lea     edx, [r8+2Ch]; dwDesiredAccess
0x180042bd7  call    cs:__imp_DuplicateTokenEx
0x180042bdd  test    eax, eax
0x180042bdf  jnz     short loc_180042BF8
0x180042be1  call    cs:__imp_GetLastError
0x180042be7  mov     ebx, eax
0x180042be9  test    eax, eax
0x180042beb  jle     short loc_180042C36
0x180042bed  movzx   ebx, ax
0x180042bf0  or      ebx, 80070000h
0x180042bf6  jmp     short loc_180042C36
0x180042bf8  mov     rcx, [rbp+Token]; TokenHandle
0x180042bfc  lea     r8, [rbp+NewState]; NewState
0x180042c00  mov     [rsp+68h+phNewToken], 0; ReturnLength
0x180042c09  xor     r9d, r9d; BufferLength
0x180042c0c  xor     edx, edx; DisableAllPrivileges
0x180042c0e  mov     qword ptr [rsp+68h+TokenType], 0; PreviousState
0x180042c17  call    cs:__imp_AdjustTokenPrivileges
0x180042c1d  test    eax, eax
0x180042c1f  jz      short loc_180042BE1
0x180042c21  mov     rdx, [rbp+Token]; Token
0x180042c25  xor     ecx, ecx; Thread
0x180042c27  call    cs:__imp_SetThreadToken
0x180042c2d  test    eax, eax
0x180042c2f  jz      short loc_180042BE1
0x180042c31  xor     ebx, ebx
0x180042c33  mov     [rsi], rdi
0x180042c36  test    rdi, rdi
0x180042c39  jnz     short loc_180042C4B
0x180042c3b  mov     rcx, [rbp+TokenHandle]; hObject
0x180042c3f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180042c43  jz      short loc_180042C4B
0x180042c45  call    cs:__imp_CloseHandle
0x180042c4b  mov     rcx, [rbp+Token]; hObject
0x180042c4f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180042c53  jz      short loc_180042C5B
0x180042c55  call    cs:__imp_CloseHandle
0x180042c5b  mov     eax, ebx
0x180042c5d  mov     rcx, [rbp+var_18]
0x180042c61  xor     rcx, rsp; StackCookie
0x180042c64  call    __security_check_cookie
0x180042c69  add     rsp, 68h
0x180042c6d  pop     rdi
0x180042c6e  pop     rsi
0x180042c6f  pop     rbx
0x180042c70  pop     rbp
0x180042c71  retn
```
