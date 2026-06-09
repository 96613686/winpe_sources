# DeviceIdStore::AddDeviceInfoToPersistentStore(ushort const *,ushort const *,CAutoZeroMemoryStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CTime const &,ATL::CTime const &,bool)

- ea: `0x180101fe8`
- end: `0x180102790`
- name: `?AddDeviceInfoToPersistentStore@DeviceIdStore@@SAJPEBG0AEBV?$CAutoZeroMemoryStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@@AEBVCTime@ATL@@2_N@Z`
- size: `1960`
- prototype: ``
- caller_count: `2`
- callee_count: `30`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180100200`
- `0x1801033c0`

## callees

- `0x18000c050`
- `0x18000ed04`
- `0x180012f64`
- `0x180013fb4`
- `0x1800151c4`
- `0x180015430`
- `0x1800191c0`
- `0x180019690`
- `0x180019780`
- `0x18001a530`
- `0x18001a9c0`
- `0x180021b28`
- `0x180021bbc`
- `0x180037288`
- `0x1800396e8`
- `0x180039d60`
- `0x180039ee8`
- `0x18003c814`
- `0x1800406a8`
- `0x1800469b8`
- `0x18007c408`
- `0x1800814f8`
- `0x180087a84`
- `0x18008916c`
- `0x180098f5c`
- `0x180101fe8`
- `0x180102f10`
- `0x1801066ac`
- `0x180107238`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010257a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010257a`
- `OLEAUT32!__imp_SysFreeString` at `0x1801023c7`
- `OLEAUT32!__imp_SysFreeString` at `0x18010265d`
- `OLEAUT32!__imp_SysFreeString` at `0x1801023c7`
- `OLEAUT32!__imp_SysFreeString` at `0x18010265d`
- `OLEAUT32!__imp_VariantInit` at `0x18010204c`
- `OLEAUT32!__imp_VariantInit` at `0x18010204c`
- `OLEAUT32!__imp_VariantClear` at `0x180102242`
- `OLEAUT32!__imp_VariantClear` at `0x180102252`
- `OLEAUT32!__imp_VariantClear` at `0x18010225e`
- `OLEAUT32!__imp_VariantClear` at `0x1801022ee`
- `OLEAUT32!__imp_VariantClear` at `0x1801022fa`
- `OLEAUT32!__imp_VariantClear` at `0x18010246f`
- `OLEAUT32!__imp_VariantClear` at `0x180102707`
- `OLEAUT32!__imp_VariantClear` at `0x180102242`
- `OLEAUT32!__imp_VariantClear` at `0x180102252`
- `OLEAUT32!__imp_VariantClear` at `0x18010225e`
- `OLEAUT32!__imp_VariantClear` at `0x1801022ee`
- `OLEAUT32!__imp_VariantClear` at `0x1801022fa`
- `OLEAUT32!__imp_VariantClear` at `0x18010246f`
- `OLEAUT32!__imp_VariantClear` at `0x180102707`
- `CRYPT32!CryptProtectData` at `0x180102570`
- `CRYPT32!CryptProtectData` at `0x180102570`

## string_xrefs

