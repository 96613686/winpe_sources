# KeyboardHosting::TabTipAdapter::TabTipAdapter(Windows::Internal::Shell::Text::IInputExperienceHost *,Windows::Internal::Shell::Text::IShellKeyboardHostingPolicy *,Windows::Internal::Shell::KeyboardHosting::IDesktopKeyboardHostingPolicy *,Windows::Internal::Shell::KeyboardHosting::IInputInjectionValidityHelper *)

- ea: `0x18029e4d8`
- end: `0x18029ea45`
- name: `??0TabTipAdapter@KeyboardHosting@@QEAA@PEAUIInputExperienceHost@Text@Shell@Internal@Windows@@PEAUIShellKeyboardHostingPolicy@3456@PEAUIDesktopKeyboardHostingPolicy@1456@PEAUIInputInjectionValidityHelper@1456@@Z`
- size: `1389`
- prototype: `__int64 __fastcall(KeyboardHosting::TabTipAdapter *__hidden this, struct Windows::Internal::Shell::Text::IInputExperienceHost *, struct Windows::Internal::Shell::Text::IShellKeyboardHostingPolicy *, struct Windows::Internal::Shell::KeyboardHosting::IDesktopKeyboardHostingPolicy *, struct Windows::Internal::Shell::KeyboardHosting::IInputInjectionValidityHelper *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18029e498`

## callees

