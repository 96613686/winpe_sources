# MatsHelpers::GetCombinedTelemetryJson(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation const &,Microsoft::WRL::Wrappers::HString &)

- ea: `0x1800f14e8`
- end: `0x1800f195c`
- name: `?GetCombinedTelemetryJson@MatsHelpers@@CAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBVRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@AEAVHString@Wrappers@WRL@Microsoft@@@Z`
- size: `1140`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800f12dc`
- `0x1800f143c`

## callees

- `0x18002d36c`
- `0x18007ddf4`
- `0x18007e27c`
- `0x18007e2b8`
- `0x18007e2dc`
- `0x180089ce0`
- `0x1800a3b60`
- `0x1800f11ac`
- `0x1800f14e8`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f1518`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f187e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f189e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f1518`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f187e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f189e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800f15b5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800f1621`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800f15b5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800f1621`

## string_xrefs

- `0x1800f1544`: `onecoreuap\ds\ext\common\lib\cloudidentitymatscommon\requesttelemetryoperationjsonserializer.cpp`
- `0x1800f1602`: `Windows.Data.Json.JsonValue`
- `0x1800f1596`: `Windows.Data.Json.JsonObject`
- `0x1800f156a`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\matshelpers.cpp`
- `0x1800f15c7`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\matshelpers.cpp`
- `0x1800f1635`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\matshelpers.cpp`
- `0x1800f16b2`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\matshelpers.cpp`
- `0x1800f1760`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\matshelpers.cpp`
- `0x1800f18c0`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\matshelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall MatsHelpers::GetCombinedTelemetryJson(
        const WCHAR **a1,
        const struct Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation *a2,
        HSTRING *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int ActivationFactory; // eax
  __int64 v10; // r9
  __int64 v11; // rdx
  int v12; // eax
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64, __int64 *); // rbx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r9
  __int64 v20; // rbx
  const WCHAR *v21; // rdi
  _QWORD *v22; // rbx
  __int64 v23; // rsi
  unsigned __int64 v24; // rcx
  int v25; // eax
  int v26; // edx
  unsigned int v27; // r8d
  unsigned int v28; // eax
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r9
  __int64 *v32; // rcx
  __int64 v33; // rbx
  __int64 v34; // rsi
  __int64 (__fastcall *v35)(__int64, __int64, __int64); // rdi
  struct Windows::Data::Json::IJsonValue *v36; // rdi
  __int64 (__fastcall *v37)(__int64, __int64, struct Windows::Data::Json::IJsonValue *); // rsi
  int v38; // eax
  unsigned __int64 v39; // r9
  __int64 v40; // rdx
  __int64 v41; // rbx
  __int64 (__fastcall *v42)(__int64, HSTRING *); // rdi
  __int64 v44; // [rsp+20h] [rbp-60h] BYREF
  __int64 v45; // [rsp+28h] [rbp-58h] BYREF
  _QWORD *v46; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v47; // [rsp+38h] [rbp-48h] BYREF
  __int64 v48; // [rsp+40h] [rbp-40h] BYREF
  __int64 v49; // [rsp+48h] [rbp-38h] BYREF
  struct Windows::Data::Json::IJsonValue *v50; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  __int64 v52; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  WindowsDeleteString(*a3);
  *a3 = 0;
  v50 = 0;
  v6 = Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperationJsonSerializer::SerializeCore(
         a2,
         &v50,
         0);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x39,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\lib\\cloudidentitymatscommon\\requesttelemetryoperationjsonserializer.cpp",
      (const char *)(unsigned int)v6,
      v44);
    v8 = 66;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\matshelpers.cpp",
      (const char *)v7,
      v44);
LABEL_55:
    ATL::CComPtrBase<Windows::Data::Json::IJsonValueStatics>::~CComPtrBase<Windows::Data::Json::IJsonValueStatics>((__int64 *)&v50);
    return v7;
  }
  if ( !v50 )
  {
    v7 = -2147024882;
    v8 = 67;
    goto LABEL_5;
  }
  v44 = 0;
  v52 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  ActivationFactory = RoGetActivationFactory(v52, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v44);
  v7 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v10 = (unsigned int)ActivationFactory;
    v11 = 77;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\matshelpers.cpp",
      (const char *)v10,
      v44);
