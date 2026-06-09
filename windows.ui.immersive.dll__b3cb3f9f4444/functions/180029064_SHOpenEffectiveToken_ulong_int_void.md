# SHOpenEffectiveToken(ulong,int,void * *)

- ea: `0x180029064`
- end: `0x18002912a`
- name: `?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z`
- size: `198`
- prototype: `int(unsigned int, int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180028f08`

## callees

- `0x180029064`
- `0x18003d244`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180029093`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800290d2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180029093`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800290d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002907a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800290b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002907a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800290b7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180029105`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180029105`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800290ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800290ee`

## pseudocode

```c
__int64 __fastcall SHOpenEffectiveToken(__int64 a1, int a2, void **a3)
{
  HANDLE CurrentThread; // rax
  __int64 result; // rax
  HANDLE v7; // rax
  HANDLE CurrentProcess; // rax

  *a3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, a3) )
    return 0;
  result = ResultFromKnownLastError();
  if ( (int)result >= 0 )
    return result;
  if ( a2 && (_DWORD)result == -2147024891 )
  {
    v7 = GetCurrentThread();
    if ( !OpenThreadToken(v7, 8u, 1, a3) )
    {
      result = ResultFromKnownLastError();
      goto LABEL_7;
    }
    return 0;
  }
LABEL_7:
  if ( (_DWORD)result != -2147023888 )
    return result;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, a3) )
    return 0;
  return ResultFromKnownLastError();
}

```

## disassembly

```asm
0x180029064  mov     [rsp+arg_0], rbx
0x180029069  push    rdi
0x18002906a  sub     rsp, 20h
0x18002906e  mov     rbx, r8
0x180029071  mov     qword ptr [r8], 0
0x180029078  mov     edi, edx
0x18002907a  call    cs:__imp_GetCurrentThread
0x180029081  nop     dword ptr [rax+rax+00h]
0x180029086  xor     r8d, r8d; OpenAsSelf
0x180029089  mov     r9, rbx; TokenHandle
0x18002908c  mov     rcx, rax; ThreadHandle
0x18002908f  lea     edx, [r8+8]; DesiredAccess
0x180029093  call    cs:__imp_OpenThreadToken
0x18002909a  nop     dword ptr [rax+rax+00h]
0x18002909f  test    eax, eax
0x1800290a1  jnz     short loc_180029115
0x1800290a3  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800290a8  test    eax, eax
0x1800290aa  jns     short loc_18002911E
0x1800290ac  test    edi, edi
0x1800290ae  jz      short loc_1800290E7
0x1800290b0  cmp     eax, 80070005h
0x1800290b5  jnz     short loc_1800290E7
0x1800290b7  call    cs:__imp_GetCurrentThread
0x1800290be  nop     dword ptr [rax+rax+00h]
0x1800290c3  mov     edx, 8; DesiredAccess
0x1800290c8  mov     r9, rbx; TokenHandle
0x1800290cb  mov     rcx, rax; ThreadHandle
0x1800290ce  lea     r8d, [rdx-7]; OpenAsSelf
0x1800290d2  call    cs:__imp_OpenThreadToken
0x1800290d9  nop     dword ptr [rax+rax+00h]
0x1800290de  test    eax, eax
0x1800290e0  jnz     short loc_180029115
0x1800290e2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800290e7  cmp     eax, 800703F0h
0x1800290ec  jnz     short loc_18002911E
0x1800290ee  call    cs:__imp_GetCurrentProcess
0x1800290f5  nop     dword ptr [rax+rax+00h]
0x1800290fa  mov     r8, rbx; TokenHandle
0x1800290fd  mov     edx, 8; DesiredAccess
0x180029102  mov     rcx, rax; ProcessHandle
0x180029105  call    cs:__imp_OpenProcessToken
0x18002910c  nop     dword ptr [rax+rax+00h]
0x180029111  test    eax, eax
0x180029113  jz      short loc_180029119
0x180029115  xor     eax, eax
0x180029117  jmp     short loc_18002911E
0x180029119  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002911e  mov     rbx, [rsp+28h+arg_0]
0x180029123  add     rsp, 20h
0x180029127  pop     rdi
0x180029128  retn
```
