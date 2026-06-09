# FvepAcquirePrivilege

- ea: `0x140051a38`
- end: `0x140051b9e`
- name: `FvepAcquirePrivilege`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140051ba4`

## callees

- `0x140051a38`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051a99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051ac1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051b0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051a99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051ac1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051b0d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x140051b03`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x140051b03`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x140051b43`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x140051b43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140051a7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140051a7c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140051ab7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140051ab7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140051a8f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140051a8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140051aa8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140051aa8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140051b53`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140051b53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140051b71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140051b81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140051b71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140051b81`

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
0x140051a38  push    rbp
0x140051a3a  push    rbx
0x140051a3b  push    rsi
0x140051a3c  push    rdi
0x140051a3d  mov     rbp, rsp
0x140051a40  sub     rsp, 68h
0x140051a44  mov     rax, cs:__security_cookie
0x140051a4b  xor     rax, rsp
0x140051a4e  mov     [rbp+var_18], rax
0x140051a52  mov     ebx, 2
0x140051a57  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x140051a5f  mov     [rbp+NewState.Privileges.Attributes], ebx
0x140051a62  mov     rsi, rdx
0x140051a65  mov     [rbp+Token], 0FFFFFFFFFFFFFFFFh
0x140051a6d  mov     [rbp+NewState.PrivilegeCount], 1
0x140051a74  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 11h
0x140051a7c  call    cs:__imp_GetCurrentThread
0x140051a82  lea     r9, [rbp+TokenHandle]; TokenHandle
0x140051a86  xor     r8d, r8d; OpenAsSelf
0x140051a89  mov     rcx, rax; ThreadHandle
0x140051a8c  lea     edx, [rbx+4]; DesiredAccess
0x140051a8f  call    cs:__imp_OpenThreadToken
0x140051a95  test    eax, eax
0x140051a97  jnz     short loc_140051AE5
0x140051a99  call    cs:__imp_GetLastError
0x140051a9f  cmp     eax, 3F0h
0x140051aa4  jnz     short loc_140051AC1
0x140051aa6  xor     edi, edi
0x140051aa8  call    cs:__imp_GetCurrentProcess
0x140051aae  lea     r8, [rbp+TokenHandle]; TokenHandle
0x140051ab2  mov     edx, ebx; DesiredAccess
0x140051ab4  mov     rcx, rax; ProcessHandle
0x140051ab7  call    cs:__imp_OpenProcessToken
0x140051abd  test    eax, eax
0x140051abf  jnz     short loc_140051ADF
0x140051ac1  call    cs:__imp_GetLastError
0x140051ac7  mov     ebx, eax
0x140051ac9  test    eax, eax
0x140051acb  jle     loc_140051B67
0x140051ad1  movzx   ebx, ax
0x140051ad4  or      ebx, 80070000h
0x140051ada  jmp     loc_140051B67
0x140051adf  mov     rcx, [rbp+TokenHandle]
0x140051ae3  jmp     short loc_140051AEC
0x140051ae5  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x140051ae9  mov     rdi, rcx
0x140051aec  xor     r8d, r8d; lpTokenAttributes
0x140051aef  lea     rax, [rbp+Token]
0x140051af3  mov     [rsp+68h+phNewToken], rax; phNewToken
0x140051af8  mov     r9d, ebx; ImpersonationLevel
0x140051afb  mov     [rsp+68h+TokenType], ebx; TokenType
0x140051aff  lea     edx, [r8+2Ch]; dwDesiredAccess
0x140051b03  call    cs:__imp_DuplicateTokenEx
0x140051b09  test    eax, eax
0x140051b0b  jnz     short loc_140051B24
0x140051b0d  call    cs:__imp_GetLastError
0x140051b13  mov     ebx, eax
0x140051b15  test    eax, eax
0x140051b17  jle     short loc_140051B62
0x140051b19  movzx   ebx, ax
0x140051b1c  or      ebx, 80070000h
0x140051b22  jmp     short loc_140051B62
0x140051b24  mov     rcx, [rbp+Token]; TokenHandle
0x140051b28  lea     r8, [rbp+NewState]; NewState
0x140051b2c  mov     [rsp+68h+phNewToken], 0; ReturnLength
0x140051b35  xor     r9d, r9d; BufferLength
0x140051b38  xor     edx, edx; DisableAllPrivileges
0x140051b3a  mov     qword ptr [rsp+68h+TokenType], 0; PreviousState
0x140051b43  call    cs:__imp_AdjustTokenPrivileges
0x140051b49  test    eax, eax
0x140051b4b  jz      short loc_140051B0D
0x140051b4d  mov     rdx, [rbp+Token]; Token
0x140051b51  xor     ecx, ecx; Thread
0x140051b53  call    cs:__imp_SetThreadToken
0x140051b59  test    eax, eax
0x140051b5b  jz      short loc_140051B0D
0x140051b5d  xor     ebx, ebx
0x140051b5f  mov     [rsi], rdi
0x140051b62  test    rdi, rdi
0x140051b65  jnz     short loc_140051B77
0x140051b67  mov     rcx, [rbp+TokenHandle]; hObject
0x140051b6b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140051b6f  jz      short loc_140051B77
0x140051b71  call    cs:__imp_CloseHandle
0x140051b77  mov     rcx, [rbp+Token]; hObject
0x140051b7b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140051b7f  jz      short loc_140051B87
0x140051b81  call    cs:__imp_CloseHandle
0x140051b87  mov     eax, ebx
0x140051b89  mov     rcx, [rbp+var_18]
0x140051b8d  xor     rcx, rsp; StackCookie
0x140051b90  call    __security_check_cookie
0x140051b95  add     rsp, 68h
0x140051b99  pop     rdi
0x140051b9a  pop     rsi
0x140051b9b  pop     rbx
0x140051b9c  pop     rbp
0x140051b9d  retn
```