LABEL_54:
    ATL::CComPtrBase<Windows::Data::Json::IJsonValueStatics>::~CComPtrBase<Windows::Data::Json::IJsonValueStatics>(&v44);
    goto LABEL_55;
  }
  if ( !v44 )
  {
    v7 = -2147024882;
    v10 = 2147942414LL;
    v11 = 78;
    goto LABEL_8;
  }
  v46 = 0;
  v52 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonValue",
    0x1Cu,
    0x1Bu);
  v12 = RoGetActivationFactory(v52, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v46);
  v7 = v12;
  if ( v12 < 0 )
  {
    v13 = (unsigned int)v12;
    v14 = 83;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\matshelpers.cpp",
      (const char *)v13,
      v44);
LABEL_53:
    ATL::CComPtrBase<Windows::Data::Json::IJsonValueStatics>::~CComPtrBase<Windows::Data::Json::IJsonValueStatics>((__int64 *)&v46);
    goto LABEL_54;
  }
  if ( !v46 )
  {
    v7 = -2147024882;
    v13 = 2147942414LL;
    v14 = 84;
    goto LABEL_13;
  }
  v45 = 0;
  v15 = v44;
  v16 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v44 + 48LL);
  v52 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"{}", 3u, 2u);
  v17 = v16(v15, v52, &v45);
  v7 = v17;
  if ( v17 < 0 )
  {
    v18 = 87;
LABEL_18:
    v19 = (unsigned int)v17;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\matshelpers.cpp",
      (const char *)v19,
      v44);
LABEL_52:
    ATL::CComPtrBase<Windows::Data::Json::IJsonValueStatics>::~CComPtrBase<Windows::Data::Json::IJsonValueStatics>(&v45);
    goto LABEL_53;
  }
  v20 = v45;
  if ( !v45 )
  {
    v7 = -2147024882;
    v19 = 2147942414LL;
    v18 = 88;
    goto LABEL_19;
  }
  v21 = *a1;
  if ( *((_DWORD *)*a1 - 4) )
  {
    v49 = 0;
    v22 = v46;
    v23 = *v46;
    v52 = 0;
    v47 = 0;
    v24 = -1;
    do
      ++v24;
    while ( v21[v24] );
    v25 = ULongLongToUInt(v24, &v47);
    if ( v25 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v25, v26, v27);
      __debugbreak();
    }
    v28 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v47);
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, v21, v28, v47);
    v29 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64 *))(v23 + 80))(v22, v52, &v49);
    v7 = v29;
    if ( v29 < 0 )
    {
      v30 = 93;
LABEL_29:
      v31 = (unsigned int)v29;
LABEL_30:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v30,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\matshelpers.cpp",
        (const char *)v31,
        v44);
      v32 = &v49;
