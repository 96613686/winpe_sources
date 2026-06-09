# CProfMgr::IsFullyBackedUpRUP(_FILETIME,ushort const *,int *)

- ea: `0x180031b7c`
- end: `0x180031d15`
- name: `?IsFullyBackedUpRUP@CProfMgr@@AEAAJU_FILETIME@@PEBGPEAH@Z`
- size: `409`
- prototype: `__int64 __fastcall(CProfMgr *__hidden this, struct _FILETIME, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016674`

## callees

- `0x180003f30`
- `0x180017b30`
- `0x18001a280`
- `0x180031b7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031c38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031c8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031c38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031c8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031cca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031cd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031cca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031cd5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180031ce5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180031ce5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031c29`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031c29`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180031c84`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180031c84`

## string_xrefs

- `0x180031c5b`: `CreateFile failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CProfMgr::IsFullyBackedUpRUP(CProfMgr *this, FILETIME a2, const unsigned __int16 *a3, int *a4)
{
  signed int v5; // ebx
  int v6; // eax
  HANDLE FileW; // rdi
  signed int LastError; // eax
  signed int v9; // eax
  struct _FILETIME LastWriteTime; // [rsp+40h] [rbp-448h] BYREF
  FILETIME FileTime1; // [rsp+48h] [rbp-440h] BYREF
  WCHAR FileName[520]; // [rsp+50h] [rbp-438h] BYREF

  FileTime1 = a2;
  LastWriteTime = 0;
  *a4 = 0;
  if ( !a3 )
    return (unsigned int)-2147024809;
  v6 = StringCchPrintfW(FileName, 0x208u, L"%s\\NTUSER.DAT", a3);
  v5 = v6;
  if ( v6 < 0 )
  {
    _DbgPrintMessage(8, "StringCchPrintf failed: 0x%x in %s", v6, "CProfMgr::IsFullyBackedUpRUP");
    return (unsigned int)v5;
  }
  FileW = CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 < 0 )
    {
      _DbgPrintMessage(8, "CreateFile failed: 0x%x in %s", v5, "CProfMgr::IsFullyBackedUpRUP");
      goto LABEL_15;
    }
  }
  LastWriteTime = 0;
  if ( !GetFileTime(FileW, 0, 0, &LastWriteTime) )
  {
    v9 = GetLastError();
    v5 = v9;
    if ( v9 > 0 )
      v5 = (unsigned __int16)v9 | 0x80070000;
    if ( v5 < 0 )
    {
      _DbgPrintMessage(8, "GetFileTime failed: 0x%x in %s", v5, "CProfMgr::IsFullyBackedUpRUP");
      if ( !FileW )
        return (unsigned int)v5;
LABEL_15:
      CloseHandle(FileW);
      return (unsigned int)v5;
    }
  }
  CloseHandle(FileW);
  if ( CompareFileTime(&FileTime1, &LastWriteTime) != -1 )
    *a4 = 1;
  return 0;
}

