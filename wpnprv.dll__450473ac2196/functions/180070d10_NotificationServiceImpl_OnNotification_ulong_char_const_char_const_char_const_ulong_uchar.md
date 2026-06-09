# NotificationServiceImpl::OnNotification(ulong,char const *,char const *,char const *,ulong,uchar *)

- ea: `0x180070d10`
- end: `0x180071767`
- name: `?OnNotification@NotificationServiceImpl@@UEAAJKPEBD00KPEAE@Z`
- size: `2647`
- prototype: `__int64 __fastcall(NotificationServiceImpl *this, unsigned int, const char *, const char *, char *, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `26`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000a7b8`
- `0x18000aadc`
- `0x18000af1c`
- `0x18000ba54`
- `0x18000fddc`
- `0x18000fe0c`
- `0x18000fe54`
- `0x18001c4bc`
- `0x18001ce24`
- `0x1800210fc`
- `0x180069df4`
- `0x18006a690`
- `0x18006a718`
- `0x18006ad9c`
- `0x18006c638`
- `0x18006d890`
- `0x18006ec7c`
- `0x18006edc8`
- `0x18006f030`
- `0x180070d10`
- `0x180075448`
- `0x1800763f4`
- `0x1800764dc`
- `0x180076e0c`
- `0x1800794a4`
- `0x180096010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180070db8`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180070db8`

## string_xrefs

- `0x1800715f1`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x1800716bf`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x1800716d4`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x1800716e9`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x1800716fe`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x180071713`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x180071728`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x180071740`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x180071754`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`

## pseudocode