LABEL_51:
      ATL::CComPtrBase<Windows::Data::Json::IJsonValueStatics>::~CComPtrBase<Windows::Data::Json::IJsonValueStatics>(v32);
      goto LABEL_52;
    }
    v33 = v49;
    if ( !v49 )
    {
      v7 = -2147024882;
      v31 = 2147942414LL;
      v30 = 94;
      goto LABEL_30;
    }
    v34 = v45;
    v35 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v45 + 56LL);
    v52 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"MATS", 5u, 4u);
    v29 = v35(v34, v52, v33);
    v7 = v29;
    if ( v29 < 0 )
    {
      v30 = 95;
      goto LABEL_29;
    }
    ATL::CComPtrBase<Windows::Data::Json::IJsonValueStatics>::~CComPtrBase<Windows::Data::Json::IJsonValueStatics>(&v49);
    v20 = v45;
  }
  v36 = v50;
  if ( v50 )
  {
    v37 = *(__int64 (__fastcall **)(__int64, __int64, struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v20 + 56LL);
    v52 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"perf", 5u, 4u);
    v17 = v37(v20, v52, v36);
    v7 = v17;
    if ( v17 < 0 )
    {
      v18 = 100;
      goto LABEL_18;
    }
    v20 = v45;
  }
  v48 = 0;
  v38 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v20)(
          v20,
          &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e,
          &v48);
  v7 = v38;
  if ( v38 < 0 )
  {
    v39 = (unsigned int)v38;
    v40 = 104;
LABEL_50:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v40,
      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\matshelpers.cpp",
      (const char *)v39,
      v44);
    v32 = &v48;
    goto LABEL_51;
  }
  v41 = v48;
  if ( !v48 )
  {
    v40 = 105;
LABEL_48:
    v7 = -2147024882;
    goto LABEL_49;
  }
  v42 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v48 + 56LL);
  WindowsDeleteString(*a3);
  *a3 = 0;
  v7 = v42(v41, a3);
  if ( (v7 & 0x80000000) != 0 )
  {
    WindowsDeleteString(*a3);
    *a3 = 0;
    v40 = 110;
LABEL_49:
    v39 = v7;
    goto LABEL_50;
  }
  if ( !*a3 )
  {
    v40 = 113;
    goto LABEL_48;
  }
  ATL::CComPtrBase<Windows::Data::Json::IJsonValueStatics>::~CComPtrBase<Windows::Data::Json::IJsonValueStatics>(&v48);
  ATL::CComPtrBase<Windows::Data::Json::IJsonValueStatics>::~CComPtrBase<Windows::Data::Json::IJsonValueStatics>(&v45);
  ATL::CComPtrBase<Windows::Data::Json::IJsonValueStatics>::~CComPtrBase<Windows::Data::Json::IJsonValueStatics>((__int64 *)&v46);
  ATL::CComPtrBase<Windows::Data::Json::IJsonValueStatics>::~CComPtrBase<Windows::Data::Json::IJsonValueStatics>(&v44);
  ATL::CComPtrBase<Windows::Data::Json::IJsonValueStatics>::~CComPtrBase<Windows::Data::Json::IJsonValueStatics>((__int64 *)&v50);
  return 0;
}

