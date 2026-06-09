# RDSHTelemetryLogging::GetLicenseInfo(long *,ulong *,ulong * *)

- ea: `0x18008d628`
- end: `0x18008e440`
- name: `?GetLicenseInfo@RDSHTelemetryLogging@@SAJPEAJPEAKPEAPEAK@Z`
- size: `3608`
- prototype: `__int64 __fastcall(int *, unsigned int *, unsigned int **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18008fb70`

## callees

- `0x180001688`
- `0x18000a210`
- `0x180013150`
- `0x1800148f0`
- `0x18003864c`
- `0x18008d188`
- `0x18008d394`
- `0x18008d628`
- `0x18008e640`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008dd73`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008dd73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008e393`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008e393`
- `OLEAUT32!__imp_SysAllocString` at `0x18008de8d`
- `OLEAUT32!__imp_SysAllocString` at `0x18008deb2`
- `OLEAUT32!__imp_SysAllocString` at `0x18008de8d`
- `OLEAUT32!__imp_SysAllocString` at `0x18008deb2`
- `OLEAUT32!__imp_SysFreeString` at `0x18008df91`
- `OLEAUT32!__imp_SysFreeString` at `0x18008df91`
- `OLEAUT32!__imp_VariantInit` at `0x18008d66f`
- `OLEAUT32!__imp_VariantInit` at `0x18008d67a`
- `OLEAUT32!__imp_VariantInit` at `0x18008d685`
- `OLEAUT32!__imp_VariantInit` at `0x18008d690`
- `OLEAUT32!__imp_VariantInit` at `0x18008ded7`
- `OLEAUT32!__imp_VariantInit` at `0x18008d66f`
- `OLEAUT32!__imp_VariantInit` at `0x18008d67a`
- `OLEAUT32!__imp_VariantInit` at `0x18008d685`
- `OLEAUT32!__imp_VariantInit` at `0x18008d690`
- `OLEAUT32!__imp_VariantInit` at `0x18008ded7`
- `OLEAUT32!__imp_VariantClear` at `0x18008dea0`
- `OLEAUT32!__imp_VariantClear` at `0x18008e020`
- `OLEAUT32!__imp_VariantClear` at `0x18008e02b`
- `OLEAUT32!__imp_VariantClear` at `0x18008e189`
- `OLEAUT32!__imp_VariantClear` at `0x18008e194`
- `OLEAUT32!__imp_VariantClear` at `0x18008e340`
- `OLEAUT32!__imp_VariantClear` at `0x18008e34b`
- `OLEAUT32!__imp_VariantClear` at `0x18008e3b2`
- `OLEAUT32!__imp_VariantClear` at `0x18008e3bd`
- `OLEAUT32!__imp_VariantClear` at `0x18008e3c8`
- `OLEAUT32!__imp_VariantClear` at `0x18008e3d3`
- `OLEAUT32!__imp_VariantClear` at `0x18008dea0`
- `OLEAUT32!__imp_VariantClear` at `0x18008e020`
- `OLEAUT32!__imp_VariantClear` at `0x18008e02b`
- `OLEAUT32!__imp_VariantClear` at `0x18008e189`
- `OLEAUT32!__imp_VariantClear` at `0x18008e194`
- `OLEAUT32!__imp_VariantClear` at `0x18008e340`
- `OLEAUT32!__imp_VariantClear` at `0x18008e34b`
- `OLEAUT32!__imp_VariantClear` at `0x18008e3b2`
- `OLEAUT32!__imp_VariantClear` at `0x18008e3bd`
- `OLEAUT32!__imp_VariantClear` at `0x18008e3c8`
- `OLEAUT32!__imp_VariantClear` at `0x18008e3d3`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18008dd35`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18008dd35`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18008dda6`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18008dda6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18008e054`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18008e054`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18008e39d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18008e39d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18008d6e5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18008d6e5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008d789`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008d789`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18008d85d`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18008d85d`

## string_xrefs

