# MapMUIFile

- ea: `0x18001ab64`
- end: `0x18001ac48`
- name: `MapMUIFile`
- size: `228`
- prototype: `HMODULE __fastcall(const WCHAR *, int, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x18001ac90`
- `0x18001ada8`

## callees

- `0x18001ab64`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001ac33`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001ac33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001abe3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ac10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001abe3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ac10`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001aba7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001aba7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001ac04`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001ac04`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001abd7`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001abd7`

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
0x18001ab64  mov     [rsp+arg_0], rbx
0x18001ab69  push    rdi
0x18001ab6a  sub     rsp, 40h
0x18001ab6e  mov     eax, r8d
0x18001ab71  test    rcx, rcx
0x18001ab74  jz      loc_18001AC3B
0x18001ab7a  test    edx, edx
0x18001ab7c  jz      loc_18001AC28
0x18001ab82  xor     r9d, r9d; lpSecurityAttributes
0x18001ab85  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18001ab8e  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18001ab96  mov     edx, 80000000h; dwDesiredAccess
0x18001ab9b  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18001aba3  lea     r8d, [r9+5]; dwShareMode
0x18001aba7  call    cs:__imp_CreateFileW
0x18001abad  mov     rbx, rax
0x18001abb0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001abb4  jz      loc_18001AC3B
0x18001abba  xor     r9d, r9d; dwMaximumSizeHigh
0x18001abbd  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x18001abc6  xor     edx, edx; lpFileMappingAttributes
0x18001abc8  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18001abd0  mov     rcx, rax; hFile
0x18001abd3  lea     r8d, [r9+8]; flProtect
0x18001abd7  call    cs:__imp_CreateFileMappingW
0x18001abdd  mov     rcx, rbx; hObject
0x18001abe0  mov     rdi, rax
0x18001abe3  call    cs:__imp_CloseHandle
0x18001abe9  test    rdi, rdi
0x18001abec  jz      short loc_18001AC3B
0x18001abee  xor     r9d, r9d; dwFileOffsetLow
0x18001abf1  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18001abfa  xor     r8d, r8d; dwFileOffsetHigh
0x18001abfd  mov     rcx, rdi; hFileMappingObject
0x18001ac00  lea     edx, [r9+1]; dwDesiredAccess
0x18001ac04  call    cs:__imp_MapViewOfFile
0x18001ac0a  mov     rcx, rdi; hObject
0x18001ac0d  mov     rbx, rax
0x18001ac10  call    cs:__imp_CloseHandle
0x18001ac16  mov     rcx, rbx
0x18001ac19  or      rcx, 1; lpLibFileName
0x18001ac1d  neg     rbx
0x18001ac20  sbb     rax, rax
0x18001ac23  and     rax, rcx
0x18001ac26  jmp     short loc_18001AC3D
0x18001ac28  xor     r8d, r8d
0x18001ac2b  test    eax, eax
0x18001ac2d  setnz   r8b; dwFlags
0x18001ac31  xor     edx, edx; hFile
0x18001ac33  call    cs:__imp_LoadLibraryExW
0x18001ac39  jmp     short loc_18001AC3D
0x18001ac3b  xor     eax, eax
0x18001ac3d  mov     rbx, [rsp+48h+arg_0]
0x18001ac42  add     rsp, 40h
0x18001ac46  pop     rdi
0x18001ac47  retn
```
