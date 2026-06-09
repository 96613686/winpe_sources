# CopyEmbeddedFontDataToFile

- ea: `0x180021ed4`
- end: `0x180021f8a`
- name: `CopyEmbeddedFontDataToFile`
- size: `182`
- prototype: `__int64 __fastcall(LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, LPCSTR lpFileName)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001a1a4`
- `0x180022de8`
- `0x180022fcc`

## callees

- `0x180021ed4`

## import_xrefs

- `KERNEL32!CreateFileA` at `0x180021f1d`
- `KERNEL32!CreateFileA` at `0x180021f1d`
- `KERNEL32!CloseHandle` at `0x180021f5c`
- `KERNEL32!CloseHandle` at `0x180021f6d`
- `KERNEL32!CloseHandle` at `0x180021f5c`
- `KERNEL32!CloseHandle` at `0x180021f6d`
- `KERNEL32!WriteFile` at `0x180021f46`
- `KERNEL32!WriteFile` at `0x180021f46`
- `KERNEL32!DeleteFileA` at `0x180021f76`
- `KERNEL32!DeleteFileA` at `0x180021f76`

## pseudocode

```c
__int64 __fastcall CopyEmbeddedFontDataToFile(LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, LPCSTR lpFileName, int a4)
{
  HANDLE FileA; // rax
  void *v8; // rbx
  DWORD NumberOfBytesWritten; // [rsp+88h] [rbp+20h] BYREF

  NumberOfBytesWritten = 0;
  FileA = CreateFileA(lpFileName, 0xC0000000, 1u, 0, 2u, a4 != 0 ? 2 : 128, 0);
  v8 = FileA;
  if ( FileA != (HANDLE)-1LL )
  {
    if ( WriteFile(FileA, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0)
      && NumberOfBytesWritten == nNumberOfBytesToWrite )
    {
      if ( CloseHandle(v8) )
        return 0;
    }
    else
    {
      CloseHandle(v8);
    }
    DeleteFileA(lpFileName);
  }
  return 515;
}

```

## disassembly

```asm
0x180021ed4  mov     rax, rsp
0x180021ed7  push    rbx
0x180021ed8  push    rbp
0x180021ed9  push    rsi
0x180021eda  push    rdi
0x180021edb  sub     rsp, 48h
0x180021edf  mov     dword ptr [rax+20h], 0
0x180021ee6  neg     r9d
0x180021ee9  mov     rdi, r8
0x180021eec  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180021ef5  sbb     eax, eax
0x180021ef7  mov     esi, edx
0x180021ef9  xor     r9d, r9d; lpSecurityAttributes
0x180021efc  and     eax, 0FFFFFF82h
0x180021eff  sub     eax, 0FFFFFF80h
0x180021f02  mov     rbp, rcx
0x180021f05  mov     [rsp+68h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180021f09  mov     edx, 0C0000000h; dwDesiredAccess
0x180021f0e  mov     rcx, rdi; lpFileName
0x180021f11  mov     [rsp+68h+dwCreationDisposition], 2; dwCreationDisposition
0x180021f19  lea     r8d, [r9+1]; dwShareMode
0x180021f1d  call    cs:__imp_CreateFileA
0x180021f23  mov     rbx, rax
0x180021f26  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180021f2a  jz      short loc_180021F7C
0x180021f2c  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180021f34  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOverlapped
0x180021f3d  mov     r8d, esi; nNumberOfBytesToWrite
0x180021f40  mov     rdx, rbp; lpBuffer
0x180021f43  mov     rcx, rax; hFile
0x180021f46  call    cs:__imp_WriteFile
0x180021f4c  test    eax, eax
0x180021f4e  jz      short loc_180021F6A
0x180021f50  cmp     [rsp+68h+NumberOfBytesWritten], esi
0x180021f57  jnz     short loc_180021F6A
0x180021f59  mov     rcx, rbx; hObject
0x180021f5c  call    cs:__imp_CloseHandle
0x180021f62  test    eax, eax
0x180021f64  jz      short loc_180021F73
0x180021f66  xor     eax, eax
0x180021f68  jmp     short loc_180021F81
0x180021f6a  mov     rcx, rbx; hObject
0x180021f6d  call    cs:__imp_CloseHandle
0x180021f73  mov     rcx, rdi; lpFileName
0x180021f76  call    cs:__imp_DeleteFileA
0x180021f7c  mov     eax, 203h
0x180021f81  add     rsp, 48h
0x180021f85  pop     rdi
0x180021f86  pop     rsi
0x180021f87  pop     rbp
0x180021f88  pop     rbx
0x180021f89  retn
```
