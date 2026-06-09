# winrt::WindowsUdkInternal::PlatformExtensions::FileAssociations::implementation::UdkDynamicProgIdPlatformExtension::TryGetDynamicProgIdQuerySource(winrt::hstring,winrt::hstring const &)

- ea: `0x18014b114`
- end: `0x18014b4c9`
- name: `?TryGetDynamicProgIdQuerySource@UdkDynamicProgIdPlatformExtension@implementation@FileAssociations@PlatformExtensions@WindowsUdkInternal@winrt@@QEAA?AUIAssociationQuerySource@3Shell@Internal@Windows@6@Uhstring@6@AEBUhstring@6@@Z`
- size: `949`
- prototype: `struct winrt::Windows::Internal::Shell::FileAssociations::IAssociationQuerySource __high(struct winrt::hstring, const struct winrt::hstring *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1802ac600`

## callees

- `0x18000aa40`
- `0x18001cb54`
- `0x180021bbc`
- `0x1800225cc`
- `0x1800227a4`
- `0x180025264`
- `0x180025348`
- `0x1800260c0`
- `0x180026860`
- `0x180027af0`
- `0x18002881c`
- `0x1800535d4`
- `0x180067e90`
- `0x180071cec`
- `0x18009c9b0`
- `0x1800e2ac8`
- `0x18014b114`
- `0x18014b4d0`
- `0x18014b550`
- `0x18014b61c`
- `0x18014b68c`
- `0x18015cb00`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_QuerySourceCreateFromKey` at `0x18014b38d`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_QuerySourceCreateFromKey` at `0x18014b38d`
- `SHCORE!__imp_QuerySourceCreateFromKeyEx` at `0x18014b3d9`
- `SHCORE!__imp_QuerySourceCreateFromKeyEx` at `0x18014b3d9`

## string_xrefs

