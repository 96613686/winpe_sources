# ConsentCoordinationHelpers::GetConsentValuesInJsonFromCR(winrt::hstring,bool &)

- ea: `0x180014a08`
- end: `0x180015d53`
- name: `?GetConsentValuesInJsonFromCR@ConsentCoordinationHelpers@@YA?AUJsonObject@Json@Data@Windows@winrt@@Uhstring@6@AEA_N@Z`
- size: `4939`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018380`
- `0x180028bb4`

## callees

- `0x1800034f7`
- `0x1800035ab`
- `0x180005004`
- `0x18000ed24`
- `0x180010e50`
- `0x180010fe4`
- `0x1800130a4`
- `0x180013f6c`
- `0x180014038`
- `0x1800143c4`
- `0x180014a08`
- `0x180016314`
- `0x18001637c`
- `0x1800163d0`
- `0x180016438`
- `0x1800165b4`
- `0x18001666c`
- `0x180017fec`
- `0x180018098`
- `0x180018198`
- `0x180018320`
- `0x18001c1d4`
- `0x18007d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x180015aac`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x180015aac`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180014c2c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180014d5a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180014dc3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180015073`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180015180`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001537f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800153d0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001544f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800154fe`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001558b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180015670`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800156fa`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001577c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001582b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180015959`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180015962`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180015b30`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180015c07`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180014c2c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180014d5a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180014dc3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180015073`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180015180`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001537f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800153d0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001544f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800154fe`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001558b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180015670`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800156fa`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001577c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001582b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180015959`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180015962`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180015b30`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180015c07`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014ce9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014f98`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014ce9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014f98`

## pseudocode

