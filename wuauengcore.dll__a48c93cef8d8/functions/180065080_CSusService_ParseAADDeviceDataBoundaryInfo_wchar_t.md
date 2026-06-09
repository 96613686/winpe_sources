# CSusService::ParseAADDeviceDataBoundaryInfo(wchar_t *)

- ea: `0x180065080`
- end: `0x180065a45`
- name: `?ParseAADDeviceDataBoundaryInfo@CSusService@@AEAAJPEA_W@Z`
- size: `2501`
- prototype: `__int64 __fastcall(CSusService *__hidden this, wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180060b3c`

## callees

- `0x18000def4`
- `0x18005f43c`
- `0x180065080`
- `0x180110d24`
- `0x180113a10`
- `0x180113ae8`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180065438`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180065438`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006512b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006512b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800650eb`
- `OLEAUT32!__imp_SysAllocString` at `0x1800650eb`
- `OLEAUT32!__imp_VariantInit` at `0x1800650d3`
- `OLEAUT32!__imp_VariantInit` at `0x1800653e1`
- `OLEAUT32!__imp_VariantInit` at `0x180065578`
- `OLEAUT32!__imp_VariantInit` at `0x180065667`
- `OLEAUT32!__imp_VariantInit` at `0x180065756`
- `OLEAUT32!__imp_VariantInit` at `0x1800650d3`
- `OLEAUT32!__imp_VariantInit` at `0x1800653e1`
- `OLEAUT32!__imp_VariantInit` at `0x180065578`
- `OLEAUT32!__imp_VariantInit` at `0x180065667`
- `OLEAUT32!__imp_VariantInit` at `0x180065756`
- `OLEAUT32!__imp_VariantClear` at `0x180065483`
- `OLEAUT32!__imp_VariantClear` at `0x180065600`
- `OLEAUT32!__imp_VariantClear` at `0x180065610`
- `OLEAUT32!__imp_VariantClear` at `0x1800656ef`
- `OLEAUT32!__imp_VariantClear` at `0x1800656ff`
- `OLEAUT32!__imp_VariantClear` at `0x1800657de`
- `OLEAUT32!__imp_VariantClear` at `0x180065844`
- `OLEAUT32!__imp_VariantClear` at `0x1800658bb`
- `OLEAUT32!__imp_VariantClear` at `0x180065939`
- `OLEAUT32!__imp_VariantClear` at `0x1800659fb`
- `OLEAUT32!__imp_VariantClear` at `0x180065483`
- `OLEAUT32!__imp_VariantClear` at `0x180065600`
- `OLEAUT32!__imp_VariantClear` at `0x180065610`
- `OLEAUT32!__imp_VariantClear` at `0x1800656ef`
- `OLEAUT32!__imp_VariantClear` at `0x1800656ff`
- `OLEAUT32!__imp_VariantClear` at `0x1800657de`
- `OLEAUT32!__imp_VariantClear` at `0x180065844`
- `OLEAUT32!__imp_VariantClear` at `0x1800658bb`
- `OLEAUT32!__imp_VariantClear` at `0x180065939`
- `OLEAUT32!__imp_VariantClear` at `0x1800659fb`

## string_xrefs

- `0x18006522b`: `C:\__w\1\s\src\Client\Engine\Agent\SusService.cpp`
- `0x180065316`: `C:\__w\1\s\src\Client\Engine\Agent\SusService.cpp`
- `0x18006550e`: `C:\__w\1\s\src\Client\Engine\Agent\SusService.cpp`
- `0x180065553`: `C:\__w\1\s\src\Client\Engine\Agent\SusService.cpp`
- `0x1800655ea`: `C:\__w\1\s\src\Client\Engine\Agent\SusService.cpp`
- `0x180065642`: `C:\__w\1\s\src\Client\Engine\Agent\SusService.cpp`
- `0x1800656d9`: `C:\__w\1\s\src\Client\Engine\Agent\SusService.cpp`
- `0x180065731`: `C:\__w\1\s\src\Client\Engine\Agent\SusService.cpp`
- `0x1800657c8`: `C:\__w\1\s\src\Client\Engine\Agent\SusService.cpp`
- `0x180065928`: `C:\__w\1\s\src\Client\Engine\Agent\SusService.cpp`
- `0x180065973`: `C:\__w\1\s\src\Client\Engine\Agent\SusService.cpp`
- `0x1800650e4`: `xmlns:plugin="http://schemas.microsoft.com/msus/2011/04/StoreWUAuthInitialization"`
- `0x18006524f`: `/plugin:ProviderData/plugin:RequiredAuthTickets`

## pseudocode

```c
// Hidden C++ exception states: #wind=196
__int64 __fastcall CSusService::ParseAADDeviceDataBoundaryInfo(CSusService *this, wchar_t *a2)
{
  HRESULT v4; // ebx
  __int64 v5; // rdx
  int v6; // eax
  __int64 v7; // r9
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // rbx
  __int64 (__fastcall *v11)(__int64, __int64 *); // rdi
  int v12; // eax
  __int64 v13; // rdi
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, const wchar_t *, __int64 *); // rsi
  __int64 (__fastcall *v16)(__int64, __int64 *); // rbx
  int v17; // eax
  unsigned __int64 v18; // r9
  __int64 v19; // rdx
  _BYTE *v20; // rax
  _QWORD *v21; // rsi
  int v22; // eax
  __int64 v23; // rdx
  unsigned __int64 v24; // r9
  LONGLONG llVal; // r14
  void *v26; // rcx
  int v27; // eax
  int v28; // eax
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r9
  LONGLONG v32; // r14
  void *v33; // rcx
  int v34; // eax
  int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // r9
  LONGLONG v38; // r14
  void *v39; // rcx
  __int64 v40; // rdx
  int ppv; // [rsp+20h] [rbp-A9h]
  _QWORD v43[2]; // [rsp+30h] [rbp-99h] BYREF
  VARIANTARG v44; // [rsp+40h] [rbp-89h] BYREF
  VARIANTARG v45; // [rsp+60h] [rbp-69h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-51h] BYREF
  __int64 v47; // [rsp+90h] [rbp-39h] BYREF
  __int64 v48; // [rsp+98h] [rbp-31h] BYREF
  _WORD v49[2]; // [rsp+A0h] [rbp-29h] BYREF
  __int16 v50; // [rsp+A4h] [rbp-25h] BYREF
  __int64 v51; // [rsp+A8h] [rbp-21h] BYREF
  LPVOID v52; // [rsp+B0h] [rbp-19h] BYREF
  __int64 v53; // [rsp+B8h] [rbp-11h] BYREF
  __int64 v54; // [rsp+C0h] [rbp-9h] BYREF
  __int64 v55; // [rsp+C8h] [rbp-1h] BYREF
  __int64 v56; // [rsp+D0h] [rbp+7h] BYREF
  int v57; // [rsp+D8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  if ( !a2 || !*a2 )
    return 0;
  v52 = 0;
  v49[0] = 0;
  VariantInit(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(L"xmlns:plugin=\"http://schemas.microsoft.com/msus/2011/04/StoreWUAuthInitialization\"");
  if ( v52 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v52 + 16LL))(v52);
    v52 = 0;
  }
  v4 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, &v52);
  if ( v4 < 0 )
  {
    v5 = 5402;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\SusService.cpp",
      (const char *)(unsigned int)v4,
      ppv);
    goto LABEL_142;
  }
  v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v52 + 544LL))(v52, 0);
  if ( v4 < 0 )
  {
    v5 = 5404;
    goto LABEL_19;
  }
  v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v52 + 560LL))(v52, 0);
  if ( v4 < 0 )
  {
    v5 = 5405;
    goto LABEL_19;
  }
  v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v52 + 504LL))(v52, 0);
  if ( v4 < 0 )
  {
    v5 = 5406;
    goto LABEL_19;
  }
  v44 = pvarg;
  v4 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(*(_QWORD *)v52 + 640LL))(
         v52,
         L"SelectionNamespaces",
         &v44);
  if ( v4 < 0 )
  {
    v5 = 5407;
    goto LABEL_19;
  }
  v4 = (*(__int64 (__fastcall **)(LPVOID, wchar_t *, _WORD *))(*(_QWORD *)v52 + 520LL))(v52, a2, v49);
  if ( v4 < 0 )
  {
    v5 = 5409;
    goto LABEL_19;
  }
  if ( !v49[0] )
  {
    v4 = -2145124338;
    v5 = 5410;
    goto LABEL_19;
  }
  v56 = 0;
  v47 = 0;
  v6 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)v52 + 296LL))(
         v52,
         L"/plugin:ProviderData/plugin:RequiredAuthTickets",
         &v56);
  v4 = v6;
  if ( v6 < 0 )
  {
    v7 = (unsigned int)v6;
    v8 = 5424;
LABEL_35:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\SusService.cpp",
      (const char *)v7,
      ppv);
    goto LABEL_137;
  }
  if ( !v56 )
  {
    v4 = 0;
    goto LABEL_137;
  }
  v50 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v56 + 176LL))(v56, &v50);
  v4 = v9;
  if ( v9 < 0 )
  {
    v7 = (unsigned int)v9;
    v8 = 5428;
    goto LABEL_35;
  }
  if ( !v50 )
  {
    v8 = 5430;
LABEL_34:
    v4 = -2145124338;
    v7 = 2149842958LL;
    goto LABEL_35;
  }
  v10 = v56;
  v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v56 + 104LL);
  if ( v47 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    v47 = 0;
  }
  v12 = v11(v10, &v47);
  v4 = v12;
  if ( v12 < 0 )
  {
    v7 = (unsigned int)v12;
    v8 = 5432;
    goto LABEL_35;
  }
  v13 = v47;
  if ( !v47 )
  {
    v8 = 5433;
    goto LABEL_34;
  }
  while ( 1 )
  {
    v47 = 0;
    v43[1] = v13;
    v48 = 0;
    v51 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 136LL))(v13, &v48);
    if ( v4 < 0 )
    {
      v40 = 5448;
      goto LABEL_131;
    }
    v57 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v48 + 88LL))(v48, &v57);
    if ( v4 < 0 )
    {
      v40 = 5450;
      goto LABEL_131;
    }
    if ( !v57 )
    {
      v4 = -2145124338;
      v40 = 5451;
      goto LABEL_131;
    }
    v14 = v48;
    v15 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v48 + 56LL);
    if ( v51 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      v51 = 0;
    }
    v4 = v15(v14, L"Name", &v51);
    if ( v4 < 0 )
    {
      v40 = 5454;
LABEL_131:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v40,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\SusService.cpp",
        (const char *)(unsigned int)v4,
        ppv);
      goto LABEL_132;
    }
    if ( !v51 )
    {
      v4 = -2145124338;
      v40 = 5455;
      goto LABEL_131;
    }
    VariantInit(&v45);
    v4 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v51 + 64LL))(v51, &v45);
    if ( v4 < 0 )
    {
      v19 = 5458;
LABEL_123:
      v18 = (unsigned int)v4;
      goto LABEL_124;
    }
    if ( v45.vt != 8 )
    {
      v4 = -2145124338;
      v19 = 5459;
      goto LABEL_123;
    }
    if ( v45.bstrVal == L"AADdevice" || v45.llVal && CompareStringW(0x7Fu, 1u, v45.bstrVal, -1, L"AADdevice", -1) == 2 )
      break;
    v16 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 128LL);
    if ( v47 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
      v47 = 0;
    }
    v17 = v16(v13, &v47);
    v4 = v17;
    if ( v17 < 0 )
    {
      v18 = (unsigned int)v17;
      v19 = 5509;
LABEL_124:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\SusService.cpp",
        (const char *)v18,
        ppv);
      goto LABEL_125;
    }
    VariantClear(&v45);
    if ( v51 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      v51 = 0;
    }
    if ( v48 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
      v48 = 0;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = v47;
    if ( !v47 )
      goto LABEL_120;
  }
  v20 = SusAlloc(0x20u);
  v21 = v20;
  v43[0] = v20;
  if ( !v20 )
  {
    v4 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1559,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\SusService.cpp",
      (const char *)0x8007000ELL,
      ppv);
    goto LABEL_107;
  }
  *v20 = 1;
  v55 = 0;
  v22 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v48 + 56LL))(
          v48,
          L"AADClientID",
          &v55);
  v4 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x155F,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\SusService.cpp",
      (const char *)(unsigned int)v22,
      ppv);
    goto LABEL_105;
  }
  if ( !v55 )
    goto LABEL_74;
  VariantInit(&v44);
  v4 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v55 + 64LL))(v55, &v44);
  if ( v4 < 0 )
  {
    v23 = 5475;
    goto LABEL_67;
  }
  if ( v44.vt == 8 )
  {
    llVal = v44.llVal;
    v26 = (void *)v21[1];
    if ( v26 )
    {
      SusFree(v26);
      v21[1] = 0;
    }
    v27 = DuplicateOptionalString<wchar_t const *,wchar_t *>(llVal, v21 + 1);
    v4 = v27;
    if ( v27 < 0 )
    {
      v24 = (unsigned int)v27;
      v23 = 5477;
      goto LABEL_72;
    }
    VariantClear(&v44);
LABEL_74:
    v54 = 0;
    v28 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v48 + 56LL))(
            v48,
            L"AADResourceID",
            &v54);
    v4 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x156A,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\SusService.cpp",
        (const char *)(unsigned int)v28,
        ppv);
      goto LABEL_103;
    }
    if ( v54 )
    {
      VariantInit(&v44);
      v29 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v54 + 64LL))(v54, &v44);
      v4 = v29;
      if ( v29 < 0 )
      {
        v30 = 5486;
LABEL_85:
        v31 = (unsigned int)v29;
        goto LABEL_86;
      }
      if ( v44.vt != 8 )
      {
        v4 = -2145124338;
        v31 = 2149842958LL;
        v30 = 5487;
LABEL_86:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v30,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\SusService.cpp",
          (const char *)v31,
          ppv);
        VariantClear(&v44);
