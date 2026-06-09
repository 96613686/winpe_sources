# Windows::UI::Core::DesktopWindowContentBridge::Connect(Windows::UI::IUIContentRoot *)

- ea: `0x1800249f0`
- end: `0x180025169`
- name: `?Connect@DesktopWindowContentBridge@Core@UI@Windows@@UEAAJPEAUIUIContentRoot@34@@Z`
- size: `1913`
- prototype: `__int64 __fastcall(Windows::UI::Core::DesktopWindowContentBridge *__hidden this, struct Windows::UI::IUIContentRoot *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1800038e0`
- `0x180014754`
- `0x180016064`
- `0x1800243ac`
- `0x1800249f0`
- `0x180025170`
- `0x1800251ac`
- `0x1800251d8`
- `0x180050360`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800250ac`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800250f5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800250ac`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800250f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024b82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024c33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024b82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024c33`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180024ba4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180024c5c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180024ba4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180024c5c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindowVisible` at `0x180024c97`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindowVisible` at `0x180024c97`

## string_xrefs

- `0x180024b7b`: `Windows.UI.Composition.CompositionIsland`
- `0x180024db1`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180024e9d`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180024eb6`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180024f01`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180024f16`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180024f2b`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180024f40`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180024f59`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x18002506a`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180025089`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x1800250be`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x1800250d8`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180025103`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall Windows::UI::Core::DesktopWindowContentBridge::Connect(
        HWND *this,
        struct Windows::UI::IUIContentRoot *a2)
{
  unsigned int IsValidState; // ebx
  __int64 (__fastcall *v5)(struct Windows::UI::IUIContentRoot *, GUID *, __int64 *); // rbx
  int v6; // eax
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v9; // eax
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v11)(_QWORD, GUID *, __int64 *); // rdi
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v15; // eax
  __int64 (__fastcall ***v16)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v17)(_QWORD, GUID *, __int64 *); // rdi
  int v18; // eax
  int ActivationFactory; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  HRESULT StringReference; // eax
  __int64 v24; // rbx
  int v25; // eax
  int v26; // eax
  BOOL v27; // eax
  int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 (__fastcall ***v33)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v34; // rcx
  __int64 (__fastcall ***v35)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v36; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 (__fastcall ***v42)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v43; // rcx
  __int64 (__fastcall ***v44)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v45; // rcx
  __int64 (__fastcall ***v46)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 (__fastcall ***v51)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v52; // rcx
  __int64 (__fastcall ***v53)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v54; // rcx
  HWND v55; // rcx
  __int64 v56; // rdx
  __int64 v57; // [rsp+20h] [rbp-29h] BYREF
  __int64 v58; // [rsp+28h] [rbp-21h] BYREF
  __int64 v59; // [rsp+30h] [rbp-19h] BYREF
  __int64 (__fastcall ***v60)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-11h] BYREF
  __int64 v61; // [rsp+40h] [rbp-9h] BYREF
  __int64 v62; // [rsp+48h] [rbp-1h] BYREF
  __int64 (__fastcall ***v63)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp+7h] BYREF
  __int64 v64; // [rsp+58h] [rbp+Fh] BYREF
  struct Windows::UI::IUIContentRoot *v65; // [rsp+60h] [rbp+17h] BYREF
  HSTRING string; // [rsp+68h] [rbp+1Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  IsValidState = Windows::UI::Core::DesktopWindowContentBridge::IsValidState((Windows::UI::Core::DesktopWindowContentBridge *)this);
  if ( (IsValidState & 0x80000000) != 0 )
  {
    v56 = 192;
LABEL_84:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v56,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)IsValidState,
      v57);
    return IsValidState;
  }
  IsValidState = Windows::UI::Core::DesktopWindowContentBridge::CheckThread((Windows::UI::Core::DesktopWindowContentBridge *)this);
  if ( (IsValidState & 0x80000000) != 0 )
  {
    v56 = 193;
    goto LABEL_84;
  }
  if ( this[21] == (HWND)a2 )
  {
    a2 = (struct Windows::UI::IUIContentRoot *)this[21];
  }
  else
  {
    v65 = a2;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v65);
    v55 = this[21];
    this[21] = (HWND)a2;
    if ( v55 )
    {
      (*(void (__fastcall **)(HWND))(*(_QWORD *)v55 + 16LL))(v55);
      a2 = (struct Windows::UI::IUIContentRoot *)this[21];
    }
  }
  v57 = 0;
  v5 = **(__int64 (__fastcall ***)(struct Windows::UI::IUIContentRoot *, GUID *, __int64 *))a2;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v57);
  v6 = v5(a2, &GUID_603381cb_2327_5454_919d_a61c5dc4a7d9, &v57);
  if ( v6 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xC6,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)v6,
      v57);
  v60 = 0;
  v7 = v57;
  v8 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v57 + 56LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v60);
  v9 = v8(v7, &v60);
  IsValidState = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCA,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)v9,
      v57);
    v46 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v60;
    if ( v60 )
    {
      v60 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v46)[2])(v46);
    }
    v47 = v57;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    }
    return IsValidState;
  }
  v61 = 0;
  v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v60;
  v11 = **v60;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v61);
  v12 = v11(v10, &GUID_9d031780_ae09_5272_80e0_50a215c0baf0, &v61);
  if ( v12 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xCC,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)v12,
      v57);
  v63 = 0;
  v13 = v57;
  v14 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v57 + 48LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v63);
  v15 = v14(v13, &v63);
  IsValidState = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD0,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)v15,
      v57);
LABEL_92:
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v63);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v61);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v60);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v57);
    return IsValidState;
  }
  v59 = 0;
  v16 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v63;
  v17 = **v63;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v59);
  v18 = v17(v16, &GUID_cfb32fa7_5399_5f3d_82ba_9641f106ffcd, &v59);
  if ( v18 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xD2,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)v18,
      v57);
  v58 = 0;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v58);
  if ( WindowsCreateStringReference(L"Windows.UI.Composition.CompositionIsland", 0x28u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(string, &GUID_77fcc60e_69bd_4d67_8fab_e9787219b184, &v58);
  IsValidState = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD7,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v57);
LABEL_91:
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v58);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v59);
    goto LABEL_92;
  }
  v62 = 0;
  v20 = Microsoft::WRL::ComPtr<Windows::UI::Composition::IVisualIslandSite>::As<Windows::UI::Composition::ICompositionIslandSite>(
          this + 19,
          &v62);
  if ( v20 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xDA,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)v20,
      v57);
  v21 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v58 + 48LL))(v58, v62, v61);
  IsValidState = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)v21,
      v57);
    v48 = v62;
    if ( v62 )
    {
      v62 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    }
    v49 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    }
    v50 = v59;
    if ( v59 )
    {
      v59 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    }
    v51 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v63;
    if ( v63 )
    {
      v63 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v51)[2])(v51);
    }
    v52 = v61;
    if ( v61 )
    {
      v61 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    }
    v53 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v60;
    if ( v60 )
    {
      v60 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v53)[2])(v53);
    }
    v54 = v57;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    }
    return IsValidState;
  }
  v22 = (*(__int64 (__fastcall **)(__int64, HWND))(*(_QWORD *)v61 + 80LL))(v61, this[23]);
  IsValidState = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE0,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)v22,
      v57);
LABEL_90:
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v62);
    goto LABEL_91;
  }
  v64 = 0;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
  StringReference = WindowsCreateStringReference(
                      L"Windows.UI.Internal.Input.InputSite",
                      0x23u,
                      (HSTRING_HEADER *)&string,
                      (HSTRING *)&hstringHeader.Reserved.Reserved2[16]);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    __debugbreak();
  }
  v24 = *(_QWORD *)&hstringHeader.Reserved.Reserved2[16];
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v64);
  v25 = RoGetActivationFactory(v24, &GUID_73f80911_7a51_5b0f_906b_f6402ea6c3cb, &v64);
  if ( v25 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xE6,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)v25,
      v57);
  v26 = (*(__int64 (__fastcall **)(__int64, HWND, __int64))(*(_QWORD *)v64 + 112LL))(v64, this[26], v59);
  IsValidState = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE9,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)v26,
      v57);
    v38 = v64;
    if ( v64 )
    {
      v64 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
    v39 = v62;
    if ( v62 )
    {
      v62 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
    v40 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    }
    v41 = v59;
    if ( v59 )
    {
      v59 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    }
    v42 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v63;
    if ( v63 )
    {
      v63 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v42)[2])(v42);
    }
    v43 = v61;
    if ( v61 )
    {
      v61 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    }
    v44 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v60;
    if ( v60 )
    {
      v60 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v44)[2])(v44);
    }
    v45 = v57;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    }
    return IsValidState;
  }
  v27 = IsWindowVisible(this[13]);
  v28 = Windows::UI::Core::DesktopWindowContentBridge::ShowIslandSite(
          (Windows::UI::Core::DesktopWindowContentBridge *)this,
          v27);
  IsValidState = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEC,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)v28,
      v57);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v64);
    goto LABEL_90;
  }
  v29 = v64;
  if ( v64 )
  {
    v64 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  v30 = v62;
  if ( v62 )
  {
    v62 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  v31 = v58;
  if ( v58 )
  {
    v58 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  }
  v32 = v59;
  if ( v59 )
  {
    v59 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
  v33 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v63;
  if ( v63 )
  {
    v63 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v33)[2])(v33);
  }
  v34 = v61;
  if ( v61 )
  {
    v61 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
  v35 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v60;
  if ( v60 )
  {
    v60 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v35)[2])(v35);
  }
  v36 = v57;
  if ( v57 )
  {
    v57 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  }
  return 0;
}

```

