# MakeNotificationType(Windows::Data::Json::IJsonObject *)

- ea: `0x180032458`
- end: `0x180032629`
- name: `?MakeNotificationType@@YA?AV?$shared_ptr@VINotificationType@@@std@@PEAUIJsonObject@Json@Data@Windows@@@Z`
- size: `465`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180024cd0`
- `0x18002ca40`

## callees

- `0x180003110`
- `0x180009384`
- `0x180009fcc`
- `0x18000a250`
- `0x18000b0bc`
- `0x1800101fc`
- `0x180011a44`
- `0x180011b20`
- `0x180032458`
- `0x180032630`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800324e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800324e7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003250c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003250c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MakeNotificationType(__int64 a1, __int64 a2)
{
  __int64 (__fastcall *v4)(__int64, __int64, HSTRING *); // rbx
  int v5; // eax
  const char *StringRawBuffer; // rbx
  wchar_t **v7; // rdi
  __int64 v8; // rdx
  __int64 (__fastcall *v9)(__int64, __int64, __int64 *); // rbx
  int v10; // eax
  unsigned int v12; // eax
  int bIgnoreCase; // [rsp+20h] [rbp-50h]
  int bIgnoreCasea; // [rsp+20h] [rbp-50h]
  HSTRING string; // [rsp+30h] [rbp-40h] BYREF
  __int64 v16[2]; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  __int64 v18; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  string = 0;
  v4 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)a2 + 80LL);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    &string,
    0);
  v18 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"NotificationType", 0x11u, 0x10u);
  v5 = v4(a2, v18, &string);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\notifications\\notificationtypefactory.cpp",
      (const char *)(unsigned int)v5,
      bIgnoreCase);
  StringRawBuffer = (const char *)WindowsGetStringRawBuffer(string, 0);
  v7 = &off_18005B380;
  while ( CompareStringOrdinal(*v7, -1, (LPCWCH)StringRawBuffer, -1, 1) != 2 )
  {
    v7 += 2;
    if ( v7 == (wchar_t **)&std::_Ref_count_obj2<WnfNotificationType>::`vftable' )
    {
      v12 = wil::verify_hresult<long>(2147943568LL, v8);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x37,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\notifications\\notificationtypefactory.cpp",
        (const char *)v12,
        (int)"The specified notification type %ws is not known",
        StringRawBuffer);
    }
  }
  v16[0] = 0;
  v9 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)a2 + 64LL);
  wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::reset(v16);
  v18 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Metadata", 9u, 8u);
  v10 = v9(a2, v18, v16);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x30,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\notifications\\notificationtypefactory.cpp",
      (const char *)(unsigned int)v10,
      bIgnoreCasea);
  ((void (__fastcall *)(__int64, __int64 *))v7[1])(a1, v16);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(v16);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
  return a1;
}

