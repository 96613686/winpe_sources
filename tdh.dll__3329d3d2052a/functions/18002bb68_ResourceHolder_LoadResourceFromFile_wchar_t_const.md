# ResourceHolder::LoadResourceFromFile(wchar_t const *)

- ea: `0x18002bb68`
- end: `0x18002bc24`
- name: `?LoadResourceFromFile@ResourceHolder@@AEAAKPEB_W@Z`
- size: `188`
- prototype: `DWORD __fastcall(ResourceHolder *this, const wchar_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000799c`

## callees

- `0x18002bb68`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002bc0e`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002bc0e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002bb9c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002bb9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bbb1`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002bbd5`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002bbd5`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002bbfa`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002bbfa`

## pseudocode

```c
DWORD __fastcall ResourceHolder::LoadResourceFromFile(ResourceHolder *this, const wchar_t *a2)
{
  HANDLE FileW; // rax
  HANDLE FileMappingW; // rax
  LPVOID v6; // rax
  DWORD FileSize; // eax

  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  *((_QWORD *)this + 6) = FileW;
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  FileMappingW = CreateFileMappingW(FileW, 0, 2u, 0, 0, 0);
  *((_QWORD *)this + 7) = FileMappingW;
  if ( !FileMappingW )
    return GetLastError();
  v6 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
  *(_QWORD *)this = v6;
  if ( !v6 )
    return GetLastError();
  FileSize = GetFileSize(*((HANDLE *)this + 6), 0);
  *((_DWORD *)this + 6) = FileSize;
  if ( FileSize == -1 )
    return GetLastError();
  else
    return 0;
}

```

## disassembly

```asm
0x18002bb68  push    rbx
0x18002bb6a  sub     rsp, 40h
0x18002bb6e  mov     rax, rdx
0x18002bb71  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18002bb7a  xor     r9d, r9d; lpSecurityAttributes
0x18002bb7d  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002bb85  mov     rbx, rcx
0x18002bb88  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18002bb90  mov     edx, 80000000h; dwDesiredAccess
0x18002bb95  mov     rcx, rax; lpFileName
0x18002bb98  lea     r8d, [r9+1]; dwShareMode
0x18002bb9c  call    cs:__imp_CreateFileW
0x18002bba2  mov     [rbx+30h], rax
0x18002bba6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002bbaa  jnz     short loc_18002BBB8
0x18002bbac  add     rsp, 40h
0x18002bbb0  pop     rbx
0x18002bbb1  jmp     cs:__imp_GetLastError
0x18002bbb8  xor     r9d, r9d; dwMaximumSizeHigh
0x18002bbbb  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x18002bbc4  xor     edx, edx; lpFileMappingAttributes
0x18002bbc6  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18002bbce  mov     rcx, rax; hFile
0x18002bbd1  lea     r8d, [r9+2]; flProtect
0x18002bbd5  call    cs:__imp_CreateFileMappingW
0x18002bbdb  mov     [rbx+38h], rax
0x18002bbdf  test    rax, rax
0x18002bbe2  jz      short loc_18002BBAC
0x18002bbe4  xor     r9d, r9d; dwFileOffsetLow
0x18002bbe7  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18002bbf0  xor     r8d, r8d; dwFileOffsetHigh
0x18002bbf3  mov     rcx, rax; hFileMappingObject
0x18002bbf6  lea     edx, [r9+4]; dwDesiredAccess
0x18002bbfa  call    cs:__imp_MapViewOfFile
0x18002bc00  mov     [rbx], rax
0x18002bc03  test    rax, rax
0x18002bc06  jz      short loc_18002BBAC
0x18002bc08  mov     rcx, [rbx+30h]; hFile
0x18002bc0c  xor     edx, edx; lpFileSizeHigh
0x18002bc0e  call    cs:__imp_GetFileSize
0x18002bc14  mov     [rbx+18h], eax
0x18002bc17  cmp     eax, 0FFFFFFFFh
0x18002bc1a  jz      short loc_18002BBAC
0x18002bc1c  xor     eax, eax
0x18002bc1e  add     rsp, 40h
0x18002bc22  pop     rbx
0x18002bc23  retn
```
