# RDSHTelemetryLogging::GetLicenseInfo(long *,ulong *,ulong * *)

- ea: `0x180091298`
- end: `0x180092159`
- name: `?GetLicenseInfo@RDSHTelemetryLogging@@SAJPEAJPEAKPEAPEAK@Z`
- size: `3777`
- prototype: `__int64 __fastcall(int *, unsigned int *, unsigned int **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800938f0`

## callees

- `0x1800016a8`
- `0x180009940`
- `0x1800139c0`
- `0x180015310`
- `0x18003a634`
- `0x180090dc0`
- `0x180090ff4`
- `0x180091298`
- `0x18009236c`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180091a13`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180091a13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180092087`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180092087`
- `OLEAUT32!__imp_SysAllocString` at `0x180091b39`
- `OLEAUT32!__imp_SysAllocString` at `0x180091b6a`
- `OLEAUT32!__imp_SysAllocString` at `0x180091b39`
- `OLEAUT32!__imp_SysAllocString` at `0x180091b6a`
- `OLEAUT32!__imp_SysFreeString` at `0x180091c55`
- `OLEAUT32!__imp_SysFreeString` at `0x180091c55`
- `OLEAUT32!__imp_VariantInit` at `0x1800912df`
- `OLEAUT32!__imp_VariantInit` at `0x1800912f0`
- `OLEAUT32!__imp_VariantInit` at `0x180091301`
- `OLEAUT32!__imp_VariantInit` at `0x180091312`
- `OLEAUT32!__imp_VariantInit` at `0x180091b95`
- `OLEAUT32!__imp_VariantInit` at `0x1800912df`
- `OLEAUT32!__imp_VariantInit` at `0x1800912f0`
- `OLEAUT32!__imp_VariantInit` at `0x180091301`
- `OLEAUT32!__imp_VariantInit` at `0x180091312`
- `OLEAUT32!__imp_VariantInit` at `0x180091b95`
- `OLEAUT32!__imp_VariantClear` at `0x180091b52`
- `OLEAUT32!__imp_VariantClear` at `0x180091cea`
- `OLEAUT32!__imp_VariantClear` at `0x180091cfb`
- `OLEAUT32!__imp_VariantClear` at `0x180091e65`
- `OLEAUT32!__imp_VariantClear` at `0x180091e76`
- `OLEAUT32!__imp_VariantClear` at `0x180092028`
- `OLEAUT32!__imp_VariantClear` at `0x180092039`
- `OLEAUT32!__imp_VariantClear` at `0x1800920b2`
- `OLEAUT32!__imp_VariantClear` at `0x1800920c3`
- `OLEAUT32!__imp_VariantClear` at `0x1800920d4`
- `OLEAUT32!__imp_VariantClear` at `0x1800920e5`
- `OLEAUT32!__imp_VariantClear` at `0x180091b52`
- `OLEAUT32!__imp_VariantClear` at `0x180091cea`
- `OLEAUT32!__imp_VariantClear` at `0x180091cfb`
- `OLEAUT32!__imp_VariantClear` at `0x180091e65`
- `OLEAUT32!__imp_VariantClear` at `0x180091e76`
- `OLEAUT32!__imp_VariantClear` at `0x180092028`
- `OLEAUT32!__imp_VariantClear` at `0x180092039`
- `OLEAUT32!__imp_VariantClear` at `0x1800920b2`
- `OLEAUT32!__imp_VariantClear` at `0x1800920c3`
- `OLEAUT32!__imp_VariantClear` at `0x1800920d4`
- `OLEAUT32!__imp_VariantClear` at `0x1800920e5`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800919cf`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800919cf`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180091a4c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180091a4c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180091d2a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180091d2a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180092097`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180092097`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18009136d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18009136d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180091417`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180091417`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800914f1`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800914f1`

## string_xrefs

- `0x180091444`: `CoCreateInstance() failed`
- `0x180091484`: `\\.\ROOT\cimv2\TerminalServices`
- `0x18009154c`: `SELECT * FROM Win32_TerminalServiceSetting`
- `0x180091682`: `__PATH`
- `0x1800916b3`: `Failed to get class __PATH property.`
- `0x1800916f1`: `Failed to get class __PATH property. Return value is not VT_BSTR.`
- `0x180091a79`: `SafeArrayAccessData failed.`
- `0x180091b09`: `Failed to get Win32_TerminalServiceSetting.GetTStoLSConnectivityStatus.`
- `0x18009206c`: `Failed to create a new instance of a class.`
- `0x180091d57`: `SafeArrayUnaccessData failed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall RDSHTelemetryLogging::GetLicenseInfo(int *a1, LONG *a2, unsigned int **a3)
{
  unsigned int **v3; // r12
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  LONG lVal; // esi
  char *v8; // r15
  struct IUnknown *v9; // rdx
  int v10; // ecx
  HRESULT Instance; // ebx
  int v12; // r8d
  int v13; // r9d
  int v14; // edi
  const char *v15; // rax
  int *v16; // rdx
  BSTR *p_bstrString; // rax
  int v18; // ebx
  struct IUnknown *v19; // rdx
  SAFEARRAY *parray; // r12
  HRESULT UBound; // eax
  bool v22; // zf
  unsigned int v23; // eax
  int v24; // ecx
  const unsigned __int16 *v25; // r8
  int v26; // r9d
  const char *v27; // rax
  int *v28; // rdx
  unsigned int v29; // r15d
  const OLECHAR *v30; // rbx
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  IUnknown *v34; // rsi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  const char *v36; // rbx
  _QWORD *v37; // rax
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  int v41; // ecx
  int v42; // r8d
  int v43; // r9d
  const char **v44; // rax
  int *v45; // rdx
  const char *v46; // rax
  int *v47; // rdx
  const char **dwImpLevel; // [rsp+28h] [rbp-D8h]
  const char **dwCapabilities; // [rsp+38h] [rbp-C8h]
  const char **dwCapabilitiesa; // [rsp+38h] [rbp-C8h]
  BSTR bstrString; // [rsp+50h] [rbp-B0h] BYREF
  const char *v53; // [rsp+58h] [rbp-A8h] BYREF
  const char *v54; // [rsp+60h] [rbp-A0h] BYREF
  const char *v55; // [rsp+68h] [rbp-98h] BYREF
  const char *v56; // [rsp+70h] [rbp-90h] BYREF
  const char *v57; // [rsp+78h] [rbp-88h] BYREF
  struct IUnknown *v58; // [rsp+80h] [rbp-80h] BYREF
  LONG plUbound; // [rsp+88h] [rbp-78h] BYREF
  IUnknown *pProxy; // [rsp+90h] [rbp-70h] BYREF
  int v61; // [rsp+98h] [rbp-68h] BYREF
  struct IUnknown *ppv; // [rsp+A0h] [rbp-60h] BYREF
  VARIANTARG v63; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v64; // [rsp+C0h] [rbp-40h] BYREF
  struct IWbemClassObject *v65; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v66; // [rsp+D0h] [rbp-30h] BYREF
  VARIANTARG v67; // [rsp+D8h] [rbp-28h] BYREF
  void *ppvData; // [rsp+F0h] [rbp-10h] BYREF
  struct IWbemClassObject *v69; // [rsp+F8h] [rbp-8h] BYREF
  VARIANTARG v70; // [rsp+100h] [rbp+0h] BYREF
  VARIANTARG pvarg; // [rsp+118h] [rbp+18h] BYREF
  VARIANTARG v72; // [rsp+130h] [rbp+30h] BYREF
  VARIANTARG v73; // [rsp+148h] [rbp+48h] BYREF
  const char *v77; // [rsp+1B8h] [rbp+B8h] BYREF

  v3 = a3;
  ppv = 0;
  pProxy = 0;
  v66 = 0;
  v58 = 0;
  v69 = 0;
  v65 = 0;
  VariantInit(&pvarg);
  VariantInit(&v70);
  VariantInit(&v73);
  VariantInit(&v72);
  ppvData = 0;
  lVal = 0;
  plUbound = 0;
  v8 = 0;
  v64 = 0;
  v61 = 0;
  if ( (unsigned int)dword_18012E170 > 4 )
  {
    v77 = "Getting license information";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v4,
      (unsigned int)&unk_1801168B0,
      v5,
      v6,
      (__int64)&v77);
  }
  Instance = CoInitializeEx(0, 2u);
  if ( Instance < 0 )
  {
    v14 = 0;
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_90;
    v54 = "GetLicenseInfo";
    v15 = "CoInitializeEx() failed.";
    v16 = &dword_18011686C;
    goto LABEL_6;
  }
  v14 = 1;
  Instance = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, (LPVOID *)&ppv);
  if ( Instance < 0 )
  {
    if ( (unsigned int)dword_18012E170 > 3 )
    {
      v54 = "GetLicenseInfo";
      v15 = "CoCreateInstance() failed";
      v16 = (int *)&unk_180116828;
LABEL_6:
      v53 = v15;
      bstrString = (BSTR)"Warning HResult failed";
      dwCapabilities = &v54;
      dwImpLevel = &v53;
      p_bstrString = &bstrString;
LABEL_7:
      LODWORD(v77) = Instance;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v10,
        (_DWORD)v16,
        v12,
        v13,
        (__int64)p_bstrString,
        (__int64)dwImpLevel,
        (__int64)&v77,
        (__int64)dwCapabilities);
      goto LABEL_90;
    }
    goto LABEL_90;
  }
  Instance = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, _QWORD, _QWORD, _QWORD, int, _QWORD, _QWORD, IUnknown **))ppv->lpVtbl[1].QueryInterface)(
               ppv,
               L"\\\\.\\ROOT\\cimv2\\TerminalServices",
               0,
               0,
               0,
               128,
               0,
               0,
               &pProxy);
  if ( Instance >= 0 )
  {
    Instance = CoSetProxyBlanket(pProxy, 0xAu, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 6u, 3u, 0, 0);
    if ( Instance < 0 )
    {
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v54 = "GetLicenseInfo";
        v15 = "CoSetProxyBlanket() failed";
        v16 = (int *)&unk_1801167A0;
        goto LABEL_6;
      }
      goto LABEL_90;
    }
    Instance = ((__int64 (__fastcall *)(IUnknown *, const wchar_t *, const wchar_t *, __int64, _QWORD, __int64 *))pProxy->lpVtbl[6].Release)(
                 pProxy,
                 L"WQL",
                 L"SELECT * FROM Win32_TerminalServiceSetting",
                 48,
                 0,
                 &v64);
    if ( Instance < 0 )
    {
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v54 = "GetLicenseInfo";
        v15 = "Failed to enum settingdata.";
        v16 = &dword_18011675C;
        goto LABEL_6;
      }
      goto LABEL_90;
    }
    v10 = v64;
    if ( !v64 )
    {
      Instance = -2147467259;
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v54 = "GetLicenseInfo";
        v15 = "Enum object is NULL.";
        v16 = (int *)&unk_180116718;
        goto LABEL_6;
      }
      goto LABEL_90;
    }
    Instance = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, int *))(*(_QWORD *)v64 + 32LL))(
                 v64,
                 0xFFFFFFFFLL,
                 1,
                 &v66,
                 &v61);
    if ( Instance < 0 )
    {
LABEL_26:
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v57 = "GetLicenseInfo";
        v56 = "Failed to get settingdata object.";
        v55 = "Warning HResult failed";
        dwCapabilities = &v57;
        dwImpLevel = &v56;
        p_bstrString = (BSTR *)&v55;
        v16 = &dword_1801166D4;
        goto LABEL_7;
      }
      goto LABEL_90;
    }
    if ( !v61 )
    {
      Instance = -2147023728;
      goto LABEL_26;
    }
    Instance = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v66 + 32LL))(
                 v66,
                 L"__PATH",
                 0,
                 &pvarg,
                 0,
                 0);
    if ( Instance < 0 )
    {
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v54 = "GetLicenseInfo";
        v15 = "Failed to get class __PATH property.";
        v16 = (int *)&unk_180116690;
        goto LABEL_6;
      }
      goto LABEL_90;
    }
    if ( pvarg.vt != 8 )
    {
      Instance = -2147467259;
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v54 = "GetLicenseInfo";
        v15 = "Failed to get class __PATH property. Return value is not VT_BSTR.";
        v16 = &dword_18011664C;
        goto LABEL_6;
      }
      goto LABEL_90;
    }
    v18 = ((__int64 (__fastcall *)(IUnknown *, LONGLONG, const wchar_t *, _QWORD, _QWORD, _QWORD, struct IUnknown **, _QWORD))pProxy->lpVtbl[8].QueryInterface)(
            pProxy,
            pvarg.llVal,
            L"GetGracePeriodDays",
            0,
            0,
            0,
            &v58,
            0);
    if ( v18 < 0 )
    {
      _DbgPrintMessage(8, "GetGracePeriodDays failed.");
      lVal = v18;
      LODWORD(v77) = v18;
    }
    else
    {
      Instance = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v58->lpVtbl[1].AddRef)(
                   v58,
                   L"ReturnValue",
                   0,
                   &v70,
                   0,
                   0);
      if ( Instance < 0 )
      {
        if ( (unsigned int)dword_18012E170 > 3 )
        {
          v54 = "GetLicenseInfo";
          v15 = "Failed to get ReturnValue from GetGracePeriodDays call.";
          v16 = (int *)&unk_180116608;
          goto LABEL_6;
        }
        goto LABEL_90;
      }
      lVal = v70.lVal;
      LODWORD(v77) = v70.lVal;
      if ( v70.lVal < 0 )
      {
        _DbgPrintMessage(8, "GetGracePeriodDays failed.");
      }
      else
      {
        lVal = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v58->lpVtbl[1].AddRef)(
                 v58,
                 L"DaysLeft",
                 0,
                 &v73,
                 0,
                 0);
        LODWORD(v77) = lVal;
        if ( lVal < 0 )
        {
          _DbgPrintMessage(8, "Failed to get DaysLeft value.");
        }
        else
        {
          lVal = v73.lVal;
          LODWORD(v77) = v73.lVal;
        }
      }
    }
    if ( v58 )
      ATL::AtlComPtrAssign(&v58, v19);
    Instance = ((__int64 (__fastcall *)(IUnknown *, LONGLONG, const wchar_t *, _QWORD, _QWORD, _QWORD, struct IUnknown **, _QWORD))pProxy->lpVtbl[8].QueryInterface)(
                 pProxy,
                 pvarg.llVal,
                 L"GetSpecifiedLicenseServerList",
                 0,
                 0,
                 0,
                 &v58,
                 0);
    if ( Instance < 0 )
    {
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v54 = "GetLicenseInfo";
        v15 = "Failed to execute GetSpecifiedLicenseServerList method.";
        v16 = &dword_1801165C4;
        goto LABEL_6;
      }
      goto LABEL_90;
    }
    Instance = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v58->lpVtbl[1].AddRef)(
                 v58,
                 L"ReturnValue",
                 0,
                 &v70,
                 0,
                 0);
    if ( Instance < 0 )
    {
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v54 = "GetLicenseInfo";
        v15 = "Failed to get ReturnValue from GetSpecifiedLicenseServerList call.";
        v16 = (int *)&unk_180116580;
        goto LABEL_6;
      }
      goto LABEL_90;
    }
    Instance = v70.lVal;
    if ( v70.lVal < 0 )
    {
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v54 = "GetLicenseInfo";
        v15 = "GetSpecifiedLicenseServerList failed.";
        v16 = &dword_18011653C;
        goto LABEL_6;
      }
      goto LABEL_90;
    }
    Instance = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD))v58->lpVtbl[1].AddRef)(
                 v58,
                 L"SpecifiedLSList",
                 0,
                 &v72,
                 0);
    if ( Instance < 0 )
    {
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v54 = "GetLicenseInfo";
        v15 = "Failed to get SpecifiedLSList from GetSpecifiedLicenseServerList call.";
        v16 = (int *)&unk_1801164F8;
        goto LABEL_6;
      }
      goto LABEL_90;
    }
    if ( v72.vt != 8200 )
    {
      Instance = -2147467259;
      _DbgPrintMessage(8, "SpecifiedLSList value is invalid.");
      goto LABEL_90;
    }
    parray = v72.parray;
    if ( v58 )
      ATL::AtlComPtrAssign(&v58, v9);
    UBound = SafeArrayGetUBound(parray, 1u, &plUbound);
    Instance = UBound;
    if ( UBound < 0 )
    {
      _DbgPrintMessage(8, "SafeArrayGetLBound failed 0x%x", UBound);
      goto LABEL_89;
    }
    v22 = plUbound == -1;
    v23 = ++plUbound;
    if ( v22 )
      goto LABEL_89;
    v8 = (char *)LocalAlloc(0x40u, 4LL * v23);
    v54 = v8;
    if ( !v8 )
    {
      Instance = -2147467259;
      _DbgPrintMessage(8, "Out of memmory while allocating pdwServerStatus");
      goto LABEL_89;
    }
    Instance = SafeArrayAccessData(parray, &ppvData);
    if ( Instance >= 0 )
    {
      Instance = RDSHTelemetryLogging::GetMethod(
                   (struct IWbemServices *)pProxy,
                   (const unsigned __int16 *)v9,
                   v25,
                   &v69,
                   &v65,
                   0);
      if ( Instance >= 0 )
      {
        v29 = 0;
        if ( plUbound )
        {
          while ( 1 )
          {
            v53 = 0;
            v30 = SysAllocString(*((const OLECHAR **)ppvData + v29));
            v63.vt = 0;
            VariantClear(&v63);
            v63.vt = 8;
            v63.llVal = (LONGLONG)SysAllocString(v30);
            if ( !v63.llVal && v30 )
            {
              v63.vt = 10;
              v63.lVal = -2147024882;
              ATL::AtlThrowImpl(-2147024882);
            }
            VariantInit(&v67);
            Instance = ((__int64 (__fastcall *)(struct IWbemClassObject *, _QWORD, const char **))v65->lpVtbl->SpawnInstance)(
                         v65,
                         0,
                         &v53);
            if ( Instance < 0 )
              break;
            Instance = (*(__int64 (__fastcall **)(const char *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v53 + 40LL))(
                         v53,
                         L"ServerName",
                         0,
                         &v63,
                         0);
            if ( Instance < 0 )
            {
              if ( (unsigned int)dword_18012E170 <= 3 )
                goto LABEL_110;
              v57 = "GetLicenseInfo";
              v46 = "Failed to put 'ServerName' parameter.";
              v47 = (int *)&unk_1801163E8;
              goto LABEL_109;
            }
            v34 = pProxy;
            QueryInterface = pProxy->lpVtbl[8].QueryInterface;
            v36 = v53;
            v37 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"GetTStoLSConnectivityStatus");
            Instance = ((__int64 (__fastcall *)(IUnknown *, LONGLONG, _QWORD, _QWORD, _QWORD, const char *, struct IUnknown **, _QWORD))QueryInterface)(
                         v34,
                         pvarg.llVal,
                         *v37,
                         0,
                         0,
                         v36,
                         &v58,
                         0);
            SysFreeString(bstrString);
            if ( Instance < 0 )
            {
              if ( (unsigned int)dword_18012E170 <= 3 )
                goto LABEL_99;
              v57 = "GetLicenseInfo";
              v56 = "Failed to execute SetSpecifiedLicenseServerList method.";
              v55 = "Warning HResult failed";
              dwCapabilitiesa = &v57;
              v44 = &v55;
              v45 = &dword_1801163A4;
LABEL_98:
              LODWORD(bstrString) = Instance;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                v38,
                (_DWORD)v45,
                v39,
                v40,
                (__int64)v44,
                (__int64)&v56,
                (__int64)&bstrString,
                (__int64)dwCapabilitiesa);
              goto LABEL_99;
            }
            Instance = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v58->lpVtbl[1].AddRef)(
                         v58,
                         L"ReturnValue",
                         0,
                         &v70,
                         0,
                         0);
            if ( Instance < 0 )
            {
              if ( (unsigned int)dword_18012E170 <= 3 )
                goto LABEL_99;
              v57 = "GetLicenseInfo";
              v56 = "Failed to get ReturnValue from GetTStoLSConnectivityStatus call.";
              v55 = "Warning HResult failed";
              dwCapabilitiesa = &v57;
              v44 = &v55;
              v45 = (int *)&unk_180116360;
              goto LABEL_98;
            }
            Instance = v70.lVal;
            if ( v70.lVal < 0 )
            {
              if ( (unsigned int)dword_18012E170 <= 3 )
                goto LABEL_99;
              v57 = "GetLicenseInfo";
              v56 = "GetTStoLSConnectivityStatus failed.";
              v55 = "Warning HResult failed";
              dwCapabilitiesa = &v57;
              v44 = &v55;
              v45 = &dword_18011631C;
              goto LABEL_98;
            }
            Instance = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v58->lpVtbl[1].AddRef)(
                         v58,
                         L"TStoLSConnectivityStatus",
                         0,
                         &v67,
                         0,
                         0);
            if ( Instance < 0 )
            {
              if ( (unsigned int)dword_18012E170 > 3 )
              {
                v55 = "GetLicenseInfo";
                v56 = "Failed to get SpecifiedLSList from TStoLSConnectivityStatus call.";
                v57 = "Warning HResult failed";
                dwCapabilitiesa = &v55;
                v44 = &v57;
                v45 = (int *)&unk_1801162D8;
                goto LABEL_98;
              }
LABEL_99:
              VariantClear(&v67);
              VariantClear(&v63);
              SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v53);
              v14 = 1;
              goto LABEL_88;
            }
            *(_DWORD *)&v54[4 * v29] = v67.lVal;
            VariantClear(&v67);
            VariantClear(&v63);
            SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v53);
            v14 = 1;
            if ( ++v29 >= plUbound )
              goto LABEL_85;
          }
          if ( (unsigned int)dword_18012E170 > 3 )
          {
            v57 = "GetLicenseInfo";
            v46 = "Failed to create a new instance of a class.";
            v47 = &dword_18011642C;
LABEL_109:
            v56 = v46;
            v55 = "Warning HResult failed";
            LODWORD(bstrString) = Instance;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v31,
              (_DWORD)v47,
              v32,
              v33,
              (__int64)&v55,
              (__int64)&v56,
              (__int64)&bstrString,
              (__int64)&v57);
          }
