# ToastSession::ToastRequestCompleted(INotificationCollection *,INotificationHandlerCollection *)

- ea: `0x180092570`
- end: `0x180093452`
- name: `?ToastRequestCompleted@ToastSession@@UEAAJPEAUINotificationCollection@@PEAUINotificationHandlerCollection@@@Z`
- size: `3810`
- prototype: `__int64 __fastcall(ToastSession *__hidden this, struct INotificationCollection *, struct INotificationHandlerCollection *)`
- caller_count: `0`
- callee_count: `30`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004e38`
- `0x18000e090`
- `0x18000e5f4`
- `0x180011618`
- `0x1800117c0`
- `0x180013360`
- `0x180014120`
- `0x18001bf30`
- `0x18004187c`
- `0x180049644`
- `0x18004b4c4`
- `0x1800542a8`
- `0x18007162c`
- `0x180079d24`
- `0x180084690`
- `0x180085560`
- `0x180086414`
- `0x1800884e8`
- `0x18008a97c`
- `0x180092570`
- `0x180094814`
- `0x180094854`
- `0x18009487c`
- `0x1800b99f0`
- `0x1800ba0d0`
- `0x1800ec8dc`
- `0x180104628`
- `0x180104660`
- `0x1801048ec`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800925c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800925c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180092a7d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180092a7d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180092a6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180092a6f`
- `OLEAUT32!__imp_SysAllocString` at `0x180092cd5`
- `OLEAUT32!__imp_SysAllocString` at `0x180092ceb`
- `OLEAUT32!__imp_SysAllocString` at `0x180092dc6`
- `OLEAUT32!__imp_SysAllocString` at `0x180092ddc`
- `OLEAUT32!__imp_SysAllocString` at `0x180093028`
- `OLEAUT32!__imp_SysAllocString` at `0x180092cd5`
- `OLEAUT32!__imp_SysAllocString` at `0x180092ceb`
- `OLEAUT32!__imp_SysAllocString` at `0x180092dc6`
- `OLEAUT32!__imp_SysAllocString` at `0x180092ddc`
- `OLEAUT32!__imp_SysAllocString` at `0x180093028`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x180092a51`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x180092a51`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180092a99`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180092a99`

## string_xrefs

