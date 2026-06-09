# CAppidData::Load(IComProcessInfo *,ulong,ushort const *,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)

- ea: `0x180091620`
- end: `0x1800920ac`
- name: `?Load@CAppidData@@QEAAJPEAUIComProcessInfo@@KPEBG1IQEBQEAUHSTRING__@@I2@Z`
- size: `2700`
- prototype: `__int64 __fastcall(CAppidData *this, struct IComProcessInfo *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, unsigned int, HSTRING *const, unsigned int, HSTRING *const)`
- caller_count: `5`
- callee_count: `21`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180060644`
- `0x180090a0c`
- `0x18009fc80`
- `0x1800eafd0`
- `0x1800f8224`

## callees

- `0x180003064`
- `0x180005c40`
- `0x18000b310`
- `0x180016160`
- `0x180026a50`
- `0x180029db0`
- `0x18002ba28`
- `0x18002d960`
- `0x180034540`
- `0x180043850`
- `0x180056bd0`
- `0x18005d4f4`
- `0x180070740`
- `0x18007e3d4`
- `0x18008e98c`
- `0x180091620`
- `0x180094190`
- `0x180098b54`
- `0x1800ab634`
- `0x1800b27e0`
- `0x18010b010`

## import_xrefs

- `ntdll!RtlCreateVirtualAccountSid` at `0x18009202f`
- `ntdll!RtlCreateVirtualAccountSid` at `0x18009202f`
- `ntdll!RtlNtStatusToDosError` at `0x18009203b`
- `ntdll!RtlNtStatusToDosError` at `0x18009203b`
- `ntdll!RtlInitUnicodeString` at `0x180092014`
- `ntdll!RtlInitUnicodeString` at `0x180092014`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180091bb2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180091bb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180091f12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180091f3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180091f12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180091f3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180091f7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180091f7a`
- `KERNELBASE!FormatApplicationUserModelId` at `0x180091f51`
- `KERNELBASE!FormatApplicationUserModelId` at `0x180091f51`
- `KERNELBASE!LocalAlloc` at `0x180091fef`
- `KERNELBASE!LocalAlloc` at `0x180091fef`
- `KERNELBASE!PackageFamilyNameFromFullName` at `0x180091f24`
- `KERNELBASE!PackageFamilyNameFromFullName` at `0x180091f24`

## string_xrefs

- `0x180091709`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18009186c`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x180091959`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x180091e78`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18009208b`: `onecore\com\combase\rpcss\olescm\clsid.cxx`

## pseudocode

