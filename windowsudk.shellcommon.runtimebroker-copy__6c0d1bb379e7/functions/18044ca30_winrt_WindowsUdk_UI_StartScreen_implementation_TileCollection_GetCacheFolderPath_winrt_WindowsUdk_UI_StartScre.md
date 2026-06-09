# winrt::WindowsUdk::UI::StartScreen::implementation::TileCollection::GetCacheFolderPath(winrt::WindowsUdk::UI::StartScreen::TileCollectionCreateOptions const &)

- ea: `0x18044ca30`
- end: `0x18044cc9b`
- name: `?GetCacheFolderPath@TileCollection@implementation@StartScreen@UI@WindowsUdk@winrt@@SA?AUhstring@6@AEBUTileCollectionCreateOptions@3456@@Z`
- size: `619`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c97e0`

## callees

- `0x18000b428`
- `0x180025348`
- `0x180026860`
- `0x180027af0`
- `0x180033198`
- `0x180037df8`
- `0x1800488d0`
- `0x180072c50`
- `0x1800869dc`
- `0x1800d9c48`
- `0x1800e488c`
- `0x18011d484`
- `0x18013bcf8`
- `0x1801588c4`
- `0x18015cb00`
- `0x1803bb5c0`
- `0x18044c470`
- `0x18044c784`
- `0x18044ca30`
- `0x18044dcbc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18044cb4c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18044cb4c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18044cb18`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18044cb18`
- `api-ms-win-appmodel-runtime-l1-1-0!GetCurrentPackageFullName` at `0x18044ca6a`
- `api-ms-win-appmodel-runtime-l1-1-0!GetCurrentPackageFullName` at `0x18044ca6a`
- `ext-ms-win-shell-shlwapi-l1-1-0!PathIsDirectoryW` at `0x18044cb30`
- `ext-ms-win-shell-shlwapi-l1-1-0!PathIsDirectoryW` at `0x18044cb68`
- `ext-ms-win-shell-shlwapi-l1-1-0!PathIsDirectoryW` at `0x18044cb30`
- `ext-ms-win-shell-shlwapi-l1-1-0!PathIsDirectoryW` at `0x18044cb68`

## string_xrefs

