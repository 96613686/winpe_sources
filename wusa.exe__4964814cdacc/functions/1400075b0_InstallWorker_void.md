# InstallWorker(void *)

- ea: `0x1400075b0`
- end: `0x1400086f3`
- name: `?InstallWorker@@YAKPEAX@Z`
- size: `4419`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1400044e0`
- `0x140004d6c`
- `0x140005794`
- `0x140005c70`
- `0x140006a44`
- `0x1400075b0`
- `0x14000a4bc`
- `0x14000ab54`
- `0x14000c124`
- `0x14000d620`
- `0x14000e280`
- `0x14000ec58`
- `0x14000ee88`
- `0x14000f240`
- `0x14000f674`
- `0x140013490`
- `0x140014910`
- `0x140015010`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x14000808e`
- `ADVAPI32!RegCreateKeyExW` at `0x14000808e`
- `ADVAPI32!RegSetValueExW` at `0x1400080ec`
- `ADVAPI32!RegSetValueExW` at `0x1400080ec`
- `ADVAPI32!RegCloseKey` at `0x14000861a`
- `ADVAPI32!RegCloseKey` at `0x14000861a`
- `ADVAPI32!EventWrite` at `0x14000844e`
- `ADVAPI32!EventWrite` at `0x14000844e`
- `KERNEL32!GetCommandLineW` at `0x1400083ed`
- `KERNEL32!GetCommandLineW` at `0x1400083ed`
- `KERNEL32!LocalFree` at `0x1400086c8`
- `KERNEL32!LocalFree` at `0x1400086c8`
- `KERNEL32!GetLastError` at `0x140007a56`
- `KERNEL32!GetLastError` at `0x140007a56`
- `KERNEL32!SetLastError` at `0x140007a69`
- `KERNEL32!SetLastError` at `0x140007a69`
- `USER32!ShowWindow` at `0x1400081cf`
- `USER32!ShowWindow` at `0x1400081cf`
- `OLEAUT32!__imp_SysAllocString` at `0x1400077b3`
- `OLEAUT32!__imp_SysAllocString` at `0x1400078e0`
- `OLEAUT32!__imp_SysAllocString` at `0x1400077b3`
- `OLEAUT32!__imp_SysAllocString` at `0x1400078e0`
- `OLEAUT32!__imp_SysFreeString` at `0x140007abc`
- `OLEAUT32!__imp_SysFreeString` at `0x140007af3`
- `OLEAUT32!__imp_SysFreeString` at `0x140007b78`
- `OLEAUT32!__imp_SysFreeString` at `0x1400084f1`
- `OLEAUT32!__imp_SysFreeString` at `0x140008503`
- `OLEAUT32!__imp_SysFreeString` at `0x140008515`
- `OLEAUT32!__imp_SysFreeString` at `0x140008525`
- `OLEAUT32!__imp_SysFreeString` at `0x140007abc`
- `OLEAUT32!__imp_SysFreeString` at `0x140007af3`
- `OLEAUT32!__imp_SysFreeString` at `0x140007b78`
- `OLEAUT32!__imp_SysFreeString` at `0x1400084f1`
- `OLEAUT32!__imp_SysFreeString` at `0x140008503`
- `OLEAUT32!__imp_SysFreeString` at `0x140008515`
- `OLEAUT32!__imp_SysFreeString` at `0x140008525`
- `OLEAUT32!__imp_VariantInit` at `0x140007930`
- `OLEAUT32!__imp_VariantInit` at `0x140007930`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140007633`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140007633`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140008684`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140008684`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140007a61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140007a84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140007a61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140007a84`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400076ea`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000778f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400076ea`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000778f`

## string_xrefs

- `0x140007e7b`: `Failed to get update out of collection`
- `0x140007ea7`: `Failed to get update title`
- `0x140007e41`: `Failed to display no-update message box`
- `0x140007643`: `Failed to initialize COM`
- `0x140007b48`: `Failed to set update title`
- `0x140007f89`: `Failed to display welcome`
- `0x140007c02`: `Failed; user cancelled the install`
- `0x140007d63`: `Update requires new servicing stack`
- `0x140007db0`: `Failed to get update collection from search result`
- `0x140007ddb`: `Failed to get count of updates to install`
- `0x140007df9`: `There should be only one update to install`
- `0x140007e0e`: `There is no update bundle to install`
- `0x140007edc`: `Failed to query whether update is already installed`
- `0x140007ef8`: `Update is already installed`
- `0x140007f35`: `Failed to display update-installed message box`
- `0x14000764f`: `InstallWorker`
- `0x1400076aa`: `InstallWorker`
- `0x1400077c6`: `InstallWorker`
- `0x1400078eb`: `InstallWorker`
- `0x1400076f6`: `Failed to get IUpdateServiceManager interface`
- `0x140007737`: `Failed to add scan package service`
- `0x140007762`: `Failed to get service ID for scan package service`
- `0x14000779b`: `Failed to get IUpdateSession interface`
- `0x14000782f`: `Failed to create a searcher object`
- `0x140007889`: `Failed to set the service ID`
- `0x1400078b5`: `%lsDeploymentAction='Installation'`
- `0x140007b94`: `Failed to search updates. Error code 0X%x`
- `0x140007fa8`: `Failed; user cancelled the installation`
- `0x140007fb9`: `Starting to copy payload`
- `0x140007fdb`: `Failed to copy the offline update to WU's cache`
- `0x140007ff8`: `End of copying payload`
- `0x14000809a`: `Failed to create registry key`
- `0x1400080f8`: `Failed to set command line registry value`
- `0x140008120`: `Failed to create UpdateInstaller object`
- `0x140008151`: `Failed to tell installer what update to install`
- `0x140008162`: `Start of install`
- `0x1400081b5`: `Failed to install update`
- `0x14000820c`: `End of install`
- `0x140008253`: `Failed to get install result code`
- `0x14000827e`: `Failed to get install HResult`
- `0x1400082ab`: `Failed to get IUpdateInstallationResult interface`
- `0x1400082d6`: `Failed to get update HResult`
- `0x140008304`: `Failed to get update result code`
- `0x140008318`: `OperationResultCode of the installation: 0X%x	HRESULT of the installation: 0X%x	OperationResultCode of the update: 0X%x	HRESULT of the update: 0X%x`
- `0x140008368`: `Warning. WUA error code are inconsistent: HRESULT of the update and the installation both indicate sucess while operation result code indicates error.`
- `0x1400083d2`: `Reboot was required for update %ls`
- `0x140008477`: `Failed install update %S`
- `0x1400084d1`: `Failed to remove package scan service from service manager %ls`
- `0x1400080e5`: `WUSACommandLine`

## pseudocode

