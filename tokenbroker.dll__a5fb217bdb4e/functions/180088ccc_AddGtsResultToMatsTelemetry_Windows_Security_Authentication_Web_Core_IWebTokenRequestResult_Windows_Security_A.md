# AddGtsResultToMatsTelemetry(Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *,Windows::Security::Authentication::Web::Core::MatsSilentCallResult &,uchar)

- ea: `0x180088ccc`
- end: `0x180089452`
- name: `?AddGtsResultToMatsTelemetry@@YAJPEAUIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@AEAUMatsSilentCallResult@23456@E@Z`
- size: `1926`
- prototype: `__int64 __fastcall(struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *, struct Windows::Security::Authentication::Web::Core::MatsSilentCallResult *, unsigned __int8)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180100fb8`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x18002d940`
- `0x180040cc0`
- `0x18004ce78`
- `0x18005101c`
- `0x1800513a4`
- `0x18007f02c`
- `0x18007f5bc`
- `0x18007f828`
- `0x180088ccc`
- `0x18008e690`
- `0x1800b3bdc`
- `0x1801018c8`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088d7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088d98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088dd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088dea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088f1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088f38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008935d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180089409`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180089423`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088d7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088d98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088dd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088dea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088f1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088f38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008935d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180089409`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180089423`

## string_xrefs

- `0x180088ed1`: `Windows.Data.Json.JsonObject`
- `0x180088fa0`: `Windows.Data.Json.JsonValue`
- `0x180088d22`: `onecore\ds\security\tokenbroker\api\lib\webtokenrequestresultoperation.cpp`
- `0x180088d64`: `onecore\ds\security\tokenbroker\api\lib\webtokenrequestresultoperation.cpp`
- `0x180088db5`: `onecore\ds\security\tokenbroker\api\lib\webtokenrequestresultoperation.cpp`
- `0x180088efa`: `onecore\ds\security\tokenbroker\api\lib\webtokenrequestresultoperation.cpp`
- `0x180088f7c`: `onecore\ds\security\tokenbroker\api\lib\webtokenrequestresultoperation.cpp`
- `0x180088fc9`: `onecore\ds\security\tokenbroker\api\lib\webtokenrequestresultoperation.cpp`
- `0x180089024`: `onecore\ds\security\tokenbroker\api\lib\webtokenrequestresultoperation.cpp`
- `0x1800891b6`: `onecore\ds\security\tokenbroker\api\lib\webtokenrequestresultoperation.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall AddGtsResultToMatsTelemetry(
        struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *a1,
        struct Windows::Security::Authentication::Web::Core::MatsSilentCallResult *a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  __int64 v7; // rsi
  void (__fastcall *v8)(__int64, HSTRING, __int64, _BYTE *); // rdi
  __int64 v9; // rbx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING, HSTRING *); // rbx
  char IsEnabled; // al
  HSTRING v13; // rbx
  _QWORD *v14; // rax
  int v15; // eax
  int v16; // edi
  __int64 v17; // rsi
  __int64 (__fastcall *v18)(__int64, HSTRING, __int64 *); // rdi
  int v19; // eax
  _QWORD *v20; // rax
  int v21; // eax
  __int64 v22; // rsi
  __int64 (__fastcall *v23)(__int64, _QWORD, __int64 *); // rdi
  __int64 v24; // rdx
  __int64 v25; // r14
  __int64 (__fastcall *v26)(__int64, HSTRING, __int64); // rsi
  __int64 v27; // rdi
  __int64 v28; // rsi
  __int64 (__fastcall *v29)(__int64, _QWORD, __int64 *); // rdi
  __int64 v30; // r14
  __int64 (__fastcall *v31)(__int64, HSTRING, __int64); // rsi
  __int64 v32; // rdi
  __int64 v33; // rsi
  __int64 (__fastcall *v34)(__int64, _QWORD, __int64 *); // rdi
  __int64 v35; // r14
  __int64 (__fastcall *v36)(__int64, HSTRING, __int64); // rsi
  __int64 v37; // rdi
  __int64 v38; // rsi
  __int64 (__fastcall *v39)(__int64, _QWORD, HSTRING *, _BYTE *); // rdi
  __int64 v40; // rdx
  __int64 v41; // r14
  __int64 (__fastcall *v42)(__int64, HSTRING, __int64); // rsi
  __int64 v43; // rdi
  __int64 v44; // rsi
  __int64 (__fastcall *v45)(__int64, __int64, __int64 *); // rdi
  __int64 v46; // rdx
  __int64 v47; // r14
  __int64 (__fastcall *v48)(__int64, HSTRING, __int64); // rsi
  __int64 v49; // rdi
  __int64 v50; // rsi
  __int64 (__fastcall *v51)(__int64, __int64, __int64 *); // rdi
  __int64 v52; // rdx
  __int64 v53; // r14
  __int64 (__fastcall *v54)(__int64, HSTRING, __int64); // rsi
  __int64 v55; // rdi
  __int64 v56; // rsi
  __int64 (__fastcall *v57)(__int64, HSTRING *); // rdi
  __int64 v58; // r14
  __int64 (__fastcall *v59)(__int64, HSTRING, HSTRING, _BYTE *); // rsi
  HSTRING v60; // rdi
  int v61; // [rsp+20h] [rbp-89h]
  _BYTE v62[8]; // [rsp+30h] [rbp-79h] BYREF
  __int64 v63; // [rsp+38h] [rbp-71h] BYREF
  _BYTE v64[8]; // [rsp+40h] [rbp-69h] BYREF
  __int64 v65; // [rsp+48h] [rbp-61h] BYREF
  __int64 v66; // [rsp+50h] [rbp-59h] BYREF
  HSTRING v67; // [rsp+58h] [rbp-51h] BYREF
  __int64 v68; // [rsp+60h] [rbp-49h] BYREF
  __int64 v69; // [rsp+68h] [rbp-41h] BYREF
  HSTRING v70; // [rsp+70h] [rbp-39h] BYREF
  _BYTE v71[8]; // [rsp+78h] [rbp-31h] BYREF
  HSTRING string; // [rsp+80h] [rbp-29h] BYREF
  HSTRING v73[4]; // [rsp+88h] [rbp-21h] BYREF
  HSTRING v74[4]; // [rsp+A8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v67 = 0;
  v65 = 0;
  v64[0] = 0;
  string = 0;
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
      (const char *)0x80070057LL,
      v61);
