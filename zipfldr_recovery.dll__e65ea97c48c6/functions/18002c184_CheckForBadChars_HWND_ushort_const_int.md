# CheckForBadChars(HWND__ *,ushort const *,int)

- ea: `0x18002c184`
- end: `0x18002c46c`
- name: `?CheckForBadChars@@YAHPEAUHWND__@@PEBGH@Z`
- size: `744`
- prototype: `__int64 __fastcall(HWND, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18000b430`
- `0x18002c184`

## callees

- `0x180010c30`
- `0x180021b4c`
- `0x180028c2c`
- `0x18002c184`
- `0x180036f50`
- `0x180037958`
- `0x18003ef3c`
- `0x180040a68`
- `0x180040b24`

## import_xrefs

- `SHLWAPI!PathRemoveFileSpecW` at `0x18002c1dc`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18002c1dc`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18002c264`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18002c3ea`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18002c42a`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18002c264`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18002c3ea`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18002c42a`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002c309`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002c32f`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002c397`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002c309`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002c32f`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002c397`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002c290`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002c290`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002c35b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002c35b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002c43a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002c43a`

## pseudocode

```c
__int64 __fastcall CheckForBadChars(HWND a1, const unsigned __int16 *a2, int a3)
{
  __int64 v6; // rcx
  unsigned int v7; // ebx
  HANDLE FirstFileW; // r12
  int v9; // r15d
  __int64 v10; // rcx
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v13[8]; // [rsp+290h] [rbp+190h] BYREF
  __int128 v14; // [rsp+2A0h] [rbp+1A0h]
  WCHAR pszPath[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR FileName[264]; // [rsp+4C0h] [rbp+3C0h] BYREF
  WCHAR v17[264]; // [rsp+6D0h] [rbp+5D0h] BYREF

  StringCchCopyW(pszPath, 0x104u, a2);
  PathRemoveFileSpecW(pszPath);
  *(_OWORD *)v13 = 0;
  v14 = 0;
  if ( a3 && !(unsigned int)IsPathMappable(pszPath, v13, 16) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
      MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short___unsigned_short___(v6, a1);
    else
      ShellMessageBoxW(g_hmodThisDll, a1, (LPCWSTR)0x28B3, (LPCWSTR)0x2747, 0x30u, pszPath, v13);
    return 0;
  }
  v7 = 1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(a2, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
    return v7;
  while ( 1 )
  {
    if ( (unsigned int)PathIsDotOrDotDotW(FindFileData.cFileName) )
      goto LABEL_15;
    if ( !(unsigned int)IsPathMappable(FindFileData.cFileName, v13, 16) )
      break;
    if ( (int)StringCchCopyW(FileName, 0x104u, pszPath) < 0
      || PathCchAppend(FileName, 0x104u, FindFileData.cFileName) < 0 )
    {
      goto LABEL_24;
    }
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
    {
      if ( PathCchAppend(FileName, 0x104u, L"*.*") < 0 )
        goto LABEL_24;
      if ( !(unsigned int)CheckForBadChars(a1, FileName, 0) )
      {
        v7 = 0;
        goto LABEL_27;
      }
    }
LABEL_15:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
      goto LABEL_27;
  }
  v9 = 1;
  if ( (int)StringCchCopyW(v17, 0x104u, pszPath) >= 0 && PathCchAppend(v17, 0x104u, FindFileData.cFileName) >= 0 )
  {
    v9 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
      MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short___unsigned_short___(v10, a1);
    else
      ShellMessageBoxW(g_hmodThisDll, a1, (LPCWSTR)0x28B3, (LPCWSTR)0x2747, 0x30u, v17, v13);
  }
  v7 = 0;
  if ( v9 )
  {
LABEL_24:
    v7 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
      MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short___(
        g_hmodThisDll,
        a1,
        (LPCWSTR)0x28B4,
        (LPCWSTR)0x2747,
        0x30u,
        (__int64)FindFileData.cFileName);
    else
      ShellMessageBoxW(g_hmodThisDll, a1, (LPCWSTR)0x28B4, (LPCWSTR)0x2747, 0x30u, FindFileData.cFileName);
  }
LABEL_27:
  FindClose(FirstFileW);
  return v7;
}

```

## disassembly

