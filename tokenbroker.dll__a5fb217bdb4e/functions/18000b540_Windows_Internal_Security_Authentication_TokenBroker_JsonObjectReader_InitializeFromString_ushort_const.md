# Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::InitializeFromString(ushort const *)

- ea: `0x18000b540`
- end: `0x18000bd38`
- name: `?InitializeFromString@JsonObjectReader@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJPEBG@Z`
- size: `2040`
- prototype: `int(Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *__hidden this, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180071428`
- `0x180072cd0`
- `0x180072ec0`
- `0x18010913c`
- `0x18010a138`
- `0x18010c554`

## callees

- `0x180007350`
- `0x18000b540`
- `0x18000bd40`
- `0x1800792b0`
- `0x18008e690`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b616`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b6d3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000ba7f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000bad2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000baed`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000bb08`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000bbdd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000bc64`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b616`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b6d3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000ba7f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000bad2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000baed`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000bb08`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000bbdd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000bc64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b58d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b629`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b701`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b75b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b7c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b80e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b85c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b8aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b58d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b629`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b701`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b75b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b7c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b80e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b85c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b8aa`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000b5c7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000b5c7`

## string_xrefs

- `0x18000b586`: `Windows.Data.Json.JsonObject`
- `0x18000b653`: `onecore\ds\security\tokenbroker\datastore\lib\jsonformat.cpp`
- `0x18000b9f0`: `onecore\ds\security\tokenbroker\datastore\lib\jsonformat.cpp`
- `0x18000ba91`: `onecore\ds\security\tokenbroker\datastore\lib\jsonformat.cpp`
- `0x18000bb1a`: `onecore\ds\security\tokenbroker\datastore\lib\jsonformat.cpp`
- `0x18000bbef`: `onecore\ds\security\tokenbroker\datastore\lib\jsonformat.cpp`
- `0x18000bc76`: `onecore\ds\security\tokenbroker\datastore\lib\jsonformat.cpp`
- `0x18000bc90`: `onecore\ds\security\tokenbroker\datastore\lib\jsonformat.cpp`
- `0x18000bcf3`: `onecore\ds\security\tokenbroker\datastore\lib\jsonformat.cpp`
- `0x18000bd17`: `onecore\ds\security\tokenbroker\datastore\lib\jsonformat.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::InitializeFromString(
        Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader *this,
        const unsigned __int16 *a2)
{
  int ActivationFactory; // eax
  unsigned int v5; // ebx
  __int64 v6; // rsi
  __int64 (__fastcall *v7)(__int64, HSTRING, __int64 *); // r14
  unsigned __int64 v8; // rbx
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, HSTRING, __int64 *); // rdi
  int v15; // eax
  __int64 v16; // rbx
  __int64 (__fastcall *v17)(__int64, HSTRING, struct Windows::Data::Json::IJsonObject **); // rdi
  int v18; // eax
  int v19; // eax
  __int64 v20; // rbx
  __int64 (__fastcall *v21)(__int64, HSTRING, __int64 *); // rdi
  int v22; // eax
  __int64 v23; // rbx
  __int64 (__fastcall *v24)(__int64, HSTRING, __int64 *); // rdi
  int v25; // eax
  __int64 v26; // rbx
  __int64 (__fastcall *v27)(__int64, HSTRING, __int64 *); // rdi
  int v28; // eax
  __int64 v29; // rbx
  __int64 (__fastcall *v30)(__int64, HSTRING, __int64 *); // rdi
  int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // rcx
  struct Windows::Data::Json::IJsonObject *v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  struct Windows::Data::Json::IJsonObject *v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  struct Windows::Data::Json::IJsonObject *v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rcx
  __int64 v55; // [rsp+20h] [rbp-49h] BYREF
  __int64 v56; // [rsp+28h] [rbp-41h] BYREF
  __int64 v57; // [rsp+30h] [rbp-39h] BYREF
  struct Windows::Data::Json::IJsonObject *v58; // [rsp+38h] [rbp-31h] BYREF
  __int64 v59; // [rsp+40h] [rbp-29h] BYREF
  __int64 v60; // [rsp+48h] [rbp-21h] BYREF
  __int64 v61; // [rsp+50h] [rbp-19h] BYREF
  __int64 v62; // [rsp+58h] [rbp-11h] BYREF
  __int64 v63; // [rsp+60h] [rbp-9h] BYREF
  int v64; // [rsp+68h] [rbp-1h]
  HSTRING string; // [rsp+70h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v55 = 0;
  if ( WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(string, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v55);
  v5 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43F,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\jsonformat.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v55);
    v45 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    }
  }
  else
  {
    v56 = 0;
    v6 = v55;
    v7 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v55 + 48LL);
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
    if ( v8 > 0xFFFFFFFF )
    {
      LODWORD(v8) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(a2, v8, &hstringHeader, &string);
    v9 = v7(v6, string, &v56);
    v5 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x442,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\jsonformat.cpp",
        (const char *)(unsigned int)v9,
        v55);
      v10 = v56;
      if ( v56 )
      {
        v56 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
      v11 = v55;
      if ( v55 )
      {
        v55 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
      return v5;
    }
    v57 = 0;
    v13 = v56;
    v14 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v56 + 64LL);
    if ( WindowsCreateStringReference(L"TBDataStoreObject", 0x11u, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v15 = v14(v13, string, &v57);
    v5 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x445,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\jsonformat.cpp",
        (const char *)(unsigned int)v15,
        v55);
      v52 = v57;
      if ( v57 )
      {
        v57 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      }
      v53 = v56;
      if ( v56 )
      {
        v56 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      }
      v54 = v55;
      if ( v55 )
      {
        v55 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      }
    }
    else
    {
      v63 = 5;
      v64 = 0;
      v58 = 0;
      v16 = v57;
      v17 = *(__int64 (__fastcall **)(__int64, HSTRING, struct Windows::Data::Json::IJsonObject **))(*(_QWORD *)v57 + 64LL);
      if ( WindowsCreateStringReference(L"Header", 6u, &hstringHeader, &string) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      v18 = v17(v16, string, &v58);
      v5 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x44E,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\jsonformat.cpp",
          (const char *)(unsigned int)v18,
          v55);
        goto LABEL_85;
      }
      v19 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectHeader::Initialize(
              (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectHeader *)&v63,
              v58);
      v5 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x44F,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\jsonformat.cpp",
          (const char *)(unsigned int)v19,
          v55);
        v41 = v58;
        if ( v58 )
        {
          v58 = 0;
          (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v41 + 16LL))(v41);
        }
        v42 = v57;
        if ( v57 )
        {
          v57 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
        }
        v43 = v56;
        if ( v56 )
        {
          v56 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
        }
        v44 = v55;
        if ( v55 )
        {
          v55 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
        }
      }
      else
      {
        v59 = 0;
        v20 = v57;
        v21 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v57 + 64LL);
        if ( WindowsCreateStringReference(L"ObjectData", 0xAu, &hstringHeader, &string) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        v22 = v21(v20, string, &v59);
        v5 = v22;
        if ( v22 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x456,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\jsonformat.cpp",
            (const char *)(unsigned int)v22,
            v55);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
          goto LABEL_85;
        }
        v60 = 0;
        v23 = v59;
        v24 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v59 + 64LL);
        if ( WindowsCreateStringReference(L"SystemDefinedProperties", 0x17u, &hstringHeader, &string) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        v25 = v24(v23, string, &v60);
        v5 = v25;
        if ( v25 >= 0 )
        {
          v61 = 0;
          v26 = v59;
          v27 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v59 + 72LL);
          if ( WindowsCreateStringReference(L"ProviderDefinedProperties", 0x19u, &hstringHeader, &string) < 0 )
            RaiseException(0xC000000D, 1u, 0, 0);
          v28 = v27(v26, string, &v61);
          v5 = v28;
          if ( v28 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x45F,
              (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\jsonformat.cpp",
              (const char *)(unsigned int)v28,
              v55);
          }
          else
          {
            v62 = 0;
            v29 = v59;
            v30 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v59 + 64LL);
            if ( WindowsCreateStringReference(L"PerApplicationProperties", 0x18u, &hstringHeader, &string) < 0 )
              RaiseException(0xC000000D, 1u, 0, 0);
            v31 = v30(v29, string, &v62);
            v5 = v31;
            if ( v31 >= 0 )
            {
              *(_QWORD *)this = v63;
              *((_DWORD *)this + 2) = v64;
              v32 = *((_QWORD *)this + 2);
              *((_QWORD *)this + 2) = v60;
              v60 = v32;
              v33 = *((_QWORD *)this + 3);
              *((_QWORD *)this + 3) = v61;
              v61 = v33;
              v34 = *((_QWORD *)this + 4);
              *((_QWORD *)this + 4) = v62;
              v62 = v34;
              if ( v34 )
              {
                v62 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
                v33 = v61;
              }
              if ( v33 )
              {
                v61 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
              }
              v35 = v60;
              if ( v60 )
              {
                v60 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
              }
              v36 = v59;
              if ( v59 )
              {
                v59 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
              }
              v37 = v58;
              if ( v58 )
              {
                v58 = 0;
                (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v37 + 16LL))(v37);
              }
              v38 = v57;
              if ( v57 )
              {
                v57 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
              }
              v39 = v56;
              if ( v56 )
              {
                v56 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
              }
              v40 = v55;
              if ( v55 )
              {
                v55 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
              }
              return v5;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x463,
              (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\jsonformat.cpp",
              (const char *)(unsigned int)v31,
              v55);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
LABEL_85:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
          return v5;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x45A,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\jsonformat.cpp",
          (const char *)(unsigned int)v25,
          v55);
        v46 = v60;
        if ( v60 )
        {
          v60 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
        }
        v47 = v59;
        if ( v59 )
        {
          v59 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
        }
        v48 = v58;
        if ( v58 )
        {
          v58 = 0;
          (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v48 + 16LL))(v48);
        }
        v49 = v57;
        if ( v57 )
        {
          v57 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
        }
        v50 = v56;
        if ( v56 )
        {
          v56 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
        }
        v51 = v55;
        if ( v55 )
        {
          v55 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        }
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18000b540  mov     [rsp-8+arg_10], rbx
0x18000b545  mov     [rsp-8+arg_18], rsi
0x18000b54a  push    rbp
0x18000b54b  push    rdi
0x18000b54c  push    r12
0x18000b54e  push    r14
0x18000b550  push    r15
0x18000b552  lea     rbp, [rsp-37h]
0x18000b557  sub     rsp, 0A0h
0x18000b55e  mov     rax, cs:__security_cookie
0x18000b565  xor     rax, rsp
0x18000b568  mov     [rbp+57h+var_30], rax
0x18000b56c  mov     rdi, rdx
0x18000b56f  mov     r15, rcx
0x18000b572  xor     r12d, r12d
0x18000b575  mov     [rbp+57h+var_A0], r12
0x18000b579  lea     r9, [rbp+57h+string]; string
0x18000b57d  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18000b581  mov     edx, 1Ch; length
0x18000b586  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18000b58d  call    cs:__imp_WindowsCreateStringReference
0x18000b593  test    eax, eax
0x18000b595  js      loc_18000B6C3
0x18000b59b  mov     rbx, [rbp+57h+string]
0x18000b59f  mov     rcx, [rbp+57h+var_A0]
0x18000b5a3  test    rcx, rcx
0x18000b5a6  jz      short loc_18000B5B9
0x18000b5a8  mov     [rbp+57h+var_A0], r12
0x18000b5ac  mov     rax, [rcx]
0x18000b5af  mov     rax, [rax+10h]
0x18000b5b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5b8  nop
0x18000b5b9  lea     r8, [rbp+57h+var_A0]
0x18000b5bd  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x18000b5c4  mov     rcx, rbx
0x18000b5c7  call    cs:__imp_RoGetActivationFactory
0x18000b5cd  mov     ebx, eax
0x18000b5cf  test    eax, eax
0x18000b5d1  js      loc_18000BA8A
0x18000b5d7  mov     [rbp+57h+var_98], r12
0x18000b5db  mov     rsi, [rbp+57h+var_A0]
0x18000b5df  mov     rax, [rsi]
0x18000b5e2  mov     r14, [rax+30h]
0x18000b5e6  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000b5ed  nop     dword ptr [rax]
0x18000b5f0  inc     rbx
0x18000b5f3  cmp     word ptr [rdi+rbx*2], 0
0x18000b5f8  jnz     short loc_18000B5F0
0x18000b5fa  mov     eax, 0FFFFFFFFh
0x18000b5ff  cmp     rbx, rax
0x18000b602  jbe     short loc_18000B61C
0x18000b604  mov     ebx, eax
0x18000b606  xor     r9d, r9d; lpArguments
0x18000b609  xor     r8d, r8d; nNumberOfArguments
0x18000b60c  mov     edx, 1; dwExceptionFlags
0x18000b611  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000b616  call    cs:__imp_RaiseException
0x18000b61c  lea     r9, [rbp+57h+string]; string
0x18000b620  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18000b624  mov     edx, ebx; length
0x18000b626  mov     rcx, rdi; sourceString
0x18000b629  call    cs:__imp_WindowsCreateStringReference
0x18000b62f  lea     r8, [rbp+57h+var_98]
0x18000b633  mov     rdx, [rbp+57h+string]
0x18000b637  mov     rcx, rsi
0x18000b63a  mov     rax, r14
0x18000b63d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b642  mov     ebx, eax
0x18000b644  test    eax, eax
0x18000b646  jns     loc_18000B6DE
0x18000b64c  mov     rcx, [rbp+5Fh]; this
0x18000b650  mov     r9d, eax; char *
0x18000b653  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18000b65a  mov     edx, 442h; void *
0x18000b65f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b664  nop
0x18000b665  mov     rcx, [rbp+57h+var_98]
0x18000b669  test    rcx, rcx
0x18000b66c  jz      short loc_18000B67F
0x18000b66e  mov     [rbp+57h+var_98], r12
0x18000b672  mov     rax, [rcx]
0x18000b675  mov     rax, [rax+10h]
0x18000b679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b67e  nop
0x18000b67f  mov     rcx, [rbp+57h+var_A0]
0x18000b683  test    rcx, rcx
0x18000b686  jz      short loc_18000B699
0x18000b688  mov     [rbp+57h+var_A0], r12
0x18000b68c  mov     rax, [rcx]
0x18000b68f  mov     rax, [rax+10h]
0x18000b693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b698  nop
0x18000b699  mov     eax, ebx
0x18000b69b  mov     rcx, [rbp+57h+var_30]
0x18000b69f  xor     rcx, rsp; StackCookie
0x18000b6a2  call    __security_check_cookie
0x18000b6a7  lea     r11, [rsp+0C0h+var_20]
0x18000b6af  mov     rbx, [r11+40h]
0x18000b6b3  mov     rsi, [r11+48h]
0x18000b6b7  mov     rsp, r11
0x18000b6ba  pop     r15
0x18000b6bc  pop     r14
0x18000b6be  pop     r12
0x18000b6c0  pop     rdi
0x18000b6c1  pop     rbp
0x18000b6c2  retn
0x18000b6c3  xor     r9d, r9d; lpArguments
0x18000b6c6  xor     r8d, r8d; nNumberOfArguments
0x18000b6c9  mov     edx, 1; dwExceptionFlags
0x18000b6ce  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000b6d3  call    cs:__imp_RaiseException
0x18000b6d9  jmp     loc_18000B59B
0x18000b6de  mov     [rbp+57h+var_90], r12
0x18000b6e2  mov     rbx, [rbp+57h+var_98]
0x18000b6e6  mov     rax, [rbx]
0x18000b6e9  mov     rdi, [rax+40h]
0x18000b6ed  lea     r9, [rbp+57h+string]; string
0x18000b6f1  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18000b6f5  mov     edx, 11h; length
0x18000b6fa  lea     rcx, aTbdatastoreobj; "TBDataStoreObject"
0x18000b701  call    cs:__imp_WindowsCreateStringReference
0x18000b707  test    eax, eax
0x18000b709  js      loc_18000BA6F
0x18000b70f  lea     r8, [rbp+57h+var_90]
0x18000b713  mov     rdx, [rbp+57h+string]
0x18000b717  mov     rcx, rbx
0x18000b71a  mov     rax, rdi
0x18000b71d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b722  mov     ebx, eax
0x18000b724  test    eax, eax
0x18000b726  js      loc_18000BBE8
0x18000b72c  mov     [rbp+57h+var_60], 5
0x18000b734  mov     [rbp+57h+var_58], r12d
0x18000b738  mov     [rbp+57h+var_88], r12
0x18000b73c  mov     rbx, [rbp+57h+var_90]
0x18000b740  mov     rax, [rbx]
0x18000b743  mov     rdi, [rax+40h]
0x18000b747  lea     r9, [rbp+57h+string]; string
0x18000b74b  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18000b74f  mov     edx, 6; length
0x18000b754  lea     rcx, aHeader; "Header"
0x18000b75b  call    cs:__imp_WindowsCreateStringReference
0x18000b761  test    eax, eax
0x18000b763  js      loc_18000BBCD
0x18000b769  lea     r8, [rbp+57h+var_88]
0x18000b76d  mov     rdx, [rbp+57h+string]
0x18000b771  mov     rcx, rbx
0x18000b774  mov     rax, rdi
0x18000b777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b77c  mov     ebx, eax
0x18000b77e  test    eax, eax
0x18000b780  js      loc_18000BC6F
0x18000b786  mov     rdx, [rbp+57h+var_88]; struct Windows::Data::Json::IJsonObject *
0x18000b78a  lea     rcx, [rbp+57h+var_60]; this
0x18000b78e  call    ?Initialize@JsonObjectHeader@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJPEAUIJsonObject@Json@Data@6@@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectHeader::Initialize(Windows::Data::Json::IJsonObject *)
0x18000b793  mov     ebx, eax
0x18000b795  test    eax, eax
0x18000b797  js      loc_18000B9E9
0x18000b79d  mov     [rbp+57h+var_80], r12
0x18000b7a1  mov     rbx, [rbp+57h+var_90]
0x18000b7a5  mov     rax, [rbx]
0x18000b7a8  mov     rdi, [rax+40h]
0x18000b7ac  lea     r9, [rbp+57h+string]; string
0x18000b7b0  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18000b7b4  mov     edx, 0Ah; length
0x18000b7b9  lea     rcx, aObjectdata; "ObjectData"
0x18000b7c0  call    cs:__imp_WindowsCreateStringReference
0x18000b7c6  test    eax, eax
0x18000b7c8  js      loc_18000BAC2
0x18000b7ce  lea     r8, [rbp+57h+var_80]
0x18000b7d2  mov     rdx, [rbp+57h+string]
0x18000b7d6  mov     rcx, rbx
0x18000b7d9  mov     rax, rdi
0x18000b7dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7e1  mov     ebx, eax
0x18000b7e3  test    eax, eax
0x18000b7e5  js      loc_18000BCEC
0x18000b7eb  mov     [rbp+57h+var_78], r12
0x18000b7ef  mov     rbx, [rbp+57h+var_80]
0x18000b7f3  mov     rax, [rbx]
0x18000b7f6  mov     rdi, [rax+40h]
0x18000b7fa  lea     r9, [rbp+57h+string]; string
0x18000b7fe  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18000b802  mov     edx, 17h; length
0x18000b807  lea     rcx, aSystemdefinedp; "SystemDefinedProperties"
0x18000b80e  call    cs:__imp_WindowsCreateStringReference
0x18000b814  test    eax, eax
0x18000b816  js      loc_18000BADD
0x18000b81c  lea     r8, [rbp+57h+var_78]
0x18000b820  mov     rdx, [rbp+57h+string]
0x18000b824  mov     rcx, rbx
0x18000b827  mov     rax, rdi
0x18000b82a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b82f  mov     ebx, eax
0x18000b831  test    eax, eax
0x18000b833  js      loc_18000BB13
0x18000b839  mov     [rbp+57h+var_70], r12
0x18000b83d  mov     rbx, [rbp+57h+var_80]
0x18000b841  mov     rax, [rbx]
0x18000b844  mov     rdi, [rax+48h]
0x18000b848  lea     r9, [rbp+57h+string]; string
0x18000b84c  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18000b850  mov     edx, 19h; length
0x18000b855  lea     rcx, aProviderdefine; "ProviderDefinedProperties"
0x18000b85c  call    cs:__imp_WindowsCreateStringReference
0x18000b862  test    eax, eax
0x18000b864  js      loc_18000BAF8
0x18000b86a  lea     r8, [rbp+57h+var_70]
0x18000b86e  mov     rdx, [rbp+57h+string]
0x18000b872  mov     rcx, rbx
0x18000b875  mov     rax, rdi
0x18000b878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b87d  mov     ebx, eax
0x18000b87f  test    eax, eax
0x18000b881  js      loc_18000BC89
0x18000b887  mov     [rbp+57h+var_68], r12
0x18000b88b  mov     rbx, [rbp+57h+var_80]
0x18000b88f  mov     rax, [rbx]
0x18000b892  mov     rdi, [rax+40h]
0x18000b896  lea     r9, [rbp+57h+string]; string
0x18000b89a  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18000b89e  mov     edx, 18h; length
0x18000b8a3  lea     rcx, aPerapplication; "PerApplicationProperties"
0x18000b8aa  call    cs:__imp_WindowsCreateStringReference
0x18000b8b0  test    eax, eax
0x18000b8b2  js      loc_18000BC54
0x18000b8b8  lea     r8, [rbp+57h+var_68]
0x18000b8bc  mov     rdx, [rbp+57h+string]
0x18000b8c0  mov     rcx, rbx
0x18000b8c3  mov     rax, rdi
0x18000b8c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8cb  mov     ebx, eax
0x18000b8cd  test    eax, eax
0x18000b8cf  js      loc_18000BD10
0x18000b8d5  movsd   xmm0, [rbp+57h+var_60]
0x18000b8da  movsd   qword ptr [r15], xmm0
0x18000b8df  mov     eax, [rbp+57h+var_58]
0x18000b8e2  mov     [r15+8], eax
0x18000b8e6  mov     rcx, [r15+10h]
0x18000b8ea  mov     rax, [rbp+57h+var_78]
0x18000b8ee  mov     [r15+10h], rax
0x18000b8f2  mov     [rbp+57h+var_78], rcx
0x18000b8f6  mov     rcx, [r15+18h]
0x18000b8fa  mov     rax, [rbp+57h+var_70]
0x18000b8fe  mov     [r15+18h], rax
0x18000b902  mov     [rbp+57h+var_70], rcx
0x18000b906  mov     rdx, [r15+20h]
0x18000b90a  mov     rax, [rbp+57h+var_68]
0x18000b90e  mov     [r15+20h], rax
0x18000b912  mov     [rbp+57h+var_68], rdx
0x18000b916  test    rdx, rdx
0x18000b919  jz      short loc_18000B932
0x18000b91b  mov     [rbp+57h+var_68], r12
0x18000b91f  mov     rax, [rdx]
0x18000b922  mov     rcx, rdx
0x18000b925  mov     rax, [rax+10h]
0x18000b929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b92e  mov     rcx, [rbp+57h+var_70]
0x18000b932  test    rcx, rcx
0x18000b935  jz      short loc_18000B948
0x18000b937  mov     [rbp+57h+var_70], r12
0x18000b93b  mov     rax, [rcx]
0x18000b93e  mov     rax, [rax+10h]
0x18000b942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b947  nop
0x18000b948  mov     rcx, [rbp+57h+var_78]
0x18000b94c  test    rcx, rcx
0x18000b94f  jz      short loc_18000B962
0x18000b951  mov     [rbp+57h+var_78], r12
0x18000b955  mov     rax, [rcx]
0x18000b958  mov     rax, [rax+10h]
0x18000b95c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b961  nop
0x18000b962  mov     rcx, [rbp+57h+var_80]
0x18000b966  test    rcx, rcx
0x18000b969  jz      short loc_18000B97C
0x18000b96b  mov     [rbp+57h+var_80], r12
0x18000b96f  mov     rax, [rcx]
0x18000b972  mov     rax, [rax+10h]
0x18000b976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b97b  nop
0x18000b97c  mov     rcx, [rbp+57h+var_88]
0x18000b980  test    rcx, rcx
0x18000b983  jz      short loc_18000B996
0x18000b985  mov     [rbp+57h+var_88], r12
0x18000b989  mov     rax, [rcx]
0x18000b98c  mov     rax, [rax+10h]
0x18000b990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b995  nop
0x18000b996  mov     rcx, [rbp+57h+var_90]
0x18000b99a  test    rcx, rcx
0x18000b99d  jz      short loc_18000B9B0
0x18000b99f  mov     [rbp+57h+var_90], r12
0x18000b9a3  mov     rax, [rcx]
0x18000b9a6  mov     rax, [rax+10h]
0x18000b9aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9af  nop
0x18000b9b0  mov     rcx, [rbp+57h+var_98]
0x18000b9b4  test    rcx, rcx
0x18000b9b7  jz      short loc_18000B9CA
  ... truncated ...
```
