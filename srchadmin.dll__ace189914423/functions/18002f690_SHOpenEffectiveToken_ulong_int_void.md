# SHOpenEffectiveToken(ulong,int,void * *)

- ea: `0x18002f690`
- end: `0x18002f6f7`
- name: `?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z`
- size: `103`
- prototype: `int(unsigned int, int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18002f56c`

## callees

- `0x18000d4dc`
- `0x18002f690`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002f6a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002f6a0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002f6b3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002f6b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002f6c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002f6c9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002f6da`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002f6da`

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
0x18002f690  push    rbx
0x18002f692  sub     rsp, 20h
0x18002f696  mov     rbx, r8
0x18002f699  mov     qword ptr [r8], 0
0x18002f6a0  call    cs:__imp_GetCurrentThread
0x18002f6a6  xor     r8d, r8d; OpenAsSelf
0x18002f6a9  mov     r9, rbx; TokenHandle
0x18002f6ac  mov     rcx, rax; ThreadHandle
0x18002f6af  lea     edx, [r8+8]; DesiredAccess
0x18002f6b3  call    cs:__imp_OpenThreadToken
0x18002f6b9  test    eax, eax
0x18002f6bb  jnz     short loc_18002F6E4
0x18002f6bd  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002f6c2  cmp     eax, 800703F0h
0x18002f6c7  jnz     short loc_18002F6F1
0x18002f6c9  call    cs:__imp_GetCurrentProcess
0x18002f6cf  mov     r8, rbx; TokenHandle
0x18002f6d2  mov     edx, 8; DesiredAccess
0x18002f6d7  mov     rcx, rax; ProcessHandle
0x18002f6da  call    cs:__imp_OpenProcessToken
0x18002f6e0  test    eax, eax
0x18002f6e2  jz      short loc_18002F6EC
0x18002f6e4  xor     eax, eax
0x18002f6e6  add     rsp, 20h
0x18002f6ea  pop     rbx
0x18002f6eb  retn
0x18002f6ec  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002f6f1  add     rsp, 20h
0x18002f6f5  pop     rbx
0x18002f6f6  retn
```