- `0x18044ca87`: `shellcommon\undockeddevkit\libs\windowsudk.ui.startscreen\tilecollection.cpp`
- `0x18044cac7`: `shellcommon\undockeddevkit\libs\windowsudk.ui.startscreen\tilecollection.cpp`
- `0x18044cbfb`: `shellcommon\undockeddevkit\libs\windowsudk.ui.startscreen\tilecollection.cpp`
- `0x18044cc74`: `shellcommon\undockeddevkit\libs\windowsudk.ui.startscreen\tilecollection.cpp`
- `0x18044cc86`: `shellcommon\undockeddevkit\libs\windowsudk.ui.startscreen\tilecollection.cpp`
- `0x18044cab1`: `Unpackaged callers must specify a cache folder`
- `0x18044cbe5`: `Packaged callers shouldn't specify a cache folder`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall winrt::WindowsUdk::UI::StartScreen::implementation::TileCollection::GetCacheFolderPath(
        __int64 a1,
        __int64 a2)
{
  unsigned int CurrentPackageFullName; // eax
  const wchar_t *v5; // rax
  const WCHAR *v6; // rcx
  const WCHAR *v7; // rcx
  const WCHAR *v8; // rcx
  const char *v9; // r9
  const WCHAR *v10; // rcx
  const wchar_t *v11; // rdx
  LPCWSTR *v12; // rcx
  int DirectoryDeepNoThrow; // eax
  _QWORD *v14; // rax
  __int64 v15; // rax
  unsigned int v17; // [rsp+20h] [rbp-60h]
  int v18; // [rsp+20h] [rbp-60h]
  UINT32 packageFullNameLength[2]; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v20[2]; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v21[16]; // [rsp+48h] [rbp-38h] BYREF
  LPCWSTR pszPath[3]; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int64 v23; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v20[0] = a1;
  packageFullNameLength[0] = 0;
  CurrentPackageFullName = GetCurrentPackageFullName(packageFullNameLength, 0);
  if ( CurrentPackageFullName == 122 )
  {
    v14 = (_QWORD *)winrt::impl::consume_WindowsUdk_UI_StartScreen_ITileCollectionCreateOptions2<winrt::WindowsUdk::UI::StartScreen::TileCollectionCreateOptions>::CacheSubfolder(
                      a2,
                      packageFullNameLength);
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0xF3,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.ui.startscreen\\tilecollection.cpp",
      (const char *)0x8007139FLL,
      *v14 != 0,
      (bool)"Packaged callers shouldn't specify a cache folder",
      *(const char **)packageFullNameLength);
    winrt::handle_type<winrt::impl::hstring_traits>::close(packageFullNameLength);
    winrt::Windows::Storage::ApplicationData::Current();
    v15 = winrt::impl::consume_Windows_Internal_IAutomaticDestinationListItemInfo<winrt::Windows::Internal::IAutomaticDestinationListItemInfo>::ExtendedProperties(
            v20,
            packageFullNameLength);
    winrt::impl::consume_Windows_Storage_IStorageItem<winrt::Windows::Storage::IStorageFolder>::Path(v15, a1);
    winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)packageFullNameLength);
    winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)v20);
  }
  else
  {
    if ( CurrentPackageFullName != 15700 )
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0x35,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.ui.startscreen\\tilecollection.cpp",
        (const char *)CurrentPackageFullName,
        v17);
    winrt::impl::consume_WindowsUdk_UI_StartScreen_ITileCollectionCreateOptions2<winrt::WindowsUdk::UI::StartScreen::TileCollectionCreateOptions>::CacheSubfolder(
      a2,
      packageFullNameLength);
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0xFB,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.ui.startscreen\\tilecollection.cpp",
      (const char *)0x8007139FLL,
      *(_QWORD *)packageFullNameLength == 0,
      (bool)"Unpackaged callers must specify a cache folder",
      *(const char **)packageFullNameLength);
    wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
      v20,
      L"%localappdata%\\Microsoft\\Windows\\Tiles");
    v5 = winrt::hstring::c_str((winrt::hstring *)packageFullNameLength);
    wil::str_printf<std::wstring>(pszPath, L"%ws\\%ws", v20[0], v5);
    v6 = (const WCHAR *)pszPath;
    if ( v23 > 7 )
      v6 = pszPath[0];
    if ( PathFileExistsW(v6) )
    {
      v7 = (const WCHAR *)pszPath;
      if ( v23 > 7 )
        v7 = pszPath[0];
      if ( !PathIsDirectoryW(v7) )
      {
        v8 = (const WCHAR *)pszPath;
        if ( v23 > 7 )
          v8 = pszPath[0];
        if ( !DeleteFileW(v8) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x105,
            (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.ui.startscreen\\tilecollection.cpp",
            v9);
      }
    }
    v10 = (const WCHAR *)pszPath;
    if ( v23 > 7 )
      v10 = pszPath[0];
    if ( !PathIsDirectoryW(v10) )
    {
      v12 = pszPath;
      if ( v23 > 7 )
        v12 = (LPCWSTR *)pszPath[0];
      DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow((wil *)v12, v11);
      if ( DirectoryDeepNoThrow < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x10A,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.ui.startscreen\\tilecollection.cpp",
          (const char *)(unsigned int)DirectoryDeepNoThrow,
          v18);
    }
    std::wstring::operator std::wstring_view(pszPath, v21);
    winrt::hstring::hstring(a1, v21);
    std::filesystem::path::~path((std::filesystem::path *)pszPath);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(v20);
    winrt::handle_type<winrt::impl::hstring_traits>::close(packageFullNameLength);
  }
  return a1;
}

