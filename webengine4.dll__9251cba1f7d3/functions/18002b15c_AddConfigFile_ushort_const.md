# AddConfigFile(ushort const *)

- ea: `0x18002b15c`
- end: `0x18002b1f8`
- name: `?AddConfigFile@@YAJPEBG@Z`
- size: `156`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x18002b1f8`

## callees

- `0x18002b15c`
- `0x18004d350`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18002b1d1`
- `KERNEL32!WriteFile` at `0x18002b1d1`
- `KERNEL32!CloseHandle` at `0x18002b1e5`
- `KERNEL32!CloseHandle` at `0x18002b1e5`
- `KERNEL32!lstrlenA` at `0x18002b172`
- `KERNEL32!lstrlenA` at `0x18002b172`
- `KERNEL32!CreateFileW` at `0x18002b1a0`
- `KERNEL32!CreateFileW` at `0x18002b1a0`

## string_xrefs

- `0x18002b16b`: `<configuration>\n   <startup>\n      <requiredRuntime version="v2.0.50727" />\n   </startup>\n</configuration>`
- `0x18002b1c2`: `<configuration>\n   <startup>\n      <requiredRuntime version="v2.0.50727" />\n   </startup>\n</configuration>`

## pseudocode

```c
__int64 __fastcall AddConfigFile(LPCWSTR lpFileName)
{
  unsigned int LastWin32Error; // edi
  HANDLE FileW; // rax
  void *v4; // rbx
  DWORD NumberOfBytesWritten; // [rsp+58h] [rbp+10h] BYREF

  LastWin32Error = 0;
  NumberOfBytesWritten = lstrlenA(
                           "<configuration>\r\n"
                           "   <startup>\r\n"
                           "      <requiredRuntime version=\"v2.0.50727\" />\r\n"
                           "   </startup>\r\n"
                           "</configuration>");
  FileW = CreateFileW(lpFileName, 0x40000000u, 3u, 0, 1u, 0x80u, 0);
  v4 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    return (unsigned int)GetLastWin32Error();
  }
  else
  {
    if ( !WriteFile(
            FileW,
            "<configuration>\r\n"
            "   <startup>\r\n"
            "      <requiredRuntime version=\"v2.0.50727\" />\r\n"
            "   </startup>\r\n"
            "</configuration>",
            NumberOfBytesWritten,
            &NumberOfBytesWritten,
            0) )
      LastWin32Error = GetLastWin32Error();
    CloseHandle(v4);
  }
  return LastWin32Error;
}

```

## disassembly

```asm
0x18002b15c  mov     [rsp+arg_0], rbx
0x18002b161  push    rdi
0x18002b162  sub     rsp, 40h
0x18002b166  mov     rbx, rcx
0x18002b169  xor     edi, edi
0x18002b16b  lea     rcx, Buffer; "<configuration>\r\n   <startup>\r\n    "...
0x18002b172  call    cs:__imp_lstrlenA
0x18002b178  mov     [rsp+48h+hTemplateFile], rdi; hTemplateFile
0x18002b17d  lea     r8d, [rdi+3]; dwShareMode
0x18002b181  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002b189  xor     r9d, r9d; lpSecurityAttributes
0x18002b18c  mov     edx, 40000000h; dwDesiredAccess
0x18002b191  mov     [rsp+48h+NumberOfBytesWritten], eax
0x18002b195  mov     rcx, rbx; lpFileName
0x18002b198  mov     [rsp+48h+dwCreationDisposition], 1; dwCreationDisposition
0x18002b1a0  call    cs:__imp_CreateFileW
0x18002b1a6  mov     rbx, rax
0x18002b1a9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002b1ad  jnz     short loc_18002B1B8
0x18002b1af  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18002b1b4  mov     edi, eax
0x18002b1b6  jmp     short loc_18002B1EB
0x18002b1b8  mov     r8d, [rsp+48h+NumberOfBytesWritten]; nNumberOfBytesToWrite
0x18002b1bd  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002b1c2  lea     rdx, Buffer; "<configuration>\r\n   <startup>\r\n    "...
0x18002b1c9  mov     qword ptr [rsp+48h+dwCreationDisposition], rdi; lpOverlapped
0x18002b1ce  mov     rcx, rbx; hFile
0x18002b1d1  call    cs:__imp_WriteFile
0x18002b1d7  test    eax, eax
0x18002b1d9  jnz     short loc_18002B1E2
0x18002b1db  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18002b1e0  mov     edi, eax
0x18002b1e2  mov     rcx, rbx; hObject
0x18002b1e5  call    cs:__imp_CloseHandle
0x18002b1eb  mov     rbx, [rsp+48h+arg_0]
0x18002b1f0  mov     eax, edi
0x18002b1f2  add     rsp, 40h
0x18002b1f6  pop     rdi
0x18002b1f7  retn
```
