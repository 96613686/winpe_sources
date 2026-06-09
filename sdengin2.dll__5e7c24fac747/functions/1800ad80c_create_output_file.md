# create_output_file

- ea: `0x1800ad80c`
- end: `0x1800ad8d1`
- name: `create_output_file`
- size: `197`
- prototype: `__int64 __fastcall(LPCSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800a73e8`

## callees

- `0x1800ad80c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800ad8ae`
- `KERNEL32!GetLastError` at `0x1800ad8ae`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800ad81f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800ad81f`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800ad897`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800ad897`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x1800ad851`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x1800ad851`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x1800ad83e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x1800ad83e`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x1800ad85e`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x1800ad85e`

## pseudocode

```c
__int64 __fastcall create_output_file(LPCSTR lpFileName)
{
  _DWORD *Value; // rax
  _DWORD *v3; // rdi
  DWORD FileAttributesA; // eax
  HANDLE FileA; // rax
  DWORD LastError; // eax
  unsigned int v8; // ecx

  Value = TlsGetValue(dwUnZIPTlsIndex);
  v3 = Value;
  if ( !Value )
    return 4;
  if ( Value[1] )
  {
    FileAttributesA = GetFileAttributesA(lpFileName);
    if ( FileAttributesA != -1
      && (!SetFileAttributesA(lpFileName, FileAttributesA & 0xFFFFFFFE) || !DeleteFileA(lpFileName)) )
    {
      return 28;
    }
  }
  FileA = CreateFileA(lpFileName, 0xC0000000, 3u, 0, 2u, 0x8000020u, 0);
  *(_QWORD *)((char *)v3 + 72178) = FileA;
  if ( FileA != (HANDLE)-1LL )
    return 0;
  LastError = GetLastError();
  v8 = 28;
  if ( LastError == 206 )
    return 51;
  return v8;
}

```

## disassembly

```asm
0x1800ad80c  mov     [rsp+arg_0], rbx
0x1800ad811  push    rdi
0x1800ad812  sub     rsp, 40h
0x1800ad816  mov     rbx, rcx
0x1800ad819  mov     ecx, cs:dwUnZIPTlsIndex; dwTlsIndex
0x1800ad81f  call    cs:__imp_TlsGetValue
0x1800ad825  mov     rdi, rax
0x1800ad828  test    rax, rax
0x1800ad82b  jnz     short loc_1800AD835
0x1800ad82d  lea     eax, [rdi+4]
0x1800ad830  jmp     loc_1800AD8C6
0x1800ad835  cmp     dword ptr [rax+4], 0
0x1800ad839  jz      short loc_1800AD86F
0x1800ad83b  mov     rcx, rbx; lpFileName
0x1800ad83e  call    cs:__imp_GetFileAttributesA
0x1800ad844  cmp     eax, 0FFFFFFFFh
0x1800ad847  jz      short loc_1800AD86F
0x1800ad849  and     eax, 0FFFFFFFEh
0x1800ad84c  mov     rcx, rbx; lpFileName
0x1800ad84f  mov     edx, eax; dwFileAttributes
0x1800ad851  call    cs:__imp_SetFileAttributesA
0x1800ad857  test    eax, eax
0x1800ad859  jz      short loc_1800AD868
0x1800ad85b  mov     rcx, rbx; lpFileName
0x1800ad85e  call    cs:__imp_DeleteFileA
0x1800ad864  test    eax, eax
0x1800ad866  jnz     short loc_1800AD86F
0x1800ad868  mov     eax, 1Ch
0x1800ad86d  jmp     short loc_1800AD8C6
0x1800ad86f  xor     r9d, r9d; lpSecurityAttributes
0x1800ad872  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800ad87b  mov     [rsp+48h+dwFlagsAndAttributes], 8000020h; dwFlagsAndAttributes
0x1800ad883  mov     edx, 0C0000000h; dwDesiredAccess
0x1800ad888  mov     rcx, rbx; lpFileName
0x1800ad88b  mov     [rsp+48h+dwCreationDisposition], 2; dwCreationDisposition
0x1800ad893  lea     r8d, [r9+3]; dwShareMode
0x1800ad897  call    cs:__imp_CreateFileA
0x1800ad89d  mov     [rdi+119F2h], rax
0x1800ad8a4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ad8a8  jz      short loc_1800AD8AE
0x1800ad8aa  xor     eax, eax
0x1800ad8ac  jmp     short loc_1800AD8C6
0x1800ad8ae  call    cs:__imp_GetLastError
0x1800ad8b4  mov     ecx, 1Ch
0x1800ad8b9  cmp     eax, 0CEh
0x1800ad8be  lea     edx, [rcx+17h]
0x1800ad8c1  cmovz   ecx, edx
0x1800ad8c4  mov     eax, ecx
0x1800ad8c6  mov     rbx, [rsp+48h+arg_0]
0x1800ad8cb  add     rsp, 40h
0x1800ad8cf  pop     rdi
0x1800ad8d0  retn
```
