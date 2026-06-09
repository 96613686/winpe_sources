# WnsProvider::ParseAppVersion(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>,PushNotificationAppToRefresh &)

- ea: `0x18004d540`
- end: `0x18004d64b`
- name: `?ParseAppVersion@WnsProvider@@CA_NV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@AEAUPushNotificationAppToRefresh@@@Z`
- size: `267`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004d2c8`

## callees

- `0x180003110`
- `0x180006b9c`
- `0x180009fcc`
- `0x180019e68`
- `0x180020748`
- `0x18004af38`
- `0x18004d540`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d57e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d614`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d57e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d614`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d5ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d5ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall WnsProvider::ParseAppVersion(__int64 *a1, __int64 a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, PVOID, HSTRING *); // rbx
  HSTRING_HEADER *v6; // rax
  int v7; // eax
  char v8; // bl
  PCWSTR StringRawBuffer; // rax
  __int64 v10; // r8
  HSTRING string; // [rsp+20h] [rbp-58h] BYREF
  int v13; // [rsp+28h] [rbp-50h] BYREF
  __int64 *v14; // [rsp+30h] [rbp-48h]
  HSTRING_HEADER v15; // [rsp+38h] [rbp-40h] BYREF

  v14 = a1;
  string = 0;
  v4 = *a1;
  v5 = *(__int64 (__fastcall **)(__int64, PVOID, HSTRING *))(*(_QWORD *)*a1 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v15, (const WCHAR **)&WnsProvider::s_tagAppVersion);
  v7 = v5(v4, v6[1].Reserved.Reserved1, &string);
  v13 = v7;
  if ( v7 == -2089484279 )
  {
    *(_QWORD *)(a2 + 48) = 0;
    *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 32) = 0;
LABEL_8:
    v8 = 1;
    goto LABEL_9;
  }
  if ( v7 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v10 = -1;
    do
      ++v10;
    while ( StringRawBuffer[v10] );
    std::wstring::_Assign<unsigned short>(a2 + 32, StringRawBuffer);
    goto LABEL_8;
  }
  OneSettingsClientTelemetry::WnsPushNotificationPayloadParsingFailed<long &,unsigned short const * const &>(
    &v13,
    &WnsProvider::s_tagAppVersion);
  v8 = 0;
LABEL_9:
  WindowsDeleteString(string);
  string = 0;
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(a1);
  return v8;
}

```

## disassembly

```asm
0x18004d540  mov     r11, rsp
0x18004d543  mov     [r11+18h], rbx
0x18004d547  mov     [r11+20h], rbp
0x18004d54b  push    rsi
0x18004d54c  push    rdi
0x18004d54d  push    r14
0x18004d54f  sub     rsp, 60h
0x18004d553  mov     rax, cs:__security_cookie
0x18004d55a  xor     rax, rsp
0x18004d55d  mov     [rsp+78h+var_20], rax
0x18004d562  mov     rsi, rdx
0x18004d565  mov     r14, rcx
0x18004d568  mov     [r11-48h], rcx
0x18004d56c  xor     ebp, ebp
0x18004d56e  mov     [r11-58h], rbp
0x18004d572  mov     rdi, [rcx]
0x18004d575  mov     rax, [rdi]
0x18004d578  mov     rbx, [rax+50h]
0x18004d57c  xor     ecx, ecx; string
0x18004d57e  call    cs:__imp_WindowsDeleteString
0x18004d584  mov     [rsp+78h+string], rbp
0x18004d589  lea     rdx, ?s_tagAppVersion@WnsProvider@@0QEBGEB; ushort const * const WnsProvider::s_tagAppVersion
0x18004d590  lea     rcx, [rsp+78h+var_40]
0x18004d595  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004d59a  nop
0x18004d59b  lea     r8, [rsp+78h+string]
0x18004d5a0  mov     rdx, [rax+18h]
0x18004d5a4  mov     rcx, rdi
0x18004d5a7  mov     rax, rbx
0x18004d5aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d5af  mov     [rsp+78h+var_50], eax
0x18004d5b3  cmp     eax, 83750009h
0x18004d5b8  jnz     short loc_18004D5CC
0x18004d5ba  lea     rcx, [rsi+20h]
0x18004d5be  mov     [rcx+10h], rbp
0x18004d5c2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004d5c7  mov     [rax], bp
0x18004d5ca  jmp     short loc_18004D60D
0x18004d5cc  test    eax, eax
0x18004d5ce  jns     short loc_18004D5E6
0x18004d5d0  lea     rdx, ?s_tagAppVersion@WnsProvider@@0QEBGEB; ushort const * const WnsProvider::s_tagAppVersion
0x18004d5d7  lea     rcx, [rsp+78h+var_50]
0x18004d5dc  call    ??$WnsPushNotificationPayloadParsingFailed@AEAJAEBQEBG@OneSettingsClientTelemetry@@SAXAEAJAEBQEBG@Z; OneSettingsClientTelemetry::WnsPushNotificationPayloadParsingFailed<long &,ushort const * const &>(long &,ushort const * const &)
0x18004d5e1  mov     bl, bpl
0x18004d5e4  jmp     short loc_18004D60F
0x18004d5e6  xor     edx, edx; length
0x18004d5e8  mov     rcx, [rsp+78h+string]; string
0x18004d5ed  call    cs:__imp_WindowsGetStringRawBuffer
0x18004d5f3  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004d5f7  inc     r8
0x18004d5fa  cmp     [rax+r8*2], bp
0x18004d5ff  jnz     short loc_18004D5F7
0x18004d601  lea     rcx, [rsi+20h]
0x18004d605  mov     rdx, rax
0x18004d608  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18004d60d  mov     bl, 1
0x18004d60f  mov     rcx, [rsp+78h+string]; string
0x18004d614  call    cs:__imp_WindowsDeleteString
0x18004d61a  mov     [rsp+78h+string], rbp
0x18004d61f  mov     rcx, r14
0x18004d622  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x18004d627  mov     al, bl
0x18004d629  mov     rcx, [rsp+78h+var_20]
0x18004d62e  xor     rcx, rsp; StackCookie
0x18004d631  call    __security_check_cookie
0x18004d636  lea     r11, [rsp+78h+var_18]
0x18004d63b  mov     rbx, [r11+30h]
0x18004d63f  mov     rbp, [r11+38h]
0x18004d643  mov     rsp, r11
0x18004d646  pop     r14
0x18004d648  pop     rdi
0x18004d649  pop     rsi
0x18004d64a  retn
```
