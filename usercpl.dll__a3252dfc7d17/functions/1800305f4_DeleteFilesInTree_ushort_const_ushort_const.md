# DeleteFilesInTree(ushort const *,ushort const *)

- ea: `0x1800305f4`
- end: `0x1800307c3`
- name: `?DeleteFilesInTree@@YAXPEBG0@Z`
- size: `463`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18002fc14`
- `0x1800305f4`

## callees

- `0x1800305f4`
- `0x18007728a`
- `0x1800772c0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18003077b`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18003077b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800306b0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800306b0`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800306be`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180030789`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800306be`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180030789`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180030677`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180030710`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180030677`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180030710`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800306cb`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180030796`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800306cb`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180030796`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180030651`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18003069f`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800306e5`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180030757`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180030651`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18003069f`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800306e5`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180030757`

## pseudocode

```c
void __fastcall DeleteFilesInTree(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  HANDLE FirstFile; // rbx
  HANDLE v4; // rbx
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszPathIn[264]; // [rsp+280h] [rbp+180h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( PathCchCombine(pszPathIn, 0x104u, a1, L"*.lnk") >= 0 )
  {
    FirstFile = FindFirstFileExW(pszPathIn, FindExInfoStandard, &FindFileData, FindExSearchNameMatch, 0, 0);
    if ( FirstFile != (HANDLE)-1LL )
    {
      do
      {
        if ( (FindFileData.dwFileAttributes & 0x10) == 0
          && PathCchCombine(pszPathIn, 0x104u, a1, FindFileData.cFileName) >= 0 )
        {
          DeleteFileW(pszPathIn);
        }
      }
      while ( FindNextFileW(FirstFile, &FindFileData) );
      FindClose(FirstFile);
    }
  }
  if ( PathCchCombine(pszPathIn, 0x104u, a1, L"*") >= 0 )
  {
    v4 = FindFirstFileExW(pszPathIn, FindExInfoStandard, &FindFileData, FindExSearchLimitToDirectories, 0, 0);
    if ( v4 != (HANDLE)-1LL )
    {
      do
      {
        if ( (FindFileData.cFileName[0] != 46
           || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]))
          && (FindFileData.dwFileAttributes & 0x10) != 0 )
        {
          if ( PathCchCombine(pszPathIn, 0x104u, a1, FindFileData.cFileName) >= 0 )
            DeleteFilesInTree(pszPathIn, L"*.lnk");
          RemoveDirectoryW(pszPathIn);
        }
      }
      while ( FindNextFileW(v4, &FindFileData) );
      FindClose(v4);
    }
  }
}

```

## disassembly

