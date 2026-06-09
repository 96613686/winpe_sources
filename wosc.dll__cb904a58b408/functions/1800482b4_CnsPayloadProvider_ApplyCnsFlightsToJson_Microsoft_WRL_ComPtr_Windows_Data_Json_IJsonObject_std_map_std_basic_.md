# CnsPayloadProvider::ApplyCnsFlightsToJson(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::shared_ptr<CnsFlightState>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<CnsFlightState>>>>,IPayloadHandler *,bool &,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::shared_ptr<CnsFlightState>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<CnsFlightState>>>> *,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::shared_ptr<CnsFlightState>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<CnsFlightState>>>> *)

- ea: `0x1800482b4`
- end: `0x180048653`
- name: `?ApplyCnsFlightsToJson@CnsPayloadProvider@@CAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@2@@std@@PEAVIPayloadHandler@@AEA_NPEAV56@4@Z`
- size: `927`
- prototype: `__int64 __fastcall(_QWORD *, __int64 **, __int64, _BYTE *, __int64, __int64)`
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180049460`
- `0x180049b18`

## callees

- `0x180003110`
- `0x180005f50`
- `0x180006b9c`
- `0x18000847c`
- `0x180009fcc`
- `0x18000b0bc`
- `0x1800101fc`
- `0x180010278`
- `0x180011a44`
- `0x1800133c4`
- `0x180013620`
- `0x180019e68`
- `0x1800213c0`
- `0x180021f60`
- `0x18002560c`
- `0x180047e24`
- `0x180048230`
- `0x1800482b4`
- `0x180048ab8`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048490`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004854d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048490`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004854d`

## string_xrefs

- `0x180048307`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CnsPayloadProvider::ApplyCnsFlightsToJson(
        _QWORD *a1,
        __int64 **a2,
        __int64 a3,
        _BYTE *a4,
        __int64 a5,
        __int64 a6)
{
  int v9; // eax
  __int64 v10; // rax
  __int64 v11; // rsi
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64, int *); // rbx
  int v14; // eax
  __int64 v16; // rbx
  __int64 v17; // rax
  int CnsFlightVersionFromJson; // eax
  __int64 v19; // r9
  __int64 v20; // rax
  _QWORD *v21; // rax
  HSTRING v22; // rsi
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, HSTRING, __int64 *); // rbx
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v29[2]; // [rsp+20h] [rbp-A9h] BYREF
  __int64 v30; // [rsp+28h] [rbp-A1h] BYREF
  __int64 v31; // [rsp+30h] [rbp-99h] BYREF
  __int64 v32; // [rsp+38h] [rbp-91h] BYREF
  __int64 v33; // [rsp+40h] [rbp-89h] BYREF
  __int64 v34; // [rsp+48h] [rbp-81h] BYREF
  _BYTE v35[8]; // [rsp+50h] [rbp-79h] BYREF
  _BYTE *v36; // [rsp+58h] [rbp-71h]
  _QWORD *v37; // [rsp+60h] [rbp-69h]
  __int64 **v38; // [rsp+68h] [rbp-61h]
  _BYTE v39[16]; // [rsp+70h] [rbp-59h] BYREF
  __int128 v40; // [rsp+80h] [rbp-49h] BYREF
  __int64 v41; // [rsp+90h] [rbp-39h]
  __int64 v42; // [rsp+98h] [rbp-31h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v44; // [rsp+B8h] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+4Fh]

  v36 = a4;
  v37 = a1;
  v38 = a2;
  v33 = 0;
  v44 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v9 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(
         v44,
         &v33);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E0,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\cnspayloadprovider.cpp",
      (const char *)(unsigned int)v9,
      v29[0]);
  v10 = **a2;
  v34 = v10;
  while ( !*(_BYTE *)(v10 + 25) )
  {
    v11 = v10 + 32;
    *(_QWORD *)v29 = 0;
    v31 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v10 + 32);
    Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v31);
    v12 = *a1;
    v13 = *(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)*a1 + 64LL);
    wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::reset(v29);
    v14 = v13(v12, v44, v29);
    if ( (int)(v14 + 0x80000000) >= 0 && v14 != -2089484279 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1E7,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\cnspayloadprovider.cpp",
        (const char *)(unsigned int)v14,
        v29[0]);
    v16 = v11 + 32;
    if ( v14 >= 0 )
    {
      v40 = 0;
      v41 = 0;
      v42 = 7;
      LOWORD(v40) = 0;
      v17 = wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(
              v35,
              v29);
      CnsFlightVersionFromJson = CnsPayloadProvider::GetCnsFlightVersionFromJson(v17, &v40);
      if ( CnsFlightVersionFromJson < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1EB,
          (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\cnspayloadprovider.cpp",
          (const char *)(unsigned int)CnsFlightVersionFromJson,
          v29[0]);
      v19 = -1;
      do
        ++v19;
      while ( *(_WORD *)(**(_QWORD **)v16 + 2 * v19) );
      v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v40);
      if ( (int)std::_Traits_compare<std::char_traits<unsigned short>>(v20, v41) >= 0 )
      {
        if ( a6 )
        {
          v21 = (_QWORD *)std::map<std::wstring,std::shared_ptr<CnsFlightState>>::_Try_emplace<std::wstring const &,>(
                            a6,
                            v39,
                            v11);
          std::shared_ptr<CnsFlightState>::operator=(*v21 + 64LL, v11 + 32);
        }
        std::wstring::_Tidy_deallocate(&v40);
        goto LABEL_23;
      }
      std::wstring::_Tidy_deallocate(&v40);
    }
    v31 = 0;
    v22 = (HSTRING)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a3 + 96LL))(
                     a3,
                     *(_QWORD *)(*(_QWORD *)v16 + 40LL));
    WindowsDeleteString(0);
    v31 = (__int64)v22;
    if ( !v22 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1FA,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\cnspayloadprovider.cpp",
        (const char *)0x8000FFFFLL,
        v29[0]);
    v30 = 0;
    v23 = v33;
    v24 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v33 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
    v25 = v24(v23, v22, &v30);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1FC,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\cnspayloadprovider.cpp",
        (const char *)(unsigned int)v25,
        v29[0]);
    v32 = 0;
    v26 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(&v30, &v32);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1FE,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\cnspayloadprovider.cpp",
        (const char *)(unsigned int)v26,
        v29[0]);
    v27 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*a1 + 56LL))(*a1, v44, v32);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1FF,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\cnspayloadprovider.cpp",
        (const char *)(unsigned int)v27,
        v29[0]);
    *v36 = 1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
    WindowsDeleteString(v22);
