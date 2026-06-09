# MakePayloadHandler(Windows::Data::Json::IJsonObject *)

- ea: `0x18003c3e0`
- end: `0x18003c5c8`
- name: `?MakePayloadHandler@@YA?AV?$shared_ptr@VIPayloadHandler@@@std@@PEAUIJsonObject@Json@Data@Windows@@@Z`
- size: `488`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180024dec`
- `0x18002ca40`

## callees

- `0x180003110`
- `0x180009384`
- `0x180009fcc`
- `0x18000a250`
- `0x18000b0bc`
- `0x1800101fc`
- `0x180010ff8`
- `0x180011a44`
- `0x180011b20`
- `0x180032630`
- `0x18003c3e0`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c46f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c576`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c46f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c576`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003c494`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003c494`

## pseudocode

```c
__int64 __fastcall MakePayloadHandler(__int64 a1, __int64 a2)
{
  __int64 (__fastcall *v4)(__int64, __int64, HSTRING *); // rbx
  int v5; // eax
  const WCHAR *StringRawBuffer; // rbx
  wchar_t **v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64, _QWORD *); // rbx
  int v9; // eax
  HSTRING v11; // rax
  PCWSTR v12; // rax
  unsigned int v13; // eax
  const char *v14; // rdx
  int bIgnoreCase; // [rsp+20h] [rbp-50h]
  int bIgnoreCasea; // [rsp+20h] [rbp-50h]
  HSTRING string; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v18[2]; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  __int64 v20; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v18[0] = a1;
  string = 0;
  v4 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)a2 + 80LL);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    &string,
    0);
  v20 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"PayloadHandler", 0xFu, 0xEu);
  v5 = v4(a2, v20, &string);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\payloadhandlerfactory.cpp",
      (const char *)(unsigned int)v5,
      bIgnoreCase);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v7 = &off_18005B4F0;
  while ( CompareStringOrdinal(*v7, -1, StringRawBuffer, -1, 1) != 2 )
  {
    v7 += 2;
    if ( v7 == (wchar_t **)&std::_Ref_count_obj2<FilePayloadHandler>::`vftable' )
    {
      v11 = (HSTRING)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::get(&string);
      v12 = WindowsGetStringRawBuffer(v11, 0);
      v13 = wil::verify_hresult<long>(2147943568LL, v12);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x3A,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\payloadhandlerfactory.cpp",
        (const char *)v13,
        (int)"The specified OneSettings payload handler %ws is not known",
        v14);
    }
  }
  v18[0] = 0;
  v8 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)a2 + 64LL);
  wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::reset(v18);
  v20 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Metadata", 9u, 8u);
  v9 = v8(a2, v20, v18);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\payloadhandlerfactory.cpp",
      (const char *)(unsigned int)v9,
      bIgnoreCasea);
  ((void (__fastcall *)(__int64, _QWORD))v7[1])(a1, v18[0]);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(v18);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
  return a1;
}

```

## disassembly

```asm
0x18003c3e0  mov     [rsp-18h+arg_10], rbx
0x18003c3e5  mov     [rsp-18h+arg_18], rsi
0x18003c3ea  push    rbp
0x18003c3eb  push    rdi
0x18003c3ec  push    r14
0x18003c3ee  mov     rbp, rsp
0x18003c3f1  sub     rsp, 70h
0x18003c3f5  mov     rax, cs:__security_cookie
0x18003c3fc  xor     rax, rsp
0x18003c3ff  mov     [rbp+var_8], rax
0x18003c403  mov     r14, rdx
0x18003c406  mov     rsi, rcx
0x18003c409  mov     [rbp+var_38], rcx
0x18003c40d  mov     [rbp+string], 0
0x18003c415  mov     rax, [rdx]
0x18003c418  mov     rbx, [rax+50h]
0x18003c41c  xor     edx, edx
0x18003c41e  lea     rcx, [rbp+string]
0x18003c422  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18003c427  mov     [rbp+var_10], 0
0x18003c42f  mov     r9d, 0Eh; unsigned int
0x18003c435  lea     r8d, [r9+1]; unsigned int
0x18003c439  lea     rdx, aPayloadhandler; "PayloadHandler"
0x18003c440  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18003c444  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003c449  nop
0x18003c44a  lea     r8, [rbp+string]
0x18003c44e  mov     rdx, [rbp+var_10]
0x18003c452  mov     rcx, r14
0x18003c455  mov     rax, rbx
0x18003c458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c45d  mov     rcx, [rbp+18h]; this
0x18003c461  test    eax, eax
0x18003c463  js      loc_18003C5B3
0x18003c469  xor     edx, edx; length
0x18003c46b  mov     rcx, [rbp+string]; string
0x18003c46f  call    cs:__imp_WindowsGetStringRawBuffer
0x18003c475  mov     rbx, rax
0x18003c478  lea     rdi, off_18005B4F0; "FILE"
0x18003c47f  mov     [rsp+70h+bIgnoreCase], 1; int
0x18003c487  or      r9d, 0FFFFFFFFh; cchCount2
0x18003c48b  mov     r8, rbx; lpString2
0x18003c48e  or      edx, r9d; cchCount1
0x18003c491  mov     rcx, [rdi]; lpString1
0x18003c494  call    cs:__imp_CompareStringOrdinal
0x18003c49a  cmp     eax, 2
0x18003c49d  jz      short loc_18003C4B5
0x18003c49f  add     rdi, 10h
0x18003c4a3  lea     rax, ??_7?$_Ref_count_obj2@VFilePayloadHandler@@@std@@6B@; const std::_Ref_count_obj2<FilePayloadHandler>::`vftable'
0x18003c4aa  cmp     rdi, rax
0x18003c4ad  jz      loc_18003C568
0x18003c4b3  jmp     short loc_18003C47F
0x18003c4b5  mov     [rbp+var_38], 0
0x18003c4bd  mov     rax, [r14]
0x18003c4c0  mov     rbx, [rax+40h]
0x18003c4c4  lea     rcx, [rbp+var_38]
0x18003c4c8  call    ?reset@?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::reset(void)
0x18003c4cd  mov     [rbp+var_10], 0
0x18003c4d5  mov     r9d, 8; unsigned int
0x18003c4db  lea     r8d, [r9+1]; unsigned int
0x18003c4df  lea     rdx, aMetadata; "Metadata"
0x18003c4e6  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18003c4ea  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003c4ef  nop
0x18003c4f0  lea     r8, [rbp+var_38]
0x18003c4f4  mov     rdx, [rbp+var_10]
0x18003c4f8  mov     rcx, r14
0x18003c4fb  mov     rax, rbx
0x18003c4fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c503  mov     rcx, [rbp+18h]; this
0x18003c507  test    eax, eax
0x18003c509  js      short loc_18003C553
0x18003c50b  mov     rdx, [rbp+var_38]
0x18003c50f  mov     rcx, rsi
0x18003c512  mov     rax, [rdi+8]
0x18003c516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c51b  nop
0x18003c51c  lea     rcx, [rbp+var_38]
0x18003c520  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x18003c525  nop
0x18003c526  lea     rcx, [rbp+string]
0x18003c52a  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18003c52f  mov     rax, rsi
0x18003c532  mov     rcx, [rbp+var_8]
0x18003c536  xor     rcx, rsp; StackCookie
0x18003c539  call    __security_check_cookie
0x18003c53e  lea     r11, [rsp+70h+var_s0]
0x18003c543  mov     rbx, [r11+30h]
0x18003c547  mov     rsi, [r11+38h]
0x18003c54b  mov     rsp, r11
0x18003c54e  pop     r14
0x18003c550  pop     rdi
0x18003c551  pop     rbp
0x18003c552  retn
0x18003c553  mov     r9d, eax; char *
0x18003c556  lea     r8, aOnecoreBaseFli_18; "onecore\\base\\flighting\\onesettings\\"...
0x18003c55d  mov     edx, 31h ; '1'; void *
0x18003c562  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003c568  lea     rcx, [rbp+string]
0x18003c56c  call    ?get@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEBAPEAUHSTRING__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::get(void)
0x18003c571  mov     rcx, rax; string
0x18003c574  xor     edx, edx; length
0x18003c576  call    cs:__imp_WindowsGetStringRawBuffer
0x18003c57c  mov     rdx, rax
0x18003c57f  mov     ecx, 80070490h
0x18003c584  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18003c589  mov     r9d, eax; char *
0x18003c58c  mov     rcx, [rbp+18h]; this
0x18003c590  mov     [rsp+70h+var_48], rdx; char *
0x18003c595  lea     rax, aTheSpecifiedOn_2; "The specified OneSettings payload handl"...
0x18003c59c  mov     qword ptr [rsp+70h+bIgnoreCase], rax; int
0x18003c5a1  lea     r8, aOnecoreBaseFli_18; "onecore\\base\\flighting\\onesettings\\"...
0x18003c5a8  mov     edx, 3Ah ; ':'; void *
0x18003c5ad  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003c5b3  mov     r9d, eax; char *
0x18003c5b6  lea     r8, aOnecoreBaseFli_18; "onecore\\base\\flighting\\onesettings\\"...
0x18003c5bd  mov     edx, 27h ; '''; void *
0x18003c5c2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
