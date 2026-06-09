# SHOpenEffectiveToken(ulong,int,void * *)

- ea: `0x180015b34`
- end: `0x180015bd5`
- name: `?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z`
- size: `161`
- prototype: `int(unsigned int, int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800159d4`

## callees

- `0x1800092b8`
- `0x180015b34`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180015b4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180015b7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180015b4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180015b7b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180015b5d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180015b90`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180015b5d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180015b90`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180015bb7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180015bb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015ba6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015ba6`

## pseudocode

```c
int __fastcall SHOpenEffectiveToken(__int64 a1, int a2, void **a3)
{
  HANDLE CurrentThread; // rax
  int result; // eax
  HANDLE v7; // rax
  HANDLE CurrentProcess; // rax

  *a3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, a3) )
    return 0;
  result = ResultFromKnownLastError();
  if ( result >= 0 )
    return result;
  if ( a2 && result == -2147024891 )
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
  if ( result != -2147023888 )
    return result;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, a3) )
    return 0;
  return ResultFromKnownLastError();
}

```

## disassembly

```asm
0x180015b34  mov     [rsp+arg_0], rbx
0x180015b39  push    rdi
0x180015b3a  sub     rsp, 20h
0x180015b3e  mov     rbx, r8
0x180015b41  mov     qword ptr [r8], 0
0x180015b48  mov     edi, edx
0x180015b4a  call    cs:__imp_GetCurrentThread
0x180015b50  xor     r8d, r8d; OpenAsSelf
0x180015b53  mov     r9, rbx; TokenHandle
0x180015b56  mov     rcx, rax; ThreadHandle
0x180015b59  lea     edx, [r8+8]; DesiredAccess
0x180015b5d  call    cs:__imp_OpenThreadToken
0x180015b63  test    eax, eax
0x180015b65  jnz     short loc_180015BC1
0x180015b67  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180015b6c  test    eax, eax
0x180015b6e  jns     short loc_180015BCA
0x180015b70  test    edi, edi
0x180015b72  jz      short loc_180015B9F
0x180015b74  cmp     eax, 80070005h
0x180015b79  jnz     short loc_180015B9F
0x180015b7b  call    cs:__imp_GetCurrentThread
0x180015b81  mov     edx, 8; DesiredAccess
0x180015b86  mov     r9, rbx; TokenHandle
0x180015b89  mov     rcx, rax; ThreadHandle
0x180015b8c  lea     r8d, [rdx-7]; OpenAsSelf
0x180015b90  call    cs:__imp_OpenThreadToken
0x180015b96  test    eax, eax
0x180015b98  jnz     short loc_180015BC1
0x180015b9a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180015b9f  cmp     eax, 800703F0h
0x180015ba4  jnz     short loc_180015BCA
0x180015ba6  call    cs:__imp_GetCurrentProcess
0x180015bac  mov     r8, rbx; TokenHandle
0x180015baf  mov     edx, 8; DesiredAccess
0x180015bb4  mov     rcx, rax; ProcessHandle
0x180015bb7  call    cs:__imp_OpenProcessToken
0x180015bbd  test    eax, eax
0x180015bbf  jz      short loc_180015BC5
0x180015bc1  xor     eax, eax
0x180015bc3  jmp     short loc_180015BCA
0x180015bc5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180015bca  mov     rbx, [rsp+28h+arg_0]
0x180015bcf  add     rsp, 20h
0x180015bd3  pop     rdi
0x180015bd4  retn
```
