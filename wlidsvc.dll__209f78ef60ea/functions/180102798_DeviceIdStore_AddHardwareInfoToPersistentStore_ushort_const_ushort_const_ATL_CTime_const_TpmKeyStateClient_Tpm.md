# DeviceIdStore::AddHardwareInfoToPersistentStore(ushort const *,ushort const *,ATL::CTime const &,TpmKeyStateClient,TpmKeyStateServer,ulong,long,ulong)

- ea: `0x180102798`
- end: `0x180102f09`
- name: `?AddHardwareInfoToPersistentStore@DeviceIdStore@@SAJPEBG0AEBVCTime@ATL@@W4TpmKeyStateClient@@W4TpmKeyStateServer@@KJK@Z`
- size: `1905`
- prototype: `static int __high(const unsigned __int16 *, const unsigned __int16 *, const struct ATL::CTime *, enum TpmKeyStateClient, enum TpmKeyStateServer, unsigned int, int, unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180100200`

## callees

- `0x18000c050`
- `0x18000ed04`
- `0x180013fb4`
- `0x1800151c4`
- `0x18001925c`
- `0x180019690`
- `0x18001a530`
- `0x18001a9c0`
- `0x180039d60`
- `0x180039ee8`
- `0x18003c814`
- `0x1800406a8`
- `0x18008916c`
- `0x180102798`
- `0x1801066ac`
- `0x180107238`
- `0x180128010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1801028db`
- `OLEAUT32!__imp_SysFreeString` at `0x18010297e`
- `OLEAUT32!__imp_SysFreeString` at `0x1801028db`
- `OLEAUT32!__imp_SysFreeString` at `0x18010297e`
- `OLEAUT32!__imp_VariantClear` at `0x180102a52`
- `OLEAUT32!__imp_VariantClear` at `0x180102ab0`
- `OLEAUT32!__imp_VariantClear` at `0x180102ac7`
- `OLEAUT32!__imp_VariantClear` at `0x180102b4d`
- `OLEAUT32!__imp_VariantClear` at `0x180102b64`
- `OLEAUT32!__imp_VariantClear` at `0x180102be6`
- `OLEAUT32!__imp_VariantClear` at `0x180102bfd`
- `OLEAUT32!__imp_VariantClear` at `0x180102cae`
- `OLEAUT32!__imp_VariantClear` at `0x180102cba`
- `OLEAUT32!__imp_VariantClear` at `0x180102d6d`
- `OLEAUT32!__imp_VariantClear` at `0x180102d79`
- `OLEAUT32!__imp_VariantClear` at `0x180102e33`
- `OLEAUT32!__imp_VariantClear` at `0x180102e3f`
- `OLEAUT32!__imp_VariantClear` at `0x180102a52`
- `OLEAUT32!__imp_VariantClear` at `0x180102ab0`
- `OLEAUT32!__imp_VariantClear` at `0x180102ac7`
- `OLEAUT32!__imp_VariantClear` at `0x180102b4d`
- `OLEAUT32!__imp_VariantClear` at `0x180102b64`
- `OLEAUT32!__imp_VariantClear` at `0x180102be6`
- `OLEAUT32!__imp_VariantClear` at `0x180102bfd`
- `OLEAUT32!__imp_VariantClear` at `0x180102cae`
- `OLEAUT32!__imp_VariantClear` at `0x180102cba`
- `OLEAUT32!__imp_VariantClear` at `0x180102d6d`
- `OLEAUT32!__imp_VariantClear` at `0x180102d79`
- `OLEAUT32!__imp_VariantClear` at `0x180102e33`
- `OLEAUT32!__imp_VariantClear` at `0x180102e3f`

## string_xrefs

