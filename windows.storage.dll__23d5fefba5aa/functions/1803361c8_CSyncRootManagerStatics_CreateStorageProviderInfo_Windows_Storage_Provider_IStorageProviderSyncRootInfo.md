# CSyncRootManagerStatics::CreateStorageProviderInfo(Windows::Storage::Provider::IStorageProviderSyncRootInfo *)

- ea: `0x1803361c8`
- end: `0x18033676a`
- name: `?CreateStorageProviderInfo@CSyncRootManagerStatics@@AEAA?AV?$com_ptr_t@UIStorageProviderInfo@@Uerr_exception_policy@wil@@@wil@@PEAUIStorageProviderSyncRootInfo@Provider@Storage@Windows@@@Z`
- size: `1442`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18034d450`

## callees

- `0x180033c60`
- `0x180079ccc`
- `0x1801720d0`
- `0x180240b68`
- `0x1803361c8`
- `0x180363cdc`
- `0x1803b1f60`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18033655c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18033655c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180336222`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180336222`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180336282`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803362f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033635e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803364f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180336535`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180336282`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803362f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033635e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803364f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180336535`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180336247`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803362b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180336323`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803364b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033651f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803365aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803365be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803365d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180336247`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803362b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180336323`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803364b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033651f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803365aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803365be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803365d2`

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
  HRESULT v41; // eax
  int v42; // eax
  int ppv; // [rsp+20h] [rbp-59h]
  __int64 *v45; // [rsp+38h] [rbp-41h] BYREF
  __int64 v46; // [rsp+40h] [rbp-39h] BYREF
  char v47; // [rsp+48h] [rbp-31h]
  LPVOID *v48; // [rsp+50h] [rbp-29h]
  char v49; // [rsp+58h] [rbp-21h] BYREF
  _BYTE v50[7]; // [rsp+59h] [rbp-20h] BYREF
  HSTRING v51; // [rsp+60h] [rbp-19h] BYREF
  int v52; // [rsp+68h] [rbp-11h] BYREF
  HSTRING v53; // [rsp+70h] [rbp-9h] BYREF
  HSTRING v54; // [rsp+78h] [rbp-1h] BYREF
  HSTRING string; // [rsp+80h] [rbp+7h] BYREF
  __int64 v56; // [rsp+88h] [rbp+Fh] BYREF
  GUID pclsid; // [rsp+90h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v48 = a2;
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
  v54 = 0;
  v12 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*a3 + 96);
  WindowsDeleteString(0);
  v54 = 0;
  v13 = v12(a3, &v54);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x39C,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v13,
      ppv);
  v14 = *a2;
  v15 = *(__int64 (__fastcall **)(LPVOID, PCWSTR))(*(_QWORD *)*a2 + 72LL);
  v16 = WindowsGetStringRawBuffer(v54, 0);
  v17 = v15(v14, v16);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x39D,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v17,
      ppv);
  v53 = 0;
  v18 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*a3 + 112);
  WindowsDeleteString(0);
  v53 = 0;
  v19 = v18(a3, &v53);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3A1,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v19,
      ppv);
  v20 = *a2;
  v21 = *(__int64 (__fastcall **)(LPVOID, PCWSTR))(*(_QWORD *)*a2 + 96LL);
  v22 = WindowsGetStringRawBuffer(v53, 0);
  v23 = v21(v20, v22);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3A2,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v23,
      ppv);
  v49 = 0;
  v24 = (*(__int64 (__fastcall **)(__int64 *, char *))(*a3 + 256))(a3, &v49);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3A7,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v24,
      ppv);
  v25 = v49 != 0 ? 34 : 2;
  v50[0] = 0;
  v26 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *))(*a3 + 208))(a3, v50);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3AB,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v26,
      ppv);
  if ( v50[0] )
    v25 |= 0x200u;
  v27 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)*a2 + 176LL))(*a2, 4095, v25);
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3AE,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v27,
      ppv);
  v52 = 0;
  v28 = (*(__int64 (__fastcall **)(__int64 *, int *))(*a3 + 240))(a3, &v52);
  if ( v28 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3B1,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v28,
      ppv);
  if ( v52 == 1 )
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
  v56 = 0;
  v30 = *a3;
  v45 = &v56;
  v46 = 0;
  v47 = 1;
  v31 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v30 + 280))(a3, &v46);
  if ( v31 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3B9,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v31,
      ppv);
  wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IUriRuntimeClass,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IUriRuntimeClass,wil::err_exception_policy>>(&v45);
  v32 = v56;
  if ( v56 )
  {
    v51 = 0;
    v33 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v56 + 48LL);
    WindowsDeleteString(0);
    v51 = 0;
    v34 = v33(v32, &v51);
    if ( v34 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3BD,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
        (const char *)(unsigned int)v34,
        ppv);
    v35 = *a2;
    v36 = *(__int64 (__fastcall **)(LPVOID, PCWSTR))(*(_QWORD *)*a2 + 224LL);
    v37 = WindowsGetStringRawBuffer(v51, 0);
    v38 = v36(v35, v37);
    if ( v38 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3BE,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
        (const char *)(unsigned int)v38,
        ppv);
    WindowsDeleteString(v51);
  }
  v51 = 0;
  v39 = WindowsGetStringRawBuffer(string, 0);
  CSyncRootManagerStatics::GetNamespaceCLSIDForSyncRoot(v40, v39, (unsigned __int16 **)&v51);
  pclsid = 0;
  v41 = CLSIDFromString((LPCOLESTR)v51, &pclsid);
  if ( v41 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3C6,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v41,
      ppv);
  v42 = (*(__int64 (__fastcall **)(LPVOID, GUID *))(*(_QWORD *)*a2 + 304LL))(*a2, &pclsid);
  if ( v42 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3C7,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v42,
      ppv);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v51);
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v56);
  WindowsDeleteString(v53);
  v53 = 0;
  WindowsDeleteString(v54);
  v54 = 0;
  WindowsDeleteString(string);
  return a2;
}

