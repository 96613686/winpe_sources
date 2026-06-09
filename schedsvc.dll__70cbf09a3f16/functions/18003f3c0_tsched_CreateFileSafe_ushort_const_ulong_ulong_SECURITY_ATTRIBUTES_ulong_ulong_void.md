# tsched::CreateFileSafe(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)

- ea: `0x18003f3c0`
- end: `0x18003f4c6`
- name: `?CreateFileSafe@tsched@@YAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(wchar_t *String2, const unsigned __int16 *, DWORD, struct _SECURITY_ATTRIBUTES *, struct _SECURITY_ATTRIBUTES *dwCreationDisposition, DWORD dwFlagsAndAttributes)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180026460`
- `0x18007a26c`

## callees

- `0x18003f3c0`
- `0x180052584`
- `0x18007e6d0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18003f460`
- `msvcrt!_wcsnicmp` at `0x18003f460`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f488`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f488`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003f401`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003f401`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18003f440`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18003f440`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18003f472`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18003f472`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f491`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f491`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall tsched::CreateFileSafe(
        wchar_t *String2,
        const unsigned __int16 *a2,
        DWORD a3,
        struct _SECURITY_ATTRIBUTES *a4,
        struct _SECURITY_ATTRIBUTES *dwCreationDisposition,
        DWORD dwFlagsAndAttributes)
{
  HANDLE FileW; // rbx
  int v8; // edx
  tsched *v9; // rcx
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+40h] [rbp-278h] BYREF
  WCHAR szFilePath[264]; // [rsp+80h] [rbp-238h] BYREF

  FileW = CreateFileW(String2, (DWORD)a2, a3, a4, (DWORD)dwCreationDisposition, dwFlagsAndAttributes, 0);
  if ( FileW == (HANDLE)-1LL )
    return -1;
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( GetFinalPathNameByHandleW(FileW, szFilePath, 0x105u, 0) - 1 > 0x103 )
  {
    if ( (int)tsched::GetLastHrError(v9, v8) < 0 )
    {
LABEL_6:
      SetLastError(5u);
      CloseHandle(FileW);
      return -1;
    }
  }
  else if ( _wcsnicmp(szFilePath, String2, 0x105u)
         || !GetFileInformationByHandle(FileW, &FileInformation)
         || FileInformation.nNumberOfLinks > 1 )
  {
    goto LABEL_6;
  }
  return (__int64)FileW;
}

```

## disassembly

```asm
0x18003f3c0  push    rbx
0x18003f3c2  push    rdi
0x18003f3c3  sub     rsp, 2A8h
0x18003f3ca  mov     rax, cs:__security_cookie
0x18003f3d1  xor     rax, rsp
0x18003f3d4  mov     [rsp+2B8h+var_28], rax
0x18003f3dc  mov     eax, [rsp+2B8h+arg_28]
0x18003f3e3  mov     rdi, rcx
0x18003f3e6  mov     ecx, dword ptr [rsp+2B8h+arg_20]
0x18003f3ed  mov     [rsp+2B8h+hTemplateFile], 0; hTemplateFile
0x18003f3f6  mov     [rsp+2B8h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18003f3fa  mov     [rsp+2B8h+dwCreationDisposition], ecx; dwCreationDisposition
0x18003f3fe  mov     rcx, rdi; lpFileName
0x18003f401  call    cs:__imp_CreateFileW
0x18003f407  mov     rbx, rax
0x18003f40a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003f40e  jz      loc_18003F497
0x18003f414  xorps   xmm0, xmm0
0x18003f417  lea     rdx, [rsp+2B8h+szFilePath]; lpszFilePath
0x18003f41f  xor     eax, eax
0x18003f421  xor     r9d, r9d; dwFlags
0x18003f424  mov     r8d, 105h; cchFilePath
0x18003f42a  mov     [rsp+2B8h+FileInformation.nFileIndexLow], eax
0x18003f42e  mov     rcx, rbx; hFile
0x18003f431  movups  xmmword ptr [rsp+2B8h+FileInformation.dwFileAttributes], xmm0
0x18003f436  movups  xmmword ptr [rsp+2B8h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18003f43b  movups  xmmword ptr [rsp+2B8h+FileInformation.nFileSizeHigh], xmm0
0x18003f440  call    cs:__imp_GetFinalPathNameByHandleW
0x18003f446  dec     eax
0x18003f448  cmp     eax, 103h
0x18003f44d  ja      short loc_18003F4A0
0x18003f44f  mov     r8d, 105h; MaxCount
0x18003f455  lea     rcx, [rsp+2B8h+szFilePath]; String1
0x18003f45d  mov     rdx, rdi; String2
0x18003f460  call    cs:__imp__wcsnicmp
0x18003f466  test    eax, eax
0x18003f468  jnz     short loc_18003F483
0x18003f46a  lea     rdx, [rsp+2B8h+FileInformation]; lpFileInformation
0x18003f46f  mov     rcx, rbx; hFile
0x18003f472  call    cs:__imp_GetFileInformationByHandle
0x18003f478  test    eax, eax
0x18003f47a  jz      short loc_18003F483
0x18003f47c  cmp     [rsp+2B8h+FileInformation.nNumberOfLinks], 1
0x18003f481  jbe     short loc_18003F4A9
0x18003f483  mov     ecx, 5; dwErrCode
0x18003f488  call    cs:__imp_SetLastError
0x18003f48e  mov     rcx, rbx; hObject
0x18003f491  call    cs:__imp_CloseHandle
0x18003f497  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18003f49e  jmp     short loc_18003F4AC
0x18003f4a0  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x18003f4a5  test    eax, eax
0x18003f4a7  js      short loc_18003F483
0x18003f4a9  mov     rax, rbx
0x18003f4ac  mov     rcx, [rsp+2B8h+var_28]
0x18003f4b4  xor     rcx, rsp; StackCookie
0x18003f4b7  call    __security_check_cookie
0x18003f4bc  add     rsp, 2A8h
0x18003f4c3  pop     rdi
0x18003f4c4  pop     rbx
0x18003f4c5  retn
```