LABEL_103:
        if ( v54 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
          v54 = 0;
        }
        goto LABEL_105;
      }
      v32 = v44.llVal;
      v33 = (void *)v21[2];
      if ( v33 )
      {
        SusFree(v33);
        v21[2] = 0;
      }
      v29 = DuplicateOptionalString<wchar_t const *,wchar_t *>(v32, v21 + 2);
      v4 = v29;
      if ( v29 < 0 )
      {
        v30 = 5488;
        goto LABEL_85;
      }
      VariantClear(&v44);
    }
    v53 = 0;
    v34 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v48 + 56LL))(
            v48,
            L"AADAuthority",
            &v53);
    v4 = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1575,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\SusService.cpp",
        (const char *)(unsigned int)v34,
        ppv);
      goto LABEL_101;
    }
    if ( v53 )
    {
      VariantInit(&v44);
      v35 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v53 + 64LL))(v53, &v44);
      v4 = v35;
      if ( v35 < 0 )
      {
        v36 = 5497;
LABEL_99:
        v37 = (unsigned int)v35;
        goto LABEL_100;
      }
      if ( v44.vt != 8 )
      {
        v4 = -2145124338;
        v37 = 2149842958LL;
        v36 = 5498;
LABEL_100:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v36,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\SusService.cpp",
          (const char *)v37,
          ppv);
        VariantClear(&v44);