- `0x1801020b7`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x180102180`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x180102230`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x1801022d7`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x180102334`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x1801025af`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x1801026a5`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x180102214`: `hr = pDocumentElement->setAttribute(g_bstrDeviceLastUpdatedTime, cvAttributeValue)`
- `0x1801023d1`: `hr = pDOM->selectSingleNode(CComBSTR(wstrXPath), &pPasswordNode)`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall DeviceIdStore::AddDeviceInfoToPersistentStore(
        __int64 a1,
        _WORD *a2,
        LONGLONG *a3,
        LONGLONG *a4,
        LONGLONG *a5,
        char a6)
{
  unsigned __int8 v10; // dl
  PPTraceStatus *v11; // rcx
  bool v12; // zf
  char v13; // cl
  char v14; // al
  const unsigned __int16 *String; // rax
  __int64 v16; // r8
  char v17; // di
  const char *v18; // rax
  unsigned int v19; // r8d
  int v20; // eax
  __int64 v21; // rbx
  int v22; // eax
  __int64 v23; // rcx
  LONGLONG v24; // rax
  int v25; // eax
  LONGLONG v26; // rdx
  int v27; // eax
  int v28; // eax
  const char *v29; // rcx
  unsigned int v30; // r8d
  __int64 (__fastcall *v31)(__int64, _QWORD, __int64 *); // rdi
  ATL::CComBSTR *v32; // rax
  int v33; // edi
  signed int LastError; // eax
  const char *v35; // rcx
  unsigned int v36; // r8d
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, _QWORD); // rbx
  ATL::CComBSTR *v39; // rax
  unsigned int v40; // ebx
  CRYPTPROTECT_PROMPTSTRUCT *pPromptStruct; // [rsp+20h] [rbp-E0h]
  __int64 v43; // [rsp+40h] [rbp-C0h] BYREF
  DATA_BLOB bstrString; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG v45; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v46; // [rsp+70h] [rbp-90h] BYREF
  __int64 v47; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG v48; // [rsp+80h] [rbp-80h] BYREF
  char v49; // [rsp+98h] [rbp-68h]
  __int64 v50; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v51; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v52; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v53; // [rsp+B8h] [rbp-48h] BYREF
  char *v54; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v55; // [rsp+C8h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v57[16]; // [rsp+E8h] [rbp-18h] BYREF
  const char *v58[13]; // [rsp+F8h] [rbp-8h] BYREF
  int v59; // [rsp+178h] [rbp+78h] BYREF

  v59 = 0;
  v47 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v55);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v51);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v54);
  v50 = 0;
  v46 = 0;
  v53 = 0;
  v52 = 0;
  VariantInit(&pvarg);
  if ( !PPTraceShouldRedact() || (LOBYTE(v11) = 1, v12 = !PPTraceStatus::TraceOnFlag(v11, v10), v14 = v13, v12) )
    v14 = 0;
  *(_OWORD *)&v48.decVal.Lo32 = (unsigned __int64)a2;
  v49 = v14;
  *(_QWORD *)&v48.vt = &PPRedactedStringW::`vftable';
  String = PPRedactedStringW::GetString((PPRedactedStringW *)&v48);
  CTraceFuncW<long>::CTraceFuncW<long>(
    v58,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
    927,
    (const char *)&v59,
    "DeviceIdStore::AddDeviceInfoToPersistentStore",
    L"wstrDeviceIDKey=%ls,wszUserName=%ls",
    a1,
    String);
  PPRedactedStringW::~PPRedactedStringW((PPRedactedStringW *)&v48);
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(
    (__int64)v57,
    (struct _RTL_CRITICAL_SECTION *)qword_1801C43A8,
    1);
  if ( !a2 || !*a2 )
  {
    v18 = "wszUserName != nullptr && *wszUserName != L'\\0'";
    v19 = 932;
LABEL_54:
    v59 = -2147024809;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
      "DeviceIdStore::AddDeviceInfoToPersistentStore",
      v19,
      -2147024809,
      v18);
    goto LABEL_56;
  }
  v17 = a6;
  if ( a6 && !*(_DWORD *)(*a3 - 16) )
  {
    v18 = "!persistPassword || !wstrPwd.IsEmpty()";
    v19 = 934;
    goto LABEL_54;
  }
  LOBYTE(v16) = 1;
  v20 = DeviceIdStore::LoadPersistedDOM(a1, a2, v16, &v47);
  v59 = v20;
  if ( v20 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
      "DeviceIdStore::AddDeviceInfoToPersistentStore",
      0x3A8u,
      v20,
      "hr = DeviceIdStore::LoadPersistedDOM(wstrDeviceIDKey, wszUserName, true, pDOM)");
    goto LABEL_56;
  }
  v21 = v47;
  if ( !v47 )
  {
    LODWORD(pPromptStruct) = v20;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
      0x3ABu,
      L"::LoadPersistedDOM failed with hr = %x",
      pPromptStruct);
    goto LABEL_56;
  }
  v22 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v47 + 360LL))(v47, &v50);
  v59 = v22;
  if ( !v22 )
  {
    v23 = v50;
    if ( v50 )
    {
      v24 = *a4;
      if ( *a4 > 0 )
      {
        v45.vt = 20;
        v45.llVal = v24;
        v48 = v45;
        v25 = (*(__int64 (__fastcall **)(__int64, BSTR, VARIANTARG *))(*(_QWORD *)v50 + 360LL))(
                v50,
                g_bstrDeviceLastUpdatedTime,
                &v48);
        v59 = v25;
        if ( v25 < 0 )
        {
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
            "DeviceIdStore::AddDeviceInfoToPersistentStore",
            0x3C0u,
            v25,
            "hr = pDocumentElement->setAttribute(g_bstrDeviceLastUpdatedTime, cvAttributeValue)");
LABEL_18:
          VariantClear(&v45);
          goto LABEL_56;
        }
        VariantClear(&v45);
        VariantClear(&v45);
        v23 = v50;
      }
      v26 = *a5;
      if ( *a5 > 0 )
      {
        v45.vt = 20;
        v45.llVal = v26;
        v48 = v45;
        v27 = (*(__int64 (__fastcall **)(__int64, BSTR, VARIANTARG *))(*(_QWORD *)v23 + 360LL))(
                v23,
                g_bstrDeviceDAInvalidationTime,
                &v48);
        v59 = v27;
        if ( v27 < 0 )
        {
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
            "DeviceIdStore::AddDeviceInfoToPersistentStore",
            0x3CAu,
            v27,
            "hr = pDocumentElement->setAttribute(g_bstrDeviceDAInvalidationTime, cvAttributeValue)");
          goto LABEL_18;
        }
        VariantClear(&v45);
        VariantClear(&v45);
      }
      v28 = DeviceIdStore::AddMembernameToDOM(a2, &v47, &v53);
      v59 = v28;
      if ( v28 < 0 )
      {
        v29 = "hr = DeviceIdStore::AddMembernameToDOM(wszUserName, pDOM, pNodeMembername)";
        v30 = 975;
LABEL_26:
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
          "DeviceIdStore::AddDeviceInfoToPersistentStore",
          v30,
          v28,
          v29);
        goto LABEL_56;
      }
      SanitizeAndEscapeXML(a2, &v51);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeUpper(&v51);
      if ( v17 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v55,
          L"//%s[@%s='%s']/%s",
          g_bstrDeviceUser,
          g_bstrDeviceUsername,
          v51,
          g_bstrDevicePwd);
        v31 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v21 + 296LL);
        v32 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, v55);
        v33 = v31(v21, *(_QWORD *)v32, &v46);
        v59 = v33;
        SysFreeString(*(BSTR *)&bstrString.cbData);
        if ( v33 < 0 )
        {
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
            "DeviceIdStore::AddDeviceInfoToPersistentStore",
            0x3DFu,
            v33,
            "hr = pDOM->selectSingleNode(CComBSTR(wstrXPath), &pPasswordNode)");
          goto LABEL_56;
        }
        if ( v59 )
        {
          v43 = 0;
          *(_QWORD *)&bstrString.cbData = 0;
          v59 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v21 + 376LL))(
                  v21,
                  g_bstrDevicePwd,
                  &v43);
          if ( v59
            || (v59 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v53 + 168LL))(v53, v43, &v46)) != 0 )
          {
            ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&bstrString);
            ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v43);
            goto LABEL_56;
          }
          ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&bstrString);
          ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v43);
        }
        ATL::CComQIPtr<IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>::operator=(&v52, v46);
        VariantClear(&pvarg);
        pvarg.vt = 8;
        pvarg.llVal = (LONGLONG)ATL::CComBSTR::Copy((ATL::CComBSTR *)&g_bstrDevicePwdVersionValue);
        if ( !pvarg.llVal && g_bstrDevicePwdVersionValue )
        {
          pvarg.vt = 10;
          pvarg.lVal = -2147024882;
          ATL::AtlThrowImpl(-2147024882);
        }
        if ( !v52 )
        {
          v59 = -2147024882;
          goto LABEL_56;
        }
        v48 = pvarg;
        v59 = (*(__int64 (__fastcall **)(__int64, BSTR, VARIANTARG *))(*(_QWORD *)v52 + 360LL))(
                v52,
                g_bstrDevicePwdVersion,
                &v48);
        if ( v59 )
          goto LABEL_56;
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v43);
        *(_QWORD *)&bstrString.cbData = 0;
        bstrString.pbData = 0;
        *(_QWORD *)&v45.vt = 0;
        v48.llVal = 0;
        *(_DWORD *)&v48.vt = 0;
        *((_DWORD *)&v48.decVal + 4) = 0;
        v45.llVal = *a3;
        *(_DWORD *)&v45.vt = 2 * *(_DWORD *)(v45.llVal - 16) + 2;
        if ( !CryptProtectData((DATA_BLOB *)&v45, 0, 0, 0, 0, 1u, &bstrString) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v59 = LastError;
          if ( LastError < 0 )
          {
            v35 = "hr = HRESULT_FROM_WIN32(GetLastError())";
            v36 = 1029;
LABEL_45:
            Telemetry::IfFailExit(
              "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
              "DeviceIdStore::AddDeviceInfoToPersistentStore",
              v36,
              LastError,
              v35);
            CBytePtr::Empty((CBytePtr *)&v48);
            ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v43);
            goto LABEL_56;
          }
        }
        CBytePtr::Attach((CBytePtr *)&v48, bstrString.pbData, bstrString.cbData, 1);
        LastError = PassportEncode::Base64Encode(bstrString.pbData, bstrString.cbData);
        v59 = LastError;
        if ( LastError < 0 )
        {
          v35 = "hr = PassportEncode::Base64Encode( (void*)dbEncryptedData.pbData, dbEncryptedData.cbData, strEncryptedPwd)";
          v36 = 1037;
          goto LABEL_45;
        }
        CBytePtr::Empty((CBytePtr *)&v48);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v43);
        v37 = v46;
        v38 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v46 + 216LL);
        v39 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, v54);
        LODWORD(v38) = v38(v37, *(_QWORD *)v39);
        v59 = (int)v38;
        SysFreeString(*(BSTR *)&bstrString.cbData);
        if ( (_DWORD)v38 )
          goto LABEL_56;
      }
      v28 = DeviceIdStore::SaveDOM(a1, a2, &v47);
      v59 = v28;
      if ( v28 >= 0 )
        goto LABEL_56;
      v29 = "hr = DeviceIdStore::SaveDOM(wstrDeviceIDKey, wszUserName, pDOM)";
      v30 = 1044;
      goto LABEL_26;
    }
  }
  LODWORD(pPromptStruct) = v22;
  TracePrintW(
    2u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
    0x3B2u,
    L"::get_documentElement failed with hr = %x",
    pPromptStruct);
  if ( v59 == 1 )
    v59 = -2147418113;
