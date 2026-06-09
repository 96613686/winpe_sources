# AuthorizationProvider::GetDefaultAADUserTicket(ushort const *)

- ea: `0x180030600`
- end: `0x180030db7`
- name: `?GetDefaultAADUserTicket@AuthorizationProvider@@UEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z`
- size: `1975`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003110`
- `0x180005f50`
- `0x180006b9c`
- `0x18000b0bc`
- `0x1800101fc`
- `0x180011b20`
- `0x18002efe8`
- `0x18002f01c`
- `0x18002f238`
- `0x18002ff98`
- `0x1800301c0`
- `0x180030600`
- `0x18003128c`
- `0x180031430`
- `0x18004ee7c`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003067e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003067e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003075f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180030841`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003075f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180030841`

## string_xrefs

- `0x180030855`: `Windows.Security.Authentication.Web.Core.WebTokenRequest`
- `0x180030816`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`
- `0x180030731`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
HSTRING *__fastcall AuthorizationProvider::GetDefaultAADUserTicket(
        AuthorizationProvider *a1,
        HSTRING *a2,
        const WCHAR *a3)
{
  bool v4; // r15
  HRESULT v5; // eax
  int v6; // eax
  int v7; // eax
  __int64 v8; // rbx
  int ActivationFactory; // eax
  __int64 v10; // rsi
  __int64 (__fastcall *v11)(__int64, PVOID, PVOID, __int64 *); // rdi
  PVOID Reserved1; // rbx
  HSTRING_HEADER *v13; // rax
  int v14; // eax
  __int64 v15; // rbx
  int v16; // eax
  __int64 v17; // rbx
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, __int64, _QWORD, _QWORD); // rbx
  int v21; // eax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, _QWORD, __int64 *); // rbx
  int v24; // eax
  int v25; // eax
  AuthorizationProvider *v26; // rcx
  int PrimaryAccount; // eax
  __int64 v28; // rsi
  __int64 (__fastcall *v29)(__int64, __int64, __int64, PVOID); // rdi
  PVOID v30; // rbx
  int v31; // eax
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, __int64 *); // rbx
  int v34; // eax
  __int64 v35; // rsi
  __int64 (__fastcall *v36)(__int64, __int64, PVOID, char *); // rdi
  PVOID v37; // rbx
  int v38; // eax
  __int64 v39; // rsi
  __int64 (__fastcall *v40)(__int64, __int64, PVOID, char *); // rdi
  PVOID v41; // rbx
  int v42; // eax
  __int64 v43; // rdi
  __int64 (__fastcall *v44)(__int64, __int64, struct Windows::Security::Credentials::IWebAccount *, __int64 *); // rbx
  int v45; // eax
  int v46; // eax
  AuthorizationProvider *v47; // rcx
  int TicketFromTokenResult; // eax
  int *ppv; // [rsp+20h] [rbp-E0h]
  char v51; // [rsp+40h] [rbp-C0h] BYREF
  char v52; // [rsp+41h] [rbp-BFh] BYREF
  _BYTE v53[6]; // [rsp+42h] [rbp-BEh] BYREF
  __int64 v54; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v55; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v56; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v57; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v58; // [rsp+68h] [rbp-98h] BYREF
  __int64 v59; // [rsp+70h] [rbp-90h] BYREF
  int v60[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v61; // [rsp+80h] [rbp-80h] BYREF
  struct Windows::Security::Credentials::IWebAccount *v62; // [rsp+88h] [rbp-78h] BYREF
  __int64 v63; // [rsp+90h] [rbp-70h] BYREF
  __int64 v64; // [rsp+98h] [rbp-68h] BYREF
  struct Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics *v65; // [rsp+A0h] [rbp-60h] BYREF
  int v66; // [rsp+A8h] [rbp-58h]
  __int64 v67; // [rsp+B0h] [rbp-50h] BYREF
  struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *v68; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v69; // [rsp+C0h] [rbp-40h] BYREF
  const WCHAR *v70; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v71[3]; // [rsp+D0h] [rbp-30h] BYREF
  char v72; // [rsp+E8h] [rbp-18h]
  HSTRING *v73; // [rsp+F0h] [rbp-10h]
  HSTRING_HEADER hstringHeader; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v75; // [rsp+110h] [rbp+10h]
  HSTRING_HEADER v76; // [rsp+118h] [rbp+18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v73 = a2;
  v70 = a3;
  v66 = 0;
  v53[0] = 0;
  v4 = AuthorizationProvider::ImpersonateUserIfLocalSystem(a1, (struct UstCommon::CImpersonator *)v53);
  v56 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
  v5 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &v56);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)(unsigned int)v5,
      (int)ppv);
  v67 = 0;
  v6 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v56 + 32LL))(v56, 5, &v67);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)(unsigned int)v6,
      (int)ppv);
  if ( v67 == 1 )
  {
    v51 = 0;
  }
  else
  {
    v51 = 1;
    v7 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v56 + 24LL))(v56, 5, 1);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5C,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
        (const char *)(unsigned int)v7,
        (int)ppv);
  }
  v71[0] = &v56;
  v71[1] = &v51;
  v71[2] = &v67;
  v72 = 1;
  v55 = 0;
  v54 = 0;
  v65 = 0;
  v64 = 0;
  v75 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
    0x46u,
    0x45u);
  v8 = v75;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
  ActivationFactory = RoGetActivationFactory(v8, &GUID_6aca7c92_a581_4479_9c10_752eff44fd34, &v55);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)ppv);
  v63 = 0;
  v10 = v55;
  v11 = *(__int64 (__fastcall **)(__int64, PVOID, PVOID, __int64 *))(*(_QWORD *)v55 + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
  Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                &hstringHeader,
                (const WCHAR **)&AuthorizationProvider::c_AadAuthority)[1].Reserved.Reserved1;
  v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
          &v76,
          (const WCHAR **)&AuthorizationProvider::c_MicrosoftProvider);
  v14 = v11(v10, v13[1].Reserved.Reserved1, Reserved1, &v63);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)(unsigned int)v14,
      (int)ppv);
  v15 = v63;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v54);
  v16 = BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>,Windows::Security::Credentials::IWebAccountProvider *>(
          v15,
          (__int64)&v54);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)(unsigned int)v16,
      (int)ppv);
  if ( !v54 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6A,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)0x80070490LL,
      (int)ppv);
  v75 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
    0x41u,
    0x40u);
  v17 = v75;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v65);
  RoGetActivationFactory(v17, &GUID_07650a66_66ea_489d_aa90_0dabc75f3567, &v65);
  v75 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.Authentication.Web.Core.WebTokenRequest",
    0x39u,
    0x38u);
  v18 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>>(
          v75,
          (__int64)&v64);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)(unsigned int)v18,
      (int)ppv);
  if ( v4 )
  {
    *(_QWORD *)v60 = 0;
    v19 = v64;
    v20 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v64 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v60);
    ppv = v60;
    v21 = v20(v19, v54, 0, 0);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x78,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
        (const char *)(unsigned int)v21,
        (int)v60);
    v59 = 0;
    v22 = v55;
    v23 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v55 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
    v24 = v23(v22, *(_QWORD *)v60, &v59);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7B,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
        (const char *)(unsigned int)v24,
        (int)v60);
    v69 = 0;
    v25 = BlockOnCompletionAndGetResults<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult>(
            v59,
            (__int64)&v69);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7E,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
        (const char *)(unsigned int)v25,
        (int)v60);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v69);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v60);
  }
  v62 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
  PrimaryAccount = AuthorizationProvider::GetPrimaryAccount(v26, v65, &v62);
  if ( PrimaryAccount < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x82,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)(unsigned int)PrimaryAccount,
      (int)ppv);
  v58 = 0;
  v28 = v64;
  v29 = *(__int64 (__fastcall **)(__int64, __int64, __int64, PVOID))(*(_QWORD *)v64 + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
  v30 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
          &v76,
          (const WCHAR **)&AuthorizationProvider::c_FlightingAadAppId)[1].Reserved.Reserved1;
  v75 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, &String1, 1u, 0);
  v31 = v29(v28, v54, v75, v30);
  if ( v31 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)(unsigned int)v31,
      0);
  v57 = 0;
  v32 = v58;
  v33 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v58 + 80LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
  v34 = v33(v32, &v57);
  if ( v34 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8A,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)(unsigned int)v34,
      0);
  v52 = 0;
  v35 = v57;
  v36 = *(__int64 (__fastcall **)(__int64, __int64, PVOID, char *))(*(_QWORD *)v57 + 80LL);
  v37 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
          &v76,
          (const WCHAR **)&AuthorizationProvider::c_AadAuthority)[1].Reserved.Reserved1;
  v75 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"authority", 0xAu, 9u);
  v38 = v36(v35, v75, v37, &v52);
  if ( v38 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)(unsigned int)v38,
      0);
  v39 = v57;
  v40 = *(__int64 (__fastcall **)(__int64, __int64, PVOID, char *))(*(_QWORD *)v57 + 80LL);
  v41 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v76, &v70)[1].Reserved.Reserved1;
  v75 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"resource", 9u, 8u);
  v42 = v40(v39, v75, v41, &v52);
  if ( v42 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8F,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)(unsigned int)v42,
      0);
  v61 = 0;
  v43 = v55;
  v44 = *(__int64 (__fastcall **)(__int64, __int64, struct Windows::Security::Credentials::IWebAccount *, __int64 *))(*(_QWORD *)v55 + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
  v45 = v44(v43, v58, v62, &v61);
  if ( v45 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)(unsigned int)v45,
      0);
  v68 = 0;
  v46 = BlockOnCompletionAndGetResults<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult>(
          v61,
          (__int64)&v68);
  if ( v46 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x95,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)(unsigned int)v46,
      0);
  *a2 = 0;
  v66 = 1;
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    a2,
    0);
  TicketFromTokenResult = AuthorizationProvider::ExtractTicketFromTokenResult(v47, v68, a2);
  if ( TicketFromTokenResult < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x99,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)(unsigned int)TicketFromTokenResult,
      0);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v65);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v54);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
  v72 = 0;
  lambda_e1c0100e0d85763bd660b2e821726c9d_::operator()(v71);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
  UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)v53);
  return a2;
}

