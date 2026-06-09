# CSyncRootManagerStatics::CreateStorageProviderInfo(Windows::Storage::Provider::IStorageProviderSyncRootInfo *)

- ea: `0x1803239e0`
- end: `0x180323f2b`
- name: `?CreateStorageProviderInfo@CSyncRootManagerStatics@@AEAA?AV?$com_ptr_t@UIStorageProviderInfo@@Uerr_exception_policy@wil@@@wil@@PEAUIStorageProviderSyncRootInfo@Provider@Storage@Windows@@@Z`
- size: `1355`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18033b6e0`

## callees

- `0x18000ee84`
- `0x18001c14c`
- `0x1802252d8`
- `0x1803239e0`
- `0x18035387c`
- `0x1803a4cb0`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180323d69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180323d69`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180323d31`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180323d31`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180323a3a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180323a3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180323a8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180323af0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180323b52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180323cd9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180323d0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180323a8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180323af0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180323b52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180323cd9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180323d0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180323a59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180323abb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180323b1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180323ca1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180323cfd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180323d7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180323d8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180323d9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180323a59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180323abb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180323b1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180323ca1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180323cfd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180323d7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180323d8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180323d9a`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
LPVOID *__fastcall CSyncRootManagerStatics::CreateStorageProviderInfo(__int64 a1, LPVOID *a2, __int64 *a3)
{
  HRESULT Instance; // eax
  __int64 (__fastcall *v6)(__int64 *, HSTRING *); // rbx
  int v7; // eax
  LPVOID v8; // rdi
  __int64 (__fastcall *v9)(LPVOID, PCWSTR); // rbx
  PCWSTR StringRawBuffer; // rax
  int v11; // eax
  __int64 (__fastcall *v12)(__int64 *, HSTRING *); // rbx
  int v13; // eax
  LPVOID v14; // rdi
  __int64 (__fastcall *v15)(LPVOID, PCWSTR); // rbx
  PCWSTR v16; // rax
  int v17; // eax
  __int64 (__fastcall *v18)(__int64 *, HSTRING *); // rbx
  int v19; // eax
  LPVOID v20; // rdi
  __int64 (__fastcall *v21)(LPVOID, PCWSTR); // rbx
  PCWSTR v22; // rax
  int v23; // eax
  int v24; // eax
  unsigned int v25; // ebx
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rbx
  __int64 (__fastcall *v33)(__int64, HSTRING *); // rdi
  int v34; // eax
  LPVOID v35; // rdi
  __int64 (__fastcall *v36)(LPVOID, PCWSTR); // rbx
  PCWSTR v37; // rax
  int v38; // eax
  const unsigned __int16 *v39; // rax
  CSyncRootManagerStatics *v40; // rcx
  HSTRING v41; // rbx
  HRESULT v42; // eax
  int v43; // eax
  int ppv; // [rsp+20h] [rbp-59h]
  __int64 *v46; // [rsp+38h] [rbp-41h] BYREF
  __int64 v47; // [rsp+40h] [rbp-39h] BYREF
  char v48; // [rsp+48h] [rbp-31h]
  LPVOID *v49; // [rsp+50h] [rbp-29h]
  char v50; // [rsp+58h] [rbp-21h] BYREF
  _BYTE v51[7]; // [rsp+59h] [rbp-20h] BYREF
  HSTRING v52; // [rsp+60h] [rbp-19h] BYREF
  int v53; // [rsp+68h] [rbp-11h] BYREF
  HSTRING v54; // [rsp+70h] [rbp-9h] BYREF
  HSTRING v55; // [rsp+78h] [rbp-1h] BYREF
  HSTRING string; // [rsp+80h] [rbp+7h] BYREF
  __int64 v57; // [rsp+88h] [rbp+Fh] BYREF
  GUID pclsid; // [rsp+90h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v49 = a2;
  *a2 = 0;
  Instance = CoCreateInstance(&CLSID_StorageProviderInfo, 0, 3u, &GUID_ca01c124_2769_4576_bf12_8a54ee671a86, a2);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x393,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
  string = 0;
  v6 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*a3 + 48);
  WindowsDeleteString(0);
  string = 0;
  v7 = v6(a3, &string);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x397,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v7,
      ppv);
  v8 = *a2;
  v9 = *(__int64 (__fastcall **)(LPVOID, PCWSTR))(*(_QWORD *)*a2 + 32LL);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v11 = v9(v8, StringRawBuffer);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x398,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v11,
      ppv);
  v55 = 0;
  v12 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*a3 + 96);
  WindowsDeleteString(0);
  v55 = 0;
  v13 = v12(a3, &v55);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x39C,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v13,
      ppv);
  v14 = *a2;
  v15 = *(__int64 (__fastcall **)(LPVOID, PCWSTR))(*(_QWORD *)*a2 + 72LL);
  v16 = WindowsGetStringRawBuffer(v55, 0);
  v17 = v15(v14, v16);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x39D,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v17,
      ppv);
  v54 = 0;
  v18 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*a3 + 112);
  WindowsDeleteString(0);
  v54 = 0;
  v19 = v18(a3, &v54);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3A1,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v19,
      ppv);
  v20 = *a2;
  v21 = *(__int64 (__fastcall **)(LPVOID, PCWSTR))(*(_QWORD *)*a2 + 96LL);
  v22 = WindowsGetStringRawBuffer(v54, 0);
  v23 = v21(v20, v22);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3A2,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v23,
      ppv);
  v50 = 0;
  v24 = (*(__int64 (__fastcall **)(__int64 *, char *))(*a3 + 256))(a3, &v50);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3A7,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v24,
      ppv);
  v25 = v50 != 0 ? 34 : 2;
  v51[0] = 0;
  v26 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *))(*a3 + 208))(a3, v51);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3AB,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v26,
      ppv);
  if ( v51[0] )
    v25 |= 0x200u;
  v27 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)*a2 + 176LL))(*a2, 4095, v25);
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3AE,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v27,
      ppv);
  v53 = 0;
  v28 = (*(__int64 (__fastcall **)(__int64 *, int *))(*a3 + 240))(a3, &v53);
  if ( v28 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3B1,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v28,
      ppv);
  if ( v53 == 1 )
  {
    v29 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *))(*(_QWORD *)*a2 + 208LL))(*a2, L"Personal");
    if ( v29 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3B4,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
        (const char *)(unsigned int)v29,
        ppv);
  }
  v57 = 0;
  v30 = *a3;
  v46 = &v57;
  v47 = 0;
  v48 = 1;
  v31 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v30 + 280))(a3, &v47);
  if ( v31 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3B9,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v31,
      ppv);
  wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IUriRuntimeClass,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IUriRuntimeClass,wil::err_exception_policy>>(&v46);
  v32 = v57;
  if ( v57 )
  {
    v52 = 0;
    v33 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v57 + 48LL);
    WindowsDeleteString(0);
    v52 = 0;
    v34 = v33(v32, &v52);
    if ( v34 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3BD,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
        (const char *)(unsigned int)v34,
        ppv);
    v35 = *a2;
    v36 = *(__int64 (__fastcall **)(LPVOID, PCWSTR))(*(_QWORD *)*a2 + 224LL);
    v37 = WindowsGetStringRawBuffer(v52, 0);
    v38 = v36(v35, v37);
    if ( v38 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3BE,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
        (const char *)(unsigned int)v38,
        ppv);
    WindowsDeleteString(v52);
  }
  v52 = 0;
  v39 = WindowsGetStringRawBuffer(string, 0);
  CSyncRootManagerStatics::GetNamespaceCLSIDForSyncRoot(v40, v39, (unsigned __int16 **)&v52);
  pclsid = 0;
  v41 = v52;
  v42 = CLSIDFromString((LPCOLESTR)v52, &pclsid);
  if ( v42 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3C6,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v42,
      ppv);
  v43 = (*(__int64 (__fastcall **)(LPVOID, GUID *))(*(_QWORD *)*a2 + 304LL))(*a2, &pclsid);
  if ( v43 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3C7,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v43,
      ppv);
  if ( v41 )
    CoTaskMemFree(v41);
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v57);
  WindowsDeleteString(v54);
  v54 = 0;
  WindowsDeleteString(v55);
  v55 = 0;
  WindowsDeleteString(string);
  return a2;
}

```