- `0x18014b319`: `UdkDynamicProgIdPlatformExtension: Unable to locate ProgId information for override %ls`
- `0x18014b29c`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\DynamicProgIdPlatformExtension.cpp`
- `0x18014b32f`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\DynamicProgIdPlatformExtension.cpp`
- `0x18014b41d`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\DynamicProgIdPlatformExtension.cpp`
- `0x18014b286`: `UdkDynamicProgIdPlatformExtension: Expected only one valid override to be present for ProgId %ls`
- `0x18014b411`: `pszSubKey = %ws, pszFileExtOrProtocol = %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
_QWORD *__fastcall winrt::WindowsUdkInternal::PlatformExtensions::FileAssociations::implementation::UdkDynamicProgIdPlatformExtension::TryGetDynamicProgIdQuerySource(
        __int64 a1,
        _QWORD *a2,
        const struct winrt::hstring *a3,
        winrt::hstring *a4)
{
  __int64 MsixProgIdMap; // rax
  __int64 v8; // rbx
  __int64 *i; // r14
  int v10; // ebx
  __int64 v11; // rax
  _QWORD *v12; // rdx
  const char *v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rax
  const char *v17; // rdx
  char **v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  char **v21; // rdx
  int v22; // eax
  const wchar_t *v23; // rax
  const char *v24; // r9
  const char *v25; // rdx
  __int64 v27; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v28; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v29[4]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v30[7]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD *v31; // [rsp+A8h] [rbp-58h]
  _BYTE v32[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v33[32]; // [rsp+D0h] [rbp-30h] BYREF
  const struct winrt::hstring *v34; // [rsp+F0h] [rbp-10h]
  __int64 v35; // [rsp+F8h] [rbp-8h] BYREF
  char *v36[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v37; // [rsp+110h] [rbp+10h]
  unsigned __int64 v38; // [rsp+118h] [rbp+18h]
  __int128 v39; // [rsp+120h] [rbp+20h] BYREF
  __int64 v40; // [rsp+130h] [rbp+30h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v29[0] = a2;
  v34 = a3;
  if ( !*(_QWORD *)a3 )
  {
    *a2 = 0;
    goto LABEL_35;
  }
  winrt::WindowsUdkInternal::PlatformExtensions::FileAssociations::implementation::UdkDynamicProgIdPlatformExtension::UpdateCacheState(1);
  v28 = 0;
  wil::AcquireSRWLockShared(
    &v28,
    &winrt::WindowsUdkInternal::PlatformExtensions::FileAssociations::implementation::UdkDynamicProgIdPlatformExtension::s_srwLock);
  MsixProgIdMap = winrt::WindowsUdkInternal::PlatformExtensions::FileAssociations::implementation::UdkDynamicProgIdPlatformExtension::GetMsixProgIdMap();
  v8 = std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::hstring,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::hstring>>,0>>::_Find<winrt::hstring>(
         MsixProgIdMap,
         a3);
  if ( v8 != *(_QWORD *)winrt::WindowsUdkInternal::PlatformExtensions::FileAssociations::implementation::UdkDynamicProgIdPlatformExtension::GetMsixProgIdMap() )
    winrt::hstring::operator=(a3, v8 + 40);
  for ( i = &qword_1804B0580; ; i += 5 )
  {
    if ( i == (__int64 *)&winrt::impl::heap_implements<winrt::WindowsUdk::System::UserProfile::implementation::MicrosoftAccountEngagementCoordinator>::`vftable' )
    {
      *a2 = 0;
      goto LABEL_32;
    }
    v39 = 0;
    v40 = 0;
    v10 = winrt::WindowsUdkInternal::PlatformExtensions::FileAssociations::implementation::UdkDynamicProgIdPlatformExtension::s_extensionCache;
    winrt::hstring::hstring((winrt::hstring *)&v27, a3);
    v30[0] = &std::_Func_impl_no_alloc<_lambda_6f1988c76c87fa02a56952e5281aec21_,bool,std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo> const &>::`vftable';
    v11 = v27;
    v27 = 0;
    v30[1] = v11;
    v31 = v30;
    winrt::hstring::hstring((winrt::hstring *)v29, (const wchar_t *)i[1]);
    winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionCache::GetFilteredExtensionList(
      v10,
      (unsigned int)&v39,
      (unsigned int)v29,
      0,
      (__int64)v30);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v29);
    if ( v31 )
    {
      v12 = v30;
      LOBYTE(v12) = v31 != v30;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v31 + 32LL))(v31, v12);
      v31 = 0;
    }
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v27);
    v13 = (const char *)winrt::hstring::c_str(a3);
    wil::details::in1diag3::Log_HrIfMsg(
      retaddr,
      (void *)0xF2,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\DynamicProgIdPlatformExtension.cpp",
      (const char *)0x8000FFFFLL,
      (unsigned __int64)((__int64)(*((_QWORD *)&v39 + 1) - v39) >> 4) > 1,
      (bool)"UdkDynamicProgIdPlatformExtension: Expected only one valid override to be present for ProgId %ls",
      v13);
    if ( (__int64)(*((_QWORD *)&v39 + 1) - v39) >> 4 )
      break;
LABEL_28:
    std::vector<std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo>>::_Tidy(&v39);
  }
  v35 = 0;
  v14 = *(_QWORD *)v39;
  v15 = std::wstring::wstring(v32, L"DynamicProgId::OverrideProgId");
  winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::GetProperty(v14, v36, v15);
  v16 = winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Id(*(_QWORD *)v39, v33);
  v17 = (const char *)v16;
  if ( *(_QWORD *)(v16 + 24) > 7u )
    v17 = *(const char **)v16;
  wil::details::in1diag3::Log_HrIfMsg(
    retaddr,
    (void *)0xF7,
    (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\DynamicProgIdPlatformExtension.cpp",
    (const char *)0x8000FFFFLL,
    v37 == 0,
    (bool)"UdkDynamicProgIdPlatformExtension: Unable to locate ProgId information for override %ls",
    v17);
  std::filesystem::path::~path((std::filesystem::path *)v33);
  if ( !v37 )
  {
LABEL_26:
    std::filesystem::path::~path((std::filesystem::path *)v36);
    if ( v35 )
      winrt::com_ptr<Windows::Internal::Shell::Experience::ITrayMtcUvcFlyoutExperienceManager>::unconditional_release_ref(&v35);
    goto LABEL_28;
  }
  if ( v35 )
    winrt::com_ptr<Windows::Internal::Shell::Experience::ITrayMtcUvcFlyoutExperienceManager>::unconditional_release_ref(&v35);
  v18 = v36;
  if ( v38 > 7 )
    v18 = (char **)v36[0];
  if ( (int)QuerySourceCreateFromKey(0xFFFFFFFF80000000uLL, v18, 0, &GUID_7bc28ac2_0d9c_4941_bb9a_72becb184fac, &v35) < 0 )
  {
    if ( v35 )
      winrt::com_ptr<Windows::Internal::Shell::Experience::ITrayMtcUvcFlyoutExperienceManager>::unconditional_release_ref(&v35);
    v21 = v36;
    if ( v38 > 7 )
      v21 = (char **)v36[0];
    v22 = QuerySourceCreateFromKeyEx(
            0xFFFFFFFF80000000uLL,
            v21,
            0,
            512,
            &GUID_7bc28ac2_0d9c_4941_bb9a_72becb184fac,
            &v35);
    v20 = (unsigned int)v22;
    if ( v22 < 0 )
    {
      if ( v22 != -2147024894 )
      {
        v23 = winrt::hstring::c_str(a4);
        v25 = (const char *)v36;
        if ( v38 > 7 )
          v25 = v36[0];
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x109,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\DynamicProgIdPlatf"
                        "ormExtension.cpp",
          v24,
          (int)"pszSubKey = %ws, pszFileExtOrProtocol = %ws",
          v25,
          v23);
      }
      goto LABEL_26;
    }
  }
  winrt::impl::as<winrt::Windows::Internal::Shell::FileAssociations::IAssociationQuerySource,IQuerySource,0>(
    a2,
    v35,
    v19,
    v20);
  std::filesystem::path::~path((std::filesystem::path *)v36);
  if ( v35 )
    winrt::com_ptr<Windows::Internal::Shell::Experience::ITrayMtcUvcFlyoutExperienceManager>::unconditional_release_ref(&v35);
  std::vector<std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo>>::_Tidy(&v39);
