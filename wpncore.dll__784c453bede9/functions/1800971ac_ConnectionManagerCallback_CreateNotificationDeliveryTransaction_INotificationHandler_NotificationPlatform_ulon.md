# ConnectionManagerCallback::CreateNotificationDeliveryTransaction(INotificationHandler *,NotificationPlatform *,ulong,double,ushort const *,unsigned __int64,char const *,__MIDL___MIDL_itf_wpntypes_0000_0000_0005,__MIDL___MIDL_itf_wpnplatform_0000_0007_0005,__MIDL___MIDL_itf_wpntypes_0000_0000_0007,double,ushort const *,ushort const *,ushort const *,ulong,int,ushort const *,uchar *,uint,int,std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> &,__MIDL___MIDL_itf_wpntypes_0000_0000_0006,ushort const *,std::unique_ptr<NotificationDeliveryTransaction,std::default_delete<NotificationDeliveryTransaction>> &)

- ea: `0x1800971ac`
- end: `0x180097e89`
- name: `?CreateNotificationDeliveryTransaction@ConnectionManagerCallback@@CAJPEAUINotificationHandler@@PEAVNotificationPlatform@@KNPEBG_KPEBDW4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@W4__MIDL___MIDL_itf_wpnplatform_0000_0007_0005@@W4__MIDL___MIDL_itf_wpntypes_0000_0000_0007@@N222KH2PEAEIHAEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@W4__MIDL___MIDL_itf_wpntypes_0000_0000_0006@@2AEAV?$unique_ptr@VNotificationDeliveryTransaction@@U?$default_delete@VNotificationDeliveryTransaction@@@std@@@8@@Z`
- size: `3293`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, int, int, char, DOUBLE vtime, __int64, __int64, __int64, char, char, __int64, __int64, int, int, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800e8780`

## callees

- `0x180004e38`
- `0x18000de40`
- `0x18000e090`
- `0x18000e5f4`
- `0x180011618`
- `0x1800117c0`
- `0x180014120`
- `0x18001a40c`
- `0x18001bf30`
- `0x18002ab88`
- `0x180037270`
- `0x180045ab4`
- `0x1800535d0`
- `0x1800542a8`
- `0x18006e48c`
- `0x18006e4c4`
- `0x18006e700`
- `0x18007ce88`
- `0x18009574c`
- `0x180096738`
- `0x1800971ac`
- `0x180097e90`
- `0x180097eb8`
- `0x180097f6c`
- `0x180097fa0`
- `0x1800b99f0`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180097c58`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180097c58`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180097599`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180097605`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180097599`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180097605`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x180097516`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x1800975e2`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x180097516`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x1800975e2`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180097829`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180097829`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall ConnectionManagerCallback::CreateNotificationDeliveryTransaction(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        DOUBLE a4,
        __int64 a5,
        BYTE *a6,
        __int64 a7,
        int a8,
        unsigned int a9,
        char a10,
        DOUBLE vtime,
        _WORD *a12,
        _WORD *a13,
        _WORD *a14,
        char a15,
        char a16,
        __int64 a17,
        BYTE *a18,
        UINT a19,
        int a20,
        __int64 a21,
        unsigned int a22,
        __int64 a23,
        __int64 a24)
{
  int v26; // ecx
  _WORD *v27; // r14
  _WORD *v28; // rsi
  _WORD *v29; // rdi
  WpnDatabaseHelpers *v30; // rdx
  __int64 (__fastcall *v31)(__int64, WpnDatabaseHelpers **); // rbx
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // ebx
  __int64 v36; // rdi
  __int64 (__fastcall *v37)(__int64, _QWORD, __int64 *); // rbx
  __int64 v38; // r12
  int v39; // eax
  int v40; // eax
  int v41; // eax
  unsigned int v42; // ebx
  int v43; // eax
  __int64 (__fastcall *v44)(__int64, unsigned __int16 **); // rbx
  int v45; // eax
  unsigned __int16 **v46; // r8
  int PraidFromSecondaryId; // eax
  int v48; // eax
  _QWORD *v49; // rdi
  _QWORD *i; // rbx
  _QWORD *v51; // rdx
  _QWORD *v52; // r8
  int v53; // eax
  IStream *v54; // rax
  __int64 v55; // rax
  unsigned int v56; // ebx
  _QWORD *v57; // rax
  bool v58; // zf
  _QWORD *v59; // rax
  _QWORD *v60; // rax
  int v61; // eax
  HRESULT v62; // eax
  int v63; // eax
  __int64 v64; // rax
  const char *v65; // r9
  __int64 result; // rax
  int v67; // [rsp+20h] [rbp-2C8h]
  int v68; // [rsp+20h] [rbp-2C8h]
  _BYTE v69[8]; // [rsp+50h] [rbp-298h] BYREF
  __int64 v70; // [rsp+58h] [rbp-290h] BYREF
  UINT cbInit; // [rsp+60h] [rbp-288h] BYREF
  unsigned __int16 *v72; // [rsp+68h] [rbp-280h] BYREF
  __int64 v73; // [rsp+70h] [rbp-278h] BYREF
  int v74; // [rsp+78h] [rbp-270h]
  unsigned int v75; // [rsp+7Ch] [rbp-26Ch]
  unsigned int v76; // [rsp+80h] [rbp-268h]
  WpnDatabaseHelpers *v77; // [rsp+88h] [rbp-260h] BYREF
  __int64 v78; // [rsp+90h] [rbp-258h] BYREF
  __int64 v79; // [rsp+98h] [rbp-250h] BYREF
  __int128 v80; // [rsp+A0h] [rbp-248h]
  __int128 v81; // [rsp+B0h] [rbp-238h]
  __int128 v82; // [rsp+C0h] [rbp-228h]
  __int128 v83; // [rsp+D0h] [rbp-218h]
  __int128 v84; // [rsp+E0h] [rbp-208h]
  __int128 v85; // [rsp+F0h] [rbp-1F8h]
  __m256i v86; // [rsp+100h] [rbp-1E8h]
  struct _FILETIME v87; // [rsp+130h] [rbp-1B8h] BYREF
  struct _FILETIME FileTime; // [rsp+138h] [rbp-1B0h] BYREF
  __int64 v89; // [rsp+140h] [rbp-1A8h] BYREF
  __int64 v90; // [rsp+148h] [rbp-1A0h] BYREF
  __int64 v91; // [rsp+150h] [rbp-198h] BYREF
  __int64 v92; // [rsp+158h] [rbp-190h] BYREF
  _QWORD v93[3]; // [rsp+160h] [rbp-188h] BYREF
  unsigned __int16 v94[4]; // [rsp+178h] [rbp-170h] BYREF
  __int64 v95; // [rsp+180h] [rbp-168h]
  __int64 v96; // [rsp+188h] [rbp-160h]
  __int64 v97; // [rsp+190h] [rbp-158h] BYREF
  __int64 v98; // [rsp+198h] [rbp-150h]
  BYTE *pInit[2]; // [rsp+1A0h] [rbp-148h] BYREF
  _QWORD v100[3]; // [rsp+1B0h] [rbp-138h] BYREF
  unsigned __int64 v101; // [rsp+1C8h] [rbp-120h]
  _OWORD v102[6]; // [rsp+1D0h] [rbp-118h] BYREF
  __m256i v103; // [rsp+230h] [rbp-B8h]
  __int64 v104; // [rsp+250h] [rbp-98h]
  struct _SYSTEMTIME SystemTime; // [rsp+260h] [rbp-88h] BYREF
  SYSTEMTIME v106; // [rsp+270h] [rbp-78h] BYREF
  GUID pguid; // [rsp+280h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+0h]

  try
  {
    v75 = a3;
    v97 = a5;
    v91 = a7;
    v26 = a8;
    v74 = a8;
    v76 = a9;
    v27 = a12;
    v28 = a13;
    v29 = a14;
    v92 = a17;
    pInit[0] = a18;
    cbInit = a19;
    v79 = a23;
    v98 = a24;
    v30 = 0;
    v77 = 0;
    if ( a1 )
    {
      v31 = *(__int64 (__fastcall **)(__int64, WpnDatabaseHelpers **))(*(_QWORD *)a1 + 24LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v77,
        0);
      v32 = v31(a1, &v77);
      if ( v32 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x276,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\connectionmanagercallbackimpl.cpp",
          (const char *)(unsigned int)v32,
          v67);
      v30 = v77;
      v26 = v74;
    }
    memset(v93, 0, sizeof(v93));
    v78 = 0;
    if ( v30 && *(_WORD *)v30 )
    {
      if ( v29 && *v29 && v26 == 3 )
      {
        v72 = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v72,
          0);
        v33 = ParseAppUserModelId((const unsigned __int16 *)v77, &v72, 0);
        if ( v33 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x286,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\connectionmanagercallbackimpl.cpp",
            (const char *)(unsigned int)v33,
            v67);
        v34 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                v93,
                L"%s!%s",
                v72,
                v29);
        if ( v34 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x287,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\connectionmanagercallbackimpl.cpp",
            (const char *)(unsigned int)v34,
            v67);
        v70 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v70);
        v35 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(a2 + 144))(
                *(_QWORD *)(a2 + 144),
                &GUID_145e48ec_626a_4302_9000_36e8172c6d29,
                &v70);
        if ( v35 >= 0 && !v70 )
        {
          v35 = -2143420155;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x400,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
            (const char *)0x803E0105LL,
            v67);
        }
        if ( v35 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x289,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\connectionmanagercallbackimpl.cpp",
            (const char *)(unsigned int)v35,
            v67);
        v36 = v70;
        v37 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v70 + 192LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v78);
        v38 = v93[0];
        v39 = v37(v36, v93[0], &v78);
        if ( v39 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x28A,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\connectionmanagercallbackimpl.cpp",
            (const char *)(unsigned int)v39,
            v67);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v70);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v72);
LABEL_27:
        SystemTime = 0;
        if ( VariantTimeToSystemTime(a4, &SystemTime) != 1 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x294,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\connectionmanagercallbackimpl.cpp",
            (const char *)0x80070057LL,
            v67);
        FileTime = 0;
        if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x296,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\connectionmanagercallbackimpl.cpp",
            (const char *)0x80070057LL,
            v67);
        v106 = 0;
        v87 = 0;
        if ( VariantTimeToSystemTime(vtime, &v106) == 1 && !SystemTimeToFileTime(&v106, &v87) )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x29F,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\connectionmanagercallbackimpl.cpp",
            (const char *)0x80070057LL,
            v67);
        v73 = 0;
        v42 = v74;
        if ( v74 == 4 )
        {
          LODWORD(v70) = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
          v43 = Microsoft::WRL::Details::MakeAndInitialize<WpnNotificationData,WpnNotificationData,int>(&v73, &v70);
          if ( v43 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x2A6,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\connectionmanagercallbackimpl.cpp",
              (const char *)(unsigned int)v43,
              v67);
          if ( a1 )
          {
            v72 = 0;
            v44 = *(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)a1 + 40LL);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &v72,
              0);
            v45 = v44(a1, &v72);
            if ( v45 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x2AB,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\connectionmanagercallbackimpl.cpp",
                (const char *)(unsigned int)v45,
                v67);
            if ( v72 && *v72 )
            {
              *(_QWORD *)v94 = 0;
              v95 = 0;
              v96 = 0;
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v94);
              v95 = -1;
              v96 = -1;
              PraidFromSecondaryId = WpnDatabaseHelpers::GetPraidFromSecondaryId(v77, v94, v46);
              if ( PraidFromSecondaryId < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x2B0,
                  (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\connectionmanagercallbackimpl.cpp",
                  (const char *)(unsigned int)PraidFromSecondaryId,
                  v67);
              v48 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _QWORD))(*(_QWORD *)(v73 + 32) + 40LL))(
                      v73 + 32,
                      L"SecondaryChannelId",
                      *(_QWORD *)v94);
              if ( v48 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x2B1,
                  (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\connectionmanagercallbackimpl.cpp",
                  (const char *)(unsigned int)v48,
                  v67);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v94);
            }
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v72);
          }
          v49 = *(_QWORD **)(a21 + 8);
          for ( i = (_QWORD *)*v49; i != v49; i = (_QWORD *)*i )
          {
            v51 = i + 2;
            v52 = i + 6;
            if ( i[9] > 7u )
              v52 = (_QWORD *)*v52;
            if ( i[5] > 7u )
              v51 = (_QWORD *)*v51;
            v53 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD *))(*(_QWORD *)(v73 + 32) + 40LL))(
                    v73 + 32,
                    v51,
                    v52);
            if ( v53 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x2B8,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\connectionmanagercallbackimpl.cpp",
                (const char *)(unsigned int)v53,
                v67);
          }
          v42 = v74;
        }
        v70 = 0;
        v54 = SHCreateMemStream(pInit[0], cbInit);
        Microsoft::WRL::ComPtr<WNSChannelDetails>::Attach(&v70, v54);
        v55 = WpnDatabaseHelpers::NotificationTypeNameFromValue(v42);
        std::wstring::wstring(v100, v55);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID54436891>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID54436891>::GetImpl'::`2'::impl) )
        {
          if ( v42 == 4 )
          {
            v56 = a22;
            if ( a22 != 1 )
            {
              *(_QWORD *)&v80 = v75;
              *((_QWORD *)&v80 + 1) = v38;
              v57 = v100;
              if ( v101 > 7 )
                v57 = (_QWORD *)v100[0];
              *(_QWORD *)&v81 = v57;
              *((_QWORD *)&v81 + 1) = ConnectionManagerCallback::GetPayloadTypeStringFromPayloadType(v76);
              *(_QWORD *)&v82 = v70;
              if ( !v27 || (v58 = *v27 == 0, *((_QWORD *)&v82 + 1) = v27, v58) )
                *((_QWORD *)&v82 + 1) = 0;
              if ( !v28 || (v58 = *v28 == 0, *(_QWORD *)&v83 = v28, v58) )
                *(_QWORD *)&v83 = 0;
              *((struct _FILETIME *)&v83 + 1) = v87;
              v84 = (unsigned __int64)FileTime;
              *(_QWORD *)&v85 = GetLastBootTime();
              *(_DWORD *)((char *)&v85 + 9) = 0;
              *(_WORD *)((char *)&v85 + 13) = 0;
              HIBYTE(v85) = 0;
              v86.m256i_i64[0] = v73;
              v86.m256i_i64[3] = v56;
              v104 = v79;
              goto LABEL_90;
            }
          }
          *(_QWORD *)&v80 = v75;
          *((_QWORD *)&v80 + 1) = v38;
          v59 = v100;
          if ( v101 > 7 )
            v59 = (_QWORD *)v100[0];
          *(_QWORD *)&v81 = v59;
          *((_QWORD *)&v81 + 1) = ConnectionManagerCallback::GetPayloadTypeStringFromPayloadType(v76);
          *(_QWORD *)&v82 = v70;
          if ( !v27 || (v58 = *v27 == 0, *((_QWORD *)&v82 + 1) = v27, v58) )
            *((_QWORD *)&v82 + 1) = 0;
          if ( !v28 || (v58 = *v28 == 0, *(_QWORD *)&v83 = v28, v58) )
            *(_QWORD *)&v83 = 0;
        }
        else
        {
          *(_QWORD *)&v80 = v75;
          *((_QWORD *)&v80 + 1) = v38;
          v60 = v100;
          if ( v101 > 7 )
            v60 = (_QWORD *)v100[0];
          *(_QWORD *)&v81 = v60;
          *((_QWORD *)&v81 + 1) = ConnectionManagerCallback::GetPayloadTypeStringFromPayloadType(v76);
          *(_QWORD *)&v82 = v70;
          if ( !v27 || (v58 = *v27 == 0, *((_QWORD *)&v82 + 1) = v27, v58) )
            *((_QWORD *)&v82 + 1) = 0;
          if ( !v28 || (v58 = *v28 == 0, *(_QWORD *)&v83 = v28, v58) )
            *(_QWORD *)&v83 = 0;
        }
        *((struct _FILETIME *)&v83 + 1) = v87;
        v84 = (unsigned __int64)FileTime;
        *(_QWORD *)&v85 = GetLastBootTime();
        *(_DWORD *)((char *)&v85 + 9) = 0;
        *(_WORD *)((char *)&v85 + 13) = 0;
        HIBYTE(v85) = 0;
        v104 = 0;
        v86.m256i_i64[3] = 1;
        v86.m256i_i64[0] = v73;