LABEL_13:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
    if ( v67 )
      WindowsDeleteString(v67);
    return 2147942487LL;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
  v4 = ExtractMatsDataFromRequestResult(a1, &v65, &string, v64);
  if ( v4 < 0 )
  {
    v5 = 148;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
      (const char *)(unsigned int)v4,
      v61);
    if ( string )
      WindowsDeleteString(string);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
    if ( v67 )
      WindowsDeleteString(v67);
    return (unsigned int)v4;
  }
  if ( !v65 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x95,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
      (const char *)0x80070057LL,
      v61);
    if ( string )
      WindowsDeleteString(string);
    goto LABEL_13;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MatsOnCancel>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MatsOnCancel>::GetImpl'::`2'::impl)
    && !v64[0] )
  {
    v70 = 0;
    v62[0] = 0;
    v7 = v65;
    v8 = *(void (__fastcall **)(__int64, HSTRING, __int64, _BYTE *))(*(_QWORD *)v65 + 80LL);
    v9 = *(_QWORD *)Windows::Internal::StringReference::StringReference(v74, L"{}");
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v73, L"MATS");
    v8(v7, v73[0], v9, v62);
    v10 = v65;
    v11 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)v65 + 48LL);
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v73, L"MATS");
    v4 = v11(v10, v73[0], &v70);
    if ( v4 < 0 )
    {
      v5 = 158;
      goto LABEL_5;
    }
    Windows::Internal::String::Initialize((Windows::Internal::String *)&string, &v70);
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_MatsOnCancel>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MatsOnCancel>::GetImpl'::`2'::impl);
  v13 = string;
  if ( IsEnabled || v64[0] )
  {
    v69 = 0;
    v14 = (_QWORD *)Windows::Internal::StringReference::StringReference(v74, L"Windows.Data.Json.JsonObject");
    v15 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(
            *v14,
            &v69);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA6,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
        (const char *)(unsigned int)v15,
        v61);