```asm
0x18002c184  mov     [rsp-8+arg_10], rbx
0x18002c189  push    rbp
0x18002c18a  push    rsi
0x18002c18b  push    rdi
0x18002c18c  push    r12
0x18002c18e  push    r13
0x18002c190  push    r14
0x18002c192  push    r15
0x18002c194  lea     rbp, [rsp-7F0h]
0x18002c19c  sub     rsp, 8F0h
0x18002c1a3  mov     rax, cs:__security_cookie
0x18002c1aa  xor     rax, rsp
0x18002c1ad  mov     [rbp+820h+var_40], rax
0x18002c1b4  mov     ebx, r8d
0x18002c1b7  mov     rsi, rdx
0x18002c1ba  mov     r8, rdx; unsigned __int16 *
0x18002c1bd  mov     rdi, rcx
0x18002c1c0  mov     r13d, 104h
0x18002c1c6  lea     rcx, [rbp+820h+pszPath]; unsigned __int16 *
0x18002c1cd  mov     edx, r13d; unsigned __int64
0x18002c1d0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002c1d5  lea     rcx, [rbp+820h+pszPath]; pszPath
0x18002c1dc  call    cs:__imp_PathRemoveFileSpecW
0x18002c1e2  xorps   xmm0, xmm0
0x18002c1e5  mov     r15d, 10h
0x18002c1eb  movups  xmmword ptr [rbp+820h+var_690], xmm0
0x18002c1f2  movups  [rbp+820h+var_680], xmm0
0x18002c1f9  test    ebx, ebx
0x18002c1fb  jz      short loc_18002C271
0x18002c1fd  mov     r8d, r15d; int
0x18002c200  lea     rdx, [rbp+820h+var_690]; unsigned __int16 *
0x18002c207  lea     rcx, [rbp+820h+pszPath]; unsigned __int16 *
0x18002c20e  call    ?IsPathMappable@@YAHPEBGPEAGH@Z; IsPathMappable(ushort const *,ushort *,int)
0x18002c213  test    eax, eax
0x18002c215  jnz     short loc_18002C271
0x18002c217  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x18002c21e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x18002c223  test    al, al
0x18002c225  mov     rdx, rdi; hWnd
0x18002c228  lea     rax, [rbp+820h+var_690]
0x18002c22f  mov     [rsp+920h+var_8F0], rax
0x18002c234  lea     rax, [rbp+820h+pszPath]
0x18002c23b  mov     [rsp+920h+var_8F8], rax
0x18002c240  jz      short loc_18002C249
0x18002c242  call    MessageBoxHelper__ShellMessageBoxTextScaled_unsigned_short___unsigned_short___
0x18002c247  jmp     short loc_18002C26A
0x18002c249  mov     rcx, cs:g_hmodThisDll; hAppInst
0x18002c250  mov     r9d, 2747h; lpcTitle
0x18002c256  mov     r8d, 28B3h; lpcText
0x18002c25c  mov     [rsp+920h+fuStyle], 30h ; '0'; fuStyle
0x18002c264  call    cs:__imp_ShellMessageBoxW
0x18002c26a  xor     ebx, ebx
0x18002c26c  jmp     loc_18002C440
0x18002c271  xor     edx, edx; Val
0x18002c273  lea     rcx, [rsp+920h+FindFileData]; void *
0x18002c278  mov     r8d, 250h; Size
0x18002c27e  mov     ebx, 1
0x18002c283  call    memset_0
0x18002c288  lea     rdx, [rsp+920h+FindFileData]; lpFindFileData
0x18002c28d  mov     rcx, rsi; lpFileName
0x18002c290  call    cs:__imp_FindFirstFileW
0x18002c296  mov     r12, rax
0x18002c299  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002c29d  jz      loc_18002C440
0x18002c2a3  lea     rcx, [rsp+920h+FindFileData.cFileName]; unsigned __int16 *
0x18002c2a8  call    ?PathIsDotOrDotDotW@@YAHPEBG@Z; PathIsDotOrDotDotW(ushort const *)
0x18002c2ad  test    eax, eax
0x18002c2af  jnz     loc_18002C353
0x18002c2b5  mov     r8d, r15d; int
0x18002c2b8  lea     rdx, [rbp+820h+var_690]; unsigned __int16 *
0x18002c2bf  lea     rcx, [rsp+920h+FindFileData.cFileName]; unsigned __int16 *
0x18002c2c4  call    ?IsPathMappable@@YAHPEBGPEAGH@Z; IsPathMappable(ushort const *,ushort *,int)
0x18002c2c9  lea     r8, [rbp+820h+pszPath]; unsigned __int16 *
0x18002c2d0  mov     esi, 30h ; '0'
0x18002c2d5  mov     r14d, 2747h
0x18002c2db  mov     rdx, r13; unsigned __int64
0x18002c2de  test    eax, eax
0x18002c2e0  jz      loc_18002C375
0x18002c2e6  lea     rcx, [rbp+820h+FileName]; unsigned __int16 *
0x18002c2ed  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002c2f2  test    eax, eax
0x18002c2f4  js      loc_18002C3F7
0x18002c2fa  lea     r8, [rsp+920h+FindFileData.cFileName]; pszMore
0x18002c2ff  mov     rdx, r13; cchPath
0x18002c302  lea     rcx, [rbp+820h+FileName]; pszPath
0x18002c309  call    cs:__imp_PathCchAppend
0x18002c30f  test    eax, eax
0x18002c311  js      loc_18002C3F7
0x18002c317  test    byte ptr [rsp+920h+FindFileData.dwFileAttributes], r15b
0x18002c31c  jz      short loc_18002C353
0x18002c31e  lea     r8, pszMore; "*.*"
0x18002c325  mov     rdx, r13; cchPath
0x18002c328  lea     rcx, [rbp+820h+FileName]; pszPath
0x18002c32f  call    cs:__imp_PathCchAppend
0x18002c335  test    eax, eax
0x18002c337  js      loc_18002C3F7
0x18002c33d  xor     r8d, r8d; int
0x18002c340  lea     rdx, [rbp+820h+FileName]; unsigned __int16 *
0x18002c347  mov     rcx, rdi; HWND
0x18002c34a  call    ?CheckForBadChars@@YAHPEAUHWND__@@PEBGH@Z; CheckForBadChars(HWND__ *,ushort const *,int)
0x18002c34f  test    eax, eax
0x18002c351  jz      short loc_18002C36E
0x18002c353  lea     rdx, [rsp+920h+FindFileData]; lpFindFileData
0x18002c358  mov     rcx, r12; hFindFile
0x18002c35b  call    cs:__imp_FindNextFileW
0x18002c361  test    eax, eax
0x18002c363  jnz     loc_18002C2A3
0x18002c369  jmp     loc_18002C437
0x18002c36e  xor     ebx, ebx
0x18002c370  jmp     loc_18002C437
0x18002c375  lea     rcx, [rbp+820h+var_250]; unsigned __int16 *
0x18002c37c  mov     r15d, ebx
0x18002c37f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002c384  test    eax, eax
0x18002c386  js      short loc_18002C3F0
0x18002c388  lea     r8, [rsp+920h+FindFileData.cFileName]; pszMore
0x18002c38d  mov     rdx, r13; cchPath
0x18002c390  lea     rcx, [rbp+820h+var_250]; pszPath
0x18002c397  call    cs:__imp_PathCchAppend
0x18002c39d  test    eax, eax
0x18002c39f  js      short loc_18002C3F0
0x18002c3a1  xor     r15d, r15d
0x18002c3a4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x18002c3ab  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x18002c3b0  test    al, al
0x18002c3b2  mov     rdx, rdi; hWnd
0x18002c3b5  lea     rax, [rbp+820h+var_690]
0x18002c3bc  mov     [rsp+920h+var_8F0], rax
0x18002c3c1  lea     rax, [rbp+820h+var_250]
0x18002c3c8  mov     [rsp+920h+var_8F8], rax
0x18002c3cd  jz      short loc_18002C3D6
0x18002c3cf  call    MessageBoxHelper__ShellMessageBoxTextScaled_unsigned_short___unsigned_short___
0x18002c3d4  jmp     short loc_18002C3F0
0x18002c3d6  mov     rcx, cs:g_hmodThisDll; hAppInst
0x18002c3dd  mov     r9, r14; lpcTitle
0x18002c3e0  mov     r8d, 28B3h; lpcText
0x18002c3e6  mov     [rsp+920h+fuStyle], esi; fuStyle
0x18002c3ea  call    cs:__imp_ShellMessageBoxW
0x18002c3f0  xor     ebx, ebx
0x18002c3f2  test    r15d, r15d
0x18002c3f5  jz      short loc_18002C437
0x18002c3f7  xor     ebx, ebx
0x18002c3f9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x18002c400  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x18002c405  mov     rcx, cs:g_hmodThisDll; hAppInst
0x18002c40c  test    al, al
0x18002c40e  lea     rax, [rsp+920h+FindFileData.cFileName]
0x18002c413  mov     r9, r14; lpcTitle
0x18002c416  mov     [rsp+920h+var_8F8], rax; __int64
0x18002c41b  mov     r8d, 28B4h; lpcText
0x18002c421  mov     [rsp+920h+fuStyle], esi; UINT
0x18002c425  mov     rdx, rdi; hWnd
0x18002c428  jnz     short loc_18002C432
0x18002c42a  call    cs:__imp_ShellMessageBoxW
0x18002c430  jmp     short loc_18002C437
0x18002c432  call    MessageBoxHelper__ShellMessageBoxTextScaled_unsigned_short___
0x18002c437  mov     rcx, r12; hFindFile
0x18002c43a  call    cs:__imp_FindClose
0x18002c440  mov     eax, ebx
0x18002c442  mov     rcx, [rbp+820h+var_40]
0x18002c449  xor     rcx, rsp; StackCookie
0x18002c44c  call    __security_check_cookie
0x18002c451  mov     rbx, [rsp+920h+arg_10]
0x18002c459  add     rsp, 8F0h
0x18002c460  pop     r15
0x18002c462  pop     r14
0x18002c464  pop     r13
0x18002c466  pop     r12
0x18002c468  pop     rdi
0x18002c469  pop     rsi
0x18002c46a  pop     rbp
0x18002c46b  retn
```