LABEL_32:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v28);
LABEL_35:
  winrt::handle_type<winrt::impl::hstring_traits>::close(a3);
  return a2;
}

```

## disassembly

```asm
0x18014b114  push    rbp
0x18014b116  push    rbx
0x18014b117  push    rsi
0x18014b118  push    rdi
0x18014b119  push    r12
0x18014b11b  push    r14
0x18014b11d  push    r15
0x18014b11f  lea     rbp, [rsp-40h]
0x18014b124  sub     rsp, 140h
0x18014b12b  mov     rax, cs:__security_cookie
0x18014b132  xor     rax, rsp
0x18014b135  mov     [rbp+70h+var_38], rax
0x18014b139  mov     r15, r9
0x18014b13c  mov     rsi, r8
0x18014b13f  mov     rdi, rdx
0x18014b142  mov     [rsp+170h+var_120], rdx
0x18014b147  mov     [rbp+70h+var_80], r8
0x18014b14b  xor     r12d, r12d
0x18014b14e  cmp     [r8], r12
0x18014b151  jz      loc_18014B49D
0x18014b157  mov     cl, 1; bool
0x18014b159  call    ?UpdateCacheState@UdkDynamicProgIdPlatformExtension@implementation@FileAssociations@PlatformExtensions@WindowsUdkInternal@winrt@@CAX_N@Z; winrt::WindowsUdkInternal::PlatformExtensions::FileAssociations::implementation::UdkDynamicProgIdPlatformExtension::UpdateCacheState(bool)
0x18014b15e  mov     [rsp+170h+var_128], r12
0x18014b163  lea     rdx, ?s_srwLock@UdkDynamicProgIdPlatformExtension@implementation@FileAssociations@PlatformExtensions@WindowsUdkInternal@winrt@@0Vsrwlock@wil@@A; wil::srwlock winrt::WindowsUdkInternal::PlatformExtensions::FileAssociations::implementation::UdkDynamicProgIdPlatformExtension::s_srwLock
0x18014b16a  lea     rcx, [rsp+170h+var_128]
0x18014b16f  call    ?AcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockShared(_RTL_SRWLOCK *)
0x18014b174  nop
0x18014b175  call    ?GetMsixProgIdMap@UdkDynamicProgIdPlatformExtension@implementation@FileAssociations@PlatformExtensions@WindowsUdkInternal@winrt@@CAAEAV?$map@Uhstring@winrt@@U12@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@U12@@std@@@4@@std@@XZ; winrt::WindowsUdkInternal::PlatformExtensions::FileAssociations::implementation::UdkDynamicProgIdPlatformExtension::GetMsixProgIdMap(void)
0x18014b17a  mov     rdx, rsi
0x18014b17d  mov     rcx, rax
0x18014b180  call    ??$_Find@Uhstring@winrt@@@?$_Tree@V?$_Tmap_traits@Uhstring@winrt@@U12@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@U12@@std@@@4@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBUhstring@winrt@@U12@@std@@PEAX@1@AEBUhstring@winrt@@@Z; std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::hstring,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::hstring>>,0>>::_Find<winrt::hstring>(winrt::hstring const &)
0x18014b185  mov     rbx, rax
0x18014b188  call    ?GetMsixProgIdMap@UdkDynamicProgIdPlatformExtension@implementation@FileAssociations@PlatformExtensions@WindowsUdkInternal@winrt@@CAAEAV?$map@Uhstring@winrt@@U12@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@U12@@std@@@4@@std@@XZ; winrt::WindowsUdkInternal::PlatformExtensions::FileAssociations::implementation::UdkDynamicProgIdPlatformExtension::GetMsixProgIdMap(void)
0x18014b18d  cmp     rbx, [rax]
0x18014b190  jz      short loc_18014B19E
0x18014b192  lea     rdx, [rbx+28h]
0x18014b196  mov     rcx, rsi
0x18014b199  call    ??4hstring@winrt@@QEAAAEAU01@AEBU01@@Z; winrt::hstring::operator=(winrt::hstring const &)
0x18014b19e  lea     r14, qword_1804B0580
0x18014b1a5  lea     rax, ??_7?$heap_implements@UMicrosoftAccountEngagementCoordinator@implementation@UserProfile@System@WindowsUdk@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::WindowsUdk::System::UserProfile::implementation::MicrosoftAccountEngagementCoordinator>::`vftable'
0x18014b1ac  cmp     r14, rax
0x18014b1af  jz      loc_18014B498
0x18014b1b5  xorps   xmm0, xmm0
0x18014b1b8  xor     eax, eax
0x18014b1ba  movups  [rbp+70h+var_50], xmm0
0x18014b1be  mov     [rbp+70h+var_40], rax
0x18014b1c2  mov     rbx, cs:?s_extensionCache@UdkDynamicProgIdPlatformExtension@implementation@FileAssociations@PlatformExtensions@WindowsUdkInternal@winrt@@0V?$shared_ptr@VExtensionCache@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@A; std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionCache> winrt::WindowsUdkInternal::PlatformExtensions::FileAssociations::implementation::UdkDynamicProgIdPlatformExtension::s_extensionCache
0x18014b1c9  mov     rdx, rsi; struct winrt::hstring *
0x18014b1cc  lea     rcx, [rsp+170h+var_130]; this
0x18014b1d1  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x18014b1d6  nop
0x18014b1d7  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_6f1988c76c87fa02a56952e5281aec21_@@_NAEBV?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_6f1988c76c87fa02a56952e5281aec21_,bool,std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo> const &>::`vftable'
0x18014b1de  mov     [rsp+170h+var_100], rax
0x18014b1e3  mov     rax, [rsp+170h+var_130]
0x18014b1e8  mov     [rsp+170h+var_130], r12
0x18014b1ed  mov     [rsp+170h+var_F8], rax
0x18014b1f2  lea     rax, [rsp+170h+var_100]
0x18014b1f7  mov     [rbp+70h+var_C8], rax
0x18014b1fb  mov     rdx, [r14+8]; wchar_t *
0x18014b1ff  lea     rcx, [rsp+170h+var_120]; this
0x18014b204  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x18014b209  nop
0x18014b20a  lea     rax, [rsp+170h+var_100]
0x18014b20f  mov     qword ptr [rsp+170h+var_150], rax
0x18014b214  xor     r9d, r9d
0x18014b217  lea     r8, [rsp+170h+var_120]
0x18014b21c  lea     rdx, [rbp+70h+var_50]
0x18014b220  mov     rcx, rbx
0x18014b223  call    ?GetFilteredExtensionList@ExtensionCache@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEAA?AV?$vector@V?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@V?$allocator@V?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@@2@@std@@AEBUhstring@6@W4CacheEnumerationOptions@23456@$$QEAV?$function@$$A6A_NAEBV?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@@Z@8@@Z; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionCache::GetFilteredExtensionList(winrt::hstring const &,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::CacheEnumerationOptions,std::function<bool (std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo> const &)> &&)
0x18014b228  nop
0x18014b229  lea     rcx, [rsp+170h+var_120]
0x18014b22e  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18014b233  nop
0x18014b234  mov     rcx, [rbp+70h+var_C8]
0x18014b238  test    rcx, rcx
0x18014b23b  jz      short loc_18014B258
0x18014b23d  mov     rax, [rcx]
0x18014b240  lea     rdx, [rsp+170h+var_100]
0x18014b245  cmp     rcx, rdx
0x18014b248  setnz   dl
0x18014b24b  mov     rax, [rax+20h]
0x18014b24f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014b254  mov     [rbp+70h+var_C8], r12
0x18014b258  lea     rcx, [rsp+170h+var_130]
0x18014b25d  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18014b262  mov     rcx, rsi; this
0x18014b265  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x18014b26a  mov     rcx, qword ptr [rbp+70h+var_50+8]
0x18014b26e  sub     rcx, qword ptr [rbp+70h+var_50]
0x18014b272  sar     rcx, 4
0x18014b276  cmp     rcx, 1
0x18014b27a  setnbe  dl
0x18014b27d  mov     rcx, [rbp+78h]; this
0x18014b281  mov     [rsp+170h+var_140], rax; char *
0x18014b286  lea     rax, aUdkdynamicprog; "UdkDynamicProgIdPlatformExtension: Expe"...
0x18014b28d  mov     [rsp+170h+var_148], rax; bool
0x18014b292  mov     [rsp+170h+var_150], dl; char
0x18014b296  mov     r9d, 8000FFFFh; char *
0x18014b29c  lea     r8, aShellcommonUnd_37; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18014b2a3  mov     edx, 0F2h; void *
0x18014b2a8  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18014b2ad  mov     rax, qword ptr [rbp+70h+var_50+8]
0x18014b2b1  mov     rbx, qword ptr [rbp+70h+var_50]
0x18014b2b5  sub     rax, rbx
0x18014b2b8  sar     rax, 4
0x18014b2bc  test    rax, rax
0x18014b2bf  jz      loc_18014B449
0x18014b2c5  mov     [rbp+70h+var_78], r12
0x18014b2c9  mov     rbx, [rbx]
0x18014b2cc  lea     rdx, aDynamicprogidO; "DynamicProgId::OverrideProgId"
0x18014b2d3  lea     rcx, [rbp+70h+var_C0]
0x18014b2d7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18014b2dc  mov     r8, rax
0x18014b2df  lea     rdx, [rbp+70h+var_70]
0x18014b2e3  mov     rcx, rbx
0x18014b2e6  call    ?GetProperty@ExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V78@@Z; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::GetProperty(std::wstring)
0x18014b2eb  nop
0x18014b2ec  lea     rdx, [rbp+70h+var_A0]
0x18014b2f0  mov     rcx, qword ptr [rbp+70h+var_50]
0x18014b2f4  mov     rcx, [rcx]
0x18014b2f7  call    ?Id@ExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Id(void)
0x18014b2fc  mov     rdx, rax
0x18014b2ff  cmp     qword ptr [rax+18h], 7
0x18014b304  jbe     short loc_18014B309
0x18014b306  mov     rdx, [rax]
0x18014b309  cmp     [rbp+70h+var_60], r12
0x18014b30d  setz    al
0x18014b310  mov     rcx, [rbp+78h]; this
0x18014b314  mov     [rsp+170h+var_140], rdx; char *
0x18014b319  lea     rdx, aUdkdynamicprog_0; "UdkDynamicProgIdPlatformExtension: Unab"...
0x18014b320  mov     [rsp+170h+var_148], rdx; bool
0x18014b325  mov     [rsp+170h+var_150], al; char
0x18014b329  mov     r9d, 8000FFFFh; char *
0x18014b32f  lea     r8, aShellcommonUnd_37; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18014b336  mov     edx, 0F7h; void *
0x18014b33b  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18014b340  lea     rcx, [rbp+70h+var_A0]; this
0x18014b344  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18014b349  cmp     [rbp+70h+var_60], r12
0x18014b34d  jz      loc_18014B42F
0x18014b353  cmp     [rbp+70h+var_78], r12
0x18014b357  jz      short loc_18014B362
0x18014b359  lea     rcx, [rbp+70h+var_78]
0x18014b35d  call    ?unconditional_release_ref@?$com_ptr@UITrayMtcUvcFlyoutExperienceManager@Experience@Shell@Internal@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Internal::Shell::Experience::ITrayMtcUvcFlyoutExperienceManager>::unconditional_release_ref(void)
0x18014b362  lea     rdx, [rbp+70h+var_70]
0x18014b366  cmp     [rbp+70h+var_58], 7
0x18014b36b  cmova   rdx, [rbp+70h+var_70]
0x18014b370  lea     rax, [rbp+70h+var_78]
0x18014b374  mov     qword ptr [rsp+170h+var_150], rax
0x18014b379  lea     r9, _GUID_7bc28ac2_0d9c_4941_bb9a_72becb184fac
0x18014b380  xor     r8d, r8d
0x18014b383  mov     rbx, 0FFFFFFFF80000000h
0x18014b38a  mov     rcx, rbx
0x18014b38d  call    cs:__imp_QuerySourceCreateFromKey
0x18014b393  test    eax, eax
0x18014b395  jns     loc_18014B45B
0x18014b39b  cmp     [rbp+70h+var_78], r12
0x18014b39f  jz      short loc_18014B3AA
0x18014b3a1  lea     rcx, [rbp+70h+var_78]
0x18014b3a5  call    ?unconditional_release_ref@?$com_ptr@UITrayMtcUvcFlyoutExperienceManager@Experience@Shell@Internal@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Internal::Shell::Experience::ITrayMtcUvcFlyoutExperienceManager>::unconditional_release_ref(void)
0x18014b3aa  lea     rdx, [rbp+70h+var_70]
0x18014b3ae  cmp     [rbp+70h+var_58], 7
0x18014b3b3  cmova   rdx, [rbp+70h+var_70]
0x18014b3b8  lea     rax, [rbp+70h+var_78]
0x18014b3bc  mov     [rsp+170h+var_148], rax
0x18014b3c1  lea     rax, _GUID_7bc28ac2_0d9c_4941_bb9a_72becb184fac
0x18014b3c8  mov     qword ptr [rsp+170h+var_150], rax
0x18014b3cd  mov     r9d, 200h
0x18014b3d3  xor     r8d, r8d
0x18014b3d6  mov     rcx, rbx
0x18014b3d9  call    cs:__imp_QuerySourceCreateFromKeyEx
0x18014b3df  mov     r9d, eax
0x18014b3e2  test    eax, eax
0x18014b3e4  jns     short loc_18014B45B
0x18014b3e6  cmp     eax, 80070002h
0x18014b3eb  jz      short loc_18014B42F
0x18014b3ed  mov     rcx, r15; this
0x18014b3f0  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x18014b3f5  lea     rdx, [rbp+70h+var_70]
0x18014b3f9  cmp     [rbp+70h+var_58], 7
0x18014b3fe  cmova   rdx, [rbp+70h+var_70]
0x18014b403  mov     rcx, [rbp+78h]; this
0x18014b407  mov     [rsp+170h+var_140], rax
0x18014b40c  mov     [rsp+170h+var_148], rdx; char *
0x18014b411  lea     rax, aPszsubkeyWsPsz; "pszSubKey = %ws, pszFileExtOrProtocol ="...
0x18014b418  mov     qword ptr [rsp+170h+var_150], rax; int
0x18014b41d  lea     r8, aShellcommonUnd_37; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18014b424  mov     edx, 109h; void *
0x18014b429  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18014b42e  nop
0x18014b42f  lea     rcx, [rbp+70h+var_70]; this
0x18014b433  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18014b438  nop
0x18014b439  cmp     [rbp+70h+var_78], r12
0x18014b43d  jz      short loc_18014B449
0x18014b43f  lea     rcx, [rbp+70h+var_78]
0x18014b443  call    ?unconditional_release_ref@?$com_ptr@UITrayMtcUvcFlyoutExperienceManager@Experience@Shell@Internal@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Internal::Shell::Experience::ITrayMtcUvcFlyoutExperienceManager>::unconditional_release_ref(void)
0x18014b448  nop
0x18014b449  lea     rcx, [rbp+70h+var_50]
0x18014b44d  call    ?_Tidy@?$vector@V?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@V?$allocator@V?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo>>::_Tidy(void)
0x18014b452  add     r14, 28h ; '('
0x18014b456  jmp     loc_18014B1A5
0x18014b45b  mov     rdx, [rbp+70h+var_78]
0x18014b45f  mov     rcx, rdi
0x18014b462  call    ??$as@UIAssociationQuerySource@FileAssociations@Shell@Internal@Windows@winrt@@UIQuerySource@@$0A@@impl@winrt@@YA?AUIAssociationQuerySource@FileAssociations@Shell@Internal@Windows@1@PEAUIQuerySource@@@Z; winrt::impl::as<winrt::Windows::Internal::Shell::FileAssociations::IAssociationQuerySource,IQuerySource,0>(IQuerySource *)
0x18014b467  nop
0x18014b468  lea     rcx, [rbp+70h+var_70]; this
0x18014b46c  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18014b471  nop
0x18014b472  cmp     [rbp+70h+var_78], r12
0x18014b476  jz      short loc_18014B482
0x18014b478  lea     rcx, [rbp+70h+var_78]
0x18014b47c  call    ?unconditional_release_ref@?$com_ptr@UITrayMtcUvcFlyoutExperienceManager@Experience@Shell@Internal@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::Internal::Shell::Experience::ITrayMtcUvcFlyoutExperienceManager>::unconditional_release_ref(void)
0x18014b481  nop
0x18014b482  lea     rcx, [rbp+70h+var_50]
0x18014b486  call    ?_Tidy@?$vector@V?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@V?$allocator@V?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo>>::_Tidy(void)
0x18014b48b  nop
0x18014b48c  lea     rcx, [rsp+170h+var_128]
0x18014b491  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18014b496  jmp     short loc_18014B4A0
0x18014b498  mov     [rdi], r12
0x18014b49b  jmp     short loc_18014B48C
0x18014b49d  mov     [rdx], r12
0x18014b4a0  mov     rcx, rsi
0x18014b4a3  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18014b4a8  mov     rax, rdi
0x18014b4ab  mov     rcx, [rbp+70h+var_38]
0x18014b4af  xor     rcx, rsp; StackCookie
0x18014b4b2  call    __security_check_cookie
0x18014b4b7  add     rsp, 140h
0x18014b4be  pop     r15
0x18014b4c0  pop     r14
0x18014b4c2  pop     r12
0x18014b4c4  pop     rdi
0x18014b4c5  pop     rsi
0x18014b4c6  pop     rbx
0x18014b4c7  pop     rbp
0x18014b4c8  retn
```