```asm
0x1800305f4  mov     [rsp-8+arg_8], rbx
0x1800305f9  mov     [rsp-8+arg_10], rsi
0x1800305fe  push    rbp
0x1800305ff  push    rdi
0x180030600  push    r14
0x180030602  lea     rbp, [rsp-3A0h]
0x18003060a  sub     rsp, 4A0h
0x180030611  mov     rax, cs:__security_cookie
0x180030618  xor     rax, rsp
0x18003061b  mov     [rbp+3B0h+var_20], rax
0x180030622  mov     rdi, rcx
0x180030625  xor     edx, edx; Val
0x180030627  lea     rcx, [rsp+4B0h+FindFileData]; void *
0x18003062c  mov     r8d, 250h; Size
0x180030632  call    memset_0
0x180030637  mov     r14d, 104h
0x18003063d  lea     r9, aLnk; "*.lnk"
0x180030644  mov     edx, r14d; cchPathOut
0x180030647  lea     rcx, [rbp+3B0h+pszPathIn]; pszPathOut
0x18003064e  mov     r8, rdi; pszPathIn
0x180030651  call    cs:__imp_PathCchCombine
0x180030657  xor     esi, esi
0x180030659  test    eax, eax
0x18003065b  js      short loc_1800306D1
0x18003065d  mov     [rsp+4B0h+dwAdditionalFlags], esi; dwAdditionalFlags
0x180030661  lea     r8, [rsp+4B0h+FindFileData]; lpFindFileData
0x180030666  xor     r9d, r9d; fSearchOp
0x180030669  mov     [rsp+4B0h+lpSearchFilter], rsi; lpSearchFilter
0x18003066e  xor     edx, edx; fInfoLevelId
0x180030670  lea     rcx, [rbp+3B0h+pszPathIn]; lpFileName
0x180030677  call    cs:__imp_FindFirstFileExW
0x18003067d  mov     rbx, rax
0x180030680  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180030684  jz      short loc_1800306D1
0x180030686  test    [rsp+4B0h+FindFileData], 10h
0x18003068b  jnz     short loc_1800306B6
0x18003068d  lea     r9, [rsp+4B0h+pszMore]; pszMore
0x180030692  mov     r8, rdi; pszPathIn
0x180030695  mov     rdx, r14; cchPathOut
0x180030698  lea     rcx, [rbp+3B0h+pszPathIn]; pszPathOut
0x18003069f  call    cs:__imp_PathCchCombine
0x1800306a5  test    eax, eax
0x1800306a7  js      short loc_1800306B6
0x1800306a9  lea     rcx, [rbp+3B0h+pszPathIn]; lpFileName
0x1800306b0  call    cs:__imp_DeleteFileW
0x1800306b6  lea     rdx, [rsp+4B0h+FindFileData]; lpFindFileData
0x1800306bb  mov     rcx, rbx; hFindFile
0x1800306be  call    cs:__imp_FindNextFileW
0x1800306c4  test    eax, eax
0x1800306c6  jnz     short loc_180030686
0x1800306c8  mov     rcx, rbx; hFindFile
0x1800306cb  call    cs:__imp_FindClose
0x1800306d1  lea     r9, asc_18008A458; "*"
0x1800306d8  mov     r8, rdi; pszPathIn
0x1800306db  mov     rdx, r14; cchPathOut
0x1800306de  lea     rcx, [rbp+3B0h+pszPathIn]; pszPathOut
0x1800306e5  call    cs:__imp_PathCchCombine
0x1800306eb  test    eax, eax
0x1800306ed  js      loc_18003079C
0x1800306f3  mov     [rsp+4B0h+dwAdditionalFlags], esi; dwAdditionalFlags
0x1800306f7  lea     r8, [rsp+4B0h+FindFileData]; lpFindFileData
0x1800306fc  mov     r9d, 1; fSearchOp
0x180030702  mov     [rsp+4B0h+lpSearchFilter], rsi; lpSearchFilter
0x180030707  xor     edx, edx; fInfoLevelId
0x180030709  lea     rcx, [rbp+3B0h+pszPathIn]; lpFileName
0x180030710  call    cs:__imp_FindFirstFileExW
0x180030716  mov     rbx, rax
0x180030719  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003071d  jz      short loc_18003079C
0x18003071f  cmp     [rsp+4B0h+pszMore], 2Eh ; '.'
0x180030725  jnz     short loc_18003073E
0x180030727  movzx   ecx, [rsp+4B0h+var_452]
0x18003072c  test    cx, cx
0x18003072f  jz      short loc_180030781
0x180030731  cmp     cx, 2Eh ; '.'
0x180030735  jnz     short loc_18003073E
0x180030737  cmp     [rsp+4B0h+var_450], si
0x18003073c  jz      short loc_180030781
0x18003073e  test    [rsp+4B0h+FindFileData], 10h
0x180030743  jz      short loc_180030781
0x180030745  lea     r9, [rsp+4B0h+pszMore]; pszMore
0x18003074a  mov     r8, rdi; pszPathIn
0x18003074d  mov     rdx, r14; cchPathOut
0x180030750  lea     rcx, [rbp+3B0h+pszPathIn]; pszPathOut
0x180030757  call    cs:__imp_PathCchCombine
0x18003075d  test    eax, eax
0x18003075f  js      short loc_180030774
0x180030761  lea     rdx, aLnk; "*.lnk"
0x180030768  lea     rcx, [rbp+3B0h+pszPathIn]; unsigned __int16 *
0x18003076f  call    ?DeleteFilesInTree@@YAXPEBG0@Z; DeleteFilesInTree(ushort const *,ushort const *)
0x180030774  lea     rcx, [rbp+3B0h+pszPathIn]; lpPathName
0x18003077b  call    cs:__imp_RemoveDirectoryW
0x180030781  lea     rdx, [rsp+4B0h+FindFileData]; lpFindFileData
0x180030786  mov     rcx, rbx; hFindFile
0x180030789  call    cs:__imp_FindNextFileW
0x18003078f  test    eax, eax
0x180030791  jnz     short loc_18003071F
0x180030793  mov     rcx, rbx; hFindFile
0x180030796  call    cs:__imp_FindClose
0x18003079c  mov     rcx, [rbp+3B0h+var_20]
0x1800307a3  xor     rcx, rsp; StackCookie
0x1800307a6  call    __security_check_cookie
0x1800307ab  lea     r11, [rsp+4B0h+var_10]
0x1800307b3  mov     rbx, [r11+28h]
0x1800307b7  mov     rsi, [r11+30h]
0x1800307bb  mov     rsp, r11
0x1800307be  pop     r14
0x1800307c0  pop     rdi
0x1800307c1  pop     rbp
0x1800307c2  retn
```
