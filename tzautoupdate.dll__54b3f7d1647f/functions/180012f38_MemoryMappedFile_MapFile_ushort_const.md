# MemoryMappedFile::MapFile(ushort const *)

- ea: `0x180012f38`
- end: `0x180013075`
- name: `?MapFile@MemoryMappedFile@@QEAAJPEBG@Z`
- size: `317`
- prototype: `__int64 __fastcall(union _LARGE_INTEGER *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x18001007c`

## callees

- `0x18000883c`
- `0x180012f38`
- `0x18001b0f6`
- `0x18001b150`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180012fed`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180012fed`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180012fb8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180012fb8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180012f7d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180012f7d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180013041`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180013041`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001301a`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001301a`

## string_xrefs

- `0x180012fd2`: `onecore\base\win32\winnls\tzautoupdate\memorymappedfile.cpp`

## pseudocode

```c
__int64 __fastcall MemoryMappedFile::MapFile(union _LARGE_INTEGER *this, const unsigned __int16 *a2)
{
  HANDLE FileW; // rax
  const char *v5; // r9
  __int64 v6; // rdx
  void *QuadPart; // rcx
  HANDLE FileMappingW; // rax
  union _LARGE_INTEGER FileSize; // [rsp+40h] [rbp-238h] BYREF
  WCHAR Dst[264]; // [rsp+50h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  memset_0(Dst, 0, 0x208u);
  if ( ExpandEnvironmentStringsW(a2, Dst, 0x104u) - 1 > 0x103 )
    return 2147942487LL;
  FileW = CreateFileW(Dst, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  this->QuadPart = (LONGLONG)FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v6 = 18;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v6,
             (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\memorymappedfile.cpp",
             v5);
  }
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(FileW, &FileSize) )
  {
    v6 = 21;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v6,
             (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\memorymappedfile.cpp",
             v5);
  }
  QuadPart = (void *)this->QuadPart;
  this[2] = FileSize;
  FileMappingW = CreateFileMappingW(QuadPart, 0, 2u, 0, 0, 0);
  this[1].QuadPart = (LONGLONG)FileMappingW;
  if ( FileMappingW == (HANDLE)-1LL )
  {
    v6 = 25;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v6,
             (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\memorymappedfile.cpp",
             v5);
  }
  this[3].QuadPart = (LONGLONG)MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x180012f38  mov     [rsp+arg_10], rbx
0x180012f3d  push    rdi
0x180012f3e  sub     rsp, 270h
0x180012f45  mov     rax, cs:__security_cookie
0x180012f4c  xor     rax, rsp
0x180012f4f  mov     [rsp+278h+var_18], rax
0x180012f57  mov     rbx, rdx
0x180012f5a  mov     rdi, rcx
0x180012f5d  xor     edx, edx; Val
0x180012f5f  lea     rcx, [rsp+278h+Dst]; void *
0x180012f64  mov     r8d, 208h; Size
0x180012f6a  call    memset_0
0x180012f6f  mov     r8d, 104h; nSize
0x180012f75  lea     rdx, [rsp+278h+Dst]; lpDst
0x180012f7a  mov     rcx, rbx; lpSrc
0x180012f7d  call    cs:__imp_ExpandEnvironmentStringsW
0x180012f83  dec     eax
0x180012f85  cmp     eax, 103h
0x180012f8a  ja      loc_18001304F
0x180012f90  xor     ebx, ebx
0x180012f92  lea     rcx, [rsp+278h+Dst]; lpFileName
0x180012f97  mov     [rsp+278h+hTemplateFile], rbx; hTemplateFile
0x180012f9c  xor     r9d, r9d; lpSecurityAttributes
0x180012f9f  mov     [rsp+278h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180012fa7  mov     edx, 80000000h; dwDesiredAccess
0x180012fac  mov     [rsp+278h+dwCreationDisposition], 3; dwCreationDisposition
0x180012fb4  lea     r8d, [rbx+1]; dwShareMode
0x180012fb8  call    cs:__imp_CreateFileW
0x180012fbe  mov     [rdi], rax
0x180012fc1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180012fc5  jnz     short loc_180012FE0
0x180012fc7  lea     edx, [rbx+12h]; void *
0x180012fca  mov     rcx, [rsp+278h]; this
0x180012fd2  lea     r8, aOnecoreBaseWin_0; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x180012fd9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180012fde  jmp     short loc_180013054
0x180012fe0  lea     rdx, [rsp+278h+FileSize]; lpFileSize
0x180012fe5  mov     qword ptr [rsp+278h+FileSize], rbx
0x180012fea  mov     rcx, rax; hFile
0x180012fed  call    cs:__imp_GetFileSizeEx
0x180012ff3  test    eax, eax
0x180012ff5  jnz     short loc_180012FFC
0x180012ff7  lea     edx, [rax+15h]
0x180012ffa  jmp     short loc_180012FCA
0x180012ffc  mov     rax, qword ptr [rsp+278h+FileSize]
0x180013001  xor     r9d, r9d; dwMaximumSizeHigh
0x180013004  mov     rcx, [rdi]; hFile
0x180013007  xor     edx, edx; lpFileMappingAttributes
0x180013009  mov     qword ptr [rsp+278h+dwFlagsAndAttributes], rbx; lpName
0x18001300e  mov     [rdi+10h], rax
0x180013012  lea     r8d, [r9+2]; flProtect
0x180013016  mov     [rsp+278h+dwCreationDisposition], ebx; dwMaximumSizeLow
0x18001301a  call    cs:__imp_CreateFileMappingW
0x180013020  mov     [rdi+8], rax
0x180013024  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013028  jnz     short loc_18001302F
0x18001302a  lea     edx, [rax+1Ah]
0x18001302d  jmp     short loc_180012FCA
0x18001302f  xor     r9d, r9d; dwFileOffsetLow
0x180013032  mov     qword ptr [rsp+278h+dwCreationDisposition], rbx; dwNumberOfBytesToMap
0x180013037  xor     r8d, r8d; dwFileOffsetHigh
0x18001303a  mov     rcx, rax; hFileMappingObject
0x18001303d  lea     edx, [r9+4]; dwDesiredAccess
0x180013041  call    cs:__imp_MapViewOfFile
0x180013047  mov     [rdi+18h], rax
0x18001304b  xor     eax, eax
0x18001304d  jmp     short loc_180013054
0x18001304f  mov     eax, 80070057h
0x180013054  mov     rcx, [rsp+278h+var_18]
0x18001305c  xor     rcx, rsp; StackCookie
0x18001305f  call    __security_check_cookie
0x180013064  mov     rbx, [rsp+278h+arg_10]
0x18001306c  add     rsp, 270h
0x180013073  pop     rdi
0x180013074  retn
```
