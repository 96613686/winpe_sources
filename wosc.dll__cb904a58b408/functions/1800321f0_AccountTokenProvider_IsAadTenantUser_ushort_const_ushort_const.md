# AccountTokenProvider::IsAadTenantUser(ushort const *,ushort const *)

- ea: `0x1800321f0`
- end: `0x180032451`
- name: `?IsAadTenantUser@AccountTokenProvider@@UEAA_NPEBG0@Z`
- size: `609`
- prototype: `bool __fastcall(AccountTokenProvider *__hidden this, LPCWCH lpString2, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003110`
- `0x180005f50`
- `0x18000a250`
- `0x18000b0bc`
- `0x1800101fc`
- `0x180011b20`
- `0x180031b74`
- `0x180031c6c`
- `0x180031d54`
- `0x180031fcc`
- `0x1800321f0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003236f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003236f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003225c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003225c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180032389`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180032389`

## string_xrefs

- `0x18003223c`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`
- `0x1800323eb`: `onecore\base\flighting\onesettings\libs\identityprovider\accounttokenprovider.cpp`
- `0x180032400`: `onecore\base\flighting\onesettings\libs\identityprovider\accounttokenprovider.cpp`
- `0x180032415`: `onecore\base\flighting\onesettings\libs\identityprovider\accounttokenprovider.cpp`
- `0x18003242a`: `onecore\base\flighting\onesettings\libs\identityprovider\accounttokenprovider.cpp`
- `0x18003243f`: `onecore\base\flighting\onesettings\libs\identityprovider\accounttokenprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
bool __fastcall AccountTokenProvider::IsAadTenantUser(
        AccountTokenProvider *this,
        LPCWCH lpString2,
        const unsigned __int16 *a3)
{
  int ActivationFactory; // eax
  int AccountProvider; // eax
  int WebTokenRequestResult; // eax
  AccountTokenProvider *v10; // rcx
  int WebTokenResponse; // eax
  int TenantId; // eax
  const WCHAR *StringRawBuffer; // rax
  bool v14; // bl
  int bIgnoreCase; // [rsp+20h] [rbp-60h]
  int bIgnoreCasea; // [rsp+20h] [rbp-60h]
  struct Windows::Security::Credentials::IWebAccountProvider *v17; // [rsp+30h] [rbp-50h] BYREF
  struct Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics *v18; // [rsp+38h] [rbp-48h] BYREF
  struct Windows::Security::Authentication::Web::Core::IWebTokenResponse *v19; // [rsp+40h] [rbp-40h] BYREF
  struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *v20; // [rsp+48h] [rbp-38h] BYREF
  HSTRING string; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  __int64 v23; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v18 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  v23 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
    0x46u,
    0x45u);
  ActivationFactory = RoGetActivationFactory(v23, &GUID_6aca7c92_a581_4479_9c10_752eff44fd34, &v18);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4C,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\accounttokenprovider.cpp",
      (const char *)(unsigned int)ActivationFactory,
      bIgnoreCase);
  v17 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  AccountProvider = AccountTokenProvider::FindAccountProvider(this, v18, &v17);
  if ( AccountProvider < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\accounttokenprovider.cpp",
      (const char *)(unsigned int)AccountProvider,
      bIgnoreCase);
  if ( !v17 )
    goto LABEL_4;
  v20 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  WebTokenRequestResult = AccountTokenProvider::GetWebTokenRequestResult(this, v17, v18, a3, &v20);
  if ( WebTokenRequestResult < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\accounttokenprovider.cpp",
      (const char *)(unsigned int)WebTokenRequestResult,
      bIgnoreCasea);
  v19 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  WebTokenResponse = AccountTokenProvider::GetWebTokenResponse(v10, v20, &v19);
  if ( WebTokenResponse == -2138701812 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
LABEL_4:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
    return 0;
  }
  if ( WebTokenResponse < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\accounttokenprovider.cpp",
      (const char *)(unsigned int)WebTokenResponse,
      bIgnoreCasea);
  string = 0;
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    &string,
    0);
  TenantId = AccountTokenProvider::GetTenantId(this, v19, &string);
  if ( TenantId < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\accounttokenprovider.cpp",
      (const char *)(unsigned int)TenantId,
      bIgnoreCasea);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v14 = CompareStringOrdinal(StringRawBuffer, -1, lpString2, -1, 1) == 2;
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  return v14;
}

```

