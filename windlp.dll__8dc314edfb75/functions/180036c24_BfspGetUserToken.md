# BfspGetUserToken

- ea: `0x180036c24`
- end: `0x180036ca1`
- name: `BfspGetUserToken`
- size: `125`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18003682c`
- `0x180036adc`

## callees

- `0x180036c24`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180036c7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180036c7d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180036c8c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180036c8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180036c31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180036c52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180036c31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180036c52`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180036c46`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180036c64`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180036c46`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180036c64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036c70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036c70`

## pseudocode

```c
__int64 __fastcall BfspGetUserToken(PHANDLE TokenHandle)
{
  HANDLE CurrentThread; // rax
  unsigned int v3; // ebx
  HANDLE v4; // rax
  HANDLE CurrentProcess; // rax

  CurrentThread = GetCurrentThread();
  v3 = OpenThreadToken(CurrentThread, 0x28u, 1, TokenHandle);
  if ( !v3 )
  {
    v4 = GetCurrentThread();
    v3 = OpenThreadToken(v4, 0x28u, 0, TokenHandle);
    if ( !v3 && GetLastError() == 1008 )
    {
      CurrentProcess = GetCurrentProcess();
      return OpenProcessToken(CurrentProcess, 0x28u, TokenHandle);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180036c24  mov     [rsp+arg_0], rbx
0x180036c29  push    rdi
0x180036c2a  sub     rsp, 20h
0x180036c2e  mov     rdi, rcx
0x180036c31  call    cs:__imp_GetCurrentThread
0x180036c37  mov     edx, 28h ; '('; DesiredAccess
0x180036c3c  mov     r9, rdi; TokenHandle
0x180036c3f  mov     rcx, rax; ThreadHandle
0x180036c42  lea     r8d, [rdx-27h]; OpenAsSelf
0x180036c46  call    cs:__imp_OpenThreadToken
0x180036c4c  mov     ebx, eax
0x180036c4e  test    eax, eax
0x180036c50  jnz     short loc_180036C94
0x180036c52  call    cs:__imp_GetCurrentThread
0x180036c58  mov     r9, rdi; TokenHandle
0x180036c5b  lea     edx, [rbx+28h]; DesiredAccess
0x180036c5e  mov     rcx, rax; ThreadHandle
0x180036c61  xor     r8d, r8d; OpenAsSelf
0x180036c64  call    cs:__imp_OpenThreadToken
0x180036c6a  mov     ebx, eax
0x180036c6c  test    eax, eax
0x180036c6e  jnz     short loc_180036C94
0x180036c70  call    cs:__imp_GetLastError
0x180036c76  cmp     eax, 3F0h
0x180036c7b  jnz     short loc_180036C94
0x180036c7d  call    cs:__imp_GetCurrentProcess
0x180036c83  mov     r8, rdi; TokenHandle
0x180036c86  lea     edx, [rbx+28h]; DesiredAccess
0x180036c89  mov     rcx, rax; ProcessHandle
0x180036c8c  call    cs:__imp_OpenProcessToken
0x180036c92  mov     ebx, eax
0x180036c94  mov     eax, ebx
0x180036c96  mov     rbx, [rsp+28h+arg_0]
0x180036c9b  add     rsp, 20h
0x180036c9f  pop     rdi
0x180036ca0  retn
```
