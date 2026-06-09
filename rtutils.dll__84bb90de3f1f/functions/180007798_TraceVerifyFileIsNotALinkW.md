# TraceVerifyFileIsNotALinkW

- ea: `0x180007798`
- end: `0x1800078a8`
- name: `TraceVerifyFileIsNotALinkW`
- size: `272`
- prototype: `DWORD __fastcall(HANDLE hFile, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x180006c6c`
- `0x1800074e8`

## callees

- `0x180003bb0`
- `0x180007798`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180007866`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180007866`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180007819`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180007819`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800077e3`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800077e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007879`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007879`

## pseudocode

```c
DWORD __fastcall TraceVerifyFileIsNotALinkW(HANDLE hFile, __int64 a2)
{
  __int64 v4; // rbx
  DWORD FinalPathNameByHandleW; // eax
  WCHAR *v6; // rdx
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR szFilePath[4]; // [rsp+60h] [rbp-A0h] BYREF
  char v10; // [rsp+68h] [rbp-98h] BYREF

  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( !GetFileInformationByHandle(hFile, &FileInformation)
    || (FileInformation.dwFileAttributes & 0x400) != 0
    || FileInformation.nNumberOfLinks > 1 )
  {
    return 161;
  }
  v4 = 260;
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, szFilePath, 0x104u, 0);
  if ( FinalPathNameByHandleW - 1 > 0x103 )
    return GetLastError();
  if ( FinalPathNameByHandleW >= 4
    && szFilePath[0] == 92
    && szFilePath[1] == 92
    && szFilePath[2] == 63
    && szFilePath[3] == 92 )
  {
    v4 = 256;
    v6 = (WCHAR *)&v10;
  }
  else
  {
    v6 = szFilePath;
  }
  return (unsigned int)_o__wcsnicmp(a2, v6, v4) != 0 ? 0xA1 : 0;
}

```

## disassembly

```asm
0x180007798  mov     [rsp-8+arg_10], rbx
0x18000779d  push    rbp
0x18000779e  push    rsi
0x18000779f  push    rdi
0x1800077a0  lea     rbp, [rsp-180h]
0x1800077a8  sub     rsp, 280h
0x1800077af  mov     rax, cs:__security_cookie
0x1800077b6  xor     rax, rsp
0x1800077b9  mov     [rbp+190h+var_20], rax
0x1800077c0  xorps   xmm0, xmm0
0x1800077c3  mov     rsi, rdx
0x1800077c6  xor     eax, eax
0x1800077c8  lea     rdx, [rsp+290h+FileInformation]; lpFileInformation
0x1800077cd  movups  xmmword ptr [rsp+290h+FileInformation.dwFileAttributes], xmm0
0x1800077d2  mov     [rsp+290h+FileInformation.nFileIndexLow], eax
0x1800077d6  mov     rdi, rcx
0x1800077d9  movups  xmmword ptr [rsp+290h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1800077de  movups  xmmword ptr [rsp+290h+FileInformation.nFileSizeHigh], xmm0
0x1800077e3  call    cs:__imp_GetFileInformationByHandle
0x1800077e9  test    eax, eax
0x1800077eb  jz      loc_180007881
0x1800077f1  test    [rsp+290h+FileInformation.dwFileAttributes], 400h
0x1800077f9  jnz     loc_180007881
0x1800077ff  cmp     [rsp+290h+FileInformation.nNumberOfLinks], 1
0x180007804  ja      short loc_180007881
0x180007806  mov     ebx, 104h
0x18000780b  lea     rdx, [rsp+290h+szFilePath]; lpszFilePath
0x180007810  mov     r8d, ebx; cchFilePath
0x180007813  xor     r9d, r9d; dwFlags
0x180007816  mov     rcx, rdi; hFile
0x180007819  call    cs:__imp_GetFinalPathNameByHandleW
0x18000781f  lea     ecx, [rax-1]
0x180007822  cmp     ecx, 103h
0x180007828  ja      short loc_180007879
0x18000782a  cmp     eax, 4
0x18000782d  jb      short loc_18000785B
0x18000782f  cmp     [rsp+290h+szFilePath], 5Ch ; '\'
0x180007835  jnz     short loc_18000785B
0x180007837  cmp     [rsp+290h+var_22E], 5Ch ; '\'
0x18000783d  jnz     short loc_18000785B
0x18000783f  cmp     [rsp+290h+var_22C], 3Fh ; '?'
0x180007845  jnz     short loc_18000785B
0x180007847  cmp     [rsp+290h+var_22A], 5Ch ; '\'
0x18000784d  jnz     short loc_18000785B
0x18000784f  mov     ebx, 100h
0x180007854  lea     rdx, [rsp+290h+var_228]
0x180007859  jmp     short loc_180007860
0x18000785b  lea     rdx, [rsp+290h+szFilePath]
0x180007860  mov     r8, rbx
0x180007863  mov     rcx, rsi
0x180007866  call    cs:__imp__o__wcsnicmp
0x18000786c  neg     eax
0x18000786e  mov     eax, 0A1h
0x180007873  sbb     ecx, ecx
0x180007875  and     eax, ecx
0x180007877  jmp     short loc_180007886
0x180007879  call    cs:__imp_GetLastError
0x18000787f  jmp     short loc_180007886
0x180007881  mov     eax, 0A1h
0x180007886  mov     rcx, [rbp+190h+var_20]
0x18000788d  xor     rcx, rsp; StackCookie
0x180007890  call    __security_check_cookie
0x180007895  mov     rbx, [rsp+290h+arg_10]
0x18000789d  add     rsp, 280h
0x1800078a4  pop     rdi
0x1800078a5  pop     rsi
0x1800078a6  pop     rbp
0x1800078a7  retn
```
