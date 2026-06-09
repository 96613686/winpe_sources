# winrt::Windows::Internal::Shell::XamlExplorerHost::implementation::XamlExplorerHostWindow_WASDK::XamlExplorerHostWindow_WASDK(uint,winrt::Windows::Foundation::Rect const &,uint)

- ea: `0x1804a205c`
- end: `0x1804a2393`
- name: `??0XamlExplorerHostWindow_WASDK@implementation@XamlExplorerHost@Shell@Internal@Windows@winrt@@QEAA@IAEBURect@Foundation@56@I@Z`
- size: `823`
- prototype: `__int64 __fastcall(winrt::Windows::Internal::Shell::XamlExplorerHost::implementation::XamlExplorerHostWindow_WASDK *__hidden this, unsigned int, const struct winrt::Windows::Foundation::Rect *, unsigned int)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1804a1ef8`
- `0x1804a1f64`

## callees

- `0x18001bf0c`
- `0x18006e370`
- `0x18027e698`
- `0x1802885f8`
- `0x180356360`
- `0x180356edc`
- `0x18049f2bc`
- `0x18049f8f8`
- `0x18049fde0`
- `0x1804a07b4`
- `0x1804a0a38`
- `0x1804a205c`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1804a20ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1804a20ef`
- `USER32!RegisterClassW` at `0x1804a2157`
- `USER32!RegisterClassW` at `0x1804a2157`
- `USER32!LoadCursorW` at `0x1804a211e`
- `USER32!LoadCursorW` at `0x1804a211e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x1804a221e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x1804a2232`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x1804a221e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x1804a2232`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x1804a233b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x1804a233b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x1804a232c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x1804a232c`
- `api-ms-win-rtcore-ntuser-private-l1-1-0!CreateWindowInBand` at `0x1804a21c9`
- `api-ms-win-rtcore-ntuser-private-l1-1-0!CreateWindowInBand` at `0x1804a21c9`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x1804a2345`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x1804a2345`
- `ext-ms-win-ntuser-private-l1-1-1!SetWindowCompositionAttribute` at `0x1804a220a`
- `ext-ms-win-ntuser-private-l1-1-1!SetWindowCompositionAttribute` at `0x1804a220a`
- `GDI32!GetStockObject` at `0x1804a212c`
- `GDI32!GetStockObject` at `0x1804a212c`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
winrt::Windows::Internal::Shell::XamlExplorerHost::implementation::XamlExplorerHostWindow_WASDK *__fastcall winrt::Windows::Internal::Shell::XamlExplorerHost::implementation::XamlExplorerHostWindow_WASDK::XamlExplorerHostWindow_WASDK(
        winrt::Windows::Internal::Shell::XamlExplorerHost::implementation::XamlExplorerHostWindow_WASDK *this,
        int a2,
        const struct winrt::Windows::Foundation::Rect *a3,
        int a4)
{
  char *v8; // r13
  const char *v9; // r9
  int v10; // r14d
  int cy; // r15d
  const char *v12; // r9
  __int64 v13; // rax
  __int64 v14; // rbx
  unsigned int v15; // eax
  __int64 v16; // rax
  _QWORD *v17; // rbx
  unsigned int v18; // eax
  _BYTE v20[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v21; // [rsp+78h] [rbp-88h] BYREF
  int v22; // [rsp+80h] [rbp-80h] BYREF
  __int128 v23; // [rsp+88h] [rbp-78h]
  winrt::Windows::Internal::Shell::XamlExplorerHost::implementation::XamlExplorerHostWindow_WASDK *v24; // [rsp+98h] [rbp-68h]
  _BYTE v25[8]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v26; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v27[4]; // [rsp+B0h] [rbp-50h] BYREF
  WNDCLASSW WndClass; // [rsp+D0h] [rbp-30h] BYREF
  int v29; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v24 = this;
  *((_QWORD *)this + 1) = &winrt::impl::produce<winrt::Windows::Internal::Shell::XamlExplorerHost::implementation::XamlExplorerHostWindow_WASDK,winrt::Windows::Internal::Shell::XamlExplorerHost::IXamlExplorerHostWindow_WASDK>::`vftable';
  *((_QWORD *)this + 2) = &winrt::impl::produce<winrt::Windows::Internal::Shell::XamlExplorerHost::implementation::XamlExplorerHostWindow_WASDK,winrt::Windows::Foundation::IClosable>::`vftable';
  *(_QWORD *)this = &Windows::Foundation::ITypedEventHandler<Windows::Internal::Shell::Experience::IBaseExperienceManager *,Windows::Internal::Shell::Experience::IVisibilityChangedEventArgs *>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *((_QWORD *)this + 4) = 1;
  *(_QWORD *)this = &winrt::Windows::Internal::Shell::XamlExplorerHost::implementation::XamlExplorerHostWindow_WASDK::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Internal::Shell::XamlExplorerHost::implementation::XamlExplorerHostWindow_WASDK,std::tuple<winrt::Windows::Internal::Shell::XamlExplorerHost::XamlExplorerHostWindow_WASDK,winrt::Windows::Foundation::IClosable,IXamlExplorerHostWindowLocal>>'};
  *((_QWORD *)this + 3) = &winrt::impl::heap_implements<winrt::Windows::Internal::Shell::XamlExplorerHost::implementation::XamlExplorerHostWindow_WASDK>::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Internal::Shell::XamlExplorerHost::implementation::XamlExplorerHostWindow_WASDK,winrt::Windows::Internal::Shell::XamlExplorerHost::XamlExplorerHostWindow_WASDK,winrt::Windows::Foundation::IClosable,IXamlExplorerHostWindowLocal>'};
  *((_QWORD *)this + 5) = 0;
  v8 = (char *)this + 48;
  *((_QWORD *)this + 6) = 0;
  *((_WORD *)this + 28) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 18) = GetCurrentThreadId();
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  memset_0(&WndClass, 0, sizeof(WndClass));
  WndClass.hCursor = LoadCursorW(0, (LPCWSTR)0x7F00);
  WndClass.hbrBackground = (HBRUSH)GetStockObject(4);
  WndClass.lpszClassName = L"XamlExplorerHostIslandWindow_WASDK";
  WndClass.style = 3;
  WndClass.lpfnWndProc = (WNDPROC)winrt::Windows::Internal::Shell::XamlExplorerHost::implementation::XamlExplorerHostWindow_WASDK::WndProc;
  RegisterClassW(&WndClass);
  if ( *((_QWORD *)this + 5) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x76,
      (unsigned int)"pcshell\\twinui\\xamlexplorerhost\\lib\\XamlExplorerHostIslandWindow_WASDK.cpp",
      v9);
  v10 = (int)*((float *)a3 + 2);
  cy = (int)*((float *)a3 + 3);
  CreateWindowInBand(
    a4 | 0x200000u,
    WndClass.lpszClassName,
    &pvData,
    0x80000000LL,
    (int)*(float *)a3,
    (int)*((float *)a3 + 1),
    v10,
    cy,
    0,
    0,
    WndClass.hInstance,
    this,
    a2);
  if ( !*((_QWORD *)this + 5) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x8C,
      (unsigned int)"pcshell\\twinui\\xamlexplorerhost\\lib\\XamlExplorerHostIslandWindow_WASDK.cpp",
      v12);
  v29 = 1;
  v27[0] = 13;
  v27[1] = &v29;
  v27[2] = 4;
  SetWindowCompositionAttribute(*((_QWORD *)this + 5), v27);
  SetPropW(*((HWND *)this + 5), L"NonRudeHWND", HANDLE_FLAG_INHERIT);
  SetPropW(*((HWND *)this + 5), L"UIA_WindowPatternEnabled", HANDLE_FLAG_INHERIT);
  v13 = winrt::Microsoft::UI::Xaml::Hosting::DesktopWindowXamlSource::DesktopWindowXamlSource((winrt::Microsoft::UI::Xaml::Hosting::DesktopWindowXamlSource *)&v26);
  winrt::WindowsUdk::UI::Shell::ShellViewCoordinator::operator=(v8, v13);
  winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v26);
  v14 = *((_QWORD *)this + 5);
  v26 = 0;
  winrt::Microsoft::UI::EnsureInteropImplLoaded();
  v22 = 0;
  v23 = 0;
  v15 = winrt::Microsoft::UI::s_impl(v14, &v26);
  winrt::check_hresult(v20, v15, &v22);
  v21 = v26;
  winrt::impl::consume_Windows_UI_Xaml_Controls_IBorder<winrt::Windows::UI::Xaml::Controls::IBorder>::Child(v8, &v21);
  v16 = winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::SiteBridge(
          v8,
          &v21);
  v17 = (_QWORD *)winrt::impl::consume_Microsoft_UI_Content_IDesktopSiteBridge<winrt::Microsoft::UI::Content::DesktopChildSiteBridge>::WindowId(
                    v16,
                    v25);
  v26 = 0;
  winrt::Microsoft::UI::EnsureInteropImplLoaded();
  v22 = 0;
  v23 = 0;
  v18 = ((__int64 (__fastcall *)(_QWORD, __int64 *))qword_1808D9E30)(*v17, &v26);
  winrt::check_hresult(v20, v18, &v22);
  *((_QWORD *)this + 8) = v26;
  winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v21);
  SetWindowPos(*((HWND *)this + 8), 0, 0, 0, v10, cy, 0x56u);
  ShowWindow(*((HWND *)this + 5), 5);
  UpdateWindow(*((HWND *)this + 5));
  return this;
}

```

