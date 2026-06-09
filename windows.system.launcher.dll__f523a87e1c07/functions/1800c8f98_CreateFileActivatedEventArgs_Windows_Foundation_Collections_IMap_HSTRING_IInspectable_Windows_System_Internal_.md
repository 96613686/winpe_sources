# CreateFileActivatedEventArgs(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,Windows::System::Internal::Launch::LauncherPluginActivationType,IInspectable * *)

- ea: `0x1800c8f98`
- end: `0x1800c9736`
- name: `?CreateFileActivatedEventArgs@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@W4LauncherPluginActivationType@Launch@Internal@System@4@PEAPEAUIInspectable@@@Z`
- size: `1950`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c8d10`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x180033a5c`
- `0x180034ba0`
- `0x18004966c`
- `0x18006cf1c`
- `0x18008a030`
- `0x1800ac844`
- `0x1800c765c`
- `0x1800c779c`
- `0x1800c8f98`
- `0x1800cadfc`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c9486`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c9498`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c960c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c961d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c9486`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c9498`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c960c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c961d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c92b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c92f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c935a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c939c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c96b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c96c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c92b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c92f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c935a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c939c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c96b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c96c7`

## string_xrefs

- `0x1800c9053`: `onecoreuap\shell\windows.system.launcher\lib\launcheractivationbrokerplugin.cpp`
- `0x1800c91de`: `onecoreuap\shell\windows.system.launcher\lib\launcheractivationbrokerplugin.cpp`
- `0x1800c92da`: `onecoreuap\shell\windows.system.launcher\lib\launcheractivationbrokerplugin.cpp`
- `0x1800c9385`: `onecoreuap\shell\windows.system.launcher\lib\launcheractivationbrokerplugin.cpp`
- `0x1800c9403`: `onecoreuap\shell\windows.system.launcher\lib\launcheractivationbrokerplugin.cpp`
- `0x1800c9536`: `onecoreuap\shell\windows.system.launcher\lib\launcheractivationbrokerplugin.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CreateFileActivatedEventArgs(__int64 *a1, int a2, __int64 a3)
{
  __int64 v6; // rcx
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 (__fastcall *v10)(__int64 *, PVOID, char *); // rbx
  HSTRING_HEADER *v11; // rax
  __int64 (__fastcall *v12)(__int64 *, PVOID, struct Windows::Foundation::IPropertyValue **); // rbx
  HSTRING_HEADER *v13; // rax
  unsigned int i; // r14d
  __int64 (__fastcall *v15)(__int64 *, _QWORD, struct Windows::Foundation::IPropertyValue **); // rbx
  __int64 v16; // rax
  struct IUnknown *v17; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, const WCHAR **); // rbx
  __int64 (__fastcall *v23)(__int64 *, PVOID, struct Windows::Foundation::IPropertyValue **); // rbx
  HSTRING_HEADER *v24; // rax
  struct Windows::Foundation::IPropertyValue *v25; // rdi
  __int64 (__fastcall *v26)(struct Windows::Foundation::IPropertyValue *, HSTRING *); // rbx
  int v27; // eax
  __int64 v28; // rdx
  __int64 (__fastcall *v29)(__int64 *, PVOID, struct Windows::Foundation::IPropertyValue **); // rbx
  HSTRING_HEADER *v30; // rax
  struct Windows::Foundation::IPropertyValue *v31; // rdi
  __int64 (__fastcall *v32)(struct Windows::Foundation::IPropertyValue *, HSTRING *); // rbx
  int v33; // eax
  __int64 v34; // rbx
  HSTRING_HEADER *v35; // rax
  int v36; // eax
  __int64 v37; // rdx
  struct IUnknown *v38; // rbx
  HRESULT (__stdcall *v39)(IUnknown *, const IID *const, void **); // rdi
  HSTRING_HEADER *v40; // rax
  int v41; // eax
  __int64 v42; // rdx
  __int64 (__fastcall *v43)(__int64 *, PVOID, struct Windows::Foundation::IPropertyValue **); // rbx
  HSTRING_HEADER *v44; // rax
  struct IUnknown *v45; // rbx
  HRESULT (__stdcall *v46)(IUnknown *, const IID *const, void **); // rdi
  int v48; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING v50; // [rsp+38h] [rbp-C8h] BYREF
  char v51; // [rsp+40h] [rbp-C0h] BYREF
  char v52[7]; // [rsp+41h] [rbp-BFh] BYREF
  struct Windows::Foundation::IPropertyValue *v53; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v54)(_QWORD, GUID *, __int64); // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR StringRawBuffer; // [rsp+58h] [rbp-A8h] BYREF
  struct IUnknown *v56; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v57; // [rsp+68h] [rbp-98h] BYREF
  const WCHAR *v58; // [rsp+70h] [rbp-90h] BYREF
  __int64 v59; // [rsp+78h] [rbp-88h] BYREF
  const WCHAR *v60; // [rsp+80h] [rbp-80h] BYREF
  PCWSTR v61; // [rsp+88h] [rbp-78h] BYREF
  PCWSTR v62; // [rsp+90h] [rbp-70h] BYREF
  PCWSTR v63; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v64; // [rsp+A0h] [rbp-60h] BYREF
  const WCHAR *v65; // [rsp+A8h] [rbp-58h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR sourceString[256]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v53 = 0;
  v60 = 0;
  v56 = 0;
  v59 = 0;
  v58 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
  v7 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Storage::IStorageItem,Windows::Foundation::Collections::Internal::AgileVector<Windows::Storage::IStorageItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::IStorageItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::IStorageItem *>,0>>(
         v6,
         &v59);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v51 = 0;
    v10 = *(__int64 (__fastcall **)(__int64 *, PVOID, char *))(*a1 + 64);
    v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_180123090);
    v7 = v10(a1, v11[1].Reserved.Reserved1, &v51);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = 151;
      goto LABEL_5;
    }
    if ( v51 )
    {
      v64 = 0;
      v12 = *(__int64 (__fastcall **)(__int64 *, PVOID, struct Windows::Foundation::IPropertyValue **))(*a1 + 48);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
      v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_180123090);
      v7 = v12(a1, v13[1].Reserved.Reserved1, &v53);
      v8 = v7;
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValue *, unsigned __int64 *))(*(_QWORD *)v53 + 112LL))(
               v53,
               &v64);
        v8 = v7;
        if ( v7 >= 0 )
        {
          for ( i = 0; ; ++i )
          {
            if ( i >= v64 )
              goto LABEL_25;
            v7 = StringCchPrintfW(sourceString, 0x100u, L"%u", i);
            v8 = v7;
            if ( v7 < 0 )
              break;
            v15 = *(__int64 (__fastcall **)(__int64 *, _QWORD, struct Windows::Foundation::IPropertyValue **))(*a1 + 48);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
            v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, sourceString);
            v7 = v15(a1, *(_QWORD *)(v16 + 24), &v53);
            v8 = v7;
            if ( v7 < 0 )
            {
              v9 = 162;
              goto LABEL_5;
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
            v7 = ReadIUnknownFromUInt8ArrayPropertyValue(v53, &v56);
            v8 = v7;
            if ( v7 < 0 )
            {
              v9 = 163;
              goto LABEL_5;
            }
            v57 = 0;
            v17 = v56;
            QueryInterface = v56->lpVtbl->QueryInterface;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
            v19 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))QueryInterface)(
                    v17,
                    &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30,
                    &v57);
            v8 = v19;
            if ( v19 < 0 )
            {
              v20 = 165;
              goto LABEL_21;
            }
            v19 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v59 + 104LL))(v59, v57);
            v8 = v19;
            if ( v19 < 0 )
            {
              v20 = 166;
LABEL_21:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v20,
                (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcheractivationbrokerplugin.cpp",
                (const char *)(unsigned int)v19,
                v48);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
              goto LABEL_66;
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
          }
          v9 = 161;
        }
        else
        {
          v9 = 158;
        }
      }
      else
      {
        v9 = 157;
      }
      goto LABEL_5;
    }
