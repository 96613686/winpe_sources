# CreateProtocolActivatedEventArgs(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,Windows::System::Internal::Launch::LauncherPluginActivationType,IInspectable * *)

- ea: `0x18007a6b0`
- end: `0x18007aecc`
- name: `?CreateProtocolActivatedEventArgs@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@W4LauncherPluginActivationType@Launch@Internal@System@4@PEAPEAUIInspectable@@@Z`
- size: `2076`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c8d10`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x1800272d8`
- `0x18002cec0`
- `0x180034ba0`
- `0x18004966c`
- `0x18007a6b0`
- `0x18008a030`
- `0x1800c7880`
- `0x1800c7950`
- `0x1800cadfc`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a758`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a797`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a8a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a8e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ae67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ae8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a758`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a797`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a8a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a8e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ae67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ae8b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007a9cf`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007a9cf`

## string_xrefs

- `0x18007a7b4`: `Windows.Foundation.Uri`
- `0x18007a72d`: `onecoreuap\shell\windows.system.launcher\lib\launcheractivationbrokerplugin.cpp`
- `0x18007a780`: `onecoreuap\shell\windows.system.launcher\lib\launcheractivationbrokerplugin.cpp`
- `0x18007a7de`: `onecoreuap\shell\windows.system.launcher\lib\launcheractivationbrokerplugin.cpp`
- `0x18007a832`: `onecoreuap\shell\windows.system.launcher\lib\launcheractivationbrokerplugin.cpp`
- `0x18007a8cf`: `onecoreuap\shell\windows.system.launcher\lib\launcheractivationbrokerplugin.cpp`
- `0x18007a934`: `onecoreuap\shell\windows.system.launcher\lib\launcheractivationbrokerplugin.cpp`
- `0x18007a9e2`: `onecoreuap\shell\windows.system.launcher\lib\launcheractivationbrokerplugin.cpp`
- `0x18007aa3a`: `onecoreuap\shell\windows.system.launcher\lib\launcheractivationbrokerplugin.cpp`
- `0x18007aaa5`: `onecoreuap\shell\windows.system.launcher\lib\launcheractivationbrokerplugin.cpp`
- `0x18007ab04`: `onecoreuap\shell\windows.system.launcher\lib\launcheractivationbrokerplugin.cpp`
- `0x18007ab72`: `onecoreuap\shell\windows.system.launcher\lib\launcheractivationbrokerplugin.cpp`
- `0x18007ac18`: `onecoreuap\shell\windows.system.launcher\lib\launcheractivationbrokerplugin.cpp`
- `0x18007acaa`: `onecoreuap\shell\windows.system.launcher\lib\launcheractivationbrokerplugin.cpp`
- `0x18007ad62`: `onecoreuap\shell\windows.system.launcher\lib\launcheractivationbrokerplugin.cpp`
- `0x18007ae07`: `onecoreuap\shell\windows.system.launcher\lib\launcheractivationbrokerplugin.cpp`
- `0x18007a9b0`: `Windows.Storage.Streams.DataWriter`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CreateProtocolActivatedEventArgs(__int64 a1, int a2, __int64 a3)
{
  __int64 (__fastcall *v6)(__int64, PVOID, struct Windows::Foundation::IPropertyValue **); // rbx
  HSTRING_HEADER *v7; // rax
  int v8; // eax
  unsigned int v9; // ebx
  struct Windows::Foundation::IPropertyValue *v10; // rdi
  __int64 (__fastcall *v11)(struct Windows::Foundation::IPropertyValue *, HSTRING *); // rbx
  int v12; // eax
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, HSTRING, HSTRING *); // rbx
  int v16; // eax
  __int64 v17; // rdx
  __int64 (__fastcall *v18)(__int64, PVOID, struct Windows::Foundation::IPropertyValue **); // rbx
  HSTRING_HEADER *v19; // rax
  struct Windows::Foundation::IPropertyValue *v20; // rdi
  __int64 (__fastcall *v21)(struct Windows::Foundation::IPropertyValue *, HSTRING *); // rbx
  int v22; // eax
  __int64 (__fastcall *v23)(__int64, PVOID, char *); // rbx
  HSTRING_HEADER *v24; // rax
  int v25; // eax
  __int64 v26; // rdx
  __int64 (__fastcall *v27)(__int64, PVOID, struct Windows::Foundation::IPropertyValue **); // rbx
  HSTRING_HEADER *v28; // rax
  int ActivationFactory; // eax
  __int64 v30; // rcx
  int v31; // eax
  __int64 v32; // rcx
  int v33; // eax
  __int64 v34; // rcx
  int v35; // eax
  __int64 v36; // rcx
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, __int64 *); // rbx
  int v39; // eax
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 (__fastcall *v42)(__int64, PVOID, _BYTE *); // rbx
  HSTRING_HEADER *v43; // rax
  int v44; // eax
  __int64 v45; // rdx
  __int64 (__fastcall *v46)(__int64, PVOID, struct Windows::Foundation::IPropertyValue **); // rbx
  HSTRING_HEADER *v47; // rax
  int v48; // eax
  __int64 v49; // rdx
  struct IUnknown *v50; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  int v52; // eax
  __int64 v53; // rdx
  int v54; // eax
  __int64 v55; // rdx
  int v57; // [rsp+20h] [rbp-99h]
  int v58; // [rsp+20h] [rbp-99h]
  HSTRING string; // [rsp+30h] [rbp-89h] BYREF
  HSTRING v60; // [rsp+38h] [rbp-81h] BYREF
  char v61; // [rsp+40h] [rbp-79h] BYREF
  _BYTE v62[7]; // [rsp+41h] [rbp-78h] BYREF
  HSTRING v63; // [rsp+48h] [rbp-71h] BYREF
  __int64 v64; // [rsp+50h] [rbp-69h] BYREF
  __int64 v65; // [rsp+58h] [rbp-61h] BYREF
  __int64 v66; // [rsp+60h] [rbp-59h] BYREF
  struct Windows::Foundation::IPropertyValue *v67; // [rsp+68h] [rbp-51h] BYREF
  __int64 v68; // [rsp+70h] [rbp-49h] BYREF
  __int64 v69; // [rsp+78h] [rbp-41h] BYREF
  int v70[2]; // [rsp+80h] [rbp-39h] BYREF
  struct IUnknown *v71; // [rsp+88h] [rbp-31h] BYREF
  __int64 (__fastcall ***v72)(_QWORD, GUID *, __int64); // [rsp+90h] [rbp-29h] BYREF
  unsigned int v73; // [rsp+98h] [rbp-21h] BYREF
  HSTRING v74; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v75; // [rsp+A8h] [rbp-11h] BYREF
  HSTRING v76; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v77; // [rsp+B8h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v79; // [rsp+D8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v67 = 0;
  v6 = *(__int64 (__fastcall **)(__int64, PVOID, struct Windows::Foundation::IPropertyValue **))(*(_QWORD *)a1 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
  v7 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_180123088);
  v8 = v6(a1, v7[1].Reserved.Reserved1, &v67);
  v9 = v8;
  if ( v8 >= 0 )
  {
    string = 0;
    v10 = v67;
    v11 = *(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValue *, HSTRING *))(*(_QWORD *)v67 + 152LL);
    WindowsDeleteString(0);
    string = 0;
    v12 = v11(v10, &string);
    v9 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4A,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcheractivationbrokerplugin.cpp",
        (const char *)(unsigned int)v12,
        v57);
