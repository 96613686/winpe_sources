# W3_MGD_USER_CONTEXT::Initialize(void)

- ea: `0x180063df0`
- end: `0x180063e7e`
- name: `?Initialize@W3_MGD_USER_CONTEXT@@SAJXZ`
- size: `142`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005bbb4`

## callees

- `0x180063df0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180063e60`
- `KERNEL32!CloseHandle` at `0x180063e60`
- `KERNEL32!GetLastError` at `0x180063e23`
- `KERNEL32!GetLastError` at `0x180063e23`
- `KERNEL32!GetCurrentProcess` at `0x180063e06`
- `KERNEL32!GetCurrentProcess` at `0x180063e06`
- `ADVAPI32!OpenProcessToken` at `0x180063e19`
- `ADVAPI32!OpenProcessToken` at `0x180063e19`
- `ADVAPI32!DuplicateToken` at `0x180063e4a`
- `ADVAPI32!DuplicateToken` at `0x180063e4a`

## pseudocode

```c
__int64 W3_MGD_USER_CONTEXT::Initialize(void)
{
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  signed int v2; // ebx
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  if ( !W3_MGD_USER_CONTEXT::sm_hProcessToken )
  {
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0xF01FFu, &TokenHandle)
      && DuplicateToken(TokenHandle, SecurityImpersonation, &W3_MGD_USER_CONTEXT::sm_hProcessToken) )
    {
      v2 = 0;
    }
    else
    {
      LastError = GetLastError();
      v2 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v2 = LastError;
    }
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    if ( v2 < 0 )
      return (unsigned int)v2;
  }
  W3_MGD_USER_CONTEXT::sm_pUserTraceLog = 0;
  return 0;
}

```

## disassembly

```asm
0x180063df0  push    rbx
0x180063df2  sub     rsp, 20h
0x180063df6  cmp     cs:?sm_hProcessToken@W3_MGD_USER_CONTEXT@@0PEAXEA, 0; void * W3_MGD_USER_CONTEXT::sm_hProcessToken
0x180063dfe  jnz     short loc_180063E6E
0x180063e00  and     [rsp+28h+TokenHandle], 0
0x180063e06  call    cs:__imp_GetCurrentProcess
0x180063e0c  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x180063e11  mov     edx, 0F01FFh; DesiredAccess
0x180063e16  mov     rcx, rax; ProcessHandle
0x180063e19  call    cs:__imp_OpenProcessToken
0x180063e1f  test    eax, eax
0x180063e21  jnz     short loc_180063E39
0x180063e23  call    cs:__imp_GetLastError
0x180063e29  movzx   ebx, ax
0x180063e2c  or      ebx, 80070000h
0x180063e32  test    eax, eax
0x180063e34  cmovle  ebx, eax
0x180063e37  jmp     short loc_180063E56
0x180063e39  mov     rcx, [rsp+28h+TokenHandle]; ExistingTokenHandle
0x180063e3e  lea     r8, ?sm_hProcessToken@W3_MGD_USER_CONTEXT@@0PEAXEA; DuplicateTokenHandle
0x180063e45  mov     edx, 2; ImpersonationLevel
0x180063e4a  call    cs:__imp_DuplicateToken
0x180063e50  test    eax, eax
0x180063e52  jz      short loc_180063E23
0x180063e54  xor     ebx, ebx
0x180063e56  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180063e5b  test    rcx, rcx
0x180063e5e  jz      short loc_180063E66
0x180063e60  call    cs:__imp_CloseHandle
0x180063e66  test    ebx, ebx
0x180063e68  jns     short loc_180063E6E
0x180063e6a  mov     eax, ebx
0x180063e6c  jmp     short loc_180063E78
0x180063e6e  and     cs:?sm_pUserTraceLog@W3_MGD_USER_CONTEXT@@0PEAU_TRACE_LOG@@EA, 0; _TRACE_LOG * W3_MGD_USER_CONTEXT::sm_pUserTraceLog
0x180063e76  xor     eax, eax
0x180063e78  add     rsp, 20h
0x180063e7c  pop     rbx
0x180063e7d  retn
```
