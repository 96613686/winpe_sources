# Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperationJsonSerializer::SerializeCore(Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation const &,Windows::Data::Json::IJsonValue * *,Windows::Data::Json::IJsonObjectStatics *,Windows::Data::Json::IJsonValueStatics *,Windows::Data::Json::IJsonArrayStatics *,unsigned __int64)

- ea: `0x18010b754`
- end: `0x18010c00d`
- name: `?SerializeCore@RequestTelemetryOperationJsonSerializer@OnlineId@Authentication@Security@Internal@Windows@@CAJAEBVRequestTelemetryOperation@23456@PEAPEAUIJsonValue@Json@Data@6@PEAUIJsonObjectStatics@9Data@6@PEAUIJsonValueStatics@9Data@6@PEAUIJsonArrayStatics@9Data@6@_K@Z`
- size: `2233`
- prototype: `__int64 __fastcall(const struct Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation *, struct Windows::Data::Json::IJsonValue **, struct Windows::Data::Json::IJsonObjectStatics *, struct Windows::Data::Json::IJsonValueStatics *, struct Windows::Data::Json::IJsonArrayStatics *, unsigned __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007ddf4`
- `0x18010b754`

## callees

- `0x18002d36c`
- `0x18007e210`
- `0x18007e27c`
- `0x18007fd90`
- `0x18007fdec`
- `0x18007fe18`
- `0x1800a3b60`
- `0x1800ab414`
- `0x18010b754`
- `0x18010c014`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18010b9a9`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18010bb51`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18010b9a9`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18010bb51`

## string_xrefs