LABEL_90:
        *(GUID *)&v86.m256i_u64[1] = GUID_NULL;
        v102[0] = v80;
        v102[1] = v81;
        v102[2] = v82;
        v102[3] = v83;
        BYTE8(v85) = 0;
        v102[4] = v84;
        v102[5] = v85;
        v103 = v86;
        v90 = 0;
        v61 = Microsoft::WRL::Details::MakeAndInitialize<Notification,Notification,Notification::Initializer &>(
                &v90,
                v102);
        if ( v61 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x307,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\connectionmanagercallbackimpl.cpp",
            (const char *)(unsigned int)v61,
            v67);
        pguid = GUID_NULL;
        v62 = CoCreateGuid(&pguid);
        if ( v62 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x30B,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\connectionmanagercallbackimpl.cpp",
            (const char *)(unsigned int)v62,
            v67);
        pInit[0] = *(BYTE **)&GUID_NULL.Data1;
        pInit[1] = a6;
        v89 = 0;
        v79 = 0;
        cbInit = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v89);
        v63 = Microsoft::WRL::Details::MakeAndInitialize<TransientNotificationDetails,TransientNotificationDetails,unsigned long &,unsigned short * &,int &,int &,_GUID &,_GUID &,enum WpnToastNotificationPriority,std::nullptr_t,std::nullptr_t>(
                (unsigned int)&v89,
                (unsigned int)&a15,
                (unsigned int)&v92,
                (unsigned int)&a16,
                (__int64)&a20,
                (__int64)&pguid,
                (__int64)pInit,
                (__int64)&cbInit,
                (__int64)&v91,
                (__int64)&v79);
        if ( v63 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x31C,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\connectionmanagercallbackimpl.cpp",
            (const char *)(unsigned int)v63,
            v68);
        v69[0] = 0;
        v92 = v89;
        v91 = v90;
        v79 = v78;
        v64 = std::make_unique<NotificationDeliveryTransaction,INotificationHandler *,Notification *,TransientNotificationDetails *,bool,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0007 &,unsigned short * &,0>(
                (unsigned int)pInit,
                (unsigned int)&v79,
                (unsigned int)&v91,
                (unsigned int)&v92,
                (__int64)v69,
                (__int64)&a10,
                (__int64)&v97);
        std::unique_ptr<NotificationDeliveryTransaction>::operator=<std::default_delete<NotificationDeliveryTransaction>,0>(
          v98,
          v64);
        std::unique_ptr<NotificationDeliveryTransaction>::~unique_ptr<NotificationDeliveryTransaction>(pInit);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v89);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v90);
        std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(v100);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v70);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v78);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v93);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v77);
        return 0;
      }
      v40 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              (__int64)v93,
              v30,
              0xFFFFFFFFFFFFFFFFuLL);
      if ( v40 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x28E,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\connectionmanagercallbackimpl.cpp",
          (const char *)(unsigned int)v40,
          v67);
      Microsoft::WRL::ComPtr<IStream>::operator=(&v78, a1);
    }
    else
    {
      v41 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              (__int64)v93,
              &word_180124798,
              0xFFFFFFFFFFFFFFFFuLL);
      if ( v41 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x281,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\connectionmanagercallbackimpl.cpp",
          (const char *)(unsigned int)v41,
          v67);
    }
    v38 = v93[0];
    goto LABEL_27;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x326,
                           (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\connectio"
                                         "nmanagercallbackimpl.cpp",
                           v65);
  }
  return result;
}

