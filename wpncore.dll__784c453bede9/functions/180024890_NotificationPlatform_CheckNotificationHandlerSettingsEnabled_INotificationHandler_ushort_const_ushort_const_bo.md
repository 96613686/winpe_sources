# NotificationPlatform::CheckNotificationHandlerSettingsEnabled(INotificationHandler *,ushort const *,ushort const *,bool,NOTIFICATION_POLICY_REASON *,PolicyLevel *)

- ea: `0x180024890`
- end: `0x1800254f0`
- name: `?CheckNotificationHandlerSettingsEnabled@NotificationPlatform@@QEAAJPEAUINotificationHandler@@PEBG1_NPEAW4NOTIFICATION_POLICY_REASON@@PEAW4PolicyLevel@@@Z`
- size: `3168`
- prototype: `int(NotificationPlatform *__hidden this, struct INotificationHandler *, const unsigned __int16 *, const unsigned __int16 *, bool, enum NOTIFICATION_POLICY_REASON *, enum PolicyLevel *)`
- caller_count: `4`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180054a78`
- `0x180056420`
- `0x18005f240`
- `0x18007ed94`

## callees

- `0x180004e38`
- `0x18000e090`
- `0x180011618`
- `0x180023cc4`
- `0x180024890`
- `0x1800254f8`
- `0x180025588`
- `0x18002ee38`
- `0x180080828`
- `0x1800efbfc`
- `0x1801071a4`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002497e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024c38`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024c97`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024cf6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002497e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024c38`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024c97`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024cf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024b03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024b1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024baa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024bc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024d9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024b03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024b1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024baa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024bc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024d9e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NotificationPlatform::CheckNotificationHandlerSettingsEnabled(
        CtaManager **this,
        struct INotificationHandler *a2,
        WpnDatabaseHelpers *a3,
        const unsigned __int16 *a4,
        bool a5,
        enum NOTIFICATION_POLICY_REASON *a6,
        enum PolicyLevel *a7)
{
  int v7; // r15d
  char v10; // r13
  enum NOTIFICATION_POLICY_REASON *v11; // rdi
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  char v15; // si
  const WCHAR *v16; // rbx
  const WCHAR *v17; // r8
  __int64 v18; // rdx
  const WCHAR *v19; // rcx
  __int64 (__fastcall *v20)(struct INotificationHandler *, __int64 *); // rbx
  int v21; // eax
  __int64 v22; // rdx
  bool v23; // r15
  __int64 v24; // rdx
  unsigned int v25; // esi
  CtaManager **v26; // r15
  int v27; // eax
  __int64 v28; // rcx
  int v30; // eax
  __int64 v31; // rcx
  const WCHAR *v32; // r8
  __int64 v33; // rdx
  const WCHAR *v34; // rcx
  const WCHAR *v35; // r8
  __int64 v36; // rdx
  const WCHAR *v37; // rcx
  const WCHAR *v38; // r8
  __int64 v39; // rdx
  __int64 v40; // rcx
  int v41; // eax
  __int64 v42; // rdx
  int v43; // eax
  int v44; // eax
  int v45; // eax
  __int64 v46; // rcx
  int v47; // eax
  __int64 v48; // rcx
  int v49; // eax
  __int64 v50; // rcx
  int v51; // eax
  int v52; // eax
  __int64 v53; // rcx
  __int64 v54; // rcx
  int v55; // eax
  int v56; // eax
  __int64 v57; // rcx
  int v58; // eax
  int v59; // eax
  int v60; // eax
  const unsigned __int16 *v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // rcx
  __int64 v64; // rcx
  __int64 v65; // rcx
  unsigned __int64 v66; // r9
  int v67; // eax
  int v68; // [rsp+28h] [rbp-71h]
  int v69; // [rsp+28h] [rbp-71h]
  __int64 v70; // [rsp+38h] [rbp-61h] BYREF
  LPCWCH lpString1; // [rsp+40h] [rbp-59h] BYREF
  __int64 v72; // [rsp+48h] [rbp-51h]
  __int64 v73; // [rsp+50h] [rbp-49h]
  int v74; // [rsp+58h] [rbp-41h] BYREF
  LPVOID pv[3]; // [rsp+60h] [rbp-39h] BYREF
  int v76; // [rsp+78h] [rbp-21h] BYREF
  int v77; // [rsp+7Ch] [rbp-1Dh] BYREF
  int v78; // [rsp+80h] [rbp-19h] BYREF
  int v79; // [rsp+84h] [rbp-15h] BYREF
  int v80; // [rsp+88h] [rbp-11h] BYREF
  int v81; // [rsp+8Ch] [rbp-Dh] BYREF
  int v82; // [rsp+90h] [rbp-9h] BYREF
  int v83; // [rsp+94h] [rbp-5h] BYREF
  int v84; // [rsp+98h] [rbp-1h] BYREF
  int v85; // [rsp+9Ch] [rbp+3h] BYREF
  int v86; // [rsp+A0h] [rbp+7h] BYREF
  _DWORD v87[13]; // [rsp+A4h] [rbp+Bh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+47h]
  char v90; // [rsp+F0h] [rbp+57h] BYREF
  WpnDatabaseHelpers *v91; // [rsp+F8h] [rbp+5Fh]

  v91 = a3;
  v10 = 0;
  v11 = a6;
  *(_DWORD *)a6 = 0;
  pv[0] = 0;
  pv[1] = (LPVOID)-1LL;
  pv[2] = (LPVOID)-1LL;
  v12 = (*(__int64 (__fastcall **)(struct INotificationHandler *, LPVOID *))(*(_QWORD *)a2 + 24LL))(a2, pv);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x541,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
      (const char *)(unsigned int)v12,
      v68);
LABEL_43:
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    return v13;
  }
  v74 = 0;
  lpString1 = 0;
  v72 = -1;
  v73 = -1;
  v14 = (*(__int64 (__fastcall **)(struct INotificationHandler *, LPCWCH *))(*(_QWORD *)a2 + 48LL))(a2, &lpString1);
  v13 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x54A,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
      (const char *)(unsigned int)v14,
      v68);
LABEL_174:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pv);
    return v13;
  }
  v15 = 0;
  LOBYTE(v7) = 0;
  LODWORD(a6) = v7;
  v16 = &word_180124798;
  v17 = &word_180124798;
  if ( L"app:immersive" )
    v17 = L"app:immersive";
  v18 = v72;
  if ( v72 == -1 )
  {
    if ( lpString1 )
    {
      do
        ++v18;
      while ( lpString1[v18] );
    }
    else
    {
      LODWORD(v18) = 0;
    }
  }
  v19 = &word_180124798;
  if ( lpString1 )
    v19 = lpString1;
  if ( CompareStringOrdinal(v19, v18, v17, -(L"app:immersive" != 0), 0) == 2 )
  {
    v10 = 1;
  }
  else
  {
    v32 = &word_180124798;
    if ( L"app:phone" )
      v32 = L"app:phone";
    v33 = v72;
    if ( v72 == -1 )
    {
      if ( lpString1 )
      {
        do
          ++v33;
        while ( lpString1[v33] );
      }
      else
      {
        LODWORD(v33) = 0;
      }
    }
    v34 = &word_180124798;
    if ( lpString1 )
      v34 = lpString1;
    if ( CompareStringOrdinal(v34, v33, v32, -(L"app:phone" != 0), 0) != 2 )
    {
      v35 = &word_180124798;
      if ( L"app:system" )
        v35 = L"app:system";
      v36 = v72;
      if ( v72 == -1 )
      {
        if ( lpString1 )
        {
          do
            ++v36;
          while ( lpString1[v36] );
        }
        else
        {
          LODWORD(v36) = 0;
        }
      }
      v37 = &word_180124798;
      if ( lpString1 )
        v37 = lpString1;
      if ( CompareStringOrdinal(v37, v36, v35, -(L"app:system" != 0), 0) == 2 )
      {
        v15 = 1;
      }
      else
      {
        v38 = &word_180124798;
        if ( L"app:desktop" )
          v38 = L"app:desktop";
        v39 = v72;
        if ( v72 == -1 )
        {
          if ( lpString1 )
          {
            do
              ++v39;
            while ( lpString1[v39] );
          }
          else
          {
            LODWORD(v39) = 0;
          }
        }
        if ( lpString1 )
          v16 = lpString1;
        LODWORD(a6) = CompareStringOrdinal(v16, v39, v38, -(L"app:desktop" != 0), 0) == 2;
      }
    }
  }
  v70 = 0;
  v20 = *(__int64 (__fastcall **)(struct INotificationHandler *, __int64 *))(*(_QWORD *)a2 + 32LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v70);
  v21 = v20(a2, &v70);
  v13 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55E,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
      (const char *)(unsigned int)v21,
      v69);
    v40 = v70;
    if ( v70 )
    {
      v70 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    }
    if ( lpString1 )
    {
      CoTaskMemFree((LPVOID)lpString1);
      lpString1 = 0;
    }
    v72 = 0;
    v73 = 0;
    goto LABEL_43;
  }
  v23 = a5;
  if ( !v15 && !(_BYTE)a6 )
    goto LABEL_15;
  v76 = 0;
  v49 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v70 + 32LL))(v70, L"s:stopCloud", &v76);
  v13 = v49;
  if ( v49 < 0 )
  {
    v66 = (unsigned int)v49;
    v42 = 1380;
    goto LABEL_172;
  }
  v13 = 0;
  if ( v23 && v76 == 1 )
  {
    *(_DWORD *)v11 = 1;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x569,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
      (const char *)0x803E020BLL,
      v69);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v70);
    v13 = -2143419893;
    goto LABEL_174;
  }
  if ( v15 && (wcscmp_0(a4, L"toast") || !CanAppShowInToastSettings((const unsigned __int16 *)pv[0])) )
    goto LABEL_173;
LABEL_15:
  LOBYTE(v22) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_40670583>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_40670583>::GetImpl'::`2'::impl,
    v22);
  v25 = 3;
  if ( !v23 )
  {
    v26 = this;
    goto LABEL_17;
  }
  LOBYTE(v24) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_40670583>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_40670583>::GetImpl'::`2'::impl,
    v24);
  v26 = this;
  if ( v10 )
  {
    v30 = CtaManager::ValidateCtaPolicy(this[46], (const unsigned __int16 *)pv[0]);
    v13 = v30;
    if ( v30 == -2143419893 )
    {
      *(_DWORD *)v11 = 9;
LABEL_38:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x590,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
        (const char *)(unsigned int)v30,
        v69);
      v31 = v70;
      if ( v70 )
      {
        v70 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      }
      goto LABEL_40;
    }
    if ( v30 < 0 )
      goto LABEL_38;
  }
  v77 = 0;
  v58 = (*(__int64 (__fastcall **)(CtaManager *, __int64, int *, int *))(*(_QWORD *)this[29] + 8LL))(
          this[29],
          3,
          &v77,
          &v74);
  v13 = v58;
  if ( v58 < 0 )
  {
    v66 = (unsigned int)v58;
    v42 = 1430;
    goto LABEL_172;
  }
  if ( !v77 )
  {
    *(_DWORD *)v11 = 2;
    v13 = -2143420151;
    v42 = 1434;
    goto LABEL_171;
  }
  LOBYTE(a6) = 0;
  v59 = (*(__int64 (__fastcall **)(CtaManager *, enum NOTIFICATION_POLICY_REASON **))(*(_QWORD *)this[29] + 216LL))(
          this[29],
          &a6);
  v13 = v59;
  if ( v59 < 0 )
  {
    v66 = (unsigned int)v59;
    v42 = 1439;
    goto LABEL_172;
  }
  if ( !(_BYTE)a6 )
  {
    *(_DWORD *)v11 = 3;
    v13 = -2143420151;
    v42 = 1443;
    goto LABEL_171;
  }
  v78 = 1;
  v60 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v70 + 32LL))(v70, L"c:internet", &v78);
  v13 = v60;
  if ( v60 < 0 )
  {
    v66 = (unsigned int)v60;
    v42 = 1447;
    goto LABEL_172;
  }
  if ( !v78 && !WpnDatabaseHelpers::IsPackageInternetCapable(v91, v61) )
  {
    *(_DWORD *)v11 = 4;
    v13 = -2143420144;
    v42 = 1451;
    goto LABEL_171;
  }
