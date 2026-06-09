# winrt::WindowsUdk::Security::Credentials::UI::implementation::CredUICoordinator::GetOrCreateForWindow(unsigned __int64)

- ea: `0x1802fa130`
- end: `0x1802fa27e`
- name: `?GetOrCreateForWindow@CredUICoordinator@implementation@UI@Credentials@Security@WindowsUdk@winrt@@SA?AU134567@_K@Z`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1802fa0e0`

## callees

- `0x18000b428`
- `0x180011f98`
- `0x18002a030`
- `0x1800d6d38`
- `0x1800dca48`
- `0x18015d898`
- `0x180294f10`
- `0x1802f9af4`
- `0x1802fa130`
- `0x1802fa3b8`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x1802fa185`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x1802fa185`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1802fa198`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1802fa198`
- `twinapi.appcore!__imp_CoreRegisterWindowService` at `0x1802fa208`
- `twinapi.appcore!__imp_CoreRegisterWindowService` at `0x1802fa208`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x1802fa1c2`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x1802fa1c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
winrt *__fastcall winrt::WindowsUdk::Security::Credentials::UI::implementation::CredUICoordinator::GetOrCreateForWindow(
        winrt *a1,
        __int64 a2)
{
  struct IUnknown *v4; // rdx
  void **v5; // rax
  __int64 v6; // rax
  unsigned int v7; // eax
  const struct winrt::impl::slim_source_location *v9; // rax
  const struct winrt::impl::slim_source_location *v10; // rax
  int pExceptionObject; // [rsp+28h] [rbp-38h] BYREF
  __int128 v12; // [rsp+30h] [rbp-30h]
  _BYTE v13[32]; // [rsp+40h] [rbp-20h] BYREF
  char v14; // [rsp+80h] [rbp+20h] BYREF

  *(_QWORD *)a1 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59048065>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59048065>::GetImpl'::`2'::impl) )
  {
    if ( !a2 )
    {
      v9 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v13);
      winrt::hresult_invalid_argument::hresult_invalid_argument(
        (winrt::hresult_invalid_argument *)&pExceptionObject,
        v9);
      throw (winrt::hresult_invalid_argument *)&pExceptionObject;
    }
    if ( !IsWindow((HWND)(int)a2) || !GetWindowThreadProcessId((HWND)(int)a2, 0) )
    {
      v10 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v13);
      winrt::hresult_invalid_argument::hresult_invalid_argument(
        (winrt::hresult_invalid_argument *)&pExceptionObject,
        v10);
      throw (winrt::hresult_invalid_argument *)&pExceptionObject;
    }
    v5 = winrt::put_abi(a1, v4);
    if ( (unsigned int)CoreQueryWindowService(
                         (int)a2,
                         qword_180537EC8,
                         &winrt::impl::guid_v<winrt::WindowsUdk::Security::Credentials::UI::ICredUICoordinator>,
                         v5) == -2147221163 )
    {
      v6 = winrt::make<winrt::WindowsUdk::Security::Credentials::UI::implementation::CredUICoordinator,>(&v14);
      winrt::Windows::Foundation::IUnknown::operator=(a1, v6);
      winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v14);
      pExceptionObject = 0;
      v12 = 0;
      v7 = CoreRegisterWindowService((int)a2, qword_180537EC8, *(_QWORD *)a1);
      winrt::check_hresult(&v14, v7, &pExceptionObject);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1802fa130  mov     [rsp-8+arg_8], rbx
