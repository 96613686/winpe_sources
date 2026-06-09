# EnsureTsecIni

- ea: `0x18003120c`
- end: `0x1800312e4`
- name: `EnsureTsecIni`
- size: `216`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18002d6d0`

## callees

- `0x180001600`
- `0x18001c740`
- `0x18003120c`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x18003122f`
- `KERNEL32!GetSystemDirectoryW` at `0x18003122f`
- `KERNEL32!CreateFileW` at `0x1800312ae`
- `KERNEL32!CreateFileW` at `0x1800312ae`
- `KERNEL32!CloseHandle` at `0x1800312bd`
- `KERNEL32!CloseHandle` at `0x1800312bd`

## pseudocode

```c
__int64 EnsureTsecIni()
{
  UINT SystemDirectoryW; // eax
  HANDLE FileW; // rax
  WCHAR Buffer[264]; // [rsp+40h] [rbp-228h] BYREF

  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x105u);
  if ( SystemDirectoryW - 1 > 0x103 )
    return 0;
  if ( 260 - SystemDirectoryW < 0x12 )
    return 0;
  if ( StringCbCatW(Buffer, 0x20Au, L"\\") < 0 )
    return 0;
  if ( StringCbCatW(Buffer, 0x20Au, gszFileName) < 0 )
    return 0;
  FileW = CreateFileW(Buffer, 0x80000000, 1u, 0, 4u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
    return 0;
  CloseHandle(FileW);
  return 1;
}

```

## disassembly

```asm
0x18003120c  sub     rsp, 268h
0x180031213  mov     rax, cs:__security_cookie
0x18003121a  xor     rax, rsp
0x18003121d  mov     [rsp+268h+var_18], rax
0x180031225  mov     edx, 105h; uSize
0x18003122a  lea     rcx, [rsp+268h+Buffer]; lpBuffer
0x18003122f  call    cs:__imp_GetSystemDirectoryW
0x180031235  lea     ecx, [rax-1]
0x180031238  cmp     ecx, 103h
0x18003123e  ja      loc_1800312CA
0x180031244  mov     ecx, 104h
0x180031249  sub     ecx, eax
0x18003124b  cmp     ecx, 12h
0x18003124e  jb      short loc_1800312CA
0x180031250  lea     r8, pszSrc; "\\"
0x180031257  mov     edx, 20Ah; cbDest
0x18003125c  lea     rcx, [rsp+268h+Buffer]; pszDest
0x180031261  call    StringCbCatW
0x180031266  test    eax, eax
0x180031268  js      short loc_1800312CA
0x18003126a  lea     r8, gszFileName; "..\\TAPI\\tsec.ini"
0x180031271  mov     edx, 20Ah; cbDest
0x180031276  lea     rcx, [rsp+268h+Buffer]; pszDest
0x18003127b  call    StringCbCatW
0x180031280  test    eax, eax
0x180031282  js      short loc_1800312CA
0x180031284  xor     r9d, r9d; lpSecurityAttributes
0x180031287  mov     [rsp+268h+hTemplateFile], 0; hTemplateFile
0x180031290  mov     [rsp+268h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180031298  lea     rcx, [rsp+268h+Buffer]; lpFileName
0x18003129d  mov     edx, 80000000h; dwDesiredAccess
0x1800312a2  mov     [rsp+268h+dwCreationDisposition], 4; dwCreationDisposition
0x1800312aa  lea     r8d, [r9+1]; dwShareMode
0x1800312ae  call    cs:__imp_CreateFileW
0x1800312b4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800312b8  jz      short loc_1800312CA
0x1800312ba  mov     rcx, rax; hObject
0x1800312bd  call    cs:__imp_CloseHandle
0x1800312c3  mov     eax, 1
0x1800312c8  jmp     short loc_1800312CC
0x1800312ca  xor     eax, eax
0x1800312cc  mov     rcx, [rsp+268h+var_18]
0x1800312d4  xor     rcx, rsp; StackCookie
0x1800312d7  call    __security_check_cookie
0x1800312dc  add     rsp, 268h
0x1800312e3  retn
```