LABEL_25:
    v21 = v59;
    v22 = *(__int64 (__fastcall **)(__int64, const WCHAR **))(*(_QWORD *)v59 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
    v7 = v22(v21, &v58);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = 169;
      goto LABEL_5;
    }
    v23 = *(__int64 (__fastcall **)(__int64 *, PVOID, struct Windows::Foundation::IPropertyValue **))(*a1 + 48);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
    v24 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_1801230A8);
    v7 = v23(a1, v24[1].Reserved.Reserved1, &v53);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = 171;
      goto LABEL_5;
    }
    string = 0;
    v25 = v53;
    v26 = *(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValue *, HSTRING *))(*(_QWORD *)v53 + 152LL);
    WindowsDeleteString(0);
    string = 0;
    v27 = v26(v25, &string);
    v8 = v27;
    if ( v27 < 0 )
    {
      v28 = 173;
LABEL_31:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcheractivationbrokerplugin.cpp",
        (const char *)(unsigned int)v27,
        v48);
LABEL_32:
      WindowsDeleteString(string);
LABEL_65:
      string = 0;
      goto LABEL_66;
    }
    v29 = *(__int64 (__fastcall **)(__int64 *, PVOID, struct Windows::Foundation::IPropertyValue **))(*a1 + 48);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
    v30 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_1801230A0);
    v27 = v29(a1, v30[1].Reserved.Reserved1, &v53);
    v8 = v27;
    if ( v27 < 0 )
    {
      v28 = 175;
      goto LABEL_31;
    }
    v50 = 0;
    v31 = v53;
    v32 = *(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValue *, HSTRING *))(*(_QWORD *)v53 + 152LL);
    WindowsDeleteString(0);
    v50 = 0;
    v33 = v32(v31, &v50);
    v8 = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB1,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcheractivationbrokerplugin.cpp",
        (const char *)(unsigned int)v33,
        v48);
