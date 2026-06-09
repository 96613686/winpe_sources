# SHOpenEffectiveToken(ulong,int,void * *)

- ea: `0x180035d30`
- end: `0x180035d97`
- name: `?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z`
- size: `103`
- prototype: `int(unsigned int, int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180035c04`

## callees

- `0x18000eaf0`
- `0x180035d30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180035d7a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180035d7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180035d69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180035d69`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180035d53`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180035d53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180035d40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180035d40`

## pseudocode

```c
__int64 __fastcall SHOpenEffectiveToken(__int64 a1, __int64 a2, void **a3)
{
  HANDLE CurrentThread; // rax
  __int64 result; // rax
  HANDLE CurrentProcess; // rax

  *a3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, a3) )
    return 0;
  result = ResultFromKnownLastError();
  if ( (_DWORD)result != -2147023888 )
    return result;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, a3) )
    return 0;
  else
    return ResultFromKnownLastError();
}

```

## disassembly

```asm
0x180035d30  push    rbx
0x180035d32  sub     rsp, 20h
0x180035d36  mov     rbx, r8
0x180035d39  mov     qword ptr [r8], 0
0x180035d40  call    cs:__imp_GetCurrentThread
0x180035d46  xor     r8d, r8d; OpenAsSelf
0x180035d49  mov     r9, rbx; TokenHandle
0x180035d4c  mov     rcx, rax; ThreadHandle
0x180035d4f  lea     edx, [r8+8]; DesiredAccess
0x180035d53  call    cs:__imp_OpenThreadToken
0x180035d59  test    eax, eax
0x180035d5b  jnz     short loc_180035D84
0x180035d5d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180035d62  cmp     eax, 800703F0h
0x180035d67  jnz     short loc_180035D91
0x180035d69  call    cs:__imp_GetCurrentProcess
0x180035d6f  mov     r8, rbx; TokenHandle
0x180035d72  mov     edx, 8; DesiredAccess
0x180035d77  mov     rcx, rax; ProcessHandle
0x180035d7a  call    cs:__imp_OpenProcessToken
0x180035d80  test    eax, eax
0x180035d82  jz      short loc_180035D8C
0x180035d84  xor     eax, eax
0x180035d86  add     rsp, 20h
0x180035d8a  pop     rbx
0x180035d8b  retn
0x180035d8c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180035d91  add     rsp, 20h
0x180035d95  pop     rbx
0x180035d96  retn
```
