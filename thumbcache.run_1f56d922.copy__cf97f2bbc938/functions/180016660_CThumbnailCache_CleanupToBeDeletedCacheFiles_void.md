# CThumbnailCache::_CleanupToBeDeletedCacheFiles(void)

- ea: `0x180016660`
- end: `0x180016806`
- name: `?_CleanupToBeDeletedCacheFiles@CThumbnailCache@@AEAAJXZ`
- size: `422`
- prototype: `__int64 __fastcall(CThumbnailCache *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180015868`

## callees

- `0x18000b3c0`
- `0x180016660`
- `0x18001680c`
- `0x180035830`
- `0x180036100`
- `0x1800364ac`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18001677e`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18001677e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800167d1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800167d1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800166ad`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800166ad`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800167e3`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800167e3`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800167f5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800167f5`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001673e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001673e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180016716`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x1800167c0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180016716`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x1800167c0`

## pseudocode

```c
__int64 __fastcall CThumbnailCache::_CleanupToBeDeletedCacheFiles(CThumbnailCache *this, __int64 a2, unsigned int a3)
{
  int Error; // ebx
  __int64 v6; // rdi
  const WCHAR *v7; // rdx
  HANDLE FirstFileW; // rsi
  BOOL NextFileW; // eax
  _WIN32_FIND_DATAW FindFileData; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR FileName[264]; // [rsp+270h] [rbp+170h] BYREF

  Error = CThumbnailCache::_GetToBeDeletedDirectory(this, FileName, a3);
  if ( Error >= 0 && GetFileAttributesW(FileName) != -1 )
  {
    v6 = -1;
    do
      ++v6;
    while ( FileName[v6] );
    v7 = L"icn*";
    if ( (*((_BYTE *)this + 768) & 2) == 0 )
      v7 = L"thm*";
    if ( !PathAppendW(FileName, v7) )
      return (unsigned int)ResultFromKnownLastError();
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    FirstFileW = FindFirstFileW(FileName, &FindFileData);
    NextFileW = 1;
    if ( FirstFileW != (HANDLE)-1LL )
    {
      while ( NextFileW )
      {
        if ( (unsigned __int64)(2LL * (int)v6) >= 0x208 )
          goto LABEL_21;
        FileName[(int)v6] = 0;
        if ( !PathAppendW(FileName, FindFileData.cFileName) || !DeleteFileW(FileName) )
        {
          Error = ResultFromKnownLastError();
          break;
        }
        NextFileW = FindNextFileW(FirstFileW, &FindFileData);
      }
      FindClose(FirstFileW);
    }
    if ( (unsigned __int64)(2LL * (int)v6) >= 0x208 )
LABEL_21:
      _report_rangecheckfailure();
    FileName[(int)v6] = 0;
    if ( Error >= 0 && !RemoveDirectoryW(FileName) )
      return (unsigned int)ResultFromKnownLastError();
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180016660  mov     [rsp-8+arg_8], rbx
0x180016665  mov     [rsp-8+arg_10], rsi
0x18001666a  push    rbp
0x18001666b  push    rdi
0x18001666c  push    r14
0x18001666e  lea     rbp, [rsp-390h]
0x180016676  sub     rsp, 490h
0x18001667d  mov     rax, cs:__security_cookie
0x180016684  xor     rax, rsp
0x180016687  mov     [rbp+3A0h+var_20], rax
0x18001668e  lea     rdx, [rbp+3A0h+FileName]; unsigned __int16 *
0x180016695  mov     rsi, rcx
0x180016698  call    ?_GetToBeDeletedDirectory@CThumbnailCache@@AEAAJPEAGI@Z; CThumbnailCache::_GetToBeDeletedDirectory(ushort *,uint)
0x18001669d  xor     r14d, r14d
0x1800166a0  mov     ebx, eax
0x1800166a2  test    eax, eax
0x1800166a4  js      short loc_1800166B8
0x1800166a6  lea     rcx, [rbp+3A0h+FileName]; lpFileName
0x1800166ad  call    cs:__imp_GetFileAttributesW
0x1800166b3  cmp     eax, 0FFFFFFFFh
0x1800166b6  jnz     short loc_1800166E1
0x1800166b8  mov     eax, ebx
0x1800166ba  mov     rcx, [rbp+3A0h+var_20]
0x1800166c1  xor     rcx, rsp; StackCookie
0x1800166c4  call    __security_check_cookie
0x1800166c9  lea     r11, [rsp+4A0h+var_10]
0x1800166d1  mov     rbx, [r11+28h]
0x1800166d5  mov     rsi, [r11+30h]
0x1800166d9  mov     rsp, r11
0x1800166dc  pop     r14
0x1800166de  pop     rdi
0x1800166df  pop     rbp
0x1800166e0  retn
0x1800166e1  lea     rax, [rbp+3A0h+FileName]
0x1800166e8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800166ec  inc     rdi
0x1800166ef  cmp     [rax+rdi*2], r14w
0x1800166f4  jnz     short loc_1800166EC
0x1800166f6  test    byte ptr [rsi+300h], 2
0x1800166fd  lea     rax, aThm_0; "thm*"
0x180016704  lea     rdx, aIcn; "icn*"
0x18001670b  cmovz   rdx, rax; pszMore
0x18001670f  lea     rcx, [rbp+3A0h+FileName]; pszPath
0x180016716  call    cs:__imp_PathAppendW
0x18001671c  test    eax, eax
0x18001671e  jz      short loc_18001678C
0x180016720  xor     edx, edx; Val
0x180016722  lea     rcx, [rsp+4A0h+FindFileData]; void *
0x180016727  mov     r8d, 250h; Size
0x18001672d  call    memset_0
0x180016732  lea     rdx, [rsp+4A0h+FindFileData]; lpFindFileData
0x180016737  lea     rcx, [rbp+3A0h+FileName]; lpFileName
0x18001673e  call    cs:__imp_FindFirstFileW
0x180016744  mov     rsi, rax
0x180016747  mov     eax, 1
0x18001674c  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180016750  jnz     short loc_180016798
0x180016752  movsxd  rax, edi
0x180016755  lea     rcx, [rax+rax]
0x180016759  cmp     rcx, 208h
0x180016760  jnb     loc_180016800
0x180016766  mov     [rbp+rcx+3A0h+FileName], r14w
0x18001676f  test    ebx, ebx
0x180016771  js      loc_1800166B8
0x180016777  lea     rcx, [rbp+3A0h+FileName]; lpPathName
0x18001677e  call    cs:__imp_RemoveDirectoryW
0x180016784  test    eax, eax
0x180016786  jnz     loc_1800166B8
0x18001678c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180016791  mov     ebx, eax
0x180016793  jmp     loc_1800166B8
0x180016798  test    eax, eax
0x18001679a  jz      short loc_1800167F2
0x18001679c  movsxd  rcx, edi
0x18001679f  add     rcx, rcx
0x1800167a2  cmp     rcx, 208h
0x1800167a9  jnb     short loc_180016800
0x1800167ab  mov     [rbp+rcx+3A0h+FileName], r14w
0x1800167b4  lea     rdx, [rsp+4A0h+FindFileData.cFileName]; pszMore
0x1800167b9  lea     rcx, [rbp+3A0h+FileName]; pszPath
0x1800167c0  call    cs:__imp_PathAppendW
0x1800167c6  test    eax, eax
0x1800167c8  jz      short loc_1800167EB
0x1800167ca  lea     rcx, [rbp+3A0h+FileName]; lpFileName
0x1800167d1  call    cs:__imp_DeleteFileW
0x1800167d7  test    eax, eax
0x1800167d9  jz      short loc_1800167EB
0x1800167db  lea     rdx, [rsp+4A0h+FindFileData]; lpFindFileData
0x1800167e0  mov     rcx, rsi; hFindFile
0x1800167e3  call    cs:__imp_FindNextFileW
0x1800167e9  jmp     short loc_180016798
0x1800167eb  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800167f0  mov     ebx, eax
0x1800167f2  mov     rcx, rsi; hFindFile
0x1800167f5  call    cs:__imp_FindClose
0x1800167fb  jmp     loc_180016752
0x180016800  call    __report_rangecheckfailure
```
