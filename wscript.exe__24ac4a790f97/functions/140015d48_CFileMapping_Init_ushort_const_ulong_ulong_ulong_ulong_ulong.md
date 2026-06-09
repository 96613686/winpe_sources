# CFileMapping::Init(ushort const *,ulong,ulong,ulong,ulong,ulong)

- ea: `0x140015d48`
- end: `0x140015f11`
- name: `?Init@CFileMapping@@QEAAJPEBGKKKKK@Z`
- size: `457`
- prototype: `int(CFileMapping *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14000757c`

## callees

- `0x140015d48`
- `0x1400175a0`
- `0x1400175d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140015e95`
- `KERNEL32!GetLastError` at `0x140015e95`
- `KERNEL32!WideCharToMultiByte` at `0x140015dd4`
- `KERNEL32!WideCharToMultiByte` at `0x140015e41`
- `KERNEL32!WideCharToMultiByte` at `0x140015dd4`
- `KERNEL32!WideCharToMultiByte` at `0x140015e41`
- `KERNEL32!CreateFileA` at `0x140015e73`
- `KERNEL32!CreateFileA` at `0x140015e73`
- `KERNEL32!CreateFileW` at `0x140015d9b`
- `KERNEL32!CreateFileW` at `0x140015d9b`
- `KERNEL32!CreateFileMappingA` at `0x140015ec6`
- `KERNEL32!CreateFileMappingA` at `0x140015ec6`
- `KERNEL32!GetFileSize` at `0x140015e87`
- `KERNEL32!GetFileSize` at `0x140015e87`
- `KERNEL32!MapViewOfFile` at `0x140015eeb`
- `KERNEL32!MapViewOfFile` at `0x140015eeb`

## pseudocode

