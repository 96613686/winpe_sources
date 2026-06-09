# GetFlightIdsFromPayload(char const *)

- ea: `0x180041f84`
- end: `0x1800423fb`
- name: `?GetFlightIdsFromPayload@@YA?AV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBD@Z`
- size: `1143`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800425f8`

## callees

- `0x180003110`
- `0x180006b9c`
- `0x180009b4c`
- `0x180009fcc`
- `0x18000a798`
- `0x18000a8f8`
- `0x18000a964`
- `0x18000b0bc`
- `0x1800101fc`
- `0x180010278`
- `0x180011a44`
- `0x180014928`
- `0x180014b60`
- `0x180014da4`
- `0x180019e68`
- `0x180021a84`
- `0x180021ad8`
- `0x180021c88`
- `0x18004184c`
- `0x180041b34`
- `0x180041f84`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042283`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800422f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042283`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800422f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800422c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800422c3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180042003`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180042003`

## string_xrefs

- `0x180041fe2`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall GetFlightIdsFromPayload(__int64 a1, __int64 a2, __int64 a3)
{
  int ActivationFactory; // eax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v8; // rax
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64, _QWORD); // rbx
  unsigned int v12; // eax
  char v13; // cl
  __int64 (__fastcall **v14)(_QWORD, GUID *, __int64 *); // rax
  int v15; // eax
  __int64 **v16; // rax
  __int64 *v17; // rcx
  __int64 v18; // rax
  int v19; // eax
  int v20; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, int *); // rbx
  int v23; // eax
  __int64 v24; // rdi
  void (__fastcall *v25)(__int64, PVOID, HSTRING *); // rbx
  HSTRING_HEADER *v26; // rax
  HSTRING v27; // rcx
  PCWSTR StringRawBuffer; // rax
  int v30[2]; // [rsp+20h] [rbp-E0h] BYREF
  int v31; // [rsp+28h] [rbp-D8h] BYREF
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v33; // [rsp+38h] [rbp-C8h] BYREF
  __int64 (__fastcall ***v34)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v36; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v37[2]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v38[16]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v39; // [rsp+78h] [rbp-88h] BYREF
  int v40; // [rsp+80h] [rbp-80h]
  _BYTE v41[16]; // [rsp+90h] [rbp-70h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v43; // [rsp+B8h] [rbp-48h]
  _BYTE v44[32]; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING_HEADER v45; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v46[128]; // [rsp+100h] [rbp+0h] BYREF
  HSTRING_HEADER v47; // [rsp+180h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v36 = a1;
  if ( a2 )
  {
    v36 = 0;
    v43 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonObject",
      0x1Du,
      0x1Cu);
    ActivationFactory = RoGetActivationFactory(v43, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v36);
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1E,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\payloadhandlershared.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v30[0]);
    std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v46);
    std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::from_bytes(
      v46,
      v44,
      a2);
    v35 = 0;
    v6 = v36;
    v7 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v36 + 48LL);
    wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::reset(&v35);
    *(_QWORD *)v30 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v44);
    v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v45, (const WCHAR **)v30);
    v9 = v7(v6, v8[1].Reserved.Reserved1, &v35);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x25,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\payloadhandlershared.cpp",
        (const char *)(unsigned int)v9,
        v30[0]);
    v34 = 0;
    v10 = v35;
    v11 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v35 + 64LL);
    wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::reset(&v34);
    v43 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"settings", 9u, 8u);
    v12 = v11(v10, v43, &v34);
    if ( (int)(v12 + 0x80000000) < 0 || (v13 = 1, v12 == -2089484279) )
      v13 = 0;
    if ( v13 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x29,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\payloadhandlershared.cpp",
        (const char *)v12,
        v30[0]);
    if ( v12 == -2089484279 )
    {
      std::set<std::wstring>::set<std::wstring>(a1, 0x80000000LL, 2205483017LL);
    }
    else
    {
      std::set<std::wstring>::set<std::wstring>(v38, 0x80000000LL, 2205483017LL);
      v37[0] = 0;
      v14 = *v34;
      v37[0] = 0;
      v15 = (*v14)(v34, &GUID_dfabb6e1_0411_5a8f_aa87_354e7110f099, v37);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x32,
          (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\payloadhandlershared.cpp",
          (const char *)(unsigned int)v15,
          v30[0]);
      wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::iterable_iterator(
        &v39,
        v37[0]);
      hstringHeader.Reserved.Reserved1 = 0;
      *(_DWORD *)&hstringHeader.Reserved.Reserved2[8] = -1;
      *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
      while ( v40 != -1 )
      {
        v16 = (__int64 **)wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::operator*(&v39);
        v33 = 0;
        v17 = *v16;
        v18 = **v16;
        v33 = 0;
        v19 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v18 + 56))(v17, &v33);
        if ( v19 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x37,
            (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\payloadhandlershared.cpp",
            (const char *)(unsigned int)v19,
            v30[0]);
        v31 = 0;
        v20 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v33 + 48LL))(v33, &v31);
        if ( v20 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x3A,
            (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\payloadhandlershared.cpp",
            (const char *)(unsigned int)v20,
            v30[0]);
        if ( v31 == 5 )
        {
          *(_QWORD *)v30 = 0;
          v21 = v33;
          v22 = *(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v33 + 96LL);
          wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::reset(v30);
          v23 = v22(v21, v30);
          if ( v23 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x3F,
              (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\payloadhandlershared.cpp",
              (const char *)(unsigned int)v23,
              v30[0]);
          string = 0;
          v24 = *(_QWORD *)v30;
          v25 = *(void (__fastcall **)(__int64, PVOID, HSTRING *))(**(_QWORD **)v30 + 80LL);
          WindowsDeleteString(0);
          string = 0;
          v26 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v47, (const WCHAR **)&off_18005BE68);
          v25(v24, v26[1].Reserved.Reserved1, &string);
          v27 = string;
          if ( string )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
            std::wstring::wstring((__int64)&v45, (__int64)StringRawBuffer);
            std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(
              v38,
              v41,
              &v45);
            std::wstring::_Tidy_deallocate(&v45);
            v27 = string;
          }
          WindowsDeleteString(v27);
          string = 0;
          wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>((__int64 *)v30);
        }
        wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(&v33);
        wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::operator++(&v39);
      }
      wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator((__int64)&hstringHeader);
      wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator((__int64)&v39);
      std::set<std::wstring>::set<std::wstring>(a1, v38);
      wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(v37);
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v38);
    }
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>((__int64 *)&v34);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(&v35);
    std::wstring::_Tidy_deallocate(v44);
    std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v46);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(&v36);
  }
  else
  {
    std::set<std::wstring>::set<std::wstring>(a1, 0, a3);
  }
  return a1;
}

```