LABEL_25:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
      if ( v13 )
        WindowsDeleteString(v13);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
      if ( v67 )
        WindowsDeleteString(v67);
      return (unsigned int)v16;
    }
    v66 = 0;
    v17 = v69;
    v18 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v69 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
    v19 = v18(v17, v13, &v66);
    v16 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA9,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
        (const char *)(unsigned int)v19,
        v61);
LABEL_32:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
      goto LABEL_25;
    }
    v68 = 0;
    v20 = (_QWORD *)Windows::Internal::StringReference::StringReference(v74, L"Windows.Data.Json.JsonValue");
    v21 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValueStatics>>(
            *v20,
            &v68);
    v16 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAC,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
        (const char *)(unsigned int)v21,
        v61);
LABEL_35:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
      goto LABEL_32;
    }
    v63 = 0;
    v22 = v68;
    v23 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v68 + 72LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
    v16 = v23(v22, *((unsigned int *)a2 + 2), &v63);
    if ( v16 < 0 )
    {
      v24 = 175;
LABEL_38:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
        (const char *)(unsigned int)v16,
        v61);
LABEL_39:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
      goto LABEL_35;
    }
    v25 = v66;
    v26 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64))(*(_QWORD *)v66 + 56LL);
    v27 = v63;
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v73, L"silent_code");
    v16 = v26(v25, v73[0], v27);
    if ( v16 < 0 )
    {
      v24 = 176;
      goto LABEL_38;
    }
    v28 = v68;
    v29 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v68 + 72LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
    v16 = v29(v28, *((unsigned int *)a2 + 4), &v63);
    if ( v16 < 0 )
    {
      v24 = 178;
      goto LABEL_38;
    }
    v30 = v66;
    v31 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64))(*(_QWORD *)v66 + 56LL);
    v32 = v63;
    Windows::Internal::StringReference::_ConstructorHelper(
      (Windows::Internal::StringReference *)v73,
      L"silent_bi_sub_code");
    v16 = v31(v30, v73[0], v32);
    if ( v16 < 0 )
    {
      v24 = 179;
      goto LABEL_38;
    }
    v33 = v68;
    v34 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v68 + 80LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
    v16 = v34(v33, *(_QWORD *)a2, &v63);
    if ( v16 < 0 )
    {
      v24 = 181;
      goto LABEL_38;
    }
    v35 = v66;
    v36 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64))(*(_QWORD *)v66 + 56LL);
    v37 = v63;
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v73, L"silent_message");
    v16 = v36(v35, v73[0], v37);
    if ( v16 < 0 )
    {
      v24 = 182;
      goto LABEL_38;
    }
    v70 = 0;
    v62[0] = 0;
    v38 = v69;
    v39 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *, _BYTE *))(*(_QWORD *)v69 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
    v16 = v39(v38, *((_QWORD *)a2 + 3), &v70, v62);
    if ( v16 < 0 )
    {
      v40 = 188;
LABEL_52:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v40,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
        (const char *)(unsigned int)v16,
        v61);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
      goto LABEL_39;
    }
    if ( v62[0] )
    {
      v16 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(&v70, &v63);
      if ( v16 < 0 )
      {
        v40 = 192;
        goto LABEL_52;
      }
      v41 = v66;
      v42 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64))(*(_QWORD *)v66 + 56LL);
      v43 = v63;
      Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v73, L"silent_mats");
      v16 = v42(v41, v73[0], v43);
      if ( v16 < 0 )
      {
        v40 = 193;
        goto LABEL_52;
      }
    }
    v44 = v68;
    v45 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v68 + 72LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
    v16 = v45(v44, v46, &v63);
    if ( v16 < 0 )
    {
      v40 = 196;
      goto LABEL_52;
    }
    v47 = v66;
    v48 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64))(*(_QWORD *)v66 + 56LL);
    v49 = v63;
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v73, L"silent_status");
    v16 = v48(v47, v73[0], v49);
    if ( v16 < 0 )
    {
      v40 = 197;
      goto LABEL_52;
    }
    v50 = v68;
    v51 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v68 + 72LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
    v16 = v51(v50, v52, &v63);
    if ( v16 < 0 )
    {
      v40 = 199;
      goto LABEL_52;
    }
    v53 = v66;
    v54 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64))(*(_QWORD *)v66 + 56LL);
    v55 = v63;
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v73, L"is_cached");
    v16 = v54(v53, v73[0], v55);
    if ( v16 < 0 )
    {
      v40 = 200;
      goto LABEL_52;
    }
    v16 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(&v66, &v63);
    if ( v16 < 0 )
    {
      v40 = 202;
      goto LABEL_52;
    }
    v56 = v63;
    v57 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v63 + 56LL);
    WindowsDeleteString(v67);
    v67 = 0;
    v16 = v57(v56, &v67);
    if ( v16 < 0 )
    {
      v40 = 203;
      goto LABEL_52;
    }
    v71[0] = 0;
    v58 = v65;
    v59 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, _BYTE *))(*(_QWORD *)v65 + 80LL);
    v60 = v67;
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v73, L"MATS");
    v16 = v59(v58, v73[0], v60, v71);
    if ( v16 < 0 )
    {
      v40 = 206;
      goto LABEL_52;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
  }
  if ( v13 )
    WindowsDeleteString(v13);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
  if ( v67 )
    WindowsDeleteString(v67);
  return 0;
}