LABEL_110:
          VariantClear(&v67);
          VariantClear(&v63);
          SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v53);
        }
        else
        {
LABEL_85:
          Instance = SafeArrayUnaccessData(parray);
          if ( Instance < 0 && (unsigned int)dword_18012E170 > 3 )
          {
            v57 = "GetLicenseInfo";
            LODWORD(bstrString) = Instance;
            v56 = "SafeArrayUnaccessData failed.";
            v55 = "Warning HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v41,
              (unsigned int)&dword_180116294,
              v42,
              v43,
              (__int64)&v55,
              (__int64)&v56,
              (__int64)&bstrString,
              (__int64)&v57);
          }
        }
LABEL_88:
        lVal = (int)v77;
        v8 = (char *)v54;
        goto LABEL_89;
      }
      if ( (unsigned int)dword_18012E170 <= 3 )
      {
LABEL_89:
        v3 = a3;
        goto LABEL_90;
      }
      v54 = "GetLicenseInfo";
      v27 = "Failed to get Win32_TerminalServiceSetting.GetTStoLSConnectivityStatus.";
      v28 = (int *)&unk_180116470;
    }
    else
    {
      if ( (unsigned int)dword_18012E170 <= 3 )
        goto LABEL_89;
      v54 = "GetLicenseInfo";
      v27 = "SafeArrayAccessData failed.";
      v28 = &dword_1801164B4;
    }
    v53 = v27;
    bstrString = (BSTR)"Warning HResult failed";
    LODWORD(v77) = Instance;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v24,
      (_DWORD)v28,
      (_DWORD)v25,
      v26,
      (__int64)&bstrString,
      (__int64)&v53,
      (__int64)&v77,
      (__int64)&v54);
    goto LABEL_89;
  }
  if ( (unsigned int)dword_18012E170 > 3 )
  {
    v54 = "GetLicenseInfo";
    v15 = "ConnectServer() failed";
    v16 = &dword_1801167E4;
    goto LABEL_6;
  }
