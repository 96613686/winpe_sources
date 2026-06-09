# ExpandThemeTokens(ushort const *,ushort *,int)

- ea: `0x18000d490`
- end: `0x18000db19`
- name: `?ExpandThemeTokens@@YAJPEBGPEAGH@Z`
- size: `1673`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `11`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800090e0`
- `0x1800097b0`
- `0x180009bd0`
- `0x180009ea0`
- `0x18000a760`
- `0x18000ab90`
- `0x18000b78c`
- `0x180013af0`
- `0x180013e50`
- `0x1800311a0`
- `0x18005fb24`

## callees

- `0x18000ab10`
- `0x18000bb40`
- `0x18000d490`
- `0x18000db20`
- `0x18000db58`
- `0x18000dbcc`
- `0x18000ee20`
- `0x180015660`
- `0x18001ec70`
- `0x180020d5c`
- `0x1800358c0`
- `0x18003633c`
- `0x1800505ec`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x18000d777`
- `SHLWAPI!PathFindFileNameW` at `0x18000d777`
- `SHLWAPI!PathFileExistsW` at `0x18000d7d5`
- `SHLWAPI!PathFileExistsW` at `0x18000d8aa`
- `SHLWAPI!PathFileExistsW` at `0x18000da83`
- `SHLWAPI!PathFileExistsW` at `0x18000d7d5`
- `SHLWAPI!PathFileExistsW` at `0x18000d8aa`
- `SHLWAPI!PathFileExistsW` at `0x18000da83`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18000dab5`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18000dab5`
- `SHLWAPI!StrCmpNIW` at `0x18000d5d8`
- `SHLWAPI!StrCmpNIW` at `0x18000d5d8`
- `SHLWAPI!PathAppendW` at `0x18000d6c2`
- `SHLWAPI!PathAppendW` at `0x18000d6c2`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsForUserW` at `0x18000d6e5`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsForUserW` at `0x18000d6e5`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18000d9e4`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18000d9e4`
- `GDI32!GetDeviceCaps` at `0x18000da1c`
- `GDI32!GetDeviceCaps` at `0x18000da1c`
- `USER32!ReleaseDC` at `0x18000da27`
- `USER32!ReleaseDC` at `0x18000da27`
- `USER32!GetDC` at `0x18000da0b`
- `USER32!GetDC` at `0x18000da0b`

## pseudocode

