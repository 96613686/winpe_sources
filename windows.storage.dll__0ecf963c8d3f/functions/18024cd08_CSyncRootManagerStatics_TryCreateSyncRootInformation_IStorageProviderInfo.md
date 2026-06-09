# CSyncRootManagerStatics::TryCreateSyncRootInformation(IStorageProviderInfo *)

- ea: `0x18024cd08`
- end: `0x18024d941`
- name: `?TryCreateSyncRootInformation@CSyncRootManagerStatics@@AEAA?AV?$com_ptr_t@UIStorageProviderSyncRootInfo@Provider@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@PEAUIStorageProviderInfo@@@Z`
- size: `3129`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18024c920`
- `0x18033d93c`

## callees

- `0x18000ee84`
- `0x18001c14c`
- `0x1800d13a0`
- `0x1801bdcb8`
- `0x1801dfea8`
- `0x1801dff1c`
- `0x1801dffa0`
- `0x1801f85b0`
- `0x18024cd08`
- `0x180253864`
- `0x18026c22c`
- `0x18028cd88`
- `0x18028f180`
- `0x1802e82c8`
- `0x1803061a0`
- `0x18035387c`
- `0x18035f4ec`
- `0x1803a4cb0`
- `0x1805318f8`
- `0x180628830`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18024ce4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18024ce4f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18024d3dd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18024d3dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18024d255`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18024d614`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18024d624`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18024d638`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18024d652`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18024d662`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18024d67d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18024d68d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18024d255`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18024d614`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18024d624`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18024d638`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18024d652`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18024d662`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18024d67d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18024d68d`
- `cldapi!CfGetSyncRootInfoByPath` at `0x18024d430`
- `cldapi!CfGetSyncRootInfoByPath` at `0x18024d430`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18024d2f4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18024d2f4`

## string_xrefs

- `0x18024d2d1`: `Windows.Foundation.Uri`

## pseudocode

```c
// Hidden C++ exception states: #wind=35
_QWORD *__fastcall CSyncRootManagerStatics::TryCreateSyncRootInformation(__int64 a1, _QWORD *a2, __int64 *a3)
{
  int v6; // eax
  __int64 v7; // rax
  int v8; // eax
  _QWORD *v9; // rdi
  __int64 (__fastcall *v10)(_QWORD *, _QWORD); // rbx
  __int64 v11; // rax
  int v12; // eax
  __int64 *v13; // rcx
  __int64 v14; // rax
  int v15; // ebx
  HANDLE CurrentProcess; // rax
  bool *v17; // r8
  void *v18; // rcx
  int StorageItemFromPath_FullTrustCaller_ForPackage; // eax
  void *v20; // rcx
  __int64 v21; // rdx
  void *v22; // rcx
  int v23; // eax
  __int64 v24; // rax
  int v25; // eax
  _QWORD *v26; // rdi
  __int64 (__fastcall *v27)(_QWORD *, _QWORD); // rbx
  __int64 v28; // rax
  int v29; // eax
  __int64 v30; // rax
  int v31; // eax
  _QWORD *v32; // rdi
  __int64 (__fastcall *v33)(_QWORD *, _QWORD); // rbx
  __int64 v34; // rax
  int v35; // eax
  int v36; // eax
  __int64 v37; // rdx
  int v38; // eax
  __int64 v39; // rax
  int v40; // eax
  __int64 v41; // rax
  int v42; // eax
  char *v43; // r14
  char *v44; // r12
  unsigned int v45; // edi
  __int64 v46; // rax
  int v47; // eax
  int v48; // eax
  __int64 v49; // rbx
  int v50; // eax
  __int64 (__fastcall *v51)(__int64, _QWORD); // rdi
  __int64 v52; // rax
  int v53; // eax
  int v54; // eax
  __int64 v55; // rax
  int v56; // eax
  int ActivationFactory; // eax
  LPVOID v58; // rdi
  __int64 (__fastcall *v59)(LPVOID, _QWORD, __int64 *); // rbx
  __int64 v60; // rax
  int v61; // eax
  int v62; // eax
  __int64 (__fastcall *v63)(__int64 *, __int64); // rbx
  __int64 v64; // rax
  int v65; // eax
  int v66; // eax
  _QWORD *v67; // rdi
  __int64 (__fastcall *v68)(_QWORD *, _QWORD); // rbx
  __int64 v69; // rax
  int v70; // eax
  _QWORD *v71; // rdi
  __int64 (__fastcall *v72)(_QWORD *, _QWORD); // rbx
  _QWORD *v73; // rax
  int v74; // eax
  __int64 v75; // rdx
  int v76; // eax
  __int64 v77; // rdx
  int v78; // eax
  __int64 v79; // rdx
  unsigned int v80; // eax
  __int64 v81; // r8
  __int64 v82; // r9
  int v83; // eax
  __int64 v84; // rdx
  int v85; // eax
  int v86; // eax
  _QWORD *v87; // rax
  void *v88; // rcx
  void **bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  _BYTE v92[8]; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v94; // [rsp+50h] [rbp-B0h]
  unsigned int v95[2]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v96; // [rsp+68h] [rbp-98h] BYREF
  void *v97; // [rsp+70h] [rbp-90h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v99; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v100; // [rsp+88h] [rbp-78h] BYREF
  __int64 v101; // [rsp+90h] [rbp-70h] BYREF
  int v102; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v103; // [rsp+9Ch] [rbp-64h] BYREF
  LPVOID v104; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID v105; // [rsp+A8h] [rbp-58h] BYREF
  int v106; // [rsp+B0h] [rbp-50h] BYREF
  LPCWCH lpString1; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v108; // [rsp+C0h] [rbp-40h] BYREF
  LPVOID v109; // [rsp+C8h] [rbp-38h] BYREF
  LPVOID v110; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v111[8]; // [rsp+E0h] [rbp-20h] BYREF
  __int16 v112; // [rsp+E8h] [rbp-18h]
  char v113; // [rsp+EAh] [rbp-16h]
  __int16 v114; // [rsp+ECh] [rbp-14h]
  unsigned int v115; // [rsp+F0h] [rbp-10h]
  char v116; // [rsp+F4h] [rbp-Ch]
  WCHAR sourceString[256]; // [rsp+2FCh] [rbp+1FCh] BYREF
  unsigned int Src; // [rsp+4FCh] [rbp+3FCh]
  Windows::Storage::Streams *Src_4; // [rsp+500h] [rbp+400h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2128h] [rbp+2028h]

  *(_QWORD *)v95 = a2;
  v96 = 0;
  v6 = Microsoft::WRL::Details::MakeAndInitialize<CSyncRootInformation,Windows::Storage::Provider::IStorageProviderSyncRootInfo,>(&v96);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x46E,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v6,
      (int)bIgnoreCase);
  v100 = 0;
  v7 = *a3;
  hstringHeader.Reserved.Reserved1 = &v100;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
  hstringHeader.Reserved.Reserved2[16] = 1;
  v8 = (*(__int64 (__fastcall **)(__int64 *, char *))(v7 + 24))(a3, &hstringHeader.Reserved.Reserved2[8]);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x472,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v8,
      (int)bIgnoreCase);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&hstringHeader);
  v9 = v96;
  v10 = *(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v96 + 56LL);
  pv = v100;
  v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &pv);
  v12 = v10(v9, *(_QWORD *)(v11 + 24));
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x473,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v12,
      (int)bIgnoreCase);
  v99 = 0;
  v13 = *(__int64 **)(a1 + 88);
  v14 = *v13;
  hstringHeader.Reserved.Reserved1 = &v99;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
  hstringHeader.Reserved.Reserved2[16] = 1;
  v15 = (*(__int64 (__fastcall **)(__int64 *, LPVOID, _QWORD, char *))(v14 + 136))(
          v13,
          v100,
          0,
          &hstringHeader.Reserved.Reserved2[8]);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&hstringHeader);
  if ( v15 < 0 )
  {
    *a2 = 0;
    goto LABEL_86;
  }
  v97 = 0;
  v92[0] = 0;
  CurrentProcess = GetCurrentProcess();
  if ( (int)CallerIdentity::IsProcessAppContainer(CurrentProcess, v92, v17) >= 0 && v92[0] )
  {
    v18 = v97;
    v97 = 0;
    if ( v18 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v18 + 16LL))(v18);
    StorageItemFromPath_FullTrustCaller_ForPackage = CreateStorageItemFromPath_PartialTrustCaller(
                                                       v99,
                                                       0x40u,
                                                       &GUID_72d1cb78_b3ef_4f75_a80b_6fd9dae2944b,
                                                       &v97);
  }
  else
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57509102>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57509102>::GetImpl'::`2'::impl) )
    {
      v20 = v97;
      v97 = 0;
      if ( v20 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
      v21 = 68;
    }
    else
    {
      v22 = v97;
      v97 = 0;
      if ( v22 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v22 + 16LL))(v22);
      v21 = 64;
    }
    bIgnoreCase = &v97;
    StorageItemFromPath_FullTrustCaller_ForPackage = CreateStorageItemFromPath_FullTrustCaller_ForPackage(
                                                       v99,
                                                       v21,
                                                       0,
                                                       &GUID_72d1cb78_b3ef_4f75_a80b_6fd9dae2944b);
  }
  if ( StorageItemFromPath_FullTrustCaller_ForPackage >= 0 )
  {
    v23 = (*(__int64 (__fastcall **)(_QWORD *, void *))(*v96 + 88LL))(v96, v97);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4A5,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
        (const char *)(unsigned int)v23,
        (int)bIgnoreCase);
    v110 = 0;
    v24 = *a3;
    hstringHeader.Reserved.Reserved1 = &v110;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
    hstringHeader.Reserved.Reserved2[16] = 1;
    v25 = (*(__int64 (__fastcall **)(__int64 *, char *))(v24 + 64))(a3, &hstringHeader.Reserved.Reserved2[8]);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4A9,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
        (const char *)(unsigned int)v25,
        (int)bIgnoreCase);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&hstringHeader);
    v26 = v96;
    v27 = *(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v96 + 104LL);
    pv = v110;
    v28 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &pv);
    v29 = v27(v26, *(_QWORD *)(v28 + 24));
    if ( v29 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4AA,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
        (const char *)(unsigned int)v29,
        (int)bIgnoreCase);
    v109 = 0;
    v30 = *a3;
    hstringHeader.Reserved.Reserved1 = &v109;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
    hstringHeader.Reserved.Reserved2[16] = 1;
    v31 = (*(__int64 (__fastcall **)(__int64 *, char *))(v30 + 88))(a3, &hstringHeader.Reserved.Reserved2[8]);
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4AE,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
        (const char *)(unsigned int)v31,
        (int)bIgnoreCase);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&hstringHeader);
    v32 = v96;
    v33 = *(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v96 + 120LL);
    pv = v109;
    v34 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &pv);
    v35 = v33(v32, *(_QWORD *)(v34 + 24));
    if ( v35 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4AF,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
        (const char *)(unsigned int)v35,
        (int)bIgnoreCase);
    v102 = 0;
    v36 = (*(__int64 (__fastcall **)(__int64 *, int *))(*a3 + 168))(a3, &v102);
    if ( v36 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4B3,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
        (const char *)(unsigned int)v36,
        (int)bIgnoreCase);
    if ( (v102 & 0x20) != 0 )
    {
      LOBYTE(v37) = 1;
      v38 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v96 + 264LL))(v96, v37);
      if ( v38 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4B6,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
          (const char *)(unsigned int)v38,
          (int)bIgnoreCase);
    }
    v108 = 0;
    v39 = *v96;
    hstringHeader.Reserved.Reserved1 = &v108;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
    hstringHeader.Reserved.Reserved2[16] = 1;
    v40 = (*(__int64 (__fastcall **)(_QWORD *, char *))(v39 + 272))(v96, &hstringHeader.Reserved.Reserved2[8]);
    if ( v40 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4BB,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
        (const char *)(unsigned int)v40,
        (int)bIgnoreCase);
    wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IUriRuntimeClass,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IUriRuntimeClass,wil::err_exception_policy>>(&hstringHeader);
    v105 = 0;
    v103 = 0;
    v41 = *a3;
    hstringHeader.Reserved.Reserved1 = &v105;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
    hstringHeader.Reserved.Reserved2[16] = 1;
    v42 = (*(__int64 (__fastcall **)(__int64 *, char *, unsigned int *))(v41 + 184))(
            a3,
            &hstringHeader.Reserved.Reserved2[8],
            &v103);
    if ( v42 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4BE,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
        (const char *)(unsigned int)v42,
        (int)bIgnoreCase);
    wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&hstringHeader);
    v43 = (char *)v105;
    v44 = (char *)v105 + 4 * v103;
    while ( v43 != v44 )
    {
      v45 = *(_DWORD *)v43;
      pv = 0;
      v46 = *a3;
      hstringHeader.Reserved.Reserved1 = &pv;
      *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
      hstringHeader.Reserved.Reserved2[16] = 1;
      v47 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, char *))(v46 + 192))(
              a3,
              v45,
              &hstringHeader.Reserved.Reserved2[8]);
      if ( v47 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4C2,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
          (const char *)(unsigned int)v47,
          (int)bIgnoreCase);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&hstringHeader);
      v101 = 0;
      v48 = Microsoft::WRL::Details::MakeAndInitialize<CCustomStateDefinition,CCustomStateDefinition,>(&v101);
      if ( v48 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4C4,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
          (const char *)(unsigned int)v48,
          (int)bIgnoreCase);
      v49 = v101;
      v50 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v101 + 56LL))(v101, v45);
      if ( v50 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4C5,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
          (const char *)(unsigned int)v50,
          (int)bIgnoreCase);
      v51 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v49 + 72LL);
      *(_QWORD *)v95 = pv;
      v52 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v95);
      v53 = v51(v49, *(_QWORD *)(v52 + 24));
      if ( v53 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4C6,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
          (const char *)(unsigned int)v53,
          (int)bIgnoreCase);
      v54 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v108 + 104LL))(v108, v49);
      if ( v54 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4C7,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
          (const char *)(unsigned int)v54,
          (int)bIgnoreCase);
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v101);
      if ( pv )
        CoTaskMemFree(pv);
      v43 += 4;
    }
    v104 = 0;
    v55 = *a3;
    hstringHeader.Reserved.Reserved1 = &v104;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
    hstringHeader.Reserved.Reserved2[16] = 1;
    v56 = (*(__int64 (__fastcall **)(__int64 *, char *))(v55 + 216))(a3, &hstringHeader.Reserved.Reserved2[8]);
    if ( v56 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4CC,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
        (const char *)(unsigned int)v56,
        (int)bIgnoreCase);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&hstringHeader);
    if ( v104 )
    {
      pv = 0;
      v94 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Foundation.Uri",
        0x17u,
        0x16u);
      ActivationFactory = RoGetActivationFactory(v94, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &pv);
      if ( ActivationFactory < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4D0,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
          (const char *)(unsigned int)ActivationFactory,
          (int)bIgnoreCase);
      v101 = 0;
      v58 = pv;
      v59 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)pv + 48LL);
      v101 = 0;
      *(_QWORD *)v95 = v104;
      v60 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v95);
      v61 = v59(v58, *(_QWORD *)(v60 + 24), &v101);
      if ( v61 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4D2,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
          (const char *)(unsigned int)v61,
          (int)bIgnoreCase);
      v62 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v96 + 288LL))(v96, v101);
      if ( v62 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4D3,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
          (const char *)(unsigned int)v62,
          (int)bIgnoreCase);
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v101);
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&pv);
    }
    lpString1 = 0;
    v63 = *(__int64 (__fastcall **)(__int64 *, __int64))(*a3 + 200);
    v64 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&lpString1);
    v65 = v63(a3, v64);
    if ( v65 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4D8,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
        (const char *)(unsigned int)v65,
        (int)bIgnoreCase);
    if ( CompareStringOrdinal(lpString1, -1, L"Personal", -1, 1) == 2 )
    {
      v66 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v96 + 248LL))(v96, 1);
      if ( v66 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4DB,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
          (const char *)(unsigned int)v66,
          bIgnoreCasea);
    }
    v106 = 0;
    if ( (int)CfGetSyncRootInfoByPath(v99, 1, v111, 0x2000) < 0 )
      goto LABEL_75;
    v67 = v96;
    v68 = *(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v96 + 232LL);
    v69 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, sourceString);
    v70 = v68(v67, *(_QWORD *)(v69 + 24));
    if ( v70 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4E7,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
        (const char *)(unsigned int)v70,
        (int)&v106);
    v71 = v96;
    v72 = *(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v96 + 72LL);
    v73 = (_QWORD *)CreateIBufferFromBytes((unsigned int)v95, &Src_4, (Windows::Storage::Streams *)Src);
    v74 = v72(v71, *v73);
    if ( v74 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4EA,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
        (const char *)(unsigned int)v74,
        (int)&v106);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(v95);
    if ( v112 )
    {
      switch ( v112 )
      {
        case 1:
          v75 = 1;
          goto LABEL_61;
        case 2:
          v75 = 2;
          goto LABEL_61;
        case 3:
          v75 = 3;
LABEL_61:
          v76 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v96 + 136LL))(v96, v75);
          if ( v76 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x4ED,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
              (const char *)(unsigned int)v76,
              (int)&v106);
          if ( v114 == 2 || (v77 = 2, v114 != 3) )
            v77 = 1;
          v78 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v96 + 168LL))(v96, v77);
          if ( v78 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x4EE,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
              (const char *)(unsigned int)v78,
              (int)&v106);
          v80 = CfInSyncPolicyToInSyncPolicy(v115, v79, *v96);
          v83 = (*(__int64 (__fastcall **)(__int64, _QWORD))(v81 + 184))(v82, v80);
          if ( v83 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x4EF,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
              (const char *)(unsigned int)v83,
              (int)&v106);
          v84 = (v113 & 1) != 0;
          if ( (v113 & 2) != 0 )
            v84 = (unsigned int)v84 | 2;
          if ( (v113 & 4) != 0 )
            v84 = (unsigned int)v84 | 4;
          if ( (v113 & 8) != 0 )
            v84 = (unsigned int)v84 | 8;
          v85 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v96 + 152LL))(v96, v84);
          if ( v85 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x4F0,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
              (const char *)(unsigned int)v85,
              (int)&v106);
          v86 = (*(__int64 (__fastcall **)(_QWORD *, bool))(*v96 + 200LL))(v96, (v116 & 1) != 0);
          if ( v86 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x4F1,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
              (const char *)(unsigned int)v86,
              (int)&v106);