```c
__int64 __fastcall InstallWorker(PVOID Parameter)
{
  OLECHAR *v1; // rsi
  unsigned __int16 *v2; // rbx
  __int64 v3; // r8
  HRESULT v4; // r15d
  signed int AllFilesFromCabinet; // edi
  const char *v6; // r8
  __int64 v7; // rdx
  BSTR v8; // rax
  const wchar_t *v9; // r9
  __int64 v10; // r8
  __int64 v11; // rsi
  char v12; // si
  int RelatedMSUFiles; // eax
  int v14; // r13d
  int v15; // eax
  struct IUpdateCollection *v16; // rbx
  int v17; // eax
  void **Ptr; // r15
  ULONGLONG v19; // r12
  void *v20; // rdi
  DWORD LastError; // esi
  AppModule *v22; // rcx
  const char *v23; // r8
  __int64 v24; // rdx
  int v25; // r9d
  unsigned int v26; // ebx
  BYTE *v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rbx
  int v30; // ebx
  LPWSTR CommandLineW; // rcx
  __int64 v32; // rax
  OLECHAR *v33; // rdx
  HLOCAL v34; // rbx
  OLECHAR *v36; // [rsp+50h] [rbp-B0h]
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  _WORD v38[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v39; // [rsp+64h] [rbp-9Ch] BYREF
  __int16 v40; // [rsp+68h] [rbp-98h] BYREF
  struct IUpdateCollection *v41; // [rsp+70h] [rbp-90h] BYREF
  BSTR v42; // [rsp+78h] [rbp-88h] BYREF
  int v43; // [rsp+80h] [rbp-80h] BYREF
  int v44; // [rsp+84h] [rbp-7Ch] BYREF
  int v45; // [rsp+88h] [rbp-78h] BYREF
  BSTR v46; // [rsp+90h] [rbp-70h] BYREF
  struct IUpdateCollection *v47; // [rsp+98h] [rbp-68h] BYREF
  __int64 v48; // [rsp+A0h] [rbp-60h] BYREF
  BSTR bstrString; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v50; // [rsp+B0h] [rbp-50h] BYREF
  char v51; // [rsp+B4h] [rbp-4Ch]
  int v52; // [rsp+B8h] [rbp-48h] BYREF
  struct IUpdateSearcher *v53; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v54; // [rsp+C8h] [rbp-38h] BYREF
  LPVOID v55; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v56; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v57; // [rsp+E0h] [rbp-20h] BYREF
  int v58; // [rsp+E8h] [rbp-18h] BYREF
  int v59; // [rsp+ECh] [rbp-14h] BYREF
  __int64 v60; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v61; // [rsp+F8h] [rbp-8h] BYREF
  LPVOID ppv; // [rsp+100h] [rbp+0h] BYREF
  __int64 v63; // [rsp+108h] [rbp+8h] BYREF
  __int64 v64; // [rsp+110h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+118h] [rbp+18h] BYREF
  VARIANTARG pvarg; // [rsp+120h] [rbp+20h] BYREF
  struct _EVENT_DATA_DESCRIPTOR pv; // [rsp+138h] [rbp+38h] BYREF
  LPWSTR v68; // [rsp+148h] [rbp+48h]
  int v69; // [rsp+150h] [rbp+50h]
  int v70; // [rsp+154h] [rbp+54h]
  OLECHAR psz[200]; // [rsp+160h] [rbp+60h] BYREF

  LODWORD(v41) = 0;
  v1 = 0;
  ppv = 0;
  v2 = 0;
  v64 = 0;
  v55 = 0;
  v53 = 0;
  v54 = 0;
  v57 = 0;
  v48 = 0;
  v61 = 0;
  v47 = 0;
  v60 = 0;
  v63 = 0;
  v56 = 0;
  v46 = 0;
  v42 = 0;
  hKey = 0;
  v58 = 0;
  v4 = CoInitializeEx(0, 2u);
  if ( v4 < 0 )
  {
    AllFilesFromCabinet = 0;
    v6 = "Failed to initialize COM";
    v7 = 1017;
LABEL_3:
    WusaLogDebugEventA(L"InstallWorker", v7, v6);
    goto LABEL_184;
  }
  v39 = 0;
  v4 = 0;
  WusaPostMessage(0x403u, 0, v3);
  AllFilesFromCabinet = WusaMountOrExtractAllFilesFromCabinet(TargetPath, pszPath, (int *)&v41);
  if ( AllFilesFromCabinet < 0 )
  {
    WusaLogDebugEventA(L"InstallWorker", 1027, "Failed to extract the MSU %S", pszPath);
    goto LABEL_184;
  }
  dword_140020180 = (int)v41;
  AllFilesFromCabinet = CoCreateInstance(
                          &GUID_f8d253d9_89a4_4daa_87b6_1168369f0b21,
                          0,
                          1u,
                          &GUID_23857e3c_02ba_44a3_9423_b1c900805f37,
                          &ppv);
  if ( AllFilesFromCabinet < 0 )
  {
    v6 = "Failed to get IUpdateServiceManager interface";
    v7 = 1040;
    goto LABEL_3;
  }
  AllFilesFromCabinet = (*(__int64 (__fastcall **)(LPVOID, LPCWSTR, __int64, _QWORD, __int64 *))(*(_QWORD *)ppv + 96LL))(
                          ppv,
                          lpWindowName,
                          qword_1400201B8,
                          0,
                          &v64);
  if ( AllFilesFromCabinet < 0 )
  {
    v6 = "Failed to add scan package service";
    v7 = 1047;
    goto LABEL_3;
  }
  AllFilesFromCabinet = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v64 + 120LL))(v64, &v46);
  if ( AllFilesFromCabinet < 0 )
  {
    v6 = "Failed to get service ID for scan package service";
    v7 = 1050;
    goto LABEL_3;
  }
  AllFilesFromCabinet = CoCreateInstance(
                          &GUID_4cb43d7f_7eee_4906_8698_60da1c38f2fe,
                          0,
                          1u,
                          &GUID_816858a4_260d_4260_933a_2585f1abc76b,
                          &v55);
  if ( AllFilesFromCabinet < 0 )
  {
    v6 = "Failed to get IUpdateSession interface";
    v7 = 1056;
    goto LABEL_3;
  }
  v8 = SysAllocString(L"wusa");
  v36 = v8;
  v1 = v8;
  if ( !v8 )
  {
    WusaLogDebugEventA(L"InstallWorker", 1059, "Failed to allocate client application ID");
LABEL_16:
    AllFilesFromCabinet = -2147024882;
    goto LABEL_184;
  }
  AllFilesFromCabinet = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)v55 + 64LL))(v55, v8);
  if ( AllFilesFromCabinet < 0 )
  {
    v6 = "Failed to set client application ID";
    v7 = 1062;
    goto LABEL_3;
  }
  AllFilesFromCabinet = (*(__int64 (__fastcall **)(LPVOID, struct IUpdateSearcher **))(*(_QWORD *)v55 + 96LL))(
                          v55,
                          &v53);
  if ( AllFilesFromCabinet < 0 )
  {
    v6 = "Failed to create a searcher object";
    v7 = 1076;
    goto LABEL_3;
  }
  AllFilesFromCabinet = ((__int64 (__fastcall *)(struct IUpdateSearcher *, __int64))v53->lpVtbl->put_ServerSelection)(
                          v53,
                          3);
  if ( AllFilesFromCabinet < 0 )
  {
    v6 = "Failed to set offline scab cab as the search server";
    v7 = 1080;
    goto LABEL_3;
  }
  AllFilesFromCabinet = ((__int64 (__fastcall *)(struct IUpdateSearcher *, BSTR))v53->lpVtbl->put_ServiceID)(v53, v46);
  if ( AllFilesFromCabinet < 0 )
  {
    v6 = "Failed to set the service ID";
    v7 = 1086;
    goto LABEL_3;
  }
  v9 = L"IsAssigned=1 and ";
  if ( v46 )
    v9 = &pwszReason;
  AllFilesFromCabinet = StringCchPrintfW(psz, 0xC8u, L"%lsDeploymentAction='Installation'", v9);
  if ( AllFilesFromCabinet < 0 )
  {
    v6 = "Failed to build search criteria";
    v7 = 1092;
    goto LABEL_3;
  }
  hMem = SysAllocString(psz);
  v2 = (unsigned __int16 *)hMem;
  if ( !hMem )
  {
    WusaLogDebugEventA(L"InstallWorker", 1095, "Failed to allocate BSTR for search criteria");
    goto LABEL_16;
  }
  WusaLogDebugEventA(L"InstallWorker", 1097, "Start of search");
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  WusaPostMessage(0x400u, 0, v10);
  v11 = -1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WUSARebaseMultiMSU>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WUSARebaseMultiMSU>::GetImpl'::`2'::impl) )
  {
    LOBYTE(v38[0]) = 0;
    bstrString = (BSTR)&pv;
    pv.Ptr = 0;
    v12 = 0;
    *(_QWORD *)&pv.Size = 0;
    v50 = 0;
    v51 = 1;
    RelatedMSUFiles = WusaFindRelatedMSUFiles(&v50, (unsigned __int16 ***)&pv);
    if ( v51 )
      *((_QWORD *)bstrString + 1) = v50;
    if ( RelatedMSUFiles < 0 )
      WusaLogDebugEventA(
        L"InstallWorker",
        1123,
        "Failed to find related MSU files. Continue evaluation without related msu files. Error code 0X%x",
        RelatedMSUFiles);
    v14 = 0;
    while ( 1 )
    {
      v41 = 0;
      bstrString = 0;
      v15 = SearchUpdates(v53, v2, &bstrString, &v41);
      AllFilesFromCabinet = v15;
      if ( v15 < 0 )
        break;
      if ( v15 )
        goto LABEL_65;
      v16 = v41;
      if ( v12 || (v17 = EvaluateContentApplicabilityForUUP(v41), AllFilesFromCabinet = v17, v17 >= 0) )
      {
        v42 = bstrString;
        v47 = v16;
LABEL_62:
        wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>(&pv);
        v2 = (unsigned __int16 *)hMem;
        v11 = -1;
        v4 = v39;
        goto LABEL_63;
      }
      WusaLogDebugEventA(L"InstallWorker", 1159, "Evaluate Content Applicability failed. Error code 0X%x", v17);
      if ( AllFilesFromCabinet == -2146498504 || AllFilesFromCabinet == -2145124329 )
      {
        if ( v16 )
          ((void (__fastcall *)(struct IUpdateCollection *))v16->lpVtbl->Release)(v16);
        if ( bstrString )
          SysFreeString(bstrString);
        wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>(&pv);
        v4 = v39;
        goto LABEL_182;
      }
      if ( *(_QWORD *)&pv.Size )
      {
        Ptr = (void **)pv.Ptr;
        if ( pv.Ptr )
        {
          v19 = pv.Ptr + 8LL * *(_QWORD *)&pv.Size;
          if ( pv.Ptr != v19 )
          {
            do
            {
              v20 = *Ptr;
              LastError = GetLastError();
              CoTaskMemFree(v20);
              SetLastError(LastError);
              ++Ptr;
            }
            while ( Ptr != (void **)v19 );
            Ptr = (void **)pv.Ptr;
            v12 = v38[0];
          }
          CoTaskMemFree(Ptr);
          pv.Ptr = 0;
          *(_QWORD *)&pv.Size = 0;
        }
      }
      else
      {
        v12 = 1;
        LOBYTE(v38[0]) = 1;
      }
      if ( v16 )
        ((void (__fastcall *)(struct IUpdateCollection *))v16->lpVtbl->Release)(v16);
      if ( bstrString )
        SysFreeString(bstrString);
      v2 = (unsigned __int16 *)hMem;
      if ( ++v14 >= 3 )
        goto LABEL_62;
    }
    WusaLogDebugEventA(L"InstallWorker", 1147, "Failed to search updates. Error code 0X%x", v15);
LABEL_65:
    if ( v41 )
      ((void (__fastcall *)(struct IUpdateCollection *))v41->lpVtbl->Release)(v41);
    if ( bstrString )
      SysFreeString(bstrString);
    wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>(&pv);
    v4 = v39;
    goto LABEL_183;
  }
  AllFilesFromCabinet = ((__int64 (__fastcall *)(struct IUpdateSearcher *, HLOCAL, __int64 *))v53->lpVtbl->Search)(
                          v53,
                          hMem,
                          &v57);
  if ( AllFilesFromCabinet < 0 )
  {
    v23 = "Failed to begin search";
    v24 = 1178;
    goto LABEL_73;
  }
  WusaLogDebugEventA(L"InstallWorker", 1180, "End of search");
  if ( dword_1400201AC )
  {
    AllFilesFromCabinet = -2147023673;
    v23 = "Failed; user cancelled the install";
    v24 = 1185;
    goto LABEL_73;
  }
  LODWORD(v41) = 4;
  AllFilesFromCabinet = (*(__int64 (__fastcall **)(__int64, struct IUpdateCollection **))(*(_QWORD *)v57 + 56LL))(
                          v57,
                          &v41);
  if ( AllFilesFromCabinet < 0 )
  {
    v23 = "Failed to get search result code";
    v24 = 1192;
    goto LABEL_73;
  }
  v25 = (int)v41;
  if ( (_DWORD)v41 != 2 )
  {
    if ( (_DWORD)v41 != 3 )
    {
      if ( (_DWORD)v41 == 5 )
      {
        AllFilesFromCabinet = -2147023673;
LABEL_95:
        WusaLogDebugEventA(L"InstallWorker", 1246, "Failed. Search result code is %u", v25);
        goto LABEL_183;
      }
LABEL_94:
      AllFilesFromCabinet = -2147467259;
      goto LABEL_95;
    }
    v39 = 0;
    AllFilesFromCabinet = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v57 + 80LL))(v57, &v63);
    if ( AllFilesFromCabinet < 0 )
    {
      v23 = "Failed to get search warnings";
      v24 = 1214;
      goto LABEL_73;
    }
    AllFilesFromCabinet = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v63 + 72LL))(v63, &v39);
    if ( AllFilesFromCabinet < 0 )
    {
      v23 = "Failed to get warning count";
      v24 = 1217;
      goto LABEL_73;
    }
    v26 = 0;
    if ( v39 <= 0 )
    {
LABEL_93:
      v25 = (int)v41;
      v2 = (unsigned __int16 *)hMem;
      goto LABEL_94;
    }
    while ( 1 )
    {
      LODWORD(bstrString) = 0;
      if ( v56 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
        v56 = 0;
      }
      AllFilesFromCabinet = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v63 + 56LL))(
                              v63,
                              v26,
                              &v56);
      if ( AllFilesFromCabinet < 0 )
        break;
      AllFilesFromCabinet = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v56 + 64LL))(v56, &bstrString);
      if ( AllFilesFromCabinet < 0 )
      {
        WusaLogDebugEventA(L"InstallWorker", 1229, "Failed to get warning HRESULT");
        goto LABEL_182;
      }
      if ( (_DWORD)bstrString == -2145116137 )
      {
        AllFilesFromCabinet = -2145116137;
        WusaLogDebugEventA(L"InstallWorker", 1236, "Update requires new servicing stack");
        goto LABEL_182;
      }
      if ( (int)++v26 >= v39 )
        goto LABEL_93;
    }
    WusaLogDebugEventA(L"InstallWorker", 1226, "Failed to get warning");
    goto LABEL_182;
  }
  AllFilesFromCabinet = (*(__int64 (__fastcall **)(__int64, struct IUpdateCollection **))(*(_QWORD *)v57 + 72LL))(
                          v57,
                          &v47);
  if ( AllFilesFromCabinet < 0 )
  {
    v23 = "Failed to get update collection from search result";
    v24 = 1249;
    goto LABEL_73;
  }
  AllFilesFromCabinet = ((__int64 (__fastcall *)(struct IUpdateCollection *, int *))v47->lpVtbl->get_Count)(v47, &v58);
  if ( AllFilesFromCabinet < 0 )
  {
    v23 = "Failed to get count of updates to install";
    v24 = 1252;
    goto LABEL_73;
  }
  if ( v58 > 1 )
  {
    AllFilesFromCabinet = -2147467259;
    v23 = "There should be only one update to install";
    v24 = 1257;
    goto LABEL_73;
  }
  if ( v58 <= 0 )
  {
    WusaLogDebugEventA(L"InstallWorker", 1262, "There is no update bundle to install");
    if ( (int)WusaMessageBox(0xEA64u, 0xEA60u, 1, (PCWSTR)0xFFFE, 0) < 0 )
      WusaLogDebugEventA(L"InstallWorker", 1266, "Failed to display no-update message box");
    AllFilesFromCabinet = -2145124329;
    goto LABEL_183;
  }
  AllFilesFromCabinet = ((__int64 (__fastcall *)(struct IUpdateCollection *, _QWORD, __int64 *))v47->lpVtbl->get_Item)(
                          v47,
                          0,
                          &v60);
  if ( AllFilesFromCabinet < 0 )
  {
    v23 = "Failed to get update out of collection";
    v24 = 1274;
    goto LABEL_73;
  }
  AllFilesFromCabinet = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v60 + 56LL))(v60, &v42);
  if ( AllFilesFromCabinet < 0 )
  {
    v23 = "Failed to get update title";
    v24 = 1277;
    goto LABEL_73;
  }
  v38[0] = 0;
  AllFilesFromCabinet = (*(__int64 (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v60 + 208LL))(v60, v38);
  if ( AllFilesFromCabinet < 0 )
  {
    v23 = "Failed to query whether update is already installed";
    v24 = 1281;
    goto LABEL_73;
  }
  if ( v38[0] == 0xFFFF )
  {
    WusaLogDebugEventA(L"InstallWorker", 1285, "Update is already installed");
    if ( (int)WusaMessageBox(0xEA6Eu, 0xEA60u, 1, (PCWSTR)0xFFFF, 0, v42) < 0 )
      WusaLogDebugEventA(L"InstallWorker", 1289, "Failed to display update-installed message box");
    AllFilesFromCabinet = 2359302;
    goto LABEL_183;
  }
LABEL_63:
  AllFilesFromCabinet = AppModule::SetUpdateTitle(v22, v42);
  if ( AllFilesFromCabinet >= 0 )
  {
    v59 = 6;
    AllFilesFromCabinet = WusaMessageBox(0xEA66u, 0xEA60u, 6, (PCWSTR)0xFFFD, &v59, v42);
    if ( AllFilesFromCabinet < 0 )
    {
      v23 = "Failed to display welcome";
      v24 = 1307;
      goto LABEL_73;
    }
    if ( v59 == 7 )
    {
      AllFilesFromCabinet = -2147023673;
      WusaLogDebugEventA(L"InstallWorker", 1312, "Failed; user cancelled the installation");
      goto LABEL_183;
    }
    WusaLogDebugEventA(L"InstallWorker", 1319, "Starting to copy payload");
    AllFilesFromCabinet = CopyToCache(v47, 0);
    if ( AllFilesFromCabinet < 0 )
    {
      v23 = "Failed to copy the offline update to WU's cache";
      v24 = 1322;
      goto LABEL_73;
    }
    AppModule::DeleteSandBox((AppModule *)&_Module);
    WusaLogDebugEventA(L"InstallWorker", 1341, "End of copying payload");
    v27 = lpData;
    if ( lpData )
    {
      v28 = 0x7FFFFFFF;
      do
      {
        if ( !*(_WORD *)v27 )
          break;
        v27 += 2;
        --v28;
      }
      while ( v28 );
      AllFilesFromCabinet = v28 == 0 ? 0x80070057 : 0;
      v29 = (0x7FFFFFFF - v28) & -(__int64)(v28 != 0);
      if ( v28 )
      {
        AllFilesFromCabinet = RegCreateKeyExW(
                                HKEY_LOCAL_MACHINE,
                                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WUSA",
                                0,
                                0,
                                0,
                                2u,
                                0,
                                &hKey,
                                0);
        if ( AllFilesFromCabinet )
        {
          WusaLogDebugEventA(L"InstallWorker", 1355, "Failed to create registry key");
        }
        else
        {
          AllFilesFromCabinet = RegSetValueExW(hKey, L"WUSACommandLine", 0, 1u, lpData, 2 * v29 + 2);
          if ( !AllFilesFromCabinet )
          {
            AllFilesFromCabinet = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v55 + 112LL))(v55, &v54);
            if ( AllFilesFromCabinet >= 0 )
            {
              AllFilesFromCabinet = (*(__int64 (__fastcall **)(__int64, struct IUpdateCollection *))(*(_QWORD *)v54 + 128LL))(
                                      v54,
                                      v47);
              if ( AllFilesFromCabinet >= 0 )
              {
                WusaLogDebugEventA(L"InstallWorker", 1366, "Start of install");
                AllFilesFromCabinet = BlockShutDown();
                if ( AllFilesFromCabinet >= 0 )
                {
                  if ( dword_140020188 )
                  {
                    AllFilesFromCabinet = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v54 + 168LL))(
                                            v54,
                                            &v48);
                    if ( AllFilesFromCabinet < 0 )
                    {
                      WusaLogDebugEventA(L"InstallWorker", 1374, "Failed to install update");
                      goto LABEL_182;
                    }
                  }
                  else
                  {
                    ShowWindow(hWndParent, 0);
                    AllFilesFromCabinet = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v54 + 176LL))(
                                            v54,
                                            0,
                                            &v48);
                    if ( AllFilesFromCabinet < 0 )
                    {
                      WusaLogDebugEventA(L"InstallWorker", 1383, "Failed to run wizard");
                      goto LABEL_182;
                    }
                    dword_14002021C = 1;
                  }
                  WusaLogDebugEventA(L"InstallWorker", 1389, "End of install");
                  v52 = -2147467259;
                  v43 = 4;
                  v44 = 4;
                  v45 = -2147467259;
                  AllFilesFromCabinet = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v48 + 72LL))(v48, &v43);
                  if ( AllFilesFromCabinet >= 0 )
                  {
                    AllFilesFromCabinet = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v48 + 56LL))(v48, &v52);
                    if ( AllFilesFromCabinet >= 0 )
                    {
                      AllFilesFromCabinet = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v48 + 80LL))(
                                              v48,
                                              0,
                                              &v61);
                      if ( AllFilesFromCabinet >= 0 )
                      {
                        AllFilesFromCabinet = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v61 + 56LL))(
                                                v61,
                                                &v45);
                        if ( AllFilesFromCabinet >= 0 )
                        {
                          AllFilesFromCabinet = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v61 + 72LL))(
                                                  v61,
                                                  &v44);
                          if ( AllFilesFromCabinet >= 0 )
                          {
                            WusaLogDebugEventA(
                              L"InstallWorker",
                              1429,
                              "OperationResultCode of the installation: 0X%x\tHRESULT of the installation: 0X%x\tOperatio"
                              "nResultCode of the update: 0X%x\tHRESULT of the update: 0X%x",
                              v43,
                              v52,
                              v44,
                              v45);
                            if ( v43 != 2 || (v30 = 0, v44 != 2) )
                            {
                              if ( v43 == 5 || v44 == 5 )
                              {
                                v30 = -2147023673;
                              }
                              else
                              {
                                v30 = v45;
                                if ( v52 < 0 )
                                {
                                  if ( v45 >= 0 )
                                    v30 = v52;
                                }
                                else if ( v45 >= 0 )
                                {
                                  v30 = -2147467259;
                                  WusaLogDebugEventA(
                                    L"InstallWorker",
                                    1445,
                                    "Warning. WUA error code are inconsistent: HRESULT of the update and the installation"
                                    " both indicate sucess while operation result code indicates error.");
                                }
                              }
                            }
                            v40 = 0;
                            AllFilesFromCabinet = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v48 + 64LL))(
                                                    v48,
                                                    &v40);
                            if ( AllFilesFromCabinet >= 0 )
                            {
                              if ( v40 == -1 )
                              {
                                dword_140020250 = 1;
                                WusaLogDebugEventA(L"InstallWorker", 1468, "Reboot was required for update %ls", v42);
                                CommandLineW = GetCommandLineW();
                                pv.Ptr = (ULONGLONG)v42;
                                v32 = -1;
                                do
                                  ++v32;
                                while ( v42[v32] );
                                *(_QWORD *)&pv.Size = (unsigned int)(2 * v32 + 2);
                                v68 = CommandLineW;
                                do
                                  ++v11;
                                while ( CommandLineW[v11] );
                                v69 = 2 * v11 + 2;
                                v70 = 0;
                                EventWrite(RegHandle, &WUSA_EVENT_INSTALLREBOOTREQUIRED, 2u, &pv);
                              }
                              else if ( dword_140020194 == 2 )
                              {
                                dword_140020250 = 1;
                              }
                              dword_14002024C = v30;
                              AllFilesFromCabinet = v30;
                              if ( v30 < 0 )
                                WusaLogDebugEventA(L"InstallWorker", 1478, "Failed install update %S", v42);
                            }
                            else
                            {
                              WusaLogDebugEventA(L"InstallWorker", 1463, "Failed to get reboot requirement");
                            }
                          }
                          else
                          {
                            WusaLogDebugEventA(L"InstallWorker", 1423, "Failed to get update result code");
                          }
                        }
                        else
                        {
                          WusaLogDebugEventA(L"InstallWorker", 1420, "Failed to get update HResult");
                        }
                      }
                      else
                      {
                        WusaLogDebugEventA(L"InstallWorker", 1416, "Failed to get IUpdateInstallationResult interface");
                      }
                    }
                    else
                    {
                      WusaLogDebugEventA(L"InstallWorker", 1412, "Failed to get install HResult");
                    }
                  }
                  else
                  {
                    WusaLogDebugEventA(L"InstallWorker", 1409, "Failed to get install result code");
                  }
                  goto LABEL_182;
                }
                WusaLogDebugEventA(L"InstallWorker", 1369, "Failed to block Operation System shutdown");
              }
              else
              {
                WusaLogDebugEventA(L"InstallWorker", 1364, "Failed to tell installer what update to install");
              }
            }
            else
            {
              WusaLogDebugEventA(L"InstallWorker", 1361, "Failed to create UpdateInstaller object");
            }
