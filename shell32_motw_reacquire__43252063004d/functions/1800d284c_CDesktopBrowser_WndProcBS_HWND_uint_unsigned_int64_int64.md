# CDesktopBrowser::_WndProcBS(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800d284c`
- end: `0x1800d3b69`
- name: `?_WndProcBS@CDesktopBrowser@@IEAA_JPEAUHWND__@@I_K_J@Z`
- size: `4893`
- prototype: `__int64 __fastcall(CDesktopBrowser *__hidden this, HWND hWnd, unsigned int, unsigned __int64, LPARAM lParam)`
- caller_count: `1`
- callee_count: `73`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d2750`

## callees

- `0x18000f6cc`
- `0x18000fc30`
- `0x180031fe8`
- `0x1800322a4`
- `0x180078a24`
- `0x1800bd834`
- `0x1800c0c68`
- `0x1800c12cc`
- `0x1800cc680`
- `0x1800d284c`
- `0x18010642c`
- `0x180106be8`
- `0x180106c60`
- `0x1801124bc`
- `0x180126a6c`
- `0x180126cb0`
- `0x180126ebc`
- `0x180129fd4`
- `0x18015e8f8`
- `0x1801602a4`
- `0x18016dc0c`
- `0x18016dcdc`
- `0x18017a144`
- `0x1801825e8`
- `0x1801833e0`
- `0x18018461c`
- `0x1801979ac`
- `0x18019a02c`
- `0x1801b591c`
- `0x1801b5af0`
- `0x1801b5c20`
- `0x1801b5eb0`
- `0x1801b622c`
- `0x1801b89d8`
- `0x1801b95e4`
- `0x1801bcd70`
- `0x1801d15c4`
- `0x1801d6c84`
- `0x1801da8cc`
- `0x1801e99c8`
- `0x1801ec698`
- `0x1801ecc8c`
- `0x1802103a0`
- `0x180249490`
- `0x180492eb0`
- `0x180493010`
- `0x1804934e0`
- `0x180496474`
- `0x18049993c`
- `0x180499f98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d39e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3a42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d39e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3a42`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d39bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d3a15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d39bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d3a15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d2ea4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d2ea4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800d2b8c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800d2b8c`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x1800d2d71`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x1800d2d71`
- `USER32!UpdateWindow` at `0x1800d3aa4`
- `USER32!UpdateWindow` at `0x1800d3aa4`
- `USER32!ReleaseDC` at `0x1800d2e93`
- `USER32!ReleaseDC` at `0x1800d2e93`
- `USER32!GetDC` at `0x1800d2d8e`
- `USER32!GetDC` at `0x1800d2d8e`
- `USER32!IsWindow` at `0x1800d30cb`
- `USER32!IsWindow` at `0x1800d30cb`
- `USER32!RemovePropW` at `0x1800d30b3`
- `USER32!RemovePropW` at `0x1800d30b3`
- `USER32!SetPropW` at `0x1800d2bab`
- `USER32!SetPropW` at `0x1800d2bab`
- `USER32!FillRect` at `0x1800d2a28`
- `USER32!FillRect` at `0x1800d2a28`
- `USER32!SetFocus` at `0x1800d2a9b`
- `USER32!SetFocus` at `0x1800d2a9b`
- `USER32!DestroyWindow` at `0x1800d293d`
- `USER32!DestroyWindow` at `0x1800d293d`
- `USER32!KillTimer` at `0x1800d32ff`
- `USER32!KillTimer` at `0x1800d331c`
- `USER32!KillTimer` at `0x1800d32ff`
- `USER32!KillTimer` at `0x1800d331c`
- `USER32!PostQuitMessage` at `0x1800d310e`
- `USER32!PostQuitMessage` at `0x1800d310e`
- `USER32!PostMessageW` at `0x1800d2f8f`
- `USER32!PostMessageW` at `0x1800d30ec`
- `USER32!PostMessageW` at `0x1800d31e9`
- `USER32!PostMessageW` at `0x1800d2f8f`
- `USER32!PostMessageW` at `0x1800d30ec`
- `USER32!PostMessageW` at `0x1800d31e9`
- `USER32!GetClientRect` at `0x1800d2d3c`
- `USER32!GetClientRect` at `0x1800d2d3c`
- `USER32!GetSystemMetrics` at `0x1800d2cb3`
- `USER32!GetSystemMetrics` at `0x1800d2cc8`
- `USER32!GetSystemMetrics` at `0x1800d2cdd`
- `USER32!GetSystemMetrics` at `0x1800d2cf2`
- `USER32!GetSystemMetrics` at `0x1800d2cb3`
- `USER32!GetSystemMetrics` at `0x1800d2cc8`
- `USER32!GetSystemMetrics` at `0x1800d2cdd`
- `USER32!GetSystemMetrics` at `0x1800d2cf2`
- `USER32!ShowWindow` at `0x1800d2b24`
- `USER32!ShowWindow` at `0x1800d2b24`
- `USER32!SendMessageW` at `0x1800d2a7a`
- `USER32!SendMessageW` at `0x1800d2ac4`
- `USER32!SendMessageW` at `0x1800d2aff`
- `USER32!SendMessageW` at `0x1800d2b64`
- `USER32!SendMessageW` at `0x1800d2fb6`
- `USER32!SendMessageW` at `0x1800d2fdc`
- `USER32!SendMessageW` at `0x1800d319e`
- `USER32!SendMessageW` at `0x1800d34a5`
- `USER32!SendMessageW` at `0x1800d39d9`
- `USER32!SendMessageW` at `0x1800d3a36`
- `USER32!SendMessageW` at `0x1800d2a7a`
- `USER32!SendMessageW` at `0x1800d2ac4`
- `USER32!SendMessageW` at `0x1800d2aff`
- `USER32!SendMessageW` at `0x1800d2b64`
- `USER32!SendMessageW` at `0x1800d2fb6`
- `USER32!SendMessageW` at `0x1800d2fdc`
- `USER32!SendMessageW` at `0x1800d319e`
- `USER32!SendMessageW` at `0x1800d34a5`
- `USER32!SendMessageW` at `0x1800d39d9`
- `USER32!SendMessageW` at `0x1800d3a36`
- `GDI32!GetStockObject` at `0x1800d2a12`
- `GDI32!GetStockObject` at `0x1800d2a12`
- `GDI32!DeleteObject` at `0x1800d2e7d`
- `GDI32!DeleteObject` at `0x1800d2e7d`
- `GDI32!CreateDIBSection` at `0x1800d2dfa`
- `GDI32!CreateDIBSection` at `0x1800d2dfa`
- `GDI32!CreateCompatibleDC` at `0x1800d2e15`
- `GDI32!CreateCompatibleDC` at `0x1800d2e15`
- `GDI32!SelectObject` at `0x1800d2e32`
- `GDI32!SelectObject` at `0x1800d2e5a`
- `GDI32!SelectObject` at `0x1800d2e32`
- `GDI32!SelectObject` at `0x1800d2e5a`
- `GDI32!DeleteDC` at `0x1800d2e6a`
- `GDI32!DeleteDC` at `0x1800d2e6a`
- `GDI32!GetClipBox` at `0x1800d29ee`
- `GDI32!GetClipBox` at `0x1800d29ee`
- `GDI32!SetDCBrushColor` at `0x1800d29ff`
- `GDI32!SetDCBrushColor` at `0x1800d2a39`
- `GDI32!SetDCBrushColor` at `0x1800d29ff`
- `GDI32!SetDCBrushColor` at `0x1800d2a39`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800d3623`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800d3623`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x1800d3726`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x1800d3726`
- `SHCORE!__imp_SHLockShared` at `0x1800d373d`
- `SHCORE!__imp_SHLockShared` at `0x1800d373d`
- `SHCORE!__imp_SHUnlockShared` at `0x1800d3763`
- `SHCORE!__imp_SHUnlockShared` at `0x1800d3763`
- `SHLWAPI!__imp_SHDefWindowProc` at `0x1800d3b36`
- `SHLWAPI!__imp_SHDefWindowProc` at `0x1800d3b36`
- `WTSAPI32!WTSRegisterSessionNotification` at `0x1800d32cb`
- `WTSAPI32!WTSRegisterSessionNotification` at `0x1800d32cb`
- `Windows.Storage!CTaskEnumHKCR_Create` at `0x1800d3340`
- `Windows.Storage!CTaskEnumHKCR_Create` at `0x1800d3340`

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
      if ( (unsigned int)a3 > 0x52F )
      {
        if ( (_DWORD)a3 != 1328 && (_DWORD)a3 != 1329 && (_DWORD)a3 != 1330 )
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
      else if ( (_DWORD)a3 != 1327 )
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
        if ( (unsigned int)(a3 - 1325) > 1 )
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
              (void *)0x1110,
              (unsigned int)"shell\\shell32\\unicpp\\desktop.cpp",
              (const char *)(unsigned int)updated,
              hSection);
          v67 = *((_QWORD *)this + 54);
          CWallpaperRenderer::OnDisplayChanged((CWallpaperRenderer *)(v67 + 88));
          v69 = *(CSlideshow **)(v67 + 552);
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
          if ( LOBYTE(qword_1806F8540[3 * (int)lParam]) )
          {
            v58 = Microsoft::WRL::Details::MakeAndInitialize<LocalServerWrapper,IUnknown,int &>(&v79, &v80);
            v59 = retaddr;
            if ( v58 >= 0 )
              goto LABEL_208;
            v60 = 4474;
          }
          else
          {
            ppvBits = &v80;
            v58 = Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<LocalSTAServerWrapper,IUnknown,_lambda_804e7137b8bf95f75e05b2bffd849b35_>(
                    qword_1806F8540,
                    hWnd,
                    &v79,
                    &ppvBits);
            v59 = retaddr;
            if ( v58 >= 0 )
              goto LABEL_208;
            v60 = 4478;
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
                (void *)0x1185,
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
            CSlideshow::SessionChanged(v54[69], a4);
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
            v52 = CSlideshow::Tick(*((CSlideshow **)ppvBits + 69), 1);
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
          (void *)0xB8C,
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
0x1800d284c  push    rbp
0x1800d284e  push    rbx
0x1800d284f  push    rsi
0x1800d2850  push    rdi
0x1800d2851  push    r12
0x1800d2853  push    r13
0x1800d2855  push    r14
0x1800d2857  push    r15
0x1800d2859  lea     rbp, [rsp-17h]
0x1800d285e  sub     rsp, 0E8h
0x1800d2865  mov     rax, cs:__security_cookie
0x1800d286c  xor     rax, rsp
0x1800d286f  mov     [rbp+4Fh+var_50], rax
0x1800d2873  mov     r14, r9
0x1800d2876  mov     r12d, r8d
0x1800d2879  mov     rsi, rdx
0x1800d287c  mov     [rsp+120h+hWnd], rdx
0x1800d2881  mov     rdi, rcx
0x1800d2884  mov     r15, [rbp+4Fh+lParam]
0x1800d2888  xor     r9d, r9d; __int64
0x1800d288b  mov     ebx, r9d
0x1800d288e  mov     r13d, r9d
0x1800d2891  mov     eax, 3E3h
0x1800d2896  cmp     r8d, eax
0x1800d2899  ja      loc_1800D34E3
0x1800d289f  jz      loc_1800D3448
0x1800d28a5  mov     eax, 82h
0x1800d28aa  cmp     r8d, eax
0x1800d28ad  ja      loc_1800D311F
0x1800d28b3  jz      loc_1800D3098
0x1800d28b9  cmp     r8d, 1Ah
0x1800d28bd  ja      loc_1800D2BF2
0x1800d28c3  jz      loc_1800D2BE3
0x1800d28c9  mov     eax, r8d
0x1800d28cc  sub     eax, 1
0x1800d28cf  jz      loc_1800D2B56
0x1800d28d5  sub     eax, 1
0x1800d28d8  jz      loc_1800D2B4C
0x1800d28de  sub     eax, 3
0x1800d28e1  jz      loc_1800D2B10
0x1800d28e7  sub     eax, 1
0x1800d28ea  jz      loc_1800D2AAC
0x1800d28f0  sub     eax, 1
0x1800d28f3  jz      loc_1800D2A8B
0x1800d28f9  sub     eax, 9
0x1800d28fc  jz      loc_1800D2A6B
0x1800d2902  sub     eax, 4
0x1800d2905  jz      loc_1800D29D7
0x1800d290b  sub     eax, 1
0x1800d290e  jz      short loc_1800D294E
0x1800d2910  cmp     eax, 1
0x1800d2913  jnz     loc_1800D2CA6
0x1800d2919  test    r14, r14
0x1800d291c  jz      loc_1800D2C38
0x1800d2922  mov     rcx, [rcx+2E8h]
0x1800d2929  mov     rax, [rcx]
0x1800d292c  xor     r8d, r8d
0x1800d292f  xor     edx, edx
0x1800d2931  mov     rax, [rax+30h]
0x1800d2935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d293a  mov     rcx, rsi; hWnd
0x1800d293d  call    cs:__imp_DestroyWindow
0x1800d2944  nop     dword ptr [rax+rax+00h]
0x1800d2949  jmp     loc_1800D2C3B
0x1800d294e  call    ?_IsDesktopWallpaperInitialized@CDesktopBrowser@@IEAA_NXZ; CDesktopBrowser::_IsDesktopWallpaperInitialized(void)
0x1800d2953  test    al, al
0x1800d2955  jz      short loc_1800D296A
0x1800d2957  mov     rcx, [rcx+1B0h]
0x1800d295e  add     rcx, 58h ; 'X'; this
0x1800d2962  call    ?Invalidate@CWallpaperRenderer@@QEAAX_N0@Z; CWallpaperRenderer::Invalidate(bool,bool)
0x1800d2967  xor     r9d, r9d
0x1800d296a  cmp     [rdi+0F8h], r9d
0x1800d2971  jnz     short loc_1800D29B7
0x1800d2973  mov     rcx, [rdi+2F0h]
0x1800d297a  test    rcx, rcx
0x1800d297d  jz      short loc_1800D29B7
0x1800d297f  cmp     cs:?g_wallpaperAnimationEnabled@@3_NA, r9b; bool g_wallpaperAnimationEnabled
0x1800d2986  jz      short loc_1800D29A2
0x1800d2988  mov     rax, [rcx]
0x1800d298b  mov     rax, [rax+40h]
0x1800d298f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2994  test    al, al
0x1800d2996  jz      short loc_1800D29A2
0x1800d2998  mov     rcx, rdi; this
0x1800d299b  call    ?_CreateAndFadeWallpaper@CDesktopBrowser@@IEAAJXZ; CDesktopBrowser::_CreateAndFadeWallpaper(void)
0x1800d29a0  jmp     short loc_1800D29B7
0x1800d29a2  mov     rcx, [rdi+2F0h]
0x1800d29a9  mov     rax, [rcx]
0x1800d29ac  xor     edx, edx
0x1800d29ae  mov     rax, [rax+28h]
0x1800d29b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d29b7  mov     rcx, [rdi+98h]
0x1800d29be  test    rcx, rcx
0x1800d29c1  jz      loc_1800D2C3B
0x1800d29c7  mov     r9, r15
0x1800d29ca  mov     r8, r14
0x1800d29cd  mov     edx, 15h
0x1800d29d2  jmp     loc_1800D2A7A
0x1800d29d7  cmp     [rcx+314h], r9b
0x1800d29de  jz      short loc_1800D2A55
0x1800d29e0  xorps   xmm0, xmm0
0x1800d29e3  movups  xmmword ptr [rbp+4Fh+rect.left], xmm0
0x1800d29e7  lea     rdx, [rbp+4Fh+rect]; lprect
0x1800d29eb  mov     rcx, r14; hdc
0x1800d29ee  call    cs:__imp_GetClipBox
0x1800d29f5  nop     dword ptr [rax+rax+00h]
0x1800d29fa  xor     edx, edx; color
0x1800d29fc  mov     rcx, r14; hdc
0x1800d29ff  call    cs:__imp_SetDCBrushColor
0x1800d2a06  nop     dword ptr [rax+rax+00h]
0x1800d2a0b  mov     ebx, eax
0x1800d2a0d  mov     ecx, 12h; i
0x1800d2a12  call    cs:__imp_GetStockObject
0x1800d2a19  nop     dword ptr [rax+rax+00h]
0x1800d2a1e  mov     r8, rax; hbr
0x1800d2a21  lea     rdx, [rbp+4Fh+rect]; lprc
0x1800d2a25  mov     rcx, r14; hDC
0x1800d2a28  call    cs:__imp_FillRect
0x1800d2a2f  nop     dword ptr [rax+rax+00h]
0x1800d2a34  mov     edx, ebx; color
0x1800d2a36  mov     rcx, r14; hdc
0x1800d2a39  call    cs:__imp_SetDCBrushColor
0x1800d2a40  nop     dword ptr [rax+rax+00h]
0x1800d2a45  mov     r8, r14; HDC
0x1800d2a48  mov     rdx, rsi; HWND
0x1800d2a4b  mov     rcx, rdi; this
0x1800d2a4e  call    ?_PaintDesktopWatermarkText@CDesktopBrowser@@IEAAXPEAUHWND__@@PEAUHDC__@@@Z; CDesktopBrowser::_PaintDesktopWatermarkText(HWND__ *,HDC__ *)
0x1800d2a53  jmp     short loc_1800D2A61
0x1800d2a55  add     rcx, 48h ; 'H'; this
0x1800d2a59  mov     r8, r14; HDC
0x1800d2a5c  call    ?PaintWallpaper@CDesktopBrowser@@UEAAJPEAUHWND__@@PEAUHDC__@@@Z; CDesktopBrowser::PaintWallpaper(HWND__ *,HDC__ *)
0x1800d2a61  mov     ebx, 1
0x1800d2a66  jmp     loc_1800D2C3B
0x1800d2a6b  xor     r8d, r8d; wParam
0x1800d2a6e  mov     edx, 556h; Msg
0x1800d2a73  mov     rcx, [rcx+0F0h]; hWnd
0x1800d2a7a  call    cs:__imp_SendMessageW
0x1800d2a81  nop     dword ptr [rax+rax+00h]
0x1800d2a86  jmp     loc_1800D2C3B
0x1800d2a8b  mov     rcx, [rcx+98h]; hWnd
0x1800d2a92  test    rcx, rcx
0x1800d2a95  jz      loc_1800D2C38
0x1800d2a9b  call    cs:__imp_SetFocus
0x1800d2aa2  nop     dword ptr [rax+rax+00h]
0x1800d2aa7  jmp     loc_1800D2C3B
0x1800d2aac  test    r14w, r14w
0x1800d2ab0  jnz     loc_1800D2D02
0x1800d2ab6  mov     edx, 127h; Msg
0x1800d2abb  mov     r8d, 30001h; wParam
0x1800d2ac1  mov     rcx, rsi; hWnd
0x1800d2ac4  call    cs:__imp_SendMessageW
0x1800d2acb  nop     dword ptr [rax+rax+00h]
0x1800d2ad0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59927077@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59927077@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59927077> `wil::Feature<__WilFeatureTraits_Feature_59927077>::GetImpl(void)'::`2'::impl
0x1800d2ad7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59927077@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59927077>::__private_IsEnabled(void)
0x1800d2adc  test    al, al
0x1800d2ade  jz      loc_1800D2D02
0x1800d2ae4  mov     rcx, [rdi+98h]; hWnd
0x1800d2aeb  test    rcx, rcx
0x1800d2aee  jz      loc_1800D2D02
0x1800d2af4  mov     r9, r15; lParam
0x1800d2af7  mov     r8, r14; wParam
0x1800d2afa  mov     edx, 6; Msg
0x1800d2aff  call    cs:__imp_SendMessageW
0x1800d2b06  nop     dword ptr [rax+rax+00h]
0x1800d2b0b  jmp     loc_1800D2D02
0x1800d2b10  mov     esi, 1
0x1800d2b15  cmp     r14, rsi
0x1800d2b18  jnz     short loc_1800D2B30
0x1800d2b1a  lea     edx, [rsi+8]; nCmdShow
0x1800d2b1d  mov     rcx, [rcx+90h]; hWnd
0x1800d2b24  call    cs:__imp_ShowWindow
0x1800d2b2b  nop     dword ptr [rax+rax+00h]
0x1800d2b30  mov     rdx, [rdi+98h]; HWND
0x1800d2b37  call    ?_GetListview@CDesktopBrowser@@IEAAPEAUHWND__@@PEAU2@@Z; CDesktopBrowser::_GetListview(HWND__ *)
0x1800d2b3c  mov     r8, rax; HWND
0x1800d2b3f  mov     rcx, rdi; this
0x1800d2b42  call    ?UpdateViewSize@CDesktopBrowser@@IEAAJ_NPEAUHWND__@@@Z; CDesktopBrowser::UpdateViewSize(bool,HWND__ *)
0x1800d2b47  jmp     loc_1800D2BDC
0x1800d2b4c  call    ?_OnDestroy@CDesktopBrowser@@IEAAJXZ; CDesktopBrowser::_OnDestroy(void)
0x1800d2b51  jmp     loc_1800D2C3B
0x1800d2b56  mov     edx, 127h; Msg
0x1800d2b5b  mov     r8d, 3; wParam
0x1800d2b61  mov     rcx, rsi; hWnd
0x1800d2b64  call    cs:__imp_SendMessageW
0x1800d2b6b  nop     dword ptr [rax+rax+00h]
0x1800d2b70  lea     rsi, [rdi+268h]
0x1800d2b77  mov     r9d, 40h ; '@'; cchBufferMax
0x1800d2b7d  mov     r8, rsi; lpBuffer
0x1800d2b80  mov     edx, 1042h; uID
0x1800d2b85  mov     rcx, cs:g_hinst; hInstance
0x1800d2b8c  call    cs:__imp_LoadStringW
0x1800d2b93  nop     dword ptr [rax+rax+00h]
0x1800d2b98  test    eax, eax
0x1800d2b9a  jz      short loc_1800D2BB7
0x1800d2b9c  mov     r8, rsi; hData
0x1800d2b9f  lea     rdx, aPszdesktoptitl; "pszDesktopTitleW"
0x1800d2ba6  mov     rcx, [rsp+120h+hWnd]; hWnd
0x1800d2bab  call    cs:__imp_SetPropW
0x1800d2bb2  nop     dword ptr [rax+rax+00h]
0x1800d2bb7  mov     rcx, rdi; this
0x1800d2bba  call    ?_OnCreate@CDesktopBrowser@@IEAAJPEBUtagCREATESTRUCTW@@@Z; CDesktopBrowser::_OnCreate(tagCREATESTRUCTW const *)
0x1800d2bbf  test    eax, eax
0x1800d2bc1  jns     short loc_1800D2BD1
0x1800d2bc3  mov     rcx, rdi; this
0x1800d2bc6  call    ?_OnDestroy@CDesktopBrowser@@IEAAJXZ; CDesktopBrowser::_OnDestroy(void)
0x1800d2bcb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800d2bcf  jmp     short loc_1800D2BD7
0x1800d2bd1  mov     r13d, 1
0x1800d2bd7  call    ?UpdateWallpaperGlobals@@YAXXZ; UpdateWallpaperGlobals(void)
0x1800d2bdc  mov     rsi, [rsp+120h+hWnd]
0x1800d2be1  jmp     short loc_1800D2C3B
0x1800d2be3  cmp     r14, 14h
0x1800d2be7  jz      loc_1800D380B
0x1800d2bed  jmp     loc_1800D37FA
0x1800d2bf2  mov     eax, r12d
0x1800d2bf5  sub     eax, 20h ; ' '
0x1800d2bf8  jz      loc_1800D2FFF
0x1800d2bfe  sub     eax, 0Bh
0x1800d2c01  jz      loc_1800D2FC7
0x1800d2c07  sub     eax, 1
0x1800d2c0a  jz      loc_1800D2FC7
0x1800d2c10  sub     eax, 8
0x1800d2c13  jz      loc_1800D2D0D
0x1800d2c19  sub     eax, 12h
0x1800d2c1c  jz      loc_1800D2CAE
0x1800d2c22  sub     eax, 1
0x1800d2c25  jz      short loc_1800D2CA6
0x1800d2c27  sub     eax, 7
0x1800d2c2a  jz      short loc_1800D2C6C
0x1800d2c2c  cmp     eax, 2
0x1800d2c2f  jnz     short loc_1800D2CA6
0x1800d2c31  test    r14, r14
0x1800d2c34  setnz   r13b
0x1800d2c38  mov     rsi, rdx
0x1800d2c3b  cmp     r12d, [rdi+320h]
0x1800d2c42  jnz     loc_1800D3B25
0x1800d2c48  mov     rcx, [rdi+318h]
0x1800d2c4f  test    rcx, rcx
0x1800d2c52  jz      loc_1800D3B45
0x1800d2c58  mov     rax, [rcx]
0x1800d2c5b  mov     edx, r14d
0x1800d2c5e  mov     rax, [rax+40h]
0x1800d2c62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2c67  jmp     loc_1800D3B45
0x1800d2c6c  mov     ecx, [r15+10h]
0x1800d2c70  lea     eax, [rcx+0Ah]
0x1800d2c73  mov     esi, 1
0x1800d2c78  cmp     eax, esi
0x1800d2c7a  ja      short loc_1800D2C9E
0x1800d2c7c  cmp     ecx, 0FFFFFFF7h
0x1800d2c7f  setz    r8b
0x1800d2c83  test    rdi, rdi
0x1800d2c86  lea     rdx, [rdi+10h]
0x1800d2c8a  jnz     short loc_1800D2C8F
0x1800d2c8c  mov     rdx, r9
0x1800d2c8f  lea     rcx, [rdi+88h]
0x1800d2c96  call    ?_ShowHideAppStartingCursor@CAppCursorManager@@IEAAXPEAUIUnknown@@_NW4APPCURSORCONTEXT@@@Z; CAppCursorManager::_ShowHideAppStartingCursor(IUnknown *,bool,APPCURSORCONTEXT)
0x1800d2c9b  xor     r9d, r9d
0x1800d2c9e  mov     rbx, r9
0x1800d2ca1  jmp     loc_1800D2BDC
0x1800d2ca6  mov     r13d, 1
0x1800d2cac  jmp     short loc_1800D2C38
0x1800d2cae  mov     ecx, 4Ch ; 'L'; nIndex
0x1800d2cb3  call    cs:__imp_GetSystemMetrics
0x1800d2cba  nop     dword ptr [rax+rax+00h]
0x1800d2cbf  mov     [r15+10h], eax
0x1800d2cc3  mov     ecx, 4Dh ; 'M'; nIndex
0x1800d2cc8  call    cs:__imp_GetSystemMetrics
0x1800d2ccf  nop     dword ptr [rax+rax+00h]
0x1800d2cd4  mov     [r15+14h], eax
0x1800d2cd8  mov     ecx, 4Eh ; 'N'; nIndex
0x1800d2cdd  call    cs:__imp_GetSystemMetrics
0x1800d2ce4  nop     dword ptr [rax+rax+00h]
0x1800d2ce9  mov     [r15+18h], eax
0x1800d2ced  mov     ecx, 4Fh ; 'O'; nIndex
0x1800d2cf2  call    cs:__imp_GetSystemMetrics
0x1800d2cf9  nop     dword ptr [rax+rax+00h]
0x1800d2cfe  mov     [r15+1Ch], eax
0x1800d2d02  mov     r13d, 1
0x1800d2d08  jmp     loc_1800D2C3B
0x1800d2d0d  mov     rax, r14
0x1800d2d10  sub     rax, 4
0x1800d2d14  jz      loc_1800D2EBF
0x1800d2d1a  sub     rax, 1
0x1800d2d1e  jz      loc_1800D2EB5
0x1800d2d24  cmp     rax, 1
0x1800d2d28  jnz     loc_1800D2F9B
0x1800d2d2e  xorps   xmm0, xmm0
0x1800d2d31  movups  xmmword ptr [rbp+4Fh+rect.left], xmm0
0x1800d2d35  lea     rdx, [rbp+4Fh+rect]; lpRect
0x1800d2d39  mov     rcx, rsi; hWnd
0x1800d2d3c  call    cs:__imp_GetClientRect
0x1800d2d43  nop     dword ptr [rax+rax+00h]
0x1800d2d48  mov     ecx, [rbp+4Fh+rect.bottom]
0x1800d2d4b  sub     ecx, [rbp+4Fh+rect.top]
0x1800d2d4e  mov     eax, [rbp+4Fh+rect.right]
0x1800d2d51  sub     eax, [rbp+4Fh+rect.left]
0x1800d2d54  imul    ecx, eax
0x1800d2d57  shl     ecx, 2
0x1800d2d5a  cmp     ecx, r15d
  ... truncated ...
```
