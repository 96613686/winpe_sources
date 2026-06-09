# SHOpenEffectiveToken(ulong,int,void * *)

- ea: `0x18002c5bc`
- end: `0x18002c623`
- name: `?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z`
- size: `103`
- prototype: `int(unsigned int, int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18002c48c`

## callees

- `0x18000b3c0`
- `0x18002c5bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002c5cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002c5cc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002c606`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002c606`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002c5df`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002c5df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002c5f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002c5f5`

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
0x18002c5bc  push    rbx
0x18002c5be  sub     rsp, 20h
0x18002c5c2  mov     rbx, r8
0x18002c5c5  mov     qword ptr [r8], 0
0x18002c5cc  call    cs:__imp_GetCurrentThread
0x18002c5d2  xor     r8d, r8d; OpenAsSelf
0x18002c5d5  mov     r9, rbx; TokenHandle
0x18002c5d8  mov     rcx, rax; ThreadHandle
0x18002c5db  lea     edx, [r8+8]; DesiredAccess
0x18002c5df  call    cs:__imp_OpenThreadToken
0x18002c5e5  test    eax, eax
0x18002c5e7  jnz     short loc_18002C610
0x18002c5e9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002c5ee  cmp     eax, 800703F0h
0x18002c5f3  jnz     short loc_18002C61D
0x18002c5f5  call    cs:__imp_GetCurrentProcess
0x18002c5fb  mov     r8, rbx; TokenHandle
0x18002c5fe  mov     edx, 8; DesiredAccess
0x18002c603  mov     rcx, rax; ProcessHandle
0x18002c606  call    cs:__imp_OpenProcessToken
0x18002c60c  test    eax, eax
0x18002c60e  jz      short loc_18002C618
0x18002c610  xor     eax, eax
0x18002c612  add     rsp, 20h
0x18002c616  pop     rbx
0x18002c617  retn
0x18002c618  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002c61d  add     rsp, 20h
0x18002c621  pop     rbx
0x18002c622  retn
```
