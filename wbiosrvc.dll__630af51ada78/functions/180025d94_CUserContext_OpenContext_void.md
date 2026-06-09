# CUserContext::OpenContext(void *)

- ea: `0x180025d94`
- end: `0x180025e76`
- name: `?OpenContext@CUserContext@@QEAAJPEAX@Z`
- size: `226`
- prototype: `int __fastcall(CUserContext *this, void *)`
- caller_count: `7`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180025bc0`
- `0x180060a78`
- `0x1800bc1d0`
- `0x1800bc7e0`
- `0x1800bc920`
- `0x1800bca60`
- `0x1800bcd80`

## callees

- `0x180025d94`
- `0x1800401b8`
- `0x180060dc8`
- `0x1800bc048`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025dde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025e0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025dde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025e0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180025df2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180025df2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180025dbf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180025dbf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180025dd4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180025dd4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180025e01`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180025e01`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall CUserContext::OpenContext(CUserContext *this, void *a2)
{
  int result; // eax
  HANDLE CurrentThread; // rax
  signed int LastError; // ebx
  HANDLE CurrentProcess; // rax
  int v8; // eax
  int v9; // ecx

  *((_QWORD *)this + 1) = a2;
  if ( a2 )
  {
    result = CUserContext::Impersonate(this);
    if ( result < 0 )
      return result;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, (PHANDLE)this) )
    goto LABEL_14;
  LastError = GetLastError();
  if ( LastError == 1008 )
  {
    if ( !a2 )
    {
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 8u, (PHANDLE)this) )
      {
        result = GetLastError();
        if ( result > 0 )
          return (unsigned __int16)result | 0x80070000;
        return result;
      }
LABEL_14:
      if ( !*(_QWORD *)this )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      if ( !a2 )
        return 0;
      v8 = CUserContext::RevertToSelf(this);
      v9 = 0;
      if ( v8 < 0 )
        return v8;
      return v9;
    }
    goto LABEL_10;
  }
  if ( a2 )
  {
LABEL_10:
    result = CUserContext::RevertToSelf(this);
    if ( result < 0 )
      return result;
  }
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return LastError;
}

```

## disassembly

```asm
0x180025d94  mov     [rsp+arg_0], rbx
0x180025d99  mov     [rsp+arg_8], rsi
0x180025d9e  push    rdi
0x180025d9f  sub     rsp, 20h
0x180025da3  mov     [rcx+8], rdx
0x180025da7  mov     rsi, rdx
0x180025daa  mov     rdi, rcx
0x180025dad  test    rdx, rdx
0x180025db0  jz      short loc_180025DBF
0x180025db2  call    ?Impersonate@CUserContext@@QEAAJXZ; CUserContext::Impersonate(void)
0x180025db7  test    eax, eax
0x180025db9  js      loc_180025E66
0x180025dbf  call    cs:__imp_GetCurrentThread
0x180025dc5  mov     edx, 8; DesiredAccess
0x180025dca  mov     r9, rdi; TokenHandle
0x180025dcd  mov     rcx, rax; ThreadHandle
0x180025dd0  lea     r8d, [rdx-7]; OpenAsSelf
0x180025dd4  call    cs:__imp_OpenThreadToken
0x180025dda  test    eax, eax
0x180025ddc  jnz     short loc_180025E41
0x180025dde  call    cs:__imp_GetLastError
0x180025de4  mov     ebx, eax
0x180025de6  cmp     eax, 3F0h
0x180025deb  jnz     short loc_180025E1F
0x180025ded  test    rsi, rsi
0x180025df0  jnz     short loc_180025E24
0x180025df2  call    cs:__imp_GetCurrentProcess
0x180025df8  mov     r8, rdi; TokenHandle
0x180025dfb  lea     edx, [rsi+8]; DesiredAccess
0x180025dfe  mov     rcx, rax; ProcessHandle
0x180025e01  call    cs:__imp_OpenProcessToken
0x180025e07  test    eax, eax
0x180025e09  jnz     short loc_180025E41
0x180025e0b  call    cs:__imp_GetLastError
0x180025e11  test    eax, eax
0x180025e13  jle     short loc_180025E66
0x180025e15  movzx   eax, ax
0x180025e18  or      eax, 80070000h
0x180025e1d  jmp     short loc_180025E66
0x180025e1f  test    rsi, rsi
0x180025e22  jz      short loc_180025E30
0x180025e24  mov     rcx, rdi; this
0x180025e27  call    ?RevertToSelf@CUserContext@@QEAAJXZ; CUserContext::RevertToSelf(void)
0x180025e2c  test    eax, eax
0x180025e2e  js      short loc_180025E66
0x180025e30  test    ebx, ebx
0x180025e32  jle     short loc_180025E3D
0x180025e34  movzx   ebx, bx
0x180025e37  or      ebx, 80070000h
0x180025e3d  mov     eax, ebx
0x180025e3f  jmp     short loc_180025E66
0x180025e41  cmp     qword ptr [rdi], 0
0x180025e45  jnz     short loc_180025E4C
0x180025e47  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180025e4c  test    rsi, rsi
0x180025e4f  jz      short loc_180025E64
0x180025e51  mov     rcx, rdi; this
0x180025e54  call    ?RevertToSelf@CUserContext@@QEAAJXZ; CUserContext::RevertToSelf(void)
0x180025e59  xor     ecx, ecx
0x180025e5b  test    eax, eax
0x180025e5d  cmovs   ecx, eax
0x180025e60  mov     eax, ecx
0x180025e62  jmp     short loc_180025E66
0x180025e64  xor     eax, eax
0x180025e66  mov     rbx, [rsp+28h+arg_0]
0x180025e6b  mov     rsi, [rsp+28h+arg_8]
0x180025e70  add     rsp, 20h
0x180025e74  pop     rdi
0x180025e75  retn
```