```

## disassembly

```asm
0x1800971ac  mov     r11, rsp
0x1800971af  push    rbx
0x1800971b0  push    rsi
0x1800971b1  push    rdi
0x1800971b2  push    r12
0x1800971b4  push    r13
0x1800971b6  push    r14
0x1800971b8  push    r15
0x1800971ba  sub     rsp, 2B0h
0x1800971c1  movaps  xmmword ptr [r11-48h], xmm6
0x1800971c6  mov     rax, cs:__security_cookie
0x1800971cd  xor     rax, rsp
0x1800971d0  mov     [rsp+2E8h+var_58], rax
0x1800971d8  movaps  xmm6, xmm3
0x1800971db  mov     [rsp+2E8h+var_26C], r8d
0x1800971e0  mov     r13, rdx
0x1800971e3  mov     r15, rcx
0x1800971e6  mov     rax, [rsp+2E8h+arg_20]
0x1800971ee  mov     [r11-158h], rax
0x1800971f5  mov     rax, [rsp+2E8h+arg_30]
0x1800971fd  mov     [r11-198h], rax
0x180097204  mov     ecx, [rsp+2E8h+arg_38]
0x18009720b  mov     [rsp+2E8h+var_270], ecx
0x18009720f  mov     eax, [rsp+2E8h+arg_40]
0x180097216  mov     [rsp+2E8h+var_268], eax
0x18009721d  mov     r14, [rsp+2E8h+arg_58]
0x180097225  mov     rsi, [rsp+2E8h+arg_60]
0x18009722d  mov     rdi, [rsp+2E8h+arg_68]
0x180097235  mov     rax, [rsp+2E8h+arg_80]
0x18009723d  mov     [r11-190h], rax
0x180097244  mov     rax, [rsp+2E8h+arg_88]
0x18009724c  mov     [rsp+2E8h+pInit], rax
0x180097254  mov     eax, [rsp+2E8h+arg_90]
0x18009725b  mov     [rsp+2E8h+cbInit], eax
0x18009725f  mov     rax, [rsp+2E8h+arg_B0]
0x180097267  mov     [r11-250h], rax
0x18009726e  mov     rax, [rsp+2E8h+arg_B8]
0x180097276  mov     [rsp+2E8h+var_150], rax
0x18009727e  xor     r12d, r12d
0x180097281  mov     edx, r12d
0x180097284  mov     [rsp+2E8h+var_260], rdx
0x18009728c  test    r15, r15
0x18009728f  jz      short loc_1800972E3
0x180097291  mov     rax, [r15]
0x180097294  mov     rbx, [rax+18h]
0x180097298  lea     rcx, [r11-260h]
0x18009729f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800972a4  lea     rdx, [rsp+2E8h+var_260]
0x1800972ac  mov     rcx, r15
0x1800972af  mov     rax, rbx
0x1800972b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800972b7  mov     rcx, [rsp+2E8h]; this
0x1800972bf  test    eax, eax
0x1800972c1  jns     short loc_1800972D7
0x1800972c3  mov     r9d, eax; char *
0x1800972c6  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800972cd  mov     edx, 276h; void *
0x1800972d2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800972d7  mov     rdx, [rsp+2E8h+var_260]
0x1800972df  mov     ecx, [rsp+2E8h+var_270]
0x1800972e3  mov     [rsp+2E8h+var_188], r12
0x1800972eb  mov     [rsp+2E8h+var_180], r12
0x1800972f3  mov     [rsp+2E8h+var_178], r12
0x1800972fb  mov     [rsp+2E8h+var_258], r12
0x180097303  test    rdx, rdx
0x180097306  jz      loc_18009753B
0x18009730c  cmp     r12w, [rdx]
0x180097310  jz      loc_18009753B
0x180097316  test    rdi, rdi
0x180097319  jz      loc_1800974A9
0x18009731f  cmp     r12w, [rdi]
0x180097323  jz      loc_1800974A9
0x180097329  cmp     ecx, 3
0x18009732c  jnz     loc_1800974A9
0x180097332  mov     [rsp+2E8h+var_280], r12
0x180097337  xor     edx, edx
0x180097339  lea     rcx, [rsp+2E8h+var_280]
0x18009733e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180097343  xor     r8d, r8d; unsigned __int16 **
0x180097346  lea     rdx, [rsp+2E8h+var_280]; unsigned __int16 **
0x18009734b  mov     rcx, [rsp+2E8h+var_260]; unsigned __int16 *
0x180097353  call    ?ParseAppUserModelId@@YAJPEBGPEAPEAG1@Z; ParseAppUserModelId(ushort const *,ushort * *,ushort * *)
0x180097358  mov     rcx, [rsp+2E8h]; this
0x180097360  test    eax, eax
0x180097362  jns     short loc_180097378
0x180097364  mov     r9d, eax; char *
0x180097367  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18009736e  mov     edx, 286h; void *
0x180097373  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180097378  mov     r9, rdi
0x18009737b  mov     r8, [rsp+2E8h+var_280]
0x180097380  lea     rdx, aSS_2; "%s!%s"
0x180097387  lea     rcx, [rsp+2E8h+var_188]
0x18009738f  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180097394  mov     rcx, [rsp+2E8h]; this
0x18009739c  test    eax, eax
0x18009739e  jns     short loc_1800973B4
0x1800973a0  mov     r9d, eax; char *
0x1800973a3  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800973aa  mov     edx, 287h; void *
0x1800973af  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800973b4  mov     [rsp+2E8h+var_290], r12
0x1800973b9  lea     rcx, [rsp+2E8h+var_290]
0x1800973be  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800973c3  nop
0x1800973c4  mov     rcx, [r13+90h]
0x1800973cb  mov     rax, [rcx]
0x1800973ce  lea     r8, [rsp+2E8h+var_290]
0x1800973d3  lea     rdx, _GUID_145e48ec_626a_4302_9000_36e8172c6d29
0x1800973da  mov     rax, [rax]
0x1800973dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800973e2  mov     ebx, eax
0x1800973e4  xor     r13d, r13d
0x1800973e7  test    eax, eax
0x1800973e9  js      short loc_180097413
0x1800973eb  cmp     [rsp+2E8h+var_290], r13
0x1800973f0  jnz     short loc_180097413
0x1800973f2  mov     rcx, [rsp+2E8h]; this
0x1800973fa  mov     ebx, 803E0105h
0x1800973ff  mov     r9d, ebx; char *
0x180097402  lea     r8, aOnecoreuapBase_161; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180097409  mov     edx, 400h; void *
0x18009740e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180097413  mov     rcx, [rsp+2E8h]; this
0x18009741b  test    ebx, ebx
0x18009741d  jns     short loc_180097433
0x18009741f  mov     r9d, ebx; char *
0x180097422  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180097429  mov     edx, 289h; void *
0x18009742e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180097433  mov     rdi, [rsp+2E8h+var_290]
0x180097438  mov     rax, [rdi]
0x18009743b  mov     rbx, [rax+0C0h]
0x180097442  lea     rcx, [rsp+2E8h+var_258]
0x18009744a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009744f  lea     r8, [rsp+2E8h+var_258]
0x180097457  mov     r12, [rsp+2E8h+var_188]
0x18009745f  mov     rdx, r12
0x180097462  mov     rcx, rdi
0x180097465  mov     rax, rbx
0x180097468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009746d  mov     rcx, [rsp+2E8h]; this
0x180097475  test    eax, eax
0x180097477  jns     short loc_18009748E
0x180097479  mov     r9d, eax; char *
0x18009747c  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180097483  mov     edx, 28Ah; void *
0x180097488  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009748e  lea     rcx, [rsp+2E8h+var_290]
0x180097493  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180097498  nop
0x180097499  lea     rcx, [rsp+2E8h+var_280]
0x18009749e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800974a3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800974a7  jmp     short loc_1800974F8
0x1800974a9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800974ad  mov     r8, rdi
0x1800974b0  lea     rcx, [rsp+2E8h+var_188]
0x1800974b8  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800974bd  mov     rcx, [rsp+2E8h]; this
0x1800974c5  xor     r13d, r13d
0x1800974c8  test    eax, eax
0x1800974ca  jns     short loc_1800974E0
0x1800974cc  mov     r9d, eax; char *
0x1800974cf  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800974d6  mov     edx, 28Eh; void *
0x1800974db  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800974e0  mov     rdx, r15
0x1800974e3  lea     rcx, [rsp+2E8h+var_258]
0x1800974eb  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x1800974f0  mov     r12, [rsp+2E8h+var_188]
0x1800974f8  xorps   xmm1, xmm1
0x1800974fb  movups  xmmword ptr [rsp+2E8h+SystemTime.wYear], xmm1
0x180097503  mov     rbx, [rsp+2E8h]
0x18009750b  lea     rdx, [rsp+2E8h+SystemTime]; lpSystemTime
0x180097513  movaps  xmm0, xmm6; vtime
0x180097516  call    cs:__imp_VariantTimeToSystemTime
0x18009751c  cmp     eax, 1
0x18009751f  jz      short loc_180097579
0x180097521  mov     r9d, 80070057h; char *
0x180097527  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18009752e  mov     edx, 294h; void *
0x180097533  mov     rcx, rbx; this
0x180097536  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009753b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18009753f  mov     r8, rdi
0x180097542  lea     rdx, word_180124798
0x180097549  lea     rcx, [rsp+2E8h+var_188]
0x180097551  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180097556  mov     rcx, [rsp+2E8h]; this
0x18009755e  xor     r13d, r13d
0x180097561  test    eax, eax
0x180097563  jns     short loc_1800974F0
0x180097565  mov     r9d, eax; char *
0x180097568  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18009756f  mov     edx, 281h; void *
0x180097574  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180097579  mov     qword ptr [rsp+2E8h+FileTime.dwLowDateTime], r13
0x180097581  mov     rbx, [rsp+2E8h]
0x180097589  lea     rdx, [rsp+2E8h+FileTime]; lpFileTime
0x180097591  lea     rcx, [rsp+2E8h+SystemTime]; lpSystemTime
0x180097599  call    cs:__imp_SystemTimeToFileTime
0x18009759f  cmp     eax, 1
0x1800975a2  jz      short loc_1800975BE
0x1800975a4  mov     r9d, 80070057h; char *
0x1800975aa  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800975b1  mov     edx, 296h; void *
0x1800975b6  mov     rcx, rbx; this
0x1800975b9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800975be  xorps   xmm0, xmm0
0x1800975c1  movups  xmmword ptr [rsp+2E8h+var_78.wYear], xmm0
0x1800975c9  mov     qword ptr [rsp+2E8h+var_1B8.dwLowDateTime], r13
0x1800975d1  lea     rdx, [rsp+2E8h+var_78]; lpSystemTime
0x1800975d9  movsd   xmm0, [rsp+2E8h+vtime]; vtime
0x1800975e2  call    cs:__imp_VariantTimeToSystemTime
0x1800975e8  cmp     eax, 1
0x1800975eb  jnz     short loc_18009762A
0x1800975ed  mov     rbx, [rsp+2E8h]
0x1800975f5  lea     rdx, [rsp+2E8h+var_1B8]; lpFileTime
0x1800975fd  lea     rcx, [rsp+2E8h+var_78]; lpSystemTime
0x180097605  call    cs:__imp_SystemTimeToFileTime
0x18009760b  cmp     eax, 1
0x18009760e  jz      short loc_18009762A
0x180097610  mov     r9d, 80070057h; char *
0x180097616  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18009761d  mov     edx, 29Fh; void *
0x180097622  mov     rcx, rbx; this
0x180097625  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009762a  mov     [rsp+2E8h+var_278], r13
0x18009762f  mov     ebx, [rsp+2E8h+var_270]
0x180097633  cmp     ebx, 4
0x180097636  jnz     loc_180097818
0x18009763c  mov     dword ptr [rsp+2E8h+var_290], r13d
0x180097641  lea     rcx, [rsp+2E8h+var_278]
0x180097646  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009764b  lea     rdx, [rsp+2E8h+var_290]
0x180097650  lea     rcx, [rsp+2E8h+var_278]
0x180097655  call    ??$MakeAndInitialize@VWpnNotificationData@@V1@H@Details@WRL@Microsoft@@YAJPEAPEAVWpnNotificationData@@$$QEAH@Z; Microsoft::WRL::Details::MakeAndInitialize<WpnNotificationData,WpnNotificationData,int>(WpnNotificationData * *,int &&)
0x18009765a  mov     rcx, [rsp+2E8h]; this
0x180097662  test    eax, eax
0x180097664  jns     short loc_18009767A
0x180097666  mov     r9d, eax; char *
0x180097669  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180097670  mov     edx, 2A6h; void *
0x180097675  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009767a  test    r15, r15
0x18009767d  jz      loc_1800977AA
0x180097683  mov     [rsp+2E8h+var_280], r13
0x180097688  mov     rax, [r15]
0x18009768b  mov     rbx, [rax+28h]
0x18009768f  xor     edx, edx
0x180097691  lea     rcx, [rsp+2E8h+var_280]
0x180097696  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18009769b  lea     rdx, [rsp+2E8h+var_280]
0x1800976a0  mov     rcx, r15
0x1800976a3  mov     rax, rbx
0x1800976a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800976ab  mov     rcx, [rsp+2E8h]; this
0x1800976b3  test    eax, eax
0x1800976b5  jns     short loc_1800976CB
0x1800976b7  mov     r9d, eax; char *
0x1800976ba  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800976c1  mov     edx, 2ABh; void *
0x1800976c6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800976cb  mov     rax, [rsp+2E8h+var_280]
0x1800976d0  test    rax, rax
0x1800976d3  jz      loc_1800977A0
0x1800976d9  cmp     r13w, [rax]
0x1800976dd  jz      loc_1800977A0
0x1800976e3  mov     qword ptr [rsp+2E8h+var_170], r13
0x1800976eb  mov     [rsp+2E8h+var_168], r13
0x1800976f3  mov     [rsp+2E8h+var_160], r13
0x1800976fb  lea     rcx, [rsp+2E8h+var_170]
0x180097703  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180097708  mov     [rsp+2E8h+var_168], rdi
0x180097710  mov     [rsp+2E8h+var_160], rdi
0x180097718  lea     rdx, [rsp+2E8h+var_170]; unsigned __int16 *
0x180097720  mov     rcx, [rsp+2E8h+var_260]; this
0x180097728  call    ?GetPraidFromSecondaryId@WpnDatabaseHelpers@@YAJPEBGPEAPEAG@Z; WpnDatabaseHelpers::GetPraidFromSecondaryId(ushort const *,ushort * *)
0x18009772d  mov     rcx, [rsp+2E8h]; this
0x180097735  test    eax, eax
0x180097737  jns     short loc_18009774D
0x180097739  mov     r9d, eax; char *
0x18009773c  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180097743  mov     edx, 2B0h; void *
0x180097748  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009774d  mov     rcx, [rsp+2E8h+var_278]
0x180097752  add     rcx, 20h ; ' '
0x180097756  mov     rax, [rcx]
0x180097759  mov     r8, qword ptr [rsp+2E8h+var_170]
0x180097761  lea     rdx, ?SecondaryChannelId@PayloadPropertyNames@@3QBGB; "SecondaryChannelId"
0x180097768  mov     rax, [rax+28h]
0x18009776c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097771  mov     rcx, [rsp+2E8h]; this
0x180097779  test    eax, eax
0x18009777b  jns     short loc_180097792
0x18009777d  mov     r9d, eax; char *
0x180097780  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180097787  mov     edx, 2B1h; void *
0x18009778c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
  ... truncated ...
```