LABEL_5:
      WindowsDeleteString(string);
LABEL_74:
      string = 0;
      goto LABEL_75;
    }
    v64 = 0;
    v79 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Foundation.Uri", 0x17u, 0x16u);
    v13 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
            v79,
            &v64);
    v9 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4D,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcheractivationbrokerplugin.cpp",
        (const char *)(unsigned int)v13,
        v57);
LABEL_8:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
      goto LABEL_5;
    }
    v63 = 0;
    v14 = v64;
    v15 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)v64 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
    v16 = v15(v14, string, &v63);
    v9 = v16;
    if ( v16 < 0 )
    {
      v17 = 79;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcheractivationbrokerplugin.cpp",
        (const char *)(unsigned int)v16,
        v57);
LABEL_12:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
      goto LABEL_8;
    }
    v18 = *(__int64 (__fastcall **)(__int64, PVOID, struct Windows::Foundation::IPropertyValue **))(*(_QWORD *)a1 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
    v19 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_1801230A8);
    v16 = v18(a1, v19[1].Reserved.Reserved1, &v67);
    v9 = v16;
    if ( v16 < 0 )
    {
      v17 = 81;
      goto LABEL_11;
    }
    v60 = 0;
    v20 = v67;
    v21 = *(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValue *, HSTRING *))(*(_QWORD *)v67 + 152LL);
    WindowsDeleteString(0);
    v60 = 0;
    v22 = v21(v20, &v60);
    v9 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x53,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcheractivationbrokerplugin.cpp",
        (const char *)(unsigned int)v22,
        v57);
