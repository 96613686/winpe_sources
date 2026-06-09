# CDesktopBrowser::_WndProcBS(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800cbc94`
- end: `0x1800cce5f`
- name: `?_WndProcBS@CDesktopBrowser@@IEAA_JPEAUHWND__@@I_K_J@Z`
- size: `4555`
- prototype: `__int64 __fastcall(CDesktopBrowser *__hidden this, HWND hWnd, unsigned int, unsigned __int64, LPARAM lParam)`
- caller_count: `1`
- callee_count: `73`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800cbbb0`

## callees

- `0x18000f05c`
- `0x18000f5a4`
- `0x180074c60`
- `0x18007b398`
- `0x18007b640`
- `0x1800aae20`
- `0x1800ac89c`
- `0x1800b77c8`
- `0x1800b7d04`
- `0x1800c3820`
- `0x1800cbc94`
- `0x1800fe1c4`
- `0x1800fe978`
- `0x1801096ec`
- `0x18011c834`
- `0x180147550`
- `0x180147788`
- `0x18014e5a0`
- `0x18014ffb4`
- `0x18015dc40`
- `0x18015dd08`
- `0x180169118`
- `0x1801711dc`
- `0x1801716b8`
- `0x180172f40`
- `0x1801749a8`
- `0x1801855c0`
- `0x180187980`
- `0x1801a12e8`
- `0x1801a14b0`
- `0x1801a15c0`
- `0x1801a1860`
- `0x1801a1bcc`
- `0x1801a43b4`
- `0x1801a4f7c`
- `0x1801a83d0`
- `0x1801bbd48`
- `0x1801c1084`
- `0x1801c4700`
- `0x1801d29b8`
- `0x1801d54a4`
- `0x1801d5a84`
- `0x1801f9070`
- `0x180233280`
- `0x18045fb40`
- `0x18045fc0c`
- `0x1804600d4`
- `0x180462f2c`
- `0x180465b44`
- `0x180466188`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ccd09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ccd54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ccd09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ccd54`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ccceb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ccd33`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ccceb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ccd33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cc241`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cc241`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800cbf89`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800cbf89`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x1800cc144`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x1800cc144`
- `USER32!UpdateWindow` at `0x1800ccdb0`
- `USER32!UpdateWindow` at `0x1800ccdb0`
- `USER32!ReleaseDC` at `0x1800cc236`
- `USER32!ReleaseDC` at `0x1800cc236`
- `USER32!GetDC` at `0x1800cc15b`
- `USER32!GetDC` at `0x1800cc15b`
- `USER32!IsWindow` at `0x1800cc44a`
- `USER32!IsWindow` at `0x1800cc44a`
- `USER32!RemovePropW` at `0x1800cc438`
- `USER32!RemovePropW` at `0x1800cc438`
- `USER32!SetPropW` at `0x1800cbfa2`
- `USER32!SetPropW` at `0x1800cbfa2`
- `USER32!FillRect` at `0x1800cbe58`
- `USER32!FillRect` at `0x1800cbe58`
- `USER32!SetFocus` at `0x1800cbeb9`
- `USER32!SetFocus` at `0x1800cbeb9`
- `USER32!DestroyWindow` at `0x1800cbd85`
- `USER32!DestroyWindow` at `0x1800cbd85`
- `USER32!KillTimer` at `0x1800cc65a`
- `USER32!KillTimer` at `0x1800cc671`
- `USER32!KillTimer` at `0x1800cc65a`
- `USER32!KillTimer` at `0x1800cc671`
- `USER32!PostQuitMessage` at `0x1800cc481`
- `USER32!PostQuitMessage` at `0x1800cc481`
- `USER32!SendMessageW` at `0x1800cbe9e`
- `USER32!SendMessageW` at `0x1800cbedc`
- `USER32!SendMessageW` at `0x1800cbf11`
- `USER32!SendMessageW` at `0x1800cbf67`
- `USER32!SendMessageW` at `0x1800cc347`
- `USER32!SendMessageW` at `0x1800cc367`
- `USER32!SendMessageW` at `0x1800cc50b`
- `USER32!SendMessageW` at `0x1800cc7ee`
- `USER32!SendMessageW` at `0x1800ccd03`
- `USER32!SendMessageW` at `0x1800ccd4e`
- `USER32!SendMessageW` at `0x1800cbe9e`
- `USER32!SendMessageW` at `0x1800cbedc`
- `USER32!SendMessageW` at `0x1800cbf11`
- `USER32!SendMessageW` at `0x1800cbf67`
- `USER32!SendMessageW` at `0x1800cc347`
- `USER32!SendMessageW` at `0x1800cc367`
- `USER32!SendMessageW` at `0x1800cc50b`
- `USER32!SendMessageW` at `0x1800cc7ee`
- `USER32!SendMessageW` at `0x1800ccd03`
- `USER32!SendMessageW` at `0x1800ccd4e`
- `USER32!PostMessageW` at `0x1800cc326`
- `USER32!PostMessageW` at `0x1800cc465`
- `USER32!PostMessageW` at `0x1800cc550`
- `USER32!PostMessageW` at `0x1800cc326`
- `USER32!PostMessageW` at `0x1800cc465`
- `USER32!PostMessageW` at `0x1800cc550`
- `USER32!GetClientRect` at `0x1800cc115`
- `USER32!GetClientRect` at `0x1800cc115`
- `USER32!GetSystemMetrics` at `0x1800cc0a4`
- `USER32!GetSystemMetrics` at `0x1800cc0b3`
- `USER32!GetSystemMetrics` at `0x1800cc0c2`
- `USER32!GetSystemMetrics` at `0x1800cc0d1`
- `USER32!GetSystemMetrics` at `0x1800cc0a4`
- `USER32!GetSystemMetrics` at `0x1800cc0b3`
- `USER32!GetSystemMetrics` at `0x1800cc0c2`
- `USER32!GetSystemMetrics` at `0x1800cc0d1`
- `USER32!ShowWindow` at `0x1800cbf30`
- `USER32!ShowWindow` at `0x1800cbf30`
- `GDI32!GetStockObject` at `0x1800cbe48`
- `GDI32!GetStockObject` at `0x1800cbe48`
- `GDI32!DeleteObject` at `0x1800cc226`
- `GDI32!DeleteObject` at `0x1800cc226`
- `GDI32!CreateDIBSection` at `0x1800cc1c1`
- `GDI32!CreateDIBSection` at `0x1800cc1c1`
- `GDI32!CreateCompatibleDC` at `0x1800cc1d6`
- `GDI32!CreateCompatibleDC` at `0x1800cc1d6`
- `GDI32!SelectObject` at `0x1800cc1ed`
- `GDI32!SelectObject` at `0x1800cc20f`
- `GDI32!SelectObject` at `0x1800cc1ed`
- `GDI32!SelectObject` at `0x1800cc20f`
- `GDI32!DeleteDC` at `0x1800cc219`
- `GDI32!DeleteDC` at `0x1800cc219`
- `GDI32!GetClipBox` at `0x1800cbe30`
- `GDI32!GetClipBox` at `0x1800cbe30`
- `GDI32!SetDCBrushColor` at `0x1800cbe3b`
- `GDI32!SetDCBrushColor` at `0x1800cbe63`
- `GDI32!SetDCBrushColor` at `0x1800cbe3b`
- `GDI32!SetDCBrushColor` at `0x1800cbe63`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800cc966`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800cc966`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x1800cca63`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x1800cca63`
- `SHCORE!__imp_SHLockShared` at `0x1800cca74`
- `SHCORE!__imp_SHLockShared` at `0x1800cca74`
- `SHCORE!__imp_SHUnlockShared` at `0x1800cca94`
- `SHCORE!__imp_SHUnlockShared` at `0x1800cca94`
- `SHLWAPI!__imp_SHDefWindowProc` at `0x1800cce33`
- `SHLWAPI!__imp_SHDefWindowProc` at `0x1800cce33`
- `WTSAPI32!WTSRegisterSessionNotification` at `0x1800cc62c`
- `WTSAPI32!WTSRegisterSessionNotification` at `0x1800cc62c`
- `Windows.Storage!CTaskEnumHKCR_Create` at `0x1800cc68f`
- `Windows.Storage!CTaskEnumHKCR_Create` at `0x1800cc68f`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall CDesktopBrowser::_WndProcBS(
        CDesktopBrowser *this,
        HWND hWnd,
        __int64 a3,
        unsigned __int64 a4,
        LPARAM lParam)
{
  unsigned int v6; // r12d
  HWND v7; // rsi
  __int64 v9; // r15
  LPARAM v10; // r9
  __int64 v11; // rbx
  BOOL v12; // r13d
  bool v13; // dl
  __int64 v14; // rcx
  bool v15; // r8
  int v16; // r9d
  __int64 v17; // rcx
  HWND v18; // rcx
  WPARAM v19; // r8
  UINT v20; // edx
  COLORREF v21; // ebx
  HBRUSH StockObject; // rax
  HWND v23; // rcx
  HWND v24; // rcx
  HWND Listview; // rax
  bool v26; // dl
  const struct tagCREATESTRUCTW *v27; // rdx
  __int64 v28; // rcx
  int v29; // ecx
  char *v30; // rdx
  HDC DC; // rcx
  HDC CompatibleDC; // rax
  HGDIOBJ v33; // rbx
  bool v34; // dl
  __int64 v35; // r8
  __int64 v36; // rdx
  unsigned __int64 v37; // rdx
  unsigned __int8 v38; // cl
  int v39; // eax
  CMultimonWallpaperState *v40; // rcx
  __int64 v41; // rcx
  HWND v42; // rcx
  HWND v43; // rcx
  LRESULT v44; // rax
  HWND v45; // rcx
  HWND v46; // rcx
  WPARAM v47; // r8
  UINT v48; // edx
  HWND v49; // rcx
  LRESULT v50; // rax
  __int64 v51; // rcx
  unsigned int v52; // eax
  unsigned int v53; // eax
  CSlideshow **v54; // rbx
  HWND v55; // rcx
  int v56; // eax
  _QWORD *v57; // rcx
  int v58; // eax
  wil::details::in1diag3 *v59; // rcx
  __int64 v60; // rdx
  char *v61; // rbx
  int AgileReference; // eax
  ULONG (__stdcall *v63)(PVOID); // rcx
  char *v64; // rax
  void *v65; // rbx
  int updated; // eax
  __int64 v67; // rbx
  int *v68; // r8
  CSlideshow *v69; // rcx
  __int64 v70; // rcx
  bool IsXamlDesktopControllerEnabled; // al
  int hSection; // [rsp+20h] [rbp-B1h]
  char v75[8]; // [rsp+38h] [rbp-99h] BYREF
  HGDIOBJ h; // [rsp+40h] [rbp-91h]
  HDC hdc; // [rsp+48h] [rbp-89h]
  HANDLE hObject; // [rsp+50h] [rbp-81h]
  void *v79; // [rsp+58h] [rbp-79h] BYREF
  HDC v80; // [rsp+60h] [rbp-71h] BYREF
  void *ppvBits; // [rsp+68h] [rbp-69h] BYREF
  struct tagRECT rect; // [rsp+70h] [rbp-61h] BYREF
  BITMAPINFO pbmi; // [rsp+80h] [rbp-51h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+57h]

  v6 = a3;
  v7 = hWnd;
  v9 = lParam;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  if ( (unsigned int)a3 > 0x3E3 )
  {
    if ( (unsigned int)a3 > 0x45C )
    {
      if ( (unsigned int)a3 > 0x530 )
      {
        if ( (_DWORD)a3 != 1329 && (_DWORD)a3 != 1330 )
        {
          switch ( (_DWORD)a3 )
          {
            case 0x533:
              ShowShellInfrastuctureCriticalFailureDialog(a4);
              goto LABEL_63;
            case 0x534:
            case 0x535:
              goto LABEL_62;
            case 0x536:
              IsXamlDesktopControllerEnabled = CDesktopBrowser::IsXamlDesktopControllerEnabled(this);
              CDesktopBrowser::OnDesktopControllerEnableChanged(this, IsXamlDesktopControllerEnabled);
              goto LABEL_63;
            case 0x537:
              CDesktopBrowser::OnGamingExperienceActiveChanged(this);
              goto LABEL_63;
          }
          goto LABEL_71;
        }
      }
      else if ( (_DWORD)a3 != 1328 )
      {
        switch ( (_DWORD)a3 )
        {
          case 0x45D:
            UpdateWindow(hWnd);
            goto LABEL_63;
          case 0x45E:
            CDesktopBrowser::_OnCreateApiSurface(this, a4, lParam);
            goto LABEL_63;
          case 0x460:
            v10 = lParam;
            v19 = a4;
            v20 = 1190;
            v18 = (HWND)*((_QWORD *)this + 19);
            goto LABEL_33;
          case 0x462:
            DesktopWallpaperTelemetry::RestoreMessageRecieved();
            SetLastError(0);
            SendMessageW(*((HWND *)this + 19), 0x4B6u, a4, lParam);
            LODWORD(v80) = GetLastError();
            ppvBits = (void *)*((_QWORD *)this + 19);
            LODWORD(v79) = 0;
            DesktopWallpaperTelemetry::RestoreViewSettings<int,unsigned __int64,unsigned long>(&v79, &ppvBits, &v80);
            SetLastError(0);
            SendMessageW(*((HWND *)this + 18), 0x111u, 0xA220u, 0);
            LODWORD(v79) = GetLastError();
            ppvBits = (void *)*((_QWORD *)this + 18);
            LODWORD(v80) = 1;
            DesktopWallpaperTelemetry::RestoreViewSettings<int,unsigned __int64,unsigned long>(&v80, &ppvBits, &v79);
            goto LABEL_50;
          case 0x466:
            DesktopWallpaperTelemetry::WatchCurrentThread(&pbmi, "Repaint");
            DesktopWallpaperTelemetry::Repaint();
            if ( CDesktopBrowser::_EnsureDesktopWallpaper(this) )
            {
              v70 = *((_QWORD *)this + 94);
              if ( v70 )
                (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v70 + 40LL))(v70, 0);
            }
            v11 = 1;
            wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)&pbmi);
            goto LABEL_50;
          case 0x52C:
            v11 = (int)CDesktopBrowser::_OnWallpaperUpdate(this, a4, lParam);
            goto LABEL_63;
        }
        if ( (_DWORD)a3 != 1325 && (unsigned int)(a3 - 1326) > 1 )
        {
LABEL_71:
          v12 = 1;
          goto LABEL_62;
        }
      }
      if ( !CDesktopBrowser::_EnsureDesktopWallpaper(this) )
        goto LABEL_63;
      v50 = CDesktopWallpaper::HandleSlideshowMessage(*((CDesktopWallpaper **)this + 54), v6, a4, lParam);
      goto LABEL_183;
    }
    if ( (_DWORD)a3 == 1116 )
    {
      CDesktopBrowser::_OnShowDesktopVisuals(this, a4, lParam);
      goto LABEL_63;
    }
    if ( (unsigned int)a3 > 0x44B )
    {
      switch ( (_DWORD)a3 )
      {
        case 0x44C:
          *((_BYTE *)this + 775) = a4 != 0;
          goto LABEL_62;
        case 0x44D:
          CDesktopBrowser::_SaveState(this);
          goto LABEL_63;
        case 0x453:
          CDesktopBrowser::_OnRaise(this, a4, lParam);
          goto LABEL_63;
        case 0x455:
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54572881>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54572881>::GetImpl'::`2'::impl) )
            CDesktopBrowser::CreateSavedWindowsRestoreTabs();
          else
            CDesktopBrowser::_CreateSavedWindows();
          goto LABEL_63;
        case 0x458:
        case 0x459:
          CDesktopBrowser::_OnFocusMsg(this, a3, a4, 0);
          goto LABEL_63;
        case 0x45A:
          CDesktopBrowser::_SetupAppRan(this, (unsigned __int64)hWnd, a3);
          goto LABEL_63;
        case 0x45B:
          CDesktopBrowser::_OnFinalInitialize(this, lParam);
          goto LABEL_63;
      }
      goto LABEL_71;
    }
    switch ( (_DWORD)a3 )
    {
      case 0x44B:
        *((_BYTE *)this + 294) = a4 != 0;
        v9 = 0;
        a4 = 0;
        CDesktopBrowser::_InitMonitors(this);
        if ( CDesktopBrowser::_EnsureDesktopWallpaper(this) )
        {
          updated = CDesktopBrowser::_UpdateWallpaperWindow(this);
          if ( updated < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1121,
              (unsigned int)"shell\\shell32\\unicpp\\desktop.cpp",
              (const char *)(unsigned int)updated,
              hSection);
          v67 = *((_QWORD *)this + 54);
          CWallpaperRenderer::OnDisplayChanged((CWallpaperRenderer *)(v67 + 88));
          v69 = *(CSlideshow **)(v67 + 640);
          if ( v69 )
          {
            *((_BYTE *)v69 + 56) &= 0xCFu;
            CSlideshow::_Refresh(v69, 0, v68);
          }
          v11 = 1;
        }
        goto LABEL_243;
      case 0x3E4:
      case 0x3E5:
      case 0x3E6:
      case 0x3E7:
      case 0x3E8:
LABEL_177:
        v50 = DDEHandleMsgs(*((HWND *)this + 18));
        goto LABEL_183;
      case 0x412:
        CDesktopBrowser::_OnAddToRecent(this, (void *)a4, lParam);
        goto LABEL_63;
      case 0x413:
        v64 = (char *)SHLockShared((HANDLE)a4, lParam);
        v65 = v64;
        if ( v64 )
        {
          *((_DWORD *)v64 + 3) = (unsigned int)SHWaitOp_OperateInternal(
                                                 *((_DWORD *)v64 + 1),
                                                 (const struct _ITEMIDLIST_ABSOLUTE *)(v64 + 20));
          SHUnlockShared(v65);
        }
        v11 = 0;
        goto LABEL_63;
    }
    if ( (_DWORD)a3 != 1046 )
    {
      if ( (_DWORD)a3 != 1048 )
        goto LABEL_71;
      LODWORD(v80) = lParam;
      if ( (unsigned int)lParam > 0x14 )
        goto LABEL_213;
      v57 = (_QWORD *)((char *)this + 8 * (int)lParam + 448);
      if ( a4 )
      {
        if ( !*v57 )
        {
          v79 = 0;
          if ( LOBYTE(qword_1806B7580[3 * (int)lParam]) )
          {
            v58 = Microsoft::WRL::Details::MakeAndInitialize<LocalServerWrapper,IUnknown,int &>(&v79, &v80);
            v59 = retaddr;
            if ( v58 >= 0 )
              goto LABEL_208;
            v60 = 4491;
          }
          else
          {
            ppvBits = &v80;
            v58 = Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<LocalSTAServerWrapper,IUnknown,_lambda_804e7137b8bf95f75e05b2bffd849b35_>(
                    qword_1806B7580,
                    hWnd,
                    &v79,
                    &ppvBits);
            v59 = retaddr;
            if ( v58 >= 0 )
              goto LABEL_208;
            v60 = 4495;
          }
          wil::details::in1diag3::_Log_Hr(
            v59,
            (void *)v60,
            (unsigned int)"shell\\shell32\\unicpp\\desktop.cpp",
            (const char *)(unsigned int)v58,
            hSection);
LABEL_208:
          if ( v79 )
          {
            v61 = (char *)this + 8 * (int)v80;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v61 + 448);
            AgileReference = RoGetAgileReference(1, &IID_IUnknown, v79, v61 + 448);
            if ( AgileReference < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x1196,
                (unsigned int)"shell\\shell32\\unicpp\\desktop.cpp",
                (const char *)(unsigned int)AgileReference,
                hSection);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
        }
      }
      else
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v57);
      }
