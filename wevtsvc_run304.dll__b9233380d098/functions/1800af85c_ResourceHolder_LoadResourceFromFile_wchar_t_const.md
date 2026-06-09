# ResourceHolder::LoadResourceFromFile(wchar_t const *)

- ea: `0x1800af85c`
- end: `0x1800af918`
- name: `?LoadResourceFromFile@ResourceHolder@@AEAAKPEB_W@Z`
- size: `188`
- prototype: `unsigned int(ResourceHolder *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180039acc`

## callees

- `0x1800af85c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af8a5`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800af902`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800af902`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800af890`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800af890`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800af8c9`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800af8c9`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800af8ee`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800af8ee`

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
0x1800af85c  push    rbx
0x1800af85e  sub     rsp, 40h
0x1800af862  mov     rax, rdx
0x1800af865  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800af86e  xor     r9d, r9d; lpSecurityAttributes
0x1800af871  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800af879  mov     rbx, rcx
0x1800af87c  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1800af884  mov     edx, 80000000h; dwDesiredAccess
0x1800af889  mov     rcx, rax; lpFileName
0x1800af88c  lea     r8d, [r9+1]; dwShareMode
0x1800af890  call    cs:__imp_CreateFileW
0x1800af896  mov     [rbx+30h], rax
0x1800af89a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800af89e  jnz     short loc_1800AF8AC
0x1800af8a0  add     rsp, 40h
0x1800af8a4  pop     rbx
0x1800af8a5  jmp     cs:__imp_GetLastError
0x1800af8ac  xor     r9d, r9d; dwMaximumSizeHigh
0x1800af8af  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x1800af8b8  xor     edx, edx; lpFileMappingAttributes
0x1800af8ba  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x1800af8c2  mov     rcx, rax; hFile
0x1800af8c5  lea     r8d, [r9+2]; flProtect
0x1800af8c9  call    cs:__imp_CreateFileMappingW
0x1800af8cf  mov     [rbx+38h], rax
0x1800af8d3  test    rax, rax
0x1800af8d6  jz      short loc_1800AF8A0
0x1800af8d8  xor     r9d, r9d; dwFileOffsetLow
0x1800af8db  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x1800af8e4  xor     r8d, r8d; dwFileOffsetHigh
0x1800af8e7  mov     rcx, rax; hFileMappingObject
0x1800af8ea  lea     edx, [r9+4]; dwDesiredAccess
0x1800af8ee  call    cs:__imp_MapViewOfFile
0x1800af8f4  mov     [rbx], rax
0x1800af8f7  test    rax, rax
0x1800af8fa  jz      short loc_1800AF8A0
0x1800af8fc  mov     rcx, [rbx+30h]; hFile
0x1800af900  xor     edx, edx; lpFileSizeHigh
0x1800af902  call    cs:__imp_GetFileSize
0x1800af908  mov     [rbx+18h], eax
0x1800af90b  cmp     eax, 0FFFFFFFFh
0x1800af90e  jz      short loc_1800AF8A0
0x1800af910  xor     eax, eax
0x1800af912  add     rsp, 40h
0x1800af916  pop     rbx
0x1800af917  retn
```