```

## disassembly

```asm
0x180032458  mov     [rsp-18h+arg_10], rbx
0x18003245d  mov     [rsp-18h+arg_18], rsi
0x180032462  push    rbp
0x180032463  push    rdi
0x180032464  push    r14
0x180032466  mov     rbp, rsp
0x180032469  sub     rsp, 70h
0x18003246d  mov     rax, cs:__security_cookie
0x180032474  xor     rax, rsp
0x180032477  mov     [rbp+var_8], rax
0x18003247b  mov     r14, rdx
0x18003247e  mov     rsi, rcx
0x180032481  mov     [rbp+string], rcx
0x180032485  mov     [rbp+string], 0
0x18003248d  mov     rax, [rdx]
0x180032490  mov     rbx, [rax+50h]
0x180032494  xor     edx, edx
0x180032496  lea     rcx, [rbp+string]
0x18003249a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18003249f  mov     [rbp+var_10], 0
0x1800324a7  mov     r9d, 10h; unsigned int
0x1800324ad  lea     r8d, [r9+1]; unsigned int
0x1800324b1  lea     rdx, aNotificationty; "NotificationType"
0x1800324b8  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800324bc  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800324c1  nop
0x1800324c2  lea     r8, [rbp+string]
0x1800324c6  mov     rdx, [rbp+var_10]
0x1800324ca  mov     rcx, r14
0x1800324cd  mov     rax, rbx
0x1800324d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324d5  mov     rcx, [rbp+18h]; this
0x1800324d9  test    eax, eax
0x1800324db  js      loc_180032614
0x1800324e1  xor     edx, edx; length
0x1800324e3  mov     rcx, [rbp+string]; string
0x1800324e7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800324ed  mov     rbx, rax
0x1800324f0  lea     rdi, off_18005B380; "WNF"
0x1800324f7  mov     [rsp+70h+bIgnoreCase], 1; int
0x1800324ff  or      r9d, 0FFFFFFFFh; cchCount2
0x180032503  mov     r8, rbx; lpString2
0x180032506  or      edx, r9d; cchCount1
0x180032509  mov     rcx, [rdi]; lpString1
0x18003250c  call    cs:__imp_CompareStringOrdinal
0x180032512  cmp     eax, 2
0x180032515  jz      short loc_18003252D
0x180032517  add     rdi, 10h
0x18003251b  lea     rax, ??_7?$_Ref_count_obj2@VWnfNotificationType@@@std@@6B@; const std::_Ref_count_obj2<WnfNotificationType>::`vftable'
0x180032522  cmp     rdi, rax
0x180032525  jz      loc_1800325E0
0x18003252b  jmp     short loc_1800324F7
0x18003252d  mov     [rbp+var_38], 0
0x180032535  mov     rax, [r14]
0x180032538  mov     rbx, [rax+40h]
0x18003253c  lea     rcx, [rbp+var_38]
0x180032540  call    ?reset@?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::reset(void)
0x180032545  mov     [rbp+var_10], 0
0x18003254d  mov     r9d, 8; unsigned int
0x180032553  lea     r8d, [r9+1]; unsigned int
0x180032557  lea     rdx, aMetadata; "Metadata"
0x18003255e  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180032562  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180032567  nop
0x180032568  lea     r8, [rbp+var_38]
0x18003256c  mov     rdx, [rbp+var_10]
0x180032570  mov     rcx, r14
0x180032573  mov     rax, rbx
0x180032576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003257b  mov     rcx, [rbp+18h]; this
0x18003257f  test    eax, eax
0x180032581  js      short loc_1800325CB
0x180032583  lea     rdx, [rbp+var_38]
0x180032587  mov     rcx, rsi
0x18003258a  mov     rax, [rdi+8]
0x18003258e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032593  nop
0x180032594  lea     rcx, [rbp+var_38]
0x180032598  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x18003259d  nop
0x18003259e  lea     rcx, [rbp+string]
0x1800325a2  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800325a7  mov     rax, rsi
0x1800325aa  mov     rcx, [rbp+var_8]
0x1800325ae  xor     rcx, rsp; StackCookie
0x1800325b1  call    __security_check_cookie
0x1800325b6  lea     r11, [rsp+70h+var_s0]
0x1800325bb  mov     rbx, [r11+30h]
0x1800325bf  mov     rsi, [r11+38h]
0x1800325c3  mov     rsp, r11
0x1800325c6  pop     r14
0x1800325c8  pop     rdi
0x1800325c9  pop     rbp
0x1800325ca  retn
0x1800325cb  mov     r9d, eax; char *
0x1800325ce  lea     r8, aOnecoreBaseFli_36; "onecore\\base\\flighting\\onesettings\\"...
0x1800325d5  mov     edx, 30h ; '0'; void *
0x1800325da  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800325e0  mov     ecx, 80070490h
0x1800325e5  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800325ea  mov     r9d, eax; char *
0x1800325ed  mov     rcx, [rbp+18h]; this
0x1800325f1  mov     [rsp+70h+var_48], rbx; char *
0x1800325f6  lea     rax, aTheSpecifiedNo; "The specified notification type %ws is "...
0x1800325fd  mov     qword ptr [rsp+70h+bIgnoreCase], rax; int
0x180032602  lea     r8, aOnecoreBaseFli_36; "onecore\\base\\flighting\\onesettings\\"...
0x180032609  mov     edx, 37h ; '7'; void *
0x18003260e  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180032614  mov     r9d, eax; char *
0x180032617  lea     r8, aOnecoreBaseFli_36; "onecore\\base\\flighting\\onesettings\\"...
0x18003261e  mov     edx, 26h ; '&'; void *
0x180032623  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
