# WTSQueryUserToken

- ea: `0x180001a00`
- end: `0x180001b83`
- name: `WTSQueryUserToken`
- size: `387`
- prototype: `BOOL __stdcall(ULONG SessionId, PHANDLE phToken)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001a00`
- `0x1800155c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001ade`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001b7b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001ade`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001b7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001a4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001a4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001b04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001b04`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180001a63`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180001a63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001b11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001b11`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180001a90`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180001a90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001a7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001a7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001ae8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001af4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001ae8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001af4`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x180001ac7`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x180001ac7`
- `WINSTA!WinStationQueryInformationW` at `0x180001b3d`
- `WINSTA!WinStationQueryInformationW` at `0x180001b3d`

## pseudocode

```c
BOOL __stdcall WTSQueryUserToken(ULONG SessionId, PHANDLE phToken)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  BOOL v6; // ebx
  BOOL result; // eax
  WINBOOL pfResult; // [rsp+30h] [rbp-50h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-48h] BYREF
  int v10; // [rsp+40h] [rbp-40h] BYREF
  __int128 v11; // [rsp+48h] [rbp-38h] BYREF
  void *v12; // [rsp+58h] [rbp-28h]
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+60h] [rbp-20h] BYREF

  v10 = 0;
  v12 = 0;
  v11 = 0;
  if ( !phToken )
  {
    SetLastError(0x57u);
    return 0;
  }
  pfResult = 0;
  TokenHandle = 0;
  memset(&RequiredPrivileges, 0, sizeof(RequiredPrivileges));
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x2000000u, 0, &TokenHandle) )
  {
    if ( GetLastError() != 1008 )
      return 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x2000000u, &TokenHandle) )
      return 0;
  }
  RequiredPrivileges.PrivilegeCount = 1;
  RequiredPrivileges.Control = 1;
  RequiredPrivileges.Privilege[0].Luid = (LUID)7LL;
  RequiredPrivileges.Privilege[0].Attributes = 2;
  v6 = PrivilegeCheck(TokenHandle, &RequiredPrivileges, &pfResult);
  if ( !v6 || pfResult )
  {
    CloseHandle(TokenHandle);
    if ( !v6 )
      return 0;
  }
  else
  {
    SetLastError(0x522u);
    CloseHandle(TokenHandle);
  }
  if ( pfResult )
  {
    *(_QWORD *)&v11 = (int)GetCurrentProcessId();
    *((_QWORD *)&v11 + 1) = (int)GetCurrentThreadId();
    if ( (unsigned __int8)WinStationQueryInformationW(0, SessionId, 14, &v11, 24, &v10) )
    {
      result = 1;
      *phToken = v12;
      return result;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180001a00  mov     [rsp-18h+arg_10], rbx; QueryUserToken
0x180001a05  push    rbp
0x180001a06  push    rsi
0x180001a07  push    rdi
0x180001a08  mov     rbp, rsp
0x180001a0b  sub     rsp, 80h
0x180001a12  mov     rax, cs:__security_cookie
0x180001a19  xor     rax, rsp
0x180001a1c  mov     [rbp+var_8], rax
0x180001a20  xor     ebx, ebx
0x180001a22  xor     eax, eax
0x180001a24  mov     [rbp+var_40], ebx
0x180001a27  xorps   xmm0, xmm0
0x180001a2a  mov     [rbp+var_28], rax
0x180001a2e  mov     rdi, rdx
0x180001a31  mov     esi, ecx
0x180001a33  movups  [rbp+var_38], xmm0
0x180001a37  test    rdx, rdx
0x180001a3a  jz      loc_180001B76
0x180001a40  mov     [rbp+pfResult], ebx
0x180001a43  mov     [rbp+TokenHandle], rbx
0x180001a47  movups  xmmword ptr [rbp+RequiredPrivileges.PrivilegeCount], xmm0
0x180001a4b  mov     [rbp+RequiredPrivileges.Privilege.Attributes], eax
0x180001a4e  call    cs:__imp_GetCurrentThread
0x180001a54  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180001a58  xor     r8d, r8d; OpenAsSelf
0x180001a5b  mov     rcx, rax; ThreadHandle
0x180001a5e  mov     edx, 2000000h; DesiredAccess
0x180001a63  call    cs:__imp_OpenThreadToken
0x180001a69  test    eax, eax
0x180001a6b  jnz     short loc_180001A9E
0x180001a6d  call    cs:__imp_GetLastError
0x180001a73  cmp     eax, 3F0h
0x180001a78  jnz     loc_180001B72
0x180001a7e  call    cs:__imp_GetCurrentProcess
0x180001a84  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180001a88  mov     edx, 2000000h; DesiredAccess
0x180001a8d  mov     rcx, rax; ProcessHandle
0x180001a90  call    cs:__imp_OpenProcessToken
0x180001a96  test    eax, eax
0x180001a98  jz      loc_180001B72
0x180001a9e  mov     rcx, [rbp+TokenHandle]; ClientToken
0x180001aa2  lea     r8, [rbp+pfResult]; pfResult
0x180001aa6  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x180001aaa  mov     [rbp+RequiredPrivileges.PrivilegeCount], 1
0x180001ab1  mov     [rbp+RequiredPrivileges.Control], 1
0x180001ab8  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.LowPart], 7
0x180001ac0  mov     [rbp+RequiredPrivileges.Privilege.Attributes], 2
0x180001ac7  call    cs:__imp_PrivilegeCheck
0x180001acd  mov     ebx, eax
0x180001acf  test    eax, eax
0x180001ad1  jz      short loc_180001AF0
0x180001ad3  cmp     [rbp+pfResult], 0
0x180001ad7  jnz     short loc_180001AF0
0x180001ad9  mov     ecx, 522h; dwErrCode
0x180001ade  call    cs:__imp_SetLastError
0x180001ae4  mov     rcx, [rbp+TokenHandle]; hObject
0x180001ae8  call    cs:__imp_CloseHandle
0x180001aee  jmp     short loc_180001AFE
0x180001af0  mov     rcx, [rbp+TokenHandle]; hObject
0x180001af4  call    cs:__imp_CloseHandle
0x180001afa  test    ebx, ebx
0x180001afc  jz      short loc_180001B72
0x180001afe  cmp     [rbp+pfResult], 0
0x180001b02  jz      short loc_180001B72
0x180001b04  call    cs:__imp_GetCurrentProcessId
0x180001b0a  movsxd  rcx, eax
0x180001b0d  mov     qword ptr [rbp+var_38], rcx
0x180001b11  call    cs:__imp_GetCurrentThreadId
0x180001b17  movsxd  rcx, eax
0x180001b1a  lea     r9, [rbp+var_38]
0x180001b1e  mov     qword ptr [rbp+var_38+8], rcx
0x180001b22  mov     r8d, 0Eh
0x180001b28  lea     rcx, [rbp+var_40]
0x180001b2c  mov     edx, esi
0x180001b2e  mov     [rsp+80h+var_58], rcx
0x180001b33  xor     ecx, ecx
0x180001b35  mov     [rsp+80h+var_60], 18h
0x180001b3d  call    cs:__imp_WinStationQueryInformationW
0x180001b43  test    al, al
0x180001b45  jz      short loc_180001B72
0x180001b47  mov     rcx, [rbp+var_28]
0x180001b4b  mov     eax, 1
0x180001b50  mov     [rdi], rcx
0x180001b53  mov     rcx, [rbp+var_8]
0x180001b57  xor     rcx, rsp; StackCookie
0x180001b5a  call    __security_check_cookie
0x180001b5f  mov     rbx, [rsp+80h+arg_10]
0x180001b67  add     rsp, 80h
0x180001b6e  pop     rdi
0x180001b6f  pop     rsi
0x180001b70  pop     rbp
0x180001b71  retn
0x180001b72  xor     eax, eax
0x180001b74  jmp     short loc_180001B53
0x180001b76  mov     ecx, 57h ; 'W'; dwErrCode
0x180001b7b  call    cs:__imp_SetLastError
0x180001b81  jmp     short loc_180001B72
```
