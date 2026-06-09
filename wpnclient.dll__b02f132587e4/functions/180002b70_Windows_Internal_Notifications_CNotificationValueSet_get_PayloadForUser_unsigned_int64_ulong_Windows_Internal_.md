# Windows::Internal::Notifications::CNotificationValueSet::get_PayloadForUser(unsigned __int64,ulong,Windows::Internal::Notifications::WPN_DEVICE_THEME,Windows::Foundation::Collections::IPropertySet * *)

- ea: `0x180002b70`
- end: `0x18000398a`
- name: `?get_PayloadForUser@CNotificationValueSet@Notifications@Internal@Windows@@UEAAJ_KKW4WPN_DEVICE_THEME@234@PEAPEAUIPropertySet@Collections@Foundation@4@@Z`
- size: `3610`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002084`
- `0x1800020d0`
- `0x180002b70`
- `0x180003990`
- `0x180005670`
- `0x180008fe0`
- `0x1800180cc`
- `0x180018d90`
- `0x180019d04`
- `0x18001b848`
- `0x18001bd10`
- `0x18001c9bc`
- `0x18001ff00`
- `0x1800307c0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180003187`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800037e8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180003880`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180003187`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800037e8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180003880`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180002d97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800031a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800035a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180002d97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800031a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800035a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800030ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800030ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000310a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003211`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800033da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000310a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003211`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800033da`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180002ddb`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180002ddb`
- `OLEAUT32!__imp_SysFreeString` at `0x180003220`
- `OLEAUT32!__imp_SysFreeString` at `0x18000322f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800032e7`
- `OLEAUT32!__imp_SysFreeString` at `0x180003220`
- `OLEAUT32!__imp_SysFreeString` at `0x18000322f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800032e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
__int64 __fastcall Windows::Internal::Notifications::CNotificationValueSet::get_PayloadForUser(
        __int64 a1,
        __int64 a2,
        int a3,
        const char *a4,
        _QWORD *a5)
{
  unsigned int v5; // ebx
  int v6; // r12d
  __int64 v7; // rdi
  _QWORD *v9; // rsi
  int v10; // ecx
  _QWORD *v11; // r15
  __int64 v12; // rcx
  _QWORD *v13; // rsi
  __int64 v14; // rdx
  const char *v15; // rbx
  int v16; // edx
  int v17; // edx
  int v18; // edx
  int v19; // edx
  int v20; // edi
  __int64 (__fastcall ***v21)(_QWORD, GUID *, _QWORD **); // rbx
  __int64 (__fastcall *v22)(_QWORD, GUID *, _QWORD **); // rdi
  _QWORD *v23; // rcx
  int v24; // eax
  struct IXMLDOMDocument *v25; // rbx
  HRESULT (__stdcall *get_documentElement)(IXMLDOMDocument *, IXMLDOMElement **); // rdi
  _QWORD *v27; // rcx
  int v28; // eax
  int v29; // eax
  __int64 v30; // rax
  OLECHAR *v31; // rcx
  int v32; // r8d
  int v33; // r8d
  __int64 v34; // rdx
  int v35; // r8d
  __int64 v36; // r8
  int v37; // eax
  int v38; // eax
  int i; // r12d
  int v40; // eax
  int v41; // eax
  int v42; // eax
  HSTRING v43; // rbx
  unsigned __int64 v44; // rdx
  HRESULT v45; // edi
  __int64 v46; // r14
  __int64 (__fastcall *v47)(__int64, HSTRING, __int64 *); // r15
  __int64 v48; // rcx
  const WCHAR *v49; // rsi
  unsigned __int64 v50; // rdi
  int v51; // eax
  int v52; // eax
  __int64 v53; // rcx
  _QWORD *v54; // rcx
  __int64 (__fastcall ***v55)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 (__fastcall ***v56)(_QWORD, _QWORD, _QWORD); // rax
  __int64 v57; // rcx
  _QWORD *v58; // rcx
  __int64 (__fastcall ***v59)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v60; // rcx
  struct IXMLDOMDocument *v61; // rcx
  HSTRING v62; // rcx
  __int64 v63; // rcx
  __int64 v64; // rcx
  __int64 result; // rax
  _QWORD *v66; // rdi
  __int64 (__fastcall *v67)(_QWORD *, const WCHAR *, __int64 *); // rbx
  int v68; // eax
  _QWORD *v69; // rbx
  __int64 (__fastcall *v70)(_QWORD *, HSTRING, __int64, char *); // rsi
  __int64 v71; // rdi
  int v72; // eax
  __int64 v73; // rcx
  int v74; // ecx
  __int64 v75; // rcx
  _QWORD *v76; // rdx
  __int64 v77; // rcx
  int v78; // [rsp+20h] [rbp-168h]
  char v79; // [rsp+50h] [rbp-138h] BYREF
  char v80[7]; // [rsp+51h] [rbp-137h] BYREF
  __int64 v81; // [rsp+58h] [rbp-130h] BYREF
  __int64 (__fastcall ***v82)(_QWORD, _QWORD, _QWORD); // [rsp+60h] [rbp-128h] BYREF
  _QWORD *v83; // [rsp+68h] [rbp-120h] BYREF
  __int64 (__fastcall ***v84)(_QWORD, GUID *, _QWORD *); // [rsp+70h] [rbp-118h] BYREF
  _QWORD *v85; // [rsp+78h] [rbp-110h] BYREF
  _QWORD *v86; // [rsp+80h] [rbp-108h]
  unsigned int v87; // [rsp+88h] [rbp-100h]
  __int64 (__fastcall ***v88)(_QWORD, _QWORD, _QWORD); // [rsp+90h] [rbp-F8h]
  __int64 v89; // [rsp+98h] [rbp-F0h] BYREF
  struct IXMLDOMDocument *v90; // [rsp+A0h] [rbp-E8h] BYREF
  int v91; // [rsp+A8h] [rbp-E0h]
  BSTR bstrString; // [rsp+B0h] [rbp-D8h] BYREF
  PCWSTR v93; // [rsp+B8h] [rbp-D0h] BYREF
  PCNZWCH sourceString; // [rsp+C0h] [rbp-C8h] BYREF
  __int128 v95; // [rsp+C8h] [rbp-C0h] BYREF
  HSTRING v96[2]; // [rsp+D8h] [rbp-B0h]
  __int64 v97; // [rsp+E8h] [rbp-A0h]
  HSTRING v98; // [rsp+F0h] [rbp-98h] BYREF
  HSTRING v99; // [rsp+F8h] [rbp-90h]
  _QWORD *v100; // [rsp+100h] [rbp-88h]
  __int64 v101; // [rsp+108h] [rbp-80h]
  _QWORD *v102; // [rsp+110h] [rbp-78h]
  __int128 v103; // [rsp+118h] [rbp-70h] BYREF
  __m128i si128; // [rsp+128h] [rbp-60h]
  HSTRING string; // [rsp+138h] [rbp-50h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+140h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  try
  {
    v5 = (unsigned int)a4;
    v87 = (unsigned int)a4;
    v6 = a3;
    v91 = a3;
    v7 = a2;
    v101 = a2;
    v9 = a5;
    v102 = a5;
    *a5 = 0;
    if ( *(_BYTE *)(a1 + 112) )
    {
      if ( *(_QWORD *)(a1 + 120) == a2 && a3 == *(_DWORD *)(a1 + 128) && (_DWORD)a4 == *(_DWORD *)(a1 + 136) )
      {
        v11 = (_QWORD *)(a1 + 96);
        if ( *(_QWORD *)(a1 + 96) )
        {
LABEL_91:
          if ( *v11 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 8LL))(*v11);
          *v9 = *v11;
          return 0;
        }
      }
    }
    v95 = 0;
    *(_OWORD *)v96 = 0;
    v97 = a2;
    v10 = *(_DWORD *)(a1 + 88);
    if ( v10 != 2 && v10 )
    {
      v74 = v10 - 1;
      if ( v74 )
      {
        if ( v74 != 2 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x55,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cnotificationvalueset.cpp",
            (const char *)0x8000FFFFLL,
            v78);
        v11 = (_QWORD *)(a1 + 96);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 96);
        Windows::Internal::Notifications::CNotificationValueSet::GetMRTContrastFromTheme(v77, v5);
        v78 = v6;
        NotificationParser::TransformAdaptiveToast(&v95, *(_QWORD *)(a1 + 104));
      }
      else
      {
        v11 = (_QWORD *)(a1 + 96);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 96);
        Windows::Internal::Notifications::CNotificationValueSet::GetMRTContrastFromTheme(v75, v5);
        v76 = (_QWORD *)(a1 + 56);
        if ( *(_QWORD *)(a1 + 80) > 0xFu )
          v76 = (_QWORD *)*v76;
        NotificationParser::ParseToast(&v95, v76, *(unsigned int *)(a1 + 132));
      }