LABEL_23:
    v44 = 0;
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(v29);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>>,std::_Iterator_base0>::operator++(&v34);
    v10 = v34;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>,void *>>>(
    a2,
    a2);
  return 0;
}

```

## disassembly

```asm
0x1800482b4  push    rbp
0x1800482b6  push    rbx
0x1800482b7  push    rsi
0x1800482b8  push    rdi
0x1800482b9  push    r12
0x1800482bb  push    r13
0x1800482bd  push    r14
0x1800482bf  push    r15
0x1800482c1  lea     rbp, [rsp-0Fh]
0x1800482c6  sub     rsp, 0D8h
0x1800482cd  mov     rax, cs:__security_cookie
0x1800482d4  xor     rax, rsp
0x1800482d7  mov     [rbp+47h+var_50], rax
0x1800482db  mov     [rbp+47h+var_B8], r9
0x1800482df  mov     r13, r8
0x1800482e2  mov     r14, rdx
0x1800482e5  mov     r15, rcx
0x1800482e8  mov     [rbp+47h+var_B0], rcx
0x1800482ec  mov     [rbp+47h+var_A8], rdx
0x1800482f0  mov     r12, [rbp+47h+arg_28]
0x1800482f4  xor     edi, edi
0x1800482f6  mov     [rsp+110h+var_D0], rdi
0x1800482fb  mov     [rbp+47h+var_58], rdi
0x1800482ff  lea     r9d, [rdi+1Ch]; unsigned int
0x180048303  lea     r8d, [rdi+1Dh]; unsigned int
0x180048307  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18004830e  lea     rcx, [rbp+47h+hstringHeader]; hstringHeader
0x180048312  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180048317  nop
0x180048318  lea     rdx, [rsp+110h+var_D0]
0x18004831d  mov     rcx, [rbp+47h+var_58]
0x180048321  call    ??$GetActivationFactory@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>)
0x180048326  mov     rcx, [rbp+4Fh]; this
0x18004832a  test    eax, eax
0x18004832c  js      loc_1800485CF
0x180048332  mov     rax, [r14]
0x180048335  mov     rax, [rax]
0x180048338  mov     [rsp+110h+var_C8], rax
0x18004833d  cmp     [rax+19h], dil
0x180048341  jnz     loc_180048576
0x180048347  lea     rsi, [rax+20h]
0x18004834b  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x180048350  mov     rcx, rsi
0x180048353  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180048358  mov     [rsp+110h+var_E0], rax
0x18004835d  lea     rdx, [rsp+110h+var_E0]
0x180048362  lea     rcx, [rbp+47h+hstringHeader]
0x180048366  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004836b  nop
0x18004836c  mov     rdi, [r15]
0x18004836f  mov     rax, [rdi]
0x180048372  mov     rbx, [rax+40h]
0x180048376  lea     rcx, [rsp+110h+var_F0]
0x18004837b  call    ?reset@?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::reset(void)
0x180048380  lea     r8, [rsp+110h+var_F0]
0x180048385  mov     rdx, [rbp+47h+var_58]
0x180048389  mov     rcx, rdi
0x18004838c  mov     rax, rbx
0x18004838f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048394  mov     edx, 80000000h
0x180048399  lea     ecx, [rax+rdx]
0x18004839c  test    edx, ecx
0x18004839e  jnz     short loc_1800483AD
0x1800483a0  cmp     eax, 83750009h
0x1800483a5  jz      short loc_1800483AD
0x1800483a7  mov     cl, 1
0x1800483a9  xor     edi, edi
0x1800483ab  jmp     short loc_1800483B2
0x1800483ad  xor     edi, edi
0x1800483af  mov     cl, dil
0x1800483b2  mov     r10, [rbp+4Fh]
0x1800483b6  test    cl, cl
0x1800483b8  jnz     loc_1800485B7
0x1800483be  lea     rbx, [rsi+20h]
0x1800483c2  test    eax, eax
0x1800483c4  js      loc_18004846F
0x1800483ca  xorps   xmm0, xmm0
0x1800483cd  movups  [rbp+47h+var_90], xmm0
0x1800483d1  mov     [rbp+47h+var_80], rdi
0x1800483d5  mov     [rbp+47h+var_78], 7
0x1800483dd  mov     word ptr [rbp+47h+var_90], di
0x1800483e1  lea     rdx, [rsp+110h+var_F0]
0x1800483e6  lea     rcx, [rbp+47h+var_C0]
0x1800483ea  call    ??0?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy> const &)
0x1800483ef  lea     rdx, [rbp+47h+var_90]
0x1800483f3  mov     rcx, rax
0x1800483f6  call    ?GetCnsFlightVersionFromJson@CnsPayloadProvider@@CAJV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CnsPayloadProvider::GetCnsFlightVersionFromJson(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>,std::wstring &)
0x1800483fb  mov     rcx, [rbp+4Fh]; this
0x1800483ff  test    eax, eax
0x180048401  js      loc_1800485E4
0x180048407  mov     rax, [rbx]
0x18004840a  mov     r8, [rax]
0x18004840d  or      r9, 0FFFFFFFFFFFFFFFFh
0x180048411  inc     r9
0x180048414  cmp     [r8+r9*2], di
0x180048419  jnz     short loc_180048411
0x18004841b  lea     rcx, [rbp+47h+var_90]
0x18004841f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180048424  mov     rcx, rax
0x180048427  mov     rdx, [rbp+47h+var_80]
0x18004842b  call    ??$_Traits_compare@U?$char_traits@G@std@@@std@@YAHQEBG_K01@Z; std::_Traits_compare<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180048430  test    eax, eax
0x180048432  js      short loc_180048466
0x180048434  test    r12, r12
0x180048437  jz      short loc_180048458
0x180048439  mov     r8, rsi
0x18004843c  lea     rdx, [rbp+47h+var_A0]
0x180048440  mov     rcx, r12
0x180048443  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::shared_ptr<CnsFlightState>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180048448  mov     rcx, [rax]
0x18004844b  add     rcx, 40h ; '@'
0x18004844f  mov     rdx, rbx
0x180048452  call    ??4?$shared_ptr@UCnsFlightState@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<CnsFlightState>::operator=(std::shared_ptr<CnsFlightState> const &)
0x180048457  nop
0x180048458  lea     rcx, [rbp+47h+var_90]
0x18004845c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048461  jmp     loc_180048554
0x180048466  lea     rcx, [rbp+47h+var_90]
0x18004846a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004846f  mov     [rsp+110h+var_E0], rdi
0x180048474  mov     rax, [r13+0]
0x180048478  mov     rdx, [rbx]
0x18004847b  mov     rdx, [rdx+28h]
0x18004847f  mov     rcx, r13
0x180048482  mov     rax, [rax+60h]
0x180048486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004848b  mov     rsi, rax
0x18004848e  xor     ecx, ecx; string
0x180048490  call    cs:__imp_WindowsDeleteString
0x180048496  mov     [rsp+110h+var_E0], rsi
0x18004849b  test    rsi, rsi
0x18004849e  setz    cl
0x1800484a1  mov     rax, [rbp+4Fh]
0x1800484a5  test    cl, cl
0x1800484a7  jnz     loc_180048638
0x1800484ad  mov     [rsp+110h+var_E8], rdi
0x1800484b2  mov     rdi, [rsp+110h+var_D0]
0x1800484b7  mov     rcx, [rdi]
0x1800484ba  mov     rbx, [rcx+30h]
0x1800484be  lea     rcx, [rsp+110h+var_E8]
0x1800484c3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800484c8  lea     r8, [rsp+110h+var_E8]
0x1800484cd  mov     rdx, rsi
0x1800484d0  mov     rcx, rdi
0x1800484d3  mov     rax, rbx
0x1800484d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800484db  mov     rcx, [rbp+4Fh]; this
0x1800484df  xor     edi, edi
0x1800484e1  test    eax, eax
0x1800484e3  js      loc_180048623
0x1800484e9  mov     [rsp+110h+var_D8], rdi
0x1800484ee  lea     rdx, [rsp+110h+var_D8]
0x1800484f3  lea     rcx, [rsp+110h+var_E8]
0x1800484f8  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x1800484fd  mov     rcx, [rbp+4Fh]; this
0x180048501  test    eax, eax
0x180048503  js      loc_18004860E
0x180048509  mov     rcx, [r15]
0x18004850c  mov     rax, [rcx]
0x18004850f  mov     r8, [rsp+110h+var_D8]
0x180048514  mov     rdx, [rbp+47h+var_58]
0x180048518  mov     rax, [rax+38h]
0x18004851c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048521  mov     rcx, [rbp+4Fh]; this
0x180048525  test    eax, eax
0x180048527  js      loc_1800485F9
0x18004852d  mov     rax, [rbp+47h+var_B8]
0x180048531  mov     byte ptr [rax], 1
0x180048534  lea     rcx, [rsp+110h+var_D8]
0x180048539  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004853e  nop
0x18004853f  lea     rcx, [rsp+110h+var_E8]
0x180048544  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048549  nop
0x18004854a  mov     rcx, rsi; string
0x18004854d  call    cs:__imp_WindowsDeleteString
0x180048553  nop
0x180048554  mov     [rbp+47h+var_58], rdi
0x180048558  lea     rcx, [rsp+110h+var_F0]
0x18004855d  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x180048562  lea     rcx, [rsp+110h+var_C8]
0x180048567  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>>,std::_Iterator_base0>::operator++(void)
0x18004856c  mov     rax, [rsp+110h+var_C8]
0x180048571  jmp     loc_18004833D
0x180048576  lea     rcx, [rsp+110h+var_D0]
0x18004857b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048580  nop
0x180048581  mov     rcx, r15
0x180048584  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048589  nop
0x18004858a  mov     rdx, r14
0x18004858d  mov     rcx, r14
0x180048590  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>,void *>> &)
0x180048595  xor     eax, eax
0x180048597  mov     rcx, [rbp+47h+var_50]
0x18004859b  xor     rcx, rsp; StackCookie
0x18004859e  call    __security_check_cookie
0x1800485a3  add     rsp, 0D8h
0x1800485aa  pop     r15
0x1800485ac  pop     r14
0x1800485ae  pop     r13
0x1800485b0  pop     r12
0x1800485b2  pop     rdi
0x1800485b3  pop     rsi
0x1800485b4  pop     rbx
0x1800485b5  pop     rbp
0x1800485b6  retn
0x1800485b7  mov     r9d, eax; char *
0x1800485ba  lea     r8, aOnecoreBaseFli_38; "onecore\\base\\flighting\\onesettings\\"...
0x1800485c1  mov     edx, 1E7h; void *
0x1800485c6  mov     rcx, r10; this
0x1800485c9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800485cf  mov     r9d, eax; char *
0x1800485d2  lea     r8, aOnecoreBaseFli_38; "onecore\\base\\flighting\\onesettings\\"...
0x1800485d9  mov     edx, 1E0h; void *
0x1800485de  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800485e4  mov     r9d, eax; char *
0x1800485e7  lea     r8, aOnecoreBaseFli_38; "onecore\\base\\flighting\\onesettings\\"...
0x1800485ee  mov     edx, 1EBh; void *
0x1800485f3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800485f9  mov     r9d, eax; char *
0x1800485fc  lea     r8, aOnecoreBaseFli_38; "onecore\\base\\flighting\\onesettings\\"...
0x180048603  mov     edx, 1FFh; void *
0x180048608  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004860e  mov     r9d, eax; char *
0x180048611  lea     r8, aOnecoreBaseFli_38; "onecore\\base\\flighting\\onesettings\\"...
0x180048618  mov     edx, 1FEh; void *
0x18004861d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048623  mov     r9d, eax; char *
0x180048626  lea     r8, aOnecoreBaseFli_38; "onecore\\base\\flighting\\onesettings\\"...
0x18004862d  mov     edx, 1FCh; void *
0x180048632  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048638  mov     r9d, 8000FFFFh; char *
0x18004863e  lea     r8, aOnecoreBaseFli_38; "onecore\\base\\flighting\\onesettings\\"...
0x180048645  mov     edx, 1FAh; void *
0x18004864a  mov     rcx, rax; this
0x18004864d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