- `0x180092d60`: `AdaptiveJson`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall ToastSession::ToastRequestCompleted(
        ToastSession *this,
        struct INotificationCollection *a2,
        OLECHAR *a3)
{
  struct INotificationCollection *v3; // r14
  ToastSession *v4; // r15
  char *v5; // rbx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, GUID *, __int64 *); // rbx
  int v8; // ebx
  __int64 v9; // rdx
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  int v13; // eax
  unsigned int i; // r12d
  __int64 (__fastcall *v15)(struct INotificationCollection *, _QWORD, WpnDatabaseHelpers **); // rbx
  int v16; // eax
  WpnDatabaseHelpers *v17; // rdi
  __int64 (__fastcall *v18)(WpnDatabaseHelpers *, __int64 *); // rbx
  int v19; // eax
  int v20; // eax
  unsigned __int16 **v21; // r8
  int AppUserModelId; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  WpnDatabaseHelpers *v26; // rdi
  __int64 (__fastcall *v27)(WpnDatabaseHelpers *, OLECHAR **); // rbx
  int v28; // eax
  WpnDatabaseHelpers *v29; // rdi
  __int64 (__fastcall *v30)(WpnDatabaseHelpers *, OLECHAR **); // rbx
  int v31; // eax
  WpnDatabaseHelpers *v32; // rdi
  __int64 (__fastcall *v33)(WpnDatabaseHelpers *, IStream **); // rbx
  int v34; // eax
  HRESULT v35; // eax
  SIZE_T QuadPart; // rbx
  HANDLE ProcessHeap; // rax
  void *v38; // r13
  HRESULT v39; // eax
  WpnDatabaseHelpers *v40; // rdi
  __int64 (__fastcall *v41)(WpnDatabaseHelpers *, __int64 *); // rbx
  int v42; // eax
  _QWORD *v43; // r14
  WpnDatabaseHelpers *v44; // rdi
  int (__fastcall *v45)(WpnDatabaseHelpers *, __int64 *); // rbx
  int v46; // eax
  unsigned int j; // r12d
  __int64 v48; // rdi
  __int64 (__fastcall *v49)(__int64, _QWORD, __int64 *, __int64 *); // rbx
  int v50; // eax
  __int64 v51; // rbx
  _QWORD *v52; // rax
  __int64 v53; // r9
  __int64 v54; // rdx
  BSTR v55; // r13
  int v56; // eax
  unsigned int k; // r14d
  __int64 (__fastcall *v58)(BSTR, _QWORD, _QWORD **); // rbx
  int v59; // eax
  _QWORD *v60; // rdi
  __int64 (__fastcall *v61)(_QWORD *, OLECHAR **); // rbx
  int v62; // eax
  int v63; // eax
  wil *v64; // rcx
  int v65; // r8d
  int v66; // r9d
  int v68; // [rsp+20h] [rbp-2E8h]
  int v69; // [rsp+20h] [rbp-2E8h]
  WpnDatabaseHelpers *v70; // [rsp+40h] [rbp-2C8h] BYREF
  unsigned int v71; // [rsp+48h] [rbp-2C0h] BYREF
  char *v72; // [rsp+50h] [rbp-2B8h] BYREF
  _QWORD *v73; // [rsp+58h] [rbp-2B0h] BYREF
  __int64 v74; // [rsp+60h] [rbp-2A8h] BYREF
  int v75; // [rsp+68h] [rbp-2A0h]
  __int64 v76; // [rsp+70h] [rbp-298h] BYREF
  __int64 v77; // [rsp+78h] [rbp-290h] BYREF
  unsigned int v78; // [rsp+80h] [rbp-288h] BYREF
  int v79; // [rsp+84h] [rbp-284h] BYREF
  unsigned int v80; // [rsp+88h] [rbp-280h]
  unsigned int v81; // [rsp+8Ch] [rbp-27Ch] BYREF
  __int64 v82; // [rsp+90h] [rbp-278h] BYREF
  IStream *pstm; // [rsp+98h] [rbp-270h] BYREF
  BSTR v84; // [rsp+A0h] [rbp-268h] BYREF
  int v85[2]; // [rsp+A8h] [rbp-260h] BYREF
  OLECHAR *v86; // [rsp+B0h] [rbp-258h] BYREF
  __int64 v87; // [rsp+B8h] [rbp-250h]
  __int64 v88; // [rsp+C0h] [rbp-248h]
  ULARGE_INTEGER pui; // [rsp+C8h] [rbp-240h] BYREF
  __int128 v90; // [rsp+D0h] [rbp-238h] BYREF
  __int64 v91; // [rsp+E0h] [rbp-228h]
  ToastSession *v92; // [rsp+E8h] [rbp-220h] BYREF
  OLECHAR *psz; // [rsp+F0h] [rbp-218h] BYREF
  __int64 v94; // [rsp+F8h] [rbp-210h]
  __int64 v95; // [rsp+100h] [rbp-208h]
  int v96[4]; // [rsp+108h] [rbp-200h] BYREF
  __int64 v97; // [rsp+118h] [rbp-1F0h]
  __int64 v98; // [rsp+120h] [rbp-1E8h] BYREF
  __int64 v99; // [rsp+128h] [rbp-1E0h]
  __int64 v100; // [rsp+130h] [rbp-1D8h]
  OLECHAR *v101; // [rsp+138h] [rbp-1D0h] BYREF
  __int64 v102; // [rsp+140h] [rbp-1C8h]
  __int64 v103; // [rsp+148h] [rbp-1C0h]
  OLECHAR *v104; // [rsp+150h] [rbp-1B8h] BYREF
  __int64 v105; // [rsp+158h] [rbp-1B0h]
  __int64 v106; // [rsp+160h] [rbp-1A8h]
  __int128 v107; // [rsp+168h] [rbp-1A0h] BYREF
  __int64 v108; // [rsp+178h] [rbp-190h]
  __int64 v109; // [rsp+180h] [rbp-188h] BYREF
  __int64 v110; // [rsp+188h] [rbp-180h]
  __int64 v111; // [rsp+190h] [rbp-178h]
  __int128 v112; // [rsp+198h] [rbp-170h] BYREF
  __int64 v113; // [rsp+1A8h] [rbp-160h]
  struct INotificationCollection *v114; // [rsp+1B0h] [rbp-158h]
  _QWORD v115[2]; // [rsp+1B8h] [rbp-150h] BYREF
  _QWORD v116[2]; // [rsp+1C8h] [rbp-140h] BYREF
  char v117; // [rsp+1D8h] [rbp-130h]
  _QWORD v118[2]; // [rsp+1E0h] [rbp-128h] BYREF
  _QWORD v119[2]; // [rsp+1F0h] [rbp-118h] BYREF
  int v120; // [rsp+200h] [rbp-108h]
  int v121; // [rsp+204h] [rbp-104h]
  __int64 v122; // [rsp+208h] [rbp-100h]
  char *v123; // [rsp+210h] [rbp-F8h]
  void *v124; // [rsp+218h] [rbp-F0h]
  DWORD LowPart; // [rsp+220h] [rbp-E8h]
  int v126; // [rsp+224h] [rbp-E4h]
  __int64 v127; // [rsp+228h] [rbp-E0h]
  GUID v128; // [rsp+230h] [rbp-D8h]
  BSTR v129; // [rsp+240h] [rbp-C8h]
  BSTR v130; // [rsp+248h] [rbp-C0h]
  __int64 v131; // [rsp+250h] [rbp-B8h]
  __int64 v132; // [rsp+258h] [rbp-B0h]
  __int128 v133; // [rsp+260h] [rbp-A8h]
  int v134; // [rsp+270h] [rbp-98h]
  unsigned int v135; // [rsp+274h] [rbp-94h]
  __int64 v136; // [rsp+278h] [rbp-90h]
  __int128 v137; // [rsp+280h] [rbp-88h]
  __int128 v138; // [rsp+290h] [rbp-78h]
  _BYTE v139[32]; // [rsp+2A0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+0h]

  v84 = a3;
  v3 = a2;
  v114 = a2;
  v4 = this;
  v92 = this;
  v76 = 0;
  v5 = (char *)this + 88;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v72 = v5;
  if ( !*((_QWORD *)v4 + 2) || !*((_DWORD *)v4 + 3) || (v6 = *((_QWORD *)v4 + 3)) == 0 )
  {
    v8 = -2147467259;
    v9 = 961;
    goto LABEL_66;
  }
  v7 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v6 + 40LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v76);
  v8 = v7(v6, *((unsigned int *)v4 + 3), &GUID_904a654e_bee8_4654_bbba_e78766776239, &v76);
  if ( v8 < 0 )
  {
    v9 = 965;
LABEL_66:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
      (const char *)(unsigned int)v8,
      v68);
    Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v72);
    goto LABEL_67;
  }
  v75 = 0;
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v72);
  if ( (unsigned int)dword_18015C038 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18015C038, 0x200000000000LL) )
  {
    v72 = (char *)*((_QWORD *)v4 + 7);
    *(_QWORD *)v85 = *((_QWORD *)v4 + 4);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v10,
      (unsigned int)&byte_18013A99F,
      v11,
      v12,
      (__int64)v85,
      (__int64)&v72);
  }
  try
  {
    v112 = 0;
    v113 = 0;
    *(_OWORD *)v96 = 0;
    v97 = 0;
    v107 = 0;
    v108 = 0;
    v90 = 0;
    v91 = 0;
    v116[0] = &v112;
    v116[1] = v96;
    v117 = 1;
    v78 = 0;
    v13 = (*(__int64 (__fastcall **)(struct INotificationCollection *, unsigned int *))(*(_QWORD *)v3 + 32LL))(v3, &v78);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3EB,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)(unsigned int)v13,
        v68);
    for ( i = 0; ; ++i )
    {
      v80 = i;
      if ( i >= v78 )
        break;
      v70 = 0;
      v15 = *(__int64 (__fastcall **)(struct INotificationCollection *, _QWORD, WpnDatabaseHelpers **))(*(_QWORD *)v3 + 24LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v70);
      v16 = v15(v3, i, &v70);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3EF,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v16,
          v68);
      v109 = 0;
      v110 = 0;
      v111 = 0;
      v17 = v70;
      v18 = *(__int64 (__fastcall **)(WpnDatabaseHelpers *, __int64 *))(*(_QWORD *)v70 + 40LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v109);
      v110 = -1;
      v111 = -1;
      v19 = v18(v17, &v109);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3F2,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v19,
          v68);
      v79 = 0;
      *(_QWORD *)v85 = 0;
      v72 = 0;
      psz = 0;
      v94 = 0;
      v95 = 0;
      v86 = 0;
      v87 = 0;
      v88 = 0;
      v104 = 0;
      v105 = 0;
      v106 = 0;
      v101 = 0;
      v102 = 0;
      v103 = 0;
      v20 = (*(__int64 (__fastcall **)(WpnDatabaseHelpers *, int *))(*(_QWORD *)v70 + 24LL))(v70, &v79);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3FA,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v20,
          v68);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&psz);
      v94 = -1;
      v95 = -1;
      AppUserModelId = WpnDatabaseHelpers::GetAppUserModelId(v70, (struct IWpnNotification *)&psz, v21);
      if ( AppUserModelId < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3FB,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)AppUserModelId,
          v68);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v86);
      v87 = -1;
      v88 = -1;
      v23 = ToastSession::PopulatePFN((ToastSession *)((char *)v4 - 8), psz, &v86);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3FC,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v23,
          v68);
      v24 = (*(__int64 (__fastcall **)(WpnDatabaseHelpers *, int *))(*(_QWORD *)v70 + 88LL))(v70, v85);
      if ( v24 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3FD,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v24,
          v68);
      v25 = (*(__int64 (__fastcall **)(WpnDatabaseHelpers *, char **))(*(_QWORD *)v70 + 72LL))(v70, &v72);
      if ( v25 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3FE,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v25,
          v68);
      v26 = v70;
      v27 = *(__int64 (__fastcall **)(WpnDatabaseHelpers *, OLECHAR **))(*(_QWORD *)v70 + 56LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v104);
      v105 = -1;
      v106 = -1;
      v28 = v27(v26, &v104);
      if ( v28 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3FF,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v28,
          v68);
      v29 = v70;
      v30 = *(__int64 (__fastcall **)(WpnDatabaseHelpers *, OLECHAR **))(*(_QWORD *)v70 + 64LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v101);
      v102 = -1;
      v103 = -1;
      v31 = v30(v29, &v101);
      if ( v31 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x400,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v31,
          v68);
      pui.QuadPart = 0;
      pstm = 0;
      v32 = v70;
      v33 = *(__int64 (__fastcall **)(WpnDatabaseHelpers *, IStream **))(*(_QWORD *)v70 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pstm);
      v34 = v33(v32, &pstm);
      if ( v34 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x405,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v34,
          v68);
      v35 = IStream_Size(pstm, &pui);
      if ( v35 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x406,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v35,
          v68);
      QuadPart = pui.QuadPart;
      ProcessHeap = GetProcessHeap();
      v38 = HeapAlloc(ProcessHeap, 0, QuadPart);
      v39 = IStream_Read(pstm, v38, pui.LowPart);
      if ( v39 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x40D,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v39,
          v68);
      v98 = 0;
      v99 = 0;
      v100 = 0;
      v40 = v70;
      v41 = *(__int64 (__fastcall **)(WpnDatabaseHelpers *, __int64 *))(*(_QWORD *)v70 + 120LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v98);
      v99 = -1;
      v100 = -1;
      v42 = v41(v40, &v98);
      if ( v42 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x410,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v42,
          v68);
      v82 = 0;
      v43 = 0;
      v73 = 0;
      v71 = 0;
      v44 = v70;
      v45 = *(int (__fastcall **)(WpnDatabaseHelpers *, __int64 *))(*(_QWORD *)v70 + 96LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v82);
      if ( v45(v44, &v82) >= 0 && v82 )
      {
        v46 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v82 + 48LL))(v82, &v71);
        if ( v46 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x418,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
            (const char *)(unsigned int)v46,
            v68);
        if ( v71 )
        {
          v43 = operator new(0x18u);
          *v43 = 0;
          v43[1] = 0;
          v43[2] = 0;
          v74 = 0;
          v73 = v43;
          std::unique_ptr<std::vector<_WPN_NOTIFICATION_METADATA_PAIR>>::~unique_ptr<std::vector<_WPN_NOTIFICATION_METADATA_PAIR>>(&v74);
          std::vector<_WPN_NOTIFICATION_METADATA_PAIR>::reserve(v43, v71);
          for ( j = 0; j < v71; ++j )
          {
            v74 = 0;
            v77 = 0;
            v48 = v82;
            v49 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, __int64 *))(*(_QWORD *)v82 + 56LL);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &v77,
              0);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &v74,
              0);
            v50 = v49(v48, j, &v74, &v77);
            if ( v50 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x424,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
                (const char *)(unsigned int)v50,
                v68);
            v118[0] = v74;
            v118[1] = v77;
            std::vector<_WPN_NOTIFICATION_METADATA_PAIR>::push_back(v43, v118);
            v115[0] = v74;
            v74 = 0;
            v115[1] = v77;
            v77 = 0;
            std::vector<std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>::push_back(
              &v107,
              v115);
            std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v115);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v77);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v74);
          }
          i = v80;
        }
      }
      v119[0] = SysAllocString(psz);
      v119[1] = SysAllocString(v86);
      v120 = v79;
      v121 = 0;
      v122 = *(_QWORD *)v85;
      v123 = v72;
      v124 = v38;
      LowPart = pui.LowPart;
      v51 = v98;
      v52 = (_QWORD *)std::wstring::wstring(v139, L"AdaptiveJson");
      v53 = -1;
      do
        ++v53;
      while ( *(_WORD *)(v51 + 2 * v53) );
      v54 = v52[2];
      if ( v52[3] > 7u )
        v52 = (_QWORD *)*v52;
      v126 = (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v52, v54, v51, v53);
      v127 = 0;
      v128 = GUID_NULL;
      v129 = SysAllocString(v104);
      v130 = SysAllocString(v101);
      v131 = 0;
      v132 = 0;
      v133 = 0;
      v134 = 0;
      v135 = v71;
      if ( v43 )
        v136 = *v43;
      else
        v136 = 0;
      v137 = 0;
      v138 = 0;
      std::vector<_WPN_TOAST_NOTIFICATION>::_Emplace_one_at_back<_WPN_TOAST_NOTIFICATION>(&v112, v119);
      std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(v139);
      if ( v43 )
      {
        if ( *((_QWORD *)&v90 + 1) == v91 )
        {
          std::vector<std::unique_ptr<std::vector<_WPN_NOTIFICATION_METADATA_PAIR>>>::_Emplace_reallocate<std::unique_ptr<std::vector<_WPN_NOTIFICATION_METADATA_PAIR>>>(
            &v90,
            *((_QWORD *)&v90 + 1),
            &v73);
        }
        else
        {
          v73 = 0;
          **((_QWORD **)&v90 + 1) = v43;
          *((_QWORD *)&v90 + 1) += 8LL;
        }
      }
      std::unique_ptr<std::vector<_WPN_NOTIFICATION_METADATA_PAIR>>::~unique_ptr<std::vector<_WPN_NOTIFICATION_METADATA_PAIR>>(&v73);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v82);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v98);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pstm);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v101);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v104);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v86);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&psz);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v109);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v70);
      v3 = v114;
    }
    v81 = 0;
    v55 = v84;
    v56 = (*(__int64 (__fastcall **)(BSTR, unsigned int *))(*(_QWORD *)v84 + 32LL))(v84, &v81);
    if ( v56 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x44A,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)(unsigned int)v56,
        v68);
    for ( k = 0; k < v81; ++k )
    {
      v73 = 0;
      v58 = *(__int64 (__fastcall **)(BSTR, _QWORD, _QWORD **))(*(_QWORD *)v55 + 24LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
      v59 = v58(v55, k, &v73);
      if ( v59 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x44E,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v59,
          v68);
      v86 = 0;
      v87 = 0;
      v88 = 0;
      v60 = v73;
      v61 = *(__int64 (__fastcall **)(_QWORD *, OLECHAR **))(*v73 + 24LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v86);
      v87 = -1;
      v88 = -1;
      v62 = v61(v60, &v86);
      if ( v62 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x451,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v62,
          v68);
      v84 = SysAllocString(v86);
      std::vector<unsigned short const *>::_Emplace_one_at_back<unsigned short const *>(v96, &v84);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v86);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
    }
    v69 = v96[0];
    v63 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v76 + 48LL))(
            v76,
            *((unsigned int *)v4 + 2),
            v112,
            0x2E8BA2E8BA2E8BA3LL * ((__int64)(*((_QWORD *)&v112 + 1) - v112) >> 4));
    if ( v63 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x45B,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)(unsigned int)v63,
        v69);
    v117 = 0;
    lambda_817ee658191cb58eccb943418947fb1c_::operator()(v116);
    if ( (_QWORD)v90 )
    {
      std::_Destroy_range<std::allocator<std::unique_ptr<std::vector<_WPN_NOTIFICATION_METADATA_PAIR>>>>(
        v90,
        *((_QWORD *)&v90 + 1));
      std::_Deallocate<16>(v90, (v91 - v90) & 0xFFFFFFFFFFFFFFF8uLL);
      v90 = 0;
      v91 = 0;
    }
    if ( (_QWORD)v107 )
    {
      std::_Destroy_range<std::allocator<std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>>(
        v107,
        *((_QWORD *)&v107 + 1));
      std::_Deallocate<16>(v107, (v108 - v107) & 0xFFFFFFFFFFFFFFF0uLL);
      v107 = 0;
      v108 = 0;
    }
    if ( *(_QWORD *)v96 )
    {
      std::_Deallocate<16>(*(_QWORD *)v96, (v97 - *(_QWORD *)v96) & 0xFFFFFFFFFFFFFFF8uLL);
      *(_OWORD *)v96 = 0;
      v97 = 0;
    }
    v64 = (wil *)v112;
    if ( (_QWORD)v112 )
      std::_Deallocate<16>(v112, 16 * ((v113 - (__int64)v112) >> 4));
  }
  catch ( ... )
  {
    v75 = wil::ResultFromCaughtException(v64);
    v4 = v92;
  }
  v8 = v75;
  if ( (unsigned int)dword_18015C038 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18015C038, 0x200000000000LL) )
  {
    v92 = (ToastSession *)*((_QWORD *)v4 + 7);
    v84 = (BSTR)*((_QWORD *)v4 + 4);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v84,
      (unsigned int)byte_18013AAC1,
      v65,
      v66,
      (__int64)&v84,
      (__int64)&v92);
  }
