# SHOpenEffectiveToken(ulong,int,void * *)

- ea: `0x180009248`
- end: `0x1800092df`
- name: `?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z`
- size: `151`
- prototype: `int __fastcall(__int64, __int64, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000911c`

## callees

- `0x180009248`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800092b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800092b8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000926b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000926b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009258`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009258`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800092aa`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800092aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009299`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009299`

## pseudocode

```c
int __fastcall SHOpenEffectiveToken(__int64 a1, __int64 a2, void **a3)
{
  HANDLE CurrentThread; // rax
  int result; // eax
  bool v6; // sf
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  signed int v9; // ecx

  *a3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, a3) )
    return 0;
  result = GetLastError();
  v6 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v6 = result < 0;
  }
  if ( !v6 )
    return -2147467259;
  if ( result == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, a3) )
      return 0;
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 >= 0 )
      return -2147467259;
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x180009248  push    rbx
0x18000924a  sub     rsp, 20h
0x18000924e  mov     rbx, r8
0x180009251  mov     qword ptr [r8], 0
0x180009258  call    cs:__imp_GetCurrentThread
0x18000925e  xor     r8d, r8d; OpenAsSelf
0x180009261  mov     r9, rbx; TokenHandle
0x180009264  mov     rcx, rax; ThreadHandle
0x180009267  lea     edx, [r8+8]; DesiredAccess
0x18000926b  call    cs:__imp_OpenThreadToken
0x180009271  test    eax, eax
0x180009273  jnz     short loc_1800092B4
0x180009275  call    cs:__imp_GetLastError
0x18000927b  test    eax, eax
0x18000927d  jle     short loc_180009289
0x18000927f  movzx   eax, ax
0x180009282  or      eax, 80070000h
0x180009287  test    eax, eax
0x180009289  js      short loc_180009292
0x18000928b  mov     eax, 80004005h
0x180009290  jmp     short loc_1800092D9
0x180009292  cmp     eax, 800703F0h
0x180009297  jnz     short loc_1800092D9
0x180009299  call    cs:__imp_GetCurrentProcess
0x18000929f  mov     r8, rbx; TokenHandle
0x1800092a2  mov     edx, 8; DesiredAccess
0x1800092a7  mov     rcx, rax; ProcessHandle
0x1800092aa  call    cs:__imp_OpenProcessToken
0x1800092b0  test    eax, eax
0x1800092b2  jz      short loc_1800092B8
0x1800092b4  xor     eax, eax
0x1800092b6  jmp     short loc_1800092D9
0x1800092b8  call    cs:__imp_GetLastError
0x1800092be  mov     ecx, eax
0x1800092c0  test    eax, eax
0x1800092c2  jle     short loc_1800092CD
0x1800092c4  movzx   ecx, ax
0x1800092c7  or      ecx, 80070000h
0x1800092cd  mov     eax, 80004005h
0x1800092d2  test    ecx, ecx
0x1800092d4  cmovns  ecx, eax
0x1800092d7  mov     eax, ecx
0x1800092d9  add     rsp, 20h
0x1800092dd  pop     rbx
0x1800092de  retn
```