LABEL_17:
      WindowsDeleteString(v60);
      v60 = 0;
      goto LABEL_12;
    }
    v61 = 0;
    v65 = 0;
    v23 = *(__int64 (__fastcall **)(__int64, PVOID, char *))(*(_QWORD *)a1 + 64LL);
    v24 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_180123080);
    v25 = v23(a1, v24[1].Reserved.Reserved1, &v61);
    v9 = v25;
    if ( v25 < 0 )
    {
      v26 = 87;
LABEL_20:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v26,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcheractivationbrokerplugin.cpp",
        (const char *)(unsigned int)v25,
        v57);
LABEL_21:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
      goto LABEL_17;
    }
    if ( v61 )
    {
      v27 = *(__int64 (__fastcall **)(__int64, PVOID, struct Windows::Foundation::IPropertyValue **))(*(_QWORD *)a1 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
      v28 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_180123080);
      v25 = v27(a1, v28[1].Reserved.Reserved1, &v67);
      v9 = v25;
      if ( v25 < 0 )
      {
        v26 = 90;
        goto LABEL_20;
      }
      v66 = 0;
      v79 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Storage.Streams.DataWriter",
        0x23u,
        0x22u);
      ActivationFactory = RoGetActivationFactory(v79, &GUID_338c67c2_8b84_4c2b_9c50_7b8767847a1f, &v66);
      v9 = ActivationFactory;
      if ( ActivationFactory < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5C,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcheractivationbrokerplugin.cpp",
          (const char *)(unsigned int)ActivationFactory,
          v57);
        v30 = v66;
        if ( v66 )
        {
          v66 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
        }
        goto LABEL_21;
      }
      v69 = 0;
      v31 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v66 + 48LL))(v66, 0, &v69);
      v9 = v31;
      if ( v31 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5F,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcheractivationbrokerplugin.cpp",
          (const char *)(unsigned int)v31,
          v57);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
        v32 = v66;
        if ( v66 )
        {
          v66 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
        }
        goto LABEL_21;
      }
      v73 = 0;
      v77 = 0;
      v33 = (*(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValue *, unsigned int *, __int64 *))(*(_QWORD *)v67 + 208LL))(
              v67,
              &v73,
              &v77);
      v9 = v33;
      if ( v33 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x63,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcheractivationbrokerplugin.cpp",
          (const char *)(unsigned int)v33,
          v57);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
        v34 = v66;
        if ( v66 )
        {
          v66 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
        }
        goto LABEL_21;
      }
      v35 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v69 + 96LL))(v69, v73, v77);
      v9 = v35;
      if ( v35 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x65,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcheractivationbrokerplugin.cpp",
          (const char *)(unsigned int)v35,
          v57);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
        v36 = v66;
        if ( v66 )
        {
          v66 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
        }
        goto LABEL_21;
      }
      v37 = v69;
      v38 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v69 + 248LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
      v39 = v38(v37, &v65);
      v9 = v39;
      if ( v39 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x66,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcheractivationbrokerplugin.cpp",
          (const char *)(unsigned int)v39,
          v57);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
        v40 = v66;
        if ( v66 )
        {
          v66 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
        }
        goto LABEL_21;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
      v41 = v66;
      if ( v66 )
      {
        v66 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      }
    }
    if ( a2 == 4 )
    {
      v62[0] = 0;
      v68 = 0;
      v42 = *(__int64 (__fastcall **)(__int64, PVOID, _BYTE *))(*(_QWORD *)a1 + 64LL);
      v43 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_180123098);
      v44 = v42(a1, v43[1].Reserved.Reserved1, v62);
      v9 = v44;
      if ( v44 < 0 )
      {
        v45 = 109;
LABEL_50:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v45,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcheractivationbrokerplugin.cpp",
          (const char *)(unsigned int)v44,
          v57);
