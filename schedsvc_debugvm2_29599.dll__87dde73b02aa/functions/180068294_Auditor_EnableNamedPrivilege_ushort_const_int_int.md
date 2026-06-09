# Auditor::EnableNamedPrivilege(ushort const *,int,int *)

- ea: `0x180068294`
- end: `0x18006838f`
- name: `?EnableNamedPrivilege@Auditor@@AEAAKPEBGHPEAH@Z`
- size: `251`
- prototype: `unsigned int __fastcall(Auditor *__hidden this, const unsigned __int16 *, int, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180068398`

## callees

- `0x18006818c`
- `0x18006825c`
- `0x180068294`
- `0x18007e6d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068307`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068307`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800682d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800682d7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800682e9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800682e9`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180068341`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180068341`

## string_xrefs

- `0x1800682f7`: `SeAuditPrivilege`

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
0x180068294  mov     [rsp-8+arg_0], rbx
0x180068299  push    rbp
0x18006829a  mov     rbp, rsp
0x18006829d  sub     rsp, 70h
0x1800682a1  mov     rax, cs:__security_cookie
0x1800682a8  xor     rax, rsp
0x1800682ab  mov     [rbp+var_8], rax
0x1800682af  xorps   xmm0, xmm0
0x1800682b2  mov     [rbp+var_40], 0
0x1800682b9  xorps   xmm1, xmm1
0x1800682bc  mov     [rbp+TokenHandle], 0
0x1800682c4  lea     rax, [rbp+TokenHandle]
0x1800682c8  mov     rbx, r9
0x1800682cb  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x1800682cf  mov     [rbp+var_30], rax
0x1800682d3  movups  xmmword ptr [rbp+var_18.PrivilegeCount], xmm1
0x1800682d7  call    cs:__imp_GetCurrentProcess
0x1800682dd  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800682e1  mov     edx, 28h ; '('; DesiredAccess
0x1800682e6  mov     rcx, rax; ProcessHandle
0x1800682e9  call    cs:__imp_OpenProcessToken
0x1800682ef  test    eax, eax
0x1800682f1  jz      short loc_180068307
0x1800682f3  lea     rdx, [rbp+NewState.Privileges]; lpLuid
0x1800682f7  lea     rcx, aSeauditprivile; "SeAuditPrivilege"
0x1800682fe  call    ?LookupPrivilege@User@@SAHPEBGAEAU_LUID@@@Z; User::LookupPrivilege(ushort const *,_LUID &)
0x180068303  test    eax, eax
0x180068305  jnz     short loc_180068311
0x180068307  call    cs:__imp_GetLastError
0x18006830d  mov     ebx, eax
0x18006830f  jmp     short loc_18006836A
0x180068311  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180068315  lea     rax, [rbp+var_40]
0x180068319  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18006831e  lea     r8, [rbp+NewState]; NewState
0x180068322  lea     rax, [rbp+var_18]
0x180068326  mov     [rbp+NewState.Privileges.Attributes], 2
0x18006832d  mov     r9d, 10h; BufferLength
0x180068333  mov     [rsp+70h+PreviousState], rax; PreviousState
0x180068338  xor     edx, edx; DisableAllPrivileges
0x18006833a  mov     [rbp+NewState.PrivilegeCount], 1
0x180068341  call    cs:__imp_AdjustTokenPrivileges
0x180068347  test    eax, eax
0x180068349  jz      short loc_180068307
0x18006834b  test    rbx, rbx
0x18006834e  jz      short loc_180068368
0x180068350  cmp     [rbp+var_18.PrivilegeCount], 0
0x180068354  jnz     short loc_18006835E
0x180068356  mov     dword ptr [rbx], 1
0x18006835c  jmp     short loc_180068368
0x18006835e  mov     eax, [rbp+var_18.Privileges.Attributes]
0x180068361  shr     eax, 1
0x180068363  and     eax, 1
0x180068366  mov     [rbx], eax
0x180068368  xor     ebx, ebx
0x18006836a  lea     rcx, [rbp+var_30]; this
0x18006836e  call    ??1HandleFree@tsched@@QEAA@XZ; tsched::HandleFree::~HandleFree(void)
0x180068373  mov     eax, ebx
0x180068375  mov     rcx, [rbp+var_8]
0x180068379  xor     rcx, rsp; StackCookie
0x18006837c  call    __security_check_cookie
0x180068381  mov     rbx, [rsp+70h+arg_0]
0x180068389  add     rsp, 70h
0x18006838d  pop     rbp
0x18006838e  retn
```
