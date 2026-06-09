# BackgroundActivation::ActivateRawNotificationWorkItem(INotificationHandler *,Notification *,TransientNotificationDetails *,_GUID)

- ea: `0x180099b48`
- end: `0x18009aa64`
- name: `?ActivateRawNotificationWorkItem@BackgroundActivation@@QEAAJPEAUINotificationHandler@@PEAVNotification@@PEAVTransientNotificationDetails@@U_GUID@@@Z`
- size: `3868`
- prototype: `int(BackgroundActivation *__hidden this, struct INotificationHandler *, struct Notification *, struct TransientNotificationDetails *, struct _GUID *__struct_ptr)`
- caller_count: `2`
- callee_count: `37`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180054a78`
- `0x180056420`

## callees

- `0x180004e38`
- `0x18000a784`
- `0x18000e090`
- `0x18000e5f4`
- `0x1800117c0`
- `0x18001bf30`
- `0x180023540`
- `0x1800236a4`
- `0x180023820`
- `0x18002ee38`
- `0x18002f224`
- `0x1800394ec`
- `0x18004d6f0`
- `0x18004f124`
- `0x1800542a8`
- `0x180057ad0`
- `0x180058bb4`
- `0x18005b2b4`
- `0x18005c090`
- `0x18006244c`
- `0x18006a36c`
- `0x18006a3f0`
- `0x18006dfa0`
- `0x180070fc0`
- `0x1800710cc`
- `0x180082308`
- `0x180099b48`
- `0x18009aa6c`
- `0x18009ab50`
- `0x18009ad38`
- `0x18009c2e0`
- `0x1800a57a0`
- `0x1800a5b54`
- `0x1800b99f0`
- `0x1800bc541`
- `0x1800f59ec`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180099e83`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180099e83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099e75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099f5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099e75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099f5f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099f6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099f6d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180099d70`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180099d70`
- `ntdll!RtlPublishWnfStateData` at `0x180099f43`
- `ntdll!RtlPublishWnfStateData` at `0x180099fa1`
- `ntdll!RtlPublishWnfStateData` at `0x180099f43`
- `ntdll!RtlPublishWnfStateData` at `0x180099fa1`

## string_xrefs

