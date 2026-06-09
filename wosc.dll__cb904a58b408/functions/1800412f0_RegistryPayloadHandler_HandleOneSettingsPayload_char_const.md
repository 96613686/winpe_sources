# RegistryPayloadHandler::HandleOneSettingsPayload(char const *)

- ea: `0x1800412f0`
- end: `0x1800415d5`
- name: `?HandleOneSettingsPayload@RegistryPayloadHandler@@UEAAXPEBD@Z`
- size: `741`
- prototype: `void __fastcall(RegistryPayloadHandler *__hidden this, const char *)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003110`
- `0x180005f50`
- `0x180006b9c`
- `0x18000b0bc`
- `0x1800101fc`
- `0x180010278`
- `0x180013374`
- `0x180013620`
- `0x180014b60`
- `0x180014da4`
- `0x180019e68`
- `0x18002e830`
- `0x180040570`
- `0x18004057c`
- `0x180040a40`
- `0x1800412f0`
- `0x18004184c`
- `0x1800425f8`
- `0x180059010`

## string_xrefs

- `0x180041340`: `Windows.Data.Json.JsonObject`
- `0x18004136b`: `onecore\base\flighting\onesettings\libs\payloadhandlers\registrypayloadhandler.cpp`
- `0x1800413f7`: `onecore\base\flighting\onesettings\libs\payloadhandlers\registrypayloadhandler.cpp`
- `0x18004149b`: `onecore\base\flighting\onesettings\libs\payloadhandlers\registrypayloadhandler.cpp`
- `0x180041504`: `onecore\base\flighting\onesettings\libs\payloadhandlers\registrypayloadhandler.cpp`
- `0x180041544`: `onecore\base\flighting\onesettings\libs\payloadhandlers\registrypayloadhandler.cpp`

## pseudocode

```c
void __fastcall RegistryPayloadHandler::HandleOneSettingsPayload(RegistryPayloadHandler *this, const char *a2)
{
  __int64 v4; // rax
  int v5; // eax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, __int64 *); // rbx
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64, int *); // rbx
  int v12; // eax
  int v13; // eax
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rax
  __int64 v17; // r9
  int v18[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v19; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v21; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v22[3]; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+70h] [rbp-90h]
  _BYTE v25[40]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v26[128]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v4 = 0;
  *(_QWORD *)v18 = 0;
  if ( a2 )
  {
    v22[0] = 0;
    v24 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonObject",
      0x1Du,
      0x1Cu);
    v5 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(
           v24,
           v22);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x69,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\registrypayloadhandler.cpp",
        (const char *)(unsigned int)v5,
        v18[0]);
    std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v26);
    std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::from_bytes(
      v26,
      v25,
      a2);
    v19 = 0;
    v6 = v22[0];
    v7 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v22[0] + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
    v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v25);
    v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v21);
    v9 = v7(v6, *(_QWORD *)(v8 + 24), &v19);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\registrypayloadhandler.cpp",
        (const char *)(unsigned int)v9,
        v18[0]);
    v10 = v19;
    v11 = *(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v19 + 64LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v18);
    v24 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"settings", 9u, 8u);
    v12 = v11(v10, v24, v18);
    if ( v12 == -2089484279 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
      std::wstring::_Tidy_deallocate(v25);
      std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v26);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v22);
      goto LABEL_21;
    }
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7A,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\registrypayloadhandler.cpp",
        (const char *)(unsigned int)v12,
        v18[0]);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
    std::wstring::_Tidy_deallocate(v25);
    std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v26);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v22);
    v4 = *(_QWORD *)v18;
  }
  v20 = 0;
  if ( v4 )
  {
    v13 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(
            v18,
            &v20);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x83,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\registrypayloadhandler.cpp",
        (const char *)(unsigned int)v13,
        v18[0]);
  }
  v14 = lambda_a3d66e65fe9a74e278f1f3c9f4f62a5d_::_lambda_a3d66e65fe9a74e278f1f3c9f4f62a5d_(v22, this, v18, &v20);
  v15 = FoundationCollectionHelper::ForEach_Windows::Foundation::Collections::IKeyValuePair_HSTRING_____Windows::Data::Json::IJsonValue_____lambda_a3d66e65fe9a74e278f1f3c9f4f62a5d___(
          *((_QWORD *)this + 2),
          v14);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCD,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\registrypayloadhandler.cpp",
      (const char *)(unsigned int)v15,
      v18[0]);
  if ( v20 )
  {
    v21 = 0;
    v16 = lambda_cd52ac7978fa0dc890a256c46c7b7588_::_lambda_cd52ac7978fa0dc890a256c46c7b7588_(v22, &v19, &v21);
    FoundationCollectionHelper::ForEachKvp_HSTRING_____Windows::Data::Json::IJsonValue____lambda_cd52ac7978fa0dc890a256c46c7b7588___(
      v17,
      v16);
  }
  if ( *((_QWORD *)this + 5) )
    ProcessFlightRegistrationForPayload((char *)this + 24, a2);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
LABEL_21:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v18);
}

```