```c
// Hidden C++ exception states: #wind=28 #try_helpers=1
_QWORD *__fastcall ConsentCoordinationHelpers::GetConsentValuesInJsonFromCR(_QWORD *a1, int **a2, _BYTE *a3)
{
  int v3; // eax
  LPVOID v4; // rdi
  __int64 v5; // rbx
  double v6; // xmm7_8
  int v7; // r13d
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rax
  const WCHAR *v12; // rcx
  int v13; // r12d
  void *v14; // r14
  int v15; // ecx
  HANDLE v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // r13d
  int v20; // eax
  __int64 v21; // rax
  const WCHAR *v22; // rcx
  void *v23; // r14
  int v24; // eax
  HANDLE v25; // rax
  __int64 BooleanValue; // rax
  void *v27; // r14
  int v28; // eax
  HANDLE v29; // rax
  void (__fastcall ****v30)(_QWORD, __int64 *, __int64 *); // rcx
  __int64 v31; // rax
  void *v32; // r14
  int v33; // eax
  HANDLE v34; // rax
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // rcx
  __int64 v38; // rcx
  int v39; // eax
  __int64 v40; // rcx
  __int64 v41; // r8
  __int64 v42; // rcx
  __int64 v43; // r8
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rax
  volatile signed __int32 *v47; // rbx
  signed __int32 v48; // r15d
  HANDLE v49; // rax
  int v51; // eax
  LPVOID v52; // r14
  int v53; // r12d
  double v54; // xmm6_8
  __int64 v55; // rax
  const wchar_t *v56; // rcx
  void *v57; // r14
  int v58; // eax
  HANDLE ProcessHeap; // rax
  const char *v60; // r9
  const char *v61; // r9
  unsigned int v62; // eax
  unsigned int v63; // eax
  unsigned int v64; // eax
  char *v65; // [rsp+28h] [rbp-190h]
  __int128 *v66; // [rsp+30h] [rbp-188h] BYREF
  __int128 v67; // [rsp+38h] [rbp-180h] BYREF
  const wchar_t *v68; // [rsp+48h] [rbp-170h]
  LPVOID v69; // [rsp+50h] [rbp-168h] BYREF
  int *v70; // [rsp+58h] [rbp-160h] BYREF
  int v71; // [rsp+60h] [rbp-158h] BYREF
  int v72; // [rsp+64h] [rbp-154h]
  const wchar_t *v73; // [rsp+70h] [rbp-148h]
  __int64 v75; // [rsp+80h] [rbp-138h] BYREF
  __int64 v76; // [rsp+88h] [rbp-130h] BYREF
  void (__fastcall ***v77)(_QWORD, __int64 *, __int64 *); // [rsp+90h] [rbp-128h] BYREF
  void (__fastcall ***v78)(_QWORD, __int64 *, LPVOID *); // [rsp+98h] [rbp-120h] BYREF
  __int64 v79; // [rsp+A0h] [rbp-118h] BYREF
  __int64 v80; // [rsp+A8h] [rbp-110h] BYREF
  LPVOID v81; // [rsp+B0h] [rbp-108h] BYREF
  __int64 v82; // [rsp+B8h] [rbp-100h] BYREF
  __int64 v83; // [rsp+C0h] [rbp-F8h] BYREF
  __int64 v84; // [rsp+C8h] [rbp-F0h] BYREF
  void (__fastcall ***v85)(_QWORD, __int64 *, __int64 *); // [rsp+D0h] [rbp-E8h] BYREF
  __int64 v86; // [rsp+D8h] [rbp-E0h] BYREF
  __int64 v87; // [rsp+E0h] [rbp-D8h] BYREF
  __int64 v88; // [rsp+E8h] [rbp-D0h] BYREF
  LPVOID v89; // [rsp+F0h] [rbp-C8h] BYREF
  __int64 *v90; // [rsp+F8h] [rbp-C0h] BYREF
  __int128 v91; // [rsp+100h] [rbp-B8h]
  int i; // [rsp+110h] [rbp-A8h]
  LPVOID v93; // [rsp+118h] [rbp-A0h] BYREF
  bool v94[8]; // [rsp+120h] [rbp-98h] BYREF
  LPVOID v95[2]; // [rsp+128h] [rbp-90h] BYREF
  _QWORD v96[9]; // [rsp+138h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]
  LPVOID lpMem; // [rsp+1D8h] [rbp+20h] BYREF

  v70 = *a2;
  lpMem = &v70;
  v69 = &qword_18009CE68;
  _InterlockedIncrement64(&qword_18009CE68);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> )
  {
    lpMem = 0;
    LODWORD(v90) = 0;
    v91 = 0;
    v3 = (*(__int64 (__fastcall **)(__int64, int *, LPVOID *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
                                                             + 48LL))(
           winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
           v70,
           &lpMem);
    if ( v3 < 0 )
      winrt::throw_hresult((unsigned int)v3, &v90);
    v4 = lpMem;
    v89 = lpMem;
    _InterlockedAdd64(&qword_18009CE68, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_18009CE68, 0xFFFFFFFFFFFFFFFFuLL);
    winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::call<_lambda_fa5bfa998c3b0e5f1b75589fad572465_ &>(
      0,
      &v89,
      &lpMem);
    v4 = v89;
  }
  winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(&v89, &v88);
  winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v79);
  winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v78);
  v71 = 1;
  v72 = 13;
  v73 = (const wchar_t *)L"consentValues";
  v70 = &v71;
  if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                           &v88,
                           &v70) )
  {
    v60 = (const char *)(unsigned int)wil::verify_hresult<long>(2205483011LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecoreuap\\shell\\consentux\\unifiedconsent\\inc\\ConsentCoordinationHelpers.h",
      v60,
      (int)"Missing required field in consent response:%ls",
      L"consentValues");
  }
  v71 = 1;
  v72 = 13;
  v73 = (const wchar_t *)L"consentValues";
  v70 = &v71;
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
    &v88,
    &v87,
    &v70);
  v5 = 0;
  v76 = 0;
  v6 = DOUBLE_N1_0;
  v90 = &v87;
  v7 = 0;
  LODWORD(v91) = 0;
  v8 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(&v87);
  LODWORD(lpMem) = v8;
  while ( v7 != v8 )
  {
    winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(&v90, &v80);
    winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(&v80, &v75);
    v71 = 1;
    v72 = 7;
    v73 = (const wchar_t *)L"version";
    v70 = &v71;
    if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                             &v75,
                             &v70) )
    {
      v64 = wil::verify_hresult<long>(2205483011LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0xC1,
        (unsigned int)"onecoreuap\\shell\\consentux\\unifiedconsent\\inc\\ConsentCoordinationHelpers.h",
        (const char *)v64,
        (int)"Missing required field in consent response:%ls",
        L"version");
    }
    v71 = 1;
    v72 = 7;
    v73 = (const wchar_t *)L"version";
    v70 = &v71;
    v69 = 0;
    LODWORD(v66) = 0;
    v67 = 0;
    v51 = (*(__int64 (__fastcall **)(__int64, int *, LPVOID *))(*(_QWORD *)v75 + 48LL))(v75, &v71, &v69);
    if ( v51 < 0 )
      winrt::throw_hresult((unsigned int)v51, &v66);
    v52 = v69;
    v53 = winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(&v69);
    v54 = 0.0;
    if ( v52 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v69);
    if ( v53 )
    {
      v71 = 1;
      v72 = 7;
      v73 = (const wchar_t *)L"version";
      v70 = &v71;
      v55 = *(_QWORD *)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                         &v75,
                         &v81,
                         &v70);
      v56 = v55 ? *(const wchar_t **)(v55 + 16) : &Name;
      v54 = _wtof(v56);
      v57 = v81;
      if ( v81 )
      {
        v58 = _InterlockedDecrement((volatile signed __int32 *)v81 + 6);
        if ( v58 )
        {
          if ( v58 < 0 )
            abort();
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, v57);
        }
        v81 = 0;
      }
    }
    if ( v54 <= v6 )
    {
      if ( v54 == v6 )
        *a3 = 1;
    }
    else
    {
      v6 = v54;
      if ( v5 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v76);
      v5 = v75;
      v76 = v75;
      if ( v75 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 8LL))(v75);
    }
    if ( v75 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v75);
    if ( v80 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v80);
    LODWORD(v91) = ++v7;
    v8 = (int)lpMem;
  }
  lpMem = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v76, &lpMem) )
  {
    v61 = (const char *)(unsigned int)wil::verify_hresult<long>(2205483015LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0xD7,
      (unsigned int)"onecoreuap\\shell\\consentux\\unifiedconsent\\inc\\ConsentCoordinationHelpers.h",
      v61,
      (int)"Failed to parse consent response.",
      v65);
  }
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)&aModeltype[2 * v9] );
  if ( (_DWORD)v9 )
  {
    if ( *(_WORD *)&aModeltype[2 * (unsigned int)v9] )
      abort();
    LODWORD(v67) = 1;
    DWORD1(v67) = v9;
    v68 = (const wchar_t *)L"modelType";
    v66 = &v67;
  }
  else
  {
    v66 = 0;
  }
  if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                           &v76,
                           &v66) )
  {
    v62 = wil::verify_hresult<long>(2205483011LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecoreuap\\shell\\consentux\\unifiedconsent\\inc\\ConsentCoordinationHelpers.h",
      (const char *)v62,
      (int)"Missing required field in consent response:%ls",
      L"modelType",
      v66);
  }
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)&aModeltype[2 * v10] );
  if ( (_DWORD)v10 )
  {
    if ( *(_WORD *)&aModeltype[2 * (unsigned int)v10] )
      goto LABEL_193;
    LODWORD(v67) = 1;
    DWORD1(v67) = v10;
    v68 = (const wchar_t *)L"modelType";
    v66 = &v67;
  }
  else
  {
    v66 = 0;
  }
  v11 = *(_QWORD *)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                     &v76,
                     &lpMem,
                     &v66);
  if ( v11 )
    v12 = *(const WCHAR **)(v11 + 16);
  else
    v12 = &Name;
  v13 = CompareStringOrdinal(v12, -1, L"windowsaccountsyncconsent", -1, 1);
  v14 = lpMem;
  if ( lpMem )
  {
    v15 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( !v15 )
    {
      v16 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v16, 0, v14);
      goto LABEL_30;
    }
    if ( v15 < 0 )
LABEL_193:
      abort();
  }
LABEL_30:
  if ( v13 != 2 )
  {
    v63 = wil::verify_hresult<long>(2205483011LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0xE1,
      (unsigned int)"onecoreuap\\shell\\consentux\\unifiedconsent\\inc\\ConsentCoordinationHelpers.h",
      (const char *)v63,
      (int)"Missing required model type in consent response:%ls",
      (const char *)L"windowsaccountsyncconsent",
      v66);
  }
  v17 = -1;
  do
    ++v17;
  while ( aIsapplicable[v17] );
  if ( (_DWORD)v17 )
  {
    if ( aIsapplicable[(unsigned int)v17] )
      abort();
    LODWORD(v67) = 1;
    DWORD1(v67) = v17;
    v68 = L"isApplicable";
    v66 = &v67;
  }
  else
  {
    v66 = 0;
  }
  if ( (unsigned __int8)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedBoolean(
                          &v76,
                          &v66) )
  {
    v18 = -1;
    do
      ++v18;
    while ( aMaxpromptsreac[v18] );
    if ( (_DWORD)v18 )
    {
      if ( aMaxpromptsreac[(unsigned int)v18] )
        abort();
      LODWORD(v67) = 1;
      DWORD1(v67) = v18;
      v68 = L"maxPromptsReached";
      v66 = &v67;
    }
    else
    {
      v66 = 0;
    }
    LOBYTE(lpMem) = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedBoolean(
                      &v76,
                      &v66);
    v71 = 1;
    v72 = 6;
    v73 = L"values";
    v70 = &v71;
    winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
      &v76,
      &v82,
      &v70);
    if ( (unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(&v82) )
    {
      v90 = &v82;
      v19 = 0;
      LODWORD(v91) = 0;
      v20 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(&v82);
      for ( i = v20; v19 != v20; v20 = i )
      {
        winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(&v90, &v80);
        winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(
          &v80,
          &v75);
        *(_QWORD *)&v67 = 0x500000001LL;
        v68 = L"value";
        v66 = &v67;
        if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                                &v75,
                                &v66)
          && (*(_QWORD *)&v67 = 0xC00000001LL,
              v68 = L"categoryName",
              v66 = &v67,
              (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                                 &v75,
                                 &v66)) )
        {
          *(_QWORD *)&v67 = 0x500000001LL;
          v68 = L"value";
          v66 = &v67;
          v21 = *(_QWORD *)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                             &v75,
                             &v93,
                             &v66);
          if ( v21 )
            v22 = *(const WCHAR **)(v21 + 16);
          else
            v22 = &Name;
          CompareStringOrdinal(v22, -1, L"true", -1, 1);
          v23 = v93;
          if ( v93 )
          {
            v24 = _InterlockedDecrement((volatile signed __int32 *)v93 + 6);
            if ( v24 )
            {
              if ( v24 < 0 )
                abort();
            }
            else
            {
              v25 = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(v25, 0, v23);
            }
            v93 = 0;
          }
          winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v85);
          BooleanValue = winrt::Windows::Data::Json::JsonValue::CreateBooleanValue((bool)v94);
          *(_QWORD *)&v67 = 0x1100000001LL;
          v68 = L"isConsentAccepted";
          v66 = &v67;
          winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Insert(
            &v85,
            &v66,
            BooleanValue);
          if ( *(_QWORD *)v94 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v94);
          if ( v85 )
          {
            v83 = 0;
            (**v85)(v85, winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>, &v83);
            v84 = v83;
          }
          else
          {
            v84 = 0;
          }
          *(_QWORD *)&v67 = 0xC00000001LL;
          v68 = L"categoryName";
          v66 = &v67;
          v96[0] = *(_QWORD *)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                                &v75,
                                v95,
                                &v66);
          winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Insert(
            &v78,
            v96,
            &v84);
          v27 = v95[0];
          if ( v95[0] )
          {
            v28 = _InterlockedDecrement((volatile signed __int32 *)v95[0] + 6);
            if ( v28 )
            {
              if ( v28 < 0 )
                abort();
            }
            else
            {
              v29 = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(v29, 0, v27);
            }
            v95[0] = 0;
          }
          if ( v84 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v84);
          if ( v85 )
          {
            v30 = &v85;
LABEL_89:
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v30);
          }
        }
        else
        {
          *(_QWORD *)&v67 = 0xC00000001LL;
          v68 = L"categoryName";
          v66 = &v67;
          if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                                  &v75,
                                  &v66) )
          {
            winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v77);
            v31 = winrt::Windows::Data::Json::JsonValue::CreateBooleanValue((bool)&v81);
            *(_QWORD *)&v67 = 0x1100000001LL;
            v68 = L"isConsentAccepted";
            v66 = &v67;
            winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Insert(
              &v77,
              &v66,
              v31);
            if ( v81 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v81);
            if ( v77 )
            {
              v83 = 0;
              (**v77)(v77, winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>, &v83);
              v86 = v83;
            }
            else
            {
              v86 = 0;
            }
            *(_QWORD *)&v67 = 0xC00000001LL;
            v68 = L"categoryName";
            v66 = &v67;
            v96[0] = *(_QWORD *)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                                  &v75,
                                  &v69,
                                  &v66);
            winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Insert(
              &v78,
              v96,
              &v86);
            v32 = v69;
            if ( v69 )
            {
              v33 = _InterlockedDecrement((volatile signed __int32 *)v69 + 6);
              if ( v33 )
              {
                if ( v33 < 0 )
                  abort();
              }
              else
              {
                v34 = WINRT_IMPL_GetProcessHeap();
                WINRT_IMPL_HeapFree(v34, 0, v32);
              }
              v69 = 0;
            }
            if ( v86 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v86);
            if ( v77 )
            {
              v30 = &v77;
              goto LABEL_89;
            }
          }
        }
        if ( v75 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v75);
        if ( v80 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v80);
        LODWORD(v91) = ++v19;
      }
    }
    if ( !(unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Size(&v78) )
      goto LABEL_106;
    v35 = -1;
    do
      ++v35;
    while ( aDatasharing[v35] );
    if ( (_DWORD)v35 )
    {
      if ( aDatasharing[(unsigned int)v35] )
        abort();
      LODWORD(v67) = 1;
      DWORD1(v67) = v35;
      v68 = L"DataSharing";
      v66 = &v67;
    }
    else
    {
      v66 = 0;
    }
    if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                             &v78,
                             &v66) )
    {
LABEL_106:
      winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v77);
      v36 = winrt::Windows::Data::Json::JsonValue::CreateBooleanValue((bool)&lpMem);
      v37 = -1;
      do
        ++v37;
      while ( aIsconsentaccep[v37] );
      if ( (_DWORD)v37 )
      {
        if ( aIsconsentaccep[(unsigned int)v37] )
          abort();
        LODWORD(v67) = 1;
        DWORD1(v67) = v37;
        v68 = L"isConsentAccepted";
        v66 = &v67;
      }
      else
      {
        v66 = 0;
      }
      winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Insert(
        &v77,
        &v66,
        v36);
      if ( lpMem )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
      if ( v77 )
      {
        v69 = 0;
        (**v77)(v77, winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>, (__int64 *)&v69);
        lpMem = v69;
      }
      else
      {
        lpMem = 0;
      }
      v38 = -1;
      do
        ++v38;
      while ( aDatasharing[v38] );
      if ( (_DWORD)v38 )
      {
        if ( aDatasharing[(unsigned int)v38] )
          abort();
        LODWORD(v67) = 1;
        DWORD1(v67) = v38;
        v68 = L"DataSharing";
        v66 = &v67;
      }
      else
      {
        v66 = 0;
      }
      winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Insert(
        &v78,
        &v66,
        &lpMem);
      if ( lpMem )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
      if ( v77 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v77);
    }
    if ( v82 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v82);
  }
  if ( String2[25] )
    abort();
  *(_QWORD *)&v67 = 0x1900000001LL;
  v68 = L"windowsaccountsyncconsent";
  v66 = &v67;
  v69 = &v66;
  v81 = &qword_18009CE68;
  _InterlockedAdd64(&qword_18009CE68, 1u);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> )
  {
    v69 = 0;
    LODWORD(v90) = 0;
    v91 = 0;
    v39 = (*(__int64 (__fastcall **)(__int64, __int128 *, LPVOID *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
                                                                   + 80LL))(
            winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
            v66,
            &v69);
    if ( v39 < 0 )
      winrt::throw_hresult((unsigned int)v39, &v90);
    lpMem = v69;
    _InterlockedAdd64(&qword_18009CE68, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_18009CE68, 0xFFFFFFFFFFFFFFFFuLL);
    winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::call<_lambda_ca425077811c26dd994b3d0531fe1de0_ &>(
      0,
      &lpMem,
      &v69);
  }
  v40 = -1;
  do
    ++v40;
  while ( *(_WORD *)&aModeltype[2 * v40] );
  if ( (_DWORD)v40 )
  {
    if ( *(_WORD *)&aModeltype[2 * (unsigned int)v40] )
      abort();
    v71 = 1;
    v72 = v40;
    v73 = (const wchar_t *)L"modelType";
    v70 = &v71;
  }
  else
  {
    v70 = 0;
  }
  winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Insert(
    &v79,
    &v70,
    &lpMem);
  if ( lpMem )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
  v41 = winrt::Windows::Data::Json::JsonValue::CreateBooleanValue((bool)&lpMem);
  v42 = -1;
  do
    ++v42;
  while ( aIsapplicable[v42] );
  if ( (_DWORD)v42 )
  {
    if ( aIsapplicable[(unsigned int)v42] )
      abort();
    v71 = 1;
    v72 = v42;
    v73 = L"isApplicable";
    v70 = &v71;
  }
  else
  {
    v70 = 0;
  }
  winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Insert(
    &v79,
    &v70,
    v41);
  if ( lpMem )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
  v43 = winrt::Windows::Data::Json::JsonValue::CreateBooleanValue((bool)&lpMem);
  v44 = -1;
  do
    ++v44;
  while ( aIssysteminitia[v44] );
  if ( (_DWORD)v44 )
  {
    if ( aIssysteminitia[(unsigned int)v44] )
      abort();
    v71 = 1;
    v72 = v44;
    v73 = L"isSystemInitiatedPromptAllowed";
    v70 = &v71;
  }
  else
  {
    v70 = 0;
  }
  winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Insert(
    &v79,
    &v70,
    v43);
  if ( lpMem )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
  if ( v78 )
  {
    v69 = 0;
    (**v78)(v78, winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>, &v69);
    lpMem = v69;
  }
  else
  {
    lpMem = 0;
  }
  v45 = -1;
  do
    ++v45;
  while ( *(_WORD *)&aConsentvalues[2 * v45] );
  if ( (_DWORD)v45 )
  {
    if ( *(_WORD *)&aConsentvalues[2 * (unsigned int)v45] )
      abort();
    v71 = 1;
    v72 = v45;
    v73 = (const wchar_t *)L"consentValues";
    v70 = &v71;
  }
  else
  {
    v70 = 0;
  }
  winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Insert(
    &v79,
    &v70,
    &lpMem);
  if ( lpMem )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
  v46 = v79;
  v79 = 0;
  *a1 = v46;
  if ( v5 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v76);
  if ( v87 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v87);
  if ( v78 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v78);
  if ( v79 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v79);
  if ( v88 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v88);
  if ( v4 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v89);
  v47 = *a2;
  if ( *a2 )
  {
    v48 = _InterlockedExchangeAdd(v47 + 6, 0xFFFFFFFF);
    if ( v48 == 1 )
    {
      v49 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v49, 0, (LPVOID)v47);
    }
    else if ( v48 - 1 < 0 )
    {
      abort();
    }
    *a2 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180014a08  mov     r11, rsp
0x180014a0b  mov     [r11+18h], r8
0x180014a0f  mov     [r11+10h], rdx
0x180014a13  mov     [r11+8], rcx
0x180014a17  push    rbx
0x180014a18  push    rsi
0x180014a19  push    rdi
0x180014a1a  push    r12
0x180014a1c  push    r13
0x180014a1e  push    r14
0x180014a20  push    r15
0x180014a22  sub     rsp, 180h
0x180014a29  movaps  xmmword ptr [r11-48h], xmm6
0x180014a2e  movaps  xmmword ptr [r11-58h], xmm7
0x180014a33  xor     esi, esi
0x180014a35  lea     r12, aModeltype; "modelType"
0x180014a3c  lea     r13, aConsentvalues; "consentValues"
0x180014a43  lea     r14, aVersion; "version"
0x180014a4a  mov     rax, [rdx]
0x180014a4d  mov     [rsp+1B8h+var_160], rax
0x180014a52  lea     rax, [rsp+1B8h+var_160]
0x180014a57  mov     [r11+20h], rax
0x180014a5b  lea     rax, qword_18009CE68
0x180014a62  mov     [rsp+1B8h+var_168], rax
0x180014a67  lock inc cs:qword_18009CE68
0x180014a6f  mov     rcx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x180014a76  test    rcx, rcx
0x180014a79  jz      short loc_180014ACD
0x180014a7b  mov     [r11+20h], rsi
0x180014a7f  mov     dword ptr [rsp+1B8h+var_C0], esi
0x180014a86  xorps   xmm0, xmm0
0x180014a89  movdqu  [rsp+1B8h+var_B8], xmm0
0x180014a92  mov     rax, [rcx]
0x180014a95  lea     r8, [r11+20h]
0x180014a99  mov     rdx, [rsp+1B8h+var_160]
0x180014a9e  mov     rax, [rax+30h]
0x180014aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014aa7  test    eax, eax
0x180014aa9  js      loc_180015C0E
0x180014aaf  mov     rdi, [rsp+1B8h+lpMem]
0x180014ab7  mov     [rsp+1B8h+var_C8], rdi
0x180014abf  or      r15, 0FFFFFFFFFFFFFFFFh
0x180014ac3  lock add cs:qword_18009CE68, r15
0x180014acb  jmp     short loc_180014AF6
0x180014acd  or      r15, 0FFFFFFFFFFFFFFFFh
0x180014ad1  lock add cs:qword_18009CE68, r15
0x180014ad9  lea     r8, [rsp+1B8h+lpMem]
0x180014ae1  lea     rdx, [rsp+1B8h+var_C8]
0x180014ae9  call    ??$call@AEAV_lambda_fa5bfa998c3b0e5f1b75589fad572465_@@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_fa5bfa998c3b0e5f1b75589fad572465_@@@Z
0x180014aee  mov     rdi, [rsp+1B8h+var_C8]
0x180014af6  lea     rdx, [rsp+1B8h+var_D0]
0x180014afe  lea     rcx, [rsp+1B8h+var_C8]
0x180014b06  call    ?GetObjectW@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(void)
0x180014b0b  nop
0x180014b0c  lea     rcx, [rsp+1B8h+var_118]; this
0x180014b14  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x180014b19  nop
0x180014b1a  lea     rcx, [rsp+1B8h+var_120]; this
0x180014b22  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x180014b27  nop
0x180014b28  mov     [rsp+1B8h+var_158], 1
0x180014b30  mov     ebx, 0Dh
0x180014b35  mov     [rsp+1B8h+var_154], ebx
0x180014b39  mov     [rsp+1B8h+var_148], r13
0x180014b3e  lea     rax, [rsp+1B8h+var_158]
0x180014b43  mov     [rsp+1B8h+var_160], rax
0x180014b48  lea     rdx, [rsp+1B8h+var_160]
0x180014b4d  lea     rcx, [rsp+1B8h+var_D0]
0x180014b55  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)
0x180014b5a  test    al, al
0x180014b5c  jz      loc_180015C1E
0x180014b62  mov     [rsp+1B8h+var_158], 1
0x180014b6a  mov     [rsp+1B8h+var_154], ebx
0x180014b6e  mov     [rsp+1B8h+var_148], r13
0x180014b73  lea     rax, [rsp+1B8h+var_158]
0x180014b78  mov     [rsp+1B8h+var_160], rax
0x180014b7d  lea     r8, [rsp+1B8h+var_160]
0x180014b82  lea     rdx, [rsp+1B8h+var_D8]
0x180014b8a  lea     rcx, [rsp+1B8h+var_D0]
0x180014b92  call    ?GetNamedArray@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(winrt::param::hstring const &)
0x180014b97  nop
0x180014b98  mov     rbx, rsi
0x180014b9b  mov     [rsp+1B8h+var_130], rbx
0x180014ba3  movsd   xmm7, cs:__real@bff0000000000000
0x180014bab  lea     rax, [rsp+1B8h+var_D8]
0x180014bb3  mov     [rsp+1B8h+var_C0], rax
0x180014bbb  mov     r13d, esi
0x180014bbe  mov     dword ptr [rsp+1B8h+var_B8], esi
0x180014bc5  lea     rcx, [rsp+1B8h+var_D8]
0x180014bcd  call    ?Size@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(void)
0x180014bd2  mov     dword ptr [rsp+1B8h+lpMem], eax
0x180014bd9  cmp     r13d, eax
0x180014bdc  jnz     loc_180015969
0x180014be2  mov     [rsp+1B8h+lpMem], rsi
0x180014bea  lea     rdx, [rsp+1B8h+lpMem]
0x180014bf2  lea     rcx, [rsp+1B8h+var_130]
0x180014bfa  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180014bff  test    al, al
0x180014c01  jnz     loc_180015C56
0x180014c07  mov     rcx, r15
0x180014c0a  inc     rcx
0x180014c0d  cmp     [r12+rcx*2], si
0x180014c12  jnz     short loc_180014C0A
0x180014c14  test    ecx, ecx
0x180014c16  jnz     short loc_180014C23
0x180014c18  mov     [rsp+1B8h+var_188], rsi
0x180014c1d  lea     r13d, [rcx+1]
0x180014c21  jmp     short loc_180014C51
0x180014c23  mov     eax, ecx
0x180014c25  cmp     [r12+rax*2], si
0x180014c2a  jz      short loc_180014C33
0x180014c2c  call    cs:__imp_abort
0x180014c33  mov     r13d, 1
0x180014c39  mov     dword ptr [rsp+1B8h+var_180], r13d
0x180014c3e  mov     dword ptr [rsp+1B8h+var_180+4], ecx
0x180014c42  mov     [rsp+1B8h+var_170], r12
0x180014c47  lea     rax, [rsp+1B8h+var_180]
0x180014c4c  mov     [rsp+1B8h+var_188], rax
0x180014c51  lea     rdx, [rsp+1B8h+var_188]
0x180014c56  lea     rcx, [rsp+1B8h+var_130]
0x180014c5e  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)
0x180014c63  test    al, al
0x180014c65  jz      loc_180015C88
0x180014c6b  mov     rcx, r15
0x180014c6e  inc     rcx
0x180014c71  cmp     [r12+rcx*2], si
0x180014c76  jnz     short loc_180014C6E
0x180014c78  test    ecx, ecx
0x180014c7a  jnz     short loc_180014C83
0x180014c7c  mov     [rsp+1B8h+var_188], rsi
0x180014c81  jmp     short loc_180014CA8
0x180014c83  mov     eax, ecx
0x180014c85  cmp     [r12+rax*2], si
0x180014c8a  jnz     loc_180015959
0x180014c90  mov     dword ptr [rsp+1B8h+var_180], r13d
0x180014c95  mov     dword ptr [rsp+1B8h+var_180+4], ecx
0x180014c99  mov     [rsp+1B8h+var_170], r12
0x180014c9e  lea     rax, [rsp+1B8h+var_180]
0x180014ca3  mov     [rsp+1B8h+var_188], rax
0x180014ca8  lea     r8, [rsp+1B8h+var_188]
0x180014cad  lea     rdx, [rsp+1B8h+lpMem]
0x180014cb5  lea     rcx, [rsp+1B8h+var_130]
0x180014cbd  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(winrt::param::hstring const &)
0x180014cc2  mov     rax, [rax]
0x180014cc5  test    rax, rax
0x180014cc8  jz      short loc_180014CD0
0x180014cca  mov     rcx, [rax+10h]
0x180014cce  jmp     short loc_180014CD7
0x180014cd0  lea     rcx, Name; lpString1
0x180014cd7  mov     [rsp+1B8h+bIgnoreCase], r13d; bIgnoreCase
0x180014cdc  mov     r9d, r15d; cchCount2
0x180014cdf  lea     r8, String2; "windowsaccountsyncconsent"
0x180014ce6  mov     edx, r15d; cchCount1
0x180014ce9  call    cs:__imp_CompareStringOrdinal
0x180014cef  mov     r12d, eax
0x180014cf2  mov     r14, [rsp+1B8h+lpMem]
0x180014cfa  test    r14, r14
0x180014cfd  jz      short loc_180014D2A
0x180014cff  mov     ecx, r15d
0x180014d02  lock xadd [r14+18h], ecx
0x180014d08  sub     ecx, 1
0x180014d0b  jnz     short loc_180014D22
0x180014d0d  nop
0x180014d0e  call    WINRT_IMPL_GetProcessHeap
0x180014d13  mov     rcx, rax; hHeap
0x180014d16  mov     r8, r14; lpMem
0x180014d19  xor     edx, edx; dwFlags
0x180014d1b  call    WINRT_IMPL_HeapFree
0x180014d20  jmp     short loc_180014D2A
0x180014d22  test    ecx, ecx
0x180014d24  js      loc_180015959
0x180014d2a  cmp     r12d, 2
0x180014d2e  jnz     loc_180015CBF
0x180014d34  mov     rcx, r15
0x180014d37  lea     rdx, aIsapplicable; "isApplicable"
0x180014d3e  inc     rcx
0x180014d41  cmp     [rdx+rcx*2], si
0x180014d45  jnz     short loc_180014D3E
0x180014d47  test    ecx, ecx
0x180014d49  jnz     short loc_180014D52
0x180014d4b  mov     [rsp+1B8h+var_188], rsi
0x180014d50  jmp     short loc_180014D79
0x180014d52  mov     eax, ecx
0x180014d54  cmp     [rdx+rax*2], si
0x180014d58  jz      short loc_180014D61
0x180014d5a  call    cs:__imp_abort
0x180014d61  mov     dword ptr [rsp+1B8h+var_180], r13d
0x180014d66  mov     dword ptr [rsp+1B8h+var_180+4], ecx
0x180014d6a  mov     [rsp+1B8h+var_170], rdx
0x180014d6f  lea     rax, [rsp+1B8h+var_180]
0x180014d74  mov     [rsp+1B8h+var_188], rax
0x180014d79  mov     r14b, sil
0x180014d7c  lea     rdx, [rsp+1B8h+var_188]
0x180014d81  lea     rcx, [rsp+1B8h+var_130]
0x180014d89  call    ?GetNamedBoolean@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedBoolean(winrt::param::hstring const &)
0x180014d8e  mov     r12b, al
0x180014d91  mov     [rsp+1B8h+var_140], al
0x180014d95  test    al, al
0x180014d97  jz      loc_180015582
0x180014d9d  mov     rcx, r15
0x180014da0  lea     rdx, aMaxpromptsreac; "maxPromptsReached"
0x180014da7  inc     rcx
0x180014daa  cmp     [rdx+rcx*2], si
0x180014dae  jnz     short loc_180014DA7
0x180014db0  test    ecx, ecx
0x180014db2  jnz     short loc_180014DBB
0x180014db4  mov     [rsp+1B8h+var_188], rsi
0x180014db9  jmp     short loc_180014DE2
0x180014dbb  mov     eax, ecx
0x180014dbd  cmp     [rdx+rax*2], si
0x180014dc1  jz      short loc_180014DCA
0x180014dc3  call    cs:__imp_abort
0x180014dca  mov     dword ptr [rsp+1B8h+var_180], r13d
0x180014dcf  mov     dword ptr [rsp+1B8h+var_180+4], ecx
0x180014dd3  mov     [rsp+1B8h+var_170], rdx
0x180014dd8  lea     rax, [rsp+1B8h+var_180]
0x180014ddd  mov     [rsp+1B8h+var_188], rax
0x180014de2  lea     rdx, [rsp+1B8h+var_188]
0x180014de7  lea     rcx, [rsp+1B8h+var_130]
0x180014def  call    ?GetNamedBoolean@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedBoolean(winrt::param::hstring const &)
0x180014df4  mov     r14b, al
0x180014df7  mov     byte ptr [rsp+1B8h+lpMem], al
0x180014dfe  mov     [rsp+1B8h+var_158], r13d
0x180014e03  mov     [rsp+1B8h+var_154], 6
0x180014e0b  lea     rax, aValues; "values"
0x180014e12  mov     [rsp+1B8h+var_148], rax
0x180014e17  lea     rax, [rsp+1B8h+var_158]
0x180014e1c  mov     [rsp+1B8h+var_160], rax
0x180014e21  lea     r8, [rsp+1B8h+var_160]
0x180014e26  lea     rdx, [rsp+1B8h+var_100]
0x180014e2e  lea     rcx, [rsp+1B8h+var_130]
0x180014e36  call    ?GetNamedArray@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(winrt::param::hstring const &)
0x180014e3b  nop
0x180014e3c  lea     rcx, [rsp+1B8h+var_100]
0x180014e44  call    ?Size@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(void)
0x180014e49  test    eax, eax
0x180014e4b  jz      loc_180015399
0x180014e51  lea     rax, [rsp+1B8h+var_100]
0x180014e59  mov     [rsp+1B8h+var_C0], rax
0x180014e61  mov     r13d, esi
0x180014e64  mov     dword ptr [rsp+1B8h+var_B8], esi
0x180014e6b  lea     rcx, [rsp+1B8h+var_100]
0x180014e73  call    ?Size@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(void)
0x180014e78  mov     [rsp+1B8h+var_A8], eax
0x180014e7f  mov     r12d, 1
0x180014e85  cmp     r13d, eax
0x180014e88  jz      loc_180015386
0x180014e8e  lea     rdx, [rsp+1B8h+var_110]
0x180014e96  lea     rcx, [rsp+1B8h+var_C0]
0x180014e9e  call    ??D?$fast_iterator@UJsonArray@Json@Data@Windows@winrt@@@impl@winrt@@QEBA?AUIJsonValue@Json@Data@Windows@2@XZ; winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(void)
0x180014ea3  nop
0x180014ea4  lea     rdx, [rsp+1B8h+var_138]
0x180014eac  lea     rcx, [rsp+1B8h+var_110]
0x180014eb4  call    ?GetObjectW@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(void)
0x180014eb9  nop
0x180014eba  mov     dword ptr [rsp+1B8h+var_180], r12d
0x180014ebf  mov     dword ptr [rsp+1B8h+var_180+4], 5
0x180014ec7  lea     rax, aValue_0; "value"
0x180014ece  mov     [rsp+1B8h+var_170], rax
0x180014ed3  lea     rax, [rsp+1B8h+var_180]
0x180014ed8  mov     [rsp+1B8h+var_188], rax
0x180014edd  lea     rdx, [rsp+1B8h+var_188]
0x180014ee2  lea     rcx, [rsp+1B8h+var_138]
0x180014eea  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)
0x180014eef  lea     r14, aCategoryname; "categoryName"
0x180014ef6  test    al, al
0x180014ef8  jz      loc_180015187
0x180014efe  mov     dword ptr [rsp+1B8h+var_180], r12d
0x180014f03  mov     dword ptr [rsp+1B8h+var_180+4], 0Ch
0x180014f0b  mov     [rsp+1B8h+var_170], r14
0x180014f10  lea     rax, [rsp+1B8h+var_180]
0x180014f15  mov     [rsp+1B8h+var_188], rax
0x180014f1a  lea     rdx, [rsp+1B8h+var_188]
0x180014f1f  lea     rcx, [rsp+1B8h+var_138]
0x180014f27  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)
0x180014f2c  test    al, al
0x180014f2e  jz      loc_180015187
0x180014f34  mov     dword ptr [rsp+1B8h+var_180], r12d
0x180014f39  mov     dword ptr [rsp+1B8h+var_180+4], 5
0x180014f41  lea     rax, aValue_0; "value"
0x180014f48  mov     [rsp+1B8h+var_170], rax
0x180014f4d  lea     rax, [rsp+1B8h+var_180]
0x180014f52  mov     [rsp+1B8h+var_188], rax
0x180014f57  lea     r8, [rsp+1B8h+var_188]
0x180014f5c  lea     rdx, [rsp+1B8h+var_A0]
0x180014f64  lea     rcx, [rsp+1B8h+var_138]
0x180014f6c  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(winrt::param::hstring const &)
0x180014f71  mov     rax, [rax]
0x180014f74  test    rax, rax
0x180014f77  jz      short loc_180014F7F
0x180014f79  mov     rcx, [rax+10h]
0x180014f7d  jmp     short loc_180014F86
0x180014f7f  lea     rcx, Name; lpString1
0x180014f86  mov     [rsp+1B8h+bIgnoreCase], r12d; bIgnoreCase
0x180014f8b  mov     r9d, r15d; cchCount2
0x180014f8e  lea     r8, aTrue; "true"
0x180014f95  mov     edx, r15d; cchCount1
0x180014f98  call    cs:__imp_CompareStringOrdinal
0x180014f9e  cmp     eax, 2
0x180014fa1  setz    r12b
  ... truncated ...
```