```c
__int64 __fastcall NotificationServiceImpl::OnNotification(
        NotificationServiceImpl *this,
        unsigned int a2,
        const char *a3,
        const char *a4,
        char *a5,
        unsigned int a6,
        unsigned __int8 *a7)
{
  const CHAR *v7; // r13
  __int64 v9; // r9
  int v10; // r12d
  int v11; // eax
  int v12; // eax
  int v13; // eax
  unsigned __int64 v14; // r14
  int v15; // ebx
  __int64 v16; // rdx
  __int64 v17; // rcx
  int v18; // edx
  int v19; // ecx
  int v20; // eax
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  struct IConnectionProviderEvents *v32; // rbx
  __int64 (__fastcall *v33)(struct IConnectionProviderEvents *, unsigned __int16 *, __int64, struct INotificationAckResponse **); // rdi
  int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r9
  void *v41; // rcx
  wil *v42; // rcx
  char v43; // di
  __int64 v44; // rdx
  wil::details::in1diag3 *v45; // rcx
  __int64 v46; // r8
  __int64 v47; // r9
  int v48; // ebx
  int v49; // eax
  __int64 v50; // rdx
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // r9
  int v55; // ebx
  int v56; // edx
  int v57; // [rsp+20h] [rbp-278h]
  int v58; // [rsp+20h] [rbp-278h]
  int v59; // [rsp+20h] [rbp-278h]
  int v60; // [rsp+20h] [rbp-278h]
  int v61; // [rsp+30h] [rbp-268h]
  unsigned int v62; // [rsp+38h] [rbp-260h]
  unsigned int *v63; // [rsp+50h] [rbp-248h]
  int *v64; // [rsp+58h] [rbp-240h]
  unsigned __int16 *v65; // [rsp+60h] [rbp-238h]
  char v66; // [rsp+C0h] [rbp-1D8h]
  int v67; // [rsp+C4h] [rbp-1D4h] BYREF
  int v68; // [rsp+C8h] [rbp-1D0h] BYREF
  unsigned __int16 *v69; // [rsp+D0h] [rbp-1C8h] BYREF
  unsigned int v70; // [rsp+D8h] [rbp-1C0h] BYREF
  int v71; // [rsp+DCh] [rbp-1BCh] BYREF
  int v72; // [rsp+E0h] [rbp-1B8h] BYREF
  int v73; // [rsp+E4h] [rbp-1B4h]
  struct INotificationAckResponse *v74; // [rsp+E8h] [rbp-1B0h] BYREF
  unsigned int v75; // [rsp+F0h] [rbp-1A8h] BYREF
  int v76; // [rsp+F4h] [rbp-1A4h] BYREF
  int v77; // [rsp+F8h] [rbp-1A0h] BYREF
  struct IConnectionProviderEvents *v78; // [rsp+100h] [rbp-198h] BYREF
  __int64 v79; // [rsp+108h] [rbp-190h] BYREF
  void *v80; // [rsp+110h] [rbp-188h] BYREF
  unsigned __int16 *v81; // [rsp+118h] [rbp-180h] BYREF
  unsigned __int16 *v82; // [rsp+120h] [rbp-178h] BYREF
  WNPMessageParser *v83; // [rsp+128h] [rbp-170h] BYREF
  NotificationServiceImpl *v84; // [rsp+130h] [rbp-168h]
  unsigned __int16 *v85; // [rsp+138h] [rbp-160h] BYREF
  unsigned __int16 *v86; // [rsp+140h] [rbp-158h] BYREF
  unsigned __int16 *v87; // [rsp+148h] [rbp-150h] BYREF
  unsigned __int16 *v88; // [rsp+150h] [rbp-148h] BYREF
  unsigned __int16 *v89; // [rsp+158h] [rbp-140h] BYREF
  unsigned __int16 *v90; // [rsp+160h] [rbp-138h] BYREF
  unsigned __int16 *v91; // [rsp+168h] [rbp-130h] BYREF
  unsigned __int16 *v92; // [rsp+170h] [rbp-128h] BYREF
  unsigned __int64 v93; // [rsp+178h] [rbp-120h]
  unsigned __int16 *v94; // [rsp+180h] [rbp-118h] BYREF
  void *v95; // [rsp+188h] [rbp-110h] BYREF
  struct WNPMessageParser *v96; // [rsp+190h] [rbp-108h] BYREF
  char v97; // [rsp+198h] [rbp-100h]
  double v98; // [rsp+1A0h] [rbp-F8h] BYREF
  double v99; // [rsp+1A8h] [rbp-F0h] BYREF
  _QWORD v100[2]; // [rsp+1B0h] [rbp-E8h] BYREF
  int v101; // [rsp+1C0h] [rbp-D8h]
  int v102; // [rsp+1C4h] [rbp-D4h]
  double v103; // [rsp+1C8h] [rbp-D0h]
  unsigned __int16 *v104; // [rsp+1D0h] [rbp-C8h]
  unsigned __int16 *v105; // [rsp+1D8h] [rbp-C0h]
  unsigned __int16 *v106; // [rsp+1E0h] [rbp-B8h]
  unsigned __int64 v107; // [rsp+1E8h] [rbp-B0h]
  unsigned int v108; // [rsp+1F0h] [rbp-A8h]
  int v109; // [rsp+1F4h] [rbp-A4h]
  unsigned __int16 *v110; // [rsp+1F8h] [rbp-A0h]
  int v111; // [rsp+200h] [rbp-98h]
  int v112; // [rsp+204h] [rbp-94h]
  unsigned __int16 *v113; // [rsp+208h] [rbp-90h]
  unsigned __int16 *v114; // [rsp+210h] [rbp-88h]
  unsigned __int16 *v115; // [rsp+218h] [rbp-80h]
  unsigned int v116; // [rsp+220h] [rbp-78h]
  int v117; // [rsp+224h] [rbp-74h]
  void *v118; // [rsp+228h] [rbp-70h]
  int v119; // [rsp+230h] [rbp-68h]
  int v120; // [rsp+234h] [rbp-64h]
  char *v121; // [rsp+238h] [rbp-60h]
  unsigned __int16 *v122; // [rsp+240h] [rbp-58h]
  unsigned __int16 *v123; // [rsp+248h] [rbp-50h]
  int v124; // [rsp+250h] [rbp-48h]
  int v125; // [rsp+254h] [rbp-44h]
  unsigned __int16 *v126; // [rsp+258h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]
  int v129; // [rsp+2B0h] [rbp+18h]

  v129 = (int)a3;
  v7 = a4;
  v9 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, a2);
  }
  v10 = 0;
  v93 = 0;
  v74 = 0;
  v69 = 0;
  v68 = 1;
  v67 = 0;
  v11 = _o__stricmp("WNS\\NOTIF", a3, a3, v9);
  try
  {
    if ( v11 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x28F,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)0x80070057LL,
        v57);
    v83 = 0;
    v95 = &v83;
    v96 = 0;
    v97 = 1;
    v12 = WNPMessageParser::CreateInstance(a7, a6, &v96);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x292,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)v12,
        v57);
    wil::details::out_param_t<std::unique_ptr<WNPMessageParser>>::~out_param_t<std::unique_ptr<WNPMessageParser>>(&v95);
    v98 = 0.0;
    v76 = 0;
    v99 = DOUBLE_N657435_0;
    v70 = 0;
    v71 = 0;
    v72 = 0;
    v80 = 0;
    v75 = 0;
    v77 = 1;
    v85 = 0;
    v95 = &v80;
    v96 = 0;
    v97 = 1;
    v86 = 0;
    v87 = 0;
    v88 = 0;
    v81 = 0;
    v82 = 0;
    v89 = 0;
    v90 = 0;
    v91 = 0;
    v92 = 0;
    v69 = 0;
    v13 = WNPMessageParser::ParseNotification(
            v83,
            &v98,
            &v69,
            (enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005 *)&v68,
            (enum __MIDL___MIDL_itf_wpnplatform_0000_0007_0005 *)&v76,
            (enum __MIDL___MIDL_itf_wpntypes_0000_0000_0007 *)&v67,
            &v99,
            &v92,
            &v91,
            &v90,
            &v70,
            &v71,
            &v89,
            &v72,
            &v82,
            &v81,
            &v88,
            &v87,
            &v86,
            (unsigned __int8 **)&v96,
            &v75,
            (enum __MIDL___MIDL_itf_wpntypes_0000_0000_0006 *)&v77,
            &v85);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2BF,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)v13,
        v58);
    wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&v95);
    v14 = *((_QWORD *)v83 + 6);
    v93 = v14;
    v15 = *((unsigned __int8 *)v83 + 32);
    v73 = v15;
    v66 = v15;
    v65 = v81;
    HIDWORD(v64) = HIDWORD(v82);
    HIDWORD(v63) = HIDWORD(a5);
    v62 = v70;
    v61 = v67;
    v59 = v15;
    NotificationServiceImpl::LogNotificationReceived(v17, v16, v69, v14);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57975764>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57975764>::GetImpl'::`2'::impl) )
    {
      if ( byte_1800AFD84 < 0 )
        McTemplateU0ssqxts_EventWriteTransfer(v19, v18, (_DWORD)a3, (_DWORD)v7, a6, v14, v15, (__int64)a5);
    }
    else if ( (byte_1800AFD82 & 0x10) != 0 )
    {
      McTemplateU0ssqxt_EventWriteTransfer(v19, v18, (_DWORD)a3, (_DWORD)v7, a6, v14, v15);
    }
    v84 = (NotificationServiceImpl *)((char *)this - 8);
    v20 = (*(__int64 (__fastcall **)(_QWORD, const CHAR *, unsigned __int64))(**((_QWORD **)this + 13) + 56LL))(
            *((_QWORD *)this + 13),
            v7,
            v14);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2E3,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)v20,
        v59);
    v94 = 0;
    v21 = WpnUtf8ToUtf16(v7, &v94);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2E6,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)v21,
        v59);
    *(double *)v100 = v98;
    v100[1] = v69;
    v101 = v68;
    v102 = v67;
    v103 = v99;
    v104 = v92;
    v105 = v91;
    v106 = v90;
    v107 = v14;
    v108 = v70;
    v109 = v71;
    v110 = v89;
    v111 = v72;
    v112 = 0;
    v113 = v88;
    v114 = v87;
    v115 = v86;
    v116 = v75;
    v117 = 0;
    v118 = v80;
    v119 = v76;
    v120 = 0;
    v121 = a5;
    v122 = v82;
    v123 = v81;
    v124 = v77;
    v125 = 0;
    v126 = v85;
    v79 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79, v22, v23, v24);
    v25 = Microsoft::WRL::Details::MakeAndInitialize<NotificationDataPackage,INotificationDataPackage,NotificationDataPackage::Initializer &>(
            &v79,
            v100);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x305,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)v25,
        v59);
    v78 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v78, v26, v27, v28);
    NotificationServiceImpl::GetConnectionProviderEvents((NotificationServiceImpl *)((char *)this - 8), &v78);
    v32 = v78;
    if ( !v78 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x309,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)0x8000FFFFLL,
        v59);
    v33 = *(__int64 (__fastcall **)(struct IConnectionProviderEvents *, unsigned __int16 *, __int64, struct INotificationAckResponse **))(*(_QWORD *)v78 + 64LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v74, v29, v30, v31);
    v34 = v33(v32, v94, v79, &v74);
    if ( v34 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x30D,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)v34,
        v59);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v78, v35, v36, v37);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79, v38, v39, v40);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v94);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v85);
    v41 = v80;
    v80 = 0;
    if ( v41 )
      MemoryFree(v41);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v86);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v87);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v88);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v81);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v82);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v89);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v90);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v91);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v92);
    std::unique_ptr<SleepStudyManager>::~unique_ptr<SleepStudyManager>(&v83);
    v43 = v73;
  }
  catch ( ... )
  {
    v55 = wil::ResultFromCaughtException(v42);
    v73 = v55;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57975764>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57975764>::GetImpl'::`2'::impl) )
    {
      if ( (byte_1800AFD84 & 0x40) != 0 )
        McTemplateU0qssqx_EventWriteTransfer((_DWORD)v42, v56, v55, v129, (__int64)a4, a6, v93);
    }
    v84 = (NotificationServiceImpl *)((char *)this - 8);
    v7 = a4;
    v10 = v73;
    v14 = v93;
    v43 = v66;
  }
  NotificationServiceImpl::LogNotificationDeliveredToNotificationPlatform(v42, v10, v69, v14, a5);
  v48 = 0;
  if ( v43 )
  {
    if ( v10 < 0 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v74, v44, v46, v47);
      v49 = NotificationServiceImpl::CreateErrorAckResponse(v10, &v74);
      v48 = v49;
      v45 = retaddr;
      if ( v49 < 0 )
      {
        v50 = 808;
LABEL_28:
        wil::details::in1diag3::_Log_Hr(
          v45,
          (void *)v50,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
          (const char *)(unsigned int)v49,
          v60);
        goto LABEL_29;
      }
    }
    v49 = NotificationServiceImpl::AckNotification(v84, v7, v14, v74);
    v48 = v49;
    v45 = retaddr;
    if ( v49 < 0 )
    {
      v50 = 814;
      goto LABEL_28;
    }
  }
