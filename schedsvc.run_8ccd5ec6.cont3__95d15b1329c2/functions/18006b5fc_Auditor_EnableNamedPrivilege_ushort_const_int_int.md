# Auditor::EnableNamedPrivilege(ushort const *,int,int *)

- ea: `0x18006b5fc`
- end: `0x18006b710`
- name: `?EnableNamedPrivilege@Auditor@@AEAAKPEBGHPEAH@Z`
- size: `276`
- prototype: `unsigned int __fastcall(Auditor *__hidden this, const unsigned __int16 *, int, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006b718`

## callees

- `0x18006b4d0`
- `0x18006b5c0`
- `0x18006b5fc`
- `0x180082a40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b67b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b67b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006b63f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006b63f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18006b657`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18006b657`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18006b6bb`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18006b6bb`

## string_xrefs

- `0x18006b66b`: `SeAuditPrivilege`

## pseudocode

```c
__int64 __fastcall Auditor::EnableNamedPrivilege(Auditor *this, const unsigned __int16 *a2, __int64 a3, DWORD *a4)
{
  HANDLE CurrentProcess; // rax
  DWORD LastError; // ebx
  DWORD ReturnLength; // [rsp+30h] [rbp-40h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-38h] BYREF
  void **p_TokenHandle; // [rsp+40h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+48h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+58h] [rbp-18h] BYREF

  ReturnLength = 0;
  TokenHandle = 0;
  NewState = 0;
  p_TokenHandle = &TokenHandle;
  PreviousState = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle)
    && (unsigned int)User::LookupPrivilege(L"SeAuditPrivilege", &NewState.Privileges[0].Luid)
    && (NewState.Privileges[0].Attributes = 2,
        NewState.PrivilegeCount = 1,
        AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &ReturnLength)) )
  {
    if ( a4 )
    {
      if ( PreviousState.PrivilegeCount )
        *a4 = (PreviousState.Privileges[0].Attributes >> 1) & 1;
      else
        *a4 = 1;
    }
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
  }
  tsched::HandleFree::~HandleFree((tsched::HandleFree *)&p_TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x18006b5fc  mov     [rsp-8+arg_0], rbx
0x18006b601  push    rbp
0x18006b602  mov     rbp, rsp
0x18006b605  sub     rsp, 70h
0x18006b609  mov     rax, cs:__security_cookie
0x18006b610  xor     rax, rsp
0x18006b613  mov     [rbp+var_8], rax
0x18006b617  xorps   xmm0, xmm0
0x18006b61a  mov     [rbp+var_40], 0
0x18006b621  xorps   xmm1, xmm1
0x18006b624  mov     [rbp+TokenHandle], 0
0x18006b62c  lea     rax, [rbp+TokenHandle]
0x18006b630  mov     rbx, r9
0x18006b633  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x18006b637  mov     [rbp+var_30], rax
0x18006b63b  movups  xmmword ptr [rbp+var_18.PrivilegeCount], xmm1
0x18006b63f  call    cs:__imp_GetCurrentProcess
0x18006b646  nop     dword ptr [rax+rax+00h]
0x18006b64b  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18006b64f  mov     edx, 28h ; '('; DesiredAccess
0x18006b654  mov     rcx, rax; ProcessHandle
0x18006b657  call    cs:__imp_OpenProcessToken
0x18006b65e  nop     dword ptr [rax+rax+00h]
0x18006b663  test    eax, eax
0x18006b665  jz      short loc_18006B67B
0x18006b667  lea     rdx, [rbp+NewState.Privileges]; lpLuid
0x18006b66b  lea     rcx, aSeauditprivile; "SeAuditPrivilege"
0x18006b672  call    ?LookupPrivilege@User@@SAHPEBGAEAU_LUID@@@Z; User::LookupPrivilege(ushort const *,_LUID &)
0x18006b677  test    eax, eax
0x18006b679  jnz     short loc_18006B68B
0x18006b67b  call    cs:__imp_GetLastError
0x18006b682  nop     dword ptr [rax+rax+00h]
0x18006b687  mov     ebx, eax
0x18006b689  jmp     short loc_18006B6EA
0x18006b68b  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18006b68f  lea     rax, [rbp+var_40]
0x18006b693  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18006b698  lea     r8, [rbp+NewState]; NewState
0x18006b69c  lea     rax, [rbp+var_18]
0x18006b6a0  mov     [rbp+NewState.Privileges.Attributes], 2
0x18006b6a7  mov     r9d, 10h; BufferLength
0x18006b6ad  mov     [rsp+70h+PreviousState], rax; PreviousState
0x18006b6b2  xor     edx, edx; DisableAllPrivileges
0x18006b6b4  mov     [rbp+NewState.PrivilegeCount], 1
0x18006b6bb  call    cs:__imp_AdjustTokenPrivileges
0x18006b6c2  nop     dword ptr [rax+rax+00h]
0x18006b6c7  test    eax, eax
0x18006b6c9  jz      short loc_18006B67B
0x18006b6cb  test    rbx, rbx
0x18006b6ce  jz      short loc_18006B6E8
0x18006b6d0  cmp     [rbp+var_18.PrivilegeCount], 0
0x18006b6d4  jnz     short loc_18006B6DE
0x18006b6d6  mov     dword ptr [rbx], 1
0x18006b6dc  jmp     short loc_18006B6E8
0x18006b6de  mov     eax, [rbp+var_18.Privileges.Attributes]
0x18006b6e1  shr     eax, 1
0x18006b6e3  and     eax, 1
0x18006b6e6  mov     [rbx], eax
0x18006b6e8  xor     ebx, ebx
0x18006b6ea  lea     rcx, [rbp+var_30]; this
0x18006b6ee  call    ??1HandleFree@tsched@@QEAA@XZ; tsched::HandleFree::~HandleFree(void)
0x18006b6f3  mov     eax, ebx
0x18006b6f5  mov     rcx, [rbp+var_8]
0x18006b6f9  xor     rcx, rsp; StackCookie
0x18006b6fc  call    __security_check_cookie
0x18006b701  mov     rbx, [rsp+70h+arg_0]
0x18006b709  add     rsp, 70h
0x18006b70d  pop     rbp
0x18006b70e  retn
```
