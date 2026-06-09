# ShellHostHelpers::LaunchComponent(winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)

- ea: `0x18042a720`
- end: `0x18042ada1`
- name: `?LaunchComponent@ShellHostHelpers@@YAXAEBUhstring@winrt@@000AEBUValueSet@Collections@Foundation@Windows@3@@Z`
- size: `1665`
- prototype: `void __fastcall(ShellHostHelpers *__hidden this, const struct winrt::hstring *, const struct winrt::hstring *, const struct winrt::hstring *, const struct winrt::hstring *, const struct winrt::Windows::Foundation::Collections::ValueSet *)`
- caller_count: `2`
- callee_count: `40`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18042a614`
- `0x18042ada8`

## callees

- `0x18000b428`
- `0x180011e64`
- `0x180011f98`
- `0x180013490`
- `0x180025348`
- `0x1800260c0`
- `0x180026860`
- `0x180027af0`
- `0x18002ddb0`
- `0x180037df8`
- `0x18004ad84`
- `0x180052b80`
- `0x18005edb0`
- `0x180062160`
- `0x180077910`
- `0x180087cf8`
- `0x1800a14f8`
- `0x1800f0710`
- `0x1800f0ab8`
- `0x18013bcf8`
- `0x18013f98c`
- `0x18013fa00`
- `0x1801505c4`
- `0x1801588c4`
- `0x18015cb00`
- `0x18015d868`
- `0x1802aec7c`
- `0x1802b0c58`
- `0x1804226e8`
- `0x18042287c`
- `0x18042391c`
- `0x1804262c4`
- `0x1804262f4`
- `0x180429910`
- `0x18042a720`
- `0x18042b960`
- `0x18042d114`
- `0x18042e98c`
- `0x1804303c8`
- `0x180430404`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18042a79c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18042a79c`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18042ad14`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18042ad14`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18042ac43`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18042ac43`
- `ext-ms-win-rtcore-ntuser-iam-l1-1-2!SetProcessLaunchForegroundPolicy` at `0x18042ad0a`
- `ext-ms-win-rtcore-ntuser-iam-l1-1-2!SetProcessLaunchForegroundPolicy` at `0x18042ad0a`

## string_xrefs

