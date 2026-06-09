# ClientEndpoint::ClientEndpoint(ushort const *,Windows::Data::Json::IJsonObject *)

- ea: `0x18002ca40`
- end: `0x18002d10f`
- name: `??0ClientEndpoint@@QEAA@PEBGPEAUIJsonObject@Json@Data@Windows@@@Z`
- size: `1743`
- prototype: `ClientEndpoint *__fastcall(ClientEndpoint *this, unsigned __int16 *, struct Windows::Data::Json::IJsonObject *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002ca2c`

## callees

- `0x180003110`
- `0x180003210`
- `0x180005f50`
- `0x180006b9c`
- `0x180008a80`
- `0x180009fcc`
- `0x18000a194`
- `0x18000b0bc`
- `0x18000fe24`
- `0x1800101fc`
- `0x180014b08`
- `0x18001a64c`
- `0x180020748`
- `0x180021f1c`
- `0x180028324`
- `0x18002c5a0`
- `0x18002ca40`
- `0x18002d13c`
- `0x18002d258`
- `0x18002ecfc`
- `0x180032458`
- `0x18003c3e0`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002cb27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002cb93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002cc08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d087`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002cb27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002cb93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002cc08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d087`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002cfc4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002cfc4`

## string_xrefs

- `0x18002cfa4`: `Windows.Data.Json.JsonObject`
- `0x18002cb73`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientendpoint.cpp`
- `0x18002cbe5`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientendpoint.cpp`
- `0x18002cc4e`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientendpoint.cpp`
- `0x18002ccfc`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientendpoint.cpp`
- `0x18002cfd5`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientendpoint.cpp`
- `0x18002d03b`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientendpoint.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
ClientEndpoint *__fastcall ClientEndpoint::ClientEndpoint(
        ClientEndpoint *this,
        unsigned __int16 *a2,
        struct Windows::Data::Json::IJsonObject *a3)
{
  __int64 v5; // rdx
  HSTRING *v6; // r13
  __int64 v7; // r15
  __int64 v8; // r8
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64, char *); // rbx
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64, char *); // rbx
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64, char *); // rbx
  int v17; // eax
  __int64 v18; // rdi
  int (__fastcall *v19)(__int64, __int64, char *); // rbx
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, __int64, char *); // rbx
  int v22; // eax
  __int64 PayloadHandler; // rax
  __int64 v24; // rdi
  int (__fastcall *v25)(__int64, __int64, char *); // rbx
  __int64 NotificationType; // rax
  __int64 v27; // rdi
  int (__fastcall *v28)(__int64, __int64, struct Windows::Data::Json::IJsonObject **); // rbx
  struct Windows::Data::Json::IJsonObject *v29; // rbx
  __int64 v30; // rdi
  int (__fastcall *v31)(__int64, __int64, double *); // rbx
  __int64 v32; // rdi
  int (__fastcall *v33)(__int64, __int64, double *); // rbx
  int v34; // ecx
  __int64 v35; // rdi
  int (__fastcall *v36)(__int64, __int64, char *); // rbx
  __int64 v37; // rdi
  int (__fastcall *v38)(__int64, __int64, char *); // rbx
  int ActivationFactory; // eax
  __int64 v40; // rdi
  __int64 (__fastcall *v41)(__int64, PVOID, char *); // rbx
  HSTRING_HEADER *v42; // rax
  int v43; // eax
  __int64 v44; // rax
  __int64 v45; // rdi
  void (__fastcall *v46)(__int64, __int64, char *); // rbx
  struct Windows::Data::Json::IJsonObject *v48; // [rsp+28h] [rbp-79h] BYREF
  __int64 v49; // [rsp+30h] [rbp-71h] BYREF
  double v50; // [rsp+38h] [rbp-69h] BYREF
  double v51[2]; // [rsp+40h] [rbp-61h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-51h] BYREF
  __int64 v53; // [rsp+68h] [rbp-39h]
  HSTRING_HEADER v54; // [rsp+70h] [rbp-31h] BYREF
  __int64 v55; // [rsp+88h] [rbp-19h]
  HSTRING_HEADER v56; // [rsp+90h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+5Fh]

  *(_QWORD *)&v51[1] = this;
  v54.Reserved.Reserved1 = a2;
  *(_QWORD *)this = 0;
  std::wstring::wstring((char *)this + 8);
  *((_QWORD *)this + 5) = v5;
  v6 = (HSTRING *)((char *)this + 48);
  *((_QWORD *)this + 6) = v5;
  *((_QWORD *)this + 7) = v5;
  *((_BYTE *)this + 64) = v5;
  *((_QWORD *)this + 9) = v5;
  *((_QWORD *)this + 10) = v5;
  *((_QWORD *)this + 11) = v5;
  *((_QWORD *)this + 12) = v5;
  *((_QWORD *)this + 13) = v5;
  *((_QWORD *)this + 14) = v5;
  *((_QWORD *)this + 15) = v5;
  *((_QWORD *)this + 16) = v5;
  *((_QWORD *)this + 17) = v5;
  *((_QWORD *)this + 18) = v5;
  v7 = (unsigned int)(v5 + 1);
  *((_QWORD *)this + 19) = v7;
  *((_BYTE *)this + 160) = v5;
  *((_BYTE *)this + 162) = v5;
  *((_QWORD *)this + 21) = v5;
  Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::operator=(this, v8);
  std::_WChar_traits<unsigned short>::length(a2);
  std::wstring::_Assign<unsigned short>((char *)this + 8, a2);
  v9 = *(_QWORD *)this;
  v10 = *(__int64 (__fastcall **)(__int64, __int64, char *))(**(_QWORD **)this + 80LL);
  WindowsDeleteString(*((HSTRING *)this + 5));
  *((_QWORD *)this + 5) = 0;
  v53 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Partner", v7 + 7, v7 + 6);
  v11 = v10(v9, v53, (char *)this + 40);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientendpoint.cpp",
      (const char *)(unsigned int)v11,
      (int)v48);
  v12 = *(_QWORD *)this;
  v13 = *(__int64 (__fastcall **)(__int64, __int64, char *))(**(_QWORD **)this + 80LL);
  WindowsDeleteString(*v6);
  *v6 = 0;
  v53 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Feature", 8u, 7u);
  v14 = v13(v12, v53, (char *)this + 48);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE0,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientendpoint.cpp",
      (const char *)(unsigned int)v14,
      (int)v48);
  v15 = *(_QWORD *)this;
  v16 = *(__int64 (__fastcall **)(__int64, __int64, char *))(**(_QWORD **)this + 80LL);
  WindowsDeleteString(*((HSTRING *)this + 7));
  *((_QWORD *)this + 7) = 0;
  v53 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"CtacAppId", 0xAu, 9u);
  v17 = v16(v15, v53, (char *)this + 56);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE3,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientendpoint.cpp",
      (const char *)(unsigned int)v17,
      (int)v48);
  v18 = *(_QWORD *)this;
  v19 = *(int (__fastcall **)(__int64, __int64, char *))(**(_QWORD **)this + 96LL);
  v53 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"OnDemandOnly", 0xDu, 0xCu);
  if ( v19(v18, v53, (char *)this + 65) < 0 )
    *((_BYTE *)this + 65) = *((_BYTE *)this + 64);
  v20 = *(_QWORD *)this;
  v21 = *(__int64 (__fastcall **)(__int64, __int64, char *))(**(_QWORD **)this + 64LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 72);
  v53 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Payload", 8u, 7u);
  v22 = v21(v20, v53, (char *)this + 72);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xEC,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientendpoint.cpp",
      (const char *)(unsigned int)v22,
      (int)v48);
  PayloadHandler = MakePayloadHandler((__int64)&hstringHeader, *((_QWORD *)this + 9));
  std::shared_ptr<CnsFlightState>::operator=((char *)this + 80, PayloadHandler);
  if ( *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] )
    std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&hstringHeader.Reserved.Reserved2[8]);
  v24 = *(_QWORD *)this;
  v25 = *(int (__fastcall **)(__int64, __int64, char *))(**(_QWORD **)this + 64LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 120);
  v53 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Notification", 0xDu, 0xCu);
  if ( v25(v24, v53, (char *)this + 120) >= 0 )
  {
    NotificationType = MakeNotificationType(&hstringHeader, *((_QWORD *)this + 15));
    std::shared_ptr<CnsFlightState>::operator=((char *)this + 128, NotificationType);
    if ( *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&hstringHeader.Reserved.Reserved2[8]);
  }
  v48 = 0;
  v27 = *(_QWORD *)this;
  v28 = *(int (__fastcall **)(__int64, __int64, struct Windows::Data::Json::IJsonObject **))(**(_QWORD **)this + 64LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
  v53 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"RefreshIntervals", 0x11u, 0x10u);
  if ( v28(v27, v53, &v48) >= 0 )
  {
    v29 = v48;
    hstringHeader.Reserved.Reserved1 = operator new(0x20u);
    hstringHeader.Reserved.Reserved1 = RefreshPolicy::RefreshPolicy(
                                         (RefreshPolicy *)hstringHeader.Reserved.Reserved1,
                                         v29);
    std::unique_ptr<RefreshPolicy>::operator=<std::default_delete<RefreshPolicy>,0>(
      (__int64 *)this + 18,
      (__int64 *)&hstringHeader);
    std::unique_ptr<RefreshPolicy>::~unique_ptr<RefreshPolicy>(&hstringHeader);
  }
  v50 = 0.0;
  v30 = *(_QWORD *)this;
  v31 = *(int (__fastcall **)(__int64, __int64, double *))(**(_QWORD **)this + 88LL);
  v53 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"DeviceTicketOption", 0x13u, 0x12u);
  if ( v31(v30, v53, &v50) >= 0 )
  {
    if ( (unsigned int)(int)v50 <= 2 )
      LODWORD(v7) = (int)v50;
    *((_DWORD *)this + 38) = v7;
  }
  v51[0] = 0.0;
  v32 = *(_QWORD *)this;
  v33 = *(int (__fastcall **)(__int64, __int64, double *))(**(_QWORD **)this + 88LL);
  v53 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"UserTicketOption", 0x11u, 0x10u);
  if ( v33(v32, v53, v51) >= 0 )
  {
    v34 = (int)v51[0];
    if ( (unsigned int)(int)v51[0] > 2 )
      v34 = 0;
    *((_DWORD *)this + 39) = v34;
  }
  v35 = *(_QWORD *)this;
  v36 = *(int (__fastcall **)(__int64, __int64, char *))(**(_QWORD **)this + 96LL);
  v53 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"MigrateSettings", 0x10u, 0xFu);
  if ( v36(v35, v53, (char *)this + 161) < 0 )
    *((_BYTE *)this + 161) = *((_BYTE *)this + 160);
  v37 = *(_QWORD *)this;
  v38 = *(int (__fastcall **)(__int64, __int64, char *))(**(_QWORD **)this + 96LL);
  v53 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"StrictRefreshInterval", 0x16u, 0x15u);
  if ( v38(v37, v53, (char *)this + 163) < 0 )
    *((_BYTE *)this + 163) = *((_BYTE *)this + 162);
  std::make_unique<ClientState,unsigned short const * &,0>((ClientState **)&hstringHeader, (unsigned __int16 **)&v54);
  v49 = 0;
  v55 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v54, L"Windows.Data.Json.JsonObject", 0x1Du, 0x1Cu);
  ActivationFactory = RoGetActivationFactory(v55, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v49);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x121,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientendpoint.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)v48);
  v54.Reserved.Reserved1 = (PVOID)ClientState::GetLastTestPayloadHandlerJsonString((ClientState *)hstringHeader.Reserved.Reserved1);
  if ( v54.Reserved.Reserved1 )
  {
    v40 = v49;
    v41 = *(__int64 (__fastcall **)(__int64, PVOID, char *))(*(_QWORD *)v49 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 96);
    v42 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v56, (const WCHAR **)&v54);
    v43 = v41(v40, v42[1].Reserved.Reserved1, (char *)this + 96);
    if ( v43 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x125,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientendpoint.cpp",
        (const char *)(unsigned int)v43,
        (int)v48);
    v44 = MakePayloadHandler((__int64)&v54, *((_QWORD *)this + 12));
    std::shared_ptr<CnsFlightState>::operator=((char *)this + 104, v44);
    if ( *(_QWORD *)&v54.Reserved.Reserved2[8] )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v54.Reserved.Reserved2[8]);
  }
  v45 = *(_QWORD *)this;
  v46 = *(void (__fastcall **)(__int64, __int64, char *))(**(_QWORD **)this + 80LL);
  WindowsDeleteString(*((HSTRING *)this + 21));
  *((_QWORD *)this + 21) = 0;
  v55 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v54, L"KnownEntityId", 0xEu, 0xDu);
  v46(v45, v55, (char *)this + 168);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(&v49);
  std::_Temporary_owner<ClientState>::~_Temporary_owner<ClientState>(&hstringHeader);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
  return this;
}