LABEL_37:
      WindowsDeleteString(v50);
      v50 = 0;
      goto LABEL_32;
    }
    v54 = 0;
    v34 = *a1;
    if ( a2 == 2 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
      v35 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_1801230B8);
      v36 = (*(__int64 (__fastcall **)(__int64 *, PVOID, struct Windows::Foundation::IPropertyValue **))(v34 + 48))(
              a1,
              v35[1].Reserved.Reserved1,
              &v53);
      v8 = v36;
      if ( v36 < 0 )
      {
        v37 = 183;
LABEL_41:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v37,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcheractivationbrokerplugin.cpp",
          (const char *)(unsigned int)v36,
          v48);
LABEL_42:
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v54);
        goto LABEL_37;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
      v36 = ReadIUnknownFromUInt8ArrayPropertyValue(v53, &v56);
      v8 = v36;
      if ( v36 < 0 )
      {
        v37 = 184;
        goto LABEL_41;
      }
      v38 = v56;
      v39 = v56->lpVtbl->QueryInterface;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
      v36 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, const WCHAR **))v39)(
              v38,
              &GUID_72d1cb78_b3ef_4f75_a80b_6fd9dae2944b,
              &v60);
      v8 = v36;
      if ( v36 < 0 )
      {
        v37 = 185;
        goto LABEL_41;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v61 = WindowsGetStringRawBuffer(v50, 0);
      v62 = v60;
      v63 = v58;
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v54);
      v36 = Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::Launch::FileActivatedEventArgs,Windows::System::Internal::Launch::FileActivatedEventArgs,Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *,Windows::Storage::IStorageFolder *,unsigned short const *,unsigned short const *>(
              (unsigned int)&v54,
              (unsigned int)&v63,
              (unsigned int)&v62,
              (unsigned int)&v61,
              (__int64)&StringRawBuffer);
      v8 = v36;
      if ( v36 < 0 )
      {
        v37 = 187;
        goto LABEL_41;
      }