LABEL_17:
  if ( wcscmp_0(a4, L"raw") )
  {
    if ( !wcscmp_0(a4, L"toast") )
    {
      v25 = 2;
    }
    else if ( !wcscmp_0(a4, L"tile") )
    {
      v25 = 0;
    }
    else
    {
      if ( wcscmp_0(a4, L"badge") )
      {
        v13 = -2147024809;
        v42 = 1475;
        goto LABEL_171;
      }
      v25 = 1;
    }
  }
  v79 = 0;
  v27 = (*(__int64 (__fastcall **)(CtaManager *, _QWORD, int *, int *))(*(_QWORD *)v26[29] + 8LL))(
          v26[29],
          v25,
          &v79,
          &v74);
  v13 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C7,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
      (const char *)(unsigned int)v27,
      v69);
    v64 = v70;
    if ( v70 )
    {
      v70 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
    }
    goto LABEL_40;
  }
  if ( !v79 )
  {
    *(_DWORD *)v11 = 5;
    v13 = -2143420140;
    v42 = 1484;
    goto LABEL_171;
  }
  if ( !wcscmp_0(a4, L"tile") || !wcscmp_0(a4, L"badge") )
  {
    v90 = 0;
    v41 = (*(__int64 (__fastcall **)(CtaManager *, char *))(*(_QWORD *)v26[29] + 224LL))(v26[29], &v90);
    v13 = v41;
    if ( v41 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5D3,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
        (const char *)(unsigned int)v41,
        v69);
      v46 = v70;
      if ( v70 )
      {
        v70 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
      }
      goto LABEL_40;
    }
    if ( !v90 )
    {
      *(_DWORD *)v11 = 6;
      v13 = -2143420140;
      v42 = 1495;
LABEL_171:
      v66 = v13;
      goto LABEL_172;
    }
  }
  if ( !wcscmp_0(a4, L"raw") )
  {
    v80 = 0;
    v47 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v70 + 32LL))(v70, L"c:cloud", &v80);
    v13 = v47;
    if ( v47 >= 0 )
    {
      if ( v80 )
        goto LABEL_26;
      *(_DWORD *)v11 = 8;
      v13 = -2143420142;
      v42 = 1507;
      goto LABEL_171;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5DF,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
      (const char *)(unsigned int)v47,
      v69);
    v48 = v70;
    if ( v70 )
    {
      v70 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    }