- `0x180102816`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x180102901`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x180102c3e`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x180102c9b`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x180102cf6`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x180102d5a`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x180102dc3`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x180102e20`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x1801028e5`: `hr = pDOM->selectSingleNode(CComBSTR(wstrXPath), &pNodeMembername)`
- `0x180102d32`: `LicenseInstallError`
- `0x18010298a`: `hr = pNodeMembername->selectSingleNode(CComBSTR(wstrXPath), &pNodeHwdInfo)`
- `0x180102d4d`: `SetAttribute LicenseInstallError failed with 0x%x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall DeviceIdStore::AddHardwareInfoToPersistentStore(
        __int64 a1,
        _WORD *a2,
        __time64_t *a3,
        LONG a4,
        LONG a5,
        LONG a6,
        LONG a7,
        LONG a8)
{
  _QWORD *v12; // rax
  __int64 v13; // r8
  int v14; // eax
  __int64 v15; // rsi
  __int64 (__fastcall *v16)(__int64, _QWORD, __int64 *); // rbx
  ATL::CComBSTR *v17; // rax
  int v18; // ebx
  const char *v19; // rax
  unsigned int v20; // r8d
  int v21; // r9d
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, _QWORD, __int64 *); // rbx
  ATL::CComBSTR *v24; // rax
  LONG v25; // ebx
  int v26; // eax
  int v27; // eax
  LONG v28; // ebx
  int v29; // eax
  int v30; // eax
  unsigned int v31; // ebx
  char *v33; // [rsp+20h] [rbp-C1h]
  __int64 v34; // [rsp+40h] [rbp-A1h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-99h] BYREF
  __int64 v36; // [rsp+60h] [rbp-81h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-79h] BYREF
  unsigned __int16 *v38; // [rsp+70h] [rbp-71h] BYREF
  __int64 v39; // [rsp+78h] [rbp-69h] BYREF
  VARIANTARG v40; // [rsp+80h] [rbp-61h] BYREF
  __int64 v41; // [rsp+A0h] [rbp-41h] BYREF
  _BYTE v42[16]; // [rsp+A8h] [rbp-39h] BYREF
  const char *v43[13]; // [rsp+B8h] [rbp-29h] BYREF
  int v44; // [rsp+138h] [rbp+57h] BYREF

  v44 = 0;
  v41 = 0;
  v36 = 0;
  v39 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v38);
  v12 = (_QWORD *)ATL::CTime::FormatGmt(a3);
  CTraceFuncW<long>::CTraceFuncW<long>(
    v43,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
    1066,
    (const char *)&v44,
    "DeviceIdStore::AddHardwareInfoToPersistentStore",
    L"ctHWBoundTime=%ls",
    *v12);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&bstrString);
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(
    (__int64)v42,
    (struct _RTL_CRITICAL_SECTION *)qword_1801C43A8,
    1);
  if ( a2 && *a2 )
  {
    LOBYTE(v13) = 1;
    v14 = DeviceIdStore::LoadPersistedDOM(a1, a2, v13, &v41);
    v44 = v14;
    if ( v14 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
        "DeviceIdStore::AddHardwareInfoToPersistentStore",
        0x430u,
        v14,
        "hr = DeviceIdStore::LoadPersistedDOM(wstrDeviceIDKey, wstrDeviceIDName, true, pDOM)");
      goto LABEL_53;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &v38,
      L"//%s",
      g_bstrDeviceUser);
    v15 = v41;
    v16 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v41 + 296LL);
    v17 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, v38);
    v18 = v16(v15, *(_QWORD *)v17, &v39);
    v44 = v18;
    SysFreeString(bstrString);
    if ( v18 < 0 )
    {
      v19 = "hr = pDOM->selectSingleNode(CComBSTR(wstrXPath), &pNodeMembername)";
      v20 = 1076;
LABEL_7:
      v21 = v18;
LABEL_8:
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
        "DeviceIdStore::AddHardwareInfoToPersistentStore",
        v20,
        v21,
        v19);
      goto LABEL_53;
    }
    if ( !v39 )
    {
      v44 = -2147418113;
      v19 = "pNodeMembername != nullptr";
      v21 = -2147418113;
      v20 = 1079;
      goto LABEL_8;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &v38,
      L"//%s",
      g_bstrDeviceHardwareInfo);
    v22 = v39;
    v23 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v39 + 296LL);
    v24 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, v38);
    v18 = v23(v22, *(_QWORD *)v24, &v36);
    v44 = v18;
    SysFreeString(bstrString);
    if ( v18 < 0 )
    {
      v19 = "hr = pNodeMembername->selectSingleNode(CComBSTR(wstrXPath), &pNodeHwdInfo)";
      v20 = 1083;
      goto LABEL_7;
    }
    if ( v44 )
    {
      v34 = 0;
      bstrString = 0;
      v44 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v15 + 376LL))(
              v15,
              g_bstrDeviceHardwareInfo,
              &v34);
      if ( v44
        || (v44 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v39 + 168LL))(v39, v34, &v36)) != 0 )
      {
        ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&bstrString);
        ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v34);
        goto LABEL_53;
      }
      ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&bstrString);
      ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v34);
    }
    pvarg.vt = 20;
    pvarg.llVal = *a3;
    v34 = 0;
    ATL::CComQIPtr<IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>::operator=(&v34, v36);
    if ( !v34 )
    {
      v44 = -2147024882;
LABEL_19:
      ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v34);
      VariantClear(&pvarg);
      goto LABEL_53;
    }
    v40 = pvarg;
    v44 = (*(__int64 (__fastcall **)(__int64, BSTR, VARIANTARG *))(*(_QWORD *)v34 + 360LL))(
            v34,
            g_bstrDeviceHardwareBoundTime,
            &v40);
    if ( v44 )
      goto LABEL_19;
    VariantClear(&pvarg);
    ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v34);
    VariantClear(&pvarg);
    pvarg.vt = 19;
    pvarg.lVal = a4;
    v34 = 0;
    ATL::CComQIPtr<IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>::operator=(&v34, v36);
    if ( !v34 )
    {
      v44 = -2147024882;
      goto LABEL_19;
    }
    v40 = pvarg;
    v44 = (*(__int64 (__fastcall **)(__int64, BSTR, VARIANTARG *))(*(_QWORD *)v34 + 360LL))(
            v34,
            g_bstrDeviceTpmKeyStateClient,
            &v40);
    if ( v44 )
      goto LABEL_19;
    VariantClear(&pvarg);
    ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v34);
    VariantClear(&pvarg);
    pvarg.vt = 19;
    pvarg.lVal = a5;
    v34 = 0;
    ATL::CComQIPtr<IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>::operator=(&v34, v36);
    if ( !v34 )
    {
      v44 = -2147024882;
      goto LABEL_19;
    }
    v40 = pvarg;
    v44 = (*(__int64 (__fastcall **)(__int64, BSTR, VARIANTARG *))(*(_QWORD *)v34 + 360LL))(
            v34,
            g_bstrDeviceTpmKeyStateServer,
            &v40);
    if ( v44 )
      goto LABEL_19;
    VariantClear(&pvarg);
    ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v34);
    VariantClear(&pvarg);
    v25 = a6;
    if ( a6 )
    {
      v34 = 0;
      ATL::CComQIPtr<IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>::operator=(&v34, v36);
      if ( v34 )
      {
        pvarg.vt = 19;
        pvarg.lVal = v25;
        v40 = pvarg;
        v26 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v34 + 360LL))(
                v34,
                L"LicenseKeySequence",
                &v40);
        if ( v26 < 0 )
        {
          LODWORD(v33) = v26;
          TracePrintW(
            2u,
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
            0x47Fu,
            L"SetAttribute LicenseKeySequence failed with 0x%x.",
            v33);
        }
        VariantClear(&pvarg);
        VariantClear(&pvarg);
      }
      else
      {
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
          0x477u,
          L"pElement is null.");
      }
      ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v34);
    }
    v34 = 0;
    ATL::CComQIPtr<IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>::operator=(&v34, v36);
    if ( v34 )
    {
      pvarg.vt = 3;
      pvarg.lVal = a7;
      v40 = pvarg;
      v27 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v34 + 360LL))(
              v34,
              L"LicenseInstallError",
              &v40);
      if ( v27 < 0 )
      {
        LODWORD(v33) = v27;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
          0x495u,
          L"SetAttribute LicenseInstallError failed with 0x%x.",
          v33);
      }
      VariantClear(&pvarg);
      VariantClear(&pvarg);
    }
    else
    {
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
        0x48Du,
        L"hardwareInfoElement is null.");
    }
    ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v34);
    v28 = a8;
    if ( a8 )
    {
      v34 = 0;
      ATL::CComQIPtr<IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>::operator=(&v34, v36);
      if ( v34 )
      {
        pvarg.vt = 19;
        pvarg.lVal = v28;
        v40 = pvarg;
        v29 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v34 + 360LL))(
                v34,
                L"LicenseKeyVersion",
                &v40);
        if ( v29 < 0 )
        {
          LODWORD(v33) = v29;
          TracePrintW(
            2u,
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
            0x4ABu,
            L"SetAttribute LicenseKeyVersionClient failed with 0x%x.",
            v33);
        }
        VariantClear(&pvarg);
        VariantClear(&pvarg);
      }
      else
      {
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
          0x4A3u,
          L"licenseKeyVersionClientElement is null.");
      }
      ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v34);
    }
    v30 = DeviceIdStore::SaveDOM(a1, a2, &v41);
    v44 = v30;
    if ( v30 < 0 )
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
        "DeviceIdStore::AddHardwareInfoToPersistentStore",
        0x4B2u,
        v30,
        "hr = DeviceIdStore::SaveDOM(wstrDeviceIDKey, wstrDeviceIDName, pDOM)");
  }
  else
  {
    v44 = -2147024809;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidstore.cpp",
      "DeviceIdStore::AddHardwareInfoToPersistentStore",
      0x42Eu,
      -2147024809,
      "wstrDeviceIDName != nullptr && wstrDeviceIDName[0] != L'\\0'");
  }
LABEL_53:
  if ( v44 == 1 )
    v44 = -2147418113;
  v31 = v44;
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)v42);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v43);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v38);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v39);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v36);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v41);
  return v31;
}

```