LABEL_101:
        if ( v53 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
          v53 = 0;
        }
        goto LABEL_103;
      }
      v38 = v44.llVal;
      v39 = (void *)v21[3];
      if ( v39 )
      {
        SusFree(v39);
        v21[3] = 0;
      }
      v35 = DuplicateOptionalString<wchar_t const *,wchar_t *>(v38, v21 + 3);
      v4 = v35;
      if ( v35 < 0 )
      {
        v36 = 5499;
        goto LABEL_99;
      }
      VariantClear(&v44);
    }
    v43[0] = 0;
    WuSmartPtr::XPtrBase<AADDeviceDataBoundaryInfo,WuSmartPtr::Policies::FreeMethodPolicy<AADDeviceDataBoundaryInfo,&void FreeAADDeviceDataBoundaryInfo(void *)>>::InternalRelease((char *)this + 512);
    *((_QWORD *)this + 64) = v21;
    if ( v53 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      v53 = 0;
    }
    if ( v54 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      v54 = 0;
    }
    if ( v55 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
      v55 = 0;
    }
    WuSmartPtr::XPtrBase<AADDeviceDataBoundaryInfo,WuSmartPtr::Policies::FreeMethodPolicy<AADDeviceDataBoundaryInfo,&void FreeAADDeviceDataBoundaryInfo(void *)>>::InternalRelease(v43);
    VariantClear(&v45);
    if ( v51 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      v51 = 0;
    }
    if ( v48 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
      v48 = 0;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = v47;
LABEL_120:
    v4 = 0;
    goto LABEL_138;
  }
  v4 = -2145124338;
  v23 = 5476;
