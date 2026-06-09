# GetTokenHandleInternal(void * *,ulong,int)

- ea: `0x14005f1dc`
- end: `0x14005f26c`
- name: `?GetTokenHandleInternal@@YAHPEAPEAXKH@Z`
- size: `144`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle, DWORD DesiredAccess, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14005f274`

## callees

- `0x14005f1dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005f21b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005f21b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14005f22e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14005f22e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14005f20b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14005f20b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14005f1f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14005f1f4`
- `ADVAPI32!OpenProcessToken` at `0x14005f242`
- `ADVAPI32!OpenProcessToken` at `0x14005f242`

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
0x14005f1dc  mov     [rsp+arg_0], rbx
0x14005f1e1  mov     [rsp+arg_8], rsi
0x14005f1e6  push    rdi
0x14005f1e7  sub     rsp, 20h
0x14005f1eb  mov     edi, edx
0x14005f1ed  movzx   ebx, r8b
0x14005f1f1  mov     rsi, rcx
0x14005f1f4  call    cs:__imp_GetCurrentThread
0x14005f1fb  nop     dword ptr [rax+rax+00h]
0x14005f200  mov     r9, rsi; TokenHandle
0x14005f203  mov     r8d, ebx; OpenAsSelf
0x14005f206  mov     rcx, rax; ThreadHandle
0x14005f209  mov     edx, edi; DesiredAccess
0x14005f20b  call    cs:__imp_OpenThreadToken
0x14005f212  nop     dword ptr [rax+rax+00h]
0x14005f217  test    eax, eax
0x14005f219  jnz     short loc_14005F256
0x14005f21b  call    cs:__imp_GetLastError
0x14005f222  nop     dword ptr [rax+rax+00h]
0x14005f227  cmp     eax, 3F0h
0x14005f22c  jnz     short loc_14005F252
0x14005f22e  call    cs:__imp_GetCurrentProcess
0x14005f235  nop     dword ptr [rax+rax+00h]
0x14005f23a  mov     r8, rsi; TokenHandle
0x14005f23d  mov     edx, edi; DesiredAccess
0x14005f23f  mov     rcx, rax; ProcessHandle
0x14005f242  call    cs:__imp_OpenProcessToken
0x14005f249  nop     dword ptr [rax+rax+00h]
0x14005f24e  test    eax, eax
0x14005f250  jnz     short loc_14005F256
0x14005f252  xor     eax, eax
0x14005f254  jmp     short loc_14005F25B
0x14005f256  mov     eax, 1
0x14005f25b  mov     rbx, [rsp+28h+arg_0]
0x14005f260  mov     rsi, [rsp+28h+arg_8]
0x14005f265  add     rsp, 20h
0x14005f269  pop     rdi
0x14005f26a  retn
```