LABEL_40:
    if ( lpString1 )
    {
      CoTaskMemFree((LPVOID)lpString1);
      lpString1 = 0;
    }
    v72 = 0;
    v73 = 0;
    goto LABEL_43;
  }
  if ( !wcscmp_0(a4, L"toast") )
  {
    v43 = NotificationPlatform::RecoverToastSettingsIfBroken((NotificationPlatform *)v26, a2);
    if ( v43 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5E9,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
        (const char *)(unsigned int)v43,
        v69);
    v81 = 0;
    v44 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v70 + 32LL))(v70, L"s:toast", &v81);
    v13 = v44;
    if ( v44 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5EC,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
        (const char *)(unsigned int)v44,
        v69);
      v50 = v70;
      if ( v70 )
      {
        v70 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      }
    }
    else if ( v81 )
    {
      v82 = 0;
      v45 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v70 + 32LL))(v70, L"c:toast", &v82);
      v13 = v45;
      if ( v45 >= 0 )
      {
        if ( v82 )
          goto LABEL_26;
        *(_DWORD *)v11 = 11;
        v13 = -2143420142;
        v42 = 1528;
        goto LABEL_171;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F4,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
        (const char *)(unsigned int)v45,
        v69);
      v62 = v70;
      if ( v70 )
      {
        v70 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
      }
    }
    else
    {
      *(_DWORD *)v11 = 10;
      v13 = -2143420143;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F0,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
        (const char *)0x803E0111LL,
        v69);
      v54 = v70;
      if ( v70 )
      {
        v70 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      }
    }
    goto LABEL_40;
  }
  if ( !wcscmp_0(a4, L"tile") )
  {
    v83 = 0;
    v84 = 0;
    v51 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v70 + 32LL))(v70, L"s:tile", &v83);
    v13 = v51;
    if ( v51 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5FF,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
        (const char *)(unsigned int)v51,
        v69);
      v63 = v70;
      if ( v70 )
      {
        v70 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
      }
      goto LABEL_40;
    }
    v52 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v70 + 32LL))(
            v70,
            L"s:lock:tile",
            &v84);
    v13 = v52;
    if ( v52 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x600,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
        (const char *)(unsigned int)v52,
        v69);
      v53 = v70;
      if ( v70 )
      {
        v70 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      }
      goto LABEL_40;
    }
    if ( !v83 && !v84 )
    {
      *(_DWORD *)v11 = 12;
      v42 = 1540;
      goto LABEL_139;
    }
    v85 = 0;
    v67 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v70 + 32LL))(v70, L"c:tile", &v85);
    v13 = v67;
    if ( v67 >= 0 )
    {
      if ( v85 )
        goto LABEL_26;
      *(_DWORD *)v11 = 13;
      v13 = -2143420142;
      v42 = 1548;
      goto LABEL_171;
    }
    v66 = (unsigned int)v67;
    v42 = 1544;