LABEL_56:
  v40 = v59;
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)v57);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v58);
  VariantClear(&pvarg);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v52);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v53);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v46);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v50);
  CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v54);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v51);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v55);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v47);
  return v40;
}

```

## disassembly

```asm
0x180101fe8  push    rbp
0x180101fea  push    rbx
0x180101feb  push    rsi
0x180101fec  push    rdi
0x180101fed  push    r12
0x180101fef  push    r13
0x180101ff1  push    r14
0x180101ff3  push    r15
0x180101ff5  lea     rbp, [rsp-28h]
0x180101ffa  sub     rsp, 128h
0x180102001  mov     r14, r9
0x180102004  mov     r12, r8
0x180102007  mov     rsi, rdx
0x18010200a  mov     r15, rcx
0x18010200d  xor     r13d, r13d
0x180102010  mov     [rbp+60h+arg_8], r13d
0x180102014  mov     [rsp+160h+var_E8], r13
0x180102019  lea     rcx, [rbp+60h+var_98]
0x18010201d  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180102022  nop
0x180102023  lea     rcx, [rbp+60h+var_B8]
0x180102027  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18010202c  nop
0x18010202d  lea     rcx, [rbp+60h+var_A0]
0x180102031  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180102036  nop
0x180102037  mov     [rbp+60h+var_C0], r13
0x18010203b  mov     [rsp+160h+var_F0], r13
0x180102040  mov     [rbp+60h+var_A8], r13
0x180102044  mov     [rbp+60h+var_B0], r13
0x180102048  lea     rcx, [rbp+60h+pvarg]; pvarg
0x18010204c  call    cs:__imp_VariantInit
0x180102052  nop
0x180102053  call    ?PPTraceShouldRedact@@YA_NXZ; PPTraceShouldRedact(void)
0x180102058  test    al, al
0x18010205a  jz      short loc_180102069
0x18010205c  mov     cl, 1; this
0x18010205e  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x180102063  test    al, al
0x180102065  mov     al, cl
0x180102067  jnz     short loc_18010206C
0x180102069  mov     al, r13b
0x18010206c  mov     qword ptr [rbp+60h+var_E0+8], rsi
0x180102070  mov     [rbp+60h+var_D0], r13
0x180102074  mov     [rbp+60h+var_C8], al
0x180102077  lea     rax, ??_7PPRedactedStringW@@6B@; const PPRedactedStringW::`vftable'
0x18010207e  mov     qword ptr [rbp+60h+var_E0], rax
0x180102082  lea     rcx, [rbp+60h+var_E0]; this
0x180102086  call    ?GetString@PPRedactedStringW@@QEAAPEBGXZ; PPRedactedStringW::GetString(void)
0x18010208b  mov     [rsp+160h+var_128], rax
0x180102090  mov     [rsp+160h+pDataOut], r15
0x180102095  lea     rax, aWstrdeviceidke_3; "wstrDeviceIDKey=%ls,wszUserName=%ls"
0x18010209c  mov     qword ptr [rsp+160h+dwFlags], rax
0x1801020a1  lea     rdi, aDeviceidstoreA; "DeviceIdStore::AddDeviceInfoToPersisten"...
0x1801020a8  mov     [rsp+160h+pPromptStruct], rdi
0x1801020ad  lea     r9, [rbp+60h+arg_8]
0x1801020b1  mov     r8d, 39Fh
0x1801020b7  lea     rbx, aOnecoreuapDsEx_105; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1801020be  mov     rdx, rbx
0x1801020c1  lea     rcx, [rbp+60h+var_68]
0x1801020c5  call    ??0?$CTraceFuncW@J@@QEAA@PEBDKAEAJ0PEBGZZ; CTraceFuncW<long>::CTraceFuncW<long>(char const *,ulong,long &,char const *,ushort const *,...)
0x1801020ca  nop
0x1801020cb  lea     rcx, [rbp+60h+var_E0]; this
0x1801020cf  call    ??1PPRedactedStringW@@QEAA@XZ; PPRedactedStringW::~PPRedactedStringW(void)
0x1801020d4  mov     r8b, 1
0x1801020d7  lea     rdx, qword_1801C43A8
0x1801020de  lea     rcx, [rbp+60h+var_78]
0x1801020e2  call    ??0?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@AEAVCComAutoCriticalSectionWTry@@_N@Z; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(CComAutoCriticalSectionWTry &,bool)
0x1801020e7  nop
0x1801020e8  test    rsi, rsi
0x1801020eb  jz      loc_1801026C5
0x1801020f1  cmp     [rsi], r13w
0x1801020f5  jz      loc_1801026C5
0x1801020fb  mov     dil, [rbp+60h+arg_28]
0x180102102  test    dil, dil
0x180102105  jz      short loc_18010212A
0x180102107  mov     rax, [r12]
0x18010210b  cmp     [rax-10h], r13d
0x18010210f  jnz     short loc_18010212A
0x180102111  lea     rax, aPersistpasswor; "!persistPassword || !wstrPwd.IsEmpty()"
0x180102118  mov     r8d, 3A6h
0x18010211e  lea     rdx, aDeviceidstoreA; "DeviceIdStore::AddDeviceInfoToPersisten"...
0x180102125  jmp     loc_1801026D5
0x18010212a  lea     r9, [rsp+160h+var_E8]
0x18010212f  mov     r8b, 1
0x180102132  mov     rdx, rsi
0x180102135  mov     rcx, r15
0x180102138  call    ?LoadPersistedDOM@DeviceIdStore@@CAJPEBG0_NAEAV?$CComPtr@UIXMLDOMDocument@@@ATL@@@Z; DeviceIdStore::LoadPersistedDOM(ushort const *,ushort const *,bool,ATL::CComPtr<IXMLDOMDocument> &)
0x18010213d  mov     [rbp+60h+arg_8], eax
0x180102140  test    eax, eax
0x180102142  jns     short loc_180102165
0x180102144  lea     rcx, aHrDeviceidstor_11; "hr = DeviceIdStore::LoadPersistedDOM(ws"...
0x18010214b  mov     [rsp+160h+pPromptStruct], rcx
0x180102150  mov     r9d, eax
0x180102153  mov     r8d, 3A8h
0x180102159  lea     rdx, aDeviceidstoreA; "DeviceIdStore::AddDeviceInfoToPersisten"...
0x180102160  jmp     loc_1801026E4
0x180102165  mov     rbx, [rsp+160h+var_E8]
0x18010216a  test    rbx, rbx
0x18010216d  jnz     short loc_180102194
0x18010216f  mov     dword ptr [rsp+160h+pPromptStruct], eax
0x180102173  lea     r9, aLoadpersistedd; "::LoadPersistedDOM failed with hr = %x"
0x18010217a  mov     r8d, 3ABh; unsigned int
0x180102180  lea     rdx, aOnecoreuapDsEx_105; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180102187  lea     ecx, [rbx+2]; unsigned __int8
0x18010218a  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18010218f  jmp     loc_1801026EC
0x180102194  mov     rax, [rbx]
0x180102197  lea     rdx, [rbp+60h+var_C0]
0x18010219b  mov     rcx, rbx
0x18010219e  mov     rax, [rax+168h]
0x1801021a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801021aa  mov     [rbp+60h+arg_8], eax
0x1801021ad  test    eax, eax
0x1801021af  jnz     loc_180102694
0x1801021b5  mov     rcx, [rbp+60h+var_C0]
0x1801021b9  test    rcx, rcx
0x1801021bc  jz      loc_180102694
0x1801021c2  mov     rax, [r14]
0x1801021c5  mov     r14d, 14h
0x1801021cb  test    rax, rax
0x1801021ce  jle     loc_180102268
0x1801021d4  mov     word ptr [rsp+160h+var_108], r14w
0x1801021da  mov     qword ptr [rsp+160h+var_108+8], rax
0x1801021df  movups  xmm0, xmmword ptr [rsp+160h+var_108]
0x1801021e4  movaps  [rbp+60h+var_E0], xmm0
0x1801021e8  movsd   xmm1, qword ptr [rsp+160h+var_108+10h]
0x1801021ee  movsd   [rbp+60h+var_D0], xmm1
0x1801021f3  mov     rax, [rcx]
0x1801021f6  lea     r8, [rbp+60h+var_E0]
0x1801021fa  mov     rdx, cs:?g_bstrDeviceLastUpdatedTime@@3VCComBSTR@ATL@@A; ATL::CComBSTR g_bstrDeviceLastUpdatedTime
0x180102201  mov     rax, [rax+168h]
0x180102208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010220d  mov     [rbp+60h+arg_8], eax
0x180102210  test    eax, eax
0x180102212  jns     short loc_18010224D
0x180102214  lea     rcx, aHrPdocumentele; "hr = pDocumentElement->setAttribute(g_b"...
0x18010221b  mov     [rsp+160h+pPromptStruct], rcx; char *
0x180102220  mov     r9d, eax; int
0x180102223  mov     r8d, 3C0h; unsigned int
0x180102229  lea     rdx, aDeviceidstoreA; "DeviceIdStore::AddDeviceInfoToPersisten"...
0x180102230  lea     rcx, aOnecoreuapDsEx_105; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180102237  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18010223c  nop
0x18010223d  lea     rcx, [rsp+160h+var_108]; pvarg
0x180102242  call    cs:__imp_VariantClear
0x180102248  jmp     loc_1801026EC
0x18010224d  lea     rcx, [rsp+160h+var_108]; pvarg
0x180102252  call    cs:__imp_VariantClear
0x180102258  nop
0x180102259  lea     rcx, [rsp+160h+var_108]; pvarg
0x18010225e  call    cs:__imp_VariantClear
0x180102264  mov     rcx, [rbp+60h+var_C0]
0x180102268  mov     rax, [rbp+60h+arg_20]
0x18010226f  mov     rdx, [rax]
0x180102272  test    rdx, rdx
0x180102275  jle     loc_180102300
0x18010227b  mov     word ptr [rsp+160h+var_108], r14w
0x180102281  mov     qword ptr [rsp+160h+var_108+8], rdx
0x180102286  movups  xmm0, xmmword ptr [rsp+160h+var_108]
0x18010228b  movaps  [rbp+60h+var_E0], xmm0
0x18010228f  movsd   xmm1, qword ptr [rsp+160h+var_108+10h]
0x180102295  movsd   [rbp+60h+var_D0], xmm1
0x18010229a  mov     rax, [rcx]
0x18010229d  lea     r8, [rbp+60h+var_E0]
0x1801022a1  mov     rdx, cs:?g_bstrDeviceDAInvalidationTime@@3VCComBSTR@ATL@@A; ATL::CComBSTR g_bstrDeviceDAInvalidationTime
0x1801022a8  mov     rax, [rax+168h]
0x1801022af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801022b4  mov     [rbp+60h+arg_8], eax
0x1801022b7  test    eax, eax
0x1801022b9  jns     short loc_1801022E9
0x1801022bb  lea     rcx, aHrPdocumentele_0; "hr = pDocumentElement->setAttribute(g_b"...
0x1801022c2  mov     [rsp+160h+pPromptStruct], rcx; char *
0x1801022c7  mov     r9d, eax; int
0x1801022ca  mov     r8d, 3CAh; unsigned int
0x1801022d0  lea     rdx, aDeviceidstoreA; "DeviceIdStore::AddDeviceInfoToPersisten"...
0x1801022d7  lea     rcx, aOnecoreuapDsEx_105; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1801022de  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1801022e3  nop
0x1801022e4  jmp     loc_18010223D
0x1801022e9  lea     rcx, [rsp+160h+var_108]; pvarg
0x1801022ee  call    cs:__imp_VariantClear
0x1801022f4  nop
0x1801022f5  lea     rcx, [rsp+160h+var_108]; pvarg
0x1801022fa  call    cs:__imp_VariantClear
0x180102300  lea     r8, [rbp+60h+var_A8]
0x180102304  lea     rdx, [rsp+160h+var_E8]
0x180102309  mov     rcx, rsi
0x18010230c  call    ?AddMembernameToDOM@DeviceIdStore@@CAJPEBGAEAV?$CComPtr@UIXMLDOMDocument@@@ATL@@AEAV?$CComPtr@UIXMLDOMNode@@@3@@Z; DeviceIdStore::AddMembernameToDOM(ushort const *,ATL::CComPtr<IXMLDOMDocument> &,ATL::CComPtr<IXMLDOMNode> &)
0x180102311  mov     [rbp+60h+arg_8], eax
0x180102314  test    eax, eax
0x180102316  jns     short loc_180102340
0x180102318  lea     rcx, aHrDeviceidstor_8; "hr = DeviceIdStore::AddMembernameToDOM("...
0x18010231f  mov     r8d, 3CFh
0x180102325  mov     r9d, eax
0x180102328  mov     [rsp+160h+pPromptStruct], rcx
0x18010232d  lea     rdx, aDeviceidstoreA; "DeviceIdStore::AddDeviceInfoToPersisten"...
0x180102334  lea     rcx, aOnecoreuapDsEx_105; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18010233b  jmp     loc_1801026E7
0x180102340  lea     rdx, [rbp+60h+var_B8]
0x180102344  mov     rcx, rsi
0x180102347  call    ?SanitizeAndEscapeXML@@YAXPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; SanitizeAndEscapeXML(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18010234c  lea     rcx, [rbp+60h+var_B8]
0x180102350  call    ?MakeUpper@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::MakeUpper(void)
0x180102355  test    dil, dil
0x180102358  jz      loc_18010266B
0x18010235e  mov     rax, cs:?g_bstrDevicePwd@@3VCComBSTR@ATL@@A; ATL::CComBSTR g_bstrDevicePwd
0x180102365  mov     qword ptr [rsp+160h+dwFlags], rax
0x18010236a  mov     rax, [rbp+60h+var_B8]
0x18010236e  mov     [rsp+160h+pPromptStruct], rax
0x180102373  mov     r9, cs:?g_bstrDeviceUsername@@3VCComBSTR@ATL@@A; ATL::CComBSTR g_bstrDeviceUsername
0x18010237a  mov     r8, cs:?g_bstrDeviceUser@@3VCComBSTR@ATL@@A; ATL::CComBSTR g_bstrDeviceUser
0x180102381  lea     rdx, aSSSS; "//%s[@%s='%s']/%s"
0x180102388  lea     rcx, [rbp+60h+var_98]
0x18010238c  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180102391  mov     rax, [rbx]
0x180102394  mov     rdi, [rax+128h]
0x18010239b  mov     rdx, [rbp+60h+var_98]; unsigned __int16 *
0x18010239f  lea     rcx, [rsp+160h+bstrString]; this
0x1801023a4  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1801023a9  nop
0x1801023aa  lea     r8, [rsp+160h+var_F0]
0x1801023af  mov     rdx, [rax]
0x1801023b2  mov     rcx, rbx
0x1801023b5  mov     rax, rdi
0x1801023b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801023bd  mov     edi, eax
0x1801023bf  mov     [rbp+60h+arg_8], eax
0x1801023c2  mov     rcx, [rsp+160h+bstrString]; bstrString
0x1801023c7  call    cs:__imp_SysFreeString
0x1801023cd  test    edi, edi
0x1801023cf  jns     short loc_1801023EB
0x1801023d1  lea     rax, aHrPdomSelectsi_1; "hr = pDOM->selectSingleNode(CComBSTR(ws"...
0x1801023d8  mov     [rsp+160h+pPromptStruct], rax
0x1801023dd  mov     r9d, edi
0x1801023e0  mov     r8d, 3DFh
0x1801023e6  jmp     loc_18010232D
0x1801023eb  cmp     [rbp+60h+arg_8], r13d
0x1801023ef  jz      short loc_18010245D
0x1801023f1  mov     [rsp+160h+var_120], r13
0x1801023f6  mov     [rsp+160h+bstrString], r13
0x1801023fb  mov     rax, [rbx]
0x1801023fe  lea     r8, [rsp+160h+var_120]
0x180102403  mov     rdx, cs:?g_bstrDevicePwd@@3VCComBSTR@ATL@@A; ATL::CComBSTR g_bstrDevicePwd
0x18010240a  mov     rcx, rbx
0x18010240d  mov     rax, [rax+178h]
0x180102414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102419  mov     [rbp+60h+arg_8], eax
0x18010241c  test    eax, eax
0x18010241e  jnz     loc_1801024BE
0x180102424  mov     rcx, [rbp+60h+var_A8]
0x180102428  mov     rax, [rcx]
0x18010242b  lea     r8, [rsp+160h+var_F0]
0x180102430  mov     rdx, [rsp+160h+var_120]
0x180102435  mov     rax, [rax+0A8h]
0x18010243c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102441  mov     [rbp+60h+arg_8], eax
0x180102444  test    eax, eax
0x180102446  jnz     short loc_1801024BE
0x180102448  lea     rcx, [rsp+160h+bstrString]
0x18010244d  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180102452  nop
0x180102453  lea     rcx, [rsp+160h+var_120]
0x180102458  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18010245d  mov     rdx, [rsp+160h+var_F0]
0x180102462  lea     rcx, [rbp+60h+var_B0]
0x180102466  call    ??4?$CComQIPtr@UIXMLDOMElement@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@ATL@@QEAAPEAUIXMLDOMElement@@PEAUIUnknown@@@Z; ATL::CComQIPtr<IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>::operator=(IUnknown *)
0x18010246b  lea     rcx, [rbp+60h+pvarg]; pvarg
0x18010246f  call    cs:__imp_VariantClear
0x180102475  mov     eax, 8
0x18010247a  mov     word ptr [rbp+60h+pvarg], ax
0x18010247e  lea     rcx, ?g_bstrDevicePwdVersionValue@@3VCComBSTR@ATL@@A; this
0x180102485  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x18010248a  mov     dword ptr [rbp+60h+pvarg+8], eax
0x18010248d  mov     rcx, rax
0x180102490  sar     rcx, 20h
0x180102494  mov     dword ptr [rbp+60h+pvarg+0Ch], ecx
0x180102497  test    rax, rax
0x18010249a  jnz     short loc_1801024A9
0x18010249c  cmp     cs:?g_bstrDevicePwdVersionValue@@3VCComBSTR@ATL@@A, r13; ATL::CComBSTR g_bstrDevicePwdVersionValue
0x1801024a3  jnz     loc_180102775
0x1801024a9  mov     rcx, [rbp+60h+var_B0]
0x1801024ad  test    rcx, rcx
0x1801024b0  jnz     short loc_1801024D8
0x1801024b2  mov     [rbp+60h+arg_8], 8007000Eh
0x1801024b9  jmp     loc_1801026EC
0x1801024be  lea     rcx, [rsp+160h+bstrString]
0x1801024c3  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1801024c8  nop
0x1801024c9  lea     rcx, [rsp+160h+var_120]
0x1801024ce  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1801024d3  jmp     loc_1801026EC
0x1801024d8  movups  xmm0, xmmword ptr [rbp+60h+pvarg]
0x1801024dc  movaps  [rbp+60h+var_E0], xmm0
0x1801024e0  movsd   xmm1, qword ptr [rbp+60h+pvarg+10h]
0x1801024e5  movsd   [rbp+60h+var_D0], xmm1
0x1801024ea  mov     rax, [rcx]
0x1801024ed  lea     r8, [rbp+60h+var_E0]
0x1801024f1  mov     rdx, cs:?g_bstrDevicePwdVersion@@3VCComBSTR@ATL@@A; ATL::CComBSTR g_bstrDevicePwdVersion
0x1801024f8  mov     rax, [rax+168h]
  ... truncated ...
```
