# PfPreHistoryRead

- ea: `0x180039c90`
- end: `0x180039e13`
- name: `PfPreHistoryRead`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180038a10`

## callees

- `0x180039c90`
- `0x180039f94`
- `0x18003a020`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039d1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039d28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039d5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039d86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039d1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039d28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039d5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039d86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039dda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039de3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039dda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039de3`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180039d78`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180039d78`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180039d4d`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180039d4d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180039d0c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180039d0c`

## pseudocode

```c
__int64 __fastcall PfPreHistoryRead(int a1, _QWORD *a2)
{
  HANDLE FileW; // rsi
  DWORD v4; // ebx
  DWORD LastError; // ebp
  HANDLE FileMappingW; // rax
  void *v7; // rdi
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  wchar_t pszDest[264]; // [rsp+40h] [rbp-238h] BYREF

  StringCbPrintfW(pszDest, 0x208u, L"%ws\\PfPre_%08lx.mkd", *(_QWORD *)&PfSvcGlobals + 888LL, a1);
  FileW = CreateFileW(pszDest, 0xC0000000, 0, 0, 4u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    return GetLastError();
  }
  else
  {
    LastError = GetLastError();
    FileMappingW = CreateFileMappingW(FileW, 0, 4u, 0, 0x3000Cu, 0);
    v7 = FileMappingW;
    if ( FileMappingW == (HANDLE)-1LL )
    {
      v4 = GetLastError();
    }
    else
    {
      v8 = MapViewOfFile(FileMappingW, 2u, 0, 0, 0x3000Cu);
      v9 = v8;
      if ( v8 )
      {
        if ( LastError != 183 )
        {
          memset_0(v8 + 1, 0, 0x30008u);
          *v9 = 5;
        }
        if ( (unsigned int)PfPreHistoryFileVerify(v9) )
        {
          memset_0(v9 + 1, 0, 0x30008u);
          *v9 = 5;
        }
        *a2 = v9;
        v4 = 0;
      }
      else
      {
        v4 = GetLastError();
      }
      CloseHandle(v7);
    }
    CloseHandle(FileW);
  }
  return v4;
}

```

## disassembly

```asm
0x180039c90  mov     [rsp+arg_10], rbx
0x180039c95  mov     [rsp+arg_18], rbp
0x180039c9a  push    rsi
0x180039c9b  push    rdi
0x180039c9c  push    r14
0x180039c9e  sub     rsp, 260h
0x180039ca5  mov     rax, cs:__security_cookie
0x180039cac  xor     rax, rsp
0x180039caf  mov     [rsp+278h+var_28], rax
0x180039cb7  mov     r9, cs:PfSvcGlobals
0x180039cbe  lea     r8, aWsPfpre08lxMkd; "%ws\\PfPre_%08lx.mkd"
0x180039cc5  mov     r14, rdx
0x180039cc8  mov     [rsp+278h+dwCreationDisposition], ecx
0x180039ccc  add     r9, 378h
0x180039cd3  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180039cd8  mov     edx, 208h; cbDest
0x180039cdd  call    StringCbPrintfW
0x180039ce2  mov     [rsp+278h+hTemplateFile], 0; hTemplateFile
0x180039ceb  lea     rcx, [rsp+278h+pszDest]; lpFileName
0x180039cf0  mov     edi, 4
0x180039cf5  mov     [rsp+278h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180039cfd  xor     r9d, r9d; lpSecurityAttributes
0x180039d00  mov     [rsp+278h+dwCreationDisposition], edi; dwCreationDisposition
0x180039d04  xor     r8d, r8d; dwShareMode
0x180039d07  mov     edx, 0C0000000h; dwDesiredAccess
0x180039d0c  call    cs:__imp_CreateFileW
0x180039d12  mov     rsi, rax
0x180039d15  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180039d19  jnz     short loc_180039D28
0x180039d1b  call    cs:__imp_GetLastError
0x180039d21  mov     ebx, eax
0x180039d23  jmp     loc_180039DE9
0x180039d28  call    cs:__imp_GetLastError
0x180039d2e  mov     ebx, 3000Ch
0x180039d33  mov     qword ptr [rsp+278h+dwFlagsAndAttributes], 0; lpName
0x180039d3c  xor     r9d, r9d; dwMaximumSizeHigh
0x180039d3f  mov     [rsp+278h+dwCreationDisposition], ebx; dwMaximumSizeLow
0x180039d43  mov     r8d, edi; flProtect
0x180039d46  xor     edx, edx; lpFileMappingAttributes
0x180039d48  mov     rcx, rsi; hFile
0x180039d4b  mov     ebp, eax
0x180039d4d  call    cs:__imp_CreateFileMappingW
0x180039d53  mov     rdi, rax
0x180039d56  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180039d5a  jnz     short loc_180039D66
0x180039d5c  call    cs:__imp_GetLastError
0x180039d62  mov     ebx, eax
0x180039d64  jmp     short loc_180039DE0
0x180039d66  xor     r9d, r9d; dwFileOffsetLow
0x180039d69  mov     qword ptr [rsp+278h+dwCreationDisposition], rbx; dwNumberOfBytesToMap
0x180039d6e  xor     r8d, r8d; dwFileOffsetHigh
0x180039d71  mov     rcx, rdi; hFileMappingObject
0x180039d74  lea     edx, [r9+2]; dwDesiredAccess
0x180039d78  call    cs:__imp_MapViewOfFile
0x180039d7e  mov     rbx, rax
0x180039d81  test    rax, rax
0x180039d84  jnz     short loc_180039D90
0x180039d86  call    cs:__imp_GetLastError
0x180039d8c  mov     ebx, eax
0x180039d8e  jmp     short loc_180039DD7
0x180039d90  cmp     ebp, 0B7h
0x180039d96  jz      short loc_180039DAF
0x180039d98  lea     rcx, [rax+4]; void *
0x180039d9c  xor     edx, edx; Val
0x180039d9e  mov     r8d, 30008h; Size
0x180039da4  call    memset_0
0x180039da9  mov     dword ptr [rbx], 5
0x180039daf  mov     rcx, rbx
0x180039db2  call    PfPreHistoryFileVerify
0x180039db7  test    eax, eax
0x180039db9  jz      short loc_180039DD2
0x180039dbb  lea     rcx, [rbx+4]; void *
0x180039dbf  xor     edx, edx; Val
0x180039dc1  mov     r8d, 30008h; Size
0x180039dc7  call    memset_0
0x180039dcc  mov     dword ptr [rbx], 5
0x180039dd2  mov     [r14], rbx
0x180039dd5  xor     ebx, ebx
0x180039dd7  mov     rcx, rdi; hObject
0x180039dda  call    cs:__imp_CloseHandle
0x180039de0  mov     rcx, rsi; hObject
0x180039de3  call    cs:__imp_CloseHandle
0x180039de9  mov     eax, ebx
0x180039deb  mov     rcx, [rsp+278h+var_28]
0x180039df3  xor     rcx, rsp; StackCookie
0x180039df6  call    __security_check_cookie
0x180039dfb  lea     r11, [rsp+278h+var_18]
0x180039e03  mov     rbx, [r11+30h]
0x180039e07  mov     rbp, [r11+38h]
0x180039e0b  mov     rsp, r11
0x180039e0e  pop     r14
0x180039e10  pop     rdi
0x180039e11  pop     rsi
0x180039e12  retn
```