0x1802fa135  mov     [rsp-8+arg_18], rdi
0x1802fa13a  mov     [rsp-8+arg_0], rcx
0x1802fa13f  push    rbp
0x1802fa140  mov     rbp, rsp
0x1802fa143  sub     rsp, 60h
0x1802fa147  mov     rdi, rdx
0x1802fa14a  mov     rbx, rcx
0x1802fa14d  mov     [rbp+var_40], 0
0x1802fa154  mov     qword ptr [rcx], 0
0x1802fa15b  mov     [rbp+var_40], 1
0x1802fa162  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59048065@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59048065@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59048065> `wil::Feature<__WilFeatureTraits_Feature_59048065>::GetImpl(void)'::`2'::impl
0x1802fa169  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59048065@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59048065>::__private_IsEnabled(void)
0x1802fa16e  test    al, al
0x1802fa170  jz      loc_1802FA21D
0x1802fa176  test    rdi, rdi
0x1802fa179  jz      loc_1802FA232
0x1802fa17f  movsxd  rdi, edi
0x1802fa182  mov     rcx, rdi; hWnd
0x1802fa185  call    cs:__imp_IsWindow
0x1802fa18b  test    eax, eax
0x1802fa18d  jz      loc_1802FA258
0x1802fa193  xor     edx, edx; lpdwProcessId
0x1802fa195  mov     rcx, rdi; hWnd
0x1802fa198  call    cs:__imp_GetWindowThreadProcessId
0x1802fa19e  test    eax, eax
0x1802fa1a0  jz      loc_1802FA258
0x1802fa1a6  mov     rcx, rbx; this
0x1802fa1a9  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x1802fa1ae  mov     r9, rax
0x1802fa1b1  lea     r8, ??$guid_v@UICredUICoordinator@UI@Credentials@Security@WindowsUdk@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::WindowsUdk::Security::Credentials::UI::ICredUICoordinator>
0x1802fa1b8  lea     rdx, qword_180537EC8
0x1802fa1bf  mov     rcx, rdi
0x1802fa1c2  call    cs:__imp_CoreQueryWindowService
0x1802fa1c8  cmp     eax, 80040155h
0x1802fa1cd  jnz     short loc_1802FA21D
0x1802fa1cf  lea     rcx, [rbp+arg_10]
0x1802fa1d3  call    ??$make@UCredUICoordinator@implementation@UI@Credentials@Security@WindowsUdk@winrt@@$$V@winrt@@YA?A_PXZ
0x1802fa1d8  mov     rdx, rax
0x1802fa1db  mov     rcx, rbx
0x1802fa1de  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x1802fa1e3  lea     rcx, [rbp+arg_10]; this
0x1802fa1e7  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1802fa1ec  mov     [rbp+pExceptionObject], 0
0x1802fa1f3  xorps   xmm0, xmm0
0x1802fa1f6  movdqu  [rbp+var_30], xmm0
0x1802fa1fb  mov     r8, [rbx]
0x1802fa1fe  lea     rdx, qword_180537EC8
0x1802fa205  mov     rcx, rdi
0x1802fa208  call    cs:__imp_CoreRegisterWindowService
0x1802fa20e  lea     r8, [rbp+pExceptionObject]
0x1802fa212  mov     edx, eax
0x1802fa214  lea     rcx, [rbp+arg_10]
0x1802fa218  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1802fa21d  mov     rax, rbx
0x1802fa220  lea     r11, [rsp+60h+var_s0]
0x1802fa225  mov     rbx, [r11+18h]
0x1802fa229  mov     rdi, [r11+28h]
0x1802fa22d  mov     rsp, r11
0x1802fa230  pop     rbp
0x1802fa231  retn
0x1802fa232  lea     rcx, [rbp+var_20]
0x1802fa236  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1802fa23b  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1802fa23e  lea     rcx, [rbp+pExceptionObject]; this
0x1802fa242  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::impl::slim_source_location const &)
0x1802fa247  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x1802fa24e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1802fa252  call    _CxxThrowException_0
0x1802fa258  lea     rcx, [rbp+var_20]
0x1802fa25c  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1802fa261  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1802fa264  lea     rcx, [rbp+pExceptionObject]; this
0x1802fa268  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::impl::slim_source_location const &)
0x1802fa26d  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x1802fa274  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1802fa278  call    _CxxThrowException_0
```
