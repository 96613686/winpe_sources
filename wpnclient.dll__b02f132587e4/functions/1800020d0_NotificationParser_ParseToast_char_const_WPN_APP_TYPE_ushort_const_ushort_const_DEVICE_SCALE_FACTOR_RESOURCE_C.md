# NotificationParser::ParseToast(char const *,WPN_APP_TYPE,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST,Windows::Foundation::Collections::IPropertySet * *)

- ea: `0x1800020d0`
- end: `0x180002b63`
- name: `?ParseToast@NotificationParser@@QEAAXPEBDW4WPN_APP_TYPE@@PEBG2W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `2707`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x180002b70`

## callees

- `0x1800020d0`
- `0x180003990`
- `0x180008390`
- `0x1800089a0`
- `0x180008fe0`
- `0x18000b440`
- `0x18000c7d0`
- `0x18001780c`
- `0x180018d90`
- `0x18001b848`
- `0x18001ff00`
- `0x1800202d0`
- `0x18002030c`
- `0x18002d370`
- `0x18002e0ac`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800023a4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002437`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002492`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002595`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002697`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000279e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002911`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800023a4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002437`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002492`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002595`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002697`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000279e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002911`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000238a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000241d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180002478`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000257b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000267d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180002784`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800028f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000238a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000241d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180002478`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000257b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000267d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180002784`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800028f7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800029b5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800029b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
void __fastcall NotificationParser::ParseToast(
        NotificationParser *a1,
        const char *a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        _QWORD *a8)
{
  struct IXMLDOMDocument *v11; // rbx
  HRESULT (__stdcall *get_documentElement)(IXMLDOMDocument *, IXMLDOMElement **); // rdi
  __int64 v13; // rdx
  int v14; // eax
  int v15; // eax
  __int64 v16; // rdx
  OLECHAR *v17; // rcx
  OLECHAR v18; // ax
  int v19; // eax
  _OWORD *v20; // rax
  unsigned __int64 v21; // rdx
  PVOID Reserved1; // rcx
  __int64 v23; // rbx
  __int64 (__fastcall *v24)(__int64, PVOID, __int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *), _BYTE *); // rsi
  __int64 (__fastcall ***v25)(_QWORD, GUID *, _QWORD *); // rdi
  int v26; // eax
  int v27; // eax
  __int64 v28; // rbx
  int (__fastcall *v29)(__int64, PVOID, __int64 *); // rdi
  __int64 v30; // rbx
  __int64 (__fastcall *v31)(__int64, PVOID, __int64, _BYTE *); // rsi
  __int64 v32; // rdi
  int v33; // eax
  __int64 v34; // rbx
  __int64 (__fastcall *v35)(__int64, const WCHAR *, __int64 *); // rdi
  __int64 v36; // rdx
  int v37; // eax
  __int64 v38; // rdx
  __int64 v39; // rbx
  __int64 (__fastcall *v40)(__int64, PVOID, __int64, _BYTE *); // rsi
  __int64 v41; // rdi
  int v42; // eax
  __int64 v43; // rcx
  __int64 v44; // rbx
  void (__fastcall *v45)(__int64, const WCHAR *, __int64 *); // rdi
  __int64 v46; // rdx
  __int64 v47; // rbx
  __int64 (__fastcall *v48)(__int64, PVOID, __int64, _BYTE *); // rsi
  __int64 v49; // rdi
  int v50; // eax
  __int64 v51; // rcx
  __int64 v52; // rbx
  void (__fastcall *v53)(__int64, const WCHAR *, __int64 *); // rdi
  __int64 v54; // rdx
  __int64 v55; // r15
  __int64 v56; // rbx
  __int64 (__fastcall *v57)(__int64, PVOID, __int64, _BYTE *); // rsi
  __int64 v58; // rdi
  int v59; // eax
  __int64 v60; // rcx
  __int64 v61; // rbx
  void (__fastcall *v62)(__int64, const WCHAR *, __int64 *); // rdi
  __int64 v63; // rcx
  __int64 v64; // rbx
  __int64 v65; // rax
  __int64 v66; // rcx
  __int64 v67; // rdx
  __int64 v68; // rbx
  __int64 (__fastcall *v69)(__int64, PVOID, __int64, _BYTE *); // rsi
  __int64 v70; // rdi
  int v71; // eax
  __int64 v72; // rcx
  __int64 v73; // rcx
  __int64 v74; // rcx
  __int64 (__fastcall ***v75)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v76; // rax
  __int64 v77; // rcx
  __int64 v78; // rcx
  __int64 v79; // rcx
  __int64 v80; // rcx
  struct IXMLDOMDocument *v81; // rcx
  int v82; // [rsp+20h] [rbp-E0h]
  int v83; // [rsp+20h] [rbp-E0h]
  _BYTE v84[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v85; // [rsp+58h] [rbp-A8h] BYREF
  int v86[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v87; // [rsp+68h] [rbp-98h] BYREF
  __int64 v88; // [rsp+70h] [rbp-90h] BYREF
  __int64 v89; // [rsp+78h] [rbp-88h] BYREF
  __int64 v90; // [rsp+80h] [rbp-80h] BYREF
  __int64 (__fastcall ***v91)(_QWORD, GUID *, __int64 *); // [rsp+88h] [rbp-78h]
  __int64 v92; // [rsp+90h] [rbp-70h]
  __int64 v93; // [rsp+98h] [rbp-68h] BYREF
  __int64 v94; // [rsp+A0h] [rbp-60h] BYREF
  struct IXMLDOMDocument *v95; // [rsp+A8h] [rbp-58h] BYREF
  BSTR bstrString; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD *v97; // [rsp+B8h] [rbp-48h]
  __int64 v98; // [rsp+C0h] [rbp-40h]
  __int64 v99; // [rsp+C8h] [rbp-38h]
  HSTRING_HEADER hstringHeader; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int64 v101; // [rsp+E8h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v89 = a4;
  v97 = a8;
  v95 = 0;
  v88 = 0;
  v90 = 0;
  v87 = 0;
  v85 = 0;
  bstrString = 0;
  v84[0] = 0;
  v98 = 0;
  NotificationParser::LoadXml(a1, a2, 0x66u, &v95);
  NotificationParser::CreateValueSet(0, &v90, &v87);
  v11 = v95;
  get_documentElement = v95->lpVtbl->get_documentElement;
  v13 = v88;
  if ( v88 )
  {
    v88 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  v14 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, __int64 *))get_documentElement)(v11, &v88);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A8,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v14,
      v82);
  v15 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v88 + 56LL))(v88, &bstrString);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1AB,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v15,
      v82);
  v16 = 0;
  v17 = bstrString;
  while ( 1 )
  {
    v18 = bstrString[v16++];
    if ( v18 != aToast[v16 - 1] )
      break;
    if ( v16 == 6 )
    {
      NotificationParser::GetAttributes(a1, v88);
      NotificationParser::ConvertDisplayTimestampToFILETIME(a1, v87);
      v19 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, __int64 *))(*(_QWORD *)v88 + 296LL))(
              v88,
              L"visual",
              &v85);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1B8,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v19,
          v82);
      if ( !v85 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1B9,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)0x80070490LL,
          v82);
      v91 = 0;
      memset(&hstringHeader, 0, sizeof(hstringHeader));
      v101 = 0;
      v20 = operator new(0x20u);
      hstringHeader.Reserved.Reserved1 = v20;
      *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 12;
      v101 = 15;
      *v20 = *(_OWORD *)L"ToastGeneric";
      *((_QWORD *)v20 + 2) = *(_QWORD *)L"eric";
      *((_WORD *)v20 + 12) = 0;
      NotificationParser::ParseVisual((_DWORD)a1, a4);
      if ( v101 > 7 )
      {
        v21 = 2 * v101 + 2;
        if ( v21 < 0x1000 )
        {
          Reserved1 = hstringHeader.Reserved.Reserved1;
        }
        else
        {
          Reserved1 = (PVOID)*((_QWORD *)hstringHeader.Reserved.Reserved1 - 1);
          if ( (unsigned __int64)((char *)hstringHeader.Reserved.Reserved1 - (char *)Reserved1 - 8) > 0x1F )
            __fastfail(5u);
          v21 = 2 * v101 + 41;
        }
        operator delete(Reserved1, v21);
      }
      v23 = v87;
      v24 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *), _BYTE *))(*(_QWORD *)v87 + 80LL);
      v25 = v91;
      if ( WindowsCreateStringReference(
             L"visual",
             6u,
             (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
             (HSTRING *)&hstringHeader) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      v26 = v24(v23, hstringHeader.Reserved.Reserved1, v25, v84);
      if ( v26 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1BE,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v26,
          v83);
      v94 = 0;
      v27 = (**v91)(v91, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v94);
      if ( v27 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1C2,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v27,
          v83);
      v93 = 0;
      v28 = v94;
      v29 = *(int (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v94 + 48LL);
      if ( WindowsCreateStringReference(
             L"activationType",
             0xEu,
             (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
             (HSTRING *)&hstringHeader) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      if ( v29(v28, hstringHeader.Reserved.Reserved1, &v93) >= 0 )
      {
        v30 = v87;
        v31 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v87 + 80LL);
        v32 = v93;
        if ( WindowsCreateStringReference(
               L"activationType",
               0xEu,
               (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
               (HSTRING *)&hstringHeader) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        v33 = v31(v30, hstringHeader.Reserved.Reserved1, v32, v84);
        if ( v33 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1C7,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
            (const char *)(unsigned int)v33,
            v83);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58788260>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58788260>::GetImpl'::`2'::impl) )
      {
        v34 = v88;
        v35 = *(__int64 (__fastcall **)(__int64, const WCHAR *, __int64 *))(*(_QWORD *)v88 + 296LL);
        v36 = v85;
        if ( v85 )
        {
          v85 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
        }
        v37 = v35(v34, L"expandableContent", &v85);
        if ( v37 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1CB,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
            (const char *)(unsigned int)v37,
            v83);
        v38 = v85;
        if ( v85 )
        {
          *(_QWORD *)v86 = 0;
          v83 = a6;
          NotificationParser::ParseExpandableContent(a1, v85, v89);
          v39 = v87;
          v40 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v87 + 80LL);
          v41 = *(_QWORD *)v86;
          if ( WindowsCreateStringReference(
                 L"expandableContent",
                 0x11u,
                 (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
                 (HSTRING *)&hstringHeader) < 0 )
            RaiseException(0xC000000D, 1u, 0, 0);
          v42 = v40(v39, hstringHeader.Reserved.Reserved1, v41, v84);
          if ( v42 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1D0,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notif"
                            "icationparser.cpp",
              (const char *)(unsigned int)v42,
              a6);
          v43 = *(_QWORD *)v86;
          if ( *(_QWORD *)v86 )
          {
            *(_QWORD *)v86 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
          }
          goto LABEL_37;
        }
      }
      else
      {
LABEL_37:
        v38 = v85;
      }
      v44 = v88;
      v45 = *(void (__fastcall **)(__int64, const WCHAR *, __int64 *))(*(_QWORD *)v88 + 296LL);
      if ( v38 )
      {
        v85 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      }
      v45(v44, L"audio", &v85);
      v46 = v85;
      if ( v85 )
      {
        *(_QWORD *)v86 = 0;
        NotificationParser::ParseAudio((__int64 *)a1, v85, a3, v89, (HSTRING *)v86);
        v47 = v87;
        v48 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v87 + 80LL);
        v49 = *(_QWORD *)v86;
        if ( WindowsCreateStringReference(
               L"audio",
               5u,
               (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
               (HSTRING *)&hstringHeader) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        v50 = v48(v47, hstringHeader.Reserved.Reserved1, v49, v84);
        if ( v50 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1D9,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
            (const char *)(unsigned int)v50,
            v83);
        v51 = *(_QWORD *)v86;
        if ( *(_QWORD *)v86 )
        {
          *(_QWORD *)v86 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        }
        v46 = v85;
      }
      v52 = v88;
      v53 = *(void (__fastcall **)(__int64, const WCHAR *, __int64 *))(*(_QWORD *)v88 + 296LL);
      if ( v46 )
      {
        v85 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
      }
      v53(v52, L"actions", &v85);
      v54 = v85;
      if ( v85 )
      {
        *(_QWORD *)v86 = 0;
        v83 = a6;
        v55 = v89;
        NotificationParser::ParseActions(a1, v85, v89);
        v56 = v87;
        v57 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v87 + 80LL);
        v58 = *(_QWORD *)v86;
        if ( WindowsCreateStringReference(
               L"actions",
               7u,
               (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
               (HSTRING *)&hstringHeader) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        v59 = v57(v56, hstringHeader.Reserved.Reserved1, v58, v84);
        if ( v59 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1E2,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
            (const char *)(unsigned int)v59,
            a6);
        v60 = *(_QWORD *)v86;
        if ( *(_QWORD *)v86 )
        {
          *(_QWORD *)v86 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
        }
        v54 = v85;
      }
      else
      {
        v55 = v89;
      }
      v61 = v88;
      v62 = *(void (__fastcall **)(__int64, const WCHAR *, __int64 *))(*(_QWORD *)v88 + 296LL);
      if ( v54 )
      {
        v85 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      }
      v62(v61, L"header", &v85);
      v64 = v85;
      if ( v85 )
      {
        v92 = 0;
        *(_QWORD *)v86 = 0;
        v89 = 0;
        v99 = 0;
        NotificationParser::CreateValueSet(v63, v86, &v89);
        NotificationParser::GetAttributes(a1, v64);
        NotificationParser::ResolveTextElement(a1, v89, L"title", v55);
        v65 = *(_QWORD *)v86;
        v66 = 0;
        *(_QWORD *)v86 = 0;
        v92 = v65;
        v67 = v89;
        if ( v89 )
        {
          v89 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
          v66 = *(_QWORD *)v86;
        }
        if ( v66 )
        {
          *(_QWORD *)v86 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
        }
        v68 = v87;
        v69 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v87 + 80LL);
        v70 = v92;
        if ( WindowsCreateStringReference(
               L"header",
               6u,
               (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
               (HSTRING *)&hstringHeader) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        v71 = v69(v68, hstringHeader.Reserved.Reserved1, v70, v84);
        if ( v71 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1EB,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
            (const char *)(unsigned int)v71,
            v83);
        v72 = v92;
        if ( v92 )
        {
          v92 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
        }
      }
      v73 = v93;
      if ( v93 )
      {
        v93 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
      }
      v74 = v94;
      if ( v94 )
      {
        v94 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      }
      v75 = v91;
      if ( v91 )
      {
        v91 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v75)[2])(v75);
      }
      v17 = bstrString;
      break;
    }
  }
  v76 = v90;
  v90 = 0;
  *v97 = v76;
  SysFreeString(v17);
  v77 = v85;
  if ( v85 )
  {
    v85 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
  }
  v78 = v87;
  if ( v87 )
  {
    v87 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
  }
  v79 = v90;
  if ( v90 )
  {
    v90 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
  }
  v80 = v88;
  if ( v88 )
  {
    v88 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
  }
  v81 = v95;
  if ( v95 )
  {
    v95 = 0;
    ((void (__fastcall *)(struct IXMLDOMDocument *))v81->lpVtbl->Release)(v81);
  }
}

```

## disassembly

```asm
0x1800020d0  push    rbp
0x1800020d2  push    rbx
0x1800020d3  push    rsi
0x1800020d4  push    rdi
0x1800020d5  push    r12
0x1800020d7  push    r13
0x1800020d9  push    r14
0x1800020db  push    r15
0x1800020dd  lea     rbp, [rsp-8]
0x1800020e2  sub     rsp, 108h
0x1800020e9  mov     rax, cs:__security_cookie
0x1800020f0  xor     rax, rsp
0x1800020f3  mov     [rbp+40h+var_50], rax
0x1800020f7  mov     rsi, r9
0x1800020fa  mov     [rsp+140h+var_C8], r9
0x1800020ff  mov     r13d, r8d
0x180002102  mov     r14, rcx
0x180002105  mov     rax, [rbp+40h+arg_38]
0x18000210c  mov     [rbp+40h+var_88], rax
0x180002110  xor     r12d, r12d
0x180002113  mov     [rbp+40h+var_98], r12
0x180002117  mov     [rsp+140h+var_D0], r12
0x18000211c  mov     [rbp+40h+var_C0], r12
0x180002120  mov     [rsp+140h+var_D8], r12
0x180002125  mov     [rsp+140h+var_E8], r12
0x18000212a  mov     [rbp+40h+bstrString], r12
0x18000212e  mov     [rsp+140h+var_F0], r12b
0x180002133  mov     [rbp+40h+var_80], r12
0x180002137  lea     r9, [rbp+40h+var_98]; struct IXMLDOMDocument **
0x18000213b  mov     r8d, 66h ; 'f'; unsigned int
0x180002141  call    ?LoadXml@NotificationParser@@AEAAXPEBDIPEAPEAUIXMLDOMDocument@@@Z; NotificationParser::LoadXml(char const *,uint,IXMLDOMDocument * *)
0x180002146  nop
0x180002147  mov     rcx, [rsp+140h+var_D8]
0x18000214c  test    rcx, rcx
0x18000214f  jz      short loc_180002163
0x180002151  mov     [rsp+140h+var_D8], r12
0x180002156  mov     rax, [rcx]
0x180002159  mov     rax, [rax+10h]
0x18000215d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002162  nop
0x180002163  mov     rcx, [rbp+40h+var_C0]
0x180002167  test    rcx, rcx
0x18000216a  jz      short loc_18000217D
0x18000216c  mov     [rbp+40h+var_C0], r12
0x180002170  mov     rax, [rcx]
0x180002173  mov     rax, [rax+10h]
0x180002177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000217c  nop
0x18000217d  lea     r8, [rsp+140h+var_D8]
0x180002182  lea     rdx, [rbp+40h+var_C0]
0x180002186  call    ?CreateValueSet@NotificationParser@@AEAAXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@345@@Z; NotificationParser::CreateValueSet(Windows::Foundation::Collections::IPropertySet * *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x18000218b  mov     rbx, [rbp+40h+var_98]
0x18000218f  mov     rax, [rbx]
0x180002192  mov     rdi, [rax+168h]
0x180002199  mov     rdx, [rsp+140h+var_D0]
0x18000219e  test    rdx, rdx
0x1800021a1  jz      short loc_1800021B8
0x1800021a3  mov     [rsp+140h+var_D0], r12
0x1800021a8  mov     rcx, [rdx]
0x1800021ab  mov     rax, [rcx+10h]
0x1800021af  mov     rcx, rdx
0x1800021b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021b7  nop
0x1800021b8  lea     rdx, [rsp+140h+var_D0]
0x1800021bd  mov     rcx, rbx
0x1800021c0  mov     rax, rdi
0x1800021c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021c8  mov     rcx, [rbp+48h]; this
0x1800021cc  test    eax, eax
0x1800021ce  js      loc_180002A79
0x1800021d4  mov     rcx, [rsp+140h+var_D0]
0x1800021d9  mov     rax, [rcx]
0x1800021dc  lea     rdx, [rbp+40h+bstrString]
0x1800021e0  mov     rax, [rax+38h]
0x1800021e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021e9  mov     rcx, [rbp+48h]; this
0x1800021ed  test    eax, eax
0x1800021ef  js      loc_180002A8E
0x1800021f5  mov     rdx, r12
0x1800021f8  mov     rcx, [rbp+40h+bstrString]
0x1800021fc  lea     r8, aToast; "toast"
0x180002203  movzx   eax, word ptr [rcx+rdx*2]
0x180002207  inc     rdx
0x18000220a  cmp     ax, [r8+rdx*2-2]
0x180002210  jnz     loc_1800029A6
0x180002216  cmp     rdx, 6
0x18000221a  jnz     short loc_180002203
0x18000221c  mov     r8, [rsp+140h+var_D8]
0x180002221  mov     rdx, [rsp+140h+var_D0]
0x180002226  mov     rcx, r14
0x180002229  call    ?GetAttributes@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Z; NotificationParser::GetAttributes(IXMLDOMNode *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *)
0x18000222e  mov     rdx, [rsp+140h+var_D8]
0x180002233  mov     rcx, r14
0x180002236  call    ?ConvertDisplayTimestampToFILETIME@NotificationParser@@AEAAXPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Z; NotificationParser::ConvertDisplayTimestampToFILETIME(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *)
0x18000223b  mov     rbx, [rsp+140h+var_D0]
0x180002240  mov     rax, [rbx]
0x180002243  mov     rdi, [rax+128h]
0x18000224a  mov     rdx, [rsp+140h+var_E8]
0x18000224f  test    rdx, rdx
0x180002252  jz      short loc_180002269
0x180002254  mov     [rsp+140h+var_E8], r12
0x180002259  mov     rcx, [rdx]
0x18000225c  mov     rax, [rcx+10h]
0x180002260  mov     rcx, rdx
0x180002263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002268  nop
0x180002269  lea     r8, [rsp+140h+var_E8]
0x18000226e  lea     rdx, sourceString; "visual"
0x180002275  mov     rcx, rbx
0x180002278  mov     rax, rdi
0x18000227b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002280  mov     rcx, [rbp+48h]; this
0x180002284  test    eax, eax
0x180002286  js      loc_180002AA3
0x18000228c  mov     rcx, [rbp+48h]; this
0x180002290  cmp     [rsp+140h+var_E8], 0
0x180002296  jz      loc_180002AB8
0x18000229c  mov     [rbp+40h+var_B8], r12
0x1800022a0  xorps   xmm0, xmm0
0x1800022a3  movups  xmmword ptr [rbp+40h+hstringHeader.Reserved], xmm0
0x1800022a7  mov     qword ptr [rbp+40h+hstringHeader.Reserved+10h], r12
0x1800022ab  mov     [rbp+40h+var_58], r12
0x1800022af  mov     ecx, 20h ; ' '; Size
0x1800022b4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800022b9  mov     qword ptr [rbp+40h+hstringHeader.Reserved], rax
0x1800022bd  mov     qword ptr [rbp+40h+hstringHeader.Reserved+10h], 0Ch
0x1800022c5  mov     [rbp+40h+var_58], 0Fh
0x1800022cd  movups  xmm0, xmmword ptr cs:aToastgeneric; "ToastGeneric"
0x1800022d4  movups  xmmword ptr [rax], xmm0
0x1800022d7  movsd   xmm1, qword ptr cs:aToastgeneric+10h; "eric"
0x1800022df  movsd   qword ptr [rax+10h], xmm1
0x1800022e4  mov     [rax+18h], r12w
0x1800022e9  lea     rax, [rbp+40h+var_B8]
0x1800022ed  mov     [rsp+140h+var_100], rax
0x1800022f2  mov     r15d, [rbp+40h+arg_30]
0x1800022f9  mov     [rsp+140h+var_108], r15d
0x1800022fe  mov     r12d, [rbp+40h+arg_28]
0x180002302  mov     dword ptr [rsp+140h+var_110], r12d
0x180002307  mov     qword ptr [rsp+140h+var_120], rsi; int
0x18000230c  mov     r9d, r13d
0x18000230f  lea     r8, [rbp+40h+hstringHeader]
0x180002313  mov     rdx, [rsp+140h+var_E8]
0x180002318  mov     rcx, r14
0x18000231b  call    ?ParseVisual@NotificationParser@@AEAAXPEAUIXMLDOMNode@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4WPN_APP_TYPE@@PEBG3W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z; NotificationParser::ParseVisual(IXMLDOMNode *,std::wstring const &,WPN_APP_TYPE,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST,Windows::Foundation::Collections::IPropertySet * *)
0x180002320  nop
0x180002321  mov     rdx, [rbp+40h+var_58]
0x180002325  cmp     rdx, 7
0x180002329  jbe     short loc_180002366
0x18000232b  mov     rax, qword ptr [rbp+40h+hstringHeader.Reserved]
0x18000232f  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x180002337  cmp     rdx, 1000h
0x18000233e  jb      short loc_18000235E
0x180002340  mov     rcx, [rax-8]
0x180002344  sub     rax, rcx
0x180002347  sub     rax, 8
0x18000234b  cmp     rax, 1Fh
0x18000234f  ja      short loc_180002357
0x180002351  add     rdx, 27h ; '''
0x180002355  jmp     short loc_180002361
0x180002357  mov     ecx, 5
0x18000235c  int     29h; Win8: RtlFailFast(ecx)
0x18000235e  mov     rcx, rax; void *
0x180002361  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002366  mov     rbx, [rsp+140h+var_D8]
0x18000236b  mov     rax, [rbx]
0x18000236e  mov     rsi, [rax+50h]
0x180002372  mov     rdi, [rbp+40h+var_B8]
0x180002376  lea     r9, [rbp+40h+hstringHeader]; string
0x18000237a  lea     r8, [rbp+40h+hstringHeader.Reserved+8]; hstringHeader
0x18000237e  mov     edx, 6; length
0x180002383  lea     rcx, sourceString; "visual"
0x18000238a  call    cs:__imp_WindowsCreateStringReference
0x180002390  test    eax, eax
0x180002392  jns     short loc_1800023AA
0x180002394  xor     r9d, r9d; lpArguments
0x180002397  xor     r8d, r8d; nNumberOfArguments
0x18000239a  mov     edx, 1; dwExceptionFlags
0x18000239f  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800023a4  call    cs:__imp_RaiseException
0x1800023aa  lea     r9, [rsp+140h+var_F0]
0x1800023af  mov     r8, rdi
0x1800023b2  mov     rdx, qword ptr [rbp+40h+hstringHeader.Reserved]
0x1800023b6  mov     rcx, rbx
0x1800023b9  mov     rax, rsi
0x1800023bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023c1  mov     rcx, [rbp+48h]; this
0x1800023c5  test    eax, eax
0x1800023c7  js      loc_180002AD0
0x1800023cd  xor     esi, esi
0x1800023cf  mov     [rbp+40h+var_A0], rsi
0x1800023d3  mov     rcx, [rbp+40h+var_B8]
0x1800023d7  mov     rax, [rcx]
0x1800023da  lea     r8, [rbp+40h+var_A0]
0x1800023de  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x1800023e5  mov     rax, [rax]
0x1800023e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023ed  nop
0x1800023ee  mov     rcx, [rbp+48h]; this
0x1800023f2  test    eax, eax
0x1800023f4  js      loc_180002AE5
0x1800023fa  mov     [rbp+40h+var_A8], rsi
0x1800023fe  mov     rbx, [rbp+40h+var_A0]
0x180002402  mov     rax, [rbx]
0x180002405  mov     rdi, [rax+30h]
0x180002409  lea     r9, [rbp+40h+hstringHeader]; string
0x18000240d  lea     r8, [rbp+40h+hstringHeader.Reserved+8]; hstringHeader
0x180002411  mov     edx, 0Eh; length
0x180002416  lea     rcx, aActivationtype; "activationType"
0x18000241d  call    cs:__imp_WindowsCreateStringReference
0x180002423  test    eax, eax
0x180002425  jns     short loc_18000243D
0x180002427  xor     r9d, r9d; lpArguments
0x18000242a  xor     r8d, r8d; nNumberOfArguments
0x18000242d  mov     edx, 1; dwExceptionFlags
0x180002432  mov     ecx, 0C000000Dh; dwExceptionCode
0x180002437  call    cs:__imp_RaiseException
0x18000243d  lea     r8, [rbp+40h+var_A8]
0x180002441  mov     rdx, qword ptr [rbp+40h+hstringHeader.Reserved]
0x180002445  mov     rcx, rbx
0x180002448  mov     rax, rdi
0x18000244b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002450  test    eax, eax
0x180002452  js      short loc_1800024BD
0x180002454  mov     rbx, [rsp+140h+var_D8]
0x180002459  mov     rax, [rbx]
0x18000245c  mov     rsi, [rax+50h]
0x180002460  mov     rdi, [rbp+40h+var_A8]
0x180002464  lea     r9, [rbp+40h+hstringHeader]; string
0x180002468  lea     r8, [rbp+40h+hstringHeader.Reserved+8]; hstringHeader
0x18000246c  mov     edx, 0Eh; length
0x180002471  lea     rcx, aActivationtype; "activationType"
0x180002478  call    cs:__imp_WindowsCreateStringReference
0x18000247e  test    eax, eax
0x180002480  jns     short loc_180002498
0x180002482  xor     r9d, r9d; lpArguments
0x180002485  xor     r8d, r8d; nNumberOfArguments
0x180002488  mov     edx, 1; dwExceptionFlags
0x18000248d  mov     ecx, 0C000000Dh; dwExceptionCode
0x180002492  call    cs:__imp_RaiseException
0x180002498  lea     r9, [rsp+140h+var_F0]
0x18000249d  mov     r8, rdi
0x1800024a0  mov     rdx, qword ptr [rbp+40h+hstringHeader.Reserved]
0x1800024a4  mov     rcx, rbx
0x1800024a7  mov     rax, rsi
0x1800024aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024af  mov     rcx, [rbp+48h]; this
0x1800024b3  test    eax, eax
0x1800024b5  js      loc_180002AFA
0x1800024bb  xor     esi, esi
0x1800024bd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_58788260@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_58788260@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58788260> `wil::Feature<__WilFeatureTraits_Feature_58788260>::GetImpl(void)'::`2'::impl
0x1800024c4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_58788260@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58788260>::__private_IsEnabled(void)
0x1800024c9  test    al, al
0x1800024cb  jz      loc_1800025DE
0x1800024d1  mov     rbx, [rsp+140h+var_D0]
0x1800024d6  mov     rax, [rbx]
0x1800024d9  mov     rdi, [rax+128h]
0x1800024e0  mov     rdx, [rsp+140h+var_E8]
0x1800024e5  test    rdx, rdx
0x1800024e8  jz      short loc_1800024FF
0x1800024ea  mov     [rsp+140h+var_E8], rsi
0x1800024ef  mov     rcx, [rdx]
0x1800024f2  mov     rax, [rcx+10h]
0x1800024f6  mov     rcx, rdx
0x1800024f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024fe  nop
0x1800024ff  lea     r8, [rsp+140h+var_E8]
0x180002504  lea     rdx, aExpandablecont; "expandableContent"
0x18000250b  mov     rcx, rbx
0x18000250e  mov     rax, rdi
0x180002511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002516  mov     rcx, [rbp+48h]; this
0x18000251a  test    eax, eax
0x18000251c  js      loc_180002B0F
0x180002522  mov     rdx, [rsp+140h+var_E8]
0x180002527  test    rdx, rdx
0x18000252a  jz      loc_1800025E3
0x180002530  mov     qword ptr [rsp+140h+var_E0], rsi
0x180002535  lea     rax, [rsp+140h+var_E0]
0x18000253a  mov     [rsp+140h+var_110], rax
0x18000253f  mov     [rsp+140h+var_118], r15d
0x180002544  mov     [rsp+140h+var_120], r12d; int
0x180002549  mov     r8, [rsp+140h+var_C8]
0x18000254e  mov     rcx, r14
0x180002551  call    ?ParseExpandableContent@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEBG1W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z; NotificationParser::ParseExpandableContent(IXMLDOMNode *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST,Windows::Foundation::Collections::IPropertySet * *)
0x180002556  mov     rbx, [rsp+140h+var_D8]
0x18000255b  mov     rax, [rbx]
0x18000255e  mov     rsi, [rax+50h]
0x180002562  mov     rdi, qword ptr [rsp+140h+var_E0]
0x180002567  lea     r9, [rbp+40h+hstringHeader]; string
0x18000256b  lea     r8, [rbp+40h+hstringHeader.Reserved+8]; hstringHeader
0x18000256f  mov     edx, 11h; length
0x180002574  lea     rcx, aExpandablecont; "expandableContent"
0x18000257b  call    cs:__imp_WindowsCreateStringReference
0x180002581  test    eax, eax
0x180002583  jns     short loc_18000259B
0x180002585  xor     r9d, r9d; lpArguments
0x180002588  xor     r8d, r8d; nNumberOfArguments
0x18000258b  mov     edx, 1; dwExceptionFlags
0x180002590  mov     ecx, 0C000000Dh; dwExceptionCode
0x180002595  call    cs:__imp_RaiseException
  ... truncated ...
```
