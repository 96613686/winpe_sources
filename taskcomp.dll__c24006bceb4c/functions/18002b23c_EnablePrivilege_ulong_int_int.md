# EnablePrivilege(ulong,int,int *)

- ea: `0x18002b23c`
- end: `0x18002b329`
- name: `?EnablePrivilege@@YAKKHPEAH@Z`
- size: `237`
- prototype: `__int64 __fastcall(__int64, int, DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a734`

## callees

- `0x18002b23c`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002b290`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002b290`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002b27e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002b27e`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002b2df`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002b2df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b29a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b29a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b303`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b303`

## pseudocode

```c
__int64 __fastcall EnablePrivilege(__int64 a1, int a2, DWORD *a3)
{
  HANDLE CurrentProcess; // rax
  DWORD LastError; // ebx
  DWORD ReturnLength; // [rsp+30h] [rbp-40h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+50h] [rbp-20h] BYREF

  TokenHandle = 0;
  ReturnLength = 0;
  NewState = 0;
  PreviousState = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle)
    && (NewState.PrivilegeCount = 1,
        NewState.Privileges[0].Luid = (LUID)8LL,
        NewState.Privileges[0].Attributes = a2 != 0 ? 2 : 0,
        AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &ReturnLength)) )
  {
    LastError = 0;
    if ( a3 )
      *a3 = (PreviousState.Privileges[0].Attributes >> 1) & 1;
  }
  else
  {
    LastError = GetLastError();
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x18002b23c  mov     [rsp-8+arg_0], rbx
0x18002b241  mov     [rsp-8+arg_8], rdi
0x18002b246  push    rbp
0x18002b247  mov     rbp, rsp
0x18002b24a  sub     rsp, 70h
0x18002b24e  mov     rax, cs:__security_cookie
0x18002b255  xor     rax, rsp
0x18002b258  mov     [rbp+var_10], rax
0x18002b25c  xorps   xmm0, xmm0
0x18002b25f  mov     [rbp+TokenHandle], 0
0x18002b267  xorps   xmm1, xmm1
0x18002b26a  mov     [rbp+var_40], 0
0x18002b271  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x18002b275  mov     rdi, r8
0x18002b278  mov     ebx, edx
0x18002b27a  movups  xmmword ptr [rbp+var_20.PrivilegeCount], xmm1
0x18002b27e  call    cs:__imp_GetCurrentProcess
0x18002b284  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18002b288  mov     edx, 28h ; '('; DesiredAccess
0x18002b28d  mov     rcx, rax; ProcessHandle
0x18002b290  call    cs:__imp_OpenProcessToken
0x18002b296  test    eax, eax
0x18002b298  jnz     short loc_18002B2A4
0x18002b29a  call    cs:__imp_GetLastError
0x18002b2a0  mov     ebx, eax
0x18002b2a2  jmp     short loc_18002B2FA
0x18002b2a4  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002b2a8  lea     r8, [rbp+NewState]; NewState
0x18002b2ac  neg     ebx
0x18002b2ae  mov     [rbp+NewState.PrivilegeCount], 1
0x18002b2b5  mov     r9d, 10h; BufferLength
0x18002b2bb  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 8
0x18002b2c3  sbb     eax, eax
0x18002b2c5  xor     edx, edx; DisableAllPrivileges
0x18002b2c7  and     eax, 2
0x18002b2ca  mov     [rbp+NewState.Privileges.Attributes], eax
0x18002b2cd  lea     rax, [rbp+var_40]
0x18002b2d1  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18002b2d6  lea     rax, [rbp+var_20]
0x18002b2da  mov     [rsp+70h+PreviousState], rax; PreviousState
0x18002b2df  call    cs:__imp_AdjustTokenPrivileges
0x18002b2e5  test    eax, eax
0x18002b2e7  jz      short loc_18002B29A
0x18002b2e9  xor     ebx, ebx
0x18002b2eb  test    rdi, rdi
0x18002b2ee  jz      short loc_18002B2FA
0x18002b2f0  mov     eax, [rbp+var_20.Privileges.Attributes]
0x18002b2f3  shr     eax, 1
0x18002b2f5  and     eax, 1
0x18002b2f8  mov     [rdi], eax
0x18002b2fa  mov     rcx, [rbp+TokenHandle]; hObject
0x18002b2fe  test    rcx, rcx
0x18002b301  jz      short loc_18002B309
0x18002b303  call    cs:__imp_CloseHandle
0x18002b309  mov     eax, ebx
0x18002b30b  mov     rcx, [rbp+var_10]
0x18002b30f  xor     rcx, rsp; StackCookie
0x18002b312  call    __security_check_cookie
0x18002b317  lea     r11, [rsp+70h+var_s0]
0x18002b31c  mov     rbx, [r11+10h]
0x18002b320  mov     rdi, [r11+18h]
0x18002b324  mov     rsp, r11
0x18002b327  pop     rbp
0x18002b328  retn
```