LABEL_67:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v76);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180092570  push    rbx
0x180092572  push    rsi
0x180092573  push    rdi
0x180092574  push    r12
0x180092576  push    r13
0x180092578  push    r14
0x18009257a  push    r15
0x18009257c  sub     rsp, 2D0h
0x180092583  mov     rax, cs:__security_cookie
0x18009258a  xor     rax, rsp
0x18009258d  mov     [rsp+308h+var_48], rax
0x180092595  mov     [rsp+308h+var_268], r8
0x18009259d  mov     r14, rdx
0x1800925a0  mov     [rsp+308h+var_158], rdx
0x1800925a8  mov     r15, rcx
0x1800925ab  mov     [rsp+308h+var_220], rcx
0x1800925b3  xor     esi, esi
0x1800925b5  mov     [rsp+308h+var_298], rsi
0x1800925ba  lea     rbx, [rcx+58h]
0x1800925be  mov     rcx, rbx; lpCriticalSection
0x1800925c1  call    cs:__imp_EnterCriticalSection
0x1800925c7  mov     [rsp+308h+var_2B8], rbx
0x1800925cc  cmp     [r15+10h], rsi
0x1800925d0  jz      loc_180093259
0x1800925d6  cmp     [r15+0Ch], esi
0x1800925da  jz      loc_180093259
0x1800925e0  mov     rdi, [r15+18h]
0x1800925e4  test    rdi, rdi
0x1800925e7  jz      loc_180093259
0x1800925ed  mov     rax, [rdi]
0x1800925f0  mov     rbx, [rax+28h]
0x1800925f4  lea     rcx, [rsp+308h+var_298]
0x1800925f9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800925fe  lea     r9, [rsp+308h+var_298]
0x180092603  lea     r8, _GUID_904a654e_bee8_4654_bbba_e78766776239
0x18009260a  mov     edx, [r15+0Ch]
0x18009260e  mov     rcx, rdi
0x180092611  mov     rax, rbx
0x180092614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092619  mov     ebx, eax
0x18009261b  test    eax, eax
0x18009261d  jns     short loc_180092629
0x18009261f  mov     edx, 3C5h
0x180092624  jmp     loc_180093263
0x180092629  mov     [rsp+308h+var_2A0], esi
0x18009262d  lea     rcx, [rsp+308h+var_2B8]; this
0x180092632  call    ??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)
0x180092637  mov     eax, cs:dword_18015C038
0x18009263d  cmp     eax, 5
0x180092640  jbe     short loc_180092695
0x180092642  mov     rdx, 200000000000h
0x18009264c  lea     rcx, dword_18015C038
0x180092653  call    _tlgKeywordOn
0x180092658  test    al, al
0x18009265a  jz      short loc_180092695
0x18009265c  mov     rax, [r15+38h]
0x180092660  mov     [rsp+308h+var_2B8], rax
0x180092665  mov     rax, [r15+20h]
0x180092669  mov     qword ptr [rsp+308h+var_260], rax
0x180092671  lea     rax, [rsp+308h+var_2B8]
0x180092676  mov     [rsp+308h+var_2E0], rax
0x18009267b  lea     rax, [rsp+308h+var_260]
0x180092683  mov     qword ptr [rsp+308h+var_2E8], rax; int
0x180092688  lea     rdx, byte_18013A99F
0x18009268f  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180092694  nop
0x180092695  xorps   xmm0, xmm0
0x180092698  movdqu  [rsp+308h+var_170], xmm0
0x1800926a1  mov     [rsp+308h+var_160], rsi
0x1800926a9  movdqu  xmmword ptr [rsp+308h+var_200], xmm0
0x1800926b2  mov     [rsp+308h+var_1F0], rsi
0x1800926ba  movdqu  [rsp+308h+var_1A0], xmm0
0x1800926c3  mov     [rsp+308h+var_190], rsi
0x1800926cb  movdqu  [rsp+308h+var_238], xmm0
0x1800926d4  mov     [rsp+308h+var_228], rsi
0x1800926dc  lea     rax, [rsp+308h+var_170]
0x1800926e4  mov     [rsp+308h+var_140], rax
0x1800926ec  lea     rax, [rsp+308h+var_200]
0x1800926f4  mov     [rsp+308h+var_138], rax
0x1800926fc  mov     [rsp+308h+var_130], 1
0x180092704  mov     [rsp+308h+var_288], esi
0x18009270b  mov     rax, [r14]
0x18009270e  lea     rdx, [rsp+308h+var_288]
0x180092716  mov     rcx, r14
0x180092719  mov     rax, [rax+20h]
0x18009271d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092722  mov     rcx, [rsp+308h]; this
0x18009272a  test    eax, eax
0x18009272c  js      loc_1800932B5
0x180092732  mov     r12d, esi
0x180092735  mov     [rsp+308h+var_280], r12d
0x18009273d  cmp     r12d, [rsp+308h+var_288]
0x180092745  jnb     loc_180092F36
0x18009274b  mov     [rsp+308h+var_2C8], rsi
0x180092750  mov     rax, [r14]
0x180092753  mov     rbx, [rax+18h]
0x180092757  lea     rcx, [rsp+308h+var_2C8]
0x18009275c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180092761  lea     r8, [rsp+308h+var_2C8]
0x180092766  mov     edx, r12d
0x180092769  mov     rcx, r14
0x18009276c  mov     rax, rbx
0x18009276f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092774  mov     rcx, [rsp+308h]; this
0x18009277c  test    eax, eax
0x18009277e  js      loc_1800932CA
0x180092784  mov     [rsp+308h+var_188], rsi
0x18009278c  mov     [rsp+308h+var_180], rsi
0x180092794  mov     [rsp+308h+var_178], rsi
0x18009279c  mov     rdi, [rsp+308h+var_2C8]
0x1800927a1  mov     rax, [rdi]
0x1800927a4  mov     rbx, [rax+28h]
0x1800927a8  lea     rcx, [rsp+308h+var_188]
0x1800927b0  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800927b5  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800927b9  mov     [rsp+308h+var_180], r14
0x1800927c1  mov     [rsp+308h+var_178], r14
0x1800927c9  lea     rdx, [rsp+308h+var_188]
0x1800927d1  mov     rcx, rdi
0x1800927d4  mov     rax, rbx
0x1800927d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800927dc  mov     rcx, [rsp+308h]; this
0x1800927e4  test    eax, eax
0x1800927e6  js      loc_1800932DF
0x1800927ec  mov     [rsp+308h+var_284], esi
0x1800927f3  mov     qword ptr [rsp+308h+var_260], rsi
0x1800927fb  mov     [rsp+308h+var_2B8], rsi
0x180092800  mov     [rsp+308h+psz], rsi
0x180092808  mov     [rsp+308h+var_210], rsi
0x180092810  mov     [rsp+308h+var_208], rsi
0x180092818  mov     [rsp+308h+var_258], rsi
0x180092820  mov     [rsp+308h+var_250], rsi
0x180092828  mov     [rsp+308h+var_248], rsi
0x180092830  mov     [rsp+308h+var_1B8], rsi
0x180092838  mov     [rsp+308h+var_1B0], rsi
0x180092840  mov     [rsp+308h+var_1A8], rsi
0x180092848  mov     [rsp+308h+var_1D0], rsi
0x180092850  mov     [rsp+308h+var_1C8], rsi
0x180092858  mov     [rsp+308h+var_1C0], rsi
0x180092860  mov     rcx, [rsp+308h+var_2C8]
0x180092865  mov     rax, [rcx]
0x180092868  lea     rdx, [rsp+308h+var_284]
0x180092870  mov     rax, [rax+18h]
0x180092874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092879  mov     rcx, [rsp+308h]; this
0x180092881  test    eax, eax
0x180092883  js      loc_1800932F4
0x180092889  lea     rcx, [rsp+308h+psz]
0x180092891  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180092896  mov     [rsp+308h+var_210], r14
0x18009289e  mov     [rsp+308h+var_208], r14
0x1800928a6  lea     rdx, [rsp+308h+psz]; struct IWpnNotification *
0x1800928ae  mov     rcx, [rsp+308h+var_2C8]; this
0x1800928b3  call    ?GetAppUserModelId@WpnDatabaseHelpers@@YAJPEAUIWpnNotification@@PEAPEAG@Z; WpnDatabaseHelpers::GetAppUserModelId(IWpnNotification *,ushort * *)
0x1800928b8  mov     rcx, [rsp+308h]; this
0x1800928c0  test    eax, eax
0x1800928c2  js      loc_180093308
0x1800928c8  lea     rcx, [rsp+308h+var_258]
0x1800928d0  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800928d5  mov     [rsp+308h+var_250], r14
0x1800928dd  mov     [rsp+308h+var_248], r14
0x1800928e5  lea     rcx, [r15-8]; this
0x1800928e9  lea     r8, [rsp+308h+var_258]; unsigned __int16 **
0x1800928f1  mov     rdx, [rsp+308h+psz]; unsigned __int16 *
0x1800928f9  call    ?PopulatePFN@ToastSession@@AEAAJPEBGPEAPEAG@Z; ToastSession::PopulatePFN(ushort const *,ushort * *)
0x1800928fe  mov     rcx, [rsp+308h]; this
0x180092906  test    eax, eax
0x180092908  js      loc_18009331C
0x18009290e  mov     rcx, [rsp+308h+var_2C8]
0x180092913  mov     rax, [rcx]
0x180092916  lea     rdx, [rsp+308h+var_260]
0x18009291e  mov     rax, [rax+58h]
0x180092922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092927  mov     rcx, [rsp+308h]; this
0x18009292f  test    eax, eax
0x180092931  js      loc_180093330
0x180092937  mov     rcx, [rsp+308h+var_2C8]
0x18009293c  mov     rax, [rcx]
0x18009293f  lea     rdx, [rsp+308h+var_2B8]
0x180092944  mov     rax, [rax+48h]
0x180092948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009294d  mov     rcx, [rsp+308h]; this
0x180092955  test    eax, eax
0x180092957  js      loc_180093344
0x18009295d  mov     rdi, [rsp+308h+var_2C8]
0x180092962  mov     rax, [rdi]
0x180092965  mov     rbx, [rax+38h]
0x180092969  lea     rcx, [rsp+308h+var_1B8]
0x180092971  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180092976  mov     [rsp+308h+var_1B0], r14
0x18009297e  mov     [rsp+308h+var_1A8], r14
0x180092986  lea     rdx, [rsp+308h+var_1B8]
0x18009298e  mov     rcx, rdi
0x180092991  mov     rax, rbx
0x180092994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092999  mov     rcx, [rsp+308h]; this
0x1800929a1  test    eax, eax
0x1800929a3  js      loc_180093358
0x1800929a9  mov     rdi, [rsp+308h+var_2C8]
0x1800929ae  mov     rax, [rdi]
0x1800929b1  mov     rbx, [rax+40h]
0x1800929b5  lea     rcx, [rsp+308h+var_1D0]
0x1800929bd  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800929c2  mov     [rsp+308h+var_1C8], r14
0x1800929ca  mov     [rsp+308h+var_1C0], r14
0x1800929d2  lea     rdx, [rsp+308h+var_1D0]
0x1800929da  mov     rcx, rdi
0x1800929dd  mov     rax, rbx
0x1800929e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800929e5  mov     rcx, [rsp+308h]; this
0x1800929ed  test    eax, eax
0x1800929ef  js      loc_18009336C
0x1800929f5  mov     qword ptr [rsp+308h+pui], rsi
0x1800929fd  mov     [rsp+308h+pstm], rsi
0x180092a05  mov     rdi, [rsp+308h+var_2C8]
0x180092a0a  mov     rax, [rdi]
0x180092a0d  mov     rbx, [rax+30h]
0x180092a11  lea     rcx, [rsp+308h+pstm]
0x180092a19  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180092a1e  lea     rdx, [rsp+308h+pstm]
0x180092a26  mov     rcx, rdi
0x180092a29  mov     rax, rbx
0x180092a2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092a31  mov     rcx, [rsp+308h]; this
0x180092a39  test    eax, eax
0x180092a3b  js      loc_180093381
0x180092a41  lea     rdx, [rsp+308h+pui]; pui
0x180092a49  mov     rcx, [rsp+308h+pstm]; pstm
0x180092a51  call    cs:__imp_IStream_Size
0x180092a57  mov     rcx, [rsp+308h]; this
0x180092a5f  test    eax, eax
0x180092a61  js      loc_180093395
0x180092a67  mov     rbx, qword ptr [rsp+308h+pui]
0x180092a6f  call    cs:__imp_GetProcessHeap
0x180092a75  mov     r8, rbx; dwBytes
0x180092a78  xor     edx, edx; dwFlags
0x180092a7a  mov     rcx, rax; hHeap
0x180092a7d  call    cs:__imp_HeapAlloc
0x180092a83  mov     r13, rax
0x180092a86  mov     r8d, dword ptr [rsp+308h+pui]; cb
0x180092a8e  mov     rdx, rax; pv
0x180092a91  mov     rcx, [rsp+308h+pstm]; pstm
0x180092a99  call    cs:__imp_IStream_Read
0x180092a9f  mov     rcx, [rsp+308h]; this
0x180092aa7  test    eax, eax
0x180092aa9  js      loc_1800933A9
0x180092aaf  mov     [rsp+308h+var_1E8], rsi
0x180092ab7  mov     [rsp+308h+var_1E0], rsi
0x180092abf  mov     [rsp+308h+var_1D8], rsi
0x180092ac7  mov     rdi, [rsp+308h+var_2C8]
0x180092acc  mov     rax, [rdi]
0x180092acf  mov     rbx, [rax+78h]
0x180092ad3  lea     rcx, [rsp+308h+var_1E8]
0x180092adb  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180092ae0  mov     [rsp+308h+var_1E0], r14
0x180092ae8  mov     [rsp+308h+var_1D8], r14
0x180092af0  lea     rdx, [rsp+308h+var_1E8]
0x180092af8  mov     rcx, rdi
0x180092afb  mov     rax, rbx
0x180092afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092b03  mov     rcx, [rsp+308h]; this
0x180092b0b  test    eax, eax
0x180092b0d  js      loc_1800933BE
0x180092b13  mov     [rsp+308h+var_278], rsi
0x180092b1b  mov     r14, rsi
0x180092b1e  mov     [rsp+308h+var_2B0], rsi
0x180092b23  mov     [rsp+308h+var_2C0], esi
0x180092b27  mov     rdi, [rsp+308h+var_2C8]
0x180092b2c  mov     rax, [rdi]
0x180092b2f  mov     rbx, [rax+60h]
0x180092b33  lea     rcx, [rsp+308h+var_278]
0x180092b3b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180092b40  lea     rdx, [rsp+308h+var_278]
0x180092b48  mov     rcx, rdi
0x180092b4b  mov     rax, rbx
0x180092b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092b53  test    eax, eax
0x180092b55  js      loc_180092CCD
0x180092b5b  mov     rcx, [rsp+308h+var_278]
0x180092b63  test    rcx, rcx
0x180092b66  jz      loc_180092CCD
0x180092b6c  mov     rax, [rcx]
0x180092b6f  lea     rdx, [rsp+308h+var_2C0]
0x180092b74  mov     rax, [rax+30h]
0x180092b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092b7d  mov     rcx, [rsp+308h]; this
0x180092b85  test    eax, eax
0x180092b87  js      loc_1800933D3
0x180092b8d  cmp     [rsp+308h+var_2C0], esi
0x180092b91  jbe     loc_180092CCD
0x180092b97  mov     ecx, 18h; Size
0x180092b9c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180092ba1  mov     r14, rax
0x180092ba4  mov     [rax], rsi
0x180092ba7  mov     [rax+8], rsi
0x180092bab  mov     [rax+10h], rsi
0x180092baf  mov     [rsp+308h+var_2A8], rsi
0x180092bb4  mov     [rsp+308h+var_2B0], rax
0x180092bb9  lea     rcx, [rsp+308h+var_2A8]
0x180092bbe  call    ??1?$unique_ptr@V?$vector@U_WPN_NOTIFICATION_METADATA_PAIR@@V?$allocator@U_WPN_NOTIFICATION_METADATA_PAIR@@@std@@@std@@U?$default_delete@V?$vector@U_WPN_NOTIFICATION_METADATA_PAIR@@V?$allocator@U_WPN_NOTIFICATION_METADATA_PAIR@@@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::vector<_WPN_NOTIFICATION_METADATA_PAIR>>::~unique_ptr<std::vector<_WPN_NOTIFICATION_METADATA_PAIR>>(void)
  ... truncated ...
```
