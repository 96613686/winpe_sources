# MapMUIFile

- ea: `0x18000c8a4`
- end: `0x18000c988`
- name: `MapMUIFile`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x18000ca88`
- `0x18000cba0`

## callees

- `0x18000c8a4`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x18000c944`
- `KERNEL32!MapViewOfFile` at `0x18000c944`
- `KERNEL32!CreateFileMappingW` at `0x18000c917`
- `KERNEL32!CreateFileMappingW` at `0x18000c917`
- `KERNEL32!CreateFileW` at `0x18000c8e7`
- `KERNEL32!CreateFileW` at `0x18000c8e7`
- `KERNEL32!CloseHandle` at `0x18000c923`
- `KERNEL32!CloseHandle` at `0x18000c950`
- `KERNEL32!CloseHandle` at `0x18000c923`
- `KERNEL32!CloseHandle` at `0x18000c950`
- `KERNEL32!LoadLibraryExW` at `0x18000c973`
- `KERNEL32!LoadLibraryExW` at `0x18000c973`

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
0x18000c8a4  mov     [rsp+arg_0], rbx
0x18000c8a9  push    rdi
0x18000c8aa  sub     rsp, 40h
0x18000c8ae  mov     eax, r8d
0x18000c8b1  test    rcx, rcx
0x18000c8b4  jz      loc_18000C97B
0x18000c8ba  test    edx, edx
0x18000c8bc  jz      loc_18000C968
0x18000c8c2  xor     r9d, r9d; lpSecurityAttributes
0x18000c8c5  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18000c8ce  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18000c8d6  mov     edx, 80000000h; dwDesiredAccess
0x18000c8db  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18000c8e3  lea     r8d, [r9+5]; dwShareMode
0x18000c8e7  call    cs:__imp_CreateFileW
0x18000c8ed  mov     rbx, rax
0x18000c8f0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c8f4  jz      loc_18000C97B
0x18000c8fa  xor     r9d, r9d; dwMaximumSizeHigh
0x18000c8fd  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x18000c906  xor     edx, edx; lpFileMappingAttributes
0x18000c908  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18000c910  mov     rcx, rax; hFile
0x18000c913  lea     r8d, [r9+8]; flProtect
0x18000c917  call    cs:__imp_CreateFileMappingW
0x18000c91d  mov     rcx, rbx; hObject
0x18000c920  mov     rdi, rax
0x18000c923  call    cs:__imp_CloseHandle
0x18000c929  test    rdi, rdi
0x18000c92c  jz      short loc_18000C97B
0x18000c92e  xor     r9d, r9d; dwFileOffsetLow
0x18000c931  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18000c93a  xor     r8d, r8d; dwFileOffsetHigh
0x18000c93d  mov     rcx, rdi; hFileMappingObject
0x18000c940  lea     edx, [r9+1]; dwDesiredAccess
0x18000c944  call    cs:__imp_MapViewOfFile
0x18000c94a  mov     rcx, rdi; hObject
0x18000c94d  mov     rbx, rax
0x18000c950  call    cs:__imp_CloseHandle
0x18000c956  mov     rcx, rbx
0x18000c959  or      rcx, 1; lpLibFileName
0x18000c95d  neg     rbx
0x18000c960  sbb     rax, rax
0x18000c963  and     rax, rcx
0x18000c966  jmp     short loc_18000C97D
0x18000c968  xor     r8d, r8d
0x18000c96b  test    eax, eax
0x18000c96d  setnz   r8b; dwFlags
0x18000c971  xor     edx, edx; hFile
0x18000c973  call    cs:__imp_LoadLibraryExW
0x18000c979  jmp     short loc_18000C97D
0x18000c97b  xor     eax, eax
0x18000c97d  mov     rbx, [rsp+48h+arg_0]
0x18000c982  add     rsp, 40h
0x18000c986  pop     rdi
0x18000c987  retn
```
