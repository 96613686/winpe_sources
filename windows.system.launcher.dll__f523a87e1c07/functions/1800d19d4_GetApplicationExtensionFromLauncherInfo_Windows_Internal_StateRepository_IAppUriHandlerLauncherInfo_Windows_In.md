# GetApplicationExtensionFromLauncherInfo(Windows::Internal::StateRepository::IAppUriHandlerLauncherInfo *,Windows::Internal::StateRepository::IApplicationExtension * *,HSTRING__ * *)

- ea: `0x1800d19d4`
- end: `0x1800d1f8f`
- name: `?GetApplicationExtensionFromLauncherInfo@@YAJPEAUIAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@PEAPEAUIApplicationExtension@234@PEAPEAUHSTRING__@@@Z`
- size: `1467`
- prototype: `int(struct Windows::Internal::StateRepository::IAppUriHandlerLauncherInfo *, struct Windows::Internal::StateRepository::IApplicationExtension **, HSTRING *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002984c`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x180021a88`
- `0x18006323c`
- `0x180064714`
- `0x180080640`
- `0x180087298`
- `0x1800d19d4`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800d1aa9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800d1aa9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d1a80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d1a8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d1a80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d1a8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1a37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1a61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1aff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1b3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1b61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1b72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1b80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1b93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1ba1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1c7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1ddb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1e1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1e52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1eaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1ee1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1f39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1a37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1a61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1aff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1b3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1b61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1b72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1b80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1b93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1ba1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1c7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1ddb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1e1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1e52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1eaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1ee1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1f39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800d1b4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800d1e90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800d1b4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800d1e90`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall GetApplicationExtensionFromLauncherInfo(
        struct Windows::Internal::StateRepository::IAppUriHandlerLauncherInfo *a1,
        struct Windows::Internal::StateRepository::IApplicationExtension **a2,
        HSTRING *a3)
{
  int v6; // r14d
  int (__fastcall *v7)(struct Windows::Internal::StateRepository::IAppUriHandlerLauncherInfo *, __int64 *); // rbx
  void (__fastcall *v8)(struct Windows::Internal::StateRepository::IAppUriHandlerLauncherInfo *, HSTRING *); // rbx
  __int64 v9; // rdi
  void (__fastcall *v10)(__int64, HSTRING *); // rbx
  const WCHAR *StringRawBuffer; // rbx
  const WCHAR *v12; // rax
  int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  HRESULT v17; // eax
  __int64 v18; // rdx
  int v19; // eax
  __int64 v20; // rdi
  void (__fastcall *v21)(__int64, __int64, __int64 *); // rbx
  __int64 v22; // rdi
  void (__fastcall *v23)(__int64, __int64, __int64 *); // rbx
  __int64 v24; // rdi
  void (__fastcall *v25)(__int64, HSTRING *); // rbx
  __int64 v26; // rdi
  void (__fastcall *v27)(__int64, HSTRING, __int64 *); // rbx
  int v28; // eax
  int v29; // r13d
  __int64 v30; // rdi
  void (__fastcall *v31)(__int64, struct Windows::Internal::StateRepository::IApplicationExtension **); // rbx
  struct Windows::Internal::StateRepository::IApplicationExtension *v32; // rcx
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, HSTRING *); // rbx
  HRESULT v35; // eax
  __int64 v36; // rdx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-99h]
  struct Windows::Internal::StateRepository::IApplicationExtension *v39; // [rsp+30h] [rbp-89h] BYREF
  __int64 v40; // [rsp+38h] [rbp-81h] BYREF
  HSTRING string; // [rsp+40h] [rbp-79h] BYREF
  __int64 v42; // [rsp+48h] [rbp-71h] BYREF
  __int64 v43; // [rsp+50h] [rbp-69h] BYREF
  HSTRING v44; // [rsp+58h] [rbp-61h] BYREF
  __int64 v45; // [rsp+60h] [rbp-59h] BYREF
  __int64 v46; // [rsp+68h] [rbp-51h] BYREF
  __int64 v47; // [rsp+70h] [rbp-49h] BYREF
  __int64 v48; // [rsp+78h] [rbp-41h] BYREF
  __int64 v49; // [rsp+80h] [rbp-39h] BYREF
  __int64 v50; // [rsp+88h] [rbp-31h] BYREF
  __int64 v51; // [rsp+90h] [rbp-29h] BYREF
  __int64 v52; // [rsp+98h] [rbp-21h] BYREF
  __int64 v53; // [rsp+A0h] [rbp-19h] BYREF
  int v54; // [rsp+A8h] [rbp-11h] BYREF
  int *v55; // [rsp+B0h] [rbp-9h]
  int v56; // [rsp+B8h] [rbp-1h]
  _QWORD v57[10]; // [rsp+C0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  int v59; // [rsp+120h] [rbp+67h] BYREF
  HSTRING v60; // [rsp+128h] [rbp+6Fh] BYREF
  HSTRING v61; // [rsp+130h] [rbp+77h] BYREF
  HSTRING v62; // [rsp+138h] [rbp+7Fh] BYREF

  v6 = 0;
  *a2 = 0;
  *a3 = 0;
  v45 = 0;
  v7 = *(int (__fastcall **)(struct Windows::Internal::StateRepository::IAppUriHandlerLauncherInfo *, __int64 *))(*(_QWORD *)a1 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
  if ( v7(a1, &v45) >= 0 )
  {
    v44 = 0;
    v8 = *(void (__fastcall **)(struct Windows::Internal::StateRepository::IAppUriHandlerLauncherInfo *, HSTRING *))(*(_QWORD *)a1 + 96LL);
    WindowsDeleteString(0);
    v44 = 0;
    v8(a1, &v44);
    string = 0;
    v9 = v45;
    v10 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v45 + 112LL);
    WindowsDeleteString(0);
    string = 0;
    v10(v9, &string);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v12 = WindowsGetStringRawBuffer(v44, 0);
    if ( CompareStringOrdinal(v12, -1, StringRawBuffer, -1, 1) == 2 )
    {
      v13 = (*(__int64 (__fastcall **)(__int64, struct Windows::Internal::StateRepository::IApplicationExtension **))(*(_QWORD *)v45 + 96LL))(
              v45,
              a2);
      v14 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1AE,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
          (const char *)(unsigned int)v13,
          bIgnoreCase);
LABEL_12:
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v44);
        v44 = 0;
        goto LABEL_30;
      }
      v61 = 0;
      v15 = v45;
      v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v45 + 64LL);
      WindowsDeleteString(0);
      v61 = 0;
      v17 = v16(v15, &v61);
      v14 = v17;
      if ( v17 >= 0 )
      {
        v17 = WindowsDuplicateString(v61, a3);
        v14 = v17;
        if ( v17 >= 0 )
        {
          WindowsDeleteString(v61);
          v14 = 0;
          goto LABEL_11;
        }
        v18 = 434;
      }
      else
      {
        v18 = 433;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
        (const char *)(unsigned int)v17,
        bIgnoreCase);
      WindowsDeleteString(v61);