LABEL_67:
  v24 = (unsigned int)v4;
LABEL_72:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v23,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\SusService.cpp",
    (const char *)v24,
    ppv);
  VariantClear(&v44);
LABEL_105:
  if ( v55 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    v55 = 0;
  }
LABEL_107:
  WuSmartPtr::XPtrBase<AADDeviceDataBoundaryInfo,WuSmartPtr::Policies::FreeMethodPolicy<AADDeviceDataBoundaryInfo,&void FreeAADDeviceDataBoundaryInfo(void *)>>::InternalRelease(v43);
LABEL_125:
  VariantClear(&v45);
LABEL_132:
  if ( v51 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    v51 = 0;
  }
  if ( v48 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    v48 = 0;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
LABEL_137:
  v13 = v47;
LABEL_138:
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v47 = 0;
  }
  if ( v56 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    v56 = 0;
  }
LABEL_142:
  VariantClear(&pvarg);
  if ( v52 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v52 + 16LL))(v52);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180065080  mov     [rsp-8+arg_10], rbx
0x180065085  push    rbp
0x180065086  push    rsi
0x180065087  push    rdi
0x180065088  push    r12
0x18006508a  push    r13
0x18006508c  push    r14
0x18006508e  push    r15
0x180065090  lea     rbp, [rsp-27h]
0x180065095  sub     rsp, 0F0h
0x18006509c  mov     rax, cs:__security_cookie
0x1800650a3  xor     rax, rsp
0x1800650a6  mov     [rbp+57h+var_40], rax
0x1800650aa  mov     rdi, rdx
0x1800650ad  mov     r15, rcx
0x1800650b0  xor     r12d, r12d
0x1800650b3  test    rdx, rdx
0x1800650b6  jz      loc_180065A1C
0x1800650bc  cmp     [rdx], r12w
0x1800650c0  jz      loc_180065A1C
0x1800650c6  mov     [rbp+57h+var_70], r12
0x1800650ca  mov     [rbp+57h+var_80], r12w
0x1800650cf  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800650d3  call    cs:__imp_VariantInit
0x1800650d9  nop
0x1800650da  lea     r13d, [r12+8]
0x1800650df  mov     word ptr [rbp+57h+pvarg], r13w
0x1800650e4  lea     rcx, aXmlnsPluginHtt; "xmlns:plugin=\"http://schemas.microsoft"...
0x1800650eb  call    cs:__imp_SysAllocString
0x1800650f1  mov     qword ptr [rbp+57h+pvarg+8], rax
0x1800650f5  mov     rcx, [rbp+57h+var_70]
0x1800650f9  test    rcx, rcx
0x1800650fc  jz      short loc_18006510E
0x1800650fe  mov     rax, [rcx]
0x180065101  mov     rax, [rax+10h]
0x180065105  call    _guard_dispatch_icall
0x18006510a  mov     [rbp+57h+var_70], r12
0x18006510e  lea     rax, [rbp+57h+var_70]
0x180065112  mov     [rsp+120h+ppv], rax; int
0x180065117  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x18006511e  xor     edx, edx; pUnkOuter
0x180065120  lea     r8d, [rdx+1]; dwClsContext
0x180065124  lea     rcx, CLSID_DOMDocument60; rclsid
0x18006512b  call    cs:__imp_CoCreateInstance
0x180065131  mov     ebx, eax
0x180065133  test    eax, eax
0x180065135  jns     short loc_180065141
0x180065137  mov     edx, 151Ah
0x18006513c  jmp     loc_180065224
0x180065141  xor     edx, edx
0x180065143  mov     rcx, [rbp+57h+var_70]
0x180065147  mov     rax, [rcx]
0x18006514a  mov     rax, [rax+220h]
0x180065151  call    _guard_dispatch_icall
0x180065156  mov     ebx, eax
0x180065158  test    eax, eax
0x18006515a  jns     short loc_180065166
0x18006515c  mov     edx, 151Ch
0x180065161  jmp     loc_180065224
0x180065166  xor     edx, edx
0x180065168  mov     rcx, [rbp+57h+var_70]
0x18006516c  mov     rax, [rcx]
0x18006516f  mov     rax, [rax+230h]
0x180065176  call    _guard_dispatch_icall
0x18006517b  mov     ebx, eax
0x18006517d  test    eax, eax
0x18006517f  jns     short loc_18006518B
0x180065181  mov     edx, 151Dh
0x180065186  jmp     loc_180065224
0x18006518b  xor     edx, edx
0x18006518d  mov     rcx, [rbp+57h+var_70]
0x180065191  mov     rax, [rcx]
0x180065194  mov     rax, [rax+1F8h]
0x18006519b  call    _guard_dispatch_icall
0x1800651a0  mov     ebx, eax
0x1800651a2  test    eax, eax
0x1800651a4  jns     short loc_1800651AD
0x1800651a6  mov     edx, 151Eh
0x1800651ab  jmp     short loc_180065224
0x1800651ad  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x1800651b1  movaps  xmmword ptr [rsp+120h+var_E0], xmm0
0x1800651b6  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x1800651bb  movsd   qword ptr [rbp+57h+var_E0+10h], xmm1
0x1800651c0  mov     rcx, [rbp+57h+var_70]
0x1800651c4  mov     rax, [rcx]
0x1800651c7  lea     r8, [rsp+120h+var_E0]
0x1800651cc  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x1800651d3  mov     rax, [rax+280h]
0x1800651da  call    _guard_dispatch_icall
0x1800651df  mov     ebx, eax
0x1800651e1  test    eax, eax
0x1800651e3  jns     short loc_1800651EC
0x1800651e5  mov     edx, 151Fh
0x1800651ea  jmp     short loc_180065224
0x1800651ec  mov     rcx, [rbp+57h+var_70]
0x1800651f0  mov     rax, [rcx]
0x1800651f3  lea     r8, [rbp+57h+var_80]
0x1800651f7  mov     rdx, rdi
0x1800651fa  mov     rax, [rax+208h]
0x180065201  call    _guard_dispatch_icall
0x180065206  mov     ebx, eax
0x180065208  test    eax, eax
0x18006520a  jns     short loc_180065213
0x18006520c  mov     edx, 1521h
0x180065211  jmp     short loc_180065224
0x180065213  cmp     [rbp+57h+var_80], r12w
0x180065218  jnz     short loc_18006523C
0x18006521a  mov     ebx, 8024000Eh
0x18006521f  mov     edx, 1522h; void *
0x180065224  mov     rcx, [rbp+5Fh]; this
0x180065228  mov     r9d, ebx; char *
0x18006522b  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x180065232  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065237  jmp     loc_1800659F7
0x18006523c  mov     [rbp+57h+var_50], r12
0x180065240  mov     [rbp+57h+var_90], r12
0x180065244  mov     rcx, [rbp+57h+var_70]
0x180065248  mov     rax, [rcx]
0x18006524b  lea     r8, [rbp+57h+var_50]
0x18006524f  lea     rdx, aPluginProvider; "/plugin:ProviderData/plugin:RequiredAut"...
0x180065256  mov     rax, [rax+128h]
0x18006525d  call    _guard_dispatch_icall
0x180065262  mov     ebx, eax
0x180065264  test    eax, eax
0x180065266  jns     short loc_180065275
0x180065268  mov     r9d, eax
0x18006526b  mov     edx, 1530h
0x180065270  jmp     loc_180065316
0x180065275  cmp     [rbp+57h+var_50], r12
0x180065279  jnz     short loc_180065283
0x18006527b  mov     ebx, r12d
0x18006527e  jmp     loc_1800659C2
0x180065283  mov     [rbp+57h+var_7C], r12w
0x180065288  mov     rcx, [rbp+57h+var_50]
0x18006528c  mov     rax, [rcx]
0x18006528f  lea     rdx, [rbp+57h+var_7C]
0x180065293  mov     rax, [rax+0B0h]
0x18006529a  call    _guard_dispatch_icall
0x18006529f  mov     ebx, eax
0x1800652a1  test    eax, eax
0x1800652a3  jns     short loc_1800652AF
0x1800652a5  mov     r9d, eax
0x1800652a8  mov     edx, 1534h
0x1800652ad  jmp     short loc_180065316
0x1800652af  cmp     [rbp+57h+var_7C], r12w
0x1800652b4  jnz     short loc_1800652BD
0x1800652b6  mov     edx, 1536h
0x1800652bb  jmp     short loc_18006530E
0x1800652bd  mov     rbx, [rbp+57h+var_50]
0x1800652c1  mov     rax, [rbx]
0x1800652c4  mov     rdi, [rax+68h]
0x1800652c8  mov     rcx, [rbp+57h+var_90]
0x1800652cc  test    rcx, rcx
0x1800652cf  jz      short loc_1800652E1
0x1800652d1  mov     rdx, [rcx]
0x1800652d4  mov     rax, [rdx+10h]
0x1800652d8  call    _guard_dispatch_icall
0x1800652dd  mov     [rbp+57h+var_90], r12
0x1800652e1  lea     rdx, [rbp+57h+var_90]
0x1800652e5  mov     rcx, rbx
0x1800652e8  mov     rax, rdi
0x1800652eb  call    _guard_dispatch_icall
0x1800652f0  mov     ebx, eax
0x1800652f2  test    eax, eax
0x1800652f4  jns     short loc_180065300
0x1800652f6  mov     r9d, eax
0x1800652f9  mov     edx, 1538h
0x1800652fe  jmp     short loc_180065316
0x180065300  mov     rdi, [rbp+57h+var_90]
0x180065304  test    rdi, rdi
0x180065307  jnz     short loc_18006532B
0x180065309  mov     edx, 1539h; void *
0x18006530e  mov     ebx, 8024000Eh
0x180065313  mov     r9d, ebx; char *
0x180065316  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x18006531d  mov     rcx, [rbp+5Fh]; this
0x180065321  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065326  jmp     loc_1800659C2
0x18006532b  lea     r14, aAaddevice; "AADdevice"
0x180065332  mov     [rbp+57h+var_90], r12
0x180065336  mov     [rsp+120h+var_E8], rdi
0x18006533b  mov     [rbp+57h+var_88], r12
0x18006533f  mov     [rbp+57h+var_78], r12
0x180065343  mov     rax, [rdi]
0x180065346  lea     rdx, [rbp+57h+var_88]
0x18006534a  mov     rcx, rdi
0x18006534d  mov     rax, [rax+88h]
0x180065354  call    _guard_dispatch_icall
0x180065359  mov     ebx, eax
0x18006535b  test    eax, eax
0x18006535d  js      loc_180065967
0x180065363  mov     [rbp+57h+var_48], r12d
0x180065367  mov     rcx, [rbp+57h+var_88]
0x18006536b  mov     rax, [rcx]
0x18006536e  lea     rdx, [rbp+57h+var_48]
0x180065372  mov     rax, [rax+58h]
0x180065376  call    _guard_dispatch_icall
0x18006537b  mov     ebx, eax
0x18006537d  test    eax, eax
0x18006537f  js      loc_180065960
0x180065385  cmp     [rbp+57h+var_48], r12d
0x180065389  jz      loc_180065954
0x18006538f  mov     rbx, [rbp+57h+var_88]
0x180065393  mov     rax, [rbx]
0x180065396  mov     rsi, [rax+38h]
0x18006539a  mov     rcx, [rbp+57h+var_78]
0x18006539e  test    rcx, rcx
0x1800653a1  jz      short loc_1800653B3
0x1800653a3  mov     rdx, [rcx]
0x1800653a6  mov     rax, [rdx+10h]
0x1800653aa  call    _guard_dispatch_icall
0x1800653af  mov     [rbp+57h+var_78], r12
0x1800653b3  lea     r8, [rbp+57h+var_78]
0x1800653b7  lea     rdx, aName_2; "Name"
0x1800653be  mov     rcx, rbx
0x1800653c1  mov     rax, rsi
0x1800653c4  call    _guard_dispatch_icall
0x1800653c9  mov     ebx, eax
0x1800653cb  test    eax, eax
0x1800653cd  js      loc_18006594D
0x1800653d3  cmp     [rbp+57h+var_78], r12
0x1800653d7  jz      loc_180065941
0x1800653dd  lea     rcx, [rbp+57h+var_C0]; pvarg
0x1800653e1  call    cs:__imp_VariantInit
0x1800653e7  nop
0x1800653e8  mov     rcx, [rbp+57h+var_78]
0x1800653ec  mov     rax, [rcx]
0x1800653ef  lea     rdx, [rbp+57h+var_C0]
0x1800653f3  mov     rax, [rax+40h]
0x1800653f7  call    _guard_dispatch_icall
0x1800653fc  mov     ebx, eax
0x1800653fe  test    eax, eax
0x180065400  js      loc_18006591C
0x180065406  cmp     word ptr [rbp+57h+var_C0], r13w
0x18006540b  jnz     loc_180065910
0x180065411  mov     r8, qword ptr [rbp+57h+var_C0+8]; lpString1
0x180065415  cmp     r8, r14
0x180065418  jz      loc_1800654EB
0x18006541e  test    r8, r8
0x180065421  jz      short loc_180065447
0x180065423  or      esi, 0FFFFFFFFh
0x180065426  mov     [rsp+120h+cchCount2], esi; cchCount2
0x18006542a  mov     [rsp+120h+ppv], r14; lpString2
0x18006542f  mov     r9d, esi; cchCount1
0x180065432  lea     edx, [rsi+2]; dwCmpFlags
0x180065435  lea     ecx, [rdx+7Eh]; Locale
0x180065438  call    cs:__imp_CompareStringW
0x18006543e  cmp     eax, 2
0x180065441  jz      loc_1800654EB
0x180065447  mov     rax, [rdi]
0x18006544a  mov     rbx, [rax+80h]
0x180065451  mov     rcx, [rbp+57h+var_90]
0x180065455  test    rcx, rcx
0x180065458  jz      short loc_18006546A
0x18006545a  mov     rdx, [rcx]
0x18006545d  mov     rax, [rdx+10h]
0x180065461  call    _guard_dispatch_icall
0x180065466  mov     [rbp+57h+var_90], r12
0x18006546a  lea     rdx, [rbp+57h+var_90]
0x18006546e  mov     rcx, rdi
0x180065471  mov     rax, rbx
0x180065474  call    _guard_dispatch_icall
0x180065479  mov     ebx, eax
0x18006547b  test    eax, eax
0x18006547d  js      short loc_1800654DE
0x18006547f  lea     rcx, [rbp+57h+var_C0]; pvarg
0x180065483  call    cs:__imp_VariantClear
0x180065489  nop
0x18006548a  mov     rcx, [rbp+57h+var_78]
0x18006548e  test    rcx, rcx
0x180065491  jz      short loc_1800654A3
0x180065493  mov     rax, [rcx]
0x180065496  mov     rax, [rax+10h]
0x18006549a  call    _guard_dispatch_icall
0x18006549f  mov     [rbp+57h+var_78], r12
0x1800654a3  mov     rcx, [rbp+57h+var_88]
0x1800654a7  test    rcx, rcx
0x1800654aa  jz      short loc_1800654BC
0x1800654ac  mov     rax, [rcx]
0x1800654af  mov     rax, [rax+10h]
0x1800654b3  call    _guard_dispatch_icall
0x1800654b8  mov     [rbp+57h+var_88], r12
0x1800654bc  mov     rax, [rdi]
0x1800654bf  mov     rcx, rdi
0x1800654c2  mov     rax, [rax+10h]
0x1800654c6  call    _guard_dispatch_icall
0x1800654cb  nop
0x1800654cc  mov     rdi, [rbp+57h+var_90]
0x1800654d0  test    rdi, rdi
0x1800654d3  jnz     loc_180065332
0x1800654d9  jmp     loc_180065908
0x1800654de  mov     r9d, eax
0x1800654e1  mov     edx, 1585h
0x1800654e6  jmp     loc_180065924
0x1800654eb  mov     ecx, 20h ; ' '; unsigned __int64
0x1800654f0  call    ?SusAlloc@@YAPEAX_K@Z; SusAlloc(unsigned __int64)
0x1800654f5  mov     rsi, rax
0x1800654f8  mov     [rsp+120h+var_F0], rax
0x1800654fd  test    rax, rax
0x180065500  jnz     short loc_180065524
  ... truncated ...
```
