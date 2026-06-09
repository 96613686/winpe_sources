# SetPrivilege(void *,ushort const *,int)

- ea: `0x18003b188`
- end: `0x18003b29c`
- name: `?SetPrivilege@@YAJPEAXPEBGH@Z`
- size: `276`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18003b000`

## callees

- `0x180001600`
- `0x18003b188`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003b1d6`
- `KERNEL32!GetLastError` at `0x18003b245`
- `KERNEL32!GetLastError` at `0x18003b281`
- `KERNEL32!GetLastError` at `0x18003b1d6`
- `KERNEL32!GetLastError` at `0x18003b245`
- `KERNEL32!GetLastError` at `0x18003b281`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18003b23f`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18003b27b`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18003b23f`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18003b27b`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18003b1cc`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18003b1cc`

## pseudocode

```c
__int64 __fastcall SetPrivilege(HANDLE TokenHandle, const unsigned __int16 *a2)
{
  signed int LastError; // eax
  unsigned int v4; // ebx
  bool v5; // cc
  DWORD BufferLength; // [rsp+30h] [rbp-40h] BYREF
  _LUID Luid; // [rsp+38h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+40h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+50h] [rbp-20h] BYREF

  Luid = 0;
  NewState = 0;
  BufferLength = 16;
  PreviousState = 0;
  if ( LookupPrivilegeValueW(0, a2, &Luid) )
  {
    NewState.Privileges[0].Luid = Luid;
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Attributes = 0;
    AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &BufferLength);
    LastError = GetLastError();
    v4 = LastError;
    v5 = LastError <= 0;
    if ( !LastError )
    {
      PreviousState.Privileges[0].Attributes |= 2u;
      PreviousState.Privileges[0].Luid = Luid;
      PreviousState.PrivilegeCount = 1;
      AdjustTokenPrivileges(TokenHandle, 0, &PreviousState, BufferLength, 0, 0);
      LastError = GetLastError();
      if ( !LastError )
        return v4;
      if ( LastError <= 0 )
        return (unsigned int)LastError;
      return (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    v5 = LastError <= 0;
  }
  if ( !v5 )
    return (unsigned __int16)LastError | 0x80070000;
  return v4;
}

```

## disassembly

```asm
0x18003b188  mov     [rsp-8+arg_10], rbx
0x18003b18d  mov     [rsp-8+arg_18], rdi
0x18003b192  push    rbp
0x18003b193  mov     rbp, rsp
0x18003b196  sub     rsp, 70h
0x18003b19a  mov     rax, cs:__security_cookie
0x18003b1a1  xor     rax, rsp
0x18003b1a4  mov     [rbp+var_10], rax
0x18003b1a8  xorps   xmm0, xmm0
0x18003b1ab  mov     qword ptr [rbp+Luid.LowPart], 0
0x18003b1b3  mov     rdi, rcx
0x18003b1b6  lea     r8, [rbp+Luid]; lpLuid
0x18003b1ba  mov     ebx, 10h
0x18003b1bf  xor     ecx, ecx; lpSystemName
0x18003b1c1  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x18003b1c5  mov     [rbp+BufferLength], ebx
0x18003b1c8  movups  xmmword ptr [rbp+var_30.PrivilegeCount], xmm0
0x18003b1cc  call    cs:__imp_LookupPrivilegeValueW
0x18003b1d2  test    eax, eax
0x18003b1d4  jnz     short loc_18003B20B
0x18003b1d6  call    cs:__imp_GetLastError
0x18003b1dc  mov     ebx, eax
0x18003b1de  test    eax, eax
0x18003b1e0  jle     short loc_18003B1EB
0x18003b1e2  movzx   ebx, ax
0x18003b1e5  or      ebx, 80070000h
0x18003b1eb  mov     eax, ebx
0x18003b1ed  mov     rcx, [rbp+var_10]
0x18003b1f1  xor     rcx, rsp; StackCookie
0x18003b1f4  call    __security_check_cookie
0x18003b1f9  lea     r11, [rsp+70h+var_s0]
0x18003b1fe  mov     rbx, [r11+20h]
0x18003b202  mov     rdi, [r11+28h]
0x18003b206  mov     rsp, r11
0x18003b209  pop     rbp
0x18003b20a  retn
0x18003b20b  mov     rax, qword ptr [rbp+Luid.LowPart]
0x18003b20f  lea     r8, [rbp+NewState]; NewState
0x18003b213  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x18003b217  mov     r9d, ebx; BufferLength
0x18003b21a  lea     rax, [rbp+BufferLength]
0x18003b21e  mov     [rbp+NewState.PrivilegeCount], 1
0x18003b225  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18003b22a  xor     edx, edx; DisableAllPrivileges
0x18003b22c  lea     rax, [rbp+var_30]
0x18003b230  mov     [rbp+NewState.Privileges.Attributes], 0
0x18003b237  mov     rcx, rdi; TokenHandle
0x18003b23a  mov     [rsp+70h+PreviousState], rax; PreviousState
0x18003b23f  call    cs:__imp_AdjustTokenPrivileges
0x18003b245  call    cs:__imp_GetLastError
0x18003b24b  mov     ebx, eax
0x18003b24d  test    eax, eax
0x18003b24f  jnz     short loc_18003B1E0
0x18003b251  mov     rax, qword ptr [rbp+Luid.LowPart]
0x18003b255  lea     r8, [rbp+var_30]; NewState
0x18003b259  mov     r9d, [rbp+BufferLength]; BufferLength
0x18003b25d  xor     edx, edx; DisableAllPrivileges
0x18003b25f  or      [rbp+var_30.Privileges.Attributes], 2
0x18003b263  mov     rcx, rdi; TokenHandle
0x18003b266  mov     [rsp+70h+ReturnLength], rbx; ReturnLength
0x18003b26b  mov     qword ptr [rbp+var_30.Privileges.Luid.LowPart], rax
0x18003b26f  mov     [rbp+var_30.PrivilegeCount], 1
0x18003b276  mov     [rsp+70h+PreviousState], rbx; PreviousState
0x18003b27b  call    cs:__imp_AdjustTokenPrivileges
0x18003b281  call    cs:__imp_GetLastError
0x18003b287  test    eax, eax
0x18003b289  jz      loc_18003B1EB
0x18003b28f  jg      loc_18003B1E2
0x18003b295  mov     ebx, eax
0x18003b297  jmp     loc_18003B1EB
```
