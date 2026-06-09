# CMultitaskingViewFrame::CreateFrame(Geometry::CRect const &,MultitaskingViewZOrder)

- ea: `0x1802fbf10`
- end: `0x1802fc9cc`
- name: `?CreateFrame@CMultitaskingViewFrame@@UEAAJAEBUCRect@Geometry@@W4MultitaskingViewZOrder@@@Z`
- size: `2748`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800134f8`
- `0x1800237c8`
- `0x180031c70`
- `0x18008577c`
- `0x18008a6f0`
- `0x1801b7c6c`
- `0x1802bbaf8`
- `0x1802fbf10`
- `0x1802fcb10`
- `0x1802fcb60`
- `0x1802fcbb0`
- `0x180356360`
- `0x180356edc`
- `0x1804fa990`
- `0x1804fb5c4`
- `0x1804fb9ac`
- `0x1804fc584`
- `0x1804fd630`
- `0x1804fd684`
- `0x180505104`
- `0x180507264`
- `0x180507de8`
- `0x1806fa010`

## import_xrefs

- `USER32!RegisterClassExW` at `0x1802fbfa0`
- `USER32!RegisterClassExW` at `0x1802fbfa0`
- `USER32!LoadCursorW` at `0x1802fbf80`
- `USER32!LoadCursorW` at `0x1802fbf80`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x1802fc382`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x1802fc382`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x1802fc0d3`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x1802fc0e6`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x1802fc0d3`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x1802fc0e6`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x1802fc11c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x1802fc98c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x1802fc11c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x1802fc98c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x1802fc159`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x1802fc159`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClientRect` at `0x1802fc730`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClientRect` at `0x1802fc730`
- `api-ms-win-rtcore-ntuser-private-l1-1-0!CreateWindowInBand` at `0x1802fc094`
- `api-ms-win-rtcore-ntuser-private-l1-1-0!CreateWindowInBand` at `0x1802fc094`
- `ext-ms-win-ntuser-private-l1-1-1!SetWindowCompositionAttribute` at `0x1802fc14b`
- `ext-ms-win-ntuser-private-l1-1-1!SetWindowCompositionAttribute` at `0x1802fc14b`
- `ext-ms-win-rtcore-ntuser-dpi-l1-1-0!GetDpiForMonitorInternal` at `0x1802fc18f`
- `ext-ms-win-rtcore-ntuser-dpi-l1-1-0!GetDpiForMonitorInternal` at `0x1802fc18f`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!MonitorFromWindow` at `0x1802fc171`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!MonitorFromWindow` at `0x1802fc343`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!MonitorFromWindow` at `0x1802fc171`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!MonitorFromWindow` at `0x1802fc343`

## string_xrefs

- `0x1802fc6c4`: `pcshell\twinui\multitaskingview\lib\frameelement.cpp`
- `0x1802fbfe5`: `pcshell\twinui\multitaskingview\lib\frame.cpp`
- `0x1802fc0ad`: `pcshell\twinui\multitaskingview\lib\frame.cpp`
- `0x1802fc10c`: `pcshell\twinui\multitaskingview\lib\frame.cpp`
- `0x1802fc245`: `pcshell\twinui\multitaskingview\lib\frame.cpp`
- `0x1802fc276`: `pcshell\twinui\multitaskingview\lib\frame.cpp`
- `0x1802fbf8a`: `MultitaskingViewFrame`
- `0x1802fc08d`: `MultitaskingViewFrame`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CMultitaskingViewFrame::CreateFrame(__int64 a1, _DWORD *a2, int a3)
{
  int v6; // eax
  unsigned int LastError; // ebx
  __int64 v8; // rcx
  int v9; // edi
  int v10; // edx
  const WCHAR *v11; // r8
  HWND WindowInBand; // rax
  const char *v13; // r9
  HWND v14; // r14
  int v15; // eax
  __int64 v16; // rdx
  unsigned int v17; // ebx
  HMONITOR v18; // rax
  struct MultitaskingViewConfig *v19; // r9
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, HWND, __int64, struct ISwitchThumbnailFactory **); // rbx
  int v24; // eax
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, GUID *, _DWORD **); // rbx
  int v27; // eax
  wil::details::in1diag3 *v28; // rcx
  __int64 v29; // rdx
  struct ISwitchThumbnailFactory *v30; // rdi
  __int64 (__fastcall *v31)(struct ISwitchThumbnailFactory *, _QWORD, __int64, GUID *); // rbx
  HMONITOR v32; // rax
  __int64 v33; // rdx
  LONG left; // esi
  LONG top; // ebx
  LONG right; // edi
  int v37; // eax
  int v38; // eax
  __int64 v39; // rdx
  unsigned int v40; // ebx
  int Instance; // eax
  __int64 v42; // rcx
  int v43; // eax
  int v44; // eax
  int v45; // eax
  int v46; // edi
  int v47; // ebx
  _DWORD *v48; // rax
  int v49; // eax
  int v50; // eax
  int v52; // [rsp+20h] [rbp-E0h]
  int *v53; // [rsp+20h] [rbp-E0h]
  int v54; // [rsp+20h] [rbp-E0h]
  int v55; // [rsp+20h] [rbp-E0h]
  int *v56; // [rsp+20h] [rbp-E0h]
  int v57; // [rsp+20h] [rbp-E0h]
  struct _GUID *v58; // [rsp+30h] [rbp-D0h]
  struct ISwitchThumbnailFactory *v59; // [rsp+70h] [rbp-90h] BYREF
  _DWORD *v60; // [rsp+78h] [rbp-88h] BYREF
  int v61[2]; // [rsp+80h] [rbp-80h] BYREF
  int bottom; // [rsp+88h] [rbp-78h] BYREF
  void *v63; // [rsp+90h] [rbp-70h] BYREF
  __int64 v64; // [rsp+98h] [rbp-68h] BYREF
  __int64 v65; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v66; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v67; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v68; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v69; // [rsp+C0h] [rbp-40h] BYREF
  int v70; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v71; // [rsp+D0h] [rbp-30h] BYREF
  int v72[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v73; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD *v74; // [rsp+E8h] [rbp-18h]
  int v75[2]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v76[3]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v77[4]; // [rsp+110h] [rbp+10h] BYREF
  WNDCLASSEXW v78; // [rsp+130h] [rbp+30h] BYREF
  struct tagMONITORINFO mi; // [rsp+180h] [rbp+80h] BYREF
  _QWORD v80[2]; // [rsp+1A8h] [rbp+A8h] BYREF
  struct tagRECT Rect; // [rsp+1B8h] [rbp+B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  v74 = a2;
  v78.cbSize = 80;
  memset_0(&v78.style, 0, 0x4Cu);
  v78.lpfnWndProc = (WNDPROC)CWRLImpWndProc<CMultitaskingViewFrame>::s_WndProcBase;
  v78.hInstance = &_ImageBase;
  v78.hCursor = LoadCursorW(0, (LPCWSTR)0x7F00);
  v78.lpszClassName = L"MultitaskingViewFrame";
  v78.cbWndExtra = 8;
  RegisterClassExW(&v78);
  *(_OWORD *)(a1 + 2552) = *(_OWORD *)a2;
  memset(v77, 0, 24);
  v6 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
         v77,
         &_ImageBase,
         *(unsigned int *)(a1 + 56));
  LastError = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBE,
      (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\frame.cpp",
      (const char *)(unsigned int)v6,
      v52);
    goto LABEL_80;
  }
  if ( a3 == 1 )
  {
    v8 = 2097288;
LABEL_7:
    v10 = 1;
    goto LABEL_10;
  }
  v8 = 2097280;
  v9 = a3 - 2;
  if ( v9 )
  {
    if ( v9 != 1 )
      goto LABEL_7;
    v10 = 16;
  }
  else
  {
    v10 = 5;
  }
LABEL_10:
  v11 = &pvData;
  if ( v77[0] )
    v11 = (const WCHAR *)v77[0];
  WindowInBand = (HWND)CreateWindowInBand(
                         v8,
                         L"MultitaskingViewFrame",
                         v11,
                         0x80000000LL,
                         *a2,
                         a2[1],
                         a2[2] - *a2,
                         a2[3] - a2[1],
                         0,
                         0,
                         &_ImageBase,
                         a1,
                         v10);
  v14 = WindowInBand;
  v77[3] = WindowInBand;
  if ( !WindowInBand )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xD8,
                  (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\frame.cpp",
                  v13);
    goto LABEL_80;
  }
  SetPropW(WindowInBand, L"NonRudeHWND", HANDLE_FLAG_INHERIT);
  SetPropW(v14, L"UIA_WindowPatternEnabled", HANDLE_FLAG_INHERIT);
  v15 = CMultitaskingViewFrame::_CloakWindow((CMultitaskingViewFrame *)a1, 1);
  LastError = v15;
  if ( v15 < 0 )
  {
    v16 = 225;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\frame.cpp",
      (const char *)(unsigned int)v15,
      (int)v53);
LABEL_17:
    DestroyWindow(v14);
    goto LABEL_80;
  }
  v70 = 1;
  v76[0] = 13;
  v76[1] = &v70;
  v76[2] = 4;
  SetWindowCompositionAttribute(*(_QWORD *)(a1 + 48), v76);
  ShowWindow(v14, 8);
  CMultitaskingViewFrame::_EnsureDesktopZOrder((CMultitaskingViewFrame *)a1);
  v17 = 96;
  v18 = MonitorFromWindow(v14, 0);
  if ( v18 )
  {
    bottom = 0;
    LODWORD(v64) = 0;
    if ( (unsigned int)GetDpiForMonitorInternal(v18, 0, &bottom, &v64) )
      v17 = bottom;
  }
  MultitaskingViewConfigHelpers::ScaleMetricsByDPI(
    (MultitaskingViewConfigHelpers *)(a1 + 1240),
    (const struct MultitaskingViewConfig *)v17,
    a1 + 56,
    v19);
  v20 = *(_QWORD *)(a1 + 2488);
  if ( v20 )
  {
    v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 24LL))(v20, a1 + 56);
    LastError = v15;
    if ( v15 < 0 )
    {
      v16 = 256;
      goto LABEL_16;
    }
  }
  v21 = *(_QWORD *)(a1 + 2504);
  if ( v21 )
  {
    v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 24LL))(v21, a1 + 56);
    LastError = v15;
    if ( v15 < 0 )
    {
      v16 = 261;
      goto LABEL_16;
    }
  }
  v59 = 0;
  v22 = *(_QWORD *)(a1 + 2472);
  v23 = *(__int64 (__fastcall **)(__int64, HWND, __int64, struct ISwitchThumbnailFactory **))(*(_QWORD *)v22 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
  v24 = v23(v22, v14, 1, &v59);
  LastError = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10D,
      (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\frame.cpp",
      (const char *)(unsigned int)v24,
      (int)v53);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
    goto LABEL_17;
  }
  *(_QWORD *)v61 = 0;
  v60 = 0;
  v25 = *(_QWORD *)(a1 + 2512);
  if ( v25 )
  {
    v26 = *(__int64 (__fastcall **)(__int64, GUID *, _DWORD **))(*(_QWORD *)v25 + 24LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
    v27 = v26(v25, &GUID_b406b6c5_d8ab_475a_b797_5e5d2d5d22c4, &v60);
    v28 = retaddr;
    if ( v27 < 0 )
    {
      v29 = 273;
LABEL_34:
      wil::details::in1diag3::_Log_Hr(
        v28,
        (void *)v29,
        (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\frame.cpp",
        (const char *)(unsigned int)v27,
        (int)v53);
      goto LABEL_36;
    }
    v30 = v59;
    v31 = *(__int64 (__fastcall **)(struct ISwitchThumbnailFactory *, _QWORD, __int64, GUID *))(*(_QWORD *)v59 + 112LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v61);
    v64 = 0x100000001LL;
    v53 = v61;
    v27 = v31(v30, 0, 0x100000001LL, &GUID_47267895_a4f8_4012_9e98_087c619e7cfc);
    v28 = retaddr;
    if ( v27 < 0 )
    {
      v29 = 275;
      goto LABEL_34;
    }
    (*(void (__fastcall **)(_DWORD *, struct ISwitchThumbnailFactory *, __int64, _QWORD))(*(_QWORD *)v60 + 80LL))(
      v60,
      v59,
      a1,
      *(_QWORD *)v61);
  }
LABEL_36:
  v32 = MonitorFromWindow(v14, 0);
  if ( !v32 )
  {
    v33 = 283;
LABEL_40:
    LastError = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v33,
      (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\frame.cpp",
      (const char *)0x8007139FLL,
      (int)v53);
    goto LABEL_41;
  }
  mi.cbSize = 40;
  memset(&mi.rcMonitor, 0, 36);
  if ( !GetMonitorInfoW(v32, &mi) )
  {
    v33 = 285;
    goto LABEL_40;
  }
  left = mi.rcMonitor.left;
  top = mi.rcMonitor.top;
  right = mi.rcMonitor.right;
  bottom = mi.rcMonitor.bottom;
  v63 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
  bottom -= top;
  LODWORD(v64) = right - left;
  HIDWORD(v64) = bottom;
  v37 = CSwitchItemGrid_CreateInstance(
          (const struct GridMetrics *)(a1 + 64),
          (const struct Geometry::CSize *)&v64,
          *(struct IElementFactory **)(a1 + 2488),
          v59,
          *(struct ISwitchItemController **)(a1 + 2496),
          *(struct IObservableObjectArray **)(a1 + 2448),
          v58,
          &v63);
  LastError = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x129,
      (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\frame.cpp",
      (const char *)(unsigned int)v37,
      v54);
LABEL_45:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
LABEL_41:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v61);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
    if ( !v14 )
      goto LABEL_80;
    goto LABEL_17;
  }
  v65 = 0;
  v38 = Microsoft::WRL::ComPtr<IScrollViewer>::As<IMultitaskingViewElement>(&v63, &v65);
  LastError = v38;
  if ( v38 < 0 )
  {
    v39 = 300;
LABEL_48:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v39,
      (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\frame.cpp",
      (const char *)(unsigned int)v38,
      v54);
LABEL_49:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
    goto LABEL_45;
  }
  (*(void (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v65 + 392LL))(v65, v60);
  v38 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v63 + 32LL))(v63, *(_QWORD *)(a1 + 2432));
  LastError = v38;
  if ( v38 < 0 )
  {
    v39 = 302;
    goto LABEL_48;
  }
  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v65 + 392LL))(v65, 0);
  v40 = (*(_DWORD *)(a1 + 2424) >> 3) & 1;
  if ( (*(_DWORD *)(a1 + 2424) & 0x40) != 0 )
    v40 |= 4u;
  v67 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
  v55 = *(_DWORD *)(a1 + 60);
  Instance = CScrollViewerHost_CreateInstance(v40, a1 + 408, a1 + 64, a1 + 80);
  LastError = Instance;
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13F,
      (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\frame.cpp",
      (const char *)(unsigned int)Instance,
      v55);
LABEL_56:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
    goto LABEL_49;
  }
  v66 = 0;
  v42 = *(_QWORD *)(a1 + 2448);
  if ( v42 )
  {
    if ( (*(_BYTE *)(a1 + 2424) & 2) != 0 )
    {
      v64 = (__int64)v59;
      *(_QWORD *)v72 = *(_QWORD *)(a1 + 2504);
      v73 = v42;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
      v43 = Microsoft::WRL::Details::MakeAndInitialize<CVirtualDesktopBarElement,IMultitaskingViewElement,VirtualDesktopMetrics &,Geometry::CRect const &,IObservableObjectArray *,IVirtualDesktopElementFactory *,ISwitchThumbnailFactory *>(
              &v66,
              a1 + 744,
              v74,
              &v73);
      LastError = v43;
      if ( v43 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14B,
          (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\frame.cpp",
          (const char *)(unsigned int)v43,
          (int)v72);
LABEL_61:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
        goto LABEL_56;
      }
    }
  }
  v69 = 0;
  v68 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
  v74 = v60;
  v73 = v69;
  *(_QWORD *)v72 = v66;
  v64 = v67;
  *(_QWORD *)v75 = v59;
  v80[0] = v14;
  v56 = v75;
  v44 = Microsoft::WRL::Details::MakeAndInitialize<CMultitaskingViewFrameElement,IMultitaskingViewElement,FrameMetrics const &,HWND__ * &,AsyncFrameEvents const &,ISwitchThumbnailFactory * &,IMultitaskingViewElement * &,IMultitaskingViewElement * &,IMultitaskingViewElement * &,IAnimationCoordinator * &>(
          &v68,
          a1 + 576,
          v80,
          a1 + 2456);
  LastError = v44;
  if ( v44 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3DE,
      (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\frameelement.cpp",
      (const char *)(unsigned int)v44,
      (int)v75);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x176,
      (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\frame.cpp",
      (const char *)LastError,
      v57);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
    goto LABEL_61;
  }
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v68 + 184LL))(v68, a1 + 8);
  Rect = 0;
  GetClientRect(v14, &Rect);
  (*(void (__fastcall **)(__int64, struct tagRECT *))(*(_QWORD *)v68 + 104LL))(v68, &Rect);
  v45 = ThumbnailHeight::GetForScreenHeight((ThumbnailHeight *)(a1 + 136), bottom);
  v46 = (int)((double)v45 * *(double *)(a1 + 168));
  if ( (*(_BYTE *)(a1 + 2424) & 8) != 0 )
    v47 = v45
        + *(_DWORD *)(a1 + 180)
        + *(_DWORD *)(a1 + 216)
        + *(_DWORD *)(a1 + 220)
        + *(_DWORD *)(a1 + 232)
        + *(_DWORD *)(a1 + 236)
        + *(_DWORD *)(a1 + 436)
        + *(_DWORD *)(a1 + 440)
        + *(_DWORD *)(a1 + 452);
  else
    v47 = v45
        + *(_DWORD *)(a1 + 180)
        + *(_DWORD *)(a1 + 216)
        + *(_DWORD *)(a1 + 220)
        + *(_DWORD *)(a1 + 232)
        + *(_DWORD *)(a1 + 236);
  v48 = (_DWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v67 + 88LL))(v67, v80);
  if ( v48[2] - *v48 < v46 || v48[3] - v48[1] < v47 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v61);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
    if ( v14 )
      DestroyWindow(v14);
    LastError = -2147024809;
  }
  else
  {
    v71 = 0;
    if ( v66 )
    {
      v49 = Microsoft::WRL::ComPtr<IAnimatableMultitaskingViewElement>::As<IVirtualDesktopBarElement>(&v66, &v71);
      if ( v49 >= 0 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 48LL))(v71);
      else
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x186,
          (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\frame.cpp",
          (const char *)(unsigned int)v49,
          (int)v75);
    }
    if ( *(_QWORD *)v61 )
    {
      v50 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)v61 + 152LL))(*(_QWORD *)v61, 0, 0);
      if ( v50 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x18D,
          (unsigned int)"pcshell\\twinui\\multitaskingview\\lib\\frame.cpp",
          (const char *)(unsigned int)v50,
          (int)v56);
    }
    Microsoft::WRL::ComPtr<IWindowArrangementView>::operator=(a1 + 2480, &v59);
    Microsoft::WRL::ComPtr<IApplicationView>::operator=(a1 + 2520, &v68);
    Microsoft::WRL::ComPtr<IApplicationView>::operator=(a1 + 2528, &v67);
    Microsoft::WRL::ComPtr<ISwitchItemGrid>::operator=(a1 + 2536, &v63);
    Microsoft::WRL::ComPtr<IApplicationView>::operator=(a1 + 2544, &v66);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v61);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
    LastError = 0;
  }
LABEL_80:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v77);
  return LastError;
}

```