```c
int __fastcall CFileMapping::Init(CFileMapping *this, const unsigned __int16 *a2)
{
  HANDLE FileW; // rax
  int v5; // eax
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // rcx
  void *v8; // rsp
  void *v9; // rsp
  int result; // eax
  DWORD FileSize; // eax
  HANDLE FileMappingA; // rax
  LPVOID v13; // rax
  CHAR MultiByteStr[48]; // [rsp+40h] [rbp+0h] BYREF

  if ( Global::g_fWindowsNT )
  {
    FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
  }
  else
  {
    v5 = WideCharToMultiByte(0, 0, a2, -1, 0, 0, 0, 0);
    if ( !v5 )
      goto LABEL_12;
    v6 = v5 + 15LL;
    if ( v6 < v5 )
      v6 = 0xFFFFFFFFFFFFFF0LL;
    v7 = v6 & 0xFFFFFFFFFFFFFFF0uLL;
    v8 = alloca(v7);
    v9 = alloca(v7);
    if ( !MultiByteStr )
      return -2147024882;
    if ( !WideCharToMultiByte(0, 0, a2, -1, MultiByteStr, v5, 0, 0) )
      goto LABEL_12;
    FileW = CreateFileA(MultiByteStr, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
  }
  if ( FileW != (HANDLE)-1LL )
  {
    *(_QWORD *)this = FileW;
    FileSize = GetFileSize(FileW, 0);
    *((_DWORD *)this + 6) = FileSize;
    if ( FileSize != -1 )
    {
      if ( !FileSize )
        return 0;
      FileMappingA = CreateFileMappingA(*(HANDLE *)this, 0, 2u, 0, FileSize, 0);
      *((_QWORD *)this + 1) = FileMappingA;
      if ( FileMappingA )
      {
        v13 = MapViewOfFile(FileMappingA, 4u, 0, 0, 0);
        *((_QWORD *)this + 2) = v13;
        if ( v13 )
          return 0;
      }
    }
  }
LABEL_12:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140015d48  push    rbp
0x140015d4a  push    rbx
0x140015d4b  push    rsi
0x140015d4c  push    rdi
0x140015d4d  sub     rsp, 58h
0x140015d51  lea     rbp, [rsp+40h]
0x140015d56  mov     rax, cs:__security_cookie
0x140015d5d  xor     rax, rbp
0x140015d60  mov     qword ptr [rbp+30h+MultiByteStr], rax
0x140015d64  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x140015d6b  mov     rsi, rdx
0x140015d6e  mov     rbx, rcx
0x140015d71  jz      short loc_140015DA6
0x140015d73  xor     r9d, r9d; lpSecurityAttributes
0x140015d76  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x140015d7f  mov     [rsp+70h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x140015d87  mov     edx, 80000000h; dwDesiredAccess
0x140015d8c  mov     rcx, rsi; lpFileName
0x140015d8f  mov     [rsp+70h+dwCreationDisposition], 3; dwCreationDisposition
0x140015d97  lea     r8d, [r9+1]; dwShareMode
0x140015d9b  call    cs:__imp_CreateFileW
0x140015da1  jmp     loc_140015E79
0x140015da6  mov     [rsp+70h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x140015daf  or      r9d, 0FFFFFFFFh; cchWideChar
0x140015db3  mov     [rsp+70h+hTemplateFile], 0; lpDefaultChar
0x140015dbc  mov     r8, rsi; lpWideCharStr
0x140015dbf  mov     [rsp+70h+dwFlagsAndAttributes], 0; cbMultiByte
0x140015dc7  xor     edx, edx; dwFlags
0x140015dc9  xor     ecx, ecx; CodePage
0x140015dcb  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpMultiByteStr
0x140015dd4  call    cs:__imp_WideCharToMultiByte
0x140015dda  movsxd  rdx, eax
0x140015ddd  test    eax, eax
0x140015ddf  jz      loc_140015E95
0x140015de5  lea     rcx, [rdx+0Fh]
0x140015de9  cmp     rcx, rdx
0x140015dec  ja      short loc_140015DF8
0x140015dee  mov     rcx, 0FFFFFFFFFFFFFF0h
0x140015df8  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140015dfc  mov     rax, rcx
0x140015dff  call    _alloca_probe
0x140015e04  sub     rsp, rcx
0x140015e07  lea     rdi, [rsp+70h+MultiByteStr]
0x140015e0c  test    rdi, rdi
0x140015e0f  jnz     short loc_140015E1B
0x140015e11  mov     eax, 8007000Eh
0x140015e16  jmp     loc_140015EFC
0x140015e1b  mov     [rsp+70h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x140015e24  or      r9d, 0FFFFFFFFh; cchWideChar
0x140015e28  mov     [rsp+70h+hTemplateFile], 0; lpDefaultChar
0x140015e31  mov     r8, rsi; lpWideCharStr
0x140015e34  mov     [rsp+70h+dwFlagsAndAttributes], edx; cbMultiByte
0x140015e38  xor     ecx, ecx; CodePage
0x140015e3a  xor     edx, edx; dwFlags
0x140015e3c  mov     qword ptr [rsp+70h+dwCreationDisposition], rdi; lpMultiByteStr
0x140015e41  call    cs:__imp_WideCharToMultiByte
0x140015e47  test    eax, eax
0x140015e49  jz      short loc_140015E95
0x140015e4b  xor     r9d, r9d; lpSecurityAttributes
0x140015e4e  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x140015e57  mov     [rsp+70h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x140015e5f  mov     edx, 80000000h; dwDesiredAccess
0x140015e64  mov     rcx, rdi; lpFileName
0x140015e67  mov     [rsp+70h+dwCreationDisposition], 3; dwCreationDisposition
0x140015e6f  lea     r8d, [r9+1]; dwShareMode
0x140015e73  call    cs:__imp_CreateFileA
0x140015e79  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140015e7d  jz      short loc_140015E95
0x140015e7f  xor     edx, edx; lpFileSizeHigh
0x140015e81  mov     [rbx], rax
0x140015e84  mov     rcx, rax; hFile
0x140015e87  call    cs:__imp_GetFileSize
0x140015e8d  mov     [rbx+18h], eax
0x140015e90  cmp     eax, 0FFFFFFFFh
0x140015e93  jnz     short loc_140015EA9
0x140015e95  call    cs:__imp_GetLastError
0x140015e9b  test    eax, eax
0x140015e9d  jle     short loc_140015EFC
0x140015e9f  movzx   eax, ax
0x140015ea2  or      eax, 80070000h
0x140015ea7  jmp     short loc_140015EFC
0x140015ea9  test    eax, eax
0x140015eab  jz      short loc_140015EFA
0x140015ead  mov     rcx, [rbx]; hFile
0x140015eb0  xor     r9d, r9d; dwMaximumSizeHigh
0x140015eb3  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], 0; lpName
0x140015ebc  xor     edx, edx; lpFileMappingAttributes
0x140015ebe  mov     [rsp+70h+dwCreationDisposition], eax; dwMaximumSizeLow
0x140015ec2  lea     r8d, [r9+2]; flProtect
0x140015ec6  call    cs:__imp_CreateFileMappingA
0x140015ecc  mov     [rbx+8], rax
0x140015ed0  test    rax, rax
0x140015ed3  jz      short loc_140015E95
0x140015ed5  xor     r9d, r9d; dwFileOffsetLow
0x140015ed8  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x140015ee1  xor     r8d, r8d; dwFileOffsetHigh
0x140015ee4  mov     rcx, rax; hFileMappingObject
0x140015ee7  lea     edx, [r9+4]; dwDesiredAccess
0x140015eeb  call    cs:__imp_MapViewOfFile
0x140015ef1  mov     [rbx+10h], rax
0x140015ef5  test    rax, rax
0x140015ef8  jz      short loc_140015E95
0x140015efa  xor     eax, eax
0x140015efc  mov     rcx, qword ptr [rbp+30h+MultiByteStr]
0x140015f00  xor     rcx, rbp; StackCookie
0x140015f03  call    __security_check_cookie
0x140015f08  lea     rsp, [rbp+18h]
0x140015f0c  pop     rdi
0x140015f0d  pop     rsi
0x140015f0e  pop     rbx
0x140015f0f  pop     rbp
0x140015f10  retn
```
