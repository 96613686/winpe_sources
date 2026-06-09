# winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::XamlExtension::GetActivationFactory(winrt::hstring const &)

- ea: `0x1800b95fc`
- end: `0x1800b99c9`
- name: `?GetActivationFactory@XamlExtension@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEAA?AUIInspectable@Foundation@Windows@6@AEBUhstring@6@@Z`
- size: `973`
- prototype: `struct IInspectable __fastcall(winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::XamlExtension *this, const struct winrt::hstring *, _QWORD *)`
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180036104`
- `0x1802bb998`

## callees

- `0x180020a14`
- `0x1800227a4`
- `0x180025348`
- `0x180026860`
- `0x180027af0`
- `0x18002a030`
- `0x180033198`
- `0x180053fac`
- `0x180054018`
- `0x18009fe54`
- `0x1800b94b0`
- `0x1800b95fc`
- `0x1800cd5a4`
- `0x1800dca48`
- `0x1800e3810`
- `0x180115c44`
- `0x1801170cc`
- `0x18011eccc`
- `0x18015cb00`
- `0x1802ab01c`
- `0x1802bb868`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!AddDllDirectory` at `0x1800b9768`
- `api-ms-win-core-libraryloader-l1-2-0!AddDllDirectory` at `0x1800b9768`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b96c5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b9742`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b97c0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b98e3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b96c5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b9742`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b97c0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b98e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b994c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b994c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b9723`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b97a1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b9873`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b9723`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b97a1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b9873`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b96a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b96a6`

## string_xrefs

- `0x1800b9942`: `DllGetActivationFactory`
- `0x1800b964e`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\XamlExtension.cpp`
- `0x1800b97e0`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\XamlExtension.cpp`
- `0x1800b989a`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\XamlExtension.cpp`
- `0x1800b988a`: `Failed to load a dependent dll`
- `0x1800b966b`: `ExtensionBinary should point a dll`
- `0x1800b97d0`: `Failed to load an extension dll`

## pseudocode

