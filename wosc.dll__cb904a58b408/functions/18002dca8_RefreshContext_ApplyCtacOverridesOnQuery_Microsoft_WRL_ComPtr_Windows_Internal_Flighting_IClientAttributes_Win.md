# RefreshContext::_ApplyCtacOverridesOnQuery(Microsoft::WRL::ComPtr<Windows::Internal::Flighting::IClientAttributes> &,Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *)

- ea: `0x18002dca8`
- end: `0x18002e01a`
- name: `?_ApplyCtacOverridesOnQuery@RefreshContext@@AEAAXAEAV?$ComPtr@UIClientAttributes@Flighting@Internal@Windows@@@WRL@Microsoft@@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Z`
- size: `882`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002e110`
- `0x18002e298`

## callees

- `0x180003110`
- `0x180005f50`
- `0x180009b4c`
- `0x18000a798`
- `0x1800101fc`
- `0x180010278`
- `0x1800146a8`
- `0x180014928`
- `0x180019e68`
- `0x18002d9c0`
- `0x18002dc50`
- `0x18002dca8`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002dd95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ddc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ded5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002dee3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002dd95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ddc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ded5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002dee3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002de51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002de6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002de51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002de6c`

## string_xrefs

- `0x18002df72`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18002df9c`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18002df87`: `onecore\base\flighting\onesettings\libs\configurationsmanager\refreshcontext.cpp`
- `0x18002dfb4`: `onecore\base\flighting\onesettings\libs\configurationsmanager\refreshcontext.cpp`
- `0x18002dfc9`: `onecore\base\flighting\onesettings\libs\configurationsmanager\refreshcontext.cpp`
- `0x18002dfde`: `onecore\base\flighting\onesettings\libs\configurationsmanager\refreshcontext.cpp`
- `0x18002dff3`: `onecore\base\flighting\onesettings\libs\configurationsmanager\refreshcontext.cpp`
- `0x18002e008`: `onecore\base\flighting\onesettings\libs\configurationsmanager\refreshcontext.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall RefreshContext::_ApplyCtacOverridesOnQuery(
        __int64 a1,
        __int64 (__fastcall ****a2)(_QWORD, GUID *, __int64),
        __int64 (__fastcall ***a3)(_QWORD, GUID *, __int64 *))
{
  __int64 (__fastcall *v6)(_QWORD, GUID *, __int64 *); // rbx
  int v7; // eax
  int i; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64 *); // rbx
  int v11; // eax
  __int64 v12; // rbx
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rdi
  int v14; // eax
  __int64 (__fastcall *v15)(__int64, HSTRING *); // rdi
  int v16; // eax
  int v17; // eax
  int v18; // eax
  PCWSTR StringRawBuffer; // rax
  PCWSTR v20; // rax
  __int64 v21; // rax
  int v22; // eax
  int v24; // [rsp+20h] [rbp-89h]
  char v25; // [rsp+30h] [rbp-79h] BYREF
  _BYTE v26[3]; // [rsp+31h] [rbp-78h] BYREF
  UINT32 length; // [rsp+34h] [rbp-75h] BYREF
  HSTRING string; // [rsp+38h] [rbp-71h] BYREF
  HSTRING v29; // [rsp+40h] [rbp-69h] BYREF
  __int64 v30; // [rsp+48h] [rbp-61h] BYREF
  __int64 v31; // [rsp+50h] [rbp-59h] BYREF
  __int64 v32; // [rsp+58h] [rbp-51h] BYREF
  int v33; // [rsp+60h] [rbp-49h]
  __int64 v34; // [rsp+68h] [rbp-41h] BYREF
  __int64 v35; // [rsp+70h] [rbp-39h] BYREF
  __int64 v36; // [rsp+78h] [rbp-31h] BYREF
  int v37; // [rsp+80h] [rbp-29h]
  __int64 v38; // [rsp+88h] [rbp-21h]
  _BYTE v39[16]; // [rsp+90h] [rbp-19h] BYREF
  __int64 v40; // [rsp+A0h] [rbp-9h]
  _BYTE v41[32]; // [rsp+B0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v30 = 0;
  v6 = **a3;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  v7 = v6(a3, &GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b, &v30);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\refreshcontext.cpp",
      (const char *)(unsigned int)v7,
      v24);
  wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::iterable_iterator(
    &v32,
    v30);
  v36 = 0;
  v37 = -1;
  v38 = 0;
  for ( i = v33; i != -1; v33 = i )
  {
    v9 = v32;
    v10 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    v11 = v10(v9, &v34);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v11,
        v24);
    v12 = v34;
    v35 = v34;
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 8LL))(v34);
    v29 = 0;
    string = 0;
    v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v12 + 48LL);
    WindowsDeleteString(0);
    v29 = 0;
    v14 = v13(v12, &v29);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\refreshcontext.cpp",
        (const char *)(unsigned int)v14,
        v24);
    v15 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v12 + 56LL);
    WindowsDeleteString(string);
    string = 0;
    v16 = v15(v12, &string);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x67,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\refreshcontext.cpp",
        (const char *)(unsigned int)v16,
        v24);
    v31 = 0;
    v17 = Microsoft::WRL::ComPtr<Windows::Internal::Flighting::IClientAttributes>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *>>(
            a2,
            (__int64)&v31);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6A,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\refreshcontext.cpp",
        (const char *)(unsigned int)v17,
        v24);
    v25 = 0;
    v18 = (*(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, char *))(*(_QWORD *)v31 + 80LL))(v31, v29, string, &v25);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6C,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\refreshcontext.cpp",
        (const char *)(unsigned int)v18,
        v24);
    if ( !v25 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6D,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\refreshcontext.cpp",
        (const char *)0x8000FFFFLL,
        v24);
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(v29, &length);
    std::wstring::wstring((__int64)v39, (__int64)StringRawBuffer);
    v20 = WindowsGetStringRawBuffer(string, &length);
    std::wstring::wstring((__int64)v41, (__int64)v20);
    v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v39);
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v21, v40) )
      std::wstring::operator=(a1 + 16);
    std::wstring::_Tidy_deallocate(v41);
    std::wstring::_Tidy_deallocate(v39);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v29);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    v26[0] = 0;
    v22 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v32 + 64LL))(v32, v26);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v22,
        v24);
    if ( v26[0] )
      i = v33 + 1;
    else
      i = -1;
  }
  wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator((__int64)&v36);
  wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator((__int64)&v32);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
}

```