- `0x1800134f8`
- `0x18007f488`
- `0x1801b4418`
- `0x1801d9500`
- `0x1801dbe30`
- `0x18027e698`
- `0x18029e4d8`
- `0x180356360`
- `0x1804c21a4`
- `0x1804ca1e0`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18029e8a9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18029e8a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18029e890`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18029e890`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18029e806`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18029e8ca`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18029e806`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18029e8ca`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x18029e927`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x18029e927`
- `CoreMessaging!CoreUICreate` at `0x18029e78d`
- `CoreMessaging!CoreUICreate` at `0x18029e78d`
- `CoreUIComponents!CoreUIFactoryCreate` at `0x18029e7aa`
- `CoreUIComponents!CoreUIFactoryCreate` at `0x18029e7aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
KeyboardHosting::TabTipAdapter *__fastcall KeyboardHosting::TabTipAdapter::TabTipAdapter(
        KeyboardHosting::TabTipAdapter *this,
        struct Windows::Internal::Shell::Text::IInputExperienceHost *a2,
        struct Windows::Internal::Shell::Text::IShellKeyboardHostingPolicy *a3,
        struct Windows::Internal::Shell::KeyboardHosting::IDesktopKeyboardHostingPolicy *a4)
{
  char *v7; // r14
  const char *v8; // r9
  int v9; // eax
  int v10; // eax
  int v11; // eax
  HSTRING v12; // rbx
  int ActivationFactory; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, char *); // rbx
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, char *); // rbx
  int v19; // eax
  HSTRING v20; // rbx
  int v21; // eax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, char *); // rbx
  int v24; // eax
  __int64 v26; // [rsp+20h] [rbp-58h] BYREF
  __int64 v27; // [rsp+28h] [rbp-50h] BYREF
  struct Windows::Internal::Shell::Text::IInputExperienceHost *v28; // [rsp+30h] [rbp-48h]
  KeyboardHosting::TabTipAdapter *v29; // [rsp+38h] [rbp-40h]
  HSTRING string; // [rsp+48h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  v28 = a2;
  v29 = this;
  *(_QWORD *)this = &Windows::Foundation::Collections::IIterable<Windows::Internal::ApplicationModel::WindowingEnvironment::DisplayRegionId>::`vftable';
  *((_QWORD *)this + 1) = &TwinUI::Cortana::ISearchAppDesktopNotifications::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *((_QWORD *)this + 3) = 1;
  *(_QWORD *)this = &winrt::impl::heap_implements<KeyboardHosting::TabTipAdapter>::`vftable'{for `winrt::impl::producer_convert<KeyboardHosting::TabTipAdapter,IMessageProxyReconnectAdapterOwner,void>'};
  *((_QWORD *)this + 1) = &KeyboardHosting::TabTipAdapter::`vftable'{for `winrt::impl::producer_convert<KeyboardHosting::TabTipAdapter,IRemoteTabTipAdapter,void>'};
  *((_QWORD *)this + 2) = &winrt::impl::heap_implements<KeyboardHosting::TabTipAdapter>::`vftable';
  v7 = (char *)this + 32;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = a2;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = a3;
  if ( a3 )
    (*(void (__fastcall **)(struct Windows::Internal::Shell::Text::IShellKeyboardHostingPolicy *))(*(_QWORD *)a3 + 8LL))(a3);
  *((_QWORD *)this + 16) = a4;
  if ( a4 )
    (*(void (__fastcall **)(struct Windows::Internal::Shell::KeyboardHosting::IDesktopKeyboardHostingPolicy *))(*(_QWORD *)a4 + 8LL))(a4);
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 21) = 0x3FF0000000000000LL;
  *((_DWORD *)this + 44) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 41) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 45) = 0;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 47) = 0;
  *((_QWORD *)this + 48) = 0;
  *((_QWORD *)this + 49) = 0;
  *((_DWORD *)this + 100) = 11;
  *(_QWORD *)((char *)this + 404) = 0;
  *((_DWORD *)this + 103) = 11;
  *((_QWORD *)this + 52) = 0;
  *((_QWORD *)this + 53) = 0;
  *((_QWORD *)this + 54) = 0;
  *((_QWORD *)this + 55) = 0;
  *((_DWORD *)this + 112) = 0;
  *((_WORD *)this + 226) = 0;
  *(_OWORD *)((char *)this + 456) = 0;
  *(_OWORD *)((char *)this + 472) = 0;
  *((_BYTE *)this + 492) = 0;
  *((_DWORD *)this + 124) = 0;
  *((_WORD *)this + 250) = 0;
  *((_DWORD *)this + 126) = 0;
  *((_QWORD *)this + 64) = 0;
  *((_QWORD *)this + 65) = 0;
  *((_QWORD *)this + 66) = 0;
  *((_QWORD *)this + 67) = 0;
  *((_QWORD *)this + 68) = 0;
  std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>();
  *((_QWORD *)this + 69) = 0;
  *((_QWORD *)this + 70) = 0;
  *((_QWORD *)this + 71) = 0;
  *((_QWORD *)this + 72) = 0;
  if ( !v28 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x17C,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\tabtipadapter.cpp",
      v8);
  if ( !a3 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x17D,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\tabtipadapter.cpp",
      v8);
  if ( !a4 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x17E,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\tabtipadapter.cpp",
      v8);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 96);
  v9 = CoreUICreate((char *)this + 96);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x180,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\tabtipadapter.cpp",
      (const char *)(unsigned int)v9,
      v26);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 80);
  v10 = CoreUIFactoryCreate((char *)this + 80);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x181,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\tabtipadapter.cpp",
      (const char *)(unsigned int)v10,
      v26);
  v11 = SharedMessagePortRefPtr::Initialize((char *)this + 144);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x182,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\tabtipadapter.cpp",
      (const char *)(unsigned int)v11,
      v26);
  v27 = 0;
  v12 = *Windows::Internal::StringReference::StringReference(
           &string,
           L"Windows.UI.Internal.Text.Core.CoreKeyboardManager");
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
  ActivationFactory = RoGetActivationFactory(v12, &GUID_4781e102_173f_40ee_b985_685f98a866aa, &v27);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x188,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\tabtipadapter.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v26);
  v14 = v27;
  v15 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v27 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 32);
  v16 = v15(v14, (char *)this + 32);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x189,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\tabtipadapter.cpp",
      (const char *)(unsigned int)v16,
      v26);
  v17 = *(_QWORD *)v7;
  v18 = *(__int64 (__fastcall **)(__int64, char *))(**(_QWORD **)v7 + 696LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 40);
  v19 = v18(v17, (char *)this + 40);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18A,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\tabtipadapter.cpp",
      (const char *)(unsigned int)v19,
      v26);
  v26 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.UI.Internal.Text.Core.CoreInputViewManager",
         0x32u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v20 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
  v21 = RoGetActivationFactory(v20, &GUID_6fa49ca9_046b_4d5c_b942_7dbc066f6579, &v26);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x190,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\tabtipadapter.cpp",
      (const char *)(unsigned int)v21,
      v26);
  v22 = v26;
  v23 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v26 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 48);
  v24 = v23(v22, (char *)this + 48);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x191,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\tabtipadapter.cpp",
      (const char *)(unsigned int)v24,
      v26);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RacyAccessInMonitorInfo>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RacyAccessInMonitorInfo>::GetImpl'::`2'::impl)
    || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangOnCoreKeyboardHandler>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HangOnCoreKeyboardHandler>::GetImpl'::`2'::impl) )
  {
    *((_DWORD *)this + 144) = SHTaskPoolGetUniqueContext();
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
  return this;
}

