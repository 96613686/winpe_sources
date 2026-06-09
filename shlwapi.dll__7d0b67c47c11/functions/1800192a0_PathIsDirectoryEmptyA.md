# PathIsDirectoryEmptyA

- ea: `0x1800192a0`
- end: `0x180019377`
- name: `PathIsDirectoryEmptyA`
- size: `215`
- prototype: `BOOL __stdcall(LPCSTR pszPath)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180012550`
- `0x180013066`
- `0x1800192a0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001934e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001934e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileA` at `0x180019306`
- `api-ms-win-core-file-l1-1-0!FindFirstFileA` at `0x180019306`
- `api-ms-win-core-file-l1-1-0!FindNextFileA` at `0x18001933d`
- `api-ms-win-core-file-l1-1-0!FindNextFileA` at `0x18001933d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineA` at `0x1800192dc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineA` at `0x1800192dc`

## pseudocode

```c
BOOL __stdcall PathIsDirectoryEmptyA(LPCSTR pszPath)
{
  BOOL v1; // ebx
  HANDLE FirstFileA; // rdi
  struct _WIN32_FIND_DATAA FindFileData; // [rsp+20h] [rbp-268h] BYREF
  CHAR pszDest[272]; // [rsp+160h] [rbp-128h] BYREF

  v1 = 0;
  if ( pszPath )
  {
    if ( PathCombineA(pszDest, pszPath, "*.*") )
    {
      memset_0(&FindFileData, 0, sizeof(FindFileData));
      FirstFileA = FindFirstFileA(pszDest, &FindFileData);
      if ( FirstFileA != (HANDLE)-1LL )
      {
        v1 = 1;
        while ( FindFileData.cFileName[0] == 46
             && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2]) )
        {
          if ( !FindNextFileA(FirstFileA, &FindFileData) )
            goto LABEL_12;
        }
        v1 = 0;
LABEL_12:
        FindClose(FirstFileA);
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800192a0  mov     [rsp+arg_8], rbx
0x1800192a5  push    rdi
0x1800192a6  sub     rsp, 280h
0x1800192ad  mov     rax, cs:__security_cookie
0x1800192b4  xor     rax, rsp
0x1800192b7  mov     [rsp+288h+var_18], rax
0x1800192bf  xor     ebx, ebx
0x1800192c1  test    rcx, rcx
0x1800192c4  jz      loc_180019354
0x1800192ca  mov     rdx, rcx; pszDir
0x1800192cd  lea     r8, asc_18003D9E8; "*.*"
0x1800192d4  lea     rcx, [rsp+288h+pszDest]; pszDest
0x1800192dc  call    cs:__imp_PathCombineA
0x1800192e2  test    rax, rax
0x1800192e5  jz      short loc_180019354
0x1800192e7  xor     edx, edx; Val
0x1800192e9  lea     rcx, [rsp+288h+FindFileData]; void *
0x1800192ee  mov     r8d, 140h; Size
0x1800192f4  call    memset_0
0x1800192f9  lea     rdx, [rsp+288h+FindFileData]; lpFindFileData
0x1800192fe  lea     rcx, [rsp+288h+pszDest]; lpFileName
0x180019306  call    cs:__imp_FindFirstFileA
0x18001930c  mov     rdi, rax
0x18001930f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180019313  jz      short loc_180019354
0x180019315  mov     ebx, 1
0x18001931a  cmp     [rsp+288h+FindFileData.cFileName], 2Eh ; '.'
0x18001931f  jnz     short loc_180019349
0x180019321  mov     cl, [rsp+288h+FindFileData.cFileName+1]
0x180019325  test    cl, cl
0x180019327  jz      short loc_180019335
0x180019329  cmp     cl, 2Eh ; '.'
0x18001932c  jnz     short loc_180019349
0x18001932e  cmp     [rsp+288h+FindFileData.cFileName+2], 0
0x180019333  jnz     short loc_180019349
0x180019335  lea     rdx, [rsp+288h+FindFileData]; lpFindFileData
0x18001933a  mov     rcx, rdi; hFindFile
0x18001933d  call    cs:__imp_FindNextFileA
0x180019343  test    eax, eax
0x180019345  jnz     short loc_18001931A
0x180019347  jmp     short loc_18001934B
0x180019349  xor     ebx, ebx
0x18001934b  mov     rcx, rdi; hFindFile
0x18001934e  call    cs:__imp_FindClose
0x180019354  mov     eax, ebx
0x180019356  mov     rcx, [rsp+288h+var_18]
0x18001935e  xor     rcx, rsp; StackCookie
0x180019361  call    __security_check_cookie
0x180019366  mov     rbx, [rsp+288h+arg_8]
0x18001936e  add     rsp, 280h
0x180019375  pop     rdi
0x180019376  retn
```
