# DebugPriv(void)

- ea: `0x18004a330`
- end: `0x18004a3b7`
- name: `?DebugPriv@@YAXXZ`
- size: `135`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18004a85c`

## callees

- `0x18004a330`
- `0x18004d030`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18004a39f`
- `KERNEL32!CloseHandle` at `0x18004a39f`
- `KERNEL32!GetCurrentProcess` at `0x18004a343`
- `KERNEL32!GetCurrentProcess` at `0x18004a343`
- `ADVAPI32!OpenProcessToken` at `0x18004a356`
- `ADVAPI32!OpenProcessToken` at `0x18004a356`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18004a394`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18004a394`

## pseudocode

```c
void DebugPriv(void)
{
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-30h] BYREF

  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x2000000u, &TokenHandle) )
  {
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Luid = (LUID)20LL;
    NewState.Privileges[0].Attributes = 2;
    AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0);
    CloseHandle(TokenHandle);
  }
}

```

## disassembly

```asm
0x18004a330  sub     rsp, 68h
0x18004a334  mov     rax, cs:__security_cookie
0x18004a33b  xor     rax, rsp
0x18004a33e  mov     [rsp+68h+var_10], rax
0x18004a343  call    cs:__imp_GetCurrentProcess
0x18004a349  lea     r8, [rsp+68h+TokenHandle]; TokenHandle
0x18004a34e  mov     edx, 2000000h; DesiredAccess
0x18004a353  mov     rcx, rax; ProcessHandle
0x18004a356  call    cs:__imp_OpenProcessToken
0x18004a35c  xor     ecx, ecx
0x18004a35e  test    eax, eax
0x18004a360  jz      short loc_18004A3A5
0x18004a362  mov     [rsp+68h+ReturnLength], rcx; ReturnLength
0x18004a367  lea     r8, [rsp+68h+NewState]; NewState
0x18004a36c  mov     [rsp+68h+PreviousState], rcx; PreviousState
0x18004a371  xor     r9d, r9d; BufferLength
0x18004a374  mov     rcx, [rsp+68h+TokenHandle]; TokenHandle
0x18004a379  xor     edx, edx; DisableAllPrivileges
0x18004a37b  mov     [rsp+68h+NewState.PrivilegeCount], 1
0x18004a383  mov     qword ptr [rsp+68h+NewState.Privileges.Luid.LowPart], 14h
0x18004a38c  mov     [rsp+68h+NewState.Privileges.Attributes], 2
0x18004a394  call    cs:__imp_AdjustTokenPrivileges
0x18004a39a  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x18004a39f  call    cs:__imp_CloseHandle
0x18004a3a5  mov     rcx, [rsp+68h+var_10]
0x18004a3aa  xor     rcx, rsp; StackCookie
0x18004a3ad  call    __security_check_cookie
0x18004a3b2  add     rsp, 68h
0x18004a3b6  retn
```