LABEL_84:
      if ( !*v11 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x58,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cnotificationvalueset.cpp",
          (const char *)0x8000FFFFLL,
          v78);
      *(_QWORD *)(a1 + 120) = v7;
      *(_DWORD *)(a1 + 128) = v6;
      *(_DWORD *)(a1 + 136) = v5;
      *(_BYTE *)(a1 + 112) = 1;
      WindowsDeleteString(v96[1]);
      v96[1] = 0;
      v62 = v96[0];
      if ( v96[0] )
      {
        v96[0] = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v62 + 16LL))(v62);
      }
      v63 = *((_QWORD *)&v95 + 1);
      if ( *((_QWORD *)&v95 + 1) )
      {
        *((_QWORD *)&v95 + 1) = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
      }
      v64 = v95;
      if ( (_QWORD)v95 )
      {
        *(_QWORD *)&v95 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
      }
      goto LABEL_91;
    }
    v11 = (_QWORD *)(a1 + 96);
    v12 = *(_QWORD *)(a1 + 96);
    if ( v12 )
    {
      *v11 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    if ( v5 > 2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB8,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cnotificationvalueset.cpp",
        (const char *)0x80070057LL,
        v78);
    v13 = (_QWORD *)(a1 + 24);
    if ( *(_QWORD *)(a1 + 48) > 7u )
      v13 = (_QWORD *)*v13;
    v14 = *(unsigned int *)(a1 + 140);
    v15 = (const char *)(a1 + 56);
    if ( *(_QWORD *)(a1 + 80) > 0xFu )
      v15 = *(const char **)v15;
    v90 = 0;
    v85 = 0;
    v88 = 0;
    v86 = 0;
    v89 = 0;
    bstrString = 0;
    v79 = 0;
    v103 = 0;
    si128 = 0;
    std::wstring::_Construct_empty(&v103, v14);
    v17 = v16 - 1;
    if ( v17 )
    {
      v18 = v17 - 1;
      if ( v18 )
      {
        v19 = v18 - 1;
        if ( v19 )
        {
          if ( v19 == 1 )
            std::wstring::_Assign<unsigned short>(&v103, L"TileLarge", 9);
          else
            std::wstring::_Assign<unsigned short>(&v103, L"TileGeneric", 11);
        }
        else
        {
          std::wstring::_Assign<unsigned short>(&v103, L"TileWide", 8);
        }
      }
      else
      {
        std::wstring::_Assign<unsigned short>(&v103, L"TileMedium", 10);
      }
    }
    else
    {
      std::wstring::_Assign<unsigned short>(&v103, L"TileSmall", 9);
    }
    NotificationParser::LoadXml((NotificationParser *)&v95, v15, 0x67u, &v90);
    v82 = 0;
    v83 = 0;
    if ( WindowsCreateStringReference(L"Windows.Foundation.Collections.ValueSet", 0x27u, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v82 = 0;
    v84 = 0;
    v20 = RoActivateInstance(string, &v84);
    if ( v20 >= 0 )
    {
      if ( !memcmp_0(&GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
      {
        v21 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **))v84;
        v82 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v84;
LABEL_22:
        if ( v20 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6E8,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
            (const char *)(unsigned int)v20,
            v78);
        v22 = **v21;
        v23 = v83;
        if ( v83 )
        {
          v83 = 0;
          (*(void (__fastcall **)(_QWORD *, _QWORD))(*v23 + 16LL))(v23, *v23);
        }
        v24 = v22(v21, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v83);
        if ( v24 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6EB,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
            (const char *)(unsigned int)v24,
            v78);
        v88 = v82;
        v86 = v83;
        v25 = v90;
        get_documentElement = v90->lpVtbl->get_documentElement;
        v27 = v85;
        if ( v85 )
        {
          v85 = 0;
          (*(void (__fastcall **)(_QWORD *, _QWORD))(*v27 + 16LL))(v27, *v27);
        }
        v28 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, _QWORD **))get_documentElement)(v25, &v85);
        if ( v28 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x63,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
            (const char *)(unsigned int)v28,
            v78);
        v29 = (*(__int64 (__fastcall **)(_QWORD *, BSTR *))(*v85 + 56LL))(v85, &bstrString);
        if ( v29 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x66,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
            (const char *)(unsigned int)v29,
            v78);
        v30 = 0;
        v31 = bstrString;
        do
        {
          v32 = bstrString[v30++];
          v33 = v32 - aTile[v30 - 1];
        }
        while ( !v33 && v30 != 5 );
        if ( v33 )
        {
          v34 = 0;
          do
          {
            v35 = bstrString[v34++];
            v36 = v35 - (unsigned int)aBadge[v34 - 1];
          }
          while ( !(_DWORD)v36 && v34 != 6 );
          if ( (_DWORD)v36 )
            goto LABEL_71;
          v100 = v86;
          v84 = 0;
          v37 = (*(__int64 (__fastcall **)(_QWORD *, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *), __int64, const wchar_t *))(*v85 + 136LL))(
                  v85,
                  &v84,
                  v36,
                  L"badge");
          if ( v37 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x69A,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notif"
                            "icationparser.cpp",
              (const char *)(unsigned int)v37,
              v78);
          LODWORD(v82) = 0;
          v38 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *), __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)))(*v84)[11])(
                  v84,
                  &v82);
          if ( v38 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x69E,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notif"
                            "icationparser.cpp",
              (const char *)(unsigned int)v38,
              v78);
          for ( i = 0; i < (int)v82; ++i )
          {
            v83 = 0;
            v81 = 0;
            v40 = ((__int64 (__fastcall **)(_QWORD, GUID *, _QWORD **))*v84)[10](v84, (GUID *)(unsigned int)i, &v83);
            if ( v40 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x6A6,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\not"
                              "ificationparser.cpp",
                (const char *)(unsigned int)v40,
                v78);
            sourceString = 0;
            v93 = 0;
            v41 = (*(__int64 (__fastcall **)(_QWORD *, PCNZWCH *))(*v83 + 56LL))(v83, &sourceString);
            if ( v41 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x6AB,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\not"
                              "ificationparser.cpp",
                (const char *)(unsigned int)v41,
                v78);
            v42 = (*(__int64 (__fastcall **)(_QWORD *, PCWSTR *))(*v83 + 208LL))(v83, &v93);
            if ( v42 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x6AD,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\not"
                              "ificationparser.cpp",
                (const char *)(unsigned int)v42,
                v78);
            v43 = 0;
            v99 = 0;
            if ( sourceString )
            {
              v98 = 0;
              v44 = -1;
              do
                ++v44;
              while ( sourceString[v44] );
              if ( v44 > 0xFFFFFFFF )
              {
                v45 = -2147024362;
              }
              else
              {
                v45 = WindowsCreateString(sourceString, v44, &v98);
                if ( v45 >= 0 )
                {
                  v43 = v98;
                  v99 = v98;
                  WindowsDeleteString(0);
                }
              }
            }
            else
            {
              v45 = -2147467261;
            }
            if ( v45 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x6B2,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\not"
                              "ificationparser.cpp",
                (const char *)(unsigned int)v45,
                v78);
            v46 = v95;
            v47 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v95 + 144LL);
            v48 = v81;
            if ( v81 )
            {
              v81 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
            }
            v49 = v93;
            v50 = -1;
            do
              ++v50;
            while ( v93[v50] );
            if ( v50 > 0xFFFFFFFF )
            {
              LODWORD(v50) = -1;
              RaiseException(0xC000000D, 1u, 0, 0);
            }
            WindowsCreateStringReference(v49, v50, &hstringHeader, &string);
            v51 = v47(v46, string, &v81);
            if ( v51 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x6B6,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\not"
                              "ificationparser.cpp",
                (const char *)(unsigned int)v51,
                v78);
            v80[0] = 0;
            v52 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, char *))(*v100 + 80LL))(v100, v43, v81, v80);
            if ( v52 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x6BB,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\not"
                              "ificationparser.cpp",
                (const char *)(unsigned int)v52,
                v78);
            if ( v43 )
              WindowsDeleteString(v43);
            SysFreeString((BSTR)v93);
            SysFreeString((BSTR)sourceString);
            v53 = v81;
            if ( v81 )
            {
              v81 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
            }
            v54 = v83;
            if ( v83 )
            {
              v83 = 0;
              (*(void (__fastcall **)(_QWORD *))(*v54 + 16LL))(v54);
            }
          }
          v55 = v84;
          if ( v84 )
          {
            v84 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v55)[2])(v55);
          }
          v6 = v91;
          v11 = (_QWORD *)(a1 + 96);
        }
        else
        {
          NotificationParser::GetAttributes(&v95, v85);
          v66 = v85;
          v67 = *(__int64 (__fastcall **)(_QWORD *, const WCHAR *, __int64 *))(*v85 + 296LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v89);
          v68 = v67(v66, L"visual", &v89);
          if ( v68 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x70,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notif"
                            "icationparser.cpp",
              (const char *)(unsigned int)v68,
              v78);
          if ( !v89 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x71,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notif"
                            "icationparser.cpp",
              (const char *)0x80070490LL,
              v78);
          v81 = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
          NotificationParser::ParseVisual((unsigned int)&v95, (__int64)v13);
          v69 = v86;
          v70 = *(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, char *))(*v86 + 80LL);
          v71 = v81;
          if ( WindowsCreateStringReference(L"visual", 6u, &hstringHeader, &string) < 0 )
            RaiseException(0xC000000D, 1u, 0, 0);
          v72 = v70(v69, string, v71, &v79);
          if ( v72 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x76,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notif"
                            "icationparser.cpp",
              (const char *)(unsigned int)v72,
              v78);
          v73 = v81;
          if ( v81 )
          {
            v81 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
          }
        }
        v31 = bstrString;