- `0x18008d7b0`: `CoCreateInstance() failed`
- `0x18008d7f0`: `\\.\ROOT\cimv2\TerminalServices`
- `0x18008d8b2`: `SELECT * FROM Win32_TerminalServiceSetting`
- `0x18008d9e8`: `__PATH`
- `0x18008da19`: `Failed to get class __PATH property.`
- `0x18008da57`: `Failed to get class __PATH property. Return value is not VT_BSTR.`
- `0x18008ddcd`: `SafeArrayAccessData failed.`
- `0x18008de5d`: `Failed to get Win32_TerminalServiceSetting.GetTStoLSConnectivityStatus.`
- `0x18008e378`: `Failed to create a new instance of a class.`
- `0x18008e07b`: `SafeArrayUnaccessData failed.`

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
  if ( (unsigned int)dword_180128170 > 4 )
  {
    v77 = "Getting license information";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v4,
      (unsigned int)&unk_180110830,
      v5,
      v6,
      (__int64)&v77);
  }
  Instance = CoInitializeEx(0, 2u);
  if ( Instance < 0 )
  {
    v14 = 0;
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_90;
    v54 = "GetLicenseInfo";
    v15 = "CoInitializeEx() failed.";
    v16 = &dword_1801107EC;
    goto LABEL_6;
  }
  v14 = 1;
  Instance = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, (LPVOID *)&ppv);
  if ( Instance < 0 )
  {
    if ( (unsigned int)dword_180128170 > 3 )
    {
      v54 = "GetLicenseInfo";
      v15 = "CoCreateInstance() failed";
      v16 = (int *)&unk_1801107A8;
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
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v54 = "GetLicenseInfo";
        v15 = "CoSetProxyBlanket() failed";
        v16 = (int *)&unk_180110720;
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
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v54 = "GetLicenseInfo";
        v15 = "Failed to enum settingdata.";
        v16 = &dword_1801106DC;
        goto LABEL_6;
      }
      goto LABEL_90;
    }
    v10 = v64;
    if ( !v64 )
    {
      Instance = -2147467259;
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v54 = "GetLicenseInfo";
        v15 = "Enum object is NULL.";
        v16 = (int *)&unk_180110698;
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
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v57 = "GetLicenseInfo";
        v56 = "Failed to get settingdata object.";
        v55 = "Warning HResult failed";
        dwCapabilities = &v57;
        dwImpLevel = &v56;
        p_bstrString = (BSTR *)&v55;
        v16 = &dword_180110654;
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
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v54 = "GetLicenseInfo";
        v15 = "Failed to get class __PATH property.";
        v16 = (int *)&unk_180110610;
        goto LABEL_6;
      }
      goto LABEL_90;
    }
    if ( pvarg.vt != 8 )
    {
      Instance = -2147467259;
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v54 = "GetLicenseInfo";
        v15 = "Failed to get class __PATH property. Return value is not VT_BSTR.";
        v16 = &dword_1801105CC;
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
        if ( (unsigned int)dword_180128170 > 3 )
        {
          v54 = "GetLicenseInfo";
          v15 = "Failed to get ReturnValue from GetGracePeriodDays call.";
          v16 = (int *)&unk_180110588;
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
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v54 = "GetLicenseInfo";
        v15 = "Failed to execute GetSpecifiedLicenseServerList method.";
        v16 = &dword_180110544;
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
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v54 = "GetLicenseInfo";
        v15 = "Failed to get ReturnValue from GetSpecifiedLicenseServerList call.";
        v16 = (int *)&unk_180110500;
        goto LABEL_6;
      }
      goto LABEL_90;
    }
    Instance = v70.lVal;
    if ( v70.lVal < 0 )
    {
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v54 = "GetLicenseInfo";
        v15 = "GetSpecifiedLicenseServerList failed.";
        v16 = &dword_1801104BC;
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
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v54 = "GetLicenseInfo";
        v15 = "Failed to get SpecifiedLSList from GetSpecifiedLicenseServerList call.";
        v16 = (int *)&unk_180110478;
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
              if ( (unsigned int)dword_180128170 <= 3 )
                goto LABEL_110;
              v57 = "GetLicenseInfo";
              v46 = "Failed to put 'ServerName' parameter.";
              v47 = (int *)&unk_180110368;
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
              if ( (unsigned int)dword_180128170 <= 3 )
                goto LABEL_99;
              v57 = "GetLicenseInfo";
              v56 = "Failed to execute SetSpecifiedLicenseServerList method.";
              v55 = "Warning HResult failed";
              dwCapabilitiesa = &v57;
              v44 = &v55;
              v45 = &dword_180110324;
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
              if ( (unsigned int)dword_180128170 <= 3 )
                goto LABEL_99;
              v57 = "GetLicenseInfo";
              v56 = "Failed to get ReturnValue from GetTStoLSConnectivityStatus call.";
              v55 = "Warning HResult failed";
              dwCapabilitiesa = &v57;
              v44 = &v55;
              v45 = (int *)&unk_1801102E0;
              goto LABEL_98;
            }
            Instance = v70.lVal;
            if ( v70.lVal < 0 )
            {
              if ( (unsigned int)dword_180128170 <= 3 )
                goto LABEL_99;
              v57 = "GetLicenseInfo";
              v56 = "GetTStoLSConnectivityStatus failed.";
              v55 = "Warning HResult failed";
              dwCapabilitiesa = &v57;
              v44 = &v55;
              v45 = &dword_18011029C;
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
              if ( (unsigned int)dword_180128170 > 3 )
              {
                v55 = "GetLicenseInfo";
                v56 = "Failed to get SpecifiedLSList from TStoLSConnectivityStatus call.";
                v57 = "Warning HResult failed";
                dwCapabilitiesa = &v55;
                v44 = &v57;
                v45 = (int *)&unk_180110258;
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
          if ( (unsigned int)dword_180128170 > 3 )
          {
            v57 = "GetLicenseInfo";
            v46 = "Failed to create a new instance of a class.";
            v47 = &dword_1801103AC;
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
          if ( Instance < 0 && (unsigned int)dword_180128170 > 3 )
          {
            v57 = "GetLicenseInfo";
            LODWORD(bstrString) = Instance;
            v56 = "SafeArrayUnaccessData failed.";
            v55 = "Warning HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v41,
              (unsigned int)&dword_180110214,
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
      if ( (unsigned int)dword_180128170 <= 3 )
      {
LABEL_89:
        v3 = a3;
        goto LABEL_90;
      }
      v54 = "GetLicenseInfo";
      v27 = "Failed to get Win32_TerminalServiceSetting.GetTStoLSConnectivityStatus.";
      v28 = (int *)&unk_1801103F0;
    }
    else
    {
      if ( (unsigned int)dword_180128170 <= 3 )
        goto LABEL_89;
      v54 = "GetLicenseInfo";
      v27 = "SafeArrayAccessData failed.";
      v28 = &dword_180110434;
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
  if ( (unsigned int)dword_180128170 > 3 )
  {
    v54 = "GetLicenseInfo";
    v15 = "ConnectServer() failed";
    v16 = &dword_180110764;
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
0x18008d628  mov     [rsp-8+arg_10], r8
0x18008d62d  mov     [rsp-8+arg_8], rdx
0x18008d632  mov     [rsp-8+arg_0], rcx
0x18008d637  push    rbp
0x18008d638  push    rbx
0x18008d639  push    rsi
0x18008d63a  push    rdi
0x18008d63b  push    r12
0x18008d63d  push    r13
0x18008d63f  push    r15
0x18008d641  lea     rbp, [rsp-60h]
0x18008d646  sub     rsp, 160h
0x18008d64d  mov     r12, r8
0x18008d650  xor     r13d, r13d
0x18008d653  mov     [rbp+90h+var_F0], r13
0x18008d657  mov     [rbp+90h+pProxy], r13
0x18008d65b  mov     [rbp+90h+var_C0], r13
0x18008d65f  mov     [rbp+90h+var_110], r13
0x18008d663  mov     [rbp+90h+var_98], r13
0x18008d667  mov     [rbp+90h+var_C8], r13
0x18008d66b  lea     rcx, [rbp+90h+pvarg]; pvarg
0x18008d66f  call    cs:__imp_VariantInit
0x18008d675  nop
0x18008d676  lea     rcx, [rbp+90h+var_90]; pvarg
0x18008d67a  call    cs:__imp_VariantInit
0x18008d680  nop
0x18008d681  lea     rcx, [rbp+90h+var_48]; pvarg
0x18008d685  call    cs:__imp_VariantInit
0x18008d68b  nop
0x18008d68c  lea     rcx, [rbp+90h+var_60]; pvarg
0x18008d690  call    cs:__imp_VariantInit
0x18008d696  nop
0x18008d697  mov     [rbp+90h+ppvData], r13
0x18008d69b  mov     esi, r13d
0x18008d69e  mov     [rbp+90h+plUbound], r13d
0x18008d6a2  mov     r15d, r13d
0x18008d6a5  mov     [rbp+90h+var_D0], r13
0x18008d6a9  mov     [rbp+90h+var_F8], r13d
0x18008d6ad  mov     eax, cs:dword_180128170
0x18008d6b3  cmp     eax, 4
0x18008d6b6  jbe     short loc_18008D6DE
0x18008d6b8  lea     rax, aGettingLicense; "Getting license information"
0x18008d6bf  mov     [rbp+90h+arg_18], rax
0x18008d6c6  lea     rax, [rbp+90h+arg_18]
0x18008d6cd  mov     [rsp+190h+ppv], rax
0x18008d6d2  lea     rdx, unk_180110830
0x18008d6d9  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18008d6de  mov     edx, 2; dwCoInit
0x18008d6e3  xor     ecx, ecx; pvReserved
0x18008d6e5  call    cs:__imp_CoInitializeEx
0x18008d6eb  mov     ebx, eax
0x18008d6ed  test    eax, eax
0x18008d6ef  jns     short loc_18008D768
0x18008d6f1  mov     edi, r13d
0x18008d6f4  mov     eax, cs:dword_180128170
0x18008d6fa  cmp     eax, 3
0x18008d6fd  jbe     loc_18008E0D9
0x18008d703  lea     rax, aGetlicenseinfo; "GetLicenseInfo"
0x18008d70a  mov     [rsp+190h+var_130], rax
0x18008d70f  lea     rax, aCoinitializeex_0; "CoInitializeEx() failed."
0x18008d716  lea     rdx, dword_1801107EC
0x18008d71d  mov     [rsp+190h+var_138], rax
0x18008d722  lea     rax, aWarningHresult; "Warning HResult failed"
0x18008d729  mov     [rsp+190h+bstrString], rax
0x18008d72e  lea     rax, [rsp+190h+var_130]
0x18008d733  mov     qword ptr [rsp+190h+dwCapabilities], rax
0x18008d738  lea     rax, [rbp+90h+arg_18]
0x18008d73f  mov     [rsp+190h+pAuthInfo], rax
0x18008d744  lea     rax, [rsp+190h+var_138]
0x18008d749  mov     qword ptr [rsp+190h+dwImpLevel], rax
0x18008d74e  lea     rax, [rsp+190h+bstrString]
0x18008d753  mov     [rsp+190h+ppv], rax
0x18008d758  mov     dword ptr [rbp+90h+arg_18], ebx
0x18008d75e  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18008d763  jmp     loc_18008E0D9
0x18008d768  mov     edi, 1
0x18008d76d  lea     rax, [rbp+90h+var_F0]
0x18008d771  mov     [rsp+190h+ppv], rax; ppv
0x18008d776  lea     r9, IID_IWbemLocator; riid
0x18008d77d  mov     r8d, edi; dwClsContext
0x18008d780  xor     edx, edx; pUnkOuter
0x18008d782  lea     rcx, CLSID_WbemLocator; rclsid
0x18008d789  call    cs:__imp_CoCreateInstance
0x18008d78f  mov     ebx, eax
0x18008d791  test    eax, eax
0x18008d793  jns     short loc_18008D7C3
0x18008d795  mov     eax, cs:dword_180128170
0x18008d79b  cmp     eax, 3
0x18008d79e  jbe     loc_18008E0D9
0x18008d7a4  lea     rax, aGetlicenseinfo; "GetLicenseInfo"
0x18008d7ab  mov     [rsp+190h+var_130], rax
0x18008d7b0  lea     rax, aCocreateinstan_0; "CoCreateInstance() failed"
0x18008d7b7  lea     rdx, unk_1801107A8
0x18008d7be  jmp     loc_18008D71D
0x18008d7c3  mov     rcx, [rbp+90h+var_F0]
0x18008d7c7  mov     rax, [rcx]
0x18008d7ca  lea     rdx, [rbp+90h+pProxy]
0x18008d7ce  mov     [rsp+190h+var_150], rdx
0x18008d7d3  mov     qword ptr [rsp+190h+dwCapabilities], r13
0x18008d7d8  mov     [rsp+190h+pAuthInfo], r13
0x18008d7dd  mov     [rsp+190h+dwImpLevel], 80h
0x18008d7e5  mov     [rsp+190h+ppv], r13
0x18008d7ea  xor     r9d, r9d
0x18008d7ed  xor     r8d, r8d
0x18008d7f0  lea     rdx, aRootCimv2Termi; "\\\\.\\ROOT\\cimv2\\TerminalServices"
0x18008d7f7  mov     rax, [rax+18h]
0x18008d7fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d800  mov     ebx, eax
0x18008d802  test    eax, eax
0x18008d804  jns     short loc_18008D834
0x18008d806  mov     eax, cs:dword_180128170
0x18008d80c  cmp     eax, 3
0x18008d80f  jbe     loc_18008E0D9
0x18008d815  lea     rax, aGetlicenseinfo; "GetLicenseInfo"
0x18008d81c  mov     [rsp+190h+var_130], rax
0x18008d821  lea     rax, aConnectserverF; "ConnectServer() failed"
0x18008d828  lea     rdx, dword_180110764
0x18008d82f  jmp     loc_18008D71D
0x18008d834  mov     [rsp+190h+dwCapabilities], r13d; dwCapabilities
0x18008d839  mov     [rsp+190h+pAuthInfo], r13; pAuthInfo
0x18008d83e  mov     [rsp+190h+dwImpLevel], 3; dwImpLevel
0x18008d846  mov     dword ptr [rsp+190h+ppv], 6; dwAuthnLevel
0x18008d84e  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18008d852  xor     r8d, r8d; dwAuthzSvc
0x18008d855  lea     edx, [r9+0Bh]; dwAuthnSvc
0x18008d859  mov     rcx, [rbp+90h+pProxy]; pProxy
0x18008d85d  call    cs:__imp_CoSetProxyBlanket
0x18008d863  mov     ebx, eax
0x18008d865  test    eax, eax
0x18008d867  jns     short loc_18008D897
0x18008d869  mov     eax, cs:dword_180128170
0x18008d86f  cmp     eax, 3
0x18008d872  jbe     loc_18008E0D9
0x18008d878  lea     rax, aGetlicenseinfo; "GetLicenseInfo"
0x18008d87f  mov     [rsp+190h+var_130], rax
0x18008d884  lea     rax, aCosetproxyblan_2; "CoSetProxyBlanket() failed"
0x18008d88b  lea     rdx, unk_180110720
0x18008d892  jmp     loc_18008D71D
0x18008d897  mov     rcx, [rbp+90h+pProxy]
0x18008d89b  mov     rax, [rcx]
0x18008d89e  lea     rdx, [rbp+90h+var_D0]
0x18008d8a2  mov     qword ptr [rsp+190h+dwImpLevel], rdx
0x18008d8a7  mov     [rsp+190h+ppv], r13
0x18008d8ac  mov     r9d, 30h ; '0'
0x18008d8b2  lea     r8, aSelectFromWin3; "SELECT * FROM Win32_TerminalServiceSett"...
0x18008d8b9  lea     rdx, aWql; "WQL"
0x18008d8c0  mov     rax, [rax+0A0h]
0x18008d8c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d8cc  mov     ebx, eax
0x18008d8ce  test    eax, eax
0x18008d8d0  jns     short loc_18008D900
0x18008d8d2  mov     eax, cs:dword_180128170
0x18008d8d8  cmp     eax, 3
0x18008d8db  jbe     loc_18008E0D9
0x18008d8e1  lea     rax, aGetlicenseinfo; "GetLicenseInfo"
0x18008d8e8  mov     [rsp+190h+var_130], rax
0x18008d8ed  lea     rax, aFailedToEnumSe; "Failed to enum settingdata."
0x18008d8f4  lea     rdx, dword_1801106DC
0x18008d8fb  jmp     loc_18008D71D
0x18008d900  mov     rcx, [rbp+90h+var_D0]
0x18008d904  test    rcx, rcx
0x18008d907  jnz     short loc_18008D93C
0x18008d909  mov     ebx, 80004005h
0x18008d90e  mov     eax, cs:dword_180128170
0x18008d914  cmp     eax, 3
0x18008d917  jbe     loc_18008E0D9
0x18008d91d  lea     rax, aGetlicenseinfo; "GetLicenseInfo"
0x18008d924  mov     [rsp+190h+var_130], rax
0x18008d929  lea     rax, aEnumObjectIsNu; "Enum object is NULL."
0x18008d930  lea     rdx, unk_180110698
0x18008d937  jmp     loc_18008D71D
0x18008d93c  mov     rax, [rcx]
0x18008d93f  lea     r8, [rbp+90h+var_F8]
0x18008d943  mov     [rsp+190h+ppv], r8
0x18008d948  lea     r9, [rbp+90h+var_C0]
0x18008d94c  mov     r8d, edi
0x18008d94f  or      edx, 0FFFFFFFFh
0x18008d952  mov     rax, [rax+20h]
0x18008d956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d95b  mov     ebx, eax
0x18008d95d  test    eax, eax
0x18008d95f  js      short loc_18008D96C
0x18008d961  cmp     [rbp+90h+var_F8], r13d
0x18008d965  jnz     short loc_18008D9D0
0x18008d967  mov     ebx, 80070490h
0x18008d96c  mov     eax, cs:dword_180128170
0x18008d972  cmp     eax, 3
0x18008d975  jbe     loc_18008E0D9
0x18008d97b  lea     rax, aGetlicenseinfo; "GetLicenseInfo"
0x18008d982  mov     [rsp+190h+var_118], rax
0x18008d987  lea     rax, aFailedToGetSet; "Failed to get settingdata object."
0x18008d98e  mov     [rsp+190h+var_120], rax
0x18008d993  lea     rax, aWarningHresult; "Warning HResult failed"
0x18008d99a  mov     [rsp+190h+var_128], rax
0x18008d99f  lea     rax, [rsp+190h+var_118]
0x18008d9a4  mov     qword ptr [rsp+190h+dwCapabilities], rax
0x18008d9a9  lea     rax, [rbp+90h+arg_18]
0x18008d9b0  mov     [rsp+190h+pAuthInfo], rax
0x18008d9b5  lea     rax, [rsp+190h+var_120]
0x18008d9ba  mov     qword ptr [rsp+190h+dwImpLevel], rax
0x18008d9bf  lea     rax, [rsp+190h+var_128]
0x18008d9c4  lea     rdx, dword_180110654
0x18008d9cb  jmp     loc_18008D753
0x18008d9d0  mov     rcx, [rbp+90h+var_C0]
0x18008d9d4  mov     rax, [rcx]
0x18008d9d7  mov     qword ptr [rsp+190h+dwImpLevel], r13
0x18008d9dc  mov     [rsp+190h+ppv], r13
0x18008d9e1  lea     r9, [rbp+90h+pvarg]
0x18008d9e5  xor     r8d, r8d
0x18008d9e8  lea     rdx, aPath; "__PATH"
0x18008d9ef  mov     rax, [rax+20h]
0x18008d9f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d9f8  mov     ebx, eax
0x18008d9fa  test    eax, eax
0x18008d9fc  jns     short loc_18008DA2C
0x18008d9fe  mov     eax, cs:dword_180128170
0x18008da04  cmp     eax, 3
0x18008da07  jbe     loc_18008E0D9
0x18008da0d  lea     rax, aGetlicenseinfo; "GetLicenseInfo"
0x18008da14  mov     [rsp+190h+var_130], rax
0x18008da19  lea     rax, aFailedToGetCla_0; "Failed to get class __PATH property."
0x18008da20  lea     rdx, unk_180110610
0x18008da27  jmp     loc_18008D71D
0x18008da2c  mov     eax, 8
0x18008da31  cmp     word ptr [rbp+90h+pvarg], ax
0x18008da35  jz      short loc_18008DA6A
0x18008da37  mov     ebx, 80004005h
0x18008da3c  mov     eax, cs:dword_180128170
0x18008da42  cmp     eax, 3
0x18008da45  jbe     loc_18008E0D9
0x18008da4b  lea     rax, aGetlicenseinfo; "GetLicenseInfo"
0x18008da52  mov     [rsp+190h+var_130], rax
0x18008da57  lea     rax, aFailedToGetCla_2; "Failed to get class __PATH property. Re"...
0x18008da5e  lea     rdx, dword_1801105CC
0x18008da65  jmp     loc_18008D71D
0x18008da6a  mov     rcx, [rbp+90h+pProxy]
0x18008da6e  mov     rax, [rcx]
0x18008da71  mov     qword ptr [rsp+190h+dwCapabilities], r13
0x18008da76  lea     rdx, [rbp+90h+var_110]
0x18008da7a  mov     [rsp+190h+pAuthInfo], rdx
0x18008da7f  mov     qword ptr [rsp+190h+dwImpLevel], r13
0x18008da84  mov     [rsp+190h+ppv], r13
0x18008da89  xor     r9d, r9d
0x18008da8c  lea     r8, aGetgraceperiod_1; "GetGracePeriodDays"
0x18008da93  mov     rdx, qword ptr [rbp+90h+pvarg+8]
0x18008da97  mov     rax, [rax+0C0h]
0x18008da9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008daa3  mov     ebx, eax
0x18008daa5  test    eax, eax
0x18008daa7  js      loc_18008DB71
0x18008daad  mov     rcx, [rbp+90h+var_110]
0x18008dab1  mov     rax, [rcx]
0x18008dab4  mov     qword ptr [rsp+190h+dwImpLevel], r13
0x18008dab9  mov     [rsp+190h+ppv], r13
0x18008dabe  lea     r9, [rbp+90h+var_90]
0x18008dac2  xor     r8d, r8d
0x18008dac5  lea     rdx, aReturnvalue; "ReturnValue"
0x18008dacc  mov     rax, [rax+20h]
0x18008dad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dad5  mov     ebx, eax
0x18008dad7  test    eax, eax
0x18008dad9  jns     short loc_18008DB09
0x18008dadb  mov     eax, cs:dword_180128170
0x18008dae1  cmp     eax, 3
0x18008dae4  jbe     loc_18008E0D9
0x18008daea  lea     rax, aGetlicenseinfo; "GetLicenseInfo"
0x18008daf1  mov     [rsp+190h+var_130], rax
0x18008daf6  lea     rax, aFailedToGetRet; "Failed to get ReturnValue from GetGrace"...
0x18008dafd  lea     rdx, unk_180110588
0x18008db04  jmp     loc_18008D71D
0x18008db09  mov     esi, dword ptr [rbp+90h+var_90+8]
0x18008db0c  mov     dword ptr [rbp+90h+arg_18], esi
0x18008db12  test    esi, esi
0x18008db14  js      short loc_18008DB5E
0x18008db16  mov     rcx, [rbp+90h+var_110]
0x18008db1a  mov     rax, [rcx]
0x18008db1d  mov     qword ptr [rsp+190h+dwImpLevel], r13
0x18008db22  mov     [rsp+190h+ppv], r13
0x18008db27  lea     r9, [rbp+90h+var_48]
0x18008db2b  xor     r8d, r8d
0x18008db2e  lea     rdx, aDaysleft; "DaysLeft"
0x18008db35  mov     rax, [rax+20h]
0x18008db39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008db3e  mov     esi, eax
0x18008db40  mov     dword ptr [rbp+90h+arg_18], eax
0x18008db46  test    eax, eax
0x18008db48  js      short loc_18008DB55
0x18008db4a  mov     esi, dword ptr [rbp+90h+var_48+8]
0x18008db4d  mov     dword ptr [rbp+90h+arg_18], esi
0x18008db53  jmp     short loc_18008DB8A
0x18008db55  lea     rdx, aFailedToGetDay; "Failed to get DaysLeft value."
0x18008db5c  jmp     short loc_18008DB65
0x18008db5e  lea     rdx, aGetgraceperiod_0; "GetGracePeriodDays failed."
0x18008db65  mov     ecx, 8; int
0x18008db6a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18008db6f  jmp     short loc_18008DB8A
0x18008db71  lea     rdx, aGetgraceperiod_0; "GetGracePeriodDays failed."
0x18008db78  mov     ecx, 8; int
0x18008db7d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18008db82  mov     esi, ebx
  ... truncated ...
```
