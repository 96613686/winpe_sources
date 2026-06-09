# Windows::UI::Core::DesktopWindowContentBridge::Initialize(Windows::UI::Composition::ICompositor *,HWND__ *)

- ea: `0x180025870`
- end: `0x180026063`
- name: `?Initialize@DesktopWindowContentBridge@Core@UI@Windows@@UEAAJPEAUICompositor@Composition@34@PEAUHWND__@@@Z`
- size: `2035`
- prototype: `__int64 __fastcall(Windows::UI::Core::DesktopWindowContentBridge *__hidden this, struct Windows::UI::Composition::ICompositor *, HWND)`
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800038e0`
- `0x180014754`
- `0x180025870`
- `0x18002606c`
- `0x1800268e0`
- `0x1800269e8`
- `0x180026aac`
- `0x180026afc`
- `0x180026b84`
- `0x180026c00`
- `0x180026c4c`
- `0x180049078`
- `0x180050360`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025fd0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002605c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025fd0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002605c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180025a60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180025b6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180025a60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180025b6c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180025a89`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180025b95`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180025a89`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180025b95`

## string_xrefs

- `0x180025cd0`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180025d58`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180025d6e`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180025d87`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180025db8`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180025dcd`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180025de2`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180025df7`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180025e0c`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180025e25`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180025ecf`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180025f3b`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180025f8d`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180025faf`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180025fde`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180026013`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180025a59`: `Windows.UI.Composition.CompositionIslandEnvironment`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Windows::UI::Core::DesktopWindowContentBridge::Initialize(
        Windows::UI::Core::DesktopWindowContentBridge *this,
        struct Windows::UI::Composition::ICompositor *a2,
        HWND a3)
{
  __int64 v6; // rcx
  int Hwnd; // eax
  unsigned int v8; // ebx
  __int64 (__fastcall *v9)(struct Windows::UI::Composition::ICompositor *, GUID *, __int64 *); // rbx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, char *); // rbx
  _QWORD *v13; // r13
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, char *); // rbx
  int v17; // eax
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v19)(_QWORD, GUID *, __int64 *); // rbx
  int v20; // eax
  int v21; // eax
  int v22; // eax
  HRESULT v23; // eax
  HSTRING v24; // rbx
  int ActivationFactory; // eax
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, char *); // rbx
  int v28; // eax
  int v29; // eax
  int v30; // eax
  Windows::UI::Core::DesktopWindowContentBridge *v31; // rcx
  bool v32; // zf
  Windows::UI::Core::DesktopWindowContentBridge *v33; // rcx
  float v34; // xmm0_4
  int v35; // eax
  HRESULT v36; // eax
  HSTRING v37; // rbx
  int v38; // eax
  __int64 v39; // rdi
  __int64 (__fastcall *v40)(__int64, _QWORD, HSTRING_HEADER *, char *); // rbx
  int v41; // eax
  int v42; // eax
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // rcx
  float Window_ScaleFactor; // xmm0_4
  int updated; // eax
  __int64 v60; // rdx
  __int64 v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  __int64 v64; // rcx
  __int64 v65; // rcx
  __int64 v66; // rdx
  float System_ScaleFactor; // xmm0_4
  int v68; // [rsp+20h] [rbp-49h]
  __int64 v69; // [rsp+30h] [rbp-39h] BYREF
  __int64 v70; // [rsp+38h] [rbp-31h] BYREF
  __int64 v71; // [rsp+40h] [rbp-29h] BYREF
  __int64 v72; // [rsp+48h] [rbp-21h] BYREF
  _QWORD v73[2]; // [rsp+50h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-9h] BYREF
  HSTRING string; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  if ( *((struct Windows::UI::Composition::ICompositor **)this + 12) != a2 )
  {
    if ( a2 )
      (*(void (__fastcall **)(struct Windows::UI::Composition::ICompositor *))(*(_QWORD *)a2 + 8LL))(a2);
    v6 = *((_QWORD *)this + 12);
    *((_QWORD *)this + 12) = a2;
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  Hwnd = Windows::UI::Core::DesktopWindowContentBridge::CreateHwnd((LONG_PTR)this - 40, a3);
  v8 = Hwnd;
  if ( Hwnd < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)Hwnd,
      v68);
    return v8;
  }
  v70 = 0;
  v9 = **(__int64 (__fastcall ***)(struct Windows::UI::Composition::ICompositor *, GUID *, __int64 *))a2;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v70);
  v10 = v9(a2, &GUID_d1d6b44a_72fa_4fa1_ba27_a5f207cb37ca, &v70);
  if ( v10 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)v10,
      v68);
  v11 = v70;
  v12 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v70 + 48LL);
  v13 = (_QWORD *)((char *)this + 112);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 112);
  v14 = v12(v11, (char *)this + 112);
  v8 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)v14,
      v68);
LABEL_90:
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v70);
    return v8;
  }
  v15 = *v13;
  v16 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)*v13 + 88LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 120);
  v17 = v16(v15, (char *)this + 120);
  v8 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)v17,
      v68);
    v53 = v70;
    if ( v70 )
    {
      v70 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    }
    return v8;
  }
  v69 = 0;
  v18 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 13);
  v19 = **v18;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v69);
  v20 = v19(v18, &GUID_da5d6502_31dd_5bfe_bd07_99f4e5bb5098, &v69);
  if ( v20 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)v20,
      v68);
  v21 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v69 + 56LL))(v69, *((_QWORD *)this + 15));
  v8 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)v21,
      v68);
    v64 = v69;
    if ( v69 )
    {
      v69 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
    }
    v65 = v70;
    if ( v70 )
    {
      v70 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
    }
    return v8;
  }
  hstringHeader.Reserved.Reserved1 = (char *)this - 40;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 152);
  v22 = Microsoft::WRL::Details::MakeAndInitialize<Windows::UI::Core::DesktopWindowLayout,Windows::UI::Core::DesktopWindowLayout,Windows::UI::Core::DesktopWindowContentBridge *>(
          (char *)this + 152,
          &hstringHeader);
  v8 = v22;
  if ( v22 < 0 )
  {
    v66 = 55;
LABEL_82:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v66,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)v22,
      v68);
LABEL_89:
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v69);
    goto LABEL_90;
  }
  LODWORD(hstringHeader.Reserved.Reserved1) = ~*((_DWORD *)this + 16);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 160);
  v22 = Microsoft::WRL::Details::MakeAndInitialize<Windows::UI::Core::DesktopWindowInformation,Windows::UI::Core::IWindowInformation,int,HWND__ * &>(
          (char *)this + 160,
          &hstringHeader,
          (char *)this + 64);
  v8 = v22;
  if ( v22 < 0 )
  {
    v66 = 56;
    goto LABEL_82;
  }
  v71 = 0;
  string = 0;
  v23 = WindowsCreateStringReference(
          L"Windows.UI.Composition.CompositionIslandEnvironment",
          0x33u,
          &hstringHeader,
          &string);
  if ( v23 < 0 )
  {
    RaiseException(v23, 1u, 0, 0);
    __debugbreak();
  }
  v24 = string;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v71);
  ActivationFactory = RoGetActivationFactory(v24, &GUID_132e54b7_bd29_5cf0_b131_c1dea47235ec, &v71);
  v8 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v68);
LABEL_88:
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v71);
    goto LABEL_89;
  }
  v26 = v71;
  v27 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v71 + 48LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 144);
  v28 = v27(v26, (char *)this + 144);
  v8 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)v28,
      v68);
    v61 = v71;
    if ( v71 )
    {
      v71 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
    }
    v62 = v69;
    if ( v69 )
    {
      v69 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
    }
    v63 = v70;
    if ( v70 )
    {
      v70 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
    }
    return v8;
  }
  v72 = 0;
  v29 = Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionIslandEnvironment>::As<Windows::UI::Composition::ICompositionIslandEnvironmentPartner>(
          (char *)this + 144,
          &v72);
  if ( v29 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)v29,
      v68);
  v30 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v72 + 56LL))(
          v72,
          ((unsigned __int64)this - 16) & ((unsigned __int128)-(__int128)((unsigned __int64)this - 40) >> 64));
  v8 = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)v30,
      v68);
    v54 = v72;
    if ( v72 )
    {
      v72 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    }
    v55 = v71;
    if ( v71 )
    {
      v71 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    }
    v56 = v69;
    if ( v69 )
    {
      v69 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    }
    v57 = v70;
    if ( v70 )
    {
      v70 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    }
    return v8;
  }
  Windows::UI::Core::DesktopWindowContentBridge::CacheDpiMode((Windows::UI::Core::DesktopWindowContentBridge *)((char *)this - 40));
  v31 = (Windows::UI::Core::DesktopWindowContentBridge *)(unsigned int)(*((_DWORD *)this + 22) - 2);
  if ( *((_DWORD *)this + 22) == 2 )
  {
    System_ScaleFactor = Windows::UI::Core::DesktopWindowContentBridge::Get_System_ScaleFactor(v31);
    updated = Windows::UI::Core::DesktopWindowContentBridge::UpdateScaleFactor(
                (Windows::UI::Core::DesktopWindowContentBridge *)((char *)this - 40),
                System_ScaleFactor);
    v8 = updated;
    if ( updated >= 0 )
      goto LABEL_22;
    v60 = 80;
LABEL_87:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v60,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)updated,
      v68);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v72);
    goto LABEL_88;
  }
  v32 = (_DWORD)v31 == 1;
  v33 = (Windows::UI::Core::DesktopWindowContentBridge *)((char *)this - 40);
  if ( !v32 )
  {
    Window_ScaleFactor = Windows::UI::Core::DesktopWindowContentBridge::Get_Window_ScaleFactor(v33);
    updated = Windows::UI::Core::DesktopWindowContentBridge::UpdateScaleFactor(
                (Windows::UI::Core::DesktopWindowContentBridge *)((char *)this - 40),
                Window_ScaleFactor);
    v8 = updated;
    if ( updated >= 0 )
      goto LABEL_22;
    v60 = 96;
    goto LABEL_87;
  }
  v34 = Windows::UI::Core::DesktopWindowContentBridge::Get_Window_ScaleFactor(v33);
  v35 = Windows::UI::Core::DesktopWindowContentBridge::UpdateScaleFactor(
          (Windows::UI::Core::DesktopWindowContentBridge *)((char *)this - 40),
          v34);
  v8 = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x57,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)v35,
      v68);
    v49 = v72;
    if ( v72 )
    {
      v72 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    }
    v50 = v71;
    if ( v71 )
    {
      v71 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    }
    v51 = v69;
    if ( v69 )
    {
      v69 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    }
    v52 = v70;
    if ( v70 )
    {
      v70 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    }
    return v8;
  }
LABEL_22:
  v73[0] = 0;
  string = 0;
  v36 = WindowsCreateStringReference(L"Windows.UI.Internal.Input.InputSite", 0x23u, &hstringHeader, &string);
  if ( v36 < 0 )
  {
    RaiseException(v36, 1u, 0, 0);
    JUMPOUT(0x180026062LL);
  }
  v37 = string;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v73);
  v38 = RoGetActivationFactory(v37, &GUID_73f80911_7a51_5b0f_906b_f6402ea6c3cb, v73);
  if ( v38 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x68,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)v38,
      v68);
  *(_OWORD *)&hstringHeader.Reserved.Reserved1 = 0;
  hstringHeader.Reserved.Reserved1 = (PVOID)*((unsigned int *)this + 16);
  *(_DWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
  hstringHeader.Reserved.Reserved2[12] = 0;
  v39 = v73[0];
  v40 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING_HEADER *, char *))(*(_QWORD *)v73[0] + 96LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 168);
  v41 = v40(v39, *v13, &hstringHeader, (char *)this + 168);
  if ( v41 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)v41,
      v68);
  v42 = Microsoft::WRL::ComPtr<Windows::UI::Internal::Input::IInputSite>::As<IInputSiteForIslandSitePartnerInterop>(
          (char *)this + 168,
          (char *)this + 176);
  if ( v42 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)v42,
      v68);
  v43 = v73[0];
  if ( v73[0] )
  {
    v73[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  v44 = v72;
  if ( v72 )
  {
    v72 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
  v45 = v71;
  if ( v71 )
  {
    v71 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  }
  v46 = v69;
  if ( v69 )
  {
    v69 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  }
  v47 = v70;
  if ( v70 )
  {
    v70 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  }
  return 0;
}

```

