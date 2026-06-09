# MapMUIFile

- ea: `0x180028a30`
- end: `0x180028b14`
- name: `MapMUIFile`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180028b5c`
- `0x180028c74`

## callees

- `0x180028a30`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180028aff`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180028aff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028aaf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028adc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028aaf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028adc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180028a73`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180028a73`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180028ad0`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180028ad0`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180028aa3`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180028aa3`

## pseudocode

```c
HMODULE __fastcall MapMUIFile(const WCHAR *a1, int a2, int a3)
{
  HANDLE FileW; // rax
  void *v4; // rbx
  HANDLE FileMappingW; // rdi
  unsigned __int64 v6; // rbx

  if ( a1 )
  {
    if ( !a2 )
      return LoadLibraryExW(a1, 0, a3 != 0);
    FileW = CreateFileW(a1, 0x80000000, 5u, 0, 3u, 0, 0);
    v4 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      FileMappingW = CreateFileMappingW(FileW, 0, 8u, 0, 0, 0);
      CloseHandle(v4);
      if ( FileMappingW )
      {
        v6 = (unsigned __int64)MapViewOfFile(FileMappingW, 1u, 0, 0, 0);
        CloseHandle(FileMappingW);
        return (HMODULE)((v6 | 1) & -(__int64)(v6 != 0));
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180028a30  mov     [rsp+arg_0], rbx
0x180028a35  push    rdi
0x180028a36  sub     rsp, 40h
0x180028a3a  mov     eax, r8d
0x180028a3d  test    rcx, rcx
0x180028a40  jz      loc_180028B07
0x180028a46  test    edx, edx
0x180028a48  jz      loc_180028AF4
0x180028a4e  xor     r9d, r9d; lpSecurityAttributes
0x180028a51  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180028a5a  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180028a62  mov     edx, 80000000h; dwDesiredAccess
0x180028a67  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180028a6f  lea     r8d, [r9+5]; dwShareMode
0x180028a73  call    cs:__imp_CreateFileW
0x180028a79  mov     rbx, rax
0x180028a7c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180028a80  jz      loc_180028B07
0x180028a86  xor     r9d, r9d; dwMaximumSizeHigh
0x180028a89  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x180028a92  xor     edx, edx; lpFileMappingAttributes
0x180028a94  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x180028a9c  mov     rcx, rax; hFile
0x180028a9f  lea     r8d, [r9+8]; flProtect
0x180028aa3  call    cs:__imp_CreateFileMappingW
0x180028aa9  mov     rcx, rbx; hObject
0x180028aac  mov     rdi, rax
0x180028aaf  call    cs:__imp_CloseHandle
0x180028ab5  test    rdi, rdi
0x180028ab8  jz      short loc_180028B07
0x180028aba  xor     r9d, r9d; dwFileOffsetLow
0x180028abd  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x180028ac6  xor     r8d, r8d; dwFileOffsetHigh
0x180028ac9  mov     rcx, rdi; hFileMappingObject
0x180028acc  lea     edx, [r9+1]; dwDesiredAccess
0x180028ad0  call    cs:__imp_MapViewOfFile
0x180028ad6  mov     rcx, rdi; hObject
0x180028ad9  mov     rbx, rax
0x180028adc  call    cs:__imp_CloseHandle
0x180028ae2  mov     rcx, rbx
0x180028ae5  or      rcx, 1; lpLibFileName
0x180028ae9  neg     rbx
0x180028aec  sbb     rax, rax
0x180028aef  and     rax, rcx
0x180028af2  jmp     short loc_180028B09
0x180028af4  xor     r8d, r8d
0x180028af7  test    eax, eax
0x180028af9  setnz   r8b; dwFlags
0x180028afd  xor     edx, edx; hFile
0x180028aff  call    cs:__imp_LoadLibraryExW
0x180028b05  jmp     short loc_180028B09
0x180028b07  xor     eax, eax
0x180028b09  mov     rbx, [rsp+48h+arg_0]
0x180028b0e  add     rsp, 40h
0x180028b12  pop     rdi
0x180028b13  retn
```
