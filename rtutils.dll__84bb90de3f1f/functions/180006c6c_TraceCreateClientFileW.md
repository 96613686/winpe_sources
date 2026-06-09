# TraceCreateClientFileW

- ea: `0x180006c6c`
- end: `0x180006e93`
- name: `TraceCreateClientFileW`
- size: `551`
- prototype: `signed int __fastcall(__int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180005450`
- `0x1800074e8`

## callees

- `0x180003bb0`
- `0x180004a2c`
- `0x180006948`
- `0x180006c6c`
- `0x180007664`
- `0x180007798`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e64`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180006e46`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180006e46`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180006cc0`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180006cc0`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180006df7`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180006df7`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180006e1a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180006e1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006db3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006db3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e50`
- `api-ms-win-core-file-l1-2-5!CreateFile3` at `0x180006daa`
- `api-ms-win-core-file-l1-2-5!CreateFile3` at `0x180006daa`

## pseudocode

```c
signed int __fastcall TraceCreateClientFileW(__int64 a1)
{
  DWORD FullPathNameW; // eax
  signed int result; // eax
  HRESULT v4; // eax
  unsigned __int16 v5; // bx
  HRESULT v6; // eax
  void *File3; // rbx
  DWORD LastError; // edi
  DWORD IsNotALinkW; // esi
  __int16 FileInformation; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-C8h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v13; // [rsp+48h] [rbp-B8h]
  __int128 v14; // [rsp+58h] [rbp-A8h]
  WCHAR Buffer[264]; // [rsp+70h] [rbp-90h] BYREF

  v13 = 0;
  v14 = 0;
  FullPathNameW = GetFullPathNameW((LPCWSTR)(a1 + 546), 0x104u, Buffer, 0);
  if ( !FullPathNameW )
    return GetLastError();
  if ( FullPathNameW >= 0x104 )
    return 161;
  result = TraceVerifyDirectoryPathW(Buffer);
  if ( !result )
  {
    result = StringCchCatW(Buffer, 0x104u, L"\\");
    if ( result >= 0 )
    {
      hObject = (HANDLE)-1LL;
      result = CreateTracingDirectoryW(Buffer, &hObject);
      if ( !result )
      {
        v4 = StringCchCatW(Buffer, 0x104u, (STRSAFE_LPCWSTR)(a1 + 128));
        v5 = v4;
        if ( v4 < 0 || (v6 = StringCchCatW(Buffer, 0x104u, L".LOG"), v5 = v6, v6 < 0) )
        {
          CloseHandle(hObject);
          return v5;
        }
        else
        {
          LODWORD(v13) = 32;
          DWORD2(v13) = 3211392;
          File3 = (void *)CreateFile3(Buffer, 3221291008LL, 1);
          LastError = GetLastError();
          if ( File3 != (void *)-1LL )
          {
            IsNotALinkW = TraceVerifyFileIsNotALinkW(File3, (__int64)Buffer);
            if ( IsNotALinkW )
            {
              if ( LastError != 183 )
              {
                LOBYTE(FileInformation) = 1;
                SetFileInformationByHandle(File3, FileDispositionInfo, &FileInformation, 1u);
              }
              CloseHandle(File3);
              LastError = IsNotALinkW;
            }
            else
            {
              SetFilePointer(File3, 0, 0, 2u);
              LastError = 0;
              NumberOfBytesWritten = 0;
              FileInformation = -257;
              if ( !WriteFile(File3, &FileInformation, 2u, &NumberOfBytesWritten, 0) )
                LastError = GetLastError();
              *(_QWORD *)(a1 + 256) = File3;
            }
          }
          CloseHandle(hObject);
          return LastError;
        }
      }
    }
    else
    {
      return (unsigned __int16)result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006c6c  mov     [rsp-8+arg_8], rbx
0x180006c71  mov     [rsp-8+arg_10], rsi
0x180006c76  push    rbp
0x180006c77  push    rdi
0x180006c78  push    r14
0x180006c7a  lea     rbp, [rsp-190h]
0x180006c82  sub     rsp, 290h
0x180006c89  mov     rax, cs:__security_cookie
0x180006c90  xor     rax, rsp
0x180006c93  mov     [rbp+1A0h+var_20], rax
0x180006c9a  xorps   xmm0, xmm0
0x180006c9d  lea     r8, [rsp+2A0h+Buffer]; lpBuffer
0x180006ca2  mov     r14, rcx
0x180006ca5  mov     edi, 104h
0x180006caa  mov     edx, edi; nBufferLength
0x180006cac  add     rcx, 222h; lpFileName
0x180006cb3  xor     r9d, r9d; lpFilePart
0x180006cb6  movups  [rsp+2A0h+var_258], xmm0
0x180006cbb  movups  [rsp+2A0h+var_248], xmm0
0x180006cc0  call    cs:__imp_GetFullPathNameW
0x180006cc6  test    eax, eax
0x180006cc8  jnz     short loc_180006CD5
0x180006cca  call    cs:__imp_GetLastError
0x180006cd0  jmp     loc_180006E6C
0x180006cd5  cmp     eax, edi
0x180006cd7  jb      short loc_180006CE3
0x180006cd9  mov     eax, 0A1h
0x180006cde  jmp     loc_180006E6C
0x180006ce3  lea     rcx, [rsp+2A0h+Buffer]; psz
0x180006ce8  call    TraceVerifyDirectoryPathW
0x180006ced  test    eax, eax
0x180006cef  jnz     loc_180006E6C
0x180006cf5  lea     r8, asc_18000C888; "\\"
0x180006cfc  mov     rdx, rdi; cchDest
0x180006cff  lea     rcx, [rsp+2A0h+Buffer]; pszDest
0x180006d04  call    StringCchCatW
0x180006d09  test    eax, eax
0x180006d0b  jns     short loc_180006D15
0x180006d0d  movzx   eax, ax
0x180006d10  jmp     loc_180006E6C
0x180006d15  lea     rdx, [rsp+2A0h+hObject]; FileHandle
0x180006d1a  mov     [rsp+2A0h+hObject], 0FFFFFFFFFFFFFFFFh
0x180006d23  lea     rcx, [rsp+2A0h+Buffer]; lpFileName
0x180006d28  call    CreateTracingDirectoryW
0x180006d2d  test    eax, eax
0x180006d2f  jnz     loc_180006E6C
0x180006d35  lea     r8, [r14+80h]; pszSrc
0x180006d3c  mov     rdx, rdi; cchDest
0x180006d3f  lea     rcx, [rsp+2A0h+Buffer]; pszDest
0x180006d44  call    StringCchCatW
0x180006d49  mov     ebx, eax
0x180006d4b  test    eax, eax
0x180006d4d  jns     short loc_180006D62
0x180006d4f  mov     rcx, [rsp+2A0h+hObject]; hObject
0x180006d54  call    cs:__imp_CloseHandle
0x180006d5a  movzx   eax, bx
0x180006d5d  jmp     loc_180006E6C
0x180006d62  lea     r8, aLog; ".LOG"
0x180006d69  mov     rdx, rdi; cchDest
0x180006d6c  lea     rcx, [rsp+2A0h+Buffer]; pszDest
0x180006d71  call    StringCchCatW
0x180006d76  mov     ebx, eax
0x180006d78  test    eax, eax
0x180006d7a  js      short loc_180006D4F
0x180006d7c  mov     r9d, 4
0x180006d82  mov     dword ptr [rsp+2A0h+var_258], 20h ; ' '
0x180006d8a  lea     rax, [rsp+2A0h+var_258]
0x180006d8f  mov     dword ptr [rsp+2A0h+var_258+8], 310080h
0x180006d97  mov     edx, 0C0010000h
0x180006d9c  mov     [rsp+2A0h+lpOverlapped], rax
0x180006da1  lea     rcx, [rsp+2A0h+Buffer]
0x180006da6  lea     r8d, [r9-3]
0x180006daa  call    cs:__imp_CreateFile3
0x180006db0  mov     rbx, rax
0x180006db3  call    cs:__imp_GetLastError
0x180006db9  mov     edi, eax
0x180006dbb  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180006dbf  jz      loc_180006E5F
0x180006dc5  lea     rdx, [rsp+2A0h+Buffer]
0x180006dca  mov     rcx, rbx; hFile
0x180006dcd  call    TraceVerifyFileIsNotALinkW
0x180006dd2  mov     esi, eax
0x180006dd4  test    eax, eax
0x180006dd6  jz      short loc_180006E0A
0x180006dd8  cmp     edi, 0B7h
0x180006dde  jz      short loc_180006DFD
0x180006de0  mov     r9d, 1; dwBufferSize
0x180006de6  mov     byte ptr [rsp+2A0h+FileInformation], 1
0x180006deb  lea     r8, [rsp+2A0h+FileInformation]; lpFileInformation
0x180006df0  mov     rcx, rbx; hFile
0x180006df3  lea     edx, [r9+3]; FileInformationClass
0x180006df7  call    cs:__imp_SetFileInformationByHandle
0x180006dfd  mov     rcx, rbx; hObject
0x180006e00  call    cs:__imp_CloseHandle
0x180006e06  mov     edi, esi
0x180006e08  jmp     short loc_180006E5F
0x180006e0a  mov     esi, 2
0x180006e0f  xor     r8d, r8d; lpDistanceToMoveHigh
0x180006e12  mov     r9d, esi; dwMoveMethod
0x180006e15  xor     edx, edx; lDistanceToMove
0x180006e17  mov     rcx, rbx; hFile
0x180006e1a  call    cs:__imp_SetFilePointer
0x180006e20  xor     edi, edi
0x180006e22  mov     [rsp+2A0h+NumberOfBytesWritten], 0
0x180006e2a  lea     r9, [rsp+2A0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180006e2f  mov     [rsp+2A0h+lpOverlapped], rdi; lpOverlapped
0x180006e34  mov     r8d, esi; nNumberOfBytesToWrite
0x180006e37  mov     [rsp+2A0h+FileInformation], 0FEFFh
0x180006e3e  lea     rdx, [rsp+2A0h+FileInformation]; lpBuffer
0x180006e43  mov     rcx, rbx; hFile
0x180006e46  call    cs:__imp_WriteFile
0x180006e4c  test    eax, eax
0x180006e4e  jnz     short loc_180006E58
0x180006e50  call    cs:__imp_GetLastError
0x180006e56  mov     edi, eax
0x180006e58  mov     [r14+100h], rbx
0x180006e5f  mov     rcx, [rsp+2A0h+hObject]; hObject
0x180006e64  call    cs:__imp_CloseHandle
0x180006e6a  mov     eax, edi
0x180006e6c  mov     rcx, [rbp+1A0h+var_20]
0x180006e73  xor     rcx, rsp; StackCookie
0x180006e76  call    __security_check_cookie
0x180006e7b  lea     r11, [rsp+2A0h+var_10]
0x180006e83  mov     rbx, [r11+28h]
0x180006e87  mov     rsi, [r11+30h]
0x180006e8b  mov     rsp, r11
0x180006e8e  pop     r14
0x180006e90  pop     rdi
0x180006e91  pop     rbp
0x180006e92  retn
```
