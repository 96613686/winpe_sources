# _ValidateLink(LINKPROP_DATA *)

- ea: `0x180436770`
- end: `0x180436bf6`
- name: `?_ValidateLink@@YAHPEAULINKPROP_DATA@@@Z`
- size: `1158`
- prototype: `__int64 __fastcall(struct LINKPROP_DATA *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1804357d0`

## callees

- `0x18000f05c`
- `0x1800181e0`
- `0x1800295b0`
- `0x1800415dc`
- `0x180054320`
- `0x180080470`
- `0x1800ac89c`
- `0x180233280`
- `0x1802342fc`
- `0x18026387c`
- `0x180359914`
- `0x180434958`
- `0x180434a00`
- `0x180434aac`
- `0x180434bc0`
- `0x180434f0c`
- `0x18043537c`
- `0x180436770`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1804367d2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1804367d2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180436b5e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180436b5e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x1804368b0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x1804368b0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1804367e8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1804367e8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathQuoteSpacesW` at `0x1804369f9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathQuoteSpacesW` at `0x1804369f9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesW` at `0x1804368ba`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesW` at `0x1804368ba`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x18043698a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x18043698a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x1804368c4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18043699f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x1804368c4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18043699f`
- `USER32!GetDlgItem` at `0x180436868`
- `USER32!GetDlgItem` at `0x180436868`
- `USER32!SetDlgItemTextW` at `0x180436af0`
- `USER32!SetDlgItemTextW` at `0x180436b75`
- `USER32!SetDlgItemTextW` at `0x180436af0`
- `USER32!SetDlgItemTextW` at `0x180436b75`
- `USER32!GetDlgItemTextW` at `0x180436b4d`
- `USER32!GetDlgItemTextW` at `0x180436b4d`
- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x18043680d`
- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x18043680d`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180436859`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180436921`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180436beb`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180436859`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180436921`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180436beb`
- `Windows.Storage!PathComposeWithArgs` at `0x180436b20`
- `Windows.Storage!PathComposeWithArgs` at `0x180436b20`
- `Windows.Storage!PathIsLnk` at `0x1804368e3`
- `Windows.Storage!PathIsLnk` at `0x1804368e3`
- `Windows.Storage!PathResolve` at `0x180436953`
- `Windows.Storage!PathResolve` at `0x1804369cc`
- `Windows.Storage!PathResolve` at `0x180436953`
- `Windows.Storage!PathResolve` at `0x1804369cc`

## string_xrefs

- `0x180436a9f`: `shell\shell32\linkprop.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall _ValidateLink(HWND *a1, int a2)
{
  unsigned int v3; // r8d
  char IsEnabled; // al
  __int64 v5; // rcx
  HWND v6; // rdx
  int v7; // edx
  HWND DlgItem; // rax
  char v10; // al
  __int64 v11; // rcx
  HWND v12; // rdx
  unsigned int v13; // r8d
  int v14; // r14d
  int (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // rdi
  int (__fastcall *v16)(_QWORD, GUID *, __int64 *); // rbx
  int v17; // eax
  char v18; // al
  __int64 v19; // rcx
  HWND v20; // rdx
  UINT fuStyle; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpString; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v23[8]; // [rsp+38h] [rbp-C8h] BYREF
  PROPERTYKEY v24; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+68h] [rbp-98h] BYREF
  PCWSTR dirs[2]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszPath[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR pszStart[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR String[264]; // [rsp+4A0h] [rbp+3A0h] BYREF
  unsigned __int16 v31[264]; // [rsp+6B0h] [rbp+5B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+908h] [rbp+808h]

  if ( *((_DWORD *)a1 + 8) )
  {
    GetDlgItemPath(a1[2], a2, pszStart);
    if ( pszStart[0]
      && !StrChrW(pszStart, 0x25u)
      && !PathIsUNCW(pszStart)
      && !(unsigned int)PathIsRemovable(pszStart)
      && !PathIsDirectoryW(pszStart) )
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56287097>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID56287097>::GetImpl'::`2'::impl);
      v6 = a1[2];
      if ( IsEnabled )
        MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short____2(v5, v6, 4209);
      else
        ShellMessageBoxW(g_hinst, v6, (LPCWSTR)0x1071, (LPCWSTR)0x1070, 0x30u, pszStart);
      v7 = 12290;
      goto LABEL_11;
    }
    if ( _GetPathAndArgs((struct LINKPROP_DATA *)a1, pszPath, v3, v31, 0x104u) < 0 || !pszPath[0] )
      goto LABEL_43;
    PathRemoveBlanksW(pszPath);
    PathUnquoteSpacesW(pszPath);
    if ( !PathIsRootW(pszPath) || !(unsigned int)PathIsRemovable(pszPath) )
    {
      if ( (unsigned int)PathIsLnk(pszPath) )
      {
        v10 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56287097>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID56287097>::GetImpl'::`2'::impl);
        v12 = a1[2];
        if ( v10 )
          MessageBoxHelper::ShellMessageBoxTextScaled___7(v11, v12);
        else
          ShellMessageBoxW(g_hinst, v12, (LPCWSTR)0x107A, (LPCWSTR)0x1070, 0x30u);
LABEL_20:
        v7 = 13058;
LABEL_11:
        DlgItem = GetDlgItem(a1[2], v7);
        SetEditFocus(DlgItem);
        return 0;
      }
      dirs[0] = pszStart;
      dirs[1] = 0;
      if ( PathResolve(pszPath, dirs, 0xBu) )
        goto LABEL_27;
      if ( _GetPathAndArgs((struct LINKPROP_DATA *)a1, pszPath, v13, v31, 0x104u) < 0
        || !(unsigned int)SHExpandEnvironmentStringsW(pszPath, String, 260) )
      {
LABEL_43:
        v18 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56287097>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID56287097>::GetImpl'::`2'::impl);
        v20 = a1[2];
        if ( v18 )
          MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short____2(v19, v20, 4210);
        else
          ShellMessageBoxW(g_hinst, v20, (LPCWSTR)0x1072, (LPCWSTR)0x1070, 0x30u, pszPath);
        goto LABEL_20;
      }
      if ( !PathIsRootW(String) || !(unsigned int)PathIsRemovable(String) )
      {
        if ( PathResolve(String, dirs, 0xBu) )
        {
LABEL_27:
          v14 = *((_DWORD *)a1 + 12);
          if ( *((_DWORD *)a1 + 11) )
            *((_DWORD *)a1 + 12) = 0;
          if ( *((_BYTE *)a1 + 1116) )
          {
            PathQuoteSpacesW(pszPath);
            v26 = 0;
            lpString = 0;
            v25 = 0;
            v15 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))a1[1];
            v16 = (int (__fastcall *)(_QWORD, GUID *, __int64 *))**v15;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
            if ( v16(v15, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &v26) < 0
              || (wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                    &v25,
                    0),
                  v24 = PKEY_Link_Arguments,
                  (int)wil::PropertyStoreHelperBase<IPropertyStore>::GetAsString<_tagpropertykey>(&v26, &v24, &v25) < 0) )
            {
              wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                v23,
                pszPath,
                -1);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                &lpString,
                v23);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(v23);
            }
            else
            {
              v17 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                      &lpString,
                      L"%s %s",
                      pszPath,
                      v25);
              if ( v17 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x432,
                  (unsigned int)"shell\\shell32\\linkprop.cpp",
                  (const char *)(unsigned int)v17,
                  fuStyle);
            }
            if ( lpString )
              SetDlgItemTextW(a1[2], 13058, lpString);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v25);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpString);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
          }
          else
          {
            PathComposeWithArgs(pszPath, v31);
            memset_0(String, 0, 0x208u);
            GetDlgItemTextW(a1[2], 13058, String, 260);
            if ( lstrcmpiW(pszPath, String) )
              SetDlgItemTextW(a1[2], 13058, pszPath);
          }
          if ( *((_DWORD *)a1 + 11) )
            *((_DWORD *)a1 + 12) = v14;
          return 1;
        }
        goto LABEL_43;
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180436770  push    rbp
0x180436772  push    rbx
0x180436773  push    rsi
0x180436774  push    rdi
0x180436775  push    r14
0x180436777  push    r15
0x180436779  lea     rbp, [rsp-7D8h]
0x180436781  sub     rsp, 8D8h
0x180436788  mov     rax, cs:__security_cookie
0x18043678f  xor     rax, rsp
0x180436792  mov     [rbp+800h+var_40], rax
0x180436799  mov     rsi, rcx
0x18043679c  xor     r15d, r15d
0x18043679f  cmp     [rcx+20h], r15d
0x1804367a3  jz      loc_180436B85
0x1804367a9  lea     r8, [rbp+800h+pszStart]; unsigned __int16 *
0x1804367b0  mov     rcx, [rcx+10h]; HWND
0x1804367b4  call    ?GetDlgItemPath@@YAXPEAUHWND__@@HPEAG@Z; GetDlgItemPath(HWND__ *,int,ushort *)
0x1804367b9  cmp     [rbp+800h+pszStart], r15w
0x1804367c1  jz      loc_18043687D
0x1804367c7  lea     edx, [r15+25h]; wMatch
0x1804367cb  lea     rcx, [rbp+800h+pszStart]; pszStart
0x1804367d2  call    cs:__imp_StrChrW
0x1804367d8  test    rax, rax
0x1804367db  jnz     loc_18043687D
0x1804367e1  lea     rcx, [rbp+800h+pszStart]; pszPath
0x1804367e8  call    cs:__imp_PathIsUNCW
0x1804367ee  test    eax, eax
0x1804367f0  jnz     loc_18043687D
0x1804367f6  lea     rcx, [rbp+800h+pszStart]; unsigned __int16 *
0x1804367fd  call    ?PathIsRemovable@@YAHPEBG@Z; PathIsRemovable(ushort const *)
0x180436802  test    eax, eax
0x180436804  jnz     short loc_18043687D
0x180436806  lea     rcx, [rbp+800h+pszStart]; pszPath
0x18043680d  call    cs:__imp_PathIsDirectoryW
0x180436813  test    eax, eax
0x180436815  jnz     short loc_18043687D
0x180436817  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID56287097@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID56287097@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56287097> `wil::Feature<__WilFeatureTraits_Feature_ID56287097>::GetImpl(void)'::`2'::impl
0x18043681e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56287097@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56287097>::__private_IsEnabled(void)
0x180436823  mov     r8d, 1071h; lpcText
0x180436829  mov     rdx, [rsi+10h]; hWnd
0x18043682d  test    al, al
0x18043682f  lea     rax, [rbp+800h+pszStart]
0x180436836  mov     [rsp+900h+var_8D8], rax
0x18043683b  jz      short loc_180436844
0x18043683d  call    MessageBoxHelper__ShellMessageBoxTextScaled_unsigned_short____2
0x180436842  jmp     short loc_18043685F
0x180436844  mov     [rsp+900h+fuStyle], 30h ; '0'; fuStyle
0x18043684c  mov     r9d, 1070h; lpcTitle
0x180436852  mov     rcx, cs:g_hinst; hAppInst
0x180436859  call    cs:__imp_ShellMessageBoxW
0x18043685f  mov     edx, 3002h; nIDDlgItem
0x180436864  mov     rcx, [rsi+10h]; hDlg
0x180436868  call    cs:__imp_GetDlgItem
0x18043686e  mov     rcx, rax; HWND
0x180436871  call    ?SetEditFocus@@YAXPEAUHWND__@@@Z; SetEditFocus(HWND__ *)
0x180436876  xor     eax, eax
0x180436878  jmp     loc_180436B8A
0x18043687d  mov     ebx, 104h
0x180436882  mov     [rsp+900h+fuStyle], ebx; unsigned int
0x180436886  lea     r9, [rbp+800h+var_250]; unsigned __int16 *
0x18043688d  lea     rdx, [rbp+800h+pszPath]; unsigned __int16 *
0x180436891  mov     rcx, rsi; struct LINKPROP_DATA *
0x180436894  call    ?_GetPathAndArgs@@YAJPEAULINKPROP_DATA@@PEAGI1I@Z; _GetPathAndArgs(LINKPROP_DATA *,ushort *,uint,ushort *,uint)
0x180436899  test    eax, eax
0x18043689b  js      loc_180436BA9
0x1804368a1  cmp     [rbp+800h+pszPath], r15w
0x1804368a6  jz      loc_180436BA9
0x1804368ac  lea     rcx, [rbp+800h+pszPath]; pszPath
0x1804368b0  call    cs:__imp_PathRemoveBlanksW
0x1804368b6  lea     rcx, [rbp+800h+pszPath]; lpsz
0x1804368ba  call    cs:__imp_PathUnquoteSpacesW
0x1804368c0  lea     rcx, [rbp+800h+pszPath]; pszPath
0x1804368c4  call    cs:__imp_PathIsRootW
0x1804368ca  test    eax, eax
0x1804368cc  jz      short loc_1804368DF
0x1804368ce  lea     rcx, [rbp+800h+pszPath]; unsigned __int16 *
0x1804368d2  call    ?PathIsRemovable@@YAHPEBG@Z; PathIsRemovable(ushort const *)
0x1804368d7  test    eax, eax
0x1804368d9  jnz     loc_180436B85
0x1804368df  lea     rcx, [rbp+800h+pszPath]
0x1804368e3  call    cs:__imp_PathIsLnk
0x1804368e9  test    eax, eax
0x1804368eb  jz      short loc_180436931
0x1804368ed  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID56287097@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID56287097@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56287097> `wil::Feature<__WilFeatureTraits_Feature_ID56287097>::GetImpl(void)'::`2'::impl
0x1804368f4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56287097@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56287097>::__private_IsEnabled(void)
0x1804368f9  mov     rdx, [rsi+10h]; hWnd
0x1804368fd  test    al, al
0x1804368ff  jz      short loc_180436908
0x180436901  call    MessageBoxHelper__ShellMessageBoxTextScaled___7
0x180436906  jmp     short loc_180436927
0x180436908  mov     [rsp+900h+fuStyle], 30h ; '0'; fuStyle
0x180436910  mov     r9d, 1070h; lpcTitle
0x180436916  lea     r8d, [r9+0Ah]; lpcText
0x18043691a  mov     rcx, cs:g_hinst; hAppInst
0x180436921  call    cs:__imp_ShellMessageBoxW
0x180436927  mov     edx, 3302h
0x18043692c  jmp     loc_180436864
0x180436931  lea     rax, [rbp+800h+pszStart]
0x180436938  mov     [rsp+900h+dirs], rax
0x18043693d  mov     [rsp+900h+var_888], r15
0x180436942  mov     edi, 0Bh
0x180436947  mov     r8d, edi; fFlags
0x18043694a  lea     rdx, [rsp+900h+dirs]; dirs
0x18043694f  lea     rcx, [rbp+800h+pszPath]; pszPath
0x180436953  call    cs:__imp_PathResolve
0x180436959  test    eax, eax
0x18043695b  jnz     short loc_1804369DA
0x18043695d  mov     [rsp+900h+fuStyle], ebx; int
0x180436961  lea     r9, [rbp+800h+var_250]; unsigned __int16 *
0x180436968  lea     rdx, [rbp+800h+pszPath]; unsigned __int16 *
0x18043696c  mov     rcx, rsi; struct LINKPROP_DATA *
0x18043696f  call    ?_GetPathAndArgs@@YAJPEAULINKPROP_DATA@@PEAGI1I@Z; _GetPathAndArgs(LINKPROP_DATA *,ushort *,uint,ushort *,uint)
0x180436974  test    eax, eax
0x180436976  js      loc_180436BA9
0x18043697c  mov     r8d, ebx
0x18043697f  lea     rdx, [rbp+800h+String]
0x180436986  lea     rcx, [rbp+800h+pszPath]
0x18043698a  call    cs:__imp_SHExpandEnvironmentStringsW
0x180436990  test    eax, eax
0x180436992  jz      loc_180436BA9
0x180436998  lea     rcx, [rbp+800h+String]; pszPath
0x18043699f  call    cs:__imp_PathIsRootW
0x1804369a5  test    eax, eax
0x1804369a7  jz      short loc_1804369BD
0x1804369a9  lea     rcx, [rbp+800h+String]; unsigned __int16 *
0x1804369b0  call    ?PathIsRemovable@@YAHPEBG@Z; PathIsRemovable(ushort const *)
0x1804369b5  test    eax, eax
0x1804369b7  jnz     loc_180436B85
0x1804369bd  mov     r8d, edi; fFlags
0x1804369c0  lea     rdx, [rsp+900h+dirs]; dirs
0x1804369c5  lea     rcx, [rbp+800h+String]; pszPath
0x1804369cc  call    cs:__imp_PathResolve
0x1804369d2  test    eax, eax
0x1804369d4  jz      loc_180436BA9
0x1804369da  mov     r14d, [rsi+30h]
0x1804369de  cmp     [rsi+2Ch], r15d
0x1804369e2  jz      short loc_1804369E8
0x1804369e4  mov     [rsi+30h], r15d
0x1804369e8  lea     rcx, [rbp+800h+pszPath]; lpsz
0x1804369ec  cmp     [rsi+45Ch], r15b
0x1804369f3  jz      loc_180436B19
0x1804369f9  call    cs:__imp_PathQuoteSpacesW
0x1804369ff  mov     [rsp+900h+var_898], r15
0x180436a04  mov     [rsp+900h+lpString], r15
0x180436a09  mov     [rsp+900h+var_8A0], r15
0x180436a0e  mov     rdi, [rsi+8]
0x180436a12  mov     rax, [rdi]
0x180436a15  mov     rbx, [rax]
0x180436a18  lea     rcx, [rsp+900h+var_898]
0x180436a1d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180436a22  lea     r8, [rsp+900h+var_898]
0x180436a27  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180436a2e  mov     rcx, rdi
0x180436a31  mov     rax, rbx
0x180436a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180436a39  test    eax, eax
0x180436a3b  js      short loc_180436AB2
0x180436a3d  xor     edx, edx
0x180436a3f  lea     rcx, [rsp+900h+var_8A0]
0x180436a44  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180436a49  movups  xmm0, xmmword ptr cs:PKEY_Link_Arguments.fmtid.Data1
0x180436a50  movaps  [rsp+900h+var_8C0], xmm0
0x180436a55  mov     eax, cs:PKEY_Link_Arguments.pid
0x180436a5b  mov     [rsp+900h+var_8B0], eax
0x180436a5f  lea     r8, [rsp+900h+var_8A0]
0x180436a64  lea     rdx, [rsp+900h+var_8C0]
0x180436a69  lea     rcx, [rsp+900h+var_898]
0x180436a6e  call    ??$GetAsString@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAPEAG@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetAsString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x180436a73  test    eax, eax
0x180436a75  js      short loc_180436AB2
0x180436a77  mov     r9, [rsp+900h+var_8A0]
0x180436a7c  lea     r8, [rbp+800h+pszPath]
0x180436a80  lea     rdx, aSS_7; "%s %s"
0x180436a87  lea     rcx, [rsp+900h+lpString]
0x180436a8c  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180436a91  mov     rcx, [rbp+808h]; this
0x180436a98  test    eax, eax
0x180436a9a  jns     short loc_180436ADD
0x180436a9c  mov     r9d, eax; char *
0x180436a9f  lea     r8, aShellShell32Li_0; "shell\\shell32\\linkprop.cpp"
0x180436aa6  mov     edx, 432h; void *
0x180436aab  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180436ab0  jmp     short loc_180436ADD
0x180436ab2  or      r8, 0FFFFFFFFFFFFFFFFh
0x180436ab6  lea     rdx, [rbp+800h+pszPath]
0x180436aba  lea     rcx, [rsp+900h+var_8C8]
0x180436abf  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180436ac4  lea     rdx, [rsp+900h+var_8C8]
0x180436ac9  lea     rcx, [rsp+900h+lpString]
0x180436ace  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180436ad3  lea     rcx, [rsp+900h+var_8C8]; void *
0x180436ad8  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180436add  mov     r8, [rsp+900h+lpString]; lpString
0x180436ae2  test    r8, r8
0x180436ae5  jz      short loc_180436AF7
0x180436ae7  mov     edx, 3302h; nIDDlgItem
0x180436aec  mov     rcx, [rsi+10h]; hDlg
0x180436af0  call    cs:__imp_SetDlgItemTextW
0x180436af6  nop
0x180436af7  lea     rcx, [rsp+900h+var_8A0]; void *
0x180436afc  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180436b01  nop
0x180436b02  lea     rcx, [rsp+900h+lpString]; void *
0x180436b07  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180436b0c  nop
0x180436b0d  lea     rcx, [rsp+900h+var_898]
0x180436b12  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180436b17  jmp     short loc_180436B7B
0x180436b19  lea     rdx, [rbp+800h+var_250]
0x180436b20  call    cs:__imp_PathComposeWithArgs
0x180436b26  xor     edx, edx; Val
0x180436b28  mov     r8d, 208h; Size
0x180436b2e  lea     rcx, [rbp+800h+String]; void *
0x180436b35  call    memset_0
0x180436b3a  mov     r9d, ebx; cchMax
0x180436b3d  lea     r8, [rbp+800h+String]; lpString
0x180436b44  mov     edx, 3302h; nIDDlgItem
0x180436b49  mov     rcx, [rsi+10h]; hDlg
0x180436b4d  call    cs:__imp_GetDlgItemTextW
0x180436b53  lea     rdx, [rbp+800h+String]; lpString2
0x180436b5a  lea     rcx, [rbp+800h+pszPath]; lpString1
0x180436b5e  call    cs:__imp_lstrcmpiW
0x180436b64  test    eax, eax
0x180436b66  jz      short loc_180436B7B
0x180436b68  lea     r8, [rbp+800h+pszPath]; lpString
0x180436b6c  mov     edx, 3302h; nIDDlgItem
0x180436b71  mov     rcx, [rsi+10h]; hDlg
0x180436b75  call    cs:__imp_SetDlgItemTextW
0x180436b7b  cmp     [rsi+2Ch], r15d
0x180436b7f  jz      short loc_180436B85
0x180436b81  mov     [rsi+30h], r14d
0x180436b85  mov     eax, 1
0x180436b8a  mov     rcx, [rbp+800h+var_40]
0x180436b91  xor     rcx, rsp; StackCookie
0x180436b94  call    __security_check_cookie
0x180436b99  add     rsp, 8D8h
0x180436ba0  pop     r15
0x180436ba2  pop     r14
0x180436ba4  pop     rdi
0x180436ba5  pop     rsi
0x180436ba6  pop     rbx
0x180436ba7  pop     rbp
0x180436ba8  retn
0x180436ba9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID56287097@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID56287097@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56287097> `wil::Feature<__WilFeatureTraits_Feature_ID56287097>::GetImpl(void)'::`2'::impl
0x180436bb0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56287097@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56287097>::__private_IsEnabled(void)
0x180436bb5  mov     r8d, 1072h; lpcText
0x180436bbb  mov     rdx, [rsi+10h]; hWnd
0x180436bbf  test    al, al
0x180436bc1  lea     rax, [rbp+800h+pszPath]
0x180436bc5  mov     [rsp+900h+var_8D8], rax
0x180436bca  jz      short loc_180436BD6
0x180436bcc  call    MessageBoxHelper__ShellMessageBoxTextScaled_unsigned_short____2
0x180436bd1  jmp     loc_180436927
0x180436bd6  mov     [rsp+900h+fuStyle], 30h ; '0'; fuStyle
0x180436bde  mov     r9d, 1070h; lpcTitle
0x180436be4  mov     rcx, cs:g_hinst; hAppInst
0x180436beb  call    cs:__imp_ShellMessageBoxW
0x180436bf1  jmp     loc_180436927
```
