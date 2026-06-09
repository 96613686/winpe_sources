# CLauncherTipContextMenu::_EnumerateAndBuildMenu(void)

- ea: `0x1800c8b20`
- end: `0x1800c94f1`
- name: `?_EnumerateAndBuildMenu@CLauncherTipContextMenu@@AEAAJXZ`
- size: `2513`
- prototype: `__int64 __fastcall(CLauncherTipContextMenu *__hidden this)`
- caller_count: `1`
- callee_count: `41`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801e7d1c`

## callees

- `0x1800134f8`
- `0x18001f6e0`
- `0x1800290dc`
- `0x18002d770`
- `0x18002e580`
- `0x18005a710`
- `0x180086ac0`
- `0x18008a6f0`
- `0x18008ba80`
- `0x1800c8b20`
- `0x1800c94f8`
- `0x1800c95e8`
- `0x1800caa04`
- `0x180160078`
- `0x180164a6c`
- `0x180164adc`
- `0x1801b7c6c`
- `0x180248854`
- `0x18025f2c8`
- `0x18025f414`
- `0x1802688dc`
- `0x180269044`
- `0x1802697f0`
- `0x1802698e0`
- `0x1802698fc`
- `0x180269d2c`
- `0x18026aab0`
- `0x18026b0f8`
- `0x180271618`
- `0x1802cd938`
- `0x1802d49d0`
- `0x180356360`
- `0x180356edc`
- `0x180357044`
- `0x18035b7fd`
- `0x1806062b8`
- `0x180607260`
- `0x180608fe8`
- `0x180609a88`
- `0x18060a684`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800c8d4e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800c8d4e`
- `USER32!AppendMenuW` at `0x1800c9380`
- `USER32!AppendMenuW` at `0x1800c93f5`
- `USER32!AppendMenuW` at `0x1800c9380`
- `USER32!AppendMenuW` at `0x1800c93f5`
- `USER32!CreatePopupMenu` at `0x1800c930f`
- `USER32!CreatePopupMenu` at `0x1800c938c`
- `USER32!CreatePopupMenu` at `0x1800c930f`
- `USER32!CreatePopupMenu` at `0x1800c938c`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderItem` at `0x1800c8c0d`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderItem` at `0x1800c8c86`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderItem` at `0x1800c8c0d`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderItem` at `0x1800c8c86`
- `SHELL32!SHFileOperationW` at `0x1800c8e6f`
- `SHELL32!SHFileOperationW` at `0x1800c8e6f`
- `SHELL32!SHCreateItemFromRelativeName` at `0x1800c8c4b`
- `SHELL32!SHCreateItemFromRelativeName` at `0x1800c8cc1`
- `SHELL32!SHCreateItemFromRelativeName` at `0x1800c8e9b`
- `SHELL32!SHCreateItemFromRelativeName` at `0x1800c8c4b`
- `SHELL32!SHCreateItemFromRelativeName` at `0x1800c8cc1`
- `SHELL32!SHCreateItemFromRelativeName` at `0x1800c8e9b`

## pseudocode