## disassembly

```asm
0x180102798  push    rbp
0x18010279a  push    rbx
0x18010279b  push    rsi
0x18010279c  push    rdi
0x18010279d  push    r12
0x18010279f  push    r13
0x1801027a1  push    r14
0x1801027a3  push    r15
0x1801027a5  lea     rbp, [rsp-7]
0x1801027aa  sub     rsp, 0E8h
0x1801027b1  mov     r12d, r9d
0x1801027b4  mov     r15, r8
0x1801027b7  mov     r14, rdx
0x1801027ba  mov     r13, rcx
0x1801027bd  xor     edi, edi
0x1801027bf  mov     [rbp+3Fh+arg_8], edi
0x1801027c2  mov     [rbp+3Fh+var_80], rdi
0x1801027c6  mov     [rsp+120h+var_C0], rdi
0x1801027cb  mov     [rbp+3Fh+var_A8], rdi
0x1801027cf  lea     rcx, [rbp+3Fh+var_B0]
0x1801027d3  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1801027d8  nop
0x1801027d9  lea     r8, aYMDtHMSz; "%Y-%m-%dT%H:%M:%SZ"
0x1801027e0  lea     rdx, [rbp+3Fh+bstrString]
0x1801027e4  mov     rcx, r15; Time
0x1801027e7  call    ?FormatGmt@CTime@ATL@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@PEBG@Z; ATL::CTime::FormatGmt(ushort const *)
0x1801027ec  mov     rcx, [rax]
0x1801027ef  mov     [rsp+120h+var_F0], rcx
0x1801027f4  lea     rax, aCthwboundtimeL; "ctHWBoundTime=%ls"
0x1801027fb  mov     [rsp+120h+var_F8], rax
0x180102800  lea     rsi, aDeviceidstoreA_3; "DeviceIdStore::AddHardwareInfoToPersist"...
0x180102807  mov     [rsp+120h+var_100], rsi
0x18010280c  lea     r9, [rbp+3Fh+arg_8]
0x180102810  mov     r8d, 42Ah
0x180102816  lea     rbx, aOnecoreuapDsEx_105; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18010281d  mov     rdx, rbx
0x180102820  lea     rcx, [rbp+3Fh+var_68]
0x180102824  call    ??0?$CTraceFuncW@J@@QEAA@PEBDKAEAJ0PEBGZZ; CTraceFuncW<long>::CTraceFuncW<long>(char const *,ulong,long &,char const *,ushort const *,...)
0x180102829  nop
0x18010282a  lea     rcx, [rbp+3Fh+bstrString]
0x18010282e  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180102833  mov     r8b, 1
0x180102836  lea     rdx, qword_1801C43A8
0x18010283d  lea     rcx, [rbp+3Fh+var_78]
0x180102841  call    ??0?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@AEAVCComAutoCriticalSectionWTry@@_N@Z; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(CComAutoCriticalSectionWTry &,bool)
0x180102846  nop
0x180102847  test    r14, r14
0x18010284a  jz      loc_180102E80
0x180102850  cmp     [r14], di
0x180102854  jz      loc_180102E80
0x18010285a  lea     r9, [rbp+3Fh+var_80]
0x18010285e  mov     r8b, 1
0x180102861  mov     rdx, r14
0x180102864  mov     rcx, r13
0x180102867  call    ?LoadPersistedDOM@DeviceIdStore@@CAJPEBG0_NAEAV?$CComPtr@UIXMLDOMDocument@@@ATL@@@Z; DeviceIdStore::LoadPersistedDOM(ushort const *,ushort const *,bool,ATL::CComPtr<IXMLDOMDocument> &)
0x18010286c  mov     [rbp+3Fh+arg_8], eax
0x18010286f  test    eax, eax
0x180102871  jns     short loc_18010288D
0x180102873  lea     r8, aHrDeviceidstor_12; "hr = DeviceIdStore::LoadPersistedDOM(ws"...
0x18010287a  mov     [rsp+120h+var_100], r8
0x18010287f  mov     r9d, eax
0x180102882  mov     r8d, 430h
0x180102888  jmp     loc_180102E9C
0x18010288d  mov     r8, cs:?g_bstrDeviceUser@@3VCComBSTR@ATL@@A; ATL::CComBSTR g_bstrDeviceUser
0x180102894  lea     rdx, aS_2; "//%s"
0x18010289b  lea     rcx, [rbp+3Fh+var_B0]
0x18010289f  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1801028a4  mov     rsi, [rbp+3Fh+var_80]
0x1801028a8  mov     rax, [rsi]
0x1801028ab  mov     rbx, [rax+128h]
0x1801028b2  mov     rdx, [rbp+3Fh+var_B0]; unsigned __int16 *
0x1801028b6  lea     rcx, [rbp+3Fh+bstrString]; this
0x1801028ba  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1801028bf  nop
0x1801028c0  lea     r8, [rbp+3Fh+var_A8]
0x1801028c4  mov     rdx, [rax]
0x1801028c7  mov     rcx, rsi
0x1801028ca  mov     rax, rbx
0x1801028cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801028d2  mov     ebx, eax
0x1801028d4  mov     [rbp+3Fh+arg_8], eax
0x1801028d7  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x1801028db  call    cs:__imp_SysFreeString
0x1801028e1  test    ebx, ebx
0x1801028e3  jns     short loc_18010290D
0x1801028e5  lea     rax, aHrPdomSelectsi; "hr = pDOM->selectSingleNode(CComBSTR(ws"...
0x1801028ec  mov     r8d, 434h
0x1801028f2  mov     r9d, ebx
0x1801028f5  mov     [rsp+120h+var_100], rax
0x1801028fa  lea     rdx, aDeviceidstoreA_3; "DeviceIdStore::AddHardwareInfoToPersist"...
0x180102901  lea     rcx, aOnecoreuapDsEx_105; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180102908  jmp     loc_180102EA2
0x18010290d  cmp     [rbp+3Fh+var_A8], rdi
0x180102911  jnz     short loc_18010292F
0x180102913  mov     [rbp+3Fh+arg_8], 8000FFFFh
0x18010291a  lea     rax, aPnodemembernam; "pNodeMembername != nullptr"
0x180102921  mov     r9d, 8000FFFFh
0x180102927  mov     r8d, 437h
0x18010292d  jmp     short loc_1801028F5
0x18010292f  mov     r8, cs:?g_bstrDeviceHardwareInfo@@3VCComBSTR@ATL@@A; ATL::CComBSTR g_bstrDeviceHardwareInfo
0x180102936  lea     rdx, aS_2; "//%s"
0x18010293d  lea     rcx, [rbp+3Fh+var_B0]
0x180102941  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180102946  mov     rdi, [rbp+3Fh+var_A8]
0x18010294a  mov     rax, [rdi]
0x18010294d  mov     rbx, [rax+128h]
0x180102954  mov     rdx, [rbp+3Fh+var_B0]; unsigned __int16 *
0x180102958  lea     rcx, [rbp+3Fh+bstrString]; this
0x18010295c  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180102961  nop
0x180102962  lea     r8, [rsp+120h+var_C0]
0x180102967  mov     rdx, [rax]
0x18010296a  mov     rcx, rdi
0x18010296d  mov     rax, rbx
0x180102970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102975  mov     ebx, eax
0x180102977  mov     [rbp+3Fh+arg_8], eax
0x18010297a  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x18010297e  call    cs:__imp_SysFreeString
0x180102984  xor     edi, edi
0x180102986  test    ebx, ebx
0x180102988  jns     short loc_18010299C
0x18010298a  lea     rax, aHrPnodemembern; "hr = pNodeMembername->selectSingleNode("...
0x180102991  mov     r8d, 43Bh
0x180102997  jmp     loc_1801028F2
0x18010299c  cmp     [rbp+3Fh+arg_8], edi
0x18010299f  jz      short loc_180102A0B
0x1801029a1  mov     [rsp+120h+var_E0], rdi
0x1801029a6  mov     [rbp+3Fh+bstrString], rdi
0x1801029aa  mov     rax, [rsi]
0x1801029ad  lea     r8, [rsp+120h+var_E0]
0x1801029b2  mov     rdx, cs:?g_bstrDeviceHardwareInfo@@3VCComBSTR@ATL@@A; ATL::CComBSTR g_bstrDeviceHardwareInfo
0x1801029b9  mov     rcx, rsi
0x1801029bc  mov     rax, [rax+178h]
0x1801029c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801029c8  mov     [rbp+3Fh+arg_8], eax
0x1801029cb  test    eax, eax
0x1801029cd  jnz     loc_180102A5D
0x1801029d3  mov     rcx, [rbp+3Fh+var_A8]
0x1801029d7  mov     rax, [rcx]
0x1801029da  lea     r8, [rsp+120h+var_C0]
0x1801029df  mov     rdx, [rsp+120h+var_E0]
0x1801029e4  mov     rax, [rax+0A8h]
0x1801029eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801029f0  mov     [rbp+3Fh+arg_8], eax
0x1801029f3  test    eax, eax
0x1801029f5  jnz     short loc_180102A5D
0x1801029f7  lea     rcx, [rbp+3Fh+bstrString]
0x1801029fb  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180102a00  nop
0x180102a01  lea     rcx, [rsp+120h+var_E0]
0x180102a06  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180102a0b  mov     eax, 14h
0x180102a10  mov     word ptr [rsp+120h+pvarg], ax
0x180102a15  mov     rax, [r15]
0x180102a18  mov     qword ptr [rsp+120h+pvarg+8], rax
0x180102a1d  mov     [rsp+120h+var_E0], rdi
0x180102a22  mov     rdx, [rsp+120h+var_C0]
0x180102a27  lea     rcx, [rsp+120h+var_E0]
0x180102a2c  call    ??4?$CComQIPtr@UIXMLDOMElement@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@ATL@@QEAAPEAUIXMLDOMElement@@PEAUIUnknown@@@Z; ATL::CComQIPtr<IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>::operator=(IUnknown *)
0x180102a31  mov     rcx, [rsp+120h+var_E0]
0x180102a36  test    rcx, rcx
0x180102a39  jnz     short loc_180102A76
0x180102a3b  mov     [rbp+3Fh+arg_8], 8007000Eh
0x180102a42  lea     rcx, [rsp+120h+var_E0]
0x180102a47  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180102a4c  nop
0x180102a4d  lea     rcx, [rsp+120h+pvarg]; pvarg
0x180102a52  call    cs:__imp_VariantClear
0x180102a58  jmp     loc_180102EA7
0x180102a5d  lea     rcx, [rbp+3Fh+bstrString]
0x180102a61  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180102a66  nop
0x180102a67  lea     rcx, [rsp+120h+var_E0]
0x180102a6c  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180102a71  jmp     loc_180102EA7
0x180102a76  movups  xmm0, xmmword ptr [rsp+120h+pvarg]
0x180102a7b  movaps  [rbp+3Fh+var_A0], xmm0
0x180102a7f  movsd   xmm1, qword ptr [rsp+120h+pvarg+10h]
0x180102a85  movsd   [rbp+3Fh+var_90], xmm1
0x180102a8a  mov     rax, [rcx]
0x180102a8d  lea     r8, [rbp+3Fh+var_A0]
0x180102a91  mov     rdx, cs:?g_bstrDeviceHardwareBoundTime@@3VCComBSTR@ATL@@A; ATL::CComBSTR g_bstrDeviceHardwareBoundTime
0x180102a98  mov     rax, [rax+168h]
0x180102a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102aa4  mov     [rbp+3Fh+arg_8], eax
0x180102aa7  test    eax, eax
0x180102aa9  jnz     short loc_180102A42
0x180102aab  lea     rcx, [rsp+120h+pvarg]; pvarg
0x180102ab0  call    cs:__imp_VariantClear
0x180102ab6  nop
0x180102ab7  lea     rcx, [rsp+120h+var_E0]
0x180102abc  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180102ac1  nop
0x180102ac2  lea     rcx, [rsp+120h+pvarg]; pvarg
0x180102ac7  call    cs:__imp_VariantClear
0x180102acd  mov     r15d, 13h
0x180102ad3  mov     word ptr [rsp+120h+pvarg], r15w
0x180102ad9  mov     dword ptr [rsp+120h+pvarg+8], r12d
0x180102ade  mov     [rsp+120h+var_E0], rdi
0x180102ae3  mov     rdx, [rsp+120h+var_C0]
0x180102ae8  lea     rcx, [rsp+120h+var_E0]
0x180102aed  call    ??4?$CComQIPtr@UIXMLDOMElement@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@ATL@@QEAAPEAUIXMLDOMElement@@PEAUIUnknown@@@Z; ATL::CComQIPtr<IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>::operator=(IUnknown *)
0x180102af2  mov     rcx, [rsp+120h+var_E0]
0x180102af7  test    rcx, rcx
0x180102afa  jnz     short loc_180102B13
0x180102afc  mov     [rbp+3Fh+arg_8], 8007000Eh
0x180102b03  lea     rcx, [rsp+120h+var_E0]
0x180102b08  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180102b0d  nop
0x180102b0e  jmp     loc_180102A4D
0x180102b13  movups  xmm0, xmmword ptr [rsp+120h+pvarg]
0x180102b18  movaps  [rbp+3Fh+var_A0], xmm0
0x180102b1c  movsd   xmm1, qword ptr [rsp+120h+pvarg+10h]
0x180102b22  movsd   [rbp+3Fh+var_90], xmm1
0x180102b27  mov     rax, [rcx]
0x180102b2a  lea     r8, [rbp+3Fh+var_A0]
0x180102b2e  mov     rdx, cs:?g_bstrDeviceTpmKeyStateClient@@3VCComBSTR@ATL@@A; ATL::CComBSTR g_bstrDeviceTpmKeyStateClient
0x180102b35  mov     rax, [rax+168h]
0x180102b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102b41  mov     [rbp+3Fh+arg_8], eax
0x180102b44  test    eax, eax
0x180102b46  jnz     short loc_180102B03
0x180102b48  lea     rcx, [rsp+120h+pvarg]; pvarg
0x180102b4d  call    cs:__imp_VariantClear
0x180102b53  nop
0x180102b54  lea     rcx, [rsp+120h+var_E0]
0x180102b59  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180102b5e  nop
0x180102b5f  lea     rcx, [rsp+120h+pvarg]; pvarg
0x180102b64  call    cs:__imp_VariantClear
0x180102b6a  mov     word ptr [rsp+120h+pvarg], r15w
0x180102b70  mov     eax, [rbp+3Fh+arg_20]
0x180102b73  mov     dword ptr [rsp+120h+pvarg+8], eax
0x180102b77  mov     [rsp+120h+var_E0], rdi
0x180102b7c  mov     rdx, [rsp+120h+var_C0]
0x180102b81  lea     rcx, [rsp+120h+var_E0]
0x180102b86  call    ??4?$CComQIPtr@UIXMLDOMElement@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@ATL@@QEAAPEAUIXMLDOMElement@@PEAUIUnknown@@@Z; ATL::CComQIPtr<IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>::operator=(IUnknown *)
0x180102b8b  mov     rcx, [rsp+120h+var_E0]
0x180102b90  test    rcx, rcx
0x180102b93  jnz     short loc_180102BAC
0x180102b95  mov     [rbp+3Fh+arg_8], 8007000Eh
0x180102b9c  lea     rcx, [rsp+120h+var_E0]
0x180102ba1  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180102ba6  nop
0x180102ba7  jmp     loc_180102A4D
0x180102bac  movups  xmm0, xmmword ptr [rsp+120h+pvarg]
0x180102bb1  movaps  [rbp+3Fh+var_A0], xmm0
0x180102bb5  movsd   xmm1, qword ptr [rsp+120h+pvarg+10h]
0x180102bbb  movsd   [rbp+3Fh+var_90], xmm1
0x180102bc0  mov     rax, [rcx]
0x180102bc3  lea     r8, [rbp+3Fh+var_A0]
0x180102bc7  mov     rdx, cs:?g_bstrDeviceTpmKeyStateServer@@3VCComBSTR@ATL@@A; ATL::CComBSTR g_bstrDeviceTpmKeyStateServer
0x180102bce  mov     rax, [rax+168h]
0x180102bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102bda  mov     [rbp+3Fh+arg_8], eax
0x180102bdd  test    eax, eax
0x180102bdf  jnz     short loc_180102B9C
0x180102be1  lea     rcx, [rsp+120h+pvarg]; pvarg
0x180102be6  call    cs:__imp_VariantClear
0x180102bec  nop
0x180102bed  lea     rcx, [rsp+120h+var_E0]
0x180102bf2  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180102bf7  nop
0x180102bf8  lea     rcx, [rsp+120h+pvarg]; pvarg
0x180102bfd  call    cs:__imp_VariantClear
0x180102c03  mov     esi, 2
0x180102c08  mov     ebx, [rbp+3Fh+arg_28]
0x180102c0b  test    ebx, ebx
0x180102c0d  jz      loc_180102CCB
0x180102c13  mov     [rsp+120h+var_E0], rdi
0x180102c18  mov     rdx, [rsp+120h+var_C0]
0x180102c1d  lea     rcx, [rsp+120h+var_E0]
0x180102c22  call    ??4?$CComQIPtr@UIXMLDOMElement@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@ATL@@QEAAPEAUIXMLDOMElement@@PEAUIUnknown@@@Z; ATL::CComQIPtr<IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>::operator=(IUnknown *)
0x180102c27  mov     rcx, [rsp+120h+var_E0]
0x180102c2c  test    rcx, rcx
0x180102c2f  jnz     short loc_180102C4E
0x180102c31  lea     r9, aPelementIsNull; "pElement is null."
0x180102c38  mov     r8d, 477h; unsigned int
0x180102c3e  lea     rdx, aOnecoreuapDsEx_105; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180102c45  mov     ecx, esi; unsigned __int8
0x180102c47  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180102c4c  jmp     short loc_180102CC1
0x180102c4e  mov     word ptr [rsp+120h+pvarg], r15w
0x180102c54  mov     dword ptr [rsp+120h+pvarg+8], ebx
0x180102c58  movups  xmm0, xmmword ptr [rsp+120h+pvarg]
0x180102c5d  movaps  [rbp+3Fh+var_A0], xmm0
0x180102c61  movsd   xmm1, qword ptr [rsp+120h+pvarg+10h]
0x180102c67  movsd   [rbp+3Fh+var_90], xmm1
0x180102c6c  mov     rax, [rcx]
0x180102c6f  lea     r8, [rbp+3Fh+var_A0]
0x180102c73  lea     rdx, aLicensekeysequ; "LicenseKeySequence"
0x180102c7a  mov     rax, [rax+168h]
0x180102c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102c86  test    eax, eax
0x180102c88  jns     short loc_180102CA9
0x180102c8a  mov     dword ptr [rsp+120h+var_100], eax
0x180102c8e  lea     r9, aSetattributeLi_1; "SetAttribute LicenseKeySequence failed "...
0x180102c95  mov     r8d, 47Fh; unsigned int
0x180102c9b  lea     rdx, aOnecoreuapDsEx_105; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
  ... truncated ...
```