- `0x18010b7f6`: `onecoreuap\ds\ext\common\lib\cloudidentitymatscommon\requesttelemetryoperationjsonserializer.cpp`
- `0x18010b83a`: `onecoreuap\ds\ext\common\lib\cloudidentitymatscommon\requesttelemetryoperationjsonserializer.cpp`
- `0x18010b900`: `onecoreuap\ds\ext\common\lib\cloudidentitymatscommon\requesttelemetryoperationjsonserializer.cpp`
- `0x18010ba28`: `onecoreuap\ds\ext\common\lib\cloudidentitymatscommon\requesttelemetryoperationjsonserializer.cpp`
- `0x18010bab0`: `onecoreuap\ds\ext\common\lib\cloudidentitymatscommon\requesttelemetryoperationjsonserializer.cpp`
- `0x18010bb1e`: `onecoreuap\ds\ext\common\lib\cloudidentitymatscommon\requesttelemetryoperationjsonserializer.cpp`
- `0x18010bb96`: `onecoreuap\ds\ext\common\lib\cloudidentitymatscommon\requesttelemetryoperationjsonserializer.cpp`
- `0x18010bcb1`: `onecoreuap\ds\ext\common\lib\cloudidentitymatscommon\requesttelemetryoperationjsonserializer.cpp`
- `0x18010bd08`: `onecoreuap\ds\ext\common\lib\cloudidentitymatscommon\requesttelemetryoperationjsonserializer.cpp`
- `0x18010bda6`: `onecoreuap\ds\ext\common\lib\cloudidentitymatscommon\requesttelemetryoperationjsonserializer.cpp`
- `0x18010be35`: `onecoreuap\ds\ext\common\lib\cloudidentitymatscommon\requesttelemetryoperationjsonserializer.cpp`
- `0x18010bf05`: `onecoreuap\ds\ext\common\lib\cloudidentitymatscommon\requesttelemetryoperationjsonserializer.cpp`
- `0x18010bfb3`: `onecoreuap\ds\ext\common\lib\cloudidentitymatscommon\requesttelemetryoperationjsonserializer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperationJsonSerializer::SerializeCore(
        const struct Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation *a1,
        struct Windows::Data::Json::IJsonValue **a2,
        struct Windows::Data::Json::IJsonObjectStatics *a3,
        struct Windows::Data::Json::IJsonValueStatics *a4,
        struct Windows::Data::Json::IJsonArrayStatics *a5,
        unsigned __int64 a6)
{
  __int64 (__fastcall *v9)(struct Windows::Data::Json::IJsonObjectStatics *, __int64, _QWORD); // rbx
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r9
  struct Windows::Data::Json::IJsonValue **v17; // rbx
  __int64 (__fastcall ***v18)(_QWORD, _QWORD, _QWORD); // rsi
  __int64 (__fastcall *v19)(_QWORD, GUID *, struct Windows::Data::Json::IJsonValue **); // rdi
  __int64 (__fastcall *v20)(struct Windows::Data::Json::IJsonArrayStatics *, __int64, _QWORD); // rbx
  int v21; // eax
  __int64 v22; // r9
  __int64 v23; // rdx
  bool v24; // di
  int v25; // eax
  unsigned __int64 v26; // r9
  __int64 v27; // rdx
  __int64 (__fastcall *v28)(struct Windows::Data::Json::IJsonValueStatics *, _QWORD, struct Windows::Data::Json::IJsonValue **); // rbx
  __int64 v29; // rax
  int v30; // eax
  int v31; // eax
  __int64 v32; // rdx
  char IsEnabled; // al
  char v34; // cl
  bool v35; // zf
  unsigned __int64 v36; // rcx
  int v37; // eax
  __int64 v38; // rdx
  struct Windows::Data::Json::IJsonValue **v39; // rcx
  struct Windows::Data::Json::IJsonValue **v40; // rcx
  int v41; // eax
  __int64 v42; // rdx
  __int64 (__fastcall *v43)(struct Windows::Data::Json::IJsonValueStatics *, _QWORD, __int64 *); // rbx
  __int64 v44; // rax
  int v45; // eax
  __int64 v46; // rdx
  __int64 v47; // r9
  __int64 (__fastcall ***v48)(_QWORD, _QWORD, _QWORD); // rsi
  __int64 (__fastcall *v49)(_QWORD, GUID *, struct Windows::Data::Json::IJsonValue **); // rdi
  struct Windows::Data::Json::IJsonValue **v50; // rbx
  __int64 (__fastcall *v51)(struct Windows::Data::Json::IJsonArrayStatics *, __int64, _QWORD); // rbx
  int v52; // eax
  __int64 v53; // r9
  __int64 v54; // rdx
  int v55; // eax
  _QWORD *v56; // rdi
  _QWORD *v57; // rbx
  struct Windows::Data::Json::IJsonObjectStatics *v58; // r14
  int v59; // esi
  __int64 v60; // rdx
  int v61; // eax
  __int64 v62; // rdx
  __int64 (__fastcall ***v63)(_QWORD, _QWORD, _QWORD); // rsi
  __int64 (__fastcall *v64)(_QWORD, GUID *, struct Windows::Data::Json::IJsonValue **); // rdi
  struct Windows::Data::Json::IJsonValue **v65; // rbx
  __int64 (__fastcall ***v66)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v67)(_QWORD, GUID *, struct Windows::Data::Json::IJsonValue **); // rdi
  int v68; // eax
  struct Windows::Data::Json::IJsonValue *v69; // rax
  int v71; // [rsp+20h] [rbp-E0h]
  struct Windows::Data::Json::IJsonValue **v72; // [rsp+30h] [rbp-D0h] BYREF
  __int64 (__fastcall ***v73)(_QWORD, GUID *, __int64); // [rsp+38h] [rbp-C8h] BYREF
  struct Windows::Data::Json::IJsonValue *v74; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v75; // [rsp+48h] [rbp-B8h] BYREF
  struct Windows::Data::Json::IJsonValue **v76; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v77)(_QWORD, GUID *, __int64); // [rsp+58h] [rbp-A8h] BYREF
  struct Windows::Data::Json::IJsonValue *v78; // [rsp+60h] [rbp-A0h] BYREF
  __int64 (__fastcall ***v79)(_QWORD, GUID *, struct Windows::Data::Json::IJsonValue **); // [rsp+68h] [rbp-98h] BYREF
  __int64 v80; // [rsp+70h] [rbp-90h] BYREF
  __int64 v81; // [rsp+78h] [rbp-88h] BYREF
  struct Windows::Data::Json::IJsonValue *v82; // [rsp+80h] [rbp-80h] BYREF
  struct Windows::Data::Json::IJsonValue **v83; // [rsp+88h] [rbp-78h] BYREF
  struct Windows::Data::Json::IJsonObjectStatics *v84; // [rsp+90h] [rbp-70h]
  struct Windows::Data::Json::IJsonValue **v85; // [rsp+98h] [rbp-68h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  GUID *v87; // [rsp+B8h] [rbp-48h]
  WCHAR sourceString[24]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v84 = a3;
  v85 = a2;
  v79 = 0;
  v9 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObjectStatics *, __int64, _QWORD))(*(_QWORD *)a3 + 48LL);
  v87 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"{}", 3u, 2u);
  v10 = v9(a3, (__int64)v87, &v79);
  v11 = v10;
  if ( v10 >= 0 )
  {
    if ( !v79 )
    {
      v11 = -2147024882;
      v12 = 2147942414LL;
      v13 = 134;
      goto LABEL_5;
    }
    v72 = 0;
    v14 = (*(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonValueStatics *, _QWORD, struct Windows::Data::Json::IJsonValue ***))(*(_QWORD *)a4 + 80LL))(
            a4,
            *((_QWORD *)a1 + 3),
            &v72);
    v11 = v14;
    if ( v14 < 0 )
    {
      v15 = 137;
LABEL_8:
      v16 = (unsigned int)v14;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecoreuap\\ds\\ext\\common\\lib\\cloudidentitymatscommon\\requesttelemetryoperationjsonserializer.cpp",
        (const char *)v16,
        v71);
LABEL_98:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v72);
      goto LABEL_99;
    }
    v17 = v72;
    if ( !v72 )
    {
      v11 = -2147024882;
      v16 = 2147942414LL;
      v15 = 138;
      goto LABEL_9;
    }
    v18 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v79;
    v19 = (*v79)[7];
    v87 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"n", 2u, 1u);
    v14 = v19(v18, v87, v17);
    v11 = v14;
    if ( v14 < 0 )
    {
      v15 = 140;
      goto LABEL_8;
    }
    v73 = 0;
    v20 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonArrayStatics *, __int64, _QWORD))(*(_QWORD *)a5 + 48LL);
    v87 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"[]", 3u, 2u);
    v21 = v20(a5, (__int64)v87, &v73);
    v11 = v21;
    if ( v21 < 0 )
    {
      v22 = (unsigned int)v21;
      v23 = 143;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecoreuap\\ds\\ext\\common\\lib\\cloudidentitymatscommon\\requesttelemetryoperationjsonserializer.cpp",
        (const char *)v22,
        v71);
LABEL_97:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v73);
      goto LABEL_98;
    }
    if ( !v73 )
    {
      v11 = -2147024882;
      v22 = 2147942414LL;
      v23 = 144;
      goto LABEL_16;
    }
    v24 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::GetImpl'::`2'::impl) )
      v24 = a6 == 0;
    v74 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::GetImpl'::`2'::impl) )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v74);
      v25 = Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperationJsonSerializer::SerializeTime(
              *(_QWORD *)a1 - a6,
              v24,
              a4,
              &v74);
      v11 = v25;
      if ( v25 < 0 )
      {
        v26 = (unsigned int)v25;
        v27 = 159;
LABEL_95:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v27,
          (unsigned int)"onecoreuap\\ds\\ext\\common\\lib\\cloudidentitymatscommon\\requesttelemetryoperationjsonserializer.cpp",
          (const char *)v26,
          v71);
        goto LABEL_96;
      }
      goto LABEL_29;
    }
    if ( (unsigned int)_o__ui64tow_s(*(_QWORD *)a1 - a6, sourceString, 21) )
    {
      v11 = -2147418113;
      v27 = 163;
    }
    else
    {
      v28 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonValueStatics *, _QWORD, struct Windows::Data::Json::IJsonValue **))(*(_QWORD *)a4 + 80LL);
      v29 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, sourceString);
      v30 = v28(a4, *(_QWORD *)(v29 + 24), &v74);
      v11 = v30;
      if ( v30 < 0 )
      {
        v26 = (unsigned int)v30;
        v27 = 164;
        goto LABEL_95;
      }
      if ( v74 )
      {
LABEL_29:
        v75 = 0;
        v31 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
                &v73,
                (__int64)&v75);
        v11 = v31;
        if ( v31 < 0 )
        {
          v32 = 169;
LABEL_31:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v32,
            (unsigned int)"onecoreuap\\ds\\ext\\common\\lib\\cloudidentitymatscommon\\requesttelemetryoperationjsonserializer.cpp",
            (const char *)(unsigned int)v31,
            v71);
