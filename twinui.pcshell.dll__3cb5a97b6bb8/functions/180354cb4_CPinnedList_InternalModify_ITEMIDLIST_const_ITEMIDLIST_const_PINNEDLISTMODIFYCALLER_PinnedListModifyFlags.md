# CPinnedList::InternalModify(_ITEMIDLIST const *,_ITEMIDLIST const *,PINNEDLISTMODIFYCALLER,PinnedListModifyFlags)

- ea: `0x180354cb4`
- end: `0x18035578e`
- name: `?InternalModify@CPinnedList@@IEAAJPEFBU_ITEMIDLIST@@0W4PINNEDLISTMODIFYCALLER@@W4PinnedListModifyFlags@@@Z`
- size: `2778`
- prototype: ``
- caller_count: `7`
- callee_count: `54`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1803541e0`
- `0x1803545a0`
- `0x180354890`
- `0x1805f33d4`
- `0x18067abf0`
- `0x180680180`
- `0x1806801d0`

## callees

- `0x1800134f8`
- `0x18001d664`
- `0x1800237c8`
- `0x180031c70`
- `0x180051b5c`
- `0x18005a710`
- `0x180070884`
- `0x18007b3e0`
- `0x18008a6f0`
- `0x1800c85d8`
- `0x1800e1ce4`
- `0x18012ddf4`
- `0x18014b060`
- `0x1801c8d40`
- `0x1801dfbe0`
- `0x1801fdc4c`
- `0x1802789e0`
- `0x1802be370`
- `0x1802c8218`
- `0x1802d8b84`
- `0x1802dd7d4`
- `0x1802ead90`
- `0x1802eb1f0`
- `0x1802eb5a0`
- `0x180354cb4`
- `0x18035594c`
- `0x180356360`
- `0x180356970`
- `0x180356edc`
- `0x180364c2c`
- `0x180679b78`
- `0x180679ec4`
- `0x18067a5e4`
- `0x18067a6f8`
- `0x18067aa40`
- `0x18067aa6c`
- `0x18067b1d4`
- `0x18067c254`
- `0x18067e47c`
- `0x18067efc8`
- `0x18067f98c`
- `0x18067fb80`
- `0x180680ee0`
- `0x1806810ac`
- `0x180681180`
- `0x180681e64`
- `0x180682694`
- `0x18068337c`
- `0x180683848`
- `0x1806838dc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18035562a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18035562a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180354da2`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180354da2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180354db0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180354db0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180355092`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180355092`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180354fd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180354fd2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180354ed6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180354ed6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18035524f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18035524f`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180354f5b`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1803554d8`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180354f5b`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1803554d8`
- `SHELL32!__imp_ILFree` at `0x180355560`
- `SHELL32!__imp_ILFree` at `0x1803556df`
- `SHELL32!__imp_ILFree` at `0x1803556f1`
- `SHELL32!__imp_ILFree` at `0x1803556fb`
- `SHELL32!__imp_ILFree` at `0x180355560`
- `SHELL32!__imp_ILFree` at `0x1803556df`
- `SHELL32!__imp_ILFree` at `0x1803556f1`
- `SHELL32!__imp_ILFree` at `0x1803556fb`
- `Windows.Storage!ILIsEqual` at `0x180354e73`
- `Windows.Storage!ILIsEqual` at `0x180354e73`
- `Windows.Storage!__imp_SHLogILFromFSIL` at `0x180354d47`
- `Windows.Storage!__imp_SHLogILFromFSIL` at `0x180354d6b`
- `Windows.Storage!__imp_SHLogILFromFSIL` at `0x180354d47`
- `Windows.Storage!__imp_SHLogILFromFSIL` at `0x180354d6b`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall CPinnedList::InternalModify(
        struct CPinnedList *a1,
        struct _ITEMIDLIST *a2,
        struct _ITEMIDLIST *a3,
        unsigned int a4,
        int a5)
{
  struct _ITEMIDLIST *v6; // rsi
  ITEMIDLIST *v9; // rax
  ITEMIDLIST *v10; // rax
  const WCHAR *v11; // rax
  wil::details *v12; // rcx
  HANDLE Mutex; // rbx
  int LastErrorFailHr; // edi
  __int64 v15; // rbx
  __int64 *v16; // r14
  int v17; // edi
  int TimestampFromPidl; // eax
  void *v19; // rcx
  int BackupLnk; // r14d
  unsigned int v21; // edx
  LPWSTR *v22; // rbx
  unsigned int v23; // r9d
  __int64 v24; // rax
  int v25; // r12d
  void (__fastcall *v26)(char *, LPITEMIDLIST, wchar_t **); // rbx
  const struct _ITEMIDLIST *v27; // rdx
  __int64 v28; // rdx
  const unsigned __int16 *v29; // rdx
  wchar_t *v30; // rcx
  __int64 v31; // rbx
  int ActivationFactory; // eax
  struct _FILETIME v33; // rbx
  __int64 (__fastcall *v34)(struct _FILETIME, GUID *, LPVOID *); // rdi
  int v35; // eax
  unsigned __int16 **v36; // r9
  int AumidAndAppSpecifiedTileIdFromFullyQualifiedTileIdentifier; // eax
  LPVOID v38; // rsi
  __int64 (__fastcall *v39)(LPVOID, PVOID, PVOID); // rdi
  PVOID Reserved1; // rbx
  HSTRING_HEADER *v41; // rax
  unsigned int v42; // eax
  LPWSTR *v43; // rbx
  unsigned int v44; // edx
  unsigned int v45; // r9d
  ITEMIDLIST *v46; // rax
  int appended; // eax
  PINENTRY *ItemPtr; // rax
  void (__fastcall *v49)(char *, LPITEMIDLIST, struct _ITEMIDLIST **); // rbx
  __int64 v50; // rax
  __int64 v51; // rdx
  int ppv; // [rsp+20h] [rbp-E0h]
  LPITEMIDLIST *p_pidl; // [rsp+28h] [rbp-D8h]
  bool v54; // [rsp+40h] [rbp-C0h]
  __int64 v56; // [rsp+48h] [rbp-B8h] BYREF
  struct _ITEMIDLIST *v57; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v58; // [rsp+58h] [rbp-A8h] BYREF
  struct _ITEMIDLIST *v59; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR *ppwsz; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v61[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v62; // [rsp+80h] [rbp-80h]
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-78h] BYREF
  __int64 v64; // [rsp+A0h] [rbp-60h]
  LPITEMIDLIST v65; // [rsp+A8h] [rbp-58h]
  LPITEMIDLIST v66; // [rsp+B0h] [rbp-50h]
  HSTRING_HEADER v67; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v68; // [rsp+D8h] [rbp-28h] BYREF
  LPITEMIDLIST pidl; // [rsp+F8h] [rbp-8h] BYREF
  LPVOID pv; // [rsp+100h] [rbp+0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+108h] [rbp+8h] BYREF
  struct _ITEMIDLIST *v72[2]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v73; // [rsp+120h] [rbp+20h]
  wchar_t *Str[2]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v75; // [rsp+138h] [rbp+38h]
  unsigned __int16 *v76[2]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v77; // [rsp+150h] [rbp+50h]
  HDSA hdsa[2]; // [rsp+158h] [rbp+58h] BYREF
  unsigned __int16 *v79[2]; // [rsp+168h] [rbp+68h] BYREF
  __int64 v80; // [rsp+178h] [rbp+78h]
  _BYTE v81[336]; // [rsp+180h] [rbp+80h] BYREF
  WCHAR psz[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  WCHAR Filename[264]; // [rsp+4E0h] [rbp+3E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+748h] [rbp+648h]

  v6 = a2;
  v57 = a2;
  if ( (*(unsigned int (__fastcall **)(struct CPinnedList *))(*(_QWORD *)a1 + 120LL))(a1) )
    return 2147942405LL;
  memset_0(v81, 0, sizeof(v81));
  TaskbarPinningTelemetry::PinningActivity::Start<>((TaskbarPinningTelemetry::PinningActivity *)v81);
  v65 = 0;
  v66 = 0;
  v59 = 0;
  if ( v6 )
  {
    v9 = (ITEMIDLIST *)SHLogILFromFSIL(v6);
    v65 = v9;
    if ( v9 )
      v6 = v9;
    v57 = v6;
  }
  if ( (unsigned __int64)a3 >= 0x10000 )
  {
    v10 = (ITEMIDLIST *)SHLogILFromFSIL(a3);
    v66 = v10;
    if ( v10 )
      a3 = v10;
  }
  v58 = 0;
  v11 = (const WCHAR *)(*(__int64 (__fastcall **)(struct CPinnedList *))(*(_QWORD *)a1 + 208LL))(a1);
  Mutex = CreateMutexExW(0, v11, 0, 0x1F0001u);
  if ( Mutex )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &v58,
      Mutex);
    LastErrorFailHr = 0;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v12);
  }
  v15 = 0;
  v56 = 0;
  if ( LastErrorFailHr >= 0 )
  {
    v16 = (__int64 *)_acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
                       &v58,
                       &SystemTimeAsFileTime);
    if ( &v56 != v16 )
    {
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        &v56,
        *v16);
      *v16 = 0;
      v15 = v56;
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&SystemTimeAsFileTime);
    if ( !v15 )
      LastErrorFailHr = -2147019873;
  }
  *(_OWORD *)hdsa = 0;
  if ( LastErrorFailHr >= 0 && (int)CPinList::Load((CPinList *)hdsa, a1) >= 0 )
  {
    pidl = 0;
    v17 = 1;
    if ( !v6 )
    {
      if ( a3 )
      {
        BackupLnk = (*(__int64 (__fastcall **)(struct CPinnedList *, WCHAR *, __int64))(*(_QWORD *)a1 + 104LL))(
                      a1,
                      psz,
                      260);
        if ( BackupLnk >= 0 )
        {
          v43 = (LPWSTR *)operator new(8u);
          ppwsz = v43;
          *v43 = 0;
          BackupLnk = SHStrDupW(psz, v43);
          if ( BackupLnk >= 0 )
          {
            BackupLnk = CBackupLocationManager::CreateBackupLnk((CBackupLocationManager *)v43, a3, &pidl, v45);
            if ( BackupLnk >= 0 )
            {
              LODWORD(pv) = 0;
              GetPinSourceForPinnedItem(a3, (enum TaskbarPinningSource *)&pv);
              BackupLnk = SetPinSourceForPinnedItem(pidl, &pidl);
              if ( BackupLnk >= 0 )
              {
                SystemTimeAsFileTime = 0;
                BackupLnk = SetPinTimeForPinnedItem(pidl, 0, (struct _ITEMIDLIST **)&SystemTimeAsFileTime);
                ILFree(pidl);
                v46 = (ITEMIDLIST *)SystemTimeAsFileTime;
                SystemTimeAsFileTime = 0;
                pidl = v46;
                CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&SystemTimeAsFileTime);
                if ( BackupLnk >= 0 )
                {
                  BackupLnk = CacheAppIDInIDList(pidl);
                  if ( BackupLnk >= 0 )
                  {
                    appended = CPinList::AppendPidl((CPinList *)hdsa, a1, pidl);
                    if ( appended < 0 )
                    {
                      BackupLnk = -2147024882;
                    }
                    else
                    {
                      ItemPtr = (PINENTRY *)DSA_GetItemPtr(hdsa[0], appended);
                      PINENTRY::UpdateShellLink(ItemPtr);
                    }
                    if ( BackupLnk >= 0 )
                    {
                      v72[0] = 0;
                      v72[1] = 0;
                      v73 = 0;
                      v49 = *(void (__fastcall **)(char *, LPITEMIDLIST, struct _ITEMIDLIST **))(*((_QWORD *)a1 + 2)
                                                                                               + 88LL);
                      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v72);
                      v72[1] = (struct _ITEMIDLIST *)-1LL;
                      v73 = -1;
                      v49((char *)a1 + 16, pidl, v72);
                      if ( GetModuleFileNameW(0, Filename, 0x104u) )
                      {
                        v57 = 0;
                        v50 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v57);
                        ILGetHiddenStringAllocW(pidl, 3203334174LL, v50);
                        TaskbarPinningTelemetry::PinningActivity::PinnedListAdded(v81, v72[0], Filename, a4);
                        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v57);
                      }
                      BackupLnk = CPinList::Save((CPinList *)hdsa, a1);
                      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v72);
                      v43 = ppwsz;
                      v17 = 1;
                    }
                  }
                }
              }
            }
          }
          CBackupLocationManager::`scalar deleting destructor'((CBackupLocationManager *)v43, v44);
          goto LABEL_87;
        }
      }
      else
      {
        BackupLnk = -2147024809;
      }
LABEL_93:
      ILFree(pidl);
      goto LABEL_95;
    }
    v54 = 0;
    if ( !a3 )
      goto LABEL_47;
    if ( (unsigned __int64)a3 < 0x10000 || !ILIsEqual(v6, a3) )
    {
      (*(void (__fastcall **)(struct CPinnedList *))(*(_QWORD *)a1 + 168LL))(a1);
      v54 = 1;
      if ( (unsigned __int64)a3 < 0x10000 )
        goto LABEL_47;
    }
    SystemTimeAsFileTime = 0;
    TimestampFromPidl = GetTimestampFromPidl(v6, 3203334187LL, &SystemTimeAsFileTime);
    if ( TimestampFromPidl < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C,
        (unsigned int)"Desktop\\Internal\\Shell\\Inc\\private\\PinningTimeHelpers.h",
        (const char *)(unsigned int)TimestampFromPidl,
        ppv);
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    }
    BackupLnk = SetPinTimeForPinnedItem(a3, &SystemTimeAsFileTime, &v59);
    if ( BackupLnk < 0 )
      goto LABEL_37;
    a3 = v59;
    if ( (unsigned __int64)v59 >= 0x10000 )
    {
      BackupLnk = (*(__int64 (__fastcall **)(struct CPinnedList *, WCHAR *, __int64))(*(_QWORD *)a1 + 104LL))(
                    a1,
                    psz,
                    260);
      wil::make_unique_nothrow<CBackupLocationManager,>(&ppwsz);
      v22 = ppwsz;
      if ( ppwsz )
      {
        BackupLnk = SHStrDupW(psz, ppwsz);
        if ( BackupLnk >= 0 )
        {
          pv = 0;
          v72[0] = (struct _ITEMIDLIST *)&pv;
          v72[1] = 0;
          LOBYTE(v73) = 1;
          BackupLnk = CBackupLocationManager::CreateBackupLnk((CBackupLocationManager *)v22, a3, &v72[1], v23);
          wil::details::out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(v72);
          if ( BackupLnk >= 0 )
          {
            p_pidl = &pidl;
            ppv = a5;
            BackupLnk = CPinList::ReplacePidl(hdsa, a1, v6, pv);
          }
          v19 = pv;
          pv = 0;
          if ( v19 )
            CoTaskMemFree(v19);
        }
      }
      if ( v22 )
        CBackupLocationManager::`scalar deleting destructor'((CBackupLocationManager *)v22, v21);
    }
    else
    {
LABEL_47:
      p_pidl = &pidl;
      ppv = a5;
      BackupLnk = CPinList::ReplacePidl(hdsa, a1, v6, a3);
    }
