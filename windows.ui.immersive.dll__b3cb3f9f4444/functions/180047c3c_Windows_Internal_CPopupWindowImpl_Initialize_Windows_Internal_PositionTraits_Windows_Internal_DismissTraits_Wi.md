# Windows::Internal::CPopupWindowImpl::_Initialize(Windows::Internal::PositionTraits *,Windows::Internal::DismissTraits *,Windows::Internal::WindowTraits *,Windows::Internal::AnimationTraits *,HWND__ *,POPUP_PERSONALITY,bool,POPUP_OPTIONS,XamlPopupOptions,HMONITOR__ *)

- ea: `0x180047c3c`
- end: `0x180048921`
- name: `?_Initialize@CPopupWindowImpl@Internal@Windows@@AEAAJPEAUPositionTraits@23@PEAUDismissTraits@23@PEAUWindowTraits@23@PEAUAnimationTraits@23@PEAUHWND__@@W4POPUP_PERSONALITY@@_NW4POPUP_OPTIONS@@W4XamlPopupOptions@@PEAUHMONITOR__@@@Z`
- size: `3301`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18009204c`

## callees

- `0x180013f14`
- `0x18002cf2c`
- `0x1800321c0`
- `0x1800325e4`
- `0x180032744`
- `0x180032d58`
- `0x1800343ec`
- `0x180039820`
- `0x18003a0a8`
- `0x18003d1bc`
- `0x18003e1e0`
- `0x180047c3c`
- `0x180048b3c`
- `0x18004ba4c`
- `0x18004c5bc`
- `0x18004d874`
- `0x18005ec94`
- `0x1800904ec`
- `0x18009080c`
- `0x180090a80`
- `0x1800931c4`
- `0x180093870`
- `0x1800938bc`
- `0x1800939ec`
- `0x18009462c`
- `0x180096ca4`
- `0x1800975d4`
- `0x1800a0bbc`
- `0x1800e45f4`
- `0x1800e4fa4`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800487d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800487d0`
- `USER32!MonitorFromWindow` at `0x180047e09`
- `USER32!MonitorFromWindow` at `0x180047e09`
- `USER32!SetPropW` at `0x180047e4d`
- `USER32!SetPropW` at `0x180047e7e`
- `USER32!SetPropW` at `0x180047e4d`
- `USER32!SetPropW` at `0x180047e7e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180048856`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180048856`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x180048116`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x1800481cd`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x18004822e`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x180048293`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x1800482d1`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x18004832c`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x18004857c`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x180048788`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x180048116`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x1800481cd`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x18004822e`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x180048293`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x1800482d1`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x18004832c`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x18004857c`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x180048788`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180048135`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800481e6`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180048247`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180048597`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800485fb`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18004860c`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800487ae`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800487bf`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180048135`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800481e6`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180048247`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180048597`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800485fb`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18004860c`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800487ae`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800487bf`
- `DUI70!?SetPadding@Element@DirectUI@@QEAAJHHHH@Z` at `0x180048196`
- `DUI70!?SetPadding@Element@DirectUI@@QEAAJHHHH@Z` at `0x180048196`
- `DUI70!?SetForegroundStdColor@Element@DirectUI@@QEAAJH@Z` at `0x180048672`
- `DUI70!?SetForegroundStdColor@Element@DirectUI@@QEAAJH@Z` at `0x180048672`
- `DUI70!?SetBackgroundStdColor@Element@DirectUI@@QEAAJH@Z` at `0x18004865a`
- `DUI70!?SetBackgroundStdColor@Element@DirectUI@@QEAAJH@Z` at `0x18004865a`
- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800482f3`
- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800482f3`
- `DUI70!?SetAccRole@Element@DirectUI@@QEAAJH@Z` at `0x180048015`
- `DUI70!?SetAccRole@Element@DirectUI@@QEAAJH@Z` at `0x180048015`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x180047df5`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x180047e34`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x180047e65`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x180047f09`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x1800486fc`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x180048897`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x180047df5`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x180047e34`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x180047e65`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x180047f09`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x1800486fc`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x180048897`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x18004837b`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x1800483d0`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180048486`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x18004837b`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x1800483d0`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180048486`
- `DUI70!?Initialize@NativeHWNDHost@DirectUI@@QEAAJPEBGPEAUHWND__@@PEAUHICON__@@HHHHHHI@Z` at `0x180047d8a`
- `DUI70!?Initialize@NativeHWNDHost@DirectUI@@QEAAJPEBGPEAUHWND__@@PEAUHICON__@@HHHHHHI@Z` at `0x180047d8a`
- `DUI70!?Host@NativeHWNDHost@DirectUI@@QEAAXPEAVElement@2@@Z` at `0x180048055`
- `DUI70!?Host@NativeHWNDHost@DirectUI@@QEAAXPEAVElement@2@@Z` at `0x180048055`
- `DUI70!?SetLightDismissIHM@TouchHWNDElement@DirectUI@@QEAAJ_N@Z` at `0x18004803c`
- `DUI70!?SetLightDismissIHM@TouchHWNDElement@DirectUI@@QEAAJ_N@Z` at `0x18004803c`
- `DUI70!RegisterPVLBehaviorFactory` at `0x180047cd9`
- `DUI70!RegisterPVLBehaviorFactory` at `0x180047cd9`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x1800483b2`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x18004840a`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x180048430`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x180048463`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x180048495`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x1800484ff`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x1800483b2`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x18004840a`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x180048430`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x180048463`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x180048495`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x1800484ff`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180048067`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180048146`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800481f7`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180048258`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180048067`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180048146`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800481f7`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180048258`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180047fdd`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180048100`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180048178`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800481bb`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18004821c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18004827d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800482bf`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180048318`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800483a3`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800483f8`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800484eb`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18004856a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180048779`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180047fdd`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180048100`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180048178`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800481bb`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18004821c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18004827d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800482bf`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180048318`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800483a3`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800483f8`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800484eb`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18004856a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180048779`
- `DUI70!StrToID` at `0x180047fcb`
- `DUI70!StrToID` at `0x1800480ee`
- `DUI70!StrToID` at `0x180048166`
- `DUI70!StrToID` at `0x1800481a9`
- `DUI70!StrToID` at `0x18004820a`
- `DUI70!StrToID` at `0x18004826b`
- `DUI70!StrToID` at `0x1800482ad`
- `DUI70!StrToID` at `0x180048306`
- `DUI70!StrToID` at `0x180048391`
- `DUI70!StrToID` at `0x1800483e6`
- `DUI70!StrToID` at `0x1800484d9`
- `DUI70!StrToID` at `0x180048558`
- `DUI70!StrToID` at `0x180048767`
- `DUI70!StrToID` at `0x180047fcb`
- `DUI70!StrToID` at `0x1800480ee`
- `DUI70!StrToID` at `0x180048166`
- `DUI70!StrToID` at `0x1800481a9`
- `DUI70!StrToID` at `0x18004820a`
- `DUI70!StrToID` at `0x18004826b`
- `DUI70!StrToID` at `0x1800482ad`
- `DUI70!StrToID` at `0x180048306`
- `DUI70!StrToID` at `0x180048391`
- `DUI70!StrToID` at `0x1800483e6`
- `DUI70!StrToID` at `0x1800484d9`
- `DUI70!StrToID` at `0x180048558`
- `DUI70!StrToID` at `0x180048767`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x180047f9a`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x180047ff8`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x180047f9a`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x180047ff8`
- `DUser!SetGadgetFlags` at `0x180048447`
- `DUser!SetGadgetFlags` at `0x180048516`
- `DUser!SetGadgetFlags` at `0x180048447`
- `DUser!SetGadgetFlags` at `0x180048516`
- `DUser!SetHardwareDeviceUsage` at `0x180047e18`
- `DUser!SetHardwareDeviceUsage` at `0x180047e18`
- `DUser!AddLayeredRef` at `0x1800483c1`
- `DUser!AddLayeredRef` at `0x180048419`
- `DUser!AddLayeredRef` at `0x180048472`
- `DUser!AddLayeredRef` at `0x1800484a4`
- `DUser!AddLayeredRef` at `0x1800483c1`
- `DUser!AddLayeredRef` at `0x180048419`
- `DUser!AddLayeredRef` at `0x180048472`
- `DUser!AddLayeredRef` at `0x1800484a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::CPopupWindowImpl::_Initialize(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        struct DirectUI::Element *a5,
        HWND a6,
        int a7,
        char a8,
        int a9,
        int a10,
        DirectUI::Element *a11)
{
  __int64 v15; // rdx
  HRESULT Instance; // edi
  __int64 *v17; // rax
  __int64 v18; // rcx
  struct DirectUI::Element *v19; // rcx
  int v20; // eax
  HWND HWND; // rax
  HMONITOR v22; // rax
  HWND v23; // rax
  HWND v24; // rax
  Windows::Internal::CPopupWindowImpl *v25; // rcx
  int v26; // esi
  bool v27; // di
  HWND v28; // rax
  bool v29; // dl
  unsigned int v30; // r9d
  int v31; // eax
  DirectUI::Element *v32; // rsi
  int v33; // eax
  DirectUI::Element *v34; // rcx
  const unsigned __int16 *v35; // rdx
  unsigned __int16 v36; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::TouchHWNDElement *v38; // rax
  __int64 v39; // r15
  void (__fastcall *v40)(__int64, __int64); // rbx
  __int64 v41; // rdx
  unsigned __int16 v42; // ax
  unsigned __int16 v43; // ax
  DirectUI::Element *v44; // rax
  unsigned __int16 v45; // ax
  DirectUI::Element *v46; // rbx
  unsigned __int16 v47; // ax
  DirectUI::Element *v48; // rbx
  unsigned __int16 v49; // ax
  unsigned __int16 v50; // ax
  DirectUI::Element *v51; // r12
  unsigned __int16 v52; // ax
  DirectUI::Element *v53; // rax
  Windows::Internal *v54; // rcx
  DirectUI::Element *Element; // rbx
  unsigned __int16 v56; // ax
  DirectUI::Element *v57; // rax
  struct HGADGET__ *DisplayNode; // rax
  DirectUI::Element *v59; // rbx
  unsigned __int16 v60; // ax
  DirectUI::Element *v61; // rbx
  struct HGADGET__ *v62; // rax
  unsigned int v63; // edx
  struct HGADGET__ *v64; // rax
  struct HGADGET__ *v65; // rax
  DirectUI::Element *v66; // rax
  struct HGADGET__ *v67; // rax
  unsigned __int16 v68; // ax
  DirectUI::Element *v69; // rcx
  struct HGADGET__ *v70; // rax
  int v71; // eax
  int v72; // eax
  int v73; // eax
  unsigned __int16 v74; // ax
  DirectUI::Element *v75; // rbx
  CShellItemThumbnailElement *v76; // rax
  Windows::Internal::CBackButton *v77; // rax
  __int64 v78; // rax
  __int64 *v79; // r15
  struct DirectUI::Element *v80; // rcx
  unsigned __int16 v81; // ax
  DirectUI::Element *v82; // rax
  Windows::Internal *CurrentProcess; // rax
  void *v84; // rdx
  HWND v85; // rdx
  Windows::Internal *v86; // rcx
  struct DirectUI::Element *v87; // rsi
  __int64 (__fastcall *v88)(struct DirectUI::Element *, HWND, __int64, __int64, __int64); // rdi
  __int64 v89; // rbx
  HWND v90; // rax
  bool ShouldUseRestrictedModeKeyboard; // al
  LPVOID *ppv; // [rsp+20h] [rbp-40h]
  DirectUI::Element *v94; // [rsp+90h] [rbp+30h]

  Windows::Internal::CPopupWindowImpl::_EnsureTabletModeSubscription((Windows::Internal::CPopupWindowImpl *)a1);
  *(_QWORD *)(a1 + 80) = a2;
  *(_QWORD *)(a1 + 88) = a3;
  *(_QWORD *)(a1 + 96) = a4;
  *(_QWORD *)(a1 + 104) = a5;
  *(_DWORD *)(a1 + 140) = a9;
  *(_DWORD *)(a1 + 144) = a10;
  *(_BYTE *)(a1 + 136) = a8;
  *(_QWORD *)(a1 + 160) = a11;
  *(_BYTE *)(a1 + 701) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a4 + 144LL))(a4);
  LOBYTE(v15) = *(_BYTE *)(a1 + 705);
  (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 96) + 152LL))(*(_QWORD *)(a1 + 96), v15);
  Instance = RegisterPVLBehaviorFactory();
  if ( Instance < 0 )
    return (unsigned int)Instance;
  v17 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::CCustomDefaultDismissEvent,>(&a5);
  v18 = *v17;
  *v17 = 0;
  a11 = *(DirectUI::Element **)(a1 + 432);
  *(_QWORD *)(a1 + 432) = v18;
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&a11);
  v19 = a5;
  if ( a5 )
  {
    a5 = 0;
    (*(void (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v19 + 16LL))(v19);
  }
  if ( !*(_QWORD *)(a1 + 432) )
    return (unsigned int)-2147024882;
  v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a4 + 96LL))(a4);
  Instance = DirectUI::NativeHWNDHost::Initialize(
               (DirectUI::NativeHWNDHost *)a1,
               0,
               a6,
               0,
               0x80000000,
               0x80000000,
               0x80000000,
               0x80000000,
               v20,
               0x80000000,
               0x13u);
  if ( Instance < 0 )
    return (unsigned int)Instance;
  if ( (*(_DWORD *)(a1 + 140) & 0x800) == 0
    && ((*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 88LL))(*(_QWORD *)(a1 + 96)) == 1
     || (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 88LL))(*(_QWORD *)(a1 + 96)) == 3
     || (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 88LL))(*(_QWORD *)(a1 + 96)) == 2) )
  {
    HWND = DirectUI::NativeHWNDHost::GetHWND((DirectUI::NativeHWNDHost *)a1);
    v22 = MonitorFromWindow(HWND, 2u);
    SetHardwareDeviceUsage(v22);
  }
  if ( (*(_DWORD *)(a1 + 140) & 0x2000) != 0 )
  {
    v23 = DirectUI::NativeHWNDHost::GetHWND((DirectUI::NativeHWNDHost *)a1);
    SetPropW(v23, L"IHM_AutoInvokeKeyboard", HANDLE_FLAG_INHERIT);
  }
  if ( !*(_BYTE *)(a1 + 136) )
  {
    v24 = DirectUI::NativeHWNDHost::GetHWND((DirectUI::NativeHWNDHost *)a1);
    SetPropW(v24, L"UIA_WindowPatternEnabled", HANDLE_FLAG_INHERIT);
  }
  if ( a7 == 1 )
  {
    a8 = 1;
  }
  else
  {
    a8 = 0;
    if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 88LL))(*(_QWORD *)(a1 + 96)) == 1 )
    {
      *(_DWORD *)(a1 + 344) |= 8u;
      if ( (int)Windows::Internal::CPopupWindowImpl::_GetImmersiveApplicationBackgroundColor(
                  v25,
                  a6,
                  (unsigned int *)(a1 + 568)) < 0 )
      {
        *(_DWORD *)(a1 + 568) = 0xFFFFFF;
        *(_DWORD *)(a1 + 344) &= ~8u;
      }
    }
  }
  v26 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 112LL))(*(_QWORD *)(a1 + 96));
  a5 = 0;
  v27 = (*(_DWORD *)(a1 + 140) & 0x100000) != 0;
  v28 = DirectUI::NativeHWNDHost::GetHWND((DirectUI::NativeHWNDHost *)a1);
  Instance = Windows::Internal::FlyoutElement::Create(
               v28,
               v29,
               v26,
               v30,
               (struct DirectUI::Element *)ppv,
               v27,
               (unsigned int *)(a1 + 172),
               &a5);
  if ( Instance < 0 )
    return (unsigned int)Instance;
  v31 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 88LL))(*(_QWORD *)(a1 + 96));
  v32 = a5;
  if ( v31 == 2 )
  {
    if ( a6 && (unsigned __int8)Windows::Internal::_anonymous_namespace_::IsHostingContainerInCharmWindow(a6) )
    {
      v33 = IsHighContrast();
      v34 = v32;
      if ( v33 )
        v35 = L"HighContrastHostingContainerInCharmWindow";
      else
        v35 = L"HostingContainerInCharmWindow";
      goto LABEL_29;
    }
    if ( (unsigned int)IsHighContrast() )
    {
      v35 = L"HighContrastHostingContainer";
      v34 = v32;
LABEL_29:
      DirectUI::Element::SetClass(v34, v35);
    }
  }
  if ( (unsigned int)IsHighContrast() )
  {
    if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 88LL))(*(_QWORD *)(a1 + 96)) == 1 )
    {
      v36 = StrToID(L"PopupContent");
      Descendent = DirectUI::Element::FindDescendent(v32, v36);
      if ( Descendent )
        DirectUI::Element::SetClass(Descendent, L"HighContrast");
    }
  }
  if ( *(_BYTE *)(a1 + 136) )
    DirectUI::Element::SetAccRole(v32, 11);
  if ( (*(_DWORD *)(a1 + 140) & 0x1000) != 0 )
  {
    v38 = (DirectUI::TouchHWNDElement *)element_cast<DirectUI::TouchHWNDElement>(v32);
    DirectUI::TouchHWNDElement::SetLightDismissIHM(v38, 1);
  }
  ++*(_DWORD *)(a1 + 176);
  DirectUI::NativeHWNDHost::Host((DirectUI::NativeHWNDHost *)a1, v32);
  DirectUI::Element::SetVisible(v32, 1);
  Instance = -2147467259;
  if ( !*(_DWORD *)(a1 + 480) )
  {
    CSafeElementListenerPtr<UIBridgeWindow>::ReleaseListener(a1 + 456);
    *(_QWORD *)(a1 + 472) = (a1 + 48) & -(__int64)(a1 != 0);
    Instance = CSafeElementPtrBase<DirectUI::Element>::_Assign(a1 + 456, v32);
    if ( Instance < 0 )
    {
      *(_QWORD *)(a1 + 472) = 0;
      return (unsigned int)Instance;
    }
  }
  if ( Instance < 0 )
    return (unsigned int)Instance;
  v39 = a1 + 56;
  v40 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(a1 + 56) + 328LL);
  LOBYTE(v41) = (unsigned int)Windows::Internal::_anonymous_namespace_::GetPopupWindowLayoutDirection() == 1;
  v40(a1 + 56, v41);
  v42 = StrToID(L"UpButton");
  v94 = DirectUI::Element::FindDescendent(v32, v42);
  *(_DWORD *)(a1 + 396) = DirectUI::Element::GetLayoutPos(v94);
  DirectUI::Element::SetLayoutPos(v94, -3);
  DirectUI::Element::SetVisible(v94, 0);
  if ( (*(_DWORD *)(a1 + 140) & 0x8000000) != 0 )
  {
    v43 = StrToID(L"PopupContent");
    v44 = DirectUI::Element::FindDescendent(v32, v43);
    DirectUI::Element::SetPadding(v44, 24, 0, 24, 24);
  }
  v45 = StrToID(L"ButtonBar");
  v46 = DirectUI::Element::FindDescendent(v32, v45);
  *(_DWORD *)(a1 + 408) = DirectUI::Element::GetLayoutPos(v46);
  DirectUI::Element::SetLayoutPos(v46, -3);
  DirectUI::Element::SetVisible(v46, 0);
  v47 = StrToID(L"Title");
  v48 = DirectUI::Element::FindDescendent(v32, v47);
  *(_DWORD *)(a1 + 400) = DirectUI::Element::GetLayoutPos(v48);
  DirectUI::Element::SetLayoutPos(v48, -3);
  DirectUI::Element::SetVisible(v48, 0);
  v49 = StrToID(L"TitleBar");
  a11 = DirectUI::Element::FindDescendent(v32, v49);
  *(_DWORD *)(a1 + 404) = DirectUI::Element::GetLayoutPos(a11);
  v50 = StrToID(L"ContentArea");
  v51 = DirectUI::Element::FindDescendent(v32, v50);
  *(_DWORD *)(a1 + 412) = DirectUI::Element::GetLayoutPos(v51);
  if ( *(_BYTE *)(a1 + 136) )
    DirectUI::Element::SetAccessible(v51, 0);
  v52 = StrToID(L"Progress");
  v53 = DirectUI::Element::FindDescendent(v32, v52);
  if ( v53 )
  {
    *(_DWORD *)(a1 + 416) = DirectUI::Element::GetLayoutPos(v53);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v39 + 344LL))(a1 + 56, 0);
  }
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 88LL))(*(_QWORD *)(a1 + 96)) == 3 )
  {
    *(_BYTE *)(a1 + 700) = Windows::Internal::ImmersiveShellExists(v54);
    Element = DirectUI::NativeHWNDHost::GetElement((DirectUI::NativeHWNDHost *)a1);
    v56 = StrToID(L"TitleBarBackground");
    v57 = DirectUI::Element::FindDescendent(Element, v56);
    DisplayNode = DirectUI::Element::GetDisplayNode(v57);
    AddLayeredRef(DisplayNode);
    v59 = DirectUI::NativeHWNDHost::GetElement((DirectUI::NativeHWNDHost *)a1);
    v60 = StrToID(L"CharmWindowBorder");
    v61 = DirectUI::Element::FindDescendent(v59, v60);
    v62 = DirectUI::Element::GetDisplayNode(v61);
    AddLayeredRef(v62);
    DUI_SetGadgetZOrder(v61, v63);
    v64 = DirectUI::Element::GetDisplayNode(v61);
    SetGadgetFlags(v64, 8224, 8224);
    if ( (*(_DWORD *)(a1 + 140) & 0x500) == 0 )
    {
      v65 = DirectUI::Element::GetDisplayNode(v51);
      AddLayeredRef(v65);
      goto LABEL_57;
    }
  }
  else
  {
    v66 = DirectUI::NativeHWNDHost::GetElement((DirectUI::NativeHWNDHost *)a1);
    v67 = DirectUI::Element::GetDisplayNode(v66);
    AddLayeredRef(v67);
  }
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 88LL))(*(_QWORD *)(a1 + 96)) == 1
    && (*(_DWORD *)(a1 + 140) & 0x20000) != 0 )
  {
    v68 = StrToID(L"ContentAreaTSV");
    v69 = DirectUI::Element::FindDescendent(v32, v68);
  }
  else
  {
    v69 = v51;
  }
  v70 = DirectUI::Element::GetDisplayNode(v69);
  SetGadgetFlags(v70, 1025, 1025);