```

## disassembly

```asm
0x1800f14e8  mov     [rsp-28h+arg_18], rbx
0x1800f14ed  push    rbp
0x1800f14ee  push    rsi
0x1800f14ef  push    rdi
0x1800f14f0  push    r14
0x1800f14f2  push    r15
0x1800f14f4  mov     rbp, rsp
0x1800f14f7  sub     rsp, 80h
0x1800f14fe  mov     rax, cs:__security_cookie
0x1800f1505  xor     rax, rsp
0x1800f1508  mov     [rbp+var_8], rax
0x1800f150c  mov     r14, r8
0x1800f150f  mov     rbx, rdx
0x1800f1512  mov     rsi, rcx
0x1800f1515  mov     rcx, [r8]; string
0x1800f1518  call    cs:__imp_WindowsDeleteString
0x1800f151e  xor     r15d, r15d
0x1800f1521  mov     [r14], r15
0x1800f1524  mov     [rbp+var_30], r15
0x1800f1528  xor     r8d, r8d; unsigned __int64
0x1800f152b  lea     rdx, [rbp+var_30]; struct Windows::Data::Json::IJsonValue **
0x1800f152f  mov     rcx, rbx; struct Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation *
0x1800f1532  call    ?SerializeCore@RequestTelemetryOperationJsonSerializer@OnlineId@Authentication@Security@Internal@Windows@@CAJAEBVRequestTelemetryOperation@23456@PEAPEAUIJsonValue@Json@Data@6@_K@Z; Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperationJsonSerializer::SerializeCore(Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation const &,Windows::Data::Json::IJsonValue * *,unsigned __int64)
0x1800f1537  mov     ebx, eax
0x1800f1539  test    eax, eax
0x1800f153b  jns     short loc_1800F155A
0x1800f153d  mov     rcx, [rbp+28h]; this
0x1800f1541  mov     r9d, eax; char *
0x1800f1544  lea     r8, aOnecoreuapDsEx_32; "onecoreuap\\ds\\ext\\common\\lib\\cloud"...
0x1800f154b  lea     edx, [r15+39h]; void *
0x1800f154f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1554  lea     edx, [r15+42h]
0x1800f1558  jmp     short loc_1800F156A
0x1800f155a  cmp     [rbp+var_30], r15
0x1800f155e  jnz     short loc_1800F1582
0x1800f1560  mov     ebx, 8007000Eh
0x1800f1565  mov     edx, 43h ; 'C'; void *
0x1800f156a  lea     r8, aOnecoreuapDsEx_61; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800f1571  mov     r9d, ebx; char *
0x1800f1574  mov     rcx, [rbp+28h]; this
0x1800f1578  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f157d  jmp     loc_1800F18F9
0x1800f1582  mov     [rbp+var_60], r15
0x1800f1586  mov     [rbp+var_10], r15
0x1800f158a  mov     edi, 1Ch
0x1800f158f  mov     r9d, edi; unsigned int
0x1800f1592  lea     r8d, [rdi+1]; unsigned int
0x1800f1596  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1800f159d  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800f15a1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800f15a6  lea     r8, [rbp+var_60]
0x1800f15aa  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x1800f15b1  mov     rcx, [rbp+var_10]
0x1800f15b5  call    cs:__imp_RoGetActivationFactory
0x1800f15bb  mov     ebx, eax
0x1800f15bd  test    eax, eax
0x1800f15bf  jns     short loc_1800F15DC
0x1800f15c1  mov     r9d, eax; char *
0x1800f15c4  lea     edx, [rdi+31h]; void *
0x1800f15c7  lea     r8, aOnecoreuapDsEx_61; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800f15ce  mov     rcx, [rbp+28h]; this
0x1800f15d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f15d7  jmp     loc_1800F18EF
0x1800f15dc  cmp     [rbp+var_60], r15
0x1800f15e0  jnz     short loc_1800F15F1
0x1800f15e2  mov     ebx, 8007000Eh
0x1800f15e7  mov     r9d, ebx
0x1800f15ea  mov     edx, 4Eh ; 'N'
0x1800f15ef  jmp     short loc_1800F15C7
0x1800f15f1  mov     [rbp+var_50], r15
0x1800f15f5  mov     [rbp+var_10], r15
0x1800f15f9  mov     r9d, 1Bh; unsigned int
0x1800f15ff  mov     r8d, edi; unsigned int
0x1800f1602  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x1800f1609  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800f160d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800f1612  lea     r8, [rbp+var_50]
0x1800f1616  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x1800f161d  mov     rcx, [rbp+var_10]
0x1800f1621  call    cs:__imp_RoGetActivationFactory
0x1800f1627  mov     ebx, eax
0x1800f1629  test    eax, eax
0x1800f162b  jns     short loc_1800F164A
0x1800f162d  mov     r9d, eax; char *
0x1800f1630  mov     edx, 53h ; 'S'; void *
0x1800f1635  lea     r8, aOnecoreuapDsEx_61; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800f163c  mov     rcx, [rbp+28h]; this
0x1800f1640  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1645  jmp     loc_1800F18E5
0x1800f164a  cmp     [rbp+var_50], r15
0x1800f164e  jnz     short loc_1800F165F
0x1800f1650  mov     ebx, 8007000Eh
0x1800f1655  mov     r9d, ebx
0x1800f1658  mov     edx, 54h ; 'T'
0x1800f165d  jmp     short loc_1800F1635
0x1800f165f  mov     [rbp+var_58], r15
0x1800f1663  mov     rdi, [rbp+var_60]
0x1800f1667  mov     rax, [rdi]
0x1800f166a  mov     rbx, [rax+30h]
0x1800f166e  mov     [rbp+var_10], r15
0x1800f1672  mov     r9d, 2; unsigned int
0x1800f1678  lea     r8d, [r9+1]; unsigned int
0x1800f167c  lea     rdx, sourceString; "{}"
0x1800f1683  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800f1687  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800f168c  nop
0x1800f168d  lea     r8, [rbp+var_58]
0x1800f1691  mov     rdx, [rbp+var_10]
0x1800f1695  mov     rcx, rdi
0x1800f1698  mov     rax, rbx
0x1800f169b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f16a0  mov     ebx, eax
0x1800f16a2  test    eax, eax
0x1800f16a4  jns     short loc_1800F16C3
0x1800f16a6  mov     edx, 57h ; 'W'; void *
0x1800f16ab  mov     r9d, eax; char *
0x1800f16ae  mov     rcx, [rbp+28h]; this
0x1800f16b2  lea     r8, aOnecoreuapDsEx_61; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800f16b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f16be  jmp     loc_1800F18DB
0x1800f16c3  mov     rbx, [rbp+var_58]
0x1800f16c7  test    rbx, rbx
0x1800f16ca  jnz     short loc_1800F16DB
0x1800f16cc  mov     ebx, 8007000Eh
0x1800f16d1  mov     r9d, ebx
0x1800f16d4  mov     edx, 58h ; 'X'
0x1800f16d9  jmp     short loc_1800F16AE
0x1800f16db  mov     rdi, [rsi]
0x1800f16de  cmp     [rdi-10h], r15d
0x1800f16e2  jz      loc_1800F17E4
0x1800f16e8  mov     [rbp+var_38], r15
0x1800f16ec  mov     rbx, [rbp+var_50]
0x1800f16f0  mov     rsi, [rbx]
0x1800f16f3  mov     [rbp+var_10], r15
0x1800f16f7  mov     [rbp+var_48], r15d
0x1800f16fb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800f16ff  inc     rcx; unsigned __int64
0x1800f1702  cmp     [rdi+rcx*2], r15w
0x1800f1707  jnz     short loc_1800F16FF
0x1800f1709  lea     rdx, [rbp+var_48]; unsigned int *
0x1800f170d  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800f1712  test    eax, eax
0x1800f1714  jns     short loc_1800F171E
0x1800f1716  mov     ecx, eax; this
0x1800f1718  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800f171d  int     3; Trap to Debugger
0x1800f171e  mov     ecx, [rbp+var_48]; unsigned int
0x1800f1721  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800f1726  mov     r9d, [rbp+var_48]; unsigned int
0x1800f172a  mov     r8d, eax; unsigned int
0x1800f172d  mov     rdx, rdi; sourceString
0x1800f1730  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800f1734  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800f1739  nop
0x1800f173a  lea     r8, [rbp+var_38]
0x1800f173e  mov     rdx, [rbp+var_10]
0x1800f1742  mov     rcx, rbx
0x1800f1745  mov     rax, [rsi+50h]
0x1800f1749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f174e  mov     ebx, eax
0x1800f1750  test    eax, eax
0x1800f1752  jns     short loc_1800F1776
0x1800f1754  mov     edx, 5Dh ; ']'; void *
0x1800f1759  mov     r9d, eax; char *
0x1800f175c  mov     rcx, [rbp+28h]; this
0x1800f1760  lea     r8, aOnecoreuapDsEx_61; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800f1767  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f176c  nop
0x1800f176d  lea     rcx, [rbp+var_38]
0x1800f1771  jmp     loc_1800F18D5
0x1800f1776  mov     rbx, [rbp+var_38]
0x1800f177a  test    rbx, rbx
0x1800f177d  jnz     short loc_1800F178E
0x1800f177f  mov     ebx, 8007000Eh
0x1800f1784  mov     r9d, ebx
0x1800f1787  mov     edx, 5Eh ; '^'
0x1800f178c  jmp     short loc_1800F175C
0x1800f178e  mov     rsi, [rbp+var_58]
0x1800f1792  mov     rax, [rsi]
0x1800f1795  mov     rdi, [rax+38h]
0x1800f1799  mov     [rbp+var_10], r15
0x1800f179d  mov     r9d, 4; unsigned int
0x1800f17a3  lea     r8d, [r9+1]; unsigned int
0x1800f17a7  lea     rdx, aMats; "MATS"
0x1800f17ae  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800f17b2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800f17b7  nop
0x1800f17b8  mov     r8, rbx
0x1800f17bb  mov     rdx, [rbp+var_10]
0x1800f17bf  mov     rcx, rsi
0x1800f17c2  mov     rax, rdi
0x1800f17c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f17ca  mov     ebx, eax
0x1800f17cc  test    eax, eax
0x1800f17ce  jns     short loc_1800F17D7
0x1800f17d0  mov     edx, 5Fh ; '_'
0x1800f17d5  jmp     short loc_1800F1759
0x1800f17d7  lea     rcx, [rbp+var_38]
0x1800f17db  call    ??1?$CComPtrBase@UIJsonValueStatics@Json@Data@Windows@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Windows::Data::Json::IJsonValueStatics>::~CComPtrBase<Windows::Data::Json::IJsonValueStatics>(void)
0x1800f17e0  mov     rbx, [rbp+var_58]
0x1800f17e4  mov     rdi, [rbp+var_30]
0x1800f17e8  test    rdi, rdi
0x1800f17eb  jz      short loc_1800F1839
0x1800f17ed  mov     rax, [rbx]
0x1800f17f0  mov     rsi, [rax+38h]
0x1800f17f4  mov     [rbp+var_10], r15
0x1800f17f8  mov     r9d, 4; unsigned int
0x1800f17fe  lea     r8d, [r9+1]; unsigned int
0x1800f1802  lea     rdx, aPerf; "perf"
0x1800f1809  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800f180d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800f1812  nop
0x1800f1813  mov     r8, rdi
0x1800f1816  mov     rdx, [rbp+var_10]
0x1800f181a  mov     rcx, rbx
0x1800f181d  mov     rax, rsi
0x1800f1820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1825  mov     ebx, eax
0x1800f1827  test    eax, eax
0x1800f1829  jns     short loc_1800F1835
0x1800f182b  mov     edx, 64h ; 'd'
0x1800f1830  jmp     loc_1800F16AB
0x1800f1835  mov     rbx, [rbp+var_58]
0x1800f1839  mov     [rbp+var_40], r15
0x1800f183d  mov     rax, [rbx]
0x1800f1840  lea     r8, [rbp+var_40]
0x1800f1844  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x1800f184b  mov     rcx, rbx
0x1800f184e  mov     rax, [rax]
0x1800f1851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1856  mov     ebx, eax
0x1800f1858  test    eax, eax
0x1800f185a  jns     short loc_1800F1866
0x1800f185c  mov     r9d, eax
0x1800f185f  mov     edx, 68h ; 'h'
0x1800f1864  jmp     short loc_1800F18C0
0x1800f1866  mov     rbx, [rbp+var_40]
0x1800f186a  test    rbx, rbx
0x1800f186d  jnz     short loc_1800F1874
0x1800f186f  lea     edx, [rbx+69h]
0x1800f1872  jmp     short loc_1800F18B8
0x1800f1874  mov     rax, [rbx]
0x1800f1877  mov     rdi, [rax+38h]
0x1800f187b  mov     rcx, [r14]; string
0x1800f187e  call    cs:__imp_WindowsDeleteString
0x1800f1884  mov     [r14], r15
0x1800f1887  mov     rdx, r14
0x1800f188a  mov     rcx, rbx
0x1800f188d  mov     rax, rdi
0x1800f1890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1895  mov     ebx, eax
0x1800f1897  test    eax, eax
0x1800f1899  jns     short loc_1800F18AE
0x1800f189b  mov     rcx, [r14]; string
0x1800f189e  call    cs:__imp_WindowsDeleteString
0x1800f18a4  mov     [r14], r15
0x1800f18a7  mov     edx, 6Eh ; 'n'
0x1800f18ac  jmp     short loc_1800F18BD
0x1800f18ae  cmp     [r14], r15
0x1800f18b1  jnz     short loc_1800F1906
0x1800f18b3  mov     edx, 71h ; 'q'; void *
0x1800f18b8  mov     ebx, 8007000Eh
0x1800f18bd  mov     r9d, ebx; char *
0x1800f18c0  lea     r8, aOnecoreuapDsEx_61; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800f18c7  mov     rcx, [rbp+28h]; this
0x1800f18cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f18d0  nop
0x1800f18d1  lea     rcx, [rbp+var_40]
0x1800f18d5  call    ??1?$CComPtrBase@UIJsonValueStatics@Json@Data@Windows@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Windows::Data::Json::IJsonValueStatics>::~CComPtrBase<Windows::Data::Json::IJsonValueStatics>(void)
0x1800f18da  nop
0x1800f18db  lea     rcx, [rbp+var_58]
0x1800f18df  call    ??1?$CComPtrBase@UIJsonValueStatics@Json@Data@Windows@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Windows::Data::Json::IJsonValueStatics>::~CComPtrBase<Windows::Data::Json::IJsonValueStatics>(void)
0x1800f18e4  nop
0x1800f18e5  lea     rcx, [rbp+var_50]
0x1800f18e9  call    ??1?$CComPtrBase@UIJsonValueStatics@Json@Data@Windows@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Windows::Data::Json::IJsonValueStatics>::~CComPtrBase<Windows::Data::Json::IJsonValueStatics>(void)
0x1800f18ee  nop
0x1800f18ef  lea     rcx, [rbp+var_60]
0x1800f18f3  call    ??1?$CComPtrBase@UIJsonValueStatics@Json@Data@Windows@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Windows::Data::Json::IJsonValueStatics>::~CComPtrBase<Windows::Data::Json::IJsonValueStatics>(void)
0x1800f18f8  nop
0x1800f18f9  lea     rcx, [rbp+var_30]
0x1800f18fd  call    ??1?$CComPtrBase@UIJsonValueStatics@Json@Data@Windows@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Windows::Data::Json::IJsonValueStatics>::~CComPtrBase<Windows::Data::Json::IJsonValueStatics>(void)
0x1800f1902  mov     eax, ebx
0x1800f1904  jmp     short loc_1800F1939
0x1800f1906  lea     rcx, [rbp+var_40]
0x1800f190a  call    ??1?$CComPtrBase@UIJsonValueStatics@Json@Data@Windows@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Windows::Data::Json::IJsonValueStatics>::~CComPtrBase<Windows::Data::Json::IJsonValueStatics>(void)
0x1800f190f  nop
0x1800f1910  lea     rcx, [rbp+var_58]
0x1800f1914  call    ??1?$CComPtrBase@UIJsonValueStatics@Json@Data@Windows@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Windows::Data::Json::IJsonValueStatics>::~CComPtrBase<Windows::Data::Json::IJsonValueStatics>(void)
0x1800f1919  nop
0x1800f191a  lea     rcx, [rbp+var_50]
0x1800f191e  call    ??1?$CComPtrBase@UIJsonValueStatics@Json@Data@Windows@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Windows::Data::Json::IJsonValueStatics>::~CComPtrBase<Windows::Data::Json::IJsonValueStatics>(void)
0x1800f1923  nop
0x1800f1924  lea     rcx, [rbp+var_60]
0x1800f1928  call    ??1?$CComPtrBase@UIJsonValueStatics@Json@Data@Windows@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Windows::Data::Json::IJsonValueStatics>::~CComPtrBase<Windows::Data::Json::IJsonValueStatics>(void)
0x1800f192d  nop
0x1800f192e  lea     rcx, [rbp+var_30]
0x1800f1932  call    ??1?$CComPtrBase@UIJsonValueStatics@Json@Data@Windows@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Windows::Data::Json::IJsonValueStatics>::~CComPtrBase<Windows::Data::Json::IJsonValueStatics>(void)
0x1800f1937  xor     eax, eax
0x1800f1939  mov     rcx, [rbp+var_8]
0x1800f193d  xor     rcx, rsp; StackCookie
  ... truncated ...
```
