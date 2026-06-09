# tsched::VerifyJobFilePath(ushort const *,void *)

- ea: `0x18002d820`
- end: `0x18002d8e6`
- name: `?VerifyJobFilePath@tsched@@YAJPEBGPEAX@Z`
- size: `198`
- prototype: `__int64 __fastcall(wchar_t *String2, HANDLE hFile, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x180006534`

## callees

- `0x180019cf0`
- `0x18002d820`
- `0x18002e5b0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18002d88b`
- `msvcrt!_wcsnicmp` at `0x18002d88b`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18002d86e`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18002d86e`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18002d89d`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18002d89d`

## pseudocode

```c
__int64 __fastcall tsched::VerifyJobFilePath(wchar_t *String2, HANDLE hFile, void *a3)
{
  int v5; // edx
  tsched *v6; // rcx
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+20h] [rbp-268h] BYREF
  WCHAR szFilePath[264]; // [rsp+60h] [rbp-228h] BYREF

  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( GetFinalPathNameByHandleW(hFile, szFilePath, 0x105u, 0) - 1 > 0x103 )
    return tsched::GetLastHrError(v6, v5);
  if ( _wcsnicmp(szFilePath, String2, 0x105u) || !GetFileInformationByHandle(hFile, &FileInformation) )
    return 2147942561LL;
  return FileInformation.nNumberOfLinks > 1 ? 0x800700A1 : 0;
}

```

## disassembly

```asm
0x18002d820  mov     [rsp+arg_10], rbx
0x18002d825  push    rdi
0x18002d826  sub     rsp, 280h
0x18002d82d  mov     rax, cs:__security_cookie
0x18002d834  xor     rax, rsp
0x18002d837  mov     [rsp+288h+var_18], rax
0x18002d83f  xorps   xmm0, xmm0
0x18002d842  mov     rbx, rdx
0x18002d845  mov     rdi, rcx
0x18002d848  lea     rdx, [rsp+288h+szFilePath]; lpszFilePath
0x18002d84d  xor     eax, eax
0x18002d84f  mov     rcx, rbx; hFile
0x18002d852  xor     r9d, r9d; dwFlags
0x18002d855  mov     [rsp+288h+FileInformation.nFileIndexLow], eax
0x18002d859  mov     r8d, 105h; cchFilePath
0x18002d85f  movups  xmmword ptr [rsp+288h+FileInformation.dwFileAttributes], xmm0
0x18002d864  movups  xmmword ptr [rsp+288h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18002d869  movups  xmmword ptr [rsp+288h+FileInformation.nFileSizeHigh], xmm0
0x18002d86e  call    cs:__imp_GetFinalPathNameByHandleW
0x18002d874  dec     eax
0x18002d876  cmp     eax, 103h
0x18002d87b  ja      short loc_18002D8C0
0x18002d87d  mov     r8d, 105h; MaxCount
0x18002d883  lea     rcx, [rsp+288h+szFilePath]; String1
0x18002d888  mov     rdx, rdi; String2
0x18002d88b  call    cs:__imp__wcsnicmp
0x18002d891  test    eax, eax
0x18002d893  jnz     short loc_18002D8B9
0x18002d895  lea     rdx, [rsp+288h+FileInformation]; lpFileInformation
0x18002d89a  mov     rcx, rbx; hFile
0x18002d89d  call    cs:__imp_GetFileInformationByHandle
0x18002d8a3  test    eax, eax
0x18002d8a5  jz      short loc_18002D8B9
0x18002d8a7  mov     eax, 1
0x18002d8ac  cmp     eax, [rsp+288h+FileInformation.nNumberOfLinks]
0x18002d8b0  sbb     eax, eax
0x18002d8b2  and     eax, 800700A1h
0x18002d8b7  jmp     short loc_18002D8C5
0x18002d8b9  mov     eax, 800700A1h
0x18002d8be  jmp     short loc_18002D8C5
0x18002d8c0  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x18002d8c5  mov     rcx, [rsp+288h+var_18]
0x18002d8cd  xor     rcx, rsp; StackCookie
0x18002d8d0  call    __security_check_cookie
0x18002d8d5  mov     rbx, [rsp+288h+arg_10]
0x18002d8dd  add     rsp, 280h
0x18002d8e4  pop     rdi
0x18002d8e5  retn
```
