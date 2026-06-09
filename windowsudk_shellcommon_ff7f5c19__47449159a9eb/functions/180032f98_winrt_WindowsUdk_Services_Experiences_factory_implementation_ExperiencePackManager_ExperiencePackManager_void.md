# winrt::WindowsUdk::Services::Experiences::factory_implementation::ExperiencePackManager::ExperiencePackManager(void)

- ea: `0x180032f98`
- end: `0x180033191`
- name: `??0ExperiencePackManager@factory_implementation@Experiences@Services@WindowsUdk@winrt@@QEAA@XZ`
- size: `505`
- prototype: `__int64 __fastcall(winrt::WindowsUdk::Services::Experiences::factory_implementation::ExperiencePackManager *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180032f38`

## callees

- `0x180011e64`
- `0x180011f98`
- `0x1800260c0`
- `0x180026860`
- `0x180027af0`
- `0x1800290b8`
- `0x180032e84`
- `0x180032f98`
- `0x180033f28`
- `0x1800dca48`
- `0x1800fed10`
- `0x180115c44`
- `0x18011eccc`
- `0x180156de8`
- `0x18015cb00`
- `0x18015d524`
- `0x18028584c`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180033071`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180033071`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180033052`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180033052`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180033010`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180033010`

## string_xrefs

- `0x1800330a5`: `WindowsUdk.Services.Experiences.ExperiencePackManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
winrt::WindowsUdk::Services::Experiences::factory_implementation::ExperiencePackManager *__fastcall winrt::WindowsUdk::Services::Experiences::factory_implementation::ExperiencePackManager::ExperiencePackManager(
        winrt::WindowsUdk::Services::Experiences::factory_implementation::ExperiencePackManager *this)
{
  BOOL v2; // esi
  void *v3; // rcx
  const WCHAR *p_lpLibFileName; // rcx
  const struct winrt::impl::slim_source_location *v5; // rdx
  __int64 (__fastcall ***v6)(_QWORD, __int64 *, WCHAR **); // rcx
  unsigned int v7; // eax
  void *Block; // [rsp+20h] [rbp-39h] BYREF
  __int64 v10; // [rsp+28h] [rbp-31h] BYREF
  WCHAR *v11; // [rsp+30h] [rbp-29h] BYREF
  __int128 v12; // [rsp+38h] [rbp-21h]
  _QWORD v13[2]; // [rsp+48h] [rbp-11h] BYREF
  LPCWSTR lpLibFileName; // [rsp+58h] [rbp-1h] BYREF
  __int128 v15; // [rsp+60h] [rbp+7h]
  unsigned __int64 v16; // [rsp+70h] [rbp+17h]

  v13[1] = this;
  winrt::impl::producers_base<winrt::WindowsUdk::Services::Experiences::factory_implementation::ExperiencePackManager,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::WindowsUdk::Services::Experiences::IExperiencePackManagerStatics>>::producers_base<winrt::WindowsUdk::Services::Experiences::factory_implementation::ExperiencePackManager,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::WindowsUdk::Services::Experiences::IExperiencePackManagerStatics>>((char *)this + 16);
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  std::atomic<unsigned __int64>::atomic<unsigned __int64>((char *)this + 8, 1);
  *(_QWORD *)this = &winrt::impl::heap_implements<winrt::WindowsUdk::Services::Experiences::factory_implementation::ExperiencePackManager>::`vftable';
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&Block, -6);
  v2 = IsWellKnownSid(*(PSID *)Block, WinLocalSystemSid);
  v3 = Block;
  Block = 0;
  if ( v3 )
    operator delete(v3);
  if ( v2 )
  {
    anonymous_namespace_::GetWsxPackManagerDllPath(&lpLibFileName);
    v10 = 0;
    p_lpLibFileName = (const WCHAR *)&lpLibFileName;
    if ( v16 > 7 )
      p_lpLibFileName = lpLibFileName;
    Block = LoadLibraryExW(p_lpLibFileName, 0, 0xD00u);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(
      (char *)this + 32,
      &Block);
    if ( Block )
      FreeLibrary((HMODULE)Block);
    if ( !*((_QWORD *)this + 4) )
    {
      LODWORD(v11) = 0;
      v12 = 0;
      winrt::throw_last_error((winrt *)&v11, v5);
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int RemoveDllDirectory(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int RemoveDllDirectory(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v10);
    std::filesystem::path::~path((std::filesystem::path *)&lpLibFileName);
  }
  winrt::hstring::hstring((winrt::hstring *)&v10, L"WindowsUdk.Services.Experiences.ExperiencePackManager");
  if ( v10 )
  {
    v11 = *(WCHAR **)(v10 + 16);
    *(_QWORD *)&v12 = *(unsigned int *)(v10 + 4);
  }
  else
  {
    v11 = (WCHAR *)&String1;
    *(_QWORD *)&v12 = 0;
  }
  v6 = *(__int64 (__fastcall ****)(_QWORD, __int64 *, WCHAR **))winrt::WindowsUdk::Services::Experiences::factory_implementation::ExperiencePackManager::GetActivationFactory(
                                                                  this,
                                                                  v13,
                                                                  &v11);
  if ( v6 )
  {
    v11 = 0;
    LODWORD(lpLibFileName) = 0;
    v15 = 0;
    v7 = (**v6)(v6, &winrt::impl::guid_v<winrt::WindowsUdk::Services::Experiences::IExperiencePackManagerStatics>, &v11);
    winrt::check_hresult(&Block, v7, &lpLibFileName);
    Block = v11;
  }
  else
  {
    Block = 0;
  }
  winrt::Windows::Foundation::IUnknown::operator=((char *)this + 40, &Block);
  if ( Block )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&Block);
  if ( v13[0] )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v13);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v10);
  return this;
}