LABEL_213:
      v11 = 1;
      goto LABEL_50;
    }
    if ( a4 )
    {
      switch ( a4 )
      {
        case 1uLL:
LABEL_223:
          v47 = 0;
          v48 = 1379;
          goto LABEL_180;
        case 2uLL:
          if ( (unsigned int)FindAndSetForegroundWindow(2u) )
            goto LABEL_63;
          v63 = (ULONG (__stdcall *)(PVOID))lambda_ed7adb8822251162338ef5e1df3b2bd6_::_lambda_invoker_cdecl_;
          break;
        case 3uLL:
          v48 = 1379;
          v47 = 2;
          goto LABEL_180;
        case 4uLL:
        case 5uLL:
          v48 = 1379;
          v47 = 1;
          goto LABEL_180;
        case 6uLL:
          goto LABEL_223;
        case 7uLL:
          if ( (unsigned int)FindAndSetForegroundWindow(1u) )
            goto LABEL_63;
          v63 = (ULONG (__stdcall *)(PVOID))lambda_88ce2f2e15fe8a737b1ae6b2a654ef52_::_lambda_invoker_cdecl_;
          break;
        case 8uLL:
          goto LABEL_223;
        default:
          goto LABEL_62;
      }
    }
    else
    {
      if ( (unsigned int)FindAndSetForegroundWindow(0) )
        goto LABEL_63;
      v63 = lambda_856f828d9b2937e4e82d7bd7c54ee067_::_lambda_invoker_cdecl_;
    }
    SHCreateThread(v63, 0, 8u, 0);
    goto LABEL_63;
  }
  if ( (_DWORD)a3 == 995 )
    goto LABEL_177;
  if ( (unsigned int)a3 > 0x82 )
  {
    if ( (unsigned int)a3 <= 0x2B1 )
    {
      switch ( (_DWORD)a3 )
      {
        case 0x2B1:
          if ( !CDesktopBrowser::_EnsureDesktopWallpaper(this) )
            goto LABEL_63;
          v54 = (CSlideshow **)*((_QWORD *)this + 54);
          if ( CDesktopWallpaper::_EnsureSlideshow((CDesktopWallpaper *)v54) )
            CSlideshow::SessionChanged(v54[80], a4);
LABEL_31:
          v11 = 1;
          goto LABEL_63;
        case 0x111:
          CDesktopBrowser::_OnCommand(this, a4, lParam);
          goto LABEL_63;
        case 0x112:
          if ( (a4 & 0xFFF0) == 0xF020 )
            goto LABEL_62;
          v7 = hWnd;
          if ( (a4 & 0xFFF0) == 0xF060 )
            goto LABEL_63;
          goto LABEL_73;
        case 0x113:
          switch ( a4 )
          {
            case 1uLL:
              DDEHandleTimeout(*((_QWORD *)this + 18));
              goto LABEL_63;
            case 2uLL:
              KillTimer(*((HWND *)this + 18), 2u);
              if ( (int)CDesktopBrowser::_InitScheduler(this) >= 0 )
              {
                v79 = 0;
                if ( (int)CTaskEnumHKCR_Create(&v79) >= 0 )
                {
                  (*(void (__fastcall **)(_QWORD, void *, GUID *, _QWORD, int))(**((_QWORD **)this + 55) + 24LL))(
                    *((_QWORD *)this + 55),
                    v79,
                    &CLSID_QueryAssociations,
                    0,
                    0x10000000);
                  (*(void (__fastcall **)(void *))(*(_QWORD *)v79 + 16LL))(v79);
                }
              }
              goto LABEL_63;
            case 4uLL:
              if ( WTSRegisterSessionNotification(hWnd, 0) || (v53 = *((_DWORD *)this + 195), v53 > 3) )
                KillTimer(*((HWND *)this + 18), 4u);
              else
                *((_DWORD *)this + 195) = v53 + 1;
              goto LABEL_63;
          }
          if ( a4 != 11 )
            goto LABEL_71;
          if ( !CDesktopBrowser::_EnsureDesktopWallpaper(this) )
            goto LABEL_63;
          ppvBits = (void *)*((_QWORD *)this + 54);
          if ( CDesktopWallpaper::_EnsureSlideshow((CDesktopWallpaper *)ppvBits) )
            v52 = CSlideshow::Tick(*((CSlideshow **)ppvBits + 80), 1);
          else
            v52 = -2147467259;
          if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
            McTemplateU0q_EtwEventWriteTransfer(v51, Shell32_CDesktopBrowser_Slideshow_Tick_Timer_Info, v52);
          goto LABEL_50;
        case 0x117:
          goto LABEL_143;
        case 0x128:
          goto LABEL_71;
        case 0x211:
        case 0x212:
LABEL_143:
          v18 = (HWND)*((_QWORD *)this + 19);
          if ( !v18 )
            goto LABEL_62;
          v10 = lParam;
          v19 = a4;
          v20 = v6;
LABEL_33:
          SendMessageW(v18, v20, v19, v10);
          goto LABEL_63;
      }
      if ( (_DWORD)a3 != 536 )
      {
        if ( (_DWORD)a3 != 537 )
          goto LABEL_71;
        v46 = (HWND)*((_QWORD *)this + 19);
        if ( v46 )
          SendMessageW(v46, 0x219u, a4, lParam);
        _OnDeviceBroadcast(v46, a4, (const struct _DEV_BROADCAST_HDR *)lParam);
        v12 = 1;
        if ( a4 != 24 && a4 != 32772 && a4 != 0x8000 )
          goto LABEL_63;
        v10 = 0;
        v47 = 0;
        v48 = 1099;
        v49 = (HWND)*((_QWORD *)this + 18);
LABEL_140:
        PostMessageW(v49, v48, v47, v10);
        goto LABEL_63;
      }
      if ( !CDesktopBrowser::_EnsureDesktopWallpaper(this) )
        goto LABEL_63;
      v50 = CDesktopWallpaper::HandlePowerBroadcastMessage(*((CDesktopWallpaper **)this + 54), a4, lParam);
LABEL_183:
      v11 = v50;
      goto LABEL_63;
    }
    if ( (_DWORD)a3 == 736 )
    {
      v56 = CDesktopBrowser::_SaveViewState(this);
      if ( v56 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xB8D,
          (unsigned int)"shell\\shell32\\unicpp\\desktop.cpp",
          (const char *)(unsigned int)v56,
          hSection);
      goto LABEL_63;
    }
    if ( (_DWORD)a3 == 783 || (_DWORD)a3 == 785 )
    {
      v55 = (HWND)*((_QWORD *)this + 19);
      if ( !v55 )
        goto LABEL_71;
      v50 = SendMessageW(v55, a3, a4, lParam);
      goto LABEL_183;
    }
    if ( (_DWORD)a3 != 786 )
    {
      if ( (_DWORD)a3 == 798 )
      {
        UpdateWallpaperGlobals();
        CDesktopBrowser::_UpdateWallpaperWindow(this);
        goto LABEL_63;
      }
      if ( (_DWORD)a3 != 992 && (unsigned int)(a3 - 993) > 1 )
        goto LABEL_71;
      goto LABEL_177;
    }
    v47 = a4 + 500;
    v10 = lParam;
    v48 = 786;
LABEL_180:
    v49 = (HWND)*((_QWORD *)this + 30);
    goto LABEL_140;
  }
  if ( (_DWORD)a3 == 130 )
  {
    CDesktopBrowser::RegisterWindow((CDesktopBrowser *)((char *)this + 64), 1, -1);
    RemovePropW(v7, L"pszDesktopTitleW");
    v45 = (HWND)*((_QWORD *)this + 30);
    if ( v45 && IsWindow(v45) )
      PostMessageW(*((HWND *)this + 30), 0x12u, 0, 0);
    SafeRelease<IUpdatableItemSet>((char *)this + 224);
    CDesktopBrowser::Release(this);
    PostQuitMessage(0);
    goto LABEL_63;
  }
  if ( (unsigned int)a3 > 0x1A )
  {
    if ( (_DWORD)a3 != 32 )
    {
      if ( (_DWORD)a3 == 43 || (_DWORD)a3 == 44 )
      {
        v43 = (HWND)*((_QWORD *)this + 19);
        if ( v43 )
          v44 = SendMessageW(v43, a3, a4, lParam);
        else
          v44 = 0;
        v12 = v44 == 0;
        goto LABEL_63;
      }
      if ( (_DWORD)a3 != 52 )
      {
        if ( (_DWORD)a3 != 70 )
        {
          if ( (_DWORD)a3 != 71 )
          {
            if ( (_DWORD)a3 == 78 )
            {
              v29 = *(_DWORD *)(lParam + 16);
              if ( (unsigned int)(v29 + 10) <= 1 )
              {
                v30 = (char *)this + 16;
                if ( !this )
                  v30 = 0;
                LOBYTE(a3) = v29 == -9;
                CAppCursorManager::_ShowHideAppStartingCursor((char *)this + 136, v30, a3);
              }
              v11 = 0;
              goto LABEL_50;
            }
            if ( (_DWORD)a3 == 80 )
            {
              LOBYTE(v12) = a4 != 0;
LABEL_62:
              v7 = hWnd;
              goto LABEL_63;
            }
          }
          goto LABEL_71;
        }
        *(_DWORD *)(lParam + 16) = GetSystemMetrics(76);
        *(_DWORD *)(lParam + 20) = GetSystemMetrics(77);
        *(_DWORD *)(lParam + 24) = GetSystemMetrics(78);
        *(_DWORD *)(lParam + 28) = GetSystemMetrics(79);
LABEL_73:
        v12 = 1;
        goto LABEL_63;
      }
      switch ( a4 )
      {
        case 4uLL:
          if ( CDesktopBrowser::_EnsureDesktopWallpaper(this) )
          {
            v36 = *((_QWORD *)this + 54);
            if ( lParam )
            {
              v40 = *(CMultimonWallpaperState **)(v36 + 104);
              if ( v40 )
                CMultimonWallpaperState::OnDisplayChanged(v40, (bool *)(v36 + 139));
              if ( !*((_DWORD *)this + 62) )
              {
                v41 = *((_QWORD *)this + 94);
                if ( v41 )
                  (*(void (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v41 + 40LL))(v41, 0, v35, 0);
              }
              break;
            }
            CWallpaperRenderer::UpdateImage((CWallpaperRenderer *)(v36 + 88));
            if ( DesktopPersonalizationTelemetry::IsEnabled(v38, v37) )
              DesktopPersonalizationTelemetry::WallpaperUpdatedViaUpdateImageToSystemSetting();
          }
          if ( !g_wallpaperAnimationEnabled || !*((_DWORD *)this + 62) )
            CDesktopBrowser::_EnsureAutoColorization(this, v34);
          CDesktopBrowser::_HandleSlideshowEnableDisable(this);
          CDesktopBrowser::_OnSystemParametersChanged(this, 0x1Au, 0x14u, 0);
          v39 = *((_DWORD *)this + 192);
          if ( v39 )
            *((_DWORD *)this + 192) = v39 - 1;
          else
            PostMessageW(*((HWND *)this + 18), 0x532u, 2u, 0);
          break;
        case 5uLL:
          CDesktopBrowser::_LoadWallpaper(this);
          break;
        case 6uLL:
          rect = 0;
          GetClientRect(hWnd, &rect);
          if ( 4 * (rect.right - rect.left) * (rect.bottom - rect.top) == (_DWORD)lParam )
          {
            hObject = OpenFileMappingW(0xF001Fu, 0, L"Local\\Microsoft-Windows-DesktopBackground");
            if ( hObject )
            {
              DC = GetDC(v7);
              hdc = DC;
              if ( DC )
              {
                memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
                pbmi.bmiHeader.biSize = 40;
                pbmi.bmiHeader.biWidth = rect.right - rect.left;
                pbmi.bmiHeader.biHeight = rect.bottom - rect.top;
                *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
                ppvBits = 0;
                h = CreateDIBSection(DC, &pbmi, 0, &ppvBits, hObject, 0);
                if ( h )
                {
                  CompatibleDC = CreateCompatibleDC(hdc);
                  v80 = CompatibleDC;
                  if ( CompatibleDC )
                  {
                    v33 = SelectObject(CompatibleDC, h);
                    CDesktopBrowser::PaintWallpaper((CDesktopBrowser *)((char *)this + 72), hWnd, v80);
                    SelectObject(v80, v33);
                    DeleteDC(v80);
                    v11 = 1;
                  }
                  DeleteObject(h);
                }
                ReleaseDC(hWnd, hdc);
              }
              CloseHandle(hObject);
            }
          }
          break;
      }
      v42 = (HWND)*((_QWORD *)this + 19);
      if ( v42 )
        SendMessageW(v42, 0x34u, a4, lParam);
      goto LABEL_50;
    }
    v12 = 1;
    if ( (unsigned __int16)lParam == 10
      || (unsigned __int16)lParam == 11
      || (unsigned __int16)lParam == 12
      || (unsigned __int16)lParam == 13
      || (unsigned __int16)lParam == 14
      || (unsigned __int16)lParam == 15
      || (unsigned int)(unsigned __int16)lParam - 16 < 2 )
    {
      goto LABEL_62;
    }
    v79 = 0;
    if ( CDesktopBrowser::QueryService(
           (CDesktopBrowser *)((char *)this + 16),
           &IID_IWaitCursorManager,
           &GUID_fc992f1f_debb_4596_b355_50c7a6dd1222,
           &v79) >= 0
      && !(*(unsigned int (__fastcall **)(void *))(*(_QWORD *)v79 + 32LL))(v79) )
    {
      v11 = 1;
      v12 = 0;
    }
    ATL::CComPtrBase<IConflictDialogDataMode>::~CComPtrBase<IConflictDialogDataMode>(&v79);
LABEL_50:
    v7 = hWnd;
    goto LABEL_63;
  }
  switch ( (_DWORD)a3 )
  {
    case 0x1A:
      if ( a4 == 20 )
      {
LABEL_244:
        CDesktopBrowser::BroadcastSettingsChanged(this, v75);
        goto LABEL_50;
      }
LABEL_243:
      CDesktopBrowser::_OnSystemParametersChanged(this, v6, a4, v9);
      goto LABEL_244;
    case 1:
      SendMessageW(hWnd, 0x127u, 3u, 0);
      if ( LoadStringW(g_hinst, 0x1042u, (LPWSTR)this + 308, 64) )
        SetPropW(hWnd, L"pszDesktopTitleW", (char *)this + 616);
      if ( (int)CDesktopBrowser::_OnCreate(this, v27) >= 0 )
      {
        v12 = 1;
      }
      else
      {
        CDesktopBrowser::_OnDestroy(this);
        v11 = -1;
      }
      UpdateWallpaperGlobals();
      goto LABEL_50;
    case 2:
      CDesktopBrowser::_OnDestroy(this);
      goto LABEL_63;
    case 5:
      if ( a4 == 1 )
        ShowWindow(*((HWND *)this + 18), 9);
      Listview = CDesktopBrowser::_GetListview(this, *((HWND *)this + 19));
      CDesktopBrowser::UpdateViewSize(this, v26, Listview);
      goto LABEL_50;
    case 6:
      if ( !(_WORD)a4 )
      {
        SendMessageW(hWnd, 0x127u, 0x30001u, 0);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59927077>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59927077>::GetImpl'::`2'::impl) )
        {
          v24 = (HWND)*((_QWORD *)this + 19);
          if ( v24 )
            SendMessageW(v24, 6u, a4, lParam);
        }
      }
      goto LABEL_73;
    case 7:
      v23 = (HWND)*((_QWORD *)this + 19);
      if ( v23 )
      {
        SetFocus(v23);
        goto LABEL_63;
      }
      goto LABEL_62;
    case 0x10:
      v19 = 0;
      v20 = 1366;
      v18 = (HWND)*((_QWORD *)this + 30);
      goto LABEL_33;
    case 0x14:
      if ( *((_BYTE *)this + 788) )
      {
        rect = 0;
        GetClipBox((HDC)a4, &rect);
        v21 = SetDCBrushColor((HDC)a4, 0);
        StockObject = (HBRUSH)GetStockObject(18);
        FillRect((HDC)a4, &rect, StockObject);
        SetDCBrushColor((HDC)a4, v21);
        CDesktopBrowser::_PaintDesktopWatermarkText(this, v7, (HDC)a4);
      }
      else
      {
        CDesktopBrowser::PaintWallpaper((CDesktopBrowser *)((char *)this + 72), hWnd, (HDC)a4);
      }
      goto LABEL_31;
  }
  if ( (_DWORD)a3 != 21 )
  {
    if ( (_DWORD)a3 == 22 )
    {
      if ( a4 )
      {
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 93) + 48LL))(*((_QWORD *)this + 93), 0, 0);
        DestroyWindow(v7);
        goto LABEL_63;
      }
      goto LABEL_62;
    }
    goto LABEL_71;
  }
  if ( CDesktopBrowser::_IsDesktopWallpaperInitialized(this) )
  {
    CWallpaperRenderer::Invalidate((CWallpaperRenderer *)(*(_QWORD *)(v14 + 432) + 88LL), v13, v15);
    v16 = 0;
  }
  if ( *((_DWORD *)this + 62) == v16 )
  {
    v17 = *((_QWORD *)this + 94);
    if ( v17 )
    {
      if ( g_wallpaperAnimationEnabled == (_BYTE)v16
        || !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v17 + 64LL))(v17) )
      {
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 94) + 40LL))(*((_QWORD *)this + 94), 0);
      }
      else
      {
        CDesktopBrowser::_CreateAndFadeWallpaper(this);
      }
    }
  }
  v18 = (HWND)*((_QWORD *)this + 19);
  if ( v18 )
  {
    v10 = lParam;
    v19 = a4;
    v20 = 21;
    goto LABEL_33;
  }
