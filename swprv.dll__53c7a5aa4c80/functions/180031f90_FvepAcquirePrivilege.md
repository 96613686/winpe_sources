# FvepAcquirePrivilege

- ea: `0x180031f90`
- end: `0x1800320f6`
- name: `FvepAcquirePrivilege`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800320fc`

## callees

- `0x180001580`
- `0x180031f90`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800320c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800320d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800320c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800320d9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800320ab`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800320ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180032000`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180032000`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003200f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003200f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180031fd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180031fd4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180031fe7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180031fe7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ff1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032019`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032065`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ff1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032019`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032065`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18003209b`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18003209b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003205b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003205b`

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
0x180031f90  push    rbp
0x180031f92  push    rbx
0x180031f93  push    rsi
0x180031f94  push    rdi
0x180031f95  mov     rbp, rsp
0x180031f98  sub     rsp, 68h
0x180031f9c  mov     rax, cs:__security_cookie
0x180031fa3  xor     rax, rsp
0x180031fa6  mov     [rbp+var_18], rax
0x180031faa  mov     ebx, 2
0x180031faf  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180031fb7  mov     [rbp+NewState.Privileges.Attributes], ebx
0x180031fba  mov     rsi, rdx
0x180031fbd  mov     [rbp+Token], 0FFFFFFFFFFFFFFFFh
0x180031fc5  mov     [rbp+NewState.PrivilegeCount], 1
0x180031fcc  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 11h
0x180031fd4  call    cs:__imp_GetCurrentThread
0x180031fda  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180031fde  xor     r8d, r8d; OpenAsSelf
0x180031fe1  mov     rcx, rax; ThreadHandle
0x180031fe4  lea     edx, [rbx+4]; DesiredAccess
0x180031fe7  call    cs:__imp_OpenThreadToken
0x180031fed  test    eax, eax
0x180031fef  jnz     short loc_18003203D
0x180031ff1  call    cs:__imp_GetLastError
0x180031ff7  cmp     eax, 3F0h
0x180031ffc  jnz     short loc_180032019
0x180031ffe  xor     edi, edi
0x180032000  call    cs:__imp_GetCurrentProcess
0x180032006  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18003200a  mov     edx, ebx; DesiredAccess
0x18003200c  mov     rcx, rax; ProcessHandle
0x18003200f  call    cs:__imp_OpenProcessToken
0x180032015  test    eax, eax
0x180032017  jnz     short loc_180032037
0x180032019  call    cs:__imp_GetLastError
0x18003201f  mov     ebx, eax
0x180032021  test    eax, eax
0x180032023  jle     loc_1800320BF
0x180032029  movzx   ebx, ax
0x18003202c  or      ebx, 80070000h
0x180032032  jmp     loc_1800320BF
0x180032037  mov     rcx, [rbp+TokenHandle]
0x18003203b  jmp     short loc_180032044
0x18003203d  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x180032041  mov     rdi, rcx
0x180032044  xor     r8d, r8d; lpTokenAttributes
0x180032047  lea     rax, [rbp+Token]
0x18003204b  mov     [rsp+68h+phNewToken], rax; phNewToken
0x180032050  mov     r9d, ebx; ImpersonationLevel
0x180032053  mov     [rsp+68h+TokenType], ebx; TokenType
0x180032057  lea     edx, [r8+2Ch]; dwDesiredAccess
0x18003205b  call    cs:__imp_DuplicateTokenEx
0x180032061  test    eax, eax
0x180032063  jnz     short loc_18003207C
0x180032065  call    cs:__imp_GetLastError
0x18003206b  mov     ebx, eax
0x18003206d  test    eax, eax
0x18003206f  jle     short loc_1800320BA
0x180032071  movzx   ebx, ax
0x180032074  or      ebx, 80070000h
0x18003207a  jmp     short loc_1800320BA
0x18003207c  mov     rcx, [rbp+Token]; TokenHandle
0x180032080  lea     r8, [rbp+NewState]; NewState
0x180032084  mov     [rsp+68h+phNewToken], 0; ReturnLength
0x18003208d  xor     r9d, r9d; BufferLength
0x180032090  xor     edx, edx; DisableAllPrivileges
0x180032092  mov     qword ptr [rsp+68h+TokenType], 0; PreviousState
0x18003209b  call    cs:__imp_AdjustTokenPrivileges
0x1800320a1  test    eax, eax
0x1800320a3  jz      short loc_180032065
0x1800320a5  mov     rdx, [rbp+Token]; Token
0x1800320a9  xor     ecx, ecx; Thread
0x1800320ab  call    cs:__imp_SetThreadToken
0x1800320b1  test    eax, eax
0x1800320b3  jz      short loc_180032065
0x1800320b5  xor     ebx, ebx
0x1800320b7  mov     [rsi], rdi
0x1800320ba  test    rdi, rdi
0x1800320bd  jnz     short loc_1800320CF
0x1800320bf  mov     rcx, [rbp+TokenHandle]; hObject
0x1800320c3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800320c7  jz      short loc_1800320CF
0x1800320c9  call    cs:__imp_CloseHandle
0x1800320cf  mov     rcx, [rbp+Token]; hObject
0x1800320d3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800320d7  jz      short loc_1800320DF
0x1800320d9  call    cs:__imp_CloseHandle
0x1800320df  mov     eax, ebx
0x1800320e1  mov     rcx, [rbp+var_18]
0x1800320e5  xor     rcx, rsp; StackCookie
0x1800320e8  call    __security_check_cookie
0x1800320ed  add     rsp, 68h
0x1800320f1  pop     rdi
0x1800320f2  pop     rsi
0x1800320f3  pop     rbx
0x1800320f4  pop     rbp
0x1800320f5  retn
```