## disassembly

```asm
0x180041f84  mov     [rsp-8+arg_10], rbx
0x180041f89  mov     [rsp-8+arg_18], rsi
0x180041f8e  push    rbp
0x180041f8f  push    rdi
0x180041f90  push    r14
0x180041f92  lea     rbp, [rsp-0B0h]
0x180041f9a  sub     rsp, 1B0h
0x180041fa1  mov     rax, cs:__security_cookie
0x180041fa8  xor     rax, rsp
0x180041fab  mov     [rbp+0C0h+var_20], rax
0x180041fb2  mov     rbx, rdx
0x180041fb5  mov     rsi, rcx
0x180041fb8  mov     [rsp+1C0h+var_170], rcx
0x180041fbd  xor     r14d, r14d
0x180041fc0  test    rdx, rdx
0x180041fc3  jnz     short loc_180041FCF
0x180041fc5  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x180041fca  jmp     loc_1800423D1
0x180041fcf  mov     [rsp+1C0h+var_170], r14
0x180041fd4  mov     [rbp+0C0h+var_108], r14
0x180041fd8  mov     r9d, 1Ch; unsigned int
0x180041fde  lea     r8d, [r9+1]; unsigned int
0x180041fe2  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180041fe9  lea     rcx, [rbp+0C0h+hstringHeader]; hstringHeader
0x180041fed  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180041ff2  nop
0x180041ff3  lea     r8, [rsp+1C0h+var_170]
0x180041ff8  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x180041fff  mov     rcx, [rbp+0C0h+var_108]
0x180042003  call    cs:__imp_RoGetActivationFactory
0x180042009  mov     rcx, [rbp+0C8h]; this
0x180042010  test    eax, eax
0x180042012  jns     short loc_180042029
0x180042014  mov     r9d, eax; char *
0x180042017  lea     r8, aOnecoreBaseFli_3; "onecore\\base\\flighting\\onesettings\\"...
0x18004201e  mov     edx, 1Eh; void *
0x180042023  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180042029  lea     rcx, [rbp+0C0h+var_C0]
0x18004202d  call    ??0?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x180042032  nop
0x180042033  mov     r8, rbx
0x180042036  lea     rdx, [rbp+0C0h+var_100]
0x18004203a  lea     rcx, [rbp+0C0h+var_C0]
0x18004203e  call    ?from_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@PEBD@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::from_bytes(char const *)
0x180042043  nop
0x180042044  mov     [rsp+1C0h+var_178], r14
0x180042049  mov     rdi, [rsp+1C0h+var_170]
0x18004204e  mov     rax, [rdi]
0x180042051  mov     rbx, [rax+30h]
0x180042055  lea     rcx, [rsp+1C0h+var_178]
0x18004205a  call    ?reset@?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::reset(void)
0x18004205f  lea     rcx, [rbp+0C0h+var_100]
0x180042063  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180042068  mov     qword ptr [rsp+1C0h+var_1A0], rax; int
0x18004206d  lea     rdx, [rsp+1C0h+var_1A0]
0x180042072  lea     rcx, [rbp+0C0h+var_E0]
0x180042076  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004207b  nop
0x18004207c  lea     r8, [rsp+1C0h+var_178]
0x180042081  mov     rdx, [rax+18h]
0x180042085  mov     rcx, rdi
0x180042088  mov     rax, rbx
0x18004208b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042090  mov     rcx, [rbp+0C8h]; this
0x180042097  test    eax, eax
0x180042099  jns     short loc_1800420B0
0x18004209b  mov     r9d, eax; char *
0x18004209e  lea     r8, aOnecoreBaseFli_3; "onecore\\base\\flighting\\onesettings\\"...
0x1800420a5  mov     edx, 25h ; '%'; void *
0x1800420aa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800420b0  mov     [rsp+1C0h+var_180], r14
0x1800420b5  mov     rdi, [rsp+1C0h+var_178]
0x1800420ba  mov     rax, [rdi]
0x1800420bd  mov     rbx, [rax+40h]
0x1800420c1  lea     rcx, [rsp+1C0h+var_180]
0x1800420c6  call    ?reset@?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::reset(void)
0x1800420cb  mov     [rbp+0C0h+var_108], r14
0x1800420cf  mov     r9d, 8; unsigned int
0x1800420d5  lea     r8d, [r9+1]; unsigned int
0x1800420d9  lea     rdx, aSettings; "settings"
0x1800420e0  lea     rcx, [rbp+0C0h+hstringHeader]; hstringHeader
0x1800420e4  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800420e9  nop
0x1800420ea  lea     r8, [rsp+1C0h+var_180]
0x1800420ef  mov     rdx, [rbp+0C0h+var_108]
0x1800420f3  mov     rcx, rdi
0x1800420f6  mov     rax, rbx
0x1800420f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800420fe  nop
0x1800420ff  mov     edx, 80000000h
0x180042104  lea     ecx, [rax+rdx]
0x180042107  mov     r8d, 83750009h
0x18004210d  test    edx, ecx
0x18004210f  jnz     short loc_180042118
0x180042111  cmp     eax, r8d
0x180042114  mov     cl, 1
0x180042116  jnz     short loc_18004211B
0x180042118  mov     cl, r14b
0x18004211b  mov     r10, [rbp+0C8h]
0x180042122  test    cl, cl
0x180042124  jz      short loc_18004213E
0x180042126  mov     r9d, eax; char *
0x180042129  lea     r8, aOnecoreBaseFli_3; "onecore\\base\\flighting\\onesettings\\"...
0x180042130  mov     edx, 29h ; ')'; void *
0x180042135  mov     rcx, r10; this
0x180042138  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004213e  cmp     eax, r8d
0x180042141  jnz     short loc_180042150
0x180042143  mov     rcx, rsi
0x180042146  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x18004214b  jmp     loc_18004239D
0x180042150  lea     rcx, [rsp+1C0h+var_158]
0x180042155  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x18004215a  nop
0x18004215b  mov     [rsp+1C0h+var_168], r14
0x180042160  mov     rcx, [rsp+1C0h+var_180]
0x180042165  mov     rax, [rcx]
0x180042168  mov     [rsp+1C0h+var_168], r14
0x18004216d  lea     r8, [rsp+1C0h+var_168]
0x180042172  lea     rdx, _GUID_dfabb6e1_0411_5a8f_aa87_354e7110f099
0x180042179  mov     rax, [rax]
0x18004217c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042181  mov     rcx, [rbp+0C8h]; this
0x180042188  test    eax, eax
0x18004218a  jns     short loc_1800421A1
0x18004218c  mov     r9d, eax; char *
0x18004218f  lea     r8, aOnecoreBaseFli_3; "onecore\\base\\flighting\\onesettings\\"...
0x180042196  mov     edx, 32h ; '2'; void *
0x18004219b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800421a1  mov     rdx, [rsp+1C0h+var_168]
0x1800421a6  lea     rcx, [rsp+1C0h+var_148]
0x1800421ab  call    ??0iterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAU?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@Z; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::iterable_iterator(Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *> *)
0x1800421b0  nop
0x1800421b1  mov     qword ptr [rbp+0C0h+hstringHeader.Reserved], r14
0x1800421b5  mov     dword ptr [rbp+0C0h+hstringHeader.Reserved+8], 0FFFFFFFFh
0x1800421bc  mov     qword ptr [rbp+0C0h+hstringHeader.Reserved+10h], r14
0x1800421c0  cmp     [rbp+0C0h+var_140], 0FFFFFFFFh
0x1800421c4  jz      loc_180042365
0x1800421ca  lea     rcx, [rsp+1C0h+var_148]
0x1800421cf  call    ??Diterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEBV?$ComPtr@U?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::operator*(void)
0x1800421d4  mov     [rsp+1C0h+var_188], r14
0x1800421d9  mov     rcx, [rax]
0x1800421dc  mov     rax, [rcx]
0x1800421df  mov     [rsp+1C0h+var_188], r14
0x1800421e4  lea     rdx, [rsp+1C0h+var_188]
0x1800421e9  mov     rax, [rax+38h]
0x1800421ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800421f2  mov     rcx, [rbp+0C8h]; this
0x1800421f9  test    eax, eax
0x1800421fb  js      loc_180042350
0x180042201  mov     [rsp+1C0h+var_198], r14d
0x180042206  mov     rcx, [rsp+1C0h+var_188]
0x18004220b  mov     rax, [rcx]
0x18004220e  lea     rdx, [rsp+1C0h+var_198]
0x180042213  mov     rax, [rax+30h]
0x180042217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004221c  mov     rcx, [rbp+0C8h]; this
0x180042223  test    eax, eax
0x180042225  js      loc_18004233B
0x18004222b  cmp     [rsp+1C0h+var_198], 5
0x180042230  jnz     loc_18004230D
0x180042236  mov     qword ptr [rsp+1C0h+var_1A0], r14; int
0x18004223b  mov     rdi, [rsp+1C0h+var_188]
0x180042240  mov     rax, [rdi]
0x180042243  mov     rbx, [rax+60h]
0x180042247  lea     rcx, [rsp+1C0h+var_1A0]
0x18004224c  call    ?reset@?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::reset(void)
0x180042251  lea     rdx, [rsp+1C0h+var_1A0]
0x180042256  mov     rcx, rdi
0x180042259  mov     rax, rbx
0x18004225c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042261  mov     rcx, [rbp+0C8h]; this
0x180042268  test    eax, eax
0x18004226a  js      loc_180042326
0x180042270  mov     [rsp+1C0h+string], r14
0x180042275  mov     rdi, qword ptr [rsp+1C0h+var_1A0]
0x18004227a  mov     rax, [rdi]
0x18004227d  mov     rbx, [rax+50h]
0x180042281  xor     ecx, ecx; string
0x180042283  call    cs:__imp_WindowsDeleteString
0x180042289  mov     [rsp+1C0h+string], r14
0x18004228e  lea     rdx, off_18005BE68; "__flightId"
0x180042295  lea     rcx, [rbp+0C0h+var_40]
0x18004229c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800422a1  nop
0x1800422a2  lea     r8, [rsp+1C0h+string]
0x1800422a7  mov     rdx, [rax+18h]
0x1800422ab  mov     rcx, rdi
0x1800422ae  mov     rax, rbx
0x1800422b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800422b6  nop
0x1800422b7  mov     rcx, [rsp+1C0h+string]; string
0x1800422bc  test    rcx, rcx
0x1800422bf  jz      short loc_1800422F7
0x1800422c1  xor     edx, edx; length
0x1800422c3  call    cs:__imp_WindowsGetStringRawBuffer
0x1800422c9  mov     rdx, rax
0x1800422cc  lea     rcx, [rbp+0C0h+var_E0]
0x1800422d0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800422d5  nop
0x1800422d6  lea     r8, [rbp+0C0h+var_E0]
0x1800422da  lea     rdx, [rbp+0C0h+var_130]
0x1800422de  lea     rcx, [rsp+1C0h+var_158]
0x1800422e3  call    ??$_Emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(std::wstring &&)
0x1800422e8  nop
0x1800422e9  lea     rcx, [rbp+0C0h+var_E0]
0x1800422ed  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800422f2  mov     rcx, [rsp+1C0h+string]; string
0x1800422f7  call    cs:__imp_WindowsDeleteString
0x1800422fd  mov     [rsp+1C0h+string], r14
0x180042302  lea     rcx, [rsp+1C0h+var_1A0]
0x180042307  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x18004230c  nop
0x18004230d  lea     rcx, [rsp+1C0h+var_188]
0x180042312  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x180042317  lea     rcx, [rsp+1C0h+var_148]
0x18004231c  call    ??Eiterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV012@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::operator++(void)
0x180042321  jmp     loc_1800421C0
0x180042326  mov     r9d, eax; char *
0x180042329  lea     r8, aOnecoreBaseFli_3; "onecore\\base\\flighting\\onesettings\\"...
0x180042330  mov     edx, 3Fh ; '?'; void *
0x180042335  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004233b  mov     r9d, eax; char *
0x18004233e  lea     r8, aOnecoreBaseFli_3; "onecore\\base\\flighting\\onesettings\\"...
0x180042345  mov     edx, 3Ah ; ':'; void *
0x18004234a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180042350  mov     r9d, eax; char *
0x180042353  lea     r8, aOnecoreBaseFli_3; "onecore\\base\\flighting\\onesettings\\"...
0x18004235a  mov     edx, 37h ; '7'; void *
0x18004235f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180042365  lea     rcx, [rbp+0C0h+hstringHeader]
0x180042369  call    ??1iterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(void)
0x18004236e  nop
0x18004236f  lea     rcx, [rsp+1C0h+var_148]
0x180042374  call    ??1iterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(void)
0x180042379  lea     rdx, [rsp+1C0h+var_158]
0x18004237e  mov     rcx, rsi
0x180042381  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@$$QEAV01@@Z; std::set<std::wstring>::set<std::wstring>(std::set<std::wstring> &&)
0x180042386  nop
0x180042387  lea     rcx, [rsp+1C0h+var_168]
0x18004238c  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x180042391  nop
0x180042392  lea     rcx, [rsp+1C0h+var_158]
0x180042397  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18004239c  nop
0x18004239d  lea     rcx, [rsp+1C0h+var_180]
0x1800423a2  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x1800423a7  nop
0x1800423a8  lea     rcx, [rsp+1C0h+var_178]
0x1800423ad  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x1800423b2  nop
0x1800423b3  lea     rcx, [rbp+0C0h+var_100]
0x1800423b7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800423bc  nop
0x1800423bd  lea     rcx, [rbp+0C0h+var_C0]
0x1800423c1  call    ??1?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1800423c6  nop
0x1800423c7  lea     rcx, [rsp+1C0h+var_170]
0x1800423cc  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x1800423d1  mov     rax, rsi
0x1800423d4  mov     rcx, [rbp+0C0h+var_20]
0x1800423db  xor     rcx, rsp; StackCookie
0x1800423de  call    __security_check_cookie
0x1800423e3  lea     r11, [rsp+1C0h+var_10]
0x1800423eb  mov     rbx, [r11+30h]
0x1800423ef  mov     rsi, [r11+38h]
0x1800423f3  mov     rsp, r11
0x1800423f6  pop     r14
0x1800423f8  pop     rdi
0x1800423f9  pop     rbp
0x1800423fa  retn
```