```c
int __fastcall ExpandThemeTokens(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  __int64 v4; // rdi
  WCHAR *v5; // r8
  __int64 v6; // rcx
  unsigned __int16 *v7; // rdx
  __int64 v8; // r9
  bool v9; // zf
  WCHAR *v10; // rcx
  unsigned __int16 *v11; // rdx
  __int64 v12; // r9
  unsigned __int16 *v13; // r8
  __int64 v14; // rcx
  unsigned __int16 *v15; // rcx
  __int64 v16; // rsi
  unsigned int i; // r14d
  __int64 v18; // r8
  __int64 v19; // rbx
  const WCHAR *v20; // rcx
  __int64 v21; // rcx
  WCHAR *v22; // rdx
  __int64 v23; // r9
  __m256i *v24; // r8
  __m256i *v25; // rcx
  unsigned __int16 * near *v26; // rcx
  __m256i *v27; // rax
  __int64 v28; // r8
  WCHAR *v29; // rdx
  WCHAR *v30; // rcx
  int result; // eax
  WCHAR *v32; // rcx
  __int64 v33; // rdx
  char v34; // bl
  const WCHAR *v35; // rax
  const unsigned __int16 *v36; // rax
  __int64 v37; // rdx
  unsigned int v38; // edx
  char v39; // bl
  const WCHAR *v40; // rax
  const unsigned __int16 *v41; // rax
  unsigned int v42; // edx
  __int64 v43; // rcx
  const wchar_t *v44; // r9
  WCHAR *v45; // rdx
  __int64 v46; // r8
  __int64 v47; // rax
  WCHAR *v48; // rax
  __int64 v49; // rdx
  HDC DC; // rbx
  __int64 v51; // rax
  int v52; // [rsp+20h] [rbp-E0h]
  char v53[8]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v54[40]; // [rsp+38h] [rbp-C8h] BYREF
  __m256i v55; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v56; // [rsp+80h] [rbp-80h]
  _BYTE v57[22]; // [rsp+90h] [rbp-70h]
  char v58[458]; // [rsp+A6h] [rbp-5Ah] BYREF
  WCHAR psz2[264]; // [rsp+270h] [rbp+170h] BYREF
  unsigned __int16 v60[264]; // [rsp+480h] [rbp+380h] BYREF
  WCHAR pszPath[264]; // [rsp+690h] [rbp+590h] BYREF

  memset_0(psz2, 0, 0x208u);
  memset_0(v60, 0, 0x208u);
  v4 = 2147483646;
  v5 = psz2;
  v6 = 2147483646;
  v7 = a2;
  v8 = 260;
  do
  {
    if ( !v6 )
      break;
    if ( !*v7 )
      break;
    *v5++ = *v7++;
    --v6;
    --v8;
  }
  while ( v8 );
  v9 = v8 == 0;
  v10 = v5 - 1;
  v11 = a2;
  v12 = 260;
  if ( !v9 )
    v10 = v5;
  v13 = v60;
  *v10 = 0;
  v14 = 2147483646;
  do
  {
    if ( !v14 )
      break;
    if ( !*v11 )
      break;
    *v13++ = *v11++;
    --v14;
    --v12;
  }
  while ( v12 );
  v15 = v13 - 1;
  v16 = -1;
  if ( v12 )
    v15 = v13;
  v9 = dword_18008B4F8 == 0;
  *v15 = 0;
  if ( v9 )
  {
    dword_18008B4F8 = 1;
    if ( !GetWindowsDirectoryW(&g_szWinDir, 0x104u) )
      g_szWinDir = 0;
    StringCchCopyW(&g_szThemeDir, 0x104u, &g_szWinDir);
    DC = GetDC(0);
    GetDeviceCaps(DC, 12);
    ReleaseDC(0, DC);
    StringCchCopyW(&g_szCurDir, 0x105u, &g_szThemeDir);
    if ( g_szWinDir )
    {
      v51 = -1;
      do
        v9 = *(&g_szWinDir + ++v51) == 0;
      while ( !v9 );
      if ( *(&g_szWinDir + v51 - 1) != 92 )
      {
        v49 = 260;
        v48 = &g_szWinDir;
        do
        {
          if ( !*v48 )
            break;
          ++v48;
          --v49;
        }
        while ( v49 );
        v43 = 260 - v49;
        if ( v49 )
        {
          v44 = L"\\";
          v45 = &g_szWinDir + v43;
          v46 = 2147483646;
          v47 = 260 - v43;
          if ( v43 != 260 )
          {
            do
            {
              if ( !v46 )
                break;
              if ( !*v44 )
                break;
              *v45++ = *v44++;
              --v46;
              --v47;
            }
            while ( v47 );
          }
          v32 = v45 - 1;
          if ( v47 )
            v32 = v45;
          *v32 = 0;
        }
      }
    }
    if ( HandGet(HKEY_CURRENT_USER, L"Software\\Microsoft\\Plus!\\Themes\\Current", 0, &g_szMsg) )
    {
      StringCchCopyW(&g_szCurDir, 0x105u, &g_szMsg);
      *PathFindFileNameW(&g_szCurDir) = 0;
    }
    v34 = 0;
    LOBYTE(v33) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AUTest>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_AUTest>::GetImpl'::`2'::impl,
      v33);
    winrt::param::hstring::hstring((winrt::param::hstring *)v54, L"CustomThemeRTM");
    winrt::WindowsUdk::Management::Deployment::PackageManager::FindAssetReferencePath((const struct winrt::param::hstring *)v53);
    if ( *(_QWORD *)(winrt::hstring::operator std::basic_string_view<unsigned short>(v53, v54) + 8) )
    {
      v35 = winrt::hstring::c_str((winrt::hstring *)v53);
      if ( PathFileExistsW(v35) )
      {
        v36 = winrt::hstring::c_str((winrt::hstring *)v53);
        StringCchCopyW(&g_szLiftedThemeDir, 0x104u, v36);
        v34 = 1;
      }
    }
    winrt::handle_type<winrt::impl::hstring_traits>::close(v53);
    if ( !v34 )
    {
      *(_OWORD *)v55.m256i_i8 = *(_OWORD *)L"%ResourceDir%";
      *(_OWORD *)((char *)&v55.m256i_u64[1] + 4) = *(_OWORD *)L"rceDir%";
      memset_0((char *)&v55.m256i_u64[3] + 4, 0, 0x1ECu);
      ExpandResourceDir((unsigned __int16 *)&v55, v38);
      StringCchCopyW(&g_szLiftedThemeDir, 0x104u, (const unsigned __int16 *)&v55);
    }
    v39 = 0;
    LOBYTE(v37) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AUTest>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_AUTest>::GetImpl'::`2'::impl,
      v37);
    winrt::param::hstring::hstring((winrt::param::hstring *)v54, L"CustomThemeBackgrounds");
    winrt::WindowsUdk::Management::Deployment::PackageManager::FindAssetReferencePath((const struct winrt::param::hstring *)v53);
    if ( *(_QWORD *)(winrt::hstring::operator std::basic_string_view<unsigned short>(v53, v54) + 8) )
    {
      v40 = winrt::hstring::c_str((winrt::hstring *)v53);
      if ( PathFileExistsW(v40) )
      {
        v41 = winrt::hstring::c_str((winrt::hstring *)v53);
        StringCchCopyW(&g_szLiftedWallpaperDir, 0x104u, v41);
        v39 = 1;
      }
    }
    winrt::handle_type<winrt::impl::hstring_traits>::close(v53);
    if ( !v39 )
    {
      v55 = *(__m256i *)L"%SystemRoot%\\web\\wallpaper\\Windows";
      v56 = *(_OWORD *)L"\\wallpaper\\Windows";
      *(_OWORD *)v57 = *(_OWORD *)L"er\\Windows";
      *(_QWORD *)&v57[14] = *(_QWORD *)L"ows";
      memset_0(v58, 0, 0x1C2u);
      ExpandResourceDir((unsigned __int16 *)&v55, v42);
      StringCchCopyW(&g_szLiftedWallpaperDir, 0x104u, (const unsigned __int16 *)&v55);
    }
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= 5 )
      goto LABEL_36;
    v18 = -1;
    v19 = (int)i;
    v20 = (const WCHAR *)(&g_pszThemeTokens)[v19];
    do
      ++v18;
    while ( v20[v18] );
    if ( !StrCmpNIW(v20, psz2, v18 - 1) )
      break;
  }
  _mm_lfence();
  v21 = 2147483646;
  v22 = psz2;
  v23 = 260;
  v24 = &v55;
  do
  {
    if ( !v21 )
      break;
    if ( !*v22 )
      break;
    v24->m256i_i16[0] = *v22++;
    v24 = (__m256i *)((char *)v24 + 2);
    --v21;
    --v23;
  }
  while ( v23 );
  v25 = (__m256i *)((char *)v24 - 2);
  if ( v23 )
    v25 = v24;
  v25->m256i_i16[0] = 0;
  v26 = (&g_pszThemeValues)[v19];
  _mm_lfence();
  do
    v9 = *((_WORD *)(&g_pszThemeTokens)[v19] + ++v16) == 0;
  while ( !v9 );
  v27 = &v55;
  v28 = 260;
  if ( v55.m256i_i16[v16] == 92 )
    v27 = (__m256i *)&v55.m256i_i16[1];
  v29 = psz2;
  do
  {
    if ( !v4 )
      break;
    if ( !*(_WORD *)v26 )
      break;
    *v29 = *(_WORD *)v26;
    v26 = (unsigned __int16 * near *)((char *)v26 + 2);
    ++v29;
    --v4;
    --v28;
  }
  while ( v28 );
  v30 = v29 - 1;
  if ( v28 )
    v30 = v29;
  *v30 = 0;
  PathAppendW(psz2, (LPCWSTR)v27 + v16);
  if ( i
    || PathFileExistsW(psz2)
    || !a1
    || (StringCchCopyW(pszPath, 0x104u, a1),
        PathRemoveFileSpecW(pszPath),
        StringCchCopyW((unsigned __int16 *)&v55, 0x104u, v60),
        result = ReplaceStringToken(
                   (const unsigned __int16 *)&v55,
                   (const unsigned __int16 *)(&g_pszThemeTokens)[v19],
                   pszPath,
                   psz2,
                   v52),
        result >= 0) )
  {
LABEL_36:
    if ( (unsigned int)SHExpandEnvironmentStringsForUserW(0, psz2, a2, 260) )
    {
      return 0;
    }
    else
    {
      StringCchCopyW(a2, 0x104u, psz2);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000d490  push    rbp
0x18000d492  push    rsi
0x18000d493  push    rdi
0x18000d494  push    r12
0x18000d496  push    r13
0x18000d498  push    r14
0x18000d49a  push    r15
0x18000d49c  lea     rbp, [rsp-7B0h]
0x18000d4a4  sub     rsp, 8B0h
0x18000d4ab  mov     rax, cs:__security_cookie
0x18000d4b2  xor     rax, rsp
0x18000d4b5  mov     [rbp+7E0h+var_40], rax
0x18000d4bc  mov     r15, rdx
0x18000d4bf  mov     r12, rcx
0x18000d4c2  xor     edx, edx; Val
0x18000d4c4  lea     rcx, [rbp+7E0h+psz2]; void *
0x18000d4cb  mov     r8d, 208h; Size
0x18000d4d1  call    memset_0
0x18000d4d6  xor     edx, edx; Val
0x18000d4d8  lea     rcx, [rbp+7E0h+var_460]; void *
0x18000d4df  mov     r8d, 208h; Size
0x18000d4e5  call    memset_0
0x18000d4ea  mov     edi, 7FFFFFFEh
0x18000d4ef  lea     r8, [rbp+7E0h+psz2]
0x18000d4f6  mov     ecx, edi
0x18000d4f8  mov     rdx, r15
0x18000d4fb  mov     r9d, 104h
0x18000d501  test    rcx, rcx
0x18000d504  jz      short loc_18000D523
0x18000d506  movzx   eax, word ptr [rdx]
0x18000d509  test    ax, ax
0x18000d50c  jz      short loc_18000D523
0x18000d50e  mov     [r8], ax
0x18000d512  add     rdx, 2
0x18000d516  add     r8, 2
0x18000d51a  dec     rcx
0x18000d51d  sub     r9, 1
0x18000d521  jnz     short loc_18000D501
0x18000d523  test    r9, r9
0x18000d526  lea     rcx, [r8-2]
0x18000d52a  mov     rdx, r15
0x18000d52d  mov     r9d, 104h
0x18000d533  cmovnz  rcx, r8
0x18000d537  xor     eax, eax
0x18000d539  lea     r8, [rbp+7E0h+var_460]
0x18000d540  mov     [rcx], ax
0x18000d543  mov     rcx, rdi
0x18000d546  test    rcx, rcx
0x18000d549  jz      short loc_18000D568
0x18000d54b  movzx   eax, word ptr [rdx]
0x18000d54e  test    ax, ax
0x18000d551  jz      short loc_18000D568
0x18000d553  mov     [r8], ax
0x18000d557  add     rdx, 2
0x18000d55b  add     r8, 2
0x18000d55f  dec     rcx
0x18000d562  sub     r9, 1
0x18000d566  jnz     short loc_18000D546
0x18000d568  test    r9, r9
0x18000d56b  mov     [rsp+8E0h+arg_10], rbx
0x18000d573  lea     rcx, [r8-2]
0x18000d577  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18000d57e  cmovnz  rcx, r8
0x18000d582  mov     r13d, 5Ch ; '\'
0x18000d588  xor     eax, eax
0x18000d58a  cmp     cs:dword_18008B4F8, eax
0x18000d590  mov     [rcx], ax
0x18000d593  jz      loc_18000D9CB
0x18000d599  xor     r14d, r14d
0x18000d59c  lea     r13, __ImageBase
0x18000d5a3  cmp     r14d, 5
0x18000d5a7  jnb     loc_18000D6D1
0x18000d5ad  movsxd  rax, r14d
0x18000d5b0  mov     r8, rsi
0x18000d5b3  lea     rbx, ds:0[rax*8]
0x18000d5bb  mov     rcx, [rbx+r13+6FFC0h]; psz1
0x18000d5c3  inc     r8
0x18000d5c6  cmp     word ptr [rcx+r8*2], 0
0x18000d5cc  jnz     short loc_18000D5C3
0x18000d5ce  dec     r8d; nChar
0x18000d5d1  lea     rdx, [rbp+7E0h+psz2]; psz2
0x18000d5d8  call    cs:__imp_StrCmpNIW
0x18000d5de  test    eax, eax
0x18000d5e0  jnz     loc_18000D71F
0x18000d5e6  lfence
0x18000d5e9  mov     rcx, rdi
0x18000d5ec  lea     rdx, [rbp+7E0h+psz2]
0x18000d5f3  mov     r9d, 104h
0x18000d5f9  lea     r8, [rsp+8E0h+var_880]
0x18000d5fe  xchg    ax, ax
0x18000d600  test    rcx, rcx
0x18000d603  jz      short loc_18000D622
0x18000d605  movzx   eax, word ptr [rdx]
0x18000d608  test    ax, ax
0x18000d60b  jz      short loc_18000D622
0x18000d60d  mov     [r8], ax
0x18000d611  add     rdx, 2
0x18000d615  add     r8, 2
0x18000d619  dec     rcx
0x18000d61c  sub     r9, 1
0x18000d620  jnz     short loc_18000D600
0x18000d622  test    r9, r9
0x18000d625  lea     rcx, [r8-2]
0x18000d629  cmovnz  rcx, r8
0x18000d62d  xor     eax, eax
0x18000d62f  mov     [rcx], ax
0x18000d632  mov     rcx, [rbx+r13+6FFE8h]
0x18000d63a  lfence
0x18000d63d  mov     rax, [rbx+r13+6FFC0h]
0x18000d645  nop     word ptr [rax+rax+00000000h]
0x18000d650  cmp     word ptr [rax+rsi*2+2], 0
0x18000d656  lea     rsi, [rsi+1]
0x18000d65a  jnz     short loc_18000D650
0x18000d65c  mov     r8d, 5Ch ; '\'
0x18000d662  lea     rdx, [rsp+8E0h+var_880+2]
0x18000d667  cmp     r8w, [rsp+rsi*2+8E0h+var_880]
0x18000d66d  lea     rax, [rsp+8E0h+var_880]
0x18000d672  mov     r8d, 104h
0x18000d678  cmovz   rax, rdx
0x18000d67c  lea     rdx, [rbp+7E0h+psz2]
0x18000d683  lea     r9, [rax+rsi*2]
0x18000d687  test    rdi, rdi
0x18000d68a  jz      short loc_18000D6A8
0x18000d68c  movzx   eax, word ptr [rcx]
0x18000d68f  test    ax, ax
0x18000d692  jz      short loc_18000D6A8
0x18000d694  mov     [rdx], ax
0x18000d697  add     rcx, 2
0x18000d69b  add     rdx, 2
0x18000d69f  dec     rdi
0x18000d6a2  sub     r8, 1
0x18000d6a6  jnz     short loc_18000D687
0x18000d6a8  lea     rcx, [rdx-2]
0x18000d6ac  test    r8, r8
0x18000d6af  cmovnz  rcx, rdx
0x18000d6b3  xor     eax, eax
0x18000d6b5  mov     rdx, r9; pszMore
0x18000d6b8  mov     [rcx], ax
0x18000d6bb  lea     rcx, [rbp+7E0h+psz2]; pszPath
0x18000d6c2  call    cs:__imp_PathAppendW
0x18000d6c8  test    r14d, r14d
0x18000d6cb  jz      loc_18000DA7C
0x18000d6d1  mov     r9d, 104h
0x18000d6d7  lea     rdx, [rbp+7E0h+psz2]
0x18000d6de  mov     r8, r15
0x18000d6e1  xor     ecx, ecx
0x18000d6e3  xor     ebx, ebx
0x18000d6e5  call    cs:__imp_SHExpandEnvironmentStringsForUserW
0x18000d6eb  test    eax, eax
0x18000d6ed  jz      loc_18000DAFE
0x18000d6f3  mov     eax, ebx
0x18000d6f5  mov     rbx, [rsp+8E0h+arg_10]
0x18000d6fd  mov     rcx, [rbp+7E0h+var_40]
0x18000d704  xor     rcx, rsp; StackCookie
0x18000d707  call    __security_check_cookie
0x18000d70c  add     rsp, 8B0h
0x18000d713  pop     r15
0x18000d715  pop     r14
0x18000d717  pop     r13
0x18000d719  pop     r12
0x18000d71b  pop     rdi
0x18000d71c  pop     rsi
0x18000d71d  pop     rbp
0x18000d71e  retn
0x18000d71f  inc     r14d
0x18000d722  jmp     loc_18000D5A3
0x18000d727  test    rax, rax
0x18000d72a  lea     rcx, [rdx-2]
0x18000d72e  cmovnz  rcx, rdx
0x18000d732  xor     eax, eax
0x18000d734  mov     [rcx], ax
0x18000d737  lea     r9, ?g_szMsg@@3PAGA; unsigned __int16 *
0x18000d73e  xor     r8d, r8d; unsigned __int16 *
0x18000d741  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Plus!\\Themes\\Cur"...
0x18000d748  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x18000d74f  call    ?HandGet@@YAHPEAUHKEY__@@PEBG1PEAG@Z; HandGet(HKEY__ *,ushort const *,ushort const *,ushort *)
0x18000d754  test    eax, eax
0x18000d756  jz      short loc_18000D782
0x18000d758  lea     r8, ?g_szMsg@@3PAGA; unsigned __int16 *
0x18000d75f  mov     edx, 105h; unsigned __int64
0x18000d764  lea     rcx, ?g_szCurDir@@3PAGA; unsigned __int16 *
0x18000d76b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d770  lea     rcx, ?g_szCurDir@@3PAGA; pszPath
0x18000d777  call    cs:__imp_PathFindFileNameW
0x18000d77d  xor     ecx, ecx
0x18000d77f  mov     [rax], cx
0x18000d782  xor     bl, bl
0x18000d784  mov     dl, 1
0x18000d786  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AUTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AUTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AUTest> `wil::Feature<__WilFeatureTraits_Feature_AUTest>::GetImpl(void)'::`2'::impl
0x18000d78d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AUTest@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AUTest>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000d792  lea     rdx, aCustomthemertm; "CustomThemeRTM"
0x18000d799  lea     rcx, [rsp+8E0h+var_8A8]; this
0x18000d79e  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18000d7a3  lea     rdx, [rsp+8E0h+var_8A8]
0x18000d7a8  lea     rcx, [rsp+8E0h+var_8B0]; struct winrt::param::hstring *
0x18000d7ad  call    ?FindAssetReferencePath@PackageManager@Deployment@Management@WindowsUdk@winrt@@SA@AEBUhstring@param@5@@Z; winrt::WindowsUdk::Management::Deployment::PackageManager::FindAssetReferencePath(winrt::param::hstring const &)
0x18000d7b2  lea     rdx, [rsp+8E0h+var_8A8]
0x18000d7b7  lea     rcx, [rsp+8E0h+var_8B0]
0x18000d7bc  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x18000d7c1  cmp     qword ptr [rax+8], 0
0x18000d7c6  jz      short loc_18000D7FF
0x18000d7c8  lea     rcx, [rsp+8E0h+var_8B0]; this
0x18000d7cd  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18000d7d2  mov     rcx, rax; pszPath
0x18000d7d5  call    cs:__imp_PathFileExistsW
0x18000d7db  test    eax, eax
0x18000d7dd  jz      short loc_18000D7FF
0x18000d7df  lea     rcx, [rsp+8E0h+var_8B0]; this
0x18000d7e4  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18000d7e9  mov     r8, rax; unsigned __int16 *
0x18000d7ec  lea     rcx, ?g_szLiftedThemeDir@@3PAGA; unsigned __int16 *
0x18000d7f3  mov     edx, 104h; unsigned __int64
0x18000d7f8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d7fd  mov     bl, 1
0x18000d7ff  lea     rcx, [rsp+8E0h+var_8B0]
0x18000d804  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18000d809  test    bl, bl
0x18000d80b  jnz     short loc_18000D857
0x18000d80d  movups  xmm0, xmmword ptr cs:aResourcedir; "%ResourceDir%"
0x18000d814  xor     edx, edx; Val
0x18000d816  mov     r8d, 1ECh; Size
0x18000d81c  movups  xmm1, xmmword ptr cs:aResourcedir+0Ch; "rceDir%"
0x18000d823  lea     rcx, [rsp+8E0h+var_864]; void *
0x18000d828  movaps  xmmword ptr [rsp+8E0h+var_880], xmm0
0x18000d82d  movups  xmmword ptr [rsp+8E0h+var_880+0Ch], xmm1
0x18000d832  call    memset_0
0x18000d837  lea     rcx, [rsp+8E0h+var_880]; unsigned __int16 *
0x18000d83c  call    ?ExpandResourceDir@@YAJPEAGK@Z; ExpandResourceDir(ushort *,ulong)
0x18000d841  lea     r8, [rsp+8E0h+var_880]; unsigned __int16 *
0x18000d846  mov     edx, 104h; unsigned __int64
0x18000d84b  lea     rcx, ?g_szLiftedThemeDir@@3PAGA; unsigned __int16 *
0x18000d852  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d857  xor     bl, bl
0x18000d859  mov     dl, 1
0x18000d85b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AUTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AUTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AUTest> `wil::Feature<__WilFeatureTraits_Feature_AUTest>::GetImpl(void)'::`2'::impl
0x18000d862  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AUTest@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AUTest>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000d867  lea     rdx, aCustomthemebac; "CustomThemeBackgrounds"
0x18000d86e  lea     rcx, [rsp+8E0h+var_8A8]; this
0x18000d873  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18000d878  lea     rdx, [rsp+8E0h+var_8A8]
0x18000d87d  lea     rcx, [rsp+8E0h+var_8B0]; struct winrt::param::hstring *
0x18000d882  call    ?FindAssetReferencePath@PackageManager@Deployment@Management@WindowsUdk@winrt@@SA@AEBUhstring@param@5@@Z; winrt::WindowsUdk::Management::Deployment::PackageManager::FindAssetReferencePath(winrt::param::hstring const &)
0x18000d887  lea     rdx, [rsp+8E0h+var_8A8]
0x18000d88c  lea     rcx, [rsp+8E0h+var_8B0]
0x18000d891  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x18000d896  cmp     qword ptr [rax+8], 0
0x18000d89b  jz      short loc_18000D8D4
0x18000d89d  lea     rcx, [rsp+8E0h+var_8B0]; this
0x18000d8a2  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18000d8a7  mov     rcx, rax; pszPath
0x18000d8aa  call    cs:__imp_PathFileExistsW
0x18000d8b0  test    eax, eax
0x18000d8b2  jz      short loc_18000D8D4
0x18000d8b4  lea     rcx, [rsp+8E0h+var_8B0]; this
0x18000d8b9  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18000d8be  mov     r8, rax; unsigned __int16 *
0x18000d8c1  lea     rcx, ?g_szLiftedWallpaperDir@@3PAGA; unsigned __int16 *
0x18000d8c8  mov     edx, 104h; unsigned __int64
0x18000d8cd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d8d2  mov     bl, 1
0x18000d8d4  lea     rcx, [rsp+8E0h+var_8B0]
0x18000d8d9  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18000d8de  test    bl, bl
0x18000d8e0  jnz     loc_18000D599
0x18000d8e6  movaps  xmm0, xmmword ptr cs:aSystemrootWebW; "%SystemRoot%\\web\\wallpaper\\Windows"
0x18000d8ed  lea     rcx, [rbp+7E0h+var_83A]; void *
0x18000d8f1  movaps  xmm1, xmmword ptr cs:aSystemrootWebW+10h; "oot%\\web\\wallpaper\\Windows"
0x18000d8f8  xor     edx, edx; Val
0x18000d8fa  movaps  xmmword ptr [rsp+8E0h+var_880], xmm0
0x18000d8ff  mov     r8d, 1C2h; Size
0x18000d905  movaps  xmm0, xmmword ptr cs:aSystemrootWebW+20h; "\\wallpaper\\Windows"
0x18000d90c  movaps  xmmword ptr [rsp+70h], xmm1
0x18000d911  movaps  xmm1, xmmword ptr cs:aSystemrootWebW+30h; "er\\Windows"
0x18000d918  movaps  [rbp+7E0h+var_860], xmm0
0x18000d91c  movsd   xmm0, qword ptr cs:aSystemrootWebW+3Eh; "ows"
0x18000d924  movaps  xmmword ptr [rbp+7E0h+var_850], xmm1
0x18000d928  movsd   qword ptr [rbp+7E0h+var_850+0Eh], xmm0
0x18000d92d  call    memset_0
0x18000d932  lea     rcx, [rsp+8E0h+var_880]; unsigned __int16 *
0x18000d937  call    ?ExpandResourceDir@@YAJPEAGK@Z; ExpandResourceDir(ushort *,ulong)
0x18000d93c  lea     r8, [rsp+8E0h+var_880]; unsigned __int16 *
0x18000d941  mov     edx, 104h; unsigned __int64
0x18000d946  lea     rcx, ?g_szLiftedWallpaperDir@@3PAGA; unsigned __int16 *
0x18000d94d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d952  jmp     loc_18000D599
0x18000d957  cmp     word ptr [rax], 0
0x18000d95b  jnz     short loc_18000D9BF
0x18000d95d  xor     eax, eax
0x18000d95f  mov     ecx, 104h
0x18000d964  sub     rcx, rdx
0x18000d967  test    rdx, rdx
0x18000d96a  cmovz   rcx, rax
0x18000d96e  jz      loc_18000D737
0x18000d974  mov     eax, 104h
0x18000d979  lea     r9, Control; "\\"
0x18000d980  lea     rdx, [r14+rcx*2]
0x18000d984  mov     r8, rdi
0x18000d987  sub     rax, rcx
0x18000d98a  jz      loc_18000D727
0x18000d990  test    r8, r8
  ... truncated ...
```
