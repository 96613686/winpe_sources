# ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)

- ea: `0x180025b34`
- end: `0x180025b80`
- name: `?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z`
- size: `76`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, PHANDLE TokenHandle, void **)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180025a24`
- `0x180025acc`
- `0x180026ba4`

## callees

- `0x180025b34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025b64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025b64`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180025b44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180025b44`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180025b5a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180025b5a`

## pseudocode

```c
DWORD __fastcall ARI::ProcessToken::SysAppId::OpenTokenForProcess(HANDLE ProcessHandle, PHANDLE TokenHandle, void **a3)
{
  if ( ProcessHandle == GetCurrentProcess() )
  {
    *TokenHandle = (void *)-4LL;
  }
  else if ( !OpenProcessToken(ProcessHandle, 8u, TokenHandle) )
  {
    return GetLastError();
  }
  return 0;
}

```

## disassembly

```asm
0x180025b34  mov     [rsp+arg_0], rbx
0x180025b39  push    rdi
0x180025b3a  sub     rsp, 20h
0x180025b3e  mov     rbx, rdx
0x180025b41  mov     rdi, rcx
0x180025b44  call    cs:__imp_GetCurrentProcess
0x180025b4a  cmp     rdi, rax
0x180025b4d  jz      short loc_180025B6C
0x180025b4f  mov     r8, rbx; TokenHandle
0x180025b52  mov     edx, 8; DesiredAccess
0x180025b57  mov     rcx, rdi; ProcessHandle
0x180025b5a  call    cs:__imp_OpenProcessToken
0x180025b60  test    eax, eax
0x180025b62  jnz     short loc_180025B73
0x180025b64  call    cs:__imp_GetLastError
0x180025b6a  jmp     short loc_180025B75
0x180025b6c  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFCh
0x180025b73  xor     eax, eax
0x180025b75  mov     rbx, [rsp+28h+arg_0]
0x180025b7a  add     rsp, 20h
0x180025b7e  pop     rdi
0x180025b7f  retn
```
