# WinSAT::ManagePrivilege::AdjustProcessPrivilege(ulong,int)

- ea: `0x140060688`
- end: `0x140060730`
- name: `?AdjustProcessPrivilege@ManagePrivilege@WinSAT@@AEAAKKH@Z`
- size: `168`
- prototype: `DWORD __fastcall(WinSAT::ManagePrivilege *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140061600`

## callees

- `0x140060688`
- `0x140113220`

## import_xrefs

- `ADVAPI32!AdjustTokenPrivileges` at `0x140060712`
- `ADVAPI32!AdjustTokenPrivileges` at `0x140060712`
- `ADVAPI32!OpenThreadToken` at `0x1400606c1`
- `ADVAPI32!OpenThreadToken` at `0x1400606c1`
- `KERNEL32!GetCurrentThread` at `0x1400606ac`
- `KERNEL32!GetCurrentThread` at `0x1400606ac`
- `KERNEL32!GetLastError` at `0x140060718`
- `KERNEL32!GetLastError` at `0x140060718`

## pseudocode

```c
// Hidden C++ exception states: #wind=86
DWORD __fastcall WinSAT::ManagePrivilege::AdjustProcessPrivilege(WinSAT::ManagePrivilege *this)
{
  HANDLE CurrentThread; // rax
  void *TokenHandle; // [rsp+38h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-28h] BYREF

  TokenHandle = 0;
  NewState = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x20u, 0, &TokenHandle) )
  {
    NewState.Privileges[0].Luid = (LUID)28LL;
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Attributes = 2;
    AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, 0, 0);
  }
  return GetLastError();
}

```

## disassembly

```asm
0x140060688  sub     rsp, 68h
0x14006068c  mov     rax, cs:__security_cookie
0x140060693  xor     rax, rsp
0x140060696  mov     [rsp+68h+var_18], rax
0x14006069b  xorps   xmm0, xmm0
0x14006069e  mov     [rsp+68h+TokenHandle], 0
0x1400606a7  movups  xmmword ptr [rsp+68h+NewState.PrivilegeCount], xmm0
0x1400606ac  call    cs:__imp_GetCurrentThread
0x1400606b2  xor     r8d, r8d; OpenAsSelf
0x1400606b5  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x1400606ba  mov     rcx, rax; ThreadHandle
0x1400606bd  lea     edx, [r8+20h]; DesiredAccess
0x1400606c1  call    cs:__imp_OpenThreadToken
0x1400606c7  test    eax, eax
0x1400606c9  jz      short loc_140060718
0x1400606cb  mov     rcx, [rsp+68h+TokenHandle]; TokenHandle
0x1400606d0  lea     r8, [rsp+68h+NewState]; NewState
0x1400606d5  mov     [rsp+68h+var_38], 1Ch
0x1400606de  mov     r9d, 10h; BufferLength
0x1400606e4  mov     rax, [rsp+68h+var_38]
0x1400606e9  xor     edx, edx; DisableAllPrivileges
0x1400606eb  mov     [rsp+68h+ReturnLength], 0; ReturnLength
0x1400606f4  mov     qword ptr [rsp+68h+NewState.Privileges.Luid.LowPart], rax
0x1400606f9  mov     [rsp+68h+NewState.PrivilegeCount], 1
0x140060701  mov     [rsp+68h+NewState.Privileges.Attributes], 2
0x140060709  mov     [rsp+68h+PreviousState], 0; PreviousState
0x140060712  call    cs:__imp_AdjustTokenPrivileges
0x140060718  call    cs:__imp_GetLastError
0x14006071e  mov     rcx, [rsp+68h+var_18]
0x140060723  xor     rcx, rsp; StackCookie
0x140060726  call    __security_check_cookie
0x14006072b  add     rsp, 68h
0x14006072f  retn
```