## disassembly

```asm
0x1800321f0  mov     [rsp-18h+arg_18], rbx
0x1800321f5  push    rbp
0x1800321f6  push    rsi
0x1800321f7  push    rdi
0x1800321f8  mov     rbp, rsp
0x1800321fb  sub     rsp, 80h
0x180032202  mov     rax, cs:__security_cookie
0x180032209  xor     rax, rsp
0x18003220c  mov     [rbp+var_8], rax
0x180032210  mov     rdi, r8
0x180032213  mov     rsi, rdx
0x180032216  mov     rbx, rcx
0x180032219  mov     [rbp+var_48], 0
0x180032221  lea     rcx, [rbp+var_48]
0x180032225  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003222a  mov     [rbp+var_10], 0
0x180032232  mov     r9d, 45h ; 'E'; unsigned int
0x180032238  lea     r8d, [r9+1]; unsigned int
0x18003223c  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x180032243  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180032247  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003224c  nop
0x18003224d  lea     r8, [rbp+var_48]
0x180032251  lea     rdx, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x180032258  mov     rcx, [rbp+var_10]
0x18003225c  call    cs:__imp_RoGetActivationFactory
0x180032262  mov     rcx, [rbp+18h]; this
0x180032266  test    eax, eax
0x180032268  js      loc_1800323FD
0x18003226e  mov     [rbp+var_50], 0
0x180032276  lea     rcx, [rbp+var_50]
0x18003227a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003227f  lea     r8, [rbp+var_50]; struct Windows::Security::Credentials::IWebAccountProvider **
0x180032283  mov     rdx, [rbp+var_48]; struct Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics *
0x180032287  mov     rcx, rbx; this
0x18003228a  call    ?FindAccountProvider@AccountTokenProvider@@AEAAJPEAUIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@PEAPEAUIWebAccountProvider@Credentials@67@@Z; AccountTokenProvider::FindAccountProvider(Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics *,Windows::Security::Credentials::IWebAccountProvider * *)
0x18003228f  mov     rcx, [rbp+18h]; this
0x180032293  test    eax, eax
0x180032295  js      loc_180032412
0x18003229b  cmp     [rbp+var_50], 0
0x1800322a0  jnz     short loc_1800322BC
0x1800322a2  lea     rcx, [rbp+var_50]
0x1800322a6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800322ab  nop
0x1800322ac  lea     rcx, [rbp+var_48]
0x1800322b0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800322b5  xor     al, al
0x1800322b7  jmp     loc_1800323C9
0x1800322bc  mov     [rbp+var_38], 0
0x1800322c4  lea     rcx, [rbp+var_38]
0x1800322c8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800322cd  lea     rax, [rbp+var_38]
0x1800322d1  mov     qword ptr [rsp+80h+bIgnoreCase], rax; int
0x1800322d6  mov     r9, rdi; unsigned __int16 *
0x1800322d9  mov     r8, [rbp+var_48]; struct Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics *
0x1800322dd  mov     rdx, [rbp+var_50]; struct Windows::Security::Credentials::IWebAccountProvider *
0x1800322e1  mov     rcx, rbx; this
0x1800322e4  call    ?GetWebTokenRequestResult@AccountTokenProvider@@AEAAJPEAUIWebAccountProvider@Credentials@Security@Windows@@PEAUIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@45@PEBGPEAPEAUIWebTokenRequestResult@78945@@Z; AccountTokenProvider::GetWebTokenRequestResult(Windows::Security::Credentials::IWebAccountProvider *,Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics *,ushort const *,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult * *)
0x1800322e9  mov     rcx, [rbp+18h]; this
0x1800322ed  test    eax, eax
0x1800322ef  js      loc_180032427
0x1800322f5  mov     [rbp+var_40], 0
0x1800322fd  lea     rcx, [rbp+var_40]
0x180032301  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180032306  lea     r8, [rbp+var_40]; struct Windows::Security::Authentication::Web::Core::IWebTokenResponse **
0x18003230a  mov     rdx, [rbp+var_38]; struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *
0x18003230e  call    ?GetWebTokenResponse@AccountTokenProvider@@AEAAJPEAUIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@PEAPEAUIWebTokenResponse@34567@@Z; AccountTokenProvider::GetWebTokenResponse(Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *,Windows::Security::Authentication::Web::Core::IWebTokenResponse * *)
0x180032313  cmp     eax, 8086000Ch
0x180032318  jnz     short loc_180032332
0x18003231a  lea     rcx, [rbp+var_40]
0x18003231e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180032323  nop
0x180032324  lea     rcx, [rbp+var_38]
0x180032328  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003232d  jmp     loc_1800322A2
0x180032332  mov     rcx, [rbp+18h]; this
0x180032336  test    eax, eax
0x180032338  js      loc_18003243C
0x18003233e  mov     [rbp+string], 0
0x180032346  xor     edx, edx
0x180032348  lea     rcx, [rbp+string]
0x18003234c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180032351  lea     r8, [rbp+string]; HSTRING *
0x180032355  mov     rdx, [rbp+var_40]; struct Windows::Security::Authentication::Web::Core::IWebTokenResponse *
0x180032359  mov     rcx, rbx; this
0x18003235c  call    ?GetTenantId@AccountTokenProvider@@AEAAJPEAUIWebTokenResponse@Core@Web@Authentication@Security@Windows@@PEAPEAUHSTRING__@@@Z; AccountTokenProvider::GetTenantId(Windows::Security::Authentication::Web::Core::IWebTokenResponse *,HSTRING__ * *)
0x180032361  mov     rcx, [rbp+18h]; this
0x180032365  test    eax, eax
0x180032367  js      short loc_1800323E8
0x180032369  xor     edx, edx; length
0x18003236b  mov     rcx, [rbp+string]; string
0x18003236f  call    cs:__imp_WindowsGetStringRawBuffer
0x180032375  mov     rcx, rax; lpString1
0x180032378  mov     [rsp+80h+bIgnoreCase], 1; bIgnoreCase
0x180032380  or      edx, 0FFFFFFFFh; cchCount1
0x180032383  mov     r9d, edx; cchCount2
0x180032386  mov     r8, rsi; lpString2
0x180032389  call    cs:__imp_CompareStringOrdinal
0x18003238f  nop
0x180032390  cmp     eax, 2
0x180032393  setz    bl
0x180032396  lea     rcx, [rbp+string]
0x18003239a  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18003239f  nop
0x1800323a0  lea     rcx, [rbp+var_40]
0x1800323a4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800323a9  nop
0x1800323aa  lea     rcx, [rbp+var_38]
0x1800323ae  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800323b3  nop
0x1800323b4  lea     rcx, [rbp+var_50]
0x1800323b8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800323bd  nop
0x1800323be  lea     rcx, [rbp+var_48]
0x1800323c2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800323c7  mov     al, bl
0x1800323c9  mov     rcx, [rbp+var_8]
0x1800323cd  xor     rcx, rsp; StackCookie
0x1800323d0  call    __security_check_cookie
0x1800323d5  mov     rbx, [rsp+80h+arg_18]
0x1800323dd  add     rsp, 80h
0x1800323e4  pop     rdi
0x1800323e5  pop     rsi
0x1800323e6  pop     rbp
0x1800323e7  retn
0x1800323e8  mov     r9d, eax; char *
0x1800323eb  lea     r8, aOnecoreBaseFli_29; "onecore\\base\\flighting\\onesettings\\"...
0x1800323f2  mov     edx, 31h ; '1'; void *
0x1800323f7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800323fd  mov     r9d, eax; char *
0x180032400  lea     r8, aOnecoreBaseFli_29; "onecore\\base\\flighting\\onesettings\\"...
0x180032407  mov     edx, 4Ch ; 'L'; void *
0x18003240c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032412  mov     r9d, eax; char *
0x180032415  lea     r8, aOnecoreBaseFli_29; "onecore\\base\\flighting\\onesettings\\"...
0x18003241c  mov     edx, 1Dh; void *
0x180032421  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032427  mov     r9d, eax; char *
0x18003242a  lea     r8, aOnecoreBaseFli_29; "onecore\\base\\flighting\\onesettings\\"...
0x180032431  mov     edx, 24h ; '$'; void *
0x180032436  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003243c  mov     r9d, eax; char *
0x18003243f  lea     r8, aOnecoreBaseFli_29; "onecore\\base\\flighting\\onesettings\\"...
0x180032446  mov     edx, 2Eh ; '.'; void *
0x18003244b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