LABEL_29:
  LODWORD(v64) = v67;
  LODWORD(v63) = v68;
  LOBYTE(v62) = v43;
  LOBYTE(v61) = 1;
  NotificationServiceImpl::LogProcessedNotification(v45, v7, v69, a6, a5, v14, v61, v62, v10, v48, v63, v64, v65);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      56,
      &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
      (unsigned int)v10);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v69);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v74, v51, v52, v53);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180070d10  mov     [rsp+arg_18], r9
0x180070d15  mov     [rsp+arg_10], r8
0x180070d1a  mov     [rsp+arg_0], rcx
0x180070d1f  push    rbx
0x180070d20  push    rsi
0x180070d21  push    rdi
0x180070d22  push    r12
0x180070d24  push    r13
0x180070d26  push    r14
0x180070d28  push    r15
0x180070d2a  sub     rsp, 260h
0x180070d31  mov     r13, r9
0x180070d34  mov     rdi, r8
0x180070d37  mov     r9d, edx
0x180070d3a  lea     rax, WPP_GLOBAL_Control
0x180070d41  mov     rcx, cs:WPP_GLOBAL_Control
0x180070d48  cmp     rcx, rax
0x180070d4b  jz      short loc_180070D6E
0x180070d4d  test    byte ptr [rcx+1Ch], 2
0x180070d51  jz      short loc_180070D6E
0x180070d53  cmp     byte ptr [rcx+19h], 6
0x180070d57  jb      short loc_180070D6E
0x180070d59  mov     edx, 37h ; '7'
0x180070d5e  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x180070d65  mov     rcx, [rcx+10h]
0x180070d69  call    WPP_SF_d
0x180070d6e  xor     esi, esi
0x180070d70  mov     r12d, esi
0x180070d73  mov     [rsp+298h+var_120], rsi
0x180070d7b  mov     [rsp+298h+var_1D8], sil
0x180070d83  mov     [rsp+298h+var_1D7], sil
0x180070d8b  mov     [rsp+298h+var_1B0], rsi
0x180070d93  mov     [rsp+298h+var_1C8], rsi
0x180070d9b  lea     r15d, [rsi+1]
0x180070d9f  mov     [rsp+298h+var_1D0], r15d
0x180070da7  mov     [rsp+298h+var_1D4], esi
0x180070dae  mov     rdx, rdi
0x180070db1  lea     rcx, aWnsNotif; "WNS\\NOTIF"
0x180070db8  call    cs:__imp__o__stricmp
0x180070dbe  mov     rcx, [rsp+298h]; this
0x180070dc6  test    eax, eax
0x180070dc8  jnz     loc_1800716B9
0x180070dce  mov     [rsp+298h+var_170], rsi
0x180070dd6  lea     rax, [rsp+298h+var_170]
0x180070dde  mov     [rsp+298h+var_110], rax
0x180070de6  mov     [rsp+298h+var_108], rsi
0x180070dee  mov     [rsp+298h+var_100], r15b
0x180070df6  lea     r8, [rsp+298h+var_108]; struct WNPMessageParser **
0x180070dfe  mov     edx, [rsp+298h+arg_28]; unsigned int
0x180070e05  mov     rcx, [rsp+298h+arg_30]; unsigned __int8 *
0x180070e0d  call    ?CreateInstance@WNPMessageParser@@SAJPEAEKPEAPEAV1@@Z; WNPMessageParser::CreateInstance(uchar *,ulong,WNPMessageParser * *)
0x180070e12  mov     rcx, [rsp+298h]; this
0x180070e1a  test    eax, eax
0x180070e1c  js      loc_1800716D1
0x180070e22  lea     rcx, [rsp+298h+var_110]
0x180070e2a  call    ??1?$out_param_t@V?$unique_ptr@VWNPMessageParser@@U?$default_delete@VWNPMessageParser@@@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<WNPMessageParser>>::~out_param_t<std::unique_ptr<WNPMessageParser>>(void)
0x180070e2f  xorps   xmm0, xmm0
0x180070e32  movsd   [rsp+298h+var_F8], xmm0
0x180070e3b  mov     [rsp+298h+var_1A4], esi
0x180070e42  movsd   xmm1, cs:__real@c124103600000000
0x180070e4a  movsd   [rsp+298h+var_F0], xmm1
0x180070e53  mov     [rsp+298h+var_1C0], esi
0x180070e5a  mov     [rsp+298h+var_1BC], esi
0x180070e61  mov     [rsp+298h+var_1B8], esi
0x180070e68  mov     [rsp+298h+var_188], rsi
0x180070e70  mov     [rsp+298h+var_1A8], esi
0x180070e77  mov     [rsp+298h+var_1A0], r15d
0x180070e7f  mov     r14, [rsp+298h+var_170]
0x180070e87  mov     [rsp+298h+var_160], rsi
0x180070e8f  lea     rax, [rsp+298h+var_188]
0x180070e97  mov     [rsp+298h+var_110], rax
0x180070e9f  mov     [rsp+298h+var_108], rsi
0x180070ea7  mov     [rsp+298h+var_100], r15b
0x180070eaf  mov     [rsp+298h+var_158], rsi
0x180070eb7  mov     [rsp+298h+var_150], rsi
0x180070ebf  mov     [rsp+298h+var_148], rsi
0x180070ec7  mov     [rsp+298h+var_180], rsi
0x180070ecf  mov     [rsp+298h+var_178], rsi
0x180070ed7  mov     [rsp+298h+var_140], rsi
0x180070edf  mov     [rsp+298h+var_138], rsi
0x180070ee7  mov     [rsp+298h+var_130], rsi
0x180070eef  mov     [rsp+298h+var_128], rsi
0x180070ef7  mov     rbx, [rsp+298h+var_1C8]
0x180070eff  test    rbx, rbx
0x180070f02  jz      short loc_180070F26
0x180070f04  lea     rcx, [rsp+298h+var_168]; this
0x180070f0c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180070f11  mov     rcx, rbx; void *
0x180070f14  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180070f19  lea     rcx, [rsp+298h+var_168]; this
0x180070f21  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180070f26  mov     [rsp+298h+var_1C8], rsi
0x180070f2e  lea     rax, [rsp+298h+var_160]
0x180070f36  mov     [rsp+298h+var_1E8], rax; unsigned __int16 **
0x180070f3e  lea     rax, [rsp+298h+var_1A0]
0x180070f46  mov     [rsp+298h+var_1F0], rax; enum __MIDL___MIDL_itf_wpntypes_0000_0000_0006 *
0x180070f4e  lea     rax, [rsp+298h+var_1A8]
0x180070f56  mov     [rsp+298h+var_1F8], rax; unsigned int *
0x180070f5e  lea     rax, [rsp+298h+var_108]
0x180070f66  mov     [rsp+298h+var_200], rax; unsigned __int8 **
0x180070f6e  lea     rax, [rsp+298h+var_158]
0x180070f76  mov     [rsp+298h+var_208], rax; unsigned __int16 **
0x180070f7e  lea     rax, [rsp+298h+var_150]
0x180070f86  mov     [rsp+298h+var_210], rax; unsigned __int16 **
0x180070f8e  lea     rax, [rsp+298h+var_148]
0x180070f96  mov     [rsp+298h+var_218], rax; unsigned __int16 **
0x180070f9e  lea     rax, [rsp+298h+var_180]
0x180070fa6  mov     [rsp+298h+var_220], rax; unsigned __int16 **
0x180070fab  lea     rax, [rsp+298h+var_178]
0x180070fb3  mov     [rsp+298h+var_228], rax; unsigned __int16 **
0x180070fb8  lea     rax, [rsp+298h+var_1B8]
0x180070fc0  mov     [rsp+298h+var_230], rax; int *
0x180070fc5  lea     rax, [rsp+298h+var_140]
0x180070fcd  mov     [rsp+298h+var_238], rax; unsigned __int16 **
0x180070fd2  lea     rax, [rsp+298h+var_1BC]
0x180070fda  mov     [rsp+298h+var_240], rax; int *
0x180070fdf  lea     rax, [rsp+298h+var_1C0]
0x180070fe7  mov     [rsp+298h+var_248], rax; unsigned int *
0x180070fec  lea     rax, [rsp+298h+var_138]
0x180070ff4  mov     [rsp+298h+var_250], rax; unsigned __int16 **
0x180070ff9  lea     rax, [rsp+298h+var_130]
0x180071001  mov     [rsp+298h+var_258], rax; unsigned __int16 **
0x180071006  lea     rax, [rsp+298h+var_128]
0x18007100e  mov     [rsp+298h+var_260], rax; unsigned __int16 **
0x180071013  lea     rax, [rsp+298h+var_F0]
0x18007101b  mov     [rsp+298h+var_268], rax; double *
0x180071020  lea     rax, [rsp+298h+var_1D4]
0x180071028  mov     [rsp+298h+var_270], rax; enum __MIDL___MIDL_itf_wpntypes_0000_0000_0007 *
0x18007102d  lea     rax, [rsp+298h+var_1A4]
0x180071035  mov     [rsp+298h+var_278], rax; int
0x18007103a  lea     r9, [rsp+298h+var_1D0]; enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005 *
0x180071042  lea     r8, [rsp+298h+var_1C8]; unsigned __int16 **
0x18007104a  lea     rdx, [rsp+298h+var_F8]; double *
0x180071052  mov     rcx, r14; this
0x180071055  call    ?ParseNotification@WNPMessageParser@@QEAAJPEANPEAPEAGPEAW4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@PEAW4__MIDL___MIDL_itf_wpnplatform_0000_0007_0005@@PEAW4__MIDL___MIDL_itf_wpntypes_0000_0000_0007@@0111PEAKPEAH1611111PEAPEAEPEAIPEAW4__MIDL___MIDL_itf_wpntypes_0000_0000_0006@@1@Z; WNPMessageParser::ParseNotification(double *,ushort * *,__MIDL___MIDL_itf_wpntypes_0000_0000_0005 *,__MIDL___MIDL_itf_wpnplatform_0000_0007_0005 *,__MIDL___MIDL_itf_wpntypes_0000_0000_0007 *,double *,ushort * *,ushort * *,ushort * *,ulong *,int *,ushort * *,int *,ushort * *,ushort * *,ushort * *,ushort * *,ushort * *,uchar * *,uint *,__MIDL___MIDL_itf_wpntypes_0000_0000_0006 *,ushort * *)
0x18007105a  mov     rcx, [rsp+298h]; this
0x180071062  test    eax, eax
0x180071064  js      loc_1800716E6
0x18007106a  lea     rcx, [rsp+298h+var_110]
0x180071072  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x180071077  mov     rax, [rsp+298h+var_170]
0x18007107f  mov     r14, [rax+30h]
0x180071083  mov     [rsp+298h+var_120], r14
0x18007108b  movzx   ebx, byte ptr [rax+20h]
0x18007108f  mov     [rsp+298h+var_1B4], ebx
0x180071096  mov     [rsp+298h+var_1D8], bl
0x18007109d  mov     rax, [rsp+298h+var_180]
0x1800710a5  mov     [rsp+298h+var_238], rax
0x1800710aa  mov     rax, [rsp+298h+var_178]
0x1800710b2  mov     [rsp+298h+var_240], rax
0x1800710b7  mov     rax, [rsp+298h+arg_20]
0x1800710bf  mov     [rsp+298h+var_248], rax
0x1800710c4  mov     eax, [rsp+298h+var_1B8]
0x1800710cb  mov     dword ptr [rsp+298h+var_250], eax
0x1800710cf  mov     eax, [rsp+298h+var_1BC]
0x1800710d6  mov     dword ptr [rsp+298h+var_258], eax
0x1800710da  mov     eax, [rsp+298h+var_1C0]
0x1800710e1  mov     dword ptr [rsp+298h+var_260], eax
0x1800710e5  mov     eax, [rsp+298h+var_1D4]
0x1800710ec  mov     dword ptr [rsp+298h+var_268], eax
0x1800710f0  mov     eax, [rsp+298h+var_1D0]
0x1800710f7  mov     dword ptr [rsp+298h+var_270], eax
0x1800710fb  mov     dword ptr [rsp+298h+var_278], ebx
0x1800710ff  mov     r9, r14
0x180071102  mov     r8, [rsp+298h+var_1C8]
0x18007110a  call    ?LogNotificationReceived@NotificationServiceImpl@@AEAAXJPEAG_KHW4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@W4__MIDL___MIDL_itf_wpntypes_0000_0000_0007@@KHHPEBDPEBG5@Z; NotificationServiceImpl::LogNotificationReceived(long,ushort *,unsigned __int64,int,__MIDL___MIDL_itf_wpntypes_0000_0000_0005,__MIDL___MIDL_itf_wpntypes_0000_0000_0007,ulong,int,int,char const *,ushort const *,ushort const *)
0x18007110f  mov     [rsp+298h+var_1D7], r15b
0x180071117  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57975764@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57975764@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57975764> `wil::Feature<__WilFeatureTraits_Feature_57975764>::GetImpl(void)'::`2'::impl
0x18007111e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57975764@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57975764>::__private_IsEnabled(void)
0x180071123  test    al, al
0x180071125  jz      short loc_18007115E
0x180071127  cmp     cs:byte_1800AFD84, sil
0x18007112e  jge     short loc_180071186
0x180071130  mov     rax, [rsp+298h+arg_20]
0x180071138  mov     [rsp+298h+var_260], rax
0x18007113d  mov     dword ptr [rsp+298h+var_268], ebx
0x180071141  mov     [rsp+298h+var_270], r14
0x180071146  mov     eax, [rsp+298h+arg_28]
0x18007114d  mov     dword ptr [rsp+298h+var_278], eax
0x180071151  mov     r9, r13
0x180071154  mov     r8, rdi
0x180071157  call    McTemplateU0ssqxts_EventWriteTransfer
0x18007115c  jmp     short loc_180071186
0x18007115e  test    cs:byte_1800AFD82, 10h
0x180071165  jz      short loc_180071186
0x180071167  mov     dword ptr [rsp+298h+var_268], ebx
0x18007116b  mov     [rsp+298h+var_270], r14
0x180071170  mov     eax, [rsp+298h+arg_28]
0x180071177  mov     dword ptr [rsp+298h+var_278], eax; int
0x18007117b  mov     r9, r13
0x18007117e  mov     r8, rdi
0x180071181  call    McTemplateU0ssqxt_EventWriteTransfer
0x180071186  mov     rbx, [rsp+298h+arg_0]
0x18007118e  add     rbx, 0FFFFFFFFFFFFFFF8h
0x180071192  mov     [rsp+298h+var_168], rbx
0x18007119a  mov     rcx, [rbx+70h]
0x18007119e  mov     rax, [rcx]
0x1800711a1  mov     r8, r14
0x1800711a4  mov     rdx, r13
0x1800711a7  mov     rax, [rax+38h]
0x1800711ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800711b0  mov     rcx, [rsp+298h]; this
0x1800711b8  test    eax, eax
0x1800711ba  js      loc_1800716FB
0x1800711c0  mov     [rsp+298h+var_118], rsi
0x1800711c8  lea     rdx, [rsp+298h+var_118]; unsigned __int16 **
0x1800711d0  mov     rcx, r13; lpMultiByteStr
0x1800711d3  call    ?WpnUtf8ToUtf16@@YAJPEBDPEAPEAG@Z; WpnUtf8ToUtf16(char const *,ushort * *)
0x1800711d8  mov     rcx, [rsp+298h]; this
0x1800711e0  test    eax, eax
0x1800711e2  js      loc_180071710
0x1800711e8  movsd   xmm0, [rsp+298h+var_F8]
0x1800711f1  movsd   [rsp+298h+var_E8], xmm0
0x1800711fa  mov     rax, [rsp+298h+var_1C8]
0x180071202  mov     [rsp+298h+var_E0], rax
0x18007120a  mov     eax, [rsp+298h+var_1D0]
0x180071211  mov     [rsp+298h+var_D8], eax
0x180071218  mov     eax, [rsp+298h+var_1D4]
0x18007121f  mov     [rsp+298h+var_D4], eax
0x180071226  movsd   xmm0, [rsp+298h+var_F0]
0x18007122f  movsd   [rsp+298h+var_D0], xmm0
0x180071238  mov     rax, [rsp+298h+var_128]
0x180071240  mov     [rsp+298h+var_C8], rax
0x180071248  mov     rax, [rsp+298h+var_130]
0x180071250  mov     [rsp+298h+var_C0], rax
0x180071258  mov     rax, [rsp+298h+var_138]
0x180071260  mov     [rsp+298h+var_B8], rax
0x180071268  mov     [rsp+298h+var_B0], r14
0x180071270  mov     eax, [rsp+298h+var_1C0]
0x180071277  mov     [rsp+298h+var_A8], eax
0x18007127e  mov     eax, [rsp+298h+var_1BC]
0x180071285  mov     [rsp+298h+var_A4], eax
0x18007128c  mov     rax, [rsp+298h+var_140]
0x180071294  mov     [rsp+298h+var_A0], rax
0x18007129c  mov     eax, [rsp+298h+var_1B8]
0x1800712a3  mov     [rsp+298h+var_98], eax
0x1800712aa  xor     eax, eax
0x1800712ac  mov     [rsp+298h+var_94], eax
0x1800712b3  mov     rax, [rsp+298h+var_148]
0x1800712bb  mov     [rsp+298h+var_90], rax
0x1800712c3  mov     rax, [rsp+298h+var_150]
0x1800712cb  mov     [rsp+298h+var_88], rax
0x1800712d3  mov     rax, [rsp+298h+var_158]
0x1800712db  mov     [rsp+298h+var_80], rax
0x1800712e3  mov     eax, [rsp+298h+var_1A8]
0x1800712ea  mov     [rsp+298h+var_78], eax
0x1800712f1  xor     eax, eax
0x1800712f3  mov     [rsp+298h+var_74], eax
0x1800712fa  mov     rax, [rsp+298h+var_188]
0x180071302  mov     [rsp+298h+var_70], rax
0x18007130a  mov     eax, [rsp+298h+var_1A4]
0x180071311  mov     [rsp+298h+var_68], eax
0x180071318  xor     eax, eax
0x18007131a  mov     [rsp+298h+var_64], eax
0x180071321  mov     rax, [rsp+298h+arg_20]
0x180071329  mov     [rsp+298h+var_60], rax
0x180071331  mov     rax, [rsp+298h+var_178]
0x180071339  mov     [rsp+298h+var_58], rax
0x180071341  mov     rax, [rsp+298h+var_180]
0x180071349  mov     [rsp+298h+var_50], rax
0x180071351  mov     eax, [rsp+298h+var_1A0]
0x180071358  mov     [rsp+298h+var_48], eax
0x18007135f  xor     eax, eax
0x180071361  mov     [rsp+298h+var_44], eax
0x180071368  mov     rax, [rsp+298h+var_160]
0x180071370  mov     [rsp+298h+var_40], rax
0x180071378  mov     [rsp+298h+var_190], rsi
0x180071380  lea     rcx, [rsp+298h+var_190]
0x180071388  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007138d  lea     rdx, [rsp+298h+var_E8]
0x180071395  lea     rcx, [rsp+298h+var_190]
0x18007139d  call    ??$MakeAndInitialize@VNotificationDataPackage@@UINotificationDataPackage@@AEAUInitializer@1@@Details@WRL@Microsoft@@YAJPEAPEAUINotificationDataPackage@@AEAUInitializer@NotificationDataPackage@@@Z; Microsoft::WRL::Details::MakeAndInitialize<NotificationDataPackage,INotificationDataPackage,NotificationDataPackage::Initializer &>(INotificationDataPackage * *,NotificationDataPackage::Initializer &)
0x1800713a2  mov     rcx, [rsp+298h]; this
0x1800713aa  test    eax, eax
0x1800713ac  js      loc_180071725
0x1800713b2  mov     [rsp+298h+var_198], rsi
0x1800713ba  lea     rcx, [rsp+298h+var_198]
0x1800713c2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800713c7  lea     rdx, [rsp+298h+var_198]; struct IConnectionProviderEvents **
0x1800713cf  mov     rcx, rbx; this
0x1800713d2  call    ?GetConnectionProviderEvents@NotificationServiceImpl@@AEAAXPEAPEAUIConnectionProviderEvents@@@Z; NotificationServiceImpl::GetConnectionProviderEvents(IConnectionProviderEvents * *)
0x1800713d7  mov     rcx, [rsp+298h]; this
0x1800713df  mov     rbx, [rsp+298h+var_198]
0x1800713e7  test    rbx, rbx
0x1800713ea  jz      loc_18007173A
0x1800713f0  mov     rax, [rbx]
0x1800713f3  mov     rdi, [rax+40h]
0x1800713f7  lea     rcx, [rsp+298h+var_1B0]
0x1800713ff  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071404  lea     r9, [rsp+298h+var_1B0]
0x18007140c  mov     r8, [rsp+298h+var_190]
0x180071414  mov     rdx, [rsp+298h+var_118]
0x18007141c  mov     rcx, rbx
0x18007141f  mov     rax, rdi
0x180071422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071427  mov     rcx, [rsp+298h]; this
0x18007142f  test    eax, eax
0x180071431  js      loc_180071751
0x180071437  lea     rcx, [rsp+298h+var_198]
0x18007143f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
  ... truncated ...
```
