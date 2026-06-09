# CAppidData::Load(IComProcessInfo *,ulong,ushort const *,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)

- ea: `0x18009280c`
- end: `0x1800932d9`
- name: `?Load@CAppidData@@QEAAJPEAUIComProcessInfo@@KPEBG1IQEBQEAUHSTRING__@@I2@Z`
- size: `2765`
- prototype: `__int64 __usercall@<rax>(CAppidData *__hidden this@<rcx>, struct IComProcessInfo *@<rdx>, unsigned int@<r8d>, const unsigned __int16 *@<r9>, const unsigned __int16 *, unsigned int, HSTRING *const, unsigned int, HSTRING *const)`
- caller_count: `5`
- callee_count: `21`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180065988`
- `0x180091b8c`
- `0x1800a505c`
- `0x1800f2970`
- `0x180100298`

## callees

- `0x180003194`
- `0x1800065a4`
- `0x180011db0`
- `0x18001a374`
- `0x18001f340`
- `0x1800210f8`
- `0x180023090`
- `0x180034260`
- `0x180051680`
- `0x180051e0c`
- `0x1800535d0`
- `0x18005c154`
- `0x180074d98`
- `0x18008172c`
- `0x18009280c`
- `0x180095c0c`
- `0x18009979c`
- `0x18009e160`
- `0x1800b05c4`
- `0x1800b7ac0`
- `0x180114010`

## import_xrefs

- `ntdll!RtlCreateVirtualAccountSid` at `0x180093250`
- `ntdll!RtlCreateVirtualAccountSid` at `0x180093250`
- `ntdll!RtlNtStatusToDosError` at `0x180093262`
- `ntdll!RtlNtStatusToDosError` at `0x180093262`
- `ntdll!RtlInitUnicodeString` at `0x18009322f`
- `ntdll!RtlInitUnicodeString` at `0x18009322f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180092d9f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180092d9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093105`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009313f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093105`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009313f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180093189`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180093189`
- `KERNELBASE!FormatApplicationUserModelId` at `0x18009315a`
- `KERNELBASE!FormatApplicationUserModelId` at `0x18009315a`
- `KERNELBASE!LocalAlloc` at `0x180093204`
- `KERNELBASE!LocalAlloc` at `0x180093204`
- `KERNELBASE!PackageFamilyNameFromFullName` at `0x18009311d`
- `KERNELBASE!PackageFamilyNameFromFullName` at `0x18009311d`

## string_xrefs