```

## disassembly

```asm
0x180030600  mov     [rsp-8+arg_0], rbx
0x180030605  mov     [rsp-8+arg_18], rsi
0x18003060a  push    rbp
0x18003060b  push    rdi
0x18003060c  push    r12
0x18003060e  push    r14
0x180030610  push    r15
0x180030612  lea     rbp, [rsp-40h]
0x180030617  sub     rsp, 140h
0x18003061e  mov     rax, cs:__security_cookie
0x180030625  xor     rax, rsp
0x180030628  mov     [rbp+60h+var_28], rax
0x18003062c  mov     r14, rdx
0x18003062f  mov     [rbp+60h+var_70], rdx
0x180030633  mov     [rbp+60h+var_98], r8
0x180030637  xor     r12d, r12d
0x18003063a  mov     [rbp+60h+var_B8], r12d
0x18003063e  mov     [rsp+160h+var_11E], r12b
0x180030643  lea     rdx, [rsp+160h+var_11E]; struct UstCommon::CImpersonator *
0x180030648  call    ?ImpersonateUserIfLocalSystem@AuthorizationProvider@@AEAA_NPEAVCImpersonator@UstCommon@@@Z; AuthorizationProvider::ImpersonateUserIfLocalSystem(UstCommon::CImpersonator *)
0x18003064d  mov     r15b, al
0x180030650  mov     [rsp+160h+var_108], r12
0x180030655  lea     rcx, [rsp+160h+var_108]
0x18003065a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003065f  lea     rax, [rsp+160h+var_108]
0x180030664  mov     [rsp+160h+ppv], rax; int
0x180030669  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x180030670  xor     edx, edx; pUnkOuter
0x180030672  lea     r8d, [r12+1]; dwClsContext
0x180030677  lea     rcx, CLSID_GlobalOptions; rclsid
0x18003067e  call    cs:__imp_CoCreateInstance
0x180030684  mov     rcx, [rbp+68h]; this
0x180030688  test    eax, eax
0x18003068a  js      loc_180030C4F
0x180030690  mov     [rbp+60h+var_B0], r12
0x180030694  mov     rcx, [rsp+160h+var_108]
0x180030699  mov     rax, [rcx]
0x18003069c  lea     r8, [rbp+60h+var_B0]
0x1800306a0  lea     ebx, [r12+5]
0x1800306a5  mov     edx, ebx
0x1800306a7  mov     rax, [rax+20h]
0x1800306ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800306b0  mov     rcx, [rbp+68h]; this
0x1800306b4  test    eax, eax
0x1800306b6  js      loc_180030C64
0x1800306bc  cmp     [rbp+60h+var_B0], 1
0x1800306c1  jz      short loc_1800306EE
0x1800306c3  mov     [rsp+160h+var_120], 1
0x1800306c8  mov     rcx, [rsp+160h+var_108]
0x1800306cd  mov     rax, [rcx]
0x1800306d0  lea     r8d, [r12+1]
0x1800306d5  mov     edx, ebx
0x1800306d7  mov     rax, [rax+18h]
0x1800306db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800306e0  mov     rcx, [rbp+68h]; this
0x1800306e4  test    eax, eax
0x1800306e6  js      loc_180030C3A
0x1800306ec  jmp     short loc_1800306F3
0x1800306ee  mov     [rsp+160h+var_120], r12b
0x1800306f3  lea     rax, [rsp+160h+var_108]
0x1800306f8  mov     [rbp+60h+var_90], rax
0x1800306fc  lea     rax, [rsp+160h+var_120]
0x180030701  mov     [rbp+60h+var_88], rax
0x180030705  lea     rax, [rbp+60h+var_B0]
0x180030709  mov     [rbp+60h+var_80], rax
0x18003070d  mov     [rbp+60h+var_78], 1
0x180030711  mov     [rsp+160h+var_110], r12
0x180030716  mov     [rsp+160h+var_118], r12
0x18003071b  mov     [rbp+60h+var_C0], r12
0x18003071f  mov     [rbp+60h+var_C8], r12
0x180030723  mov     [rbp+60h+var_50], r12
0x180030727  mov     r9d, 45h ; 'E'; unsigned int
0x18003072d  lea     r8d, [r9+1]; unsigned int
0x180030731  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x180030738  lea     rcx, [rbp+60h+hstringHeader]; hstringHeader
0x18003073c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180030741  nop
0x180030742  mov     rbx, [rbp+60h+var_50]
0x180030746  lea     rcx, [rsp+160h+var_110]
0x18003074b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180030750  lea     r8, [rsp+160h+var_110]
0x180030755  lea     rdx, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x18003075c  mov     rcx, rbx
0x18003075f  call    cs:__imp_RoGetActivationFactory
0x180030765  mov     rcx, [rbp+68h]; this
0x180030769  test    eax, eax
0x18003076b  js      loc_180030C79
0x180030771  mov     [rbp+60h+var_D0], r12
0x180030775  mov     rsi, [rsp+160h+var_110]
0x18003077a  mov     rax, [rsi]
0x18003077d  mov     rdi, [rax+60h]
0x180030781  lea     rcx, [rbp+60h+var_D0]
0x180030785  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003078a  lea     rdx, ?c_AadAuthority@AuthorizationProvider@@0QEBGEB; ushort const * const AuthorizationProvider::c_AadAuthority
0x180030791  lea     rcx, [rbp+60h+hstringHeader]
0x180030795  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003079a  nop
0x18003079b  mov     rbx, [rax+18h]
0x18003079f  lea     rdx, ?c_MicrosoftProvider@AuthorizationProvider@@0QEBGEB; ushort const * const AuthorizationProvider::c_MicrosoftProvider
0x1800307a6  lea     rcx, [rbp+60h+var_48]
0x1800307aa  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800307af  nop
0x1800307b0  lea     r9, [rbp+60h+var_D0]
0x1800307b4  mov     r8, rbx
0x1800307b7  mov     rdx, [rax+18h]
0x1800307bb  mov     rcx, rsi
0x1800307be  mov     rax, rdi
0x1800307c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307c6  mov     rcx, [rbp+68h]; this
0x1800307ca  test    eax, eax
0x1800307cc  js      loc_180030C8E
0x1800307d2  mov     rbx, [rbp+60h+var_D0]
0x1800307d6  lea     rcx, [rsp+160h+var_118]
0x1800307db  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800307e0  lea     rdx, [rsp+160h+var_118]
0x1800307e5  mov     rcx, rbx
0x1800307e8  call    ??$BlockOnCompletionAndGetResults@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@PEAUIWebAccountProvider@Credentials@Security@3@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@PEAPEAUIWebAccountProvider@Credentials@Security@2@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>,Windows::Security::Credentials::IWebAccountProvider *>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,Windows::Security::Credentials::IWebAccountProvider * *,tagCOWAIT_FLAGS,void *)
0x1800307ed  mov     rcx, [rbp+68h]; this
0x1800307f1  test    eax, eax
0x1800307f3  js      loc_180030CA3
0x1800307f9  mov     rcx, [rbp+68h]; this
0x1800307fd  cmp     [rsp+160h+var_118], r12
0x180030802  jz      loc_180030CB8
0x180030808  mov     [rbp+60h+var_50], r12
0x18003080c  mov     r9d, 40h ; '@'; unsigned int
0x180030812  lea     r8d, [r9+1]; unsigned int
0x180030816  lea     rdx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x18003081d  lea     rcx, [rbp+60h+hstringHeader]; hstringHeader
0x180030821  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180030826  mov     rbx, [rbp+60h+var_50]
0x18003082a  lea     rcx, [rbp+60h+var_C0]
0x18003082e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180030833  lea     r8, [rbp+60h+var_C0]
0x180030837  lea     rdx, _GUID_07650a66_66ea_489d_aa90_0dabc75f3567
0x18003083e  mov     rcx, rbx
0x180030841  call    cs:__imp_RoGetActivationFactory
0x180030847  mov     [rbp+60h+var_50], r12
0x18003084b  mov     r9d, 38h ; '8'; unsigned int
0x180030851  lea     r8d, [r9+1]; unsigned int
0x180030855  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebTokenRequest@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x18003085c  lea     rcx, [rbp+60h+hstringHeader]; hstringHeader
0x180030860  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180030865  nop
0x180030866  lea     rdx, [rbp+60h+var_C8]
0x18003086a  mov     rcx, [rbp+60h+var_50]
0x18003086e  call    ??$GetActivationFactory@V?$ComPtr@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>>)
0x180030873  mov     rcx, [rbp+68h]; this
0x180030877  test    eax, eax
0x180030879  js      loc_180030CD0
0x18003087f  test    r15b, r15b
0x180030882  jz      loc_180030947
0x180030888  mov     qword ptr [rsp+160h+var_E8], r12
0x18003088d  mov     rdi, [rbp+60h+var_C8]
0x180030891  mov     rax, [rdi]
0x180030894  mov     rbx, [rax+30h]
0x180030898  lea     rcx, [rsp+160h+var_E8]
0x18003089d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800308a2  lea     rax, [rsp+160h+var_E8]
0x1800308a7  mov     [rsp+160h+ppv], rax; int
0x1800308ac  xor     r9d, r9d
0x1800308af  xor     r8d, r8d
0x1800308b2  mov     rdx, [rsp+160h+var_118]
0x1800308b7  mov     rcx, rdi
0x1800308ba  mov     rax, rbx
0x1800308bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800308c2  mov     rcx, [rbp+68h]; this
0x1800308c6  test    eax, eax
0x1800308c8  js      loc_180030CE5
0x1800308ce  mov     [rsp+160h+var_F0], r12
0x1800308d3  mov     rdi, [rsp+160h+var_110]
0x1800308d8  mov     rax, [rdi]
0x1800308db  mov     rbx, [rax+30h]
0x1800308df  lea     rcx, [rsp+160h+var_F0]
0x1800308e4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800308e9  lea     r8, [rsp+160h+var_F0]
0x1800308ee  mov     rdx, qword ptr [rsp+160h+var_E8]
0x1800308f3  mov     rcx, rdi
0x1800308f6  mov     rax, rbx
0x1800308f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800308fe  mov     rcx, [rbp+68h]; this
0x180030902  test    eax, eax
0x180030904  js      loc_180030CFA
0x18003090a  mov     [rbp+60h+var_A0], r12
0x18003090e  lea     rdx, [rbp+60h+var_A0]
0x180030912  mov     rcx, [rsp+160h+var_F0]
0x180030917  call    ??$BlockOnCompletionAndGetResults@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@UIWebTokenRequestResult@23456@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestResult>>,tagCOWAIT_FLAGS,void *)
0x18003091c  mov     rcx, [rbp+68h]; this
0x180030920  test    eax, eax
0x180030922  js      loc_180030D0F
0x180030928  lea     rcx, [rbp+60h+var_A0]
0x18003092c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180030931  nop
0x180030932  lea     rcx, [rsp+160h+var_F0]
0x180030937  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003093c  nop
0x18003093d  lea     rcx, [rsp+160h+var_E8]
0x180030942  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180030947  mov     [rbp+60h+var_D8], r12
0x18003094b  lea     rcx, [rbp+60h+var_D8]
0x18003094f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180030954  lea     r8, [rbp+60h+var_D8]; struct Windows::Security::Credentials::IWebAccount **
0x180030958  mov     rdx, [rbp+60h+var_C0]; struct Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics *
0x18003095c  call    ?GetPrimaryAccount@AuthorizationProvider@@AEAAJQEAUITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@PEAPEAUIWebAccount@Credentials@57@@Z; AuthorizationProvider::GetPrimaryAccount(Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics * const,Windows::Security::Credentials::IWebAccount * *)
0x180030961  mov     rcx, [rbp+68h]; this
0x180030965  test    eax, eax
0x180030967  js      loc_180030D24
0x18003096d  mov     [rsp+160h+var_F8], r12
0x180030972  mov     rsi, [rbp+60h+var_C8]
0x180030976  mov     rax, [rsi]
0x180030979  mov     rdi, [rax+38h]
0x18003097d  lea     rcx, [rsp+160h+var_F8]
0x180030982  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180030987  lea     rdx, ?c_FlightingAadAppId@AuthorizationProvider@@0QEBGEB; ushort const * const AuthorizationProvider::c_FlightingAadAppId
0x18003098e  lea     rcx, [rbp+60h+var_48]
0x180030992  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180030997  nop
0x180030998  mov     rbx, [rax+18h]
0x18003099c  mov     [rbp+60h+var_50], r12
0x1800309a0  xor     r9d, r9d; unsigned int
0x1800309a3  lea     r8d, [r9+1]; unsigned int
0x1800309a7  lea     rdx, String1; sourceString
0x1800309ae  lea     rcx, [rbp+60h+hstringHeader]; hstringHeader
0x1800309b2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800309b7  nop
0x1800309b8  lea     rax, [rsp+160h+var_F8]
0x1800309bd  mov     [rsp+160h+var_138], rax
0x1800309c2  mov     dword ptr [rsp+160h+ppv], r12d; int
0x1800309c7  mov     r9, rbx
0x1800309ca  mov     r8, [rbp+60h+var_50]
0x1800309ce  mov     rdx, [rsp+160h+var_118]
0x1800309d3  mov     rcx, rsi
0x1800309d6  mov     rax, rdi
0x1800309d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309de  mov     rcx, [rbp+68h]; this
0x1800309e2  test    eax, eax
0x1800309e4  js      loc_180030D39
0x1800309ea  mov     [rsp+160h+var_100], r12
0x1800309ef  mov     rdi, [rsp+160h+var_F8]
0x1800309f4  mov     rax, [rdi]
0x1800309f7  mov     rbx, [rax+50h]
0x1800309fb  lea     rcx, [rsp+160h+var_100]
0x180030a00  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180030a05  lea     rdx, [rsp+160h+var_100]
0x180030a0a  mov     rcx, rdi
0x180030a0d  mov     rax, rbx
0x180030a10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a15  mov     rcx, [rbp+68h]; this
0x180030a19  test    eax, eax
0x180030a1b  js      loc_180030D4E
0x180030a21  mov     [rsp+160h+var_11F], r12b
0x180030a26  mov     rsi, [rsp+160h+var_100]
0x180030a2b  mov     rax, [rsi]
0x180030a2e  mov     rdi, [rax+50h]
0x180030a32  lea     rdx, ?c_AadAuthority@AuthorizationProvider@@0QEBGEB; ushort const * const AuthorizationProvider::c_AadAuthority
0x180030a39  lea     rcx, [rbp+60h+var_48]
0x180030a3d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180030a42  nop
0x180030a43  mov     rbx, [rax+18h]
0x180030a47  mov     [rbp+60h+var_50], r12
0x180030a4b  mov     r15d, 9
0x180030a51  mov     r9d, r15d; unsigned int
0x180030a54  lea     r8d, [r15+1]; unsigned int
0x180030a58  lea     rdx, aAuthority; "authority"
0x180030a5f  lea     rcx, [rbp+60h+hstringHeader]; hstringHeader
0x180030a63  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180030a68  nop
0x180030a69  lea     r9, [rsp+160h+var_11F]
0x180030a6e  mov     r8, rbx
0x180030a71  mov     rdx, [rbp+60h+var_50]
0x180030a75  mov     rcx, rsi
0x180030a78  mov     rax, rdi
0x180030a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a80  mov     rcx, [rbp+68h]; this
0x180030a84  test    eax, eax
0x180030a86  js      loc_180030D63
0x180030a8c  mov     rsi, [rsp+160h+var_100]
0x180030a91  mov     rax, [rsi]
0x180030a94  mov     rdi, [rax+50h]
0x180030a98  lea     rdx, [rbp+60h+var_98]
0x180030a9c  lea     rcx, [rbp+60h+var_48]
0x180030aa0  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180030aa5  nop
0x180030aa6  mov     rbx, [rax+18h]
0x180030aaa  mov     [rbp+60h+var_50], r12
0x180030aae  lea     r9d, [r15-1]; unsigned int
0x180030ab2  mov     r8d, r15d; unsigned int
0x180030ab5  lea     rdx, aResource; "resource"
0x180030abc  lea     rcx, [rbp+60h+hstringHeader]; hstringHeader
0x180030ac0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180030ac5  nop
0x180030ac6  lea     r9, [rsp+160h+var_11F]
0x180030acb  mov     r8, rbx
0x180030ace  mov     rdx, [rbp+60h+var_50]
0x180030ad2  mov     rcx, rsi
0x180030ad5  mov     rax, rdi
0x180030ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030add  mov     rcx, [rbp+68h]; this
0x180030ae1  test    eax, eax
0x180030ae3  js      loc_180030D78
0x180030ae9  mov     [rbp+60h+var_E0], r12
  ... truncated ...
```