## disassembly

```asm
0x1804a205c  push    rbp
0x1804a205e  push    rbx
0x1804a205f  push    rsi
0x1804a2060  push    rdi
0x1804a2061  push    r12
0x1804a2063  push    r13
0x1804a2065  push    r14
0x1804a2067  push    r15
0x1804a2069  lea     rbp, [rsp-38h]
0x1804a206e  sub     rsp, 138h
0x1804a2075  mov     rax, cs:__security_cookie
0x1804a207c  xor     rax, rsp
0x1804a207f  mov     [rbp+70h+var_48], rax
0x1804a2083  mov     esi, r9d
0x1804a2086  mov     rbx, r8
0x1804a2089  mov     r12d, edx
0x1804a208c  mov     rdi, rcx
0x1804a208f  mov     [rbp+70h+var_D8], rcx
0x1804a2093  lea     rax, ??_7?$produce@UXamlExplorerHostWindow_WASDK@implementation@XamlExplorerHost@Shell@Internal@Windows@winrt@@UIXamlExplorerHostWindow_WASDK@34567@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Internal::Shell::XamlExplorerHost::implementation::XamlExplorerHostWindow_WASDK,winrt::Windows::Internal::Shell::XamlExplorerHost::IXamlExplorerHostWindow_WASDK>::`vftable'
0x1804a209a  mov     [rcx+8], rax
0x1804a209e  lea     rax, ??_7?$produce@UXamlExplorerHostWindow_WASDK@implementation@XamlExplorerHost@Shell@Internal@Windows@winrt@@UIClosable@Foundation@67@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Internal::Shell::XamlExplorerHost::implementation::XamlExplorerHostWindow_WASDK,winrt::Windows::Foundation::IClosable>::`vftable'
0x1804a20a5  mov     [rcx+10h], rax
0x1804a20a9  lea     rax, ??_7?$ITypedEventHandler@PEAUIBaseExperienceManager@Experience@Shell@Internal@Windows@@PEAUIVisibilityChangedEventArgs@2345@@Foundation@Windows@@6B@; const Windows::Foundation::ITypedEventHandler<Windows::Internal::Shell::Experience::IBaseExperienceManager *,Windows::Internal::Shell::Experience::IVisibilityChangedEventArgs *>::`vftable'
0x1804a20b0  mov     [rcx], rax
0x1804a20b3  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1804a20ba  mov     qword ptr [rcx+20h], 1
0x1804a20c2  lea     rax, ??_7XamlExplorerHostWindow_WASDK@implementation@XamlExplorerHost@Shell@Internal@Windows@winrt@@6B?$producers_base@UXamlExplorerHostWindow_WASDK@implementation@XamlExplorerHost@Shell@Internal@Windows@winrt@@V?$tuple@UXamlExplorerHostWindow_WASDK@XamlExplorerHost@Shell@Internal@Windows@winrt@@UIClosable@Foundation@56@UIXamlExplorerHostWindowLocal@@@std@@@impl@6@@; const winrt::Windows::Internal::Shell::XamlExplorerHost::implementation::XamlExplorerHostWindow_WASDK::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Internal::Shell::XamlExplorerHost::implementation::XamlExplorerHostWindow_WASDK,std::tuple<winrt::Windows::Internal::Shell::XamlExplorerHost::XamlExplorerHostWindow_WASDK,winrt::Windows::Foundation::IClosable,IXamlExplorerHostWindowLocal>>'}
0x1804a20c9  mov     [rcx], rax
0x1804a20cc  lea     rax, ??_7?$heap_implements@UXamlExplorerHostWindow_WASDK@implementation@XamlExplorerHost@Shell@Internal@Windows@winrt@@@impl@winrt@@6B?$root_implements@UXamlExplorerHostWindow_WASDK@implementation@XamlExplorerHost@Shell@Internal@Windows@winrt@@U134567@UIClosable@Foundation@67@UIXamlExplorerHostWindowLocal@@@12@@; const winrt::impl::heap_implements<winrt::Windows::Internal::Shell::XamlExplorerHost::implementation::XamlExplorerHostWindow_WASDK>::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Internal::Shell::XamlExplorerHost::implementation::XamlExplorerHostWindow_WASDK,winrt::Windows::Internal::Shell::XamlExplorerHost::XamlExplorerHostWindow_WASDK,winrt::Windows::Foundation::IClosable,IXamlExplorerHostWindowLocal>'}
0x1804a20d3  mov     [rcx+18h], rax
0x1804a20d7  xor     r14d, r14d
0x1804a20da  mov     [rcx+28h], r14
0x1804a20de  lea     r13, [rcx+30h]
0x1804a20e2  mov     [r13+0], r14
0x1804a20e6  mov     [rcx+38h], r14w
0x1804a20eb  mov     [rcx+40h], r14
0x1804a20ef  call    cs:__imp_GetCurrentThreadId
0x1804a20f5  mov     [rdi+48h], eax
0x1804a20f8  mov     [rdi+50h], r14
0x1804a20fc  mov     [rdi+58h], r14
0x1804a2100  mov     [rdi+60h], r14
0x1804a2104  mov     [rdi+68h], r14
0x1804a2108  xor     edx, edx; Val
0x1804a210a  lea     r8d, [r14+48h]; Size
0x1804a210e  lea     rcx, [rbp+70h+WndClass]; void *
0x1804a2112  call    memset_0
0x1804a2117  mov     edx, 7F00h; lpCursorName
0x1804a211c  xor     ecx, ecx; hInstance
0x1804a211e  call    cs:__imp_LoadCursorW
0x1804a2124  mov     [rbp+70h+WndClass.hCursor], rax
0x1804a2128  lea     ecx, [r14+4]; i
0x1804a212c  call    cs:__imp_GetStockObject
0x1804a2132  mov     [rbp+70h+WndClass.hbrBackground], rax
0x1804a2136  lea     rax, aXamlexplorerho; "XamlExplorerHostIslandWindow_WASDK"
0x1804a213d  mov     [rbp+70h+WndClass.lpszClassName], rax
0x1804a2141  mov     [rbp+70h+WndClass.style], 3
0x1804a2148  lea     rax, ?WndProc@XamlExplorerHostWindow_WASDK@implementation@XamlExplorerHost@Shell@Internal@Windows@winrt@@SA_JQEAUHWND__@@I_K_J@Z; winrt::Windows::Internal::Shell::XamlExplorerHost::implementation::XamlExplorerHostWindow_WASDK::WndProc(HWND__ * const,uint,unsigned __int64,__int64)
0x1804a214f  mov     [rbp+70h+WndClass.lpfnWndProc], rax
0x1804a2153  lea     rcx, [rbp+70h+WndClass]; lpWndClass
0x1804a2157  call    cs:__imp_RegisterClassW
0x1804a215d  mov     rcx, [rbp+78h]; this
0x1804a2161  cmp     [rdi+28h], r14
0x1804a2165  jnz     loc_1804A2381
0x1804a216b  cvttss2si r14d, dword ptr [rbx+8]
0x1804a2171  cvttss2si r15d, dword ptr [rbx+0Ch]
0x1804a2177  cvttss2si ecx, dword ptr [rbx+4]
0x1804a217c  cvttss2si edx, dword ptr [rbx]
0x1804a2180  bts     esi, 15h
0x1804a2184  mov     [rsp+170h+var_110], r12d
0x1804a2189  mov     [rsp+170h+var_118], rdi
0x1804a218e  mov     rax, [rbp+70h+WndClass.hInstance]
0x1804a2192  mov     [rsp+170h+var_120], rax
0x1804a2197  xor     r12d, r12d
0x1804a219a  mov     [rsp+170h+var_128], r12
0x1804a219f  mov     [rsp+170h+var_130], r12
0x1804a21a4  mov     [rsp+170h+var_138], r15d
0x1804a21a9  mov     [rsp+170h+uFlags], r14d
0x1804a21ae  mov     [rsp+170h+cy], ecx
0x1804a21b2  mov     [rsp+170h+var_150], edx
0x1804a21b6  mov     r9d, 80000000h
0x1804a21bc  lea     r8, pvData
0x1804a21c3  mov     rdx, [rbp+70h+WndClass.lpszClassName]
0x1804a21c7  mov     ecx, esi
0x1804a21c9  call    cs:__imp_CreateWindowInBand
0x1804a21cf  cmp     [rdi+28h], r12
0x1804a21d3  setz    al
0x1804a21d6  mov     rcx, [rbp+78h]; this
0x1804a21da  test    al, al
0x1804a21dc  jnz     loc_1804A236F
0x1804a21e2  lea     ebx, [r12+1]
0x1804a21e7  mov     [rbp+70h+var_50], ebx
0x1804a21ea  mov     [rbp+70h+var_C0], 0Dh
0x1804a21f2  lea     rax, [rbp+70h+var_50]
0x1804a21f6  mov     [rbp+70h+var_B8], rax
0x1804a21fa  mov     [rbp+70h+var_B0], 4
0x1804a2202  lea     rdx, [rbp+70h+var_C0]
0x1804a2206  mov     rcx, [rdi+28h]
0x1804a220a  call    cs:__imp_SetWindowCompositionAttribute
0x1804a2210  mov     r8d, ebx; hData
0x1804a2213  lea     rdx, aNonrudehwnd; "NonRudeHWND"
0x1804a221a  mov     rcx, [rdi+28h]; hWnd
0x1804a221e  call    cs:__imp_SetPropW
0x1804a2224  mov     r8d, ebx; hData
0x1804a2227  lea     rdx, aUiaWindowpatte; "UIA_WindowPatternEnabled"
0x1804a222e  mov     rcx, [rdi+28h]; hWnd
0x1804a2232  call    cs:__imp_SetPropW
0x1804a2238  lea     rcx, [rbp+70h+var_C8]; this
0x1804a223c  call    ??0DesktopWindowXamlSource@Hosting@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::Hosting::DesktopWindowXamlSource::DesktopWindowXamlSource(void)
0x1804a2241  mov     rdx, rax
0x1804a2244  mov     rcx, r13
0x1804a2247  call    ??4ShellViewCoordinator@Shell@UI@WindowsUdk@winrt@@QEAAAEAU01234@$$QEAU01234@@Z; winrt::WindowsUdk::UI::Shell::ShellViewCoordinator::operator=(winrt::WindowsUdk::UI::Shell::ShellViewCoordinator &&)
0x1804a224c  lea     rcx, [rbp+70h+var_C8]; this
0x1804a2250  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1804a2255  mov     rbx, [rdi+28h]
0x1804a2259  mov     [rbp+70h+var_C8], r12
0x1804a225d  call    winrt__Microsoft__UI__EnsureInteropImplLoaded
0x1804a2262  mov     [rbp+70h+var_F0], r12d
0x1804a2266  xorps   xmm0, xmm0
0x1804a2269  movdqu  [rbp+70h+var_E8], xmm0
0x1804a226e  lea     rdx, [rbp+70h+var_C8]
0x1804a2272  mov     rcx, rbx
0x1804a2275  mov     rax, cs:?s_impl@UI@Microsoft@winrt@@3U_InteropImpl@123@A; winrt::Microsoft::UI::_InteropImpl winrt::Microsoft::UI::s_impl
0x1804a227c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804a2281  lea     r8, [rbp+70h+var_F0]
0x1804a2285  mov     edx, eax
0x1804a2287  lea     rcx, [rsp+170h+var_100]
0x1804a228c  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1804a2291  mov     rax, [rbp+70h+var_C8]
0x1804a2295  mov     [rsp+170h+var_F8], rax
0x1804a229a  lea     rdx, [rsp+170h+var_F8]
0x1804a229f  mov     rcx, r13
0x1804a22a2  call    ?Child@?$consume_Windows_UI_Xaml_Controls_IBorder@UIBorder@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUUIElement@Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_IBorder<winrt::Windows::UI::Xaml::Controls::IBorder>::Child(winrt::Windows::UI::Xaml::UIElement const &)
0x1804a22a7  lea     rdx, [rsp+170h+var_F8]
0x1804a22ac  mov     rcx, r13
0x1804a22af  call    ?SiteBridge@?$consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource@UIDesktopWindowXamlSource@Hosting@Xaml@UI@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::SiteBridge(void)
0x1804a22b4  nop
0x1804a22b5  lea     rdx, [rbp+70h+var_D0]
0x1804a22b9  mov     rcx, rax
0x1804a22bc  call    ?WindowId@?$consume_Microsoft_UI_Content_IDesktopSiteBridge@UDesktopChildSiteBridge@Content@UI@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_UI_Content_IDesktopSiteBridge<winrt::Microsoft::UI::Content::DesktopChildSiteBridge>::WindowId(void)
0x1804a22c1  mov     rbx, rax
0x1804a22c4  mov     [rbp+70h+var_C8], r12
0x1804a22c8  call    winrt__Microsoft__UI__EnsureInteropImplLoaded
0x1804a22cd  mov     [rbp+70h+var_F0], r12d
0x1804a22d1  xorps   xmm0, xmm0
0x1804a22d4  movdqu  [rbp+70h+var_E8], xmm0
0x1804a22d9  lea     rdx, [rbp+70h+var_C8]
0x1804a22dd  mov     rcx, [rbx]
0x1804a22e0  mov     rax, cs:qword_1808D9E30
0x1804a22e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804a22ec  lea     r8, [rbp+70h+var_F0]
0x1804a22f0  mov     edx, eax
0x1804a22f2  lea     rcx, [rsp+170h+var_100]
0x1804a22f7  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1804a22fc  mov     rax, [rbp+70h+var_C8]
0x1804a2300  mov     [rdi+40h], rax
0x1804a2304  lea     rcx, [rsp+170h+var_F8]; this
0x1804a2309  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1804a230e  mov     [rsp+170h+uFlags], 56h ; 'V'; uFlags
0x1804a2316  mov     [rsp+170h+cy], r15d; cy
0x1804a231b  mov     [rsp+170h+var_150], r14d; cx
0x1804a2320  xor     r9d, r9d; Y
0x1804a2323  xor     r8d, r8d; X
0x1804a2326  xor     edx, edx; hWndInsertAfter
0x1804a2328  mov     rcx, [rdi+40h]; hWnd
0x1804a232c  call    cs:__imp_SetWindowPos
0x1804a2332  lea     edx, [r12+5]; nCmdShow
0x1804a2337  mov     rcx, [rdi+28h]; hWnd
0x1804a233b  call    cs:__imp_ShowWindow
0x1804a2341  mov     rcx, [rdi+28h]; hWnd
0x1804a2345  call    cs:__imp_UpdateWindow
0x1804a234b  nop
0x1804a234c  mov     rax, rdi
0x1804a234f  mov     rcx, [rbp+70h+var_48]
0x1804a2353  xor     rcx, rsp; StackCookie
0x1804a2356  call    __security_check_cookie
0x1804a235b  add     rsp, 138h
0x1804a2362  pop     r15
0x1804a2364  pop     r14
0x1804a2366  pop     r13
0x1804a2368  pop     r12
0x1804a236a  pop     rdi
0x1804a236b  pop     rsi
0x1804a236c  pop     rbx
0x1804a236d  pop     rbp
0x1804a236e  retn
0x1804a236f  lea     r8, aPcshellTwinuiX_9; "pcshell\\twinui\\xamlexplorerhost\\lib"...
0x1804a2376  mov     edx, 8Ch; void *
0x1804a237b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1804a2381  lea     r8, aPcshellTwinuiX_9; "pcshell\\twinui\\xamlexplorerhost\\lib"...
0x1804a2388  mov     edx, 76h ; 'v'; void *
0x1804a238d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