```

## disassembly

```asm
0x18029e4d8  push    rbp
0x18029e4da  push    rbx
0x18029e4db  push    rsi
0x18029e4dc  push    rdi
0x18029e4dd  push    r12
0x18029e4df  push    r13
0x18029e4e1  push    r14
0x18029e4e3  push    r15
0x18029e4e5  mov     rbp, rsp
0x18029e4e8  sub     rsp, 78h
0x18029e4ec  mov     rax, cs:__security_cookie
0x18029e4f3  xor     rax, rsp
0x18029e4f6  mov     [rbp+var_10], rax
0x18029e4fa  mov     rbx, r9
0x18029e4fd  mov     rdi, r8
0x18029e500  mov     rax, rdx
0x18029e503  mov     [rbp+var_48], rdx
0x18029e507  mov     rsi, rcx
0x18029e50a  mov     [rbp+var_40], rcx
0x18029e50e  lea     rcx, ??_7?$IIterable@UDisplayRegionId@WindowingEnvironment@ApplicationModel@Internal@Windows@@@Collections@Foundation@Windows@@6B@; const Windows::Foundation::Collections::IIterable<Windows::Internal::ApplicationModel::WindowingEnvironment::DisplayRegionId>::`vftable'
0x18029e515  mov     [rsi], rcx
0x18029e518  lea     rcx, ??_7ISearchAppDesktopNotifications@Cortana@TwinUI@@6B@; const TwinUI::Cortana::ISearchAppDesktopNotifications::`vftable'
0x18029e51f  mov     [rsi+8], rcx
0x18029e523  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18029e52a  mov     qword ptr [rsi+18h], 1
0x18029e532  lea     rcx, ??_7?$heap_implements@UTabTipAdapter@KeyboardHosting@@@impl@winrt@@6B?$producer_convert@UTabTipAdapter@KeyboardHosting@@UIMessageProxyReconnectAdapterOwner@@X@12@@; const winrt::impl::heap_implements<KeyboardHosting::TabTipAdapter>::`vftable'{for `winrt::impl::producer_convert<KeyboardHosting::TabTipAdapter,IMessageProxyReconnectAdapterOwner,void>'}
0x18029e539  mov     [rsi], rcx
0x18029e53c  lea     rcx, ??_7TabTipAdapter@KeyboardHosting@@6B?$producer_convert@UTabTipAdapter@KeyboardHosting@@UIRemoteTabTipAdapter@@X@impl@winrt@@@; const KeyboardHosting::TabTipAdapter::`vftable'{for `winrt::impl::producer_convert<KeyboardHosting::TabTipAdapter,IRemoteTabTipAdapter,void>'}
0x18029e543  mov     [rsi+8], rcx
0x18029e547  lea     rcx, ??_7?$heap_implements@UTabTipAdapter@KeyboardHosting@@@impl@winrt@@6B@; const winrt::impl::heap_implements<KeyboardHosting::TabTipAdapter>::`vftable'
0x18029e54e  mov     [rsi+10h], rcx
0x18029e552  lea     r14, [rsi+20h]
0x18029e556  xor     edx, edx
0x18029e558  mov     [r14], rdx
0x18029e55b  lea     r13, [rsi+28h]
0x18029e55f  mov     [r13+0], rdx
0x18029e563  mov     [rsi+30h], rdx
0x18029e567  mov     [rsi+38h], rdx
0x18029e56b  mov     [rsi+40h], rdx
0x18029e56f  mov     [rsi+48h], rax
0x18029e573  lea     r15, [rsi+50h]
0x18029e577  mov     [r15], rdx
0x18029e57a  mov     [rsi+58h], rdx
0x18029e57e  lea     r12, [rsi+60h]
0x18029e582  mov     [r12], rdx
0x18029e586  mov     [rsi+68h], rdx
0x18029e58a  mov     [rsi+70h], rdx
0x18029e58e  mov     [rsi+78h], r8
0x18029e592  test    r8, r8
0x18029e595  jz      short loc_18029E5A8
0x18029e597  mov     rax, [r8]
0x18029e59a  mov     rcx, r8
0x18029e59d  mov     rax, [rax+8]
0x18029e5a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029e5a6  xor     edx, edx
0x18029e5a8  mov     [rsi+80h], rbx
0x18029e5af  test    rbx, rbx
0x18029e5b2  jz      short loc_18029E5C5
0x18029e5b4  mov     rax, [rbx]
0x18029e5b7  mov     rcx, rbx
0x18029e5ba  mov     rax, [rax+8]
0x18029e5be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029e5c3  xor     edx, edx
0x18029e5c5  mov     [rsi+88h], rdx
0x18029e5cc  lea     rax, [rsi+90h]
0x18029e5d3  mov     [rax], rdx
0x18029e5d6  mov     [rax+8], rdx
0x18029e5da  mov     rax, 3FF0000000000000h
0x18029e5e4  mov     [rsi+0A8h], rax
0x18029e5eb  mov     [rsi+0B0h], edx
0x18029e5f1  xor     eax, eax
0x18029e5f3  mov     [rsi+0B8h], rax
0x18029e5fa  mov     [rsi+0C0h], rax
0x18029e601  mov     [rsi+0C8h], rax
0x18029e608  mov     [rsi+0D0h], rax
0x18029e60f  mov     [rsi+0D8h], rax
0x18029e616  mov     [rsi+0E0h], rax
0x18029e61d  mov     [rsi+0E8h], rax
0x18029e624  mov     [rsi+0F0h], rax
0x18029e62b  mov     [rsi+0F8h], rax
0x18029e632  mov     [rsi+100h], rax
0x18029e639  mov     [rsi+108h], rax
0x18029e640  mov     [rsi+110h], rax
0x18029e647  mov     [rsi+118h], rax
0x18029e64e  mov     [rsi+120h], rax
0x18029e655  mov     [rsi+128h], rax
0x18029e65c  mov     [rsi+130h], rax
0x18029e663  mov     [rsi+138h], rax
0x18029e66a  mov     [rsi+140h], rax
0x18029e671  mov     [rsi+148h], rax
0x18029e678  mov     [rsi+150h], rax
0x18029e67f  mov     [rsi+158h], rax
0x18029e686  mov     [rsi+160h], rax
0x18029e68d  mov     [rsi+168h], rax
0x18029e694  mov     [rsi+170h], rax
0x18029e69b  mov     [rsi+178h], rax
0x18029e6a2  mov     [rsi+180h], rax
0x18029e6a9  mov     [rsi+188h], rax
0x18029e6b0  lea     ecx, [rax+0Bh]
0x18029e6b3  mov     [rsi+190h], ecx
0x18029e6b9  mov     [rsi+194h], rax
0x18029e6c0  mov     [rsi+19Ch], ecx
0x18029e6c6  mov     [rsi+1A0h], rax
0x18029e6cd  mov     [rsi+1A8h], rax
0x18029e6d4  mov     [rsi+1B0h], rax
0x18029e6db  mov     [rsi+1B8h], rax
0x18029e6e2  mov     [rsi+1C0h], eax
0x18029e6e8  mov     [rsi+1C4h], ax
0x18029e6ef  xorps   xmm0, xmm0
0x18029e6f2  movups  xmmword ptr [rsi+1C8h], xmm0
0x18029e6f9  xorps   xmm1, xmm1
0x18029e6fc  movups  xmmword ptr [rsi+1D8h], xmm1
0x18029e703  mov     [rsi+1ECh], dl
0x18029e709  mov     [rsi+1F0h], edx
0x18029e70f  mov     [rsi+1F4h], ax
0x18029e716  mov     [rsi+1F8h], edx
0x18029e71c  lea     rcx, [rsi+200h]
0x18029e723  mov     [rcx], rdx
0x18029e726  mov     [rcx+8], rdx
0x18029e72a  mov     [rcx+10h], rdx
0x18029e72e  mov     [rcx+18h], rdx
0x18029e732  mov     [rcx+20h], rdx
0x18029e736  call    ??$_Alloc_proxy@V?$allocator@U_Container_proxy@std@@@std@@@_Container_base12@std@@QEAAX$$QEAV?$allocator@U_Container_proxy@std@@@1@@Z; std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(std::allocator<std::_Container_proxy> &&)
0x18029e73b  nop
0x18029e73c  xor     eax, eax
0x18029e73e  mov     [rsi+228h], rax
0x18029e745  mov     [rsi+230h], rax
0x18029e74c  mov     [rsi+238h], rax
0x18029e753  mov     [rsi+240h], rax
0x18029e75a  mov     rcx, [rbp+40h]; this
0x18029e75e  cmp     [rbp+var_48], rax
0x18029e762  jz      loc_18029E97C
0x18029e768  mov     rcx, [rbp+40h]; this
0x18029e76c  test    rdi, rdi
0x18029e76f  jz      loc_18029E98E
0x18029e775  mov     rcx, [rbp+40h]; this
0x18029e779  test    rbx, rbx
0x18029e77c  jz      loc_18029E9A0
0x18029e782  mov     rcx, r12
0x18029e785  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18029e78a  mov     rcx, r12
0x18029e78d  call    cs:__imp_CoreUICreate
0x18029e793  mov     rcx, [rbp+40h]; this
0x18029e797  test    eax, eax
0x18029e799  js      loc_18029E9B2
0x18029e79f  mov     rcx, r15
0x18029e7a2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18029e7a7  mov     rcx, r15
0x18029e7aa  call    cs:__imp_CoreUIFactoryCreate
0x18029e7b0  mov     rcx, [rbp+40h]; this
0x18029e7b4  test    eax, eax
0x18029e7b6  js      loc_18029E9C7
0x18029e7bc  lea     rcx, [rsi+90h]
0x18029e7c3  call    ?Initialize@SharedMessagePortRefPtr@@QEAAJW4InputCapability@@@Z; SharedMessagePortRefPtr::Initialize(InputCapability)
0x18029e7c8  mov     rcx, [rbp+40h]; this
0x18029e7cc  test    eax, eax
0x18029e7ce  js      loc_18029E9DC
0x18029e7d4  mov     [rbp+var_50], 0
0x18029e7dc  lea     rdx, ?RuntimeClass_Windows_UI_Internal_Text_Core_CoreKeyboardManager@@3QBGB; "Windows.UI.Internal.Text.Core.CoreKeybo"...
0x18029e7e3  lea     rcx, [rbp+string]; string
0x18029e7e7  call    ??$?0$0DC@@StringReference@Internal@Windows@@QEAA@AEAY0DC@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[50])
0x18029e7ec  mov     rbx, [rax]
0x18029e7ef  lea     rcx, [rbp+var_50]
0x18029e7f3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18029e7f8  lea     r8, [rbp+var_50]
0x18029e7fc  lea     rdx, _GUID_4781e102_173f_40ee_b985_685f98a866aa
0x18029e803  mov     rcx, rbx
0x18029e806  call    cs:__imp_RoGetActivationFactory
0x18029e80c  mov     rcx, [rbp+40h]; this
0x18029e810  test    eax, eax
0x18029e812  js      loc_18029E9F1
0x18029e818  mov     rdi, [rbp+var_50]
0x18029e81c  mov     rax, [rdi]
0x18029e81f  mov     rbx, [rax+30h]
0x18029e823  mov     rcx, r14
0x18029e826  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18029e82b  mov     rdx, r14
0x18029e82e  mov     rcx, rdi
0x18029e831  mov     rax, rbx
0x18029e834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029e839  mov     rcx, [rbp+40h]; this
0x18029e83d  test    eax, eax
0x18029e83f  js      loc_18029EA06
0x18029e845  mov     rdi, [r14]
0x18029e848  mov     rax, [rdi]
0x18029e84b  mov     rbx, [rax+2B8h]
0x18029e852  mov     rcx, r13
0x18029e855  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18029e85a  mov     rdx, r13
0x18029e85d  mov     rcx, rdi
0x18029e860  mov     rax, rbx
0x18029e863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029e868  mov     rcx, [rbp+40h]; this
0x18029e86c  test    eax, eax
0x18029e86e  js      loc_18029EA1B
0x18029e874  mov     [rbp+var_58], 0
0x18029e87c  lea     r9, [rbp+string]; string
0x18029e880  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18029e884  mov     edx, 32h ; '2'; length
0x18029e889  lea     rcx, ?RuntimeClass_Windows_UI_Internal_Text_Core_CoreInputViewManager@@3QBGB; "Windows.UI.Internal.Text.Core.CoreInput"...
0x18029e890  call    cs:__imp_WindowsCreateStringReference
0x18029e896  test    eax, eax
0x18029e898  jns     short loc_18029E8AF
0x18029e89a  xor     r9d, r9d; lpArguments
0x18029e89d  xor     r8d, r8d; nNumberOfArguments
0x18029e8a0  lea     edx, [r9+1]; dwExceptionFlags
0x18029e8a4  mov     ecx, 0C000000Dh; dwExceptionCode
0x18029e8a9  call    cs:__imp_RaiseException
0x18029e8af  mov     rbx, [rbp+string]
0x18029e8b3  lea     rcx, [rbp+var_58]
0x18029e8b7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18029e8bc  lea     r8, [rbp+var_58]
0x18029e8c0  lea     rdx, _GUID_6fa49ca9_046b_4d5c_b942_7dbc066f6579
0x18029e8c7  mov     rcx, rbx
0x18029e8ca  call    cs:__imp_RoGetActivationFactory
0x18029e8d0  mov     rcx, [rbp+40h]; this
0x18029e8d4  test    eax, eax
0x18029e8d6  js      loc_18029EA30
0x18029e8dc  mov     rdi, [rbp+var_58]
0x18029e8e0  mov     rax, [rdi]
0x18029e8e3  mov     rbx, [rax+30h]
0x18029e8e7  lea     rcx, [rsi+30h]
0x18029e8eb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18029e8f0  lea     rdx, [rsi+30h]
0x18029e8f4  mov     rcx, rdi
0x18029e8f7  mov     rax, rbx
0x18029e8fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029e8ff  mov     rcx, [rbp+40h]; this
0x18029e903  test    eax, eax
0x18029e905  js      short loc_18029E967
0x18029e907  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RacyAccessInMonitorInfo@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RacyAccessInMonitorInfo@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RacyAccessInMonitorInfo> `wil::Feature<__WilFeatureTraits_Feature_RacyAccessInMonitorInfo>::GetImpl(void)'::`2'::impl
0x18029e90e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_RacyAccessInMonitorInfo@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RacyAccessInMonitorInfo>::__private_IsEnabled(void)
0x18029e913  test    al, al
0x18029e915  jnz     short loc_18029E927
0x18029e917  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HangOnCoreKeyboardHandler@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HangOnCoreKeyboardHandler@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangOnCoreKeyboardHandler> `wil::Feature<__WilFeatureTraits_Feature_HangOnCoreKeyboardHandler>::GetImpl(void)'::`2'::impl
0x18029e91e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_HangOnCoreKeyboardHandler@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangOnCoreKeyboardHandler>::__private_IsEnabled(void)
0x18029e923  test    al, al
0x18029e925  jz      short loc_18029E933
0x18029e927  call    cs:__imp_SHTaskPoolGetUniqueContext
0x18029e92d  mov     [rsi+240h], eax
0x18029e933  lea     rcx, [rbp+var_58]
0x18029e937  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18029e93c  nop
0x18029e93d  lea     rcx, [rbp+var_50]
0x18029e941  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18029e946  nop
0x18029e947  mov     rax, rsi
0x18029e94a  mov     rcx, [rbp+var_10]
0x18029e94e  xor     rcx, rsp; StackCookie
0x18029e951  call    __security_check_cookie
0x18029e956  add     rsp, 78h
0x18029e95a  pop     r15
0x18029e95c  pop     r14
0x18029e95e  pop     r13
0x18029e960  pop     r12
0x18029e962  pop     rdi
0x18029e963  pop     rsi
0x18029e964  pop     rbx
0x18029e965  pop     rbp
0x18029e966  retn
0x18029e967  mov     r9d, eax; char *
0x18029e96a  lea     r8, aPcshellTwinuiT_43; "pcshell\\twinui\\touchkeyboardexperienc"...
0x18029e971  mov     edx, 191h; void *
0x18029e976  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18029e97c  lea     r8, aPcshellTwinuiT_43; "pcshell\\twinui\\touchkeyboardexperienc"...
0x18029e983  mov     edx, 17Ch; void *
0x18029e988  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18029e98e  lea     r8, aPcshellTwinuiT_43; "pcshell\\twinui\\touchkeyboardexperienc"...
0x18029e995  mov     edx, 17Dh; void *
0x18029e99a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18029e9a0  lea     r8, aPcshellTwinuiT_43; "pcshell\\twinui\\touchkeyboardexperienc"...
0x18029e9a7  mov     edx, 17Eh; void *
0x18029e9ac  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18029e9b2  mov     r9d, eax; char *
0x18029e9b5  lea     r8, aPcshellTwinuiT_43; "pcshell\\twinui\\touchkeyboardexperienc"...
0x18029e9bc  mov     edx, 180h; void *
0x18029e9c1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18029e9c7  mov     r9d, eax; char *
0x18029e9ca  lea     r8, aPcshellTwinuiT_43; "pcshell\\twinui\\touchkeyboardexperienc"...
0x18029e9d1  mov     edx, 181h; void *
0x18029e9d6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18029e9dc  mov     r9d, eax; char *
0x18029e9df  lea     r8, aPcshellTwinuiT_43; "pcshell\\twinui\\touchkeyboardexperienc"...
0x18029e9e6  mov     edx, 182h; void *
0x18029e9eb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18029e9f1  mov     r9d, eax; char *
0x18029e9f4  lea     r8, aPcshellTwinuiT_43; "pcshell\\twinui\\touchkeyboardexperienc"...
0x18029e9fb  mov     edx, 188h; void *
0x18029ea00  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18029ea06  mov     r9d, eax; char *
0x18029ea09  lea     r8, aPcshellTwinuiT_43; "pcshell\\twinui\\touchkeyboardexperienc"...
0x18029ea10  mov     edx, 189h; void *
0x18029ea15  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18029ea1b  mov     r9d, eax; char *
0x18029ea1e  lea     r8, aPcshellTwinuiT_43; "pcshell\\twinui\\touchkeyboardexperienc"...
0x18029ea25  mov     edx, 18Ah; void *
0x18029ea2a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18029ea30  mov     r9d, eax; char *
0x18029ea33  lea     r8, aPcshellTwinuiT_43; "pcshell\\twinui\\touchkeyboardexperienc"...
0x18029ea3a  mov     edx, 190h; void *
  ... truncated ...
```