LABEL_37:
    v24 = wil::details::static_lazy<TaskbarPinningTelemetry>::get(
            v19,
            _lambda_576b8a055e1eddaf8c0f48bcebe2427e_::_lambda_invoker_cdecl_);
    if ( *(_QWORD *)(v24 + 8) && **(_DWORD **)(v24 + 8) )
    {
      Str[0] = 0;
      Str[1] = 0;
      v75 = 0;
      v25 = -1;
      if ( !pidl
        || (v26 = *(void (__fastcall **)(char *, LPITEMIDLIST, wchar_t **))(*((_QWORD *)a1 + 2) + 88LL),
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(Str),
            Str[1] = (wchar_t *)-1LL,
            v75 = -1,
            v26((char *)a1 + 16, pidl, Str),
            v17 = 1,
            !Str[0])
        || !*Str[0] )
      {
        pv = 0;
        Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&pv);
        if ( CoCreateInstance(
               &CLSID_StartMenuCacheAndAppResolver,
               0,
               1u,
               &GUID_de25675a_72de_44b4_9373_05170450c140,
               &pv) >= 0 )
        {
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(Str);
          Str[1] = (wchar_t *)-1LL;
          v75 = -1;
          _GetAppIDFromIDList((struct IApplicationResolver *)pv, v6, Str, 0);
        }
        Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&pv);
      }
      if ( TaskbarPinHelper::IsPlaceholderPin((TaskbarPinHelper *)v6, v27) )
      {
        TaskbarPinningTelemetry::PinningActivity::PinnedListPlaceholderProcessed(
          (TaskbarPinningTelemetry::PinningActivity *)v81,
          Str[0],
          v54);
      }
      else if ( v54 )
      {
        TaskbarPinningTelemetry::PinningActivity::TaskListTileMoved(v81, Str[0], a4);
      }
      else
      {
        v72[0] = 0;
        v72[1] = 0;
        v73 = 0;
        v79[0] = 0;
        v79[1] = 0;
        v80 = 0;
        v76[0] = 0;
        v76[1] = 0;
        v77 = 0;
        LOBYTE(v28) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_TaskbarSuggestions>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_TaskbarSuggestions>::GetImpl'::`2'::impl,
          v28);
        v30 = Str[0];
        if ( Str[0] )
        {
          if ( *Str[0] )
          {
            (*(void (__fastcall **)(struct CPinnedList *, wchar_t *))(*(_QWORD *)a1 + 192LL))(a1, Str[0]);
            v30 = Str[0];
          }
          if ( v30 && *v30 && SecondaryTileIdentifierHelpers::IsFullyQualifiedTileIdentifier(v30, v29) )
          {
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v76);
            v76[1] = (unsigned __int16 *)-1LL;
            v77 = -1;
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v79);
            v79[1] = (unsigned __int16 *)-1LL;
            v80 = -1;
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v72);
            v72[1] = (struct _ITEMIDLIST *)-1LL;
            v73 = -1;
            TaskbarTelemetryHelper::GetSecondaryTileLaunchArguments(Str[0], (unsigned __int16 *)v72, v79, v76);
            SystemTimeAsFileTime = 0;
            v64 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(
              &hstringHeader,
              L"Windows.UI.StartScreen.SecondaryTile",
              0x25u,
              0x24u);
            v31 = v64;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&SystemTimeAsFileTime);
            ActivationFactory = RoGetActivationFactory(
                                  v31,
                                  &GUID_57f52ca0_51bc_4abf_8ebf_627a0398b05a,
                                  &SystemTimeAsFileTime);
            if ( ActivationFactory >= 0 )
            {
              pv = 0;
              v33 = SystemTimeAsFileTime;
              v34 = ***(__int64 (__fastcall ****)(struct _FILETIME, GUID *, LPVOID *))&SystemTimeAsFileTime;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
              v35 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))v34)(
                      v33,
                      &GUID_5365d67e_eedb_4ecd_a099_a195558a9f80,
                      &pv);
              if ( v35 >= 0 )
              {
                memset(&hstringHeader, 0, sizeof(hstringHeader));
                v61[0] = 0;
                v61[1] = 0;
                v62 = 0;
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v61);
                v61[1] = (unsigned __int16 *)-1LL;
                v62 = -1;
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
                *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = -1;
                *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = -1;
                AumidAndAppSpecifiedTileIdFromFullyQualifiedTileIdentifier = SecondaryTileIdentifierHelpers::GetAumidAndAppSpecifiedTileIdFromFullyQualifiedTileIdentifier(
                                                                               Str[0],
                                                                               (const unsigned __int16 *)&hstringHeader,
                                                                               v61,
                                                                               v36);
                if ( AumidAndAppSpecifiedTileIdFromFullyQualifiedTileIdentifier >= 0 )
                {
                  v38 = pv;
                  v39 = *(__int64 (__fastcall **)(LPVOID, PVOID, PVOID))(*(_QWORD *)pv + 72LL);
                  Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v67, (const WCHAR **)v61)[1].Reserved.Reserved1;
                  v41 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                          &v68,
                          (const WCHAR **)&hstringHeader);
                  v42 = v39(v38, v41[1].Reserved.Reserved1, Reserved1);
                  wil::details::in1diag3::Log_IfFailedWithExpected(
                    retaddr,
                    (void *)0x6F5,
                    (unsigned int)"pcshell\\shell\\pinninglib\\lib\\PinnedList.cpp",
                    (const char *)v42,
                    1,
                    0x80070490);
                  v6 = v57;
                }
                else
                {
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x6F3,
                    (unsigned int)"pcshell\\shell\\pinninglib\\lib\\PinnedList.cpp",
                    (const char *)(unsigned int)AumidAndAppSpecifiedTileIdFromFullyQualifiedTileIdentifier,
                    ppv);
                }
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v61);
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
              }
              else
              {
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x6EF,
                  (unsigned int)"pcshell\\shell\\pinninglib\\lib\\PinnedList.cpp",
                  (const char *)(unsigned int)v35,
                  ppv);
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
              v17 = 1;
            }
            else
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x6EC,
                (unsigned int)"pcshell\\shell\\pinninglib\\lib\\PinnedList.cpp",
                (const char *)(unsigned int)ActivationFactory,
                ppv);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&SystemTimeAsFileTime);
          }
        }
        if ( !v76[0] )
        {
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v76);
          v76[1] = (unsigned __int16 *)-1LL;
          v77 = -1;
          ILGetHiddenStringAllocW(pidl, 3203334174LL, v76);
        }
        LODWORD(pv) = 0;
        if ( (int)GetPinSourceForPinnedItem(pidl, (enum TaskbarPinningSource *)&pv) >= 0 )
          v25 = (int)pv;
        LODWORD(p_pidl) = v25;
        TaskbarPinningTelemetry::PinningActivity::PinnedListRemoved(v81, Str[0], v72[0], v79[0], v76[0], p_pidl, a4);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v76);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v79);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v72);
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(Str);
    }