```c
// Hidden C++ exception states: #wind=17 #try_helpers=1
__int64 __fastcall CLauncherTipContextMenu::_EnumerateAndBuildMenu(CLauncherTipContextMenu *this)
{
  void **v2; // r12
  volatile signed __int32 *v3; // rcx
  void *v4; // rax
  __int64 v5; // rdx
  HRESULT Error; // edi
  void *v7; // rdi
  __int64 (__fastcall *v8)(void *, __int64, LPCWSTR *); // rbx
  IShellItem *v9; // rdi
  HRESULT (__stdcall *GetDisplayName)(IShellItem *, SIGDN, LPWSTR *); // rbx
  __int64 v11; // rax
  unsigned int i; // r14d
  char *v13; // r8
  __int64 v14; // rdx
  _DWORD *v15; // rdx
  unsigned int v16; // r14d
  int v17; // eax
  _DWORD *v18; // rdx
  bool v19; // r15
  __int64 v20; // r14
  __int64 v21; // rdx
  int *v22; // rbx
  int *v23; // r14
  int v24; // eax
  void **v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rax
  unsigned __int64 j; // rbx
  _QWORD *v29; // r14
  struct IShellItem *v30; // r15
  IShellItem *v31; // r12
  int v32; // r8d
  unsigned __int64 v33; // rax
  unsigned __int64 v34; // r13
  unsigned __int64 v35; // r8
  IShellItem **v36; // rcx
  HMENU PopupMenu; // rax
  UINT_PTR v38; // r14
  __int64 v39; // rax
  __int64 v40; // rbx
  HMENU v41; // rax
  _QWORD *v42; // r12
  __int64 v43; // rsi
  IShellItem *v44; // rcx
  IShellItem *v46; // [rsp+30h] [rbp-518h] BYREF
  bool v47[8]; // [rsp+38h] [rbp-510h] BYREF
  void *v48; // [rsp+40h] [rbp-508h] BYREF
  struct IShellItem *ppv; // [rsp+48h] [rbp-500h] BYREF
  IShellItem *psiParent; // [rsp+50h] [rbp-4F8h] BYREF
  LPCWSTR lpNewItem; // [rsp+58h] [rbp-4F0h] BYREF
  __int64 v52; // [rsp+60h] [rbp-4E8h]
  __int64 v53; // [rsp+68h] [rbp-4E0h]
  _BYTE *v54; // [rsp+78h] [rbp-4D0h] BYREF
  char *v55; // [rsp+80h] [rbp-4C8h]
  char *v56; // [rsp+88h] [rbp-4C0h]
  __int64 v57; // [rsp+90h] [rbp-4B8h] BYREF
  __int64 v58; // [rsp+98h] [rbp-4B0h]
  __int64 v59; // [rsp+A0h] [rbp-4A8h]
  _SHFILEOPSTRUCTW FileOp; // [rsp+A8h] [rbp-4A0h] BYREF
  char v61[16]; // [rsp+E0h] [rbp-468h] BYREF
  _BYTE v62[528]; // [rsp+F0h] [rbp-458h] BYREF
  wchar_t Buffer[264]; // [rsp+300h] [rbp-248h] BYREF

  v2 = (void **)((char *)this + 408);
  v3 = *(volatile signed __int32 **)(tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_WinXMenuEnumerationTest,_tip_WinXMenuEnumerationTest>>>((struct wil::details::IFailureCallback *)&FileOp)
                                   + 56);
  v4 = *v2;
  *v2 = (void *)v3;
  if ( v3 )
    _InterlockedIncrement(v3 + 78);
  if ( v4 )
    tip2::details::merged_data<_tip_WinXMenuEnumerationTest,_tip_WinXMenuEnumerationTest>::Release(v4);
  wil::com_ptr_t<tip2::details::merged_data<_tip_WinXMenuEnumerationTest,_tip_WinXMenuEnumerationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WinXMenuEnumerationTest,_tip_WinXMenuEnumerationTest>,wil::err_returncode_policy>(v61);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)&FileOp.wFunc);
  LOBYTE(v5) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WinXReplaceTerminalWithPowerShell_37536857>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_Servicing_WinXReplaceTerminalWithPowerShell_37536857>::GetImpl'::`2'::impl,
    v5);
  *((_BYTE *)this + 345) = 0;
  if ( (char *)this + 346 <= (char *)this + 349 )
    memset_0((char *)this + 346, 0, (char *)this + 349 >= (char *)this + 346 ? 3 : 0);
  psiParent = 0;
  Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&psiParent);
  Error = SHGetKnownFolderItem(
            &FOLDERID_LocalAppData,
            KF_FLAG_DEFAULT,
            0,
            &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
            (void **)&psiParent);
  if ( Error >= 0 )
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&ppv);
    Error = SHCreateItemFromRelativeName(
              psiParent,
              L"Microsoft\\Windows\\WinX",
              0,
              &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
              (void **)&ppv);
    if ( Error == -2147024894 )
    {
      v46 = 0;
      Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v46);
      Error = SHGetKnownFolderItem(
                &FOLDERID_UserProfiles,
                KF_FLAG_DEFAULT,
                0,
                &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                (void **)&v46);
      if ( Error >= 0 )
      {
        v48 = 0;
        Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v48);
        Error = SHCreateItemFromRelativeName(
                  v46,
                  L"Default\\AppData\\Local\\Microsoft\\Windows\\WinX",
                  0,
                  &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                  &v48);
        if ( Error >= 0 )
        {
          lpNewItem = 0;
          v52 = 0;
          v53 = 0;
          v7 = v48;
          v8 = *(__int64 (__fastcall **)(void *, __int64, LPCWSTR *))(*(_QWORD *)v48 + 40LL);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpNewItem);
          v52 = -1;
          v53 = -1;
          Error = v8(v7, 2147844096LL, &lpNewItem);
          if ( Error >= 0 )
          {
            memset_0(v62, 0, 0x208u);
            if ( (unsigned int)_o_wcscpy_s(v62, 260, lpNewItem) )
            {
              Error = -2147467259;
            }
            else
            {
              v57 = 0;
              v58 = 0;
              v59 = 0;
              v9 = psiParent;
              GetDisplayName = psiParent->lpVtbl->GetDisplayName;
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v57);
              v58 = -1;
              v59 = -1;
              Error = ((__int64 (__fastcall *)(IShellItem *, __int64, __int64 *))GetDisplayName)(v9, 2147844096LL, &v57);
              if ( Error >= 0 )
              {
                memset_0(Buffer, 0, 0x208u);
                if ( swprintf_s(Buffer, 0x104u, L"%s\\%s", v57, L"Microsoft\\Windows\\WinX") <= 0
                  || (*(_OWORD *)&FileOp.hwnd = 0,
                      memset(&FileOp.fFlags, 0, 24),
                      FileOp.wFunc = 2,
                      FileOp.pFrom = (PCZZWSTR)v62,
                      FileOp.pTo = Buffer,
                      FileOp.fFlags = 2564,
                      SHFileOperationW(&FileOp)) )
                {
                  Error = -2147467259;
                }
                else
                {
                  Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&ppv);
                  Error = SHCreateItemFromRelativeName(
                            psiParent,
                            L"Microsoft\\Windows\\WinX",
                            0,
                            &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                            (void **)&ppv);
                }
              }
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v57);
            }
          }
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpNewItem);
        }
        Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v48);
      }
      Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v46);
    }
    v11 = *((_QWORD *)this + 45);
    if ( v11 != *((_QWORD *)this + 46) )
      *((_QWORD *)this + 46) = v11;
    for ( i = 0; i < 0x11; ++i )
    {
      v13 = (char *)&CLauncherTipContextMenu::c_rgItemMap + 12 * i;
      v14 = *((_QWORD *)this + 46);
      if ( v14 == *((_QWORD *)this + 47) )
      {
        std::vector<CLauncherTipContextMenu::LTCMITEM>::_Emplace_reallocate<CLauncherTipContextMenu::LTCMITEM const &>(
          (char *)this + 360,
          v14,
          v13);
      }
      else
      {
        *(_QWORD *)v14 = *(_QWORD *)v13;
        *(_DWORD *)(v14 + 8) = *((_DWORD *)v13 + 2);
        *((_QWORD *)this + 46) += 12LL;
      }
    }
    v15 = (_DWORD *)*((_QWORD *)this + 48);
    if ( v15 == *((_DWORD **)this + 49) )
      v15 = (_DWORD *)*((_QWORD *)this + 49);
    else
      *((_QWORD *)this + 49) = v15;
    LODWORD(v48) = 0;
    if ( v15 == *((_DWORD **)this + 50) )
    {
      std::vector<unsigned int>::_Emplace_reallocate<unsigned int>((char *)this + 384, v15, &v48);
    }
    else
    {
      *v15 = 0;
      *((_QWORD *)this + 49) += 4LL;
    }
    if ( Error >= 0 )
    {
      CShallowContainerIterator::CShallowContainerIterator((CShallowContainerIterator *)&lpNewItem, ppv, 0x20u);
      Error = (int)lpNewItem;
      if ( (int)lpNewItem >= 0 )
      {
        v16 = 0;
        v46 = 0;
        while ( Error >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
          if ( !CShallowContainerIterator::Next((CShallowContainerIterator *)&lpNewItem, (struct IShellItem2 **)&v46) )
            break;
          if ( *((_QWORD *)this + 23) )
          {
            CLauncherTipContextMenu::_AddSeparator(this);
            v17 = *((_DWORD *)this + 46);
            LODWORD(v48) = v17;
            v18 = (_DWORD *)*((_QWORD *)this + 49);
            if ( v18 == *((_DWORD **)this + 50) )
            {
              std::vector<unsigned int>::_Emplace_reallocate<unsigned int>((char *)this + 384, v18, &v48);
            }
            else
            {
              *v18 = v17;
              *((_QWORD *)this + 49) += 4LL;
            }
            ++v16;
          }
          Error = CLauncherTipContextMenu::_AddFolderLinksToCommands(this, (struct IShellItem2 *)v46, 0, v16);
          if ( Error >= 0 )
            Error = *((_BYTE *)this + 322) != 0 ? 0x80004004 : 0;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      }
      CShallowContainerIterator::~CShallowContainerIterator((CShallowContainerIterator *)&lpNewItem);
    }
    Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&ppv);
    if ( Error >= 0 )
      CLauncherTipContextMenu::AddMissingLinksFromDefaultProfile(this);
  }
  v19 = *((_QWORD *)this + 45) == *((_QWORD *)this + 46);
  v20 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_WinXMenuEnumerationTest,_tip_WinXMenuEnumerationTest>>::ensure_data((char *)this + 408);
  v46 = (IShellItem *)v20;
  if ( v20 )
    _InterlockedIncrement((volatile signed __int32 *)(v20 + 312));
  tip2::details::shared_data<0,0,1>::begin_update(v20 + 8);
  *(_BYTE *)(v20 + 273) = v19;
  tip2::details::shared_data<0,0,0>::end_update(v20 + 8);
  wil::com_ptr_t<tip2::details::merged_data<_tip_WinXMenuEnumerationTest,_tip_WinXMenuEnumerationTest>,wil::err_returncode_policy>::reset(&v46);
  wil::com_ptr_t<tip2::details::merged_data<_tip_WinXMenuEnumerationTest,_tip_WinXMenuEnumerationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WinXMenuEnumerationTest,_tip_WinXMenuEnumerationTest>,wil::err_returncode_policy>(&v46);
  if ( *((_QWORD *)this + 45) != *((_QWORD *)this + 46) )
  {
    std::vector<winrt::event_revoker<winrt::Windows::Internal::Shell::CloudDesktop::TransitionScreen::ITransitionScreen>>::vector<winrt::event_revoker<winrt::Windows::Internal::Shell::CloudDesktop::TransitionScreen::ITransitionScreen>>(&v54);
    v22 = (int *)*((_QWORD *)this + 45);
    v23 = (int *)*((_QWORD *)this + 46);
    while ( v22 != v23 )
    {
      v24 = *v22;
      LODWORD(v48) = *v22;
      if ( v55 == v56 )
      {
        std::vector<winrt::Windows::Internal::ApplicationModel::WindowManagement::WindowId>::_Emplace_reallocate<winrt::Windows::Internal::ApplicationModel::WindowManagement::WindowId const &>(
          &v54,
          v55,
          &v48);
      }
      else
      {
        *(_DWORD *)v55 = v24;
        v55 += 4;
      }
      v22 += 3;
    }
    v25 = (void **)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_WinXMenuEnumerationTest,_tip_WinXMenuEnumerationTest>>::operator->(
                                 (char *)this + 408,
                                 &v46)
                  + 280LL);
    if ( v25 != (void **)&v54 )
      std::vector<unsigned long>::_Assign_counted_range<unsigned long *>(v25, v54, (v55 - v54) >> 2);
    tip2::test_data_control<tip2::details::merged_data<_tip_WinXMenuEnumerationTest,_tip_WinXMenuEnumerationTest>>::~test_data_control<tip2::details::merged_data<_tip_WinXMenuEnumerationTest,_tip_WinXMenuEnumerationTest>>(&v46);
    if ( v54 )
      std::_Deallocate<16>(v54, (v56 - v54) & 0xFFFFFFFFFFFFFFFCuLL);
  }
  LOBYTE(v21) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WinXReplaceTerminalWithPowerShell_37536857>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_Servicing_WinXReplaceTerminalWithPowerShell_37536857>::GetImpl'::`2'::impl,
    v21);
  v26 = *((_QWORD *)this + 45);
  if ( v26 != *((_QWORD *)this + 46) )
    *((_QWORD *)this + 46) = v26;
  v27 = *((_QWORD *)this + 48);
  if ( v27 != *((_QWORD *)this + 49) )
    *((_QWORD *)this + 49) = v27;
  for ( j = 0; j < *((_QWORD *)this + 23); ++j )
  {
    v29 = (_QWORD *)((char *)this + 176);
    ppv = *(struct IShellItem **)(*((_QWORD *)this + 22) + 8 * j);
    v30 = ppv;
    Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(&ppv);
    if ( ((__int64)v30[14].lpVtbl & 0x100) != 0 )
    {
      CreateRefCountedObj<CLauncherTipContextMenu::LauncherTipMenuCommand,>(&v46);
      v31 = v46;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
        &v46[11],
        v30[11].lpVtbl,
        -1);
      v32 = (__int64)v30[14].lpVtbl & 1;
      LODWORD(v31[14].lpVtbl) = v32 | 0xA02;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
        &v31[2],
        &_ImageBase,
        (unsigned int)(v32 + 10960));
      v33 = *((_QWORD *)this + 23);
      if ( j >= v33 )
        v33 = j;
      v34 = v33 + 1;
      if ( v33 + 1 <= *((_QWORD *)this + 25)
        || (int)CTSimpleArray<Microsoft::WRL::ComPtr<IPlaceModeButtonAcc>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IPlaceModeButtonAcc>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IPlaceModeButtonAcc>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IPlaceModeButtonAcc>>>::_EnsureCapacity(
                  (char *)this + 176,
                  v33 + 1) >= 0 )
      {
        v35 = *((_QWORD *)this + 23);
        if ( j < v35 )
          memmove_0((void *)(*v29 + 8 * j + 8), (const void *)(*v29 + 8 * j), 8 * (v35 - j));
        *((_QWORD *)this + 23) = v34;
        v36 = (IShellItem **)(*v29 + 8 * j);
        if ( v36 )
        {
          *v36 = v31;
          Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(v36);
        }
      }
      ++j;
      if ( v31 )
      {
        v46 = 0;
        ((void (__fastcall *)(IShellItem *))v31->lpVtbl->Release)(v31);
      }
    }
    if ( v30 )
      ((void (__fastcall *)(struct IShellItem *))v30->lpVtbl->Release)(v30);
  }
  if ( Error >= 0 )
  {
    PopupMenu = CreatePopupMenu();
    *((_QWORD *)this + 41) = PopupMenu;
    if ( PopupMenu )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_102;
    }
    v38 = *((_QWORD *)this + 23);
    if ( v38 )
    {
      do
      {
        v39 = *((_QWORD *)this + 22);
        v40 = *(_QWORD *)(v39 + 8 * v38 - 8);
        if ( v40 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v40 + 8LL))(*(_QWORD *)(v39 + 8 * v38 - 8));
        AppendMenuW(*((HMENU *)this + 41), *(_BYTE *)(v40 + 8) != 0 ? 0x800 : 0, v38, *(LPCWSTR *)(v40 + 16));
        if ( v38 == 2 )
        {
          v41 = CreatePopupMenu();
          *((_QWORD *)this + 42) = v41;
          if ( v41 || (Error = ResultFromKnownLastError(), Error >= 0) )
          {
            lpNewItem = 0;
            v52 = 0;
            v53 = 0;
            Error = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
                      &lpNewItem,
                      &_ImageBase,
                      10930);
            if ( Error >= 0 )
              AppendMenuW(*((HMENU *)this + 41), 0x10u, *((unsigned int *)this + 84), lpNewItem);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpNewItem);
          }
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
        --v38;
      }
      while ( v38 );
      if ( ShouldPowershellReplaceCmd() )
      {
        v47[0] = *((_BYTE *)this + 345) == 0;
        LauncherTipContextMenuTelemetry::LauncherTipContextMenuDefaultConsole<bool>(v47);
      }
    }
  }