## disassembly

```asm
0x18002dca8  mov     [rsp-8+arg_18], rbx
0x18002dcad  push    rbp
0x18002dcae  push    rsi
0x18002dcaf  push    rdi
0x18002dcb0  push    r14
0x18002dcb2  push    r15
0x18002dcb4  lea     rbp, [rsp-37h]
0x18002dcb9  sub     rsp, 0E0h
0x18002dcc0  mov     rax, cs:__security_cookie
0x18002dcc7  xor     rax, rsp
0x18002dcca  mov     [rbp+57h+var_30], rax
0x18002dcce  mov     rdi, r8
0x18002dcd1  mov     r14, rdx
0x18002dcd4  mov     rsi, rcx
0x18002dcd7  xor     r15d, r15d
0x18002dcda  mov     [rbp+57h+var_B8], r15
0x18002dcde  mov     rax, [r8]
0x18002dce1  mov     rbx, [rax]
0x18002dce4  lea     rcx, [rbp+57h+var_B8]
0x18002dce8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002dced  lea     r8, [rbp+57h+var_B8]
0x18002dcf1  lea     rdx, _GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b
0x18002dcf8  mov     rcx, rdi
0x18002dcfb  mov     rax, rbx
0x18002dcfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd03  mov     rcx, [rbp+5Fh]; this
0x18002dd07  test    eax, eax
0x18002dd09  js      loc_18002DF84
0x18002dd0f  mov     rdx, [rbp+57h+var_B8]
0x18002dd13  lea     rcx, [rbp+57h+var_A8]
0x18002dd17  call    ??0iterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAU?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@Z; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::iterable_iterator(Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *> *)
0x18002dd1c  nop
0x18002dd1d  mov     [rbp+57h+var_88], r15
0x18002dd21  mov     [rbp+57h+var_80], 0FFFFFFFFh
0x18002dd28  mov     [rbp+57h+var_78], r15
0x18002dd2c  mov     eax, [rbp+57h+var_A0]
0x18002dd2f  cmp     eax, 0FFFFFFFFh
0x18002dd32  jz      loc_18002DF2F
0x18002dd38  mov     rdi, [rbp+57h+var_A8]
0x18002dd3c  mov     rax, [rdi]
0x18002dd3f  mov     rbx, [rax+30h]
0x18002dd43  lea     rcx, [rbp+57h+var_98]
0x18002dd47  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002dd4c  lea     rdx, [rbp+57h+var_98]
0x18002dd50  mov     rcx, rdi
0x18002dd53  mov     rax, rbx
0x18002dd56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd5b  mov     rcx, [rbp+5Fh]; this
0x18002dd5f  test    eax, eax
0x18002dd61  js      loc_18002DF6F
0x18002dd67  mov     rbx, [rbp+57h+var_98]
0x18002dd6b  mov     [rbp+57h+var_90], rbx
0x18002dd6f  test    rbx, rbx
0x18002dd72  jz      short loc_18002DD84
0x18002dd74  mov     rax, [rbx]
0x18002dd77  mov     rcx, rbx
0x18002dd7a  mov     rax, [rax+8]
0x18002dd7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd83  nop
0x18002dd84  mov     [rbp+57h+var_C0], r15
0x18002dd88  mov     [rbp+57h+string], r15
0x18002dd8c  mov     rax, [rbx]
0x18002dd8f  mov     rdi, [rax+30h]
0x18002dd93  xor     ecx, ecx; string
0x18002dd95  call    cs:__imp_WindowsDeleteString
0x18002dd9b  mov     [rbp+57h+var_C0], r15
0x18002dd9f  lea     rdx, [rbp+57h+var_C0]
0x18002dda3  mov     rcx, rbx
0x18002dda6  mov     rax, rdi
0x18002dda9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ddae  mov     rcx, [rbp+5Fh]; this
0x18002ddb2  test    eax, eax
0x18002ddb4  js      loc_18002E005
0x18002ddba  mov     rax, [rbx]
0x18002ddbd  mov     rdi, [rax+38h]
0x18002ddc1  mov     rcx, [rbp+57h+string]; string
0x18002ddc5  call    cs:__imp_WindowsDeleteString
0x18002ddcb  mov     [rbp+57h+string], r15
0x18002ddcf  lea     rdx, [rbp+57h+string]
0x18002ddd3  mov     rcx, rbx
0x18002ddd6  mov     rax, rdi
0x18002ddd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ddde  mov     rcx, [rbp+5Fh]; this
0x18002dde2  test    eax, eax
0x18002dde4  js      loc_18002DFF0
0x18002ddea  mov     [rbp+57h+var_B0], r15
0x18002ddee  lea     rdx, [rbp+57h+var_B0]
0x18002ddf2  mov     rcx, r14
0x18002ddf5  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@?$ComPtr@UIClientAttributes@Flighting@Internal@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Internal::Flighting::IClientAttributes>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *>>>)
0x18002ddfa  mov     rcx, [rbp+5Fh]; this
0x18002ddfe  test    eax, eax
0x18002de00  js      loc_18002DFDB
0x18002de06  mov     [rbp+57h+var_D0], r15b
0x18002de0a  mov     rcx, [rbp+57h+var_B0]
0x18002de0e  mov     rax, [rcx]
0x18002de11  lea     r9, [rbp+57h+var_D0]
0x18002de15  mov     r8, [rbp+57h+string]
0x18002de19  mov     rdx, [rbp+57h+var_C0]
0x18002de1d  mov     rax, [rax+50h]
0x18002de21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de26  mov     rcx, [rbp+5Fh]; this
0x18002de2a  test    eax, eax
0x18002de2c  js      loc_18002DFC6
0x18002de32  cmp     [rbp+57h+var_D0], r15b
0x18002de36  setz    al
0x18002de39  mov     rcx, [rbp+5Fh]; this
0x18002de3d  test    al, al
0x18002de3f  jnz     loc_18002DFAE
0x18002de45  mov     [rbp+57h+length], r15d
0x18002de49  lea     rdx, [rbp+57h+length]; length
0x18002de4d  mov     rcx, [rbp+57h+var_C0]; string
0x18002de51  call    cs:__imp_WindowsGetStringRawBuffer
0x18002de57  mov     rdx, rax
0x18002de5a  lea     rcx, [rbp+57h+var_70]
0x18002de5e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002de63  nop
0x18002de64  lea     rdx, [rbp+57h+length]; length
0x18002de68  mov     rcx, [rbp+57h+string]; string
0x18002de6c  call    cs:__imp_WindowsGetStringRawBuffer
0x18002de72  mov     rdx, rax
0x18002de75  lea     rcx, [rbp+57h+var_50]
0x18002de79  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002de7e  nop
0x18002de7f  lea     rcx, [rbp+57h+var_70]
0x18002de83  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002de88  mov     rcx, rax
0x18002de8b  mov     r9d, 9
0x18002de91  lea     r8, sourceString; "OSVersion"
0x18002de98  mov     rdx, [rbp+57h+var_60]
0x18002de9c  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18002dea1  test    al, al
0x18002dea3  jz      short loc_18002DEB3
0x18002dea5  lea     rcx, [rsi+10h]
0x18002dea9  lea     rdx, [rbp+57h+var_50]
0x18002dead  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002deb2  nop
0x18002deb3  lea     rcx, [rbp+57h+var_50]
0x18002deb7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002debc  nop
0x18002debd  lea     rcx, [rbp+57h+var_70]
0x18002dec1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002dec6  nop
0x18002dec7  lea     rcx, [rbp+57h+var_B0]
0x18002decb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ded0  nop
0x18002ded1  mov     rcx, [rbp+57h+string]; string
0x18002ded5  call    cs:__imp_WindowsDeleteString
0x18002dedb  mov     [rbp+57h+string], r15
0x18002dedf  mov     rcx, [rbp+57h+var_C0]; string
0x18002dee3  call    cs:__imp_WindowsDeleteString
0x18002dee9  nop
0x18002deea  lea     rcx, [rbp+57h+var_90]
0x18002deee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002def3  mov     [rbp+57h+var_CF], r15b
0x18002def7  mov     rcx, [rbp+57h+var_A8]
0x18002defb  mov     rax, [rcx]
0x18002defe  lea     rdx, [rbp+57h+var_CF]
0x18002df02  mov     rax, [rax+40h]
0x18002df06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df0b  mov     rcx, [rbp+5Fh]; this
0x18002df0f  test    eax, eax
0x18002df11  js      loc_18002DF99
0x18002df17  cmp     [rbp+57h+var_CF], r15b
0x18002df1b  jz      short loc_18002DF2A
0x18002df1d  mov     eax, [rbp+57h+var_A0]
0x18002df20  inc     eax
0x18002df22  mov     [rbp+57h+var_A0], eax
0x18002df25  jmp     loc_18002DD2F
0x18002df2a  or      eax, 0FFFFFFFFh
0x18002df2d  jmp     short loc_18002DF22
0x18002df2f  lea     rcx, [rbp+57h+var_88]
0x18002df33  call    ??1iterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(void)
0x18002df38  nop
0x18002df39  lea     rcx, [rbp+57h+var_A8]
0x18002df3d  call    ??1iterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(void)
0x18002df42  nop
0x18002df43  lea     rcx, [rbp+57h+var_B8]
0x18002df47  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002df4c  mov     rcx, [rbp+57h+var_30]
0x18002df50  xor     rcx, rsp; StackCookie
0x18002df53  call    __security_check_cookie
0x18002df58  mov     rbx, [rsp+100h+arg_18]
0x18002df60  add     rsp, 0E0h
0x18002df67  pop     r15
0x18002df69  pop     r14
0x18002df6b  pop     rdi
0x18002df6c  pop     rsi
0x18002df6d  pop     rbp
0x18002df6e  retn
0x18002df6f  mov     r9d, eax; char *
0x18002df72  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002df79  mov     edx, 1CBEh; void *
0x18002df7e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002df84  mov     r9d, eax; char *
0x18002df87  lea     r8, aOnecoreBaseFli_20; "onecore\\base\\flighting\\onesettings\\"...
0x18002df8e  mov     edx, 61h ; 'a'; void *
0x18002df93  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002df99  mov     r9d, eax; char *
0x18002df9c  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002dfa3  mov     edx, 1CBEh; void *
0x18002dfa8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002dfae  mov     r9d, 8000FFFFh; char *
0x18002dfb4  lea     r8, aOnecoreBaseFli_20; "onecore\\base\\flighting\\onesettings\\"...
0x18002dfbb  mov     edx, 6Dh ; 'm'; void *
0x18002dfc0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002dfc6  mov     r9d, eax; char *
0x18002dfc9  lea     r8, aOnecoreBaseFli_20; "onecore\\base\\flighting\\onesettings\\"...
0x18002dfd0  mov     edx, 6Ch ; 'l'; void *
0x18002dfd5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002dfdb  mov     r9d, eax; char *
0x18002dfde  lea     r8, aOnecoreBaseFli_20; "onecore\\base\\flighting\\onesettings\\"...
0x18002dfe5  mov     edx, 6Ah ; 'j'; void *
0x18002dfea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002dff0  mov     r9d, eax; char *
0x18002dff3  lea     r8, aOnecoreBaseFli_20; "onecore\\base\\flighting\\onesettings\\"...
0x18002dffa  mov     edx, 67h ; 'g'; void *
0x18002dfff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002e005  mov     r9d, eax; char *
0x18002e008  lea     r8, aOnecoreBaseFli_20; "onecore\\base\\flighting\\onesettings\\"...
0x18002e00f  mov     edx, 66h ; 'f'; void *
0x18002e014  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
