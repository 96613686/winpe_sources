# InitFrost(void)

- ea: `0x1800328e8`
- end: `0x180032bf3`
- name: `?InitFrost@@YAXXZ`
- size: `779`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800104c0`
- `0x180010600`
- `0x18001078c`

## callees

- `0x18000ab10`
- `0x18000bb40`
- `0x18000db20`
- `0x18000db58`
- `0x18000dbcc`
- `0x18000ed70`
- `0x180015660`
- `0x18001ec70`
- `0x180020d5c`
- `0x1800328e8`
- `0x1800358c0`
- `0x18003633c`
- `0x1800505ec`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x180032a08`
- `SHLWAPI!PathFindFileNameW` at `0x180032a08`
- `SHLWAPI!PathFileExistsW` at `0x180032a64`
- `SHLWAPI!PathFileExistsW` at `0x180032b35`
- `SHLWAPI!PathFileExistsW` at `0x180032a64`
- `SHLWAPI!PathFileExistsW` at `0x180032b35`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18003293a`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18003293a`
- `GDI32!GetDeviceCaps` at `0x180032970`
- `GDI32!GetDeviceCaps` at `0x180032970`
- `USER32!ReleaseDC` at `0x18003297b`
- `USER32!ReleaseDC` at `0x18003297b`
- `USER32!GetDC` at `0x18003295f`
- `USER32!GetDC` at `0x18003295f`

## pseudocode

```c
void InitFrost(void)
{
  HDC DC; // rbx
  __int64 v1; // rax
  __int64 v2; // rdx
  char v3; // bl
  const WCHAR *v4; // rax
  const unsigned __int16 *v5; // rax
  __int64 v6; // rdx
  unsigned int v7; // edx
  char v8; // bl
  const WCHAR *v9; // rax
  const unsigned __int16 *v10; // rax
  unsigned int v11; // edx
  _BYTE v12[8]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v13[40]; // [rsp+28h] [rbp-D8h] BYREF
  __m256i v14; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v15; // [rsp+70h] [rbp-90h]
  _BYTE v16[22]; // [rsp+80h] [rbp-80h]
  _BYTE v17[458]; // [rsp+96h] [rbp-6Ah] BYREF

  if ( !dword_18008B4F8 )
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
      v1 = -1;
      do
        ++v1;
      while ( *(&g_szWinDir + v1) );
      if ( *(&g_szWinDir + v1 - 1) != 92 )
        StringCchCatW(&g_szWinDir, 0x104u, L"\\");
    }
    if ( HandGet(HKEY_CURRENT_USER, L"Software\\Microsoft\\Plus!\\Themes\\Current", 0, &g_szMsg) )
    {
      StringCchCopyW(&g_szCurDir, 0x105u, &g_szMsg);
      *PathFindFileNameW(&g_szCurDir) = 0;
    }
    v3 = 0;
    LOBYTE(v2) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AUTest>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_AUTest>::GetImpl'::`2'::impl,
      v2);
    winrt::param::hstring::hstring((winrt::param::hstring *)v13, L"CustomThemeRTM");
    winrt::WindowsUdk::Management::Deployment::PackageManager::FindAssetReferencePath((const struct winrt::param::hstring *)v12);
    if ( *(_QWORD *)(winrt::hstring::operator std::basic_string_view<unsigned short>(v12, v13) + 8) )
    {
      v4 = winrt::hstring::c_str((winrt::hstring *)v12);
      if ( PathFileExistsW(v4) )
      {
        v5 = winrt::hstring::c_str((winrt::hstring *)v12);
        StringCchCopyW(&g_szLiftedThemeDir, 0x104u, v5);
        v3 = 1;
      }
    }
    winrt::handle_type<winrt::impl::hstring_traits>::close(v12);
    if ( !v3 )
    {
      *(_OWORD *)v14.m256i_i8 = *(_OWORD *)L"%ResourceDir%";
      *(_OWORD *)((char *)&v14.m256i_u64[1] + 4) = *(_OWORD *)L"rceDir%";
      memset_0((char *)&v14.m256i_u64[3] + 4, 0, 0x1ECu);
      ExpandResourceDir((unsigned __int16 *)&v14, v7);
      StringCchCopyW(&g_szLiftedThemeDir, 0x104u, (const unsigned __int16 *)&v14);
    }
    v8 = 0;
    LOBYTE(v6) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AUTest>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_AUTest>::GetImpl'::`2'::impl,
      v6);
    winrt::param::hstring::hstring((winrt::param::hstring *)v13, L"CustomThemeBackgrounds");
    winrt::WindowsUdk::Management::Deployment::PackageManager::FindAssetReferencePath((const struct winrt::param::hstring *)v12);
    if ( *(_QWORD *)(winrt::hstring::operator std::basic_string_view<unsigned short>(v12, v13) + 8) )
    {
      v9 = winrt::hstring::c_str((winrt::hstring *)v12);
      if ( PathFileExistsW(v9) )
      {
        v10 = winrt::hstring::c_str((winrt::hstring *)v12);
        StringCchCopyW(&g_szLiftedWallpaperDir, 0x104u, v10);
        v8 = 1;
      }
    }
    winrt::handle_type<winrt::impl::hstring_traits>::close(v12);
    if ( !v8 )
    {
      v14 = *(__m256i *)L"%SystemRoot%\\web\\wallpaper\\Windows";
      v15 = *(_OWORD *)L"\\wallpaper\\Windows";
      *(_OWORD *)v16 = *(_OWORD *)L"er\\Windows";
      *(_QWORD *)&v16[14] = *(_QWORD *)L"ows";
      memset_0(v17, 0, 0x1C2u);
      ExpandResourceDir((unsigned __int16 *)&v14, v11);
      StringCchCopyW(&g_szLiftedWallpaperDir, 0x104u, (const unsigned __int16 *)&v14);
    }
  }
}