LABEL_102:
  v42 = (_QWORD *)((char *)this + 408);
  v43 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_WinXMenuEnumerationTest,_tip_WinXMenuEnumerationTest>>::ensure_data((char *)this + 408);
  v46 = (IShellItem *)v43;
  if ( v43 )
    _InterlockedIncrement((volatile signed __int32 *)(v43 + 312));
  tip2::details::shared_data<0,0,1>::begin_update(v43 + 8);
  *(_DWORD *)(v43 + 304) = Error;
  tip2::details::shared_data<0,0,0>::end_update(v43 + 8);
  wil::com_ptr_t<tip2::details::merged_data<_tip_WinXMenuEnumerationTest,_tip_WinXMenuEnumerationTest>,wil::err_returncode_policy>::reset(&v46);
  wil::com_ptr_t<tip2::details::merged_data<_tip_WinXMenuEnumerationTest,_tip_WinXMenuEnumerationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WinXMenuEnumerationTest,_tip_WinXMenuEnumerationTest>,wil::err_returncode_policy>(&v46);
  if ( *v42 )
    tip2::details::shared_data<0,0,0>::complete_without_lock(*v42 + 8LL);
  v44 = psiParent;
  if ( psiParent )
  {
    psiParent = 0;
    ((void (__fastcall *)(IShellItem *))v44->lpVtbl->Release)(v44);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800c8b20  mov     [rsp+arg_8], rbx
0x1800c8b25  mov     [rsp+arg_10], rsi
0x1800c8b2a  push    rdi
0x1800c8b2b  push    r12
0x1800c8b2d  push    r13
0x1800c8b2f  push    r14
0x1800c8b31  push    r15
0x1800c8b33  sub     rsp, 520h
0x1800c8b3a  mov     rax, cs:__security_cookie
0x1800c8b41  xor     rax, rsp
0x1800c8b44  mov     [rsp+548h+var_38], rax
0x1800c8b4c  mov     rsi, rcx
0x1800c8b4f  lea     rcx, [rsp+548h+FileOp]; struct wil::details::IFailureCallback *
0x1800c8b57  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_WinXMenuEnumerationTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x1800c8b5c  lea     r12, [rsi+198h]
0x1800c8b63  mov     rcx, [rax+38h]
0x1800c8b67  mov     rax, [r12]
0x1800c8b6b  mov     [r12], rcx
0x1800c8b6f  xor     r15d, r15d
0x1800c8b72  test    rcx, rcx
0x1800c8b75  jz      short loc_1800C8B7E
0x1800c8b77  lock inc dword ptr [rcx+138h]
0x1800c8b7e  test    rax, rax
0x1800c8b81  jz      short loc_1800C8B8B
0x1800c8b83  mov     rcx, rax; pv
0x1800c8b86  call    ?Release@?$merged_data@U_tip_WinXMenuEnumerationTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_WinXMenuEnumerationTest,_tip_WinXMenuEnumerationTest>::Release(void)
0x1800c8b8b  lea     rcx, [rsp+548h+var_468]
0x1800c8b93  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WinXMenuEnumerationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WinXMenuEnumerationTest,_tip_WinXMenuEnumerationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WinXMenuEnumerationTest,_tip_WinXMenuEnumerationTest>,wil::err_returncode_policy>(void)
0x1800c8b98  lea     rcx, [rsp+548h+FileOp.wFunc]; this
0x1800c8ba0  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800c8ba5  mov     dl, 1
0x1800c8ba7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WinXReplaceTerminalWithPowerShell_37536857@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WinXReplaceTerminalWithPowerShell_37536857@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WinXReplaceTerminalWithPowerShell_37536857> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WinXReplaceTerminalWithPowerShell_37536857>::GetImpl(void)'::`2'::impl
0x1800c8bae  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WinXReplaceTerminalWithPowerShell_37536857@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WinXReplaceTerminalWithPowerShell_37536857>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800c8bb3  mov     [rsi+159h], r15b
0x1800c8bba  lea     rcx, [rsi+15Ah]; void *
0x1800c8bc1  lea     rax, [rcx+3]
0x1800c8bc5  cmp     rax, rcx
0x1800c8bc8  sbb     r8, r8
0x1800c8bcb  not     r8
0x1800c8bce  and     r8d, 3; Size
0x1800c8bd2  cmp     rcx, rax
0x1800c8bd5  ja      short loc_1800C8BDE
0x1800c8bd7  xor     edx, edx; Val
0x1800c8bd9  call    memset_0
0x1800c8bde  mov     [rsp+548h+psiParent], r15
0x1800c8be3  lea     rcx, [rsp+548h+psiParent]
0x1800c8be8  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x1800c8bed  lea     rax, [rsp+548h+psiParent]
0x1800c8bf2  mov     [rsp+548h+ppv], rax; ppv
0x1800c8bf7  lea     r14, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x1800c8bfe  mov     r9, r14; riid
0x1800c8c01  xor     r8d, r8d; hToken
0x1800c8c04  xor     edx, edx; flags
0x1800c8c06  lea     rcx, FOLDERID_LocalAppData; rfid
0x1800c8c0d  call    cs:__imp_SHGetKnownFolderItem
0x1800c8c13  mov     edi, eax
0x1800c8c15  test    eax, eax
0x1800c8c17  js      loc_1800C906F
0x1800c8c1d  mov     [rsp+548h+var_500], r15
0x1800c8c22  lea     rcx, [rsp+548h+var_500]
0x1800c8c27  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x1800c8c2c  lea     rax, [rsp+548h+var_500]
0x1800c8c31  mov     [rsp+548h+ppv], rax; ppv
0x1800c8c36  mov     r9, r14; riid
0x1800c8c39  xor     r8d, r8d; pbc
0x1800c8c3c  lea     r13, pszName; "Microsoft\\Windows\\WinX"
0x1800c8c43  mov     rdx, r13; pszName
0x1800c8c46  mov     rcx, [rsp+548h+psiParent]; psiParent
0x1800c8c4b  call    cs:__imp_SHCreateItemFromRelativeName
0x1800c8c51  mov     edi, eax
0x1800c8c53  cmp     eax, 80070002h
0x1800c8c58  jnz     loc_1800C8EDE
0x1800c8c5e  mov     [rsp+548h+var_518], r15
0x1800c8c63  lea     rcx, [rsp+548h+var_518]
0x1800c8c68  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x1800c8c6d  lea     rax, [rsp+548h+var_518]
0x1800c8c72  mov     [rsp+548h+ppv], rax; ppv
0x1800c8c77  mov     r9, r14; riid
0x1800c8c7a  xor     r8d, r8d; hToken
0x1800c8c7d  xor     edx, edx; flags
0x1800c8c7f  lea     rcx, FOLDERID_UserProfiles; rfid
0x1800c8c86  call    cs:__imp_SHGetKnownFolderItem
0x1800c8c8c  mov     edi, eax
0x1800c8c8e  test    eax, eax
0x1800c8c90  js      loc_1800C8ED4
0x1800c8c96  mov     [rsp+548h+var_508], r15
0x1800c8c9b  lea     rcx, [rsp+548h+var_508]
0x1800c8ca0  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x1800c8ca5  lea     rax, [rsp+548h+var_508]
0x1800c8caa  mov     [rsp+548h+ppv], rax; ppv
0x1800c8caf  mov     r9, r14; riid
0x1800c8cb2  xor     r8d, r8d; pbc
0x1800c8cb5  lea     rdx, aDefaultAppdata; "Default\\AppData\\Local\\Microsoft\\Win"...
0x1800c8cbc  mov     rcx, [rsp+548h+var_518]; psiParent
0x1800c8cc1  call    cs:__imp_SHCreateItemFromRelativeName
0x1800c8cc7  mov     edi, eax
0x1800c8cc9  test    eax, eax
0x1800c8ccb  js      loc_1800C8EC9
0x1800c8cd1  mov     [rsp+548h+lpNewItem], r15
0x1800c8cd6  mov     [rsp+548h+var_4E8], r15
0x1800c8cdb  mov     [rsp+548h+var_4E0], r15
0x1800c8ce0  mov     rdi, [rsp+548h+var_508]
0x1800c8ce5  mov     rax, [rdi]
0x1800c8ce8  mov     rbx, [rax+28h]
0x1800c8cec  lea     rcx, [rsp+548h+lpNewItem]
0x1800c8cf1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800c8cf6  mov     [rsp+548h+var_4E8], 0FFFFFFFFFFFFFFFFh
0x1800c8cff  mov     [rsp+548h+var_4E0], 0FFFFFFFFFFFFFFFFh
0x1800c8d08  lea     r8, [rsp+548h+lpNewItem]
0x1800c8d0d  mov     edx, 80058000h
0x1800c8d12  mov     rcx, rdi
0x1800c8d15  mov     rax, rbx
0x1800c8d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8d1d  mov     edi, eax
0x1800c8d1f  test    eax, eax
0x1800c8d21  js      loc_1800C8EBE
0x1800c8d27  xor     edx, edx; Val
0x1800c8d29  mov     r8d, 208h; Size
0x1800c8d2f  lea     rcx, [rsp+548h+var_458]; void *
0x1800c8d37  call    memset_0
0x1800c8d3c  mov     r8, [rsp+548h+lpNewItem]
0x1800c8d41  mov     edx, 104h
0x1800c8d46  lea     rcx, [rsp+548h+var_458]
0x1800c8d4e  call    cs:__imp__o_wcscpy_s
0x1800c8d54  test    eax, eax
0x1800c8d56  jnz     loc_1800C8EB9
0x1800c8d5c  mov     [rsp+548h+var_4B8], r15
0x1800c8d64  mov     [rsp+548h+var_4B0], r15
0x1800c8d6c  mov     [rsp+548h+var_4A8], r15
0x1800c8d74  mov     rdi, [rsp+548h+psiParent]
0x1800c8d79  mov     rax, [rdi]
0x1800c8d7c  mov     rbx, [rax+28h]
0x1800c8d80  lea     rcx, [rsp+548h+var_4B8]
0x1800c8d88  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800c8d8d  mov     [rsp+548h+var_4B0], 0FFFFFFFFFFFFFFFFh
0x1800c8d99  mov     [rsp+548h+var_4A8], 0FFFFFFFFFFFFFFFFh
0x1800c8da5  lea     r8, [rsp+548h+var_4B8]
0x1800c8dad  mov     edx, 80058000h
0x1800c8db2  mov     rcx, rdi
0x1800c8db5  mov     rax, rbx
0x1800c8db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8dbd  mov     edi, eax
0x1800c8dbf  test    eax, eax
0x1800c8dc1  js      loc_1800C8EAA
0x1800c8dc7  xor     edx, edx; Val
0x1800c8dc9  mov     r8d, 208h; Size
0x1800c8dcf  lea     rcx, [rsp+548h+Buffer]; void *
0x1800c8dd7  call    memset_0
0x1800c8ddc  mov     [rsp+548h+ppv], r13
0x1800c8de1  mov     r9, [rsp+548h+var_4B8]
0x1800c8de9  lea     r8, aSS_0; "%s\\%s"
0x1800c8df0  mov     edx, 104h; BufferCount
0x1800c8df5  lea     rcx, [rsp+548h+Buffer]; Buffer
0x1800c8dfd  call    swprintf_s
0x1800c8e02  test    eax, eax
0x1800c8e04  jle     loc_1800C8EA5
0x1800c8e0a  xorps   xmm0, xmm0
0x1800c8e0d  xor     eax, eax
0x1800c8e0f  movups  xmmword ptr [rsp+548h+FileOp.hwnd], xmm0
0x1800c8e17  movups  xmmword ptr [rsp+548h+FileOp.pFrom], xmm0
0x1800c8e1f  movups  xmmword ptr [rsp+548h+FileOp.fFlags], xmm0
0x1800c8e27  mov     [rsp+548h+FileOp.lpszProgressTitle], rax
0x1800c8e2f  mov     [rsp+548h+FileOp.wFunc], 2
0x1800c8e3a  lea     rax, [rsp+548h+var_458]
0x1800c8e42  mov     [rsp+548h+FileOp.pFrom], rax
0x1800c8e4a  lea     rax, [rsp+548h+Buffer]
0x1800c8e52  mov     [rsp+548h+FileOp.pTo], rax
0x1800c8e5a  mov     eax, 0A04h
0x1800c8e5f  mov     [rsp+548h+FileOp.fFlags], ax
0x1800c8e67  lea     rcx, [rsp+548h+FileOp]; lpFileOp
0x1800c8e6f  call    cs:__imp_SHFileOperationW
0x1800c8e75  test    eax, eax
0x1800c8e77  jnz     short loc_1800C8EA5
0x1800c8e79  lea     rcx, [rsp+548h+var_500]
0x1800c8e7e  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x1800c8e83  lea     rax, [rsp+548h+var_500]
0x1800c8e88  mov     [rsp+548h+ppv], rax; ppv
0x1800c8e8d  mov     r9, r14; riid
0x1800c8e90  xor     r8d, r8d; pbc
0x1800c8e93  mov     rdx, r13; pszName
0x1800c8e96  mov     rcx, [rsp+548h+psiParent]; psiParent
0x1800c8e9b  call    cs:__imp_SHCreateItemFromRelativeName
0x1800c8ea1  mov     edi, eax
0x1800c8ea3  jmp     short loc_1800C8EAA
0x1800c8ea5  mov     edi, 80004005h
0x1800c8eaa  lea     rcx, [rsp+548h+var_4B8]
0x1800c8eb2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800c8eb7  jmp     short loc_1800C8EBE
0x1800c8eb9  mov     edi, 80004005h
0x1800c8ebe  lea     rcx, [rsp+548h+lpNewItem]
0x1800c8ec3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800c8ec8  nop
0x1800c8ec9  lea     rcx, [rsp+548h+var_508]
0x1800c8ece  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x1800c8ed3  nop
0x1800c8ed4  lea     rcx, [rsp+548h+var_518]
0x1800c8ed9  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x1800c8ede  lea     rbx, [rsi+168h]
0x1800c8ee5  mov     rax, [rbx]
0x1800c8ee8  cmp     rax, [rbx+8]
0x1800c8eec  jz      short loc_1800C8EF2
0x1800c8eee  mov     [rbx+8], rax
0x1800c8ef2  mov     r14d, r15d
0x1800c8ef5  lea     r13, __ImageBase
0x1800c8efc  cmp     r14d, 11h
0x1800c8f00  jnb     short loc_1800C8F42
0x1800c8f02  mov     eax, r14d
0x1800c8f05  lea     rcx, [rax+rax*2]
0x1800c8f09  lea     r8, rva ?c_rgItemMap@CLauncherTipContextMenu@@0QBULTCMITEM@1@B[r13]; CLauncherTipContextMenu::LTCMITEM const near * const CLauncherTipContextMenu::c_rgItemMap ...
0x1800c8f10  lea     r8, [r8+rcx*4]
0x1800c8f14  mov     rdx, [rbx+8]
0x1800c8f18  cmp     rdx, [rbx+10h]
0x1800c8f1c  jz      short loc_1800C8F35
0x1800c8f1e  movsd   xmm0, qword ptr [r8]
0x1800c8f23  movsd   qword ptr [rdx], xmm0
0x1800c8f27  mov     eax, [r8+8]
0x1800c8f2b  mov     [rdx+8], eax
0x1800c8f2e  add     qword ptr [rbx+8], 0Ch
0x1800c8f33  jmp     short loc_1800C8F3D
0x1800c8f35  mov     rcx, rbx
0x1800c8f38  call    ??$_Emplace_reallocate@AEBULTCMITEM@CLauncherTipContextMenu@@@?$vector@ULTCMITEM@CLauncherTipContextMenu@@V?$allocator@ULTCMITEM@CLauncherTipContextMenu@@@std@@@std@@AEAAPEAULTCMITEM@CLauncherTipContextMenu@@QEAU23@AEBU23@@Z; std::vector<CLauncherTipContextMenu::LTCMITEM>::_Emplace_reallocate<CLauncherTipContextMenu::LTCMITEM const &>(CLauncherTipContextMenu::LTCMITEM * const,CLauncherTipContextMenu::LTCMITEM const &)
0x1800c8f3d  inc     r14d
0x1800c8f40  jmp     short loc_1800C8EFC
0x1800c8f42  lea     rbx, [rsi+180h]
0x1800c8f49  mov     rdx, [rbx]
0x1800c8f4c  cmp     rdx, [rbx+8]
0x1800c8f50  jz      short loc_1800C8F58
0x1800c8f52  mov     [rbx+8], rdx
0x1800c8f56  jmp     short loc_1800C8F5C
0x1800c8f58  mov     rdx, [rbx+8]
0x1800c8f5c  mov     dword ptr [rsp+548h+var_508], r15d
0x1800c8f61  cmp     rdx, [rbx+10h]
0x1800c8f65  jz      short loc_1800C8F71
0x1800c8f67  mov     [rdx], r15d
0x1800c8f6a  add     qword ptr [rbx+8], 4
0x1800c8f6f  jmp     short loc_1800C8F7E
0x1800c8f71  lea     r8, [rsp+548h+var_508]
0x1800c8f76  mov     rcx, rbx
0x1800c8f79  call    ??$_Emplace_reallocate@I@?$vector@IV?$allocator@I@std@@@std@@AEAAPEAIQEAI$$QEAI@Z; std::vector<uint>::_Emplace_reallocate<uint>(uint * const,uint &&)
0x1800c8f7e  test    edi, edi
0x1800c8f80  js      loc_1800C9057
0x1800c8f86  mov     r8d, 20h ; ' '; unsigned int
0x1800c8f8c  mov     rdx, [rsp+548h+var_500]; struct IShellItem *
0x1800c8f91  lea     rcx, [rsp+548h+lpNewItem]; this
0x1800c8f96  call    ??0CShallowContainerIterator@@QEAA@PEAUIShellItem@@K@Z; CShallowContainerIterator::CShallowContainerIterator(IShellItem *,ulong)
0x1800c8f9b  nop
0x1800c8f9c  mov     edi, dword ptr [rsp+548h+lpNewItem]
0x1800c8fa0  test    edi, edi
0x1800c8fa2  js      loc_1800C904C
0x1800c8fa8  mov     r14d, r15d
0x1800c8fab  mov     [rsp+548h+var_518], r15
0x1800c8fb0  test    edi, edi
0x1800c8fb2  js      loc_1800C9041
0x1800c8fb8  lea     rcx, [rsp+548h+var_518]
0x1800c8fbd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c8fc2  lea     rdx, [rsp+548h+var_518]; struct IShellItem2 **
0x1800c8fc7  lea     rcx, [rsp+548h+lpNewItem]; this
0x1800c8fcc  call    ?Next@CShallowContainerIterator@@QEAA_NPEAPEAUIShellItem2@@@Z; CShallowContainerIterator::Next(IShellItem2 * *)
0x1800c8fd1  test    al, al
0x1800c8fd3  jz      short loc_1800C9041
0x1800c8fd5  cmp     [rsi+0B8h], r15
0x1800c8fdc  jbe     short loc_1800C9013
0x1800c8fde  mov     rcx, rsi; this
0x1800c8fe1  call    ?_AddSeparator@CLauncherTipContextMenu@@AEAAXXZ; CLauncherTipContextMenu::_AddSeparator(void)
0x1800c8fe6  mov     eax, [rsi+0B8h]
0x1800c8fec  mov     dword ptr [rsp+548h+var_508], eax
0x1800c8ff0  mov     rdx, [rbx+8]
0x1800c8ff4  cmp     rdx, [rbx+10h]
0x1800c8ff8  jz      short loc_1800C9003
0x1800c8ffa  mov     [rdx], eax
0x1800c8ffc  add     qword ptr [rbx+8], 4
0x1800c9001  jmp     short loc_1800C9010
0x1800c9003  lea     r8, [rsp+548h+var_508]
0x1800c9008  mov     rcx, rbx
0x1800c900b  call    ??$_Emplace_reallocate@I@?$vector@IV?$allocator@I@std@@@std@@AEAAPEAIQEAI$$QEAI@Z; std::vector<uint>::_Emplace_reallocate<uint>(uint * const,uint &&)
0x1800c9010  inc     r14d
0x1800c9013  mov     r9d, r14d; unsigned int
0x1800c9016  xor     r8d, r8d; bool
0x1800c9019  mov     rdx, [rsp+548h+var_518]; struct IShellItem2 *
0x1800c901e  mov     rcx, rsi; this
0x1800c9021  call    ?_AddFolderLinksToCommands@CLauncherTipContextMenu@@AEAAJPEAUIShellItem2@@_NI@Z; CLauncherTipContextMenu::_AddFolderLinksToCommands(IShellItem2 *,bool,uint)
0x1800c9026  mov     edi, eax
0x1800c9028  test    eax, eax
0x1800c902a  js      short loc_1800C8FB0
0x1800c902c  mov     al, [rsi+142h]
0x1800c9032  neg     al
0x1800c9034  sbb     edi, edi
0x1800c9036  and     edi, 80004004h
0x1800c903c  jmp     loc_1800C8FB0
0x1800c9041  lea     rcx, [rsp+548h+var_518]
0x1800c9046  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c904b  nop
0x1800c904c  lea     rcx, [rsp+548h+lpNewItem]; this
0x1800c9051  call    ??1CShallowContainerIterator@@QEAA@XZ; CShallowContainerIterator::~CShallowContainerIterator(void)
0x1800c9056  nop
0x1800c9057  lea     rcx, [rsp+548h+var_500]
0x1800c905c  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x1800c9061  test    edi, edi
0x1800c9063  js      short loc_1800C9076
0x1800c9065  mov     rcx, rsi; this
  ... truncated ...
```
