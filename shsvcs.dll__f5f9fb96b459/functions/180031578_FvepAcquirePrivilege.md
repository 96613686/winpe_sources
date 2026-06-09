# FvepAcquirePrivilege

- ea: `0x180031578`
- end: `0x1800316de`
- name: `FvepAcquirePrivilege`
- size: `358`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800316e4`

## callees

- `0x180031578`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800315f7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800315f7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180031693`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180031693`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800315bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800315bc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800315cf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800315cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800315e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800315e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800315d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031601`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003164d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800315d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031601`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003164d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800316b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800316c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800316b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800316c1`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180031683`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180031683`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180031643`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180031643`

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
0x180031578  push    rbp
0x18003157a  push    rbx
0x18003157b  push    rsi
0x18003157c  push    rdi
0x18003157d  mov     rbp, rsp
0x180031580  sub     rsp, 68h
0x180031584  mov     rax, cs:__security_cookie
0x18003158b  xor     rax, rsp
0x18003158e  mov     [rbp+var_18], rax
0x180031592  mov     ebx, 2
0x180031597  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18003159f  mov     [rbp+NewState.Privileges.Attributes], ebx
0x1800315a2  mov     rsi, rdx
0x1800315a5  mov     [rbp+Token], 0FFFFFFFFFFFFFFFFh
0x1800315ad  mov     [rbp+NewState.PrivilegeCount], 1
0x1800315b4  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 11h
0x1800315bc  call    cs:__imp_GetCurrentThread
0x1800315c2  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800315c6  xor     r8d, r8d; OpenAsSelf
0x1800315c9  mov     rcx, rax; ThreadHandle
0x1800315cc  lea     edx, [rbx+4]; DesiredAccess
0x1800315cf  call    cs:__imp_OpenThreadToken
0x1800315d5  test    eax, eax
0x1800315d7  jnz     short loc_180031625
0x1800315d9  call    cs:__imp_GetLastError
0x1800315df  cmp     eax, 3F0h
0x1800315e4  jnz     short loc_180031601
0x1800315e6  xor     edi, edi
0x1800315e8  call    cs:__imp_GetCurrentProcess
0x1800315ee  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800315f2  mov     edx, ebx; DesiredAccess
0x1800315f4  mov     rcx, rax; ProcessHandle
0x1800315f7  call    cs:__imp_OpenProcessToken
0x1800315fd  test    eax, eax
0x1800315ff  jnz     short loc_18003161F
0x180031601  call    cs:__imp_GetLastError
0x180031607  mov     ebx, eax
0x180031609  test    eax, eax
0x18003160b  jle     loc_1800316A7
0x180031611  movzx   ebx, ax
0x180031614  or      ebx, 80070000h
0x18003161a  jmp     loc_1800316A7
0x18003161f  mov     rcx, [rbp+TokenHandle]
0x180031623  jmp     short loc_18003162C
0x180031625  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x180031629  mov     rdi, rcx
0x18003162c  xor     r8d, r8d; lpTokenAttributes
0x18003162f  lea     rax, [rbp+Token]
0x180031633  mov     [rsp+68h+phNewToken], rax; phNewToken
0x180031638  mov     r9d, ebx; ImpersonationLevel
0x18003163b  mov     [rsp+68h+TokenType], ebx; TokenType
0x18003163f  lea     edx, [r8+2Ch]; dwDesiredAccess
0x180031643  call    cs:__imp_DuplicateTokenEx
0x180031649  test    eax, eax
0x18003164b  jnz     short loc_180031664
0x18003164d  call    cs:__imp_GetLastError
0x180031653  mov     ebx, eax
0x180031655  test    eax, eax
0x180031657  jle     short loc_1800316A2
0x180031659  movzx   ebx, ax
0x18003165c  or      ebx, 80070000h
0x180031662  jmp     short loc_1800316A2
0x180031664  mov     rcx, [rbp+Token]; TokenHandle
0x180031668  lea     r8, [rbp+NewState]; NewState
0x18003166c  mov     [rsp+68h+phNewToken], 0; ReturnLength
0x180031675  xor     r9d, r9d; BufferLength
0x180031678  xor     edx, edx; DisableAllPrivileges
0x18003167a  mov     qword ptr [rsp+68h+TokenType], 0; PreviousState
0x180031683  call    cs:__imp_AdjustTokenPrivileges
0x180031689  test    eax, eax
0x18003168b  jz      short loc_18003164D
0x18003168d  mov     rdx, [rbp+Token]; Token
0x180031691  xor     ecx, ecx; Thread
0x180031693  call    cs:__imp_SetThreadToken
0x180031699  test    eax, eax
0x18003169b  jz      short loc_18003164D
0x18003169d  xor     ebx, ebx
0x18003169f  mov     [rsi], rdi
0x1800316a2  test    rdi, rdi
0x1800316a5  jnz     short loc_1800316B7
0x1800316a7  mov     rcx, [rbp+TokenHandle]; hObject
0x1800316ab  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800316af  jz      short loc_1800316B7
0x1800316b1  call    cs:__imp_CloseHandle
0x1800316b7  mov     rcx, [rbp+Token]; hObject
0x1800316bb  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800316bf  jz      short loc_1800316C7
0x1800316c1  call    cs:__imp_CloseHandle
0x1800316c7  mov     eax, ebx
0x1800316c9  mov     rcx, [rbp+var_18]
0x1800316cd  xor     rcx, rsp; StackCookie
0x1800316d0  call    __security_check_cookie
0x1800316d5  add     rsp, 68h
0x1800316d9  pop     rdi
0x1800316da  pop     rsi
0x1800316db  pop     rbx
0x1800316dc  pop     rbp
0x1800316dd  retn
```