LABEL_91:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v75);
LABEL_96:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v74);
          goto LABEL_97;
        }
        v31 = (*(__int64 (__fastcall **)(__int64, struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v75 + 104LL))(
                v75,
                v74);
        v11 = v31;
        if ( v31 < 0 )
        {
          v32 = 170;
          goto LABEL_31;
        }
        IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::GetImpl'::`2'::impl);
        v34 = *((_BYTE *)a1 + 16);
        if ( IsEnabled )
        {
          if ( v34 || *((_QWORD *)a1 + 1) )
          {
            v78 = 0;
            v35 = v34 == 0;
            v36 = 0;
            if ( v35 )
              v36 = *((_QWORD *)a1 + 1);
            v37 = Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperationJsonSerializer::SerializeTime(
                    v36,
                    v24,
                    a4,
                    &v78);
            v11 = v37;
            if ( v37 < 0 )
            {
              v38 = 181;
LABEL_41:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v38,
                (unsigned int)"onecoreuap\\ds\\ext\\common\\lib\\cloudidentitymatscommon\\requesttelemetryoperationjsonserializer.cpp",
                (const char *)(unsigned int)v37,
                v71);
              v39 = &v78;
LABEL_90:
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(v39);
              goto LABEL_91;
            }
            v37 = (*(__int64 (__fastcall **)(__int64, struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v75 + 104LL))(
                    v75,
                    v78);
            v11 = v37;
            if ( v37 < 0 )
            {
              v38 = 182;
              goto LABEL_41;
            }
            v40 = &v78;
            goto LABEL_45;
          }
LABEL_46:
          v76 = 0;
          v41 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                  &v73,
                  (__int64)&v76);
          v11 = v41;
          if ( v41 < 0 )
          {
            v42 = 198;
LABEL_48:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v42,
              (unsigned int)"onecoreuap\\ds\\ext\\common\\lib\\cloudidentitymatscommon\\requesttelemetryoperationjsonserializer.cpp",
              (const char *)(unsigned int)v41,
              v71);