```

## disassembly

```asm
0x1803361c8  mov     [rsp-8+arg_0], rbx
0x1803361cd  push    rbp
0x1803361ce  push    rsi
0x1803361cf  push    rdi
0x1803361d0  push    r14
0x1803361d2  push    r15
0x1803361d4  lea     rbp, [rsp-37h]
0x1803361d9  sub     rsp, 0B0h
0x1803361e0  mov     rax, cs:__security_cookie
0x1803361e7  xor     rax, rsp
0x1803361ea  mov     [rbp+57h+var_30], rax
0x1803361ee  mov     rsi, r8
0x1803361f1  mov     r14, rdx
0x1803361f4  mov     [rbp+57h+var_80], rdx
0x1803361f8  xor     r15d, r15d
0x1803361fb  mov     [rbp+57h+var_A0], r15d
0x1803361ff  mov     [rbp+57h+var_A0], 1
0x180336206  mov     [rdx], r15
0x180336209  mov     qword ptr [rsp+0D0h+ppv], rdx; int
0x18033620e  lea     r9, _GUID_ca01c124_2769_4576_bf12_8a54ee671a86; riid
0x180336215  xor     edx, edx; pUnkOuter
0x180336217  lea     r8d, [r15+3]; dwClsContext
0x18033621b  lea     rcx, CLSID_StorageProviderInfo; rclsid
0x180336222  call    cs:__imp_CoCreateInstance
0x180336229  nop     dword ptr [rax+rax+00h]
0x18033622e  mov     rcx, [rbp+5Fh]; this
0x180336232  test    eax, eax
0x180336234  js      loc_18033661A
0x18033623a  mov     [rbp+57h+string], r15
0x18033623e  mov     rax, [rsi]
0x180336241  mov     rbx, [rax+30h]
0x180336245  xor     ecx, ecx; string
0x180336247  call    cs:__imp_WindowsDeleteString
0x18033624e  nop     dword ptr [rax+rax+00h]
0x180336253  mov     [rbp+57h+string], r15
0x180336257  lea     rdx, [rbp+57h+string]
0x18033625b  mov     rcx, rsi
0x18033625e  mov     rax, rbx
0x180336261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180336266  mov     rcx, [rbp+5Fh]; this
0x18033626a  test    eax, eax
0x18033626c  js      loc_18033662F
0x180336272  mov     rdi, [r14]
0x180336275  mov     rax, [rdi]
0x180336278  mov     rbx, [rax+20h]
0x18033627c  xor     edx, edx; length
0x18033627e  mov     rcx, [rbp+57h+string]; string
0x180336282  call    cs:__imp_WindowsGetStringRawBuffer
0x180336289  nop     dword ptr [rax+rax+00h]
0x18033628e  mov     rdx, rax
0x180336291  mov     rcx, rdi
0x180336294  mov     rax, rbx
0x180336297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033629c  mov     rcx, [rbp+5Fh]; this
0x1803362a0  test    eax, eax
0x1803362a2  js      loc_180336644
0x1803362a8  mov     [rbp+57h+var_58], r15
0x1803362ac  mov     rax, [rsi]
0x1803362af  mov     rbx, [rax+60h]
0x1803362b3  xor     ecx, ecx; string
0x1803362b5  call    cs:__imp_WindowsDeleteString
0x1803362bc  nop     dword ptr [rax+rax+00h]
0x1803362c1  mov     [rbp+57h+var_58], r15
0x1803362c5  lea     rdx, [rbp+57h+var_58]
0x1803362c9  mov     rcx, rsi
0x1803362cc  mov     rax, rbx
0x1803362cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803362d4  mov     rcx, [rbp+5Fh]; this
0x1803362d8  test    eax, eax
0x1803362da  js      loc_180336659
0x1803362e0  mov     rdi, [r14]
0x1803362e3  mov     rax, [rdi]
0x1803362e6  mov     rbx, [rax+48h]
0x1803362ea  xor     edx, edx; length
0x1803362ec  mov     rcx, [rbp+57h+var_58]; string
0x1803362f0  call    cs:__imp_WindowsGetStringRawBuffer
0x1803362f7  nop     dword ptr [rax+rax+00h]
0x1803362fc  mov     rdx, rax
0x1803362ff  mov     rcx, rdi
0x180336302  mov     rax, rbx
0x180336305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033630a  mov     rcx, [rbp+5Fh]; this
0x18033630e  test    eax, eax
0x180336310  js      loc_18033666E
0x180336316  mov     [rbp+57h+var_60], r15
0x18033631a  mov     rax, [rsi]
0x18033631d  mov     rbx, [rax+70h]
0x180336321  xor     ecx, ecx; string
0x180336323  call    cs:__imp_WindowsDeleteString
0x18033632a  nop     dword ptr [rax+rax+00h]
0x18033632f  mov     [rbp+57h+var_60], r15
0x180336333  lea     rdx, [rbp+57h+var_60]
0x180336337  mov     rcx, rsi
0x18033633a  mov     rax, rbx
0x18033633d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180336342  mov     rcx, [rbp+5Fh]; this
0x180336346  test    eax, eax
0x180336348  js      loc_180336683
0x18033634e  mov     rdi, [r14]
0x180336351  mov     rax, [rdi]
0x180336354  mov     rbx, [rax+60h]
0x180336358  xor     edx, edx; length
0x18033635a  mov     rcx, [rbp+57h+var_60]; string
0x18033635e  call    cs:__imp_WindowsGetStringRawBuffer
0x180336365  nop     dword ptr [rax+rax+00h]
0x18033636a  mov     rdx, rax
0x18033636d  mov     rcx, rdi
0x180336370  mov     rax, rbx
0x180336373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180336378  mov     rcx, [rbp+5Fh]; this
0x18033637c  test    eax, eax
0x18033637e  js      loc_180336698
0x180336384  mov     [rbp+57h+var_78], r15b
0x180336388  mov     rax, [rsi]
0x18033638b  lea     rdx, [rbp+57h+var_78]
0x18033638f  mov     rcx, rsi
0x180336392  mov     rax, [rax+100h]
0x180336399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033639e  mov     rcx, [rbp+5Fh]; this
0x1803363a2  test    eax, eax
0x1803363a4  js      loc_1803366AD
0x1803363aa  mov     al, [rbp+57h+var_78]
0x1803363ad  neg     al
0x1803363af  sbb     ebx, ebx
0x1803363b1  and     ebx, 20h
0x1803363b4  add     ebx, 2
0x1803363b7  mov     [rbp+57h+var_77], r15b
0x1803363bb  mov     rax, [rsi]
0x1803363be  lea     rdx, [rbp+57h+var_77]
0x1803363c2  mov     rcx, rsi
0x1803363c5  mov     rax, [rax+0D0h]
0x1803363cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803363d1  mov     rcx, [rbp+5Fh]; this
0x1803363d5  test    eax, eax
0x1803363d7  js      loc_1803366C2
0x1803363dd  cmp     [rbp+57h+var_77], r15b
0x1803363e1  jz      short loc_1803363E7
0x1803363e3  bts     ebx, 9
0x1803363e7  mov     rcx, [r14]
0x1803363ea  mov     rax, [rcx]
0x1803363ed  mov     r8d, ebx
0x1803363f0  mov     edx, 0FFFh
0x1803363f5  mov     rax, [rax+0B0h]
0x1803363fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180336401  mov     rcx, [rbp+5Fh]; this
0x180336405  test    eax, eax
0x180336407  js      loc_1803366D7
0x18033640d  mov     [rbp+57h+var_68], r15d
0x180336411  mov     rax, [rsi]
0x180336414  lea     rdx, [rbp+57h+var_68]
0x180336418  mov     rcx, rsi
0x18033641b  mov     rax, [rax+0F0h]
0x180336422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180336427  mov     rcx, [rbp+5Fh]; this
0x18033642b  test    eax, eax
0x18033642d  js      loc_1803366EC
0x180336433  cmp     [rbp+57h+var_68], 1
0x180336437  jnz     short loc_18033645E
0x180336439  mov     rcx, [r14]
0x18033643c  mov     rax, [rcx]
0x18033643f  lea     rdx, aPersonal; "Personal"
0x180336446  mov     rax, [rax+0D0h]
0x18033644d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180336452  mov     rcx, [rbp+5Fh]; this
0x180336456  test    eax, eax
0x180336458  js      loc_180336701
0x18033645e  mov     [rbp+57h+var_48], r15
0x180336462  mov     rax, [rsi]
0x180336465  lea     rcx, [rbp+57h+var_48]
0x180336469  mov     [rbp+57h+var_98], rcx
0x18033646d  mov     [rbp+57h+var_90], r15
0x180336471  mov     [rbp+57h+var_88], 1
0x180336475  lea     rdx, [rbp+57h+var_90]
0x180336479  mov     rcx, rsi
0x18033647c  mov     rax, [rax+118h]
0x180336483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180336488  mov     rcx, [rbp+5Fh]; this
0x18033648c  test    eax, eax
0x18033648e  js      loc_180336716
0x180336494  lea     rcx, [rbp+57h+var_98]
0x180336498  call    ??1?$out_param_t@V?$com_ptr_t@UIUriRuntimeClass@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IUriRuntimeClass,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IUriRuntimeClass,wil::err_exception_policy>>(void)
0x18033649d  mov     rbx, [rbp+57h+var_48]
0x1803364a1  test    rbx, rbx
0x1803364a4  jz      loc_18033652B
0x1803364aa  mov     [rbp+57h+var_70], r15
0x1803364ae  mov     rax, [rbx]
0x1803364b1  mov     rdi, [rax+30h]
0x1803364b5  xor     ecx, ecx; string
0x1803364b7  call    cs:__imp_WindowsDeleteString
0x1803364be  nop     dword ptr [rax+rax+00h]
0x1803364c3  mov     [rbp+57h+var_70], r15
0x1803364c7  lea     rdx, [rbp+57h+var_70]
0x1803364cb  mov     rcx, rbx
0x1803364ce  mov     rax, rdi
0x1803364d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803364d6  mov     rcx, [rbp+5Fh]; this
0x1803364da  test    eax, eax
0x1803364dc  js      loc_18033672B
0x1803364e2  mov     rdi, [r14]
0x1803364e5  mov     rax, [rdi]
0x1803364e8  mov     rbx, [rax+0E0h]
0x1803364ef  xor     edx, edx; length
0x1803364f1  mov     rcx, [rbp+57h+var_70]; string
0x1803364f5  call    cs:__imp_WindowsGetStringRawBuffer
0x1803364fc  nop     dword ptr [rax+rax+00h]
0x180336501  mov     rdx, rax
0x180336504  mov     rcx, rdi
0x180336507  mov     rax, rbx
0x18033650a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033650f  mov     rcx, [rbp+5Fh]; this
0x180336513  test    eax, eax
0x180336515  js      loc_180336740
0x18033651b  mov     rcx, [rbp+57h+var_70]; string
0x18033651f  call    cs:__imp_WindowsDeleteString
0x180336526  nop     dword ptr [rax+rax+00h]
0x18033652b  mov     [rbp+57h+var_70], r15
0x18033652f  xor     edx, edx; length
0x180336531  mov     rcx, [rbp+57h+string]; string
0x180336535  call    cs:__imp_WindowsGetStringRawBuffer
0x18033653c  nop     dword ptr [rax+rax+00h]
0x180336541  lea     r8, [rbp+57h+var_70]; unsigned __int16 **
0x180336545  mov     rdx, rax; unsigned __int16 *
0x180336548  call    ?GetNamespaceCLSIDForSyncRoot@CSyncRootManagerStatics@@AEAAXPEBGPEAPEAG@Z; CSyncRootManagerStatics::GetNamespaceCLSIDForSyncRoot(ushort const *,ushort * *)
0x18033654d  xorps   xmm0, xmm0
0x180336550  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x180336554  lea     rdx, [rbp+57h+pclsid]; pclsid
0x180336558  mov     rcx, [rbp+57h+var_70]; lpsz
0x18033655c  call    cs:__imp_CLSIDFromString
0x180336563  nop     dword ptr [rax+rax+00h]
0x180336568  mov     rcx, [rbp+5Fh]; this
0x18033656c  test    eax, eax
0x18033656e  js      loc_180336755
0x180336574  mov     rcx, [r14]
0x180336577  mov     rax, [rcx]
0x18033657a  lea     rdx, [rbp+57h+pclsid]
0x18033657e  mov     rax, [rax+130h]
0x180336585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033658a  mov     rcx, [rbp+5Fh]; this
0x18033658e  test    eax, eax
0x180336590  js      short loc_180336605
0x180336592  lea     rcx, [rbp+57h+var_70]; void *
0x180336596  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18033659b  nop
0x18033659c  lea     rcx, [rbp+57h+var_48]
0x1803365a0  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x1803365a5  nop
0x1803365a6  mov     rcx, [rbp+57h+var_60]; string
0x1803365aa  call    cs:__imp_WindowsDeleteString
0x1803365b1  nop     dword ptr [rax+rax+00h]
0x1803365b6  mov     [rbp+57h+var_60], r15
0x1803365ba  mov     rcx, [rbp+57h+var_58]; string
0x1803365be  call    cs:__imp_WindowsDeleteString
0x1803365c5  nop     dword ptr [rax+rax+00h]
0x1803365ca  mov     [rbp+57h+var_58], r15
0x1803365ce  mov     rcx, [rbp+57h+string]; string
0x1803365d2  call    cs:__imp_WindowsDeleteString
0x1803365d9  nop     dword ptr [rax+rax+00h]
0x1803365de  mov     rax, r14
0x1803365e1  mov     rcx, [rbp+57h+var_30]
0x1803365e5  xor     rcx, rsp; StackCookie
0x1803365e8  call    __security_check_cookie
0x1803365ed  mov     rbx, [rsp+0D0h+arg_0]
0x1803365f5  add     rsp, 0B0h
0x1803365fc  pop     r15
0x1803365fe  pop     r14
0x180336600  pop     rdi
0x180336601  pop     rsi
0x180336602  pop     rbp
0x180336603  retn
0x180336605  mov     r9d, eax; char *
0x180336608  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18033660f  mov     edx, 3C7h; void *
0x180336614  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18033661a  mov     r9d, eax; char *
0x18033661d  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180336624  mov     edx, 393h; void *
0x180336629  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18033662f  mov     r9d, eax; char *
0x180336632  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180336639  mov     edx, 397h; void *
0x18033663e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180336644  mov     r9d, eax; char *
0x180336647  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18033664e  mov     edx, 398h; void *
0x180336653  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180336659  mov     r9d, eax; char *
0x18033665c  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180336663  mov     edx, 39Ch; void *
0x180336668  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18033666e  mov     r9d, eax; char *
0x180336671  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180336678  mov     edx, 39Dh; void *
0x18033667d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180336683  mov     r9d, eax; char *
0x180336686  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18033668d  mov     edx, 3A1h; void *
0x180336692  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180336698  mov     r9d, eax; char *
0x18033669b  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x1803366a2  mov     edx, 3A2h; void *
  ... truncated ...
```
