# CWiaLog::WriteStringToLog(ushort *,int)

- ea: `0x180074db0`
- end: `0x180074eed`
- name: `?WriteStringToLog@CWiaLog@@AEAAXPEAGH@Z`
- size: `317`
- prototype: `void(CWiaLog *__hidden this, unsigned __int16 *, int)`
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180073da0`
- `0x180074230`
- `0x180074758`
- `0x180074b80`
- `0x180074c0c`
- `0x180074c84`
- `0x180074f00`
- `0x180075020`

## callees

- `0x180033cc0`
- `0x180074db0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180074e82`
- `KERNEL32!WriteFile` at `0x180074ea7`
- `KERNEL32!WriteFile` at `0x180074e82`
- `KERNEL32!WriteFile` at `0x180074ea7`
- `KERNEL32!lstrlenW` at `0x180074e5f`
- `KERNEL32!lstrlenW` at `0x180074e5f`
- `KERNEL32!OutputDebugStringW` at `0x180074eb9`
- `KERNEL32!OutputDebugStringW` at `0x180074ec6`
- `KERNEL32!OutputDebugStringW` at `0x180074eb9`
- `KERNEL32!OutputDebugStringW` at `0x180074ec6`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180074e1b`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180074e1b`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180074dfe`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180074dfe`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180074e56`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180074e56`

## pseudocode

```c
void __fastcall CWiaLog::WriteStringToLog(CWiaLog *this, unsigned __int16 *a2)
{
  void *v4; // rcx
  DWORD v5; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-168h] BYREF
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+48h] [rbp-160h] BYREF
  CHAR MultiByteStr[272]; // [rsp+80h] [rbp-128h] BYREF

  NumberOfBytesWritten = 0;
  v4 = (void *)*((_QWORD *)this + 5);
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( GetFileInformationByHandle(v4, &FileInformation) )
  {
    SetFilePointer(*((HANDLE *)this + 5), 0, 0, 2u);
    WideCharToMultiByte(0, 0x400u, a2, -1, MultiByteStr, 260, 0, 0);
    v5 = lstrlenW(a2);
    WriteFile(*((HANDLE *)this + 5), MultiByteStr, v5, &NumberOfBytesWritten, 0);
    WriteFile(*((HANDLE *)this + 5), "\r\n", 2u, &NumberOfBytesWritten, 0);
    if ( *((_DWORD *)this + 177) )
    {
      OutputDebugStringW(a2);
      OutputDebugStringW(L"\n");
    }
  }
}

```

## disassembly

```asm
0x180074db0  mov     [rsp+arg_10], rbx
0x180074db5  push    rdi
0x180074db6  sub     rsp, 1A0h
0x180074dbd  mov     rax, cs:__security_cookie
0x180074dc4  xor     rax, rsp
0x180074dc7  mov     [rsp+1A8h+var_18], rax
0x180074dcf  xorps   xmm0, xmm0
0x180074dd2  mov     [rsp+1A8h+NumberOfBytesWritten], 0
0x180074dda  mov     rbx, rdx
0x180074ddd  mov     rdi, rcx
0x180074de0  mov     rcx, [rcx+28h]; hFile
0x180074de4  lea     rdx, [rsp+1A8h+FileInformation]; lpFileInformation
0x180074de9  xor     eax, eax
0x180074deb  movups  xmmword ptr [rsp+1A8h+FileInformation.dwFileAttributes], xmm0
0x180074df0  mov     [rsp+1A8h+FileInformation.nFileIndexLow], eax
0x180074df4  movups  xmmword ptr [rsp+1A8h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180074df9  movups  xmmword ptr [rsp+1A8h+FileInformation.nFileSizeHigh], xmm0
0x180074dfe  call    cs:__imp_GetFileInformationByHandle
0x180074e04  test    eax, eax
0x180074e06  jz      loc_180074ECC
0x180074e0c  mov     rcx, [rdi+28h]; hFile
0x180074e10  mov     r9d, 2; dwMoveMethod
0x180074e16  xor     r8d, r8d; lpDistanceToMoveHigh
0x180074e19  xor     edx, edx; lDistanceToMove
0x180074e1b  call    cs:__imp_SetFilePointer
0x180074e21  mov     [rsp+1A8h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180074e2a  lea     rax, [rsp+1A8h+MultiByteStr]
0x180074e32  mov     [rsp+1A8h+lpDefaultChar], 0; lpDefaultChar
0x180074e3b  or      r9d, 0FFFFFFFFh; cchWideChar
0x180074e3f  mov     [rsp+1A8h+cbMultiByte], 104h; cbMultiByte
0x180074e47  mov     r8, rbx; lpWideCharStr
0x180074e4a  mov     edx, 400h; dwFlags
0x180074e4f  mov     [rsp+1A8h+lpMultiByteStr], rax; lpMultiByteStr
0x180074e54  xor     ecx, ecx; CodePage
0x180074e56  call    cs:__imp_WideCharToMultiByte
0x180074e5c  mov     rcx, rbx; lpString
0x180074e5f  call    cs:__imp_lstrlenW
0x180074e65  mov     rcx, [rdi+28h]; hFile
0x180074e69  lea     r9, [rsp+1A8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180074e6e  mov     r8d, eax; nNumberOfBytesToWrite
0x180074e71  mov     [rsp+1A8h+lpMultiByteStr], 0; lpOverlapped
0x180074e7a  lea     rdx, [rsp+1A8h+MultiByteStr]; lpBuffer
0x180074e82  call    cs:__imp_WriteFile
0x180074e88  mov     rcx, [rdi+28h]; hFile
0x180074e8c  lea     r9, [rsp+1A8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180074e91  mov     r8d, 2; nNumberOfBytesToWrite
0x180074e97  mov     [rsp+1A8h+lpMultiByteStr], 0; lpOverlapped
0x180074ea0  lea     rdx, asc_1800A13C0; "\r\n"
0x180074ea7  call    cs:__imp_WriteFile
0x180074ead  cmp     dword ptr [rdi+2C4h], 0
0x180074eb4  jz      short loc_180074ECC
0x180074eb6  mov     rcx, rbx; lpOutputString
0x180074eb9  call    cs:__imp_OutputDebugStringW
0x180074ebf  lea     rcx, OutputString; "\n"
0x180074ec6  call    cs:__imp_OutputDebugStringW
0x180074ecc  mov     rcx, [rsp+1A8h+var_18]
0x180074ed4  xor     rcx, rsp; StackCookie
0x180074ed7  call    __security_check_cookie
0x180074edc  mov     rbx, [rsp+1A8h+arg_10]
0x180074ee4  add     rsp, 1A0h
0x180074eeb  pop     rdi
0x180074eec  retn
```
