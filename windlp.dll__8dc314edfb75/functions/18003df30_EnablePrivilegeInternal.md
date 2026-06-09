# EnablePrivilegeInternal

- ea: `0x18003df30`
- end: `0x18003e027`
- name: `EnablePrivilegeInternal`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003ded4`

## callees

- `0x18003df30`
- `0x18007ed40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003df77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003df77`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003df87`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003df87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dfd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dfd4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003dffe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003dffe`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18003dfca`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18003dfca`

## pseudocode

```c
__int64 __fastcall EnablePrivilegeInternal(LUID a1, DWORD a2, DWORD *a3)
{
  unsigned int v3; // edi
  HANDLE CurrentProcess; // rax
  DWORD ReturnLength; // [rsp+30h] [rbp-40h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+50h] [rbp-20h] BYREF

  TokenHandle = 0;
  v3 = 0;
  NewState = 0;
  ReturnLength = 0;
  PreviousState = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    NewState.Privileges[0].Luid = a1;
    v3 = 1;
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Attributes = a2 != 0 ? 2 : 0;
    if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &ReturnLength) || GetLastError() )
    {
      v3 = 0;
    }
    else if ( a3 )
    {
      if ( PreviousState.PrivilegeCount )
        *a3 = (PreviousState.Privileges[0].Attributes >> 1) & 1;
      else
        *a3 = a2;
    }
    CloseHandle(TokenHandle);
  }
  return v3;
}

```

## disassembly

```asm
0x18003df30  mov     [rsp-18h+arg_8], rbx
0x18003df35  mov     [rsp-18h+arg_18], rsi
0x18003df3a  push    rbp
0x18003df3b  push    rdi
0x18003df3c  push    r14
0x18003df3e  mov     rbp, rsp
0x18003df41  sub     rsp, 70h
0x18003df45  mov     rax, cs:__security_cookie
0x18003df4c  xor     rax, rsp
0x18003df4f  mov     [rbp+var_10], rax
0x18003df53  xorps   xmm0, xmm0
0x18003df56  mov     [rbp+TokenHandle], 0
0x18003df5e  xorps   xmm1, xmm1
0x18003df61  xor     edi, edi
0x18003df63  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x18003df67  mov     [rbp+var_40], edi
0x18003df6a  mov     rsi, r8
0x18003df6d  movups  xmmword ptr [rbp+var_20.PrivilegeCount], xmm1
0x18003df71  mov     r14d, edx
0x18003df74  mov     rbx, rcx
0x18003df77  call    cs:__imp_GetCurrentProcess
0x18003df7d  mov     rcx, rax; ProcessHandle
0x18003df80  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18003df84  lea     edx, [rdi+28h]; DesiredAccess
0x18003df87  call    cs:__imp_OpenProcessToken
0x18003df8d  test    eax, eax
0x18003df8f  jz      short loc_18003E004
0x18003df91  mov     eax, r14d
0x18003df94  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rbx
0x18003df98  neg     eax
0x18003df9a  lea     r8, [rbp+NewState]; NewState
0x18003df9e  mov     edi, 1
0x18003dfa3  lea     rax, [rbp+var_40]
0x18003dfa7  sbb     ecx, ecx
0x18003dfa9  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18003dfae  and     ecx, 2
0x18003dfb1  mov     [rbp+NewState.PrivilegeCount], edi
0x18003dfb4  mov     [rbp+NewState.Privileges.Attributes], ecx
0x18003dfb7  lea     rax, [rbp+var_20]
0x18003dfbb  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18003dfbf  lea     r9d, [rdi+0Fh]; BufferLength
0x18003dfc3  xor     edx, edx; DisableAllPrivileges
0x18003dfc5  mov     [rsp+70h+PreviousState], rax; PreviousState
0x18003dfca  call    cs:__imp_AdjustTokenPrivileges
0x18003dfd0  test    eax, eax
0x18003dfd2  jz      short loc_18003DFF8
0x18003dfd4  call    cs:__imp_GetLastError
0x18003dfda  test    eax, eax
0x18003dfdc  jnz     short loc_18003DFF8
0x18003dfde  test    rsi, rsi
0x18003dfe1  jz      short loc_18003DFFA
0x18003dfe3  cmp     [rbp+var_20.PrivilegeCount], eax
0x18003dfe6  jnz     short loc_18003DFED
0x18003dfe8  mov     [rsi], r14d
0x18003dfeb  jmp     short loc_18003DFFA
0x18003dfed  mov     eax, [rbp+var_20.Privileges.Attributes]
0x18003dff0  shr     eax, 1
0x18003dff2  and     eax, edi
0x18003dff4  mov     [rsi], eax
0x18003dff6  jmp     short loc_18003DFFA
0x18003dff8  xor     edi, edi
0x18003dffa  mov     rcx, [rbp+TokenHandle]; hObject
0x18003dffe  call    cs:__imp_CloseHandle
0x18003e004  mov     eax, edi
0x18003e006  mov     rcx, [rbp+var_10]
0x18003e00a  xor     rcx, rsp; StackCookie
0x18003e00d  call    __security_check_cookie
0x18003e012  lea     r11, [rsp+70h+var_s0]
0x18003e017  mov     rbx, [r11+28h]
0x18003e01b  mov     rsi, [r11+38h]
0x18003e01f  mov     rsp, r11
0x18003e022  pop     r14
0x18003e024  pop     rdi
0x18003e025  pop     rbp
0x18003e026  retn
```
