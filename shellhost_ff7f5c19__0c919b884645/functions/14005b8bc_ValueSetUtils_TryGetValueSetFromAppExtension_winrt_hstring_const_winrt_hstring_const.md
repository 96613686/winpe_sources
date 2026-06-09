# ValueSetUtils::TryGetValueSetFromAppExtension(winrt::hstring const &,winrt::hstring const &)

- ea: `0x14005b8bc`
- end: `0x14005bc60`
- name: `?TryGetValueSetFromAppExtension@ValueSetUtils@@YA?AUValueSet@Collections@Foundation@Windows@winrt@@AEBUhstring@6@0@Z`
- size: `932`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140057370`
- `0x140057574`

## callees

- `0x14000a310`
- `0x14000cc7c`
- `0x14004f138`
- `0x140052594`
- `0x140052978`
- `0x140052bf8`
- `0x1400538ac`
- `0x140053eb8`
- `0x1400579a8`
- `0x140057a74`
- `0x14005b8bc`
- `0x14005d50c`
- `0x14005d614`
- `0x14005d654`
- `0x14005e8fc`
- `0x14005fcbc`
- `0x140067010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14005ba57`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14005ba57`

## string_xrefs

- `0x14005bbe0`: `PackageFolderPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
ValueSetUtils::details *__fastcall ValueSetUtils::TryGetValueSetFromAppExtension(
        ValueSetUtils::details *a1,
        _QWORD *a2,
        winrt::hstring *a3)
{
  unsigned int v5; // edi
  unsigned int v6; // r14d
  __int64 v7; // r15
  unsigned int v8; // eax
  struct IUnknown *v9; // rdx
  __int64 (__fastcall *v10)(__int64, _QWORD, void **); // rbx
  void **v11; // rax
  unsigned int v12; // eax
  const WCHAR *v13; // rbx
  unsigned int v14; // eax
  const WCHAR *v15; // rax
  unsigned int v16; // eax
  __int64 v17; // rax
  const struct winrt::Windows::Foundation::Collections::IPropertySet *v18; // r8
  unsigned int v19; // eax
  __int64 *v20; // rbx
  unsigned int v21; // eax
  __int64 *v22; // r14
  struct IInspectableVtbl *lpVtbl; // rbx
  struct IInspectableVtbl *v24; // rbx
  __int64 *v26; // [rsp+38h] [rbp-41h] BYREF
  __int64 v27; // [rsp+40h] [rbp-39h] BYREF
  int v28; // [rsp+48h] [rbp-31h] BYREF
  __int128 v29; // [rsp+50h] [rbp-29h]
  __int64 v30; // [rsp+68h] [rbp-11h] BYREF
  __int64 *v31; // [rsp+70h] [rbp-9h] BYREF
  _QWORD v32[11]; // [rsp+78h] [rbp-1h] BYREF
  _QWORD *v33; // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 *v34; // [rsp+F8h] [rbp+7Fh] BYREF

  *(_QWORD *)a1 = 0;
  v32[0] = *a2;
  v33 = v32;
  v34 = &qword_1400839B8;
  _InterlockedIncrement64(&qword_1400839B8);
  if ( winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics> )
  {
    _lambda_57b55f0f887558b5f7921754fb17175c_::operator()(
      &v33,
      &v30,
      &winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>);
    _InterlockedDecrement64(&qword_1400839B8);
  }
  else
  {
    _InterlockedDecrement64(&qword_1400839B8);
    winrt::impl::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>::call<_lambda_57b55f0f887558b5f7921754fb17175c_ &>(
      a1,
      &v30,
      &v33);
  }
  v5 = 7;
  v6 = 0;
  LODWORD(v33) = 0;
  v7 = v30;
  v28 = 0;
  v29 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v30 + 56LL))(v30, &v33);
  winrt::check_hresult(&v34, v8, &v28);
  while ( v6 != (_DWORD)v33 )
  {
    v27 = 0;
    v28 = 0;
    v29 = 0;
    v10 = *(__int64 (__fastcall **)(__int64, _QWORD, void **))(*(_QWORD *)v7 + 48LL);
    v11 = winrt::put_abi((winrt *)&v27, v9);
    v12 = v10(v7, v6, v11);
    winrt::check_hresult(&v34, v12, &v28);
    v13 = winrt::hstring::c_str(a3);
    v26 = 0;
    v28 = 0;
    v29 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v27 + 48LL))(v27, &v26);
    winrt::check_hresult(&v31, v14, &v28);
    v5 = v5 & 0xFFFFFFC7 | 0x28;
    v15 = winrt::hstring::c_str((winrt::hstring *)&v26);
    LODWORD(v13) = CompareStringOrdinal(v15, -1, v13, -1, 1);
    std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v26);
    if ( (_DWORD)v13 == 2 )
    {
      v34 = 0;
      v28 = 0;
      v29 = 0;
      v16 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v27 + 88LL))(v27, &v34);
      winrt::check_hresult(&v33, v16, &v28);
      v26 = v34;
      if ( v34 )
      {
        v17 = winrt::Windows::Foundation::Collections::ValueSet::ValueSet((winrt::Windows::Foundation::Collections::ValueSet *)&v33);
        winrt::com_ptr<winrt::impl::IRestrictedErrorInfo>::operator=(a1, v17);
        winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v33);
        ValueSetUtils::details::InsertManifestPropertyValuesRecursive(
          a1,
          (const struct winrt::Windows::Foundation::Collections::ValueSet *)&v26,
          v18);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OverlappedWindowBehavior>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OverlappedWindowBehavior>::GetImpl'::`2'::impl) )
        {
          v34 = 0;
          v28 = 0;
          v29 = 0;
          v19 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v27 + 80LL))(v27, &v34);
          winrt::check_hresult(&v33, v19, &v28);
          v20 = v34;
          v31 = v34;
          v34 = 0;
          v28 = 0;
          v29 = 0;
          v21 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v27 + 72LL))(v27, &v34);
          winrt::check_hresult(&v33, v21, &v28);
          v22 = v34;
          v32[0] = v20;
          lpVtbl = winrt::box_value((winrt *)&v33, (const struct winrt::param::hstring *)v32).lpVtbl;
          winrt::param::hstring::hstring((winrt::param::hstring *)&v28, L"PackageFullName");
          winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
            a1,
            &v28,
            lpVtbl);
          if ( v33 )
            winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v33);
          v32[0] = v22;
          v24 = winrt::box_value((winrt *)&v33, (const struct winrt::param::hstring *)v32).lpVtbl;
          winrt::param::hstring::hstring((winrt::param::hstring *)&v28, L"PackageFolderPath");
          winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
            a1,
            &v28,
            v24);
          if ( v33 )
            winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v33);
          std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v34);
          std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v31);
        }
      }
      winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v26);
      winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v27);
      break;
    }
    winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v27);
    ++v6;
  }
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v30);
  return a1;
}

