# AuthorizationProvider::GetMSADeviceTicket(ushort const *)

- ea: `0x180030dc0`
- end: `0x180031285`
- name: `?GetMSADeviceTicket@AuthorizationProvider@@UEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z`
- size: `1221`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003110`
- `0x18000564b`
- `0x180006b9c`
- `0x180009fcc`
- `0x18000b0bc`
- `0x1800101fc`
- `0x180011b20`
- `0x18002f094`
- `0x18002f904`
- `0x18002fdc0`
- `0x180030dc0`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180030fd9`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180030fd9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180030e29`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180030e29`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180030f49`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180030f49`

## string_xrefs

- `0x180030f27`: `Windows.Internal.Security.WebAuthentication.AuthenticationManager`
- `0x180030e09`: `Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
_QWORD *__fastcall AuthorizationProvider::GetMSADeviceTicket(
        __int64 a1,
        _QWORD *a2,
        __int64 (__fastcall ***a3)(_QWORD, GUID *, _QWORD *))
{
  int ActivationFactory; // eax
  __int64 v5; // rsi
  __int64 (__fastcall *v6)(__int64, PVOID, PVOID, __int64 *); // rdi
  PVOID Reserved1; // rbx
  HSTRING_HEADER *v8; // rax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // ebx
  HRESULT v13; // eax
  int v14; // eax
  PVOID v15; // rdi
  __int64 (__fastcall *v16)(PVOID, _QWORD, _QWORD); // rbx
  _QWORD *v17; // rax
  int v18; // eax
  int (__fastcall ***v19)(_QWORD, GUID *, __int64 *); // rbx
  HRESULT v20; // edx
  __int64 v21; // r8
  int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rax
  int v26; // eax
  int v27; // eax
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, _QWORD *); // rbx
  int v30; // eax
  int v32; // [rsp+20h] [rbp-99h]
  PVOID v33; // [rsp+30h] [rbp-89h] BYREF
  __int64 (__fastcall ***v34)(_QWORD, GUID *, _QWORD *); // [rsp+38h] [rbp-81h] BYREF
  char *v35; // [rsp+40h] [rbp-79h] BYREF
  __int64 v36; // [rsp+48h] [rbp-71h] BYREF
  __int64 *v37; // [rsp+50h] [rbp-69h] BYREF
  int (__fastcall ***v38)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-61h] BYREF
  __int64 v39; // [rsp+60h] [rbp-59h] BYREF
  int v40; // [rsp+68h] [rbp-51h]
  __int64 *v41; // [rsp+70h] [rbp-49h] BYREF
  __int64 v42[3]; // [rsp+78h] [rbp-41h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-29h] BYREF
  __int64 v44; // [rsp+A8h] [rbp-11h]
  GUID pclsid; // [rsp+B0h] [rbp-9h] BYREF
  HSTRING_HEADER v46; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v47; // [rsp+D8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v42[1] = (__int64)a2;
  v34 = a3;
  v40 = 0;
  v42[0] = 0;
  v44 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest",
    0x46u,
    0x45u);
  ActivationFactory = RoGetActivationFactory(v44, &GUID_bebb0a08_9e73_4077_9614_08614c0bc245, v42);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA3,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v32);
  v39 = 0;
  v5 = v42[0];
  v6 = *(__int64 (__fastcall **)(__int64, PVOID, PVOID, __int64 *))(*(_QWORD *)v42[0] + 48LL);
  v39 = 0;
  Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                &v46,
                (const WCHAR **)&AuthorizationProvider::c_AuthPolicy)[1].Reserved.Reserved1;
  v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)&v34);
  v9 = v6(v5, v8[1].Reserved.Reserved1, Reserved1, &v39);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA9,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)(unsigned int)v9,
      v32);
  v34 = 0;
  v10 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest,Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>>(
          (__int64)retaddr,
          &v34);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAC,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)(unsigned int)v10,
      v32);
  v11 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *), __int64))(*v34)[13])(v34, v39);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAD,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)(unsigned int)v11,
      v32);
  v47 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v46,
    L"Windows.Internal.Security.WebAuthentication.AuthenticationManager",
    0x42u,
    0x41u);
  v33 = 0;
  hstringHeader.Reserved.Reserved1 = 0;
  v12 = RoActivateInstance(v47, &hstringHeader);
  if ( v12 >= 0 )
  {
    if ( !memcmp_0(&GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v33 = hstringHeader.Reserved.Reserved1;
    }
    else
    {
      v12 = (**(__int64 (__fastcall ***)(PVOID, GUID *, PVOID *))hstringHeader.Reserved.Reserved1)(
              hstringHeader.Reserved.Reserved1,
              &GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb,
              &v33);
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)hstringHeader.Reserved.Reserved1 + 16LL))(hstringHeader.Reserved.Reserved1);
    }
  }
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB2,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)(unsigned int)v12,
      v32);
  pclsid = 0;
  v13 = CLSIDFromString(L"{0CB4A94A-6E8C-477B-88C8-A3799FC97414}", &pclsid);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB5,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)(unsigned int)v13,
      v32);
  *(GUID *)&hstringHeader.Reserved.Reserved1 = pclsid;
  v14 = (*(__int64 (__fastcall **)(PVOID, HSTRING_HEADER *))(*(_QWORD *)v33 + 72LL))(v33, &hstringHeader);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB6,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)(unsigned int)v14,
      v32);
  v38 = 0;
  v15 = v33;
  v16 = *(__int64 (__fastcall **)(PVOID, _QWORD, _QWORD))(*(_QWORD *)v33 + 64LL);
  v38 = 0;
  v17 = wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::query<Windows::Foundation::Collections::IIterable<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>(
          &v34,
          &hstringHeader);
  v18 = v16(v15, *v17, &v38);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBA,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)(unsigned int)v18,
      v32);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>((__int64 *)&hstringHeader);
  v41 = 0;
  v19 = v38;
  v22 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(
          v38,
          v20,
          v21);
  if ( v22 >= 0 )
    v22 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 **))(*v19)[8])(v19, &v41);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)(unsigned int)v22,
      v32);
  if ( !v41 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBE,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)0x80070490LL,
      v32);
  v37 = 0;
  v23 = *v41;
  v37 = 0;
  v24 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v23 + 48))(v41, &v37);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)(unsigned int)v24,
      v32);
  v36 = 0;
  v25 = *v37;
  v36 = 0;
  v26 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v25 + 48))(v37, 0, &v36);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)(unsigned int)v26,
      v32);
  LODWORD(v35) = 0;
  v27 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v36 + 64LL))(v36, &v35);
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC7,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)(unsigned int)v27,
      v32);
  if ( (int)v35 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)(unsigned int)v35,
      v32);
  *a2 = 0;
  v40 = 1;
  v28 = v36;
  v29 = *(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v36 + 48LL);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    a2,
    0);
  v30 = v29(v28, a2);
  if ( v30 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCB,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)(unsigned int)v30,
      v32);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(&v36);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>((__int64 *)&v37);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>((__int64 *)&v41);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>((__int64 *)&v38);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>((__int64 *)&v33);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>((__int64 *)&v34);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(&v39);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(v42);
  return a2;
}

```