```c
__int64 __fastcall CAppidData::Load(
        CAppidData *this,
        struct IComProcessInfo *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        unsigned int a6,
        HSTRING *const a7,
        unsigned int a8,
        HSTRING *const a9)
{
  int ComCatalogObject; // ebx
  _QWORD *v13; // r14
  __int64 (__fastcall ***v14)(_QWORD, GUID *, __int64 *); // rdi
  int v15; // eax
  int v16; // eax
  CGuidStr *v17; // rax
  int UserServiceNameIfAvailable; // ebx
  __int64 v19; // rcx
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, char *); // rbx
  int v26; // ecx
  bool v27; // al
  bool v28; // zf
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rax
  unsigned __int64 v32; // rbx
  SIZE_T v33; // rax
  unsigned __int64 v34; // kr00_8
  unsigned __int16 *v35; // rax
  unsigned __int16 *v36; // rcx
  unsigned __int16 v37; // ax
  unsigned __int16 *v38; // rdx
  int v39; // ebx
  __int64 (__fastcall ***v40)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v41; // rcx
  __int64 (__fastcall *v42)(__int64, char *); // rdi
  unsigned __int16 *v43; // rax
  CGuidStr *v44; // rax
  __int64 (__fastcall *v45)(__int64, char *); // rbx
  HSTRING v46; // rcx
  const WCHAR *StringRawBuffer; // rax
  LONG v48; // eax
  HSTRING v49; // rcx
  const WCHAR *v50; // rax
  LONG v51; // eax
  HLOCAL v52; // rax
  NTSTATUS v53; // eax
  signed int v54; // eax
  unsigned __int16 **v55; // [rsp+20h] [rbp-E0h]
  bool *v56; // [rsp+28h] [rbp-D8h]
  UINT32 packageFamilyNameLength[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v58; // [rsp+78h] [rbp-88h] BYREF
  int v59; // [rsp+80h] [rbp-80h] BYREF
  __int64 v60; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v61; // [rsp+90h] [rbp-70h] BYREF
  UINT32 applicationUserModelIdLength[2]; // [rsp+98h] [rbp-68h] BYREF
  int v63; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v64; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v65; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-48h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+160h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  ComCatalogObject = 0;
  *(_QWORD *)applicationUserModelIdLength = a9;
  v64 = 0;
  v59 = 0;
  v61 = 0;
  v63 = 0;
  v60 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    *((_DWORD *)this + 56) = a3 & 0xFFFFF300;
  v13 = (_QWORD *)((char *)this + 216);
  v14 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 27);
  if ( v14 )
    goto LABEL_27;
  if ( a2 )
  {
    *v13 = a2;
    (*(void (__fastcall **)(struct IComProcessInfo *))(*(_QWORD *)a2 + 8LL))(a2);
  }
  else
  {
    *(_QWORD *)packageFamilyNameLength = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    {
      if ( *(_QWORD *)this )
      {
        ComCatalogObject = GetComCatalogObject(&GUID_000001fd_0000_0000_c000_000000000046, packageFamilyNameLength);
        if ( ComCatalogObject < 0 )
          goto LABEL_17;
        v56 = (bool *)this + 216;
        v55 = (unsigned __int16 **)&IID_IComProcessInfo;
        v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, char *))(**(_QWORD **)packageFamilyNameLength + 40LL))(
                *(_QWORD *)packageFamilyNameLength,
                a3,
                *(_QWORD *)this,
                (char *)this + 196);
      }
      else
      {
        ComCatalogObject = GetComCatalogObject(&GUID_000001e0_0000_0000_c000_000000000046, packageFamilyNameLength);
        if ( ComCatalogObject < 0 )
          goto LABEL_17;
        v16 = (*(__int64 (__fastcall **)(_QWORD, char *, GUID *, char *))(**(_QWORD **)packageFamilyNameLength + 40LL))(
                *(_QWORD *)packageFamilyNameLength,
                (char *)this + 196,
                &IID_IComProcessInfo,
                (char *)this + 216);
      }
      ComCatalogObject = v16;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)packageFamilyNameLength + 16LL))(*(_QWORD *)packageFamilyNameLength);
      goto LABEL_17;
    }
    v15 = GetComCatalogObject(&GUID_bcf8570c_b66f_4849_aa7a_94d710f655bf, packageFamilyNameLength);
    ComCatalogObject = v15;
    if ( v15 >= 0 )
    {
      HIDWORD(v56) = 0;
      LODWORD(v55) = 0;
      ComCatalogObject = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, char *))(**(_QWORD **)packageFamilyNameLength
                                                                                   + 32LL))(
                           *(_QWORD *)packageFamilyNameLength,
                           a3,
                           *(_QWORD *)this,
                           (char *)this + 196);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x967,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
        (const char *)(unsigned int)v15,
        (int)v55);
    }
    wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(packageFamilyNameLength);
  }
LABEL_17:
  v14 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v13;
  if ( !*v13 || ComCatalogObject )
  {
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      v17 = CGuidStr::CGuidStr((CGuidStr *)packageFamilyName, (const struct _GUID *)((char *)this + 196));
      ComTraceMessageT<unsigned short *,long>(
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
        (unsigned int)"CAppidData::Load",
        2447,
        0,
        (__int64)L"APPID:%ws %!HRESULT!",
        v17,
        ComCatalogObject);
    }
    UserServiceNameIfAvailable = -2147221164;
    goto LABEL_24;
  }
LABEL_27:
  v21 = v60;
  v60 = 0;
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  v22 = (**v14)(v14, &GUID_430be197_0244_2f7b_80fd_c7c473983ad0, &v60);
  UserServiceNameIfAvailable = v22;
  if ( v22 < 0 )
  {
    v23 = 2455;
LABEL_33:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
      (const char *)(unsigned int)v22,
      (int)v55);
    goto LABEL_26;
  }
  v22 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v60 + 24LL))(v60, (char *)this + 288);
  UserServiceNameIfAvailable = v22;
  if ( v22 < 0 )
  {
    v23 = 2457;
    goto LABEL_33;
  }
  v24 = v60;
  v25 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v60 + 32LL);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    (char *)this + 248,
    0);
  v22 = v25(v24, (char *)this + 248);
  UserServiceNameIfAvailable = v22;
  if ( v22 < 0 )
  {
    v23 = 2468;
    goto LABEL_33;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
  {
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      (char *)this + 256,
      0);
    v22 = NormalizePackageNameCasing_nothrow(*((HSTRING *)this + 31), (HSTRING *)this + 32);
    UserServiceNameIfAvailable = v22;
    if ( v22 < 0 )
    {
      v23 = 2471;
      goto LABEL_33;
    }
  }
  v22 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v60 + 40LL))(v60, (char *)this + 264);
  UserServiceNameIfAvailable = v22;
  if ( v22 < 0 )
  {
    v23 = 2474;
    goto LABEL_33;
  }
  v26 = *((_DWORD *)this + 72);
  v27 = (unsigned int)(v26 - 1) <= 1;
  v28 = v26 == 1;
  v29 = *((_QWORD *)this + 27);
  *((_BYTE *)this + 304) = v27;
  *((_BYTE *)this + 305) = v28;
  if ( (*(unsigned int (__fastcall **)(__int64, char *))(*(_QWORD *)v29 + 72LL))(v29, (char *)this + 96) )
    *((_DWORD *)this + 24) = 0;
  if ( (*(unsigned int (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 27) + 40LL))(*((_QWORD *)this + 27), &v59) )
    v59 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    *((_BYTE *)this + 116) = ((v59 - 2) & 0xFFFFFFFD) == 0;
  else
    *((_DWORD *)this + 28) = v59 == 2;
  if ( (*(unsigned int (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 27) + 144LL))(
         *((_QWORD *)this + 27),
         (char *)this + 104) )
  {
    *((_QWORD *)this + 13) = 0;
  }
  if ( (*(unsigned int (__fastcall **)(_QWORD, char *, int *))(**((_QWORD **)this + 27) + 96LL))(
         *((_QWORD *)this + 27),
         (char *)this + 48,
         &v63) )
  {
    *((_QWORD *)this + 6) = 0;
  }
  v30 = *((_QWORD *)this + 27);
  v65 = 0;
  if ( (*(unsigned int (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v30 + 56LL))(v30, &v65) )
  {
    *((_QWORD *)this + 2) = 0;
  }
  else
  {
    UserServiceNameIfAvailable = GetUserServiceNameIfAvailable(
                                   *((struct IUnknown **)this + 27),
                                   v65,
                                   *(struct CToken **)this,
                                   *((_QWORD *)this + 1),
                                   (unsigned __int16 **)this + 2,
                                   (bool *)this + 306);
    if ( UserServiceNameIfAvailable < 0 )
      goto LABEL_24;
  }
  if ( (*(unsigned int (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 27) + 64LL))(
         *((_QWORD *)this + 27),
         (char *)this + 24) )
  {
    *((_QWORD *)this + 3) = 0;
  }
  if ( (*(unsigned int (__fastcall **)(_QWORD, unsigned __int16 **))(**((_QWORD **)this + 27) + 88LL))(
         *((_QWORD *)this + 27),
         &v61) )
  {
    *((_QWORD *)this + 4) = 0;
    *((_QWORD *)this + 5) = 0;
    goto LABEL_71;
  }
  v31 = -1;
  do
    ++v31;
  while ( v61[v31] );
  v32 = v31 + 1;
  v34 = v31 + 1;
  v33 = 2 * (v31 + 1);
  if ( !is_mul_ok(v34, 2u) )
    v33 = -1;
  v35 = (unsigned __int16 *)HeapAlloc(g_hHeap, 0, v33);
  *((_QWORD *)this + 4) = v35;
  if ( !v35 )
  {
    UserServiceNameIfAvailable = -2147024882;
    goto LABEL_24;
  }
  UserServiceNameIfAvailable = StringCchCopyW(v35, v32, v61);
  if ( UserServiceNameIfAvailable < 0 )
  {
LABEL_24:
    CAppidData::Purge(this);
    v19 = *((_QWORD *)this + 27);
    if ( v19 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      *((_QWORD *)this + 27) = 0;
    }
    goto LABEL_26;
  }
  v36 = (unsigned __int16 *)*((_QWORD *)this + 4);
  v61 = v36;
  v37 = *v36;
  if ( *v36 )
  {
    v38 = v36;
    while ( v37 != 92 )
    {
      v36 = v38 + 1;
      v61 = v36;
      ++v38;
      v37 = *v36;
      if ( !*v36 )
        goto LABEL_70;
    }
    *v36 = 0;
    *((_QWORD *)this + 5) = *((_QWORD *)this + 4);
    v43 = v61 + 1;
    *((_QWORD *)this + 4) = v61 + 1;
    if ( !*v43 )
    {
      UserServiceNameIfAvailable = -2147467259;
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      {
        v44 = CGuidStr::CGuidStr((CGuidStr *)packageFamilyName, (const struct _GUID *)((char *)this + 196));
        ComTraceMessageT<unsigned short *,long>(
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
          (unsigned int)"CAppidData::Load",
          2626,
          0,
          (__int64)L"APPID:%ws %!HRESULT!",
          v44,
          -2147467259);
      }
      goto LABEL_24;
    }
  }
  else
  {
LABEL_70:
    *((_QWORD *)this + 5) = L".";
  }
LABEL_71:
  v39 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 27))(
          *((_QWORD *)this + 27),
          &IID_IComProcessInfo2,
          &v64);
  if ( v39 >= 0 )
  {
    v39 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v64 + 168LL))(v64, (char *)this + 56);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
  }
  *((_DWORD *)this + 15) = v39 >= 0;
  v40 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 27);
  v58 = 0;
  UserServiceNameIfAvailable = (**v40)(v40, &GUID_5b0300bc_3a64_4bfe_9a06_ee2bcce72680, &v58);
  if ( UserServiceNameIfAvailable < 0 )
  {
    UserServiceNameIfAvailable = 0;
  }
  else
  {
    (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v58 + 184LL))(v58, (char *)this + 64);
    (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v58 + 192LL))(v58, (char *)this + 72);
    (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v58 + 224LL))(v58, (char *)this + 68);
    if ( (*(int (__fastcall **)(__int64, char *))(*(_QWORD *)v58 + 264LL))(v58, (char *)this + 76) < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v41);
    (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v58 + 256LL))(v58, (char *)this + 80);
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
      && !*((_BYTE *)this + 305) )
    {
      *((_DWORD *)this + 56) &= ~0x1000u;
    }
    if ( *((_BYTE *)this + 304) )
    {
      v42 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v58 + 240LL);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        (char *)this + 272,
        0);
      UserServiceNameIfAvailable = v42(v58, (char *)this + 272);
    }
    if ( CAppidData::HasActivateAsPackage(this) )
    {
      *(_QWORD *)packageFamilyNameLength = 0;
      if ( (**(int (__fastcall ***)(__int64, GUID *, UINT32 *))v58)(
             v58,
             &GUID_6c41cb64_51a5_4177_b4ae_3e1d2e3f0157,
             packageFamilyNameLength) < 0 )
      {
        *((_DWORD *)this + 73) = 1;
        *((_DWORD *)this + 74) = 1;
      }
      else
      {
        (*(void (__fastcall **)(_QWORD, char *))(**(_QWORD **)packageFamilyNameLength + 32LL))(
          *(_QWORD *)packageFamilyNameLength,
          (char *)this + 292);
        (*(void (__fastcall **)(_QWORD, char *))(**(_QWORD **)packageFamilyNameLength + 24LL))(
          *(_QWORD *)packageFamilyNameLength,
          (char *)this + 296);
        (*(void (__fastcall **)(_QWORD, char *))(**(_QWORD **)packageFamilyNameLength + 40LL))(
          *(_QWORD *)packageFamilyNameLength,
          (char *)this + 300);
      }
      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(packageFamilyNameLength);
    }
    if ( UserServiceNameIfAvailable >= 0 && (unsigned int)CAppidData::GetRunAsType((__int64)this) == 4 )
    {
      v45 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v58 + 232LL);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        (char *)this + 240,
        0);
      UserServiceNameIfAvailable = v45(v58, (char *)this + 240);
      if ( UserServiceNameIfAvailable >= 0 )
      {
        v46 = (HSTRING)*((_QWORD *)this + 34);
        packageFamilyNameLength[0] = 65;
        StringRawBuffer = WindowsGetStringRawBuffer(v46, 0);
        v48 = PackageFamilyNameFromFullName(StringRawBuffer, packageFamilyNameLength, packageFamilyName);
        UserServiceNameIfAvailable = v48;
        if ( v48 )
        {
          if ( v48 > 0 )
            UserServiceNameIfAvailable = (unsigned __int16)v48 | 0x80070000;
        }
        else
        {
          v49 = (HSTRING)*((_QWORD *)this + 30);
          applicationUserModelIdLength[0] = 130;
          v50 = WindowsGetStringRawBuffer(v49, 0);
          v51 = FormatApplicationUserModelId(
                  packageFamilyName,
                  v50,
                  applicationUserModelIdLength,
                  applicationUserModelId);
          UserServiceNameIfAvailable = v51;
          if ( v51 )
          {
            if ( v51 > 0 )
              UserServiceNameIfAvailable = (unsigned __int16)v51 | 0x80070000;
          }
          else
          {
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
              (char *)this + 280,
              0);
            UserServiceNameIfAvailable = WindowsCreateString(
                                           applicationUserModelId,
                                           applicationUserModelIdLength[0] - 1,
                                           (HSTRING *)this + 35);
          }
          if ( UserServiceNameIfAvailable >= 0 )
          {
            *(_QWORD *)&DestinationString.Length = this;
            UserServiceNameIfAvailable = lambda_7ea31cf5c60b100a9bc7ad8691952db1_::operator()(&DestinationString);
          }
        }
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    if ( UserServiceNameIfAvailable < 0 )
      goto LABEL_24;
  }
  if ( !(unsigned int)CAppidData::GetRunAsType((__int64)this) && (*((_BYTE *)this + 72) & 2) != 0 )
  {
    packageFamilyNameLength[0] = 68;
    UserServiceNameIfAvailable = -2147024882;
    v52 = LocalAlloc(0, 0x44u);
    *((_QWORD *)this + 29) = v52;
    if ( !v52 )
      goto LABEL_24;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, (PCWSTR)this + 59);
    v53 = RtlCreateVirtualAccountSid(&DestinationString, 89, *((_QWORD *)this + 29), packageFamilyNameLength);
    if ( v53 >= 0 )
    {
      UserServiceNameIfAvailable = 0;
      goto LABEL_26;
    }
    v54 = RtlNtStatusToDosError(v53);
    UserServiceNameIfAvailable = v54;
    if ( v54 > 0 )
      UserServiceNameIfAvailable = (unsigned __int16)v54 | 0x80070000;
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      LODWORD(v56) = UserServiceNameIfAvailable;
      ComTraceMessageT<long>(
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
        (unsigned int)"CAppidData::Load",
        2810,
        0,
        (__int64)L"%!HRESULT!",
        v56);
    }
    if ( UserServiceNameIfAvailable < 0 )
      goto LABEL_24;
  }
LABEL_26:
  wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v60);
  return (unsigned int)UserServiceNameIfAvailable;
}

```