LABEL_62:
      v36 = (**v54)(v54, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, a3);
      v8 = v36;
      if ( v36 >= 0 )
      {
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v54);
        WindowsDeleteString(v50);
        v50 = 0;
        WindowsDeleteString(string);
        v8 = 0;
        goto LABEL_65;
      }
      v37 = 203;
      goto LABEL_41;
    }
    v52[0] = 0;
    StringRawBuffer = 0;
    v40 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_1801230B0);
    v41 = (*(__int64 (__fastcall **)(__int64 *, PVOID, char *))(v34 + 64))(a1, v40[1].Reserved.Reserved1, v52);
    v8 = v41;
    if ( v41 >= 0 )
    {
      if ( v52[0] )
      {
        v43 = *(__int64 (__fastcall **)(__int64 *, PVOID, struct Windows::Foundation::IPropertyValue **))(*a1 + 48);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
        v44 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                &hstringHeader,
                (const WCHAR **)off_1801230B0);
        v41 = v43(a1, v44[1].Reserved.Reserved1, &v53);
        v8 = v41;
        if ( v41 < 0 )
        {
          v42 = 196;
          goto LABEL_51;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
        v41 = ReadIUnknownFromUInt8ArrayPropertyValue(v53, &v56);
        v8 = v41;
        if ( v41 < 0 )
        {
          v42 = 197;
          goto LABEL_51;
        }
        v45 = v56;
        v46 = v56->lpVtbl->QueryInterface;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&StringRawBuffer);
        v41 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, PCWSTR *))v46)(
                v45,
                &GUID_52fda447_2baa_412c_b29f_d4b1778efa1e,
                &StringRawBuffer);
        v8 = v41;
        if ( v41 < 0 )
        {
          v42 = 198;
          goto LABEL_51;
        }
      }
      v63 = WindowsGetStringRawBuffer(string, 0);
      v62 = WindowsGetStringRawBuffer(v50, 0);
      v61 = StringRawBuffer;
      v65 = v58;
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v54);
      v41 = Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::Launch::FileActivatedEventArgs,Windows::System::Internal::Launch::FileActivatedEventArgs,Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *,Windows::Storage::Search::IStorageFileQueryResult *,unsigned short const *,unsigned short const *>(
              (unsigned int)&v54,
              (unsigned int)&v65,
              (unsigned int)&v61,
              (unsigned int)&v62,
              (__int64)&v63);
      v8 = v41;
      if ( v41 >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&StringRawBuffer);
        goto LABEL_62;
      }
      v42 = 201;
    }
    else
    {
      v42 = 193;
    }
LABEL_51:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v42,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcheractivationbrokerplugin.cpp",
      (const char *)(unsigned int)v41,
      v48);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&StringRawBuffer);
    goto LABEL_42;
  }
  v9 = 148;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcheractivationbrokerplugin.cpp",
    (const char *)(unsigned int)v7,
    v48);
LABEL_66:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
  return v8;
}

