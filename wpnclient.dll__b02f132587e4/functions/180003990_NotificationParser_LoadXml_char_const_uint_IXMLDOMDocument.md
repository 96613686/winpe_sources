# NotificationParser::LoadXml(char const *,uint,IXMLDOMDocument * *)

- ea: `0x180003990`
- end: `0x1800043c9`
- name: `?LoadXml@NotificationParser@@AEAAXPEBDIPEAPEAUIXMLDOMDocument@@@Z`
- size: `2617`
- prototype: `void(NotificationParser *__hidden this, const char *, unsigned int, struct IXMLDOMDocument **)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800020d0`
- `0x180002b70`

## callees

- `0x180003990`
- `0x1800043d0`
- `0x180004868`
- `0x1800180cc`
- `0x18001b848`
- `0x18001ff00`
- `0x180020d34`
- `0x180025700`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800042d4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800042d4`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180003a3a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180003a9b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180003a3a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180003a9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180003d9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180003d9e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180003dd7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180003dd7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003afe`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003be6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003e08`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003eea`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003afe`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003be6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003e08`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003eea`
- `OLEAUT32!__imp_SysAllocString` at `0x1800039dd`
- `OLEAUT32!__imp_SysAllocString` at `0x180003aae`
- `OLEAUT32!__imp_SysAllocString` at `0x1800039dd`
- `OLEAUT32!__imp_SysAllocString` at `0x180003aae`
- `OLEAUT32!__imp_SysFreeString` at `0x180003cf9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000406d`
- `OLEAUT32!__imp_SysFreeString` at `0x180004077`
- `OLEAUT32!__imp_SysFreeString` at `0x180003cf9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000406d`
- `OLEAUT32!__imp_SysFreeString` at `0x180004077`
- `OLEAUT32!__imp_VariantClear` at `0x180003d2c`
- `OLEAUT32!__imp_VariantClear` at `0x180003e99`
- `OLEAUT32!__imp_VariantClear` at `0x18000400b`
- `OLEAUT32!__imp_VariantClear` at `0x180003d2c`
- `OLEAUT32!__imp_VariantClear` at `0x180003e99`
- `OLEAUT32!__imp_VariantClear` at `0x18000400b`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
void __fastcall NotificationParser::LoadXml(
        NotificationParser *this,
        const char *a2,
        unsigned int a3,
        struct IXMLDOMDocument **a4)
{
  OLECHAR *v7; // rbx
  unsigned __int64 v8; // rax
  int v9; // eax
  int cchWideChar; // r14d
  LONGLONG v11; // r15
  unsigned __int64 v12; // rcx
  LONGLONG v13; // rax
  OLECHAR *v14; // rdi
  HRESULT v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  struct IXMLDOMDocument2 *v19; // rcx
  LPVOID v20; // rcx
  HRESULT v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  LPVOID v27; // rcx
  LPVOID v28; // rcx
  struct IXMLDOMDocument2 *v29; // rcx
  PVOID Reserved1; // rdi
  __int64 v31; // rcx
  int ActivationFactory; // eax
  HRESULT v33; // eax
  struct IXMLDOMDocument2 *v34; // rcx
  LPVOID v35; // rdi
  __int64 (__fastcall *v36)(LPVOID, OLECHAR *, HSTRING_HEADER *); // rsi
  int v37; // edi
  struct IXMLDOMDocument *v38; // rcx
  HRESULT v39; // eax
  int v40; // eax
  int v41; // eax
  int v42; // eax
  LPVOID v43; // rdi
  __int64 (__fastcall *v44)(LPVOID, GUID *, __int64 *); // rsi
  __int64 v45; // rcx
  int v46; // eax
  __int64 v47; // rdi
  __int64 (__fastcall *v48)(__int64, HSTRING_HEADER *); // rsi
  int v49; // edi
  int v50; // eax
  struct IXMLDOMDocument *v51; // rax
  struct IXMLDOMDocument2 *v52; // rcx
  LPVOID v53; // rcx
  __int64 v54; // rcx
  struct IXMLDOMDocument *v55; // rcx
  size_t v56; // rdi
  int lpWideCharStr; // [rsp+20h] [rbp-A9h]
  int lpWideCharStra; // [rsp+20h] [rbp-A9h]
  int lpWideCharStrb; // [rsp+20h] [rbp-A9h]
  int lpWideCharStrc; // [rsp+20h] [rbp-A9h]
  int lpWideCharStrd; // [rsp+20h] [rbp-A9h]
  int lpWideCharStre; // [rsp+20h] [rbp-A9h]
  __int16 v63; // [rsp+30h] [rbp-99h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-91h] BYREF
  LPVOID v65; // [rsp+40h] [rbp-89h] BYREF
  HSTRING_HEADER psz; // [rsp+48h] [rbp-81h] BYREF
  __int64 v67; // [rsp+60h] [rbp-69h] BYREF
  struct IXMLDOMDocument *v68; // [rsp+68h] [rbp-61h]
  LPVOID v69; // [rsp+70h] [rbp-59h]
  struct IXMLDOMDocument2 *v70; // [rsp+78h] [rbp-51h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp-49h] BYREF
  struct IXMLDOMDocument2 *v72; // [rsp+88h] [rbp-41h] BYREF
  LPVOID v73; // [rsp+90h] [rbp-39h] BYREF
  struct IXMLDOMDocument **v74; // [rsp+98h] [rbp-31h]
  OLECHAR *v75; // [rsp+A0h] [rbp-29h]
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v74 = a4;
  v68 = 0;
  v67 = 0;
  v73 = 0;
  v72 = 0;
  v7 = SysAllocString(&pwzBaseUrl);
  v75 = v7;
  v63 = 0;
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  if ( v8 >= 3 )
  {
    if ( *a2 == -17 && a2[1] == -69 && a2[2] == -65 )
    {
      a2 += 3;
      goto LABEL_5;
    }
  }
  else if ( v8 < 2 )
  {
    goto LABEL_5;
  }
  if ( *a2 == -2 )
  {
    if ( a2[1] == -1 )
LABEL_74:
      a2 += 2;
  }
  else if ( *a2 == -1 && a2[1] == -2 )
  {
    goto LABEL_74;
  }
LABEL_5:
  std::vector<Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord>::vector<Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord>(&psz);
  v9 = MultiByteToWideChar(0xFDE9u, 8u, a2, -1, 0, 0);
  cchWideChar = v9;
  if ( v9 <= 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x22C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)0x8000FFFFLL,
      lpWideCharStr);
  v11 = *(_QWORD *)&psz.Reserved.Reserved2[8];
  v12 = (__int64)(*(_QWORD *)&psz.Reserved.Reserved2[8] - (unsigned __int64)psz.Reserved.Reserved1) >> 1;
  if ( v9 < v12 )
  {
    v13 = (LONGLONG)psz.Reserved.Reserved1 + 2 * v9;
LABEL_8:
    *(_QWORD *)&psz.Reserved.Reserved2[8] = v13;
    goto LABEL_9;
  }
  if ( v9 > v12 )
  {
    if ( v9 <= (unsigned __int64)((__int64)(*(_QWORD *)&psz.Reserved.Reserved2[16]
                                          - (unsigned __int64)psz.Reserved.Reserved1) >> 1) )
    {
      v56 = 2 * (v9 - v12);
      memset_0(*(void **)&psz.Reserved.Reserved2[8], 0, v56);
      v13 = v56 + v11;
      goto LABEL_8;
    }
    std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(&psz, v9);
  }
LABEL_9:
  if ( MultiByteToWideChar(0xFDE9u, 8u, a2, -1, (LPWSTR)psz.Reserved.Reserved1, cchWideChar) <= 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x237,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)0x8000FFFFLL,
      lpWideCharStra);
  v14 = SysAllocString((const OLECHAR *)psz.Reserved.Reserved1);
  if ( psz.Reserved.Reserved1 )
    std::_Deallocate<16>(
      psz.Reserved.Reserved1,
      2 * ((__int64)(*(_QWORD *)&psz.Reserved.Reserved2[16] - (unsigned __int64)psz.Reserved.Reserved1) >> 1));
  bstrString = v14;
  v70 = 0;
  v69 = 0;
  v65 = 0;
  ppv = 0;
  v15 = CoCreateInstance(
          &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
          0,
          1u,
          &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60,
          &ppv);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F5,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v15,
      lpWideCharStrb);
  v16 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F7,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v16,
      lpWideCharStrb);
  v17 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 544LL))(ppv, 0);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1FF,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v17,
      lpWideCharStrb);
  v18 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 560LL))(ppv, 0);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x200,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v18,
      lpWideCharStrb);
  v65 = ppv;
  v19 = v70;
  if ( v70 )
  {
    v70 = 0;
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v19->lpVtbl->Release)(v19);
  }
  XmlDocFromResource(a3, &v70);
  v20 = v69;
  if ( v69 )
  {
    v69 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
  }
  ppv = 0;
  v21 = CoCreateInstance(
          &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
          0,
          1u,
          &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60,
          &ppv);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F5,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v21,
      lpWideCharStrc);
  v22 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F7,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v22,
      lpWideCharStrc);
  v23 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 544LL))(ppv, 0);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1FF,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v23,
      lpWideCharStrc);
  v24 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 560LL))(ppv, 0);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x200,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v24,
      lpWideCharStrc);
  v69 = ppv;
  (*(void (__fastcall **)(LPVOID, BSTR, __int16 *))(*(_QWORD *)ppv + 520LL))(ppv, bstrString, &v63);
  if ( v63 != -1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x22E,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)0xC00CE225LL,
      lpWideCharStrc);
  LOWORD(psz.Reserved.Reserved1) = 9;
  *(_QWORD *)&psz.Reserved.Reserved2[8] = v65;
  if ( v65 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v65 + 8LL))(v65);
  hstringHeader = psz;
  v25 = (*(__int64 (__fastcall **)(LPVOID, struct IXMLDOMDocument2 *, HSTRING_HEADER *))(*(_QWORD *)v69 + 336LL))(
          v69,
          v70,
          &hstringHeader);
  if ( v25 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x232,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v25,
      lpWideCharStrc);
  SysFreeString(bstrString);
  bstrString = 0;
  v26 = (*(__int64 (__fastcall **)(LPVOID, BSTR *))(*(_QWORD *)v65 + 272LL))(v65, &bstrString);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x236,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v26,
      lpWideCharStrc);
  VariantClear((VARIANTARG *)&psz);
  v27 = v65;
  if ( v65 )
  {
    v65 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
  }
  v28 = v69;
  if ( v69 )
  {
    v69 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v28 + 16LL))(v28);
  }
  v29 = v70;
  if ( v70 )
  {
    v70 = 0;
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v29->lpVtbl->Release)(v29);
  }
  if ( !*(_QWORD *)this )
  {
    if ( WindowsCreateStringReference(
           L"Windows.Foundation.PropertyValue",
           0x20u,
           (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
           (HSTRING *)&hstringHeader) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    Reserved1 = hstringHeader.Reserved.Reserved1;
    v31 = *(_QWORD *)this;
    if ( *(_QWORD *)this )
    {
      *(_QWORD *)this = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    ActivationFactory = RoGetActivationFactory(Reserved1, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, this);
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x23D,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)ActivationFactory,
        lpWideCharStrc);
  }
  v33 = CoCreateInstance(
          &GUID_88d96a07_f192_11d4_a65f_0040963251e5,
          0,
          1u,
          &GUID_373984c8_b845_449b_91e7_45ac83036ade,
          &v73);
  if ( v33 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x242,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v33,
      lpWideCharStrd);
  v34 = v72;
  if ( v72 )
  {
    v72 = 0;
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v34->lpVtbl->Release)(v34);
  }
  XmlDocFromResource(0x65u, &v72);
  v35 = v73;
  v36 = *(__int64 (__fastcall **)(LPVOID, OLECHAR *, HSTRING_HEADER *))(*(_QWORD *)v73 + 56LL);
  LOWORD(psz.Reserved.Reserved1) = 9;
  *(_QWORD *)&psz.Reserved.Reserved2[8] = v72;
  if ( v72 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v72->lpVtbl->AddRef)(v72);
  hstringHeader = psz;
  v37 = v36(v35, v7, &hstringHeader);
  VariantClear((VARIANTARG *)&psz);
  if ( v37 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x248,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v37,
      lpWideCharStrd);
  v38 = v68;
  if ( v68 )
  {
    v68 = 0;
    ((void (__fastcall *)(struct IXMLDOMDocument *))v38->lpVtbl->Release)(v38);
  }
  v65 = 0;
  v39 = CoCreateInstance(
          &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
          0,
          1u,
          &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60,
          &v65);
  if ( v39 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F5,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v39,
      lpWideCharStre);
  v40 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v65 + 504LL))(v65, 0);
  if ( v40 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F7,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v40,
      lpWideCharStre);
  v41 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v65 + 544LL))(v65, 0xFFFFFFFFLL);
  if ( v41 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1FA,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v41,
      lpWideCharStre);
  v42 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v65 + 560LL))(v65, 0xFFFFFFFFLL);
  if ( v42 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1FB,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v42,
      lpWideCharStre);
  v43 = v65;
  v68 = (struct IXMLDOMDocument *)v65;
  v44 = **(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v65;
  v45 = v67;
  if ( v67 )
  {
    v67 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  }
  v46 = v44(v43, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, &v67);
  if ( v46 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x24E,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v46,
      lpWideCharStre);
  v47 = v67;
  v48 = *(__int64 (__fastcall **)(__int64, HSTRING_HEADER *))(*(_QWORD *)v67 + 624LL);
  LOWORD(psz.Reserved.Reserved1) = 9;
  *(_QWORD *)&psz.Reserved.Reserved2[8] = v73;
  if ( v73 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v73 + 8LL))(v73);
  hstringHeader = psz;
  v49 = v48(v47, &hstringHeader);
  VariantClear((VARIANTARG *)&psz);
  if ( v49 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x252,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v49,
      lpWideCharStre);
  v50 = (*(__int64 (__fastcall **)(__int64, BSTR, __int16 *))(*(_QWORD *)v67 + 520LL))(v67, bstrString, &v63);
  if ( v50 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x256,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v50,
      lpWideCharStre);
  if ( v63 != -1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x257,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)0xC00CE225LL,
      lpWideCharStre);
  v51 = v68;
  v68 = 0;
  *v74 = v51;
  SysFreeString(bstrString);
  SysFreeString(v7);
  v52 = v72;
  if ( v72 )
  {
    v72 = 0;
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v52->lpVtbl->Release)(v52);
  }
  v53 = v73;
  if ( v73 )
  {
    v73 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v53 + 16LL))(v53);
  }
  v54 = v67;
  if ( v67 )
  {
    v67 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
  }
  v55 = v68;
  if ( v68 )
  {
    v68 = 0;
    ((void (__fastcall *)(struct IXMLDOMDocument *))v55->lpVtbl->Release)(v55);
  }
}

```

