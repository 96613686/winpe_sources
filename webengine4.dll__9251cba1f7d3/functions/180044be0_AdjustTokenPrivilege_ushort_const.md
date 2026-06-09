# AdjustTokenPrivilege(ushort const *)

- ea: `0x180044be0`
- end: `0x180044ca1`
- name: `?AdjustTokenPrivilege@@YAJPEBG@Z`
- size: `193`
- prototype: `__int64 __fastcall(LPCWSTR lpName)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800400a8`

## callees

- `0x180044be0`
- `0x18004d030`
- `0x18004d350`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180044c81`
- `KERNEL32!CloseHandle` at `0x180044c81`
- `KERNEL32!GetCurrentProcess` at `0x180044c03`
- `KERNEL32!GetCurrentProcess` at `0x180044c03`
- `ADVAPI32!OpenProcessToken` at `0x180044c14`
- `ADVAPI32!OpenProcessToken` at `0x180044c14`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180044c66`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180044c66`
- `ADVAPI32!LookupPrivilegeValueW` at `0x180044c28`
- `ADVAPI32!LookupPrivilegeValueW` at `0x180044c28`

## pseudocode

```c
__int64 __fastcall AdjustTokenPrivilege(LPCWSTR lpName)
{
  unsigned int LastWin32Error; // ebx
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-38h] BYREF
  _LUID Luid; // [rsp+38h] [rbp-30h] BYREF
  _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-28h] BYREF

  LastWin32Error = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle)
    || !LookupPrivilegeValueW(0, lpName, &Luid)
    || (NewState.Privileges[0].Luid = Luid,
        NewState.PrivilegeCount = 1,
        NewState.Privileges[0].Attributes = 2,
        !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, 0, 0)) )
  {
    LastWin32Error = GetLastWin32Error();
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastWin32Error;
}

```

## disassembly

```asm
0x180044be0  mov     [rsp+arg_8], rbx
0x180044be5  push    rdi
0x180044be6  sub     rsp, 60h
0x180044bea  mov     rax, cs:__security_cookie
0x180044bf1  xor     rax, rsp
0x180044bf4  mov     [rsp+68h+var_18], rax
0x180044bf9  xor     ebx, ebx
0x180044bfb  mov     rdi, rcx
0x180044bfe  and     [rsp+68h+TokenHandle], rbx
0x180044c03  call    cs:__imp_GetCurrentProcess
0x180044c09  mov     rcx, rax; ProcessHandle
0x180044c0c  lea     r8, [rsp+68h+TokenHandle]; TokenHandle
0x180044c11  lea     edx, [rbx+28h]; DesiredAccess
0x180044c14  call    cs:__imp_OpenProcessToken
0x180044c1a  test    eax, eax
0x180044c1c  jz      short loc_180044C70
0x180044c1e  lea     r8, [rsp+68h+Luid]; lpLuid
0x180044c23  mov     rdx, rdi; lpName
0x180044c26  xor     ecx, ecx; lpSystemName
0x180044c28  call    cs:__imp_LookupPrivilegeValueW
0x180044c2e  test    eax, eax
0x180044c30  jz      short loc_180044C70
0x180044c32  mov     rax, qword ptr [rsp+68h+Luid.LowPart]
0x180044c37  lea     r9d, [rbx+10h]; BufferLength
0x180044c3b  and     [rsp+68h+var_40], rbx
0x180044c40  lea     r8, [rsp+68h+NewState]; NewState
0x180044c45  mov     rcx, [rsp+68h+TokenHandle]; TokenHandle
0x180044c4a  xor     edx, edx; DisableAllPrivileges
0x180044c4c  and     [rsp+68h+var_48], rbx
0x180044c51  mov     qword ptr [rsp+68h+NewState.Privileges.Luid.LowPart], rax
0x180044c56  mov     [rsp+68h+NewState.PrivilegeCount], 1
0x180044c5e  mov     [rsp+68h+NewState.Privileges.Attributes], 2
0x180044c66  call    cs:__imp_AdjustTokenPrivileges
0x180044c6c  test    eax, eax
0x180044c6e  jnz     short loc_180044C77
0x180044c70  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180044c75  mov     ebx, eax
0x180044c77  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x180044c7c  test    rcx, rcx
0x180044c7f  jz      short loc_180044C87
0x180044c81  call    cs:__imp_CloseHandle
0x180044c87  mov     eax, ebx
0x180044c89  mov     rcx, [rsp+68h+var_18]
0x180044c8e  xor     rcx, rsp; StackCookie
0x180044c91  call    __security_check_cookie
0x180044c96  mov     rbx, [rsp+68h+arg_8]
0x180044c9b  add     rsp, 60h
0x180044c9f  pop     rdi
0x180044ca0  retn
```
