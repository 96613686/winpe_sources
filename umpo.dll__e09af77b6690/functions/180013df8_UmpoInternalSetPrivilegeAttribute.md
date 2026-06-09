# UmpoInternalSetPrivilegeAttribute

- ea: `0x180013df8`
- end: `0x180013f0f`
- name: `UmpoInternalSetPrivilegeAttribute`
- size: `279`
- prototype: `DWORD __fastcall(int, DWORD Attributes, DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012254`

## callees

- `0x180010070`
- `0x180013df8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180013ec9`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180013ec9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e84`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180013e4d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180013e4d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180013e7a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180013e7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013e37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013e37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180013e68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180013e68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013ed7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013ef2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013ed7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013ef2`

## pseudocode

```c
DWORD __fastcall UmpoInternalSetPrivilegeAttribute(int a1, DWORD Attributes, DWORD *a3)
{
  LUID v3; // rsi
  HANDLE CurrentThread; // rax
  DWORD result; // eax
  HANDLE CurrentProcess; // rax
  DWORD ReturnLength; // [rsp+30h] [rbp-48h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-40h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+50h] [rbp-28h] BYREF

  v3 = (LUID)a1;
  ReturnLength = 0;
  NewState = 0;
  PreviousState = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x28u, 1, &TokenHandle) )
  {
    result = GetLastError();
    if ( result != 1008 )
      return result;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
      return GetLastError();
  }
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Luid = v3;
  NewState.Privileges[0].Attributes = Attributes;
  ReturnLength = 16;
  if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &ReturnLength) )
  {
    CloseHandle(TokenHandle);
    return GetLastError();
  }
  if ( a3 )
  {
    if ( PreviousState.PrivilegeCount )
      Attributes = PreviousState.Privileges[0].Attributes;
    *a3 = Attributes;
  }
  CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x180013df8  push    rbp
0x180013dfa  push    rbx
0x180013dfb  push    rsi
0x180013dfc  push    rdi
0x180013dfd  mov     rbp, rsp
0x180013e00  sub     rsp, 78h
0x180013e04  mov     rax, cs:__security_cookie
0x180013e0b  xor     rax, rsp
0x180013e0e  mov     [rbp+var_18], rax
0x180013e12  xorps   xmm0, xmm0
0x180013e15  movsxd  rsi, ecx
0x180013e18  xorps   xmm1, xmm1
0x180013e1b  mov     [rbp+var_48], 0
0x180013e22  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x180013e26  mov     rdi, r8
0x180013e29  mov     ebx, edx
0x180013e2b  movups  xmmword ptr [rbp+var_28.PrivilegeCount], xmm1
0x180013e2f  mov     [rbp+TokenHandle], 0
0x180013e37  call    cs:__imp_GetCurrentThread
0x180013e3d  mov     edx, 28h ; '('; DesiredAccess
0x180013e42  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180013e46  mov     rcx, rax; ThreadHandle
0x180013e49  lea     r8d, [rdx-27h]; OpenAsSelf
0x180013e4d  call    cs:__imp_OpenThreadToken
0x180013e53  test    eax, eax
0x180013e55  jnz     short loc_180013E8C
0x180013e57  call    cs:__imp_GetLastError
0x180013e5d  cmp     eax, 3F0h
0x180013e62  jnz     loc_180013EFA
0x180013e68  call    cs:__imp_GetCurrentProcess
0x180013e6e  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180013e72  mov     edx, 28h ; '('; DesiredAccess
0x180013e77  mov     rcx, rax; ProcessHandle
0x180013e7a  call    cs:__imp_OpenProcessToken
0x180013e80  test    eax, eax
0x180013e82  jnz     short loc_180013E8C
0x180013e84  call    cs:__imp_GetLastError
0x180013e8a  jmp     short loc_180013EFA
0x180013e8c  lea     rax, [rbp+var_48]
0x180013e90  mov     [rbp+NewState.PrivilegeCount], 1
0x180013e97  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x180013e9c  lea     r8, [rbp+NewState]; NewState
0x180013ea0  mov     r9d, 10h; BufferLength
0x180013ea6  mov     [rbp+NewState.Privileges.Luid.LowPart], esi
0x180013ea9  lea     rax, [rbp+var_28]
0x180013ead  mov     [rbp+NewState.Privileges.Attributes], ebx
0x180013eb0  mov     rcx, rsi
0x180013eb3  mov     [rbp+var_48], r9d
0x180013eb7  shr     rcx, 20h
0x180013ebb  xor     edx, edx; DisableAllPrivileges
0x180013ebd  mov     [rbp+NewState.Privileges.Luid.HighPart], ecx
0x180013ec0  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180013ec4  mov     [rsp+78h+PreviousState], rax; PreviousState
0x180013ec9  call    cs:__imp_AdjustTokenPrivileges
0x180013ecf  test    eax, eax
0x180013ed1  jnz     short loc_180013EDF
0x180013ed3  mov     rcx, [rbp+TokenHandle]; hObject
0x180013ed7  call    cs:__imp_CloseHandle
0x180013edd  jmp     short loc_180013E84
0x180013edf  test    rdi, rdi
0x180013ee2  jz      short loc_180013EEE
0x180013ee4  cmp     [rbp+var_28.PrivilegeCount], 0
0x180013ee8  cmovnz  ebx, [rbp+var_28.Privileges.Attributes]
0x180013eec  mov     [rdi], ebx
0x180013eee  mov     rcx, [rbp+TokenHandle]; hObject
0x180013ef2  call    cs:__imp_CloseHandle
0x180013ef8  xor     eax, eax
0x180013efa  mov     rcx, [rbp+var_18]
0x180013efe  xor     rcx, rsp; StackCookie
0x180013f01  call    __security_check_cookie
0x180013f06  add     rsp, 78h
0x180013f0a  pop     rdi
0x180013f0b  pop     rsi
0x180013f0c  pop     rbx
0x180013f0d  pop     rbp
0x180013f0e  retn
```