```

## disassembly

```asm
0x18044ca30  mov     [rsp-8+arg_10], rsi
0x18044ca35  mov     [rsp-8+arg_18], rdi
0x18044ca3a  push    rbp
0x18044ca3b  mov     rbp, rsp
0x18044ca3e  sub     rsp, 80h
0x18044ca45  mov     rax, cs:__security_cookie
0x18044ca4c  xor     rax, rsp
0x18044ca4f  mov     [rbp+var_8], rax
0x18044ca53  mov     rsi, rdx
0x18044ca56  mov     rdi, rcx
0x18044ca59  mov     [rbp+var_48], rcx
0x18044ca5d  mov     [rbp+packageFullNameLength], 0
0x18044ca64  xor     edx, edx; packageFullName
0x18044ca66  lea     rcx, [rbp+packageFullNameLength]; packageFullNameLength
0x18044ca6a  call    cs:__imp_GetCurrentPackageFullName
0x18044ca70  cmp     eax, 7Ah ; 'z'
0x18044ca73  jz      loc_18044CBCD
0x18044ca79  cmp     eax, 3D54h
0x18044ca7e  jz      short loc_18044CA98
0x18044ca80  mov     rcx, [rbp+8]; this
0x18044ca84  mov     r9d, eax; char *
0x18044ca87  lea     r8, aShellcommonUnd_158; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18044ca8e  mov     edx, 35h ; '5'; void *
0x18044ca93  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18044ca98  lea     rdx, [rbp+packageFullNameLength]
0x18044ca9c  mov     rcx, rsi
0x18044ca9f  call    ?CacheSubfolder@?$consume_WindowsUdk_UI_StartScreen_ITileCollectionCreateOptions2@UTileCollectionCreateOptions@StartScreen@UI@WindowsUdk@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUdk_UI_StartScreen_ITileCollectionCreateOptions2<winrt::WindowsUdk::UI::StartScreen::TileCollectionCreateOptions>::CacheSubfolder(void)
0x18044caa4  nop
0x18044caa5  cmp     qword ptr [rbp+packageFullNameLength], 0
0x18044caaa  setz    al
0x18044caad  mov     rcx, [rbp+8]; this
0x18044cab1  lea     rdx, aUnpackagedCall; "Unpackaged callers must specify a cache"...
0x18044cab8  mov     qword ptr [rsp+80h+var_58], rdx; bool
0x18044cabd  mov     [rsp+80h+var_60], al; int
0x18044cac1  mov     r9d, 8007139Fh; char *
0x18044cac7  lea     r8, aShellcommonUnd_158; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18044cace  mov     edx, 0FBh; void *
0x18044cad3  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18044cad8  lea     rdx, aLocalappdataMi; "%localappdata%\\Microsoft\\Windows\\Til"...
0x18044cadf  lea     rcx, [rbp+var_48]
0x18044cae3  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x18044cae8  nop
0x18044cae9  lea     rcx, [rbp+packageFullNameLength]; this
0x18044caed  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x18044caf2  mov     r9, rax
0x18044caf5  mov     r8, [rbp+var_48]
0x18044caf9  lea     rdx, aWsWs_0; "%ws\\%ws"
0x18044cb00  lea     rcx, [rbp+pszPath]
0x18044cb04  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x18044cb09  nop
0x18044cb0a  lea     rcx, [rbp+pszPath]
0x18044cb0e  cmp     [rbp+var_10], 7
0x18044cb13  cmova   rcx, [rbp+pszPath]; pszPath
0x18044cb18  call    cs:__imp_PathFileExistsW
0x18044cb1e  test    eax, eax
0x18044cb20  jz      short loc_18044CB5A
0x18044cb22  lea     rcx, [rbp+pszPath]
0x18044cb26  cmp     [rbp+var_10], 7
0x18044cb2b  cmova   rcx, [rbp+pszPath]; pszPath
0x18044cb30  call    cs:__imp_PathIsDirectoryW
0x18044cb36  test    eax, eax
0x18044cb38  jnz     short loc_18044CB5A
0x18044cb3a  lea     rcx, [rbp+pszPath]
0x18044cb3e  cmp     [rbp+var_10], 7
0x18044cb43  cmova   rcx, [rbp+pszPath]; lpFileName
0x18044cb48  mov     rsi, [rbp+8]
0x18044cb4c  call    cs:__imp_DeleteFileW
0x18044cb52  test    eax, eax
0x18044cb54  jz      loc_18044CC86
0x18044cb5a  lea     rcx, [rbp+pszPath]
0x18044cb5e  cmp     [rbp+var_10], 7
0x18044cb63  cmova   rcx, [rbp+pszPath]; pszPath
0x18044cb68  call    cs:__imp_PathIsDirectoryW
0x18044cb6e  test    eax, eax
0x18044cb70  jnz     short loc_18044CB91
0x18044cb72  lea     rcx, [rbp+pszPath]
0x18044cb76  cmp     [rbp+var_10], 7
0x18044cb7b  cmova   rcx, [rbp+pszPath]; this
0x18044cb80  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEB_W@Z; wil::CreateDirectoryDeepNoThrow(wchar_t const *)
0x18044cb85  mov     rcx, [rbp+8]; this
0x18044cb89  test    eax, eax
0x18044cb8b  js      loc_18044CC71
0x18044cb91  lea     rdx, [rbp+var_38]
0x18044cb95  lea     rcx, [rbp+pszPath]
0x18044cb99  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18044cb9e  lea     rdx, [rbp+var_38]
0x18044cba2  mov     rcx, rdi
0x18044cba5  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x18044cbaa  nop
0x18044cbab  lea     rcx, [rbp+pszPath]; this
0x18044cbaf  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18044cbb4  nop
0x18044cbb5  lea     rcx, [rbp+var_48]
0x18044cbb9  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18044cbbe  nop
0x18044cbbf  lea     rcx, [rbp+packageFullNameLength]
0x18044cbc3  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18044cbc8  jmp     loc_18044CC4D
0x18044cbcd  lea     rdx, [rbp+packageFullNameLength]
0x18044cbd1  mov     rcx, rsi
0x18044cbd4  call    ?CacheSubfolder@?$consume_WindowsUdk_UI_StartScreen_ITileCollectionCreateOptions2@UTileCollectionCreateOptions@StartScreen@UI@WindowsUdk@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUdk_UI_StartScreen_ITileCollectionCreateOptions2<winrt::WindowsUdk::UI::StartScreen::TileCollectionCreateOptions>::CacheSubfolder(void)
0x18044cbd9  nop
0x18044cbda  cmp     qword ptr [rax], 0
0x18044cbde  setnz   al
0x18044cbe1  mov     rcx, [rbp+8]; this
0x18044cbe5  lea     rdx, aPackagedCaller; "Packaged callers shouldn't specify a ca"...
0x18044cbec  mov     qword ptr [rsp+80h+var_58], rdx; bool
0x18044cbf1  mov     [rsp+80h+var_60], al; char
0x18044cbf5  mov     r9d, 8007139Fh; char *
0x18044cbfb  lea     r8, aShellcommonUnd_158; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18044cc02  mov     edx, 0F3h; void *
0x18044cc07  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18044cc0c  nop
0x18044cc0d  lea     rcx, [rbp+packageFullNameLength]
0x18044cc11  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18044cc16  lea     rcx, [rbp+var_48]
0x18044cc1a  call    ?Current@ApplicationData@Storage@Windows@winrt@@SA@XZ; winrt::Windows::Storage::ApplicationData::Current(void)
0x18044cc1f  nop
0x18044cc20  lea     rdx, [rbp+packageFullNameLength]
0x18044cc24  lea     rcx, [rbp+var_48]
0x18044cc28  call    ?ExtendedProperties@?$consume_Windows_Internal_IAutomaticDestinationListItemInfo@UIAutomaticDestinationListItemInfo@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_IAutomaticDestinationListItemInfo<winrt::Windows::Internal::IAutomaticDestinationListItemInfo>::ExtendedProperties(void)
0x18044cc2d  nop
0x18044cc2e  mov     rdx, rdi
0x18044cc31  mov     rcx, rax
0x18044cc34  call    ?Path@?$consume_Windows_Storage_IStorageItem@UIStorageFolder@Storage@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Storage_IStorageItem<winrt::Windows::Storage::IStorageFolder>::Path(void)
0x18044cc39  nop
0x18044cc3a  lea     rcx, [rbp+packageFullNameLength]; this
0x18044cc3e  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x18044cc43  nop
0x18044cc44  lea     rcx, [rbp+var_48]; this
0x18044cc48  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x18044cc4d  mov     rax, rdi
0x18044cc50  mov     rcx, [rbp+var_8]
0x18044cc54  xor     rcx, rsp; StackCookie
0x18044cc57  call    __security_check_cookie
0x18044cc5c  lea     r11, [rsp+80h+var_s0]
0x18044cc64  mov     rsi, [r11+20h]
0x18044cc68  mov     rdi, [r11+28h]
0x18044cc6c  mov     rsp, r11
0x18044cc6f  pop     rbp
0x18044cc70  retn
0x18044cc71  mov     r9d, eax; char *
0x18044cc74  lea     r8, aShellcommonUnd_158; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18044cc7b  mov     edx, 10Ah; void *
0x18044cc80  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18044cc86  lea     r8, aShellcommonUnd_158; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18044cc8d  mov     edx, 105h; void *
0x18044cc92  mov     rcx, rsi; this
0x18044cc95  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