## disassembly

```asm
0x1803239e0  mov     [rsp-8+arg_0], rbx
0x1803239e5  push    rbp
0x1803239e6  push    rsi
0x1803239e7  push    rdi
0x1803239e8  push    r14
0x1803239ea  push    r15
0x1803239ec  lea     rbp, [rsp-37h]
0x1803239f1  sub     rsp, 0B0h
0x1803239f8  mov     rax, cs:__security_cookie
0x1803239ff  xor     rax, rsp
0x180323a02  mov     [rbp+57h+var_30], rax
0x180323a06  mov     rsi, r8
0x180323a09  mov     r14, rdx
0x180323a0c  mov     [rbp+57h+var_80], rdx
0x180323a10  xor     r15d, r15d
0x180323a13  mov     [rbp+57h+var_A0], r15d
0x180323a17  mov     [rbp+57h+var_A0], 1
0x180323a1e  mov     [rdx], r15
0x180323a21  mov     qword ptr [rsp+0D0h+ppv], rdx; int
0x180323a26  lea     r9, _GUID_ca01c124_2769_4576_bf12_8a54ee671a86; riid
0x180323a2d  xor     edx, edx; pUnkOuter
0x180323a2f  lea     r8d, [r15+3]; dwClsContext
0x180323a33  lea     rcx, CLSID_StorageProviderInfo; rclsid
0x180323a3a  call    cs:__imp_CoCreateInstance
0x180323a40  mov     rcx, [rbp+5Fh]; this
0x180323a44  test    eax, eax
0x180323a46  js      loc_180323DDB
0x180323a4c  mov     [rbp+57h+string], r15
0x180323a50  mov     rax, [rsi]
0x180323a53  mov     rbx, [rax+30h]
0x180323a57  xor     ecx, ecx; string
0x180323a59  call    cs:__imp_WindowsDeleteString
0x180323a5f  mov     [rbp+57h+string], r15
0x180323a63  lea     rdx, [rbp+57h+string]
0x180323a67  mov     rcx, rsi
0x180323a6a  mov     rax, rbx
0x180323a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180323a72  mov     rcx, [rbp+5Fh]; this
0x180323a76  test    eax, eax
0x180323a78  js      loc_180323DF0
0x180323a7e  mov     rdi, [r14]
0x180323a81  mov     rax, [rdi]
0x180323a84  mov     rbx, [rax+20h]
0x180323a88  xor     edx, edx; length
0x180323a8a  mov     rcx, [rbp+57h+string]; string
0x180323a8e  call    cs:__imp_WindowsGetStringRawBuffer
0x180323a94  mov     rdx, rax
0x180323a97  mov     rcx, rdi
0x180323a9a  mov     rax, rbx
0x180323a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180323aa2  mov     rcx, [rbp+5Fh]; this
0x180323aa6  test    eax, eax
0x180323aa8  js      loc_180323E05
0x180323aae  mov     [rbp+57h+var_58], r15
0x180323ab2  mov     rax, [rsi]
0x180323ab5  mov     rbx, [rax+60h]
0x180323ab9  xor     ecx, ecx; string
0x180323abb  call    cs:__imp_WindowsDeleteString
0x180323ac1  mov     [rbp+57h+var_58], r15
0x180323ac5  lea     rdx, [rbp+57h+var_58]
0x180323ac9  mov     rcx, rsi
0x180323acc  mov     rax, rbx
0x180323acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180323ad4  mov     rcx, [rbp+5Fh]; this
0x180323ad8  test    eax, eax
0x180323ada  js      loc_180323E1A
0x180323ae0  mov     rdi, [r14]
0x180323ae3  mov     rax, [rdi]
0x180323ae6  mov     rbx, [rax+48h]
0x180323aea  xor     edx, edx; length
0x180323aec  mov     rcx, [rbp+57h+var_58]; string
0x180323af0  call    cs:__imp_WindowsGetStringRawBuffer
0x180323af6  mov     rdx, rax
0x180323af9  mov     rcx, rdi
0x180323afc  mov     rax, rbx
0x180323aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180323b04  mov     rcx, [rbp+5Fh]; this
0x180323b08  test    eax, eax
0x180323b0a  js      loc_180323E2F
0x180323b10  mov     [rbp+57h+var_60], r15
0x180323b14  mov     rax, [rsi]
0x180323b17  mov     rbx, [rax+70h]
0x180323b1b  xor     ecx, ecx; string
0x180323b1d  call    cs:__imp_WindowsDeleteString
0x180323b23  mov     [rbp+57h+var_60], r15
0x180323b27  lea     rdx, [rbp+57h+var_60]
0x180323b2b  mov     rcx, rsi
0x180323b2e  mov     rax, rbx
0x180323b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180323b36  mov     rcx, [rbp+5Fh]; this
0x180323b3a  test    eax, eax
0x180323b3c  js      loc_180323E44
0x180323b42  mov     rdi, [r14]
0x180323b45  mov     rax, [rdi]
0x180323b48  mov     rbx, [rax+60h]
0x180323b4c  xor     edx, edx; length
0x180323b4e  mov     rcx, [rbp+57h+var_60]; string
0x180323b52  call    cs:__imp_WindowsGetStringRawBuffer
0x180323b58  mov     rdx, rax
0x180323b5b  mov     rcx, rdi
0x180323b5e  mov     rax, rbx
0x180323b61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180323b66  mov     rcx, [rbp+5Fh]; this
0x180323b6a  test    eax, eax
0x180323b6c  js      loc_180323E59
0x180323b72  mov     [rbp+57h+var_78], r15b
0x180323b76  mov     rax, [rsi]
0x180323b79  lea     rdx, [rbp+57h+var_78]
0x180323b7d  mov     rcx, rsi
0x180323b80  mov     rax, [rax+100h]
0x180323b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180323b8c  mov     rcx, [rbp+5Fh]; this
0x180323b90  test    eax, eax
0x180323b92  js      loc_180323E6E
0x180323b98  mov     al, [rbp+57h+var_78]
0x180323b9b  neg     al
0x180323b9d  sbb     ebx, ebx
0x180323b9f  and     ebx, 20h
0x180323ba2  add     ebx, 2
0x180323ba5  mov     [rbp+57h+var_77], r15b
0x180323ba9  mov     rax, [rsi]
0x180323bac  lea     rdx, [rbp+57h+var_77]
0x180323bb0  mov     rcx, rsi
0x180323bb3  mov     rax, [rax+0D0h]
0x180323bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180323bbf  mov     rcx, [rbp+5Fh]; this
0x180323bc3  test    eax, eax
0x180323bc5  js      loc_180323E83
0x180323bcb  cmp     [rbp+57h+var_77], r15b
0x180323bcf  jz      short loc_180323BD5
0x180323bd1  bts     ebx, 9
0x180323bd5  mov     rcx, [r14]
0x180323bd8  mov     rax, [rcx]
0x180323bdb  mov     r8d, ebx
0x180323bde  mov     edx, 0FFFh
0x180323be3  mov     rax, [rax+0B0h]
0x180323bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180323bef  mov     rcx, [rbp+5Fh]; this
0x180323bf3  test    eax, eax
0x180323bf5  js      loc_180323E98
0x180323bfb  mov     [rbp+57h+var_68], r15d
0x180323bff  mov     rax, [rsi]
0x180323c02  lea     rdx, [rbp+57h+var_68]
0x180323c06  mov     rcx, rsi
0x180323c09  mov     rax, [rax+0F0h]
0x180323c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180323c15  mov     rcx, [rbp+5Fh]; this
0x180323c19  test    eax, eax
0x180323c1b  js      loc_180323EAD
0x180323c21  cmp     [rbp+57h+var_68], 1
0x180323c25  jnz     short loc_180323C4C
0x180323c27  mov     rcx, [r14]
0x180323c2a  mov     rax, [rcx]
0x180323c2d  lea     rdx, aPersonal; "Personal"
0x180323c34  mov     rax, [rax+0D0h]
0x180323c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180323c40  mov     rcx, [rbp+5Fh]; this
0x180323c44  test    eax, eax
0x180323c46  js      loc_180323EC2
0x180323c4c  mov     [rbp+57h+var_48], r15
0x180323c50  mov     rax, [rsi]
0x180323c53  lea     rcx, [rbp+57h+var_48]
0x180323c57  mov     [rbp+57h+var_98], rcx
0x180323c5b  mov     [rbp+57h+var_90], r15
0x180323c5f  mov     [rbp+57h+var_88], 1
0x180323c63  lea     rdx, [rbp+57h+var_90]
0x180323c67  mov     rcx, rsi
0x180323c6a  mov     rax, [rax+118h]
0x180323c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180323c76  mov     rcx, [rbp+5Fh]; this
0x180323c7a  test    eax, eax
0x180323c7c  js      loc_180323ED7
0x180323c82  lea     rcx, [rbp+57h+var_98]
0x180323c86  call    ??1?$out_param_t@V?$com_ptr_t@UIUriRuntimeClass@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IUriRuntimeClass,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IUriRuntimeClass,wil::err_exception_policy>>(void)
0x180323c8b  mov     rbx, [rbp+57h+var_48]
0x180323c8f  test    rbx, rbx
0x180323c92  jz      short loc_180323D03
0x180323c94  mov     [rbp+57h+var_70], r15
0x180323c98  mov     rax, [rbx]
0x180323c9b  mov     rdi, [rax+30h]
0x180323c9f  xor     ecx, ecx; string
0x180323ca1  call    cs:__imp_WindowsDeleteString
0x180323ca7  mov     [rbp+57h+var_70], r15
0x180323cab  lea     rdx, [rbp+57h+var_70]
0x180323caf  mov     rcx, rbx
0x180323cb2  mov     rax, rdi
0x180323cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180323cba  mov     rcx, [rbp+5Fh]; this
0x180323cbe  test    eax, eax
0x180323cc0  js      loc_180323EEC
0x180323cc6  mov     rdi, [r14]
0x180323cc9  mov     rax, [rdi]
0x180323ccc  mov     rbx, [rax+0E0h]
0x180323cd3  xor     edx, edx; length
0x180323cd5  mov     rcx, [rbp+57h+var_70]; string
0x180323cd9  call    cs:__imp_WindowsGetStringRawBuffer
0x180323cdf  mov     rdx, rax
0x180323ce2  mov     rcx, rdi
0x180323ce5  mov     rax, rbx
0x180323ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180323ced  mov     rcx, [rbp+5Fh]; this
0x180323cf1  test    eax, eax
0x180323cf3  js      loc_180323F01
0x180323cf9  mov     rcx, [rbp+57h+var_70]; string
0x180323cfd  call    cs:__imp_WindowsDeleteString
0x180323d03  mov     [rbp+57h+var_70], r15
0x180323d07  xor     edx, edx; length
0x180323d09  mov     rcx, [rbp+57h+string]; string
0x180323d0d  call    cs:__imp_WindowsGetStringRawBuffer
0x180323d13  lea     r8, [rbp+57h+var_70]; unsigned __int16 **
0x180323d17  mov     rdx, rax; unsigned __int16 *
0x180323d1a  call    ?GetNamespaceCLSIDForSyncRoot@CSyncRootManagerStatics@@AEAAXPEBGPEAPEAG@Z; CSyncRootManagerStatics::GetNamespaceCLSIDForSyncRoot(ushort const *,ushort * *)
0x180323d1f  xorps   xmm0, xmm0
0x180323d22  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x180323d26  lea     rdx, [rbp+57h+pclsid]; pclsid
0x180323d2a  mov     rbx, [rbp+57h+var_70]
0x180323d2e  mov     rcx, rbx; lpsz
0x180323d31  call    cs:__imp_CLSIDFromString
0x180323d37  mov     rcx, [rbp+5Fh]; this
0x180323d3b  test    eax, eax
0x180323d3d  js      loc_180323F16
0x180323d43  mov     rcx, [r14]
0x180323d46  mov     rax, [rcx]
0x180323d49  lea     rdx, [rbp+57h+pclsid]
0x180323d4d  mov     rax, [rax+130h]
0x180323d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180323d59  mov     rcx, [rbp+5Fh]; this
0x180323d5d  test    eax, eax
0x180323d5f  js      short loc_180323DC6
0x180323d61  test    rbx, rbx
0x180323d64  jz      short loc_180323D70
0x180323d66  mov     rcx, rbx; pv
0x180323d69  call    cs:__imp_CoTaskMemFree
0x180323d6f  nop
0x180323d70  lea     rcx, [rbp+57h+var_48]
0x180323d74  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180323d79  nop
0x180323d7a  mov     rcx, [rbp+57h+var_60]; string
0x180323d7e  call    cs:__imp_WindowsDeleteString
0x180323d84  mov     [rbp+57h+var_60], r15
0x180323d88  mov     rcx, [rbp+57h+var_58]; string
0x180323d8c  call    cs:__imp_WindowsDeleteString
0x180323d92  mov     [rbp+57h+var_58], r15
0x180323d96  mov     rcx, [rbp+57h+string]; string
0x180323d9a  call    cs:__imp_WindowsDeleteString
0x180323da0  mov     rax, r14
0x180323da3  mov     rcx, [rbp+57h+var_30]
0x180323da7  xor     rcx, rsp; StackCookie
0x180323daa  call    __security_check_cookie
0x180323daf  mov     rbx, [rsp+0D0h+arg_0]
0x180323db7  add     rsp, 0B0h
0x180323dbe  pop     r15
0x180323dc0  pop     r14
0x180323dc2  pop     rdi
0x180323dc3  pop     rsi
0x180323dc4  pop     rbp
0x180323dc5  retn
0x180323dc6  mov     r9d, eax; char *
0x180323dc9  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180323dd0  mov     edx, 3C7h; void *
0x180323dd5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180323ddb  mov     r9d, eax; char *
0x180323dde  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180323de5  mov     edx, 393h; void *
0x180323dea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180323df0  mov     r9d, eax; char *
0x180323df3  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180323dfa  mov     edx, 397h; void *
0x180323dff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180323e05  mov     r9d, eax; char *
0x180323e08  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180323e0f  mov     edx, 398h; void *
0x180323e14  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180323e1a  mov     r9d, eax; char *
0x180323e1d  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180323e24  mov     edx, 39Ch; void *
0x180323e29  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180323e2f  mov     r9d, eax; char *
0x180323e32  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180323e39  mov     edx, 39Dh; void *
0x180323e3e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180323e44  mov     r9d, eax; char *
0x180323e47  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180323e4e  mov     edx, 3A1h; void *
0x180323e53  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180323e59  mov     r9d, eax; char *
0x180323e5c  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180323e63  mov     edx, 3A2h; void *
0x180323e68  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180323e6e  mov     r9d, eax; char *
0x180323e71  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180323e78  mov     edx, 3A7h; void *
0x180323e7d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180323e83  mov     r9d, eax; char *
0x180323e86  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180323e8d  mov     edx, 3ABh; void *
0x180323e92  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180323e98  mov     r9d, eax; char *
0x180323e9b  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180323ea2  mov     edx, 3AEh; void *
  ... truncated ...
```