## disassembly

```asm
0x180030dc0  mov     [rsp-8+arg_0], rbx
0x180030dc5  push    rbp
0x180030dc6  push    rsi
0x180030dc7  push    rdi
0x180030dc8  push    r14
0x180030dca  push    r15
0x180030dcc  lea     rbp, [rsp-37h]
0x180030dd1  sub     rsp, 0F0h
0x180030dd8  mov     rax, cs:__security_cookie
0x180030ddf  xor     rax, rsp
0x180030de2  mov     [rbp+57h+var_30], rax
0x180030de6  mov     r14, rdx
0x180030de9  mov     [rbp+57h+var_90], rdx
0x180030ded  mov     [rsp+110h+var_D8], r8
0x180030df2  xor     r15d, r15d
0x180030df5  mov     [rbp+57h+var_A8], r15d
0x180030df9  mov     [rbp+57h+var_98], r15
0x180030dfd  mov     [rbp+57h+var_68], r15
0x180030e01  lea     r9d, [r15+45h]; unsigned int
0x180030e05  lea     r8d, [r15+46h]; unsigned int
0x180030e09  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdServiceTicketRequest@@3QBGB; "Windows.Security.Authentication.OnlineI"...
0x180030e10  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180030e14  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180030e19  nop
0x180030e1a  lea     r8, [rbp+57h+var_98]
0x180030e1e  lea     rdx, _GUID_bebb0a08_9e73_4077_9614_08614c0bc245
0x180030e25  mov     rcx, [rbp+57h+var_68]
0x180030e29  call    cs:__imp_RoGetActivationFactory
0x180030e2f  mov     rcx, [rbp+5Fh]; this
0x180030e33  test    eax, eax
0x180030e35  jns     short loc_180030E4C
0x180030e37  mov     r9d, eax; char *
0x180030e3a  lea     r8, aOnecoreBaseFli_25; "onecore\\base\\flighting\\onesettings\\"...
0x180030e41  mov     edx, 0A3h; void *
0x180030e46  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030e4c  mov     [rbp+57h+var_B0], r15
0x180030e50  mov     rsi, [rbp+57h+var_98]
0x180030e54  mov     rax, [rsi]
0x180030e57  mov     rdi, [rax+30h]
0x180030e5b  mov     [rbp+57h+var_B0], r15
0x180030e5f  lea     rdx, ?c_AuthPolicy@AuthorizationProvider@@0QEBGEB; ushort const * const AuthorizationProvider::c_AuthPolicy
0x180030e66  lea     rcx, [rbp+57h+var_50]
0x180030e6a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180030e6f  nop
0x180030e70  mov     rbx, [rax+18h]
0x180030e74  lea     rdx, [rsp+110h+var_D8]
0x180030e79  lea     rcx, [rbp+57h+hstringHeader]
0x180030e7d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180030e82  nop
0x180030e83  lea     r9, [rbp+57h+var_B0]
0x180030e87  mov     r8, rbx
0x180030e8a  mov     rdx, [rax+18h]
0x180030e8e  mov     rcx, rsi
0x180030e91  mov     rax, rdi
0x180030e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e99  mov     rcx, [rbp+5Fh]; this
0x180030e9d  test    eax, eax
0x180030e9f  jns     short loc_180030EB6
0x180030ea1  mov     r9d, eax; char *
0x180030ea4  lea     r8, aOnecoreBaseFli_25; "onecore\\base\\flighting\\onesettings\\"...
0x180030eab  mov     edx, 0A9h; void *
0x180030eb0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030eb6  mov     [rsp+110h+var_D8], r15
0x180030ebb  lea     rdx, [rsp+110h+var_D8]
0x180030ec0  call    ??$CreateExternalObjectVector@VOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest,Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>> * *)
0x180030ec5  mov     rcx, [rbp+5Fh]; this
0x180030ec9  test    eax, eax
0x180030ecb  jns     short loc_180030EE2
0x180030ecd  mov     r9d, eax; char *
0x180030ed0  lea     r8, aOnecoreBaseFli_25; "onecore\\base\\flighting\\onesettings\\"...
0x180030ed7  mov     edx, 0ACh; void *
0x180030edc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030ee2  mov     rcx, [rsp+110h+var_D8]
0x180030ee7  mov     rax, [rcx]
0x180030eea  mov     rdx, [rbp+57h+var_B0]
0x180030eee  mov     rax, [rax+68h]
0x180030ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ef7  mov     rcx, [rbp+5Fh]; this
0x180030efb  test    eax, eax
0x180030efd  jns     short loc_180030F14
0x180030eff  mov     r9d, eax; char *
0x180030f02  lea     r8, aOnecoreBaseFli_25; "onecore\\base\\flighting\\onesettings\\"...
0x180030f09  mov     edx, 0ADh; void *
0x180030f0e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030f14  mov     [rsp+110h+var_E0], r15
0x180030f19  mov     [rbp+57h+var_38], r15
0x180030f1d  mov     r9d, 41h ; 'A'; unsigned int
0x180030f23  lea     r8d, [r9+1]; unsigned int
0x180030f27  lea     rdx, ?RuntimeClass_Windows_Internal_Security_WebAuthentication_AuthenticationManager@@3QBGB; "Windows.Internal.Security.WebAuthentica"...
0x180030f2e  lea     rcx, [rbp+57h+var_50]; hstringHeader
0x180030f32  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180030f37  nop
0x180030f38  mov     [rsp+110h+var_E0], r15
0x180030f3d  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r15
0x180030f41  lea     rdx, [rbp+57h+hstringHeader]
0x180030f45  mov     rcx, [rbp+57h+var_38]
0x180030f49  call    cs:__imp_RoActivateInstance
0x180030f4f  mov     ebx, eax
0x180030f51  test    eax, eax
0x180030f53  js      short loc_180030FAA
0x180030f55  mov     r8d, 10h; Size
0x180030f5b  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180030f62  lea     rcx, _GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb; Buf1
0x180030f69  call    memcmp_0
0x180030f6e  test    eax, eax
0x180030f70  jnz     short loc_180030F7D
0x180030f72  mov     rax, qword ptr [rbp+57h+hstringHeader.Reserved]
0x180030f76  mov     [rsp+110h+var_E0], rax
0x180030f7b  jmp     short loc_180030FAA
0x180030f7d  mov     rcx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x180030f81  mov     rax, [rcx]
0x180030f84  lea     r8, [rsp+110h+var_E0]
0x180030f89  lea     rdx, _GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb
0x180030f90  mov     rax, [rax]
0x180030f93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f98  mov     ebx, eax
0x180030f9a  mov     rcx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x180030f9e  mov     rax, [rcx]
0x180030fa1  mov     rax, [rax+10h]
0x180030fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030faa  mov     rcx, [rbp+5Fh]; this
0x180030fae  test    ebx, ebx
0x180030fb0  jns     short loc_180030FC7
0x180030fb2  mov     r9d, ebx; char *
0x180030fb5  lea     r8, aOnecoreBaseFli_25; "onecore\\base\\flighting\\onesettings\\"...
0x180030fbc  mov     edx, 0B2h; void *
0x180030fc1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030fc7  xorps   xmm0, xmm0
0x180030fca  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x180030fce  lea     rdx, [rbp+57h+pclsid]; pclsid
0x180030fd2  lea     rcx, sz; "{0CB4A94A-6E8C-477B-88C8-A3799FC97414}"
0x180030fd9  call    cs:__imp_CLSIDFromString
0x180030fdf  mov     rcx, [rbp+5Fh]; this
0x180030fe3  test    eax, eax
0x180030fe5  jns     short loc_180030FFC
0x180030fe7  mov     r9d, eax; char *
0x180030fea  lea     r8, aOnecoreBaseFli_25; "onecore\\base\\flighting\\onesettings\\"...
0x180030ff1  mov     edx, 0B5h; void *
0x180030ff6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030ffc  mov     rcx, [rsp+110h+var_E0]
0x180031001  movaps  xmm0, xmmword ptr [rbp+57h+pclsid.Data1]
0x180031005  movdqa  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x18003100a  mov     rax, [rcx]
0x18003100d  lea     rdx, [rbp+57h+hstringHeader]
0x180031011  mov     rax, [rax+48h]
0x180031015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003101a  mov     rcx, [rbp+5Fh]; this
0x18003101e  test    eax, eax
0x180031020  jns     short loc_180031037
0x180031022  mov     r9d, eax; char *
0x180031025  lea     r8, aOnecoreBaseFli_25; "onecore\\base\\flighting\\onesettings\\"...
0x18003102c  mov     edx, 0B6h; void *
0x180031031  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031037  mov     [rbp+57h+var_B8], r15
0x18003103b  mov     rdi, [rsp+110h+var_E0]
0x180031040  mov     rax, [rdi]
0x180031043  mov     rbx, [rax+40h]
0x180031047  mov     [rbp+57h+var_B8], r15
0x18003104b  lea     rdx, [rbp+57h+hstringHeader]
0x18003104f  lea     rcx, [rsp+110h+var_D8]
0x180031054  call    ??$query@U?$IIterable@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Collections@Foundation@Windows@@@?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@U?$IIterable@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::query<Windows::Foundation::Collections::IIterable<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>(void)
0x180031059  nop
0x18003105a  lea     r8, [rbp+57h+var_B8]
0x18003105e  mov     rdx, [rax]
0x180031061  mov     rcx, rdi
0x180031064  mov     rax, rbx
0x180031067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003106c  mov     rcx, [rbp+5Fh]; this
0x180031070  test    eax, eax
0x180031072  jns     short loc_180031089
0x180031074  mov     r9d, eax; char *
0x180031077  lea     r8, aOnecoreBaseFli_25; "onecore\\base\\flighting\\onesettings\\"...
0x18003107e  mov     edx, 0BAh; void *
0x180031083  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031089  lea     rcx, [rbp+57h+hstringHeader]
0x18003108d  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x180031092  nop
0x180031093  mov     [rbp+57h+var_A0], r15
0x180031097  mov     rbx, [rbp+57h+var_B8]
0x18003109b  mov     rcx, rbx
0x18003109e  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *> *,tagCOWAIT_FLAGS,void *)
0x1800310a3  test    eax, eax
0x1800310a5  js      short loc_1800310BA
0x1800310a7  mov     rax, [rbx]
0x1800310aa  lea     rdx, [rbp+57h+var_A0]
0x1800310ae  mov     rcx, rbx
0x1800310b1  mov     rax, [rax+40h]
0x1800310b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800310ba  mov     rcx, [rbp+5Fh]; this
0x1800310be  test    eax, eax
0x1800310c0  jns     short loc_1800310D7
0x1800310c2  mov     r9d, eax; char *
0x1800310c5  lea     r8, aOnecoreBaseFli_25; "onecore\\base\\flighting\\onesettings\\"...
0x1800310cc  mov     edx, 0BDh; void *
0x1800310d1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800310d7  mov     rax, [rbp+5Fh]
0x1800310db  mov     rcx, [rbp+57h+var_A0]
0x1800310df  test    rcx, rcx
0x1800310e2  jnz     short loc_1800310FF
0x1800310e4  mov     r9d, 80070490h; char *
0x1800310ea  lea     r8, aOnecoreBaseFli_25; "onecore\\base\\flighting\\onesettings\\"...
0x1800310f1  mov     edx, 0BEh; void *
0x1800310f6  mov     rcx, rax; this
0x1800310f9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800310ff  mov     [rbp+57h+var_C0], r15
0x180031103  mov     rax, [rcx]
0x180031106  mov     [rbp+57h+var_C0], r15
0x18003110a  lea     rdx, [rbp+57h+var_C0]
0x18003110e  mov     rax, [rax+30h]
0x180031112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031117  mov     rcx, [rbp+5Fh]; this
0x18003111b  test    eax, eax
0x18003111d  jns     short loc_180031134
0x18003111f  mov     r9d, eax; char *
0x180031122  lea     r8, aOnecoreBaseFli_25; "onecore\\base\\flighting\\onesettings\\"...
0x180031129  mov     edx, 0C1h; void *
0x18003112e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031134  mov     [rbp+57h+var_C8], r15
0x180031138  mov     rcx, [rbp+57h+var_C0]
0x18003113c  mov     rax, [rcx]
0x18003113f  mov     [rbp+57h+var_C8], r15
0x180031143  lea     r8, [rbp+57h+var_C8]
0x180031147  xor     edx, edx
0x180031149  mov     rax, [rax+30h]
0x18003114d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031152  mov     rcx, [rbp+5Fh]; this
0x180031156  test    eax, eax
0x180031158  jns     short loc_18003116F
0x18003115a  mov     r9d, eax; char *
0x18003115d  lea     r8, aOnecoreBaseFli_25; "onecore\\base\\flighting\\onesettings\\"...
0x180031164  mov     edx, 0C4h; void *
0x180031169  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003116f  mov     dword ptr [rbp+57h+var_D0], r15d
0x180031173  mov     rcx, [rbp+57h+var_C8]
0x180031177  mov     rax, [rcx]
0x18003117a  lea     rdx, [rbp+57h+var_D0]
0x18003117e  mov     rax, [rax+40h]
0x180031182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031187  mov     rcx, [rbp+5Fh]; this
0x18003118b  test    eax, eax
0x18003118d  jns     short loc_1800311A4
0x18003118f  mov     r9d, eax; char *
0x180031192  lea     r8, aOnecoreBaseFli_25; "onecore\\base\\flighting\\onesettings\\"...
0x180031199  mov     edx, 0C7h; void *
0x18003119e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800311a4  mov     r9d, dword ptr [rbp+57h+var_D0]; char *
0x1800311a8  mov     rcx, [rbp+5Fh]; this
0x1800311ac  test    r9d, r9d
0x1800311af  jns     short loc_1800311C3
0x1800311b1  lea     r8, aOnecoreBaseFli_25; "onecore\\base\\flighting\\onesettings\\"...
0x1800311b8  mov     edx, 0C8h; void *
0x1800311bd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800311c3  mov     [r14], r15
0x1800311c6  mov     [rbp+57h+var_A8], 1
0x1800311cd  mov     rdi, [rbp+57h+var_C8]
0x1800311d1  mov     rax, [rdi]
0x1800311d4  mov     rbx, [rax+30h]
0x1800311d8  xor     edx, edx
0x1800311da  mov     rcx, r14
0x1800311dd  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800311e2  mov     rdx, r14
0x1800311e5  mov     rcx, rdi
0x1800311e8  mov     rax, rbx
0x1800311eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800311f0  mov     rcx, [rbp+5Fh]; this
0x1800311f4  test    eax, eax
0x1800311f6  jns     short loc_18003120D
0x1800311f8  mov     r9d, eax; char *
0x1800311fb  lea     r8, aOnecoreBaseFli_25; "onecore\\base\\flighting\\onesettings\\"...
0x180031202  mov     edx, 0CBh; void *
0x180031207  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003120d  lea     rcx, [rbp+57h+var_C8]
0x180031211  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x180031216  nop
0x180031217  lea     rcx, [rbp+57h+var_C0]
0x18003121b  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x180031220  nop
0x180031221  lea     rcx, [rbp+57h+var_A0]
0x180031225  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x18003122a  nop
0x18003122b  lea     rcx, [rbp+57h+var_B8]
0x18003122f  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x180031234  nop
0x180031235  lea     rcx, [rsp+110h+var_E0]
0x18003123a  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x18003123f  nop
0x180031240  lea     rcx, [rsp+110h+var_D8]
0x180031245  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x18003124a  nop
0x18003124b  lea     rcx, [rbp+57h+var_B0]
0x18003124f  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x180031254  nop
0x180031255  lea     rcx, [rbp+57h+var_98]
0x180031259  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x18003125e  mov     rax, r14
0x180031261  mov     rcx, [rbp+57h+var_30]
0x180031265  xor     rcx, rsp; StackCookie
0x180031268  call    __security_check_cookie
0x18003126d  mov     rbx, [rsp+110h+arg_0]
0x180031275  add     rsp, 0F0h
  ... truncated ...
```