- `0x18042a7b8`: `LauncherProcessID`
- `0x18042a8fb`: ` --extensionCategory `
- `0x18042a92f`: ` --extensionId `
- `0x18042ad8f`: `shellcommon\internal\shell\inc\ShellHostHelpers.h`
- `0x18042a8b1`: `loadComponent`
- `0x18042abc2`: `%WINDIR%\system32\shellhost.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall ShellHostHelpers::LaunchComponent(
        ShellHostHelpers *this,
        const struct winrt::hstring *a2,
        const struct winrt::hstring *a3,
        const struct winrt::hstring *a4,
        const struct winrt::hstring *a5)
{
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rbx
  char v12; // bl
  __int64 v13; // rdi
  const wchar_t *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // r8
  _QWORD *v18; // rax
  __int64 v19; // r9
  __int64 v20; // rax
  __int64 v21; // r8
  _QWORD *v22; // rax
  __int64 v23; // r9
  __int64 v24; // rax
  __int64 v25; // r8
  _QWORD *v26; // rax
  __int64 v27; // r9
  __int64 v28; // rax
  __int64 v29; // r8
  _QWORD *v30; // rax
  __int64 v31; // r9
  __int64 v32; // rax
  __int64 v33; // r8
  _QWORD *v34; // rax
  __int64 v35; // r9
  __int64 v36; // rbx
  __int64 *v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rax
  __int64 v40; // r8
  _QWORD *v41; // rax
  __int64 v42; // r9
  const wchar_t *v43; // rdx
  struct IInspectableVtbl *lpVtbl; // rbx
  const wchar_t *v45; // rax
  __int64 v46; // r8
  wchar_t **v47; // rax
  const char *v48; // r9
  char v49; // bl
  ShellHostHelpers::details::UIContainment *v50; // rdi
  int v51; // ebx
  unsigned int v52; // r8d
  struct _PROCESS_INFORMATION *v53; // rdx
  void *v54; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v55; // [rsp+58h] [rbp-A8h]
  __int64 v56; // [rsp+60h] [rbp-A0h] BYREF
  ShellHostHelpers::details::UIContainment *v57[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v58; // [rsp+78h] [rbp-88h] BYREF
  LPCWSTR lpApplicationName; // [rsp+80h] [rbp-80h] BYREF
  LPWSTR lpCommandLine; // [rsp+88h] [rbp-78h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v62[32]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v63[40]; // [rsp+C8h] [rbp-38h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v65[16]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v66[8]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v67[232]; // [rsp+178h] [rbp+78h] BYREF
  wchar_t *v68[3]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int64 v69; // [rsp+278h] [rbp+178h]
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v56 = *(_QWORD *)a5;
  v9 = v56;
  winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ModalDialog>::add_ref(&v56);
  if ( !v9 )
  {
    v10 = winrt::Windows::Foundation::Collections::ValueSet::ValueSet((winrt::Windows::Foundation::Collections::ValueSet *)&v54);
    winrt::Windows::Foundation::IUnknown::operator=(&v56, v10);
    winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v54);
  }
  LODWORD(v57[0]) = GetCurrentProcessId();
  v11 = winrt::box_value<unsigned int,0>(&v54, v57);
  winrt::param::hstring::hstring((winrt::param::hstring *)v62, L"LauncherProcessID");
  winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
    &v56,
    v62,
    v11);
  if ( v54 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v54);
  winrt::hstring::hstring((winrt::hstring *)&v54, L"SkipSingletonOptimization");
  v12 = ValueSetUtils::details::get_bool_or<winrt::Windows::Foundation::Collections::ValueSet>(&v54, &v56);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v54);
  v13 = -1;
  if ( v12 )
  {
LABEL_11:
    std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v65);
    std::operator<<<wchar_t,std::char_traits<wchar_t>>(v66, L"loadComponent");
    if ( *(_QWORD *)this )
    {
      v16 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v66, L" ");
      v18 = (_QWORD *)winrt::hstring::operator std::wstring_view(this, &v54, v17, v16);
      std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(v19, *v18, v18[1]);
    }
    if ( *(_QWORD *)a2 )
    {
      v20 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v66, L" --extensionCategory ");
      v22 = (_QWORD *)winrt::hstring::operator std::wstring_view(a2, &v54, v21, v20);
      std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(v23, *v22, v22[1]);
    }
    if ( *(_QWORD *)a3 )
    {
      v24 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v66, L" --extensionId ");
      v26 = (_QWORD *)winrt::hstring::operator std::wstring_view(a3, &v54, v25, v24);
      std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(v27, *v26, v26[1]);
    }
    if ( *(_QWORD *)a4 )
    {
      v28 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v66, L" --controlName ");
      v30 = (_QWORD *)winrt::hstring::operator std::wstring_view(a4, &v54, v29, v28);
      std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(v31, *v30, v30[1]);
    }
    if ( v56 )
    {
      ValueSetUtils::SerializeValueSetToBase64(&v54, &v56);
      v32 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v66, L" --valueSet ");
      v34 = (_QWORD *)winrt::hstring::operator std::wstring_view(&v54, v57, v33, v32);
      std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(v35, *v34, v34[1]);
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v54);
    }
    v36 = 0;
    v58 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl) )
    {
      winrt::hstring::hstring(
        (winrt::hstring *)&v54,
        ShellHostHelpers::details::SingleInstanceConstants::TargetShellHostInstanceKey);
      v37 = (__int64 *)ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(
                         v57,
                         &v54,
                         &v56);
      if ( &v58 != v37 )
      {
        v38 = *v37;
        *v37 = 0;
        winrt::handle_type<winrt::impl::hstring_traits>::attach(&v58, v38);
        v36 = v58;
      }
      winrt::handle_type<winrt::impl::hstring_traits>::close(v57);
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v54);
      if ( v36 )
      {
        v39 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v66, L" --instance ");
        v41 = (_QWORD *)winrt::hstring::operator std::wstring_view(&v58, &v54, v40, v39);
        std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(v42, *v41, v41[1]);
      }
    }
    std::wstringbuf::str(v67, v68);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl)
      && v36 )
    {
      winrt::Windows::Foundation::Collections::ValueSet::ValueSet((winrt::Windows::Foundation::Collections::ValueSet *)v57);
      v43 = (const wchar_t *)v68;
      if ( v69 > 7 )
        v43 = v68[0];
      winrt::param::hstring::hstring((winrt::param::hstring *)v62, v43);
      lpVtbl = winrt::box_value((winrt *)&v54, (const struct winrt::param::hstring *)v62).lpVtbl;
      winrt::param::hstring::hstring(v63, &ShellHostHelpers::details::SingleInstanceConstants::CommandLineKey);
      winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
        v57,
        v63,
        lpVtbl);
      if ( v54 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v54);
      v45 = winrt::hstring::c_str((winrt::hstring *)&v58);
      v54 = (void *)v45;
      do
        ++v13;
      while ( v45[v13] );
      v55 = v13;
      if ( (unsigned __int8)SingletonHelpers::SingletonHelper::TryRedirectLaunch(
                              (unsigned int)&ShellHostHelpers::details::SingleInstanceConstants::ShellHostSingletonCategory,
                              (unsigned int)&v54,
                              (unsigned int)v57,
                              0,
                              2,
                              0) )
      {
        winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)v57);
LABEL_46:
        std::filesystem::path::~path((std::filesystem::path *)v68);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v58);
        std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(v65);
        goto LABEL_47;
      }
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)v57);
    }
    *(_QWORD *)&StartupInfo.cb = 104;
    memset_0(&StartupInfo.lpReserved, 0, 0x60u);
    StartupInfo.dwFlags = 128;
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShellHostInBasicJobObject>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShellHostInBasicJobObject>::GetImpl'::`2'::impl);
    wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
      &lpApplicationName,
      L"%WINDIR%\\system32\\shellhost.exe");
    v47 = v68;
    if ( v69 > 7 )
      v47 = (wchar_t **)v68[0];
    v54 = v47;
    v57[0] = (ShellHostHelpers::details::UIContainment *)lpApplicationName;
    wil::str_concat<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wchar_t *,wchar_t const (&)[2],wchar_t const *>(
      &lpCommandLine,
      v57,
      v46,
      &v54);
    if ( !CreateProcessW(lpApplicationName, lpCommandLine, 0, 0, 0, 0x24u, 0, 0, &StartupInfo, &ProcessInformation) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xF2,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\ShellHostHelpers.h",
        v48);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShellHostInBasicJobObject>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShellHostInBasicJobObject>::GetImpl'::`2'::impl) )
    {
      winrt::hstring::hstring((winrt::hstring *)&v54, L"RunInJob");
      v49 = ValueSetUtils::details::get_bool_or<winrt::Windows::Foundation::Collections::ValueSet>(&v54, &v56);
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v54);
      if ( v49 )
      {
        ShellHostHelpers::details::UIContainment::PlaceShellHostIntoContainer(v57, ProcessInformation.hProcess);
        v50 = v57[0];
        if ( (unsigned __int64)v57[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          winrt::hstring::hstring((winrt::hstring *)&v54, L"JobUIRestrictions");
          v51 = ValueSetUtils::get_value_or<unsigned int,winrt::Windows::Foundation::Collections::ValueSet>(
                  &v54,
                  &v56,
                  24);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v54);
          ShellHostHelpers::details::UIContainment::ConfigureContainerWithUILimits(v50, (void *)(v51 | 0x2C0u), v52);
        }
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v57);
      }
    }
    SetProcessLaunchForegroundPolicy(ProcessInformation.dwProcessId, 4);
    ResumeThread(ProcessInformation.hThread);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpCommandLine);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpApplicationName);
    wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v53);
    goto LABEL_46;
  }
  ShellHostHelpers::details::GetOrGenerateSingletonName(v57, this, a2, a3, a4, &v56);
  v14 = winrt::hstring::c_str((winrt::hstring *)v57);
  v54 = (void *)v14;
  v15 = -1;
  do
    ++v15;
  while ( v14[v15] );
  v55 = v15;
  if ( !(unsigned __int8)SingletonHelpers::SingletonHelper::TryRedirectLaunch(
                           (unsigned int)&ShellHostHelpers::details::c_shellHostComponentSingletonCategoryName,
                           (unsigned int)&v54,
                           (unsigned int)&v56,
                           0,
                           2,
                           0) )
  {
    winrt::handle_type<winrt::impl::hstring_traits>::close(v57);
    goto LABEL_11;
  }
  winrt::handle_type<winrt::impl::hstring_traits>::close(v57);
