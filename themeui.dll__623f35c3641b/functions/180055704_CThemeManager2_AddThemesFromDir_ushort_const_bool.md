# CThemeManager2::_AddThemesFromDir(ushort const *,bool)

- ea: `0x180055704`
- end: `0x1800559c4`
- name: `?_AddThemesFromDir@CThemeManager2@@AEAAJPEBG_N@Z`
- size: `704`
- prototype: `__int64 __fastcall(CThemeManager2 *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800311a0`
- `0x180055704`

## callees

- `0x18000dd60`
- `0x180017cc4`
- `0x18001e1ec`
- `0x18001e5d0`
- `0x180030dac`
- `0x1800358c0`
- `0x18003633c`
- `0x180055704`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x180055870`
- `SHLWAPI!PathFindExtensionW` at `0x180055870`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800557ff`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180055823`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005588d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800557ff`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180055823`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005588d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005591d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005591d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1800557a9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1800557a9`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18005595f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18005595f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180055947`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180055947`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180055763`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180055842`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800558bb`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180055763`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180055842`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800558bb`

## pseudocode

```c
__int64 __fastcall CThemeManager2::_AddThemesFromDir(CThemeManager2 *this, const unsigned __int16 *a2, char a3)
{
  const WCHAR *v4; // r9
  HRESULT v7; // ebx
  HANDLE FirstFile; // rsi
  const WCHAR *ExtensionW; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // r8d
  int v13; // r9d
  void *v14; // rdi
  __int64 v15; // rcx
  int lpSearchFilter; // [rsp+20h] [rbp-E0h]
  DWORD dwAdditionalFlags; // [rsp+28h] [rbp-D8h]
  LPVOID pv[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v4 = L"*";
  if ( !a3 )
    v4 = L"*.theme";
  v7 = PathCchCombine(pszPathOut, 0x104u, a2, v4);
  if ( v7 >= 0 )
  {
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    FirstFile = FindFirstFileExW(pszPathOut, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 2u);
    if ( FirstFile != (HANDLE)-1LL )
    {
      while ( 1 )
      {
        if ( v7 < 0 )
        {
LABEL_23:
          FindClose(FirstFile);
          return (unsigned int)v7;
        }
        if ( !a3
          || (FindFileData.dwFileAttributes & 0x10) == 0
          || (FindFileData.dwFileAttributes & 2) != 0
          || CompareStringOrdinal(L".", -1, FindFileData.cFileName, -1, 0) == 2
          || CompareStringOrdinal(L"..", -1, FindFileData.cFileName, -1, 0) == 2 )
        {
          ExtensionW = PathFindExtensionW(FindFileData.cFileName);
          if ( CompareStringOrdinal(ExtensionW, -1, L".theme", -1, 1) == 2
            && (FindFileData.dwFileAttributes & 0x12) == 0 )
          {
            v7 = PathCchCombine(pszPathOut, 0x104u, a2, FindFileData.cFileName);
            if ( v7 >= 0 )
            {
              if ( (unsigned int)IsValidThemeFile(pszPathOut) )
              {
                pv[0] = 0;
                v7 = _AllocString<CTCoAllocPolicy>(v11, v10, pszPathOut, pv);
                if ( v7 >= 0 )
                {
                  v14 = pv[0];
                  if ( (unsigned int)CDPA<unsigned short,CTContainer_PolicyUnOwned<unsigned short>>::SortedInsertPtr(
                                       (int)this + 2112,
                                       (int)pv[0],
                                       v12,
                                       v13,
                                       lpSearchFilter,
                                       dwAdditionalFlags,
                                       pv[0]) != -1 )
                  {
                    v7 = 0;
                    if ( (Microsoft_Windows_ThemeUIEnableBits & 1) != 0 )
                      McTemplateU0z_EtwEventWriteTransfer(v15, ThemeLoaded_Info, pszPathOut);
                    CThemeManager2::_SQMThemeInstalled(this, pszPathOut);
                    goto LABEL_22;
                  }
                  v7 = -2147467259;
                  CoTaskMemFree(v14);
                }
              }
              if ( (Microsoft_Windows_ThemeUIEnableBits & 1) != 0 )
                McTemplateU0z_EtwEventWriteTransfer(v11, ThemeLoadFailed_Info, pszPathOut);
            }
          }
        }
        else
        {
          v7 = PathCchCombine(pszPathOut, 0x104u, a2, FindFileData.cFileName);
          if ( v7 >= 0 )
            v7 = CThemeManager2::_AddThemesFromDir(this, pszPathOut, 0);
        }
LABEL_22:
        if ( !FindNextFileW(FirstFile, &FindFileData) )
          goto LABEL_23;
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180055704  mov     [rsp-8+arg_10], rbx
0x180055709  mov     [rsp-8+arg_18], rsi
0x18005570e  push    rbp
0x18005570f  push    rdi
0x180055710  push    r12
0x180055712  push    r14
0x180055714  push    r15
0x180055716  lea     rbp, [rsp-3C0h]
0x18005571e  sub     rsp, 4C0h
0x180055725  mov     rax, cs:__security_cookie
0x18005572c  xor     rax, rsp
0x18005572f  mov     [rbp+3E0h+var_30], rax
0x180055736  test    r8b, r8b
0x180055739  lea     rax, aTheme_0; "*.theme"
0x180055740  mov     r12b, r8b
0x180055743  lea     r9, asc_1800721E4; "*"
0x18005574a  mov     r15, rdx
0x18005574d  mov     r14, rcx
0x180055750  mov     r8, rdx; pszPathIn
0x180055753  lea     rcx, [rbp+3E0h+pszPathOut]; pszPathOut
0x18005575a  cmovz   r9, rax; pszMore
0x18005575e  mov     edx, 104h; cchPathOut
0x180055763  call    cs:__imp_PathCchCombine
0x180055769  mov     ebx, eax
0x18005576b  test    eax, eax
0x18005576d  js      loc_180055965
0x180055773  xor     edx, edx; Val
0x180055775  lea     rcx, [rsp+4E0h+FindFileData]; void *
0x18005577a  mov     r8d, 250h; Size
0x180055780  call    memset_0
0x180055785  xor     r9d, r9d; fSearchOp
0x180055788  mov     [rsp+4E0h+dwAdditionalFlags], 2; int
0x180055790  lea     r8, [rsp+4E0h+FindFileData]; lpFindFileData
0x180055795  mov     [rsp+4E0h+lpSearchFilter], 0; lpSearchFilter
0x18005579e  lea     rcx, [rbp+3E0h+pszPathOut]; lpFileName
0x1800557a5  lea     edx, [r9+1]; fInfoLevelId
0x1800557a9  call    cs:__imp_FindFirstFileExW
0x1800557af  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800557b3  mov     rsi, rax
0x1800557b6  cmp     rax, rdi
0x1800557b9  jz      loc_180055965
0x1800557bf  test    ebx, ebx
0x1800557c1  js      loc_18005595C
0x1800557c7  test    r12b, r12b
0x1800557ca  jz      loc_18005586B
0x1800557d0  test    [rsp+4E0h+FindFileData], 10h
0x1800557d5  jz      loc_18005586B
0x1800557db  test    [rsp+4E0h+FindFileData], 2
0x1800557e0  jnz     loc_18005586B
0x1800557e6  mov     r9d, edi; cchCount2
0x1800557e9  mov     dword ptr [rsp+4E0h+lpSearchFilter], 0; bIgnoreCase
0x1800557f1  lea     r8, [rsp+4E0h+String2]; lpString2
0x1800557f6  mov     edx, edi; cchCount1
0x1800557f8  lea     rcx, asc_18007A724; "."
0x1800557ff  call    cs:__imp_CompareStringOrdinal
0x180055805  cmp     eax, 2
0x180055808  jz      short loc_18005586B
0x18005580a  mov     r9d, edi; cchCount2
0x18005580d  mov     dword ptr [rsp+4E0h+lpSearchFilter], 0; bIgnoreCase
0x180055815  lea     r8, [rsp+4E0h+String2]; lpString2
0x18005581a  mov     edx, edi; cchCount1
0x18005581c  lea     rcx, asc_18007A2A8; ".."
0x180055823  call    cs:__imp_CompareStringOrdinal
0x180055829  cmp     eax, 2
0x18005582c  jz      short loc_18005586B
0x18005582e  lea     r9, [rsp+4E0h+String2]; pszMore
0x180055833  mov     r8, r15; pszPathIn
0x180055836  mov     edx, 104h; cchPathOut
0x18005583b  lea     rcx, [rbp+3E0h+pszPathOut]; pszPathOut
0x180055842  call    cs:__imp_PathCchCombine
0x180055848  mov     ebx, eax
0x18005584a  test    eax, eax
0x18005584c  js      loc_18005593F
0x180055852  xor     r8d, r8d; bool
0x180055855  lea     rdx, [rbp+3E0h+pszPathOut]; unsigned __int16 *
0x18005585c  mov     rcx, r14; this
0x18005585f  call    ?_AddThemesFromDir@CThemeManager2@@AEAAJPEBG_N@Z; CThemeManager2::_AddThemesFromDir(ushort const *,bool)
0x180055864  mov     ebx, eax
0x180055866  jmp     loc_18005593F
0x18005586b  lea     rcx, [rsp+4E0h+String2]; pszPath
0x180055870  call    cs:__imp_PathFindExtensionW
0x180055876  mov     r9d, edi; cchCount2
0x180055879  mov     dword ptr [rsp+4E0h+lpSearchFilter], 1; int
0x180055881  mov     rcx, rax; lpString1
0x180055884  lea     r8, aTheme; ".theme"
0x18005588b  mov     edx, edi; cchCount1
0x18005588d  call    cs:__imp_CompareStringOrdinal
0x180055893  cmp     eax, 2
0x180055896  jnz     loc_18005593F
0x18005589c  test    [rsp+4E0h+FindFileData], 12h
0x1800558a1  jnz     loc_18005593F
0x1800558a7  lea     r9, [rsp+4E0h+String2]; pszMore
0x1800558ac  mov     r8, r15; pszPathIn
0x1800558af  mov     edx, 104h; cchPathOut
0x1800558b4  lea     rcx, [rbp+3E0h+pszPathOut]; pszPathOut
0x1800558bb  call    cs:__imp_PathCchCombine
0x1800558c1  mov     ebx, eax
0x1800558c3  test    eax, eax
0x1800558c5  js      short loc_18005593F
0x1800558c7  lea     rcx, [rbp+3E0h+pszPathOut]; lpFileName
0x1800558ce  call    ?IsValidThemeFile@@YAHPEBG@Z; IsValidThemeFile(ushort const *)
0x1800558d3  test    eax, eax
0x1800558d5  jz      short loc_180055923
0x1800558d7  lea     r9, [rsp+4E0h+pv]
0x1800558dc  mov     [rsp+4E0h+pv], 0
0x1800558e5  lea     r8, [rbp+3E0h+pszPathOut]
0x1800558ec  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800558f1  mov     ebx, eax
0x1800558f3  test    eax, eax
0x1800558f5  js      short loc_180055923
0x1800558f7  mov     rdi, [rsp+4E0h+pv]
0x1800558fc  lea     rcx, [r14+840h]; int
0x180055903  mov     rdx, rdi; int
0x180055906  mov     [rsp+4E0h+p], rdi; p
0x18005590b  call    ?SortedInsertPtr@?$CDPA@GV?$CTContainer_PolicyUnOwned@G@@@@QEAAHPEBGHP6AH00_J@Z1I0@Z; CDPA<ushort,CTContainer_PolicyUnOwned<ushort>>::SortedInsertPtr(ushort const *,int,int (*)(ushort const *,ushort const *,__int64),__int64,uint,ushort const *)
0x180055910  cmp     eax, 0FFFFFFFFh
0x180055913  jnz     short loc_180055992
0x180055915  mov     rcx, rdi; pv
0x180055918  mov     ebx, 80004005h
0x18005591d  call    cs:__imp_CoTaskMemFree
0x180055923  test    cs:Microsoft_Windows_ThemeUIEnableBits, 1
0x18005592a  jz      short loc_18005593F
0x18005592c  lea     r8, [rbp+3E0h+pszPathOut]
0x180055933  lea     rdx, ThemeLoadFailed_Info
0x18005593a  call    McTemplateU0z_EtwEventWriteTransfer
0x18005593f  lea     rdx, [rsp+4E0h+FindFileData]; lpFindFileData
0x180055944  mov     rcx, rsi; hFindFile
0x180055947  call    cs:__imp_FindNextFileW
0x18005594d  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180055954  test    eax, eax
0x180055956  jnz     loc_1800557BF
0x18005595c  mov     rcx, rsi; hFindFile
0x18005595f  call    cs:__imp_FindClose
0x180055965  mov     eax, ebx
0x180055967  mov     rcx, [rbp+3E0h+var_30]
0x18005596e  xor     rcx, rsp; StackCookie
0x180055971  call    __security_check_cookie
0x180055976  lea     r11, [rsp+4E0h+var_20]
0x18005597e  mov     rbx, [r11+40h]
0x180055982  mov     rsi, [r11+48h]
0x180055986  mov     rsp, r11
0x180055989  pop     r15
0x18005598b  pop     r14
0x18005598d  pop     r12
0x18005598f  pop     rdi
0x180055990  pop     rbp
0x180055991  retn
0x180055992  xor     ebx, ebx
0x180055994  test    cs:Microsoft_Windows_ThemeUIEnableBits, 1
0x18005599b  jz      short loc_1800559B0
0x18005599d  lea     r8, [rbp+3E0h+pszPathOut]
0x1800559a4  lea     rdx, ThemeLoaded_Info
0x1800559ab  call    McTemplateU0z_EtwEventWriteTransfer
0x1800559b0  lea     rdx, [rbp+3E0h+pszPathOut]; unsigned __int16 *
0x1800559b7  mov     rcx, r14; this
0x1800559ba  call    ?_SQMThemeInstalled@CThemeManager2@@AEAAXPEBG@Z; CThemeManager2::_SQMThemeInstalled(ushort const *)
0x1800559bf  jmp     loc_18005593F
```
