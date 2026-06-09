# RemoveDirectoryAndChildren

- ea: `0x1800d0298`
- end: `0x1800d0560`
- name: `RemoveDirectoryAndChildren`
- size: `712`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800d0298`
- `0x1800d6abc`

## callees

- `0x18004d7f0`
- `0x18005dd10`
- `0x18005e1c0`
- `0x1800d0298`
- `0x1801285fe`
- `0x180128660`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x1800d0378`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x1800d0398`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x1800d0378`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x1800d0398`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d04bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d04cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d051b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d04bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d04cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d051b`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x1800d0458`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x1800d047d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x1800d0458`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x1800d047d`
- `api-ms-win-core-file-l1-1-0!FindNextFileA` at `0x1800d04a8`
- `api-ms-win-core-file-l1-1-0!FindNextFileA` at `0x1800d04a8`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800d04eb`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800d04fc`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800d04eb`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800d04fc`
- `api-ms-win-core-file-l1-1-0!FindFirstFileA` at `0x1800d0353`
- `api-ms-win-core-file-l1-1-0!FindFirstFileA` at `0x1800d0353`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryA` at `0x1800d02f1`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryA` at `0x1800d050b`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryA` at `0x1800d02f1`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryA` at `0x1800d050b`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x1800d0490`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x1800d0490`

## pseudocode

```c
__int64 __fastcall RemoveDirectoryAndChildren(char *a1)
{
  int v2; // ebx
  HANDLE FirstFileA; // rsi
  signed int LastError; // eax
  signed int v5; // eax
  unsigned __int64 v7; // [rsp+30h] [rbp-D0h] BYREF
  STRSAFE_LPSTR pszDest; // [rsp+38h] [rbp-C8h] BYREF
  struct _WIN32_FIND_DATAA FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  CHAR PathName[272]; // [rsp+180h] [rbp+80h] BYREF

  v2 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( a1 )
  {
    if ( *a1 )
    {
      if ( !RemoveDirectoryA(a1) )
      {
        v2 = StringCchCopyA(PathName, 0x104u, a1);
        if ( v2 >= 0 )
        {
          v2 = StringCchCatA(PathName, 260, "\\*");
          if ( v2 >= 0 )
          {
            FirstFileA = FindFirstFileA(PathName, &FindFileData);
            if ( FirstFileA == (HANDLE)-1LL )
              goto LABEL_22;
            do
            {
              if ( lstrcmpA(FindFileData.cFileName, ".") && lstrcmpA(FindFileData.cFileName, "..") )
              {
                pszDest = PathName;
                v7 = 260;
                v2 = StringCchCopyExA(PathName, 0x104u, a1, &pszDest, &v7, 0);
                if ( v2 < 0 )
                  goto LABEL_20;
                v2 = StringCchCopyExA(pszDest, v7, "\\", &pszDest, &v7, 0);
                if ( v2 < 0 )
                  goto LABEL_20;
                v2 = StringCchCopyA(pszDest, v7, FindFileData.cFileName);
                if ( v2 < 0 )
                  goto LABEL_20;
                if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
                {
                  SetFileAttributesA(PathName, 0x90u);
                  v2 = RemoveDirectoryAndChildren(PathName);
                  if ( v2 < 0 )
                    goto LABEL_20;
                }
                else
                {
                  SetFileAttributesA(PathName, 0x80u);
                  if ( !DeleteFileA(PathName) )
                    goto LABEL_18;
                }
              }
            }
            while ( FindNextFileA(FirstFileA, &FindFileData) );
            if ( GetLastError() != 18 )
            {
LABEL_18:
              LastError = GetLastError();
              v2 = LastError;
              if ( LastError > 0 )
                v2 = (unsigned __int16)LastError | 0x80070000;
LABEL_20:
              FindClose(FirstFileA);
              return (unsigned int)v2;
            }
            FindClose(FirstFileA);
            if ( !RemoveDirectoryA(a1) )
            {
LABEL_22:
              v5 = GetLastError();
              v2 = v5;
              if ( v5 > 0 )
                return (unsigned __int16)v5 | 0x80070000;
            }
          }
        }
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800d0298  mov     [rsp-8+arg_8], rbx
0x1800d029d  mov     [rsp-8+arg_10], rsi
0x1800d02a2  push    rbp
0x1800d02a3  push    rdi
0x1800d02a4  push    r15
0x1800d02a6  lea     rbp, [rsp-1A0h]
0x1800d02ae  sub     rsp, 2A0h
0x1800d02b5  mov     rax, cs:__security_cookie
0x1800d02bc  xor     rax, rsp
0x1800d02bf  mov     [rbp+1B0h+var_20], rax
0x1800d02c6  mov     rdi, rcx
0x1800d02c9  xor     edx, edx; Val
0x1800d02cb  lea     rcx, [rsp+2B0h+FindFileData]; void *
0x1800d02d0  mov     r8d, 140h; Size
0x1800d02d6  xor     ebx, ebx
0x1800d02d8  call    memset_0
0x1800d02dd  test    rdi, rdi
0x1800d02e0  jz      loc_1800D0536
0x1800d02e6  cmp     [rdi], bl
0x1800d02e8  jz      loc_1800D0536
0x1800d02ee  mov     rcx, rdi; lpPathName
0x1800d02f1  call    cs:__imp_RemoveDirectoryA
0x1800d02f8  nop     dword ptr [rax+rax+00h]
0x1800d02fd  test    eax, eax
0x1800d02ff  jnz     loc_1800D0536
0x1800d0305  mov     r15d, 104h
0x1800d030b  lea     rcx, [rbp+1B0h+PathName]; char *
0x1800d0312  mov     edx, r15d; unsigned __int64
0x1800d0315  mov     r8, rdi; char *
0x1800d0318  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800d031d  mov     ebx, eax
0x1800d031f  test    eax, eax
0x1800d0321  js      loc_1800D0536
0x1800d0327  lea     r8, asc_180141D2C; "\\*"
0x1800d032e  mov     edx, r15d; unsigned __int64
0x1800d0331  lea     rcx, [rbp+1B0h+PathName]; char *
0x1800d0338  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x1800d033d  mov     ebx, eax
0x1800d033f  test    eax, eax
0x1800d0341  js      loc_1800D0536
0x1800d0347  lea     rdx, [rsp+2B0h+FindFileData]; lpFindFileData
0x1800d034c  lea     rcx, [rbp+1B0h+PathName]; lpFileName
0x1800d0353  call    cs:__imp_FindFirstFileA
0x1800d035a  nop     dword ptr [rax+rax+00h]
0x1800d035f  mov     rsi, rax
0x1800d0362  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800d0366  jz      loc_1800D051B
0x1800d036c  lea     rdx, asc_180141D30; "."
0x1800d0373  lea     rcx, [rsp+2B0h+FindFileData.cFileName]; lpString1
0x1800d0378  call    cs:__imp_lstrcmpA
0x1800d037f  nop     dword ptr [rax+rax+00h]
0x1800d0384  test    eax, eax
0x1800d0386  jz      loc_1800D04A0
0x1800d038c  lea     rdx, asc_180141D34; ".."
0x1800d0393  lea     rcx, [rsp+2B0h+FindFileData.cFileName]; lpString1
0x1800d0398  call    cs:__imp_lstrcmpA
0x1800d039f  nop     dword ptr [rax+rax+00h]
0x1800d03a4  test    eax, eax
0x1800d03a6  jz      loc_1800D04A0
0x1800d03ac  lea     rax, [rbp+1B0h+PathName]
0x1800d03b3  mov     [rsp+2B0h+var_288], 0; unsigned int
0x1800d03bb  mov     [rsp+2B0h+pszDest], rax
0x1800d03c0  lea     r9, [rsp+2B0h+pszDest]; char **
0x1800d03c5  lea     rax, [rsp+2B0h+var_280]
0x1800d03ca  mov     [rsp+2B0h+var_280], r15
0x1800d03cf  mov     r8, rdi; char *
0x1800d03d2  mov     [rsp+2B0h+var_290], rax; unsigned __int64 *
0x1800d03d7  mov     rdx, r15; unsigned __int64
0x1800d03da  lea     rcx, [rbp+1B0h+PathName]; pszDest
0x1800d03e1  call    ?StringCchCopyExA@@YAJPEAD_KPEBDPEAPEADPEA_KK@Z; StringCchCopyExA(char *,unsigned __int64,char const *,char * *,unsigned __int64 *,ulong)
0x1800d03e6  mov     ebx, eax
0x1800d03e8  test    eax, eax
0x1800d03ea  js      loc_1800D04E8
0x1800d03f0  mov     rdx, [rsp+2B0h+var_280]; unsigned __int64
0x1800d03f5  lea     rax, [rsp+2B0h+var_280]
0x1800d03fa  mov     rcx, [rsp+2B0h+pszDest]; pszDest
0x1800d03ff  lea     r9, [rsp+2B0h+pszDest]; char **
0x1800d0404  mov     [rsp+2B0h+var_288], 0; unsigned int
0x1800d040c  lea     r8, asc_18013A808; "\\"
0x1800d0413  mov     [rsp+2B0h+var_290], rax; unsigned __int64 *
0x1800d0418  call    ?StringCchCopyExA@@YAJPEAD_KPEBDPEAPEADPEA_KK@Z; StringCchCopyExA(char *,unsigned __int64,char const *,char * *,unsigned __int64 *,ulong)
0x1800d041d  mov     ebx, eax
0x1800d041f  test    eax, eax
0x1800d0421  js      loc_1800D04E8
0x1800d0427  mov     rdx, [rsp+2B0h+var_280]; unsigned __int64
0x1800d042c  lea     r8, [rsp+2B0h+FindFileData.cFileName]; char *
0x1800d0431  mov     rcx, [rsp+2B0h+pszDest]; char *
0x1800d0436  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800d043b  mov     ebx, eax
0x1800d043d  test    eax, eax
0x1800d043f  js      loc_1800D04E8
0x1800d0445  test    byte ptr [rsp+2B0h+FindFileData.dwFileAttributes], 10h
0x1800d044a  lea     rcx, [rbp+1B0h+PathName]; lpFileName
0x1800d0451  jz      short loc_1800D0478
0x1800d0453  mov     edx, 90h; dwFileAttributes
0x1800d0458  call    cs:__imp_SetFileAttributesA
0x1800d045f  nop     dword ptr [rax+rax+00h]
0x1800d0464  lea     rcx, [rbp+1B0h+PathName]
0x1800d046b  call    RemoveDirectoryAndChildren
0x1800d0470  mov     ebx, eax
0x1800d0472  test    eax, eax
0x1800d0474  js      short loc_1800D04E8
0x1800d0476  jmp     short loc_1800D04A0
0x1800d0478  mov     edx, 80h; dwFileAttributes
0x1800d047d  call    cs:__imp_SetFileAttributesA
0x1800d0484  nop     dword ptr [rax+rax+00h]
0x1800d0489  lea     rcx, [rbp+1B0h+PathName]; lpFileName
0x1800d0490  call    cs:__imp_DeleteFileA
0x1800d0497  nop     dword ptr [rax+rax+00h]
0x1800d049c  test    eax, eax
0x1800d049e  jz      short loc_1800D04CD
0x1800d04a0  lea     rdx, [rsp+2B0h+FindFileData]; lpFindFileData
0x1800d04a5  mov     rcx, rsi; hFindFile
0x1800d04a8  call    cs:__imp_FindNextFileA
0x1800d04af  nop     dword ptr [rax+rax+00h]
0x1800d04b4  test    eax, eax
0x1800d04b6  jnz     loc_1800D036C
0x1800d04bc  call    cs:__imp_GetLastError
0x1800d04c3  nop     dword ptr [rax+rax+00h]
0x1800d04c8  cmp     eax, 12h
0x1800d04cb  jz      short loc_1800D04F9
0x1800d04cd  call    cs:__imp_GetLastError
0x1800d04d4  nop     dword ptr [rax+rax+00h]
0x1800d04d9  mov     ebx, eax
0x1800d04db  test    eax, eax
0x1800d04dd  jle     short loc_1800D04E8
0x1800d04df  movzx   ebx, ax
0x1800d04e2  or      ebx, 80070000h
0x1800d04e8  mov     rcx, rsi; hFindFile
0x1800d04eb  call    cs:__imp_FindClose
0x1800d04f2  nop     dword ptr [rax+rax+00h]
0x1800d04f7  jmp     short loc_1800D0536
0x1800d04f9  mov     rcx, rsi; hFindFile
0x1800d04fc  call    cs:__imp_FindClose
0x1800d0503  nop     dword ptr [rax+rax+00h]
0x1800d0508  mov     rcx, rdi; lpPathName
0x1800d050b  call    cs:__imp_RemoveDirectoryA
0x1800d0512  nop     dword ptr [rax+rax+00h]
0x1800d0517  test    eax, eax
0x1800d0519  jnz     short loc_1800D0536
0x1800d051b  call    cs:__imp_GetLastError
0x1800d0522  nop     dword ptr [rax+rax+00h]
0x1800d0527  mov     ebx, eax
0x1800d0529  test    eax, eax
0x1800d052b  jle     short loc_1800D0536
0x1800d052d  movzx   ebx, ax
0x1800d0530  or      ebx, 80070000h
0x1800d0536  mov     eax, ebx
0x1800d0538  mov     rcx, [rbp+1B0h+var_20]
0x1800d053f  xor     rcx, rsp; StackCookie
0x1800d0542  call    __security_check_cookie
0x1800d0547  lea     r11, [rsp+2B0h+var_10]
0x1800d054f  mov     rbx, [r11+28h]
0x1800d0553  mov     rsi, [r11+30h]
0x1800d0557  mov     rsp, r11
0x1800d055a  pop     r15
0x1800d055c  pop     rdi
0x1800d055d  pop     rbp
0x1800d055e  retn
```