LABEL_57:
  v71 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 88LL))(*(_QWORD *)(a1 + 96));
  if ( v71 )
  {
    v72 = v71 - 1;
    if ( !v72 )
    {
      DirectUI::Element::SetLayoutPos(a11, -3);
      DirectUI::Element::SetLayoutPos(v51, -3);
      goto LABEL_66;
    }
    v73 = v72 - 1;
    if ( !v73 )
    {
      v81 = StrToID(L"AppIcon");
      v82 = DirectUI::Element::FindDescendent(v32, v81);
      *(_DWORD *)(a1 + 392) = DirectUI::Element::GetLayoutPos(v82);
      goto LABEL_66;
    }
    if ( v73 != 1 )
      goto LABEL_66;
  }
  v74 = StrToID(L"AppIconContainer");
  v75 = DirectUI::Element::FindDescendent(v32, v74);
  *(_DWORD *)(a1 + 392) = DirectUI::Element::GetLayoutPos(v75);
  DirectUI::Element::SetLayoutPos(v75, -3);
  a5 = 0;
  Instance = shell::TaskScheduler::CreateInstance(&stru_18010C408, &a5);
  if ( Instance >= 0 )
  {
    v76 = (CShellItemThumbnailElement *)FindDescendentElement<CShellItemThumbnailElement>(v75);
    Instance = CShellItemThumbnailElement::SetTaskScheduler(v76, *((struct IShellTaskScheduler **)a5 + 2));
  }
  if ( !(*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 88LL))(*(_QWORD *)(a1 + 96)) )
  {
    DirectUI::Element::SetLayoutPos(a11, -3);
    DirectUI::Element::SetLayoutPos(v51, -3);
  }
  CAutoMemPtr<shell::TaskScheduler>::~CAutoMemPtr<shell::TaskScheduler>(&a5);
