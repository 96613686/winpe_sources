# tsched::VerifyJobFilePath(ushort const *,void *)

- ea: `0x18002f86c`
- end: `0x18002f945`
- name: `?VerifyJobFilePath@tsched@@YAJPEBGPEAX@Z`
- size: `217`
- prototype: `__int64 __fastcall(wchar_t *String2, HANDLE hFile, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x18002f578`

## callees

- `0x18001afc0`
- `0x18002f86c`
- `0x180030700`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18002f8dd`
- `msvcrt!_wcsnicmp` at `0x18002f8dd`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18002f8ba`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18002f8ba`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18002f8f5`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18002f8f5`

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
0x18002f86c  mov     [rsp+arg_10], rbx
0x18002f871  push    rdi
0x18002f872  sub     rsp, 280h
0x18002f879  mov     rax, cs:__security_cookie
0x18002f880  xor     rax, rsp
0x18002f883  mov     [rsp+288h+var_18], rax
0x18002f88b  xorps   xmm0, xmm0
0x18002f88e  mov     rbx, rdx
0x18002f891  mov     rdi, rcx
0x18002f894  lea     rdx, [rsp+288h+szFilePath]; lpszFilePath
0x18002f899  xor     eax, eax
0x18002f89b  mov     rcx, rbx; hFile
0x18002f89e  xor     r9d, r9d; dwFlags
0x18002f8a1  mov     [rsp+288h+FileInformation.nFileIndexLow], eax
0x18002f8a5  mov     r8d, 105h; cchFilePath
0x18002f8ab  movups  xmmword ptr [rsp+288h+FileInformation.dwFileAttributes], xmm0
0x18002f8b0  movups  xmmword ptr [rsp+288h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18002f8b5  movups  xmmword ptr [rsp+288h+FileInformation.nFileSizeHigh], xmm0
0x18002f8ba  call    cs:__imp_GetFinalPathNameByHandleW
0x18002f8c1  nop     dword ptr [rax+rax+00h]
0x18002f8c6  dec     eax
0x18002f8c8  cmp     eax, 103h
0x18002f8cd  ja      short loc_18002F91E
0x18002f8cf  mov     r8d, 105h; MaxCount
0x18002f8d5  lea     rcx, [rsp+288h+szFilePath]; String1
0x18002f8da  mov     rdx, rdi; String2
0x18002f8dd  call    cs:__imp__wcsnicmp
0x18002f8e4  nop     dword ptr [rax+rax+00h]
0x18002f8e9  test    eax, eax
0x18002f8eb  jnz     short loc_18002F917
0x18002f8ed  lea     rdx, [rsp+288h+FileInformation]; lpFileInformation
0x18002f8f2  mov     rcx, rbx; hFile
0x18002f8f5  call    cs:__imp_GetFileInformationByHandle
0x18002f8fc  nop     dword ptr [rax+rax+00h]
0x18002f901  test    eax, eax
0x18002f903  jz      short loc_18002F917
0x18002f905  mov     eax, 1
0x18002f90a  cmp     eax, [rsp+288h+FileInformation.nNumberOfLinks]
0x18002f90e  sbb     eax, eax
0x18002f910  and     eax, 800700A1h
0x18002f915  jmp     short loc_18002F923
0x18002f917  mov     eax, 800700A1h
0x18002f91c  jmp     short loc_18002F923
0x18002f91e  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x18002f923  mov     rcx, [rsp+288h+var_18]
0x18002f92b  xor     rcx, rsp; StackCookie
0x18002f92e  call    __security_check_cookie
0x18002f933  mov     rbx, [rsp+288h+arg_10]
0x18002f93b  add     rsp, 280h
0x18002f942  pop     rdi
0x18002f943  retn
```
