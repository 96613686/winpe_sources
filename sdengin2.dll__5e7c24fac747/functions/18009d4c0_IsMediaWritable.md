# IsMediaWritable

- ea: `0x18009d4c0`
- end: `0x18009d5de`
- name: `IsMediaWritable`
- size: `286`
- prototype: `__int64 __fastcall(unsigned int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18009d5e4`

## callees

- `0x18009d2f0`
- `0x18009d4c0`
- `0x18009d98c`
- `0x1800c9830`

## import_xrefs

- `msvcrt!_getdrive` at `0x18009d4f9`
- `msvcrt!_getdrive` at `0x18009d4f9`
- `KERNEL32!CloseHandle` at `0x18009d5a5`
- `KERNEL32!CloseHandle` at `0x18009d5a5`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeA` at `0x18009d526`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeA` at `0x18009d526`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18009d596`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18009d596`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x18009d5b0`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x18009d5b0`
- `api-ms-win-core-file-l1-2-2!GetTempFileNameA` at `0x18009d567`
- `api-ms-win-core-file-l1-2-2!GetTempFileNameA` at `0x18009d567`

## pseudocode

```c
__int64 __fastcall IsMediaWritable(unsigned int a1, __int64 a2)
{
  unsigned int v2; // edi
  unsigned int v3; // ebx
  HANDLE FileA; // rax
  char pszDest[16]; // [rsp+40h] [rbp-248h] BYREF
  CHAR TempFileName[272]; // [rsp+50h] [rbp-238h] BYREF
  CHAR RootPathName[272]; // [rsp+160h] [rbp-128h] BYREF

  v2 = a1;
  if ( (*(_WORD *)(a2 + 3740) & 0x4000) != 0 )
    return 1;
  v3 = 0;
  if ( !a1 )
    v2 = _getdrive();
  if ( (unsigned int)GetRootDirName(v2, RootPathName, 260) )
  {
    if ( GetDriveTypeA(RootPathName) == 5 )
      return 1;
    StringCchPrintfA(pszDest, 4u, "%c:\\", (unsigned int)(char)(v2 + 64));
    if ( GetTempFileNameA(pszDest, "~mv", 0, TempFileName) )
    {
      FileA = CreateFileA(TempFileName, 0xC0000000, 0, 0, 2u, 0x80u, 0);
      if ( FileA != (HANDLE)-1LL )
      {
        CloseHandle(FileA);
        DeleteFileA(TempFileName);
        return 1;
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18009d4c0  mov     [rsp+arg_8], rbx
0x18009d4c5  push    rdi
0x18009d4c6  sub     rsp, 280h
0x18009d4cd  mov     rax, cs:__security_cookie
0x18009d4d4  xor     rax, rsp
0x18009d4d7  mov     [rsp+288h+var_18], rax
0x18009d4df  mov     eax, 4000h
0x18009d4e4  mov     edi, ecx
0x18009d4e6  test    [rdx+0E9Ch], ax
0x18009d4ed  jnz     loc_18009D5B6
0x18009d4f3  xor     ebx, ebx
0x18009d4f5  test    ecx, ecx
0x18009d4f7  jnz     short loc_18009D501
0x18009d4f9  call    cs:__imp__getdrive
0x18009d4ff  mov     edi, eax
0x18009d501  mov     r8d, 104h
0x18009d507  lea     rdx, [rsp+288h+RootPathName]
0x18009d50f  mov     ecx, edi
0x18009d511  call    GetRootDirName
0x18009d516  test    eax, eax
0x18009d518  jz      loc_18009D5BB
0x18009d51e  lea     rcx, [rsp+288h+RootPathName]; lpRootPathName
0x18009d526  call    cs:__imp_GetDriveTypeA
0x18009d52c  cmp     eax, 5
0x18009d52f  jz      loc_18009D5B6
0x18009d535  add     dil, 40h ; '@'
0x18009d539  lea     r8, aC; "%c:\\"
0x18009d540  movsx   r9d, dil
0x18009d544  lea     rcx, [rsp+288h+pszDest]; pszDest
0x18009d549  mov     edx, 4; cchDest
0x18009d54e  call    StringCchPrintfA
0x18009d553  lea     r9, [rsp+288h+TempFileName]; lpTempFileName
0x18009d558  xor     r8d, r8d; uUnique
0x18009d55b  lea     rdx, PrefixString; "~mv"
0x18009d562  lea     rcx, [rsp+288h+pszDest]; lpPathName
0x18009d567  call    cs:__imp_GetTempFileNameA
0x18009d56d  test    eax, eax
0x18009d56f  jz      short loc_18009D5BB
0x18009d571  mov     [rsp+288h+hTemplateFile], rbx; hTemplateFile
0x18009d576  lea     rcx, [rsp+288h+TempFileName]; lpFileName
0x18009d57b  mov     [rsp+288h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18009d583  xor     r9d, r9d; lpSecurityAttributes
0x18009d586  xor     r8d, r8d; dwShareMode
0x18009d589  mov     [rsp+288h+dwCreationDisposition], 2; dwCreationDisposition
0x18009d591  mov     edx, 0C0000000h; dwDesiredAccess
0x18009d596  call    cs:__imp_CreateFileA
0x18009d59c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009d5a0  jz      short loc_18009D5BB
0x18009d5a2  mov     rcx, rax; hObject
0x18009d5a5  call    cs:__imp_CloseHandle
0x18009d5ab  lea     rcx, [rsp+288h+TempFileName]; lpFileName
0x18009d5b0  call    cs:__imp_DeleteFileA
0x18009d5b6  mov     ebx, 1
0x18009d5bb  mov     eax, ebx
0x18009d5bd  mov     rcx, [rsp+288h+var_18]
0x18009d5c5  xor     rcx, rsp; StackCookie
0x18009d5c8  call    __security_check_cookie
0x18009d5cd  mov     rbx, [rsp+288h+arg_8]
0x18009d5d5  add     rsp, 280h
0x18009d5dc  pop     rdi
0x18009d5dd  retn
```