LABEL_87:
    if ( BackupLnk >= 0 )
    {
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        &v56,
        0);
      if ( !v6 || a3 )
        v17 = 0;
      CPinnedList::_DoNotifyPinListChange(a1, pidl, v17);
    }
    goto LABEL_93;
  }
  BackupLnk = -2147024882;
LABEL_95:
  ILFree(v65);
  ILFree(v66);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v56,
    0);
  v51 = (unsigned int)BackupLnk;
  if ( v6 && !a3 && BackupLnk == -2147023728 )
    v51 = 0;
  wil::ActivityBase<TaskbarLogging,1,35184372088832,5,33554432,_TlgReflectorTag_Param0IsProviderType>::Stop(v81, v51);
  CPinList::~CPinList((CPinList *)hdsa);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v56);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v58);
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v59);
  TaskbarPinningTelemetry::PinningActivity::~PinningActivity((TaskbarPinningTelemetry::PinningActivity *)v81);
  return (unsigned int)BackupLnk;
}

```

## disassembly

```asm
0x180354cb4  push    rbp
0x180354cb6  push    rbx
0x180354cb7  push    rsi
0x180354cb8  push    rdi
0x180354cb9  push    r12
0x180354cbb  push    r13
0x180354cbd  push    r14
0x180354cbf  push    r15
0x180354cc1  lea     rbp, [rsp-608h]
0x180354cc9  sub     rsp, 708h
0x180354cd0  mov     rax, cs:__security_cookie
0x180354cd7  xor     rax, rsp
0x180354cda  mov     [rbp+640h+var_50], rax
0x180354ce1  mov     [rsp+740h+var_6FC], r9d
0x180354ce6  mov     r15, r8
0x180354ce9  mov     rsi, rdx
0x180354cec  mov     [rsp+740h+var_6F0], rdx
0x180354cf1  mov     r13, rcx
0x180354cf4  mov     rax, [rcx]
0x180354cf7  mov     rax, [rax+78h]
0x180354cfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180354d00  xor     r12d, r12d
0x180354d03  test    eax, eax
0x180354d05  jz      short loc_180354D11
0x180354d07  mov     eax, 80070005h
0x180354d0c  jmp     loc_18035576B
0x180354d11  xor     edx, edx; Val
0x180354d13  mov     r8d, 150h; Size
0x180354d19  lea     rcx, [rbp+640h+var_5C0]; void *
0x180354d20  call    memset_0
0x180354d25  lea     rcx, [rbp+640h+var_5C0]; this
0x180354d2c  call    ??$Start@$$V@PinningActivity@TaskbarPinningTelemetry@@SA?AV01@XZ; TaskbarPinningTelemetry::PinningActivity::Start<>(void)
0x180354d31  nop
0x180354d32  mov     [rbp+640h+var_698], r12
0x180354d36  mov     [rbp+640h+var_690], r12
0x180354d3a  mov     [rsp+740h+var_6E0], r12
0x180354d3f  test    rsi, rsi
0x180354d42  jz      short loc_180354D5D
0x180354d44  mov     rcx, rsi
0x180354d47  call    cs:__imp_SHLogILFromFSIL
0x180354d4d  mov     [rbp+640h+var_698], rax
0x180354d51  test    rax, rax
0x180354d54  cmovnz  rsi, rax
0x180354d58  mov     [rsp+740h+var_6F0], rsi
0x180354d5d  mov     r14d, 10000h
0x180354d63  cmp     r15, r14
0x180354d66  jb      short loc_180354D7C
0x180354d68  mov     rcx, r15
0x180354d6b  call    cs:__imp_SHLogILFromFSIL
0x180354d71  mov     [rbp+640h+var_690], rax
0x180354d75  test    rax, rax
0x180354d78  cmovnz  r15, rax
0x180354d7c  mov     [rsp+740h+var_6E8], r12
0x180354d81  mov     rcx, [r13+0]
0x180354d85  mov     rax, [rcx+0D0h]
0x180354d8c  mov     rcx, r13
0x180354d8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180354d94  mov     r9d, 1F0001h; dwDesiredAccess
0x180354d9a  xor     r8d, r8d; dwFlags
0x180354d9d  mov     rdx, rax; lpName
0x180354da0  xor     ecx, ecx; lpMutexAttributes
0x180354da2  call    cs:__imp_CreateMutexExW
0x180354da8  mov     rbx, rax
0x180354dab  test    rax, rax
0x180354dae  jz      short loc_180354DC8
0x180354db0  call    cs:__imp_GetLastError
0x180354db6  mov     rdx, rbx
0x180354db9  lea     rcx, [rsp+740h+var_6E8]
0x180354dbe  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180354dc3  mov     edi, r12d
0x180354dc6  jmp     short loc_180354DCF
0x180354dc8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180354dcd  mov     edi, eax
0x180354dcf  mov     rbx, r12
0x180354dd2  mov     [rsp+740h+var_6F8], rbx
0x180354dd7  test    edi, edi
0x180354dd9  js      short loc_180354E25
0x180354ddb  lea     rdx, [rbp+640h+SystemTimeAsFileTime]
0x180354ddf  lea     rcx, [rsp+740h+var_6E8]
0x180354de4  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180354de9  mov     r14, rax
0x180354dec  lea     rax, [rsp+740h+var_6F8]
0x180354df1  cmp     rax, r14
0x180354df4  jz      short loc_180354E0B
0x180354df6  mov     rdx, [r14]
0x180354df9  lea     rcx, [rsp+740h+var_6F8]
0x180354dfe  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180354e03  mov     [r14], r12
0x180354e06  mov     rbx, [rsp+740h+var_6F8]
0x180354e0b  lea     rcx, [rbp+640h+SystemTimeAsFileTime]
0x180354e0f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180354e14  mov     eax, 8007139Fh
0x180354e19  test    rbx, rbx
0x180354e1c  cmovz   edi, eax
0x180354e1f  mov     r14d, 10000h
0x180354e25  xorps   xmm1, xmm1
0x180354e28  movdqu  xmmword ptr [rbp+640h+hdsa], xmm1
0x180354e2d  xor     ebx, ebx
0x180354e2f  test    edi, edi
0x180354e31  js      loc_1803556E7
0x180354e37  mov     rdx, r13; struct CPinnedList *
0x180354e3a  lea     rcx, [rbp+640h+hdsa]; this
0x180354e3e  call    ?Load@CPinList@@QEAAJPEAVCPinnedList@@@Z; CPinList::Load(CPinnedList *)
0x180354e43  test    eax, eax
0x180354e45  js      loc_1803556E7
0x180354e4b  mov     [rbp+640h+pidl], rbx
0x180354e4f  lea     edi, [rbx+1]
0x180354e52  test    rsi, rsi
0x180354e55  jz      loc_180355486
0x180354e5b  mov     [rsp+740h+var_700], bl
0x180354e5f  test    r15, r15
0x180354e62  jz      loc_1803550F0
0x180354e68  cmp     r15, r14
0x180354e6b  jb      short loc_180354E7D
0x180354e6d  mov     rdx, r15; pidl2
0x180354e70  mov     rcx, rsi; pidl1
0x180354e73  call    cs:__imp_ILIsEqual
0x180354e79  test    eax, eax
0x180354e7b  jnz     short loc_180354E9E
0x180354e7d  mov     rax, [r13+0]
0x180354e81  mov     rcx, r13
0x180354e84  mov     rax, [rax+0A8h]
0x180354e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180354e90  mov     [rsp+740h+var_700], dil
0x180354e95  cmp     r15, r14
0x180354e98  jb      loc_1803550F0
0x180354e9e  mov     qword ptr [rbp+640h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x180354ea2  lea     r8, [rbp+640h+SystemTimeAsFileTime]
0x180354ea6  mov     edx, 0BEEF002Bh
0x180354eab  mov     rcx, rsi
0x180354eae  call    ?GetTimestampFromPidl@@YAJPEFBU_ITEMIDLIST@@W4IDLHID@@PEAU_FILETIME@@@Z; GetTimestampFromPidl(_ITEMIDLIST const *,IDLHID,_FILETIME *)
0x180354eb3  test    eax, eax
0x180354eb5  jns     short loc_180354EDC
0x180354eb7  mov     rcx, [rbp+648h]; this
0x180354ebe  mov     r9d, eax; char *
0x180354ec1  lea     r8, aDesktopInterna_18; "Desktop\\Internal\\Shell\\Inc\\private"...
0x180354ec8  mov     edx, 1Ch; void *
0x180354ecd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180354ed2  lea     rcx, [rbp+640h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180354ed6  call    cs:__imp_GetSystemTimeAsFileTime
0x180354edc  lea     r8, [rsp+740h+var_6E0]; struct _ITEMIDLIST **
0x180354ee1  lea     rdx, [rbp+640h+SystemTimeAsFileTime]; struct _FILETIME *
0x180354ee5  mov     rcx, r15; Src
0x180354ee8  call    ?SetPinTimeForPinnedItem@@YAJPEFBU_ITEMIDLIST@@PEAU_FILETIME@@PEAPEFAU1@@Z; SetPinTimeForPinnedItem(_ITEMIDLIST const *,_FILETIME *,_ITEMIDLIST * *)
0x180354eed  mov     r14d, eax
0x180354ef0  test    eax, eax
0x180354ef2  js      loc_180354FE8
0x180354ef8  mov     r15, [rsp+740h+var_6E0]
0x180354efd  test    r15, r15
0x180354f00  jz      loc_1803550F0
0x180354f06  mov     r14d, 10000h
0x180354f0c  cmp     r15, r14
0x180354f0f  jb      loc_1803550F0
0x180354f15  mov     rax, [r13+0]
0x180354f19  mov     r8d, 104h
0x180354f1f  lea     rdx, [rbp+640h+psz]
0x180354f26  mov     rcx, r13
0x180354f29  mov     rax, [rax+68h]
0x180354f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180354f32  mov     r14d, eax
0x180354f35  lea     rcx, [rsp+740h+ppwsz]
0x180354f3a  call    ??$make_unique_nothrow@VCBackupLocationManager@@$$V@wil@@YA?AV?$unique_ptr@VCBackupLocationManager@@U?$default_delete@VCBackupLocationManager@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<CBackupLocationManager,>(void)
0x180354f3f  nop
0x180354f40  mov     rbx, [rsp+740h+ppwsz]
0x180354f45  xor     r12d, r12d
0x180354f48  test    rbx, rbx
0x180354f4b  jz      loc_180354FD9
0x180354f51  mov     rdx, rbx; ppwsz
0x180354f54  lea     rcx, [rbp+640h+psz]; psz
0x180354f5b  call    cs:__imp_SHStrDupW
0x180354f61  mov     r14d, eax
0x180354f64  test    eax, eax
0x180354f66  js      short loc_180354FD9
0x180354f68  mov     [rbp+640h+pv], r12
0x180354f6c  lea     rax, [rbp+640h+pv]
0x180354f70  mov     [rbp+640h+var_630], rax
0x180354f74  mov     [rbp+640h+var_630+8], r12
0x180354f78  mov     byte ptr [rbp+640h+var_620], dil
0x180354f7c  lea     r8, [rbp+640h+var_630+8]; struct _ITEMIDLIST **
0x180354f80  mov     rdx, r15; struct _ITEMIDLIST *
0x180354f83  mov     rcx, rbx; this
0x180354f86  call    ?CreateBackupLnk@CBackupLocationManager@@QEBAJPEFBU_ITEMIDLIST@@PEAPEFAU2@@Z; CBackupLocationManager::CreateBackupLnk(_ITEMIDLIST const *,_ITEMIDLIST * *)
0x180354f8b  mov     r14d, eax
0x180354f8e  lea     rcx, [rbp+640h+var_630]
0x180354f92  call    ??1?$out_param_ptr_t@PEAPEAUGMRelatedProcess@KnownGameList@@V?$unique_ptr@$$BY0A@UGMRelatedProcess@KnownGameList@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180354f97  test    r14d, r14d
0x180354f9a  js      short loc_180354FC5
0x180354f9c  lea     rax, [rbp+640h+pidl]
0x180354fa0  mov     qword ptr [rsp+740h+var_718], rax
0x180354fa5  mov     eax, [rbp+640h+arg_20]
0x180354fab  mov     dword ptr [rsp+740h+ppv], eax
0x180354faf  mov     r9, [rbp+640h+pv]
0x180354fb3  mov     r8, rsi
0x180354fb6  mov     rdx, r13
0x180354fb9  lea     rcx, [rbp+640h+hdsa]
0x180354fbd  call    ?ReplacePidl@CPinList@@QEAAJPEAVCPinnedList@@PEFBU_ITEMIDLIST@@1W4PinnedListModifyFlags@@PEAPEFAU3@@Z; CPinList::ReplacePidl(CPinnedList *,_ITEMIDLIST const *,_ITEMIDLIST const *,PinnedListModifyFlags,_ITEMIDLIST * *)
0x180354fc2  mov     r14d, eax
0x180354fc5  mov     rcx, [rbp+640h+pv]; pv
0x180354fc9  mov     [rbp+640h+pv], r12
0x180354fcd  test    rcx, rcx
0x180354fd0  jz      short loc_180354FD9
0x180354fd2  call    cs:__imp_CoTaskMemFree
0x180354fd8  nop
0x180354fd9  test    rbx, rbx
0x180354fdc  jz      short loc_180354FE6
0x180354fde  mov     rcx, rbx; this
0x180354fe1  call    ??_GCBackupLocationManager@@QEAAPEAXI@Z; CBackupLocationManager::`scalar deleting destructor'(uint)
0x180354fe6  xor     ebx, ebx
0x180354fe8  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_576b8a055e1eddaf8c0f48bcebe2427e_@@CA@XZ; _lambda_576b8a055e1eddaf8c0f48bcebe2427e_::_lambda_invoker_cdecl_(void)
0x180354fef  call    ?get@?$static_lazy@VTaskbarPinningTelemetry@@@details@wil@@QEAAPEAVTaskbarPinningTelemetry@@P6AXXZ@Z; wil::details::static_lazy<TaskbarPinningTelemetry>::get(void (*)(void))
0x180354ff4  cmp     [rax+8], rbx
0x180354ff8  jz      loc_1803556A7
0x180354ffe  mov     rax, [rax+8]
0x180355002  mov     ecx, [rax]
0x180355004  test    ecx, ecx
0x180355006  jz      loc_1803556A7
0x18035500c  xorps   xmm0, xmm0
0x18035500f  movups  xmmword ptr [rbp+640h+Str], xmm0
0x180355013  mov     [rbp+640h+Str], rbx
0x180355017  mov     [rbp+640h+Str+8], rbx
0x18035501b  mov     [rbp+640h+var_608], rbx
0x18035501f  or      r12, 0FFFFFFFFFFFFFFFFh
0x180355023  cmp     [rbp+640h+pidl], rbx
0x180355027  jz      short loc_180355069
0x180355029  mov     rax, [r13+10h]
0x18035502d  mov     rbx, [rax+58h]
0x180355031  lea     rcx, [rbp+640h+Str]
0x180355035  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18035503a  mov     [rbp+640h+Str+8], r12
0x18035503e  mov     [rbp+640h+var_608], r12
0x180355042  lea     r8, [rbp+640h+Str]
0x180355046  mov     rdx, [rbp+640h+pidl]
0x18035504a  lea     rcx, [r13+10h]
0x18035504e  mov     rax, rbx
0x180355051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180355056  mov     rax, [rbp+640h+Str]
0x18035505a  xor     ebx, ebx
0x18035505c  lea     edi, [rbx+1]
0x18035505f  test    rax, rax
0x180355062  jz      short loc_180355069
0x180355064  cmp     [rax], bx
0x180355067  jnz     short loc_1803550CA
0x180355069  mov     [rbp+640h+pv], rbx
0x18035506d  lea     rcx, [rbp+640h+pv]
0x180355071  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x180355076  lea     rax, [rbp+640h+pv]
0x18035507a  mov     [rsp+740h+ppv], rax; int
0x18035507f  lea     r9, _GUID_de25675a_72de_44b4_9373_05170450c140; riid
0x180355086  mov     r8d, edi; dwClsContext
0x180355089  xor     edx, edx; pUnkOuter
0x18035508b  lea     rcx, CLSID_StartMenuCacheAndAppResolver; rclsid
0x180355092  call    cs:__imp_CoCreateInstance
0x180355098  test    eax, eax
0x18035509a  js      short loc_1803550C1
0x18035509c  lea     rcx, [rbp+640h+Str]
0x1803550a0  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1803550a5  mov     [rbp+640h+Str+8], r12
0x1803550a9  mov     [rbp+640h+var_608], r12
0x1803550ad  xor     r9d, r9d; int *
0x1803550b0  lea     r8, [rbp+640h+Str]; unsigned __int16 **
0x1803550b4  mov     rdx, rsi; struct _ITEMIDLIST *
0x1803550b7  mov     rcx, [rbp+640h+pv]; struct IApplicationResolver *
0x1803550bb  call    ?_GetAppIDFromIDList@@YAJPEAUIApplicationResolver@@PEFBU_ITEMIDLIST@@PEAPEAGPEAH@Z; _GetAppIDFromIDList(IApplicationResolver *,_ITEMIDLIST const *,ushort * *,int *)
0x1803550c0  nop
0x1803550c1  lea     rcx, [rbp+640h+pv]
0x1803550c5  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x1803550ca  mov     rcx, rsi; this
0x1803550cd  call    ?IsPlaceholderPin@TaskbarPinHelper@@YA_NPEFBU_ITEMIDLIST@@@Z; TaskbarPinHelper::IsPlaceholderPin(_ITEMIDLIST const *)
0x1803550d2  test    al, al
0x1803550d4  jz      short loc_18035511D
0x1803550d6  mov     r8b, [rsp+740h+var_700]; bool
0x1803550db  mov     rdx, [rbp+640h+Str]; unsigned __int16 *
0x1803550df  lea     rcx, [rbp+640h+var_5C0]; this
0x1803550e6  call    ?PinnedListPlaceholderProcessed@PinningActivity@TaskbarPinningTelemetry@@QEAAXPEBG_N@Z; TaskbarPinningTelemetry::PinningActivity::PinnedListPlaceholderProcessed(ushort const *,bool)
0x1803550eb  jmp     loc_180355478
0x1803550f0  lea     rax, [rbp+640h+pidl]
0x1803550f4  mov     qword ptr [rsp+740h+var_718], rax
0x1803550f9  mov     eax, [rbp+640h+arg_20]
0x1803550ff  mov     dword ptr [rsp+740h+ppv], eax
0x180355103  mov     r9, r15
0x180355106  mov     r8, rsi
0x180355109  mov     rdx, r13
0x18035510c  lea     rcx, [rbp+640h+hdsa]
0x180355110  call    ?ReplacePidl@CPinList@@QEAAJPEAVCPinnedList@@PEFBU_ITEMIDLIST@@1W4PinnedListModifyFlags@@PEAPEFAU3@@Z; CPinList::ReplacePidl(CPinnedList *,_ITEMIDLIST const *,_ITEMIDLIST const *,PinnedListModifyFlags,_ITEMIDLIST * *)
0x180355115  mov     r14d, eax
0x180355118  jmp     loc_180354FE8
0x18035511d  cmp     [rsp+740h+var_700], bl
0x180355121  jz      short loc_18035513D
0x180355123  mov     r8d, [rsp+740h+var_6FC]
0x180355128  mov     rdx, [rbp+640h+Str]
0x18035512c  lea     rcx, [rbp+640h+var_5C0]
0x180355133  call    ?TaskListTileMoved@PinningActivity@TaskbarPinningTelemetry@@QEAAXPEBGW4PINNEDLISTMODIFYCALLER@@@Z; TaskbarPinningTelemetry::PinningActivity::TaskListTileMoved(ushort const *,PINNEDLISTMODIFYCALLER)
0x180355138  jmp     loc_180355478
0x18035513d  xorps   xmm0, xmm0
0x180355140  movups  xmmword ptr [rbp+640h+var_630], xmm0
0x180355144  mov     [rbp+640h+var_630], rbx
0x180355148  mov     [rbp+640h+var_630+8], rbx
0x18035514c  mov     [rbp+640h+var_620], rbx
0x180355150  movups  xmmword ptr [rbp+640h+var_5D8], xmm0
0x180355154  mov     [rbp+640h+var_5D8], rbx
  ... truncated ...
```