```

## disassembly

```asm
0x1800328e8  push    rbp
0x1800328ea  push    rbx
0x1800328eb  push    rsi
0x1800328ec  push    rdi
0x1800328ed  push    r14
0x1800328ef  lea     rbp, [rsp-170h]
0x1800328f7  sub     rsp, 270h
0x1800328fe  mov     rax, cs:__security_cookie
0x180032905  xor     rax, rsp
0x180032908  mov     [rbp+190h+var_30], rax
0x18003290f  xor     edi, edi
0x180032911  cmp     cs:dword_18008B4F8, edi
0x180032917  jnz     loc_180032BD6
0x18003291d  mov     r14d, 104h
0x180032923  mov     cs:dword_18008B4F8, 1
0x18003292d  lea     rsi, ?g_szWinDir@@3PAGA; ushort near * g_szWinDir
0x180032934  mov     edx, r14d; uSize
0x180032937  mov     rcx, rsi; lpBuffer
0x18003293a  call    cs:__imp_GetWindowsDirectoryW
0x180032940  test    eax, eax
0x180032942  jnz     short loc_18003294B
0x180032944  mov     cs:?g_szWinDir@@3PAGA, di; ushort near * g_szWinDir
0x18003294b  mov     r8, rsi; unsigned __int16 *
0x18003294e  lea     rcx, ?g_szThemeDir@@3PAGA; unsigned __int16 *
0x180032955  mov     rdx, r14; unsigned __int64
0x180032958  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003295d  xor     ecx, ecx; hWnd
0x18003295f  call    cs:__imp_GetDC
0x180032965  mov     rcx, rax; hdc
0x180032968  mov     edx, 0Ch; index
0x18003296d  mov     rbx, rax
0x180032970  call    cs:__imp_GetDeviceCaps
0x180032976  mov     rdx, rbx; hDC
0x180032979  xor     ecx, ecx; hWnd
0x18003297b  call    cs:__imp_ReleaseDC
0x180032981  lea     rbx, ?g_szCurDir@@3PAGA; ushort near * g_szCurDir
0x180032988  mov     edx, 105h; unsigned __int64
0x18003298d  mov     rcx, rbx; unsigned __int16 *
0x180032990  lea     r8, ?g_szThemeDir@@3PAGA; unsigned __int16 *
0x180032997  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003299c  cmp     cs:?g_szWinDir@@3PAGA, di; ushort near * g_szWinDir
0x1800329a3  jz      short loc_1800329D0
0x1800329a5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800329a9  inc     rax
0x1800329ac  cmp     [rsi+rax*2], di
0x1800329b0  jnz     short loc_1800329A9
0x1800329b2  mov     ecx, 5Ch ; '\'
0x1800329b7  cmp     cx, [rsi+rax*2-2]
0x1800329bc  jz      short loc_1800329D0
0x1800329be  lea     r8, Control; "\\"
0x1800329c5  mov     rdx, r14; unsigned __int64
0x1800329c8  mov     rcx, rsi; unsigned __int16 *
0x1800329cb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800329d0  lea     r9, ?g_szMsg@@3PAGA; unsigned __int16 *
0x1800329d7  xor     r8d, r8d; unsigned __int16 *
0x1800329da  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Plus!\\Themes\\Cur"...
0x1800329e1  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800329e8  call    ?HandGet@@YAHPEAUHKEY__@@PEBG1PEAG@Z; HandGet(HKEY__ *,ushort const *,ushort const *,ushort *)
0x1800329ed  test    eax, eax
0x1800329ef  jz      short loc_180032A11
0x1800329f1  lea     r8, ?g_szMsg@@3PAGA; unsigned __int16 *
0x1800329f8  mov     edx, 105h; unsigned __int64
0x1800329fd  mov     rcx, rbx; unsigned __int16 *
0x180032a00  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180032a05  mov     rcx, rbx; pszPath
0x180032a08  call    cs:__imp_PathFindFileNameW
0x180032a0e  mov     [rax], di
0x180032a11  mov     bl, dil
0x180032a14  mov     dl, 1
0x180032a16  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AUTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AUTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AUTest> `wil::Feature<__WilFeatureTraits_Feature_AUTest>::GetImpl(void)'::`2'::impl
0x180032a1d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AUTest@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AUTest>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180032a22  lea     rdx, aCustomthemertm; "CustomThemeRTM"
0x180032a29  lea     rcx, [rsp+290h+var_268]; this
0x180032a2e  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180032a33  lea     rdx, [rsp+290h+var_268]
0x180032a38  lea     rcx, [rsp+290h+var_270]; struct winrt::param::hstring *
0x180032a3d  call    ?FindAssetReferencePath@PackageManager@Deployment@Management@WindowsUdk@winrt@@SA@AEBUhstring@param@5@@Z; winrt::WindowsUdk::Management::Deployment::PackageManager::FindAssetReferencePath(winrt::param::hstring const &)
0x180032a42  lea     rdx, [rsp+290h+var_268]
0x180032a47  lea     rcx, [rsp+290h+var_270]
0x180032a4c  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x180032a51  cmp     [rax+8], rdi
0x180032a55  jz      short loc_180032A8C
0x180032a57  lea     rcx, [rsp+290h+var_270]; this
0x180032a5c  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180032a61  mov     rcx, rax; pszPath
0x180032a64  call    cs:__imp_PathFileExistsW
0x180032a6a  test    eax, eax
0x180032a6c  jz      short loc_180032A8C
0x180032a6e  lea     rcx, [rsp+290h+var_270]; this
0x180032a73  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180032a78  mov     r8, rax; unsigned __int16 *
0x180032a7b  lea     rcx, ?g_szLiftedThemeDir@@3PAGA; unsigned __int16 *
0x180032a82  mov     rdx, r14; unsigned __int64
0x180032a85  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180032a8a  mov     bl, 1
0x180032a8c  lea     rcx, [rsp+290h+var_270]
0x180032a91  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180032a96  test    bl, bl
0x180032a98  jnz     short loc_180032AE2
0x180032a9a  movups  xmm0, xmmword ptr cs:aResourcedir; "%ResourceDir%"
0x180032aa1  xor     edx, edx; Val
0x180032aa3  mov     r8d, 1ECh; Size
0x180032aa9  movups  xmm1, xmmword ptr cs:aResourcedir+0Ch; "rceDir%"
0x180032ab0  lea     rcx, [rsp+290h+var_224]; void *
0x180032ab5  movaps  xmmword ptr [rsp+290h+var_240], xmm0
0x180032aba  movups  xmmword ptr [rsp+290h+var_240+0Ch], xmm1
0x180032abf  call    memset_0
0x180032ac4  lea     rcx, [rsp+290h+var_240]; unsigned __int16 *
0x180032ac9  call    ?ExpandResourceDir@@YAJPEAGK@Z; ExpandResourceDir(ushort *,ulong)
0x180032ace  lea     r8, [rsp+290h+var_240]; unsigned __int16 *
0x180032ad3  mov     rdx, r14; unsigned __int64
0x180032ad6  lea     rcx, ?g_szLiftedThemeDir@@3PAGA; unsigned __int16 *
0x180032add  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180032ae2  mov     bl, dil
0x180032ae5  mov     dl, 1
0x180032ae7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AUTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AUTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AUTest> `wil::Feature<__WilFeatureTraits_Feature_AUTest>::GetImpl(void)'::`2'::impl
0x180032aee  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AUTest@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AUTest>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180032af3  lea     rdx, aCustomthemebac; "CustomThemeBackgrounds"
0x180032afa  lea     rcx, [rsp+290h+var_268]; this
0x180032aff  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180032b04  lea     rdx, [rsp+290h+var_268]
0x180032b09  lea     rcx, [rsp+290h+var_270]; struct winrt::param::hstring *
0x180032b0e  call    ?FindAssetReferencePath@PackageManager@Deployment@Management@WindowsUdk@winrt@@SA@AEBUhstring@param@5@@Z; winrt::WindowsUdk::Management::Deployment::PackageManager::FindAssetReferencePath(winrt::param::hstring const &)
0x180032b13  lea     rdx, [rsp+290h+var_268]
0x180032b18  lea     rcx, [rsp+290h+var_270]
0x180032b1d  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x180032b22  cmp     [rax+8], rdi
0x180032b26  jz      short loc_180032B5D
0x180032b28  lea     rcx, [rsp+290h+var_270]; this
0x180032b2d  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180032b32  mov     rcx, rax; pszPath
0x180032b35  call    cs:__imp_PathFileExistsW
0x180032b3b  test    eax, eax
0x180032b3d  jz      short loc_180032B5D
0x180032b3f  lea     rcx, [rsp+290h+var_270]; this
0x180032b44  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180032b49  mov     r8, rax; unsigned __int16 *
0x180032b4c  lea     rcx, ?g_szLiftedWallpaperDir@@3PAGA; unsigned __int16 *
0x180032b53  mov     rdx, r14; unsigned __int64
0x180032b56  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180032b5b  mov     bl, 1
0x180032b5d  lea     rcx, [rsp+290h+var_270]
0x180032b62  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180032b67  test    bl, bl
0x180032b69  jnz     short loc_180032BD6
0x180032b6b  movaps  xmm0, xmmword ptr cs:aSystemrootWebW; "%SystemRoot%\\web\\wallpaper\\Windows"
0x180032b72  lea     rcx, [rbp+190h+var_1FA]; void *
0x180032b76  movaps  xmm1, xmmword ptr cs:aSystemrootWebW+10h; "oot%\\web\\wallpaper\\Windows"
0x180032b7d  xor     edx, edx; Val
0x180032b7f  movaps  xmmword ptr [rsp+290h+var_240], xmm0
0x180032b84  mov     r8d, 1C2h; Size
0x180032b8a  movaps  xmm0, xmmword ptr cs:aSystemrootWebW+20h; "\\wallpaper\\Windows"
0x180032b91  movaps  xmmword ptr [rsp+60h], xmm1
0x180032b96  movaps  xmm1, xmmword ptr cs:aSystemrootWebW+30h; "er\\Windows"
0x180032b9d  movaps  [rsp+290h+var_220], xmm0
0x180032ba2  movsd   xmm0, qword ptr cs:aSystemrootWebW+3Eh; "ows"
0x180032baa  movaps  xmmword ptr [rbp+190h+var_210], xmm1
0x180032bae  movsd   qword ptr [rbp+190h+var_210+0Eh], xmm0
0x180032bb3  call    memset_0
0x180032bb8  lea     rcx, [rsp+290h+var_240]; unsigned __int16 *
0x180032bbd  call    ?ExpandResourceDir@@YAJPEAGK@Z; ExpandResourceDir(ushort *,ulong)
0x180032bc2  lea     r8, [rsp+290h+var_240]; unsigned __int16 *
0x180032bc7  mov     rdx, r14; unsigned __int64
0x180032bca  lea     rcx, ?g_szLiftedWallpaperDir@@3PAGA; unsigned __int16 *
0x180032bd1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180032bd6  mov     rcx, [rbp+190h+var_30]
0x180032bdd  xor     rcx, rsp; StackCookie
0x180032be0  call    __security_check_cookie
0x180032be5  add     rsp, 270h
0x180032bec  pop     r14
0x180032bee  pop     rdi
0x180032bef  pop     rsi
0x180032bf0  pop     rbx
0x180032bf1  pop     rbp
0x180032bf2  retn
```
