# SHCreateSharedSection(ulong,ulong,ushort const *,void * *)

- ea: `0x180005a64`
- end: `0x180005b26`
- name: `?SHCreateSharedSection@@YAJKKPEBGPEAPEAX@Z`
- size: `194`
- prototype: `int(unsigned int, unsigned int, const unsigned __int16 *, void **)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180004df0`
- `0x180005350`
- `0x1800058a0`

## callees

- `0x180004860`
- `0x180005a64`
- `0x18001c82c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005abf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005abf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005ad1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005ada`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005ad1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005ada`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180005b06`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180005b06`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180005a7e`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180005b16`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180005a7e`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180005b16`

## pseudocode

```c
__int64 __fastcall SHCreateSharedSection(__int64 a1, __int64 a2, const unsigned __int16 *a3, void **a4)
{
  HANDLE v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  void *NamedSection; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v13; // rax
  HANDLE TargetHandle; // [rsp+68h] [rbp+20h] BYREF

  v6 = OpenFileMappingW(6u, 0, a3);
  TargetHandle = v6;
  if ( v6 )
    goto LABEL_2;
  NamedSection = (void *)CreateNamedSection(v8, v7, v9, a3);
  if ( NamedSection )
  {
    CurrentProcess = GetCurrentProcess();
    v13 = GetCurrentProcess();
    DuplicateHandle(v13, NamedSection, CurrentProcess, &TargetHandle, 6u, 0, 1u);
    goto LABEL_7;
  }
  if ( GetLastError() != 5 )
  {
LABEL_7:
    v6 = TargetHandle;
    goto LABEL_2;
  }
  v6 = OpenFileMappingW(6u, 0, a3);
  TargetHandle = v6;
LABEL_2:
  *a4 = v6;
  if ( v6 )
    return 0;
  else
    return ResultFromKnownLastError();
}

```

## disassembly

```asm
0x180005a64  mov     [rsp+arg_0], rbx
0x180005a69  mov     [rsp+arg_8], rsi
0x180005a6e  push    rdi
0x180005a6f  sub     rsp, 40h
0x180005a73  xor     edx, edx; bInheritHandle
0x180005a75  mov     rsi, r9
0x180005a78  mov     rbx, r8
0x180005a7b  lea     ecx, [rdx+6]; dwDesiredAccess
0x180005a7e  call    cs:__imp_OpenFileMappingW
0x180005a84  mov     [rsp+48h+TargetHandle], rax
0x180005a89  test    rax, rax
0x180005a8c  jz      short loc_180005AAF
0x180005a8e  mov     [rsi], rax
0x180005a91  test    rax, rax
0x180005a94  jz      short loc_180005AA8
0x180005a96  xor     eax, eax
0x180005a98  mov     rbx, [rsp+48h+arg_0]
0x180005a9d  mov     rsi, [rsp+48h+arg_8]
0x180005aa2  add     rsp, 40h
0x180005aa6  pop     rdi
0x180005aa7  retn
0x180005aa8  call    ResultFromKnownLastError
0x180005aad  jmp     short loc_180005A98
0x180005aaf  mov     r9, rbx
0x180005ab2  call    _CreateNamedSection
0x180005ab7  mov     rdi, rax
0x180005aba  test    rax, rax
0x180005abd  jnz     short loc_180005AD1
0x180005abf  call    cs:__imp_GetLastError
0x180005ac5  cmp     eax, 5
0x180005ac8  jz      short loc_180005B0E
0x180005aca  mov     rax, [rsp+48h+TargetHandle]
0x180005acf  jmp     short loc_180005A8E
0x180005ad1  call    cs:__imp_GetCurrentProcess
0x180005ad7  mov     rbx, rax
0x180005ada  call    cs:__imp_GetCurrentProcess
0x180005ae0  mov     [rsp+48h+dwOptions], 1; dwOptions
0x180005ae8  lea     r9, [rsp+48h+TargetHandle]; lpTargetHandle
0x180005aed  mov     rcx, rax; hSourceProcessHandle
0x180005af0  mov     [rsp+48h+bInheritHandle], 0; bInheritHandle
0x180005af8  mov     r8, rbx; hTargetProcessHandle
0x180005afb  mov     [rsp+48h+dwDesiredAccess], 6; dwDesiredAccess
0x180005b03  mov     rdx, rdi; hSourceHandle
0x180005b06  call    cs:__imp_DuplicateHandle
0x180005b0c  jmp     short loc_180005ACA
0x180005b0e  xor     edx, edx; bInheritHandle
0x180005b10  mov     r8, rbx; lpName
0x180005b13  lea     ecx, [rdx+6]; dwDesiredAccess
0x180005b16  call    cs:__imp_OpenFileMappingW
0x180005b1c  mov     [rsp+48h+TargetHandle], rax
0x180005b21  jmp     loc_180005A8E
```