```

## disassembly

```asm
0x14005b8bc  mov     [rsp-8+arg_10], rbx
0x14005b8c1  mov     [rsp-8+arg_0], rcx
0x14005b8c6  push    rbp
0x14005b8c7  push    rsi
0x14005b8c8  push    rdi
0x14005b8c9  push    r12
0x14005b8cb  push    r13
0x14005b8cd  push    r14
0x14005b8cf  push    r15
0x14005b8d1  lea     rbp, [rsp-27h]
0x14005b8d6  sub     rsp, 0A0h
0x14005b8dd  mov     r12, r8
0x14005b8e0  mov     rsi, rcx
0x14005b8e3  xor     r13d, r13d
0x14005b8e6  mov     [rbp+57h+var_A0], r13d
0x14005b8ea  mov     [rcx], r13
0x14005b8ed  mov     [rbp+57h+var_A0], 1
0x14005b8f4  mov     rax, [rdx]
0x14005b8f7  mov     [rbp+57h+var_58], rax
0x14005b8fb  lea     rax, [rbp+57h+var_58]
0x14005b8ff  mov     [rbp+57h+arg_8], rax
0x14005b903  lea     rax, qword_1400839B8
0x14005b90a  mov     [rbp+57h+arg_18], rax
0x14005b90e  lock inc cs:qword_1400839B8
0x14005b916  cmp     cs:??$factory_cache_entry_v@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics@2345@@12@A, r13; factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>::winrt::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>
0x14005b91d  jz      short loc_14005B93E
0x14005b91f  lea     r8, ??$factory_cache_entry_v@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics@2345@@12@A; factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>::winrt::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>
0x14005b926  lea     rdx, [rbp+57h+var_68]
0x14005b92a  lea     rcx, [rbp+57h+arg_8]
0x14005b92e  call    ??R_lambda_57b55f0f887558b5f7921754fb17175c_@@QEBA@AEBUIAppExtensionStatics@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@Z; _lambda_57b55f0f887558b5f7921754fb17175c_::operator()(winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics const &)
0x14005b933  nop
0x14005b934  lock dec cs:qword_1400839B8
0x14005b93c  jmp     short loc_14005B953
0x14005b93e  lock dec cs:qword_1400839B8
0x14005b946  lea     r8, [rbp+57h+arg_8]
0x14005b94a  lea     rdx, [rbp+57h+var_68]
0x14005b94e  call    ??$call@AEAV_lambda_57b55f0f887558b5f7921754fb17175c_@@@?$factory_cache_entry@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_57b55f0f887558b5f7921754fb17175c_@@@Z
0x14005b953  mov     edi, 7
0x14005b958  mov     [rbp+57h+var_A0], edi
0x14005b95b  mov     r14d, r13d
0x14005b95e  mov     dword ptr [rbp+57h+arg_8], r13d
0x14005b962  mov     r15, [rbp+57h+var_68]
0x14005b966  mov     [rbp+57h+var_88], r13d
0x14005b96a  xorps   xmm0, xmm0
0x14005b96d  movdqu  [rbp+57h+var_80], xmm0
0x14005b972  mov     rax, [r15]
0x14005b975  lea     rdx, [rbp+57h+arg_8]
0x14005b979  mov     rcx, r15
0x14005b97c  mov     rax, [rax+38h]
0x14005b980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b985  lea     r8, [rbp+57h+var_88]
0x14005b989  mov     edx, eax
0x14005b98b  lea     rcx, [rbp+57h+arg_18]
0x14005b98f  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x14005b994  cmp     r14d, dword ptr [rbp+57h+arg_8]
0x14005b998  jz      loc_14005BC38
0x14005b99e  mov     [rbp+57h+var_90], r13
0x14005b9a2  or      edi, 10h
0x14005b9a5  mov     [rbp+57h+var_A0], edi
0x14005b9a8  mov     [rbp+57h+var_88], r13d
0x14005b9ac  xorps   xmm0, xmm0
0x14005b9af  movdqu  [rbp+57h+var_80], xmm0
0x14005b9b4  mov     rax, [r15]
0x14005b9b7  mov     rbx, [rax+30h]
0x14005b9bb  lea     rcx, [rbp+57h+var_90]; this
0x14005b9bf  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x14005b9c4  mov     r8, rax
0x14005b9c7  mov     edx, r14d
0x14005b9ca  mov     rcx, r15
0x14005b9cd  mov     rax, rbx
0x14005b9d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b9d5  lea     r8, [rbp+57h+var_88]
0x14005b9d9  mov     edx, eax
0x14005b9db  lea     rcx, [rbp+57h+arg_18]
0x14005b9df  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x14005b9e4  and     edi, 0FFFFFFEFh
0x14005b9e7  or      edi, 8
0x14005b9ea  mov     [rbp+57h+var_A0], edi
0x14005b9ed  mov     rcx, r12; this
0x14005b9f0  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x14005b9f5  mov     rbx, rax
0x14005b9f8  mov     [rbp+57h+var_98], r13
0x14005b9fc  mov     rcx, [rbp+57h+var_90]
0x14005ba00  mov     [rbp+57h+var_88], r13d
0x14005ba04  xorps   xmm0, xmm0
0x14005ba07  movdqu  [rbp+57h+var_80], xmm0
0x14005ba0c  mov     rdx, [rcx]
0x14005ba0f  mov     rax, [rdx+30h]
0x14005ba13  lea     rdx, [rbp+57h+var_98]
0x14005ba17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005ba1c  lea     r8, [rbp+57h+var_88]
0x14005ba20  mov     edx, eax
0x14005ba22  lea     rcx, [rbp+57h+var_60]
0x14005ba26  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x14005ba2b  mov     rax, [rbp+57h+var_98]
0x14005ba2f  mov     [rbp+57h+var_98], rax
0x14005ba33  or      edi, 20h
0x14005ba36  mov     [rbp+57h+var_A0], edi
0x14005ba39  lea     rcx, [rbp+57h+var_98]; this
0x14005ba3d  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x14005ba42  mov     rcx, rax; lpString1
0x14005ba45  mov     [rsp+0D0h+bIgnoreCase], 1; bIgnoreCase
0x14005ba4d  or      r9d, 0FFFFFFFFh; cchCount2
0x14005ba51  mov     r8, rbx; lpString2
0x14005ba54  or      edx, r9d; cchCount1
0x14005ba57  call    cs:__imp_CompareStringOrdinal
0x14005ba5d  mov     ebx, eax
0x14005ba5f  lea     rcx, [rbp+57h+var_98]
0x14005ba63  call    ??1?$pair@Uhstring@winrt@@_N@std@@QEAA@XZ; std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(void)
0x14005ba68  cmp     ebx, 2
0x14005ba6b  jz      short loc_14005BA7E
0x14005ba6d  lea     rcx, [rbp+57h+var_90]; this
0x14005ba71  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x14005ba76  inc     r14d
0x14005ba79  jmp     loc_14005B994
0x14005ba7e  mov     [rbp+57h+arg_18], r13
0x14005ba82  mov     rcx, [rbp+57h+var_90]
0x14005ba86  mov     [rbp+57h+var_88], r13d
0x14005ba8a  xorps   xmm0, xmm0
0x14005ba8d  movdqu  [rbp+57h+var_80], xmm0
0x14005ba92  mov     rax, [rcx]
0x14005ba95  lea     rdx, [rbp+57h+arg_18]
0x14005ba99  mov     rax, [rax+58h]
0x14005ba9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005baa2  lea     r8, [rbp+57h+var_88]
0x14005baa6  mov     edx, eax
0x14005baa8  lea     rcx, [rbp+57h+arg_8]
0x14005baac  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x14005bab1  mov     rax, [rbp+57h+arg_18]
0x14005bab5  mov     [rbp+57h+var_98], rax
0x14005bab9  or      edi, 40h
0x14005babc  mov     [rbp+57h+var_A0], edi
0x14005babf  test    rax, rax
0x14005bac2  jz      loc_14005BC24
0x14005bac8  lea     rcx, [rbp+57h+arg_8]; this
0x14005bacc  call    ??0ValueSet@Collections@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::Collections::ValueSet::ValueSet(void)
0x14005bad1  mov     rdx, rax
0x14005bad4  mov     rcx, rsi
0x14005bad7  call    ??4?$com_ptr@UIRestrictedErrorInfo@impl@winrt@@@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::com_ptr<winrt::impl::IRestrictedErrorInfo>::operator=(winrt::com_ptr<winrt::impl::IRestrictedErrorInfo> &&)
0x14005badc  lea     rcx, [rbp+57h+arg_8]; this
0x14005bae0  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x14005bae5  lea     rdx, [rbp+57h+var_98]; struct winrt::Windows::Foundation::Collections::ValueSet *
0x14005bae9  mov     rcx, rsi; this
0x14005baec  call    ?InsertManifestPropertyValuesRecursive@details@ValueSetUtils@@YAXAEBUValueSet@Collections@Foundation@Windows@winrt@@AEBUIPropertySet@4567@@Z; ValueSetUtils::details::InsertManifestPropertyValuesRecursive(winrt::Windows::Foundation::Collections::ValueSet const &,winrt::Windows::Foundation::Collections::IPropertySet const &)
0x14005baf1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OverlappedWindowBehavior@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OverlappedWindowBehavior@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OverlappedWindowBehavior> `wil::Feature<__WilFeatureTraits_Feature_OverlappedWindowBehavior>::GetImpl(void)'::`2'::impl
0x14005baf8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OverlappedWindowBehavior@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OverlappedWindowBehavior>::__private_IsEnabled(void)
0x14005bafd  test    al, al
0x14005baff  jz      loc_14005BC24
0x14005bb05  mov     [rbp+57h+arg_18], r13
0x14005bb09  mov     rcx, [rbp+57h+var_90]
0x14005bb0d  mov     [rbp+57h+var_88], r13d
0x14005bb11  xorps   xmm0, xmm0
0x14005bb14  movdqu  [rbp+57h+var_80], xmm0
0x14005bb19  mov     rax, [rcx]
0x14005bb1c  lea     rdx, [rbp+57h+arg_18]
0x14005bb20  mov     rax, [rax+50h]
0x14005bb24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005bb29  lea     r8, [rbp+57h+var_88]
0x14005bb2d  mov     edx, eax
0x14005bb2f  lea     rcx, [rbp+57h+arg_8]
0x14005bb33  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x14005bb38  mov     rbx, [rbp+57h+arg_18]
0x14005bb3c  mov     [rbp+57h+var_60], rbx
0x14005bb40  bts     edi, 7
0x14005bb44  mov     [rbp+57h+var_A0], edi
0x14005bb47  mov     [rbp+57h+arg_18], r13
0x14005bb4b  mov     rcx, [rbp+57h+var_90]
0x14005bb4f  mov     [rbp+57h+var_88], r13d
0x14005bb53  xorps   xmm0, xmm0
0x14005bb56  movdqu  [rbp+57h+var_80], xmm0
0x14005bb5b  mov     rax, [rcx]
0x14005bb5e  lea     rdx, [rbp+57h+arg_18]
0x14005bb62  mov     rax, [rax+48h]
0x14005bb66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005bb6b  lea     r8, [rbp+57h+var_88]
0x14005bb6f  mov     edx, eax
0x14005bb71  lea     rcx, [rbp+57h+arg_8]
0x14005bb75  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x14005bb7a  mov     r14, [rbp+57h+arg_18]
0x14005bb7e  mov     [rbp+57h+arg_18], r14
0x14005bb82  bts     edi, 8
0x14005bb86  mov     [rbp+57h+var_A0], edi
0x14005bb89  mov     [rbp+57h+var_58], rbx
0x14005bb8d  lea     rdx, [rbp+57h+var_58]; struct winrt::param::hstring *
0x14005bb91  lea     rcx, [rbp+57h+arg_8]; this
0x14005bb95  call    ?box_value@winrt@@YA?AUIInspectable@Foundation@Windows@1@AEBUhstring@param@1@@Z; winrt::box_value(winrt::param::hstring const &)
0x14005bb9a  mov     rbx, rax
0x14005bb9d  lea     rdx, aPackagefullnam; "PackageFullName"
0x14005bba4  lea     rcx, [rbp+57h+var_88]; this
0x14005bba8  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x14005bbad  mov     r8, rbx
0x14005bbb0  lea     rdx, [rbp+57h+var_88]
0x14005bbb4  mov     rcx, rsi
0x14005bbb7  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x14005bbbc  nop
0x14005bbbd  cmp     [rbp+57h+arg_8], r13
0x14005bbc1  jz      short loc_14005BBCC
0x14005bbc3  lea     rcx, [rbp+57h+arg_8]
0x14005bbc7  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x14005bbcc  mov     [rbp+57h+var_58], r14
0x14005bbd0  lea     rdx, [rbp+57h+var_58]; struct winrt::param::hstring *
0x14005bbd4  lea     rcx, [rbp+57h+arg_8]; this
0x14005bbd8  call    ?box_value@winrt@@YA?AUIInspectable@Foundation@Windows@1@AEBUhstring@param@1@@Z; winrt::box_value(winrt::param::hstring const &)
0x14005bbdd  mov     rbx, rax
0x14005bbe0  lea     rdx, aPackagefolderp; "PackageFolderPath"
0x14005bbe7  lea     rcx, [rbp+57h+var_88]; this
0x14005bbeb  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x14005bbf0  mov     r8, rbx
0x14005bbf3  lea     rdx, [rbp+57h+var_88]
0x14005bbf7  mov     rcx, rsi
0x14005bbfa  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x14005bbff  nop
0x14005bc00  cmp     [rbp+57h+arg_8], r13
0x14005bc04  jz      short loc_14005BC10
0x14005bc06  lea     rcx, [rbp+57h+arg_8]
0x14005bc0a  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x14005bc0f  nop
0x14005bc10  lea     rcx, [rbp+57h+arg_18]
0x14005bc14  call    ??1?$pair@Uhstring@winrt@@_N@std@@QEAA@XZ; std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(void)
0x14005bc19  nop
0x14005bc1a  lea     rcx, [rbp+57h+var_60]
0x14005bc1e  call    ??1?$pair@Uhstring@winrt@@_N@std@@QEAA@XZ; std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(void)
0x14005bc23  nop
0x14005bc24  lea     rcx, [rbp+57h+var_98]; this
0x14005bc28  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x14005bc2d  nop
0x14005bc2e  lea     rcx, [rbp+57h+var_90]; this
0x14005bc32  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x14005bc37  nop
0x14005bc38  lea     rcx, [rbp+57h+var_68]; this
0x14005bc3c  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x14005bc41  mov     rax, rsi
0x14005bc44  mov     rbx, [rsp+0D0h+arg_10]
0x14005bc4c  add     rsp, 0A0h
0x14005bc53  pop     r15
0x14005bc55  pop     r14
0x14005bc57  pop     r13
0x14005bc59  pop     r12
0x14005bc5b  pop     rdi
0x14005bc5c  pop     rsi
0x14005bc5d  pop     rbp
0x14005bc5e  retn
```