LABEL_11:
      v61 = 0;
      goto LABEL_12;
    }
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v44);
  }
  v49 = 0;
  v19 = (*(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IAppUriHandlerLauncherInfo *, __int64 *))(*(_QWORD *)a1 + 48LL))(
          a1,
          &v49);
  v14 = v19;
  if ( v19 >= 0 )
  {
    wil::GetActivationFactory<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics>(&v48);
    v40 = 0;
    v20 = v48;
    v21 = *(void (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v48 + 128LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
    v21(v20, v49, &v40);
    v50 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 80LL))(v40, &v50);
    wil::GetActivationFactory<Windows::Internal::StateRepository::IDynamicAppUriHandlerGroupStatics>(&v47);
    v43 = 0;
    v22 = v47;
    v23 = *(void (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v47 + 112LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
    v23(v22, v50, &v43);
    v60 = 0;
    v24 = v43;
    v25 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v43 + 144LL);
    WindowsDeleteString(0);
    v60 = 0;
    v25(v24, &v60);
    wil::GetActivationFactory<Windows::Internal::StateRepository::IAppUriHandlerGroupStatics>(&v46);
    v42 = 0;
    v26 = v46;
    v27 = *(void (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v46 + 112LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    v27(v26, v60, &v42);
    v59 = 0;
    v53 = v42;
    v55 = &v59;
    v56 = 0;
    v57[0] = 0;
    v28 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v42 + 56LL))(v42, &v54);
    *v55 = v28;
    wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::AppUriHandlerGroup *>>::get_at_current(
      &v53,
      0);
    v29 = v54;
    while ( 1 )
    {
      if ( *v55 < 0 || v6 == v29 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v57);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
        wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v46);
        WindowsDeleteString(v60);
        v60 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
        wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v47);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
        wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v48);
        v14 = 1168;
        goto LABEL_30;
      }
      v39 = 0;
      v30 = v57[0];
      v31 = *(void (__fastcall **)(__int64, struct Windows::Internal::StateRepository::IApplicationExtension **))(*(_QWORD *)v57[0] + 80LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
      v31(v30, &v39);
      v52 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IApplicationExtension *, __int64 *))(*(_QWORD *)v39 + 64LL))(
        v39,
        &v52);
      v51 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IAppUriHandlerLauncherInfo *, __int64 *))(*(_QWORD *)a1 + 64LL))(
        a1,
        &v51);
      if ( v52 == v51 )
        break;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
      wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::AppUriHandlerGroup *>>::get_at_current(
        &v53,
        (unsigned int)++v6);
    }
    v32 = v39;
    if ( v39 )
    {
      (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IApplicationExtension *))(*(_QWORD *)v39 + 8LL))(v39);
      v32 = v39;
    }
    *a2 = v32;
    v62 = 0;
    v33 = v40;
    v34 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v40 + 112LL);
    WindowsDeleteString(0);
    v62 = 0;
    v35 = v34(v33, &v62);
    v14 = v35;
    if ( v35 < 0 )
    {
      v36 = 484;
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v36,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
        (const char *)(unsigned int)v35,
        bIgnoreCase);
      WindowsDeleteString(v62);
      v62 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v57);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v46);
      WindowsDeleteString(v60);
      v60 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v47);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v48);
      goto LABEL_30;
    }
    v35 = WindowsDuplicateString(v62, a3);
    v14 = v35;
    if ( v35 < 0 )
    {
      v36 = 485;
      goto LABEL_25;
    }
    WindowsDeleteString(v62);
    v62 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v57);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v46);
    WindowsDeleteString(v60);
    v60 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v47);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v48);
    v14 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BA,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)(unsigned int)v19,
      bIgnoreCase);
  }