LABEL_51:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
        goto LABEL_21;
      }
      if ( v62[0] )
      {
        v46 = *(__int64 (__fastcall **)(__int64, PVOID, struct Windows::Foundation::IPropertyValue **))(*(_QWORD *)a1 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
        v47 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                &hstringHeader,
                (const WCHAR **)off_180123098);
        v44 = v46(a1, v47[1].Reserved.Reserved1, &v67);
        v9 = v44;
        if ( v44 < 0 )
        {
          v45 = 112;
          goto LABEL_50;
        }
        v71 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
        v48 = ReadIUnknownFromUInt8ArrayPropertyValue(v67, &v71);
        v9 = v48;
        if ( v48 < 0 )
        {
          v49 = 114;
LABEL_57:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v49,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcheractivationbrokerplugin.cpp",
            (const char *)(unsigned int)v48,
            v57);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
          goto LABEL_51;
        }
        v50 = v71;
        QueryInterface = v71->lpVtbl->QueryInterface;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
        v48 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))QueryInterface)(
                v50,
                &GUID_d581293a_6de9_4d28_9378_f86782e182bb,
                &v68);
        v9 = v48;
        if ( v48 < 0 )
        {
          v49 = 116;
          goto LABEL_57;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
      }
      v72 = 0;
      *(_QWORD *)v70 = v68;
      v74 = v60;
      v75 = v65;
      v76 = v63;
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v72);
      v52 = Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::Launch::ProtocolForResultsActivatedEventArgs,Windows::System::Internal::Launch::ProtocolForResultsActivatedEventArgs,Windows::Foundation::IUriRuntimeClass *,Windows::Storage::Streams::IBuffer *,HSTRING__ *,Windows::System::IProtocolForResultsOperation *>(
              (unsigned int)&v72,
              (unsigned int)&v76,
              (unsigned int)&v75,
              (unsigned int)&v74,
              (__int64)v70);
      v9 = v52;
      if ( v52 < 0 )
      {
        v53 = 124;
LABEL_63:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v53,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcheractivationbrokerplugin.cpp",
          (const char *)(unsigned int)v52,
          v58);
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v72);
        goto LABEL_51;
      }
      v52 = (**v72)(v72, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, a3);
      v9 = v52;
      if ( v52 < 0 )
      {
        v53 = 125;
        goto LABEL_63;
      }
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v72);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
LABEL_73:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
      WindowsDeleteString(v60);
      v60 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
      WindowsDeleteString(string);
      v9 = 0;
      goto LABEL_74;
    }
    *(_QWORD *)v70 = 0;
    v76 = v60;
    v75 = v65;
    v74 = v63;
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v70);
    v54 = Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::Launch::ProtocolActivatedEventArgs,Windows::System::Internal::Launch::ProtocolActivatedEventArgs,Windows::Foundation::IUriRuntimeClass *,Windows::Storage::Streams::IBuffer *,HSTRING__ *>(
            v70,
            &v74,
            &v75,
            &v76);
    v9 = v54;
    if ( v54 >= 0 )
    {
      v54 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64))v70)(
              *(_QWORD *)v70,
              &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
              a3);
      v9 = v54;
      if ( v54 >= 0 )
      {
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v70);
        goto LABEL_73;
      }
      v55 = 135;
    }
    else
    {
      v55 = 134;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v55,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcheractivationbrokerplugin.cpp",
      (const char *)(unsigned int)v54,
      v57);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v70);
    goto LABEL_21;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x48,
    (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcheractivationbrokerplugin.cpp",
    (const char *)(unsigned int)v8,
    v57);
