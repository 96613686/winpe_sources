# MapMUIFile

- ea: `0x18000f980`
- end: `0x18000fa64`
- name: `MapMUIFile`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x18000fb64`
- `0x18000fc7c`

## callees

- `0x18000f980`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x18000fa20`
- `KERNEL32!MapViewOfFile` at `0x18000fa20`
- `KERNEL32!CreateFileMappingW` at `0x18000f9f3`
- `KERNEL32!CreateFileMappingW` at `0x18000f9f3`
- `KERNEL32!CreateFileW` at `0x18000f9c3`
- `KERNEL32!CreateFileW` at `0x18000f9c3`
- `KERNEL32!CloseHandle` at `0x18000f9ff`
- `KERNEL32!CloseHandle` at `0x18000fa2c`
- `KERNEL32!CloseHandle` at `0x18000f9ff`
- `KERNEL32!CloseHandle` at `0x18000fa2c`
- `KERNEL32!LoadLibraryExW` at `0x18000fa4f`
- `KERNEL32!LoadLibraryExW` at `0x18000fa4f`

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
0x18000f980  mov     [rsp+arg_0], rbx
0x18000f985  push    rdi
0x18000f986  sub     rsp, 40h
0x18000f98a  mov     eax, r8d
0x18000f98d  test    rcx, rcx
0x18000f990  jz      loc_18000FA57
0x18000f996  test    edx, edx
0x18000f998  jz      loc_18000FA44
0x18000f99e  xor     r9d, r9d; lpSecurityAttributes
0x18000f9a1  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18000f9aa  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18000f9b2  mov     edx, 80000000h; dwDesiredAccess
0x18000f9b7  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18000f9bf  lea     r8d, [r9+5]; dwShareMode
0x18000f9c3  call    cs:__imp_CreateFileW
0x18000f9c9  mov     rbx, rax
0x18000f9cc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f9d0  jz      loc_18000FA57
0x18000f9d6  xor     r9d, r9d; dwMaximumSizeHigh
0x18000f9d9  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x18000f9e2  xor     edx, edx; lpFileMappingAttributes
0x18000f9e4  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18000f9ec  mov     rcx, rax; hFile
0x18000f9ef  lea     r8d, [r9+8]; flProtect
0x18000f9f3  call    cs:__imp_CreateFileMappingW
0x18000f9f9  mov     rcx, rbx; hObject
0x18000f9fc  mov     rdi, rax
0x18000f9ff  call    cs:__imp_CloseHandle
0x18000fa05  test    rdi, rdi
0x18000fa08  jz      short loc_18000FA57
0x18000fa0a  xor     r9d, r9d; dwFileOffsetLow
0x18000fa0d  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18000fa16  xor     r8d, r8d; dwFileOffsetHigh
0x18000fa19  mov     rcx, rdi; hFileMappingObject
0x18000fa1c  lea     edx, [r9+1]; dwDesiredAccess
0x18000fa20  call    cs:__imp_MapViewOfFile
0x18000fa26  mov     rcx, rdi; hObject
0x18000fa29  mov     rbx, rax
0x18000fa2c  call    cs:__imp_CloseHandle
0x18000fa32  mov     rcx, rbx
0x18000fa35  or      rcx, 1; lpLibFileName
0x18000fa39  neg     rbx
0x18000fa3c  sbb     rax, rax
0x18000fa3f  and     rax, rcx
0x18000fa42  jmp     short loc_18000FA59
0x18000fa44  xor     r8d, r8d
0x18000fa47  test    eax, eax
0x18000fa49  setnz   r8b; dwFlags
0x18000fa4d  xor     edx, edx; hFile
0x18000fa4f  call    cs:__imp_LoadLibraryExW
0x18000fa55  jmp     short loc_18000FA59
0x18000fa57  xor     eax, eax
0x18000fa59  mov     rbx, [rsp+48h+arg_0]
0x18000fa5e  add     rsp, 40h
0x18000fa62  pop     rdi
0x18000fa63  retn
```