- `0x1800928f5`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x180092a58`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x180092b46`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18009306b`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x1800932b8`: `onecore\com\combase\rpcss\olescm\clsid.cxx`

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
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
    if ( UserServiceNameIfAvailable >= 0 && (unsigned int)CAppidData::GetRunAsType(this) == 4 )
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
  if ( !(unsigned int)CAppidData::GetRunAsType(this) && (*((_BYTE *)this + 72) & 2) != 0 )
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
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
0x18009280c  mov     [rsp-8+arg_8], rbx
0x180092811  push    rbp
0x180092812  push    rsi
0x180092813  push    rdi
0x180092814  push    r12
0x180092816  push    r13
0x180092818  push    r14
0x18009281a  push    r15
0x18009281c  lea     rbp, [rsp-180h]
0x180092824  sub     rsp, 280h
0x18009282b  mov     rax, cs:__security_cookie
0x180092832  xor     rax, rsp
0x180092835  mov     [rbp+1B0h+var_40], rax
0x18009283c  mov     rax, [rbp+1B0h+arg_40]
0x180092843  xor     ebx, ebx
0x180092845  mov     r13, [rbp+1B0h+arg_30]
0x18009284c  mov     r12d, r8d
0x18009284f  mov     qword ptr [rbp+1B0h+applicationUserModelIdLength], rax
0x180092853  mov     r15, rdx
0x180092856  mov     [rbp+1B0h+var_208], rbx
0x18009285a  mov     rsi, rcx
0x18009285d  mov     [rbp+1B0h+var_230], ebx
0x180092860  mov     [rbp+1B0h+var_220], rbx
0x180092864  mov     [rbp+1B0h+var_210], ebx
0x180092867  mov     [rbp+1B0h+var_228], rbx
0x18009286b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x180092872  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180092877  test    al, al
0x180092879  jnz     short loc_180092889
0x18009287b  mov     eax, r12d
0x18009287e  and     eax, 0FFFFF300h
0x180092883  mov     [rsi+0E0h], eax
0x180092889  lea     r14, [rsi+0D8h]
0x180092890  mov     rdi, [r14]
0x180092893  test    rdi, rdi
0x180092896  jnz     loc_180092ADB
0x18009289c  test    r15, r15
0x18009289f  jz      short loc_1800928BB
0x1800928a1  mov     [r14], r15
0x1800928a4  mov     rcx, r15
0x1800928a7  mov     rax, [r15]
0x1800928aa  mov     rax, [rax+8]
0x1800928ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800928b3  xor     r15d, r15d
0x1800928b6  jmp     loc_180092A0A
0x1800928bb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800928c2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800928c7  xor     r15d, r15d
0x1800928ca  lea     rdx, [rsp+2B0h+packageFamilyNameLength]
0x1800928cf  mov     qword ptr [rsp+2B0h+packageFamilyNameLength], r15
0x1800928d4  test    al, al
0x1800928d6  jz      loc_18009297B
0x1800928dc  lea     rcx, _GUID_bcf8570c_b66f_4849_aa7a_94d710f655bf
0x1800928e3  call    GetComCatalogObject
0x1800928e8  mov     ebx, eax
0x1800928ea  test    eax, eax
0x1800928ec  jns     short loc_18009290B
0x1800928ee  mov     rcx, [rbp+1B8h]; this
0x1800928f5  lea     r8, aOnecoreComComb_27; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x1800928fc  mov     r9d, eax; char *
0x1800928ff  mov     edx, 967h; void *
0x180092904  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180092909  jmp     short loc_18009296C
0x18009290b  mov     r8d, [rbp+1B0h+arg_38]
0x180092912  lea     rdx, _GUID_000001ed_0000_0000_c000_000000000046
0x180092919  mov     rcx, qword ptr [rsp+2B0h+packageFamilyNameLength]
0x18009291e  lea     r9, [rsi+0C4h]
0x180092925  mov     [rsp+2B0h+var_258], r14
0x18009292a  mov     [rsp+2B0h+var_260], rdx
0x18009292f  mov     rdx, qword ptr [rbp+1B0h+applicationUserModelIdLength]
0x180092933  mov     rax, [rcx]
0x180092936  mov     [rsp+2B0h+var_268], rdx
0x18009293b  mov     edx, r12d
0x18009293e  mov     [rsp+2B0h+var_270], r8d
0x180092943  mov     r8d, [rbp+1B0h+arg_28]
0x18009294a  mov     rax, [rax+20h]
0x18009294e  mov     [rsp+2B0h+var_278], r13
0x180092953  mov     [rsp+2B0h+var_280], r8d
0x180092958  mov     r8, [rsi]
0x18009295b  mov     [rsp+2B0h+var_288], r15
0x180092960  mov     [rsp+2B0h+var_290], r15
0x180092965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009296a  mov     ebx, eax
0x18009296c  lea     rcx, [rsp+2B0h+packageFamilyNameLength]
0x180092971  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x180092976  jmp     loc_180092A0A
0x18009297b  cmp     [rsi], r15
0x18009297e  jz      short loc_1800929C3
0x180092980  lea     rcx, _GUID_000001fd_0000_0000_c000_000000000046
0x180092987  call    GetComCatalogObject
0x18009298c  mov     ebx, eax
0x18009298e  test    eax, eax
0x180092990  js      short loc_180092A0A
0x180092992  mov     rcx, qword ptr [rsp+2B0h+packageFamilyNameLength]
0x180092997  lea     r8, IID_IComProcessInfo
0x18009299e  mov     [rsp+2B0h+var_288], r14
0x1800929a3  lea     r9, [rsi+0C4h]
0x1800929aa  mov     [rsp+2B0h+var_290], r8
0x1800929af  mov     edx, r12d
0x1800929b2  mov     r8, [rsi]
0x1800929b5  mov     rax, [rcx]
0x1800929b8  mov     rax, [rax+28h]
0x1800929bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800929c1  jmp     short loc_1800929F7
0x1800929c3  lea     rcx, _GUID_000001e0_0000_0000_c000_000000000046
0x1800929ca  call    GetComCatalogObject
0x1800929cf  mov     ebx, eax
0x1800929d1  test    eax, eax
0x1800929d3  js      short loc_180092A0A
0x1800929d5  mov     rcx, qword ptr [rsp+2B0h+packageFamilyNameLength]
0x1800929da  lea     rdx, [rsi+0C4h]
0x1800929e1  mov     r9, r14
0x1800929e4  lea     r8, IID_IComProcessInfo
0x1800929eb  mov     rax, [rcx]
0x1800929ee  mov     rax, [rax+28h]
0x1800929f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800929f7  mov     rcx, qword ptr [rsp+2B0h+packageFamilyNameLength]
0x1800929fc  mov     ebx, eax
0x1800929fe  mov     rax, [rcx]
0x180092a01  mov     rax, [rax+10h]
0x180092a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092a0a  mov     rdi, [r14]
0x180092a0d  test    rdi, rdi
0x180092a10  jz      short loc_180092A1A
0x180092a12  test    ebx, ebx
0x180092a14  jz      loc_180092ADE
0x180092a1a  mov     eax, cs:dword_1801574B8
0x180092a20  test    eax, eax
0x180092a22  jnz     short loc_180092A38
0x180092a24  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x180092a2b  jz      short loc_180092A79
0x180092a2d  xor     ecx, ecx
0x180092a2f  call    IsWppLevelEnabled
0x180092a34  test    al, al
0x180092a36  jz      short loc_180092A79
0x180092a38  lea     rdx, [rsi+0C4h]; struct _GUID *
0x180092a3f  lea     rcx, [rbp+1B0h+packageFamilyName]; this
0x180092a43  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x180092a48  mov     [rsp+2B0h+var_280], ebx
0x180092a4c  lea     rdx, aCappiddataLoad; "CAppidData::Load"
0x180092a53  mov     [rsp+2B0h+var_288], rax
0x180092a58  lea     rcx, aOnecoreComComb_27; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180092a5f  lea     rax, aAppidWsHresult; "APPID:%ws %!HRESULT!"
0x180092a66  xor     r9d, r9d
0x180092a69  mov     r8d, 98Fh
0x180092a6f  mov     [rsp+2B0h+var_290], rax
0x180092a74  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x180092a79  mov     ebx, 80040154h
0x180092a7e  mov     rcx, rsi; this
0x180092a81  call    ?Purge@CAppidData@@QEAAXXZ; CAppidData::Purge(void)
0x180092a86  mov     rcx, [rsi+0D8h]
0x180092a8d  test    rcx, rcx
0x180092a90  jz      short loc_180092AA5
0x180092a92  mov     rax, [rcx]
0x180092a95  mov     rax, [rax+10h]
0x180092a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092a9e  mov     [rsi+0D8h], r15
0x180092aa5  lea     rcx, [rbp+1B0h+var_228]
0x180092aa9  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x180092aae  mov     eax, ebx
0x180092ab0  mov     rcx, [rbp+1B0h+var_40]
0x180092ab7  xor     rcx, rsp; StackCookie
0x180092aba  call    __security_check_cookie
0x180092abf  mov     rbx, [rsp+2B0h+arg_8]
0x180092ac7  add     rsp, 280h
0x180092ace  pop     r15
0x180092ad0  pop     r14
0x180092ad2  pop     r13
0x180092ad4  pop     r12
0x180092ad6  pop     rdi
0x180092ad7  pop     rsi
0x180092ad8  pop     rbp
0x180092ad9  retn
0x180092adb  xor     r15d, r15d
0x180092ade  mov     rcx, [rbp+1B0h+var_228]
0x180092ae2  mov     [rbp+1B0h+var_228], r15
0x180092ae6  test    rcx, rcx
0x180092ae9  jz      short loc_180092AF7
0x180092aeb  mov     rax, [rcx]
0x180092aee  mov     rax, [rax+10h]
0x180092af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092af7  mov     rax, [rdi]
0x180092afa  lea     r8, [rbp+1B0h+var_228]
0x180092afe  lea     rdx, _GUID_430be197_0244_2f7b_80fd_c7c473983ad0
0x180092b05  mov     rcx, rdi
0x180092b08  mov     rax, [rax]
0x180092b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092b10  mov     ebx, eax
0x180092b12  test    eax, eax
0x180092b14  jns     short loc_180092B1D
0x180092b16  mov     edx, 997h
0x180092b1b  jmp     short loc_180092B3F
0x180092b1d  mov     rcx, [rbp+1B0h+var_228]
0x180092b21  lea     rdx, [rsi+120h]
0x180092b28  mov     rax, [rcx]
0x180092b2b  mov     rax, [rax+18h]
0x180092b2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092b34  mov     ebx, eax
0x180092b36  test    eax, eax
0x180092b38  jns     short loc_180092B5A
0x180092b3a  mov     edx, 999h; void *
0x180092b3f  mov     rcx, [rbp+1B8h]; this
0x180092b46  lea     r8, aOnecoreComComb_27; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180092b4d  mov     r9d, eax; char *
0x180092b50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180092b55  jmp     loc_180092AA5
0x180092b5a  mov     rdi, [rbp+1B0h+var_228]
0x180092b5e  lea     r14, [rsi+0F8h]
0x180092b65  xor     edx, edx
0x180092b67  mov     rcx, r14
0x180092b6a  mov     rax, [rdi]
0x180092b6d  mov     rbx, [rax+20h]
0x180092b71  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180092b76  mov     rdx, r14
0x180092b79  mov     rcx, rdi
0x180092b7c  mov     rax, rbx
0x180092b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092b84  mov     ebx, eax
0x180092b86  test    eax, eax
0x180092b88  jns     short loc_180092B91
0x180092b8a  mov     edx, 9A4h
0x180092b8f  jmp     short loc_180092B3F
0x180092b91  lea     rdi, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x180092b98  mov     rcx, rdi
0x180092b9b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180092ba0  test    al, al
0x180092ba2  jz      short loc_180092BD0
0x180092ba4  lea     rbx, [rsi+100h]
0x180092bab  xor     edx, edx
0x180092bad  mov     rcx, rbx
0x180092bb0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180092bb5  mov     rcx, [r14]; HSTRING
0x180092bb8  mov     rdx, rbx; HSTRING *
0x180092bbb  call    ?NormalizePackageNameCasing_nothrow@@YAJPEAUHSTRING__@@PEAPEAU1@@Z; NormalizePackageNameCasing_nothrow(HSTRING__ *,HSTRING__ * *)
0x180092bc0  mov     ebx, eax
0x180092bc2  test    eax, eax
0x180092bc4  jns     short loc_180092BD0
0x180092bc6  mov     edx, 9A7h
0x180092bcb  jmp     loc_180092B3F
0x180092bd0  mov     rcx, [rbp+1B0h+var_228]
0x180092bd4  lea     rdx, [rsi+108h]
0x180092bdb  mov     rax, [rcx]
0x180092bde  mov     rax, [rax+28h]
0x180092be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092be7  mov     ebx, eax
0x180092be9  test    eax, eax
0x180092beb  jns     short loc_180092BF7
0x180092bed  mov     edx, 9AAh
0x180092bf2  jmp     loc_180092B3F
0x180092bf7  mov     ecx, [rsi+120h]
0x180092bfd  lea     rdx, [rsi+60h]
0x180092c01  mov     r13d, 1
0x180092c07  lea     eax, [rcx-1]
0x180092c0a  cmp     eax, r13d
0x180092c0d  setbe   al
0x180092c10  cmp     ecx, r13d
0x180092c13  mov     rcx, [rsi+0D8h]
0x180092c1a  mov     [rsi+130h], al
0x180092c20  setz    al
0x180092c23  mov     [rsi+131h], al
0x180092c29  mov     rax, [rcx]
0x180092c2c  mov     rax, [rax+48h]
0x180092c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092c35  test    eax, eax
0x180092c37  jz      short loc_180092C3D
0x180092c39  mov     [rsi+60h], r15d
0x180092c3d  mov     rcx, [rsi+0D8h]
0x180092c44  lea     rdx, [rbp+1B0h+var_230]
0x180092c48  mov     rax, [rcx]
0x180092c4b  mov     rax, [rax+28h]
0x180092c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092c54  test    eax, eax
0x180092c56  jz      short loc_180092C5C
0x180092c58  mov     [rbp+1B0h+var_230], r15d
0x180092c5c  mov     rcx, rdi
0x180092c5f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180092c64  test    al, al
0x180092c66  jz      short loc_180092C7B
0x180092c68  mov     eax, [rbp+1B0h+var_230]
0x180092c6b  add     eax, 0FFFFFFFEh
0x180092c6e  test    eax, 0FFFFFFFDh
0x180092c73  setz    al
0x180092c76  mov     [rsi+74h], al
0x180092c79  jmp     short loc_180092C88
0x180092c7b  cmp     [rbp+1B0h+var_230], 2
0x180092c7f  mov     eax, r15d
0x180092c82  setz    al
0x180092c85  mov     [rsi+70h], eax
0x180092c88  mov     rcx, [rsi+0D8h]
0x180092c8f  lea     rdx, [rsi+68h]
0x180092c93  mov     rax, [rcx]
0x180092c96  mov     rax, [rax+90h]
0x180092c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092ca2  test    eax, eax
0x180092ca4  jz      short loc_180092CAA
0x180092ca6  mov     [rsi+68h], r15
0x180092caa  mov     rcx, [rsi+0D8h]
0x180092cb1  lea     r8, [rbp+1B0h+var_210]
0x180092cb5  lea     rdx, [rsi+30h]
0x180092cb9  mov     rax, [rcx]
  ... truncated ...
```