LABEL_71:
        v56 = v88;
        v88 = 0;
        *v11 = v56;
        if ( si128.m128i_i64[1] > 7uLL )
        {
          std::_Deallocate<16>(v103, 2 * si128.m128i_i64[1] + 2);
          v31 = bstrString;
        }
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v103) = 0;
        SysFreeString(v31);
        v57 = v89;
        if ( v89 )
        {
          v89 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
        }
        v58 = v86;
        if ( v86 )
        {
          v86 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v58 + 16LL))(v58);
        }
        v59 = v88;
        if ( v88 )
        {
          v88 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v59)[2])(v59);
        }
        v60 = v85;
        if ( v85 )
        {
          v85 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v60 + 16LL))(v60);
        }
        v61 = v90;
        if ( v90 )
        {
          v90 = 0;
          ((void (__fastcall *)(struct IXMLDOMDocument *))v61->lpVtbl->Release)(v61);
        }
        v5 = v87;
        v7 = v101;
        v9 = v102;
        goto LABEL_84;
      }
      v20 = (**v84)(v84, &GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c, &v82);
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v84)[2])(v84);
    }
    v21 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **))v82;
    goto LABEL_22;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x62,
                           (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cnotificationvalueset.cpp",
                           a4);
  }
  return result;
}

```

## disassembly

```asm
0x180002b70  mov     [rsp+arg_8], rbx
0x180002b75  mov     [rsp+arg_10], rsi
0x180002b7a  push    rdi
0x180002b7b  push    r12
0x180002b7d  push    r13
0x180002b7f  push    r14
0x180002b81  push    r15
0x180002b83  sub     rsp, 160h
0x180002b8a  mov     rax, cs:__security_cookie
0x180002b91  xor     rax, rsp
0x180002b94  mov     [rsp+188h+var_30], rax
0x180002b9c  mov     ebx, r9d
0x180002b9f  mov     [rsp+188h+var_100], ebx
0x180002ba6  mov     r12d, r8d
0x180002ba9  mov     [rsp+188h+var_E0], r8d
0x180002bb1  mov     rdi, rdx
0x180002bb4  mov     [rsp+188h+var_80], rdx
0x180002bbc  mov     r13, rcx
0x180002bbf  mov     rsi, [rsp+188h+arg_20]
0x180002bc7  mov     [rsp+188h+var_78], rsi
0x180002bcf  xor     r14d, r14d
0x180002bd2  mov     [rsi], r14
0x180002bd5  cmp     [rcx+70h], r14b
0x180002bd9  jnz     loc_1800036D0
0x180002bdf  xorps   xmm0, xmm0
0x180002be2  movdqu  [rsp+188h+var_C0], xmm0
0x180002beb  xorps   xmm1, xmm1
0x180002bee  movdqu  xmmword ptr [rsp+188h+var_B0], xmm1
0x180002bf7  mov     [rsp+188h+var_A0], rdx
0x180002bff  mov     ecx, [rcx+58h]
0x180002c02  cmp     ecx, 2
0x180002c05  jnz     loc_180003625
0x180002c0b  lea     r15, [r13+60h]
0x180002c0f  mov     rcx, [r15]
0x180002c12  test    rcx, rcx
0x180002c15  jz      short loc_180002C27
0x180002c17  mov     [r15], r14
0x180002c1a  mov     rax, [rcx]
0x180002c1d  mov     rax, [rax+10h]
0x180002c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c26  nop
0x180002c27  test    ebx, ebx
0x180002c29  jnz     loc_180003742
0x180002c2f  lea     rsi, [r13+18h]
0x180002c33  cmp     qword ptr [rsi+18h], 7
0x180002c38  ja      loc_180003783
0x180002c3e  mov     edx, [r13+8Ch]
0x180002c45  lea     rbx, [r13+38h]
0x180002c49  cmp     qword ptr [rbx+18h], 0Fh
0x180002c4e  ja      loc_18000378B
0x180002c54  xor     edi, edi
0x180002c56  mov     [rsp+188h+var_E8], rdi
0x180002c5e  mov     [rsp+188h+var_110], rdi
0x180002c63  mov     [rsp+188h+var_F8], rdi
0x180002c6b  mov     [rsp+188h+var_108], rdi
0x180002c73  mov     [rsp+188h+var_F0], rdi
0x180002c7b  mov     [rsp+188h+bstrString], rdi
0x180002c83  mov     [rsp+188h+var_138], dil
0x180002c88  xorps   xmm0, xmm0
0x180002c8b  movups  [rsp+188h+var_70], xmm0
0x180002c93  xorps   xmm1, xmm1
0x180002c96  movdqu  [rsp+188h+var_60], xmm1
0x180002c9f  lea     rcx, [rsp+188h+var_70]
0x180002ca7  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180002cac  nop
0x180002cad  sub     edx, 1
0x180002cb0  lea     rcx, [rsp+188h+var_70]
0x180002cb8  jz      loc_180003604
0x180002cbe  sub     edx, 1
0x180002cc1  jz      loc_1800037C1
0x180002cc7  sub     edx, 1
0x180002cca  jz      loc_1800037AA
0x180002cd0  cmp     edx, 1
0x180002cd3  jz      loc_180003793
0x180002cd9  mov     r8d, 0Bh
0x180002cdf  lea     rdx, aTilegeneric; "TileGeneric"
0x180002ce6  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180002ceb  nop
0x180002cec  mov     rcx, [rsp+188h+var_E8]
0x180002cf4  test    rcx, rcx
0x180002cf7  jz      short loc_180002D0E
0x180002cf9  mov     [rsp+188h+var_E8], rdi
0x180002d01  mov     rax, [rcx]
0x180002d04  mov     rax, [rax+10h]
0x180002d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d0d  nop
0x180002d0e  lea     r9, [rsp+188h+var_E8]; struct IXMLDOMDocument **
0x180002d16  mov     r8d, 67h ; 'g'; unsigned int
0x180002d1c  mov     rdx, rbx; char *
0x180002d1f  lea     rcx, [rsp+188h+var_C0]; this
0x180002d27  call    ?LoadXml@NotificationParser@@AEAAXPEBDIPEAPEAUIXMLDOMDocument@@@Z; NotificationParser::LoadXml(char const *,uint,IXMLDOMDocument * *)
0x180002d2c  nop
0x180002d2d  mov     rcx, [rsp+188h+var_108]
0x180002d35  test    rcx, rcx
0x180002d38  jz      short loc_180002D4F
0x180002d3a  mov     [rsp+188h+var_108], rdi
0x180002d42  mov     rax, [rcx]
0x180002d45  mov     rax, [rax+10h]
0x180002d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d4e  nop
0x180002d4f  mov     rcx, [rsp+188h+var_F8]
0x180002d57  test    rcx, rcx
0x180002d5a  jz      short loc_180002D71
0x180002d5c  mov     [rsp+188h+var_F8], rdi
0x180002d64  mov     rax, [rcx]
0x180002d67  mov     rax, [rax+10h]
0x180002d6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d70  nop
0x180002d71  mov     [rsp+188h+var_128], rdi
0x180002d76  mov     [rsp+188h+var_120], rdi
0x180002d7b  lea     r9, [rsp+188h+string]; string
0x180002d83  lea     r8, [rsp+188h+hstringHeader]; hstringHeader
0x180002d8b  mov     edx, 27h ; '''; length
0x180002d90  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_ValueSet@@3QBGB; "Windows.Foundation.Collections.ValueSet"
0x180002d97  call    cs:__imp_WindowsCreateStringReference
0x180002d9d  test    eax, eax
0x180002d9f  js      loc_1800037D8
0x180002da5  mov     rbx, [rsp+188h+string]
0x180002dad  mov     rcx, [rsp+188h+var_128]
0x180002db2  test    rcx, rcx
0x180002db5  jz      short loc_180002DC9
0x180002db7  mov     [rsp+188h+var_128], rdi
0x180002dbc  mov     rax, [rcx]
0x180002dbf  mov     rax, [rax+10h]
0x180002dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dc8  nop
0x180002dc9  mov     [rsp+188h+var_128], rdi
0x180002dce  mov     [rsp+188h+var_118], rdi
0x180002dd3  lea     rdx, [rsp+188h+var_118]
0x180002dd8  mov     rcx, rbx
0x180002ddb  call    cs:__imp_RoActivateInstance
0x180002de1  mov     edi, eax
0x180002de3  test    eax, eax
0x180002de5  js      short loc_180002E37
0x180002de7  mov     r8d, 10h; Size
0x180002ded  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180002df4  lea     rcx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c; Buf1
0x180002dfb  call    memcmp_0
0x180002e00  test    eax, eax
0x180002e02  jz      loc_1800034A2
0x180002e08  mov     rcx, [rsp+188h+var_118]
0x180002e0d  mov     rax, [rcx]
0x180002e10  lea     r8, [rsp+188h+var_128]
0x180002e15  lea     rdx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c
0x180002e1c  mov     rax, [rax]
0x180002e1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e24  mov     edi, eax
0x180002e26  mov     rcx, [rsp+188h+var_118]
0x180002e2b  mov     rax, [rcx]
0x180002e2e  mov     rax, [rax+10h]
0x180002e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e37  mov     rbx, [rsp+188h+var_128]
0x180002e3c  mov     rcx, [rsp+188h]; this
0x180002e44  test    edi, edi
0x180002e46  js      loc_1800037F3
0x180002e4c  mov     rax, [rbx]
0x180002e4f  mov     rdi, [rax]
0x180002e52  mov     rcx, [rsp+188h+var_120]
0x180002e57  test    rcx, rcx
0x180002e5a  jz      short loc_180002E72
0x180002e5c  mov     [rsp+188h+var_120], 0
0x180002e65  mov     rdx, [rcx]
0x180002e68  mov     rax, [rdx+10h]
0x180002e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e71  nop
0x180002e72  lea     r8, [rsp+188h+var_120]
0x180002e77  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180002e7e  mov     rcx, rbx
0x180002e81  mov     rax, rdi
0x180002e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e89  nop
0x180002e8a  mov     rcx, [rsp+188h]; this
0x180002e92  test    eax, eax
0x180002e94  js      loc_180003807
0x180002e9a  mov     rax, [rsp+188h+var_128]
0x180002e9f  mov     [rsp+188h+var_F8], rax
0x180002ea7  mov     rax, [rsp+188h+var_120]
0x180002eac  mov     [rsp+188h+var_108], rax
0x180002eb4  mov     rbx, [rsp+188h+var_E8]
0x180002ebc  mov     rax, [rbx]
0x180002ebf  mov     rdi, [rax+168h]
0x180002ec6  mov     rcx, [rsp+188h+var_110]
0x180002ecb  test    rcx, rcx
0x180002ece  jz      short loc_180002EE6
0x180002ed0  mov     [rsp+188h+var_110], 0
0x180002ed9  mov     rdx, [rcx]
0x180002edc  mov     rax, [rdx+10h]
0x180002ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ee5  nop
0x180002ee6  lea     rdx, [rsp+188h+var_110]
0x180002eeb  mov     rcx, rbx
0x180002eee  mov     rax, rdi
0x180002ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ef6  mov     rcx, [rsp+188h]; this
0x180002efe  test    eax, eax
0x180002f00  js      loc_18000381C
0x180002f06  mov     rcx, [rsp+188h+var_110]
0x180002f0b  mov     rax, [rcx]
0x180002f0e  lea     rdx, [rsp+188h+bstrString]
0x180002f16  mov     rax, [rax+38h]
0x180002f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f1f  mov     rcx, [rsp+188h]; this
0x180002f27  test    eax, eax
0x180002f29  js      loc_180003830
0x180002f2f  xor     eax, eax
0x180002f31  mov     rcx, [rsp+188h+bstrString]
0x180002f39  lea     r9, aTile; "tile"
0x180002f40  movzx   r8d, word ptr [rcx+rax*2]
0x180002f45  inc     rax
0x180002f48  movzx   edx, word ptr [r9+rax*2-2]
0x180002f4e  sub     r8d, edx
0x180002f51  jnz     short loc_180002F59
0x180002f53  cmp     rax, 5
0x180002f57  jnz     short loc_180002F40
0x180002f59  test    r8d, r8d
0x180002f5c  jz      loc_1800034B1
0x180002f62  xor     r14d, r14d
0x180002f65  mov     edx, r14d
0x180002f68  lea     r9, aBadge; "badge"
0x180002f6f  nop
0x180002f70  movzx   r8d, word ptr [rcx+rdx*2]
0x180002f75  inc     rdx
0x180002f78  movzx   eax, word ptr [r9+rdx*2-2]
0x180002f7e  sub     r8d, eax
0x180002f81  jnz     short loc_180002F89
0x180002f83  cmp     rdx, 6
0x180002f87  jnz     short loc_180002F70
0x180002f89  test    r8d, r8d
0x180002f8c  jnz     loc_1800032A8
0x180002f92  mov     rax, [rsp+188h+var_108]
0x180002f9a  mov     [rsp+188h+var_88], rax
0x180002fa2  mov     rcx, [rsp+188h+var_110]
0x180002fa7  mov     [rsp+188h+var_118], r14
0x180002fac  mov     rax, [rcx]
0x180002faf  lea     rdx, [rsp+188h+var_118]
0x180002fb4  mov     rax, [rax+88h]
0x180002fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fc0  mov     rcx, [rsp+188h]; this
0x180002fc8  test    eax, eax
0x180002fca  js      loc_1800038A0
0x180002fd0  mov     dword ptr [rsp+188h+var_128], r14d
0x180002fd5  mov     rcx, [rsp+188h+var_118]
0x180002fda  mov     rax, [rcx]
0x180002fdd  lea     rdx, [rsp+188h+var_128]
0x180002fe2  mov     rax, [rax+58h]
0x180002fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002feb  mov     rcx, [rsp+188h]; this
0x180002ff3  test    eax, eax
0x180002ff5  js      loc_1800038B4
0x180002ffb  mov     r12d, r14d
0x180002ffe  mov     edi, 0FFFFFFFFh
0x180003003  cmp     r12d, dword ptr [rsp+188h+var_128]
0x180003008  jge     loc_180003279
0x18000300e  mov     [rsp+188h+var_120], r14
0x180003013  mov     [rsp+188h+var_130], r14
0x180003018  mov     rcx, [rsp+188h+var_118]
0x18000301d  mov     rax, [rcx]
0x180003020  lea     r8, [rsp+188h+var_120]
0x180003025  mov     edx, r12d
0x180003028  mov     rax, [rax+50h]
0x18000302c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003031  mov     rcx, [rsp+188h]; this
0x180003039  test    eax, eax
0x18000303b  js      loc_1800038C9
0x180003041  mov     [rsp+188h+sourceString], r14
0x180003049  mov     [rsp+188h+var_D0], r14
0x180003051  mov     rcx, [rsp+188h+var_120]
0x180003056  mov     rax, [rcx]
0x180003059  lea     rdx, [rsp+188h+sourceString]
0x180003061  mov     rax, [rax+38h]
0x180003065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000306a  mov     rcx, [rsp+188h]; this
0x180003072  test    eax, eax
0x180003074  js      loc_1800038DE
0x18000307a  mov     rcx, [rsp+188h+var_120]
0x18000307f  mov     rax, [rcx]
0x180003082  lea     rdx, [rsp+188h+var_D0]
0x18000308a  mov     rax, [rax+0D0h]
0x180003091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003096  mov     rcx, [rsp+188h]; this
0x18000309e  test    eax, eax
0x1800030a0  js      loc_1800038F2
0x1800030a6  mov     rbx, r14
0x1800030a9  mov     [rsp+188h+var_90], rbx
0x1800030b1  mov     rcx, [rsp+188h+sourceString]; sourceString
0x1800030b9  test    rcx, rcx
0x1800030bc  jz      loc_18000361B
0x1800030c2  mov     [rsp+188h+var_98], r14
0x1800030ca  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1800030d1  inc     rdx; length
0x1800030d4  cmp     word ptr [rcx+rdx*2], 0
0x1800030d9  jnz     short loc_1800030D1
0x1800030db  cmp     rdx, rdi
0x1800030de  ja      loc_180003498
0x1800030e4  lea     r8, [rsp+188h+var_98]; string
0x1800030ec  call    cs:__imp_WindowsCreateString
0x1800030f2  mov     edi, eax
0x1800030f4  test    eax, eax
0x1800030f6  js      short loc_180003110
0x1800030f8  mov     rbx, [rsp+188h+var_98]
  ... truncated ...
```