LABEL_30:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
  return v14;
}

```

## disassembly

```asm
0x1800d19d4  push    rbp
0x1800d19d6  push    rbx
0x1800d19d7  push    rsi
0x1800d19d8  push    rdi
0x1800d19d9  push    r12
0x1800d19db  push    r13
0x1800d19dd  push    r14
0x1800d19df  push    r15
0x1800d19e1  lea     rbp, [rsp-1Fh]
0x1800d19e6  sub     rsp, 0D8h
0x1800d19ed  mov     r15, r8
0x1800d19f0  mov     r12, rdx
0x1800d19f3  mov     rsi, rcx
0x1800d19f6  xor     r14d, r14d
0x1800d19f9  mov     [rdx], r14
0x1800d19fc  mov     [r8], r14
0x1800d19ff  mov     [rbp+57h+var_B0], r14
0x1800d1a03  mov     rax, [rcx]
0x1800d1a06  mov     rbx, [rax+38h]
0x1800d1a0a  lea     rcx, [rbp+57h+var_B0]
0x1800d1a0e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d1a13  lea     rdx, [rbp+57h+var_B0]
0x1800d1a17  mov     rcx, rsi
0x1800d1a1a  mov     rax, rbx
0x1800d1a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1a22  test    eax, eax
0x1800d1a24  js      loc_1800D1BA7
0x1800d1a2a  mov     [rbp+57h+var_B8], r14
0x1800d1a2e  mov     rax, [rsi]
0x1800d1a31  mov     rbx, [rax+60h]
0x1800d1a35  xor     ecx, ecx; string
0x1800d1a37  call    cs:__imp_WindowsDeleteString
0x1800d1a3d  mov     [rbp+57h+var_B8], r14
0x1800d1a41  lea     rdx, [rbp+57h+var_B8]
0x1800d1a45  mov     rcx, rsi
0x1800d1a48  mov     rax, rbx
0x1800d1a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1a50  mov     [rbp+57h+string], r14
0x1800d1a54  mov     rdi, [rbp+57h+var_B0]
0x1800d1a58  mov     rax, [rdi]
0x1800d1a5b  mov     rbx, [rax+70h]
0x1800d1a5f  xor     ecx, ecx; string
0x1800d1a61  call    cs:__imp_WindowsDeleteString
0x1800d1a67  mov     [rbp+57h+string], r14
0x1800d1a6b  lea     rdx, [rbp+57h+string]
0x1800d1a6f  mov     rcx, rdi
0x1800d1a72  mov     rax, rbx
0x1800d1a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1a7a  xor     edx, edx; length
0x1800d1a7c  mov     rcx, [rbp+57h+string]; string
0x1800d1a80  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d1a86  mov     rbx, rax
0x1800d1a89  xor     edx, edx; length
0x1800d1a8b  mov     rcx, [rbp+57h+var_B8]; string
0x1800d1a8f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d1a95  mov     [rsp+110h+bIgnoreCase], 1; int
0x1800d1a9d  or      edx, 0FFFFFFFFh; cchCount1
0x1800d1aa0  mov     r9d, edx; cchCount2
0x1800d1aa3  mov     r8, rbx; lpString2
0x1800d1aa6  mov     rcx, rax; lpString1
0x1800d1aa9  call    cs:__imp_CompareStringOrdinal
0x1800d1aaf  cmp     eax, 2
0x1800d1ab2  jnz     loc_1800D1B8F
0x1800d1ab8  mov     rcx, [rbp+57h+var_B0]
0x1800d1abc  mov     rax, [rcx]
0x1800d1abf  mov     rdx, r12
0x1800d1ac2  mov     rax, [rax+60h]
0x1800d1ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1acb  mov     ebx, eax
0x1800d1acd  test    eax, eax
0x1800d1acf  jns     short loc_1800D1AEE
0x1800d1ad1  mov     rcx, [rbp+5Fh]; this
0x1800d1ad5  mov     r9d, eax; char *
0x1800d1ad8  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x1800d1adf  mov     edx, 1AEh; void *
0x1800d1ae4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d1ae9  jmp     loc_1800D1B6E
0x1800d1aee  mov     [rbp+57h+arg_10], r14
0x1800d1af2  mov     rdi, [rbp+57h+var_B0]
0x1800d1af6  mov     rax, [rdi]
0x1800d1af9  mov     rbx, [rax+40h]
0x1800d1afd  xor     ecx, ecx; string
0x1800d1aff  call    cs:__imp_WindowsDeleteString
0x1800d1b05  mov     [rbp+57h+arg_10], r14
0x1800d1b09  lea     rdx, [rbp+57h+arg_10]
0x1800d1b0d  mov     rcx, rdi
0x1800d1b10  mov     rax, rbx
0x1800d1b13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1b18  mov     ebx, eax
0x1800d1b1a  test    eax, eax
0x1800d1b1c  jns     short loc_1800D1B43
0x1800d1b1e  mov     edx, 1B1h; void *
0x1800d1b23  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x1800d1b2a  mov     r9d, eax; char *
0x1800d1b2d  mov     rcx, [rbp+5Fh]; this
0x1800d1b31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d1b36  nop
0x1800d1b37  mov     rcx, [rbp+57h+arg_10]; string
0x1800d1b3b  call    cs:__imp_WindowsDeleteString
0x1800d1b41  jmp     short loc_1800D1B6A
0x1800d1b43  mov     rdx, r15; newString
0x1800d1b46  mov     rcx, [rbp+57h+arg_10]; string
0x1800d1b4a  call    cs:__imp_WindowsDuplicateString
0x1800d1b50  mov     ebx, eax
0x1800d1b52  test    eax, eax
0x1800d1b54  jns     short loc_1800D1B5D
0x1800d1b56  mov     edx, 1B2h
0x1800d1b5b  jmp     short loc_1800D1B23
0x1800d1b5d  mov     rcx, [rbp+57h+arg_10]; string
0x1800d1b61  call    cs:__imp_WindowsDeleteString
0x1800d1b67  mov     ebx, r14d
0x1800d1b6a  mov     [rbp+57h+arg_10], r14
0x1800d1b6e  mov     rcx, [rbp+57h+string]; string
0x1800d1b72  call    cs:__imp_WindowsDeleteString
0x1800d1b78  mov     [rbp+57h+string], r14
0x1800d1b7c  mov     rcx, [rbp+57h+var_B8]; string
0x1800d1b80  call    cs:__imp_WindowsDeleteString
0x1800d1b86  mov     [rbp+57h+var_B8], r14
0x1800d1b8a  jmp     loc_1800D1F70
0x1800d1b8f  mov     rcx, [rbp+57h+string]; string
0x1800d1b93  call    cs:__imp_WindowsDeleteString
0x1800d1b99  mov     [rbp+57h+string], r14
0x1800d1b9d  mov     rcx, [rbp+57h+var_B8]; string
0x1800d1ba1  call    cs:__imp_WindowsDeleteString
0x1800d1ba7  mov     [rbp+57h+var_90], r14
0x1800d1bab  mov     rax, [rsi]
0x1800d1bae  lea     rdx, [rbp+57h+var_90]
0x1800d1bb2  mov     rcx, rsi
0x1800d1bb5  mov     rax, [rax+30h]
0x1800d1bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1bbe  mov     ebx, eax
0x1800d1bc0  test    eax, eax
0x1800d1bc2  jns     short loc_1800D1BE1
0x1800d1bc4  mov     rcx, [rbp+5Fh]; this
0x1800d1bc8  mov     r9d, eax; char *
0x1800d1bcb  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x1800d1bd2  mov     edx, 1BAh; void *
0x1800d1bd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d1bdc  jmp     loc_1800D1F70
0x1800d1be1  lea     rcx, [rbp+57h+var_98]
0x1800d1be5  call    ??$GetActivationFactory@UIDynamicAppUriHandlerStatics@StateRepository@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIDynamicAppUriHandlerStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics>(ushort const *)
0x1800d1bea  nop
0x1800d1beb  mov     [rsp+110h+var_D8], r14
0x1800d1bf0  mov     rdi, [rbp+57h+var_98]
0x1800d1bf4  mov     rax, [rdi]
0x1800d1bf7  mov     rbx, [rax+80h]
0x1800d1bfe  lea     rcx, [rsp+110h+var_D8]
0x1800d1c03  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d1c08  lea     r8, [rsp+110h+var_D8]
0x1800d1c0d  mov     rdx, [rbp+57h+var_90]
0x1800d1c11  mov     rcx, rdi
0x1800d1c14  mov     rax, rbx
0x1800d1c17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1c1c  mov     [rbp+57h+var_88], r14
0x1800d1c20  mov     rcx, [rsp+110h+var_D8]
0x1800d1c25  mov     rax, [rcx]
0x1800d1c28  lea     rdx, [rbp+57h+var_88]
0x1800d1c2c  mov     rax, [rax+50h]
0x1800d1c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1c35  lea     rcx, [rbp+57h+var_A0]
0x1800d1c39  call    ??$GetActivationFactory@UIDynamicAppUriHandlerGroupStatics@StateRepository@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIDynamicAppUriHandlerGroupStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::StateRepository::IDynamicAppUriHandlerGroupStatics>(ushort const *)
0x1800d1c3e  nop
0x1800d1c3f  mov     [rbp+57h+var_C0], r14
0x1800d1c43  mov     rdi, [rbp+57h+var_A0]
0x1800d1c47  mov     rax, [rdi]
0x1800d1c4a  mov     rbx, [rax+70h]
0x1800d1c4e  lea     rcx, [rbp+57h+var_C0]
0x1800d1c52  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d1c57  lea     r8, [rbp+57h+var_C0]
0x1800d1c5b  mov     rdx, [rbp+57h+var_88]
0x1800d1c5f  mov     rcx, rdi
0x1800d1c62  mov     rax, rbx
0x1800d1c65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1c6a  mov     [rbp+57h+arg_8], r14
0x1800d1c6e  mov     rdi, [rbp+57h+var_C0]
0x1800d1c72  mov     rax, [rdi]
0x1800d1c75  mov     rbx, [rax+90h]
0x1800d1c7c  xor     ecx, ecx; string
0x1800d1c7e  call    cs:__imp_WindowsDeleteString
0x1800d1c84  mov     [rbp+57h+arg_8], r14
0x1800d1c88  lea     rdx, [rbp+57h+arg_8]
0x1800d1c8c  mov     rcx, rdi
0x1800d1c8f  mov     rax, rbx
0x1800d1c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1c97  lea     rcx, [rbp+57h+var_A8]
0x1800d1c9b  call    ??$GetActivationFactory@UIAppUriHandlerGroupStatics@StateRepository@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIAppUriHandlerGroupStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::StateRepository::IAppUriHandlerGroupStatics>(ushort const *)
0x1800d1ca0  nop
0x1800d1ca1  mov     [rbp+57h+var_C8], r14
0x1800d1ca5  mov     rdi, [rbp+57h+var_A8]
0x1800d1ca9  mov     rax, [rdi]
0x1800d1cac  mov     rbx, [rax+70h]
0x1800d1cb0  lea     rcx, [rbp+57h+var_C8]
0x1800d1cb4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d1cb9  lea     r8, [rbp+57h+var_C8]
0x1800d1cbd  mov     rdx, [rbp+57h+arg_8]
0x1800d1cc1  mov     rcx, rdi
0x1800d1cc4  mov     rax, rbx
0x1800d1cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1ccc  mov     [rbp+57h+arg_0], r14d
0x1800d1cd0  mov     rcx, [rbp+57h+var_C8]
0x1800d1cd4  mov     [rbp+57h+var_70], rcx
0x1800d1cd8  lea     rax, [rbp+57h+arg_0]
0x1800d1cdc  mov     [rbp+57h+var_60], rax
0x1800d1ce0  mov     [rbp+57h+var_58], r14d
0x1800d1ce4  mov     [rbp+57h+var_50], r14
0x1800d1ce8  mov     rax, [rcx]
0x1800d1ceb  lea     rdx, [rbp+57h+var_68]
0x1800d1cef  mov     rax, [rax+38h]
0x1800d1cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1cf8  mov     rcx, [rbp+57h+var_60]
0x1800d1cfc  mov     [rcx], eax
0x1800d1cfe  xor     edx, edx
0x1800d1d00  lea     rcx, [rbp+57h+var_70]
0x1800d1d04  call    ?get_at_current@?$vector_range_nothrow@U?$IVectorView@PEAVAppUriHandlerGroup@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@@wil@@QEAAXI@Z; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::AppUriHandlerGroup *>>::get_at_current(uint)
0x1800d1d09  mov     r13d, [rbp+57h+var_68]
0x1800d1d0d  xor     ebx, ebx
0x1800d1d0f  mov     rax, [rbp+57h+var_60]
0x1800d1d13  cmp     [rax], ebx
0x1800d1d15  jl      loc_1800D1F17
0x1800d1d1b  cmp     r14d, r13d
0x1800d1d1e  jz      loc_1800D1F17
0x1800d1d24  mov     [rsp+110h+var_E0], rbx
0x1800d1d29  mov     rdi, [rbp+57h+var_50]
0x1800d1d2d  mov     rax, [rdi]
0x1800d1d30  mov     rbx, [rax+50h]
0x1800d1d34  lea     rcx, [rsp+110h+var_E0]
0x1800d1d39  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d1d3e  lea     rdx, [rsp+110h+var_E0]
0x1800d1d43  mov     rcx, rdi
0x1800d1d46  mov     rax, rbx
0x1800d1d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1d4e  xor     ebx, ebx
0x1800d1d50  mov     [rbp+57h+var_78], rbx
0x1800d1d54  mov     rcx, [rsp+110h+var_E0]
0x1800d1d59  mov     rax, [rcx]
0x1800d1d5c  lea     rdx, [rbp+57h+var_78]
0x1800d1d60  mov     rax, [rax+40h]
0x1800d1d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1d69  mov     [rbp+57h+var_80], rbx
0x1800d1d6d  mov     rax, [rsi]
0x1800d1d70  lea     rdx, [rbp+57h+var_80]
0x1800d1d74  mov     rcx, rsi
0x1800d1d77  mov     rax, [rax+40h]
0x1800d1d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1d80  mov     rax, [rbp+57h+var_80]
0x1800d1d84  cmp     [rbp+57h+var_78], rax
0x1800d1d88  jz      short loc_1800D1DA8
0x1800d1d8a  lea     rcx, [rsp+110h+var_E0]
0x1800d1d8f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d1d94  inc     r14d
0x1800d1d97  mov     edx, r14d
0x1800d1d9a  lea     rcx, [rbp+57h+var_70]
0x1800d1d9e  call    ?get_at_current@?$vector_range_nothrow@U?$IVectorView@PEAVAppUriHandlerGroup@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@@wil@@QEAAXI@Z; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::AppUriHandlerGroup *>>::get_at_current(uint)
0x1800d1da3  jmp     loc_1800D1D0F
0x1800d1da8  mov     rcx, [rsp+110h+var_E0]
0x1800d1dad  xor     esi, esi
0x1800d1daf  test    rcx, rcx
0x1800d1db2  jz      short loc_1800D1DC5
0x1800d1db4  mov     rax, [rcx]
0x1800d1db7  mov     rax, [rax+8]
0x1800d1dbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1dc0  mov     rcx, [rsp+110h+var_E0]
0x1800d1dc5  mov     [r12], rcx
0x1800d1dc9  mov     [rbp+57h+arg_18], rsi
0x1800d1dcd  mov     rdi, [rsp+110h+var_D8]
0x1800d1dd2  mov     rax, [rdi]
0x1800d1dd5  mov     rbx, [rax+70h]
0x1800d1dd9  xor     ecx, ecx; string
0x1800d1ddb  call    cs:__imp_WindowsDeleteString
0x1800d1de1  mov     [rbp+57h+arg_18], rsi
0x1800d1de5  lea     rdx, [rbp+57h+arg_18]
0x1800d1de9  mov     rcx, rdi
0x1800d1dec  mov     rax, rbx
0x1800d1def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1df4  mov     ebx, eax
0x1800d1df6  test    eax, eax
0x1800d1df8  jns     loc_1800D1E89
0x1800d1dfe  mov     edx, 1E4h; void *
0x1800d1e03  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x1800d1e0a  mov     r9d, eax; char *
0x1800d1e0d  mov     rcx, [rbp+5Fh]; this
0x1800d1e11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d1e16  nop
0x1800d1e17  mov     rcx, [rbp+57h+arg_18]; string
0x1800d1e1b  call    cs:__imp_WindowsDeleteString
0x1800d1e21  mov     [rbp+57h+arg_18], rsi
0x1800d1e25  lea     rcx, [rsp+110h+var_E0]
0x1800d1e2a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d1e2f  nop
0x1800d1e30  lea     rcx, [rbp+57h+var_50]
0x1800d1e34  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d1e39  nop
0x1800d1e3a  lea     rcx, [rbp+57h+var_C8]
0x1800d1e3e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d1e43  nop
0x1800d1e44  lea     rcx, [rbp+57h+var_A8]
0x1800d1e48  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1800d1e4d  nop
0x1800d1e4e  mov     rcx, [rbp+57h+arg_8]; string
0x1800d1e52  call    cs:__imp_WindowsDeleteString
  ... truncated ...
```
