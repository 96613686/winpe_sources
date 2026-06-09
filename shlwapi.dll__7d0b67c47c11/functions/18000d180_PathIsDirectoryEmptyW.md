# PathIsDirectoryEmptyW

- ea: `0x18000d180`
- end: `0x18000d264`
- name: `PathIsDirectoryEmptyW`
- size: `228`
- prototype: `BOOL __stdcall(LPCWSTR pszPath)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x18000d180`
- `0x180012550`
- `0x180013066`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000d226`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000d226`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000d1ed`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000d1ed`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000d237`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000d237`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineW` at `0x18000d1c3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineW` at `0x18000d1c3`

## pseudocode

```c
BOOL __stdcall PathIsDirectoryEmptyW(LPCWSTR pszPath)
{
  BOOL v1; // ebx
  HANDLE FirstFileW; // rdi
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+20h] [rbp-478h] BYREF
  WCHAR pszDest[264]; // [rsp+270h] [rbp-228h] BYREF

  v1 = 0;
  if ( pszPath )
  {
    if ( PathCombineW(pszDest, pszPath, L"*.*") )
    {
      memset_0(&FindFileData, 0, sizeof(FindFileData));
      FirstFileW = FindFirstFileW(pszDest, &FindFileData);
      if ( FirstFileW != (HANDLE)-1LL )
      {
        v1 = 1;
        while ( FindFileData.cFileName[0] == 46
             && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2]) )
        {
          if ( !FindNextFileW(FirstFileW, &FindFileData) )
            goto LABEL_12;
        }
        v1 = 0;
LABEL_12:
        FindClose(FirstFileW);
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18000d180  mov     [rsp+arg_8], rbx
0x18000d185  mov     [rsp+arg_10], rsi
0x18000d18a  push    rdi
0x18000d18b  sub     rsp, 490h
0x18000d192  mov     rax, cs:__security_cookie
0x18000d199  xor     rax, rsp
0x18000d19c  mov     [rsp+498h+var_18], rax
0x18000d1a4  xor     esi, esi
0x18000d1a6  mov     ebx, esi
0x18000d1a8  test    rcx, rcx
0x18000d1ab  jz      loc_18000D23D
0x18000d1b1  mov     rdx, rcx; pszDir
0x18000d1b4  lea     r8, asc_18003CC50; "*.*"
0x18000d1bb  lea     rcx, [rsp+498h+pszDest]; pszDest
0x18000d1c3  call    cs:__imp_PathCombineW
0x18000d1c9  test    rax, rax
0x18000d1cc  jz      short loc_18000D23D
0x18000d1ce  xor     edx, edx; Val
0x18000d1d0  lea     rcx, [rsp+498h+FindFileData]; void *
0x18000d1d5  mov     r8d, 250h; Size
0x18000d1db  call    memset_0
0x18000d1e0  lea     rdx, [rsp+498h+FindFileData]; lpFindFileData
0x18000d1e5  lea     rcx, [rsp+498h+pszDest]; lpFileName
0x18000d1ed  call    cs:__imp_FindFirstFileW
0x18000d1f3  mov     rdi, rax
0x18000d1f6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d1fa  jz      short loc_18000D23D
0x18000d1fc  lea     ebx, [rsi+1]
0x18000d1ff  cmp     [rsp+498h+FindFileData.cFileName], 2Eh ; '.'
0x18000d205  jnz     short loc_18000D232
0x18000d207  movzx   ecx, [rsp+498h+FindFileData.cFileName+2]
0x18000d20c  test    cx, cx
0x18000d20f  jz      short loc_18000D21E
0x18000d211  cmp     cx, 2Eh ; '.'
0x18000d215  jnz     short loc_18000D232
0x18000d217  cmp     [rsp+498h+FindFileData.cFileName+4], si
0x18000d21c  jnz     short loc_18000D232
0x18000d21e  lea     rdx, [rsp+498h+FindFileData]; lpFindFileData
0x18000d223  mov     rcx, rdi; hFindFile
0x18000d226  call    cs:__imp_FindNextFileW
0x18000d22c  test    eax, eax
0x18000d22e  jnz     short loc_18000D1FF
0x18000d230  jmp     short loc_18000D234
0x18000d232  mov     ebx, esi
0x18000d234  mov     rcx, rdi; hFindFile
0x18000d237  call    cs:__imp_FindClose
0x18000d23d  mov     eax, ebx
0x18000d23f  mov     rcx, [rsp+498h+var_18]
0x18000d247  xor     rcx, rsp; StackCookie
0x18000d24a  call    __security_check_cookie
0x18000d24f  lea     r11, [rsp+498h+var_8]
0x18000d257  mov     rbx, [r11+18h]
0x18000d25b  mov     rsi, [r11+20h]
0x18000d25f  mov     rsp, r11
0x18000d262  pop     rdi
0x18000d263  retn
```
