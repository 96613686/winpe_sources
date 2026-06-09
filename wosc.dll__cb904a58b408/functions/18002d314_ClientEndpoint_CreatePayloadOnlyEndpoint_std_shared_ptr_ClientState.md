# ClientEndpoint::CreatePayloadOnlyEndpoint(std::shared_ptr<ClientState>)

- ea: `0x18002d314`
- end: `0x18002d585`
- name: `?CreatePayloadOnlyEndpoint@ClientEndpoint@@SA?AV?$shared_ptr@VClientEndpoint@@@std@@V?$shared_ptr@VClientState@@@3@@Z`
- size: `625`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180023e60`

## callees

- `0x180003110`
- `0x180003210`
- `0x180005f50`
- `0x180006b9c`
- `0x180009fcc`
- `0x18000b0bc`
- `0x18000fe24`
- `0x1800101fc`
- `0x180010278`
- `0x180019e68`
- `0x180024aa8`
- `0x18002599c`
- `0x1800261c0`
- `0x180028324`
- `0x18002c480`
- `0x18002ca2c`
- `0x18002d314`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002d415`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002d415`

## string_xrefs

- `0x18002d3f4`: `Windows.Data.Json.JsonObject`
- `0x18002d429`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientendpoint.cpp`
- `0x18002d4a7`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientendpoint.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall ClientEndpoint::CreatePayloadOnlyEndpoint(__int64 a1, const unsigned __int16 *a2)
{
  const unsigned __int16 *LastTestPayloadHandlerJsonString; // rax
  int ActivationFactory; // eax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, PVOID, int *); // rbx
  __int64 v8; // rax
  HSTRING_HEADER *v9; // rax
  int v10; // eax
  unsigned __int16 *v11; // rdi
  std::_Ref_count_base *v12; // rcx
  int v14[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v15; // [rsp+28h] [rbp-D8h] BYREF
  struct Windows::Data::Json::IJsonObject *v16; // [rsp+30h] [rbp-D0h] BYREF
  const unsigned __int16 *v17[5]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v18[240]; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+150h] [rbp+50h] BYREF
  __int64 v20; // [rsp+168h] [rbp+68h]
  _BYTE v21[32]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v17[0] = (const unsigned __int16 *)a1;
  v17[2] = a2;
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(v18);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v18, L"{");
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v18, L"\"Partner\": \"TEST\",");
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v18, L"\"Feature\": \"TEST\",");
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v18, L"\"CtacAppId\": \"TEST\",");
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v18, L"\"Payload\": ");
  LastTestPayloadHandlerJsonString = ClientState::GetLastTestPayloadHandlerJsonString(*(ClientState **)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v18, LastTestPayloadHandlerJsonString);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v18, L"}");
  v15 = 0;
  v20 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  ActivationFactory = RoGetActivationFactory(v20, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v15);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13A,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientendpoint.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v14[0]);
  *(_QWORD *)v14 = 0;
  v6 = v15;
  v7 = *(__int64 (__fastcall **)(__int64, PVOID, int *))(*(_QWORD *)v15 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v14);
  v8 = std::basic_ostringstream<unsigned short>::str(v18, v21);
  v16 = (struct Windows::Data::Json::IJsonObject *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v8);
  v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)&v16);
  v10 = v7(v6, v9[1].Reserved.Reserved1, v14);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13D,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientendpoint.cpp",
      (const char *)(unsigned int)v10,
      v14[0]);
  v20 = 0;
  std::wstring::_Tidy_deallocate(v21);
  v16 = *(struct Windows::Data::Json::IJsonObject **)v14;
  v17[0] = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*(_QWORD *)a2);
  v11 = (unsigned __int16 *)operator new(0xC0u);
  v17[3] = v11;
  *(_OWORD *)v11 = 0;
  *((_DWORD *)v11 + 2) = 1;
  *((_DWORD *)v11 + 3) = 1;
  *(_QWORD *)v11 = &std::_Ref_count_obj2<ClientEndpoint>::`vftable';
  std::_Construct_in_place<ClientEndpoint,unsigned short const * &,Windows::Data::Json::IJsonObject *>(
    (ClientEndpoint *)(v11 + 8),
    v17,
    &v16);
  *(_QWORD *)a1 = v11 + 8;
  *(_QWORD *)(a1 + 8) = v11;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v14);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(&v15);
  std::basic_ostringstream<unsigned short>::`vbase destructor'(v18);
  v12 = (std::_Ref_count_base *)*((_QWORD *)a2 + 1);
  if ( v12 )
    std::_Ref_count_base::_Decref(v12);
  return a1;
}