LABEL_66:
  if ( ((*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 88LL))(*(_QWORD *)(a1 + 96)) == 1
     || (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 88LL))(*(_QWORD *)(a1 + 96)) == 2)
    && a8
    && (int)DirectUI::Element::SetBackgroundStdColor(v32, 20042) >= 0 )
  {
    DirectUI::Element::SetForegroundStdColor(v32, 20256);
  }
  Windows::Internal::CPopupWindowImpl::_InitializeDefaultColors((Windows::Internal::CPopupWindowImpl *)a1);
  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v39 + 240LL))(a1 + 56, 0);
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v39 + 176LL))(a1 + 56, 0);
    if ( Instance >= 0 )
    {
      v77 = (Windows::Internal::CBackButton *)FindDescendentElement<Windows::Internal::CBackButton>(v94);
      Instance = Windows::Internal::CBackButton::ResetColors(v77);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v39 + 296LL))(a1 + 56, 0);
        if ( Instance >= 0 )
        {
          a11 = (DirectUI::Element *)DirectUI::NativeHWNDHost::GetHWND((DirectUI::NativeHWNDHost *)a1);
          v78 = Microsoft::WRL::Details::Make<Windows::Internal::CTouchKeyboardNotificationCallback,HWND__ *>(&a5, &a11);
          v79 = (__int64 *)(a1 + 584);
          Microsoft::WRL::ComPtr<CRefCountedObject<Windows::Internal::String>>::operator=(a1 + 584, v78);
          v80 = a5;
          if ( a5 )
          {
            a5 = 0;
            (*(void (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v80 + 16LL))(v80);
          }
          if ( !*v79 )
            return (unsigned int)-2147024882;
          CurrentProcess = (Windows::Internal *)GetCurrentProcess();
          if ( Windows::Internal::IsProcessHighIL(CurrentProcess, v84)
            || !Windows::Internal::IsWindowImmersive((Windows::Internal *)a6, v85)
            || !(*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 88LL))(*(_QWORD *)(a1 + 96))
            || (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 88LL))(*(_QWORD *)(a1 + 96)) == 2 )
          {
            Instance = 0;
            ShouldUseRestrictedModeKeyboard = Windows::Internal::ShouldUseRestrictedModeKeyboard(v86);
            CTouchKeyboardNotifications::SubscribeToNotifications(
              a1 + 592,
              (*v79 + 16) & ((unsigned __int128)-(__int128)(unsigned __int64)*v79 >> 64),
              ShouldUseRestrictedModeKeyboard);
            CTouchKeyboardNotifications::RefreshKeyboardState((CTouchKeyboardNotifications *)(a1 + 592));
          }
          else
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1 + 624);
            Instance = CoCreateInstance(
                         &CLSID_FrameworkInputPane,
                         0,
                         1u,
                         &GUID_5752238b_24f0_495a_82f1_2fd593056796,
                         (LPVOID *)(a1 + 624));
            if ( Instance >= 0 )
            {
              a5 = 0;
              Instance = Microsoft::WRL::ComPtr<IFrameworkInputPane>::As<IFrameworkInputPanePriv>(a1 + 624, &a5);
              if ( Instance >= 0 )
              {
                v87 = a5;
                v88 = *(__int64 (__fastcall **)(struct DirectUI::Element *, HWND, __int64, __int64, __int64))(*(_QWORD *)a5 + 32LL);
                v89 = *v79;
                v90 = DirectUI::NativeHWNDHost::GetHWND((DirectUI::NativeHWNDHost *)a1);
                Instance = v88(v87, v90, 1, v89, a1 + 632);
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&a5);
            }
          }
        }
      }
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180047c3c  mov     [rsp-28h+arg_8], rbx
0x180047c41  mov     [rsp-28h+arg_10], rsi
0x180047c46  push    rbp
0x180047c47  push    rdi
0x180047c48  push    r12
0x180047c4a  push    r14
0x180047c4c  push    r15
0x180047c4e  mov     rbp, rsp
0x180047c51  sub     rsp, 60h
0x180047c55  mov     rsi, r9
0x180047c58  mov     rdi, r8
0x180047c5b  mov     rbx, rdx
0x180047c5e  mov     r14, rcx
0x180047c61  call    ?_EnsureTabletModeSubscription@CPopupWindowImpl@Internal@Windows@@AEAAXXZ; Windows::Internal::CPopupWindowImpl::_EnsureTabletModeSubscription(void)
0x180047c66  mov     [r14+50h], rbx
0x180047c6a  mov     [r14+58h], rdi
0x180047c6e  mov     [r14+60h], rsi
0x180047c72  mov     rax, [rbp+arg_20]
0x180047c76  mov     [r14+68h], rax
0x180047c7a  mov     eax, [rbp+arg_40]
0x180047c7d  mov     [r14+8Ch], eax
0x180047c84  mov     eax, [rbp+arg_48]
0x180047c87  mov     [r14+90h], eax
0x180047c8e  mov     al, [rbp+arg_38]
0x180047c91  mov     [r14+88h], al
0x180047c98  mov     rax, [rbp+arg_50]
0x180047c9f  mov     [r14+0A0h], rax
0x180047ca6  mov     rax, [rsi]
0x180047ca9  mov     rcx, rsi
0x180047cac  mov     rax, [rax+90h]
0x180047cb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047cb8  mov     [r14+2BDh], al
0x180047cbf  mov     rcx, [r14+60h]
0x180047cc3  mov     rax, [rcx]
0x180047cc6  mov     dl, [r14+2C1h]
0x180047ccd  mov     rax, [rax+98h]
0x180047cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047cd9  call    cs:__imp_RegisterPVLBehaviorFactory
0x180047ce0  nop     dword ptr [rax+rax+00h]
0x180047ce5  mov     edi, eax
0x180047ce7  xor     r12d, r12d
0x180047cea  test    eax, eax
0x180047cec  js      loc_180048905
0x180047cf2  lea     rcx, [rbp+arg_20]
0x180047cf6  call    ??$Make@VCCustomDefaultDismissEvent@Internal@Windows@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCCustomDefaultDismissEvent@Internal@Windows@@@12@XZ; Microsoft::WRL::Details::Make<Windows::Internal::CCustomDefaultDismissEvent,>(void)
0x180047cfb  mov     rcx, [rax]
0x180047cfe  mov     [rax], r12
0x180047d01  mov     rax, [r14+1B0h]
0x180047d08  mov     [rbp+arg_50], rax
0x180047d0f  mov     [r14+1B0h], rcx
0x180047d16  lea     rcx, [rbp+arg_50]
0x180047d1d  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180047d22  nop
0x180047d23  mov     rcx, [rbp+arg_20]
0x180047d27  test    rcx, rcx
0x180047d2a  jz      short loc_180047D3D
0x180047d2c  mov     [rbp+arg_20], r12
0x180047d30  mov     rax, [rcx]
0x180047d33  mov     rax, [rax+10h]
0x180047d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047d3c  nop
0x180047d3d  cmp     [r14+1B0h], r12
0x180047d44  jz      loc_180048756
0x180047d4a  mov     rax, [rsi]
0x180047d4d  mov     rcx, rsi
0x180047d50  mov     rax, [rax+60h]
0x180047d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047d59  mov     [rsp+60h+var_10], 13h
0x180047d61  mov     ecx, 80000000h
0x180047d66  mov     [rsp+60h+var_18], ecx
0x180047d6a  mov     [rsp+60h+var_20], eax
0x180047d6e  mov     dword ptr [rsp+60h+var_28], ecx
0x180047d72  mov     dword ptr [rsp+60h+var_30], ecx
0x180047d76  mov     dword ptr [rsp+60h+var_38], ecx
0x180047d7a  mov     dword ptr [rsp+60h+ppv], ecx; struct DirectUI::Element *
0x180047d7e  xor     r9d, r9d
0x180047d81  mov     r8, [rbp+arg_28]
0x180047d85  xor     edx, edx
0x180047d87  mov     rcx, r14
0x180047d8a  call    cs:__imp_?Initialize@NativeHWNDHost@DirectUI@@QEAAJPEBGPEAUHWND__@@PEAUHICON__@@HHHHHHI@Z; DirectUI::NativeHWNDHost::Initialize(ushort const *,HWND__ *,HICON__ *,int,int,int,int,int,int,uint)
0x180047d91  nop     dword ptr [rax+rax+00h]
0x180047d96  mov     edi, eax
0x180047d98  test    eax, eax
0x180047d9a  js      loc_180048905
0x180047da0  mov     r15d, 1
0x180047da6  test    dword ptr [r14+8Ch], 800h
0x180047db1  jnz     short loc_180047E24
0x180047db3  mov     rcx, [r14+60h]
0x180047db7  mov     rax, [rcx]
0x180047dba  mov     rax, [rax+58h]
0x180047dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047dc3  cmp     eax, r15d
0x180047dc6  jz      short loc_180047DF2
0x180047dc8  mov     rcx, [r14+60h]
0x180047dcc  mov     rax, [rcx]
0x180047dcf  mov     rax, [rax+58h]
0x180047dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047dd8  cmp     eax, 3
0x180047ddb  jz      short loc_180047DF2
0x180047ddd  mov     rcx, [r14+60h]
0x180047de1  mov     rax, [rcx]
0x180047de4  mov     rax, [rax+58h]
0x180047de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ded  cmp     eax, 2
0x180047df0  jnz     short loc_180047E24
0x180047df2  mov     rcx, r14
0x180047df5  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x180047dfc  nop     dword ptr [rax+rax+00h]
0x180047e01  mov     rcx, rax; hwnd
0x180047e04  mov     edx, 2; dwFlags
0x180047e09  call    cs:__imp_MonitorFromWindow
0x180047e10  nop     dword ptr [rax+rax+00h]
0x180047e15  mov     rcx, rax
0x180047e18  call    cs:__imp_SetHardwareDeviceUsage
0x180047e1f  nop     dword ptr [rax+rax+00h]
0x180047e24  test    dword ptr [r14+8Ch], 2000h
0x180047e2f  jz      short loc_180047E59
0x180047e31  mov     rcx, r14
0x180047e34  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x180047e3b  nop     dword ptr [rax+rax+00h]
0x180047e40  mov     rcx, rax; hWnd
0x180047e43  mov     r8, r15; hData
0x180047e46  lea     rdx, aIhmAutoinvokek; "IHM_AutoInvokeKeyboard"
0x180047e4d  call    cs:__imp_SetPropW
0x180047e54  nop     dword ptr [rax+rax+00h]
0x180047e59  cmp     [r14+88h], r12b
0x180047e60  jnz     short loc_180047E8A
0x180047e62  mov     rcx, r14
0x180047e65  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x180047e6c  nop     dword ptr [rax+rax+00h]
0x180047e71  mov     rcx, rax; hWnd
0x180047e74  mov     r8, r15; hData
0x180047e77  lea     rdx, aUiaWindowpatte; "UIA_WindowPatternEnabled"
0x180047e7e  call    cs:__imp_SetPropW
0x180047e85  nop     dword ptr [rax+rax+00h]
0x180047e8a  cmp     [rbp+arg_30], r15d
0x180047e8e  jnz     short loc_180047E96
0x180047e90  mov     [rbp+arg_38], r15b
0x180047e94  jmp     short loc_180047EDC
0x180047e96  mov     [rbp+arg_38], r12b
0x180047e9a  mov     rcx, [r14+60h]
0x180047e9e  mov     rax, [rcx]
0x180047ea1  mov     rax, [rax+58h]
0x180047ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047eaa  cmp     eax, r15d
0x180047ead  jnz     short loc_180047EDC
0x180047eaf  or      dword ptr [r14+158h], 8
0x180047eb7  lea     rbx, [r14+238h]
0x180047ebe  mov     r8, rbx; unsigned int *
0x180047ec1  mov     rdx, [rbp+arg_28]; HWND
0x180047ec5  call    ?_GetImmersiveApplicationBackgroundColor@CPopupWindowImpl@Internal@Windows@@AEAAJPEAUHWND__@@PEAK@Z; Windows::Internal::CPopupWindowImpl::_GetImmersiveApplicationBackgroundColor(HWND__ *,ulong *)
0x180047eca  test    eax, eax
0x180047ecc  jns     short loc_180047EDC
0x180047ece  mov     dword ptr [rbx], 0FFFFFFh
0x180047ed4  and     dword ptr [r14+158h], 0FFFFFFF7h
0x180047edc  mov     rcx, [r14+60h]
0x180047ee0  mov     rax, [rcx]
0x180047ee3  mov     rax, [rax+70h]
0x180047ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047eec  mov     esi, eax
0x180047eee  mov     [rbp+arg_20], r12
0x180047ef2  mov     edi, [r14+8Ch]
0x180047ef9  shr     edi, 14h
0x180047efc  and     dil, r15b
0x180047eff  lea     rbx, [r14+0ACh]
0x180047f06  mov     rcx, r14
0x180047f09  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x180047f10  nop     dword ptr [rax+rax+00h]
0x180047f15  mov     rcx, rax; HWND
0x180047f18  lea     rax, [rbp+arg_20]
0x180047f1c  mov     [rsp+60h+var_28], rax; struct DirectUI::Element **
0x180047f21  mov     [rsp+60h+var_30], rbx; unsigned int *
0x180047f26  mov     [rsp+60h+var_38], dil; bool
0x180047f2b  mov     r8d, esi; int
0x180047f2e  call    ?Create@FlyoutElement@Internal@Windows@@SAJPEAUHWND__@@_NHIPEAVElement@DirectUI@@1PEAKPEAPEAV56@@Z; Windows::Internal::FlyoutElement::Create(HWND__ *,bool,int,uint,DirectUI::Element *,bool,ulong *,DirectUI::Element * *)
0x180047f33  mov     edi, eax
0x180047f35  test    eax, eax
0x180047f37  js      loc_180048905
0x180047f3d  mov     rcx, [r14+60h]
0x180047f41  mov     rax, [rcx]
0x180047f44  mov     rax, [rax+58h]
0x180047f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047f4d  mov     rsi, [rbp+arg_20]
0x180047f51  cmp     eax, 2
0x180047f54  jnz     short loc_180047FA6
0x180047f56  cmp     [rbp+arg_28], r12
0x180047f5a  jz      short loc_180047F87
0x180047f5c  mov     rcx, [rbp+arg_28]
0x180047f60  call    Windows__Internal___anonymous_namespace___IsHostingContainerInCharmWindow
0x180047f65  test    al, al
0x180047f67  jz      short loc_180047F87
0x180047f69  call    ?IsHighContrast@@YAHXZ; IsHighContrast(void)
0x180047f6e  mov     rcx, rsi
0x180047f71  test    eax, eax
0x180047f73  jz      short loc_180047F7E
0x180047f75  lea     rdx, aHighcontrastho_0; "HighContrastHostingContainerInCharmWind"...
0x180047f7c  jmp     short loc_180047F9A
0x180047f7e  lea     rdx, aHostingcontain_1; "HostingContainerInCharmWindow"
0x180047f85  jmp     short loc_180047F9A
0x180047f87  call    ?IsHighContrast@@YAHXZ; IsHighContrast(void)
0x180047f8c  test    eax, eax
0x180047f8e  jz      short loc_180047FA6
0x180047f90  lea     rdx, aHighcontrastho; "HighContrastHostingContainer"
0x180047f97  mov     rcx, rsi
0x180047f9a  call    cs:__imp_?SetClass@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetClass(ushort const *)
0x180047fa1  nop     dword ptr [rax+rax+00h]
0x180047fa6  call    ?IsHighContrast@@YAHXZ; IsHighContrast(void)
0x180047fab  test    eax, eax
0x180047fad  jz      short loc_180048004
0x180047faf  mov     rcx, [r14+60h]
0x180047fb3  mov     rax, [rcx]
0x180047fb6  mov     rax, [rax+58h]
0x180047fba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047fbf  cmp     eax, r15d
0x180047fc2  jnz     short loc_180048004
0x180047fc4  lea     rcx, aPopupcontent; "PopupContent"
0x180047fcb  call    cs:__imp_StrToID
0x180047fd2  nop     dword ptr [rax+rax+00h]
0x180047fd7  movzx   edx, ax
0x180047fda  mov     rcx, rsi
0x180047fdd  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180047fe4  nop     dword ptr [rax+rax+00h]
0x180047fe9  test    rax, rax
0x180047fec  jz      short loc_180048004
0x180047fee  lea     rdx, aHighcontrast; "HighContrast"
0x180047ff5  mov     rcx, rax
0x180047ff8  call    cs:__imp_?SetClass@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetClass(ushort const *)
0x180047fff  nop     dword ptr [rax+rax+00h]
0x180048004  cmp     [r14+88h], r12b
0x18004800b  jz      short loc_180048021
0x18004800d  mov     edx, 0Bh
0x180048012  mov     rcx, rsi
0x180048015  call    cs:__imp_?SetAccRole@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetAccRole(int)
0x18004801c  nop     dword ptr [rax+rax+00h]
0x180048021  test    dword ptr [r14+8Ch], 1000h
0x18004802c  jz      short loc_180048048
0x18004802e  mov     rcx, rsi
0x180048031  call    ??$element_cast@VTouchHWNDElement@DirectUI@@@@YAPEAVTouchHWNDElement@DirectUI@@PEAVElement@1@@Z; element_cast<DirectUI::TouchHWNDElement>(DirectUI::Element *)
0x180048036  mov     dl, r15b
0x180048039  mov     rcx, rax
0x18004803c  call    cs:__imp_?SetLightDismissIHM@TouchHWNDElement@DirectUI@@QEAAJ_N@Z; DirectUI::TouchHWNDElement::SetLightDismissIHM(bool)
0x180048043  nop     dword ptr [rax+rax+00h]
0x180048048  add     [r14+0B0h], r15d
0x18004804f  mov     rdx, rsi
0x180048052  mov     rcx, r14
0x180048055  call    cs:__imp_?Host@NativeHWNDHost@DirectUI@@QEAAXPEAVElement@2@@Z; DirectUI::NativeHWNDHost::Host(DirectUI::Element *)
0x18004805c  nop     dword ptr [rax+rax+00h]
0x180048061  mov     dl, r15b
0x180048064  mov     rcx, rsi
0x180048067  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x18004806e  nop     dword ptr [rax+rax+00h]
0x180048073  lea     rbx, [r14+1C8h]
0x18004807a  mov     rax, r14
0x18004807d  lea     rcx, [r14+30h]
0x180048081  neg     rax
0x180048084  sbb     r15, r15
0x180048087  and     r15, rcx
0x18004808a  mov     edi, 80004005h
0x18004808f  cmp     [rbx+18h], r12d
0x180048093  jnz     short loc_1800480BB
0x180048095  mov     rcx, rbx
0x180048098  call    ?ReleaseListener@?$CSafeElementListenerPtr@VUIBridgeWindow@@@@QEAAXXZ; CSafeElementListenerPtr<UIBridgeWindow>::ReleaseListener(void)
0x18004809d  mov     [rbx+10h], r15
0x1800480a1  mov     rdx, rsi
0x1800480a4  mov     rcx, rbx
0x1800480a7  call    ?_Assign@?$CSafeElementPtrBase@VElement@DirectUI@@@@IEAAJPEAVElement@DirectUI@@@Z; CSafeElementPtrBase<DirectUI::Element>::_Assign(DirectUI::Element *)
0x1800480ac  mov     edi, eax
0x1800480ae  test    eax, eax
0x1800480b0  jns     short loc_1800480BB
0x1800480b2  mov     [rbx+10h], r12
0x1800480b6  jmp     loc_180048905
0x1800480bb  test    edi, edi
0x1800480bd  js      loc_180048905
0x1800480c3  lea     r15, [r14+38h]
0x1800480c7  mov     rax, [r15]
0x1800480ca  mov     rbx, [rax+148h]
0x1800480d1  call    Windows__Internal___anonymous_namespace___GetPopupWindowLayoutDirection
0x1800480d6  cmp     eax, 1
0x1800480d9  setz    dl
0x1800480dc  mov     rcx, r15
0x1800480df  mov     rax, rbx
0x1800480e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800480e7  lea     rcx, aUpbutton; "UpButton"
0x1800480ee  call    cs:__imp_StrToID
0x1800480f5  nop     dword ptr [rax+rax+00h]
0x1800480fa  movzx   edx, ax
0x1800480fd  mov     rcx, rsi
0x180048100  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180048107  nop     dword ptr [rax+rax+00h]
0x18004810c  mov     rbx, rax
0x18004810f  mov     [rbp+arg_0], rax
0x180048113  mov     rcx, rax
0x180048116  call    cs:__imp_?GetLayoutPos@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetLayoutPos(void)
0x18004811d  nop     dword ptr [rax+rax+00h]
0x180048122  mov     [r14+18Ch], eax
0x180048129  mov     r12d, 0FFFFFFFDh
0x18004812f  mov     edx, r12d
0x180048132  mov     rcx, rbx
0x180048135  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18004813c  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