```

## disassembly

```asm
0x180032f98  push    rbp
0x180032f9a  push    rbx
0x180032f9b  push    rsi
0x180032f9c  push    rdi
0x180032f9d  push    r14
0x180032f9f  push    r15
0x180032fa1  lea     rbp, [rsp-2Fh]
0x180032fa6  sub     rsp, 88h
0x180032fad  mov     rax, cs:__security_cookie
0x180032fb4  xor     rax, rsp
0x180032fb7  mov     [rbp+57h+var_38], rax
0x180032fbb  mov     rbx, rcx
0x180032fbe  mov     [rbp+57h+var_60], rcx
0x180032fc2  xor     r15d, r15d
0x180032fc5  add     rcx, 10h
0x180032fc9  call    ??0?$producers_base@UExperiencePackManager@factory_implementation@Experiences@Services@WindowsUdk@winrt@@V?$tuple@UIActivationFactory@Foundation@Windows@winrt@@UIExperiencePackManagerStatics@Experiences@Services@WindowsUdk@4@@std@@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<winrt::WindowsUdk::Services::Experiences::factory_implementation::ExperiencePackManager,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::WindowsUdk::Services::Experiences::IExperiencePackManagerStatics>>::producers_base<winrt::WindowsUdk::Services::Experiences::factory_implementation::ExperiencePackManager,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::WindowsUdk::Services::Experiences::IExperiencePackManagerStatics>>(void)
0x180032fce  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180032fd5  lea     rcx, [rbx+8]
0x180032fd9  lea     edx, [r15+1]
0x180032fdd  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x180032fe2  nop
0x180032fe3  lea     rax, ??_7?$heap_implements@UExperiencePackManager@factory_implementation@Experiences@Services@WindowsUdk@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::WindowsUdk::Services::Experiences::factory_implementation::ExperiencePackManager>::`vftable'
0x180032fea  mov     [rbx], rax
0x180032fed  lea     rdi, [rbx+20h]
0x180032ff1  mov     [rdi], r15
0x180032ff4  mov     [rbx+28h], r15
0x180032ff8  lea     rdx, [r15-6]
0x180032ffc  lea     rcx, [rbp+57h+Block]
0x180033000  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x180033005  lea     edx, [r15+16h]; WellKnownSidType
0x180033009  mov     rcx, [rbp+57h+Block]
0x18003300d  mov     rcx, [rcx]; pSid
0x180033010  call    cs:__imp_IsWellKnownSid
0x180033016  mov     esi, eax
0x180033018  mov     rcx, [rbp+57h+Block]; Block
0x18003301c  mov     [rbp+57h+Block], r15
0x180033020  test    rcx, rcx
0x180033023  jz      short loc_18003302A
0x180033025  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003302a  test    esi, esi
0x18003302c  jz      short loc_1800330A5
0x18003302e  lea     rcx, [rbp+57h+lpLibFileName]
0x180033032  call    _anonymous_namespace___GetWsxPackManagerDllPath
0x180033037  nop
0x180033038  mov     [rbp+57h+var_88], r15
0x18003303c  lea     rcx, [rbp+57h+lpLibFileName]
0x180033040  cmp     [rbp+57h+var_40], 7
0x180033045  cmova   rcx, [rbp+57h+lpLibFileName]; lpLibFileName
0x18003304a  xor     edx, edx; hFile
0x18003304c  mov     r8d, 0D00h; dwFlags
0x180033052  call    cs:__imp_LoadLibraryExW
0x180033058  mov     [rbp+57h+Block], rax
0x18003305c  lea     rdx, [rbp+57h+Block]
0x180033060  mov     rcx, rdi
0x180033063  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&)
0x180033068  mov     rcx, [rbp+57h+Block]; hLibModule
0x18003306c  test    rcx, rcx
0x18003306f  jz      short loc_180033077
0x180033071  call    cs:__imp_FreeLibrary
0x180033077  cmp     [rdi], r15
0x18003307a  jnz     short loc_180033092
0x18003307c  mov     dword ptr [rbp+57h+var_80], r15d
0x180033080  xorps   xmm0, xmm0
0x180033083  movdqu  [rbp+57h+var_78], xmm0
0x180033088  lea     rcx, [rbp+57h+var_80]; this
0x18003308c  call    ?throw_last_error@winrt@@YAXAEBUslim_source_location@impl@1@@Z; winrt::throw_last_error(winrt::impl::slim_source_location const &)
0x180033092  lea     rcx, [rbp+57h+var_88]
0x180033096  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?RemoveDllDirectory@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&RemoveDllDirectory(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&RemoveDllDirectory(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18003309b  nop
0x18003309c  lea     rcx, [rbp+57h+lpLibFileName]; this
0x1800330a0  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800330a5  lea     rdx, aWindowsudkServ_2; "WindowsUdk.Services.Experiences.Experie"...
0x1800330ac  lea     rcx, [rbp+57h+var_88]; this
0x1800330b0  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x1800330b5  nop
0x1800330b6  mov     rcx, [rbp+57h+var_88]
0x1800330ba  test    rcx, rcx
0x1800330bd  jz      short loc_1800330D0
0x1800330bf  mov     rax, [rcx+10h]
0x1800330c3  mov     [rbp+57h+var_80], rax
0x1800330c7  mov     eax, [rcx+4]
0x1800330ca  mov     qword ptr [rbp+57h+var_78], rax
0x1800330ce  jmp     short loc_1800330DF
0x1800330d0  lea     rax, String1
0x1800330d7  mov     [rbp+57h+var_80], rax
0x1800330db  mov     qword ptr [rbp+57h+var_78], r15
0x1800330df  lea     r8, [rbp+57h+var_80]
0x1800330e3  lea     rdx, [rbp+57h+var_68]
0x1800330e7  mov     rcx, rbx
0x1800330ea  call    ?GetActivationFactory@ExperiencePackManager@factory_implementation@Experiences@Services@WindowsUdk@winrt@@QEAA?AUIInspectable@Foundation@Windows@6@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::WindowsUdk::Services::Experiences::factory_implementation::ExperiencePackManager::GetActivationFactory(std::wstring_view const &)
0x1800330ef  nop
0x1800330f0  mov     rcx, [rax]
0x1800330f3  test    rcx, rcx
0x1800330f6  jnz     short loc_1800330FE
0x1800330f8  mov     [rbp+57h+Block], r15
0x1800330fc  jmp     short loc_18003313B
0x1800330fe  mov     [rbp+57h+var_80], r15
0x180033102  mov     dword ptr [rbp+57h+lpLibFileName], r15d
0x180033106  xorps   xmm0, xmm0
0x180033109  movdqu  [rbp+57h+var_50], xmm0
0x18003310e  mov     rax, [rcx]
0x180033111  lea     r8, [rbp+57h+var_80]
0x180033115  lea     rdx, ??$guid_v@UIExperiencePackManagerStatics@Experiences@Services@WindowsUdk@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::WindowsUdk::Services::Experiences::IExperiencePackManagerStatics>
0x18003311c  mov     rax, [rax]
0x18003311f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033124  lea     r8, [rbp+57h+lpLibFileName]
0x180033128  mov     edx, eax
0x18003312a  lea     rcx, [rbp+57h+Block]
0x18003312e  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180033133  mov     rax, [rbp+57h+var_80]
0x180033137  mov     [rbp+57h+Block], rax
0x18003313b  lea     rdx, [rbp+57h+Block]
0x18003313f  lea     rcx, [rbx+28h]
0x180033143  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x180033148  cmp     [rbp+57h+Block], r15
0x18003314c  jz      short loc_180033158
0x18003314e  lea     rcx, [rbp+57h+Block]
0x180033152  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180033157  nop
0x180033158  cmp     [rbp+57h+var_68], r15
0x18003315c  jz      short loc_180033168
0x18003315e  lea     rcx, [rbp+57h+var_68]
0x180033162  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180033167  nop
0x180033168  lea     rcx, [rbp+57h+var_88]
0x18003316c  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180033171  nop
0x180033172  mov     rax, rbx
0x180033175  mov     rcx, [rbp+57h+var_38]
0x180033179  xor     rcx, rsp; StackCookie
0x18003317c  call    __security_check_cookie
0x180033181  add     rsp, 88h
0x180033188  pop     r15
0x18003318a  pop     r14
0x18003318c  pop     rdi
0x18003318d  pop     rsi
0x18003318e  pop     rbx
0x18003318f  pop     rbp
0x180033190  retn
```
