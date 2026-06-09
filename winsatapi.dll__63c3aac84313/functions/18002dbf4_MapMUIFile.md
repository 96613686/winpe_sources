# MapMUIFile

- ea: `0x18002dbf4`
- end: `0x18002dcd8`
- name: `MapMUIFile`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180010818`
- `0x18002dd20`

## callees

- `0x18002dbf4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002dcc3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002dcc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dc73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dca0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dc73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dca0`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002dc67`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002dc67`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002dc94`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002dc94`
- `KERNEL32!CreateFileW` at `0x18002dc37`
- `KERNEL32!CreateFileW` at `0x18002dc37`

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
0x18002dbf4  mov     [rsp+arg_0], rbx
0x18002dbf9  push    rdi
0x18002dbfa  sub     rsp, 40h
0x18002dbfe  mov     eax, r8d
0x18002dc01  test    rcx, rcx
0x18002dc04  jz      loc_18002DCCB
0x18002dc0a  test    edx, edx
0x18002dc0c  jz      loc_18002DCB8
0x18002dc12  xor     r9d, r9d; lpSecurityAttributes
0x18002dc15  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18002dc1e  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18002dc26  mov     edx, 80000000h; dwDesiredAccess
0x18002dc2b  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18002dc33  lea     r8d, [r9+5]; dwShareMode
0x18002dc37  call    cs:__imp_CreateFileW
0x18002dc3d  mov     rbx, rax
0x18002dc40  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002dc44  jz      loc_18002DCCB
0x18002dc4a  xor     r9d, r9d; dwMaximumSizeHigh
0x18002dc4d  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x18002dc56  xor     edx, edx; lpFileMappingAttributes
0x18002dc58  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18002dc60  mov     rcx, rax; hFile
0x18002dc63  lea     r8d, [r9+8]; flProtect
0x18002dc67  call    cs:__imp_CreateFileMappingW
0x18002dc6d  mov     rcx, rbx; hObject
0x18002dc70  mov     rdi, rax
0x18002dc73  call    cs:__imp_CloseHandle
0x18002dc79  test    rdi, rdi
0x18002dc7c  jz      short loc_18002DCCB
0x18002dc7e  xor     r9d, r9d; dwFileOffsetLow
0x18002dc81  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18002dc8a  xor     r8d, r8d; dwFileOffsetHigh
0x18002dc8d  mov     rcx, rdi; hFileMappingObject
0x18002dc90  lea     edx, [r9+1]; dwDesiredAccess
0x18002dc94  call    cs:__imp_MapViewOfFile
0x18002dc9a  mov     rcx, rdi; hObject
0x18002dc9d  mov     rbx, rax
0x18002dca0  call    cs:__imp_CloseHandle
0x18002dca6  mov     rcx, rbx
0x18002dca9  or      rcx, 1; lpLibFileName
0x18002dcad  neg     rbx
0x18002dcb0  sbb     rax, rax
0x18002dcb3  and     rax, rcx
0x18002dcb6  jmp     short loc_18002DCCD
0x18002dcb8  xor     r8d, r8d
0x18002dcbb  test    eax, eax
0x18002dcbd  setnz   r8b; dwFlags
0x18002dcc1  xor     edx, edx; hFile
0x18002dcc3  call    cs:__imp_LoadLibraryExW
0x18002dcc9  jmp     short loc_18002DCCD
0x18002dccb  xor     eax, eax
0x18002dccd  mov     rbx, [rsp+48h+arg_0]
0x18002dcd2  add     rsp, 40h
0x18002dcd6  pop     rdi
0x18002dcd7  retn
```