## disassembly

```asm
0x180025870  mov     [rsp-8+arg_18], rbx
0x180025875  push    rbp
0x180025876  push    rsi
0x180025877  push    rdi
0x180025878  push    r12
0x18002587a  push    r13
0x18002587c  push    r14
0x18002587e  push    r15
0x180025880  lea     rbp, [rsp-27h]
0x180025885  sub     rsp, 90h
0x18002588c  mov     rax, cs:__security_cookie
0x180025893  xor     rax, rsp
0x180025896  mov     [rbp+57h+var_40], rax
0x18002589a  mov     rbx, r8
0x18002589d  mov     rdi, rdx
0x1800258a0  mov     rsi, rcx
0x1800258a3  xor     r12d, r12d
0x1800258a6  cmp     [rcx+60h], rdx
0x1800258aa  jz      short loc_1800258DB
0x1800258ac  test    rdx, rdx
0x1800258af  jz      short loc_1800258C1
0x1800258b1  mov     rax, [rdx]
0x1800258b4  mov     rcx, rdx
0x1800258b7  mov     rax, [rax+8]
0x1800258bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258c0  nop
0x1800258c1  mov     rcx, [rsi+60h]
0x1800258c5  mov     [rsi+60h], rdi
0x1800258c9  test    rcx, rcx
0x1800258cc  jz      short loc_1800258DB
0x1800258ce  mov     rax, [rcx]
0x1800258d1  mov     rax, [rax+10h]
0x1800258d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258da  nop
0x1800258db  lea     r14, [rsi-28h]
0x1800258df  mov     rdx, rbx; hWndParent
0x1800258e2  mov     rcx, r14; dwNewLong
0x1800258e5  call    ?CreateHwnd@DesktopWindowContentBridge@Core@UI@Windows@@AEAAJPEAUHWND__@@@Z; Windows::UI::Core::DesktopWindowContentBridge::CreateHwnd(HWND__ *)
0x1800258ea  mov     ebx, eax
0x1800258ec  test    eax, eax
0x1800258ee  js      loc_180025D51
0x1800258f4  mov     [rbp+57h+var_88], r12
0x1800258f8  mov     rax, [rdi]
0x1800258fb  mov     rbx, [rax]
0x1800258fe  lea     rcx, [rbp+57h+var_88]
0x180025902  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180025907  lea     r8, [rbp+57h+var_88]
0x18002590b  lea     rdx, _GUID_d1d6b44a_72fa_4fa1_ba27_a5f207cb37ca
0x180025912  mov     rcx, rdi
0x180025915  mov     rax, rbx
0x180025918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002591d  mov     rcx, [rbp+5Fh]; this
0x180025921  test    eax, eax
0x180025923  js      loc_180025D6B
0x180025929  mov     rdi, [rbp+57h+var_88]
0x18002592d  mov     rax, [rdi]
0x180025930  mov     rbx, [rax+30h]
0x180025934  lea     r13, [rsi+70h]
0x180025938  mov     rcx, r13
0x18002593b  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180025940  mov     rdx, r13
0x180025943  mov     rcx, rdi
0x180025946  mov     rax, rbx
0x180025949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002594e  mov     ebx, eax
0x180025950  test    eax, eax
0x180025952  js      loc_180025F86
0x180025958  mov     rdi, [r13+0]
0x18002595c  mov     rax, [rdi]
0x18002595f  mov     rbx, [rax+58h]
0x180025963  lea     r15, [rsi+78h]
0x180025967  mov     rcx, r15
0x18002596a  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18002596f  mov     rdx, r15
0x180025972  mov     rcx, rdi
0x180025975  mov     rax, rbx
0x180025978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002597d  mov     ebx, eax
0x18002597f  test    eax, eax
0x180025981  js      loc_180025D80
0x180025987  mov     [rbp+57h+var_90], r12
0x18002598b  mov     rdi, [rsi+68h]
0x18002598f  mov     rax, [rdi]
0x180025992  mov     rbx, [rax]
0x180025995  lea     rcx, [rbp+57h+var_90]
0x180025999  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18002599e  lea     r8, [rbp+57h+var_90]
0x1800259a2  lea     rdx, _GUID_da5d6502_31dd_5bfe_bd07_99f4e5bb5098
0x1800259a9  mov     rcx, rdi
0x1800259ac  mov     rax, rbx
0x1800259af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259b4  nop
0x1800259b5  mov     rcx, [rbp+5Fh]; this
0x1800259b9  test    eax, eax
0x1800259bb  js      loc_180025DB5
0x1800259c1  mov     rcx, [rbp+57h+var_90]
0x1800259c5  mov     rax, [rcx]
0x1800259c8  mov     rdx, [r15]
0x1800259cb  mov     rax, [rax+38h]
0x1800259cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259d4  mov     ebx, eax
0x1800259d6  test    eax, eax
0x1800259d8  js      loc_180025F34
0x1800259de  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r14
0x1800259e2  lea     rbx, [rsi+98h]
0x1800259e9  mov     rcx, rbx
0x1800259ec  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800259f1  lea     rdx, [rbp+57h+hstringHeader]
0x1800259f5  mov     rcx, rbx
0x1800259f8  call    ??$MakeAndInitialize@VDesktopWindowLayout@Core@UI@Windows@@V1234@PEAVDesktopWindowContentBridge@234@@Details@WRL@Microsoft@@YAJPEAPEAVDesktopWindowLayout@Core@UI@Windows@@$$QEAPEAVDesktopWindowContentBridge@456@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::UI::Core::DesktopWindowLayout,Windows::UI::Core::DesktopWindowLayout,Windows::UI::Core::DesktopWindowContentBridge *>(Windows::UI::Core::DesktopWindowLayout * *,Windows::UI::Core::DesktopWindowContentBridge * &&)
0x1800259fd  mov     ebx, eax
0x1800259ff  test    eax, eax
0x180025a01  js      loc_180025FA3
0x180025a07  lea     r12, [rsi+40h]
0x180025a0b  mov     eax, [r12]
0x180025a0f  not     eax
0x180025a11  mov     dword ptr [rbp+57h+hstringHeader.Reserved], eax
0x180025a14  lea     rbx, [rsi+0A0h]
0x180025a1b  mov     rcx, rbx
0x180025a1e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180025a23  mov     r8, r12
0x180025a26  lea     rdx, [rbp+57h+hstringHeader]
0x180025a2a  mov     rcx, rbx
0x180025a2d  call    ??$MakeAndInitialize@VDesktopWindowInformation@Core@UI@Windows@@UIWindowInformation@234@HAEAPEAUHWND__@@@Details@WRL@Microsoft@@YAJPEAPEAUIWindowInformation@Core@UI@Windows@@$$QEAHAEAPEAUHWND__@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::UI::Core::DesktopWindowInformation,Windows::UI::Core::IWindowInformation,int,HWND__ * &>(Windows::UI::Core::IWindowInformation * *,int &&,HWND__ * &)
0x180025a32  mov     ebx, eax
0x180025a34  test    eax, eax
0x180025a36  js      loc_180025FAA
0x180025a3c  mov     [rbp+57h+var_80], 0
0x180025a44  mov     [rbp+57h+string], 0
0x180025a4c  lea     r9, [rbp+57h+string]; string
0x180025a50  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180025a54  mov     edx, 33h ; '3'; length
0x180025a59  lea     rcx, ?RuntimeClass_Windows_UI_Composition_CompositionIslandEnvironment@@3QBGB; "Windows.UI.Composition.CompositionIslan"...
0x180025a60  call    cs:__imp_WindowsCreateStringReference
0x180025a66  test    eax, eax
0x180025a68  js      loc_180025FC4
0x180025a6e  mov     rbx, [rbp+57h+string]
0x180025a72  lea     rcx, [rbp+57h+var_80]
0x180025a76  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180025a7b  lea     r8, [rbp+57h+var_80]
0x180025a7f  lea     rdx, _GUID_132e54b7_bd29_5cf0_b131_c1dea47235ec
0x180025a86  mov     rcx, rbx
0x180025a89  call    cs:__imp_RoGetActivationFactory
0x180025a8f  mov     ebx, eax
0x180025a91  test    eax, eax
0x180025a93  js      loc_180025FD7
0x180025a99  mov     rdi, [rbp+57h+var_80]
0x180025a9d  mov     rax, [rdi]
0x180025aa0  mov     rbx, [rax+30h]
0x180025aa4  lea     r15, [rsi+90h]
0x180025aab  mov     rcx, r15
0x180025aae  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180025ab3  mov     rdx, r15
0x180025ab6  mov     rcx, rdi
0x180025ab9  mov     rax, rbx
0x180025abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ac1  mov     ebx, eax
0x180025ac3  xor     edi, edi
0x180025ac5  test    eax, eax
0x180025ac7  js      loc_180025EC8
0x180025acd  mov     [rbp+57h+var_78], rdi
0x180025ad1  lea     rdx, [rbp+57h+var_78]
0x180025ad5  mov     rcx, r15
0x180025ad8  call    ??$As@UICompositionIslandEnvironmentPartner@Composition@UI@Windows@@@?$ComPtr@UICompositionIslandEnvironment@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICompositionIslandEnvironmentPartner@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionIslandEnvironment>::As<Windows::UI::Composition::ICompositionIslandEnvironmentPartner>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionIslandEnvironmentPartner>>)
0x180025add  mov     rcx, [rbp+5Fh]; this
0x180025ae1  xor     r15d, r15d
0x180025ae4  test    eax, eax
0x180025ae6  js      loc_180025DCA
0x180025aec  mov     rcx, [rbp+57h+var_78]
0x180025af0  mov     r9, [rcx]
0x180025af3  mov     rax, r14
0x180025af6  lea     r8, [rsi-10h]
0x180025afa  neg     rax
0x180025afd  sbb     rdx, rdx
0x180025b00  and     rdx, r8
0x180025b03  mov     rax, [r9+38h]
0x180025b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b0c  mov     ebx, eax
0x180025b0e  test    eax, eax
0x180025b10  js      loc_180025E1E
0x180025b16  mov     rcx, r14; this
0x180025b19  call    ?CacheDpiMode@DesktopWindowContentBridge@Core@UI@Windows@@AEAAXXZ; Windows::UI::Core::DesktopWindowContentBridge::CacheDpiMode(void)
0x180025b1e  mov     ecx, [rsi+58h]
0x180025b21  sub     ecx, 2; this
0x180025b24  jz      loc_180025FF1
0x180025b2a  cmp     ecx, 1
0x180025b2d  mov     rcx, r14; this
0x180025b30  jnz     loc_180025EA4
0x180025b36  call    ?Get_Window_ScaleFactor@DesktopWindowContentBridge@Core@UI@Windows@@AEAAMXZ; Windows::UI::Core::DesktopWindowContentBridge::Get_Window_ScaleFactor(void)
0x180025b3b  movaps  xmm1, xmm0; float
0x180025b3e  mov     rcx, r14; this
0x180025b41  call    ?UpdateScaleFactor@DesktopWindowContentBridge@Core@UI@Windows@@AEAAJM@Z; Windows::UI::Core::DesktopWindowContentBridge::UpdateScaleFactor(float)
0x180025b46  mov     ebx, eax
0x180025b48  test    eax, eax
0x180025b4a  js      loc_180025CC9
0x180025b50  mov     [rbp+57h+var_70], r15
0x180025b54  mov     [rbp+57h+string], r15
0x180025b58  lea     r9, [rbp+57h+string]; string
0x180025b5c  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180025b60  mov     edx, 23h ; '#'; length
0x180025b65  lea     rcx, ?RuntimeClass_Windows_UI_Internal_Input_InputSite@@3QBGB; "Windows.UI.Internal.Input.InputSite"
0x180025b6c  call    cs:__imp_WindowsCreateStringReference
0x180025b72  test    eax, eax
0x180025b74  js      loc_180026050
0x180025b7a  mov     rbx, [rbp+57h+string]
0x180025b7e  lea     rcx, [rbp+57h+var_70]
0x180025b82  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180025b87  lea     r8, [rbp+57h+var_70]
0x180025b8b  lea     rdx, _GUID_73f80911_7a51_5b0f_906b_f6402ea6c3cb
0x180025b92  mov     rcx, rbx
0x180025b95  call    cs:__imp_RoGetActivationFactory
0x180025b9b  mov     rcx, [rbp+5Fh]; this
0x180025b9f  test    eax, eax
0x180025ba1  js      loc_180025DDF
0x180025ba7  xorps   xmm0, xmm0
0x180025baa  movups  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x180025bae  mov     eax, [r12]
0x180025bb2  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x180025bb6  mov     dword ptr [rbp+57h+hstringHeader.Reserved+8], r15d
0x180025bba  mov     byte ptr [rbp+57h+hstringHeader.Reserved+0Ch], r15b
0x180025bbe  mov     rdi, [rbp+57h+var_70]
0x180025bc2  mov     rax, [rdi]
0x180025bc5  mov     rbx, [rax+60h]
0x180025bc9  lea     r14, [rsi+0A8h]
0x180025bd0  mov     rcx, r14
0x180025bd3  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180025bd8  movaps  xmm0, xmmword ptr [rbp+57h+hstringHeader.Reserved]
0x180025bdc  movdqa  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x180025be1  mov     r9, r14
0x180025be4  lea     r8, [rbp+57h+hstringHeader]
0x180025be8  mov     rdx, [r13+0]
0x180025bec  mov     rcx, rdi
0x180025bef  mov     rax, rbx
0x180025bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bf7  mov     rcx, [rbp+5Fh]; this
0x180025bfb  test    eax, eax
0x180025bfd  js      loc_180025DF4
0x180025c03  lea     rdx, [rsi+0B0h]
0x180025c0a  mov     rcx, r14
0x180025c0d  call    ??$As@UIInputSiteForIslandSitePartnerInterop@@@?$ComPtr@UIInputSite@Input@Internal@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIInputSiteForIslandSitePartnerInterop@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Internal::Input::IInputSite>::As<IInputSiteForIslandSitePartnerInterop>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IInputSiteForIslandSitePartnerInterop>>)
0x180025c12  mov     rcx, [rbp+5Fh]; this
0x180025c16  test    eax, eax
0x180025c18  js      loc_180025E09
0x180025c1e  mov     rcx, [rbp+57h+var_70]
0x180025c22  test    rcx, rcx
0x180025c25  jz      short loc_180025C38
0x180025c27  mov     [rbp+57h+var_70], r15
0x180025c2b  mov     rax, [rcx]
0x180025c2e  mov     rax, [rax+10h]
0x180025c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c37  nop
0x180025c38  mov     rcx, [rbp+57h+var_78]
0x180025c3c  test    rcx, rcx
0x180025c3f  jz      short loc_180025C52
0x180025c41  mov     [rbp+57h+var_78], r15
0x180025c45  mov     rax, [rcx]
0x180025c48  mov     rax, [rax+10h]
0x180025c4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c51  nop
0x180025c52  mov     rcx, [rbp+57h+var_80]
0x180025c56  test    rcx, rcx
0x180025c59  jz      short loc_180025C6C
0x180025c5b  mov     [rbp+57h+var_80], r15
0x180025c5f  mov     rax, [rcx]
0x180025c62  mov     rax, [rax+10h]
0x180025c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c6b  nop
0x180025c6c  mov     rcx, [rbp+57h+var_90]
0x180025c70  test    rcx, rcx
0x180025c73  jz      short loc_180025C86
0x180025c75  mov     [rbp+57h+var_90], r15
0x180025c79  mov     rax, [rcx]
0x180025c7c  mov     rax, [rax+10h]
0x180025c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c85  nop
0x180025c86  mov     rcx, [rbp+57h+var_88]
0x180025c8a  test    rcx, rcx
0x180025c8d  jz      short loc_180025CA0
0x180025c8f  mov     [rbp+57h+var_88], r15
0x180025c93  mov     rax, [rcx]
0x180025c96  mov     rax, [rax+10h]
0x180025c9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c9f  nop
0x180025ca0  xor     eax, eax
0x180025ca2  mov     rcx, [rbp+57h+var_40]
0x180025ca6  xor     rcx, rsp; StackCookie
0x180025ca9  call    __security_check_cookie
0x180025cae  mov     rbx, [rsp+0C0h+arg_18]
0x180025cb6  add     rsp, 90h
0x180025cbd  pop     r15
0x180025cbf  pop     r14
0x180025cc1  pop     r13
0x180025cc3  pop     r12
0x180025cc5  pop     rdi
0x180025cc6  pop     rsi
0x180025cc7  pop     rbp
0x180025cc8  retn
0x180025cc9  mov     rcx, [rbp+5Fh]; this
0x180025ccd  mov     r9d, ebx; char *
0x180025cd0  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\advcore\\winrt\\on"...
  ... truncated ...
```
