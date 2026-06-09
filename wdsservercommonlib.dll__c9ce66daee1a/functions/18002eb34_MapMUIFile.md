# MapMUIFile

- ea: `0x18002eb34`
- end: `0x18002ec2f`
- name: `MapMUIFile`
- size: `251`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x18002ec84`
- `0x18002edd8`

## callees

- `0x18002eb34`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18002ec0e`
- `KERNEL32!LoadLibraryExW` at `0x18002ec0e`
- `KERNEL32!CloseHandle` at `0x18002ebb1`
- `KERNEL32!CloseHandle` at `0x18002ebe5`
- `KERNEL32!CloseHandle` at `0x18002ebb1`
- `KERNEL32!CloseHandle` at `0x18002ebe5`
- `KERNEL32!MapViewOfFile` at `0x18002ebd3`
- `KERNEL32!MapViewOfFile` at `0x18002ebd3`
- `KERNEL32!CreateFileMappingW` at `0x18002eb9f`
- `KERNEL32!CreateFileMappingW` at `0x18002eb9f`
- `KERNEL32!CreateFileW` at `0x18002eb71`
- `KERNEL32!CreateFileW` at `0x18002eb71`

## pseudocode

```c
HMODULE __fastcall MapMUIFile(const WCHAR *a1, int a2, int a3)
{
  DWORD v3; // ebx
  HANDLE FileW; // rax
  void *v5; // rdi
  HANDLE FileMappingW; // rsi
  unsigned __int64 v7; // rbx

  v3 = 0;
  if ( a1 )
  {
    if ( !a2 )
    {
      LOBYTE(v3) = a3 != 0;
      return LoadLibraryExW(a1, 0, v3);
    }
    FileW = CreateFileW(a1, 0x80000000, 5u, 0, 3u, 0, 0);
    v5 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      FileMappingW = CreateFileMappingW(FileW, 0, 8u, 0, 0, 0);
      CloseHandle(v5);
      if ( FileMappingW )
      {
        v7 = (unsigned __int64)MapViewOfFile(FileMappingW, 1u, 0, 0, 0);
        CloseHandle(FileMappingW);
        return (HMODULE)((v7 | 1) & -(__int64)(v7 != 0));
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002eb34  mov     rax, rsp
0x18002eb37  mov     [rax+8], rbx
0x18002eb3b  mov     [rax+10h], rsi
0x18002eb3f  push    rdi
0x18002eb40  sub     rsp, 40h
0x18002eb44  xor     ebx, ebx
0x18002eb46  test    rcx, rcx
0x18002eb49  jz      loc_18002EC1C
0x18002eb4f  test    edx, edx
0x18002eb51  jz      loc_18002EC03
0x18002eb57  mov     [rax-18h], rbx
0x18002eb5b  lea     r8d, [rbx+5]; dwShareMode
0x18002eb5f  mov     [rax-20h], ebx
0x18002eb62  xor     r9d, r9d; lpSecurityAttributes
0x18002eb65  mov     edx, 80000000h; dwDesiredAccess
0x18002eb6a  mov     dword ptr [rax-28h], 3
0x18002eb71  call    cs:__imp_CreateFileW
0x18002eb78  nop     dword ptr [rax+rax+00h]
0x18002eb7d  mov     rdi, rax
0x18002eb80  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002eb84  jz      loc_18002EC1C
0x18002eb8a  mov     [rsp+48h+lpName], rbx; lpName
0x18002eb8f  lea     r8d, [rbx+8]; flProtect
0x18002eb93  xor     r9d, r9d; dwMaximumSizeHigh
0x18002eb96  mov     [rsp+48h+dwMaximumSizeLow], ebx; dwMaximumSizeLow
0x18002eb9a  xor     edx, edx; lpFileMappingAttributes
0x18002eb9c  mov     rcx, rax; hFile
0x18002eb9f  call    cs:__imp_CreateFileMappingW
0x18002eba6  nop     dword ptr [rax+rax+00h]
0x18002ebab  mov     rcx, rdi; hObject
0x18002ebae  mov     rsi, rax
0x18002ebb1  call    cs:__imp_CloseHandle
0x18002ebb8  nop     dword ptr [rax+rax+00h]
0x18002ebbd  test    rsi, rsi
0x18002ebc0  jz      short loc_18002EC1C
0x18002ebc2  xor     r9d, r9d; dwFileOffsetLow
0x18002ebc5  mov     qword ptr [rsp+48h+dwMaximumSizeLow], rbx; dwNumberOfBytesToMap
0x18002ebca  xor     r8d, r8d; dwFileOffsetHigh
0x18002ebcd  lea     edx, [rbx+1]; dwDesiredAccess
0x18002ebd0  mov     rcx, rsi; hFileMappingObject
0x18002ebd3  call    cs:__imp_MapViewOfFile
0x18002ebda  nop     dword ptr [rax+rax+00h]
0x18002ebdf  mov     rcx, rsi; hObject
0x18002ebe2  mov     rbx, rax
0x18002ebe5  call    cs:__imp_CloseHandle
0x18002ebec  nop     dword ptr [rax+rax+00h]
0x18002ebf1  mov     rcx, rbx
0x18002ebf4  or      rcx, 1; lpLibFileName
0x18002ebf8  neg     rbx
0x18002ebfb  sbb     rax, rax
0x18002ebfe  and     rax, rcx
0x18002ec01  jmp     short loc_18002EC1E
0x18002ec03  test    r8d, r8d
0x18002ec06  setnz   bl
0x18002ec09  xor     edx, edx; hFile
0x18002ec0b  mov     r8d, ebx; dwFlags
0x18002ec0e  call    cs:__imp_LoadLibraryExW
0x18002ec15  nop     dword ptr [rax+rax+00h]
0x18002ec1a  jmp     short loc_18002EC1E
0x18002ec1c  xor     eax, eax
0x18002ec1e  mov     rbx, [rsp+48h+arg_0]
0x18002ec23  mov     rsi, [rsp+48h+arg_8]
0x18002ec28  add     rsp, 40h
0x18002ec2c  pop     rdi
0x18002ec2d  retn
```
