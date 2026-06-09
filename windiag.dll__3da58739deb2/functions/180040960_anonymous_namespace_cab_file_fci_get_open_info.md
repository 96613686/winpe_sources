# _anonymous_namespace_::cab_file::fci_get_open_info

- ea: `0x180040960`
- end: `0x180040a86`
- name: `_anonymous_namespace_::cab_file::fci_get_open_info`
- size: `294`
- prototype: `INT_PTR __cdecl(LPSTR pszName, USHORT *pdate, USHORT *ptime, USHORT *pattribs, int *err, void *pv)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180004510`
- `0x180040960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800409c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040a47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040a5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800409c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040a47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040a5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040a52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040a52`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800409b6`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800409b6`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180040a03`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180040a03`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180040a17`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180040a17`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x180040a2c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x180040a2c`

## pseudocode

```c
INT_PTR __fastcall anonymous_namespace_::cab_file::fci_get_open_info(
        const CHAR *pszName,
        USHORT *pdate,
        USHORT *ptime,
        USHORT *pattribs,
        int *err)
{
  HANDLE FileA; // rbx
  struct _FILETIME LocalFileTime; // [rsp+40h] [rbp-78h] BYREF
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+48h] [rbp-70h] BYREF

  FileA = CreateFileA(pszName, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  if ( FileA == (HANDLE)-1LL )
  {
    *err = GetLastError();
  }
  else
  {
    LocalFileTime = 0;
    memset(&FileInformation, 0, sizeof(FileInformation));
    if ( GetFileInformationByHandle(FileA, &FileInformation)
      && FileTimeToLocalFileTime(&FileInformation.ftCreationTime, &LocalFileTime)
      && FileTimeToDosDateTime(&LocalFileTime, pdate, ptime) )
    {
      *pattribs = FileInformation.dwFileAttributes & 0x27;
      return (INT_PTR)FileA;
    }
    *err = GetLastError();
    if ( !CloseHandle(FileA) )
      *err = GetLastError();
  }
  return -1;
}

```

## disassembly

```asm
0x180040960  push    rbx
0x180040962  push    rbp
0x180040963  push    rsi
0x180040964  push    rdi
0x180040965  push    r14
0x180040967  sub     rsp, 90h
0x18004096e  mov     rax, cs:__security_cookie
0x180040975  xor     rax, rsp
0x180040978  mov     [rsp+0B8h+var_38], rax
0x180040980  mov     rdi, [rsp+0B8h+err]
0x180040988  mov     rsi, r9
0x18004098b  xor     r9d, r9d; lpSecurityAttributes
0x18004098e  mov     [rsp+0B8h+hTemplateFile], 0; hTemplateFile
0x180040997  mov     r14, r8
0x18004099a  mov     [rsp+0B8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800409a2  mov     rbp, rdx
0x1800409a5  mov     [rsp+0B8h+dwCreationDisposition], 3; dwCreationDisposition
0x1800409ad  mov     edx, 80000000h; dwDesiredAccess
0x1800409b2  lea     r8d, [r9+7]; dwShareMode
0x1800409b6  call    cs:__imp_CreateFileA
0x1800409bc  mov     rbx, rax
0x1800409bf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800409c3  jnz     short loc_1800409D0
0x1800409c5  call    cs:__imp_GetLastError
0x1800409cb  mov     [rdi], eax
0x1800409cd  or      rbx, rbx
0x1800409d0  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800409d4  jz      loc_180040A64
0x1800409da  xorps   xmm0, xmm0
0x1800409dd  mov     qword ptr [rsp+0B8h+LocalFileTime.dwLowDateTime], 0
0x1800409e6  xor     eax, eax
0x1800409e8  lea     rdx, [rsp+0B8h+FileInformation]; lpFileInformation
0x1800409ed  mov     rcx, rbx; hFile
0x1800409f0  mov     [rsp+0B8h+FileInformation.nFileIndexLow], eax
0x1800409f4  movups  xmmword ptr [rsp+0B8h+FileInformation.dwFileAttributes], xmm0
0x1800409f9  movups  xmmword ptr [rsp+0B8h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1800409fe  movups  xmmword ptr [rsp+0B8h+FileInformation.nFileSizeHigh], xmm0
0x180040a03  call    cs:__imp_GetFileInformationByHandle
0x180040a09  test    eax, eax
0x180040a0b  jz      short loc_180040A47
0x180040a0d  lea     rdx, [rsp+0B8h+LocalFileTime]; lpLocalFileTime
0x180040a12  lea     rcx, [rsp+0B8h+FileInformation.ftCreationTime]; lpFileTime
0x180040a17  call    cs:__imp_FileTimeToLocalFileTime
0x180040a1d  test    eax, eax
0x180040a1f  jz      short loc_180040A47
0x180040a21  mov     r8, r14; lpFatTime
0x180040a24  lea     rcx, [rsp+0B8h+LocalFileTime]; lpFileTime
0x180040a29  mov     rdx, rbp; lpFatDate
0x180040a2c  call    cs:__imp_FileTimeToDosDateTime
0x180040a32  test    eax, eax
0x180040a34  jz      short loc_180040A47
0x180040a36  movzx   eax, word ptr [rsp+0B8h+FileInformation.dwFileAttributes]
0x180040a3b  and     ax, 27h
0x180040a3f  mov     [rsi], ax
0x180040a42  mov     rax, rbx
0x180040a45  jmp     short loc_180040A68
0x180040a47  call    cs:__imp_GetLastError
0x180040a4d  mov     rcx, rbx; hObject
0x180040a50  mov     [rdi], eax
0x180040a52  call    cs:__imp_CloseHandle
0x180040a58  test    eax, eax
0x180040a5a  jnz     short loc_180040A64
0x180040a5c  call    cs:__imp_GetLastError
0x180040a62  mov     [rdi], eax
0x180040a64  or      rax, 0FFFFFFFFFFFFFFFFh
0x180040a68  mov     rcx, [rsp+0B8h+var_38]
0x180040a70  xor     rcx, rsp; StackCookie
0x180040a73  call    __security_check_cookie
0x180040a78  add     rsp, 90h
0x180040a7f  pop     r14
0x180040a81  pop     rdi
0x180040a82  pop     rsi
0x180040a83  pop     rbp
0x180040a84  pop     rbx
0x180040a85  retn
```