```

## disassembly

```asm
0x1800c8f98  mov     [rsp-8+arg_8], rbx
0x1800c8f9d  push    rbp
0x1800c8f9e  push    rsi
0x1800c8f9f  push    rdi
0x1800c8fa0  push    r12
0x1800c8fa2  push    r13
0x1800c8fa4  push    r14
0x1800c8fa6  push    r15
0x1800c8fa8  lea     rbp, [rsp-1E0h]
0x1800c8fb0  sub     rsp, 2E0h
0x1800c8fb7  mov     rax, cs:__security_cookie
0x1800c8fbe  xor     rax, rsp
0x1800c8fc1  mov     [rbp+210h+var_40], rax
0x1800c8fc8  mov     r12, r8
0x1800c8fcb  mov     r15d, edx
0x1800c8fce  mov     rsi, rcx
0x1800c8fd1  xor     r13d, r13d
0x1800c8fd4  mov     [rsp+310h+var_2C8], r13
0x1800c8fd9  mov     [rbp+210h+var_290], r13
0x1800c8fdd  mov     [rsp+310h+var_2B0], r13
0x1800c8fe2  mov     [rsp+310h+var_298], r13
0x1800c8fe7  mov     [rsp+310h+var_2A0], r13
0x1800c8fec  lea     rcx, [rsp+310h+var_298]
0x1800c8ff1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c8ff6  lea     rdx, [rsp+310h+var_298]
0x1800c8ffb  call    ??$CreateExternalObjectVector@UIStorageItem@Storage@Windows@@V?$AgileVector@PEAUIStorageItem@Storage@Windows@@U?$DefaultEqualityPredicate@PEAUIStorageItem@Storage@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@PEAUIStorageItem@Storage@Windows@@@5673@$0A@@Internal@Collections@Foundation@3@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAUIStorageItem@Storage@Windows@@U?$DefaultEqualityPredicate@PEAUIStorageItem@Storage@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@PEAUIStorageItem@Storage@Windows@@@5673@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Storage::IStorageItem,Windows::Foundation::Collections::Internal::AgileVector<Windows::Storage::IStorageItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::IStorageItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::IStorageItem *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Storage::IStorageItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::IStorageItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::IStorageItem *>,0> * *)
0x1800c9000  mov     ebx, eax
0x1800c9002  test    eax, eax
0x1800c9004  jns     short loc_1800C900D
0x1800c9006  mov     edx, 94h
0x1800c900b  jmp     short loc_1800C9049
0x1800c900d  mov     [rsp+310h+var_2D0], r13b
0x1800c9012  mov     rax, [rsi]
0x1800c9015  mov     rbx, [rax+40h]
0x1800c9019  lea     rdx, off_180123090; "NumberOfStorageItems"
0x1800c9020  lea     rcx, [rbp+210h+hstringHeader]
0x1800c9024  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800c9029  nop
0x1800c902a  lea     r8, [rsp+310h+var_2D0]
0x1800c902f  mov     rdx, [rax+18h]
0x1800c9033  mov     rcx, rsi
0x1800c9036  mov     rax, rbx
0x1800c9039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c903e  mov     ebx, eax
0x1800c9040  test    eax, eax
0x1800c9042  jns     short loc_1800C9064
0x1800c9044  mov     edx, 97h; void *
0x1800c9049  mov     rcx, [rbp+218h]; this
0x1800c9050  mov     r9d, eax; char *
0x1800c9053  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\windows.system.launc"...
0x1800c905a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c905f  jmp     loc_1800C96D5
0x1800c9064  cmp     [rsp+310h+var_2D0], r13b
0x1800c9069  jz      loc_1800C9222
0x1800c906f  mov     [rbp+210h+var_270], r13
0x1800c9073  mov     rax, [rsi]
0x1800c9076  mov     rbx, [rax+30h]
0x1800c907a  lea     rcx, [rsp+310h+var_2C8]
0x1800c907f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c9084  lea     rdx, off_180123090; "NumberOfStorageItems"
0x1800c908b  lea     rcx, [rbp+210h+hstringHeader]
0x1800c908f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800c9094  nop
0x1800c9095  lea     r8, [rsp+310h+var_2C8]
0x1800c909a  mov     rdx, [rax+18h]
0x1800c909e  mov     rcx, rsi
0x1800c90a1  mov     rax, rbx
0x1800c90a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c90a9  mov     ebx, eax
0x1800c90ab  test    eax, eax
0x1800c90ad  jns     short loc_1800C90B6
0x1800c90af  mov     edx, 9Dh
0x1800c90b4  jmp     short loc_1800C9049
0x1800c90b6  mov     rcx, [rsp+310h+var_2C8]
0x1800c90bb  mov     rax, [rcx]
0x1800c90be  lea     rdx, [rbp+210h+var_270]
0x1800c90c2  mov     rax, [rax+70h]
0x1800c90c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c90cb  mov     ebx, eax
0x1800c90cd  test    eax, eax
0x1800c90cf  jns     short loc_1800C90DB
0x1800c90d1  mov     edx, 9Eh
0x1800c90d6  jmp     loc_1800C9049
0x1800c90db  mov     r14d, r13d
0x1800c90de  mov     eax, r14d
0x1800c90e1  cmp     rax, [rbp+210h+var_270]
0x1800c90e5  jnb     loc_1800C9222
0x1800c90eb  mov     r9d, r14d
0x1800c90ee  lea     r8, aU_0; "%u"
0x1800c90f5  mov     edx, 100h; unsigned __int64
0x1800c90fa  lea     rcx, [rbp+210h+sourceString]; unsigned __int16 *
0x1800c90fe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c9103  mov     ebx, eax
0x1800c9105  test    eax, eax
0x1800c9107  js      loc_1800C9218
0x1800c910d  mov     rax, [rsi]
0x1800c9110  mov     rbx, [rax+30h]
0x1800c9114  lea     rcx, [rsp+310h+var_2C8]
0x1800c9119  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c911e  lea     rdx, [rbp+210h+sourceString]; sourceString
0x1800c9122  lea     rcx, [rbp+210h+hstringHeader]; hstringHeader
0x1800c9126  call    ??$?0$0BAA@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0BAA@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[256])
0x1800c912b  nop
0x1800c912c  lea     r8, [rsp+310h+var_2C8]
0x1800c9131  mov     rdx, [rax+18h]
0x1800c9135  mov     rcx, rsi
0x1800c9138  mov     rax, rbx
0x1800c913b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9140  mov     ebx, eax
0x1800c9142  test    eax, eax
0x1800c9144  js      loc_1800C920E
0x1800c914a  lea     rcx, [rsp+310h+var_2B0]
0x1800c914f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c9154  lea     rdx, [rsp+310h+var_2B0]; struct IUnknown **
0x1800c9159  mov     rcx, [rsp+310h+var_2C8]; struct Windows::Foundation::IPropertyValue *
0x1800c915e  call    ?ReadIUnknownFromUInt8ArrayPropertyValue@@YAJPEAUIPropertyValue@Foundation@Windows@@PEAPEAUIUnknown@@@Z; ReadIUnknownFromUInt8ArrayPropertyValue(Windows::Foundation::IPropertyValue *,IUnknown * *)
0x1800c9163  mov     ebx, eax
0x1800c9165  test    eax, eax
0x1800c9167  js      loc_1800C9204
0x1800c916d  mov     [rsp+310h+var_2A8], r13
0x1800c9172  mov     rbx, [rsp+310h+var_2B0]
0x1800c9177  mov     rax, [rbx]
0x1800c917a  mov     rdi, [rax]
0x1800c917d  lea     rcx, [rsp+310h+var_2A8]
0x1800c9182  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c9187  lea     r8, [rsp+310h+var_2A8]
0x1800c918c  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x1800c9193  mov     rcx, rbx
0x1800c9196  mov     rax, rdi
0x1800c9199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c919e  mov     ebx, eax
0x1800c91a0  test    eax, eax
0x1800c91a2  js      short loc_1800C91D9
0x1800c91a4  mov     rcx, [rsp+310h+var_298]
0x1800c91a9  mov     rax, [rcx]
0x1800c91ac  mov     rdx, [rsp+310h+var_2A8]
0x1800c91b1  mov     rax, [rax+68h]
0x1800c91b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c91ba  mov     ebx, eax
0x1800c91bc  test    eax, eax
0x1800c91be  js      short loc_1800C91D2
0x1800c91c0  lea     rcx, [rsp+310h+var_2A8]
0x1800c91c5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c91ca  inc     r14d
0x1800c91cd  jmp     loc_1800C90DE
0x1800c91d2  mov     edx, 0A6h
0x1800c91d7  jmp     short loc_1800C91DE
0x1800c91d9  mov     edx, 0A5h; void *
0x1800c91de  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\windows.system.launc"...
0x1800c91e5  mov     r9d, eax; char *
0x1800c91e8  mov     rcx, [rbp+218h]; this
0x1800c91ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c91f4  nop
0x1800c91f5  lea     rcx, [rsp+310h+var_2A8]
0x1800c91fa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c91ff  jmp     loc_1800C96D5
0x1800c9204  mov     edx, 0A3h
0x1800c9209  jmp     loc_1800C9049
0x1800c920e  mov     edx, 0A2h
0x1800c9213  jmp     loc_1800C9049
0x1800c9218  mov     edx, 0A1h
0x1800c921d  jmp     loc_1800C9049
0x1800c9222  mov     rdi, [rsp+310h+var_298]
0x1800c9227  mov     rax, [rdi]
0x1800c922a  mov     rbx, [rax+40h]
0x1800c922e  lea     rcx, [rsp+310h+var_2A0]
0x1800c9233  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c9238  lea     rdx, [rsp+310h+var_2A0]
0x1800c923d  mov     rcx, rdi
0x1800c9240  mov     rax, rbx
0x1800c9243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9248  mov     ebx, eax
0x1800c924a  test    eax, eax
0x1800c924c  jns     short loc_1800C9258
0x1800c924e  mov     edx, 0A9h
0x1800c9253  jmp     loc_1800C9049
0x1800c9258  mov     rax, [rsi]
0x1800c925b  mov     rbx, [rax+30h]
0x1800c925f  lea     rcx, [rsp+310h+var_2C8]
0x1800c9264  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c9269  lea     rdx, off_1801230A8; "CallerPackageFamilyName"
0x1800c9270  lea     rcx, [rbp+210h+hstringHeader]
0x1800c9274  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800c9279  nop
0x1800c927a  lea     r8, [rsp+310h+var_2C8]
0x1800c927f  mov     rdx, [rax+18h]
0x1800c9283  mov     rcx, rsi
0x1800c9286  mov     rax, rbx
0x1800c9289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c928e  mov     ebx, eax
0x1800c9290  test    eax, eax
0x1800c9292  jns     short loc_1800C929E
0x1800c9294  mov     edx, 0ABh
0x1800c9299  jmp     loc_1800C9049
0x1800c929e  mov     [rsp+310h+string], r13
0x1800c92a3  mov     rdi, [rsp+310h+var_2C8]
0x1800c92a8  mov     rax, [rdi]
0x1800c92ab  mov     rbx, [rax+98h]
0x1800c92b2  xor     ecx, ecx; string
0x1800c92b4  call    cs:__imp_WindowsDeleteString
0x1800c92ba  mov     [rsp+310h+string], r13
0x1800c92bf  lea     rdx, [rsp+310h+string]
0x1800c92c4  mov     rcx, rdi
0x1800c92c7  mov     rax, rbx
0x1800c92ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c92cf  mov     ebx, eax
0x1800c92d1  test    eax, eax
0x1800c92d3  jns     short loc_1800C9301
0x1800c92d5  mov     edx, 0ADh; void *
0x1800c92da  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\windows.system.launc"...
0x1800c92e1  mov     r9d, eax; char *
0x1800c92e4  mov     rcx, [rbp+218h]; this
0x1800c92eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c92f0  nop
0x1800c92f1  mov     rcx, [rsp+310h+string]; string
0x1800c92f6  call    cs:__imp_WindowsDeleteString
0x1800c92fc  jmp     loc_1800C96D0
0x1800c9301  mov     rax, [rsi]
0x1800c9304  mov     rbx, [rax+30h]
0x1800c9308  lea     rcx, [rsp+310h+var_2C8]
0x1800c930d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c9312  lea     rdx, off_1801230A0; "Verb"
0x1800c9319  lea     rcx, [rbp+210h+hstringHeader]
0x1800c931d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800c9322  nop
0x1800c9323  lea     r8, [rsp+310h+var_2C8]
0x1800c9328  mov     rdx, [rax+18h]
0x1800c932c  mov     rcx, rsi
0x1800c932f  mov     rax, rbx
0x1800c9332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9337  mov     ebx, eax
0x1800c9339  test    eax, eax
0x1800c933b  jns     short loc_1800C9344
0x1800c933d  mov     edx, 0AFh
0x1800c9342  jmp     short loc_1800C92DA
0x1800c9344  mov     [rsp+310h+var_2D8], r13
0x1800c9349  mov     rdi, [rsp+310h+var_2C8]
0x1800c934e  mov     rax, [rdi]
0x1800c9351  mov     rbx, [rax+98h]
0x1800c9358  xor     ecx, ecx; string
0x1800c935a  call    cs:__imp_WindowsDeleteString
0x1800c9360  mov     [rsp+310h+var_2D8], r13
0x1800c9365  lea     rdx, [rsp+310h+var_2D8]
0x1800c936a  mov     rcx, rdi
0x1800c936d  mov     rax, rbx
0x1800c9370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9375  mov     ebx, eax
0x1800c9377  test    eax, eax
0x1800c9379  jns     short loc_1800C93AC
0x1800c937b  mov     rcx, [rbp+218h]; this
0x1800c9382  mov     r9d, eax; char *
0x1800c9385  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\windows.system.launc"...
0x1800c938c  mov     edx, 0B1h; void *
0x1800c9391  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9396  nop
0x1800c9397  mov     rcx, [rsp+310h+var_2D8]; string
0x1800c939c  call    cs:__imp_WindowsDeleteString
0x1800c93a2  mov     [rsp+310h+var_2D8], r13
0x1800c93a7  jmp     loc_1800C92F1
0x1800c93ac  mov     [rsp+310h+var_2C0], r13
0x1800c93b1  mov     rbx, [rsi]
0x1800c93b4  cmp     r15d, 2
0x1800c93b8  jnz     loc_1800C94F1
0x1800c93be  lea     rcx, [rsp+310h+var_2C8]
0x1800c93c3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c93c8  lea     rdx, off_1801230B8; "StorageFolder"
0x1800c93cf  lea     rcx, [rbp+210h+hstringHeader]
0x1800c93d3  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800c93d8  nop
0x1800c93d9  lea     r8, [rsp+310h+var_2C8]
0x1800c93de  mov     rdx, [rax+18h]
0x1800c93e2  mov     rcx, rsi
0x1800c93e5  mov     rax, [rbx+30h]
0x1800c93e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c93ee  mov     ebx, eax
0x1800c93f0  test    eax, eax
0x1800c93f2  jns     short loc_1800C941F
0x1800c93f4  mov     edx, 0B7h; void *
0x1800c93f9  mov     rcx, [rbp+218h]; this
0x1800c9400  mov     r9d, eax; char *
0x1800c9403  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\windows.system.launc"...
0x1800c940a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c940f  nop
0x1800c9410  lea     rcx, [rsp+310h+var_2C0]
0x1800c9415  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800c941a  jmp     loc_1800C9397
0x1800c941f  lea     rcx, [rsp+310h+var_2B0]
0x1800c9424  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c9429  lea     rdx, [rsp+310h+var_2B0]; struct IUnknown **
0x1800c942e  mov     rcx, [rsp+310h+var_2C8]; struct Windows::Foundation::IPropertyValue *
0x1800c9433  call    ?ReadIUnknownFromUInt8ArrayPropertyValue@@YAJPEAUIPropertyValue@Foundation@Windows@@PEAPEAUIUnknown@@@Z; ReadIUnknownFromUInt8ArrayPropertyValue(Windows::Foundation::IPropertyValue *,IUnknown * *)
0x1800c9438  mov     ebx, eax
0x1800c943a  test    eax, eax
0x1800c943c  jns     short loc_1800C9445
0x1800c943e  mov     edx, 0B8h
0x1800c9443  jmp     short loc_1800C93F9
0x1800c9445  mov     rbx, [rsp+310h+var_2B0]
0x1800c944a  mov     rax, [rbx]
0x1800c944d  mov     rdi, [rax]
0x1800c9450  lea     rcx, [rbp+210h+var_290]
  ... truncated ...
```