LABEL_47:
  winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v56);
}

```

## disassembly

```asm
0x18042a720  push    rbp
0x18042a722  push    rbx
0x18042a723  push    rsi
0x18042a724  push    rdi
0x18042a725  push    r12
0x18042a727  push    r13
0x18042a729  push    r14
0x18042a72b  push    r15
0x18042a72d  lea     rbp, [rsp-198h]
0x18042a735  sub     rsp, 298h
0x18042a73c  mov     rax, cs:__security_cookie
0x18042a743  xor     rax, rsp
0x18042a746  mov     [rbp+1D0h+var_50], rax
0x18042a74d  mov     rsi, r9
0x18042a750  mov     r14, r8
0x18042a753  mov     r15, rdx
0x18042a756  mov     r12, rcx
0x18042a759  xor     r13d, r13d
0x18042a75c  mov     rax, [rbp+1D0h+arg_20]
0x18042a763  mov     rbx, [rax]
0x18042a766  mov     [rsp+2D0h+var_270], rbx
0x18042a76b  lea     rcx, [rsp+2D0h+var_270]
0x18042a770  call    ?add_ref@?$com_ptr@UModalDialog@implementation@Shell@UI@WindowsUdk@winrt@@@winrt@@AEBAXXZ; winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ModalDialog>::add_ref(void)
0x18042a775  nop
0x18042a776  test    rbx, rbx
0x18042a779  jnz     short loc_18042A79C
0x18042a77b  lea     rcx, [rsp+2D0h+var_280]; this
0x18042a780  call    ??0ValueSet@Collections@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::Collections::ValueSet::ValueSet(void)
0x18042a785  mov     rdx, rax
0x18042a788  lea     rcx, [rsp+2D0h+var_270]
0x18042a78d  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18042a792  lea     rcx, [rsp+2D0h+var_280]; this
0x18042a797  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x18042a79c  call    cs:__imp_GetCurrentProcessId
0x18042a7a2  mov     dword ptr [rsp+2D0h+var_268], eax
0x18042a7a6  lea     rdx, [rsp+2D0h+var_268]
0x18042a7ab  lea     rcx, [rsp+2D0h+var_280]
0x18042a7b0  call    ??$box_value@I$0A@@winrt@@YA?AUIInspectable@Foundation@Windows@0@AEBI@Z; winrt::box_value<uint,0>(uint const &)
0x18042a7b5  mov     rbx, rax
0x18042a7b8  lea     rdx, aLauncherproces; "LauncherProcessID"
0x18042a7bf  lea     rcx, [rbp+1D0h+var_228]; this
0x18042a7c3  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18042a7c8  mov     r8, rbx
0x18042a7cb  lea     rdx, [rbp+1D0h+var_228]
0x18042a7cf  lea     rcx, [rsp+2D0h+var_270]
0x18042a7d4  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x18042a7d9  nop
0x18042a7da  cmp     [rsp+2D0h+var_280], r13
0x18042a7df  jz      short loc_18042A7EB
0x18042a7e1  lea     rcx, [rsp+2D0h+var_280]
0x18042a7e6  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18042a7eb  lea     rdx, aSkipsingletono; "SkipSingletonOptimization"
0x18042a7f2  lea     rcx, [rsp+2D0h+var_280]; this
0x18042a7f7  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x18042a7fc  nop
0x18042a7fd  lea     rdx, [rsp+2D0h+var_270]
0x18042a802  lea     rcx, [rsp+2D0h+var_280]
0x18042a807  call    ??$get_bool_or@UValueSet@Collections@Foundation@Windows@winrt@@@details@ValueSetUtils@@YA_NAEBUhstring@winrt@@AEBUValueSet@Collections@Foundation@Windows@3@_N@Z; ValueSetUtils::details::get_bool_or<winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &,bool)
0x18042a80c  mov     bl, al
0x18042a80e  lea     rcx, [rsp+2D0h+var_280]
0x18042a813  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18042a818  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18042a81c  test    bl, bl
0x18042a81e  jnz     loc_18042A8A7
0x18042a824  lea     rax, [rsp+2D0h+var_270]
0x18042a829  mov     qword ptr [rsp+2D0h+dwCreationFlags], rax
0x18042a82e  mov     qword ptr [rsp+2D0h+bInheritHandles], rsi
0x18042a833  mov     r9, r14
0x18042a836  mov     r8, r15
0x18042a839  mov     rdx, r12
0x18042a83c  lea     rcx, [rsp+2D0h+var_268]
0x18042a841  call    ?GetOrGenerateSingletonName@details@ShellHostHelpers@@YA?AUhstring@winrt@@AEBU34@000AEBUValueSet@Collections@Foundation@Windows@4@@Z; ShellHostHelpers::details::GetOrGenerateSingletonName(winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x18042a846  nop
0x18042a847  lea     rcx, [rsp+2D0h+var_268]; this
0x18042a84c  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x18042a851  mov     [rsp+2D0h+var_280], rax
0x18042a856  mov     rcx, rdi
0x18042a859  inc     rcx
0x18042a85c  cmp     [rax+rcx*2], r13w
0x18042a861  jnz     short loc_18042A859
0x18042a863  mov     [rsp+2D0h+var_278], rcx
0x18042a868  mov     qword ptr [rsp+2D0h+dwCreationFlags], r13
0x18042a86d  mov     [rsp+2D0h+bInheritHandles], 2
0x18042a875  xor     r9d, r9d
0x18042a878  lea     r8, [rsp+2D0h+var_270]
0x18042a87d  lea     rdx, [rsp+2D0h+var_280]
0x18042a882  lea     rcx, ?c_shellHostComponentSingletonCategoryName@details@ShellHostHelpers@@3V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const ShellHostHelpers::details::c_shellHostComponentSingletonCategoryName
0x18042a889  call    ?TryRedirectLaunch@SingletonHelper@SingletonHelpers@@SA_NAEBV?$basic_zstring_view@_W@wil@@0AEBUValueSet@Collections@Foundation@Windows@winrt@@W4ForegroundOption@12@W4StandardMessage@@PEAVFlowEndpointBase@@@Z; SingletonHelpers::SingletonHelper::TryRedirectLaunch(wil::basic_zstring_view<wchar_t> const &,wil::basic_zstring_view<wchar_t> const &,winrt::Windows::Foundation::Collections::ValueSet const &,SingletonHelpers::SingletonHelper::ForegroundOption,StandardMessage,FlowEndpointBase *)
0x18042a88e  nop
0x18042a88f  lea     rcx, [rsp+2D0h+var_268]
0x18042a894  test    al, al
0x18042a896  jz      short loc_18042A8A2
0x18042a898  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18042a89d  jmp     loc_18042AD5B
0x18042a8a2  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18042a8a7  lea     rcx, [rbp+1D0h+var_170]
0x18042a8ab  call    ??0?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)
0x18042a8b0  nop
0x18042a8b1  lea     rdx, aLoadcomponent; "loadComponent"
0x18042a8b8  lea     rcx, [rbp+1D0h+var_160]
0x18042a8bc  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x18042a8c1  cmp     [r12], r13
0x18042a8c5  jz      short loc_18042A8F6
0x18042a8c7  lea     rdx, asc_180518AD8; " "
0x18042a8ce  lea     rcx, [rbp+1D0h+var_160]
0x18042a8d2  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x18042a8d7  mov     r9, rax
0x18042a8da  lea     rdx, [rsp+2D0h+var_280]
0x18042a8df  mov     rcx, r12
0x18042a8e2  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; winrt::hstring::operator std::wstring_view(void)
0x18042a8e7  mov     r8, [rax+8]
0x18042a8eb  mov     rdx, [rax]
0x18042a8ee  mov     rcx, r9
0x18042a8f1  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x18042a8f6  cmp     [r15], r13
0x18042a8f9  jz      short loc_18042A92A
0x18042a8fb  lea     rdx, aExtensioncateg; " --extensionCategory "
0x18042a902  lea     rcx, [rbp+1D0h+var_160]
0x18042a906  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x18042a90b  mov     r9, rax
0x18042a90e  lea     rdx, [rsp+2D0h+var_280]
0x18042a913  mov     rcx, r15
0x18042a916  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; winrt::hstring::operator std::wstring_view(void)
0x18042a91b  mov     r8, [rax+8]
0x18042a91f  mov     rdx, [rax]
0x18042a922  mov     rcx, r9
0x18042a925  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x18042a92a  cmp     [r14], r13
0x18042a92d  jz      short loc_18042A95E
0x18042a92f  lea     rdx, aExtensionid; " --extensionId "
0x18042a936  lea     rcx, [rbp+1D0h+var_160]
0x18042a93a  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x18042a93f  mov     r9, rax
0x18042a942  lea     rdx, [rsp+2D0h+var_280]
0x18042a947  mov     rcx, r14
0x18042a94a  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; winrt::hstring::operator std::wstring_view(void)
0x18042a94f  mov     r8, [rax+8]
0x18042a953  mov     rdx, [rax]
0x18042a956  mov     rcx, r9
0x18042a959  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x18042a95e  cmp     [rsi], r13
0x18042a961  jz      short loc_18042A992
0x18042a963  lea     rdx, aControlname; " --controlName "
0x18042a96a  lea     rcx, [rbp+1D0h+var_160]
0x18042a96e  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x18042a973  mov     r9, rax
0x18042a976  lea     rdx, [rsp+2D0h+var_280]
0x18042a97b  mov     rcx, rsi
0x18042a97e  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; winrt::hstring::operator std::wstring_view(void)
0x18042a983  mov     r8, [rax+8]
0x18042a987  mov     rdx, [rax]
0x18042a98a  mov     rcx, r9
0x18042a98d  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x18042a992  cmp     [rsp+2D0h+var_270], r13
0x18042a997  jz      short loc_18042A9E5
0x18042a999  lea     rdx, [rsp+2D0h+var_270]
0x18042a99e  lea     rcx, [rsp+2D0h+var_280]
0x18042a9a3  call    ?SerializeValueSetToBase64@ValueSetUtils@@YA?AUhstring@winrt@@AEBUValueSet@Collections@Foundation@Windows@3@@Z; ValueSetUtils::SerializeValueSetToBase64(winrt::Windows::Foundation::Collections::ValueSet const &)
0x18042a9a8  nop
0x18042a9a9  lea     rdx, aValueset; " --valueSet "
0x18042a9b0  lea     rcx, [rbp+1D0h+var_160]
0x18042a9b4  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x18042a9b9  mov     r9, rax
0x18042a9bc  lea     rdx, [rsp+2D0h+var_268]
0x18042a9c1  lea     rcx, [rsp+2D0h+var_280]
0x18042a9c6  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; winrt::hstring::operator std::wstring_view(void)
0x18042a9cb  mov     r8, [rax+8]
0x18042a9cf  mov     rdx, [rax]
0x18042a9d2  mov     rcx, r9
0x18042a9d5  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x18042a9da  nop
0x18042a9db  lea     rcx, [rsp+2D0h+var_280]
0x18042a9e0  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18042a9e5  mov     rbx, r13
0x18042a9e8  mov     [rsp+2D0h+var_258], rbx
0x18042a9ed  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4> `wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl(void)'::`2'::impl
0x18042a9f4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(void)
0x18042a9f9  test    al, al
0x18042a9fb  jz      loc_18042AA91
0x18042aa01  mov     rdx, cs:?TargetShellHostInstanceKey@SingleInstanceConstants@details@ShellHostHelpers@@3V?$basic_zstring_view@_W@wil@@B; wchar_t *
0x18042aa08  lea     rcx, [rsp+2D0h+var_280]; this
0x18042aa0d  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x18042aa12  nop
0x18042aa13  lea     r8, [rsp+2D0h+var_270]
0x18042aa18  lea     rdx, [rsp+2D0h+var_280]
0x18042aa1d  lea     rcx, [rsp+2D0h+var_268]
0x18042aa22  call    ??$try_get_value@Uhstring@winrt@@UValueSet@Collections@Foundation@Windows@2@@ValueSetUtils@@YA?AUhstring@winrt@@AEBU12@AEBUValueSet@Collections@Foundation@Windows@2@@Z; ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x18042aa27  lea     rcx, [rsp+2D0h+var_258]
0x18042aa2c  cmp     rcx, rax
0x18042aa2f  jz      short loc_18042AA46
0x18042aa31  mov     rdx, [rax]
0x18042aa34  mov     [rax], r13
0x18042aa37  lea     rcx, [rsp+2D0h+var_258]
0x18042aa3c  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x18042aa41  mov     rbx, [rsp+2D0h+var_258]
0x18042aa46  lea     rcx, [rsp+2D0h+var_268]
0x18042aa4b  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18042aa50  nop
0x18042aa51  lea     rcx, [rsp+2D0h+var_280]
0x18042aa56  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18042aa5b  test    rbx, rbx
0x18042aa5e  jz      short loc_18042AA91
0x18042aa60  lea     rdx, aInstance; " --instance "
0x18042aa67  lea     rcx, [rbp+1D0h+var_160]
0x18042aa6b  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x18042aa70  mov     r9, rax
0x18042aa73  lea     rdx, [rsp+2D0h+var_280]
0x18042aa78  lea     rcx, [rsp+2D0h+var_258]
0x18042aa7d  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; winrt::hstring::operator std::wstring_view(void)
0x18042aa82  mov     r8, [rax+8]
0x18042aa86  mov     rdx, [rax]
0x18042aa89  mov     rcx, r9
0x18042aa8c  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x18042aa91  lea     rdx, [rbp+1D0h+var_70]
0x18042aa98  lea     rcx, [rbp+1D0h+var_158]
0x18042aa9c  call    ?str@?$basic_stringbuf@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::wstringbuf::str(void)
0x18042aaa1  nop
0x18042aaa2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4> `wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl(void)'::`2'::impl
0x18042aaa9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(void)
0x18042aaae  test    al, al
0x18042aab0  jz      loc_18042AB8B
0x18042aab6  test    rbx, rbx
0x18042aab9  jz      loc_18042AB8B
0x18042aabf  lea     rcx, [rsp+2D0h+var_268]; this
0x18042aac4  call    ??0ValueSet@Collections@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::Collections::ValueSet::ValueSet(void)
0x18042aac9  nop
0x18042aaca  lea     rdx, [rbp+1D0h+var_70]
0x18042aad1  cmp     [rbp+1D0h+var_58], 7
0x18042aad9  cmova   rdx, [rbp+1D0h+var_70]; wchar_t *
0x18042aae1  lea     rcx, [rbp+1D0h+var_228]; this
0x18042aae5  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18042aaea  lea     rdx, [rbp+1D0h+var_228]; struct winrt::param::hstring *
0x18042aaee  lea     rcx, [rsp+2D0h+var_280]; this
0x18042aaf3  call    ?box_value@winrt@@YA?AUIInspectable@Foundation@Windows@1@AEBUhstring@param@1@@Z; winrt::box_value(winrt::param::hstring const &)
0x18042aaf8  mov     rbx, rax
0x18042aafb  lea     rdx, ?CommandLineKey@SingleInstanceConstants@details@ShellHostHelpers@@3V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const ShellHostHelpers::details::SingleInstanceConstants::CommandLineKey
0x18042ab02  lea     rcx, [rbp+1D0h+var_208]
0x18042ab06  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::param::hstring::hstring(std::wstring_view const &)
0x18042ab0b  mov     r8, rbx
0x18042ab0e  lea     rdx, [rbp+1D0h+var_208]
0x18042ab12  lea     rcx, [rsp+2D0h+var_268]
0x18042ab17  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x18042ab1c  nop
0x18042ab1d  cmp     [rsp+2D0h+var_280], r13
0x18042ab22  jz      short loc_18042AB2E
0x18042ab24  lea     rcx, [rsp+2D0h+var_280]
0x18042ab29  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18042ab2e  lea     rcx, [rsp+2D0h+var_258]; this
0x18042ab33  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x18042ab38  mov     [rsp+2D0h+var_280], rax
0x18042ab3d  inc     rdi
0x18042ab40  cmp     [rax+rdi*2], r13w
0x18042ab45  jnz     short loc_18042AB3D
0x18042ab47  mov     [rsp+2D0h+var_278], rdi
0x18042ab4c  mov     qword ptr [rsp+2D0h+dwCreationFlags], r13
0x18042ab51  mov     [rsp+2D0h+bInheritHandles], 2
0x18042ab59  xor     r9d, r9d
0x18042ab5c  lea     r8, [rsp+2D0h+var_268]
0x18042ab61  lea     rdx, [rsp+2D0h+var_280]
0x18042ab66  lea     rcx, ?ShellHostSingletonCategory@SingleInstanceConstants@details@ShellHostHelpers@@3V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const ShellHostHelpers::details::SingleInstanceConstants::ShellHostSingletonCategory
0x18042ab6d  call    ?TryRedirectLaunch@SingletonHelper@SingletonHelpers@@SA_NAEBV?$basic_zstring_view@_W@wil@@0AEBUValueSet@Collections@Foundation@Windows@winrt@@W4ForegroundOption@12@W4StandardMessage@@PEAVFlowEndpointBase@@@Z; SingletonHelpers::SingletonHelper::TryRedirectLaunch(wil::basic_zstring_view<wchar_t> const &,wil::basic_zstring_view<wchar_t> const &,winrt::Windows::Foundation::Collections::ValueSet const &,SingletonHelpers::SingletonHelper::ForegroundOption,StandardMessage,FlowEndpointBase *)
0x18042ab72  nop
0x18042ab73  lea     rcx, [rsp+2D0h+var_268]; this
0x18042ab78  test    al, al
0x18042ab7a  jz      short loc_18042AB86
0x18042ab7c  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x18042ab81  jmp     loc_18042AD39
0x18042ab86  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x18042ab8b  mov     qword ptr [rbp+1D0h+StartupInfo.cb], 68h ; 'h'
0x18042ab93  xor     edx, edx; Val
0x18042ab95  lea     r8d, [rdx+60h]; Size
0x18042ab99  lea     rcx, [rbp+1D0h+StartupInfo.lpReserved]; void *
0x18042ab9d  call    memset_0
0x18042aba2  mov     [rbp+1D0h+StartupInfo.dwFlags], 80h
0x18042aba9  xorps   xmm0, xmm0
0x18042abac  xor     eax, eax
0x18042abae  movups  xmmword ptr [rbp+1D0h+ProcessInformation.hProcess], xmm0
0x18042abb2  mov     qword ptr [rbp+1D0h+ProcessInformation.dwProcessId], rax
0x18042abb6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShellHostInBasicJobObject@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShellHostInBasicJobObject@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShellHostInBasicJobObject> `wil::Feature<__WilFeatureTraits_Feature_ShellHostInBasicJobObject>::GetImpl(void)'::`2'::impl
0x18042abbd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShellHostInBasicJobObject@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShellHostInBasicJobObject>::__private_IsEnabled(void)
0x18042abc2  lea     rdx, aWindirSystem32_0; "%WINDIR%\\system32\\shellhost.exe"
0x18042abc9  lea     rcx, [rbp+1D0h+lpApplicationName]
0x18042abcd  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x18042abd2  nop
0x18042abd3  lea     rax, [rbp+1D0h+var_70]
0x18042abda  cmp     [rbp+1D0h+var_58], 7
0x18042abe2  cmova   rax, [rbp+1D0h+var_70]
0x18042abea  mov     [rsp+2D0h+var_280], rax
0x18042abef  mov     rax, [rbp+1D0h+lpApplicationName]
0x18042abf3  mov     [rsp+2D0h+var_268], rax
0x18042abf8  lea     r9, [rsp+2D0h+var_280]
0x18042abfd  lea     rdx, [rsp+2D0h+var_268]
0x18042ac02  lea     rcx, [rbp+1D0h+lpCommandLine]
0x18042ac06  call    ??$str_concat@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@PEA_WAEAY01$$CB_WPEB_W@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@$$QEAPEA_WAEAY01$$CB_W$$QEAPEB_W@Z; wil::str_concat<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wchar_t *,wchar_t const (&)[2],wchar_t const *>(wchar_t * &&,wchar_t const (&)[2],wchar_t const * &&)
0x18042ac0b  nop
0x18042ac0c  lea     rax, [rbp+1D0h+ProcessInformation]
0x18042ac10  mov     [rsp+2D0h+lpProcessInformation], rax; lpProcessInformation
0x18042ac15  lea     rax, [rbp+1D0h+StartupInfo]
0x18042ac19  mov     [rsp+2D0h+lpStartupInfo], rax; lpStartupInfo
0x18042ac1e  mov     [rsp+2D0h+lpCurrentDirectory], r13; lpCurrentDirectory
  ... truncated ...
```
