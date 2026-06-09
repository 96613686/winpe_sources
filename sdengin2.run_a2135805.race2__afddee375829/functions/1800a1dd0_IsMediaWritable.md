# IsMediaWritable

- ea: `0x1800a1dd0`
- end: `0x1800a1f13`
- name: `IsMediaWritable`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800a1f1c`

## callees

- `0x1800a1be0`
- `0x1800a1dd0`
- `0x1800a22e4`
- `0x1800cf5c0`

## import_xrefs

- `msvcrt!_getdrive` at `0x1800a1e09`
- `msvcrt!_getdrive` at `0x1800a1e09`
- `KERNEL32!CloseHandle` at `0x1800a1ecd`
- `KERNEL32!CloseHandle` at `0x1800a1ecd`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeA` at `0x1800a1e3c`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeA` at `0x1800a1e3c`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800a1eb8`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800a1eb8`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x1800a1ede`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x1800a1ede`
- `api-ms-win-core-file-l1-2-2!GetTempFileNameA` at `0x1800a1e83`
- `api-ms-win-core-file-l1-2-2!GetTempFileNameA` at `0x1800a1e83`

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
0x1800a1dd0  mov     [rsp+arg_8], rbx
0x1800a1dd5  push    rdi
0x1800a1dd6  sub     rsp, 280h
0x1800a1ddd  mov     rax, cs:__security_cookie
0x1800a1de4  xor     rax, rsp
0x1800a1de7  mov     [rsp+288h+var_18], rax
0x1800a1def  mov     eax, 4000h
0x1800a1df4  mov     edi, ecx
0x1800a1df6  test    [rdx+0E9Ch], ax
0x1800a1dfd  jnz     loc_1800A1EEA
0x1800a1e03  xor     ebx, ebx
0x1800a1e05  test    ecx, ecx
0x1800a1e07  jnz     short loc_1800A1E17
0x1800a1e09  call    cs:__imp__getdrive
0x1800a1e10  nop     dword ptr [rax+rax+00h]
0x1800a1e15  mov     edi, eax
0x1800a1e17  mov     r8d, 104h
0x1800a1e1d  lea     rdx, [rsp+288h+RootPathName]
0x1800a1e25  mov     ecx, edi
0x1800a1e27  call    GetRootDirName
0x1800a1e2c  test    eax, eax
0x1800a1e2e  jz      loc_1800A1EEF
0x1800a1e34  lea     rcx, [rsp+288h+RootPathName]; lpRootPathName
0x1800a1e3c  call    cs:__imp_GetDriveTypeA
0x1800a1e43  nop     dword ptr [rax+rax+00h]
0x1800a1e48  cmp     eax, 5
0x1800a1e4b  jz      loc_1800A1EEA
0x1800a1e51  add     dil, 40h ; '@'
0x1800a1e55  lea     r8, aC; "%c:\\"
0x1800a1e5c  movsx   r9d, dil
0x1800a1e60  lea     rcx, [rsp+288h+pszDest]; pszDest
0x1800a1e65  mov     edx, 4; cchDest
0x1800a1e6a  call    StringCchPrintfA
0x1800a1e6f  lea     r9, [rsp+288h+TempFileName]; lpTempFileName
0x1800a1e74  xor     r8d, r8d; uUnique
0x1800a1e77  lea     rdx, PrefixString; "~mv"
0x1800a1e7e  lea     rcx, [rsp+288h+pszDest]; lpPathName
0x1800a1e83  call    cs:__imp_GetTempFileNameA
0x1800a1e8a  nop     dword ptr [rax+rax+00h]
0x1800a1e8f  test    eax, eax
0x1800a1e91  jz      short loc_1800A1EEF
0x1800a1e93  mov     [rsp+288h+hTemplateFile], rbx; hTemplateFile
0x1800a1e98  lea     rcx, [rsp+288h+TempFileName]; lpFileName
0x1800a1e9d  mov     [rsp+288h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800a1ea5  xor     r9d, r9d; lpSecurityAttributes
0x1800a1ea8  xor     r8d, r8d; dwShareMode
0x1800a1eab  mov     [rsp+288h+dwCreationDisposition], 2; dwCreationDisposition
0x1800a1eb3  mov     edx, 0C0000000h; dwDesiredAccess
0x1800a1eb8  call    cs:__imp_CreateFileA
0x1800a1ebf  nop     dword ptr [rax+rax+00h]
0x1800a1ec4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a1ec8  jz      short loc_1800A1EEF
0x1800a1eca  mov     rcx, rax; hObject
0x1800a1ecd  call    cs:__imp_CloseHandle
0x1800a1ed4  nop     dword ptr [rax+rax+00h]
0x1800a1ed9  lea     rcx, [rsp+288h+TempFileName]; lpFileName
0x1800a1ede  call    cs:__imp_DeleteFileA
0x1800a1ee5  nop     dword ptr [rax+rax+00h]
0x1800a1eea  mov     ebx, 1
0x1800a1eef  mov     eax, ebx
0x1800a1ef1  mov     rcx, [rsp+288h+var_18]
0x1800a1ef9  xor     rcx, rsp; StackCookie
0x1800a1efc  call    __security_check_cookie
0x1800a1f01  mov     rbx, [rsp+288h+arg_8]
0x1800a1f09  add     rsp, 280h
0x1800a1f10  pop     rdi
0x1800a1f11  retn
```