LABEL_63:
  if ( v6 == *((_DWORD *)this + 200) )
  {
    v28 = *((_QWORD *)this + 99);
    if ( v28 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v28 + 64LL))(v28, (unsigned int)a4);
  }
  else if ( v12 )
  {
    return SHDefWindowProc(v7, v6, a4, v9);
  }
  return v11;
}

```

## disassembly

```asm
0x1800cbc94  push    rbp
0x1800cbc96  push    rbx
0x1800cbc97  push    rsi
0x1800cbc98  push    rdi
0x1800cbc99  push    r12
0x1800cbc9b  push    r13
0x1800cbc9d  push    r14
0x1800cbc9f  push    r15
0x1800cbca1  lea     rbp, [rsp-17h]
0x1800cbca6  sub     rsp, 0E8h
0x1800cbcad  mov     rax, cs:__security_cookie
0x1800cbcb4  xor     rax, rsp
0x1800cbcb7  mov     [rbp+4Fh+var_50], rax
0x1800cbcbb  mov     r14, r9
0x1800cbcbe  mov     r12d, r8d
0x1800cbcc1  mov     rsi, rdx
0x1800cbcc4  mov     [rsp+120h+hWnd], rdx
0x1800cbcc9  mov     rdi, rcx
0x1800cbccc  mov     r15, [rbp+4Fh+lParam]
0x1800cbcd0  xor     r9d, r9d; __int64
0x1800cbcd3  mov     ebx, r9d
0x1800cbcd6  mov     r13d, r9d
0x1800cbcd9  mov     eax, 3E3h
0x1800cbcde  cmp     r8d, eax
0x1800cbce1  ja      loc_1800CC826
0x1800cbce7  jz      loc_1800CC791
0x1800cbced  mov     eax, 82h
0x1800cbcf2  cmp     r8d, eax
0x1800cbcf5  ja      loc_1800CC48C
0x1800cbcfb  jz      loc_1800CC41D
0x1800cbd01  cmp     r8d, 1Ah
0x1800cbd05  ja      loc_1800CBFE3
0x1800cbd0b  jz      loc_1800CBFD4
0x1800cbd11  mov     eax, r8d
0x1800cbd14  sub     eax, 1
0x1800cbd17  jz      loc_1800CBF59
0x1800cbd1d  sub     eax, 1
0x1800cbd20  jz      loc_1800CBF4F
0x1800cbd26  sub     eax, 3
0x1800cbd29  jz      loc_1800CBF1C
0x1800cbd2f  sub     eax, 1
0x1800cbd32  jz      loc_1800CBEC4
0x1800cbd38  sub     eax, 1
0x1800cbd3b  jz      loc_1800CBEA9
0x1800cbd41  sub     eax, 9
0x1800cbd44  jz      loc_1800CBE8F
0x1800cbd4a  sub     eax, 4
0x1800cbd4d  jz      loc_1800CBE19
0x1800cbd53  sub     eax, 1
0x1800cbd56  jz      short loc_1800CBD90
0x1800cbd58  cmp     eax, 1
0x1800cbd5b  jnz     loc_1800CC097
0x1800cbd61  test    r14, r14
0x1800cbd64  jz      loc_1800CC029
0x1800cbd6a  mov     rcx, [rcx+2E8h]
0x1800cbd71  mov     rax, [rcx]
0x1800cbd74  xor     r8d, r8d
0x1800cbd77  xor     edx, edx
0x1800cbd79  mov     rax, [rax+30h]
0x1800cbd7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbd82  mov     rcx, rsi; hWnd
0x1800cbd85  call    cs:__imp_DestroyWindow
0x1800cbd8b  jmp     loc_1800CC02C
0x1800cbd90  call    ?_IsDesktopWallpaperInitialized@CDesktopBrowser@@IEAA_NXZ; CDesktopBrowser::_IsDesktopWallpaperInitialized(void)
0x1800cbd95  test    al, al
0x1800cbd97  jz      short loc_1800CBDAC
0x1800cbd99  mov     rcx, [rcx+1B0h]
0x1800cbda0  add     rcx, 58h ; 'X'; this
0x1800cbda4  call    ?Invalidate@CWallpaperRenderer@@QEAAX_N0@Z; CWallpaperRenderer::Invalidate(bool,bool)
0x1800cbda9  xor     r9d, r9d
0x1800cbdac  cmp     [rdi+0F8h], r9d
0x1800cbdb3  jnz     short loc_1800CBDF9
0x1800cbdb5  mov     rcx, [rdi+2F0h]
0x1800cbdbc  test    rcx, rcx
0x1800cbdbf  jz      short loc_1800CBDF9
0x1800cbdc1  cmp     cs:?g_wallpaperAnimationEnabled@@3_NA, r9b; bool g_wallpaperAnimationEnabled
0x1800cbdc8  jz      short loc_1800CBDE4
0x1800cbdca  mov     rax, [rcx]
0x1800cbdcd  mov     rax, [rax+40h]
0x1800cbdd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbdd6  test    al, al
0x1800cbdd8  jz      short loc_1800CBDE4
0x1800cbdda  mov     rcx, rdi; this
0x1800cbddd  call    ?_CreateAndFadeWallpaper@CDesktopBrowser@@IEAAJXZ; CDesktopBrowser::_CreateAndFadeWallpaper(void)
0x1800cbde2  jmp     short loc_1800CBDF9
0x1800cbde4  mov     rcx, [rdi+2F0h]
0x1800cbdeb  mov     rax, [rcx]
0x1800cbdee  xor     edx, edx
0x1800cbdf0  mov     rax, [rax+28h]
0x1800cbdf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbdf9  mov     rcx, [rdi+98h]
0x1800cbe00  test    rcx, rcx
0x1800cbe03  jz      loc_1800CC02C
0x1800cbe09  mov     r9, r15
0x1800cbe0c  mov     r8, r14
0x1800cbe0f  mov     edx, 15h
0x1800cbe14  jmp     loc_1800CBE9E
0x1800cbe19  cmp     [rcx+314h], r9b
0x1800cbe20  jz      short loc_1800CBE79
0x1800cbe22  xorps   xmm0, xmm0
0x1800cbe25  movups  xmmword ptr [rbp+4Fh+rect.left], xmm0
0x1800cbe29  lea     rdx, [rbp+4Fh+rect]; lprect
0x1800cbe2d  mov     rcx, r14; hdc
0x1800cbe30  call    cs:__imp_GetClipBox
0x1800cbe36  xor     edx, edx; color
0x1800cbe38  mov     rcx, r14; hdc
0x1800cbe3b  call    cs:__imp_SetDCBrushColor
0x1800cbe41  mov     ebx, eax
0x1800cbe43  mov     ecx, 12h; i
0x1800cbe48  call    cs:__imp_GetStockObject
0x1800cbe4e  mov     r8, rax; hbr
0x1800cbe51  lea     rdx, [rbp+4Fh+rect]; lprc
0x1800cbe55  mov     rcx, r14; hDC
0x1800cbe58  call    cs:__imp_FillRect
0x1800cbe5e  mov     edx, ebx; color
0x1800cbe60  mov     rcx, r14; hdc
0x1800cbe63  call    cs:__imp_SetDCBrushColor
0x1800cbe69  mov     r8, r14; HDC
0x1800cbe6c  mov     rdx, rsi; HWND
0x1800cbe6f  mov     rcx, rdi; this
0x1800cbe72  call    ?_PaintDesktopWatermarkText@CDesktopBrowser@@IEAAXPEAUHWND__@@PEAUHDC__@@@Z; CDesktopBrowser::_PaintDesktopWatermarkText(HWND__ *,HDC__ *)
0x1800cbe77  jmp     short loc_1800CBE85
0x1800cbe79  add     rcx, 48h ; 'H'; this
0x1800cbe7d  mov     r8, r14; HDC
0x1800cbe80  call    ?PaintWallpaper@CDesktopBrowser@@UEAAJPEAUHWND__@@PEAUHDC__@@@Z; CDesktopBrowser::PaintWallpaper(HWND__ *,HDC__ *)
0x1800cbe85  mov     ebx, 1
0x1800cbe8a  jmp     loc_1800CC02C
0x1800cbe8f  xor     r8d, r8d; wParam
0x1800cbe92  mov     edx, 556h; Msg
0x1800cbe97  mov     rcx, [rcx+0F0h]; hWnd
0x1800cbe9e  call    cs:__imp_SendMessageW
0x1800cbea4  jmp     loc_1800CC02C
0x1800cbea9  mov     rcx, [rcx+98h]; hWnd
0x1800cbeb0  test    rcx, rcx
0x1800cbeb3  jz      loc_1800CC029
0x1800cbeb9  call    cs:__imp_SetFocus
0x1800cbebf  jmp     loc_1800CC02C
0x1800cbec4  test    r14w, r14w
0x1800cbec8  jnz     loc_1800CC0DB
0x1800cbece  mov     edx, 127h; Msg
0x1800cbed3  mov     r8d, 30001h; wParam
0x1800cbed9  mov     rcx, rsi; hWnd
0x1800cbedc  call    cs:__imp_SendMessageW
0x1800cbee2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59927077@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59927077@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59927077> `wil::Feature<__WilFeatureTraits_Feature_59927077>::GetImpl(void)'::`2'::impl
0x1800cbee9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59927077@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59927077>::__private_IsEnabled(void)
0x1800cbeee  test    al, al
0x1800cbef0  jz      loc_1800CC0DB
0x1800cbef6  mov     rcx, [rdi+98h]; hWnd
0x1800cbefd  test    rcx, rcx
0x1800cbf00  jz      loc_1800CC0DB
0x1800cbf06  mov     r9, r15; lParam
0x1800cbf09  mov     r8, r14; wParam
0x1800cbf0c  mov     edx, 6; Msg
0x1800cbf11  call    cs:__imp_SendMessageW
0x1800cbf17  jmp     loc_1800CC0DB
0x1800cbf1c  mov     esi, 1
0x1800cbf21  cmp     r14, rsi
0x1800cbf24  jnz     short loc_1800CBF36
0x1800cbf26  lea     edx, [rsi+8]; nCmdShow
0x1800cbf29  mov     rcx, [rcx+90h]; hWnd
0x1800cbf30  call    cs:__imp_ShowWindow
0x1800cbf36  mov     rdx, [rdi+98h]; HWND
0x1800cbf3d  call    ?_GetListview@CDesktopBrowser@@IEAAPEAUHWND__@@PEAU2@@Z; CDesktopBrowser::_GetListview(HWND__ *)
0x1800cbf42  mov     r8, rax; HWND
0x1800cbf45  mov     rcx, rdi; this
0x1800cbf48  call    ?UpdateViewSize@CDesktopBrowser@@IEAAJ_NPEAUHWND__@@@Z; CDesktopBrowser::UpdateViewSize(bool,HWND__ *)
0x1800cbf4d  jmp     short loc_1800CBFCD
0x1800cbf4f  call    ?_OnDestroy@CDesktopBrowser@@IEAAJXZ; CDesktopBrowser::_OnDestroy(void)
0x1800cbf54  jmp     loc_1800CC02C
0x1800cbf59  mov     edx, 127h; Msg
0x1800cbf5e  mov     r8d, 3; wParam
0x1800cbf64  mov     rcx, rsi; hWnd
0x1800cbf67  call    cs:__imp_SendMessageW
0x1800cbf6d  lea     rsi, [rdi+268h]
0x1800cbf74  mov     r9d, 40h ; '@'; cchBufferMax
0x1800cbf7a  mov     r8, rsi; lpBuffer
0x1800cbf7d  mov     edx, 1042h; uID
0x1800cbf82  mov     rcx, cs:g_hinst; hInstance
0x1800cbf89  call    cs:__imp_LoadStringW
0x1800cbf8f  test    eax, eax
0x1800cbf91  jz      short loc_1800CBFA8
0x1800cbf93  mov     r8, rsi; hData
0x1800cbf96  lea     rdx, aPszdesktoptitl; "pszDesktopTitleW"
0x1800cbf9d  mov     rcx, [rsp+120h+hWnd]; hWnd
0x1800cbfa2  call    cs:__imp_SetPropW
0x1800cbfa8  mov     rcx, rdi; this
0x1800cbfab  call    ?_OnCreate@CDesktopBrowser@@IEAAJPEBUtagCREATESTRUCTW@@@Z; CDesktopBrowser::_OnCreate(tagCREATESTRUCTW const *)
0x1800cbfb0  test    eax, eax
0x1800cbfb2  jns     short loc_1800CBFC2
0x1800cbfb4  mov     rcx, rdi; this
0x1800cbfb7  call    ?_OnDestroy@CDesktopBrowser@@IEAAJXZ; CDesktopBrowser::_OnDestroy(void)
0x1800cbfbc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800cbfc0  jmp     short loc_1800CBFC8
0x1800cbfc2  mov     r13d, 1
0x1800cbfc8  call    ?UpdateWallpaperGlobals@@YAXXZ; UpdateWallpaperGlobals(void)
0x1800cbfcd  mov     rsi, [rsp+120h+hWnd]
0x1800cbfd2  jmp     short loc_1800CC02C
0x1800cbfd4  cmp     r14, 14h
0x1800cbfd8  jz      loc_1800CCB36
0x1800cbfde  jmp     loc_1800CCB25
0x1800cbfe3  mov     eax, r12d
0x1800cbfe6  sub     eax, 20h ; ' '
0x1800cbfe9  jz      loc_1800CC384
0x1800cbfef  sub     eax, 0Bh
0x1800cbff2  jz      loc_1800CC352
0x1800cbff8  sub     eax, 1
0x1800cbffb  jz      loc_1800CC352
0x1800cc001  sub     eax, 8
0x1800cc004  jz      loc_1800CC0E6
0x1800cc00a  sub     eax, 12h
0x1800cc00d  jz      loc_1800CC09F
0x1800cc013  sub     eax, 1
0x1800cc016  jz      short loc_1800CC097
0x1800cc018  sub     eax, 7
0x1800cc01b  jz      short loc_1800CC05D
0x1800cc01d  cmp     eax, 2
0x1800cc020  jnz     short loc_1800CC097
0x1800cc022  test    r14, r14
0x1800cc025  setnz   r13b
0x1800cc029  mov     rsi, rdx
0x1800cc02c  cmp     r12d, [rdi+320h]
0x1800cc033  jnz     loc_1800CCE22
0x1800cc039  mov     rcx, [rdi+318h]
0x1800cc040  test    rcx, rcx
0x1800cc043  jz      loc_1800CCE3C
0x1800cc049  mov     rax, [rcx]
0x1800cc04c  mov     edx, r14d
0x1800cc04f  mov     rax, [rax+40h]
0x1800cc053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc058  jmp     loc_1800CCE3C
0x1800cc05d  mov     ecx, [r15+10h]
0x1800cc061  lea     eax, [rcx+0Ah]
0x1800cc064  mov     esi, 1
0x1800cc069  cmp     eax, esi
0x1800cc06b  ja      short loc_1800CC08F
0x1800cc06d  cmp     ecx, 0FFFFFFF7h
0x1800cc070  setz    r8b
0x1800cc074  test    rdi, rdi
0x1800cc077  lea     rdx, [rdi+10h]
0x1800cc07b  jnz     short loc_1800CC080
0x1800cc07d  mov     rdx, r9
0x1800cc080  lea     rcx, [rdi+88h]
0x1800cc087  call    ?_ShowHideAppStartingCursor@CAppCursorManager@@IEAAXPEAUIUnknown@@_NW4APPCURSORCONTEXT@@@Z; CAppCursorManager::_ShowHideAppStartingCursor(IUnknown *,bool,APPCURSORCONTEXT)
0x1800cc08c  xor     r9d, r9d
0x1800cc08f  mov     rbx, r9
0x1800cc092  jmp     loc_1800CBFCD
0x1800cc097  mov     r13d, 1
0x1800cc09d  jmp     short loc_1800CC029
0x1800cc09f  mov     ecx, 4Ch ; 'L'; nIndex
0x1800cc0a4  call    cs:__imp_GetSystemMetrics
0x1800cc0aa  mov     [r15+10h], eax
0x1800cc0ae  mov     ecx, 4Dh ; 'M'; nIndex
0x1800cc0b3  call    cs:__imp_GetSystemMetrics
0x1800cc0b9  mov     [r15+14h], eax
0x1800cc0bd  mov     ecx, 4Eh ; 'N'; nIndex
0x1800cc0c2  call    cs:__imp_GetSystemMetrics
0x1800cc0c8  mov     [r15+18h], eax
0x1800cc0cc  mov     ecx, 4Fh ; 'O'; nIndex
0x1800cc0d1  call    cs:__imp_GetSystemMetrics
0x1800cc0d7  mov     [r15+1Ch], eax
0x1800cc0db  mov     r13d, 1
0x1800cc0e1  jmp     loc_1800CC02C
0x1800cc0e6  mov     rax, r14
0x1800cc0e9  sub     rax, 4
0x1800cc0ed  jz      loc_1800CC256
0x1800cc0f3  sub     rax, 1
0x1800cc0f7  jz      loc_1800CC24C
0x1800cc0fd  cmp     rax, 1
0x1800cc101  jnz     loc_1800CC32C
0x1800cc107  xorps   xmm0, xmm0
0x1800cc10a  movups  xmmword ptr [rbp+4Fh+rect.left], xmm0
0x1800cc10e  lea     rdx, [rbp+4Fh+rect]; lpRect
0x1800cc112  mov     rcx, rsi; hWnd
0x1800cc115  call    cs:__imp_GetClientRect
0x1800cc11b  mov     ecx, [rbp+4Fh+rect.bottom]
0x1800cc11e  sub     ecx, [rbp+4Fh+rect.top]
0x1800cc121  mov     eax, [rbp+4Fh+rect.right]
0x1800cc124  sub     eax, [rbp+4Fh+rect.left]
0x1800cc127  imul    ecx, eax
0x1800cc12a  shl     ecx, 2
0x1800cc12d  cmp     ecx, r15d
0x1800cc130  jnz     loc_1800CC32C
0x1800cc136  lea     r8, aLocalMicrosoft; "Local\\Microsoft-Windows-DesktopBackgro"...
0x1800cc13d  xor     edx, edx; bInheritHandle
0x1800cc13f  mov     ecx, 0F001Fh; dwDesiredAccess
0x1800cc144  call    cs:__imp_OpenFileMappingW
0x1800cc14a  mov     [rsp+120h+hObject], rax
0x1800cc14f  test    rax, rax
0x1800cc152  jz      loc_1800CC32C
0x1800cc158  mov     rcx, rsi; hWnd
0x1800cc15b  call    cs:__imp_GetDC
0x1800cc161  mov     rcx, rax; hdc
0x1800cc164  mov     [rsp+120h+hdc], rax
0x1800cc169  xor     edx, edx
0x1800cc16b  test    rax, rax
0x1800cc16e  jz      loc_1800CC23C
0x1800cc174  xorps   xmm0, xmm0
0x1800cc177  movdqu  xmmword ptr [rbp+4Fh+pbmi.bmiHeader.biSizeImage], xmm0
0x1800cc17c  mov     qword ptr [rbp+4Fh+pbmi.bmiHeader.biClrImportant], rdx
0x1800cc180  mov     [rbp+4Fh+pbmi.bmiHeader.biSize], 28h ; '('
  ... truncated ...
```
