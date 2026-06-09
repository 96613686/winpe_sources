# EnablePrivilege(ulong,int,int *)

- ea: `0x18002ce54`
- end: `0x18002cf60`
- name: `?EnablePrivilege@@YAKKHPEAH@Z`
- size: `268`
- prototype: `unsigned int __fastcall(unsigned int, int, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002c238`

## callees

- `0x18002ce54`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002ceae`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002ceae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002ce96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002ce96`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002cf09`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002cf09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cebe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cebe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cf33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cf33`

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
0x18002ce54  mov     [rsp-8+arg_0], rbx
0x18002ce59  mov     [rsp-8+arg_8], rdi
0x18002ce5e  push    rbp
0x18002ce5f  mov     rbp, rsp
0x18002ce62  sub     rsp, 70h
0x18002ce66  mov     rax, cs:__security_cookie
0x18002ce6d  xor     rax, rsp
0x18002ce70  mov     [rbp+var_10], rax
0x18002ce74  xorps   xmm0, xmm0
0x18002ce77  mov     [rbp+TokenHandle], 0
0x18002ce7f  xorps   xmm1, xmm1
0x18002ce82  mov     [rbp+var_40], 0
0x18002ce89  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x18002ce8d  mov     rdi, r8
0x18002ce90  mov     ebx, edx
0x18002ce92  movups  xmmword ptr [rbp+var_20.PrivilegeCount], xmm1
0x18002ce96  call    cs:__imp_GetCurrentProcess
0x18002ce9d  nop     dword ptr [rax+rax+00h]
0x18002cea2  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18002cea6  mov     edx, 28h ; '('; DesiredAccess
0x18002ceab  mov     rcx, rax; ProcessHandle
0x18002ceae  call    cs:__imp_OpenProcessToken
0x18002ceb5  nop     dword ptr [rax+rax+00h]
0x18002ceba  test    eax, eax
0x18002cebc  jnz     short loc_18002CECE
0x18002cebe  call    cs:__imp_GetLastError
0x18002cec5  nop     dword ptr [rax+rax+00h]
0x18002ceca  mov     ebx, eax
0x18002cecc  jmp     short loc_18002CF2A
0x18002cece  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002ced2  lea     r8, [rbp+NewState]; NewState
0x18002ced6  neg     ebx
0x18002ced8  mov     [rbp+NewState.PrivilegeCount], 1
0x18002cedf  mov     r9d, 10h; BufferLength
0x18002cee5  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 8
0x18002ceed  sbb     eax, eax
0x18002ceef  xor     edx, edx; DisableAllPrivileges
0x18002cef1  and     eax, 2
0x18002cef4  mov     [rbp+NewState.Privileges.Attributes], eax
0x18002cef7  lea     rax, [rbp+var_40]
0x18002cefb  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18002cf00  lea     rax, [rbp+var_20]
0x18002cf04  mov     [rsp+70h+PreviousState], rax; PreviousState
0x18002cf09  call    cs:__imp_AdjustTokenPrivileges
0x18002cf10  nop     dword ptr [rax+rax+00h]
0x18002cf15  test    eax, eax
0x18002cf17  jz      short loc_18002CEBE
0x18002cf19  xor     ebx, ebx
0x18002cf1b  test    rdi, rdi
0x18002cf1e  jz      short loc_18002CF2A
0x18002cf20  mov     eax, [rbp+var_20.Privileges.Attributes]
0x18002cf23  shr     eax, 1
0x18002cf25  and     eax, 1
0x18002cf28  mov     [rdi], eax
0x18002cf2a  mov     rcx, [rbp+TokenHandle]; hObject
0x18002cf2e  test    rcx, rcx
0x18002cf31  jz      short loc_18002CF3F
0x18002cf33  call    cs:__imp_CloseHandle
0x18002cf3a  nop     dword ptr [rax+rax+00h]
0x18002cf3f  mov     eax, ebx
0x18002cf41  mov     rcx, [rbp+var_10]
0x18002cf45  xor     rcx, rsp; StackCookie
0x18002cf48  call    __security_check_cookie
0x18002cf4d  lea     r11, [rsp+70h+var_s0]
0x18002cf52  mov     rbx, [r11+10h]
0x18002cf56  mov     rdi, [r11+18h]
0x18002cf5a  mov     rsp, r11
0x18002cf5d  pop     rbp
0x18002cf5e  retn
```