- `0x18009a4fb`: `Cached`
- `0x18009a53c`: `Cached`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall BackgroundActivation::ActivateRawNotificationWorkItem(
        BackgroundActivation *this,
        struct INotificationHandler *a2,
        struct Notification *a3,
        struct TransientNotificationDetails *a4,
        struct _GUID *a5)
{
  BackgroundActivation *v8; // rdi
  char v9; // r12
  int v10; // r13d
  __int64 correlationVector; // rbx
  __int64 (__fastcall *v12)(struct INotificationHandler *, LPCWCH *); // rbx
  int v13; // eax
  const WCHAR *v14; // r10
  const WCHAR *v15; // r8
  __int64 v16; // rdx
  int v17; // eax
  __int64 (__fastcall *v18)(struct INotificationHandler *, struct Windows::Storage::Streams::IBuffer **); // rbx
  int v19; // eax
  unsigned int v20; // edi
  HANDLE ProcessHeap; // rax
  _DWORD *v22; // rbx
  const char *v23; // r9
  int v24; // eax
  size_t payloadSize; // r14
  unsigned __int8 *payloadBytes; // rax
  unsigned int v27; // eax
  int v28; // edx
  int v29; // ebx
  void *v30; // rdi
  HANDLE v31; // rax
  unsigned int v32; // ebx
  unsigned __int8 *v33; // rax
  unsigned int v34; // eax
  int v35; // edx
  int CurrentProcessIntegrityLevel; // eax
  int UserSidAccount; // eax
  int v38; // eax
  _QWORD *v39; // rax
  __int64 v40; // rcx
  bool v41; // zf
  _QWORD *handlerKey; // rax
  __int64 v43; // rcx
  int v44; // esi
  wil *v45; // rcx
  int v46; // eax
  char *v47; // rdi
  int (__fastcall *v48)(char *, const unsigned __int16 *, LPVOID **); // rbx
  __int64 v49; // rax
  int v50; // eax
  struct WpnNotificationData *v51; // rdi
  int (__fastcall *v52)(char *, const unsigned __int16 *, LPVOID **); // rbx
  __int64 v53; // rax
  int v54; // eax
  struct WpnNotificationData *v55; // rdi
  int (__fastcall *v56)(char *, const unsigned __int16 *, LPVOID **); // rbx
  __int64 v57; // rax
  int v58; // eax
  struct WpnNotificationData *v59; // rdi
  int (__fastcall *v60)(char *, const unsigned __int16 *, LPVOID **); // rbx
  __int64 v61; // rax
  int v62; // eax
  struct WpnNotificationData *v63; // rdi
  int (__fastcall *v64)(char *, const unsigned __int16 *, LPVOID **); // rbx
  __int64 v65; // rax
  int v66; // eax
  struct WpnNotificationData *v67; // rdi
  int (__fastcall *v68)(char *, const unsigned __int16 *, LPVOID **); // rbx
  __int64 v69; // rax
  int v70; // eax
  const unsigned __int8 *v71; // rax
  const unsigned __int16 *v72; // rdx
  int v73; // eax
  __int64 v74; // rdx
  __int128 *v75; // r8
  int v76; // eax
  LPVOID *v77; // rax
  __int64 v78; // rax
  int v79; // eax
  int v80; // eax
  int v81; // eax
  int v82; // eax
  int v83; // eax
  __int64 (__fastcall *v84)(struct INotificationHandler *, LPVOID *); // rbx
  int v85; // eax
  __int64 v86; // rbx
  int v87; // r14d
  __int64 v88; // r15
  LPVOID v89; // r8
  _QWORD *v90; // rax
  int v91; // eax
  int bIgnoreCase; // [rsp+20h] [rbp-208h]
  int bIgnoreCasea; // [rsp+20h] [rbp-208h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-208h]
  bool v96; // [rsp+70h] [rbp-1B8h] BYREF
  char v97; // [rsp+71h] [rbp-1B7h] BYREF
  char v98[2]; // [rsp+72h] [rbp-1B6h] BYREF
  int v99; // [rsp+74h] [rbp-1B4h] BYREF
  struct Windows::Storage::Streams::IBuffer *v100; // [rsp+78h] [rbp-1B0h] BYREF
  unsigned int v101; // [rsp+80h] [rbp-1A8h] BYREF
  int v102; // [rsp+84h] [rbp-1A4h] BYREF
  struct WpnNotificationData *v103; // [rsp+88h] [rbp-1A0h] BYREF
  LPVOID lpMem; // [rsp+90h] [rbp-198h] BYREF
  enum _SID_NAME_USE v105; // [rsp+98h] [rbp-190h] BYREF
  LPVOID *p_lpMem; // [rsp+A0h] [rbp-188h] BYREF
  char v107; // [rsp+A8h] [rbp-180h]
  __int64 v108; // [rsp+B0h] [rbp-178h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+B8h] [rbp-170h] BYREF
  unsigned int v110; // [rsp+BCh] [rbp-16Ch] BYREF
  LPVOID *v111; // [rsp+C0h] [rbp-168h] BYREF
  LPVOID *v112; // [rsp+C8h] [rbp-160h] BYREF
  LPVOID *v113; // [rsp+D0h] [rbp-158h] BYREF
  LPVOID *v114; // [rsp+D8h] [rbp-150h] BYREF
  LPVOID *v115; // [rsp+E0h] [rbp-148h] BYREF
  LPVOID *v116; // [rsp+E8h] [rbp-140h] BYREF
  struct _GUID *v117; // [rsp+F0h] [rbp-138h]
  LPCWCH lpString1; // [rsp+F8h] [rbp-130h] BYREF
  __int64 v119; // [rsp+100h] [rbp-128h]
  __int64 v120; // [rsp+108h] [rbp-120h]
  __int64 v121; // [rsp+110h] [rbp-118h] BYREF
  BackgroundActivation *v122; // [rsp+118h] [rbp-110h]
  struct Notification *v123; // [rsp+120h] [rbp-108h] BYREF
  struct _GUID *v124; // [rsp+130h] [rbp-F8h] BYREF
  __int64 v125; // [rsp+140h] [rbp-E8h] BYREF
  __int128 v126; // [rsp+148h] [rbp-E0h] BYREF
  __int64 v127; // [rsp+158h] [rbp-D0h]
  __int128 v128; // [rsp+168h] [rbp-C0h] BYREF
  __int128 v129; // [rsp+178h] [rbp-B0h]
  _BYTE v130[32]; // [rsp+188h] [rbp-A0h] BYREF
  GUID v131; // [rsp+1A8h] [rbp-80h] BYREF
  int v132; // [rsp+1B8h] [rbp-70h] BYREF
  _BYTE v133[24]; // [rsp+1C0h] [rbp-68h] BYREF
  __int64 v134; // [rsp+1D8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  v8 = this;
  v122 = this;
  v123 = a3;
  v117 = a5;
  v124 = a5;
  v9 = 0;
  v105 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ebc66346838a30418ba30573d23d0a14_Traceguids);
  }
  v10 = 0;
  v102 = 0;
  v98[0] = 0;
  v97 = 0;
  v101 = 0;
  v125 = 0;
  v110 = 0;
  peUse = SidTypeUnknown;
  v96 = 0;
  std::string::string(&v128);
  try
  {
    v131 = GUID_NULL;
    v132 = 0;
    correlationVector = TransientNotificationDetails::get_correlationVector(a4, &v126);
    if ( &v128 != (__int128 *)correlationVector )
    {
      std::string::_Tidy_deallocate(&v128);
      v128 = *(_OWORD *)correlationVector;
      v129 = *(_OWORD *)(correlationVector + 16);
      *(_QWORD *)(correlationVector + 16) = 0;
      *(_QWORD *)(correlationVector + 24) = 15;
      *(_BYTE *)correlationVector = 0;
    }
    std::string::_Tidy_deallocate(&v126);
    lpString1 = 0;
    v119 = 0;
    v120 = 0;
    v12 = *(__int64 (__fastcall **)(struct INotificationHandler *, LPCWCH *))(*(_QWORD *)a2 + 48LL);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
    v119 = -1;
    v120 = -1;
    v13 = v12(a2, &lpString1);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6C,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
        (const char *)(unsigned int)v13,
        bIgnoreCase);
    v14 = &word_180124798;
    v15 = &word_180124798;
    if ( L"app:system" )
      v15 = L"app:system";
    v16 = v119;
    if ( v119 == -1 )
    {
      if ( lpString1 )
      {
        do
          ++v16;
        while ( lpString1[v16] );
      }
      else
      {
        LODWORD(v16) = 0;
      }
    }
    if ( lpString1 )
      v14 = lpString1;
    if ( CompareStringOrdinal(v14, v16, v15, -(L"app:system" != 0), 0) == 2 )
    {
      v98[0] = 1;
      v108 = 0;
      v17 = (*(__int64 (__fastcall **)(struct INotificationHandler *, __int64 *))(*(_QWORD *)a2 + 64LL))(a2, &v108);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x74,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
          (const char *)(unsigned int)v17,
          bIgnoreCasea);
      if ( v108 )
      {
        v97 = 1;
        v125 = v108;
        v100 = 0;
        v18 = *(__int64 (__fastcall **)(struct INotificationHandler *, struct Windows::Storage::Streams::IBuffer **))(*(_QWORD *)a2 + 32LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
        v19 = v18(a2, &v100);
        if ( v19 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x81,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
            (const char *)(unsigned int)v19,
            bIgnoreCasea);
        v99 = 0;
        v10 = (*(__int64 (__fastcall **)(struct Windows::Storage::Streams::IBuffer *, const wchar_t *, int *))(*(_QWORD *)v100 + 32LL))(
                v100,
                L"c:offlineHeaders",
                &v99);
        if ( v10 < 0 )
          v10 = 0;
        v102 = v10;
        if ( v99 )
        {
          v20 = Notification::get_payloadSize(a3) + 8;
          v101 = v20;
          ProcessHeap = GetProcessHeap();
          v22 = HeapAlloc(ProcessHeap, 0, v20);
          lpMem = v22;
          if ( !v22 )
            wil::details::in1diag3::_Throw_NullAlloc(
              retaddr,
              (void *)0x8F,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
              v23);
          p_lpMem = &lpMem;
          v107 = 1;
          *v22 = 1;
          v24 = (*(__int64 (__fastcall **)(char *, _DWORD *))(*((_QWORD *)a4 + 4) + 24LL))((char *)a4 + 32, v22 + 1);
          if ( v24 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x99,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
              (const char *)(unsigned int)v24,
              bIgnoreCasea);
          payloadSize = Notification::get_payloadSize(a3);
          payloadBytes = Notification::get_payloadBytes(a3);
          memcpy_0(v22 + 2, payloadBytes, payloadSize);
          bIgnoreCaseb = 0;
          v27 = RtlPublishWnfStateData(v125, 0, lpMem, v20);
          v29 = wil::details::NtStatusToHr((wil::details *)v27, v28);
          v30 = lpMem;
          if ( lpMem )
          {
            v31 = GetProcessHeap();
            HeapFree(v31, 0, v30);
          }
        }
        else
        {
          v32 = Notification::get_payloadSize(a3);
          v101 = v32;
          v33 = Notification::get_payloadBytes(a3);
          bIgnoreCaseb = 0;
          v34 = RtlPublishWnfStateData(v125, 0, v33, v32);
          v29 = wil::details::NtStatusToHr((wil::details *)v34, v35);
        }
        if ( v29 == -2147024891 )
        {
          CurrentProcessIntegrityLevel = WpnGetCurrentProcessIntegrityLevel(&v110);
          if ( CurrentProcessIntegrityLevel < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xB8,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
              (const char *)(unsigned int)CurrentProcessIntegrityLevel,
              0);
          UserSidAccount = WpnGetUserSidAccount(&peUse);
          if ( UserSidAccount < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xB9,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
              (const char *)(unsigned int)UserSidAccount,
              bIgnoreCaseb);
          v38 = IsAuthenticatedUser(&v96);
          if ( v38 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xBA,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
              (const char *)(unsigned int)v38,
              bIgnoreCaseb);
        }
        if ( v29 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xBD,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
            (const char *)(unsigned int)v29,
            bIgnoreCaseb);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57975764>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57975764>::GetImpl'::`2'::impl) )
        {
          if ( (byte_18015DE47 & 2) != 0 )
          {
            handlerKey = (_QWORD *)Notification::get_handlerKey(a3, &v126);
            v9 = 1;
            if ( handlerKey[3] > 7u )
              handlerKey = (_QWORD *)*handlerKey;
            McTemplateU0z_EventWriteTransfer(v43, WPNEND_BACKGROUND_TASK_ACTIVATED_SYSTEM_UPDATED, handlerKey);
          }
          v41 = (v9 & 1) == 0;
        }
        else
        {
          if ( (byte_18015DE45 & 1) != 0 )
          {
            v39 = (_QWORD *)Notification::get_handlerKey(a3, &v126);
            v9 = 2;
            if ( v39[3] > 7u )
              v39 = (_QWORD *)*v39;
            McTemplateU0z_EventWriteTransfer(v40, WPNEND_BACKGROUND_TASK_ACTIVATED_SYSTEM, v39);
          }
          v41 = (v9 & 2) == 0;
        }
        if ( !v41 )
          std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(&v126);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
      }
      v44 = (int)v117;
    }
    else
    {
      v126 = 0;
      v127 = 0;
      v46 = PropertySetHelper::Initialize((PropertySetHelper *)&v126);
      if ( v46 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xCC,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
          (const char *)(unsigned int)v46,
          bIgnoreCasea);
      v103 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103);
      Notification::get_data(a3, &v103);
      if ( v103 )
      {
        v116 = 0;
        v47 = (char *)v103 + 32;
        v48 = *(int (__fastcall **)(char *, const unsigned __int16 *, LPVOID **))(*((_QWORD *)v103 + 4) + 32LL);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v116,
          0);
        if ( v48(v47, L"SecondaryChannelId", &v116) >= 0 )
        {
          p_lpMem = v116;
          v49 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v130, &p_lpMem);
          v50 = PropertySetHelper::SetValue<HSTRING__ *>(&v126, L"SecondaryChannelId", *(_QWORD *)(v49 + 24));
          if ( v50 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xD7,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
              (const char *)(unsigned int)v50,
              bIgnoreCasea);
        }
        v115 = 0;
        v51 = v103;
        v52 = *(int (__fastcall **)(char *, const unsigned __int16 *, LPVOID **))(*((_QWORD *)v103 + 4) + 32LL);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v115,
          0);
        if ( v52((char *)v51 + 32, L"Encryption", &v115) >= 0 )
        {
          p_lpMem = v115;
          v53 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v130, &p_lpMem);
          v54 = PropertySetHelper::SetValue<HSTRING__ *>(&v126, L"Encryption", *(_QWORD *)(v53 + 24));
          if ( v54 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xDE,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
              (const char *)(unsigned int)v54,
              bIgnoreCasea);
        }
        v114 = 0;
        v55 = v103;
        v56 = *(int (__fastcall **)(char *, const unsigned __int16 *, LPVOID **))(*((_QWORD *)v103 + 4) + 32LL);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v114,
          0);
        if ( v56((char *)v55 + 32, L"Crypto-Key", &v114) >= 0 )
        {
          p_lpMem = v114;
          v57 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v130, &p_lpMem);
          v58 = PropertySetHelper::SetValue<HSTRING__ *>(&v126, L"Crypto-Key", *(_QWORD *)(v57 + 24));
          if ( v58 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xE4,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
              (const char *)(unsigned int)v58,
              bIgnoreCasea);
        }
        v113 = 0;
        v59 = v103;
        v60 = *(int (__fastcall **)(char *, const unsigned __int16 *, LPVOID **))(*((_QWORD *)v103 + 4) + 32LL);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v113,
          0);
        if ( v60((char *)v59 + 32, L"Content-Encoding", &v113) >= 0 )
        {
          p_lpMem = v113;
          v61 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v130, &p_lpMem);
          v62 = PropertySetHelper::SetValue<HSTRING__ *>(&v126, L"Content-Encoding", *(_QWORD *)(v61 + 24));
          if ( v62 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xEA,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
              (const char *)(unsigned int)v62,
              bIgnoreCasea);
        }
        v112 = 0;
        v63 = v103;
        v64 = *(int (__fastcall **)(char *, const unsigned __int16 *, LPVOID **))(*((_QWORD *)v103 + 4) + 32LL);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v112,
          0);
        if ( v64((char *)v63 + 32, L"Priority", &v112) >= 0 )
        {
          p_lpMem = v112;
          v65 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v130, &p_lpMem);
          v66 = PropertySetHelper::SetValue<HSTRING__ *>(&v126, L"Priority", *(_QWORD *)(v65 + 24));
          if ( v66 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xF0,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
              (const char *)(unsigned int)v66,
              bIgnoreCasea);
        }
        v111 = 0;
        v67 = v103;
        v68 = *(int (__fastcall **)(char *, const unsigned __int16 *, LPVOID **))(*((_QWORD *)v103 + 4) + 32LL);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v111,
          0);
        if ( v68((char *)v67 + 32, L"Cached", &v111) >= 0 )
        {
          p_lpMem = v111;
          v69 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v130, &p_lpMem);
          v70 = PropertySetHelper::SetValue<HSTRING__ *>(&v126, L"Cached", *(_QWORD *)(v69 + 24));
          if ( v70 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xF6,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
              (const char *)(unsigned int)v70,
              bIgnoreCasea);
        }
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v111);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v112);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v113);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v114);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v115);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v116);
        v8 = v122;
      }
      v101 = Notification::get_payloadSize(a3);
      v71 = Notification::get_payloadBytes(a3);
      v73 = PropertySetHelper::SetByteArrayValue((PropertySetHelper *)&v126, v72, v101, v71);
      if ( v73 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xFB,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
          (const char *)(unsigned int)v73,
          bIgnoreCasea);
      v75 = &v128;
      if ( *((_QWORD *)&v129 + 1) > 0xFu )
        v75 = (__int128 *)v128;
      v76 = PropertySetHelper::SetValue<char const *>(&v126, v74, v75);
      if ( v76 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xFD,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
          (const char *)(unsigned int)v76,
          bIgnoreCasea);
      v77 = (LPVOID *)Notification::get_handlerKey(a3, v130);
      if ( (unsigned __int64)v77[3] > 7 )
        v77 = (LPVOID *)*v77;
      p_lpMem = v77;
      v78 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v133, &p_lpMem);
      v79 = PropertySetHelper::SetValue<HSTRING__ *>(&v126, L"AppUserModelId", *(_QWORD *)(v78 + 24));
      if ( v79 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xFE,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
          (const char *)(unsigned int)v79,
          bIgnoreCasea);
      v134 = 0;
      std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(v130);
      v100 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
      v80 = PropertySetHelper::Serialize((PropertySetHelper *)&v126, &v100);
      if ( v80 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x101,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
          (const char *)(unsigned int)v80,
          bIgnoreCasea);
      v108 = 0;
      v81 = Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBuffer>::As<Windows::Storage::Streams::IBufferByteAccess>(
              &v100,
              &v108);
      if ( v81 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x104,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
          (const char *)(unsigned int)v81,
          bIgnoreCasea);
      v99 = 0;
      v82 = (*(__int64 (__fastcall **)(struct Windows::Storage::Streams::IBuffer *, int *))(*(_QWORD *)v100 + 56LL))(
              v100,
              &v99);
      if ( v82 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x107,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
          (const char *)(unsigned int)v82,
          bIgnoreCasea);
      v121 = 0;
      v83 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v108 + 24LL))(v108, &v121);
      if ( v83 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x10C,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
          (const char *)(unsigned int)v83,
          bIgnoreCasea);
      lpMem = 0;
      v84 = *(__int64 (__fastcall **)(struct INotificationHandler *, LPVOID *))(*(_QWORD *)a2 + 40LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &lpMem,
        0);
      v85 = v84(a2, &lpMem);
      if ( v85 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x10F,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
          (const char *)(unsigned int)v85,
          bIgnoreCasea);
      v86 = *(_QWORD *)v8;
      Notification::get_id(a3);
      v87 = v99;
      v88 = v121;
      v89 = lpMem;
      if ( !lpMem || !*(_WORD *)lpMem )
      {
        v90 = (_QWORD *)Notification::get_handlerKey(a3, v130);
        v9 = 4;
        v105 = SidTypeAlias;
        if ( v90[3] > 7u )
          v90 = (_QWORD *)*v90;
        v89 = v90;
      }
      v44 = (int)v117;
      v91 = (*(__int64 (__fastcall **)(BackgroundActivation *, _QWORD, LPVOID, __int64))(v86 + 8))(v122, 0, v89, v88);
      if ( v91 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x118,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
          (const char *)(unsigned int)v91,
          v87);
      if ( (v9 & 4) != 0 )
        std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(v130);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpMem);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v108);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103);
      PropertySetHelper::~PropertySetHelper((PropertySetHelper *)&v126);
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
  }
  catch ( ... )
  {
    v102 = wil::ResultFromCaughtException(v45);
    v10 = v102;
    v44 = (int)v124;
  }
  v105 = peUse;
  v124 = (struct _GUID *)&v125;
  WpncoreTelemetryLegacy::ActivateRawNotificationWorkItem<Notification * &,_GUID &,std::string &,long &,bool &,bool &,unsigned char *,unsigned long &,unsigned long &,unsigned long,bool &,_GUID &,long &>(
    (unsigned int)&v123,
    v44,
    (unsigned int)&v128,
    (unsigned int)&v102,
    (__int64)v98,
    (__int64)&v97,
    (__int64)&v124,
    (__int64)&v101,
    (__int64)&v110,
    (__int64)&v105,
    (__int64)&v96,
    (__int64)&v131,
    (__int64)&v132);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ebc66346838a30418ba30573d23d0a14_Traceguids);
  }
  std::string::_Tidy_deallocate(&v128);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180099b48  push    rbx