## disassembly

```asm
0x1800249f0  mov     [rsp-8+arg_8], rbx
0x1800249f5  mov     [rsp-8+arg_10], rsi
0x1800249fa  push    rbp
0x1800249fb  push    rdi
0x1800249fc  push    r14
0x1800249fe  lea     rbp, [rsp-47h]
0x180024a03  sub     rsp, 90h
0x180024a0a  mov     rax, cs:__security_cookie
0x180024a11  xor     rax, rsp
0x180024a14  mov     [rbp+57h+var_18], rax
0x180024a18  mov     rdi, rdx
0x180024a1b  mov     rsi, rcx
0x180024a1e  call    ?IsValidState@DesktopWindowContentBridge@Core@UI@Windows@@AEAAJXZ; Windows::UI::Core::DesktopWindowContentBridge::IsValidState(void)
0x180024a23  mov     ebx, eax
0x180024a25  xor     r14d, r14d
0x180024a28  test    eax, eax
0x180024a2a  js      loc_18002505E
0x180024a30  mov     rcx, rsi; this
0x180024a33  call    ?CheckThread@DesktopWindowContentBridge@Core@UI@Windows@@AEAAJXZ; Windows::UI::Core::DesktopWindowContentBridge::CheckThread(void)
0x180024a38  mov     ebx, eax
0x180024a3a  test    eax, eax
0x180024a3c  js      loc_180025065
0x180024a42  mov     rax, [rsi+0A8h]
0x180024a49  cmp     rax, rdi
0x180024a4c  jnz     loc_180025026
0x180024a52  mov     rdi, rax
0x180024a55  mov     [rbp+57h+var_80], r14
0x180024a59  mov     rax, [rdi]
0x180024a5c  mov     rbx, [rax]
0x180024a5f  lea     rcx, [rbp+57h+var_80]
0x180024a63  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180024a68  lea     r8, [rbp+57h+var_80]
0x180024a6c  lea     rdx, _GUID_603381cb_2327_5454_919d_a61c5dc4a7d9
0x180024a73  mov     rcx, rdi
0x180024a76  mov     rax, rbx
0x180024a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a7e  nop
0x180024a7f  mov     rcx, [rbp+5Fh]; this
0x180024a83  test    eax, eax
0x180024a85  js      loc_180024E9A
0x180024a8b  mov     [rbp+57h+var_68], r14
0x180024a8f  mov     rdi, [rbp+57h+var_80]
0x180024a93  mov     rax, [rdi]
0x180024a96  mov     rbx, [rax+38h]
0x180024a9a  lea     rcx, [rbp+57h+var_68]
0x180024a9e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180024aa3  lea     rdx, [rbp+57h+var_68]
0x180024aa7  mov     rcx, rdi
0x180024aaa  mov     rax, rbx
0x180024aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ab2  mov     ebx, eax
0x180024ab4  test    eax, eax
0x180024ab6  js      loc_180024EAF
0x180024abc  mov     [rbp+57h+var_60], r14
0x180024ac0  mov     rbx, [rbp+57h+var_68]
0x180024ac4  mov     rax, [rbx]
0x180024ac7  mov     rdi, [rax]
0x180024aca  lea     rcx, [rbp+57h+var_60]
0x180024ace  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180024ad3  lea     r8, [rbp+57h+var_60]
0x180024ad7  lea     rdx, _GUID_9d031780_ae09_5272_80e0_50a215c0baf0
0x180024ade  mov     rcx, rbx
0x180024ae1  mov     rax, rdi
0x180024ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ae9  nop
0x180024aea  mov     rcx, [rbp+5Fh]; this
0x180024aee  test    eax, eax
0x180024af0  js      loc_180024EFE
0x180024af6  mov     [rbp+57h+var_50], r14
0x180024afa  mov     rdi, [rbp+57h+var_80]
0x180024afe  mov     rax, [rdi]
0x180024b01  mov     rbx, [rax+30h]
0x180024b05  lea     rcx, [rbp+57h+var_50]
0x180024b09  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180024b0e  lea     rdx, [rbp+57h+var_50]
0x180024b12  mov     rcx, rdi
0x180024b15  mov     rax, rbx
0x180024b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b1d  mov     ebx, eax
0x180024b1f  test    eax, eax
0x180024b21  js      loc_180025082
0x180024b27  mov     [rbp+57h+var_70], r14
0x180024b2b  mov     rbx, [rbp+57h+var_50]
0x180024b2f  mov     rax, [rbx]
0x180024b32  mov     rdi, [rax]
0x180024b35  lea     rcx, [rbp+57h+var_70]
0x180024b39  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180024b3e  lea     r8, [rbp+57h+var_70]
0x180024b42  lea     rdx, _GUID_cfb32fa7_5399_5f3d_82ba_9641f106ffcd
0x180024b49  mov     rcx, rbx
0x180024b4c  mov     rax, rdi
0x180024b4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b54  nop
0x180024b55  mov     rcx, [rbp+5Fh]; this
0x180024b59  test    eax, eax
0x180024b5b  js      loc_180024F13
0x180024b61  mov     [rbp+57h+var_78], r14
0x180024b65  lea     rcx, [rbp+57h+var_78]
0x180024b69  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180024b6e  lea     r9, [rbp+57h+string]; string
0x180024b72  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180024b76  mov     edx, 28h ; '('; length
0x180024b7b  lea     rcx, ?RuntimeClass_Windows_UI_Composition_CompositionIsland@@3QBGB; "Windows.UI.Composition.CompositionIslan"...
0x180024b82  call    cs:__imp_WindowsCreateStringReference
0x180024b88  mov     edi, 1
0x180024b8d  test    eax, eax
0x180024b8f  js      loc_18002509F
0x180024b95  lea     r8, [rbp+57h+var_78]
0x180024b99  lea     rdx, _GUID_77fcc60e_69bd_4d67_8fab_e9787219b184
0x180024ba0  mov     rcx, [rbp+57h+string]
0x180024ba4  call    cs:__imp_RoGetActivationFactory
0x180024baa  mov     ebx, eax
0x180024bac  test    eax, eax
0x180024bae  js      loc_1800250B7
0x180024bb4  mov     [rbp+57h+var_58], r14
0x180024bb8  lea     rcx, [rsi+98h]
0x180024bbf  lea     rdx, [rbp+57h+var_58]
0x180024bc3  call    ??$As@UICompositionIslandSite@Composition@UI@Windows@@@?$ComPtr@UIVisualIslandSite@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICompositionIslandSite@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::IVisualIslandSite>::As<Windows::UI::Composition::ICompositionIslandSite>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionIslandSite>>)
0x180024bc8  mov     rcx, [rbp+5Fh]; this
0x180024bcc  test    eax, eax
0x180024bce  js      loc_180024F28
0x180024bd4  mov     rcx, [rbp+57h+var_78]
0x180024bd8  mov     rax, [rcx]
0x180024bdb  mov     r8, [rbp+57h+var_60]
0x180024bdf  mov     rdx, [rbp+57h+var_58]
0x180024be3  mov     rax, [rax+30h]
0x180024be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024bec  mov     ebx, eax
0x180024bee  test    eax, eax
0x180024bf0  js      loc_180024F52
0x180024bf6  mov     rcx, [rbp+57h+var_60]
0x180024bfa  mov     rax, [rcx]
0x180024bfd  mov     rdx, [rsi+0B8h]
0x180024c04  mov     rax, [rax+50h]
0x180024c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c0d  mov     ebx, eax
0x180024c0f  test    eax, eax
0x180024c11  js      loc_1800250D1
0x180024c17  mov     [rbp+57h+var_48], r14
0x180024c1b  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], r14
0x180024c1f  lea     r9, [rbp+57h+hstringHeader.Reserved+10h]; string
0x180024c23  lea     r8, [rbp+57h+string]; hstringHeader
0x180024c27  mov     edx, 23h ; '#'; length
0x180024c2c  lea     rcx, ?RuntimeClass_Windows_UI_Internal_Input_InputSite@@3QBGB; "Windows.UI.Internal.Input.InputSite"
0x180024c33  call    cs:__imp_WindowsCreateStringReference
0x180024c39  test    eax, eax
0x180024c3b  js      loc_1800250EB
0x180024c41  mov     rbx, qword ptr [rbp+57h+hstringHeader.Reserved+10h]
0x180024c45  lea     rcx, [rbp+57h+var_48]
0x180024c49  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180024c4e  lea     r8, [rbp+57h+var_48]
0x180024c52  lea     rdx, _GUID_73f80911_7a51_5b0f_906b_f6402ea6c3cb
0x180024c59  mov     rcx, rbx
0x180024c5c  call    cs:__imp_RoGetActivationFactory
0x180024c62  mov     rcx, [rbp+5Fh]; this
0x180024c66  test    eax, eax
0x180024c68  js      loc_180024F3D
0x180024c6e  mov     rcx, [rbp+57h+var_48]
0x180024c72  mov     rax, [rcx]
0x180024c75  mov     r8, [rbp+57h+var_70]
0x180024c79  mov     rdx, [rsi+0D0h]
0x180024c80  mov     rax, [rax+70h]
0x180024c84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c89  mov     ebx, eax
0x180024c8b  test    eax, eax
0x180024c8d  js      loc_180024DAA
0x180024c93  mov     rcx, [rsi+68h]; hWnd
0x180024c97  call    cs:__imp_IsWindowVisible
0x180024c9d  test    eax, eax
0x180024c9f  setnz   dl; bool
0x180024ca2  mov     rcx, rsi; this
0x180024ca5  call    ?ShowIslandSite@DesktopWindowContentBridge@Core@UI@Windows@@AEAAJ_N@Z; Windows::UI::Core::DesktopWindowContentBridge::ShowIslandSite(bool)
0x180024caa  mov     ebx, eax
0x180024cac  test    eax, eax
0x180024cae  js      loc_1800250FC
0x180024cb4  mov     rcx, [rbp+57h+var_48]
0x180024cb8  test    rcx, rcx
0x180024cbb  jz      short loc_180024CCE
0x180024cbd  mov     [rbp+57h+var_48], r14
0x180024cc1  mov     rax, [rcx]
0x180024cc4  mov     rax, [rax+10h]
0x180024cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ccd  nop
0x180024cce  mov     rcx, [rbp+57h+var_58]
0x180024cd2  test    rcx, rcx
0x180024cd5  jz      short loc_180024CE8
0x180024cd7  mov     [rbp+57h+var_58], r14
0x180024cdb  mov     rax, [rcx]
0x180024cde  mov     rax, [rax+10h]
0x180024ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ce7  nop
0x180024ce8  mov     rcx, [rbp+57h+var_78]
0x180024cec  test    rcx, rcx
0x180024cef  jz      short loc_180024D02
0x180024cf1  mov     [rbp+57h+var_78], r14
0x180024cf5  mov     rax, [rcx]
0x180024cf8  mov     rax, [rax+10h]
0x180024cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d01  nop
0x180024d02  mov     rcx, [rbp+57h+var_70]
0x180024d06  test    rcx, rcx
0x180024d09  jz      short loc_180024D1C
0x180024d0b  mov     [rbp+57h+var_70], r14
0x180024d0f  mov     rax, [rcx]
0x180024d12  mov     rax, [rax+10h]
0x180024d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d1b  nop
0x180024d1c  mov     rcx, [rbp+57h+var_50]
0x180024d20  test    rcx, rcx
0x180024d23  jz      short loc_180024D36
0x180024d25  mov     [rbp+57h+var_50], r14
0x180024d29  mov     rax, [rcx]
0x180024d2c  mov     rax, [rax+10h]
0x180024d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d35  nop
0x180024d36  mov     rcx, [rbp+57h+var_60]
0x180024d3a  test    rcx, rcx
0x180024d3d  jz      short loc_180024D50
0x180024d3f  mov     [rbp+57h+var_60], r14
0x180024d43  mov     rax, [rcx]
0x180024d46  mov     rax, [rax+10h]
0x180024d4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d4f  nop
0x180024d50  mov     rcx, [rbp+57h+var_68]
0x180024d54  test    rcx, rcx
0x180024d57  jz      short loc_180024D6A
0x180024d59  mov     [rbp+57h+var_68], r14
0x180024d5d  mov     rax, [rcx]
0x180024d60  mov     rax, [rax+10h]
0x180024d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d69  nop
0x180024d6a  mov     rcx, [rbp+57h+var_80]
0x180024d6e  test    rcx, rcx
0x180024d71  jz      short loc_180024D84
0x180024d73  mov     [rbp+57h+var_80], r14
0x180024d77  mov     rax, [rcx]
0x180024d7a  mov     rax, [rax+10h]
0x180024d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d83  nop
0x180024d84  xor     eax, eax
0x180024d86  mov     rcx, [rbp+57h+var_18]
0x180024d8a  xor     rcx, rsp; StackCookie
0x180024d8d  call    __security_check_cookie
0x180024d92  lea     r11, [rsp+0A0h+var_10]
0x180024d9a  mov     rbx, [r11+28h]
0x180024d9e  mov     rsi, [r11+30h]
0x180024da2  mov     rsp, r11
0x180024da5  pop     r14
0x180024da7  pop     rdi
0x180024da8  pop     rbp
0x180024da9  retn
0x180024daa  mov     rcx, [rbp+5Fh]; this
0x180024dae  mov     r9d, ebx; char *
0x180024db1  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180024db8  mov     edx, 0E9h; void *
0x180024dbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024dc2  nop
0x180024dc3  mov     rcx, [rbp+57h+var_48]
0x180024dc7  test    rcx, rcx
0x180024dca  jz      short loc_180024DDD
0x180024dcc  mov     [rbp+57h+var_48], r14
0x180024dd0  mov     rax, [rcx]
0x180024dd3  mov     rax, [rax+10h]
0x180024dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ddc  nop
0x180024ddd  mov     rcx, [rbp+57h+var_58]
0x180024de1  test    rcx, rcx
0x180024de4  jz      short loc_180024DF7
0x180024de6  mov     [rbp+57h+var_58], r14
0x180024dea  mov     rax, [rcx]
0x180024ded  mov     rax, [rax+10h]
0x180024df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024df6  nop
0x180024df7  mov     rcx, [rbp+57h+var_78]
0x180024dfb  test    rcx, rcx
0x180024dfe  jz      short loc_180024E11
0x180024e00  mov     [rbp+57h+var_78], r14
0x180024e04  mov     rax, [rcx]
0x180024e07  mov     rax, [rax+10h]
0x180024e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e10  nop
0x180024e11  mov     rcx, [rbp+57h+var_70]
0x180024e15  test    rcx, rcx
0x180024e18  jz      short loc_180024E2B
0x180024e1a  mov     [rbp+57h+var_70], r14
0x180024e1e  mov     rax, [rcx]
0x180024e21  mov     rax, [rax+10h]
0x180024e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e2a  nop
0x180024e2b  mov     rcx, [rbp+57h+var_50]
0x180024e2f  test    rcx, rcx
0x180024e32  jz      short loc_180024E45
0x180024e34  mov     [rbp+57h+var_50], r14
0x180024e38  mov     rax, [rcx]
0x180024e3b  mov     rax, [rax+10h]
0x180024e3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e44  nop
0x180024e45  mov     rcx, [rbp+57h+var_60]
0x180024e49  test    rcx, rcx
0x180024e4c  jz      short loc_180024E5F
  ... truncated ...
```
