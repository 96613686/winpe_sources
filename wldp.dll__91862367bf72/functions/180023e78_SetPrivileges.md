# SetPrivileges

- ea: `0x180023e78`
- end: `0x180023fc7`
- name: `SetPrivileges`
- size: `335`
- prototype: `__int64 __fastcall(void **, struct _TOKEN_PRIVILEGES *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023cd0`
- `0x180024430`

## callees

- `0x180021ec0`
- `0x180023e78`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023ebf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023ebf`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180023f15`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180023f15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023f03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023f03`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180023ed5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180023ed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ee5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023f74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ee5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023f74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023f93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023f93`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180023f6a`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180023f6a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180023f2c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180023f2c`

## string_xrefs

- `0x180023f25`: `SeSystemEnvironmentPrivilege`

## pseudocode

```c
__int64 __fastcall SetPrivileges(void **a1, struct _TOKEN_PRIVILEGES *a2)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v6; // ebx
  HANDLE CurrentProcess; // rax
  signed int v8; // eax
  void *TokenHandle; // [rsp+30h] [rbp-30h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-28h] BYREF
  struct _LUID Luid; // [rsp+40h] [rbp-20h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+48h] [rbp-18h] BYREF

  Luid = 0;
  NewState = 0;
  TokenHandle = 0;
  ReturnLength = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x28u, 1, &TokenHandle) )
    goto LABEL_6;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    {
LABEL_8:
      v8 = GetLastError();
      v6 = v8;
      if ( v8 > 0 )
        v6 = (unsigned __int16)v8 | 0x80070000;
      goto LABEL_10;
    }
LABEL_6:
    if ( LookupPrivilegeValueW(0, L"SeSystemEnvironmentPrivilege", &Luid) )
    {
      NewState.Privileges[0].Luid = Luid;
      NewState.PrivilegeCount = 1;
      NewState.Privileges[0].Attributes = 2;
      if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, a2, &ReturnLength) )
      {
        v6 = 0;
        goto LABEL_14;
      }
    }
    goto LABEL_8;
  }
LABEL_10:
  if ( (v6 & 0x80000000) == 0 )
  {
LABEL_14:
    *a1 = TokenHandle;
    return v6;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v6;
}

```

## disassembly

```asm
0x180023e78  mov     [rsp-18h+arg_10], rbx
0x180023e7d  mov     [rsp-18h+arg_18], rsi
0x180023e82  push    rbp
0x180023e83  push    rdi
0x180023e84  push    r15
0x180023e86  mov     rbp, rsp
0x180023e89  sub     rsp, 60h
0x180023e8d  mov     rax, cs:__security_cookie
0x180023e94  xor     rax, rsp
0x180023e97  mov     [rbp+var_8], rax
0x180023e9b  xorps   xmm0, xmm0
0x180023e9e  mov     qword ptr [rbp+Luid.LowPart], 0
0x180023ea6  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x180023eaa  mov     rdi, rdx
0x180023ead  mov     [rbp+TokenHandle], 0
0x180023eb5  mov     rsi, rcx
0x180023eb8  mov     [rbp+var_28], 0
0x180023ebf  call    cs:__imp_GetCurrentThread
0x180023ec5  mov     edx, 28h ; '('; DesiredAccess
0x180023eca  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180023ece  mov     rcx, rax; ThreadHandle
0x180023ed1  lea     r8d, [rdx-27h]; OpenAsSelf
0x180023ed5  call    cs:__imp_OpenThreadToken
0x180023edb  mov     r15d, 80070000h
0x180023ee1  test    eax, eax
0x180023ee3  jnz     short loc_180023F1F
0x180023ee5  call    cs:__imp_GetLastError
0x180023eeb  mov     ebx, eax
0x180023eed  test    eax, eax
0x180023eef  jle     short loc_180023EF7
0x180023ef1  movzx   ebx, ax
0x180023ef4  or      ebx, r15d
0x180023ef7  cmp     ebx, 800703F0h
0x180023efd  jnz     loc_180023F86
0x180023f03  call    cs:__imp_GetCurrentProcess
0x180023f09  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180023f0d  mov     edx, 28h ; '('; DesiredAccess
0x180023f12  mov     rcx, rax; ProcessHandle
0x180023f15  call    cs:__imp_OpenProcessToken
0x180023f1b  test    eax, eax
0x180023f1d  jz      short loc_180023F74
0x180023f1f  lea     r8, [rbp+Luid]; lpLuid
0x180023f23  xor     ecx, ecx; lpSystemName
0x180023f25  lea     rdx, Name; "SeSystemEnvironmentPrivilege"
0x180023f2c  call    cs:__imp_LookupPrivilegeValueW
0x180023f32  test    eax, eax
0x180023f34  jz      short loc_180023F74
0x180023f36  mov     rax, qword ptr [rbp+Luid.LowPart]
0x180023f3a  lea     r8, [rbp+NewState]; NewState
0x180023f3e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180023f42  mov     r9d, 10h; BufferLength
0x180023f48  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x180023f4c  xor     edx, edx; DisableAllPrivileges
0x180023f4e  lea     rax, [rbp+var_28]
0x180023f52  mov     [rbp+NewState.PrivilegeCount], 1
0x180023f59  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180023f5e  mov     [rsp+60h+PreviousState], rdi; PreviousState
0x180023f63  mov     [rbp+NewState.Privileges.Attributes], 2
0x180023f6a  call    cs:__imp_AdjustTokenPrivileges
0x180023f70  test    eax, eax
0x180023f72  jnz     short loc_180023F9B
0x180023f74  call    cs:__imp_GetLastError
0x180023f7a  mov     ebx, eax
0x180023f7c  test    eax, eax
0x180023f7e  jle     short loc_180023F86
0x180023f80  movzx   ebx, ax
0x180023f83  or      ebx, r15d
0x180023f86  test    ebx, ebx
0x180023f88  jns     short loc_180023F9D
0x180023f8a  mov     rcx, [rbp+TokenHandle]; hObject
0x180023f8e  test    rcx, rcx
0x180023f91  jz      short loc_180023FA4
0x180023f93  call    cs:__imp_CloseHandle
0x180023f99  jmp     short loc_180023FA4
0x180023f9b  xor     ebx, ebx
0x180023f9d  mov     rcx, [rbp+TokenHandle]
0x180023fa1  mov     [rsi], rcx
0x180023fa4  mov     eax, ebx
0x180023fa6  mov     rcx, [rbp+var_8]
0x180023faa  xor     rcx, rsp; StackCookie
0x180023fad  call    __security_check_cookie
0x180023fb2  lea     r11, [rsp+60h+var_s0]
0x180023fb7  mov     rbx, [r11+30h]
0x180023fbb  mov     rsi, [r11+38h]
0x180023fbf  mov     rsp, r11
0x180023fc2  pop     r15
0x180023fc4  pop     rdi
0x180023fc5  pop     rbp
0x180023fc6  retn
```