LABEL_182:
            v2 = (unsigned __int16 *)hMem;
            goto LABEL_183;
          }
          WusaLogDebugEventA(L"InstallWorker", 1358, "Failed to set command line registry value");
        }
        if ( AllFilesFromCabinet > 0 )
          AllFilesFromCabinet = (unsigned __int16)AllFilesFromCabinet | 0x80070000;
        goto LABEL_182;
      }
    }
    else
    {
      AllFilesFromCabinet = -2147024809;
    }
    WusaLogDebugEventA(L"InstallWorker", 1352, "Failed to get the length of ignored arguments");
    goto LABEL_182;
  }
  v23 = "Failed to set update title";
  v24 = 1302;
LABEL_73:
  WusaLogDebugEventA(L"InstallWorker", v24, v23);
LABEL_183:
  v1 = v36;
LABEL_184:
  v33 = v46;
  if ( v46 )
  {
    if ( (*(int (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 80LL))(ppv) < 0 )
      WusaLogDebugEventA(L"InstallWorker", 1487, "Failed to remove package scan service from service manager %ls", v46);
    v33 = v46;
  }
  if ( v2 )
  {
    SysFreeString(v2);
    v33 = v46;
  }
  if ( v33 )
  {
    SysFreeString(v33);
    v46 = 0;
  }
  if ( v1 )
    SysFreeString(v1);
  if ( v42 )
  {
    SysFreeString(v42);
    v42 = 0;
  }
  if ( v47 )
  {
    ((void (__fastcall *)(struct IUpdateCollection *))v47->lpVtbl->Release)(v47);
    v47 = 0;
  }
  if ( v60 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
    v60 = 0;
  }
  if ( v54 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    v54 = 0;
  }
  if ( v61 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
    v61 = 0;
  }
  if ( v48 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    v48 = 0;
  }
  if ( v53 )
  {
    ((void (__fastcall *)(struct IUpdateSearcher *))v53->lpVtbl->Release)(v53);
    v53 = 0;
  }
  if ( v55 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v55 + 16LL))(v55);
    v55 = 0;
  }
  if ( v64 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
    v64 = 0;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WUSARebaseMultiMSU>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WUSARebaseMultiMSU>::GetImpl'::`2'::impl) )
  {
    if ( v56 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
      v56 = 0;
    }
    if ( v63 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
      v63 = 0;
    }
    if ( v57 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
      v57 = 0;
    }
  }
  if ( !v4 )
    CoUninitialize();
  if ( AllFilesFromCabinet < 0 )
  {
    hMem = 0;
    WusaGetErrorMessage(AllFilesFromCabinet, (unsigned __int16 **)&hMem);
    v34 = hMem;
    WusaLogDebugEventA(
      L"InstallWorker",
      1525,
      "Exit with error code 0X%x (%ls)",
      AllFilesFromCabinet,
      (const wchar_t *)hMem);
    if ( v34 )
      LocalFree(v34);
  }
  return (unsigned int)AllFilesFromCabinet;
}