```

## disassembly

```asm
0x18002ca40  mov     rax, rsp
0x18002ca43  mov     [rax+20h], rbx
0x18002ca47  push    rbp
0x18002ca48  push    rsi
0x18002ca49  push    rdi
0x18002ca4a  push    r12
0x18002ca4c  push    r13
0x18002ca4e  push    r14
0x18002ca50  push    r15
0x18002ca52  lea     rbp, [rax-5Fh]
0x18002ca56  sub     rsp, 0C0h
0x18002ca5d  movaps  xmmword ptr [rax-48h], xmm6
0x18002ca61  mov     rax, cs:__security_cookie
0x18002ca68  xor     rax, rsp
0x18002ca6b  mov     [rbp+57h+var_48], rax
0x18002ca6f  mov     rdi, rdx
0x18002ca72  mov     r14, rcx
0x18002ca75  mov     [rbp+57h+var_B0], rcx
0x18002ca79  mov     qword ptr [rbp+57h+var_88.Reserved], rdx
0x18002ca7d  xor     edx, edx
0x18002ca7f  mov     [rcx], rdx
0x18002ca82  add     rcx, 8
0x18002ca86  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002ca8b  nop
0x18002ca8c  lea     rsi, [r14+28h]
0x18002ca90  mov     [rsi], rdx
0x18002ca93  lea     r13, [r14+30h]
0x18002ca97  mov     [r13+0], rdx
0x18002ca9b  mov     [r14+38h], rdx
0x18002ca9f  mov     [r14+40h], dl
0x18002caa3  mov     [r14+48h], rdx
0x18002caa7  mov     [r14+50h], rdx
0x18002caab  mov     [r14+58h], rdx
0x18002caaf  mov     [r14+60h], rdx
0x18002cab3  mov     [r14+68h], rdx
0x18002cab7  mov     [r14+70h], rdx
0x18002cabb  lea     r12, [r14+78h]
0x18002cabf  mov     [r12], rdx
0x18002cac3  lea     rax, [r14+80h]
0x18002caca  mov     [rax], rdx
0x18002cacd  mov     [rax+8], rdx
0x18002cad1  mov     [r14+90h], rdx
0x18002cad8  lea     r15d, [rdx+1]
0x18002cadc  mov     [r14+98h], r15
0x18002cae3  mov     [r14+0A0h], dl
0x18002caea  mov     [r14+0A2h], dl
0x18002caf1  mov     [r14+0A8h], rdx
0x18002caf8  mov     rdx, r8
0x18002cafb  mov     rcx, r14
0x18002cafe  call    ??4?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEAAAEAV012@PEAUIJsonObject@Json@Data@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::operator=(Windows::Data::Json::IJsonObject *)
0x18002cb03  mov     rcx, rdi
0x18002cb06  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002cb0b  mov     r8, rax
0x18002cb0e  mov     rdx, rdi
0x18002cb11  lea     rcx, [r14+8]
0x18002cb15  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002cb1a  mov     rdi, [r14]
0x18002cb1d  mov     rax, [rdi]
0x18002cb20  mov     rbx, [rax+50h]
0x18002cb24  mov     rcx, [rsi]; string
0x18002cb27  call    cs:__imp_WindowsDeleteString
0x18002cb2d  mov     qword ptr [rsi], 0
0x18002cb34  mov     [rbp+57h+var_90], 0
0x18002cb3c  lea     r9d, [r15+6]; unsigned int
0x18002cb40  lea     r8d, [r15+7]; unsigned int
0x18002cb44  lea     rdx, ?s_jsonPartner@ClientEndpoint@@0QBGB; "Partner"
0x18002cb4b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18002cb4f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002cb54  nop
0x18002cb55  mov     r8, rsi
0x18002cb58  mov     rdx, [rbp+57h+var_90]
0x18002cb5c  mov     rcx, rdi
0x18002cb5f  mov     rax, rbx
0x18002cb62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb67  nop
0x18002cb68  mov     rcx, [rbp+5Fh]; this
0x18002cb6c  test    eax, eax
0x18002cb6e  jns     short loc_18002CB85
0x18002cb70  mov     r9d, eax; char *
0x18002cb73  lea     r8, aOnecoreBaseFli; "onecore\\base\\flighting\\onesettings\\"...
0x18002cb7a  mov     edx, 0DDh; void *
0x18002cb7f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002cb85  mov     rdi, [r14]
0x18002cb88  mov     rax, [rdi]
0x18002cb8b  mov     rbx, [rax+50h]
0x18002cb8f  mov     rcx, [r13+0]; string
0x18002cb93  call    cs:__imp_WindowsDeleteString
0x18002cb99  mov     qword ptr [r13+0], 0
0x18002cba1  mov     [rbp+57h+var_90], 0
0x18002cba9  mov     r9d, 7; unsigned int
0x18002cbaf  lea     r8d, [r9+1]; unsigned int
0x18002cbb3  lea     rdx, ?s_jsonFeature@ClientEndpoint@@0QBGB; "Feature"
0x18002cbba  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18002cbbe  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002cbc3  nop
0x18002cbc4  mov     r8, r13
0x18002cbc7  mov     rdx, [rbp+57h+var_90]
0x18002cbcb  mov     rcx, rdi
0x18002cbce  mov     rax, rbx
0x18002cbd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cbd6  nop
0x18002cbd7  mov     rcx, [rbp+5Fh]; this
0x18002cbdb  xor     r13d, r13d
0x18002cbde  test    eax, eax
0x18002cbe0  jns     short loc_18002CBF7
0x18002cbe2  mov     r9d, eax; char *
0x18002cbe5  lea     r8, aOnecoreBaseFli; "onecore\\base\\flighting\\onesettings\\"...
0x18002cbec  mov     edx, 0E0h; void *
0x18002cbf1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002cbf7  mov     rdi, [r14]
0x18002cbfa  mov     rax, [rdi]
0x18002cbfd  mov     rbx, [rax+50h]
0x18002cc01  lea     rsi, [r14+38h]
0x18002cc05  mov     rcx, [rsi]; string
0x18002cc08  call    cs:__imp_WindowsDeleteString
0x18002cc0e  mov     [rsi], r13
0x18002cc11  mov     [rbp+57h+var_90], r13
0x18002cc15  mov     r9d, 9; unsigned int
0x18002cc1b  lea     r8d, [r9+1]; unsigned int
0x18002cc1f  lea     rdx, ?s_jsonCtacAppId@ClientEndpoint@@0QBGB; "CtacAppId"
0x18002cc26  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18002cc2a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002cc2f  nop
0x18002cc30  mov     r8, rsi
0x18002cc33  mov     rdx, [rbp+57h+var_90]
0x18002cc37  mov     rcx, rdi
0x18002cc3a  mov     rax, rbx
0x18002cc3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc42  nop
0x18002cc43  mov     rcx, [rbp+5Fh]; this
0x18002cc47  test    eax, eax
0x18002cc49  jns     short loc_18002CC60
0x18002cc4b  mov     r9d, eax; char *
0x18002cc4e  lea     r8, aOnecoreBaseFli; "onecore\\base\\flighting\\onesettings\\"...
0x18002cc55  mov     edx, 0E3h; void *
0x18002cc5a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002cc60  mov     rdi, [r14]
0x18002cc63  mov     rax, [rdi]
0x18002cc66  mov     rbx, [rax+60h]
0x18002cc6a  mov     [rbp+57h+var_90], r13
0x18002cc6e  mov     r9d, 0Ch; unsigned int
0x18002cc74  lea     r8d, [r9+1]; unsigned int
0x18002cc78  lea     rdx, ?s_jsonOnDemandOnly@ClientEndpoint@@0QBGB; "OnDemandOnly"
0x18002cc7f  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18002cc83  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002cc88  nop
0x18002cc89  lea     r8, [r14+41h]
0x18002cc8d  mov     rdx, [rbp+57h+var_90]
0x18002cc91  mov     rcx, rdi
0x18002cc94  mov     rax, rbx
0x18002cc97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc9c  nop
0x18002cc9d  test    eax, eax
0x18002cc9f  jns     short loc_18002CCA9
0x18002cca1  mov     al, [r14+40h]
0x18002cca5  mov     [r14+41h], al
0x18002cca9  mov     rdi, [r14]
0x18002ccac  mov     rax, [rdi]
0x18002ccaf  mov     rbx, [rax+40h]
0x18002ccb3  lea     rsi, [r14+48h]
0x18002ccb7  mov     rcx, rsi
0x18002ccba  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ccbf  mov     [rbp+57h+var_90], r13
0x18002ccc3  mov     r9d, 7; unsigned int
0x18002ccc9  lea     r8d, [r9+1]; unsigned int
0x18002cccd  lea     rdx, ?s_jsonPayload@ClientEndpoint@@0QBGB; "Payload"
0x18002ccd4  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18002ccd8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002ccdd  nop
0x18002ccde  mov     r8, rsi
0x18002cce1  mov     rdx, [rbp+57h+var_90]
0x18002cce5  mov     rcx, rdi
0x18002cce8  mov     rax, rbx
0x18002cceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ccf0  nop
0x18002ccf1  mov     rcx, [rbp+5Fh]; this
0x18002ccf5  test    eax, eax
0x18002ccf7  jns     short loc_18002CD0E
0x18002ccf9  mov     r9d, eax; char *
0x18002ccfc  lea     r8, aOnecoreBaseFli; "onecore\\base\\flighting\\onesettings\\"...
0x18002cd03  mov     edx, 0ECh; void *
0x18002cd08  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002cd0e  mov     rdx, [rsi]
0x18002cd11  lea     rcx, [rbp+57h+hstringHeader]
0x18002cd15  call    ?MakePayloadHandler@@YA?AV?$shared_ptr@VIPayloadHandler@@@std@@PEAUIJsonObject@Json@Data@Windows@@@Z; MakePayloadHandler(Windows::Data::Json::IJsonObject *)
0x18002cd1a  mov     rdx, rax
0x18002cd1d  lea     rcx, [r14+50h]
0x18002cd21  call    ??4?$shared_ptr@UCnsFlightState@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CnsFlightState>::operator=(std::shared_ptr<CnsFlightState> &&)
0x18002cd26  mov     rcx, qword ptr [rbp+57h+hstringHeader.Reserved+8]; this
0x18002cd2a  test    rcx, rcx
0x18002cd2d  jz      short loc_18002CD34
0x18002cd2f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002cd34  mov     rdi, [r14]
0x18002cd37  mov     rax, [rdi]
0x18002cd3a  mov     rbx, [rax+40h]
0x18002cd3e  mov     rcx, r12
0x18002cd41  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002cd46  mov     [rbp+57h+var_90], r13
0x18002cd4a  mov     r9d, 0Ch; unsigned int
0x18002cd50  lea     r8d, [r9+1]; unsigned int
0x18002cd54  lea     rdx, ?s_jsonNotification@ClientEndpoint@@0QBGB; "Notification"
0x18002cd5b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18002cd5f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002cd64  nop
0x18002cd65  mov     r8, r12
0x18002cd68  mov     rdx, [rbp+57h+var_90]
0x18002cd6c  mov     rcx, rdi
0x18002cd6f  mov     rax, rbx
0x18002cd72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd77  nop
0x18002cd78  test    eax, eax
0x18002cd7a  js      short loc_18002CDA6
0x18002cd7c  mov     rdx, [r12]
0x18002cd80  lea     rcx, [rbp+57h+hstringHeader]
0x18002cd84  call    ?MakeNotificationType@@YA?AV?$shared_ptr@VINotificationType@@@std@@PEAUIJsonObject@Json@Data@Windows@@@Z; MakeNotificationType(Windows::Data::Json::IJsonObject *)
0x18002cd89  mov     rdx, rax
0x18002cd8c  lea     rcx, [r14+80h]
0x18002cd93  call    ??4?$shared_ptr@UCnsFlightState@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CnsFlightState>::operator=(std::shared_ptr<CnsFlightState> &&)
0x18002cd98  mov     rcx, qword ptr [rbp+57h+hstringHeader.Reserved+8]; this
0x18002cd9c  test    rcx, rcx
0x18002cd9f  jz      short loc_18002CDA6
0x18002cda1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002cda6  mov     [rbp+57h+var_D0], r13
0x18002cdaa  mov     rdi, [r14]
0x18002cdad  mov     rax, [rdi]
0x18002cdb0  mov     rbx, [rax+40h]
0x18002cdb4  lea     rcx, [rbp+57h+var_D0]
0x18002cdb8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002cdbd  mov     [rbp+57h+var_90], r13
0x18002cdc1  mov     esi, 10h
0x18002cdc6  mov     r9d, esi; unsigned int
0x18002cdc9  lea     r12d, [rsi+1]
0x18002cdcd  mov     r8d, r12d; unsigned int
0x18002cdd0  lea     rdx, ?s_jsonRefreshIntervals@ClientEndpoint@@0QBGB; "RefreshIntervals"
0x18002cdd7  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18002cddb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002cde0  nop
0x18002cde1  lea     r8, [rbp+57h+var_D0]
0x18002cde5  mov     rdx, [rbp+57h+var_90]
0x18002cde9  mov     rcx, rdi
0x18002cdec  mov     rax, rbx
0x18002cdef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cdf4  nop
0x18002cdf5  test    eax, eax
0x18002cdf7  js      short loc_18002CE32
0x18002cdf9  mov     rbx, [rbp+57h+var_D0]
0x18002cdfd  lea     ecx, [rsi+10h]; Size
0x18002ce00  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002ce05  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x18002ce09  mov     rdx, rbx; struct Windows::Data::Json::IJsonObject *
0x18002ce0c  mov     rcx, rax; this
0x18002ce0f  call    ??0RefreshPolicy@@QEAA@PEAUIJsonObject@Json@Data@Windows@@@Z; RefreshPolicy::RefreshPolicy(Windows::Data::Json::IJsonObject *)
0x18002ce14  nop
0x18002ce15  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x18002ce19  lea     rdx, [rbp+57h+hstringHeader]
0x18002ce1d  lea     rcx, [r14+90h]
0x18002ce24  call    ??$?4U?$default_delete@VRefreshPolicy@@@std@@$0A@@?$unique_ptr@VRefreshPolicy@@U?$default_delete@VRefreshPolicy@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<RefreshPolicy>::operator=<std::default_delete<RefreshPolicy>,0>(std::unique_ptr<RefreshPolicy> &&)
0x18002ce29  lea     rcx, [rbp+57h+hstringHeader]
0x18002ce2d  call    ??1?$unique_ptr@VRefreshPolicy@@U?$default_delete@VRefreshPolicy@@@std@@@std@@QEAA@XZ; std::unique_ptr<RefreshPolicy>::~unique_ptr<RefreshPolicy>(void)
0x18002ce32  xorps   xmm6, xmm6
0x18002ce35  movsd   [rbp+57h+var_C0], xmm6
0x18002ce3a  mov     rdi, [r14]
0x18002ce3d  mov     rax, [rdi]
0x18002ce40  mov     rbx, [rax+58h]
0x18002ce44  mov     [rbp+57h+var_90], r13
0x18002ce48  mov     r9d, 12h; unsigned int
0x18002ce4e  lea     r8d, [r9+1]; unsigned int
0x18002ce52  lea     rdx, ?s_jsonDeviceTicketOption@ClientEndpoint@@0QBGB; "DeviceTicketOption"
0x18002ce59  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18002ce5d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002ce62  nop
0x18002ce63  lea     r8, [rbp+57h+var_C0]
0x18002ce67  mov     rdx, [rbp+57h+var_90]
0x18002ce6b  mov     rcx, rdi
0x18002ce6e  mov     rax, rbx
0x18002ce71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce76  nop
0x18002ce77  test    eax, eax
0x18002ce79  js      short loc_18002CE8F
0x18002ce7b  cvttsd2si rax, [rbp+57h+var_C0]
0x18002ce81  cmp     eax, 2
0x18002ce84  cmovbe  r15d, eax
0x18002ce88  mov     [r14+98h], r15d
0x18002ce8f  movsd   [rbp+57h+var_B8], xmm6
0x18002ce94  mov     rdi, [r14]
0x18002ce97  mov     rax, [rdi]
0x18002ce9a  mov     rbx, [rax+58h]
0x18002ce9e  mov     [rbp+57h+var_90], r13
0x18002cea2  mov     r9d, esi; unsigned int
0x18002cea5  mov     r8d, r12d; unsigned int
0x18002cea8  lea     rdx, ?s_jsonUserTicketOption@ClientEndpoint@@0QBGB; "UserTicketOption"
0x18002ceaf  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18002ceb3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002ceb8  nop
0x18002ceb9  lea     r8, [rbp+57h+var_B8]
0x18002cebd  mov     rdx, [rbp+57h+var_90]
0x18002cec1  mov     rcx, rdi
0x18002cec4  mov     rax, rbx
0x18002cec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cecc  nop
  ... truncated ...
```
