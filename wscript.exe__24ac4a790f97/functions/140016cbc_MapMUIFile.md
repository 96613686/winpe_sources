# MapMUIFile

- ea: `0x140016cbc`
- end: `0x140016da0`
- name: `MapMUIFile`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x140016e80`
- `0x140016f68`

## callees

- `0x140016cbc`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140016d3b`
- `KERNEL32!CloseHandle` at `0x140016d68`
- `KERNEL32!CloseHandle` at `0x140016d3b`
- `KERNEL32!CloseHandle` at `0x140016d68`
- `KERNEL32!CreateFileMappingW` at `0x140016d2f`
- `KERNEL32!CreateFileMappingW` at `0x140016d2f`
- `KERNEL32!CreateFileW` at `0x140016cff`
- `KERNEL32!CreateFileW` at `0x140016cff`
- `KERNEL32!LoadLibraryExW` at `0x140016d8b`
- `KERNEL32!LoadLibraryExW` at `0x140016d8b`
- `KERNEL32!MapViewOfFile` at `0x140016d5c`
- `KERNEL32!MapViewOfFile` at `0x140016d5c`

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
0x140016cbc  mov     [rsp+arg_0], rbx
0x140016cc1  push    rdi
0x140016cc2  sub     rsp, 40h
0x140016cc6  mov     eax, r8d
0x140016cc9  test    rcx, rcx
0x140016ccc  jz      loc_140016D93
0x140016cd2  test    edx, edx
0x140016cd4  jz      loc_140016D80
0x140016cda  xor     r9d, r9d; lpSecurityAttributes
0x140016cdd  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x140016ce6  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x140016cee  mov     edx, 80000000h; dwDesiredAccess
0x140016cf3  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x140016cfb  lea     r8d, [r9+5]; dwShareMode
0x140016cff  call    cs:__imp_CreateFileW
0x140016d05  mov     rbx, rax
0x140016d08  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140016d0c  jz      loc_140016D93
0x140016d12  xor     r9d, r9d; dwMaximumSizeHigh
0x140016d15  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x140016d1e  xor     edx, edx; lpFileMappingAttributes
0x140016d20  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x140016d28  mov     rcx, rax; hFile
0x140016d2b  lea     r8d, [r9+8]; flProtect
0x140016d2f  call    cs:__imp_CreateFileMappingW
0x140016d35  mov     rcx, rbx; hObject
0x140016d38  mov     rdi, rax
0x140016d3b  call    cs:__imp_CloseHandle
0x140016d41  test    rdi, rdi
0x140016d44  jz      short loc_140016D93
0x140016d46  xor     r9d, r9d; dwFileOffsetLow
0x140016d49  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x140016d52  xor     r8d, r8d; dwFileOffsetHigh
0x140016d55  mov     rcx, rdi; hFileMappingObject
0x140016d58  lea     edx, [r9+1]; dwDesiredAccess
0x140016d5c  call    cs:__imp_MapViewOfFile
0x140016d62  mov     rcx, rdi; hObject
0x140016d65  mov     rbx, rax
0x140016d68  call    cs:__imp_CloseHandle
0x140016d6e  mov     rcx, rbx
0x140016d71  or      rcx, 1; lpLibFileName
0x140016d75  neg     rbx
0x140016d78  sbb     rax, rax
0x140016d7b  and     rax, rcx
0x140016d7e  jmp     short loc_140016D95
0x140016d80  xor     r8d, r8d
0x140016d83  test    eax, eax
0x140016d85  setnz   r8b; dwFlags
0x140016d89  xor     edx, edx; hFile
0x140016d8b  call    cs:__imp_LoadLibraryExW
0x140016d91  jmp     short loc_140016D95
0x140016d93  xor     eax, eax
0x140016d95  mov     rbx, [rsp+48h+arg_0]
0x140016d9a  add     rsp, 40h
0x140016d9e  pop     rdi
0x140016d9f  retn
```