```

## disassembly

```asm
0x1400075b0  push    rbp
0x1400075b2  push    rbx
0x1400075b3  push    rsi
0x1400075b4  push    rdi
0x1400075b5  push    r12
0x1400075b7  push    r13
0x1400075b9  push    r14
0x1400075bb  push    r15
0x1400075bd  lea     rbp, [rsp-208h]
0x1400075c5  sub     rsp, 308h
0x1400075cc  mov     rax, cs:__security_cookie
0x1400075d3  xor     rax, rsp
0x1400075d6  mov     [rbp+240h+var_50], rax
0x1400075dd  xor     r12d, r12d
0x1400075e0  xor     ecx, ecx; pvReserved
0x1400075e2  mov     dword ptr [rsp+340h+var_2D0], r12d
0x1400075e7  mov     esi, r12d
0x1400075ea  mov     [rbp+240h+var_240], r12
0x1400075ee  mov     ebx, r12d
0x1400075f1  mov     [rbp+240h+var_230], r12
0x1400075f5  lea     edx, [r12+2]; dwCoInit
0x1400075fa  mov     [rbp+240h+var_270], r12
0x1400075fe  mov     [rbp+240h+var_280], r12
0x140007602  mov     [rbp+240h+var_278], r12
0x140007606  mov     [rbp+240h+var_260], r12
0x14000760a  mov     [rbp+240h+var_2A0], r12
0x14000760e  mov     [rbp+240h+var_248], r12
0x140007612  mov     [rbp+240h+var_2A8], r12
0x140007616  mov     [rbp+240h+var_250], r12
0x14000761a  mov     [rbp+240h+var_238], r12
0x14000761e  mov     [rbp+240h+var_268], r12
0x140007622  mov     [rbp+240h+var_2B0], r12
0x140007626  mov     [rsp+340h+var_2C8], r12
0x14000762b  mov     [rbp+240h+hKey], r12
0x14000762f  mov     [rbp+240h+var_258], r12d
0x140007633  call    cs:__imp_CoInitializeEx
0x140007639  mov     r15d, eax
0x14000763c  test    eax, eax
0x14000763e  jns     short loc_140007663
0x140007640  mov     edi, r12d
0x140007643  lea     r8, aFailedToInitia_2; "Failed to initialize COM"
0x14000764a  mov     edx, 3F9h
0x14000764f  lea     r14, aInstallworker; "InstallWorker"
0x140007656  mov     rcx, r14
0x140007659  call    WusaLogDebugEventA
0x14000765e  jmp     loc_1400084B0
0x140007663  mov     r14d, 403h
0x140007669  mov     [rsp+340h+var_2DC], r12d
0x14000766e  mov     ecx, r14d; Msg
0x140007671  xor     edx, edx; wParam
0x140007673  mov     r15d, r12d
0x140007676  call    ?WusaPostMessage@@YAXI_K_J@Z; WusaPostMessage(uint,unsigned __int64,__int64)
0x14000767b  mov     rdx, cs:pszPath; pszPath
0x140007682  lea     r8, [rsp+340h+var_2D0]; int *
0x140007687  mov     rcx, cs:TargetPath; TargetPath
0x14000768e  call    ?WusaMountOrExtractAllFilesFromCabinet@@YAJPEBG0PEAH@Z; WusaMountOrExtractAllFilesFromCabinet(ushort const *,ushort const *,int *)
0x140007693  mov     edi, eax
0x140007695  test    eax, eax
0x140007697  jns     short loc_1400076BE
0x140007699  mov     r9, cs:pszPath
0x1400076a0  lea     r8, aFailedToExtrac_0; "Failed to extract the MSU %S"
0x1400076a7  mov     edx, r14d
0x1400076aa  lea     r14, aInstallworker; "InstallWorker"
0x1400076b1  mov     rcx, r14
0x1400076b4  call    WusaLogDebugEventA
0x1400076b9  jmp     loc_1400084B0
0x1400076be  mov     eax, dword ptr [rsp+340h+var_2D0]
0x1400076c2  lea     r9, _GUID_23857e3c_02ba_44a3_9423_b1c900805f37; riid
0x1400076c9  mov     cs:dword_140020180, eax
0x1400076cf  lea     rcx, _GUID_f8d253d9_89a4_4daa_87b6_1168369f0b21; rclsid
0x1400076d6  lea     rax, [rbp+240h+var_240]
0x1400076da  mov     r13d, 1
0x1400076e0  mov     r8d, r13d; dwClsContext
0x1400076e3  mov     [rsp+340h+ppv], rax; ppv
0x1400076e8  xor     edx, edx; pUnkOuter
0x1400076ea  call    cs:__imp_CoCreateInstance
0x1400076f0  mov     edi, eax
0x1400076f2  test    eax, eax
0x1400076f4  jns     short loc_140007707
0x1400076f6  lea     r8, aFailedToGetIup_2; "Failed to get IUpdateServiceManager int"...
0x1400076fd  mov     edx, 410h
0x140007702  jmp     loc_14000764F
0x140007707  mov     rcx, [rbp+240h+var_240]
0x14000770b  lea     rdx, [rbp+240h+var_230]
0x14000770f  mov     r8, cs:qword_1400201B8
0x140007716  xor     r9d, r9d
0x140007719  mov     [rsp+340h+ppv], rdx
0x14000771e  mov     rdx, cs:lpWindowName
0x140007725  mov     rax, [rcx]
0x140007728  mov     rax, [rax+60h]
0x14000772c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007731  mov     edi, eax
0x140007733  test    eax, eax
0x140007735  jns     short loc_140007748
0x140007737  lea     r8, aFailedToAddSca; "Failed to add scan package service"
0x14000773e  mov     edx, 417h
0x140007743  jmp     loc_14000764F
0x140007748  mov     rcx, [rbp+240h+var_230]
0x14000774c  lea     rdx, [rbp+240h+var_2B0]
0x140007750  mov     rax, [rcx]
0x140007753  mov     rax, [rax+78h]
0x140007757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000775c  mov     edi, eax
0x14000775e  test    eax, eax
0x140007760  jns     short loc_140007773
0x140007762  lea     r8, aFailedToGetSer; "Failed to get service ID for scan packa"...
0x140007769  mov     edx, 41Ah
0x14000776e  jmp     loc_14000764F
0x140007773  lea     rax, [rbp+240h+var_270]
0x140007777  mov     r8d, r13d; dwClsContext
0x14000777a  lea     r9, _GUID_816858a4_260d_4260_933a_2585f1abc76b; riid
0x140007781  mov     [rsp+340h+ppv], rax; ppv
0x140007786  xor     edx, edx; pUnkOuter
0x140007788  lea     rcx, _GUID_4cb43d7f_7eee_4906_8698_60da1c38f2fe; rclsid
0x14000778f  call    cs:__imp_CoCreateInstance
0x140007795  mov     edi, eax
0x140007797  test    eax, eax
0x140007799  jns     short loc_1400077AC
0x14000779b  lea     r8, aFailedToGetIup_0; "Failed to get IUpdateSession interface"
0x1400077a2  mov     edx, 420h
0x1400077a7  jmp     loc_14000764F
0x1400077ac  lea     rcx, psz; "wusa"
0x1400077b3  call    cs:__imp_SysAllocString
0x1400077b9  mov     [rsp+340h+var_2F0], rax
0x1400077be  mov     rsi, rax
0x1400077c1  test    rax, rax
0x1400077c4  jnz     short loc_1400077EB
0x1400077c6  lea     r14, aInstallworker; "InstallWorker"
0x1400077cd  mov     edx, 423h
0x1400077d2  mov     rcx, r14
0x1400077d5  lea     r8, aFailedToAlloca_12; "Failed to allocate client application I"...
0x1400077dc  call    WusaLogDebugEventA
0x1400077e1  mov     edi, 8007000Eh
0x1400077e6  jmp     loc_1400084B0
0x1400077eb  mov     rcx, [rbp+240h+var_270]
0x1400077ef  mov     rdx, rsi
0x1400077f2  mov     rax, [rcx]
0x1400077f5  mov     rax, [rax+40h]
0x1400077f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400077fe  mov     edi, eax
0x140007800  test    eax, eax
0x140007802  jns     short loc_140007815
0x140007804  lea     r8, aFailedToSetCli; "Failed to set client application ID"
0x14000780b  mov     edx, 426h
0x140007810  jmp     loc_14000764F
0x140007815  mov     rcx, [rbp+240h+var_270]
0x140007819  lea     rdx, [rbp+240h+var_280]
0x14000781d  mov     rax, [rcx]
0x140007820  mov     rax, [rax+60h]
0x140007824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007829  mov     edi, eax
0x14000782b  test    eax, eax
0x14000782d  jns     short loc_140007840
0x14000782f  lea     r8, aFailedToCreate_4; "Failed to create a searcher object"
0x140007836  mov     edx, 434h
0x14000783b  jmp     loc_14000764F
0x140007840  mov     rcx, [rbp+240h+var_280]
0x140007844  mov     edx, 3
0x140007849  mov     rax, [rcx]
0x14000784c  mov     rax, [rax+70h]
0x140007850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007855  mov     edi, eax
0x140007857  test    eax, eax
0x140007859  jns     short loc_14000786C
0x14000785b  lea     r8, aFailedToSetOff; "Failed to set offline scab cab as the s"...
0x140007862  mov     edx, 438h
0x140007867  jmp     loc_14000764F
0x14000786c  mov     rcx, [rbp+240h+var_280]
0x140007870  mov     rdx, [rbp+240h+var_2B0]
0x140007874  mov     rax, [rcx]
0x140007877  mov     rax, [rax+0C0h]
0x14000787e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007883  mov     edi, eax
0x140007885  test    eax, eax
0x140007887  jns     short loc_14000789A
0x140007889  lea     r8, aFailedToSetThe; "Failed to set the service ID"
0x140007890  mov     edx, 43Eh
0x140007895  jmp     loc_14000764F
0x14000789a  cmp     [rbp+240h+var_2B0], r12
0x14000789e  lea     rax, pwszReason
0x1400078a5  lea     r9, aIsassigned1And; "IsAssigned=1 and "
0x1400078ac  mov     edx, 0C8h; unsigned __int64
0x1400078b1  cmovnz  r9, rax
0x1400078b5  lea     r8, aLsdeploymentac; "%lsDeploymentAction='Installation'"
0x1400078bc  lea     rcx, [rbp+240h+psz]; unsigned __int16 *
0x1400078c0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400078c5  mov     edi, eax
0x1400078c7  test    eax, eax
0x1400078c9  jns     short loc_1400078DC
0x1400078cb  lea     r8, aFailedToBuildS; "Failed to build search criteria"
0x1400078d2  mov     edx, 444h
0x1400078d7  jmp     loc_14000764F
0x1400078dc  lea     rcx, [rbp+240h+psz]; psz
0x1400078e0  call    cs:__imp_SysAllocString
0x1400078e6  mov     [rsp+340h+hMem], rax
0x1400078eb  lea     r14, aInstallworker; "InstallWorker"
0x1400078f2  mov     rbx, rax
0x1400078f5  mov     rcx, r14
0x1400078f8  test    rax, rax
0x1400078fb  jnz     short loc_14000790E
0x1400078fd  lea     r8, aFailedToAlloca_13; "Failed to allocate BSTR for search crit"...
0x140007904  mov     edx, 447h
0x140007909  jmp     loc_1400077DC
0x14000790e  lea     r8, aStartOfSearch; "Start of search"
0x140007915  mov     edx, 449h
0x14000791a  call    WusaLogDebugEventA
0x14000791f  xorps   xmm0, xmm0
0x140007922  lea     rcx, [rbp+240h+pvarg]; pvarg
0x140007926  xor     eax, eax
0x140007928  movups  xmmword ptr [rbp+240h+pvarg], xmm0
0x14000792c  mov     qword ptr [rbp+240h+pvarg+10h], rax
0x140007930  call    cs:__imp_VariantInit
0x140007936  xor     edx, edx; wParam
0x140007938  mov     ecx, 400h; Msg
0x14000793d  call    ?WusaPostMessage@@YAXI_K_J@Z; WusaPostMessage(uint,unsigned __int64,__int64)
0x140007942  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WUSARebaseMultiMSU@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WUSARebaseMultiMSU@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WUSARebaseMultiMSU> `wil::Feature<__WilFeatureTraits_Feature_WUSARebaseMultiMSU>::GetImpl(void)'::`2'::impl
0x140007949  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WUSARebaseMultiMSU@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WUSARebaseMultiMSU>::__private_IsEnabled(void)
0x14000794e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140007952  test    al, al
0x140007954  jz      loc_140007BAA
0x14000795a  lea     rax, [rbp+240h+pv]
0x14000795e  mov     byte ptr [rsp+340h+var_2E0], r12b
0x140007963  lea     rdx, [rbp+240h+pv]; unsigned __int16 ***
0x140007967  mov     [rbp+240h+bstrString], rax
0x14000796b  lea     rcx, [rbp+240h+var_290]; unsigned int *
0x14000796f  mov     [rbp+240h+pv], r12
0x140007973  mov     sil, r12b
0x140007976  mov     [rbp+240h+var_200], r12
0x14000797a  mov     [rbp+240h+var_290], r12d
0x14000797e  mov     [rbp+240h+var_28C], r13b
0x140007982  call    ?WusaFindRelatedMSUFiles@@YAJPEAKPEAPEAPEAG@Z; WusaFindRelatedMSUFiles(ulong *,ushort * * *)
0x140007987  cmp     [rbp+240h+var_28C], r12b
0x14000798b  jz      short loc_140007998
0x14000798d  mov     rcx, [rbp+240h+bstrString]
0x140007991  mov     edx, [rbp+240h+var_290]
0x140007994  mov     [rcx+8], rdx
0x140007998  test    eax, eax
0x14000799a  jns     short loc_1400079B3
0x14000799c  mov     r9d, eax
0x14000799f  lea     r8, aFailedToFindRe; "Failed to find related MSU files. Conti"...
0x1400079a6  mov     edx, 463h
0x1400079ab  mov     rcx, r14
0x1400079ae  call    WusaLogDebugEventA
0x1400079b3  mov     r13d, r12d
0x1400079b6  mov     rcx, [rbp+240h+var_280]; struct IUpdateSearcher *
0x1400079ba  lea     r9, [rsp+340h+var_2D0]; struct IUpdateCollection **
0x1400079bf  lea     r8, [rbp+240h+bstrString]; unsigned __int16 **
0x1400079c3  mov     [rsp+340h+var_2D0], r12
0x1400079c8  mov     rdx, rbx; unsigned __int16 *
0x1400079cb  mov     [rbp+240h+bstrString], r12
0x1400079cf  call    ?SearchUpdates@@YAJPEAUIUpdateSearcher@@PEAGPEAPEAGPEAPEAUIUpdateCollection@@@Z; SearchUpdates(IUpdateSearcher *,ushort *,ushort * *,IUpdateCollection * *)
0x1400079d4  mov     edi, eax
0x1400079d6  test    eax, eax
0x1400079d8  js      loc_140007B91
0x1400079de  jnz     loc_140007B59
0x1400079e4  mov     rbx, [rsp+340h+var_2D0]
0x1400079e9  test    sil, sil
0x1400079ec  jnz     loc_140007B0C
0x1400079f2  lea     rdx, [rbp+240h+pv]
0x1400079f6  mov     rcx, rbx; struct IUpdateCollection *
0x1400079f9  call    ?EvaluateContentApplicabilityForUUP@@YAJPEAUIUpdateCollection@@AEAV?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@@Z; EvaluateContentApplicabilityForUUP(IUpdateCollection *,wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64> &)
0x1400079fe  mov     edi, eax
0x140007a00  test    eax, eax
0x140007a02  jns     loc_140007B0C
0x140007a08  mov     r9d, eax
0x140007a0b  lea     r8, aEvaluateConten; "Evaluate Content Applicability failed. "...
0x140007a12  mov     edx, 487h
0x140007a17  mov     rcx, r14
0x140007a1a  call    WusaLogDebugEventA
0x140007a1f  cmp     edi, 800F0838h
0x140007a25  jz      loc_140007AD6
0x140007a2b  cmp     edi, 80240017h
0x140007a31  jz      loc_140007AD6
0x140007a37  mov     rax, [rbp+240h+var_200]
0x140007a3b  cmp     rax, 1
0x140007a3f  jb      short loc_140007A97
0x140007a41  mov     r15, [rbp+240h+pv]
0x140007a45  test    r15, r15
0x140007a48  jz      short loc_140007A9F
0x140007a4a  lea     r12, [r15+rax*8]
0x140007a4e  cmp     r15, r12
0x140007a51  jz      short loc_140007A81
0x140007a53  mov     rdi, [r15]
0x140007a56  call    cs:__imp_GetLastError
0x140007a5c  mov     rcx, rdi; pv
0x140007a5f  mov     esi, eax
0x140007a61  call    cs:__imp_CoTaskMemFree
0x140007a67  mov     ecx, esi; dwErrCode
0x140007a69  call    cs:__imp_SetLastError
0x140007a6f  add     r15, 8
0x140007a73  cmp     r15, r12
0x140007a76  jnz     short loc_140007A53
0x140007a78  mov     r15, [rbp+240h+pv]
0x140007a7c  mov     sil, byte ptr [rsp+340h+var_2E0]
0x140007a81  mov     rcx, r15; pv
0x140007a84  call    cs:__imp_CoTaskMemFree
0x140007a8a  xor     r12d, r12d
0x140007a8d  mov     [rbp+240h+pv], r12
0x140007a91  mov     [rbp+240h+var_200], r12
0x140007a95  jmp     short loc_140007A9F
  ... truncated ...
```