LABEL_172:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v42,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
      (const char *)v66,
      v69);
LABEL_173:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v70);
    goto LABEL_174;
  }
  if ( !wcscmp_0(a4, L"badge") )
  {
    v86 = 0;
    v87[0] = 0;
    v55 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v70 + 32LL))(v70, L"s:badge", &v86);
    v13 = v55;
    if ( v55 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x613,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
        (const char *)(unsigned int)v55,
        v69);
      v65 = v70;
      if ( v70 )
      {
        v70 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
      }
      goto LABEL_40;
    }
    v56 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _DWORD *))(*(_QWORD *)v70 + 32LL))(
            v70,
            L"s:lock:badge",
            v87);
    v13 = v56;
    if ( v56 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x614,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
        (const char *)(unsigned int)v56,
        v69);
      v57 = v70;
      if ( v70 )
      {
        v70 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
      }
      goto LABEL_40;
    }
    if ( v86 || v87[0] )
      goto LABEL_26;
    *(_DWORD *)v11 = 14;
    v42 = 1560;
LABEL_139:
    v13 = -2143420143;
    goto LABEL_171;
  }
LABEL_26:
  if ( a7 )
    *(_DWORD *)a7 = v74;
  v28 = v70;
  if ( v70 )
  {
    v70 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  if ( lpString1 )
  {
    CoTaskMemFree((LPVOID)lpString1);
    lpString1 = 0;
  }
  v72 = 0;
  v73 = 0;
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  return 0;
}

