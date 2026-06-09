# FvepAcquirePrivilege

- ea: `0x18006ee80`
- end: `0x18006efe6`
- name: `FvepAcquirePrivilege`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006efec`

## callees

- `0x18006ee80`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x18006eef0`
- `KERNEL32!GetCurrentProcess` at `0x18006eef0`
- `KERNEL32!GetCurrentThread` at `0x18006eec4`
- `KERNEL32!GetCurrentThread` at `0x18006eec4`
- `KERNEL32!GetLastError` at `0x18006eee1`
- `KERNEL32!GetLastError` at `0x18006ef09`
- `KERNEL32!GetLastError` at `0x18006ef55`
- `KERNEL32!GetLastError` at `0x18006eee1`
- `KERNEL32!GetLastError` at `0x18006ef09`
- `KERNEL32!GetLastError` at `0x18006ef55`
- `KERNEL32!CloseHandle` at `0x18006efb9`
- `KERNEL32!CloseHandle` at `0x18006efc9`
- `KERNEL32!CloseHandle` at `0x18006efb9`
- `KERNEL32!CloseHandle` at `0x18006efc9`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18006ef8b`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18006ef8b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18006ef4b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18006ef4b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18006eeff`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18006eeff`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18006ef9b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18006ef9b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006eed7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006eed7`

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
0x18006ee80  push    rbp
0x18006ee82  push    rbx
0x18006ee83  push    rsi
0x18006ee84  push    rdi
0x18006ee85  mov     rbp, rsp
0x18006ee88  sub     rsp, 68h
0x18006ee8c  mov     rax, cs:__security_cookie
0x18006ee93  xor     rax, rsp
0x18006ee96  mov     [rbp+var_18], rax
0x18006ee9a  mov     ebx, 2
0x18006ee9f  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18006eea7  mov     [rbp+NewState.Privileges.Attributes], ebx
0x18006eeaa  mov     rsi, rdx
0x18006eead  mov     [rbp+Token], 0FFFFFFFFFFFFFFFFh
0x18006eeb5  mov     [rbp+NewState.PrivilegeCount], 1
0x18006eebc  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 11h
0x18006eec4  call    cs:__imp_GetCurrentThread
0x18006eeca  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18006eece  xor     r8d, r8d; OpenAsSelf
0x18006eed1  mov     rcx, rax; ThreadHandle
0x18006eed4  lea     edx, [rbx+4]; DesiredAccess
0x18006eed7  call    cs:__imp_OpenThreadToken
0x18006eedd  test    eax, eax
0x18006eedf  jnz     short loc_18006EF2D
0x18006eee1  call    cs:__imp_GetLastError
0x18006eee7  cmp     eax, 3F0h
0x18006eeec  jnz     short loc_18006EF09
0x18006eeee  xor     edi, edi
0x18006eef0  call    cs:__imp_GetCurrentProcess
0x18006eef6  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18006eefa  mov     edx, ebx; DesiredAccess
0x18006eefc  mov     rcx, rax; ProcessHandle
0x18006eeff  call    cs:__imp_OpenProcessToken
0x18006ef05  test    eax, eax
0x18006ef07  jnz     short loc_18006EF27
0x18006ef09  call    cs:__imp_GetLastError
0x18006ef0f  mov     ebx, eax
0x18006ef11  test    eax, eax
0x18006ef13  jle     loc_18006EFAF
0x18006ef19  movzx   ebx, ax
0x18006ef1c  or      ebx, 80070000h
0x18006ef22  jmp     loc_18006EFAF
0x18006ef27  mov     rcx, [rbp+TokenHandle]
0x18006ef2b  jmp     short loc_18006EF34
0x18006ef2d  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x18006ef31  mov     rdi, rcx
0x18006ef34  xor     r8d, r8d; lpTokenAttributes
0x18006ef37  lea     rax, [rbp+Token]
0x18006ef3b  mov     [rsp+68h+phNewToken], rax; phNewToken
0x18006ef40  mov     r9d, ebx; ImpersonationLevel
0x18006ef43  mov     [rsp+68h+TokenType], ebx; TokenType
0x18006ef47  lea     edx, [r8+2Ch]; dwDesiredAccess
0x18006ef4b  call    cs:__imp_DuplicateTokenEx
0x18006ef51  test    eax, eax
0x18006ef53  jnz     short loc_18006EF6C
0x18006ef55  call    cs:__imp_GetLastError
0x18006ef5b  mov     ebx, eax
0x18006ef5d  test    eax, eax
0x18006ef5f  jle     short loc_18006EFAA
0x18006ef61  movzx   ebx, ax
0x18006ef64  or      ebx, 80070000h
0x18006ef6a  jmp     short loc_18006EFAA
0x18006ef6c  mov     rcx, [rbp+Token]; TokenHandle
0x18006ef70  lea     r8, [rbp+NewState]; NewState
0x18006ef74  mov     [rsp+68h+phNewToken], 0; ReturnLength
0x18006ef7d  xor     r9d, r9d; BufferLength
0x18006ef80  xor     edx, edx; DisableAllPrivileges
0x18006ef82  mov     qword ptr [rsp+68h+TokenType], 0; PreviousState
0x18006ef8b  call    cs:__imp_AdjustTokenPrivileges
0x18006ef91  test    eax, eax
0x18006ef93  jz      short loc_18006EF55
0x18006ef95  mov     rdx, [rbp+Token]; Token
0x18006ef99  xor     ecx, ecx; Thread
0x18006ef9b  call    cs:__imp_SetThreadToken
0x18006efa1  test    eax, eax
0x18006efa3  jz      short loc_18006EF55
0x18006efa5  xor     ebx, ebx
0x18006efa7  mov     [rsi], rdi
0x18006efaa  test    rdi, rdi
0x18006efad  jnz     short loc_18006EFBF
0x18006efaf  mov     rcx, [rbp+TokenHandle]; hObject
0x18006efb3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006efb7  jz      short loc_18006EFBF
0x18006efb9  call    cs:__imp_CloseHandle
0x18006efbf  mov     rcx, [rbp+Token]; hObject
0x18006efc3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006efc7  jz      short loc_18006EFCF
0x18006efc9  call    cs:__imp_CloseHandle
0x18006efcf  mov     eax, ebx
0x18006efd1  mov     rcx, [rbp+var_18]
0x18006efd5  xor     rcx, rsp; StackCookie
0x18006efd8  call    __security_check_cookie
0x18006efdd  add     rsp, 68h
0x18006efe1  pop     rdi
0x18006efe2  pop     rsi
0x18006efe3  pop     rbx
0x18006efe4  pop     rbp
0x18006efe5  retn
```