## disassembly

```asm
0x180003990  push    rbp
0x180003992  push    rbx
0x180003993  push    rsi
0x180003994  push    rdi
0x180003995  push    r12
0x180003997  push    r13
0x180003999  push    r14
0x18000399b  push    r15
0x18000399d  lea     rbp, [rsp-1Fh]
0x1800039a2  sub     rsp, 0E8h
0x1800039a9  mov     rax, cs:__security_cookie
0x1800039b0  xor     rax, rsp
0x1800039b3  mov     [rbp+57h+var_50], rax
0x1800039b7  mov     [rbp+57h+var_88], r9
0x1800039bb  mov     r13d, r8d
0x1800039be  mov     rsi, rdx
0x1800039c1  mov     r12, rcx
0x1800039c4  xor     edi, edi
0x1800039c6  mov     [rbp+57h+var_B8], rdi
0x1800039ca  mov     [rbp+57h+var_C0], rdi
0x1800039ce  mov     [rbp+57h+var_90], rdi
0x1800039d2  mov     [rbp+57h+var_98], rdi
0x1800039d6  lea     rcx, pwzBaseUrl; psz
0x1800039dd  call    cs:__imp_SysAllocString
0x1800039e3  mov     rbx, rax
0x1800039e6  mov     [rbp+57h+var_80], rax
0x1800039ea  mov     [rsp+120h+var_F0], di
0x1800039ef  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800039f6  inc     rax
0x1800039f9  cmp     byte ptr [rsi+rax], 0
0x1800039fd  jnz     short loc_1800039F6
0x1800039ff  cmp     rax, 3
0x180003a03  jnb     loc_180004106
0x180003a09  cmp     rax, 2
0x180003a0d  jnb     loc_18000410B
0x180003a13  lea     rcx, [rsp+120h+psz]
0x180003a18  call    ??0?$vector@UAppInfoRecord@CAppInfoAggregator@Notifications@Internal@Windows@@V?$allocator@UAppInfoRecord@CAppInfoAggregator@Notifications@Internal@Windows@@@std@@@std@@QEAA@XZ; std::vector<Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord>::vector<Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord>(void)
0x180003a1d  nop
0x180003a1e  mov     [rsp+120h+cchWideChar], edi; cchWideChar
0x180003a22  mov     [rsp+120h+lpWideCharStr], rdi; int
0x180003a27  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x180003a2d  mov     r8, rsi; lpMultiByteStr
0x180003a30  mov     edx, 8; dwFlags
0x180003a35  mov     ecx, 0FDE9h; CodePage
0x180003a3a  call    cs:__imp_MultiByteToWideChar
0x180003a40  movsxd  r14, eax
0x180003a43  mov     rcx, [rbp+5Fh]; this
0x180003a47  test    eax, eax
0x180003a49  jle     loc_18000414D
0x180003a4f  mov     rdi, r14
0x180003a52  mov     r15, [rbp+57h+psz+8]
0x180003a56  mov     rdx, [rsp+120h+psz]
0x180003a5b  mov     rcx, r15
0x180003a5e  sub     rcx, rdx
0x180003a61  sar     rcx, 1
0x180003a64  cmp     r14, rcx
0x180003a67  jnb     loc_180004165
0x180003a6d  lea     rax, [rdx+r14*2]
0x180003a71  mov     [rbp+57h+psz+8], rax
0x180003a75  mov     rdi, [rbp+5Fh]
0x180003a79  mov     [rsp+120h+cchWideChar], r14d; cchWideChar
0x180003a7e  mov     rax, [rsp+120h+psz]
0x180003a83  mov     [rsp+120h+lpWideCharStr], rax; int
0x180003a88  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x180003a8e  mov     r8, rsi; lpMultiByteStr
0x180003a91  mov     edx, 8; dwFlags
0x180003a96  mov     ecx, 0FDE9h; CodePage
0x180003a9b  call    cs:__imp_MultiByteToWideChar
0x180003aa1  test    eax, eax
0x180003aa3  jle     loc_1800041A8
0x180003aa9  mov     rcx, [rsp+120h+psz]; psz
0x180003aae  call    cs:__imp_SysAllocString
0x180003ab4  mov     rdi, rax
0x180003ab7  mov     rcx, [rsp+120h+psz]
0x180003abc  test    rcx, rcx
0x180003abf  jnz     loc_1800041C3
0x180003ac5  mov     [rbp+57h+bstrString], rdi
0x180003ac9  xor     r14d, r14d
0x180003acc  mov     [rbp+57h+var_A8], r14
0x180003ad0  mov     [rbp+57h+var_B0], r14
0x180003ad4  mov     [rsp+120h+var_E0], r14
0x180003ad9  mov     [rsp+120h+ppv], r14
0x180003ade  lea     rax, [rsp+120h+ppv]
0x180003ae3  mov     [rsp+120h+lpWideCharStr], rax; int
0x180003ae8  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x180003aef  xor     edx, edx; pUnkOuter
0x180003af1  mov     r8d, 1; dwClsContext
0x180003af7  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x180003afe  call    cs:__imp_CoCreateInstance
0x180003b04  mov     rcx, [rbp+5Fh]; this
0x180003b08  test    eax, eax
0x180003b0a  js      loc_1800041DA
0x180003b10  mov     rcx, [rsp+120h+ppv]
0x180003b15  mov     rax, [rcx]
0x180003b18  xor     edx, edx
0x180003b1a  mov     rax, [rax+1F8h]
0x180003b21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b26  mov     rcx, [rbp+5Fh]; this
0x180003b2a  test    eax, eax
0x180003b2c  js      loc_1800041EF
0x180003b32  mov     rcx, [rsp+120h+ppv]
0x180003b37  mov     rax, [rcx]
0x180003b3a  xor     edx, edx
0x180003b3c  mov     rax, [rax+220h]
0x180003b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b48  mov     rcx, [rbp+5Fh]; this
0x180003b4c  test    eax, eax
0x180003b4e  js      loc_180004204
0x180003b54  mov     rcx, [rsp+120h+ppv]
0x180003b59  mov     rax, [rcx]
0x180003b5c  xor     edx, edx
0x180003b5e  mov     rax, [rax+230h]
0x180003b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b6a  mov     rcx, [rbp+5Fh]; this
0x180003b6e  test    eax, eax
0x180003b70  js      loc_180004219
0x180003b76  mov     rax, [rsp+120h+ppv]
0x180003b7b  mov     [rsp+120h+var_E0], rax
0x180003b80  mov     rcx, [rbp+57h+var_A8]
0x180003b84  test    rcx, rcx
0x180003b87  jz      short loc_180003B9A
0x180003b89  mov     [rbp+57h+var_A8], r14
0x180003b8d  mov     rax, [rcx]
0x180003b90  mov     rax, [rax+10h]
0x180003b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b99  nop
0x180003b9a  lea     rdx, [rbp+57h+var_A8]; struct IXMLDOMDocument2 **
0x180003b9e  mov     ecx, r13d; unsigned int
0x180003ba1  call    ?XmlDocFromResource@@YAXIPEAPEAUIXMLDOMDocument2@@@Z; XmlDocFromResource(uint,IXMLDOMDocument2 * *)
0x180003ba6  nop
0x180003ba7  mov     rcx, [rbp+57h+var_B0]
0x180003bab  test    rcx, rcx
0x180003bae  jz      short loc_180003BC1
0x180003bb0  mov     [rbp+57h+var_B0], r14
0x180003bb4  mov     rax, [rcx]
0x180003bb7  mov     rax, [rax+10h]
0x180003bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bc0  nop
0x180003bc1  mov     [rsp+120h+ppv], r14
0x180003bc6  lea     rax, [rsp+120h+ppv]
0x180003bcb  mov     [rsp+120h+lpWideCharStr], rax; int
0x180003bd0  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x180003bd7  xor     edx, edx; pUnkOuter
0x180003bd9  mov     r8d, 1; dwClsContext
0x180003bdf  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x180003be6  call    cs:__imp_CoCreateInstance
0x180003bec  mov     rcx, [rbp+5Fh]; this
0x180003bf0  test    eax, eax
0x180003bf2  js      loc_18000422E
0x180003bf8  mov     rcx, [rsp+120h+ppv]
0x180003bfd  mov     rax, [rcx]
0x180003c00  xor     edx, edx
0x180003c02  mov     rax, [rax+1F8h]
0x180003c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c0e  mov     rcx, [rbp+5Fh]; this
0x180003c12  test    eax, eax
0x180003c14  js      loc_180004243
0x180003c1a  mov     rcx, [rsp+120h+ppv]
0x180003c1f  mov     rax, [rcx]
0x180003c22  xor     edx, edx
0x180003c24  mov     rax, [rax+220h]
0x180003c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c30  mov     rcx, [rbp+5Fh]; this
0x180003c34  test    eax, eax
0x180003c36  js      loc_180004258
0x180003c3c  mov     rcx, [rsp+120h+ppv]
0x180003c41  mov     rax, [rcx]
0x180003c44  xor     edx, edx
0x180003c46  mov     rax, [rax+230h]
0x180003c4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c52  mov     rcx, [rbp+5Fh]; this
0x180003c56  test    eax, eax
0x180003c58  js      loc_18000426D
0x180003c5e  mov     rcx, [rsp+120h+ppv]
0x180003c63  mov     [rbp+57h+var_B0], rcx
0x180003c67  mov     rax, [rcx]
0x180003c6a  lea     r8, [rsp+120h+var_F0]
0x180003c6f  mov     rdx, [rbp+57h+bstrString]
0x180003c73  mov     rax, [rax+208h]
0x180003c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c7f  cmp     [rsp+120h+var_F0], 0FFFFh
0x180003c85  setz    al
0x180003c88  mov     rcx, [rbp+5Fh]; this
0x180003c8c  test    al, al
0x180003c8e  jz      loc_180004282
0x180003c94  mov     r15d, 9
0x180003c9a  mov     word ptr [rsp+120h+psz], r15w
0x180003ca0  mov     rcx, [rsp+120h+var_E0]
0x180003ca5  mov     [rbp+57h+psz+8], rcx
0x180003ca9  test    rcx, rcx
0x180003cac  jz      short loc_180003CBB
0x180003cae  mov     rax, [rcx]
0x180003cb1  mov     rax, [rax+8]
0x180003cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cba  nop
0x180003cbb  mov     rcx, [rbp+57h+var_B0]
0x180003cbf  movups  xmm0, xmmword ptr [rsp+120h+psz]
0x180003cc4  movaps  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x180003cc8  movsd   xmm1, [rbp+57h+var_C8]
0x180003ccd  movsd   qword ptr [rbp+57h+hstringHeader.Reserved+10h], xmm1
0x180003cd2  mov     rax, [rcx]
0x180003cd5  lea     r8, [rbp+57h+hstringHeader]
0x180003cd9  mov     rdx, [rbp+57h+var_A8]
0x180003cdd  mov     rax, [rax+150h]
0x180003ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ce9  mov     rcx, [rbp+5Fh]; this
0x180003ced  test    eax, eax
0x180003cef  js      loc_18000429A
0x180003cf5  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180003cf9  call    cs:__imp_SysFreeString
0x180003cff  mov     [rbp+57h+bstrString], r14
0x180003d03  mov     rcx, [rsp+120h+var_E0]
0x180003d08  mov     rax, [rcx]
0x180003d0b  lea     rdx, [rbp+57h+bstrString]
0x180003d0f  mov     rax, [rax+110h]
0x180003d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d1b  mov     rcx, [rbp+5Fh]; this
0x180003d1f  test    eax, eax
0x180003d21  js      loc_1800042AF
0x180003d27  lea     rcx, [rsp+120h+psz]; pvarg
0x180003d2c  call    cs:__imp_VariantClear
0x180003d32  nop
0x180003d33  mov     rcx, [rsp+120h+var_E0]
0x180003d38  test    rcx, rcx
0x180003d3b  jz      short loc_180003D4F
0x180003d3d  mov     [rsp+120h+var_E0], r14
0x180003d42  mov     rax, [rcx]
0x180003d45  mov     rax, [rax+10h]
0x180003d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d4e  nop
0x180003d4f  mov     rcx, [rbp+57h+var_B0]
0x180003d53  test    rcx, rcx
0x180003d56  jz      short loc_180003D69
0x180003d58  mov     [rbp+57h+var_B0], r14
0x180003d5c  mov     rax, [rcx]
0x180003d5f  mov     rax, [rax+10h]
0x180003d63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d68  nop
0x180003d69  mov     rcx, [rbp+57h+var_A8]
0x180003d6d  test    rcx, rcx
0x180003d70  jz      short loc_180003D83
0x180003d72  mov     [rbp+57h+var_A8], r14
0x180003d76  mov     rax, [rcx]
0x180003d79  mov     rax, [rax+10h]
0x180003d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d82  nop
0x180003d83  cmp     qword ptr [r12], 0
0x180003d88  jnz     short loc_180003DE9
0x180003d8a  lea     r9, [rbp+57h+hstringHeader]; string
0x180003d8e  lea     r8, [rbp+57h+hstringHeader.Reserved+8]; hstringHeader
0x180003d92  mov     edx, 20h ; ' '; length
0x180003d97  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x180003d9e  call    cs:__imp_WindowsCreateStringReference
0x180003da4  test    eax, eax
0x180003da6  js      loc_1800042C4
0x180003dac  mov     rdi, qword ptr [rbp+57h+hstringHeader.Reserved]
0x180003db0  mov     rcx, [r12]
0x180003db4  test    rcx, rcx
0x180003db7  jz      short loc_180003DCA
0x180003db9  mov     [r12], r14
0x180003dbd  mov     rax, [rcx]
0x180003dc0  mov     rax, [rax+10h]
0x180003dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dc9  nop
0x180003dca  mov     r8, r12
0x180003dcd  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x180003dd4  mov     rcx, rdi
0x180003dd7  call    cs:__imp_RoGetActivationFactory
0x180003ddd  mov     rcx, [rbp+5Fh]; this
0x180003de1  test    eax, eax
0x180003de3  js      loc_1800042DF
0x180003de9  lea     rax, [rbp+57h+var_90]
0x180003ded  mov     [rsp+120h+lpWideCharStr], rax; int
0x180003df2  lea     r9, _GUID_373984c8_b845_449b_91e7_45ac83036ade; riid
0x180003df9  xor     edx, edx; pUnkOuter
0x180003dfb  mov     r8d, 1; dwClsContext
0x180003e01  lea     rcx, _GUID_88d96a07_f192_11d4_a65f_0040963251e5; rclsid
0x180003e08  call    cs:__imp_CoCreateInstance
0x180003e0e  mov     rcx, [rbp+5Fh]; this
0x180003e12  test    eax, eax
0x180003e14  js      loc_1800042F4
0x180003e1a  mov     rcx, [rbp+57h+var_98]
0x180003e1e  test    rcx, rcx
0x180003e21  jz      short loc_180003E34
0x180003e23  mov     [rbp+57h+var_98], r14
0x180003e27  mov     rax, [rcx]
0x180003e2a  mov     rax, [rax+10h]
0x180003e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e33  nop
0x180003e34  lea     rdx, [rbp+57h+var_98]; struct IXMLDOMDocument2 **
0x180003e38  mov     ecx, 65h ; 'e'; unsigned int
0x180003e3d  call    ?XmlDocFromResource@@YAXIPEAPEAUIXMLDOMDocument2@@@Z; XmlDocFromResource(uint,IXMLDOMDocument2 * *)
0x180003e42  mov     rdi, [rbp+57h+var_90]
0x180003e46  mov     rax, [rdi]
0x180003e49  mov     rsi, [rax+38h]
0x180003e4d  mov     word ptr [rsp+120h+psz], r15w
0x180003e53  mov     rcx, [rbp+57h+var_98]
0x180003e57  mov     [rbp+57h+psz+8], rcx
0x180003e5b  test    rcx, rcx
0x180003e5e  jz      short loc_180003E6D
  ... truncated ...
```
