# MapMUIFile

- ea: `0x18002faec`
- end: `0x18002fbe7`
- name: `MapMUIFile`
- size: `251`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x18002fc3c`
- `0x18002fd90`

## callees

- `0x18002faec`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18002fb29`
- `KERNEL32!CreateFileW` at `0x18002fb29`
- `KERNEL32!CloseHandle` at `0x18002fb69`
- `KERNEL32!CloseHandle` at `0x18002fb9d`
- `KERNEL32!CloseHandle` at `0x18002fb69`
- `KERNEL32!CloseHandle` at `0x18002fb9d`
- `KERNEL32!LoadLibraryExW` at `0x18002fbc6`
- `KERNEL32!LoadLibraryExW` at `0x18002fbc6`
- `KERNEL32!MapViewOfFile` at `0x18002fb8b`
- `KERNEL32!MapViewOfFile` at `0x18002fb8b`
- `KERNEL32!CreateFileMappingW` at `0x18002fb57`
- `KERNEL32!CreateFileMappingW` at `0x18002fb57`

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
0x18002faec  mov     rax, rsp
0x18002faef  mov     [rax+8], rbx
0x18002faf3  mov     [rax+10h], rsi
0x18002faf7  push    rdi
0x18002faf8  sub     rsp, 40h
0x18002fafc  xor     ebx, ebx
0x18002fafe  test    rcx, rcx
0x18002fb01  jz      loc_18002FBD4
0x18002fb07  test    edx, edx
0x18002fb09  jz      loc_18002FBBB
0x18002fb0f  mov     [rax-18h], rbx
0x18002fb13  lea     r8d, [rbx+5]; dwShareMode
0x18002fb17  mov     [rax-20h], ebx
0x18002fb1a  xor     r9d, r9d; lpSecurityAttributes
0x18002fb1d  mov     edx, 80000000h; dwDesiredAccess
0x18002fb22  mov     dword ptr [rax-28h], 3
0x18002fb29  call    cs:__imp_CreateFileW
0x18002fb30  nop     dword ptr [rax+rax+00h]
0x18002fb35  mov     rdi, rax
0x18002fb38  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002fb3c  jz      loc_18002FBD4
0x18002fb42  mov     [rsp+48h+lpName], rbx; lpName
0x18002fb47  lea     r8d, [rbx+8]; flProtect
0x18002fb4b  xor     r9d, r9d; dwMaximumSizeHigh
0x18002fb4e  mov     [rsp+48h+dwMaximumSizeLow], ebx; dwMaximumSizeLow
0x18002fb52  xor     edx, edx; lpFileMappingAttributes
0x18002fb54  mov     rcx, rax; hFile
0x18002fb57  call    cs:__imp_CreateFileMappingW
0x18002fb5e  nop     dword ptr [rax+rax+00h]
0x18002fb63  mov     rcx, rdi; hObject
0x18002fb66  mov     rsi, rax
0x18002fb69  call    cs:__imp_CloseHandle
0x18002fb70  nop     dword ptr [rax+rax+00h]
0x18002fb75  test    rsi, rsi
0x18002fb78  jz      short loc_18002FBD4
0x18002fb7a  xor     r9d, r9d; dwFileOffsetLow
0x18002fb7d  mov     qword ptr [rsp+48h+dwMaximumSizeLow], rbx; dwNumberOfBytesToMap
0x18002fb82  xor     r8d, r8d; dwFileOffsetHigh
0x18002fb85  lea     edx, [rbx+1]; dwDesiredAccess
0x18002fb88  mov     rcx, rsi; hFileMappingObject
0x18002fb8b  call    cs:__imp_MapViewOfFile
0x18002fb92  nop     dword ptr [rax+rax+00h]
0x18002fb97  mov     rcx, rsi; hObject
0x18002fb9a  mov     rbx, rax
0x18002fb9d  call    cs:__imp_CloseHandle
0x18002fba4  nop     dword ptr [rax+rax+00h]
0x18002fba9  mov     rcx, rbx
0x18002fbac  or      rcx, 1; lpLibFileName
0x18002fbb0  neg     rbx
0x18002fbb3  sbb     rax, rax
0x18002fbb6  and     rax, rcx
0x18002fbb9  jmp     short loc_18002FBD6
0x18002fbbb  test    r8d, r8d
0x18002fbbe  setnz   bl
0x18002fbc1  xor     edx, edx; hFile
0x18002fbc3  mov     r8d, ebx; dwFlags
0x18002fbc6  call    cs:__imp_LoadLibraryExW
0x18002fbcd  nop     dword ptr [rax+rax+00h]
0x18002fbd2  jmp     short loc_18002FBD6
0x18002fbd4  xor     eax, eax
0x18002fbd6  mov     rbx, [rsp+48h+arg_0]
0x18002fbdb  mov     rsi, [rsp+48h+arg_8]
0x18002fbe0  add     rsp, 40h
0x18002fbe4  pop     rdi
0x18002fbe5  retn
```
