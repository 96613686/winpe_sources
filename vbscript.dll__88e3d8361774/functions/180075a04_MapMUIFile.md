# MapMUIFile

- ea: `0x180075a04`
- end: `0x180075ae8`
- name: `MapMUIFile`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180075b30`
- `0x180075c48`

## callees

- `0x180075a04`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x180075aa4`
- `KERNEL32!MapViewOfFile` at `0x180075aa4`
- `KERNEL32!CreateFileMappingW` at `0x180075a77`
- `KERNEL32!CreateFileMappingW` at `0x180075a77`
- `KERNEL32!CreateFileW` at `0x180075a47`
- `KERNEL32!CreateFileW` at `0x180075a47`
- `KERNEL32!LoadLibraryExW` at `0x180075ad3`
- `KERNEL32!LoadLibraryExW` at `0x180075ad3`
- `KERNEL32!CloseHandle` at `0x180075a83`
- `KERNEL32!CloseHandle` at `0x180075ab0`
- `KERNEL32!CloseHandle` at `0x180075a83`
- `KERNEL32!CloseHandle` at `0x180075ab0`

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
0x180075a04  mov     [rsp+arg_0], rbx
0x180075a09  push    rdi
0x180075a0a  sub     rsp, 40h
0x180075a0e  mov     eax, r8d
0x180075a11  test    rcx, rcx
0x180075a14  jz      loc_180075ADB
0x180075a1a  test    edx, edx
0x180075a1c  jz      loc_180075AC8
0x180075a22  xor     r9d, r9d; lpSecurityAttributes
0x180075a25  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180075a2e  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180075a36  mov     edx, 80000000h; dwDesiredAccess
0x180075a3b  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180075a43  lea     r8d, [r9+5]; dwShareMode
0x180075a47  call    cs:__imp_CreateFileW
0x180075a4d  mov     rbx, rax
0x180075a50  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180075a54  jz      loc_180075ADB
0x180075a5a  xor     r9d, r9d; dwMaximumSizeHigh
0x180075a5d  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x180075a66  xor     edx, edx; lpFileMappingAttributes
0x180075a68  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x180075a70  mov     rcx, rax; hFile
0x180075a73  lea     r8d, [r9+8]; flProtect
0x180075a77  call    cs:__imp_CreateFileMappingW
0x180075a7d  mov     rcx, rbx; hObject
0x180075a80  mov     rdi, rax
0x180075a83  call    cs:__imp_CloseHandle
0x180075a89  test    rdi, rdi
0x180075a8c  jz      short loc_180075ADB
0x180075a8e  xor     r9d, r9d; dwFileOffsetLow
0x180075a91  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x180075a9a  xor     r8d, r8d; dwFileOffsetHigh
0x180075a9d  mov     rcx, rdi; hFileMappingObject
0x180075aa0  lea     edx, [r9+1]; dwDesiredAccess
0x180075aa4  call    cs:__imp_MapViewOfFile
0x180075aaa  mov     rcx, rdi; hObject
0x180075aad  mov     rbx, rax
0x180075ab0  call    cs:__imp_CloseHandle
0x180075ab6  mov     rcx, rbx
0x180075ab9  or      rcx, 1; lpLibFileName
0x180075abd  neg     rbx
0x180075ac0  sbb     rax, rax
0x180075ac3  and     rax, rcx
0x180075ac6  jmp     short loc_180075ADD
0x180075ac8  xor     r8d, r8d
0x180075acb  test    eax, eax
0x180075acd  setnz   r8b; dwFlags
0x180075ad1  xor     edx, edx; hFile
0x180075ad3  call    cs:__imp_LoadLibraryExW
0x180075ad9  jmp     short loc_180075ADD
0x180075adb  xor     eax, eax
0x180075add  mov     rbx, [rsp+48h+arg_0]
0x180075ae2  add     rsp, 40h
0x180075ae6  pop     rdi
0x180075ae7  retn
```