LABEL_90:
  if ( pProxy )
    ATL::AtlComPtrAssign(&pProxy, v9);
  if ( ppv )
    ATL::AtlComPtrAssign(&ppv, v9);
  if ( Instance < 0 )
  {
    if ( v8 )
      LocalFree(v8);
  }
  else
  {
    *a1 = lVal;
    *a2 = plUbound;
    *v3 = (unsigned int *)v8;
  }
  if ( v14 )
    CoUninitialize();
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v64);
  VariantClear(&v72);
  VariantClear(&v73);
  VariantClear(&v70);
  VariantClear(&pvarg);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v65);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v69);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v58);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v66);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&pProxy);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180091298  mov     [rsp-8+arg_10], r8
0x18009129d  mov     [rsp-8+arg_8], rdx
0x1800912a2  mov     [rsp-8+arg_0], rcx
0x1800912a7  push    rbp
0x1800912a8  push    rbx
0x1800912a9  push    rsi
0x1800912aa  push    rdi
0x1800912ab  push    r12
0x1800912ad  push    r13
0x1800912af  push    r15
0x1800912b1  lea     rbp, [rsp-60h]
0x1800912b6  sub     rsp, 160h
0x1800912bd  mov     r12, r8
0x1800912c0  xor     r13d, r13d
0x1800912c3  mov     [rbp+90h+var_F0], r13
0x1800912c7  mov     [rbp+90h+pProxy], r13
0x1800912cb  mov     [rbp+90h+var_C0], r13
0x1800912cf  mov     [rbp+90h+var_110], r13
0x1800912d3  mov     [rbp+90h+var_98], r13
0x1800912d7  mov     [rbp+90h+var_C8], r13
0x1800912db  lea     rcx, [rbp+90h+pvarg]; pvarg
0x1800912df  call    cs:__imp_VariantInit
0x1800912e6  nop     dword ptr [rax+rax+00h]
0x1800912eb  nop
0x1800912ec  lea     rcx, [rbp+90h+var_90]; pvarg
0x1800912f0  call    cs:__imp_VariantInit
0x1800912f7  nop     dword ptr [rax+rax+00h]
0x1800912fc  nop
0x1800912fd  lea     rcx, [rbp+90h+var_48]; pvarg
0x180091301  call    cs:__imp_VariantInit
0x180091308  nop     dword ptr [rax+rax+00h]
0x18009130d  nop
0x18009130e  lea     rcx, [rbp+90h+var_60]; pvarg
0x180091312  call    cs:__imp_VariantInit
0x180091319  nop     dword ptr [rax+rax+00h]
0x18009131e  nop
0x18009131f  mov     [rbp+90h+ppvData], r13
0x180091323  mov     esi, r13d
0x180091326  mov     [rbp+90h+plUbound], r13d
0x18009132a  mov     r15d, r13d
0x18009132d  mov     [rbp+90h+var_D0], r13
0x180091331  mov     [rbp+90h+var_F8], r13d
0x180091335  mov     eax, cs:dword_18012E170
0x18009133b  cmp     eax, 4
0x18009133e  jbe     short loc_180091366
0x180091340  lea     rax, aGettingLicense; "Getting license information"
0x180091347  mov     [rbp+90h+arg_18], rax
0x18009134e  lea     rax, [rbp+90h+arg_18]
0x180091355  mov     [rsp+190h+ppv], rax
0x18009135a  lea     rdx, unk_1801168B0
0x180091361  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180091366  mov     edx, 2; dwCoInit
0x18009136b  xor     ecx, ecx; pvReserved
0x18009136d  call    cs:__imp_CoInitializeEx
0x180091374  nop     dword ptr [rax+rax+00h]
0x180091379  mov     ebx, eax
0x18009137b  test    eax, eax
0x18009137d  jns     short loc_1800913F6
0x18009137f  mov     edi, r13d
0x180091382  mov     eax, cs:dword_18012E170
0x180091388  cmp     eax, 3
0x18009138b  jbe     loc_180091DB5
0x180091391  lea     rax, aGetlicenseinfo; "GetLicenseInfo"
0x180091398  mov     [rsp+190h+var_130], rax
0x18009139d  lea     rax, aCoinitializeex_0; "CoInitializeEx() failed."
0x1800913a4  lea     rdx, dword_18011686C
0x1800913ab  mov     [rsp+190h+var_138], rax
0x1800913b0  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800913b7  mov     [rsp+190h+bstrString], rax
0x1800913bc  lea     rax, [rsp+190h+var_130]
0x1800913c1  mov     qword ptr [rsp+190h+dwCapabilities], rax
0x1800913c6  lea     rax, [rbp+90h+arg_18]
0x1800913cd  mov     [rsp+190h+pAuthInfo], rax
0x1800913d2  lea     rax, [rsp+190h+var_138]
0x1800913d7  mov     qword ptr [rsp+190h+dwImpLevel], rax
0x1800913dc  lea     rax, [rsp+190h+bstrString]
0x1800913e1  mov     [rsp+190h+ppv], rax
0x1800913e6  mov     dword ptr [rbp+90h+arg_18], ebx
0x1800913ec  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800913f1  jmp     loc_180091DB5
0x1800913f6  mov     edi, 1
0x1800913fb  lea     rax, [rbp+90h+var_F0]
0x1800913ff  mov     [rsp+190h+ppv], rax; ppv
0x180091404  lea     r9, IID_IWbemLocator; riid
0x18009140b  mov     r8d, edi; dwClsContext
0x18009140e  xor     edx, edx; pUnkOuter
0x180091410  lea     rcx, CLSID_WbemLocator; rclsid
0x180091417  call    cs:__imp_CoCreateInstance
0x18009141e  nop     dword ptr [rax+rax+00h]
0x180091423  mov     ebx, eax
0x180091425  test    eax, eax
0x180091427  jns     short loc_180091457
0x180091429  mov     eax, cs:dword_18012E170
0x18009142f  cmp     eax, 3
0x180091432  jbe     loc_180091DB5
0x180091438  lea     rax, aGetlicenseinfo; "GetLicenseInfo"
0x18009143f  mov     [rsp+190h+var_130], rax
0x180091444  lea     rax, aCocreateinstan_0; "CoCreateInstance() failed"
0x18009144b  lea     rdx, unk_180116828
0x180091452  jmp     loc_1800913AB
0x180091457  mov     rcx, [rbp+90h+var_F0]
0x18009145b  mov     rax, [rcx]
0x18009145e  lea     rdx, [rbp+90h+pProxy]
0x180091462  mov     [rsp+190h+var_150], rdx
0x180091467  mov     qword ptr [rsp+190h+dwCapabilities], r13
0x18009146c  mov     [rsp+190h+pAuthInfo], r13
0x180091471  mov     [rsp+190h+dwImpLevel], 80h
0x180091479  mov     [rsp+190h+ppv], r13
0x18009147e  xor     r9d, r9d
0x180091481  xor     r8d, r8d
0x180091484  lea     rdx, aRootCimv2Termi; "\\\\.\\ROOT\\cimv2\\TerminalServices"
0x18009148b  mov     rax, [rax+18h]
0x18009148f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091494  mov     ebx, eax
0x180091496  test    eax, eax
0x180091498  jns     short loc_1800914C8
0x18009149a  mov     eax, cs:dword_18012E170
0x1800914a0  cmp     eax, 3
0x1800914a3  jbe     loc_180091DB5
0x1800914a9  lea     rax, aGetlicenseinfo; "GetLicenseInfo"
0x1800914b0  mov     [rsp+190h+var_130], rax
0x1800914b5  lea     rax, aConnectserverF; "ConnectServer() failed"
0x1800914bc  lea     rdx, dword_1801167E4
0x1800914c3  jmp     loc_1800913AB
0x1800914c8  mov     [rsp+190h+dwCapabilities], r13d; dwCapabilities
0x1800914cd  mov     [rsp+190h+pAuthInfo], r13; pAuthInfo
0x1800914d2  mov     [rsp+190h+dwImpLevel], 3; dwImpLevel
0x1800914da  mov     dword ptr [rsp+190h+ppv], 6; dwAuthnLevel
0x1800914e2  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1800914e6  xor     r8d, r8d; dwAuthzSvc
0x1800914e9  lea     edx, [r9+0Bh]; dwAuthnSvc
0x1800914ed  mov     rcx, [rbp+90h+pProxy]; pProxy
0x1800914f1  call    cs:__imp_CoSetProxyBlanket
0x1800914f8  nop     dword ptr [rax+rax+00h]
0x1800914fd  mov     ebx, eax
0x1800914ff  test    eax, eax
0x180091501  jns     short loc_180091531
0x180091503  mov     eax, cs:dword_18012E170
0x180091509  cmp     eax, 3
0x18009150c  jbe     loc_180091DB5
0x180091512  lea     rax, aGetlicenseinfo; "GetLicenseInfo"
0x180091519  mov     [rsp+190h+var_130], rax
0x18009151e  lea     rax, aCosetproxyblan_2; "CoSetProxyBlanket() failed"
0x180091525  lea     rdx, unk_1801167A0
0x18009152c  jmp     loc_1800913AB
0x180091531  mov     rcx, [rbp+90h+pProxy]
0x180091535  mov     rax, [rcx]
0x180091538  lea     rdx, [rbp+90h+var_D0]
0x18009153c  mov     qword ptr [rsp+190h+dwImpLevel], rdx
0x180091541  mov     [rsp+190h+ppv], r13
0x180091546  mov     r9d, 30h ; '0'
0x18009154c  lea     r8, aSelectFromWin3; "SELECT * FROM Win32_TerminalServiceSett"...
0x180091553  lea     rdx, aWql; "WQL"
0x18009155a  mov     rax, [rax+0A0h]
0x180091561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091566  mov     ebx, eax
0x180091568  test    eax, eax
0x18009156a  jns     short loc_18009159A
0x18009156c  mov     eax, cs:dword_18012E170
0x180091572  cmp     eax, 3
0x180091575  jbe     loc_180091DB5
0x18009157b  lea     rax, aGetlicenseinfo; "GetLicenseInfo"
0x180091582  mov     [rsp+190h+var_130], rax
0x180091587  lea     rax, aFailedToEnumSe; "Failed to enum settingdata."
0x18009158e  lea     rdx, dword_18011675C
0x180091595  jmp     loc_1800913AB
0x18009159a  mov     rcx, [rbp+90h+var_D0]
0x18009159e  test    rcx, rcx
0x1800915a1  jnz     short loc_1800915D6
0x1800915a3  mov     ebx, 80004005h
0x1800915a8  mov     eax, cs:dword_18012E170
0x1800915ae  cmp     eax, 3
0x1800915b1  jbe     loc_180091DB5
0x1800915b7  lea     rax, aGetlicenseinfo; "GetLicenseInfo"
0x1800915be  mov     [rsp+190h+var_130], rax
0x1800915c3  lea     rax, aEnumObjectIsNu; "Enum object is NULL."
0x1800915ca  lea     rdx, unk_180116718
0x1800915d1  jmp     loc_1800913AB
0x1800915d6  mov     rax, [rcx]
0x1800915d9  lea     r8, [rbp+90h+var_F8]
0x1800915dd  mov     [rsp+190h+ppv], r8
0x1800915e2  lea     r9, [rbp+90h+var_C0]
0x1800915e6  mov     r8d, edi
0x1800915e9  or      edx, 0FFFFFFFFh
0x1800915ec  mov     rax, [rax+20h]
0x1800915f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800915f5  mov     ebx, eax
0x1800915f7  test    eax, eax
0x1800915f9  js      short loc_180091606
0x1800915fb  cmp     [rbp+90h+var_F8], r13d
0x1800915ff  jnz     short loc_18009166A
0x180091601  mov     ebx, 80070490h
0x180091606  mov     eax, cs:dword_18012E170
0x18009160c  cmp     eax, 3
0x18009160f  jbe     loc_180091DB5
0x180091615  lea     rax, aGetlicenseinfo; "GetLicenseInfo"
0x18009161c  mov     [rsp+190h+var_118], rax
0x180091621  lea     rax, aFailedToGetSet; "Failed to get settingdata object."
0x180091628  mov     [rsp+190h+var_120], rax
0x18009162d  lea     rax, aWarningHresult; "Warning HResult failed"
0x180091634  mov     [rsp+190h+var_128], rax
0x180091639  lea     rax, [rsp+190h+var_118]
0x18009163e  mov     qword ptr [rsp+190h+dwCapabilities], rax
0x180091643  lea     rax, [rbp+90h+arg_18]
0x18009164a  mov     [rsp+190h+pAuthInfo], rax
0x18009164f  lea     rax, [rsp+190h+var_120]
0x180091654  mov     qword ptr [rsp+190h+dwImpLevel], rax
0x180091659  lea     rax, [rsp+190h+var_128]
0x18009165e  lea     rdx, dword_1801166D4
0x180091665  jmp     loc_1800913E1
0x18009166a  mov     rcx, [rbp+90h+var_C0]
0x18009166e  mov     rax, [rcx]
0x180091671  mov     qword ptr [rsp+190h+dwImpLevel], r13
0x180091676  mov     [rsp+190h+ppv], r13
0x18009167b  lea     r9, [rbp+90h+pvarg]
0x18009167f  xor     r8d, r8d
0x180091682  lea     rdx, aPath; "__PATH"
0x180091689  mov     rax, [rax+20h]
0x18009168d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091692  mov     ebx, eax
0x180091694  test    eax, eax
0x180091696  jns     short loc_1800916C6
0x180091698  mov     eax, cs:dword_18012E170
0x18009169e  cmp     eax, 3
0x1800916a1  jbe     loc_180091DB5
0x1800916a7  lea     rax, aGetlicenseinfo; "GetLicenseInfo"
0x1800916ae  mov     [rsp+190h+var_130], rax
0x1800916b3  lea     rax, aFailedToGetCla_0; "Failed to get class __PATH property."
0x1800916ba  lea     rdx, unk_180116690
0x1800916c1  jmp     loc_1800913AB
0x1800916c6  mov     eax, 8
0x1800916cb  cmp     word ptr [rbp+90h+pvarg], ax
0x1800916cf  jz      short loc_180091704
0x1800916d1  mov     ebx, 80004005h
0x1800916d6  mov     eax, cs:dword_18012E170
0x1800916dc  cmp     eax, 3
0x1800916df  jbe     loc_180091DB5
0x1800916e5  lea     rax, aGetlicenseinfo; "GetLicenseInfo"
0x1800916ec  mov     [rsp+190h+var_130], rax
0x1800916f1  lea     rax, aFailedToGetCla_2; "Failed to get class __PATH property. Re"...
0x1800916f8  lea     rdx, dword_18011664C
0x1800916ff  jmp     loc_1800913AB
0x180091704  mov     rcx, [rbp+90h+pProxy]
0x180091708  mov     rax, [rcx]
0x18009170b  mov     qword ptr [rsp+190h+dwCapabilities], r13
0x180091710  lea     rdx, [rbp+90h+var_110]
0x180091714  mov     [rsp+190h+pAuthInfo], rdx
0x180091719  mov     qword ptr [rsp+190h+dwImpLevel], r13
0x18009171e  mov     [rsp+190h+ppv], r13
0x180091723  xor     r9d, r9d
0x180091726  lea     r8, aGetgraceperiod_1; "GetGracePeriodDays"
0x18009172d  mov     rdx, qword ptr [rbp+90h+pvarg+8]
0x180091731  mov     rax, [rax+0C0h]
0x180091738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009173d  mov     ebx, eax
0x18009173f  test    eax, eax
0x180091741  js      loc_18009180B
0x180091747  mov     rcx, [rbp+90h+var_110]
0x18009174b  mov     rax, [rcx]
0x18009174e  mov     qword ptr [rsp+190h+dwImpLevel], r13
0x180091753  mov     [rsp+190h+ppv], r13
0x180091758  lea     r9, [rbp+90h+var_90]
0x18009175c  xor     r8d, r8d
0x18009175f  lea     rdx, aReturnvalue; "ReturnValue"
0x180091766  mov     rax, [rax+20h]
0x18009176a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009176f  mov     ebx, eax
0x180091771  test    eax, eax
0x180091773  jns     short loc_1800917A3
0x180091775  mov     eax, cs:dword_18012E170
0x18009177b  cmp     eax, 3
0x18009177e  jbe     loc_180091DB5
0x180091784  lea     rax, aGetlicenseinfo; "GetLicenseInfo"
0x18009178b  mov     [rsp+190h+var_130], rax
0x180091790  lea     rax, aFailedToGetRet; "Failed to get ReturnValue from GetGrace"...
0x180091797  lea     rdx, unk_180116608
0x18009179e  jmp     loc_1800913AB
0x1800917a3  mov     esi, dword ptr [rbp+90h+var_90+8]
0x1800917a6  mov     dword ptr [rbp+90h+arg_18], esi
0x1800917ac  test    esi, esi
0x1800917ae  js      short loc_1800917F8
0x1800917b0  mov     rcx, [rbp+90h+var_110]
0x1800917b4  mov     rax, [rcx]
0x1800917b7  mov     qword ptr [rsp+190h+dwImpLevel], r13
0x1800917bc  mov     [rsp+190h+ppv], r13
0x1800917c1  lea     r9, [rbp+90h+var_48]
0x1800917c5  xor     r8d, r8d
0x1800917c8  lea     rdx, aDaysleft; "DaysLeft"
0x1800917cf  mov     rax, [rax+20h]
0x1800917d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800917d8  mov     esi, eax
0x1800917da  mov     dword ptr [rbp+90h+arg_18], eax
0x1800917e0  test    eax, eax
0x1800917e2  js      short loc_1800917EF
0x1800917e4  mov     esi, dword ptr [rbp+90h+var_48+8]
0x1800917e7  mov     dword ptr [rbp+90h+arg_18], esi
0x1800917ed  jmp     short loc_180091824
0x1800917ef  lea     rdx, aFailedToGetDay; "Failed to get DaysLeft value."
0x1800917f6  jmp     short loc_1800917FF
0x1800917f8  lea     rdx, aGetgraceperiod_0; "GetGracePeriodDays failed."
  ... truncated ...
```
