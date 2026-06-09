# SHOpenEffectiveToken(ulong,int,void * *)

- ea: `0x18006e74c`
- end: `0x18006e7e9`
- name: `?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z`
- size: `157`
- prototype: `__int64 __fastcall(DWORD DesiredAccess, int, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18006e4f8`
- `0x18006e628`

## callees

- `0x18006e74c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e77d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e7bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e77d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e7bd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18006e7af`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18006e7af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006e7a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006e7a1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006e773`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006e773`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006e762`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006e762`

## pseudocode

```c
signed int __fastcall SHOpenEffectiveToken(DWORD DesiredAccess, __int64 a2, void **a3)
{
  HANDLE CurrentThread; // rax
  signed int result; // eax
  bool v7; // sf
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  signed int v10; // ecx

  *a3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, DesiredAccess, 0, a3) )
    return 0;
  result = GetLastError();
  v7 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v7 = result < 0;
  }
  if ( !v7 )
    return -2147467259;
  if ( result == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, DesiredAccess, a3) )
      return 0;
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( v10 >= 0 )
      return -2147467259;
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x18006e74c  mov     [rsp+arg_0], rbx
0x18006e751  push    rdi
0x18006e752  sub     rsp, 20h
0x18006e756  mov     rbx, r8
0x18006e759  mov     qword ptr [r8], 0
0x18006e760  mov     edi, ecx
0x18006e762  call    cs:__imp_GetCurrentThread
0x18006e768  mov     r9, rbx; TokenHandle
0x18006e76b  xor     r8d, r8d; OpenAsSelf
0x18006e76e  mov     rcx, rax; ThreadHandle
0x18006e771  mov     edx, edi; DesiredAccess
0x18006e773  call    cs:__imp_OpenThreadToken
0x18006e779  test    eax, eax
0x18006e77b  jnz     short loc_18006E7B9
0x18006e77d  call    cs:__imp_GetLastError
0x18006e783  test    eax, eax
0x18006e785  jle     short loc_18006E791
0x18006e787  movzx   eax, ax
0x18006e78a  or      eax, 80070000h
0x18006e78f  test    eax, eax
0x18006e791  js      short loc_18006E79A
0x18006e793  mov     eax, 80004005h
0x18006e798  jmp     short loc_18006E7DE
0x18006e79a  cmp     eax, 800703F0h
0x18006e79f  jnz     short loc_18006E7DE
0x18006e7a1  call    cs:__imp_GetCurrentProcess
0x18006e7a7  mov     r8, rbx; TokenHandle
0x18006e7aa  mov     edx, edi; DesiredAccess
0x18006e7ac  mov     rcx, rax; ProcessHandle
0x18006e7af  call    cs:__imp_OpenProcessToken
0x18006e7b5  test    eax, eax
0x18006e7b7  jz      short loc_18006E7BD
0x18006e7b9  xor     eax, eax
0x18006e7bb  jmp     short loc_18006E7DE
0x18006e7bd  call    cs:__imp_GetLastError
0x18006e7c3  mov     ecx, eax
0x18006e7c5  test    eax, eax
0x18006e7c7  jle     short loc_18006E7D2
0x18006e7c9  movzx   ecx, ax
0x18006e7cc  or      ecx, 80070000h
0x18006e7d2  mov     eax, 80004005h
0x18006e7d7  test    ecx, ecx
0x18006e7d9  cmovns  ecx, eax
0x18006e7dc  mov     eax, ecx
0x18006e7de  mov     rbx, [rsp+28h+arg_0]
0x18006e7e3  add     rsp, 20h
0x18006e7e7  pop     rdi
0x18006e7e8  retn
```
