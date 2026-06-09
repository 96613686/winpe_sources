# MapMUIFile

- ea: `0x14003f844`
- end: `0x14003f928`
- name: `MapMUIFile`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x14003fa08`
- `0x14003faf0`

## callees

- `0x14003f844`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14003f887`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14003f887`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003f8c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003f8f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003f8c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003f8f0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14003f913`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14003f913`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x14003f8b7`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x14003f8b7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14003f8e4`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14003f8e4`

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
0x14003f844  mov     [rsp+arg_0], rbx
0x14003f849  push    rdi
0x14003f84a  sub     rsp, 40h
0x14003f84e  mov     eax, r8d
0x14003f851  test    rcx, rcx
0x14003f854  jz      loc_14003F91B
0x14003f85a  test    edx, edx
0x14003f85c  jz      loc_14003F908
0x14003f862  xor     r9d, r9d; lpSecurityAttributes
0x14003f865  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x14003f86e  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x14003f876  mov     edx, 80000000h; dwDesiredAccess
0x14003f87b  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x14003f883  lea     r8d, [r9+5]; dwShareMode
0x14003f887  call    cs:__imp_CreateFileW
0x14003f88d  mov     rbx, rax
0x14003f890  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14003f894  jz      loc_14003F91B
0x14003f89a  xor     r9d, r9d; dwMaximumSizeHigh
0x14003f89d  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x14003f8a6  xor     edx, edx; lpFileMappingAttributes
0x14003f8a8  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x14003f8b0  mov     rcx, rax; hFile
0x14003f8b3  lea     r8d, [r9+8]; flProtect
0x14003f8b7  call    cs:__imp_CreateFileMappingW
0x14003f8bd  mov     rcx, rbx; hObject
0x14003f8c0  mov     rdi, rax
0x14003f8c3  call    cs:__imp_CloseHandle
0x14003f8c9  test    rdi, rdi
0x14003f8cc  jz      short loc_14003F91B
0x14003f8ce  xor     r9d, r9d; dwFileOffsetLow
0x14003f8d1  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x14003f8da  xor     r8d, r8d; dwFileOffsetHigh
0x14003f8dd  mov     rcx, rdi; hFileMappingObject
0x14003f8e0  lea     edx, [r9+1]; dwDesiredAccess
0x14003f8e4  call    cs:__imp_MapViewOfFile
0x14003f8ea  mov     rcx, rdi; hObject
0x14003f8ed  mov     rbx, rax
0x14003f8f0  call    cs:__imp_CloseHandle
0x14003f8f6  mov     rcx, rbx
0x14003f8f9  or      rcx, 1; lpLibFileName
0x14003f8fd  neg     rbx
0x14003f900  sbb     rax, rax
0x14003f903  and     rax, rcx
0x14003f906  jmp     short loc_14003F91D
0x14003f908  xor     r8d, r8d
0x14003f90b  test    eax, eax
0x14003f90d  setnz   r8b; dwFlags
0x14003f911  xor     edx, edx; hFile
0x14003f913  call    cs:__imp_LoadLibraryExW
0x14003f919  jmp     short loc_14003F91D
0x14003f91b  xor     eax, eax
0x14003f91d  mov     rbx, [rsp+48h+arg_0]
0x14003f922  add     rsp, 40h
0x14003f926  pop     rdi
0x14003f927  retn
```