## disassembly

```asm
0x180091620  mov     [rsp-8+arg_8], rbx
0x180091625  push    rbp
0x180091626  push    rsi
0x180091627  push    rdi
0x180091628  push    r12
0x18009162a  push    r13
0x18009162c  push    r14
0x18009162e  push    r15
0x180091630  lea     rbp, [rsp-180h]
0x180091638  sub     rsp, 280h
0x18009163f  mov     rax, cs:__security_cookie
0x180091646  xor     rax, rsp
0x180091649  mov     [rbp+1B0h+var_40], rax
0x180091650  mov     rax, [rbp+1B0h+arg_40]
0x180091657  xor     ebx, ebx
0x180091659  mov     r13, [rbp+1B0h+arg_30]
0x180091660  mov     r12d, r8d
0x180091663  mov     qword ptr [rbp+1B0h+applicationUserModelIdLength], rax
0x180091667  mov     r15, rdx
0x18009166a  mov     [rbp+1B0h+var_208], rbx
0x18009166e  mov     rsi, rcx
0x180091671  mov     [rbp+1B0h+var_230], ebx
0x180091674  mov     [rbp+1B0h+var_220], rbx
0x180091678  mov     [rbp+1B0h+var_210], ebx
0x18009167b  mov     [rbp+1B0h+var_228], rbx
0x18009167f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x180091686  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x18009168b  test    al, al
0x18009168d  jnz     short loc_18009169D
0x18009168f  mov     eax, r12d
0x180091692  and     eax, 0FFFFF300h
0x180091697  mov     [rsi+0E0h], eax
0x18009169d  lea     r14, [rsi+0D8h]
0x1800916a4  mov     rdi, [r14]
0x1800916a7  test    rdi, rdi
0x1800916aa  jnz     loc_1800918EE
0x1800916b0  test    r15, r15
0x1800916b3  jz      short loc_1800916CF
0x1800916b5  mov     [r14], r15
0x1800916b8  mov     rcx, r15
0x1800916bb  mov     rax, [r15]
0x1800916be  mov     rax, [rax+8]
0x1800916c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800916c7  xor     r15d, r15d
0x1800916ca  jmp     loc_18009181E
0x1800916cf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800916d6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800916db  xor     r15d, r15d
0x1800916de  lea     rdx, [rsp+2B0h+packageFamilyNameLength]
0x1800916e3  mov     qword ptr [rsp+2B0h+packageFamilyNameLength], r15
0x1800916e8  test    al, al
0x1800916ea  jz      loc_18009178F
0x1800916f0  lea     rcx, _GUID_bcf8570c_b66f_4849_aa7a_94d710f655bf
0x1800916f7  call    GetComCatalogObject
0x1800916fc  mov     ebx, eax
0x1800916fe  test    eax, eax
0x180091700  jns     short loc_18009171F
0x180091702  mov     rcx, [rbp+1B8h]; this
0x180091709  lea     r8, aOnecoreComComb_27; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180091710  mov     r9d, eax; char *
0x180091713  mov     edx, 967h; void *
0x180091718  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009171d  jmp     short loc_180091780
0x18009171f  mov     r8d, [rbp+1B0h+arg_38]
0x180091726  lea     rdx, _GUID_000001ed_0000_0000_c000_000000000046
0x18009172d  mov     rcx, qword ptr [rsp+2B0h+packageFamilyNameLength]
0x180091732  lea     r9, [rsi+0C4h]
0x180091739  mov     [rsp+2B0h+var_258], r14
0x18009173e  mov     [rsp+2B0h+var_260], rdx
0x180091743  mov     rdx, qword ptr [rbp+1B0h+applicationUserModelIdLength]
0x180091747  mov     rax, [rcx]
0x18009174a  mov     [rsp+2B0h+var_268], rdx
0x18009174f  mov     edx, r12d
0x180091752  mov     [rsp+2B0h+var_270], r8d
0x180091757  mov     r8d, [rbp+1B0h+arg_28]
0x18009175e  mov     rax, [rax+20h]
0x180091762  mov     [rsp+2B0h+var_278], r13
0x180091767  mov     [rsp+2B0h+var_280], r8d
0x18009176c  mov     r8, [rsi]
0x18009176f  mov     [rsp+2B0h+var_288], r15
0x180091774  mov     [rsp+2B0h+var_290], r15
0x180091779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009177e  mov     ebx, eax
0x180091780  lea     rcx, [rsp+2B0h+packageFamilyNameLength]
0x180091785  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x18009178a  jmp     loc_18009181E
0x18009178f  cmp     [rsi], r15
0x180091792  jz      short loc_1800917D7
0x180091794  lea     rcx, _GUID_000001fd_0000_0000_c000_000000000046
0x18009179b  call    GetComCatalogObject
0x1800917a0  mov     ebx, eax
0x1800917a2  test    eax, eax
0x1800917a4  js      short loc_18009181E
0x1800917a6  mov     rcx, qword ptr [rsp+2B0h+packageFamilyNameLength]
0x1800917ab  lea     r8, IID_IComProcessInfo
0x1800917b2  mov     [rsp+2B0h+var_288], r14
0x1800917b7  lea     r9, [rsi+0C4h]
0x1800917be  mov     [rsp+2B0h+var_290], r8
0x1800917c3  mov     edx, r12d
0x1800917c6  mov     r8, [rsi]
0x1800917c9  mov     rax, [rcx]
0x1800917cc  mov     rax, [rax+28h]
0x1800917d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800917d5  jmp     short loc_18009180B
0x1800917d7  lea     rcx, _GUID_000001e0_0000_0000_c000_000000000046
0x1800917de  call    GetComCatalogObject
0x1800917e3  mov     ebx, eax
0x1800917e5  test    eax, eax
0x1800917e7  js      short loc_18009181E
0x1800917e9  mov     rcx, qword ptr [rsp+2B0h+packageFamilyNameLength]
0x1800917ee  lea     rdx, [rsi+0C4h]
0x1800917f5  mov     r9, r14
0x1800917f8  lea     r8, IID_IComProcessInfo
0x1800917ff  mov     rax, [rcx]
0x180091802  mov     rax, [rax+28h]
0x180091806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009180b  mov     rcx, qword ptr [rsp+2B0h+packageFamilyNameLength]
0x180091810  mov     ebx, eax
0x180091812  mov     rax, [rcx]
0x180091815  mov     rax, [rax+10h]
0x180091819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009181e  mov     rdi, [r14]
0x180091821  test    rdi, rdi
0x180091824  jz      short loc_18009182E
0x180091826  test    ebx, ebx
0x180091828  jz      loc_1800918F1
0x18009182e  mov     eax, cs:dword_18014E4B8
0x180091834  test    eax, eax
0x180091836  jnz     short loc_18009184C
0x180091838  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x18009183f  jz      short loc_18009188D
0x180091841  xor     ecx, ecx
0x180091843  call    IsWppLevelEnabled
0x180091848  test    al, al
0x18009184a  jz      short loc_18009188D
0x18009184c  lea     rdx, [rsi+0C4h]; struct _GUID *
0x180091853  lea     rcx, [rbp+1B0h+packageFamilyName]; this
0x180091857  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x18009185c  mov     [rsp+2B0h+var_280], ebx
0x180091860  lea     rdx, aCappiddataLoad; "CAppidData::Load"
0x180091867  mov     [rsp+2B0h+var_288], rax
0x18009186c  lea     rcx, aOnecoreComComb_27; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180091873  lea     rax, aAppidWsHresult; "APPID:%ws %!HRESULT!"
0x18009187a  xor     r9d, r9d
0x18009187d  mov     r8d, 98Fh
0x180091883  mov     [rsp+2B0h+var_290], rax
0x180091888  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x18009188d  mov     ebx, 80040154h
0x180091892  mov     rcx, rsi; this
0x180091895  call    ?Purge@CAppidData@@QEAAXXZ; CAppidData::Purge(void)
0x18009189a  mov     rcx, [rsi+0D8h]
0x1800918a1  test    rcx, rcx
0x1800918a4  jz      short loc_1800918B9
0x1800918a6  mov     rax, [rcx]
0x1800918a9  mov     rax, [rax+10h]
0x1800918ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800918b2  mov     [rsi+0D8h], r15
0x1800918b9  lea     rcx, [rbp+1B0h+var_228]
0x1800918bd  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x1800918c2  mov     eax, ebx
0x1800918c4  mov     rcx, [rbp+1B0h+var_40]
0x1800918cb  xor     rcx, rsp; StackCookie
0x1800918ce  call    __security_check_cookie
0x1800918d3  mov     rbx, [rsp+2B0h+arg_8]
0x1800918db  add     rsp, 280h
0x1800918e2  pop     r15
0x1800918e4  pop     r14
0x1800918e6  pop     r13
0x1800918e8  pop     r12
0x1800918ea  pop     rdi
0x1800918eb  pop     rsi
0x1800918ec  pop     rbp
0x1800918ed  retn
0x1800918ee  xor     r15d, r15d
0x1800918f1  mov     rcx, [rbp+1B0h+var_228]
0x1800918f5  mov     [rbp+1B0h+var_228], r15
0x1800918f9  test    rcx, rcx
0x1800918fc  jz      short loc_18009190A
0x1800918fe  mov     rax, [rcx]
0x180091901  mov     rax, [rax+10h]
0x180091905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009190a  mov     rax, [rdi]
0x18009190d  lea     r8, [rbp+1B0h+var_228]
0x180091911  lea     rdx, _GUID_430be197_0244_2f7b_80fd_c7c473983ad0
0x180091918  mov     rcx, rdi
0x18009191b  mov     rax, [rax]
0x18009191e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091923  mov     ebx, eax
0x180091925  test    eax, eax
0x180091927  jns     short loc_180091930
0x180091929  mov     edx, 997h
0x18009192e  jmp     short loc_180091952
0x180091930  mov     rcx, [rbp+1B0h+var_228]
0x180091934  lea     rdx, [rsi+120h]
0x18009193b  mov     rax, [rcx]
0x18009193e  mov     rax, [rax+18h]
0x180091942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091947  mov     ebx, eax
0x180091949  test    eax, eax
0x18009194b  jns     short loc_18009196D
0x18009194d  mov     edx, 999h; void *
0x180091952  mov     rcx, [rbp+1B8h]; this
0x180091959  lea     r8, aOnecoreComComb_27; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180091960  mov     r9d, eax; char *
0x180091963  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180091968  jmp     loc_1800918B9
0x18009196d  mov     rdi, [rbp+1B0h+var_228]
0x180091971  lea     r14, [rsi+0F8h]
0x180091978  xor     edx, edx
0x18009197a  mov     rcx, r14
0x18009197d  mov     rax, [rdi]
0x180091980  mov     rbx, [rax+20h]
0x180091984  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180091989  mov     rdx, r14
0x18009198c  mov     rcx, rdi
0x18009198f  mov     rax, rbx
0x180091992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091997  mov     ebx, eax
0x180091999  test    eax, eax
0x18009199b  jns     short loc_1800919A4
0x18009199d  mov     edx, 9A4h
0x1800919a2  jmp     short loc_180091952
0x1800919a4  lea     rdi, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800919ab  mov     rcx, rdi
0x1800919ae  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800919b3  test    al, al
0x1800919b5  jz      short loc_1800919E3
0x1800919b7  lea     rbx, [rsi+100h]
0x1800919be  xor     edx, edx
0x1800919c0  mov     rcx, rbx
0x1800919c3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800919c8  mov     rcx, [r14]; HSTRING
0x1800919cb  mov     rdx, rbx; HSTRING *
0x1800919ce  call    ?NormalizePackageNameCasing_nothrow@@YAJPEAUHSTRING__@@PEAPEAU1@@Z; NormalizePackageNameCasing_nothrow(HSTRING__ *,HSTRING__ * *)
0x1800919d3  mov     ebx, eax
0x1800919d5  test    eax, eax
0x1800919d7  jns     short loc_1800919E3
0x1800919d9  mov     edx, 9A7h
0x1800919de  jmp     loc_180091952
0x1800919e3  mov     rcx, [rbp+1B0h+var_228]
0x1800919e7  lea     rdx, [rsi+108h]
0x1800919ee  mov     rax, [rcx]
0x1800919f1  mov     rax, [rax+28h]
0x1800919f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800919fa  mov     ebx, eax
0x1800919fc  test    eax, eax
0x1800919fe  jns     short loc_180091A0A
0x180091a00  mov     edx, 9AAh
0x180091a05  jmp     loc_180091952
0x180091a0a  mov     ecx, [rsi+120h]
0x180091a10  lea     rdx, [rsi+60h]
0x180091a14  mov     r13d, 1
0x180091a1a  lea     eax, [rcx-1]
0x180091a1d  cmp     eax, r13d
0x180091a20  setbe   al
0x180091a23  cmp     ecx, r13d
0x180091a26  mov     rcx, [rsi+0D8h]
0x180091a2d  mov     [rsi+130h], al
0x180091a33  setz    al
0x180091a36  mov     [rsi+131h], al
0x180091a3c  mov     rax, [rcx]
0x180091a3f  mov     rax, [rax+48h]
0x180091a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091a48  test    eax, eax
0x180091a4a  jz      short loc_180091A50
0x180091a4c  mov     [rsi+60h], r15d
0x180091a50  mov     rcx, [rsi+0D8h]
0x180091a57  lea     rdx, [rbp+1B0h+var_230]
0x180091a5b  mov     rax, [rcx]
0x180091a5e  mov     rax, [rax+28h]
0x180091a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091a67  test    eax, eax
0x180091a69  jz      short loc_180091A6F
0x180091a6b  mov     [rbp+1B0h+var_230], r15d
0x180091a6f  mov     rcx, rdi
0x180091a72  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180091a77  test    al, al
0x180091a79  jz      short loc_180091A8E
0x180091a7b  mov     eax, [rbp+1B0h+var_230]
0x180091a7e  add     eax, 0FFFFFFFEh
0x180091a81  test    eax, 0FFFFFFFDh
0x180091a86  setz    al
0x180091a89  mov     [rsi+74h], al
0x180091a8c  jmp     short loc_180091A9B
0x180091a8e  cmp     [rbp+1B0h+var_230], 2
0x180091a92  mov     eax, r15d
0x180091a95  setz    al
0x180091a98  mov     [rsi+70h], eax
0x180091a9b  mov     rcx, [rsi+0D8h]
0x180091aa2  lea     rdx, [rsi+68h]
0x180091aa6  mov     rax, [rcx]
0x180091aa9  mov     rax, [rax+90h]
0x180091ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091ab5  test    eax, eax
0x180091ab7  jz      short loc_180091ABD
0x180091ab9  mov     [rsi+68h], r15
0x180091abd  mov     rcx, [rsi+0D8h]
0x180091ac4  lea     r8, [rbp+1B0h+var_210]
0x180091ac8  lea     rdx, [rsi+30h]
0x180091acc  mov     rax, [rcx]
  ... truncated ...
```