LABEL_89:
            v39 = (struct Windows::Data::Json::IJsonValue **)&v76;
            goto LABEL_90;
          }
          v48 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v79;
          v49 = (*v79)[7];
          v50 = v76;
          v87 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"t", 2u, 1u);
          v41 = v49(v48, v87, v50);
          v11 = v41;
          if ( v41 < 0 )
          {
            v42 = 199;
            goto LABEL_48;
          }
          if ( *((_QWORD *)a1 + 5) )
          {
            v77 = 0;
            v51 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonArrayStatics *, __int64, _QWORD))(*(_QWORD *)a5 + 48LL);
            v87 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"[]", 3u, 2u);
            v52 = v51(a5, (__int64)v87, &v77);
            v11 = v52;
            if ( v52 < 0 )
            {
              v53 = (unsigned int)v52;
              v54 = 204;
LABEL_66:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v54,
                (unsigned int)"onecoreuap\\ds\\ext\\common\\lib\\cloudidentitymatscommon\\requesttelemetryoperationjsonserializer.cpp",
                (const char *)v53,
                v71);
LABEL_67:
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v77);
              goto LABEL_89;
            }
            if ( !v77 )
            {
              v11 = -2147024882;
              v53 = 2147942414LL;
              v54 = 205;
              goto LABEL_66;
            }
            v80 = 0;
            v55 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
                    &v77,
                    (__int64)&v80);
            v11 = v55;
            if ( v55 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xD0,
                (unsigned int)"onecoreuap\\ds\\ext\\common\\lib\\cloudidentitymatscommon\\requesttelemetryoperationjsonserializer.cpp",
                (const char *)(unsigned int)v55,
                v71);
LABEL_72:
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v80);
              goto LABEL_67;
            }
            v56 = (_QWORD *)*((_QWORD *)a1 + 4);
            v57 = (_QWORD *)*v56;
            v58 = v84;
            while ( v57 != v56 )
            {
              v78 = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v78);
              v59 = Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperationJsonSerializer::SerializeCore(
                      (const struct Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation *)(v57 + 2),
                      &v78,
                      v58,
                      a4,
                      a5,
                      a6);
              if ( v59 < 0 )
              {
                v60 = 213;
                goto LABEL_80;
              }
              v59 = (*(__int64 (__fastcall **)(__int64, struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v80 + 104LL))(
                      v80,
                      v78);
              if ( v59 < 0 )
              {
                v60 = 214;
LABEL_80:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v60,
                  (unsigned int)"onecoreuap\\ds\\ext\\common\\lib\\cloudidentitymatscommon\\requesttelemetryoperationjsonserializer.cpp",
                  (const char *)(unsigned int)v59,
                  v71);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v78);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v80);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v77);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v76);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v75);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v74);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v73);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v72);
                v11 = v59;
                goto LABEL_99;
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v78);
              v57 = (_QWORD *)*v57;
            }
            v83 = 0;
            v61 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                    &v77,
                    (__int64)&v83);
            v11 = v61;
            if ( v61 < 0 )
            {
              v62 = 218;
LABEL_83:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v62,
                (unsigned int)"onecoreuap\\ds\\ext\\common\\lib\\cloudidentitymatscommon\\requesttelemetryoperationjsonserializer.cpp",
                (const char *)(unsigned int)v61,
                v71);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v83);
              goto LABEL_72;
            }
            v63 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v79;
            v64 = (*v79)[7];
            v65 = v83;
            v87 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"s", 2u, 1u);
            v61 = v64(v63, v87, v65);
            v11 = v61;
            if ( v61 < 0 )
            {
              v62 = 219;
              goto LABEL_83;
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v83);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v80);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v77);
          }
          v82 = 0;
          v66 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v79;
          v67 = **v79;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v82);
          v68 = v67(v66, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v82);
          v11 = v68;
          if ( v68 >= 0 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v79);
            v69 = v82;
            v82 = 0;
            *v85 = v69;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v82);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v76);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v75);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v74);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v73);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v72);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v79);
            return 0;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xDF,
            (unsigned int)"onecoreuap\\ds\\ext\\common\\lib\\cloudidentitymatscommon\\requesttelemetryoperationjsonserializer.cpp",
            (const char *)(unsigned int)v68,
            v71);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v82);
          goto LABEL_89;
        }
        if ( v34 )
          goto LABEL_46;
        v81 = 0;
        if ( (unsigned int)_o__ui64tow_s(*((_QWORD *)a1 + 1), sourceString, 21) )
        {
          v11 = -2147418113;
          v47 = 2147549183LL;
          v46 = 190;
          goto LABEL_54;
        }
        v43 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonValueStatics *, _QWORD, __int64 *))(*(_QWORD *)a4 + 80LL);
        v44 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, sourceString);
        v45 = v43(a4, *(_QWORD *)(v44 + 24), &v81);
        v11 = v45;
        if ( v45 >= 0 )
        {
          if ( !v81 )
          {
            v11 = -2147024882;
            v47 = 2147942414LL;
            v46 = 192;
            goto LABEL_54;
          }
          v45 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v75 + 104LL))(v75);
          v11 = v45;
          if ( v45 >= 0 )
          {
            v40 = (struct Windows::Data::Json::IJsonValue **)&v81;
LABEL_45:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(v40);
            goto LABEL_46;
          }
          v46 = 193;
        }
        else
        {
          v46 = 191;
        }
        v47 = (unsigned int)v45;