0x180099b4a  push    rsi
0x180099b4b  push    rdi
0x180099b4c  push    r12
0x180099b4e  push    r13
0x180099b50  push    r14
0x180099b52  push    r15
0x180099b54  sub     rsp, 1F0h
0x180099b5b  mov     rax, cs:__security_cookie
0x180099b62  xor     rax, rsp
0x180099b65  mov     [rsp+228h+var_48], rax
0x180099b6d  mov     r14, r9
0x180099b70  mov     rsi, r8
0x180099b73  mov     r15, rdx
0x180099b76  mov     rdi, rcx
0x180099b79  mov     [rsp+228h+var_110], rcx
0x180099b81  mov     [rsp+228h+var_108], r8
0x180099b89  mov     rax, [rsp+228h+arg_20]
0x180099b91  mov     [rsp+228h+var_138], rax
0x180099b99  mov     [rsp+228h+var_F8], rax
0x180099ba1  xor     ebx, ebx
0x180099ba3  mov     r12d, ebx
0x180099ba6  mov     [rsp+228h+var_190], ebx
0x180099bad  lea     rax, WPP_GLOBAL_Control
0x180099bb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180099bbb  cmp     rcx, rax
0x180099bbe  jz      short loc_180099BDF
0x180099bc0  test    byte ptr [rcx+1Ch], 40h
0x180099bc4  jz      short loc_180099BDF
0x180099bc6  cmp     byte ptr [rcx+19h], 6
0x180099bca  jb      short loc_180099BDF
0x180099bcc  lea     edx, [rbx+0Ah]
0x180099bcf  lea     r8, WPP_ebc66346838a30418ba30573d23d0a14_Traceguids
0x180099bd6  mov     rcx, [rcx+10h]
0x180099bda  call    WPP_SF_
0x180099bdf  mov     r13d, ebx
0x180099be2  mov     [rsp+228h+var_1A4], ebx
0x180099be9  mov     [rsp+228h+var_1B6], bl
0x180099bed  mov     [rsp+228h+var_1B7], bl
0x180099bf1  mov     [rsp+228h+var_1A8], ebx
0x180099bf8  mov     [rsp+228h+var_E8], rbx
0x180099c00  mov     [rsp+228h+var_16C], ebx
0x180099c07  mov     [rsp+228h+peUse], 8
0x180099c12  mov     [rsp+228h+var_1B8], bl
0x180099c16  lea     rcx, [rsp+228h+var_C0]
0x180099c1e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x180099c23  nop
0x180099c24  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x180099c2b  movdqu  [rsp+228h+var_80], xmm1
0x180099c34  mov     [rsp+228h+var_70], ebx
0x180099c3b  lea     rdx, [rsp+228h+var_E0]
0x180099c43  mov     rcx, r14
0x180099c46  call    ?get_correlationVector@TransientNotificationDetails@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; TransientNotificationDetails::get_correlationVector(void)
0x180099c4b  mov     rbx, rax
0x180099c4e  lea     rax, [rsp+228h+var_C0]
0x180099c56  cmp     rax, rbx
0x180099c59  jz      short loc_180099C8F
0x180099c5b  lea     rcx, [rsp+228h+var_C0]; void *
0x180099c63  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180099c68  movups  xmm0, xmmword ptr [rbx]
0x180099c6b  movups  [rsp+228h+var_C0], xmm0
0x180099c73  movups  xmm1, xmmword ptr [rbx+10h]
0x180099c77  movups  [rsp+228h+var_B0], xmm1
0x180099c7f  xor     edx, edx
0x180099c81  mov     [rbx+10h], rdx
0x180099c85  mov     qword ptr [rbx+18h], 0Fh
0x180099c8d  mov     [rbx], dl
0x180099c8f  lea     rcx, [rsp+228h+var_E0]; void *
0x180099c97  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180099c9c  xor     eax, eax
0x180099c9e  mov     [rsp+228h+lpString1], rax
0x180099ca6  mov     [rsp+228h+var_128], rax
0x180099cae  mov     [rsp+228h+var_120], rax
0x180099cb6  mov     rax, [r15]
0x180099cb9  mov     rbx, [rax+30h]
0x180099cbd  lea     rcx, [rsp+228h+lpString1]
0x180099cc5  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180099cca  or      rax, 0FFFFFFFFFFFFFFFFh
0x180099cce  mov     [rsp+228h+var_128], rax
0x180099cd6  mov     [rsp+228h+var_120], rax
0x180099cde  lea     rdx, [rsp+228h+lpString1]
0x180099ce6  mov     rcx, r15
0x180099ce9  mov     rax, rbx
0x180099cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099cf1  mov     rcx, [rsp+228h]; this
0x180099cf9  xor     r11d, r11d
0x180099cfc  test    eax, eax
0x180099cfe  jns     short loc_180099D13
0x180099d00  mov     r9d, eax; char *
0x180099d03  lea     r8, aOnecoreuapBase_147; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180099d0a  lea     edx, [r11+6Ch]; void *
0x180099d0e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180099d13  mov     rcx, cs:off_18011DEB0; "app:system"
0x180099d1a  mov     rax, rcx
0x180099d1d  neg     rax
0x180099d20  sbb     r9d, r9d; cchCount2
0x180099d23  lea     r10, word_180124798
0x180099d2a  mov     r8, r10
0x180099d2d  test    rcx, rcx
0x180099d30  cmovnz  r8, rcx; lpString2
0x180099d34  mov     rdx, [rsp+228h+var_128]
0x180099d3c  mov     rax, [rsp+228h+lpString1]
0x180099d44  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180099d48  jnz     short loc_180099D61
0x180099d4a  test    rax, rax
0x180099d4d  jz      short loc_180099D5E
0x180099d4f  or      rdx, rdx
0x180099d52  inc     rdx
0x180099d55  cmp     [rax+rdx*2], r11w
0x180099d5a  jnz     short loc_180099D52
0x180099d5c  jmp     short loc_180099D61
0x180099d5e  mov     rdx, r11; cchCount1
0x180099d61  test    rax, rax
0x180099d64  cmovnz  r10, rax
0x180099d68  mov     [rsp+228h+bIgnoreCase], r11d; int
0x180099d6d  mov     rcx, r10; lpString1
0x180099d70  call    cs:__imp_CompareStringOrdinal
0x180099d76  cmp     eax, 2
0x180099d79  jnz     loc_18009A11F
0x180099d7f  mov     [rsp+228h+var_1B6], 1
0x180099d84  xor     edi, edi
0x180099d86  mov     [rsp+228h+var_178], rdi
0x180099d8e  mov     rax, [r15]
0x180099d91  lea     rdx, [rsp+228h+var_178]
0x180099d99  mov     rcx, r15
0x180099d9c  mov     rax, [rax+40h]
0x180099da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099da5  mov     rcx, [rsp+228h]; this
0x180099dad  test    eax, eax
0x180099daf  jns     short loc_180099DC3
0x180099db1  mov     r9d, eax; char *
0x180099db4  lea     r8, aOnecoreuapBase_147; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180099dbb  lea     edx, [rdi+74h]; void *
0x180099dbe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180099dc3  mov     rax, [rsp+228h+var_178]
0x180099dcb  test    rax, rax
0x180099dce  jz      loc_18009A104
0x180099dd4  mov     [rsp+228h+var_1B7], 1
0x180099dd9  mov     [rsp+228h+var_E8], rax
0x180099de1  mov     [rsp+228h+var_1B0], rdi
0x180099de6  mov     rax, [r15]
0x180099de9  mov     rbx, [rax+20h]
0x180099ded  lea     rcx, [rsp+228h+var_1B0]
0x180099df2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180099df7  lea     rdx, [rsp+228h+var_1B0]
0x180099dfc  mov     rcx, r15
0x180099dff  mov     rax, rbx
0x180099e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099e07  mov     rcx, [rsp+228h]; this
0x180099e0f  test    eax, eax
0x180099e11  jns     short loc_180099E27
0x180099e13  mov     r9d, eax; char *
0x180099e16  lea     r8, aOnecoreuapBase_147; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180099e1d  mov     edx, 81h; void *
0x180099e22  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180099e27  mov     [rsp+228h+var_1B4], edi
0x180099e2b  mov     rcx, [rsp+228h+var_1B0]
0x180099e30  mov     rax, [rcx]
0x180099e33  lea     r8, [rsp+228h+var_1B4]
0x180099e38  mov     rdx, cs:off_18011DEF8; "c:offlineHeaders"
0x180099e3f  mov     rax, [rax+20h]
0x180099e43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099e48  mov     r13d, eax
0x180099e4b  test    eax, eax
0x180099e4d  cmovs   r13d, edi
0x180099e51  mov     [rsp+228h+var_1A4], r13d
0x180099e59  mov     rcx, rsi; this
0x180099e5c  cmp     [rsp+228h+var_1B4], edi
0x180099e60  jz      loc_180099F75
0x180099e66  call    ?get_payloadSize@Notification@@QEAA_KXZ; Notification::get_payloadSize(void)
0x180099e6b  lea     edi, [rax+8]
0x180099e6e  mov     [rsp+228h+var_1A8], edi
0x180099e75  call    cs:__imp_GetProcessHeap
0x180099e7b  mov     r8d, edi; dwBytes
0x180099e7e  xor     edx, edx; dwFlags
0x180099e80  mov     rcx, rax; hHeap
0x180099e83  call    cs:__imp_HeapAlloc
0x180099e89  mov     rbx, rax
0x180099e8c  mov     [rsp+228h+lpMem], rax
0x180099e94  mov     rcx, [rsp+228h]; this
0x180099e9c  xor     r15d, r15d
0x180099e9f  test    rax, rax
0x180099ea2  jnz     short loc_180099EB5
0x180099ea4  lea     r8, aOnecoreuapBase_147; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180099eab  mov     edx, 8Fh; void *
0x180099eb0  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180099eb5  lea     rax, [rsp+228h+lpMem]
0x180099ebd  mov     [rsp+228h+var_188], rax
0x180099ec5  mov     [rsp+228h+var_180], 1
0x180099ecd  mov     dword ptr [rbx], 1
0x180099ed3  lea     rcx, [r14+20h]
0x180099ed7  mov     rax, [rcx]
0x180099eda  lea     rdx, [rbx+4]
0x180099ede  mov     rax, [rax+18h]
0x180099ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099ee7  mov     rcx, [rsp+228h]; this
0x180099eef  test    eax, eax
0x180099ef1  jns     short loc_180099F07
0x180099ef3  mov     r9d, eax; char *
0x180099ef6  lea     r8, aOnecoreuapBase_147; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180099efd  mov     edx, 99h; void *
0x180099f02  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180099f07  mov     rcx, rsi; this
0x180099f0a  call    ?get_payloadSize@Notification@@QEAA_KXZ; Notification::get_payloadSize(void)
0x180099f0f  mov     r14, rax
0x180099f12  mov     rcx, rsi; this
0x180099f15  call    ?get_payloadBytes@Notification@@QEAAPEAEXZ; Notification::get_payloadBytes(void)
0x180099f1a  lea     rcx, [rbx+8]; void *
0x180099f1e  mov     r8, r14; Size
0x180099f21  mov     rdx, rax; Src
0x180099f24  call    memcpy_0
0x180099f29  mov     qword ptr [rsp+228h+bIgnoreCase], r15
0x180099f2e  mov     r9d, edi
0x180099f31  mov     r8, [rsp+228h+lpMem]
0x180099f39  xor     edx, edx
0x180099f3b  mov     rcx, [rsp+228h+var_E8]
0x180099f43  call    cs:__imp_RtlPublishWnfStateData
0x180099f49  mov     ecx, eax; this
0x180099f4b  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180099f50  mov     ebx, eax
0x180099f52  mov     rdi, [rsp+228h+lpMem]
0x180099f5a  test    rdi, rdi
0x180099f5d  jz      short loc_180099FB0
0x180099f5f  call    cs:__imp_GetProcessHeap
0x180099f65  mov     r8, rdi; lpMem
0x180099f68  xor     edx, edx; dwFlags
0x180099f6a  mov     rcx, rax; hHeap
0x180099f6d  call    cs:__imp_HeapFree
0x180099f73  jmp     short loc_180099FB0
0x180099f75  call    ?get_payloadSize@Notification@@QEAA_KXZ; Notification::get_payloadSize(void)
0x180099f7a  mov     rbx, rax
0x180099f7d  mov     [rsp+228h+var_1A8], ebx
0x180099f84  mov     rcx, rsi; this
0x180099f87  call    ?get_payloadBytes@Notification@@QEAAPEAEXZ; Notification::get_payloadBytes(void)
0x180099f8c  mov     qword ptr [rsp+228h+bIgnoreCase], rdi; int
0x180099f91  mov     r9d, ebx
0x180099f94  mov     r8, rax
0x180099f97  xor     edx, edx
0x180099f99  mov     rcx, [rsp+228h+var_E8]
0x180099fa1  call    cs:__imp_RtlPublishWnfStateData
0x180099fa7  mov     ecx, eax; this
0x180099fa9  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180099fae  mov     ebx, eax
0x180099fb0  cmp     ebx, 80070005h
0x180099fb6  jnz     loc_18009A040
0x180099fbc  lea     rcx, [rsp+228h+var_16C]; unsigned int *
0x180099fc4  call    ?WpnGetCurrentProcessIntegrityLevel@@YAJPEAK@Z; WpnGetCurrentProcessIntegrityLevel(ulong *)
0x180099fc9  mov     rcx, [rsp+228h]; this
0x180099fd1  test    eax, eax
0x180099fd3  jns     short loc_180099FE9
0x180099fd5  mov     r9d, eax; char *
0x180099fd8  lea     r8, aOnecoreuapBase_147; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180099fdf  mov     edx, 0B8h; void *
0x180099fe4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180099fe9  lea     rcx, [rsp+228h+peUse]; peUse
0x180099ff1  call    ?WpnGetUserSidAccount@@YAJPEAW4_SID_NAME_USE@@@Z; WpnGetUserSidAccount(_SID_NAME_USE *)
0x180099ff6  mov     rcx, [rsp+228h]; this
0x180099ffe  test    eax, eax
0x18009a000  jns     short loc_18009A016
0x18009a002  mov     r9d, eax; char *
0x18009a005  lea     r8, aOnecoreuapBase_147; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18009a00c  mov     edx, 0B9h; void *
0x18009a011  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009a016  lea     rcx, [rsp+228h+var_1B8]; bool *
0x18009a01b  call    ?IsAuthenticatedUser@@YAJPEA_N@Z; IsAuthenticatedUser(bool *)
0x18009a020  mov     rcx, [rsp+228h]; this
0x18009a028  test    eax, eax
0x18009a02a  jns     short loc_18009A040
0x18009a02c  mov     r9d, eax; char *
0x18009a02f  lea     r8, aOnecoreuapBase_147; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18009a036  mov     edx, 0BAh; void *
0x18009a03b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009a040  mov     rcx, [rsp+228h]; this
0x18009a048  test    ebx, ebx
0x18009a04a  jns     short loc_18009A060
0x18009a04c  mov     r9d, ebx; char *
0x18009a04f  lea     r8, aOnecoreuapBase_147; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18009a056  mov     edx, 0BDh; void *
0x18009a05b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009a060  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57975764@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57975764@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57975764> `wil::Feature<__WilFeatureTraits_Feature_57975764>::GetImpl(void)'::`2'::impl
0x18009a067  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57975764@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57975764>::__private_IsEnabled(void)
0x18009a06c  test    al, al
0x18009a06e  jnz     short loc_18009A0AE
0x18009a070  test    cs:byte_18015DE45, 1
0x18009a077  jz      short loc_18009A0A8
0x18009a079  lea     rdx, [rsp+228h+var_E0]
0x18009a081  mov     rcx, rsi
0x18009a084  call    ?get_handlerKey@Notification@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Notification::get_handlerKey(void)
0x18009a089  mov     r12d, 2
0x18009a08f  cmp     qword ptr [rax+18h], 7
0x18009a094  jbe     short loc_18009A099
0x18009a096  mov     rax, [rax]
0x18009a099  mov     r8, rax
0x18009a09c  lea     rdx, WPNEND_BACKGROUND_TASK_ACTIVATED_SYSTEM
0x18009a0a3  call    McTemplateU0z_EventWriteTransfer
0x18009a0a8  test    r12b, 2
0x18009a0ac  jmp     short loc_18009A0EA
0x18009a0ae  test    cs:byte_18015DE47, 2
0x18009a0b5  jz      short loc_18009A0E6
0x18009a0b7  lea     rdx, [rsp+228h+var_E0]
  ... truncated ...
```