LABEL_75:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
  return v9;
}

```

## disassembly

```asm
0x18007a6b0  mov     [rsp-8+arg_8], rbx
0x18007a6b5  mov     [rsp-8+arg_18], rsi
0x18007a6ba  push    rbp
0x18007a6bb  push    rdi
0x18007a6bc  push    r12
0x18007a6be  push    r14
0x18007a6c0  push    r15
0x18007a6c2  lea     rbp, [rsp-37h]
0x18007a6c7  sub     rsp, 0F0h
0x18007a6ce  mov     rax, cs:__security_cookie
0x18007a6d5  xor     rax, rsp
0x18007a6d8  mov     [rbp+57h+var_30], rax
0x18007a6dc  mov     r15, r8
0x18007a6df  mov     r14d, edx
0x18007a6e2  mov     rsi, rcx
0x18007a6e5  xor     r12d, r12d
0x18007a6e8  mov     [rbp+57h+var_A8], r12
0x18007a6ec  mov     rax, [rcx]
0x18007a6ef  mov     rbx, [rax+30h]
0x18007a6f3  lea     rcx, [rbp+57h+var_A8]
0x18007a6f7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007a6fc  lea     rdx, off_180123088; "RawURI"
0x18007a703  lea     rcx, [rbp+57h+hstringHeader]
0x18007a707  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18007a70c  nop
0x18007a70d  lea     r8, [rbp+57h+var_A8]
0x18007a711  mov     rdx, [rax+18h]
0x18007a715  mov     rcx, rsi
0x18007a718  mov     rax, rbx
0x18007a71b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a720  mov     ebx, eax
0x18007a722  test    eax, eax
0x18007a724  jns     short loc_18007A743
0x18007a726  mov     rcx, [rbp+5Fh]; this
0x18007a72a  mov     r9d, eax; char *
0x18007a72d  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\windows.system.launc"...
0x18007a734  lea     edx, [r12+48h]; void *
0x18007a739  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a73e  jmp     loc_18007AE99
0x18007a743  mov     [rsp+110h+string], r12
0x18007a748  mov     rdi, [rbp+57h+var_A8]
0x18007a74c  mov     rax, [rdi]
0x18007a74f  mov     rbx, [rax+98h]
0x18007a756  xor     ecx, ecx; string
0x18007a758  call    cs:__imp_WindowsDeleteString
0x18007a75e  mov     [rsp+110h+string], r12
0x18007a763  lea     rdx, [rsp+110h+string]
0x18007a768  mov     rcx, rdi
0x18007a76b  mov     rax, rbx
0x18007a76e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a773  mov     ebx, eax
0x18007a775  test    eax, eax
0x18007a777  jns     short loc_18007A7A2
0x18007a779  mov     rcx, [rbp+5Fh]; this
0x18007a77d  mov     r9d, eax; char *
0x18007a780  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\windows.system.launc"...
0x18007a787  mov     edx, 4Ah ; 'J'; void *
0x18007a78c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a791  nop
0x18007a792  mov     rcx, [rsp+110h+string]; string
0x18007a797  call    cs:__imp_WindowsDeleteString
0x18007a79d  jmp     loc_18007AE94
0x18007a7a2  mov     [rbp+57h+var_C0], r12
0x18007a7a6  mov     [rbp+57h+var_38], r12
0x18007a7aa  mov     r9d, 16h; unsigned int
0x18007a7b0  lea     r8d, [r9+1]; unsigned int
0x18007a7b4  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x18007a7bb  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18007a7bf  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007a7c4  lea     rdx, [rbp+57h+var_C0]
0x18007a7c8  mov     rcx, [rbp+57h+var_38]
0x18007a7cc  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x18007a7d1  mov     ebx, eax
0x18007a7d3  test    eax, eax
0x18007a7d5  jns     short loc_18007A7FB
0x18007a7d7  mov     rcx, [rbp+5Fh]; this
0x18007a7db  mov     r9d, eax; char *
0x18007a7de  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\windows.system.launc"...
0x18007a7e5  mov     edx, 4Dh ; 'M'; void *
0x18007a7ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a7ef  nop
0x18007a7f0  lea     rcx, [rbp+57h+var_C0]
0x18007a7f4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007a7f9  jmp     short loc_18007A792
0x18007a7fb  mov     [rbp+57h+var_C8], r12
0x18007a7ff  mov     rdi, [rbp+57h+var_C0]
0x18007a803  mov     rax, [rdi]
0x18007a806  mov     rbx, [rax+30h]
0x18007a80a  lea     rcx, [rbp+57h+var_C8]
0x18007a80e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007a813  lea     r8, [rbp+57h+var_C8]
0x18007a817  mov     rdx, [rsp+110h+string]
0x18007a81c  mov     rcx, rdi
0x18007a81f  mov     rax, rbx
0x18007a822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a827  mov     ebx, eax
0x18007a829  test    eax, eax
0x18007a82b  jns     short loc_18007A851
0x18007a82d  mov     edx, 4Fh ; 'O'; void *
0x18007a832  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\windows.system.launc"...
0x18007a839  mov     r9d, eax; char *
0x18007a83c  mov     rcx, [rbp+5Fh]; this
0x18007a840  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a845  nop
0x18007a846  lea     rcx, [rbp+57h+var_C8]
0x18007a84a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007a84f  jmp     short loc_18007A7F0
0x18007a851  mov     rax, [rsi]
0x18007a854  mov     rbx, [rax+30h]
0x18007a858  lea     rcx, [rbp+57h+var_A8]
0x18007a85c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007a861  lea     rdx, off_1801230A8; "CallerPackageFamilyName"
0x18007a868  lea     rcx, [rbp+57h+hstringHeader]
0x18007a86c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18007a871  nop
0x18007a872  lea     r8, [rbp+57h+var_A8]
0x18007a876  mov     rdx, [rax+18h]
0x18007a87a  mov     rcx, rsi
0x18007a87d  mov     rax, rbx
0x18007a880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a885  mov     ebx, eax
0x18007a887  test    eax, eax
0x18007a889  jns     short loc_18007A892
0x18007a88b  mov     edx, 51h ; 'Q'
0x18007a890  jmp     short loc_18007A832
0x18007a892  mov     [rsp+110h+var_D8], r12
0x18007a897  mov     rdi, [rbp+57h+var_A8]
0x18007a89b  mov     rax, [rdi]
0x18007a89e  mov     rbx, [rax+98h]
0x18007a8a5  xor     ecx, ecx; string
0x18007a8a7  call    cs:__imp_WindowsDeleteString
0x18007a8ad  mov     [rsp+110h+var_D8], r12
0x18007a8b2  lea     rdx, [rsp+110h+var_D8]
0x18007a8b7  mov     rcx, rdi
0x18007a8ba  mov     rax, rbx
0x18007a8bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a8c2  mov     ebx, eax
0x18007a8c4  test    eax, eax
0x18007a8c6  jns     short loc_18007A8F6
0x18007a8c8  mov     rcx, [rbp+5Fh]; this
0x18007a8cc  mov     r9d, eax; char *
0x18007a8cf  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\windows.system.launc"...
0x18007a8d6  mov     edx, 53h ; 'S'; void *
0x18007a8db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a8e0  nop
0x18007a8e1  mov     rcx, [rsp+110h+var_D8]; string
0x18007a8e6  call    cs:__imp_WindowsDeleteString
0x18007a8ec  mov     [rsp+110h+var_D8], r12
0x18007a8f1  jmp     loc_18007A846
0x18007a8f6  mov     [rbp+57h+var_D0], r12b
0x18007a8fa  mov     [rbp+57h+var_B8], r12
0x18007a8fe  mov     rax, [rsi]
0x18007a901  mov     rbx, [rax+40h]
0x18007a905  lea     rdx, off_180123080; "InputDataBuffer"
0x18007a90c  lea     rcx, [rbp+57h+hstringHeader]
0x18007a910  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18007a915  nop
0x18007a916  lea     r8, [rbp+57h+var_D0]
0x18007a91a  mov     rdx, [rax+18h]
0x18007a91e  mov     rcx, rsi
0x18007a921  mov     rax, rbx
0x18007a924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a929  mov     ebx, eax
0x18007a92b  test    eax, eax
0x18007a92d  jns     short loc_18007A953
0x18007a92f  mov     edx, 57h ; 'W'; void *
0x18007a934  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\windows.system.launc"...
0x18007a93b  mov     r9d, eax; char *
0x18007a93e  mov     rcx, [rbp+5Fh]; this
0x18007a942  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a947  nop
0x18007a948  lea     rcx, [rbp+57h+var_B8]
0x18007a94c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007a951  jmp     short loc_18007A8E1
0x18007a953  cmp     [rbp+57h+var_D0], r12b
0x18007a957  jz      loc_18007ABD1
0x18007a95d  mov     rax, [rsi]
0x18007a960  mov     rbx, [rax+30h]
0x18007a964  lea     rcx, [rbp+57h+var_A8]
0x18007a968  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007a96d  lea     rdx, off_180123080; "InputDataBuffer"
0x18007a974  lea     rcx, [rbp+57h+hstringHeader]
0x18007a978  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18007a97d  nop
0x18007a97e  lea     r8, [rbp+57h+var_A8]
0x18007a982  mov     rdx, [rax+18h]
0x18007a986  mov     rcx, rsi
0x18007a989  mov     rax, rbx
0x18007a98c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a991  mov     ebx, eax
0x18007a993  test    eax, eax
0x18007a995  jns     short loc_18007A99E
0x18007a997  mov     edx, 5Ah ; 'Z'
0x18007a99c  jmp     short loc_18007A934
0x18007a99e  mov     [rbp+57h+var_B0], r12
0x18007a9a2  mov     [rbp+57h+var_38], r12
0x18007a9a6  mov     r9d, 22h ; '"'; unsigned int
0x18007a9ac  lea     r8d, [r9+1]; unsigned int
0x18007a9b0  lea     rdx, ?RuntimeClass_Windows_Storage_Streams_DataWriter@@3QBGB; "Windows.Storage.Streams.DataWriter"
0x18007a9b7  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18007a9bb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007a9c0  lea     r8, [rbp+57h+var_B0]
0x18007a9c4  lea     rdx, _GUID_338c67c2_8b84_4c2b_9c50_7b8767847a1f
0x18007a9cb  mov     rcx, [rbp+57h+var_38]
0x18007a9cf  call    cs:__imp_RoGetActivationFactory
0x18007a9d5  mov     ebx, eax
0x18007a9d7  test    eax, eax
0x18007a9d9  jns     short loc_18007AA13
0x18007a9db  mov     rcx, [rbp+5Fh]; this
0x18007a9df  mov     r9d, eax; char *
0x18007a9e2  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\windows.system.launc"...
0x18007a9e9  mov     edx, 5Ch ; '\'; void *
0x18007a9ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a9f3  nop
0x18007a9f4  mov     rcx, [rbp+57h+var_B0]
0x18007a9f8  test    rcx, rcx
0x18007a9fb  jz      short loc_18007AA0E
0x18007a9fd  mov     [rbp+57h+var_B0], r12
0x18007aa01  mov     rax, [rcx]
0x18007aa04  mov     rax, [rax+10h]
0x18007aa08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aa0d  nop
0x18007aa0e  jmp     loc_18007A948
0x18007aa13  mov     [rbp+57h+var_98], r12
0x18007aa17  mov     rcx, [rbp+57h+var_B0]
0x18007aa1b  mov     rax, [rcx]
0x18007aa1e  lea     r8, [rbp+57h+var_98]
0x18007aa22  xor     edx, edx
0x18007aa24  mov     rax, [rax+30h]
0x18007aa28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aa2d  mov     ebx, eax
0x18007aa2f  test    eax, eax
0x18007aa31  jns     short loc_18007AA75
0x18007aa33  mov     rcx, [rbp+5Fh]; this
0x18007aa37  mov     r9d, eax; char *
0x18007aa3a  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\windows.system.launc"...
0x18007aa41  mov     edx, 5Fh ; '_'; void *
0x18007aa46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007aa4b  nop
0x18007aa4c  lea     rcx, [rbp+57h+var_98]
0x18007aa50  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007aa55  nop
0x18007aa56  mov     rcx, [rbp+57h+var_B0]
0x18007aa5a  test    rcx, rcx
0x18007aa5d  jz      short loc_18007AA70
0x18007aa5f  mov     [rbp+57h+var_B0], r12
0x18007aa63  mov     rax, [rcx]
0x18007aa66  mov     rax, [rax+10h]
0x18007aa6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aa6f  nop
0x18007aa70  jmp     loc_18007A948
0x18007aa75  mov     [rbp+57h+var_78], r12d
0x18007aa79  mov     [rbp+57h+var_58], r12
0x18007aa7d  mov     rcx, [rbp+57h+var_A8]
0x18007aa81  mov     rax, [rcx]
0x18007aa84  lea     r8, [rbp+57h+var_58]
0x18007aa88  lea     rdx, [rbp+57h+var_78]
0x18007aa8c  mov     rax, [rax+0D0h]
0x18007aa93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aa98  mov     ebx, eax
0x18007aa9a  test    eax, eax
0x18007aa9c  jns     short loc_18007AAE0
0x18007aa9e  mov     rcx, [rbp+5Fh]; this
0x18007aaa2  mov     r9d, eax; char *
0x18007aaa5  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\windows.system.launc"...
0x18007aaac  mov     edx, 63h ; 'c'; void *
0x18007aab1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007aab6  nop
0x18007aab7  lea     rcx, [rbp+57h+var_98]
0x18007aabb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007aac0  nop
0x18007aac1  mov     rcx, [rbp+57h+var_B0]
0x18007aac5  test    rcx, rcx
0x18007aac8  jz      short loc_18007AADB
0x18007aaca  mov     [rbp+57h+var_B0], r12
0x18007aace  mov     rax, [rcx]
0x18007aad1  mov     rax, [rax+10h]
0x18007aad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aada  nop
0x18007aadb  jmp     loc_18007A948
0x18007aae0  mov     rcx, [rbp+57h+var_98]
0x18007aae4  mov     rax, [rcx]
0x18007aae7  mov     r8, [rbp+57h+var_58]
0x18007aaeb  mov     edx, [rbp+57h+var_78]
0x18007aaee  mov     rax, [rax+60h]
0x18007aaf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aaf7  mov     ebx, eax
0x18007aaf9  test    eax, eax
0x18007aafb  jns     short loc_18007AB3F
0x18007aafd  mov     rcx, [rbp+5Fh]; this
0x18007ab01  mov     r9d, eax; char *
0x18007ab04  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\windows.system.launc"...
0x18007ab0b  mov     edx, 65h ; 'e'; void *
0x18007ab10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ab15  nop
0x18007ab16  lea     rcx, [rbp+57h+var_98]
0x18007ab1a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ab1f  nop
0x18007ab20  mov     rcx, [rbp+57h+var_B0]
0x18007ab24  test    rcx, rcx
  ... truncated ...
```
