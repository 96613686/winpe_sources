# EnablePrivilegeInternal

- ea: `0x18000c2b0`
- end: `0x18000c3a7`
- name: `EnablePrivilegeInternal`
- size: `247`
- prototype: `__int64 __fastcall(LUID, DWORD, DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c254`

## callees

- `0x18000c2b0`
- `0x1800131e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c354`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c354`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c37e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c37e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c2f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c2f7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000c307`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000c307`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000c34a`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000c34a`

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
0x18000c2b0  mov     [rsp-18h+arg_8], rbx
0x18000c2b5  mov     [rsp-18h+arg_18], rsi
0x18000c2ba  push    rbp
0x18000c2bb  push    rdi
0x18000c2bc  push    r14
0x18000c2be  mov     rbp, rsp
0x18000c2c1  sub     rsp, 70h
0x18000c2c5  mov     rax, cs:__security_cookie
0x18000c2cc  xor     rax, rsp
0x18000c2cf  mov     [rbp+var_10], rax
0x18000c2d3  xorps   xmm0, xmm0
0x18000c2d6  mov     [rbp+TokenHandle], 0
0x18000c2de  xorps   xmm1, xmm1
0x18000c2e1  xor     edi, edi
0x18000c2e3  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x18000c2e7  mov     [rbp+var_40], edi
0x18000c2ea  mov     rsi, r8
0x18000c2ed  movups  xmmword ptr [rbp+var_20.PrivilegeCount], xmm1
0x18000c2f1  mov     r14d, edx
0x18000c2f4  mov     rbx, rcx
0x18000c2f7  call    cs:__imp_GetCurrentProcess
0x18000c2fd  mov     rcx, rax; ProcessHandle
0x18000c300  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000c304  lea     edx, [rdi+28h]; DesiredAccess
0x18000c307  call    cs:__imp_OpenProcessToken
0x18000c30d  test    eax, eax
0x18000c30f  jz      short loc_18000C384
0x18000c311  mov     eax, r14d
0x18000c314  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rbx
0x18000c318  neg     eax
0x18000c31a  lea     r8, [rbp+NewState]; NewState
0x18000c31e  mov     edi, 1
0x18000c323  lea     rax, [rbp+var_40]
0x18000c327  sbb     ecx, ecx
0x18000c329  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18000c32e  and     ecx, 2
0x18000c331  mov     [rbp+NewState.PrivilegeCount], edi
0x18000c334  mov     [rbp+NewState.Privileges.Attributes], ecx
0x18000c337  lea     rax, [rbp+var_20]
0x18000c33b  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000c33f  lea     r9d, [rdi+0Fh]; BufferLength
0x18000c343  xor     edx, edx; DisableAllPrivileges
0x18000c345  mov     [rsp+70h+PreviousState], rax; PreviousState
0x18000c34a  call    cs:__imp_AdjustTokenPrivileges
0x18000c350  test    eax, eax
0x18000c352  jz      short loc_18000C378
0x18000c354  call    cs:__imp_GetLastError
0x18000c35a  test    eax, eax
0x18000c35c  jnz     short loc_18000C378
0x18000c35e  test    rsi, rsi
0x18000c361  jz      short loc_18000C37A
0x18000c363  cmp     [rbp+var_20.PrivilegeCount], eax
0x18000c366  jnz     short loc_18000C36D
0x18000c368  mov     [rsi], r14d
0x18000c36b  jmp     short loc_18000C37A
0x18000c36d  mov     eax, [rbp+var_20.Privileges.Attributes]
0x18000c370  shr     eax, 1
0x18000c372  and     eax, edi
0x18000c374  mov     [rsi], eax
0x18000c376  jmp     short loc_18000C37A
0x18000c378  xor     edi, edi
0x18000c37a  mov     rcx, [rbp+TokenHandle]; hObject
0x18000c37e  call    cs:__imp_CloseHandle
0x18000c384  mov     eax, edi
0x18000c386  mov     rcx, [rbp+var_10]
0x18000c38a  xor     rcx, rsp; StackCookie
0x18000c38d  call    __security_check_cookie
0x18000c392  lea     r11, [rsp+70h+var_s0]
0x18000c397  mov     rbx, [r11+28h]
0x18000c39b  mov     rsi, [r11+38h]
0x18000c39f  mov     rsp, r11
0x18000c3a2  pop     r14
0x18000c3a4  pop     rdi
0x18000c3a5  pop     rbp
0x18000c3a6  retn
```