```c
struct IInspectable __fastcall winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::XamlExtension::GetActivationFactory(
        winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::XamlExtension *this,
        const struct winrt::hstring *a2,
        _QWORD *a3)
{
  _QWORD *v3; // r13
  const char *v6; // r9
  HMODULE *v7; // rbx
  const WCHAR *v8; // rax
  const WCHAR *v9; // rcx
  const WCHAR *v10; // rax
  HMODULE v11; // rax
  const WCHAR *v12; // rcx
  const struct winrt::hstring *v13; // rsi
  const struct winrt::hstring *v14; // r15
  __int64 v15; // rax
  const WCHAR *v16; // rcx
  HMODULE Library; // r13
  HMODULE *v18; // rdx
  HMODULE v19; // rcx
  FARPROC ProcAddress; // rbx
  struct IUnknown *v21; // rdx
  void **v22; // rax
  unsigned int v23; // eax
  char *v25; // [rsp+28h] [rbp-71h]
  HMODULE hLibModule; // [rsp+30h] [rbp-69h] BYREF
  int v27; // [rsp+38h] [rbp-61h]
  _QWORD *v28; // [rsp+40h] [rbp-59h]
  int v29; // [rsp+48h] [rbp-51h] BYREF
  __int128 v30; // [rsp+50h] [rbp-49h]
  const struct winrt::hstring *v31; // [rsp+68h] [rbp-31h]
  const wchar_t *v32; // [rsp+70h] [rbp-29h] BYREF
  __int128 v33; // [rsp+78h] [rbp-21h] BYREF
  __int64 v34; // [rsp+88h] [rbp-11h]
  LPCWSTR lpLibFileName[3]; // [rsp+90h] [rbp-9h] BYREF
  unsigned __int64 v36; // [rsp+A8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v3 = a3;
  v28 = a3;
  v31 = a2;
  v27 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60566491>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60566491>::GetImpl'::`2'::impl) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x182,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\XamlExtension.cpp",
      v6);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x184,
    (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\XamlExtension.cpp",
    (const char *)0x8007139FLL,
    *((_QWORD *)this + 14) == 0,
    (bool)"ExtensionBinary should point a dll",
    (const char *)hLibModule);
  v7 = (HMODULE *)((char *)this + 128);
  if ( !*((_QWORD *)this + 16) )
  {
    v8 = winrt::hstring::c_str((winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::XamlExtension *)((char *)this + 112));
    hLibModule = GetModuleHandleW(v8);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(
      (char *)this + 128,
      &hLibModule);
    if ( hLibModule )
      FreeLibrary(hLibModule);
    if ( !*v7 )
    {
      v32 = winrt::hstring::c_str((winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::XamlExtension *)((char *)this + 96));
      std::filesystem::_Convert_Source_to_wide<wchar_t const *,std::filesystem::_Normal_conversion>(lpLibFileName, &v32);
      v32 = winrt::hstring::c_str((winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::XamlExtension *)((char *)this + 112));
      std::filesystem::path::operator/=<wchar_t const *,0>(lpLibFileName, &v32);
      v9 = (const WCHAR *)lpLibFileName;
      if ( v36 > 7 )
        v9 = lpLibFileName[0];
      hLibModule = LoadLibraryExW(v9, 0, 0xC00u);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(
        (char *)this + 128,
        &hLibModule);
      if ( hLibModule )
        FreeLibrary(hLibModule);
      v33 = 0;
      v34 = 0;
      if ( !*v7 )
      {
        v10 = winrt::hstring::c_str((winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::XamlExtension *)((char *)this + 96));
        v11 = (HMODULE)AddDllDirectory(v10);
        if ( v11 )
        {
          hLibModule = v11;
          std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int RemoveDllDirectory(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::emplace_back<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int RemoveDllDirectory(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(
            &v33,
            &hLibModule);
          wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int RemoveDllDirectory(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int RemoveDllDirectory(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hLibModule);
        }
        v12 = (const WCHAR *)lpLibFileName;
        if ( v36 > 7 )
          v12 = lpLibFileName[0];
        hLibModule = LoadLibraryExW(v12, 0, 0xC00u);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(
          (char *)this + 128,
          &hLibModule);
        if ( hLibModule )
          FreeLibrary(hLibModule);
        wil::details::in1diag3::Throw_GetLastErrorIfMsg(
          retaddr,
          (void *)0x1AE,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\XamlExtension.cpp",
          (const char *)(*v7 == 0),
          (bool)"Failed to load an extension dll",
          v25);
      }
      v13 = (const struct winrt::hstring *)*((_QWORD *)this + 17);
      v14 = (const struct winrt::hstring *)*((_QWORD *)this + 18);
      if ( v13 != v14 )
      {
        do
        {
          winrt::hstring::hstring((winrt::hstring *)&v32, v13);
          hLibModule = (HMODULE)winrt::hstring::c_str((winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::XamlExtension *)((char *)this + 96));
          v15 = std::filesystem::_Convert_Source_to_wide<wchar_t const *,std::filesystem::_Normal_conversion>(
                  &v29,
                  &hLibModule);
          std::wstring::operator=(lpLibFileName, v15);
          std::filesystem::path::~path((std::filesystem::path *)&v29);
          hLibModule = (HMODULE)winrt::hstring::c_str((winrt::hstring *)&v32);
          std::filesystem::path::operator/=<wchar_t const *,0>(lpLibFileName, &hLibModule);
          v16 = (const WCHAR *)lpLibFileName;
          if ( v36 > 7 )
            v16 = lpLibFileName[0];
          Library = LoadLibraryExW(v16, 0, 0xC00u);
          hLibModule = Library;
          wil::details::in1diag3::Throw_GetLastErrorIfMsg(
            retaddr,
            (void *)0x1B8,
            (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\XamlExtension.cpp",
            (const char *)(Library == 0),
            (bool)"Failed to load a dependent dll",
            v25);
          v18 = (HMODULE *)*((_QWORD *)this + 21);
          if ( v18 == *((HMODULE **)this + 22) )
          {
            std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(
              (char *)this + 160,
              v18,
              &hLibModule);
            v19 = hLibModule;
          }
          else
          {
            *v18 = Library;
            v19 = 0;
            *((_QWORD *)this + 21) += 8LL;
          }
          if ( v19 )
            FreeLibrary(v19);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v32);
          v13 = (const struct winrt::hstring *)((char *)v13 + 8);
        }
        while ( v13 != v14 );
        v3 = v28;
      }
      if ( (_QWORD)v33 )
      {
        std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int RemoveDllDirectory(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>(
          v33,
          *((_QWORD *)&v33 + 1));
        std::_Deallocate<16>(v33, (v34 - v33) & 0xFFFFFFFFFFFFFFF8uLL);
        v33 = 0;
        v34 = 0;
      }
      std::filesystem::path::~path((std::filesystem::path *)lpLibFileName);
    }
  }
  ProcAddress = GetProcAddress(*v7, "DllGetActivationFactory");
  *(_QWORD *)a2 = 0;
  v27 = 1;
  v22 = winrt::put_abi(a2, v21);
  v29 = 0;
  v30 = 0;
  v23 = ((__int64 (__fastcall *)(_QWORD, void **))ProcAddress)(*v3, v22);
  winrt::check_hresult(&hLibModule, v23, &v29);
  return (struct IInspectable)a2;
}

```

## disassembly

```asm
0x1800b95fc  mov     [rsp-8+arg_18], rbx
0x1800b9601  push    rbp
0x1800b9602  push    rsi
0x1800b9603  push    rdi
0x1800b9604  push    r12
0x1800b9606  push    r13
0x1800b9608  push    r14
0x1800b960a  push    r15
0x1800b960c  lea     rbp, [rsp-27h]
0x1800b9611  sub     rsp, 0C0h
0x1800b9618  mov     rax, cs:__security_cookie
0x1800b961f  xor     rax, rsp
0x1800b9622  mov     [rbp+57h+var_40], rax
0x1800b9626  mov     r13, r8
0x1800b9629  mov     [rbp+57h+var_B0], r8
0x1800b962d  mov     r14, rdx
0x1800b9630  mov     rdi, rcx
0x1800b9633  mov     [rbp+57h+var_88], rdx
0x1800b9637  xor     r15d, r15d
0x1800b963a  mov     [rbp+57h+var_B8], r15d
0x1800b963e  mov     rbx, [rbp+5Fh]
0x1800b9642  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60566491@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60566491@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60566491> `wil::Feature<__WilFeatureTraits_Feature_60566491>::GetImpl(void)'::`2'::impl
0x1800b9649  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60566491@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60566491>::__private_IsEnabled(void)
0x1800b964e  lea     r8, aShellcommonUnd_125; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800b9655  test    al, al
0x1800b9657  jnz     loc_1800B99BB
0x1800b965d  lea     rsi, [rdi+70h]
0x1800b9661  cmp     [rsi], r15
0x1800b9664  setz    al
0x1800b9667  mov     rcx, [rbp+5Fh]; this
0x1800b966b  lea     rdx, aExtensionbinar; "ExtensionBinary should point a dll"
0x1800b9672  mov     [rsp+0F0h+var_C8], rdx; char *
0x1800b9677  mov     [rsp+0F0h+var_D0], al; char
0x1800b967b  mov     r9d, 8007139Fh; char *
0x1800b9681  mov     edx, 184h; void *
0x1800b9686  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800b968b  lea     rbx, [rdi+80h]
0x1800b9692  cmp     [rbx], r15
0x1800b9695  jnz     loc_1800B9942
0x1800b969b  mov     rcx, rsi; this
0x1800b969e  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x1800b96a3  mov     rcx, rax; lpModuleName
0x1800b96a6  call    cs:__imp_GetModuleHandleW
0x1800b96ac  mov     [rbp+57h+hLibModule], rax
0x1800b96b0  lea     rdx, [rbp+57h+hLibModule]
0x1800b96b4  mov     rcx, rbx
0x1800b96b7  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&)
0x1800b96bc  mov     rcx, [rbp+57h+hLibModule]; hLibModule
0x1800b96c0  test    rcx, rcx
0x1800b96c3  jz      short loc_1800B96CB
0x1800b96c5  call    cs:__imp_FreeLibrary
0x1800b96cb  cmp     [rbx], r15
0x1800b96ce  jnz     loc_1800B9942
0x1800b96d4  lea     r12, [rdi+60h]
0x1800b96d8  mov     rcx, r12; this
0x1800b96db  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x1800b96e0  mov     [rbp+57h+var_80], rax
0x1800b96e4  lea     rdx, [rbp+57h+var_80]
0x1800b96e8  lea     rcx, [rbp+57h+lpLibFileName]
0x1800b96ec  call    ??$_Convert_Source_to_wide@PEB_WU_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEBQEB_WU_Normal_conversion@01@@Z; std::filesystem::_Convert_Source_to_wide<wchar_t const *,std::filesystem::_Normal_conversion>(wchar_t const * const &,std::filesystem::_Normal_conversion)
0x1800b96f1  nop
0x1800b96f2  mov     rcx, rsi; this
0x1800b96f5  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x1800b96fa  mov     [rbp+57h+var_80], rax
0x1800b96fe  lea     rdx, [rbp+57h+var_80]
0x1800b9702  lea     rcx, [rbp+57h+lpLibFileName]
0x1800b9706  call    ??$?_0PEB_W$0A@@path@filesystem@std@@QEAAAEAV012@AEBQEB_W@Z; std::filesystem::path::operator/=<wchar_t const *,0>(wchar_t const * const &)
0x1800b970b  lea     rcx, [rbp+57h+lpLibFileName]
0x1800b970f  cmp     [rbp+57h+var_48], 7
0x1800b9714  cmova   rcx, [rbp+57h+lpLibFileName]; lpLibFileName
0x1800b9719  mov     esi, 0C00h
0x1800b971e  mov     r8d, esi; dwFlags
0x1800b9721  xor     edx, edx; hFile
0x1800b9723  call    cs:__imp_LoadLibraryExW
0x1800b9729  mov     [rbp+57h+hLibModule], rax
0x1800b972d  lea     rdx, [rbp+57h+hLibModule]
0x1800b9731  mov     rcx, rbx
0x1800b9734  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&)
0x1800b9739  mov     rcx, [rbp+57h+hLibModule]; hLibModule
0x1800b973d  test    rcx, rcx
0x1800b9740  jz      short loc_1800B9748
0x1800b9742  call    cs:__imp_FreeLibrary
0x1800b9748  xorps   xmm1, xmm1
0x1800b974b  movdqu  [rbp+57h+var_78], xmm1
0x1800b9750  mov     [rbp+57h+var_68], r15
0x1800b9754  cmp     [rbx], r15
0x1800b9757  jnz     loc_1800B97F1
0x1800b975d  mov     rcx, r12; this
0x1800b9760  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x1800b9765  mov     rcx, rax; NewDirectory
0x1800b9768  call    cs:__imp_AddDllDirectory
0x1800b976e  test    rax, rax
0x1800b9771  jz      short loc_1800B978E
0x1800b9773  mov     [rbp+57h+hLibModule], rax
0x1800b9777  lea     rdx, [rbp+57h+hLibModule]
0x1800b977b  lea     rcx, [rbp+57h+var_78]
0x1800b977f  call    ??$emplace_back@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?RemoveDllDirectory@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?RemoveDllDirectory@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?RemoveDllDirectory@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?RemoveDllDirectory@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&RemoveDllDirectory(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::emplace_back<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&RemoveDllDirectory(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&RemoveDllDirectory(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&)
0x1800b9784  nop
0x1800b9785  lea     rcx, [rbp+57h+hLibModule]
0x1800b9789  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?RemoveDllDirectory@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&RemoveDllDirectory(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&RemoveDllDirectory(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800b978e  lea     rcx, [rbp+57h+lpLibFileName]
0x1800b9792  cmp     [rbp+57h+var_48], 7
0x1800b9797  cmova   rcx, [rbp+57h+lpLibFileName]; lpLibFileName
0x1800b979c  mov     r8d, esi; dwFlags
0x1800b979f  xor     edx, edx; hFile
0x1800b97a1  call    cs:__imp_LoadLibraryExW
0x1800b97a7  mov     [rbp+57h+hLibModule], rax
0x1800b97ab  lea     rdx, [rbp+57h+hLibModule]
0x1800b97af  mov     rcx, rbx
0x1800b97b2  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&)
0x1800b97b7  mov     rcx, [rbp+57h+hLibModule]; hLibModule
0x1800b97bb  test    rcx, rcx
0x1800b97be  jz      short loc_1800B97C6
0x1800b97c0  call    cs:__imp_FreeLibrary
0x1800b97c6  cmp     [rbx], r15
0x1800b97c9  setz    al
0x1800b97cc  mov     rcx, [rbp+5Fh]; this
0x1800b97d0  lea     rdx, aFailedToLoadAn; "Failed to load an extension dll"
0x1800b97d7  mov     qword ptr [rsp+0F0h+var_D0], rdx; bool
0x1800b97dc  movzx   r9d, al; char *
0x1800b97e0  lea     r8, aShellcommonUnd_125; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800b97e7  mov     edx, 1AEh; void *
0x1800b97ec  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x1800b97f1  mov     rsi, [rdi+88h]
0x1800b97f8  mov     r15, [rdi+90h]
0x1800b97ff  cmp     rsi, r15
0x1800b9802  jz      loc_1800B9904
0x1800b9808  mov     rdx, rsi; struct winrt::hstring *
0x1800b980b  lea     rcx, [rbp+57h+var_80]; this
0x1800b980f  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x1800b9814  nop
0x1800b9815  mov     rcx, r12; this
0x1800b9818  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x1800b981d  mov     [rbp+57h+hLibModule], rax
0x1800b9821  lea     rdx, [rbp+57h+hLibModule]
0x1800b9825  lea     rcx, [rbp+57h+var_A8]
0x1800b9829  call    ??$_Convert_Source_to_wide@PEB_WU_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEBQEB_WU_Normal_conversion@01@@Z; std::filesystem::_Convert_Source_to_wide<wchar_t const *,std::filesystem::_Normal_conversion>(wchar_t const * const &,std::filesystem::_Normal_conversion)
0x1800b982e  mov     rdx, rax
0x1800b9831  lea     rcx, [rbp+57h+lpLibFileName]
0x1800b9835  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800b983a  lea     rcx, [rbp+57h+var_A8]; this
0x1800b983e  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800b9843  lea     rcx, [rbp+57h+var_80]; this
0x1800b9847  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x1800b984c  mov     [rbp+57h+hLibModule], rax
0x1800b9850  lea     rdx, [rbp+57h+hLibModule]
0x1800b9854  lea     rcx, [rbp+57h+lpLibFileName]
0x1800b9858  call    ??$?_0PEB_W$0A@@path@filesystem@std@@QEAAAEAV012@AEBQEB_W@Z; std::filesystem::path::operator/=<wchar_t const *,0>(wchar_t const * const &)
0x1800b985d  lea     rcx, [rbp+57h+lpLibFileName]
0x1800b9861  cmp     [rbp+57h+var_48], 7
0x1800b9866  cmova   rcx, [rbp+57h+lpLibFileName]; lpLibFileName
0x1800b986b  xor     edx, edx; hFile
0x1800b986d  mov     r8d, 0C00h; dwFlags
0x1800b9873  call    cs:__imp_LoadLibraryExW
0x1800b9879  mov     r13, rax
0x1800b987c  mov     [rbp+57h+hLibModule], rax
0x1800b9880  test    rax, rax
0x1800b9883  setz    dl
0x1800b9886  mov     rcx, [rbp+5Fh]; this
0x1800b988a  lea     rax, aFailedToLoadAD; "Failed to load a dependent dll"
0x1800b9891  mov     qword ptr [rsp+0F0h+var_D0], rax; bool
0x1800b9896  movzx   r9d, dl; char *
0x1800b989a  lea     r8, aShellcommonUnd_125; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800b98a1  mov     edx, 1B8h; void *
0x1800b98a6  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x1800b98ab  mov     rdx, [rdi+0A8h]
0x1800b98b2  cmp     rdx, [rdi+0B0h]
0x1800b98b9  jz      short loc_1800B98CA
0x1800b98bb  mov     [rdx], r13
0x1800b98be  xor     ecx, ecx
0x1800b98c0  add     qword ptr [rdi+0A8h], 8
0x1800b98c8  jmp     short loc_1800B98DE
0x1800b98ca  lea     r8, [rbp+57h+hLibModule]
0x1800b98ce  lea     rcx, [rdi+0A0h]
0x1800b98d5  call    ??$_Emplace_reallocate@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&)
0x1800b98da  mov     rcx, [rbp+57h+hLibModule]; hLibModule
0x1800b98de  test    rcx, rcx
0x1800b98e1  jz      short loc_1800B98EA
0x1800b98e3  call    cs:__imp_FreeLibrary
0x1800b98e9  nop
0x1800b98ea  lea     rcx, [rbp+57h+var_80]
0x1800b98ee  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800b98f3  add     rsi, 8
0x1800b98f7  cmp     rsi, r15
0x1800b98fa  jnz     loc_1800B9808
0x1800b9900  mov     r13, [rbp+57h+var_B0]
0x1800b9904  mov     rcx, qword ptr [rbp+57h+var_78]
0x1800b9908  xor     r15d, r15d
0x1800b990b  test    rcx, rcx
0x1800b990e  jz      short loc_1800B9939
0x1800b9910  mov     rdx, qword ptr [rbp+57h+var_78+8]
0x1800b9914  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?RemoveDllDirectory@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?RemoveDllDirectory@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?RemoveDllDirectory@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&RemoveDllDirectory(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&RemoveDllDirectory(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&RemoveDllDirectory(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&RemoveDllDirectory(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>> &)
0x1800b9919  mov     rcx, qword ptr [rbp+57h+var_78]
0x1800b991d  mov     rdx, [rbp+57h+var_68]
0x1800b9921  sub     rdx, rcx
0x1800b9924  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800b9928  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800b992d  xorps   xmm0, xmm0
0x1800b9930  movdqu  [rbp+57h+var_78], xmm0
0x1800b9935  mov     [rbp+57h+var_68], r15
0x1800b9939  lea     rcx, [rbp+57h+lpLibFileName]; this
0x1800b993d  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800b9942  lea     rdx, aDllgetactivati_0; "DllGetActivationFactory"
0x1800b9949  mov     rcx, [rbx]; hModule
0x1800b994c  call    cs:__imp_GetProcAddress
0x1800b9952  mov     rbx, rax
0x1800b9955  mov     [r14], r15
0x1800b9958  mov     [rbp+57h+var_B8], 1
0x1800b995f  mov     rcx, r14; this
0x1800b9962  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x1800b9967  mov     [rbp+57h+var_A8], r15d
0x1800b996b  xorps   xmm0, xmm0
0x1800b996e  movdqu  [rbp+57h+var_A0], xmm0
0x1800b9973  mov     rdx, rax
0x1800b9976  mov     rcx, [r13+0]
0x1800b997a  mov     rax, rbx
0x1800b997d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9982  lea     r8, [rbp+57h+var_A8]
0x1800b9986  mov     edx, eax
0x1800b9988  lea     rcx, [rbp+57h+hLibModule]
0x1800b998c  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800b9991  mov     rax, r14
0x1800b9994  mov     rcx, [rbp+57h+var_40]
0x1800b9998  xor     rcx, rsp; StackCookie
0x1800b999b  call    __security_check_cookie
0x1800b99a0  mov     rbx, [rsp+0F0h+arg_18]
0x1800b99a8  add     rsp, 0C0h
0x1800b99af  pop     r15
0x1800b99b1  pop     r14
0x1800b99b3  pop     r13
0x1800b99b5  pop     r12
0x1800b99b7  pop     rdi
0x1800b99b8  pop     rsi
0x1800b99b9  pop     rbp
0x1800b99ba  retn
0x1800b99bb  mov     edx, 182h; void *
0x1800b99c0  mov     rcx, rbx; this
0x1800b99c3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