```

## disassembly

```asm
0x180024890  mov     rax, rsp
0x180024893  mov     [rax+20h], rbx
0x180024897  mov     [rax+18h], r8
0x18002489b  mov     [rax+8], rcx
0x18002489f  push    rbp
0x1800248a0  push    rsi
0x1800248a1  push    rdi
0x1800248a2  push    r12
0x1800248a4  push    r13
0x1800248a6  push    r14
0x1800248a8  push    r15
0x1800248aa  lea     rbp, [rax-47h]
0x1800248ae  sub     rsp, 0A0h
0x1800248b5  mov     r14, r9
0x1800248b8  mov     r12, rdx
0x1800248bb  xor     r13d, r13d
0x1800248be  mov     rdi, [rbp+3Fh+arg_28]
0x1800248c2  mov     [rdi], r13d
0x1800248c5  mov     [rbp+3Fh+pv], r13
0x1800248c9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800248cd  mov     [rbp+3Fh+var_70], rsi
0x1800248d1  mov     [rbp+3Fh+var_68], rsi
0x1800248d5  mov     rax, [rdx]
0x1800248d8  lea     rdx, [rbp+3Fh+pv]
0x1800248dc  mov     rcx, r12
0x1800248df  mov     rax, [rax+18h]
0x1800248e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248e8  mov     ebx, eax
0x1800248ea  test    eax, eax
0x1800248ec  js      loc_18002532F
0x1800248f2  mov     [rbp+3Fh+var_80], r13d
0x1800248f6  mov     [rbp+3Fh+lpString1], r13
0x1800248fa  mov     [rbp+3Fh+var_90], rsi
0x1800248fe  mov     [rbp+3Fh+var_88], rsi
0x180024902  mov     rax, [r12]
0x180024906  lea     rdx, [rbp+3Fh+lpString1]
0x18002490a  mov     rcx, r12
0x18002490d  mov     rax, [rax+30h]
0x180024911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024916  mov     ebx, eax
0x180024918  test    eax, eax
0x18002491a  js      loc_18002536C
0x180024920  mov     sil, r13b
0x180024923  mov     r15b, r13b
0x180024926  mov     dword ptr [rbp+3Fh+arg_28], r15d
0x18002492a  mov     rcx, cs:lpString2
0x180024931  mov     rax, rcx
0x180024934  neg     rax
0x180024937  sbb     r9d, r9d; cchCount2
0x18002493a  lea     rbx, word_180124798
0x180024941  mov     r8, rbx
0x180024944  test    rcx, rcx
0x180024947  cmovnz  r8, rcx; lpString2
0x18002494b  mov     rdx, [rbp+3Fh+var_90]
0x18002494f  mov     rax, [rbp+3Fh+lpString1]
0x180024953  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180024957  jnz     short loc_18002496F
0x180024959  test    rax, rax
0x18002495c  jz      loc_18002534C
0x180024962  or      rdx, rdx
0x180024965  inc     rdx; cchCount1
0x180024968  cmp     [rax+rdx*2], r13w
0x18002496d  jnz     short loc_180024965
0x18002496f  mov     rcx, rbx
0x180024972  test    rax, rax
0x180024975  cmovnz  rcx, rax; lpString1
0x180024979  mov     [rsp+20h], r13d; int
0x18002497e  call    cs:__imp_CompareStringOrdinal
0x180024984  cmp     eax, 2
0x180024987  jnz     loc_180024BE8
0x18002498d  mov     r13b, 1
0x180024990  xor     r15d, r15d
0x180024993  mov     [rbp+3Fh+var_A0], r15
0x180024997  mov     rax, [r12]
0x18002499b  mov     rbx, [rax+20h]
0x18002499f  lea     rcx, [rbp+3Fh+var_A0]
0x1800249a3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800249a8  lea     rdx, [rbp+3Fh+var_A0]
0x1800249ac  mov     rcx, r12
0x1800249af  mov     rax, rbx
0x1800249b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249b7  mov     ebx, eax
0x1800249b9  test    eax, eax
0x1800249bb  js      loc_180024D62
0x1800249c1  mov     r15b, [rbp+3Fh+arg_20]
0x1800249c5  xor     ebx, ebx
0x1800249c7  test    sil, sil
0x1800249ca  jnz     loc_180024F37
0x1800249d0  cmp     byte ptr [rbp+3Fh+arg_28], bl
0x1800249d3  jnz     loc_180024F37
0x1800249d9  mov     dl, 1
0x1800249db  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_40670583@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_40670583@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_40670583> `wil::Feature<__WilFeatureTraits_Feature_40670583>::GetImpl(void)'::`2'::impl
0x1800249e2  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_40670583@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_40670583>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800249e7  mov     esi, 3
0x1800249ec  test    r15b, r15b
0x1800249ef  jnz     loc_180024B2B
0x1800249f5  mov     r15, [rbp+3Fh+arg_0]
0x1800249f9  xor     r13d, r13d
0x1800249fc  lea     rdx, aRaw; "raw"
0x180024a03  mov     rcx, r14; String1
0x180024a06  call    wcscmp_0
0x180024a0b  test    eax, eax
0x180024a0d  jnz     loc_180024D15
0x180024a13  mov     [rbp+3Fh+var_54], r13d
0x180024a17  mov     rcx, [r15+0E8h]
0x180024a1e  mov     rax, [rcx]
0x180024a21  lea     r9, [rbp+3Fh+var_80]
0x180024a25  lea     r8, [rbp+3Fh+var_54]
0x180024a29  mov     edx, esi
0x180024a2b  mov     rax, [rax+8]
0x180024a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a34  mov     ebx, eax
0x180024a36  test    eax, eax
0x180024a38  js      loc_1800252BF
0x180024a3e  cmp     [rbp+3Fh+var_54], r13d
0x180024a42  jz      loc_180025437
0x180024a48  lea     rdx, aTile; "tile"
0x180024a4f  mov     rcx, r14; String1
0x180024a52  call    wcscmp_0
0x180024a57  test    eax, eax
0x180024a59  jz      loc_180024DB5
0x180024a5f  lea     rdx, aBadge; "badge"
0x180024a66  mov     rcx, r14; String1
0x180024a69  call    wcscmp_0
0x180024a6e  test    eax, eax
0x180024a70  jz      loc_180024DB5
0x180024a76  lea     rdx, aRaw; "raw"
0x180024a7d  mov     rcx, r14; String1
0x180024a80  call    wcscmp_0
0x180024a85  test    eax, eax
0x180024a87  jz      loc_180024ED6
0x180024a8d  lea     rdx, aToast_0; "toast"
0x180024a94  mov     rcx, r14; String1
0x180024a97  call    wcscmp_0
0x180024a9c  test    eax, eax
0x180024a9e  jz      loc_180024DFC
0x180024aa4  lea     rdx, aTile; "tile"
0x180024aab  mov     rcx, r14; String1
0x180024aae  call    wcscmp_0
0x180024ab3  test    eax, eax
0x180024ab5  jz      loc_180024FE2
0x180024abb  lea     rdx, aBadge; "badge"
0x180024ac2  mov     rcx, r14; String1
0x180024ac5  call    wcscmp_0
0x180024aca  test    eax, eax
0x180024acc  jz      loc_1800250AF
0x180024ad2  mov     rcx, [rbp+3Fh+arg_30]
0x180024ad6  test    rcx, rcx
0x180024ad9  jz      short loc_180024AE0
0x180024adb  mov     eax, [rbp+3Fh+var_80]
0x180024ade  mov     [rcx], eax
0x180024ae0  mov     rcx, [rbp+3Fh+var_A0]
0x180024ae4  test    rcx, rcx
0x180024ae7  jz      short loc_180024AFA
0x180024ae9  mov     [rbp+3Fh+var_A0], r13
0x180024aed  mov     rax, [rcx]
0x180024af0  mov     rax, [rax+10h]
0x180024af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024af9  nop
0x180024afa  mov     rcx, [rbp+3Fh+lpString1]; pv
0x180024afe  test    rcx, rcx
0x180024b01  jz      short loc_180024B0D
0x180024b03  call    cs:__imp_CoTaskMemFree
0x180024b09  mov     [rbp+3Fh+lpString1], r13
0x180024b0d  mov     [rbp+3Fh+var_90], r13
0x180024b11  mov     [rbp+3Fh+var_88], r13
0x180024b15  mov     rcx, [rbp+3Fh+pv]; pv
0x180024b19  test    rcx, rcx
0x180024b1c  jz      short loc_180024B24
0x180024b1e  call    cs:__imp_CoTaskMemFree
0x180024b24  xor     eax, eax
0x180024b26  jmp     loc_180024BCD
0x180024b2b  mov     dl, 1
0x180024b2d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_40670583@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_40670583@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_40670583> `wil::Feature<__WilFeatureTraits_Feature_40670583>::GetImpl(void)'::`2'::impl
0x180024b34  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_40670583@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_40670583>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180024b39  mov     r15, [rbp+3Fh+arg_0]
0x180024b3d  test    r13b, r13b
0x180024b40  jz      loc_180025139
0x180024b46  mov     rdx, [rbp+3Fh+pv]; unsigned __int16 *
0x180024b4a  mov     rcx, [r15+170h]; this
0x180024b51  call    ?ValidateCtaPolicy@CtaManager@@QEAAJPEBG@Z; CtaManager::ValidateCtaPolicy(ushort const *)
0x180024b56  mov     ebx, eax
0x180024b58  xor     r13d, r13d
0x180024b5b  cmp     eax, 803E020Bh
0x180024b60  jz      loc_1800253DF
0x180024b66  test    eax, eax
0x180024b68  jns     loc_18002513C
0x180024b6e  mov     rcx, [rbp+47h]; this
0x180024b72  mov     r9d, ebx; char *
0x180024b75  lea     r8, aOnecoreuapBase_161; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180024b7c  mov     edx, 590h; void *
0x180024b81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024b86  nop
0x180024b87  mov     rcx, [rbp+3Fh+var_A0]
0x180024b8b  test    rcx, rcx
0x180024b8e  jz      short loc_180024BA1
0x180024b90  mov     [rbp+3Fh+var_A0], r13
0x180024b94  mov     rax, [rcx]
0x180024b97  mov     rax, [rax+10h]
0x180024b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ba0  nop
0x180024ba1  mov     rcx, [rbp+3Fh+lpString1]; pv
0x180024ba5  test    rcx, rcx
0x180024ba8  jz      short loc_180024BB4
0x180024baa  call    cs:__imp_CoTaskMemFree
0x180024bb0  mov     [rbp+3Fh+lpString1], r13
0x180024bb4  mov     [rbp+3Fh+var_90], r13
0x180024bb8  mov     [rbp+3Fh+var_88], r13
0x180024bbc  mov     rcx, [rbp+3Fh+pv]; pv
0x180024bc0  test    rcx, rcx
0x180024bc3  jz      short loc_180024BCB
0x180024bc5  call    cs:__imp_CoTaskMemFree
0x180024bcb  mov     eax, ebx
0x180024bcd  mov     rbx, [rsp+0D0h+arg_18]
0x180024bd5  add     rsp, 0A0h
0x180024bdc  pop     r15
0x180024bde  pop     r14
0x180024be0  pop     r13
0x180024be2  pop     r12
0x180024be4  pop     rdi
0x180024be5  pop     rsi
0x180024be6  pop     rbp
0x180024be7  retn
0x180024be8  mov     rcx, cs:off_18011DEA8; "app:phone"
0x180024bef  mov     rax, rcx
0x180024bf2  neg     rax
0x180024bf5  sbb     r9d, r9d; cchCount2
0x180024bf8  mov     r8, rbx
0x180024bfb  xor     r10d, r10d
0x180024bfe  test    rcx, rcx
0x180024c01  cmovnz  r8, rcx; lpString2
0x180024c05  mov     rdx, [rbp+3Fh+var_90]
0x180024c09  mov     rax, [rbp+3Fh+lpString1]
0x180024c0d  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180024c11  jnz     short loc_180024C29
0x180024c13  test    rax, rax
0x180024c16  jz      loc_180025354
0x180024c1c  or      rdx, rdx
0x180024c1f  inc     rdx; cchCount1
0x180024c22  cmp     [rax+rdx*2], r10w
0x180024c27  jnz     short loc_180024C1F
0x180024c29  mov     rcx, rbx
0x180024c2c  test    rax, rax
0x180024c2f  cmovnz  rcx, rax; lpString1
0x180024c33  mov     [rsp+20h], r10d; bIgnoreCase
0x180024c38  call    cs:__imp_CompareStringOrdinal
0x180024c3e  cmp     eax, 2
0x180024c41  jz      loc_180024990
0x180024c47  mov     rcx, cs:off_18011DEB0; "app:system"
0x180024c4e  mov     rax, rcx
0x180024c51  neg     rax
0x180024c54  sbb     r9d, r9d; cchCount2
0x180024c57  mov     r8, rbx
0x180024c5a  xor     r10d, r10d
0x180024c5d  test    rcx, rcx
0x180024c60  cmovnz  r8, rcx; lpString2
0x180024c64  mov     rdx, [rbp+3Fh+var_90]
0x180024c68  mov     rax, [rbp+3Fh+lpString1]
0x180024c6c  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180024c70  jnz     short loc_180024C88
0x180024c72  test    rax, rax
0x180024c75  jz      loc_18002535C
0x180024c7b  or      rdx, rdx
0x180024c7e  inc     rdx; cchCount1
0x180024c81  cmp     [rax+rdx*2], r10w
0x180024c86  jnz     short loc_180024C7E
0x180024c88  mov     rcx, rbx
0x180024c8b  test    rax, rax
0x180024c8e  cmovnz  rcx, rax; lpString1
0x180024c92  mov     [rsp+20h], r10d; bIgnoreCase
0x180024c97  call    cs:__imp_CompareStringOrdinal
0x180024c9d  cmp     eax, 2
0x180024ca0  jz      loc_180025389
0x180024ca6  mov     rcx, cs:off_18011DE80; "app:desktop"
0x180024cad  mov     rax, rcx
0x180024cb0  neg     rax
0x180024cb3  sbb     r9d, r9d; cchCount2
0x180024cb6  mov     r8, rbx
0x180024cb9  xor     r10d, r10d
0x180024cbc  test    rcx, rcx
0x180024cbf  cmovnz  r8, rcx; lpString2
0x180024cc3  mov     rdx, [rbp+3Fh+var_90]
0x180024cc7  mov     rax, [rbp+3Fh+lpString1]
0x180024ccb  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180024ccf  jnz     short loc_180024CE7
0x180024cd1  test    rax, rax
0x180024cd4  jz      loc_180025364
0x180024cda  or      rdx, rdx
0x180024cdd  inc     rdx; cchCount1
0x180024ce0  cmp     [rax+rdx*2], r10w
0x180024ce5  jnz     short loc_180024CDD
0x180024ce7  test    rax, rax
0x180024cea  cmovnz  rbx, rax
0x180024cee  mov     [rsp+20h], r10d; bIgnoreCase
0x180024cf3  mov     rcx, rbx; lpString1
0x180024cf6  call    cs:__imp_CompareStringOrdinal
0x180024cfc  movzx   r15d, r15b
0x180024d00  cmp     eax, 2
0x180024d03  mov     eax, 1
0x180024d08  cmovz   r15d, eax
  ... truncated ...
```