```

## disassembly

```asm
0x180031b7c  push    rbx
0x180031b7e  push    rsi
0x180031b7f  push    rdi
0x180031b80  sub     rsp, 470h
0x180031b87  mov     rax, cs:__security_cookie
0x180031b8e  xor     rax, rsp
0x180031b91  mov     [rsp+488h+var_28], rax
0x180031b99  mov     qword ptr [rsp+488h+FileTime1.dwLowDateTime], rdx
0x180031b9e  mov     rsi, r9
0x180031ba1  mov     qword ptr [rsp+488h+LastWriteTime.dwLowDateTime], 0
0x180031baa  mov     dword ptr [r9], 0
0x180031bb1  test    r8, r8
0x180031bb4  jnz     short loc_180031BC0
0x180031bb6  mov     ebx, 80070057h
0x180031bbb  jmp     loc_180031CF8
0x180031bc0  mov     r9, r8
0x180031bc3  lea     rcx, [rsp+488h+FileName]; unsigned __int16 *
0x180031bc8  lea     r8, aSNtuserDat; "%s\\NTUSER.DAT"
0x180031bcf  mov     edx, 208h; unsigned __int64
0x180031bd4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180031bd9  mov     ebx, eax
0x180031bdb  test    eax, eax
0x180031bdd  jns     short loc_180031BFF
0x180031bdf  lea     r9, aCprofmgrIsfull; "CProfMgr::IsFullyBackedUpRUP"
0x180031be6  mov     r8d, eax
0x180031be9  lea     rdx, aStringcchprint; "StringCchPrintf failed: 0x%x in %s"
0x180031bf0  mov     ecx, 8; int
0x180031bf5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180031bfa  jmp     loc_180031CF8
0x180031bff  xor     r9d, r9d; lpSecurityAttributes
0x180031c02  mov     [rsp+488h+hTemplateFile], 0; hTemplateFile
0x180031c0b  mov     [rsp+488h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180031c13  lea     rcx, [rsp+488h+FileName]; lpFileName
0x180031c18  mov     edx, 80000000h; dwDesiredAccess
0x180031c1d  mov     [rsp+488h+dwCreationDisposition], 3; dwCreationDisposition
0x180031c25  lea     r8d, [r9+1]; dwShareMode
0x180031c29  call    cs:__imp_CreateFileW
0x180031c2f  mov     rdi, rax
0x180031c32  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180031c36  jnz     short loc_180031C6E
0x180031c38  call    cs:__imp_GetLastError
0x180031c3e  mov     ebx, eax
0x180031c40  test    eax, eax
0x180031c42  jle     short loc_180031C4D
0x180031c44  movzx   ebx, ax
0x180031c47  or      ebx, 80070000h
0x180031c4d  test    ebx, ebx
0x180031c4f  jns     short loc_180031C6E
0x180031c51  lea     r9, aCprofmgrIsfull; "CProfMgr::IsFullyBackedUpRUP"
0x180031c58  mov     r8d, ebx
0x180031c5b  lea     rdx, aCreatefileFail; "CreateFile failed: 0x%x in %s"
0x180031c62  mov     ecx, 8; int
0x180031c67  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180031c6c  jmp     short loc_180031CC7
0x180031c6e  lea     r9, [rsp+488h+LastWriteTime]; lpLastWriteTime
0x180031c73  mov     qword ptr [rsp+488h+LastWriteTime.dwLowDateTime], 0
0x180031c7c  xor     r8d, r8d; lpLastAccessTime
0x180031c7f  xor     edx, edx; lpCreationTime
0x180031c81  mov     rcx, rdi; hFile
0x180031c84  call    cs:__imp_GetFileTime
0x180031c8a  test    eax, eax
0x180031c8c  jnz     short loc_180031CD2
0x180031c8e  call    cs:__imp_GetLastError
0x180031c94  mov     ebx, eax
0x180031c96  test    eax, eax
0x180031c98  jle     short loc_180031CA3
0x180031c9a  movzx   ebx, ax
0x180031c9d  or      ebx, 80070000h
0x180031ca3  test    ebx, ebx
0x180031ca5  jns     short loc_180031CD2
0x180031ca7  lea     r9, aCprofmgrIsfull; "CProfMgr::IsFullyBackedUpRUP"
0x180031cae  mov     r8d, ebx
0x180031cb1  lea     rdx, aGetfiletimeFai; "GetFileTime failed: 0x%x in %s"
0x180031cb8  mov     ecx, 8; int
0x180031cbd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180031cc2  test    rdi, rdi
0x180031cc5  jz      short loc_180031CF8
0x180031cc7  mov     rcx, rdi; hObject
0x180031cca  call    cs:__imp_CloseHandle
0x180031cd0  jmp     short loc_180031CF8
0x180031cd2  mov     rcx, rdi; hObject
0x180031cd5  call    cs:__imp_CloseHandle
0x180031cdb  lea     rdx, [rsp+488h+LastWriteTime]; lpFileTime2
0x180031ce0  lea     rcx, [rsp+488h+FileTime1]; lpFileTime1
0x180031ce5  call    cs:__imp_CompareFileTime
0x180031ceb  cmp     eax, 0FFFFFFFFh
0x180031cee  jz      short loc_180031CF6
0x180031cf0  mov     dword ptr [rsi], 1
0x180031cf6  xor     ebx, ebx
0x180031cf8  mov     eax, ebx
0x180031cfa  mov     rcx, [rsp+488h+var_28]
0x180031d02  xor     rcx, rsp; StackCookie
0x180031d05  call    __security_check_cookie
0x180031d0a  add     rsp, 470h
0x180031d11  pop     rdi
0x180031d12  pop     rsi
0x180031d13  pop     rbx
0x180031d14  retn
```