LABEL_54:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v46,
          (unsigned int)"onecoreuap\\ds\\ext\\common\\lib\\cloudidentitymatscommon\\requesttelemetryoperationjsonserializer.cpp",
          (const char *)v47,
          v71);
        v39 = (struct Windows::Data::Json::IJsonValue **)&v81;
        goto LABEL_90;
      }
      v11 = -2147024882;
      v27 = 165;
    }
    v26 = v11;
    goto LABEL_95;
  }
  v12 = (unsigned int)v10;
  v13 = 133;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"onecoreuap\\ds\\ext\\common\\lib\\cloudidentitymatscommon\\requesttelemetryoperationjsonserializer.cpp",
    (const char *)v12,
    v71);
LABEL_99:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v79);
  return v11;
}

```

## disassembly

```asm
0x18010b754  push    rbp
0x18010b756  push    rbx
0x18010b757  push    rsi
0x18010b758  push    rdi
0x18010b759  push    r12
0x18010b75b  push    r13
0x18010b75d  push    r14
0x18010b75f  push    r15
0x18010b761  lea     rbp, [rsp-8]
0x18010b766  sub     rsp, 108h
0x18010b76d  mov     rax, cs:__security_cookie
0x18010b774  xor     rax, rsp
0x18010b777  mov     [rbp+40h+var_50], rax
0x18010b77b  mov     r15, r9
0x18010b77e  mov     rdi, r8
0x18010b781  mov     [rbp+40h+var_B0], r8
0x18010b785  mov     [rbp+40h+var_A8], rdx
0x18010b789  mov     r14, rcx
0x18010b78c  mov     r13, [rbp+40h+arg_20]
0x18010b790  xor     r12d, r12d
0x18010b793  mov     [rsp+140h+var_D8], r12
0x18010b798  mov     rax, [r8]
0x18010b79b  mov     rbx, [rax+30h]
0x18010b79f  mov     [rbp+40h+var_88], r12
0x18010b7a3  lea     r9d, [r12+2]; unsigned int
0x18010b7a8  lea     r8d, [r12+3]; unsigned int
0x18010b7ad  lea     rdx, sourceString; "{}"
0x18010b7b4  lea     rcx, [rbp+40h+hstringHeader]; hstringHeader
0x18010b7b8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18010b7bd  nop
0x18010b7be  lea     r8, [rsp+140h+var_D8]
0x18010b7c3  mov     rdx, [rbp+40h+var_88]
0x18010b7c7  mov     rcx, rdi
0x18010b7ca  mov     rax, rbx
0x18010b7cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010b7d2  mov     ebx, eax
0x18010b7d4  test    eax, eax
0x18010b7d6  jns     short loc_18010B7E2
0x18010b7d8  mov     r9d, eax
0x18010b7db  mov     edx, 85h
0x18010b7e0  jmp     short loc_18010B7F6
0x18010b7e2  cmp     [rsp+140h+var_D8], r12
0x18010b7e7  jnz     short loc_18010B80B
0x18010b7e9  mov     ebx, 8007000Eh
0x18010b7ee  mov     r9d, ebx; char *
0x18010b7f1  mov     edx, 86h; void *
0x18010b7f6  lea     r8, aOnecoreuapDsEx_32; "onecoreuap\\ds\\ext\\common\\lib\\cloud"...
0x18010b7fd  mov     rcx, [rbp+48h]; this
0x18010b801  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010b806  jmp     loc_18010BFE1
0x18010b80b  mov     [rsp+140h+var_110], r12
0x18010b810  mov     rax, [r15]
0x18010b813  lea     r8, [rsp+140h+var_110]
0x18010b818  mov     rdx, [r14+18h]
0x18010b81c  mov     rcx, r15
0x18010b81f  mov     rax, [rax+50h]
0x18010b823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010b828  mov     ebx, eax
0x18010b82a  test    eax, eax
0x18010b82c  jns     short loc_18010B84B
0x18010b82e  mov     edx, 89h; void *
0x18010b833  mov     r9d, eax; char *
0x18010b836  mov     rcx, [rbp+48h]; this
0x18010b83a  lea     r8, aOnecoreuapDsEx_32; "onecoreuap\\ds\\ext\\common\\lib\\cloud"...
0x18010b841  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010b846  jmp     loc_18010BFD6
0x18010b84b  mov     rbx, [rsp+140h+var_110]
0x18010b850  test    rbx, rbx
0x18010b853  jnz     short loc_18010B864
0x18010b855  mov     ebx, 8007000Eh
0x18010b85a  mov     r9d, ebx
0x18010b85d  mov     edx, 8Ah
0x18010b862  jmp     short loc_18010B836
0x18010b864  mov     rsi, [rsp+140h+var_D8]
0x18010b869  mov     rax, [rsi]
0x18010b86c  mov     rdi, [rax+38h]
0x18010b870  mov     [rbp+40h+var_88], r12
0x18010b874  mov     r9d, 1; unsigned int
0x18010b87a  lea     r12d, [r9+1]
0x18010b87e  mov     r8d, r12d; unsigned int
0x18010b881  lea     rdx, aN; "n"
0x18010b888  lea     rcx, [rbp+40h+hstringHeader]; hstringHeader
0x18010b88c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18010b891  nop
0x18010b892  mov     r8, rbx
0x18010b895  mov     rdx, [rbp+40h+var_88]
0x18010b899  mov     rcx, rsi
0x18010b89c  mov     rax, rdi
0x18010b89f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010b8a4  mov     ebx, eax
0x18010b8a6  xor     esi, esi
0x18010b8a8  test    eax, eax
0x18010b8aa  jns     short loc_18010B8B3
0x18010b8ac  mov     edx, 8Ch
0x18010b8b1  jmp     short loc_18010B833
0x18010b8b3  mov     [rsp+140h+var_108], rsi
0x18010b8b8  mov     rax, [r13+0]
0x18010b8bc  mov     rbx, [rax+30h]
0x18010b8c0  mov     [rbp+40h+var_88], rsi
0x18010b8c4  mov     r9d, r12d; unsigned int
0x18010b8c7  mov     r8d, 3; unsigned int
0x18010b8cd  lea     rdx, asc_18018DE54; "[]"
0x18010b8d4  lea     rcx, [rbp+40h+hstringHeader]; hstringHeader
0x18010b8d8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18010b8dd  nop
0x18010b8de  lea     r8, [rsp+140h+var_108]
0x18010b8e3  mov     rdx, [rbp+40h+var_88]
0x18010b8e7  mov     rcx, r13
0x18010b8ea  mov     rax, rbx
0x18010b8ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010b8f2  mov     ebx, eax
0x18010b8f4  test    eax, eax
0x18010b8f6  jns     short loc_18010B915
0x18010b8f8  mov     r9d, eax; char *
0x18010b8fb  mov     edx, 8Fh; void *
0x18010b900  lea     r8, aOnecoreuapDsEx_32; "onecoreuap\\ds\\ext\\common\\lib\\cloud"...
0x18010b907  mov     rcx, [rbp+48h]; this
0x18010b90b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010b910  jmp     loc_18010BFCB
0x18010b915  cmp     [rsp+140h+var_108], rsi
0x18010b91a  jnz     short loc_18010B92B
0x18010b91c  mov     ebx, 8007000Eh
0x18010b921  mov     r9d, ebx
0x18010b924  mov     edx, 90h
0x18010b929  jmp     short loc_18010B900
0x18010b92b  mov     dil, sil
0x18010b92e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry> `wil::Feature<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::GetImpl(void)'::`2'::impl
0x18010b935  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::__private_IsEnabled(void)
0x18010b93a  mov     r12, [rbp+40h+arg_28]
0x18010b93e  test    al, al
0x18010b940  jz      short loc_18010B949
0x18010b942  test    r12, r12
0x18010b945  setz    dil
0x18010b949  mov     [rsp+140h+var_100], rsi
0x18010b94e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry> `wil::Feature<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::GetImpl(void)'::`2'::impl
0x18010b955  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::__private_IsEnabled(void)
0x18010b95a  test    al, al
0x18010b95c  jz      short loc_18010B995
0x18010b95e  lea     rcx, [rsp+140h+var_100]
0x18010b963  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x18010b968  mov     rcx, [r14]
0x18010b96b  sub     rcx, r12; unsigned __int64
0x18010b96e  lea     r9, [rsp+140h+var_100]; struct Windows::Data::Json::IJsonValue **
0x18010b973  mov     r8, r15; struct Windows::Data::Json::IJsonValueStatics *
0x18010b976  mov     dl, dil; bool
0x18010b979  call    ?SerializeTime@RequestTelemetryOperationJsonSerializer@OnlineId@Authentication@Security@Internal@Windows@@CAJ_K_NPEAUIJsonValueStatics@Json@Data@6@PEAPEAUIJsonValue@896@@Z; Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperationJsonSerializer::SerializeTime(unsigned __int64,bool,Windows::Data::Json::IJsonValueStatics *,Windows::Data::Json::IJsonValue * *)
0x18010b97e  mov     ebx, eax
0x18010b980  test    eax, eax
0x18010b982  jns     loc_18010BA09
0x18010b988  mov     r9d, eax
0x18010b98b  mov     edx, 9Fh
0x18010b990  jmp     loc_18010BFAF
0x18010b995  mov     rcx, [r14]
0x18010b998  sub     rcx, r12
0x18010b99b  mov     r9d, 0Ah
0x18010b9a1  lea     r8d, [r9+0Bh]
0x18010b9a5  lea     rdx, [rbp+40h+sourceString]
0x18010b9a9  call    cs:__imp__o__ui64tow_s
0x18010b9af  test    eax, eax
0x18010b9b1  jnz     loc_18010BFA2
0x18010b9b7  mov     rax, [r15]
0x18010b9ba  mov     rbx, [rax+50h]
0x18010b9be  lea     rdx, [rbp+40h+sourceString]; sourceString
0x18010b9c2  lea     rcx, [rbp+40h+hstringHeader]; hstringHeader
0x18010b9c6  call    ??$?0$0BF@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0BF@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[21])
0x18010b9cb  nop
0x18010b9cc  lea     r8, [rsp+140h+var_100]
0x18010b9d1  mov     rdx, [rax+18h]
0x18010b9d5  mov     rcx, r15
0x18010b9d8  mov     rax, rbx
0x18010b9db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010b9e0  mov     ebx, eax
0x18010b9e2  test    eax, eax
0x18010b9e4  jns     short loc_18010B9F3
0x18010b9e6  mov     r9d, eax
0x18010b9e9  mov     edx, 0A4h
0x18010b9ee  jmp     loc_18010BFAF
0x18010b9f3  cmp     [rsp+140h+var_100], rsi
0x18010b9f8  jnz     short loc_18010BA09
0x18010b9fa  mov     ebx, 8007000Eh
0x18010b9ff  mov     edx, 0A5h
0x18010ba04  jmp     loc_18010BFAC
0x18010ba09  mov     [rsp+140h+var_F8], rsi
0x18010ba0e  lea     rdx, [rsp+140h+var_F8]
0x18010ba13  lea     rcx, [rsp+140h+var_108]
0x18010ba18  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x18010ba1d  mov     ebx, eax
0x18010ba1f  test    eax, eax
0x18010ba21  jns     short loc_18010BA40
0x18010ba23  mov     edx, 0A9h; void *
0x18010ba28  lea     r8, aOnecoreuapDsEx_32; "onecoreuap\\ds\\ext\\common\\lib\\cloud"...
0x18010ba2f  mov     r9d, eax; char *
0x18010ba32  mov     rcx, [rbp+48h]; this
0x18010ba36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010ba3b  jmp     loc_18010BF2B
0x18010ba40  mov     rcx, [rsp+140h+var_F8]
0x18010ba45  mov     rax, [rcx]
0x18010ba48  mov     rdx, [rsp+140h+var_100]
0x18010ba4d  mov     rax, [rax+68h]
0x18010ba51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ba56  mov     ebx, eax
0x18010ba58  test    eax, eax
0x18010ba5a  jns     short loc_18010BA63
0x18010ba5c  mov     edx, 0AAh
0x18010ba61  jmp     short loc_18010BA28
0x18010ba63  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry> `wil::Feature<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::GetImpl(void)'::`2'::impl
0x18010ba6a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::__private_IsEnabled(void)
0x18010ba6f  mov     cl, [r14+10h]
0x18010ba73  test    al, al
0x18010ba75  jz      loc_18010BB36
0x18010ba7b  test    cl, cl
0x18010ba7d  jnz     short loc_18010BA85
0x18010ba7f  cmp     [r14+8], rsi
0x18010ba83  jbe     short loc_18010BAFB
0x18010ba85  mov     [rsp+140h+var_E0], rsi
0x18010ba8a  test    cl, cl
0x18010ba8c  mov     rcx, rsi
0x18010ba8f  jnz     short loc_18010BA95
0x18010ba91  mov     rcx, [r14+8]; unsigned __int64
0x18010ba95  lea     r9, [rsp+140h+var_E0]; struct Windows::Data::Json::IJsonValue **
0x18010ba9a  mov     r8, r15; struct Windows::Data::Json::IJsonValueStatics *
0x18010ba9d  mov     dl, dil; bool
0x18010baa0  call    ?SerializeTime@RequestTelemetryOperationJsonSerializer@OnlineId@Authentication@Security@Internal@Windows@@CAJ_K_NPEAUIJsonValueStatics@Json@Data@6@PEAPEAUIJsonValue@896@@Z; Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperationJsonSerializer::SerializeTime(unsigned __int64,bool,Windows::Data::Json::IJsonValueStatics *,Windows::Data::Json::IJsonValue * *)
0x18010baa5  mov     ebx, eax
0x18010baa7  test    eax, eax
0x18010baa9  jns     short loc_18010BACE
0x18010baab  mov     edx, 0B5h; void *
0x18010bab0  lea     r8, aOnecoreuapDsEx_32; "onecoreuap\\ds\\ext\\common\\lib\\cloud"...
0x18010bab7  mov     r9d, eax; char *
0x18010baba  mov     rcx, [rbp+48h]; this
0x18010babe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010bac3  nop
0x18010bac4  lea     rcx, [rsp+140h+var_E0]
0x18010bac9  jmp     loc_18010BF25
0x18010bace  mov     rcx, [rsp+140h+var_F8]
0x18010bad3  mov     rax, [rcx]
0x18010bad6  mov     rdx, [rsp+140h+var_E0]
0x18010badb  mov     rax, [rax+68h]
0x18010badf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010bae4  mov     ebx, eax
0x18010bae6  test    eax, eax
0x18010bae8  jns     short loc_18010BAF1
0x18010baea  mov     edx, 0B6h
0x18010baef  jmp     short loc_18010BAB0
0x18010baf1  lea     rcx, [rsp+140h+var_E0]
0x18010baf6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x18010bafb  mov     [rsp+140h+var_F0], rsi
0x18010bb00  lea     rdx, [rsp+140h+var_F0]
0x18010bb05  lea     rcx, [rsp+140h+var_108]
0x18010bb0a  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x18010bb0f  mov     ebx, eax
0x18010bb11  test    eax, eax
0x18010bb13  jns     loc_18010BC01
0x18010bb19  mov     edx, 0C6h; void *
0x18010bb1e  lea     r8, aOnecoreuapDsEx_32; "onecoreuap\\ds\\ext\\common\\lib\\cloud"...
0x18010bb25  mov     r9d, eax; char *
0x18010bb28  mov     rcx, [rbp+48h]; this
0x18010bb2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010bb31  jmp     loc_18010BF20
0x18010bb36  test    cl, cl
0x18010bb38  jnz     short loc_18010BAFB
0x18010bb3a  mov     [rsp+140h+var_C8], rsi
0x18010bb3f  mov     r9d, 0Ah
0x18010bb45  lea     r8d, [r9+0Bh]
0x18010bb49  lea     rdx, [rbp+40h+sourceString]
0x18010bb4d  mov     rcx, [r14+8]
0x18010bb51  call    cs:__imp__o__ui64tow_s
0x18010bb57  test    eax, eax
0x18010bb59  jnz     loc_18010BBF2
0x18010bb5f  mov     rax, [r15]
0x18010bb62  mov     rbx, [rax+50h]
0x18010bb66  lea     rdx, [rbp+40h+sourceString]; sourceString
0x18010bb6a  lea     rcx, [rbp+40h+hstringHeader]; hstringHeader
0x18010bb6e  call    ??$?0$0BF@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0BF@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[21])
0x18010bb73  nop
0x18010bb74  lea     r8, [rsp+140h+var_C8]
0x18010bb79  mov     rdx, [rax+18h]
0x18010bb7d  mov     rcx, r15
0x18010bb80  mov     rax, rbx
0x18010bb83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010bb88  mov     ebx, eax
0x18010bb8a  test    eax, eax
0x18010bb8c  jns     short loc_18010BBB1
0x18010bb8e  mov     edx, 0BFh; void *
0x18010bb93  mov     r9d, eax; char *
0x18010bb96  lea     r8, aOnecoreuapDsEx_32; "onecoreuap\\ds\\ext\\common\\lib\\cloud"...
0x18010bb9d  mov     rcx, [rbp+48h]; this
0x18010bba1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010bba6  nop
0x18010bba7  lea     rcx, [rsp+140h+var_C8]
0x18010bbac  jmp     loc_18010BF25
0x18010bbb1  mov     rdx, [rsp+140h+var_C8]
0x18010bbb6  test    rdx, rdx
0x18010bbb9  jnz     short loc_18010BBCA
0x18010bbbb  mov     ebx, 8007000Eh
0x18010bbc0  mov     r9d, ebx
0x18010bbc3  mov     edx, 0C0h
0x18010bbc8  jmp     short loc_18010BB96
0x18010bbca  mov     rcx, [rsp+140h+var_F8]
0x18010bbcf  mov     rax, [rcx]
  ... truncated ...
```
