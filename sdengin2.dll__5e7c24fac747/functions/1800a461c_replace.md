# replace

- ea: `0x1800a461c`
- end: `0x1800a4705`
- name: `replace`
- size: `233`
- prototype: `__int64 __fastcall(LPCSTR lpFileName, LPCSTR)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800a3378`

## callees

- `0x18009f1cc`
- `0x1800a3b14`
- `0x1800a461c`

## import_xrefs

- `KERNEL32!ReplaceFileA` at `0x1800a4643`
- `KERNEL32!ReplaceFileA` at `0x1800a4643`
- `KERNEL32!CloseHandle` at `0x1800a46c1`
- `KERNEL32!CloseHandle` at `0x1800a46e0`
- `KERNEL32!CloseHandle` at `0x1800a46e9`
- `KERNEL32!CloseHandle` at `0x1800a46c1`
- `KERNEL32!CloseHandle` at `0x1800a46e0`
- `KERNEL32!CloseHandle` at `0x1800a46e9`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800a4673`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800a46af`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800a4673`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800a46af`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x1800a46f2`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x1800a46f2`

## pseudocode

```c
__int64 __fastcall replace(LPCSTR lpFileName, LPCSTR a2)
{
  unsigned int v2; // edi
  HANDLE FileA; // rbx
  __int64 v6; // rcx
  HANDLE v8; // rax
  void *v9; // rsi

  v2 = 0;
  if ( !ReplaceFileA(lpFileName, a2, 0, 1u, 0, 0) )
  {
    FileA = CreateFileA(a2, 0x80000000, 3u, 0, 3u, 0x80u, 0);
    if ( FileA == (HANDLE)-1LL )
    {
      v6 = 10;
      return ZipErrorFromLastError(v6);
    }
    v8 = CreateFileA(lpFileName, 0xC0000000, 0, 0, 2u, 0x80u, 0);
    v9 = v8;
    if ( v8 == (HANDLE)-1LL )
    {
      CloseHandle(FileA);
      v6 = 15;
      return ZipErrorFromLastError(v6);
    }
    v2 = fcopy(FileA, v8);
    CloseHandle(FileA);
    CloseHandle(v9);
    DeleteFileA(a2);
  }
  return v2;
}

```

## disassembly

```asm
0x1800a461c  push    rbx
0x1800a461e  push    rbp
0x1800a461f  push    rsi
0x1800a4620  push    rdi
0x1800a4621  push    r14
0x1800a4623  sub     rsp, 40h
0x1800a4627  xor     edi, edi
0x1800a4629  mov     r14, r8
0x1800a462c  mov     [rsp+68h+lpReserved], rdi; lpReserved
0x1800a4631  xor     r8d, r8d; lpBackupFileName
0x1800a4634  mov     rbp, rdx
0x1800a4637  mov     [rsp+68h+lpExclude], rdi; lpExclude
0x1800a463c  mov     rsi, rcx
0x1800a463f  lea     r9d, [rdi+1]; dwReplaceFlags
0x1800a4643  call    cs:__imp_ReplaceFileA
0x1800a4649  test    eax, eax
0x1800a464b  jnz     loc_1800A46F8
0x1800a4651  mov     [rsp+68h+hTemplateFile], rdi; hTemplateFile
0x1800a4656  lea     r8d, [rax+3]; dwShareMode
0x1800a465a  mov     edi, 80h
0x1800a465f  xor     r9d, r9d; lpSecurityAttributes
0x1800a4662  mov     dword ptr [rsp+68h+lpReserved], edi; dwFlagsAndAttributes
0x1800a4666  mov     edx, 80000000h; dwDesiredAccess
0x1800a466b  mov     rcx, rbp; lpFileName
0x1800a466e  mov     dword ptr [rsp+68h+lpExclude], r8d; dwCreationDisposition
0x1800a4673  call    cs:__imp_CreateFileA
0x1800a4679  mov     rbx, rax
0x1800a467c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a4680  jnz     short loc_1800A468C
0x1800a4682  lea     ecx, [rdi-76h]
0x1800a4685  call    ZipErrorFromLastError
0x1800a468a  jmp     short loc_1800A46FA
0x1800a468c  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1800a4695  xor     r9d, r9d; lpSecurityAttributes
0x1800a4698  mov     dword ptr [rsp+68h+lpReserved], edi; dwFlagsAndAttributes
0x1800a469c  xor     r8d, r8d; dwShareMode
0x1800a469f  mov     edx, 0C0000000h; dwDesiredAccess
0x1800a46a4  mov     dword ptr [rsp+68h+lpExclude], 2; dwCreationDisposition
0x1800a46ac  mov     rcx, rsi; lpFileName
0x1800a46af  call    cs:__imp_CreateFileA
0x1800a46b5  mov     rsi, rax
0x1800a46b8  mov     rcx, rbx; hFile
0x1800a46bb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a46bf  jnz     short loc_1800A46CC
0x1800a46c1  call    cs:__imp_CloseHandle
0x1800a46c7  lea     ecx, [rsi+10h]
0x1800a46ca  jmp     short loc_1800A4685
0x1800a46cc  mov     r9, r14
0x1800a46cf  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800a46d3  mov     rdx, rsi; HANDLE
0x1800a46d6  call    fcopy
0x1800a46db  mov     rcx, rbx; hObject
0x1800a46de  mov     edi, eax
0x1800a46e0  call    cs:__imp_CloseHandle
0x1800a46e6  mov     rcx, rsi; hObject
0x1800a46e9  call    cs:__imp_CloseHandle
0x1800a46ef  mov     rcx, rbp; lpFileName
0x1800a46f2  call    cs:__imp_DeleteFileA
0x1800a46f8  mov     eax, edi
0x1800a46fa  add     rsp, 40h
0x1800a46fe  pop     r14
0x1800a4700  pop     rdi
0x1800a4701  pop     rsi
0x1800a4702  pop     rbp
0x1800a4703  pop     rbx
0x1800a4704  retn
```
