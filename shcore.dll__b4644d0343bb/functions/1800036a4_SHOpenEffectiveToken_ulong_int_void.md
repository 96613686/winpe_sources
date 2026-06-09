# SHOpenEffectiveToken(ulong,int,void * *)

- ea: `0x1800036a4`
- end: `0x18000370a`
- name: `?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z`
- size: `102`
- prototype: `int(unsigned int, int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000357c`

## callees

- `0x1800036a4`
- `0x18001c82c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800036c7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800036c7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800036f6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800036f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800036b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800036b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800036e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800036e5`

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
  if ( (_DWORD)result == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, a3) )
      return ResultFromKnownLastError();
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800036a4  push    rbx
0x1800036a6  sub     rsp, 20h
0x1800036aa  mov     rbx, r8
0x1800036ad  mov     qword ptr [r8], 0
0x1800036b4  call    cs:__imp_GetCurrentThread
0x1800036ba  xor     r8d, r8d; OpenAsSelf
0x1800036bd  mov     r9, rbx; TokenHandle
0x1800036c0  mov     rcx, rax; ThreadHandle
0x1800036c3  lea     edx, [r8+8]; DesiredAccess
0x1800036c7  call    cs:__imp_OpenThreadToken
0x1800036cd  test    eax, eax
0x1800036cf  jz      short loc_1800036D9
0x1800036d1  xor     eax, eax
0x1800036d3  add     rsp, 20h
0x1800036d7  pop     rbx
0x1800036d8  retn
0x1800036d9  call    ResultFromKnownLastError
0x1800036de  cmp     eax, 800703F0h
0x1800036e3  jnz     short loc_1800036D3
0x1800036e5  call    cs:__imp_GetCurrentProcess
0x1800036eb  mov     r8, rbx; TokenHandle
0x1800036ee  mov     edx, 8; DesiredAccess
0x1800036f3  mov     rcx, rax; ProcessHandle
0x1800036f6  call    cs:__imp_OpenProcessToken
0x1800036fc  test    eax, eax
0x1800036fe  jnz     short loc_1800036D1
0x180003700  add     rsp, 20h
0x180003704  pop     rbx
0x180003705  jmp     ResultFromKnownLastError
```