## disassembly

```asm
0x1802fbf10  mov     [rsp-8+arg_10], rbx
0x1802fbf15  push    rbp
0x1802fbf16  push    rsi
0x1802fbf17  push    rdi
0x1802fbf18  push    r12
0x1802fbf1a  push    r13
0x1802fbf1c  push    r14
0x1802fbf1e  push    r15
0x1802fbf20  lea     rbp, [rsp-0D0h]
0x1802fbf28  sub     rsp, 1D0h
0x1802fbf2f  mov     rax, cs:__security_cookie
0x1802fbf36  xor     rax, rsp
0x1802fbf39  mov     [rbp+100h+var_38], rax
0x1802fbf40  mov     edi, r8d
0x1802fbf43  mov     rsi, rdx
0x1802fbf46  mov     [rbp+100h+var_118], rdx
0x1802fbf4a  mov     r13, rcx
0x1802fbf4d  mov     [rbp+100h+var_D0.cbSize], 50h ; 'P'
0x1802fbf54  xor     edx, edx; Val
0x1802fbf56  lea     r8d, [rdx+4Ch]; Size
0x1802fbf5a  lea     rcx, [rbp+100h+var_D0.style]; void *
0x1802fbf5e  call    memset_0
0x1802fbf63  lea     rax, ?s_WndProcBase@?$CWRLImpWndProc@VCMultitaskingViewFrame@@@@KA_JPEAUHWND__@@I_K_J@Z; CWRLImpWndProc<CMultitaskingViewFrame>::s_WndProcBase(HWND__ *,uint,unsigned __int64,__int64)
0x1802fbf6a  mov     [rbp+100h+var_D0.lpfnWndProc], rax
0x1802fbf6e  lea     rbx, __ImageBase
0x1802fbf75  mov     [rbp+100h+var_D0.hInstance], rbx
0x1802fbf79  mov     edx, 7F00h; lpCursorName
0x1802fbf7e  xor     ecx, ecx; hInstance
0x1802fbf80  call    cs:__imp_LoadCursorW
0x1802fbf86  mov     [rbp+100h+var_D0.hCursor], rax
0x1802fbf8a  lea     rax, aMultitaskingvi_0; "MultitaskingViewFrame"
0x1802fbf91  mov     [rbp+100h+var_D0.lpszClassName], rax
0x1802fbf95  mov     [rbp+100h+var_D0.cbWndExtra], 8
0x1802fbf9c  lea     rcx, [rbp+100h+var_D0]; WNDCLASSEXW *
0x1802fbfa0  call    cs:__imp_RegisterClassExW
0x1802fbfa6  movups  xmm0, xmmword ptr [rsi]
0x1802fbfa9  movdqu  xmmword ptr [r13+9F8h], xmm0
0x1802fbfb2  xor     r14d, r14d
0x1802fbfb5  mov     [rbp+100h+var_F0], r14
0x1802fbfb9  mov     [rbp+100h+var_E8], r14
0x1802fbfbd  mov     [rbp+100h+var_E0], r14
0x1802fbfc1  lea     r12, [r13+38h]
0x1802fbfc5  mov     r8d, [r12]
0x1802fbfc9  mov     rdx, rbx
0x1802fbfcc  lea     rcx, [rbp+100h+var_F0]
0x1802fbfd0  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@IG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint,ushort)
0x1802fbfd5  mov     ebx, eax
0x1802fbfd7  test    eax, eax
0x1802fbfd9  jns     short loc_1802FBFFB
0x1802fbfdb  mov     rcx, [rbp+108h]; this
0x1802fbfe2  mov     r9d, eax; char *
0x1802fbfe5  lea     r8, aPcshellTwinuiM_26; "pcshell\\twinui\\multitaskingview\\lib"...
0x1802fbfec  mov     edx, 0BEh; void *
0x1802fbff1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802fbff6  jmp     loc_1802FC997
0x1802fbffb  mov     r15d, 1
0x1802fc001  cmp     edi, r15d
0x1802fc004  jnz     short loc_1802FC00D
0x1802fc006  mov     ecx, 200088h
0x1802fc00b  jmp     short loc_1802FC01C
0x1802fc00d  mov     ecx, 200080h
0x1802fc012  sub     edi, 2
0x1802fc015  jz      short loc_1802FC028
0x1802fc017  cmp     edi, r15d
0x1802fc01a  jz      short loc_1802FC021
0x1802fc01c  mov     edx, r15d
0x1802fc01f  jmp     short loc_1802FC02D
0x1802fc021  mov     edx, 10h
0x1802fc026  jmp     short loc_1802FC02D
0x1802fc028  mov     edx, 5
0x1802fc02d  mov     ebx, [rsi+4]
0x1802fc030  mov     r10d, [rsi+0Ch]
0x1802fc034  sub     r10d, ebx
0x1802fc037  mov     r11d, [rsi]
0x1802fc03a  mov     r9d, [rsi+8]
0x1802fc03e  sub     r9d, r11d
0x1802fc041  mov     rax, [rbp+100h+var_F0]
0x1802fc045  lea     r8, pvData
0x1802fc04c  xor     esi, esi
0x1802fc04e  test    rax, rax
0x1802fc051  cmovnz  r8, rax
0x1802fc055  mov     [rsp+200h+var_1A0], edx
0x1802fc059  mov     [rsp+200h+var_1A8], r13
0x1802fc05e  lea     rax, __ImageBase
0x1802fc065  mov     [rsp+200h+var_1B0], rax
0x1802fc06a  mov     [rsp+200h+var_1B8], rsi
0x1802fc06f  mov     [rsp+200h+var_1C0], rsi
0x1802fc074  mov     dword ptr [rsp+200h+var_1C8], r10d
0x1802fc079  mov     dword ptr [rsp+200h+var_1D0], r9d; struct _GUID *
0x1802fc07e  mov     dword ptr [rsp+200h+var_1D8], ebx
0x1802fc082  mov     dword ptr [rsp+200h+var_1E0], r11d; int
0x1802fc087  mov     r9d, 80000000h
0x1802fc08d  lea     rdx, aMultitaskingvi_0; "MultitaskingViewFrame"
0x1802fc094  call    cs:__imp_CreateWindowInBand
0x1802fc09a  mov     r14, rax
0x1802fc09d  mov     [rbp+100h+var_D8], rax
0x1802fc0a1  test    rax, rax
0x1802fc0a4  jnz     short loc_1802FC0C6
0x1802fc0a6  mov     rcx, [rbp+108h]; this
0x1802fc0ad  lea     r8, aPcshellTwinuiM_26; "pcshell\\twinui\\multitaskingview\\lib"...
0x1802fc0b4  mov     edx, 0D8h; void *
0x1802fc0b9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1802fc0be  nop
0x1802fc0bf  mov     ebx, eax
0x1802fc0c1  jmp     loc_1802FC997
0x1802fc0c6  mov     r8, r15; hData
0x1802fc0c9  lea     rdx, aNonrudehwnd; "NonRudeHWND"
0x1802fc0d0  mov     rcx, r14; hWnd
0x1802fc0d3  call    cs:__imp_SetPropW
0x1802fc0d9  mov     r8, r15; hData
0x1802fc0dc  lea     rdx, aUiaWindowpatte; "UIA_WindowPatternEnabled"
0x1802fc0e3  mov     rcx, r14; hWnd
0x1802fc0e6  call    cs:__imp_SetPropW
0x1802fc0ec  mov     dl, r15b; bool
0x1802fc0ef  mov     rcx, r13; this
0x1802fc0f2  call    ?_CloakWindow@CMultitaskingViewFrame@@AEAAJ_N@Z; CMultitaskingViewFrame::_CloakWindow(bool)
0x1802fc0f7  mov     ebx, eax
0x1802fc0f9  test    eax, eax
0x1802fc0fb  jns     short loc_1802FC127
0x1802fc0fd  mov     edx, 0E1h; void *
0x1802fc102  mov     rcx, [rbp+108h]; this
0x1802fc109  mov     r9d, eax; char *
0x1802fc10c  lea     r8, aPcshellTwinuiM_26; "pcshell\\twinui\\multitaskingview\\lib"...
0x1802fc113  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802fc118  nop
0x1802fc119  mov     rcx, r14; hWnd
0x1802fc11c  call    cs:__imp_DestroyWindow
0x1802fc122  jmp     loc_1802FC997
0x1802fc127  mov     [rbp+100h+var_138], r15d
0x1802fc12b  mov     [rbp+100h+var_108], 0Dh
0x1802fc133  lea     rax, [rbp+100h+var_138]
0x1802fc137  mov     [rbp+100h+var_100], rax
0x1802fc13b  mov     [rbp+100h+var_F8], 4
0x1802fc143  lea     rdx, [rbp+100h+var_108]
0x1802fc147  mov     rcx, [r13+30h]
0x1802fc14b  call    cs:__imp_SetWindowCompositionAttribute
0x1802fc151  mov     edx, 8; nCmdShow
0x1802fc156  mov     rcx, r14; hWnd
0x1802fc159  call    cs:__imp_ShowWindow
0x1802fc15f  mov     rcx, r13; this
0x1802fc162  call    ?_EnsureDesktopZOrder@CMultitaskingViewFrame@@AEAAXXZ; CMultitaskingViewFrame::_EnsureDesktopZOrder(void)
0x1802fc167  mov     ebx, 60h ; '`'
0x1802fc16c  xor     edx, edx; dwFlags
0x1802fc16e  mov     rcx, r14; hwnd
0x1802fc171  call    cs:__imp_MonitorFromWindow
0x1802fc177  test    rax, rax
0x1802fc17a  jz      short loc_1802FC19B
0x1802fc17c  mov     [rbp+100h+var_178], esi
0x1802fc17f  mov     dword ptr [rbp+100h+var_168], esi
0x1802fc182  lea     r9, [rbp+100h+var_168]
0x1802fc186  lea     r8, [rbp+100h+var_178]
0x1802fc18a  xor     edx, edx
0x1802fc18c  mov     rcx, rax
0x1802fc18f  call    cs:__imp_GetDpiForMonitorInternal
0x1802fc195  test    eax, eax
0x1802fc197  cmovnz  ebx, [rbp+100h+var_178]
0x1802fc19b  lea     rcx, [r13+4D8h]; this
0x1802fc1a2  mov     r8, r12; unsigned int
0x1802fc1a5  mov     edx, ebx; struct MultitaskingViewConfig *
0x1802fc1a7  call    ?ScaleMetricsByDPI@MultitaskingViewConfigHelpers@@YAXAEBUMultitaskingViewConfig@@IPEAU2@@Z; MultitaskingViewConfigHelpers::ScaleMetricsByDPI(MultitaskingViewConfig const &,uint,MultitaskingViewConfig *)
0x1802fc1ac  mov     rcx, [r13+9B8h]
0x1802fc1b3  test    rcx, rcx
0x1802fc1b6  jz      short loc_1802FC1D7
0x1802fc1b8  mov     rax, [rcx]
0x1802fc1bb  mov     rdx, r12
0x1802fc1be  mov     rax, [rax+18h]
0x1802fc1c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fc1c7  mov     ebx, eax
0x1802fc1c9  test    eax, eax
0x1802fc1cb  jns     short loc_1802FC1D7
0x1802fc1cd  mov     edx, 100h
0x1802fc1d2  jmp     loc_1802FC102
0x1802fc1d7  mov     rcx, [r13+9C8h]
0x1802fc1de  test    rcx, rcx
0x1802fc1e1  jz      short loc_1802FC202
0x1802fc1e3  mov     rax, [rcx]
0x1802fc1e6  mov     rdx, r12
0x1802fc1e9  mov     rax, [rax+18h]
0x1802fc1ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fc1f2  mov     ebx, eax
0x1802fc1f4  test    eax, eax
0x1802fc1f6  jns     short loc_1802FC202
0x1802fc1f8  mov     edx, 105h
0x1802fc1fd  jmp     loc_1802FC102
0x1802fc202  mov     [rsp+200h+var_190], rsi
0x1802fc207  mov     rdi, [r13+9A8h]
0x1802fc20e  mov     rax, [rdi]
0x1802fc211  mov     rbx, [rax+38h]
0x1802fc215  lea     rcx, [rsp+200h+var_190]
0x1802fc21a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802fc21f  lea     r9, [rsp+200h+var_190]
0x1802fc224  mov     r8d, r15d
0x1802fc227  mov     rdx, r14
0x1802fc22a  mov     rcx, rdi
0x1802fc22d  mov     rax, rbx
0x1802fc230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fc235  mov     ebx, eax
0x1802fc237  test    eax, eax
0x1802fc239  jns     short loc_1802FC266
0x1802fc23b  mov     rcx, [rbp+108h]; this
0x1802fc242  mov     r9d, eax; char *
0x1802fc245  lea     r8, aPcshellTwinuiM_26; "pcshell\\twinui\\multitaskingview\\lib"...
0x1802fc24c  mov     edx, 10Dh; void *
0x1802fc251  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802fc256  nop
0x1802fc257  lea     rcx, [rsp+200h+var_190]
0x1802fc25c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802fc261  jmp     loc_1802FC119
0x1802fc266  mov     qword ptr [rbp+100h+var_180], rsi
0x1802fc26a  mov     [rsp+200h+var_188], rsi
0x1802fc26f  mov     rdi, [r13+9D0h]
0x1802fc276  lea     r15, aPcshellTwinuiM_26; "pcshell\\twinui\\multitaskingview\\lib"...
0x1802fc27d  test    rdi, rdi
0x1802fc280  jz      loc_1802FC33E
0x1802fc286  mov     rax, [rdi]
0x1802fc289  mov     rbx, [rax+18h]
0x1802fc28d  lea     rcx, [rsp+200h+var_188]
0x1802fc292  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802fc297  lea     r8, [rsp+200h+var_188]
0x1802fc29c  lea     rdx, _GUID_b406b6c5_d8ab_475a_b797_5e5d2d5d22c4
0x1802fc2a3  mov     rcx, rdi
0x1802fc2a6  mov     rax, rbx
0x1802fc2a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fc2ae  mov     rcx, [rbp+108h]
0x1802fc2b5  test    eax, eax
0x1802fc2b7  jns     short loc_1802FC2C0
0x1802fc2b9  mov     edx, 111h
0x1802fc2be  jmp     short loc_1802FC314
0x1802fc2c0  mov     rdi, [rsp+200h+var_190]
0x1802fc2c5  mov     rax, [rdi]
0x1802fc2c8  mov     rbx, [rax+70h]
0x1802fc2cc  lea     rcx, [rbp+100h+var_180]
0x1802fc2d0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802fc2d5  mov     dword ptr [rbp+100h+var_168], 1
0x1802fc2dc  mov     dword ptr [rbp+100h+var_168+4], 1
0x1802fc2e3  lea     rax, [rbp+100h+var_180]
0x1802fc2e7  mov     [rsp+200h+var_1E0], rax; int
0x1802fc2ec  lea     r9, _GUID_47267895_a4f8_4012_9e98_087c619e7cfc
0x1802fc2f3  mov     r8, [rbp+100h+var_168]
0x1802fc2f7  xor     edx, edx
0x1802fc2f9  mov     rcx, rdi
0x1802fc2fc  mov     rax, rbx
0x1802fc2ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fc304  mov     rcx, [rbp+108h]; this
0x1802fc30b  test    eax, eax
0x1802fc30d  jns     short loc_1802FC321
0x1802fc30f  mov     edx, 113h; void *
0x1802fc314  mov     r8, r15; unsigned int
0x1802fc317  mov     r9d, eax; char *
0x1802fc31a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1802fc31f  jmp     short loc_1802FC33E
0x1802fc321  mov     rcx, [rsp+200h+var_188]
0x1802fc326  mov     rax, [rcx]
0x1802fc329  mov     r9, qword ptr [rbp+100h+var_180]
0x1802fc32d  mov     r8, r13
0x1802fc330  mov     rdx, [rsp+200h+var_190]
0x1802fc335  mov     rax, [rax+50h]
0x1802fc339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fc33e  xor     edx, edx; dwFlags
0x1802fc340  mov     rcx, r14; hwnd
0x1802fc343  call    cs:__imp_MonitorFromWindow
0x1802fc349  test    rax, rax
0x1802fc34c  jnz     short loc_1802FC355
0x1802fc34e  mov     edx, 11Bh
0x1802fc353  jmp     short loc_1802FC391
0x1802fc355  mov     [rbp+100h+mi.cbSize], 28h ; '('
0x1802fc35f  xorps   xmm0, xmm0
0x1802fc362  xor     ecx, ecx
0x1802fc364  movups  xmmword ptr [rbp+100h+mi.rcMonitor.left], xmm0
0x1802fc36b  movups  xmmword ptr [rbp+100h+mi.rcWork.left], xmm0
0x1802fc372  mov     [rbp+100h+mi.dwFlags], ecx
0x1802fc378  lea     rdx, [rbp+100h+mi]; lpmi
0x1802fc37f  mov     rcx, rax; hMonitor
0x1802fc382  call    cs:__imp_GetMonitorInfoW
0x1802fc388  test    eax, eax
0x1802fc38a  jnz     short loc_1802FC3D7
0x1802fc38c  mov     edx, 11Dh; void *
0x1802fc391  mov     ebx, 8007139Fh
0x1802fc396  mov     r9d, ebx; char *
0x1802fc399  mov     r8, r15; unsigned int
0x1802fc39c  mov     rcx, [rbp+108h]; this
0x1802fc3a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802fc3a8  nop
0x1802fc3a9  lea     rcx, [rsp+200h+var_188]
0x1802fc3ae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802fc3b3  nop
0x1802fc3b4  lea     rcx, [rbp+100h+var_180]
0x1802fc3b8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802fc3bd  nop
0x1802fc3be  lea     rcx, [rsp+200h+var_190]
0x1802fc3c3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802fc3c8  nop
0x1802fc3c9  test    r14, r14
0x1802fc3cc  jz      loc_1802FC997
0x1802fc3d2  jmp     loc_1802FC119
0x1802fc3d7  mov     esi, [rbp+100h+mi.rcMonitor.left]
0x1802fc3dd  mov     ebx, [rbp+100h+mi.rcMonitor.top]
0x1802fc3e3  mov     edi, [rbp+100h+mi.rcMonitor.right]
0x1802fc3e9  mov     edx, [rbp+100h+mi.rcMonitor.bottom]
0x1802fc3ef  mov     [rbp+100h+var_178], edx
  ... truncated ...
```