## disassembly

```asm
0x1800412f0  mov     [rsp-8+arg_10], rbx
0x1800412f5  mov     [rsp-8+arg_18], rsi
0x1800412fa  push    rbp
0x1800412fb  push    rdi
0x1800412fc  push    r14
0x1800412fe  lea     rbp, [rsp-30h]
0x180041303  sub     rsp, 130h
0x18004130a  mov     rax, cs:__security_cookie
0x180041311  xor     rax, rsp
0x180041314  mov     [rbp+40h+var_20], rax
0x180041318  mov     r14, rdx
0x18004131b  mov     rsi, rcx
0x18004131e  xor     eax, eax
0x180041320  mov     qword ptr [rsp+140h+var_120], rax; int
0x180041325  test    rdx, rdx
0x180041328  jz      loc_1800414DC
0x18004132e  mov     [rsp+140h+var_100], rax
0x180041333  mov     [rsp+140h+var_D0], rax
0x180041338  lea     r9d, [rax+1Ch]; unsigned int
0x18004133c  lea     r8d, [rax+1Dh]; unsigned int
0x180041340  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180041347  lea     rcx, [rsp+140h+hstringHeader]; hstringHeader
0x18004134c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180041351  lea     rdx, [rsp+140h+var_100]
0x180041356  mov     rcx, [rsp+140h+var_D0]
0x18004135b  call    ??$GetActivationFactory@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>)
0x180041360  mov     rcx, [rbp+48h]; this
0x180041364  test    eax, eax
0x180041366  jns     short loc_18004137D
0x180041368  mov     r9d, eax; char *
0x18004136b  lea     r8, aOnecoreBaseFli_16; "onecore\\base\\flighting\\onesettings\\"...
0x180041372  mov     edx, 69h ; 'i'; void *
0x180041377  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004137d  lea     rcx, [rbp+40h+var_A0]
0x180041381  call    ??0?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x180041386  nop
0x180041387  mov     r8, r14
0x18004138a  lea     rdx, [rsp+140h+var_C8]
0x18004138f  lea     rcx, [rbp+40h+var_A0]
0x180041393  call    ?from_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@PEBD@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::from_bytes(char const *)
0x180041398  nop
0x180041399  mov     [rsp+140h+var_118], 0
0x1800413a2  mov     rdi, [rsp+140h+var_100]
0x1800413a7  mov     rax, [rdi]
0x1800413aa  mov     rbx, [rax+30h]
0x1800413ae  lea     rcx, [rsp+140h+var_118]
0x1800413b3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800413b8  lea     rcx, [rsp+140h+var_C8]
0x1800413bd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800413c2  mov     [rsp+140h+var_108], rax
0x1800413c7  lea     rdx, [rsp+140h+var_108]
0x1800413cc  lea     rcx, [rsp+140h+hstringHeader]
0x1800413d1  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800413d6  nop
0x1800413d7  lea     r8, [rsp+140h+var_118]
0x1800413dc  mov     rdx, [rax+18h]
0x1800413e0  mov     rcx, rdi
0x1800413e3  mov     rax, rbx
0x1800413e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800413eb  nop
0x1800413ec  mov     rcx, [rbp+48h]; this
0x1800413f0  test    eax, eax
0x1800413f2  jns     short loc_180041409
0x1800413f4  mov     r9d, eax; char *
0x1800413f7  lea     r8, aOnecoreBaseFli_16; "onecore\\base\\flighting\\onesettings\\"...
0x1800413fe  mov     edx, 71h ; 'q'; void *
0x180041403  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180041409  mov     rdi, [rsp+140h+var_118]
0x18004140e  mov     rax, [rdi]
0x180041411  mov     rbx, [rax+40h]
0x180041415  lea     rcx, [rsp+140h+var_120]
0x18004141a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004141f  mov     [rsp+140h+var_D0], 0
0x180041428  mov     r9d, 8; unsigned int
0x18004142e  lea     r8d, [r9+1]; unsigned int
0x180041432  lea     rdx, aSettings; "settings"
0x180041439  lea     rcx, [rsp+140h+hstringHeader]; hstringHeader
0x18004143e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180041443  nop
0x180041444  lea     r8, [rsp+140h+var_120]
0x180041449  mov     rdx, [rsp+140h+var_D0]
0x18004144e  mov     rcx, rdi
0x180041451  mov     rax, rbx
0x180041454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041459  nop
0x18004145a  cmp     eax, 83750009h
0x18004145f  jnz     short loc_180041490
0x180041461  lea     rcx, [rsp+140h+var_118]
0x180041466  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004146b  nop
0x18004146c  lea     rcx, [rsp+140h+var_C8]
0x180041471  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180041476  nop
0x180041477  lea     rcx, [rbp+40h+var_A0]
0x18004147b  call    ??1?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x180041480  nop
0x180041481  lea     rcx, [rsp+140h+var_100]
0x180041486  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004148b  jmp     loc_1800415A7
0x180041490  mov     rcx, [rbp+48h]; this
0x180041494  test    eax, eax
0x180041496  jns     short loc_1800414AD
0x180041498  mov     r9d, eax; char *
0x18004149b  lea     r8, aOnecoreBaseFli_16; "onecore\\base\\flighting\\onesettings\\"...
0x1800414a2  mov     edx, 7Ah ; 'z'; void *
0x1800414a7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800414ad  lea     rcx, [rsp+140h+var_118]
0x1800414b2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800414b7  nop
0x1800414b8  lea     rcx, [rsp+140h+var_C8]
0x1800414bd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800414c2  nop
0x1800414c3  lea     rcx, [rbp+40h+var_A0]
0x1800414c7  call    ??1?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1800414cc  nop
0x1800414cd  lea     rcx, [rsp+140h+var_100]
0x1800414d2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800414d7  mov     rax, qword ptr [rsp+140h+var_120]
0x1800414dc  mov     [rsp+140h+var_110], 0
0x1800414e5  test    rax, rax
0x1800414e8  jz      short loc_180041516
0x1800414ea  lea     rdx, [rsp+140h+var_110]
0x1800414ef  lea     rcx, [rsp+140h+var_120]
0x1800414f4  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>>)
0x1800414f9  mov     rcx, [rbp+48h]; this
0x1800414fd  test    eax, eax
0x1800414ff  jns     short loc_180041516
0x180041501  mov     r9d, eax; char *
0x180041504  lea     r8, aOnecoreBaseFli_16; "onecore\\base\\flighting\\onesettings\\"...
0x18004150b  mov     edx, 83h; void *
0x180041510  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180041516  lea     r9, [rsp+140h+var_110]
0x18004151b  lea     r8, [rsp+140h+var_120]
0x180041520  mov     rdx, rsi
0x180041523  lea     rcx, [rsp+140h+var_100]
0x180041528  call    _lambda_a3d66e65fe9a74e278f1f3c9f4f62a5d____lambda_a3d66e65fe9a74e278f1f3c9f4f62a5d_
0x18004152d  mov     rdx, rax
0x180041530  mov     rcx, [rsi+10h]
0x180041534  call    FoundationCollectionHelper__ForEach_Windows__Foundation__Collections__IKeyValuePair_HSTRING_____Windows__Data__Json__IJsonValue_____lambda_a3d66e65fe9a74e278f1f3c9f4f62a5d___
0x180041539  mov     rcx, [rbp+48h]; this
0x18004153d  test    eax, eax
0x18004153f  jns     short loc_180041556
0x180041541  mov     r9d, eax; char *
0x180041544  lea     r8, aOnecoreBaseFli_16; "onecore\\base\\flighting\\onesettings\\"...
0x18004154b  mov     edx, 0CDh; void *
0x180041550  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180041556  mov     r9, [rsp+140h+var_110]
0x18004155b  test    r9, r9
0x18004155e  jz      short loc_180041588
0x180041560  mov     [rsp+140h+var_108], 0
0x180041569  lea     r8, [rsp+140h+var_108]
0x18004156e  lea     rdx, [rsp+140h+var_118]
0x180041573  lea     rcx, [rsp+140h+var_100]
0x180041578  call    _lambda_cd52ac7978fa0dc890a256c46c7b7588____lambda_cd52ac7978fa0dc890a256c46c7b7588_
0x18004157d  mov     rdx, rax
0x180041580  mov     rcx, r9
0x180041583  call    FoundationCollectionHelper__ForEachKvp_HSTRING_____Windows__Data__Json__IJsonValue____lambda_cd52ac7978fa0dc890a256c46c7b7588___
0x180041588  lea     rcx, [rsi+18h]
0x18004158c  cmp     qword ptr [rcx+10h], 0
0x180041591  jz      short loc_18004159C
0x180041593  mov     rdx, r14
0x180041596  call    ?ProcessFlightRegistrationForPayload@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; ProcessFlightRegistrationForPayload(std::wstring const &,char const *)
0x18004159b  nop
0x18004159c  lea     rcx, [rsp+140h+var_110]
0x1800415a1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800415a6  nop
0x1800415a7  lea     rcx, [rsp+140h+var_120]
0x1800415ac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800415b1  mov     rcx, [rbp+40h+var_20]
0x1800415b5  xor     rcx, rsp; StackCookie
0x1800415b8  call    __security_check_cookie
0x1800415bd  lea     r11, [rsp+140h+var_10]
0x1800415c5  mov     rbx, [r11+30h]
0x1800415c9  mov     rsi, [r11+38h]
0x1800415cd  mov     rsp, r11
0x1800415d0  pop     r14
0x1800415d2  pop     rdi
0x1800415d3  pop     rbp
0x1800415d4  retn
```