```

## disassembly

```asm
0x18002d314  mov     [rsp-8+arg_10], rbx
0x18002d319  mov     [rsp-8+arg_18], rsi
0x18002d31e  push    rbp
0x18002d31f  push    rdi
0x18002d320  push    r14
0x18002d322  lea     rbp, [rsp-0A0h]
0x18002d32a  sub     rsp, 1A0h
0x18002d331  mov     rax, cs:__security_cookie
0x18002d338  xor     rax, rsp
0x18002d33b  mov     [rbp+0B0h+var_20], rax
0x18002d342  mov     r14, rdx
0x18002d345  mov     rsi, rcx
0x18002d348  mov     [rsp+1B0h+var_178], rcx
0x18002d34d  mov     [rsp+1B0h+var_168], rdx
0x18002d352  lea     rcx, [rsp+1B0h+var_150]
0x18002d357  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18002d35c  nop
0x18002d35d  lea     rdx, asc_180061254; "{"
0x18002d364  lea     rcx, [rsp+1B0h+var_150]
0x18002d369  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002d36e  lea     rdx, aPartnerTest; "\"Partner\": \"TEST\","
0x18002d375  lea     rcx, [rsp+1B0h+var_150]
0x18002d37a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002d37f  lea     rdx, aFeatureTest; "\"Feature\": \"TEST\","
0x18002d386  lea     rcx, [rsp+1B0h+var_150]
0x18002d38b  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002d390  lea     rdx, aCtacappidTest; "\"CtacAppId\": \"TEST\","
0x18002d397  lea     rcx, [rsp+1B0h+var_150]
0x18002d39c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002d3a1  lea     rdx, aPayload; "\"Payload\": "
0x18002d3a8  lea     rcx, [rsp+1B0h+var_150]
0x18002d3ad  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002d3b2  mov     rcx, [r14]; this
0x18002d3b5  call    ?GetLastTestPayloadHandlerJsonString@ClientState@@QEBAPEBGXZ; ClientState::GetLastTestPayloadHandlerJsonString(void)
0x18002d3ba  mov     rdx, rax
0x18002d3bd  lea     rcx, [rsp+1B0h+var_150]
0x18002d3c2  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002d3c7  lea     rdx, asc_1800612F0; "}"
0x18002d3ce  lea     rcx, [rsp+1B0h+var_150]
0x18002d3d3  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002d3d8  nop
0x18002d3d9  mov     [rsp+1B0h+var_188], 0
0x18002d3e2  mov     [rbp+0B0h+var_48], 0
0x18002d3ea  mov     r9d, 1Ch; unsigned int
0x18002d3f0  lea     r8d, [r9+1]; unsigned int
0x18002d3f4  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18002d3fb  lea     rcx, [rbp+0B0h+hstringHeader]; hstringHeader
0x18002d3ff  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002d404  nop
0x18002d405  lea     r8, [rsp+1B0h+var_188]
0x18002d40a  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x18002d411  mov     rcx, [rbp+0B0h+var_48]
0x18002d415  call    cs:__imp_RoGetActivationFactory
0x18002d41b  mov     rcx, [rbp+0B8h]; this
0x18002d422  test    eax, eax
0x18002d424  jns     short loc_18002D43B
0x18002d426  mov     r9d, eax; char *
0x18002d429  lea     r8, aOnecoreBaseFli; "onecore\\base\\flighting\\onesettings\\"...
0x18002d430  mov     edx, 13Ah; void *
0x18002d435  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002d43b  mov     qword ptr [rsp+1B0h+var_190], 0; int
0x18002d444  mov     rdi, [rsp+1B0h+var_188]
0x18002d449  mov     rax, [rdi]
0x18002d44c  mov     rbx, [rax+30h]
0x18002d450  lea     rcx, [rsp+1B0h+var_190]
0x18002d455  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d45a  lea     rdx, [rbp+0B0h+var_40]
0x18002d45e  lea     rcx, [rsp+1B0h+var_150]
0x18002d463  call    ?str@?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_ostringstream<ushort>::str(void)
0x18002d468  nop
0x18002d469  mov     rcx, rax
0x18002d46c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002d471  mov     [rsp+1B0h+var_180], rax
0x18002d476  lea     rdx, [rsp+1B0h+var_180]
0x18002d47b  lea     rcx, [rbp+0B0h+hstringHeader]
0x18002d47f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002d484  nop
0x18002d485  lea     r8, [rsp+1B0h+var_190]
0x18002d48a  mov     rdx, [rax+18h]
0x18002d48e  mov     rcx, rdi
0x18002d491  mov     rax, rbx
0x18002d494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d499  mov     rcx, [rbp+0B8h]; this
0x18002d4a0  test    eax, eax
0x18002d4a2  jns     short loc_18002D4B9
0x18002d4a4  mov     r9d, eax; char *
0x18002d4a7  lea     r8, aOnecoreBaseFli; "onecore\\base\\flighting\\onesettings\\"...
0x18002d4ae  mov     edx, 13Dh; void *
0x18002d4b3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002d4b9  mov     [rbp+0B0h+var_48], 0
0x18002d4c1  lea     rcx, [rbp+0B0h+var_40]
0x18002d4c5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d4ca  mov     rax, qword ptr [rsp+1B0h+var_190]
0x18002d4cf  mov     [rsp+1B0h+var_180], rax
0x18002d4d4  mov     rcx, [r14]
0x18002d4d7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002d4dc  mov     [rsp+1B0h+var_178], rax
0x18002d4e1  mov     ecx, 0C0h; Size
0x18002d4e6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002d4eb  mov     rdi, rax
0x18002d4ee  mov     [rsp+1B0h+var_160], rax
0x18002d4f3  xorps   xmm0, xmm0
0x18002d4f6  movups  xmmword ptr [rax], xmm0
0x18002d4f9  mov     eax, 1
0x18002d4fe  mov     [rdi+8], eax
0x18002d501  mov     [rdi+0Ch], eax
0x18002d504  lea     rax, ??_7?$_Ref_count_obj2@VClientEndpoint@@@std@@6B@; const std::_Ref_count_obj2<ClientEndpoint>::`vftable'
0x18002d50b  mov     [rdi], rax
0x18002d50e  lea     rbx, [rdi+10h]
0x18002d512  lea     r8, [rsp+1B0h+var_180]
0x18002d517  lea     rdx, [rsp+1B0h+var_178]
0x18002d51c  mov     rcx, rbx
0x18002d51f  call    ??$_Construct_in_place@VClientEndpoint@@AEAPEBGPEAUIJsonObject@Json@Data@Windows@@@std@@YAXAEAVClientEndpoint@@AEAPEBG$$QEAPEAUIJsonObject@Json@Data@Windows@@@Z; std::_Construct_in_place<ClientEndpoint,ushort const * &,Windows::Data::Json::IJsonObject *>(ClientEndpoint &,ushort const * &,Windows::Data::Json::IJsonObject * &&)
0x18002d524  nop
0x18002d525  mov     [rsi], rbx
0x18002d528  mov     [rsi+8], rdi
0x18002d52c  lea     rcx, [rsp+1B0h+var_190]
0x18002d531  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d536  nop
0x18002d537  lea     rcx, [rsp+1B0h+var_188]
0x18002d53c  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x18002d541  nop
0x18002d542  lea     rcx, [rsp+1B0h+var_150]
0x18002d547  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x18002d54c  nop
0x18002d54d  mov     rcx, [r14+8]; this
0x18002d551  test    rcx, rcx
0x18002d554  jz      short loc_18002D55B
0x18002d556  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002d55b  mov     rax, rsi
0x18002d55e  mov     rcx, [rbp+0B0h+var_20]
0x18002d565  xor     rcx, rsp; StackCookie
0x18002d568  call    __security_check_cookie
0x18002d56d  lea     r11, [rsp+1B0h+var_10]
0x18002d575  mov     rbx, [r11+30h]
0x18002d579  mov     rsi, [r11+38h]
0x18002d57d  mov     rsp, r11
0x18002d580  pop     r14
0x18002d582  pop     rdi
0x18002d583  pop     rbp
0x18002d584  retn
```