LABEL_75:
          v87 = v96;
          v96 = 0;
          *a2 = v87;
          if ( lpString1 )
            CoTaskMemFree((LPVOID)lpString1);
          if ( v104 )
            CoTaskMemFree(v104);
          v88 = v105;
          v105 = 0;
          if ( v88 )
            CoTaskMemFree(v88);
          wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v108);
          if ( v109 )
            CoTaskMemFree(v109);
          if ( v110 )
            CoTaskMemFree(v110);
          goto LABEL_85;
      }
    }
    v75 = 0;
    goto LABEL_61;
  }
  *a2 = 0;
LABEL_85:
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v97);
LABEL_86:
  if ( v99 )
    CoTaskMemFree(v99);
  if ( v100 )
    CoTaskMemFree(v100);
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v96);
  return a2;
}

```

## disassembly

```asm
0x18024cd08  mov     [rsp-8+arg_18], rbx
0x18024cd0d  push    rbp
0x18024cd0e  push    rsi
0x18024cd0f  push    rdi
0x18024cd10  push    r12
0x18024cd12  push    r13
0x18024cd14  push    r14
0x18024cd16  push    r15
0x18024cd18  lea     rbp, [rsp-1FF0h]
0x18024cd20  mov     eax, 20F0h
0x18024cd25  call    _alloca_probe
0x18024cd2a  sub     rsp, rax
0x18024cd2d  mov     rax, cs:__security_cookie
0x18024cd34  xor     rax, rsp
0x18024cd37  mov     [rbp+2020h+var_40], rax
0x18024cd3e  mov     rsi, r8
0x18024cd41  mov     r15, rdx
0x18024cd44  mov     r14, rcx
0x18024cd47  mov     qword ptr [rsp+2120h+var_20C8], rdx
0x18024cd4c  xor     r13d, r13d
0x18024cd4f  mov     [rsp+2120h+var_20B8], r13
0x18024cd54  lea     rcx, [rsp+2120h+var_20B8]
0x18024cd59  call    ??$MakeAndInitialize@VCSyncRootInformation@@UIStorageProviderSyncRootInfo@Provider@Storage@Windows@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIStorageProviderSyncRootInfo@Provider@Storage@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CSyncRootInformation,Windows::Storage::Provider::IStorageProviderSyncRootInfo,>(Windows::Storage::Provider::IStorageProviderSyncRootInfo * *)
0x18024cd5e  mov     rcx, [rbp+2028h]; this
0x18024cd65  test    eax, eax
0x18024cd67  js      loc_18024D6E0
0x18024cd6d  mov     [rbp+2020h+var_2098], r13
0x18024cd71  mov     rax, [rsi]
0x18024cd74  lea     rcx, [rbp+2020h+var_2098]
0x18024cd78  mov     qword ptr [rsp+2120h+hstringHeader.Reserved], rcx
0x18024cd7d  mov     qword ptr [rsp+2120h+hstringHeader.Reserved+8], r13
0x18024cd82  mov     byte ptr [rsp+2120h+hstringHeader.Reserved+10h], 1
0x18024cd87  lea     rdx, [rsp+2120h+hstringHeader.Reserved+8]
0x18024cd8c  mov     rcx, rsi
0x18024cd8f  mov     rax, [rax+18h]
0x18024cd93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024cd98  mov     rcx, [rbp+2028h]; this
0x18024cd9f  test    eax, eax
0x18024cda1  js      loc_18024D6F5
0x18024cda7  lea     rcx, [rsp+2120h+hstringHeader]
0x18024cdac  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18024cdb1  mov     rdi, [rsp+2120h+var_20B8]
0x18024cdb6  mov     rax, [rdi]
0x18024cdb9  mov     rbx, [rax+38h]
0x18024cdbd  mov     rax, [rbp+2020h+var_2098]
0x18024cdc1  mov     [rsp+2120h+pv], rax
0x18024cdc6  lea     rdx, [rsp+2120h+pv]
0x18024cdcb  lea     rcx, [rsp+2120h+hstringHeader]
0x18024cdd0  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18024cdd5  nop
0x18024cdd6  mov     rdx, [rax+18h]
0x18024cdda  mov     rcx, rdi
0x18024cddd  mov     rax, rbx
0x18024cde0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024cde5  mov     rcx, [rbp+2028h]; this
0x18024cdec  test    eax, eax
0x18024cdee  js      loc_18024D70A
0x18024cdf4  mov     [rbp+2020h+var_20A0], r13
0x18024cdf8  mov     rcx, [r14+58h]
0x18024cdfc  mov     rax, [rcx]
0x18024cdff  lea     rdx, [rbp+2020h+var_20A0]
0x18024ce03  mov     qword ptr [rsp+2120h+hstringHeader.Reserved], rdx
0x18024ce08  mov     qword ptr [rsp+2120h+hstringHeader.Reserved+8], r13
0x18024ce0d  mov     byte ptr [rsp+2120h+hstringHeader.Reserved+10h], 1
0x18024ce12  lea     r9, [rsp+2120h+hstringHeader.Reserved+8]
0x18024ce17  xor     r8d, r8d
0x18024ce1a  mov     rdx, [rbp+2020h+var_2098]
0x18024ce1e  mov     rax, [rax+88h]
0x18024ce25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024ce2a  mov     ebx, eax
0x18024ce2c  lea     rcx, [rsp+2120h+hstringHeader]
0x18024ce31  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18024ce36  shr     ebx, 1Fh
0x18024ce39  test    bl, bl
0x18024ce3b  jz      short loc_18024CE45
0x18024ce3d  mov     [r15], r13
0x18024ce40  jmp     loc_18024D674
0x18024ce45  mov     [rsp+2120h+var_20B0], r13
0x18024ce4a  mov     [rsp+2120h+var_20F0], r13b
0x18024ce4f  call    cs:__imp_GetCurrentProcess
0x18024ce55  mov     rcx, rax; ProcessHandle
0x18024ce58  lea     rdx, [rsp+2120h+var_20F0]; void *
0x18024ce5d  call    ?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z; CallerIdentity::IsProcessAppContainer(void *,bool *)
0x18024ce62  test    eax, eax
0x18024ce64  js      short loc_18024CEAF
0x18024ce66  cmp     [rsp+2120h+var_20F0], r13b
0x18024ce6b  jz      short loc_18024CEAF
0x18024ce6d  mov     rcx, [rsp+2120h+var_20B0]
0x18024ce72  mov     [rsp+2120h+var_20B0], r13
0x18024ce77  test    rcx, rcx
0x18024ce7a  jz      short loc_18024CE89
0x18024ce7c  mov     rax, [rcx]
0x18024ce7f  mov     rax, [rax+10h]
0x18024ce83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024ce88  nop
0x18024ce89  lea     r9, [rsp+2120h+var_20B0]; void **
0x18024ce8e  lea     r8, _GUID_72d1cb78_b3ef_4f75_a80b_6fd9dae2944b; struct _GUID *
0x18024ce95  mov     edx, 40h ; '@'; unsigned int
0x18024ce9a  mov     rcx, [rbp+2020h+var_20A0]; unsigned __int16 *
0x18024ce9e  call    CreateStorageItemFromPath_PartialTrustCaller
0x18024cea3  test    eax, eax
0x18024cea5  jns     short loc_18024CF22
0x18024cea7  mov     [r15], r13
0x18024ceaa  jmp     loc_18024D669
0x18024ceaf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57509102@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57509102@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57509102> `wil::Feature<__WilFeatureTraits_Feature_57509102>::GetImpl(void)'::`2'::impl
0x18024ceb6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57509102@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57509102>::__private_IsEnabled(void)
0x18024cebb  test    al, al
0x18024cebd  jz      short loc_18024CEFF
0x18024cebf  mov     rcx, [rsp+2120h+var_20B0]
0x18024cec4  mov     [rsp+2120h+var_20B0], r13
0x18024cec9  test    rcx, rcx
0x18024cecc  jz      short loc_18024CEDB
0x18024cece  mov     rax, [rcx]
0x18024ced1  mov     rax, [rax+10h]
0x18024ced5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024ceda  nop
0x18024cedb  mov     edx, 44h ; 'D'
0x18024cee0  lea     rax, [rsp+2120h+var_20B0]
0x18024cee5  xor     r8d, r8d
0x18024cee8  lea     r9, _GUID_72d1cb78_b3ef_4f75_a80b_6fd9dae2944b
0x18024ceef  mov     qword ptr [rsp+2120h+bIgnoreCase], rax
0x18024cef4  mov     rcx, [rbp+2020h+var_20A0]
0x18024cef8  call    ?CreateStorageItemFromPath_FullTrustCaller_ForPackage@@YAJPEBGW4STORAGEITEM_CREATION_FLAGS@@0AEBU_GUID@@PEAPEAX@Z; CreateStorageItemFromPath_FullTrustCaller_ForPackage(ushort const *,STORAGEITEM_CREATION_FLAGS,ushort const *,_GUID const &,void * *)
0x18024cefd  jmp     short loc_18024CEA3
0x18024ceff  mov     rcx, [rsp+2120h+var_20B0]
0x18024cf04  mov     [rsp+2120h+var_20B0], r13
0x18024cf09  test    rcx, rcx
0x18024cf0c  jz      short loc_18024CF1B
0x18024cf0e  mov     rax, [rcx]
0x18024cf11  mov     rax, [rax+10h]
0x18024cf15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024cf1a  nop
0x18024cf1b  mov     edx, 40h ; '@'
0x18024cf20  jmp     short loc_18024CEE0
0x18024cf22  mov     rcx, [rsp+2120h+var_20B8]
0x18024cf27  mov     rax, [rcx]
0x18024cf2a  mov     rdx, [rsp+2120h+var_20B0]
0x18024cf2f  mov     rax, [rax+58h]
0x18024cf33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024cf38  mov     rcx, [rbp+2028h]; this
0x18024cf3f  test    eax, eax
0x18024cf41  js      loc_18024D71F
0x18024cf47  mov     [rbp+2020h+var_2050], r13
0x18024cf4b  mov     rax, [rsi]
0x18024cf4e  lea     rcx, [rbp+2020h+var_2050]
0x18024cf52  mov     qword ptr [rsp+2120h+hstringHeader.Reserved], rcx
0x18024cf57  mov     qword ptr [rsp+2120h+hstringHeader.Reserved+8], r13
0x18024cf5c  mov     byte ptr [rsp+2120h+hstringHeader.Reserved+10h], 1
0x18024cf61  lea     rdx, [rsp+2120h+hstringHeader.Reserved+8]
0x18024cf66  mov     rcx, rsi
0x18024cf69  mov     rax, [rax+40h]
0x18024cf6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024cf72  mov     rcx, [rbp+2028h]; this
0x18024cf79  test    eax, eax
0x18024cf7b  js      loc_18024D734
0x18024cf81  lea     rcx, [rsp+2120h+hstringHeader]
0x18024cf86  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18024cf8b  mov     rdi, [rsp+2120h+var_20B8]
0x18024cf90  mov     rax, [rdi]
0x18024cf93  mov     rbx, [rax+68h]
0x18024cf97  mov     rax, [rbp+2020h+var_2050]
0x18024cf9b  mov     [rsp+2120h+pv], rax
0x18024cfa0  lea     rdx, [rsp+2120h+pv]
0x18024cfa5  lea     rcx, [rsp+2120h+hstringHeader]
0x18024cfaa  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18024cfaf  nop
0x18024cfb0  mov     rdx, [rax+18h]
0x18024cfb4  mov     rcx, rdi
0x18024cfb7  mov     rax, rbx
0x18024cfba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024cfbf  mov     rcx, [rbp+2028h]; this
0x18024cfc6  test    eax, eax
0x18024cfc8  js      loc_18024D749
0x18024cfce  mov     [rbp+2020h+var_2058], r13
0x18024cfd2  mov     rax, [rsi]
0x18024cfd5  lea     rcx, [rbp+2020h+var_2058]
0x18024cfd9  mov     qword ptr [rsp+2120h+hstringHeader.Reserved], rcx
0x18024cfde  mov     qword ptr [rsp+2120h+hstringHeader.Reserved+8], r13
0x18024cfe3  mov     byte ptr [rsp+2120h+hstringHeader.Reserved+10h], 1
0x18024cfe8  lea     rdx, [rsp+2120h+hstringHeader.Reserved+8]
0x18024cfed  mov     rcx, rsi
0x18024cff0  mov     rax, [rax+58h]
0x18024cff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024cff9  mov     rcx, [rbp+2028h]; this
0x18024d000  test    eax, eax
0x18024d002  js      loc_18024D75E
0x18024d008  lea     rcx, [rsp+2120h+hstringHeader]
0x18024d00d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18024d012  mov     rdi, [rsp+2120h+var_20B8]
0x18024d017  mov     rax, [rdi]
0x18024d01a  mov     rbx, [rax+78h]
0x18024d01e  mov     rax, [rbp+2020h+var_2058]
0x18024d022  mov     [rsp+2120h+pv], rax
0x18024d027  lea     rdx, [rsp+2120h+pv]
0x18024d02c  lea     rcx, [rsp+2120h+hstringHeader]
0x18024d031  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18024d036  nop
0x18024d037  mov     rdx, [rax+18h]
0x18024d03b  mov     rcx, rdi
0x18024d03e  mov     rax, rbx
0x18024d041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024d046  mov     rcx, [rbp+2028h]; this
0x18024d04d  test    eax, eax
0x18024d04f  js      loc_18024D773
0x18024d055  mov     [rbp+2020h+var_2088], r13d
0x18024d059  mov     rax, [rsi]
0x18024d05c  lea     rdx, [rbp+2020h+var_2088]
0x18024d060  mov     rcx, rsi
0x18024d063  mov     rax, [rax+0A8h]
0x18024d06a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024d06f  mov     rcx, [rbp+2028h]; this
0x18024d076  test    eax, eax
0x18024d078  js      loc_18024D788
0x18024d07e  test    byte ptr [rbp+2020h+var_2088], 20h
0x18024d082  jz      short loc_18024D0A9
0x18024d084  mov     rcx, [rsp+2120h+var_20B8]
0x18024d089  mov     rax, [rcx]
0x18024d08c  mov     dl, 1
0x18024d08e  mov     rax, [rax+108h]
0x18024d095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024d09a  mov     rcx, [rbp+2028h]; this
0x18024d0a1  test    eax, eax
0x18024d0a3  js      loc_18024D79D
0x18024d0a9  mov     [rbp+2020h+var_2060], r13
0x18024d0ad  mov     rcx, [rsp+2120h+var_20B8]
0x18024d0b2  mov     rax, [rcx]
0x18024d0b5  lea     rdx, [rbp+2020h+var_2060]
0x18024d0b9  mov     qword ptr [rsp+2120h+hstringHeader.Reserved], rdx
0x18024d0be  mov     qword ptr [rsp+2120h+hstringHeader.Reserved+8], r13
0x18024d0c3  mov     byte ptr [rsp+2120h+hstringHeader.Reserved+10h], 1
0x18024d0c8  lea     rdx, [rsp+2120h+hstringHeader.Reserved+8]
0x18024d0cd  mov     rax, [rax+110h]
0x18024d0d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024d0d9  mov     rcx, [rbp+2028h]; this
0x18024d0e0  test    eax, eax
0x18024d0e2  js      loc_18024D7B2
0x18024d0e8  lea     rcx, [rsp+2120h+hstringHeader]
0x18024d0ed  call    ??1?$out_param_t@V?$com_ptr_t@UIUriRuntimeClass@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IUriRuntimeClass,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IUriRuntimeClass,wil::err_exception_policy>>(void)
0x18024d0f2  mov     [rbp+2020h+var_2078], r13
0x18024d0f6  mov     [rbp+2020h+var_2084], r13d
0x18024d0fa  mov     rax, [rsi]
0x18024d0fd  lea     rcx, [rbp+2020h+var_2078]
0x18024d101  mov     qword ptr [rsp+2120h+hstringHeader.Reserved], rcx
0x18024d106  mov     qword ptr [rsp+2120h+hstringHeader.Reserved+8], r13
0x18024d10b  mov     byte ptr [rsp+2120h+hstringHeader.Reserved+10h], 1
0x18024d110  lea     r8, [rbp+2020h+var_2084]
0x18024d114  lea     rdx, [rsp+2120h+hstringHeader.Reserved+8]
0x18024d119  mov     rcx, rsi
0x18024d11c  mov     rax, [rax+0B8h]
0x18024d123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024d128  mov     rcx, [rbp+2028h]; this
0x18024d12f  test    eax, eax
0x18024d131  js      loc_18024D7C7
0x18024d137  lea     rcx, [rsp+2120h+hstringHeader]
0x18024d13c  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18024d141  mov     r14, [rbp+2020h+var_2078]
0x18024d145  mov     eax, [rbp+2020h+var_2084]
0x18024d148  lea     r12, [r14+rax*4]
0x18024d14c  jmp     loc_18024D25F
0x18024d151  mov     edi, [r14]
0x18024d154  mov     [rsp+2120h+pv], r13
0x18024d159  mov     rax, [rsi]
0x18024d15c  lea     rcx, [rsp+2120h+pv]
0x18024d161  mov     qword ptr [rsp+2120h+hstringHeader.Reserved], rcx
0x18024d166  mov     qword ptr [rsp+2120h+hstringHeader.Reserved+8], r13
0x18024d16b  mov     byte ptr [rsp+2120h+hstringHeader.Reserved+10h], 1
0x18024d170  lea     r8, [rsp+2120h+hstringHeader.Reserved+8]
0x18024d175  mov     edx, edi
0x18024d177  mov     rcx, rsi
0x18024d17a  mov     rax, [rax+0C0h]
0x18024d181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024d186  mov     rcx, [rbp+2028h]; this
0x18024d18d  test    eax, eax
0x18024d18f  js      loc_18024D845
0x18024d195  lea     rcx, [rsp+2120h+hstringHeader]
0x18024d19a  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18024d19f  nop
0x18024d1a0  mov     [rbp+2020h+var_2090], r13
0x18024d1a4  lea     rcx, [rbp+2020h+var_2090]
0x18024d1a8  call    ??$MakeAndInitialize@VCCustomStateDefinition@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCCustomStateDefinition@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CCustomStateDefinition,CCustomStateDefinition,>(CCustomStateDefinition * *)
0x18024d1ad  mov     rcx, [rbp+2028h]; this
0x18024d1b4  test    eax, eax
0x18024d1b6  js      loc_18024D830
0x18024d1bc  mov     rbx, [rbp+2020h+var_2090]
0x18024d1c0  mov     rax, [rbx]
0x18024d1c3  mov     edx, edi
0x18024d1c5  mov     rcx, rbx
0x18024d1c8  mov     rax, [rax+38h]
0x18024d1cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024d1d1  mov     rcx, [rbp+2028h]; this
0x18024d1d8  test    eax, eax
0x18024d1da  js      loc_18024D81B
0x18024d1e0  mov     rax, [rbx]
0x18024d1e3  mov     rdi, [rax+48h]
0x18024d1e7  mov     rax, [rsp+2120h+pv]
0x18024d1ec  mov     qword ptr [rsp+2120h+var_20C8], rax
0x18024d1f1  lea     rdx, [rsp+2120h+var_20C8]
0x18024d1f6  lea     rcx, [rsp+2120h+hstringHeader]
0x18024d1fb  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18024d200  nop
  ... truncated ...
```
