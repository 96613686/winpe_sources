# GetTokenHandleInternal(void * *,ulong,int)

- ea: `0x1400599f4`
- end: `0x140059a65`
- name: `?GetTokenHandleInternal@@YAHPEAPEAXKH@Z`
- size: `113`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle, DWORD DesiredAccess, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140059a6c`

## callees

- `0x1400599f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059a27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059a27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140059a34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140059a34`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140059a1d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140059a1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140059a0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140059a0c`
- `ADVAPI32!OpenProcessToken` at `0x140059a42`
- `ADVAPI32!OpenProcessToken` at `0x140059a42`

## pseudocode

```c
_BOOL8 __fastcall GetTokenHandleInternal(PHANDLE TokenHandle, DWORD DesiredAccess, unsigned __int8 a3)
{
  int v4; // ebx
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  _BOOL8 result; // rax

  v4 = a3;
  CurrentThread = GetCurrentThread();
  result = 1;
  if ( !OpenThreadToken(CurrentThread, DesiredAccess, v4, TokenHandle) )
  {
    if ( GetLastError() != 1008 )
      return 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, DesiredAccess, TokenHandle) )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400599f4  mov     [rsp+arg_0], rbx
0x1400599f9  mov     [rsp+arg_8], rsi
0x1400599fe  push    rdi
0x1400599ff  sub     rsp, 20h
0x140059a03  mov     edi, edx
0x140059a05  movzx   ebx, r8b
0x140059a09  mov     rsi, rcx
0x140059a0c  call    cs:__imp_GetCurrentThread
0x140059a12  mov     r9, rsi; TokenHandle
0x140059a15  mov     r8d, ebx; OpenAsSelf
0x140059a18  mov     rcx, rax; ThreadHandle
0x140059a1b  mov     edx, edi; DesiredAccess
0x140059a1d  call    cs:__imp_OpenThreadToken
0x140059a23  test    eax, eax
0x140059a25  jnz     short loc_140059A50
0x140059a27  call    cs:__imp_GetLastError
0x140059a2d  cmp     eax, 3F0h
0x140059a32  jnz     short loc_140059A4C
0x140059a34  call    cs:__imp_GetCurrentProcess
0x140059a3a  mov     r8, rsi; TokenHandle
0x140059a3d  mov     edx, edi; DesiredAccess
0x140059a3f  mov     rcx, rax; ProcessHandle
0x140059a42  call    cs:__imp_OpenProcessToken
0x140059a48  test    eax, eax
0x140059a4a  jnz     short loc_140059A50
0x140059a4c  xor     eax, eax
0x140059a4e  jmp     short loc_140059A55
0x140059a50  mov     eax, 1
0x140059a55  mov     rbx, [rsp+28h+arg_0]
0x140059a5a  mov     rsi, [rsp+28h+arg_8]
0x140059a5f  add     rsp, 20h
0x140059a63  pop     rdi
0x140059a64  retn
```
