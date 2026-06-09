# ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)

- ea: `0x18002d758`
- end: `0x18002d7a4`
- name: `?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z`
- size: `76`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, PHANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18002d69c`

## callees

- `0x18002d758`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d79c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d79c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002d792`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002d792`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002d768`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002d768`

## pseudocode

```c
DWORD __fastcall ARI::ProcessToken::SysAppId::OpenTokenForProcess(HANDLE ProcessHandle, PHANDLE TokenHandle, void **a3)
{
  if ( ProcessHandle == GetCurrentProcess() )
  {
    *TokenHandle = (void *)-4LL;
    return 0;
  }
  if ( OpenProcessToken(ProcessHandle, 8u, TokenHandle) )
    return 0;
  return GetLastError();
}

```

## disassembly

```asm
0x18002d758  mov     [rsp+arg_0], rbx
0x18002d75d  push    rdi
0x18002d75e  sub     rsp, 20h
0x18002d762  mov     rbx, rdx
0x18002d765  mov     rdi, rcx
0x18002d768  call    cs:__imp_GetCurrentProcess
0x18002d76e  cmp     rdi, rax
0x18002d771  jnz     short loc_18002D787
0x18002d773  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFCh
0x18002d77a  xor     eax, eax
0x18002d77c  mov     rbx, [rsp+28h+arg_0]
0x18002d781  add     rsp, 20h
0x18002d785  pop     rdi
0x18002d786  retn
0x18002d787  mov     r8, rbx; TokenHandle
0x18002d78a  mov     edx, 8; DesiredAccess
0x18002d78f  mov     rcx, rdi; ProcessHandle
0x18002d792  call    cs:__imp_OpenProcessToken
0x18002d798  test    eax, eax
0x18002d79a  jnz     short loc_18002D77A
0x18002d79c  call    cs:__imp_GetLastError
0x18002d7a2  jmp     short loc_18002D77C
```