```

## disassembly

```asm
0x180088ccc  mov     [rsp-8+arg_18], rbx
0x180088cd1  push    rbp
0x180088cd2  push    rsi
0x180088cd3  push    rdi
0x180088cd4  push    r12
0x180088cd6  push    r13
0x180088cd8  push    r14
0x180088cda  push    r15
0x180088cdc  lea     rbp, [rsp-27h]
0x180088ce1  sub     rsp, 0D0h
0x180088ce8  mov     rax, cs:__security_cookie
0x180088cef  xor     rax, rsp
0x180088cf2  mov     [rbp+57h+var_38], rax
0x180088cf6  movzx   r12d, r8b
0x180088cfa  mov     r15, rdx
0x180088cfd  mov     rbx, rcx
0x180088d00  xor     r13d, r13d
0x180088d03  mov     [rbp+57h+var_A8], r13
0x180088d07  mov     [rbp+57h+var_B8], r13
0x180088d0b  mov     [rbp+57h+var_C0], r13b
0x180088d0f  mov     [rbp+57h+string], r13
0x180088d13  test    rcx, rcx
0x180088d16  jnz     short loc_180088D39
0x180088d18  mov     rcx, [rbp+5Fh]; this
0x180088d1c  mov     r9d, 80070057h; char *
0x180088d22  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\tokenbroker\\api"...
0x180088d29  mov     edx, 92h; void *
0x180088d2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180088d33  nop
0x180088d34  jmp     loc_180088DD7
0x180088d39  lea     rcx, [rbp+57h+var_B8]
0x180088d3d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180088d42  lea     r9, [rbp+57h+var_C0]
0x180088d46  lea     r8, [rbp+57h+string]
0x180088d4a  lea     rdx, [rbp+57h+var_B8]
0x180088d4e  mov     rcx, rbx
0x180088d51  call    ?ExtractMatsDataFromRequestResult@@YAJPEAUIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAU1@@Collections@Foundation@6@AEAVString@Internal@6@AEAE@Z; ExtractMatsDataFromRequestResult(Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *,Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *> * *,Windows::Internal::String &,uchar &)
0x180088d56  mov     ebx, eax
0x180088d58  test    eax, eax
0x180088d5a  jns     short loc_180088DA5
0x180088d5c  mov     edx, 94h; void *
0x180088d61  mov     r9d, ebx; char *
0x180088d64  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\tokenbroker\\api"...
0x180088d6b  mov     rcx, [rbp+5Fh]; this
0x180088d6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180088d74  nop
0x180088d75  mov     rcx, [rbp+57h+string]; string
0x180088d79  test    rcx, rcx
0x180088d7c  jz      short loc_180088D85
0x180088d7e  call    cs:__imp_WindowsDeleteString
0x180088d84  nop
0x180088d85  lea     rcx, [rbp+57h+var_B8]
0x180088d89  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180088d8e  nop
0x180088d8f  mov     rcx, [rbp+57h+var_A8]; string
0x180088d93  test    rcx, rcx
0x180088d96  jz      short loc_180088D9E
0x180088d98  call    cs:__imp_WindowsDeleteString
0x180088d9e  mov     eax, ebx
0x180088da0  jmp     loc_18008942B
0x180088da5  cmp     [rbp+57h+var_B8], r13
0x180088da9  jnz     short loc_180088DFA
0x180088dab  mov     rcx, [rbp+5Fh]; this
0x180088daf  mov     r9d, 80070057h; char *
0x180088db5  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\tokenbroker\\api"...
0x180088dbc  mov     edx, 95h; void *
0x180088dc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180088dc6  nop
0x180088dc7  mov     rcx, [rbp+57h+string]; string
0x180088dcb  test    rcx, rcx
0x180088dce  jz      short loc_180088DD7
0x180088dd0  call    cs:__imp_WindowsDeleteString
0x180088dd6  nop
0x180088dd7  lea     rcx, [rbp+57h+var_B8]
0x180088ddb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180088de0  nop
0x180088de1  mov     rcx, [rbp+57h+var_A8]; string
0x180088de5  test    rcx, rcx
0x180088de8  jz      short loc_180088DF0
0x180088dea  call    cs:__imp_WindowsDeleteString
0x180088df0  mov     eax, 80070057h
0x180088df5  jmp     loc_18008942B
0x180088dfa  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MatsOnCancel@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MatsOnCancel@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MatsOnCancel> `wil::Feature<__WilFeatureTraits_Feature_MatsOnCancel>::GetImpl(void)'::`2'::impl
0x180088e01  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MatsOnCancel@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MatsOnCancel>::__private_IsEnabled(void)
0x180088e06  test    al, al
0x180088e08  jz      loc_180088EAF
0x180088e0e  cmp     [rbp+57h+var_C0], r13b
0x180088e12  jnz     loc_180088EAF
0x180088e18  mov     [rbp+57h+var_90], r13
0x180088e1c  mov     [rbp+57h+var_D0], r13b
0x180088e20  mov     rsi, [rbp+57h+var_B8]
0x180088e24  mov     rax, [rsi]
0x180088e27  mov     rdi, [rax+50h]
0x180088e2b  lea     rdx, asc_18014048C; "{}"
0x180088e32  lea     rcx, [rbp+57h+var_58]; string
0x180088e36  call    ??$?0$02@StringReference@Internal@Windows@@QEAA@AEAY02$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[3])
0x180088e3b  mov     rbx, [rax]
0x180088e3e  mov     rdx, cs:off_180120360; unsigned __int16 *
0x180088e45  lea     rcx, [rbp+57h+var_78]; this
0x180088e49  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180088e4e  lea     r9, [rbp+57h+var_D0]
0x180088e52  mov     r8, rbx
0x180088e55  mov     rdx, [rbp+57h+var_78]
0x180088e59  mov     rcx, rsi
0x180088e5c  mov     rax, rdi
0x180088e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088e64  mov     rdi, [rbp+57h+var_B8]
0x180088e68  mov     rax, [rdi]
0x180088e6b  mov     rbx, [rax+30h]
0x180088e6f  mov     rdx, cs:off_180120360; unsigned __int16 *
0x180088e76  lea     rcx, [rbp+57h+var_78]; this
0x180088e7a  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180088e7f  lea     r8, [rbp+57h+var_90]
0x180088e83  mov     rdx, [rbp+57h+var_78]
0x180088e87  mov     rcx, rdi
0x180088e8a  mov     rax, rbx
0x180088e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088e92  mov     ebx, eax
0x180088e94  test    eax, eax
0x180088e96  jns     short loc_180088EA2
0x180088e98  mov     edx, 9Eh
0x180088e9d  jmp     loc_180088D61
0x180088ea2  lea     rdx, [rbp+57h+var_90]; HSTRING *
0x180088ea6  lea     rcx, [rbp+57h+string]; this
0x180088eaa  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180088eaf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MatsOnCancel@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MatsOnCancel@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MatsOnCancel> `wil::Feature<__WilFeatureTraits_Feature_MatsOnCancel>::GetImpl(void)'::`2'::impl
0x180088eb6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MatsOnCancel@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MatsOnCancel>::__private_IsEnabled(void)
0x180088ebb  mov     rbx, [rbp+57h+string]
0x180088ebf  test    al, al
0x180088ec1  jnz     short loc_180088ECD
0x180088ec3  cmp     [rbp+57h+var_C0], r13b
0x180088ec7  jz      loc_180089401
0x180088ecd  mov     [rbp+57h+var_98], r13
0x180088ed1  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180088ed8  lea     rcx, [rbp+57h+var_58]; string
0x180088edc  call    ??$?0$0BN@@StringReference@Internal@Windows@@QEAA@AEAY0BN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[29])
0x180088ee1  lea     rdx, [rbp+57h+var_98]
0x180088ee5  mov     rcx, [rax]
0x180088ee8  call    ??$GetActivationFactory@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>)
0x180088eed  mov     edi, eax
0x180088eef  test    eax, eax
0x180088ef1  jns     short loc_180088F45
0x180088ef3  mov     rcx, [rbp+5Fh]; this
0x180088ef7  mov     r9d, eax; char *
0x180088efa  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\tokenbroker\\api"...
0x180088f01  mov     edx, 0A6h; void *
0x180088f06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180088f0b  nop
0x180088f0c  lea     rcx, [rbp+57h+var_98]
0x180088f10  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180088f15  nop
0x180088f16  test    rbx, rbx
0x180088f19  jz      short loc_180088F25
0x180088f1b  mov     rcx, rbx; string
0x180088f1e  call    cs:__imp_WindowsDeleteString
0x180088f24  nop
0x180088f25  lea     rcx, [rbp+57h+var_B8]
0x180088f29  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180088f2e  nop
0x180088f2f  mov     rcx, [rbp+57h+var_A8]; string
0x180088f33  test    rcx, rcx
0x180088f36  jz      short loc_180088F3E
0x180088f38  call    cs:__imp_WindowsDeleteString
0x180088f3e  mov     eax, edi
0x180088f40  jmp     loc_18008942B
0x180088f45  mov     [rbp+57h+var_B0], r13
0x180088f49  mov     rsi, [rbp+57h+var_98]
0x180088f4d  mov     rax, [rsi]
0x180088f50  mov     rdi, [rax+30h]
0x180088f54  lea     rcx, [rbp+57h+var_B0]
0x180088f58  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180088f5d  lea     r8, [rbp+57h+var_B0]
0x180088f61  mov     rdx, rbx
0x180088f64  mov     rcx, rsi
0x180088f67  mov     rax, rdi
0x180088f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088f6f  mov     edi, eax
0x180088f71  test    eax, eax
0x180088f73  jns     short loc_180088F9C
0x180088f75  mov     rcx, [rbp+5Fh]; this
0x180088f79  mov     r9d, eax; char *
0x180088f7c  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\tokenbroker\\api"...
0x180088f83  mov     edx, 0A9h; void *
0x180088f88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180088f8d  nop
0x180088f8e  lea     rcx, [rbp+57h+var_B0]
0x180088f92  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180088f97  jmp     loc_180088F0C
0x180088f9c  mov     [rbp+57h+var_A0], r13
0x180088fa0  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x180088fa7  lea     rcx, [rbp+57h+var_58]; string
0x180088fab  call    ??$?0$0BM@@StringReference@Internal@Windows@@QEAA@AEAY0BM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[28])
0x180088fb0  lea     rdx, [rbp+57h+var_A0]
0x180088fb4  mov     rcx, [rax]
0x180088fb7  call    ??$GetActivationFactory@V?$ComPtr@UIJsonValueStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonValueStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValueStatics>>)
0x180088fbc  mov     edi, eax
0x180088fbe  test    eax, eax
0x180088fc0  jns     short loc_180088FE6
0x180088fc2  mov     rcx, [rbp+5Fh]; this
0x180088fc6  mov     r9d, eax; char *
0x180088fc9  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\tokenbroker\\api"...
0x180088fd0  mov     edx, 0ACh; void *
0x180088fd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180088fda  nop
0x180088fdb  lea     rcx, [rbp+57h+var_A0]
0x180088fdf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180088fe4  jmp     short loc_180088F8E
0x180088fe6  mov     [rbp+57h+var_C8], r13
0x180088fea  mov     rsi, [rbp+57h+var_A0]
0x180088fee  mov     rax, [rsi]
0x180088ff1  mov     rdi, [rax+48h]
0x180088ff5  lea     rcx, [rbp+57h+var_C8]
0x180088ff9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180088ffe  mov     edx, [r15+8]
0x180089002  xorps   xmm1, xmm1
0x180089005  cvtsi2sd xmm1, rdx
0x18008900a  lea     r8, [rbp+57h+var_C8]
0x18008900e  mov     rcx, rsi
0x180089011  mov     rax, rdi
0x180089014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089019  mov     edi, eax
0x18008901b  test    eax, eax
0x18008901d  jns     short loc_180089043
0x18008901f  mov     edx, 0AFh; void *
0x180089024  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\tokenbroker\\api"...
0x18008902b  mov     r9d, edi; char *
0x18008902e  mov     rcx, [rbp+5Fh]; this
0x180089032  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089037  nop
0x180089038  lea     rcx, [rbp+57h+var_C8]
0x18008903c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180089041  jmp     short loc_180088FDB
0x180089043  mov     r14, [rbp+57h+var_B0]
0x180089047  mov     rax, [r14]
0x18008904a  mov     rsi, [rax+38h]
0x18008904e  mov     rdi, [rbp+57h+var_C8]
0x180089052  mov     rdx, cs:off_18012BD70; unsigned __int16 *
0x180089059  lea     rcx, [rbp+57h+var_78]; this
0x18008905d  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180089062  mov     r8, rdi
0x180089065  mov     rdx, [rbp+57h+var_78]
0x180089069  mov     rcx, r14
0x18008906c  mov     rax, rsi
0x18008906f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089074  mov     edi, eax
0x180089076  test    eax, eax
0x180089078  jns     short loc_180089081
0x18008907a  mov     edx, 0B0h
0x18008907f  jmp     short loc_180089024
0x180089081  mov     rsi, [rbp+57h+var_A0]
0x180089085  mov     rax, [rsi]
0x180089088  mov     rdi, [rax+48h]
0x18008908c  lea     rcx, [rbp+57h+var_C8]
0x180089090  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180089095  mov     edx, [r15+10h]
0x180089099  xorps   xmm1, xmm1
0x18008909c  cvtsi2sd xmm1, rdx
0x1800890a1  lea     r8, [rbp+57h+var_C8]
0x1800890a5  mov     rcx, rsi
0x1800890a8  mov     rax, rdi
0x1800890ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800890b0  mov     edi, eax
0x1800890b2  test    eax, eax
0x1800890b4  jns     short loc_1800890C0
0x1800890b6  mov     edx, 0B2h
0x1800890bb  jmp     loc_180089024
0x1800890c0  mov     r14, [rbp+57h+var_B0]
0x1800890c4  mov     rax, [r14]
0x1800890c7  mov     rsi, [rax+38h]
0x1800890cb  mov     rdi, [rbp+57h+var_C8]
0x1800890cf  mov     rdx, cs:off_18012BD78; unsigned __int16 *
0x1800890d6  lea     rcx, [rbp+57h+var_78]; this
0x1800890da  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1800890df  mov     r8, rdi
0x1800890e2  mov     rdx, [rbp+57h+var_78]
0x1800890e6  mov     rcx, r14
0x1800890e9  mov     rax, rsi
0x1800890ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800890f1  mov     edi, eax
0x1800890f3  test    eax, eax
0x1800890f5  jns     short loc_180089101
0x1800890f7  mov     edx, 0B3h
0x1800890fc  jmp     loc_180089024
0x180089101  mov     rsi, [rbp+57h+var_A0]
0x180089105  mov     rax, [rsi]
0x180089108  mov     rdi, [rax+50h]
0x18008910c  lea     rcx, [rbp+57h+var_C8]
0x180089110  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180089115  lea     r8, [rbp+57h+var_C8]
0x180089119  mov     rdx, [r15]
0x18008911c  mov     rcx, rsi
0x18008911f  mov     rax, rdi
0x180089122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089127  mov     edi, eax
0x180089129  test    eax, eax
0x18008912b  jns     short loc_180089137
0x18008912d  mov     edx, 0B5h
0x180089132  jmp     loc_180089024
0x180089137  mov     r14, [rbp+57h+var_B0]
0x18008913b  mov     rax, [r14]
  ... truncated ...
```
